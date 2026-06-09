# ReadSecurityDescriptorFromSDDL(HKEY__ *,ushort *,bool,CSecDescriptor * *)

- ea: `0x1800e9e78`
- end: `0x1800ea203`
- name: `?ReadSecurityDescriptorFromSDDL@@YAKPEAUHKEY__@@PEAG_NPEAPEAVCSecDescriptor@@@Z`
- size: `907`
- prototype: `unsigned int __fastcall(HKEY hKey, LPCWSTR lpValueName, bool, struct CSecDescriptor **)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800456f8`

## callees

- `0x180034540`
- `0x18005f3a0`
- `0x180081210`
- `0x1800e9e78`
- `0x1800ea20c`
- `0x18010a084`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800ea040`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800ea058`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800ea040`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800ea058`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ea0a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ea0a7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800ea1a3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800ea1cd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800ea1a3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800ea1cd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800e9f33`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800ea11d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800e9f33`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800ea11d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800e9ec3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800e9f64`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800e9ec3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800e9f64`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x1800ea109`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x1800ea109`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800ea074`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800ea074`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1800ea1b2`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1800ea1b2`

## string_xrefs

- `0x1800e9f15`: `onecore\com\combase\rpcss\olescm\registry.cxx`
- `0x1800ea18b`: `onecore\com\combase\rpcss\olescm\registry.cxx`
- `0x1800e9f03`: `ReadSecurityDescriptorFromSDDL`
- `0x1800ea184`: `ReadSecurityDescriptorFromSDDL`

## pseudocode

```c

```
