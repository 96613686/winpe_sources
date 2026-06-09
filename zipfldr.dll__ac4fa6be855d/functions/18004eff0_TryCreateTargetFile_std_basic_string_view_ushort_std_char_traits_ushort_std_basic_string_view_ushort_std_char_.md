# TryCreateTargetFile(std::basic_string_view<ushort,std::char_traits<ushort>>,std::basic_string_view<ushort,std::char_traits<ushort>>,ushort const *,void * *)

- ea: `0x18004eff0`
- end: `0x18004f16b`
- name: `?TryCreateTargetFile@@YAJV?$basic_string_view@GU?$char_traits@G@std@@@std@@0PEBGPEAPEAX@Z`
- size: `379`
- prototype: `__int64 __fastcall(__int64, _QWORD *, __int64, _QWORD *)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x18004dfcc`
- `0x18004f174`

## callees

- `0x1800208f8`
- `0x180020cbc`
- `0x1800210b0`
- `0x18002abd0`
- `0x180036f50`
- `0x180048d3c`
- `0x180048dac`
- `0x18004eff0`

## import_xrefs

- `SHELL32!__imp_PathYetAnotherMakeUniqueName` at `0x18004f107`
- `SHELL32!__imp_PathYetAnotherMakeUniqueName` at `0x18004f107`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f0c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f0c7`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18004f0a7`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18004f0a7`

## pseudocode

```c
__int64 __fastcall TryCreateTargetFile(__int64 a1, _QWORD *a2, __int64 a3, _QWORD *a4)
{
  __int64 v7; // rax
  __int64 v8; // r8
  const WCHAR *v9; // rax
  HANDLE FileW; // rax
  signed int LastError; // eax
  unsigned int v13; // ebx
  const WCHAR *v14; // rax
  __int64 v15; // r8
  _BYTE v16[16]; // [rsp+48h] [rbp-270h] BYREF
  __int64 v17; // [rsp+58h] [rbp-260h]
  WCHAR pszUniqueName[264]; // [rsp+70h] [rbp-248h] BYREF

  std::wstring::wstring(v16, a1);
  v7 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v16);
  if ( *(_WORD *)(v7 + 2 * v17 - 2) != 92 )
    std::wstring::push_back(v16);
  std::wstring::_Append<unsigned short>(v16, *a2, a2[1]);
  v8 = -1;
  do
    ++v8;
  while ( *(_WORD *)(a3 + 2 * v8) );
  std::wstring::_Append<unsigned short>(v16, a3, v8);
  while ( 1 )
  {
    v9 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v16);
    FileW = CreateFileW(v9, 0xC0010000, 0, 0, 1u, 0x80u, 0);
    *a4 = FileW;
    if ( FileW != (HANDLE)-1LL )
    {
      std::wstring::_Tidy_deallocate(v16);
      return 0;
    }
    LastError = GetLastError();
    v13 = LastError;
    if ( LastError != 80 )
      break;
    v14 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v16);
    if ( !PathYetAnotherMakeUniqueName(pszUniqueName, v14, 0, 0) )
    {
      std::wstring::_Tidy_deallocate(v16);
      return 2147500037LL;
    }
    v15 = -1;
    do
      ++v15;
    while ( pszUniqueName[v15] );
    std::wstring::_Assign<unsigned short>(v16, pszUniqueName, v15);
  }
  if ( LastError > 0 )
    v13 = (unsigned __int16)LastError | 0x80070000;
  std::wstring::_Tidy_deallocate(v16);
  return v13;
}

