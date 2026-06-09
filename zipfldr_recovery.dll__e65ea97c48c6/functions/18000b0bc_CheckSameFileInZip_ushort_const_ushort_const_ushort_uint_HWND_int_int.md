# CheckSameFileInZip(ushort const *,ushort const *,ushort *,uint,HWND__ *,int,int *)

- ea: `0x18000b0bc`
- end: `0x18000b429`
- name: `?CheckSameFileInZip@@YAKPEBG0PEAGIPEAUHWND__@@HPEAH@Z`
- size: `877`
- prototype: `unsigned int __usercall@<eax>(const unsigned __int16 *@<rcx>, const unsigned __int16 *@<rdx>, unsigned __int16 *@<r8>, unsigned int@<r9d>, HWND, int, int *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x18000c380`

## callees

- `0x18000b0bc`
- `0x18000d4e4`
- `0x18000f530`
- `0x18000fe10`
- `0x180010c30`
- `0x180010cb0`
- `0x180010d20`
- `0x180022ee8`
- `0x180036f50`
- `0x180037958`
- `0x18003ef3c`
- `0x180040a68`
- `0x180071010`

## import_xrefs

- `SHELL32!SHCreateItemFromParsingName` at `0x18000b359`
- `SHELL32!SHCreateItemFromParsingName` at `0x18000b37c`
- `SHELL32!SHCreateItemFromParsingName` at `0x18000b359`
- `SHELL32!SHCreateItemFromParsingName` at `0x18000b37c`
- `SHELL32!__imp_SHConfirmOperation` at `0x18000b3a7`
- `SHELL32!__imp_SHConfirmOperation` at `0x18000b3a7`
- `SHLWAPI!PathFindFileNameW` at `0x18000b246`
- `SHLWAPI!PathFindFileNameW` at `0x18000b274`
- `SHLWAPI!PathFindFileNameW` at `0x18000b246`
- `SHLWAPI!PathFindFileNameW` at `0x18000b274`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x18000b29b`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x18000b29b`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18000b2d6`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18000b2fc`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18000b2d6`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18000b2fc`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000b177`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000b177`

## pseudocode

