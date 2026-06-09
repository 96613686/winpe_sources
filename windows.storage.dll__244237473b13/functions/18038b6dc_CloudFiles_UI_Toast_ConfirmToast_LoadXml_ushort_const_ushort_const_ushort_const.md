# CloudFiles::UI::Toast::ConfirmToast::LoadXml(ushort const *,ushort const *,ushort const *)

- ea: `0x18038b6dc`
- end: `0x18038bcfe`
- name: `?LoadXml@ConfirmToast@Toast@UI@CloudFiles@@YA?AV?$com_ptr_t@UIXmlDocument@Dom@Xml@Data@Windows@@Uerr_exception_policy@wil@@@wil@@PEBG00@Z`
- size: `1570`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180391f34`

## callees

- `0x180033c60`
- `0x180079ccc`
- `0x18007dcf0`
- `0x18015f938`
- `0x18023ee10`
- `0x18038b6dc`
- `0x18038bd04`
- `0x18038bdb0`
- `0x18038bec4`
- `0x18038bfd8`
- `0x18038c1c8`
- `0x18038c334`
- `0x18038c7dc`
- `0x1803b1f60`
- `0x18067d010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18038bb42`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18038bb57`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18038bb6c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18038bb81`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18038bb42`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18038bb57`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18038bb6c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18038bb81`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18038b856`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18038b8c4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18038b932`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18038b9a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18038bc85`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18038bc99`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18038bcad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18038bcc1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18038b856`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18038b8c4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18038b932`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18038b9a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18038bc85`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18038bc99`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18038bcad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18038bcc1`

## string_xrefs

- `0x18038b718`: `<toast scenario='reminder'>     <visual>         <binding template='ToastGeneric'>             <text id='1'></text>             <text id='2'></text>         </binding>     </visual>     <actions>         <action id='button1' activationType='background'/>         <action id='button2' activationType='background'/>     </actions>     <audio silent='true'/> </toast>`

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
  const OLECHAR *v35; // rcx
  const OLECHAR *v36; // rax
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
  v35 = (const OLECHAR *)a4;
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
0x18038b6dc  push    rbp
0x18038b6de  push    rbx
0x18038b6df  push    rsi
0x18038b6e0  push    rdi
0x18038b6e1  push    r12
0x18038b6e3  push    r13
0x18038b6e5  push    r14
0x18038b6e7  push    r15
0x18038b6e9  lea     rbp, [rsp-1Fh]
0x18038b6ee  sub     rsp, 0E8h
0x18038b6f5  mov     rax, cs:__security_cookie
0x18038b6fc  xor     rax, rsp
0x18038b6ff  mov     [rbp+57h+var_50], rax
0x18038b703  mov     r12, r9
0x18038b706  mov     r15, r8
0x18038b709  mov     r13, rdx
0x18038b70c  mov     r14, rcx
0x18038b70f  mov     [rbp+57h+var_88], rcx
0x18038b713  xor     esi, esi
0x18038b715  mov     [rbp+57h+var_A8], esi
0x18038b718  lea     rdx, aToastScenarioR; "<toast scenario='reminder'>     <visual"...
0x18038b71f  call    ?LoadXmlFromString@@YA?AV?$com_ptr_t@UIXmlDocument@Dom@Xml@Data@Windows@@Uerr_exception_policy@wil@@@wil@@PEBG@Z; LoadXmlFromString(ushort const *)
0x18038b724  mov     [rbp+57h+var_A8], 1
0x18038b72b  mov     rdx, r12; struct Windows::Data::Xml::Dom::IXmlDocument *
0x18038b72e  mov     rcx, [r14]; this
0x18038b731  call    ?PopulateTitleSubTitle@ConfirmToast@Toast@UI@CloudFiles@@YAJPEAUIXmlDocument@Dom@Xml@Data@Windows@@PEBG@Z; CloudFiles::UI::Toast::ConfirmToast::PopulateTitleSubTitle(Windows::Data::Xml::Dom::IXmlDocument *,ushort const *)
0x18038b736  mov     rcx, [rbp+5Fh]; this
0x18038b73a  test    eax, eax
0x18038b73c  jns     short loc_18038B753
0x18038b73e  mov     r9d, eax; char *
0x18038b741  lea     r8, aOnecoreuapShel_162; "onecoreuap\\shell\\windows.storage\\clo"...
0x18038b748  mov     edx, 1CAh; void *
0x18038b74d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18038b753  mov     qword ptr [rbp+57h+var_D0], rsi
0x18038b757  lea     rdx, [rbp+57h+var_D0]; unsigned __int16 *
0x18038b75b  mov     rcx, r15; lpString2
0x18038b75e  call    ?DoesToastExist@Toast@UI@CloudFiles@@YAJPEBGPEAPEAUIToastNotification@Notifications@2Windows@@@Z; CloudFiles::UI::Toast::DoesToastExist(ushort const *,Windows::UI::Notifications::IToastNotification * *)
0x18038b763  mov     rcx, [rbp+5Fh]; this
0x18038b767  test    eax, eax
0x18038b769  jns     short loc_18038B780
0x18038b76b  mov     r9d, eax; char *
0x18038b76e  lea     r8, aOnecoreuapShel_162; "onecoreuap\\shell\\windows.storage\\clo"...
0x18038b775  mov     edx, 1CEh; void *
0x18038b77a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18038b780  mov     [rbp+57h+string], rsi
0x18038b784  mov     [rbp+57h+var_68], rsi
0x18038b788  mov     [rbp+57h+var_70], rsi
0x18038b78c  mov     [rbp+57h+var_78], rsi
0x18038b790  cmp     qword ptr [rbp+57h+var_D0], rsi
0x18038b794  jz      loc_18038BA12
0x18038b79a  mov     [rbp+57h+var_58], rsi
0x18038b79e  lea     rdx, [rbp+57h+var_80]
0x18038b7a2  lea     rcx, [rbp+57h+var_D0]
0x18038b7a6  call    ??$query@UIToastNotification4@Notifications@UI@Windows@@@?$com_ptr_t@UIToastNotification@Notifications@UI@Windows@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UIToastNotification4@Notifications@UI@Windows@@Uerr_exception_policy@wil@@@1@XZ; wil::com_ptr_t<Windows::UI::Notifications::IToastNotification,wil::err_exception_policy>::query<Windows::UI::Notifications::IToastNotification4>(void)
0x18038b7ab  nop
0x18038b7ac  mov     rbx, [rax]
0x18038b7af  mov     rax, [rbx]
0x18038b7b2  mov     rdi, [rax+30h]
0x18038b7b6  mov     rcx, [rbp+57h+var_58]
0x18038b7ba  mov     [rbp+57h+var_58], rsi
0x18038b7be  test    rcx, rcx
0x18038b7c1  jz      short loc_18038B7D0
0x18038b7c3  mov     rax, [rcx]
0x18038b7c6  mov     rax, [rax+10h]
0x18038b7ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18038b7cf  nop
0x18038b7d0  lea     rdx, [rbp+57h+var_58]
0x18038b7d4  mov     rcx, rbx
0x18038b7d7  mov     rax, rdi
0x18038b7da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18038b7df  mov     rcx, [rbp+5Fh]; this
0x18038b7e3  test    eax, eax
0x18038b7e5  jns     short loc_18038B7FC
0x18038b7e7  mov     r9d, eax; char *
0x18038b7ea  lea     r8, aOnecoreuapShel_162; "onecoreuap\\shell\\windows.storage\\clo"...
0x18038b7f1  mov     edx, 1D4h; void *
0x18038b7f6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18038b7fc  lea     rcx, [rbp+57h+var_80]
0x18038b800  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x18038b805  mov     rcx, [rbp+57h+var_58]
0x18038b809  test    rcx, rcx
0x18038b80c  jz      loc_18038BA09
0x18038b812  mov     [rbp+57h+var_80], rsi
0x18038b816  mov     rax, [rcx]
0x18038b819  mov     [rbp+57h+var_80], rsi
0x18038b81d  lea     rdx, [rbp+57h+var_80]
0x18038b821  mov     rax, [rax+30h]
0x18038b825  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18038b82a  mov     rcx, [rbp+5Fh]; this
0x18038b82e  test    eax, eax
0x18038b830  jns     short loc_18038B847
0x18038b832  mov     r9d, eax; char *
0x18038b835  lea     r8, aOnecoreuapShel_162; "onecoreuap\\shell\\windows.storage\\clo"...
0x18038b83c  mov     edx, 1D9h; void *
0x18038b841  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18038b847  mov     rdi, [rbp+57h+var_80]
0x18038b84b  mov     rax, [rdi]
0x18038b84e  mov     rbx, [rax+30h]
0x18038b852  mov     rcx, [rbp+57h+string]; string
0x18038b856  call    cs:__imp_WindowsDeleteString
0x18038b85d  nop     dword ptr [rax+rax+00h]
0x18038b862  mov     [rbp+57h+string], rsi
0x18038b866  mov     [rbp+57h+var_B0], rsi
0x18038b86a  mov     r9d, 9; unsigned int
0x18038b870  lea     r8d, [r9+1]; unsigned int
0x18038b874  lea     rdx, aFilecount; "fileCount"
0x18038b87b  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18038b87f  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18038b884  nop
0x18038b885  lea     r8, [rbp+57h+string]
0x18038b889  mov     rdx, [rbp+57h+var_B0]
0x18038b88d  mov     rcx, rdi
0x18038b890  mov     rax, rbx
0x18038b893  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18038b898  mov     rcx, [rbp+5Fh]; this
0x18038b89c  test    eax, eax
0x18038b89e  jns     short loc_18038B8B5
0x18038b8a0  mov     r9d, eax; char *
0x18038b8a3  lea     r8, aOnecoreuapShel_162; "onecoreuap\\shell\\windows.storage\\clo"...
0x18038b8aa  mov     edx, 1DAh; void *
0x18038b8af  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18038b8b5  mov     rdi, [rbp+57h+var_80]
0x18038b8b9  mov     rax, [rdi]
0x18038b8bc  mov     rbx, [rax+30h]
0x18038b8c0  mov     rcx, [rbp+57h+var_68]; string
0x18038b8c4  call    cs:__imp_WindowsDeleteString
0x18038b8cb  nop     dword ptr [rax+rax+00h]
0x18038b8d0  mov     [rbp+57h+var_68], rsi
0x18038b8d4  mov     [rbp+57h+var_B0], rsi
0x18038b8d8  mov     r9d, 0Ch; unsigned int
0x18038b8de  lea     r8d, [r9+1]; unsigned int
0x18038b8e2  lea     rdx, aAbortkeyarg0; "abortKeyArg0"
0x18038b8e9  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18038b8ed  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18038b8f2  nop
0x18038b8f3  lea     r8, [rbp+57h+var_68]
0x18038b8f7  mov     rdx, [rbp+57h+var_B0]
0x18038b8fb  mov     rcx, rdi
0x18038b8fe  mov     rax, rbx
0x18038b901  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18038b906  mov     rcx, [rbp+5Fh]; this
0x18038b90a  test    eax, eax
0x18038b90c  jns     short loc_18038B923
0x18038b90e  mov     r9d, eax; char *
0x18038b911  lea     r8, aOnecoreuapShel_162; "onecoreuap\\shell\\windows.storage\\clo"...
0x18038b918  mov     edx, 1DBh; void *
0x18038b91d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18038b923  mov     rdi, [rbp+57h+var_80]
0x18038b927  mov     rax, [rdi]
0x18038b92a  mov     rbx, [rax+30h]
0x18038b92e  mov     rcx, [rbp+57h+var_70]; string
0x18038b932  call    cs:__imp_WindowsDeleteString
0x18038b939  nop     dword ptr [rax+rax+00h]
0x18038b93e  mov     [rbp+57h+var_70], rsi
0x18038b942  mov     [rbp+57h+var_B0], rsi
0x18038b946  mov     r9d, 0Ch; unsigned int
0x18038b94c  lea     r8d, [r9+1]; unsigned int
0x18038b950  lea     rdx, aAbortkeyarg1; "abortKeyArg1"
0x18038b957  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18038b95b  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18038b960  nop
0x18038b961  lea     r8, [rbp+57h+var_70]
0x18038b965  mov     rdx, [rbp+57h+var_B0]
0x18038b969  mov     rcx, rdi
0x18038b96c  mov     rax, rbx
0x18038b96f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18038b974  mov     rcx, [rbp+5Fh]; this
0x18038b978  test    eax, eax
0x18038b97a  jns     short loc_18038B991
0x18038b97c  mov     r9d, eax; char *
0x18038b97f  lea     r8, aOnecoreuapShel_162; "onecoreuap\\shell\\windows.storage\\clo"...
0x18038b986  mov     edx, 1DCh; void *
0x18038b98b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18038b991  mov     rdi, [rbp+57h+var_80]
0x18038b995  mov     rax, [rdi]
0x18038b998  mov     rbx, [rax+30h]
0x18038b99c  mov     rcx, [rbp+57h+var_78]; string
0x18038b9a0  call    cs:__imp_WindowsDeleteString
0x18038b9a7  nop     dword ptr [rax+rax+00h]
0x18038b9ac  mov     [rbp+57h+var_78], rsi
0x18038b9b0  mov     [rbp+57h+var_B0], rsi
0x18038b9b4  mov     r9d, 0Ch; unsigned int
0x18038b9ba  lea     r8d, [r9+1]; unsigned int
0x18038b9be  lea     rdx, aAbortkeyarg2; "abortKeyArg2"
0x18038b9c5  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18038b9c9  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18038b9ce  nop
0x18038b9cf  lea     r8, [rbp+57h+var_78]
0x18038b9d3  mov     rdx, [rbp+57h+var_B0]
0x18038b9d7  mov     rcx, rdi
0x18038b9da  mov     rax, rbx
0x18038b9dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18038b9e2  mov     rcx, [rbp+5Fh]; this
0x18038b9e6  test    eax, eax
0x18038b9e8  jns     short loc_18038B9FF
0x18038b9ea  mov     r9d, eax; char *
0x18038b9ed  lea     r8, aOnecoreuapShel_162; "onecoreuap\\shell\\windows.storage\\clo"...
0x18038b9f4  mov     edx, 1DDh; void *
0x18038b9f9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18038b9ff  lea     rcx, [rbp+57h+var_80]
0x18038ba03  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x18038ba08  nop
0x18038ba09  lea     rcx, [rbp+57h+var_58]
0x18038ba0d  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x18038ba12  mov     r9d, 4B5h; unsigned int
0x18038ba18  lea     rdx, aToastActionsAc; "/toast/actions/action[@id='button1']"
0x18038ba1f  mov     rcx, [r14]; struct Windows::Data::Xml::Dom::IXmlDocument *
0x18038ba22  call    ?SetXmlAttributeFromResource@@YAJPEAUIXmlDocument@Dom@Xml@Data@Windows@@PEBG1I@Z; SetXmlAttributeFromResource(Windows::Data::Xml::Dom::IXmlDocument *,ushort const *,ushort const *,uint)
0x18038ba27  mov     rcx, [rbp+5Fh]; this
0x18038ba2b  test    eax, eax
0x18038ba2d  jns     short loc_18038BA44
0x18038ba2f  mov     r9d, eax; char *
0x18038ba32  lea     r8, aOnecoreuapShel_162; "onecoreuap\\shell\\windows.storage\\clo"...
0x18038ba39  mov     edx, 1E2h; void *
0x18038ba3e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18038ba44  mov     r9d, 4BCh; unsigned int
0x18038ba4a  lea     rdx, aToastActionsAc_0; "/toast/actions/action[@id='button2']"
0x18038ba51  mov     rcx, [r14]; struct Windows::Data::Xml::Dom::IXmlDocument *
0x18038ba54  call    ?SetXmlAttributeFromResource@@YAJPEAUIXmlDocument@Dom@Xml@Data@Windows@@PEBG1I@Z; SetXmlAttributeFromResource(Windows::Data::Xml::Dom::IXmlDocument *,ushort const *,ushort const *,uint)
0x18038ba59  mov     rcx, [rbp+5Fh]; this
0x18038ba5d  test    eax, eax
0x18038ba5f  jns     short loc_18038BA76
0x18038ba61  mov     r9d, eax; char *
0x18038ba64  lea     r8, aOnecoreuapShel_162; "onecoreuap\\shell\\windows.storage\\clo"...
0x18038ba6b  mov     edx, 1E3h; void *
0x18038ba70  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18038ba76  mov     qword ptr [rbp+57h+hstringHeader.Reserved], rsi
0x18038ba7a  mov     qword ptr [rbp+57h+hstringHeader.Reserved+8], rsi
0x18038ba7e  mov     qword ptr [rbp+57h+hstringHeader.Reserved+10h], rsi
0x18038ba82  lea     rdx, WindowName
0x18038ba89  mov     rcx, r12
0x18038ba8c  test    r12, r12
0x18038ba8f  cmovz   rcx, rdx
0x18038ba93  mov     rax, r15
0x18038ba96  test    r15, r15
0x18038ba99  cmovz   rax, rdx
0x18038ba9d  mov     [rsp+120h+var_D8], rcx
0x18038baa2  lea     rcx, asc_1807381CC; "$"
0x18038baa9  mov     [rsp+120h+var_E0], rcx
0x18038baae  mov     [rsp+120h+var_E8], rax
0x18038bab3  mov     [rsp+120h+var_F0], rcx
0x18038bab8  mov     [rsp+120h+var_F8], r13
0x18038babd  mov     [rsp+120h+var_100], rcx; int
0x18038bac2  lea     r9, aToastConfirmBo; "Toast.Confirm.Body"
0x18038bac9  mov     r8, rcx
0x18038bacc  lea     rdx, aSSSSSSSS; "%s%s%s%s%s%s%s%s"
0x18038bad3  lea     rcx, [rbp+57h+hstringHeader]
0x18038bad7  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x18038badc  mov     rcx, [rbp+5Fh]; this
0x18038bae0  test    eax, eax
0x18038bae2  jns     short loc_18038BAF9
0x18038bae4  mov     r9d, eax; char *
0x18038bae7  lea     r8, aOnecoreuapShel_162; "onecoreuap\\shell\\windows.storage\\clo"...
0x18038baee  mov     edx, 1F0h; void *
0x18038baf3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18038baf9  mov     r9, qword ptr [rbp+57h+hstringHeader.Reserved]; unsigned __int16 *
0x18038bafd  lea     r8, aLaunch_0; "launch"
0x18038bb04  lea     rdx, aToast; "/toast"
0x18038bb0b  mov     rcx, [r14]; struct Windows::Data::Xml::Dom::IXmlDocument *
0x18038bb0e  call    ?SetXmlAttribute@@YAJPEAUIXmlDocument@Dom@Xml@Data@Windows@@PEBG11@Z; SetXmlAttribute(Windows::Data::Xml::Dom::IXmlDocument *,ushort const *,ushort const *,ushort const *)
0x18038bb13  mov     rcx, [rbp+5Fh]; this
0x18038bb17  test    eax, eax
0x18038bb19  jns     short loc_18038BB30
0x18038bb1b  mov     r9d, eax; char *
0x18038bb1e  lea     r8, aOnecoreuapShel_162; "onecoreuap\\shell\\windows.storage\\clo"...
0x18038bb25  mov     edx, 1F1h; void *
0x18038bb2a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18038bb30  mov     [rbp+57h+var_A0], rsi
0x18038bb34  mov     [rbp+57h+var_98], rsi
0x18038bb38  mov     [rbp+57h+var_90], rsi
0x18038bb3c  xor     edx, edx; length
0x18038bb3e  mov     rcx, [rbp+57h+var_78]; string
0x18038bb42  call    cs:__imp_WindowsGetStringRawBuffer
0x18038bb49  nop     dword ptr [rax+rax+00h]
0x18038bb4e  mov     rsi, rax
0x18038bb51  xor     edx, edx; length
0x18038bb53  mov     rcx, [rbp+57h+var_70]; string
0x18038bb57  call    cs:__imp_WindowsGetStringRawBuffer
0x18038bb5e  nop     dword ptr [rax+rax+00h]
0x18038bb63  mov     rdi, rax
0x18038bb66  xor     edx, edx; length
0x18038bb68  mov     rcx, [rbp+57h+var_68]; string
0x18038bb6c  call    cs:__imp_WindowsGetStringRawBuffer
0x18038bb73  nop     dword ptr [rax+rax+00h]
0x18038bb78  mov     rbx, rax
0x18038bb7b  xor     edx, edx; length
0x18038bb7d  mov     rcx, [rbp+57h+string]; string
0x18038bb81  call    cs:__imp_WindowsGetStringRawBuffer
0x18038bb88  nop     dword ptr [rax+rax+00h]
0x18038bb8d  mov     [rsp+120h+var_E0], rsi
0x18038bb92  lea     r9, asc_1807381CC; "$"
0x18038bb99  mov     [rsp+120h+var_E8], r9
0x18038bb9e  mov     [rsp+120h+var_F0], rdi
0x18038bba3  mov     [rsp+120h+var_F8], r9
0x18038bba8  mov     [rsp+120h+var_100], rbx; int
0x18038bbad  mov     r8, rax
0x18038bbb0  lea     rdx, aSSSSSSS; "%s%s%s%s%s%s%s"
0x18038bbb7  lea     rcx, [rbp+57h+var_A0]
0x18038bbbb  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x18038bbc0  mov     rcx, [rbp+5Fh]; this
  ... truncated ...
```
