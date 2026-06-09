# StripDSTOFFSuffix

- ea: `0x1800269b0`
- end: `0x180026a29`
- name: `StripDSTOFFSuffix`
- size: `121`
- prototype: `__int64 __fastcall(STRSAFE_LPCWSTR pszSrc, STRSAFE_LPWSTR pszDest, size_t cchDest)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800251f8`
- `0x180025f48`

## callees

- `0x180024910`
- `0x1800269b0`

## import_xrefs

- `KERNEL32!CompareStringOrdinal` at `0x180026a09`
- `KERNEL32!CompareStringOrdinal` at `0x180026a09`

## pseudocode

```c
__int64 __fastcall StripDSTOFFSuffix(STRSAFE_LPCWSTR pszSrc, STRSAFE_LPWSTR pszDest, size_t cchDest, _DWORD *a4)
{
  HRESULT v5; // edi
  __int64 v6; // r11
  unsigned __int64 v7; // rcx
  __int64 v8; // rbx

  *a4 = 0;
  v5 = StringCchCopyW(pszDest, (unsigned int)cchDest, pszSrc);
  if ( v5 >= 0 )
  {
    v7 = -1;
    do
      ++v7;
    while ( *(_WORD *)(v6 + 2 * v7) );
    if ( v7 > 7 )
    {
      v8 = v6 + 2 * v7;
      if ( CompareStringOrdinal((LPCWCH)(v8 - 14), -1, L"_dstoff", -1, 1) == 2 )
      {
        *(_WORD *)(v8 - 14) = 0;
        *a4 = 1;
      }
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800269b0  push    rbx
0x1800269b2  push    rbp
0x1800269b3  push    rsi
0x1800269b4  push    rdi
0x1800269b5  sub     rsp, 38h
0x1800269b9  mov     r11, rdx
0x1800269bc  xor     ebp, ebp
0x1800269be  mov     edx, r8d; cchDest
0x1800269c1  mov     rsi, r9
0x1800269c4  mov     r8, rcx; pszSrc
0x1800269c7  mov     [r9], ebp
0x1800269ca  mov     rcx, r11; pszDest
0x1800269cd  call    StringCchCopyW
0x1800269d2  mov     edi, eax
0x1800269d4  test    eax, eax
0x1800269d6  js      short loc_180026A1E
0x1800269d8  or      rdx, 0FFFFFFFFFFFFFFFFh; cchCount1
0x1800269dc  mov     rcx, rdx
0x1800269df  inc     rcx
0x1800269e2  cmp     [r11+rcx*2], bp
0x1800269e7  jnz     short loc_1800269DF
0x1800269e9  cmp     rcx, 7
0x1800269ed  jbe     short loc_180026A1E
0x1800269ef  lea     rbx, [r11+rcx*2]
0x1800269f3  mov     [rsp+58h+bIgnoreCase], 1; bIgnoreCase
0x1800269fb  lea     rcx, [rbx-0Eh]; lpString1
0x1800269ff  mov     r9d, edx; cchCount2
0x180026a02  lea     r8, pszSrc; "_dstoff"
0x180026a09  call    cs:__imp_CompareStringOrdinal
0x180026a0f  cmp     eax, 2
0x180026a12  jnz     short loc_180026A1E
0x180026a14  mov     [rbx-0Eh], bp
0x180026a18  mov     dword ptr [rsi], 1
0x180026a1e  mov     eax, edi
0x180026a20  add     rsp, 38h
0x180026a24  pop     rdi
0x180026a25  pop     rsi
0x180026a26  pop     rbp
0x180026a27  pop     rbx
0x180026a28  retn
```
