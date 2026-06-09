# Windows::UI::Input::KeyboardDeliveryInterceptorStaticsImpl::GetForCurrentView(Windows::UI::Input::IKeyboardDeliveryInterceptor * *)

- ea: `0x1800bf630`
- end: `0x1800bf84f`
- name: `?GetForCurrentView@KeyboardDeliveryInterceptorStaticsImpl@Input@UI@Windows@@EEAAJPEAPEAUIKeyboardDeliveryInterceptor@234@@Z`
- size: `543`
- prototype: `__int64 __fastcall(Windows::UI::Input::KeyboardDeliveryInterceptorStaticsImpl *__hidden this, struct Windows::UI::Input::IKeyboardDeliveryInterceptor **)`
- caller_count: `0`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800038e0`
- `0x180004dd4`
- `0x180014754`
- `0x18002eaa0`
- `0x18004315c`
- `0x18006d484`
- `0x1800bf370`
- `0x1800bf630`
- `0x1800c73c0`
- `0x1800ca010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800bf70d`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800bf70d`
- `twinapi.appcore!__imp_CoreRegisterWindowService` at `0x1800bf7ea`
- `twinapi.appcore!__imp_CoreRegisterWindowService` at `0x1800bf7ea`
- `twinapi.appcore!__imp_CoreQueryWindowService` at `0x1800bf79f`
- `twinapi.appcore!__imp_CoreQueryWindowService` at `0x1800bf79f`

## string_xrefs

- `0x1800bf6ee`: `This API must be called from a UI thread.`

## pseudocode

```c
__int64 __fastcall Windows::UI::Input::KeyboardDeliveryInterceptorStaticsImpl::GetForCurrentView(
        Windows::UI::Input::KeyboardDeliveryInterceptorStaticsImpl *this,
        struct Windows::UI::Input::IKeyboardDeliveryInterceptor **a2)
{
  int v3; // eax
  unsigned int v4; // ebx
  __int64 v5; // rdi
  void (__fastcall *v6)(__int64, __int64 *); // rbx
  int v7; // eax
  __int64 v8; // rdx
  int v9; // eax
  __int64 v10; // rdx
  __int64 v12; // [rsp+20h] [rbp-58h] BYREF
  __int64 (__fastcall ***v13)(_QWORD, GUID *, struct Windows::UI::Input::IKeyboardDeliveryInterceptor **); // [rsp+28h] [rbp-50h] BYREF
  __int64 v14; // [rsp+30h] [rbp-48h] BYREF
  __int64 v15; // [rsp+38h] [rbp-40h] BYREF
  __int64 v16; // [rsp+40h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-30h] BYREF
  __int64 v18; // [rsp+60h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+20h]

  *a2 = 0;
  v16 = 0;
  v18 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.UI.Core.CoreWindow",
    0x1Bu,
    0x1Au);
  v3 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::UI::Core::ICoreWindowStatic>>(
         v18,
         &v16);
  v4 = v3;
  if ( v3 >= 0 )
  {
    v5 = v16;
    v12 = 0;
    v6 = *(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v16 + 48LL);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v12);
    v6(v5, &v12);
    if ( !v12 )
    {
      v18 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &hstringHeader,
        L"This API must be called from a UI thread.",
        0x2Au,
        0x29u);
      v4 = -2147023488;
      RoOriginateError(2147943808LL, v18);
LABEL_19:
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v12);
      goto LABEL_20;
    }
    v15 = 0;
    v14 = 0;
    v7 = Microsoft::WRL::ComPtr<Windows::UI::Core::ICoreWindow>::As<ICoreWindowInterop>(&v12, &v14);
    v4 = v7;
    if ( v7 < 0 )
    {
      v8 = 191;
LABEL_7:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v8,
        (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\inputdeliveryintercepter\\kbddeliveryintercepter.cpp",
        (const char *)(unsigned int)v7,
        v12);
LABEL_18:
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v14);
      goto LABEL_19;
    }
    v7 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v14 + 24LL))(v14, &v15);
    v4 = v7;
    if ( v7 < 0 )
    {
      v8 = 192;
      goto LABEL_7;
    }
    v13 = 0;
    Microsoft::WRL::ComPtr<CInteractiveObjectDevice>::InternalRelease(&v13);
    if ( (int)CoreQueryWindowService(
                v15,
                &GUID_b4baf068_8f49_446c_8db5_8c0ffe85cc9e,
                &GUID_b4baf068_8f49_446c_8db5_8c0ffe85cc9e,
                &v13) < 0 )
    {
      Microsoft::WRL::ComPtr<CInteractiveObjectDevice>::InternalRelease(&v13);
      v9 = Microsoft::WRL::Details::MakeAndInitialize<Windows::UI::Input::KeyboardDeliveryInterceptorImpl,Windows::UI::Input::IKeyboardDeliveryInterceptor,HWND__ * &>(
             &v13,
             &v15);
      v4 = v9;
      if ( v9 < 0 )
      {
        v10 = 202;
LABEL_13:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v10,
          (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\inputdeliveryintercepter\\kbddeliveryintercepter.cpp",
          (const char *)(unsigned int)v9,
          v12);
LABEL_17:
        Microsoft::WRL::ComPtr<CInteractiveObjectDevice>::InternalRelease(&v13);
        goto LABEL_18;
      }
      v9 = CoreRegisterWindowService(v15, &GUID_b4baf068_8f49_446c_8db5_8c0ffe85cc9e, v13);
      v4 = v9;
      if ( v9 < 0 )
      {
        v10 = 205;
        goto LABEL_13;
      }
    }
    v4 = (**v13)(v13, &GUID_b4baf068_8f49_446c_8db5_8c0ffe85cc9e, a2);
    goto LABEL_17;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xAF,
    (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\inputdeliveryintercepter\\kbddeliveryintercepter.cpp",
    (const char *)(unsigned int)v3,
    v12);
LABEL_20:
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v16);
  return v4;
}

```

