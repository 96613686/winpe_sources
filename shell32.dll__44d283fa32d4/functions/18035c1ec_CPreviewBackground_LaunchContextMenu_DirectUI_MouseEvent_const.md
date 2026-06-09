# CPreviewBackground::_LaunchContextMenu(DirectUI::MouseEvent const *)

- ea: `0x18035c1ec`
- end: `0x18035c4d5`
- name: `?_LaunchContextMenu@CPreviewBackground@@AEAAXPEBUMouseEvent@DirectUI@@@Z`
- size: `745`
- prototype: `void __fastcall(CPreviewBackground *__hidden this, const struct DirectUI::MouseEvent *)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180162050`

## callees

- `0x1800903c8`
- `0x180249490`
- `0x1802b2160`
- `0x18035c140`
- `0x18035c1ec`
- `0x18035c4dc`
- `0x18050b934`
- `0x18050fbd4`
- `0x1805b2010`

## import_xrefs

- `USER32!CheckMenuItem` at `0x18035c36b`
- `USER32!CheckMenuItem` at `0x18035c388`
- `USER32!CheckMenuItem` at `0x18035c3a5`
- `USER32!CheckMenuItem` at `0x18035c36b`
- `USER32!CheckMenuItem` at `0x18035c388`
- `USER32!CheckMenuItem` at `0x18035c3a5`
- `USER32!EnableMenuItem` at `0x18035c2df`
- `USER32!EnableMenuItem` at `0x18035c2df`
- `USER32!RemoveMenu` at `0x18035c3bd`
- `USER32!RemoveMenu` at `0x18035c3d4`
- `USER32!RemoveMenu` at `0x18035c3bd`
- `USER32!RemoveMenu` at `0x18035c3d4`
- `USER32!DestroyMenu` at `0x18035c498`
- `USER32!DestroyMenu` at `0x18035c498`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x18035c234`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x18035c234`
- `SHLWAPI!__imp_SHLoadMenuPopup` at `0x18035c254`
- `SHLWAPI!__imp_SHLoadMenuPopup` at `0x18035c254`
- `DUI70!?GetBool@Value@DirectUI@@QEAA_NXZ` at `0x18035c314`
- `DUI70!?GetBool@Value@DirectUI@@QEAA_NXZ` at `0x18035c314`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18035c326`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18035c326`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x18035c302`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x18035c302`
- `DUI70!?IsRTL@Element@DirectUI@@QEAA_NXZ` at `0x18035c41b`
- `DUI70!?IsRTL@Element@DirectUI@@QEAA_NXZ` at `0x18035c41b`
- `PROPSYS!PSPropertyBag_WriteInt` at `0x18035c47f`
- `PROPSYS!PSPropertyBag_WriteInt` at `0x18035c47f`
- `PROPSYS!PSPropertyBag_ReadInt` at `0x18035c346`
- `PROPSYS!PSPropertyBag_ReadInt` at `0x18035c346`

## string_xrefs

