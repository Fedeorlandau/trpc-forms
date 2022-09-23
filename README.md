# trpc-rhf

A tRPC integration with react-hook-form to use form with as little friction as possible.

> **Warning**
>
> This is a work in progress and is not ready for production use.

## Installation

```bash
npx install trpc-forms @trpc/react react-hook-form zod
```

## Usage

```tsx
import { trpc } from "~/utils/trpc";
import { useTRPCForm } from "trpc-forms";

const App = () => {
  // 🤯 Pass your mutation to the hook
  const { register, handleSubmit } = useTRPCForm(trpc.post.create, {
    // 🧩 Use your ordinary trpc mutation options
    onMutate() {
      // ...
    },
    onSuccess() {
      // ...
    },
  });

  return (
    <form onSubmit={methods.handleSubmit}>
      {/* use the ordinary react-hook-form methods */}
      <input {...register("title")} />
      <input {...register("body")} />
      <button type="submit">Submit</button>
    </form>
  );
};
```
