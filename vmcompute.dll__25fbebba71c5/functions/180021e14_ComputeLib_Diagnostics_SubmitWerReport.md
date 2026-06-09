# ComputeLib::Diagnostics::SubmitWerReport

- ea: `0x180021e14`
- end: `0x1800228e2`
- name: `ComputeLib::Diagnostics::SubmitWerReport`
- size: `2766`
- prototype: `__int64 __fastcall(PCWSTR pwzValue)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800228e8`

## callees

- `0x180002f50`
- `0x180002f74`
- `0x180006164`
- `0x180006660`
- `0x18000d108`
- `0x18000f6d8`
- `0x180014870`
- `0x180015614`
- `0x1800166fc`
- `0x180018e8c`
- `0x18001a950`
- `0x18001ab14`
- `0x180021e14`
- `0x180022c64`
- `0x1800248bc`
- `0x180024ae4`
- `0x180086010`

## import_xrefs

- `api-ms-win-core-windowserrorreporting-l1-1-1!WerRegisterCustomMetadata` at `0x18002230b`
- `api-ms-win-core-windowserrorreporting-l1-1-1!WerRegisterCustomMetadata` at `0x180022499`
- `api-ms-win-core-windowserrorreporting-l1-1-1!WerRegisterCustomMetadata` at `0x180022576`
- `api-ms-win-core-windowserrorreporting-l1-1-1!WerRegisterCustomMetadata` at `0x1800225b2`
- `api-ms-win-core-windowserrorreporting-l1-1-1!WerRegisterCustomMetadata` at `0x18002230b`
- `api-ms-win-core-windowserrorreporting-l1-1-1!WerRegisterCustomMetadata` at `0x180022499`
- `api-ms-win-core-windowserrorreporting-l1-1-1!WerRegisterCustomMetadata` at `0x180022576`
- `api-ms-win-core-windowserrorreporting-l1-1-1!WerRegisterCustomMetadata` at `0x1800225b2`
- `wer!WerReportCloseHandle` at `0x1800227d0`
- `wer!WerReportCloseHandle` at `0x1800227d0`
- `wer!WerReportAddFile` at `0x18002253d`
- `wer!WerReportAddFile` at `0x18002253d`
- `wer!WerReportSubmit` at `0x180022795`
- `wer!WerReportSubmit` at `0x180022795`
- `wer!WerReportSetParameter` at `0x180021f3a`
- `wer!WerReportSetParameter` at `0x180021f9e`
- `wer!WerReportSetParameter` at `0x180022002`
- `wer!WerReportSetParameter` at `0x180022066`
- `wer!WerReportSetParameter` at `0x1800220ca`
- `wer!WerReportSetParameter` at `0x180022698`
- `wer!WerReportSetParameter` at `0x1800226f8`
- `wer!WerReportSetParameter` at `0x180022759`
- `wer!WerReportSetParameter` at `0x180021f3a`
- `wer!WerReportSetParameter` at `0x180021f9e`
- `wer!WerReportSetParameter` at `0x180022002`
- `wer!WerReportSetParameter` at `0x180022066`
- `wer!WerReportSetParameter` at `0x1800220ca`
- `wer!WerReportSetParameter` at `0x180022698`
- `wer!WerReportSetParameter` at `0x1800226f8`
- `wer!WerReportSetParameter` at `0x180022759`
- `wer!WerReportCreate` at `0x180021ee3`
- `wer!WerReportCreate` at `0x180021ee3`

## string_xrefs

