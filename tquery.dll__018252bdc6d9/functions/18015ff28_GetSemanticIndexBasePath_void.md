# GetSemanticIndexBasePath(void)

- ea: `0x18015ff28`
- end: `0x18016013e`
- name: `?GetSemanticIndexBasePath@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ`
- size: `534`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18017d0fc`

## callees

- `0x18006380c`
- `0x18008b084`
- `0x18009befc`
- `0x1800f7bfc`
- `0x1801199cc`
- `0x18013edc0`
- `0x18015ff28`
- `0x1801710e4`
- `0x18017e500`
- `0x180188d90`
- `0x180189cce`
- `0x18018e8d7`
- `0x18019b924`

## import_xrefs

- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18016009e`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18016009e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18015ffaa`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18015ffaa`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveBackslashW` at `0x180160042`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveBackslashW` at `0x180160042`
- `api-ms-win-shcore-registry-l1-1-0!SHGetValueW` at `0x180160017`
- `api-ms-win-shcore-registry-l1-1-0!SHGetValueW` at `0x180160017`

## string_xrefs

- `0x180160009`: `DataDirectory`
- `0x18015ffbe`: `onecoreuap\base\appmodel\Search\common\include\SemanticSearchUtil.h`
- `0x18016002b`: `onecoreuap\base\appmodel\Search\common\include\SemanticSearchUtil.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall GetSemanticIndexBasePath(__int64 a1)
{
  HKEY *v2; // rbx
  const wchar_t *v3; // rcx
  bool v4; // al
  wchar_t *v5; // rdx
  unsigned int v6; // eax
  unsigned int v7; // eax
  int v8; // r8d
  _QWORD *v9; // rcx
  __int64 v10; // rdi
  unsigned __int64 v11; // rax
  unsigned __int64 v12; // rdx
  _QWORD *v13; // rax
  unsigned __int64 v14; // rbx
  unsigned int phkResult; // [rsp+20h] [rbp-E0h]
  unsigned int phkResulta; // [rsp+20h] [rbp-E0h]
  HKEY hkey; // [rsp+30h] [rbp-D0h] BYREF
  DWORD pcbData; // [rsp+38h] [rbp-C8h] BYREF
  DWORD pdwType[3]; // [rsp+3Ch] [rbp-C4h] BYREF
  _QWORD Src[2]; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int64 v22; // [rsp+58h] [rbp-A8h]
  unsigned __int64 v23; // [rsp+60h] [rbp-A0h]
  WCHAR pvData[264]; // [rsp+70h] [rbp-90h] BYREF
  wchar_t v25[264]; // [rsp+280h] [rbp+180h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4C8h] [rbp+3C8h]

  hkey = 0;
  v2 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hkey);
  v4 = MapRegistryKeyPath(v3, HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows Search", v25);
  v5 = v25;
  if ( !v4 )
    v5 = (wchar_t *)L"SOFTWARE\\Microsoft\\Windows Search";
  v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v5, 0, 0x20019u, v2);
  if ( v6 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x301,
      (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\SemanticSearchUtil.h",
      (const char *)v6,
      phkResult);
  memset_0(pvData, 0, 0x208u);
  pcbData = 520;
  pdwType[0] = 2;
  v7 = SHGetValueW(hkey, 0, L"DataDirectory", pdwType, pvData, &pcbData);
  if ( v7 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x307,
      (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\SemanticSearchUtil.h",
      (const char *)v7,
      phkResulta);
  PathRemoveBackslashW(pvData);
  std::wstring::wstring(Src);
  v9 = Src;
  if ( v23 > 7 )
    LODWORD(v9) = Src[0];
  v10 = 11;
  v11 = std::_Traits_find<std::char_traits<wchar_t>>((_DWORD)v9, v22, v8, (unsigned int)L"Search\\Data", 11);
  v12 = v11;
  if ( v11 != -1 )
  {
    if ( v22 < v11 )
    {
      std::_Xout_of_range("invalid string position");
      __debugbreak();
    }
    if ( v22 - v11 < 0xB )
      v10 = v22 - v11;
    v13 = Src;
    if ( v23 > 7 )
      v13 = (_QWORD *)Src[0];
    v14 = v22 - v10;
    memmove_0((char *)v13 + 2 * v12, (char *)v13 + 2 * v12 + 2 * v10, 2 * (v22 - v10 - v12) + 2);
    v22 = v14;
  }
  std::wstring::_Append<wchar_t>(Src);
  std::wstring::wstring(a1, Src);
  std::wstring::_Tidy_deallocate(Src);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
  return a1;
}

```

