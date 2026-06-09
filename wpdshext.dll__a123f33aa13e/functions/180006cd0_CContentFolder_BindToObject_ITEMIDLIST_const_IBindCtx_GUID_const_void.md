# CContentFolder::BindToObject(_ITEMIDLIST const *,IBindCtx *,_GUID const &,void * *)

- ea: `0x180006cd0`
- end: `0x18000784c`
- name: `?BindToObject@CContentFolder@@UEAAJPEFBU_ITEMIDLIST@@PEAUIBindCtx@@AEBU_GUID@@PEAPEAX@Z`
- size: `2940`
- prototype: `int(CContentFolder *__hidden this, const struct _ITEMIDLIST *, struct IBindCtx *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180005b90`
- `0x180006cd0`
- `0x1800082e0`
- `0x18002eb48`
- `0x18002ff5c`
- `0x180035590`
- `0x1800361ba`
- `0x18003912c`
- `0x180039e80`
- `0x180045cdc`
- `0x1800755a8`
- `0x180078010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x180006de4`
- `KERNEL32!HeapAlloc` at `0x180006de4`
- `KERNEL32!GetProcessHeap` at `0x180006dd0`
- `KERNEL32!GetProcessHeap` at `0x180006dd0`
- `KERNEL32!EnterCriticalSection` at `0x180006e7c`
- `KERNEL32!EnterCriticalSection` at `0x180006e7c`
- `KERNEL32!LeaveCriticalSection` at `0x180006e90`
- `KERNEL32!LeaveCriticalSection` at `0x180006e90`
- `ole32!CoTaskMemAlloc` at `0x180006d8d`
- `ole32!CoTaskMemAlloc` at `0x180006d8d`
- `SHELL32!__imp_ILGetSize` at `0x180006d67`
- `SHELL32!__imp_ILGetSize` at `0x180006d67`
- `SHELL32!__imp_ILFree` at `0x180007249`
- `SHELL32!__imp_ILFree` at `0x180007249`

## string_xrefs

- `0x180006f95`: `prop:System.Size;System.DateModified;System.DateCreated`
- `0x180006f85`: `prop:System.Size;System.DateModified;System.DateCreated`
- `0x1800072a8`: `prop:System.Size;System.DateModified;System.DateCreated`
- `0x180007460`: `prop:System.Size;System.DateModified;System.DateCreated`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CContentFolder::BindToObject(
        void **this,
        const struct _ITEMIDLIST *a2,
        struct IBindCtx *a3,
        struct _GUID *a4,
        struct IPropertySetStorage **a5)
{
  const struct CONTENTITEM *v9; // rax
  const struct CONTENTITEM *v10; // rbx
  _WORD *v11; // r12
  UINT v12; // ebx
  UINT v13; // eax
  ITEMIDLIST *v14; // rax
  ITEMIDLIST *v15; // rbp
  size_t v16; // rbx
  HANDLE ProcessHeap; // rax
  _QWORD *v18; // rax
  _QWORD *v19; // rbx
  void **v20; // r13
  struct CONTENTITEM *v21; // r14
  int v22; // esi
  __int64 v23; // rcx
  int v24; // eax
  int v25; // eax
  int v26; // eax
  const wchar_t *v27; // rax
  __int64 *v28; // rcx
  int v29; // esi
  struct IBindCtx *v30; // rsi
  __int64 v31; // rax
  __int64 v32; // rax
  __int64 v33; // rax
  __int64 v34; // rax
  unsigned int v35; // eax
  int v36; // edx
  __int64 v37; // rax
  __int64 v38; // rax
  __int64 v39; // rax
  int v40; // eax
  unsigned int v41; // ebx
  PVOID *v42; // rcx
  __int64 result; // rax
  unsigned int v44; // edi
  int Mode; // eax
  PVOID *v46; // rcx
  __int64 v47; // rdx
  int v48; // eax
  int v49; // edi
  unsigned int v50; // r12d
  int v51; // eax
  __int64 v52; // rdx
  __int64 v53; // rax
  __int64 v54; // r9
  __int64 v55; // r9
  struct IBindCtx *v56; // [rsp+30h] [rbp-108h] BYREF
  void **v57; // [rsp+38h] [rbp-100h] BYREF
  struct CONTENTITEM *v58; // [rsp+40h] [rbp-F8h]
  void *Src; // [rsp+48h] [rbp-F0h]
  CContentFolder *v60; // [rsp+50h] [rbp-E8h]
  OLECHAR sz[64]; // [rsp+60h] [rbp-D8h] BYREF

