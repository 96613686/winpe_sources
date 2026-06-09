# StringCopyWorkerW

- ea: `0x18001648c`
- end: `0x1800164dd`
- name: `StringCopyWorkerW`
- size: `81`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180014850`
- `0x1800163ac`
- `0x180016754`

## callees

- `0x18001648c`

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
0x18001648c  xor     r10d, r10d
0x18001648f  mov     r8, rdx
0x180016492  mov     eax, 7FFFFFFEh
0x180016497  test    rdx, rdx
0x18001649a  jz      short loc_1800164BE
0x18001649c  test    rax, rax
0x18001649f  jz      short loc_1800164BE
0x1800164a1  movzx   edx, word ptr [r9]
0x1800164a5  test    dx, dx
0x1800164a8  jz      short loc_1800164BE
0x1800164aa  mov     [rcx], dx
0x1800164ad  add     r9, 2
0x1800164b1  add     rcx, 2
0x1800164b5  dec     rax
0x1800164b8  sub     r8, 1
0x1800164bc  jnz     short loc_18001649C
0x1800164be  mov     rax, r8
0x1800164c1  lea     rdx, [rcx-2]
0x1800164c5  neg     rax
0x1800164c8  sbb     eax, eax
0x1800164ca  not     eax
0x1800164cc  and     eax, 8007007Ah
0x1800164d1  test    r8, r8
0x1800164d4  cmovnz  rdx, rcx
0x1800164d8  mov     [rdx], r10w
0x1800164dc  retn
```
