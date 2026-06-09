# StringCopyWorkerA

- ea: `0x18001ba48`
- end: `0x18001ba93`
- name: `StringCopyWorkerA`
- size: `75`
- prototype: `static HRESULT __stdcall(STRSAFE_LPSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZCH pszSrc, size_t cchToCopy)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18001ba0c`
- `0x18001f3e4`

## callees

- `0x18001ba48`

## pseudocode

```c
HRESULT __stdcall StringCopyWorkerA(
        STRSAFE_LPSTR pszDest,
        size_t cchDest,
        size_t *pcchNewDestLength,
        STRSAFE_PCNZCH pszSrc,
        size_t cchToCopy)
{
  __int64 i; // rax
  STRSAFE_LPSTR v7; // rcx
  HRESULT result; // eax

  for ( i = 2147483646; cchDest; --cchDest )
  {
    if ( !i )
      break;
    if ( !*pszSrc )
      break;
    *pszDest++ = *pszSrc++;
    --i;
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
0x18001ba48  mov     r8, rcx
0x18001ba4b  mov     eax, 7FFFFFFEh
0x18001ba50  test    rdx, rdx
0x18001ba53  jz      short loc_18001BA61
0x18001ba55  test    rax, rax
0x18001ba58  jz      short loc_18001BA61
0x18001ba5a  mov     cl, [r9]
0x18001ba5d  test    cl, cl
0x18001ba5f  jnz     short loc_18001BA7F
0x18001ba61  mov     rax, rdx
0x18001ba64  lea     rcx, [r8-1]
0x18001ba68  neg     rax
0x18001ba6b  sbb     eax, eax
0x18001ba6d  not     eax
0x18001ba6f  and     eax, 8007007Ah
0x18001ba74  test    rdx, rdx
0x18001ba77  cmovnz  rcx, r8
0x18001ba7b  mov     byte ptr [rcx], 0
0x18001ba7e  retn
0x18001ba7f  mov     [r8], cl
0x18001ba82  inc     r9
0x18001ba85  inc     r8
0x18001ba88  dec     rax
0x18001ba8b  sub     rdx, 1
0x18001ba8f  jnz     short loc_18001BA55
0x18001ba91  jmp     short loc_18001BA61
```
