# TpmPolicySession::GetTpmTicket(unsigned __int64,int,uchar const *,ulong,uchar const *,ulong,uchar const *,ulong,uchar * *,ulong *)

- ea: `0x18003a51c`
- end: `0x18003a795`
- name: `?GetTpmTicket@TpmPolicySession@@YAJ_KHPEBEK1K1KPEAPEAEPEAK@Z`
- size: `633`
- prototype: `__int64 __usercall@<rax>(NCRYPT_HANDLE hObject@<rcx>, unsigned __int64@<rdx>, int@<r8d>, const unsigned __int8 *@<r9>, void *Source, rsize_t SourceSize, void *, const unsigned __int8 *, unsigned int, unsigned __int8 **, unsigned int *)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180053704`
- `0x1800538d4`

## callees

- `0x1800351e0`
- `0x18003a51c`
- `0x18005388c`
- `0x180053fb0`
- `0x1800586d0`
- `0x180068f60`
- `0x180069c3a`
- `0x180069cc8`
- `0x18006b0b5`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18003a723`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18003a785`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18003a723`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18003a785`
- `ncrypt!NCryptGetProperty` at `0x18003a65f`
- `ncrypt!NCryptGetProperty` at `0x18003a6be`
- `ncrypt!NCryptGetProperty` at `0x18003a65f`
- `ncrypt!NCryptGetProperty` at `0x18003a6be`
- `ncrypt!NCryptSetProperty` at `0x18003a60e`
- `ncrypt!NCryptSetProperty` at `0x18003a60e`

## string_xrefs

- `0x18003a625`: `onecore\ds\security\biometrics\service\trustlet\lib\tpmpolicysession.cpp`
- `0x18003a676`: `onecore\ds\security\biometrics\service\trustlet\lib\tpmpolicysession.cpp`
- `0x18003a6d5`: `onecore\ds\security\biometrics\service\trustlet\lib\tpmpolicysession.cpp`
- `0x18003a744`: `onecore\ds\security\biometrics\service\trustlet\lib\tpmpolicysession.cpp`

## pseudocode

```c

```
