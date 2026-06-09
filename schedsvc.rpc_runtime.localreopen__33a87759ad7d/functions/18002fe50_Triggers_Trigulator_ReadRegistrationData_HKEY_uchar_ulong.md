# Triggers::Trigulator::ReadRegistrationData(HKEY__ *,uchar *,ulong)

- ea: `0x18002fe50`
- end: `0x180030f6d`
- name: `?ReadRegistrationData@Trigulator@Triggers@@AEAAJPEAUHKEY__@@PEAEK@Z`
- size: `4381`
- prototype: `int(Triggers::Trigulator *__hidden this, HKEY, unsigned __int8 *, unsigned int)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000c3c0`
- `0x1800199c0`

## callees

- `0x18000dc30`
- `0x18001a260`
- `0x18001b070`
- `0x18002fe50`
- `0x180030f80`
- `0x180043d78`
- `0x180052118`
- `0x180056794`
- `0x18005790c`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18002ffec`
- `OLEAUT32!__imp_SysAllocString` at `0x18003008e`
- `OLEAUT32!__imp_SysAllocString` at `0x180030130`
- `OLEAUT32!__imp_SysAllocString` at `0x1800301d5`
- `OLEAUT32!__imp_SysAllocString` at `0x18003027d`
- `OLEAUT32!__imp_SysAllocString` at `0x180030325`
- `OLEAUT32!__imp_SysAllocString` at `0x18003050d`
- `OLEAUT32!__imp_SysAllocString` at `0x180030545`
- `OLEAUT32!__imp_SysAllocString` at `0x1800305ca`
- `OLEAUT32!__imp_SysAllocString` at `0x18002ffec`
- `OLEAUT32!__imp_SysAllocString` at `0x18003008e`
- `OLEAUT32!__imp_SysAllocString` at `0x180030130`
- `OLEAUT32!__imp_SysAllocString` at `0x1800301d5`
- `OLEAUT32!__imp_SysAllocString` at `0x18003027d`
- `OLEAUT32!__imp_SysAllocString` at `0x180030325`
- `OLEAUT32!__imp_SysAllocString` at `0x18003050d`
- `OLEAUT32!__imp_SysAllocString` at `0x180030545`
- `OLEAUT32!__imp_SysAllocString` at `0x1800305ca`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002feb9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002ff70`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003002e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800300d0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180030172`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003021a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800302c2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003036a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800303e3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003045a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800307b5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800308b5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800309af`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180030aa9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180030ba3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180030c9d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180030d97`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180030e4d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180030f05`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002feb9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002ff70`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003002e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800300d0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180030172`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003021a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800302c2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003036a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800303e3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003045a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800307b5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800308b5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800309af`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180030aa9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180030ba3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180030c9d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180030d97`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180030e4d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180030f05`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800304b7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800306ce`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800304b7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800306ce`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002ffc3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180030065`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180030107`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800301ac`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180030254`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800302fc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002ffc3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180030065`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180030107`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800301ac`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180030254`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800302fc`

## string_xrefs

- `0x1800300c6`: `SecurityDescriptor`
- `0x1800309a5`: `SecurityDescriptor`
- `0x1800309fa`: `SecurityDescriptor`

## pseudocode

```c

```
