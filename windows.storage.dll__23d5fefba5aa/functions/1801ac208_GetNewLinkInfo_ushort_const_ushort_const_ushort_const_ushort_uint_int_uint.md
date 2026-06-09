# _GetNewLinkInfo(ushort const *,ushort const *,ushort const *,ushort *,uint,int *,uint)

- ea: `0x1801ac208`
- end: `0x1801ac5c4`
- name: `?_GetNewLinkInfo@@YAHPEBG00PEAGIPEAHI@Z`
- size: `956`
- prototype: `__int64 __usercall@<rax>(LPCWSTR pszPath@<rcx>, const unsigned __int16 *@<rdx>, const unsigned __int16 *@<r8>, unsigned __int16 *@<r9>, unsigned int, int *, unsigned int)`
- caller_count: `3`
- callee_count: `12`
- tags: `reparse_path, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1801abdb0`
- `0x1805cc630`
- `0x1805cc760`

## callees

- `0x180063050`
- `0x180133f50`
- `0x180144260`
- `0x18015b0b0`
- `0x180171de0`
- `0x1801ac208`
- `0x1801ac5cc`
- `0x1801ac628`
- `0x1801ac668`
- `0x1801ac940`
- `0x1803b1f60`
- `0x1803b2ac0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18066fbca`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18066fbca`
- `api-ms-win-core-path-l1-1-0!PathCchRenameExtension` at `0x1801ac3fe`
- `api-ms-win-core-path-l1-1-0!PathCchRenameExtension` at `0x1801ac3fe`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveExtensionW` at `0x1801ac57e`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveExtensionW` at `0x1801ac57e`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x18066fb59`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x18066fb59`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRootW` at `0x1801ac39d`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRootW` at `0x1801ac39d`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1801ac4a9`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1801ac4a9`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x18066fb74`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x18066fb90`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x18066fb74`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x18066fb90`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801ac37c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801ac37c`
- `SHCORE!__imp_DriveType` at `0x18066fb9e`
- `SHCORE!__imp_DriveType` at `0x18066fb9e`

## pseudocode

