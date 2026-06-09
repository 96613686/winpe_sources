# CAppViewManager::_ShowAsViewModeWorker(Windows::Internal::Shell::ViewManagerInterop::IViewEventArgsForShowAsViewMode *,IPresentationRequestedArgs *)

- ea: `0x18037f630`
- end: `0x18038068e`
- name: `?_ShowAsViewModeWorker@CAppViewManager@@AEAAJPEAUIViewEventArgsForShowAsViewMode@ViewManagerInterop@Shell@Internal@Windows@@PEAUIPresentationRequestedArgs@@@Z`
- size: `4190`
- prototype: `__int64 __fastcall(CAppViewManager *__hidden this, struct Windows::Internal::Shell::ViewManagerInterop::IViewEventArgsForShowAsViewMode *, struct IPresentationRequestedArgs *)`
- caller_count: `1`
- callee_count: `37`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18037c460`

## callees

- `0x1800134f8`
- `0x18001f6e0`
- `0x1800237c8`
- `0x1800255d0`
- `0x180031200`
- `0x180031c70`
- `0x180047278`
- `0x18007b3e0`
- `0x18007e3bc`
- `0x18008a6f0`
- `0x1800d4050`
- `0x1800d8fac`
- `0x1800ed8e0`
- `0x1800edeb4`
- `0x180190b30`
- `0x1801a5050`
- `0x1801b1d6c`
- `0x1801c1240`
- `0x18027e678`
- `0x1802f6ca4`
- `0x180356360`
- `0x18037220c`
- `0x180379544`
- `0x1803797b0`
- `0x18037a940`
- `0x18037ab24`
- `0x18037b860`
- `0x18037c6a0`
- `0x18037cdb0`
- `0x18037d038`
- `0x18037d0cc`
- `0x18037d160`
- `0x18037d1f4`
- `0x18037d6a8`
- `0x18037eccc`
- `0x18037f630`
- `0x1806fa010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18038045f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18038059d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180380603`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18038045f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18038059d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180380603`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1803804f0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1803804f0`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x18037fb7f`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x18037fce4`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x18037fe5c`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x18037fb7f`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x18037fce4`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x18037fe5c`

## string_xrefs

- `0x180380321`: `ModalExperienceOption.LinkAsTreeNode`
- `0x18037fb35`: `EnterCompactOverlayModeForView`
- `0x18037fde9`: `EnterCompactOverlayModeForView`

## pseudocode

```c
// Hidden C++ exception states: #wind=29
__int64 __fastcall CAppViewManager::_ShowAsViewModeWorker(
        IUnknown **this,
        struct Windows::Internal::Shell::ViewManagerInterop::IViewEventArgsForShowAsViewMode *a2,
        struct IPresentationRequestedArgs *a3)
{
  float v3; // xmm2_4
  unsigned int v7; // r15d
  __int64 (__fastcall *v8)(struct Windows::Internal::Shell::ViewManagerInterop::IViewEventArgsForShowAsViewMode *, struct Windows::Internal::Shell::ViewManagerInterop::IViewWrapper **); // rbx
  int v9; // eax
  unsigned int v10; // ebx
  __int64 v11; // rdx
  __int64 (__fastcall *v12)(struct Windows::Internal::Shell::ViewManagerInterop::IViewEventArgsForShowAsViewMode *, struct Windows::Internal::Shell::ViewManagerInterop::IViewWrapper **); // rbx
  int v13; // eax
  __int64 v14; // rdx
  Windows::Internal::ApplicationModel::WindowManagement *v15; // rcx
  __int64 (__fastcall *v16)(struct Windows::Internal::Shell::ViewManagerInterop::IViewEventArgsForShowAsViewMode *, GUID *, struct Windows::Foundation::Collections::IPropertySet **); // rbx
  int v17; // eax
  wil::details::in1diag3 *v18; // rcx
  __int64 v19; // rdx
  Windows::Internal::ApplicationModel::WindowManagement *v20; // rcx
  __int64 (__fastcall *v21)(struct Windows::Internal::Shell::ViewManagerInterop::IViewEventArgsForShowAsViewMode *, GUID *, __int64 *); // rbx
  int v22; // eax
  __int64 v23; // rdi
  __int64 (__fastcall *v24)(__int64, struct Windows::Foundation::Collections::IPropertySet **); // rbx
  int v25; // eax
  __int64 v26; // rdx
  struct Windows::Foundation::Collections::IPropertySet *v27; // rdx
  struct Windows::Foundation::Collections::IPropertySet *v28; // rax
  const unsigned __int16 *v29; // rdx
  int v30; // eax
  __int64 v31; // rdx
  __int64 (__fastcall *v32)(struct Windows::Internal::Shell::ViewManagerInterop::IViewEventArgsForShowAsViewMode *, GUID *, __int64 *); // rbx
  int v33; // eax
  __int64 v34; // rdi
  __int64 (__fastcall *v35)(__int64, __int64 *); // rbx
  int v36; // eax
  int v37; // ebx
  HWND v38; // r14
  void **v39; // rax
  HRESULT Service; // eax
  struct Windows::Foundation::Collections::IPropertySet **v41; // rcx
  struct Windows::Foundation::Collections::IPropertySet *v42; // rdi
  __int64 (__fastcall *v43)(struct Windows::Foundation::Collections::IPropertySet *, HWND, FullScreenPositionerHelpers **); // rbx
  int v44; // eax
  FullScreenPositionerHelpers *v45; // rdi
  int (__fastcall *v46)(FullScreenPositionerHelpers *, GUID *, __int64); // rbx
  __int64 v47; // rax
  struct IApplicationView *v48; // rdx
  int v49; // eax
  bool v50; // bl
  struct Windows::Foundation::Collections::IPropertySet **v51; // rcx
  void **v52; // rax
  HRESULT v53; // eax
  __int64 v54; // rdi
  __int64 (__fastcall *v55)(__int64, HWND, __int64 *); // rbx
  int v56; // eax
  __int64 v57; // rdi
  __int64 (__fastcall *v58)(__int64, HSTRING_HEADER *); // rbx
  int v59; // eax
  PVOID Reserved1; // rbx
  HRESULT v61; // eax
  __int64 v62; // rdx
  struct Windows::Internal::ShellHelpers::PropertySetHelper *v63; // rdx
  int v64; // edi
  __int64 v65; // rdx
  struct Windows::Internal::ShellHelpers::PropertySetHelper *v66; // rdx
  int v67; // eax
  __int64 v68; // rdx
  struct IAsyncCallback **v69; // rax
  struct IAsyncCallback *v70; // rbx
  int v71; // eax
  int v72; // eax
  __int64 v73; // rdx
  HSTRING *v74; // rax
  int v75; // eax
  __int64 (__fastcall ***v76)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v77)(_QWORD, GUID *, struct Windows::Foundation::Collections::IPropertySet **); // rdi
  int v78; // eax
  __int64 v79; // r8
  int v80; // eax
  __int64 v81; // rdx
  __int64 v82; // r9
  __int64 v83; // r8
  __int64 v84; // r8
  __int64 v85; // r9
  __int64 v86; // r8
  bool v87; // di
  __int64 v88; // r9
  __int64 v89; // r8
  __int64 v90; // r9
  __int64 v91; // r8
  struct Windows::Internal::Shell::ViewManagerInterop::IViewWrapper *v92; // rdi
  __int64 (__fastcall *v93)(struct Windows::Internal::Shell::ViewManagerInterop::IViewWrapper *, HSTRING *); // rbx
  int v94; // eax
  __int64 v95; // rdx
  HRESULT v96; // eax
  __int64 v97; // rdx
  LPVOID v98; // rdi
  __int64 (__fastcall *v99)(LPVOID, __int64 *, GUID *, HWND *); // rbx
  int ppv; // [rsp+20h] [rbp-E0h]
  int ppva; // [rsp+20h] [rbp-E0h]
  int ppvb; // [rsp+20h] [rbp-E0h]
  struct Windows::Internal::Shell::ViewManagerInterop::IViewWrapper *v104; // [rsp+40h] [rbp-C0h] BYREF
  struct Windows::Foundation::Collections::IPropertySet *v105; // [rsp+48h] [rbp-B8h] BYREF
  int v106; // [rsp+50h] [rbp-B0h] BYREF
  __int64 (__fastcall ***v107)(_QWORD, GUID *, struct Windows::Foundation::Collections::IPropertySet **); // [rsp+58h] [rbp-A8h] BYREF
  __int64 v108; // [rsp+60h] [rbp-A0h] BYREF
  struct Windows::Foundation::Collections::IPropertySet *v109; // [rsp+68h] [rbp-98h] BYREF
  __int64 v110; // [rsp+70h] [rbp-90h] BYREF
  __int64 v111; // [rsp+78h] [rbp-88h] BYREF
  struct Windows::Foundation::Collections::IPropertySet *v112; // [rsp+80h] [rbp-80h] BYREF
  HSTRING string; // [rsp+88h] [rbp-78h] BYREF
  __int64 v114; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v115; // [rsp+98h] [rbp-68h] BYREF
  __int64 v116; // [rsp+A0h] [rbp-60h] BYREF
  HWND v117; // [rsp+A8h] [rbp-58h] BYREF
  LPVOID v118; // [rsp+B0h] [rbp-50h] BYREF
  HWND v119; // [rsp+B8h] [rbp-48h] BYREF
  void *ppvOut; // [rsp+C0h] [rbp-40h] BYREF
  struct Windows::Foundation::Collections::IPropertySet *v121; // [rsp+C8h] [rbp-38h] BYREF
  int v122; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v123; // [rsp+D8h] [rbp-28h] BYREF
  FullScreenPositionerHelpers *v124; // [rsp+E0h] [rbp-20h] BYREF
  struct Windows::Internal::Shell::ViewManagerInterop::IViewWrapper *v125; // [rsp+E8h] [rbp-18h] BYREF
  struct IAsyncCallback *v126; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v127; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v128; // [rsp+100h] [rbp+0h] BYREF
  __int64 v129; // [rsp+108h] [rbp+8h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+110h] [rbp+10h] BYREF
  HSTRING v131; // [rsp+128h] [rbp+28h]
  _QWORD v132[42]; // [rsp+130h] [rbp+30h] BYREF
  _QWORD v133[42]; // [rsp+280h] [rbp+180h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+418h] [rbp+318h]

  v7 = 0;
  v125 = 0;
  v119 = 0;
  v8 = *(__int64 (__fastcall **)(struct Windows::Internal::Shell::ViewManagerInterop::IViewEventArgsForShowAsViewMode *, struct Windows::Internal::Shell::ViewManagerInterop::IViewWrapper **))(*(_QWORD *)a2 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v125);
  v9 = v8(a2, &v125);
  v10 = v9;
  if ( v9 < 0 )
  {
    v11 = 2009;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"pcshell\\twinui\\appmanager\\lib\\appviewmanager.cpp",
      (const char *)(unsigned int)v9,
      ppv);
