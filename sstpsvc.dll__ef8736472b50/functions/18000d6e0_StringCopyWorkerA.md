# StringCopyWorkerA

- ea: `0x18000d6e0`
- end: `0x18000d729`
- name: `StringCopyWorkerA`
- size: `73`
- prototype: `static HRESULT __stdcall(STRSAFE_LPSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZCH pszSrc, size_t cchToCopy)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000ca68`
- `0x18000d694`

## callees

- `0x18000d6e0`

## pseudocode

```c
HRESULT __stdcall StringCopyWorkerA(
        STRSAFE_LPSTR pszDest,
        size_t cchDest,
        size_t *pcchNewDestLength,
        STRSAFE_PCNZCH pszSrc,
        size_t cchToCopy)
{
  STRSAFE_LPSTR v7; // rcx
  HRESULT result; // eax

  for ( ; cchDest; --cchDest )
  {
    if ( !cchToCopy )
      break;
    if ( !*pszSrc )
      break;
    *pszDest++ = *pszSrc++;
    --cchToCopy;
  }
  v7 = pszDest - 1;
  result = cchDest == 0 ? 0x8007007A : 0;
  if ( cchDest )
    v7 = pszDest;
  *v7 = 0;
  return result;
}

```

## disassembly

```asm
0x18000d6e0  mov     r8, rcx
0x18000d6e3  test    rdx, rdx
0x18000d6e6  jz      short loc_18000D70B
0x18000d6e8  mov     rax, [rsp+cchToCopy]
0x18000d6ed  test    rax, rax
0x18000d6f0  jz      short loc_18000D70B
0x18000d6f2  mov     cl, [r9]
0x18000d6f5  test    cl, cl
0x18000d6f7  jz      short loc_18000D70B
0x18000d6f9  mov     [r8], cl
0x18000d6fc  inc     r9
0x18000d6ff  inc     r8
0x18000d702  dec     rax
0x18000d705  sub     rdx, 1
0x18000d709  jnz     short loc_18000D6ED
0x18000d70b  mov     rax, rdx
0x18000d70e  lea     rcx, [r8-1]
0x18000d712  neg     rax
0x18000d715  sbb     eax, eax
0x18000d717  not     eax
0x18000d719  and     eax, 8007007Ah
0x18000d71e  test    rdx, rdx
0x18000d721  cmovnz  rcx, r8
0x18000d725  mov     byte ptr [rcx], 0
0x18000d728  retn
```
