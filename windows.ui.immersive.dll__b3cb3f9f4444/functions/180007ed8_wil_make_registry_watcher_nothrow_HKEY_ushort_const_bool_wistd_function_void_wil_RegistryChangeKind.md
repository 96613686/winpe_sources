# wil::make_registry_watcher_nothrow(HKEY__ *,ushort const *,bool,wistd::function<void (wil::RegistryChangeKind)> &&)

- ea: `0x180007ed8`
- end: `0x180008186`
- name: `?make_registry_watcher_nothrow@wil@@YA?AV?$unique_any_t@V?$registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@1@PEAUHKEY__@@PEBG_N$$QEAV?$function@$$A6AXW4RegistryChangeKind@wil@@@Z@wistd@@@Z`
- size: `686`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x180007590`

## callees

- `0x180007ed8`
- `0x1800083a4`
- `0x180008954`
- `0x180029660`
- `0x180036c2c`
- `0x180037140`
- `0x18003729c`
- `0x18003ee74`
- `0x18003ee98`
- `0x1800419a0`
- `0x180059b4c`
- `0x18006f7f8`
- `0x1800ed010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180007fef`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180007fef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000800a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000800a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000812b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000812b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1800080aa`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1800080aa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008162`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008162`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180007f26`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180007f26`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x180008072`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x180008072`

## string_xrefs

- `0x180008031`: `onecore\internal\sdk\inc\wil\opensource\wil\registry.h`
- `0x180008087`: `onecore\internal\sdk\inc\wil\opensource\wil\registry.h`
- `0x1800080f8`: `onecore\internal\sdk\inc\wil\opensource\wil\registry.h`
- `0x18000813e`: `onecore\internal\sdk\inc\wil\opensource\wil\registry.h`

## pseudocode

```c
wil::details::registry_watcher_state **__fastcall wil::make_registry_watcher_nothrow(
        wil::details::registry_watcher_state **a1,
        __int64 a2,
        const WCHAR *a3,
        __int64 a4,
        __int64 a5)
{
  LSTATUS v6; // eax
  bool v7; // sf
  _QWORD *v8; // rax
  _QWORD *v9; // rbx
  __int64 v10; // rdi
  wil::details *v11; // rcx
  HANDLE Event; // rbp
  HANDLE *v13; // rdi
  int LastErrorFailHr; // eax
  unsigned int v15; // edx
  unsigned int v16; // eax
  PTP_WAIT ThreadpoolWait; // rax
  const char *v18; // r9
  struct _TP_WAIT *v19; // r14
  PTP_WAIT v20; // rbp
  BOOL fAsynchronous; // [rsp+20h] [rbp-58h]
  BOOL fAsynchronousa; // [rsp+20h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  char v25; // [rsp+80h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+88h] [rbp+10h] BYREF

  *a1 = 0;
  hKey = 0;
  v6 = RegCreateKeyExW(HKEY_CURRENT_USER, a3, 0, 0, 0, 0x10u, 0, &hKey, 0);
  v7 = v6 < 0;
  if ( v6 > 0 )
    v7 = 1;
  if ( !v7 )
  {
    v8 = operator new(0xA0u, (const struct std::nothrow_t *)&std::nothrow);
    v9 = v8;
    if ( v8 )
    {
      v10 = a5;
      if ( *(_QWORD *)(a5 + 112) )
      {
        v8[14] = v8 + 1;
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v10 + 112) + 16LL))(*(_QWORD *)(v10 + 112));
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v10 + 112) + 24LL))(*(_QWORD *)(v10 + 112));
        *(_QWORD *)(v10 + 112) = 0;
      }
      else
      {
        v8[14] = 0;
      }
      v9[15] = hKey;
      hKey = 0;
      v9[16] = 0;
      v9[17] = 0;
      *((_BYTE *)v9 + 144) = 0;
      *((_DWORD *)v9 + 37) = 1;
      v9[19] = 0;
      Event = CreateEventExW(0, 0, 0, 0x1F0003u);
      if ( Event )
      {
        v13 = (HANDLE *)(v9 + 16);
        GetLastError();
        _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
          v9 + 16,
          Event);
      }
      else
      {
        LastErrorFailHr = wil::details::GetLastErrorFailHr(v11);
        if ( LastErrorFailHr < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xCBC,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\registry.h",
            (const char *)(unsigned int)LastErrorFailHr,
            fAsynchronous);
LABEL_12:
          wil::details::registry_watcher_state::`scalar deleting destructor'(
            (wil::details::registry_watcher_state *)v9,
            v15);
          goto LABEL_24;
        }
        v13 = (HANDLE *)(v9 + 16);
      }
      v16 = RegNotifyChangeKeyValue((HKEY)v9[15], *((unsigned __int8 *)v9 + 144), 0x10000005u, *v13, 1);
      if ( v16 )
      {
        wil::details::in1diag3::Return_Win32(
          retaddr,
          (void *)0xCC2,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\registry.h",
          (const char *)v16,
          fAsynchronousa);
        goto LABEL_12;
      }
      ThreadpoolWait = CreateThreadpoolWait(
                         wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_returncode_policy>::callback,
                         v9,
                         0);
      v19 = (struct _TP_WAIT *)v9[17];
      v20 = ThreadpoolWait;
      if ( v19 )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&v25);
        wil::details::DestroyThreadPoolWait<0>::Destroy(v19);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&v25);
      }
      v9[17] = v20;
      if ( !v20 )
      {
        wil::details::in1diag3::Return_GetLastError(
          retaddr,
          (void *)0xCC5,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\registry.h",
          v18);
        goto LABEL_12;
      }
      if ( *a1 )
        wil::details::close_invoke_helper<1,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wil::details::registry_watcher_state *>::close_reset(*a1);
      *a1 = (wil::details::registry_watcher_state *)v9;
      SetThreadpoolWait((PTP_WAIT)v9[17], *v13, 0);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xCBB,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\registry.h",
        (const char *)0x8007000ELL,
        fAsynchronous);
    }
  }
