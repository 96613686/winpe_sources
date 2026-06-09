# __std_fs_convert_wide_to_narrow_replace_chars

- ea: `0x18000f220`
- end: `0x18000f303`
- name: `__std_fs_convert_wide_to_narrow_replace_chars`
- size: `227`
- prototype: `__int64 __fastcall(UINT CodePage, LPCWCH lpWideCharStr, int cchWideChar, LPSTR lpMultiByteStr, int)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180007280`

## callees

- `0x18000f220`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f286`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f2cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f286`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f2cf`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000f278`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000f2c1`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000f278`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000f2c1`

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
  __int64 v11; // [rsp+40h] [rbp-18h]

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
0x18000f220  mov     rax, rsp
0x18000f223  mov     [rax+8], rbx
0x18000f227  mov     [rax+10h], rbp
0x18000f22b  mov     [rax+18h], rsi
0x18000f22f  mov     [rax+20h], rdi
0x18000f233  push    r14
0x18000f235  sub     rsp, 50h
0x18000f239  mov     r14d, [rsp+58h+arg_20]
0x18000f241  mov     rbx, r9
0x18000f244  mov     qword ptr [rax-20h], 0
0x18000f24c  mov     r9d, r8d; cchWideChar
0x18000f24f  mov     qword ptr [rax-28h], 0
0x18000f257  mov     edi, r8d
0x18000f25a  mov     r8, rdx; lpWideCharStr
0x18000f25d  mov     [rax-30h], r14d
0x18000f261  mov     rsi, rdx
0x18000f264  mov     [rsp+58h+var_18], 0
0x18000f26d  mov     edx, 400h; dwFlags
0x18000f272  mov     [rax-38h], rbx
0x18000f276  mov     ebp, ecx
0x18000f278  call    cs:__imp_WideCharToMultiByte
0x18000f27e  mov     dword ptr [rsp+58h+var_18], eax
0x18000f282  test    eax, eax
0x18000f284  jnz     short loc_18000F28E
0x18000f286  call    cs:__imp_GetLastError
0x18000f28c  jmp     short loc_18000F290
0x18000f28e  xor     eax, eax
0x18000f290  mov     dword ptr [rsp+58h+var_18+4], eax
0x18000f294  cmp     eax, 3ECh
0x18000f299  jnz     short loc_18000F2E3
0x18000f29b  mov     [rsp+58h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x18000f2a4  mov     r9d, edi; cchWideChar
0x18000f2a7  mov     [rsp+58h+lpDefaultChar], 0; lpDefaultChar
0x18000f2b0  mov     r8, rsi; lpWideCharStr
0x18000f2b3  mov     [rsp+58h+cbMultiByte], r14d; cbMultiByte
0x18000f2b8  xor     edx, edx; dwFlags
0x18000f2ba  mov     ecx, ebp; CodePage
0x18000f2bc  mov     [rsp+58h+lpMultiByteStr], rbx; lpMultiByteStr
0x18000f2c1  call    cs:__imp_WideCharToMultiByte
0x18000f2c7  mov     dword ptr [rsp+58h+var_18], eax
0x18000f2cb  test    eax, eax
0x18000f2cd  jnz     short loc_18000F2DB
0x18000f2cf  call    cs:__imp_GetLastError
0x18000f2d5  mov     dword ptr [rsp+58h+var_18+4], eax
0x18000f2d9  jmp     short loc_18000F2E3
0x18000f2db  mov     dword ptr [rsp+58h+var_18+4], 0
0x18000f2e3  mov     rax, [rsp+58h+var_18]
0x18000f2e8  mov     rbx, [rsp+58h+arg_0]
0x18000f2ed  mov     rbp, [rsp+58h+arg_8]
0x18000f2f2  mov     rsi, [rsp+58h+arg_10]
0x18000f2f7  mov     rdi, [rsp+58h+arg_18]
0x18000f2fc  add     rsp, 50h
0x18000f300  pop     r14
0x18000f302  retn
```
