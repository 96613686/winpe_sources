# CFSFolder::ParseDisplayName(HWND__ *,IBindCtx *,ushort *,ulong *,_ITEMIDLIST_RELATIVE * *,ulong *)

- ea: `0x1800f1da0`
- end: `0x1800f2d59`
- name: `?ParseDisplayName@CFSFolder@@UEAAJPEAUHWND__@@PEAUIBindCtx@@PEAGPEAKPEAPEAU_ITEMIDLIST_RELATIVE@@3@Z`
- size: `4025`
- prototype: `int(CFSFolder *__hidden this, HWND, struct IBindCtx *, unsigned __int16 *, unsigned int *, struct _ITEMIDLIST_RELATIVE **, unsigned int *)`
- caller_count: `0`
- callee_count: `35`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180035d30`
- `0x180038f50`
- `0x18005dc40`
- `0x180060720`
- `0x1800625e0`
- `0x180063050`
- `0x180064ad0`
- `0x180066a00`
- `0x180069550`
- `0x18006a8c0`
- `0x18006c460`
- `0x1800aeb90`
- `0x1800ee270`
- `0x1800f0b80`
- `0x1800f1680`
- `0x1800f1da0`
- `0x1800f2d60`
- `0x1800f2df0`
- `0x1800f2ebc`
- `0x1800f3080`
- `0x1800f3f50`
- `0x180116e60`
- `0x180133f50`
- `0x1801cff34`
- `0x1801ee6c0`
- `0x1801f0550`
- `0x1802039e0`
- `0x180209948`
- `0x180237520`
- `0x1802377cc`
- `0x1802e43cc`
- `0x1803b1f60`
- `0x1803b2ac0`
- `0x1803b69c5`
- `0x18067d010`

## import_xrefs

- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x1800f1fcf`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x1800f1fcf`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800f1f9e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800f1f9e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f26ab`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f2809`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f2844`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f2c27`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f26ab`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f2809`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f2844`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f2c27`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800f2aa2`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800f2aa2`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1800f20e6`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1800f20e6`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x18066680e`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x18066680e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f2105`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f229e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f2437`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f2446`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f2492`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f25d1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f27d4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f2b37`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f2c0d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1806667c5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1806668d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f2105`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f229e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f2437`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f2446`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f2492`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f25d1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f27d4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f2b37`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f2c0d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1806667c5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1806668d7`
- `MPR!WNetUseConnectionW` at `0x1800f2ba3`
- `MPR!WNetUseConnectionW` at `0x1800f2c76`
- `MPR!WNetUseConnectionW` at `0x1800f2ba3`
- `MPR!WNetUseConnectionW` at `0x1800f2c76`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x1800f1e9f`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x1800f1ebf`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x1800f1edf`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x1800f1eff`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x1800f1f14`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x1800f1e9f`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x1800f1ebf`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x1800f1edf`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x1800f1eff`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x1800f1f14`

## string_xrefs

- `0x1800f2506`: `ParseAndCreateItem`
- `0x1800f2a30`: `FindDataFullPath`
- `0x180666793`: `FindDataFullPath`
- `0x1800f2988`: `Don't Force Create`
- `0x1800f1e32`: `ItemCacheContext`
- `0x1800f1eaf`: `FSFolder_ConvertToSidString`
- `0x1800f1e8c`: `FSFolder_ResolveSidToUserName`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CFSFolder::ParseDisplayName(
        IUnknown **this,
        HWND a2,
        struct IBindCtx *a3,
        unsigned __int16 *a4,
        unsigned int *a5,
        struct _ITEMIDLIST_RELATIVE **a6,
        unsigned int *a7)
{
  struct IBindCtx *v8; // r14
  LPVOID *v10; // r12
  unsigned int *v11; // rbx
  int v12; // ebx
  int v13; // eax
  int IDListFromName; // esi
  __int64 v15; // rbx
  unsigned __int64 v16; // rbx
  unsigned __int16 *v17; // r13
  PWSTR v18; // rax
  PWSTR v19; // r9
  unsigned __int64 v20; // rdx
  unsigned __int16 *v21; // rcx
  unsigned __int16 *v22; // r8
  unsigned __int16 v23; // ax
  unsigned __int16 *v24; // rcx
  PWSTR v25; // r15
  int v26; // r12d
  CFSFolder *v27; // rbx
  const WCHAR *v28; // rcx
  HRESULT v29; // eax
  unsigned int v30; // esi
  int v31; // ebx
  int v32; // ebx
  int DataForPathWithTimeout; // eax
  BOOL v34; // eax
  char v35; // bl
  unsigned int v36; // esi
  enum FOLDER_ENUM_MODE FolderEnumMode; // eax
  HWND v38; // rdi
  IUnknown *v39; // rcx
  void *v40; // r14
  void *v41; // r15
  unsigned __int16 *v42; // rdx
  unsigned int v43; // esi
  int v44; // r8d
  __int64 v45; // rcx
  size_t v46; // rbx
  unsigned __int16 *v47; // rdx
  __int64 v48; // rcx
  struct _ITEMIDLIST_RELATIVE *v49; // rax
  struct _ITEMIDLIST_RELATIVE *v50; // rdi
  const struct _ITEMIDLIST_RELATIVE *v51; // rdi
  int v52; // ebx
  IShellFolder *v53; // rbx
  ITEMIDLIST *v54; // r15
  HRESULT v55; // ebx
  unsigned __int16 v56; // ax
  const struct _ITEMIDLIST_RELATIVE *v57; // rdx
  unsigned __int16 *v58; // rcx
  __int64 v60; // rcx
  unsigned __int16 *v61; // rdx
  unsigned __int16 *v62; // r8
  unsigned __int16 v63; // ax
  _WORD *v64; // rcx
  unsigned __int16 **v65; // rax
  int FolderPath; // eax
  DWORD TickCount; // eax
  signed int v68; // eax
  signed int v69; // eax
  int FileSystemBindData; // eax
  struct tagWIN32_FIND_DATA_EX *v71; // rbx
  unsigned __int16 **v72; // rax
  int v73; // edi
  struct tagWIN32_FIND_DATA_EX *v74; // rbx
  int ppv; // [rsp+20h] [rbp-E0h]
  int lpAccessName; // [rsp+28h] [rbp-D8h]
  IUnknown **lpBufferSize; // [rsp+30h] [rbp-D0h]
  char lpBufferSizea; // [rsp+30h] [rbp-D0h]
  CFSFolder *v79; // [rsp+50h] [rbp-B0h]
  PWSTR ppszPathOut; // [rsp+68h] [rbp-98h] BYREF
  IUnknown *punk; // [rsp+70h] [rbp-90h] BYREF
  unsigned int *v83; // [rsp+78h] [rbp-88h] BYREF
  void *Src; // [rsp+80h] [rbp-80h] BYREF
  _NETRESOURCEW NetResource; // [rsp+88h] [rbp-78h] BYREF
  LPVOID pv; // [rsp+B8h] [rbp-48h] BYREF
  struct tagWIN32_FIND_DATA_EX *v87[2]; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD v88[2]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v89[624]; // [rsp+E0h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3A8h] [rbp+2A8h]

  v8 = a3;
  Src = this;
  v10 = (LPVOID *)a6;
  v11 = a7;
  v83 = a7;
  if ( a6 )
  {
    *a6 = 0;
    if ( a4 )
    {
      if ( *a4 )
      {
        punk = 0;
        pv = 0;
        if ( a3
          && ((int (__fastcall *)(struct IBindCtx *, const wchar_t *, LPVOID *))a3->lpVtbl->GetObjectParam)(
               a3,
               L"ItemCacheContext",
               &pv) >= 0 )
        {
          v12 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, IUnknown **))pv)(
                  pv,
                  &GUID_0000000e_0000_0000_c000_000000000046,
                  &punk);
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
          if ( v12 >= 0 )
          {
            this[37] = (IUnknown *)L"FSFolder_ResolveSidToUserName";
            IUnknown_Set(this + 35, punk);
            this[40] = (IUnknown *)L"FSFolder_ConvertToSidString";
            IUnknown_Set(this + 38, punk);
            this[43] = (IUnknown *)L"FSFolder_InplaceShareEngine";
            IUnknown_Set(this + 41, punk);
            this[46] = (IUnknown *)L"FSFolder_SmbShareEngine";
            IUnknown_Set(this + 44, punk);
            IUnknown_Set(this + 47, punk);
            ((void (__fastcall *)(IUnknown *))punk->lpVtbl->Release)(punk);
          }
          v11 = v83;
        }
        v79 = (CFSFolder *)(this - 6);
        v13 = CFSFolder::TrySimpleParse((CFSFolder *)(this - 6), a4, v8, (LPVOID *)a6);
        IDListFromName = v13;
        if ( v13 )
        {
          if ( v13 != 1 )
            goto LABEL_119;
          v15 = -1;
          do
            ++v15;
          while ( a4[v15] );
          v16 = v15 + 1;
          v88[0] = 0;
          if ( !is_mul_ok(v16, 2u) )
          {
            IDListFromName = -2147024362;
            goto LABEL_92;
          }
          v17 = (unsigned __int16 *)LocalAlloc(0x40u, 2 * v16);
          if ( !v17 )
          {
            IDListFromName = -2147024882;
            goto LABEL_92;
          }
          *v17 = 0;
          v18 = StrChrW(a4, 0x5Cu);
          v19 = v18;
          if ( v18 )
          {
            if ( v18 <= a4 )
            {
LABEL_129:
              IDListFromName = -2147024809;
              goto LABEL_118;
            }
            if ( v16 )
            {
              if ( v16 > 0x7FFFFFFF )
              {
                *v17 = 0;
              }
              else
              {
                v20 = (int)(v18 - a4);
                if ( v20 > 0x7FFFFFFE )
                {
                  *v17 = 0;
                }
                else
                {
                  v21 = a4;
                  v22 = v17;
                  do
                  {
                    if ( !v20 )
                      break;
                    v23 = *v21;
                    if ( !*v21 )
                      break;
                    ++v21;
                    *v22++ = v23;
                    --v20;
                    --v16;
                  }
                  while ( v16 );
                  v24 = v22 - 1;
                  if ( v16 )
                    v24 = v22;
                  *v24 = 0;
                }
              }
            }
            v25 = 0;
            if ( v19[1] )
              v25 = v19 + 1;
          }
          else
          {
            if ( v16 )
            {
              if ( v16 > 0x7FFFFFFF )
              {
LABEL_128:
                *v17 = 0;
                goto LABEL_129;
              }
              v60 = 2147483646;
              v61 = a4;
              v62 = v17;
              do
              {
                if ( !v60 )
                  break;
                v63 = *v61;
                if ( !*v61 )
                  break;
                ++v61;
                *v62++ = v63;
                --v60;
                --v16;
              }
              while ( v16 );
              v58 = v62 - 1;
              if ( v16 )
                v58 = v62;
              *v58 = 0;
              IDListFromName = -2147024774;
              if ( v16 )
                IDListFromName = 0;
            }
            else
            {
              IDListFromName = -2147024809;
            }
            v25 = 0;
            if ( IDListFromName < 0 )
            {
LABEL_118:
              LocalFree(v17);
LABEL_119:
              if ( IDListFromName >= 0 )
                return (unsigned int)IDListFromName;
LABEL_92:
              if ( *v10 )
              {
                CoTaskMemFree(*v10);
                *v10 = 0;
              }
              return (unsigned int)IDListFromName;
            }
          }
          if ( (unsigned int)ValidPathSegment(v17) )
          {
            punk = 0;
            v88[0] = 0;
            if ( v25 )
            {
              v26 = 0;
              if ( (*((_BYTE *)Src + 488) & 0x20) != 0 )
              {
                v27 = v79;
                IDListFromName = CFSFolder::_CreateIDListFromName(
                                   v79,
                                   v17,
                                   0x10u,
                                   0,
                                   v8,
                                   (struct _ITEMID_CHILD **)&punk);
LABEL_62:
                if ( (unsigned int)(IDListFromName + 2147024894) <= 1 )
                {
                  if ( (unsigned int)BindCtx_ContainsObject(v8, L"FindDataFullPath") )
                  {
                    IDListFromName = -2147024891;
                    goto LABEL_138;
                  }
                  v87[0] = 0;
                  if ( (int)CFSFolder::_GetFindDataByHandleFromName(v27, a4, v87) >= 0 )
                  {
                    ppszPathOut = 0;
                    FileSystemBindData = CreateFileSystemBindData(
                                           &GUID_3acf075f_71db_4afa_81f0_3fc4fdf2a5b8,
                                           (void **)&ppszPathOut);
                    IDListFromName = FileSystemBindData;
                    v71 = v87[0];
                    if ( FileSystemBindData >= 0 )
                    {
                      IDListFromName = (*(__int64 (__fastcall **)(PWSTR, struct tagWIN32_FIND_DATA_EX *))(*(_QWORD *)ppszPathOut + 24LL))(
                                         ppszPathOut,
                                         v87[0]);
                      if ( IDListFromName >= 0 )
                      {
                        IDListFromName = (*(__int64 (__fastcall **)(PWSTR, _QWORD))(*(_QWORD *)ppszPathOut + 40LL))(
                                           ppszPathOut,
                                           *((_QWORD *)v71 + 74));
                        if ( IDListFromName >= 0 )
                        {
                          IDListFromName = BindCtx_RegisterObjectParam(v8, L"FindDataFullPath", ppszPathOut, v88);
                          if ( IDListFromName >= 0 )
                          {
                            v8 = (struct IBindCtx *)v88[0];
                            IDListFromName = -2147024891;
                          }
                        }
                      }
                      (*(void (__fastcall **)(PWSTR))(*(_QWORD *)ppszPathOut + 16LL))(ppszPathOut);
                    }
                    CoTaskMemFree(v71);
                    v27 = v79;
                  }
                }
LABEL_63:
                if ( IDListFromName > -2147023584 )
                {
                  if ( IDListFromName != -2147023106 && IDListFromName != -2147023570 && IDListFromName != -2147023499 )
                    goto LABEL_70;
                }
                else if ( IDListFromName != -2147023584
                       && IDListFromName != -2147024891
                       && IDListFromName != -2147024810
                       && IDListFromName != -2147024672
                       && IDListFromName != -2147023652 )
                {
                  if ( (unsigned int)(IDListFromName + 2147024894) <= 1
                    && !v25
                    && (BindCtx_GetMode(v8, 0) & 0x1000) != 0
                    && !(unsigned int)BindCtx_ContainsObject(v8, L"Don't Force Create") )
                  {
                    IDListFromName = CFSFolder::_CreateIDListFromName(
                                       v27,
                                       v17,
                                       0x80u,
                                       v26,
                                       v8,
                                       (struct _ITEMID_CHILD **)&punk);
                  }
                  goto LABEL_70;
                }
LABEL_138:
                if ( v26 )
                {
                  if ( (*((_BYTE *)v27 + 536) & 0x20) != 0 )
                  {
                    pv = 0;
                    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
                      &pv,
                      0);
                    if ( (int)CFSFolder::GetPathForFileAccess(v27, v17, (PWSTR *)&pv) >= 0 && PathIsUNCW((LPCWSTR)pv) )
                    {
                      memset(&NetResource, 0, 24);
                      *(_OWORD *)&NetResource.lpComment = 0;
                      NetResource.lpRemoteName = (LPWSTR)pv;
                      v87[0] = 0;
                      v38 = a2;
                      v68 = WNetUseConnectionW(a2, &NetResource, 0, 0, a2 != 0 ? 8 : 0, 0, 0, 0);
                      IDListFromName = v68;
                      if ( v68 > 0 )
                        IDListFromName = (unsigned __int16)v68 | 0x80070000;
                      if ( IDListFromName == -2147024629 || IDListFromName == -2147024843 )
                      {
                        v72 = (unsigned __int16 **)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(v87);
                        if ( CFSFolder::GetFolderPath(v79, v72) >= 0 )
                        {
                          memset(&NetResource, 0, 24);
                          *(_OWORD *)&NetResource.lpComment = 0;
                          NetResource.lpRemoteName = (LPWSTR)v87[0];
                          v69 = WNetUseConnectionW(a2, &NetResource, 0, 0, a2 != 0 ? 8 : 0, 0, 0, 0);
                          IDListFromName = v69;
                          if ( v69 > 0 )
                            IDListFromName = (unsigned __int16)v69 | 0x80070000;
                        }
                      }
                      v27 = v79;
                      if ( IDListFromName >= 0 )
                        IDListFromName = CFSFolder::_CreateIDListFromName(
                                           v79,
                                           v17,
                                           0xFFFFFFFF,
                                           v26,
                                           v8,
                                           (struct _ITEMID_CHILD **)&punk);
                      if ( v87[0] )
                        CoTaskMemFree(v87[0]);
                    }
                    else
                    {
                      v38 = a2;
                    }
                    if ( pv )
                      LocalFree(pv);
                    goto LABEL_71;
                  }
                  v73 = 1;
                  if ( !(unsigned int)SHSkipJunctionBinding(v8, 0) )
                    v73 = 7;
                  v87[0] = 0;
                  if ( (int)GetFindDataFromBindCtx(v8, v87) >= 0
                    || (int)CFSFolder::_GetFindDataByHandleFromName(v27, v17, v87) >= 0 )
                  {
                    v74 = v87[0];
                    StringCchCopyW((unsigned __int16 *)v87[0] + 22, 0x104u, v17);
                    lpBufferSize = &punk;
                    lpAccessName = v73;
                    IDListFromName = CFSFolder::_CreateIDListWithBindCtx(v79, v74, 0, 0);
                    CoTaskMemFree(v74);
                    v27 = v79;
                  }
                }
                else
                {
                  IDListFromName = CFSFolder::_CreateIDListFromName(
                                     v27,
                                     v17,
                                     0x10u,
                                     0,
                                     v8,
                                     (struct _ITEMID_CHILD **)&punk);
                }
LABEL_70:
                v38 = a2;
LABEL_71:
                v39 = punk;
                v10 = (LPVOID *)a6;
                *a6 = (struct _ITEMIDLIST_RELATIVE *)punk;
                if ( IDListFromName >= 0 )
                {
                  if ( v25 )
                  {
                    v87[0] = 0;
                    IDListFromName = (*(__int64 (__fastcall **)(void *, IUnknown *, struct IBindCtx *, GUID *, struct tagWIN32_FIND_DATA_EX **, int, IUnknown **))(*(_QWORD *)Src + 40LL))(
                                       Src,
                                       v39,
                                       v8,
                                       &GUID_000214e6_0000_0000_c000_000000000046,
                                       v87,
                                       lpAccessName,
                                       lpBufferSize);
                    if ( IDListFromName >= 0 )
                    {
                      Src = 0;
                      IDListFromName = (*(__int64 (__fastcall **)(struct tagWIN32_FIND_DATA_EX *, HWND, struct IBindCtx *, PWSTR, _QWORD, void **, unsigned int *))(*(_QWORD *)v87[0] + 24LL))(
                                         v87[0],
                                         v38,
                                         v8,
                                         v25,
                                         0,
                                         &Src,
                                         v83);
                      if ( IDListFromName >= 0 )
                      {
                        v40 = Src;
                        v41 = *a6;
                        if ( Src && v41 )
                        {
                          v42 = (unsigned __int16 *)*a6;
                          v43 = 2;
                          v44 = 2;
                          do
                          {
                            v45 = *v42;
                            if ( !(_WORD)v45 )
                              break;
                            v44 += v45;
                            v42 = (unsigned __int16 *)((char *)v42 + v45);
                          }
                          while ( v42 );
                          v46 = (unsigned int)(v44 - 2);
                          v47 = (unsigned __int16 *)Src;
                          do
                          {
                            v48 = *v47;
                            if ( !(_WORD)v48 )
                              break;
                            v43 += v48;
                            v47 = (unsigned __int16 *)((char *)v47 + v48);
                          }
                          while ( v47 );
                          v49 = (struct _ITEMIDLIST_RELATIVE *)ILCreate(v43 + (unsigned int)v46);
                          v50 = v49;
                          if ( v49 )
                          {
                            memcpy_0(v49, v41, v46);
                            memcpy_0((char *)v50 + v46, v40, v43);
                          }
                          *a6 = v50;
                          IDListFromName = 0;
                          if ( !v50 )
                            IDListFromName = -2147024882;
                          CoTaskMemFree(v41);
                          CoTaskMemFree(v40);
                        }
                        else
                        {
                          IDListFromName = 0;
                          if ( !v41 )
                          {
                            if ( Src )
                              *a6 = (struct _ITEMIDLIST_RELATIVE *)Src;
                            else
                              IDListFromName = -2147024809;
                          }
                        }
                      }
                      (*(void (__fastcall **)(struct tagWIN32_FIND_DATA_EX *))(*(_QWORD *)v87[0] + 16LL))(v87[0]);
                    }
                  }
                  else
                  {
                    if ( v83 && *v83 )
                    {
                      (*(void (__fastcall **)(void *, __int64, IUnknown **))(*(_QWORD *)Src + 72LL))(Src, 1, &punk);
                      v39 = punk;
                    }
                    CFSFolder::_SetParseAndCreateItem(v27, v8, (const struct _ITEMIDLIST_RELATIVE *)v39);
                  }
                }
                if ( v88[0] )
                  (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v88[0] + 16LL))(v88[0]);
                goto LABEL_118;
              }
            }
            else
            {
              v26 = 1;
            }
            memset_0(v89, 0, 0x268u);
            if ( (unsigned int)PathIsInvalidW(v17) )
            {
              IDListFromName = -2147023696;
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x901,
                (unsigned int)"onecoreuap\\shell\\windows.storage\\filefldr.cpp",
                (const char *)0x800704B0LL,
                ppv);
              v27 = v79;
              goto LABEL_61;
            }
            ppszPathOut = 0;
            pv = 0;
            v27 = v79;
            v28 = (const WCHAR *)*((_QWORD *)v79 + 56);
            if ( !v28 )
            {
              v65 = (unsigned __int16 **)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&pv);
              FolderPath = CFSFolder::GetFolderPath(v79, v65);
              IDListFromName = FolderPath;
              if ( FolderPath < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x4E6,
                  (unsigned int)"onecoreuap\\shell\\windows.storage\\filefldr.cpp",
                  (const char *)(unsigned int)FolderPath,
                  ppv);
                if ( pv )
                  CoTaskMemFree(pv);
                goto LABEL_140;
              }
              v28 = (const WCHAR *)pv;
            }
            v29 = PathAllocCombine(v28, v17, 1u, &ppszPathOut);
            IDListFromName = v29;
            if ( v29 < 0 )
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x4EB,
                (unsigned int)"onecoreuap\\shell\\windows.storage\\filefldr.cpp",
                (const char *)(unsigned int)v29,
                ppv);
            if ( pv )
              CoTaskMemFree(pv);
            if ( IDListFromName >= 0 )
            {
              v30 = 0;
              v87[0] = 0;
              v31 = -2147467262;
              pv = 0;
              if ( v8
                && ((int (__fastcall *)(struct IBindCtx *, const wchar_t *, LPVOID *))v8->lpVtbl->GetObjectParam)(
                     v8,
                     L"bind context timeout value",
                     &pv) >= 0 )
              {
                v32 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, struct tagWIN32_FIND_DATA_EX **))pv)(
                        pv,
                        &GUID_bd1ae5e0_a6ae_11ce_bd37_504200c10000,
                        v87);
                (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
                if ( v32 < 0 )
                  goto LABEL_43;
                pv = 0;
                v31 = (*(__int64 (__fastcall **)(struct tagWIN32_FIND_DATA_EX *, LPVOID *, __int64, __int64))(*(_QWORD *)v87[0] + 48LL))(
                        v87[0],
                        &pv,
                        1,
                        8);
                if ( v31 >= 0 )
                {
                  TickCount = GetTickCount();
                  if ( TickCount - (unsigned int)pv <= HIDWORD(pv) )
                    v30 = HIDWORD(pv) - TickCount + (_DWORD)pv - 1;
                }
                (*(void (__fastcall **)(struct tagWIN32_FIND_DATA_EX *))(*(_QWORD *)v87[0] + 16LL))(v87[0]);
              }
              if ( v31 >= 0 )
              {
                v27 = v79;
                if ( (unsigned int)CFSFolder::_IsNetFolder(v79) )
                {
                  DataForPathWithTimeout = GetFindDataForPathWithTimeout(
                                             ppszPathOut,
                                             v26,
                                             v30,
                                             (struct tagWIN32_FIND_DATA_EX *)v89);
LABEL_45:
                  IDListFromName = DataForPathWithTimeout;
                  if ( DataForPathWithTimeout >= 0 )
                  {
                    if ( ppszPathOut )
                      LocalFree(ppszPathOut);
                    v34 = 0;
                    if ( v8 )
                    {
                      v87[0] = (struct tagWIN32_FIND_DATA_EX *)16;
                      v87[1] = 0;
                      v34 = ((int (__fastcall *)(struct IBindCtx *, struct tagWIN32_FIND_DATA_EX **))v8->lpVtbl->GetBindOptions)(
                              v8,
                              v87) >= 0
                         && HIDWORD(v87[0]) == 2;
                    }
                    v35 = 1;
                    if ( !v34 )
                      v35 = 7;
                    ppszPathOut = 0;
                    v36 = -1091633152;
                    if ( (v89[0] & 0x10) == 0 && v8 )
                    {
                      if ( (int)_BindCtx_GetValue<unsigned short *>(v8, L"ExplicitProgid", &ppszPathOut) >= 0 )
                      {
                        v36 = -1091633126;
                        pv = 0;
                        goto LABEL_56;
                      }
                      ppszPathOut = 0;
                      if ( (int)_BindCtx_GetValue<unsigned short *>(v8, L"ExplicitAssociationApp", &ppszPathOut) >= 0 )
                      {
                        v36 = -1091633125;
                        pv = 0;
                        goto LABEL_56;
                      }
                    }
                    pv = 0;
                    if ( !v8 )
                    {
LABEL_58:
                      FolderEnumMode = BindCtx_GetFolderEnumMode(v8);
                      lpBufferSizea = v35;
                      v27 = v79;
                      IDListFromName = CFSFolder::_CreateIDList(
                                         v79,
                                         (__int64)v89,
                                         0,
                                         0,
                                         (__int64)ppszPathOut,
                                         v36,
                                         lpBufferSizea,
                                         FolderEnumMode,
                                         &punk);
                      if ( IDListFromName >= 0 )
                      {
                        if ( ppszPathOut )
                        {
                          IDListFromName = _BindCtx_SetValue<int>(v8, L"ExplicitAssociationSuccessful", 1);
                          if ( IDListFromName < 0 )
                          {
                            CoTaskMemFree(punk);
                            punk = 0;
                          }
                        }
                      }
                      CoTaskMemFree(ppszPathOut);
                      goto LABEL_61;
                    }
LABEL_56:
                    if ( ((int (__fastcall *)(struct IBindCtx *, const wchar_t *, LPVOID *))v8->lpVtbl->GetObjectParam)(
                           v8,
                           L"Win7FileSystemIdList",
                           &pv) >= 0 )
                    {
                      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
                      v35 |= 8u;
                    }
                    goto LABEL_58;
                  }
LABEL_141:
                  if ( ppszPathOut )
                    LocalFree(ppszPathOut);
LABEL_61:
                  if ( v26 )
                    goto LABEL_63;
                  goto LABEL_62;
                }
LABEL_44:
                DataForPathWithTimeout = GetFindDataForPath(ppszPathOut);
                goto LABEL_45;
              }
