# StringCopyWorkerW

- ea: `0x180004574`
- end: `0x1800045c5`
- name: `StringCopyWorkerW`
- size: `81`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800044e8`
- `0x180004530`

## callees

- `0x180004574`

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
0x180004574  xor     r10d, r10d
0x180004577  mov     r8, rdx
0x18000457a  mov     eax, 7FFFFFFEh
0x18000457f  test    rdx, rdx
0x180004582  jz      short loc_1800045A6
0x180004584  test    rax, rax
0x180004587  jz      short loc_1800045A6
0x180004589  movzx   edx, word ptr [r9]
0x18000458d  test    dx, dx
0x180004590  jz      short loc_1800045A6
0x180004592  mov     [rcx], dx
0x180004595  add     r9, 2
0x180004599  add     rcx, 2
0x18000459d  dec     rax
0x1800045a0  sub     r8, 1
0x1800045a4  jnz     short loc_180004584
0x1800045a6  mov     rax, r8
0x1800045a9  lea     rdx, [rcx-2]
0x1800045ad  neg     rax
0x1800045b0  sbb     eax, eax
0x1800045b2  not     eax
0x1800045b4  and     eax, 8007007Ah
0x1800045b9  test    r8, r8
0x1800045bc  cmovnz  rdx, rcx
0x1800045c0  mov     [rdx], r10w
0x1800045c4  retn
```
