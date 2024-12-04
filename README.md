# React Router v6 Catch-All Route Unexpected Behavior

This repository demonstrates an issue with the catch-all route (`/*`) in React Router v6. The catch-all route, intended to handle unmatched paths, unexpectedly overrides more specific routes. 

## Problem

In the provided `App.js`, a catch-all route (`/*`) is added after more specific routes (`/` and `/about`).  Because of the order and the nature of the catch-all route, it always matches, even if a more specific path exists. This means that even if you visit `/about`, the `NotFound` component will render instead of `About`. 

## Solution

The solution in `AppSolution.js` restructures the routes to place the catch-all route at the very end of the `Routes` component.  This ensures it only matches paths that don't match any more specific routes.