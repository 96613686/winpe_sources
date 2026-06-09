# SecondaryTileHelper::SaveIconsToAppData(std::basic_string_view<wchar_t,std::char_traits<wchar_t>> const &,std::basic_string_view<wchar_t,std::char_traits<wchar_t>> const &,std::basic_string_view<wchar_t,std::char_traits<wchar_t>> const &,std::basic_string_view<wchar_t,std::char_traits<wchar_t>> const &)

- ea: `0x18013bf04`
- end: `0x18013c11b`
- name: `?SaveIconsToAppData@SecondaryTileHelper@@YAXAEBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@000@Z`
- size: `535`
- prototype: `__int64 __fastcall(LPCWSTR *, LPCWSTR *, _QWORD *, __int64 *)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x1804690ac`

## callees

- `0x180021c00`
- `0x1800235d4`
- `0x180025264`
- `0x180026860`
- `0x180037df8`
- `0x18004b894`
- `0x1800795e4`
- `0x1800920c8`
- `0x1800d9c48`
- `0x1800e488c`
- `0x18013511c`
- `0x18013bf04`
- `0x1801588c4`
- `0x18015cb00`

## import_xrefs

- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x18013c08a`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x18013c0bc`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x18013c08a`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x18013c0bc`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x18013bf54`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x18013bf54`
- `api-ms-win-shell-shdirectory-l1-1-0!__imp_SHCreateDirectory` at `0x18013c047`
- `api-ms-win-shell-shdirectory-l1-1-0!__imp_SHCreateDirectory` at `0x18013c047`

## string_xrefs

- `0x18013bf65`: `shellcommon\undockeddevkit\libs\helpers\secondarytilehelper.cpp`
- `0x18013c064`: `shellcommon\undockeddevkit\libs\helpers\secondarytilehelper.cpp`
- `0x18013c098`: `shellcommon\undockeddevkit\libs\helpers\secondarytilehelper.cpp`
- `0x18013c0ca`: `shellcommon\undockeddevkit\libs\helpers\secondarytilehelper.cpp`

## pseudocode

```c
__int64 __fastcall SecondaryTileHelper::SaveIconsToAppData(LPCWSTR *a1, LPCWSTR *a2, _QWORD *a3, __int64 *a4)
{
  HRESULT v8; // eax
  __int64 v9; // rdi
  int v10; // r8d
  int v11; // r9d
  _QWORD *v12; // rcx
  __int64 v13; // rax
  _QWORD *v14; // r9
  const WCHAR *v15; // rdx
  unsigned int v16; // eax
  const WCHAR *v17; // rdx
  const char *v18; // r9
  const WCHAR *v19; // rdx
  const char *v20; // r9
  int v22; // [rsp+20h] [rbp-89h]
  unsigned int v23; // [rsp+20h] [rbp-89h]
  PWSTR ppszPath; // [rsp+30h] [rbp-79h] BYREF
  _DWORD v25[4]; // [rsp+38h] [rbp-71h] BYREF
  __int64 v26; // [rsp+48h] [rbp-61h]
  unsigned __int64 v27; // [rsp+50h] [rbp-59h]
  _QWORD v28[4]; // [rsp+58h] [rbp-51h] BYREF
  PCWSTR pszPath[4]; // [rsp+78h] [rbp-31h] BYREF
  LPCWSTR lpNewFileName[4]; // [rsp+98h] [rbp-11h] BYREF
  LPCWSTR v31[4]; // [rsp+B8h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  ppszPath = 0;
  wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::reset(
    &ppszPath,
    0);
  v8 = SHGetKnownFolderPath(&FOLDERID_LocalAppData, 0, 0, &ppszPath);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x27,
      (unsigned int)"shellcommon\\undockeddevkit\\libs\\helpers\\secondarytilehelper.cpp",
      (const char *)(unsigned int)v8,
      v22);
  v9 = *a4;
  std::wstring::wstring(v25, *a3);
  v12 = v25;
  if ( v27 > 7 )
    LODWORD(v12) = v25[0];
  v13 = std::_Traits_rfind<std::char_traits<wchar_t>>((_DWORD)v12, v26, v10, v11, 1);
  if ( v13 == -1 )
    std::wstring::wstring(v28, v25);
  else
    std::wstring::substr(v25, v28, 0, v13);
  v14 = v28;
  if ( v28[3] > 7u )
    v14 = (_QWORD *)v28[0];
  wil::str_printf<std::wstring>(pszPath, L"%s\\Packages\\%s\\LocalState\\Pins\\%s\\", ppszPath, v14, v9);
  std::filesystem::path::~path((std::filesystem::path *)v28);
  std::filesystem::path::~path((std::filesystem::path *)v25);
  std::operator+<wchar_t>(v31, pszPath, L"largefavicon.png");
  std::operator+<wchar_t>(lpNewFileName, pszPath, L"rawicon.png");
  v15 = (const WCHAR *)pszPath;
  if ( pszPath[3] > (PCWSTR)7 )
    v15 = pszPath[0];
  v16 = SHCreateDirectory(0, v15);
  if ( v16 && v16 != 183 && v16 != 80 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x30,
      (unsigned int)"shellcommon\\undockeddevkit\\libs\\helpers\\secondarytilehelper.cpp",
      (const char *)v16,
      v23);
  v17 = (const WCHAR *)lpNewFileName;
  if ( lpNewFileName[3] > (LPCWSTR)7 )
    v17 = lpNewFileName[0];
  if ( !CopyFileW(*a1, v17, 0) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x33,
      (unsigned int)"shellcommon\\undockeddevkit\\libs\\helpers\\secondarytilehelper.cpp",
      v18);
  v19 = (const WCHAR *)v31;
  if ( v31[3] > (LPCWSTR)7 )
    v19 = v31[0];
  if ( !CopyFileW(*a2, v19, 0) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x34,
      (unsigned int)"shellcommon\\undockeddevkit\\libs\\helpers\\secondarytilehelper.cpp",
      v20);
  std::filesystem::path::~path((std::filesystem::path *)lpNewFileName);
  std::filesystem::path::~path((std::filesystem::path *)v31);
  std::filesystem::path::~path((std::filesystem::path *)pszPath);
  return wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&ppszPath);
}

```

