# PathFileExistsDefExtW

- ea: `0x180001f40`
- end: `0x180001f82`
- name: `PathFileExistsDefExtW`
- size: `66`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001f40`
- `0x1800022c0`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCServerShareW` at `0x180001f5c`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCServerShareW` at `0x180001f5c`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCServerW` at `0x180001f4f`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCServerW` at `0x180001f4f`

## pseudocode

```c
__int64 __fastcall PathFileExistsDefExtW(WCHAR *lpFileName, int a2)
{
  if ( PathIsUNCServerW(lpFileName) || PathIsUNCServerShareW(lpFileName) )
    return 0;
  else
    return PathFileExistsDefExtAndAttributesW(lpFileName, a2, 0);
}

```

## disassembly

```asm
0x180001f40  mov     [rsp+arg_0], rbx
0x180001f45  push    rdi
0x180001f46  sub     rsp, 20h
0x180001f4a  mov     edi, edx
0x180001f4c  mov     rbx, rcx
0x180001f4f  call    cs:__imp_PathIsUNCServerW
0x180001f55  test    eax, eax
0x180001f57  jnz     short loc_180001F75
0x180001f59  mov     rcx, rbx; pszPath
0x180001f5c  call    cs:__imp_PathIsUNCServerShareW
0x180001f62  test    eax, eax
0x180001f64  jnz     short loc_180001F75
0x180001f66  xor     r8d, r8d
0x180001f69  mov     edx, edi
0x180001f6b  mov     rcx, rbx; lpFileName
0x180001f6e  call    PathFileExistsDefExtAndAttributesW
0x180001f73  jmp     short loc_180001F77
0x180001f75  xor     eax, eax
0x180001f77  mov     rbx, [rsp+28h+arg_0]
0x180001f7c  add     rsp, 20h
0x180001f80  pop     rdi
0x180001f81  retn
```
