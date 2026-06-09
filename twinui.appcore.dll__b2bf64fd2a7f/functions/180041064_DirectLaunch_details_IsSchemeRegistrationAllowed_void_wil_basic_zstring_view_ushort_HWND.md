# DirectLaunch::details::IsSchemeRegistrationAllowed(void *,wil::basic_zstring_view<ushort>,HWND__ *)

- ea: `0x180041064`
- end: `0x180041210`
- name: `?IsSchemeRegistrationAllowed@details@DirectLaunch@@YA_NPEAXV?$basic_zstring_view@G@wil@@PEAUHWND__@@@Z`
- size: `428`
- prototype: `__int64 __fastcall(HANDLE hProcess)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800414dc`
- `0x180042914`

## callees

- `0x18001d95c`
- `0x18001dc40`
- `0x18001dd64`
- `0x18002b1b0`
- `0x18002bc68`
- `0x18003e5f4`
- `0x180041064`
- `0x1800427c4`
- `0x180043e70`
- `0x1800444e8`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1800410f0`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1800410f0`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004116d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004116d`
- `api-ms-win-appmodel-runtime-l1-1-0!GetApplicationUserModelId` at `0x180041125`
- `api-ms-win-appmodel-runtime-l1-1-0!GetApplicationUserModelId` at `0x180041125`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x1800410df`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x1800410df`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall DirectLaunch::details::IsSchemeRegistrationAllowed(HANDLE hProcess, _OWORD *a2, HWND a3)
{
  DWORD ProcessId; // eax
  bool v8; // bl
  const struct std::filesystem::path *v9; // r8
  LPCWCH lpString2[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v11; // [rsp+40h] [rbp-C0h] BYREF
  DWORD dwProcessId; // [rsp+50h] [rbp-B0h] BYREF
  UINT32 applicationUserModelIdLength; // [rsp+54h] [rbp-ACh] BYREF
  _BYTE v14[40]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v15[48]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR applicationUserModelId[136]; // [rsp+B0h] [rbp-50h] BYREF

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_61155835>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_61155835>::GetImpl'::`2'::impl)
    && DirectLaunch::g_isSchemeRegistrationAllowedFn )
  {
    *(_OWORD *)lpString2 = *a2;
    return DirectLaunch::g_isSchemeRegistrationAllowedFn(hProcess, lpString2, a3);
  }
  else
  {
    dwProcessId = 0;
    if ( GetWindowThreadProcessId(a3, &dwProcessId) && (ProcessId = GetProcessId(hProcess), dwProcessId == ProcessId) )
    {
      memset_0(applicationUserModelId, 0, 0x104u);
      applicationUserModelIdLength = 130;
      if ( GetApplicationUserModelId(hProcess, &applicationUserModelIdLength, applicationUserModelId) )
      {
        DirectLaunch::details::TryGetProcessImagePath(v15, hProcess);
        v11 = *a2;
        DirectLaunch::details::TryGetStaticallyRegisteredSchemeHandlerPath((__int64)v14, &v11);
        v8 = v15[32]
          && v14[32]
          && std::filesystem::equivalent((std::filesystem *)v15, (const struct std::filesystem::path *)v14, v9);
        std::_Optional_destruct_base<std::filesystem::path,0>::~_Optional_destruct_base<std::filesystem::path,0>(v14);
        std::_Optional_destruct_base<std::filesystem::path,0>::~_Optional_destruct_base<std::filesystem::path,0>(v15);
      }
      else
      {
        lpString2[0] = 0;
        v11 = *a2;
        DirectLaunch::details::TryGetStaticallyRegisteredSchemeHandlerAumid(lpString2, &v11);
        if ( !lpString2[0] || (v8 = 1, CompareStringOrdinal(applicationUserModelId, -1, lpString2[0], -1, 1) != 2) )
          v8 = 0;
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(lpString2);
      }
      return v8;
    }
    else
    {
      return 0;
    }
  }
}

