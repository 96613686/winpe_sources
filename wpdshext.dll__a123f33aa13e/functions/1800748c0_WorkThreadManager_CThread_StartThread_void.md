# WorkThreadManager::CThread::StartThread(void)

- ea: `0x1800748c0`
- end: `0x1800749f1`
- name: `?StartThread@CThread@WorkThreadManager@@QEAAJXZ`
- size: `305`
- prototype: `__int64 __fastcall(WorkThreadManager::CThread *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180074e7c`

## callees

- `0x18002a360`
- `0x18002bee4`
- `0x18002da70`
- `0x1800362d4`
- `0x180036328`
- `0x180059aac`
- `0x180073dd0`
- `0x1800748c0`
- `0x1800749f8`
- `0x180078010`

## import_xrefs

- `KERNEL32!ResumeThread` at `0x1800749d2`
- `KERNEL32!ResumeThread` at `0x1800749d2`
- `KERNEL32!SetThreadPriority` at `0x1800749c9`
- `KERNEL32!SetThreadPriority` at `0x1800749c9`

## string_xrefs

- `0x1800748e2`: `onecore\shell\shcore\libs\comtaskpool\taskpoolprivate.cpp`
- `0x18007499c`: `onecore\shell\shcore\libs\comtaskpool\taskpoolprivate.cpp`

## pseudocode

```c
__int64 __fastcall WorkThreadManager::CThread::StartThread(WorkThreadManager::CThread *this)
{
  signed int started; // ebx
  __int64 v3; // rdx
  HANDLE Thread_0; // rbx
  signed int LastError_0; // eax
  int PriorityForOptions; // eax
  DWORD dwCreationFlags; // [rsp+20h] [rbp-18h]
  DWORD dwCreationFlagsa; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  HANDLE v11; // [rsp+48h] [rbp+10h] BYREF

  started = WorkThreadManager::CThread::StartThreadCommon(this);
  if ( started < 0 )
  {
    v3 = 712;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v3,
      (unsigned int)"onecore\\shell\\shcore\\libs\\comtaskpool\\taskpoolprivate.cpp",
      (const char *)(unsigned int)started,
      dwCreationFlags);
    return (unsigned int)started;
  }
  started = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
              (char *)this + 48,
              1);
  if ( started < 0 )
  {
    v3 = 713;
    goto LABEL_3;
  }
  _InterlockedIncrement((volatile signed __int32 *)&WorkThreadManager::s_cThreadsStarting);
  (*(void (__fastcall **)(WorkThreadManager::CThread *))(*(_QWORD *)this + 8LL))(this);
  Thread_0 = CreateThread_0(0, 0, _lambda_9844335fc14345151eefcc3593dd6895_::_lambda_invoker_cdecl_, this, 4u, 0);
  v11 = Thread_0;
  if ( (((unsigned __int64)Thread_0 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    PriorityForOptions = GetPriorityForOptions(*((unsigned int *)this + 37));
    if ( (PriorityForOptions & 0xFFFEFFFF) != 0 )
      SetThreadPriority(Thread_0, PriorityForOptions);
    ResumeThread(Thread_0);
    started = 0;
  }
  else
  {
    LastError_0 = GetLastError_0();
    started = LastError_0;
    if ( LastError_0 > 0 )
      started = (unsigned __int16)LastError_0 | 0x80070000;
    (*(void (__fastcall **)(WorkThreadManager::CThread *))(*(_QWORD *)this + 16LL))(this);
    wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(
      (char *)this + 64,
      0);
    _InterlockedDecrement((volatile signed __int32 *)&WorkThreadManager::s_cThreadsStarting);
    if ( started < 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2DD,
        (unsigned int)"onecore\\shell\\shcore\\libs\\comtaskpool\\taskpoolprivate.cpp",
        (const char *)(unsigned int)started,
        dwCreationFlagsa);
  }
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v11);
  return (unsigned int)started;
}

```

## disassembly

