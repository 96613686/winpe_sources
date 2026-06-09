# Windows::Internal::UI::WindowsTip::UpdateToastTemplateWithDataForGuidedTours(Windows::Data::Xml::Dom::IXmlDocument *,Windows::Internal::UI::WindowsTip::CreativeVisualDataForGuidedTours &,HSTRING__ *)

- ea: `0x180325be4`
- end: `0x1803261b5`
- name: `?UpdateToastTemplateWithDataForGuidedTours@WindowsTip@UI@Internal@Windows@@YAJPEAUIXmlDocument@Dom@Xml@Data@4@AEAUCreativeVisualDataForGuidedTours@1234@PEAUHSTRING__@@@Z`
- size: `1489`
- prototype: `__int64 __fastcall(Windows::Internal::UI::WindowsTip *__hidden this, struct Windows::Data::Xml::Dom::IXmlDocument *, struct Windows::Internal::UI::WindowsTip::CreativeVisualDataForGuidedTours *, HSTRING)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18031d390`

## callees

- `0x18000b7e8`
- `0x18000c350`
- `0x18003c5e4`
- `0x18003c898`
- `0x180052980`
- `0x1801321ac`
- `0x18013d330`
- `0x18021c11c`
- `0x18021c1cc`
- `0x180312c00`
- `0x18031d200`
- `0x18032251c`
- `0x180322f4c`
- `0x18032355c`
- `0x1803239b8`
- `0x180325be4`
- `0x1803a3010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180325fc0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18032600d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180326165`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803261a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180325fc0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18032600d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180326165`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803261a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180325fd5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180325fd5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180325fa5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180326123`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180325fa5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180326123`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall Windows::Internal::UI::WindowsTip::UpdateToastTemplateWithDataForGuidedTours(
        Windows::Internal::UI::WindowsTip *this,
        struct Windows::Data::Xml::Dom::IXmlDocument *a2,
        struct Windows::Internal::UI::WindowsTip::CreativeVisualDataForGuidedTours *a3,
        HSTRING a4)
{
  struct Windows::Internal::UI::WindowsTip::CreativeVisualDataForGuidedTours *v4; // r14
  unsigned __int16 *v7; // r13
  __int64 v8; // r8
  __int64 v9; // r8
  unsigned __int16 *v10; // rdi
  __int64 v11; // r8
  struct Windows::Data::Xml::Dom::IXmlDocument *v12; // rdx
  int v13; // eax
  unsigned int v14; // ebx
  __int64 (__fastcall *v15)(Windows::Internal::UI::WindowsTip *, __int64, __int64 *); // rbx
  int v16; // eax
  __int64 v17; // rdx
  int v18; // eax
  __int64 v19; // rdi
  __int64 (__fastcall *v20)(__int64, _QWORD, HSTRING *); // rbx
  int appended; // eax
  __int64 v22; // rdx
  unsigned int v23; // r14d
  int v24; // eax
  HSTRING v25; // rbx
  __int64 v26; // rax
  struct Windows::Data::Xml::Dom::IXmlNode *v27; // r8
  struct Windows::Data::Xml::Dom::IXmlNode **v28; // r9
  __int64 v29; // rdi
  __int64 (__fastcall *v30)(__int64, _QWORD, HSTRING *); // rbx
  int v31; // eax
  int v32; // eax
  unsigned __int16 *v33; // r9
  HSTRING v34; // rbx
  __int64 v35; // rax
  struct Windows::Data::Xml::Dom::IXmlNode *v36; // r8
  struct Windows::Data::Xml::Dom::IXmlNode **v37; // r9
  const unsigned __int16 *v38; // rbx
  PCWSTR StringRawBuffer; // rax
  HRESULT v40; // eax
  unsigned int v41; // ebx
  __int64 (__fastcall *v43)(Windows::Internal::UI::WindowsTip *, GUID *, unsigned __int64 *); // rbx
  int v44; // eax
  unsigned __int64 v45; // rdi
  __int64 (__fastcall *v46)(unsigned __int64, __int64, Windows::Internal::UI::WindowsTip **); // rbx
  int v47; // eax
  __int64 v48; // rdx
  const unsigned __int16 *v49; // rax
  const unsigned __int16 *v50; // r9
  HSTRING v51; // [rsp+20h] [rbp-A8h] BYREF
  unsigned __int64 v52; // [rsp+28h] [rbp-A0h] BYREF
  HSTRING string; // [rsp+30h] [rbp-98h] BYREF
  Windows::Internal::UI::WindowsTip *v54; // [rsp+38h] [rbp-90h] BYREF
  __int64 v55; // [rsp+40h] [rbp-88h] BYREF
  unsigned int v56; // [rsp+48h] [rbp-80h] BYREF
  unsigned __int16 *v57; // [rsp+50h] [rbp-78h]
  struct Windows::Internal::UI::WindowsTip::CreativeVisualDataForGuidedTours *v58; // [rsp+58h] [rbp-70h]
  unsigned __int16 *v59; // [rsp+60h] [rbp-68h]
  HSTRING_HEADER hstringHeader; // [rsp+68h] [rbp-60h] BYREF
  __int64 v61; // [rsp+80h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  v4 = a3;
  v58 = a3;
  v7 = (unsigned __int16 *)winrt::hstring::c_str((winrt::hstring *)(*((_QWORD *)a2 + 9) + 8LL));
  string = (HSTRING)v7;
  v54 = (Windows::Internal::UI::WindowsTip *)winrt::hstring::c_str((winrt::hstring *)(v8 + 16));
  v10 = (unsigned __int16 *)winrt::hstring::c_str((winrt::hstring *)(v9 + 64));
  v57 = v10;
  v59 = (unsigned __int16 *)winrt::hstring::c_str((winrt::hstring *)(v11 + 96));
  v52 = 0;
  v56 = 0;
  v13 = Windows::Internal::UI::WindowsTip::SetToastTemplateToToastGeneric(this, v12);
  v14 = v13;
  if ( v13 >= 0 )
  {
    v55 = 0;
    v15 = *(__int64 (__fastcall **)(Windows::Internal::UI::WindowsTip *, __int64, __int64 *))(*(_QWORD *)this + 128LL);
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v55);
    v61 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"text", 5u, 4u);
    v16 = v15(this, v61, &v55);
    v14 = v16;
    if ( v16 < 0 )
    {
      v17 = 289;
LABEL_28:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v17,
        (unsigned int)"shell\\twinui\\softlanding\\lib\\windowstippresenter.cpp",
        (const char *)(unsigned int)v16,
        (int)v51);
      goto LABEL_49;
    }
    v18 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v55 + 48LL))(v55, &v56);
    if ( v18 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x122,
        (unsigned int)"shell\\twinui\\softlanding\\lib\\windowstippresenter.cpp",
        (const char *)(unsigned int)v18,
        (int)v51);
LABEL_23:
      v32 = StringCchLengthW(v10, 0x104u, &v52);
      if ( v32 >= 0 )
      {
        if ( v52 )
        {
          v16 = Windows::Internal::UI::WindowsTip::SetToastImageSrc(
                  this,
                  (struct Windows::Data::Xml::Dom::IXmlDocument *)v10,
                  v59,
                  v33);
          v14 = v16;
          if ( v16 < 0 )
          {
            v17 = 315;
            goto LABEL_28;
          }
        }
      }
      else
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x139,
          (unsigned int)"shell\\twinui\\softlanding\\lib\\windowstippresenter.cpp",
          (const char *)(unsigned int)v32,
          (int)v51);
      }
      if ( !*(_BYTE *)a2 )
      {
        v16 = Windows::Internal::UI::WindowsTip::SetToastActionsForGuidedTours(this, a2, v4, (HSTRING)v33);
        v14 = v16;
        if ( v16 < 0 )
        {
          v17 = 321;
          goto LABEL_28;
        }
        if ( *((_DWORD *)a2 + 2) <= 1u )
        {
          string = 0;
          v38 = winrt::hstring::c_str((struct Windows::Data::Xml::Dom::IXmlDocument *)((char *)a2 + 40));
          StringRawBuffer = WindowsGetStringRawBuffer((HSTRING)v4, 0);
          try
          {
            Windows::Internal::UI::WindowsTip::SoftLandingV2Helper::CreateActionString(&v51, StringRawBuffer, v38);
            WindowsDeleteString(string);
            string = 0;
            v40 = WindowsDuplicateString(v51, &string);
          }
          catch ( ... )
          {
            LODWORD(v51) = *(_DWORD *)winrt::to_hresult(&v51);
            v14 = (unsigned int)v51;
            goto LABEL_51;
          }
          v41 = v40;
          if ( v40 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x14B,
              (unsigned int)"shell\\twinui\\softlanding\\lib\\windowstippresenter.cpp",
              (const char *)(unsigned int)v40,
              (int)v51);
            winrt::handle_type<winrt::impl::hstring_traits>::close(&v51);
            WindowsDeleteString(string);
            string = 0;
            Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v55);
            return v41;
          }
          winrt::handle_type<winrt::impl::hstring_traits>::close(&v51);
          v52 = 0;
          v43 = **(__int64 (__fastcall ***)(Windows::Internal::UI::WindowsTip *, GUID *, unsigned __int64 *))this;
          Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v52);
          v44 = v43(this, &GUID_63dbba8b_d0db_4fe1_b745_f9433afdc25b, &v52);
          v14 = v44;
          if ( v44 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x154,
              (unsigned int)"shell\\twinui\\softlanding\\lib\\windowstippresenter.cpp",
              (const char *)(unsigned int)v44,
              (int)v51);
            goto LABEL_41;
          }
          v54 = 0;
          v45 = v52;
          v46 = *(__int64 (__fastcall **)(unsigned __int64, __int64, Windows::Internal::UI::WindowsTip **))(*(_QWORD *)v52 + 48LL);
          Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v54);
          v61 = 0;
          Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"toast", 6u, 5u);
          v47 = v46(v45, v61, &v54);
          v14 = v47;
          if ( v47 < 0 )
          {
            v48 = 342;
LABEL_44:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v48,
              (unsigned int)"shell\\twinui\\softlanding\\lib\\windowstippresenter.cpp",
              (const char *)(unsigned int)v47,
              (int)v51);
            Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v54);
LABEL_41:
            Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v52);
LABEL_51:
            WindowsDeleteString(string);
            string = 0;
            goto LABEL_49;
          }
          v49 = WindowsGetStringRawBuffer(string, 0);
          v47 = Windows::Internal::UI::WindowsTip::SetNodeAttribute(
                  v54,
                  (struct Windows::Data::Xml::Dom::IXmlNode *)L"launch",
                  v49,
                  v50);
          v14 = v47;
          if ( v47 < 0 )
          {
            v48 = 343;
            goto LABEL_44;
          }
          Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v54);
          Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v52);
          WindowsDeleteString(string);
        }
      }
      v14 = 0;
      goto LABEL_49;
    }
    if ( !v56 )
      goto LABEL_23;
    v51 = 0;
    v19 = v55;
    v20 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v55 + 56LL);
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v51);
    appended = v20(v19, 0, &v51);
    v14 = appended;
    if ( appended < 0 )
    {
      v22 = 294;
LABEL_10:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v22,
        (unsigned int)"shell\\twinui\\softlanding\\lib\\windowstippresenter.cpp",
        (const char *)(unsigned int)appended,
        (int)v51);
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v51);
LABEL_49:
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v55);
      return v14;
    }
    v23 = 0;
    v24 = StringCchLengthW(v7, 0x7FFFFFFFu, &v52);
    if ( v24 >= 0 )
    {
      if ( v52 )
      {
        v25 = v51;
        v26 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &string);
        appended = Windows::Internal::UI::WindowsTip::CreateAndAppendTextNode(
                     *(Windows::Internal::UI::WindowsTip **)(v26 + 24),
                     v25,
                     v27,
                     v28);
        v14 = appended;
        if ( appended < 0 )
        {
          v22 = 298;
          goto LABEL_10;
        }
        v23 = 1;
      }
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x128,
        (unsigned int)"shell\\twinui\\softlanding\\lib\\windowstippresenter.cpp",
        (const char *)(unsigned int)v24,
        (int)v51);
    }
    if ( v56 > v23 )
    {
      v29 = v55;
      v30 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v55 + 56LL);
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v51);
      appended = v30(v29, v23, &v51);
      v14 = appended;
      if ( appended < 0 )
      {
        v22 = 304;
        goto LABEL_10;
      }
      v31 = StringCchLengthW((const unsigned __int16 *)v54, 0x7FFFFFFFu, &v52);
      if ( v31 >= 0 )
      {
        if ( v52 )
        {
          v34 = v51;
          v35 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v54);
          appended = Windows::Internal::UI::WindowsTip::CreateAndAppendTextNode(
                       *(Windows::Internal::UI::WindowsTip **)(v35 + 24),
                       v34,
                       v36,
                       v37);
          v14 = appended;
          if ( appended < 0 )
          {
            v22 = 308;
            goto LABEL_10;
          }
        }
      }
      else
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x132,
          (unsigned int)"shell\\twinui\\softlanding\\lib\\windowstippresenter.cpp",
          (const char *)(unsigned int)v31,
          (int)v51);
      }
    }
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v51);
    v10 = v57;
    v4 = v58;
    goto LABEL_23;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x11E,
    (unsigned int)"shell\\twinui\\softlanding\\lib\\windowstippresenter.cpp",
    (const char *)(unsigned int)v13,
    (int)v51);
  return v14;
}

```

