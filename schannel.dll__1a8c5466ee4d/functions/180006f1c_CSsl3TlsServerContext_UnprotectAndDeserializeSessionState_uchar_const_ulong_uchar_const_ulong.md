# CSsl3TlsServerContext::UnprotectAndDeserializeSessionState(uchar * const,ulong,uchar * const,ulong)

- ea: `0x180006f1c`
- end: `0x180007160`
- name: `?UnprotectAndDeserializeSessionState@CSsl3TlsServerContext@@QEAAEQEAEKQEAEK@Z`
- size: `580`
- prototype: `unsigned __int8 __usercall@<al>(CSsl3TlsServerContext *__hidden this@<rcx>, unsigned __int8 *const@<rdx>, unsigned int@<r8d>, unsigned __int8 *const@<r9>, unsigned int)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180007b50`
- `0x18007fca8`

## callees

- `0x180006f1c`
- `0x180008bc0`
- `0x1800194c0`
- `0x180019650`
- `0x180021da8`
- `0x18003f740`
- `0x180041390`
- `0x180072b68`
- `0x180076b98`
- `0x18007a5a4`
- `0x180091010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000710a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000710a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180007071`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180007071`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180007002`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180007002`

## pseudocode

```c

```