LABEL_159:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v125);
    return v10;
  }
  v9 = WindowFromViewWrapper(v125, &v119);
  v10 = v9;
  if ( v9 < 0 )
  {
    v11 = 2010;
    goto LABEL_5;
  }
  v104 = 0;
  v117 = 0;
  v12 = *(__int64 (__fastcall **)(struct Windows::Internal::Shell::ViewManagerInterop::IViewEventArgsForShowAsViewMode *, struct Windows::Internal::Shell::ViewManagerInterop::IViewWrapper **))(*(_QWORD *)a2 + 56LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v104);
  v13 = v12(a2, &v104);
  v10 = v13;
  if ( v13 < 0 )
  {
    v14 = 2014;
LABEL_8:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"pcshell\\twinui\\appmanager\\lib\\appviewmanager.cpp",
      (const char *)(unsigned int)v13,
      ppv);
LABEL_158:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v104);
    goto LABEL_159;
  }
  v13 = WindowFromViewWrapper(v104, &v117);
  v10 = v13;
  if ( v13 < 0 )
  {
    v14 = 2015;
    goto LABEL_8;
  }
  v122 = 0;
  v13 = (*(__int64 (__fastcall **)(struct Windows::Internal::Shell::ViewManagerInterop::IViewEventArgsForShowAsViewMode *, int *))(*(_QWORD *)a2 + 72LL))(
          a2,
          &v122);
  v10 = v13;
  if ( v13 < 0 )
  {
    v14 = 2018;
    goto LABEL_8;
  }
  if ( (unsigned int)(v122 - 1) > 1 )
  {
    v115 = 0;
    v13 = (*(__int64 (__fastcall **)(struct Windows::Internal::Shell::ViewManagerInterop::IViewEventArgsForShowAsViewMode *, unsigned int *))(*(_QWORD *)a2 + 64LL))(
            a2,
            &v115);
    v10 = v13;
    if ( v13 < 0 )
    {
      v14 = 2066;
      goto LABEL_8;
    }
    v128 = 0;
    v129 = 0;
    v13 = (*(__int64 (__fastcall **)(struct Windows::Internal::Shell::ViewManagerInterop::IViewEventArgsForShowAsViewMode *, __int64 *))(*(_QWORD *)a2 + 80LL))(
            a2,
            &v128);
    v10 = v13;
    if ( v13 < 0 )
    {
      v14 = 2069;
      goto LABEL_8;
    }
    v13 = (*(__int64 (__fastcall **)(struct Windows::Internal::Shell::ViewManagerInterop::IViewEventArgsForShowAsViewMode *, char *))(*(_QWORD *)a2 + 88LL))(
            a2,
            (char *)&v128 + 4);
    v10 = v13;
    if ( v13 < 0 )
    {
      v14 = 2070;
      goto LABEL_8;
    }
    if ( !Windows::Internal::ApplicationModel::WindowManagement::IsWindowManagerIDKEnabledForSKU(v15) )
    {
LABEL_27:
      v127 = 0;
      v13 = (*(__int64 (__fastcall **)(struct Windows::Internal::Shell::ViewManagerInterop::IViewEventArgsForShowAsViewMode *, __int64 *))(*(_QWORD *)a2 + 96LL))(
              a2,
              &v127);
      v10 = v13;
      if ( v13 < 0 )
      {
        v14 = 2082;
        goto LABEL_8;
      }
      v105 = 0;
      if ( Windows::Internal::ApplicationModel::WindowManagement::IsWindowManagerIDKEnabledForSKU(v20) )
      {
        v123 = 0;
        v21 = **(__int64 (__fastcall ***)(struct Windows::Internal::Shell::ViewManagerInterop::IViewEventArgsForShowAsViewMode *, GUID *, __int64 *))a2;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v123);
        v22 = v21(a2, &GUID_96c11dea_68de_44ef_a7f7_3aa869663d57, &v123);
        v10 = v22;
        if ( v22 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x829,
            (unsigned int)"pcshell\\twinui\\appmanager\\lib\\appviewmanager.cpp",
            (const char *)(unsigned int)v22,
            ppv);
LABEL_32:
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v123);
LABEL_33:
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v105);
          goto LABEL_158;
        }
        v121 = 0;
        v23 = v123;
        v24 = *(__int64 (__fastcall **)(__int64, struct Windows::Foundation::Collections::IPropertySet **))(*(_QWORD *)v123 + 56LL);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v121);
        v25 = v24(v23, &v121);
        v10 = v25;
        if ( v25 < 0 )
        {
          v26 = 2092;
LABEL_36:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v26,
            (unsigned int)"pcshell\\twinui\\appmanager\\lib\\appviewmanager.cpp",
            (const char *)(unsigned int)v25,
            ppv);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v121);
          goto LABEL_32;
        }
        v27 = v121;
        if ( !v121 )
        {
          v131 = 0;
          Microsoft::WRL::Wrappers::HStringReference::CreateReference(
            &hstringHeader,
            L"Windows.Foundation.Collections.ValueSet",
            0x28u,
            0x27u);
          v25 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>>(
                  v131,
                  &v121);
          v10 = v25;
          if ( v25 < 0 )
          {
            v26 = 2095;
            goto LABEL_36;
          }
          v27 = v121;
        }
        Windows::Internal::ShellHelpers::PropertySetHelper::PropertySetHelper(
          (Windows::Internal::ShellHelpers::PropertySetHelper *)&v112,
          v27);
        v28 = v112;
        v112 = 0;
        v126 = 0;
        v105 = v28;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v126);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v112);
        Windows::Internal::ShellHelpers::PropertySetHelper::Remove(
          (Windows::Internal::ShellHelpers::PropertySetHelper *)&v105,
          v29);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v121);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v123);
      }
      else
      {
        v30 = Windows::Internal::ShellHelpers::PropertySetHelper::CreateFromValueSet((struct Windows::Internal::ShellHelpers::PropertySetHelper *)&v105);
        v10 = v30;
        if ( v30 < 0 )
        {
          v31 = 2105;
          goto LABEL_46;
        }
      }
      v131 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &hstringHeader,
        L"ClientRequestedNavigationType",
        0x1Eu,
        0x1Du);
      v30 = Windows::Internal::ShellHelpers::PropertySetHelper::SetValue<unsigned int>(
              (Windows::Internal::ShellHelpers::PropertySetHelper *)&v105,
              v131);
      v10 = v30;
      if ( v30 < 0 )
      {
        v31 = 2108;
LABEL_46:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v31,
          (unsigned int)"pcshell\\twinui\\appmanager\\lib\\appviewmanager.cpp",
          (const char *)(unsigned int)v30,
          ppv);
        goto LABEL_33;
      }
      v111 = 0;
      v32 = **(__int64 (__fastcall ***)(struct Windows::Internal::Shell::ViewManagerInterop::IViewEventArgsForShowAsViewMode *, GUID *, __int64 *))a2;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v111);
      v33 = v32(a2, &GUID_ca746cf0_7375_4d7a_9d29_6c72d8b5e684, &v111);
      if ( v33 < 0 )
        wil::details::in1diag3::FailFast_Hr(
          retaddr,
          (void *)0x844,
          (unsigned int)"pcshell\\twinui\\appmanager\\lib\\appviewmanager.cpp",
          (const char *)(unsigned int)v33,
          ppv);
      v110 = 0;
      v34 = v111;
      v35 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v111 + 48LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v110);
      v36 = v35(v34, &v110);
      v10 = v36;
      if ( v36 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x847,
          (unsigned int)"pcshell\\twinui\\appmanager\\lib\\appviewmanager.cpp",
          (const char *)(unsigned int)v36,
          ppv);
