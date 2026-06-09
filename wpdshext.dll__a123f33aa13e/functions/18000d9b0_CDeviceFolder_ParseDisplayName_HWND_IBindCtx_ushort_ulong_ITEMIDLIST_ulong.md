# CDeviceFolder::ParseDisplayName(HWND__ *,IBindCtx *,ushort *,ulong *,_ITEMIDLIST * *,ulong *)

- ea: `0x18000d9b0`
- end: `0x18000e4cb`
- name: `?ParseDisplayName@CDeviceFolder@@UEAAJPEAUHWND__@@PEAUIBindCtx@@PEAGPEAKPEAPEFAU_ITEMIDLIST@@3@Z`
- size: `2843`
- prototype: `__int64 __fastcall(CDeviceFolder *__hidden this, HWND, struct IBindCtx *, unsigned __int16 *, unsigned int *, struct _ITEMIDLIST **, unsigned int *)`
- caller_count: `0`
- callee_count: `18`
- tags: `service_task, broker_com_uri`

## callees

- `0x180004110`
- `0x180007860`
- `0x18000cc48`
- `0x18000d9b0`
- `0x18000e4d4`
- `0x18001a5b0`
- `0x18001d6b0`
- `0x18001d860`
- `0x180023c34`
- `0x1800285c8`
- `0x1800287d0`
- `0x18002ff5c`
- `0x180035590`
- `0x1800361ba`
- `0x180039e80`
- `0x18006bc1c`
- `0x180075530`
- `0x180078010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18000dd3e`
- `KERNEL32!EnterCriticalSection` at `0x18000dd3e`
- `KERNEL32!LeaveCriticalSection` at `0x18000dd5a`
- `KERNEL32!LeaveCriticalSection` at `0x18000dd88`
- `KERNEL32!LeaveCriticalSection` at `0x18000ddf9`
- `KERNEL32!LeaveCriticalSection` at `0x18000dd5a`
- `KERNEL32!LeaveCriticalSection` at `0x18000dd88`
- `KERNEL32!LeaveCriticalSection` at `0x18000ddf9`
- `SHLWAPI!StrCmpW` at `0x18000df27`
- `SHLWAPI!StrCmpW` at `0x18000df40`
- `SHLWAPI!StrCmpW` at `0x18000df59`
- `SHLWAPI!StrCmpW` at `0x18000df27`
- `SHLWAPI!StrCmpW` at `0x18000df40`
- `SHLWAPI!StrCmpW` at `0x18000df59`
- `ole32!CoTaskMemFree` at `0x18000e43c`
- `ole32!CoTaskMemFree` at `0x18000e451`
- `ole32!CoTaskMemFree` at `0x18000e43c`
- `ole32!CoTaskMemFree` at `0x18000e451`
- `ole32!CoTaskMemAlloc` at `0x18000da83`
- `ole32!CoTaskMemAlloc` at `0x18000da91`
- `ole32!CoTaskMemAlloc` at `0x18000da83`
- `ole32!CoTaskMemAlloc` at `0x18000da91`
- `SHELL32!__imp_ILFindLastID` at `0x18000dda3`
- `SHELL32!__imp_ILFindLastID` at `0x18000dda3`
- `SHELL32!__imp_ILClone` at `0x18000e2ec`
- `SHELL32!__imp_ILClone` at `0x18000e2ec`
- `SHELL32!__imp_ILFree` at `0x18000dc8b`
- `SHELL32!__imp_ILFree` at `0x18000e221`
- `SHELL32!__imp_ILFree` at `0x18000e2cc`
- `SHELL32!__imp_ILFree` at `0x18000e3de`
- `SHELL32!__imp_ILFree` at `0x18000e3fe`
- `SHELL32!__imp_ILFree` at `0x18000e41e`
- `SHELL32!__imp_ILFree` at `0x18000dc8b`
- `SHELL32!__imp_ILFree` at `0x18000e221`
- `SHELL32!__imp_ILFree` at `0x18000e2cc`
- `SHELL32!__imp_ILFree` at `0x18000e3de`
- `SHELL32!__imp_ILFree` at `0x18000e3fe`
- `SHELL32!__imp_ILFree` at `0x18000e41e`

## string_xrefs

