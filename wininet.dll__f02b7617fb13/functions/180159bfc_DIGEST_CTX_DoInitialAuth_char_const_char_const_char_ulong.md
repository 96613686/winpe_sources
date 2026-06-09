# DIGEST_CTX::DoInitialAuth(char const *,char const *,char *,ulong *)

- ea: `0x180159bfc`
- end: `0x18015a051`
- name: `?DoInitialAuth@DIGEST_CTX@@AEAAKPEBD0PEADPEAK@Z`
- size: `1109`
- prototype: `unsigned int __usercall@<eax>(DIGEST_CTX *__hidden this@<rcx>, const char *@<rdx>, const char *@<r8>, char *@<r9>, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18015a550`

## callees

- `0x1800701d0`
- `0x1800e66ec`
- `0x1800e77f8`
- `0x1800fc53c`
- `0x180138484`
- `0x18014a7a0`
- `0x180159bfc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180159cc6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180159d35`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180159cc6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180159d35`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180159d82`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180159d99`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180159dcc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180159d82`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180159d99`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180159dcc`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180159caf`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180159cf3`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180159d1e`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180159d5c`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180159caf`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180159cf3`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180159d1e`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180159d5c`
- `SspiCli!AcquireCredentialsHandleW` at `0x180159eb6`
- `SspiCli!AcquireCredentialsHandleW` at `0x180159eb6`
- `SspiCli!InitializeSecurityContextW` at `0x18015a003`
- `SspiCli!InitializeSecurityContextW` at `0x18015a003`

## pseudocode

```c

```
