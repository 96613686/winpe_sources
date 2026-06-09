# CWdsTransportServer::SignalSettingsChange(void)

- ea: `0x180009254`
- end: `0x180009358`
- name: `?SignalSettingsChange@CWdsTransportServer@@QEAAJXZ`
- size: `260`
- prototype: `__int64 __fastcall(CWdsTransportServer *__hidden this)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000c790`
- `0x18000ee50`
- `0x180017200`

## callees

- `0x180005e70`
- `0x180005ed0`
- `0x180009254`
- `0x180009af8`
- `0x180020010`

## import_xrefs

- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000928c`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x1800092f1`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180009333`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000928c`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x1800092f1`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180009333`

## string_xrefs

- `0x1800092de`: `Failed to notify WDS Transport services of a settings change with error 0x%lx.\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CWdsTransportServer::SignalSettingsChange(CWdsTransportServer *this)
{
  __int64 v2; // rbx
  __int64 v3; // rdx
  __int64 v4; // r8
  int v5; // eax
  int v7; // [rsp+20h] [rbp-28h]
  _BYTE v8[24]; // [rsp+30h] [rbp-18h] BYREF
  __int64 v9; // [rsp+50h] [rbp+8h] BYREF

  CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(v8, (char *)this + 72);
  v9 = 0;
  CTrace::Trace((CTrace *)qword_18003B770, 0x10000u, L"-> CWdsTransportServer::SignalSettingsChange(0x%p)", this);
  v2 = (*(unsigned int (__fastcall **)(CWdsTransportServer *, __int64 *))(*(_QWORD *)this + 72LL))(this, &v9);
  if ( (int)ElValidateHr_1(v2, v3, v4, 607) >= 0 )
  {
    v5 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v9 + 120LL))(v9, 1);
    LODWORD(v2) = v5;
    if ( v5 < 0 )
      CTrace::Trace(
        (CTrace *)qword_18003B770,
        0x80000u,
        L"Failed to notify WDS Transport services of a settings change with error 0x%lx.\n",
        (unsigned int)v5);
  }
  if ( v9 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    v9 = 0;
  }
  v7 = v2;
  CTrace::Trace(
    (CTrace *)qword_18003B770,
    0x10000u,
    L"<- CWdsTransportServer::SignalSettingsChange(0x%p) =%x",
    this,
    v7);
  CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(v8);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180009254  mov     [rsp+arg_8], rbx
0x180009259  push    rdi
0x18000925a  sub     rsp, 40h
0x18000925e  mov     rdi, rcx
0x180009261  lea     rdx, [rcx+48h]
0x180009265  lea     rcx, [rsp+48h+var_18]
0x18000926a  call    ??0?$CAutoTypeLock@VCCriticalSection@@@@QEAA@PEAVCCriticalSection@@H@Z; CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(CCriticalSection *,int)
0x18000926f  nop
0x180009270  and     [rsp+48h+arg_0], 0
0x180009276  mov     r9, rdi
0x180009279  lea     r8, aCwdstransports_51; "-> CWdsTransportServer::SignalSettingsC"...
0x180009280  mov     edx, 10000h
0x180009285  lea     rcx, qword_18003B770
0x18000928c  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x180009293  nop     dword ptr [rax+rax+00h]
0x180009298  mov     rax, [rdi]
0x18000929b  lea     rdx, [rsp+48h+arg_0]
0x1800092a0  mov     rcx, rdi
0x1800092a3  mov     rax, [rax+48h]
0x1800092a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800092ac  mov     ebx, eax
0x1800092ae  mov     r9d, 25Fh
0x1800092b4  mov     ecx, eax
0x1800092b6  call    ElValidateHr_1
0x1800092bb  test    eax, eax
0x1800092bd  js      short loc_1800092FD
0x1800092bf  mov     rcx, [rsp+48h+arg_0]
0x1800092c4  mov     rax, [rcx]
0x1800092c7  mov     edx, 1
0x1800092cc  mov     rax, [rax+78h]
0x1800092d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800092d5  mov     ebx, eax
0x1800092d7  test    eax, eax
0x1800092d9  jns     short loc_1800092FD
0x1800092db  mov     r9d, eax
0x1800092de  lea     r8, aFailedToNotify; "Failed to notify WDS Transport services"...
0x1800092e5  mov     edx, 80000h
0x1800092ea  lea     rcx, qword_18003B770
0x1800092f1  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x1800092f8  nop     dword ptr [rax+rax+00h]
0x1800092fd  mov     rcx, [rsp+48h+arg_0]
0x180009302  test    rcx, rcx
0x180009305  jz      short loc_180009319
0x180009307  mov     rax, [rcx]
0x18000930a  mov     rax, [rax+10h]
0x18000930e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009313  and     [rsp+48h+arg_0], 0
0x180009319  mov     [rsp+48h+var_28], ebx
0x18000931d  mov     r9, rdi
0x180009320  lea     r8, aCwdstransports_40; "<- CWdsTransportServer::SignalSettingsC"...
0x180009327  mov     edx, 10000h
0x18000932c  lea     rcx, qword_18003B770
0x180009333  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18000933a  nop     dword ptr [rax+rax+00h]
0x18000933f  nop
0x180009340  lea     rcx, [rsp+48h+var_18]
0x180009345  call    ??1?$CAutoTypeLock@VCCriticalSection@@@@QEAA@XZ; CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(void)
0x18000934a  mov     eax, ebx
0x18000934c  mov     rbx, [rsp+48h+arg_8]
0x180009351  add     rsp, 40h
0x180009355  pop     rdi
0x180009356  retn
```
