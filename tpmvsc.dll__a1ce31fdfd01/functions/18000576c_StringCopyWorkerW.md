# StringCopyWorkerW

- ea: `0x18000576c`
- end: `0x1800057bd`
- name: `StringCopyWorkerW`
- size: `81`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180003a90`
- `0x18000568c`
- `0x180005878`

## callees

- `0x18000576c`

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
0x18000576c  xor     r10d, r10d
0x18000576f  mov     r8, rdx
0x180005772  mov     eax, 7FFFFFFEh
0x180005777  test    rdx, rdx
0x18000577a  jz      short loc_18000579E
0x18000577c  test    rax, rax
0x18000577f  jz      short loc_18000579E
0x180005781  movzx   edx, word ptr [r9]
0x180005785  test    dx, dx
0x180005788  jz      short loc_18000579E
0x18000578a  mov     [rcx], dx
0x18000578d  add     r9, 2
0x180005791  add     rcx, 2
0x180005795  dec     rax
0x180005798  sub     r8, 1
0x18000579c  jnz     short loc_18000577C
0x18000579e  mov     rax, r8
0x1800057a1  lea     rdx, [rcx-2]
0x1800057a5  neg     rax
0x1800057a8  sbb     eax, eax
0x1800057aa  not     eax
0x1800057ac  and     eax, 8007007Ah
0x1800057b1  test    r8, r8
0x1800057b4  cmovnz  rdx, rcx
0x1800057b8  mov     [rdx], r10w
0x1800057bc  retn
```
