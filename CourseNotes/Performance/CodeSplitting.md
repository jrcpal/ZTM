# Code Splitting

## What is Code Splitting?

Code splitting is a technique used to improve the performance of web applications by breaking down the code into smaller, more manageable pieces, or "chunks". This allows the application to load only the necessary code for the initial render, and defer loading other parts of the code until they are needed.

## Benefits of Code Splitting

- **Improved Load Time**: By loading only the essential code initially, the application can start faster, improving the user experience.
- **Reduced Bundle Size**: Smaller chunks mean that the browser has to download less code upfront, which can be particularly beneficial for users with slow internet connections.
- **Better Caching**: Since chunks are loaded separately, they can be cached independently. This means that if only a part of the application changes, only the corresponding chunk needs to be re-downloaded.

## How Code Splitting Works

Rather than importing all components at the top of the page, code splitting allows you to dynamically import components as they are needed. This can be done using dynamic `import()` statements.

### Example

```javascript
// Before code splitting
import ComponentA from './ComponentA';
import ComponentB from './ComponentB';

function App() {
  return (
    <div>
      <ComponentA />
      <ComponentB />
    </div>
  );
}

export default App;

// After code splitting
import React, { Suspense, lazy } from 'react';

const ComponentA = lazy(() => import('./ComponentA'));
const ComponentB = lazy(() => import('./ComponentB'));

function App() {
  return (
    <div>
      <Suspense fallback={<div>Loading...</div>}>
        <ComponentA />
        <ComponentB />
      </Suspense>
    </div>
  );
}

export default App;