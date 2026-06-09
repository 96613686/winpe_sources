# WindowsInternal::UI::CreateHostBackdropBrush(IDCompositionDesktopDevicePartner *,Windows::UI::Composition::ICompositionBrush * *)

- ea: `0x180006aa8`
- end: `0x1800070df`
- name: `?CreateHostBackdropBrush@UI@WindowsInternal@@YAJPEAUIDCompositionDesktopDevicePartner@@PEAPEAUICompositionBrush@Composition@1Windows@@@Z`
- size: `1591`
- prototype: `__int64 __fastcall(WindowsInternal::UI *__hidden this, struct IDCompositionDesktopDevicePartner *, struct Windows::UI::Composition::ICompositionBrush **)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180060080`

## callees

- `0x1800028f4`
- `0x1800029dc`
- `0x180006aa8`
- `0x1800070e8`
- `0x180007114`
- `0x180007140`
- `0x180081a68`
- `0x180095130`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180006b0b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180006b7f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180006ec6`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180006b0b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180006b7f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180006ec6`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180006b2d`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180006b2d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180006af5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180006b65`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180006eac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180006af5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180006b65`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180006eac`

## string_xrefs

- `0x180006aee`: `Windows.UI.Composition.CompositionEffectSourceParameter`

## pseudocode

