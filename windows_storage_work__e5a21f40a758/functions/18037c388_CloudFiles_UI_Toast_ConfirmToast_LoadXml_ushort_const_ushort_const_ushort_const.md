# CloudFiles::UI::Toast::ConfirmToast::LoadXml(ushort const *,ushort const *,ushort const *)

- ea: `0x18037c388`
- end: `0x18037c962`
- name: `?LoadXml@ConfirmToast@Toast@UI@CloudFiles@@YA?AV?$com_ptr_t@UIXmlDocument@Dom@Xml@Data@Windows@@Uerr_exception_policy@wil@@@wil@@PEBG00@Z`
- size: `1498`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18038340c`

## callees

- `0x18000ee84`
- `0x18001c14c`
- `0x18005dc50`
- `0x18005f240`
- `0x1801dffa0`
- `0x18037c388`
- `0x18037c968`
- `0x18037ca14`
- `0x18037cb28`
- `0x18037cc3c`
- `0x18037ce24`
- `0x18037cf8c`
- `0x18037d400`
- `0x1803a4cb0`
- `0x18065a010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18037c7d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18037c7e5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18037c7f4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18037c803`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18037c7d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18037c7e5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18037c7f4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18037c803`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18037c502`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18037c56a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18037c5d2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18037c63a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18037c901`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18037c90f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18037c91d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18037c92b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18037c502`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18037c56a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18037c5d2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18037c63a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18037c901`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18037c90f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18037c91d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18037c92b`

## string_xrefs

- `0x18037c3c4`: `<toast scenario='reminder'>     <visual>         <binding template='ToastGeneric'>             <text id='1'></text>             <text id='2'></text>         </binding>     </visual>     <actions>         <action id='button1' activationType='background'/>         <action id='button2' activationType='background'/>     </actions>     <audio silent='true'/> </toast>`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
unsigned __int16 *__fastcall CloudFiles::UI::Toast::ConfirmToast::LoadXml(
        unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const WCHAR *a3,
        struct Windows::Data::Xml::Dom::IXmlDocument *a4)
{
  const unsigned __int16 *v8; // r8
  int v9; // eax
  struct Windows::UI::Notifications::IToastNotification **v10; // r8
  int DoesToastExist; // eax
  const unsigned __int16 *v12; // r8
  __int64 v13; // rax
  __int64 v14; // rbx
  __int64 (__fastcall *v15)(__int64, _QWORD **); // rdi
  _QWORD *v16; // rcx
  int v17; // eax
  __int64 v18; // rax
  int v19; // eax
  __int64 v20; // rdi
  __int64 (__fastcall *v21)(__int64, __int64, HSTRING *); // rbx
  int v22; // eax
  __int64 v23; // rdi
  __int64 (__fastcall *v24)(__int64, __int64, HSTRING *); // rbx
  int v25; // eax
  __int64 v26; // rdi
  __int64 (__fastcall *v27)(__int64, __int64, HSTRING *); // rbx
  int v28; // eax
  __int64 v29; // rdi
  __int64 (__fastcall *v30)(__int64, __int64, HSTRING *); // rbx
  int v31; // eax
  int v32; // eax
  const unsigned __int16 *v33; // r8
  int v34; // eax
  const WCHAR *v35; // rcx
  const WCHAR *v36; // rax
  int v37; // eax
  int v38; // eax
  int StringRawBuffer; // ebx
  PCWSTR v40; // rax
  int v41; // eax
  const unsigned __int16 *v42; // rbx
  int v43; // eax
  int v44; // eax
  int v46; // [rsp+20h] [rbp-A9h]
  int v47; // [rsp+20h] [rbp-A9h]
  int v48; // [rsp+20h] [rbp-A9h]
  int v49; // [rsp+20h] [rbp-A9h]
  unsigned __int16 v50[4]; // [rsp+50h] [rbp-79h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+58h] [rbp-71h] BYREF
  __int64 v52; // [rsp+70h] [rbp-59h]
  int v53; // [rsp+78h] [rbp-51h]
  unsigned __int16 *v54[4]; // [rsp+80h] [rbp-49h] BYREF
  __int64 v55; // [rsp+A0h] [rbp-29h] BYREF
  HSTRING v56; // [rsp+A8h] [rbp-21h] BYREF
  HSTRING v57; // [rsp+B0h] [rbp-19h] BYREF
  HSTRING v58; // [rsp+B8h] [rbp-11h] BYREF
  HSTRING string; // [rsp+C0h] [rbp-9h] BYREF
  _QWORD *v60; // [rsp+C8h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+5Fh]

  v54[3] = a1;
  LoadXmlFromString(
    a1,
    L"<toast scenario='reminder'>     <visual>         <binding template='ToastGeneric'>             <text id='1'></text> "
     "            <text id='2'></text>         </binding>     </visual>     <actions>         <action id='button1' activa"
     "tionType='background'/>         <action id='button2' activationType='background'/>     </actions>     <audio silent"
     "='true'/> </toast>");
  v53 = 1;
  v9 = CloudFiles::UI::Toast::ConfirmToast::PopulateTitleSubTitle(*(CloudFiles::UI::Toast::ConfirmToast **)a1, a4, v8);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1CA,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\cloudfilestoasts.cpp",
      (const char *)(unsigned int)v9,
      v46);
  *(_QWORD *)v50 = 0;
  DoesToastExist = CloudFiles::UI::Toast::DoesToastExist(a3, v50, v10);
  if ( DoesToastExist < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1CE,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\cloudfilestoasts.cpp",
      (const char *)(unsigned int)DoesToastExist,
      v46);
  string = 0;
  v58 = 0;
  v57 = 0;
  v56 = 0;
  if ( *(_QWORD *)v50 )
  {
    v60 = 0;
    v13 = wil::com_ptr_t<Windows::UI::Notifications::IToastNotification,wil::err_exception_policy>::query<Windows::UI::Notifications::IToastNotification4>(
            v50,
            &v55);
    v14 = *(_QWORD *)v13;
    v15 = *(__int64 (__fastcall **)(__int64, _QWORD **))(**(_QWORD **)v13 + 48LL);
    v16 = v60;
    v60 = 0;
    if ( v16 )
      (*(void (__fastcall **)(_QWORD *))(*v16 + 16LL))(v16);
    v17 = v15(v14, &v60);
    if ( v17 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1D4,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\cloudfilestoasts.cpp",
        (const char *)(unsigned int)v17,
        v46);
    wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v55);
    if ( v60 )
    {
      v55 = 0;
      v18 = *v60;
      v55 = 0;
      v19 = (*(__int64 (__fastcall **)(_QWORD *, __int64 *))(v18 + 48))(v60, &v55);
      if ( v19 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1D9,
          (unsigned int)"onecoreuap\\shell\\windows.storage\\cloudfilestoasts.cpp",
          (const char *)(unsigned int)v19,
          v46);
      v20 = v55;
      v21 = *(__int64 (__fastcall **)(__int64, __int64, HSTRING *))(*(_QWORD *)v55 + 48LL);
      WindowsDeleteString(string);
      string = 0;
      v52 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"fileCount", 0xAu, 9u);
      v22 = v21(v20, v52, &string);
      if ( v22 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1DA,
          (unsigned int)"onecoreuap\\shell\\windows.storage\\cloudfilestoasts.cpp",
          (const char *)(unsigned int)v22,
          v46);
      v23 = v55;
      v24 = *(__int64 (__fastcall **)(__int64, __int64, HSTRING *))(*(_QWORD *)v55 + 48LL);
      WindowsDeleteString(v58);
      v58 = 0;
      v52 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"abortKeyArg0", 0xDu, 0xCu);
      v25 = v24(v23, v52, &v58);
      if ( v25 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1DB,
          (unsigned int)"onecoreuap\\shell\\windows.storage\\cloudfilestoasts.cpp",
          (const char *)(unsigned int)v25,
          v46);
      v26 = v55;
      v27 = *(__int64 (__fastcall **)(__int64, __int64, HSTRING *))(*(_QWORD *)v55 + 48LL);
      WindowsDeleteString(v57);
      v57 = 0;
      v52 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"abortKeyArg1", 0xDu, 0xCu);
      v28 = v27(v26, v52, &v57);
      if ( v28 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1DC,
          (unsigned int)"onecoreuap\\shell\\windows.storage\\cloudfilestoasts.cpp",
          (const char *)(unsigned int)v28,
          v46);
      v29 = v55;
      v30 = *(__int64 (__fastcall **)(__int64, __int64, HSTRING *))(*(_QWORD *)v55 + 48LL);
      WindowsDeleteString(v56);
      v56 = 0;
      v52 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"abortKeyArg2", 0xDu, 0xCu);
      v31 = v30(v29, v52, &v56);
      if ( v31 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1DD,
          (unsigned int)"onecoreuap\\shell\\windows.storage\\cloudfilestoasts.cpp",
          (const char *)(unsigned int)v31,
          v46);
      wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v55);
    }
    wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v60);
  }
  v32 = SetXmlAttributeFromResource(
          *(struct Windows::Data::Xml::Dom::IXmlDocument **)a1,
          L"/toast/actions/action[@id='button1']",
          v12,
          0x4B5u);
  if ( v32 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1E2,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\cloudfilestoasts.cpp",
      (const char *)(unsigned int)v32,
      v46);
  v34 = SetXmlAttributeFromResource(
          *(struct Windows::Data::Xml::Dom::IXmlDocument **)a1,
          L"/toast/actions/action[@id='button2']",
          v33,
          0x4BCu);
  if ( v34 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1E3,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\cloudfilestoasts.cpp",
      (const char *)(unsigned int)v34,
      v46);
  memset(&hstringHeader, 0, sizeof(hstringHeader));
  v35 = (const WCHAR *)a4;
  if ( !a4 )
    v35 = &WindowName;
  v36 = a3;
  if ( !a3 )
    v36 = &WindowName;
  v37 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
          &hstringHeader,
          L"%s%s%s%s%s%s%s%s",
          L"$",
          L"Toast.Confirm.Body",
          L"$",
          a2,
          L"$",
          v36,
          L"$",
          v35);
  if ( v37 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1F0,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\cloudfilestoasts.cpp",
      (const char *)(unsigned int)v37,
      v47);
  v38 = SetXmlAttribute(
          *(struct Windows::Data::Xml::Dom::IXmlDocument **)a1,
          L"/toast",
          L"launch",
          (const unsigned __int16 *)hstringHeader.Reserved.Reserved1);
  if ( v38 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1F1,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\cloudfilestoasts.cpp",
      (const char *)(unsigned int)v38,
      v47);
  memset(v54, 0, 24);
  WindowsGetStringRawBuffer(v56, 0);
  WindowsGetStringRawBuffer(v57, 0);
  StringRawBuffer = (unsigned int)WindowsGetStringRawBuffer(v58, 0);
  v40 = WindowsGetStringRawBuffer(string, 0);
  v41 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
          v54,
          L"%s%s%s%s%s%s%s",
          v40);
  if ( v41 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1FD,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\cloudfilestoasts.cpp",
      (const char *)(unsigned int)v41,
      StringRawBuffer);
  v42 = v54[0];
  v43 = SetXmlButtonArgs(
          *(struct Windows::Data::Xml::Dom::IXmlDocument **)a1,
          L"/toast/actions/action[@id='button1']",
          L"Toast.Confirm.Button.Cancel",
          a2,
          a3,
          (const unsigned __int16 *)a4,
          v54[0]);
  if ( v43 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x207,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\cloudfilestoasts.cpp",
      (const char *)(unsigned int)v43,
      v48);
  v44 = SetXmlButtonArgs(
          *(struct Windows::Data::Xml::Dom::IXmlDocument **)a1,
          L"/toast/actions/action[@id='button2']",
          L"Toast.Confirm.Button.Block",
          a2,
          a3,
          (const unsigned __int16 *)a4,
          v42);
  if ( v44 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x211,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\cloudfilestoasts.cpp",
      (const char *)(unsigned int)v44,
      v49);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v54);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&hstringHeader);
  WindowsDeleteString(v56);
  v56 = 0;
  WindowsDeleteString(v57);
  v57 = 0;
  WindowsDeleteString(v58);
  v58 = 0;
  WindowsDeleteString(string);
  string = 0;
  wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(v50);
  return a1;
}

```

