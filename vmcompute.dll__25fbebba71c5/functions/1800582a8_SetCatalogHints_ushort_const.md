# SetCatalogHints(ushort const *)

- ea: `0x1800582a8`
- end: `0x18005855b`
- name: `?SetCatalogHints@@YAXPEBG@Z`
- size: `691`
- prototype: `void __fastcall(PCWSTR pszPathIn)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18005a8c8`

## callees

- `0x180002f50`
- `0x1800044b0`
- `0x180006660`
- `0x180008c34`
- `0x18000e8dc`
- `0x180018bd4`
- `0x180022d10`
- `0x180024ae4`
- `0x18002e07c`
- `0x18002f94c`
- `0x180057b04`
- `0x180057f2c`
- `0x180058190`
- `0x1800582a8`
- `0x18007a7e4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005830f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005830f`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800582f3`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800582f3`

## string_xrefs

- `0x1800584d4`: `onecore\vm\compute\dll\lib\storage\cicache.cpp`
- `0x180058533`: `onecore\vm\compute\dll\lib\storage\cicache.cpp`
- `0x180058426`: `Windows\System32\catroot\{F750E6C3-38EE-11D1-85E5-00C04FC295EE}`
- `0x180058361`: `Windows\System32\ntdll.dll`
- `0x180058549`: `onecore\internal\sdk\inc\wil\opensource\wil\stl.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall SetCatalogHints(PCWSTR pszPathIn)
{
  const WCHAR *v2; // rax
  DWORD FileAttributesW; // ebx
  DWORD LastError; // eax
  wchar_t *trivial_1; // rax
  const char *v6; // r9
  const wchar_t **v7; // rbx
  char *v8; // rax
  char v9; // bl
  __int64 v10; // rdx
  __int64 v11; // r8
  _WORD *v12; // rax
  _QWORD *v13; // rax
  PCWSTR v14; // rbx
  PCWSTR v15; // rdi
  _QWORD *v16; // rdx
  const WCHAR *v17; // rcx
  unsigned int v18; // eax
  unsigned int v19; // [rsp+20h] [rbp-59h]
  __int64 v20; // [rsp+40h] [rbp-39h] BYREF
  const wchar_t **v21; // [rsp+48h] [rbp-31h]
  _QWORD v22[2]; // [rsp+50h] [rbp-29h] BYREF
  _QWORD Src[2]; // [rsp+60h] [rbp-19h] BYREF
  __int64 v24; // [rsp+70h] [rbp-9h]
  unsigned __int64 v25; // [rsp+78h] [rbp-1h]
  PCWSTR SourceString[4]; // [rsp+80h] [rbp+7h] BYREF
  const wchar_t *v27; // [rsp+A0h] [rbp+27h] BYREF
  const WCHAR *v28; // [rsp+A8h] [rbp+2Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v2 = (const WCHAR *)Vml::CombineFilePath(SourceString, pszPathIn, L"Windows\\WinSxS");
  if ( *((_QWORD *)v2 + 3) > 7u )
    v2 = *(const WCHAR **)v2;
  FileAttributesW = GetFileAttributesW(v2);
  std::wstring::~wstring(SourceString);
  if ( FileAttributesW == -1 )
  {
    LastError = GetLastError();
    if ( LastError - 2 > 1 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x179,
        (unsigned int)"onecore\\vm\\compute\\dll\\lib\\storage\\cicache.cpp",
        (const char *)LastError,
        v19);
  }
  else
  {
    trivial_1 = (wchar_t *)_std_find_trivial_1("$CI.CATALOGHINT", L"winmd", 0);
    if ( trivial_1 == L"winmd"
      || (v7 = (const wchar_t **)((char *)trivial_1 - "$CI.CATALOGHINT"), (char *)trivial_1 - "$CI.CATALOGHINT" == -1) )
    {
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xEB,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\stl.h",
        v6);
    }
    v8 = (char *)Vml::CombineFilePath(SourceString, pszPathIn, L"Windows\\System32\\ntdll.dll");
    v20 = (__int64)"$CI.CATALOGHINT";
    v21 = v7;
    v9 = HasExtendedAttribute(v8, (__int64)&v20);
    std::wstring::~wstring(SourceString);
    if ( !v9 )
    {
      Vml::CombineFilePath(Src, pszPathIn, L"Windows");
      v12 = Src;
      if ( v25 > 7 )
        v12 = (_WORD *)Src[0];
      if ( *v12 != 92 )
      {
        if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - v24) < 4 )
          std::_Xlen_string();
        v13 = Src;
        if ( v25 > 7 )
          v13 = (_QWORD *)Src[0];
        std::wstring::wstring(SourceString, v10, v11, L"\\\\?\\", 4, v13, v24);
        std::wstring::operator=(Src, SourceString);
        std::wstring::~wstring(SourceString);
      }
      v28 = L"Windows\\System32\\catroot\\{F750E6C3-38EE-11D1-85E5-00C04FC295EE}";
      v27 = L"cat";
      v20 = 1;
      v21 = &v27;
      v22[0] = 1;
      v22[1] = &v28;
      LOBYTE(v19) = 0;
      FindFiles(SourceString, pszPathIn, v22, &v20, v19);
      v14 = SourceString[0];
      v15 = SourceString[1];
      while ( v14 != v15 )
      {
        v16 = Src;
        if ( v25 > 7 )
          v16 = (_QWORD *)Src[0];
        if ( *((_QWORD *)v14 + 3) <= 7u )
          v17 = v14;
        else
          v17 = *(const WCHAR **)v14;
        v18 = CiSetHintsForPackageCatalog2(v17, (__int64)v16);
        if ( v18 != -1073741766 && v18 )
        {
          if ( *((_QWORD *)v14 + 3) <= 7u )
            wil::details::in1diag3::Log_NtStatusMsg(
              retaddr,
              (void *)0x197,
              (unsigned int)"onecore\\vm\\compute\\dll\\lib\\storage\\cicache.cpp",
              (const char *)v18,
              (int)"%ws",
              (const char *)v14);
          else
            wil::details::in1diag3::Log_NtStatusMsg(
              retaddr,
              (void *)0x197,
              (unsigned int)"onecore\\vm\\compute\\dll\\lib\\storage\\cicache.cpp",
              (const char *)v18,
              (int)"%ws",
              *(const char **)v14);
        }
        v14 += 16;
      }
      std::vector<std::wstring>::_Tidy(SourceString);
      std::wstring::~wstring(Src);
    }
  }
}

```

