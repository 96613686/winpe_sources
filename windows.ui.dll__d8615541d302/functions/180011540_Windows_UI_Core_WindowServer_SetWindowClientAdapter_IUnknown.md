# Windows::UI::Core::WindowServer::SetWindowClientAdapter(IUnknown *)

- ea: `0x180011540`
- end: `0x180011dd3`
- name: `?SetWindowClientAdapter@WindowServer@Core@UI@Windows@@UEAAJPEAUIUnknown@@@Z`
- size: `2195`
- prototype: `__int64 __fastcall(Windows::UI::Core::WindowServer *__hidden this, struct IUnknown *)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800038e0`
- `0x180010738`
- `0x180011540`
- `0x180014754`
- `0x180050360`
- `0x180059988`
- `0x18005a804`
- `0x18005f1a4`
- `0x1800ca010`

## import_xrefs

- `api-ms-win-rtcore-ntuser-private-l1-1-7!IsOneCoreTransformMode` at `0x1800115d9`
- `api-ms-win-rtcore-ntuser-private-l1-1-7!IsOneCoreTransformMode` at `0x1800115d9`

## string_xrefs

- `0x18001183b`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\windowserver.cpp`
- `0x1800119e6`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\windowserver.cpp`
- `0x180011aaf`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\windowserver.cpp`
- `0x180011ae7`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\windowserver.cpp`
- `0x180011b1f`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\windowserver.cpp`
- `0x180011bb0`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\windowserver.cpp`
- `0x180011bfe`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\windowserver.cpp`
- `0x180011c17`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\windowserver.cpp`
- `0x180011c69`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\windowserver.cpp`
- `0x180011ca1`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\windowserver.cpp`
- `0x180011ceb`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\windowserver.cpp`
- `0x180011d7e`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\windowserver.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::UI::Core::WindowServer::SetWindowClientAdapter(
        Windows::UI::Core::WindowServer *this,
        struct IUnknown *a2)
{
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rbx
  _QWORD *v5; // r14
  int v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, __int64 *); // rbx
  int v10; // eax
  __int64 (__fastcall ***v11)(_QWORD, GUID *, __int64 *); // rdi
  __int64 (__fastcall *v12)(_QWORD, GUID *, __int64 *); // rbx
  int v13; // eax
  int v14; // eax
  __int64 v15; // rcx
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64, __int64, char *); // r12
  void *v18; // rax
  __int64 v19; // rbx
  int v20; // edi
  __int64 v21; // rdi
  __int64 (__fastcall *v22)(__int64, __int64, char *); // r12
  void *v23; // rax
  __int64 v24; // rbx
  __int64 v25; // rdi
  __int64 (__fastcall *v26)(__int64, __int64, char *); // r12
  void *v27; // rax
  __int64 v28; // rbx
  __int64 v29; // rdi
  __int64 (__fastcall *v30)(__int64, __int64, char *); // r12
  void *v31; // rax
  __int64 v32; // rbx
  int v33; // edi
  __int64 v34; // rcx
  __int64 v36; // rdi
  __int64 (__fastcall *v37)(__int64, __int64, char *); // r12
  void *v38; // rax
  __int64 v39; // rbx
  __int64 v40; // rdi
  __int64 (__fastcall *v41)(__int64, __int64, char *); // r12
  void *v42; // rax
  __int64 v43; // rbx
  int v44; // eax
  __int64 v45; // rdi
  __int64 (__fastcall *v46)(__int64, __int64 *); // rbx
  int v47; // eax
  __int64 v48; // rdi
  int v49; // eax
  __int64 v50; // rcx
  __int64 v51; // rcx
  __int64 v52; // rdi
  __int64 (__fastcall *v53)(__int64, __int64, char *); // r12
  void *v54; // rax
  __int64 v55; // rbx
  __int64 v56; // rcx
  __int64 v57; // rcx
  __int64 (__fastcall *v58)(__int64, __int64, char *); // r14
  void *v59; // rax
  __int64 v60; // rbx
  __int64 v61; // rcx
  __int64 v62; // rcx
  __int64 v63; // rcx
  __int64 v64; // rcx
  __int64 v65; // rcx
  __int64 v66; // rdx
  char *v67; // [rsp+20h] [rbp-20h] BYREF
  int (*v68)(Windows::UI::Core::WindowServer *__hidden, struct IInspectable *, struct IInspectable *); // [rsp+28h] [rbp-18h]
  int v69; // [rsp+30h] [rbp-10h]
  int v70; // [rsp+34h] [rbp-Ch]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+38h]
  __int64 v72; // [rsp+80h] [rbp+40h] BYREF
  __int64 v73; // [rsp+88h] [rbp+48h] BYREF
  __int64 v74; // [rsp+90h] [rbp+50h] BYREF

  QueryInterface = a2->lpVtbl->QueryInterface;
  v5 = (_QWORD *)((char *)this + 2768);
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease((char *)this + 2768);
  v6 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, _QWORD *))QueryInterface)(
         a2,
         &GUID_6d015416_85e6_48c2_8b21_66b2be166aeb,
         v5);
  v7 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1496,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\windowserver.cpp",
      (const char *)(unsigned int)v6,
      (int)v67);
    return v7;
  }
  v72 = 0;
  v8 = *((_QWORD *)this + 346);
  v9 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v8 + 56LL);
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v72);
  v10 = v9(v8, &v72);
  v7 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1499,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\windowserver.cpp",
      (const char *)(unsigned int)v10,
      (int)v67);
LABEL_96:
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v72);
    return v7;
  }
  if ( v72 )
  {
    if ( (unsigned int)IsOneCoreTransformMode() )
    {
      v52 = v72;
      v53 = *(__int64 (__fastcall **)(__int64, __int64, char *))(*(_QWORD *)v72 + 96LL);
      v67 = (char *)this - 296;
      v68 = (int (*)(Windows::UI::Core::WindowServer *__hidden, struct IInspectable *, struct IInspectable *))Windows::UI::Core::WindowServer::OnScaleChanged;
      v69 = 0;
      v70 = (unsigned __int64)Windows::UI::Core::WindowServer::OnScaleChanged >> 32;
      v54 = operator new(0x28u, (const struct std::nothrow_t *)std::nothrow);
      if ( v54 )
        v55 = Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::IEventHandler_impl<IInspectable *>::*)(IInspectable *,IInspectable *)>::DelegateInvokeHelper<Windows::Foundation::IEventHandler<IInspectable *>,_lambda_634b894932902ed343c0f50784bfa094_,-1,IInspectable *,IInspectable *>::DelegateInvokeHelper<Windows::Foundation::IEventHandler<IInspectable *>,_lambda_634b894932902ed343c0f50784bfa094_,-1,IInspectable *,IInspectable *>(
                v54,
                &v67);
      else
        v55 = 0;
      v33 = v53(v52, v55, (char *)this + 712);
      if ( v55 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
      if ( v33 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x14A2,
          (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\windowserver.cpp",
          (const char *)(unsigned int)v33,
          (int)v67);
        v56 = v72;
        if ( v72 )
        {
          v72 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
        }
        return (unsigned int)v33;
      }
    }
    v74 = 0;
    v11 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 379);
    v12 = **v11;
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v74);
    v13 = v12(v11, &GUID_482462bd_3f10_48f1_a406_7bf22c9a3732, &v74);
    if ( v13 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x14A6,
        (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\windowserver.cpp",
        (const char *)(unsigned int)v13,
        (int)v67);
    v14 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v74 + 48LL))(v74, v72);
    v7 = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x14A8,
        (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\windowserver.cpp",
        (const char *)(unsigned int)v14,
        (int)v67);
      v63 = v74;
      if ( v74 )
      {
        v74 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v63 + 16LL))(v63);
      }
      v64 = v72;
      if ( v72 )
      {
        v72 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v64 + 16LL))(v64);
      }
      return v7;
    }
    v15 = v74;
    if ( v74 )
    {
      v74 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    }
  }
  v16 = *v5;
  v17 = *(__int64 (__fastcall **)(__int64, __int64, char *))(*(_QWORD *)*v5 + 416LL);
  v67 = (char *)this - 296;
  v68 = Windows::UI::Core::WindowServer::OnWindowClientAdapterConsolidated;
  v69 = 0;
  v70 = (unsigned __int64)Windows::UI::Core::WindowServer::OnWindowClientAdapterConsolidated >> 32;
  v18 = operator new(0x28u, (const struct std::nothrow_t *)std::nothrow);
  if ( v18 )
    v19 = Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::IEventHandler_impl<IInspectable *>::*)(IInspectable *,IInspectable *)>::DelegateInvokeHelper<Windows::Foundation::IEventHandler<IInspectable *>,_lambda_634b894932902ed343c0f50784bfa094_,-1,IInspectable *,IInspectable *>::DelegateInvokeHelper<Windows::Foundation::IEventHandler<IInspectable *>,_lambda_634b894932902ed343c0f50784bfa094_,-1,IInspectable *,IInspectable *>(
            v18,
            &v67);
  else
    v19 = 0;
  v20 = v17(v16, v19, (char *)this + 680);
  if ( v19 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  if ( v20 < 0 )
  {
    v66 = 5294;
LABEL_87:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v66,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\windowserver.cpp",
      (const char *)(unsigned int)v20,
      (int)v67);
    v7 = v20;
    goto LABEL_96;
  }
  v21 = *v5;
  v22 = *(__int64 (__fastcall **)(__int64, __int64, char *))(*(_QWORD *)*v5 + 400LL);
  v67 = (char *)this - 296;
  v68 = (int (*)(Windows::UI::Core::WindowServer *__hidden, struct IInspectable *, struct IInspectable *))Windows::UI::Core::WindowServer::OnWindowClientAdapterClosed;
  v69 = 0;
  v70 = (unsigned __int64)Windows::UI::Core::WindowServer::OnWindowClientAdapterClosed >> 32;
  v23 = operator new(0x28u, (const struct std::nothrow_t *)std::nothrow);
  if ( v23 )
    v24 = Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::IEventHandler_impl<IInspectable *>::*)(IInspectable *,IInspectable *)>::DelegateInvokeHelper<Windows::Foundation::IEventHandler<IInspectable *>,_lambda_634b894932902ed343c0f50784bfa094_,-1,IInspectable *,IInspectable *>::DelegateInvokeHelper<Windows::Foundation::IEventHandler<IInspectable *>,_lambda_634b894932902ed343c0f50784bfa094_,-1,IInspectable *,IInspectable *>(
            v23,
            &v67);
  else
    v24 = 0;
  v20 = v22(v21, v24, (char *)this + 672);
  if ( v24 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  if ( v20 < 0 )
  {
    v66 = 5297;
    goto LABEL_87;
  }
  v25 = *v5;
  v26 = *(__int64 (__fastcall **)(__int64, __int64, char *))(*(_QWORD *)*v5 + 496LL);
  v67 = (char *)this - 296;
  v68 = (int (*)(Windows::UI::Core::WindowServer *__hidden, struct IInspectable *, struct IInspectable *))Windows::UI::Core::WindowServer::OnLogicalSizeChanged;
  v69 = 0;
  v70 = (unsigned __int64)Windows::UI::Core::WindowServer::OnLogicalSizeChanged >> 32;
  v27 = operator new(0x28u, (const struct std::nothrow_t *)std::nothrow);
  if ( v27 )
    v28 = Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::IEventHandler_impl<IInspectable *>::*)(IInspectable *,IInspectable *)>::DelegateInvokeHelper<Windows::Foundation::IEventHandler<IInspectable *>,_lambda_634b894932902ed343c0f50784bfa094_,-1,IInspectable *,IInspectable *>::DelegateInvokeHelper<Windows::Foundation::IEventHandler<IInspectable *>,_lambda_634b894932902ed343c0f50784bfa094_,-1,IInspectable *,IInspectable *>(
            v27,
            &v67);
  else
    v28 = 0;
  v20 = v26(v25, v28, (char *)this + 688);
  if ( v28 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
  if ( v20 < 0 )
  {
    v66 = 5300;
    goto LABEL_87;
  }
  v29 = *v5;
  v30 = *(__int64 (__fastcall **)(__int64, __int64, char *))(*(_QWORD *)*v5 + 528LL);
  v67 = (char *)this - 296;
  v68 = (int (*)(Windows::UI::Core::WindowServer *__hidden, struct IInspectable *, struct IInspectable *))Windows::UI::Core::WindowServer::OnPhysicalBoundsChanged;
  v69 = 0;
  v70 = (unsigned __int64)Windows::UI::Core::WindowServer::OnPhysicalBoundsChanged >> 32;
  v31 = operator new(0x28u, (const struct std::nothrow_t *)std::nothrow);
  if ( v31 )
    v32 = Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::IEventHandler_impl<IInspectable *>::*)(IInspectable *,IInspectable *)>::DelegateInvokeHelper<Windows::Foundation::IEventHandler<IInspectable *>,_lambda_634b894932902ed343c0f50784bfa094_,-1,IInspectable *,IInspectable *>::DelegateInvokeHelper<Windows::Foundation::IEventHandler<IInspectable *>,_lambda_634b894932902ed343c0f50784bfa094_,-1,IInspectable *,IInspectable *>(
            v31,
            &v67);
  else
    v32 = 0;
  v33 = v30(v29, v32, (char *)this + 704);
  if ( v32 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
  if ( v33 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x14B7,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\windowserver.cpp",
      (const char *)(unsigned int)v33,
      (int)v67);
    v34 = v72;
    if ( v72 )
    {
      v72 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
    }
    return (unsigned int)v33;
  }
  v36 = *v5;
  v37 = *(__int64 (__fastcall **)(__int64, __int64, char *))(*(_QWORD *)*v5 + 544LL);
  v67 = (char *)this - 296;
  v68 = Windows::UI::Core::WindowServer::OnVisibleBoundsChanged;
  v69 = 0;
  v70 = (unsigned __int64)Windows::UI::Core::WindowServer::OnVisibleBoundsChanged >> 32;
  v38 = operator new(0x28u, (const struct std::nothrow_t *)std::nothrow);
  if ( v38 )
    v39 = Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::IEventHandler_impl<IInspectable *>::*)(IInspectable *,IInspectable *)>::DelegateInvokeHelper<Windows::Foundation::IEventHandler<IInspectable *>,_lambda_634b894932902ed343c0f50784bfa094_,-1,IInspectable *,IInspectable *>::DelegateInvokeHelper<Windows::Foundation::IEventHandler<IInspectable *>,_lambda_634b894932902ed343c0f50784bfa094_,-1,IInspectable *,IInspectable *>(
            v38,
            &v67);
  else
    v39 = 0;
  v20 = v37(v36, v39, (char *)this + 720);
  if ( v39 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
  if ( v20 < 0 )
  {
    v66 = 5306;
    goto LABEL_87;
  }
  v40 = *v5;
  v41 = *(__int64 (__fastcall **)(__int64, __int64, char *))(*(_QWORD *)*v5 + 560LL);
  v67 = (char *)this - 296;
  v68 = Windows::UI::Core::WindowServer::OnVisibilityChanged;
  v69 = 0;
  v70 = (unsigned __int64)Windows::UI::Core::WindowServer::OnVisibilityChanged >> 32;
  v42 = operator new(0x28u, (const struct std::nothrow_t *)std::nothrow);
  if ( v42 )
    v43 = Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::IEventHandler_impl<IInspectable *>::*)(IInspectable *,IInspectable *)>::DelegateInvokeHelper<Windows::Foundation::IEventHandler<IInspectable *>,_lambda_634b894932902ed343c0f50784bfa094_,-1,IInspectable *,IInspectable *>::DelegateInvokeHelper<Windows::Foundation::IEventHandler<IInspectable *>,_lambda_634b894932902ed343c0f50784bfa094_,-1,IInspectable *,IInspectable *>(
            v42,
            &v67);
  else
    v43 = 0;
  v33 = v41(v40, v43, (char *)this + 728);
  if ( v43 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
  if ( v33 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x14BD,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\windowserver.cpp",
      (const char *)(unsigned int)v33,
      (int)v67);
    v65 = v72;
    if ( v72 )
    {
      v72 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v65 + 16LL))(v65);
    }
    return (unsigned int)v33;
  }
  v44 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v5 + 312LL))(*v5, 1024);
  v7 = v44;
  if ( v44 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x14BF,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\windowserver.cpp",
      (const char *)(unsigned int)v44,
      (int)v67);
    v57 = v72;
    if ( v72 )
    {
      v72 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v57 + 16LL))(v57);
    }
    return v7;
  }
  v73 = 0;
  v45 = *v5;
  v46 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)*v5 + 32LL);
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v73);
  v47 = v46(v45, &v73);
  v7 = v47;
  if ( v47 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x14C2,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\windowserver.cpp",
      (const char *)(unsigned int)v47,
      (int)v67);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v73);
    goto LABEL_96;
  }
  v48 = v73;
  if ( v73 )
  {
    v58 = *(__int64 (__fastcall **)(__int64, __int64, char *))(*(_QWORD *)v73 + 248LL);
    v67 = (char *)this - 296;
    v68 = (int (*)(Windows::UI::Core::WindowServer *__hidden, struct IInspectable *, struct IInspectable *))Windows::UI::Core::WindowServer::OnApplicationViewStateChanged;
    v69 = 0;
    v70 = (unsigned __int64)Windows::UI::Core::WindowServer::OnApplicationViewStateChanged >> 32;
    v59 = operator new(0x28u, (const struct std::nothrow_t *)std::nothrow);
    if ( v59 )
      v60 = Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::ITypedEventHandler_impl<IInspectable *,IInspectable *>::*)(IInspectable *,IInspectable *)>::DelegateInvokeHelper<Windows::Foundation::ITypedEventHandler<IInspectable *,IInspectable *>,_lambda_31d71d10df95786210cc3031184be59b_,-1,IInspectable *,IInspectable *>::DelegateInvokeHelper<Windows::Foundation::ITypedEventHandler<IInspectable *,IInspectable *>,_lambda_31d71d10df95786210cc3031184be59b_,-1,IInspectable *,IInspectable *>(
              v59,
              &v67);
    else
      v60 = 0;
    v33 = v58(v48, v60, (char *)this + 664);
    if ( v60 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 16LL))(v60);
    if ( v33 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x14C7,
        (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\windowserver.cpp",
        (const char *)(unsigned int)v33,
        (int)v67);
      v61 = v73;
      if ( v73 )
      {
        v73 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v61 + 16LL))(v61);
      }
      v62 = v72;
      if ( v72 )
      {
        v72 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v62 + 16LL))(v62);
      }
      return (unsigned int)v33;
    }
  }
  v49 = Windows::UI::Core::WindowServer::WindowClientInitialize((Windows::UI::Core::WindowServer *)((char *)this - 296));
  v7 = v49;
  if ( v49 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x14CA,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\windowserver.cpp",
      (const char *)(unsigned int)v49,
      (int)v67);
    v50 = v73;
    if ( v73 )
    {
      v73 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
    }
    v51 = v72;
    if ( v72 )
    {
      v72 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
    }
    return v7;
  }
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v73);
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v72);
  return 0;
}

```

