# AvhdUtilities::DeleteAutomaticVhd(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x1400ecd78`
- end: `0x1400ecec5`
- name: `?DeleteAutomaticVhd@AvhdUtilities@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `333`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1400ecce8`

## callees

- `0x14003c108`
- `0x14003d828`
- `0x140083990`
- `0x1400ba144`
- `0x1400ecd78`
- `0x1401aae8c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400ecde9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400ece54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400ecde9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400ece54`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1400ecdcd`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1400ece38`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1400ece8b`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1400ecdcd`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1400ece38`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1400ece8b`

## string_xrefs

- `0x1400ecd97`: `onecore\vm\common\avhd\avhdutilities.cpp`
- `0x1400ece02`: `onecore\vm\common\avhd\avhdutilities.cpp`
- `0x1400ece6d`: `onecore\vm\common\avhd\avhdutilities.cpp`
- `0x1400ecea0`: `onecore\vm\common\avhd\avhdutilities.cpp`

## pseudocode

```c
__int64 __fastcall AvhdUtilities::DeleteAutomaticVhd(void **Src)
{
  int IsAutomaticVhd; // eax
  const WCHAR *v3; // rcx
  BOOL v4; // ebx
  DWORD LastError; // eax
  const WCHAR *v6; // rcx
  BOOL v7; // ebx
  DWORD v8; // eax
  const char *v9; // r9
  __int64 result; // rax
  LPCWSTR lpFileName[3]; // [rsp+20h] [rbp-28h] BYREF
  unsigned __int64 v12; // [rsp+38h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  IsAutomaticVhd = AvhdUtilities::IsAutomaticVhd();
  try
  {
    if ( !IsAutomaticVhd )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x24E,
        (unsigned int)"onecore\\vm\\common\\avhd\\avhdutilities.cpp",
        (const char *)0x57,
        (unsigned int)lpFileName[0]);
    std::operator+<unsigned short>(lpFileName, Src, L".rct");
    v3 = (const WCHAR *)lpFileName;
    if ( v12 > 7 )
      v3 = lpFileName[0];
    v4 = DeleteFileW(v3);
    std::wstring::_Tidy_deallocate(lpFileName);
    if ( !v4 )
    {
      LastError = GetLastError();
      if ( LastError != 2 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x260,
          (unsigned int)"onecore\\vm\\common\\avhd\\avhdutilities.cpp",
          (const char *)LastError,
          (unsigned int)lpFileName[0]);
    }
    std::operator+<unsigned short>(lpFileName, Src, L".mrt");
    v6 = (const WCHAR *)lpFileName;
    if ( v12 > 7 )
      v6 = lpFileName[0];
    v7 = DeleteFileW(v6);
    std::wstring::_Tidy_deallocate(lpFileName);
    if ( !v7 )
    {
      v8 = GetLastError();
      if ( v8 != 2 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x26C,
          (unsigned int)"onecore\\vm\\common\\avhd\\avhdutilities.cpp",
          (const char *)v8,
          (unsigned int)lpFileName[0]);
    }
    if ( (unsigned __int64)Src[3] > 7 )
      Src = (void **)*Src;
    if ( !DeleteFileW((LPCWSTR)Src) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x270,
        (unsigned int)"onecore\\vm\\common\\avhd\\avhdutilities.cpp",
        v9);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x273,
                           (unsigned int)"onecore\\vm\\common\\avhd\\avhdutilities.cpp",
                           v9);
  }
  return result;
}

```

## disassembly

