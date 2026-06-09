# StrRetToStrA

- ea: `0x180021bb0`
- end: `0x180021c2e`
- name: `StrRetToStrA`
- size: `126`
- prototype: `HRESULT __stdcall(STRRET *pstr, LPCITEMIDLIST pidl, LPSTR *ppsz)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000d020`
- `0x1800218dc`
- `0x180021bb0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021c1b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021c1b`

## pseudocode

```c
HRESULT __stdcall StrRetToStrA(STRRET *pstr, LPCITEMIDLIST pidl, LPSTR *ppsz)
{
  HRESULT v4; // ebx
  union _STRRET::$CBA4CBE4EE73FCDBDFD08B2527F2F26D *p_pOleStr; // rcx
  HRESULT v6; // eax
  LPWSTR pOleStr; // rcx

  switch ( pstr->uType )
  {
    case 0u:
      v6 = DupWideToAnsi(pstr->pOleStr, ppsz);
      pOleStr = pstr->pOleStr;
      v4 = v6;
      pstr->pOleStr = 0;
      CoTaskMemFree(pOleStr);
      return v4;
    case 1u:
      v4 = -2147024809;
      if ( !pidl )
        return v4;
      p_pOleStr = (union _STRRET::$CBA4CBE4EE73FCDBDFD08B2527F2F26D *)((char *)pidl + pstr->uOffset);
      return DupAnsiToAnsi((STRSAFE_LPCSTR)p_pOleStr, ppsz);
    case 2u:
      p_pOleStr = (union _STRRET::$CBA4CBE4EE73FCDBDFD08B2527F2F26D *)&pstr->pOleStr;
      return DupAnsiToAnsi((STRSAFE_LPCSTR)p_pOleStr, ppsz);
  }
  *ppsz = 0;
  return -2147467259;
}

```

## disassembly

```asm
0x180021bb0  mov     [rsp+arg_0], rbx
0x180021bb5  push    rdi
0x180021bb6  sub     rsp, 20h
0x180021bba  mov     r9d, [rcx]
0x180021bbd  mov     rdi, rcx
0x180021bc0  test    r9d, r9d
0x180021bc3  jz      short loc_180021C01
0x180021bc5  sub     r9d, 1
0x180021bc9  jz      short loc_180021BE5
0x180021bcb  cmp     r9d, 1
0x180021bcf  jz      short loc_180021BDF
0x180021bd1  mov     qword ptr [r8], 0
0x180021bd8  mov     ebx, 80004005h
0x180021bdd  jmp     short loc_180021C21
0x180021bdf  add     rcx, 8
0x180021be3  jmp     short loc_180021BF5
0x180021be5  mov     ebx, 80070057h
0x180021bea  test    rdx, rdx
0x180021bed  jz      short loc_180021C21
0x180021bef  mov     ecx, [rcx+8]
0x180021bf2  add     rcx, rdx; pszSrc
0x180021bf5  mov     rdx, r8
0x180021bf8  call    DupAnsiToAnsi
0x180021bfd  mov     ebx, eax
0x180021bff  jmp     short loc_180021C21
0x180021c01  mov     rcx, [rcx+8]; pwszSrc
0x180021c05  mov     rdx, r8
0x180021c08  call    DupWideToAnsi
0x180021c0d  mov     rcx, [rdi+8]; pv
0x180021c11  mov     ebx, eax
0x180021c13  mov     qword ptr [rdi+8], 0
0x180021c1b  call    cs:__imp_CoTaskMemFree
0x180021c21  mov     eax, ebx
0x180021c23  mov     rbx, [rsp+28h+arg_0]
0x180021c28  add     rsp, 20h
0x180021c2c  pop     rdi
0x180021c2d  retn
```
