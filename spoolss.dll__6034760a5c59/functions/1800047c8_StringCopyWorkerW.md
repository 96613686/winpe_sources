# StringCopyWorkerW

- ea: `0x1800047c8`
- end: `0x180004819`
- name: `StringCopyWorkerW`
- size: `81`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180004734`
- `0x18000ae10`

## callees

- `0x1800047c8`

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
0x1800047c8  xor     r10d, r10d
0x1800047cb  mov     r8, rdx
0x1800047ce  mov     eax, 7FFFFFFEh
0x1800047d3  test    rdx, rdx
0x1800047d6  jz      short loc_1800047FA
0x1800047d8  test    rax, rax
0x1800047db  jz      short loc_1800047FA
0x1800047dd  movzx   edx, word ptr [r9]
0x1800047e1  test    dx, dx
0x1800047e4  jz      short loc_1800047FA
0x1800047e6  mov     [rcx], dx
0x1800047e9  add     r9, 2
0x1800047ed  add     rcx, 2
0x1800047f1  dec     rax
0x1800047f4  sub     r8, 1
0x1800047f8  jnz     short loc_1800047D8
0x1800047fa  mov     rax, r8
0x1800047fd  lea     rdx, [rcx-2]
0x180004801  neg     rax
0x180004804  sbb     eax, eax
0x180004806  not     eax
0x180004808  and     eax, 8007007Ah
0x18000480d  test    r8, r8
0x180004810  cmovnz  rdx, rcx
0x180004814  mov     [rdx], r10w
0x180004818  retn
```
