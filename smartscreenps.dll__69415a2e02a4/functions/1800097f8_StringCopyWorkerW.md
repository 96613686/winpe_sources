# StringCopyWorkerW

- ea: `0x1800097f8`
- end: `0x180009849`
- name: `StringCopyWorkerW`
- size: `81`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180007aa8`
- `0x180009700`
- `0x180009958`

## callees

- `0x1800097f8`

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
0x1800097f8  xor     r10d, r10d
0x1800097fb  mov     r8, rdx
0x1800097fe  mov     eax, 7FFFFFFEh
0x180009803  test    rdx, rdx
0x180009806  jz      short loc_18000982A
0x180009808  test    rax, rax
0x18000980b  jz      short loc_18000982A
0x18000980d  movzx   edx, word ptr [r9]
0x180009811  test    dx, dx
0x180009814  jz      short loc_18000982A
0x180009816  mov     [rcx], dx
0x180009819  add     r9, 2
0x18000981d  add     rcx, 2
0x180009821  dec     rax
0x180009824  sub     r8, 1
0x180009828  jnz     short loc_180009808
0x18000982a  mov     rax, r8
0x18000982d  lea     rdx, [rcx-2]
0x180009831  neg     rax
0x180009834  sbb     eax, eax
0x180009836  not     eax
0x180009838  and     eax, 8007007Ah
0x18000983d  test    r8, r8
0x180009840  cmovnz  rdx, rcx
0x180009844  mov     [rdx], r10w
0x180009848  retn
```
