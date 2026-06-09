# Windows::Internal::CloudNotifications::CommonNotificationsInterface::IsCachedChannelStale(winrt::hstring,winrt::hstring)

- ea: `0x18005cf28`
- end: `0x18005d288`
- name: `?IsCachedChannelStale@CommonNotificationsInterface@CloudNotifications@Internal@Windows@@AEAA_NUhstring@winrt@@0@Z`
- size: `864`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180059840`

## callees

- `0x180002810`
- `0x1800034f7`
- `0x1800035ab`
- `0x18003fbf8`
- `0x18005cf28`
- `0x18007d010`

## import_xrefs

- `msvcp_win!_Xtime_get_ticks` at `0x18005d077`
- `msvcp_win!_Xtime_get_ticks` at `0x18005d077`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18005d275`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18005d281`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18005d275`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18005d281`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005d06a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005d1ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005d06a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005d1ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005d032`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005d17e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005d032`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005d17e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18005d1d5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18005d1d5`

## string_xrefs

- `0x18005d0f8`: `WnsChannelUri`
- `0x18005cfa1`: `LastUpdated`
- `0x18005cfe3`: `onecoreuap\shell\clouddirect\cloudnotifications\src\commonnotificationsinterface.cpp`
- `0x18005d040`: `onecoreuap\shell\clouddirect\cloudnotifications\src\commonnotificationsinterface.cpp`
- `0x18005d135`: `onecoreuap\shell\clouddirect\cloudnotifications\src\commonnotificationsinterface.cpp`
- `0x18005d18c`: `onecoreuap\shell\clouddirect\cloudnotifications\src\commonnotificationsinterface.cpp`
- `0x18005d13c`: `No cached Channel URI value found in the registry.`
- `0x18005d00e`: `Error while retrieving the Channel URI Last Updated value from the registry: 0x%08X`
- `0x18005cfea`: `No Channel URI Last Updated value found in the registry.`
- `0x18005d15a`: `Error while retrieving the cached Channel URI from the registry: 0x%08X`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char __fastcall Windows::Internal::CloudNotifications::CommonNotificationsInterface::IsCachedChannelStale(
        __int64 a1,
        volatile signed __int32 **a2,
        volatile signed __int32 **a3)
{
  __int64 v6; // rcx
  const WCHAR *v7; // rbx
  const WCHAR *v8; // r8
  __int64 v9; // rdi
  char v10; // si
  __int64 v11; // rdi
  void (__fastcall *v12)(__int64, _QWORD, PCWSTR, const char *, int); // rbx
  PCWSTR StringRawBuffer; // rax
  __int64 ticks; // rax
  const WCHAR *v15; // r8
  __int64 v16; // rdi
  __int64 v17; // rdi
  void (__fastcall *v18)(__int64, _QWORD, PCWSTR, const char *, int); // rbx
  PCWSTR v19; // rax
  volatile signed __int32 *v20; // rbx
  int v21; // eax
  HANDLE ProcessHeap; // rax
  volatile signed __int32 *v23; // rbx
  int v24; // r14d
  HANDLE v25; // rax
  HSTRING string; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v28[3]; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR String2[1024]; // [rsp+60h] [rbp-A0h] BYREF

  v28[1] = a2;
  v28[2] = a3;
  v28[0] = 0;
  v6 = *(_QWORD *)(a1 + 104);
  v7 = &Name;
  if ( *a2 )
    v8 = (const WCHAR *)*((_QWORD *)*a2 + 2);
  else
    v8 = &Name;
  v9 = (*(unsigned int (__fastcall **)(__int64, __int64, const WCHAR *, const wchar_t *, _QWORD *))(*(_QWORD *)v6 + 32LL))(
         v6,
         -2147483647,
         v8,
         L"LastUpdated",
         v28);
  v10 = 1;
  if ( (*(unsigned __int8 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(a1 + 104) + 8LL))(*(_QWORD *)(a1 + 104), v9) )
  {
    (*(void (__fastcall **)(_QWORD, __int64, const wchar_t *, const char *, int))(**(_QWORD **)(a1 + 88) + 16LL))(
      *(_QWORD *)(a1 + 88),
      1,
      L"No Channel URI Last Updated value found in the registry.",
      "onecoreuap\\shell\\clouddirect\\cloudnotifications\\src\\commonnotificationsinterface.cpp",
      654);
    v28[0] = 0;
  }
  else if ( (int)v9 < 0 )
  {
    wil::str_printf<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(
      &string,
      L"Error while retrieving the Channel URI Last Updated value from the registry: 0x%08X",
      (unsigned int)v9);
    v11 = *(_QWORD *)(a1 + 88);
    v12 = *(void (__fastcall **)(__int64, _QWORD, PCWSTR, const char *, int))(*(_QWORD *)v11 + 16LL);
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v12(
      v11,
      0,
      StringRawBuffer,
      "onecoreuap\\shell\\clouddirect\\cloudnotifications\\src\\commonnotificationsinterface.cpp",
      668);
    v28[0] = 0;
    if ( string )
      WindowsDeleteString(string);
    v7 = &Name;
  }
  ticks = _Xtime_get_ticks();
  if ( v28[0]
    && (unsigned __int64)(ticks / 10000000 - v28[0]) <= *(_QWORD *)(a1 + 120)
    && v28[0] <= (unsigned __int64)(ticks / 10000000) )
  {
    if ( *a2 )
      v15 = (const WCHAR *)*((_QWORD *)*a2 + 2);
    else
      v15 = &Name;
    v16 = (*(unsigned int (__fastcall **)(_QWORD, __int64, const WCHAR *, const wchar_t *, WCHAR *, int))(**(_QWORD **)(a1 + 104) + 40LL))(
            *(_QWORD *)(a1 + 104),
            -2147483647,
            v15,
            L"WnsChannelUri",
            String2,
            1024);
    if ( (*(unsigned __int8 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(a1 + 104) + 8LL))(
           *(_QWORD *)(a1 + 104),
           v16) )
    {
      (*(void (__fastcall **)(_QWORD, __int64, const wchar_t *, const char *, int))(**(_QWORD **)(a1 + 88) + 16LL))(
        *(_QWORD *)(a1 + 88),
        1,
        L"No cached Channel URI value found in the registry.",
        "onecoreuap\\shell\\clouddirect\\cloudnotifications\\src\\commonnotificationsinterface.cpp",
        707);
    }
    else if ( (int)v16 >= 0 )
    {
      if ( *a3 )
        v7 = (const WCHAR *)*((_QWORD *)*a3 + 2);
      if ( CompareStringOrdinal(v7, -1, String2, -1, 1) == 2 )
        v10 = 0;
    }
    else
    {
      wil::str_printf<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(
        &string,
        L"Error while retrieving the cached Channel URI from the registry: 0x%08X",
        (unsigned int)v16);
      v17 = *(_QWORD *)(a1 + 88);
      v18 = *(void (__fastcall **)(__int64, _QWORD, PCWSTR, const char *, int))(*(_QWORD *)v17 + 16LL);
      v19 = WindowsGetStringRawBuffer(string, 0);
      v18(v17, 0, v19, "onecoreuap\\shell\\clouddirect\\cloudnotifications\\src\\commonnotificationsinterface.cpp", 719);
      if ( string )
        WindowsDeleteString(string);
    }
  }
  v20 = *a2;
  if ( *a2 )
  {
    v21 = _InterlockedDecrement(v20 + 6);
    if ( v21 )
    {
      if ( v21 < 0 )
        abort();
    }
    else
    {
      ProcessHeap = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v20);
    }
    *a2 = 0;
  }
  v23 = *a3;
  if ( *a3 )
  {
    v24 = _InterlockedDecrement(v23 + 6);
    if ( v24 )
    {
      if ( v24 < 0 )
        abort();
    }
    else
    {
      v25 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v25, 0, (LPVOID)v23);
    }
    *a3 = 0;
  }
  return v10;
}

