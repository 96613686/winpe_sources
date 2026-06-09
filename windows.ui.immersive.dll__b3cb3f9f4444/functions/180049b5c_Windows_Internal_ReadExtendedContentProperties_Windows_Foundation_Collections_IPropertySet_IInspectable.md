# Windows::Internal::ReadExtendedContentProperties(Windows::Foundation::Collections::IPropertySet *,IInspectable * *)

- ea: `0x180049b5c`
- end: `0x18004a0d8`
- name: `?ReadExtendedContentProperties@Internal@Windows@@YAJPEAUIPropertySet@Collections@Foundation@2@PEAPEAUIInspectable@@@Z`
- size: `1404`
- prototype: `__int64 __fastcall(Windows::Internal *__hidden this, struct Windows::Foundation::Collections::IPropertySet *, struct IInspectable **)`
- caller_count: `1`
- callee_count: `17`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180034674`

## callees

- `0x180013900`
- `0x180013f14`
- `0x180014350`
- `0x180026ce8`
- `0x18003729c`
- `0x180039310`
- `0x18003ae60`
- `0x180045dec`
- `0x180049a84`
- `0x180049b5c`
- `0x18004a0e0`
- `0x18004a138`
- `0x18004a1d8`
- `0x180054130`
- `0x180059b4c`
- `0x180087934`
- `0x1800ed010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180049ece`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180049ee4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180049efa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180049f10`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180049f26`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180049ece`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180049ee4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180049efa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180049f10`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180049f26`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180049d16`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180049d7c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180049dd0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180049e24`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180049e78`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180049fb1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180049fc5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180049fd9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180049fed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a001`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a033`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a047`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a05b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a06f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a083`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180049d16`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180049d7c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180049dd0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180049e24`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180049e78`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180049fb1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180049fc5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180049fd9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180049fed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a001`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a033`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a047`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a05b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a06f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a083`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall Windows::Internal::ReadExtendedContentProperties(
        Windows::Internal *this,
        struct Windows::Foundation::Collections::IPropertySet *a2,
        struct IInspectable **a3)
{
  __int64 v5; // rdx
  __int64 v6; // r8
  int v7; // eax
  unsigned int v8; // ebx
  __int64 v9; // rdi
  int (__fastcall *v10)(__int64, _QWORD, _QWORD); // rbx
  __int64 v11; // rax
  __int64 (__fastcall ***v12)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v13)(_QWORD, GUID *, struct IUnknown **); // rdi
  int v14; // eax
  struct IUnknown *v15; // rdi
  HSTRING v16; // rbx
  Windows::Internal::PopupWindowXAMLContentImpl *v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  unsigned int v20; // eax
  __int64 v21; // rax
  unsigned int v22; // eax
  __int64 v23; // rax
  unsigned int v24; // eax
  __int64 v25; // rax
  unsigned int v26; // eax
  __int64 v27; // rax
  unsigned int v28; // eax
  PCWSTR *v29; // rax
  PCWSTR v30; // rbx
  struct IUnknown *v31; // rcx
  int v33; // [rsp+20h] [rbp-89h]
  int v34; // [rsp+20h] [rbp-89h]
  HSTRING string; // [rsp+30h] [rbp-79h] BYREF
  HSTRING v36; // [rsp+38h] [rbp-71h] BYREF
  HSTRING v37; // [rsp+40h] [rbp-69h]
  HSTRING v38; // [rsp+48h] [rbp-61h]
  HSTRING v39; // [rsp+50h] [rbp-59h]
  struct IUnknown *v40; // [rsp+58h] [rbp-51h] BYREF
  Windows::Internal *v41; // [rsp+60h] [rbp-49h] BYREF
  PCWSTR StringRawBuffer; // [rsp+68h] [rbp-41h] BYREF
  __int64 v43; // [rsp+70h] [rbp-39h] BYREF
  Windows::Internal *v44; // [rsp+78h] [rbp-31h] BYREF
  __int64 (__fastcall ***v45)(_QWORD, GUID *, struct IUnknown **); // [rsp+80h] [rbp-29h] BYREF
  int v46[2]; // [rsp+88h] [rbp-21h] BYREF
  PCWSTR v47; // [rsp+90h] [rbp-19h] BYREF
  PCWSTR v48; // [rsp+98h] [rbp-11h] BYREF
  PCWSTR v49; // [rsp+A0h] [rbp-9h] BYREF
  _BYTE v50[32]; // [rsp+A8h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  *(_QWORD *)a2 = 0;
  v41 = this;
  Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(&v41, a2, a3);
  v45 = 0;
  v44 = this;
  Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(&v44, v5, v6);
  v43 = 0;
  v7 = Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(
         &v44,
         &v43);
  v8 = v7;
  if ( v7 >= 0 )
  {
    v9 = v43;
    v10 = *(int (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v43 + 48LL);
    v11 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
            v50,
            c_MessageDialogContentProp_FullCustomExtendedContent);
    if ( v10(v9, *(_QWORD *)(v11 + 24), &v45) < 0 )
    {
      string = 0;
      v39 = 0;
      v38 = 0;
      v37 = 0;
      WindowsDeleteString(0);
      v36 = 0;
      v19 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v50, &c_MessageDialogContentProp_Primary);
      v20 = Windows::Internal::ShellHelpers::PropertySetHelper::GetValue<HSTRING__ *>(
              (Windows::Internal::ShellHelpers::PropertySetHelper *)&v41,
              *(HSTRING *)(v19 + 24));
      wil::details::in1diag3::Log_IfFailedWithExpected(
        retaddr,
        (void *)0x148,
        (unsigned int)"shell\\windowsuiimmersive\\popup\\messagedialog.cpp",
        (const char *)v20,
        1,
        0x8000000B);
      WindowsDeleteString(0);
      string = 0;
      v21 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v50, c_MessageDialogContentProp_Secondary);
      v22 = Windows::Internal::ShellHelpers::PropertySetHelper::GetValue<HSTRING__ *>(
              (Windows::Internal::ShellHelpers::PropertySetHelper *)&v41,
              *(HSTRING *)(v21 + 24));
      wil::details::in1diag3::Log_IfFailedWithExpected(
        retaddr,
        (void *)0x149,
        (unsigned int)"shell\\windowsuiimmersive\\popup\\messagedialog.cpp",
        (const char *)v22,
        1,
        0x8000000B);
      WindowsDeleteString(0);
      v39 = 0;
      v23 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v50, c_MessageDialogContentProp_Glyph);
      v24 = Windows::Internal::ShellHelpers::PropertySetHelper::GetValue<HSTRING__ *>(
              (Windows::Internal::ShellHelpers::PropertySetHelper *)&v41,
              *(HSTRING *)(v23 + 24));
      wil::details::in1diag3::Log_IfFailedWithExpected(
        retaddr,
        (void *)0x14A,
        (unsigned int)"shell\\windowsuiimmersive\\popup\\messagedialog.cpp",
        (const char *)v24,
        1,
        0x8000000B);
      WindowsDeleteString(0);
      v38 = 0;
      v25 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v50, c_MessageDialogContentProp_GlyphFont);
      v26 = Windows::Internal::ShellHelpers::PropertySetHelper::GetValue<HSTRING__ *>(
              (Windows::Internal::ShellHelpers::PropertySetHelper *)&v41,
              *(HSTRING *)(v25 + 24));
      wil::details::in1diag3::Log_IfFailedWithExpected(
        retaddr,
        (void *)0x14B,
        (unsigned int)"shell\\windowsuiimmersive\\popup\\messagedialog.cpp",
        (const char *)v26,
        1,
        0x8000000B);
      WindowsDeleteString(0);
      v37 = 0;
      v27 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v50, c_MessageDialogContentProp_Hyperlink);
      v28 = Windows::Internal::ShellHelpers::PropertySetHelper::GetValue<HSTRING__ *>(
              (Windows::Internal::ShellHelpers::PropertySetHelper *)&v41,
              *(HSTRING *)(v27 + 24));
      wil::details::in1diag3::Log_IfFailedWithExpected(
        retaddr,
        (void *)0x14C,
        (unsigned int)"shell\\windowsuiimmersive\\popup\\messagedialog.cpp",
        (const char *)v28,
        1,
        0x8000000B);
      StringRawBuffer = WindowsGetStringRawBuffer(0, 0);
      *(_QWORD *)v46 = WindowsGetStringRawBuffer(0, 0);
      v47 = WindowsGetStringRawBuffer(0, 0);
      v48 = WindowsGetStringRawBuffer(0, 0);
      v49 = WindowsGetStringRawBuffer(0, 0);
      v29 = (PCWSTR *)Microsoft::WRL::Details::Make<Windows::Internal::PopupWindowExtendedStringContentImpl,unsigned short const *,unsigned short const *,unsigned short const *,unsigned short const *,unsigned short const *>(
                        (unsigned int)&v40,
                        (unsigned int)&v49,
                        (unsigned int)&v48,
                        (unsigned int)&v47,
                        (__int64)v46,
                        (__int64)&StringRawBuffer);
      v30 = *v29;
      StringRawBuffer = *v29;
      *v29 = 0;
      v31 = v40;
      if ( v40 )
      {
        v40 = 0;
        ((void (__fastcall *)(struct IUnknown *))v31->lpVtbl->Release)(v31);
      }
      if ( !v30 )
      {
        v8 = -2147024882;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x150,
          (unsigned int)"shell\\windowsuiimmersive\\popup\\messagedialog.cpp",
          (const char *)0x8007000ELL,
          v34);
        Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&StringRawBuffer);
        WindowsDeleteString(v37);
        v37 = 0;
        WindowsDeleteString(v38);
        v38 = 0;
        WindowsDeleteString(v39);
        v39 = 0;
        WindowsDeleteString(string);
        string = 0;
        WindowsDeleteString(v36);
        v36 = 0;
        goto LABEL_17;
      }
      (*(void (__fastcall **)(PCWSTR))(*(_QWORD *)v30 + 8LL))(v30);
      *(_QWORD *)a2 = v30;
      Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&StringRawBuffer);
      WindowsDeleteString(v37);
      v37 = 0;
      WindowsDeleteString(v38);
      v38 = 0;
      WindowsDeleteString(v39);
      v39 = 0;
      WindowsDeleteString(string);
      string = 0;
      WindowsDeleteString(v36);
    }
    else
    {
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_CustomXamlUIDialog>::ReportUsage(
        `wil::Feature<__WilFeatureTraits_Feature_CustomXamlUIDialog>::GetImpl'::`2'::impl,
        1);
      v40 = 0;
      v12 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v45;
      v13 = **v45;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v40);
      v14 = v13(v12, &GUID_00000000_0000_0000_c000_000000000046, &v40);
      v8 = v14;
      if ( v14 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x13A,
          (unsigned int)"shell\\windowsuiimmersive\\popup\\messagedialog.cpp",
          (const char *)(unsigned int)v14,
          v33);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v40);
        goto LABEL_17;
      }
      v15 = v40;
      v16 = 0;
      v36 = 0;
      v17 = (Windows::Internal::PopupWindowXAMLContentImpl *)operator new(
                                                               0x28u,
                                                               (const struct std::nothrow_t *)&std::nothrow);
      string = (HSTRING)v17;
      if ( v17 )
      {
        v18 = Windows::Internal::PopupWindowXAMLContentImpl::PopupWindowXAMLContentImpl(v17, v15);
        Microsoft::WRL::ComPtr<Windows::Internal::PopupWindowXAMLContentImpl>::Attach(&v36, v18);
        string = 0;
        v16 = v36;
      }
      Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::Details::DelegateArgTraits<long (IPopupEventHandler::*)(IPopupWindow *)>::DelegateInvokeHelper<IPopupEventHandler,_lambda_3f7781bf84e6b498cf9989aa99f207ed_,-1,IPopupWindow *>>::~MakeAllocator<Microsoft::WRL::Details::DelegateArgTraits<long (IPopupEventHandler::*)(IPopupWindow *)>::DelegateInvokeHelper<IPopupEventHandler,_lambda_3f7781bf84e6b498cf9989aa99f207ed_,-1,IPopupWindow *>>(&string);
      StringRawBuffer = (PCWSTR)v16;
      if ( v16 )
        (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v16 + 8LL))(v16);
      *(_QWORD *)a2 = v16;
      Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&StringRawBuffer);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v40);
    }
    v8 = 0;
    goto LABEL_17;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x132,
    (unsigned int)"shell\\windowsuiimmersive\\popup\\messagedialog.cpp",
    (const char *)(unsigned int)v7,
    v33);
