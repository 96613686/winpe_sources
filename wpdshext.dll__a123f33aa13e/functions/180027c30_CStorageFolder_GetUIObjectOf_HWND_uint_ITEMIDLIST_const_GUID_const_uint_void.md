# CStorageFolder::GetUIObjectOf(HWND__ *,uint,_ITEMIDLIST const * *,_GUID const &,uint *,void * *)

- ea: `0x180027c30`
- end: `0x18002851b`
- name: `?GetUIObjectOf@CStorageFolder@@UEAAJPEAUHWND__@@IPEAPEFBU_ITEMIDLIST@@AEBU_GUID@@PEAIPEAPEAX@Z`
- size: `2283`
- prototype: `int(CStorageFolder *__hidden this, HWND, unsigned int, const struct _ITEMIDLIST **, const struct _GUID *, unsigned int *, void **)`
- caller_count: `0`
- callee_count: `17`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180004110`
- `0x180009890`
- `0x18000d610`
- `0x180027c30`
- `0x1800285c8`
- `0x1800287d0`
- `0x18002a0d4`
- `0x18002ff5c`
- `0x180035590`
- `0x18005f93c`
- `0x1800607fc`
- `0x1800621ec`
- `0x180062f08`
- `0x180066a7c`
- `0x180066ed8`
- `0x18006709c`
- `0x180078010`

## import_xrefs

- `SHELL32!SHCreateDefaultContextMenu` at `0x180028275`
- `SHELL32!SHCreateDefaultContextMenu` at `0x180028340`
- `SHELL32!SHCreateDefaultContextMenu` at `0x180028275`
- `SHELL32!SHCreateDefaultContextMenu` at `0x180028340`
- `SHELL32!__imp_ILFree` at `0x180027d72`
- `SHELL32!__imp_ILFree` at `0x180027d72`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CStorageFolder::GetUIObjectOf(
        unsigned __int64 this,
        HWND a2,
        unsigned int a3,
        const struct _ITEMIDLIST **a4,
        const struct _GUID *riid,
        unsigned int *a6,
        void **ppv)
{
  int v10; // ebx
  const struct STORAGEITEM *v11; // rsi
  __int64 v12; // rax
  unsigned int v13; // r14d
  int v14; // r14d
  _QWORD *v15; // rcx
  __int64 v16; // rdx
  int v18; // r10d
  __int64 (__fastcall *v19)(unsigned __int64, LPITEMIDLIST, unsigned __int16 *, struct IContextMenuCB **, int, unsigned int, int, const struct _GUID *, void **); // r11
  __int64 v20; // rax
  GUID fmtid; // xmm0
  DWORD pid; // eax
  __int64 (__fastcall *v23)(unsigned __int64, LPITEMIDLIST, unsigned __int16 *, struct IContextMenuCB **, const struct _GUID *, void **); // r10
  __int64 v24; // rax
  int DataObject; // eax
  CStorageFolder *v26; // rcx
  _QWORD *v27; // rcx
  __int64 v28; // rdx
  unsigned int v29; // esi
  __int64 v30; // rdi
  const struct STORAGEITEM *v31; // rax
  __int64 v32; // rax
  _QWORD *v33; // rcx
  __int64 v34; // rdx
  __int64 v35; // rsi
  const struct _GUID *v36; // rdx
  CStorageFolder *v37; // rcx
  HRESULT v38; // eax
  unsigned int v39; // esi
  int v40; // edi
  __int64 v41; // rax
  __int64 v42; // rax
  struct IContextMenuCB *v43; // rdi
  unsigned int v44; // [rsp+50h] [rbp-B0h] BYREF
  LPITEMIDLIST pidl; // [rsp+58h] [rbp-A8h] BYREF
  IQueryAssociations *pqa; // [rsp+60h] [rbp-A0h] BYREF
  HWND v47; // [rsp+68h] [rbp-98h]
  DEFCONTEXTMENU pdcm; // [rsp+70h] [rbp-90h] BYREF
  struct IContextMenuCB *v49[2]; // [rsp+C0h] [rbp-40h] BYREF
  DWORD v50; // [rsp+D0h] [rbp-30h]
  HKEY rgKeys[2]; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v52; // [rsp+F0h] [rbp-10h]
  __int128 v53; // [rsp+100h] [rbp+0h]
  unsigned __int16 v54[264]; // [rsp+110h] [rbp+10h] BYREF

  v47 = a2;
  v10 = -2147467262;
  v44 = -2147467262;
  pidl = 0;
  if ( ppv )
  {
    if ( a3 && !a4 )
    {
      v10 = -2147024809;
      goto LABEL_21;
    }
    *ppv = 0;
    if ( a3 )
    {
      v11 = CStorageFolder::_IsValid(0, *a4);
      a2 = v47;
    }
    else
    {
      v11 = 0;
    }
    v12 = *(_QWORD *)&riid->Data1 - *(_QWORD *)&IID_IExtractIconW.Data1;
    if ( *(_QWORD *)&riid->Data1 == *(_QWORD *)&IID_IExtractIconW.Data1 )
      v12 = *(_QWORD *)riid->Data4 - *(_QWORD *)IID_IExtractIconW.Data4;
    if ( !v12 && v11 )
    {
      v13 = *(_DWORD *)((char *)v11 + 14);
      v44 = (v13 >> 18) & 1;
      v14 = (v13 >> 19) & 1;
      v10 = SHILCombine(*(_QWORD *)(this + 48), *a4, &pidl);
      if ( v10 >= 0 )
      {
        StringCchCopyW(v54, 0x104u, (const unsigned __int16 *)v11 + *(unsigned int *)((char *)v11 + 38) + 27);
        *(GUID *)v49 = GUID_NULL;
        v10 = v19(this - 16, pidl, v54, v49, v18, v44, v14, riid, ppv);
        if ( v10 < 0 )
        {
          v15 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            v16 = 38;
            goto LABEL_17;
          }
        }
      }
      else
      {
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          v16 = 37;
LABEL_17:
          WPP_SF_d(v15[2], v16, WPP_9caa288f52d13f713777aed0becde05d_Traceguids, (unsigned int)v10);
        }
      }
LABEL_18:
      if ( pidl )
        ILFree(pidl);
      goto LABEL_20;
    }
    v20 = *(_QWORD *)&riid->Data1 - *(_QWORD *)&IID_IExtractImage.Data1;
    if ( *(_QWORD *)&riid->Data1 == *(_QWORD *)&IID_IExtractImage.Data1 )
      v20 = *(_QWORD *)riid->Data4 - *(_QWORD *)IID_IExtractImage.Data4;
    if ( !v20 && v11 )
    {
      if ( (*(_DWORD *)((_BYTE *)v11 + 14) & 0x20000) != 0 )
      {
        fmtid = WPD_RESOURCE_THUMBNAIL.fmtid;
        pid = WPD_RESOURCE_THUMBNAIL.pid;
      }
      else if ( (*(_DWORD *)((_BYTE *)v11 + 14) & 0x100000) != 0 )
      {
        fmtid = WPD_RESOURCE_ALBUM_ART.fmtid;
        pid = WPD_RESOURCE_ALBUM_ART.pid;
      }
      else
      {
        if ( (*(_DWORD *)((_BYTE *)v11 + 14) & 0x10000) == 0 )
        {
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
            return (unsigned int)v10;
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              39,
              WPP_9caa288f52d13f713777aed0becde05d_Traceguids,
              2147500034LL);
          goto LABEL_21;
        }
        fmtid = WPD_RESOURCE_CONTACT_PHOTO.fmtid;
        pid = WPD_RESOURCE_CONTACT_PHOTO.pid;
      }
      *(GUID *)v49 = fmtid;
      v50 = pid;
      v10 = SHILCombine(*(_QWORD *)(this + 48), *a4, &pidl);
      if ( v10 >= 0 )
      {
        StringCchCopyW(v54, 0x104u, (const unsigned __int16 *)v11 + *(unsigned int *)((char *)v11 + 38) + 27);
        v10 = v23(this - 16, pidl, v54, v49, riid, ppv);
        if ( v10 < 0 )
        {
          v15 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            v16 = 41;
            goto LABEL_17;
          }
        }
      }
      else
      {
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          v16 = 40;
          goto LABEL_17;
        }
      }
      goto LABEL_18;
    }
    v24 = *(_QWORD *)&riid->Data1 - *(_QWORD *)&IID_IDataObject.Data1;
    if ( *(_QWORD *)&riid->Data1 == *(_QWORD *)&IID_IDataObject.Data1 )
      v24 = *(_QWORD *)riid->Data4 - *(_QWORD *)IID_IDataObject.Data4;
    if ( !v24 && a3 )
    {
      DataObject = CreateDataObject(
                     *(const struct _ITEMIDLIST **)(this + 48),
                     a3,
                     a4,
                     (struct IDataObject *)a4,
                     (struct IDataObject **)ppv);
      v10 = DataObject;
      if ( DataObject < 0 )
      {
        v27 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_20;
        v28 = 42;
        goto LABEL_58;
      }
      v29 = -1;
      v30 = 0;
      do
      {
        v31 = CStorageFolder::_IsValid(v26, a4[v30]);
        if ( v31 )
          v29 &= *(_DWORD *)((char *)v31 + 10);
        v30 = (unsigned int)(v30 + 1);
      }
      while ( (unsigned int)v30 < a3 );
      DataObj_SetDWORD(*ppv, g_cfWPD_ATTRIBUTES, v29);
      DataObj_SetDWORD(*ppv, g_cfWPDShellExtension, 1);
LABEL_20:
      if ( v10 >= 0 )
        return (unsigned int)v10;
      goto LABEL_21;
    }
    v32 = *(_QWORD *)&riid->Data1 - *(_QWORD *)&IID_IContextMenu.Data1;
    if ( *(_QWORD *)&riid->Data1 == *(_QWORD *)&IID_IContextMenu.Data1 )
      v32 = *(_QWORD *)riid->Data4 - *(_QWORD *)IID_IContextMenu.Data4;
    if ( v32 || !v11 )
    {
      v41 = *(_QWORD *)&riid->Data1 - *(_QWORD *)&IID_IQueryAssociations.Data1;
      if ( *(_QWORD *)&riid->Data1 == *(_QWORD *)&IID_IQueryAssociations.Data1 )
        v41 = *(_QWORD *)riid->Data4 - *(_QWORD *)IID_IQueryAssociations.Data4;
      if ( !v41 )
      {
        DataObject = CStorageFolder::_AssocCreate(0, riid, ppv);
        v10 = DataObject;
        if ( DataObject >= 0 )
          goto LABEL_20;
        v27 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_20;
        v28 = 47;
LABEL_58:
        WPP_SF_d(v27[2], v28, WPP_9caa288f52d13f713777aed0becde05d_Traceguids, (unsigned int)DataObject);
        goto LABEL_20;
      }
      v42 = *(_QWORD *)&riid->Data1 - *(_QWORD *)&IID_IDropTarget.Data1;
      if ( *(_QWORD *)&riid->Data1 == *(_QWORD *)&IID_IDropTarget.Data1 )
        v42 = *(_QWORD *)riid->Data4 - *(_QWORD *)IID_IDropTarget.Data4;
      if ( v42 )
        goto LABEL_18;
      v43 = (struct IContextMenuCB *)operator new(0x50u, (const struct std::nothrow_t *)a2);
      v49[0] = v43;
      if ( v43 )
      {
        CBaseDropTarget::CBaseDropTarget(
          (CBaseDropTarget *)v43,
          (struct CBaseFolder *)(this - 16),
          v47,
          *a4,
          (int *)&v44);
        v43->lpVtbl = (struct IContextMenuCBVtbl *)&CStorageDropTarget::`vftable'{for `IDropTarget'};
        v43[1].lpVtbl = (struct IContextMenuCBVtbl *)&CDeviceDropTarget::`vftable'{for `IEnterpriseDropTarget'};
        v43[2].lpVtbl = (struct IContextMenuCBVtbl *)&CStorageDropTarget::`vftable'{for `CObjectWindow'};
        v10 = v44;
      }
      else
      {
        v43 = 0;
      }
      if ( v10 >= 0 )
      {
        if ( !v43 )
        {
          v10 = -2147024882;
          goto LABEL_20;
        }
        v10 = ((__int64 (__fastcall *)(struct IContextMenuCB *, GUID *, void **))v43->lpVtbl->QueryInterface)(
                v43,
                &IID_IDropTarget,
                ppv);
        if ( v10 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            49,
            WPP_9caa288f52d13f713777aed0becde05d_Traceguids,
            (unsigned int)v10);
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            48,
            WPP_9caa288f52d13f713777aed0becde05d_Traceguids,
            (unsigned int)v10);
        if ( !v43 )
          goto LABEL_20;
      }
      ((void (__fastcall *)(struct IContextMenuCB *))v43->lpVtbl->Release)(v43);
      goto LABEL_20;
    }
    if ( (*((_BYTE *)v11 + 10) & 2) == 0 )
    {
      v49[0] = 0;
      v10 = CStorageFolder::_ContextMenuCBCreate((CStorageFolder *)(this - 16), v49, 0);
      if ( v10 < 0 )
        goto LABEL_90;
      pdcm.hwnd = v47;
      pdcm.pcmcb = v49[0];
      pdcm.pidlFolder = *(LPCITEMIDLIST *)(this + 48);
      pdcm.psf = (IShellFolder *)(this & -(__int64)(this != 16));
      pdcm.cidl = a3;
      *(&pdcm.cidl + 1) = 0;
      pdcm.apidl = a4;
      memset(&pdcm.punkAssociationInfo, 0, 24);
      v10 = SHCreateDefaultContextMenu(&pdcm, riid, ppv);
      if ( v10 < 0 )
      {
LABEL_90:
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            46,
            WPP_9caa288f52d13f713777aed0becde05d_Traceguids,
            (unsigned int)v10);
      }
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v49);
      goto LABEL_20;
    }
    pqa = 0;
    pidl = 0;
    *(_OWORD *)rgKeys = 0;
    v52 = 0;
    v53 = 0;
    v10 = (*(__int64 (__fastcall **)(unsigned __int64, HWND, __int64, const struct _ITEMIDLIST **, GUID *, _QWORD, IQueryAssociations **))(*(_QWORD *)this + 80LL))(
            this,
            a2,
            1,
            a4,
            &IID_IQueryAssociations,
            0,
            &pqa);
    if ( v10 >= 0 )
    {
      v35 = SHGetAssocKeys(pqa, rgKeys, 3u);
      v10 = CStorageFolder::_ContextAssocCreate(v37, v36, (void **)&pidl);
      if ( v10 >= 0 )
      {
        v44 = v35 + SHGetAssocKeys((IQueryAssociations *)pidl, &rgKeys[v35], 6 - v35);
        v49[0] = 0;
        v38 = CStorageFolder::_ContextMenuCBCreate((CStorageFolder *)(this - 16), v49, 0);
        v10 = v38;
        if ( v38 < 0 )
        {
          v39 = v44;
        }
        else
        {
          pdcm.hwnd = v47;
          pdcm.pcmcb = v49[0];
          pdcm.pidlFolder = *(LPCITEMIDLIST *)(this + 48);
          pdcm.psf = (IShellFolder *)(this & -(__int64)(this != 16));
          pdcm.cidl = a3;
          *(&pdcm.cidl + 1) = 0;
          pdcm.apidl = a4;
          pdcm.punkAssociationInfo = 0;
          v39 = v44;
          pdcm.cKeys = v44;
          *(&pdcm.cKeys + 1) = 0;
          pdcm.aKeys = rgKeys;
          v38 = SHCreateDefaultContextMenu(&pdcm, riid, ppv);
          v10 = v38;
        }
        v40 = v38;
        SHRegCloseKeys(rgKeys, v39);
        if ( v40 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            45,
            WPP_9caa288f52d13f713777aed0becde05d_Traceguids,
            (unsigned int)v10);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v49);
        goto LABEL_78;
      }
      v33 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      {
LABEL_78:
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&pidl);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&pqa);
        goto LABEL_20;
      }
      v34 = 44;
    }
    else
    {
      v33 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_78;
      v34 = 43;
    }
    WPP_SF_d(v33[2], v34, WPP_9caa288f52d13f713777aed0becde05d_Traceguids, (unsigned int)v10);
    goto LABEL_78;
  }
  v10 = -2147467261;
