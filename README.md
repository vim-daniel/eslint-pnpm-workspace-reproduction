1. make sure you have pnpm >6.32 (tested with `6.32.21`)
2. pnpm install
3. ```bash
   cd services/example
   pnpm run lint
   ```
4. should output

   ```bash
   > example@1.0.0 lint eslint-pnpm-workspace-reproduction/services/example
   > eslint src


   eslint-pnpm-workspace-reproduction/services/example/src/index.ts
   2:19  error  'unused' is defined but never used. Allowed unused args must match /^_/u  @typescript-eslint/no-unused-vars

   ✖ 1 problem (1 error, 0 warnings)

    ELIFECYCLE  Command failed with exit code 1.
   ```

5. go over to index.ts file -> no errors from eslint extension, extension output contains following logs:
   ```js
   Uncaught exception received.
   Error: Failed to load plugin '@typescript-eslint' declared in 'services/example/.eslintrc » eslint-config-shared': Cannot find module '@typescript-eslint/eslint-plugin'
   Require stack:
   - /eslint-pnpm-workspace-reproduction/services/example/__placeholder__.js
   Referenced from: /eslint-pnpm-workspace-reproduction/dev-tools/shared-lint/index.js
   ```
