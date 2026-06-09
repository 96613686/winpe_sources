# CFSFolder::_CreateIDList(tagWIN32_FIND_DATA_EX const *,_ITEMIDLIST_RELATIVE const *,ushort const *,ushort const *,IDLHID,CREATE_IDLIST_FLAGS,FOLDER_ENUM_MODE,_ITEMID_CHILD * *)

- ea: `0x18006a8c0`
- end: `0x18006b691`
- name: `?_CreateIDList@CFSFolder@@IEAAJPEBUtagWIN32_FIND_DATA_EX@@PEFBU_ITEMIDLIST_RELATIVE@@PEBG2W4IDLHID@@W4CREATE_IDLIST_FLAGS@@W4FOLDER_ENUM_MODE@@PEAPEAU_ITEMID_CHILD@@@Z`
- size: `3537`
- prototype: ``
- caller_count: `5`
- callee_count: `23`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800694d0`
- `0x180069550`
- `0x18006c460`
- `0x1800f1680`
- `0x1800f1da0`

## callees

- `0x180038f80`
- `0x180045230`
- `0x180048ad0`
- `0x1800693a0`
- `0x18006a8c0`
- `0x18006b698`
- `0x18006b770`
- `0x18006b970`
- `0x18006ba00`
- `0x18008ecb0`
- `0x1801c8bc0`
- `0x1801caa30`
- `0x1801d5130`
- `0x1801d8c20`
- `0x1801e6d08`
- `0x180201330`
- `0x180363da4`
- `0x1803b1f60`
- `0x1803b2ac0`
- `0x1803b2ea5`
- `0x1803b69b9`
- `0x1803b69c5`
- `0x18067d010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006b29f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006b29f`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x18006b0a2`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x18006b0a2`
- `api-ms-win-core-kernel32-legacy-l1-1-0!DosDateTimeToFileTime` at `0x18006acac`
- `api-ms-win-core-kernel32-legacy-l1-1-0!DosDateTimeToFileTime` at `0x18006acac`
- `api-ms-win-core-kernel32-legacy-l1-1-0!FileTimeToDosDateTime` at `0x18006aafc`
- `api-ms-win-core-kernel32-legacy-l1-1-0!FileTimeToDosDateTime` at `0x18006abb5`
- `api-ms-win-core-kernel32-legacy-l1-1-0!FileTimeToDosDateTime` at `0x18006abe4`
- `api-ms-win-core-kernel32-legacy-l1-1-0!FileTimeToDosDateTime` at `0x18006ac8b`
- `api-ms-win-core-kernel32-legacy-l1-1-0!FileTimeToDosDateTime` at `0x18006aafc`
- `api-ms-win-core-kernel32-legacy-l1-1-0!FileTimeToDosDateTime` at `0x18006abb5`
- `api-ms-win-core-kernel32-legacy-l1-1-0!FileTimeToDosDateTime` at `0x18006abe4`
- `api-ms-win-core-kernel32-legacy-l1-1-0!FileTimeToDosDateTime` at `0x18006ac8b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006aa4f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006b1bc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006b306`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006aa4f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006b1bc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006b306`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x18006aa76`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x18006aa76`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006ae11`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006ae26`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006ae3b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006aee6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006b005`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006b166`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006b37d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006b52f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006b5e0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006b609`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006ae11`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006ae26`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006ae3b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006aee6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006b005`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006b166`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006b37d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006b52f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006b5e0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006b609`
- `SHCORE!__imp_SHRegGetCLSIDKey` at `0x18006b287`
- `SHCORE!__imp_SHRegGetCLSIDKey` at `0x18006b287`
- `SHCORE!__imp_IsAppCompatModeEnabled` at `0x18006ae5e`
- `SHCORE!__imp_IsAppCompatModeEnabled` at `0x18006ae5e`
- `SHCORE!__imp_GUIDFromStringW` at `0x18006b5b5`
- `SHCORE!__imp_GUIDFromStringW` at `0x18006b5b5`
- `SHCORE!__imp_ualstrcpynW` at `0x18006ac37`
- `SHCORE!__imp_ualstrcpynW` at `0x18006ac61`
- `SHCORE!__imp_ualstrcpynW` at `0x18006b569`
- `SHCORE!__imp_ualstrcpynW` at `0x18006b680`
- `SHCORE!__imp_ualstrcpynW` at `0x18006ac37`
- `SHCORE!__imp_ualstrcpynW` at `0x18006ac61`
- `SHCORE!__imp_ualstrcpynW` at `0x18006b569`
- `SHCORE!__imp_ualstrcpynW` at `0x18006b680`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!__imp_DoesStringRoundTripW` at `0x18006a94f`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!__imp_DoesStringRoundTripW` at `0x18006a94f`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CFSFolder::_CreateIDList(
        CFSFolder *a1,
        __int64 a2,
        void *a3,
        unsigned __int16 *a4,
        __int64 a5,
        unsigned int a6,
        char a7,
        enum FOLDER_ENUM_MODE a8,
        _QWORD *a9)
{
  unsigned __int16 *v9; // r13
  const WCHAR *v11; // rbx
  _BYTE *v12; // r12
  _BYTE *v13; // rdi
  __int64 v14; // rsi
  bool v15; // zf
  __int64 v16; // rax
  int v17; // r15d
  __int64 v18; // rax
  int v19; // edi
  int v20; // edi
  __int64 v21; // r15
  unsigned int v22; // r14d
  unsigned __int16 *p_cb; // rdi
  __int64 v24; // rcx
  unsigned int v25; // r13d
  int v26; // ecx
  ITEMIDLIST *v27; // rsi
  size_t v28; // rdi
  __int64 v29; // rax
  const FILETIME *v30; // r14
  BYTE v31; // al
  CFSFolder *v32; // rcx
  char *v33; // rdi
  unsigned __int16 *v34; // rdx
  int v35; // r14d
  ITEMIDLIST *v36; // r14
  int FolderValue; // r15d
  __int64 v38; // rcx
  __int64 v39; // rcx
  __int64 v40; // rcx
  __int64 v41; // rcx
  const struct _ITEMIDLIST_RELATIVE *v42; // rcx
  unsigned __int16 v43; // r8
  unsigned __int16 *v44; // rdx
  __int64 result; // rax
  unsigned __int16 *v46; // rax
  __int64 v47; // rax
  unsigned __int16 *v48; // r14
  CFSFolder *v49; // rcx
  char *v50; // r12
  char *abID; // r12
  char v52; // al
  int v53; // r14d
  LPWSTR ExtensionW; // rax
  __int64 v55; // rdx
  __int64 v56; // rcx
  const struct _ITEMIDLIST_RELATIVE *v57; // r14
  unsigned __int16 v58; // r14
  unsigned __int16 *v59; // rsi
  unsigned __int16 v60; // cx
  unsigned __int16 v61; // si
  unsigned __int16 *v62; // rdx
  __int64 v63; // rcx
  _WORD *v64; // rax
  _WORD *v65; // r14
  size_t v66; // rax
  unsigned __int16 v67; // ax
  const struct _ITEMIDLIST_RELATIVE *v68; // rcx
  const struct _ITEMIDLIST_RELATIVE *v69; // rbx
  void *v70; // r15
  unsigned int v71; // esi
  __int64 v72; // rcx
  unsigned __int16 *v73; // rax
  size_t v74; // rax
  unsigned __int16 v75; // ax
  const struct _ITEMIDLIST_RELATIVE *v76; // rcx
  const struct _ITEMIDLIST_RELATIVE *v77; // rbx
  unsigned __int16 *v78; // rdx
  int v79; // r8d
  __int64 v80; // rcx
  __int64 v81; // r15
  ITEMIDLIST *v82; // rdx
  unsigned int v83; // r14d
  __int64 cb; // rcx
  ITEMIDLIST *v85; // rax
  LPITEMIDLIST v86; // r12
  LPMALLOC v87; // r14
  int v88; // r15d
  unsigned int v89; // ebx
  unsigned __int16 *v90; // rdx
  unsigned __int16 *v91; // rax
  GUID v92; // xmm0
  unsigned int v93; // [rsp+20h] [rbp-E0h]
  unsigned int v94; // [rsp+40h] [rbp-C0h]
  unsigned int v95; // [rsp+44h] [rbp-BCh]
  ITEMIDLIST *v96; // [rsp+48h] [rbp-B8h]
  WORD FatTime[2]; // [rsp+78h] [rbp-88h] BYREF
  WORD v100[2]; // [rsp+7Ch] [rbp-84h] BYREF
  size_t Size[2]; // [rsp+80h] [rbp-80h] BYREF
  WORD FatDate[8]; // [rsp+90h] [rbp-70h] BYREF
  LPMALLOC ppMalloc[4]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 *v104[2]; // [rsp+C0h] [rbp-40h] BYREF
  void *Buf1[2]; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD v106[2]; // [rsp+E0h] [rbp-20h] BYREF
  LPVOID v107; // [rsp+F0h] [rbp-10h]
  LPVOID v108; // [rsp+F8h] [rbp-8h]
  LPVOID pv; // [rsp+110h] [rbp+10h]
  __int64 v110; // [rsp+118h] [rbp+18h]
  __int64 v111; // [rsp+120h] [rbp+20h]
  __int64 v112; // [rsp+128h] [rbp+28h]
  _BYTE Src[272]; // [rsp+390h] [rbp+290h] BYREF
  unsigned __int16 v114[264]; // [rsp+4A0h] [rbp+3A0h] BYREF

  v9 = a4;
  v104[0] = a4;
  Buf1[0] = a3;
  v11 = (const WCHAR *)(a2 + 44);
  v12 = (_BYTE *)(a2 + 44);
  v13 = (_BYTE *)(a2 + 564);
  if ( *(_WORD *)(a2 + 564) && !(unsigned int)IsAppCompatModeEnabled(19) )
    v12 = v13;
  v14 = -1;
  v15 = (unsigned int)DoesStringRoundTripW(v12, Src, 260) == 0;
  v16 = -1;
  if ( v15 )
  {
    do
      ++v16;
    while ( *(_WORD *)&v12[2 * v16] );
    v17 = 2 * v16 + 2;
    *(_DWORD *)v100 = 1;
  }
  else
  {
    do
      ++v16;
    while ( Src[v16] );
    v17 = v16 + 1;
    v12 = Src;
    *(_DWORD *)v100 = 0;
  }
  LODWORD(Size[0]) = v17;
  v18 = -1;
  do
    ++v18;
  while ( v11[v18] );
  v95 = 2 * v18 + 2;
  v19 = 42;
  if ( (a7 & 8) == 0 )
    v19 = 46;
  v20 = 2 * v18 + 2 + v19;
  v94 = 0;
  if ( (a7 & 1) != 0 )
  {
    if ( !v9 )
    {
      if ( CFSFolder::_DiscoverLocalizedName(
             a1,
             (const struct _ITEMIDLIST_RELATIVE *)Buf1[0],
             (const struct tagWIN32_FIND_DATA_EX *)a2,
             v114,
             v93) < 0 )
        goto LABEL_11;
      v9 = v114;
      v104[0] = v114;
    }
    do
      ++v14;
    while ( v9[v14] );
    v94 = v14 + 1;
    v20 += 2 * (v14 + 1);
  }
  else
  {
    v104[0] = 0;
  }
LABEL_11:
  v21 = (v17 + 15) & 0xFFFFFFFE;
  v22 = (v20 + 1) & 0xFFFFFFFE;
  p_cb = 0;
  v24 = *((_QWORD *)a1 + 77);
  v25 = 2;
  if ( !v24 || Buf1[0] )
  {
    if ( (unsigned int)v21 > 0xFFFF )
      goto LABEL_72;
    if ( v22 > 0xFFFF )
      goto LABEL_72;
    v26 = v22 + v21;
    if ( (unsigned __int64)(v22 + (unsigned int)v21) + 2 > 0xFFFF )
      goto LABEL_72;
    *(_DWORD *)FatDate = v26 + 2;
    v27 = (ITEMIDLIST *)CoTaskMemAlloc((unsigned int)(v26 + 4));
    if ( !v27 )
      goto LABEL_72;
    v28 = 0;
    ppMalloc[0] = 0;
    if ( CoGetMalloc(1u, ppMalloc) >= 0 )
    {
      v28 = ((__int64 (__fastcall *)(LPMALLOC, ITEMIDLIST *))ppMalloc[0]->lpVtbl->GetSize)(ppMalloc[0], v27);
      ((void (__fastcall *)(LPMALLOC))ppMalloc[0]->lpVtbl->Release)(ppMalloc[0]);
    }
    memset_0(v27, 0, v28);
    *(USHORT *)((char *)&v27->mkid.cb + v21) = v22 + 2;
    v29 = FatDate[0];
    v27->mkid.cb = FatDate[0];
    *(_WORD *)((char *)v27 + v29 - 2) = v21;
    *(_DWORD *)((char *)&v27[1].mkid.cb + 1) = *(_DWORD *)(a2 + 32);
    v27[4].mkid.cb = *(_WORD *)a2;
    FatDate[0] = 0;
    FatTime[0] = 0;
    v30 = (const FILETIME *)(a2 + 20);
    if ( FileTimeToDosDateTime((const FILETIME *)(a2 + 20), FatDate, FatTime) )
    {
      *(_WORD *)v27[2].mkid.abID = FatDate[0];
      *(USHORT *)((char *)&v27[3].mkid.cb + 1) = FatTime[0];
    }
    else if ( *(unsigned int *)(a2 + 20) + ((unsigned __int64)*(unsigned int *)(a2 + 24) << 32) )
    {
      *(_WORD *)v27[2].mkid.abID = 1;
    }
    memcpy_0(v27[4].mkid.abID, v12, LODWORD(Size[0]));
    v31 = ((*(_BYTE *)a2 & 0x10) == 0) + 49;
    v27->mkid.abID[0] = v31;
    v32 = (CFSFolder *)(*((_QWORD *)a1 + 62) - *(_QWORD *)&FOLDERID_PublicDesktop.Data1);
    if ( !v32 )
      v32 = (CFSFolder *)(*((_QWORD *)a1 + 63) - *(_QWORD *)FOLDERID_PublicDesktop.Data4);
    if ( !v32 )
    {
      v31 |= 0x38u;
      v27->mkid.abID[0] = v31;
    }
    if ( *(_DWORD *)v100 )
      v27->mkid.abID[0] = v31 | 0x34;
    v33 = (char *)v27 + (unsigned int)v21;
    if ( (a7 & 8) != 0 )
    {
      CFSFolder::_PopulateIDXHelper(
        v32,
        (const struct tagWIN32_FIND_DATA_EX *)a2,
        (struct IDFOLDEREX_V3 *)((char *)v27 + (unsigned int)v21));
      *((_WORD *)v33 + 1) = 8;
      *((_WORD *)v33 + 8) = 42;
      ualstrcpynW(v33 + 42, v11, v95 >> 1);
      v90 = v104[0];
      if ( v104[0] )
      {
        *((_WORD *)v33 + 18) = v95 + 42;
        ualstrcpynW(&v33[(unsigned __int16)(v95 + 42)], v90, v94);
      }
    }
    else
    {
      *((_DWORD *)v33 + 1) = -1091633148;
      *((_DWORD *)v33 + 7) = *(_DWORD *)(a2 + 28);
      FatTime[0] = 0;
      FatDate[0] = 0;
      if ( FileTimeToDosDateTime((const FILETIME *)(a2 + 4), FatTime, FatDate) )
      {
        *((_WORD *)v33 + 4) = FatTime[0];
        *((_WORD *)v33 + 5) = FatDate[0];
      }
      if ( FileTimeToDosDateTime((const FILETIME *)(a2 + 12), FatTime, FatDate) )
      {
        *((_WORD *)v33 + 6) = FatTime[0];
        *((_WORD *)v33 + 7) = FatDate[0];
      }
      *(_QWORD *)(v33 + 20) = *(_QWORD *)(a2 + 592);
      *((_DWORD *)v33 + 8) = *(_DWORD *)(a2 + 36);
      *((_WORD *)v33 + 1) = 9;
      *((_WORD *)v33 + 8) = 46;
      ualstrcpynW(v33 + 46, v11, v95 >> 1);
      v34 = v104[0];
      if ( v104[0] )
      {
        *((_WORD *)v33 + 18) = v95 + 46;
        ualstrcpynW(&v33[(unsigned __int16)(v95 + 46)], v34, v94);
      }
      *(_DWORD *)(v33 + 42) = 0;
      LOWORD(Size[0]) = 0;
      v100[0] = 0;
      if ( FileTimeToDosDateTime(v30, (LPWORD)Size, v100) )
      {
        ppMalloc[0] = 0;
        if ( DosDateTimeToFileTime(Size[0], v100[0], (LPFILETIME)ppMalloc) )
          *(_DWORD *)(v33 + 42) = LODWORD(ppMalloc[0]) - v30->dwLowDateTime;
      }
    }
    v35 = 0;
    if ( a8 == FEM_NAVIGATION )
    {
      FolderValue = 0;
      CFileSysItemString::CFileSysItemString(
        (CFileSysItemString *)v106,
        a1,
        (const struct _ITEMIDLIST_RELATIVE *)v27,
        0);
      *(_OWORD *)ppMalloc = 0;
      if ( (unsigned int)CFileSysItemString::GetJunctionClsid(v106, 3, ppMalloc) )
        FolderValue = CCLSIDInfoCache::GetFolderValue(v38, ppMalloc, 0x4000);
      v106[0] = &CFileSysItemString::`vftable';
      v39 = v112;
      v112 = 0;
      if ( v39 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
      v40 = v110;
      v110 = 0;
      if ( v40 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
      v41 = v111;
      v111 = 0;
      if ( v41 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
      if ( pv )
        CoTaskMemFree(pv);
      if ( v108 )
        CoTaskMemFree(v108);
      if ( v107 )
        CoTaskMemFree(v107);
      if ( FolderValue )
        v35 = 1;
    }
    *(_DWORD *)(v33 + 38) = v35;
    p_cb = &v27->mkid.cb;
    v36 = v27;
  }
  else
  {
    v46 = (unsigned __int16 *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v24 + 24LL))(
                                v24,
                                (unsigned int)(v21 + 6));
    *(_QWORD *)FatDate = v46;
    if ( !v46 )
      goto LABEL_72;
    v27 = 0;
    v47 = ILCreateWithHidden(*v46, v22);
    v48 = *(unsigned __int16 **)FatDate;
    if ( v47 )
    {
      p_cb = (unsigned __int16 *)v47;
      memcpy_0((void *)(v47 + 2), (const void *)(*(_QWORD *)FatDate + 2LL), (unsigned __int16)**(_WORD **)FatDate - 2LL);
      *(_DWORD *)(p_cb + 3) = 1179862595;
      v27 = (ITEMIDLIST *)(p_cb + 5);
      p_cb[5] = v21;
      CFSFolder::_PopulateID(
        a1,
        (const struct tagWIN32_FIND_DATA_EX *)a2,
        v12,
        Size[0],
        *(int *)v100,
        (struct IDFOLDER *)(p_cb + 5));
      v50 = (char *)p_cb + *v48;
      if ( (a7 & 8) != 0 )
        CFSFolder::_PopulateIDXV3(
          v49,
          (const struct tagWIN32_FIND_DATA_EX *)a2,
          v95,
          v104[0],
          v94,
          (struct IDFOLDEREX_V3 *)v50);
      else
        CFSFolder::_PopulateIDXLatest(
          v49,
          (const struct tagWIN32_FIND_DATA_EX *)a2,
          v95,
          v104[0],
          v94,
          (struct IDFOLDEREX_V4 *)v50);
      *(_DWORD *)(v50 + 38) = CFSFolder::_GetEnumMode(a1, (const struct _ITEMID_CHILD *)p_cb, a8);
    }
    CoTaskMemFree(v48);
    if ( !p_cb )
      goto LABEL_72;
    if ( !v27 )
      goto LABEL_102;
    v36 = (ITEMIDLIST *)p_cb;
  }
  if ( (a7 & 2) == 0 )
    goto LABEL_102;
  *(_OWORD *)FatDate = *(_OWORD *)(a2 + 600);
  if ( memcmp_0(FatDate, &GUID_NULL, 0x10u) || (a7 & 4) == 0 )
    goto LABEL_115;
  abID = (char *)v27->mkid.abID;
  v52 = (v27->mkid.abID[0] & 0x37) - 49;
  *(GUID *)FatDate = GUID_NULL;
  if ( (v52 & 0xFB) == 0 )
  {
    v53 = 1;
LABEL_89:
    *(_OWORD *)ppMalloc = 0;
    ExtensionW = PathFindExtensionW(v11);
    if ( ExtensionW )
    {
      if ( *ExtensionW == 46 && ExtensionW[1] == 123 )
      {
        *(_OWORD *)v104 = 0;
        if ( (int)SHCLSIDFromStringEx(ExtensionW + 1, v55, ppMalloc) >= 0
          && (!v53 || !(unsigned int)CCLSIDInfoCache::GetFolderValue(v56, ppMalloc, 4096)) )
        {
          *(_OWORD *)FatDate = *(_OWORD *)ppMalloc;
          goto LABEL_115;
        }
      }
    }
    goto LABEL_129;
  }
  p_cb = &v36->mkid.cb;
  if ( SHRestricted(REST_ALLOWFILECLSIDJUNCTIONS) )
  {
    v53 = 0;
    goto LABEL_89;
  }
LABEL_129:
  if ( (((*abID & 0x37) - 49) & 0xFB) != 0 || *abID < 0 || (v27[4].mkid.cb & 5) == 0 )
    goto LABEL_115;
  if ( Buf1[0] )
  {
    v78 = (unsigned __int16 *)Buf1[0];
    v79 = 2;
    do
    {
      v80 = *v78;
      if ( !(_WORD)v80 )
        break;
      v79 += v80;
      v78 = (unsigned __int16 *)((char *)v78 + v80);
    }
    while ( v78 );
    v81 = (unsigned int)(v79 - 2);
    v82 = v27;
    v83 = 2;
    do
    {
      cb = v82->mkid.cb;
      if ( !(_WORD)cb )
        break;
      v83 += cb;
      v82 = (ITEMIDLIST *)((char *)v82 + cb);
    }
    while ( v82 );
    v85 = (ITEMIDLIST *)WINRT_IMPL_CoTaskMemAlloc(v83 + (unsigned int)v81);
    v86 = v85;
    v96 = v85;
    if ( v85 )
    {
      memset_0(v85, 0, v83 + (unsigned int)v81);
      memcpy_0(v86, Buf1[0], (unsigned int)v81);
      memcpy_0((char *)v86 + v81, v27, v83);
    }
  }
  else
  {
    v86 = ILClone(v27);
    v96 = v86;
  }
  if ( !v86 )
    goto LABEL_115;
  ppMalloc[0] = 0;
  if ( (*(int (__fastcall **)(_QWORD *, LPITEMIDLIST, _QWORD, GUID *, LPMALLOC *))(*((_QWORD *)a1 + 6) + 40LL))(
         (_QWORD *)a1 + 6,
         v86,
         0,
         &GUID_b57046bc_32e5_428a_9887_19f712b907bf,
         ppMalloc) < 0 )
    goto LABEL_152;
  v87 = ppMalloc[0];
  v88 = 0;
  v89 = 0;
  while ( v89 < 3 )
  {
    v104[0] = 0;
    if ( ((int (__fastcall *)(LPMALLOC, const wchar_t *, wchar_t *, _QWORD, _DWORD, unsigned __int16 **))v87->lpVtbl->GetSize)(
           v87,
           L".ShellClassInfo",
           off_180686600[v89],
           0,
           0,
           v104) >= 0 )
    {
      v91 = v104[0];
      if ( *v104[0] )
      {
        v92 = GUID_NULL;
        *(GUID *)Buf1 = GUID_NULL;
        if ( !v104[0] )
          goto LABEL_161;
        v15 = (unsigned int)GUIDFromStringW(v104[0]) == 0;
        v91 = v104[0];
        if ( !v15 )
        {
          v92 = *(GUID *)Buf1;
LABEL_161:
          if ( v89 != 2 )
          {
            *(GUID *)FatDate = v92;
            goto LABEL_163;
          }
          v15 = memcmp_0(Buf1, &GUID_7bd29e00_76c1_11cf_9dd0_00a0c9034933, 0x10u) == 0;
          v91 = v104[0];
          if ( v15 )
          {
            *(GUID *)FatDate = GUID_7bd29e01_76c1_11cf_9dd0_00a0c9034933;
LABEL_163:
            v88 = 1;
          }
        }
      }
      CoTaskMemFree(v91);
    }
    ++v89;
    if ( v88 )
      break;
  }
  ((void (__fastcall *)(LPMALLOC))ppMalloc[0]->lpVtbl->Release)(ppMalloc[0]);
  v25 = 2;
  v86 = v96;
LABEL_152:
  CoTaskMemFree(v86);
LABEL_115:
  ppMalloc[0] = 0;
  if ( !memcmp_0(FatDate, &GUID_NULL, 0x10u) || (int)SHRegGetCLSIDKey(FatDate, 0, 0, 0, 1, ppMalloc) < 0 )
    goto LABEL_102;
  RegCloseKey((HKEY)ppMalloc[0]);
  v27->mkid.abID[0] |= 0x80u;
  ppMalloc[0] = (LPMALLOC)0xBEEF000300000018LL;
  *(_OWORD *)&ppMalloc[1] = *(_OWORD *)FatDate;
  if ( *p_cb )
  {
    v70 = p_cb;
    v71 = 2;
    do
    {
      v72 = *p_cb;
      if ( !(_WORD)v72 )
        break;
      v71 += v72;
      p_cb = (unsigned __int16 *)((char *)p_cb + v72);
    }
    while ( p_cb );
    v73 = (unsigned __int16 *)CoTaskMemAlloc(v71 + 26);
    p_cb = v73;
    if ( v73 )
    {
      v74 = SHGetSize(v73);
      memset_0(p_cb, 0, v74);
      memcpy_0(p_cb, v70, v71);
      v75 = *p_cb;
      if ( *p_cb )
      {
        v76 = (const struct _ITEMIDLIST_RELATIVE *)p_cb;
        do
        {
          v77 = v76;
          v76 = (const struct _ITEMIDLIST_RELATIVE *)((char *)v76 + v75);
          v75 = *(_WORD *)v76;
        }
        while ( *(_WORD *)v76 );
      }
      else
      {
        v77 = (const struct _ITEMIDLIST_RELATIVE *)p_cb;
      }
      if ( ILFindFirstHiddenID(v77) )
        v57 = (const struct _ITEMIDLIST_RELATIVE *)((char *)v77 + *(unsigned __int16 *)v77 - 2);
      else
        v57 = v77;
      v58 = *(_WORD *)v57;
      v59 = (unsigned __int16 *)((char *)p_cb + v71 - 2);
      memcpy_0(v59, ppMalloc, 0x18u);
      v60 = *v59 + 2;
      if ( v60 < *v59 || (*v59 = v60, (unsigned __int16)(v60 + *(_WORD *)v77) < *(_WORD *)v77) )
      {
        CoTaskMemFree(p_cb);
        p_cb = 0;
      }
      else
      {
        *(_WORD *)v77 += v60;
        *(unsigned __int16 *)((char *)v59 + *v59 - 2) = v58;
      }
    }
    CoTaskMemFree(v70);
  }
  if ( p_cb )
  {
LABEL_102:
    if ( !a5 || (p_cb = (unsigned __int16 *)ILAppendHiddenStringW(p_cb, a6, a5)) != 0 )
    {
      v61 = *(_WORD *)(a2 + 2);
      if ( v61 )
      {
        if ( *p_cb )
        {
          v62 = p_cb;
          do
          {
            v63 = *v62;
            if ( !(_WORD)v63 )
              break;
            v25 += v63;
            v62 = (unsigned __int16 *)((char *)v62 + v63);
          }
          while ( v62 );
          v64 = CoTaskMemAlloc(v25 + 12);
          v65 = v64;
          if ( v64 )
          {
            v66 = SHGetSize(v64);
            memset_0(v65, 0, v66);
            memcpy_0(v65, p_cb, v25);
            v67 = *v65;
            if ( *v65 )
            {
              v68 = (const struct _ITEMIDLIST_RELATIVE *)v65;
              do
              {
                v69 = v68;
                v68 = (const struct _ITEMIDLIST_RELATIVE *)((char *)v68 + v67);
                v67 = *(_WORD *)v68;
              }
              while ( *(_WORD *)v68 );
            }
            else
            {
              v69 = (const struct _ITEMIDLIST_RELATIVE *)v65;
            }
            if ( ILFindFirstHiddenID(v69) )
              v42 = (const struct _ITEMIDLIST_RELATIVE *)((char *)v69 + *(unsigned __int16 *)v69 - 2);
            else
              v42 = v69;
            v43 = *(_WORD *)v42;
            v44 = (_WORD *)((char *)v65 + v25 - 2);
            *(_DWORD *)v44 = 10;
            *((_DWORD *)v44 + 1) = -1091633111;
            v44[4] = v61;
            *v44 = 12;
            if ( (unsigned __int16)(*(_WORD *)v69 + 12) < *(_WORD *)v69 )
            {
              CoTaskMemFree(v65);
              v65 = 0;
            }
            else
            {
              *(_WORD *)v69 += 12;
              *(unsigned __int16 *)((char *)v44 + *v44 - 2) = v43;
            }
          }
          CoTaskMemFree(p_cb);
        }
        else
        {
          v65 = p_cb;
        }
        p_cb = v65;
      }
    }
  }
LABEL_72:
  *a9 = p_cb;
  result = 0;
  if ( !p_cb )
    return 2147942414LL;
  return result;
}

```

## disassembly

```asm
0x18006a8c0  push    rbp
0x18006a8c2  push    rbx
0x18006a8c3  push    rsi
0x18006a8c4  push    rdi
0x18006a8c5  push    r12
0x18006a8c7  push    r13
0x18006a8c9  push    r14
0x18006a8cb  push    r15
0x18006a8cd  lea     rbp, [rsp-5C8h]
0x18006a8d5  sub     rsp, 6C8h
0x18006a8dc  mov     rax, cs:__security_cookie
0x18006a8e3  xor     rax, rsp
0x18006a8e6  mov     [rbp+600h+var_50], rax
0x18006a8ed  mov     r13, r9
0x18006a8f0  mov     [rbp+600h+var_640], r9
0x18006a8f4  mov     [rbp+600h+Buf1], r8
0x18006a8f8  mov     r14, rdx
0x18006a8fb  mov     [rsp+700h+var_6A8], rdx
0x18006a900  mov     [rsp+700h+var_6B0], rcx
0x18006a905  mov     rax, [rbp+600h+arg_20]
0x18006a90c  mov     [rsp+700h+var_698], rax
0x18006a911  mov     eax, [rbp+600h+arg_28]
0x18006a917  mov     [rsp+700h+var_6A0], eax
0x18006a91b  mov     rax, [rbp+600h+arg_40]
0x18006a922  mov     [rsp+700h+var_690], rax
0x18006a927  lea     rbx, [rdx+2Ch]
0x18006a92b  mov     r12, rbx
0x18006a92e  lea     rdi, [rdx+234h]
0x18006a935  cmp     word ptr [rdi], 0
0x18006a939  jnz     loc_18006AE59
0x18006a93f  mov     r8d, 104h
0x18006a945  lea     rdx, [rbp+600h+Src]
0x18006a94c  mov     rcx, r12
0x18006a94f  call    cs:__imp_DoesStringRoundTripW
0x18006a956  nop     dword ptr [rax+rax+00h]
0x18006a95b  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x18006a962  test    eax, eax
0x18006a964  mov     rax, rsi
0x18006a967  jz      loc_18006AD60
0x18006a96d  lea     rcx, [rbp+600h+Src]
0x18006a974  lea     rax, [rax+1]
0x18006a978  cmp     byte ptr [rcx+rax], 0
0x18006a97c  jnz     short loc_18006A974
0x18006a97e  lea     r15d, [rax+1]
0x18006a982  lea     r12, [rbp+600h+Src]
0x18006a989  mov     dword ptr [rsp+700h+var_684], 0
0x18006a991  mov     dword ptr [rbp+600h+Size], r15d
0x18006a995  mov     rax, rsi
0x18006a998  nop     dword ptr [rax+rax+00000000h]
0x18006a9a0  lea     rax, [rax+1]
0x18006a9a4  cmp     word ptr [rbx+rax*2], 0
0x18006a9a9  jnz     short loc_18006A9A0
0x18006a9ab  lea     edx, ds:2[rax*2]
0x18006a9b2  mov     [rsp+700h+var_6BC], edx
0x18006a9b6  mov     ecx, dword ptr [rbp+600h+arg_30]
0x18006a9bc  mov     eax, ecx
0x18006a9be  and     eax, 8
0x18006a9c1  mov     dword ptr [rsp+700h+var_6B8], eax
0x18006a9c5  mov     edi, 2Ah ; '*'
0x18006a9ca  mov     r8d, 2Eh ; '.'
0x18006a9d0  cmovz   edi, r8d
0x18006a9d4  add     edi, edx
0x18006a9d6  xor     edx, edx
0x18006a9d8  mov     [rsp+700h+var_6C0], edx
0x18006a9dc  test    cl, 1
0x18006a9df  jnz     loc_18006ACE4
0x18006a9e5  mov     [rbp+600h+var_640], rdx
0x18006a9e9  add     r15d, 0Fh
0x18006a9ed  and     r15d, 0FFFFFFFEh
0x18006a9f1  lea     r14d, [rdi+1]
0x18006a9f5  and     r14d, 0FFFFFFFEh
0x18006a9f9  mov     rdi, rdx
0x18006a9fc  mov     rax, [rsp+700h+var_6B0]
0x18006aa01  mov     rcx, [rax+268h]
0x18006aa08  mov     r13d, 2
0x18006aa0e  test    rcx, rcx
0x18006aa11  jnz     loc_18006AF2E
0x18006aa17  cmp     r15d, 0FFFFh
0x18006aa1e  ja      loc_18006AEF5
0x18006aa24  cmp     r14d, 0FFFFh
0x18006aa2b  ja      loc_18006AEF5
0x18006aa31  lea     ecx, [r14+r15]
0x18006aa35  mov     eax, ecx
0x18006aa37  add     rax, r13
0x18006aa3a  cmp     rax, 0FFFFh
0x18006aa40  ja      loc_18006AEF5
0x18006aa46  lea     eax, [rcx+2]
0x18006aa49  mov     dword ptr [rbp+600h+FatDate], eax
0x18006aa4c  lea     ecx, [rax+2]; cb
0x18006aa4f  call    cs:__imp_CoTaskMemAlloc
0x18006aa56  nop     dword ptr [rax+rax+00h]
0x18006aa5b  mov     rsi, rax
0x18006aa5e  test    rax, rax
0x18006aa61  jz      loc_18006AEF5
0x18006aa67  xor     edi, edi
0x18006aa69  mov     [rbp+600h+ppMalloc], rdi
0x18006aa6d  lea     rdx, [rbp+600h+ppMalloc]; ppMalloc
0x18006aa71  mov     ecx, 1; dwMemContext
0x18006aa76  call    cs:__imp_CoGetMalloc
0x18006aa7d  nop     dword ptr [rax+rax+00h]
0x18006aa82  test    eax, eax
0x18006aa84  js      short loc_18006AAAC
0x18006aa86  mov     rcx, [rbp+600h+ppMalloc]
0x18006aa8a  mov     rdx, [rcx]
0x18006aa8d  mov     rax, [rdx+30h]
0x18006aa91  mov     rdx, rsi
0x18006aa94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006aa99  mov     rdi, rax
0x18006aa9c  mov     rcx, [rbp+600h+ppMalloc]
0x18006aaa0  mov     rdx, [rcx]
0x18006aaa3  mov     rax, [rdx+10h]
0x18006aaa7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006aaac  mov     r8, rdi; Size
0x18006aaaf  xor     edx, edx; Val
0x18006aab1  mov     rcx, rsi; void *
0x18006aab4  call    memset_0
0x18006aab9  add     r14w, r13w
0x18006aabd  mov     [r15+rsi], r14w
0x18006aac2  movzx   eax, [rbp+600h+FatDate]
0x18006aac6  mov     [rsi], ax
0x18006aac9  mov     [rax+rsi-2], r15w
0x18006aacf  mov     rcx, [rsp+700h+var_6A8]
0x18006aad4  mov     eax, [rcx+20h]
0x18006aad7  mov     [rsi+4], eax
0x18006aada  movzx   eax, word ptr [rcx]
0x18006aadd  mov     [rsi+0Ch], ax
0x18006aae1  xor     eax, eax
0x18006aae3  mov     [rbp+600h+FatDate], ax
0x18006aae7  mov     [rsp+700h+FatTime], ax
0x18006aaec  lea     r14, [rcx+14h]
0x18006aaf0  lea     r8, [rsp+700h+FatTime]; lpFatTime
0x18006aaf5  lea     rdx, [rbp+600h+FatDate]; lpFatDate
0x18006aaf9  mov     rcx, r14; lpFileTime
0x18006aafc  call    cs:__imp_FileTimeToDosDateTime
0x18006ab03  nop     dword ptr [rax+rax+00h]
0x18006ab08  test    eax, eax
0x18006ab0a  jz      loc_18006AD3C
0x18006ab10  movzx   eax, [rbp+600h+FatDate]
0x18006ab14  mov     [rsi+8], ax
0x18006ab18  movzx   eax, [rsp+700h+FatTime]
0x18006ab1d  mov     [rsi+0Ah], ax
0x18006ab21  mov     r8d, dword ptr [rbp+600h+Size]; Size
0x18006ab25  lea     rcx, [rsi+0Eh]; void *
0x18006ab29  mov     rdx, r12; Src
0x18006ab2c  call    memcpy_0
0x18006ab31  mov     r12, [rsp+700h+var_6A8]
0x18006ab36  test    byte ptr [r12], 10h
0x18006ab3b  setz    al
0x18006ab3e  add     al, 31h ; '1'
0x18006ab40  mov     [rsi+2], al
0x18006ab43  mov     rdx, [rsp+700h+var_6B0]
0x18006ab48  mov     rcx, [rdx+1F0h]
0x18006ab4f  sub     rcx, qword ptr cs:FOLDERID_PublicDesktop.Data1
0x18006ab56  jnz     short loc_18006AB66
0x18006ab58  mov     rcx, [rdx+1F8h]
0x18006ab5f  sub     rcx, qword ptr cs:FOLDERID_PublicDesktop.Data4; this
0x18006ab66  test    rcx, rcx
0x18006ab69  jnz     short loc_18006AB70
0x18006ab6b  or      al, 38h
0x18006ab6d  mov     [rsi+2], al
0x18006ab70  cmp     dword ptr [rsp+700h+var_684], 0
0x18006ab75  jz      short loc_18006AB7C
0x18006ab77  or      al, 34h
0x18006ab79  mov     [rsi+2], al
0x18006ab7c  mov     edi, r15d
0x18006ab7f  add     rdi, rsi
0x18006ab82  cmp     dword ptr [rsp+700h+var_6B8], 0
0x18006ab87  jnz     loc_18006B540
0x18006ab8d  mov     dword ptr [rdi+4], 0BEEF0004h
0x18006ab94  mov     eax, [r12+1Ch]
0x18006ab99  mov     [rdi+1Ch], eax
0x18006ab9c  xor     eax, eax
0x18006ab9e  mov     [rsp+700h+FatTime], ax
0x18006aba3  mov     [rbp+600h+FatDate], ax
0x18006aba7  lea     rcx, [r12+4]; lpFileTime
0x18006abac  lea     r8, [rbp+600h+FatDate]; lpFatTime
0x18006abb0  lea     rdx, [rsp+700h+FatTime]; lpFatDate
0x18006abb5  call    cs:__imp_FileTimeToDosDateTime
0x18006abbc  nop     dword ptr [rax+rax+00h]
0x18006abc1  test    eax, eax
0x18006abc3  jz      short loc_18006ABD6
0x18006abc5  movzx   eax, [rsp+700h+FatTime]
0x18006abca  mov     [rdi+8], ax
0x18006abce  movzx   eax, [rbp+600h+FatDate]
0x18006abd2  mov     [rdi+0Ah], ax
0x18006abd6  lea     rcx, [r12+0Ch]; lpFileTime
0x18006abdb  lea     r8, [rbp+600h+FatDate]; lpFatTime
0x18006abdf  lea     rdx, [rsp+700h+FatTime]; lpFatDate
0x18006abe4  call    cs:__imp_FileTimeToDosDateTime
0x18006abeb  nop     dword ptr [rax+rax+00h]
0x18006abf0  test    eax, eax
0x18006abf2  jz      short loc_18006AC05
0x18006abf4  movzx   eax, [rsp+700h+FatTime]
0x18006abf9  mov     [rdi+0Ch], ax
0x18006abfd  movzx   eax, [rbp+600h+FatDate]
0x18006ac01  mov     [rdi+0Eh], ax
0x18006ac05  mov     rax, [r12+250h]
0x18006ac0d  mov     [rdi+14h], rax
0x18006ac11  mov     eax, [r12+24h]
0x18006ac16  mov     [rdi+20h], eax
0x18006ac19  mov     word ptr [rdi+2], 9
0x18006ac1f  mov     word ptr [rdi+10h], 2Eh ; '.'
0x18006ac25  mov     r15d, [rsp+700h+var_6BC]
0x18006ac2a  mov     r8d, r15d
0x18006ac2d  shr     r8d, 1
0x18006ac30  lea     rcx, [rdi+2Eh]
0x18006ac34  mov     rdx, rbx
0x18006ac37  call    cs:__imp_ualstrcpynW
0x18006ac3e  nop     dword ptr [rax+rax+00h]
0x18006ac43  mov     rdx, [rbp+600h+var_640]
0x18006ac47  test    rdx, rdx
0x18006ac4a  jz      short loc_18006AC6D
0x18006ac4c  add     r15w, 2Eh ; '.'
0x18006ac51  movzx   ecx, r15w
0x18006ac55  mov     [rdi+24h], cx
0x18006ac59  add     rcx, rdi
0x18006ac5c  mov     r8d, [rsp+700h+var_6C0]
0x18006ac61  call    cs:__imp_ualstrcpynW
0x18006ac68  nop     dword ptr [rax+rax+00h]
0x18006ac6d  xor     r12d, r12d
0x18006ac70  mov     [rdi+2Ah], r12d
0x18006ac74  mov     word ptr [rbp+600h+Size], r12w
0x18006ac79  mov     [rsp+700h+var_684], r12w
0x18006ac7f  lea     r8, [rsp+700h+var_684]; lpFatTime
0x18006ac84  lea     rdx, [rbp+600h+Size]; lpFatDate
0x18006ac88  mov     rcx, r14; lpFileTime
0x18006ac8b  call    cs:__imp_FileTimeToDosDateTime
0x18006ac92  nop     dword ptr [rax+rax+00h]
0x18006ac97  test    eax, eax
0x18006ac99  jz      short loc_18006ACC5
0x18006ac9b  mov     [rbp+600h+ppMalloc], r12
0x18006ac9f  lea     r8, [rbp+600h+ppMalloc]; lpFileTime
0x18006aca3  movzx   edx, [rsp+700h+var_684]; wFatTime
0x18006aca8  movzx   ecx, word ptr [rbp+600h+Size]; wFatDate
0x18006acac  call    cs:__imp_DosDateTimeToFileTime
0x18006acb3  nop     dword ptr [rax+rax+00h]
0x18006acb8  test    eax, eax
0x18006acba  jz      short loc_18006ACC5
0x18006acbc  mov     eax, dword ptr [rbp+600h+ppMalloc]
0x18006acbf  sub     eax, [r14]
0x18006acc2  mov     [rdi+2Ah], eax
0x18006acc5  mov     r14d, r12d
0x18006acc8  cmp     [rbp+600h+arg_38], 1
0x18006accf  jz      loc_18006AD81
0x18006acd5  mov     [rdi+26h], r14d
0x18006acd9  mov     rdi, rsi
0x18006acdc  mov     r14, rsi
0x18006acdf  jmp     loc_18006B026
0x18006ace4  test    r13, r13
0x18006ace7  jnz     short loc_18006AD20
0x18006ace9  lea     r9, [rbp+600h+var_260]; unsigned __int16 *
0x18006acf0  mov     r8, r14; struct tagWIN32_FIND_DATA_EX *
0x18006acf3  mov     rdx, [rbp+600h+Buf1]; struct _ITEMIDLIST_RELATIVE *
0x18006acf7  mov     rcx, [rsp+700h+var_6B0]; this
0x18006acfc  call    ?_DiscoverLocalizedName@CFSFolder@@IEAAJPEFBU_ITEMIDLIST_RELATIVE@@PEBUtagWIN32_FIND_DATA_EX@@PEAGI@Z; CFSFolder::_DiscoverLocalizedName(_ITEMIDLIST_RELATIVE const *,tagWIN32_FIND_DATA_EX const *,ushort *,uint)
0x18006ad01  xor     edx, edx
0x18006ad03  test    eax, eax
0x18006ad05  js      loc_18006A9E9
0x18006ad0b  lea     r13, [rbp+600h+var_260]
0x18006ad12  mov     [rbp+600h+var_640], r13
0x18006ad16  nop     word ptr [rax+rax+00000000h]
0x18006ad20  lea     rsi, [rsi+1]
0x18006ad24  cmp     word ptr [r13+rsi*2+0], 0
0x18006ad2b  jnz     short loc_18006AD20
0x18006ad2d  lea     eax, [rsi+1]
0x18006ad30  mov     [rsp+700h+var_6C0], eax
0x18006ad34  lea     edi, [rdi+rax*2]
0x18006ad37  jmp     loc_18006A9E9
0x18006ad3c  mov     ecx, [r14+4]
0x18006ad40  shl     rcx, 20h
0x18006ad44  mov     eax, [r14]
0x18006ad47  add     rcx, rax
0x18006ad4a  jz      loc_18006AB21
0x18006ad50  mov     word ptr [rsi+8], 1
0x18006ad56  jmp     loc_18006AB21
0x18006ad60  lea     rax, [rax+1]
0x18006ad64  cmp     word ptr [r12+rax*2], 0
0x18006ad6a  jnz     short loc_18006AD60
0x18006ad6c  lea     r15d, ds:2[rax*2]
0x18006ad74  mov     dword ptr [rsp+700h+var_684], 1
0x18006ad7c  jmp     loc_18006A991
0x18006ad81  mov     r15d, r12d
0x18006ad84  xor     r9d, r9d; struct IDFOLDER *
0x18006ad87  mov     r8, rsi; struct _ITEMIDLIST_RELATIVE *
0x18006ad8a  mov     rdx, [rsp+700h+var_6B0]; struct CFSFolder *
0x18006ad8f  lea     rcx, [rbp+600h+var_620]; this
0x18006ad93  call    ??0CFileSysItemString@@QEAA@PEAVCFSFolder@@PEFBU_ITEMIDLIST_RELATIVE@@PEFBUIDFOLDER@@@Z; CFileSysItemString::CFileSysItemString(CFSFolder *,_ITEMIDLIST_RELATIVE const *,IDFOLDER const *)
0x18006ad98  nop
0x18006ad99  xorps   xmm0, xmm0
0x18006ad9c  movups  xmmword ptr [rbp+600h+ppMalloc], xmm0
0x18006ada0  lea     r8, [rbp+600h+ppMalloc]
0x18006ada4  mov     edx, 3
0x18006ada9  lea     rcx, [rbp+600h+var_620]
0x18006adad  call    ?GetJunctionClsid@CFileSysItemString@@QEAAHW4FSIS_JUNCTION_FLAGS@@PEAU_GUID@@@Z; CFileSysItemString::GetJunctionClsid(FSIS_JUNCTION_FLAGS,_GUID *)
0x18006adb2  test    eax, eax
0x18006adb4  jnz     loc_18006AE86
0x18006adba  lea     rax, ??_7CFileSysItemString@@6B@; const CFileSysItemString::`vftable'
0x18006adc1  mov     [rbp+600h+var_620], rax
0x18006adc5  mov     rcx, [rbp+600h+var_5D8]
0x18006adc9  mov     [rbp+600h+var_5D8], r12
  ... truncated ...
```
