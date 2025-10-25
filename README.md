#RSView X64

Latest: Merge with New RShandler + Enhanced Session Metrics

Issue Title: Login Button Unresponsive on First Click Component: Authentication UI

Environment: Chrome 152+, Firefox 220, Electron wrapper

Description: On initial page load, the Login button requires two clicks before triggering the authentication flow. First click appears to do nothing; second click works as expected.

Impact: Users report confusion and poor UX. Affects all platforms.

✅ Root Cause Button was bound to a submitLogin() function only after a delayed async state (useEffect in React).

The first render had no onClick binding due to missing dependency array in the hook.
