# DesktopAppXExecuteCommandBase::TryDDEExecFirstTime(IShellItem *,ushort const *,Windows::Internal::Storage::IDDEExecHelper *)

- ea: `0x1800492e8`
- end: `0x180049659`
- name: `?TryDDEExecFirstTime@DesktopAppXExecuteCommandBase@@IEAA?AW4DDEContinuationState@Storage@Internal@Windows@@PEAUIShellItem@@PEBGPEAUIDDEExecHelper@345@@Z`
- size: `881`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004b230`

## callees

- `0x1800049bc`
- `0x18000f194`
- `0x18001eb04`
- `0x18001eb40`
- `0x1800491d0`
- `0x1800492e8`
- `0x18004966c`
- `0x18004a510`
- `0x18004a844`
- `0x18004aab4`
- `0x18004acdc`
- `0x180055370`
- `0x18008a030`
- `0x180111010`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x18004943f`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x18004943f`
- `api-ms-win-core-processenvironment-l1-1-0!GetCurrentDirectoryW` at `0x18004933c`
- `api-ms-win-core-processenvironment-l1-1-0!GetCurrentDirectoryW` at `0x1800493fe`
- `api-ms-win-core-processenvironment-l1-1-0!GetCurrentDirectoryW` at `0x18004933c`
- `api-ms-win-core-processenvironment-l1-1-0!GetCurrentDirectoryW` at `0x1800493fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180049360`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800494bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180049360`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800494bc`

## string_xrefs

- `0x180049499`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\desktopappxexecutecommand.cpp`
- `0x18004955c`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\desktopappxexecutecommand.cpp`
- `0x18004959c`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\desktopappxexecutecommand.cpp`
- `0x1800495dd`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\desktopappxexecutecommand.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall DesktopAppXExecuteCommandBase::TryDDEExecFirstTime(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 (__fastcall ***a4)(_QWORD, GUID *, __int64 *))
{
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // rax
  WCHAR *v10; // r14
  const WCHAR *v11; // rcx
  __int64 (__fastcall *v12)(_QWORD, GUID *, __int64 *); // rbx
  int v13; // eax
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, _QWORD *, _QWORD, _QWORD); // rbx
  _QWORD *v16; // rdx
  int v17; // eax
  int v18; // eax
  __int64 v19; // rdx
  int v20; // eax
  const char *v21; // r9
  unsigned int v22; // ebx
  int v24; // [rsp+20h] [rbp-368h]
  _BYTE v25[4]; // [rsp+60h] [rbp-328h] BYREF
  UINT32 length; // [rsp+64h] [rbp-324h] BYREF
  int v27; // [rsp+68h] [rbp-320h] BYREF
  __int64 v28; // [rsp+70h] [rbp-318h] BYREF
  LPCWSTR v29[2]; // [rsp+78h] [rbp-310h] BYREF
  LPCWSTR pszPath[4]; // [rsp+88h] [rbp-300h] BYREF
  _QWORD v31[3]; // [rsp+A8h] [rbp-2E0h] BYREF
  _QWORD v32[4]; // [rsp+C8h] [rbp-2C0h] BYREF
  _BYTE v33[32]; // [rsp+E8h] [rbp-2A0h] BYREF
  _BYTE v34[40]; // [rsp+108h] [rbp-280h] BYREF
  WCHAR Buffer[264]; // [rsp+130h] [rbp-258h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+388h] [rbp+0h]

  LaunchExecuteCommandBase::GetSite(a1, v29);
  if ( !*(_QWORD *)(a1 + 144) )
    GetCurrentDirectoryW(0x104u, Buffer);
  std::wstring::wstring(v31);
  length = 0;
  WindowsGetStringRawBuffer(*(HSTRING *)(a1 + 208), &length);
  if ( length )
  {
    std::wstring::wstring(v33);
    v8 = std::wstring::find(v33, L"!") + 1;
    v9 = std::wstring::substr(v33, v34, v8);
    std::wstring::operator=(v31, v9);
    std::wstring::_Tidy_deallocate(v34);
    std::wstring::_Tidy_deallocate(v33);
  }
  if ( *(_QWORD *)(a1 + 144) )
  {
    v10 = (WCHAR *)(a1 + 128);
    if ( *(_QWORD *)(a1 + 152) > 7u )
      v10 = *(WCHAR **)v10;
  }
  else
  {
    GetCurrentDirectoryW(0x104u, Buffer);
    v10 = Buffer;
  }
  v29[1] = 0;
  DesktopAppXExecuteCommandBase::GetFileItemStringFromShellItem(v7, pszPath, a2);
  v11 = (const WCHAR *)pszPath;
  if ( pszPath[3] > (LPCWSTR)7 )
    v11 = pszPath[0];
  PathFindExtensionW(v11);
  std::wstring::wstring(v32);
  v27 = 2;
  v28 = 0;
  v12 = **a4;
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v28);
  try
  {
    v13 = v12(a4, &GUID_2d6d3a33_aaa2_467b_9147_a146963e8066, &v28);
    if ( v13 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xC5,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\desktopappxexecutecommand.cpp",
        (const char *)(unsigned int)v13,
        v24);
    v14 = v28;
    v15 = *(__int64 (__fastcall **)(__int64, _QWORD *, _QWORD, _QWORD))(*(_QWORD *)v28 + 24LL);
    WindowsGetStringRawBuffer(*(HSTRING *)(a1 + 96), 0);
    v16 = v32;
    if ( v32[3] > 7u )
      v16 = (_QWORD *)v32[0];
    v17 = v15(v14, v16, *(_QWORD *)(a1 + 176), 0);
    if ( v17 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xD1,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\desktopappxexecutecommand.cpp",
        (const char *)(unsigned int)v17,
        (int)v10);
    v25[0] = 0;
    v18 = (*a4)[7](a4, *(GUID **)(a1 + 216), (__int64 *)v25);
    if ( v18 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xD4,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\desktopappxexecutecommand.cpp",
        (const char *)(unsigned int)v18,
        (int)v10);
    if ( v25[0] )
    {
      LOBYTE(v19) = 1;
      v20 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64, _QWORD, int *))(*a4)[6])(
              a4,
              v19,
              *(unsigned int *)(a1 + 124),
              &v27);
      if ( v20 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xD8,
          (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\desktopappxexecutecommand.cpp",
          (const char *)(unsigned int)v20,
          (int)v10);
    }
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v28);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0xDB,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\desktopappxexecutecommand.cpp",
      v21);
  }
  v22 = v27;
  std::wstring::_Tidy_deallocate(v32);
  std::wstring::_Tidy_deallocate(pszPath);
  std::wstring::_Tidy_deallocate(v31);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v29);
  return v22;
}

