# CWdsTransportServicePolicy::Discard(void)

- ea: `0x18000cf90`
- end: `0x18000d053`
- name: `?Discard@CWdsTransportServicePolicy@@UEAAJXZ`
- size: `195`
- prototype: `__int64 __fastcall(CWdsTransportServicePolicy *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180005e70`
- `0x180005ed0`
- `0x18000cf90`
- `0x180020010`

## import_xrefs

- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000cfc3`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000cff2`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000d02f`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000cfc3`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000cff2`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000d02f`

## string_xrefs

- `0x18000cfb0`: `-> CWdsTransportServicePolicy::Discard(0x%p)`
- `0x18000cfdb`: `Discarding modified data for Service Policy on server: %s\n`
- `0x18000d01c`: `<- CWdsTransportServicePolicy::Discard(0x%p) =%x`

## pseudocode

```c
__int64 __fastcall CWdsTransportServicePolicy::Discard(CWdsTransportServicePolicy *this)
{
  unsigned int v2; // edi
  __int64 v3; // rax
  int v5; // [rsp+20h] [rbp-28h]
  _BYTE v6[24]; // [rsp+30h] [rbp-18h] BYREF

  v2 = 0;
  CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(v6, (char *)this + 80);
  CTrace::Trace((CTrace *)qword_18003B770, 0x10000u, L"-> CWdsTransportServicePolicy::Discard(0x%p)", this);
  if ( *((_DWORD *)this + 32) )
  {
    CTrace::Trace(
      (CTrace *)qword_18003B770,
      0x10000u,
      L"Discarding modified data for Service Policy on server: %s\n",
      *(_QWORD *)(*((_QWORD *)this + 8) + 112LL));
    v3 = *(_QWORD *)this;
    *((_DWORD *)this + 32) = 0;
    v2 = (*(__int64 (__fastcall **)(CWdsTransportServicePolicy *))(v3 + 72))(this);
  }
  v5 = v2;
  CTrace::Trace((CTrace *)qword_18003B770, 0x10000u, L"<- CWdsTransportServicePolicy::Discard(0x%p) =%x", this, v5);
  CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(v6);
  return v2;
}

```

## disassembly

```asm
0x18000cf90  mov     [rsp+arg_0], rbx
0x18000cf95  push    rdi
0x18000cf96  sub     rsp, 40h
0x18000cf9a  mov     rbx, rcx
0x18000cf9d  lea     rdx, [rcx+50h]
0x18000cfa1  lea     rcx, [rsp+48h+var_18]
0x18000cfa6  xor     edi, edi
0x18000cfa8  call    ??0?$CAutoTypeLock@VCCriticalSection@@@@QEAA@PEAVCCriticalSection@@H@Z; CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(CCriticalSection *,int)
0x18000cfad  mov     r9, rbx
0x18000cfb0  lea     r8, aCwdstransports; "-> CWdsTransportServicePolicy::Discard("...
0x18000cfb7  mov     edx, 10000h
0x18000cfbc  lea     rcx, qword_18003B770
0x18000cfc3  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18000cfca  nop     dword ptr [rax+rax+00h]
0x18000cfcf  cmp     [rbx+80h], edi
0x18000cfd5  jz      short loc_18000D015
0x18000cfd7  mov     r9, [rbx+40h]
0x18000cfdb  lea     r8, aDiscardingModi; "Discarding modified data for Service Po"...
0x18000cfe2  mov     edx, 10000h
0x18000cfe7  lea     rcx, qword_18003B770
0x18000cfee  mov     r9, [r9+70h]
0x18000cff2  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18000cff9  nop     dword ptr [rax+rax+00h]
0x18000cffe  mov     rax, [rbx]
0x18000d001  mov     rcx, rbx
0x18000d004  mov     [rbx+80h], edi
0x18000d00a  mov     rax, [rax+48h]
0x18000d00e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d013  mov     edi, eax
0x18000d015  mov     r9, rbx
0x18000d018  mov     [rsp+48h+var_28], edi
0x18000d01c  lea     r8, aCwdstransports_1; "<- CWdsTransportServicePolicy::Discard("...
0x18000d023  mov     edx, 10000h
0x18000d028  lea     rcx, qword_18003B770
0x18000d02f  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18000d036  nop     dword ptr [rax+rax+00h]
0x18000d03b  lea     rcx, [rsp+48h+var_18]
0x18000d040  call    ??1?$CAutoTypeLock@VCCriticalSection@@@@QEAA@XZ; CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(void)
0x18000d045  mov     rbx, [rsp+48h+arg_0]
0x18000d04a  mov     eax, edi
0x18000d04c  add     rsp, 40h
0x18000d050  pop     rdi
0x18000d051  retn
```
