# _lambda_64f2ac5619e08f59fc2531d6f89a2aed_::operator()(void)

- ea: `0x14002fe9c`
- end: `0x140030af6`
- name: `??R_lambda_64f2ac5619e08f59fc2531d6f89a2aed_@@QEBA@XZ`
- size: `3162`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation`

## callers

- `0x140032aa0`

## callees

- `0x140005530`
- `0x1400089e0`
- `0x14000ccac`
- `0x14002a6ac`
- `0x14002aa68`
- `0x14002f2e0`
- `0x14002fe9c`
- `0x140030ee4`
- `0x140030f24`
- `0x140031d90`
- `0x140031f68`
- `0x140048418`
- `0x140067b84`
- `0x140082c2c`
- `0x1400a8010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14002ff5c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140030092`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400301c6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140030264`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400303e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400304f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14003058f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140030712`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14003089f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400308c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14002ff5c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140030092`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400301c6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140030264`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400303e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400304f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14003058f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140030712`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14003089f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400308c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14002ff91`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14003014d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140030299`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14003046a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1400305c4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1400307e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14002ff91`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14003014d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140030299`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14003046a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1400305c4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1400307e6`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall _lambda_64f2ac5619e08f59fc2531d6f89a2aed_::operator()(__int64 a1)
{
  int (__fastcall ***v2)(_QWORD, GUID *, __int64 *); // r14
  __int64 *v3; // rbx
  int (__fastcall *v4)(_QWORD, GUID *, __int64 *); // rdi
  __int64 v5; // rcx
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, HSTRING *); // rbx
  int v8; // eax
  __int64 v9; // rbx
  PCWSTR v10; // rax
  __int64 v11; // rdi
  char v12; // al
  char v13; // bl
  int v14; // eax
  int v15; // eax
  int v16; // eax
  int v17; // eax
  __int64 v18; // rdi
  __int64 (__fastcall *v19)(__int64, HSTRING *); // rbx
  int v20; // eax
  __int64 v21; // rbx
  PCWSTR v22; // rax
  __int64 v23; // rcx
  __int64 v24; // rax
  __int64 v25; // rcx
  HSTRING v26; // rcx
  __int64 *v27; // rbx
  int (__fastcall *v28)(_QWORD, GUID *, __int64 *); // rdi
  __int64 v29; // rcx
  __int64 v30; // rdi
  __int64 (__fastcall *v31)(__int64, HSTRING *); // rbx
  int v32; // eax
  __int64 v33; // rbx
  PCWSTR v34; // rax
  __int64 v35; // rdi
  char v36; // al
  char v37; // bl
  int v38; // eax
  int v39; // eax
  int v40; // eax
  int v41; // eax
  int v42; // eax
  int v43; // eax
  __int64 v44; // rdi
  __int64 (__fastcall *v45)(__int64, HSTRING *); // rbx
  int v46; // eax
  wpc::AppTimeLimits::UI::UICallbackImpl *v47; // rbx
  PCWSTR v48; // rax
  __int64 v49; // rcx
  const struct appids::AnyRuntimeApp *v50; // rax
  __int64 v51; // rcx
  __int64 *v52; // rbx
  int (__fastcall *v53)(_QWORD, GUID *, __int64 *); // rdi
  __int64 v54; // rcx
  __int64 v55; // rdi
  __int64 (__fastcall *v56)(__int64, HSTRING *); // rbx
  int v57; // eax
  __int64 v58; // rbx
  PCWSTR StringRawBuffer; // rax
  __int64 v60; // rdi
  char v61; // al
  char v62; // bl
  int v63; // eax
  int v64; // eax
  int v65; // eax
  int v66; // eax
  int v67; // eax
  int v68; // eax
  __int64 v69; // rdi
  __int64 (__fastcall *v70)(__int64, HSTRING *); // rbx
  int v71; // eax
  wpc::AppTimeLimits::UI::UICallbackImpl *v72; // r15
  PCWSTR *v73; // rax
  _BYTE *v74; // rcx
  bool v75; // di
  PCWSTR v76; // rax
  __int64 v77; // rcx
  const struct appids::AnyRuntimeApp *v78; // rdx
  const struct appids::AnyRuntimeApp *v79; // rbx
  __int64 v80; // rcx
  int v82; // [rsp+20h] [rbp-E0h]
  char v83[4]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v84; // [rsp+44h] [rbp-BCh] BYREF
  unsigned int v85; // [rsp+48h] [rbp-B8h] BYREF
  HSTRING v86; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v87; // [rsp+58h] [rbp-A8h] BYREF
  HSTRING string; // [rsp+60h] [rbp-A0h] BYREF
  int v89; // [rsp+68h] [rbp-98h] BYREF
  __int64 v90; // [rsp+70h] [rbp-90h] BYREF
  __int64 v91; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v92[2]; // [rsp+80h] [rbp-80h] BYREF
  PCWSTR v93; // [rsp+90h] [rbp-70h] BYREF
  __int64 v94; // [rsp+98h] [rbp-68h] BYREF
  const WCHAR *v95; // [rsp+A0h] [rbp-60h] BYREF
  int v96; // [rsp+A8h] [rbp-58h]
  const WCHAR *v97; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD v98[3]; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v99; // [rsp+D0h] [rbp-30h] BYREF
  char *v100; // [rsp+E0h] [rbp-20h]
  PCWSTR v101; // [rsp+F4h] [rbp-Ch] BYREF
  int v102; // [rsp+FCh] [rbp-4h]
  struct DateTime *v103; // [rsp+100h] [rbp+0h]
  char v104[8]; // [rsp+110h] [rbp+10h] BYREF
  char *v105[4]; // [rsp+118h] [rbp+18h] BYREF
  char v106; // [rsp+138h] [rbp+38h]
  char *v107[3]; // [rsp+140h] [rbp+40h] BYREF
  char *v108[5]; // [rsp+158h] [rbp+58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+B8h]

  v2 = **(int (__fastcall *****)(_QWORD, GUID *, __int64 *))a1;
  v98[1] = v2;
  if ( v2 )
    ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v2)[1])(v2);
  v3 = *(__int64 **)(a1 + 8);
  v4 = **v2;
  v5 = *v3;
  if ( *v3 )
  {
    *v3 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  }
  if ( v4(v2, &GUID_a8290aa4_d64b_406f_a404_0af939c3a81f, v3) < 0 )
  {
    v27 = *(__int64 **)(a1 + 24);
    v28 = **v2;
    v29 = *v27;
    if ( *v27 )
    {
      *v27 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
    }
    if ( v28(v2, &GUID_427c042a_4508_4606_81f6_59fe8004c909, v27) < 0 )
    {
      v52 = *(__int64 **)(a1 + 32);
      v53 = **v2;
      v54 = *v52;
      if ( *v52 )
      {
        *v52 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
      }
      if ( v53(v2, &GUID_ef24ee0b_5322_455c_bfb3_1413ea776828, v52) < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x132,
          (unsigned int)"pcshell\\shell\\wpc\\monitor\\apptimelimitsviewstatecontroller.cpp",
          (const char *)0x80070057LL,
          v82);
      v86 = 0;
      v87 = 0;
      v84 = 0;
      v85 = 0;
      v83[0] = 0;
      v90 = 0;
      v97 = 0;
      v55 = **(_QWORD **)(a1 + 32);
      v56 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v55 + 48LL);
      WindowsDeleteString(0);
      v86 = 0;
      v57 = v56(v55, &v86);
      if ( v57 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x117,
          (unsigned int)"pcshell\\shell\\wpc\\monitor\\apptimelimitsviewstatecontroller.cpp",
          (const char *)(unsigned int)v57,
          v82);
      v58 = *(_QWORD *)(a1 + 16);
      StringRawBuffer = WindowsGetStringRawBuffer(v86, 0);
      v60 = Sid::FromString(v104, StringRawBuffer) + 72;
      if ( (unsigned __int8)std::operator<<unsigned short>(v58 + 160, v60)
        || (v61 = std::operator<<unsigned short>(v60, v58 + 160), v62 = 1, v61) )
      {
        v62 = 0;
      }
      std::wstring::~wstring(v108);
      if ( v62 )
      {
        v63 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(***(_QWORD ***)(a1 + 32) + 56LL))(
                **(_QWORD **)(a1 + 32),
                &v87);
        if ( v63 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0x11B,
            (unsigned int)"pcshell\\shell\\wpc\\monitor\\apptimelimitsviewstatecontroller.cpp",
            (const char *)(unsigned int)v63,
            v82);
        v64 = (*(__int64 (__fastcall **)(_QWORD, char *))(***(_QWORD ***)(a1 + 32) + 64LL))(**(_QWORD **)(a1 + 32), v83);
        if ( v64 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0x11C,
            (unsigned int)"pcshell\\shell\\wpc\\monitor\\apptimelimitsviewstatecontroller.cpp",
            (const char *)(unsigned int)v64,
            v82);
        v65 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(***(_QWORD ***)(a1 + 32) + 72LL))(
                **(_QWORD **)(a1 + 32),
                &v84);
        if ( v65 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0x11D,
            (unsigned int)"pcshell\\shell\\wpc\\monitor\\apptimelimitsviewstatecontroller.cpp",
            (const char *)(unsigned int)v65,
            v82);
        v66 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(***(_QWORD ***)(a1 + 32) + 80LL))(
                **(_QWORD **)(a1 + 32),
                &v90);
        if ( v66 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0x11E,
            (unsigned int)"pcshell\\shell\\wpc\\monitor\\apptimelimitsviewstatecontroller.cpp",
            (const char *)(unsigned int)v66,
            v82);
        v67 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(***(_QWORD ***)(a1 + 32) + 88LL))(
                **(_QWORD **)(a1 + 32),
                &v85);
        if ( v67 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0x11F,
            (unsigned int)"pcshell\\shell\\wpc\\monitor\\apptimelimitsviewstatecontroller.cpp",
            (const char *)(unsigned int)v67,
            v82);
        v68 = (*(__int64 (__fastcall **)(_QWORD, const WCHAR **))(***(_QWORD ***)(a1 + 32) + 96LL))(
                **(_QWORD **)(a1 + 32),
                &v97);
        if ( v68 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0x120,
            (unsigned int)"pcshell\\shell\\wpc\\monitor\\apptimelimitsviewstatecontroller.cpp",
            (const char *)(unsigned int)v68,
            v82);
        string = 0;
        v69 = v87;
        v70 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v87 + 48LL);
        WindowsDeleteString(0);
        string = 0;
        v71 = v70(v69, &string);
        if ( v71 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0x123,
            (unsigned int)"pcshell\\shell\\wpc\\monitor\\apptimelimitsviewstatecontroller.cpp",
            (const char *)(unsigned int)v71,
            v82);
        v72 = *(wpc::AppTimeLimits::UI::UICallbackImpl **)(*(_QWORD *)(a1 + 16) + 72LL);
        v98[0] = v97;
        v89 = wpc::AppTimeLimits::UI::EnforcementReasonFromTimeUsageEnforcementReason(v85);
        if ( v90 )
        {
          v92[0] = v90;
          DateTime::DateTime(&v95, v92, 0);
          v93 = v95;
          LODWORD(v94) = v96;
          BYTE4(v94) = 1;
          v73 = &v93;
          v74 = (char *)&v94 + 4;
        }
        else
        {
          BYTE12(v99) = 0;
          v73 = (PCWSTR *)&v99;
          v74 = (char *)&v99 + 12;
        }
        if ( *v74 )
        {
          v101 = *v73;
          v102 = *((_DWORD *)v73 + 2);
          v103 = (struct DateTime *)&v101;
        }
        else
        {
          v103 = 0;
        }
        LODWORD(v91) = wpc::AppTimeLimits::UI::EnforcementReasonFromTimeUsageEnforcementReason(v84);
        v75 = v83[0] != 0;
        v76 = WindowsGetStringRawBuffer(string, 0);
        v77 = -1;
        do
          ++v77;
        while ( v76[v77] );
        *(_QWORD *)&v99 = v76;
        *((_QWORD *)&v99 + 1) = v77;
        v79 = (const struct appids::AnyRuntimeApp *)appids::AnyRuntimeApp::FromPlatformIndependentId(v104, &v99);
        if ( v103 && v75 )
        {
          v95 = (const WCHAR *)v98[0];
          wpc::AppTimeLimits::UI::UICallbackImpl::ShowWarning(
            v72,
            (const struct Sid *)(*(_QWORD *)(a1 + 16) + 88LL),
            v79,
            (const enum wpc::TimeLimits::EnforcementReason *)&v91,
            v103,
            (const enum wpc::TimeLimits::EnforcementReason *)&v89,
            (const struct TimeSpan *)v98,
            (const struct TimeSpan *)&v95);
        }
        else
        {
          wpc::AppTimeLimits::UI::ToastNotification::ClearAppTimeLimitToast(v79, v78);
          wpc::UI::Logging::MonitorUILogger::LogClearToast(v79);
        }
        wpc::UI::Logging::MonitorUILogger::LogShowInfo(v79);
        std::wstring::~wstring(v107);
        if ( v106 != -1 )
          std::wstring::~wstring(v105);
        WindowsDeleteString(string);
      }
      v80 = v87;
      if ( v87 )
      {
        v87 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v80 + 16LL))(v80);
      }
    }
    else
    {
      v86 = 0;
      v87 = 0;
      v84 = 0;
      v85 = 0;
      v90 = 0;
      v97 = 0;
      v92[0] = 0;
      v30 = **(_QWORD **)(a1 + 24);
      v31 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v30 + 48LL);
      WindowsDeleteString(0);
      v86 = 0;
      v32 = v31(v30, &v86);
      if ( v32 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0xF5,
          (unsigned int)"pcshell\\shell\\wpc\\monitor\\apptimelimitsviewstatecontroller.cpp",
          (const char *)(unsigned int)v32,
          v82);
      v33 = *(_QWORD *)(a1 + 16);
      v34 = WindowsGetStringRawBuffer(v86, 0);
      v35 = Sid::FromString(v104, v34) + 72;
      if ( (unsigned __int8)std::operator<<unsigned short>(v33 + 160, v35)
        || (v36 = std::operator<<unsigned short>(v35, v33 + 160), v37 = 1, v36) )
      {
        v37 = 0;
      }
      std::wstring::~wstring(v108);
      if ( v37 )
      {
        v38 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(***(_QWORD ***)(a1 + 24) + 56LL))(
                **(_QWORD **)(a1 + 24),
                &v87);
        if ( v38 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0xF9,
            (unsigned int)"pcshell\\shell\\wpc\\monitor\\apptimelimitsviewstatecontroller.cpp",
            (const char *)(unsigned int)v38,
            v82);
        v39 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(***(_QWORD ***)(a1 + 24) + 64LL))(
                **(_QWORD **)(a1 + 24),
                &v84);
        if ( v39 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0xFA,
            (unsigned int)"pcshell\\shell\\wpc\\monitor\\apptimelimitsviewstatecontroller.cpp",
            (const char *)(unsigned int)v39,
            v82);
        v40 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(***(_QWORD ***)(a1 + 24) + 72LL))(
                **(_QWORD **)(a1 + 24),
                &v90);
        if ( v40 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0xFB,
            (unsigned int)"pcshell\\shell\\wpc\\monitor\\apptimelimitsviewstatecontroller.cpp",
            (const char *)(unsigned int)v40,
            v82);
        v41 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(***(_QWORD ***)(a1 + 24) + 80LL))(
                **(_QWORD **)(a1 + 24),
                &v85);
        if ( v41 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0xFC,
            (unsigned int)"pcshell\\shell\\wpc\\monitor\\apptimelimitsviewstatecontroller.cpp",
            (const char *)(unsigned int)v41,
            v82);
        v42 = (*(__int64 (__fastcall **)(_QWORD, const WCHAR **))(***(_QWORD ***)(a1 + 24) + 88LL))(
                **(_QWORD **)(a1 + 24),
                &v97);
        if ( v42 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0xFD,
            (unsigned int)"pcshell\\shell\\wpc\\monitor\\apptimelimitsviewstatecontroller.cpp",
            (const char *)(unsigned int)v42,
            v82);
        v43 = (*(__int64 (__fastcall **)(_QWORD, _QWORD *))(***(_QWORD ***)(a1 + 24) + 96LL))(
                **(_QWORD **)(a1 + 24),
                v92);
        if ( v43 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0xFE,
            (unsigned int)"pcshell\\shell\\wpc\\monitor\\apptimelimitsviewstatecontroller.cpp",
            (const char *)(unsigned int)v43,
            v82);
        string = 0;
        v44 = v87;
        v45 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v87 + 48LL);
        WindowsDeleteString(0);
        string = 0;
        v46 = v45(v44, &string);
        if ( v46 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0x101,
            (unsigned int)"pcshell\\shell\\wpc\\monitor\\apptimelimitsviewstatecontroller.cpp",
            (const char *)(unsigned int)v46,
            v82);
        v47 = *(wpc::AppTimeLimits::UI::UICallbackImpl **)(*(_QWORD *)(a1 + 16) + 72LL);
        v98[0] = v92[0];
        v95 = v97;
        v89 = wpc::AppTimeLimits::UI::EnforcementReasonFromTimeUsageEnforcementReason(v85);
        v91 = v90;
        DateTime::DateTime(&v93, &v91, 0);
        LODWORD(v91) = wpc::AppTimeLimits::UI::EnforcementReasonFromTimeUsageEnforcementReason(v84);
        v48 = WindowsGetStringRawBuffer(string, 0);
        v49 = -1;
        do
          ++v49;
        while ( v48[v49] );
        *(_QWORD *)&v99 = v48;
        *((_QWORD *)&v99 + 1) = v49;
        v50 = (const struct appids::AnyRuntimeApp *)appids::AnyRuntimeApp::FromPlatformIndependentId(v104, &v99);
        wpc::AppTimeLimits::UI::UICallbackImpl::ShowWarning(
          v47,
          (const struct Sid *)(*(_QWORD *)(a1 + 16) + 88LL),
          v50,
          (const enum wpc::TimeLimits::EnforcementReason *)&v91,
          (const struct DateTime *)&v93,
          (const enum wpc::TimeLimits::EnforcementReason *)&v89,
          (const struct TimeSpan *)&v95,
          (const struct TimeSpan *)v98);
        std::wstring::~wstring(v107);
        if ( v106 != -1 )
          std::wstring::~wstring(v105);
        WindowsDeleteString(string);
      }
      v51 = v87;
      if ( v87 )
      {
        v87 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
      }
    }
    v26 = v86;
  }
  else
  {
    string = 0;
    v87 = 0;
    v85 = 0;
    v84 = 0;
    v90 = 0;
    v6 = **(_QWORD **)(a1 + 8);
    v7 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v6 + 48LL);
    WindowsDeleteString(0);
    string = 0;
    v8 = v7(v6, &string);
    if ( v8 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0xD8,
        (unsigned int)"pcshell\\shell\\wpc\\monitor\\apptimelimitsviewstatecontroller.cpp",
        (const char *)(unsigned int)v8,
        v82);
    v9 = *(_QWORD *)(a1 + 16);
    v10 = WindowsGetStringRawBuffer(string, 0);
    v11 = Sid::FromString(v104, v10) + 72;
    if ( (unsigned __int8)std::operator<<unsigned short>(v9 + 160, v11)
      || (v12 = std::operator<<unsigned short>(v11, v9 + 160), v13 = 1, v12) )
    {
      v13 = 0;
    }
    std::wstring::~wstring(v108);
    if ( v13 )
    {
      v14 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(***(_QWORD ***)(a1 + 8) + 56LL))(**(_QWORD **)(a1 + 8), &v87);
      if ( v14 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0xDC,
          (unsigned int)"pcshell\\shell\\wpc\\monitor\\apptimelimitsviewstatecontroller.cpp",
          (const char *)(unsigned int)v14,
          v82);
      v15 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(***(_QWORD ***)(a1 + 8) + 64LL))(
              **(_QWORD **)(a1 + 8),
              &v85);
      if ( v15 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0xDD,
          (unsigned int)"pcshell\\shell\\wpc\\monitor\\apptimelimitsviewstatecontroller.cpp",
          (const char *)(unsigned int)v15,
          v82);
      v16 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(***(_QWORD ***)(a1 + 8) + 72LL))(**(_QWORD **)(a1 + 8), &v90);
      if ( v16 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0xDE,
          (unsigned int)"pcshell\\shell\\wpc\\monitor\\apptimelimitsviewstatecontroller.cpp",
          (const char *)(unsigned int)v16,
          v82);
      v17 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(***(_QWORD ***)(a1 + 8) + 80LL))(
              **(_QWORD **)(a1 + 8),
              &v84);
      if ( v17 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0xDF,
          (unsigned int)"pcshell\\shell\\wpc\\monitor\\apptimelimitsviewstatecontroller.cpp",
          (const char *)(unsigned int)v17,
          v82);
      v86 = 0;
      v18 = v87;
      v19 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v87 + 48LL);
      WindowsDeleteString(0);
      v86 = 0;
      v20 = v19(v18, &v86);
      if ( v20 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0xE2,
          (unsigned int)"pcshell\\shell\\wpc\\monitor\\apptimelimitsviewstatecontroller.cpp",
          (const char *)(unsigned int)v20,
          v82);
      v21 = *(_QWORD *)(*(_QWORD *)(a1 + 16) + 72LL);
      LODWORD(v91) = wpc::AppTimeLimits::UI::EnforcementReasonFromTimeUsageEnforcementReason(v84);
      if ( v90 )
      {
        v92[0] = v90;
        DateTime::DateTime(&v95, v92, 0);
        v93 = v95;
        LODWORD(v94) = v96;
        BYTE4(v94) = 1;
      }
      else
      {
        BYTE4(v94) = 0;
      }
      if ( BYTE4(v94) )
      {
        *(_QWORD *)((char *)&v99 + 4) = v93;
        HIDWORD(v99) = v94;
        v100 = (char *)&v99 + 4;
      }
      else
      {
        v100 = 0;
      }
      v89 = wpc::AppTimeLimits::UI::EnforcementReasonFromTimeUsageEnforcementReason(v85);
      v22 = WindowsGetStringRawBuffer(v86, 0);
      v23 = -1;
      do
        ++v23;
      while ( v22[v23] );
      v93 = v22;
      v94 = v23;
      v24 = appids::AnyRuntimeApp::FromPlatformIndependentId(v104, &v93);
      wpc::AppTimeLimits::UI::UICallbackImpl::ShowDisallowed(v21, *(_QWORD *)(a1 + 16) + 88LL, v24, &v89, &v99, &v91);
      std::wstring::~wstring(v107);
      if ( v106 != -1 )
        std::wstring::~wstring(v105);
      WindowsDeleteString(v86);
    }
    v25 = v87;
    if ( v87 )
    {
      v87 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    }
    v26 = string;
  }
  WindowsDeleteString(v26);
  return ((__int64 (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v2)[2])(v2);
}

```