```

## disassembly

```asm
0x180041064  mov     [rsp-8+arg_18], rbx
0x180041069  push    rbp
0x18004106a  push    rsi
0x18004106b  push    rdi
0x18004106c  lea     rbp, [rsp-0D0h]
0x180041074  sub     rsp, 1D0h
0x18004107b  mov     rax, cs:__security_cookie
0x180041082  xor     rax, rsp
0x180041085  mov     [rbp+0E0h+var_20], rax
0x18004108c  mov     rsi, r8
0x18004108f  mov     rdi, rdx
0x180041092  mov     rbx, rcx
0x180041095  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_61155835@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_61155835@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_61155835> `wil::Feature<__WilFeatureTraits_Feature_61155835>::GetImpl(void)'::`2'::impl
0x18004109c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_61155835@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_61155835>::__private_IsEnabled(void)
0x1800410a1  test    al, al
0x1800410a3  jz      short loc_1800410CF
0x1800410a5  mov     rax, cs:?g_isSchemeRegistrationAllowedFn@DirectLaunch@@3P6A_NPEAXV?$basic_zstring_view@G@wil@@PEAUHWND__@@@_EEA
0x1800410ac  test    rax, rax
0x1800410af  jz      short loc_1800410CF
0x1800410b1  movaps  xmm0, xmmword ptr [rdi]
0x1800410b4  movdqa  xmmword ptr [rsp+1E0h+lpString2], xmm0
0x1800410ba  mov     r8, rsi
0x1800410bd  lea     rdx, [rsp+1E0h+lpString2]
0x1800410c2  mov     rcx, rbx
0x1800410c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800410ca  jmp     loc_1800411EE
0x1800410cf  mov     [rsp+1E0h+dwProcessId], 0
0x1800410d7  lea     rdx, [rsp+1E0h+dwProcessId]; lpdwProcessId
0x1800410dc  mov     rcx, rsi; hWnd
0x1800410df  call    cs:__imp_GetWindowThreadProcessId
0x1800410e5  test    eax, eax
0x1800410e7  jz      loc_1800411EC
0x1800410ed  mov     rcx, rbx; Process
0x1800410f0  call    cs:__imp_GetProcessId
0x1800410f6  cmp     [rsp+1E0h+dwProcessId], eax
0x1800410fa  jnz     loc_1800411EC
0x180041100  xor     edx, edx; Val
0x180041102  mov     r8d, 104h; Size
0x180041108  lea     rcx, [rbp+0E0h+applicationUserModelId]; void *
0x18004110c  call    memset_0
0x180041111  mov     [rsp+1E0h+applicationUserModelIdLength], 82h
0x180041119  lea     r8, [rbp+0E0h+applicationUserModelId]; applicationUserModelId
0x18004111d  lea     rdx, [rsp+1E0h+applicationUserModelIdLength]; applicationUserModelIdLength
0x180041122  mov     rcx, rbx; hProcess
0x180041125  call    cs:__imp_GetApplicationUserModelId
0x18004112b  test    eax, eax
0x18004112d  jnz     short loc_180041188
0x18004112f  mov     [rsp+1E0h+lpString2], 0
0x180041138  movaps  xmm0, xmmword ptr [rdi]
0x18004113b  movdqa  [rsp+1E0h+var_1A0], xmm0
0x180041141  lea     rdx, [rsp+1E0h+var_1A0]
0x180041146  lea     rcx, [rsp+1E0h+lpString2]
0x18004114b  call    ?TryGetStaticallyRegisteredSchemeHandlerAumid@details@DirectLaunch@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@V?$basic_zstring_view@G@4@@Z; DirectLaunch::details::TryGetStaticallyRegisteredSchemeHandlerAumid(wil::basic_zstring_view<ushort>)
0x180041150  mov     r8, [rsp+1E0h+lpString2]; lpString2
0x180041155  test    r8, r8
0x180041158  jz      short loc_180041178
0x18004115a  mov     ebx, 1
0x18004115f  mov     [rsp+1E0h+bIgnoreCase], ebx; bIgnoreCase
0x180041163  or      edx, 0FFFFFFFFh; cchCount1
0x180041166  mov     r9d, edx; cchCount2
0x180041169  lea     rcx, [rbp+0E0h+applicationUserModelId]; lpString1
0x18004116d  call    cs:__imp_CompareStringOrdinal
0x180041173  cmp     eax, 2
0x180041176  jz      short loc_18004117A
0x180041178  xor     bl, bl
0x18004117a  lea     rcx, [rsp+1E0h+lpString2]
0x18004117f  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180041184  mov     al, bl
0x180041186  jmp     short loc_1800411EE
0x180041188  mov     rdx, rbx
0x18004118b  lea     rcx, [rbp+0E0h+var_160]
0x18004118f  call    ?TryGetProcessImagePath@details@DirectLaunch@@YA?AV?$optional@Vpath@filesystem@std@@@std@@PEAX@Z; DirectLaunch::details::TryGetProcessImagePath(void *)
0x180041194  nop
0x180041195  movaps  xmm0, xmmword ptr [rdi]
0x180041198  movdqa  [rsp+1E0h+var_1A0], xmm0
0x18004119e  lea     rdx, [rsp+1E0h+var_1A0]
0x1800411a3  lea     rcx, [rsp+1E0h+var_188]
0x1800411a8  call    ?TryGetStaticallyRegisteredSchemeHandlerPath@details@DirectLaunch@@YA?AV?$optional@Vpath@filesystem@std@@@std@@V?$basic_zstring_view@G@wil@@@Z; DirectLaunch::details::TryGetStaticallyRegisteredSchemeHandlerPath(wil::basic_zstring_view<ushort>)
0x1800411ad  nop
0x1800411ae  cmp     [rbp+0E0h+var_140], 0
0x1800411b2  jz      short loc_1800411D4
0x1800411b4  cmp     [rsp+1E0h+var_168], 0
0x1800411b9  jz      short loc_1800411D4
0x1800411bb  lea     rdx, [rsp+1E0h+var_188]; struct std::filesystem::path *
0x1800411c0  lea     rcx, [rbp+0E0h+var_160]; this
0x1800411c4  call    ?equivalent@filesystem@std@@YA_NAEBVpath@12@0@Z; std::filesystem::equivalent(std::filesystem::path const &,std::filesystem::path const &)
0x1800411c9  test    al, al
0x1800411cb  jz      short loc_1800411D4
0x1800411cd  mov     ebx, 1
0x1800411d2  jmp     short loc_1800411D6
0x1800411d4  xor     bl, bl
0x1800411d6  lea     rcx, [rsp+1E0h+var_188]
0x1800411db  call    ??1?$_Optional_destruct_base@Vpath@filesystem@std@@$0A@@std@@QEAA@XZ; std::_Optional_destruct_base<std::filesystem::path,0>::~_Optional_destruct_base<std::filesystem::path,0>(void)
0x1800411e0  nop
0x1800411e1  lea     rcx, [rbp+0E0h+var_160]
0x1800411e5  call    ??1?$_Optional_destruct_base@Vpath@filesystem@std@@$0A@@std@@QEAA@XZ; std::_Optional_destruct_base<std::filesystem::path,0>::~_Optional_destruct_base<std::filesystem::path,0>(void)
0x1800411ea  jmp     short loc_180041184
0x1800411ec  xor     al, al
0x1800411ee  mov     rcx, [rbp+0E0h+var_20]
0x1800411f5  xor     rcx, rsp; StackCookie
0x1800411f8  call    __security_check_cookie
0x1800411fd  mov     rbx, [rsp+1E0h+arg_18]
0x180041205  add     rsp, 1D0h
0x18004120c  pop     rdi
0x18004120d  pop     rsi
0x18004120e  pop     rbp
0x18004120f  retn
```
