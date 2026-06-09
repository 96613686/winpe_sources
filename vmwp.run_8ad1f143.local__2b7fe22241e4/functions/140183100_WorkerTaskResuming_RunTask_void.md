# WorkerTaskResuming::RunTask(void)

- ea: `0x140183100`
- end: `0x14018344a`
- name: `?RunTask@WorkerTaskResuming@@UEAAXXZ`
- size: `842`
- prototype: `void __fastcall(WorkerTaskResuming *__hidden this)`
- caller_count: `0`
- callee_count: `16`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x14002ecf0`
- `0x140032f60`
- `0x140042260`
- `0x14005497c`
- `0x14005dbf0`
- `0x140078cb8`
- `0x1400941fc`
- `0x1400dbe6c`
- `0x1400df15c`
- `0x1400eb548`
- `0x1400f6680`
- `0x14012f6ac`
- `0x140132960`
- `0x140170e7c`
- `0x140183100`
- `0x1402c2010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1401832ea`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1401832ea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140183329`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140183329`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14018321e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14018321e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140183305`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140183305`
- `vmprox!GetVmErrInfo` at `0x140183400`
- `vmprox!GetVmErrInfo` at `0x140183400`
- `vid!VidSuspendClear` at `0x1401831d8`
- `vid!VidSuspendClear` at `0x1401831d8`

## string_xrefs

- `0x1401831f6`: `onecore\vm\worker\wpcore\workertaskresuming.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall WorkerTaskResuming::RunTask(WorkerTaskResuming *this)
{
  VirtualMachine *v2; // rcx
  signed int started; // ebx
  __int64 v4; // rcx
  int v5; // edi
  int v6; // ebx
  unsigned int v7; // r14d
  __int64 v8; // rcx
  __int64 v9; // rax
  signed int LastError; // eax
  int v11; // eax
  __int64 v12; // rcx
  __int64 v13; // rbx
  __int64 v14; // rcx
  __int64 VmErrInfo; // rax
  int v16; // [rsp+20h] [rbp-48h]
  struct IUnknown *v17; // [rsp+30h] [rbp-38h] BYREF
  __int64 v18; // [rsp+38h] [rbp-30h] BYREF
  __int64 VmName; // [rsp+40h] [rbp-28h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+48h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+30h]

  v17 = 0;
  (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(*((_QWORD *)this + 2) + 1040LL) + 608LL))(*(_QWORD *)(*((_QWORD *)this + 2) + 1040LL));
  if ( *((_DWORD *)this + 100) == 19 )
  {
    v2 = (VirtualMachine *)*((_QWORD *)this + 2);
    if ( *((_DWORD *)v2 + 586) == 4 )
    {
      started = VirtualMachine::ValidateRecovery(v2);
      if ( started < 0 )
        goto LABEL_14;
    }
  }
  v4 = *((_QWORD *)this + 2);
  v5 = *(_DWORD *)(v4 + 2344);
  v6 = 5;
  if ( v5 != 4 )
    v6 = 0;
  v7 = v6 | 0x100;
  if ( !(*(unsigned __int8 (__fastcall **)(_QWORD))(**(_QWORD **)(v4 + 1040) + 504LL))(*(_QWORD *)(v4 + 1040)) )
    v7 = v6;
  v8 = *((_QWORD *)this + 2);
  if ( *(_DWORD *)(v8 + 2620) )
  {
    v9 = (**(__int64 (__fastcall ***)(__int64))(*(_QWORD *)(v8 + 1024) + 24LL))(*(_QWORD *)(v8 + 1024) + 24LL);
    if ( !(unsigned int)VidSuspendClear(v9) )
    {
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0x7C,
        (unsigned int)"onecore\\vm\\worker\\wpcore\\workertaskresuming.cpp",
        (const char *)0x8000FFFFLL,
        v16);
      if ( (unsigned int)VmlIsDebugTraceEnabled(0) )
        VmlDebugTraceEx(0, &off_1402D9CB8);
      LastError = GetLastError();
      started = LastError;
      if ( LastError > 0 )
        started = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_14;
    }
    *(_DWORD *)(*((_QWORD *)this + 2) + 2620LL) = 0;
    v8 = *((_QWORD *)this + 2);
  }
  if ( v5 == 4 )
    VirtualMotherboard::NotifyVmResumedFromCriticalError(*(VirtualMotherboard **)(v8 + 984));
  started = VirtualMachine::StartVm(*((_QWORD *)this + 2), v7, 5 - (unsigned int)(v5 != 4));
  if ( started >= 0 )
  {
    v13 = *((_QWORD *)this + 2);
    EnterCriticalSection((LPCRITICAL_SECTION)(v13 + 2456));
    SetThreadpoolTimer(*(PTP_TIMER *)(v13 + 2496), 0, 0, 0);
    *(_QWORD *)(v13 + 2504) = 0;
    *(_DWORD *)(v13 + 2512) = 0;
    LeaveCriticalSection((LPCRITICAL_SECTION)(v13 + 2456));
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(*((_QWORD *)this + 2) + 1064LL) + 72LL))(*(_QWORD *)(*((_QWORD *)this + 2) + 1064LL));
    VirtualMachine::SetState(*((_QWORD *)this + 2), 2, *((unsigned int *)this + 100));
    started = 0;
    v11 = *((_DWORD *)this + 100);
    goto LABEL_15;
  }
