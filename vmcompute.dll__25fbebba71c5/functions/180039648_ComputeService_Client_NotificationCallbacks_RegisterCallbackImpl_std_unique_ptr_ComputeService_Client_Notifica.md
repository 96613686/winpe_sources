# ComputeService::Client::NotificationCallbacks::RegisterCallbackImpl(std::unique_ptr<ComputeService::Client::NotificationCallbacks::NotificationContext,std::default_delete<ComputeService::Client::NotificationCallbacks::NotificationContext>>,void *,void *)

- ea: `0x180039648`
- end: `0x1800399d3`
- name: `?RegisterCallbackImpl@NotificationCallbacks@Client@ComputeService@@AEAAPEAXV?$unique_ptr@UNotificationContext@NotificationCallbacks@Client@ComputeService@@U?$default_delete@UNotificationContext@NotificationCallbacks@Client@ComputeService@@@std@@@std@@PEAX1@Z`
- size: `907`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800395a4`

## callees

- `0x180002f50`
- `0x180002f74`
- `0x180003388`
- `0x18000d0ec`
- `0x18000d108`
- `0x18000e664`
- `0x18000e8bc`
- `0x180012048`
- `0x1800188a4`
- `0x1800391e8`
- `0x180039254`
- `0x180039648`
- `0x180039c70`
- `0x180039e00`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800397fe`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800397fe`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800398ec`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800398ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003972b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003972b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003974a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003974a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1800396a4`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1800396dd`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1800396a4`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1800396dd`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18003973c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18003973c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180039713`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180039713`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180039903`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18003991a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180039903`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18003991a`

## string_xrefs

- `0x1800397b9`: `onecore\vm\compute\dll\lib\core\notificationcallbacks.cpp`
- `0x180039982`: `onecore\vm\compute\dll\lib\core\notificationcallbacks.cpp`
- `0x180039994`: `onecore\vm\compute\dll\lib\core\notificationcallbacks.cpp`
- `0x1800399a6`: `onecore\vm\compute\dll\lib\core\notificationcallbacks.cpp`
- `0x1800399b8`: `onecore\vm\compute\dll\lib\core\notificationcallbacks.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
PVOID __fastcall ComputeService::Client::NotificationCallbacks::RegisterCallbackImpl(
        __int64 a1,
        char *a2,
        char *a3,
        __int64 a4)
{
  char *v6; // rbx
  PTP_WAIT ThreadpoolWait; // rax
  const char *v8; // r9
  char *v9; // rbx
  PTP_WAIT v10; // rax
  const char *v11; // r9
  PVOID v12; // rsi
  const char *v13; // r9
  PTP_WORK ThreadpoolWork; // r15
  struct _TP_WORK *v15; // r14
  DWORD LastError; // ebx
  const char *v17; // rbx
  unsigned int v18; // eax
  char v19; // r14
  PVOID v20; // rsi
  RTL_SRWLOCK *v21; // rbx
  char **v22; // r15
  char *v23; // rcx
  char *v24; // rax
  int v25; // r12d
  char **v26; // r13
  char *v27; // rbx
  char **v28; // rax
  char *v29; // rdx
  PVOID v30; // rbx
  int v32; // [rsp+20h] [rbp-49h]
  __int64 v33; // [rsp+30h] [rbp-39h] BYREF
  __int64 v34; // [rsp+38h] [rbp-31h] BYREF
  char **v35; // [rsp+40h] [rbp-29h] BYREF
  unsigned __int64 v36; // [rsp+48h] [rbp-21h]
  _QWORD v37[2]; // [rsp+50h] [rbp-19h] BYREF
  __int64 v38; // [rsp+60h] [rbp-9h]
  __int64 v39; // [rsp+68h] [rbp-1h]
  char *v40[2]; // [rsp+70h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v40[1] = a2;
  v40[0] = a3;
  **(_QWORD **)a2 = a3;
  *(_QWORD *)(*(_QWORD *)a2 + 24LL) = a4;
  *(_QWORD *)(*(_QWORD *)a2 + 96LL) = a1;
  v6 = *(char **)a2;
  ThreadpoolWait = CreateThreadpoolWait(ComputeService::Client::NotificationCallbacks::WaitCallback, *(PVOID *)a2, 0);
  wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&public: static void wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(
    v6 + 40,
    ThreadpoolWait);
  v9 = *(char **)a2;
  if ( !*(_QWORD *)(*(_QWORD *)a2 + 40LL) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x7E,
      (unsigned int)"onecore\\vm\\compute\\dll\\lib\\core\\notificationcallbacks.cpp",
      v8);
  v10 = CreateThreadpoolWait(ComputeService::Client::NotificationCallbacks::WaitCallback, *(PVOID *)a2, 0);
  wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&public: static void wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(
    v9 + 56,
    v10);
  v12 = *(PVOID *)a2;
  if ( !*(_QWORD *)(*(_QWORD *)a2 + 56LL) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x82,
      (unsigned int)"onecore\\vm\\compute\\dll\\lib\\core\\notificationcallbacks.cpp",
      v11);
  ThreadpoolWork = CreateThreadpoolWork(ComputeService::Client::NotificationCallbacks::CleanupCallback, *(PVOID *)a2, 0);
  v15 = (struct _TP_WORK *)*((_QWORD *)v12 + 11);
  if ( v15 )
  {
    LastError = GetLastError();
    CloseThreadpoolWork(v15);
    SetLastError(LastError);
  }
  *((_QWORD *)v12 + 11) = ThreadpoolWork;
  if ( !*(_QWORD *)(*(_QWORD *)a2 + 88LL) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x87,
      (unsigned int)"onecore\\vm\\compute\\dll\\lib\\core\\notificationcallbacks.cpp",
      v13);
  v17 = v40[0];
  v33 = wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator&(*(_QWORD *)a2 + 48LL);
  v34 = wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator&(*(_QWORD *)a2 + 32LL);
  v18 = ComputeService::Client::InvokeRpcFunction<long (*)(void *,void * *,void * *),void * &,void * *,void * *>(
          *(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))a1,
          v40,
          &v34,
          &v33);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x90,
    (unsigned int)"onecore\\vm\\compute\\dll\\lib\\core\\notificationcallbacks.cpp",
    (const char *)v18,
    (int)"Failed to register notifications for handle %p",
    v17);
  v38 = 257;
  v37[0] = a1;
  v37[1] = v40;
  v19 = 1;
  v20 = *(PVOID *)a2;
  v21 = (RTL_SRWLOCK *)(a1 + 40);
  v33 = a1 + 40;
  AcquireSRWLockExclusive((PSRWLOCK)(a1 + 40));
  v39 = a1 + 40;
  v22 = (char **)(a1 + 24);
  v23 = *(char **)(a1 + 24);
  v24 = (char *)*((_QWORD *)v23 + 1);
  v25 = 0;
  v34 = 0;
  if ( v24[25] )
  {
    v26 = (char **)v24;
  }
  else
  {
    do
    {
      v26 = (char **)v24;
      if ( (char *)*((_QWORD *)v24 + 4) >= v40[0] )
      {
        v25 = 1;
        v23 = v24;
        v24 = *(char **)v24;
      }
      else
      {
        v25 = 0;
        v24 = (char *)*((_QWORD *)v24 + 2);
      }
    }
    while ( !v24[25] );
  }
  if ( v23[25] || v40[0] < (char *)*((_QWORD *)v23 + 4) )
  {
    if ( v22[1] == (char *)0x555555555555555LL )
      std::_Throw_tree_length_error();
    v27 = *v22;
    v35 = v22;
    v36 = 0;
    v28 = (char **)operator new(0x30u);
    v28[4] = v40[0];
    v29 = *(char **)a2;
    *(_QWORD *)a2 = 0;
    v28[5] = v29;
    *v28 = v27;
    v28[1] = v27;
    v28[2] = v27;
    *((_WORD *)v28 + 12) = 0;
    v35 = v26;
    v36 = __PAIR64__(v34, v25);
    std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,Schema::Responses::Service::PropertyResponse>>>::_Insert_node(
      v22,
      &v35,
      v28);
    v21 = (RTL_SRWLOCK *)v33;
  }
  else
  {
    v19 = 0;
  }
  if ( !v19 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x9D,
      (unsigned int)"onecore\\vm\\compute\\dll\\lib\\core\\notificationcallbacks.cpp",
      (const char *)0xC0370104LL,
      v32);
  if ( v21 )
    ReleaseSRWLockExclusive(v21);
  SetThreadpoolWait(*((PTP_WAIT *)v20 + 5), *((HANDLE *)v20 + 4), 0);
  SetThreadpoolWait(*((PTP_WAIT *)v20 + 7), *((HANDLE *)v20 + 6), 0);
  BYTE1(v38) = 0;
  wil::details::ScopeExitFnGuard__lambda_8e49fbe7b9768f69f4d98cda15c76ced___::operator()(v37);
  v30 = *(PVOID *)a2;
  if ( *(_QWORD *)a2 )
  {
    ComputeService::Client::NotificationCallbacks::NotificationContext::~NotificationContext(*(ComputeService::Client::NotificationCallbacks::NotificationContext **)a2);
    operator delete(v30, 0x68u);
  }
  return v20;
}

