# wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_returncode_policy>::create_common(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &&,bool,wistd::function<void (wil::RegistryChangeKind)> &&)

- ea: `0x180010990`
- end: `0x180010b9d`
- name: `?create_common@?$registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@AEAAJ$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@_N$$QEAV?$function@$$A6AXW4RegistryChangeKind@wil@@@Z@wistd@@@Z`
- size: `525`
- prototype: ``
- caller_count: `3`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009db0`
- `0x18001041c`
- `0x18001075c`

## callees

- `0x18000f2f8`
- `0x180010990`
- `0x180010ba4`
- `0x180010c44`
- `0x18004f234`
- `0x18004f258`
- `0x1800e2988`
- `0x1800e34bc`
- `0x1800e3660`
- `0x18027741c`
- `0x18034aaf8`
- `0x1804a2010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180010b36`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180010b36`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180010ae5`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180010ae5`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x180010a7c`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x180010a7c`

## string_xrefs

- `0x180010a8e`: `onecore\internal\sdk\inc\wil\opensource\wil\registry.h`
- `0x180010ac3`: `onecore\internal\sdk\inc\wil\opensource\wil\registry.h`
- `0x180010b0b`: `onecore\internal\sdk\inc\wil\opensource\wil\registry.h`
- `0x180010b4b`: `onecore\internal\sdk\inc\wil\opensource\wil\registry.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_returncode_policy>::create_common(
        wil::details::registry_watcher_state **a1,
        _QWORD *a2,
        char a3,
        __int64 a4)
{
  _QWORD *v8; // rax
  _QWORD *v9; // rbx
  HANDLE *v10; // rsi
  int event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEB_WPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // eax
  unsigned int v12; // edi
  unsigned int v13; // eax
  unsigned int LastError; // eax
  unsigned int v15; // edx
  PTP_WAIT ThreadpoolWait; // rdi
  const char *v18; // r9
  struct _TP_WAIT *v19; // rbp
  BOOL fAsynchronous; // [rsp+20h] [rbp-48h]
  BOOL fAsynchronousa; // [rsp+20h] [rbp-48h]
  _QWORD v22[7]; // [rsp+30h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v8 = operator new(0xA0u, (const struct std::nothrow_t *)std::nothrow);
  v9 = v8;
  v22[0] = v8;
  if ( v8 )
  {
    if ( *(_QWORD *)(a4 + 112) )
    {
      v8[14] = v8 + 1;
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a4 + 112) + 16LL))(*(_QWORD *)(a4 + 112));
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a4 + 112) + 24LL))(*(_QWORD *)(a4 + 112));
      *(_QWORD *)(a4 + 112) = 0;
    }
    else
    {
      v8[14] = 0;
    }
    v9[15] = *a2;
    *a2 = 0;
    v9[16] = 0;
    v9[17] = 0;
    *((_BYTE *)v9 + 144) = a3;
    *((_DWORD *)v9 + 37) = 1;
    v9[19] = 0;
  }
  else
  {
    v9 = 0;
  }
  if ( v9 )
  {
    v10 = (HANDLE *)(v9 + 16);
    event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEB_WPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEB_WPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(v9 + 16);
    v12 = event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEB_WPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
    if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEB_WPEAU_SECURITY_ATTRIBUTES__PEA_N_Z < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xCBC,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\registry.h",
        (const char *)(unsigned int)event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEB_WPEAU_SECURITY_ATTRIBUTES__PEA_N_Z,
        fAsynchronous);
      goto LABEL_10;
    }
    v13 = RegNotifyChangeKeyValue((HKEY)v9[15], *((unsigned __int8 *)v9 + 144), 0x10000005u, *v10, 1);
    if ( v13 )
    {
      LastError = wil::details::in1diag3::Return_Win32(
                    retaddr,
                    (void *)0xCC2,
                    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\registry.h",
                    (const char *)v13,
                    fAsynchronousa);
LABEL_9:
      v12 = LastError;
LABEL_10:
      wil::details::registry_watcher_state::`scalar deleting destructor'(
        (wil::details::registry_watcher_state *)v9,
        v15);
      return v12;
    }
    ThreadpoolWait = CreateThreadpoolWait(
                       wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_returncode_policy>::callback,
                       v9,
                       0);
    v19 = (struct _TP_WAIT *)v9[17];
    if ( v19 )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)v22);
      wil::details::DestroyThreadPoolWait<0>::Destroy(v19);
      wil::last_error_context::~last_error_context((wil::last_error_context *)v22);
    }
    v9[17] = ThreadpoolWait;
    if ( !ThreadpoolWait )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0xCC5,
                    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\registry.h",
                    v18);
      goto LABEL_9;
    }
    if ( *a1 )
      wil::details::close_invoke_helper<1,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wil::details::registry_watcher_state *>::close_reset(*a1);
    *a1 = (wil::details::registry_watcher_state *)v9;
    SetThreadpoolWait((PTP_WAIT)v9[17], *v10, 0);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCBB,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\registry.h",
      (const char *)0x8007000ELL,
      fAsynchronous);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x180010990  push    rbx
