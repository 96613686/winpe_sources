# wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::create_common(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &&,bool,wistd::function<void (wil::RegistryChangeKind)> &&)

- ea: `0x1400a6138`
- end: `0x1400a62f8`
- name: `?create_common@?$registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@AEAAJ$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@_N$$QEAV?$function@$$A6AXW4RegistryChangeKind@wil@@@Z@wistd@@@Z`
- size: `448`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400a48d8`

## callees

- `0x140046df8`
- `0x1400a597c`
- `0x1400a6138`
- `0x1400a6300`
- `0x1400a632c`
- `0x1400a6578`
- `0x1400a65a0`
- `0x140133358`
- `0x140218618`
- `0x14022274c`
- `0x140228d6c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1400a61bb`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1400a61bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400a61d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400a61d6`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x1400a623b`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x1400a623b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1400a6273`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1400a6273`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1400a62db`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1400a62db`

## string_xrefs

- `0x1400a6196`: `onecore\internal\sdk\inc\wil\opensource\wil\registry.h`
- `0x1400a6202`: `onecore\internal\sdk\inc\wil\opensource\wil\registry.h`
- `0x1400a6253`: `onecore\internal\sdk\inc\wil\opensource\wil\registry.h`
- `0x1400a629c`: `onecore\internal\sdk\inc\wil\opensource\wil\registry.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::create_common(
        __int64 a1,
        __int64 a2,
        char a3,
        __int64 a4)
{
  void *v8; // rax
  __int64 v9; // r8
  __int64 v10; // rdi
  unsigned int v11; // ebx
  wil::details *v13; // rcx
  HANDLE Event; // rsi
  HANDLE *v15; // rbx
  int LastErrorFailHr; // eax
  unsigned int v17; // edx
  unsigned int v18; // eax
  int LastError; // eax
  PTP_WAIT ThreadpoolWait; // rax
  const char *v21; // r9
  BOOL fAsynchronous; // [rsp+20h] [rbp-38h]
  BOOL fAsynchronousa; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v8 = operator new(0xA0u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v8 )
  {
    LOBYTE(v9) = a3;
    v10 = wil::details::registry_watcher_state::registry_watcher_state(v8, a2, v9, a4);
  }
  else
  {
    v10 = 0;
  }
  if ( !v10 )
  {
    v11 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCBB,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\registry.h",
      (const char *)0x8007000ELL,
      fAsynchronous);
    return v11;
  }
  Event = CreateEventExW(0, 0, 0, 0x1F0003u);
  if ( Event )
  {
    v15 = (HANDLE *)(v10 + 128);
    GetLastError();
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      v10 + 128,
      Event);
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v13);
    v11 = LastErrorFailHr;
    if ( LastErrorFailHr < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xCBC,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\registry.h",
        (const char *)(unsigned int)LastErrorFailHr,
        fAsynchronous);
LABEL_17:
      wil::details::registry_watcher_state::`scalar deleting destructor'(
        (wil::details::registry_watcher_state *)v10,
        v17);
      return v11;
    }
    v15 = (HANDLE *)(v10 + 128);
  }
  v18 = RegNotifyChangeKeyValue(*(HKEY *)(v10 + 120), *(unsigned __int8 *)(v10 + 144), 0x10000005u, *v15, 1);
  if ( v18 )
  {
    LastError = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0xCC2,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\registry.h",
                  (const char *)v18,
                  fAsynchronousa);
LABEL_16:
    v11 = LastError;
    goto LABEL_17;
  }
  ThreadpoolWait = CreateThreadpoolWait(
                     wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::callback,
                     (PVOID)v10,
                     0);
  wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&public: static void wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(
    v10 + 136,
    ThreadpoolWait);
  if ( !*(_QWORD *)(v10 + 136) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xCC5,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\registry.h",
                  v21);
    goto LABEL_16;
  }
  wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>::reset(
    a1,
    v10);
  SetThreadpoolWait(*(PTP_WAIT *)(*(_QWORD *)a1 + 136LL), *(HANDLE *)(*(_QWORD *)a1 + 128LL), 0);
  return 0;
}

```

## disassembly

