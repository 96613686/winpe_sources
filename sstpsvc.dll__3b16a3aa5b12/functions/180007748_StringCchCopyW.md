# StringCchCopyW

- ea: `0x180007748`
- end: `0x1800077b3`
- name: `StringCchCopyW`
- size: `107`
- prototype: `HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszSrc)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180007660`

## callees

- `0x180007748`

## pseudocode

```c
HRESULT __stdcall StringCchCopyW(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszSrc)
{
  STRSAFE_LPWSTR v3; // r9
  HRESULT result; // eax
  __int64 v5; // rax

  v3 = pszDest;
  if ( !cchDest )
    return -2147024809;
  if ( cchDest <= 0x7FFFFFFF )
  {
    v5 = 2147483646;
    do
    {
      if ( !v5 )
        break;
      if ( !*pszSrc )
        break;
      *v3++ = *pszSrc++;
      --v5;
      --cchDest;
    }
    while ( cchDest );
    pszDest = v3 - 1;
    if ( cchDest )
      pszDest = v3;
    result = cchDest == 0 ? 0x8007007A : 0;
  }
  else
  {
    result = -2147024809;
  }
  *pszDest = 0;
  return result;
}

```

## disassembly

```asm
0x180007748  xor     r10d, r10d
0x18000774b  mov     r9, rcx
0x18000774e  test    rdx, rdx
0x180007751  jz      short loc_1800077A4
0x180007753  cmp     rdx, 7FFFFFFFh
0x18000775a  jbe     short loc_180007763
0x18000775c  mov     eax, 80070057h
0x180007761  jmp     short loc_1800077AE
0x180007763  mov     eax, 7FFFFFFEh
0x180007768  test    rax, rax
0x18000776b  jz      short loc_18000778B
0x18000776d  movzx   ecx, word ptr [r8]
0x180007771  test    cx, cx
0x180007774  jz      short loc_18000778B
0x180007776  mov     [r9], cx
0x18000777a  add     r8, 2
0x18000777e  add     r9, 2
0x180007782  dec     rax
0x180007785  sub     rdx, 1
0x180007789  jnz     short loc_180007768
0x18000778b  test    rdx, rdx
0x18000778e  lea     rcx, [r9-2]
0x180007792  cmovnz  rcx, r9
0x180007796  neg     rdx
0x180007799  sbb     eax, eax
0x18000779b  not     eax
0x18000779d  and     eax, 8007007Ah
0x1800077a2  jmp     short loc_1800077AE
0x1800077a4  mov     eax, 80070057h
0x1800077a9  test    rdx, rdx
0x1800077ac  jz      short locret_1800077B2
0x1800077ae  mov     [rcx], r10w
0x1800077b2  retn
```
