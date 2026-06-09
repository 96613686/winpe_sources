# Windows::Internal::UI::WindowsTip::SetToastActions(Windows::Data::Xml::Dom::IXmlDocument *,Windows::Internal::UI::SoftLanding::SOFTLANDING_BUTTON const &,Windows::Internal::UI::SoftLanding::SOFTLANDING_BUTTON const &,Windows::Internal::UI::SoftLanding::SOFTLANDING_NOTIFICATION const &,HSTRING__ *,HSTRING__ *,HSTRING__ *)

- ea: `0x180322818`
- end: `0x180322f43`
- name: `?SetToastActions@WindowsTip@UI@Internal@Windows@@YAJPEAUIXmlDocument@Dom@Xml@Data@4@AEBUSOFTLANDING_BUTTON@SoftLanding@234@1AEBUSOFTLANDING_NOTIFICATION@SoftLanding@234@PEAUHSTRING__@@33@Z`
- size: `1835`
- prototype: `__int64 __fastcall(Windows::Internal::UI::WindowsTip *__hidden this, struct Windows::Data::Xml::Dom::IXmlDocument *, const struct Windows::Internal::UI::SoftLanding::SOFTLANDING_BUTTON *, const struct Windows::Internal::UI::SoftLanding::SOFTLANDING_BUTTON *, const struct Windows::Internal::UI::SoftLanding::SOFTLANDING_NOTIFICATION *, HSTRING, HSTRING, HSTRING)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180325504`

## callees