- `0x18000df1c`: `WPDSHSERVICEOBJECT_STADD`
- `0x18000df35`: `WPDSHSERVICEOBJECT_STREM`
- `0x18000df4e`: `WPDSHSERVICEOBJECT_EVENT`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CDeviceFolder::ParseDisplayName(
        CDeviceFolder *this,
        HWND a2,
        struct IBindCtx *a3,
        unsigned __int16 *a4,
        unsigned int *a5,
        struct _ITEMIDLIST **a6,
        unsigned int *a7)
{
  unsigned int *v8; // rdi
  unsigned __int64 i; // rdx
  __int64 v10; // rcx
  int WpdDevicePathFromAnyPath; // ebx
  PVOID *v12; // r10
  _WORD *v13; // rsi
  unsigned __int16 *v14; // rax
  unsigned __int16 *v15; // r13
  __int64 v16; // rcx
  __int64 v17; // r8
  _WORD *v18; // r9
  __int16 v19; // ax
  int v20; // eax
  _WORD *v21; // rcx
  _QWORD *v22; // rax
  __int64 v23; // rdx
  unsigned __int64 v24; // rcx
  _WORD *v25; // r10
  unsigned int v26; // r9d
  unsigned int v27; // r9d
  CDeviceCache *v28; // rcx
  struct DEVITEM_CACHE *Item; // rax
  __int64 v30; // rcx
  const ITEMIDLIST *Ptr; // rax
  LPITEMIDLIST ID; // rax
  CDeviceFolder *v33; // r14
  _QWORD *v34; // rcx
  __int64 v35; // rdx
  CDeviceFolder *v36; // rcx
  _QWORD *v37; // rcx
  __int64 v38; // rdx
  ITEMIDLIST *v39; // r14
  const struct DEVICEITEM *v40; // rax
  _QWORD *v41; // rax
  __int64 v42; // rdx
  LPCITEMIDLIST v44; // [rsp+40h] [rbp-C0h] BYREF
  LPITEMIDLIST v45; // [rsp+48h] [rbp-B8h] BYREF
  GUID AliasInterfaceClassGuid; // [rsp+50h] [rbp-B0h] BYREF
  LPITEMIDLIST pidl; // [rsp+60h] [rbp-A0h] BYREF
  LPITEMIDLIST v48; // [rsp+68h] [rbp-98h] BYREF
  int v49; // [rsp+70h] [rbp-90h] BYREF
  CDeviceFolder *v50; // [rsp+78h] [rbp-88h] BYREF
  __int64 v51; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int64 v52; // [rsp+88h] [rbp-78h] BYREF
  int v53; // [rsp+90h] [rbp-70h] BYREF
  unsigned int *v54; // [rsp+98h] [rbp-68h]
  struct IBindCtx *v55; // [rsp+A0h] [rbp-60h]
  HWND v56; // [rsp+A8h] [rbp-58h]
  WCHAR psz1[8]; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v58; // [rsp+C0h] [rbp-40h]
  __int128 v59; // [rsp+D0h] [rbp-30h]
  __int16 v60; // [rsp+E0h] [rbp-20h]
  unsigned __int16 v61[264]; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int16 v62[2080]; // [rsp+300h] [rbp+200h] BYREF

  v55 = a3;
  v56 = a2;
  v50 = this;
  v8 = a5;
  v52 = (unsigned __int64)a5;
  v54 = a7;
  i = 0;
  pidl = 0;
  v44 = 0;
  v48 = 0;
  v45 = 0;
  v49 = 0;
  *(_OWORD *)psz1 = 0;
  v58 = 0;
  v59 = 0;
  v60 = 0;
  v10 = 0;
  v51 = 0;
  if ( !a4 )
  {
    WpdDevicePathFromAnyPath = -2147024809;
    v12 = &WPP_GLOBAL_Control;
    goto LABEL_157;
  }
  if ( !a6 )
  {
    WpdDevicePathFromAnyPath = -2147024809;
    v12 = &WPP_GLOBAL_Control;
    goto LABEL_157;
  }
  *a6 = 0;
  if ( a5 )
    *a5 = 0;
  v13 = CoTaskMemAlloc(0x1040u);
  v14 = (unsigned __int16 *)CoTaskMemAlloc(0x1040u);
  v15 = v14;
  v12 = &WPP_GLOBAL_Control;
  if ( !v13 || !v14 )
  {
    WpdDevicePathFromAnyPath = -2147024882;
    goto LABEL_146;
  }
  memset_0(v13, 0, 0x1040u);
  memset_0(v15, 0, 0x1040u);
  v16 = 2147483646;
  i = (unsigned __int64)a4;
  v17 = 2080;
  v18 = v13;
  do
  {
    if ( !v16 )
      break;
    v19 = *(_WORD *)i;
    if ( !*(_WORD *)i )
      break;
    i += 2LL;
    *v18++ = v19;
    --v16;
    --v17;
  }
  while ( v17 );
  WpdDevicePathFromAnyPath = -2147024774;
  v20 = 0;
  if ( v17 )
    WpdDevicePathFromAnyPath = 0;
  v21 = v18 - 1;
  if ( v17 )
    v21 = v18;
  *v21 = 0;
  if ( !v17 )
  {
    v22 = WPP_GLOBAL_Control;
    v12 = &WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_146;
    v23 = 56;
    goto LABEL_21;
  }
  v24 = -1;
  do
    ++v24;
  while ( v13[v24] );
  if ( v24 < 2 )
  {
    WpdDevicePathFromAnyPath = -2147024809;
    v12 = &WPP_GLOBAL_Control;
    goto LABEL_146;
  }
  if ( *v13 != 92 )
  {
    WpdDevicePathFromAnyPath = -2147024809;
    v12 = &WPP_GLOBAL_Control;
    goto LABEL_146;
  }
  if ( v13[1] != 92 )
  {
    WpdDevicePathFromAnyPath = -2147024809;
    v12 = &WPP_GLOBAL_Control;
    goto LABEL_146;
  }
  *v15 = 0;
  for ( i = 2; ; ++i )
  {
    if ( i >= v24 )
    {
      if ( !v20 )
      {
        WpdDevicePathFromAnyPath = -2147024809;
        goto LABEL_52;
      }
LABEL_41:
      WpdDevicePathFromAnyPath = (*(__int64 (__fastcall **)(CDeviceFolder *, _QWORD, __int64, __int64 *))(*(_QWORD *)v50 + 32LL))(
                                   v50,
                                   0,
                                   224,
                                   &v51);
      if ( WpdDevicePathFromAnyPath )
        goto LABEL_52;
      while ( !(*(unsigned int (__fastcall **)(__int64, __int64, LPITEMIDLIST *, int *))(*(_QWORD *)v51 + 24LL))(
                 v51,
                 1,
                 &pidl,
                 &v49) )
      {
        if ( pidl )
        {
          ILFree(pidl);
          pidl = 0;
        }
      }
      AliasInterfaceClassGuid = GUID_DEVINTERFACE_WPD;
      if ( (int)GetWpdDevicePathFromAnyPath(&AliasInterfaceClassGuid, v13, v61, v26) < 0 )
      {
        AliasInterfaceClassGuid = GUID_DEVINTERFACE_WPD_PRIVATE;
        WpdDevicePathFromAnyPath = GetWpdDevicePathFromAnyPath(&AliasInterfaceClassGuid, v13, v61, v27);
        if ( WpdDevicePathFromAnyPath < 0 )
        {
          v12 = &WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
            goto LABEL_146;
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            58,
            (unsigned int)WPP_4da16da3d21a3bea60eae2174f41afdd_Traceguids,
            (_DWORD)v13,
            WpdDevicePathFromAnyPath);
LABEL_52:
          v12 = &WPP_GLOBAL_Control;
          goto LABEL_146;
        }
      }
      EnterCriticalSection(&g_csDeviceCache);
      if ( !g_pDeviceCache )
        goto LABEL_54;
      v44 = 0;
      Item = CDeviceCache::_FindItem(v28, v61);
      if ( !Item )
      {
        WpdDevicePathFromAnyPath = -2147467259;
        LeaveCriticalSection(&g_csDeviceCache);
        goto LABEL_64;
      }
      v30 = *((_QWORD *)Item + 3);
      if ( !v30 )
      {
LABEL_54:
        WpdDevicePathFromAnyPath = -2147418113;
LABEL_55:
        LeaveCriticalSection(&g_csDeviceCache);
        goto LABEL_64;
      }
      Ptr = (const ITEMIDLIST *)IsolationAwareDPA_GetPtr(v30, 0);
      ID = ILFindLastID(Ptr);
      WpdDevicePathFromAnyPath = SHILCloneFirst(ID, &v44);
      if ( WpdDevicePathFromAnyPath < 0
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          47,
          WPP_97b3e7d056e530596454d4c68ce08f99_Traceguids,
          (unsigned int)WpdDevicePathFromAnyPath);
        goto LABEL_55;
      }
      LeaveCriticalSection(&g_csDeviceCache);
      if ( WpdDevicePathFromAnyPath < 0 )
      {
LABEL_64:
        v12 = &WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            48,
            WPP_97b3e7d056e530596454d4c68ce08f99_Traceguids,
            (unsigned int)WpdDevicePathFromAnyPath);
          v12 = &WPP_GLOBAL_Control;
        }
        v22 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_146;
        v23 = 59;