- `0x1800228bf`: `onecore\vm\common\mgmt\inc\VirtualizationSettings.h`
- `0x180021e76`: `onecore\vm\compute\common\compute\Wer.h`
- `0x18002268a`: `ComputeSystemId`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
HRESULT __fastcall ComputeLib::Diagnostics::SubmitWerReport(_QWORD *pwzValue)
{
  const WCHAR *v2; // rcx
  HRESULT v3; // eax
  __int64 v4; // rax
  const WCHAR *v5; // r9
  HRESULT v6; // eax
  __int64 v7; // rax
  const WCHAR *v8; // r9
  HRESULT v9; // eax
  __int64 v10; // rax
  const WCHAR *v11; // r9
  HRESULT v12; // eax
  __int64 v13; // rax
  const WCHAR *v14; // r9
  HRESULT v15; // eax
  __int64 v16; // rax
  const WCHAR *v17; // r9
  HRESULT v18; // eax
  Marshal::Details *v19; // rcx
  unsigned int v20; // r14d
  _WORD *v21; // rdx
  unsigned __int64 v22; // rsi
  PCWSTR v23; // rax
  __int64 v24; // rax
  HRESULT v25; // eax
  unsigned int v26; // r14d
  _WORD *v27; // rdx
  unsigned __int64 v28; // rsi
  PCWSTR v29; // rax
  unsigned __int64 v30; // r8
  PCWSTR *v31; // rdx
  const WCHAR *v32; // rdx
  HRESULT v33; // eax
  _WORD *v34; // rdx
  unsigned __int64 v35; // r8
  PCWSTR v36; // rdi
  PCWSTR v37; // rsi
  const WCHAR *v38; // rdx
  HRESULT v39; // eax
  PCWSTR v40; // rdx
  HRESULT v41; // eax
  PCWSTR v42; // rdx
  HRESULT v43; // eax
  _QWORD *v44; // rdi
  const WCHAR *v45; // r9
  HRESULT v46; // eax
  const WCHAR *v47; // r9
  HRESULT v48; // eax
  __int64 v49; // rax
  HRESULT v50; // eax
  HRESULT v51; // eax
  HRESULT result; // eax
  int v53; // [rsp+20h] [rbp-A9h]
  int v54; // [rsp+20h] [rbp-A9h]
  const char *v55; // [rsp+30h] [rbp-99h]
  _QWORD v56[2]; // [rsp+40h] [rbp-89h] BYREF
  int v57; // [rsp+50h] [rbp-79h] BYREF
  PCWSTR pwzValuea[2]; // [rsp+58h] [rbp-71h] BYREF
  unsigned __int64 v59; // [rsp+68h] [rbp-61h]
  unsigned __int64 v60; // [rsp+70h] [rbp-59h]
  HREPORT phReportHandle; // [rsp+78h] [rbp-51h] BYREF
  PCWSTR pwzPath[2]; // [rsp+80h] [rbp-49h] BYREF
  const WCHAR *v63; // [rsp+90h] [rbp-39h]
  __int64 v64; // [rsp+98h] [rbp-31h] BYREF
  PCWSTR value[2]; // [rsp+A0h] [rbp-29h] BYREF
  __int64 v66; // [rsp+B0h] [rbp-19h]
  unsigned __int64 v67; // [rsp+B8h] [rbp-11h]
  _BYTE v68[6]; // [rsp+CAh] [rbp+1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+5Fh]

  v57 = 0;
  v56[0] = &v57;
  v56[1] = pwzValue;
  LOBYTE(v53) = pwzValue[2] == 0;
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0x4A,
    (unsigned int)"onecore\\vm\\compute\\common\\compute\\Wer.h",
    (const char *)0x8037010DLL,
    v53,
    (bool)"System Id of crash report is required",
    v55);
  if ( (unsigned __int64)((__int64)(pwzValue[39] - pwzValue[38]) >> 3) < 5 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x4D,
      (unsigned int)"onecore\\vm\\compute\\common\\compute\\Wer.h",
      (const char *)0x8037010DLL,
      v54);
  if ( *((_DWORD *)pwzValue + 116) )
  {
    v2 = L"VirtualFirmwareCrashDump";
  }
  else
  {
    v2 = L"ContainerCrashDump";
    if ( v57 )
      v2 = L"VirtualMachineCrashDump";
  }
  phReportHandle = 0;
  v3 = WerReportCreate(v2, WerReportCritical, 0, &phReportHandle);
  if ( v3 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x5B,
      (unsigned int)"onecore\\vm\\compute\\common\\compute\\Wer.h",
      (const char *)(unsigned int)v3,
      v54);
  v4 = std::_UIntegral_to_buff<unsigned short,unsigned __int64>(v68, *(_QWORD *)pwzValue[38]);
  std::wstring::wstring(pwzValuea, v4, v68);
  v5 = (const WCHAR *)pwzValuea;
  if ( v60 > 7 )
    v5 = pwzValuea[0];
  v6 = WerReportSetParameter(phReportHandle, 0, L"BugcheckCode", v5);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x61,
      (unsigned int)"onecore\\vm\\compute\\common\\compute\\Wer.h",
      (const char *)(unsigned int)v6,
      v54);
  std::wstring::~wstring(pwzValuea);
  v7 = std::_UIntegral_to_buff<unsigned short,unsigned __int64>(v68, *(_QWORD *)(pwzValue[38] + 8LL));
  std::wstring::wstring(pwzValuea, v7, v68);
  v8 = (const WCHAR *)pwzValuea;
  if ( v60 > 7 )
    v8 = pwzValuea[0];
  v9 = WerReportSetParameter(phReportHandle, 1u, L"BugcheckParameter1", v8);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x67,
      (unsigned int)"onecore\\vm\\compute\\common\\compute\\Wer.h",
      (const char *)(unsigned int)v9,
      v54);
  std::wstring::~wstring(pwzValuea);
  v10 = std::_UIntegral_to_buff<unsigned short,unsigned __int64>(v68, *(_QWORD *)(pwzValue[38] + 16LL));
  std::wstring::wstring(pwzValuea, v10, v68);
  v11 = (const WCHAR *)pwzValuea;
  if ( v60 > 7 )
    v11 = pwzValuea[0];
  v12 = WerReportSetParameter(phReportHandle, 2u, L"BugcheckParameter2", v11);
  if ( v12 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x6D,
      (unsigned int)"onecore\\vm\\compute\\common\\compute\\Wer.h",
      (const char *)(unsigned int)v12,
      v54);
  std::wstring::~wstring(pwzValuea);
  v13 = std::_UIntegral_to_buff<unsigned short,unsigned __int64>(v68, *(_QWORD *)(pwzValue[38] + 24LL));
  std::wstring::wstring(pwzValuea, v13, v68);
  v14 = (const WCHAR *)pwzValuea;
  if ( v60 > 7 )
    v14 = pwzValuea[0];
  v15 = WerReportSetParameter(phReportHandle, 3u, L"BugcheckParameter3", v14);
  if ( v15 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x73,
      (unsigned int)"onecore\\vm\\compute\\common\\compute\\Wer.h",
      (const char *)(unsigned int)v15,
      v54);
  std::wstring::~wstring(pwzValuea);
  v16 = std::_UIntegral_to_buff<unsigned short,unsigned __int64>(v68, *(_QWORD *)(pwzValue[38] + 32LL));
  std::wstring::wstring(pwzValuea, v16, v68);
  v17 = (const WCHAR *)pwzValuea;
  if ( v60 > 7 )
    v17 = pwzValuea[0];
  v18 = WerReportSetParameter(phReportHandle, 4u, L"BugcheckParameter4", v17);
  if ( v18 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x79,
      (unsigned int)"onecore\\vm\\compute\\common\\compute\\Wer.h",
      (const char *)(unsigned int)v18,
      v54);
  std::wstring::~wstring(pwzValuea);
  *(_OWORD *)pwzPath = 0;
  v63 = 0;
  if ( *((_BYTE *)pwzValue + 160) )
  {
    if ( *((_DWORD *)pwzValue + 38) > 5u )
      Marshal::Details::FailFast(v19);
    v20 = *((_DWORD *)pwzValue + 37);
    v21 = *(_WORD **)(Schema::Responses::System::WindowsCrashPhase_EnumData + 8LL * *((unsigned int *)pwzValue + 38));
    *(_OWORD *)pwzValuea = 0;
    v59 = 0;
    v60 = 0;
    v22 = -1;
    do
      ++v22;
    while ( v21[v22] );
    std::wstring::_Construct<1,unsigned short const *>((__int64)pwzValuea, v21, v22);
    lambda_d79487874ee6cf89e6678931e3f6e8c0_::operator()(v56, pwzValuea, v20);
    std::wstring::~wstring(pwzValuea);
    if ( !*((_BYTE *)pwzValue + 160) )
      __fastfail(5u);
    if ( *((_DWORD *)pwzValue + 38) != 5 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x8C,
        (unsigned int)"onecore\\vm\\compute\\common\\compute\\Wer.h",
        (const char *)0x80004004LL,
        v54);
    if ( pwzPath[1] == v63 )
    {
      std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(pwzPath, pwzPath[1], pwzValue + 11);
      v23 = pwzPath[1];
    }
    else
    {
      std::wstring::wstring(pwzPath[1], pwzValue + 11);
      v23 = pwzPath[1] + 16;
      pwzPath[1] += 16;
    }
    if ( *((_BYTE *)pwzValue + 400) && *((int *)pwzValue + 98) >= 0 )
    {
      if ( v23 == v63 )
      {
        std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(pwzPath, v23, pwzValue + 45);
        v23 = pwzPath[1];
      }
      else
      {
        std::wstring::wstring(v23, pwzValue + 45);
        v23 = pwzPath[1] + 16;
        pwzPath[1] += 16;
      }
    }
    if ( *((_BYTE *)pwzValue + 448) && *((int *)pwzValue + 110) >= 0 )
    {
      if ( v23 == v63 )
      {
        std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(pwzPath, v23, pwzValue + 51);
      }
      else
      {
        std::wstring::wstring(v23, pwzValue + 51);
        pwzPath[1] += 16;
      }
    }
    if ( !*((_BYTE *)pwzValue + 160) )
      __fastfail(5u);
    v54 = *((_DWORD *)pwzValue + 32);
    v24 = Vml::FormatString(pwzValuea, (wchar_t *)L"%d.%d.%d SP %d.%d");
    if ( *(_QWORD *)(v24 + 24) > 7u )
      v24 = *(_QWORD *)v24;
    v25 = WerRegisterCustomMetadata(L"GuestOsVersion", (PCWSTR)v24);
    if ( v25 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xA4,
        (unsigned int)"onecore\\vm\\compute\\common\\compute\\Wer.h",
        (const char *)(unsigned int)v25,
        v54);
  }
  else if ( *((_BYTE *)pwzValue + 248) )
  {
    if ( *((_DWORD *)pwzValue + 61) > 4u )
      Marshal::Details::FailFast(v19);
    v26 = *((_DWORD *)pwzValue + 60);
    v27 = *(_WORD **)(Schema::Responses::System::NixCrashPhase_EnumData + 8LL * *((unsigned int *)pwzValue + 61));
    *(_OWORD *)value = 0;
    v66 = 0;
    v67 = 0;
    v28 = -1;
    do
      ++v28;
    while ( v27[v28] );
    std::wstring::_Construct<1,unsigned short const *>((__int64)value, v27, v28);
    lambda_d79487874ee6cf89e6678931e3f6e8c0_::operator()(v56, value, v26);
    std::wstring::~wstring(value);
    if ( !*((_BYTE *)pwzValue + 248) )
      __fastfail(5u);
    if ( *((_DWORD *)pwzValue + 61) != 4 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xB1,
        (unsigned int)"onecore\\vm\\compute\\common\\compute\\Wer.h",
        (const char *)0x80004004LL,
        v54);
    if ( pwzPath[1] == v63 )
    {
      std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(pwzPath, pwzPath[1], pwzValue + 21);
    }
    else
    {
      std::wstring::wstring(pwzPath[1], pwzValue + 21);
      pwzPath[1] += 16;
    }
    if ( !*((_BYTE *)pwzValue + 248) )
      __fastfail(5u);
    v29 = (PCWSTR)(pwzValue + 26);
    if ( pwzValue[29] > 7u )
      v29 = *(PCWSTR *)v29;
    v54 = (int)v29;
    Vml::FormatString(pwzValuea, (wchar_t *)L"%d.%d; %ws");
    *(_OWORD *)value = 0;
    v66 = 0;
    v67 = 0;
    v30 = 127;
    if ( v59 < 0x7F )
      v30 = v59;
    v31 = pwzValuea;
    if ( v60 > 7 )
      v31 = (PCWSTR *)pwzValuea[0];
    std::wstring::_Construct<1,unsigned short const *>((__int64)value, v31, v30);
    v32 = (const WCHAR *)value;
    if ( v67 > 7 )
      v32 = value[0];
    v33 = WerRegisterCustomMetadata(L"GuestOsVersion", v32);
    if ( v33 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xBB,
        (unsigned int)"onecore\\vm\\compute\\common\\compute\\Wer.h",
        (const char *)(unsigned int)v33,
        v54);
    std::wstring::~wstring(value);
  }
  else
  {
    v34 = *(_WORD **)(Schema::Responses::System::WindowsCrashPhase_EnumData + 8LL);
    *(_OWORD *)pwzValuea = 0;
    v59 = 0;
    v60 = 0;
    v35 = -1;
    do
      ++v35;
    while ( v34[v35] );
    std::wstring::_Construct<1,unsigned short const *>((__int64)pwzValuea, v34, v35);
    lambda_d79487874ee6cf89e6678931e3f6e8c0_::operator()(v56, pwzValuea, 0xFFFFFFFFLL);
  }
  std::wstring::~wstring(pwzValuea);
  v36 = pwzPath[0];
  v37 = pwzPath[1];
  while ( v36 != v37 )
  {
    if ( *((_QWORD *)v36 + 2) )
    {
      v38 = *((_QWORD *)v36 + 3) <= 7u ? v36 : *(const WCHAR **)v36;
      v39 = WerReportAddFile(phReportHandle, v38, WerFileTypeOther, 0);
      if ( v39 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xD3,
          (unsigned int)"onecore\\vm\\compute\\common\\compute\\Wer.h",
          (const char *)(unsigned int)v39,
          v54);
    }
    v36 += 16;
  }
  v40 = (PCWSTR)(pwzValue + 59);
  if ( pwzValue[62] > 7u )
    v40 = *(PCWSTR *)v40;
  v41 = WerRegisterCustomMetadata(L"ContainerSkuType", v40);
  if ( v41 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xD8,
      (unsigned int)"onecore\\vm\\compute\\common\\compute\\Wer.h",
      (const char *)(unsigned int)v41,
      v54);
  v42 = (PCWSTR)(pwzValue + 63);
  if ( pwzValue[66] > 7u )
    v42 = *(PCWSTR *)v42;
  v43 = WerRegisterCustomMetadata(L"ScenarioOwner", v42);
  if ( v43 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xDC,
      (unsigned int)"onecore\\vm\\compute\\common\\compute\\Wer.h",
      (const char *)(unsigned int)v43,
      v54);
  *(_OWORD *)value = 0;
  v44 = operator new(0x30u);
  *v44 = &Vml::VmMachineLocalSettingsStore::`vftable';
  v44[1] = 0;
  *((_OWORD *)v44 + 1) = 0;
  v44[4] = 0;
  v44[5] = 7;
  *((_WORD *)v44 + 8) = 0;
  v64 = 0;
  value[0] = (PCWSTR)&VirtualizationSettings::`vftable';
  v56[0] = 0;
  value[1] = (PCWSTR)v44;
  if ( !(*(unsigned __int8 (__fastcall **)(_QWORD *, _QWORD, __int64))(*v44 + 8LL))(v44, 0, 131097) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xAB,
      (unsigned int)"onecore\\vm\\common\\mgmt\\inc\\VirtualizationSettings.h",
      (const char *)0x8000FFFFLL,
      v54);
  LODWORD(v64) = 0;
  if ( (*(unsigned __int8 (__fastcall **)(_QWORD *, const unsigned __int16 *, __int64 *))(*v44 + 56LL))(
         v44,
         L"AzureFeatureSet",
         &v64)
    && (_DWORD)v64 )
  {
    if ( pwzValue[3] <= 7u )
      v45 = (const WCHAR *)pwzValue;
    else
      v45 = (const WCHAR *)*pwzValue;
    v46 = WerReportSetParameter(phReportHandle, 5u, L"ComputeSystemId", v45);
    if ( v46 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xE8,
        (unsigned int)"onecore\\vm\\compute\\common\\compute\\Wer.h",
        (const char *)(unsigned int)v46,
        v54);
    if ( *((_BYTE *)pwzValue + 64) )
    {
      std::wstring::wstring(pwzValuea, pwzValue + 4);
      v47 = (const WCHAR *)pwzValuea;
      if ( v60 > 7 )
        v47 = pwzValuea[0];
      v48 = WerReportSetParameter(phReportHandle, 6u, L"AzureContainerId", v47);
      if ( v48 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xF1,
          (unsigned int)"onecore\\vm\\compute\\common\\compute\\Wer.h",
          (const char *)(unsigned int)v48,
          v54);
      std::wstring::~wstring(pwzValuea);
    }
    v49 = Vml::FormatString(pwzValuea, (wchar_t *)L"%d");
    if ( *(_QWORD *)(v49 + 24) > 7u )
      v49 = *(_QWORD *)v49;
    v50 = WerReportSetParameter(phReportHandle, 7u, L"Vtl", (PCWSTR)v49);
    if ( v50 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xFA,
        (unsigned int)"onecore\\vm\\compute\\common\\compute\\Wer.h",
        (const char *)(unsigned int)v50,
        v54);
    std::wstring::~wstring(pwzValuea);
  }
  v51 = WerReportSubmit(phReportHandle, WerConsentNotAsked, 0x20u, 0);
  if ( v51 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x101,
      (unsigned int)"onecore\\vm\\compute\\common\\compute\\Wer.h",
      (const char *)(unsigned int)v51,
      v54);
  (*(void (__fastcall **)(_QWORD *, __int64))*v44)(v44, 1);
  result = std::vector<std::wstring>::_Tidy(pwzPath);
  if ( phReportHandle )
    return WerReportCloseHandle(phReportHandle);
  return result;
}