```c
_BOOL8 __fastcall _GetNewLinkInfo(
        LPCWSTR pszPath,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned int a5,
        int *a6,
        char a7)
{
  const unsigned __int16 *v8; // rdi
  char v11; // si
  BOOL v12; // r14d
  const ITEMIDLIST *v13; // r13
  DWORD dwAttributes; // edi
  __int64 v15; // r15
  int *v16; // rdi
  const WCHAR *v17; // rdi
  const WCHAR *v18; // r8
  __int64 v20; // rcx
  WCHAR *p_pszPatha; // rax
  __int64 v22; // rdx
  WCHAR *v23; // rcx
  bool v24; // cf
  LPWSTR FileNameW; // rax
  __int64 v26; // rdx
  WCHAR *szDisplayName; // r8
  WCHAR *v28; // rcx
  int DriveNumberW; // eax
  LPVOID pv[2]; // [rsp+40h] [rbp-C0h] BYREF
  SHFILEINFOW psfi; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR pszPatha; // [rsp+310h] [rbp+210h] BYREF
  _BYTE v34[526]; // [rsp+312h] [rbp+212h] BYREF

  v8 = a2;
  *a4 = 0;
  *a6 = 0;
  memset_0(&psfi, 0, sizeof(psfi));
  v11 = a7;
  v12 = 1;
  psfi.dwAttributes = 1614872576;
  v13 = (const ITEMIDLIST *)((unsigned __int64)pszPath & -(__int64)((a7 & 1) != 0));
  if ( v13 )
  {
    if ( (int)SHGetNameAndFlagsW(
                (LPCITEMIDLIST)((unsigned __int64)pszPath & -(__int64)((a7 & 1) != 0)),
                (a7 & 0x10) != 0 ? 0x8001 : 0,
                psfi.szDisplayName,
                0x104u,
                &psfi.dwAttributes) < 0 )
      return 0;
    if ( (a7 & 0x10) != 0 )
      PathRemoveExtensionW(psfi.szDisplayName);
    v8 = a2;
  }
  else if ( !SHGetFileInfoW(pszPath, 0, &psfi, 0x2B8u, 0x20A00u) )
  {
    return 0;
  }
  if ( a3 && (int)StringCchCopyW(psfi.szDisplayName, 0x104u, a3) < 0
    || (int)PathCleanupSpecEx(v8, psfi.szDisplayName) < 0 )
  {
    return 0;
  }
  dwAttributes = psfi.dwAttributes;
  if ( (psfi.dwAttributes & 0x40000000) == 0 )
  {
LABEL_17:
    v16 = a6;
    goto LABEL_18;
  }
  pszPatha = 0;
  memset_0(v34, 0, 0x206u);
  v15 = 2147483646;
  if ( v13 )
  {
    pszPatha = 0;
    pv[0] = 0;
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(pv);
    if ( (int)SHGetPathFromIDListAlloc(v13) >= 0 )
      StringCchCopyW(&pszPatha, 0x104u, (const unsigned __int16 *)pv[0]);
    if ( pv[0] )
      CoTaskMemFree(pv[0]);
    dwAttributes = psfi.dwAttributes;
  }
  else
  {
    v20 = 2147483646;
    p_pszPatha = &pszPatha;
    v22 = 260;
    do
    {
      if ( !v20 )
        break;
      if ( !*pszPath )
        break;
      *p_pszPatha++ = *pszPath++;
      --v20;
      --v22;
    }
    while ( v22 );
    v23 = p_pszPatha - 1;
    if ( v22 )
      v23 = p_pszPatha;
    *v23 = 0;
  }
  if ( (dwAttributes & 0x10000) == 0 )
  {
    if ( PathIsRootW(&pszPatha) )
    {
      if ( !PathIsUNCW(&pszPatha) && PathGetDriveNumberW(&pszPatha) != -1 )
      {
        DriveNumberW = PathGetDriveNumberW(&pszPatha);
        if ( DriveType(DriveNumberW) == 5 )
          LoadStringW(g_hinst, 0x2465u, psfi.szDisplayName, 260);
      }
    }
    goto LABEL_17;
  }
  v24 = (dwAttributes & 0x400000) != 0;
  v16 = a6;
  if ( v24 )
  {
    v11 = a7 & 0xF7;
    *a6 = 1;
    FileNameW = PathFindFileNameW(&pszPatha);
    v26 = 260;
    szDisplayName = psfi.szDisplayName;
    do
    {
      if ( !v15 )
        break;
      if ( !*FileNameW )
        break;
      *szDisplayName++ = *FileNameW++;
      --v15;
      --v26;
    }
    while ( v26 );
    v28 = szDisplayName - 1;
    if ( v26 )
      v28 = szDisplayName;
    *v28 = 0;
    if ( !v26 )
      return 0;
  }
LABEL_18:
  if ( *v16 )
  {
    StringCchCopyW(a4, 0x104u, psfi.szDisplayName);
    v17 = a2;
  }
  else
  {
    v17 = a2;
    _BuildLinkName(a4, 0x104u, psfi.szDisplayName, a2, v11 & 2);
  }
  if ( (v11 & 8) != 0 )
  {
    v18 = L".";
  }
  else
  {
    if ( (v11 & 0x20) == 0 )
      goto LABEL_23;
    v18 = L".url";
  }
  PathCchRenameExtension(a4, 0x104u, v18);
LABEL_23:
  if ( (v11 & 4) == 0 )
  {
    if ( PathYetAnotherMakeUniqueName(&pszPatha, v17, a4, a4) )
      v12 = (int)StringCchCopyW(a4, 0x104u, &pszPatha) >= 0;
  }
  PathStripTrailingDots(a4);
  return v12;
}

```

## disassembly