- `0x18000b7e8`
- `0x18000c350`
- `0x18003c5e4`
- `0x1801000a4`
- `0x18013d330`
- `0x18021bfe4`
- `0x18021c1cc`
- `0x180312c00`
- `0x18031d14c`
- `0x180322818`
- `0x1803a3010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180322b8d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180322bda`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180322c9d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180322e3f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180322e74`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180322b8d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180322bda`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180322c9d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180322e3f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180322e74`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180322ba2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180322ba2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180322b64`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180322b72`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180322caf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180322cbd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180322ccd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180322b64`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180322b72`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180322caf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180322cbd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180322ccd`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall Windows::Internal::UI::WindowsTip::SetToastActions(
        __int64 (__fastcall ***this)(Windows::Internal::UI::WindowsTip *, GUID *, __int64 *),
        struct Windows::Data::Xml::Dom::IXmlDocument *a2,
        const struct Windows::Internal::UI::SoftLanding::SOFTLANDING_BUTTON *a3,
        const struct Windows::Internal::UI::SoftLanding::SOFTLANDING_BUTTON *a4,
        const struct Windows::Internal::UI::SoftLanding::SOFTLANDING_NOTIFICATION *a5,
        HSTRING a6,
        HSTRING a7)
{
  __int64 (__fastcall *v11)(Windows::Internal::UI::WindowsTip *, GUID *, __int64 *); // rbx
  int v12; // eax
  unsigned int v13; // ebx
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, __int64, __int64 *); // rbx
  int v16; // eax
  __int64 (__fastcall *v17)(Windows::Internal::UI::WindowsTip *, __int64, __int64 *); // rbx
  int v18; // eax
  int v19; // eax
  HSTRING *v20; // r15
  HSTRING v21; // r13
  __int64 (__fastcall *v22)(Windows::Internal::UI::WindowsTip *, __int64, __int64 *); // rbx
  int v23; // eax
  __int64 v24; // rdx
  __int64 v25; // rsi
  __int64 (__fastcall *v26)(__int64, __int64, __int64); // rdi
  __int64 v27; // rbx
  PCWSTR StringRawBuffer; // rbx
  PCWSTR v29; // rax
  HRESULT v30; // eax
  unsigned int v31; // ebx
  __int64 v33; // rsi
  __int64 (__fastcall *v34)(__int64, __int64, HSTRING); // rdi
  HSTRING v35; // rbx
  int ActionString; // eax
  __int64 v37; // rdx
  const unsigned __int16 *v38; // rdi
  const unsigned __int16 *v39; // rbx
  Windows::Internal::UI::WindowsTip *v40; // rax
  __int64 v41; // rsi
  __int64 (__fastcall *v42)(__int64, __int64, __int64); // rdi
  __int64 v43; // rbx
  int v44; // eax
  __int64 v45; // rdi
  __int64 (__fastcall *v46)(__int64, __int64, HSTRING *); // rbx
  int v47; // eax
  __int64 v48; // rdi
  __int64 (__fastcall *v49)(__int64, __int64, __int64 *); // rbx
  int v50; // eax
  HSTRING newString; // [rsp+20h] [rbp-F8h] BYREF
  __int64 v52; // [rsp+28h] [rbp-F0h] BYREF
  __int64 v53; // [rsp+30h] [rbp-E8h] BYREF
  __int64 v54; // [rsp+38h] [rbp-E0h] BYREF
  __int64 v55; // [rsp+40h] [rbp-D8h] BYREF
  HSTRING v56; // [rsp+48h] [rbp-D0h] BYREF
  __int64 v57; // [rsp+50h] [rbp-C8h] BYREF
  HSTRING string; // [rsp+58h] [rbp-C0h] BYREF
  __int64 v59; // [rsp+60h] [rbp-B8h] BYREF
  __int64 v60; // [rsp+68h] [rbp-B0h] BYREF
  HSTRING v61; // [rsp+70h] [rbp-A8h]
  HSTRING v62; // [rsp+78h] [rbp-A0h]
  _QWORD v63[3]; // [rsp+80h] [rbp-98h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+98h] [rbp-80h] BYREF
  __int64 v65; // [rsp+B0h] [rbp-68h]
  HSTRING_HEADER v66; // [rsp+B8h] [rbp-60h] BYREF
  __int64 v67; // [rsp+D0h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+0h]

  v62 = (HSTRING)a5;
  v61 = a6;
  string = a7;
  v57 = 0;
  v11 = **this;
  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v57);
  v12 = v11((Windows::Internal::UI::WindowsTip *)this, &GUID_63dbba8b_d0db_4fe1_b745_f9433afdc25b, &v57);
  v13 = v12;
  if ( v12 >= 0 )
  {
    v53 = 0;
    v14 = v57;
    v15 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v57 + 48LL);
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v53);
    v65 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"/toast", 7u, 6u);
    v16 = v15(v14, v65, &v53);
    v13 = v16;
    if ( v16 >= 0 )
    {
      v54 = 0;
      v17 = (__int64 (__fastcall *)(Windows::Internal::UI::WindowsTip *, __int64, __int64 *))(*this)[9];
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v54);
      v65 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"actions", 8u, 7u);
      v18 = v17((Windows::Internal::UI::WindowsTip *)this, v65, &v54);
      v13 = v18;
      if ( v18 >= 0 )
      {
        v55 = 0;
        v19 = Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlElement>::As<Windows::Data::Xml::Dom::IXmlNode>(
                &v54,
                &v55);
        v13 = v19;
        if ( v19 >= 0 )
        {
          v63[0] = *((_QWORD *)a4 + 4);
          v63[1] = *((_QWORD *)a2 + 1);
          v63[2] = *((_QWORD *)a3 + 1);
          v20 = (HSTRING *)v63;
          v21 = string;
          while ( v20 != (HSTRING *)&hstringHeader )
          {
            v52 = 0;
            v22 = (__int64 (__fastcall *)(Windows::Internal::UI::WindowsTip *, __int64, __int64 *))(*this)[9];
            Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v52);
            v65 = 0;
            Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"action", 7u, 6u);
            v23 = v22((Windows::Internal::UI::WindowsTip *)this, v65, &v52);
            v13 = v23;
            if ( v23 < 0 )
            {
              v24 = 194;
LABEL_15:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v24,
                (unsigned int)"shell\\twinui\\softlanding\\lib\\windowstippresenter.cpp",
                (const char *)(unsigned int)v23,
                (int)newString);
              goto LABEL_34;
            }
            v25 = v52;
            v26 = *(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v52 + 64LL);
            v65 = 0;
            Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"foreground", 0xBu, 0xAu);
            v27 = v65;
            v67 = 0;
            Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v66, L"activationType", 0xFu, 0xEu);
            v23 = v26(v25, v67, v27);
            v13 = v23;
            if ( v23 < 0 )
            {
              v24 = 195;
              goto LABEL_15;
            }
            newString = 0;
            if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SoftLandingV2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SoftLandingV2>::GetImpl'::`2'::impl) )
            {
              StringRawBuffer = WindowsGetStringRawBuffer(*v20, 0);
              v29 = WindowsGetStringRawBuffer(v21, 0);
              try
              {
                Windows::Internal::UI::WindowsTip::SoftLandingV2Helper::CreateActionString(&v56, v29, StringRawBuffer);
                WindowsDeleteString(newString);
                newString = 0;
                v30 = WindowsDuplicateString(v56, &newString);
              }
              catch ( ... )
              {
                LODWORD(v56) = *(_DWORD *)winrt::to_hresult(&v56);
                v13 = (unsigned int)v56;
                goto LABEL_33;
              }
              v31 = v30;
              if ( v30 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0xCD,
                  (unsigned int)"shell\\twinui\\softlanding\\lib\\windowstippresenter.cpp",
                  (const char *)(unsigned int)v30,
                  (int)newString);
                winrt::handle_type<winrt::impl::hstring_traits>::close(&v56);
                WindowsDeleteString(newString);
                newString = 0;
                Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v52);
                Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v55);
                Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v54);
                Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v53);
                Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v57);
                return v31;
              }
              winrt::handle_type<winrt::impl::hstring_traits>::close(&v56);
            }
            else
            {
              WindowsDeleteString(newString);
              newString = 0;
              v38 = WindowsGetStringRawBuffer(v61, 0);
              v39 = WindowsGetStringRawBuffer(*v20, 0);
              v40 = (Windows::Internal::UI::WindowsTip *)WindowsGetStringRawBuffer(v62, 0);
              ActionString = Windows::Internal::UI::WindowsTip::CreateActionString(
                               v40,
                               v39,
                               v38,
                               (const unsigned __int16 *)&newString,
                               (HSTRING *)newString);
              v13 = ActionString;
              if ( ActionString < 0 )
              {
                v37 = 218;
                goto LABEL_25;
              }
            }
            v33 = v52;
            v34 = *(__int64 (__fastcall **)(__int64, __int64, HSTRING))(*(_QWORD *)v52 + 64LL);
            v35 = newString;
            v67 = 0;
            Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v66, L"arguments", 0xAu, 9u);
            ActionString = v34(v33, v67, v35);
            v13 = ActionString;
            if ( ActionString < 0 )
            {
              v37 = 221;
LABEL_25:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v37,
                (unsigned int)"shell\\twinui\\softlanding\\lib\\windowstippresenter.cpp",
                (const char *)(unsigned int)ActionString,
                (int)newString);
              goto LABEL_33;
            }
            v41 = v52;
            v42 = *(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v52 + 64LL);
            v67 = 0;
            Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v66, &pszDefault, 1u, 0);
            v43 = v67;
            v65 = 0;
            Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"content", 8u, 7u);
            ActionString = v42(v41, v65, v43);
            v13 = ActionString;
            if ( ActionString < 0 )
            {
              v37 = 222;
              goto LABEL_25;
            }
            v59 = 0;
            v44 = Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlElement>::As<Windows::Data::Xml::Dom::IXmlNode>(
                    &v52,
                    &v59);
            v13 = v44;
            if ( v44 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xE1,
                (unsigned int)"shell\\twinui\\softlanding\\lib\\windowstippresenter.cpp",
                (const char *)(unsigned int)v44,
                (int)newString);
              goto LABEL_32;
            }
            string = 0;
            v45 = v55;
            v46 = *(__int64 (__fastcall **)(__int64, __int64, HSTRING *))(*(_QWORD *)v55 + 176LL);
            Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&string);
            v47 = v46(v45, v59, &string);
            v13 = v47;
            if ( v47 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xE4,
                (unsigned int)"shell\\twinui\\softlanding\\lib\\windowstippresenter.cpp",
                (const char *)(unsigned int)v47,
                (int)newString);
              Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&string);
