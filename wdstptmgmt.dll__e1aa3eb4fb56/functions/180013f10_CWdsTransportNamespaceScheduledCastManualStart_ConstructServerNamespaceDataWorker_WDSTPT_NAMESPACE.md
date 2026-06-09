# CWdsTransportNamespaceScheduledCastManualStart::ConstructServerNamespaceDataWorker(_WDSTPT_NAMESPACE *)

- ea: `0x180013f10`
- end: `0x180013f9f`
- name: `?ConstructServerNamespaceDataWorker@CWdsTransportNamespaceScheduledCastManualStart@@EEAAJPEAU_WDSTPT_NAMESPACE@@@Z`
- size: `143`
- prototype: `__int64 __fastcall(CWdsTransportNamespaceScheduledCastManualStart *__hidden this, struct _WDSTPT_NAMESPACE *)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x180005e70`
- `0x180005ed0`

## import_xrefs

- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180013f45`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180013f7a`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180013f45`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180013f7a`

## string_xrefs

- `0x180013f32`: `-> CWdsTransportNamespaceScheduledCastManualStart::ConstructServerNamespaceDataWorker(0x%p)`
- `0x180013f67`: `<- CWdsTransportNamespaceScheduledCastManualStart::ConstructServerNamespaceDataWorker(0x%p) =%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CWdsTransportNamespaceScheduledCastManualStart::ConstructServerNamespaceDataWorker(
        CWdsTransportNamespaceScheduledCastManualStart *this,
        struct _WDSTPT_NAMESPACE *a2)
{
  int v5; // [rsp+20h] [rbp-28h]
  _BYTE v6[24]; // [rsp+30h] [rbp-18h] BYREF

  CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(v6, (char *)this + 64);
  CTrace::Trace(
    (CTrace *)qword_18003B770,
    0x10000u,
    L"-> CWdsTransportNamespaceScheduledCastManualStart::ConstructServerNamespaceDataWorker(0x%p)",
    this);
  *((_DWORD *)a2 + 2) = 2;
  *((_DWORD *)a2 + 20) = 1;
  v5 = 0;
  CTrace::Trace(
    (CTrace *)qword_18003B770,
    0x10000u,
    L"<- CWdsTransportNamespaceScheduledCastManualStart::ConstructServerNamespaceDataWorker(0x%p) =%x",
    this,
    v5);
  CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(v6);
  return 0;
}

```

## disassembly

```asm
0x180013f10  mov     [rsp+arg_0], rbx
0x180013f15  push    rdi
0x180013f16  sub     rsp, 40h
0x180013f1a  mov     rbx, rdx
0x180013f1d  mov     rdi, rcx
0x180013f20  lea     rdx, [rcx+40h]
0x180013f24  lea     rcx, [rsp+48h+var_18]
0x180013f29  call    ??0?$CAutoTypeLock@VCCriticalSection@@@@QEAA@PEAVCCriticalSection@@H@Z; CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(CCriticalSection *,int)
0x180013f2e  nop
0x180013f2f  mov     r9, rdi
0x180013f32  lea     r8, aCwdstransportn_6; "-> CWdsTransportNamespaceScheduledCastM"...
0x180013f39  mov     edx, 10000h
0x180013f3e  lea     rcx, qword_18003B770
0x180013f45  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x180013f4c  nop     dword ptr [rax+rax+00h]
0x180013f51  mov     dword ptr [rbx+8], 2
0x180013f58  mov     dword ptr [rbx+50h], 1
0x180013f5f  and     [rsp+48h+var_28], 0
0x180013f64  mov     r9, rdi
0x180013f67  lea     r8, aCwdstransportn_9; "<- CWdsTransportNamespaceScheduledCastM"...
0x180013f6e  mov     edx, 10000h
0x180013f73  lea     rcx, qword_18003B770
0x180013f7a  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x180013f81  nop     dword ptr [rax+rax+00h]
0x180013f86  nop
0x180013f87  lea     rcx, [rsp+48h+var_18]
0x180013f8c  call    ??1?$CAutoTypeLock@VCCriticalSection@@@@QEAA@XZ; CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(void)
0x180013f91  xor     eax, eax
0x180013f93  mov     rbx, [rsp+48h+arg_0]
0x180013f98  add     rsp, 40h
0x180013f9c  pop     rdi
0x180013f9d  retn
```
