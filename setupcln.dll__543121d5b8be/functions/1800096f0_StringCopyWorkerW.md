# StringCopyWorkerW

- ea: `0x1800096f0`
- end: `0x180009741`
- name: `StringCopyWorkerW`
- size: `81`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800095d0`
- `0x180009624`

## callees

- `0x1800096f0`

## pseudocode

```c
HRESULT __stdcall StringCopyWorkerW(
        STRSAFE_LPWSTR pszDest,
        size_t cchDest,
        size_t *pcchNewDestLength,
        STRSAFE_PCNZWCH pszSrc,
        size_t cchToCopy)
{
  size_t i; // r8
  STRSAFE_LPWSTR v7; // rdx
  HRESULT result; // eax

  for ( i = cchDest; i; --i )
  {
    if ( !cchToCopy )
      break;
    if ( !*pszSrc )
      break;
    *pszDest++ = *pszSrc++;
    --cchToCopy;
  }
  v7 = pszDest - 1;
  result = i == 0 ? 0x8007007A : 0;
  if ( i )
    v7 = pszDest;
  *v7 = 0;
  return result;
}

```

## disassembly

```asm
0x1800096f0  xor     r10d, r10d
0x1800096f3  mov     r8, rdx
0x1800096f6  test    rdx, rdx
0x1800096f9  jz      short loc_180009722
0x1800096fb  mov     rax, [rsp+cchToCopy]
0x180009700  test    rax, rax
0x180009703  jz      short loc_180009722
0x180009705  movzx   edx, word ptr [r9]
0x180009709  test    dx, dx
0x18000970c  jz      short loc_180009722
0x18000970e  mov     [rcx], dx
0x180009711  add     r9, 2
0x180009715  add     rcx, 2
0x180009719  dec     rax
0x18000971c  sub     r8, 1
0x180009720  jnz     short loc_180009700
0x180009722  mov     rax, r8
0x180009725  lea     rdx, [rcx-2]
0x180009729  neg     rax
0x18000972c  sbb     eax, eax
0x18000972e  not     eax
0x180009730  and     eax, 8007007Ah
0x180009735  test    r8, r8
0x180009738  cmovnz  rdx, rcx
0x18000973c  mov     [rdx], r10w
0x180009740  retn
```