```

## disassembly

```asm
0x18004eff0  push    rbx
0x18004eff2  push    rsi
0x18004eff3  push    rdi
0x18004eff4  push    r14
0x18004eff6  sub     rsp, 298h
0x18004effd  mov     rax, cs:__security_cookie
0x18004f004  xor     rax, rsp
0x18004f007  mov     [rsp+2B8h+var_38], rax
0x18004f00f  mov     rsi, r9
0x18004f012  mov     rdi, r8
0x18004f015  mov     rbx, rdx
0x18004f018  mov     rdx, rcx
0x18004f01b  lea     rcx, [rsp+2B8h+var_270]
0x18004f020  call    ??$?0V?$basic_string_view@GU?$char_traits@G@std@@@std@@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@1@AEBV?$allocator@G@1@@Z; std::wstring::wstring(std::basic_string_view<ushort> const &,std::allocator<ushort> const &)
0x18004f025  nop
0x18004f026  lea     rcx, [rsp+2B8h+var_270]
0x18004f02b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004f030  mov     edx, 5Ch ; '\'
0x18004f035  mov     rcx, [rsp+2B8h+var_260]
0x18004f03a  cmp     [rax+rcx*2-2], dx
0x18004f03f  jz      short loc_18004F04B
0x18004f041  lea     rcx, [rsp+2B8h+var_270]
0x18004f046  call    ?push_back@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXG@Z; std::wstring::push_back(ushort)
0x18004f04b  mov     r8, [rbx+8]
0x18004f04f  mov     rdx, [rbx]
0x18004f052  lea     rcx, [rsp+2B8h+var_270]
0x18004f057  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18004f05c  or      r8, 0FFFFFFFFFFFFFFFFh
0x18004f060  xor     r14d, r14d
0x18004f063  inc     r8
0x18004f066  cmp     [rdi+r8*2], r14w
0x18004f06b  jnz     short loc_18004F063
0x18004f06d  mov     rdx, rdi
0x18004f070  lea     rcx, [rsp+2B8h+var_270]
0x18004f075  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18004f07a  lea     rcx, [rsp+2B8h+var_270]
0x18004f07f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004f084  mov     rcx, rax; lpFileName
0x18004f087  mov     [rsp+2B8h+hTemplateFile], r14; hTemplateFile
0x18004f08c  mov     [rsp+2B8h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18004f094  mov     [rsp+2B8h+dwCreationDisposition], 1; dwCreationDisposition
0x18004f09c  xor     r9d, r9d; lpSecurityAttributes
0x18004f09f  xor     r8d, r8d; dwShareMode
0x18004f0a2  mov     edx, 0C0010000h; dwDesiredAccess
0x18004f0a7  call    cs:__imp_CreateFileW
0x18004f0ad  mov     [rsi], rax
0x18004f0b0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18004f0b4  jz      short loc_18004F0C7
0x18004f0b6  lea     rcx, [rsp+2B8h+var_270]
0x18004f0bb  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004f0c0  xor     eax, eax
0x18004f0c2  jmp     loc_18004F14D
0x18004f0c7  call    cs:__imp_GetLastError
0x18004f0cd  mov     ebx, eax
0x18004f0cf  cmp     eax, 50h ; 'P'
0x18004f0d2  jz      short loc_18004F0EF
0x18004f0d4  test    eax, eax
0x18004f0d6  jle     short loc_18004F0E1
0x18004f0d8  movzx   ebx, ax
0x18004f0db  or      ebx, 80070000h
0x18004f0e1  lea     rcx, [rsp+2B8h+var_270]
0x18004f0e6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004f0eb  mov     eax, ebx
0x18004f0ed  jmp     short loc_18004F14D
0x18004f0ef  lea     rcx, [rsp+2B8h+var_270]
0x18004f0f4  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004f0f9  mov     rdx, rax; pszPath
0x18004f0fc  xor     r9d, r9d; pszFileSpec
0x18004f0ff  xor     r8d, r8d; pszShort
0x18004f102  lea     rcx, [rsp+2B8h+pszUniqueName]; pszUniqueName
0x18004f107  call    cs:__imp_PathYetAnotherMakeUniqueName
0x18004f10d  test    eax, eax
0x18004f10f  jnz     short loc_18004F122
0x18004f111  lea     rcx, [rsp+2B8h+var_270]
0x18004f116  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004f11b  mov     eax, 80004005h
0x18004f120  jmp     short loc_18004F14D
0x18004f122  lea     rax, [rsp+2B8h+pszUniqueName]
0x18004f127  or      r8, 0FFFFFFFFFFFFFFFFh
0x18004f12b  inc     r8
0x18004f12e  cmp     [rax+r8*2], r14w
0x18004f133  jnz     short loc_18004F12B
0x18004f135  lea     rdx, [rsp+2B8h+pszUniqueName]
0x18004f13a  lea     rcx, [rsp+2B8h+var_270]
0x18004f13f  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18004f144  jmp     loc_18004F07A
0x18004f149  mov     eax, [rsp+2B8h+var_278]
0x18004f14d  mov     rcx, [rsp+2B8h+var_38]
0x18004f155  xor     rcx, rsp; StackCookie
0x18004f158  call    __security_check_cookie
0x18004f15d  add     rsp, 298h
0x18004f164  pop     r14
0x18004f166  pop     rdi
0x18004f167  pop     rsi
0x18004f168  pop     rbx
0x18004f169  retn
```