LABEL_50:
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v110);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v111);
        goto LABEL_33;
      }
      v37 = 0;
      if ( v110 )
      {
        v106 = 0;
        if ( (*(int (__fastcall **)(__int64, int *))(*(_QWORD *)v110 + 48LL))(v110, &v106) >= 0 )
        {
          v37 = v106;
          if ( v106 )
          {
            if ( v106 == 1 )
              v115 = 1;
          }
          else
          {
            v115 = 0;
          }
        }
      }
      wil::ActivityBase<CAppManagerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CAppManagerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v132);
      v132[0] = &CAppViewManagerTelemetry::EnterCompactOverlayModeForView::`vftable';
      v38 = v119;
      if ( v37 == 2 )
      {
        v112 = 0;
        v39 = (void **)IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IHolographicViewTransitionNotificationService>>(&v112);
        Service = IUnknown_QueryService(
                    this[15],
                    &GUID_1841c6d7_4f9d_42c0_af41_8747538f10e5,
                    &GUID_1841c6d7_4f9d_42c0_af41_8747538f10e5,
                    v39);
        v10 = Service;
        if ( Service < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x865,
            (unsigned int)"pcshell\\twinui\\appmanager\\lib\\appviewmanager.cpp",
            (const char *)(unsigned int)Service,
            ppv);
LABEL_60:
          v41 = &v112;
LABEL_61:
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v41);
LABEL_62:
          CAppViewManagerTelemetry::EnterCompactOverlayModeForView::~EnterCompactOverlayModeForView((CAppViewManagerTelemetry::EnterCompactOverlayModeForView *)v132);
          goto LABEL_50;
        }
        v124 = 0;
        v42 = v112;
        v43 = *(__int64 (__fastcall **)(struct Windows::Foundation::Collections::IPropertySet *, HWND, FullScreenPositionerHelpers **))(*(_QWORD *)v112 + 48LL);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v124);
        v44 = v43(v42, v38, &v124);
        v10 = v44;
        if ( v44 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x868,
            (unsigned int)"pcshell\\twinui\\appmanager\\lib\\appviewmanager.cpp",
            (const char *)(unsigned int)v44,
            ppv);
LABEL_65:
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v124);
          goto LABEL_60;
        }
        v119 = 0;
        v45 = v124;
        v46 = **(int (__fastcall ***)(FullScreenPositionerHelpers *, GUID *, __int64))v124;
        v47 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IHolographicViewTransitionNotificationService>>(&v119);
        if ( v46(v45, &GUID_d8b456d0_bec6_4f57_bb1d_50559a14384b, v47) < 0
          || FullScreenPositionerHelpers::IsFullScreenModeDisabledForView(v124, v48) )
        {
          v50 = 0;
        }
        else
        {
          v49 = ViewModePreferencesHelpers::SetTargetPresenterKind(&v105, 2);
          v10 = v49;
          if ( v49 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x870,
              (unsigned int)"pcshell\\twinui\\appmanager\\lib\\appviewmanager.cpp",
              (const char *)(unsigned int)v49,
              ppv);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v119);
            goto LABEL_65;
          }
          v50 = 1;
        }
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v119);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v124);
        v51 = &v112;
LABEL_97:
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v51);
        if ( !v50 )
        {
          v67 = (*(__int64 (__fastcall **)(struct Windows::Internal::Shell::ViewManagerInterop::IViewEventArgsForShowAsViewMode *, __int64))(*(_QWORD *)a2 + 104LL))(
                  a2,
                  1);
          v10 = v67;
          if ( v67 < 0 )
          {
            v68 = 2221;
LABEL_100:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v68,
              (unsigned int)"pcshell\\twinui\\appmanager\\lib\\appviewmanager.cpp",
              (const char *)(unsigned int)v67,
              ppv);
            goto LABEL_62;
          }
          goto LABEL_110;
        }
LABEL_105:
        v118 = a2;
        Microsoft::WRL::ComPtr<IWindowingEnvironmentConfig>::InternalAddRef(&v118);
        v119 = (HWND)a2;
        Microsoft::WRL::ComPtr<IWindowingEnvironmentConfig>::InternalAddRef(&v119);
        v69 = (struct IAsyncCallback **)Microsoft::WRL::Details::Make_Microsoft::WRL::Details::DelegateArgTraits_long____cdecl_IAsyncCallback::___long__::DelegateInvokeHelper_IAsyncCallback__lambda_2cd8efa9c73fdf6fea1f7977b917e9c3___1_long___lambda_2cd8efa9c73fdf6fea1f7977b917e9c3___(
                                          &v112,
                                          &v119);
        v70 = *v69;
        v126 = *v69;
        *v69 = 0;
        if ( v112 )
        {
          v112 = 0;
          Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IApplicationViewChangeListener>::Release();
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v119);
        v71 = CAppViewManager::_ShowViewAsyncWorker(
                (CAppViewManager *)this,
                v38,
                v117,
                (const struct CAppViewManager::ShowViewAsyncOptions *)&v128,
                v105,
                v70,
                a3);
        if ( v71 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x8A9,
            (unsigned int)"pcshell\\twinui\\appmanager\\lib\\appviewmanager.cpp",
            (const char *)(unsigned int)v71,
            ppva);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v126);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v118);
LABEL_110:
        if ( *(_DWORD *)v132[34] == 1 )
          wil::ActivityBase<CAppManagerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v132);
        CAppViewManagerTelemetry::EnterCompactOverlayModeForView::~EnterCompactOverlayModeForView((CAppViewManagerTelemetry::EnterCompactOverlayModeForView *)v132);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v110);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v111);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v105);
        goto LABEL_161;
      }
      if ( v115 != 1 )
      {
        if ( !v115 )
        {
          v67 = ViewModePreferencesHelpers::SetTargetViewMode(&v105, 0);
          v10 = v67;
          if ( v67 < 0 )
          {
            v68 = 2192;
            goto LABEL_100;
          }
          MoveTryPositionPropertiesToPropertySet(
            v38,
            (struct Windows::Internal::ShellHelpers::PropertySetHelper *)&v105);
        }
        goto LABEL_105;
      }
      v116 = 0;
      v52 = (void **)IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IHolographicViewTransitionNotificationService>>(&v116);
      v53 = IUnknown_QueryService(
              this[15],
              &GUID_1841c6d7_4f9d_42c0_af41_8747538f10e5,
              &GUID_1841c6d7_4f9d_42c0_af41_8747538f10e5,
              v52);
      v10 = v53;
      if ( v53 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x876,
          (unsigned int)"pcshell\\twinui\\appmanager\\lib\\appviewmanager.cpp",
          (const char *)(unsigned int)v53,
          ppv);
LABEL_76:
        v41 = (struct Windows::Foundation::Collections::IPropertySet **)&v116;
        goto LABEL_61;
      }
      v114 = 0;
      v54 = v116;
      v55 = *(__int64 (__fastcall **)(__int64, HWND, __int64 *))(*(_QWORD *)v116 + 48LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v114);
      v56 = v55(v54, v38, &v114);
      v10 = v56;
      if ( v56 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x879,
          (unsigned int)"pcshell\\twinui\\appmanager\\lib\\appviewmanager.cpp",
          (const char *)(unsigned int)v56,
          ppv);
LABEL_79:
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v114);
        goto LABEL_76;
      }
      memset(&hstringHeader, 0, sizeof(hstringHeader));
      v57 = v114;
      v58 = *(__int64 (__fastcall **)(__int64, HSTRING_HEADER *))(*(_QWORD *)v114 + 136LL);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&hstringHeader);
      *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = -1;
      *(_QWORD *)&hstringHeader.Reserved.Reserved2[16] = -1;
      v59 = v58(v57, &hstringHeader);
      v10 = v59;
      if ( v59 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x87B,
          (unsigned int)"pcshell\\twinui\\appmanager\\lib\\appviewmanager.cpp",
          (const char *)(unsigned int)v59,
          ppv);
LABEL_82:
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&hstringHeader);
        goto LABEL_79;
      }
      LOBYTE(v7) = v117 != v38;
      Reserved1 = hstringHeader.Reserved.Reserved1;
      wil::ActivityBase<CAppManagerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CAppManagerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v133);
      v133[0] = &CAppViewManagerTelemetry::EnterCompactOverlayModeForView::`vftable';
      CAppViewManagerTelemetry::EnterCompactOverlayModeForView::StartActivity(v133, Reserved1, v7 ^ 1);
      CAppViewManagerTelemetry::EnterCompactOverlayModeForView::operator=(v132, v133);
      CAppViewManagerTelemetry::EnterCompactOverlayModeForView::~EnterCompactOverlayModeForView((CAppViewManagerTelemetry::EnterCompactOverlayModeForView *)v133);
      ppvOut = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppvOut);
      v61 = IUnknown_QueryService(
              this[15],
              &GUID_4d20c9ad_7836_4782_add6_8d92387ee831,
              &GUID_4d20c9ad_7836_4782_add6_8d92387ee831,
              &ppvOut);
      v10 = v61;
      if ( v61 < 0 )
      {
        v62 = 2176;
LABEL_85:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v62,
          (unsigned int)"pcshell\\twinui\\appmanager\\lib\\appviewmanager.cpp",
          (const char *)(unsigned int)v61,
          ppv);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppvOut);
        goto LABEL_82;
      }
      v106 = 0;
      v61 = (*(__int64 (__fastcall **)(void *, __int64, _QWORD, int *))(*(_QWORD *)ppvOut + 96LL))(
              ppvOut,
              v114,
              v7,
              &v106);
      v10 = v61;
      if ( v61 < 0 )
      {
        v62 = 2179;
        goto LABEL_85;
      }
      v50 = v106 != 0;
      if ( v106 )
      {
        v64 = ViewModePreferencesHelpers::SetTargetViewMode(&v105, v115);
        if ( v64 < 0 )
        {
          v65 = 2184;
LABEL_91:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v65,
            (unsigned int)"pcshell\\twinui\\appmanager\\lib\\appviewmanager.cpp",
            (const char *)(unsigned int)v64,
            ppv);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppvOut);
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&hstringHeader);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v114);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v116);
          CAppViewManagerTelemetry::EnterCompactOverlayModeForView::~EnterCompactOverlayModeForView((CAppViewManagerTelemetry::EnterCompactOverlayModeForView *)v132);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v110);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v111);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v105);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v104);
          v10 = v64;
          goto LABEL_159;
        }
        v64 = ViewModePreferencesHelpers::SetSizeHintWidth((ViewModePreferencesHelpers *)&v105, v63, v3);
        if ( v64 < 0 )
        {
          v65 = 2185;
          goto LABEL_91;
        }
        v64 = ViewModePreferencesHelpers::SetSizeHintHeight((ViewModePreferencesHelpers *)&v105, v66, v3);
        if ( v64 < 0 )
        {
          v65 = 2186;
          goto LABEL_91;
        }
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppvOut);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&hstringHeader);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v114);
      v51 = (struct Windows::Foundation::Collections::IPropertySet **)&v116;
      goto LABEL_97;
    }
    v112 = 0;
    v16 = **(__int64 (__fastcall ***)(struct Windows::Internal::Shell::ViewManagerInterop::IViewEventArgsForShowAsViewMode *, GUID *, struct Windows::Foundation::Collections::IPropertySet **))a2;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v112);
    v17 = v16(a2, &GUID_0aeab5ac_7d83_4aa1_9fca_917d7d7bc43f, &v112);
    v18 = retaddr;
    if ( v17 >= 0 )
    {
      v17 = (*(__int64 (__fastcall **)(struct Windows::Foundation::Collections::IPropertySet *, __int64 *))(*(_QWORD *)v112 + 48LL))(
              v112,
              &v129);
      v18 = retaddr;
      if ( v17 >= 0 )
      {
LABEL_26:
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v112);
        goto LABEL_27;
      }
      v19 = 2077;
    }
    else
    {
      v19 = 2075;
    }
    wil::details::in1diag3::_Log_Hr(
      v18,
      (void *)v19,
      (unsigned int)"pcshell\\twinui\\appmanager\\lib\\appviewmanager.cpp",
      (const char *)(unsigned int)v17,
      ppv);
    goto LABEL_26;
  }
  v108 = 0;
  v72 = Microsoft::WRL::ComPtr<Windows::Internal::Shell::ViewManagerInterop::IViewWrapper>::As<Windows::Internal::Shell::ViewManagerInterop::IClientWindowState>(
          &v104,
          &v108);
  v10 = v72;
  if ( v72 < 0 )
  {
    v73 = 2023;
LABEL_115:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v73,
      (unsigned int)"pcshell\\twinui\\appmanager\\lib\\appviewmanager.cpp",
      (const char *)(unsigned int)v72,
      ppv);