LABEL_21:
        WPP_SF_d(v22[2], v23, WPP_4da16da3d21a3bea60eae2174f41afdd_Traceguids, (unsigned int)WpdDevicePathFromAnyPath);
        v12 = &WPP_GLOBAL_Control;
        goto LABEL_146;
      }
      if ( !v44 )
      {
        WpdDevicePathFromAnyPath = -2147467259;
        goto LABEL_52;
      }
      if ( *v15 )
      {
        if ( v15[1] )
        {
          v53 = 0;
          *(_QWORD *)&AliasInterfaceClassGuid.Data1 = 0;
          v33 = v50;
          WpdDevicePathFromAnyPath = (*(__int64 (__fastcall **)(CDeviceFolder *, LPCITEMIDLIST, _QWORD, GUID *, GUID *))(*(_QWORD *)v50 + 40LL))(
                                       v50,
                                       v44,
                                       0,
                                       &GUID_000214e6_0000_0000_c000_000000000046,
                                       &AliasInterfaceClassGuid);
          if ( WpdDevicePathFromAnyPath < 0 )
          {
            v34 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
              goto LABEL_112;
            v35 = 60;
            goto LABEL_78;
          }
          StringCchCopyW(psz1, 0x19u, v15 + 1);
          if ( StrCmpW(psz1, L"WPDSHSERVICEOBJECT_STADD") && StrCmpW(psz1, L"WPDSHSERVICEOBJECT_STREM") )
          {
            if ( StrCmpW(psz1, L"WPDSHSERVICEOBJECT_EVENT") )
            {
              WpdDevicePathFromAnyPath = (*(__int64 (__fastcall **)(_QWORD, HWND, struct IBindCtx *, unsigned __int16 *, int *, LPITEMIDLIST *, unsigned int *))(**(_QWORD **)&AliasInterfaceClassGuid.Data1 + 24LL))(
                                           *(_QWORD *)&AliasInterfaceClassGuid.Data1,
                                           v56,
                                           v55,
                                           v15 + 1,
                                           &v53,
                                           &v48,
                                           v54);
              if ( WpdDevicePathFromAnyPath < 0 )
              {
                v34 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
                  goto LABEL_112;
                v35 = 64;
LABEL_78:
                WPP_SF_d(
                  v34[2],
                  v35,
                  WPP_4da16da3d21a3bea60eae2174f41afdd_Traceguids,
                  (unsigned int)WpdDevicePathFromAnyPath);
LABEL_112:
                ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&AliasInterfaceClassGuid);
                v12 = &WPP_GLOBAL_Control;
                goto LABEL_146;
              }
              WpdDevicePathFromAnyPath = SHILCombine(v44, v48, &v45);
              if ( WpdDevicePathFromAnyPath < 0 )
              {
                v37 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
                  goto LABEL_96;
                v38 = 65;
                goto LABEL_95;
              }
              v39 = v45;
            }
            else
            {
              LODWORD(v50) = 0;
              memset_0(v62, 0, sizeof(v62));
              WpdDevicePathFromAnyPath = CDeviceFolder::_ParseShServiceObjectEvent(
                                           (CDeviceFolder *)((char *)v33 - 16),
                                           (struct _ITEMIDLIST *)v44,
                                           v15 + 25,
                                           v62);
              if ( WpdDevicePathFromAnyPath < 0 )
              {
                v34 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
                  goto LABEL_112;
                v35 = 61;
                goto LABEL_78;
              }
              if ( v62[0] )
              {
                WpdDevicePathFromAnyPath = (*(__int64 (__fastcall **)(_QWORD, HWND, struct IBindCtx *, unsigned __int16 *, CDeviceFolder **, LPITEMIDLIST *, unsigned int *))(**(_QWORD **)&AliasInterfaceClassGuid.Data1 + 24LL))(
                                             *(_QWORD *)&AliasInterfaceClassGuid.Data1,
                                             v56,
                                             v55,
                                             v62,
                                             &v50,
                                             &v48,
                                             v54);
                if ( WpdDevicePathFromAnyPath < 0 )
                {
                  v34 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
                    goto LABEL_112;
                  v35 = 62;
                  goto LABEL_78;
                }
                WpdDevicePathFromAnyPath = SHILCombine(v44, v48, &v45);
                if ( WpdDevicePathFromAnyPath < 0 )
                {
                  v37 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
                    goto LABEL_96;
                  v38 = 63;
LABEL_95:
                  WPP_SF_d(
                    v37[2],
                    v38,
                    WPP_4da16da3d21a3bea60eae2174f41afdd_Traceguids,
                    (unsigned int)WpdDevicePathFromAnyPath);
LABEL_96:
                  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&AliasInterfaceClassGuid);
                  v39 = v45;
LABEL_126:
                  v12 = &WPP_GLOBAL_Control;
                  goto LABEL_127;
                }
                v39 = v45;
                ChangeNotifyFreeSpace(v45);
              }
              else
              {
                v39 = (ITEMIDLIST *)v44;
                v44 = 0;
              }
            }
            goto LABEL_118;
          }
          v45 = 0;
          v40 = CDeviceFolder::_IsValid(v36, v44);
          if ( v40 && (*((_BYTE *)v40 + 14) & 1) != 0 )
          {
            WpdDevicePathFromAnyPath = -2147467259;
          }
          else
          {
            WpdDevicePathFromAnyPath = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, LPITEMIDLIST *))(**(_QWORD **)&AliasInterfaceClassGuid.Data1 + 32LL))(
                                         *(_QWORD *)&AliasInterfaceClassGuid.Data1,
                                         0,
                                         224,
                                         &v45);
            if ( !WpdDevicePathFromAnyPath )
            {
              while ( !(*(unsigned int (__fastcall **)(LPITEMIDLIST, __int64, LPITEMIDLIST *, int *))(*(_QWORD *)&v45->mkid.cb + 24LL))(
                         v45,
                         1,
                         &pidl,
                         &v49) )
              {
                if ( pidl )
                {
                  ILFree(pidl);
                  pidl = 0;
                }
              }
              v39 = (ITEMIDLIST *)v44;
              v44 = 0;
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v45);
LABEL_118:
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&AliasInterfaceClassGuid);
              v8 = (unsigned int *)v52;
              goto LABEL_119;
            }
          }
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v45);
          goto LABEL_112;
        }
        v8 = (unsigned int *)v52;
      }
      v39 = ILClone(v44);
      WpdDevicePathFromAnyPath = 0;
      if ( !v39 )
      {
        WpdDevicePathFromAnyPath = -2147024882;
        v12 = &WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        {
LABEL_135:
          if ( WpdDevicePathFromAnyPath >= 0 )
          {
            if ( !v54 )
              goto LABEL_120;
            WpdDevicePathFromAnyPath = (*(__int64 (__fastcall **)(CDeviceFolder *, __int64, LPCITEMIDLIST *))(*(_QWORD *)v50 + 72LL))(
                                         v50,
                                         1,
                                         &v44);
            if ( WpdDevicePathFromAnyPath >= 0 )
            {
LABEL_119:
              v12 = &WPP_GLOBAL_Control;
LABEL_120:
              *a6 = v39;
              if ( !v8 )
                goto LABEL_146;
              v52 = 0;
              WpdDevicePathFromAnyPath = StringCchLengthW(a4, 0x7FFFFFFFu, &v52);
              if ( WpdDevicePathFromAnyPath >= 0 )
              {
                *v8 = v52;
                goto LABEL_146;
              }
              v41 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == v12 || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
                goto LABEL_127;
              v42 = 68;
              goto LABEL_125;
            }
            v41 = WPP_GLOBAL_Control;
            v12 = &WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            {
              v42 = 67;
              goto LABEL_125;
            }
          }
          else
          {
            v41 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            {
              v42 = 66;
LABEL_125:
              WPP_SF_d(
                v41[2],
                v42,
                WPP_4da16da3d21a3bea60eae2174f41afdd_Traceguids,
                (unsigned int)WpdDevicePathFromAnyPath);
              goto LABEL_126;
            }
          }
LABEL_127:
          if ( v39 )
          {
            ILFree(v39);
            v12 = &WPP_GLOBAL_Control;
          }
          goto LABEL_146;
        }
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          70,
          &WPP_d7637b305d8b3afba9326780f352c02a_Traceguids,
          2147942414LL);
      }
      v12 = &WPP_GLOBAL_Control;
      goto LABEL_135;
    }
    if ( v13[i] != 92 )
      continue;
    if ( v20 )
      break;
    v20 = 1;
  }
  WpdDevicePathFromAnyPath = StringCchCopyW(v15, 0x820u, &v13[i]);
  if ( WpdDevicePathFromAnyPath >= 0 )
  {
    *v25 = 0;
    goto LABEL_41;
  }
  v22 = WPP_GLOBAL_Control;
  v12 = &WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v23 = 57;
    goto LABEL_21;
  }
