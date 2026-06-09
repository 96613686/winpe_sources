# BuildPathHr

- ea: `0x180009800`
- end: `0x18000985a`
- name: `BuildPathHr`
- size: `90`
- prototype: `signed int __fastcall(const wchar_t *, const wchar_t *, wchar_t **)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000ed8c`

## callees

- `0x180009800`
- `0x18000a780`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009826`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000983e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009826`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000983e`

## pseudocode

```c
signed int __fastcall BuildPathHr(const wchar_t *a1, const wchar_t *a2, wchar_t **a3)
{
  signed int result; // eax
  wchar_t *v5; // rax
  signed int LastError; // eax
  bool v7; // sf

  if ( !a3 )
    return -2147024809;
  v5 = BuildPath(a1, a2);
  *a3 = v5;
  if ( v5 )
    return 0;
  LastError = GetLastError();
  v7 = LastError < 0;
  if ( LastError > 0 )
    v7 = 1;
  if ( !v7 )
    return -2147467259;
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180009800  push    rbx
0x180009802  sub     rsp, 20h
0x180009806  mov     rbx, r8
0x180009809  test    r8, r8
0x18000980c  jnz     short loc_180009815
0x18000980e  mov     eax, 80070057h
0x180009813  jmp     short loc_180009854
0x180009815  call    BuildPath
0x18000981a  mov     [rbx], rax
0x18000981d  test    rax, rax
0x180009820  jz      short loc_180009826
0x180009822  xor     eax, eax
0x180009824  jmp     short loc_180009854
0x180009826  call    cs:__imp_GetLastError
0x18000982c  mov     ebx, 80070000h
0x180009831  test    eax, eax
0x180009833  jle     short loc_18000983C
0x180009835  movzx   eax, ax
0x180009838  or      eax, ebx
0x18000983a  test    eax, eax
0x18000983c  jns     short loc_18000984F
0x18000983e  call    cs:__imp_GetLastError
0x180009844  test    eax, eax
0x180009846  jle     short loc_180009854
0x180009848  movzx   eax, ax
0x18000984b  or      eax, ebx
0x18000984d  jmp     short loc_180009854
0x18000984f  mov     eax, 80004005h
0x180009854  add     rsp, 20h
0x180009858  pop     rbx
0x180009859  retn
```
