# CDefView::CreateViewWindow3(IShellBrowser *,IShellView *,ulong,FOLDERFLAGS,FOLDERFLAGS,FOLDERVIEWMODE,_GUID const *,tagRECT const *,HWND__ * *)

- ea: `0x18002bca0`
- end: `0x18002c5f2`
- name: `?CreateViewWindow3@CDefView@@UEAAJPEAUIShellBrowser@@PEAUIShellView@@KW4FOLDERFLAGS@@2W4FOLDERVIEWMODE@@PEBU_GUID@@PEBUtagRECT@@PEAPEAUHWND__@@@Z`
- size: `2386`
- prototype: `__int64 __usercall@<rax>(CDefView *__hidden this@<rcx>, struct IShellBrowser *@<rdx>, struct IShellView *@<r8>, unsigned int@<r9d>, enum FOLDERFLAGS, enum FOLDERFLAGS, FOLDERVIEWMODE, const struct _GUID *, const struct tagRECT *, HWND *)`
- caller_count: `1`
- callee_count: `26`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1802e13b0`

## callees

- `0x18000cfe8`
- `0x18000d180`
- `0x18000d220`
- `0x18000d240`
- `0x18000f6cc`
- `0x18000fc30`
- `0x18001e550`
- `0x18002a830`
- `0x18002bca0`
- `0x18002c5f8`
- `0x18002d860`
- `0x18002d938`
- `0x18002d9d8`
- `0x18002dc4c`
- `0x18002dcbc`
- `0x18002dce4`
- `0x18002dd80`
- `0x18002e668`
- `0x18005b4f8`
- `0x18005fd00`
- `0x1801246c0`
- `0x1801679e0`
- `0x180167b3c`
- `0x180249490`
- `0x1802f1e70`
- `0x1805b2010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002bcf6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002bcf6`
- `USER32!CreateWindowExW` at `0x18002c058`
- `USER32!CreateWindowExW` at `0x18002c058`
- `USER32!GetWindowLongW` at `0x18002bfd4`
- `USER32!GetWindowLongW` at `0x18002bfd4`
- `USER32!PostMessageW` at `0x18002c1f1`
- `USER32!PostMessageW` at `0x18002c1f1`
- `USER32!SetCursor` at `0x18002c33a`
- `USER32!SetCursor` at `0x18002c33a`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_SetSite` at `0x18002bd28`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_SetSite` at `0x18002bd3e`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_SetSite` at `0x18002bd28`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_SetSite` at `0x18002bd3e`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x18002bdea`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x18002be13`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x18002bee2`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x18002c2cf`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x18002c371`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x18002bdea`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x18002be13`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x18002bee2`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x18002c2cf`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x18002c371`
- `SHCORE!__imp_IUnknown_ProfferService` at `0x18002c3da`
- `SHCORE!__imp_IUnknown_ProfferService` at `0x18002c4a4`
- `SHCORE!__imp_IUnknown_ProfferService` at `0x18002c5ac`
- `SHCORE!__imp_IUnknown_ProfferService` at `0x18002c3da`
- `SHCORE!__imp_IUnknown_ProfferService` at `0x18002c4a4`
- `SHCORE!__imp_IUnknown_ProfferService` at `0x18002c5ac`
- `ole32!RegisterDragDrop` at `0x18002c395`
- `ole32!RegisterDragDrop` at `0x18002c395`
- `Windows.Storage!ViewModeFromSVID` at `0x18002c506`
- `Windows.Storage!ViewModeFromSVID` at `0x18002c506`

## string_xrefs

- `0x18002be30`: `CreateViewWindow`
- `0x18002c2ec`: `CreateViewWindow`
- `0x18002c04e`: `SHELLDLL_DefView`

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
  int InitialCollection; // ebx
  __int64 v27; // rcx
  int (__fastcall ***v28)(_QWORD, GUID *, void **); // rcx
  __int64 v29; // rcx
  int v30; // eax
  unsigned int v31; // eax
  char v32; // si
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
    goto LABEL_57;
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
    InitialCollection = 0;
    *v45 = (HWND)*((_QWORD *)this + 90);
    v27 = *((_QWORD *)this + 116);
    if ( v27 )
      (*(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v27 + 24LL))(v27, 15, *((_QWORD *)this + 90));
    ppvOut = 0;
    v28 = (int (__fastcall ***)(_QWORD, GUID *, void **))*((_QWORD *)this + 80);
    if ( v28 && (**v28)(v28, &GUID_2f7325e3_dd2c_4f75_b966_9bed1737491c, &ppvOut) >= 0 )
    {
      (*(void (__fastcall **)(void *, _QWORD))(*(_QWORD *)ppvOut + 24LL))(ppvOut, *((_QWORD *)this + 90));
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvOut + 16LL))(ppvOut);
    }
    v29 = *((_QWORD *)this + 116);
    if ( v29 )
      v30 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, char *))(*(_QWORD *)v29 + 24LL))(
              v29,
              94,
              0,
              (char *)this + 504);
    else
      v30 = -2147467263;
    *((_DWORD *)this + 131) = v30 >= 0;
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
    if ( !(unsigned int)CDefView::_IsCollectionProvider(this) )
    {
      v31 = ~(unsigned __int8)((unsigned int)CDefView::_GetViewFlags(this) >> 5) & 0x40 | 0x10;
      v32 = (char)v50;
      if ( ((unsigned __int8)v50 & 1) == 0 )
        v31 |= 8u;
      if ( ((unsigned __int8)v50 & 8) == 0 )
        v31 |= 1u;
      InitialCollection = CDefView::_CreateInitialCollection(this, v31);
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
        if ( (*((_DWORD *)this + 222) & 0x10000000) == 0 && (v32 & 0x10) == 0 )
          GetUIThreadThumbnailCache(v34, (void **)this + 176);
      }
    }
  }
  else
  {
LABEL_57:
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
0x18002bca0  mov     [rsp-8+arg_18], rbx
0x18002bca5  push    rbp
0x18002bca6  push    rsi
0x18002bca7  push    rdi
0x18002bca8  push    r12
0x18002bcaa  push    r13
0x18002bcac  push    r14
0x18002bcae  push    r15
0x18002bcb0  lea     rbp, [rsp-7]
0x18002bcb5  sub     rsp, 0C0h
0x18002bcbc  mov     rax, cs:__security_cookie
0x18002bcc3  xor     rax, rsp
0x18002bcc6  mov     [rbp+37h+var_40], rax
0x18002bcca  mov     dword ptr [rbp+37h+var_50], r9d
0x18002bcce  mov     r12, r8
0x18002bcd1  mov     [rbp+37h+punk], r8
0x18002bcd5  mov     rsi, rdx
0x18002bcd8  mov     rdi, rcx
0x18002bcdb  mov     r13, [rbp+37h+arg_40]
0x18002bce2  mov     r14, [rbp+37h+arg_38]
0x18002bce6  mov     rax, [rbp+37h+arg_48]
0x18002bced  mov     [rbp+37h+var_78], rax
0x18002bcf1  xor     ebx, ebx
0x18002bcf3  mov     [rax], rbx
0x18002bcf6  call    cs:__imp_GetCurrentThreadId
0x18002bcfd  nop     dword ptr [rax+rax+00h]
0x18002bd02  mov     [rdi+5ACh], eax
0x18002bd08  cmp     [rdi+2D0h], rbx
0x18002bd0f  jnz     loc_18002C5E8
0x18002bd15  test    rsi, rsi
0x18002bd18  jz      loc_18002C5E8
0x18002bd1e  mov     rdx, rdi; punkSite
0x18002bd21  mov     rcx, [rdi+3A0h]; punk
0x18002bd28  call    cs:__imp_IUnknown_SetSite
0x18002bd2f  nop     dword ptr [rax+rax+00h]
0x18002bd34  mov     rdx, rdi; punkSite
0x18002bd37  mov     rcx, [rdi+560h]; punk
0x18002bd3e  call    cs:__imp_IUnknown_SetSite
0x18002bd45  nop     dword ptr [rax+rax+00h]
0x18002bd4a  mov     [rbp+37h+var_58], ebx
0x18002bd4d  mov     rcx, [rdi+3A0h]
0x18002bd54  test    rcx, rcx
0x18002bd57  jnz     loc_18002C45D
0x18002bd5d  mov     [rdi+280h], rsi
0x18002bd64  mov     rax, [rsi]
0x18002bd67  mov     rcx, rsi
0x18002bd6a  mov     rax, [rax+8]
0x18002bd6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bd73  mov     rcx, [rdi+280h]
0x18002bd7a  lea     r15, [rdi+2C8h]
0x18002bd81  mov     rax, [rcx]
0x18002bd84  mov     rdx, r15
0x18002bd87  mov     rax, [rax+18h]
0x18002bd8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bd90  mov     rcx, [rdi+3A0h]
0x18002bd97  test    rcx, rcx
0x18002bd9a  jz      short loc_18002BDB2
0x18002bd9c  mov     rax, [rcx]
0x18002bd9f  mov     r9, [r15]
0x18002bda2  xor     r8d, r8d
0x18002bda5  lea     edx, [r8+2Eh]
0x18002bda9  mov     rax, [rax+18h]
0x18002bdad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bdb2  mov     rdx, [rdi+280h]; struct IUnknown *
0x18002bdb9  lea     rcx, [rbp+37h+var_90]; this
0x18002bdbd  call    ??0CAutoWaitCursor@@QEAA@PEAUIUnknown@@@Z; CAutoWaitCursor::CAutoWaitCursor(IUnknown *)
0x18002bdc2  nop
0x18002bdc3  lea     rbx, [rdi+550h]
0x18002bdca  mov     rcx, rbx
0x18002bdcd  call    ??$SafeRelease@UIUpdatableItemSet@@@@YAXPEAPEAUIUpdatableItemSet@@@Z; SafeRelease<IUpdatableItemSet>(IUpdatableItemSet * *)
0x18002bdd2  mov     r9, rbx; ppvOut
0x18002bdd5  lea     r8, _GUID_f002a70d_e74b_4721_9243_5704338cfc2f; riid
0x18002bddc  lea     rdx, IID_ITrackEvents; guidService
0x18002bde3  mov     rcx, [rdi+280h]; punk
0x18002bdea  call    cs:__imp_IUnknown_QueryService
0x18002bdf1  nop     dword ptr [rax+rax+00h]
0x18002bdf6  mov     [rbp+37h+ppvOut], 0
0x18002bdfe  lea     r9, [rbp+37h+ppvOut]; ppvOut
0x18002be02  lea     r8, _GUID_f002a70d_e74b_4721_9243_5704338cfc2f; riid
0x18002be09  lea     rdx, IID_ITrackEvents; guidService
0x18002be10  mov     rcx, rdi; punk
0x18002be13  call    cs:__imp_IUnknown_QueryService
0x18002be1a  nop     dword ptr [rax+rax+00h]
0x18002be1f  test    eax, eax
0x18002be21  js      short loc_18002BE50
0x18002be23  mov     rcx, [rbp+37h+ppvOut]
0x18002be27  mov     rax, [rcx]
0x18002be2a  xor     r9d, r9d
0x18002be2d  xor     r8d, r8d
0x18002be30  lea     rdx, aCreateviewwind; "CreateViewWindow"
0x18002be37  mov     rax, [rax+18h]
0x18002be3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002be40  mov     rcx, [rbp+37h+ppvOut]
0x18002be44  mov     rax, [rcx]
0x18002be47  mov     rax, [rax+10h]
0x18002be4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002be50  lea     rdx, [rdi+4D0h]; unsigned int *
0x18002be57  mov     rcx, [rdi+280h]; struct IUnknown *
0x18002be5e  call    ?IUnknown_BeginBrowserProgressSession@@YAJPEAUIUnknown@@PEAK@Z; IUnknown_BeginBrowserProgressSession(IUnknown *,ulong *)
0x18002be63  mov     rcx, [rdi+270h]
0x18002be6a  mov     rax, [rcx]
0x18002be6d  lea     r8, [rdi+2A8h]
0x18002be74  lea     rdx, _GUID_000214e5_0000_0000_c000_000000000046
0x18002be7b  mov     rax, [rax]
0x18002be7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002be83  mov     rcx, [rdi+270h]
0x18002be8a  mov     rax, [rcx]
0x18002be8d  lea     r8, [rdi+2B0h]
0x18002be94  lea     rdx, _GUID_7d688a70_c613_11d0_999b_00c04fd655e1
0x18002be9b  mov     rax, [rax]
0x18002be9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bea3  mov     rax, [rsi]
0x18002bea6  lea     r8, [rdi+288h]
0x18002bead  lea     rdx, _GUID_000214f1_0000_0000_c000_000000000046
0x18002beb4  mov     rcx, rsi
0x18002beb7  mov     rax, [rax]
0x18002beba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bebf  lea     rcx, [rbp+37h+var_48]; void *
0x18002bec3  call    ??0?$CComPtr@UIClassFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IClassFactory>::CComPtr<IClassFactory>(void)
0x18002bec8  nop
0x18002bec9  lea     r9, [rbp+37h+var_48]; ppvOut
0x18002becd  lea     r8, _GUID_00000000_0000_0000_c000_000000000046; riid
0x18002bed4  lea     rdx, SID_TouchViewController; guidService
0x18002bedb  mov     rcx, [rdi+90h]; punk
0x18002bee2  call    cs:__imp_IUnknown_QueryService
0x18002bee9  nop     dword ptr [rax+rax+00h]
0x18002beee  xor     ecx, ecx
0x18002bef0  test    eax, eax
0x18002bef2  setz    cl
0x18002bef5  mov     [rdi+5D4h], ecx
0x18002befb  mov     ebx, [rbp+37h+arg_20]
0x18002befe  or      [rdi+5A0h], ebx
0x18002bf04  xor     r8d, r8d; int
0x18002bf07  xor     edx, edx; int
0x18002bf09  mov     rcx, rdi; this
0x18002bf0c  call    ?_ApplySettings@CDefView@@AEAAXHH@Z; CDefView::_ApplySettings(int,int)
0x18002bf11  mov     rcx, [rdi+3A0h]
0x18002bf18  test    rcx, rcx
0x18002bf1b  jz      short loc_18002BF33
0x18002bf1d  mov     rax, [rcx]
0x18002bf20  mov     r9, r12
0x18002bf23  xor     r8d, r8d
0x18002bf26  lea     edx, [r8+63h]
0x18002bf2a  mov     rax, [rax+18h]
0x18002bf2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bf33  mov     rcx, [rdi+560h]
0x18002bf3a  mov     rax, [rcx]
0x18002bf3d  mov     r8d, [rbp+37h+arg_28]
0x18002bf41  mov     edx, ebx
0x18002bf43  mov     rax, [rax+48h]
0x18002bf47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bf4c  btr     dword ptr [rdi+378h], 1Ch
0x18002bf54  and     ebx, [rbp+37h+arg_28]
0x18002bf57  and     bl, 20h
0x18002bf5a  neg     bl
0x18002bf5c  sbb     eax, eax
0x18002bf5e  and     eax, 10000000h
0x18002bf63  or      [rdi+378h], eax
0x18002bf69  test    byte ptr [rbp+37h+var_50], 2
0x18002bf6d  jnz     loc_18002C4E4
0x18002bf73  mov     rdx, r12; struct IShellView *
0x18002bf76  mov     rcx, rdi; this
0x18002bf79  call    ?_InitFromPreviousView@CDefView@@AEAAXPEAUIShellView@@@Z; CDefView::_InitFromPreviousView(IShellView *)
0x18002bf7e  lea     r8, [rdi+400h]; struct _tagpropertykey *
0x18002bf85  mov     rdx, [rdi+270h]; struct IShellFolder *
0x18002bf8c  xor     ecx, ecx; pidl
0x18002bf8e  call    ?GetStackedKeyFromIDList@@YAJPEBU_ITEMIDLIST_ABSOLUTE@@PEAUIShellFolder@@PEAU_tagpropertykey@@@Z; GetStackedKeyFromIDList(_ITEMIDLIST_ABSOLUTE const *,IShellFolder *,_tagpropertykey *)
0x18002bf93  xor     eax, eax
0x18002bf95  cmp     [rdi+278h], rax
0x18002bf9c  setnz   al
0x18002bf9f  mov     [rdi+598h], eax
0x18002bfa5  call    ?_RegisterWindow@CDefView@@AEAAXXZ; CDefView::_RegisterWindow(void)
0x18002bfaa  mov     rax, cs:g_hinst
0x18002bfb1  mov     [rbp+37h+ppvOut], rax
0x18002bfb5  mov     rax, [r15]
0x18002bfb8  mov     [rbp+37h+var_80], rax
0x18002bfbc  mov     r15d, [r13+4]
0x18002bfc0  mov     ebx, [r13+0Ch]
0x18002bfc4  mov     r12d, [r13+0]
0x18002bfc8  mov     esi, [r13+8]
0x18002bfcc  mov     edx, 0FFFFFFECh; nIndex
0x18002bfd1  mov     rcx, rax; hWnd
0x18002bfd4  call    cs:__imp_GetWindowLongW
0x18002bfdb  nop     dword ptr [rax+rax+00h]
0x18002bfe0  mov     r14d, eax
0x18002bfe3  and     r14d, 400000h
0x18002bfea  xor     r13d, r13d
0x18002bfed  mov     [rbp+37h+ulCookie], r13
0x18002bff1  lea     rcx, [rbp+37h+ulCookie]
0x18002bff5  call    SHActivateContext
0x18002bffa  test    eax, eax
0x18002bffc  jz      loc_18002C4B5
0x18002c002  sub     ebx, r15d
0x18002c005  sub     esi, r12d
0x18002c008  cmp     cs:g_hActCtx, 0FFFFFFFFFFFFFFFDh
0x18002c010  jz      short loc_18002C017
0x18002c012  call    DelayLoadCC
0x18002c017  mov     [rsp+0F0h+lpParam], rdi; lpParam
0x18002c01c  mov     rax, [rbp+37h+ppvOut]
0x18002c020  mov     [rsp+0F0h+hInstance], rax; hInstance
0x18002c025  mov     [rsp+0F0h+hMenu], r13; hMenu
0x18002c02a  mov     rax, [rbp+37h+var_80]
0x18002c02e  mov     [rsp+0F0h+hWndParent], rax; hWndParent
0x18002c033  mov     [rsp+0F0h+nHeight], ebx; nHeight
0x18002c037  mov     [rsp+0F0h+nWidth], esi; nWidth
0x18002c03b  mov     [rsp+0F0h+Y], r15d; Y
0x18002c040  mov     [rsp+0F0h+X], r12d; X
0x18002c045  mov     r9d, 46010000h; dwStyle
0x18002c04b  xor     r8d, r8d; lpWindowName
0x18002c04e  lea     rdx, aShelldllDefvie; "SHELLDLL_DefView"
0x18002c055  mov     ecx, r14d; dwExStyle
0x18002c058  call    cs:__imp_CreateWindowExW
0x18002c05f  nop     dword ptr [rax+rax+00h]
0x18002c064  mov     rbx, rax
0x18002c067  mov     rcx, [rbp+37h+ulCookie]; ulCookie
0x18002c06b  call    SHDeactivateContext
0x18002c070  test    rbx, rbx
0x18002c073  jz      loc_18002C4B5
0x18002c079  mov     ebx, r13d
0x18002c07c  mov     rax, [rdi+2D0h]
0x18002c083  mov     rcx, [rbp+37h+var_78]
0x18002c087  mov     [rcx], rax
0x18002c08a  mov     rcx, [rdi+3A0h]
0x18002c091  test    rcx, rcx
0x18002c094  jz      short loc_18002C0B0
0x18002c096  mov     rax, [rcx]
0x18002c099  xor     r9d, r9d
0x18002c09c  mov     r8, [rdi+2D0h]
0x18002c0a3  lea     edx, [r9+0Fh]
0x18002c0a7  mov     rax, [rax+18h]
0x18002c0ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c0b0  mov     [rbp+37h+ppvOut], r13
0x18002c0b4  mov     rcx, [rdi+280h]
0x18002c0bb  test    rcx, rcx
0x18002c0be  jnz     loc_18002C3EB
0x18002c0c4  mov     rcx, [rdi+3A0h]
0x18002c0cb  test    rcx, rcx
0x18002c0ce  jz      loc_18002C4C5
0x18002c0d4  mov     rax, [rcx]
0x18002c0d7  lea     r9, [rdi+1F8h]
0x18002c0de  xor     r8d, r8d
0x18002c0e1  lea     edx, [r8+5Eh]
0x18002c0e5  mov     rax, [rax+18h]
0x18002c0e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c0ee  not     eax
0x18002c0f0  shr     eax, 1Fh
0x18002c0f3  mov     [rdi+20Ch], eax
0x18002c0f9  mov     r14d, 1
0x18002c0ff  mov     r8d, r14d; int
0x18002c102  xor     edx, edx; int
0x18002c104  mov     rcx, rdi; this
0x18002c107  call    ?_ApplySettings@CDefView@@AEAAXHH@Z; CDefView::_ApplySettings(int,int)
0x18002c10c  mov     [rdi+460h], r14d
0x18002c113  bts     dword ptr [rdi+378h], 0Eh
0x18002c11b  mov     [rbp+37h+ulCookie], r13
0x18002c11f  mov     rcx, [rdi+280h]
0x18002c126  mov     rax, [rcx]
0x18002c129  lea     r8, [rbp+37h+ulCookie]
0x18002c12d  lea     rdx, _GUID_c8ad25a1_3294_41ee_8165_71174bd01c57
0x18002c134  mov     rax, [rax]
0x18002c137  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c13c  test    eax, eax
0x18002c13e  jns     loc_18002C435
0x18002c144  mov     rcx, rdi; punkSite
0x18002c147  call    ?_LoadPersistedHistory@CDefView@@AEAAJXZ; CDefView::_LoadPersistedHistory(void)
0x18002c14c  test    eax, eax
0x18002c14e  js      loc_18002C554
0x18002c154  mov     rcx, rdi; this
0x18002c157  call    ?_IsCollectionProvider@CDefView@@AEAAHXZ; CDefView::_IsCollectionProvider(void)
0x18002c15c  test    eax, eax
0x18002c15e  jnz     loc_18002C287
0x18002c164  mov     rcx, rdi
0x18002c167  call    ?_GetViewFlags@CDefView@@AEAA?AW4BROWSER_VIEW_FLAGS@@XZ; CDefView::_GetViewFlags(void)
0x18002c16c  shr     eax, 5
0x18002c16f  not     eax
0x18002c171  and     eax, 40h
0x18002c174  or      eax, 10h
0x18002c177  mov     esi, dword ptr [rbp+37h+var_50]
0x18002c17a  test    r14b, sil
0x18002c17d  jz      loc_18002C572
0x18002c183  test    sil, 8
0x18002c187  jz      loc_18002C57A
0x18002c18d  mov     edx, eax
0x18002c18f  mov     rcx, rdi
0x18002c192  call    ?_CreateInitialCollection@CDefView@@AEAAJW4UPDATE_FLAGS@@@Z; CDefView::_CreateInitialCollection(UPDATE_FLAGS)
0x18002c197  mov     ebx, eax
0x18002c199  test    eax, eax
0x18002c19b  js      loc_18002C5D8
0x18002c1a1  mov     r10, [rdi+270h]
0x18002c1a8  mov     rcx, [r10]
0x18002c1ab  lea     r9, [rdi+320h]
0x18002c1b2  mov     rax, [rcx+40h]
0x18002c1b6  lea     r8, _GUID_00000122_0000_0000_c000_000000000046
0x18002c1bd  mov     rdx, [rdi+2C8h]
0x18002c1c4  mov     rcx, r10
0x18002c1c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c1cc  mov     r15d, 10000000h
0x18002c1d2  test    [rdi+378h], r15d
0x18002c1d9  jz      loc_18002C34F
0x18002c1df  xor     r9d, r9d; lParam
  ... truncated ...
```
