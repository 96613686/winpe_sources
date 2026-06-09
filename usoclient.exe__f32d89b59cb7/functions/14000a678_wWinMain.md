# wWinMain

- ea: `0x14000a678`
- end: `0x14000aa51`
- name: `wWinMain`
- size: `985`
- prototype: `int __stdcall(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPWSTR lpCmdLine, int nShowCmd)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x140001f70`

## callees

- `0x140002120`
- `0x1400023ec`
- `0x140006614`
- `0x140006dd8`
- `0x140006ed8`
- `0x140007188`
- `0x140007ad8`
- `0x140007ec8`
- `0x1400087e4`
- `0x140008a04`
- `0x1400095d8`
- `0x14000a140`
- `0x14000a188`
- `0x14000a678`
- `0x14000ac60`
- `0x14000c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000a935`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000a935`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14000a9a0`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14000a9a0`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14000a919`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14000a919`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x14000a6ac`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x14000a6ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000a8ae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000a8ae`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x14000a6b2`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x14000a6b2`
- `api-ms-win-core-commandlinetoargv-l1-1-0!CommandLineToArgvW` at `0x14000a6c5`
- `api-ms-win-core-commandlinetoargv-l1-1-0!CommandLineToArgvW` at `0x14000a6c5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000a9d2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000a9d2`

## string_xrefs

- `0x14000a9fe`: `onecore\enduser\windowsupdate\undocked\stubexes\main.cpp`
- `0x14000aa10`: `onecore\enduser\windowsupdate\undocked\stubexes\main.cpp`
- `0x14000aa3f`: `onecore\enduser\windowsupdate\undocked\stubexes\main.cpp`
- `0x14000a812`: `UsoClientImpl.dll`
- `0x14000a92b`: `ProcessUsoClientCommand`
- `0x14000aa26`: `onecore\internal\sdk\inc\wil\opensource/wil/win32_helpers.h`

## pseudocode

```c
int __stdcall wWinMain(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPWSTR lpCmdLine, int nShowCmd)
{
  const WCHAR *CommandLineW; // rax
  LPWSTR *v5; // rbx
  const char *v6; // r9
  unsigned __int64 v7; // r8
  __int64 v8; // r14
  __int64 v9; // r9
  int v10; // r15d
  __int128 *p_Src; // rcx
  unsigned __int64 v12; // rdx
  LPWSTR v13; // r10
  __int64 v14; // rsi
  __int128 *v15; // rdi
  uus::Session *v16; // rax
  __int64 v17; // r15
  __int64 v18; // rcx
  __int64 v19; // rax
  int v20; // eax
  void *v21; // rdi
  const WCHAR *v22; // rcx
  HMODULE Library; // rax
  const char *v24; // r9
  HMODULE v25; // rdi
  FARPROC ProcAddress; // rax
  const char *v27; // r9
  __int128 *v28; // rcx
  int v29; // eax
  __int128 *v30; // rcx
  int v31; // esi
  LPCWSTR *v32; // rcx
  int v34; // [rsp+20h] [rbp-E0h]
  char v35; // [rsp+30h] [rbp-D0h] BYREF
  char v36; // [rsp+31h] [rbp-CFh] BYREF
  _BYTE v37[2]; // [rsp+32h] [rbp-CEh] BYREF
  int pNumArgs[3]; // [rsp+34h] [rbp-CCh] BYREF
  const wchar_t *v39; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v40; // [rsp+48h] [rbp-B8h]
  LPVOID pv; // [rsp+50h] [rbp-B0h] BYREF
  __int128 *v42; // [rsp+58h] [rbp-A8h] BYREF
  __int128 Src; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v44; // [rsp+70h] [rbp-90h]
  unsigned __int64 v45; // [rsp+78h] [rbp-88h]
  LPCWSTR lpLibFileName[3]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int64 v47; // [rsp+98h] [rbp-68h]
  _BYTE v48[32]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v49[32]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v50[32]; // [rsp+E0h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+58h]

  v37[0] = 0;
  SetErrorMode(0x8003u);
  CommandLineW = GetCommandLineW();
  pNumArgs[0] = 0;
  v5 = CommandLineToArgvW(CommandLineW, pNumArgs);
  if ( !v5 )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x1C,
      (unsigned int)"onecore\\enduser\\windowsupdate\\undocked\\stubexes\\main.cpp",
      v6);
  v44 = 0;
  v7 = 7;
  v8 = -1;
  v45 = 7;
  v9 = 0;
  v10 = 1;
  Src = 0;
  LOWORD(Src) = 0;
  if ( pNumArgs[0] > 1 )
  {
    while ( 1 )
    {
      if ( v9 )
      {
        p_Src = &Src;
        if ( v7 == v9 )
        {
          std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,unsigned short const *,unsigned __int64>(
            &Src,
            1);
        }
        else
        {
          v44 = v9 + 1;
          if ( v7 > 7 )
            p_Src = (__int128 *)Src;
          *((_WORD *)p_Src + v9) = asc_14000DDCC[0];
          *((_WORD *)p_Src + v9 + 1) = 0;
        }
        v9 = v44;
        v7 = v45;
      }
      v12 = -1;
      v13 = v5[v10];
      do
        ++v12;
      while ( v13[v12] );
      if ( v12 > v7 - v9 )
      {
        std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,unsigned short const *,unsigned __int64>(
          &Src,
          v12);
      }
      else
      {
        v14 = v12 + v9;
        v44 = v12 + v9;
        v15 = &Src;
        if ( v7 > 7 )
          v15 = (__int128 *)Src;
        memmove_0((char *)v15 + 2 * v9, v13, 2 * v12);
        *((_WORD *)v15 + v14) = 0;
      }
      if ( ++v10 >= pNumArgs[0] )
        break;
      v7 = v45;
      v9 = v44;
    }
  }
  v36 = 1;
  v16 = (uus::Session *)operator new(0x10u);
  v17 = uus::Session::Session(v16, L"usoclientimpl");
  v40 = 17;
  v39 = L"UsoClientImpl.dll";
  std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(v50);
  v18 = *(_QWORD *)(v17 + 8);
  if ( v18 )
  {
    v19 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v18 + 40LL))(v18, 1);
    do
      ++v8;
    while ( *(_WORD *)(v19 + 2 * v8) );
    v39 = (const wchar_t *)v19;
    v40 = v8;
    std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(v48);
  }
  else
  {
    pv = 0;
    v20 = wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(
            0,
            &pv);
    if ( v20 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x250,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/win32_helpers.h",
        (const char *)(unsigned int)v20,
        v34);
    v21 = pv;
    do
      ++v8;
    while ( *((_WORD *)pv + v8) );
    v39 = (const wchar_t *)pv;
    v40 = v8;
    std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(v49);
    if ( v21 )
      CoTaskMemFree(v21);
    uus::Utility::GetGuestOrNativeArchFolder(v48, v49);
    std::wstring::~wstring(v49);
  }
  std::filesystem::operator/(lpLibFileName, (struct std::filesystem::path *)v48, (std::filesystem *)v50);
  std::wstring::~wstring(v48);
  std::wstring::~wstring(v50);
  v35 = 1;
  uus::UndockedStubTelemetry::UusLogStubDefines<bool &,bool &,bool>(v37, &v36, &v35);
  v22 = (const WCHAR *)lpLibFileName;
  if ( v47 > 7 )
    v22 = lpLibFileName[0];
  Library = LoadLibraryExW(v22, 0, 0);
  v25 = Library;
  if ( !Library )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x3F,
      (unsigned int)"onecore\\enduser\\windowsupdate\\undocked\\stubexes\\main.cpp",
      v24);
  ProcAddress = GetProcAddress(Library, "ProcessUsoClientCommand");
  if ( !ProcAddress )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x43,
      (unsigned int)"onecore\\enduser\\windowsupdate\\undocked\\stubexes\\main.cpp",
      v27);
  v28 = &Src;
  if ( v45 > 7 )
    v28 = (__int128 *)Src;
  v29 = ((__int64 (__fastcall *)(__int128 *))ProcAddress)(v28);
  v30 = &Src;
  LODWORD(pv) = v29;
  if ( v45 > 7 )
    v30 = (__int128 *)Src;
  v31 = v29;
  v42 = v30;
  v32 = lpLibFileName;
  if ( v47 > 7 )
    v32 = (LPCWSTR *)lpLibFileName[0];
  v39 = (const wchar_t *)v32;
  uus::UndockedStubTelemetry::UusLogStubExe2Dll<unsigned short const *,unsigned short const *,int const &>(
    &v39,
    &v42,
    &pv);
  FreeLibrary(v25);
  std::wstring::~wstring(lpLibFileName);
  (**(void (__fastcall ***)(__int64, __int64))v17)(v17, 1);
  std::wstring::~wstring(&Src);
  LocalFree(v5);
  return v31;
}

