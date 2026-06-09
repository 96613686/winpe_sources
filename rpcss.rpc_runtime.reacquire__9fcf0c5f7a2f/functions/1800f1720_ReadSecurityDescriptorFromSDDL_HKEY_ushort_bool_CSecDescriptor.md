# ReadSecurityDescriptorFromSDDL(HKEY__ *,ushort *,bool,CSecDescriptor * *)

- ea: `0x1800f1720`
- end: `0x1800f1af4`
- name: `?ReadSecurityDescriptorFromSDDL@@YAKPEAUHKEY__@@PEAG_NPEAPEAVCSecDescriptor@@@Z`
- size: `980`
- prototype: `unsigned int __fastcall(HKEY hKey, LPCWSTR lpValueName, bool, struct CSecDescriptor **)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18003afb8`

## callees

- `0x180034260`
- `0x180064614`
- `0x1800855d8`
- `0x1800f1720`
- `0x1800f1afc`
- `0x180112d84`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800f18fa`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800f1918`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800f18fa`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800f1918`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f1973`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f1973`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800f1a81`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800f1ab7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800f1a81`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800f1ab7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800f17e1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800f19f5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800f17e1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800f19f5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800f176b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800f1818`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800f176b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800f1818`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x1800f19db`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x1800f19db`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800f193a`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800f193a`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1800f1a96`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1800f1a96`

## string_xrefs

- `0x1800f17c3`: `onecore\com\combase\rpcss\olescm\registry.cxx`
- `0x1800f1a69`: `onecore\com\combase\rpcss\olescm\registry.cxx`
- `0x1800f17b1`: `ReadSecurityDescriptorFromSDDL`
- `0x1800f1a62`: `ReadSecurityDescriptorFromSDDL`

## pseudocode

```c

```