LABEL_146:
  if ( pidl )
  {
    ILFree(pidl);
    pidl = 0;
    v12 = &WPP_GLOBAL_Control;
  }
  if ( v44 )
  {
    ILFree((LPITEMIDLIST)v44);
    v44 = 0;
    v12 = &WPP_GLOBAL_Control;
  }
  if ( v48 )
  {
    ILFree(v48);
    v48 = 0;
    v12 = &WPP_GLOBAL_Control;
  }
  if ( v13 )
  {
    CoTaskMemFree(v13);
    v12 = &WPP_GLOBAL_Control;
  }
  if ( v15 )
  {
    CoTaskMemFree(v15);
    v12 = &WPP_GLOBAL_Control;
  }
  v10 = v51;
  if ( WpdDevicePathFromAnyPath < 0 )
  {
LABEL_157:
    if ( WPP_GLOBAL_Control != v12 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        69,
        WPP_4da16da3d21a3bea60eae2174f41afdd_Traceguids,
        (unsigned int)WpdDevicePathFromAnyPath);
      v10 = v51;
    }
  }
  if ( v10 )
    (*(void (__fastcall **)(__int64, unsigned __int64))(*(_QWORD *)v10 + 16LL))(v10, i);
  return (unsigned int)WpdDevicePathFromAnyPath;
}

