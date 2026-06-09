# StringExValidateSrcW

- ea: `0x180007694`
- end: `0x1800076c9`
- name: `StringExValidateSrcW`
- size: `53`
- prototype: `static HRESULT __stdcall(STRSAFE_PCNZWCH *ppszSrc, size_t *pcchToRead, const size_t cchMax, DWORD dwFlags)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800012b0`

## callees

- `0x180007694`

## pseudocode

```c
HRESULT __stdcall StringExValidateSrcW(
        STRSAFE_PCNZWCH *ppszSrc,
        size_t *pcchToRead,
        const size_t cchMax,
        DWORD dwFlags)
{
  HRESULT result; // eax

  if ( pcchToRead && *pcchToRead >= 0x7FFFFFFF )
    return -2147024809;
  result = 0;
  if ( (dwFlags & 0x100) != 0 && !*ppszSrc )
  {
    *ppszSrc = (STRSAFE_PCNZWCH)&dword_180009B54;
    if ( pcchToRead )
      *pcchToRead = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180007694  test    rdx, rdx
0x180007697  jz      short loc_1800076A8
0x180007699  cmp     qword ptr [rdx], 7FFFFFFFh
0x1800076a0  jb      short loc_1800076A8
0x1800076a2  mov     eax, 80070057h
0x1800076a7  retn
0x1800076a8  xor     eax, eax
0x1800076aa  bt      r9d, 8
0x1800076af  jnb     short locret_1800076C8
0x1800076b1  cmp     [rcx], rax
0x1800076b4  jnz     short locret_1800076C8
0x1800076b6  lea     r8, dword_180009B54
0x1800076bd  mov     [rcx], r8
0x1800076c0  test    rdx, rdx
0x1800076c3  jz      short locret_1800076C8
0x1800076c5  mov     [rdx], rax
0x1800076c8  retn
```
