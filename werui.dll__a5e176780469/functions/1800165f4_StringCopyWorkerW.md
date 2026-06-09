# StringCopyWorkerW

- ea: `0x1800165f4`
- end: `0x180016645`
- name: `StringCopyWorkerW`
- size: `81`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180016578`

## callees

- `0x1800165f4`

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
0x1800165f4  xor     r10d, r10d
0x1800165f7  mov     r8, rdx
0x1800165fa  mov     eax, 7FFFFFFEh
0x1800165ff  test    rdx, rdx
0x180016602  jz      short loc_180016626
0x180016604  test    rax, rax
0x180016607  jz      short loc_180016626
0x180016609  movzx   edx, word ptr [r9]
0x18001660d  test    dx, dx
0x180016610  jz      short loc_180016626
0x180016612  mov     [rcx], dx
0x180016615  add     r9, 2
0x180016619  add     rcx, 2
0x18001661d  dec     rax
0x180016620  sub     r8, 1
0x180016624  jnz     short loc_180016604
0x180016626  mov     rax, r8
0x180016629  lea     rdx, [rcx-2]
0x18001662d  neg     rax
0x180016630  sbb     eax, eax
0x180016632  not     eax
0x180016634  and     eax, 8007007Ah
0x180016639  test    r8, r8
0x18001663c  cmovnz  rdx, rcx
0x180016640  mov     [rdx], r10w
0x180016644  retn
```
