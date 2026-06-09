# StringCchCopyW

- ea: `0x180002214`
- end: `0x18000227f`
- name: `StringCchCopyW`
- size: `107`
- prototype: `HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszSrc)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180001bd4`
- `0x180001fc8`
- `0x180016b40`

## callees

- `0x180002214`

## pseudocode

```c
HRESULT __stdcall StringCchCopyW(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszSrc)
{
  STRSAFE_LPWSTR v3; // r9
  __int64 v4; // rax
  HRESULT result; // eax

  v3 = pszDest;
  if ( !cchDest )
    return -2147024809;
  if ( cchDest > 0x7FFFFFFF )
  {
    result = -2147024809;
  }
  else
  {
    v4 = 2147483646;
    do
    {
      if ( !v4 )
        break;
      if ( !*pszSrc )
        break;
      *v3++ = *pszSrc++;
      --v4;
      --cchDest;
    }
    while ( cchDest );
    pszDest = v3 - 1;
    if ( cchDest )
      pszDest = v3;
    result = cchDest == 0 ? 0x8007007A : 0;
  }
  *pszDest = 0;
  return result;
}

```

## disassembly

```asm
0x180002214  xor     r10d, r10d
0x180002217  mov     r9, rcx
0x18000221a  test    rdx, rdx
0x18000221d  jz      short loc_180002273
0x18000221f  cmp     rdx, 7FFFFFFFh
0x180002226  ja      short loc_18000226C
0x180002228  mov     eax, 7FFFFFFEh
0x18000222d  test    rax, rax
0x180002230  jz      short loc_180002250
0x180002232  movzx   ecx, word ptr [r8]
0x180002236  test    cx, cx
0x180002239  jz      short loc_180002250
0x18000223b  mov     [r9], cx
0x18000223f  add     r8, 2
0x180002243  add     r9, 2
0x180002247  dec     rax
0x18000224a  sub     rdx, 1
0x18000224e  jnz     short loc_18000222D
0x180002250  test    rdx, rdx
0x180002253  lea     rcx, [r9-2]
0x180002257  cmovnz  rcx, r9
0x18000225b  neg     rdx
0x18000225e  sbb     eax, eax
0x180002260  not     eax
0x180002262  and     eax, 8007007Ah
0x180002267  mov     [rcx], r10w
0x18000226b  retn
0x18000226c  mov     eax, 80070057h
0x180002271  jmp     short loc_180002267
0x180002273  mov     eax, 80070057h
0x180002278  test    rdx, rdx
0x18000227b  jz      short locret_18000226B
0x18000227d  jmp     short loc_180002267
```