```

## disassembly

```asm
0x1800492e8  push    rbx
0x1800492ea  push    rsi
0x1800492eb  push    rdi
0x1800492ec  push    r12
0x1800492ee  push    r13
0x1800492f0  push    r14
0x1800492f2  push    r15
0x1800492f4  sub     rsp, 350h
0x1800492fb  mov     rax, cs:__security_cookie
0x180049302  xor     rax, rsp
0x180049305  mov     [rsp+388h+var_48], rax
0x18004930d  mov     r15, r9
0x180049310  mov     r13, r8
0x180049313  mov     r12, rdx
0x180049316  mov     rsi, rcx
0x180049319  lea     rdx, [rsp+388h+var_310]
0x18004931e  call    ?GetSite@LaunchExecuteCommandBase@@IEAA?AV?$ComPtr@UIUnknown@@@WRL@Microsoft@@XZ; LaunchExecuteCommandBase::GetSite(void)
0x180049323  nop
0x180049324  xor     edi, edi
0x180049326  cmp     [rsi+90h], rdi
0x18004932d  jnz     short loc_180049342
0x18004932f  lea     rdx, [rsp+388h+Buffer]; lpBuffer
0x180049337  mov     ecx, 104h; nBufferLength
0x18004933c  call    cs:__imp_GetCurrentDirectoryW
0x180049342  lea     rcx, [rsp+388h+var_2E0]
0x18004934a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18004934f  nop
0x180049350  mov     [rsp+388h+length], edi
0x180049354  lea     rdx, [rsp+388h+length]; length
0x180049359  mov     rcx, [rsi+0D0h]; string
0x180049360  call    cs:__imp_WindowsGetStringRawBuffer
0x180049366  cmp     [rsp+388h+length], edi
0x18004936a  jz      short loc_1800493D5
0x18004936c  mov     rdx, rax
0x18004936f  lea     rcx, [rsp+388h+var_2A0]
0x180049377  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004937c  nop
0x18004937d  lea     rdx, asc_180136A2C; "!"
0x180049384  lea     rcx, [rsp+388h+var_2A0]
0x18004938c  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KQEBG_K@Z; std::wstring::find(ushort const * const,unsigned __int64)
0x180049391  lea     r8, [rax+1]
0x180049395  lea     rdx, [rsp+388h+var_280]
0x18004939d  lea     rcx, [rsp+388h+var_2A0]
0x1800493a5  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x1800493aa  mov     rdx, rax
0x1800493ad  lea     rcx, [rsp+388h+var_2E0]
0x1800493b5  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800493ba  lea     rcx, [rsp+388h+var_280]
0x1800493c2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800493c7  nop
0x1800493c8  lea     rcx, [rsp+388h+var_2A0]
0x1800493d0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800493d5  cmp     [rsi+90h], rdi
0x1800493dc  jz      short loc_1800493F1
0x1800493de  lea     r14, [rsi+80h]
0x1800493e5  cmp     qword ptr [r14+18h], 7
0x1800493ea  jbe     short loc_18004940C
0x1800493ec  mov     r14, [r14]
0x1800493ef  jmp     short loc_18004940C
0x1800493f1  lea     rdx, [rsp+388h+Buffer]; lpBuffer
0x1800493f9  mov     ecx, 104h; nBufferLength
0x1800493fe  call    cs:__imp_GetCurrentDirectoryW
0x180049404  lea     r14, [rsp+388h+Buffer]
0x18004940c  mov     [rsp+388h+var_308], rdi
0x180049414  mov     r8, r12
0x180049417  lea     rdx, [rsp+388h+pszPath]
0x18004941f  call    ?GetFileItemStringFromShellItem@DesktopAppXExecuteCommandBase@@IEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUIShellItem@@@Z; DesktopAppXExecuteCommandBase::GetFileItemStringFromShellItem(IShellItem *)
0x180049424  nop
0x180049425  lea     rcx, [rsp+388h+pszPath]
0x18004942d  cmp     [rsp+388h+var_2E8], 7
0x180049436  cmova   rcx, [rsp+388h+pszPath]; pszPath
0x18004943f  call    cs:__imp_PathFindExtensionW
0x180049445  mov     rdx, rax
0x180049448  lea     rcx, [rsp+388h+var_2C0]
0x180049450  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180049455  nop
0x180049456  mov     [rsp+388h+var_320], 2
0x18004945e  mov     [rsp+388h+var_318], rdi
0x180049463  mov     rax, [r15]
0x180049466  mov     rbx, [rax]
0x180049469  lea     rcx, [rsp+388h+var_318]
0x18004946e  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x180049473  lea     r8, [rsp+388h+var_318]
0x180049478  lea     rdx, _GUID_2d6d3a33_aaa2_467b_9147_a146963e8066
0x18004947f  mov     rcx, r15
0x180049482  mov     rax, rbx
0x180049485  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004948a  mov     rcx, [rsp+388h]; this
0x180049492  test    eax, eax
0x180049494  jns     short loc_1800494AA
0x180049496  mov     r9d, eax; char *
0x180049499  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\windows.system.launc"...
0x1800494a0  mov     edx, 0C5h; void *
0x1800494a5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800494aa  mov     rdi, [rsp+388h+var_318]
0x1800494af  mov     rax, [rdi]
0x1800494b2  mov     rbx, [rax+18h]
0x1800494b6  xor     edx, edx; length
0x1800494b8  mov     rcx, [rsi+60h]; string
0x1800494bc  call    cs:__imp_WindowsGetStringRawBuffer
0x1800494c2  lea     r9, [rsp+388h+pszPath]
0x1800494ca  cmp     [rsp+388h+var_2E8], 7
0x1800494d3  cmova   r9, [rsp+388h+pszPath]
0x1800494dc  lea     r8, [rsp+388h+var_2E0]
0x1800494e4  cmp     [rsp+388h+var_2C8], 7
0x1800494ed  cmova   r8, [rsp+388h+var_2E0]
0x1800494f6  mov     rcx, [rsp+388h+var_310]
0x1800494fb  lea     rdx, [rsp+388h+var_2C0]
0x180049503  cmp     [rsp+388h+var_2A8], 7
0x18004950c  cmova   rdx, [rsp+388h+var_2C0]
0x180049515  mov     [rsp+388h+var_338], rax
0x18004951a  mov     [rsp+388h+var_340], r13
0x18004951f  mov     [rsp+388h+var_348], r9
0x180049524  mov     [rsp+388h+var_350], r8
0x180049529  mov     [rsp+388h+var_358], rcx
0x18004952e  mov     [rsp+388h+var_360], r12
0x180049533  mov     qword ptr [rsp+388h+var_368], r14; int
0x180049538  xor     r9d, r9d
0x18004953b  mov     r8, [rsi+0B0h]
0x180049542  mov     rcx, rdi
0x180049545  mov     rax, rbx
0x180049548  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004954d  mov     rcx, [rsp+388h]; this
0x180049555  test    eax, eax
0x180049557  jns     short loc_18004956D
0x180049559  mov     r9d, eax; char *
0x18004955c  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\windows.system.launc"...
0x180049563  mov     edx, 0D1h; void *
0x180049568  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004956d  mov     [rsp+388h+var_328], 0
0x180049572  mov     rax, [r15]
0x180049575  lea     r8, [rsp+388h+var_328]
0x18004957a  mov     rdx, [rsi+0D8h]
0x180049581  mov     rcx, r15
0x180049584  mov     rax, [rax+38h]
0x180049588  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004958d  mov     rcx, [rsp+388h]; this
0x180049595  test    eax, eax
0x180049597  jns     short loc_1800495AD
0x180049599  mov     r9d, eax; char *
0x18004959c  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\windows.system.launc"...
0x1800495a3  mov     edx, 0D4h; void *
0x1800495a8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800495ad  cmp     [rsp+388h+var_328], 0
0x1800495b2  jz      short loc_1800495EF
0x1800495b4  mov     rax, [r15]
0x1800495b7  lea     r9, [rsp+388h+var_320]
0x1800495bc  mov     r8d, [rsi+7Ch]
0x1800495c0  mov     dl, 1
0x1800495c2  mov     rcx, r15
0x1800495c5  mov     rax, [rax+30h]
0x1800495c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800495ce  mov     rcx, [rsp+388h]; this
0x1800495d6  test    eax, eax
0x1800495d8  jns     short loc_1800495EF
0x1800495da  mov     r9d, eax; char *
0x1800495dd  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\windows.system.launc"...
0x1800495e4  mov     edx, 0D8h; void *
0x1800495e9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800495ef  lea     rcx, [rsp+388h+var_318]
0x1800495f4  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800495f9  nop
0x1800495fa  jmp     short $+2
0x1800495fc  mov     ebx, [rsp+388h+var_320]
0x180049600  lea     rcx, [rsp+388h+var_2C0]
0x180049608  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004960d  nop
0x18004960e  lea     rcx, [rsp+388h+pszPath]
0x180049616  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004961b  nop
0x18004961c  lea     rcx, [rsp+388h+var_2E0]
0x180049624  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180049629  nop
0x18004962a  lea     rcx, [rsp+388h+var_310]
0x18004962f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180049634  mov     eax, ebx
0x180049636  mov     rcx, [rsp+388h+var_48]
0x18004963e  xor     rcx, rsp; StackCookie
0x180049641  call    __security_check_cookie
0x180049646  add     rsp, 350h
0x18004964d  pop     r15
0x18004964f  pop     r14
0x180049651  pop     r13
0x180049653  pop     r12
0x180049655  pop     rdi
0x180049656  pop     rsi
0x180049657  pop     rbx
0x180049658  retn
```
