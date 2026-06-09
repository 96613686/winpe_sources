# CWcnPageTemplate<CWcnPageTransferFailed,&_GUID const CLSID_WcnPageTransferFailed,521,3312,0>::GenerateNavigationEvents(CWcnPageTransferFailed *,uint,unsigned __int64,__int64,__int64 &)

- ea: `0x18000a018`
- end: `0x18000a105`
- name: `?GenerateNavigationEvents@?$CWcnPageTemplate@VCWcnPageTransferFailed@@$1?CLSID_WcnPageTransferFailed@@3U_GUID@@B$0CAJ@$0MPA@$0A@@@SAHPEAVCWcnPageTransferFailed@@I_K_JAEA_J@Z`
- size: `237`
- prototype: `__int64 __usercall@<rax>(CWcnPageTransferFailed *this@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000ae20`

## callees

- `0x18000a018`
- `0x180013984`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000a0b2`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000a0b2`
- `USER32!PostMessageW` at `0x18000a0aa`
- `USER32!PostMessageW` at `0x18000a0aa`
- `USER32!KillTimer` at `0x18000a0f2`
- `USER32!KillTimer` at `0x18000a0f2`

## pseudocode

```c

```
