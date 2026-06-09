# CDefFolderMenu::InvokeCommand(_CMINVOKECOMMANDINFO *)

- ea: `0x18026ac20`
- end: `0x18026b3b4`
- name: `?InvokeCommand@CDefFolderMenu@@UEAAJPEAU_CMINVOKECOMMANDINFO@@@Z`
- size: `1940`
- prototype: `int(CDefFolderMenu *__hidden this, struct _CMINVOKECOMMANDINFO *)`
- caller_count: `0`
- callee_count: `24`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180078dcc`
- `0x1800aadec`
- `0x1800d6b7c`
- `0x180113fc8`
- `0x18011adf4`
- `0x180123afc`
- `0x18012aab0`
- `0x18014b4a0`
- `0x1801677c4`
- `0x18016f224`
- `0x18016fb6c`
- `0x1801723f0`
- `0x1801c54b4`
- `0x1801d2d24`
- `0x180233280`
- `0x1802342fc`
- `0x180265e14`
- `0x18026ac20`
- `0x18026dcc0`
- `0x18026e9f4`
- `0x18026eeb8`
- `0x18026f0a0`
- `0x18026f100`
- `0x180571010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18026b191`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18026b191`
- `USER32!AllowSetForegroundWindow` at `0x18026afd2`
- `USER32!AllowSetForegroundWindow` at `0x18026afd2`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x18026b122`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x18026b142`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x18026b122`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x18026b142`
- `api-ms-win-shcore-thread-l1-1-0!SHCreateThread` at `0x18026b16a`
- `api-ms-win-shcore-thread-l1-1-0!SHCreateThread` at `0x18026b16a`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x18026b283`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x18026b283`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_SetSite` at `0x18026afb4`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_SetSite` at `0x18026b056`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_SetSite` at `0x18026afb4`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_SetSite` at `0x18026b056`
- `SHCORE!__imp_SHGetObjectCompatFlags` at `0x18026afc3`
- `SHCORE!__imp_SHGetObjectCompatFlags` at `0x18026afc3`
- `ext-ms-win-com-ole32-l1-1-5!OleSetClipboard` at `0x18026b2a9`
- `ext-ms-win-com-ole32-l1-1-5!OleSetClipboard` at `0x18026b2a9`
- `Windows.Storage!DeleteItemsInDataObject` at `0x18026b1ae`
- `Windows.Storage!DeleteItemsInDataObject` at `0x18026b1ae`
- `Windows.Storage!SetAppStartingCursor` at `0x18026acaa`
- `Windows.Storage!SetAppStartingCursor` at `0x18026b382`
- `Windows.Storage!SetAppStartingCursor` at `0x18026acaa`
- `Windows.Storage!SetAppStartingCursor` at `0x18026b382`
- `Windows.Storage!__imp_SHRestricted` at `0x18026b1be`
- `Windows.Storage!__imp_SHRestricted` at `0x18026b1be`

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
  if ( SHMapICIVerbToCmdID(a2, (const struct ICIVERBTOIDMAP *)&off_180577290, &v40) < 0 )
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
      if ( v40 == LODWORD(qword_1805F20B0[i]) )
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
    DataObj_SetBlobWithIndex(v31, (unsigned __int16)word_1806B845C, &v38, 4u, v36);
    if ( (unsigned int)DataObj_CanGoAsyncAndStartOpIfSo(*((struct IDataObject **)this + 14)) )
    {
      v32 = (struct IDataObject *)*((_QWORD *)this + 14);
      v38 = 1;
      DataObj_SetBlobWithIndex(v32, (unsigned __int16)word_1806B8480, &v38, 4u, v37);
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
0x18026ac20  mov     [rsp-8+arg_10], rbx
0x18026ac25  push    rbp
0x18026ac26  push    rsi
0x18026ac27  push    rdi
0x18026ac28  push    r12
0x18026ac2a  push    r13
0x18026ac2c  push    r14
0x18026ac2e  push    r15
0x18026ac30  lea     rbp, [rsp-230h]
0x18026ac38  sub     rsp, 330h
0x18026ac3f  mov     rax, cs:__security_cookie
0x18026ac46  xor     rax, rsp
0x18026ac49  mov     [rbp+260h+var_40], rax
0x18026ac50  xor     ebx, ebx
0x18026ac52  mov     rdi, rcx
0x18026ac55  cmp     dword ptr [rdx], 60h ; '`'
0x18026ac58  mov     rsi, rdx
0x18026ac5b  mov     [rsp+360h+var_310], ebx
0x18026ac5f  lea     ecx, [rbx+1]
0x18026ac62  jb      short loc_18026AC70
0x18026ac64  test    dword ptr [rdx+4], 4000h
0x18026ac6b  mov     r14d, ecx
0x18026ac6e  jnz     short loc_18026AC73
0x18026ac70  mov     r14d, ebx
0x18026ac73  mov     rax, [rdx+8]
0x18026ac77  lea     r13, [rdi+90h]
0x18026ac7e  mov     [rsp+360h+var_320], r14d
0x18026ac83  mov     r12, rax
0x18026ac86  test    rax, rax
0x18026ac89  jnz     short loc_18026AC8F
0x18026ac8b  mov     r12, [r13+0]
0x18026ac8f  lea     r15, [rdi-10h]
0x18026ac93  mov     [rsp+360h+var_318], r12
0x18026ac98  cmp     [r15+0A0h], rbx
0x18026ac9f  jnz     short loc_18026ACA5
0x18026aca1  mov     [r13+0], rax
0x18026aca5  mov     edx, ecx
0x18026aca7  mov     rcx, r12
0x18026acaa  call    cs:__imp_SetAppStartingCursor
0x18026acb0  cmp     dword ptr [rsi], 38h ; '8'
0x18026acb3  jb      loc_18026B376
0x18026acb9  cmp     [rdi+80h], ebx
0x18026acbf  jz      short loc_18026ACD9
0x18026acc1  mov     r8d, 1
0x18026acc7  mov     rdx, rsi
0x18026acca  mov     rcx, r15
0x18026accd  call    ?_HandlePartialSelectionInvoke@CDefFolderMenu@@AEAAJPEAU_CMINVOKECOMMANDINFO@@W4SELECTIONFLAG@1@@Z; CDefFolderMenu::_HandlePartialSelectionInvoke(_CMINVOKECOMMANDINFO *,CDefFolderMenu::SELECTIONFLAG)
0x18026acd2  mov     ebx, eax
0x18026acd4  jmp     loc_18026B37B
0x18026acd9  cmp     qword ptr [rsi+10h], 10000h
0x18026ace1  jb      loc_18026ADA0
0x18026ace7  lea     r8, [rsp+360h+var_310]; unsigned int *
0x18026acec  mov     rcx, rsi; struct _CMINVOKECOMMANDINFO *
0x18026acef  lea     rdx, off_180577290; struct ICIVERBTOIDMAP *
0x18026acf6  call    ?SHMapICIVerbToCmdID@@YAJPEAU_CMINVOKECOMMANDINFO@@PEBUICIVERBTOIDMAP@@PEAI@Z; SHMapICIVerbToCmdID(_CMINVOKECOMMANDINFO *,ICIVERBTOIDMAP const *,uint *)
0x18026acfb  test    eax, eax
0x18026acfd  js      short loc_18026AD27
0x18026acff  test    byte ptr [rdi+508h], 2
0x18026ad06  jz      short loc_18026AD12
0x18026ad08  mov     ebx, 80004005h
0x18026ad0d  jmp     loc_18026B37B
0x18026ad12  mov     ecx, [rsp+360h+var_310]; unsigned int
0x18026ad16  lea     rdx, [rsp+360h+var_310]; unsigned int *
0x18026ad1b  call    ?DCMIDMtoDFM@@YAJIPEAI@Z; DCMIDMtoDFM(uint,uint *)
0x18026ad20  mov     ebx, eax
0x18026ad22  jmp     loc_18026AEC9
0x18026ad27  mov     r8, [rsi+10h]; char *
0x18026ad2b  lea     r9, [rbp+260h+Src]; unsigned __int16 *
0x18026ad2f  mov     rdx, [rsi+40h]; unsigned __int16 *
0x18026ad33  mov     ecx, r14d; int
0x18026ad36  mov     [rsp+360h+var_340], 40h ; '@'; unsigned int
0x18026ad3e  call    ?GetAnsiOrUnicodeParam@@YAPEBGHPEBGPEBDPEAGI@Z; GetAnsiOrUnicodeParam(int,ushort const *,char const *,ushort *,uint)
0x18026ad43  or      r14d, 0FFFFFFFFh
0x18026ad47  xor     ecx, ecx
0x18026ad49  mov     [rsp+360h+var_310], r14d
0x18026ad4e  cmp     word ptr [rbp+260h+Src.cbSize], cx
0x18026ad52  jz      short loc_18026AD9A
0x18026ad54  mov     rcx, [rdi+68h]
0x18026ad58  lea     rdx, [rbp+260h+Src]
0x18026ad5c  mov     r9, [rdi+70h]
0x18026ad60  mov     r8, r12
0x18026ad63  mov     [rsp+360h+var_330], rdx
0x18026ad68  lea     rdx, [rsp+360h+var_310]
0x18026ad6d  mov     [rsp+360h+var_338], rdx
0x18026ad72  mov     rax, [rcx]
0x18026ad75  mov     rdx, [rdi+88h]
0x18026ad7c  mov     [rsp+360h+var_340], 0Dh
0x18026ad84  mov     rax, [rax+18h]
0x18026ad88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026ad8d  test    eax, eax
0x18026ad8f  jns     loc_18026AEC9
0x18026ad95  mov     r14d, [rsp+360h+var_310]
0x18026ad9a  or      r12d, 0FFFFFFFFh
0x18026ad9e  jmp     short loc_18026ADFE
0x18026ada0  movzx   r14d, word ptr [rsi+10h]
0x18026ada5  mov     ecx, [rdi+0A0h]
0x18026adab  cmp     r14d, ecx
0x18026adae  jnb     short loc_18026ADCC
0x18026adb0  lea     rdx, [rsp+360h+var_310]; unsigned int *
0x18026adb5  mov     ecx, r14d; unsigned int
0x18026adb8  call    ?DCMIDMtoDFM@@YAJIPEAI@Z; DCMIDMtoDFM(uint,uint *)
0x18026adbd  mov     ebx, eax
0x18026adbf  test    eax, eax
0x18026adc1  js      loc_18026B37B
0x18026adc7  jmp     loc_18026AEC9
0x18026adcc  mov     eax, [rdi+0A4h]
0x18026add2  cmp     r14d, eax
0x18026add5  jnb     short loc_18026ADE4
0x18026add7  sub     r14d, ecx
0x18026adda  mov     [rsp+360h+var_310], r14d
0x18026addf  jmp     loc_18026AEC9
0x18026ade4  mov     ecx, [rdi+0A8h]
0x18026adea  mov     r12d, r14d
0x18026aded  cmp     r14d, ecx
0x18026adf0  jnb     loc_18026AEAF
0x18026adf6  sub     r14d, eax
0x18026adf9  mov     [rsp+360h+var_310], r14d
0x18026adfe  xor     edx, edx; Val
0x18026ae00  lea     rcx, [rbp+260h+Src]; void *
0x18026ae04  lea     r8d, [rdx+68h]; Size
0x18026ae08  call    memset_0
0x18026ae0d  mov     rdx, rsi; Src
0x18026ae10  lea     rcx, [rbp+260h+Src]; struct _CMINVOKECOMMANDINFOEX *
0x18026ae14  call    ?CopyInvokeInfo@@YAXPEAU_CMINVOKECOMMANDINFOEX@@PEBU_CMINVOKECOMMANDINFO@@@Z; CopyInvokeInfo(_CMINVOKECOMMANDINFOEX *,_CMINVOKECOMMANDINFO const *)
0x18026ae19  cmp     qword ptr [rsi+10h], 10000h
0x18026ae21  jnb     short loc_18026AE2D
0x18026ae23  movzx   esi, r14w
0x18026ae27  mov     [rbp+260h+Src.lpVerb], rsi
0x18026ae2b  jmp     short loc_18026AE31
0x18026ae2d  mov     rsi, [rbp+260h+Src.lpVerb]
0x18026ae31  xor     r14d, r14d
0x18026ae34  cmp     r12d, [rdi+0B0h]
0x18026ae3b  mov     [rsp+360h+ppStm], r14
0x18026ae40  setz    al
0x18026ae43  mov     [rdi+0B4h], al
0x18026ae49  mov     dl, 1
0x18026ae4b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AppSiloFileExplorerContextMenus@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AppSiloFileExplorerContextMenus@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppSiloFileExplorerContextMenus> `wil::Feature<__WilFeatureTraits_Feature_AppSiloFileExplorerContextMenus>::GetImpl(void)'::`2'::impl
0x18026ae52  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_AppSiloFileExplorerContextMenus@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppSiloFileExplorerContextMenus>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18026ae57  lea     rdx, [rbp+260h+Src]; struct _CMINVOKECOMMANDINFOEX *
0x18026ae5b  mov     rcx, r15; this
0x18026ae5e  call    ?BrokerFilesForAppSiloVerb@CDefFolderMenu@@AEAAJAEBU_CMINVOKECOMMANDINFOEX@@@Z; CDefFolderMenu::BrokerFilesForAppSiloVerb(_CMINVOKECOMMANDINFOEX const &)
0x18026ae63  mov     rcx, [rdi+0B8h]; hdsa
0x18026ae6a  lea     r9, [rsp+360h+var_320]
0x18026ae6f  lea     r8, [rsp+360h+ppStm]
0x18026ae74  mov     [rsp+360h+var_320], r14d
0x18026ae79  lea     rdx, [rbp+260h+Src]; Src
0x18026ae7d  call    HDXA_LetHandlerProcessCommandEx
0x18026ae82  mov     ebx, eax
0x18026ae84  test    eax, eax
0x18026ae86  js      loc_18026B37B
0x18026ae8c  cmp     [rsp+360h+ppStm], rsi
0x18026ae91  jz      loc_18026B376
0x18026ae97  cmp     [rsp+360h+var_320], r14d
0x18026ae9c  jz      loc_18026B37B
0x18026aea2  mov     rcx, r15; this
0x18026aea5  call    ?_AddToRecentDocs@CDefFolderMenu@@AEAAXXZ; CDefFolderMenu::_AddToRecentDocs(void)
0x18026aeaa  jmp     loc_18026B37B
0x18026aeaf  cmp     r12d, [rdi+0ACh]
0x18026aeb6  jnb     loc_18026B376
0x18026aebc  sub     r12d, ecx
0x18026aebf  mov     [rsp+360h+var_310], r12d
0x18026aec4  mov     r12, [rsp+360h+var_318]
0x18026aec9  test    byte ptr [rdi+53Ch], 20h
0x18026aed0  jz      short loc_18026AEF1
0x18026aed2  xor     ecx, ecx
0x18026aed4  cmp     ecx, 8
0x18026aed7  jnb     short loc_18026AEF1
0x18026aed9  lea     rdx, qword_1805F20B0
0x18026aee0  mov     eax, [rdx+rcx*8]
0x18026aee3  cmp     [rsp+360h+var_310], eax
0x18026aee7  jz      loc_18026B37B
0x18026aeed  inc     ecx
0x18026aeef  jmp     short loc_18026AED4
0x18026aef1  mov     r14d, [rsp+360h+var_320]
0x18026aef6  lea     r9, [rbp+260h+var_250]; unsigned __int16 *
0x18026aefa  mov     r8, [rsi+18h]; char *
0x18026aefe  mov     ecx, r14d; int
0x18026af01  mov     rdx, [rsi+48h]; unsigned __int16 *
0x18026af05  mov     [rsp+360h+var_340], 104h; unsigned int
0x18026af0d  call    ?GetAnsiOrUnicodeParam@@YAPEBGHPEBGPEBDPEAGI@Z; GetAnsiOrUnicodeParam(int,ushort const *,char const *,ushort *,uint)
0x18026af12  cmp     [rsp+360h+var_310], 0FFFFFFFBh
0x18026af17  mov     [rsp+360h+ppStm], rax
0x18026af1c  jz      loc_18026B1B9
0x18026af22  cmp     [rsp+360h+var_310], 0FFFFFFFCh
0x18026af27  jnz     short loc_18026AF45
0x18026af29  mov     r8, [rsi+20h]; char *
0x18026af2d  lea     r9, [rbp+260h+var_250]; unsigned __int16 *
0x18026af31  mov     rdx, [rsi+50h]; unsigned __int16 *
0x18026af35  mov     ecx, r14d; int
0x18026af38  mov     [rsp+360h+var_340], 104h; int
0x18026af40  call    ?GetAnsiOrUnicodeParam@@YAPEBGHPEBGPEBDPEAGI@Z; GetAnsiOrUnicodeParam(int,ushort const *,char const *,ushort *,uint)
0x18026af45  mov     r14, rax
0x18026af48  mov     eax, [rdi+98h]
0x18026af4e  mov     ecx, [rsi+4]
0x18026af51  mov     [rsp+360h+var_2F0], eax
0x18026af55  mov     eax, [rdi+0A0h]
0x18026af5b  mov     [rsp+360h+var_2EC], eax
0x18026af5f  mov     rax, [rdi-8]
0x18026af63  mov     [rbp+260h+var_2E0], rax
0x18026af67  mov     [rsp+360h+var_300], 28h ; '('
0x18026af6f  mov     [rsp+360h+var_2FC], ecx
0x18026af73  mov     [rsp+360h+var_2F8], r14
0x18026af78  mov     [rsp+360h+var_2E8], rsi
0x18026af7d  bt      ecx, 1Dh
0x18026af81  jnb     short loc_18026AFAC
0x18026af83  mov     rcx, [rdi+70h]; struct IDataObject *
0x18026af87  test    rcx, rcx
0x18026af8a  jz      short loc_18026AFAC
0x18026af8c  mov     rax, [rsi+60h]
0x18026af90  lea     r8, [rsp+360h+ppStm]; void *
0x18026af95  movzx   edx, cs:?g_cfOFFSETS_Storage@@3GA; unsigned int
0x18026af9c  mov     r9d, 8; unsigned int
0x18026afa2  mov     [rsp+360h+ppStm], rax
0x18026afa7  call    ?DataObj_SetBlobWithIndex@@YAJPEAUIDataObject@@IPEBXIJ@Z; DataObj_SetBlobWithIndex(IDataObject *,uint,void const *,uint,long)
0x18026afac  mov     rdx, [rdi-8]; punkSite
0x18026afb0  mov     rcx, [rdi+68h]; punk
0x18026afb4  call    cs:__imp_IUnknown_SetSite
0x18026afba  mov     rcx, [rdi+88h]
0x18026afc1  xor     edx, edx
0x18026afc3  call    cs:__imp_SHGetObjectCompatFlags
0x18026afc9  bt      eax, 0Eh
0x18026afcd  jnb     short loc_18026AFD8
0x18026afcf  or      ecx, 0FFFFFFFFh; dwProcessId
0x18026afd2  call    cs:__imp_AllowSetForegroundWindow
0x18026afd8  mov     edx, [rsp+360h+var_310]
0x18026afdc  lea     r8, [rsp+360h+var_300]
0x18026afe1  mov     rcx, [rdi+68h]
0x18026afe5  mov     r9, [rdi+70h]
0x18026afe9  mov     [rsp+360h+var_330], r8
0x18026afee  mov     r8, r12
0x18026aff1  mov     [rsp+360h+var_338], rdx
0x18026aff6  mov     rax, [rcx]
0x18026aff9  mov     rdx, [rdi+88h]
0x18026b000  mov     [rsp+360h+var_340], 0Ch
0x18026b008  mov     rax, [rax+18h]
0x18026b00c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026b011  mov     ebx, eax
0x18026b013  cmp     eax, 80004001h
0x18026b018  jnz     short loc_18026B050
0x18026b01a  mov     edx, [rsp+360h+var_310]
0x18026b01e  mov     r8, r12
0x18026b021  mov     rcx, [rdi+68h]
0x18026b025  mov     r9, [rdi+70h]
0x18026b029  mov     [rsp+360h+var_330], r14
0x18026b02e  mov     [rsp+360h+var_338], rdx
0x18026b033  mov     rax, [rcx]
0x18026b036  mov     rdx, [rdi+88h]
0x18026b03d  mov     [rsp+360h+var_340], 2; int
0x18026b045  mov     rax, [rax+18h]
0x18026b049  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026b04e  mov     ebx, eax
0x18026b050  mov     rcx, [rdi+68h]; punk
0x18026b054  xor     edx, edx; punkSite
0x18026b056  call    cs:__imp_IUnknown_SetSite
0x18026b05c  cmp     ebx, 1
0x18026b05f  jnz     loc_18026B37B
0x18026b065  mov     r9, [rdi+70h]
0x18026b069  xor     edx, edx
0x18026b06b  mov     ecx, [rsp+360h+var_310]
0x18026b06f  mov     ebx, edx
0x18026b071  test    r9, r9
0x18026b074  jz      loc_18026B34E
0x18026b07a  cmp     ecx, 0FFFFFFF3h
0x18026b07d  jz      loc_18026B341
0x18026b083  mov     eax, 0FFFFFFF6h
0x18026b088  cmp     ecx, eax
0x18026b08a  jz      loc_18026B35C
0x18026b090  cmp     ecx, 0FFFFFFF9h
0x18026b093  jz      loc_18026B35C
0x18026b099  cmp     ecx, 0FFFFFFFBh
0x18026b09c  jz      loc_18026B304
0x18026b0a2  cmp     ecx, 0FFFFFFFCh
0x18026b0a5  jz      loc_18026B2EC
0x18026b0ab  lea     eax, [rcx+3]
0x18026b0ae  cmp     eax, 1
0x18026b0b1  jbe     loc_18026B1D6
0x18026b0b7  cmp     ecx, 0FFFFFFFFh
0x18026b0ba  jnz     loc_18026B37B
0x18026b0c0  mov     rcx, [rdi-8]
0x18026b0c4  mov     edx, 3040h
0x18026b0c9  call    ?Fire_ExplorerTelemetryFromSiteWithDataObject@@YAXPEAUIUnknown@@W4EXPLORER_COMMAND_SQM_ID@@W4EXPLORER_COMMAND_SQM_SELECTED_STATE@@PEAUIDataObject@@@Z; Fire_ExplorerTelemetryFromSiteWithDataObject(IUnknown *,EXPLORER_COMMAND_SQM_ID,EXPLORER_COMMAND_SQM_SELECTED_STATE,IDataObject *)
0x18026b0ce  mov     edx, [rsp+360h+var_2FC]
0x18026b0d2  bt      edx, 14h
0x18026b0d6  jnb     loc_18026B1A3
0x18026b0dc  mov     rcx, [rdi+70h]; struct IDataObject *
0x18026b0e0  call    DataObj_CanGoAsyncAndStartOpIfSo
0x18026b0e5  xor     r14d, r14d
0x18026b0e8  test    eax, eax
0x18026b0ea  jz      loc_18026B19F
0x18026b0f0  lea     r9, [rsp+360h+ppStm]; void **
0x18026b0f5  mov     [rsp+360h+ppStm], r14
0x18026b0fa  lea     edx, [r14+40h]; unsigned int
0x18026b0fe  lea     r8d, [r14+20h]; unsigned __int64
0x18026b102  call    ?Alloc@CTLocalAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTLocalAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x18026b107  test    eax, eax
0x18026b109  js      loc_18026B19F
0x18026b10f  mov     rsi, [rsp+360h+ppStm]
0x18026b114  lea     rcx, IID_IDataObject; riid
0x18026b11b  mov     rdx, [rdi+70h]; pUnk
0x18026b11f  mov     r8, rsi; ppStm
  ... truncated ...
```