## disassembly

```asm
0x18013bf04  push    rbp
0x18013bf06  push    rbx
0x18013bf07  push    rsi
0x18013bf08  push    rdi
0x18013bf09  push    r14
0x18013bf0b  lea     rbp, [rsp-37h]
0x18013bf10  sub     rsp, 0E0h
0x18013bf17  mov     rax, cs:__security_cookie
0x18013bf1e  xor     rax, rsp
0x18013bf21  mov     [rbp+57h+var_28], rax
0x18013bf25  mov     rdi, r9
0x18013bf28  mov     rbx, r8
0x18013bf2b  mov     r14, rdx
0x18013bf2e  mov     rsi, rcx
0x18013bf31  mov     [rbp+57h+ppszPath], 0
0x18013bf39  xor     edx, edx
0x18013bf3b  lea     rcx, [rbp+57h+ppszPath]
0x18013bf3f  call    ?reset@?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAAXPEA_W@Z; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::reset(wchar_t *)
0x18013bf44  lea     r9, [rbp+57h+ppszPath]; ppszPath
0x18013bf48  xor     r8d, r8d; hToken
0x18013bf4b  xor     edx, edx; dwFlags
0x18013bf4d  lea     rcx, FOLDERID_LocalAppData; rfid
0x18013bf54  call    cs:__imp_SHGetKnownFolderPath
0x18013bf5a  mov     rcx, [rbp+5Fh]; this
0x18013bf5e  test    eax, eax
0x18013bf60  jns     short loc_18013BF77
0x18013bf62  mov     r9d, eax; char *
0x18013bf65  lea     r8, aShellcommonUnd_129; "shellcommon\\undockeddevkit\\libs\\help"...
0x18013bf6c  mov     edx, 27h ; '''; void *
0x18013bf71  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18013bf77  mov     rdi, [rdi]
0x18013bf7a  mov     rdx, [rbx]
0x18013bf7d  lea     rcx, [rbp+57h+var_C8]
0x18013bf81  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18013bf86  nop
0x18013bf87  lea     rcx, [rbp+57h+var_C8]
0x18013bf8b  cmp     [rbp+57h+var_B0], 7
0x18013bf90  cmova   rcx, qword ptr [rbp+57h+var_C8]
0x18013bf95  mov     qword ptr [rsp+100h+var_E0], 1
0x18013bf9e  mov     rdx, [rbp+57h+var_B8]
0x18013bfa2  call    ??$_Traits_rfind@U?$char_traits@_W@std@@@std@@YA_KQEB_W_K101@Z; std::_Traits_rfind<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,unsigned __int64,wchar_t const * const,unsigned __int64)
0x18013bfa7  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18013bfab  jz      short loc_18013BFC2
0x18013bfad  mov     r9, rax
0x18013bfb0  xor     r8d, r8d
0x18013bfb3  lea     rdx, [rbp+57h+var_A8]
0x18013bfb7  lea     rcx, [rbp+57h+var_C8]
0x18013bfbb  call    ?substr@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x18013bfc0  jmp     short loc_18013BFCF
0x18013bfc2  lea     rdx, [rbp+57h+var_C8]
0x18013bfc6  lea     rcx, [rbp+57h+var_A8]
0x18013bfca  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18013bfcf  mov     rax, [rbp+57h+var_A8]
0x18013bfd3  lea     r9, [rbp+57h+var_A8]
0x18013bfd7  cmp     [rbp+57h+var_90], 7
0x18013bfdc  cmova   r9, rax
0x18013bfe0  mov     qword ptr [rsp+100h+var_E0], rdi; unsigned int
0x18013bfe5  mov     r8, [rbp+57h+ppszPath]
0x18013bfe9  lea     rdx, aSPackagesSLoca; "%s\\Packages\\%s\\LocalState\\Pins\\%s"...
0x18013bff0  lea     rcx, [rbp+57h+pszPath]
0x18013bff4  call    ??$str_printf@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@wil@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WZZ; wil::str_printf<std::wstring>(wchar_t const *,...)
0x18013bff9  nop
0x18013bffa  lea     rcx, [rbp+57h+var_A8]; this
0x18013bffe  call    ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
0x18013c003  nop
0x18013c004  lea     rcx, [rbp+57h+var_C8]; this
0x18013c008  call    ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
0x18013c00d  lea     r8, aLargefaviconPn; "largefavicon.png"
0x18013c014  lea     rdx, [rbp+57h+pszPath]
0x18013c018  lea     rcx, [rbp+57h+var_48]
0x18013c01c  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@AEBV10@QEB_W@Z; std::operator+<wchar_t>(std::wstring const &,wchar_t const * const)
0x18013c021  nop
0x18013c022  lea     r8, aRawiconPng; "rawicon.png"
0x18013c029  lea     rdx, [rbp+57h+pszPath]
0x18013c02d  lea     rcx, [rbp+57h+lpNewFileName]
0x18013c031  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@AEBV10@QEB_W@Z; std::operator+<wchar_t>(std::wstring const &,wchar_t const * const)
0x18013c036  nop
0x18013c037  lea     rdx, [rbp+57h+pszPath]
0x18013c03b  cmp     [rbp+57h+var_70], 7
0x18013c040  cmova   rdx, [rbp+57h+pszPath]; pszPath
0x18013c045  xor     ecx, ecx; hwnd
0x18013c047  call    cs:__imp_SHCreateDirectory
0x18013c04d  test    eax, eax
0x18013c04f  jz      short loc_18013C076
0x18013c051  cmp     eax, 0B7h
0x18013c056  jz      short loc_18013C076
0x18013c058  cmp     eax, 50h ; 'P'
0x18013c05b  jz      short loc_18013C076
0x18013c05d  mov     rcx, [rbp+5Fh]; this
0x18013c061  mov     r9d, eax; char *
0x18013c064  lea     r8, aShellcommonUnd_129; "shellcommon\\undockeddevkit\\libs\\help"...
0x18013c06b  mov     edx, 30h ; '0'; void *
0x18013c070  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18013c076  lea     rdx, [rbp+57h+lpNewFileName]
0x18013c07a  cmp     [rbp+57h+var_50], 7
0x18013c07f  cmova   rdx, [rbp+57h+lpNewFileName]; lpNewFileName
0x18013c084  xor     r8d, r8d; bFailIfExists
0x18013c087  mov     rcx, [rsi]; lpExistingFileName
0x18013c08a  call    cs:__imp_CopyFileW
0x18013c090  mov     rcx, [rbp+5Fh]; this
0x18013c094  test    eax, eax
0x18013c096  jnz     short loc_18013C0A8
0x18013c098  lea     r8, aShellcommonUnd_129; "shellcommon\\undockeddevkit\\libs\\help"...
0x18013c09f  lea     edx, [rax+33h]; void *
0x18013c0a2  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18013c0a8  lea     rdx, [rbp+57h+var_48]
0x18013c0ac  cmp     [rbp+57h+var_30], 7
0x18013c0b1  cmova   rdx, [rbp+57h+var_48]; lpNewFileName
0x18013c0b6  xor     r8d, r8d; bFailIfExists
0x18013c0b9  mov     rcx, [r14]; lpExistingFileName
0x18013c0bc  call    cs:__imp_CopyFileW
0x18013c0c2  mov     rcx, [rbp+5Fh]; this
0x18013c0c6  test    eax, eax
0x18013c0c8  jnz     short loc_18013C0DA
0x18013c0ca  lea     r8, aShellcommonUnd_129; "shellcommon\\undockeddevkit\\libs\\help"...
0x18013c0d1  lea     edx, [rax+34h]; void *
0x18013c0d4  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18013c0da  lea     rcx, [rbp+57h+lpNewFileName]; this
0x18013c0de  call    ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
0x18013c0e3  nop
0x18013c0e4  lea     rcx, [rbp+57h+var_48]; this
0x18013c0e8  call    ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
0x18013c0ed  nop
0x18013c0ee  lea     rcx, [rbp+57h+pszPath]; this
0x18013c0f2  call    ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
0x18013c0f7  nop
0x18013c0f8  lea     rcx, [rbp+57h+ppszPath]
0x18013c0fc  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x18013c101  mov     rcx, [rbp+57h+var_28]
0x18013c105  xor     rcx, rsp; StackCookie
0x18013c108  call    __security_check_cookie
0x18013c10d  add     rsp, 0E0h
0x18013c114  pop     r14
0x18013c116  pop     rdi
0x18013c117  pop     rsi
0x18013c118  pop     rbx
0x18013c119  pop     rbp
0x18013c11a  retn
```
