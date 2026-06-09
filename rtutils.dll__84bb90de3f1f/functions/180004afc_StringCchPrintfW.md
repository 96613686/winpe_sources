# StringCchPrintfW

- ea: `0x180004afc`
- end: `0x180004b59`
- name: `StringCchPrintfW`
- size: `93`
- prototype: `HRESULT(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszFormat, ...)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180004cc0`
- `0x180008ab0`
- `0x1800092a0`
- `0x18000a1d8`

## callees

- `0x180004afc`
- `0x180004bb8`

## pseudocode

```c
HRESULT StringCchPrintfW(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszFormat, ...)
{
  HRESULT v3; // edx
  va_list va; // [rsp+68h] [rbp+20h] BYREF

  va_start(va, pszFormat);
  if ( !cchDest )
    return -2147024809;
  if ( cchDest <= 0x7FFFFFFF )
    return StringVPrintfWorkerW(pszDest, cchDest, (size_t *)pszFormat, pszFormat, va);
  v3 = -2147024809;
  *pszDest = 0;
  return v3;
}

```

## disassembly

```asm
0x180004afc  mov     [rsp+arg_10], r8
0x180004b01  mov     qword ptr [rsp+arg_18], r9
0x180004b06  sub     rsp, 48h
0x180004b0a  mov     rax, rdx
0x180004b0d  test    rdx, rdx
0x180004b10  jz      short loc_180004B43
0x180004b12  cmp     rax, 7FFFFFFFh
0x180004b18  jbe     short loc_180004B21
0x180004b1a  mov     edx, 80070057h
0x180004b1f  jmp     short loc_180004B4D
0x180004b21  lea     rdx, [rsp+48h+arg_18]
0x180004b26  mov     [rsp+48h+var_18], 0
0x180004b2f  mov     [rsp+48h+argList], rdx; argList
0x180004b34  mov     r9, r8; pszFormat
0x180004b37  mov     rdx, rax; cchDest
0x180004b3a  call    StringVPrintfWorkerW
0x180004b3f  mov     edx, eax
0x180004b41  jmp     short loc_180004B52
0x180004b43  mov     edx, 80070057h
0x180004b48  test    rax, rax
0x180004b4b  jz      short loc_180004B52
0x180004b4d  xor     eax, eax
0x180004b4f  mov     [rcx], ax
0x180004b52  mov     eax, edx
0x180004b54  add     rsp, 48h
0x180004b58  retn
```
