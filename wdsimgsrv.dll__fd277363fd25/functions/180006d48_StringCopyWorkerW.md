# StringCopyWorkerW

- ea: `0x180006d48`
- end: `0x180006d9a`
- name: `StringCopyWorkerW`
- size: `82`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180006cd4`
- `0x180006d10`
- `0x180007120`

## callees

- `0x180006d48`

## pseudocode

```c
HRESULT __stdcall StringCopyWorkerW(
        STRSAFE_LPWSTR pszDest,
        size_t cchDest,
        size_t *pcchNewDestLength,
        STRSAFE_PCNZWCH pszSrc,
        size_t cchToCopy)
{
  STRSAFE_LPWSTR v5; // r8
  __int64 v6; // rax
  signed __int64 v7; // r9
  wchar_t v8; // cx
  STRSAFE_LPWSTR v9; // rcx
  HRESULT result; // eax

  v5 = pszDest;
  if ( cchDest )
  {
    v6 = 2147483646;
    v7 = (char *)pszSrc - (char *)pszDest;
    do
    {
      if ( !v6 )
        break;
      v8 = *(STRSAFE_LPWSTR)((char *)v5 + v7);
      if ( !v8 )
        break;
      *v5 = v8;
      --v6;
      ++v5;
      --cchDest;
    }
    while ( cchDest );
  }
  v9 = v5 - 1;
  result = cchDest == 0 ? 0x8007007A : 0;
  if ( cchDest )
    v9 = v5;
  *v9 = 0;
  return result;
}

```

## disassembly

```asm
0x180006d48  xor     r10d, r10d
0x180006d4b  mov     r8, rcx
0x180006d4e  test    rdx, rdx
0x180006d51  jz      short loc_180006D7B
0x180006d53  mov     eax, 7FFFFFFEh
0x180006d58  sub     r9, rcx
0x180006d5b  test    rax, rax
0x180006d5e  jz      short loc_180006D7B
0x180006d60  movzx   ecx, word ptr [r9+r8]
0x180006d65  test    cx, cx
0x180006d68  jz      short loc_180006D7B
0x180006d6a  mov     [r8], cx
0x180006d6e  dec     rax
0x180006d71  add     r8, 2
0x180006d75  sub     rdx, 1
0x180006d79  jnz     short loc_180006D5B
0x180006d7b  mov     rax, rdx
0x180006d7e  lea     rcx, [r8-2]
0x180006d82  neg     rax
0x180006d85  sbb     eax, eax
0x180006d87  not     eax
0x180006d89  and     eax, 8007007Ah
0x180006d8e  test    rdx, rdx
0x180006d91  cmovnz  rcx, r8
0x180006d95  mov     [rcx], r10w
0x180006d99  retn
```
