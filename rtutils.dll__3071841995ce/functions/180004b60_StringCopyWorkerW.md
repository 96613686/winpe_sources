# StringCopyWorkerW

- ea: `0x180004b60`
- end: `0x180004bb1`
- name: `StringCopyWorkerW`
- size: `81`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180004a2c`
- `0x180004ab8`

## callees

- `0x180004b60`

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
0x180004b60  xor     r10d, r10d
0x180004b63  mov     r8, rdx
0x180004b66  mov     eax, 7FFFFFFEh
0x180004b6b  test    rdx, rdx
0x180004b6e  jz      short loc_180004B92
0x180004b70  test    rax, rax
0x180004b73  jz      short loc_180004B92
0x180004b75  movzx   edx, word ptr [r9]
0x180004b79  test    dx, dx
0x180004b7c  jz      short loc_180004B92
0x180004b7e  mov     [rcx], dx
0x180004b81  add     r9, 2
0x180004b85  add     rcx, 2
0x180004b89  dec     rax
0x180004b8c  sub     r8, 1
0x180004b90  jnz     short loc_180004B70
0x180004b92  mov     rax, r8
0x180004b95  lea     rdx, [rcx-2]
0x180004b99  neg     rax
0x180004b9c  sbb     eax, eax
0x180004b9e  not     eax
0x180004ba0  and     eax, 8007007Ah
0x180004ba5  test    r8, r8
0x180004ba8  cmovnz  rdx, rcx
0x180004bac  mov     [rdx], r10w
0x180004bb0  retn
```
