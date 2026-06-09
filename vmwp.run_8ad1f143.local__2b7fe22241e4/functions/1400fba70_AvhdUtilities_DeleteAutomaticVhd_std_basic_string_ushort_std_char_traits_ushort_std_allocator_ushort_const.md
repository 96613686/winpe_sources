# AvhdUtilities::DeleteAutomaticVhd(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x1400fba70`
- end: `0x1400fbbbd`
- name: `?DeleteAutomaticVhd@AvhdUtilities@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `333`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1400fb9e0`

## callees

- `0x14002fba8`
- `0x140031ca8`
- `0x14005b648`
- `0x14009d7cc`
- `0x1400fba70`
- `0x1401bbdac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400fbae1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400fbb4c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400fbae1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400fbb4c`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1400fbac5`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1400fbb30`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1400fbb83`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1400fbac5`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1400fbb30`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1400fbb83`

## string_xrefs

- `0x1400fba8f`: `onecore\vm\common\avhd\avhdutilities.cpp`
- `0x1400fbafa`: `onecore\vm\common\avhd\avhdutilities.cpp`
- `0x1400fbb65`: `onecore\vm\common\avhd\avhdutilities.cpp`
- `0x1400fbb98`: `onecore\vm\common\avhd\avhdutilities.cpp`

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
0x1400fba70  mov     [rsp+arg_0], rbx
0x1400fba75  push    rdi
0x1400fba76  sub     rsp, 40h
0x1400fba7a  mov     rdi, rcx
0x1400fba7d  call    ?IsAutomaticVhd@AvhdUtilities@@SAHAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; AvhdUtilities::IsAutomaticVhd(std::wstring const &)
0x1400fba82  test    eax, eax
0x1400fba84  jnz     short loc_1400FBAA0
0x1400fba86  mov     rcx, [rsp+48h]; this
0x1400fba8b  lea     r9d, [rax+57h]; char *
0x1400fba8f  lea     r8, aOnecoreVmCommo_109; "onecore\\vm\\common\\avhd\\avhdutilitie"...
0x1400fba96  mov     edx, 24Eh; void *
0x1400fba9b  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1400fbaa0  lea     r8, aRct; ".rct"
0x1400fbaa7  mov     rdx, rdi; Src
0x1400fbaaa  lea     rcx, [rsp+48h+lpFileName]; void *
0x1400fbaaf  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x1400fbab4  lea     rcx, [rsp+48h+lpFileName]
0x1400fbab9  cmp     [rsp+48h+var_10], 7
0x1400fbabf  cmova   rcx, [rsp+48h+lpFileName]; lpFileName
0x1400fbac5  call    cs:__imp_DeleteFileW
0x1400fbacc  nop     dword ptr [rax+rax+00h]
0x1400fbad1  mov     ebx, eax
0x1400fbad3  lea     rcx, [rsp+48h+lpFileName]
0x1400fbad8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400fbadd  test    ebx, ebx
0x1400fbadf  jnz     short loc_1400FBB0B
0x1400fbae1  call    cs:__imp_GetLastError
0x1400fbae8  nop     dword ptr [rax+rax+00h]
0x1400fbaed  cmp     eax, 2
0x1400fbaf0  jz      short loc_1400FBB0B
0x1400fbaf2  mov     rcx, [rsp+48h]; this
0x1400fbaf7  mov     r9d, eax; char *
0x1400fbafa  lea     r8, aOnecoreVmCommo_109; "onecore\\vm\\common\\avhd\\avhdutilitie"...
0x1400fbb01  mov     edx, 260h; void *
0x1400fbb06  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1400fbb0b  lea     r8, aMrt; ".mrt"
0x1400fbb12  mov     rdx, rdi; Src
0x1400fbb15  lea     rcx, [rsp+48h+lpFileName]; void *
0x1400fbb1a  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x1400fbb1f  lea     rcx, [rsp+48h+lpFileName]
0x1400fbb24  cmp     [rsp+48h+var_10], 7
0x1400fbb2a  cmova   rcx, [rsp+48h+lpFileName]; lpFileName
0x1400fbb30  call    cs:__imp_DeleteFileW
0x1400fbb37  nop     dword ptr [rax+rax+00h]
0x1400fbb3c  mov     ebx, eax
0x1400fbb3e  lea     rcx, [rsp+48h+lpFileName]
0x1400fbb43  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400fbb48  test    ebx, ebx
0x1400fbb4a  jnz     short loc_1400FBB76
0x1400fbb4c  call    cs:__imp_GetLastError
0x1400fbb53  nop     dword ptr [rax+rax+00h]
0x1400fbb58  cmp     eax, 2
0x1400fbb5b  jz      short loc_1400FBB76
0x1400fbb5d  mov     rcx, [rsp+48h]; this
0x1400fbb62  mov     r9d, eax; char *
0x1400fbb65  lea     r8, aOnecoreVmCommo_109; "onecore\\vm\\common\\avhd\\avhdutilitie"...
0x1400fbb6c  mov     edx, 26Ch; void *
0x1400fbb71  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1400fbb76  cmp     qword ptr [rdi+18h], 7
0x1400fbb7b  jbe     short loc_1400FBB80
0x1400fbb7d  mov     rdi, [rdi]
0x1400fbb80  mov     rcx, rdi; lpFileName
0x1400fbb83  call    cs:__imp_DeleteFileW
0x1400fbb8a  nop     dword ptr [rax+rax+00h]
0x1400fbb8f  mov     rcx, [rsp+48h]; this
0x1400fbb94  test    eax, eax
0x1400fbb96  jnz     short loc_1400FBBA9
0x1400fbb98  lea     r8, aOnecoreVmCommo_109; "onecore\\vm\\common\\avhd\\avhdutilitie"...
0x1400fbb9f  mov     edx, 270h; void *
0x1400fbba4  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400fbba9  xor     eax, eax
0x1400fbbab  jmp     short loc_1400FBBB1
0x1400fbbad  mov     eax, [rsp+48h+arg_8]
0x1400fbbb1  mov     rbx, [rsp+48h+arg_0]
0x1400fbbb6  add     rsp, 40h
0x1400fbbba  pop     rdi
0x1400fbbbb  retn
```
