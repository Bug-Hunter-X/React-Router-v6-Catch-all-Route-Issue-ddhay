# React Router v6 Catch-all Route Issue

This repository demonstrates a common issue with catch-all routes (`/*`) in React Router v6.  The problem is that the catch-all route sometimes fails to catch unmatched routes, leading to unexpected behavior or rendering issues.

## Problem Description
The catch-all route is intended to handle any URL path that doesn't match other defined routes.  However, in certain scenarios, it fails to function as expected, causing unmatched routes to result in blank screens or unexpected rendering.

## Solution
Ensure that the catch-all route (`/*`) is placed *after* all other routes within the `<Routes>` component. This change guarantees that it only matches paths not covered by more specific routes.  React Router processes routes sequentially; thus the order matters.

## Reproduction
Clone the repository, and run `npm install` to install dependencies.  Then run `npm start` to launch the application.
You'll notice that while `/` and `/about` are handled correctly, other URLs (e.g. `/invalid-route`) don't render the NotFound component.  The corrected solution fixes this.