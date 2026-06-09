# TpmPolicySession::GetPolicyInfo(unsigned __int64,uchar const *,ulong,uchar * *,ulong *)

- ea: `0x1800b87e4`
- end: `0x1800b8931`
- name: `?GetPolicyInfo@TpmPolicySession@@YAJ_KPEBEKPEAPEAEPEAK@Z`
- size: `333`
- prototype: `__int64 __usercall@<rax>(NCRYPT_HANDLE hObject@<rcx>, PBYTE pbInput@<rdx>, DWORD cbInput@<r8d>, unsigned int@<r9d>, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800538d4`

## callees

- `0x18005388c`
- `0x180058680`
- `0x1800b87e4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b88fc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b88fc`
- `ncrypt!NCryptGetProperty` at `0x1800b8864`
- `ncrypt!NCryptGetProperty` at `0x1800b88c4`
- `ncrypt!NCryptGetProperty` at `0x1800b8864`
- `ncrypt!NCryptGetProperty` at `0x1800b88c4`
- `ncrypt!NCryptSetProperty` at `0x1800b880e`
- `ncrypt!NCryptSetProperty` at `0x1800b880e`

## string_xrefs

- `0x1800b8822`: `onecore\ds\security\biometrics\service\trustlet\lib\tpmpolicysession.cpp`
- `0x1800b8878`: `onecore\ds\security\biometrics\service\trustlet\lib\tpmpolicysession.cpp`
- `0x1800b88d8`: `onecore\ds\security\biometrics\service\trustlet\lib\tpmpolicysession.cpp`

## pseudocode

```c

```
