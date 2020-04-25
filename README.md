# hooks

Developer Network Git Hooks

## pre-commit

The pre-commit hook is currently setup to execute a set of Golang linters
against repositories containing Go code. Each linter is capable of failing
a commit.

Along with the linters this pre-commit hook also executes a `go mod tidy`
against the module if the go.mod file exists at the root of the directory. It
also checks the `go.mod` file for `replace` directives and will fail the commit
if the developer accidentally left a `replace` directive in the mod file.

## post-merge

The post-merge hook is setup to do a recursive update of all submodules in the
git repository.
