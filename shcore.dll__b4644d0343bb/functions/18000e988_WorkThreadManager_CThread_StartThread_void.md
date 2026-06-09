# WorkThreadManager::CThread::StartThread(void)

- ea: `0x18000e988`
- end: `0x18000ead6`
- name: `?StartThread@CThread@WorkThreadManager@@QEAAJXZ`
- size: `334`
- prototype: `__int64 __fastcall(WorkThreadManager::CThread *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800536ac`

## callees

- `0x18000e988`
- `0x18000eadc`
- `0x18000ed04`
- `0x18000ed80`
- `0x1800378d4`
- `0x18003f05c`
- `0x180053bd8`
- `0x180095010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ea0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ea0a`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18000eab9`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18000eab9`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18000ea97`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18000ea97`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000e9f1`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000e9f1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000eaa1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000eaa1`

## string_xrefs

- `0x18000ea47`: `onecore\shell\shcore\libs\comtaskpool\taskpoolprivate.cpp`
- `0x18000ea6a`: `onecore\shell\shcore\libs\comtaskpool\taskpoolprivate.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WorkThreadManager::CThread::StartThread(WorkThreadManager::CThread *this)
{
  signed int started; // ebx
  HANDLE Thread; // rbx
  signed int LastError; // eax
  __int64 v5; // rdx
  int PriorityForOptions; // eax
  DWORD dwCreationFlags; // [rsp+20h] [rbp-18h]
  DWORD dwCreationFlagsa; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  HANDLE v11; // [rsp+48h] [rbp+10h] BYREF

  started = WorkThreadManager::CThread::StartThreadCommon(this);
  if ( started < 0 )
  {
    v5 = 712;
LABEL_10:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
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
    v5 = 713;
    goto LABEL_10;
  }
  _InterlockedIncrement((volatile signed __int32 *)&WorkThreadManager::s_cThreadsStarting);
  (*(void (__fastcall **)(WorkThreadManager::CThread *))(*(_QWORD *)this + 8LL))(this);
  Thread = CreateThread(0, 0, _lambda_9844335fc14345151eefcc3593dd6895_::_lambda_invoker_cdecl_, this, 4u, 0);
  v11 = Thread;
  if ( (((unsigned __int64)Thread + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    LastError = GetLastError();
    started = LastError;
    if ( LastError > 0 )
      started = (unsigned __int16)LastError | 0x80070000;
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
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v11);
    return (unsigned int)started;
  }
  PriorityForOptions = GetPriorityForOptions(*((unsigned int *)this + 37));
  if ( (PriorityForOptions & 0xFFFEFFFF) != 0 )
    SetThreadPriority(Thread, PriorityForOptions);
  ResumeThread(Thread);
  CloseHandle(Thread);
  return 0;
}

```

## disassembly

