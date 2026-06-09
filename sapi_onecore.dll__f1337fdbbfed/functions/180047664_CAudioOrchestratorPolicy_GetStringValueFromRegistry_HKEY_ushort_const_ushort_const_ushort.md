# CAudioOrchestratorPolicy::GetStringValueFromRegistry(HKEY__ *,ushort const *,ushort const *,ushort * *)

- ea: `0x180047664`
- end: `0x180047854`
- name: `?GetStringValueFromRegistry@CAudioOrchestratorPolicy@@CAJPEAUHKEY__@@PEBG1PEAPEAG@Z`
- size: `496`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpSubKey, LPCWSTR lpValueName, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800c4230`

## callees

- `0x18000a590`
- `0x180016c20`
- `0x18001fdac`
- `0x180046f00`
- `0x180047664`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800477ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800477e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800477ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800477e7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180047705`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180047769`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180047705`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180047769`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800476b7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800476b7`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800477a0`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800477da`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800477a0`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800477da`

## pseudocode

```c

```
