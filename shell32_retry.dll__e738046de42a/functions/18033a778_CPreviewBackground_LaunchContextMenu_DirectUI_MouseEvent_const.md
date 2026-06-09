# CPreviewBackground::_LaunchContextMenu(DirectUI::MouseEvent const *)

- ea: `0x18033a778`
- end: `0x18033aa06`
- name: `?_LaunchContextMenu@CPreviewBackground@@AEAAXPEBUMouseEvent@DirectUI@@@Z`
- size: `654`
- prototype: `void __fastcall(CPreviewBackground *__hidden this, const struct DirectUI::MouseEvent *)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1801515c0`

## callees

- `0x1800d4200`
- `0x180233280`
- `0x180298410`
- `0x18033a6d0`
- `0x18033a778`
- `0x18033aa0c`
- `0x1804d1d8c`
- `0x1804d5b88`
- `0x180571010`

## import_xrefs

- `USER32!CheckMenuItem` at `0x18033a8cd`
- `USER32!CheckMenuItem` at `0x18033a8e4`
- `USER32!CheckMenuItem` at `0x18033a8fb`
- `USER32!CheckMenuItem` at `0x18033a8cd`
- `USER32!CheckMenuItem` at `0x18033a8e4`
- `USER32!CheckMenuItem` at `0x18033a8fb`
- `USER32!EnableMenuItem` at `0x18033a85f`
- `USER32!EnableMenuItem` at `0x18033a85f`
- `USER32!RemoveMenu` at `0x18033a90d`
- `USER32!RemoveMenu` at `0x18033a91e`
- `USER32!RemoveMenu` at `0x18033a90d`
- `USER32!RemoveMenu` at `0x18033a91e`
- `USER32!DestroyMenu` at `0x18033a9d0`
- `USER32!DestroyMenu` at `0x18033a9d0`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x18033a7c0`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x18033a7c0`
- `SHLWAPI!__imp_SHLoadMenuPopup` at `0x18033a7da`
- `SHLWAPI!__imp_SHLoadMenuPopup` at `0x18033a7da`
- `DUI70!?GetBool@Value@DirectUI@@QEAA_NXZ` at `0x18033a888`
- `DUI70!?GetBool@Value@DirectUI@@QEAA_NXZ` at `0x18033a888`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18033a894`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18033a894`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x18033a87c`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x18033a87c`
- `DUI70!?IsRTL@Element@DirectUI@@QEAA_NXZ` at `0x18033a95f`
- `DUI70!?IsRTL@Element@DirectUI@@QEAA_NXZ` at `0x18033a95f`
- `PROPSYS!PSPropertyBag_WriteInt` at `0x18033a9bd`
- `PROPSYS!PSPropertyBag_WriteInt` at `0x18033a9bd`
- `PROPSYS!PSPropertyBag_ReadInt` at `0x18033a8ae`
- `PROPSYS!PSPropertyBag_ReadInt` at `0x18033a8ae`

## string_xrefs

- `0x18033a823`: `removeproperties`

## pseudocode

