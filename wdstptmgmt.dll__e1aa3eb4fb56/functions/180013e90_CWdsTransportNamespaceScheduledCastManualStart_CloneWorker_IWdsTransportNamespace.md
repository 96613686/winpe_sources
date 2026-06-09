# CWdsTransportNamespaceScheduledCastManualStart::CloneWorker(IWdsTransportNamespace *)

- ea: `0x180013e90`
- end: `0x180013f05`
- name: `?CloneWorker@CWdsTransportNamespaceScheduledCastManualStart@@EEAAJPEAUIWdsTransportNamespace@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(CWdsTransportNamespaceScheduledCastManualStart *__hidden this, struct IWdsTransportNamespace *)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x180005e70`
- `0x180005ed0`

## import_xrefs

- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180013ebe`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180013ee5`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180013ebe`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180013ee5`

## string_xrefs

- `0x180013eab`: `-> CWdsTransportNamespaceScheduledCastManualStart::CloneWorker(0x%p)`
- `0x180013ed2`: `<- CWdsTransportNamespaceScheduledCastManualStart::CloneWorker(0x%p) =%x`

## pseudocode

```c
__int64 __fastcall CWdsTransportNamespaceScheduledCastManualStart::CloneWorker(
        CWdsTransportNamespaceScheduledCastManualStart *this,
        struct IWdsTransportNamespace *a2)
{
  int v4; // [rsp+20h] [rbp-28h]
  _BYTE v5[24]; // [rsp+30h] [rbp-18h] BYREF

  CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(v5, (char *)this + 64);
  CTrace::Trace(
    (CTrace *)qword_18003B770,
    0x10000u,
    L"-> CWdsTransportNamespaceScheduledCastManualStart::CloneWorker(0x%p)",
    this);
  v4 = 0;
  CTrace::Trace(
    (CTrace *)qword_18003B770,
    0x10000u,
    L"<- CWdsTransportNamespaceScheduledCastManualStart::CloneWorker(0x%p) =%x",
    this,
    v4);
  CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(v5);
  return 0;
}

```

## disassembly

```asm
0x180013e90  push    rbx
0x180013e92  sub     rsp, 40h
0x180013e96  mov     rbx, rcx
0x180013e99  lea     rdx, [rcx+40h]
0x180013e9d  lea     rcx, [rsp+48h+var_18]
0x180013ea2  call    ??0?$CAutoTypeLock@VCCriticalSection@@@@QEAA@PEAVCCriticalSection@@H@Z; CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(CCriticalSection *,int)
0x180013ea7  nop
0x180013ea8  mov     r9, rbx
0x180013eab  lea     r8, aCwdstransportn_26; "-> CWdsTransportNamespaceScheduledCastM"...
0x180013eb2  mov     edx, 10000h
0x180013eb7  lea     rcx, qword_18003B770
0x180013ebe  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x180013ec5  nop     dword ptr [rax+rax+00h]
0x180013eca  and     [rsp+48h+var_28], 0
0x180013ecf  mov     r9, rbx
0x180013ed2  lea     r8, aCwdstransportn_24; "<- CWdsTransportNamespaceScheduledCastM"...
0x180013ed9  mov     edx, 10000h
0x180013ede  lea     rcx, qword_18003B770
0x180013ee5  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x180013eec  nop     dword ptr [rax+rax+00h]
0x180013ef1  nop
0x180013ef2  lea     rcx, [rsp+48h+var_18]
0x180013ef7  call    ??1?$CAutoTypeLock@VCCriticalSection@@@@QEAA@XZ; CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(void)
0x180013efc  xor     eax, eax
0x180013efe  add     rsp, 40h
0x180013f02  pop     rbx
0x180013f03  retn
```