LABEL_32:
              Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v59);
LABEL_33:
              WindowsDeleteString(newString);
              newString = 0;
LABEL_34:
              Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v52);
              goto LABEL_39;
            }
            Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&string);
            Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v59);
            WindowsDeleteString(newString);
            newString = 0;
            Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v52);
            ++v20;
          }
          v60 = 0;
          v48 = v53;
          v49 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v53 + 176LL);
          Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v60);
          v50 = v49(v48, v55, &v60);
          v13 = v50;
          if ( v50 < 0 )
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xE8,
              (unsigned int)"shell\\twinui\\softlanding\\lib\\windowstippresenter.cpp",
              (const char *)(unsigned int)v50,
              (int)newString);
          Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v60);
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xBB,
            (unsigned int)"shell\\twinui\\softlanding\\lib\\windowstippresenter.cpp",
            (const char *)(unsigned int)v19,
            (int)newString);
        }
LABEL_39:
        Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v55);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xB8,
          (unsigned int)"shell\\twinui\\softlanding\\lib\\windowstippresenter.cpp",
          (const char *)(unsigned int)v18,
          (int)newString);
      }
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v54);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB5,
        (unsigned int)"shell\\twinui\\softlanding\\lib\\windowstippresenter.cpp",
        (const char *)(unsigned int)v16,
        (int)newString);
    }
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v53);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB2,
      (unsigned int)"shell\\twinui\\softlanding\\lib\\windowstippresenter.cpp",
      (const char *)(unsigned int)v12,
      (int)newString);
  }
  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v57);
  return v13;
}

