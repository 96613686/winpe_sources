# StringCopyWorkerW

- ea: `0x1800269a8`
- end: `0x1800269f9`
- name: `StringCopyWorkerW`
- size: `81`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180026898`

## callees

- `0x1800269a8`

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
0x1800269a8  xor     r10d, r10d
0x1800269ab  mov     r8, rdx
0x1800269ae  mov     eax, 7FFFFFFEh
0x1800269b3  test    rdx, rdx
0x1800269b6  jz      short loc_1800269DA
0x1800269b8  test    rax, rax
0x1800269bb  jz      short loc_1800269DA
0x1800269bd  movzx   edx, word ptr [r9]
0x1800269c1  test    dx, dx
0x1800269c4  jz      short loc_1800269DA
0x1800269c6  mov     [rcx], dx
0x1800269c9  add     r9, 2
0x1800269cd  add     rcx, 2
0x1800269d1  dec     rax
0x1800269d4  sub     r8, 1
0x1800269d8  jnz     short loc_1800269B8
0x1800269da  mov     rax, r8
0x1800269dd  lea     rdx, [rcx-2]
0x1800269e1  neg     rax
0x1800269e4  sbb     eax, eax
0x1800269e6  not     eax
0x1800269e8  and     eax, 8007007Ah
0x1800269ed  test    r8, r8
0x1800269f0  cmovnz  rdx, rcx
0x1800269f4  mov     [rdx], r10w
0x1800269f8  retn
```
