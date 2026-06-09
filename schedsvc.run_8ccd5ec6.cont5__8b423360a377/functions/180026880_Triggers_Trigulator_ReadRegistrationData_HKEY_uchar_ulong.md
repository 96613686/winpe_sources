# Triggers::Trigulator::ReadRegistrationData(HKEY__ *,uchar *,ulong)

- ea: `0x180026880`
- end: `0x180027908`
- name: `?ReadRegistrationData@Trigulator@Triggers@@AEAAJPEAUHKEY__@@PEAEK@Z`
- size: `4232`
- prototype: `int(Triggers::Trigulator *__hidden this, HKEY, unsigned __int8 *, unsigned int)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800104c0`
- `0x180015030`

## callees

- `0x18000cc40`
- `0x18000d830`
- `0x180011e40`
- `0x180026880`
- `0x180027910`
- `0x180045d1c`
- `0x180054824`
- `0x180059140`
- `0x18005a2bc`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180026a2f`
- `OLEAUT32!__imp_SysAllocString` at `0x180026ef1`
- `OLEAUT32!__imp_SysAllocString` at `0x180026f2f`
- `OLEAUT32!__imp_SysAllocString` at `0x180026f6d`
- `OLEAUT32!__imp_SysAllocString` at `0x180026fab`
- `OLEAUT32!__imp_SysAllocString` at `0x180026fe9`
- `OLEAUT32!__imp_SysAllocString` at `0x180027027`
- `OLEAUT32!__imp_SysAllocString` at `0x180027065`
- `OLEAUT32!__imp_SysAllocString` at `0x1800270f0`
- `OLEAUT32!__imp_SysAllocString` at `0x180026a2f`
- `OLEAUT32!__imp_SysAllocString` at `0x180026ef1`
- `OLEAUT32!__imp_SysAllocString` at `0x180026f2f`
- `OLEAUT32!__imp_SysAllocString` at `0x180026f6d`
- `OLEAUT32!__imp_SysAllocString` at `0x180026fab`
- `OLEAUT32!__imp_SysAllocString` at `0x180026fe9`
- `OLEAUT32!__imp_SysAllocString` at `0x180027027`
- `OLEAUT32!__imp_SysAllocString` at `0x180027065`
- `OLEAUT32!__imp_SysAllocString` at `0x1800270f0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800268e9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800269a7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180026a77`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180026af0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180026b69`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180026be8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180026c67`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180026ce6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180026d65`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180026de2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180027272`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180027374`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180027430`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800274ec`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800275a8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180027664`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180027720`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800277dc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002789a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800268e9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800269a7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180026a77`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180026af0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180026b69`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180026be8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180026c67`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180026ce6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180026d65`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180026de2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180027272`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180027374`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180027430`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800274ec`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800275a8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180027664`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180027720`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800277dc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002789a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180026e45`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002719e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180026e45`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002719e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180026a00`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180026a00`

## string_xrefs

- `0x180026ae6`: `SecurityDescriptor`
- `0x180027426`: `SecurityDescriptor`
- `0x180027481`: `SecurityDescriptor`

## pseudocode

```c

```