LABEL_17:
  Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v43);
  Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v44);
  Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v45);
  Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v41);
  return v8;
}

```

## disassembly

```asm
0x180049b5c  push    rbp
0x180049b5e  push    rbx
0x180049b5f  push    rsi
0x180049b60  push    rdi
0x180049b61  push    r14
0x180049b63  push    r15
0x180049b65  lea     rbp, [rsp-2Fh]
0x180049b6a  sub     rsp, 0D8h
0x180049b71  mov     rax, cs:__security_cookie
0x180049b78  xor     rax, rsp
0x180049b7b  mov     [rbp+57h+var_38], rax
0x180049b7f  mov     rsi, rdx
0x180049b82  mov     rbx, rcx
0x180049b85  xor     r15d, r15d
0x180049b88  mov     [rdx], r15
0x180049b8b  mov     [rbp+57h+var_A0], rcx
0x180049b8f  lea     rcx, [rbp+57h+var_A0]
0x180049b93  call    ?InternalAddRef@?$ComPtr@UIAsyncActionCompletedHandler@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(void)
0x180049b98  nop
0x180049b99  mov     [rbp+57h+var_80], r15
0x180049b9d  mov     [rbp+57h+var_88], rbx
0x180049ba1  lea     rcx, [rbp+57h+var_88]
0x180049ba5  call    ?InternalAddRef@?$ComPtr@UIAsyncActionCompletedHandler@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(void)
0x180049baa  nop
0x180049bab  mov     [rbp+57h+var_90], r15
0x180049baf  lea     rdx, [rbp+57h+var_90]
0x180049bb3  lea     rcx, [rbp+57h+var_88]
0x180049bb7  call    ??$As@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>>)
0x180049bbc  mov     ebx, eax
0x180049bbe  test    eax, eax
0x180049bc0  jns     short loc_180049BDF
0x180049bc2  mov     rcx, [rbp+5Fh]; this
0x180049bc6  mov     r9d, eax; char *
0x180049bc9  lea     r8, aShellWindowsui; "shell\\windowsuiimmersive\\popup\\messa"...
0x180049bd0  mov     edx, 132h; void *
0x180049bd5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180049bda  jmp     loc_18004A092
0x180049bdf  mov     rdi, [rbp+57h+var_90]
0x180049be3  mov     rax, [rdi]
0x180049be6  mov     rbx, [rax+30h]
0x180049bea  lea     rdx, c_MessageDialogContentProp_FullCustomExtendedContent
0x180049bf1  lea     rcx, [rbp+57h+var_58]
0x180049bf5  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180049bfa  nop
0x180049bfb  lea     r8, [rbp+57h+var_80]
0x180049bff  mov     rdx, [rax+18h]
0x180049c03  mov     rcx, rdi
0x180049c06  mov     rax, rbx
0x180049c09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049c0e  nop
0x180049c0f  test    eax, eax
0x180049c11  js      loc_180049D00
0x180049c17  mov     edx, 1
0x180049c1c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CustomXamlUIDialog@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CustomXamlUIDialog@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CustomXamlUIDialog> `wil::Feature<__WilFeatureTraits_Feature_CustomXamlUIDialog>::GetImpl(void)'::`2'::impl
0x180049c23  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_CustomXamlUIDialog@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CustomXamlUIDialog>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180049c28  mov     [rbp+57h+var_A8], r15
0x180049c2c  mov     rbx, [rbp+57h+var_80]
0x180049c30  mov     rax, [rbx]
0x180049c33  mov     rdi, [rax]
0x180049c36  lea     rcx, [rbp+57h+var_A8]
0x180049c3a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180049c3f  lea     r8, [rbp+57h+var_A8]
0x180049c43  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180049c4a  mov     rcx, rbx
0x180049c4d  mov     rax, rdi
0x180049c50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049c55  mov     ebx, eax
0x180049c57  test    eax, eax
0x180049c59  jns     short loc_180049C81
0x180049c5b  mov     rcx, [rbp+5Fh]; this
0x180049c5f  mov     r9d, eax; char *
0x180049c62  lea     r8, aShellWindowsui; "shell\\windowsuiimmersive\\popup\\messa"...
0x180049c69  mov     edx, 13Ah; void *
0x180049c6e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180049c73  lea     rcx, [rbp+57h+var_A8]
0x180049c77  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180049c7c  jmp     loc_18004A092
0x180049c81  mov     rdi, [rbp+57h+var_A8]
0x180049c85  mov     rbx, r15
0x180049c88  mov     [rbp+57h+var_C8], rbx
0x180049c8c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180049c93  mov     ecx, 28h ; '('; unsigned __int64
0x180049c98  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180049c9d  mov     [rbp+57h+string], rax
0x180049ca1  test    rax, rax
0x180049ca4  jz      short loc_180049CC5
0x180049ca6  mov     rdx, rdi; struct IUnknown *
0x180049ca9  mov     rcx, rax; this
0x180049cac  call    ??0PopupWindowXAMLContentImpl@Internal@Windows@@QEAA@PEAUIUnknown@@@Z; Windows::Internal::PopupWindowXAMLContentImpl::PopupWindowXAMLContentImpl(IUnknown *)
0x180049cb1  mov     rdx, rax
0x180049cb4  lea     rcx, [rbp+57h+var_C8]
0x180049cb8  call    ?Attach@?$ComPtr@VPopupWindowXAMLContentImpl@Internal@Windows@@@WRL@Microsoft@@QEAAXPEAVPopupWindowXAMLContentImpl@Internal@Windows@@@Z; Microsoft::WRL::ComPtr<Windows::Internal::PopupWindowXAMLContentImpl>::Attach(Windows::Internal::PopupWindowXAMLContentImpl *)
0x180049cbd  mov     [rbp+57h+string], r15
0x180049cc1  mov     rbx, [rbp+57h+var_C8]
0x180049cc5  lea     rcx, [rbp+57h+string]
0x180049cc9  call    ??1?$MakeAllocator@U?$DelegateInvokeHelper@UIPopupEventHandler@@V_lambda_3f7781bf84e6b498cf9989aa99f207ed_@@$0?0PEAUIPopupWindow@@@?$DelegateArgTraits@P8IPopupEventHandler@@EAAJPEAUIPopupWindow@@@Z@Details@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::Details::DelegateArgTraits<long (IPopupEventHandler::*)(IPopupWindow *)>::DelegateInvokeHelper<IPopupEventHandler,_lambda_3f7781bf84e6b498cf9989aa99f207ed_,-1,IPopupWindow *>>::~MakeAllocator<Microsoft::WRL::Details::DelegateArgTraits<long (IPopupEventHandler::*)(IPopupWindow *)>::DelegateInvokeHelper<IPopupEventHandler,_lambda_3f7781bf84e6b498cf9989aa99f207ed_,-1,IPopupWindow *>>(void)
0x180049cce  mov     [rbp+57h+var_98], rbx
0x180049cd2  test    rbx, rbx
0x180049cd5  jz      short loc_180049CE6
0x180049cd7  mov     rax, [rbx]
0x180049cda  mov     rcx, rbx
0x180049cdd  mov     rax, [rax+8]
0x180049ce1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049ce6  mov     [rsi], rbx
0x180049ce9  lea     rcx, [rbp+57h+var_98]
0x180049ced  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x180049cf2  lea     rcx, [rbp+57h+var_A8]
0x180049cf6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180049cfb  jmp     loc_18004A08F
0x180049d00  mov     [rbp+57h+var_C8], r15
0x180049d04  mov     [rbp+57h+string], r15
0x180049d08  mov     [rbp+57h+var_B0], r15
0x180049d0c  mov     [rbp+57h+var_B8], r15
0x180049d10  mov     [rbp+57h+var_C0], r15
0x180049d14  xor     ecx, ecx; string
0x180049d16  call    cs:__imp_WindowsDeleteString
0x180049d1d  nop     dword ptr [rax+rax+00h]
0x180049d22  mov     [rbp+57h+var_C8], r15
0x180049d26  lea     rdx, c_MessageDialogContentProp_Primary
0x180049d2d  lea     rcx, [rbp+57h+var_58]
0x180049d31  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180049d36  nop
0x180049d37  lea     r9, [rbp+57h+var_C8]
0x180049d3b  mov     rdx, [rax+18h]
0x180049d3f  lea     rcx, [rbp+57h+var_A0]
0x180049d43  call    ??$GetValue@PEAUHSTRING__@@@PropertySetHelper@ShellHelpers@Internal@Windows@@AEAAJPEAUHSTRING__@@P8IPropertyValue@Foundation@3@EAAJPEAPEAU4@@Z1@Z; Windows::Internal::ShellHelpers::PropertySetHelper::GetValue<HSTRING__ *>(HSTRING__ *,long (Windows::Foundation::IPropertyValue::*)(HSTRING__ * *),HSTRING__ * *)
0x180049d48  mov     rcx, [rbp+5Fh]; this
0x180049d4c  mov     r14d, 8000000Bh
0x180049d52  mov     [rsp+100h+var_D8], r14d; unsigned int
0x180049d57  mov     ebx, 1
0x180049d5c  mov     [rsp+100h+var_E0], ebx; int
0x180049d60  mov     r9d, eax; char *
0x180049d63  lea     rdi, aShellWindowsui; "shell\\windowsuiimmersive\\popup\\messa"...
0x180049d6a  mov     r8, rdi; unsigned int
0x180049d6d  mov     edx, 148h; void *
0x180049d72  call    ?Log_IfFailedWithExpected@in1diag3@details@wil@@YAJPEAXIPEBDJIZZ; wil::details::in1diag3::Log_IfFailedWithExpected(void *,uint,char const *,long,uint,...)
0x180049d77  nop
0x180049d78  mov     rcx, [rbp+57h+string]; string
0x180049d7c  call    cs:__imp_WindowsDeleteString
0x180049d83  nop     dword ptr [rax+rax+00h]
0x180049d88  mov     [rbp+57h+string], r15
0x180049d8c  lea     rdx, c_MessageDialogContentProp_Secondary
0x180049d93  lea     rcx, [rbp+57h+var_58]
0x180049d97  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180049d9c  nop
0x180049d9d  lea     r9, [rbp+57h+string]
0x180049da1  mov     rdx, [rax+18h]
0x180049da5  lea     rcx, [rbp+57h+var_A0]
0x180049da9  call    ??$GetValue@PEAUHSTRING__@@@PropertySetHelper@ShellHelpers@Internal@Windows@@AEAAJPEAUHSTRING__@@P8IPropertyValue@Foundation@3@EAAJPEAPEAU4@@Z1@Z; Windows::Internal::ShellHelpers::PropertySetHelper::GetValue<HSTRING__ *>(HSTRING__ *,long (Windows::Foundation::IPropertyValue::*)(HSTRING__ * *),HSTRING__ * *)
0x180049dae  mov     rcx, [rbp+5Fh]; this
0x180049db2  mov     [rsp+100h+var_D8], r14d; unsigned int
0x180049db7  mov     [rsp+100h+var_E0], ebx; int
0x180049dbb  mov     r9d, eax; char *
0x180049dbe  mov     r8, rdi; unsigned int
0x180049dc1  mov     edx, 149h; void *
0x180049dc6  call    ?Log_IfFailedWithExpected@in1diag3@details@wil@@YAJPEAXIPEBDJIZZ; wil::details::in1diag3::Log_IfFailedWithExpected(void *,uint,char const *,long,uint,...)
0x180049dcb  nop
0x180049dcc  mov     rcx, [rbp+57h+var_B0]; string
0x180049dd0  call    cs:__imp_WindowsDeleteString
0x180049dd7  nop     dword ptr [rax+rax+00h]
0x180049ddc  mov     [rbp+57h+var_B0], r15
0x180049de0  lea     rdx, c_MessageDialogContentProp_Glyph
0x180049de7  lea     rcx, [rbp+57h+var_58]
0x180049deb  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180049df0  nop
0x180049df1  lea     r9, [rbp+57h+var_B0]
0x180049df5  mov     rdx, [rax+18h]
0x180049df9  lea     rcx, [rbp+57h+var_A0]
0x180049dfd  call    ??$GetValue@PEAUHSTRING__@@@PropertySetHelper@ShellHelpers@Internal@Windows@@AEAAJPEAUHSTRING__@@P8IPropertyValue@Foundation@3@EAAJPEAPEAU4@@Z1@Z; Windows::Internal::ShellHelpers::PropertySetHelper::GetValue<HSTRING__ *>(HSTRING__ *,long (Windows::Foundation::IPropertyValue::*)(HSTRING__ * *),HSTRING__ * *)
0x180049e02  mov     rcx, [rbp+5Fh]; this
0x180049e06  mov     [rsp+100h+var_D8], r14d; unsigned int
0x180049e0b  mov     [rsp+100h+var_E0], ebx; int
0x180049e0f  mov     r9d, eax; char *
0x180049e12  mov     r8, rdi; unsigned int
0x180049e15  mov     edx, 14Ah; void *
0x180049e1a  call    ?Log_IfFailedWithExpected@in1diag3@details@wil@@YAJPEAXIPEBDJIZZ; wil::details::in1diag3::Log_IfFailedWithExpected(void *,uint,char const *,long,uint,...)
0x180049e1f  nop
0x180049e20  mov     rcx, [rbp+57h+var_B8]; string
0x180049e24  call    cs:__imp_WindowsDeleteString
0x180049e2b  nop     dword ptr [rax+rax+00h]
0x180049e30  mov     [rbp+57h+var_B8], r15
0x180049e34  lea     rdx, c_MessageDialogContentProp_GlyphFont
0x180049e3b  lea     rcx, [rbp+57h+var_58]
0x180049e3f  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180049e44  nop
0x180049e45  lea     r9, [rbp+57h+var_B8]
0x180049e49  mov     rdx, [rax+18h]
0x180049e4d  lea     rcx, [rbp+57h+var_A0]
0x180049e51  call    ??$GetValue@PEAUHSTRING__@@@PropertySetHelper@ShellHelpers@Internal@Windows@@AEAAJPEAUHSTRING__@@P8IPropertyValue@Foundation@3@EAAJPEAPEAU4@@Z1@Z; Windows::Internal::ShellHelpers::PropertySetHelper::GetValue<HSTRING__ *>(HSTRING__ *,long (Windows::Foundation::IPropertyValue::*)(HSTRING__ * *),HSTRING__ * *)
0x180049e56  mov     rcx, [rbp+5Fh]; this
0x180049e5a  mov     [rsp+100h+var_D8], r14d; unsigned int
0x180049e5f  mov     [rsp+100h+var_E0], ebx; int
0x180049e63  mov     r9d, eax; char *
0x180049e66  mov     r8, rdi; unsigned int
0x180049e69  mov     edx, 14Bh; void *
0x180049e6e  call    ?Log_IfFailedWithExpected@in1diag3@details@wil@@YAJPEAXIPEBDJIZZ; wil::details::in1diag3::Log_IfFailedWithExpected(void *,uint,char const *,long,uint,...)
0x180049e73  nop
0x180049e74  mov     rcx, [rbp+57h+var_C0]; string
0x180049e78  call    cs:__imp_WindowsDeleteString
0x180049e7f  nop     dword ptr [rax+rax+00h]
0x180049e84  mov     [rbp+57h+var_C0], r15
0x180049e88  lea     rdx, c_MessageDialogContentProp_Hyperlink
0x180049e8f  lea     rcx, [rbp+57h+var_58]
0x180049e93  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180049e98  nop
0x180049e99  lea     r9, [rbp+57h+var_C0]
0x180049e9d  mov     rdx, [rax+18h]
0x180049ea1  lea     rcx, [rbp+57h+var_A0]
0x180049ea5  call    ??$GetValue@PEAUHSTRING__@@@PropertySetHelper@ShellHelpers@Internal@Windows@@AEAAJPEAUHSTRING__@@P8IPropertyValue@Foundation@3@EAAJPEAPEAU4@@Z1@Z; Windows::Internal::ShellHelpers::PropertySetHelper::GetValue<HSTRING__ *>(HSTRING__ *,long (Windows::Foundation::IPropertyValue::*)(HSTRING__ * *),HSTRING__ * *)
0x180049eaa  mov     rcx, [rbp+5Fh]; this
0x180049eae  mov     [rsp+100h+var_D8], r14d; unsigned int
0x180049eb3  mov     [rsp+100h+var_E0], ebx; int
0x180049eb7  mov     r9d, eax; char *
0x180049eba  mov     r8, rdi; unsigned int
0x180049ebd  mov     edx, 14Ch; void *
0x180049ec2  call    ?Log_IfFailedWithExpected@in1diag3@details@wil@@YAJPEAXIPEBDJIZZ; wil::details::in1diag3::Log_IfFailedWithExpected(void *,uint,char const *,long,uint,...)
0x180049ec7  nop
0x180049ec8  xor     edx, edx; length
0x180049eca  mov     rcx, [rbp+57h+var_C0]; string
0x180049ece  call    cs:__imp_WindowsGetStringRawBuffer
0x180049ed5  nop     dword ptr [rax+rax+00h]
0x180049eda  mov     [rbp+57h+var_98], rax
0x180049ede  xor     edx, edx; length
0x180049ee0  mov     rcx, [rbp+57h+var_B8]; string
0x180049ee4  call    cs:__imp_WindowsGetStringRawBuffer
0x180049eeb  nop     dword ptr [rax+rax+00h]
0x180049ef0  mov     qword ptr [rbp+57h+var_78], rax
0x180049ef4  xor     edx, edx; length
0x180049ef6  mov     rcx, [rbp+57h+var_B0]; string
0x180049efa  call    cs:__imp_WindowsGetStringRawBuffer
0x180049f01  nop     dword ptr [rax+rax+00h]
0x180049f06  mov     [rbp+57h+var_70], rax
0x180049f0a  xor     edx, edx; length
0x180049f0c  mov     rcx, [rbp+57h+string]; string
0x180049f10  call    cs:__imp_WindowsGetStringRawBuffer
0x180049f17  nop     dword ptr [rax+rax+00h]
0x180049f1c  mov     [rbp+57h+var_68], rax
0x180049f20  xor     edx, edx; length
0x180049f22  mov     rcx, [rbp+57h+var_C8]; string
0x180049f26  call    cs:__imp_WindowsGetStringRawBuffer
0x180049f2d  nop     dword ptr [rax+rax+00h]
0x180049f32  mov     [rbp+57h+var_60], rax
0x180049f36  lea     rax, [rbp+57h+var_98]
0x180049f3a  mov     qword ptr [rsp+100h+var_D8], rax
0x180049f3f  lea     rax, [rbp+57h+var_78]
0x180049f43  mov     qword ptr [rsp+100h+var_E0], rax; int
0x180049f48  lea     r9, [rbp+57h+var_70]
0x180049f4c  lea     r8, [rbp+57h+var_68]
0x180049f50  lea     rdx, [rbp+57h+var_60]
0x180049f54  lea     rcx, [rbp+57h+var_A8]
0x180049f58  call    ??$Make@VPopupWindowExtendedStringContentImpl@Internal@Windows@@PEBGPEBGPEBGPEBGPEBG@Details@WRL@Microsoft@@YA?AV?$ComPtr@VPopupWindowExtendedStringContentImpl@Internal@Windows@@@12@$$QEAPEBG0000@Z; Microsoft::WRL::Details::Make<Windows::Internal::PopupWindowExtendedStringContentImpl,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *>(ushort const * &&,ushort const * &&,ushort const * &&,ushort const * &&,ushort const * &&)
0x180049f5d  mov     rbx, [rax]
0x180049f60  mov     [rbp+57h+var_98], rbx
0x180049f64  mov     [rax], r15
0x180049f67  mov     rcx, [rbp+57h+var_A8]
0x180049f6b  test    rcx, rcx
0x180049f6e  jz      short loc_180049F81
0x180049f70  mov     [rbp+57h+var_A8], r15
0x180049f74  mov     rax, [rcx]
0x180049f77  mov     rax, [rax+10h]
0x180049f7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049f80  nop
0x180049f81  test    rbx, rbx
0x180049f84  jnz     loc_18004A013
0x180049f8a  mov     rcx, [rbp+5Fh]; this
0x180049f8e  mov     ebx, 8007000Eh
0x180049f93  mov     r9d, ebx; char *
0x180049f96  mov     r8, rdi; unsigned int
0x180049f99  mov     edx, 150h; void *
0x180049f9e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180049fa3  lea     rcx, [rbp+57h+var_98]
0x180049fa7  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x180049fac  nop
0x180049fad  mov     rcx, [rbp+57h+var_C0]; string
0x180049fb1  call    cs:__imp_WindowsDeleteString
0x180049fb8  nop     dword ptr [rax+rax+00h]
0x180049fbd  mov     [rbp+57h+var_C0], r15
0x180049fc1  mov     rcx, [rbp+57h+var_B8]; string
0x180049fc5  call    cs:__imp_WindowsDeleteString
0x180049fcc  nop     dword ptr [rax+rax+00h]
0x180049fd1  mov     [rbp+57h+var_B8], r15
0x180049fd5  mov     rcx, [rbp+57h+var_B0]; string
0x180049fd9  call    cs:__imp_WindowsDeleteString
0x180049fe0  nop     dword ptr [rax+rax+00h]
0x180049fe5  mov     [rbp+57h+var_B0], r15
0x180049fe9  mov     rcx, [rbp+57h+string]; string
0x180049fed  call    cs:__imp_WindowsDeleteString
0x180049ff4  nop     dword ptr [rax+rax+00h]
0x180049ff9  mov     [rbp+57h+string], r15
0x180049ffd  mov     rcx, [rbp+57h+var_C8]; string
0x18004a001  call    cs:__imp_WindowsDeleteString
0x18004a008  nop     dword ptr [rax+rax+00h]
0x18004a00d  mov     [rbp+57h+var_C8], r15
0x18004a011  jmp     short loc_18004A092
0x18004a013  mov     rax, [rbx]
0x18004a016  mov     rcx, rbx
0x18004a019  mov     rax, [rax+8]
0x18004a01d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a022  mov     [rsi], rbx
0x18004a025  lea     rcx, [rbp+57h+var_98]
  ... truncated ...
```
