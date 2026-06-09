# StringCopyWorkerA

- ea: `0x180002680`
- end: `0x1800026c6`
- name: `StringCopyWorkerA`
- size: `70`
- prototype: `static HRESULT __stdcall(STRSAFE_LPSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZCH pszSrc, size_t cchToCopy)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180002130`
- `0x180002830`

## callees

- `0x180002680`

## pseudocode

```c
HRESULT __stdcall StringCopyWorkerA(
        STRSAFE_LPSTR pszDest,
        size_t cchDest,
        size_t *pcchNewDestLength,
        STRSAFE_PCNZCH pszSrc,
        size_t cchToCopy)
{
  __int64 i; // r8
  HRESULT result; // eax
  STRSAFE_LPSTR v8; // rcx

  for ( i = 2147483646; cchDest; --cchDest )
  {
    if ( !i )
      break;
    if ( !*pszSrc )
      break;
    *pszDest++ = *pszSrc++;
    --i;
  }
  result = -2147024774;
  if ( cchDest )
    result = 0;
  v8 = pszDest - 1;
  if ( cchDest )
    v8 = pszDest;
  *v8 = 0;
  return result;
}

```

## disassembly

```asm
0x180002680  mov     r10, rcx
0x180002683  mov     r8d, 7FFFFFFEh
0x180002689  test    rdx, rdx
0x18000268c  jz      short loc_1800026AD
0x18000268e  test    r8, r8
0x180002691  jz      short loc_1800026AD
0x180002693  movzx   eax, byte ptr [r9]
0x180002697  test    al, al
0x180002699  jz      short loc_1800026AD
0x18000269b  mov     [r10], al
0x18000269e  inc     r9
0x1800026a1  inc     r10
0x1800026a4  dec     r8
0x1800026a7  sub     rdx, 1
0x1800026ab  jnz     short loc_18000268E
0x1800026ad  xor     ecx, ecx
0x1800026af  mov     eax, 8007007Ah
0x1800026b4  test    rdx, rdx
0x1800026b7  cmovnz  eax, ecx
0x1800026ba  lea     rcx, [r10-1]
0x1800026be  cmovnz  rcx, r10
0x1800026c2  mov     byte ptr [rcx], 0
0x1800026c5  retn
```