## disassembly

```asm
0x18037c388  push    rbp
0x18037c38a  push    rbx
0x18037c38b  push    rsi
0x18037c38c  push    rdi
0x18037c38d  push    r12
0x18037c38f  push    r13
0x18037c391  push    r14
0x18037c393  push    r15
0x18037c395  lea     rbp, [rsp-1Fh]
0x18037c39a  sub     rsp, 0E8h
0x18037c3a1  mov     rax, cs:__security_cookie
0x18037c3a8  xor     rax, rsp
0x18037c3ab  mov     [rbp+57h+var_50], rax
0x18037c3af  mov     r12, r9
0x18037c3b2  mov     r15, r8
0x18037c3b5  mov     r13, rdx
0x18037c3b8  mov     r14, rcx
0x18037c3bb  mov     [rbp+57h+var_88], rcx
0x18037c3bf  xor     esi, esi
0x18037c3c1  mov     [rbp+57h+var_A8], esi
0x18037c3c4  lea     rdx, aToastScenarioR; "<toast scenario='reminder'>     <visual"...
0x18037c3cb  call    ?LoadXmlFromString@@YA?AV?$com_ptr_t@UIXmlDocument@Dom@Xml@Data@Windows@@Uerr_exception_policy@wil@@@wil@@PEBG@Z; LoadXmlFromString(ushort const *)
0x18037c3d0  mov     [rbp+57h+var_A8], 1
0x18037c3d7  mov     rdx, r12; struct Windows::Data::Xml::Dom::IXmlDocument *
0x18037c3da  mov     rcx, [r14]; this
0x18037c3dd  call    ?PopulateTitleSubTitle@ConfirmToast@Toast@UI@CloudFiles@@YAJPEAUIXmlDocument@Dom@Xml@Data@Windows@@PEBG@Z; CloudFiles::UI::Toast::ConfirmToast::PopulateTitleSubTitle(Windows::Data::Xml::Dom::IXmlDocument *,ushort const *)
0x18037c3e2  mov     rcx, [rbp+5Fh]; this
0x18037c3e6  test    eax, eax
0x18037c3e8  jns     short loc_18037C3FF
0x18037c3ea  mov     r9d, eax; char *
0x18037c3ed  lea     r8, aOnecoreuapShel_162; "onecoreuap\\shell\\windows.storage\\clo"...
0x18037c3f4  mov     edx, 1CAh; void *
0x18037c3f9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18037c3ff  mov     qword ptr [rbp+57h+var_D0], rsi
0x18037c403  lea     rdx, [rbp+57h+var_D0]; unsigned __int16 *
0x18037c407  mov     rcx, r15; lpString2
0x18037c40a  call    ?DoesToastExist@Toast@UI@CloudFiles@@YAJPEBGPEAPEAUIToastNotification@Notifications@2Windows@@@Z; CloudFiles::UI::Toast::DoesToastExist(ushort const *,Windows::UI::Notifications::IToastNotification * *)
0x18037c40f  mov     rcx, [rbp+5Fh]; this
0x18037c413  test    eax, eax
0x18037c415  jns     short loc_18037C42C
0x18037c417  mov     r9d, eax; char *
0x18037c41a  lea     r8, aOnecoreuapShel_162; "onecoreuap\\shell\\windows.storage\\clo"...
0x18037c421  mov     edx, 1CEh; void *
0x18037c426  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18037c42c  mov     [rbp+57h+string], rsi
0x18037c430  mov     [rbp+57h+var_68], rsi
0x18037c434  mov     [rbp+57h+var_70], rsi
0x18037c438  mov     [rbp+57h+var_78], rsi
0x18037c43c  cmp     qword ptr [rbp+57h+var_D0], rsi
0x18037c440  jz      loc_18037C6A6
0x18037c446  mov     [rbp+57h+var_58], rsi
0x18037c44a  lea     rdx, [rbp+57h+var_80]
0x18037c44e  lea     rcx, [rbp+57h+var_D0]
0x18037c452  call    ??$query@UIToastNotification4@Notifications@UI@Windows@@@?$com_ptr_t@UIToastNotification@Notifications@UI@Windows@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UIToastNotification4@Notifications@UI@Windows@@Uerr_exception_policy@wil@@@1@XZ; wil::com_ptr_t<Windows::UI::Notifications::IToastNotification,wil::err_exception_policy>::query<Windows::UI::Notifications::IToastNotification4>(void)
0x18037c457  nop
0x18037c458  mov     rbx, [rax]
0x18037c45b  mov     rax, [rbx]
0x18037c45e  mov     rdi, [rax+30h]
0x18037c462  mov     rcx, [rbp+57h+var_58]
0x18037c466  mov     [rbp+57h+var_58], rsi
0x18037c46a  test    rcx, rcx
0x18037c46d  jz      short loc_18037C47C
0x18037c46f  mov     rax, [rcx]
0x18037c472  mov     rax, [rax+10h]
0x18037c476  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18037c47b  nop
0x18037c47c  lea     rdx, [rbp+57h+var_58]
0x18037c480  mov     rcx, rbx
0x18037c483  mov     rax, rdi
0x18037c486  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18037c48b  mov     rcx, [rbp+5Fh]; this
0x18037c48f  test    eax, eax
0x18037c491  jns     short loc_18037C4A8
0x18037c493  mov     r9d, eax; char *
0x18037c496  lea     r8, aOnecoreuapShel_162; "onecoreuap\\shell\\windows.storage\\clo"...
0x18037c49d  mov     edx, 1D4h; void *
0x18037c4a2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18037c4a8  lea     rcx, [rbp+57h+var_80]
0x18037c4ac  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x18037c4b1  mov     rcx, [rbp+57h+var_58]
0x18037c4b5  test    rcx, rcx
0x18037c4b8  jz      loc_18037C69D
0x18037c4be  mov     [rbp+57h+var_80], rsi
0x18037c4c2  mov     rax, [rcx]
0x18037c4c5  mov     [rbp+57h+var_80], rsi
0x18037c4c9  lea     rdx, [rbp+57h+var_80]
0x18037c4cd  mov     rax, [rax+30h]
0x18037c4d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18037c4d6  mov     rcx, [rbp+5Fh]; this
0x18037c4da  test    eax, eax
0x18037c4dc  jns     short loc_18037C4F3
0x18037c4de  mov     r9d, eax; char *
0x18037c4e1  lea     r8, aOnecoreuapShel_162; "onecoreuap\\shell\\windows.storage\\clo"...
0x18037c4e8  mov     edx, 1D9h; void *
0x18037c4ed  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18037c4f3  mov     rdi, [rbp+57h+var_80]
0x18037c4f7  mov     rax, [rdi]
0x18037c4fa  mov     rbx, [rax+30h]
0x18037c4fe  mov     rcx, [rbp+57h+string]; string
0x18037c502  call    cs:__imp_WindowsDeleteString
0x18037c508  mov     [rbp+57h+string], rsi
0x18037c50c  mov     [rbp+57h+var_B0], rsi
0x18037c510  mov     r9d, 9; unsigned int
0x18037c516  lea     r8d, [r9+1]; unsigned int
0x18037c51a  lea     rdx, aFilecount; "fileCount"
0x18037c521  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18037c525  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18037c52a  nop
0x18037c52b  lea     r8, [rbp+57h+string]
0x18037c52f  mov     rdx, [rbp+57h+var_B0]
0x18037c533  mov     rcx, rdi
0x18037c536  mov     rax, rbx
0x18037c539  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18037c53e  mov     rcx, [rbp+5Fh]; this
0x18037c542  test    eax, eax
0x18037c544  jns     short loc_18037C55B
0x18037c546  mov     r9d, eax; char *
0x18037c549  lea     r8, aOnecoreuapShel_162; "onecoreuap\\shell\\windows.storage\\clo"...
0x18037c550  mov     edx, 1DAh; void *
0x18037c555  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18037c55b  mov     rdi, [rbp+57h+var_80]
0x18037c55f  mov     rax, [rdi]
0x18037c562  mov     rbx, [rax+30h]
0x18037c566  mov     rcx, [rbp+57h+var_68]; string
0x18037c56a  call    cs:__imp_WindowsDeleteString
0x18037c570  mov     [rbp+57h+var_68], rsi
0x18037c574  mov     [rbp+57h+var_B0], rsi
0x18037c578  mov     r9d, 0Ch; unsigned int
0x18037c57e  lea     r8d, [r9+1]; unsigned int
0x18037c582  lea     rdx, aAbortkeyarg0; "abortKeyArg0"
0x18037c589  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18037c58d  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18037c592  nop
0x18037c593  lea     r8, [rbp+57h+var_68]
0x18037c597  mov     rdx, [rbp+57h+var_B0]
0x18037c59b  mov     rcx, rdi
0x18037c59e  mov     rax, rbx
0x18037c5a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18037c5a6  mov     rcx, [rbp+5Fh]; this
0x18037c5aa  test    eax, eax
0x18037c5ac  jns     short loc_18037C5C3
0x18037c5ae  mov     r9d, eax; char *
0x18037c5b1  lea     r8, aOnecoreuapShel_162; "onecoreuap\\shell\\windows.storage\\clo"...
0x18037c5b8  mov     edx, 1DBh; void *
0x18037c5bd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18037c5c3  mov     rdi, [rbp+57h+var_80]
0x18037c5c7  mov     rax, [rdi]
0x18037c5ca  mov     rbx, [rax+30h]
0x18037c5ce  mov     rcx, [rbp+57h+var_70]; string
0x18037c5d2  call    cs:__imp_WindowsDeleteString
0x18037c5d8  mov     [rbp+57h+var_70], rsi
0x18037c5dc  mov     [rbp+57h+var_B0], rsi
0x18037c5e0  mov     r9d, 0Ch; unsigned int
0x18037c5e6  lea     r8d, [r9+1]; unsigned int
0x18037c5ea  lea     rdx, aAbortkeyarg1; "abortKeyArg1"
0x18037c5f1  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18037c5f5  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18037c5fa  nop
0x18037c5fb  lea     r8, [rbp+57h+var_70]
0x18037c5ff  mov     rdx, [rbp+57h+var_B0]
0x18037c603  mov     rcx, rdi
0x18037c606  mov     rax, rbx
0x18037c609  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18037c60e  mov     rcx, [rbp+5Fh]; this
0x18037c612  test    eax, eax
0x18037c614  jns     short loc_18037C62B
0x18037c616  mov     r9d, eax; char *
0x18037c619  lea     r8, aOnecoreuapShel_162; "onecoreuap\\shell\\windows.storage\\clo"...
0x18037c620  mov     edx, 1DCh; void *
0x18037c625  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18037c62b  mov     rdi, [rbp+57h+var_80]
0x18037c62f  mov     rax, [rdi]
0x18037c632  mov     rbx, [rax+30h]
0x18037c636  mov     rcx, [rbp+57h+var_78]; string
0x18037c63a  call    cs:__imp_WindowsDeleteString
0x18037c640  mov     [rbp+57h+var_78], rsi
0x18037c644  mov     [rbp+57h+var_B0], rsi
0x18037c648  mov     r9d, 0Ch; unsigned int
0x18037c64e  lea     r8d, [r9+1]; unsigned int
0x18037c652  lea     rdx, aAbortkeyarg2; "abortKeyArg2"
0x18037c659  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18037c65d  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18037c662  nop
0x18037c663  lea     r8, [rbp+57h+var_78]
0x18037c667  mov     rdx, [rbp+57h+var_B0]
0x18037c66b  mov     rcx, rdi
0x18037c66e  mov     rax, rbx
0x18037c671  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18037c676  mov     rcx, [rbp+5Fh]; this
0x18037c67a  test    eax, eax
0x18037c67c  jns     short loc_18037C693
0x18037c67e  mov     r9d, eax; char *
0x18037c681  lea     r8, aOnecoreuapShel_162; "onecoreuap\\shell\\windows.storage\\clo"...
0x18037c688  mov     edx, 1DDh; void *
0x18037c68d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18037c693  lea     rcx, [rbp+57h+var_80]
0x18037c697  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x18037c69c  nop
0x18037c69d  lea     rcx, [rbp+57h+var_58]
0x18037c6a1  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x18037c6a6  mov     r9d, 4B5h; unsigned int
0x18037c6ac  lea     rdx, aToastActionsAc; "/toast/actions/action[@id='button1']"
0x18037c6b3  mov     rcx, [r14]; struct Windows::Data::Xml::Dom::IXmlDocument *
0x18037c6b6  call    ?SetXmlAttributeFromResource@@YAJPEAUIXmlDocument@Dom@Xml@Data@Windows@@PEBG1I@Z; SetXmlAttributeFromResource(Windows::Data::Xml::Dom::IXmlDocument *,ushort const *,ushort const *,uint)
0x18037c6bb  mov     rcx, [rbp+5Fh]; this
0x18037c6bf  test    eax, eax
0x18037c6c1  jns     short loc_18037C6D8
0x18037c6c3  mov     r9d, eax; char *
0x18037c6c6  lea     r8, aOnecoreuapShel_162; "onecoreuap\\shell\\windows.storage\\clo"...
0x18037c6cd  mov     edx, 1E2h; void *
0x18037c6d2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18037c6d8  mov     r9d, 4BCh; unsigned int
0x18037c6de  lea     rdx, aToastActionsAc_0; "/toast/actions/action[@id='button2']"
0x18037c6e5  mov     rcx, [r14]; struct Windows::Data::Xml::Dom::IXmlDocument *
0x18037c6e8  call    ?SetXmlAttributeFromResource@@YAJPEAUIXmlDocument@Dom@Xml@Data@Windows@@PEBG1I@Z; SetXmlAttributeFromResource(Windows::Data::Xml::Dom::IXmlDocument *,ushort const *,ushort const *,uint)
0x18037c6ed  mov     rcx, [rbp+5Fh]; this
0x18037c6f1  test    eax, eax
0x18037c6f3  jns     short loc_18037C70A
0x18037c6f5  mov     r9d, eax; char *
0x18037c6f8  lea     r8, aOnecoreuapShel_162; "onecoreuap\\shell\\windows.storage\\clo"...
0x18037c6ff  mov     edx, 1E3h; void *
0x18037c704  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18037c70a  mov     qword ptr [rbp+57h+hstringHeader.Reserved], rsi
0x18037c70e  mov     qword ptr [rbp+57h+hstringHeader.Reserved+8], rsi
0x18037c712  mov     qword ptr [rbp+57h+hstringHeader.Reserved+10h], rsi
0x18037c716  lea     rdx, WindowName
0x18037c71d  mov     rcx, r12
0x18037c720  test    r12, r12
0x18037c723  cmovz   rcx, rdx
0x18037c727  mov     rax, r15
0x18037c72a  test    r15, r15
0x18037c72d  cmovz   rax, rdx
0x18037c731  mov     [rsp+120h+var_D8], rcx
0x18037c736  lea     rcx, asc_1807148BC; "$"
0x18037c73d  mov     [rsp+120h+var_E0], rcx
0x18037c742  mov     [rsp+120h+var_E8], rax
0x18037c747  mov     [rsp+120h+var_F0], rcx
0x18037c74c  mov     [rsp+120h+var_F8], r13
0x18037c751  mov     [rsp+120h+var_100], rcx; int
0x18037c756  lea     r9, aToastConfirmBo; "Toast.Confirm.Body"
0x18037c75d  mov     r8, rcx
0x18037c760  lea     rdx, aSSSSSSSS; "%s%s%s%s%s%s%s%s"
0x18037c767  lea     rcx, [rbp+57h+hstringHeader]
0x18037c76b  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x18037c770  mov     rcx, [rbp+5Fh]; this
0x18037c774  test    eax, eax
0x18037c776  jns     short loc_18037C78D
0x18037c778  mov     r9d, eax; char *
0x18037c77b  lea     r8, aOnecoreuapShel_162; "onecoreuap\\shell\\windows.storage\\clo"...
0x18037c782  mov     edx, 1F0h; void *
0x18037c787  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18037c78d  mov     r9, qword ptr [rbp+57h+hstringHeader.Reserved]; unsigned __int16 *
0x18037c791  lea     r8, aLaunch_0; "launch"
0x18037c798  lea     rdx, aToast; "/toast"
0x18037c79f  mov     rcx, [r14]; struct Windows::Data::Xml::Dom::IXmlDocument *
0x18037c7a2  call    ?SetXmlAttribute@@YAJPEAUIXmlDocument@Dom@Xml@Data@Windows@@PEBG11@Z; SetXmlAttribute(Windows::Data::Xml::Dom::IXmlDocument *,ushort const *,ushort const *,ushort const *)
0x18037c7a7  mov     rcx, [rbp+5Fh]; this
0x18037c7ab  test    eax, eax
0x18037c7ad  jns     short loc_18037C7C4
0x18037c7af  mov     r9d, eax; char *
0x18037c7b2  lea     r8, aOnecoreuapShel_162; "onecoreuap\\shell\\windows.storage\\clo"...
0x18037c7b9  mov     edx, 1F1h; void *
0x18037c7be  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18037c7c4  mov     [rbp+57h+var_A0], rsi
0x18037c7c8  mov     [rbp+57h+var_98], rsi
0x18037c7cc  mov     [rbp+57h+var_90], rsi
0x18037c7d0  xor     edx, edx; length
0x18037c7d2  mov     rcx, [rbp+57h+var_78]; string
0x18037c7d6  call    cs:__imp_WindowsGetStringRawBuffer
0x18037c7dc  mov     rsi, rax
0x18037c7df  xor     edx, edx; length
0x18037c7e1  mov     rcx, [rbp+57h+var_70]; string
0x18037c7e5  call    cs:__imp_WindowsGetStringRawBuffer
0x18037c7eb  mov     rdi, rax
0x18037c7ee  xor     edx, edx; length
0x18037c7f0  mov     rcx, [rbp+57h+var_68]; string
0x18037c7f4  call    cs:__imp_WindowsGetStringRawBuffer
0x18037c7fa  mov     rbx, rax
0x18037c7fd  xor     edx, edx; length
0x18037c7ff  mov     rcx, [rbp+57h+string]; string
0x18037c803  call    cs:__imp_WindowsGetStringRawBuffer
0x18037c809  mov     [rsp+120h+var_E0], rsi
0x18037c80e  lea     r9, asc_1807148BC; "$"
0x18037c815  mov     [rsp+120h+var_E8], r9
0x18037c81a  mov     [rsp+120h+var_F0], rdi
0x18037c81f  mov     [rsp+120h+var_F8], r9
0x18037c824  mov     [rsp+120h+var_100], rbx; int
0x18037c829  mov     r8, rax
0x18037c82c  lea     rdx, aSSSSSSS; "%s%s%s%s%s%s%s"
0x18037c833  lea     rcx, [rbp+57h+var_A0]
0x18037c837  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x18037c83c  mov     rcx, [rbp+5Fh]; this
0x18037c840  xor     edi, edi
0x18037c842  test    eax, eax
0x18037c844  jns     short loc_18037C85B
0x18037c846  mov     r9d, eax; char *
0x18037c849  lea     r8, aOnecoreuapShel_162; "onecoreuap\\shell\\windows.storage\\clo"...
0x18037c850  mov     edx, 1FDh; void *
0x18037c855  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18037c85b  mov     rbx, [rbp+57h+var_A0]
  ... truncated ...
```
