# StringCbPrintfW

- ea: `0x1800049c8`
- end: `0x180004a25`
- name: `StringCbPrintfW`
- size: `93`
- prototype: `HRESULT(STRSAFE_LPWSTR pszDest, size_t cbDest, STRSAFE_LPCWSTR pszFormat, ...)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180005140`
- `0x18000570c`

## callees

- `0x1800049c8`
- `0x180004bb8`

## pseudocode

```c
HRESULT StringCbPrintfW(STRSAFE_LPWSTR pszDest, size_t cbDest, STRSAFE_LPCWSTR pszFormat, ...)
{
  HRESULT v3; // edx
  va_list va; // [rsp+68h] [rbp+20h] BYREF

  va_start(va, pszFormat);
  if ( !(cbDest >> 1) )
    return -2147024809;
  if ( cbDest >> 1 <= 0x7FFFFFFF )
    return StringVPrintfWorkerW(pszDest, cbDest >> 1, (size_t *)pszFormat, pszFormat, va);
  v3 = -2147024809;
  *pszDest = 0;
  return v3;
}

```

## disassembly

```asm
0x1800049c8  mov     [rsp+arg_10], r8
0x1800049cd  mov     qword ptr [rsp+arg_18], r9
0x1800049d2  sub     rsp, 48h
0x1800049d6  mov     rax, rdx
0x1800049d9  shr     rax, 1
0x1800049dc  jz      short loc_180004A0F
0x1800049de  cmp     rax, 7FFFFFFFh
0x1800049e4  jbe     short loc_1800049ED
0x1800049e6  mov     edx, 80070057h
0x1800049eb  jmp     short loc_180004A19
0x1800049ed  lea     rdx, [rsp+48h+arg_18]
0x1800049f2  mov     [rsp+48h+var_18], 0
0x1800049fb  mov     [rsp+48h+argList], rdx; argList
0x180004a00  mov     r9, r8; pszFormat
0x180004a03  mov     rdx, rax; cchDest
0x180004a06  call    StringVPrintfWorkerW
0x180004a0b  mov     edx, eax
0x180004a0d  jmp     short loc_180004A1E
0x180004a0f  mov     edx, 80070057h
0x180004a14  test    rax, rax
0x180004a17  jz      short loc_180004A1E
0x180004a19  xor     eax, eax
0x180004a1b  mov     [rcx], ax
0x180004a1e  mov     eax, edx
0x180004a20  add     rsp, 48h
0x180004a24  retn
```
