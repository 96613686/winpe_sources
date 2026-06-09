# RpcGetUserCertificates

- ea: `0x18005ed60`
- end: `0x18005efda`
- name: `RpcGetUserCertificates`
- size: `634`
- prototype: `__int64 __fastcall(__int64, unsigned int, _DWORD *, void **, _DWORD *)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800092f0`
- `0x18000a210`
- `0x18000bad0`
- `0x18000f1a0`
- `0x180013150`
- `0x1800321f0`
- `0x18003269c`
- `0x18005ed60`
- `0x1800c4e0c`
- `0x1800c8010`

## import_xrefs

- `RPCRT4!RpcRevertToSelf` at `0x18005ee62`
- `RPCRT4!RpcRevertToSelf` at `0x18005ef4d`
- `RPCRT4!RpcRevertToSelf` at `0x18005ee62`
- `RPCRT4!RpcRevertToSelf` at `0x18005ef4d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005eef2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005eef2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005ef8d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005ef8d`

## string_xrefs

- `0x18005eec7`: `GetSecurityFilterClientCert failed: 0x%x in %s`

## pseudocode

```c

```