LABEL_14:
  v11 = *((_DWORD *)this + 100);
  if ( started >= 0 )
  {
LABEL_15:
    EventDescriptor = (EVENT_DESCRIPTOR)MSVM_RESUME_SUCCESS;
    if ( v11 == 20 )
      EventDescriptor = (EVENT_DESCRIPTOR)MSVM_RESUME_CRITICAL_SUCCESS;
    v12 = *((_QWORD *)this + 2);
    v18 = v12 + 1152;
    VmName = (__int64)VirtualMachine::GetVmName((VirtualMachine *)(v12 + 16));
    VmEventWrite<unsigned short const *,unsigned short const *>(&EventDescriptor, 1u, (__int64)&v18);
    goto LABEL_26;
  }
  EventDescriptor = (EVENT_DESCRIPTOR)MSVMB_WP_RESUME_ERROR;
  if ( v11 == 20 )
    EventDescriptor = (EVENT_DESCRIPTOR)MSVMB_WP_RESUME_CRITICAL_ERROR;
  (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(*((_QWORD *)this + 2) + 1040LL) + 600LL))(*(_QWORD *)(*((_QWORD *)this + 2) + 1040LL));
  VirtualMachine::SetState(
    *((_QWORD *)this + 2),
    4 - (unsigned int)(*(_DWORD *)(*((_QWORD *)this + 2) + 2344LL) != 4),
    21);
  v14 = *((_QWORD *)this + 2);
  VmName = v14 + 1152;
  v18 = (__int64)VirtualMachine::GetVmName((VirtualMachine *)(v14 + 16));
  VmEventWriteAndReport<unsigned short const *,unsigned short const *>(
    &EventDescriptor,
    0xDu,
    (__int64)&v18,
    (__int64)&VmName);
LABEL_26:
  VmErrInfo = GetVmErrInfo();
  Vml::VmComPtr<IVmSimpleTask>::Attach<IVmSimpleTask>(&v17, VmErrInfo);
  WorkerAsyncTaskBase::SetStatusComplete(this, started, v17);
  Vml::VmComPtr<IVmMetricValueSink>::~VmComPtr<IVmMetricValueSink>(&v17);
}