## disassembly

```asm
0x18015ff28  push    rbp
0x18015ff2a  push    rbx
0x18015ff2b  push    rsi
0x18015ff2c  push    rdi
0x18015ff2d  lea     rbp, [rsp-3A8h]
0x18015ff35  sub     rsp, 4A8h
0x18015ff3c  mov     rax, cs:__security_cookie
0x18015ff43  xor     rax, rsp
0x18015ff46  mov     [rbp+3C0h+var_30], rax
0x18015ff4d  mov     rsi, rcx
0x18015ff50  mov     [rsp+4C0h+hkey], rcx
0x18015ff55  mov     [rsp+4C0h+hkey], 0
0x18015ff5e  lea     rcx, [rsp+4C0h+hkey]
0x18015ff63  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x18015ff68  mov     rbx, rax
0x18015ff6b  lea     r9, [rbp+3C0h+var_240]; wchar_t *
0x18015ff72  lea     rdi, aSoftwareMicros_4; "SOFTWARE\\Microsoft\\Windows Search"
0x18015ff79  mov     r8, rdi; wchar_t *
0x18015ff7c  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x18015ff83  call    ?MapRegistryKeyPath@@YA_NPEB_WPEAUHKEY__@@0PEA_WK@Z; MapRegistryKeyPath(wchar_t const *,HKEY__ *,wchar_t const *,wchar_t *,ulong)
0x18015ff88  lea     rdx, [rbp+3C0h+var_240]
0x18015ff8f  test    al, al
0x18015ff91  cmovz   rdx, rdi; lpSubKey
0x18015ff95  mov     [rsp+4C0h+phkResult], rbx; unsigned int
0x18015ff9a  mov     r9d, 20019h; samDesired
0x18015ffa0  xor     r8d, r8d; ulOptions
0x18015ffa3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18015ffaa  call    cs:__imp_RegOpenKeyExW
0x18015ffb0  mov     rcx, [rbp+3C8h]; this
0x18015ffb7  test    eax, eax
0x18015ffb9  jz      short loc_18015FFD0
0x18015ffbb  mov     r9d, eax; char *
0x18015ffbe  lea     r8, aOnecoreuapBase_194; "onecoreuap\\base\\appmodel\\Search\\com"...
0x18015ffc5  mov     edx, 301h; void *
0x18015ffca  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18015ffd0  mov     ebx, 208h
0x18015ffd5  mov     r8d, ebx; Size
0x18015ffd8  xor     edx, edx; Val
0x18015ffda  lea     rcx, [rsp+4C0h+pvData]; void *
0x18015ffdf  call    memset_0
0x18015ffe4  mov     [rsp+4C0h+var_488], ebx
0x18015ffe8  mov     [rsp+4C0h+pdwType], 2
0x18015fff0  lea     rax, [rsp+4C0h+var_488]
0x18015fff5  mov     [rsp+4C0h+pcbData], rax; pcbData
0x18015fffa  lea     rax, [rsp+4C0h+pvData]
0x18015ffff  mov     [rsp+4C0h+phkResult], rax; unsigned int
0x180160004  lea     r9, [rsp+4C0h+pdwType]; pdwType
0x180160009  lea     r8, pszValue; "DataDirectory"
0x180160010  xor     edx, edx; pszSubKey
0x180160012  mov     rcx, [rsp+4C0h+hkey]; hkey
0x180160017  call    cs:__imp_SHGetValueW
0x18016001d  mov     rcx, [rbp+3C8h]; this
0x180160024  test    eax, eax
0x180160026  jz      short loc_18016003D
0x180160028  mov     r9d, eax; char *
0x18016002b  lea     r8, aOnecoreuapBase_194; "onecoreuap\\base\\appmodel\\Search\\com"...
0x180160032  mov     edx, 307h; void *
0x180160037  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18016003d  lea     rcx, [rsp+4C0h+pvData]; pszPath
0x180160042  call    cs:__imp_PathRemoveBackslashW
0x180160048  lea     rdx, [rsp+4C0h+pvData]
0x18016004d  lea     rcx, [rsp+4C0h+Src]
0x180160052  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180160057  nop
0x180160058  lea     rcx, [rsp+4C0h+Src]
0x18016005d  cmp     [rsp+4C0h+var_460], 7
0x180160063  cmova   rcx, [rsp+4C0h+Src]
0x180160069  mov     edi, 0Bh
0x18016006e  mov     [rsp+4C0h+phkResult], rdi
0x180160073  mov     r9, cs:off_1802C8AD0; "Search\\Data"
0x18016007a  mov     rdx, [rsp+4C0h+var_468]
0x18016007f  call    ??$_Traits_find@U?$char_traits@_W@std@@@std@@YA_KQEB_W_K101@Z; std::_Traits_find<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,unsigned __int64,wchar_t const * const,unsigned __int64)
0x180160084  mov     rdx, rax
0x180160087  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18016008b  jz      short loc_1801600E6
0x18016008d  mov     rbx, [rsp+4C0h+var_468]
0x180160092  cmp     rbx, rax
0x180160095  jnb     short loc_1801600A5
0x180160097  lea     rcx, aInvalidStringP; "invalid string position"
0x18016009e  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x1801600a4  int     3; Trap to Debugger
0x1801600a5  mov     rax, rbx
0x1801600a8  sub     rax, rdx
0x1801600ab  cmp     rax, rdi
0x1801600ae  cmovb   rdi, rax
0x1801600b2  lea     rax, [rsp+4C0h+Src]
0x1801600b7  cmp     [rsp+4C0h+var_460], 7
0x1801600bd  cmova   rax, [rsp+4C0h+Src]
0x1801600c3  lea     rcx, [rax+rdx*2]; void *
0x1801600c7  sub     rbx, rdi
0x1801600ca  mov     r8, rbx
0x1801600cd  sub     r8, rdx
0x1801600d0  lea     r8, ds:2[r8*2]; Size
0x1801600d8  lea     rdx, [rcx+rdi*2]; Src
0x1801600dc  call    memmove_0
0x1801600e1  mov     [rsp+4C0h+var_468], rbx
0x1801600e6  mov     r8d, 9
0x1801600ec  mov     rdx, cs:off_1802C7A18; "Semantic\\"
0x1801600f3  lea     rcx, [rsp+4C0h+Src]; Src
0x1801600f8  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x1801600fd  lea     rdx, [rsp+4C0h+Src]
0x180160102  mov     rcx, rsi
0x180160105  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x18016010a  nop
0x18016010b  lea     rcx, [rsp+4C0h+Src]
0x180160110  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180160115  nop
0x180160116  lea     rcx, [rsp+4C0h+hkey]
0x18016011b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180160120  mov     rax, rsi
0x180160123  mov     rcx, [rbp+3C0h+var_30]
0x18016012a  xor     rcx, rsp; StackCookie
0x18016012d  call    __security_check_cookie
0x180160132  add     rsp, 4A8h
0x180160139  pop     rdi
0x18016013a  pop     rsi
0x18016013b  pop     rbx
0x18016013c  pop     rbp
0x18016013d  retn
```
