# StringCchCopyNA

- ea: `0x18000d694`
- end: `0x18000d6d8`
- name: `StringCchCopyNA`
- size: `68`
- prototype: `HRESULT __stdcall(STRSAFE_LPSTR pszDest, size_t cchDest, STRSAFE_PCNZCH pszSrc, size_t cchToCopy)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000ca68`

## callees

- `0x18000d694`
- `0x18000d6e0`

## pseudocode

```c
HRESULT __stdcall StringCchCopyNA(STRSAFE_LPSTR pszDest, size_t cchDest, STRSAFE_PCNZCH pszSrc, size_t cchToCopy)
{
  HRESULT result; // eax

  if ( !cchDest )
    return -2147024809;
  if ( cchDest <= 0x7FFFFFFF && cchToCopy <= 0x7FFFFFFE )
    return StringCopyWorkerA(pszDest, cchDest, (size_t *)pszSrc, pszSrc, cchToCopy);
  result = -2147024809;
  *pszDest = 0;
  return result;
}

```

## disassembly

```asm
0x18000d694  sub     rsp, 38h
0x18000d698  test    rdx, rdx
0x18000d69b  jz      short loc_18000D6C5
0x18000d69d  cmp     rdx, 7FFFFFFFh
0x18000d6a4  jbe     short loc_18000D6AD
0x18000d6a6  mov     eax, 80070057h
0x18000d6ab  jmp     short loc_18000D6CF
0x18000d6ad  cmp     r9, 7FFFFFFEh
0x18000d6b4  ja      short loc_18000D6A6
0x18000d6b6  mov     [rsp+38h+cchToCopy], r9; cchToCopy
0x18000d6bb  mov     r9, r8; pszSrc
0x18000d6be  call    StringCopyWorkerA
0x18000d6c3  jmp     short loc_18000D6D2
0x18000d6c5  mov     eax, 80070057h
0x18000d6ca  test    rdx, rdx
0x18000d6cd  jz      short loc_18000D6D2
0x18000d6cf  mov     byte ptr [rcx], 0
0x18000d6d2  add     rsp, 38h
0x18000d6d6  retn
```