LABEL_157:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v108);
    goto LABEL_158;
  }
  LODWORD(v105) = 0;
  v72 = (*(__int64 (__fastcall **)(__int64, struct Windows::Foundation::Collections::IPropertySet **))(*(_QWORD *)v108 + 48LL))(
          v108,
          &v105);
  v10 = v72;
  if ( v72 < 0 )
  {
    v73 = 2025;
    goto LABEL_115;
  }
  v107 = 0;
  v74 = Windows::Internal::StringReference::StringReference(
          (HSTRING *)&hstringHeader,
          L"Windows.Internal.Shell.ModalExperience.ModalExperienceOptions");
  v75 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Internal::Shell::ModalExperience::IModalExperienceDefaultOptions>>(
          *v74,
          &v107);
  v10 = v75;
  if ( v75 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7EF,
      (unsigned int)"pcshell\\twinui\\appmanager\\lib\\appviewmanager.cpp",
      (const char *)(unsigned int)v75,
      ppv);
LABEL_156:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v107);
    goto LABEL_157;
  }
  v109 = 0;
  v76 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v107;
  v77 = **v107;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v109);
  v78 = v77(v76, &GUID_8a43ed9f_f4e6_4421_acf9_1dab2986820c, &v109);
  v10 = v78;
  if ( v78 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7F2,
      (unsigned int)"pcshell\\twinui\\appmanager\\lib\\appviewmanager.cpp",
      (const char *)(unsigned int)v78,
      ppv);
