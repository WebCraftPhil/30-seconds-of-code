---
title: React useUpdate hook
type: snippet
language: react
tags: [components,reducer]
cover: lavender-shelf
dateModified: 2021-09-24
---

Forces the component to re-render when called.

- Use the `useReducer()` hook that creates a new object every time it's updated and return its dispatch.

```jsx
const useUpdate = () => {
  const [, update] = React.useReducer(() => ({}));
  return update;
};
```

```jsx
const MyApp = () => {
  const update = useUpdate();

  return (
    <>
      <div>Time: {Date.now()}</div>
      <button onClick={update}>Update</button>
    </>
  );
};

ReactDOM.createRoot(document.getElementById('root')).render(
  <MyApp />
);
```
