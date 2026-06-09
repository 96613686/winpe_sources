# StrRetToBufA

- ea: `0x180021b00`
- end: `0x180021ba0`
- name: `StrRetToBufA`
- size: `160`
- prototype: `HRESULT __stdcall(STRRET *pstr, LPCITEMIDLIST pidl, LPSTR pszBuf, UINT cchBuf)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001cbd0`

## callees

- `0x180017344`
- `0x180021b00`

## import_xrefs

- `api-ms-win-shcore-unicodeansi-l1-1-0!SHUnicodeToAnsi` at `0x180021b83`
- `api-ms-win-shcore-unicodeansi-l1-1-0!SHUnicodeToAnsi` at `0x180021b83`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021b8c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021b8c`

## pseudocode

```c
HRESULT __stdcall StrRetToBufA(STRRET *pstr, LPCITEMIDLIST pidl, LPSTR pszBuf, UINT cchBuf)
{
  char *v6; // r11
  int v7; // ecx
  union _STRRET::$CBA4CBE4EE73FCDBDFD08B2527F2F26D *p_pOleStr; // r8
  LPWSTR pOleStr; // rsi

  v6 = pszBuf;
  v7 = -2147467259;
  if ( pstr->uType )
  {
    if ( pstr->uType == 1 )
    {
      if ( pidl )
      {
        p_pOleStr = (union _STRRET::$CBA4CBE4EE73FCDBDFD08B2527F2F26D *)((char *)pidl + pstr->uOffset);
LABEL_7:
        v7 = StringCchCopyA(v6, cchBuf, (STRSAFE_LPCSTR)p_pOleStr);
        if ( v7 >= 0 )
          return v7;
      }
    }
    else if ( pstr->uType == 2 )
    {
      p_pOleStr = (union _STRRET::$CBA4CBE4EE73FCDBDFD08B2527F2F26D *)&pstr->pOleStr;
      goto LABEL_7;
    }
  }
  else
  {
    pOleStr = pstr->pOleStr;
    if ( pOleStr )
    {
      SHUnicodeToAnsi(pstr->pOleStr, pszBuf, cchBuf);
      CoTaskMemFree(pOleStr);
      v7 = 0;
      pstr->uType = 2;
      pstr->cStr[0] = 0;
      return v7;
    }
  }
  if ( cchBuf )
    *v6 = 0;
  return v7;
}

```

## disassembly

```asm
0x180021b00  mov     [rsp+arg_0], rbx
0x180021b05  mov     [rsp+arg_8], rsi
0x180021b0a  push    rdi
0x180021b0b  sub     rsp, 20h
0x180021b0f  mov     rbx, rcx
0x180021b12  mov     edi, r9d
0x180021b15  mov     r11, r8
0x180021b18  mov     ecx, 80004005h
0x180021b1d  mov     r10d, [rbx]
0x180021b20  test    r10d, r10d
0x180021b23  jz      short loc_180021B71
0x180021b25  sub     r10d, 1
0x180021b29  jz      short loc_180021B37
0x180021b2b  cmp     r10d, 1
0x180021b2f  jnz     short loc_180021B57
0x180021b31  lea     r8, [rbx+8]
0x180021b35  jmp     short loc_180021B43
0x180021b37  test    rdx, rdx
0x180021b3a  jz      short loc_180021B57
0x180021b3c  mov     r8d, [rbx+8]
0x180021b40  add     r8, rdx; pszSrc
0x180021b43  mov     rax, rdi
0x180021b46  mov     rcx, r11; pszDest
0x180021b49  mov     rdx, rax; cchDest
0x180021b4c  call    StringCchCopyA
0x180021b51  mov     ecx, eax
0x180021b53  test    eax, eax
0x180021b55  jns     short loc_180021B5F
0x180021b57  test    edi, edi
0x180021b59  jz      short loc_180021B5F
0x180021b5b  mov     byte ptr [r11], 0
0x180021b5f  mov     rbx, [rsp+28h+arg_0]
0x180021b64  mov     eax, ecx
0x180021b66  mov     rsi, [rsp+28h+arg_8]
0x180021b6b  add     rsp, 20h
0x180021b6f  pop     rdi
0x180021b70  retn
0x180021b71  mov     rsi, [rbx+8]
0x180021b75  test    rsi, rsi
0x180021b78  jz      short loc_180021B57
0x180021b7a  mov     r8d, edi; cchBuf
0x180021b7d  mov     rdx, r11; pszDst
0x180021b80  mov     rcx, rsi; pwszSrc
0x180021b83  call    cs:__imp_SHUnicodeToAnsi
0x180021b89  mov     rcx, rsi; pv
0x180021b8c  call    cs:__imp_CoTaskMemFree
0x180021b92  xor     ecx, ecx
0x180021b94  mov     dword ptr [rbx], 2
0x180021b9a  mov     byte ptr [rbx+8], 0
0x180021b9e  jmp     short loc_180021B5F
```
