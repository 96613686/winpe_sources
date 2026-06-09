# CDefFolderMenu::InvokeCommand(_CMINVOKECOMMANDINFO *)

- ea: `0x1802834f0`
- end: `0x180283cd9`
- name: `?InvokeCommand@CDefFolderMenu@@UEAAJPEAU_CMINVOKECOMMANDINFO@@@Z`
- size: `2025`
- prototype: `int(CDefFolderMenu *__hidden this, struct _CMINVOKECOMMANDINFO *)`
- caller_count: `0`
- callee_count: `24`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x18002f30c`
- `0x1800979b8`
- `0x1800bf8d0`
- `0x180121104`
- `0x1801292d8`
- `0x18013126c`
- `0x180138978`
- `0x18015b3d0`
- `0x180178b40`
- `0x180180000`
- `0x180180bd0`
- `0x180183680`
- `0x1801db6a8`
- `0x1801e9c90`
- `0x180249490`
- `0x18024a53c`
- `0x18027e618`
- `0x1802834f0`
- `0x180286700`
- `0x180287428`
- `0x180287930`
- `0x180287b30`
- `0x180287b98`
- `0x1805b2010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180283a91`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180283a91`
- `USER32!AllowSetForegroundWindow` at `0x1802838b4`
- `USER32!AllowSetForegroundWindow` at `0x1802838b4`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x180283a10`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x180283a36`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x180283a10`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x180283a36`
- `api-ms-win-shcore-thread-l1-1-0!SHCreateThread` at `0x180283a64`
- `api-ms-win-shcore-thread-l1-1-0!SHCreateThread` at `0x180283a64`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_SetSite` at `0x18028388a`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_SetSite` at `0x18028393e`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_SetSite` at `0x18028388a`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_SetSite` at `0x18028393e`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x180283b95`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x180283b95`
- `SHCORE!__imp_SHGetObjectCompatFlags` at `0x18028389f`
- `SHCORE!__imp_SHGetObjectCompatFlags` at `0x18028389f`
- `ext-ms-win-com-ole32-l1-1-5!OleSetClipboard` at `0x180283bc1`
- `ext-ms-win-com-ole32-l1-1-5!OleSetClipboard` at `0x180283bc1`
- `Windows.Storage!DeleteItemsInDataObject` at `0x180283ab4`
- `Windows.Storage!DeleteItemsInDataObject` at `0x180283ab4`
- `Windows.Storage!SetAppStartingCursor` at `0x18028357a`
- `Windows.Storage!SetAppStartingCursor` at `0x180283ca0`
- `Windows.Storage!SetAppStartingCursor` at `0x18028357a`
- `Windows.Storage!SetAppStartingCursor` at `0x180283ca0`
- `Windows.Storage!__imp_SHRestricted` at `0x180283aca`
- `Windows.Storage!__imp_SHRestricted` at `0x180283aca`

## pseudocode

