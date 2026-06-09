# CDefView::CreateViewWindow3(IShellBrowser *,IShellView *,ulong,FOLDERFLAGS,FOLDERFLAGS,FOLDERVIEWMODE,_GUID const *,tagRECT const *,HWND__ * *)

- ea: `0x18005bb90`
- end: `0x18005c482`
- name: `?CreateViewWindow3@CDefView@@UEAAJPEAUIShellBrowser@@PEAUIShellView@@KW4FOLDERFLAGS@@2W4FOLDERVIEWMODE@@PEBU_GUID@@PEBUtagRECT@@PEAPEAUHWND__@@@Z`
- size: `2290`
- prototype: `__int64 __usercall@<rax>(CDefView *__hidden this@<rcx>, struct IShellBrowser *@<rdx>, struct IShellView *@<r8>, unsigned int@<r9d>, enum FOLDERFLAGS, enum FOLDERFLAGS, FOLDERVIEWMODE, const struct _GUID *, const struct tagRECT *, HWND *)`
- caller_count: `1`
- callee_count: `25`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1802c3fc0`

## callees

- `0x18000d4b0`
- `0x18000d4c0`
- `0x18000f05c`
- `0x18000f5a4`
- `0x180054f88`
- `0x18005a844`
- `0x18005bb90`
- `0x18005c488`
- `0x18005c7a0`
- `0x18005d940`
- `0x18005da10`
- `0x18005daa4`
- `0x18005dd0c`
- `0x18005dd78`
- `0x18005dd98`
- `0x18005e4c8`
- `0x18006b4d0`
- `0x180113028`
- `0x180117bdc`
- `0x180155d98`
- `0x180156efc`
- `0x18015efb4`
- `0x180233280`
- `0x1802d40ec`
- `0x180571010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005bbe6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005bbe6`
- `USER32!CreateWindowExW` at `0x18005bf1e`
- `USER32!CreateWindowExW` at `0x18005bf1e`
- `USER32!GetWindowLongW` at `0x18005bea0`
- `USER32!GetWindowLongW` at `0x18005bea0`
- `USER32!PostMessageW` at `0x18005c0b0`
- `USER32!PostMessageW` at `0x18005c0b0`
- `USER32!SetCursor` at `0x18005c1ec`
- `USER32!SetCursor` at `0x18005c1ec`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x18005bcc8`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x18005bceb`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x18005bdb4`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x18005c188`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x18005c225`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x18005bcc8`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x18005bceb`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x18005bdb4`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x18005c188`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x18005c225`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_SetSite` at `0x18005bc12`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_SetSite` at `0x18005bc22`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_SetSite` at `0x18005bc12`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_SetSite` at `0x18005bc22`
- `SHCORE!__imp_IUnknown_ProfferService` at `0x18005c282`
- `SHCORE!__imp_IUnknown_ProfferService` at `0x18005c346`
- `SHCORE!__imp_IUnknown_ProfferService` at `0x18005c442`
- `SHCORE!__imp_IUnknown_ProfferService` at `0x18005c282`
- `SHCORE!__imp_IUnknown_ProfferService` at `0x18005c346`
- `SHCORE!__imp_IUnknown_ProfferService` at `0x18005c442`
- `ole32!RegisterDragDrop` at `0x18005c243`
- `ole32!RegisterDragDrop` at `0x18005c243`
- `Windows.Storage!ViewModeFromSVID` at `0x18005c3a2`
- `Windows.Storage!ViewModeFromSVID` at `0x18005c3a2`

## string_xrefs

- `0x18005bd02`: `CreateViewWindow`
- `0x18005c19f`: `CreateViewWindow`
- `0x18005bf14`: `SHELLDLL_DefView`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CDefView::CreateViewWindow3(
        CDefView *this,
        struct IShellBrowser *a2,
        IUnknown *a3,
        int a4,
        enum FOLDERFLAGS a5,
        enum FOLDERFLAGS a6,
        FOLDERVIEWMODE a7,
        const struct _GUID *a8,
        const struct tagRECT *a9,
        HWND *a10)
{
  __int64 v13; // rcx
  HWND *v14; // r15
  __int64 v15; // rcx
  __int64 v16; // rcx
  CDefView *v17; // rcx
  LONG Y; // r15d
  LONG bottom; // ebx
  LONG X; // r12d
  LONG right; // esi
  DWORD v22; // r14d
  int nHeight; // ebx
  int nWidth; // esi
  HWND Window; // rbx
  __int64 v26; // rcx
  int (__fastcall ***v27)(_QWORD, GUID *, void **); // rcx
  __int64 v28; // rcx
  int v29; // eax
  unsigned int v30; // eax
  char v31; // si
  int InitialCollection; // ebx
  __int64 v33; // rcx
  const struct _GUID *v34; // rcx
  HWND v36; // rcx
  int v37; // eax
  enum FOLDERVIEWMODE v38; // ecx
  enum FOLDERLOGICALVIEWMODE v39; // eax
  __int64 v40; // r8
  __int64 v41; // r9
  __int64 v42; // [rsp+60h] [rbp-59h] BYREF
  HCURSOR hCursor; // [rsp+68h] [rbp-51h]
  HWND hWndParent; // [rsp+70h] [rbp-49h]
  HWND *v45; // [rsp+78h] [rbp-41h]
  IUnknown *punk; // [rsp+80h] [rbp-39h]
  void *ppvOut; // [rsp+88h] [rbp-31h] BYREF
  ULONG_PTR ulCookie; // [rsp+90h] [rbp-29h] BYREF
  int v49; // [rsp+98h] [rbp-21h] BYREF
  void *v50; // [rsp+A0h] [rbp-19h] BYREF
  void *v51; // [rsp+A8h] [rbp-11h] BYREF

  LODWORD(v50) = a4;
  punk = a3;
  v45 = a10;
  *a10 = 0;
  *((_DWORD *)this + 363) = GetCurrentThreadId();
  if ( *((_QWORD *)this + 90) || !a2 )
    return 2147549183LL;
  IUnknown_SetSite(*((IUnknown **)this + 116), (IUnknown *)this);
  IUnknown_SetSite(*((IUnknown **)this + 172), (IUnknown *)this);
  v49 = 0;
  v13 = *((_QWORD *)this + 116);
  if ( v13
    && (*(int (__fastcall **)(__int64, __int64, _QWORD, int *))(*(_QWORD *)v13 + 24LL))(v13, 100, 0, &v49) >= 0
    && v49 )
  {
    return 2147942405LL;
  }
  *((_QWORD *)this + 80) = a2;
  ((void (__fastcall *)(struct IShellBrowser *))a2->lpVtbl->AddRef)(a2);
  v14 = (HWND *)((char *)this + 712);
  (*(void (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 80) + 24LL))(*((_QWORD *)this + 80), (char *)this + 712);
  v15 = *((_QWORD *)this + 116);
  if ( v15 )
    (*(void (__fastcall **)(__int64, __int64, _QWORD, HWND))(*(_QWORD *)v15 + 24LL))(v15, 46, 0, *v14);
  CAutoWaitCursor::CAutoWaitCursor((CAutoWaitCursor *)&v42, *((struct IUnknown **)this + 80));
  SafeRelease<IUpdatableItemSet>((char *)this + 1360);
  IUnknown_QueryService(
    *((IUnknown **)this + 80),
    &IID_ITrackEvents,
    &GUID_f002a70d_e74b_4721_9243_5704338cfc2f,
    (void **)this + 170);
  ppvOut = 0;
  if ( IUnknown_QueryService((IUnknown *)this, &IID_ITrackEvents, &GUID_f002a70d_e74b_4721_9243_5704338cfc2f, &ppvOut) >= 0 )
  {
    (*(void (__fastcall **)(void *, const wchar_t *, _QWORD, _QWORD))(*(_QWORD *)ppvOut + 24LL))(
      ppvOut,
      L"CreateViewWindow",
      0,
      0);
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppvOut + 16LL))(ppvOut);
  }
  IUnknown_BeginBrowserProgressSession(*((struct IUnknown **)this + 80), (unsigned int *)this + 308);
  (***((void (__fastcall ****)(_QWORD, GUID *, char *))this + 78))(
    *((_QWORD *)this + 78),
    &GUID_000214e5_0000_0000_c000_000000000046,
    (char *)this + 680);
  (***((void (__fastcall ****)(_QWORD, GUID *, char *))this + 78))(
    *((_QWORD *)this + 78),
    &GUID_7d688a70_c613_11d0_999b_00c04fd655e1,
    (char *)this + 688);
  ((void (__fastcall *)(struct IShellBrowser *, GUID *, char *))a2->lpVtbl->QueryInterface)(
    a2,
    &GUID_000214f1_0000_0000_c000_000000000046,
    (char *)this + 648);
  ATL::CComPtr<IClassFactory>::CComPtr<IClassFactory>(&v51);
  *((_DWORD *)this + 373) = IUnknown_QueryService(
                              *((IUnknown **)this + 18),
                              (const GUID *const)&SID_TouchViewController,
                              &GUID_00000000_0000_0000_c000_000000000046,
                              &v51) == 0;
  *((_DWORD *)this + 360) |= a5;
  CDefView::_ApplySettings(this, 0, 0);
  v16 = *((_QWORD *)this + 116);
  if ( v16 )
    (*(void (__fastcall **)(__int64, __int64, _QWORD, IUnknown *))(*(_QWORD *)v16 + 24LL))(v16, 99, 0, a3);
  (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 172) + 72LL))(
    *((_QWORD *)this + 172),
    (unsigned int)a5,
    (unsigned int)a6);
  *((_DWORD *)this + 222) &= ~0x10000000u;
  *((_DWORD *)this + 222) |= ((unsigned __int8)a6 & (unsigned __int8)a5 & 0x20) != 0 ? 0x10000000 : 0;
  if ( ((unsigned __int8)v50 & 2) != 0 )
  {
    if ( !a8 || (unsigned int)IsEqualGUID(a8, &VID_DefaultView) )
    {
      v38 = a7;
      if ( (unsigned int)(a7 - 1) > 7 )
        goto LABEL_11;
    }
    else
    {
      LODWORD(ppvOut) = 0;
      if ( (int)ViewModeFromSVID(a8, &ppvOut) < 0 )
        goto LABEL_11;
      v38 = (int)ppvOut;
    }
    v39 = LogicalViewModeFromViewMode(v38);
    (*(void (__fastcall **)(__int64, _QWORD, __int64))(v40 + 56))(v41, (unsigned int)v39, 0xFFFFFFFFLL);
  }
LABEL_11:
  CDefView::_InitFromPreviousView(this, (struct IShellView *)a3);
  GetStackedKeyFromIDList(0, *((struct IShellFolder **)this + 78), (struct _tagpropertykey *)((char *)this + 1024));
  *((_DWORD *)this + 358) = *((_QWORD *)this + 79) != 0;
  CDefView::_RegisterWindow(v17);
  ppvOut = g_hinst;
  hWndParent = *v14;
  Y = a9->top;
  bottom = a9->bottom;
  X = a9->left;
  right = a9->right;
  v22 = GetWindowLongW(hWndParent, -20) & 0x400000;
  ulCookie = 0;
  if ( !(unsigned int)SHActivateContext(&ulCookie) )
    goto LABEL_58;
  nHeight = bottom - Y;
  nWidth = right - X;
  if ( g_hActCtx != (HANDLE)-3LL )
    DelayLoadCC();
  Window = CreateWindowExW(
             v22,
             L"SHELLDLL_DefView",
             0,
             0x46010000u,
             X,
             Y,
             nWidth,
             nHeight,
             hWndParent,
             0,
             (HINSTANCE)ppvOut,
             this);
  SHDeactivateContext(ulCookie);
  if ( Window )
  {
    *v45 = (HWND)*((_QWORD *)this + 90);
    v26 = *((_QWORD *)this + 116);
    if ( v26 )
      (*(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v26 + 24LL))(v26, 15, *((_QWORD *)this + 90));
    ppvOut = 0;
    v27 = (int (__fastcall ***)(_QWORD, GUID *, void **))*((_QWORD *)this + 80);
    if ( v27 && (**v27)(v27, &GUID_2f7325e3_dd2c_4f75_b966_9bed1737491c, &ppvOut) >= 0 )
    {
      (*(void (__fastcall **)(void *, _QWORD))(*(_QWORD *)ppvOut + 24LL))(ppvOut, *((_QWORD *)this + 90));
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvOut + 16LL))(ppvOut);
    }
    v28 = *((_QWORD *)this + 116);
    if ( v28 )
      v29 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, char *))(*(_QWORD *)v28 + 24LL))(
              v28,
              94,
              0,
              (char *)this + 504);
    else
      v29 = -2147467263;
    *((_DWORD *)this + 131) = v29 >= 0;
    CDefView::_ApplySettings(this, 0, 1);
    *((_DWORD *)this + 280) = 1;
    *((_DWORD *)this + 222) |= 0x4000u;
    ulCookie = 0;
    if ( (***((int (__fastcall ****)(_QWORD, GUID *, ULONG_PTR *))this + 80))(
           *((_QWORD *)this + 80),
           &GUID_c8ad25a1_3294_41ee_8165_71174bd01c57,
           &ulCookie) >= 0 )
    {
      (*(void (__fastcall **)(ULONG_PTR, CDefView *))(*(_QWORD *)ulCookie + 88LL))(ulCookie, this);
      (*(void (__fastcall **)(ULONG_PTR))(*(_QWORD *)ulCookie + 16LL))(ulCookie);
    }
    if ( (int)CDefView::_LoadPersistedHistory((IUnknown *)this) < 0 && !*((_DWORD *)this + 373) )
      CDefView::_SelectFromPreviousView(this, punk);
    if ( (CDefView::_GetViewFlags(this) & 0x1000) != 0 )
    {
      InitialCollection = 0;
    }
    else
    {
      v30 = ~(unsigned __int8)((unsigned int)CDefView::_GetViewFlags(this) >> 5) & 0x40 | 0x10;
      v31 = (char)v50;
      if ( ((unsigned __int8)v50 & 1) == 0 )
        v30 |= 8u;
      if ( ((unsigned __int8)v50 & 8) == 0 )
        v30 |= 1u;
      InitialCollection = CDefView::_CreateInitialCollection(this, v30);
      if ( InitialCollection < 0 )
      {
        CDefView::_DestroyView(this, 1);
      }
      else
      {
        (*(void (__fastcall **)(_QWORD, _QWORD, GUID *, char *))(**((_QWORD **)this + 78) + 64LL))(
          *((_QWORD *)this + 78),
          *((_QWORD *)this + 89),
          &GUID_00000122_0000_0000_c000_000000000046,
          (char *)this + 800);
        if ( (*((_DWORD *)this + 222) & 0x10000000) == 0 )
        {
          ATL::CComPtr<IClassFactory>::CComPtr<IClassFactory>(&v50);
          if ( IUnknown_QueryService(
                 *((IUnknown **)this + 18),
                 (const GUID *const)&SID_SNoViewDropTarget,
                 &GUID_00000000_0000_0000_c000_000000000046,
                 &v50) < 0 )
          {
            v36 = (HWND)*((_QWORD *)this + 91);
            if ( v36 )
              v37 = RegisterDragDrop(v36, (LPDROPTARGET)this + 8) >= 0;
            else
              v37 = 0;
            *((_DWORD *)this + 222) &= ~0x200u;
            *((_DWORD *)this + 222) |= v37 << 9;
          }
          ATL::CComPtr<IUICommandWithBackgroundColor>::~CComPtr<IUICommandWithBackgroundColor>(&v50);
        }
        PostMessageW(*((HWND *)this + 90), 0x4A5u, 0, 0);
        v33 = *((_QWORD *)this + 116);
        if ( v33 && (*(int (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v33 + 24LL))(v33, 20, 0) >= 0 )
          CDefView::_AddCopyHook(this);
        v34 = (const struct _GUID *)*((_QWORD *)this + 18);
        if ( v34 || (v34 = (const struct _GUID *)*((_QWORD *)this + 80)) != 0 )
        {
          *((_QWORD *)this + 178) = v34;
          (*(void (__fastcall **)(const struct _GUID *))(*(_QWORD *)&v34->Data1 + 8LL))(v34);
          if ( !*((_DWORD *)this + 251) )
            IUnknown_ProfferService(*((_QWORD *)this + 178), &IID_IFolderView, (char *)this + 200);
          if ( !*((_DWORD *)this + 252) )
            IUnknown_ProfferService(*((_QWORD *)this + 178), &IID_INewMenuClient, (char *)this + 200);
          if ( !*((_DWORD *)this + 253) )
            IUnknown_ProfferService(
              *((_QWORD *)this + 178),
              &GUID_831d1dff_7f57_4720_87e4_cb57d6214428,
              (char *)this + 200);
        }
        if ( (*((_DWORD *)this + 222) & 0x10000000) == 0 && (v31 & 0x10) == 0 )
          GetUIThreadThumbnailCache(v34, (void **)this + 176);
      }
    }
  }
  else
  {
LABEL_58:
    InitialCollection = -2147467259;
  }
  ATL::CComPtr<IUICommandWithBackgroundColor>::~CComPtr<IUICommandWithBackgroundColor>(&v51);
  if ( v42 )
  {
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v42 + 40LL))(v42, 0);
  }
  else
  {
    SetCursor(hCursor);
    hCursor = 0;
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
  ulCookie = 0;
  if ( IUnknown_QueryService(
         (IUnknown *)this,
         &IID_ITrackEvents,
         &GUID_f002a70d_e74b_4721_9243_5704338cfc2f,
         (void **)&ulCookie) >= 0 )
  {
    (*(void (__fastcall **)(ULONG_PTR, const wchar_t *, _QWORD, __int64))(*(_QWORD *)ulCookie + 24LL))(
      ulCookie,
      L"CreateViewWindow",
      0,
      1);
    (*(void (__fastcall **)(ULONG_PTR))(*(_QWORD *)ulCookie + 16LL))(ulCookie);
  }
  return (unsigned int)InitialCollection;
}

```