```asm
0x1800748c0  mov     [rsp+arg_0], rbx
0x1800748c5  push    rdi
0x1800748c6  sub     rsp, 30h
0x1800748ca  mov     rdi, rcx
0x1800748cd  call    ?StartThreadCommon@CThread@WorkThreadManager@@QEAAJXZ; WorkThreadManager::CThread::StartThreadCommon(void)
0x1800748d2  mov     ebx, eax
0x1800748d4  test    eax, eax
0x1800748d6  jns     short loc_1800748F6
0x1800748d8  mov     edx, 2C8h; void *
0x1800748dd  mov     rcx, [rsp+38h]; this
0x1800748e2  lea     r8, aOnecoreShellSh; "onecore\\shell\\shcore\\libs\\comtaskpo"...
0x1800748e9  mov     r9d, ebx; char *
0x1800748ec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800748f1  jmp     loc_1800749E4
0x1800748f6  lea     rcx, [rdi+30h]
0x1800748fa  mov     edx, 1
0x1800748ff  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180074904  mov     ebx, eax
0x180074906  test    eax, eax
0x180074908  jns     short loc_180074911
0x18007490a  mov     edx, 2C9h
0x18007490f  jmp     short loc_1800748DD
0x180074911  lock inc cs:?s_cThreadsStarting@WorkThreadManager@@0KA; ulong WorkThreadManager::s_cThreadsStarting
0x180074918  mov     rax, [rdi]
0x18007491b  mov     rcx, rdi
0x18007491e  mov     rax, [rax+8]
0x180074922  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074927  mov     r9, rdi; lpParameter
0x18007492a  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x180074933  lea     r8, ?_lambda_invoker_cdecl_@_lambda_9844335fc14345151eefcc3593dd6895_@@CAKPEAX@Z; lpStartAddress
0x18007493a  mov     [rsp+38h+dwCreationFlags], 4; int
0x180074942  xor     edx, edx; dwStackSize
0x180074944  xor     ecx, ecx; lpThreadAttributes
0x180074946  call    CreateThread_0
0x18007494b  mov     rbx, rax
0x18007494e  mov     [rsp+38h+arg_8], rax
0x180074953  inc     rax
0x180074956  test    rax, 0FFFFFFFFFFFFFFFEh
0x18007495c  jnz     short loc_1800749B2
0x18007495e  call    GetLastError_0
0x180074963  mov     ebx, eax
0x180074965  test    eax, eax
0x180074967  jle     short loc_180074972
0x180074969  movzx   ebx, ax
0x18007496c  or      ebx, 80070000h
0x180074972  mov     rax, [rdi]
0x180074975  mov     rcx, rdi
0x180074978  mov     rax, [rax+10h]
0x18007497c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074981  lea     rcx, [rdi+40h]
0x180074985  xor     edx, edx
0x180074987  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHINSTANCE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(HINSTANCE__ *)
0x18007498c  lock dec cs:?s_cThreadsStarting@WorkThreadManager@@0KA; ulong WorkThreadManager::s_cThreadsStarting
0x180074993  test    ebx, ebx
0x180074995  jns     short loc_1800749DA
0x180074997  mov     rcx, [rsp+38h]; this
0x18007499c  lea     r8, aOnecoreShellSh; "onecore\\shell\\shcore\\libs\\comtaskpo"...
0x1800749a3  mov     r9d, ebx; char *
0x1800749a6  mov     edx, 2DDh; void *
0x1800749ab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800749b0  jmp     short loc_1800749DA
0x1800749b2  mov     ecx, [rdi+94h]
0x1800749b8  call    ?GetPriorityForOptions@@YAHW4TaskOptions@Internal@Windows@@@Z; GetPriorityForOptions(Windows::Internal::TaskOptions)
0x1800749bd  test    eax, 0FFFEFFFFh
0x1800749c2  jz      short loc_1800749CF
0x1800749c4  mov     edx, eax; nPriority
0x1800749c6  mov     rcx, rbx; hThread
0x1800749c9  call    cs:__imp_SetThreadPriority
0x1800749cf  mov     rcx, rbx; hThread
0x1800749d2  call    cs:__imp_ResumeThread
0x1800749d8  xor     ebx, ebx
0x1800749da  lea     rcx, [rsp+38h+arg_8]
0x1800749df  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800749e4  mov     eax, ebx
0x1800749e6  mov     rbx, [rsp+38h+arg_0]
0x1800749eb  add     rsp, 30h
0x1800749ef  pop     rdi
0x1800749f0  retn
```