  v56 = a3;
  v57 = this;
  if ( !a2 )
  {
    v29 = -2147024809;
    goto LABEL_77;
  }
  if ( !a5 )
  {
    v29 = -2147467261;
    goto LABEL_77;
  }
  *a5 = 0;
  v9 = CContentFolder::_IsValid((CContentFolder *)this, a2);
  v10 = v9;
  v58 = v9;
  if ( !v9 )
  {
    v29 = -2147467259;
    goto LABEL_77;
  }
  if ( (*((_BYTE *)v9 + 10) & 2) != 0 )
  {
    v11 = (USHORT *)((char *)&a2->mkid.cb + a2->mkid.cb);
    v60 = (CContentFolder *)(this - 2);
    Src = this[6];
    v12 = ILGetSize((LPCITEMIDLIST)Src);
    v13 = (_DWORD)v11 - (_DWORD)a2 + v12;
    if ( v12 > v13 )
    {
      v29 = -2147418113;
    }
    else if ( v13 )
    {
      v14 = (ITEMIDLIST *)CoTaskMemAlloc(v13);
      v15 = v14;
      if ( v14 )
      {
        memset_0(v14, 0, (_DWORD)v11 - (_DWORD)a2 + v12);
        v16 = v12 - 2;
        memcpy_0(v15, Src, v16);
        memcpy_0((char *)v15 + v16, a2, (unsigned int)((_DWORD)v11 - (_DWORD)a2));
        ProcessHeap = GetProcessHeap();
        v18 = HeapAlloc(ProcessHeap, 8u, 0xB0u);
        v19 = v18;
        Src = v18;
        v20 = v57;
        v21 = v58;
        if ( v18 )
        {
          v22 = *((_DWORD *)v57 + 33);
          LODWORD(v58) = *(_DWORD *)((char *)v58 + 10);
          *v18 = &CBaseFolder::`vftable'{for `IDelegateFolder'};
          v18[1] = &CBaseFolder::`vftable'{for `IPersistFolder2'};
          v18[2] = &CBaseFolder::`vftable'{for `IShellFolder2'};
          v18[3] = &CBaseFolder::`vftable'{for `IExplorerPaneVisibility'};
          v18[4] = &CBaseFolder::`vftable'{for `IItemNameLimits'};
          *((_DWORD *)v18 + 10) = 1;
          *(GUID *)((char *)v18 + 44) = CLSID_ContentFolder;
          v18[8] = 0;
          v18[9] = v20 - 2;
          *((_DWORD *)v18 + 20) = 0;
          v18[11] = 0;
          v18[12] = 0;
          EnterCriticalSection(&g_csDllRef);
          _InterlockedIncrement(&g_cRefThisDll);
          LeaveCriticalSection(&g_csDllRef);
          v23 = v19[9];
          if ( v23 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 8LL))(v23);
          *v19 = &CContentFolder::`vftable'{for `IDelegateFolder'};
          v19[1] = &CContentFolder::`vftable'{for `IPersistFolder2'};
          v19[2] = &CContentFolder::`vftable'{for `IShellFolder2'};
          v19[3] = &CContentFolder::`vftable'{for `IExplorerPaneVisibility'};
          v19[4] = &CContentFolder::`vftable'{for `IItemNameLimits'};
          v19[13] = &CContentFolder::`vftable'{for `IShellFolderViewCB'};
          v19[14] = &CContentFolder::`vftable'{for `IFolderViewSettings'};
          v19[15] = &CContentFolder::`vftable'{for `IShellIconOverlay'};
          v19[16] = &CContentFolder::`vftable'{for `IStorage'};
          v19[17] = &CContentFolder::`vftable'{for `IUpdateIDList'};
          *((_DWORD *)v19 + 36) = 0;
          *((_DWORD *)v19 + 37) = v22;
          *((_DWORD *)v19 + 38) = 0;
          *((_DWORD *)v19 + 39) = (_DWORD)v58;
          v19[20] = 0;
          v24 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD *))(*(_QWORD *)v19[9] + 152LL))(
                  v19[9],
                  v19[8],
                  v19 + 19);
          if ( v24 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              33,
              WPP_f4dfe53786183352449e3e96734e584d_Traceguids,
              (unsigned int)v24);
          v25 = *((_DWORD *)v19 + 38);
          *((_DWORD *)v19 + 20) = 16;
          if ( v25 == 3 )
          {
            v27 = L"prop:System.Size;System.DateModified;System.DateCreated";
            v28 = qword_180079330;
          }
          else
          {
            v26 = v25 - 1;
            if ( v26 )
            {
              if ( v26 == 1 )
              {
                v27 = L"prop:System.Size;System.DateModified;System.DateCreated";
                v28 = qword_1800797B0;
              }
              else
              {
                v27 = L"prop:System.Size;System.DateModified;System.DateCreated";
                v28 = qword_180079630;
              }
            }
            else
            {
              v27 = L"prop:System.Size;System.DateModified;System.DateCreated";
              v28 = qword_1800794B0;
            }
          }
          v19[11] = v28;
          v19[21] = v27;
        }
        else
        {
          v19 = 0;
        }
        if ( !v19 )
        {
          v29 = -2147024882;
          goto LABEL_64;
        }
        v29 = (*(__int64 (__fastcall **)(_QWORD *, ITEMIDLIST *))(v19[1] + 32LL))(v19 + 1, v15);
        if ( v29 < 0 )
        {
          v46 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
            goto LABEL_64;
          v47 = 16;
        }
        else
        {
          if ( v11 && *v11 )
          {
            v29 = (*(__int64 (__fastcall **)(_QWORD *, _WORD *, struct IBindCtx *, struct _GUID *, struct IPropertySetStorage **))(v19[2] + 40LL))(
                    v19 + 2,
                    v11,
                    v56,
                    a4,
                    a5);
            if ( v29 >= 0 || WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
              goto LABEL_64;
            v35 = (unsigned int)CGuidToString::CGuidToString(sz, a4);
            v36 = 22;
LABEL_38:
            WPP_SF_Sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v36,
              (unsigned int)WPP_953c7f1870f230da5c3777fec273291e_Traceguids,
              v35,
              v29);
LABEL_64:
            ILFree(v15);
            v42 = (PVOID *)WPP_GLOBAL_Control;
            goto LABEL_65;
          }
          v57 = 0;
          v30 = v56;
          if ( v56
            && ((int (__fastcall *)(struct IBindCtx *, const wchar_t *, void ***))v56->lpVtbl->GetObjectParam)(
                 v56,
                 L"WPDNSE Fast Enum",
                 &v57) >= 0 )
          {
            (*((void (__fastcall **)(void **))*v57 + 2))(v57);
            *((_DWORD *)v19 + 37) = 1;
          }
          v31 = *(_QWORD *)&a4->Data1 - *(_QWORD *)&IID_IStream.Data1;
          if ( *(_QWORD *)&a4->Data1 == *(_QWORD *)&IID_IStream.Data1 )
            v31 = *(_QWORD *)a4->Data4 - *(_QWORD *)IID_IStream.Data4;
          if ( v31 )
          {
            v32 = *(_QWORD *)&a4->Data1 - *(_QWORD *)&IID_IPortableDevice.Data1;
            if ( *(_QWORD *)&a4->Data1 == *(_QWORD *)&IID_IPortableDevice.Data1 )
              v32 = *(_QWORD *)a4->Data4 - *(_QWORD *)IID_IPortableDevice.Data4;
            if ( v32 )
            {
              v33 = *(_QWORD *)&a4->Data1 - *(_QWORD *)&IID_IPropertyStore.Data1;
              if ( *(_QWORD *)&a4->Data1 == *(_QWORD *)&IID_IPropertyStore.Data1 )
                v33 = *(_QWORD *)a4->Data4 - *(_QWORD *)IID_IPropertyStore.Data4;
              if ( v33 )
              {
                v34 = *(_QWORD *)&a4->Data1 - *(_QWORD *)&IID_IPropertySetStorage.Data1;
                if ( *(_QWORD *)&a4->Data1 == *(_QWORD *)&IID_IPropertySetStorage.Data1 )
                  v34 = *(_QWORD *)a4->Data4 - *(_QWORD *)IID_IPropertySetStorage.Data4;
                if ( v34 )
                {
                  v29 = (*(__int64 (__fastcall **)(_QWORD *, struct _GUID *, struct IPropertySetStorage **))*v19)(
                          v19,
                          a4,
                          a5);
                  if ( v29 >= 0
                    || WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
                  {
                    goto LABEL_64;
                  }
                  v35 = (unsigned int)CGuidToString::CGuidToString(sz, a4);
                  v36 = 21;
                  goto LABEL_38;
                }
                v29 = CContentFolder::_BindToPropertySetStorage((CContentFolder *)(v20 - 2), v21, a5);
                if ( v29 >= 0 )
                  goto LABEL_64;
                v46 = (PVOID *)WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
                  goto LABEL_64;
                v47 = 20;
                goto LABEL_120;
              }
              v48 = (*((__int64 (__fastcall **)(void **, struct CONTENTITEM *, struct IPropertySetStorage **, __int64))*(v20 - 2)
                     + 4))(
                      v20 - 2,
                      v21,
                      a5,
                      1);
              v49 = v48;
              if ( v48 < 0 )
              {
                v46 = (PVOID *)WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
                {
                  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                  {
                    WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      278,
                      WPP_953c7f1870f230da5c3777fec273291e_Traceguids,
                      (unsigned int)v48);
                    v46 = (PVOID *)WPP_GLOBAL_Control;
                  }
                  if ( v46 != &WPP_GLOBAL_Control && (*((_BYTE *)v46 + 28) & 2) != 0 )
                  {
                    WPP_SF_d(v46[2], 279, WPP_953c7f1870f230da5c3777fec273291e_Traceguids, (unsigned int)v49);
                    v29 = v49;
                    v46 = (PVOID *)WPP_GLOBAL_Control;
LABEL_132:
                    if ( v46 == &WPP_GLOBAL_Control || (*((_BYTE *)v46 + 28) & 2) == 0 )
                      goto LABEL_64;
                    v47 = 19;
                    v55 = (unsigned int)v49;
                    goto LABEL_121;
                  }
                }
              }
              else
              {
                v46 = (PVOID *)WPP_GLOBAL_Control;
              }
              v29 = v49;
              if ( v49 >= 0 )
                goto LABEL_64;
              goto LABEL_132;
            }
            v29 = (*((__int64 (__fastcall **)(void **, void *, struct IPropertySetStorage **))*(v20 - 2) + 17))(
                    v20 - 2,
                    v20[6],
                    a5);
            if ( v29 >= 0 )
              goto LABEL_64;
            v46 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
              goto LABEL_64;
            v47 = 18;
          }
          else
          {
            v44 = 0;
            v56 = 0;
            if ( v30
              && ((int (__fastcall *)(struct IBindCtx *, const wchar_t *, struct IBindCtx **))v30->lpVtbl->GetObjectParam)(
                   v30,
                   L"WPDNSE Assume Virtual File",
                   &v56) >= 0 )
            {
              v44 = 1;
              ((void (__fastcall *)(struct IBindCtx *))v56->lpVtbl->Release)(v56);
            }
            Mode = BindCtx_GetMode(v30);
            v29 = CContentFolder::_BindToStream(v60, v21, Mode, v44, (struct IStream **)a5);
            if ( v29 >= 0 )
              goto LABEL_64;
            v46 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
              goto LABEL_64;
            v47 = 17;
          }
        }
