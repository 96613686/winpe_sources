# StringCopyWorkerW

- ea: `0x180001170`
- end: `0x1800011bd`
- name: `StringCopyWorkerW`
- size: `77`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180011c1c`
- `0x18001257c`

## callees

- `0x180001170`

## pseudocode

```c
HRESULT __stdcall StringCopyWorkerW(
        STRSAFE_LPWSTR pszDest,
        size_t cchDest,
        size_t *pcchNewDestLength,
        STRSAFE_PCNZWCH pszSrc,
        size_t cchToCopy)
{
  size_t i; // r10
  STRSAFE_LPWSTR v8; // rdx
  HRESULT result; // eax

  for ( i = cchDest; i; --i )
  {
    if ( !cchToCopy )
      break;
    if ( !*pszSrc )
      break;
    *pszDest++ = *pszSrc++;
    --cchToCopy;
  }
  v8 = pszDest - 1;
  result = -2147024774;
  if ( i )
  {
    v8 = pszDest;
    result = 0;
  }
  *v8 = 0;
  return result;
}

```

## disassembly

```asm
0x180001170  mov     r10, rdx
0x180001173  mov     r11, rcx
0x180001176  test    rdx, rdx
0x180001179  jz      short loc_1800011A4
0x18000117b  mov     rax, [rsp+cchToCopy]
0x180001180  test    rax, rax
0x180001183  jz      short loc_1800011A4
0x180001185  movzx   r8d, word ptr [r9]
0x180001189  test    r8w, r8w
0x18000118d  jz      short loc_1800011A4
0x18000118f  mov     [r11], r8w
0x180001193  add     r9, 2
0x180001197  add     r11, 2
0x18000119b  dec     rax
0x18000119e  sub     r10, 1
0x1800011a2  jnz     short loc_180001180
0x1800011a4  xor     ecx, ecx
0x1800011a6  lea     rdx, [r11-2]
0x1800011aa  test    r10, r10
0x1800011ad  mov     eax, 8007007Ah
0x1800011b2  cmovnz  rdx, r11
0x1800011b6  cmovnz  eax, ecx
0x1800011b9  mov     [rdx], cx
0x1800011bc  retn
```