LABEL_155:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v109);
    goto LABEL_156;
  }
  Windows::Internal::ShellHelpers::PropertySetHelper::PropertySetHelper(
    (Windows::Internal::ShellHelpers::PropertySetHelper *)&v106,
    v109);
  v131 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"ModalExperienceOption.ShouldDisplayFullscreen",
    0x2Eu,
    0x2Du);
  v80 = Windows::Internal::ShellHelpers::PropertySetHelper::SetValue<unsigned char>(&v106, v131, v79, 0);
  v10 = v80;
  if ( v80 < 0 )
  {
    v81 = 2037;
LABEL_124:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v81,
      (unsigned int)"pcshell\\twinui\\appmanager\\lib\\appviewmanager.cpp",
      (const char *)(unsigned int)v80,
      ppv);
LABEL_154:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v106);
    goto LABEL_155;
  }
  v131 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"ModalExperienceOption.SuppressSplashscreen",
    0x2Bu,
    0x2Au);
  LOBYTE(v82) = 1;
  v80 = Windows::Internal::ShellHelpers::PropertySetHelper::SetValue<unsigned char>(&v106, v131, v83, v82);
  v10 = v80;
  if ( v80 < 0 )
  {
    v81 = 2038;
    goto LABEL_124;
  }
  v131 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"ModalExperienceOption.SuppressTitleBar",
    0x27u,
    0x26u);
  v80 = Windows::Internal::ShellHelpers::PropertySetHelper::SetValue<unsigned char>(&v106, v131, v84, 0);
  v10 = v80;
  if ( v80 < 0 )
  {
    v81 = 2039;
    goto LABEL_124;
  }
  v131 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"ModalExperienceOption.LinkAsTreeNode",
    0x25u,
    0x24u);
  LOBYTE(v85) = 1;
  v80 = Windows::Internal::ShellHelpers::PropertySetHelper::SetValue<unsigned char>(&v106, v131, v86, v85);
  v10 = v80;
  if ( v80 < 0 )
  {
    v81 = 2040;
    goto LABEL_124;
  }
  v87 = v122 == 1;
  v131 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"ModalExperienceOption.DismissOnIdle",
    0x24u,
    0x23u);
  LOBYTE(v88) = v87;
  v80 = Windows::Internal::ShellHelpers::PropertySetHelper::SetValue<unsigned char>(&v106, v131, v89, v88);
  v10 = v80;
  if ( v80 < 0 )
  {
    v81 = 2043;
    goto LABEL_124;
  }
  v131 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"ModalExperienceOption.ShouldLightDismiss",
    0x29u,
    0x28u);
  LOBYTE(v90) = v87;
  v80 = Windows::Internal::ShellHelpers::PropertySetHelper::SetValue<unsigned char>(&v106, v131, v91, v90);
  v10 = v80;
  if ( v80 < 0 )
  {
    v81 = 2044;
    goto LABEL_124;
  }
  v126 = 0;
  v80 = (*(__int64 (__fastcall **)(struct Windows::Internal::Shell::ViewManagerInterop::IViewEventArgsForShowAsViewMode *, struct IAsyncCallback **))(*(_QWORD *)a2 + 96LL))(
          a2,
          &v126);
  v10 = v80;
  if ( v80 < 0 )
  {
    v81 = 2047;
    goto LABEL_124;
  }
  v80 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, struct Windows::Foundation::Collections::IPropertySet **), struct IAsyncCallback *))(*v107)[6])(
          v107,
          v126);
  v10 = v80;
  if ( v80 < 0 )
  {
    v81 = 2048;
    goto LABEL_124;
  }
  v80 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, struct Windows::Foundation::Collections::IPropertySet **), _QWORD))(*v107)[10])(
          v107,
          0);
  v10 = v80;
  if ( v80 < 0 )
  {
    v81 = 2049;
    goto LABEL_124;
  }
  string = 0;
  v92 = v125;
  v93 = *(__int64 (__fastcall **)(struct Windows::Internal::Shell::ViewManagerInterop::IViewWrapper *, HSTRING *))(*(_QWORD *)v125 + 480LL);
  WindowsDeleteString(0);
  string = 0;
  v94 = v93(v92, &string);
  v10 = v94;
  if ( v94 < 0 )
  {
    v95 = 2052;
LABEL_143:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v95,
      (unsigned int)"pcshell\\twinui\\appmanager\\lib\\appviewmanager.cpp",
      (const char *)(unsigned int)v94,
      ppv);
