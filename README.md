# Next.js 15 useRouter Hook Issue in Non-Page Components

This repository demonstrates a subtle bug in Next.js 15 related to the `useRouter` hook from `next/navigation`.  The hook functions unexpectedly when used within a component that's not a direct child of a page component.

## Problem Description

The `useRouter` hook relies on the routing context established by Next.js's page-based routing system.  If you use this hook in a component rendered outside of the typical page structure (e.g., a component used within a shared layout or a dynamically imported component), it may not receive the full routing information and lead to unpredictable behavior such as incorrect routes or failures to update the UI after navigation.

## Solution

The provided solution demonstrates how to resolve this issue by ensuring that the `useRouter` hook is used within the correct routing context.  This typically means using it only within page components or within components that are rendered by a page component.