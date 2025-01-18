# Tailwind CSS SSR Bug: Undefined Classes Rendered Incorrectly

This repository demonstrates a common bug encountered when using Tailwind CSS with server-side rendering (SSR) frameworks like Next.js or Nuxt.js.  The bug arises from undefined Tailwind classes not being properly handled during the build process, leading to them being output literally in the HTML rather than being replaced with their compiled styles.

## The Bug

The `bug.js` file shows an example of how an undefined Tailwind class renders incorrectly in the HTML.  This example uses a class `bg-custom-blue`, which isn't defined in `tailwind.config.js`.  The result is that `bg-custom-blue` is output directly, failing to apply any styling.

## The Solution

The `bugSolution.js` file provides a solution by correctly defining the `bg-custom-blue` class in `tailwind.config.js` or ensuring that JIT mode is properly configured.  This ensures that Tailwind processes the class correctly during the build process, resulting in the expected styling.  If not using JIT mode, ensure that your `tailwind.config.js` includes `content` array pointing to all files that use Tailwind classes.