LABEL_43:
              v27 = v79;
              goto LABEL_44;
            }
LABEL_140:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x906,
              (unsigned int)"onecoreuap\\shell\\windows.storage\\filefldr.cpp",
              (const char *)(unsigned int)IDListFromName,
              ppv);
            goto LABEL_141;
          }
          goto LABEL_128;
        }
        if ( v11 && *v11 )
        {
          v88[0] = ILFindLastID((LPCITEMIDLIST)*a6);
          ((void (__fastcall *)(IUnknown **, __int64, _QWORD *, unsigned int *))(*this)[9].lpVtbl)(this, 1, v88, v11);
        }
        v51 = *a6;
        ppszPathOut = 0;
        v88[0] = 0;
        if ( v8
          && ((int (__fastcall *)(struct IBindCtx *, const wchar_t *, _QWORD *))v8->lpVtbl->GetObjectParam)(
               v8,
               L"Parse Translate Aliases",
               v88) >= 0 )
        {
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v88[0] + 16LL))(v88[0]);
          return (unsigned int)IDListFromName;
        }
        ppszPathOut = 0;
        v83 = 0;
        if ( !v8 )
          return (unsigned int)IDListFromName;
        if ( ((int (__fastcall *)(struct IBindCtx *, const wchar_t *, unsigned int **))v8->lpVtbl->GetObjectParam)(
               v8,
               L"ParseAndCreateItem",
               &v83) < 0 )
          return (unsigned int)IDListFromName;
        v52 = (**(__int64 (__fastcall ***)(unsigned int *, GUID *, PWSTR *))v83)(
                v83,
                &GUID_67efed0e_e827_4408_b493_78f3982b685c,
                &ppszPathOut);
        (*(void (__fastcall **)(unsigned int *))(*(_QWORD *)v83 + 16LL))(v83);
        if ( v52 < 0 )
          return (unsigned int)IDListFromName;
        punk = 0;
        if ( ((int (__fastcall *)(char *, GUID *, IUnknown **))(*(this - 6))->lpVtbl)(
               (char *)this - 48,
               &GUID_000214e6_0000_0000_c000_000000000046,
               &punk) < 0 )
        {
LABEL_112:
          (*(void (__fastcall **)(PWSTR))(*(_QWORD *)ppszPathOut + 16LL))(ppszPathOut);
          return (unsigned int)IDListFromName;
        }
        pv = 0;
        if ( v51 )
        {
          v53 = (IShellFolder *)punk;
          if ( punk )
          {
            if ( !*(_WORD *)v51 || (v64 = (_WORD *)((char *)v51 + *(unsigned __int16 *)v51)) == 0 || !*v64 )
            {
              v55 = ((__int64 (__fastcall *)(IUnknown *, GUID *, LPVOID *))punk->lpVtbl->QueryInterface)(
                      punk,
                      &GUID_ff314a1e_06fa_4f3a_84be_7aa1c6be2470,
                      &pv);
LABEL_105:
              if ( v55 >= 0 )
              {
                v56 = *(_WORD *)v51;
                if ( *(_WORD *)v51 )
                {
                  do
                  {
                    v57 = v51;
                    v51 = (const struct _ITEMIDLIST_RELATIVE *)((char *)v51 + v56);
                    v56 = *(_WORD *)v51;
                  }
                  while ( *(_WORD *)v51 );
                }
                else
                {
                  v57 = v51;
                }
                v83 = 0;
                if ( (*(int (__fastcall **)(LPVOID, const struct _ITEMIDLIST_RELATIVE *, GUID *, unsigned int **))(*(_QWORD *)pv + 24LL))(
                       pv,
                       v57,
                       &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
                       &v83) >= 0 )
                {
                  (*(void (__fastcall **)(PWSTR, unsigned int *))(*(_QWORD *)ppszPathOut + 24LL))(ppszPathOut, v83);
                  (*(void (__fastcall **)(unsigned int *))(*(_QWORD *)v83 + 16LL))(v83);
                }
                (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
              }
              goto LABEL_111;
            }
          }
          v54 = (ITEMIDLIST *)ILCloneParent(v51);
          if ( v54 )
          {
            v55 = SHBindToObject(v53, v54, v8, &GUID_ff314a1e_06fa_4f3a_84be_7aa1c6be2470, &pv);
            CoTaskMemFree(v54);
            goto LABEL_105;
          }
        }
LABEL_111:
        ((void (__fastcall *)(IUnknown *))punk->lpVtbl->Release)(punk);
        goto LABEL_112;
      }
    }
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x1800f1da0  push    rbp
0x1800f1da2  push    rbx
0x1800f1da3  push    rsi
0x1800f1da4  push    rdi
0x1800f1da5  push    r12
0x1800f1da7  push    r13
0x1800f1da9  push    r14
0x1800f1dab  push    r15
0x1800f1dad  lea     rbp, [rsp-268h]
0x1800f1db5  sub     rsp, 368h
0x1800f1dbc  mov     rax, cs:__security_cookie
0x1800f1dc3  xor     rax, rsp
0x1800f1dc6  mov     [rbp+2A0h+var_50], rax
0x1800f1dcd  mov     rdi, r9
0x1800f1dd0  mov     r14, r8
0x1800f1dd3  mov     [rsp+3A0h+hwndOwner], rdx
0x1800f1dd8  mov     r13, rcx
0x1800f1ddb  mov     [rbp+2A0h+Src], rcx
0x1800f1ddf  mov     r12, [rbp+2A0h+arg_28]
0x1800f1de6  mov     [rsp+3A0h+var_340], r12
0x1800f1deb  mov     rbx, [rbp+2A0h+arg_30]
0x1800f1df2  mov     [rsp+3A0h+var_328], rbx
0x1800f1df7  test    r12, r12
0x1800f1dfa  jz      loc_1800F2742
0x1800f1e00  xor     eax, eax
0x1800f1e02  mov     [r12], rax
0x1800f1e06  test    r9, r9
0x1800f1e09  jz      loc_1800F2742
0x1800f1e0f  cmp     [r9], ax
0x1800f1e13  jz      loc_1800F2742
0x1800f1e19  mov     [rsp+3A0h+punk], rax
0x1800f1e1e  mov     [rbp+2A0h+pv], rax
0x1800f1e22  test    r8, r8
0x1800f1e25  jz      loc_1800F1F36
0x1800f1e2b  mov     rax, [r8]
0x1800f1e2e  lea     r8, [rbp+2A0h+pv]
0x1800f1e32  lea     rdx, aItemcacheconte; "ItemCacheContext"
0x1800f1e39  mov     rcx, r14
0x1800f1e3c  mov     rax, [rax+50h]
0x1800f1e40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f1e45  test    eax, eax
0x1800f1e47  js      loc_1800F1F36
0x1800f1e4d  mov     rcx, [rbp+2A0h+pv]
0x1800f1e51  mov     rax, [rcx]
0x1800f1e54  lea     r8, [rsp+3A0h+punk]
0x1800f1e59  lea     rdx, _GUID_0000000e_0000_0000_c000_000000000046
0x1800f1e60  mov     rax, [rax]
0x1800f1e63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f1e68  mov     ebx, eax
0x1800f1e6a  mov     rdx, [rbp+2A0h+pv]
0x1800f1e6e  mov     rcx, [rdx]
0x1800f1e71  mov     rax, [rcx+10h]
0x1800f1e75  mov     rcx, rdx
0x1800f1e78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f1e7d  test    ebx, ebx
0x1800f1e7f  js      loc_1800F1F31
0x1800f1e85  lea     rbx, [r13+118h]
0x1800f1e8c  lea     rax, aFsfolderResolv; "FSFolder_ResolveSidToUserName"
0x1800f1e93  mov     [rbx+10h], rax
0x1800f1e97  mov     rdx, [rsp+3A0h+punk]; punk
0x1800f1e9c  mov     rcx, rbx; ppunk
0x1800f1e9f  call    cs:__imp_IUnknown_Set
0x1800f1ea6  nop     dword ptr [rax+rax+00h]
0x1800f1eab  lea     rcx, [rbx+18h]; ppunk
0x1800f1eaf  lea     rax, aFsfolderConver; "FSFolder_ConvertToSidString"
0x1800f1eb6  mov     [rcx+10h], rax
0x1800f1eba  mov     rdx, [rsp+3A0h+punk]; punk
0x1800f1ebf  call    cs:__imp_IUnknown_Set
0x1800f1ec6  nop     dword ptr [rax+rax+00h]
0x1800f1ecb  lea     rcx, [rbx+30h]; ppunk
0x1800f1ecf  lea     rax, aFsfolderInplac; "FSFolder_InplaceShareEngine"
0x1800f1ed6  mov     [rcx+10h], rax
0x1800f1eda  mov     rdx, [rsp+3A0h+punk]; punk
0x1800f1edf  call    cs:__imp_IUnknown_Set
0x1800f1ee6  nop     dword ptr [rax+rax+00h]
0x1800f1eeb  lea     rcx, [rbx+48h]; ppunk
0x1800f1eef  lea     rax, aFsfolderSmbsha; "FSFolder_SmbShareEngine"
0x1800f1ef6  mov     [rcx+10h], rax
0x1800f1efa  mov     rdx, [rsp+3A0h+punk]; punk
0x1800f1eff  call    cs:__imp_IUnknown_Set
0x1800f1f06  nop     dword ptr [rax+rax+00h]
0x1800f1f0b  lea     rcx, [rbx+60h]; ppunk
0x1800f1f0f  mov     rdx, [rsp+3A0h+punk]; punk
0x1800f1f14  call    cs:__imp_IUnknown_Set
0x1800f1f1b  nop     dword ptr [rax+rax+00h]
0x1800f1f20  mov     rcx, [rsp+3A0h+punk]
0x1800f1f25  mov     rax, [rcx]
0x1800f1f28  mov     rax, [rax+10h]
0x1800f1f2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f1f31  mov     rbx, [rsp+3A0h+var_328]
0x1800f1f36  lea     r15, [r13-30h]
0x1800f1f3a  mov     [rsp+3A0h+var_350], r15
0x1800f1f3f  mov     r9, r12; struct _ITEMIDLIST_RELATIVE **
0x1800f1f42  mov     r8, r14; struct IBindCtx *
0x1800f1f45  mov     rdx, rdi; unsigned __int16 *
0x1800f1f48  mov     rcx, r15; this
0x1800f1f4b  call    ?TrySimpleParse@CFSFolder@@IEAAJPEBGPEAUIBindCtx@@PEAPEAU_ITEMIDLIST_RELATIVE@@@Z; CFSFolder::TrySimpleParse(ushort const *,IBindCtx *,_ITEMIDLIST_RELATIVE * *)
0x1800f1f50  mov     esi, eax
0x1800f1f52  test    eax, eax
0x1800f1f54  jz      loc_1800F24AB
0x1800f1f5a  cmp     eax, 1
0x1800f1f5d  jnz     loc_1800F26B7
0x1800f1f63  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x1800f1f6a  nop     word ptr [rax+rax+00h]
0x1800f1f70  inc     rbx
0x1800f1f73  cmp     word ptr [rdi+rbx*2], 0
0x1800f1f78  jnz     short loc_1800F1F70
0x1800f1f7a  inc     rbx
0x1800f1f7d  mov     [rbp+2A0h+var_2D0], 0
0x1800f1f85  mov     eax, 2
0x1800f1f8a  mul     rbx
0x1800f1f8d  test    rdx, rdx
0x1800f1f90  jnz     loc_1800F2480
0x1800f1f96  mov     rdx, rax; uBytes
0x1800f1f99  mov     ecx, 40h ; '@'; uFlags
0x1800f1f9e  call    cs:__imp_LocalAlloc
0x1800f1fa5  nop     dword ptr [rax+rax+00h]
0x1800f1faa  mov     r13, rax
0x1800f1fad  xor     esi, esi
0x1800f1faf  mov     eax, 8007000Eh
0x1800f1fb4  test    r13, r13
0x1800f1fb7  cmovz   esi, eax
0x1800f1fba  jz      loc_1800F2485
0x1800f1fc0  xor     eax, eax
0x1800f1fc2  mov     [r13+0], ax
0x1800f1fc7  mov     edx, 5Ch ; '\'; wMatch
0x1800f1fcc  mov     rcx, rdi; pszStart
0x1800f1fcf  call    cs:__imp_StrChrW
0x1800f1fd6  nop     dword ptr [rax+rax+00h]
0x1800f1fdb  mov     r9, rax
0x1800f1fde  test    rax, rax
0x1800f1fe1  jz      loc_1800F26E5
0x1800f1fe7  cmp     rax, rdi
0x1800f1fea  jbe     loc_1800F2738
0x1800f1ff0  test    rbx, rbx
0x1800f1ff3  jz      short loc_1800F2052
0x1800f1ff5  cmp     rbx, 7FFFFFFFh
0x1800f1ffc  ja      loc_1800F2C9A
0x1800f2002  sub     rax, rdi
0x1800f2005  sar     rax, 1
0x1800f2008  movsxd  rdx, eax
0x1800f200b  mov     ecx, 7FFFFFFEh
0x1800f2010  cmp     rdx, rcx
0x1800f2013  ja      loc_1800F2CA6
0x1800f2019  mov     rcx, rdi
0x1800f201c  mov     r8, r13
0x1800f201f  nop
0x1800f2020  test    rdx, rdx
0x1800f2023  jz      short loc_1800F2042
0x1800f2025  movzx   eax, word ptr [rcx]
0x1800f2028  test    ax, ax
0x1800f202b  jz      short loc_1800F2042
0x1800f202d  add     rcx, 2
0x1800f2031  mov     [r8], ax
0x1800f2035  add     r8, 2
0x1800f2039  dec     rdx
0x1800f203c  sub     rbx, 1
0x1800f2040  jnz     short loc_1800F2020
0x1800f2042  lea     rcx, [r8-2]
0x1800f2046  test    rbx, rbx
0x1800f2049  cmovnz  rcx, r8
0x1800f204d  xor     eax, eax
0x1800f204f  mov     [rcx], ax
0x1800f2052  lea     rax, [r9+2]
0x1800f2056  xor     r15d, r15d
0x1800f2059  cmp     [rax], r15w
0x1800f205d  cmovnz  r15, rax
0x1800f2061  mov     rcx, r13; unsigned __int16 *
0x1800f2064  call    ?ValidPathSegment@@YAHPEBG@Z; ValidPathSegment(ushort const *)
0x1800f2069  test    eax, eax
0x1800f206b  jz      loc_1800F2731
0x1800f2071  xor     ebx, ebx
0x1800f2073  mov     [rsp+3A0h+punk], rbx
0x1800f2078  mov     [rbp+2A0h+var_2D0], rbx
0x1800f207c  test    r15, r15
0x1800f207f  jz      loc_1800F281A
0x1800f2085  mov     r12d, ebx
0x1800f2088  mov     rax, [rbp+2A0h+Src]
0x1800f208c  test    byte ptr [rax+1E8h], 20h
0x1800f2093  jnz     loc_1800F2CCC
0x1800f2099  xor     edx, edx; Val
0x1800f209b  mov     r8d, 268h; Size
0x1800f20a1  lea     rcx, [rbp+2A0h+var_2C0]; void *
0x1800f20a5  call    memset_0
0x1800f20aa  mov     rcx, r13; unsigned __int16 *
0x1800f20ad  call    PathIsInvalidW
0x1800f20b2  test    eax, eax
0x1800f20b4  jnz     loc_1800F2CFB
0x1800f20ba  mov     [rsp+3A0h+ppszPathOut], rbx
0x1800f20bf  mov     [rbp+2A0h+pv], rbx
0x1800f20c3  mov     rbx, [rsp+3A0h+var_350]
0x1800f20c8  mov     rcx, [rbx+1C0h]; pszPathIn
0x1800f20cf  test    rcx, rcx
0x1800f20d2  jz      loc_1800F2A09
0x1800f20d8  lea     r9, [rsp+3A0h+ppszPathOut]; ppszPathOut
0x1800f20dd  mov     r8d, 1; dwFlags
0x1800f20e3  mov     rdx, r13; pszMore
0x1800f20e6  call    cs:__imp_PathAllocCombine
0x1800f20ed  nop     dword ptr [rax+rax+00h]
0x1800f20f2  mov     esi, eax
0x1800f20f4  test    eax, eax
0x1800f20f6  js      loc_1800F2D25
0x1800f20fc  mov     rcx, [rbp+2A0h+pv]; pv
0x1800f2100  test    rcx, rcx
0x1800f2103  jz      short loc_1800F2111
0x1800f2105  call    cs:__imp_CoTaskMemFree
0x1800f210c  nop     dword ptr [rax+rax+00h]
0x1800f2111  test    esi, esi
0x1800f2113  js      loc_1800F27E0
0x1800f2119  xor     eax, eax
0x1800f211b  mov     esi, eax
0x1800f211d  mov     [rbp+2A0h+var_2E0], rax
0x1800f2121  mov     ebx, 80004002h
0x1800f2126  mov     [rbp+2A0h+pv], rax
0x1800f212a  test    r14, r14
0x1800f212d  jz      loc_1800F292D
0x1800f2133  mov     rax, [r14]
0x1800f2136  lea     r8, [rbp+2A0h+pv]
0x1800f213a  lea     rdx, aBindContextTim; "bind context timeout value"
0x1800f2141  mov     rcx, r14
0x1800f2144  mov     rax, [rax+50h]
0x1800f2148  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f214d  test    eax, eax
0x1800f214f  js      loc_1800F292D
0x1800f2155  mov     rcx, [rbp+2A0h+pv]
0x1800f2159  mov     rax, [rcx]
0x1800f215c  lea     r8, [rbp+2A0h+var_2E0]
0x1800f2160  lea     rdx, _GUID_bd1ae5e0_a6ae_11ce_bd37_504200c10000
0x1800f2167  mov     rax, [rax]
0x1800f216a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f216f  mov     ebx, eax
0x1800f2171  mov     rcx, [rbp+2A0h+pv]
0x1800f2175  mov     rax, [rcx]
0x1800f2178  mov     rax, [rax+10h]
0x1800f217c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f2181  test    ebx, ebx
0x1800f2183  jns     loc_1800F28EF
0x1800f2189  mov     rbx, [rsp+3A0h+var_350]
0x1800f218e  lea     r8, [rbp+2A0h+var_2C0]
0x1800f2192  mov     edx, r12d
0x1800f2195  mov     rcx, [rsp+3A0h+ppszPathOut]; Src
0x1800f219a  call    GetFindDataForPath
0x1800f219f  mov     esi, eax
0x1800f21a1  test    eax, eax
0x1800f21a3  js      loc_1800F27FB
0x1800f21a9  mov     rcx, [rsp+3A0h+ppszPathOut]; hMem
0x1800f21ae  test    rcx, rcx
0x1800f21b1  jnz     loc_1800F2844
0x1800f21b7  xor     esi, esi
0x1800f21b9  mov     eax, esi
0x1800f21bb  test    r14, r14
0x1800f21be  jz      short loc_1800F21F6
0x1800f21c0  mov     [rbp+2A0h+var_2E0], 10h
0x1800f21c8  mov     [rbp+2A0h+var_2D8], rax
0x1800f21cc  mov     rax, [r14]
0x1800f21cf  lea     rdx, [rbp+2A0h+var_2E0]
0x1800f21d3  mov     rcx, r14
0x1800f21d6  mov     rax, [rax+38h]
0x1800f21da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f21df  test    eax, eax
0x1800f21e1  js      loc_1800F2825
0x1800f21e7  cmp     dword ptr [rbp+2A0h+var_2E0+4], 2
0x1800f21eb  jnz     loc_1800F2825
0x1800f21f1  mov     eax, 1
0x1800f21f6  mov     ebx, 1
0x1800f21fb  test    eax, eax
0x1800f21fd  mov     eax, 7
0x1800f2202  cmovz   ebx, eax
0x1800f2205  mov     [rsp+3A0h+ppszPathOut], rsi
0x1800f220a  mov     esi, 0BEEF0000h
0x1800f220f  test    [rbp+2A0h+var_2C0], 10h
0x1800f2213  jz      loc_1800F2855
0x1800f2219  mov     [rbp+2A0h+pv], 0
0x1800f2221  test    r14, r14
0x1800f2224  jz      short loc_1800F2248
0x1800f2226  mov     rax, [r14]
0x1800f2229  lea     r8, [rbp+2A0h+pv]
0x1800f222d  lea     rdx, aWin7filesystem; "Win7FileSystemIdList"
0x1800f2234  mov     rcx, r14
0x1800f2237  mov     rax, [rax+50h]
0x1800f223b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f2240  test    eax, eax
0x1800f2242  jns     loc_1800F282C
0x1800f2248  mov     rcx, r14; struct IBindCtx *
0x1800f224b  call    ?BindCtx_GetFolderEnumMode@@YA?AW4FOLDER_ENUM_MODE@@PEAUIBindCtx@@@Z; BindCtx_GetFolderEnumMode(IBindCtx *)
0x1800f2250  mov     rcx, [rsp+3A0h+ppszPathOut]
0x1800f2255  lea     rdx, [rsp+3A0h+punk]
0x1800f225a  mov     [rsp+3A0h+var_360], rdx
0x1800f225f  mov     dword ptr [rsp+3A0h+lpResult], eax
0x1800f2263  mov     dword ptr [rsp+3A0h+lpBufferSize], ebx
0x1800f2267  mov     dword ptr [rsp+3A0h+lpAccessName], esi
0x1800f226b  mov     [rsp+3A0h+ppv], rcx
0x1800f2270  xor     r9d, r9d
0x1800f2273  xor     r8d, r8d
0x1800f2276  lea     rdx, [rbp+2A0h+var_2C0]
0x1800f227a  mov     rbx, [rsp+3A0h+var_350]
0x1800f227f  mov     rcx, rbx
0x1800f2282  call    ?_CreateIDList@CFSFolder@@IEAAJPEBUtagWIN32_FIND_DATA_EX@@PEFBU_ITEMIDLIST_RELATIVE@@PEBG2W4IDLHID@@W4CREATE_IDLIST_FLAGS@@W4FOLDER_ENUM_MODE@@PEAPEAU_ITEMID_CHILD@@@Z; CFSFolder::_CreateIDList(tagWIN32_FIND_DATA_EX const *,_ITEMIDLIST_RELATIVE const *,ushort const *,ushort const *,IDLHID,CREATE_IDLIST_FLAGS,FOLDER_ENUM_MODE,_ITEMID_CHILD * *)
0x1800f2287  mov     esi, eax
0x1800f2289  test    eax, eax
  ... truncated ...
```