```c
__int64 __fastcall CDefFolderMenu::InvokeCommand(CDefFolderMenu *this, struct _CMINVOKECOMMANDINFO *a2)
{
  HRESULT v2; // ebx
  bool v4; // cf
  int v6; // r14d
  HWND hwnd; // rax
  HWND *v8; // r13
  HWND v9; // r12
  HRESULT v10; // eax
  int v11; // r12d
  unsigned int lpVerb_low; // r14d
  unsigned int v13; // ecx
  unsigned int v14; // eax
  unsigned int v15; // ecx
  __int64 v16; // rdx
  LPSTREAM *lpVerb; // rsi
  bool v18; // zf
  struct _DSA *v19; // rcx
  __int64 i; // rcx
  unsigned __int16 *AnsiOrUnicodeParam; // rax
  LPSTREAM *v22; // r14
  DWORD fMask; // ecx
  struct IDataObject *v24; // rcx
  __int64 v25; // rdx
  void *v26; // rcx
  LPSTREAM *v27; // rsi
  IUnknown *v28; // rdx
  __int64 v29; // rdx
  int v30; // eax
  struct IDataObject *v31; // rcx
  struct IDataObject *v32; // rcx
  struct IUnknown *v33; // rcx
  unsigned int v35; // [rsp+20h] [rbp-E0h]
  unsigned int v36; // [rsp+20h] [rbp-E0h]
  unsigned int v37; // [rsp+20h] [rbp-E0h]
  int v38; // [rsp+40h] [rbp-C0h] BYREF
  HWND v39; // [rsp+48h] [rbp-B8h]
  unsigned int v40; // [rsp+50h] [rbp-B0h] BYREF
  LPSTREAM *ppStm; // [rsp+58h] [rbp-A8h] BYREF
  int v42; // [rsp+60h] [rbp-A0h]
  DWORD v43; // [rsp+64h] [rbp-9Ch]
  LPSTREAM *v44; // [rsp+68h] [rbp-98h]
  int v45; // [rsp+70h] [rbp-90h]
  int v46; // [rsp+74h] [rbp-8Ch]
  struct _CMINVOKECOMMANDINFO *v47; // [rsp+78h] [rbp-88h]
  __int64 v48; // [rsp+80h] [rbp-80h]
  _CMINVOKECOMMANDINFOEX Src; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v50[264]; // [rsp+110h] [rbp+10h] BYREF

  v2 = 0;
  v4 = a2->cbSize < 0x60;
  v40 = 0;
  if ( v4 || (v6 = 1, (a2->fMask & 0x4000) == 0) )
    v6 = 0;
  hwnd = a2->hwnd;
  v8 = (HWND *)((char *)this + 144);
  v38 = v6;
  v9 = hwnd;
  if ( !hwnd )
    v9 = *v8;
  v39 = v9;
  if ( !*((_QWORD *)this + 18) )
    *v8 = hwnd;
  SetAppStartingCursor(v9, 1);
  if ( a2->cbSize < 0x38 )
    goto LABEL_91;
  if ( *((_DWORD *)this + 32) )
  {
    v10 = CDefFolderMenu::_HandlePartialSelectionInvoke((char *)this - 16, a2, 1);
LABEL_11:
    v2 = v10;
    goto LABEL_92;
  }
  if ( a2->lpVerb < (LPCSTR)0x10000 )
  {
    lpVerb_low = LOWORD(a2->lpVerb);
    v13 = *((_DWORD *)this + 40);
    if ( lpVerb_low < v13 )
    {
      v2 = DCMIDMtoDFM(LOWORD(a2->lpVerb), &v40);
      if ( v2 < 0 )
        goto LABEL_92;
      goto LABEL_36;
    }
    v14 = *((_DWORD *)this + 41);
    if ( lpVerb_low < v14 )
    {
      v40 = lpVerb_low - v13;
      goto LABEL_36;
    }
    v15 = *((_DWORD *)this + 42);
    v11 = LOWORD(a2->lpVerb);
    if ( lpVerb_low >= v15 )
    {
      if ( lpVerb_low < *((_DWORD *)this + 43) )
      {
        v40 = lpVerb_low - v15;
        v9 = v39;
        goto LABEL_36;
      }
LABEL_91:
      v2 = -2147024809;
      goto LABEL_92;
    }
    v6 = lpVerb_low - v14;
    v40 = v6;
LABEL_28:
    memset_0(&Src, 0, sizeof(Src));
    CopyInvokeInfo(&Src, a2);
    if ( a2->lpVerb >= (LPCSTR)0x10000 )
    {
      lpVerb = (LPSTREAM *)Src.lpVerb;
    }
    else
    {
      lpVerb = (LPSTREAM *)(unsigned __int16)v6;
      Src.lpVerb = (LPCSTR)(unsigned __int16)v6;
    }
    v18 = v11 == *((_DWORD *)this + 44);
    ppStm = 0;
    *((_BYTE *)this + 180) = v18;
    LOBYTE(v16) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppSiloFileExplorerContextMenus>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_AppSiloFileExplorerContextMenus>::GetImpl'::`2'::impl,
      v16);
    CDefFolderMenu::BrokerFilesForAppSiloVerb((CDefFolderMenu *)((char *)this - 16), &Src);
    v19 = (struct _DSA *)*((_QWORD *)this + 23);
    v38 = 0;
    v2 = HDXA_LetHandlerProcessCommandEx(v19, &Src);
    if ( v2 < 0 || ppStm != lpVerb )
      goto LABEL_92;
    goto LABEL_91;
  }
  if ( SHMapICIVerbToCmdID(a2, (const struct ICIVERBTOIDMAP *)&off_1805B8830, &v40) < 0 )
  {
    GetAnsiOrUnicodeParam(v6, (const unsigned __int16 *)a2[1].hwnd, a2->lpVerb, (unsigned __int16 *)&Src, 0x40u);
    LOWORD(v6) = -1;
    v40 = -1;
    if ( LOWORD(Src.cbSize) )
    {
      if ( (*(int (__fastcall **)(_QWORD, _QWORD, HWND, _QWORD, int, unsigned int *, _CMINVOKECOMMANDINFOEX *))(**((_QWORD **)this + 13) + 24LL))(
             *((_QWORD *)this + 13),
             *((_QWORD *)this + 17),
             v9,
             *((_QWORD *)this + 14),
             13,
             &v40,
             &Src) >= 0 )
        goto LABEL_36;
      LOWORD(v6) = v40;
    }
    v11 = -1;
    goto LABEL_28;
  }
  if ( (*((_BYTE *)this + 1288) & 2) != 0 )
    goto LABEL_15;
  v2 = DCMIDMtoDFM(v40, &v40);