```

## disassembly

```asm
0x180021e14  push    rbp
0x180021e16  push    rbx
0x180021e17  push    rsi
0x180021e18  push    rdi
0x180021e19  push    r12
0x180021e1b  push    r13
0x180021e1d  push    r14
0x180021e1f  push    r15
0x180021e21  lea     rbp, [rsp-1Fh]
0x180021e26  sub     rsp, 0E8h
0x180021e2d  mov     rax, cs:__security_cookie
0x180021e34  xor     rax, rsp
0x180021e37  mov     [rbp+57h+var_50], rax
0x180021e3b  mov     rbx, rcx
0x180021e3e  xor     r15d, r15d
0x180021e41  mov     [rbp+57h+var_D0], r15d
0x180021e45  lea     rax, [rbp+57h+var_D0]
0x180021e49  mov     [rsp+120h+var_E0], rax
0x180021e4e  mov     [rsp+120h+var_D8], rcx
0x180021e53  cmp     [rcx+10h], r15
0x180021e57  setz    al
0x180021e5a  mov     rcx, [rbp+5Fh]; this
0x180021e5e  lea     rdx, aSystemIdOfCras; "System Id of crash report is required"
0x180021e65  mov     qword ptr [rsp+120h+var_F8], rdx; bool
0x180021e6a  mov     byte ptr [rsp+120h+var_100], al; int
0x180021e6e  mov     edi, 8037010Dh
0x180021e73  mov     r9d, edi; char *
0x180021e76  lea     r13, aOnecoreVmCompu_20; "onecore\\vm\\compute\\common\\compute\\"...
0x180021e7d  mov     r8, r13; unsigned int
0x180021e80  lea     edx, [r15+4Ah]; void *
0x180021e84  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180021e89  mov     rcx, [rbp+5Fh]; this
0x180021e8d  mov     rax, [rbx+138h]
0x180021e94  sub     rax, [rbx+130h]
0x180021e9b  sar     rax, 3
0x180021e9f  lea     r12d, [r15+5]
0x180021ea3  cmp     rax, r12
0x180021ea6  jb      loc_18002280E
0x180021eac  cmp     [rbx+1D0h], r15d
0x180021eb3  jnz     short loc_180021ECD
0x180021eb5  lea     rcx, aContainercrash; "ContainerCrashDump"
0x180021ebc  lea     rax, aVirtualmachine; "VirtualMachineCrashDump"
0x180021ec3  cmp     [rbp+57h+var_D0], r15d
0x180021ec7  cmovnz  rcx, rax
0x180021ecb  jmp     short loc_180021ED4
0x180021ecd  lea     rcx, pwzEventType; "VirtualFirmwareCrashDump"
0x180021ed4  mov     [rbp+57h+phReportHandle], r15
0x180021ed8  lea     r9, [rbp+57h+phReportHandle]; phReportHandle
0x180021edc  xor     r8d, r8d; pReportInformation
0x180021edf  lea     edx, [r8+1]; repType
0x180021ee3  call    cs:__imp_WerReportCreate
0x180021eea  nop     dword ptr [rax+rax+00h]
0x180021eef  mov     rcx, [rbp+5Fh]; this
0x180021ef3  test    eax, eax
0x180021ef5  js      loc_18002281F
0x180021efb  mov     rdx, [rbx+130h]
0x180021f02  mov     rdx, [rdx]
0x180021f05  lea     rcx, [rbp+57h+var_56]
0x180021f09  call    ??$_UIntegral_to_buff@G_K@std@@YAPEAGPEAG_K@Z; std::_UIntegral_to_buff<ushort,unsigned __int64>(ushort *,unsigned __int64)
0x180021f0e  lea     r8, [rbp+57h+var_56]
0x180021f12  mov     rdx, rax
0x180021f15  lea     rcx, [rbp+57h+pwzValue]
0x180021f19  call    ??$?0PEAG$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEAG0AEBV?$allocator@G@1@@Z; std::wstring::wstring(ushort *,ushort *,std::allocator<ushort> const &)
0x180021f1e  nop
0x180021f1f  lea     r9, [rbp+57h+pwzValue]
0x180021f23  cmp     [rbp+57h+var_B0], 7
0x180021f28  cmova   r9, [rbp+57h+pwzValue]; pwzValue
0x180021f2d  lea     r8, pwzName; "BugcheckCode"
0x180021f34  xor     edx, edx; dwparamID
0x180021f36  mov     rcx, [rbp+57h+phReportHandle]; hReportHandle
0x180021f3a  call    cs:__imp_WerReportSetParameter
0x180021f41  nop     dword ptr [rax+rax+00h]
0x180021f46  mov     rcx, [rbp+5Fh]; this
0x180021f4a  test    eax, eax
0x180021f4c  js      loc_180022830
0x180021f52  lea     rcx, [rbp+57h+pwzValue]
0x180021f56  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180021f5b  mov     rdx, [rbx+130h]
0x180021f62  mov     rdx, [rdx+8]
0x180021f66  lea     rcx, [rbp+57h+var_56]
0x180021f6a  call    ??$_UIntegral_to_buff@G_K@std@@YAPEAGPEAG_K@Z; std::_UIntegral_to_buff<ushort,unsigned __int64>(ushort *,unsigned __int64)
0x180021f6f  lea     r8, [rbp+57h+var_56]
0x180021f73  mov     rdx, rax
0x180021f76  lea     rcx, [rbp+57h+pwzValue]
0x180021f7a  call    ??$?0PEAG$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEAG0AEBV?$allocator@G@1@@Z; std::wstring::wstring(ushort *,ushort *,std::allocator<ushort> const &)
0x180021f7f  nop
0x180021f80  lea     r9, [rbp+57h+pwzValue]
0x180021f84  cmp     [rbp+57h+var_B0], 7
0x180021f89  cmova   r9, [rbp+57h+pwzValue]; pwzValue
0x180021f8e  lea     r8, aBugcheckparame_1; "BugcheckParameter1"
0x180021f95  mov     edx, 1; dwparamID
0x180021f9a  mov     rcx, [rbp+57h+phReportHandle]; hReportHandle
0x180021f9e  call    cs:__imp_WerReportSetParameter
0x180021fa5  nop     dword ptr [rax+rax+00h]
0x180021faa  mov     rcx, [rbp+5Fh]; this
0x180021fae  test    eax, eax
0x180021fb0  js      loc_180022841
0x180021fb6  lea     rcx, [rbp+57h+pwzValue]
0x180021fba  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180021fbf  mov     rdx, [rbx+130h]
0x180021fc6  mov     rdx, [rdx+10h]
0x180021fca  lea     rcx, [rbp+57h+var_56]
0x180021fce  call    ??$_UIntegral_to_buff@G_K@std@@YAPEAGPEAG_K@Z; std::_UIntegral_to_buff<ushort,unsigned __int64>(ushort *,unsigned __int64)
0x180021fd3  lea     r8, [rbp+57h+var_56]
0x180021fd7  mov     rdx, rax
0x180021fda  lea     rcx, [rbp+57h+pwzValue]
0x180021fde  call    ??$?0PEAG$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEAG0AEBV?$allocator@G@1@@Z; std::wstring::wstring(ushort *,ushort *,std::allocator<ushort> const &)
0x180021fe3  nop
0x180021fe4  lea     r9, [rbp+57h+pwzValue]
0x180021fe8  cmp     [rbp+57h+var_B0], 7
0x180021fed  cmova   r9, [rbp+57h+pwzValue]; pwzValue
0x180021ff2  lea     r8, aBugcheckparame_0; "BugcheckParameter2"
0x180021ff9  mov     edx, 2; dwparamID
0x180021ffe  mov     rcx, [rbp+57h+phReportHandle]; hReportHandle
0x180022002  call    cs:__imp_WerReportSetParameter
0x180022009  nop     dword ptr [rax+rax+00h]
0x18002200e  mov     rcx, [rbp+5Fh]; this
0x180022012  test    eax, eax
0x180022014  js      loc_180022852
0x18002201a  lea     rcx, [rbp+57h+pwzValue]
0x18002201e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180022023  mov     rdx, [rbx+130h]
0x18002202a  mov     rdx, [rdx+18h]
0x18002202e  lea     rcx, [rbp+57h+var_56]
0x180022032  call    ??$_UIntegral_to_buff@G_K@std@@YAPEAGPEAG_K@Z; std::_UIntegral_to_buff<ushort,unsigned __int64>(ushort *,unsigned __int64)
0x180022037  lea     r8, [rbp+57h+var_56]
0x18002203b  mov     rdx, rax
0x18002203e  lea     rcx, [rbp+57h+pwzValue]
0x180022042  call    ??$?0PEAG$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEAG0AEBV?$allocator@G@1@@Z; std::wstring::wstring(ushort *,ushort *,std::allocator<ushort> const &)
0x180022047  nop
0x180022048  lea     r9, [rbp+57h+pwzValue]
0x18002204c  cmp     [rbp+57h+var_B0], 7
0x180022051  cmova   r9, [rbp+57h+pwzValue]; pwzValue
0x180022056  lea     r8, aBugcheckparame_2; "BugcheckParameter3"
0x18002205d  mov     edx, 3; dwparamID
0x180022062  mov     rcx, [rbp+57h+phReportHandle]; hReportHandle
0x180022066  call    cs:__imp_WerReportSetParameter
0x18002206d  nop     dword ptr [rax+rax+00h]
0x180022072  mov     rcx, [rbp+5Fh]; this
0x180022076  test    eax, eax
0x180022078  js      loc_180022863
0x18002207e  lea     rcx, [rbp+57h+pwzValue]
0x180022082  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180022087  mov     rdx, [rbx+130h]
0x18002208e  mov     rdx, [rdx+20h]
0x180022092  lea     rcx, [rbp+57h+var_56]
0x180022096  call    ??$_UIntegral_to_buff@G_K@std@@YAPEAGPEAG_K@Z; std::_UIntegral_to_buff<ushort,unsigned __int64>(ushort *,unsigned __int64)
0x18002209b  lea     r8, [rbp+57h+var_56]
0x18002209f  mov     rdx, rax
0x1800220a2  lea     rcx, [rbp+57h+pwzValue]
0x1800220a6  call    ??$?0PEAG$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEAG0AEBV?$allocator@G@1@@Z; std::wstring::wstring(ushort *,ushort *,std::allocator<ushort> const &)
0x1800220ab  nop
0x1800220ac  lea     r9, [rbp+57h+pwzValue]
0x1800220b0  cmp     [rbp+57h+var_B0], 7
0x1800220b5  cmova   r9, [rbp+57h+pwzValue]; pwzValue
0x1800220ba  lea     r8, aBugcheckparame; "BugcheckParameter4"
0x1800220c1  mov     edx, 4; dwparamID
0x1800220c6  mov     rcx, [rbp+57h+phReportHandle]; hReportHandle
0x1800220ca  call    cs:__imp_WerReportSetParameter
0x1800220d1  nop     dword ptr [rax+rax+00h]
0x1800220d6  mov     rcx, [rbp+5Fh]; this
0x1800220da  test    eax, eax
0x1800220dc  js      loc_180022874
0x1800220e2  lea     rcx, [rbp+57h+pwzValue]
0x1800220e6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800220eb  xorps   xmm0, xmm0
0x1800220ee  xorps   xmm1, xmm1
0x1800220f1  movdqu  xmmword ptr [rbp+57h+pwzPath], xmm1
0x1800220f6  mov     [rbp+57h+var_90], r15
0x1800220fa  cmp     [rbx+0A0h], r15b
0x180022101  jz      loc_180022338
0x180022107  mov     al, [rbx+0A0h]
0x18002210d  test    al, al
0x18002210f  jnz     short loc_18002211C
0x180022111  mov     rcx, r12
0x180022114  int     29h; Win8: RtlFailFast(ecx)
0x180022116  test    al, al
0x180022118  jnz     short loc_18002211C
0x18002211a  int     29h; Win8: RtlFailFast(ecx)
0x18002211c  cmp     [rbx+98h], r12d
0x180022123  ja      loc_180022899
0x180022129  mov     r14d, [rbx+94h]
0x180022130  mov     rcx, cs:?WindowsCrashPhase_EnumData@System@Responses@Schema@@3UEnumData@Marshal@@B; Marshal::EnumData const Schema::Responses::System::WindowsCrashPhase_EnumData
0x180022137  mov     eax, [rbx+98h]
0x18002213d  mov     rdx, [rcx+rax*8]
0x180022141  movups  xmmword ptr [rbp+57h+pwzValue], xmm0
0x180022145  mov     [rbp+57h+var_B8], r15
0x180022149  mov     [rbp+57h+var_B0], r15
0x18002214d  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180022151  inc     rsi
0x180022154  cmp     [rdx+rsi*2], r15w
0x180022159  jnz     short loc_180022151
0x18002215b  mov     r8, rsi
0x18002215e  lea     rcx, [rbp+57h+pwzValue]
0x180022162  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180022167  mov     r8d, r14d
0x18002216a  lea     rdx, [rbp+57h+pwzValue]
0x18002216e  lea     rcx, [rsp+120h+var_E0]
0x180022173  call    _lambda_d79487874ee6cf89e6678931e3f6e8c0___operator__
0x180022178  lea     rcx, [rbp+57h+pwzValue]
0x18002217c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180022181  mov     al, [rbx+0A0h]
0x180022187  test    al, al
0x180022189  jnz     short loc_180022190
0x18002218b  mov     rcx, r12
0x18002218e  int     29h; Win8: RtlFailFast(ecx)
0x180022190  mov     rcx, [rbp+5Fh]; this
0x180022194  cmp     [rbx+98h], r12d
0x18002219b  jnz     loc_180022885
0x1800221a1  test    al, al
0x1800221a3  jnz     short loc_1800221AA
0x1800221a5  mov     rcx, r12
0x1800221a8  int     29h; Win8: RtlFailFast(ecx)
0x1800221aa  mov     rax, [rbp+57h+pwzPath+8]
0x1800221ae  cmp     rax, [rbp+57h+var_90]
0x1800221b2  jz      short loc_1800221CE
0x1800221b4  lea     rdx, [rbx+58h]
0x1800221b8  mov     rcx, rax
0x1800221bb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800221c0  mov     rax, [rbp+57h+pwzPath+8]
0x1800221c4  add     rax, 20h ; ' '
0x1800221c8  mov     [rbp+57h+pwzPath+8], rax
0x1800221cc  jmp     short loc_1800221E2
0x1800221ce  lea     r8, [rbx+58h]
0x1800221d2  mov     rdx, rax
0x1800221d5  lea     rcx, [rbp+57h+pwzPath]
0x1800221d9  call    ??$_Emplace_reallocate@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@AEBV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(std::wstring * const,std::wstring const &)
0x1800221de  mov     rax, [rbp+57h+pwzPath+8]
0x1800221e2  cmp     [rbx+190h], r15b
0x1800221e9  jz      short loc_18002223D
0x1800221eb  lea     r8, [rbx+168h]
0x1800221f2  mov     dl, [r8+28h]
0x1800221f6  test    dl, dl
0x1800221f8  jnz     short loc_1800221FF
0x1800221fa  mov     rcx, r12
0x1800221fd  int     29h; Win8: RtlFailFast(ecx)
0x1800221ff  cmp     [r8+20h], r15d
0x180022203  jl      short loc_18002223D
0x180022205  test    dl, dl
0x180022207  jnz     short loc_18002220E
0x180022209  mov     rcx, r12
0x18002220c  int     29h; Win8: RtlFailFast(ecx)
0x18002220e  cmp     rax, [rbp+57h+var_90]
0x180022212  jz      short loc_18002222D
0x180022214  mov     rdx, r8
0x180022217  mov     rcx, rax
0x18002221a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002221f  mov     rax, [rbp+57h+pwzPath+8]
0x180022223  add     rax, 20h ; ' '
0x180022227  mov     [rbp+57h+pwzPath+8], rax
0x18002222b  jmp     short loc_18002223D
0x18002222d  mov     rdx, rax
0x180022230  lea     rcx, [rbp+57h+pwzPath]
0x180022234  call    ??$_Emplace_reallocate@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@AEBV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(std::wstring * const,std::wstring const &)
0x180022239  mov     rax, [rbp+57h+pwzPath+8]
0x18002223d  cmp     [rbx+1C0h], r15b
0x180022244  jz      short loc_18002228D
0x180022246  lea     r8, [rbx+198h]
0x18002224d  mov     dl, [r8+28h]
0x180022251  test    dl, dl
0x180022253  jnz     short loc_18002225A
0x180022255  mov     rcx, r12
0x180022258  int     29h; Win8: RtlFailFast(ecx)
0x18002225a  cmp     [r8+20h], r15d
0x18002225e  jl      short loc_18002228D
0x180022260  test    dl, dl
0x180022262  jnz     short loc_180022269
0x180022264  mov     rcx, r12
0x180022267  int     29h; Win8: RtlFailFast(ecx)
0x180022269  cmp     rax, [rbp+57h+var_90]
0x18002226d  jz      short loc_180022281
0x18002226f  mov     rdx, r8
0x180022272  mov     rcx, rax
0x180022275  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002227a  add     [rbp+57h+pwzPath+8], 20h ; ' '
0x18002227f  jmp     short loc_18002228D
0x180022281  mov     rdx, rax
0x180022284  lea     rcx, [rbp+57h+pwzPath]
0x180022288  call    ??$_Emplace_reallocate@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@AEBV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(std::wstring * const,std::wstring const &)
0x18002228d  mov     al, [rbx+0A0h]
0x180022293  test    al, al
0x180022295  jnz     short loc_18002229C
0x180022297  mov     rcx, r12
0x18002229a  int     29h; Win8: RtlFailFast(ecx)
0x18002229c  mov     r9d, [rbx+88h]
0x1800222a3  test    al, al
0x1800222a5  jnz     short loc_1800222AC
0x1800222a7  mov     rcx, r12
0x1800222aa  int     29h; Win8: RtlFailFast(ecx)
0x1800222ac  mov     r8d, [rbx+84h]
0x1800222b3  test    al, al
0x1800222b5  jnz     short loc_1800222BC
0x1800222b7  mov     rcx, r12
0x1800222ba  int     29h; Win8: RtlFailFast(ecx)
0x1800222bc  mov     edx, [rbx+80h]
0x1800222c2  test    al, al
0x1800222c4  jnz     short loc_1800222D1
0x1800222c6  mov     rcx, r12
0x1800222c9  int     29h; Win8: RtlFailFast(ecx)
0x1800222cb  test    al, al
  ... truncated ...
```
