# StringCopyWorkerW

- ea: `0x180009664`
- end: `0x1800096b5`
- name: `StringCopyWorkerW`
- size: `81`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180007a24`
- `0x180009570`
- `0x180009798`

## callees

- `0x180009664`

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
0x180009664  xor     r10d, r10d
0x180009667  mov     r8, rdx
0x18000966a  mov     eax, 7FFFFFFEh
0x18000966f  test    rdx, rdx
0x180009672  jz      short loc_180009696
0x180009674  test    rax, rax
0x180009677  jz      short loc_180009696
0x180009679  movzx   edx, word ptr [r9]
0x18000967d  test    dx, dx
0x180009680  jz      short loc_180009696
0x180009682  mov     [rcx], dx
0x180009685  add     r9, 2
0x180009689  add     rcx, 2
0x18000968d  dec     rax
0x180009690  sub     r8, 1
0x180009694  jnz     short loc_180009674
0x180009696  mov     rax, r8
0x180009699  lea     rdx, [rcx-2]
0x18000969d  neg     rax
0x1800096a0  sbb     eax, eax
0x1800096a2  not     eax
0x1800096a4  and     eax, 8007007Ah
0x1800096a9  test    r8, r8
0x1800096ac  cmovnz  rdx, rcx
0x1800096b0  mov     [rdx], r10w
0x1800096b4  retn
```