```

## disassembly

```asm
0x18000d9b0  push    rbp
0x18000d9b2  push    rbx
0x18000d9b3  push    rsi
0x18000d9b4  push    rdi
0x18000d9b5  push    r12
0x18000d9b7  push    r13
0x18000d9b9  push    r14
0x18000d9bb  push    r15
0x18000d9bd  lea     rbp, [rsp-1258h]
0x18000d9c5  mov     eax, 1358h
0x18000d9ca  call    _alloca_probe
0x18000d9cf  sub     rsp, rax
0x18000d9d2  mov     rax, cs:__security_cookie
0x18000d9d9  xor     rax, rsp
0x18000d9dc  mov     [rbp+1290h+var_50], rax
0x18000d9e3  mov     r12, r9
0x18000d9e6  mov     [rbp+1290h+var_12F0], r8
0x18000d9ea  mov     [rbp+1290h+var_12E8], rdx
0x18000d9ee  mov     [rsp+1390h+var_1318], rcx
0x18000d9f3  mov     rdi, [rbp+1290h+arg_20]
0x18000d9fa  mov     [rbp+1290h+var_1308], rdi
0x18000d9fe  mov     r15, [rbp+1290h+arg_28]
0x18000da05  mov     rax, [rbp+1290h+arg_30]
0x18000da0c  mov     [rbp+1290h+var_12F8], rax
0x18000da10  xor     edx, edx
0x18000da12  mov     [rsp+1390h+pidl], rdx
0x18000da17  mov     [rsp+1390h+var_1350], rdx
0x18000da1c  mov     [rsp+1390h+var_1328], rdx
0x18000da21  mov     r14d, edx
0x18000da24  mov     [rsp+1390h+var_1348], rdx
0x18000da29  mov     [rsp+1390h+var_1320], edx
0x18000da2d  xorps   xmm0, xmm0
0x18000da30  xor     eax, eax
0x18000da32  movups  xmmword ptr [rbp+1290h+psz1], xmm0
0x18000da36  movups  [rbp+1290h+var_12D0], xmm0
0x18000da3a  movups  [rbp+1290h+var_12C0], xmm0
0x18000da3e  mov     [rbp+1290h+var_12B0], ax
0x18000da42  mov     ecx, edx
0x18000da44  mov     [rbp+1290h+var_1310], rdx
0x18000da48  test    r9, r9
0x18000da4b  jnz     short loc_18000DA5E
0x18000da4d  mov     ebx, 80070057h
0x18000da52  lea     r10, WPP_GLOBAL_Control
0x18000da59  jmp     loc_18000E466
0x18000da5e  test    r15, r15
0x18000da61  jnz     short loc_18000DA74
0x18000da63  mov     ebx, 80070057h
0x18000da68  lea     r10, WPP_GLOBAL_Control
0x18000da6f  jmp     loc_18000E466
0x18000da74  mov     [r15], rdx
0x18000da77  test    rdi, rdi
0x18000da7a  jz      short loc_18000DA7E
0x18000da7c  mov     [rdi], edx
0x18000da7e  mov     ecx, 1040h; cb
0x18000da83  call    cs:__imp_CoTaskMemAlloc
0x18000da89  mov     rsi, rax
0x18000da8c  mov     ecx, 1040h; cb
0x18000da91  call    cs:__imp_CoTaskMemAlloc
0x18000da97  mov     r13, rax
0x18000da9a  lea     r10, WPP_GLOBAL_Control
0x18000daa1  test    rsi, rsi
0x18000daa4  jz      loc_18000E3CF
0x18000daaa  test    rax, rax
0x18000daad  jz      loc_18000E3CF
0x18000dab3  xor     edx, edx; Val
0x18000dab5  mov     r8d, 1040h; Size
0x18000dabb  mov     rcx, rsi; void *
0x18000dabe  call    memset_0
0x18000dac3  xor     edx, edx; Val
0x18000dac5  mov     r8d, 1040h; Size
0x18000dacb  mov     rcx, r13; void *
0x18000dace  call    memset_0
0x18000dad3  mov     ecx, 7FFFFFFEh
0x18000dad8  mov     rdx, r12
0x18000dadb  mov     r8d, 820h
0x18000dae1  mov     r9, rsi
0x18000dae4  test    rcx, rcx
0x18000dae7  jz      short loc_18000DB06
0x18000dae9  movzx   eax, word ptr [rdx]
0x18000daec  test    ax, ax
0x18000daef  jz      short loc_18000DB06
0x18000daf1  add     rdx, 2
0x18000daf5  mov     [r9], ax
0x18000daf9  add     r9, 2
0x18000dafd  dec     rcx
0x18000db00  sub     r8, 1
0x18000db04  jnz     short loc_18000DAE4
0x18000db06  mov     ebx, 8007007Ah
0x18000db0b  xor     eax, eax
0x18000db0d  test    r8, r8
0x18000db10  cmovnz  ebx, eax
0x18000db13  lea     rcx, [r9-2]
0x18000db17  cmovnz  rcx, r9
0x18000db1b  mov     [rcx], ax
0x18000db1e  jnz     short loc_18000DB65
0x18000db20  mov     rax, cs:WPP_GLOBAL_Control
0x18000db27  lea     r10, WPP_GLOBAL_Control
0x18000db2e  cmp     rax, r10
0x18000db31  jz      loc_18000E3D4
0x18000db37  test    byte ptr [rax+1Ch], 2
0x18000db3b  jz      loc_18000E3D4
0x18000db41  mov     edx, 38h ; '8'
0x18000db46  mov     r9d, ebx
0x18000db49  lea     r8, WPP_4da16da3d21a3bea60eae2174f41afdd_Traceguids
0x18000db50  mov     rcx, [rax+10h]
0x18000db54  call    WPP_SF_d
0x18000db59  lea     r10, WPP_GLOBAL_Control
0x18000db60  jmp     loc_18000E3D4
0x18000db65  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000db6c  nop     dword ptr [rax+00h]
0x18000db70  inc     rcx
0x18000db73  cmp     [rsi+rcx*2], ax
0x18000db77  jnz     short loc_18000DB70
0x18000db79  cmp     rcx, 2
0x18000db7d  jnb     short loc_18000DB90
0x18000db7f  mov     ebx, 80070057h
0x18000db84  lea     r10, WPP_GLOBAL_Control
0x18000db8b  jmp     loc_18000E3D4
0x18000db90  mov     r8d, 5Ch ; '\'
0x18000db96  cmp     r8w, [rsi]
0x18000db9a  jz      short loc_18000DBAD
0x18000db9c  mov     ebx, 80070057h
0x18000dba1  lea     r10, WPP_GLOBAL_Control
0x18000dba8  jmp     loc_18000E3D4
0x18000dbad  cmp     r8w, [rsi+2]
0x18000dbb2  jz      short loc_18000DBC5
0x18000dbb4  mov     ebx, 80070057h
0x18000dbb9  lea     r10, WPP_GLOBAL_Control
0x18000dbc0  jmp     loc_18000E3D4
0x18000dbc5  mov     [r13+0], ax
0x18000dbca  mov     edx, 2
0x18000dbcf  cmp     rdx, rcx
0x18000dbd2  jnb     loc_18000DC9C
0x18000dbd8  lea     r10, [rsi+rdx*2]
0x18000dbdc  cmp     r8w, [r10]
0x18000dbe0  jnz     short loc_18000DBEB
0x18000dbe2  test    eax, eax
0x18000dbe4  jnz     short loc_18000DBF0
0x18000dbe6  mov     eax, 1
0x18000dbeb  inc     rdx
0x18000dbee  jmp     short loc_18000DBCF
0x18000dbf0  mov     r8, r10; unsigned __int16 *
0x18000dbf3  mov     edx, 820h; unsigned __int64
0x18000dbf8  mov     rcx, r13; unsigned __int16 *
0x18000dbfb  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000dc00  mov     ebx, eax
0x18000dc02  test    eax, eax
0x18000dc04  jns     short loc_18000DC31
0x18000dc06  mov     rax, cs:WPP_GLOBAL_Control
0x18000dc0d  lea     r10, WPP_GLOBAL_Control
0x18000dc14  cmp     rax, r10
0x18000dc17  jz      loc_18000E3D4
0x18000dc1d  test    byte ptr [rax+1Ch], 2
0x18000dc21  jz      loc_18000E3D4
0x18000dc27  mov     edx, 39h ; '9'
0x18000dc2c  jmp     loc_18000DB46
0x18000dc31  xor     eax, eax
0x18000dc33  mov     [r10], ax
0x18000dc37  mov     rcx, [rsp+1390h+var_1318]
0x18000dc3c  mov     rax, [rcx]
0x18000dc3f  lea     r9, [rbp+1290h+var_1310]
0x18000dc43  xor     edx, edx
0x18000dc45  mov     r8d, 0E0h
0x18000dc4b  mov     rax, [rax+20h]
0x18000dc4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc54  mov     ebx, eax
0x18000dc56  test    eax, eax
0x18000dc58  jnz     loc_18000DD2B
0x18000dc5e  mov     rcx, [rbp+1290h+var_1310]
0x18000dc62  mov     rax, [rcx]
0x18000dc65  lea     r9, [rsp+1390h+var_1320]
0x18000dc6a  lea     r8, [rsp+1390h+pidl]
0x18000dc6f  mov     edx, 1
0x18000dc74  mov     rax, [rax+18h]
0x18000dc78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc7d  test    eax, eax
0x18000dc7f  jnz     short loc_18000DCAA
0x18000dc81  mov     rcx, [rsp+1390h+pidl]; pidl
0x18000dc86  test    rcx, rcx
0x18000dc89  jz      short loc_18000DC5E
0x18000dc8b  call    cs:__imp_ILFree
0x18000dc91  mov     [rsp+1390h+pidl], 0
0x18000dc9a  jmp     short loc_18000DC5E
0x18000dc9c  test    eax, eax
0x18000dc9e  jnz     short loc_18000DC37
0x18000dca0  mov     ebx, 80070057h
0x18000dca5  jmp     loc_18000DD2B
0x18000dcaa  movups  xmm0, xmmword ptr cs:GUID_DEVINTERFACE_WPD.Data1
0x18000dcb1  movaps  xmmword ptr [rsp+1390h+AliasInterfaceClassGuid.Data1], xmm0
0x18000dcb6  lea     r8, [rbp+1290h+var_12A0]; unsigned __int16 *
0x18000dcba  mov     rdx, rsi; DevicePath
0x18000dcbd  lea     rcx, [rsp+1390h+AliasInterfaceClassGuid]; AliasInterfaceClassGuid
0x18000dcc2  call    ?GetWpdDevicePathFromAnyPath@@YAJU_GUID@@PEBGPEAGI@Z; GetWpdDevicePathFromAnyPath(_GUID,ushort const *,ushort *,uint)
0x18000dcc7  test    eax, eax
0x18000dcc9  jns     short loc_18000DD37
0x18000dccb  movups  xmm0, xmmword ptr cs:GUID_DEVINTERFACE_WPD_PRIVATE.Data1
0x18000dcd2  movaps  xmmword ptr [rsp+1390h+AliasInterfaceClassGuid.Data1], xmm0
0x18000dcd7  lea     r8, [rbp+1290h+var_12A0]; unsigned __int16 *
0x18000dcdb  mov     rdx, rsi; DevicePath
0x18000dcde  lea     rcx, [rsp+1390h+AliasInterfaceClassGuid]; AliasInterfaceClassGuid
0x18000dce3  call    ?GetWpdDevicePathFromAnyPath@@YAJU_GUID@@PEBGPEAGI@Z; GetWpdDevicePathFromAnyPath(_GUID,ushort const *,ushort *,uint)
0x18000dce8  mov     ebx, eax
0x18000dcea  test    eax, eax
0x18000dcec  jns     short loc_18000DD37
0x18000dcee  mov     rax, cs:WPP_GLOBAL_Control
0x18000dcf5  lea     r10, WPP_GLOBAL_Control
0x18000dcfc  cmp     rax, r10
0x18000dcff  jz      loc_18000E3D4
0x18000dd05  test    byte ptr [rax+1Ch], 2
0x18000dd09  jz      loc_18000E3D4
0x18000dd0f  mov     edx, 3Ah ; ':'
0x18000dd14  mov     [rsp+1390h+var_1370], ebx
0x18000dd18  mov     r9, rsi
0x18000dd1b  lea     r8, WPP_4da16da3d21a3bea60eae2174f41afdd_Traceguids
0x18000dd22  mov     rcx, [rax+10h]
0x18000dd26  call    WPP_SF_Sd
0x18000dd2b  lea     r10, WPP_GLOBAL_Control
0x18000dd32  jmp     loc_18000E3D4
0x18000dd37  lea     rcx, ?g_csDeviceCache@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000dd3e  call    cs:__imp_EnterCriticalSection
0x18000dd44  cmp     cs:?g_pDeviceCache@@3PEAVCDeviceCache@@EA, 0; CDeviceCache * g_pDeviceCache
0x18000dd4c  jnz     short loc_18000DD65
0x18000dd4e  mov     ebx, 8000FFFFh
0x18000dd53  lea     rcx, ?g_csDeviceCache@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000dd5a  call    cs:__imp_LeaveCriticalSection
0x18000dd60  jmp     loc_18000DE03
0x18000dd65  mov     [rsp+1390h+var_1350], 0
0x18000dd6e  lea     rdx, [rbp+1290h+var_12A0]; unsigned __int16 *
0x18000dd72  call    ?_FindItem@CDeviceCache@@AEAAPEAUDEVITEM_CACHE@@PEBG@Z; CDeviceCache::_FindItem(ushort const *)
0x18000dd77  test    rax, rax
0x18000dd7a  jnz     short loc_18000DD90
0x18000dd7c  mov     ebx, 80004005h
0x18000dd81  lea     rcx, ?g_csDeviceCache@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000dd88  call    cs:__imp_LeaveCriticalSection
0x18000dd8e  jmp     short loc_18000DE03
0x18000dd90  mov     rcx, [rax+18h]
0x18000dd94  test    rcx, rcx
0x18000dd97  jz      short loc_18000DD4E
0x18000dd99  xor     edx, edx
0x18000dd9b  call    IsolationAwareDPA_GetPtr
0x18000dda0  mov     rcx, rax; pidl
0x18000dda3  call    cs:__imp_ILFindLastID
0x18000dda9  mov     rcx, rax
0x18000ddac  lea     rdx, [rsp+1390h+var_1350]
0x18000ddb1  call    SHILCloneFirst
0x18000ddb6  mov     ebx, eax
0x18000ddb8  test    eax, eax
0x18000ddba  jns     short loc_18000DDF2
0x18000ddbc  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ddc3  lea     rax, WPP_GLOBAL_Control
0x18000ddca  cmp     rcx, rax
0x18000ddcd  jz      short loc_18000DDF2
0x18000ddcf  test    byte ptr [rcx+1Ch], 2
0x18000ddd3  jz      short loc_18000DDF2
0x18000ddd5  mov     edx, 2Fh ; '/'
0x18000ddda  mov     r9d, ebx
0x18000dddd  lea     r8, WPP_97b3e7d056e530596454d4c68ce08f99_Traceguids
0x18000dde4  mov     rcx, [rcx+10h]
0x18000dde8  call    WPP_SF_d
0x18000dded  jmp     loc_18000DD53
0x18000ddf2  lea     rcx, ?g_csDeviceCache@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000ddf9  call    cs:__imp_LeaveCriticalSection
0x18000ddff  test    ebx, ebx
0x18000de01  jns     short loc_18000DE5F
0x18000de03  mov     rax, cs:WPP_GLOBAL_Control
0x18000de0a  lea     r10, WPP_GLOBAL_Control
0x18000de11  cmp     rax, r10
0x18000de14  jz      short loc_18000DE3B
0x18000de16  test    byte ptr [rax+1Ch], 2
0x18000de1a  jz      short loc_18000DE3B
0x18000de1c  mov     edx, 30h ; '0'
0x18000de21  mov     r9d, ebx
0x18000de24  lea     r8, WPP_97b3e7d056e530596454d4c68ce08f99_Traceguids
0x18000de2b  mov     rcx, [rax+10h]
0x18000de2f  call    WPP_SF_d
0x18000de34  lea     r10, WPP_GLOBAL_Control
0x18000de3b  mov     rax, cs:WPP_GLOBAL_Control
0x18000de42  cmp     rax, r10
0x18000de45  jz      loc_18000E3D4
0x18000de4b  test    byte ptr [rax+1Ch], 2
0x18000de4f  jz      loc_18000E3D4
0x18000de55  mov     edx, 3Bh ; ';'
0x18000de5a  jmp     loc_18000DB46
0x18000de5f  cmp     [rsp+1390h+var_1350], 0
0x18000de65  jnz     short loc_18000DE71
0x18000de67  mov     ebx, 80004005h
0x18000de6c  jmp     loc_18000DD2B
0x18000de71  cmp     word ptr [r13+0], 0
0x18000de77  jz      loc_18000E2E2
0x18000de7d  cmp     word ptr [r13+2], 0
0x18000de83  jz      loc_18000E2DE
0x18000de89  mov     [rbp+1290h+var_1300], 0
0x18000de90  mov     qword ptr [rsp+1390h+AliasInterfaceClassGuid.Data1], 0
0x18000de99  mov     r14, [rsp+1390h+var_1318]
0x18000de9e  mov     rax, [r14]
0x18000dea1  lea     rcx, [rsp+1390h+AliasInterfaceClassGuid]
0x18000dea6  mov     qword ptr [rsp+1390h+var_1370], rcx
0x18000deab  lea     r9, _GUID_000214e6_0000_0000_c000_000000000046
0x18000deb2  xor     r8d, r8d
0x18000deb5  mov     rdx, [rsp+1390h+var_1350]
  ... truncated ...
```