```c
__int64 __fastcall WindowsInternal::UI::CreateHostBackdropBrush(
        __int64 (__fastcall ***this)(WindowsInternal::UI *, GUID *, __int64 *),
        struct IDCompositionDesktopDevicePartner *a2,
        struct Windows::UI::Composition::ICompositionBrush **a3)
{
  HRESULT v5; // eax
  HSTRING v6; // rbx
  int ActivationFactory; // eax
  int v8; // ebx
  _QWORD *v9; // rbx
  __int64 v10; // rdi
  HRESULT v11; // eax
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 (__fastcall ***v15)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v16; // rcx
  __int64 (__fastcall ***v17)(_QWORD, _QWORD, _QWORD); // rcx
  _QWORD *v18; // rcx
  int v20; // eax
  __int64 (__fastcall ***v21)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v22)(_QWORD, GUID *, __int64 *); // rdi
  int v23; // eax
  __int64 (__fastcall **v24)(WindowsInternal::UI *, GUID *, __int64 *); // rax
  __int64 (__fastcall *v25)(WindowsInternal::UI *, GUID *, __int64 *); // rbx
  int v26; // eax
  __int64 v27; // rdi
  __int64 (__fastcall *v28)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)); // rbx
  int v29; // eax
  __int64 (__fastcall ***v30)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v31)(_QWORD, GUID *, __int64 *); // rdi
  int v32; // eax
  int v33; // eax
  __int64 v34; // rdi
  __int64 v35; // rbx
  __int64 v36; // rcx
  __int64 (__fastcall **v37)(WindowsInternal::UI *, GUID *, __int64 *); // rax
  __int64 (__fastcall *v38)(WindowsInternal::UI *, GUID *, __int64 *); // rbx
  int v39; // eax
  __int64 v40; // rdi
  __int64 (__fastcall *v41)(__int64, __int64, __int64 *); // rbx
  __int64 v42; // rdi
  __int64 (__fastcall *v43)(__int64, _QWORD **); // rbx
  _QWORD *v44; // rbx
  __int64 v45; // rsi
  __int64 v46; // rdi
  HRESULT v47; // eax
  __int64 v48; // rdx
  __int64 v49; // rax
  __int64 (__fastcall **v50)(__int64, GUID *, __int64); // r9
  __int64 v51; // r10
  __int64 v52; // rcx
  __int64 v53; // rcx
  __int64 (__fastcall ***v54)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v55; // rcx
  __int64 (__fastcall ***v56)(_QWORD, _QWORD, _QWORD); // rcx
  _QWORD *v57; // rcx
  _QWORD *v58; // [rsp+20h] [rbp-49h] BYREF
  __int64 (__fastcall ***v59)(_QWORD, GUID *, __int64 *); // [rsp+28h] [rbp-41h] BYREF
  __int64 v60; // [rsp+30h] [rbp-39h] BYREF
  __int64 (__fastcall ***v61)(_QWORD, GUID *, __int64 *); // [rsp+38h] [rbp-31h] BYREF
  __int64 v62; // [rsp+40h] [rbp-29h] BYREF
  __int64 v63; // [rsp+48h] [rbp-21h] BYREF
  __int64 v64; // [rsp+50h] [rbp-19h] BYREF
  __int64 v65; // [rsp+58h] [rbp-11h] BYREF
  _QWORD *v66; // [rsp+60h] [rbp-9h] BYREF
  __int64 v67; // [rsp+68h] [rbp-1h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+70h] [rbp+7h] BYREF
  HSTRING string; // [rsp+88h] [rbp+1Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  *(_QWORD *)a2 = 0;
  v58 = 0;
  string = 0;
  v5 = WindowsCreateStringReference(
         L"Windows.UI.Composition.CompositionEffectSourceParameter",
         0x37u,
         &hstringHeader,
         &string);
  if ( v5 < 0 )
  {
    RaiseException(v5, 1u, 0, 0);
    __debugbreak();
  }
  v6 = string;
  Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositionEffectSourceParameterFactory>::InternalRelease(&v58);
  ActivationFactory = RoGetActivationFactory(v6, &GUID_b3d9f276_aba3_4724_acf3_d0397464db1c, &v58);
  v8 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x16,
      (unsigned int)"onecoreuap\\restricted\\shell\\inc\\windowacrylicbackdrop.h",
      (const char *)(unsigned int)ActivationFactory,
      (int)v58);
  }
  else
  {
    v9 = v58;
    v59 = 0;
    v10 = *v58;
    Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositionEffectSourceParameterFactory>::InternalRelease(&v59);
    string = 0;
    v11 = WindowsCreateStringReference(L"source", 6u, &hstringHeader, &string);
    if ( v11 < 0 )
    {
      RaiseException(v11, 1u, 0, 0);
      __debugbreak();
    }
    v20 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING, _QWORD))(v10 + 48))(v9, string, &v59);
    v8 = v20;
    if ( v20 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x19,
        (unsigned int)"onecoreuap\\restricted\\shell\\inc\\windowacrylicbackdrop.h",
        (const char *)(unsigned int)v20,
        (int)v58);
    }
    else
    {
      v21 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v59;
      v60 = 0;
      v22 = **v59;
      Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositionEffectSourceParameterFactory>::InternalRelease(&v60);
      v23 = v22(v21, &GUID_2d8f9ddc_4339_4eb9_9216_f9deb75658a2, &v60);
      v8 = v23;
      if ( v23 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1B,
          (unsigned int)"onecoreuap\\restricted\\shell\\inc\\windowacrylicbackdrop.h",
          (const char *)(unsigned int)v23,
          (int)v58);
      }
      else
      {
        v24 = *this;
        v65 = 0;
        v25 = *v24;
        Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v65);
        v26 = v25((WindowsInternal::UI *)this, &GUID_735081dc_5e24_45da_a38f_e32cc349a9a0, &v65);
        v8 = v26;
        if ( v26 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1D,
            (unsigned int)"onecoreuap\\restricted\\shell\\inc\\windowacrylicbackdrop.h",
            (const char *)(unsigned int)v26,
            (int)v58);
        }
        else
        {
          v27 = v65;
          v61 = 0;
          v28 = *(__int64 (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)v65 + 64LL);
          Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositionEffectSourceParameterFactory>::InternalRelease(&v61);
          v29 = v28(v27, &v61);
          v8 = v29;
          if ( v29 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x20,
              (unsigned int)"onecoreuap\\restricted\\shell\\inc\\windowacrylicbackdrop.h",
              (const char *)(unsigned int)v29,
              (int)v58);
          }
          else
          {
            v30 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v61;
            v67 = 0;
            v31 = **v61;
            Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v67);
            v32 = v31(v30, &GUID_ab0d7608_30c0_40e9_b568_b60a6bd1fb46, &v67);
            v8 = v32;
            if ( v32 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x22,
                (unsigned int)"onecoreuap\\restricted\\shell\\inc\\windowacrylicbackdrop.h",
                (const char *)(unsigned int)v32,
                (int)v58);
            }
            else
            {
              v66 = 0;
              v62 = 0;
              v33 = Microsoft::WRL::Details::MakeAndInitialize<Microsoft::Internal::UI::Composition::Effects::GaussianBlurEffect,Microsoft::Internal::UI::Composition::Effects::GaussianBlurEffect,>(&v62);
              v8 = v33;
              if ( v33 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x28,
                  (unsigned int)"onecoreuap\\restricted\\shell\\inc\\windowacrylicbackdrop.h",
                  (const char *)(unsigned int)v33,
                  (int)v58);
              }
              else
              {
                *(_DWORD *)(v62 + 76) = 1;
                *(_DWORD *)(v62 + 72) = 1106247680;
                v34 = v62;
                v35 = v60;
                if ( *(_QWORD *)(v62 + 64) != v60 )
                {
                  if ( v60 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 8LL))(v60);
                  v36 = *(_QWORD *)(v34 + 64);
                  *(_QWORD *)(v34 + 64) = v35;
                  if ( v36 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
                }
                v37 = *this;
                v63 = 0;
                v38 = *v37;
                Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositionEffectSourceParameterFactory>::InternalRelease(&v63);
                v39 = v38((WindowsInternal::UI *)this, &GUID_b403ca50_7f8c_4e83_985f_cc45060036d8, &v63);
                v8 = v39;
                if ( v39 < 0 )
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x2F,
                    (unsigned int)"onecoreuap\\restricted\\shell\\inc\\windowacrylicbackdrop.h",
                    (const char *)(unsigned int)v39,
                    (int)v58);
                }
                else
                {
                  v40 = v63;
                  v64 = 0;
                  v41 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v63 + 88LL);
                  Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositionEffectSourceParameterFactory>::InternalRelease(&v64);
                  v8 = v41(v40, v62, &v64);
                  if ( v8 < 0 )
                  {
                    v12 = 50;
                  }
                  else
                  {
                    v42 = v64;
                    v43 = *(__int64 (__fastcall **)(__int64, _QWORD **))(*(_QWORD *)v64 + 48LL);
                    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v66);
                    v8 = v43(v42, &v66);
                    if ( v8 < 0 )
                    {
                      v12 = 51;
                    }
                    else
                    {
                      v44 = v66;
                      v45 = v67;
                      v46 = *v66;
                      string = 0;
                      v47 = WindowsCreateStringReference(L"source", 6u, &hstringHeader, &string);
                      if ( v47 < 0 )
                      {
                        RaiseException(v47, 1u, 0, 0);
                        __debugbreak();
                      }
                      v8 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING, __int64))(v46 + 56))(v44, string, v45);
                      if ( v8 < 0 )
                      {
                        v12 = 53;
                      }
                      else
                      {
                        v49 = winrt::to_abi<ITransitionAnimationVisualNative,winrt::Udwm::Transitions::implementation::TopLevelWindow3DWrapper>(
                                a2,
                                v48);
                        v8 = (*v50)(v51, &GUID_ab0d7608_30c0_40e9_b568_b60a6bd1fb46, v49);
                        if ( v8 >= 0 )
                        {
                          v52 = v64;
                          if ( v64 )
                          {
                            v64 = 0;
                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
                          }
                          v53 = v63;
                          if ( v63 )
                          {
                            v63 = 0;
                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
                          }
                          if ( v62 )
                          {
                            v62 = 0;
                            Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Graphics::Effects::IGraphicsEffect,Windows::Graphics::Effects::IGraphicsEffectSource,Windows::Graphics::Effects::IGraphicsEffectD2D1Interop,Microsoft::Internal::UI::Composition::Effects::IGaussianBlurEffect>::Release();
                          }
                          Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v66);
                          Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v67);
                          v54 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v61;
                          if ( v61 )
                          {
                            v61 = 0;
                            ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v54)[2])(v54);
                          }
                          Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v65);
                          v55 = v60;
                          if ( v60 )
                          {
                            v60 = 0;
                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
                          }
                          v56 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v59;
                          if ( v59 )
                          {
                            v59 = 0;
                            ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v56)[2])(v56);
                          }
                          v57 = v58;
                          if ( v58 )
                          {
                            v58 = 0;
                            (*(void (__fastcall **)(_QWORD *))(*v57 + 16LL))(v57);
                          }
                          return 0;
                        }
                        v12 = 55;
                      }
                    }
                  }
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)v12,
                    (unsigned int)"onecoreuap\\restricted\\shell\\inc\\windowacrylicbackdrop.h",
                    (const char *)(unsigned int)v8,
                    (int)v58);
                  v13 = v64;
                  if ( v64 )
                  {
                    v64 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
                  }
                }
                v14 = v63;
                if ( v63 )
                {
                  v63 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
                }
              }
              if ( v62 )
              {
                v62 = 0;
                Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Graphics::Effects::IGraphicsEffect,Windows::Graphics::Effects::IGraphicsEffectSource,Windows::Graphics::Effects::IGraphicsEffectD2D1Interop,Microsoft::Internal::UI::Composition::Effects::IGaussianBlurEffect>::Release();
              }
              Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v66);
            }
            Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v67);
          }
          v15 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v61;
          if ( v61 )
          {
            v61 = 0;
            ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v15)[2])(v15);
          }
        }
        Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v65);
      }
      v16 = v60;
      if ( v60 )
      {
        v60 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
      }
    }
    v17 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v59;
    if ( v59 )
    {
      v59 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v17)[2])(v17);
    }
  }
  v18 = v58;
  if ( v58 )
  {
    v58 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v18 + 16LL))(v18);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180006aa8  mov     [rsp-8+arg_10], rbx
0x180006aad  push    rbp
0x180006aae  push    rsi
0x180006aaf  push    rdi
0x180006ab0  push    r14
0x180006ab2  push    r15
0x180006ab4  lea     rbp, [rsp-37h]
0x180006ab9  sub     rsp, 0A0h
0x180006ac0  mov     rax, cs:__security_cookie
0x180006ac7  xor     rax, rsp
0x180006aca  mov     [rbp+57h+var_30], rax
0x180006ace  xor     r15d, r15d
0x180006ad1  lea     r9, [rbp+57h+string]; string
0x180006ad5  mov     r14, rdx
0x180006ad8  mov     [rdx], r15
0x180006adb  mov     rsi, rcx
0x180006ade  mov     [rbp+57h+var_A0], r15
0x180006ae2  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180006ae6  mov     [rbp+57h+string], r15
0x180006aea  lea     edx, [r15+37h]; length
0x180006aee  lea     rcx, ?RuntimeClass_Windows_UI_Composition_CompositionEffectSourceParameter@@3QBGB; "Windows.UI.Composition.CompositionEffec"...
0x180006af5  call    cs:__imp_WindowsCreateStringReference
0x180006afb  test    eax, eax
0x180006afd  jns     short loc_180006B12
0x180006aff  xor     r9d, r9d; lpArguments
0x180006b02  lea     edx, [r15+1]; dwExceptionFlags
0x180006b06  xor     r8d, r8d; nNumberOfArguments
0x180006b09  mov     ecx, eax; dwExceptionCode
0x180006b0b  call    cs:__imp_RaiseException
0x180006b11  int     3; Trap to Debugger
0x180006b12  mov     rbx, [rbp+57h+string]
0x180006b16  lea     rcx, [rbp+57h+var_A0]
0x180006b1a  call    ?InternalRelease@?$ComPtr@UICompositionEffectSourceParameterFactory@Composition@UI@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositionEffectSourceParameterFactory>::InternalRelease(void)
0x180006b1f  lea     r8, [rbp+57h+var_A0]
0x180006b23  mov     rcx, rbx
0x180006b26  lea     rdx, _GUID_b3d9f276_aba3_4724_acf3_d0397464db1c
0x180006b2d  call    cs:__imp_RoGetActivationFactory
0x180006b33  mov     ebx, eax
0x180006b35  test    eax, eax
0x180006b37  js      short loc_180006B86
0x180006b39  mov     rbx, [rbp+57h+var_A0]
0x180006b3d  lea     rcx, [rbp+57h+var_98]
0x180006b41  mov     [rbp+57h+var_98], r15
0x180006b45  mov     rdi, [rbx]
0x180006b48  call    ?InternalRelease@?$ComPtr@UICompositionEffectSourceParameterFactory@Composition@UI@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositionEffectSourceParameterFactory>::InternalRelease(void)
0x180006b4d  lea     r9, [rbp+57h+string]; string
0x180006b51  mov     [rbp+57h+string], r15
0x180006b55  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180006b59  mov     edx, 6; length
0x180006b5e  lea     rcx, sourceString; "source"
0x180006b65  call    cs:__imp_WindowsCreateStringReference
0x180006b6b  test    eax, eax
0x180006b6d  jns     loc_180006CA3
0x180006b73  xor     r9d, r9d; lpArguments
0x180006b76  xor     r8d, r8d; nNumberOfArguments
0x180006b79  mov     ecx, eax; dwExceptionCode
0x180006b7b  lea     edx, [r9+1]; dwExceptionFlags
0x180006b7f  call    cs:__imp_RaiseException
0x180006b85  int     3; Trap to Debugger
0x180006b86  mov     rcx, [rbp+5Fh]; this
0x180006b8a  lea     r8, aOnecoreuapRest_1; "onecoreuap\\restricted\\shell\\inc\\win"...
0x180006b91  mov     r9d, ebx; char *
0x180006b94  mov     edx, 16h; void *
0x180006b99  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006b9e  jmp     loc_180006C65
0x180006ba3  mov     edx, 35h ; '5'; void *
0x180006ba8  mov     rcx, [rbp+5Fh]; this
0x180006bac  lea     r8, aOnecoreuapRest_1; "onecoreuap\\restricted\\shell\\inc\\win"...
0x180006bb3  mov     r9d, ebx; char *
0x180006bb6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006bbb  mov     rcx, [rbp+57h+var_70]
0x180006bbf  test    rcx, rcx
0x180006bc2  jz      short loc_180006BD4
0x180006bc4  mov     [rbp+57h+var_70], r15
0x180006bc8  mov     rax, [rcx]
0x180006bcb  mov     rax, [rax+10h]
0x180006bcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006bd4  mov     rcx, [rbp+57h+var_78]
0x180006bd8  test    rcx, rcx
0x180006bdb  jz      short loc_180006BED
0x180006bdd  mov     [rbp+57h+var_78], r15
0x180006be1  mov     rax, [rcx]
0x180006be4  mov     rax, [rax+10h]
0x180006be8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006bed  mov     rcx, [rbp+57h+var_80]
0x180006bf1  test    rcx, rcx
0x180006bf4  jz      short loc_180006BFF
0x180006bf6  mov     [rbp+57h+var_80], r15
0x180006bfa  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UIGraphicsEffect@Effects@Graphics@Windows@@UIGraphicsEffectSource@567@UIGraphicsEffectD2D1Interop@567@UIGaussianBlurEffect@5Composition@UI@Internal@3@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Graphics::Effects::IGraphicsEffect,Windows::Graphics::Effects::IGraphicsEffectSource,Windows::Graphics::Effects::IGraphicsEffectD2D1Interop,Microsoft::Internal::UI::Composition::Effects::IGaussianBlurEffect>::Release(void)
0x180006bff  lea     rcx, [rbp+57h+var_60]
0x180006c03  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180006c08  lea     rcx, [rbp+57h+var_58]
0x180006c0c  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180006c11  mov     rcx, [rbp+57h+var_88]
0x180006c15  test    rcx, rcx
0x180006c18  jz      short loc_180006C2A
0x180006c1a  mov     [rbp+57h+var_88], r15
0x180006c1e  mov     rax, [rcx]
0x180006c21  mov     rax, [rax+10h]
0x180006c25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c2a  lea     rcx, [rbp+57h+var_68]
0x180006c2e  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180006c33  mov     rcx, [rbp+57h+var_90]
0x180006c37  test    rcx, rcx
0x180006c3a  jz      short loc_180006C4C
0x180006c3c  mov     [rbp+57h+var_90], r15
0x180006c40  mov     rax, [rcx]
0x180006c43  mov     rax, [rax+10h]
0x180006c47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c4c  mov     rcx, [rbp+57h+var_98]
0x180006c50  test    rcx, rcx
0x180006c53  jz      short loc_180006C65
0x180006c55  mov     [rbp+57h+var_98], r15
0x180006c59  mov     rax, [rcx]
0x180006c5c  mov     rax, [rax+10h]
0x180006c60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c65  mov     rcx, [rbp+57h+var_A0]
0x180006c69  test    rcx, rcx
0x180006c6c  jz      short loc_180006C7E
0x180006c6e  mov     [rbp+57h+var_A0], r15
0x180006c72  mov     rax, [rcx]
0x180006c75  mov     rax, [rax+10h]
0x180006c79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c7e  mov     eax, ebx
0x180006c80  mov     rcx, [rbp+57h+var_30]
0x180006c84  xor     rcx, rsp; StackCookie
0x180006c87  call    __security_check_cookie
0x180006c8c  mov     rbx, [rsp+0C0h+arg_10]
0x180006c94  add     rsp, 0A0h
0x180006c9b  pop     r15
0x180006c9d  pop     r14
0x180006c9f  pop     rdi
0x180006ca0  pop     rsi
0x180006ca1  pop     rbp
0x180006ca2  retn
0x180006ca3  mov     rdx, [rbp+57h+string]
0x180006ca7  lea     r8, [rbp+57h+var_98]
0x180006cab  mov     rax, [rdi+30h]
0x180006caf  mov     rcx, rbx
0x180006cb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006cb7  mov     ebx, eax
0x180006cb9  test    eax, eax
0x180006cbb  js      loc_180006F07
0x180006cc1  mov     rbx, [rbp+57h+var_98]
0x180006cc5  lea     rcx, [rbp+57h+var_90]
0x180006cc9  mov     [rbp+57h+var_90], r15
0x180006ccd  mov     rax, [rbx]
0x180006cd0  mov     rdi, [rax]
0x180006cd3  call    ?InternalRelease@?$ComPtr@UICompositionEffectSourceParameterFactory@Composition@UI@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositionEffectSourceParameterFactory>::InternalRelease(void)
0x180006cd8  lea     r8, [rbp+57h+var_90]
0x180006cdc  mov     rcx, rbx
0x180006cdf  lea     rdx, _GUID_2d8f9ddc_4339_4eb9_9216_f9deb75658a2
0x180006ce6  mov     rax, rdi
0x180006ce9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006cee  mov     ebx, eax
0x180006cf0  test    eax, eax
0x180006cf2  js      loc_180006F24
0x180006cf8  mov     rax, [rsi]
0x180006cfb  lea     rcx, [rbp+57h+var_68]
0x180006cff  mov     [rbp+57h+var_68], r15
0x180006d03  mov     rbx, [rax]
0x180006d06  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180006d0b  lea     r8, [rbp+57h+var_68]
0x180006d0f  mov     rcx, rsi
0x180006d12  lea     rdx, _GUID_735081dc_5e24_45da_a38f_e32cc349a9a0
0x180006d19  mov     rax, rbx
0x180006d1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d21  mov     ebx, eax
0x180006d23  test    eax, eax
0x180006d25  js      loc_180006ECD
0x180006d2b  mov     rdi, [rbp+57h+var_68]
0x180006d2f  lea     rcx, [rbp+57h+var_88]
0x180006d33  mov     [rbp+57h+var_88], r15
0x180006d37  mov     rax, [rdi]
0x180006d3a  mov     rbx, [rax+40h]
0x180006d3e  call    ?InternalRelease@?$ComPtr@UICompositionEffectSourceParameterFactory@Composition@UI@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositionEffectSourceParameterFactory>::InternalRelease(void)
0x180006d43  lea     rdx, [rbp+57h+var_88]
0x180006d47  mov     rcx, rdi
0x180006d4a  mov     rax, rbx
0x180006d4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d52  mov     ebx, eax
0x180006d54  test    eax, eax
0x180006d56  js      loc_180006EEA
0x180006d5c  mov     rbx, [rbp+57h+var_88]
0x180006d60  lea     rcx, [rbp+57h+var_58]
0x180006d64  mov     [rbp+57h+var_58], r15
0x180006d68  mov     rax, [rbx]
0x180006d6b  mov     rdi, [rax]
0x180006d6e  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180006d73  lea     r8, [rbp+57h+var_58]
0x180006d77  mov     rcx, rbx
0x180006d7a  lea     rdx, _GUID_ab0d7608_30c0_40e9_b568_b60a6bd1fb46
0x180006d81  mov     rax, rdi
0x180006d84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d89  mov     ebx, eax
0x180006d8b  test    eax, eax
0x180006d8d  js      loc_180006F41
0x180006d93  lea     rcx, [rbp+57h+var_80]
0x180006d97  mov     [rbp+57h+var_60], r15
0x180006d9b  mov     [rbp+57h+var_80], r15
0x180006d9f  call    ??$MakeAndInitialize@VGaussianBlurEffect@Effects@Composition@UI@Internal@Microsoft@@V123456@$$V@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@VGaussianBlurEffect@Effects@Composition@UI@Internal@Microsoft@@@WRL@Microsoft@@@012@@Z; Microsoft::WRL::Details::MakeAndInitialize<Microsoft::Internal::UI::Composition::Effects::GaussianBlurEffect,Microsoft::Internal::UI::Composition::Effects::GaussianBlurEffect,>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Microsoft::Internal::UI::Composition::Effects::GaussianBlurEffect>>)
0x180006da4  mov     ebx, eax
0x180006da6  test    eax, eax
0x180006da8  js      loc_180006F5E
0x180006dae  mov     rax, [rbp+57h+var_80]
0x180006db2  mov     dword ptr [rax+4Ch], 1
0x180006db9  mov     rax, [rbp+57h+var_80]
0x180006dbd  mov     dword ptr [rax+48h], 41F00000h
0x180006dc4  mov     rdi, [rbp+57h+var_80]
0x180006dc8  mov     rbx, [rbp+57h+var_90]
0x180006dcc  cmp     [rdi+40h], rbx
0x180006dd0  jz      short loc_180006DF4
0x180006dd2  test    rbx, rbx
0x180006dd5  jnz     loc_1800070CB
0x180006ddb  mov     rcx, [rdi+40h]
0x180006ddf  mov     [rdi+40h], rbx
0x180006de3  test    rcx, rcx
0x180006de6  jz      short loc_180006DF4
0x180006de8  mov     rax, [rcx]
0x180006deb  mov     rax, [rax+10h]
0x180006def  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006df4  mov     rax, [rsi]
0x180006df7  lea     rcx, [rbp+57h+var_78]
0x180006dfb  mov     [rbp+57h+var_78], r15
0x180006dff  mov     rbx, [rax]
0x180006e02  call    ?InternalRelease@?$ComPtr@UICompositionEffectSourceParameterFactory@Composition@UI@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositionEffectSourceParameterFactory>::InternalRelease(void)
0x180006e07  lea     r8, [rbp+57h+var_78]
0x180006e0b  mov     rcx, rsi
0x180006e0e  lea     rdx, _GUID_b403ca50_7f8c_4e83_985f_cc45060036d8
0x180006e15  mov     rax, rbx
0x180006e18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e1d  mov     ebx, eax
0x180006e1f  test    eax, eax
0x180006e21  js      loc_180006F7B
0x180006e27  mov     rdi, [rbp+57h+var_78]
0x180006e2b  lea     rcx, [rbp+57h+var_70]
0x180006e2f  mov     [rbp+57h+var_70], r15
0x180006e33  mov     rax, [rdi]
0x180006e36  mov     rbx, [rax+58h]
0x180006e3a  call    ?InternalRelease@?$ComPtr@UICompositionEffectSourceParameterFactory@Composition@UI@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositionEffectSourceParameterFactory>::InternalRelease(void)
0x180006e3f  mov     rdx, [rbp+57h+var_80]
0x180006e43  lea     r8, [rbp+57h+var_70]
0x180006e47  mov     rcx, rdi
0x180006e4a  mov     rax, rbx
0x180006e4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e52  mov     ebx, eax
0x180006e54  test    eax, eax
0x180006e56  js      loc_180006F98
0x180006e5c  mov     rdi, [rbp+57h+var_70]
0x180006e60  lea     rcx, [rbp+57h+var_60]
0x180006e64  mov     rax, [rdi]
0x180006e67  mov     rbx, [rax+30h]
0x180006e6b  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180006e70  lea     rdx, [rbp+57h+var_60]
0x180006e74  mov     rcx, rdi
0x180006e77  mov     rax, rbx
0x180006e7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e7f  mov     ebx, eax
0x180006e81  test    eax, eax
0x180006e83  js      loc_180006FA2
0x180006e89  mov     rbx, [rbp+57h+var_60]
0x180006e8d  lea     r9, [rbp+57h+string]; string
0x180006e91  mov     rsi, [rbp+57h+var_58]
0x180006e95  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180006e99  mov     edx, 6; length
0x180006e9e  lea     rcx, sourceString; "source"
0x180006ea5  mov     rdi, [rbx]
0x180006ea8  mov     [rbp+57h+string], r15
0x180006eac  call    cs:__imp_WindowsCreateStringReference
0x180006eb2  test    eax, eax
0x180006eb4  jns     loc_180006FAC
0x180006eba  xor     r9d, r9d; lpArguments
0x180006ebd  xor     r8d, r8d; nNumberOfArguments
0x180006ec0  mov     ecx, eax; dwExceptionCode
0x180006ec2  lea     edx, [r9+1]; dwExceptionFlags
0x180006ec6  call    cs:__imp_RaiseException
0x180006ecc  int     3; Trap to Debugger
0x180006ecd  mov     rcx, [rbp+5Fh]; this
0x180006ed1  lea     r8, aOnecoreuapRest_1; "onecoreuap\\restricted\\shell\\inc\\win"...
0x180006ed8  mov     r9d, ebx; char *
0x180006edb  mov     edx, 1Dh; void *
0x180006ee0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006ee5  jmp     loc_180006C2A
0x180006eea  mov     rcx, [rbp+5Fh]; this
0x180006eee  lea     r8, aOnecoreuapRest_1; "onecoreuap\\restricted\\shell\\inc\\win"...
0x180006ef5  mov     r9d, ebx; char *
0x180006ef8  mov     edx, 20h ; ' '; void *
0x180006efd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006f02  jmp     loc_180006C11
0x180006f07  mov     rcx, [rbp+5Fh]; this
0x180006f0b  lea     r8, aOnecoreuapRest_1; "onecoreuap\\restricted\\shell\\inc\\win"...
0x180006f12  mov     r9d, ebx; char *
0x180006f15  mov     edx, 19h; void *
0x180006f1a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006f1f  jmp     loc_180006C4C
0x180006f24  mov     rcx, [rbp+5Fh]; this
0x180006f28  lea     r8, aOnecoreuapRest_1; "onecoreuap\\restricted\\shell\\inc\\win"...
0x180006f2f  mov     r9d, ebx; char *
0x180006f32  mov     edx, 1Bh; void *
0x180006f37  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
  ... truncated ...
```