```

## disassembly

```asm
0x180039648  mov     [rsp-8+arg_18], rbx
0x18003964d  push    rbp
0x18003964e  push    rsi
0x18003964f  push    rdi
0x180039650  push    r12
0x180039652  push    r13
0x180039654  push    r14
0x180039656  push    r15
0x180039658  lea     rbp, [rsp-27h]
0x18003965d  sub     rsp, 90h
0x180039664  mov     rax, cs:__security_cookie
0x18003966b  xor     rax, rsp
0x18003966e  mov     [rbp+57h+var_40], rax
0x180039672  mov     rdi, rdx
0x180039675  mov     r12, rcx
0x180039678  mov     [rbp+57h+var_48], rdx
0x18003967c  mov     [rbp+57h+var_50], r8
0x180039680  mov     rax, [rdx]
0x180039683  mov     [rax], r8
0x180039686  mov     rax, [rdx]
0x180039689  mov     [rax+18h], r9
0x18003968d  mov     rax, [rdx]
0x180039690  mov     [rax+60h], rcx
0x180039694  mov     rbx, [rdx]
0x180039697  xor     r8d, r8d; pcbe
0x18003969a  mov     rdx, rbx; pv
0x18003969d  lea     rcx, ?WaitCallback@NotificationCallbacks@Client@ComputeService@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x1800396a4  call    cs:__imp_CreateThreadpoolWait
0x1800396ab  nop     dword ptr [rax+rax+00h]
0x1800396b0  lea     rcx, [rbx+28h]
0x1800396b4  mov     rdx, rax
0x1800396b7  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_WAIT@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_WAIT@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(_TP_WAIT *)
0x1800396bc  mov     rbx, [rdi]
0x1800396bf  mov     rcx, [rbp+5Fh]; this
0x1800396c3  xor     r13d, r13d
0x1800396c6  cmp     [rbx+28h], r13
0x1800396ca  jz      loc_180039994
0x1800396d0  xor     r8d, r8d; pcbe
0x1800396d3  mov     rdx, rbx; pv
0x1800396d6  lea     rcx, ?WaitCallback@NotificationCallbacks@Client@ComputeService@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x1800396dd  call    cs:__imp_CreateThreadpoolWait
0x1800396e4  nop     dword ptr [rax+rax+00h]
0x1800396e9  lea     rcx, [rbx+38h]
0x1800396ed  mov     rdx, rax
0x1800396f0  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_WAIT@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_WAIT@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(_TP_WAIT *)
0x1800396f5  mov     rsi, [rdi]
0x1800396f8  mov     rcx, [rbp+5Fh]; this
0x1800396fc  cmp     [rsi+38h], r13
0x180039700  jz      loc_1800399A6
0x180039706  xor     r8d, r8d; pcbe
0x180039709  mov     rdx, rsi; pv
0x18003970c  lea     rcx, ?CleanupCallback@NotificationCallbacks@Client@ComputeService@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x180039713  call    cs:__imp_CreateThreadpoolWork
0x18003971a  nop     dword ptr [rax+rax+00h]
0x18003971f  mov     r15, rax
0x180039722  mov     r14, [rsi+58h]
0x180039726  test    r14, r14
0x180039729  jz      short loc_180039756
0x18003972b  call    cs:__imp_GetLastError
0x180039732  nop     dword ptr [rax+rax+00h]
0x180039737  mov     ebx, eax
0x180039739  mov     rcx, r14; pwk
0x18003973c  call    cs:__imp_CloseThreadpoolWork
0x180039743  nop     dword ptr [rax+rax+00h]
0x180039748  mov     ecx, ebx; dwErrCode
0x18003974a  call    cs:__imp_SetLastError
0x180039751  nop     dword ptr [rax+rax+00h]
0x180039756  mov     [rsi+58h], r15
0x18003975a  mov     rcx, [rdi]
0x18003975d  mov     rax, [rbp+5Fh]
0x180039761  cmp     [rcx+58h], r13
0x180039765  jz      loc_1800399B8
0x18003976b  mov     rbx, [rbp+57h+var_50]
0x18003976f  add     rcx, 30h ; '0'
0x180039773  call    ??I?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator&(void)
0x180039778  mov     [rbp+57h+var_90], rax
0x18003977c  mov     rcx, [rdi]
0x18003977f  add     rcx, 20h ; ' '
0x180039783  call    ??I?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator&(void)
0x180039788  mov     [rbp+57h+var_88], rax
0x18003978c  lea     r9, [rbp+57h+var_90]
0x180039790  lea     r8, [rbp+57h+var_88]
0x180039794  lea     rdx, [rbp+57h+var_50]
0x180039798  mov     rcx, [r12]
0x18003979c  call    ??$InvokeRpcFunction@P6AJPEAXPEAPEAX1@ZAEAPEAXPEAPEAXPEAPEAX@Client@ComputeService@@YA?A_TP6AJPEAXPEAPEAX1@ZAEAPEAX$$QEAPEAPEAX4@Z
0x1800397a1  mov     rcx, [rbp+5Fh]; this
0x1800397a5  mov     [rsp+0C0h+var_98], rbx; char *
0x1800397aa  lea     rdx, aFailedToRegist; "Failed to register notifications for ha"...
0x1800397b1  mov     qword ptr [rsp+0C0h+var_A0], rdx; int
0x1800397b6  mov     r9d, eax; char *
0x1800397b9  lea     r8, aOnecoreVmCompu_14; "onecore\\vm\\compute\\dll\\lib\\core\\n"...
0x1800397c0  mov     edx, 90h; void *
0x1800397c5  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800397ca  xorps   xmm0, xmm0
0x1800397cd  xor     eax, eax
0x1800397cf  movups  [rbp+57h+var_70], xmm0
0x1800397d3  mov     [rbp+57h+var_60], rax
0x1800397d7  mov     qword ptr [rbp+57h+var_70], r12
0x1800397db  lea     rax, [rbp+57h+var_50]
0x1800397df  mov     qword ptr [rbp+57h+var_70+8], rax
0x1800397e3  mov     r14d, 1
0x1800397e9  mov     word ptr [rbp+57h+var_60], 101h
0x1800397ef  mov     rsi, [rdi]
0x1800397f2  lea     rbx, [r12+28h]
0x1800397f7  mov     [rbp+57h+var_90], rbx
0x1800397fb  mov     rcx, rbx; SRWLock
0x1800397fe  call    cs:__imp_AcquireSRWLockExclusive
0x180039805  nop     dword ptr [rax+rax+00h]
0x18003980a  mov     [rbp+57h+var_58], rbx
0x18003980e  lea     r15, [r12+18h]
0x180039813  mov     rcx, [r15]
0x180039816  mov     rax, [rcx+8]
0x18003981a  xor     r12d, r12d
0x18003981d  xor     edx, edx
0x18003981f  mov     [rbp+57h+var_88], rdx
0x180039823  mov     rdx, [rbp+57h+var_50]
0x180039827  cmp     [rax+19h], r12b
0x18003982b  jnz     short loc_180039850
0x18003982d  mov     r13, rax
0x180039830  cmp     [rax+20h], rdx
0x180039834  jnb     short loc_18003983F
0x180039836  xor     r12d, r12d
0x180039839  mov     rax, [rax+10h]
0x18003983d  jmp     short loc_180039848
0x18003983f  mov     r12d, r14d
0x180039842  mov     rcx, rax
0x180039845  mov     rax, [rax]
0x180039848  cmp     byte ptr [rax+19h], 0
0x18003984c  jz      short loc_18003982D
0x18003984e  jmp     short loc_180039853
0x180039850  mov     r13, rax
0x180039853  cmp     byte ptr [rcx+19h], 0
0x180039857  jnz     short loc_180039864
0x180039859  cmp     rdx, [rcx+20h]
0x18003985d  jb      short loc_180039864
0x18003985f  xor     r14b, r14b
0x180039862  jmp     short loc_1800398D7
0x180039864  mov     rax, 555555555555555h
0x18003986e  cmp     [r15+8], rax
0x180039872  jz      loc_1800399CD
0x180039878  mov     rbx, [r15]
0x18003987b  mov     [rbp+57h+var_80], r15
0x18003987f  mov     [rbp+57h+var_78], 0
0x180039887  mov     ecx, 30h ; '0'; Size
0x18003988c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180039891  nop
0x180039892  mov     rcx, [rbp+57h+var_50]
0x180039896  mov     [rax+20h], rcx
0x18003989a  mov     rdx, [rdi]
0x18003989d  xor     ecx, ecx
0x18003989f  mov     [rdi], rcx
0x1800398a2  mov     [rax+28h], rdx
0x1800398a6  mov     [rax], rbx
0x1800398a9  mov     [rax+8], rbx
0x1800398ad  mov     [rax+10h], rbx
0x1800398b1  mov     [rax+18h], cx
0x1800398b5  mov     [rbp+57h+var_80], r13
0x1800398b9  mov     dword ptr [rbp+57h+var_78], r12d
0x1800398bd  mov     rcx, [rbp+57h+var_88]
0x1800398c1  mov     dword ptr [rbp+57h+var_78+4], ecx
0x1800398c4  mov     r8, rax
0x1800398c7  lea     rdx, [rbp+57h+var_80]
0x1800398cb  mov     rcx, r15
0x1800398ce  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UPropertyResponse@Service@Responses@Schema@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UPropertyResponse@Service@Responses@Schema@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UPropertyResponse@Service@Responses@Schema@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,Schema::Responses::Service::PropertyResponse>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<std::wstring const,Schema::Responses::Service::PropertyResponse>,void *> *>,std::_Tree_node<std::pair<std::wstring const,Schema::Responses::Service::PropertyResponse>,void *> * const)
0x1800398d3  mov     rbx, [rbp+57h+var_90]
0x1800398d7  mov     rcx, [rbp+5Fh]; this
0x1800398db  test    r14b, r14b
0x1800398de  jz      loc_18003997C
0x1800398e4  test    rbx, rbx
0x1800398e7  jz      short loc_1800398F8
0x1800398e9  mov     rcx, rbx; SRWLock
0x1800398ec  call    cs:__imp_ReleaseSRWLockExclusive
0x1800398f3  nop     dword ptr [rax+rax+00h]
0x1800398f8  xor     r8d, r8d; pftTimeout
0x1800398fb  mov     rdx, [rsi+20h]; h
0x1800398ff  mov     rcx, [rsi+28h]; pwa
0x180039903  call    cs:__imp_SetThreadpoolWait
0x18003990a  nop     dword ptr [rax+rax+00h]
0x18003990f  xor     r8d, r8d; pftTimeout
0x180039912  mov     rdx, [rsi+30h]; h
0x180039916  mov     rcx, [rsi+38h]; pwa
0x18003991a  call    cs:__imp_SetThreadpoolWait
0x180039921  nop     dword ptr [rax+rax+00h]
0x180039926  mov     byte ptr [rbp+57h+var_60+1], 0
0x18003992a  lea     rcx, [rbp+57h+var_70]
0x18003992e  call    wil__details__ScopeExitFnGuard__lambda_8e49fbe7b9768f69f4d98cda15c76ced_____operator__
0x180039933  nop
0x180039934  mov     rbx, [rdi]
0x180039937  test    rbx, rbx
0x18003993a  jz      short loc_180039951
0x18003993c  mov     rcx, rbx; this
0x18003993f  call    ??1NotificationContext@NotificationCallbacks@Client@ComputeService@@QEAA@XZ; ComputeService::Client::NotificationCallbacks::NotificationContext::~NotificationContext(void)
0x180039944  mov     edx, 68h ; 'h'; unsigned __int64
0x180039949  mov     rcx, rbx; void *
0x18003994c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180039951  mov     rax, rsi
0x180039954  mov     rcx, [rbp+57h+var_40]
0x180039958  xor     rcx, rsp; StackCookie
0x18003995b  call    __security_check_cookie
0x180039960  mov     rbx, [rsp+0C0h+arg_18]
0x180039968  add     rsp, 90h
0x18003996f  pop     r15
0x180039971  pop     r14
0x180039973  pop     r13
0x180039975  pop     r12
0x180039977  pop     rdi
0x180039978  pop     rsi
0x180039979  pop     rbp
0x18003997a  retn
0x18003997c  mov     r9d, 0C0370104h; char *
0x180039982  lea     r8, aOnecoreVmCompu_14; "onecore\\vm\\compute\\dll\\lib\\core\\n"...
0x180039989  mov     edx, 9Dh; void *
0x18003998e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180039994  lea     r8, aOnecoreVmCompu_14; "onecore\\vm\\compute\\dll\\lib\\core\\n"...
0x18003999b  mov     edx, 7Eh ; '~'; void *
0x1800399a0  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800399a6  lea     r8, aOnecoreVmCompu_14; "onecore\\vm\\compute\\dll\\lib\\core\\n"...
0x1800399ad  mov     edx, 82h; void *
0x1800399b2  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800399b8  lea     r8, aOnecoreVmCompu_14; "onecore\\vm\\compute\\dll\\lib\\core\\n"...
0x1800399bf  mov     edx, 87h; void *
0x1800399c4  mov     rcx, rax; this
0x1800399c7  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800399cd  call    ?_Throw_tree_length_error@std@@YAXXZ; std::_Throw_tree_length_error(void)
```
