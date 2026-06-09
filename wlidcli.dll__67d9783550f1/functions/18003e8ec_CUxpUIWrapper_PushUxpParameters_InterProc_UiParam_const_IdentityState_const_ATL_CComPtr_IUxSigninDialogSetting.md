# CUxpUIWrapper::__PushUxpParameters(_InterProc_UiParam * const,_IdentityState * const,ATL::CComPtr<IUxSigninDialogSettings> &)

- ea: `0x18003e8ec`
- end: `0x18003fb51`
- name: `?__PushUxpParameters@CUxpUIWrapper@@SAJQEAU_InterProc_UiParam@@QEAU_IdentityState@@AEAV?$CComPtr@UIUxSigninDialogSettings@@@ATL@@@Z`
- size: `4709`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003dd64`

## callees

- `0x18000a914`
- `0x18000af40`
- `0x18000ba8c`
- `0x18000be18`
- `0x18000cc9c`
- `0x18000e784`
- `0x18000e870`
- `0x180010b9c`
- `0x18003e8ec`
- `0x180053890`
- `0x180056144`
- `0x180063010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x18003f5e0`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x18003f5e0`

## string_xrefs

- `0x18003ece7`: `hr = spUxSigninDialogSettings->SetText(UXSigninControls::SignupLink, pUIParam->wszSignupText, false)`
- `0x18003ed28`: `hr = spUxSigninDialogSettings->SetTooltip(UXSigninControls::SignupLink, pUIParam->wszSignupTooltip)`
- `0x18003ed69`: `hr = spUxSigninDialogSettings->SetURL(UXSigninControls::SignupLink, pUIParam->wszSignupUrl)`
- `0x18003eda4`: `hr = spUxSigninDialogSettings->SetControlVisibility(UXSigninControls::SignupLink, TRUE == pUIParam->fSignupVisible)`
- `0x18003eef7`: `hr = spUxSigninDialogSettings->SetText(UXSigninControls::ForgotPasswordLink, pUIParam->wszForgotPasswordText, false)`
- `0x18003ef39`: `hr = spUxSigninDialogSettings->SetTooltip(UXSigninControls::ForgotPasswordLink, pUIParam->wszForgotPasswordTooltip)`
- `0x18003ef7b`: `hr = spUxSigninDialogSettings->SetURL(UXSigninControls::ForgotPasswordLink, pUIParam->wszForgotPasswordUrl)`
- `0x18003efb7`: `hr = spUxSigninDialogSettings->SetControlVisibility(UXSigninControls::ForgotPasswordLink, TRUE == pUIParam->fForgotPasswordVisible)`
- `0x18003f002`: `hr = spUxSigninDialogSettings->SetText(UXSigninControls::TOSLink, pUIParam->wszTOSText, false)`
- `0x18003f044`: `hr = spUxSigninDialogSettings->SetTooltip(UXSigninControls::TOSLink, pUIParam->wszTOSTooltip)`
- `0x18003f086`: `hr = spUxSigninDialogSettings->SetURL(UXSigninControls::TOSLink, pUIParam->wszTOSUrl)`
- `0x18003f0c2`: `hr = spUxSigninDialogSettings->SetControlVisibility(UXSigninControls::TOSLink, TRUE == pUIParam->fTOSVisible)`
- `0x18003f10d`: `hr = spUxSigninDialogSettings->SetText(UXSigninControls::PrivacyLink, pUIParam->wszPrivacyText, false)`
- `0x18003f14f`: `hr = spUxSigninDialogSettings->SetTooltip(UXSigninControls::PrivacyLink, pUIParam->wszPrivacyTooltip)`
- `0x18003f191`: `hr = spUxSigninDialogSettings->SetURL(UXSigninControls::PrivacyLink, pUIParam->wszPrivacyUrl)`
- `0x18003f1cd`: `hr = spUxSigninDialogSettings->SetControlVisibility(UXSigninControls::PrivacyLink, TRUE == pUIParam->fPrivacyVisible)`
- `0x18003f218`: `hr = spUxSigninDialogSettings->SetText(UXSigninControls::ServerStatusLink, pUIParam->wszServerStatusText, false)`
- `0x18003f25a`: `hr = spUxSigninDialogSettings->SetTooltip(UXSigninControls::ServerStatusLink, pUIParam->wszServerStatusTooltip)`
- `0x18003f29c`: `hr = spUxSigninDialogSettings->SetURL(UXSigninControls::ServerStatusLink, pUIParam->wszServerStatusUrl)`
- `0x18003f2d8`: `hr = spUxSigninDialogSettings->SetControlVisibility(UXSigninControls::ServerStatusLink, TRUE == pUIParam->fServerStatusVisible)`
- `0x18003f323`: `hr = spUxSigninDialogSettings->SetText(UXSigninControls::OptionsLink, pUIParam->wszOptionsText, false)`
- `0x18003f365`: `hr = spUxSigninDialogSettings->SetTooltip(UXSigninControls::OptionsLink, pUIParam->wszOptionsTooltip)`
- `0x18003f3a7`: `hr = spUxSigninDialogSettings->SetURL(UXSigninControls::OptionsLink, pUIParam->wszOptionsUrl)`
- `0x18003f3e3`: `hr = spUxSigninDialogSettings->SetControlVisibility(UXSigninControls::OptionsLink, TRUE == pUIParam->fOptionsVisible)`
- `0x18003f7df`: `hr = spUxSigninDialogSettings->SetText(UXSigninControls::MoreInfoLink, pUIParam->wszMoreInfoText, false)`
- `0x18003f821`: `hr = spUxSigninDialogSettings->SetTooltip(UXSigninControls::MoreInfoLink, pUIParam->wszMoreInfoTooltip)`
- `0x18003f863`: `hr = spUxSigninDialogSettings->SetURL(UXSigninControls::MoreInfoLink, pUIParam->wszMoreInfoUrl)`
- `0x18003f89f`: `hr = spUxSigninDialogSettings->SetControlVisibility(UXSigninControls::MoreInfoLink, TRUE == pUIParam->fMoreInfoVisible)`
- `0x18003fa92`: `hr = spUxSigninDialogSettings->SetControlVisibility(UXSigninControls::SignupLink, false)`

## pseudocode