```c
__int64 __fastcall CheckSameFileInZip(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        unsigned __int16 *a3,
        int a4,
        HWND hWnd,
        int a6,
        int *a7)
{
  const WCHAR *LastItem; // r12
  DWORD FileAttributesW; // eax
  DWORD v12; // ebx
  int v13; // edi
  unsigned int v14; // eax
  int v15; // ecx
  LPWSTR FileNameW; // rax
  LPWSTR v18; // rax
  unsigned int v19; // ebx
  _DWORD v20[3]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v21; // [rsp+3Ch] [rbp-C4h]
  __int128 v22; // [rsp+44h] [rbp-BCh]
  int v23; // [rsp+5Ch] [rbp-A4h]
  void *ppv; // [rsp+60h] [rbp-A0h] BYREF
  void *v25[7]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v26[4]; // [rsp+A0h] [rbp-60h] BYREF
  int v27; // [rsp+A4h] [rbp-5Ch]
  unsigned __int16 *v28; // [rsp+B0h] [rbp-50h]
  int v29; // [rsp+D4h] [rbp-2Ch]
  int v30; // [rsp+E8h] [rbp-18h]
  int v31; // [rsp+850h] [rbp+750h] BYREF
  PCWSTR pszMore; // [rsp+858h] [rbp+758h] BYREF
  unsigned __int16 v33[264]; // [rsp+860h] [rbp+760h] BYREF
  WCHAR pszPath[264]; // [rsp+A70h] [rbp+970h] BYREF

  v31 = a4;
  pszMore = a2;
  *a7 = 1;
  LastItem = PathFindLastItem(a3);
  StringCchPrintfW(v33, 0x104u, L"\"%s%s", a2, LastItem);
  memset_0(v26, 0, 0x7A4u);
  if ( InitUNZIPCMDSTRUCT((struct UNZIPCMDSTRUCT *)v26, a1, 0, 0, 0) < 0 )
    return 0xFFFFFFFFLL;
  FileAttributesW = GetFileAttributesW(a3);
  v12 = FileAttributesW;
  v13 = FileAttributesW & 0x10;
  if ( (FileAttributesW & 0x10) == 0 || FileAttributesW == -1 )
  {
    v29 = 1;
  }
  else
  {
    v29 = 0;
    StringCchCatW(v33, 0x104u, L"\\");
  }
  StringCchCatW(v33, 0x104u, L"\"");
  PathFixSeparators(v33);
  v27 = 3;
  v28 = v33;
  v30 = 0;
  v14 = dunzip(v26);
  if ( v14 > 9 )
    return 0xFFFFFFFFLL;
  v15 = 521;
  if ( !_bittest(&v15, v14) )
    return 0xFFFFFFFFLL;
  if ( !v30 )
  {
    *a7 = 0;
    return 6;
  }
  if ( !v13 || v12 == -1 )
  {
    v19 = 7;
    StringCchCopyW(pszPath, 0x104u, a1);
    if ( PathCchAppend(pszPath, 0x104u, pszMore) < 0 )
      return v19;
    PathFixSeparators(pszPath);
    if ( PathCchAppend(pszPath, 0x104u, LastItem) < 0 )
      return v19;
    memset_0(v20, 0, 0x68u);
    v20[0] = 104;
    v20[2] = 0;
    v21 = 2;
    v23 = v31;
    v22 = STCONFIRM_REPLACE_STREAM;
    v25[4] = hWnd;
    if ( SHCreateItemFromParsingName(a3, 0, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &ppv) < 0 )
      return v19;
    if ( SHCreateItemFromParsingName(pszPath, 0, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, v25) < 0 )
    {
LABEL_29:
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
      return v19;
    }
    LODWORD(pszMore) = 0;
    v31 = 0;
    if ( (int)SHConfirmOperation(v20, &v31, &pszMore) >= 0 )
    {
      if ( !v31 )
      {
LABEL_27:
        v19 = 6;
        goto LABEL_28;
      }
      if ( v31 != 1 )
      {
        if ( v31 != 2 && v31 != 3 )
        {
          if ( (unsigned int)(v31 - 4) <= 1 )
            v19 = 2;
          goto LABEL_28;
        }
        goto LABEL_27;
      }
    }
LABEL_28:
    (*(void (__fastcall **)(void *))(*(_QWORD *)v25[0] + 16LL))(v25[0]);
    goto LABEL_29;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_ID53375151>::GetImpl'::`2'::impl) )
  {
    FileNameW = PathFindFileNameW(a3);
    MessageBoxHelper::ShellMessageBoxTextScaled_unsigned_short___(
      g_hmodThisDll,
      hWnd,
      (LPCWSTR)0x27E6,
      (LPCWSTR)0x2780,
      0x30u,
      (__int64)FileNameW);
  }
  else
  {
    v18 = PathFindFileNameW(a3);
    ShellMessageBoxW(g_hmodThisDll, hWnd, (LPCWSTR)0x27E6, (LPCWSTR)0x2780, 0x30u, v18);
  }
  return 7;
}

