# CUserCplCore::InitializePage(CUserCplPage *)

- ea: `0x180015768`
- end: `0x180015da0`
- name: `?InitializePage@CUserCplCore@@QEAAJPEAVCUserCplPage@@@Z`
- size: `1592`
- prototype: `__int64 __fastcall(CUserCplCore *__hidden this, struct CUserCplPage *)`
- caller_count: `1`
- callee_count: `24`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180024270`

## callees

- `0x18000b6dc`
- `0x18000bb38`
- `0x18000d9a4`
- `0x18000e3f0`
- `0x18001315c`
- `0x180014c90`
- `0x180014dd8`
- `0x1800151d8`
- `0x180015374`
- `0x180015434`
- `0x18001552c`
- `0x180015768`
- `0x180015f4c`
- `0x180016874`
- `0x180017e60`
- `0x180017ffc`
- `0x180018c9c`
- `0x1800228d4`
- `0x180060d60`
- `0x180063bc8`
- `0x180066260`
- `0x1800679b8`
- `0x1800772c0`
- `0x180078010`

## import_xrefs

- `SHELL32!__imp_WPC_InstallState` at `0x180015b10`
- `SHELL32!__imp_WPC_InstallState` at `0x180015b10`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015c83`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015c83`
- `OLEAUT32!__imp_SysFreeString` at `0x180015922`
- `OLEAUT32!__imp_SysFreeString` at `0x180015922`
- `DUI70!?SetDataEntry@Macro@DirectUI@@QEAAXPEAUIDataEntry@2@PEAVElement@2@@Z` at `0x1800158b7`
- `DUI70!?SetDataEntry@Macro@DirectUI@@QEAAXPEAUIDataEntry@2@PEAVElement@2@@Z` at `0x1800158b7`
- `DUI70!GetElementMacro` at `0x18001589f`
- `DUI70!GetElementMacro` at `0x18001589f`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180015b93`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180015bc0`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180015b93`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180015bc0`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x180015c51`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x180015c51`
- `DUI70!?SetAccName@Element@DirectUI@@QEAAJPEBG@Z` at `0x180015c7a`
- `DUI70!?SetAccName@Element@DirectUI@@QEAAJPEBG@Z` at `0x180015c7a`
- `DUI70!StrToID` at `0x180015834`
- `DUI70!StrToID` at `0x180015859`
- `DUI70!StrToID` at `0x1800158c4`
- `DUI70!StrToID` at `0x180015936`
- `DUI70!StrToID` at `0x180015962`
- `DUI70!StrToID` at `0x180015980`
- `DUI70!StrToID` at `0x1800159ac`
- `DUI70!StrToID` at `0x1800159ca`
- `DUI70!StrToID` at `0x1800159f3`
- `DUI70!StrToID` at `0x180015a1f`
- `DUI70!StrToID` at `0x180015a3d`
- `DUI70!StrToID` at `0x180015a5a`
- `DUI70!StrToID` at `0x180015a77`
- `DUI70!StrToID` at `0x180015a94`
- `DUI70!StrToID` at `0x180015ab1`
- `DUI70!StrToID` at `0x180015af6`
- `DUI70!StrToID` at `0x180015b76`
- `DUI70!StrToID` at `0x180015ba0`
- `DUI70!StrToID` at `0x180015bd9`
- `DUI70!StrToID` at `0x180015c35`
- `DUI70!StrToID` at `0x180015c62`
- `DUI70!StrToID` at `0x180015c90`
- `DUI70!StrToID` at `0x180015cc1`
- `DUI70!StrToID` at `0x180015834`
- `DUI70!StrToID` at `0x180015859`
- `DUI70!StrToID` at `0x1800158c4`
- `DUI70!StrToID` at `0x180015936`
- `DUI70!StrToID` at `0x180015962`
- `DUI70!StrToID` at `0x180015980`
- `DUI70!StrToID` at `0x1800159ac`
- `DUI70!StrToID` at `0x1800159ca`
- `DUI70!StrToID` at `0x1800159f3`
- `DUI70!StrToID` at `0x180015a1f`
- `DUI70!StrToID` at `0x180015a3d`
- `DUI70!StrToID` at `0x180015a5a`
- `DUI70!StrToID` at `0x180015a77`
- `DUI70!StrToID` at `0x180015a94`
- `DUI70!StrToID` at `0x180015ab1`
- `DUI70!StrToID` at `0x180015af6`
- `DUI70!StrToID` at `0x180015b76`
- `DUI70!StrToID` at `0x180015ba0`
- `DUI70!StrToID` at `0x180015bd9`
- `DUI70!StrToID` at `0x180015c35`
- `DUI70!StrToID` at `0x180015c62`
- `DUI70!StrToID` at `0x180015c90`
- `DUI70!StrToID` at `0x180015cc1`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180015865`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800158d0`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180015b82`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180015bac`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180015c41`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180015c6e`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180015c9c`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180015865`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800158d0`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180015b82`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180015bac`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180015c41`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180015c6e`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180015c9c`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_GetSite` at `0x18001580a`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_GetSite` at `0x180015d37`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_GetSite` at `0x18001580a`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_GetSite` at `0x180015d37`
- `SHCORE!__imp_SHWindowsPolicy` at `0x180015ac3`
- `SHCORE!__imp_SHWindowsPolicy` at `0x180015ac3`

## string_xrefs

- `0x18001582a`: `pageAdminTasks`
- `0x180015aef`: `pageAdminTasks`
- `0x180015a36`: `pageRenameAccount`
- `0x180015979`: `pageCreatePassword`
- `0x180015bd2`: `pageDeleteAccount`
- `0x1800159c3`: `pageConfirmDeleteAccount`
- `0x180015a53`: `pageRenameMyAccount`
- `0x1800159a5`: `pageCreateMyPassword`
- `0x180015b6f`: `navCreateAccountLocal`
- `0x180015b99`: `navCreateAccountSettingsApp`
- `0x180015c89`: `actionDeleteAccountFiles`
- `0x180015c2e`: `maintaskinstruction`
- `0x180015c5b`: `maintaskinstruction`
- `0x180015d0f`: `maintaskinstruction`
- `0x180015cfc`: `maintasktitle`

## pseudocode

```c
__int64 __fastcall CUserCplCore::InitializePage(CUserCplCore *this, struct CUserCplPage *a2, __int64 a3)
{
  __int64 v5; // rcx
  __int64 v6; // r8
  int Site; // esi
  struct CUserData *SelectedUser; // rax
  __int16 v9; // bx
  struct CUserData *v10; // r13
  unsigned __int16 v11; // ax
  struct DirectUI::Element *Descendent; // r15
  unsigned __int64 v13; // rbx
  DirectUI::Macro *ElementMacro; // rax
  unsigned __int16 v15; // ax
  struct DirectUI::Element *v16; // rax
  UserTile *v17; // r15
  __int64 v18; // rcx
  __int16 v19; // bx
  bool v20; // r8
  int PasswordPages; // eax
  __int16 v22; // bx
  __int16 v23; // bx
  bool v24; // r8
  __int16 v25; // bx
  __int16 v26; // bx
  __int16 v27; // bx
  bool v28; // r8
  __int16 v29; // bx
  __int16 v30; // bx
  CUserCplCore *v31; // rcx
  __int16 v32; // bx
  __int16 v33; // bx
  __int16 v34; // bx
  __int16 v35; // bx
  __int16 v36; // bx
  int v37; // ebx
  int v38; // r15d
  unsigned __int16 v39; // ax
  DirectUI::Element *v40; // rax
  unsigned __int16 v41; // ax
  DirectUI::Element *v42; // rax
  __int16 v43; // bx
  __int64 v44; // r8
  unsigned __int16 v45; // ax
  DirectUI::Element *v46; // rax
  unsigned __int16 *v47; // rbx
  unsigned __int16 v48; // ax
  DirectUI::Element *v49; // rax
  const wchar_t *v50; // rcx
  unsigned __int16 v51; // ax
  struct DirectUI::Element *v52; // rax
  __int16 v53; // bx
  void *Src; // [rsp+20h] [rbp-30h]
  BSTR bstrString[2]; // [rsp+30h] [rbp-20h] BYREF

  if ( (Microsoft_Windows_User_ControlPanelEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(this, Perf_Initialization_Page_Start, a3, 1, bstrString);
  if ( !(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 152LL))(*((_QWORD *)this + 2)) )
  {
    Site = -2147467259;
    goto LABEL_72;
  }
  *((_QWORD *)this + 10) = a2;
  *((_QWORD *)this + 9) = a2;
  SafeRelease<IUnknown>((char *)this + 96);
  Site = IUnknown_GetSite(
           (IUnknown *)(-(__int64)(a2 != 0) & ((unsigned __int64)a2 + 208)),
           &GUID_00000000_0000_0000_c000_000000000046,
           (void **)this + 12);
  if ( Site < 0 )
    goto LABEL_72;
  SelectedUser = CUserManager::GetSelectedUser(*((CUserManager **)this + 2));
  v9 = *((_WORD *)a2 + 72);
  v10 = SelectedUser;
  if ( v9 == (unsigned __int16)StrToID(L"pageAdminTasks") )
  {
    CUserCplCore::PopulateUserArea(this, a2, 1);
  }
  else
  {
    v11 = StrToID(L"userpane");
    Descendent = DirectUI::Element::FindDescendent(a2, v11);
    Site = CUserCplCore::_EnsureValidSelectedUser(this, *((_WORD *)a2 + 72));
    if ( Site < 0 )
      goto LABEL_72;
    v10 = CUserManager::GetSelectedUser(*((CUserManager **)this + 2));
    v13 = (unsigned __int64)v10 + 16;
    if ( Descendent )
    {
      ElementMacro = (DirectUI::Macro *)GetElementMacro(Descendent);
      DirectUI::Macro::SetDataEntry(ElementMacro, (struct DirectUI::IDataEntry *)(v13 & -(__int64)(v10 != 0)), 0);
    }
    v15 = StrToID(L"UserTileControl");
    v16 = DirectUI::Element::FindDescendent(a2, v15);
    v17 = (UserTile *)element_cast<UserTile>(v16);
    if ( v17 )
    {
      v18 = *(_QWORD *)v13;
      bstrString[0] = 0;
      if ( (*(int (__fastcall **)(unsigned __int64, const WCHAR *, BSTR *, _QWORD))(v18 + 8))(
             v13,
             L"SID",
             bstrString,
             0) >= 0 )
      {
        UserTile::_SetUserInternal(v17, bstrString[0], 0);
        SysFreeString(bstrString[0]);
      }
    }
  }
  v19 = *((_WORD *)a2 + 72);
  if ( v19 == (unsigned __int16)StrToID(L"pageChangePassword") )
  {
    v20 = 0;
LABEL_16:
    PasswordPages = CUserCplCore::InitChangePasswordPages(this, a2, v20);
LABEL_64:
    Site = PasswordPages;
    goto LABEL_65;
  }
  v22 = *((_WORD *)a2 + 72);
  if ( v22 == (unsigned __int16)StrToID(L"pageChangeMyPassword") )
  {
    v20 = 1;
    goto LABEL_16;
  }
  v23 = *((_WORD *)a2 + 72);
  if ( v23 == (unsigned __int16)StrToID(L"pageCreatePassword") )
  {
    v24 = 0;
LABEL_21:
    PasswordPages = CUserCplCore::InitCreatePasswordPages(this, a2, v24);
    goto LABEL_64;
  }
  v25 = *((_WORD *)a2 + 72);
  if ( v25 == (unsigned __int16)StrToID(L"pageCreateMyPassword") )
  {
    v24 = 1;
    goto LABEL_21;
  }
  v26 = *((_WORD *)a2 + 72);
  if ( v26 == (unsigned __int16)StrToID(L"pageConfirmDeleteAccount") )
  {
    PasswordPages = CUserCplCore::InitConfirmDeleteAccountPage(this, a2);
    goto LABEL_64;
  }
  v27 = *((_WORD *)a2 + 72);
  if ( v27 == (unsigned __int16)StrToID(L"pageChangeChoices") )
  {
    v28 = 0;
LABEL_28:
    PasswordPages = CUserCplCore::InitChangeChoicesPages(this, a2, v28);
    goto LABEL_64;
  }
  v29 = *((_WORD *)a2 + 72);
  if ( v29 == (unsigned __int16)StrToID(L"pageChangeMyChoices") )
  {
    v28 = 1;
    goto LABEL_28;
  }
  v30 = *((_WORD *)a2 + 72);
  if ( v30 == (unsigned __int16)StrToID(L"pageRenameAccount")
    || (v32 = *((_WORD *)a2 + 72), v32 == (unsigned __int16)StrToID(L"pageRenameMyAccount")) )
  {
    PasswordPages = CUserCplCore::InitRenameAccountPages(v31, a2);
    goto LABEL_64;
  }
  v33 = *((_WORD *)a2 + 72);
  if ( v33 == (unsigned __int16)StrToID(L"pageChangeAccountType")
    || (v34 = *((_WORD *)a2 + 72), v34 == (unsigned __int16)StrToID(L"pageChangeMyAccountType")) )
  {
    PasswordPages = CUserCplCore::InitChangeAccountTypePages(this, a2);
    goto LABEL_64;
  }
  v35 = *((_WORD *)a2 + 72);
  if ( v35 == (unsigned __int16)StrToID(L"pageChangeGuestChoices") )
  {
    if ( (unsigned int)SHWindowsPolicy(POLID_UseDefaultTile) )
      SetVisibleNavigateButton(a2, L"GuestChangePicture", 0);
    goto LABEL_65;
  }
  v36 = *((_WORD *)a2 + 72);
  if ( v36 == (unsigned __int16)StrToID(L"pageAdminTasks") )
  {
    LODWORD(bstrString[0]) = 0;
    if ( (int)WPC_InstallState(bstrString) < 0 || LODWORD(bstrString[0]) )
    {
      SetVisibleNavigateButton(a2, L"actionGotoParentalControls", 0);
      SetVisibleNavigateButton(a2, L"actionImgGotoParentalControls", 0);
    }
    if ( *((_DWORD *)this + 27)
      && (unsigned int)LUAIsAdminAndIsOSSilentElevationOn()
      && !(unsigned int)IsOS_OS_ANYSERVER() )
    {
      v37 = 1;
      v38 = -3;
    }
    else
    {
      v37 = -3;
      v38 = 1;
    }
    v39 = StrToID(L"navCreateAccountLocal");
    v40 = DirectUI::Element::FindDescendent(a2, v39);
    if ( v40 )
      DirectUI::Element::SetLayoutPos(v40, v38);
    v41 = StrToID(L"navCreateAccountSettingsApp");
    v42 = DirectUI::Element::FindDescendent(a2, v41);
    if ( v42 )
      DirectUI::Element::SetLayoutPos(v42, v37);
    goto LABEL_65;
  }
  v43 = *((_WORD *)a2 + 72);
  if ( v43 == (unsigned __int16)StrToID(L"pageDeleteAccount") )
  {
    if ( v10 )
    {
      if ( CUserData::IsConnected(v10) )
      {
        bstrString[0] = 0;
        if ( (int)TResourceStringAllocCopyEx<unsigned short *>(
                    g_hinst,
                    209,
                    v44,
                    (__int64 (__fastcall *)(_QWORD, size_t, char **))&ResourceStringAllocCopyExCoAlloc,
                    Src,
                    (char *)bstrString) >= 0 )
        {
          v45 = StrToID(L"maintaskinstruction");
          v46 = DirectUI::Element::FindDescendent(a2, v45);
          v47 = bstrString[0];
          if ( (int)DirectUI::Element::SetContentString(v46, bstrString[0]) >= 0 )
          {
            v48 = StrToID(L"maintaskinstruction");
            v49 = DirectUI::Element::FindDescendent(a2, v48);
            DirectUI::Element::SetAccName(v49, v47);
          }
          CoTaskMemFree(v47);
        }
      }
    }
    v50 = L"actionDeleteAccountFiles";
    goto LABEL_59;
  }
  v53 = *((_WORD *)a2 + 72);
  if ( v53 == (unsigned __int16)StrToID(L"pageTurnOnGuestChoices") )
  {
    v50 = L"actionTurnOnGuest";
LABEL_59:
    v51 = StrToID(v50);
    v52 = DirectUI::Element::FindDescendent(a2, v51);
    PasswordPages = DUIFramework_SetRegisteredDefaultButton((struct IObjectWithSite *)a2 + 26, v52);
    goto LABEL_64;
  }
LABEL_65:
  if ( Site < 0 )
    goto LABEL_72;
  if ( v10 )
  {
    SetPTextContext(a2, L"maintasktitle", (struct CUserData *)((char *)v10 + 16));
    SetPTextContext(a2, L"maintaskinstruction", (struct CUserData *)((char *)v10 + 16));
  }
  if ( *((_QWORD *)this + 12) )
  {
    Site = 0;
  }
  else
  {
    Site = IUnknown_GetSite((IUnknown *)a2 + 26, &GUID_00000000_0000_0000_c000_000000000046, (void **)this + 12);
    if ( Site < 0 )
      goto LABEL_72;
  }
  DUI_WalkIUnknownElements(a2, (void (*)(struct IUnknown *, __int64))DUI_SetSiteOnUnknown, *((_QWORD *)this + 12));
LABEL_72:
  if ( (Microsoft_Windows_User_ControlPanelEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(v5, Perf_Initialization_Page_Stop, v6, 1, bstrString);
  return (unsigned int)Site;
}

```

## disassembly

```asm
0x180015768  mov     [rsp-38h+arg_10], rbx
0x18001576d  push    rbp
0x18001576e  push    rsi
0x18001576f  push    rdi
0x180015770  push    r12
0x180015772  push    r13
0x180015774  push    r14
0x180015776  push    r15
0x180015778  mov     rbp, rsp
0x18001577b  sub     rsp, 50h
0x18001577f  mov     rax, cs:__security_cookie
0x180015786  xor     rax, rsp
0x180015789  mov     [rbp+var_10], rax
0x18001578d  test    cs:Microsoft_Windows_User_ControlPanelEnableBits, 1
0x180015794  mov     rdi, rdx
0x180015797  mov     r14, rcx
0x18001579a  jz      short loc_1800157B7
0x18001579c  lea     rax, [rbp+bstrString]
0x1800157a0  mov     r9d, 1
0x1800157a6  lea     rdx, Perf_Initialization_Page_Start
0x1800157ad  mov     [rsp+50h+Src], rax; Src
0x1800157b2  call    McGenEventWrite_EventWriteTransfer
0x1800157b7  mov     rcx, [r14+10h]
0x1800157bb  mov     rax, [rcx]
0x1800157be  mov     rax, [rax+98h]
0x1800157c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800157ca  test    rax, rax
0x1800157cd  jnz     short loc_1800157D9
0x1800157cf  mov     esi, 80004005h
0x1800157d4  jmp     loc_180015D56
0x1800157d9  lea     r12, [r14+60h]
0x1800157dd  mov     [r14+50h], rdi
0x1800157e1  mov     rcx, r12
0x1800157e4  mov     [r14+48h], rdi
0x1800157e8  call    ??$SafeRelease@UIUnknown@@@@YAXPEAPEAUIUnknown@@@Z; SafeRelease<IUnknown>(IUnknown * *)
0x1800157ed  mov     rax, rdi
0x1800157f0  lea     rcx, [rdi+0D0h]
0x1800157f7  neg     rax
0x1800157fa  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x180015801  mov     r8, r12; ppv
0x180015804  sbb     r9, r9
0x180015807  and     rcx, r9; punk
0x18001580a  call    cs:__imp_IUnknown_GetSite
0x180015810  mov     esi, eax
0x180015812  test    eax, eax
0x180015814  js      loc_180015D56
0x18001581a  mov     rcx, [r14+10h]; this
0x18001581e  call    ?GetSelectedUser@CUserManager@@QEAAPEAVCUserData@@XZ; CUserManager::GetSelectedUser(void)
0x180015823  movzx   ebx, word ptr [rdi+90h]
0x18001582a  lea     rcx, aPageadmintasks_0; "pageAdminTasks"
0x180015831  mov     r13, rax
0x180015834  call    cs:__imp_StrToID
0x18001583a  cmp     bx, ax
0x18001583d  jnz     short loc_180015852
0x18001583f  mov     r8b, 1; bool
0x180015842  mov     rdx, rdi; struct DirectUI::Element *
0x180015845  mov     rcx, r14; this
0x180015848  call    ?PopulateUserArea@CUserCplCore@@AEAAXPEAVElement@DirectUI@@_N@Z; CUserCplCore::PopulateUserArea(DirectUI::Element *,bool)
0x18001584d  jmp     loc_180015928
0x180015852  lea     rcx, aUserpane; "userpane"
0x180015859  call    cs:__imp_StrToID
0x18001585f  movzx   edx, ax
0x180015862  mov     rcx, rdi
0x180015865  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18001586b  movzx   edx, word ptr [rdi+90h]; unsigned __int16
0x180015872  mov     rcx, r14; this
0x180015875  mov     r15, rax
0x180015878  call    ?_EnsureValidSelectedUser@CUserCplCore@@QEAAJG@Z; CUserCplCore::_EnsureValidSelectedUser(ushort)
0x18001587d  mov     esi, eax
0x18001587f  test    eax, eax
0x180015881  js      loc_180015D56
0x180015887  mov     rcx, [r14+10h]; this
0x18001588b  call    ?GetSelectedUser@CUserManager@@QEAAPEAVCUserData@@XZ; CUserManager::GetSelectedUser(void)
0x180015890  mov     r13, rax
0x180015893  lea     rbx, [rax+10h]
0x180015897  test    r15, r15
0x18001589a  jz      short loc_1800158BD
0x18001589c  mov     rcx, r15
0x18001589f  call    cs:__imp_GetElementMacro
0x1800158a5  mov     rcx, r13
0x1800158a8  neg     rcx
0x1800158ab  mov     rcx, rax
0x1800158ae  sbb     rdx, rdx
0x1800158b1  xor     r8d, r8d
0x1800158b4  and     rdx, rbx
0x1800158b7  call    cs:__imp_?SetDataEntry@Macro@DirectUI@@QEAAXPEAUIDataEntry@2@PEAVElement@2@@Z; DirectUI::Macro::SetDataEntry(DirectUI::IDataEntry *,DirectUI::Element *)
0x1800158bd  lea     rcx, aUsertilecontro_0; "UserTileControl"
0x1800158c4  call    cs:__imp_StrToID
0x1800158ca  movzx   edx, ax
0x1800158cd  mov     rcx, rdi
0x1800158d0  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x1800158d6  mov     rcx, rax
0x1800158d9  call    ??$element_cast@VUserTile@@@@YAPEAVUserTile@@PEAVElement@DirectUI@@@Z; element_cast<UserTile>(DirectUI::Element *)
0x1800158de  mov     r15, rax
0x1800158e1  test    rax, rax
0x1800158e4  jz      short loc_180015928
0x1800158e6  mov     rcx, [rbx]
0x1800158e9  lea     r8, [rbp+bstrString]
0x1800158ed  xor     r9d, r9d
0x1800158f0  mov     [rbp+bstrString], 0
0x1800158f8  lea     rdx, aSid_0; "SID"
0x1800158ff  mov     rax, [rcx+8]
0x180015903  mov     rcx, rbx
0x180015906  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001590b  test    eax, eax
0x18001590d  js      short loc_180015928
0x18001590f  mov     rdx, [rbp+bstrString]; unsigned __int16 *
0x180015913  xor     r8d, r8d; bool
0x180015916  mov     rcx, r15; this
0x180015919  call    ?_SetUserInternal@UserTile@@AEAAJPEBG_N@Z; UserTile::_SetUserInternal(ushort const *,bool)
0x18001591e  mov     rcx, [rbp+bstrString]; bstrString
0x180015922  call    cs:__imp_SysFreeString
0x180015928  movzx   ebx, word ptr [rdi+90h]
0x18001592f  lea     rcx, aPagechangepass; "pageChangePassword"
0x180015936  call    cs:__imp_StrToID
0x18001593c  cmp     bx, ax
0x18001593f  jnz     short loc_180015954
0x180015941  xor     r8d, r8d; bool
0x180015944  mov     rdx, rdi; struct CUserCplPage *
0x180015947  mov     rcx, r14; this
0x18001594a  call    ?InitChangePasswordPages@CUserCplCore@@AEAAJPEAVCUserCplPage@@_N@Z; CUserCplCore::InitChangePasswordPages(CUserCplPage *,bool)
0x18001594f  jmp     loc_180015CEA
0x180015954  movzx   ebx, word ptr [rdi+90h]
0x18001595b  lea     rcx, aPagechangemypa; "pageChangeMyPassword"
0x180015962  call    cs:__imp_StrToID
0x180015968  cmp     bx, ax
0x18001596b  jnz     short loc_180015972
0x18001596d  mov     r8b, 1
0x180015970  jmp     short loc_180015944
0x180015972  movzx   ebx, word ptr [rdi+90h]
0x180015979  lea     rcx, aPagecreatepass; "pageCreatePassword"
0x180015980  call    cs:__imp_StrToID
0x180015986  cmp     bx, ax
0x180015989  jnz     short loc_18001599E
0x18001598b  xor     r8d, r8d; bool
0x18001598e  mov     rdx, rdi; struct CUserCplPage *
0x180015991  mov     rcx, r14; this
0x180015994  call    ?InitCreatePasswordPages@CUserCplCore@@AEAAJPEAVCUserCplPage@@_N@Z; CUserCplCore::InitCreatePasswordPages(CUserCplPage *,bool)
0x180015999  jmp     loc_180015CEA
0x18001599e  movzx   ebx, word ptr [rdi+90h]
0x1800159a5  lea     rcx, aPagecreatemypa; "pageCreateMyPassword"
0x1800159ac  call    cs:__imp_StrToID
0x1800159b2  cmp     bx, ax
0x1800159b5  jnz     short loc_1800159BC
0x1800159b7  mov     r8b, 1
0x1800159ba  jmp     short loc_18001598E
0x1800159bc  movzx   ebx, word ptr [rdi+90h]
0x1800159c3  lea     rcx, aPageconfirmdel; "pageConfirmDeleteAccount"
0x1800159ca  call    cs:__imp_StrToID
0x1800159d0  cmp     bx, ax
0x1800159d3  jnz     short loc_1800159E5
0x1800159d5  mov     rdx, rdi; struct CUserCplPage *
0x1800159d8  mov     rcx, r14; this
0x1800159db  call    ?InitConfirmDeleteAccountPage@CUserCplCore@@AEAAJPEAVCUserCplPage@@@Z; CUserCplCore::InitConfirmDeleteAccountPage(CUserCplPage *)
0x1800159e0  jmp     loc_180015CEA
0x1800159e5  movzx   ebx, word ptr [rdi+90h]
0x1800159ec  lea     rcx, aPagechangechoi; "pageChangeChoices"
0x1800159f3  call    cs:__imp_StrToID
0x1800159f9  cmp     bx, ax
0x1800159fc  jnz     short loc_180015A11
0x1800159fe  xor     r8d, r8d; bool
0x180015a01  mov     rdx, rdi; struct CUserCplPage *
0x180015a04  mov     rcx, r14; this
0x180015a07  call    ?InitChangeChoicesPages@CUserCplCore@@AEAAJPEAVCUserCplPage@@_N@Z; CUserCplCore::InitChangeChoicesPages(CUserCplPage *,bool)
0x180015a0c  jmp     loc_180015CEA
0x180015a11  movzx   ebx, word ptr [rdi+90h]
0x180015a18  lea     rcx, aPagechangemych; "pageChangeMyChoices"
0x180015a1f  call    cs:__imp_StrToID
0x180015a25  cmp     bx, ax
0x180015a28  jnz     short loc_180015A2F
0x180015a2a  mov     r8b, 1
0x180015a2d  jmp     short loc_180015A01
0x180015a2f  movzx   ebx, word ptr [rdi+90h]
0x180015a36  lea     rcx, aPagerenameacco; "pageRenameAccount"
0x180015a3d  call    cs:__imp_StrToID
0x180015a43  cmp     bx, ax
0x180015a46  jz      loc_180015CE2
0x180015a4c  movzx   ebx, word ptr [rdi+90h]
0x180015a53  lea     rcx, aPagerenamemyac; "pageRenameMyAccount"
0x180015a5a  call    cs:__imp_StrToID
0x180015a60  cmp     bx, ax
0x180015a63  jz      loc_180015CE2
0x180015a69  movzx   ebx, word ptr [rdi+90h]
0x180015a70  lea     rcx, aPagechangeacco_0; "pageChangeAccountType"
0x180015a77  call    cs:__imp_StrToID
0x180015a7d  cmp     bx, ax
0x180015a80  jz      loc_180015CD5
0x180015a86  movzx   ebx, word ptr [rdi+90h]
0x180015a8d  lea     rcx, aPagechangemyac; "pageChangeMyAccountType"
0x180015a94  call    cs:__imp_StrToID
0x180015a9a  cmp     bx, ax
0x180015a9d  jz      loc_180015CD5
0x180015aa3  movzx   ebx, word ptr [rdi+90h]
0x180015aaa  lea     rcx, aPagechangegues; "pageChangeGuestChoices"
0x180015ab1  call    cs:__imp_StrToID
0x180015ab7  cmp     bx, ax
0x180015aba  jnz     short loc_180015AE8
0x180015abc  lea     rcx, POLID_UseDefaultTile
0x180015ac3  call    cs:__imp_SHWindowsPolicy
0x180015ac9  test    eax, eax
0x180015acb  jz      loc_180015CEC
0x180015ad1  xor     r8d, r8d; int
0x180015ad4  lea     rdx, aGuestchangepic; "GuestChangePicture"
0x180015adb  mov     rcx, rdi; struct DirectUI::Element *
0x180015ade  call    ?SetVisibleNavigateButton@@YAXPEAVElement@DirectUI@@PEBGH@Z; SetVisibleNavigateButton(DirectUI::Element *,ushort const *,int)
0x180015ae3  jmp     loc_180015CEC
0x180015ae8  movzx   ebx, word ptr [rdi+90h]
0x180015aef  lea     rcx, aPageadmintasks_0; "pageAdminTasks"
0x180015af6  call    cs:__imp_StrToID
0x180015afc  cmp     bx, ax
0x180015aff  jnz     loc_180015BCB
0x180015b05  lea     rcx, [rbp+bstrString]
0x180015b09  mov     dword ptr [rbp+bstrString], 0
0x180015b10  call    cs:__imp_WPC_InstallState
0x180015b16  test    eax, eax
0x180015b18  js      short loc_180015B20
0x180015b1a  cmp     dword ptr [rbp+bstrString], 0
0x180015b1e  jz      short loc_180015B44
0x180015b20  xor     r8d, r8d; int
0x180015b23  lea     rdx, aActiongotopare; "actionGotoParentalControls"
0x180015b2a  mov     rcx, rdi; struct DirectUI::Element *
0x180015b2d  call    ?SetVisibleNavigateButton@@YAXPEAVElement@DirectUI@@PEBGH@Z; SetVisibleNavigateButton(DirectUI::Element *,ushort const *,int)
0x180015b32  xor     r8d, r8d; int
0x180015b35  lea     rdx, aActionimggotop; "actionImgGotoParentalControls"
0x180015b3c  mov     rcx, rdi; struct DirectUI::Element *
0x180015b3f  call    ?SetVisibleNavigateButton@@YAXPEAVElement@DirectUI@@PEBGH@Z; SetVisibleNavigateButton(DirectUI::Element *,ushort const *,int)
0x180015b44  cmp     dword ptr [r14+6Ch], 0
0x180015b49  jz      short loc_180015B66
0x180015b4b  call    LUAIsAdminAndIsOSSilentElevationOn
0x180015b50  test    eax, eax
0x180015b52  jz      short loc_180015B66
0x180015b54  call    ?IsOS_OS_ANYSERVER@@YAHXZ; IsOS_OS_ANYSERVER(void)
0x180015b59  test    eax, eax
0x180015b5b  jnz     short loc_180015B66
0x180015b5d  lea     ebx, [rax+1]
0x180015b60  lea     r15d, [rax-3]
0x180015b64  jmp     short loc_180015B6F
0x180015b66  mov     ebx, 0FFFFFFFDh
0x180015b6b  lea     r15d, [rbx+4]
0x180015b6f  lea     rcx, aNavcreateaccou_0; "navCreateAccountLocal"
0x180015b76  call    cs:__imp_StrToID
0x180015b7c  movzx   edx, ax
0x180015b7f  mov     rcx, rdi
0x180015b82  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180015b88  test    rax, rax
0x180015b8b  jz      short loc_180015B99
0x180015b8d  mov     edx, r15d
0x180015b90  mov     rcx, rax
0x180015b93  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x180015b99  lea     rcx, aNavcreateaccou; "navCreateAccountSettingsApp"
0x180015ba0  call    cs:__imp_StrToID
0x180015ba6  movzx   edx, ax
0x180015ba9  mov     rcx, rdi
0x180015bac  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180015bb2  test    rax, rax
0x180015bb5  jz      loc_180015CEC
0x180015bbb  mov     edx, ebx
0x180015bbd  mov     rcx, rax
0x180015bc0  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x180015bc6  jmp     loc_180015CEC
0x180015bcb  movzx   ebx, word ptr [rdi+90h]
0x180015bd2  lea     rcx, aPagedeleteacco; "pageDeleteAccount"
0x180015bd9  call    cs:__imp_StrToID
0x180015bdf  cmp     bx, ax
0x180015be2  jnz     loc_180015CB3
0x180015be8  test    r13, r13
0x180015beb  jz      loc_180015C89
0x180015bf1  mov     rcx, r13; this
0x180015bf4  call    ?IsConnected@CUserData@@QEAA_NXZ; CUserData::IsConnected(void)
0x180015bf9  test    al, al
0x180015bfb  jz      loc_180015C89
0x180015c01  mov     rcx, cs:g_hinst; int
0x180015c08  lea     rax, [rbp+bstrString]
0x180015c0c  lea     r9, _ResourceStringAllocCopyExCoAlloc; int
0x180015c13  mov     [rsp+50h+var_28], rax; void *
0x180015c18  mov     edx, 0D1h; int
0x180015c1d  mov     [rbp+bstrString], 0
0x180015c25  call    ??$TResourceStringAllocCopyEx@PEAG@@YAJPEAUHINSTANCE__@@IGP6AJPEAX_KPEAPEAG@Z13@Z; TResourceStringAllocCopyEx<ushort *>(HINSTANCE__ *,uint,ushort,long (*)(void *,unsigned __int64,ushort * *),void *,ushort * *)
0x180015c2a  test    eax, eax
0x180015c2c  js      short loc_180015C89
0x180015c2e  lea     rcx, aMaintaskinstru; "maintaskinstruction"
0x180015c35  call    cs:__imp_StrToID
0x180015c3b  movzx   edx, ax
0x180015c3e  mov     rcx, rdi
0x180015c41  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180015c47  mov     rbx, [rbp+bstrString]
0x180015c4b  mov     rcx, rax
0x180015c4e  mov     rdx, rbx
0x180015c51  call    cs:__imp_?SetContentString@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetContentString(ushort const *)
0x180015c57  test    eax, eax
0x180015c59  js      short loc_180015C80
0x180015c5b  lea     rcx, aMaintaskinstru; "maintaskinstruction"
0x180015c62  call    cs:__imp_StrToID
0x180015c68  movzx   edx, ax
0x180015c6b  mov     rcx, rdi
0x180015c6e  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180015c74  mov     rcx, rax
0x180015c77  mov     rdx, rbx
0x180015c7a  call    cs:__imp_?SetAccName@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetAccName(ushort const *)
0x180015c80  mov     rcx, rbx; pv
  ... truncated ...
```