## disassembly

```asm
0x18005bb90  mov     [rsp-8+arg_18], rbx
0x18005bb95  push    rbp
0x18005bb96  push    rsi
0x18005bb97  push    rdi
0x18005bb98  push    r12
0x18005bb9a  push    r13
0x18005bb9c  push    r14
0x18005bb9e  push    r15
0x18005bba0  lea     rbp, [rsp-7]
0x18005bba5  sub     rsp, 0C0h
0x18005bbac  mov     rax, cs:__security_cookie
0x18005bbb3  xor     rax, rsp
0x18005bbb6  mov     [rbp+37h+var_40], rax
0x18005bbba  mov     dword ptr [rbp+37h+var_50], r9d
0x18005bbbe  mov     r12, r8
0x18005bbc1  mov     [rbp+37h+punk], r8
0x18005bbc5  mov     rsi, rdx
0x18005bbc8  mov     rdi, rcx
0x18005bbcb  mov     r13, [rbp+37h+arg_40]
0x18005bbd2  mov     r14, [rbp+37h+arg_38]
0x18005bbd6  mov     rax, [rbp+37h+arg_48]
0x18005bbdd  mov     [rbp+37h+var_78], rax
0x18005bbe1  xor     ebx, ebx
0x18005bbe3  mov     [rax], rbx
0x18005bbe6  call    cs:__imp_GetCurrentThreadId
0x18005bbec  mov     [rdi+5ACh], eax
0x18005bbf2  cmp     [rdi+2D0h], rbx
0x18005bbf9  jnz     loc_18005C478
0x18005bbff  test    rsi, rsi
0x18005bc02  jz      loc_18005C478
0x18005bc08  mov     rdx, rdi; punkSite
0x18005bc0b  mov     rcx, [rdi+3A0h]; punk
0x18005bc12  call    cs:__imp_IUnknown_SetSite
0x18005bc18  mov     rdx, rdi; punkSite
0x18005bc1b  mov     rcx, [rdi+560h]; punk
0x18005bc22  call    cs:__imp_IUnknown_SetSite
0x18005bc28  mov     [rbp+37h+var_58], ebx
0x18005bc2b  mov     rcx, [rdi+3A0h]
0x18005bc32  test    rcx, rcx
0x18005bc35  jnz     loc_18005C2FF
0x18005bc3b  mov     [rdi+280h], rsi
0x18005bc42  mov     rax, [rsi]
0x18005bc45  mov     rcx, rsi
0x18005bc48  mov     rax, [rax+8]
0x18005bc4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bc51  mov     rcx, [rdi+280h]
0x18005bc58  lea     r15, [rdi+2C8h]
0x18005bc5f  mov     rax, [rcx]
0x18005bc62  mov     rdx, r15
0x18005bc65  mov     rax, [rax+18h]
0x18005bc69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bc6e  mov     rcx, [rdi+3A0h]
0x18005bc75  test    rcx, rcx
0x18005bc78  jz      short loc_18005BC90
0x18005bc7a  mov     rax, [rcx]
0x18005bc7d  mov     r9, [r15]
0x18005bc80  xor     r8d, r8d
0x18005bc83  lea     edx, [r8+2Eh]
0x18005bc87  mov     rax, [rax+18h]
0x18005bc8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bc90  mov     rdx, [rdi+280h]; struct IUnknown *
0x18005bc97  lea     rcx, [rbp+37h+var_90]; this
0x18005bc9b  call    ??0CAutoWaitCursor@@QEAA@PEAUIUnknown@@@Z; CAutoWaitCursor::CAutoWaitCursor(IUnknown *)
0x18005bca0  nop
0x18005bca1  lea     rbx, [rdi+550h]
0x18005bca8  mov     rcx, rbx
0x18005bcab  call    ??$SafeRelease@UIUpdatableItemSet@@@@YAXPEAPEAUIUpdatableItemSet@@@Z; SafeRelease<IUpdatableItemSet>(IUpdatableItemSet * *)
0x18005bcb0  mov     r9, rbx; ppvOut
0x18005bcb3  lea     r8, _GUID_f002a70d_e74b_4721_9243_5704338cfc2f; riid
0x18005bcba  lea     rdx, IID_ITrackEvents; guidService
0x18005bcc1  mov     rcx, [rdi+280h]; punk
0x18005bcc8  call    cs:__imp_IUnknown_QueryService
0x18005bcce  mov     [rbp+37h+ppvOut], 0
0x18005bcd6  lea     r9, [rbp+37h+ppvOut]; ppvOut
0x18005bcda  lea     r8, _GUID_f002a70d_e74b_4721_9243_5704338cfc2f; riid
0x18005bce1  lea     rdx, IID_ITrackEvents; guidService
0x18005bce8  mov     rcx, rdi; punk
0x18005bceb  call    cs:__imp_IUnknown_QueryService
0x18005bcf1  test    eax, eax
0x18005bcf3  js      short loc_18005BD22
0x18005bcf5  mov     rcx, [rbp+37h+ppvOut]
0x18005bcf9  mov     rax, [rcx]
0x18005bcfc  xor     r9d, r9d
0x18005bcff  xor     r8d, r8d
0x18005bd02  lea     rdx, aCreateviewwind; "CreateViewWindow"
0x18005bd09  mov     rax, [rax+18h]
0x18005bd0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bd12  mov     rcx, [rbp+37h+ppvOut]
0x18005bd16  mov     rax, [rcx]
0x18005bd19  mov     rax, [rax+10h]
0x18005bd1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bd22  lea     rdx, [rdi+4D0h]; unsigned int *
0x18005bd29  mov     rcx, [rdi+280h]; struct IUnknown *
0x18005bd30  call    ?IUnknown_BeginBrowserProgressSession@@YAJPEAUIUnknown@@PEAK@Z; IUnknown_BeginBrowserProgressSession(IUnknown *,ulong *)
0x18005bd35  mov     rcx, [rdi+270h]
0x18005bd3c  mov     rax, [rcx]
0x18005bd3f  lea     r8, [rdi+2A8h]
0x18005bd46  lea     rdx, _GUID_000214e5_0000_0000_c000_000000000046
0x18005bd4d  mov     rax, [rax]
0x18005bd50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bd55  mov     rcx, [rdi+270h]
0x18005bd5c  mov     rax, [rcx]
0x18005bd5f  lea     r8, [rdi+2B0h]
0x18005bd66  lea     rdx, _GUID_7d688a70_c613_11d0_999b_00c04fd655e1
0x18005bd6d  mov     rax, [rax]
0x18005bd70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bd75  mov     rax, [rsi]
0x18005bd78  lea     r8, [rdi+288h]
0x18005bd7f  lea     rdx, _GUID_000214f1_0000_0000_c000_000000000046
0x18005bd86  mov     rcx, rsi
0x18005bd89  mov     rax, [rax]
0x18005bd8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bd91  lea     rcx, [rbp+37h+var_48]; void *
0x18005bd95  call    ??0?$CComPtr@UIClassFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IClassFactory>::CComPtr<IClassFactory>(void)
0x18005bd9a  nop
0x18005bd9b  lea     r9, [rbp+37h+var_48]; ppvOut
0x18005bd9f  lea     r8, _GUID_00000000_0000_0000_c000_000000000046; riid
0x18005bda6  lea     rdx, SID_TouchViewController; guidService
0x18005bdad  mov     rcx, [rdi+90h]; punk
0x18005bdb4  call    cs:__imp_IUnknown_QueryService
0x18005bdba  xor     ecx, ecx
0x18005bdbc  test    eax, eax
0x18005bdbe  setz    cl
0x18005bdc1  mov     [rdi+5D4h], ecx
0x18005bdc7  mov     ebx, [rbp+37h+arg_20]
0x18005bdca  or      [rdi+5A0h], ebx
0x18005bdd0  xor     r8d, r8d; int
0x18005bdd3  xor     edx, edx; int
0x18005bdd5  mov     rcx, rdi; this
0x18005bdd8  call    ?_ApplySettings@CDefView@@AEAAXHH@Z; CDefView::_ApplySettings(int,int)
0x18005bddd  mov     rcx, [rdi+3A0h]
0x18005bde4  test    rcx, rcx
0x18005bde7  jz      short loc_18005BDFF
0x18005bde9  mov     rax, [rcx]
0x18005bdec  mov     r9, r12
0x18005bdef  xor     r8d, r8d
0x18005bdf2  lea     edx, [r8+63h]
0x18005bdf6  mov     rax, [rax+18h]
0x18005bdfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bdff  mov     rcx, [rdi+560h]
0x18005be06  mov     rax, [rcx]
0x18005be09  mov     r8d, [rbp+37h+arg_28]
0x18005be0d  mov     edx, ebx
0x18005be0f  mov     rax, [rax+48h]
0x18005be13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005be18  btr     dword ptr [rdi+378h], 1Ch
0x18005be20  and     ebx, [rbp+37h+arg_28]
0x18005be23  and     bl, 20h
0x18005be26  neg     bl
0x18005be28  sbb     eax, eax
0x18005be2a  and     eax, 10000000h
0x18005be2f  or      [rdi+378h], eax
0x18005be35  test    byte ptr [rbp+37h+var_50], 2
0x18005be39  jnz     loc_18005C380
0x18005be3f  mov     rdx, r12; struct IShellView *
0x18005be42  mov     rcx, rdi; this
0x18005be45  call    ?_InitFromPreviousView@CDefView@@AEAAXPEAUIShellView@@@Z; CDefView::_InitFromPreviousView(IShellView *)
0x18005be4a  lea     r8, [rdi+400h]; struct _tagpropertykey *
0x18005be51  mov     rdx, [rdi+270h]; struct IShellFolder *
0x18005be58  xor     ecx, ecx; pidl
0x18005be5a  call    ?GetStackedKeyFromIDList@@YAJPEBU_ITEMIDLIST_ABSOLUTE@@PEAUIShellFolder@@PEAU_tagpropertykey@@@Z; GetStackedKeyFromIDList(_ITEMIDLIST_ABSOLUTE const *,IShellFolder *,_tagpropertykey *)
0x18005be5f  xor     eax, eax
0x18005be61  cmp     [rdi+278h], rax
0x18005be68  setnz   al
0x18005be6b  mov     [rdi+598h], eax
0x18005be71  call    ?_RegisterWindow@CDefView@@AEAAXXZ; CDefView::_RegisterWindow(void)
0x18005be76  mov     rax, cs:g_hinst
0x18005be7d  mov     [rbp+37h+ppvOut], rax
0x18005be81  mov     rax, [r15]
0x18005be84  mov     [rbp+37h+var_80], rax
0x18005be88  mov     r15d, [r13+4]
0x18005be8c  mov     ebx, [r13+0Ch]
0x18005be90  mov     r12d, [r13+0]
0x18005be94  mov     esi, [r13+8]
0x18005be98  mov     edx, 0FFFFFFECh; nIndex
0x18005be9d  mov     rcx, rax; hWnd
0x18005bea0  call    cs:__imp_GetWindowLongW
0x18005bea6  mov     r14d, eax
0x18005bea9  and     r14d, 400000h
0x18005beb0  xor     r13d, r13d
0x18005beb3  mov     [rbp+37h+ulCookie], r13
0x18005beb7  lea     rcx, [rbp+37h+ulCookie]
0x18005bebb  call    SHActivateContext
0x18005bec0  test    eax, eax
0x18005bec2  jz      loc_18005C351
0x18005bec8  sub     ebx, r15d
0x18005becb  sub     esi, r12d
0x18005bece  cmp     cs:g_hActCtx, 0FFFFFFFFFFFFFFFDh
0x18005bed6  jz      short loc_18005BEDD
0x18005bed8  call    DelayLoadCC
0x18005bedd  mov     [rsp+0F0h+lpParam], rdi; lpParam
0x18005bee2  mov     rax, [rbp+37h+ppvOut]
0x18005bee6  mov     [rsp+0F0h+hInstance], rax; hInstance
0x18005beeb  mov     [rsp+0F0h+hMenu], r13; hMenu
0x18005bef0  mov     rax, [rbp+37h+var_80]
0x18005bef4  mov     [rsp+0F0h+hWndParent], rax; hWndParent
0x18005bef9  mov     [rsp+0F0h+nHeight], ebx; nHeight
0x18005befd  mov     [rsp+0F0h+nWidth], esi; nWidth
0x18005bf01  mov     [rsp+0F0h+Y], r15d; Y
0x18005bf06  mov     [rsp+0F0h+X], r12d; X
0x18005bf0b  mov     r9d, 46010000h; dwStyle
0x18005bf11  xor     r8d, r8d; lpWindowName
0x18005bf14  lea     rdx, aShelldllDefvie; "SHELLDLL_DefView"
0x18005bf1b  mov     ecx, r14d; dwExStyle
0x18005bf1e  call    cs:__imp_CreateWindowExW
0x18005bf24  mov     rbx, rax
0x18005bf27  mov     rcx, [rbp+37h+ulCookie]; ulCookie
0x18005bf2b  call    SHDeactivateContext
0x18005bf30  test    rbx, rbx
0x18005bf33  jz      loc_18005C351
0x18005bf39  mov     rax, [rdi+2D0h]
0x18005bf40  mov     rcx, [rbp+37h+var_78]
0x18005bf44  mov     [rcx], rax
0x18005bf47  mov     rcx, [rdi+3A0h]
0x18005bf4e  test    rcx, rcx
0x18005bf51  jz      short loc_18005BF6D
0x18005bf53  mov     rax, [rcx]
0x18005bf56  xor     r9d, r9d
0x18005bf59  mov     r8, [rdi+2D0h]
0x18005bf60  lea     edx, [r9+0Fh]
0x18005bf64  mov     rax, [rax+18h]
0x18005bf68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bf6d  mov     [rbp+37h+ppvOut], r13
0x18005bf71  mov     rcx, [rdi+280h]
0x18005bf78  test    rcx, rcx
0x18005bf7b  jnz     loc_18005C28D
0x18005bf81  mov     rcx, [rdi+3A0h]
0x18005bf88  test    rcx, rcx
0x18005bf8b  jz      loc_18005C361
0x18005bf91  mov     rax, [rcx]
0x18005bf94  lea     r9, [rdi+1F8h]
0x18005bf9b  xor     r8d, r8d
0x18005bf9e  lea     edx, [r8+5Eh]
0x18005bfa2  mov     rax, [rax+18h]
0x18005bfa6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bfab  not     eax
0x18005bfad  shr     eax, 1Fh
0x18005bfb0  mov     [rdi+20Ch], eax
0x18005bfb6  mov     r14d, 1
0x18005bfbc  mov     r8d, r14d; int
0x18005bfbf  xor     edx, edx; int
0x18005bfc1  mov     rcx, rdi; this
0x18005bfc4  call    ?_ApplySettings@CDefView@@AEAAXHH@Z; CDefView::_ApplySettings(int,int)
0x18005bfc9  mov     [rdi+460h], r14d
0x18005bfd0  bts     dword ptr [rdi+378h], 0Eh
0x18005bfd8  mov     [rbp+37h+ulCookie], r13
0x18005bfdc  mov     rcx, [rdi+280h]
0x18005bfe3  mov     rax, [rcx]
0x18005bfe6  lea     r8, [rbp+37h+ulCookie]
0x18005bfea  lea     rdx, _GUID_c8ad25a1_3294_41ee_8165_71174bd01c57
0x18005bff1  mov     rax, [rax]
0x18005bff4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bff9  test    eax, eax
0x18005bffb  jns     loc_18005C2D7
0x18005c001  mov     rcx, rdi; punkSite
0x18005c004  call    ?_LoadPersistedHistory@CDefView@@AEAAJXZ; CDefView::_LoadPersistedHistory(void)
0x18005c009  test    eax, eax
0x18005c00b  js      loc_18005C3EA
0x18005c011  mov     rcx, rdi
0x18005c014  call    ?_GetViewFlags@CDefView@@AEAA?AW4BROWSER_VIEW_FLAGS@@XZ; CDefView::_GetViewFlags(void)
0x18005c019  bt      eax, 0Ch
0x18005c01d  jb      loc_18005C1FB
0x18005c023  mov     rcx, rdi
0x18005c026  call    ?_GetViewFlags@CDefView@@AEAA?AW4BROWSER_VIEW_FLAGS@@XZ; CDefView::_GetViewFlags(void)
0x18005c02b  shr     eax, 5
0x18005c02e  not     eax
0x18005c030  and     eax, 40h
0x18005c033  or      eax, 10h
0x18005c036  mov     esi, dword ptr [rbp+37h+var_50]
0x18005c039  test    r14b, sil
0x18005c03c  jz      loc_18005C408
0x18005c042  test    sil, 8
0x18005c046  jz      loc_18005C410
0x18005c04c  mov     edx, eax
0x18005c04e  mov     rcx, rdi
0x18005c051  call    ?_CreateInitialCollection@CDefView@@AEAAJW4UPDATE_FLAGS@@@Z; CDefView::_CreateInitialCollection(UPDATE_FLAGS)
0x18005c056  mov     ebx, eax
0x18005c058  test    eax, eax
0x18005c05a  js      loc_18005C468
0x18005c060  mov     r10, [rdi+270h]
0x18005c067  mov     rcx, [r10]
0x18005c06a  lea     r9, [rdi+320h]
0x18005c071  mov     rax, [rcx+40h]
0x18005c075  lea     r8, _GUID_00000122_0000_0000_c000_000000000046
0x18005c07c  mov     rdx, [rdi+2C8h]
0x18005c083  mov     rcx, r10
0x18005c086  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c08b  mov     r15d, 10000000h
0x18005c091  test    [rdi+378h], r15d
0x18005c098  jz      loc_18005C203
0x18005c09e  xor     r9d, r9d; lParam
0x18005c0a1  xor     r8d, r8d; wParam
0x18005c0a4  mov     edx, 4A5h; Msg
0x18005c0a9  mov     rcx, [rdi+2D0h]; hWnd
0x18005c0b0  call    cs:__imp_PostMessageW
0x18005c0b6  mov     rcx, [rdi+3A0h]
0x18005c0bd  test    rcx, rcx
0x18005c0c0  jz      short loc_18005C0E0
0x18005c0c2  mov     rax, [rcx]
0x18005c0c5  xor     r9d, r9d
  ... truncated ...
```