LABEL_120:
        v55 = (unsigned int)v29;
LABEL_121:
        WPP_SF_d(v46[2], v47, WPP_953c7f1870f230da5c3777fec273291e_Traceguids, v55);
        goto LABEL_64;
      }
      v29 = -2147024882;
    }
    else
    {
      v29 = -2147024809;
    }
    v19 = 0;
    v42 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          15,
          &WPP_d7637b305d8b3afba9326780f352c02a_Traceguids,
          (unsigned int)v29);
        v42 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v42 != &WPP_GLOBAL_Control && (*((_BYTE *)v42 + 28) & 2) != 0 )
      {
        WPP_SF_d(v42[2], 15, WPP_953c7f1870f230da5c3777fec273291e_Traceguids, (unsigned int)v29);
        v42 = (PVOID *)WPP_GLOBAL_Control;
      }
    }
LABEL_65:
    if ( v19 )
    {
      (*(void (__fastcall **)(_QWORD *))(*v19 + 16LL))(v19);
      v42 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v29 >= 0 )
      return (unsigned int)v29;
    goto LABEL_78;
  }
  v37 = *(_QWORD *)&a4->Data1 - *(_QWORD *)&IID_IStream.Data1;
  if ( *(_QWORD *)&a4->Data1 == *(_QWORD *)&IID_IStream.Data1 )
    v37 = *(_QWORD *)a4->Data4 - *(_QWORD *)IID_IStream.Data4;
  if ( !v37 )
  {
    v50 = 0;
    v56 = 0;
    if ( a3
      && ((int (__fastcall *)(struct IBindCtx *, const wchar_t *, struct IBindCtx **))a3->lpVtbl->GetObjectParam)(
           a3,
           L"WPDNSE Assume Virtual File",
           &v56) >= 0 )
    {
      v50 = 1;
      ((void (__fastcall *)(struct IBindCtx *))v56->lpVtbl->Release)(v56);
    }
    v51 = BindCtx_GetMode(a3);
    result = CContentFolder::_BindToStream((CContentFolder *)(this - 2), v10, v51, v50, (struct IStream **)a5);
    v29 = result;
    if ( (int)result >= 0 )
      return result;
    v42 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return (unsigned int)v29;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_78;
    v52 = 23;
LABEL_105:
    v54 = (unsigned int)result;
    goto LABEL_141;
  }
  v38 = *(_QWORD *)&a4->Data1 - *(_QWORD *)&IID_IPortableDevice.Data1;
  if ( *(_QWORD *)&a4->Data1 == *(_QWORD *)&IID_IPortableDevice.Data1 )
    v38 = *(_QWORD *)a4->Data4 - *(_QWORD *)IID_IPortableDevice.Data4;
  if ( !v38 )
  {
    result = (*((__int64 (__fastcall **)(char *, void *, struct IPropertySetStorage **))*(this - 2) + 17))(
               (char *)this - 16,
               this[6],
               a5);
    v29 = result;
    if ( (int)result >= 0 )
      return result;
    v42 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return (unsigned int)v29;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_78;
    v52 = 24;
    goto LABEL_105;
  }
  v39 = *(_QWORD *)&a4->Data1 - *(_QWORD *)&IID_IPropertyStore.Data1;
  if ( *(_QWORD *)&a4->Data1 == *(_QWORD *)&IID_IPropertyStore.Data1 )
    v39 = *(_QWORD *)a4->Data4 - *(_QWORD *)IID_IPropertyStore.Data4;
  if ( !v39 )
  {
    v40 = (*((__int64 (__fastcall **)(char *, const struct CONTENTITEM *, struct IPropertySetStorage **, __int64))*(this - 2)
           + 4))(
            (char *)this - 16,
            v10,
            a5,
            1);
    v41 = v40;
    if ( v40 < 0 )
    {
      v42 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            278,
            WPP_953c7f1870f230da5c3777fec273291e_Traceguids,
            (unsigned int)v40);
          v42 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v42 != &WPP_GLOBAL_Control && (*((_BYTE *)v42 + 28) & 2) != 0 )
        {
          WPP_SF_d(v42[2], 279, WPP_953c7f1870f230da5c3777fec273291e_Traceguids, v41);
          v29 = v41;
          v42 = (PVOID *)WPP_GLOBAL_Control;
          goto LABEL_148;
        }
      }
    }
    else
    {
      v42 = (PVOID *)WPP_GLOBAL_Control;
    }
    v29 = v41;
    if ( (v41 & 0x80000000) == 0 )
      return v41;
