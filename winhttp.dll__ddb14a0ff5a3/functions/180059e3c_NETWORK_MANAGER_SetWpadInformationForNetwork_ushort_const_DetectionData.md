# NETWORK_MANAGER::SetWpadInformationForNetwork(ushort const *,_DetectionData *)

- ea: `0x180059e3c`
- end: `0x18005a02a`
- name: `?SetWpadInformationForNetwork@NETWORK_MANAGER@@AEAAKPEBGPEAU_DetectionData@@@Z`
- size: `494`
- prototype: `unsigned int __fastcall(NETWORK_MANAGER *__hidden this, LPCWSTR lpSubKey, struct _DetectionData *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180059b58`

## callees

- `0x180056fcc`
- `0x180059e3c`
- `0x18005a030`
- `0x18005a1f0`
- `0x1800a1d10`
- `0x1800cf008`
- `0x1800db6b0`
- `0x1800dbccc`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180059f25`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180059f25`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180059f4d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180059fde`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180059f4d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180059fde`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180059ed4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180059ed4`

## pseudocode

```c

```
