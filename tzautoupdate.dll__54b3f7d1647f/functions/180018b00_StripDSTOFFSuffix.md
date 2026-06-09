# StripDSTOFFSuffix

- ea: `0x180018b00`
- end: `0x180018b79`
- name: `StripDSTOFFSuffix`
- size: `121`
- prototype: `__int64 __fastcall(STRSAFE_LPCWSTR pszSrc, STRSAFE_LPWSTR pszDest, size_t cchDest)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180018254`

## callees

- `0x180017d24`
- `0x180018b00`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180018b59`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180018b59`

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
0x180018b00  push    rbx
0x180018b02  push    rbp
0x180018b03  push    rsi
0x180018b04  push    rdi
0x180018b05  sub     rsp, 38h
0x180018b09  mov     r11, rdx
0x180018b0c  xor     ebp, ebp
0x180018b0e  mov     edx, r8d; cchDest
0x180018b11  mov     rsi, r9
0x180018b14  mov     r8, rcx; pszSrc
0x180018b17  mov     [r9], ebp
0x180018b1a  mov     rcx, r11; pszDest
0x180018b1d  call    StringCchCopyW
0x180018b22  mov     edi, eax
0x180018b24  test    eax, eax
0x180018b26  js      short loc_180018B6E
0x180018b28  or      rdx, 0FFFFFFFFFFFFFFFFh; cchCount1
0x180018b2c  mov     rcx, rdx
0x180018b2f  inc     rcx
0x180018b32  cmp     [r11+rcx*2], bp
0x180018b37  jnz     short loc_180018B2F
0x180018b39  cmp     rcx, 7
0x180018b3d  jbe     short loc_180018B6E
0x180018b3f  lea     rbx, [r11+rcx*2]
0x180018b43  mov     [rsp+58h+bIgnoreCase], 1; bIgnoreCase
0x180018b4b  lea     rcx, [rbx-0Eh]; lpString1
0x180018b4f  mov     r9d, edx; cchCount2
0x180018b52  lea     r8, pszSrc; "_dstoff"
0x180018b59  call    cs:__imp_CompareStringOrdinal
0x180018b5f  cmp     eax, 2
0x180018b62  jnz     short loc_180018B6E
0x180018b64  mov     [rbx-0Eh], bp
0x180018b68  mov     dword ptr [rsi], 1
0x180018b6e  mov     eax, edi
0x180018b70  add     rsp, 38h
0x180018b74  pop     rdi
0x180018b75  pop     rsi
0x180018b76  pop     rbp
0x180018b77  pop     rbx
0x180018b78  retn
```
