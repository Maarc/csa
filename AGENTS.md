# Agent Guidelines for Cloud Suitability Analyzer (CSA)

## Build & Test Commands
- **Full build**: `./build.sh` (builds Go backend + Angular frontend + generates binaries)
- **Go tests (all)**: `cd csa-app && go test ./...`
- **Go test (single package)**: `cd csa-app && go test ./db -v`
- **Go test (single test)**: `cd csa-app && go test ./csa -run TestCanRecalculateSamplePortfolio -v`
- **Frontend tests**: `cd csa-app/frontend && npm test`
- **Frontend build**: `cd csa-app/frontend && npm run production-build`
- **Rule tests**: `cd csa-app/tests && go test -v`

## Code Style - Go
- **Copyright header**: All files must include VMware BSD-2 license header (see existing files)
- **Imports**: Use `csa-app/<package>` for internal imports (e.g., `csa-app/db`, `csa-app/model`)
- **Naming**: PascalCase for exported types/functions, camelCase for unexported
- **Error handling**: Always check errors; use `util.TrackError()` for logging; support `*util.FailFast` flag
- **Testing**: Use `github.com/stretchr/testify/assert` for assertions; test files use `package_test` naming
- **Logging**: Use `util.WriteLog()` for verbose logging; respect `*util.Verbose` flag

## Code Style - Angular/TypeScript
- **Framework**: Angular 16, TypeScript 4.9
- **UI**: Clarity Design System (@clr/angular)
- **Testing**: Jasmine/Karma
- **Build**: Production builds use `ng build --configuration production`
