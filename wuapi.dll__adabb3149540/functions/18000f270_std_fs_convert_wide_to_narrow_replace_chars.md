# __std_fs_convert_wide_to_narrow_replace_chars

- ea: `0x18000f270`
- end: `0x18000f353`
- name: `__std_fs_convert_wide_to_narrow_replace_chars`
- size: `227`
- prototype: `__int64 __fastcall(UINT CodePage, LPCWCH lpWideCharStr, int cchWideChar, LPSTR lpMultiByteStr, int)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800080d4`

## callees

- `0x18000f270`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f2d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f31f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f2d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f31f`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000f2c8`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000f311`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000f2c8`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000f311`

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
0x18000f270  mov     rax, rsp
0x18000f273  mov     [rax+8], rbx
0x18000f277  mov     [rax+10h], rbp
0x18000f27b  mov     [rax+18h], rsi
0x18000f27f  mov     [rax+20h], rdi
0x18000f283  push    r14
0x18000f285  sub     rsp, 50h
0x18000f289  mov     r14d, [rsp+58h+arg_20]
0x18000f291  mov     rbx, r9
0x18000f294  mov     qword ptr [rax-20h], 0
0x18000f29c  mov     r9d, r8d; cchWideChar
0x18000f29f  mov     qword ptr [rax-28h], 0
0x18000f2a7  mov     edi, r8d
0x18000f2aa  mov     r8, rdx; lpWideCharStr
0x18000f2ad  mov     [rax-30h], r14d
0x18000f2b1  mov     rsi, rdx
0x18000f2b4  mov     [rsp+58h+var_18], 0
0x18000f2bd  mov     edx, 400h; dwFlags
0x18000f2c2  mov     [rax-38h], rbx
0x18000f2c6  mov     ebp, ecx
0x18000f2c8  call    cs:__imp_WideCharToMultiByte
0x18000f2ce  mov     dword ptr [rsp+58h+var_18], eax
0x18000f2d2  test    eax, eax
0x18000f2d4  jnz     short loc_18000F2DE
0x18000f2d6  call    cs:__imp_GetLastError
0x18000f2dc  jmp     short loc_18000F2E0
0x18000f2de  xor     eax, eax
0x18000f2e0  mov     dword ptr [rsp+58h+var_18+4], eax
0x18000f2e4  cmp     eax, 3ECh
0x18000f2e9  jnz     short loc_18000F333
0x18000f2eb  mov     [rsp+58h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x18000f2f4  mov     r9d, edi; cchWideChar
0x18000f2f7  mov     [rsp+58h+lpDefaultChar], 0; lpDefaultChar
0x18000f300  mov     r8, rsi; lpWideCharStr
0x18000f303  mov     [rsp+58h+cbMultiByte], r14d; cbMultiByte
0x18000f308  xor     edx, edx; dwFlags
0x18000f30a  mov     ecx, ebp; CodePage
0x18000f30c  mov     [rsp+58h+lpMultiByteStr], rbx; lpMultiByteStr
0x18000f311  call    cs:__imp_WideCharToMultiByte
0x18000f317  mov     dword ptr [rsp+58h+var_18], eax
0x18000f31b  test    eax, eax
0x18000f31d  jnz     short loc_18000F32B
0x18000f31f  call    cs:__imp_GetLastError
0x18000f325  mov     dword ptr [rsp+58h+var_18+4], eax
0x18000f329  jmp     short loc_18000F333
0x18000f32b  mov     dword ptr [rsp+58h+var_18+4], 0
0x18000f333  mov     rax, [rsp+58h+var_18]
0x18000f338  mov     rbx, [rsp+58h+arg_0]
0x18000f33d  mov     rbp, [rsp+58h+arg_8]
0x18000f342  mov     rsi, [rsp+58h+arg_10]
0x18000f347  mov     rdi, [rsp+58h+arg_18]
0x18000f34c  add     rsp, 50h
0x18000f350  pop     r14
0x18000f352  retn
```
