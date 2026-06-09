# StringCchLengthW

- ea: `0x1800163dc`
- end: `0x180016421`
- name: `StringCchLengthW`
- size: `69`
- prototype: `HRESULT __stdcall(STRSAFE_PCNZWCH psz, size_t cchMax, size_t *pcchLength)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000cbfc`

## callees

- `0x1800163dc`

## string_xrefs

- `0x1800163e1`: `ACLUIFileFolderTool-IsSecurityUIEnabled`

## pseudocode

```c
HRESULT __stdcall StringCchLengthW(STRSAFE_PCNZWCH psz, size_t cchMax, size_t *pcchLength)
{
  const wchar_t *v3; // rax
  __int64 v4; // rcx
  HRESULT result; // eax

  v3 = L"ACLUIFileFolderTool-IsSecurityUIEnabled";
  v4 = 0x7FFFFFFF;
  do
  {
    if ( !*v3 )
      break;
    ++v3;
    --v4;
  }
  while ( v4 );
  result = v4 == 0 ? 0x80070057 : 0;
  if ( pcchLength )
  {
    if ( v4 )
      *pcchLength = 0x7FFFFFFF - v4;
    else
      *pcchLength = 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800163dc  mov     edx, 7FFFFFFFh
0x1800163e1  lea     rax, aAcluifilefolde; "ACLUIFileFolderTool-IsSecurityUIEnabled"
0x1800163e8  mov     ecx, edx
0x1800163ea  xor     r9d, r9d
0x1800163ed  cmp     [rax], r9w
0x1800163f1  jz      short loc_1800163FD
0x1800163f3  add     rax, 2
0x1800163f7  sub     rcx, 1
0x1800163fb  jnz     short loc_1800163ED
0x1800163fd  mov     rax, rcx
0x180016400  neg     rax
0x180016403  sbb     eax, eax
0x180016405  not     eax
0x180016407  and     eax, 80070057h
0x18001640c  test    r8, r8
0x18001640f  jz      short locret_180016420
0x180016411  test    rcx, rcx
0x180016414  jz      short loc_18001641D
0x180016416  sub     rdx, rcx
0x180016419  mov     [r8], rdx
0x18001641c  retn
0x18001641d  mov     [r8], r9
0x180016420  retn
```
