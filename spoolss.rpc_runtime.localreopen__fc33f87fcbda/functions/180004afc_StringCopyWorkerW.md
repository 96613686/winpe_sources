# StringCopyWorkerW

- ea: `0x180004afc`
- end: `0x180004b4d`
- name: `StringCopyWorkerW`
- size: `81`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180004a64`
- `0x18000b710`

## callees

- `0x180004afc`

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
0x180004afc  xor     r10d, r10d
0x180004aff  mov     r8, rdx
0x180004b02  mov     eax, 7FFFFFFEh
0x180004b07  test    rdx, rdx
0x180004b0a  jz      short loc_180004B2E
0x180004b0c  test    rax, rax
0x180004b0f  jz      short loc_180004B2E
0x180004b11  movzx   edx, word ptr [r9]
0x180004b15  test    dx, dx
0x180004b18  jz      short loc_180004B2E
0x180004b1a  mov     [rcx], dx
0x180004b1d  add     r9, 2
0x180004b21  add     rcx, 2
0x180004b25  dec     rax
0x180004b28  sub     r8, 1
0x180004b2c  jnz     short loc_180004B0C
0x180004b2e  mov     rax, r8
0x180004b31  lea     rdx, [rcx-2]
0x180004b35  neg     rax
0x180004b38  sbb     eax, eax
0x180004b3a  not     eax
0x180004b3c  and     eax, 8007007Ah
0x180004b41  test    r8, r8
0x180004b44  cmovnz  rdx, rcx
0x180004b48  mov     [rdx], r10w
0x180004b4c  retn
```
