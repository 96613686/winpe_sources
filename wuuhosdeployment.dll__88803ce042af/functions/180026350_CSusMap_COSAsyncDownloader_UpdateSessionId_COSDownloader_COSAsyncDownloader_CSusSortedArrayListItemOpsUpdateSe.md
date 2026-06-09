# CSusMap<COSAsyncDownloader::UpdateSessionId,COSDownloader *,COSAsyncDownloader::CSusSortedArrayListItemOpsUpdateSessionId,CSusArrayListItemOpInterfacePtr<COSDownloader *>>::CMapEntryOps::Compare(CSusMap<COSAsyncDownloader::UpdateSessionId,COSDownloader *,COSAsyncDownloader::CSusSortedArrayListItemOpsUpdateSessionId,CSusArrayListItemOpInterfacePtr<COSDownloader *>>::_tagMapEntry const &,CSusMap<COSAsyncDownloader::UpdateSessionId,COSDownloader *,COSAsyncDownloader::CSusSortedArrayListItemOpsUpdateSessionId,CSusArrayListItemOpInterfacePtr<COSDownloader *>>::_tagMapEntry const &)

- ea: `0x180026350`
- end: `0x1800263e9`
- name: `?Compare@CMapEntryOps@?$CSusMap@UUpdateSessionId@COSAsyncDownloader@@PEAVCOSDownloader@@VCSusSortedArrayListItemOpsUpdateSessionId@2@V?$CSusArrayListItemOpInterfacePtr@PEAVCOSDownloader@@@@@@SAHAEBU_tagMapEntry@2@0@Z`
- size: `153`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180026008`
- `0x1800261c4`
- `0x180026284`

## callees

- `0x180026350`
- `0x180049d20`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800263b2`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800263b2`

## pseudocode

```c
__int64 __fastcall CSusMap<COSAsyncDownloader::UpdateSessionId,COSDownloader *,COSAsyncDownloader::CSusSortedArrayListItemOpsUpdateSessionId,CSusArrayListItemOpInterfacePtr<COSDownloader *>>::CMapEntryOps::Compare(
        __int64 a1,
        __int64 a2)
{
  unsigned int *v2; // rcx
  _QWORD *v3; // rdx
  unsigned int v4; // eax
  unsigned int v5; // ebx
  const WCHAR *lpString2; // rax
  const WCHAR *v7; // r8
  int v8; // eax

  v2 = (unsigned int *)(a1 + 8);
  v3 = (_QWORD *)(a2 + 8);
  if ( *(_QWORD *)v2 != *v3 || *((_QWORD *)v2 + 1) != v3[1] )
    return (unsigned int)memcmp(v2, v3, 0x10u);
  v4 = v2[4];
  if ( v4 >= *((_DWORD *)v3 + 4) )
  {
    if ( v4 <= *((_DWORD *)v3 + 4) )
    {
      lpString2 = (const WCHAR *)v3[3];
      v7 = (const WCHAR *)*((_QWORD *)v2 + 3);
      if ( v7 == lpString2 )
        return 0;
      v5 = -1;
      if ( !v7 )
        return v5;
      if ( !lpString2 )
        return 1;
      v8 = CompareStringW(0x7Fu, 1u, v7, -1, lpString2, -1);
      if ( v8 == 1 )
        return v5;
      if ( v8 == 2 )
        return 0;
      if ( v8 != 3 )
        return (unsigned int)-2;
    }
    return 1;
  }
  return (unsigned int)-1;
}

```

## disassembly

```asm
0x180026350  push    rbx
0x180026352  sub     rsp, 30h
0x180026356  add     rcx, 8; Buf1
0x18002635a  add     rdx, 8; Buf2
0x18002635e  mov     rax, [rcx]
0x180026361  cmp     rax, [rdx]
0x180026364  jnz     short loc_1800263D4
0x180026366  mov     rax, [rcx+8]
0x18002636a  cmp     rax, [rdx+8]
0x18002636e  jnz     short loc_1800263D4
0x180026370  mov     eax, [rcx+10h]
0x180026373  cmp     eax, [rdx+10h]
0x180026376  jnb     short loc_18002637D
0x180026378  or      ebx, 0FFFFFFFFh
0x18002637b  jmp     short loc_1800263E1
0x18002637d  jbe     short loc_180026386
0x18002637f  mov     ebx, 1
0x180026384  jmp     short loc_1800263E1
0x180026386  mov     rax, [rdx+18h]
0x18002638a  mov     r8, [rcx+18h]; lpString1
0x18002638e  cmp     r8, rax
0x180026391  jz      short loc_1800263D0
0x180026393  or      ebx, 0FFFFFFFFh
0x180026396  test    r8, r8
0x180026399  jz      short loc_1800263E1
0x18002639b  test    rax, rax
0x18002639e  jz      short loc_18002637F
0x1800263a0  lea     edx, [rbx+2]; dwCmpFlags
0x1800263a3  mov     [rsp+38h+cchCount2], ebx; cchCount2
0x1800263a7  lea     ecx, [rdx+7Eh]; Locale
0x1800263aa  mov     [rsp+38h+lpString2], rax; lpString2
0x1800263af  mov     r9d, ebx; cchCount1
0x1800263b2  call    cs:__imp_CompareStringW
0x1800263b8  mov     ecx, eax
0x1800263ba  sub     ecx, 1
0x1800263bd  jz      short loc_1800263E1
0x1800263bf  sub     ecx, 1
0x1800263c2  jz      short loc_1800263D0
0x1800263c4  cmp     ecx, 1
0x1800263c7  jz      short loc_18002637F
0x1800263c9  mov     ebx, 0FFFFFFFEh
0x1800263ce  jmp     short loc_1800263E1
0x1800263d0  xor     ebx, ebx
0x1800263d2  jmp     short loc_1800263E1
0x1800263d4  mov     r8d, 10h; Size
0x1800263da  call    memcmp
0x1800263df  mov     ebx, eax
0x1800263e1  mov     eax, ebx
0x1800263e3  add     rsp, 30h
0x1800263e7  pop     rbx
0x1800263e8  retn
```
