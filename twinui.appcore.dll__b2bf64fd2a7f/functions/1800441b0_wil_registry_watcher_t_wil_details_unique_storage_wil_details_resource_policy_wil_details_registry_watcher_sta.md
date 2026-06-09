# wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::create_common(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &&,bool,wistd::function<void (wil::RegistryChangeKind)> &&)

- ea: `0x1800441b0`
- end: `0x18004433d`
- name: `?create_common@?$registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@AEAAJ$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@_N$$QEAV?$function@$$A6AXW4RegistryChangeKind@wil@@@Z@wistd@@@Z`
- size: `397`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800440a4`

## callees

- `0x180016498`
- `0x18001ca50`
- `0x18001cc38`
- `0x18001e340`
- `0x180026858`
- `0x180026878`
- `0x18002b1e0`
- `0x18003e2ec`
- `0x18003fda8`
- `0x1800400bc`
- `0x1800441b0`
- `0x18004517c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180044327`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180044327`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1800442a7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1800442a7`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x180044275`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x180044275`

## string_xrefs

- `0x18004420e`: `OneCore\Internal\Sdk\Inc\wil\opensource\wil\registry.h`
- `0x180044243`: `OneCore\Internal\Sdk\Inc\wil\opensource\wil\registry.h`
- `0x180044287`: `OneCore\Internal\Sdk\Inc\wil\opensource\wil\registry.h`
- `0x1800442e9`: `OneCore\Internal\Sdk\Inc\wil\opensource\wil\registry.h`

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
  __int64 v10; // rbx
  int event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // eax
  unsigned int v13; // edi
  unsigned int v14; // edx
  unsigned int v15; // eax
  unsigned int LastError; // eax
  PTP_WAIT ThreadpoolWait; // rdi
  const char *v18; // r9
  struct _TP_WAIT *v19; // rsi
  BOOL fAsynchronous; // [rsp+20h] [rbp-38h]
  BOOL fAsynchronousa; // [rsp+20h] [rbp-38h]
  _QWORD v22[5]; // [rsp+30h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v8 = operator new(0xA0u, (const struct std::nothrow_t *)&std::nothrow);
  v22[0] = v8;
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
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCBB,
      (unsigned int)"OneCore\\Internal\\Sdk\\Inc\\wil\\opensource\\wil\\registry.h",
      (const char *)0x8007000ELL,
      fAsynchronous);
    return 2147942414LL;
  }
  event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(v10 + 128);
  v13 = event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCBC,
      (unsigned int)"OneCore\\Internal\\Sdk\\Inc\\wil\\opensource\\wil\\registry.h",
      (const char *)(unsigned int)event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z,
      fAsynchronous);
LABEL_15:
    wil::details::registry_watcher_state::`scalar deleting destructor'((wil::details::registry_watcher_state *)v10, v14);
    return v13;
  }
  v15 = RegNotifyChangeKeyValue(
          *(HKEY *)(v10 + 120),
          *(unsigned __int8 *)(v10 + 144),
          0x10000005u,
          *(HANDLE *)(v10 + 128),
          1);
  if ( v15 )
  {
    LastError = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0xCC2,
                  (unsigned int)"OneCore\\Internal\\Sdk\\Inc\\wil\\opensource\\wil\\registry.h",
                  (const char *)v15,
                  fAsynchronousa);