## disassembly

```asm
0x1800582a8  mov     [rsp-8+arg_8], rbx
0x1800582ad  mov     [rsp-8+arg_10], rsi
0x1800582b2  push    rbp
0x1800582b3  push    rdi
0x1800582b4  push    r14
0x1800582b6  lea     rbp, [rsp-47h]
0x1800582bb  sub     rsp, 0C0h
0x1800582c2  mov     rax, cs:__security_cookie
0x1800582c9  xor     rax, rsp
0x1800582cc  mov     [rbp+57h+var_20], rax
0x1800582d0  mov     rdi, rcx
0x1800582d3  lea     r8, aWindowsWinsxs; "Windows\\WinSxS"
0x1800582da  mov     rdx, rcx; pszPathIn
0x1800582dd  lea     rcx, [rbp+57h+SourceString]; Src
0x1800582e1  call    ?CombineFilePath@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG0@Z; Vml::CombineFilePath(ushort const *,ushort const *)
0x1800582e6  cmp     qword ptr [rax+18h], 7
0x1800582eb  jbe     short loc_1800582F0
0x1800582ed  mov     rax, [rax]
0x1800582f0  mov     rcx, rax; lpFileName
0x1800582f3  call    cs:__imp_GetFileAttributesW
0x1800582fa  nop     dword ptr [rax+rax+00h]
0x1800582ff  mov     ebx, eax
0x180058301  lea     rcx, [rbp+57h+SourceString]
0x180058305  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005830a  cmp     ebx, 0FFFFFFFFh
0x18005830d  jnz     short loc_18005832C
0x18005830f  call    cs:__imp_GetLastError
0x180058316  nop     dword ptr [rax+rax+00h]
0x18005831b  lea     ecx, [rax-2]
0x18005831e  cmp     ecx, 1
0x180058321  ja      loc_18005852C
0x180058327  jmp     loc_180058501
0x18005832c  xor     r8d, r8d
0x18005832f  lea     rsi, aWinmd; "winmd"
0x180058336  mov     rdx, rsi
0x180058339  lea     r14, aCiCataloghint_0; "$CI.CATALOGHINT"
0x180058340  mov     rcx, r14
0x180058343  call    __std_find_trivial_1
0x180058348  mov     rbx, rax
0x18005834b  cmp     rax, rsi
0x18005834e  jz      loc_180058545
0x180058354  sub     rbx, r14
0x180058357  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18005835b  jz      loc_180058545
0x180058361  lea     r8, aWindowsSystem3_4; "Windows\\System32\\ntdll.dll"
0x180058368  mov     rdx, rdi; pszPathIn
0x18005836b  lea     rcx, [rbp+57h+SourceString]; Src
0x18005836f  call    ?CombineFilePath@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG0@Z; Vml::CombineFilePath(ushort const *,ushort const *)
0x180058374  nop
0x180058375  mov     [rbp+57h+var_90], r14
0x180058379  mov     [rbp+57h+var_88], rbx
0x18005837d  lea     rdx, [rbp+57h+var_90]
0x180058381  mov     rcx, rax; char *
0x180058384  call    ?HasExtendedAttribute@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$basic_zstring_view@D@wil@@@Z; HasExtendedAttribute(std::wstring const &,wil::basic_zstring_view<char>)
0x180058389  mov     bl, al
0x18005838b  lea     rcx, [rbp+57h+SourceString]
0x18005838f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180058394  test    bl, bl
0x180058396  jnz     loc_180058501
0x18005839c  lea     r8, aWindows; "Windows"
0x1800583a3  mov     rdx, rdi; pszPathIn
0x1800583a6  lea     rcx, [rbp+57h+Src]; Src
0x1800583aa  call    ?CombineFilePath@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG0@Z; Vml::CombineFilePath(ushort const *,ushort const *)
0x1800583af  nop
0x1800583b0  lea     rax, [rbp+57h+Src]
0x1800583b4  cmp     [rbp+57h+var_58], 7
0x1800583b9  cmova   rax, [rbp+57h+Src]
0x1800583be  cmp     word ptr [rax], 5Ch ; '\'
0x1800583c2  jz      short loc_180058426
0x1800583c4  mov     rcx, [rbp+57h+var_60]
0x1800583c8  mov     rax, 7FFFFFFFFFFFFFFEh
0x1800583d2  sub     rax, rcx
0x1800583d5  cmp     rax, 4
0x1800583d9  jb      loc_180058526
0x1800583df  lea     rax, [rbp+57h+Src]
0x1800583e3  cmp     [rbp+57h+var_58], 7
0x1800583e8  cmova   rax, [rbp+57h+Src]
0x1800583ed  mov     [rsp+0D0h+var_A0], rcx
0x1800583f2  mov     [rsp+0D0h+var_A8], rax
0x1800583f7  mov     qword ptr [rsp+0D0h+var_B0], 4
0x180058400  lea     r9, asc_180094C98; "\\\\?\\"
0x180058407  lea     rcx, [rbp+57h+SourceString]
0x18005840b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x180058410  lea     rdx, [rbp+57h+SourceString]
0x180058414  lea     rcx, [rbp+57h+Src]
0x180058418  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18005841d  lea     rcx, [rbp+57h+SourceString]
0x180058421  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180058426  lea     rax, aWindowsSystem3_7; "Windows\\System32\\catroot\\{F750E6C3-3"...
0x18005842d  mov     [rbp+57h+var_28], rax
0x180058431  lea     rax, aCat; "cat"
0x180058438  mov     [rbp+57h+var_30], rax
0x18005843c  mov     [rbp+57h+var_90], 1
0x180058444  lea     rax, [rbp+57h+var_30]
0x180058448  mov     [rbp+57h+var_88], rax
0x18005844c  mov     [rbp+57h+var_80], 1
0x180058454  lea     rax, [rbp+57h+var_28]
0x180058458  mov     [rbp+57h+var_78], rax
0x18005845c  mov     byte ptr [rsp+0D0h+var_B0], 0
0x180058461  lea     r9, [rbp+57h+var_90]
0x180058465  lea     r8, [rbp+57h+var_80]
0x180058469  mov     rdx, rdi
0x18005846c  lea     rcx, [rbp+57h+SourceString]
0x180058470  call    ?FindFiles@@YA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@PEBGV?$span@QEBG$0?0@gsl@@1_N@Z; FindFiles(ushort const *,gsl::span<ushort const * const,-1>,gsl::span<ushort const * const,-1>,bool)
0x180058475  nop
0x180058476  mov     rbx, [rbp+57h+SourceString]
0x18005847a  mov     rdi, [rbp+57h+var_48]
0x18005847e  jmp     short loc_1800584E9
0x180058480  lea     rdx, [rbp+57h+Src]
0x180058484  cmp     [rbp+57h+var_58], 7
0x180058489  cmova   rdx, [rbp+57h+Src]
0x18005848e  cmp     qword ptr [rbx+18h], 7
0x180058493  jbe     short loc_18005849A
0x180058495  mov     rcx, [rbx]
0x180058498  jmp     short loc_18005849D
0x18005849a  mov     rcx, rbx; SourceString
0x18005849d  call    CiSetHintsForPackageCatalog2
0x1800584a2  cmp     eax, 0C000003Ah
0x1800584a7  jz      short loc_1800584E5
0x1800584a9  test    eax, eax
0x1800584ab  jz      short loc_1800584E5
0x1800584ad  cmp     qword ptr [rbx+18h], 7
0x1800584b2  jbe     short loc_1800584B9
0x1800584b4  mov     rdx, [rbx]
0x1800584b7  jmp     short loc_1800584BC
0x1800584b9  mov     rdx, rbx
0x1800584bc  mov     rcx, [rbp+5Fh]; this
0x1800584c0  mov     [rsp+0D0h+var_A8], rdx; char *
0x1800584c5  lea     rdx, aWs; "%ws"
0x1800584cc  mov     qword ptr [rsp+0D0h+var_B0], rdx; int
0x1800584d1  mov     r9d, eax; char *
0x1800584d4  lea     r8, aOnecoreVmCompu_17; "onecore\\vm\\compute\\dll\\lib\\storage"...
0x1800584db  mov     edx, 197h; void *
0x1800584e0  call    ?Log_NtStatusMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_NtStatusMsg(void *,uint,char const *,long,char const *,...)
0x1800584e5  add     rbx, 20h ; ' '
0x1800584e9  cmp     rbx, rdi
0x1800584ec  jnz     short loc_180058480
0x1800584ee  lea     rcx, [rbp+57h+SourceString]
0x1800584f2  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800584f7  nop
0x1800584f8  lea     rcx, [rbp+57h+Src]
0x1800584fc  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180058501  mov     rcx, [rbp+57h+var_20]
0x180058505  xor     rcx, rsp; StackCookie
0x180058508  call    __security_check_cookie
0x18005850d  lea     r11, [rsp+0D0h+var_10]
0x180058515  mov     rbx, [r11+28h]
0x180058519  mov     rsi, [r11+30h]
0x18005851d  mov     rsp, r11
0x180058520  pop     r14
0x180058522  pop     rdi
0x180058523  pop     rbp
0x180058524  retn
0x180058526  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
0x18005852c  mov     rcx, [rbp+5Fh]; this
0x180058530  mov     r9d, eax; char *
0x180058533  lea     r8, aOnecoreVmCompu_17; "onecore\\vm\\compute\\dll\\lib\\storage"...
0x18005853a  mov     edx, 179h; void *
0x18005853f  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180058545  mov     rcx, [rbp+5Fh]; this
0x180058549  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180058550  mov     edx, 0EBh; void *
0x180058555  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