```c
__int64 __fastcall CUxpUIWrapper::__PushUxpParameters(__int64 a1, __int64 a2, _QWORD *a3)
{
  __int64 v4; // rbx
  int LCID; // eax
  int v7; // eax
  _WORD *v8; // r8
  __int64 v9; // r9
  int v10; // eax
  __int64 v11; // rdx
  int v12; // eax
  _WORD *v13; // rdx
  int v14; // eax
  int v15; // eax
  int v16; // eax
  int v17; // eax
  _WORD *v18; // rdx
  int v19; // eax
  _WORD *v20; // rax
  int v21; // eax
  int v22; // eax
  _WORD *v23; // rdx
  int v24; // eax
  _WORD *v25; // rdx
  int v26; // eax
  _WORD *v27; // rdx
  int v28; // eax
  _WORD *v29; // r8
  int v30; // eax
  _WORD *v31; // r8
  int v32; // eax
  _WORD *v33; // r8
  int v34; // eax
  int v35; // eax
  _WORD *v36; // r8
  int v37; // eax
  _WORD *v38; // r8
  int v39; // eax
  _WORD *v40; // r8
  int v41; // eax
  int v42; // eax
  _WORD *v43; // r8
  int v44; // eax
  _WORD *v45; // r8
  int v46; // eax
  _WORD *v47; // r8
  int v48; // eax
  int v49; // eax
  _WORD *v50; // r8
  int v51; // eax
  _WORD *v52; // r8
  int v53; // eax
  _WORD *v54; // r8
  int v55; // eax
  int v56; // eax
  _WORD *v57; // r8
  int v58; // eax
  _WORD *v59; // r8
  int v60; // eax
  _WORD *v61; // r8
  int v62; // eax
  int v63; // eax
  _WORD *v64; // r8
  int v65; // eax
  _WORD *v66; // r8
  int v67; // eax
  _WORD *v68; // r8
  int v69; // eax
  int v70; // eax
  _WORD *v71; // r8
  int v72; // eax
  _WORD *v73; // r8
  int v74; // eax
  _WORD *v75; // r8
  int v76; // eax
  int v77; // eax
  _WORD *v78; // rax
  __int64 v79; // r8
  __int64 v80; // rdx
  __int64 v81; // rbx
  int *v82; // rdi
  __int64 v83; // rbx
  __int64 v84; // rdx
  __int64 v85; // rsi
  int *v86; // rdi
  __int64 v87; // rsi
  __int64 v88; // rdx
  wchar_t *v89; // rdi
  int *v90; // r12
  __int64 v91; // rdi
  ATL::CStringData *v92; // r13
  int v93; // r8d
  int v94; // eax
  __int64 v95; // rdx
  int *v96; // rdi
  __int64 v97; // rbx
  _WORD *v98; // r8
  int v99; // eax
  _WORD *v100; // r8
  int v101; // eax
  _WORD *v102; // r8
  int v103; // eax
  _WORD *v104; // r8
  int v105; // eax
  _WORD *v106; // r8
  int v107; // eax
  int v108; // eax
  _WORD *v109; // r8
  int v110; // eax
  int v111; // eax
  int v112; // eax
  int v113; // eax
  int v114; // eax
  int v115; // eax
  int v116; // eax
  int v117; // eax
  int v118; // eax
  int v119; // eax
  unsigned int v120; // ebx
  char *v122; // [rsp+20h] [rbp-59h]
  unsigned int v123; // [rsp+30h] [rbp-49h] BYREF
  __int64 v124; // [rsp+38h] [rbp-41h] BYREF
  wchar_t *String; // [rsp+40h] [rbp-39h] BYREF
  int v126; // [rsp+48h] [rbp-31h] BYREF
  __int64 v127; // [rsp+50h] [rbp-29h] BYREF
  __int64 v128; // [rsp+58h] [rbp-21h] BYREF
  __int64 v129; // [rsp+60h] [rbp-19h] BYREF
  __int64 v130; // [rsp+68h] [rbp-11h] BYREF
  __int64 v131; // [rsp+70h] [rbp-9h] BYREF
  _QWORD v132[11]; // [rsp+78h] [rbp-1h] BYREF
  int v134; // [rsp+F8h] [rbp+7Fh] BYREF

  v4 = a2;
  v134 = 0;
  v123 = 1033;
  v132[0] = "CUxpUIWrapper::__PushUxpParameters";
  v132[1] = &v134;
  v132[2] = 0;
  v132[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"clientcore\\ds\\ext\\live\\identity\\api\\classic\\uxpuiwrapper.cpp",
    "CUxpUIWrapper::__PushUxpParameters",
    (const char *)0x33A,
    0,
    (const unsigned __int16 *)v122);
  if ( !v4 || !*a3 )
  {
    v134 = -2147187932;
    goto LABEL_240;
  }
  LCID = CStringSrv::GetLCID(&v123);
  v134 = LCID;
  if ( LCID < 0 )
  {
    Telemetry::IfFailExit(
      "clientcore\\ds\\ext\\live\\identity\\api\\classic\\uxpuiwrapper.cpp",
      "CUxpUIWrapper::__PushUxpParameters",
      0x342u,
      LCID,
      "hr = CStringSrv::GetLCID(lcid)");
    goto LABEL_240;
  }
  v7 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*a3 + 40LL))(*a3, v123);
  v134 = v7;
  if ( v7 >= 0 )
  {
    if ( *(_QWORD *)v4
      && **(_WORD **)v4
      && (v10 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a3 + 24LL))(*a3), v134 = v10, v10 < 0) )
    {
      Telemetry::IfFailExit(
        "clientcore\\ds\\ext\\live\\identity\\api\\classic\\uxpuiwrapper.cpp",
        "CUxpUIWrapper::__PushUxpParameters",
        0x347u,
        v10,
        "hr = spUxSigninDialogSettings->SetUserName(pIdentityInfo->wszUserName)");
    }
    else
    {
      v11 = *(unsigned int *)(v4 + 8);
      if ( (int)v11 >= 0
        || (v12 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD))(*(_QWORD *)*a3 + 48LL))(
                    *a3,
                    v11,
                    *(_QWORD *)(v4 + 16),
                    *(_QWORD *)(v4 + 24)),
            v134 = v12,
            v12 >= 0) )
      {
        if ( a1 )
        {
          v13 = *(_WORD **)(a1 + 80);
          if ( v13 )
          {
            if ( *v13 )
            {
              v14 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a3 + 104LL))(*a3);
              v134 = v14;
              if ( v14 < 0 )
              {
                Telemetry::IfFailExit(
                  "clientcore\\ds\\ext\\live\\identity\\api\\classic\\uxpuiwrapper.cpp",
                  "CUxpUIWrapper::__PushUxpParameters",
                  0x356u,
                  v14,
                  "hr = spUxSigninDialogSettings->SetWindowText(pUIParam->wszWindowTitle)");
                goto LABEL_240;
              }
            }
          }
          if ( *(_DWORD *)(a1 + 68) )
          {
            v15 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*a3 + 96LL))(*a3, *(int *)(a1 + 68));
            v134 = v15;
            if ( v15 < 0 )
            {
              Telemetry::IfFailExit(
                "clientcore\\ds\\ext\\live\\identity\\api\\classic\\uxpuiwrapper.cpp",
                "CUxpUIWrapper::__PushUxpParameters",
                0x35Cu,
                v15,
                "hr = spUxSigninDialogSettings->SetWindowIcon((HICON)LongToHandle(pUIParam->hIcon))");
              goto LABEL_240;
            }
          }
          if ( *(_DWORD *)(a1 + 48) != 0x80000000 )
          {
            v8 = (_WORD *)*(unsigned int *)(a1 + 52);
            if ( (_DWORD)v8 != 0x80000000 )
            {
              v16 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a3 + 120LL))(*a3);
              v134 = v16;
              if ( v16 < 0 )
              {
                Telemetry::IfFailExit(
                  "clientcore\\ds\\ext\\live\\identity\\api\\classic\\uxpuiwrapper.cpp",
                  "CUxpUIWrapper::__PushUxpParameters",
                  0x362u,
                  v16,
                  "hr = spUxSigninDialogSettings->SetWindowPos(pUIParam->lWinLeft, pUIParam->lWinTop)");
                goto LABEL_240;
              }
            }
          }
          if ( *(_DWORD *)(a1 + 72) != 0x80000000 )
          {
            v8 = (_WORD *)*(unsigned int *)(a1 + 76);
            if ( (_DWORD)v8 != 0x80000000 )
            {
              v17 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a3 + 112LL))(*a3);
              v134 = v17;
              if ( v17 < 0 )
              {
                Telemetry::IfFailExit(
                  "clientcore\\ds\\ext\\live\\identity\\api\\classic\\uxpuiwrapper.cpp",
                  "CUxpUIWrapper::__PushUxpParameters",
                  0x368u,
                  v17,
                  "hr = spUxSigninDialogSettings->SetWindowSize(pUIParam->lWinWidth, pUIParam->lWinHeight)");
                goto LABEL_240;
              }
            }
          }
          v18 = *(_WORD **)(a1 + 16);
          if ( v18 )
          {
            if ( *v18 )
            {
              v19 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a3 + 32LL))(*a3);
              v134 = v19;
              if ( v19 < 0 )
              {
                Telemetry::IfFailExit(
                  "clientcore\\ds\\ext\\live\\identity\\api\\classic\\uxpuiwrapper.cpp",
                  "CUxpUIWrapper::__PushUxpParameters",
                  0x36Eu,
                  v19,
                  "hr = spUxSigninDialogSettings->SetHostName(pUIParam->wszAppName)");
                goto LABEL_240;
              }
            }
          }
          v20 = *(_WORD **)(a1 + 8);
          if ( v20 && *v20 )
          {
            LOBYTE(v8) = 1;
            v21 = (*(__int64 (__fastcall **)(_QWORD, __int64, _WORD *))(*(_QWORD *)*a3 + 80LL))(*a3, 2, v8);
            v134 = v21;
            if ( v21 < 0 )
            {
              Telemetry::IfFailExit(
                "clientcore\\ds\\ext\\live\\identity\\api\\classic\\uxpuiwrapper.cpp",
                "CUxpUIWrapper::__PushUxpParameters",
                0x374u,
                v21,
                "hr = spUxSigninDialogSettings->SetControlVisibility(UXSigninControls::DescriptiveText, true)");
              goto LABEL_240;
            }
            v22 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD))(*(_QWORD *)*a3 + 56LL))(
                    *a3,
                    2,
                    *(_QWORD *)(a1 + 8),
                    0);
            v134 = v22;
            if ( v22 < 0 )
            {
              Telemetry::IfFailExit(
                "clientcore\\ds\\ext\\live\\identity\\api\\classic\\uxpuiwrapper.cpp",
                "CUxpUIWrapper::__PushUxpParameters",
                0x375u,
                v22,
                "hr = spUxSigninDialogSettings->SetText(UXSigninControls::DescriptiveText, pUIParam->wszCobrandingText, false)");
              goto LABEL_240;
            }
          }
          v23 = *(_WORD **)(a1 + 96);
          if ( v23 )
          {
            if ( *v23 )
            {
              v24 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a3 + 184LL))(*a3);
              v134 = v24;
              if ( v24 < 0 )
              {
                Telemetry::IfFailExit(
                  "clientcore\\ds\\ext\\live\\identity\\api\\classic\\uxpuiwrapper.cpp",
                  "CUxpUIWrapper::__PushUxpParameters",
                  0x37Bu,
                  v24,
                  "hr = spUxSigninDialogSettings->SetDropdownContent(pUIParam->wszDropdownContents)");
                goto LABEL_240;
              }
            }
          }
          v25 = *(_WORD **)(a1 + 40);
          if ( v25 )
          {
            if ( *v25 )
            {
              v26 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a3 + 128LL))(*a3);
              v134 = v26;
              if ( v26 < 0 )
              {
                Telemetry::IfFailExit(
                  "clientcore\\ds\\ext\\live\\identity\\api\\classic\\uxpuiwrapper.cpp",
                  "CUxpUIWrapper::__PushUxpParameters",
                  0x381u,
                  v26,
                  "hr = spUxSigninDialogSettings->SetSceneImage(pUIParam->wszHeaderBgImage)");
                goto LABEL_240;
              }
            }
          }
          v27 = *(_WORD **)(a1 + 88);
          if ( v27 )
          {
            if ( *v27 )
            {
              v28 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a3 + 144LL))(*a3);
              v134 = v28;
              if ( v28 < 0 )
              {
                Telemetry::IfFailExit(
                  "clientcore\\ds\\ext\\live\\identity\\api\\classic\\uxpuiwrapper.cpp",
                  "CUxpUIWrapper::__PushUxpParameters",
                  0x387u,
                  v28,
                  "hr = spUxSigninDialogSettings->SetDefaultUsertile(pUIParam->wszDefaultUsertile)");
                goto LABEL_240;
              }
            }
          }
          v29 = *(_WORD **)(a1 + 24);
          if ( v29 )
          {
            if ( *v29 )
            {
              v30 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*a3 + 56LL))(*a3, 17);
              v134 = v30;
              if ( v30 < 0 )
              {
                Telemetry::IfFailExit(
                  "clientcore\\ds\\ext\\live\\identity\\api\\classic\\uxpuiwrapper.cpp",
                  "CUxpUIWrapper::__PushUxpParameters",
                  0x38Du,
                  v30,
                  "hr = spUxSigninDialogSettings->SetText(UXSigninControls::SignupLink, pUIParam->wszSignupText, false)");
                goto LABEL_240;
              }
            }
          }
          v31 = *(_WORD **)(a1 + 104);
          if ( v31 )
          {
            if ( *v31 )
            {
              v32 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*a3 + 64LL))(*a3, 17);
              v134 = v32;
              if ( v32 < 0 )
              {
                Telemetry::IfFailExit(
                  "clientcore\\ds\\ext\\live\\identity\\api\\classic\\uxpuiwrapper.cpp",
                  "CUxpUIWrapper::__PushUxpParameters",
                  0x391u,
                  v32,
                  "hr = spUxSigninDialogSettings->SetTooltip(UXSigninControls::SignupLink, pUIParam->wszSignupTooltip)");
                goto LABEL_240;
              }
            }
          }
          v33 = *(_WORD **)(a1 + 56);
          if ( v33 )
          {
            if ( *v33 )
            {
              v34 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*a3 + 72LL))(*a3, 17);
              v134 = v34;
              if ( v34 < 0 )
              {
                Telemetry::IfFailExit(
                  "clientcore\\ds\\ext\\live\\identity\\api\\classic\\uxpuiwrapper.cpp",
                  "CUxpUIWrapper::__PushUxpParameters",
                  0x395u,
                  v34,
                  "hr = spUxSigninDialogSettings->SetURL(UXSigninControls::SignupLink, pUIParam->wszSignupUrl)");
                goto LABEL_240;
              }
            }
          }
          LOBYTE(v33) = *(_DWORD *)(a1 + 112) == 1;
          v35 = (*(__int64 (__fastcall **)(_QWORD, __int64, _WORD *))(*(_QWORD *)*a3 + 80LL))(*a3, 17, v33);
          v134 = v35;
          if ( v35 < 0 )
          {
            Telemetry::IfFailExit(
              "clientcore\\ds\\ext\\live\\identity\\api\\classic\\uxpuiwrapper.cpp",
              "CUxpUIWrapper::__PushUxpParameters",
              0x397u,
              v35,
              "hr = spUxSigninDialogSettings->SetControlVisibility(UXSigninControls::SignupLink, TRUE == pUIParam->fSignupVisible)");
            goto LABEL_240;
          }
          v36 = *(_WORD **)(a1 + 120);
          if ( v36 )
          {
            if ( *v36 )
            {
              v37 = (*(__int64 (__fastcall **)(_QWORD, __int64, _WORD *, _QWORD))(*(_QWORD *)*a3 + 56LL))(
                      *a3,
                      13,
                      v36,
                      0);
              v134 = v37;
              if ( v37 < 0 )
              {
                Telemetry::IfFailExit(
                  "clientcore\\ds\\ext\\live\\identity\\api\\classic\\uxpuiwrapper.cpp",
                  "CUxpUIWrapper::__PushUxpParameters",
                  0x39Cu,
                  v37,
                  "hr = spUxSigninDialogSettings->SetText(UXSigninControls::HelpButton, pUIParam->wszHelpText, false)");
                goto LABEL_240;
              }
            }
          }
          v38 = *(_WORD **)(a1 + 128);
          if ( v38 )
          {
            if ( *v38 )
            {
              v39 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*a3 + 64LL))(*a3, 13);
              v134 = v39;
              if ( v39 < 0 )
              {
                Telemetry::IfFailExit(
                  "clientcore\\ds\\ext\\live\\identity\\api\\classic\\uxpuiwrapper.cpp",
                  "CUxpUIWrapper::__PushUxpParameters",
                  0x3A0u,
                  v39,
                  "hr = spUxSigninDialogSettings->SetTooltip(UXSigninControls::HelpButton, pUIParam->wszHelpTooltip)");
                goto LABEL_240;
              }
            }
          }
          v40 = *(_WORD **)(a1 + 136);
          if ( v40 )
          {
            if ( *v40 )
            {
              v41 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*a3 + 72LL))(*a3, 13);
              v134 = v41;
              if ( v41 < 0 )
              {
                Telemetry::IfFailExit(
                  "clientcore\\ds\\ext\\live\\identity\\api\\classic\\uxpuiwrapper.cpp",
                  "CUxpUIWrapper::__PushUxpParameters",
                  0x3A4u,
                  v41,
                  "hr = spUxSigninDialogSettings->SetURL(UXSigninControls::HelpButton, pUIParam->wszHelpUrl)");
                goto LABEL_240;
              }
            }
          }
          LOBYTE(v40) = *(_DWORD *)(a1 + 144) == 1;
          v42 = (*(__int64 (__fastcall **)(_QWORD, __int64, _WORD *))(*(_QWORD *)*a3 + 80LL))(*a3, 13, v40);
          v134 = v42;
          if ( v42 < 0 )
          {
            Telemetry::IfFailExit(
              "clientcore\\ds\\ext\\live\\identity\\api\\classic\\uxpuiwrapper.cpp",
              "CUxpUIWrapper::__PushUxpParameters",
              0x3A6u,
              v42,
              "hr = spUxSigninDialogSettings->SetControlVisibility(UXSigninControls::HelpButton, TRUE == pUIParam->fHelpVisible)");
            goto LABEL_240;
          }
          v43 = *(_WORD **)(a1 + 152);
          if ( v43 )
          {
            if ( *v43 )
            {
              v44 = (*(__int64 (__fastcall **)(_QWORD, __int64, _WORD *, _QWORD))(*(_QWORD *)*a3 + 56LL))(
                      *a3,
                      16,
                      v43,
                      0);
              v134 = v44;
              if ( v44 < 0 )
              {
                Telemetry::IfFailExit(
                  "clientcore\\ds\\ext\\live\\identity\\api\\classic\\uxpuiwrapper.cpp",
                  "CUxpUIWrapper::__PushUxpParameters",
                  0x3ABu,
                  v44,
                  "hr = spUxSigninDialogSettings->SetText(UXSigninControls::ForgotPasswordLink, pUIParam->wszForgotPasswordText, false)");
                goto LABEL_240;
              }
            }
          }
          v45 = *(_WORD **)(a1 + 160);
          if ( v45 )
          {
            if ( *v45 )
            {
              v46 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*a3 + 64LL))(*a3, 16);
              v134 = v46;
              if ( v46 < 0 )
              {
                Telemetry::IfFailExit(
                  "clientcore\\ds\\ext\\live\\identity\\api\\classic\\uxpuiwrapper.cpp",
                  "CUxpUIWrapper::__PushUxpParameters",
                  0x3AFu,
                  v46,
                  "hr = spUxSigninDialogSettings->SetTooltip(UXSigninControls::ForgotPasswordLink, pUIParam->wszForgotPasswordTooltip)");
                goto LABEL_240;
              }
            }
          }
          v47 = *(_WORD **)(a1 + 168);
          if ( v47 )
          {
            if ( *v47 )
            {
              v48 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*a3 + 72LL))(*a3, 16);
              v134 = v48;
              if ( v48 < 0 )
              {
                Telemetry::IfFailExit(
                  "clientcore\\ds\\ext\\live\\identity\\api\\classic\\uxpuiwrapper.cpp",
                  "CUxpUIWrapper::__PushUxpParameters",
                  0x3B3u,
                  v48,
                  "hr = spUxSigninDialogSettings->SetURL(UXSigninControls::ForgotPasswordLink, pUIParam->wszForgotPasswordUrl)");
                goto LABEL_240;
              }
            }
          }
          LOBYTE(v47) = *(_DWORD *)(a1 + 176) == 1;
          v49 = (*(__int64 (__fastcall **)(_QWORD, __int64, _WORD *))(*(_QWORD *)*a3 + 80LL))(*a3, 16, v47);
          v134 = v49;
          if ( v49 < 0 )
          {
            Telemetry::IfFailExit(
              "clientcore\\ds\\ext\\live\\identity\\api\\classic\\uxpuiwrapper.cpp",
              "CUxpUIWrapper::__PushUxpParameters",
              0x3B5u,
              v49,
              "hr = spUxSigninDialogSettings->SetControlVisibility(UXSigninControls::ForgotPasswordLink, TRUE == pUIParam"
              "->fForgotPasswordVisible)");
            goto LABEL_240;
          }
          v50 = *(_WORD **)(a1 + 184);
          if ( v50 )
          {
            if ( *v50 )
            {
              v51 = (*(__int64 (__fastcall **)(_QWORD, __int64, _WORD *, _QWORD))(*(_QWORD *)*a3 + 56LL))(
                      *a3,
                      19,
                      v50,
                      0);
              v134 = v51;
              if ( v51 < 0 )
              {
                Telemetry::IfFailExit(
                  "clientcore\\ds\\ext\\live\\identity\\api\\classic\\uxpuiwrapper.cpp",
                  "CUxpUIWrapper::__PushUxpParameters",
                  0x3BAu,
                  v51,
                  "hr = spUxSigninDialogSettings->SetText(UXSigninControls::TOSLink, pUIParam->wszTOSText, false)");
                goto LABEL_240;
              }
            }
          }
          v52 = *(_WORD **)(a1 + 192);
          if ( v52 )
          {
            if ( *v52 )
            {
              v53 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*a3 + 64LL))(*a3, 19);
              v134 = v53;
              if ( v53 < 0 )
              {
                Telemetry::IfFailExit(
                  "clientcore\\ds\\ext\\live\\identity\\api\\classic\\uxpuiwrapper.cpp",
                  "CUxpUIWrapper::__PushUxpParameters",
                  0x3BEu,
                  v53,
                  "hr = spUxSigninDialogSettings->SetTooltip(UXSigninControls::TOSLink, pUIParam->wszTOSTooltip)");
                goto LABEL_240;
              }
            }
          }
          v54 = *(_WORD **)(a1 + 200);
          if ( v54 )
          {
            if ( *v54 )
            {
              v55 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*a3 + 72LL))(*a3, 19);
              v134 = v55;
              if ( v55 < 0 )
              {
                Telemetry::IfFailExit(
                  "clientcore\\ds\\ext\\live\\identity\\api\\classic\\uxpuiwrapper.cpp",
                  "CUxpUIWrapper::__PushUxpParameters",
                  0x3C2u,
                  v55,
                  "hr = spUxSigninDialogSettings->SetURL(UXSigninControls::TOSLink, pUIParam->wszTOSUrl)");
                goto LABEL_240;
              }
            }
          }
          LOBYTE(v54) = *(_DWORD *)(a1 + 208) == 1;
          v56 = (*(__int64 (__fastcall **)(_QWORD, __int64, _WORD *))(*(_QWORD *)*a3 + 80LL))(*a3, 19, v54);
          v134 = v56;
          if ( v56 < 0 )
          {
            Telemetry::IfFailExit(
              "clientcore\\ds\\ext\\live\\identity\\api\\classic\\uxpuiwrapper.cpp",
              "CUxpUIWrapper::__PushUxpParameters",
              0x3C4u,
              v56,
              "hr = spUxSigninDialogSettings->SetControlVisibility(UXSigninControls::TOSLink, TRUE == pUIParam->fTOSVisible)");
            goto LABEL_240;
          }
          v57 = *(_WORD **)(a1 + 216);
          if ( v57 )
          {
            if ( *v57 )
            {
              v58 = (*(__int64 (__fastcall **)(_QWORD, __int64, _WORD *, _QWORD))(*(_QWORD *)*a3 + 56LL))(
                      *a3,
                      18,
                      v57,
                      0);
              v134 = v58;
              if ( v58 < 0 )
              {
                Telemetry::IfFailExit(
                  "clientcore\\ds\\ext\\live\\identity\\api\\classic\\uxpuiwrapper.cpp",
                  "CUxpUIWrapper::__PushUxpParameters",
                  0x3C9u,
                  v58,
                  "hr = spUxSigninDialogSettings->SetText(UXSigninControls::PrivacyLink, pUIParam->wszPrivacyText, false)");
                goto LABEL_240;
              }
            }
          }
          v59 = *(_WORD **)(a1 + 224);
          if ( v59 )
          {
            if ( *v59 )
            {
              v60 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*a3 + 64LL))(*a3, 18);
              v134 = v60;
              if ( v60 < 0 )
              {
                Telemetry::IfFailExit(
                  "clientcore\\ds\\ext\\live\\identity\\api\\classic\\uxpuiwrapper.cpp",
                  "CUxpUIWrapper::__PushUxpParameters",
                  0x3CDu,
                  v60,
                  "hr = spUxSigninDialogSettings->SetTooltip(UXSigninControls::PrivacyLink, pUIParam->wszPrivacyTooltip)");
                goto LABEL_240;
              }
            }
          }
          v61 = *(_WORD **)(a1 + 232);
          if ( v61 )
          {
            if ( *v61 )
            {
              v62 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*a3 + 72LL))(*a3, 18);
              v134 = v62;
              if ( v62 < 0 )
              {
                Telemetry::IfFailExit(
                  "clientcore\\ds\\ext\\live\\identity\\api\\classic\\uxpuiwrapper.cpp",
                  "CUxpUIWrapper::__PushUxpParameters",
                  0x3D1u,
                  v62,
                  "hr = spUxSigninDialogSettings->SetURL(UXSigninControls::PrivacyLink, pUIParam->wszPrivacyUrl)");
                goto LABEL_240;
              }
            }
          }
          LOBYTE(v61) = *(_DWORD *)(a1 + 240) == 1;
          v63 = (*(__int64 (__fastcall **)(_QWORD, __int64, _WORD *))(*(_QWORD *)*a3 + 80LL))(*a3, 18, v61);
          v134 = v63;
          if ( v63 < 0 )
          {
            Telemetry::IfFailExit(
              "clientcore\\ds\\ext\\live\\identity\\api\\classic\\uxpuiwrapper.cpp",
              "CUxpUIWrapper::__PushUxpParameters",
              0x3D3u,
              v63,
              "hr = spUxSigninDialogSettings->SetControlVisibility(UXSigninControls::PrivacyLink, TRUE == pUIParam->fPrivacyVisible)");
            goto LABEL_240;
          }
          v64 = *(_WORD **)(a1 + 248);
          if ( v64 )
          {
            if ( *v64 )
            {
              v65 = (*(__int64 (__fastcall **)(_QWORD, __int64, _WORD *, _QWORD))(*(_QWORD *)*a3 + 56LL))(
                      *a3,
                      20,
                      v64,
                      0);
              v134 = v65;
              if ( v65 < 0 )
              {
                Telemetry::IfFailExit(
                  "clientcore\\ds\\ext\\live\\identity\\api\\classic\\uxpuiwrapper.cpp",
                  "CUxpUIWrapper::__PushUxpParameters",
                  0x3D8u,
                  v65,
                  "hr = spUxSigninDialogSettings->SetText(UXSigninControls::ServerStatusLink, pUIParam->wszServerStatusText, false)");
                goto LABEL_240;
              }
            }
          }
          v66 = *(_WORD **)(a1 + 256);
          if ( v66 )
          {
            if ( *v66 )
            {
              v67 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*a3 + 64LL))(*a3, 20);
              v134 = v67;
              if ( v67 < 0 )
              {
                Telemetry::IfFailExit(
                  "clientcore\\ds\\ext\\live\\identity\\api\\classic\\uxpuiwrapper.cpp",
                  "CUxpUIWrapper::__PushUxpParameters",
                  0x3DCu,
                  v67,
                  "hr = spUxSigninDialogSettings->SetTooltip(UXSigninControls::ServerStatusLink, pUIParam->wszServerStatusTooltip)");
                goto LABEL_240;
              }
            }
          }
          v68 = *(_WORD **)(a1 + 264);
          if ( v68 )
          {
            if ( *v68 )
            {
              v69 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*a3 + 72LL))(*a3, 20);
              v134 = v69;
              if ( v69 < 0 )
              {
                Telemetry::IfFailExit(
                  "clientcore\\ds\\ext\\live\\identity\\api\\classic\\uxpuiwrapper.cpp",
                  "CUxpUIWrapper::__PushUxpParameters",
                  0x3E0u,
                  v69,
                  "hr = spUxSigninDialogSettings->SetURL(UXSigninControls::ServerStatusLink, pUIParam->wszServerStatusUrl)");
                goto LABEL_240;
              }
            }
          }
          LOBYTE(v68) = *(_DWORD *)(a1 + 272) == 1;
          v70 = (*(__int64 (__fastcall **)(_QWORD, __int64, _WORD *))(*(_QWORD *)*a3 + 80LL))(*a3, 20, v68);
          v134 = v70;
          if ( v70 < 0 )
          {
            Telemetry::IfFailExit(
              "clientcore\\ds\\ext\\live\\identity\\api\\classic\\uxpuiwrapper.cpp",
              "CUxpUIWrapper::__PushUxpParameters",
              0x3E2u,
              v70,
              "hr = spUxSigninDialogSettings->SetControlVisibility(UXSigninControls::ServerStatusLink, TRUE == pUIParam->"
              "fServerStatusVisible)");
            goto LABEL_240;
          }
          v71 = *(_WORD **)(a1 + 280);
          if ( v71 )
          {
            if ( *v71 )
            {
              v72 = (*(__int64 (__fastcall **)(_QWORD, __int64, _WORD *, _QWORD))(*(_QWORD *)*a3 + 56LL))(
                      *a3,
                      21,
                      v71,
                      0);
              v134 = v72;
              if ( v72 < 0 )
              {
                Telemetry::IfFailExit(
                  "clientcore\\ds\\ext\\live\\identity\\api\\classic\\uxpuiwrapper.cpp",
                  "CUxpUIWrapper::__PushUxpParameters",
                  0x3E7u,
                  v72,
                  "hr = spUxSigninDialogSettings->SetText(UXSigninControls::OptionsLink, pUIParam->wszOptionsText, false)");
                goto LABEL_240;
              }
            }
          }
          v73 = *(_WORD **)(a1 + 288);
          if ( v73 )
          {
            if ( *v73 )
            {
              v74 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*a3 + 64LL))(*a3, 21);
              v134 = v74;
              if ( v74 < 0 )
              {
                Telemetry::IfFailExit(
                  "clientcore\\ds\\ext\\live\\identity\\api\\classic\\uxpuiwrapper.cpp",
                  "CUxpUIWrapper::__PushUxpParameters",
                  0x3EBu,
                  v74,
                  "hr = spUxSigninDialogSettings->SetTooltip(UXSigninControls::OptionsLink, pUIParam->wszOptionsTooltip)");
                goto LABEL_240;
              }
            }
          }
          v75 = *(_WORD **)(a1 + 296);
          if ( v75 )
          {
            if ( *v75 )
            {
              v76 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*a3 + 72LL))(*a3, 21);
              v134 = v76;
              if ( v76 < 0 )
              {
                Telemetry::IfFailExit(
                  "clientcore\\ds\\ext\\live\\identity\\api\\classic\\uxpuiwrapper.cpp",
                  "CUxpUIWrapper::__PushUxpParameters",
                  0x3EFu,
                  v76,
                  "hr = spUxSigninDialogSettings->SetURL(UXSigninControls::OptionsLink, pUIParam->wszOptionsUrl)");
                goto LABEL_240;
              }
            }
          }
          LOBYTE(v75) = *(_DWORD *)(a1 + 304) == 1;
          v77 = (*(__int64 (__fastcall **)(_QWORD, __int64, _WORD *))(*(_QWORD *)*a3 + 80LL))(*a3, 21, v75);
          v134 = v77;
          if ( v77 < 0 )
          {
            Telemetry::IfFailExit(
              "clientcore\\ds\\ext\\live\\identity\\api\\classic\\uxpuiwrapper.cpp",
              "CUxpUIWrapper::__PushUxpParameters",
              0x3F1u,
              v77,
              "hr = spUxSigninDialogSettings->SetControlVisibility(UXSigninControls::OptionsLink, TRUE == pUIParam->fOptionsVisible)");
            goto LABEL_240;
          }
          v78 = *(_WORD **)(a1 + 312);
          if ( v78 && *v78 )
          {
            ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v127);
            ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v124);
            v126 = 0;
            v79 = -1;
            do
              ++v79;
            while ( *(_WORD *)(*(_QWORD *)(a1 + 312) + 2 * v79) );
            ATL::CSimpleStringT<unsigned short,0>::Append(&v127);
            v80 = *(_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Tokenize(
                               &v127,
                               &String,
                               L";",
                               &v126);
            v81 = v124;
            v82 = (int *)(v124 - 24);
            if ( v80 - 24 != v124 - 24 )
            {
              if ( v82[4] >= 0 && *(_QWORD *)(v80 - 24) == *(_QWORD *)v82 )
              {
                v83 = ATL::CSimpleStringT<unsigned short,0>::CloneData();
                ATL::CStringData::Release((ATL::CStringData *)v82);
                v81 = v83 + 24;
                v124 = v81;
              }
              else
              {
                ATL::CSimpleStringT<unsigned short,0>::SetString(&v124, v80, *(unsigned int *)(v80 - 16));
                v81 = v124;
              }
            }
            ATL::CStringData::Release((ATL::CStringData *)(String - 12));
            while ( *(_DWORD *)(v81 - 16) )
            {
              ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v128);
              ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&String);
              v123 = 0;
              v84 = *(_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Tokenize(
                                 &v124,
                                 &v129,
                                 L":",
                                 &v123);
              v85 = v128;
              v86 = (int *)(v128 - 24);
              if ( v84 - 24 != v128 - 24 )
              {
                if ( v86[4] >= 0 && *(_QWORD *)(v84 - 24) == *(_QWORD *)v86 )
                {
                  v87 = ATL::CSimpleStringT<unsigned short,0>::CloneData();
                  ATL::CStringData::Release((ATL::CStringData *)v86);
                  v85 = v87 + 24;
                  v128 = v85;
                }
                else
                {
                  ATL::CSimpleStringT<unsigned short,0>::SetString(&v128, v84, *(unsigned int *)(v84 - 16));
                  v85 = v128;
                }
              }
              ATL::CStringData::Release((ATL::CStringData *)(v129 - 24));
              v88 = *(_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Tokenize(
                                 &v124,
                                 &v130,
                                 L":",
                                 &v123);
              v89 = String;
              v90 = (int *)(String - 12);
              if ( (wchar_t *)(v88 - 24) != String - 12 )
              {
                if ( v90[4] >= 0 && *(_QWORD *)(v88 - 24) == *(_QWORD *)v90 )
                {
                  v91 = ATL::CSimpleStringT<unsigned short,0>::CloneData();
                  ATL::CStringData::Release((ATL::CStringData *)v90);
                  v89 = (wchar_t *)(v91 + 24);
                  String = v89;
                }
                else
                {
                  ATL::CSimpleStringT<unsigned short,0>::SetString(&String, v88, *(unsigned int *)(v88 - 16));
                  v89 = String;
                }
              }
              ATL::CStringData::Release((ATL::CStringData *)(v130 - 24));
              v92 = (ATL::CStringData *)(v89 - 12);
              if ( *((_DWORD *)v89 - 4) )
                v93 = wcstol(v89, 0, 10);
              else
                v93 = 0;
              if ( *(_DWORD *)(v85 - 16) )
              {
                if ( v93 )
                {
                  v94 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*a3 + 168LL))(*a3, v85);
                  v134 = v94;
                  if ( v94 < 0 )
                  {
                    Telemetry::IfFailExit(
                      "clientcore\\ds\\ext\\live\\identity\\api\\classic\\uxpuiwrapper.cpp",
                      "CUxpUIWrapper::__PushUxpParameters",
                      0x412u,
                      v94,
                      "hr = spUxSigninDialogSettings->AddMenuItem(strMenuText.GetString(), dwCmdId)");
                    ATL::CStringData::Release((ATL::CStringData *)(v89 - 12));
                    ATL::CStringData::Release((ATL::CStringData *)(v85 - 24));
                    ATL::CStringData::Release((ATL::CStringData *)(v81 - 24));
                    ATL::CStringData::Release((ATL::CStringData *)(v127 - 24));
                    goto LABEL_240;
                  }
                }
              }
              v95 = *(_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Tokenize(
                                 &v127,
                                 &v131,
                                 L";",
                                 &v126);
              v96 = (int *)(v81 - 24);
              if ( v95 - 24 != v81 - 24 )
              {
                if ( v96[4] >= 0 && *(_QWORD *)(v95 - 24) == *(_QWORD *)v96 )
                {
                  v97 = ATL::CSimpleStringT<unsigned short,0>::CloneData();
                  ATL::CStringData::Release((ATL::CStringData *)v96);
                  v81 = v97 + 24;
                  v124 = v81;
                }
                else
                {
                  ATL::CSimpleStringT<unsigned short,0>::SetString(&v124, v95, *(unsigned int *)(v95 - 16));
                  v81 = v124;
                }
              }
              ATL::CStringData::Release((ATL::CStringData *)(v131 - 24));
              ATL::CStringData::Release(v92);
              ATL::CStringData::Release((ATL::CStringData *)(v85 - 24));
            }
            ATL::CStringData::Release((ATL::CStringData *)(v81 - 24));
            ATL::CStringData::Release((ATL::CStringData *)(v127 - 24));
            v4 = a2;
          }
          v98 = *(_WORD **)(a1 + 320);
          if ( v98 )
          {
            if ( *v98 )
            {
              v99 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*a3 + 56LL))(*a3, 9);
              v134 = v99;
              if ( v99 < 0 )
              {
                Telemetry::IfFailExit(
                  "clientcore\\ds\\ext\\live\\identity\\api\\classic\\uxpuiwrapper.cpp",
                  "CUxpUIWrapper::__PushUxpParameters",
                  0x41Bu,
                  v99,
                  "hr = spUxSigninDialogSettings->SetText(UXSigninControls::RememberPasswordCheckbox, pUIParam->wszRememb"
                  "erMeCheckboxText, false)");
                goto LABEL_240;
              }
            }
          }
          v100 = *(_WORD **)(a1 + 328);
          if ( v100 )
          {
            if ( *v100 )
            {
              v101 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*a3 + 56LL))(*a3, 10);
              v134 = v101;
              if ( v101 < 0 )
              {
                Telemetry::IfFailExit(
                  "clientcore\\ds\\ext\\live\\identity\\api\\classic\\uxpuiwrapper.cpp",
                  "CUxpUIWrapper::__PushUxpParameters",
                  0x41Fu,
                  v101,
                  "hr = spUxSigninDialogSettings->SetText(UXSigninControls::SigninAutomaticallyCheckbox, pUIParam->wszAut"
                  "oSigninCheckboxText, false)");
                goto LABEL_240;
              }
            }
          }
          v102 = *(_WORD **)(a1 + 336);
          if ( v102 )
          {
            if ( *v102 )
            {
              v103 = (*(__int64 (__fastcall **)(_QWORD, __int64, _WORD *, _QWORD))(*(_QWORD *)*a3 + 56LL))(
                       *a3,
                       22,
                       v102,
                       0);
              v134 = v103;
              if ( v103 < 0 )
              {
                Telemetry::IfFailExit(
                  "clientcore\\ds\\ext\\live\\identity\\api\\classic\\uxpuiwrapper.cpp",
                  "CUxpUIWrapper::__PushUxpParameters",
                  0x425u,
                  v103,
                  "hr = spUxSigninDialogSettings->SetText(UXSigninControls::MoreInfoLink, pUIParam->wszMoreInfoText, false)");
                goto LABEL_240;
              }
            }
          }
          v104 = *(_WORD **)(a1 + 344);
          if ( v104 )
          {
            if ( *v104 )
            {
              v105 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*a3 + 64LL))(*a3, 22);
              v134 = v105;
              if ( v105 < 0 )
              {
                Telemetry::IfFailExit(
                  "clientcore\\ds\\ext\\live\\identity\\api\\classic\\uxpuiwrapper.cpp",
                  "CUxpUIWrapper::__PushUxpParameters",
                  0x429u,
                  v105,
                  "hr = spUxSigninDialogSettings->SetTooltip(UXSigninControls::MoreInfoLink, pUIParam->wszMoreInfoTooltip)");
                goto LABEL_240;
              }
            }
          }
          v106 = *(_WORD **)(a1 + 352);
          if ( v106 )
          {
            if ( *v106 )
            {
              v107 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*a3 + 72LL))(*a3, 22);
              v134 = v107;
              if ( v107 < 0 )
              {
                Telemetry::IfFailExit(
                  "clientcore\\ds\\ext\\live\\identity\\api\\classic\\uxpuiwrapper.cpp",
                  "CUxpUIWrapper::__PushUxpParameters",
                  0x42Du,
                  v107,
                  "hr = spUxSigninDialogSettings->SetURL(UXSigninControls::MoreInfoLink, pUIParam->wszMoreInfoUrl)");
                goto LABEL_240;
              }
            }
          }
          LOBYTE(v106) = *(_DWORD *)(a1 + 360) == 1;
          v108 = (*(__int64 (__fastcall **)(_QWORD, __int64, _WORD *))(*(_QWORD *)*a3 + 80LL))(*a3, 22, v106);
          v134 = v108;
          if ( v108 < 0 )
          {
            Telemetry::IfFailExit(
              "clientcore\\ds\\ext\\live\\identity\\api\\classic\\uxpuiwrapper.cpp",
              "CUxpUIWrapper::__PushUxpParameters",
              0x42Fu,
              v108,
              "hr = spUxSigninDialogSettings->SetControlVisibility(UXSigninControls::MoreInfoLink, TRUE == pUIParam->fMoreInfoVisible)");
            goto LABEL_240;
          }
          v109 = *(_WORD **)(a1 + 368);
          if ( v109 )
          {
            if ( *v109 )
            {
              v110 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*a3 + 56LL))(*a3, 2);
              v134 = v110;
              if ( v110 < 0 )
              {
                Telemetry::IfFailExit(
                  "clientcore\\ds\\ext\\live\\identity\\api\\classic\\uxpuiwrapper.cpp",
                  "CUxpUIWrapper::__PushUxpParameters",
                  0x434u,
                  v110,
                  "hr = spUxSigninDialogSettings->SetText(UXSigninControls::DescriptiveText, pUIParam->wszDescriptiveText, false)");
                goto LABEL_240;
              }
            }
          }
          LOBYTE(v109) = *(_DWORD *)(a1 + 376) == 1;
          v111 = (*(__int64 (__fastcall **)(_QWORD, __int64, _WORD *))(*(_QWORD *)*a3 + 80LL))(*a3, 2, v109);
          v134 = v111;
          if ( v111 < 0 )
          {
            Telemetry::IfFailExit(
              "clientcore\\ds\\ext\\live\\identity\\api\\classic\\uxpuiwrapper.cpp",
              "CUxpUIWrapper::__PushUxpParameters",
              0x436u,
              v111,
              "hr = spUxSigninDialogSettings->SetControlVisibility(UXSigninControls::DescriptiveText, TRUE == pUIParam->f"
              "DescriptiveTextVisible)");
            goto LABEL_240;
          }
          v8 = *(_WORD **)(a1 + 384);
          if ( v8 )
          {
            if ( *v8 )
            {
              v112 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*a3 + 56LL))(*a3, 1);
              v134 = v112;
              if ( v112 < 0 )
              {
                Telemetry::IfFailExit(
                  "clientcore\\ds\\ext\\live\\identity\\api\\classic\\uxpuiwrapper.cpp",
                  "CUxpUIWrapper::__PushUxpParameters",
                  0x43Bu,
                  v112,
                  "hr = spUxSigninDialogSettings->SetText(UXSigninControls::HeaderText, pUIParam->wszHeaderText, false)");
                goto LABEL_240;
              }
            }
          }
        }
        if ( *(_DWORD *)(v4 + 32) )
        {
          if ( (*(_BYTE *)(v4 + 32) & 1) != 0 )
          {
            v113 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*a3 + 80LL))(*a3, 9);
            v134 = v113;
            if ( v113 < 0 )
            {
              Telemetry::IfFailExit(
                "clientcore\\ds\\ext\\live\\identity\\api\\classic\\uxpuiwrapper.cpp",
                "CUxpUIWrapper::__PushUxpParameters",
                0x445u,
                v113,
                "hr = spUxSigninDialogSettings->SetControlVisibility(UXSigninControls::RememberPasswordCheckbox, false)");
              goto LABEL_240;
            }
            v114 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*a3 + 80LL))(*a3, 10);
            v134 = v114;
            if ( v114 < 0 )
            {
              Telemetry::IfFailExit(
                "clientcore\\ds\\ext\\live\\identity\\api\\classic\\uxpuiwrapper.cpp",
                "CUxpUIWrapper::__PushUxpParameters",
                0x448u,
                v114,
                "hr = spUxSigninDialogSettings->SetControlVisibility(UXSigninControls::SigninAutomaticallyCheckbox, false)");
              goto LABEL_240;
            }
          }
          if ( (*(_BYTE *)(v4 + 32) & 2) != 0
            && (v115 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*a3 + 80LL))(*a3, 10),
                v134 = v115,
                v115 < 0) )
          {
            Telemetry::IfFailExit(
              "clientcore\\ds\\ext\\live\\identity\\api\\classic\\uxpuiwrapper.cpp",
              "CUxpUIWrapper::__PushUxpParameters",
              0x44Eu,
              v115,
              "hr = spUxSigninDialogSettings->SetControlVisibility(UXSigninControls::SigninAutomaticallyCheckbox, false)");
          }
          else if ( (*(_BYTE *)(v4 + 32) & 4) != 0
                 && (LOBYTE(v9) = 1,
                     v116 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, __int64))(*(_QWORD *)*a3 + 56LL))(
                              *a3,
                              4,
                              *(_QWORD *)v4,
                              v9),
                     v134 = v116,
                     v116 < 0) )
          {
            Telemetry::IfFailExit(
              "clientcore\\ds\\ext\\live\\identity\\api\\classic\\uxpuiwrapper.cpp",
              "CUxpUIWrapper::__PushUxpParameters",
              0x454u,
              v116,
              "hr = spUxSigninDialogSettings->SetText(UXSigninControls::Username, pIdentityInfo->wszUserName, true)");
          }
          else if ( (*(_BYTE *)(v4 + 32) & 0x40) != 0
                 && (v117 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*a3 + 80LL))(*a3, 17),
                     v134 = v117,
                     v117 < 0) )
          {
            Telemetry::IfFailExit(
              "clientcore\\ds\\ext\\live\\identity\\api\\classic\\uxpuiwrapper.cpp",
              "CUxpUIWrapper::__PushUxpParameters",
              0x45Au,
              v117,
              "hr = spUxSigninDialogSettings->SetControlVisibility(UXSigninControls::SignupLink, false)");
          }
          else if ( (*(_DWORD *)(v4 + 32) & 0x100) != 0
                 && (LOBYTE(v8) = 1,
                     v118 = (*(__int64 (__fastcall **)(_QWORD, __int64, _WORD *))(*(_QWORD *)*a3 + 88LL))(*a3, 9, v8),
                     v134 = v118,
                     v118 < 0) )
          {
            Telemetry::IfFailExit(
              "clientcore\\ds\\ext\\live\\identity\\api\\classic\\uxpuiwrapper.cpp",
              "CUxpUIWrapper::__PushUxpParameters",
              0x460u,
              v118,
              "hr = spUxSigninDialogSettings->SetCheckboxState(UXSigninControls::RememberPasswordCheckbox, true, false)");
          }
          else if ( *(char *)(v4 + 32) < 0 )
          {
            v119 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*a3 + 200LL))(*a3, 0);
            v134 = v119;
            if ( v119 < 0 )
              Telemetry::IfFailExit(
                "clientcore\\ds\\ext\\live\\identity\\api\\classic\\uxpuiwrapper.cpp",
                "CUxpUIWrapper::__PushUxpParameters",
                0x466u,
                v119,
                "hr = spUxSigninDialogSettings->SetShowRememberedUsers(false)");
          }
        }
      }
      else
      {
        Telemetry::IfFailExit(
          "clientcore\\ds\\ext\\live\\identity\\api\\classic\\uxpuiwrapper.cpp",
          "CUxpUIWrapper::__PushUxpParameters",
          0x34Eu,
          v12,
          "hr = spUxSigninDialogSettings->SetError( pIdentityInfo->hrError, pIdentityInfo->wszErrorText, pIdentityInfo->wszErrorURL)");
      }
    }
  }
  else
  {
    Telemetry::IfFailExit(
      "clientcore\\ds\\ext\\live\\identity\\api\\classic\\uxpuiwrapper.cpp",
      "CUxpUIWrapper::__PushUxpParameters",
      0x343u,
      v7,
      "hr = spUxSigninDialogSettings->SetMarket(lcid)");
  }
LABEL_240:
  v120 = v134;
  CTraceFuncW<long>::~CTraceFuncW<long>(v132);
  return v120;
}

```