## disassembly

```asm
0x180011540  mov     [rsp-38h+arg_18], rbx
0x180011545  push    rbp
0x180011546  push    rsi
0x180011547  push    rdi
0x180011548  push    r12
0x18001154a  push    r13
0x18001154c  push    r14
0x18001154e  push    r15
0x180011550  mov     rbp, rsp
0x180011553  sub     rsp, 40h
0x180011557  mov     rdi, rdx
0x18001155a  mov     r15, rcx
0x18001155d  mov     rax, [rdx]
0x180011560  mov     rbx, [rax]
0x180011563  lea     r14, [rcx+0AD0h]
0x18001156a  mov     rcx, r14
0x18001156d  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180011572  mov     r8, r14
0x180011575  lea     rdx, _GUID_6d015416_85e6_48c2_8b21_66b2be166aeb
0x18001157c  mov     rcx, rdi
0x18001157f  mov     rax, rbx
0x180011582  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011587  mov     ebx, eax
0x180011589  xor     r13d, r13d
0x18001158c  test    eax, eax
0x18001158e  js      loc_180011B18
0x180011594  mov     [rbp+arg_0], r13
0x180011598  lea     rsi, [r15-128h]
0x18001159f  mov     rdi, [rsi+0BF8h]
0x1800115a6  mov     rax, [rdi]
0x1800115a9  mov     rbx, [rax+38h]
0x1800115ad  lea     rcx, [rbp+arg_0]
0x1800115b1  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x1800115b6  lea     rdx, [rbp+arg_0]
0x1800115ba  mov     rcx, rdi
0x1800115bd  mov     rax, rbx
0x1800115c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800115c5  mov     ebx, eax
0x1800115c7  test    eax, eax
0x1800115c9  js      loc_180011C9A
0x1800115cf  cmp     [rbp+arg_0], r13
0x1800115d3  jz      loc_18001165C
0x1800115d9  call    cs:__imp_IsOneCoreTransformMode
0x1800115df  test    eax, eax
0x1800115e1  jnz     loc_180011A33
0x1800115e7  mov     [rbp+arg_10], r13
0x1800115eb  mov     rdi, [r15+0BD8h]
0x1800115f2  mov     rax, [rdi]
0x1800115f5  mov     rbx, [rax]
0x1800115f8  lea     rcx, [rbp+arg_10]
0x1800115fc  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180011601  lea     r8, [rbp+arg_10]
0x180011605  lea     rdx, _GUID_482462bd_3f10_48f1_a406_7bf22c9a3732
0x18001160c  mov     rcx, rdi
0x18001160f  mov     rax, rbx
0x180011612  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011617  nop
0x180011618  mov     rcx, [rbp+38h]; this
0x18001161c  test    eax, eax
0x18001161e  js      loc_180011BFB
0x180011624  mov     rcx, [rbp+arg_10]
0x180011628  mov     rax, [rcx]
0x18001162b  mov     rdx, [rbp+arg_0]
0x18001162f  mov     rax, [rax+30h]
0x180011633  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011638  mov     ebx, eax
0x18001163a  test    eax, eax
0x18001163c  js      loc_180011C10
0x180011642  mov     rcx, [rbp+arg_10]
0x180011646  test    rcx, rcx
0x180011649  jz      short loc_18001165C
0x18001164b  mov     [rbp+arg_10], r13
0x18001164f  mov     rax, [rcx]
0x180011652  mov     rax, [rax+10h]
0x180011656  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001165b  nop
0x18001165c  mov     rdi, [r14]
0x18001165f  mov     rax, [rdi]
0x180011662  mov     r12, [rax+1A0h]
0x180011669  mov     [rbp+var_20], rsi
0x18001166d  lea     rax, ?OnWindowClientAdapterConsolidated@WindowServer@Core@UI@Windows@@AEAAJPEAUIInspectable@@0@Z; Windows::UI::Core::WindowServer::OnWindowClientAdapterConsolidated(IInspectable *,IInspectable *)
0x180011674  mov     [rbp+var_18], rax
0x180011678  mov     [rbp+var_10], r13d
0x18001167c  mov     eax, dword ptr [rbp+var_18+4]
0x18001167f  mov     [rbp+var_C], eax
0x180011682  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180011689  mov     ecx, 28h ; '('; unsigned __int64
0x18001168e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180011693  test    rax, rax
0x180011696  jnz     loc_180011CCB
0x18001169c  mov     rbx, r13
0x18001169f  lea     r8, [r15+2A8h]
0x1800116a6  mov     rdx, rbx
0x1800116a9  mov     rcx, rdi
0x1800116ac  mov     rax, r12
0x1800116af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800116b4  mov     edi, eax
0x1800116b6  test    rbx, rbx
0x1800116b9  jz      short loc_1800116CB
0x1800116bb  mov     rcx, [rbx]
0x1800116be  mov     rax, [rcx+10h]
0x1800116c2  mov     rcx, rbx
0x1800116c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800116ca  nop
0x1800116cb  test    edi, edi
0x1800116cd  js      loc_180011CDF
0x1800116d3  mov     rdi, [r14]
0x1800116d6  mov     rax, [rdi]
0x1800116d9  mov     r12, [rax+190h]
0x1800116e0  mov     [rbp+var_20], rsi
0x1800116e4  lea     rax, ?OnWindowClientAdapterClosed@WindowServer@Core@UI@Windows@@AEAAJPEAUIInspectable@@0@Z; Windows::UI::Core::WindowServer::OnWindowClientAdapterClosed(IInspectable *,IInspectable *)
0x1800116eb  mov     [rbp+var_18], rax
0x1800116ef  mov     [rbp+var_10], r13d
0x1800116f3  mov     eax, dword ptr [rbp+var_18+4]
0x1800116f6  mov     [rbp+var_C], eax
0x1800116f9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180011700  mov     ecx, 28h ; '('; unsigned __int64
0x180011705  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001170a  test    rax, rax
0x18001170d  jnz     loc_180011D05
0x180011713  mov     rbx, r13
0x180011716  lea     r8, [r15+2A0h]
0x18001171d  mov     rdx, rbx
0x180011720  mov     rcx, rdi
0x180011723  mov     rax, r12
0x180011726  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001172b  mov     edi, eax
0x18001172d  test    rbx, rbx
0x180011730  jz      short loc_180011742
0x180011732  mov     rcx, [rbx]
0x180011735  mov     rax, [rcx+10h]
0x180011739  mov     rcx, rbx
0x18001173c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011741  nop
0x180011742  test    edi, edi
0x180011744  js      loc_180011D19
0x18001174a  mov     rdi, [r14]
0x18001174d  mov     rax, [rdi]
0x180011750  mov     r12, [rax+1F0h]
0x180011757  mov     [rbp+var_20], rsi
0x18001175b  lea     rax, ?OnLogicalSizeChanged@WindowServer@Core@UI@Windows@@AEAAJPEAUIInspectable@@0@Z; Windows::UI::Core::WindowServer::OnLogicalSizeChanged(IInspectable *,IInspectable *)
0x180011762  mov     [rbp+var_18], rax
0x180011766  mov     [rbp+var_10], r13d
0x18001176a  mov     eax, dword ptr [rbp+var_18+4]
0x18001176d  mov     [rbp+var_C], eax
0x180011770  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180011777  mov     ecx, 28h ; '('; unsigned __int64
0x18001177c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180011781  test    rax, rax
0x180011784  jnz     loc_180011D20
0x18001178a  mov     rbx, r13
0x18001178d  lea     r8, [r15+2B0h]
0x180011794  mov     rdx, rbx
0x180011797  mov     rcx, rdi
0x18001179a  mov     rax, r12
0x18001179d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800117a2  mov     edi, eax
0x1800117a4  test    rbx, rbx
0x1800117a7  jz      short loc_1800117B9
0x1800117a9  mov     rcx, [rbx]
0x1800117ac  mov     rax, [rcx+10h]
0x1800117b0  mov     rcx, rbx
0x1800117b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800117b8  nop
0x1800117b9  test    edi, edi
0x1800117bb  js      loc_180011D34
0x1800117c1  mov     rdi, [r14]
0x1800117c4  mov     rax, [rdi]
0x1800117c7  mov     r12, [rax+210h]
0x1800117ce  mov     [rbp+var_20], rsi
0x1800117d2  lea     rax, ?OnPhysicalBoundsChanged@WindowServer@Core@UI@Windows@@AEAAJPEAUIInspectable@@0@Z; Windows::UI::Core::WindowServer::OnPhysicalBoundsChanged(IInspectable *,IInspectable *)
0x1800117d9  mov     [rbp+var_18], rax
0x1800117dd  mov     [rbp+var_10], r13d
0x1800117e1  mov     eax, dword ptr [rbp+var_18+4]
0x1800117e4  mov     [rbp+var_C], eax
0x1800117e7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800117ee  mov     ecx, 28h ; '('; unsigned __int64
0x1800117f3  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800117f8  test    rax, rax
0x1800117fb  jnz     loc_180011D3B
0x180011801  mov     rbx, r13
0x180011804  lea     r8, [r15+2C0h]
0x18001180b  mov     rdx, rbx
0x18001180e  mov     rcx, rdi
0x180011811  mov     rax, r12
0x180011814  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011819  mov     edi, eax
0x18001181b  test    rbx, rbx
0x18001181e  jz      short loc_180011830
0x180011820  mov     rcx, [rbx]
0x180011823  mov     rax, [rcx+10h]
0x180011827  mov     rcx, rbx
0x18001182a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001182f  nop
0x180011830  test    edi, edi
0x180011832  jns     short loc_180011881
0x180011834  mov     rcx, [rbp+38h]; this
0x180011838  mov     r9d, edi; char *
0x18001183b  lea     r8, aOnecoreuapWind_28; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x180011842  mov     edx, 14B7h; void *
0x180011847  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001184c  nop
0x18001184d  mov     rcx, [rbp+arg_0]
0x180011851  test    rcx, rcx
0x180011854  jz      short loc_180011867
0x180011856  mov     [rbp+arg_0], r13
0x18001185a  mov     rax, [rcx]
0x18001185d  mov     rax, [rax+10h]
0x180011861  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011866  nop
0x180011867  mov     eax, edi
0x180011869  mov     rbx, [rsp+40h+arg_18]
0x180011871  add     rsp, 40h
0x180011875  pop     r15
0x180011877  pop     r14
0x180011879  pop     r13
0x18001187b  pop     r12
0x18001187d  pop     rdi
0x18001187e  pop     rsi
0x18001187f  pop     rbp
0x180011880  retn
0x180011881  mov     rdi, [r14]
0x180011884  mov     rax, [rdi]
0x180011887  mov     r12, [rax+220h]
0x18001188e  mov     [rbp+var_20], rsi
0x180011892  lea     rax, ?OnVisibleBoundsChanged@WindowServer@Core@UI@Windows@@AEAAJPEAUIInspectable@@0@Z; Windows::UI::Core::WindowServer::OnVisibleBoundsChanged(IInspectable *,IInspectable *)
0x180011899  mov     [rbp+var_18], rax
0x18001189d  mov     [rbp+var_10], r13d
0x1800118a1  mov     eax, dword ptr [rbp+var_18+4]
0x1800118a4  mov     [rbp+var_C], eax
0x1800118a7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800118ae  mov     ecx, 28h ; '('; unsigned __int64
0x1800118b3  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800118b8  test    rax, rax
0x1800118bb  jnz     loc_180011D4F
0x1800118c1  mov     rbx, r13
0x1800118c4  lea     r8, [r15+2D0h]
0x1800118cb  mov     rdx, rbx
0x1800118ce  mov     rcx, rdi
0x1800118d1  mov     rax, r12
0x1800118d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800118d9  mov     edi, eax
0x1800118db  test    rbx, rbx
0x1800118de  jz      short loc_1800118F0
0x1800118e0  mov     rcx, [rbx]
0x1800118e3  mov     rax, [rcx+10h]
0x1800118e7  mov     rcx, rbx
0x1800118ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800118ef  nop
0x1800118f0  test    edi, edi
0x1800118f2  js      loc_180011CE6
0x1800118f8  mov     rdi, [r14]
0x1800118fb  mov     rax, [rdi]
0x1800118fe  mov     r12, [rax+230h]
0x180011905  mov     [rbp+var_20], rsi
0x180011909  lea     rax, ?OnVisibilityChanged@WindowServer@Core@UI@Windows@@AEAAJPEAUIInspectable@@0@Z; Windows::UI::Core::WindowServer::OnVisibilityChanged(IInspectable *,IInspectable *)
0x180011910  mov     [rbp+var_18], rax
0x180011914  mov     [rbp+var_10], r13d
0x180011918  mov     eax, dword ptr [rbp+var_18+4]
0x18001191b  mov     [rbp+var_C], eax
0x18001191e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180011925  mov     ecx, 28h ; '('; unsigned __int64
0x18001192a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001192f  test    rax, rax
0x180011932  jnz     loc_180011D63
0x180011938  mov     rbx, r13
0x18001193b  lea     r8, [r15+2D8h]
0x180011942  mov     rdx, rbx
0x180011945  mov     rcx, rdi
0x180011948  mov     rax, r12
0x18001194b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011950  mov     edi, eax
0x180011952  test    rbx, rbx
0x180011955  jz      short loc_180011967
0x180011957  mov     rcx, [rbx]
0x18001195a  mov     rax, [rcx+10h]
0x18001195e  mov     rcx, rbx
0x180011961  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011966  nop
0x180011967  test    edi, edi
0x180011969  js      loc_180011C62
0x18001196f  mov     rcx, [r14]
0x180011972  mov     rax, [rcx]
0x180011975  mov     edx, 400h
0x18001197a  mov     rax, [rax+138h]
0x180011981  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011986  mov     ebx, eax
0x180011988  test    eax, eax
0x18001198a  js      loc_180011AE0
0x180011990  mov     [rbp+arg_8], r13
0x180011994  mov     rdi, [r14]
0x180011997  mov     rax, [rdi]
0x18001199a  mov     rbx, [rax+20h]
0x18001199e  lea     rcx, [rbp+arg_8]
0x1800119a2  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x1800119a7  lea     rdx, [rbp+arg_8]
0x1800119ab  mov     rcx, rdi
0x1800119ae  mov     rax, rbx
0x1800119b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800119b6  mov     ebx, eax
  ... truncated ...
```