```

## disassembly

```asm
0x180322818  push    rbx
0x18032281a  push    rsi
0x18032281b  push    rdi
0x18032281c  push    r12
0x18032281e  push    r13
0x180322820  push    r14
0x180322822  push    r15
0x180322824  sub     rsp, 0E0h
0x18032282b  mov     rax, cs:__security_cookie
0x180322832  xor     rax, rsp
0x180322835  mov     [rsp+118h+var_40], rax
0x18032283d  mov     r13, r9
0x180322840  mov     r15, r8
0x180322843  mov     rsi, rdx
0x180322846  mov     r12, rcx
0x180322849  mov     rax, [rsp+118h+arg_20]
0x180322851  mov     [rsp+118h+var_A0], rax
0x180322856  mov     rax, [rsp+118h+arg_28]
0x18032285e  mov     [rsp+118h+var_A8], rax
0x180322863  mov     rax, [rsp+118h+arg_30]
0x18032286b  mov     [rsp+118h+string], rax
0x180322870  xor     r14d, r14d
0x180322873  mov     [rsp+118h+var_C8], r14
0x180322878  mov     rax, [rcx]
0x18032287b  mov     rbx, [rax]
0x18032287e  lea     rcx, [rsp+118h+var_C8]
0x180322883  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x180322888  lea     r8, [rsp+118h+var_C8]
0x18032288d  lea     rdx, _GUID_63dbba8b_d0db_4fe1_b745_f9433afdc25b
0x180322894  mov     rcx, r12
0x180322897  mov     rax, rbx
0x18032289a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18032289f  mov     ebx, eax
0x1803228a1  test    eax, eax
0x1803228a3  jns     short loc_1803228C6
0x1803228a5  mov     rcx, [rsp+118h]; this
0x1803228ad  mov     r9d, eax; char *
0x1803228b0  lea     r8, aShellTwinuiSof_9; "shell\\twinui\\softlanding\\lib\\window"...
0x1803228b7  mov     edx, 0B2h; void *
0x1803228bc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1803228c1  jmp     loc_180322F14
0x1803228c6  mov     [rsp+118h+var_E8], r14
0x1803228cb  mov     rdi, [rsp+118h+var_C8]
0x1803228d0  mov     rax, [rdi]
0x1803228d3  mov     rbx, [rax+30h]
0x1803228d7  lea     rcx, [rsp+118h+var_E8]
0x1803228dc  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1803228e1  mov     [rsp+118h+var_68], r14
0x1803228e9  mov     r9d, 6; unsigned int
0x1803228ef  lea     r8d, [r9+1]; unsigned int
0x1803228f3  lea     rdx, aToast; "/toast"
0x1803228fa  lea     rcx, [rsp+118h+hstringHeader]; hstringHeader
0x180322902  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180322907  nop
0x180322908  lea     r8, [rsp+118h+var_E8]
0x18032290d  mov     rdx, [rsp+118h+var_68]
0x180322915  mov     rcx, rdi
0x180322918  mov     rax, rbx
0x18032291b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180322920  mov     ebx, eax
0x180322922  test    eax, eax
0x180322924  jns     short loc_180322947
0x180322926  mov     rcx, [rsp+118h]; this
0x18032292e  mov     r9d, eax; char *
0x180322931  lea     r8, aShellTwinuiSof_9; "shell\\twinui\\softlanding\\lib\\window"...
0x180322938  mov     edx, 0B5h; void *
0x18032293d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180322942  jmp     loc_180322F09
0x180322947  mov     [rsp+118h+var_E0], r14
0x18032294c  mov     rax, [r12]
0x180322950  mov     rbx, [rax+48h]
0x180322954  lea     rcx, [rsp+118h+var_E0]
0x180322959  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18032295e  mov     [rsp+118h+var_68], r14
0x180322966  mov     r9d, 7; unsigned int
0x18032296c  lea     r8d, [r9+1]; unsigned int
0x180322970  lea     rdx, aActions_0; "actions"
0x180322977  lea     rcx, [rsp+118h+hstringHeader]; hstringHeader
0x18032297f  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180322984  nop
0x180322985  lea     r8, [rsp+118h+var_E0]
0x18032298a  mov     rdx, [rsp+118h+var_68]
0x180322992  mov     rcx, r12
0x180322995  mov     rax, rbx
0x180322998  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18032299d  mov     ebx, eax
0x18032299f  test    eax, eax
0x1803229a1  jns     short loc_1803229C4
0x1803229a3  mov     rcx, [rsp+118h]; this
0x1803229ab  mov     r9d, eax; char *
0x1803229ae  lea     r8, aShellTwinuiSof_9; "shell\\twinui\\softlanding\\lib\\window"...
0x1803229b5  mov     edx, 0B8h; void *
0x1803229ba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1803229bf  jmp     loc_180322EFE
0x1803229c4  mov     [rsp+118h+var_D8], r14
0x1803229c9  lea     rdx, [rsp+118h+var_D8]
0x1803229ce  lea     rcx, [rsp+118h+var_E0]
0x1803229d3  call    ??$As@UIXmlNode@Dom@Xml@Data@Windows@@@?$ComPtr@UIXmlElement@Dom@Xml@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIXmlNode@Dom@Xml@Data@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlElement>::As<Windows::Data::Xml::Dom::IXmlNode>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlNode>>)
0x1803229d8  mov     ebx, eax
0x1803229da  test    eax, eax
0x1803229dc  jns     short loc_1803229FF
0x1803229de  mov     rcx, [rsp+118h]; this
0x1803229e6  mov     r9d, eax; char *
0x1803229e9  lea     r8, aShellTwinuiSof_9; "shell\\twinui\\softlanding\\lib\\window"...
0x1803229f0  mov     edx, 0BBh; void *
0x1803229f5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1803229fa  jmp     loc_180322EF3
0x1803229ff  mov     rax, [r13+20h]
0x180322a03  mov     [rsp+118h+var_98], rax
0x180322a0b  mov     rax, [rsi+8]
0x180322a0f  mov     [rsp+118h+var_90], rax
0x180322a17  mov     rax, [r15+8]
0x180322a1b  mov     [rsp+118h+var_88], rax
0x180322a23  lea     r15, [rsp+118h+var_98]
0x180322a2b  mov     r13, [rsp+118h+string]
0x180322a30  lea     rax, [rsp+118h+hstringHeader]
0x180322a38  cmp     r15, rax
0x180322a3b  jz      loc_180322E92
0x180322a41  mov     [rsp+118h+var_F0], r14
0x180322a46  mov     rax, [r12]
0x180322a4a  mov     rbx, [rax+48h]
0x180322a4e  lea     rcx, [rsp+118h+var_F0]
0x180322a53  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x180322a58  mov     [rsp+118h+var_68], r14
0x180322a60  mov     r9d, 6; unsigned int
0x180322a66  lea     r8d, [r9+1]; unsigned int
0x180322a6a  lea     rdx, aAction; "action"
0x180322a71  lea     rcx, [rsp+118h+hstringHeader]; hstringHeader
0x180322a79  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180322a7e  nop
0x180322a7f  lea     r8, [rsp+118h+var_F0]
0x180322a84  mov     rdx, [rsp+118h+var_68]
0x180322a8c  mov     rcx, r12
0x180322a8f  mov     rax, rbx
0x180322a92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180322a97  mov     ebx, eax
0x180322a99  test    eax, eax
0x180322a9b  jns     short loc_180322AA7
0x180322a9d  mov     edx, 0C2h
0x180322aa2  jmp     loc_180322B2A
0x180322aa7  mov     rsi, [rsp+118h+var_F0]
0x180322aac  mov     rax, [rsi]
0x180322aaf  mov     rdi, [rax+40h]
0x180322ab3  mov     [rsp+118h+var_68], r14
0x180322abb  mov     r9d, 0Ah; unsigned int
0x180322ac1  lea     r8d, [r9+1]; unsigned int
0x180322ac5  lea     rdx, aForeground; "foreground"
0x180322acc  lea     rcx, [rsp+118h+hstringHeader]; hstringHeader
0x180322ad4  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180322ad9  nop
0x180322ada  mov     rbx, [rsp+118h+var_68]
0x180322ae2  mov     [rsp+118h+var_48], r14
0x180322aea  mov     r9d, 0Eh; unsigned int
0x180322af0  lea     r8d, [r9+1]; unsigned int
0x180322af4  lea     rdx, aActivationtype; "activationType"
0x180322afb  lea     rcx, [rsp+118h+var_60]; hstringHeader
0x180322b03  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180322b08  nop
0x180322b09  mov     r8, rbx
0x180322b0c  mov     rdx, [rsp+118h+var_48]
0x180322b14  mov     rcx, rsi
0x180322b17  mov     rax, rdi
0x180322b1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180322b1f  mov     ebx, eax
0x180322b21  test    eax, eax
0x180322b23  jns     short loc_180322B46
0x180322b25  mov     edx, 0C3h; void *
0x180322b2a  mov     r9d, eax; char *
0x180322b2d  lea     r8, aShellTwinuiSof_9; "shell\\twinui\\softlanding\\lib\\window"...
0x180322b34  mov     rcx, [rsp+118h]; this
0x180322b3c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180322b41  jmp     loc_180322E4A
0x180322b46  mov     [rsp+118h+newString], r14
0x180322b4b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SoftLandingV2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SoftLandingV2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SoftLandingV2> `wil::Feature<__WilFeatureTraits_Feature_SoftLandingV2>::GetImpl(void)'::`2'::impl
0x180322b52  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SoftLandingV2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SoftLandingV2>::__private_IsEnabled(void)
0x180322b57  test    al, al
0x180322b59  jz      loc_180322C98
0x180322b5f  xor     edx, edx; length
0x180322b61  mov     rcx, [r15]; string
0x180322b64  call    cs:__imp_WindowsGetStringRawBuffer
0x180322b6a  mov     rbx, rax
0x180322b6d  xor     edx, edx; length
0x180322b6f  mov     rcx, r13; string
0x180322b72  call    cs:__imp_WindowsGetStringRawBuffer
0x180322b78  mov     r8, rbx
0x180322b7b  mov     rdx, rax
0x180322b7e  lea     rcx, [rsp+118h+var_D0]
0x180322b83  call    ?CreateActionString@SoftLandingV2Helper@WindowsTip@UI@Internal@Windows@@SA?AUhstring@winrt@@PEBG0@Z; Windows::Internal::UI::WindowsTip::SoftLandingV2Helper::CreateActionString(ushort const *,ushort const *)
0x180322b88  mov     rcx, [rsp+118h+newString]; string
0x180322b8d  call    cs:__imp_WindowsDeleteString
0x180322b93  mov     [rsp+118h+newString], r14; int
0x180322b98  lea     rdx, [rsp+118h+newString]; newString
0x180322b9d  mov     rcx, [rsp+118h+var_D0]; string
0x180322ba2  call    cs:__imp_WindowsDuplicateString
0x180322ba8  mov     ebx, eax
0x180322baa  test    eax, eax
0x180322bac  jns     short loc_180322C22
0x180322bae  mov     rcx, [rsp+118h]; this
0x180322bb6  mov     r9d, eax; char *
0x180322bb9  lea     r8, aShellTwinuiSof_9; "shell\\twinui\\softlanding\\lib\\window"...
0x180322bc0  mov     edx, 0CDh; void *
0x180322bc5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180322bca  lea     rcx, [rsp+118h+var_D0]
0x180322bcf  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180322bd4  nop
0x180322bd5  mov     rcx, [rsp+118h+newString]; string
0x180322bda  call    cs:__imp_WindowsDeleteString
0x180322be0  mov     [rsp+118h+newString], r14
0x180322be5  lea     rcx, [rsp+118h+var_F0]
0x180322bea  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x180322bef  nop
0x180322bf0  lea     rcx, [rsp+118h+var_D8]
0x180322bf5  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x180322bfa  nop
0x180322bfb  lea     rcx, [rsp+118h+var_E0]
0x180322c00  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x180322c05  nop
0x180322c06  lea     rcx, [rsp+118h+var_E8]
0x180322c0b  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x180322c10  nop
0x180322c11  lea     rcx, [rsp+118h+var_C8]
0x180322c16  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x180322c1b  mov     eax, ebx
0x180322c1d  jmp     loc_180322F20
0x180322c22  lea     rcx, [rsp+118h+var_D0]
0x180322c27  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180322c2c  nop
0x180322c2d  mov     rsi, [rsp+118h+var_F0]
0x180322c32  mov     rax, [rsi]
0x180322c35  mov     rdi, [rax+40h]
0x180322c39  mov     rbx, [rsp+118h+newString]
0x180322c3e  mov     [rsp+118h+var_48], r14
0x180322c46  mov     r9d, 9; unsigned int
0x180322c4c  lea     r8d, [r9+1]; unsigned int
0x180322c50  lea     rdx, aArguments; "arguments"
0x180322c57  lea     rcx, [rsp+118h+var_60]; hstringHeader
0x180322c5f  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180322c64  nop
0x180322c65  mov     r8, rbx
0x180322c68  mov     rdx, [rsp+118h+var_48]
0x180322c70  mov     rcx, rsi
0x180322c73  mov     rax, rdi
0x180322c76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180322c7b  mov     ebx, eax
0x180322c7d  test    eax, eax
0x180322c7f  jns     loc_180322D11
0x180322c85  mov     edx, 0DDh
0x180322c8a  jmp     short loc_180322CF5
0x180322c8c  mov     ebx, dword ptr [rsp+118h+var_D0]
0x180322c90  xor     r14d, r14d
0x180322c93  jmp     loc_180322E3A
0x180322c98  mov     rcx, [rsp+118h+newString]; string
0x180322c9d  call    cs:__imp_WindowsDeleteString
0x180322ca3  mov     [rsp+118h+newString], r14; int
0x180322ca8  xor     edx, edx; length
0x180322caa  mov     rcx, [rsp+118h+var_A8]; string
0x180322caf  call    cs:__imp_WindowsGetStringRawBuffer
0x180322cb5  mov     rdi, rax
0x180322cb8  xor     edx, edx; length
0x180322cba  mov     rcx, [r15]; string
0x180322cbd  call    cs:__imp_WindowsGetStringRawBuffer
0x180322cc3  mov     rbx, rax
0x180322cc6  xor     edx, edx; length
0x180322cc8  mov     rcx, [rsp+118h+var_A0]; string
0x180322ccd  call    cs:__imp_WindowsGetStringRawBuffer
0x180322cd3  lea     r9, [rsp+118h+newString]; unsigned __int16 *
0x180322cd8  mov     r8, rdi; unsigned __int16 *
0x180322cdb  mov     rdx, rbx; unsigned __int16 *
0x180322cde  mov     rcx, rax; this
0x180322ce1  call    ?CreateActionString@WindowsTip@UI@Internal@Windows@@YAJPEBG00PEAPEAUHSTRING__@@@Z; Windows::Internal::UI::WindowsTip::CreateActionString(ushort const *,ushort const *,ushort const *,HSTRING__ * *)
0x180322ce6  mov     ebx, eax
0x180322ce8  test    eax, eax
0x180322cea  jns     loc_180322C2D
0x180322cf0  mov     edx, 0DAh; void *
0x180322cf5  mov     rcx, [rsp+118h]; this
0x180322cfd  mov     r9d, eax; char *
0x180322d00  lea     r8, aShellTwinuiSof_9; "shell\\twinui\\softlanding\\lib\\window"...
0x180322d07  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180322d0c  jmp     loc_180322E3A
0x180322d11  mov     rsi, [rsp+118h+var_F0]
0x180322d16  mov     rax, [rsi]
0x180322d19  mov     rdi, [rax+40h]
0x180322d1d  mov     [rsp+118h+var_48], r14
0x180322d25  xor     r9d, r9d; unsigned int
0x180322d28  lea     r8d, [r9+1]; unsigned int
0x180322d2c  lea     rdx, pszDefault; sourceString
0x180322d33  lea     rcx, [rsp+118h+var_60]; hstringHeader
0x180322d3b  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180322d40  nop
0x180322d41  mov     rbx, [rsp+118h+var_48]
0x180322d49  mov     [rsp+118h+var_68], r14
0x180322d51  mov     r9d, 7; unsigned int
0x180322d57  lea     r8d, [r9+1]; unsigned int
0x180322d5b  lea     rdx, aContent; "content"
0x180322d62  lea     rcx, [rsp+118h+hstringHeader]; hstringHeader
0x180322d6a  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180322d6f  nop
0x180322d70  mov     r8, rbx
0x180322d73  mov     rdx, [rsp+118h+var_68]
0x180322d7b  mov     rcx, rsi
  ... truncated ...
```
