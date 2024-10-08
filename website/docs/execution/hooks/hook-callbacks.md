---
sidebar_position: 5
description: Hook callbacks are a way to perform custom logic based on the current action execution status.
---

# Hook callbacks

Hook callbacks are a way to perform custom logic based on the current action execution status. You can provide them to the three hooks in the `utils` object, which is the second argument. All of them are optional:

```tsx
const action = useAction(testAction, {
  onExecute: ({ input }) => {},
  onSuccess: ({ data, input }) => {},
  onError: ({ error, input }) => {},
  onSettled: ({ result, input }) => {},
});
```

Here is the full list of callbacks, with their behavior explained. All of them are optional and have return type `void` or `Promise<void>` (async or non-async functions with no return):

| Name         | [`HookActionStatus`](/docs/types#hookactionstatus) state                 |
| ------------ | -----------------------------------------------------------------------  |
| `onExecute?` | `"executing"`                                                            |
| `onSuccess?` | `"hasSucceeded"`                                                         |
| `onError?`   | `"hasErrored"`                                                           | 
| `onSettled?` | `"hasSucceeded"` or `"hasErrored"`                                       |