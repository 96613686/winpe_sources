# StringCopyWorkerW

- ea: `0x180026b84`
- end: `0x180026bd5`
- name: `StringCopyWorkerW`
- size: `81`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180024070`
- `0x180026aa4`
- `0x180026c30`

## callees

- `0x180026b84`

## pseudocode

```c
HRESULT __stdcall StringCopyWorkerW(
        STRSAFE_LPWSTR pszDest,
        size_t cchDest,
        size_t *pcchNewDestLength,
        STRSAFE_PCNZWCH pszSrc,
        size_t cchToCopy)
{
  size_t v5; // r8
  __int64 i; // rax
  STRSAFE_LPWSTR v7; // rdx
  HRESULT result; // eax

  v5 = cchDest;
  for ( i = 2147483646; v5; --v5 )
  {
    if ( !i )
      break;
    if ( !*pszSrc )
      break;
    *pszDest++ = *pszSrc++;
    --i;
  }
  v7 = pszDest - 1;
  result = v5 == 0 ? 0x8007007A : 0;
  if ( v5 )
    v7 = pszDest;
  *v7 = 0;
  return result;
}

```

## disassembly

```asm
0x180026b84  xor     r10d, r10d
0x180026b87  mov     r8, rdx
0x180026b8a  mov     eax, 7FFFFFFEh
0x180026b8f  test    rdx, rdx
0x180026b92  jz      short loc_180026BB6
0x180026b94  test    rax, rax
0x180026b97  jz      short loc_180026BB6
0x180026b99  movzx   edx, word ptr [r9]
0x180026b9d  test    dx, dx
0x180026ba0  jz      short loc_180026BB6
0x180026ba2  mov     [rcx], dx
0x180026ba5  add     r9, 2
0x180026ba9  add     rcx, 2
0x180026bad  dec     rax
0x180026bb0  sub     r8, 1
0x180026bb4  jnz     short loc_180026B94
0x180026bb6  mov     rax, r8
0x180026bb9  lea     rdx, [rcx-2]
0x180026bbd  neg     rax
0x180026bc0  sbb     eax, eax
0x180026bc2  not     eax
0x180026bc4  and     eax, 8007007Ah
0x180026bc9  test    r8, r8
0x180026bcc  cmovnz  rdx, rcx
0x180026bd0  mov     [rdx], r10w
0x180026bd4  retn
```