```asm
0x18000e988  mov     [rsp+arg_0], rbx
0x18000e98d  push    rdi
0x18000e98e  sub     rsp, 30h
0x18000e992  mov     rdi, rcx
0x18000e995  call    ?StartThreadCommon@CThread@WorkThreadManager@@QEAAJXZ; WorkThreadManager::CThread::StartThreadCommon(void)
0x18000e99a  mov     ebx, eax
0x18000e99c  test    eax, eax
0x18000e99e  js      loc_18000EA65
0x18000e9a4  lea     rcx, [rdi+30h]
0x18000e9a8  mov     edx, 1
0x18000e9ad  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18000e9b2  mov     ebx, eax
0x18000e9b4  test    eax, eax
0x18000e9b6  js      loc_18000EACF
0x18000e9bc  lock inc cs:?s_cThreadsStarting@WorkThreadManager@@0KA; ulong WorkThreadManager::s_cThreadsStarting
0x18000e9c3  mov     rax, [rdi]
0x18000e9c6  mov     rcx, rdi
0x18000e9c9  mov     rax, [rax+8]
0x18000e9cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e9d2  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x18000e9db  mov     [rsp+38h+dwCreationFlags], 4; int
0x18000e9e3  mov     r9, rdi; lpParameter
0x18000e9e6  lea     r8, ?_lambda_invoker_cdecl_@_lambda_9844335fc14345151eefcc3593dd6895_@@CAKPEAX@Z; lpStartAddress
0x18000e9ed  xor     edx, edx; dwStackSize
0x18000e9ef  xor     ecx, ecx; lpThreadAttributes
0x18000e9f1  call    cs:__imp_CreateThread
0x18000e9f7  mov     rbx, rax
0x18000e9fa  mov     [rsp+38h+arg_8], rax
0x18000e9ff  inc     rax
0x18000ea02  test    rax, 0FFFFFFFFFFFFFFFEh
0x18000ea08  jnz     short loc_18000EA82
0x18000ea0a  call    cs:__imp_GetLastError
0x18000ea10  mov     ebx, eax
0x18000ea12  test    eax, eax
0x18000ea14  jg      loc_18000EAC1
0x18000ea1a  mov     rax, [rdi]
0x18000ea1d  mov     rcx, rdi
0x18000ea20  mov     rax, [rax+10h]
0x18000ea24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ea29  lea     rcx, [rdi+40h]
0x18000ea2d  xor     edx, edx
0x18000ea2f  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHINSTANCE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(HINSTANCE__ *)
0x18000ea34  lock dec cs:?s_cThreadsStarting@WorkThreadManager@@0KA; ulong WorkThreadManager::s_cThreadsStarting
0x18000ea3b  test    ebx, ebx
0x18000ea3d  jns     short loc_18000EA59
0x18000ea3f  mov     rcx, [rsp+38h]; this
0x18000ea44  mov     r9d, ebx; char *
0x18000ea47  lea     r8, aOnecoreShellSh_7; "onecore\\shell\\shcore\\libs\\comtaskpo"...
0x18000ea4e  mov     edx, 2DDh; void *
0x18000ea53  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ea58  nop
0x18000ea59  lea     rcx, [rsp+38h+arg_8]
0x18000ea5e  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18000ea63  jmp     short loc_18000EA7E
0x18000ea65  mov     edx, 2C8h; void *
0x18000ea6a  lea     r8, aOnecoreShellSh_7; "onecore\\shell\\shcore\\libs\\comtaskpo"...
0x18000ea71  mov     r9d, ebx; char *
0x18000ea74  mov     rcx, [rsp+38h]; this
0x18000ea79  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ea7e  mov     eax, ebx
0x18000ea80  jmp     short loc_18000EAA9
0x18000ea82  mov     ecx, [rdi+94h]
0x18000ea88  call    ?GetPriorityForOptions@@YAHW4TaskOptions@Internal@Windows@@@Z; GetPriorityForOptions(Windows::Internal::TaskOptions)
0x18000ea8d  test    eax, 0FFFEFFFFh
0x18000ea92  jnz     short loc_18000EAB4
0x18000ea94  mov     rcx, rbx; hThread
0x18000ea97  call    cs:__imp_ResumeThread
0x18000ea9d  nop
0x18000ea9e  mov     rcx, rbx; hObject
0x18000eaa1  call    cs:__imp_CloseHandle
0x18000eaa7  xor     eax, eax
0x18000eaa9  mov     rbx, [rsp+38h+arg_0]
0x18000eaae  add     rsp, 30h
0x18000eab2  pop     rdi
0x18000eab3  retn
0x18000eab4  mov     edx, eax; nPriority
0x18000eab6  mov     rcx, rbx; hThread
0x18000eab9  call    cs:__imp_SetThreadPriority
0x18000eabf  jmp     short loc_18000EA94
0x18000eac1  movzx   ebx, ax
0x18000eac4  or      ebx, 80070000h
0x18000eaca  jmp     loc_18000EA1A
0x18000eacf  mov     edx, 2C9h
0x18000ead4  jmp     short loc_18000EA6A
```
