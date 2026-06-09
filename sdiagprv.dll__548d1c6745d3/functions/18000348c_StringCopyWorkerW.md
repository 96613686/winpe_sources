# StringCopyWorkerW

- ea: `0x18000348c`
- end: `0x1800034dd`
- name: `StringCopyWorkerW`
- size: `81`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180002840`
- `0x180002ce0`
- `0x180003350`
- `0x18000e7f4`
- `0x18000edd4`

## callees

- `0x18000348c`

## pseudocode

```c
HRESULT __stdcall StringCopyWorkerW(
        STRSAFE_LPWSTR pszDest,
        size_t cchDest,
        size_t *pcchNewDestLength,
        STRSAFE_PCNZWCH pszSrc,
        size_t cchToCopy)
{
  size_t i; // r8
  STRSAFE_LPWSTR v7; // rdx
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
  v7 = pszDest - 1;
  result = i == 0 ? 0x8007007A : 0;
  if ( i )
    v7 = pszDest;
  *v7 = 0;
  return result;
}

```

## disassembly

```asm
0x18000348c  xor     r10d, r10d
0x18000348f  mov     r8, rdx
0x180003492  test    rdx, rdx
0x180003495  jz      short loc_1800034BE
0x180003497  mov     rax, [rsp+cchToCopy]
0x18000349c  test    rax, rax
0x18000349f  jz      short loc_1800034BE
0x1800034a1  movzx   edx, word ptr [r9]
0x1800034a5  test    dx, dx
0x1800034a8  jz      short loc_1800034BE
0x1800034aa  mov     [rcx], dx
0x1800034ad  add     r9, 2
0x1800034b1  add     rcx, 2
0x1800034b5  dec     rax
0x1800034b8  sub     r8, 1
0x1800034bc  jnz     short loc_18000349C
0x1800034be  mov     rax, r8
0x1800034c1  lea     rdx, [rcx-2]
0x1800034c5  neg     rax
0x1800034c8  sbb     eax, eax
0x1800034ca  not     eax
0x1800034cc  and     eax, 8007007Ah
0x1800034d1  test    r8, r8
0x1800034d4  cmovnz  rdx, rcx
0x1800034d8  mov     [rdx], r10w
0x1800034dc  retn
```
