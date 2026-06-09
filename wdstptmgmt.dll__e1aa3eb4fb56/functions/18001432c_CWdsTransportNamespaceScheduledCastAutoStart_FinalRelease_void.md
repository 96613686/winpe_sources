# CWdsTransportNamespaceScheduledCastAutoStart::FinalRelease(void)

- ea: `0x18001432c`
- end: `0x1800143a8`
- name: `?FinalRelease@CWdsTransportNamespaceScheduledCastAutoStart@@QEAAXXZ`
- size: `124`
- prototype: `void __fastcall(CWdsTransportNamespaceScheduledCastAutoStart *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180010c60`

## callees

- `0x180005e70`
- `0x180005ed0`
- `0x180013c2c`

## import_xrefs

- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18001435a`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18001438a`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18001435a`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18001438a`

## string_xrefs

- `0x180014347`: `-> CWdsTransportNamespaceScheduledCastAutoStart::FinalRelease(0x%p)`
- `0x180014377`: `<- CWdsTransportNamespaceScheduledCastAutoStart::FinalRelease(0x%p) =%x`

## pseudocode

```c
void __fastcall CWdsTransportNamespaceScheduledCastAutoStart::FinalRelease(
        CWdsTransportNamespaceScheduledCastAutoStart *this)
{
  _BYTE v2[24]; // [rsp+30h] [rbp-18h] BYREF

  CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(v2, (char *)this + 64);
  CTrace::Trace(
    (CTrace *)qword_18003B770,
    0x10000u,
    L"-> CWdsTransportNamespaceScheduledCastAutoStart::FinalRelease(0x%p)",
    this);
  CWdsTransportNamespaceScheduledCast::FinalRelease(this);
  CTrace::Trace(
    (CTrace *)qword_18003B770,
    0x10000u,
    L"<- CWdsTransportNamespaceScheduledCastAutoStart::FinalRelease(0x%p) =%x",
    this,
    0);
  CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(v2);
}

```

## disassembly

```asm
0x18001432c  push    rbx
0x18001432e  sub     rsp, 40h
0x180014332  mov     rbx, rcx
0x180014335  lea     rdx, [rcx+40h]
0x180014339  lea     rcx, [rsp+48h+var_18]
0x18001433e  call    ??0?$CAutoTypeLock@VCCriticalSection@@@@QEAA@PEAVCCriticalSection@@H@Z; CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(CCriticalSection *,int)
0x180014343  nop
0x180014344  mov     r9, rbx
0x180014347  lea     r8, aCwdstransportn_17; "-> CWdsTransportNamespaceScheduledCastA"...
0x18001434e  mov     edx, 10000h
0x180014353  lea     rcx, qword_18003B770
0x18001435a  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x180014361  nop     dword ptr [rax+rax+00h]
0x180014366  mov     rcx, rbx; this
0x180014369  call    ?FinalRelease@CWdsTransportNamespaceScheduledCast@@QEAAXXZ; CWdsTransportNamespaceScheduledCast::FinalRelease(void)
0x18001436e  and     [rsp+48h+var_28], 0
0x180014374  mov     r9, rbx
0x180014377  lea     r8, aCwdstransportn_12; "<- CWdsTransportNamespaceScheduledCastA"...
0x18001437e  mov     edx, 10000h
0x180014383  lea     rcx, qword_18003B770
0x18001438a  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x180014391  nop     dword ptr [rax+rax+00h]
0x180014396  nop
0x180014397  lea     rcx, [rsp+48h+var_18]
0x18001439c  call    ??1?$CAutoTypeLock@VCCriticalSection@@@@QEAA@XZ; CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(void)
0x1800143a1  add     rsp, 40h
0x1800143a5  pop     rbx
0x1800143a6  retn
```