```

## disassembly

```asm
0x140183100  push    rbp
0x140183102  push    rbx
0x140183103  push    rsi
0x140183104  push    rdi
0x140183105  push    r14
0x140183107  push    r15
0x140183109  mov     rbp, rsp
0x14018310c  sub     rsp, 68h
0x140183110  mov     rax, cs:__security_cookie
0x140183117  xor     rax, rsp
0x14018311a  mov     [rbp+var_10], rax
0x14018311e  mov     rsi, rcx
0x140183121  mov     [rbp+var_38], 0
0x140183129  mov     rax, [rcx+10h]
0x14018312d  mov     rcx, [rax+410h]
0x140183134  mov     rax, [rcx]
0x140183137  mov     rax, [rax+260h]
0x14018313e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140183143  cmp     dword ptr [rsi+190h], 13h
0x14018314a  jnz     short loc_140183168
0x14018314c  mov     rcx, [rsi+10h]; this
0x140183150  cmp     dword ptr [rcx+928h], 4
0x140183157  jnz     short loc_140183168
0x140183159  call    ?ValidateRecovery@VirtualMachine@@QEAAJXZ; VirtualMachine::ValidateRecovery(void)
0x14018315e  mov     ebx, eax
0x140183160  test    eax, eax
0x140183162  js      loc_140183239
0x140183168  mov     rcx, [rsi+10h]
0x14018316c  mov     edi, [rcx+928h]
0x140183172  lea     eax, [rdi-4]
0x140183175  neg     eax
0x140183177  sbb     r15d, r15d
0x14018317a  mov     ebx, 5
0x14018317f  add     r15d, ebx
0x140183182  xor     eax, eax
0x140183184  cmp     edi, 4
0x140183187  cmovnz  ebx, eax
0x14018318a  mov     rcx, [rcx+410h]
0x140183191  mov     rax, [rcx]
0x140183194  mov     rax, [rax+1F8h]
0x14018319b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401831a0  mov     r14d, ebx
0x1401831a3  bts     r14d, 8
0x1401831a8  test    al, al
0x1401831aa  cmovz   r14d, ebx
0x1401831ae  mov     rcx, [rsi+10h]
0x1401831b2  cmp     dword ptr [rcx+0A3Ch], 0
0x1401831b9  jz      loc_1401832B2
0x1401831bf  mov     rcx, [rcx+400h]
0x1401831c6  add     rcx, 18h
0x1401831ca  mov     rax, [rcx]
0x1401831cd  mov     rax, [rax]
0x1401831d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401831d5  mov     rcx, rax
0x1401831d8  call    cs:__imp_VidSuspendClear
0x1401831df  nop     dword ptr [rax+rax+00h]
0x1401831e4  test    eax, eax
0x1401831e6  jnz     loc_1401832A0
0x1401831ec  mov     rcx, [rbp+30h]; this
0x1401831f0  mov     r9d, 8000FFFFh; char *
0x1401831f6  lea     r8, aOnecoreVmWorke_38; "onecore\\vm\\worker\\wpcore\\workertask"...
0x1401831fd  lea     edx, [rax+7Ch]; void *
0x140183200  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x140183205  xor     ecx, ecx
0x140183207  call    VmlIsDebugTraceEnabled
0x14018320c  test    eax, eax
0x14018320e  jz      short loc_14018321E
0x140183210  lea     rdx, off_1402D9CB8; "Unexpected error.\n"
0x140183217  xor     ecx, ecx
0x140183219  call    VmlDebugTraceEx
0x14018321e  call    cs:__imp_GetLastError
0x140183225  nop     dword ptr [rax+rax+00h]
0x14018322a  mov     ebx, eax
0x14018322c  test    eax, eax
0x14018322e  jle     short loc_140183239
0x140183230  movzx   ebx, ax
0x140183233  or      ebx, 80070000h
0x140183239  mov     eax, [rsi+190h]
0x14018323f  test    ebx, ebx
0x140183241  js      loc_14018336E
0x140183247  movups  xmm0, cs:MSVM_RESUME_SUCCESS
0x14018324e  movdqu  xmmword ptr [rbp+EventDescriptor.Id], xmm0
0x140183253  cmp     eax, 14h
0x140183256  jnz     short loc_140183264
0x140183258  movups  xmm0, cs:MSVM_RESUME_CRITICAL_SUCCESS
0x14018325f  movdqu  xmmword ptr [rbp+EventDescriptor.Id], xmm0
0x140183264  mov     rcx, [rsi+10h]
0x140183268  lea     rax, [rcx+480h]
0x14018326f  mov     [rbp+var_30], rax
0x140183273  add     rcx, 10h; this
0x140183277  call    ?GetVmName@VirtualMachine@@UEBAPEBGXZ; VirtualMachine::GetVmName(void)
0x14018327c  mov     [rbp+var_28], rax
0x140183280  lea     rax, [rbp+var_30]
0x140183284  mov     [rsp+68h+var_48], rax; __int64
0x140183289  lea     r9, [rbp+var_28]
0x14018328d  mov     edx, 1; unsigned int
0x140183292  lea     rcx, [rbp+EventDescriptor]; EventDescriptor
0x140183296  call    ??$VmEventWrite@PEBGPEBG@@YAXPEBU_EVENT_DESCRIPTOR@@IAEBU_GUID@@$$QEAPEBG2@Z; VmEventWrite<ushort const *,ushort const *>(_EVENT_DESCRIPTOR const *,uint,_GUID const &,ushort const * &&,ushort const * &&)
0x14018329b  jmp     loc_140183400
0x1401832a0  mov     rax, [rsi+10h]
0x1401832a4  mov     dword ptr [rax+0A3Ch], 0
0x1401832ae  mov     rcx, [rsi+10h]
0x1401832b2  cmp     edi, 4
0x1401832b5  jnz     short loc_1401832C3
0x1401832b7  mov     rcx, [rcx+3D8h]; this
0x1401832be  call    ?NotifyVmResumedFromCriticalError@VirtualMotherboard@@QEAAJXZ; VirtualMotherboard::NotifyVmResumedFromCriticalError(void)
0x1401832c3  mov     r8d, r15d
0x1401832c6  mov     edx, r14d
0x1401832c9  mov     rcx, [rsi+10h]
0x1401832cd  call    ?StartVm@VirtualMachine@@QEAAJIW4__MIDL___MIDL_itf_vmbservices_0000_0011_0002@@@Z; VirtualMachine::StartVm(uint,__MIDL___MIDL_itf_vmbservices_0000_0011_0002)
0x1401832d2  mov     ebx, eax
0x1401832d4  test    eax, eax
0x1401832d6  js      loc_140183239
0x1401832dc  mov     rbx, [rsi+10h]
0x1401832e0  lea     rdi, [rbx+998h]
0x1401832e7  mov     rcx, rdi; lpCriticalSection
0x1401832ea  call    cs:__imp_EnterCriticalSection
0x1401832f1  nop     dword ptr [rax+rax+00h]
0x1401832f6  xor     r9d, r9d; msWindowLength
0x1401832f9  xor     r8d, r8d; msPeriod
0x1401832fc  xor     edx, edx; pftDueTime
0x1401832fe  mov     rcx, [rbx+9C0h]; pti
0x140183305  call    cs:__imp_SetThreadpoolTimer
0x14018330c  nop     dword ptr [rax+rax+00h]
0x140183311  mov     qword ptr [rbx+9C8h], 0
0x14018331c  mov     dword ptr [rbx+9D0h], 0
0x140183326  mov     rcx, rdi; lpCriticalSection
0x140183329  call    cs:__imp_LeaveCriticalSection
0x140183330  nop     dword ptr [rax+rax+00h]
0x140183335  mov     rax, [rsi+10h]
0x140183339  mov     rcx, [rax+428h]
0x140183340  mov     rax, [rcx]
0x140183343  mov     rax, [rax+48h]
0x140183347  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14018334c  mov     r8d, [rsi+190h]
0x140183353  mov     edx, 2
0x140183358  mov     rcx, [rsi+10h]
0x14018335c  call    ?SetState@VirtualMachine@@QEAAHW4_VM_STATE@@W4_VM_STATE_REASON_CODE@@@Z; VirtualMachine::SetState(_VM_STATE,_VM_STATE_REASON_CODE)
0x140183361  xor     ebx, ebx
0x140183363  mov     eax, [rsi+190h]
0x140183369  jmp     loc_140183247
0x14018336e  movups  xmm0, cs:MSVMB_WP_RESUME_ERROR
0x140183375  movdqu  xmmword ptr [rbp+EventDescriptor.Id], xmm0
0x14018337a  cmp     eax, 14h
0x14018337d  jnz     short loc_14018338B
0x14018337f  movups  xmm0, cs:MSVMB_WP_RESUME_CRITICAL_ERROR
0x140183386  movdqu  xmmword ptr [rbp+EventDescriptor.Id], xmm0
0x14018338b  mov     rax, [rsi+10h]
0x14018338f  mov     rcx, [rax+410h]
0x140183396  mov     rax, [rcx]
0x140183399  mov     rax, [rax+258h]
0x1401833a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401833a5  mov     rcx, [rsi+10h]
0x1401833a9  mov     eax, [rcx+928h]
0x1401833af  sub     eax, 4
0x1401833b2  neg     eax
0x1401833b4  sbb     edx, edx
0x1401833b6  add     edx, 4
0x1401833b9  mov     r8d, 15h
0x1401833bf  call    ?SetState@VirtualMachine@@QEAAHW4_VM_STATE@@W4_VM_STATE_REASON_CODE@@@Z; VirtualMachine::SetState(_VM_STATE,_VM_STATE_REASON_CODE)
0x1401833c4  mov     rcx, [rsi+10h]
0x1401833c8  lea     rax, [rcx+480h]
0x1401833cf  mov     [rbp+var_28], rax
0x1401833d3  add     rcx, 10h; this
0x1401833d7  call    ?GetVmName@VirtualMachine@@UEBAPEBGXZ; VirtualMachine::GetVmName(void)
0x1401833dc  mov     [rbp+var_30], rax
0x1401833e0  lea     rax, [rbp+var_28]
0x1401833e4  mov     [rsp+68h+var_40], rax; __int64
0x1401833e9  lea     rax, [rbp+var_30]
0x1401833ed  mov     [rsp+68h+var_48], rax; __int64
0x1401833f2  mov     edx, 0Dh; unsigned int
0x1401833f7  lea     rcx, [rbp+EventDescriptor]; struct _EVENT_DESCRIPTOR *
0x1401833fb  call    ??$VmEventWriteAndReport@PEBGPEBG@@YAXPEBU_EVENT_DESCRIPTOR@@IAEBU_GUID@@PEBG$$QEAPEBG3@Z; VmEventWriteAndReport<ushort const *,ushort const *>(_EVENT_DESCRIPTOR const *,uint,_GUID const &,ushort const *,ushort const * &&,ushort const * &&)
0x140183400  call    cs:__imp_GetVmErrInfo
0x140183407  nop     dword ptr [rax+rax+00h]
0x14018340c  mov     rdx, rax
0x14018340f  lea     rcx, [rbp+var_38]
0x140183413  call    ??$Attach@UIVmSimpleTask@@@?$VmComPtr@UIVmSimpleTask@@@Vml@@QEAAXPEAUIVmSimpleTask@@@Z; Vml::VmComPtr<IVmSimpleTask>::Attach<IVmSimpleTask>(IVmSimpleTask *)
0x140183418  mov     r8, [rbp+var_38]; struct IUnknown *
0x14018341c  mov     edx, ebx; int
0x14018341e  mov     rcx, rsi; this
0x140183421  call    ?SetStatusComplete@WorkerAsyncTaskBase@@MEAAXJPEAUIUnknown@@@Z; WorkerAsyncTaskBase::SetStatusComplete(long,IUnknown *)
0x140183426  nop
0x140183427  lea     rcx, [rbp+var_38]; void *
0x14018342b  call    ??1?$VmComPtr@UIVmMetricValueSink@@@Vml@@QEAA@XZ; Vml::VmComPtr<IVmMetricValueSink>::~VmComPtr<IVmMetricValueSink>(void)
0x140183430  mov     rcx, [rbp+var_10]
0x140183434  xor     rcx, rsp; StackCookie
0x140183437  call    __security_check_cookie
0x14018343c  add     rsp, 68h
0x140183440  pop     r15
0x140183442  pop     r14
0x140183444  pop     rdi
0x140183445  pop     rsi
0x140183446  pop     rbx
0x140183447  pop     rbp
0x140183448  retn
```