## disassembly

```asm
0x1800bf630  push    rbp
0x1800bf632  push    rbx
0x1800bf633  push    rsi
0x1800bf634  push    rdi
0x1800bf635  mov     rbp, rsp
0x1800bf638  sub     rsp, 78h
0x1800bf63c  mov     rax, cs:__security_cookie
0x1800bf643  xor     rax, rsp
0x1800bf646  mov     [rbp+var_10], rax
0x1800bf64a  mov     r9d, 1Ah; unsigned int
0x1800bf650  mov     qword ptr [rdx], 0
0x1800bf657  mov     rsi, rdx
0x1800bf65a  mov     [rbp+var_38], 0
0x1800bf662  lea     rdx, ?RuntimeClass_Windows_UI_Core_CoreWindow@@3QBGB; "Windows.UI.Core.CoreWindow"
0x1800bf669  mov     [rbp+var_18], 0
0x1800bf671  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x1800bf675  lea     r8d, [r9+1]; unsigned int
0x1800bf679  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800bf67e  mov     rcx, [rbp+var_18]
0x1800bf682  lea     rdx, [rbp+var_38]
0x1800bf686  call    ??$GetActivationFactory@V?$ComPtr@UICoreWindowStatic@Core@UI@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UICoreWindowStatic@Core@UI@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::UI::Core::ICoreWindowStatic>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::UI::Core::ICoreWindowStatic>>)
0x1800bf68b  mov     ebx, eax
0x1800bf68d  test    eax, eax
0x1800bf68f  jns     short loc_1800BF6AE
0x1800bf691  mov     rcx, [rbp+20h]; this
0x1800bf695  lea     r8, aOnecoreuapWind_22; "onecoreuap\\windows\\advcore\\winrt\\in"...
0x1800bf69c  mov     r9d, eax; char *
0x1800bf69f  mov     edx, 0AFh; void *
0x1800bf6a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bf6a9  jmp     loc_1800BF82F
0x1800bf6ae  mov     rdi, [rbp+var_38]
0x1800bf6b2  lea     rcx, [rbp+var_58]
0x1800bf6b6  mov     [rbp+var_58], 0
0x1800bf6be  mov     rax, [rdi]
0x1800bf6c1  mov     rbx, [rax+30h]
0x1800bf6c5  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x1800bf6ca  lea     rdx, [rbp+var_58]
0x1800bf6ce  mov     rcx, rdi
0x1800bf6d1  mov     rax, rbx
0x1800bf6d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bf6d9  cmp     [rbp+var_58], 0
0x1800bf6de  jnz     short loc_1800BF718
0x1800bf6e0  mov     r9d, 29h ; ')'; unsigned int
0x1800bf6e6  mov     [rbp+var_18], 0
0x1800bf6ee  lea     rdx, aThisApiMustBeC; "This API must be called from a UI threa"...
0x1800bf6f5  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x1800bf6f9  lea     r8d, [r9+1]; unsigned int
0x1800bf6fd  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800bf702  mov     rdx, [rbp+var_18]
0x1800bf706  mov     ebx, 80070580h
0x1800bf70b  mov     ecx, ebx
0x1800bf70d  call    cs:__imp_RoOriginateError
0x1800bf713  jmp     loc_1800BF826
0x1800bf718  lea     rdx, [rbp+var_48]
0x1800bf71c  mov     [rbp+var_40], 0
0x1800bf724  lea     rcx, [rbp+var_58]
0x1800bf728  mov     [rbp+var_48], 0
0x1800bf730  call    ??$As@UICoreWindowInterop@@@?$ComPtr@UICoreWindow@Core@UI@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UICoreWindowInterop@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::UI::Core::ICoreWindow>::As<ICoreWindowInterop>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<ICoreWindowInterop>>)
0x1800bf735  mov     ebx, eax
0x1800bf737  test    eax, eax
0x1800bf739  jns     short loc_1800BF758
0x1800bf73b  mov     edx, 0BFh; void *
0x1800bf740  mov     rcx, [rbp+20h]; this
0x1800bf744  lea     r8, aOnecoreuapWind_22; "onecoreuap\\windows\\advcore\\winrt\\in"...
0x1800bf74b  mov     r9d, eax; char *
0x1800bf74e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bf753  jmp     loc_1800BF81D
0x1800bf758  mov     rcx, [rbp+var_48]
0x1800bf75c  lea     rdx, [rbp+var_40]
0x1800bf760  mov     rax, [rcx]
0x1800bf763  mov     rax, [rax+18h]
0x1800bf767  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bf76c  mov     ebx, eax
0x1800bf76e  test    eax, eax
0x1800bf770  jns     short loc_1800BF779
0x1800bf772  mov     edx, 0C0h
0x1800bf777  jmp     short loc_1800BF740
0x1800bf779  lea     rcx, [rbp+var_50]
0x1800bf77d  mov     [rbp+var_50], 0
0x1800bf785  call    ?InternalRelease@?$ComPtr@VCInteractiveObjectDevice@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CInteractiveObjectDevice>::InternalRelease(void)
0x1800bf78a  mov     rcx, [rbp+var_40]
0x1800bf78e  lea     rdi, _GUID_b4baf068_8f49_446c_8db5_8c0ffe85cc9e
0x1800bf795  mov     r8, rdi
0x1800bf798  lea     r9, [rbp+var_50]
0x1800bf79c  mov     rdx, rdi
0x1800bf79f  call    cs:__imp_CoreQueryWindowService
0x1800bf7a5  test    eax, eax
0x1800bf7a7  jns     short loc_1800BF7FD
0x1800bf7a9  lea     rcx, [rbp+var_50]
0x1800bf7ad  call    ?InternalRelease@?$ComPtr@VCInteractiveObjectDevice@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CInteractiveObjectDevice>::InternalRelease(void)
0x1800bf7b2  lea     rdx, [rbp+var_40]
0x1800bf7b6  lea     rcx, [rbp+var_50]
0x1800bf7ba  call    ??$MakeAndInitialize@VKeyboardDeliveryInterceptorImpl@Input@UI@Windows@@UIKeyboardDeliveryInterceptor@234@AEAPEAUHWND__@@@Details@WRL@Microsoft@@YAJPEAPEAUIKeyboardDeliveryInterceptor@Input@UI@Windows@@AEAPEAUHWND__@@@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::UI::Input::KeyboardDeliveryInterceptorImpl,Windows::UI::Input::IKeyboardDeliveryInterceptor,HWND__ * &>(Windows::UI::Input::IKeyboardDeliveryInterceptor * *,HWND__ * &)
0x1800bf7bf  mov     ebx, eax
0x1800bf7c1  test    eax, eax
0x1800bf7c3  jns     short loc_1800BF7DF
0x1800bf7c5  mov     edx, 0CAh; void *
0x1800bf7ca  mov     rcx, [rbp+20h]; this
0x1800bf7ce  lea     r8, aOnecoreuapWind_22; "onecoreuap\\windows\\advcore\\winrt\\in"...
0x1800bf7d5  mov     r9d, eax; char *
0x1800bf7d8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bf7dd  jmp     short loc_1800BF814
0x1800bf7df  mov     r8, [rbp+var_50]
0x1800bf7e3  mov     rdx, rdi
0x1800bf7e6  mov     rcx, [rbp+var_40]
0x1800bf7ea  call    cs:__imp_CoreRegisterWindowService
0x1800bf7f0  mov     ebx, eax
0x1800bf7f2  test    eax, eax
0x1800bf7f4  jns     short loc_1800BF7FD
0x1800bf7f6  mov     edx, 0CDh
0x1800bf7fb  jmp     short loc_1800BF7CA
0x1800bf7fd  mov     rcx, [rbp+var_50]
0x1800bf801  mov     r8, rsi
0x1800bf804  mov     rdx, rdi
0x1800bf807  mov     rax, [rcx]
0x1800bf80a  mov     rax, [rax]
0x1800bf80d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bf812  mov     ebx, eax
0x1800bf814  lea     rcx, [rbp+var_50]
0x1800bf818  call    ?InternalRelease@?$ComPtr@VCInteractiveObjectDevice@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CInteractiveObjectDevice>::InternalRelease(void)
0x1800bf81d  lea     rcx, [rbp+var_48]
0x1800bf821  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x1800bf826  lea     rcx, [rbp+var_58]
0x1800bf82a  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x1800bf82f  lea     rcx, [rbp+var_38]
0x1800bf833  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x1800bf838  mov     eax, ebx
0x1800bf83a  mov     rcx, [rbp+var_10]
0x1800bf83e  xor     rcx, rsp; StackCookie
0x1800bf841  call    __security_check_cookie
0x1800bf846  add     rsp, 78h
0x1800bf84a  pop     rdi
0x1800bf84b  pop     rsi
0x1800bf84c  pop     rbx
0x1800bf84d  pop     rbp
0x1800bf84e  retn
```