```

## disassembly

```asm
0x18005cf28  mov     [rsp-8+arg_18], rbx
0x18005cf2d  push    rbp
0x18005cf2e  push    rsi
0x18005cf2f  push    rdi
0x18005cf30  push    r12
0x18005cf32  push    r13
0x18005cf34  push    r14
0x18005cf36  push    r15
0x18005cf38  lea     rbp, [rsp-770h]
0x18005cf40  sub     rsp, 870h
0x18005cf47  mov     rax, cs:__security_cookie
0x18005cf4e  xor     rax, rsp
0x18005cf51  mov     [rbp+7A0h+var_40], rax
0x18005cf58  mov     r13, r8
0x18005cf5b  mov     r12, rdx
0x18005cf5e  mov     r15, rcx
0x18005cf61  mov     [rsp+8A0h+var_850], rdx
0x18005cf66  mov     [rsp+8A0h+var_848], r8
0x18005cf6b  mov     [rsp+8A0h+var_858], 0
0x18005cf74  mov     rcx, [rcx+68h]
0x18005cf78  mov     rax, [rcx]
0x18005cf7b  mov     r10, [rax+20h]
0x18005cf7f  mov     rax, [rdx]
0x18005cf82  lea     rbx, Name
0x18005cf89  test    rax, rax
0x18005cf8c  jz      short loc_18005CF94
0x18005cf8e  mov     r8, [rax+10h]
0x18005cf92  jmp     short loc_18005CF97
0x18005cf94  mov     r8, rbx
0x18005cf97  lea     rax, [rsp+8A0h+var_858]
0x18005cf9c  mov     qword ptr [rsp+8A0h+bIgnoreCase], rax
0x18005cfa1  lea     r9, aLastupdated; "LastUpdated"
0x18005cfa8  mov     rdx, 0FFFFFFFF80000001h
0x18005cfaf  mov     rax, r10
0x18005cfb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cfb7  mov     edi, eax
0x18005cfb9  mov     rcx, [r15+68h]
0x18005cfbd  mov     rdx, [rcx]
0x18005cfc0  mov     rax, [rdx+8]
0x18005cfc4  mov     edx, edi
0x18005cfc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cfcb  mov     esi, 1
0x18005cfd0  test    al, al
0x18005cfd2  jz      short loc_18005D007
0x18005cfd4  mov     rcx, [r15+58h]
0x18005cfd8  mov     rax, [rcx]
0x18005cfdb  mov     [rsp+8A0h+bIgnoreCase], 28Eh
0x18005cfe3  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\clouddirect\\cloudno"...
0x18005cfea  lea     r8, aNoChannelUriLa; "No Channel URI Last Updated value found"...
0x18005cff1  mov     edx, esi
0x18005cff3  mov     rax, [rax+10h]
0x18005cff7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cffc  mov     [rsp+8A0h+var_858], 0
0x18005d005  jmp     short loc_18005D077
0x18005d007  test    edi, edi
0x18005d009  jns     short loc_18005D077
0x18005d00b  mov     r8d, edi
0x18005d00e  lea     rdx, aErrorWhileRetr_1; "Error while retrieving the Channel URI "...
0x18005d015  lea     rcx, [rsp+8A0h+string]
0x18005d01a  call    ??$str_printf@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(ushort const *,...)
0x18005d01f  nop
0x18005d020  mov     rdi, [r15+58h]
0x18005d024  mov     rax, [rdi]
0x18005d027  mov     rbx, [rax+10h]
0x18005d02b  xor     edx, edx; length
0x18005d02d  mov     rcx, [rsp+8A0h+string]; string
0x18005d032  call    cs:__imp_WindowsGetStringRawBuffer
0x18005d038  mov     [rsp+8A0h+bIgnoreCase], 29Ch
0x18005d040  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\clouddirect\\cloudno"...
0x18005d047  mov     r8, rax
0x18005d04a  xor     edx, edx
0x18005d04c  mov     rcx, rdi
0x18005d04f  mov     rax, rbx
0x18005d052  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d057  mov     [rsp+8A0h+var_858], 0
0x18005d060  mov     rcx, [rsp+8A0h+string]; string
0x18005d065  test    rcx, rcx
0x18005d068  jz      short loc_18005D070
0x18005d06a  call    cs:__imp_WindowsDeleteString
0x18005d070  lea     rbx, Name
0x18005d077  call    cs:__imp__Xtime_get_ticks
0x18005d07d  mov     r8, rax
0x18005d080  or      r14d, 0FFFFFFFFh
0x18005d084  mov     rcx, [rsp+8A0h+var_858]
0x18005d089  test    rcx, rcx
0x18005d08c  jz      loc_18005D1E3
0x18005d092  mov     rax, 0D6BF94D5E57A42BDh
0x18005d09c  imul    r8
0x18005d09f  add     rdx, r8
0x18005d0a2  sar     rdx, 17h
0x18005d0a6  mov     rax, rdx
0x18005d0a9  shr     rax, 3Fh
0x18005d0ad  add     rdx, rax
0x18005d0b0  mov     rax, rdx
0x18005d0b3  sub     rax, rcx
0x18005d0b6  cmp     rax, [r15+78h]
0x18005d0ba  ja      loc_18005D1E3
0x18005d0c0  cmp     rcx, rdx
0x18005d0c3  ja      loc_18005D1E3
0x18005d0c9  mov     rcx, [r15+68h]
0x18005d0cd  mov     rax, [rcx]
0x18005d0d0  mov     r10, [rax+28h]
0x18005d0d4  mov     rax, [r12]
0x18005d0d8  test    rax, rax
0x18005d0db  jz      short loc_18005D0E3
0x18005d0dd  mov     r8, [rax+10h]
0x18005d0e1  jmp     short loc_18005D0E6
0x18005d0e3  mov     r8, rbx
0x18005d0e6  mov     [rsp+8A0h+var_878], 400h
0x18005d0ee  lea     rax, [rsp+8A0h+String2]
0x18005d0f3  mov     qword ptr [rsp+8A0h+bIgnoreCase], rax
0x18005d0f8  lea     r9, aWnschanneluri; "WnsChannelUri"
0x18005d0ff  mov     rdx, 0FFFFFFFF80000001h
0x18005d106  mov     rax, r10
0x18005d109  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d10e  mov     edi, eax
0x18005d110  mov     rcx, [r15+68h]
0x18005d114  mov     rdx, [rcx]
0x18005d117  mov     rax, [rdx+8]
0x18005d11b  mov     edx, edi
0x18005d11d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d122  test    al, al
0x18005d124  jz      short loc_18005D153
0x18005d126  mov     rcx, [r15+58h]
0x18005d12a  mov     rax, [rcx]
0x18005d12d  mov     [rsp+8A0h+bIgnoreCase], 2C3h
0x18005d135  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\clouddirect\\cloudno"...
0x18005d13c  lea     r8, aNoCachedChanne; "No cached Channel URI value found in th"...
0x18005d143  mov     edx, esi
0x18005d145  mov     rax, [rax+10h]
0x18005d149  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d14e  jmp     loc_18005D1E3
0x18005d153  test    edi, edi
0x18005d155  jns     short loc_18005D1B6
0x18005d157  mov     r8d, edi
0x18005d15a  lea     rdx, aErrorWhileRetr; "Error while retrieving the cached Chann"...
0x18005d161  lea     rcx, [rsp+8A0h+string]
0x18005d166  call    ??$str_printf@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(ushort const *,...)
0x18005d16b  nop
0x18005d16c  mov     rdi, [r15+58h]
0x18005d170  mov     rax, [rdi]
0x18005d173  mov     rbx, [rax+10h]
0x18005d177  xor     edx, edx; length
0x18005d179  mov     rcx, [rsp+8A0h+string]; string
0x18005d17e  call    cs:__imp_WindowsGetStringRawBuffer
0x18005d184  mov     [rsp+8A0h+bIgnoreCase], 2CFh
0x18005d18c  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\clouddirect\\cloudno"...
0x18005d193  mov     r8, rax
0x18005d196  xor     edx, edx
0x18005d198  mov     rcx, rdi
0x18005d19b  mov     rax, rbx
0x18005d19e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d1a3  nop
0x18005d1a4  mov     rcx, [rsp+8A0h+string]; string
0x18005d1a9  test    rcx, rcx
0x18005d1ac  jz      short loc_18005D1E3
0x18005d1ae  call    cs:__imp_WindowsDeleteString
0x18005d1b4  jmp     short loc_18005D1E3
0x18005d1b6  mov     rax, [r13+0]
0x18005d1ba  test    rax, rax
0x18005d1bd  jz      short loc_18005D1C3
0x18005d1bf  mov     rbx, [rax+10h]
0x18005d1c3  mov     [rsp+8A0h+bIgnoreCase], esi; bIgnoreCase
0x18005d1c7  mov     r9d, r14d; cchCount2
0x18005d1ca  lea     r8, [rsp+8A0h+String2]; lpString2
0x18005d1cf  mov     edx, r14d; cchCount1
0x18005d1d2  mov     rcx, rbx; lpString1
0x18005d1d5  call    cs:__imp_CompareStringOrdinal
0x18005d1db  cmp     eax, 2
0x18005d1de  jnz     short loc_18005D1E3
0x18005d1e0  xor     sil, sil
0x18005d1e3  mov     rbx, [r12]
0x18005d1e7  test    rbx, rbx
0x18005d1ea  jz      short loc_18005D214
0x18005d1ec  mov     eax, r14d
0x18005d1ef  lock xadd [rbx+18h], eax
0x18005d1f4  sub     eax, 1
0x18005d1f7  jnz     short loc_18005D271
0x18005d1f9  nop
0x18005d1fa  call    WINRT_IMPL_GetProcessHeap
0x18005d1ff  mov     rcx, rax; hHeap
0x18005d202  mov     r8, rbx; lpMem
0x18005d205  xor     edx, edx; dwFlags
0x18005d207  call    WINRT_IMPL_HeapFree
0x18005d20c  mov     qword ptr [r12], 0
0x18005d214  mov     rbx, [r13+0]
0x18005d218  test    rbx, rbx
0x18005d21b  jz      short loc_18005D244
0x18005d21d  lock xadd [rbx+18h], r14d
0x18005d223  sub     r14d, 1
0x18005d227  jnz     short loc_18005D27C
0x18005d229  nop
0x18005d22a  call    WINRT_IMPL_GetProcessHeap
0x18005d22f  mov     rcx, rax; hHeap
0x18005d232  mov     r8, rbx; lpMem
0x18005d235  xor     edx, edx; dwFlags
0x18005d237  call    WINRT_IMPL_HeapFree
0x18005d23c  mov     qword ptr [r13+0], 0
0x18005d244  mov     al, sil
0x18005d247  mov     rcx, [rbp+7A0h+var_40]
0x18005d24e  xor     rcx, rsp; StackCookie
0x18005d251  call    __security_check_cookie
0x18005d256  mov     rbx, [rsp+8A0h+arg_18]
0x18005d25e  add     rsp, 870h
0x18005d265  pop     r15
0x18005d267  pop     r14
0x18005d269  pop     r13
0x18005d26b  pop     r12
0x18005d26d  pop     rdi
0x18005d26e  pop     rsi
0x18005d26f  pop     rbp
0x18005d270  retn
0x18005d271  test    eax, eax
0x18005d273  jns     short loc_18005D20C
0x18005d275  call    cs:__imp_abort
0x18005d27c  test    r14d, r14d
0x18005d27f  jns     short loc_18005D23C
0x18005d281  call    cs:__imp_abort
```