0x180010992  push    rbp
0x180010993  push    rsi
0x180010994  push    rdi
0x180010995  push    r14
0x180010997  sub     rsp, 40h
0x18001099b  mov     rdi, r9
0x18001099e  mov     bpl, r8b
0x1800109a1  mov     rsi, rdx
0x1800109a4  mov     r14, rcx
0x1800109a7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800109ae  mov     ecx, 0A0h; unsigned __int64
0x1800109b3  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800109b8  mov     rbx, rax
0x1800109bb  mov     [rsp+68h+var_38], rax
0x1800109c0  test    rax, rax
0x1800109c3  jz      loc_180010B6E
0x1800109c9  cmp     qword ptr [rdi+70h], 0
0x1800109ce  jz      loc_180010B61
0x1800109d4  lea     rdx, [rax+8]
0x1800109d8  mov     [rax+70h], rdx
0x1800109dc  mov     rcx, [rdi+70h]
0x1800109e0  mov     rax, [rcx]
0x1800109e3  mov     rax, [rax+10h]
0x1800109e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800109ec  mov     rcx, [rdi+70h]
0x1800109f0  mov     rax, [rcx]
0x1800109f3  mov     rax, [rax+18h]
0x1800109f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800109fc  mov     qword ptr [rdi+70h], 0
0x180010a04  mov     rax, [rsi]
0x180010a07  mov     [rbx+78h], rax
0x180010a0b  mov     qword ptr [rsi], 0
0x180010a12  mov     qword ptr [rbx+80h], 0
0x180010a1d  mov     qword ptr [rbx+88h], 0
0x180010a28  mov     [rbx+90h], bpl
0x180010a2f  mov     dword ptr [rbx+94h], 1
0x180010a39  xor     eax, eax
0x180010a3b  mov     [rbx+98h], rax
0x180010a42  test    rbx, rbx
0x180010a45  jz      short loc_180010AB6
0x180010a47  lea     rsi, [rbx+80h]
0x180010a4e  mov     rcx, rsi
0x180010a51  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEB_WPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180010a56  mov     edi, eax
0x180010a58  test    eax, eax
0x180010a5a  js      loc_180010B43
0x180010a60  movzx   edx, byte ptr [rbx+90h]; bWatchSubtree
0x180010a67  mov     [rsp+68h+fAsynchronous], 1; unsigned int
0x180010a6f  mov     r9, [rsi]; hEvent
0x180010a72  mov     r8d, 10000005h; dwNotifyFilter
0x180010a78  mov     rcx, [rbx+78h]; hKey
0x180010a7c  call    cs:__imp_RegNotifyChangeKeyValue
0x180010a82  test    eax, eax
0x180010a84  jz      short loc_180010AD8
0x180010a86  mov     rcx, [rsp+68h]; this
0x180010a8b  mov     r9d, eax; char *
0x180010a8e  lea     r8, aOnecoreInterna_9; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180010a95  mov     edx, 0CC2h; void *
0x180010a9a  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180010a9f  mov     edi, eax
0x180010aa1  mov     rcx, rbx; this
0x180010aa4  call    ??_Gregistry_watcher_state@details@wil@@QEAAPEAXI@Z; wil::details::registry_watcher_state::`scalar deleting destructor'(uint)
0x180010aa9  mov     eax, edi
0x180010aab  add     rsp, 40h
0x180010aaf  pop     r14
0x180010ab1  pop     rdi
0x180010ab2  pop     rsi
0x180010ab3  pop     rbp
0x180010ab4  pop     rbx
0x180010ab5  retn
0x180010ab6  mov     rcx, [rsp+68h]; this
0x180010abb  mov     ebx, 8007000Eh
0x180010ac0  mov     r9d, ebx; char *
0x180010ac3  lea     r8, aOnecoreInterna_9; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180010aca  mov     edx, 0CBBh; void *
0x180010acf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010ad4  mov     eax, ebx
0x180010ad6  jmp     short loc_180010AAB
0x180010ad8  xor     r8d, r8d; pcbe
0x180010adb  mov     rdx, rbx; pv
0x180010ade  lea     rcx, ?callback@?$registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x180010ae5  call    cs:__imp_CreateThreadpoolWait
0x180010aeb  mov     rdi, rax
0x180010aee  mov     rbp, [rbx+88h]
0x180010af5  test    rbp, rbp
0x180010af8  jnz     short loc_180010B75
0x180010afa  mov     [rbx+88h], rdi
0x180010b01  test    rdi, rdi
0x180010b04  jnz     short loc_180010B1E
0x180010b06  mov     rcx, [rsp+68h]; this
0x180010b0b  lea     r8, aOnecoreInterna_9; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180010b12  mov     edx, 0CC5h; void *
0x180010b17  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180010b1c  jmp     short loc_180010A9F
0x180010b1e  mov     rcx, [r14]; this
0x180010b21  test    rcx, rcx
0x180010b24  jnz     short loc_180010B96
0x180010b26  mov     [r14], rbx
0x180010b29  xor     r8d, r8d; pftTimeout
0x180010b2c  mov     rdx, [rsi]; h
0x180010b2f  mov     rcx, [rbx+88h]; pwa
0x180010b36  call    cs:__imp_SetThreadpoolWait
0x180010b3c  xor     eax, eax
0x180010b3e  jmp     loc_180010AAB
0x180010b43  mov     rcx, [rsp+68h]; this
0x180010b48  mov     r9d, eax; char *
0x180010b4b  lea     r8, aOnecoreInterna_9; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180010b52  mov     edx, 0CBCh; void *
0x180010b57  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010b5c  jmp     loc_180010AA1
0x180010b61  mov     qword ptr [rax+70h], 0
0x180010b69  jmp     loc_180010A04
0x180010b6e  xor     ebx, ebx
0x180010b70  jmp     loc_180010A42
0x180010b75  lea     rcx, [rsp+68h+var_38]; this
0x180010b7a  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180010b7f  mov     rcx, rbp; pwa
0x180010b82  call    ?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAXPEAU_TP_WAIT@@@Z; wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *)
0x180010b87  lea     rcx, [rsp+68h+var_38]; this
0x180010b8c  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180010b91  jmp     loc_180010AFA
0x180010b96  call    ?close_reset@?$close_invoke_helper@$00P6AXPEAUregistry_watcher_state@details@wil@@@Z$1?delete_registry_watcher_state@23@YAX0@ZPEAU123@@details@wil@@SAXPEAUregistry_watcher_state@23@@Z; wil::details::close_invoke_helper<1,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wil::details::registry_watcher_state *>::close_reset(wil::details::registry_watcher_state *)
0x180010b9b  jmp     short loc_180010B26
```