```c
void __fastcall CPreviewBackground::_LaunchContextMenu(IUnknown **this, const struct tagPOINT *a2)
{
  HMENU v4; // rsi
  __int64 v5; // r8
  UINT v6; // ebx
  DirectUI::Value *v7; // rbx
  bool Bool; // di
  UINT v9; // r8d
  UINT v10; // r8d
  UINT v11; // r8d
  struct DirectUI::Element *v12; // rcx
  bool IsRTL; // al
  int v14; // eax
  int v15; // eax
  int v16; // eax
  INT v17; // r8d
  int v18; // [rsp+20h] [rbp-50h]
  const struct tagRECT *v19; // [rsp+30h] [rbp-40h]
  struct tagRECT v20; // [rsp+40h] [rbp-30h] BYREF
  void *ppvOut; // [rsp+50h] [rbp-20h] BYREF
  struct IShellItemArray *v22; // [rsp+58h] [rbp-18h] BYREF
  INT value; // [rsp+60h] [rbp-10h] BYREF

  ppvOut = 0;
  if ( IUnknown_QueryService(
         this[27],
         &GUID_a3b24a0a_7b68_448d_9979_c700059c3ad1,
         &GUID_55272a00_42cb_11ce_8135_00aa004bb851,
         &ppvOut) >= 0 )
  {
    v4 = (HMENU)SHLoadMenuPopup(g_hinst, 502);
    if ( !v4 )
    {
LABEL_27:
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvOut + 16LL))(ppvOut);
      return;
    }
    v20.left = 0;
    v22 = 0;
    v6 = 1;
    if ( (int)CPreviewBackground::_GetSelection((CPreviewBackground *)this, &v22) >= 0 )
    {
      v19 = &v20;
      v18 = 1;
      SHIsVerbAvailableOnSelection(0, v22, v5, 1040);
      ((void (__fastcall *)(struct IShellItemArray *))v22->lpVtbl->Release)(v22);
      v6 = v20.left == 0;
    }
    EnableMenuItem(v4, 2u, v6);
    value = 0;
    v7 = DirectUI::Element::GetValue((DirectUI::Element *)this, CPreviewBackground::SizeMenuProp, 2, 0);
    Bool = DirectUI::Value::GetBool(v7);
    DirectUI::Value::Release(v7);
    if ( Bool && PSPropertyBag_ReadInt((IPropertyBag *)ppvOut, L"PreviewPaneSizer_Size", &value) >= 0 )
    {
      v9 = 0;
      if ( value == 52 )
        v9 = 8;
      CheckMenuItem(v4, 5u, v9);
      v10 = 0;
      if ( value == 70 )
        v10 = 8;
      CheckMenuItem(v4, 6u, v10);
      v11 = 0;
      if ( value == 106 )
        v11 = 8;
      CheckMenuItem(v4, 7u, v11);
    }
    else
    {
      RemoveMenu(v4, 4u, 0);
      RemoveMenu(v4, 0, 0x400u);
    }
    v12 = (struct DirectUI::Element *)*a2;
    *(_QWORD *)&v20.left = 0;
    if ( (int)DUI_GetMouseEventAbsolutePos(v12, a2 + 4, (struct tagPOINT *)&v20) >= 0 )
    {
      *(_QWORD *)&v20.right = 0;
      if ( (int)DUI_GetElementRootHWND((struct DirectUI::Element *)this, (HWND *)&v20.right) >= 0 )
      {
        IsRTL = DirectUI::Element::IsRTL((DirectUI::Element *)this);
        v14 = DUI_TrackPopupMenu(v4, 0x180u, v20.left, v20.top, v18, *(HWND *)&v20.right, v19, IsRTL) - 2;
        if ( !v14 )
        {
          CPreviewBackground::_RemoveProperties((CPreviewBackground *)this);
          goto LABEL_26;
        }
        v15 = v14 - 3;
        if ( !v15 )
        {
          v17 = 52;
          goto LABEL_24;
        }
        v16 = v15 - 1;
        if ( !v16 )
        {
          v17 = 70;
          goto LABEL_24;
        }
        if ( v16 == 1 )
        {
          v17 = 106;
LABEL_24:
          PSPropertyBag_WriteInt((IPropertyBag *)ppvOut, L"PreviewPaneSizer_Size", v17);
        }
      }
    }
LABEL_26:
    DestroyMenu(v4);
    goto LABEL_27;
  }
}

```

## disassembly

