# StringCopyWorkerW

- ea: `0x1800055a4`
- end: `0x1800055f5`
- name: `StringCopyWorkerW`
- size: `81`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180003824`
- `0x1800054b0`
- `0x1800056a8`

## callees

- `0x1800055a4`

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
0x1800055a4  xor     r10d, r10d
0x1800055a7  mov     r8, rdx
0x1800055aa  mov     eax, 7FFFFFFEh
0x1800055af  test    rdx, rdx
0x1800055b2  jz      short loc_1800055D6
0x1800055b4  test    rax, rax
0x1800055b7  jz      short loc_1800055D6
0x1800055b9  movzx   edx, word ptr [r9]
0x1800055bd  test    dx, dx
0x1800055c0  jz      short loc_1800055D6
0x1800055c2  mov     [rcx], dx
0x1800055c5  add     r9, 2
0x1800055c9  add     rcx, 2
0x1800055cd  dec     rax
0x1800055d0  sub     r8, 1
0x1800055d4  jnz     short loc_1800055B4
0x1800055d6  mov     rax, r8
0x1800055d9  lea     rdx, [rcx-2]
0x1800055dd  neg     rax
0x1800055e0  sbb     eax, eax
0x1800055e2  not     eax
0x1800055e4  and     eax, 8007007Ah
0x1800055e9  test    r8, r8
0x1800055ec  cmovnz  rdx, rcx
0x1800055f0  mov     [rdx], r10w
0x1800055f4  retn
```
