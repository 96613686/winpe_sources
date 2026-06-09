# CWdsTransportServicePolicy::DelayInitialize(void)

- ea: `0x18000cef4`
- end: `0x18000cf89`
- name: `?DelayInitialize@CWdsTransportServicePolicy@@QEAAJXZ`
- size: `149`
- prototype: `__int64 __fastcall(CWdsTransportServicePolicy *__hidden this)`
- caller_count: `19`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000c240`
- `0x18000deb0`
- `0x18000df40`
- `0x18000e010`
- `0x18000e090`
- `0x18000e150`
- `0x18000e1e0`
- `0x18000e2b0`
- `0x18000e330`
- `0x18000e3c0`
- `0x18000e450`
- `0x18000e4f0`
- `0x18000e640`
- `0x18000e6d0`
- `0x18000e7b0`
- `0x18000e850`
- `0x18000e9a0`
- `0x18000ea30`
- `0x18000eae0`

## callees

- `0x180005e70`
- `0x180005ed0`
- `0x18000cef4`
- `0x180020010`

## import_xrefs

- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000cf28`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000cf64`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000cf28`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000cf64`

## string_xrefs

- `0x18000cf15`: `-> CWdsTransportServicePolicy::DelayInitialize(0x%p)`
- `0x18000cf51`: `<- CWdsTransportServicePolicy::DelayInitialize(0x%p) =%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CWdsTransportServicePolicy::DelayInitialize(CWdsTransportServicePolicy *this)
{
  unsigned int v2; // edi
  int v4; // [rsp+20h] [rbp-28h]
  _BYTE v5[24]; // [rsp+30h] [rbp-18h] BYREF

  v2 = 0;
  CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(v5, (char *)this + 80);
  CTrace::Trace((CTrace *)qword_18003B770, 0x10000u, L"-> CWdsTransportServicePolicy::DelayInitialize(0x%p)", this);
  if ( !*((_DWORD *)this + 31) )
    v2 = (*(__int64 (__fastcall **)(CWdsTransportServicePolicy *))(*(_QWORD *)this + 72LL))(this);
  v4 = v2;
  CTrace::Trace(
    (CTrace *)qword_18003B770,
    0x10000u,
    L"<- CWdsTransportServicePolicy::DelayInitialize(0x%p) =%x",
    this,
    v4);
  CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(v5);
  return v2;
}

```

## disassembly

```asm
0x18000cef4  mov     [rsp+arg_0], rbx
0x18000cef9  push    rdi
0x18000cefa  sub     rsp, 40h
0x18000cefe  mov     rbx, rcx
0x18000cf01  xor     edi, edi
0x18000cf03  lea     rdx, [rcx+50h]
0x18000cf07  lea     rcx, [rsp+48h+var_18]
0x18000cf0c  call    ??0?$CAutoTypeLock@VCCriticalSection@@@@QEAA@PEAVCCriticalSection@@H@Z; CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(CCriticalSection *,int)
0x18000cf11  nop
0x18000cf12  mov     r9, rbx
0x18000cf15  lea     r8, aCwdstransports_46; "-> CWdsTransportServicePolicy::DelayIni"...
0x18000cf1c  mov     edx, 10000h
0x18000cf21  lea     rcx, qword_18003B770
0x18000cf28  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18000cf2f  nop     dword ptr [rax+rax+00h]
0x18000cf34  cmp     [rbx+7Ch], edi
0x18000cf37  jnz     short loc_18000CF4A
0x18000cf39  mov     rax, [rbx]
0x18000cf3c  mov     rcx, rbx
0x18000cf3f  mov     rax, [rax+48h]
0x18000cf43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cf48  mov     edi, eax
0x18000cf4a  mov     [rsp+48h+var_28], edi
0x18000cf4e  mov     r9, rbx
0x18000cf51  lea     r8, aCwdstransports_58; "<- CWdsTransportServicePolicy::DelayIni"...
0x18000cf58  mov     edx, 10000h
0x18000cf5d  lea     rcx, qword_18003B770
0x18000cf64  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18000cf6b  nop     dword ptr [rax+rax+00h]
0x18000cf70  nop
0x18000cf71  lea     rcx, [rsp+48h+var_18]
0x18000cf76  call    ??1?$CAutoTypeLock@VCCriticalSection@@@@QEAA@XZ; CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(void)
0x18000cf7b  mov     eax, edi
0x18000cf7d  mov     rbx, [rsp+48h+arg_0]
0x18000cf82  add     rsp, 40h
0x18000cf86  pop     rdi
0x18000cf87  retn
```