LABEL_148:
    if ( v42 != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)v42 + 28) & 2) == 0 )
      {
LABEL_78:
        if ( v42 != &WPP_GLOBAL_Control && (*((_BYTE *)v42 + 28) & 2) != 0 )
          WPP_SF_d(v42[2], 27, WPP_953c7f1870f230da5c3777fec273291e_Traceguids, (unsigned int)v29);
        return (unsigned int)v29;
      }
      v52 = 25;
      v54 = v41;
LABEL_141:
      WPP_SF_d(v42[2], v52, WPP_953c7f1870f230da5c3777fec273291e_Traceguids, v54);
      v42 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_78;
    }
    return (unsigned int)v29;
  }
  v29 = -2147467262;
  v53 = *(_QWORD *)&a4->Data1 - *(_QWORD *)&IID_IPropertySetStorage.Data1;
  if ( *(_QWORD *)&a4->Data1 == *(_QWORD *)&IID_IPropertySetStorage.Data1 )
    v53 = *(_QWORD *)a4->Data4 - *(_QWORD *)IID_IPropertySetStorage.Data4;
  if ( v53 )
  {
LABEL_77:
    v42 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_78;
  }
  result = CContentFolder::_BindToPropertySetStorage((CContentFolder *)(this - 2), v10, a5);
  v29 = result;
  if ( (int)result < 0 )
  {
    v42 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return (unsigned int)v29;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_78;
    v52 = 26;
    goto LABEL_105;
  }
  return result;
}

