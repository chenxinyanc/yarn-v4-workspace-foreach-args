# yarn-v4-workspace-foreach-args

## Get started

Make sure you have installed yarn.

```powershell
> npm i -g yarn
```

Execute the workspace-level command `print-args-bar` with yarn

```powershell
> yarn print-args-bar
```

Note that `print-args-bar` iterates over all the workspace packages and run `print-args` script on them.

In addition to package-a & package-b, You will see (maybe a bit surprisingly) `yarn workspaces foreach --all`
is also applied to the workspace root (`my-workspace`):

```log
[my-workspace]: Process started
[my-workspace]: package-cli::echo-args has been invoked with args [
[my-workspace]:   'C:\\Program Files\\nodejs\\node.exe',
[my-workspace]:   'D:\\repos-oss\\yarn-v4-workspace-foreach-args\\packages\\package-cli\\index.js',
[my-workspace]:   'foo',
[my-workspace]:   'bar'
[my-workspace]: ]
[my-workspace]: cwd D:\repos-oss\yarn-v4-workspace-foreach-args\packages\package-a
[my-workspace]: ----------
[my-workspace]: 
[my-workspace]: package-cli::echo-args has been invoked with args [
[my-workspace]:   'C:\\Program Files\\nodejs\\node.exe',
[my-workspace]:   'D:\\repos-oss\\yarn-v4-workspace-foreach-args\\packages\\package-cli\\index.js',
[my-workspace]:   'foo',
[my-workspace]:   'bar'
[my-workspace]: ]
[my-workspace]: cwd D:\repos-oss\yarn-v4-workspace-foreach-args\packages\package-b
[my-workspace]: ----------
[my-workspace]: 
[my-workspace]: Done in 0s 259ms
[my-workspace]: Process exited (exit code 0), completed in 0s 615ms

[package-a]: Process started
[package-a]: package-cli::echo-args has been invoked with args [
[package-a]:   'C:\\Program Files\\nodejs\\node.exe',
[package-a]:   'D:\\repos-oss\\yarn-v4-workspace-foreach-args\\packages\\package-cli\\index.js',
[package-a]:   'bar'
[package-a]: ]
[package-a]: cwd D:\repos-oss\yarn-v4-workspace-foreach-args\packages\package-a
[package-a]: ----------
[package-a]:
[package-a]: Process exited (exit code 0), completed in 0s 133ms

[package-b]: Process started
[package-b]: package-cli::echo-args has been invoked with args [
[package-b]:   'C:\\Program Files\\nodejs\\node.exe',
[package-b]:   'D:\\repos-oss\\yarn-v4-workspace-foreach-args\\packages\\package-cli\\index.js',
[package-b]:   'bar'
[package-b]: ]
[package-b]: cwd D:\repos-oss\yarn-v4-workspace-foreach-args\packages\package-b
[package-b]: ----------
[package-b]:
[package-b]: Process exited (exit code 0), completed in 0s 124ms
Done in 0s 879ms
```
