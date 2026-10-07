# Notes

## Fixes

- Fixed SQL operator precedence in the Spring Data repository, H2 reference query, and Oracle package. Parentheses now ensure archived and status filters apply consistently to both title and description matches.
- Removed the artificial `Thread.sleep()` from task search. The delay blocked request threads based on query length and added unnecessary latency.
- Fixed the frontend task loading/error state. Errors are cleared when a new request starts, and loading is always stopped using `finally`, including when the request fails.

## Verification

- Backend: `.\mvnw.cmd test` passed successfully.
- Frontend: `npm run build` passed successfully.
- `git diff --check` completed without whitespace errors.
- No automated backend tests were present in the repository.

## Scope

Only the identified high-value issues were changed. No unrelated functionality was modified.