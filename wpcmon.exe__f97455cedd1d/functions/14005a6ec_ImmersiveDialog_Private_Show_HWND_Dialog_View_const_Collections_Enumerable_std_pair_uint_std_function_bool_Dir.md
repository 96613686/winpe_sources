# ImmersiveDialog::Private::Show(HWND__ *,Dialog::View const &,Collections::Enumerable<std::pair<uint,std::function<bool (DirectUI::Element &)>>> const &,std::function<void (DirectUI::Element &,HWND__ *)> const &)

- ea: `0x14005a6ec`
- end: `0x14005b017`
- name: `?Show@Private@ImmersiveDialog@@YAXPEAUHWND__@@AEBVView@Dialog@@AEBV?$Enumerable@U?$pair@IV?$function@$$A6A_NAEAVElement@DirectUI@@@Z@std@@@std@@@Collections@@AEBV?$function@$$A6AXAEAVElement@DirectUI@@PEAUHWND__@@@Z@std@@@Z`
- size: `2347`
- prototype: `__int64 __fastcall(HWND hWnd, Dialog::View *this)`
- caller_count: `3`
- callee_count: `22`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14004f7d4`
- `0x14004f9a8`
- `0x140052144`

## callees

- `0x140005530`
- `0x140006338`
- `0x140007914`
- `0x140009aec`
- `0x14000b594`
- `0x14000b744`
- `0x14000ccac`
- `0x14000d084`
- `0x14001c760`
- `0x14001f6b4`
- `0x140058238`
- `0x140058780`
- `0x1400592b4`
- `0x1400595ec`
- `0x14005991c`
- `0x140059e4c`
- `0x14005a29c`
- `0x14005a6ec`
- `0x14005bbac`
- `0x140060f58`
- `0x140064200`
- `0x1400a8010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x14005a8a5`
- `KERNEL32!HeapAlloc` at `0x14005a8a5`
- `KERNEL32!GetProcessHeap` at `0x14005a891`
- `KERNEL32!GetProcessHeap` at `0x14005a891`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x14005a99e`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x14005a99e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14005a773`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14005a773`
- `ext-ms-win-ntuser-window-l1-1-0!SetForegroundWindow` at `0x14005ab8e`
- `ext-ms-win-ntuser-window-l1-1-0!SetForegroundWindow` at `0x14005ab8e`
- `DUI70!?EndDefer@Element@DirectUI@@QEAAXK@Z` at `0x14005ab13`
- `DUI70!?EndDefer@Element@DirectUI@@QEAAXK@Z` at `0x14005ab13`
- `DUI70!?Initialize@Element@DirectUI@@QEAAJIPEAV12@PEAK@Z` at `0x14005a91d`
- `DUI70!?Initialize@Element@DirectUI@@QEAAJIPEAV12@PEAK@Z` at `0x14005a91d`
- `DUI70!InitThread` at `0x14005a727`
- `DUI70!InitThread` at `0x14005a727`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x14005ac0a`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x14005ac0a`
- `USER32!GetWindowBand` at `0x14005a797`
- `USER32!GetWindowBand` at `0x14005a797`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
void __fastcall ImmersiveDialog::Private::Show(HWND hWnd, Dialog::View *this, __int64 *a3, __int64 a4)
{
  int inited; // eax
  int v8; // ebx
  int v9; // eax
  int v10; // ebx
  HRESULT v11; // eax
  int v12; // ebx
  unsigned int v13; // ebx
  __int64 v14; // rax
  int v15; // eax
  int v16; // ebx
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, _DWORD *); // r15
  _DWORD *v19; // rax
  _DWORD *v20; // rbx
  int v21; // edi
  HANDLE ProcessHeap; // rax
  struct DirectUI::Element *v23; // rax
  struct DirectUI::Element *v24; // rbx
  __int64 v25; // rdi
  __int64 (__fastcall *v26)(__int64, __int128 *); // rbx
  __int128 *p_pExceptionObject; // rdx
  int v28; // ebx
  struct DirectUI::Element *v29; // rdi
  int v30; // eax
  int v31; // ebx
  int v32; // eax
  int v33; // ebx
  int v34; // eax
  int v35; // ebx
  __int64 v36; // rcx
  __int64 *v37; // rbx
  int v38; // eax
  __int64 v39; // rcx
  __int64 **v40; // rbx
  __int64 **v41; // rdi
  __int64 *v42; // rax
  int v43; // eax
  int v44; // ebx
  __int64 v45; // rcx
  __int64 *v46; // rbx
  __int64 v47; // rax
  __int64 v48; // r15
  volatile signed __int32 *v49; // rbx
  int v50; // eax
  int v51; // edi
  int v52; // eax
  int v53; // edi
  __int64 v54; // rcx
  LPVOID v55; // rcx
  unsigned int v56; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v57; // [rsp+38h] [rbp-C8h] BYREF
  struct DirectUI::Element *v58; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID ppv; // [rsp+48h] [rbp-B8h] BYREF
  __int64 *v60; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v61; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v62; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v63; // [rsp+70h] [rbp-90h]
  __int64 v64; // [rsp+78h] [rbp-88h] BYREF
  __int128 v65; // [rsp+80h] [rbp-80h] BYREF
  struct DirectUI::Element *v66; // [rsp+90h] [rbp-70h]
  struct DirectUI::Element **v67; // [rsp+98h] [rbp-68h]
  _QWORD v68[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v69[2]; // [rsp+C0h] [rbp-40h] BYREF
  __int128 pExceptionObject; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v71; // [rsp+E0h] [rbp-20h]
  unsigned __int64 v72; // [rsp+E8h] [rbp-18h]
  _BYTE v73[64]; // [rsp+100h] [rbp+0h] BYREF

  v60 = a3;
  inited = InitThread(65538);
  v8 = inited;
  if ( inited < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        10,
        WPP_a3eb8c222d603a3c2faa819dca23cee7_Traceguids,
        (unsigned int)inited);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)&pExceptionObject, v8);
    throw (ErrorCodeException *)&pExceptionObject;
  }
  ScopeGuard::ScopeGuard__lambda_adde99f02c367038ca50bb6e975121dd___(v73);
  v9 = DirectUI::ClassInfo__anonymous_namespace_::ImmersiveDialogView_DirectUI::Element_DirectUI::StandardCreator__anonymous_namespace_::ImmersiveDialogView___::Register();
  v10 = v9;
  if ( v9 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        11,
        WPP_a3eb8c222d603a3c2faa819dca23cee7_Traceguids,
        (unsigned int)v9);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)&pExceptionObject, v10);
    throw (ErrorCodeException *)&pExceptionObject;
  }
  ppv = 0;
  v11 = CoCreateInstance(&CLSID_PopupWindowFactory, 0, 1u, &GUID_6a0017fe_df25_46eb_8a96_38df889cb5b1, &ppv);
  v12 = v11;
  if ( v11 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        12,
        WPP_a3eb8c222d603a3c2faa819dca23cee7_Traceguids,
        (unsigned int)v11);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)&pExceptionObject, v12);
    throw (ErrorCodeException *)&pExceptionObject;
  }
  v13 = 64;
  if ( hWnd )
  {
    v56 = 0;
    if ( !(unsigned int)GetWindowBand(hWnd, &v56) || v56 == 1 )
      v13 = 72;
  }
  (*(void (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 24LL))(ppv, v13);
  v57 = 0;
  v14 = *(_QWORD *)ppv;
  if ( hWnd )
    v15 = (*(__int64 (__fastcall **)(LPVOID, HWND, __int64 *))(v14 + 72))(ppv, hWnd, &v57);
  else
    v15 = (*(__int64 (__fastcall **)(LPVOID, __int64 *))(v14 + 80))(ppv, &v57);
  v16 = v15;
  if ( v15 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        13,
        WPP_a3eb8c222d603a3c2faa819dca23cee7_Traceguids,
        (unsigned int)v15);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)&pExceptionObject, v16);
    throw (ErrorCodeException *)&pExceptionObject;
  }
  v17 = v57;
  v18 = *(__int64 (__fastcall **)(__int64, _DWORD *))(*(_QWORD *)v57 + 168LL);
  v19 = operator new(0x18u, (const struct std::nothrow_t *)std::nothrow);
  v20 = v19;
  if ( v19 )
  {
    v19[3] = 1;
    *(_QWORD *)v19 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IPopupEventHandler>::`vftable';
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *(_QWORD *)v20 = off_1400AD8E0;
  }
  else
  {
    v20 = 0;
  }
  *(_QWORD *)&v65 = v20;
  v21 = v18(v17, v20);
  if ( v20 )
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v20 + 16LL))(v20);
  if ( v21 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        14,
        WPP_a3eb8c222d603a3c2faa819dca23cee7_Traceguids,
        (unsigned int)v21);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)&pExceptionObject, v21);
    throw (ErrorCodeException *)&pExceptionObject;
  }
  ProcessHeap = GetProcessHeap();
  v23 = (struct DirectUI::Element *)HeapAlloc(ProcessHeap, 8u, 0xD8u);
  v24 = v23;
  if ( v23 )
    anonymous_namespace_::ImmersiveDialogView::ImmersiveDialogView(v23);
  v58 = v24;
  v25 = v57;
  v26 = *(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v57 + 32LL);
  std::wstring::wstring((__int64)&pExceptionObject, (__int64)this + 8);
  p_pExceptionObject = &pExceptionObject;
  if ( v72 > 7 )
    p_pExceptionObject = (__int128 *)pExceptionObject;
  v28 = v26(v25, p_pExceptionObject);
  std::wstring::~wstring((char **)&pExceptionObject);
  if ( v28 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        15,
        WPP_a3eb8c222d603a3c2faa819dca23cee7_Traceguids,
        (unsigned int)v28);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)&pExceptionObject, v28);
    throw (ErrorCodeException *)&pExceptionObject;
  }
  v29 = v58;
  v56 = 0;
  v30 = DirectUI::Element::Initialize(v58, 0, 0, &v56);
  v31 = v30;
  if ( v30 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        16,
        WPP_a3eb8c222d603a3c2faa819dca23cee7_Traceguids,
        (unsigned int)v30);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)&pExceptionObject, v31);
    throw (ErrorCodeException *)&pExceptionObject;
  }
  Dialog::View::Load(this, v29);
  v64 = 0;
  v61 = 0;
  v32 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v57)(
          v57,
          &GUID_00000114_0000_0000_c000_000000000046,
          &v61);
  v33 = v32;
  if ( v32 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        17,
        WPP_a3eb8c222d603a3c2faa819dca23cee7_Traceguids,
        (unsigned int)v32);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)&pExceptionObject, v33);
    throw (ErrorCodeException *)&pExceptionObject;
  }
  v34 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v61 + 24LL))(v61, &v64);
  v35 = v34;
  if ( v34 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        18,
        WPP_a3eb8c222d603a3c2faa819dca23cee7_Traceguids,
        (unsigned int)v34);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)&pExceptionObject, v35);
    throw (ErrorCodeException *)&pExceptionObject;
  }
  *(_QWORD *)&v65 = v64;
  v36 = *(_QWORD *)(a4 + 56);
  if ( !v36 )
  {
    std::_Xbad_function_call();
    __debugbreak();
  }
  (*(void (__fastcall **)(__int64, struct DirectUI::Element *, __int128 *))(*(_QWORD *)v36 + 16LL))(v36, v29, &v65);
  v37 = v60;
  if ( (unsigned __int8)Collections::QueryableRange<std::pair<unsigned int,std::function<bool (DirectUI::Element &)>>,Collections::Enumerable<std::pair<unsigned int,std::function<bool (DirectUI::Element &)>>>,Collections::Private::EnumerableIterator<std::pair<unsigned int,std::function<bool (DirectUI::Element &)>>>>::Any(v60) )
  {
    pExceptionObject = 0;
    v71 = 0;
    v60 = v69;
    v65 = 0;
    Collections::Private::EnumerableIterator<Dialog::Command<bool>>::EnumerableIterator<Dialog::Command<bool>>(
      v69,
      (__int64 *)&v65);
    v38 = Collections::Enumerable<std::pair<unsigned int,std::function<bool (DirectUI::Element &)>>>::begin(v37, v68);
    *(_QWORD *)&v65 = &pExceptionObject;
    *((_QWORD *)&v65 + 1) = this;
    v66 = v29;
    v67 = &v58;
    std::transform_Collections::Private::EnumerableIterator_std::pair_unsigned_int_std::function_bool___cdecl_DirectUI::Element_________std::back_insert_iterator_std::vector_Microsoft::WRL::ComPtr_IPopupCommand__std::allocator_Microsoft::WRL::ComPtr_IPopupCommand_________lambda_d618900badb3dbfc0e96843a0ca6f905___(
      (unsigned int)&v60,
      v38,
      (unsigned int)v69,
      (unsigned int)&pExceptionObject,
      (__int64)&v65);
    v62 = 0;
    v39 = 0;
    v63 = 0;
    v41 = (__int64 **)*((_QWORD *)&pExceptionObject + 1);
    v40 = (__int64 **)pExceptionObject;
    if ( (_QWORD)pExceptionObject != *((_QWORD *)&pExceptionObject + 1) )
    {
      while ( 1 )
      {
        v42 = *v40;
        v60 = *v40;
        if ( *((_QWORD *)&v62 + 1) == v39 )
        {
          std::vector<Monitor>::_Emplace_reallocate<Monitor>(&v62, *((_QWORD *)&v62 + 1), &v60);
        }
        else
        {
          **((_QWORD **)&v62 + 1) = v42;
          *((_QWORD *)&v62 + 1) += 8LL;
        }
        if ( ++v40 == v41 )
          break;
        v39 = v63;
      }
    }
    v43 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v57 + 64LL))(
            v57,
            (__int64)(*((_QWORD *)&v62 + 1) - v62) >> 3);
    v44 = v43;
    if ( v43 < 0 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_d(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          19,
          WPP_a3eb8c222d603a3c2faa819dca23cee7_Traceguids,
          (unsigned int)v43);
      ErrorCodeException::ErrorCodeException((ErrorCodeException *)&v65, v44);
      throw (ErrorCodeException *)&v65;
    }
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v57 + 88LL))(v57, 0);
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v57 + 120LL))(
      v57,
      (unsigned int)((__int64)(*((_QWORD *)&v62 + 1) - v62) >> 3) - 1);
    std::vector<unsigned short *>::~vector<unsigned short *>((char **)&v62);
    std::vector<Microsoft::WRL::ComPtr<IPopupCommand>>::~vector<Microsoft::WRL::ComPtr<IPopupCommand>>((__int64)&pExceptionObject);
  }
  DirectUI::Element::EndDefer(v58, v56);
  v45 = v61;
  if ( v61 )
  {
    v61 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
  }
  v46 = (__int64 *)((char *)v58 + 200);
  v47 = *((_QWORD *)v58 + 26);
  if ( v47 )
    _InterlockedIncrement((volatile signed __int32 *)(v47 + 8));
  v48 = *v46;
  v68[0] = *v46;
  v49 = (volatile signed __int32 *)v46[1];
  v68[1] = v49;
  v50 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v57 + 352LL))(v57);
  v51 = v50;
  if ( v50 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        20,
        WPP_a3eb8c222d603a3c2faa819dca23cee7_Traceguids,
        (unsigned int)v50);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)&pExceptionObject, v51);
    throw (ErrorCodeException *)&pExceptionObject;
  }
  v58 = 0;
  if ( hWnd )
    SetForegroundWindow(hWnd);
  v52 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v57 + 272LL))(v57);
  v53 = v52;
  if ( v52 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        21,
        WPP_a3eb8c222d603a3c2faa819dca23cee7_Traceguids,
        (unsigned int)v52);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)&pExceptionObject, v53);
    throw (ErrorCodeException *)&pExceptionObject;
  }
  Threading::Wait(v48, qword_140110020);
  if ( v49 )
  {
    if ( _InterlockedExchangeAdd(v49 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v49)(v49);
      if ( _InterlockedExchangeAdd(v49 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v49 + 8LL))(v49);
    }
  }
  if ( v58 )
    DirectUI::Element::Destroy(v58, 1);
  v54 = v57;
  if ( v57 )
  {
    v57 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
  }
  v55 = ppv;
  if ( ppv )
  {
    ppv = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v55 + 16LL))(v55);
  }
  ScopeGuard::~ScopeGuard((ScopeGuard *)v73);
}

```

## disassembly

```asm
0x14005a6ec  push    rbp
0x14005a6ee  push    rbx
0x14005a6ef  push    rdi
0x14005a6f0  push    r12
0x14005a6f2  push    r13
0x14005a6f4  push    r14
0x14005a6f6  push    r15
0x14005a6f8  lea     rbp, [rsp-50h]
0x14005a6fd  sub     rsp, 150h
0x14005a704  mov     rax, cs:__security_cookie
0x14005a70b  xor     rax, rsp
0x14005a70e  mov     [rbp+80h+var_40], rax
0x14005a712  mov     r12, r9
0x14005a715  mov     [rsp+180h+var_130], r8
0x14005a71a  mov     r13, rdx
0x14005a71d  mov     r14, rcx
0x14005a720  xor     edi, edi
0x14005a722  mov     ecx, 10002h
0x14005a727  call    cs:__imp_InitThread
0x14005a72d  mov     ebx, eax
0x14005a72f  test    eax, eax
0x14005a731  js      loc_14005ACBF
0x14005a737  lea     rcx, [rbp+80h+var_80]
0x14005a73b  call    ScopeGuard__ScopeGuard__lambda_adde99f02c367038ca50bb6e975121dd___
0x14005a740  nop
0x14005a741  call    DirectUI__ClassInfo__anonymous_namespace___ImmersiveDialogView_DirectUI__Element_DirectUI__StandardCreator__anonymous_namespace___ImmersiveDialogView_____Register
0x14005a746  mov     ebx, eax
0x14005a748  test    eax, eax
0x14005a74a  js      loc_14005AD0D
0x14005a750  mov     [rsp+180h+var_138], rdi
0x14005a755  lea     rax, [rsp+180h+var_138]
0x14005a75a  mov     [rsp+180h+ppv], rax; ppv
0x14005a75f  lea     r9, _GUID_6a0017fe_df25_46eb_8a96_38df889cb5b1; riid
0x14005a766  xor     edx, edx; pUnkOuter
0x14005a768  lea     r8d, [rdi+1]; dwClsContext
0x14005a76c  lea     rcx, CLSID_PopupWindowFactory; rclsid
0x14005a773  call    cs:__imp_CoCreateInstance
0x14005a779  mov     ebx, eax
0x14005a77b  test    eax, eax
0x14005a77d  js      loc_14005AD5B
0x14005a783  lea     ebx, [rdi+40h]
0x14005a786  test    r14, r14
0x14005a789  jz      short loc_14005A7AD
0x14005a78b  mov     [rsp+180h+var_150], edi
0x14005a78f  lea     rdx, [rsp+180h+var_150]
0x14005a794  mov     rcx, r14
0x14005a797  call    cs:__imp_GetWindowBand
0x14005a79d  test    eax, eax
0x14005a79f  jz      short loc_14005A7A8
0x14005a7a1  cmp     [rsp+180h+var_150], 1
0x14005a7a6  jnz     short loc_14005A7AD
0x14005a7a8  mov     ebx, 48h ; 'H'
0x14005a7ad  mov     rcx, [rsp+180h+var_138]
0x14005a7b2  mov     rax, [rcx]
0x14005a7b5  mov     edx, ebx
0x14005a7b7  mov     rax, [rax+18h]
0x14005a7bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005a7c0  mov     [rsp+180h+var_148], rdi
0x14005a7c5  mov     rcx, [rsp+180h+var_138]
0x14005a7ca  mov     rax, [rcx]
0x14005a7cd  test    r14, r14
0x14005a7d0  jz      short loc_14005A7E5
0x14005a7d2  lea     r8, [rsp+180h+var_148]
0x14005a7d7  mov     rdx, r14
0x14005a7da  mov     rax, [rax+48h]
0x14005a7de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005a7e3  jmp     short loc_14005A7F3
0x14005a7e5  lea     rdx, [rsp+180h+var_148]
0x14005a7ea  mov     rax, [rax+50h]
0x14005a7ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005a7f3  mov     ebx, eax
0x14005a7f5  test    eax, eax
0x14005a7f7  js      loc_14005ADA9
0x14005a7fd  mov     rdi, [rsp+180h+var_148]
0x14005a802  mov     rax, [rdi]
0x14005a805  mov     r15, [rax+0A8h]
0x14005a80c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14005a813  mov     ecx, 18h; unsigned __int64
0x14005a818  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14005a81d  mov     rbx, rax
0x14005a820  test    rax, rax
0x14005a823  jz      short loc_14005A85B
0x14005a825  mov     dword ptr [rax+0Ch], 1
0x14005a82c  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIPopupEventHandler@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IPopupEventHandler>::`vftable'
0x14005a833  mov     [rbx], rax
0x14005a836  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x14005a83d  test    rcx, rcx
0x14005a840  jz      short loc_14005A84F
0x14005a842  mov     rax, [rcx]
0x14005a845  mov     rax, [rax+8]
0x14005a849  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005a84e  nop
0x14005a84f  lea     rax, off_1400AD8E0
0x14005a856  mov     [rbx], rax
0x14005a859  jmp     short loc_14005A85D
0x14005a85b  xor     ebx, ebx
0x14005a85d  mov     qword ptr [rbp+80h+var_100], rbx
0x14005a861  mov     rdx, rbx
0x14005a864  mov     rcx, rdi
0x14005a867  mov     rax, r15
0x14005a86a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005a86f  mov     edi, eax
0x14005a871  xor     r15d, r15d
0x14005a874  test    rbx, rbx
0x14005a877  jz      short loc_14005A889
0x14005a879  mov     rcx, [rbx]
0x14005a87c  mov     rax, [rcx+10h]
0x14005a880  mov     rcx, rbx
0x14005a883  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005a888  nop
0x14005a889  test    edi, edi
0x14005a88b  js      loc_14005ADF6
0x14005a891  call    cs:__imp_GetProcessHeap
0x14005a897  mov     rcx, rax; hHeap
0x14005a89a  mov     edx, 8; dwFlags
0x14005a89f  mov     r8d, 0D8h; dwBytes
0x14005a8a5  call    cs:__imp_HeapAlloc
0x14005a8ab  mov     rbx, rax
0x14005a8ae  test    rax, rax
0x14005a8b1  jz      short loc_14005A8BB
0x14005a8b3  mov     rcx, rax
0x14005a8b6  call    _anonymous_namespace___ImmersiveDialogView__ImmersiveDialogView
0x14005a8bb  mov     [rsp+180h+var_140], rbx
0x14005a8c0  mov     rdi, [rsp+180h+var_148]
0x14005a8c5  mov     rax, [rdi]
0x14005a8c8  mov     rbx, [rax+20h]
0x14005a8cc  lea     rdx, [r13+8]
0x14005a8d0  lea     rcx, [rbp+80h+pExceptionObject]
0x14005a8d4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14005a8d9  nop
0x14005a8da  lea     rdx, [rbp+80h+pExceptionObject]
0x14005a8de  cmp     [rbp+80h+var_98], 7
0x14005a8e3  cmova   rdx, qword ptr [rbp+80h+pExceptionObject]
0x14005a8e8  mov     rcx, rdi
0x14005a8eb  mov     rax, rbx
0x14005a8ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005a8f3  mov     ebx, eax
0x14005a8f5  lea     rcx, [rbp+80h+pExceptionObject]
0x14005a8f9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005a8fe  test    ebx, ebx
0x14005a900  js      loc_14005AE43
0x14005a906  mov     rdi, [rsp+180h+var_140]
0x14005a90b  mov     [rsp+180h+var_150], r15d
0x14005a910  lea     r9, [rsp+180h+var_150]
0x14005a915  xor     r8d, r8d
0x14005a918  xor     edx, edx
0x14005a91a  mov     rcx, rdi
0x14005a91d  call    cs:__imp_?Initialize@Element@DirectUI@@QEAAJIPEAV12@PEAK@Z; DirectUI::Element::Initialize(uint,DirectUI::Element *,ulong *)
0x14005a923  mov     ebx, eax
0x14005a925  test    eax, eax
0x14005a927  js      loc_14005AE91
0x14005a92d  mov     rdx, rdi; struct DirectUI::Element *
0x14005a930  mov     rcx, r13; this
0x14005a933  call    ?Load@View@Dialog@@QEBAXAEAVElement@DirectUI@@@Z; Dialog::View::Load(DirectUI::Element &)
0x14005a938  mov     [rsp+180h+var_108], r15
0x14005a93d  mov     [rsp+180h+var_128], r15
0x14005a942  mov     rcx, [rsp+180h+var_148]
0x14005a947  mov     rax, [rcx]
0x14005a94a  lea     r8, [rsp+180h+var_128]
0x14005a94f  lea     rdx, _GUID_00000114_0000_0000_c000_000000000046
0x14005a956  mov     rax, [rax]
0x14005a959  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005a95e  mov     ebx, eax
0x14005a960  test    eax, eax
0x14005a962  js      loc_14005AEDF
0x14005a968  mov     rcx, [rsp+180h+var_128]
0x14005a96d  mov     rax, [rcx]
0x14005a970  lea     rdx, [rsp+180h+var_108]
0x14005a975  mov     rax, [rax+18h]
0x14005a979  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005a97e  mov     ebx, eax
0x14005a980  test    eax, eax
0x14005a982  js      loc_14005AF2D
0x14005a988  mov     rax, [rsp+180h+var_108]
0x14005a98d  mov     qword ptr [rbp+80h+var_100], rax
0x14005a991  mov     rcx, [r12+38h]
0x14005a996  xor     r12d, r12d
0x14005a999  test    rcx, rcx
0x14005a99c  jnz     short loc_14005A9A5
0x14005a99e  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x14005a9a4  int     3; Trap to Debugger
0x14005a9a5  mov     rax, [rcx]
0x14005a9a8  lea     r8, [rbp+80h+var_100]
0x14005a9ac  mov     rdx, rdi
0x14005a9af  mov     rax, [rax+10h]
0x14005a9b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005a9b8  mov     rbx, [rsp+180h+var_130]
0x14005a9bd  mov     rcx, rbx
0x14005a9c0  call    ?Any@?$QueryableRange@U?$pair@IV?$function@$$A6A_NAEAVElement@DirectUI@@@Z@std@@@std@@V?$Enumerable@U?$pair@IV?$function@$$A6A_NAEAVElement@DirectUI@@@Z@std@@@std@@@Collections@@V?$EnumerableIterator@U?$pair@IV?$function@$$A6A_NAEAVElement@DirectUI@@@Z@std@@@std@@@Private@4@@Collections@@QEBA_NXZ; Collections::QueryableRange<std::pair<uint,std::function<bool (DirectUI::Element &)>>,Collections::Enumerable<std::pair<uint,std::function<bool (DirectUI::Element &)>>>,Collections::Private::EnumerableIterator<std::pair<uint,std::function<bool (DirectUI::Element &)>>>>::Any(void)
0x14005a9c5  test    al, al
0x14005a9c7  jz      loc_14005AB0A
0x14005a9cd  xorps   xmm0, xmm0
0x14005a9d0  movdqu  [rbp+80h+pExceptionObject], xmm0
0x14005a9d5  mov     [rbp+80h+var_A0], r12
0x14005a9d9  lea     rax, [rbp+80h+var_C0]
0x14005a9dd  mov     [rsp+180h+var_130], rax
0x14005a9e2  xorps   xmm1, xmm1
0x14005a9e5  movdqu  [rbp+80h+var_100], xmm1
0x14005a9ea  lea     rdx, [rbp+80h+var_100]
0x14005a9ee  lea     rcx, [rbp+80h+var_C0]
0x14005a9f2  call    ??0?$EnumerableIterator@U?$Command@_N@Dialog@@@Private@Collections@@QEAA@AEBV?$shared_ptr@U?$IEnumerator@U?$Command@_N@Dialog@@@Collections@@@std@@@Z; Collections::Private::EnumerableIterator<Dialog::Command<bool>>::EnumerableIterator<Dialog::Command<bool>>(std::shared_ptr<Collections::IEnumerator<Dialog::Command<bool>>> const &)
0x14005a9f7  nop
0x14005a9f8  lea     rdx, [rbp+80h+var_D0]
0x14005a9fc  mov     rcx, rbx
0x14005a9ff  call    ?begin@?$Enumerable@U?$pair@IV?$function@$$A6A_NAEAVElement@DirectUI@@@Z@std@@@std@@@Collections@@QEBA?AV?$EnumerableIterator@U?$pair@IV?$function@$$A6A_NAEAVElement@DirectUI@@@Z@std@@@std@@@Private@2@XZ; Collections::Enumerable<std::pair<uint,std::function<bool (DirectUI::Element &)>>>::begin(void)
0x14005aa04  lea     rcx, [rbp+80h+pExceptionObject]
0x14005aa08  mov     qword ptr [rbp+80h+var_100], rcx
0x14005aa0c  mov     qword ptr [rbp+80h+var_100+8], r13
0x14005aa10  mov     [rbp+80h+var_F0], rdi
0x14005aa14  lea     rcx, [rsp+180h+var_140]
0x14005aa19  mov     [rbp+80h+var_E8], rcx
0x14005aa1d  lea     rcx, [rbp+80h+var_100]
0x14005aa21  mov     [rsp+180h+ppv], rcx
0x14005aa26  lea     r9, [rbp+80h+pExceptionObject]
0x14005aa2a  lea     r8, [rbp+80h+var_C0]
0x14005aa2e  mov     rdx, rax
0x14005aa31  lea     rcx, [rsp+180h+var_130]
0x14005aa36  call    std__transform_Collections__Private__EnumerableIterator_std__pair_unsigned_int_std__function_bool___cdecl_DirectUI__Element_________std__back_insert_iterator_std__vector_Microsoft__WRL__ComPtr_IPopupCommand__std__allocator_Microsoft__WRL__ComPtr_IPopupCommand_________lambda_d618900badb3dbfc0e96843a0ca6f905___
0x14005aa3b  xorps   xmm0, xmm0
0x14005aa3e  movdqu  [rsp+180h+var_120], xmm0
0x14005aa44  mov     rcx, r12
0x14005aa47  mov     [rsp+180h+var_110], rcx
0x14005aa4c  mov     rbx, qword ptr [rbp+80h+pExceptionObject]
0x14005aa50  mov     rdi, qword ptr [rbp+80h+pExceptionObject+8]
0x14005aa54  cmp     rbx, rdi
0x14005aa57  jz      short loc_14005AA95
0x14005aa59  mov     rax, [rbx]
0x14005aa5c  mov     [rsp+180h+var_130], rax
0x14005aa61  mov     rdx, qword ptr [rsp+180h+var_120+8]
0x14005aa66  cmp     rdx, rcx
0x14005aa69  jz      short loc_14005AA76
0x14005aa6b  mov     [rdx], rax
0x14005aa6e  add     qword ptr [rsp+180h+var_120+8], 8
0x14005aa74  jmp     short loc_14005AA85
0x14005aa76  lea     r8, [rsp+180h+var_130]
0x14005aa7b  lea     rcx, [rsp+180h+var_120]
0x14005aa80  call    ??$_Emplace_reallocate@VMonitor@@@?$vector@VMonitor@@V?$allocator@VMonitor@@@std@@@std@@AEAAPEAVMonitor@@QEAV2@$$QEAV2@@Z; std::vector<Monitor>::_Emplace_reallocate<Monitor>(Monitor * const,Monitor &&)
0x14005aa85  add     rbx, 8
0x14005aa89  cmp     rbx, rdi
0x14005aa8c  jz      short loc_14005AA95
0x14005aa8e  mov     rcx, [rsp+180h+var_110]
0x14005aa93  jmp     short loc_14005AA59
0x14005aa95  mov     rcx, [rsp+180h+var_148]
0x14005aa9a  mov     r8, qword ptr [rsp+180h+var_120]
0x14005aa9f  mov     rax, [rcx]
0x14005aaa2  mov     rdx, qword ptr [rsp+180h+var_120+8]
0x14005aaa7  sub     rdx, r8
0x14005aaaa  sar     rdx, 3
0x14005aaae  mov     rax, [rax+40h]
0x14005aab2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005aab7  mov     ebx, eax
0x14005aab9  test    eax, eax
0x14005aabb  js      loc_14005AF7B
0x14005aac1  mov     rcx, [rsp+180h+var_148]
0x14005aac6  mov     rax, [rcx]
0x14005aac9  xor     edx, edx
0x14005aacb  mov     rax, [rax+58h]
0x14005aacf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005aad4  mov     rcx, [rsp+180h+var_148]
0x14005aad9  mov     rax, [rcx]
0x14005aadc  mov     rdx, qword ptr [rsp+180h+var_120+8]
0x14005aae1  sub     rdx, qword ptr [rsp+180h+var_120]
0x14005aae6  sar     rdx, 3
0x14005aaea  dec     edx
0x14005aaec  mov     rax, [rax+78h]
0x14005aaf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005aaf5  nop
0x14005aaf6  lea     rcx, [rsp+180h+var_120]
0x14005aafb  call    ??1?$vector@PEAGV?$allocator@PEAG@std@@@std@@QEAA@XZ; std::vector<ushort *>::~vector<ushort *>(void)
0x14005ab00  nop
0x14005ab01  lea     rcx, [rbp+80h+pExceptionObject]
0x14005ab05  call    ??1?$vector@V?$ComPtr@UIPopupCommand@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIPopupCommand@@@WRL@Microsoft@@@std@@@std@@QEAA@XZ; std::vector<Microsoft::WRL::ComPtr<IPopupCommand>>::~vector<Microsoft::WRL::ComPtr<IPopupCommand>>(void)
0x14005ab0a  mov     edx, [rsp+180h+var_150]
0x14005ab0e  mov     rcx, [rsp+180h+var_140]
0x14005ab13  call    cs:__imp_?EndDefer@Element@DirectUI@@QEAAXK@Z; DirectUI::Element::EndDefer(ulong)
0x14005ab19  nop
0x14005ab1a  mov     rcx, [rsp+180h+var_128]
0x14005ab1f  test    rcx, rcx
0x14005ab22  jz      short loc_14005AB36
0x14005ab24  mov     [rsp+180h+var_128], r12
0x14005ab29  mov     rax, [rcx]
0x14005ab2c  mov     rax, [rax+10h]
0x14005ab30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005ab35  nop
0x14005ab36  mov     rdx, [rsp+180h+var_140]
0x14005ab3b  lea     rbx, [rdx+0C8h]
0x14005ab42  mov     rax, [rbx+8]
0x14005ab46  test    rax, rax
0x14005ab49  jz      short loc_14005AB54
0x14005ab4b  lock inc dword ptr [rax+8]
0x14005ab4f  mov     rdx, [rsp+180h+var_140]
0x14005ab54  mov     r15, [rbx]
0x14005ab57  mov     [rbp+80h+var_D0], r15
0x14005ab5b  mov     rbx, [rbx+8]
0x14005ab5f  mov     [rbp+80h+var_C8], rbx
0x14005ab63  mov     rcx, [rsp+180h+var_148]
0x14005ab68  mov     rax, [rcx]
0x14005ab6b  mov     rax, [rax+160h]
0x14005ab72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005ab77  mov     edi, eax
  ... truncated ...
```
