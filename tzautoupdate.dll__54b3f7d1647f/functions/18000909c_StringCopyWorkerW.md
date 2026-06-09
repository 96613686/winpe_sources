# StringCopyWorkerW

- ea: `0x18000909c`
- end: `0x1800090ed`
- name: `StringCopyWorkerW`
- size: `81`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180005014`
- `0x180008f74`
- `0x180009738`
- `0x180017cbc`
- `0x180017d24`

## callees

- `0x18000909c`

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
0x18000909c  xor     r10d, r10d
0x18000909f  mov     r8, rdx
0x1800090a2  mov     eax, 7FFFFFFEh
0x1800090a7  test    rdx, rdx
0x1800090aa  jz      short loc_1800090CE
0x1800090ac  test    rax, rax
0x1800090af  jz      short loc_1800090CE
0x1800090b1  movzx   edx, word ptr [r9]
0x1800090b5  test    dx, dx
0x1800090b8  jz      short loc_1800090CE
0x1800090ba  mov     [rcx], dx
0x1800090bd  add     r9, 2
0x1800090c1  add     rcx, 2
0x1800090c5  dec     rax
0x1800090c8  sub     r8, 1
0x1800090cc  jnz     short loc_1800090AC
0x1800090ce  mov     rax, r8
0x1800090d1  lea     rdx, [rcx-2]
0x1800090d5  neg     rax
0x1800090d8  sbb     eax, eax
0x1800090da  not     eax
0x1800090dc  and     eax, 8007007Ah
0x1800090e1  test    r8, r8
0x1800090e4  cmovnz  rdx, rcx
0x1800090e8  mov     [rdx], r10w
0x1800090ec  retn
```