```asm
0x1801ac208  push    rbp
0x1801ac20a  push    rbx
0x1801ac20b  push    rsi
0x1801ac20c  push    rdi
0x1801ac20d  push    r12
0x1801ac20f  push    r13
0x1801ac211  push    r14
0x1801ac213  push    r15
0x1801ac215  lea     rbp, [rsp-438h]
0x1801ac21d  sub     rsp, 538h
0x1801ac224  mov     rax, cs:__security_cookie
0x1801ac22b  xor     rax, rsp
0x1801ac22e  mov     [rbp+470h+var_50], rax
0x1801ac235  mov     r12, rcx
0x1801ac238  mov     [rsp+570h+var_538], rdx
0x1801ac23d  mov     rcx, [rbp+470h+arg_28]
0x1801ac244  mov     rdi, rdx
0x1801ac247  xor     edx, edx; Val
0x1801ac249  mov     [rsp+570h+var_540], rcx
0x1801ac24e  mov     [r9], dx
0x1801ac252  mov     r15, r8
0x1801ac255  mov     r8d, 2B8h; Size
0x1801ac25b  mov     rbx, r9
0x1801ac25e  mov     [rcx], edx
0x1801ac260  lea     rcx, [rsp+570h+psfi]; void *
0x1801ac265  call    memset_0
0x1801ac26a  mov     esi, [rbp+470h+arg_30]
0x1801ac270  mov     r14d, 1
0x1801ac276  mov     eax, esi
0x1801ac278  mov     [rsp+570h+psfi.dwAttributes], 60410000h
0x1801ac280  and     al, r14b
0x1801ac283  neg     al
0x1801ac285  sbb     r13, r13
0x1801ac288  and     r13, r12
0x1801ac28b  jz      loc_1801AC4FC
0x1801ac291  mov     edi, esi
0x1801ac293  lea     r8, [rsp+570h+psfi.szDisplayName]; unsigned __int16 *
0x1801ac298  and     edi, 10h
0x1801ac29b  mov     r9d, 104h; unsigned int
0x1801ac2a1  mov     eax, edi
0x1801ac2a3  mov     rcx, r13; pidl
0x1801ac2a6  neg     eax
0x1801ac2a8  lea     rax, [rsp+570h+psfi.dwAttributes]
0x1801ac2ad  sbb     edx, edx
0x1801ac2af  mov     qword ptr [rsp+570h+uFlags], rax; unsigned int *
0x1801ac2b4  and     edx, 8001h; unsigned int
0x1801ac2ba  call    ?SHGetNameAndFlagsW@@YAJPEBU_ITEMIDLIST_ABSOLUTE@@KPEAGIPEAK@Z; SHGetNameAndFlagsW(_ITEMIDLIST_ABSOLUTE const *,ulong,ushort *,uint,ulong *)
0x1801ac2bf  test    eax, eax
0x1801ac2c1  js      loc_1801AC4F5
0x1801ac2c7  test    edi, edi
0x1801ac2c9  jnz     loc_1801AC579
0x1801ac2cf  mov     rdi, [rsp+570h+var_538]
0x1801ac2d4  test    r15, r15
0x1801ac2d7  jnz     loc_1801AC58F
0x1801ac2dd  lea     rdx, [rsp+570h+psfi.szDisplayName]
0x1801ac2e2  mov     rcx, rdi
0x1801ac2e5  call    PathCleanupSpecEx
0x1801ac2ea  test    eax, eax
0x1801ac2ec  js      loc_1801AC4F5
0x1801ac2f2  mov     edi, [rsp+570h+psfi.dwAttributes]
0x1801ac2f6  bt      edi, 1Eh
0x1801ac2fa  jnb     loc_1801AC3B1
0x1801ac300  xor     eax, eax
0x1801ac302  lea     rcx, [rbp+470h+var_25E]; void *
0x1801ac309  xor     edx, edx; Val
0x1801ac30b  mov     [rbp+470h+pszPath], ax
0x1801ac312  mov     r8d, 206h; Size
0x1801ac318  call    memset_0
0x1801ac31d  mov     r15d, 7FFFFFFEh
0x1801ac323  test    r13, r13
0x1801ac326  jz      loc_1801AC443
0x1801ac32c  xor     eax, eax
0x1801ac32e  lea     rcx, [rsp+570h+pv]
0x1801ac333  mov     [rbp+470h+pszPath], ax
0x1801ac33a  mov     [rsp+570h+pv], rax
0x1801ac33f  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x1801ac344  mov     r8d, 2
0x1801ac34a  mov     rdx, rax
0x1801ac34d  mov     rcx, r13; pidl
0x1801ac350  call    SHGetPathFromIDListAlloc
0x1801ac355  xor     r13d, r13d
0x1801ac358  test    eax, eax
0x1801ac35a  js      short loc_1801AC372
0x1801ac35c  mov     r8, [rsp+570h+pv]; unsigned __int16 *
0x1801ac361  lea     rcx, [rbp+470h+pszPath]; unsigned __int16 *
0x1801ac368  mov     edx, 104h; unsigned __int64
0x1801ac36d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1801ac372  mov     rcx, [rsp+570h+pv]; pv
0x1801ac377  test    rcx, rcx
0x1801ac37a  jz      short loc_1801AC388
0x1801ac37c  call    cs:__imp_CoTaskMemFree
0x1801ac383  nop     dword ptr [rax+rax+00h]
0x1801ac388  mov     edi, [rsp+570h+psfi.dwAttributes]
0x1801ac38c  bt      edi, 10h
0x1801ac390  jb      loc_1801AC48D
0x1801ac396  lea     rcx, [rbp+470h+pszPath]; pszPath
0x1801ac39d  call    cs:__imp_PathIsRootW
0x1801ac3a4  nop     dword ptr [rax+rax+00h]
0x1801ac3a9  test    eax, eax
0x1801ac3ab  jnz     loc_18066FB52
0x1801ac3b1  mov     rdi, [rsp+570h+var_540]
0x1801ac3b6  xor     r12d, r12d
0x1801ac3b9  lea     r8, [rsp+570h+psfi.szDisplayName]; unsigned __int16 *
0x1801ac3be  mov     rcx, rbx; unsigned __int16 *
0x1801ac3c1  cmp     [rdi], r12d
0x1801ac3c4  jnz     loc_1801AC524
0x1801ac3ca  mov     rdi, [rsp+570h+var_538]
0x1801ac3cf  mov     eax, esi
0x1801ac3d1  and     eax, 2
0x1801ac3d4  mov     r9, rdi; unsigned __int16 *
0x1801ac3d7  mov     edx, 104h; unsigned int
0x1801ac3dc  mov     [rsp+570h+uFlags], eax; int
0x1801ac3e0  call    ?_BuildLinkName@@YAXPEAGIPEBG1H@Z; _BuildLinkName(ushort *,uint,ushort const *,ushort const *,int)
0x1801ac3e5  test    sil, 8
0x1801ac3e9  jz      loc_1801AC5AE
0x1801ac3ef  lea     r8, pszExt; "."
0x1801ac3f6  mov     edx, 104h; cchPath
0x1801ac3fb  mov     rcx, rbx; pszPath
0x1801ac3fe  call    cs:__imp_PathCchRenameExtension
0x1801ac405  nop     dword ptr [rax+rax+00h]
0x1801ac40a  test    sil, 4
0x1801ac40e  jz      loc_1801AC538
0x1801ac414  mov     rcx, rbx; unsigned __int16 *
0x1801ac417  call    ?PathStripTrailingDots@@YAXPEAG@Z; PathStripTrailingDots(ushort *)
0x1801ac41c  mov     eax, r14d
0x1801ac41f  mov     rcx, [rbp+470h+var_50]
0x1801ac426  xor     rcx, rsp; StackCookie
0x1801ac429  call    __security_check_cookie
0x1801ac42e  add     rsp, 538h
0x1801ac435  pop     r15
0x1801ac437  pop     r14
0x1801ac439  pop     r13
0x1801ac43b  pop     r12
0x1801ac43d  pop     rdi
0x1801ac43e  pop     rsi
0x1801ac43f  pop     rbx
0x1801ac440  pop     rbp
0x1801ac441  retn
0x1801ac443  mov     rcx, r15
0x1801ac446  lea     rax, [rbp+470h+pszPath]
0x1801ac44d  mov     edx, 104h
0x1801ac452  xor     r13d, r13d
0x1801ac455  test    rcx, rcx
0x1801ac458  jz      short loc_1801AC479
0x1801ac45a  movzx   r8d, word ptr [r12]
0x1801ac45f  test    r8w, r8w
0x1801ac463  jz      short loc_1801AC479
0x1801ac465  mov     [rax], r8w
0x1801ac469  add     r12, 2
0x1801ac46d  add     rax, 2
0x1801ac471  sub     rcx, r14
0x1801ac474  sub     rdx, r14
0x1801ac477  jnz     short loc_1801AC455
0x1801ac479  test    rdx, rdx
0x1801ac47c  lea     rcx, [rax-2]
0x1801ac480  cmovnz  rcx, rax
0x1801ac484  mov     [rcx], r13w
0x1801ac488  jmp     loc_1801AC38C
0x1801ac48d  bt      edi, 16h
0x1801ac491  mov     rdi, [rsp+570h+var_540]
0x1801ac496  jnb     loc_1801AC3B6
0x1801ac49c  and     esi, 0FFFFFFF7h
0x1801ac49f  mov     [rdi], r14d
0x1801ac4a2  lea     rcx, [rbp+470h+pszPath]; pszPath
0x1801ac4a9  call    cs:__imp_PathFindFileNameW
0x1801ac4b0  nop     dword ptr [rax+rax+00h]
0x1801ac4b5  mov     edx, 104h
0x1801ac4ba  lea     r8, [rsp+570h+psfi.szDisplayName]
0x1801ac4bf  test    r15, r15
0x1801ac4c2  jz      short loc_1801AC4E0
0x1801ac4c4  movzx   ecx, word ptr [rax]
0x1801ac4c7  test    cx, cx
0x1801ac4ca  jz      short loc_1801AC4E0
0x1801ac4cc  mov     [r8], cx
0x1801ac4d0  add     rax, 2
0x1801ac4d4  add     r8, 2
0x1801ac4d8  sub     r15, r14
0x1801ac4db  sub     rdx, r14
0x1801ac4de  jnz     short loc_1801AC4BF
0x1801ac4e0  test    rdx, rdx
0x1801ac4e3  lea     rcx, [r8-2]
0x1801ac4e7  cmovnz  rcx, r8
0x1801ac4eb  mov     [rcx], r13w
0x1801ac4ef  jnz     loc_1801AC3B6
0x1801ac4f5  xor     eax, eax
0x1801ac4f7  jmp     loc_1801AC41F
0x1801ac4fc  mov     r9d, 2B8h; cbFileInfo
0x1801ac502  mov     [rsp+570h+uFlags], 20A00h; uFlags
0x1801ac50a  lea     r8, [rsp+570h+psfi]; psfi
0x1801ac50f  xor     edx, edx; dwFileAttributes
0x1801ac511  mov     rcx, r12; pszPath
0x1801ac514  call    SHGetFileInfoW
0x1801ac519  test    rax, rax
0x1801ac51c  jnz     loc_1801AC2D4
0x1801ac522  jmp     short loc_1801AC4F5
0x1801ac524  mov     edx, 104h; unsigned __int64
0x1801ac529  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1801ac52e  mov     rdi, [rsp+570h+var_538]
0x1801ac533  jmp     loc_1801AC3E5
0x1801ac538  mov     r9, rbx; pszFileSpec
0x1801ac53b  lea     rcx, [rbp+470h+pszPath]; pszUniqueName
0x1801ac542  mov     r8, rbx; pszShort
0x1801ac545  mov     rdx, rdi; pszPath
0x1801ac548  call    PathYetAnotherMakeUniqueName
0x1801ac54d  test    eax, eax
0x1801ac54f  jz      loc_1801AC414
0x1801ac555  lea     r8, [rbp+470h+pszPath]; unsigned __int16 *
0x1801ac55c  mov     edx, 104h; unsigned __int64
0x1801ac561  mov     rcx, rbx; unsigned __int16 *
0x1801ac564  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1801ac569  mov     edx, r12d
0x1801ac56c  test    eax, eax
0x1801ac56e  setns   dl
0x1801ac571  mov     r14d, edx
0x1801ac574  jmp     loc_1801AC414
0x1801ac579  lea     rcx, [rsp+570h+psfi.szDisplayName]; pszPath
0x1801ac57e  call    cs:__imp_PathRemoveExtensionW
0x1801ac585  nop     dword ptr [rax+rax+00h]
0x1801ac58a  jmp     loc_1801AC2CF
0x1801ac58f  mov     r8, r15; unsigned __int16 *
0x1801ac592  lea     rcx, [rsp+570h+psfi.szDisplayName]; unsigned __int16 *
0x1801ac597  mov     edx, 104h; unsigned __int64
0x1801ac59c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1801ac5a1  test    eax, eax
0x1801ac5a3  js      loc_1801AC4F5
0x1801ac5a9  jmp     loc_1801AC2DD
0x1801ac5ae  test    sil, 20h
0x1801ac5b2  jz      loc_1801AC40A
0x1801ac5b8  lea     r8, aUrl; ".url"
0x1801ac5bf  jmp     loc_1801AC3F6
0x18066fb52  lea     rcx, [rbp+470h+pszPath]; pszPath
0x18066fb59  call    cs:__imp_PathIsUNCW
0x18066fb60  nop     dword ptr [rax+rax+00h]
0x18066fb65  test    eax, eax
0x18066fb67  jnz     loc_1801AC3B1
0x18066fb6d  lea     rcx, [rbp+470h+pszPath]; pszPath
0x18066fb74  call    cs:__imp_PathGetDriveNumberW
0x18066fb7b  nop     dword ptr [rax+rax+00h]
0x18066fb80  cmp     eax, 0FFFFFFFFh
0x18066fb83  jz      loc_1801AC3B1
0x18066fb89  lea     rcx, [rbp+470h+pszPath]; pszPath
0x18066fb90  call    cs:__imp_PathGetDriveNumberW
0x18066fb97  nop     dword ptr [rax+rax+00h]
0x18066fb9c  mov     ecx, eax; iDrive
0x18066fb9e  call    cs:__imp_DriveType
0x18066fba5  nop     dword ptr [rax+rax+00h]
0x18066fbaa  cmp     eax, 5
0x18066fbad  jnz     loc_1801AC3B1
0x18066fbb3  mov     rcx, cs:g_hinst; hInstance
0x18066fbba  lea     r8, [rsp+570h+psfi.szDisplayName]; lpBuffer
0x18066fbbf  mov     r9d, 104h; cchBufferMax
0x18066fbc5  mov     edx, 2465h; uID
0x18066fbca  call    cs:__imp_LoadStringW
0x18066fbd1  nop     dword ptr [rax+rax+00h]
0x18066fbd6  nop
0x18066fbd7  jmp     loc_1801AC3B1
```
