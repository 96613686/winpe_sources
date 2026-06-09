# StringCchCopyW

- ea: `0x180004ab8`
- end: `0x180004af5`
- name: `StringCchCopyW`
- size: `61`
- prototype: `HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszSrc)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180005450`
- `0x180007e34`
- `0x180008260`
- `0x180009d80`

## callees

- `0x180004ab8`
- `0x180004b60`

## pseudocode

```c
HRESULT __stdcall StringCchCopyW(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszSrc)
{
  HRESULT v3; // edx
  size_t v5; // [rsp+20h] [rbp-18h]

  if ( !cchDest )
    return -2147024809;
  if ( cchDest <= 0x7FFFFFFF )
    return StringCopyWorkerW(pszDest, cchDest, (size_t *)pszSrc, pszSrc, v5);
  v3 = -2147024809;
  *pszDest = 0;
  return v3;
}

```

## disassembly

```asm
0x180004ab8  sub     rsp, 38h
0x180004abc  mov     rax, rdx
0x180004abf  test    rdx, rdx
0x180004ac2  jz      short loc_180004ADF
0x180004ac4  cmp     rax, 7FFFFFFFh
0x180004aca  jbe     short loc_180004AD3
0x180004acc  mov     edx, 80070057h; cchDest
0x180004ad1  jmp     short loc_180004AE9
0x180004ad3  mov     r9, r8; pszSrc
0x180004ad6  call    StringCopyWorkerW
0x180004adb  mov     edx, eax
0x180004add  jmp     short loc_180004AEE
0x180004adf  mov     edx, 80070057h
0x180004ae4  test    rax, rax
0x180004ae7  jz      short loc_180004AEE
0x180004ae9  xor     eax, eax
0x180004aeb  mov     [rcx], ax
0x180004aee  mov     eax, edx
0x180004af0  add     rsp, 38h
0x180004af4  retn
```
