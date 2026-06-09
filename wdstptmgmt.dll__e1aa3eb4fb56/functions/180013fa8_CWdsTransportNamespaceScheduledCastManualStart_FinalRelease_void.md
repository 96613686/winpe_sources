# CWdsTransportNamespaceScheduledCastManualStart::FinalRelease(void)

- ea: `0x180013fa8`
- end: `0x180014024`
- name: `?FinalRelease@CWdsTransportNamespaceScheduledCastManualStart@@QEAAXXZ`
- size: `124`
- prototype: `void __fastcall(CWdsTransportNamespaceScheduledCastManualStart *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180010cc4`

## callees

- `0x180005e70`
- `0x180005ed0`
- `0x180013c2c`

## import_xrefs

- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180013fd6`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180014006`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180013fd6`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180014006`

## string_xrefs

- `0x180013fc3`: `-> CWdsTransportNamespaceScheduledCastManualStart::FinalRelease(0x%p)`
- `0x180013ff3`: `<- CWdsTransportNamespaceScheduledCastManualStart::FinalRelease(0x%p) =%x`

## pseudocode

```c
void __fastcall CWdsTransportNamespaceScheduledCastManualStart::FinalRelease(
        CWdsTransportNamespaceScheduledCastManualStart *this)
{
  _BYTE v2[24]; // [rsp+30h] [rbp-18h] BYREF

  CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(v2, (char *)this + 64);
  CTrace::Trace(
    (CTrace *)qword_18003B770,
    0x10000u,
    L"-> CWdsTransportNamespaceScheduledCastManualStart::FinalRelease(0x%p)",
    this);
  CWdsTransportNamespaceScheduledCast::FinalRelease(this);
  CTrace::Trace(
    (CTrace *)qword_18003B770,
    0x10000u,
    L"<- CWdsTransportNamespaceScheduledCastManualStart::FinalRelease(0x%p) =%x",
    this,
    0);
  CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(v2);
}

```

## disassembly

```asm
0x180013fa8  push    rbx
0x180013faa  sub     rsp, 40h
0x180013fae  mov     rbx, rcx
0x180013fb1  lea     rdx, [rcx+40h]
0x180013fb5  lea     rcx, [rsp+48h+var_18]
0x180013fba  call    ??0?$CAutoTypeLock@VCCriticalSection@@@@QEAA@PEAVCCriticalSection@@H@Z; CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(CCriticalSection *,int)
0x180013fbf  nop
0x180013fc0  mov     r9, rbx
0x180013fc3  lea     r8, aCwdstransportn_34; "-> CWdsTransportNamespaceScheduledCastM"...
0x180013fca  mov     edx, 10000h
0x180013fcf  lea     rcx, qword_18003B770
0x180013fd6  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x180013fdd  nop     dword ptr [rax+rax+00h]
0x180013fe2  mov     rcx, rbx; this
0x180013fe5  call    ?FinalRelease@CWdsTransportNamespaceScheduledCast@@QEAAXXZ; CWdsTransportNamespaceScheduledCast::FinalRelease(void)
0x180013fea  and     [rsp+48h+var_28], 0
0x180013ff0  mov     r9, rbx
0x180013ff3  lea     r8, aCwdstransportn_52; "<- CWdsTransportNamespaceScheduledCastM"...
0x180013ffa  mov     edx, 10000h
0x180013fff  lea     rcx, qword_18003B770
0x180014006  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18001400d  nop     dword ptr [rax+rax+00h]
0x180014012  nop
0x180014013  lea     rcx, [rsp+48h+var_18]
0x180014018  call    ??1?$CAutoTypeLock@VCCriticalSection@@@@QEAA@XZ; CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(void)
0x18001401d  add     rsp, 40h
0x180014021  pop     rbx
0x180014022  retn
```