```asm
0x1400a6138  mov     [rsp+arg_10], rbx
0x1400a613d  push    rsi
0x1400a613e  push    rdi
0x1400a613f  push    r14
0x1400a6141  sub     rsp, 40h
0x1400a6145  mov     rsi, r9
0x1400a6148  mov     bl, r8b
0x1400a614b  mov     rdi, rdx
0x1400a614e  mov     r14, rcx
0x1400a6151  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400a6158  mov     ecx, 0A0h; unsigned __int64
0x1400a615d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1400a6162  mov     [rsp+58h+var_28], rax
0x1400a6167  test    rax, rax
0x1400a616a  jz      short loc_1400A6182
0x1400a616c  mov     r9, rsi
0x1400a616f  mov     r8b, bl
0x1400a6172  mov     rdx, rdi
0x1400a6175  mov     rcx, rax
0x1400a6178  call    ??0registry_watcher_state@details@wil@@QEAA@$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@_N$$QEAV?$function@$$A6AXW4RegistryChangeKind@wil@@@Z@wistd@@@Z; wil::details::registry_watcher_state::registry_watcher_state(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &&,bool,wistd::function<void (wil::RegistryChangeKind)> &&)
0x1400a617d  mov     rdi, rax
0x1400a6180  jmp     short loc_1400A6184
0x1400a6182  xor     edi, edi
0x1400a6184  test    rdi, rdi
0x1400a6187  jnz     short loc_1400A61AE
0x1400a6189  mov     rcx, [rsp+58h]; this
0x1400a618e  mov     ebx, 8007000Eh
0x1400a6193  mov     r9d, ebx; char *
0x1400a6196  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1400a619d  mov     edx, 0CBBh; void *
0x1400a61a2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400a61a7  mov     eax, ebx
0x1400a61a9  jmp     loc_1400A62E9
0x1400a61ae  mov     r9d, 1F0003h; dwDesiredAccess
0x1400a61b4  xor     r8d, r8d; dwFlags
0x1400a61b7  xor     edx, edx; lpName
0x1400a61b9  xor     ecx, ecx; lpEventAttributes
0x1400a61bb  call    cs:__imp_CreateEventExW
0x1400a61c2  nop     dword ptr [rax+rax+00h]
0x1400a61c7  mov     rsi, rax
0x1400a61ca  test    rax, rax
0x1400a61cd  jz      short loc_1400A61EF
0x1400a61cf  lea     rbx, [rdi+80h]
0x1400a61d6  call    cs:__imp_GetLastError
0x1400a61dd  nop     dword ptr [rax+rax+00h]
0x1400a61e2  mov     rdx, rsi
0x1400a61e5  mov     rcx, rbx
0x1400a61e8  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1400a61ed  jmp     short loc_1400A621F
0x1400a61ef  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1400a61f4  mov     ebx, eax
0x1400a61f6  test    eax, eax
0x1400a61f8  jns     short loc_1400A6218
0x1400a61fa  mov     rcx, [rsp+58h]; this
0x1400a61ff  mov     r9d, eax; char *
0x1400a6202  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1400a6209  mov     edx, 0CBCh; void *
0x1400a620e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400a6213  jmp     loc_1400A62AF
0x1400a6218  lea     rbx, [rdi+80h]
0x1400a621f  movzx   edx, byte ptr [rdi+90h]; bWatchSubtree
0x1400a6226  mov     [rsp+58h+fAsynchronous], 1; unsigned int
0x1400a622e  mov     r9, [rbx]; hEvent
0x1400a6231  mov     r8d, 10000005h; dwNotifyFilter
0x1400a6237  mov     rcx, [rdi+78h]; hKey
0x1400a623b  call    cs:__imp_RegNotifyChangeKeyValue
0x1400a6242  nop     dword ptr [rax+rax+00h]
0x1400a6247  test    eax, eax
0x1400a6249  jz      short loc_1400A6266
0x1400a624b  mov     rcx, [rsp+58h]; this
0x1400a6250  mov     r9d, eax; char *
0x1400a6253  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1400a625a  mov     edx, 0CC2h; void *
0x1400a625f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1400a6264  jmp     short loc_1400A62AD
0x1400a6266  xor     r8d, r8d; pcbe
0x1400a6269  mov     rdx, rdi; pv
0x1400a626c  lea     rcx, ?callback@?$registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x1400a6273  call    cs:__imp_CreateThreadpoolWait
0x1400a627a  nop     dword ptr [rax+rax+00h]
0x1400a627f  lea     rbx, [rdi+88h]
0x1400a6286  mov     rdx, rax
0x1400a6289  mov     rcx, rbx
0x1400a628c  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_WAIT@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_WAIT@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(_TP_WAIT *)
0x1400a6291  cmp     qword ptr [rbx], 0
0x1400a6295  jnz     short loc_1400A62BC
0x1400a6297  mov     rcx, [rsp+58h]; this
0x1400a629c  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1400a62a3  mov     edx, 0CC5h; void *
0x1400a62a8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1400a62ad  mov     ebx, eax
0x1400a62af  mov     rcx, rdi; this
0x1400a62b2  call    ??_Gregistry_watcher_state@details@wil@@QEAAPEAXI@Z; wil::details::registry_watcher_state::`scalar deleting destructor'(uint)
0x1400a62b7  jmp     loc_1400A61A7
0x1400a62bc  mov     rdx, rdi
0x1400a62bf  mov     rcx, r14
0x1400a62c2  call    ?reset@?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUregistry_watcher_state@23@@Z; wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>::reset(wil::details::registry_watcher_state *)
0x1400a62c7  mov     rcx, [r14]
0x1400a62ca  xor     r8d, r8d; pftTimeout
0x1400a62cd  mov     rdx, [rcx+80h]; h
0x1400a62d4  mov     rcx, [rcx+88h]; pwa
0x1400a62db  call    cs:__imp_SetThreadpoolWait
0x1400a62e2  nop     dword ptr [rax+rax+00h]
0x1400a62e7  xor     eax, eax
0x1400a62e9  mov     rbx, [rsp+58h+arg_10]
0x1400a62ee  add     rsp, 40h
0x1400a62f2  pop     r14
0x1400a62f4  pop     rdi
0x1400a62f5  pop     rsi
0x1400a62f6  retn
```