LABEL_21:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      50,
      WPP_9caa288f52d13f713777aed0becde05d_Traceguids,
      (unsigned int)v10);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180027c30  push    rbp
0x180027c32  push    rbx
0x180027c33  push    rsi
0x180027c34  push    rdi
0x180027c35  push    r12
0x180027c37  push    r13
0x180027c39  push    r14
0x180027c3b  push    r15
0x180027c3d  lea     rbp, [rsp-238h]
0x180027c45  sub     rsp, 338h
0x180027c4c  mov     rax, cs:__security_cookie
0x180027c53  xor     rax, rsp
0x180027c56  mov     [rbp+270h+var_50], rax
0x180027c5d  mov     r12, r9
0x180027c60  mov     r14d, r8d
0x180027c63  mov     [rsp+370h+var_308], rdx
0x180027c68  mov     r13, rcx
0x180027c6b  mov     rdi, [rbp+270h+riid]
0x180027c72  mov     r15, [rbp+270h+ppv]
0x180027c79  mov     ebx, 80004002h
0x180027c7e  mov     [rsp+370h+var_320], ebx
0x180027c82  xor     ecx, ecx; this
0x180027c84  mov     [rsp+370h+pidl], rcx
0x180027c89  lea     r8, WPP_GLOBAL_Control
0x180027c90  test    r15, r15
0x180027c93  jnz     short loc_180027C9F
0x180027c95  mov     ebx, 80004003h
0x180027c9a  jmp     loc_180027D83
0x180027c9f  test    r14d, r14d
0x180027ca2  jz      short loc_180027CB3
0x180027ca4  test    r12, r12
0x180027ca7  jnz     short loc_180027CB3
0x180027ca9  mov     ebx, 80070057h
0x180027cae  jmp     loc_180027D83
0x180027cb3  mov     [r15], rcx
0x180027cb6  test    r14d, r14d
0x180027cb9  jz      short loc_180027CD6
0x180027cbb  mov     rdx, [r9]; struct _ITEMIDLIST *
0x180027cbe  call    ?_IsValid@CStorageFolder@@AEAAPEFBUSTORAGEITEM@@PEFBU_ITEMIDLIST@@@Z; CStorageFolder::_IsValid(_ITEMIDLIST const *)
0x180027cc3  mov     rsi, rax
0x180027cc6  mov     rdx, [rsp+370h+var_308]
0x180027ccb  xor     ecx, ecx
0x180027ccd  lea     r8, WPP_GLOBAL_Control
0x180027cd4  jmp     short loc_180027CD9
0x180027cd6  mov     rsi, rcx
0x180027cd9  mov     rax, [rdi]
0x180027cdc  sub     rax, qword ptr cs:IID_IExtractIconW.Data1
0x180027ce3  jnz     short loc_180027CF0
0x180027ce5  mov     rax, [rdi+8]
0x180027ce9  sub     rax, qword ptr cs:IID_IExtractIconW.Data4
0x180027cf0  test    rax, rax
0x180027cf3  jnz     loc_180027E7E
0x180027cf9  test    rsi, rsi
0x180027cfc  jz      loc_180027E7E
0x180027d02  mov     r14d, [rsi+0Eh]
0x180027d06  mov     eax, r14d
0x180027d09  shr     eax, 12h
0x180027d0c  and     eax, 1
0x180027d0f  mov     [rsp+370h+var_320], eax
0x180027d13  shr     r14d, 13h
0x180027d17  and     r14d, 1
0x180027d1b  lea     r8, [rsp+370h+pidl]
0x180027d20  mov     rdx, [r12]
0x180027d24  mov     rcx, [r13+30h]
0x180027d28  call    SHILCombine
0x180027d2d  mov     ebx, eax
0x180027d2f  test    eax, eax
0x180027d31  jns     loc_180027DD2
0x180027d37  mov     rcx, cs:WPP_GLOBAL_Control
0x180027d3e  lea     rax, WPP_GLOBAL_Control
0x180027d45  cmp     rcx, rax
0x180027d48  jz      short loc_180027D68
0x180027d4a  test    byte ptr [rcx+1Ch], 2
0x180027d4e  jz      short loc_180027D68
0x180027d50  mov     edx, 25h ; '%'
0x180027d55  mov     r9d, ebx
0x180027d58  lea     r8, WPP_9caa288f52d13f713777aed0becde05d_Traceguids
0x180027d5f  mov     rcx, [rcx+10h]
0x180027d63  call    WPP_SF_d
0x180027d68  mov     rcx, [rsp+370h+pidl]; pidl
0x180027d6d  test    rcx, rcx
0x180027d70  jz      short loc_180027D78
0x180027d72  call    cs:__imp_ILFree
0x180027d78  lea     r8, WPP_GLOBAL_Control
0x180027d7f  test    ebx, ebx
0x180027d81  jns     short loc_180027DAD
0x180027d83  mov     rcx, cs:WPP_GLOBAL_Control
0x180027d8a  cmp     rcx, r8
0x180027d8d  jz      short loc_180027DAD
0x180027d8f  test    byte ptr [rcx+1Ch], 2
0x180027d93  jz      short loc_180027DAD
0x180027d95  mov     edx, 32h ; '2'
0x180027d9a  mov     r9d, ebx
0x180027d9d  lea     r8, WPP_9caa288f52d13f713777aed0becde05d_Traceguids
0x180027da4  mov     rcx, [rcx+10h]
0x180027da8  call    WPP_SF_d
0x180027dad  mov     eax, ebx
0x180027daf  mov     rcx, [rbp+270h+var_50]
0x180027db6  xor     rcx, rsp; StackCookie
0x180027db9  call    __security_check_cookie
0x180027dbe  add     rsp, 338h
0x180027dc5  pop     r15
0x180027dc7  pop     r14
0x180027dc9  pop     r13
0x180027dcb  pop     r12
0x180027dcd  pop     rdi
0x180027dce  pop     rsi
0x180027dcf  pop     rbx
0x180027dd0  pop     rbp
0x180027dd1  retn
0x180027dd2  mov     eax, [rsi+0Eh]
0x180027dd5  and     eax, 200000h
0x180027dda  neg     eax
0x180027ddc  sbb     r10d, r10d
0x180027ddf  and     r10d, 0FFFFFFFDh
0x180027de3  add     r10d, 0FFFFFFE0h
0x180027de7  mov     rax, [r13-10h]
0x180027deb  mov     r11, [rax+70h]
0x180027def  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180027df6  mov     eax, [rsi+26h]
0x180027df9  add     rax, 1Bh
0x180027dfd  lea     r8, [rsi+rax*2]; unsigned __int16 *
0x180027e01  mov     edx, 104h; unsigned __int64
0x180027e06  lea     rcx, [rbp+270h+var_260]; unsigned __int16 *
0x180027e0a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180027e0f  movdqu  xmmword ptr [rbp+270h+var_2B0], xmm0
0x180027e14  mov     [rsp+370h+var_330], r15
0x180027e19  mov     [rsp+370h+var_338], rdi
0x180027e1e  mov     dword ptr [rsp+370h+var_340], r14d
0x180027e23  mov     eax, [rsp+370h+var_320]
0x180027e27  mov     dword ptr [rsp+370h+var_348], eax
0x180027e2b  mov     dword ptr [rsp+370h+var_350], r10d
0x180027e30  lea     r9, [rbp+270h+var_2B0]
0x180027e34  lea     r8, [rbp+270h+var_260]
0x180027e38  mov     rdx, [rsp+370h+pidl]
0x180027e3d  lea     rcx, [r13-10h]
0x180027e41  mov     rax, r11
0x180027e44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027e49  mov     ebx, eax
0x180027e4b  test    eax, eax
0x180027e4d  jns     loc_180027D68
0x180027e53  mov     rcx, cs:WPP_GLOBAL_Control
0x180027e5a  lea     rax, WPP_GLOBAL_Control
0x180027e61  cmp     rcx, rax
0x180027e64  jz      loc_180027D68
0x180027e6a  test    byte ptr [rcx+1Ch], 2
0x180027e6e  jz      loc_180027D68
0x180027e74  mov     edx, 26h ; '&'
0x180027e79  jmp     loc_180027D55
0x180027e7e  mov     rax, [rdi]
0x180027e81  sub     rax, qword ptr cs:IID_IExtractImage.Data1
0x180027e88  jnz     short loc_180027E95
0x180027e8a  mov     rax, [rdi+8]
0x180027e8e  sub     rax, qword ptr cs:IID_IExtractImage.Data4
0x180027e95  test    rax, rax
0x180027e98  jnz     loc_180027FF2
0x180027e9e  test    rsi, rsi
0x180027ea1  jz      loc_180027FF2
0x180027ea7  test    dword ptr [rsi+0Eh], 20000h
0x180027eae  jz      short loc_180027EBF
0x180027eb0  movups  xmm0, xmmword ptr cs:WPD_RESOURCE_THUMBNAIL.fmtid.Data1
0x180027eb7  mov     eax, cs:WPD_RESOURCE_THUMBNAIL.pid
0x180027ebd  jmp     short loc_180027EF1
0x180027ebf  test    dword ptr [rsi+0Eh], 100000h
0x180027ec6  jz      short loc_180027ED7
0x180027ec8  movups  xmm0, xmmword ptr cs:WPD_RESOURCE_ALBUM_ART.fmtid.Data1
0x180027ecf  mov     eax, cs:WPD_RESOURCE_ALBUM_ART.pid
0x180027ed5  jmp     short loc_180027EF1
0x180027ed7  test    dword ptr [rsi+0Eh], 10000h
0x180027ede  jz      loc_180027FB4
0x180027ee4  movups  xmm0, xmmword ptr cs:WPD_RESOURCE_CONTACT_PHOTO.fmtid.Data1
0x180027eeb  mov     eax, cs:WPD_RESOURCE_CONTACT_PHOTO.pid
0x180027ef1  movups  xmmword ptr [rbp+270h+var_2B0], xmm0
0x180027ef5  mov     [rbp+270h+var_2A0], eax
0x180027ef8  lea     r8, [rsp+370h+pidl]
0x180027efd  mov     rdx, [r12]
0x180027f01  mov     rcx, [r13+30h]
0x180027f05  call    SHILCombine
0x180027f0a  mov     ebx, eax
0x180027f0c  test    eax, eax
0x180027f0e  jns     short loc_180027F3B
0x180027f10  mov     rcx, cs:WPP_GLOBAL_Control
0x180027f17  lea     rax, WPP_GLOBAL_Control
0x180027f1e  cmp     rcx, rax
0x180027f21  jz      loc_180027D68
0x180027f27  test    byte ptr [rcx+1Ch], 2
0x180027f2b  jz      loc_180027D68
0x180027f31  mov     edx, 28h ; '('
0x180027f36  jmp     loc_180027D55
0x180027f3b  mov     rax, [r13-10h]
0x180027f3f  mov     r10, [rax+78h]
0x180027f43  mov     eax, [rsi+26h]
0x180027f46  add     rax, 1Bh
0x180027f4a  lea     r8, [rsi+rax*2]; unsigned __int16 *
0x180027f4e  mov     edx, 104h; unsigned __int64
0x180027f53  lea     rcx, [rbp+270h+var_260]; unsigned __int16 *
0x180027f57  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180027f5c  mov     [rsp+370h+var_348], r15
0x180027f61  mov     [rsp+370h+var_350], rdi
0x180027f66  lea     r9, [rbp+270h+var_2B0]
0x180027f6a  lea     r8, [rbp+270h+var_260]
0x180027f6e  mov     rdx, [rsp+370h+pidl]
0x180027f73  lea     rcx, [r13-10h]
0x180027f77  mov     rax, r10
0x180027f7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027f7f  mov     ebx, eax
0x180027f81  test    eax, eax
0x180027f83  jns     loc_180027D68
0x180027f89  mov     rcx, cs:WPP_GLOBAL_Control
0x180027f90  lea     rax, WPP_GLOBAL_Control
0x180027f97  cmp     rcx, rax
0x180027f9a  jz      loc_180027D68
0x180027fa0  test    byte ptr [rcx+1Ch], 2
0x180027fa4  jz      loc_180027D68
0x180027faa  mov     edx, 29h ; ')'
0x180027faf  jmp     loc_180027D55
0x180027fb4  mov     rcx, cs:WPP_GLOBAL_Control
0x180027fbb  cmp     rcx, r8
0x180027fbe  jz      loc_180027DAD
0x180027fc4  test    byte ptr [rcx+1Ch], 2
0x180027fc8  jz      loc_180027D83
0x180027fce  mov     edx, 27h ; '''
0x180027fd3  mov     r9d, ebx
0x180027fd6  lea     r8, WPP_9caa288f52d13f713777aed0becde05d_Traceguids
0x180027fdd  mov     rcx, [rcx+10h]
0x180027fe1  call    WPP_SF_d
0x180027fe6  lea     r8, WPP_GLOBAL_Control
0x180027fed  jmp     loc_180027D83
0x180027ff2  mov     rax, [rdi]
0x180027ff5  sub     rax, qword ptr cs:IID_IDataObject.Data1
0x180027ffc  jnz     short loc_180028009
0x180027ffe  mov     rax, [rdi+8]
0x180028002  sub     rax, qword ptr cs:IID_IDataObject.Data4
0x180028009  test    rax, rax
0x18002800c  jnz     loc_1800280C1
0x180028012  test    r14d, r14d
0x180028015  jz      loc_1800280C1
0x18002801b  mov     [rsp+370h+var_350], r15; struct IDataObject **
0x180028020  mov     r8, r12; struct _ITEMIDLIST **
0x180028023  mov     edx, r14d; unsigned int
0x180028026  mov     rcx, [r13+30h]; Src
0x18002802a  call    ?CreateDataObject@@YAJPEFBU_ITEMIDLIST@@IPEAPEFBU1@PEAUIDataObject@@PEAPEAU2@@Z; CreateDataObject(_ITEMIDLIST const *,uint,_ITEMIDLIST const * *,IDataObject *,IDataObject * *)
0x18002802f  mov     ebx, eax
0x180028031  test    eax, eax
0x180028033  jns     short loc_180028073
0x180028035  mov     rcx, cs:WPP_GLOBAL_Control
0x18002803c  lea     r8, WPP_GLOBAL_Control
0x180028043  cmp     rcx, r8
0x180028046  jz      loc_180027D7F
0x18002804c  test    byte ptr [rcx+1Ch], 2
0x180028050  jz      loc_180027D7F
0x180028056  mov     edx, 2Ah ; '*'
0x18002805b  mov     r9d, eax
0x18002805e  lea     r8, WPP_9caa288f52d13f713777aed0becde05d_Traceguids
0x180028065  mov     rcx, [rcx+10h]
0x180028069  call    WPP_SF_d
0x18002806e  jmp     loc_180027D78
0x180028073  or      esi, 0FFFFFFFFh
0x180028076  xor     edi, edi
0x180028078  test    r14d, r14d
0x18002807b  jz      short loc_180028095
0x18002807d  mov     rdx, [r12+rdi*8]; struct _ITEMIDLIST *
0x180028081  call    ?_IsValid@CStorageFolder@@AEAAPEFBUSTORAGEITEM@@PEFBU_ITEMIDLIST@@@Z; CStorageFolder::_IsValid(_ITEMIDLIST const *)
0x180028086  test    rax, rax
0x180028089  jz      short loc_18002808E
0x18002808b  and     esi, [rax+0Ah]
0x18002808e  inc     edi
0x180028090  cmp     edi, r14d
0x180028093  jb      short loc_18002807D
0x180028095  movzx   edx, cs:?g_cfWPD_ATTRIBUTES@@3GA; ushort g_cfWPD_ATTRIBUTES
0x18002809c  mov     r8d, esi
0x18002809f  mov     rcx, [r15]
0x1800280a2  call    DataObj_SetDWORD
0x1800280a7  movzx   edx, cs:?g_cfWPDShellExtension@@3GA; ushort g_cfWPDShellExtension
0x1800280ae  mov     r8d, 1
0x1800280b4  mov     rcx, [r15]
0x1800280b7  call    DataObj_SetDWORD
0x1800280bc  jmp     loc_180027D78
0x1800280c1  mov     rax, [rdi]
0x1800280c4  sub     rax, qword ptr cs:IID_IContextMenu.Data1
0x1800280cb  jnz     short loc_1800280D8
0x1800280cd  mov     rax, [rdi+8]
0x1800280d1  sub     rax, qword ptr cs:IID_IContextMenu.Data4
0x1800280d8  test    rax, rax
0x1800280db  jnz     loc_18002838C
0x1800280e1  test    rsi, rsi
0x1800280e4  jz      loc_18002838C
0x1800280ea  test    byte ptr [rsi+0Ah], 2
0x1800280ee  jz      loc_1800282D4
0x1800280f4  mov     [rsp+370h+pqa], rcx
0x1800280f9  mov     [rsp+370h+pidl], rcx
0x1800280fe  xorps   xmm0, xmm0
0x180028101  movups  xmmword ptr [rbp+270h+rgKeys], xmm0
0x180028105  movups  [rbp+270h+var_280], xmm0
0x180028109  movups  [rbp+270h+var_270], xmm0
0x18002810d  mov     rax, [r13+0]
0x180028111  lea     rcx, [rsp+370h+pqa]
0x180028116  mov     [rsp+370h+var_340], rcx
0x18002811b  mov     [rsp+370h+var_348], 0
0x180028124  lea     rcx, IID_IQueryAssociations
  ... truncated ...
```