## disassembly

```asm
0x180325be4  push    rbx
0x180325be6  push    rsi
0x180325be7  push    rdi
0x180325be8  push    r12
0x180325bea  push    r13
0x180325bec  push    r14
0x180325bee  push    r15
0x180325bf0  sub     rsp, 90h
0x180325bf7  mov     rax, cs:__security_cookie
0x180325bfe  xor     rax, rsp
0x180325c01  mov     [rsp+0C8h+var_40], rax
0x180325c09  mov     r14, r8
0x180325c0c  mov     [rsp+0C8h+var_70], r8
0x180325c11  mov     r15, rdx
0x180325c14  mov     r12, rcx
0x180325c17  mov     r8, [rdx+48h]
0x180325c1b  lea     rcx, [r8+8]; this
0x180325c1f  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x180325c24  mov     r13, rax
0x180325c27  mov     [rsp+0C8h+string], rax
0x180325c2c  lea     rcx, [r8+10h]; this
0x180325c30  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x180325c35  mov     [rsp+0C8h+var_90], rax
0x180325c3a  lea     rcx, [r8+40h]; this
0x180325c3e  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x180325c43  mov     rdi, rax
0x180325c46  mov     [rsp+0C8h+var_78], rax
0x180325c4b  lea     rcx, [r8+60h]; this
0x180325c4f  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x180325c54  mov     [rsp+0C8h+var_68], rax
0x180325c59  xor     esi, esi
0x180325c5b  mov     [rsp+0C8h+var_A0], rsi
0x180325c60  mov     [rsp+0C8h+var_80], esi
0x180325c64  mov     rcx, r12; this
0x180325c67  call    ?SetToastTemplateToToastGeneric@WindowsTip@UI@Internal@Windows@@YAJPEAUIXmlDocument@Dom@Xml@Data@4@@Z; Windows::Internal::UI::WindowsTip::SetToastTemplateToToastGeneric(Windows::Data::Xml::Dom::IXmlDocument *)
0x180325c6c  mov     ebx, eax
0x180325c6e  test    eax, eax
0x180325c70  jns     short loc_180325C93
0x180325c72  mov     rcx, [rsp+0C8h]; this
0x180325c7a  mov     r9d, eax; char *
0x180325c7d  lea     r8, aShellTwinuiSof_9; "shell\\twinui\\softlanding\\lib\\window"...
0x180325c84  mov     edx, 11Eh; void *
0x180325c89  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180325c8e  jmp     loc_180326177
0x180325c93  mov     [rsp+0C8h+var_88], rsi
0x180325c98  mov     rax, [r12]
0x180325c9c  mov     rbx, [rax+80h]
0x180325ca3  lea     rcx, [rsp+0C8h+var_88]
0x180325ca8  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x180325cad  mov     [rsp+0C8h+var_48], rsi
0x180325cb5  mov     r9d, 4; unsigned int
0x180325cbb  lea     r8d, [r9+1]; unsigned int
0x180325cbf  lea     rdx, aText_0; "text"
0x180325cc6  lea     rcx, [rsp+0C8h+hstringHeader]; hstringHeader
0x180325ccb  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180325cd0  nop
0x180325cd1  lea     r8, [rsp+0C8h+var_88]
0x180325cd6  mov     rdx, [rsp+0C8h+var_48]
0x180325cde  mov     rcx, r12
0x180325ce1  mov     rax, rbx
0x180325ce4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180325ce9  mov     ebx, eax
0x180325ceb  test    eax, eax
0x180325ced  jns     short loc_180325CF9
0x180325cef  mov     edx, 121h
0x180325cf4  jmp     loc_180325EFA
0x180325cf9  mov     rcx, [rsp+0C8h+var_88]
0x180325cfe  mov     rax, [rcx]
0x180325d01  lea     rdx, [rsp+0C8h+var_80]
0x180325d06  mov     rax, [rax+30h]
0x180325d0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180325d0f  mov     rcx, [rsp+0C8h]; this
0x180325d17  test    eax, eax
0x180325d19  jns     short loc_180325D34
0x180325d1b  mov     r9d, eax; char *
0x180325d1e  lea     r8, aShellTwinuiSof_9; "shell\\twinui\\softlanding\\lib\\window"...
0x180325d25  mov     edx, 122h; void *
0x180325d2a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180325d2f  jmp     loc_180325E9E
0x180325d34  cmp     [rsp+0C8h+var_80], esi
0x180325d38  jbe     loc_180325E9E
0x180325d3e  mov     [rsp+0C8h+var_A8], rsi; int
0x180325d43  mov     rdi, [rsp+0C8h+var_88]
0x180325d48  mov     rax, [rdi]
0x180325d4b  mov     rbx, [rax+38h]
0x180325d4f  lea     rcx, [rsp+0C8h+var_A8]
0x180325d54  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x180325d59  lea     r8, [rsp+0C8h+var_A8]
0x180325d5e  xor     edx, edx
0x180325d60  mov     rcx, rdi
0x180325d63  mov     rax, rbx
0x180325d66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180325d6b  mov     ebx, eax
0x180325d6d  test    eax, eax
0x180325d6f  jns     short loc_180325D9D
0x180325d71  mov     edx, 126h; void *
0x180325d76  lea     r8, aShellTwinuiSof_9; "shell\\twinui\\softlanding\\lib\\window"...
0x180325d7d  mov     r9d, eax; char *
0x180325d80  mov     rcx, [rsp+0C8h]; this
0x180325d88  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180325d8d  nop
0x180325d8e  lea     rcx, [rsp+0C8h+var_A8]
0x180325d93  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x180325d98  jmp     loc_18032616D
0x180325d9d  mov     r14d, esi
0x180325da0  lea     r8, [rsp+0C8h+var_A0]; unsigned __int64 *
0x180325da5  mov     edx, 7FFFFFFFh; unsigned __int64
0x180325daa  mov     rcx, r13; unsigned __int16 *
0x180325dad  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180325db2  mov     rcx, [rsp+0C8h]; this
0x180325dba  test    eax, eax
0x180325dbc  jns     short loc_180325DD4
0x180325dbe  mov     r9d, eax; char *
0x180325dc1  lea     r8, aShellTwinuiSof_9; "shell\\twinui\\softlanding\\lib\\window"...
0x180325dc8  mov     edx, 128h; void *
0x180325dcd  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180325dd2  jmp     short loc_180325E11
0x180325dd4  cmp     [rsp+0C8h+var_A0], rsi
0x180325dd9  jbe     short loc_180325E11
0x180325ddb  mov     rbx, [rsp+0C8h+var_A8]
0x180325de0  lea     rdx, [rsp+0C8h+string]
0x180325de5  lea     rcx, [rsp+0C8h+hstringHeader]
0x180325dea  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180325def  mov     rdx, rbx; HSTRING
0x180325df2  mov     rcx, [rax+18h]; this
0x180325df6  call    ?CreateAndAppendTextNode@WindowsTip@UI@Internal@Windows@@YAJPEAUHSTRING__@@PEAUIXmlNode@Dom@Xml@Data@4@PEAPEAU67894@@Z; Windows::Internal::UI::WindowsTip::CreateAndAppendTextNode(HSTRING__ *,Windows::Data::Xml::Dom::IXmlNode *,Windows::Data::Xml::Dom::IXmlNode * *)
0x180325dfb  mov     ebx, eax
0x180325dfd  test    eax, eax
0x180325dff  jns     short loc_180325E0B
0x180325e01  mov     edx, 12Ah
0x180325e06  jmp     loc_180325D76
0x180325e0b  mov     r14d, 1
0x180325e11  cmp     [rsp+0C8h+var_80], r14d
0x180325e16  jbe     short loc_180325E8A
0x180325e18  mov     rdi, [rsp+0C8h+var_88]
0x180325e1d  mov     rax, [rdi]
0x180325e20  mov     rbx, [rax+38h]
0x180325e24  lea     rcx, [rsp+0C8h+var_A8]
0x180325e29  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x180325e2e  lea     r8, [rsp+0C8h+var_A8]
0x180325e33  mov     edx, r14d
0x180325e36  mov     rcx, rdi
0x180325e39  mov     rax, rbx
0x180325e3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180325e41  mov     ebx, eax
0x180325e43  test    eax, eax
0x180325e45  jns     short loc_180325E51
0x180325e47  mov     edx, 130h
0x180325e4c  jmp     loc_180325D76
0x180325e51  lea     r8, [rsp+0C8h+var_A0]; unsigned __int64 *
0x180325e56  mov     edx, 7FFFFFFFh; unsigned __int64
0x180325e5b  mov     rcx, [rsp+0C8h+var_90]; unsigned __int16 *
0x180325e60  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180325e65  mov     rcx, [rsp+0C8h]; this
0x180325e6d  test    eax, eax
0x180325e6f  jns     loc_180325F16
0x180325e75  mov     r9d, eax; char *
0x180325e78  lea     r8, aShellTwinuiSof_9; "shell\\twinui\\softlanding\\lib\\window"...
0x180325e7f  mov     edx, 132h; void *
0x180325e84  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180325e89  nop
0x180325e8a  lea     rcx, [rsp+0C8h+var_A8]
0x180325e8f  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x180325e94  mov     rdi, [rsp+0C8h+var_78]
0x180325e99  mov     r14, [rsp+0C8h+var_70]
0x180325e9e  lea     r8, [rsp+0C8h+var_A0]; unsigned __int64 *
0x180325ea3  mov     edx, 104h; unsigned __int64
0x180325ea8  mov     rcx, rdi; unsigned __int16 *
0x180325eab  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180325eb0  mov     rcx, [rsp+0C8h]; this
0x180325eb8  test    eax, eax
0x180325eba  jns     loc_180325F55
0x180325ec0  mov     r9d, eax; char *
0x180325ec3  lea     r8, aShellTwinuiSof_9; "shell\\twinui\\softlanding\\lib\\window"...
0x180325eca  mov     edx, 139h; void *
0x180325ecf  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180325ed4  cmp     [r15], sil
0x180325ed7  jnz     loc_18032616B
0x180325edd  mov     r8, r14; struct Windows::Internal::UI::WindowsTip::CreativeVisualDataForGuidedTours *
0x180325ee0  mov     rdx, r15; struct Windows::Data::Xml::Dom::IXmlDocument *
0x180325ee3  mov     rcx, r12; this
0x180325ee6  call    ?SetToastActionsForGuidedTours@WindowsTip@UI@Internal@Windows@@YAJPEAUIXmlDocument@Dom@Xml@Data@4@AEAUCreativeVisualDataForGuidedTours@1234@PEAUHSTRING__@@@Z; Windows::Internal::UI::WindowsTip::SetToastActionsForGuidedTours(Windows::Data::Xml::Dom::IXmlDocument *,Windows::Internal::UI::WindowsTip::CreativeVisualDataForGuidedTours &,HSTRING__ *)
0x180325eeb  mov     ebx, eax
0x180325eed  test    eax, eax
0x180325eef  jns     loc_180325F84
0x180325ef5  mov     edx, 141h; void *
0x180325efa  mov     r9d, eax; char *
0x180325efd  lea     r8, aShellTwinuiSof_9; "shell\\twinui\\softlanding\\lib\\window"...
0x180325f04  mov     rcx, [rsp+0C8h]; this
0x180325f0c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180325f11  jmp     loc_18032616D
0x180325f16  cmp     [rsp+0C8h+var_A0], rsi
0x180325f1b  jbe     loc_180325E8A
0x180325f21  mov     rbx, [rsp+0C8h+var_A8]
0x180325f26  lea     rdx, [rsp+0C8h+var_90]
0x180325f2b  lea     rcx, [rsp+0C8h+hstringHeader]
0x180325f30  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180325f35  mov     rdx, rbx; HSTRING
0x180325f38  mov     rcx, [rax+18h]; this
0x180325f3c  call    ?CreateAndAppendTextNode@WindowsTip@UI@Internal@Windows@@YAJPEAUHSTRING__@@PEAUIXmlNode@Dom@Xml@Data@4@PEAPEAU67894@@Z; Windows::Internal::UI::WindowsTip::CreateAndAppendTextNode(HSTRING__ *,Windows::Data::Xml::Dom::IXmlNode *,Windows::Data::Xml::Dom::IXmlNode * *)
0x180325f41  mov     ebx, eax
0x180325f43  test    eax, eax
0x180325f45  jns     loc_180325E8A
0x180325f4b  mov     edx, 134h
0x180325f50  jmp     loc_180325D76
0x180325f55  cmp     [rsp+0C8h+var_A0], rsi
0x180325f5a  jbe     loc_180325ED4
0x180325f60  mov     r8, [rsp+0C8h+var_68]; unsigned __int16 *
0x180325f65  mov     rdx, rdi; struct Windows::Data::Xml::Dom::IXmlDocument *
0x180325f68  mov     rcx, r12; this
0x180325f6b  call    ?SetToastImageSrc@WindowsTip@UI@Internal@Windows@@YAJPEAUIXmlDocument@Dom@Xml@Data@4@PEBG1@Z; Windows::Internal::UI::WindowsTip::SetToastImageSrc(Windows::Data::Xml::Dom::IXmlDocument *,ushort const *,ushort const *)
0x180325f70  mov     ebx, eax
0x180325f72  test    eax, eax
0x180325f74  jns     loc_180325ED4
0x180325f7a  mov     edx, 13Bh
0x180325f7f  jmp     loc_180325EFA
0x180325f84  cmp     dword ptr [r15+8], 1
0x180325f89  ja      loc_18032616B
0x180325f8f  mov     [rsp+0C8h+string], rsi
0x180325f94  lea     rcx, [r15+28h]; this
0x180325f98  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x180325f9d  mov     rbx, rax
0x180325fa0  xor     edx, edx; length
0x180325fa2  mov     rcx, r14; string
0x180325fa5  call    cs:__imp_WindowsGetStringRawBuffer
0x180325fab  mov     r8, rbx
0x180325fae  mov     rdx, rax
0x180325fb1  lea     rcx, [rsp+0C8h+var_A8]
0x180325fb6  call    ?CreateActionString@SoftLandingV2Helper@WindowsTip@UI@Internal@Windows@@SA?AUhstring@winrt@@PEBG0@Z; Windows::Internal::UI::WindowsTip::SoftLandingV2Helper::CreateActionString(ushort const *,ushort const *)
0x180325fbb  mov     rcx, [rsp+0C8h+string]; string
0x180325fc0  call    cs:__imp_WindowsDeleteString
0x180325fc6  mov     [rsp+0C8h+string], rsi
0x180325fcb  lea     rdx, [rsp+0C8h+string]; newString
0x180325fd0  mov     rcx, [rsp+0C8h+var_A8]; string
0x180325fd5  call    cs:__imp_WindowsDuplicateString
0x180325fdb  mov     ebx, eax
0x180325fdd  test    eax, eax
0x180325fdf  jns     short loc_180326029
0x180325fe1  mov     rcx, [rsp+0C8h]; this
0x180325fe9  mov     r9d, eax; char *
0x180325fec  lea     r8, aShellTwinuiSof_9; "shell\\twinui\\softlanding\\lib\\window"...
0x180325ff3  mov     edx, 14Bh; void *
0x180325ff8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180325ffd  lea     rcx, [rsp+0C8h+var_A8]
0x180326002  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180326007  nop
0x180326008  mov     rcx, [rsp+0C8h+string]; string
0x18032600d  call    cs:__imp_WindowsDeleteString
0x180326013  mov     [rsp+0C8h+string], rsi
0x180326018  lea     rcx, [rsp+0C8h+var_88]
0x18032601d  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x180326022  mov     eax, ebx
0x180326024  jmp     loc_180326179
0x180326029  lea     rcx, [rsp+0C8h+var_A8]
0x18032602e  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180326033  nop
0x180326034  mov     [rsp+0C8h+var_A0], rsi
0x180326039  mov     rax, [r12]
0x18032603d  mov     rbx, [rax]
0x180326040  lea     rcx, [rsp+0C8h+var_A0]
0x180326045  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18032604a  lea     r8, [rsp+0C8h+var_A0]
0x18032604f  lea     rdx, _GUID_63dbba8b_d0db_4fe1_b745_f9433afdc25b
0x180326056  mov     rcx, r12
0x180326059  mov     rax, rbx
0x18032605c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180326061  mov     ebx, eax
0x180326063  test    eax, eax
0x180326065  jns     short loc_180326093
0x180326067  mov     rcx, [rsp+0C8h]; this
0x18032606f  mov     r9d, eax; char *
0x180326072  lea     r8, aShellTwinuiSof_9; "shell\\twinui\\softlanding\\lib\\window"...
0x180326079  mov     edx, 154h; void *
0x18032607e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180326083  nop
0x180326084  lea     rcx, [rsp+0C8h+var_A0]
0x180326089  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18032608e  jmp     loc_1803261A2
0x180326093  mov     [rsp+0C8h+var_90], rsi
0x180326098  mov     rdi, [rsp+0C8h+var_A0]
0x18032609d  mov     rax, [rdi]
0x1803260a0  mov     rbx, [rax+30h]
0x1803260a4  lea     rcx, [rsp+0C8h+var_90]
0x1803260a9  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1803260ae  mov     [rsp+0C8h+var_48], rsi
0x1803260b6  mov     r9d, 5; unsigned int
0x1803260bc  lea     r8d, [r9+1]; unsigned int
0x1803260c0  lea     rdx, aToast_0; "toast"
0x1803260c7  lea     rcx, [rsp+0C8h+hstringHeader]; hstringHeader
0x1803260cc  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1803260d1  nop
0x1803260d2  lea     r8, [rsp+0C8h+var_90]
0x1803260d7  mov     rdx, [rsp+0C8h+var_48]
0x1803260df  mov     rcx, rdi
0x1803260e2  mov     rax, rbx
0x1803260e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803260ea  mov     ebx, eax
0x1803260ec  test    eax, eax
0x1803260ee  jns     short loc_18032611C
0x1803260f0  mov     edx, 156h; void *
  ... truncated ...
```