LABEL_24:
  if ( hKey )
    RegCloseKey(hKey);
  return a1;
}

```

## disassembly

```asm
0x180007ed8  mov     rax, rsp
0x180007edb  mov     [rax+18h], rbx
0x180007edf  mov     [rax+10h], rdx
0x180007ee3  push    rbp
0x180007ee4  push    rsi
0x180007ee5  push    rdi
0x180007ee6  push    r14
0x180007ee8  push    r15
0x180007eea  sub     rsp, 50h
0x180007eee  xor     r15d, r15d
0x180007ef1  mov     rsi, rcx
0x180007ef4  mov     [rax-38h], r15
0x180007ef8  mov     rdx, r8; lpSubKey
0x180007efb  mov     [rcx], r15
0x180007efe  xor     r9d, r9d; lpClass
0x180007f01  lea     rcx, [rax+10h]
0x180007f05  mov     [rax+10h], r15
0x180007f09  mov     [rax-40h], rcx
0x180007f0d  xor     r8d, r8d; Reserved
0x180007f10  mov     [rax-48h], r15
0x180007f14  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180007f1b  mov     dword ptr [rax-50h], 10h
0x180007f22  mov     [rax-58h], r15d
0x180007f26  call    cs:__imp_RegCreateKeyExW
0x180007f2d  nop     dword ptr [rax+rax+00h]
0x180007f32  test    eax, eax
0x180007f34  jle     short loc_180007F40
0x180007f36  movzx   eax, ax
0x180007f39  or      eax, 80070000h
0x180007f3e  test    eax, eax
0x180007f40  js      loc_180008155
0x180007f46  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180007f4d  mov     ecx, 0A0h; unsigned __int64
0x180007f52  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180007f57  mov     rbx, rax
0x180007f5a  test    rax, rax
0x180007f5d  jz      loc_180008139
0x180007f63  mov     rdi, [rsp+78h+arg_20]
0x180007f6b  cmp     [rdi+70h], r15
0x180007f6f  jnz     short loc_180007F77
0x180007f71  mov     [rax+70h], r15
0x180007f75  jmp     short loc_180007FA3
0x180007f77  lea     rdx, [rax+8]
0x180007f7b  mov     [rax+70h], rdx
0x180007f7f  mov     rcx, [rdi+70h]
0x180007f83  mov     rax, [rcx]
0x180007f86  mov     rax, [rax+10h]
0x180007f8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f8f  mov     rcx, [rdi+70h]
0x180007f93  mov     rax, [rcx]
0x180007f96  mov     rax, [rax+18h]
0x180007f9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f9f  mov     [rdi+70h], r15
0x180007fa3  mov     rax, [rsp+78h+hKey]
0x180007fab  mov     r14d, 1
0x180007fb1  mov     [rbx+78h], rax
0x180007fb5  mov     r9d, 1F0003h; dwDesiredAccess
0x180007fbb  mov     [rsp+78h+hKey], r15
0x180007fc3  xor     eax, eax
0x180007fc5  mov     [rbx+80h], r15
0x180007fcc  xor     r8d, r8d; dwFlags
0x180007fcf  mov     [rbx+88h], r15
0x180007fd6  xor     edx, edx; lpName
0x180007fd8  mov     [rbx+90h], r15b
0x180007fdf  xor     ecx, ecx; lpEventAttributes
0x180007fe1  mov     [rbx+94h], r14d
0x180007fe8  mov     [rbx+98h], rax
0x180007fef  call    cs:__imp_CreateEventExW
0x180007ff6  nop     dword ptr [rax+rax+00h]
0x180007ffb  mov     rbp, rax
0x180007ffe  test    rax, rax
0x180008001  jz      short loc_180008023
0x180008003  lea     rdi, [rbx+80h]
0x18000800a  call    cs:__imp_GetLastError
0x180008011  nop     dword ptr [rax+rax+00h]
0x180008016  mov     rdx, rbp
0x180008019  mov     rcx, rdi
0x18000801c  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180008021  jmp     short loc_180008059
0x180008023  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180008028  test    eax, eax
0x18000802a  jns     short loc_180008052
0x18000802c  mov     rcx, [rsp+78h]; this
0x180008031  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180008038  mov     r9d, eax; char *
0x18000803b  mov     edx, 0CBCh; void *
0x180008040  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008045  mov     rcx, rbx; this
0x180008048  call    ??_Gregistry_watcher_state@details@wil@@QEAAPEAXI@Z; wil::details::registry_watcher_state::`scalar deleting destructor'(uint)
0x18000804d  jmp     loc_180008155
0x180008052  lea     rdi, [rbx+80h]
0x180008059  movzx   edx, byte ptr [rbx+90h]; bWatchSubtree
0x180008060  mov     r8d, 10000005h; dwNotifyFilter
0x180008066  mov     r9, [rdi]; hEvent
0x180008069  mov     rcx, [rbx+78h]; hKey
0x18000806d  mov     [rsp+78h+fAsynchronous], r14d; unsigned int
0x180008072  call    cs:__imp_RegNotifyChangeKeyValue
0x180008079  nop     dword ptr [rax+rax+00h]
0x18000807e  test    eax, eax
0x180008080  jz      short loc_18000809D
0x180008082  mov     rcx, [rsp+78h]; this
0x180008087  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000808e  mov     r9d, eax; char *
0x180008091  mov     edx, 0CC2h; void *
0x180008096  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18000809b  jmp     short loc_180008045
0x18000809d  xor     r8d, r8d; pcbe
0x1800080a0  lea     rcx, ?callback@?$registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x1800080a7  mov     rdx, rbx; pv
0x1800080aa  call    cs:__imp_CreateThreadpoolWait
0x1800080b1  nop     dword ptr [rax+rax+00h]
0x1800080b6  mov     r14, [rbx+88h]
0x1800080bd  mov     rbp, rax
0x1800080c0  test    r14, r14
0x1800080c3  jz      short loc_1800080E7
0x1800080c5  lea     rcx, [rsp+78h+arg_0]; this
0x1800080cd  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800080d2  mov     rcx, r14; pwa
0x1800080d5  call    ?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAXPEAU_TP_WAIT@@@Z; wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *)
0x1800080da  lea     rcx, [rsp+78h+arg_0]; this
0x1800080e2  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800080e7  mov     [rbx+88h], rbp
0x1800080ee  test    rbp, rbp
0x1800080f1  jnz     short loc_18000810E
0x1800080f3  mov     rcx, [rsp+78h]; this
0x1800080f8  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800080ff  mov     edx, 0CC5h; void *
0x180008104  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180008109  jmp     loc_180008045
0x18000810e  mov     rcx, [rsi]; this
0x180008111  test    rcx, rcx
0x180008114  jz      short loc_18000811B
0x180008116  call    ?close_reset@?$close_invoke_helper@$00P6AXPEAUregistry_watcher_state@details@wil@@@Z$1?delete_registry_watcher_state@23@YAX0@ZPEAU123@@details@wil@@SAXPEAUregistry_watcher_state@23@@Z; wil::details::close_invoke_helper<1,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wil::details::registry_watcher_state *>::close_reset(wil::details::registry_watcher_state *)
0x18000811b  mov     [rsi], rbx
0x18000811e  xor     r8d, r8d; pftTimeout
0x180008121  mov     rdx, [rdi]; h
0x180008124  mov     rcx, [rbx+88h]; pwa
0x18000812b  call    cs:__imp_SetThreadpoolWait
0x180008132  nop     dword ptr [rax+rax+00h]
0x180008137  jmp     short loc_180008155
0x180008139  mov     rcx, [rsp+78h]; this
0x18000813e  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180008145  mov     r9d, 8007000Eh; char *
0x18000814b  mov     edx, 0CBBh; void *
0x180008150  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008155  mov     rcx, [rsp+78h+hKey]; hKey
0x18000815d  test    rcx, rcx
0x180008160  jz      short loc_18000816E
0x180008162  call    cs:__imp_RegCloseKey
0x180008169  nop     dword ptr [rax+rax+00h]
0x18000816e  mov     rbx, [rsp+78h+arg_10]
0x180008176  mov     rax, rsi
0x180008179  add     rsp, 50h
0x18000817d  pop     r15
0x18000817f  pop     r14
0x180008181  pop     rdi
0x180008182  pop     rsi
0x180008183  pop     rbp
0x180008184  retn
```
