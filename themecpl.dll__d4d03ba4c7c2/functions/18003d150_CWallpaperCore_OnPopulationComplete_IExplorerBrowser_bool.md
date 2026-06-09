# CWallpaperCore::OnPopulationComplete(IExplorerBrowser *,bool)

- ea: `0x18003d150`
- end: `0x18003d4ee`
- name: `?OnPopulationComplete@CWallpaperCore@@UEAAJPEAUIExplorerBrowser@@_N@Z`
- size: `926`
- prototype: `__int64 __fastcall(CWallpaperCore *__hidden this, struct IExplorerBrowser *, bool)`
- caller_count: `0`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000d060`
- `0x18000d164`
- `0x18003b690`
- `0x18003d150`
- `0x18003fe5c`
- `0x1800426f0`
- `0x180042808`
- `0x180042c08`
- `0x180042dc0`
- `0x180057010`

## import_xrefs

- `SHELL32!SHCreateItemFromParsingName` at `0x18003d3ec`
- `SHELL32!SHCreateItemFromParsingName` at `0x18003d3ec`
- `SHELL32!__imp_ILIsEqual` at `0x18003d19b`
- `SHELL32!__imp_ILIsEqual` at `0x18003d19b`
- `SHELL32!__imp_ILFree` at `0x18003d4cb`
- `SHELL32!__imp_ILFree` at `0x18003d4cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d437`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d437`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18003d496`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18003d496`
- `DUI70!StrToID` at `0x18003d484`
- `DUI70!StrToID` at `0x18003d484`

## string_xrefs

- `0x18003d47d`: `ComboBox_PictureFolder`

## pseudocode