## disassembly

```asm
0x18003e8ec  mov     [rsp-8+arg_0], rbx
0x18003e8f1  mov     [rsp-8+arg_8], rdx
0x18003e8f6  push    rbp
0x18003e8f7  push    rsi
0x18003e8f8  push    rdi
0x18003e8f9  push    r12
0x18003e8fb  push    r13
0x18003e8fd  push    r14
0x18003e8ff  push    r15
0x18003e901  lea     rbp, [rsp-27h]
0x18003e906  sub     rsp, 0A0h
0x18003e90d  mov     r15, r8
0x18003e910  mov     rbx, rdx
0x18003e913  mov     r14, rcx
0x18003e916  xor     r13d, r13d
0x18003e919  mov     [rbp+57h+arg_18], r13d
0x18003e91d  mov     [rbp+57h+var_A0], 409h
0x18003e924  lea     rdi, aCuxpuiwrapperP; "CUxpUIWrapper::__PushUxpParameters"
0x18003e92b  mov     [rbp+57h+var_58], rdi
0x18003e92f  lea     rax, [rbp+57h+arg_18]
0x18003e933  mov     [rbp+57h+var_50], rax
0x18003e937  mov     [rbp+57h+var_48], r13
0x18003e93b  mov     [rbp+57h+var_40], r13
0x18003e93f  xor     r9d, r9d; unsigned int
0x18003e942  mov     r8d, 33Ah; char *
0x18003e948  mov     rdx, rdi; char *
0x18003e94b  lea     rsi, aClientcoreDsEx_7; "clientcore\\ds\\ext\\live\\identity\\ap"...
0x18003e952  mov     rcx, rsi; this
0x18003e955  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x18003e95a  nop
0x18003e95b  test    rbx, rbx
0x18003e95e  jz      loc_18003FB21
0x18003e964  cmp     [r15], r13
0x18003e967  jz      loc_18003FB21
0x18003e96d  lea     rcx, [rbp+57h+var_A0]; unsigned int *
0x18003e971  call    ?GetLCID@CStringSrv@@SAJAEAK@Z; CStringSrv::GetLCID(ulong &)
0x18003e976  mov     [rbp+57h+arg_18], eax
0x18003e979  test    eax, eax
0x18003e97b  jns     short loc_18003E9A2
0x18003e97d  lea     r8, aHrCstringsrvGe; "hr = CStringSrv::GetLCID(lcid)"
0x18003e984  mov     [rsp+0D0h+var_B0], r8; char *
0x18003e989  mov     r8d, 342h; unsigned int
0x18003e98f  mov     r9d, eax; int
0x18003e992  mov     rdx, rdi; char *
0x18003e995  mov     rcx, rsi; char *
0x18003e998  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x18003e99d  jmp     loc_18003FB28
0x18003e9a2  mov     rcx, [r15]
0x18003e9a5  mov     rax, [rcx]
0x18003e9a8  mov     edx, [rbp+57h+var_A0]
0x18003e9ab  mov     rax, [rax+28h]
0x18003e9af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e9b4  mov     [rbp+57h+arg_18], eax
0x18003e9b7  test    eax, eax
0x18003e9b9  jns     short loc_18003E9CF
0x18003e9bb  lea     rcx, aHrSpuxsignindi_45; "hr = spUxSigninDialogSettings->SetMarke"...
0x18003e9c2  mov     [rsp+0D0h+var_B0], rcx
0x18003e9c7  mov     r8d, 343h
0x18003e9cd  jmp     short loc_18003E98F
0x18003e9cf  mov     rdx, [rbx]
0x18003e9d2  test    rdx, rdx
0x18003e9d5  jz      short loc_18003EA07
0x18003e9d7  cmp     [rdx], r13w
0x18003e9db  jz      short loc_18003EA07
0x18003e9dd  mov     rcx, [r15]
0x18003e9e0  mov     rax, [rcx]
0x18003e9e3  mov     rax, [rax+18h]
0x18003e9e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e9ec  mov     [rbp+57h+arg_18], eax
0x18003e9ef  test    eax, eax
0x18003e9f1  jns     short loc_18003EA07
0x18003e9f3  lea     rcx, aHrSpuxsignindi_28; "hr = spUxSigninDialogSettings->SetUserN"...
0x18003e9fa  mov     [rsp+0D0h+var_B0], rcx
0x18003e9ff  mov     r8d, 347h
0x18003ea05  jmp     short loc_18003E98F
0x18003ea07  mov     edx, [rbx+8]
0x18003ea0a  test    edx, edx
0x18003ea0c  jns     short loc_18003EA43
0x18003ea0e  mov     rcx, [r15]
0x18003ea11  mov     rax, [rcx]
0x18003ea14  mov     r9, [rbx+18h]
0x18003ea18  mov     r8, [rbx+10h]
0x18003ea1c  mov     rax, [rax+30h]
0x18003ea20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ea25  mov     [rbp+57h+arg_18], eax
0x18003ea28  test    eax, eax
0x18003ea2a  jns     short loc_18003EA43
0x18003ea2c  lea     rcx, aHrSpuxsignindi_13; "hr = spUxSigninDialogSettings->SetError"...
0x18003ea33  mov     [rsp+0D0h+var_B0], rcx
0x18003ea38  mov     r8d, 34Eh
0x18003ea3e  jmp     loc_18003E98F
0x18003ea43  test    r14, r14
0x18003ea46  jz      loc_18003F980
0x18003ea4c  mov     rdx, [r14+50h]
0x18003ea50  test    rdx, rdx
0x18003ea53  jz      short loc_18003EA88
0x18003ea55  cmp     [rdx], r13w
0x18003ea59  jz      short loc_18003EA88
0x18003ea5b  mov     rcx, [r15]
0x18003ea5e  mov     rax, [rcx]
0x18003ea61  mov     rax, [rax+68h]
0x18003ea65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ea6a  mov     [rbp+57h+arg_18], eax
0x18003ea6d  test    eax, eax
0x18003ea6f  jns     short loc_18003EA88
0x18003ea71  lea     rcx, aHrSpuxsignindi_51; "hr = spUxSigninDialogSettings->SetWindo"...
0x18003ea78  mov     [rsp+0D0h+var_B0], rcx
0x18003ea7d  mov     r8d, 356h
0x18003ea83  jmp     loc_18003E98F
0x18003ea88  cmp     [r14+44h], r13d
0x18003ea8c  jz      short loc_18003EABF
0x18003ea8e  mov     rcx, [r15]
0x18003ea91  mov     rax, [rcx]
0x18003ea94  movsxd  rdx, dword ptr [r14+44h]
0x18003ea98  mov     rax, [rax+60h]
0x18003ea9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003eaa1  mov     [rbp+57h+arg_18], eax
0x18003eaa4  test    eax, eax
0x18003eaa6  jns     short loc_18003EABF
0x18003eaa8  lea     rcx, aHrSpuxsignindi_39; "hr = spUxSigninDialogSettings->SetWindo"...
0x18003eaaf  mov     [rsp+0D0h+var_B0], rcx
0x18003eab4  mov     r8d, 35Ch
0x18003eaba  jmp     loc_18003E98F
0x18003eabf  mov     edx, [r14+30h]
0x18003eac3  mov     r12d, 80000000h
0x18003eac9  cmp     edx, r12d
0x18003eacc  jz      short loc_18003EB04
0x18003eace  mov     r8d, [r14+34h]
0x18003ead2  cmp     r8d, r12d
0x18003ead5  jz      short loc_18003EB04
0x18003ead7  mov     rcx, [r15]
0x18003eada  mov     rax, [rcx]
0x18003eadd  mov     rax, [rax+78h]
0x18003eae1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003eae6  mov     [rbp+57h+arg_18], eax
0x18003eae9  test    eax, eax
0x18003eaeb  jns     short loc_18003EB04
0x18003eaed  lea     rcx, aHrSpuxsignindi_54; "hr = spUxSigninDialogSettings->SetWindo"...
0x18003eaf4  mov     [rsp+0D0h+var_B0], rcx
0x18003eaf9  mov     r8d, 362h
0x18003eaff  jmp     loc_18003E98F
0x18003eb04  mov     edx, [r14+48h]
0x18003eb08  cmp     edx, r12d
0x18003eb0b  jz      short loc_18003EB43
0x18003eb0d  mov     r8d, [r14+4Ch]
0x18003eb11  cmp     r8d, r12d
0x18003eb14  jz      short loc_18003EB43
0x18003eb16  mov     rcx, [r15]
0x18003eb19  mov     rax, [rcx]
0x18003eb1c  mov     rax, [rax+70h]
0x18003eb20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003eb25  mov     [rbp+57h+arg_18], eax
0x18003eb28  test    eax, eax
0x18003eb2a  jns     short loc_18003EB43
0x18003eb2c  lea     rcx, aHrSpuxsignindi_1; "hr = spUxSigninDialogSettings->SetWindo"...
0x18003eb33  mov     [rsp+0D0h+var_B0], rcx
0x18003eb38  mov     r8d, 368h
0x18003eb3e  jmp     loc_18003E98F
0x18003eb43  mov     rdx, [r14+10h]
0x18003eb47  test    rdx, rdx
0x18003eb4a  jz      short loc_18003EB7F
0x18003eb4c  cmp     [rdx], r13w
0x18003eb50  jz      short loc_18003EB7F
0x18003eb52  mov     rcx, [r15]
0x18003eb55  mov     rax, [rcx]
0x18003eb58  mov     rax, [rax+20h]
0x18003eb5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003eb61  mov     [rbp+57h+arg_18], eax
0x18003eb64  test    eax, eax
0x18003eb66  jns     short loc_18003EB7F
0x18003eb68  lea     rcx, aHrSpuxsignindi_29; "hr = spUxSigninDialogSettings->SetHostN"...
0x18003eb6f  mov     [rsp+0D0h+var_B0], rcx
0x18003eb74  mov     r8d, 36Eh
0x18003eb7a  jmp     loc_18003E98F
0x18003eb7f  mov     rax, [r14+8]
0x18003eb83  test    rax, rax
0x18003eb86  jz      short loc_18003EBFE
0x18003eb88  cmp     [rax], r13w
0x18003eb8c  jz      short loc_18003EBFE
0x18003eb8e  mov     rcx, [r15]
0x18003eb91  mov     rax, [rcx]
0x18003eb94  mov     r8b, 1
0x18003eb97  mov     r12d, 2
0x18003eb9d  mov     edx, r12d
0x18003eba0  mov     rax, [rax+50h]
0x18003eba4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003eba9  mov     [rbp+57h+arg_18], eax
0x18003ebac  test    eax, eax
0x18003ebae  jns     short loc_18003EBC7
0x18003ebb0  lea     rcx, aHrSpuxsignindi_24; "hr = spUxSigninDialogSettings->SetContr"...
0x18003ebb7  mov     [rsp+0D0h+var_B0], rcx
0x18003ebbc  mov     r8d, 374h
0x18003ebc2  jmp     loc_18003E98F
0x18003ebc7  mov     rcx, [r15]
0x18003ebca  mov     rax, [rcx]
0x18003ebcd  xor     r9d, r9d
0x18003ebd0  mov     r8, [r14+8]
0x18003ebd4  mov     edx, r12d
0x18003ebd7  mov     rax, [rax+38h]
0x18003ebdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ebe0  mov     [rbp+57h+arg_18], eax
0x18003ebe3  test    eax, eax
0x18003ebe5  jns     short loc_18003EBFE
0x18003ebe7  lea     rcx, aHrSpuxsignindi_10; "hr = spUxSigninDialogSettings->SetText("...
0x18003ebee  mov     [rsp+0D0h+var_B0], rcx
0x18003ebf3  mov     r8d, 375h
0x18003ebf9  jmp     loc_18003E98F
0x18003ebfe  mov     rdx, [r14+60h]
0x18003ec02  test    rdx, rdx
0x18003ec05  jz      short loc_18003EC3D
0x18003ec07  cmp     [rdx], r13w
0x18003ec0b  jz      short loc_18003EC3D
0x18003ec0d  mov     rcx, [r15]
0x18003ec10  mov     rax, [rcx]
0x18003ec13  mov     rax, [rax+0B8h]
0x18003ec1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ec1f  mov     [rbp+57h+arg_18], eax
0x18003ec22  test    eax, eax
0x18003ec24  jns     short loc_18003EC3D
0x18003ec26  lea     rcx, aHrSpuxsignindi_8; "hr = spUxSigninDialogSettings->SetDropd"...
0x18003ec2d  mov     [rsp+0D0h+var_B0], rcx
0x18003ec32  mov     r8d, 37Bh
0x18003ec38  jmp     loc_18003E98F
0x18003ec3d  mov     rdx, [r14+28h]
0x18003ec41  test    rdx, rdx
0x18003ec44  jz      short loc_18003EC7C
0x18003ec46  cmp     [rdx], r13w
0x18003ec4a  jz      short loc_18003EC7C
0x18003ec4c  mov     rcx, [r15]
0x18003ec4f  mov     rax, [rcx]
0x18003ec52  mov     rax, [rax+80h]
0x18003ec59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ec5e  mov     [rbp+57h+arg_18], eax
0x18003ec61  test    eax, eax
0x18003ec63  jns     short loc_18003EC7C
0x18003ec65  lea     rcx, aHrSpuxsignindi_18; "hr = spUxSigninDialogSettings->SetScene"...
0x18003ec6c  mov     [rsp+0D0h+var_B0], rcx
0x18003ec71  mov     r8d, 381h
0x18003ec77  jmp     loc_18003E98F
0x18003ec7c  mov     rdx, [r14+58h]
0x18003ec80  test    rdx, rdx
0x18003ec83  jz      short loc_18003ECBB
0x18003ec85  cmp     [rdx], r13w
0x18003ec89  jz      short loc_18003ECBB
0x18003ec8b  mov     rcx, [r15]
0x18003ec8e  mov     rax, [rcx]
0x18003ec91  mov     rax, [rax+90h]
0x18003ec98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ec9d  mov     [rbp+57h+arg_18], eax
0x18003eca0  test    eax, eax
0x18003eca2  jns     short loc_18003ECBB
0x18003eca4  lea     rcx, aHrSpuxsignindi_14; "hr = spUxSigninDialogSettings->SetDefau"...
0x18003ecab  mov     [rsp+0D0h+var_B0], rcx
0x18003ecb0  mov     r8d, 387h
0x18003ecb6  jmp     loc_18003E98F
0x18003ecbb  mov     r8, [r14+18h]
0x18003ecbf  test    r8, r8
0x18003ecc2  jz      short loc_18003ECFE
0x18003ecc4  cmp     [r8], r13w
0x18003ecc8  jz      short loc_18003ECFE
0x18003ecca  mov     rcx, [r15]
0x18003eccd  mov     rax, [rcx]
0x18003ecd0  xor     r9d, r9d
0x18003ecd3  lea     edx, [r9+11h]
0x18003ecd7  mov     rax, [rax+38h]
0x18003ecdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ece0  mov     [rbp+57h+arg_18], eax
0x18003ece3  test    eax, eax
0x18003ece5  jns     short loc_18003ECFE
0x18003ece7  lea     rcx, aHrSpuxsignindi_43; "hr = spUxSigninDialogSettings->SetText("...
0x18003ecee  mov     [rsp+0D0h+var_B0], rcx
0x18003ecf3  mov     r8d, 38Dh
0x18003ecf9  jmp     loc_18003E98F
0x18003ecfe  mov     r8, [r14+68h]
0x18003ed02  test    r8, r8
0x18003ed05  jz      short loc_18003ED3F
0x18003ed07  cmp     [r8], r13w
0x18003ed0b  jz      short loc_18003ED3F
0x18003ed0d  mov     rcx, [r15]
0x18003ed10  mov     rax, [rcx]
0x18003ed13  mov     edx, 11h
0x18003ed18  mov     rax, [rax+40h]
0x18003ed1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ed21  mov     [rbp+57h+arg_18], eax
0x18003ed24  test    eax, eax
0x18003ed26  jns     short loc_18003ED3F
0x18003ed28  lea     rcx, aHrSpuxsignindi_19; "hr = spUxSigninDialogSettings->SetToolt"...
0x18003ed2f  mov     [rsp+0D0h+var_B0], rcx
0x18003ed34  mov     r8d, 391h
0x18003ed3a  jmp     loc_18003E98F
0x18003ed3f  mov     r8, [r14+38h]
0x18003ed43  test    r8, r8
0x18003ed46  jz      short loc_18003ED80
0x18003ed48  cmp     [r8], r13w
0x18003ed4c  jz      short loc_18003ED80
0x18003ed4e  mov     rcx, [r15]
0x18003ed51  mov     rax, [rcx]
0x18003ed54  mov     edx, 11h
0x18003ed59  mov     rax, [rax+48h]
0x18003ed5d  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
