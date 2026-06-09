# __std_fs_convert_wide_to_narrow_replace_chars

- ea: `0x180001d50`
- end: `0x180001e17`
- name: `__std_fs_convert_wide_to_narrow_replace_chars`
- size: `199`
- prototype: `__int64 __fastcall(UINT CodePage, LPCWCH lpWideCharStr, int cchWideChar, LPSTR lpMultiByteStr, int)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180007584`

## callees

- `0x180001d50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001daa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001df3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001daa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001df3`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180001d9c`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180001de5`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180001d9c`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180001de5`

## pseudocode

```c
__int64 __fastcall _std_fs_convert_wide_to_narrow_replace_chars(
        UINT CodePage,
        LPCWCH lpWideCharStr,
        int cchWideChar,
        LPSTR lpMultiByteStr,
        int cbMultiByte)
{
  DWORD LastError; // eax
  __int64 v11; // [rsp+40h] [rbp-38h]

  LODWORD(v11) = WideCharToMultiByte(CodePage, 0x400u, lpWideCharStr, cchWideChar, lpMultiByteStr, cbMultiByte, 0, 0);
  if ( (_DWORD)v11 )
    LastError = 0;
  else
    LastError = GetLastError();
  HIDWORD(v11) = LastError;
  if ( LastError == 1004 )
  {
    LODWORD(v11) = WideCharToMultiByte(CodePage, 0, lpWideCharStr, cchWideChar, lpMultiByteStr, cbMultiByte, 0, 0);
    if ( (_DWORD)v11 )
      HIDWORD(v11) = 0;
    else
      HIDWORD(v11) = GetLastError();
  }
  return v11;
}

```

## disassembly

```asm
0x180001d50  mov     rax, rsp
0x180001d53  push    rbx
0x180001d54  push    rbp
0x180001d55  push    rsi
0x180001d56  push    rdi
0x180001d57  push    r14
0x180001d59  sub     rsp, 50h
0x180001d5d  mov     r14d, [rsp+78h+arg_20]
0x180001d65  mov     rbx, r9
0x180001d68  mov     qword ptr [rax-40h], 0
0x180001d70  mov     r9d, r8d; cchWideChar
0x180001d73  mov     qword ptr [rax-48h], 0
0x180001d7b  mov     edi, r8d
0x180001d7e  mov     r8, rdx; lpWideCharStr
0x180001d81  mov     [rax-50h], r14d
0x180001d85  mov     rsi, rdx
0x180001d88  mov     [rsp+78h+var_38], 0
0x180001d91  mov     edx, 400h; dwFlags
0x180001d96  mov     [rax-58h], rbx
0x180001d9a  mov     ebp, ecx
0x180001d9c  call    cs:__imp_WideCharToMultiByte
0x180001da2  mov     dword ptr [rsp+78h+var_38], eax
0x180001da6  test    eax, eax
0x180001da8  jnz     short loc_180001DB2
0x180001daa  call    cs:__imp_GetLastError
0x180001db0  jmp     short loc_180001DB4
0x180001db2  xor     eax, eax
0x180001db4  mov     dword ptr [rsp+78h+var_38+4], eax
0x180001db8  cmp     eax, 3ECh
0x180001dbd  jnz     short loc_180001E07
0x180001dbf  mov     [rsp+78h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x180001dc8  mov     r9d, edi; cchWideChar
0x180001dcb  mov     [rsp+78h+lpDefaultChar], 0; lpDefaultChar
0x180001dd4  mov     r8, rsi; lpWideCharStr
0x180001dd7  mov     [rsp+78h+cbMultiByte], r14d; cbMultiByte
0x180001ddc  xor     edx, edx; dwFlags
0x180001dde  mov     ecx, ebp; CodePage
0x180001de0  mov     [rsp+78h+lpMultiByteStr], rbx; lpMultiByteStr
0x180001de5  call    cs:__imp_WideCharToMultiByte
0x180001deb  mov     dword ptr [rsp+78h+var_38], eax
0x180001def  test    eax, eax
0x180001df1  jnz     short loc_180001DFF
0x180001df3  call    cs:__imp_GetLastError
0x180001df9  mov     dword ptr [rsp+78h+var_38+4], eax
0x180001dfd  jmp     short loc_180001E07
0x180001dff  mov     dword ptr [rsp+78h+var_38+4], 0
0x180001e07  mov     rax, [rsp+78h+var_38]
0x180001e0c  add     rsp, 50h
0x180001e10  pop     r14
0x180001e12  pop     rdi
0x180001e13  pop     rsi
0x180001e14  pop     rbp
0x180001e15  pop     rbx
0x180001e16  retn
```