```

## disassembly

```asm
0x180006cd0  push    rbx
0x180006cd2  push    rbp
0x180006cd3  push    rsi
0x180006cd4  push    rdi
0x180006cd5  push    r12
0x180006cd7  push    r13
0x180006cd9  push    r14
0x180006cdb  push    r15
0x180006cdd  sub     rsp, 0F8h
0x180006ce4  mov     rax, cs:__security_cookie
0x180006ceb  xor     rax, rsp
0x180006cee  mov     [rsp+138h+var_58], rax
0x180006cf6  mov     rdi, r9
0x180006cf9  mov     r14, r8
0x180006cfc  mov     [rsp+138h+var_108], r8
0x180006d01  mov     rsi, rdx
0x180006d04  mov     r13, rcx
0x180006d07  mov     [rsp+138h+var_100], rcx
0x180006d0c  mov     r15, [rsp+138h+arg_20]
0x180006d14  test    rdx, rdx
0x180006d17  jz      loc_1800075AD
0x180006d1d  test    r15, r15
0x180006d20  jz      loc_1800075B7
0x180006d26  xor     ebp, ebp
0x180006d28  mov     [r15], rbp
0x180006d2b  call    ?_IsValid@CContentFolder@@QEAAPEFBUCONTENTITEM@@PEFBU_ITEMIDLIST@@@Z; CContentFolder::_IsValid(_ITEMIDLIST const *)
0x180006d30  mov     rbx, rax
0x180006d33  mov     [rsp+138h+var_F8], rax
0x180006d38  test    rax, rax
0x180006d3b  jz      loc_1800075C1
0x180006d41  test    byte ptr [rax+0Ah], 2
0x180006d45  jz      loc_1800070F6
0x180006d4b  movzx   r12d, word ptr [rsi]
0x180006d4f  add     r12, rsi
0x180006d52  lea     rax, [r13-10h]
0x180006d56  mov     [rsp+138h+var_E8], rax
0x180006d5b  mov     rax, [rax+40h]
0x180006d5f  mov     [rsp+138h+Src], rax
0x180006d64  mov     rcx, rax; pidl
0x180006d67  call    cs:__imp_ILGetSize
0x180006d6d  mov     ebx, eax
0x180006d6f  mov     r14d, r12d
0x180006d72  sub     r14d, esi
0x180006d75  add     eax, r14d
0x180006d78  cmp     ebx, eax
0x180006d7a  ja      loc_1800072BB
0x180006d80  test    eax, eax
0x180006d82  jz      loc_18000730E
0x180006d88  mov     r13d, eax
0x180006d8b  mov     ecx, eax; cb
0x180006d8d  call    cs:__imp_CoTaskMemAlloc
0x180006d93  mov     rbp, rax
0x180006d96  test    rax, rax
0x180006d99  jz      loc_1800075CB
0x180006d9f  mov     r8d, r13d; Size
0x180006da2  xor     edx, edx; Val
0x180006da4  mov     rcx, rax; void *
0x180006da7  call    memset_0
0x180006dac  lea     eax, [rbx-2]
0x180006daf  mov     ebx, eax
0x180006db1  mov     r8d, eax; Size
0x180006db4  mov     rdx, [rsp+138h+Src]; Src
0x180006db9  mov     rcx, rbp; void *
0x180006dbc  call    memcpy_0
0x180006dc1  mov     r8d, r14d; Size
0x180006dc4  lea     rcx, [rbx+rbp]; void *
0x180006dc8  mov     rdx, rsi; Src
0x180006dcb  call    memcpy_0
0x180006dd0  call    cs:__imp_GetProcessHeap
0x180006dd6  mov     rcx, rax; hHeap
0x180006dd9  mov     edx, 8; dwFlags
0x180006dde  mov     r8d, 0B0h; dwBytes
0x180006de4  call    cs:__imp_HeapAlloc
0x180006dea  mov     rbx, rax
0x180006ded  mov     [rsp+138h+Src], rax
0x180006df2  mov     r13, [rsp+138h+var_100]
0x180006df7  mov     r14, [rsp+138h+var_F8]
0x180006dfc  test    rax, rax
0x180006dff  jz      loc_1800074BF
0x180006e05  mov     esi, [r13+84h]
0x180006e0c  mov     eax, [r14+0Ah]
0x180006e10  mov     dword ptr [rsp+138h+var_F8], eax
0x180006e14  lea     rcx, ??_7CBaseFolder@@6BIDelegateFolder@@@; const CBaseFolder::`vftable'{for `IDelegateFolder'}
0x180006e1b  mov     [rbx], rcx
0x180006e1e  lea     rax, ??_7CBaseFolder@@6BIPersistFolder2@@@; const CBaseFolder::`vftable'{for `IPersistFolder2'}
0x180006e25  mov     [rbx+8], rax
0x180006e29  lea     rax, ??_7CBaseFolder@@6BIShellFolder2@@@; const CBaseFolder::`vftable'{for `IShellFolder2'}
0x180006e30  mov     [rbx+10h], rax
0x180006e34  lea     rax, ??_7CBaseFolder@@6BIExplorerPaneVisibility@@@; const CBaseFolder::`vftable'{for `IExplorerPaneVisibility'}
0x180006e3b  mov     [rbx+18h], rax
0x180006e3f  lea     rax, ??_7CBaseFolder@@6BIItemNameLimits@@@; const CBaseFolder::`vftable'{for `IItemNameLimits'}
0x180006e46  mov     [rbx+20h], rax
0x180006e4a  mov     dword ptr [rbx+28h], 1
0x180006e51  movups  xmm0, xmmword ptr cs:CLSID_ContentFolder.Data1
0x180006e58  movups  xmmword ptr [rbx+2Ch], xmm0
0x180006e5c  xor     ecx, ecx
0x180006e5e  mov     [rbx+40h], rcx
0x180006e62  lea     rax, [r13-10h]
0x180006e66  mov     [rbx+48h], rax
0x180006e6a  mov     [rbx+50h], ecx
0x180006e6d  mov     [rbx+58h], rcx
0x180006e71  mov     [rbx+60h], rcx
0x180006e75  lea     rcx, ?g_csDllRef@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180006e7c  call    cs:__imp_EnterCriticalSection
0x180006e82  lock inc cs:?g_cRefThisDll@@3JA; long g_cRefThisDll
0x180006e89  lea     rcx, ?g_csDllRef@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180006e90  call    cs:__imp_LeaveCriticalSection
0x180006e96  mov     rcx, [rbx+48h]
0x180006e9a  test    rcx, rcx
0x180006e9d  jz      short loc_180006EAC
0x180006e9f  mov     rax, [rcx]
0x180006ea2  mov     rax, [rax+8]
0x180006ea6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006eab  nop
0x180006eac  lea     rax, ??_7CContentFolder@@6BIDelegateFolder@@@; const CContentFolder::`vftable'{for `IDelegateFolder'}
0x180006eb3  mov     [rbx], rax
0x180006eb6  lea     rax, ??_7CContentFolder@@6BIPersistFolder2@@@; const CContentFolder::`vftable'{for `IPersistFolder2'}
0x180006ebd  mov     [rbx+8], rax
0x180006ec1  lea     rax, ??_7CContentFolder@@6BIShellFolder2@@@; const CContentFolder::`vftable'{for `IShellFolder2'}
0x180006ec8  mov     [rbx+10h], rax
0x180006ecc  lea     rax, ??_7CContentFolder@@6BIExplorerPaneVisibility@@@; const CContentFolder::`vftable'{for `IExplorerPaneVisibility'}
0x180006ed3  mov     [rbx+18h], rax
0x180006ed7  lea     rax, ??_7CContentFolder@@6BIItemNameLimits@@@; const CContentFolder::`vftable'{for `IItemNameLimits'}
0x180006ede  mov     [rbx+20h], rax
0x180006ee2  lea     rax, ??_7CContentFolder@@6BIShellFolderViewCB@@@; const CContentFolder::`vftable'{for `IShellFolderViewCB'}
0x180006ee9  mov     [rbx+68h], rax
0x180006eed  lea     rax, ??_7CContentFolder@@6BIFolderViewSettings@@@; const CContentFolder::`vftable'{for `IFolderViewSettings'}
0x180006ef4  mov     [rbx+70h], rax
0x180006ef8  lea     rax, ??_7CContentFolder@@6BIShellIconOverlay@@@; const CContentFolder::`vftable'{for `IShellIconOverlay'}
0x180006eff  mov     [rbx+78h], rax
0x180006f03  lea     rax, ??_7CContentFolder@@6BIStorage@@@; const CContentFolder::`vftable'{for `IStorage'}
0x180006f0a  mov     [rbx+80h], rax
0x180006f11  lea     rax, ??_7CContentFolder@@6BIUpdateIDList@@@; const CContentFolder::`vftable'{for `IUpdateIDList'}
0x180006f18  mov     [rbx+88h], rax
0x180006f1f  xor     ecx, ecx
0x180006f21  mov     [rbx+90h], ecx
0x180006f27  mov     [rbx+94h], esi
0x180006f2d  mov     [rbx+98h], ecx
0x180006f33  mov     eax, dword ptr [rsp+138h+var_F8]
0x180006f37  mov     [rbx+9Ch], eax
0x180006f3d  mov     [rbx+0A0h], rcx
0x180006f44  mov     rcx, [rbx+48h]
0x180006f48  mov     rax, [rcx]
0x180006f4b  lea     r8, [rbx+98h]
0x180006f52  mov     rdx, [rbx+40h]
0x180006f56  mov     rax, [rax+98h]
0x180006f5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f62  test    eax, eax
0x180006f64  js      loc_1800075D5
0x180006f6a  mov     eax, [rbx+98h]
0x180006f70  mov     dword ptr [rbx+50h], 10h
0x180006f77  cmp     eax, 3
0x180006f7a  jz      short loc_180006F95
0x180006f7c  sub     eax, 1
0x180006f7f  jnz     loc_18000729F
0x180006f85  lea     rax, aPropSystemSize; "prop:System.Size;System.DateModified;Sy"...
0x180006f8c  lea     rcx, qword_1800794B0
0x180006f93  jmp     short loc_180006FA3
0x180006f95  lea     rax, aPropSystemSize_0; "prop:System.Size;System.DateModified;Sy"...
0x180006f9c  lea     rcx, qword_180079330
0x180006fa3  mov     [rbx+58h], rcx
0x180006fa7  mov     [rbx+0A8h], rax
0x180006fae  test    rbx, rbx
0x180006fb1  jz      loc_180007231
0x180006fb7  lea     rcx, [rbx+8]
0x180006fbb  mov     rax, [rcx]
0x180006fbe  mov     rdx, rbp
0x180006fc1  mov     rax, [rax+20h]
0x180006fc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006fca  mov     esi, eax
0x180006fcc  test    eax, eax
0x180006fce  js      loc_180007613
0x180006fd4  test    r12, r12
0x180006fd7  jz      short loc_180006FE5
0x180006fd9  cmp     word ptr [r12], 0
0x180006fdf  jnz     loc_180007353
0x180006fe5  mov     [rsp+138h+var_100], 0
0x180006fee  mov     rsi, [rsp+138h+var_108]
0x180006ff3  test    rsi, rsi
0x180006ff6  jnz     loc_1800073B5
0x180006ffc  mov     r12d, 1
0x180007002  mov     rax, [rdi]
0x180007005  sub     rax, qword ptr cs:IID_IStream.Data1
0x18000700c  jnz     short loc_180007019
0x18000700e  mov     rax, [rdi+8]
0x180007012  sub     rax, qword ptr cs:IID_IStream.Data4
0x180007019  test    rax, rax
0x18000701c  jz      loc_18000719B
0x180007022  mov     rax, [rdi]
0x180007025  sub     rax, qword ptr cs:IID_IPortableDevice.Data1
0x18000702c  jnz     short loc_180007039
0x18000702e  mov     rax, [rdi+8]
0x180007032  sub     rax, qword ptr cs:IID_IPortableDevice.Data4
0x180007039  test    rax, rax
0x18000703c  jz      loc_180007662
0x180007042  mov     rax, [rdi]
0x180007045  sub     rax, qword ptr cs:IID_IPropertyStore.Data1
0x18000704c  jnz     short loc_180007059
0x18000704e  mov     rax, [rdi+8]
0x180007052  sub     rax, qword ptr cs:IID_IPropertyStore.Data4
0x180007059  test    rax, rax
0x18000705c  jz      loc_1800071F4
0x180007062  mov     rax, [rdi]
0x180007065  sub     rax, qword ptr cs:IID_IPropertySetStorage.Data1
0x18000706c  jnz     short loc_180007079
0x18000706e  mov     rax, [rdi+8]
0x180007072  sub     rax, qword ptr cs:IID_IPropertySetStorage.Data4
0x180007079  mov     r8, r15; struct IPropertySetStorage **
0x18000707c  test    rax, rax
0x18000707f  jz      loc_180007736
0x180007085  mov     rax, [rbx]
0x180007088  mov     rdx, rdi
0x18000708b  mov     rcx, rbx
0x18000708e  mov     rax, [rax]
0x180007091  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007096  mov     esi, eax
0x180007098  test    eax, eax
0x18000709a  jns     loc_180007246
0x1800070a0  mov     rax, cs:WPP_GLOBAL_Control
0x1800070a7  lea     rcx, WPP_GLOBAL_Control
0x1800070ae  cmp     rax, rcx
0x1800070b1  jz      loc_180007246
0x1800070b7  test    byte ptr [rax+1Ch], 2
0x1800070bb  jz      loc_180007246
0x1800070c1  mov     rdx, rdi; rguid
0x1800070c4  lea     rcx, [rsp+138h+sz]; lpsz
0x1800070c9  call    ??0CGuidToString@@QEAA@AEBU_GUID@@@Z; CGuidToString::CGuidToString(_GUID const &)
0x1800070ce  mov     edx, 15h
0x1800070d3  mov     dword ptr [rsp+138h+var_118], esi
0x1800070d7  mov     r9, rax
0x1800070da  lea     r8, WPP_953c7f1870f230da5c3777fec273291e_Traceguids
0x1800070e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800070e8  mov     rcx, [rcx+10h]
0x1800070ec  call    WPP_SF_Sd
0x1800070f1  jmp     loc_180007246
0x1800070f6  mov     rax, [rdi]
0x1800070f9  sub     rax, qword ptr cs:IID_IStream.Data1
0x180007100  jnz     short loc_18000710D
0x180007102  mov     rax, [rdi+8]
0x180007106  sub     rax, qword ptr cs:IID_IStream.Data4
0x18000710d  test    rax, rax
0x180007110  jz      loc_1800073FB
0x180007116  mov     rax, [rdi]
0x180007119  sub     rax, qword ptr cs:IID_IPortableDevice.Data1
0x180007120  jnz     short loc_18000712D
0x180007122  mov     rax, [rdi+8]
0x180007126  sub     rax, qword ptr cs:IID_IPortableDevice.Data4
0x18000712d  test    rax, rax
0x180007130  jz      loc_180007473
0x180007136  mov     rax, [rdi]
0x180007139  sub     rax, qword ptr cs:IID_IPropertyStore.Data1
0x180007140  jnz     short loc_18000714D
0x180007142  mov     rax, [rdi+8]
0x180007146  sub     rax, qword ptr cs:IID_IPropertyStore.Data4
0x18000714d  test    rax, rax
0x180007150  jnz     loc_1800074C6
0x180007156  lea     rcx, [r13-10h]
0x18000715a  mov     rax, [rcx]
0x18000715d  mov     r9d, 1
0x180007163  mov     r8, r15
0x180007166  mov     rdx, rbx
0x180007169  mov     rax, [rax+20h]
0x18000716d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007172  mov     ebx, eax
0x180007174  lea     rsi, WPP_GLOBAL_Control
0x18000717b  test    eax, eax
0x18000717d  js      loc_1800077C4
0x180007183  mov     rcx, cs:WPP_GLOBAL_Control
0x18000718a  mov     esi, ebx
0x18000718c  test    ebx, ebx
0x18000718e  js      loc_18000782D
0x180007194  mov     eax, ebx
0x180007196  jmp     loc_18000727B
0x18000719b  xor     edi, edi
0x18000719d  mov     [rsp+138h+var_108], rdi
0x1800071a2  test    rsi, rsi
0x1800071a5  jnz     loc_180007571
0x1800071ab  mov     rcx, rsi
0x1800071ae  call    BindCtx_GetMode
0x1800071b3  mov     [rsp+138h+var_118], r15; struct IStream **
0x1800071b8  mov     r9d, edi; int
0x1800071bb  mov     r8d, eax; unsigned int
0x1800071be  mov     rdx, r14; struct CONTENTITEM *
0x1800071c1  mov     rcx, [rsp+138h+var_E8]; this
0x1800071c6  call    ?_BindToStream@CContentFolder@@AEAAJPEFBUCONTENTITEM@@KHPEAPEAUIStream@@@Z; CContentFolder::_BindToStream(CONTENTITEM const *,ulong,int,IStream * *)
0x1800071cb  mov     esi, eax
0x1800071cd  test    eax, eax
0x1800071cf  jns     short loc_180007246
0x1800071d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800071d8  lea     rax, WPP_GLOBAL_Control
0x1800071df  cmp     rcx, rax
0x1800071e2  jz      short loc_180007246
0x1800071e4  test    byte ptr [rcx+1Ch], 2
0x1800071e8  jz      short loc_180007246
0x1800071ea  mov     edx, 11h
0x1800071ef  jmp     loc_180007640
0x1800071f4  lea     rcx, [r13-10h]
0x1800071f8  mov     rax, [rcx]
0x1800071fb  mov     r9d, r12d
0x1800071fe  mov     r8, r15
  ... truncated ...
```