```

## disassembly

```asm
0x14000a678  push    rbp
0x14000a67a  push    rbx
0x14000a67b  push    rsi
0x14000a67c  push    rdi
0x14000a67d  push    r12
0x14000a67f  push    r13
0x14000a681  push    r14
0x14000a683  push    r15
0x14000a685  lea     rbp, [rsp-18h]
0x14000a68a  sub     rsp, 118h
0x14000a691  mov     rax, cs:__security_cookie
0x14000a698  xor     rax, rsp
0x14000a69b  mov     [rbp+50h+var_50], rax
0x14000a69f  xor     r12d, r12d
0x14000a6a2  mov     ecx, 8003h; uMode
0x14000a6a7  mov     [rsp+150h+var_11E], r12b
0x14000a6ac  call    cs:__imp_SetErrorMode
0x14000a6b2  call    cs:__imp_GetCommandLineW
0x14000a6b8  lea     rdx, [rsp+150h+pNumArgs]; pNumArgs
0x14000a6bd  mov     [rsp+150h+pNumArgs], r12d
0x14000a6c2  mov     rcx, rax; lpCmdLine
0x14000a6c5  call    cs:__imp_CommandLineToArgvW
0x14000a6cb  mov     rcx, [rbp+58h]; this
0x14000a6cf  test    rax, rax
0x14000a6d2  mov     rbx, rax
0x14000a6d5  setz    al
0x14000a6d8  test    al, al
0x14000a6da  jnz     loc_14000AA10
0x14000a6e0  lea     r13d, [r12+1]
0x14000a6e5  mov     [rsp+150h+var_E0], r12
0x14000a6ea  xorps   xmm0, xmm0
0x14000a6ed  lea     r8d, [r12+7]
0x14000a6f2  or      r14, 0FFFFFFFFFFFFFFFFh
0x14000a6f6  mov     [rsp+150h+var_D8], r8
0x14000a6fb  mov     r9d, r12d
0x14000a6fe  mov     r15d, r13d
0x14000a701  movups  [rsp+150h+Src], xmm0
0x14000a706  mov     word ptr [rsp+150h+Src], r12w
0x14000a70c  cmp     [rsp+150h+pNumArgs], r13d
0x14000a711  jle     loc_14000A7E8
0x14000a717  test    r9, r9
0x14000a71a  jz      short loc_14000A76F
0x14000a71c  mov     rax, r8
0x14000a71f  lea     rcx, [rsp+150h+Src]; Src
0x14000a724  sub     rax, r9
0x14000a727  cmp     rax, r13
0x14000a72a  jb      short loc_14000A751
0x14000a72c  mov     eax, dword ptr cs:asc_14000DDCC; " "
0x14000a732  lea     rdx, [r9+1]
0x14000a736  mov     [rsp+150h+var_E0], rdx
0x14000a73b  cmp     r8, 7
0x14000a73f  cmova   rcx, qword ptr [rsp+150h+Src]
0x14000a745  mov     [rcx+r9*2], ax
0x14000a74a  mov     [rcx+rdx*2], r12w
0x14000a74f  jmp     short loc_14000A765
0x14000a751  lea     r9, asc_14000DDCC; " "
0x14000a758  mov     qword ptr [rsp+150h+var_130], r13; __int64
0x14000a75d  mov     rdx, r13
0x14000a760  call    ??$_Reallocate_grow_by@V_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@Z; std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64>(unsigned __int64,_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64)
0x14000a765  mov     r9, [rsp+150h+var_E0]
0x14000a76a  mov     r8, [rsp+150h+var_D8]
0x14000a76f  movsxd  rax, r15d
0x14000a772  mov     rdx, r14
0x14000a775  mov     r10, [rbx+rax*8]
0x14000a779  inc     rdx
0x14000a77c  cmp     [r10+rdx*2], r12w
0x14000a781  jnz     short loc_14000A779
0x14000a783  mov     rax, r8
0x14000a786  sub     rax, r9
0x14000a789  cmp     rdx, rax
0x14000a78c  ja      short loc_14000A7BD
0x14000a78e  cmp     r8, 7
0x14000a792  lea     rsi, [rdx+r9]
0x14000a796  lea     r8, [rdx+rdx]; Size
0x14000a79a  mov     [rsp+150h+var_E0], rsi
0x14000a79f  lea     rdi, [rsp+150h+Src]
0x14000a7a4  mov     rdx, r10; Src
0x14000a7a7  cmova   rdi, qword ptr [rsp+150h+Src]
0x14000a7ad  lea     rcx, [rdi+r9*2]; void *
0x14000a7b1  call    memmove_0
0x14000a7b6  mov     [rdi+rsi*2], r12w
0x14000a7bb  jmp     short loc_14000A7CF
0x14000a7bd  mov     r9, r10
0x14000a7c0  mov     qword ptr [rsp+150h+var_130], rdx; __int64
0x14000a7c5  lea     rcx, [rsp+150h+Src]; Src
0x14000a7ca  call    ??$_Reallocate_grow_by@V_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@Z; std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64>(unsigned __int64,_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64)
0x14000a7cf  add     r15d, r13d
0x14000a7d2  cmp     r15d, [rsp+150h+pNumArgs]
0x14000a7d7  jge     short loc_14000A7E8
0x14000a7d9  mov     r8, [rsp+150h+var_D8]
0x14000a7de  mov     r9, [rsp+150h+var_E0]
0x14000a7e3  jmp     loc_14000A717
0x14000a7e8  mov     ecx, 10h; Size
0x14000a7ed  mov     [rsp+150h+var_11F], r13b
0x14000a7f2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000a7f7  lea     rdx, aUsoclientimpl; "usoclientimpl"
0x14000a7fe  mov     rcx, rax; this
0x14000a801  call    ??0Session@uus@@QEAA@PEBG@Z; uus::Session::Session(ushort const *)
0x14000a806  mov     r15, rax
0x14000a809  mov     [rsp+150h+var_108], 11h
0x14000a812  lea     rax, aUsoclientimplD; "UsoClientImpl.dll"
0x14000a819  lea     rdx, [rsp+150h+var_110]
0x14000a81e  mov     [rsp+150h+var_110], rax
0x14000a823  lea     rcx, [rbp+50h+var_70]; void *
0x14000a827  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@V?$basic_string_view@GU?$char_traits@G@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::basic_string_view<ushort>,std::filesystem::_Normal_conversion)
0x14000a82c  mov     rcx, [r15+8]
0x14000a830  test    rcx, rcx
0x14000a833  jz      short loc_14000A868
0x14000a835  mov     rdx, [rcx]
0x14000a838  mov     rax, [rdx+28h]
0x14000a83c  mov     edx, r13d
0x14000a83f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a844  inc     r14
0x14000a847  cmp     [rax+r14*2], r12w
0x14000a84c  jnz     short loc_14000A844
0x14000a84e  lea     rdx, [rsp+150h+var_110]
0x14000a853  mov     [rsp+150h+var_110], rax
0x14000a858  lea     rcx, [rbp+50h+var_B0]; void *
0x14000a85c  mov     [rsp+150h+var_108], r14
0x14000a861  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@V?$basic_string_view@GU?$char_traits@G@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::basic_string_view<ushort>,std::filesystem::_Normal_conversion)
0x14000a866  jmp     short loc_14000A8CA
0x14000a868  lea     rdx, [rsp+150h+pv]
0x14000a86d  mov     [rsp+150h+pv], r12
0x14000a872  call    ??$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@@Z; wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x14000a877  test    eax, eax
0x14000a879  js      loc_14000AA22
0x14000a87f  mov     rdi, [rsp+150h+pv]
0x14000a884  inc     r14
0x14000a887  cmp     [rdi+r14*2], r12w
0x14000a88c  jnz     short loc_14000A884
0x14000a88e  lea     rdx, [rsp+150h+var_110]
0x14000a893  mov     [rsp+150h+var_110], rdi
0x14000a898  lea     rcx, [rbp+50h+var_90]; void *
0x14000a89c  mov     [rsp+150h+var_108], r14
0x14000a8a1  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@V?$basic_string_view@GU?$char_traits@G@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::basic_string_view<ushort>,std::filesystem::_Normal_conversion)
0x14000a8a6  test    rdi, rdi
0x14000a8a9  jz      short loc_14000A8B4
0x14000a8ab  mov     rcx, rdi; pv
0x14000a8ae  call    cs:__imp_CoTaskMemFree
0x14000a8b4  lea     rdx, [rbp+50h+var_90]
0x14000a8b8  lea     rcx, [rbp+50h+var_B0]
0x14000a8bc  call    ?GetGuestOrNativeArchFolder@Utility@uus@@SA?AVpath@filesystem@std@@AEBV345@@Z; uus::Utility::GetGuestOrNativeArchFolder(std::filesystem::path const &)
0x14000a8c1  lea     rcx, [rbp+50h+var_90]
0x14000a8c5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000a8ca  lea     r8, [rbp+50h+var_70]; this
0x14000a8ce  lea     rdx, [rbp+50h+var_B0]; struct std::filesystem::path *
0x14000a8d2  lea     rcx, [rbp+50h+lpLibFileName]; Src
0x14000a8d6  call    ??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z; std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)
0x14000a8db  lea     rcx, [rbp+50h+var_B0]
0x14000a8df  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000a8e4  lea     rcx, [rbp+50h+var_70]
0x14000a8e8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000a8ed  lea     r8, [rsp+150h+var_120]
0x14000a8f2  mov     [rsp+150h+var_120], r13b
0x14000a8f7  lea     rdx, [rsp+150h+var_11F]
0x14000a8fc  lea     rcx, [rsp+150h+var_11E]
0x14000a901  call    ??$UusLogStubDefines@AEA_NAEA_N_N@UndockedStubTelemetry@uus@@SAXAEA_N0$$QEA_N@Z; uus::UndockedStubTelemetry::UusLogStubDefines<bool &,bool &,bool>(bool &,bool &,bool &&)
0x14000a906  cmp     [rbp+50h+var_B8], 7
0x14000a90b  lea     rcx, [rbp+50h+lpLibFileName]
0x14000a90f  cmova   rcx, [rbp+50h+lpLibFileName]; lpLibFileName
0x14000a914  xor     r8d, r8d; dwFlags
0x14000a917  xor     edx, edx; hFile
0x14000a919  call    cs:__imp_LoadLibraryExW
0x14000a91f  mov     rdi, rax
0x14000a922  test    rax, rax
0x14000a925  jz      loc_14000AA3B
0x14000a92b  lea     rdx, aProcessusoclie; "ProcessUsoClientCommand"
0x14000a932  mov     rcx, rax; hModule
0x14000a935  call    cs:__imp_GetProcAddress
0x14000a93b  test    rax, rax
0x14000a93e  jz      loc_14000A9FA
0x14000a944  cmp     [rsp+150h+var_D8], 7
0x14000a94a  lea     rcx, [rsp+150h+Src]
0x14000a94f  cmova   rcx, qword ptr [rsp+150h+Src]
0x14000a955  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a95a  cmp     [rsp+150h+var_D8], 7
0x14000a960  lea     rcx, [rsp+150h+Src]
0x14000a965  lea     r8, [rsp+150h+pv]
0x14000a96a  mov     dword ptr [rsp+150h+pv], eax
0x14000a96e  cmova   rcx, qword ptr [rsp+150h+Src]
0x14000a974  lea     rdx, [rsp+150h+var_F8]
0x14000a979  cmp     [rbp+50h+var_B8], 7
0x14000a97e  mov     esi, eax
0x14000a980  mov     [rsp+150h+var_F8], rcx
0x14000a985  lea     rcx, [rbp+50h+lpLibFileName]
0x14000a989  cmova   rcx, [rbp+50h+lpLibFileName]
0x14000a98e  mov     [rsp+150h+var_110], rcx
0x14000a993  lea     rcx, [rsp+150h+var_110]
0x14000a998  call    ??$UusLogStubExe2Dll@PEBGPEBGAEBH@UndockedStubTelemetry@uus@@SAX$$QEAPEBG0AEBH@Z; uus::UndockedStubTelemetry::UusLogStubExe2Dll<ushort const *,ushort const *,int const &>(ushort const * &&,ushort const * &&,int const &)
0x14000a99d  mov     rcx, rdi; hLibModule
0x14000a9a0  call    cs:__imp_FreeLibrary
0x14000a9a6  lea     rcx, [rbp+50h+lpLibFileName]
0x14000a9aa  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000a9af  mov     rax, [r15]
0x14000a9b2  mov     edx, r13d
0x14000a9b5  mov     rcx, r15
0x14000a9b8  mov     rax, [rax]
0x14000a9bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a9c0  lea     rcx, [rsp+150h+Src]
0x14000a9c5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000a9ca  test    rbx, rbx
0x14000a9cd  jz      short loc_14000A9D8
0x14000a9cf  mov     rcx, rbx; hMem
0x14000a9d2  call    cs:__imp_LocalFree
0x14000a9d8  mov     eax, esi
0x14000a9da  mov     rcx, [rbp+50h+var_50]
0x14000a9de  xor     rcx, rsp; StackCookie
0x14000a9e1  call    __security_check_cookie
0x14000a9e6  add     rsp, 118h
0x14000a9ed  pop     r15
0x14000a9ef  pop     r14
0x14000a9f1  pop     r13
0x14000a9f3  pop     r12
0x14000a9f5  pop     rdi
0x14000a9f6  pop     rsi
0x14000a9f7  pop     rbx
0x14000a9f8  pop     rbp
0x14000a9f9  retn
0x14000a9fa  mov     rcx, [rbp+58h]; this
0x14000a9fe  lea     r8, aOnecoreEnduser; "onecore\\enduser\\windowsupdate\\undock"...
0x14000aa05  mov     edx, 43h ; 'C'; void *
0x14000aa0a  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x14000aa10  lea     r8, aOnecoreEnduser; "onecore\\enduser\\windowsupdate\\undock"...
0x14000aa17  mov     edx, 1Ch; void *
0x14000aa1c  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x14000aa22  mov     rcx, [rbp+58h]; this
0x14000aa26  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14000aa2d  mov     r9d, eax; char *
0x14000aa30  mov     edx, 250h; void *
0x14000aa35  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x14000aa3b  mov     rcx, [rbp+58h]; this
0x14000aa3f  lea     r8, aOnecoreEnduser; "onecore\\enduser\\windowsupdate\\undock"...
0x14000aa46  mov     edx, 3Fh ; '?'; void *
0x14000aa4b  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