```asm
0x18033a778  mov     [rsp-28h+arg_10], rbx
0x18033a77d  push    rbp
0x18033a77e  push    rsi
0x18033a77f  push    rdi
0x18033a780  push    r14
0x18033a782  push    r15
0x18033a784  mov     rbp, rsp
0x18033a787  sub     rsp, 70h
0x18033a78b  mov     rax, cs:__security_cookie
0x18033a792  xor     rax, rsp
0x18033a795  mov     [rbp+var_8], rax
0x18033a799  mov     r15, rdx
0x18033a79c  mov     [rbp+ppvOut], 0
0x18033a7a4  mov     r14, rcx
0x18033a7a7  lea     rdx, _GUID_a3b24a0a_7b68_448d_9979_c700059c3ad1; guidService
0x18033a7ae  mov     rcx, [rcx+0D8h]; punk
0x18033a7b5  lea     r9, [rbp+ppvOut]; ppvOut
0x18033a7b9  lea     r8, _GUID_55272a00_42cb_11ce_8135_00aa004bb851; riid
0x18033a7c0  call    cs:__imp_IUnknown_QueryService
0x18033a7c6  test    eax, eax
0x18033a7c8  js      loc_18033A9E6
0x18033a7ce  mov     rcx, cs:g_hinst
0x18033a7d5  mov     edx, 1F6h
0x18033a7da  call    cs:__imp_SHLoadMenuPopup
0x18033a7e0  mov     rsi, rax
0x18033a7e3  test    rax, rax
0x18033a7e6  jz      loc_18033A9D6
0x18033a7ec  lea     rdx, [rbp+var_18]; struct IShellItemArray **
0x18033a7f0  mov     [rbp+var_30.left], 0
0x18033a7f7  mov     rcx, r14; this
0x18033a7fa  mov     [rbp+var_18], 0
0x18033a802  call    ?_GetSelection@CPreviewBackground@@AEAAJPEAPEAUIShellItemArray@@@Z; CPreviewBackground::_GetSelection(IShellItemArray * *)
0x18033a807  mov     ebx, 1
0x18033a80c  test    eax, eax
0x18033a80e  js      short loc_18033A852
0x18033a810  mov     rdx, [rbp+var_18]
0x18033a814  lea     rax, [rbp+var_30]
0x18033a818  mov     [rsp+70h+var_40], rax; struct tagRECT *
0x18033a81d  mov     r9d, 410h
0x18033a823  lea     rax, aRemoveproperti; "removeproperties"
0x18033a82a  xor     ecx, ecx
0x18033a82c  mov     [rsp+70h+var_48], rax
0x18033a831  mov     [rsp+70h+var_50], ebx; int
0x18033a835  call    ?SHIsVerbAvailableOnSelection@@YAJPEAUIUnknown@@PEAUIShellItemArray@@W4SHICOIA_FLAGS@@W4DEFAULT_FOLDER_MENU_RESTRICTIONS@@HPEBDPEAH@Z; SHIsVerbAvailableOnSelection(IUnknown *,IShellItemArray *,SHICOIA_FLAGS,DEFAULT_FOLDER_MENU_RESTRICTIONS,int,char const *,int *)
0x18033a83a  mov     rcx, [rbp+var_18]
0x18033a83e  mov     rax, [rcx]
0x18033a841  mov     rax, [rax+10h]
0x18033a845  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18033a84a  cmp     [rbp+var_30.left], 0
0x18033a84e  jz      short loc_18033A852
0x18033a850  xor     ebx, ebx
0x18033a852  mov     r8d, ebx; uEnable
0x18033a855  mov     rcx, rsi; hMenu
0x18033a858  mov     ebx, 2
0x18033a85d  mov     edx, ebx; uIDEnableItem
0x18033a85f  call    cs:__imp_EnableMenuItem
0x18033a865  xor     r9d, r9d
0x18033a868  mov     [rbp+value], 0
0x18033a86f  mov     r8d, ebx
0x18033a872  lea     rdx, ?SizeMenuProp@CPreviewBackground@@SAPEBUPropertyInfo@DirectUI@@XZ; CPreviewBackground::SizeMenuProp(void)
0x18033a879  mov     rcx, r14
0x18033a87c  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::UpdateCache *)
0x18033a882  mov     rcx, rax
0x18033a885  mov     rbx, rax
0x18033a888  call    cs:__imp_?GetBool@Value@DirectUI@@QEAA_NXZ; DirectUI::Value::GetBool(void)
0x18033a88e  mov     rcx, rbx
0x18033a891  mov     dil, al
0x18033a894  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x18033a89a  test    dil, dil
0x18033a89d  jz      short loc_18033A903
0x18033a89f  mov     rcx, [rbp+ppvOut]; propBag
0x18033a8a3  lea     r8, [rbp+value]; value
0x18033a8a7  lea     rdx, aPreviewpanesiz; "PreviewPaneSizer_Size"
0x18033a8ae  call    cs:__imp_PSPropertyBag_ReadInt
0x18033a8b4  test    eax, eax
0x18033a8b6  js      short loc_18033A903
0x18033a8b8  xor     r8d, r8d
0x18033a8bb  mov     rcx, rsi; hMenu
0x18033a8be  cmp     [rbp+value], 34h ; '4'
0x18033a8c2  lea     ebx, [r8+8]
0x18033a8c6  cmovz   r8d, ebx; uCheck
0x18033a8ca  lea     edx, [rbx-3]; uIDCheckItem
0x18033a8cd  call    cs:__imp_CheckMenuItem
0x18033a8d3  xor     r8d, r8d
0x18033a8d6  lea     edx, [rbx-2]; uIDCheckItem
0x18033a8d9  cmp     [rbp+value], 46h ; 'F'
0x18033a8dd  mov     rcx, rsi; hMenu
0x18033a8e0  cmovz   r8d, ebx; uCheck
0x18033a8e4  call    cs:__imp_CheckMenuItem
0x18033a8ea  xor     r8d, r8d
0x18033a8ed  lea     edx, [rbx-1]; uIDCheckItem
0x18033a8f0  cmp     [rbp+value], 6Ah ; 'j'
0x18033a8f4  mov     rcx, rsi; hMenu
0x18033a8f7  cmovz   r8d, ebx; uCheck
0x18033a8fb  call    cs:__imp_CheckMenuItem
0x18033a901  jmp     short loc_18033A924
0x18033a903  xor     r8d, r8d; uFlags
0x18033a906  mov     rcx, rsi; hMenu
0x18033a909  lea     edx, [r8+4]; uPosition
0x18033a90d  call    cs:__imp_RemoveMenu
0x18033a913  xor     edx, edx; uPosition
0x18033a915  mov     r8d, 400h; uFlags
0x18033a91b  mov     rcx, rsi; hMenu
0x18033a91e  call    cs:__imp_RemoveMenu
0x18033a924  mov     rcx, [r15]; struct DirectUI::Element *
0x18033a927  lea     rdx, [r15+20h]; struct tagPOINT *
0x18033a92b  lea     r8, [rbp+var_30]; struct tagPOINT *
0x18033a92f  mov     qword ptr [rbp+var_30.left], 0
0x18033a937  call    ?DUI_GetMouseEventAbsolutePos@@YAJPEAVElement@DirectUI@@PEBUtagPOINT@@PEAU3@@Z; DUI_GetMouseEventAbsolutePos(DirectUI::Element *,tagPOINT const *,tagPOINT *)
0x18033a93c  test    eax, eax
0x18033a93e  js      loc_18033A9CD
0x18033a944  lea     rdx, [rbp+var_30.right]; HWND *
0x18033a948  mov     qword ptr [rbp+var_30.right], 0
0x18033a950  mov     rcx, r14; struct DirectUI::Element *
0x18033a953  call    ?DUI_GetElementRootHWND@@YAJPEAVElement@DirectUI@@PEAPEAUHWND__@@@Z; DUI_GetElementRootHWND(DirectUI::Element *,HWND__ * *)
0x18033a958  test    eax, eax
0x18033a95a  js      short loc_18033A9CD
0x18033a95c  mov     rcx, r14
0x18033a95f  call    cs:__imp_?IsRTL@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::IsRTL(void)
0x18033a965  mov     r9d, [rbp+var_30.top]; int
0x18033a969  mov     edx, 180h; unsigned int
0x18033a96e  mov     r8d, [rbp+var_30.left]; int
0x18033a972  mov     rcx, rsi; HMENU
0x18033a975  movzx   eax, al
0x18033a978  mov     [rsp+70h+var_38], eax; int
0x18033a97c  mov     rax, qword ptr [rbp+var_30.right]
0x18033a980  mov     [rsp+70h+var_48], rax; HWND
0x18033a985  call    ?DUI_TrackPopupMenu@@YAHPEAUHMENU__@@IHHHPEAUHWND__@@PEBUtagRECT@@H@Z; DUI_TrackPopupMenu(HMENU__ *,uint,int,int,int,HWND__ *,tagRECT const *,int)
0x18033a98a  sub     eax, 2
0x18033a98d  jz      short loc_18033A9C5
0x18033a98f  sub     eax, 3
0x18033a992  jz      short loc_18033A9AC
0x18033a994  sub     eax, 1
0x18033a997  jz      short loc_18033A9A4
0x18033a999  cmp     eax, 1
0x18033a99c  jnz     short loc_18033A9CD
0x18033a99e  lea     r8d, [rax+69h]
0x18033a9a2  jmp     short loc_18033A9B2
0x18033a9a4  mov     r8d, 46h ; 'F'
0x18033a9aa  jmp     short loc_18033A9B2
0x18033a9ac  mov     r8d, 34h ; '4'; value
0x18033a9b2  mov     rcx, [rbp+ppvOut]; propBag
0x18033a9b6  lea     rdx, aPreviewpanesiz; "PreviewPaneSizer_Size"
0x18033a9bd  call    cs:__imp_PSPropertyBag_WriteInt
0x18033a9c3  jmp     short loc_18033A9CD
0x18033a9c5  mov     rcx, r14; this
0x18033a9c8  call    ?_RemoveProperties@CPreviewBackground@@AEAAXXZ; CPreviewBackground::_RemoveProperties(void)
0x18033a9cd  mov     rcx, rsi; hMenu
0x18033a9d0  call    cs:__imp_DestroyMenu
0x18033a9d6  mov     rcx, [rbp+ppvOut]
0x18033a9da  mov     rax, [rcx]
0x18033a9dd  mov     rax, [rax+10h]
0x18033a9e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18033a9e6  mov     rcx, [rbp+var_8]
0x18033a9ea  xor     rcx, rsp; StackCookie
0x18033a9ed  call    __security_check_cookie
0x18033a9f2  mov     rbx, [rsp+70h+arg_10]
0x18033a9fa  add     rsp, 70h
0x18033a9fe  pop     r15
0x18033aa00  pop     r14
0x18033aa02  pop     rdi
0x18033aa03  pop     rsi
0x18033aa04  pop     rbp
0x18033aa05  retn
```