LABEL_36:
  if ( (*((_BYTE *)this + 1340) & 0x20) != 0 )
  {
    for ( i = 0; (unsigned int)i < 8; i = (unsigned int)(i + 1) )
    {
      if ( v40 == LODWORD(qword_180632C60[i]) )
        goto LABEL_92;
    }
  }
  AnsiOrUnicodeParam = (unsigned __int16 *)GetAnsiOrUnicodeParam(
                                             v38,
                                             (const unsigned __int16 *)a2[1].lpVerb,
                                             a2->lpParameters,
                                             v50,
                                             0x104u);
  ppStm = (LPSTREAM *)AnsiOrUnicodeParam;
  if ( v40 == -5 )
  {
    if ( SHRestricted(REST_NOVIEWCONTEXTMENU) )
      goto LABEL_92;
    v22 = ppStm;
  }
  else
  {
    if ( v40 == -4 )
      AnsiOrUnicodeParam = (unsigned __int16 *)GetAnsiOrUnicodeParam(
                                                 v38,
                                                 (const unsigned __int16 *)a2[1].lpParameters,
                                                 a2->lpDirectory,
                                                 v50,
                                                 0x104u);
    v22 = (LPSTREAM *)AnsiOrUnicodeParam;
  }
  fMask = a2->fMask;
  v45 = *((_DWORD *)this + 38);
  v46 = *((_DWORD *)this + 40);
  v48 = *((_QWORD *)this - 1);
  v42 = 40;
  v43 = fMask;
  v44 = v22;
  v47 = a2;
  if ( (fMask & 0x20000000) != 0 )
  {
    v24 = (struct IDataObject *)*((_QWORD *)this + 14);
    if ( v24 )
    {
      ppStm = *(LPSTREAM **)&a2[1].nShow;
      DataObj_SetBlobWithIndex(v24, g_cfOFFSETS_Storage, &ppStm, 8u, v35);
    }
  }
  IUnknown_SetSite(*((IUnknown **)this + 13), *((IUnknown **)this - 1));
  if ( (SHGetObjectCompatFlags(*((_QWORD *)this + 17), 0) & 0x4000) != 0 )
    AllowSetForegroundWindow(0xFFFFFFFF);
  v36 = 12;
  v2 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, HWND, _QWORD))(**((_QWORD **)this + 13) + 24LL))(
         *((_QWORD *)this + 13),
         *((_QWORD *)this + 17),
         v9,
         *((_QWORD *)this + 14));
  if ( v2 == -2147467263 )
  {
    v36 = 2;
    v2 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, HWND, _QWORD))(**((_QWORD **)this + 13) + 24LL))(
           *((_QWORD *)this + 13),
           *((_QWORD *)this + 17),
           v9,
           *((_QWORD *)this + 14));
  }
  IUnknown_SetSite(*((IUnknown **)this + 13), 0);
  if ( v2 != 1 )
    goto LABEL_92;
  v2 = 0;
  if ( !*((_QWORD *)this + 14) )
  {
    if ( v40 != -10 && v40 != -7 )
      goto LABEL_92;
LABEL_90:
    v10 = CDefFolderMenu::_ProcessEditPaste((CDefFolderMenu *)((char *)this - 16), *v8, v40 == -10);
    goto LABEL_11;
  }
  switch ( v40 )
  {
    case 0xFFFFFFF3:
      v10 = CDefFolderMenu::_ProcessRename((CDefFolderMenu *)((char *)this - 16));
      goto LABEL_11;
    case 0xFFFFFFF6:
    case 0xFFFFFFF9:
      goto LABEL_90;
    case 0xFFFFFFFB:
      Fire_ExplorerTelemetryFromSiteWithDataObject(*((_QWORD *)this - 1), 12384);
      if ( CDefFolderMenu::_AttributesOfItems((CDefFolderMenu *)((char *)this - 16), 0x40u) )
      {
        v10 = SHLaunchPropSheet(*((_QWORD *)this + 14), v44, &CLSID_ShellFileDefExt);
        goto LABEL_11;
      }
LABEL_15:
      v2 = -2147467259;
      goto LABEL_92;
    case 0xFFFFFFFC:
      v10 = CDefFolderMenu::_ProcessLink(
              (CDefFolderMenu *)((char *)this - 16),
              a2->hwnd,
              (const unsigned __int16 *)v22,
              a2->fMask);
      goto LABEL_11;
  }
  if ( v40 + 3 <= 1 )
  {
    v29 = 12322;
    if ( v40 != -2 )
      v29 = 12323;
    Fire_ExplorerTelemetryFromSiteWithDataObject(*((_QWORD *)this - 1), v29);
    v30 = 5;
    if ( v40 == -2 )
      v30 = 2;
    v31 = (struct IDataObject *)*((_QWORD *)this + 14);
    v38 = v30;
    DataObj_SetBlobWithIndex(v31, (unsigned __int16)word_1806F941C, &v38, 4u, v36);
    if ( (unsigned int)DataObj_CanGoAsyncAndStartOpIfSo(*((struct IDataObject **)this + 14)) )
    {
      v32 = (struct IDataObject *)*((_QWORD *)this + 14);
      v38 = 1;
      DataObj_SetBlobWithIndex(v32, (unsigned __int16)word_1806F9440, &v38, 4u, v37);
    }
    v33 = (struct IUnknown *)*((_QWORD *)this - 1);
    ppStm = 0;
    if ( (int)IUnknown_ServiceExists(v33, (const struct _GUID *)&SID_SiteWhereCommandsAffectView) >= 0
      && IUnknown_QueryService(
           *((IUnknown **)this - 1),
           &IID_IFolderView,
           &GUID_37a378c0_f82d_11ce_ae65_08002b2e1262,
           (void **)&ppStm) >= 0 )
    {
      ((void (__fastcall *)(LPSTREAM *, _QWORD))(*ppStm)[25].lpVtbl)(ppStm, *((_QWORD *)this + 14));
    }
    OleSetClipboard(*((LPDATAOBJECT *)this + 14));
    if ( ppStm )
    {
      ((void (__fastcall *)(LPSTREAM *, bool))(*ppStm)[24].lpVtbl)(ppStm, v40 == -2);
      ((void (__fastcall *)(LPSTREAM *))(*ppStm)[2].lpVtbl)(ppStm);
    }
  }
  else
  {
    if ( v40 != -1 )
      goto LABEL_92;
    Fire_ExplorerTelemetryFromSiteWithDataObject(*((_QWORD *)this - 1), 12352);
    v25 = v43;
    if ( (v43 & 0x100000) == 0 )
      goto LABEL_70;
    if ( !(unsigned int)DataObj_CanGoAsyncAndStartOpIfSo(*((struct IDataObject **)this + 14))
      || (ppStm = 0, CTLocalAllocPolicy::Alloc(v26, 0x40u, 0x20u, (void **)&ppStm) < 0) )
    {
LABEL_69:
      v25 = v43;
LABEL_70:
      v10 = DeleteItemsInDataObject(v9, v25, *((_QWORD *)this - 1), *((_QWORD *)this + 14));
      goto LABEL_11;
    }
    v27 = ppStm;
    v2 = CoMarshalInterThreadInterfaceInStream(&IID_IDataObject, *((LPUNKNOWN *)this + 14), ppStm);
    if ( v2 < 0
      || (v28 = (IUnknown *)*((_QWORD *)this - 1)) != 0
      && (v2 = CoMarshalInterThreadInterfaceInStream(&IID_IUnknown, v28, v27 + 1), v2 < 0)
      || (v27[2] = (LPSTREAM)v9, *((_DWORD *)v27 + 6) = v43, !SHCreateThread(DeleteItemsThreadProc, v27, 8u, 0)) )
    {
      SafeReleaseMarshalInterface(v27);
      SafeReleaseMarshalInterface(v27 + 1);
      LocalFree(v27);
      goto LABEL_69;
    }
  }