```asm
0x1400ecd78  mov     [rsp+arg_0], rbx
0x1400ecd7d  push    rdi
0x1400ecd7e  sub     rsp, 40h
0x1400ecd82  mov     rdi, rcx
0x1400ecd85  call    ?IsAutomaticVhd@AvhdUtilities@@SAHAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; AvhdUtilities::IsAutomaticVhd(std::wstring const &)
0x1400ecd8a  test    eax, eax
0x1400ecd8c  jnz     short loc_1400ECDA8
0x1400ecd8e  mov     rcx, [rsp+48h]; this
0x1400ecd93  lea     r9d, [rax+57h]; char *
0x1400ecd97  lea     r8, aOnecoreVmCommo_109; "onecore\\vm\\common\\avhd\\avhdutilitie"...
0x1400ecd9e  mov     edx, 24Eh; void *
0x1400ecda3  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1400ecda8  lea     r8, aRct; ".rct"
0x1400ecdaf  mov     rdx, rdi; Src
0x1400ecdb2  lea     rcx, [rsp+48h+lpFileName]; void *
0x1400ecdb7  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x1400ecdbc  lea     rcx, [rsp+48h+lpFileName]
0x1400ecdc1  cmp     [rsp+48h+var_10], 7
0x1400ecdc7  cmova   rcx, [rsp+48h+lpFileName]; lpFileName
0x1400ecdcd  call    cs:__imp_DeleteFileW
0x1400ecdd4  nop     dword ptr [rax+rax+00h]
0x1400ecdd9  mov     ebx, eax
0x1400ecddb  lea     rcx, [rsp+48h+lpFileName]
0x1400ecde0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400ecde5  test    ebx, ebx
0x1400ecde7  jnz     short loc_1400ECE13
0x1400ecde9  call    cs:__imp_GetLastError
0x1400ecdf0  nop     dword ptr [rax+rax+00h]
0x1400ecdf5  cmp     eax, 2
0x1400ecdf8  jz      short loc_1400ECE13
0x1400ecdfa  mov     rcx, [rsp+48h]; this
0x1400ecdff  mov     r9d, eax; char *
0x1400ece02  lea     r8, aOnecoreVmCommo_109; "onecore\\vm\\common\\avhd\\avhdutilitie"...
0x1400ece09  mov     edx, 260h; void *
0x1400ece0e  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1400ece13  lea     r8, aMrt; ".mrt"
0x1400ece1a  mov     rdx, rdi; Src
0x1400ece1d  lea     rcx, [rsp+48h+lpFileName]; void *
0x1400ece22  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x1400ece27  lea     rcx, [rsp+48h+lpFileName]
0x1400ece2c  cmp     [rsp+48h+var_10], 7
0x1400ece32  cmova   rcx, [rsp+48h+lpFileName]; lpFileName
0x1400ece38  call    cs:__imp_DeleteFileW
0x1400ece3f  nop     dword ptr [rax+rax+00h]
0x1400ece44  mov     ebx, eax
0x1400ece46  lea     rcx, [rsp+48h+lpFileName]
0x1400ece4b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400ece50  test    ebx, ebx
0x1400ece52  jnz     short loc_1400ECE7E
0x1400ece54  call    cs:__imp_GetLastError
0x1400ece5b  nop     dword ptr [rax+rax+00h]
0x1400ece60  cmp     eax, 2
0x1400ece63  jz      short loc_1400ECE7E
0x1400ece65  mov     rcx, [rsp+48h]; this
0x1400ece6a  mov     r9d, eax; char *
0x1400ece6d  lea     r8, aOnecoreVmCommo_109; "onecore\\vm\\common\\avhd\\avhdutilitie"...
0x1400ece74  mov     edx, 26Ch; void *
0x1400ece79  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1400ece7e  cmp     qword ptr [rdi+18h], 7
0x1400ece83  jbe     short loc_1400ECE88
0x1400ece85  mov     rdi, [rdi]
0x1400ece88  mov     rcx, rdi; lpFileName
0x1400ece8b  call    cs:__imp_DeleteFileW
0x1400ece92  nop     dword ptr [rax+rax+00h]
0x1400ece97  mov     rcx, [rsp+48h]; this
0x1400ece9c  test    eax, eax
0x1400ece9e  jnz     short loc_1400ECEB1
0x1400ecea0  lea     r8, aOnecoreVmCommo_109; "onecore\\vm\\common\\avhd\\avhdutilitie"...
0x1400ecea7  mov     edx, 270h; void *
0x1400eceac  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400eceb1  xor     eax, eax
0x1400eceb3  jmp     short loc_1400ECEB9
0x1400eceb5  mov     eax, [rsp+48h+arg_8]
0x1400eceb9  mov     rbx, [rsp+48h+arg_0]
0x1400ecebe  add     rsp, 40h
0x1400ecec2  pop     rdi
0x1400ecec3  retn
```
