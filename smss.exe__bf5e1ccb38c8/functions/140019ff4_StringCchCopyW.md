# StringCchCopyW

- ea: `0x140019ff4`
- end: `0x14001a031`
- name: `StringCchCopyW`
- size: `61`
- prototype: `HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszSrc)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140019a5c`

## callees

- `0x140019ff4`
- `0x14001a038`

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
0x140019ff4  sub     rsp, 38h
0x140019ff8  mov     rax, rdx
0x140019ffb  test    rdx, rdx
0x140019ffe  jz      short loc_14001A01B
0x14001a000  cmp     rax, 7FFFFFFFh
0x14001a006  jbe     short loc_14001A00F
0x14001a008  mov     edx, 80070057h; cchDest
0x14001a00d  jmp     short loc_14001A025
0x14001a00f  mov     r9, r8; pszSrc
0x14001a012  call    StringCopyWorkerW
0x14001a017  mov     edx, eax
0x14001a019  jmp     short loc_14001A02A
0x14001a01b  mov     edx, 80070057h
0x14001a020  test    rax, rax
0x14001a023  jz      short loc_14001A02A
0x14001a025  xor     eax, eax
0x14001a027  mov     [rcx], ax
0x14001a02a  mov     eax, edx
0x14001a02c  add     rsp, 38h
0x14001a030  retn
```
