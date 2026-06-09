# CallerIdentity::_EnsureRuntimeBrokerPID(void)

- ea: `0x180104b28`
- end: `0x180104bf7`
- name: `?_EnsureRuntimeBrokerPID@CallerIdentity@@YAXXZ`
- size: `207`
- prototype: `void __fastcall(CallerIdentity *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003aa08`

## callees

- `0x18008a030`
- `0x1800ea2d0`
- `0x180104b28`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180104bcb`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180104bcb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180104b50`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180104b50`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180104bbd`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180104bbd`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180104b98`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180104b98`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180104b73`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180104b73`

## string_xrefs

- `0x180104b91`: `%SystemRoot%\System32\RuntimeBroker.exe`

## pseudocode

```c

```