LABEL_92:
  SetAppStartingCursor(v39, 0);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1802834f0  mov     [rsp-8+arg_10], rbx
0x1802834f5  push    rbp
0x1802834f6  push    rsi
0x1802834f7  push    rdi
0x1802834f8  push    r12
0x1802834fa  push    r13
0x1802834fc  push    r14
0x1802834fe  push    r15
0x180283500  lea     rbp, [rsp-230h]
0x180283508  sub     rsp, 330h
0x18028350f  mov     rax, cs:__security_cookie
0x180283516  xor     rax, rsp
0x180283519  mov     [rbp+260h+var_40], rax
0x180283520  xor     ebx, ebx
0x180283522  mov     rdi, rcx
0x180283525  cmp     dword ptr [rdx], 60h ; '`'
0x180283528  mov     rsi, rdx
0x18028352b  mov     [rsp+360h+var_310], ebx
0x18028352f  lea     ecx, [rbx+1]
0x180283532  jb      short loc_180283540
0x180283534  test    dword ptr [rdx+4], 4000h
0x18028353b  mov     r14d, ecx
0x18028353e  jnz     short loc_180283543
0x180283540  mov     r14d, ebx
0x180283543  mov     rax, [rdx+8]
0x180283547  lea     r13, [rdi+90h]
0x18028354e  mov     [rsp+360h+var_320], r14d
0x180283553  mov     r12, rax
0x180283556  test    rax, rax
0x180283559  jnz     short loc_18028355F
0x18028355b  mov     r12, [r13+0]
0x18028355f  lea     r15, [rdi-10h]
0x180283563  mov     [rsp+360h+var_318], r12
0x180283568  cmp     [r15+0A0h], rbx
0x18028356f  jnz     short loc_180283575
0x180283571  mov     [r13+0], rax
0x180283575  mov     edx, ecx
0x180283577  mov     rcx, r12
0x18028357a  call    cs:__imp_SetAppStartingCursor
0x180283581  nop     dword ptr [rax+rax+00h]
0x180283586  cmp     dword ptr [rsi], 38h ; '8'
0x180283589  jb      loc_180283C94
0x18028358f  cmp     [rdi+80h], ebx
0x180283595  jz      short loc_1802835AF
0x180283597  mov     r8d, 1
0x18028359d  mov     rdx, rsi
0x1802835a0  mov     rcx, r15
0x1802835a3  call    ?_HandlePartialSelectionInvoke@CDefFolderMenu@@AEAAJPEAU_CMINVOKECOMMANDINFO@@W4SELECTIONFLAG@1@@Z; CDefFolderMenu::_HandlePartialSelectionInvoke(_CMINVOKECOMMANDINFO *,CDefFolderMenu::SELECTIONFLAG)
0x1802835a8  mov     ebx, eax
0x1802835aa  jmp     loc_180283C99
0x1802835af  cmp     qword ptr [rsi+10h], 10000h
0x1802835b7  jb      loc_180283676
0x1802835bd  lea     r8, [rsp+360h+var_310]; unsigned int *
0x1802835c2  mov     rcx, rsi; struct _CMINVOKECOMMANDINFO *
0x1802835c5  lea     rdx, off_1805B8830; struct ICIVERBTOIDMAP *
0x1802835cc  call    ?SHMapICIVerbToCmdID@@YAJPEAU_CMINVOKECOMMANDINFO@@PEBUICIVERBTOIDMAP@@PEAI@Z; SHMapICIVerbToCmdID(_CMINVOKECOMMANDINFO *,ICIVERBTOIDMAP const *,uint *)
0x1802835d1  test    eax, eax
0x1802835d3  js      short loc_1802835FD
0x1802835d5  test    byte ptr [rdi+508h], 2
0x1802835dc  jz      short loc_1802835E8
0x1802835de  mov     ebx, 80004005h
0x1802835e3  jmp     loc_180283C99
0x1802835e8  mov     ecx, [rsp+360h+var_310]; unsigned int
0x1802835ec  lea     rdx, [rsp+360h+var_310]; unsigned int *
0x1802835f1  call    ?DCMIDMtoDFM@@YAJIPEAI@Z; DCMIDMtoDFM(uint,uint *)
0x1802835f6  mov     ebx, eax
0x1802835f8  jmp     loc_18028379F
0x1802835fd  mov     r8, [rsi+10h]; char *
0x180283601  lea     r9, [rbp+260h+Src]; unsigned __int16 *
0x180283605  mov     rdx, [rsi+40h]; unsigned __int16 *
0x180283609  mov     ecx, r14d; int
0x18028360c  mov     [rsp+360h+var_340], 40h ; '@'; unsigned int
0x180283614  call    ?GetAnsiOrUnicodeParam@@YAPEBGHPEBGPEBDPEAGI@Z; GetAnsiOrUnicodeParam(int,ushort const *,char const *,ushort *,uint)
0x180283619  or      r14d, 0FFFFFFFFh
0x18028361d  xor     ecx, ecx
0x18028361f  mov     [rsp+360h+var_310], r14d
0x180283624  cmp     word ptr [rbp+260h+Src.cbSize], cx
0x180283628  jz      short loc_180283670
0x18028362a  mov     rcx, [rdi+68h]
0x18028362e  lea     rdx, [rbp+260h+Src]
0x180283632  mov     r9, [rdi+70h]
0x180283636  mov     r8, r12
0x180283639  mov     [rsp+360h+var_330], rdx
0x18028363e  lea     rdx, [rsp+360h+var_310]
0x180283643  mov     [rsp+360h+var_338], rdx
0x180283648  mov     rax, [rcx]
0x18028364b  mov     rdx, [rdi+88h]
0x180283652  mov     [rsp+360h+var_340], 0Dh
0x18028365a  mov     rax, [rax+18h]
0x18028365e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180283663  test    eax, eax
0x180283665  jns     loc_18028379F
0x18028366b  mov     r14d, [rsp+360h+var_310]
0x180283670  or      r12d, 0FFFFFFFFh
0x180283674  jmp     short loc_1802836D4
0x180283676  movzx   r14d, word ptr [rsi+10h]
0x18028367b  mov     ecx, [rdi+0A0h]
0x180283681  cmp     r14d, ecx
0x180283684  jnb     short loc_1802836A2
0x180283686  lea     rdx, [rsp+360h+var_310]; unsigned int *
0x18028368b  mov     ecx, r14d; unsigned int
0x18028368e  call    ?DCMIDMtoDFM@@YAJIPEAI@Z; DCMIDMtoDFM(uint,uint *)
0x180283693  mov     ebx, eax
0x180283695  test    eax, eax
0x180283697  js      loc_180283C99
0x18028369d  jmp     loc_18028379F
0x1802836a2  mov     eax, [rdi+0A4h]
0x1802836a8  cmp     r14d, eax
0x1802836ab  jnb     short loc_1802836BA
0x1802836ad  sub     r14d, ecx
0x1802836b0  mov     [rsp+360h+var_310], r14d
0x1802836b5  jmp     loc_18028379F
0x1802836ba  mov     ecx, [rdi+0A8h]
0x1802836c0  mov     r12d, r14d
0x1802836c3  cmp     r14d, ecx
0x1802836c6  jnb     loc_180283785
0x1802836cc  sub     r14d, eax
0x1802836cf  mov     [rsp+360h+var_310], r14d
0x1802836d4  xor     edx, edx; Val
0x1802836d6  lea     rcx, [rbp+260h+Src]; void *
0x1802836da  lea     r8d, [rdx+68h]; Size
0x1802836de  call    memset_0
0x1802836e3  mov     rdx, rsi; Src
0x1802836e6  lea     rcx, [rbp+260h+Src]; struct _CMINVOKECOMMANDINFOEX *
0x1802836ea  call    ?CopyInvokeInfo@@YAXPEAU_CMINVOKECOMMANDINFOEX@@PEBU_CMINVOKECOMMANDINFO@@@Z; CopyInvokeInfo(_CMINVOKECOMMANDINFOEX *,_CMINVOKECOMMANDINFO const *)
0x1802836ef  cmp     qword ptr [rsi+10h], 10000h
0x1802836f7  jnb     short loc_180283703
0x1802836f9  movzx   esi, r14w
0x1802836fd  mov     [rbp+260h+Src.lpVerb], rsi
0x180283701  jmp     short loc_180283707
0x180283703  mov     rsi, [rbp+260h+Src.lpVerb]
0x180283707  xor     r14d, r14d
0x18028370a  cmp     r12d, [rdi+0B0h]
0x180283711  mov     [rsp+360h+ppStm], r14
0x180283716  setz    al
0x180283719  mov     [rdi+0B4h], al
0x18028371f  mov     dl, 1
0x180283721  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AppSiloFileExplorerContextMenus@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AppSiloFileExplorerContextMenus@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppSiloFileExplorerContextMenus> `wil::Feature<__WilFeatureTraits_Feature_AppSiloFileExplorerContextMenus>::GetImpl(void)'::`2'::impl
0x180283728  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_AppSiloFileExplorerContextMenus@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppSiloFileExplorerContextMenus>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18028372d  lea     rdx, [rbp+260h+Src]; struct _CMINVOKECOMMANDINFOEX *
0x180283731  mov     rcx, r15; this
0x180283734  call    ?BrokerFilesForAppSiloVerb@CDefFolderMenu@@AEAAJAEBU_CMINVOKECOMMANDINFOEX@@@Z; CDefFolderMenu::BrokerFilesForAppSiloVerb(_CMINVOKECOMMANDINFOEX const &)
0x180283739  mov     rcx, [rdi+0B8h]; hdsa
0x180283740  lea     r9, [rsp+360h+var_320]
0x180283745  lea     r8, [rsp+360h+ppStm]
0x18028374a  mov     [rsp+360h+var_320], r14d
0x18028374f  lea     rdx, [rbp+260h+Src]; Src
0x180283753  call    HDXA_LetHandlerProcessCommandEx
0x180283758  mov     ebx, eax
0x18028375a  test    eax, eax
0x18028375c  js      loc_180283C99
0x180283762  cmp     [rsp+360h+ppStm], rsi
0x180283767  jz      loc_180283C94
0x18028376d  cmp     [rsp+360h+var_320], r14d
0x180283772  jz      loc_180283C99
0x180283778  mov     rcx, r15; this
0x18028377b  call    ?_AddToRecentDocs@CDefFolderMenu@@AEAAXXZ; CDefFolderMenu::_AddToRecentDocs(void)
0x180283780  jmp     loc_180283C99
0x180283785  cmp     r12d, [rdi+0ACh]
0x18028378c  jnb     loc_180283C94
0x180283792  sub     r12d, ecx
0x180283795  mov     [rsp+360h+var_310], r12d
0x18028379a  mov     r12, [rsp+360h+var_318]
0x18028379f  test    byte ptr [rdi+53Ch], 20h
0x1802837a6  jz      short loc_1802837C7
0x1802837a8  xor     ecx, ecx
0x1802837aa  cmp     ecx, 8
0x1802837ad  jnb     short loc_1802837C7
0x1802837af  lea     rdx, qword_180632C60
0x1802837b6  mov     eax, [rdx+rcx*8]
0x1802837b9  cmp     [rsp+360h+var_310], eax
0x1802837bd  jz      loc_180283C99
0x1802837c3  inc     ecx
0x1802837c5  jmp     short loc_1802837AA
0x1802837c7  mov     r14d, [rsp+360h+var_320]
0x1802837cc  lea     r9, [rbp+260h+var_250]; unsigned __int16 *
0x1802837d0  mov     r8, [rsi+18h]; char *
0x1802837d4  mov     ecx, r14d; int
0x1802837d7  mov     rdx, [rsi+48h]; unsigned __int16 *
0x1802837db  mov     [rsp+360h+var_340], 104h; unsigned int
0x1802837e3  call    ?GetAnsiOrUnicodeParam@@YAPEBGHPEBGPEBDPEAGI@Z; GetAnsiOrUnicodeParam(int,ushort const *,char const *,ushort *,uint)
0x1802837e8  cmp     [rsp+360h+var_310], 0FFFFFFFBh
0x1802837ed  mov     [rsp+360h+ppStm], rax
0x1802837f2  jz      loc_180283AC5
0x1802837f8  cmp     [rsp+360h+var_310], 0FFFFFFFCh
0x1802837fd  jnz     short loc_18028381B
0x1802837ff  mov     r8, [rsi+20h]; char *
0x180283803  lea     r9, [rbp+260h+var_250]; unsigned __int16 *
0x180283807  mov     rdx, [rsi+50h]; unsigned __int16 *
0x18028380b  mov     ecx, r14d; int
0x18028380e  mov     [rsp+360h+var_340], 104h; int
0x180283816  call    ?GetAnsiOrUnicodeParam@@YAPEBGHPEBGPEBDPEAGI@Z; GetAnsiOrUnicodeParam(int,ushort const *,char const *,ushort *,uint)
0x18028381b  mov     r14, rax
0x18028381e  mov     eax, [rdi+98h]
0x180283824  mov     ecx, [rsi+4]
0x180283827  mov     [rsp+360h+var_2F0], eax
0x18028382b  mov     eax, [rdi+0A0h]
0x180283831  mov     [rsp+360h+var_2EC], eax
0x180283835  mov     rax, [rdi-8]
0x180283839  mov     [rbp+260h+var_2E0], rax
0x18028383d  mov     [rsp+360h+var_300], 28h ; '('
0x180283845  mov     [rsp+360h+var_2FC], ecx
0x180283849  mov     [rsp+360h+var_2F8], r14
0x18028384e  mov     [rsp+360h+var_2E8], rsi
0x180283853  bt      ecx, 1Dh
0x180283857  jnb     short loc_180283882
0x180283859  mov     rcx, [rdi+70h]; struct IDataObject *
0x18028385d  test    rcx, rcx
0x180283860  jz      short loc_180283882
0x180283862  mov     rax, [rsi+60h]
0x180283866  lea     r8, [rsp+360h+ppStm]; void *
0x18028386b  movzx   edx, cs:?g_cfOFFSETS_Storage@@3GA; unsigned int
0x180283872  mov     r9d, 8; unsigned int
0x180283878  mov     [rsp+360h+ppStm], rax
0x18028387d  call    ?DataObj_SetBlobWithIndex@@YAJPEAUIDataObject@@IPEBXIJ@Z; DataObj_SetBlobWithIndex(IDataObject *,uint,void const *,uint,long)
0x180283882  mov     rdx, [rdi-8]; punkSite
0x180283886  mov     rcx, [rdi+68h]; punk
0x18028388a  call    cs:__imp_IUnknown_SetSite
0x180283891  nop     dword ptr [rax+rax+00h]
0x180283896  mov     rcx, [rdi+88h]
0x18028389d  xor     edx, edx
0x18028389f  call    cs:__imp_SHGetObjectCompatFlags
0x1802838a6  nop     dword ptr [rax+rax+00h]
0x1802838ab  bt      eax, 0Eh
0x1802838af  jnb     short loc_1802838C0
0x1802838b1  or      ecx, 0FFFFFFFFh; dwProcessId
0x1802838b4  call    cs:__imp_AllowSetForegroundWindow
0x1802838bb  nop     dword ptr [rax+rax+00h]
0x1802838c0  mov     edx, [rsp+360h+var_310]
0x1802838c4  lea     r8, [rsp+360h+var_300]
0x1802838c9  mov     rcx, [rdi+68h]
0x1802838cd  mov     r9, [rdi+70h]
0x1802838d1  mov     [rsp+360h+var_330], r8
0x1802838d6  mov     r8, r12
0x1802838d9  mov     [rsp+360h+var_338], rdx
0x1802838de  mov     rax, [rcx]
0x1802838e1  mov     rdx, [rdi+88h]
0x1802838e8  mov     [rsp+360h+var_340], 0Ch
0x1802838f0  mov     rax, [rax+18h]
0x1802838f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802838f9  mov     ebx, eax
0x1802838fb  cmp     eax, 80004001h
0x180283900  jnz     short loc_180283938
0x180283902  mov     edx, [rsp+360h+var_310]
0x180283906  mov     r8, r12
0x180283909  mov     rcx, [rdi+68h]
0x18028390d  mov     r9, [rdi+70h]
0x180283911  mov     [rsp+360h+var_330], r14
0x180283916  mov     [rsp+360h+var_338], rdx
0x18028391b  mov     rax, [rcx]
0x18028391e  mov     rdx, [rdi+88h]
0x180283925  mov     [rsp+360h+var_340], 2; int
0x18028392d  mov     rax, [rax+18h]
0x180283931  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180283936  mov     ebx, eax
0x180283938  mov     rcx, [rdi+68h]; punk
0x18028393c  xor     edx, edx; punkSite
0x18028393e  call    cs:__imp_IUnknown_SetSite
0x180283945  nop     dword ptr [rax+rax+00h]
0x18028394a  cmp     ebx, 1
0x18028394d  jnz     loc_180283C99
0x180283953  mov     r9, [rdi+70h]
0x180283957  xor     edx, edx
0x180283959  mov     ecx, [rsp+360h+var_310]
0x18028395d  mov     ebx, edx
0x18028395f  test    r9, r9
0x180283962  jz      loc_180283C6C
0x180283968  cmp     ecx, 0FFFFFFF3h
0x18028396b  jz      loc_180283C5F
0x180283971  mov     eax, 0FFFFFFF6h
0x180283976  cmp     ecx, eax
0x180283978  jz      loc_180283C7A
0x18028397e  cmp     ecx, 0FFFFFFF9h
0x180283981  jz      loc_180283C7A
0x180283987  cmp     ecx, 0FFFFFFFBh
0x18028398a  jz      loc_180283C22
0x180283990  cmp     ecx, 0FFFFFFFCh
0x180283993  jz      loc_180283C0A
0x180283999  lea     eax, [rcx+3]
0x18028399c  cmp     eax, 1
0x18028399f  jbe     loc_180283AE8
0x1802839a5  cmp     ecx, 0FFFFFFFFh
0x1802839a8  jnz     loc_180283C99
0x1802839ae  mov     rcx, [rdi-8]
0x1802839b2  mov     edx, 3040h
0x1802839b7  call    ?Fire_ExplorerTelemetryFromSiteWithDataObject@@YAXPEAUIUnknown@@W4EXPLORER_COMMAND_SQM_ID@@W4EXPLORER_COMMAND_SQM_SELECTED_STATE@@PEAUIDataObject@@@Z; Fire_ExplorerTelemetryFromSiteWithDataObject(IUnknown *,EXPLORER_COMMAND_SQM_ID,EXPLORER_COMMAND_SQM_SELECTED_STATE,IDataObject *)
0x1802839bc  mov     edx, [rsp+360h+var_2FC]
0x1802839c0  bt      edx, 14h
0x1802839c4  jnb     loc_180283AA9
0x1802839ca  mov     rcx, [rdi+70h]; struct IDataObject *
0x1802839ce  call    DataObj_CanGoAsyncAndStartOpIfSo
0x1802839d3  xor     r14d, r14d
0x1802839d6  test    eax, eax
0x1802839d8  jz      loc_180283AA5
0x1802839de  lea     r9, [rsp+360h+ppStm]; void **
0x1802839e3  mov     [rsp+360h+ppStm], r14
0x1802839e8  lea     edx, [r14+40h]; unsigned int
0x1802839ec  lea     r8d, [r14+20h]; unsigned __int64
0x1802839f0  call    ?Alloc@CTLocalAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTLocalAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x1802839f5  test    eax, eax
  ... truncated ...
```