```c
__int64 __fastcall CWallpaperCore::OnPopulationComplete(CWallpaperCore *this, struct IExplorerBrowser *a2, char a3)
{
  HRESULT v4; // edi
  const ITEMIDLIST *CurrentFolder; // rax
  ITEMIDLIST *v8; // r14
  const ITEMIDLIST *v9; // rcx
  ITEMIDLIST *v10; // rax
  struct IExplorerBrowserVtbl *lpVtbl; // rax
  HRESULT v12; // eax
  __int64 v13; // rcx
  HRESULT v14; // eax
  HRESULT v15; // eax
  PCWSTR v16; // rcx
  __int64 v17; // rcx
  const wchar_t *v18; // rcx
  DirectUI::Element *v19; // rsi
  unsigned __int16 v20; // ax
  struct DirectUI::Element *Descendent; // rax
  CWallpaperCore *v22; // rcx
  struct IShellFolder *v24; // [rsp+20h] [rbp-20h] BYREF
  __int64 v25; // [rsp+28h] [rbp-18h] BYREF
  __int64 v26; // [rsp+30h] [rbp-10h] BYREF
  void *ppv; // [rsp+80h] [rbp+40h] BYREF
  int v28; // [rsp+90h] [rbp+50h] BYREF
  PCWSTR pszPath; // [rsp+98h] [rbp+58h] BYREF

  *((_BYTE *)this + 180) = 1;
  v4 = 0;
  CurrentFolder = (const ITEMIDLIST *)CWallpaperCore::GetCurrentFolder(this, 0);
  v8 = (ITEMIDLIST *)CurrentFolder;
  if ( a3 )
  {
    if ( *((_BYTE *)this + 181) || *((_BYTE *)this + 179) || !*((_QWORD *)this + 21) )
      goto LABEL_51;
  }
  else
  {
    v9 = (const ITEMIDLIST *)*((_QWORD *)this + 55);
    if ( v9 && CurrentFolder && !ILIsEqual(v9, CurrentFolder)
      || ((v10 = (ITEMIDLIST *)*((_QWORD *)this + 55)) == 0 || !v8) && v10 != v8 )
    {
      *((_BYTE *)this + 181) = 0;
      CWallpaperCore::_OnSelectPictureFolder(this);
      goto LABEL_51;
    }
  }
  lpVtbl = a2->lpVtbl;
  v26 = 0;
  v4 = ((__int64 (__fastcall *)(struct IExplorerBrowser *, GUID *, __int64 *))lpVtbl->GetCurrentView)(
         a2,
         &GUID_1af3a467_214f_4298_908e_06b03e0b39f9,
         &v26);
  if ( v4 >= 0 )
  {
    v24 = 0;
    v4 = (*(__int64 (__fastcall **)(__int64, GUID *, struct IShellFolder **))(*(_QWORD *)v26 + 40LL))(
           v26,
           &GUID_000214e6_0000_0000_c000_000000000046,
           &v24);
    if ( v4 < 0 )
    {
LABEL_44:
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
      goto LABEL_45;
    }
    if ( *((_BYTE *)this + 179) || a3 )
    {
      v28 = 0;
      if ( *((_BYTE *)this + 185) )
      {
        CWallpaperCore::_EnterStaticImageMode(this);
        *((_BYTE *)this + 75) = 0;
      }
      else if ( (*(int (__fastcall **)(_QWORD, int *))(**((_QWORD **)this + 52) + 136LL))(*((_QWORD *)this + 52), &v28) >= 0
             && (v28 & 2) != 0 )
      {
        v13 = *((_QWORD *)this + 52);
        pszPath = 0;
        v14 = (*(__int64 (__fastcall **)(__int64, PCWSTR *))(*(_QWORD *)v13 + 104LL))(v13, &pszPath);
        v4 = v14;
        if ( v14 == 1 )
        {
          v4 = -2147467259;
        }
        else if ( !v14 )
        {
          v25 = 0;
          if ( (*(int (__fastcall **)(PCWSTR, _QWORD, __int64 *))(*(_QWORD *)pszPath + 64LL))(pszPath, 0, &v25) >= 0 )
          {
            LODWORD(ppv) = 0;
            if ( (*(int (__fastcall **)(__int64, __int64, void **))(*(_QWORD *)v25 + 48LL))(v25, 0x20000000, &ppv) >= 0 )
            {
              if ( ((unsigned int)ppv & 0x20000000) != 0 )
                v15 = CBrowserFrame::SelectAll(*((CBrowserFrame **)this + 21));
              else
                v15 = CWallpaperCore::_SelectItems(this, (struct IShellItemArray *)pszPath, v24);
              v4 = v15;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
            }
          }
        }
        v16 = pszPath;
        pszPath = 0;
        if ( v16 )
          (*(void (__fastcall **)(PCWSTR))(*(_QWORD *)v16 + 16LL))(v16);
      }
      else
      {
        v17 = *((_QWORD *)this + 52);
        pszPath = 0;
        v4 = (*(__int64 (__fastcall **)(__int64, _QWORD, PCWSTR *))(*(_QWORD *)v17 + 32LL))(v17, 0, &pszPath);
        if ( v4 >= 0 )
        {
          if ( pszPath && *pszPath )
          {
            ppv = 0;
            v4 = SHCreateItemFromParsingName(pszPath, 0, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &ppv);
            if ( v4 >= 0 )
            {
              v4 = CWallpaperCore::_SelectionHelper(this, (struct IShellItem *)ppv, v24, 1);
              (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
            }
          }
          else
          {
            v4 = CBrowserFrame::SelectAll(*((CBrowserFrame **)this + 21));
          }
          CoTaskMemFree((LPVOID)pszPath);
        }
      }
      goto LABEL_43;
    }
    if ( *((_BYTE *)this + 185) )
    {
      v12 = CBrowserFrame::SelectItem(*((CBrowserFrame **)this + 21), 0, 1);
    }
    else
    {
      if ( !*((_BYTE *)this + 176) )
      {
LABEL_43:
        ((void (__fastcall *)(struct IShellFolder *))v24->lpVtbl->Release)(v24);
        goto LABEL_44;
      }
      v12 = CBrowserFrame::SelectAll(*((CBrowserFrame **)this + 21));
    }
    v4 = v12;
    goto LABEL_43;
  }
LABEL_45:
  if ( !*((_BYTE *)this + 179) )
  {
    v18 = L"Button_Browse";
    v19 = (DirectUI::Element *)*((_QWORD *)this + 4);
    if ( !*((_BYTE *)this + 76) )
      v18 = L"ComboBox_PictureFolder";
    v20 = StrToID(v18);
    Descendent = DirectUI::Element::FindDescendent(v19, v20);
    if ( Descendent )
      (*(void (__fastcall **)(struct DirectUI::Element *))(*(_QWORD *)Descendent + 168LL))(Descendent);
  }
  *((_WORD *)this + 90) = 0;
  *((_BYTE *)this + 179) = 0;
LABEL_51:
  ILFree(v8);
  CWallpaperCore::_PostChange(v22);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18003d150  push    rbp
0x18003d152  push    rbx
0x18003d153  push    rsi
0x18003d154  push    rdi
0x18003d155  push    r12
0x18003d157  push    r14
0x18003d159  push    r15
0x18003d15b  mov     rbp, rsp
0x18003d15e  sub     rsp, 40h
0x18003d162  mov     r15, rdx
0x18003d165  mov     byte ptr [rcx+0B4h], 1
0x18003d16c  xor     r12d, r12d
0x18003d16f  xor     edx, edx; struct _tagpropertykey *
0x18003d171  mov     edi, r12d
0x18003d174  mov     sil, r8b
0x18003d177  mov     rbx, rcx
0x18003d17a  call    ?GetCurrentFolder@CWallpaperCore@@AEBAPEAU_ITEMIDLIST_ABSOLUTE@@PEAU_tagpropertykey@@@Z; CWallpaperCore::GetCurrentFolder(_tagpropertykey *)
0x18003d17f  mov     r14, rax
0x18003d182  test    sil, sil
0x18003d185  jnz     short loc_18003D1D5
0x18003d187  mov     rcx, [rbx+1B8h]; pidl1
0x18003d18e  test    rcx, rcx
0x18003d191  jz      short loc_18003D1AB
0x18003d193  test    rax, rax
0x18003d196  jz      short loc_18003D1AB
0x18003d198  mov     rdx, rax; pidl2
0x18003d19b  call    cs:__imp_ILIsEqual
0x18003d1a2  nop     dword ptr [rax+rax+00h]
0x18003d1a7  test    eax, eax
0x18003d1a9  jz      short loc_18003D1C1
0x18003d1ab  mov     rax, [rbx+1B8h]
0x18003d1b2  test    rax, rax
0x18003d1b5  jz      short loc_18003D1BC
0x18003d1b7  test    r14, r14
0x18003d1ba  jnz     short loc_18003D1FC
0x18003d1bc  cmp     rax, r14
0x18003d1bf  jz      short loc_18003D1FC
0x18003d1c1  mov     rcx, rbx; this
0x18003d1c4  mov     [rbx+0B5h], r12b
0x18003d1cb  call    ?_OnSelectPictureFolder@CWallpaperCore@@AEAAXXZ; CWallpaperCore::_OnSelectPictureFolder(void)
0x18003d1d0  jmp     loc_18003D4C8
0x18003d1d5  cmp     [rbx+0B5h], r12b
0x18003d1dc  jnz     loc_18003D4C8
0x18003d1e2  cmp     [rbx+0B3h], r12b
0x18003d1e9  jnz     loc_18003D4C8
0x18003d1ef  cmp     [rbx+0A8h], r12
0x18003d1f6  jz      loc_18003D4C8
0x18003d1fc  mov     rax, [r15]
0x18003d1ff  lea     r8, [rbp+var_10]
0x18003d203  lea     rdx, _GUID_1af3a467_214f_4298_908e_06b03e0b39f9
0x18003d20a  mov     [rbp+var_10], r12
0x18003d20e  mov     rcx, r15
0x18003d211  mov     rax, [rax+88h]
0x18003d218  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d21d  mov     edi, eax
0x18003d21f  test    eax, eax
0x18003d221  js      loc_18003D463
0x18003d227  mov     rcx, [rbp+var_10]
0x18003d22b  lea     r8, [rbp+var_20]
0x18003d22f  mov     [rbp+var_20], r12
0x18003d233  lea     rdx, _GUID_000214e6_0000_0000_c000_000000000046
0x18003d23a  mov     rax, [rcx]
0x18003d23d  mov     rax, [rax+28h]
0x18003d241  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d246  mov     edi, eax
0x18003d248  test    eax, eax
0x18003d24a  js      loc_18003D453
0x18003d250  cmp     [rbx+0B3h], r12b
0x18003d257  jnz     short loc_18003D29A
0x18003d259  test    sil, sil
0x18003d25c  jnz     short loc_18003D29A
0x18003d25e  cmp     [rbx+0B9h], r12b
0x18003d265  jz      short loc_18003D27A
0x18003d267  mov     rcx, [rbx+0A8h]; this
0x18003d26e  mov     r8b, 1; bool
0x18003d271  xor     edx, edx; struct _ITEMID_CHILD *
0x18003d273  call    ?SelectItem@CBrowserFrame@@QEAAJPEFBU_ITEMID_CHILD@@_N@Z; CBrowserFrame::SelectItem(_ITEMID_CHILD const *,bool)
0x18003d278  jmp     short loc_18003D293
0x18003d27a  cmp     [rbx+0B0h], r12b
0x18003d281  jz      loc_18003D443
0x18003d287  mov     rcx, [rbx+0A8h]; this
0x18003d28e  call    ?SelectAll@CBrowserFrame@@QEAAJXZ; CBrowserFrame::SelectAll(void)
0x18003d293  mov     edi, eax
0x18003d295  jmp     loc_18003D443
0x18003d29a  mov     [rbp+arg_10], r12d
0x18003d29e  cmp     [rbx+0B9h], r12b
0x18003d2a5  jz      short loc_18003D2B8
0x18003d2a7  mov     rcx, rbx; this
0x18003d2aa  call    ?_EnterStaticImageMode@CWallpaperCore@@AEAAXXZ; CWallpaperCore::_EnterStaticImageMode(void)
0x18003d2af  mov     [rbx+4Bh], r12b
0x18003d2b3  jmp     loc_18003D443
0x18003d2b8  mov     rcx, [rbx+1A0h]
0x18003d2bf  lea     rdx, [rbp+arg_10]
0x18003d2c3  mov     rax, [rcx]
0x18003d2c6  mov     rax, [rax+88h]
0x18003d2cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d2d2  test    eax, eax
0x18003d2d4  js      loc_18003D3A9
0x18003d2da  test    byte ptr [rbp+arg_10], 2
0x18003d2de  jz      loc_18003D3A9
0x18003d2e4  mov     rcx, [rbx+1A0h]
0x18003d2eb  lea     rdx, [rbp+pszPath]
0x18003d2ef  mov     [rbp+pszPath], r12
0x18003d2f3  mov     rax, [rcx]
0x18003d2f6  mov     rax, [rax+68h]
0x18003d2fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d2ff  mov     edi, eax
0x18003d301  cmp     eax, 1
0x18003d304  jnz     short loc_18003D30D
0x18003d306  mov     edi, 80004005h
0x18003d30b  jmp     short loc_18003D387
0x18003d30d  test    eax, eax
0x18003d30f  jnz     short loc_18003D387
0x18003d311  mov     rcx, [rbp+pszPath]
0x18003d315  lea     r8, [rbp+var_18]
0x18003d319  mov     [rbp+var_18], r12
0x18003d31d  xor     edx, edx
0x18003d31f  mov     rax, [rcx]
0x18003d322  mov     rax, [rax+40h]
0x18003d326  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d32b  test    eax, eax
0x18003d32d  js      short loc_18003D387
0x18003d32f  mov     rcx, [rbp+var_18]
0x18003d333  lea     r8, [rbp+ppv]
0x18003d337  mov     dword ptr [rbp+ppv], r12d
0x18003d33b  mov     esi, 20000000h
0x18003d340  mov     edx, esi
0x18003d342  mov     rax, [rcx]
0x18003d345  mov     rax, [rax+30h]
0x18003d349  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d34e  test    eax, eax
0x18003d350  js      short loc_18003D387
0x18003d352  test    dword ptr [rbp+ppv], esi
0x18003d355  jz      short loc_18003D365
0x18003d357  mov     rcx, [rbx+0A8h]; this
0x18003d35e  call    ?SelectAll@CBrowserFrame@@QEAAJXZ; CBrowserFrame::SelectAll(void)
0x18003d363  jmp     short loc_18003D375
0x18003d365  mov     r8, [rbp+var_20]; struct IShellFolder *
0x18003d369  mov     rcx, rbx; this
0x18003d36c  mov     rdx, [rbp+pszPath]; struct IShellItemArray *
0x18003d370  call    ?_SelectItems@CWallpaperCore@@AEAAJPEAUIShellItemArray@@PEAUIShellFolder@@@Z; CWallpaperCore::_SelectItems(IShellItemArray *,IShellFolder *)
0x18003d375  mov     rcx, [rbp+var_18]
0x18003d379  mov     edi, eax
0x18003d37b  mov     rax, [rcx]
0x18003d37e  mov     rax, [rax+10h]
0x18003d382  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d387  mov     rcx, [rbp+pszPath]
0x18003d38b  mov     [rbp+pszPath], r12
0x18003d38f  test    rcx, rcx
0x18003d392  jz      loc_18003D443
0x18003d398  mov     rax, [rcx]
0x18003d39b  mov     rax, [rax+10h]
0x18003d39f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d3a4  jmp     loc_18003D443
0x18003d3a9  mov     rcx, [rbx+1A0h]
0x18003d3b0  lea     r8, [rbp+pszPath]
0x18003d3b4  mov     [rbp+pszPath], r12
0x18003d3b8  xor     edx, edx
0x18003d3ba  mov     rax, [rcx]
0x18003d3bd  mov     rax, [rax+20h]
0x18003d3c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d3c6  mov     edi, eax
0x18003d3c8  test    eax, eax
0x18003d3ca  js      short loc_18003D443
0x18003d3cc  mov     rcx, [rbp+pszPath]; pszPath
0x18003d3d0  test    rcx, rcx
0x18003d3d3  jz      short loc_18003D425
0x18003d3d5  cmp     [rcx], r12w
0x18003d3d9  jz      short loc_18003D425
0x18003d3db  lea     r9, [rbp+ppv]; ppv
0x18003d3df  mov     [rbp+ppv], r12
0x18003d3e3  lea     r8, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x18003d3ea  xor     edx, edx; pbc
0x18003d3ec  call    cs:__imp_SHCreateItemFromParsingName
0x18003d3f3  nop     dword ptr [rax+rax+00h]
0x18003d3f8  mov     edi, eax
0x18003d3fa  test    eax, eax
0x18003d3fc  js      short loc_18003D433
0x18003d3fe  mov     r8, [rbp+var_20]; struct IShellFolder *
0x18003d402  mov     r9b, 1; bool
0x18003d405  mov     rdx, [rbp+ppv]; struct IShellItem *
0x18003d409  mov     rcx, rbx; this
0x18003d40c  call    ?_SelectionHelper@CWallpaperCore@@AEAAJPEAUIShellItem@@PEAUIShellFolder@@_N@Z; CWallpaperCore::_SelectionHelper(IShellItem *,IShellFolder *,bool)
0x18003d411  mov     rcx, [rbp+ppv]
0x18003d415  mov     edi, eax
0x18003d417  mov     rax, [rcx]
0x18003d41a  mov     rax, [rax+10h]
0x18003d41e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d423  jmp     short loc_18003D433
0x18003d425  mov     rcx, [rbx+0A8h]; this
0x18003d42c  call    ?SelectAll@CBrowserFrame@@QEAAJXZ; CBrowserFrame::SelectAll(void)
0x18003d431  mov     edi, eax
0x18003d433  mov     rcx, [rbp+pszPath]; pv
0x18003d437  call    cs:__imp_CoTaskMemFree
0x18003d43e  nop     dword ptr [rax+rax+00h]
0x18003d443  mov     rcx, [rbp+var_20]
0x18003d447  mov     rax, [rcx]
0x18003d44a  mov     rax, [rax+10h]
0x18003d44e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d453  mov     rcx, [rbp+var_10]
0x18003d457  mov     rax, [rcx]
0x18003d45a  mov     rax, [rax+10h]
0x18003d45e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d463  cmp     [rbx+0B3h], r12b
0x18003d46a  jnz     short loc_18003D4B9
0x18003d46c  lea     rcx, aButtonBrowse; "Button_Browse"
0x18003d473  mov     rsi, [rbx+20h]
0x18003d477  cmp     [rbx+4Ch], r12b
0x18003d47b  jnz     short loc_18003D484
0x18003d47d  lea     rcx, aComboboxPictur; "ComboBox_PictureFolder"
0x18003d484  call    cs:__imp_StrToID
0x18003d48b  nop     dword ptr [rax+rax+00h]
0x18003d490  movzx   edx, ax
0x18003d493  mov     rcx, rsi
0x18003d496  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18003d49d  nop     dword ptr [rax+rax+00h]
0x18003d4a2  mov     rcx, rax
0x18003d4a5  test    rax, rax
0x18003d4a8  jz      short loc_18003D4B9
0x18003d4aa  mov     rax, [rax]
0x18003d4ad  mov     rax, [rax+0A8h]
0x18003d4b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d4b9  mov     [rbx+0B4h], r12w
0x18003d4c1  mov     [rbx+0B3h], r12b
0x18003d4c8  mov     rcx, r14; pidl
0x18003d4cb  call    cs:__imp_ILFree
0x18003d4d2  nop     dword ptr [rax+rax+00h]
0x18003d4d7  call    ?_PostChange@CWallpaperCore@@AEAAXXZ; CWallpaperCore::_PostChange(void)
0x18003d4dc  mov     eax, edi
0x18003d4de  add     rsp, 40h
0x18003d4e2  pop     r15
0x18003d4e4  pop     r14
0x18003d4e6  pop     r12
0x18003d4e8  pop     rdi
0x18003d4e9  pop     rsi
0x18003d4ea  pop     rbx
0x18003d4eb  pop     rbp
0x18003d4ec  retn
```