## disassembly

```asm
0x14002fe9c  mov     [rsp-8+arg_8], rbx
0x14002fea1  mov     [rsp-8+arg_10], rsi
0x14002fea6  push    rbp
0x14002fea7  push    rdi
0x14002fea8  push    r12
0x14002feaa  push    r14
0x14002feac  push    r15
0x14002feae  lea     rbp, [rsp-90h]
0x14002feb6  sub     rsp, 190h
0x14002febd  mov     rax, cs:__security_cookie
0x14002fec4  xor     rax, rsp
0x14002fec7  mov     [rbp+0B0h+var_30], rax
0x14002fece  mov     rsi, rcx
0x14002fed1  mov     rax, [rcx]
0x14002fed4  mov     r14, [rax]
0x14002fed7  mov     [rbp+0B0h+var_F0], r14
0x14002fedb  xor     r12d, r12d
0x14002fede  test    r14, r14
0x14002fee1  jz      short loc_14002FEF3
0x14002fee3  mov     rax, [r14]
0x14002fee6  mov     rcx, r14
0x14002fee9  mov     rax, [rax+8]
0x14002feed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002fef2  nop
0x14002fef3  mov     rbx, [rsi+8]
0x14002fef7  mov     rax, [r14]
0x14002fefa  mov     rdi, [rax]
0x14002fefd  mov     rcx, [rbx]
0x14002ff00  test    rcx, rcx
0x14002ff03  jz      short loc_14002FF15
0x14002ff05  mov     [rbx], r12
0x14002ff08  mov     rdx, [rcx]
0x14002ff0b  mov     rax, [rdx+10h]
0x14002ff0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002ff14  nop
0x14002ff15  mov     r8, rbx
0x14002ff18  lea     rdx, _GUID_a8290aa4_d64b_406f_a404_0af939c3a81f
0x14002ff1f  mov     rcx, r14
0x14002ff22  mov     rax, rdi
0x14002ff25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002ff2a  nop
0x14002ff2b  test    eax, eax
0x14002ff2d  js      loc_1400301F3
0x14002ff33  mov     [rsp+1B0h+string], r12
0x14002ff38  mov     [rsp+1B0h+var_158], r12
0x14002ff3d  mov     [rsp+1B0h+var_168], r12d
0x14002ff42  mov     [rsp+1B0h+var_16C], r12d
0x14002ff47  mov     [rsp+1B0h+var_140], r12
0x14002ff4c  mov     rax, [rsi+8]
0x14002ff50  mov     rdi, [rax]
0x14002ff53  mov     rax, [rdi]
0x14002ff56  mov     rbx, [rax+30h]
0x14002ff5a  xor     ecx, ecx; string
0x14002ff5c  call    cs:__imp_WindowsDeleteString
0x14002ff62  mov     [rsp+1B0h+string], r12
0x14002ff67  lea     rdx, [rsp+1B0h+string]
0x14002ff6c  mov     rcx, rdi
0x14002ff6f  mov     rax, rbx
0x14002ff72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002ff77  mov     rcx, [rbp+0B8h]; this
0x14002ff7e  test    eax, eax
0x14002ff80  js      loc_14003093D
0x14002ff86  mov     rbx, [rsi+10h]
0x14002ff8a  xor     edx, edx; length
0x14002ff8c  mov     rcx, [rsp+1B0h+string]; string
0x14002ff91  call    cs:__imp_WindowsGetStringRawBuffer
0x14002ff97  mov     rdx, rax
0x14002ff9a  lea     rcx, [rbp+0B0h+var_A0]
0x14002ff9e  call    ?FromString@Sid@@SA?AV1@PEBG@Z; Sid::FromString(ushort const *)
0x14002ffa3  lea     rdi, [rax+48h]
0x14002ffa7  mov     rdx, rdi
0x14002ffaa  lea     rcx, [rbx+0A0h]
0x14002ffb1  call    ??$?MGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@0@Z; std::operator<<ushort>(std::wstring const &,std::wstring const &)
0x14002ffb6  test    al, al
0x14002ffb8  jnz     short loc_14002FFCF
0x14002ffba  lea     rdx, [rbx+0A0h]
0x14002ffc1  mov     rcx, rdi
0x14002ffc4  call    ??$?MGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@0@Z; std::operator<<ushort>(std::wstring const &,std::wstring const &)
0x14002ffc9  test    al, al
0x14002ffcb  mov     bl, 1
0x14002ffcd  jz      short loc_14002FFD2
0x14002ffcf  mov     bl, r12b
0x14002ffd2  lea     rcx, [rbp+0B0h+var_58]
0x14002ffd6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14002ffdb  test    bl, bl
0x14002ffdd  jz      loc_1400301CD
0x14002ffe3  mov     rax, [rsi+8]
0x14002ffe7  mov     rcx, [rax]
0x14002ffea  mov     rax, [rcx]
0x14002ffed  lea     rdx, [rsp+1B0h+var_158]
0x14002fff2  mov     rax, [rax+38h]
0x14002fff6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002fffb  mov     rcx, [rbp+0B8h]; this
0x140030002  test    eax, eax
0x140030004  js      loc_140030952
0x14003000a  mov     rax, [rsi+8]
0x14003000e  mov     rcx, [rax]
0x140030011  mov     rax, [rcx]
0x140030014  lea     rdx, [rsp+1B0h+var_168]
0x140030019  mov     rax, [rax+40h]
0x14003001d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140030022  mov     rcx, [rbp+0B8h]; this
0x140030029  test    eax, eax
0x14003002b  js      loc_140030967
0x140030031  mov     rax, [rsi+8]
0x140030035  mov     rcx, [rax]
0x140030038  mov     rax, [rcx]
0x14003003b  lea     rdx, [rsp+1B0h+var_140]
0x140030040  mov     rax, [rax+48h]
0x140030044  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140030049  mov     rcx, [rbp+0B8h]; this
0x140030050  test    eax, eax
0x140030052  js      loc_14003097C
0x140030058  mov     rax, [rsi+8]
0x14003005c  mov     rcx, [rax]
0x14003005f  mov     rax, [rcx]
0x140030062  lea     rdx, [rsp+1B0h+var_16C]
0x140030067  mov     rax, [rax+50h]
0x14003006b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140030070  mov     rcx, [rbp+0B8h]; this
0x140030077  test    eax, eax
0x140030079  js      loc_140030991
0x14003007f  mov     [rsp+1B0h+var_160], r12
0x140030084  mov     rdi, [rsp+1B0h+var_158]
0x140030089  mov     rax, [rdi]
0x14003008c  mov     rbx, [rax+30h]
0x140030090  xor     ecx, ecx; string
0x140030092  call    cs:__imp_WindowsDeleteString
0x140030098  mov     [rsp+1B0h+var_160], r12
0x14003009d  lea     rdx, [rsp+1B0h+var_160]
0x1400300a2  mov     rcx, rdi
0x1400300a5  mov     rax, rbx
0x1400300a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400300ad  mov     rcx, [rbp+0B8h]; this
0x1400300b4  test    eax, eax
0x1400300b6  js      loc_1400309A6
0x1400300bc  mov     rax, [rsi+10h]
0x1400300c0  mov     rbx, [rax+48h]
0x1400300c4  mov     ecx, [rsp+1B0h+var_16C]
0x1400300c8  call    ?EnforcementReasonFromTimeUsageEnforcementReason@UI@AppTimeLimits@wpc@@YA?AW4EnforcementReason@TimeLimits@3@W4TimeUsageEnforcementReason@FamilySafety@Internal@Windows@@@Z; wpc::AppTimeLimits::UI::EnforcementReasonFromTimeUsageEnforcementReason(Windows::Internal::FamilySafety::TimeUsageEnforcementReason)
0x1400300cd  mov     dword ptr [rsp+1B0h+var_138], eax
0x1400300d1  mov     rax, [rsp+1B0h+var_140]
0x1400300d6  test    rax, rax
0x1400300d9  jnz     short loc_1400300E1
0x1400300db  mov     byte ptr [rbp+0B0h+var_118+4], r12b
0x1400300df  jmp     short loc_14003010F
0x1400300e1  mov     ecx, dword ptr [rsp+1B0h+var_140+4]
0x1400300e5  mov     dword ptr [rbp+0B0h+var_130], eax
0x1400300e8  mov     dword ptr [rbp+0B0h+var_130+4], ecx
0x1400300eb  xor     r8d, r8d
0x1400300ee  lea     rdx, [rbp+0B0h+var_130]
0x1400300f2  lea     rcx, [rbp+0B0h+var_110]
0x1400300f6  call    ??0DateTime@@QEAA@AEBU_FILETIME@@W4TimeType@@@Z; DateTime::DateTime(_FILETIME const &,TimeType)
0x1400300fb  movsd   xmm0, [rbp+0B0h+var_110]
0x140030100  movsd   [rbp+0B0h+var_120], xmm0
0x140030105  mov     eax, [rbp+0B0h+var_108]
0x140030108  mov     dword ptr [rbp+0B0h+var_118], eax
0x14003010b  mov     byte ptr [rbp+0B0h+var_118+4], 1
0x14003010f  lea     rcx, [rbp+0B0h+var_118+4]
0x140030113  lea     rax, [rbp+0B0h+var_120]
0x140030117  cmp     [rcx], r12b
0x14003011a  jz      short loc_140030135
0x14003011c  movsd   xmm0, qword ptr [rax]
0x140030120  movsd   [rbp+0B0h+var_E0+4], xmm0
0x140030125  mov     eax, [rax+8]
0x140030128  mov     [rbp+0B0h+var_D4], eax
0x14003012b  lea     rax, [rbp+0B0h+var_E0+4]
0x14003012f  mov     [rbp+0B0h+var_D0], rax
0x140030133  jmp     short loc_140030139
0x140030135  mov     [rbp+0B0h+var_D0], r12
0x140030139  mov     ecx, [rsp+1B0h+var_168]
0x14003013d  call    ?EnforcementReasonFromTimeUsageEnforcementReason@UI@AppTimeLimits@wpc@@YA?AW4EnforcementReason@TimeLimits@3@W4TimeUsageEnforcementReason@FamilySafety@Internal@Windows@@@Z; wpc::AppTimeLimits::UI::EnforcementReasonFromTimeUsageEnforcementReason(Windows::Internal::FamilySafety::TimeUsageEnforcementReason)
0x140030142  mov     [rsp+1B0h+var_148], eax
0x140030146  xor     edx, edx; length
0x140030148  mov     rcx, [rsp+1B0h+var_160]; string
0x14003014d  call    cs:__imp_WindowsGetStringRawBuffer
0x140030153  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140030157  inc     rcx
0x14003015a  cmp     [rax+rcx*2], r12w
0x14003015f  jnz     short loc_140030157
0x140030161  mov     [rbp+0B0h+var_120], rax
0x140030165  mov     [rbp+0B0h+var_118], rcx
0x140030169  lea     rdx, [rbp+0B0h+var_120]
0x14003016d  lea     rcx, [rbp+0B0h+var_A0]
0x140030171  call    ?FromPlatformIndependentId@AnyRuntimeApp@appids@@SA?AV12@V?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; appids::AnyRuntimeApp::FromPlatformIndependentId(std::basic_string_view<ushort>)
0x140030176  nop
0x140030177  mov     rdx, [rsi+10h]
0x14003017b  add     rdx, 58h ; 'X'
0x14003017f  lea     rcx, [rsp+1B0h+var_138]
0x140030184  mov     [rsp+1B0h+var_188], rcx
0x140030189  lea     rcx, [rbp+0B0h+var_E0]
0x14003018d  mov     [rsp+1B0h+var_190], rcx
0x140030192  lea     r9, [rsp+1B0h+var_148]
0x140030197  mov     r8, rax
0x14003019a  mov     rcx, rbx
0x14003019d  call    ?ShowDisallowed@UICallbackImpl@UI@AppTimeLimits@wpc@@QEAAXAEBVSid@@AEBVAnyRuntimeApp@appids@@AEBW4EnforcementReason@TimeLimits@4@AEBV?$Optional@VDateTime@@@@2@Z; wpc::AppTimeLimits::UI::UICallbackImpl::ShowDisallowed(Sid const &,appids::AnyRuntimeApp const &,wpc::TimeLimits::EnforcementReason const &,Optional<DateTime> const &,wpc::TimeLimits::EnforcementReason const &)
0x1400301a2  nop
0x1400301a3  lea     rcx, [rbp+0B0h+var_70]
0x1400301a7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400301ac  movsx   rax, [rbp+0B0h+var_78]
0x1400301b1  add     rax, 1
0x1400301b5  jz      short loc_1400301C1
0x1400301b7  lea     rcx, [rbp+0B0h+var_98]
0x1400301bb  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400301c0  nop
0x1400301c1  mov     rcx, [rsp+1B0h+var_160]; string
0x1400301c6  call    cs:__imp_WindowsDeleteString
0x1400301cc  nop
0x1400301cd  mov     rcx, [rsp+1B0h+var_158]
0x1400301d2  test    rcx, rcx
0x1400301d5  jz      short loc_1400301E9
0x1400301d7  mov     [rsp+1B0h+var_158], r12
0x1400301dc  mov     rax, [rcx]
0x1400301df  mov     rax, [rax+10h]
0x1400301e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400301e8  nop
0x1400301e9  mov     rcx, [rsp+1B0h+string]
0x1400301ee  jmp     loc_1400308C7
0x1400301f3  mov     rbx, [rsi+18h]
0x1400301f7  mov     rax, [r14]
0x1400301fa  mov     rdi, [rax]
0x1400301fd  mov     rcx, [rbx]
0x140030200  test    rcx, rcx
0x140030203  jz      short loc_140030215
0x140030205  mov     [rbx], r12
0x140030208  mov     rdx, [rcx]
0x14003020b  mov     rax, [rdx+10h]
0x14003020f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140030214  nop
0x140030215  mov     r8, rbx
0x140030218  lea     rdx, _GUID_427c042a_4508_4606_81f6_59fe8004c909
0x14003021f  mov     rcx, r14
0x140030222  mov     rax, rdi
0x140030225  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003022a  nop
0x14003022b  test    eax, eax
0x14003022d  js      loc_14003051D
0x140030233  mov     [rsp+1B0h+var_160], r12
0x140030238  mov     [rsp+1B0h+var_158], r12
0x14003023d  mov     [rsp+1B0h+var_16C], r12d
0x140030242  mov     [rsp+1B0h+var_168], r12d
0x140030247  mov     [rsp+1B0h+var_140], r12
0x14003024c  mov     [rbp+0B0h+var_100], r12
0x140030250  mov     [rbp+0B0h+var_130], r12
0x140030254  mov     rax, [rsi+18h]
0x140030258  mov     rdi, [rax]
0x14003025b  mov     rax, [rdi]
0x14003025e  mov     rbx, [rax+30h]
0x140030262  xor     ecx, ecx; string
0x140030264  call    cs:__imp_WindowsDeleteString
0x14003026a  mov     [rsp+1B0h+var_160], r12
0x14003026f  lea     rdx, [rsp+1B0h+var_160]
0x140030274  mov     rcx, rdi
0x140030277  mov     rax, rbx
0x14003027a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003027f  mov     rcx, [rbp+0B8h]; this
0x140030286  test    eax, eax
0x140030288  js      loc_1400309BB
0x14003028e  mov     rbx, [rsi+10h]
0x140030292  xor     edx, edx; length
0x140030294  mov     rcx, [rsp+1B0h+var_160]; string
0x140030299  call    cs:__imp_WindowsGetStringRawBuffer
0x14003029f  mov     rdx, rax
0x1400302a2  lea     rcx, [rbp+0B0h+var_A0]
0x1400302a6  call    ?FromString@Sid@@SA?AV1@PEBG@Z; Sid::FromString(ushort const *)
0x1400302ab  lea     rdi, [rax+48h]
0x1400302af  mov     rdx, rdi
0x1400302b2  lea     rcx, [rbx+0A0h]
0x1400302b9  call    ??$?MGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@0@Z; std::operator<<ushort>(std::wstring const &,std::wstring const &)
0x1400302be  test    al, al
0x1400302c0  jnz     short loc_1400302D7
0x1400302c2  lea     rdx, [rbx+0A0h]
0x1400302c9  mov     rcx, rdi
0x1400302cc  call    ??$?MGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@0@Z; std::operator<<ushort>(std::wstring const &,std::wstring const &)
0x1400302d1  test    al, al
0x1400302d3  mov     bl, 1
0x1400302d5  jz      short loc_1400302DA
0x1400302d7  mov     bl, r12b
0x1400302da  lea     rcx, [rbp+0B0h+var_58]
0x1400302de  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400302e3  test    bl, bl
0x1400302e5  jz      loc_1400304FC
0x1400302eb  mov     rax, [rsi+18h]
0x1400302ef  mov     rcx, [rax]
0x1400302f2  mov     rax, [rcx]
0x1400302f5  lea     rdx, [rsp+1B0h+var_158]
0x1400302fa  mov     rax, [rax+38h]
0x1400302fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140030303  mov     rcx, [rbp+0B8h]; this
0x14003030a  test    eax, eax
0x14003030c  js      loc_1400309D0
0x140030312  mov     rax, [rsi+18h]
0x140030316  mov     rcx, [rax]
0x140030319  mov     rax, [rcx]
0x14003031c  lea     rdx, [rsp+1B0h+var_16C]
0x140030321  mov     rax, [rax+40h]
0x140030325  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003032a  mov     rcx, [rbp+0B8h]; this
0x140030331  test    eax, eax
0x140030333  js      loc_1400309E5
  ... truncated ...
```
