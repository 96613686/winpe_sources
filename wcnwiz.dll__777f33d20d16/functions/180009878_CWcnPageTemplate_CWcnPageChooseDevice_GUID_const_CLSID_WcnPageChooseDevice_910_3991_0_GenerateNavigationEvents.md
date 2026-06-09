# CWcnPageTemplate<CWcnPageChooseDevice,&_GUID const CLSID_WcnPageChooseDevice,910,3991,0>::GenerateNavigationEvents(CWcnPageChooseDevice *,uint,unsigned __int64,__int64,__int64 &)

- ea: `0x180009878`
- end: `0x1800099ad`
- name: `?GenerateNavigationEvents@?$CWcnPageTemplate@VCWcnPageChooseDevice@@$1?CLSID_WcnPageChooseDevice@@3U_GUID@@B$0DIO@$0PJH@$0A@@@SAHPEAVCWcnPageChooseDevice@@I_K_JAEA_J@Z`
- size: `309`
- prototype: `__int64 __usercall@<rax>(CWcnPageChooseDevice *this@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000a7d8`

## callees

- `0x180009878`
- `0x18000eec4`
- `0x18000efe4`
- `0x18000f020`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000991a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000991a`
- `USER32!PostMessageW` at `0x18000990f`
- `USER32!PostMessageW` at `0x18000990f`
- `USER32!KillTimer` at `0x18000995c`
- `USER32!KillTimer` at `0x18000995c`

## pseudocode

```c

```