LABEL_153:
    WindowsDeleteString(string);
    string = 0;
    goto LABEL_154;
  }
  v94 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, struct Windows::Foundation::Collections::IPropertySet **), HSTRING))(*v107)[12])(
          v107,
          string);
  v10 = v94;
  if ( v94 < 0 )
  {
    v95 = 2053;
    goto LABEL_143;
  }
  v117 = 0;
  v118 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v118);
  v96 = CoCreateInstance(&CLSID_ImmersiveShell, 0, 0x404u, &GUID_6d5140c1_7436_11ce_8034_00aa006009fa, &v118);
  v10 = v96;
  if ( v96 < 0 )
  {
    v97 = 2058;
LABEL_152:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v97,
      (unsigned int)"pcshell\\twinui\\appmanager\\lib\\appviewmanager.cpp",
      (const char *)(unsigned int)v96,
      ppvb);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v118);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v117);
    goto LABEL_153;
  }
  v98 = v118;
  v99 = *(__int64 (__fastcall **)(LPVOID, __int64 *, GUID *, HWND *))(*(_QWORD *)v118 + 24LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v117);
  v96 = v99(v98, qword_18078D7C0, &GUID_73ef35c2_3adf_4ac8_8383_0850e26e9683, &v117);
  v10 = v96;
  if ( v96 < 0 )
  {
    v97 = 2059;
    goto LABEL_152;
  }
  v96 = (*(__int64 (__fastcall **)(HWND, struct Windows::Internal::Shell::ViewManagerInterop::IViewWrapper *, _QWORD, __int64 (__fastcall ***)(_QWORD, GUID *, struct Windows::Foundation::Collections::IPropertySet **)))(*(_QWORD *)v117 + 48LL))(
          v117,
          v125,
          (unsigned int)v105,
          v107);
  v10 = v96;
  if ( v96 < 0 )
  {
    v97 = 2061;
    goto LABEL_152;
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v118);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v117);
  WindowsDeleteString(string);
  string = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v106);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v109);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v107);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v108);
LABEL_161:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v104);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v125);
  return 0;
}