LABEL_14:
    v13 = LastError;
    goto LABEL_15;
  }
  ThreadpoolWait = CreateThreadpoolWait(
                     wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::callback,
                     (PVOID)v10,
                     0);
  v19 = *(struct _TP_WAIT **)(v10 + 136);
  if ( v19 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)v22);
    wil::details::DestroyThreadPoolWait<0>::Destroy(v19);
    wil::last_error_context::~last_error_context((wil::last_error_context *)v22);
  }
  *(_QWORD *)(v10 + 136) = ThreadpoolWait;
  if ( !ThreadpoolWait )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xCC5,
                  (unsigned int)"OneCore\\Internal\\Sdk\\Inc\\wil\\opensource\\wil\\registry.h",
                  v18);
    goto LABEL_14;
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
0x1800441b0  mov     [rsp+arg_10], rbx
0x1800441b5  push    rsi
0x1800441b6  push    rdi
0x1800441b7  push    r14
0x1800441b9  sub     rsp, 40h
0x1800441bd  mov     rsi, r9
0x1800441c0  mov     bl, r8b
0x1800441c3  mov     rdi, rdx
0x1800441c6  mov     r14, rcx
0x1800441c9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800441d0  mov     ecx, 0A0h; unsigned __int64
0x1800441d5  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800441da  mov     [rsp+58h+var_28], rax
0x1800441df  test    rax, rax
0x1800441e2  jz      short loc_1800441FA
0x1800441e4  mov     r9, rsi
0x1800441e7  mov     r8b, bl
0x1800441ea  mov     rdx, rdi
0x1800441ed  mov     rcx, rax
0x1800441f0  call    ??0registry_watcher_state@details@wil@@QEAA@$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@_N$$QEAV?$function@$$A6AXW4RegistryChangeKind@wil@@@Z@wistd@@@Z; wil::details::registry_watcher_state::registry_watcher_state(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &&,bool,wistd::function<void (wil::RegistryChangeKind)> &&)
0x1800441f5  mov     rbx, rax
0x1800441f8  jmp     short loc_1800441FC
0x1800441fa  xor     ebx, ebx
0x1800441fc  test    rbx, rbx
0x1800441ff  jnz     short loc_180044226
0x180044201  mov     rcx, [rsp+58h]; this
0x180044206  mov     ebx, 8007000Eh
0x18004420b  mov     r9d, ebx; char *
0x18004420e  lea     r8, aOnecoreInterna_12; "OneCore\\Internal\\Sdk\\Inc\\wil\\opens"...
0x180044215  mov     edx, 0CBBh; void *
0x18004421a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004421f  mov     eax, ebx
0x180044221  jmp     loc_18004432F
0x180044226  lea     rsi, [rbx+80h]
0x18004422d  mov     rcx, rsi
0x180044230  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180044235  mov     edi, eax
0x180044237  test    eax, eax
0x180044239  jns     short loc_180044259
0x18004423b  mov     rcx, [rsp+58h]; this
0x180044240  mov     r9d, eax; char *
0x180044243  lea     r8, aOnecoreInterna_12; "OneCore\\Internal\\Sdk\\Inc\\wil\\opens"...
0x18004424a  mov     edx, 0CBCh; void *
0x18004424f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180044254  jmp     loc_1800442FC
0x180044259  movzx   edx, byte ptr [rbx+90h]; bWatchSubtree
0x180044260  mov     [rsp+58h+fAsynchronous], 1; unsigned int
0x180044268  mov     r9, [rsi]; hEvent
0x18004426b  mov     r8d, 10000005h; dwNotifyFilter
0x180044271  mov     rcx, [rbx+78h]; hKey
0x180044275  call    cs:__imp_RegNotifyChangeKeyValue
0x18004427b  test    eax, eax
0x18004427d  jz      short loc_18004429A
0x18004427f  mov     rcx, [rsp+58h]; this
0x180044284  mov     r9d, eax; char *
0x180044287  lea     r8, aOnecoreInterna_12; "OneCore\\Internal\\Sdk\\Inc\\wil\\opens"...
0x18004428e  mov     edx, 0CC2h; void *
0x180044293  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180044298  jmp     short loc_1800442FA
0x18004429a  xor     r8d, r8d; pcbe
0x18004429d  mov     rdx, rbx; pv
0x1800442a0  lea     rcx, ?callback@?$registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x1800442a7  call    cs:__imp_CreateThreadpoolWait
0x1800442ad  mov     rdi, rax
0x1800442b0  mov     rsi, [rbx+88h]
0x1800442b7  test    rsi, rsi
0x1800442ba  jz      short loc_1800442D8
0x1800442bc  lea     rcx, [rsp+58h+var_28]; this
0x1800442c1  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800442c6  mov     rcx, rsi; pwa
0x1800442c9  call    ?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAXPEAU_TP_WAIT@@@Z; wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *)
0x1800442ce  lea     rcx, [rsp+58h+var_28]; this
0x1800442d3  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800442d8  mov     [rbx+88h], rdi
0x1800442df  test    rdi, rdi
0x1800442e2  jnz     short loc_180044308
0x1800442e4  mov     rcx, [rsp+58h]; this
0x1800442e9  lea     r8, aOnecoreInterna_12; "OneCore\\Internal\\Sdk\\Inc\\wil\\opens"...
0x1800442f0  mov     edx, 0CC5h; void *
0x1800442f5  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800442fa  mov     edi, eax
0x1800442fc  mov     rcx, rbx; this
0x1800442ff  call    ??_Gregistry_watcher_state@details@wil@@QEAAPEAXI@Z; wil::details::registry_watcher_state::`scalar deleting destructor'(uint)
0x180044304  mov     eax, edi
0x180044306  jmp     short loc_18004432F
0x180044308  mov     rdx, rbx
0x18004430b  mov     rcx, r14
0x18004430e  call    ?reset@?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUregistry_watcher_state@23@@Z; wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>::reset(wil::details::registry_watcher_state *)
0x180044313  mov     rcx, [r14]
0x180044316  xor     r8d, r8d; pftTimeout
0x180044319  mov     rdx, [rcx+80h]; h
0x180044320  mov     rcx, [rcx+88h]; pwa
0x180044327  call    cs:__imp_SetThreadpoolWait
0x18004432d  xor     eax, eax
0x18004432f  mov     rbx, [rsp+58h+arg_10]
0x180044334  add     rsp, 40h
0x180044338  pop     r14
0x18004433a  pop     rdi
0x18004433b  pop     rsi
0x18004433c  retn
```
