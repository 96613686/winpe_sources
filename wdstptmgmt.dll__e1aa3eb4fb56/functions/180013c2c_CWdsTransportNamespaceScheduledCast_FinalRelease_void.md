# CWdsTransportNamespaceScheduledCast::FinalRelease(void)

- ea: `0x180013c2c`
- end: `0x180013ca8`
- name: `?FinalRelease@CWdsTransportNamespaceScheduledCast@@QEAAXXZ`
- size: `124`
- prototype: `void __fastcall(CWdsTransportNamespaceScheduledCast *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180013fa8`
- `0x18001432c`

## callees

- `0x180005e70`
- `0x180005ed0`
- `0x180011a54`

## import_xrefs

- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180013c5a`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180013c8a`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180013c5a`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180013c8a`

## string_xrefs

- `0x180013c47`: `-> CWdsTransportNamespaceScheduledCast::FinalRelease(0x%p)`
- `0x180013c77`: `<- CWdsTransportNamespaceScheduledCast::FinalRelease(0x%p) =%x`

## pseudocode

```c
void __fastcall CWdsTransportNamespaceScheduledCast::FinalRelease(CWdsTransportNamespaceScheduledCast *this)
{
  _BYTE v2[24]; // [rsp+30h] [rbp-18h] BYREF

  CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(v2, (char *)this + 64);
  CTrace::Trace(
    (CTrace *)qword_18003B770,
    0x10000u,
    L"-> CWdsTransportNamespaceScheduledCast::FinalRelease(0x%p)",
    this);
  CWdsTransportNamespace::FinalRelease(this);
  CTrace::Trace(
    (CTrace *)qword_18003B770,
    0x10000u,
    L"<- CWdsTransportNamespaceScheduledCast::FinalRelease(0x%p) =%x",
    this,
    0);
  CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(v2);
}

```

## disassembly

```asm
0x180013c2c  push    rbx
0x180013c2e  sub     rsp, 40h
0x180013c32  mov     rbx, rcx
0x180013c35  lea     rdx, [rcx+40h]
0x180013c39  lea     rcx, [rsp+48h+var_18]
0x180013c3e  call    ??0?$CAutoTypeLock@VCCriticalSection@@@@QEAA@PEAVCCriticalSection@@H@Z; CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(CCriticalSection *,int)
0x180013c43  nop
0x180013c44  mov     r9, rbx
0x180013c47  lea     r8, aCwdstransportn_48; "-> CWdsTransportNamespaceScheduledCast:"...
0x180013c4e  mov     edx, 10000h
0x180013c53  lea     rcx, qword_18003B770
0x180013c5a  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x180013c61  nop     dword ptr [rax+rax+00h]
0x180013c66  mov     rcx, rbx; this
0x180013c69  call    ?FinalRelease@CWdsTransportNamespace@@QEAAXXZ; CWdsTransportNamespace::FinalRelease(void)
0x180013c6e  and     [rsp+48h+var_28], 0
0x180013c74  mov     r9, rbx
0x180013c77  lea     r8, aCwdstransportn_47; "<- CWdsTransportNamespaceScheduledCast:"...
0x180013c7e  mov     edx, 10000h
0x180013c83  lea     rcx, qword_18003B770
0x180013c8a  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x180013c91  nop     dword ptr [rax+rax+00h]
0x180013c96  nop
0x180013c97  lea     rcx, [rsp+48h+var_18]
0x180013c9c  call    ??1?$CAutoTypeLock@VCCriticalSection@@@@QEAA@XZ; CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(void)
0x180013ca1  add     rsp, 40h
0x180013ca5  pop     rbx
0x180013ca6  retn
```
