# EdpHelpers::GetEnterpriseIdForWindow(HWND__ *,ushort * *)

- ea: `0x180334a70`
- end: `0x180334c64`
- name: `?GetEnterpriseIdForWindow@EdpHelpers@@YAJPEAUHWND__@@PEAPEAG@Z`
- size: `500`
- prototype: `__int64 __fastcall(EdpHelpers *__hidden this, HWND, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1801b9750`
- `0x180390e90`

## callees

- `0x18001bbc0`
- `0x18001d664`
- `0x1800237c8`
- `0x1800c1b9c`
- `0x1800c1c00`
- `0x18014b060`
- `0x180180a9c`
- `0x180193de0`
- `0x180193e68`
- `0x180334a70`
- `0x180334c6c`
- `0x180391798`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180334aae`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180334aae`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180334ac5`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180334ac5`
- `api-ms-win-core-debug-l1-1-1!CheckRemoteDebuggerPresent` at `0x180334adb`
- `api-ms-win-core-debug-l1-1-1!CheckRemoteDebuggerPresent` at `0x180334adb`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x180334a97`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x180334a97`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetContextForWindow` at `0x180334b21`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetContextForWindow` at `0x180334b21`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetContextForBinaryPath` at `0x180334b91`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetContextForBinaryPath` at `0x180334b91`
- `ext-ms-win-edputil-policy-l1-1-0!EdpFreeContext` at `0x180334b72`
- `ext-ms-win-edputil-policy-l1-1-0!EdpFreeContext` at `0x180334b72`

## pseudocode

```c

```
