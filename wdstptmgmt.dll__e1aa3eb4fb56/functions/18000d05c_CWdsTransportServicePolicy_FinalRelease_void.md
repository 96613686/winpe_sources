# CWdsTransportServicePolicy::FinalRelease(void)

- ea: `0x18000d05c`
- end: `0x18000d150`
- name: `?FinalRelease@CWdsTransportServicePolicy@@QEAAXXZ`
- size: `244`
- prototype: `void __fastcall(CWdsTransportServicePolicy *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x18000c704`

## callees

- `0x180005e70`
- `0x180005ed0`
- `0x18000d05c`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18000d0a2`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000d0c2`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000d0e2`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000d102`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000d0a2`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000d0c2`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000d0e2`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000d102`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000d08a`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000d132`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000d08a`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000d132`

## string_xrefs

- `0x18000d077`: `-> CWdsTransportServicePolicy::FinalRelease(0x%p)`
- `0x18000d11f`: `<- CWdsTransportServicePolicy::FinalRelease(0x%p) =%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CWdsTransportServicePolicy::FinalRelease(CWdsTransportServicePolicy *this)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  _BYTE v6[24]; // [rsp+30h] [rbp-18h] BYREF

  CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(v6, (char *)this + 80);
  CTrace::Trace((CTrace *)qword_18003B770, 0x10000u, L"-> CWdsTransportServicePolicy::FinalRelease(0x%p)", this);
  v2 = (void *)*((_QWORD *)this + 17);
  if ( v2 )
  {
    operator delete[](v2);
    *((_QWORD *)this + 17) = 0;
  }
  v3 = (void *)*((_QWORD *)this + 18);
  if ( v3 )
  {
    operator delete[](v3);
    *((_QWORD *)this + 18) = 0;
  }
  v4 = (void *)*((_QWORD *)this + 20);
  if ( v4 )
  {
    operator delete[](v4);
    *((_QWORD *)this + 20) = 0;
  }
  v5 = (void *)*((_QWORD *)this + 21);
  if ( v5 )
  {
    operator delete[](v5);
    *((_QWORD *)this + 21) = 0;
  }
  CTrace::Trace((CTrace *)qword_18003B770, 0x10000u, L"<- CWdsTransportServicePolicy::FinalRelease(0x%p) =%x", this, 0);
  CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(v6);
}

```

## disassembly

```asm
0x18000d05c  push    rbx
0x18000d05e  sub     rsp, 40h
0x18000d062  mov     rbx, rcx
0x18000d065  lea     rdx, [rcx+50h]
0x18000d069  lea     rcx, [rsp+48h+var_18]
0x18000d06e  call    ??0?$CAutoTypeLock@VCCriticalSection@@@@QEAA@PEAVCCriticalSection@@H@Z; CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(CCriticalSection *,int)
0x18000d073  nop
0x18000d074  mov     r9, rbx
0x18000d077  lea     r8, aCwdstransports_5; "-> CWdsTransportServicePolicy::FinalRel"...
0x18000d07e  mov     edx, 10000h
0x18000d083  lea     rcx, qword_18003B770
0x18000d08a  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18000d091  nop     dword ptr [rax+rax+00h]
0x18000d096  mov     rcx, [rbx+88h]
0x18000d09d  test    rcx, rcx
0x18000d0a0  jz      short loc_18000D0B6
0x18000d0a2  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18000d0a9  nop     dword ptr [rax+rax+00h]
0x18000d0ae  and     qword ptr [rbx+88h], 0
0x18000d0b6  mov     rcx, [rbx+90h]
0x18000d0bd  test    rcx, rcx
0x18000d0c0  jz      short loc_18000D0D6
0x18000d0c2  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18000d0c9  nop     dword ptr [rax+rax+00h]
0x18000d0ce  and     qword ptr [rbx+90h], 0
0x18000d0d6  mov     rcx, [rbx+0A0h]
0x18000d0dd  test    rcx, rcx
0x18000d0e0  jz      short loc_18000D0F6
0x18000d0e2  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18000d0e9  nop     dword ptr [rax+rax+00h]
0x18000d0ee  and     qword ptr [rbx+0A0h], 0
0x18000d0f6  mov     rcx, [rbx+0A8h]
0x18000d0fd  test    rcx, rcx
0x18000d100  jz      short loc_18000D116
0x18000d102  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18000d109  nop     dword ptr [rax+rax+00h]
0x18000d10e  and     qword ptr [rbx+0A8h], 0
0x18000d116  and     [rsp+48h+var_28], 0
0x18000d11c  mov     r9, rbx
0x18000d11f  lea     r8, aCwdstransports_61; "<- CWdsTransportServicePolicy::FinalRel"...
0x18000d126  mov     edx, 10000h
0x18000d12b  lea     rcx, qword_18003B770
0x18000d132  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18000d139  nop     dword ptr [rax+rax+00h]
0x18000d13e  nop
0x18000d13f  lea     rcx, [rsp+48h+var_18]
0x18000d144  call    ??1?$CAutoTypeLock@VCCriticalSection@@@@QEAA@XZ; CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(void)
0x18000d149  add     rsp, 40h
0x18000d14d  pop     rbx
0x18000d14e  retn
```
