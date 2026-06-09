# WorkerTaskResuming::RunTask(void)

- ea: `0x140170310`
- end: `0x14017065a`
- name: `?RunTask@WorkerTaskResuming@@UEAAXXZ`
- size: `842`
- prototype: `void __fastcall(WorkerTaskResuming *__hidden this)`
- caller_count: `0`
- callee_count: `16`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x140031480`
- `0x1400364a0`
- `0x14003b720`
- `0x1400544a8`
- `0x14008a328`
- `0x1400a61c8`
- `0x1400a6470`
- `0x1400c4fe8`
- `0x1400cf1dc`
- `0x1400dc8cc`
- `0x1400e7fe0`
- `0x14011c570`
- `0x14011ea40`
- `0x14015f0ec`
- `0x140170310`
- `0x1402cb010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1401704fa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1401704fa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140170539`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140170539`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14017042e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14017042e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140170515`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140170515`
- `vmprox!GetVmErrInfo` at `0x140170610`
- `vmprox!GetVmErrInfo` at `0x140170610`
- `vid!VidSuspendClear` at `0x1401703e8`
- `vid!VidSuspendClear` at `0x1401703e8`

## string_xrefs

- `0x140170406`: `onecore\vm\worker\wpcore\workertaskresuming.cpp`

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
        VmlDebugTraceEx(0, &off_1402E30D0);
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
0x140170310  push    rbp
0x140170312  push    rbx
0x140170313  push    rsi
0x140170314  push    rdi
0x140170315  push    r14
0x140170317  push    r15
0x140170319  mov     rbp, rsp
0x14017031c  sub     rsp, 68h
0x140170320  mov     rax, cs:__security_cookie
0x140170327  xor     rax, rsp
0x14017032a  mov     [rbp+var_10], rax
0x14017032e  mov     rsi, rcx
0x140170331  mov     [rbp+var_38], 0
0x140170339  mov     rax, [rcx+10h]
0x14017033d  mov     rcx, [rax+410h]
0x140170344  mov     rax, [rcx]
0x140170347  mov     rax, [rax+260h]
0x14017034e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140170353  cmp     dword ptr [rsi+190h], 13h
0x14017035a  jnz     short loc_140170378
0x14017035c  mov     rcx, [rsi+10h]; this
0x140170360  cmp     dword ptr [rcx+928h], 4
0x140170367  jnz     short loc_140170378
0x140170369  call    ?ValidateRecovery@VirtualMachine@@QEAAJXZ; VirtualMachine::ValidateRecovery(void)
0x14017036e  mov     ebx, eax
0x140170370  test    eax, eax
0x140170372  js      loc_140170449
0x140170378  mov     rcx, [rsi+10h]
0x14017037c  mov     edi, [rcx+928h]
0x140170382  lea     eax, [rdi-4]
0x140170385  neg     eax
0x140170387  sbb     r15d, r15d
0x14017038a  mov     ebx, 5
0x14017038f  add     r15d, ebx
0x140170392  xor     eax, eax
0x140170394  cmp     edi, 4
0x140170397  cmovnz  ebx, eax
0x14017039a  mov     rcx, [rcx+410h]
0x1401703a1  mov     rax, [rcx]
0x1401703a4  mov     rax, [rax+1F8h]
0x1401703ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401703b0  mov     r14d, ebx
0x1401703b3  bts     r14d, 8
0x1401703b8  test    al, al
0x1401703ba  cmovz   r14d, ebx
0x1401703be  mov     rcx, [rsi+10h]
0x1401703c2  cmp     dword ptr [rcx+0A3Ch], 0
0x1401703c9  jz      loc_1401704C2
0x1401703cf  mov     rcx, [rcx+400h]
0x1401703d6  add     rcx, 18h
0x1401703da  mov     rax, [rcx]
0x1401703dd  mov     rax, [rax]
0x1401703e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401703e5  mov     rcx, rax
0x1401703e8  call    cs:__imp_VidSuspendClear
0x1401703ef  nop     dword ptr [rax+rax+00h]
0x1401703f4  test    eax, eax
0x1401703f6  jnz     loc_1401704B0
0x1401703fc  mov     rcx, [rbp+30h]; this
0x140170400  mov     r9d, 8000FFFFh; char *
0x140170406  lea     r8, aOnecoreVmWorke_39; "onecore\\vm\\worker\\wpcore\\workertask"...
0x14017040d  lea     edx, [rax+7Ch]; void *
0x140170410  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x140170415  xor     ecx, ecx
0x140170417  call    VmlIsDebugTraceEnabled
0x14017041c  test    eax, eax
0x14017041e  jz      short loc_14017042E
0x140170420  lea     rdx, off_1402E30D0; "Unexpected error.\n"
0x140170427  xor     ecx, ecx
0x140170429  call    VmlDebugTraceEx
0x14017042e  call    cs:__imp_GetLastError
0x140170435  nop     dword ptr [rax+rax+00h]
0x14017043a  mov     ebx, eax
0x14017043c  test    eax, eax
0x14017043e  jle     short loc_140170449
0x140170440  movzx   ebx, ax
0x140170443  or      ebx, 80070000h
0x140170449  mov     eax, [rsi+190h]
0x14017044f  test    ebx, ebx
0x140170451  js      loc_14017057E
0x140170457  movups  xmm0, cs:MSVM_RESUME_SUCCESS
0x14017045e  movdqu  xmmword ptr [rbp+EventDescriptor.Id], xmm0
0x140170463  cmp     eax, 14h
0x140170466  jnz     short loc_140170474
0x140170468  movups  xmm0, cs:MSVM_RESUME_CRITICAL_SUCCESS
0x14017046f  movdqu  xmmword ptr [rbp+EventDescriptor.Id], xmm0
0x140170474  mov     rcx, [rsi+10h]
0x140170478  lea     rax, [rcx+480h]
0x14017047f  mov     [rbp+var_30], rax
0x140170483  add     rcx, 10h; this
0x140170487  call    ?GetVmName@VirtualMachine@@UEBAPEBGXZ; VirtualMachine::GetVmName(void)
0x14017048c  mov     [rbp+var_28], rax
0x140170490  lea     rax, [rbp+var_30]
0x140170494  mov     [rsp+68h+var_48], rax; __int64
0x140170499  lea     r9, [rbp+var_28]
0x14017049d  mov     edx, 1; unsigned int
0x1401704a2  lea     rcx, [rbp+EventDescriptor]; EventDescriptor
0x1401704a6  call    ??$VmEventWrite@PEBGPEBG@@YAXPEBU_EVENT_DESCRIPTOR@@IAEBU_GUID@@$$QEAPEBG2@Z; VmEventWrite<ushort const *,ushort const *>(_EVENT_DESCRIPTOR const *,uint,_GUID const &,ushort const * &&,ushort const * &&)
0x1401704ab  jmp     loc_140170610
0x1401704b0  mov     rax, [rsi+10h]
0x1401704b4  mov     dword ptr [rax+0A3Ch], 0
0x1401704be  mov     rcx, [rsi+10h]
0x1401704c2  cmp     edi, 4
0x1401704c5  jnz     short loc_1401704D3
0x1401704c7  mov     rcx, [rcx+3D8h]; this
0x1401704ce  call    ?NotifyVmResumedFromCriticalError@VirtualMotherboard@@QEAAJXZ; VirtualMotherboard::NotifyVmResumedFromCriticalError(void)
0x1401704d3  mov     r8d, r15d
0x1401704d6  mov     edx, r14d
0x1401704d9  mov     rcx, [rsi+10h]
0x1401704dd  call    ?StartVm@VirtualMachine@@QEAAJIW4__MIDL___MIDL_itf_vmbservices_0000_0011_0002@@@Z; VirtualMachine::StartVm(uint,__MIDL___MIDL_itf_vmbservices_0000_0011_0002)
0x1401704e2  mov     ebx, eax
0x1401704e4  test    eax, eax
0x1401704e6  js      loc_140170449
0x1401704ec  mov     rbx, [rsi+10h]
0x1401704f0  lea     rdi, [rbx+998h]
0x1401704f7  mov     rcx, rdi; lpCriticalSection
0x1401704fa  call    cs:__imp_EnterCriticalSection
0x140170501  nop     dword ptr [rax+rax+00h]
0x140170506  xor     r9d, r9d; msWindowLength
0x140170509  xor     r8d, r8d; msPeriod
0x14017050c  xor     edx, edx; pftDueTime
0x14017050e  mov     rcx, [rbx+9C0h]; pti
0x140170515  call    cs:__imp_SetThreadpoolTimer
0x14017051c  nop     dword ptr [rax+rax+00h]
0x140170521  mov     qword ptr [rbx+9C8h], 0
0x14017052c  mov     dword ptr [rbx+9D0h], 0
0x140170536  mov     rcx, rdi; lpCriticalSection
0x140170539  call    cs:__imp_LeaveCriticalSection
0x140170540  nop     dword ptr [rax+rax+00h]
0x140170545  mov     rax, [rsi+10h]
0x140170549  mov     rcx, [rax+428h]
0x140170550  mov     rax, [rcx]
0x140170553  mov     rax, [rax+48h]
0x140170557  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14017055c  mov     r8d, [rsi+190h]
0x140170563  mov     edx, 2
0x140170568  mov     rcx, [rsi+10h]
0x14017056c  call    ?SetState@VirtualMachine@@QEAAHW4_VM_STATE@@W4_VM_STATE_REASON_CODE@@@Z; VirtualMachine::SetState(_VM_STATE,_VM_STATE_REASON_CODE)
0x140170571  xor     ebx, ebx
0x140170573  mov     eax, [rsi+190h]
0x140170579  jmp     loc_140170457
0x14017057e  movups  xmm0, cs:MSVMB_WP_RESUME_ERROR
0x140170585  movdqu  xmmword ptr [rbp+EventDescriptor.Id], xmm0
0x14017058a  cmp     eax, 14h
0x14017058d  jnz     short loc_14017059B
0x14017058f  movups  xmm0, cs:MSVMB_WP_RESUME_CRITICAL_ERROR
0x140170596  movdqu  xmmword ptr [rbp+EventDescriptor.Id], xmm0
0x14017059b  mov     rax, [rsi+10h]
0x14017059f  mov     rcx, [rax+410h]
0x1401705a6  mov     rax, [rcx]
0x1401705a9  mov     rax, [rax+258h]
0x1401705b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401705b5  mov     rcx, [rsi+10h]
0x1401705b9  mov     eax, [rcx+928h]
0x1401705bf  sub     eax, 4
0x1401705c2  neg     eax
0x1401705c4  sbb     edx, edx
0x1401705c6  add     edx, 4
0x1401705c9  mov     r8d, 15h
0x1401705cf  call    ?SetState@VirtualMachine@@QEAAHW4_VM_STATE@@W4_VM_STATE_REASON_CODE@@@Z; VirtualMachine::SetState(_VM_STATE,_VM_STATE_REASON_CODE)
0x1401705d4  mov     rcx, [rsi+10h]
0x1401705d8  lea     rax, [rcx+480h]
0x1401705df  mov     [rbp+var_28], rax
0x1401705e3  add     rcx, 10h; this
0x1401705e7  call    ?GetVmName@VirtualMachine@@UEBAPEBGXZ; VirtualMachine::GetVmName(void)
0x1401705ec  mov     [rbp+var_30], rax
0x1401705f0  lea     rax, [rbp+var_28]
0x1401705f4  mov     [rsp+68h+var_40], rax; __int64
0x1401705f9  lea     rax, [rbp+var_30]
0x1401705fd  mov     [rsp+68h+var_48], rax; __int64
0x140170602  mov     edx, 0Dh; unsigned int
0x140170607  lea     rcx, [rbp+EventDescriptor]; struct _EVENT_DESCRIPTOR *
0x14017060b  call    ??$VmEventWriteAndReport@PEBGPEBG@@YAXPEBU_EVENT_DESCRIPTOR@@IAEBU_GUID@@PEBG$$QEAPEBG3@Z; VmEventWriteAndReport<ushort const *,ushort const *>(_EVENT_DESCRIPTOR const *,uint,_GUID const &,ushort const *,ushort const * &&,ushort const * &&)
0x140170610  call    cs:__imp_GetVmErrInfo
0x140170617  nop     dword ptr [rax+rax+00h]
0x14017061c  mov     rdx, rax
0x14017061f  lea     rcx, [rbp+var_38]
0x140170623  call    ??$Attach@UIVmSimpleTask@@@?$VmComPtr@UIVmSimpleTask@@@Vml@@QEAAXPEAUIVmSimpleTask@@@Z; Vml::VmComPtr<IVmSimpleTask>::Attach<IVmSimpleTask>(IVmSimpleTask *)
0x140170628  mov     r8, [rbp+var_38]; struct IUnknown *
0x14017062c  mov     edx, ebx; int
0x14017062e  mov     rcx, rsi; this
0x140170631  call    ?SetStatusComplete@WorkerAsyncTaskBase@@MEAAXJPEAUIUnknown@@@Z; WorkerAsyncTaskBase::SetStatusComplete(long,IUnknown *)
0x140170636  nop
0x140170637  lea     rcx, [rbp+var_38]; void *
0x14017063b  call    ??1?$VmComPtr@UIVmMetricValueSink@@@Vml@@QEAA@XZ; Vml::VmComPtr<IVmMetricValueSink>::~VmComPtr<IVmMetricValueSink>(void)
0x140170640  mov     rcx, [rbp+var_10]
0x140170644  xor     rcx, rsp; StackCookie
0x140170647  call    __security_check_cookie
0x14017064c  add     rsp, 68h
0x140170650  pop     r15
0x140170652  pop     r14
0x140170654  pop     rdi
0x140170655  pop     rsi
0x140170656  pop     rbx
0x140170657  pop     rbp
0x140170658  retn
```