- `0x18035c2a3`: `removeproperties`

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
0x18035c1ec  mov     [rsp-28h+arg_10], rbx
0x18035c1f1  push    rbp
0x18035c1f2  push    rsi
0x18035c1f3  push    rdi
0x18035c1f4  push    r14
0x18035c1f6  push    r15
0x18035c1f8  mov     rbp, rsp
0x18035c1fb  sub     rsp, 70h
0x18035c1ff  mov     rax, cs:__security_cookie
0x18035c206  xor     rax, rsp
0x18035c209  mov     [rbp+var_8], rax
0x18035c20d  mov     r15, rdx
0x18035c210  mov     [rbp+ppvOut], 0
0x18035c218  mov     r14, rcx
0x18035c21b  lea     rdx, _GUID_a3b24a0a_7b68_448d_9979_c700059c3ad1; guidService
0x18035c222  mov     rcx, [rcx+0D8h]; punk
0x18035c229  lea     r9, [rbp+ppvOut]; ppvOut
0x18035c22d  lea     r8, _GUID_55272a00_42cb_11ce_8135_00aa004bb851; riid
0x18035c234  call    cs:__imp_IUnknown_QueryService
0x18035c23b  nop     dword ptr [rax+rax+00h]
0x18035c240  test    eax, eax
0x18035c242  js      loc_18035C4B4
0x18035c248  mov     rcx, cs:g_hinst
0x18035c24f  mov     edx, 1F6h
0x18035c254  call    cs:__imp_SHLoadMenuPopup
0x18035c25b  nop     dword ptr [rax+rax+00h]
0x18035c260  mov     rsi, rax
0x18035c263  test    rax, rax
0x18035c266  jz      loc_18035C4A4
0x18035c26c  lea     rdx, [rbp+var_18]; struct IShellItemArray **
0x18035c270  mov     [rbp+var_30.left], 0
0x18035c277  mov     rcx, r14; this
0x18035c27a  mov     [rbp+var_18], 0
0x18035c282  call    ?_GetSelection@CPreviewBackground@@AEAAJPEAPEAUIShellItemArray@@@Z; CPreviewBackground::_GetSelection(IShellItemArray * *)
0x18035c287  mov     ebx, 1
0x18035c28c  test    eax, eax
0x18035c28e  js      short loc_18035C2D2
0x18035c290  mov     rdx, [rbp+var_18]
0x18035c294  lea     rax, [rbp+var_30]
0x18035c298  mov     [rsp+70h+var_40], rax; struct tagRECT *
0x18035c29d  mov     r9d, 410h
0x18035c2a3  lea     rax, aRemoveproperti; "removeproperties"
0x18035c2aa  xor     ecx, ecx
0x18035c2ac  mov     [rsp+70h+var_48], rax
0x18035c2b1  mov     [rsp+70h+var_50], ebx; int
0x18035c2b5  call    ?SHIsVerbAvailableOnSelection@@YAJPEAUIUnknown@@PEAUIShellItemArray@@W4SHICOIA_FLAGS@@W4DEFAULT_FOLDER_MENU_RESTRICTIONS@@HPEBDPEAH@Z; SHIsVerbAvailableOnSelection(IUnknown *,IShellItemArray *,SHICOIA_FLAGS,DEFAULT_FOLDER_MENU_RESTRICTIONS,int,char const *,int *)
0x18035c2ba  mov     rcx, [rbp+var_18]
0x18035c2be  mov     rax, [rcx]
0x18035c2c1  mov     rax, [rax+10h]
0x18035c2c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18035c2ca  cmp     [rbp+var_30.left], 0
0x18035c2ce  jz      short loc_18035C2D2
0x18035c2d0  xor     ebx, ebx
0x18035c2d2  mov     r8d, ebx; uEnable
0x18035c2d5  mov     rcx, rsi; hMenu
0x18035c2d8  mov     ebx, 2
0x18035c2dd  mov     edx, ebx; uIDEnableItem
0x18035c2df  call    cs:__imp_EnableMenuItem
0x18035c2e6  nop     dword ptr [rax+rax+00h]
0x18035c2eb  xor     r9d, r9d
0x18035c2ee  mov     [rbp+value], 0
0x18035c2f5  mov     r8d, ebx
0x18035c2f8  lea     rdx, ?SizeMenuProp@CPreviewBackground@@SAPEBUPropertyInfo@DirectUI@@XZ; CPreviewBackground::SizeMenuProp(void)
0x18035c2ff  mov     rcx, r14
0x18035c302  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::UpdateCache *)
0x18035c309  nop     dword ptr [rax+rax+00h]
0x18035c30e  mov     rcx, rax
0x18035c311  mov     rbx, rax
0x18035c314  call    cs:__imp_?GetBool@Value@DirectUI@@QEAA_NXZ; DirectUI::Value::GetBool(void)
0x18035c31b  nop     dword ptr [rax+rax+00h]
0x18035c320  mov     rcx, rbx
0x18035c323  mov     dil, al
0x18035c326  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x18035c32d  nop     dword ptr [rax+rax+00h]
0x18035c332  test    dil, dil
0x18035c335  jz      short loc_18035C3B3
0x18035c337  mov     rcx, [rbp+ppvOut]; propBag
0x18035c33b  lea     r8, [rbp+value]; value
0x18035c33f  lea     rdx, aPreviewpanesiz; "PreviewPaneSizer_Size"
0x18035c346  call    cs:__imp_PSPropertyBag_ReadInt
0x18035c34d  nop     dword ptr [rax+rax+00h]
0x18035c352  test    eax, eax
0x18035c354  js      short loc_18035C3B3
0x18035c356  xor     r8d, r8d
0x18035c359  mov     rcx, rsi; hMenu
0x18035c35c  cmp     [rbp+value], 34h ; '4'
0x18035c360  lea     ebx, [r8+8]
0x18035c364  cmovz   r8d, ebx; uCheck
0x18035c368  lea     edx, [rbx-3]; uIDCheckItem
0x18035c36b  call    cs:__imp_CheckMenuItem
0x18035c372  nop     dword ptr [rax+rax+00h]
0x18035c377  xor     r8d, r8d
0x18035c37a  lea     edx, [rbx-2]; uIDCheckItem
0x18035c37d  cmp     [rbp+value], 46h ; 'F'
0x18035c381  mov     rcx, rsi; hMenu
0x18035c384  cmovz   r8d, ebx; uCheck
0x18035c388  call    cs:__imp_CheckMenuItem
0x18035c38f  nop     dword ptr [rax+rax+00h]
0x18035c394  xor     r8d, r8d
0x18035c397  lea     edx, [rbx-1]; uIDCheckItem
0x18035c39a  cmp     [rbp+value], 6Ah ; 'j'
0x18035c39e  mov     rcx, rsi; hMenu
0x18035c3a1  cmovz   r8d, ebx; uCheck
0x18035c3a5  call    cs:__imp_CheckMenuItem
0x18035c3ac  nop     dword ptr [rax+rax+00h]
0x18035c3b1  jmp     short loc_18035C3E0
0x18035c3b3  xor     r8d, r8d; uFlags
0x18035c3b6  mov     rcx, rsi; hMenu
0x18035c3b9  lea     edx, [r8+4]; uPosition
0x18035c3bd  call    cs:__imp_RemoveMenu
0x18035c3c4  nop     dword ptr [rax+rax+00h]
0x18035c3c9  xor     edx, edx; uPosition
0x18035c3cb  mov     r8d, 400h; uFlags
0x18035c3d1  mov     rcx, rsi; hMenu
0x18035c3d4  call    cs:__imp_RemoveMenu
0x18035c3db  nop     dword ptr [rax+rax+00h]
0x18035c3e0  mov     rcx, [r15]; struct DirectUI::Element *
0x18035c3e3  lea     rdx, [r15+20h]; struct tagPOINT *
0x18035c3e7  lea     r8, [rbp+var_30]; struct tagPOINT *
0x18035c3eb  mov     qword ptr [rbp+var_30.left], 0
0x18035c3f3  call    ?DUI_GetMouseEventAbsolutePos@@YAJPEAVElement@DirectUI@@PEBUtagPOINT@@PEAU3@@Z; DUI_GetMouseEventAbsolutePos(DirectUI::Element *,tagPOINT const *,tagPOINT *)
0x18035c3f8  test    eax, eax
0x18035c3fa  js      loc_18035C495
0x18035c400  lea     rdx, [rbp+var_30.right]; HWND *
0x18035c404  mov     qword ptr [rbp+var_30.right], 0
0x18035c40c  mov     rcx, r14; struct DirectUI::Element *
0x18035c40f  call    ?DUI_GetElementRootHWND@@YAJPEAVElement@DirectUI@@PEAPEAUHWND__@@@Z; DUI_GetElementRootHWND(DirectUI::Element *,HWND__ * *)
0x18035c414  test    eax, eax
0x18035c416  js      short loc_18035C495
0x18035c418  mov     rcx, r14
0x18035c41b  call    cs:__imp_?IsRTL@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::IsRTL(void)
0x18035c422  nop     dword ptr [rax+rax+00h]
0x18035c427  mov     r9d, [rbp+var_30.top]; int
0x18035c42b  mov     edx, 180h; unsigned int
0x18035c430  mov     r8d, [rbp+var_30.left]; int
0x18035c434  mov     rcx, rsi; HMENU
0x18035c437  movzx   eax, al
0x18035c43a  mov     [rsp+70h+var_38], eax; int
0x18035c43e  mov     rax, qword ptr [rbp+var_30.right]
0x18035c442  mov     [rsp+70h+var_48], rax; HWND
0x18035c447  call    ?DUI_TrackPopupMenu@@YAHPEAUHMENU__@@IHHHPEAUHWND__@@PEBUtagRECT@@H@Z; DUI_TrackPopupMenu(HMENU__ *,uint,int,int,int,HWND__ *,tagRECT const *,int)
0x18035c44c  sub     eax, 2
0x18035c44f  jz      short loc_18035C48D
0x18035c451  sub     eax, 3
0x18035c454  jz      short loc_18035C46E
0x18035c456  sub     eax, 1
0x18035c459  jz      short loc_18035C466
0x18035c45b  cmp     eax, 1
0x18035c45e  jnz     short loc_18035C495
0x18035c460  lea     r8d, [rax+69h]
0x18035c464  jmp     short loc_18035C474
0x18035c466  mov     r8d, 46h ; 'F'
0x18035c46c  jmp     short loc_18035C474
0x18035c46e  mov     r8d, 34h ; '4'; value
0x18035c474  mov     rcx, [rbp+ppvOut]; propBag
0x18035c478  lea     rdx, aPreviewpanesiz; "PreviewPaneSizer_Size"
0x18035c47f  call    cs:__imp_PSPropertyBag_WriteInt
0x18035c486  nop     dword ptr [rax+rax+00h]
0x18035c48b  jmp     short loc_18035C495
0x18035c48d  mov     rcx, r14; this
0x18035c490  call    ?_RemoveProperties@CPreviewBackground@@AEAAXXZ; CPreviewBackground::_RemoveProperties(void)
0x18035c495  mov     rcx, rsi; hMenu
0x18035c498  call    cs:__imp_DestroyMenu
0x18035c49f  nop     dword ptr [rax+rax+00h]
0x18035c4a4  mov     rcx, [rbp+ppvOut]
0x18035c4a8  mov     rax, [rcx]
0x18035c4ab  mov     rax, [rax+10h]
0x18035c4af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18035c4b4  mov     rcx, [rbp+var_8]
0x18035c4b8  xor     rcx, rsp; StackCookie
0x18035c4bb  call    __security_check_cookie
0x18035c4c0  mov     rbx, [rsp+70h+arg_10]
0x18035c4c8  add     rsp, 70h
0x18035c4cc  pop     r15
0x18035c4ce  pop     r14
0x18035c4d0  pop     rdi
0x18035c4d1  pop     rsi
0x18035c4d2  pop     rbp
0x18035c4d3  retn
```
