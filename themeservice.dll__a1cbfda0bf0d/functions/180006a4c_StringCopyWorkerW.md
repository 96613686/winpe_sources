# StringCopyWorkerW

- ea: `0x180006a4c`
- end: `0x180006a9d`
- name: `StringCopyWorkerW`
- size: `81`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180006a08`
- `0x180009e24`

## callees

- `0x180006a4c`

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
0x180006a4c  xor     r10d, r10d
0x180006a4f  mov     r8, rdx
0x180006a52  mov     eax, 7FFFFFFEh
0x180006a57  test    rdx, rdx
0x180006a5a  jz      short loc_180006A7E
0x180006a5c  test    rax, rax
0x180006a5f  jz      short loc_180006A7E
0x180006a61  movzx   edx, word ptr [r9]
0x180006a65  test    dx, dx
0x180006a68  jz      short loc_180006A7E
0x180006a6a  mov     [rcx], dx
0x180006a6d  add     r9, 2
0x180006a71  add     rcx, 2
0x180006a75  dec     rax
0x180006a78  sub     r8, 1
0x180006a7c  jnz     short loc_180006A5C
0x180006a7e  mov     rax, r8
0x180006a81  lea     rdx, [rcx-2]
0x180006a85  neg     rax
0x180006a88  sbb     eax, eax
0x180006a8a  not     eax
0x180006a8c  and     eax, 8007007Ah
0x180006a91  test    r8, r8
0x180006a94  cmovnz  rdx, rcx
0x180006a98  mov     [rdx], r10w
0x180006a9c  retn
```