```

## disassembly

```asm
0x18037f630  mov     [rsp-8+arg_18], rbx
0x18037f635  push    rbp
0x18037f636  push    rsi
0x18037f637  push    rdi
0x18037f638  push    r12
0x18037f63a  push    r13
0x18037f63c  push    r14
0x18037f63e  push    r15
0x18037f640  lea     rbp, [rsp-2E0h]
0x18037f648  sub     rsp, 3E0h
0x18037f64f  mov     rax, cs:__security_cookie
0x18037f656  xor     rax, rsp
0x18037f659  mov     [rbp+310h+var_40], rax
0x18037f660  mov     r12, r8
0x18037f663  mov     rsi, rdx
0x18037f666  mov     r13, rcx
0x18037f669  xor     r15d, r15d
0x18037f66c  mov     [rbp+310h+var_328], r15
0x18037f670  mov     [rbp+310h+var_358], r15
0x18037f674  mov     rax, [rdx]
0x18037f677  mov     rbx, [rax+30h]
0x18037f67b  lea     rcx, [rbp+310h+var_328]
0x18037f67f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18037f684  lea     rdx, [rbp+310h+var_328]
0x18037f688  mov     rcx, rsi
0x18037f68b  mov     rax, rbx
0x18037f68e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18037f693  mov     ebx, eax
0x18037f695  test    eax, eax
0x18037f697  jns     short loc_18037F6A0
0x18037f699  mov     edx, 7D9h
0x18037f69e  jmp     short loc_18037F6B8
0x18037f6a0  lea     rdx, [rbp+310h+var_358]; HWND *
0x18037f6a4  mov     rcx, [rbp+310h+var_328]; struct Windows::Internal::Shell::ViewManagerInterop::IViewWrapper *
0x18037f6a8  call    ?WindowFromViewWrapper@@YAJPEAUIViewWrapper@ViewManagerInterop@Shell@Internal@Windows@@PEAPEAUHWND__@@@Z; WindowFromViewWrapper(Windows::Internal::Shell::ViewManagerInterop::IViewWrapper *,HWND__ * *)
0x18037f6ad  mov     ebx, eax
0x18037f6af  test    eax, eax
0x18037f6b1  jns     short loc_18037F6D3
0x18037f6b3  mov     edx, 7DAh; void *
0x18037f6b8  lea     r8, aPcshellTwinuiA_27; "pcshell\\twinui\\appmanager\\lib\\appvi"...
0x18037f6bf  mov     r9d, eax; char *
0x18037f6c2  mov     rcx, [rbp+318h]; this
0x18037f6c9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18037f6ce  jmp     loc_1803805DE
0x18037f6d3  mov     [rsp+410h+var_3D0], r15
0x18037f6d8  mov     [rbp+310h+var_368], r15
0x18037f6dc  mov     rax, [rsi]
0x18037f6df  mov     rbx, [rax+38h]
0x18037f6e3  lea     rcx, [rsp+410h+var_3D0]
0x18037f6e8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18037f6ed  lea     rdx, [rsp+410h+var_3D0]
0x18037f6f2  mov     rcx, rsi
0x18037f6f5  mov     rax, rbx
0x18037f6f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18037f6fd  mov     ebx, eax
0x18037f6ff  test    eax, eax
0x18037f701  jns     short loc_18037F723
0x18037f703  mov     edx, 7DEh; void *
0x18037f708  mov     rcx, [rbp+318h]; this
0x18037f70f  mov     r9d, eax; char *
0x18037f712  lea     r8, aPcshellTwinuiA_27; "pcshell\\twinui\\appmanager\\lib\\appvi"...
0x18037f719  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18037f71e  jmp     loc_1803805D3
0x18037f723  lea     rdx, [rbp+310h+var_368]; HWND *
0x18037f727  mov     rcx, [rsp+410h+var_3D0]; struct Windows::Internal::Shell::ViewManagerInterop::IViewWrapper *
0x18037f72c  call    ?WindowFromViewWrapper@@YAJPEAUIViewWrapper@ViewManagerInterop@Shell@Internal@Windows@@PEAPEAUHWND__@@@Z; WindowFromViewWrapper(Windows::Internal::Shell::ViewManagerInterop::IViewWrapper *,HWND__ * *)
0x18037f731  mov     ebx, eax
0x18037f733  test    eax, eax
0x18037f735  jns     short loc_18037F73E
0x18037f737  mov     edx, 7DFh
0x18037f73c  jmp     short loc_18037F708
0x18037f73e  mov     [rbp+310h+var_340], r15d
0x18037f742  mov     rax, [rsi]
0x18037f745  lea     rdx, [rbp+310h+var_340]
0x18037f749  mov     rcx, rsi
0x18037f74c  mov     rax, [rax+48h]
0x18037f750  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18037f755  mov     ebx, eax
0x18037f757  test    eax, eax
0x18037f759  jns     short loc_18037F762
0x18037f75b  mov     edx, 7E2h
0x18037f760  jmp     short loc_18037F708
0x18037f762  mov     eax, [rbp+310h+var_340]
0x18037f765  dec     eax
0x18037f767  cmp     eax, 1
0x18037f76a  jbe     loc_18038012C
0x18037f770  mov     [rbp+310h+var_378], r15d
0x18037f774  mov     rax, [rsi]
0x18037f777  lea     rdx, [rbp+310h+var_378]
0x18037f77b  mov     rcx, rsi
0x18037f77e  mov     rax, [rax+40h]
0x18037f782  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18037f787  mov     ebx, eax
0x18037f789  test    eax, eax
0x18037f78b  jns     short loc_18037F797
0x18037f78d  mov     edx, 812h
0x18037f792  jmp     loc_18037F708
0x18037f797  mov     [rbp+310h+var_310], r15
0x18037f79b  mov     [rbp+310h+var_308], r15
0x18037f79f  mov     rax, [rsi]
0x18037f7a2  lea     rdx, [rbp+310h+var_310]
0x18037f7a6  mov     rcx, rsi
0x18037f7a9  mov     rax, [rax+50h]
0x18037f7ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18037f7b2  mov     ebx, eax
0x18037f7b4  test    eax, eax
0x18037f7b6  jns     short loc_18037F7C2
0x18037f7b8  mov     edx, 815h
0x18037f7bd  jmp     loc_18037F708
0x18037f7c2  mov     rax, [rsi]
0x18037f7c5  lea     rdx, [rbp+310h+var_310+4]
0x18037f7c9  mov     rcx, rsi
0x18037f7cc  mov     rax, [rax+58h]
0x18037f7d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18037f7d5  mov     ebx, eax
0x18037f7d7  test    eax, eax
0x18037f7d9  jns     short loc_18037F7E5
0x18037f7db  mov     edx, 816h
0x18037f7e0  jmp     loc_18037F708
0x18037f7e5  call    ?IsWindowManagerIDKEnabledForSKU@WindowManagement@ApplicationModel@Internal@Windows@@YA_NXZ; Windows::Internal::ApplicationModel::WindowManagement::IsWindowManagerIDKEnabledForSKU(void)
0x18037f7ea  test    al, al
0x18037f7ec  jz      short loc_18037F866
0x18037f7ee  mov     [rbp+310h+var_390], r15
0x18037f7f2  mov     rax, [rsi]
0x18037f7f5  mov     rbx, [rax]
0x18037f7f8  lea     rcx, [rbp+310h+var_390]
0x18037f7fc  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18037f801  lea     r8, [rbp+310h+var_390]
0x18037f805  lea     rdx, _GUID_0aeab5ac_7d83_4aa1_9fca_917d7d7bc43f
0x18037f80c  mov     rcx, rsi
0x18037f80f  mov     rax, rbx
0x18037f812  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18037f817  mov     rcx, [rbp+318h]
0x18037f81e  test    eax, eax
0x18037f820  jns     short loc_18037F829
0x18037f822  mov     edx, 81Bh
0x18037f827  jmp     short loc_18037F84D
0x18037f829  mov     rcx, [rbp+310h+var_390]
0x18037f82d  mov     rax, [rcx]
0x18037f830  lea     rdx, [rbp+310h+var_308]
0x18037f834  mov     rax, [rax+30h]
0x18037f838  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18037f83d  mov     rcx, [rbp+318h]; this
0x18037f844  test    eax, eax
0x18037f846  jns     short loc_18037F85D
0x18037f848  mov     edx, 81Dh; void *
0x18037f84d  mov     r9d, eax; char *
0x18037f850  lea     r8, aPcshellTwinuiA_27; "pcshell\\twinui\\appmanager\\lib\\appvi"...
0x18037f857  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18037f85c  nop
0x18037f85d  lea     rcx, [rbp+310h+var_390]
0x18037f861  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18037f866  xor     eax, eax
0x18037f868  mov     [rbp+310h+var_318], rax
0x18037f86c  mov     rax, [rsi]
0x18037f86f  lea     rdx, [rbp+310h+var_318]
0x18037f873  mov     rcx, rsi
0x18037f876  mov     rax, [rax+60h]
0x18037f87a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18037f87f  mov     ebx, eax
0x18037f881  test    eax, eax
0x18037f883  jns     short loc_18037F88F
0x18037f885  mov     edx, 822h
0x18037f88a  jmp     loc_18037F708
0x18037f88f  mov     [rsp+410h+var_3C8], r15
0x18037f894  call    ?IsWindowManagerIDKEnabledForSKU@WindowManagement@ApplicationModel@Internal@Windows@@YA_NXZ; Windows::Internal::ApplicationModel::WindowManagement::IsWindowManagerIDKEnabledForSKU(void)
0x18037f899  test    al, al
0x18037f89b  jz      loc_18037FA26
0x18037f8a1  mov     [rbp+310h+var_338], r15
0x18037f8a5  mov     rax, [rsi]
0x18037f8a8  mov     rbx, [rax]
0x18037f8ab  lea     rcx, [rbp+310h+var_338]
0x18037f8af  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18037f8b4  lea     r8, [rbp+310h+var_338]
0x18037f8b8  lea     rdx, _GUID_96c11dea_68de_44ef_a7f7_3aa869663d57
0x18037f8bf  mov     rcx, rsi
0x18037f8c2  mov     rax, rbx
0x18037f8c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18037f8ca  mov     ebx, eax
0x18037f8cc  test    eax, eax
0x18037f8ce  jns     short loc_18037F905
0x18037f8d0  mov     rcx, [rbp+318h]; this
0x18037f8d7  mov     r9d, eax; char *
0x18037f8da  lea     r8, aPcshellTwinuiA_27; "pcshell\\twinui\\appmanager\\lib\\appvi"...
0x18037f8e1  mov     edx, 829h; void *
0x18037f8e6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18037f8eb  nop
0x18037f8ec  lea     rcx, [rbp+310h+var_338]
0x18037f8f0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18037f8f5  nop
0x18037f8f6  lea     rcx, [rsp+410h+var_3C8]
0x18037f8fb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18037f900  jmp     loc_1803805D3
0x18037f905  mov     [rbp+310h+var_348], r15
0x18037f909  mov     rdi, [rbp+310h+var_338]
0x18037f90d  mov     rax, [rdi]
0x18037f910  mov     rbx, [rax+38h]
0x18037f914  lea     rcx, [rbp+310h+var_348]
0x18037f918  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18037f91d  lea     rdx, [rbp+310h+var_348]
0x18037f921  mov     rcx, rdi
0x18037f924  mov     rax, rbx
0x18037f927  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18037f92c  mov     ebx, eax
0x18037f92e  test    eax, eax
0x18037f930  jns     short loc_18037F959
0x18037f932  mov     edx, 82Ch; void *
0x18037f937  lea     r8, aPcshellTwinuiA_27; "pcshell\\twinui\\appmanager\\lib\\appvi"...
0x18037f93e  mov     r9d, eax; char *
0x18037f941  mov     rcx, [rbp+318h]; this
0x18037f948  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18037f94d  nop
0x18037f94e  lea     rcx, [rbp+310h+var_348]
0x18037f952  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18037f957  jmp     short loc_18037F8EC
0x18037f959  mov     rdx, [rbp+310h+var_348]
0x18037f95d  test    rdx, rdx
0x18037f960  jnz     short loc_18037F99C
0x18037f962  mov     [rbp+310h+var_2E8], r15
0x18037f966  lea     r9d, [rdx+27h]; unsigned int
0x18037f96a  lea     r8d, [rdx+28h]; unsigned int
0x18037f96e  lea     rdx, ?RuntimeClass_Windows_Foundation_Collections_ValueSet@@3QBGB; "Windows.Foundation.Collections.ValueSet"
0x18037f975  lea     rcx, [rbp+310h+hstringHeader]; hstringHeader
0x18037f979  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18037f97e  lea     rdx, [rbp+310h+var_348]
0x18037f982  mov     rcx, [rbp+310h+var_2E8]
0x18037f986  call    ??$ActivateInstance@V?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>>)
0x18037f98b  mov     ebx, eax
0x18037f98d  test    eax, eax
0x18037f98f  jns     short loc_18037F998
0x18037f991  mov     edx, 82Fh
0x18037f996  jmp     short loc_18037F937
0x18037f998  mov     rdx, [rbp+310h+var_348]; struct Windows::Foundation::Collections::IPropertySet *
0x18037f99c  lea     rcx, [rbp+310h+var_390]; this
0x18037f9a0  call    ??0PropertySetHelper@ShellHelpers@Internal@Windows@@QEAA@PEAUIPropertySet@Collections@Foundation@3@@Z; Windows::Internal::ShellHelpers::PropertySetHelper::PropertySetHelper(Windows::Foundation::Collections::IPropertySet *)
0x18037f9a5  mov     rax, [rbp+310h+var_390]
0x18037f9a9  mov     [rbp+310h+var_390], r15
0x18037f9ad  mov     [rbp+310h+var_320], r15
0x18037f9b1  mov     [rsp+410h+var_3C8], rax
0x18037f9b6  lea     rcx, [rbp+310h+var_320]
0x18037f9ba  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18037f9bf  lea     rcx, [rbp+310h+var_390]
0x18037f9c3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18037f9c8  lea     rcx, [rsp+410h+var_3C8]; this
0x18037f9cd  call    ?Remove@PropertySetHelper@ShellHelpers@Internal@Windows@@QEAAJPEBG@Z; Windows::Internal::ShellHelpers::PropertySetHelper::Remove(ushort const *)
0x18037f9d2  nop
0x18037f9d3  lea     rcx, [rbp+310h+var_348]
0x18037f9d7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18037f9dc  nop
0x18037f9dd  lea     rcx, [rbp+310h+var_338]
0x18037f9e1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18037f9e6  mov     [rbp+310h+var_2E8], r15
0x18037f9ea  mov     r9d, 1Dh; unsigned int
0x18037f9f0  lea     r8d, [r9+1]; unsigned int
0x18037f9f4  lea     rdx, aClientrequeste; "ClientRequestedNavigationType"
0x18037f9fb  lea     rcx, [rbp+310h+hstringHeader]; hstringHeader
0x18037f9ff  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18037fa04  nop
0x18037fa05  mov     r9d, 2
0x18037fa0b  mov     rdx, [rbp+310h+var_2E8]; HSTRING
0x18037fa0f  lea     rcx, [rsp+410h+var_3C8]; this
0x18037fa14  call    ??$SetValue@I@PropertySetHelper@ShellHelpers@Internal@Windows@@AEAAJPEAUHSTRING__@@P8IPropertyValueStatics@Foundation@3@EAAJIPEAPEAUIInspectable@@@ZI@Z; Windows::Internal::ShellHelpers::PropertySetHelper::SetValue<uint>(HSTRING__ *,long (Windows::Foundation::IPropertyValueStatics::*)(uint,IInspectable * *),uint)
0x18037fa19  mov     ebx, eax
0x18037fa1b  test    eax, eax
0x18037fa1d  jns     short loc_18037FA56
0x18037fa1f  mov     edx, 83Ch
0x18037fa24  jmp     short loc_18037FA3B
0x18037fa26  lea     rcx, [rsp+410h+var_3C8]; struct Windows::Internal::ShellHelpers::PropertySetHelper *
0x18037fa2b  call    ?CreateFromValueSet@PropertySetHelper@ShellHelpers@Internal@Windows@@SAJAEAV1234@@Z; Windows::Internal::ShellHelpers::PropertySetHelper::CreateFromValueSet(Windows::Internal::ShellHelpers::PropertySetHelper &)
0x18037fa30  mov     ebx, eax
0x18037fa32  test    eax, eax
0x18037fa34  jns     short loc_18037F9E6
0x18037fa36  mov     edx, 839h; void *
0x18037fa3b  lea     r8, aPcshellTwinuiA_27; "pcshell\\twinui\\appmanager\\lib\\appvi"...
0x18037fa42  mov     r9d, eax; char *
0x18037fa45  mov     rcx, [rbp+318h]; this
0x18037fa4c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18037fa51  jmp     loc_18037F8F6
0x18037fa56  mov     [rsp+410h+var_398], r15
0x18037fa5b  mov     rax, [rsi]
0x18037fa5e  mov     rbx, [rax]
0x18037fa61  lea     rcx, [rsp+410h+var_398]
0x18037fa66  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18037fa6b  lea     r8, [rsp+410h+var_398]
0x18037fa70  lea     rdx, _GUID_ca746cf0_7375_4d7a_9d29_6c72d8b5e684
0x18037fa77  mov     rcx, rsi
0x18037fa7a  mov     rax, rbx
0x18037fa7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18037fa82  mov     rcx, [rbp+318h]; this
0x18037fa89  test    eax, eax
0x18037fa8b  js      loc_180380679
0x18037fa91  mov     [rsp+410h+var_3A0], r15
0x18037fa96  mov     rdi, [rsp+410h+var_398]
0x18037fa9b  mov     rax, [rdi]
0x18037fa9e  mov     rbx, [rax+30h]
0x18037faa2  lea     rcx, [rsp+410h+var_3A0]
0x18037faa7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18037faac  lea     rdx, [rsp+410h+var_3A0]
0x18037fab1  mov     rcx, rdi
0x18037fab4  mov     rax, rbx
  ... truncated ...
```