```

## disassembly

```asm
0x18000b0bc  push    rbp
0x18000b0be  push    rbx
0x18000b0bf  push    rsi
0x18000b0c0  push    rdi
0x18000b0c1  push    r12
0x18000b0c3  push    r13
0x18000b0c5  push    r14
0x18000b0c7  push    r15
0x18000b0c9  lea     rbp, [rsp-0B98h]
0x18000b0d1  sub     rsp, 0C98h
0x18000b0d8  mov     rax, cs:__security_cookie
0x18000b0df  xor     rax, rsp
0x18000b0e2  mov     [rbp+0BD0h+var_50], rax
0x18000b0e9  mov     r15, [rbp+0BD0h+arg_30]
0x18000b0f0  mov     r13, rcx
0x18000b0f3  mov     r14, [rbp+0BD0h+hWnd]
0x18000b0fa  mov     rcx, r8; unsigned __int16 *
0x18000b0fd  mov     [rbp+0BD0h+var_480], r9d
0x18000b104  mov     rsi, r8
0x18000b107  mov     rbx, rdx
0x18000b10a  mov     [rbp+0BD0h+pszMore], rdx
0x18000b111  mov     dword ptr [r15], 1
0x18000b118  call    ?PathFindLastItem@@YAPEAGPEAG@Z; PathFindLastItem(ushort *)
0x18000b11d  mov     r9, rbx
0x18000b120  mov     qword ptr [rsp+0CD0h+fuStyle], rax
0x18000b125  lea     r8, aSS; "\"%s%s"
0x18000b12c  mov     edx, 104h; unsigned __int64
0x18000b131  lea     rcx, [rbp+0BD0h+var_470]; unsigned __int16 *
0x18000b138  mov     r12, rax
0x18000b13b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000b140  xor     edx, edx; Val
0x18000b142  lea     rcx, [rbp+0BD0h+var_C30]; void *
0x18000b146  mov     r8d, 7A4h; Size
0x18000b14c  call    memset_0
0x18000b151  xor     r9d, r9d; unsigned __int16 *
0x18000b154  mov     qword ptr [rsp+0CD0h+fuStyle], 0; unsigned __int16 *
0x18000b15d  xor     r8d, r8d; unsigned __int16 *
0x18000b160  lea     rcx, [rbp+0BD0h+var_C30]; struct UNZIPCMDSTRUCT *
0x18000b164  mov     rdx, r13; unsigned __int16 *
0x18000b167  call    ?InitUNZIPCMDSTRUCT@@YAJPEAUUNZIPCMDSTRUCT@@PEBG111@Z; InitUNZIPCMDSTRUCT(UNZIPCMDSTRUCT *,ushort const *,ushort const *,ushort const *,ushort const *)
0x18000b16c  test    eax, eax
0x18000b16e  js      loc_18000B403
0x18000b174  mov     rcx, rsi; lpFileName
0x18000b177  call    cs:__imp_GetFileAttributesW
0x18000b17d  mov     edi, eax
0x18000b17f  mov     ebx, eax
0x18000b181  and     edi, 10h
0x18000b184  jz      short loc_18000B1AC
0x18000b186  cmp     eax, 0FFFFFFFFh
0x18000b189  jz      short loc_18000B1AC
0x18000b18b  lea     r8, asc_180078AAC; "\\"
0x18000b192  mov     [rbp+0BD0h+var_BFC], 0
0x18000b199  mov     edx, 104h; unsigned __int64
0x18000b19e  lea     rcx, [rbp+0BD0h+var_470]; unsigned __int16 *
0x18000b1a5  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000b1aa  jmp     short loc_18000B1B3
0x18000b1ac  mov     [rbp+0BD0h+var_BFC], 1
0x18000b1b3  lea     r8, asc_180079070; "\""
0x18000b1ba  mov     edx, 104h; unsigned __int64
0x18000b1bf  lea     rcx, [rbp+0BD0h+var_470]; unsigned __int16 *
0x18000b1c6  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000b1cb  lea     rcx, [rbp+0BD0h+var_470]; unsigned __int16 *
0x18000b1d2  call    ?PathFixSeparators@@YAXPEAG@Z; PathFixSeparators(ushort *)
0x18000b1d7  lea     rax, [rbp+0BD0h+var_470]
0x18000b1de  mov     [rbp+0BD0h+var_C2C], 3
0x18000b1e5  lea     rcx, [rbp+0BD0h+var_C30]
0x18000b1e9  mov     [rbp+0BD0h+var_C20], rax
0x18000b1ed  mov     [rbp+0BD0h+var_BE8], 0
0x18000b1f4  call    dunzip
0x18000b1f9  cmp     eax, 9
0x18000b1fc  ja      loc_18000B403
0x18000b202  mov     ecx, 209h
0x18000b207  bt      ecx, eax
0x18000b20a  jnb     loc_18000B403
0x18000b210  cmp     [rbp+0BD0h+var_BE8], 0
0x18000b214  jnz     short loc_18000B227
0x18000b216  mov     dword ptr [r15], 0
0x18000b21d  mov     eax, 6
0x18000b222  jmp     loc_18000B406
0x18000b227  xor     r15d, r15d
0x18000b22a  test    edi, edi
0x18000b22c  jz      short loc_18000B2AB
0x18000b22e  cmp     ebx, 0FFFFFFFFh
0x18000b231  jz      short loc_18000B2AB
0x18000b233  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID53375151@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID53375151@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151> `wil::Feature<__WilFeatureTraits_Feature_ID53375151>::GetImpl(void)'::`2'::impl
0x18000b23a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ID53375151@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151>::__private_IsEnabled(void)
0x18000b23f  mov     rcx, rsi; pszPath
0x18000b242  test    al, al
0x18000b244  jz      short loc_18000B274
0x18000b246  call    cs:__imp_PathFindFileNameW
0x18000b24c  mov     rcx, cs:g_hmodThisDll; hAppInst
0x18000b253  mov     r9d, 2780h; lpcTitle
0x18000b259  mov     [rsp+0CD0h+var_CA8], rax; __int64
0x18000b25e  mov     rdx, r14; hWnd
0x18000b261  mov     [rsp+0CD0h+fuStyle], 30h ; '0'; UINT
0x18000b269  lea     r8d, [r9+66h]; lpcText
0x18000b26d  call    MessageBoxHelper__ShellMessageBoxTextScaled_unsigned_short___
0x18000b272  jmp     short loc_18000B2A1
0x18000b274  call    cs:__imp_PathFindFileNameW
0x18000b27a  mov     rcx, cs:g_hmodThisDll; hAppInst
0x18000b281  mov     r9d, 2780h; lpcTitle
0x18000b287  mov     [rsp+0CD0h+var_CA8], rax
0x18000b28c  mov     rdx, r14; hWnd
0x18000b28f  mov     [rsp+0CD0h+fuStyle], 30h ; '0'; fuStyle
0x18000b297  lea     r8d, [r9+66h]; lpcText
0x18000b29b  call    cs:__imp_ShellMessageBoxW
0x18000b2a1  mov     eax, 7
0x18000b2a6  jmp     loc_18000B406
0x18000b2ab  mov     edi, 104h
0x18000b2b0  lea     rcx, [rbp+0BD0h+pszPath]; unsigned __int16 *
0x18000b2b7  mov     edx, edi; unsigned __int64
0x18000b2b9  mov     r8, r13; unsigned __int16 *
0x18000b2bc  mov     ebx, 7
0x18000b2c1  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000b2c6  mov     r8, [rbp+0BD0h+pszMore]; pszMore
0x18000b2cd  lea     rcx, [rbp+0BD0h+pszPath]; pszPath
0x18000b2d4  mov     edx, edi; cchPath
0x18000b2d6  call    cs:__imp_PathCchAppend
0x18000b2dc  test    eax, eax
0x18000b2de  js      loc_18000B3FF
0x18000b2e4  lea     rcx, [rbp+0BD0h+pszPath]; unsigned __int16 *
0x18000b2eb  call    ?PathFixSeparators@@YAXPEAG@Z; PathFixSeparators(ushort *)
0x18000b2f0  lea     rcx, [rbp+0BD0h+pszPath]; pszPath
0x18000b2f7  mov     r8, r12; pszMore
0x18000b2fa  mov     edx, edi; cchPath
0x18000b2fc  call    cs:__imp_PathCchAppend
0x18000b302  test    eax, eax
0x18000b304  js      loc_18000B3FF
0x18000b30a  lea     edi, [rbx+61h]
0x18000b30d  xor     edx, edx; Val
0x18000b30f  mov     r8d, edi; Size
0x18000b312  lea     rcx, [rsp+0CD0h+var_CA0]; void *
0x18000b317  call    memset_0
0x18000b31c  movups  xmm0, cs:STCONFIRM_REPLACE_STREAM
0x18000b323  mov     eax, [rbp+0BD0h+var_480]
0x18000b329  lea     r9, [rsp+0CD0h+ppv]; ppv
0x18000b32e  mov     [rsp+0CD0h+var_CA0], edi
0x18000b332  lea     r8, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x18000b339  lea     edi, [rbx-5]
0x18000b33c  mov     [rsp+0CD0h+var_C98], r15d
0x18000b341  xor     edx, edx; pbc
0x18000b343  mov     [rsp+0CD0h+var_C94], rdi
0x18000b348  mov     rcx, rsi; pszPath
0x18000b34b  mov     [rsp+0CD0h+var_C74], eax
0x18000b34f  movdqu  [rsp+0CD0h+var_C8C], xmm0
0x18000b355  mov     [rbp+0BD0h+var_C48], r14
0x18000b359  call    cs:__imp_SHCreateItemFromParsingName
0x18000b35f  test    eax, eax
0x18000b361  js      loc_18000B3FF
0x18000b367  lea     r9, [rsp+0CD0h+var_C68]; ppv
0x18000b36c  xor     edx, edx; pbc
0x18000b36e  lea     r8, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x18000b375  lea     rcx, [rbp+0BD0h+pszPath]; pszPath
0x18000b37c  call    cs:__imp_SHCreateItemFromParsingName
0x18000b382  test    eax, eax
0x18000b384  js      short loc_18000B3EE
0x18000b386  lea     r8, [rbp+0BD0h+pszMore]
0x18000b38d  mov     dword ptr [rbp+0BD0h+pszMore], r15d
0x18000b394  lea     rdx, [rbp+0BD0h+var_480]
0x18000b39b  mov     [rbp+0BD0h+var_480], r15d
0x18000b3a2  lea     rcx, [rsp+0CD0h+var_CA0]
0x18000b3a7  call    cs:__imp_SHConfirmOperation
0x18000b3ad  test    eax, eax
0x18000b3af  js      short loc_18000B3DD
0x18000b3b1  mov     ecx, [rbp+0BD0h+var_480]
0x18000b3b7  test    ecx, ecx
0x18000b3b9  jz      short loc_18000B3D8
0x18000b3bb  sub     ecx, 1
0x18000b3be  jz      short loc_18000B3DD
0x18000b3c0  sub     ecx, 1
0x18000b3c3  jz      short loc_18000B3D8
0x18000b3c5  sub     ecx, 1
0x18000b3c8  jz      short loc_18000B3D8
0x18000b3ca  sub     ecx, 1
0x18000b3cd  jz      short loc_18000B3D4
0x18000b3cf  cmp     ecx, 1
0x18000b3d2  jnz     short loc_18000B3DD
0x18000b3d4  mov     ebx, edi
0x18000b3d6  jmp     short loc_18000B3DD
0x18000b3d8  mov     ebx, 6
0x18000b3dd  mov     rcx, [rsp+0CD0h+var_C68]
0x18000b3e2  mov     rax, [rcx]
0x18000b3e5  mov     rax, [rax+10h]
0x18000b3e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b3ee  mov     rcx, [rsp+0CD0h+ppv]
0x18000b3f3  mov     rdx, [rcx]
0x18000b3f6  mov     rax, [rdx+10h]
0x18000b3fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b3ff  mov     eax, ebx
0x18000b401  jmp     short loc_18000B406
0x18000b403  or      eax, 0FFFFFFFFh
0x18000b406  mov     rcx, [rbp+0BD0h+var_50]
0x18000b40d  xor     rcx, rsp; StackCookie
0x18000b410  call    __security_check_cookie
0x18000b415  add     rsp, 0C98h
0x18000b41c  pop     r15
0x18000b41e  pop     r14
0x18000b420  pop     r13
0x18000b422  pop     r12
0x18000b424  pop     rdi
0x18000b425  pop     rsi
0x18000b426  pop     rbx
0x18000b427  pop     rbp
0x18000b428  retn
```
