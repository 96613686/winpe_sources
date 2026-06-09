# ComputeLib::Diagnostics::SubmitWerReport

- ea: `0x140083888`
- end: `0x14008415c`
- name: `ComputeLib::Diagnostics::SubmitWerReport`
- size: `2260`
- prototype: `__int64 __fastcall(PCWSTR pwzValue)`
- caller_count: `1`
- callee_count: `23`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1401df268`

## callees

- `0x140017040`
- `0x140018d70`
- `0x14001bce0`
- `0x14001d490`
- `0x140026a3c`
- `0x140056548`
- `0x14005b550`
- `0x140076488`
- `0x140082f4c`
- `0x140083888`
- `0x140084164`
- `0x1400857b4`
- `0x1400857dc`
- `0x140085800`
- `0x1400bf4d0`
- `0x1400c40e0`
- `0x14010ddb4`
- `0x1401332f0`
- `0x140188504`
- `0x140189f38`
- `0x140190b40`
- `0x1401b2438`
- `0x1401ddc6c`

## import_xrefs

- `api-ms-win-core-windowserrorreporting-l1-1-1!WerRegisterCustomMetadata` at `0x140083d1e`
- `api-ms-win-core-windowserrorreporting-l1-1-1!WerRegisterCustomMetadata` at `0x140083e60`
- `api-ms-win-core-windowserrorreporting-l1-1-1!WerRegisterCustomMetadata` at `0x140083f24`
- `api-ms-win-core-windowserrorreporting-l1-1-1!WerRegisterCustomMetadata` at `0x140083f60`
- `api-ms-win-core-windowserrorreporting-l1-1-1!WerRegisterCustomMetadata` at `0x140083d1e`
- `api-ms-win-core-windowserrorreporting-l1-1-1!WerRegisterCustomMetadata` at `0x140083e60`
- `api-ms-win-core-windowserrorreporting-l1-1-1!WerRegisterCustomMetadata` at `0x140083f24`
- `api-ms-win-core-windowserrorreporting-l1-1-1!WerRegisterCustomMetadata` at `0x140083f60`
- `wer!WerReportAddFile` at `0x140083eeb`
- `wer!WerReportAddFile` at `0x140083eeb`
- `wer!WerReportCreate` at `0x140083969`
- `wer!WerReportCreate` at `0x140083969`
- `wer!WerReportSetParameter` at `0x1400839cd`
- `wer!WerReportSetParameter` at `0x140083a3b`
- `wer!WerReportSetParameter` at `0x140083aac`
- `wer!WerReportSetParameter` at `0x140083b1d`
- `wer!WerReportSetParameter` at `0x140083b8e`
- `wer!WerReportSetParameter` at `0x140083fff`
- `wer!WerReportSetParameter` at `0x140084054`
- `wer!WerReportSetParameter` at `0x1400840b5`
- `wer!WerReportSetParameter` at `0x1400839cd`
- `wer!WerReportSetParameter` at `0x140083a3b`
- `wer!WerReportSetParameter` at `0x140083aac`
- `wer!WerReportSetParameter` at `0x140083b1d`
- `wer!WerReportSetParameter` at `0x140083b8e`
- `wer!WerReportSetParameter` at `0x140083fff`
- `wer!WerReportSetParameter` at `0x140084054`
- `wer!WerReportSetParameter` at `0x1400840b5`
- `wer!WerReportSubmit` at `0x1400840f1`
- `wer!WerReportSubmit` at `0x1400840f1`

## string_xrefs

- `0x1400838f4`: `onecore\vm\compute\common\compute\Wer.h`
- `0x140083ff1`: `ComputeSystemId`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall ComputeLib::Diagnostics::SubmitWerReport(_QWORD *pwzValue)
{
  __int64 v2; // r8
  const WCHAR *v3; // rcx
  HRESULT v4; // eax
  __int64 v5; // rax
  const WCHAR *v6; // r9
  HRESULT v7; // eax
  __int64 v8; // rax
  const WCHAR *v9; // r9
  HRESULT v10; // eax
  __int64 v11; // rax
  const WCHAR *v12; // r9
  HRESULT v13; // eax
  __int64 v14; // rax
  const WCHAR *v15; // r9
  HRESULT v16; // eax
  __int64 v17; // rax
  const WCHAR *v18; // r9
  HRESULT v19; // eax
  unsigned int v20; // ebx
  __int64 v21; // rax
  __int64 v22; // rax
  HRESULT v23; // eax
  __int64 v24; // rcx
  unsigned int v25; // ebx
  PCWSTR v26; // rax
  __int64 v27; // rax
  HRESULT v28; // eax
  __int64 v29; // rax
  PCWSTR v30; // rbx
  PCWSTR v31; // rsi
  const WCHAR *v32; // rdx
  HRESULT v33; // eax
  PCWSTR v34; // rdx
  HRESULT v35; // eax
  PCWSTR v36; // rdx
  HRESULT v37; // eax
  __int64 *v38; // rax
  __int64 v39; // rcx
  __int64 v40; // rdx
  __int64 v41; // r8
  const WCHAR *v42; // r9
  HRESULT v43; // eax
  const WCHAR *v44; // r9
  HRESULT v45; // eax
  __int64 v46; // rax
  HRESULT v47; // eax
  HRESULT v48; // eax
  int v50; // [rsp+20h] [rbp-99h]
  const char *v51; // [rsp+30h] [rbp-89h]
  __int64 v52; // [rsp+40h] [rbp-79h] BYREF
  _BYTE v53[16]; // [rsp+48h] [rbp-71h] BYREF
  int v54; // [rsp+58h] [rbp-61h] BYREF
  HREPORT phReportHandle; // [rsp+60h] [rbp-59h] BYREF
  PCWSTR pwzValuea[3]; // [rsp+68h] [rbp-51h] BYREF
  unsigned __int64 v57; // [rsp+80h] [rbp-39h]
  PCWSTR pwzPath[2]; // [rsp+88h] [rbp-31h] BYREF
  __int64 v59; // [rsp+98h] [rbp-21h]
  __int128 v60; // [rsp+A0h] [rbp-19h] BYREF
  _BYTE v61[42]; // [rsp+B0h] [rbp-9h] BYREF
  _BYTE v62[6]; // [rsp+DAh] [rbp+21h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  v54 = 1;
  lambda_bffcbee7f2770ed84e920f222a7c63ec_::_lambda_bffcbee7f2770ed84e920f222a7c63ec_(v53, &v54, pwzValue);
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0x4A,
    (unsigned int)"onecore\\vm\\compute\\common\\compute\\Wer.h",
    (const char *)0x8037010DLL,
    *(_QWORD *)(v2 + 16) == 0,
    (bool)"System Id of crash report is required",
    v51);
  if ( (unsigned __int64)((__int64)(pwzValue[39] - pwzValue[38]) >> 3) < 5 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x4D,
      (unsigned int)"onecore\\vm\\compute\\common\\compute\\Wer.h",
      (const char *)0x8037010DLL,
      v50);
  if ( *((_DWORD *)pwzValue + 116) )
  {
    v3 = L"VirtualFirmwareCrashDump";
  }
  else
  {
    v3 = L"ContainerCrashDump";
    if ( v54 )
      v3 = L"VirtualMachineCrashDump";
  }
  phReportHandle = 0;
  v4 = WerReportCreate(v3, WerReportCritical, 0, &phReportHandle);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x5B,
      (unsigned int)"onecore\\vm\\compute\\common\\compute\\Wer.h",
      (const char *)(unsigned int)v4,
      v50);
  v5 = std::_UIntegral_to_buff<unsigned short,unsigned __int64>(v62, *(_QWORD *)pwzValue[38]);
  std::wstring::wstring(pwzValuea, v5, v62);
  v6 = (const WCHAR *)pwzValuea;
  if ( v57 > 7 )
    v6 = pwzValuea[0];
  v7 = WerReportSetParameter(phReportHandle, 0, L"BugcheckCode", v6);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x61,
      (unsigned int)"onecore\\vm\\compute\\common\\compute\\Wer.h",
      (const char *)(unsigned int)v7,
      v50);
  Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)pwzValuea);
  v8 = std::_UIntegral_to_buff<unsigned short,unsigned __int64>(v62, *(_QWORD *)(pwzValue[38] + 8LL));
  std::wstring::wstring(pwzValuea, v8, v62);
  v9 = (const WCHAR *)pwzValuea;
  if ( v57 > 7 )
    v9 = pwzValuea[0];
  v10 = WerReportSetParameter(phReportHandle, 1u, L"BugcheckParameter1", v9);
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x67,
      (unsigned int)"onecore\\vm\\compute\\common\\compute\\Wer.h",
      (const char *)(unsigned int)v10,
      v50);
  Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)pwzValuea);
  v11 = std::_UIntegral_to_buff<unsigned short,unsigned __int64>(v62, *(_QWORD *)(pwzValue[38] + 16LL));
  std::wstring::wstring(pwzValuea, v11, v62);
  v12 = (const WCHAR *)pwzValuea;
  if ( v57 > 7 )
    v12 = pwzValuea[0];
  v13 = WerReportSetParameter(phReportHandle, 2u, L"BugcheckParameter2", v12);
  if ( v13 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x6D,
      (unsigned int)"onecore\\vm\\compute\\common\\compute\\Wer.h",
      (const char *)(unsigned int)v13,
      v50);
  Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)pwzValuea);
  v14 = std::_UIntegral_to_buff<unsigned short,unsigned __int64>(v62, *(_QWORD *)(pwzValue[38] + 24LL));
  std::wstring::wstring(pwzValuea, v14, v62);
  v15 = (const WCHAR *)pwzValuea;
  if ( v57 > 7 )
    v15 = pwzValuea[0];
  v16 = WerReportSetParameter(phReportHandle, 3u, L"BugcheckParameter3", v15);
  if ( v16 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x73,
      (unsigned int)"onecore\\vm\\compute\\common\\compute\\Wer.h",
      (const char *)(unsigned int)v16,
      v50);
  Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)pwzValuea);
  v17 = std::_UIntegral_to_buff<unsigned short,unsigned __int64>(v62, *(_QWORD *)(pwzValue[38] + 32LL));
  std::wstring::wstring(pwzValuea, v17, v62);
  v18 = (const WCHAR *)pwzValuea;
  if ( v57 > 7 )
    v18 = pwzValuea[0];
  v19 = WerReportSetParameter(phReportHandle, 4u, L"BugcheckParameter4", v18);
  if ( v19 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x79,
      (unsigned int)"onecore\\vm\\compute\\common\\compute\\Wer.h",
      (const char *)(unsigned int)v19,
      v50);
  Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)pwzValuea);
  *(_OWORD *)pwzPath = 0;
  v59 = 0;
  std::vector<Config::VirtualMachine::VpSubnodeMetadata>::vector<Config::VirtualMachine::VpSubnodeMetadata>(pwzPath);
  if ( *((_BYTE *)pwzValue + 160) )
  {
    v20 = *((_DWORD *)pwzValue + 37);
    v21 = Marshal::EnumToString<enum Schema::Responses::System::WindowsCrashPhase,0>(*((unsigned int *)pwzValue + 38));
    std::wstring::wstring(pwzValuea, v21);
    lambda_1076b0aedadf1a66c6313478c40a3126_::operator()(v53, pwzValuea, v20);
    Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)pwzValuea);
    if ( !*((_BYTE *)pwzValue + 160) )
      __fastfail(5u);
    if ( *((_DWORD *)pwzValue + 38) != 5 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x8C,
        (unsigned int)"onecore\\vm\\compute\\common\\compute\\Wer.h",
        (const char *)0x80004004LL,
        v50);
    std::vector<std::wstring>::_Emplace_one_at_back<std::wstring const &>(pwzPath, pwzValue + 11);
    if ( *((_BYTE *)pwzValue + 400) && *((int *)pwzValue + 98) >= 0 )
      std::vector<std::wstring>::_Emplace_one_at_back<std::wstring const &>(pwzPath, pwzValue + 45);
    if ( *((_BYTE *)pwzValue + 448) && *((int *)pwzValue + 110) >= 0 )
      std::vector<std::wstring>::_Emplace_one_at_back<std::wstring const &>(pwzPath, pwzValue + 51);
    if ( !*((_BYTE *)pwzValue + 160) )
      __fastfail(5u);
    v50 = *((_DWORD *)pwzValue + 32);
    v22 = Vml::FormatString(
            v61,
            L"%d.%d.%d SP %d.%d",
            *((unsigned int *)pwzValue + 30),
            *((unsigned int *)pwzValue + 31));
    if ( *(_QWORD *)(v22 + 24) > 7u )
      v22 = *(_QWORD *)v22;
    v23 = WerRegisterCustomMetadata(L"GuestOsVersion", (PCWSTR)v22);
    if ( v23 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xA4,
        (unsigned int)"onecore\\vm\\compute\\common\\compute\\Wer.h",
        (const char *)(unsigned int)v23,
        v50);
  }
  else if ( *((_BYTE *)pwzValue + 248) )
  {
    v24 = *((unsigned int *)pwzValue + 61);
    if ( (unsigned int)v24 > 4 )
      __fastfail(5u);
    v25 = *((_DWORD *)pwzValue + 60);
    std::wstring::wstring(pwzValuea, *(_QWORD *)(Schema::Responses::System::NixCrashPhase_EnumData + 8 * v24));
    lambda_1076b0aedadf1a66c6313478c40a3126_::operator()(v53, pwzValuea, v25);
    Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)pwzValuea);
    if ( !*((_BYTE *)pwzValue + 248) )
      __fastfail(5u);
    if ( *((_DWORD *)pwzValue + 61) != 4 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xB1,
        (unsigned int)"onecore\\vm\\compute\\common\\compute\\Wer.h",
        (const char *)0x80004004LL,
        v50);
    std::vector<std::wstring>::_Emplace_one_at_back<std::wstring const &>(pwzPath, pwzValue + 21);
    if ( !*((_BYTE *)pwzValue + 248) )
      __fastfail(5u);
    v26 = (PCWSTR)(pwzValue + 26);
    if ( pwzValue[29] > 7u )
      v26 = *(PCWSTR *)v26;
    v50 = (int)v26;
    Vml::FormatString(v61, L"%d.%d; %ws", *((unsigned int *)pwzValue + 50), *((unsigned int *)pwzValue + 51));
    v27 = std::wstring::substr(v61, pwzValuea, 0, 127);
    if ( *(_QWORD *)(v27 + 24) > 7u )
      v27 = *(_QWORD *)v27;
    v28 = WerRegisterCustomMetadata(L"GuestOsVersion", (PCWSTR)v27);
    if ( v28 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xBB,
        (unsigned int)"onecore\\vm\\compute\\common\\compute\\Wer.h",
        (const char *)(unsigned int)v28,
        v50);
    Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)pwzValuea);
  }
  else
  {
    v29 = Marshal::EnumToString<enum Schema::Responses::System::WindowsCrashPhase,0>(1);
    std::wstring::wstring(v61, v29);
    lambda_1076b0aedadf1a66c6313478c40a3126_::operator()(v53, v61, 0xFFFFFFFFLL);
  }
  Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)v61);
  v30 = pwzPath[0];
  v31 = pwzPath[1];
  while ( v30 != v31 )
  {
    if ( *((_QWORD *)v30 + 2) )
    {
      v32 = *((_QWORD *)v30 + 3) <= 7u ? v30 : *(const WCHAR **)v30;
      v33 = WerReportAddFile(phReportHandle, v32, WerFileTypeOther, 0);
      if ( v33 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xD3,
          (unsigned int)"onecore\\vm\\compute\\common\\compute\\Wer.h",
          (const char *)(unsigned int)v33,
          v50);
    }
    v30 += 16;
  }
  v34 = (PCWSTR)(pwzValue + 59);
  if ( pwzValue[62] > 7u )
    v34 = *(PCWSTR *)v34;
  v35 = WerRegisterCustomMetadata(L"ContainerSkuType", v34);
  if ( v35 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xD8,
      (unsigned int)"onecore\\vm\\compute\\common\\compute\\Wer.h",
      (const char *)(unsigned int)v35,
      v50);
  v36 = (PCWSTR)(pwzValue + 63);
  if ( pwzValue[66] > 7u )
    v36 = *(PCWSTR *)v36;
  v37 = WerRegisterCustomMetadata(L"ScenarioOwner", v36);
  if ( v37 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xDC,
      (unsigned int)"onecore\\vm\\compute\\common\\compute\\Wer.h",
      (const char *)(unsigned int)v37,
      v50);
  v60 = 0;
  v38 = (__int64 *)std::make_unique<Vml::VmMachineLocalSettingsStore,,0>(v53);
  v39 = *v38;
  *v38 = 0;
  v52 = v39;
  VirtualizationSettings::VirtualizationSettings(&v60, v40, v41, &v52);
  std::unique_ptr<ComputeService::Management::ComputeSystemConfiguration>::~unique_ptr<ComputeService::Management::ComputeSystemConfiguration>(&v52);
  std::unique_ptr<ComputeService::Management::ComputeSystemConfiguration>::~unique_ptr<ComputeService::Management::ComputeSystemConfiguration>(v53);
  if ( VirtualizationSettings::GetAzureFeatureSetEnabled((VirtualizationSettings *)&v60) )
  {
    if ( pwzValue[3] <= 7u )
      v42 = (const WCHAR *)pwzValue;
    else
      v42 = (const WCHAR *)*pwzValue;
    v43 = WerReportSetParameter(phReportHandle, 5u, L"ComputeSystemId", v42);
    if ( v43 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xE8,
        (unsigned int)"onecore\\vm\\compute\\common\\compute\\Wer.h",
        (const char *)(unsigned int)v43,
        v50);
    if ( *((_BYTE *)pwzValue + 64) )
    {
      std::wstring::wstring(pwzValuea);
      v44 = (const WCHAR *)pwzValuea;
      if ( v57 > 7 )
        v44 = pwzValuea[0];
      v45 = WerReportSetParameter(phReportHandle, 6u, L"AzureContainerId", v44);
      if ( v45 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xF1,
          (unsigned int)"onecore\\vm\\compute\\common\\compute\\Wer.h",
          (const char *)(unsigned int)v45,
          v50);
      Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)pwzValuea);
    }
    v46 = Vml::FormatString(v61, L"%d", *((unsigned int *)pwzValue + 116));
    if ( *(_QWORD *)(v46 + 24) > 7u )
      v46 = *(_QWORD *)v46;
    v47 = WerReportSetParameter(phReportHandle, 7u, L"Vtl", (PCWSTR)v46);
    if ( v47 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xFA,
        (unsigned int)"onecore\\vm\\compute\\common\\compute\\Wer.h",
        (const char *)(unsigned int)v47,
        v50);
    Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)v61);
  }
  v48 = WerReportSubmit(phReportHandle, WerConsentNotAsked, 0x20u, 0);
  if ( v48 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x101,
      (unsigned int)"onecore\\vm\\compute\\common\\compute\\Wer.h",
      (const char *)(unsigned int)v48,
      v50);
  std::unique_ptr<ComputeService::Management::ComputeSystemConfiguration>::~unique_ptr<ComputeService::Management::ComputeSystemConfiguration>((char *)&v60 + 8);
  std::vector<std::wstring>::_Tidy(pwzPath);
  return wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long WerReportCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long WerReportCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phReportHandle);
}

```

## disassembly

```asm
0x140083888  mov     [rsp-8+arg_8], rbx
0x14008388d  mov     [rsp-8+arg_10], rsi
0x140083892  push    rbp
0x140083893  push    rdi
0x140083894  push    r12
0x140083896  push    r14
0x140083898  push    r15
0x14008389a  lea     rbp, [rsp-37h]
0x14008389f  sub     rsp, 0F0h
0x1400838a6  mov     rax, cs:__security_cookie
0x1400838ad  xor     rax, rsp
0x1400838b0  mov     [rbp+57h+var_30], rax
0x1400838b4  mov     rdi, rcx
0x1400838b7  xor     r14d, r14d
0x1400838ba  lea     esi, [r14+1]
0x1400838be  mov     [rbp+57h+var_B8], esi
0x1400838c1  mov     r8, rcx
0x1400838c4  lea     rdx, [rbp+57h+var_B8]
0x1400838c8  lea     rcx, [rbp+57h+var_C8]
0x1400838cc  call    _lambda_bffcbee7f2770ed84e920f222a7c63ec____lambda_bffcbee7f2770ed84e920f222a7c63ec_
0x1400838d1  cmp     [r8+10h], r14
0x1400838d5  setz    al
0x1400838d8  mov     rcx, [rbp+5Fh]; this
0x1400838dc  lea     rdx, aSystemIdOfCras; "System Id of crash report is required"
0x1400838e3  mov     qword ptr [rsp+110h+var_E8], rdx; bool
0x1400838e8  mov     [rsp+110h+var_F0], al; int
0x1400838ec  mov     ebx, 8037010Dh
0x1400838f1  mov     r9d, ebx; char *
0x1400838f4  lea     r15, aOnecoreVmCompu_104; "onecore\\vm\\compute\\common\\compute\\"...
0x1400838fb  mov     r8, r15; unsigned int
0x1400838fe  lea     edx, [rsi+49h]; void *
0x140083901  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x140083906  mov     rcx, [rbp+5Fh]; this
0x14008390a  mov     rax, [rdi+138h]
0x140083911  sub     rax, [rdi+130h]
0x140083918  sar     rax, 3
0x14008391c  lea     r12d, [r14+5]
0x140083920  cmp     rax, r12
0x140083923  jnb     short loc_140083934
0x140083925  mov     r9d, ebx; char *
0x140083928  mov     r8, r15; unsigned int
0x14008392b  lea     edx, [rsi+4Ch]; void *
0x14008392e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140083934  cmp     [rdi+1D0h], r14d
0x14008393b  jnz     short loc_140083955
0x14008393d  lea     rcx, aContainercrash; "ContainerCrashDump"
0x140083944  lea     rax, aVirtualmachine_8; "VirtualMachineCrashDump"
0x14008394b  cmp     [rbp+57h+var_B8], r14d
0x14008394f  cmovnz  rcx, rax
0x140083953  jmp     short loc_14008395C
0x140083955  lea     rcx, pwzEventType; "VirtualFirmwareCrashDump"
0x14008395c  mov     [rbp+57h+phReportHandle], r14
0x140083960  lea     r9, [rbp+57h+phReportHandle]; phReportHandle
0x140083964  xor     r8d, r8d; pReportInformation
0x140083967  mov     edx, esi; repType
0x140083969  call    cs:__imp_WerReportCreate
0x140083970  nop     dword ptr [rax+rax+00h]
0x140083975  mov     rcx, [rbp+5Fh]; this
0x140083979  test    eax, eax
0x14008397b  jns     short loc_14008398E
0x14008397d  mov     r9d, eax; char *
0x140083980  mov     r8, r15; unsigned int
0x140083983  mov     edx, 5Bh ; '['; void *
0x140083988  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14008398e  mov     rdx, [rdi+130h]
0x140083995  mov     rdx, [rdx]
0x140083998  lea     rcx, [rbp+57h+var_36]
0x14008399c  call    ??$_UIntegral_to_buff@G_K@std@@YAPEAGPEAG_K@Z; std::_UIntegral_to_buff<ushort,unsigned __int64>(ushort *,unsigned __int64)
0x1400839a1  lea     r8, [rbp+57h+var_36]
0x1400839a5  mov     rdx, rax
0x1400839a8  lea     rcx, [rbp+57h+pwzValue]
0x1400839ac  call    ??$?0PEAG$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEAG0AEBV?$allocator@G@1@@Z; std::wstring::wstring(ushort *,ushort *,std::allocator<ushort> const &)
0x1400839b1  nop
0x1400839b2  lea     r9, [rbp+57h+pwzValue]
0x1400839b6  cmp     [rbp+57h+var_90], 7
0x1400839bb  cmova   r9, [rbp+57h+pwzValue]; pwzValue
0x1400839c0  lea     r8, pwzName; "BugcheckCode"
0x1400839c7  xor     edx, edx; dwparamID
0x1400839c9  mov     rcx, [rbp+57h+phReportHandle]; hReportHandle
0x1400839cd  call    cs:__imp_WerReportSetParameter
0x1400839d4  nop     dword ptr [rax+rax+00h]
0x1400839d9  mov     rcx, [rbp+5Fh]; this
0x1400839dd  test    eax, eax
0x1400839df  jns     short loc_1400839F2
0x1400839e1  mov     r9d, eax; char *
0x1400839e4  mov     r8, r15; unsigned int
0x1400839e7  mov     edx, 61h ; 'a'; void *
0x1400839ec  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400839f2  lea     rcx, [rbp+57h+pwzValue]; this
0x1400839f6  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x1400839fb  mov     rdx, [rdi+130h]
0x140083a02  mov     rdx, [rdx+8]
0x140083a06  lea     rcx, [rbp+57h+var_36]
0x140083a0a  call    ??$_UIntegral_to_buff@G_K@std@@YAPEAGPEAG_K@Z; std::_UIntegral_to_buff<ushort,unsigned __int64>(ushort *,unsigned __int64)
0x140083a0f  lea     r8, [rbp+57h+var_36]
0x140083a13  mov     rdx, rax
0x140083a16  lea     rcx, [rbp+57h+pwzValue]
0x140083a1a  call    ??$?0PEAG$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEAG0AEBV?$allocator@G@1@@Z; std::wstring::wstring(ushort *,ushort *,std::allocator<ushort> const &)
0x140083a1f  nop
0x140083a20  lea     r9, [rbp+57h+pwzValue]
0x140083a24  cmp     [rbp+57h+var_90], 7
0x140083a29  cmova   r9, [rbp+57h+pwzValue]; pwzValue
0x140083a2e  lea     r8, aBugcheckparame_1; "BugcheckParameter1"
0x140083a35  mov     edx, esi; dwparamID
0x140083a37  mov     rcx, [rbp+57h+phReportHandle]; hReportHandle
0x140083a3b  call    cs:__imp_WerReportSetParameter
0x140083a42  nop     dword ptr [rax+rax+00h]
0x140083a47  mov     rcx, [rbp+5Fh]; this
0x140083a4b  test    eax, eax
0x140083a4d  jns     short loc_140083A60
0x140083a4f  mov     r9d, eax; char *
0x140083a52  mov     r8, r15; unsigned int
0x140083a55  mov     edx, 67h ; 'g'; void *
0x140083a5a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140083a60  lea     rcx, [rbp+57h+pwzValue]; this
0x140083a64  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x140083a69  mov     rdx, [rdi+130h]
0x140083a70  mov     rdx, [rdx+10h]
0x140083a74  lea     rcx, [rbp+57h+var_36]
0x140083a78  call    ??$_UIntegral_to_buff@G_K@std@@YAPEAGPEAG_K@Z; std::_UIntegral_to_buff<ushort,unsigned __int64>(ushort *,unsigned __int64)
0x140083a7d  lea     r8, [rbp+57h+var_36]
0x140083a81  mov     rdx, rax
0x140083a84  lea     rcx, [rbp+57h+pwzValue]
0x140083a88  call    ??$?0PEAG$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEAG0AEBV?$allocator@G@1@@Z; std::wstring::wstring(ushort *,ushort *,std::allocator<ushort> const &)
0x140083a8d  nop
0x140083a8e  lea     r9, [rbp+57h+pwzValue]
0x140083a92  cmp     [rbp+57h+var_90], 7
0x140083a97  cmova   r9, [rbp+57h+pwzValue]; pwzValue
0x140083a9c  lea     r8, aBugcheckparame_0; "BugcheckParameter2"
0x140083aa3  mov     edx, 2; dwparamID
0x140083aa8  mov     rcx, [rbp+57h+phReportHandle]; hReportHandle
0x140083aac  call    cs:__imp_WerReportSetParameter
0x140083ab3  nop     dword ptr [rax+rax+00h]
0x140083ab8  mov     rcx, [rbp+5Fh]; this
0x140083abc  test    eax, eax
0x140083abe  jns     short loc_140083AD1
0x140083ac0  mov     r9d, eax; char *
0x140083ac3  mov     r8, r15; unsigned int
0x140083ac6  mov     edx, 6Dh ; 'm'; void *
0x140083acb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140083ad1  lea     rcx, [rbp+57h+pwzValue]; this
0x140083ad5  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x140083ada  mov     rdx, [rdi+130h]
0x140083ae1  mov     rdx, [rdx+18h]
0x140083ae5  lea     rcx, [rbp+57h+var_36]
0x140083ae9  call    ??$_UIntegral_to_buff@G_K@std@@YAPEAGPEAG_K@Z; std::_UIntegral_to_buff<ushort,unsigned __int64>(ushort *,unsigned __int64)
0x140083aee  lea     r8, [rbp+57h+var_36]
0x140083af2  mov     rdx, rax
0x140083af5  lea     rcx, [rbp+57h+pwzValue]
0x140083af9  call    ??$?0PEAG$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEAG0AEBV?$allocator@G@1@@Z; std::wstring::wstring(ushort *,ushort *,std::allocator<ushort> const &)
0x140083afe  nop
0x140083aff  lea     r9, [rbp+57h+pwzValue]
0x140083b03  cmp     [rbp+57h+var_90], 7
0x140083b08  cmova   r9, [rbp+57h+pwzValue]; pwzValue
0x140083b0d  lea     r8, aBugcheckparame_2; "BugcheckParameter3"
0x140083b14  mov     edx, 3; dwparamID
0x140083b19  mov     rcx, [rbp+57h+phReportHandle]; hReportHandle
0x140083b1d  call    cs:__imp_WerReportSetParameter
0x140083b24  nop     dword ptr [rax+rax+00h]
0x140083b29  mov     rcx, [rbp+5Fh]; this
0x140083b2d  test    eax, eax
0x140083b2f  jns     short loc_140083B42
0x140083b31  mov     r9d, eax; char *
0x140083b34  mov     r8, r15; unsigned int
0x140083b37  mov     edx, 73h ; 's'; void *
0x140083b3c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140083b42  lea     rcx, [rbp+57h+pwzValue]; this
0x140083b46  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x140083b4b  mov     rdx, [rdi+130h]
0x140083b52  mov     rdx, [rdx+20h]
0x140083b56  lea     rcx, [rbp+57h+var_36]
0x140083b5a  call    ??$_UIntegral_to_buff@G_K@std@@YAPEAGPEAG_K@Z; std::_UIntegral_to_buff<ushort,unsigned __int64>(ushort *,unsigned __int64)
0x140083b5f  lea     r8, [rbp+57h+var_36]
0x140083b63  mov     rdx, rax
0x140083b66  lea     rcx, [rbp+57h+pwzValue]
0x140083b6a  call    ??$?0PEAG$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEAG0AEBV?$allocator@G@1@@Z; std::wstring::wstring(ushort *,ushort *,std::allocator<ushort> const &)
0x140083b6f  nop
0x140083b70  lea     r9, [rbp+57h+pwzValue]
0x140083b74  cmp     [rbp+57h+var_90], 7
0x140083b79  cmova   r9, [rbp+57h+pwzValue]; pwzValue
0x140083b7e  lea     r8, aBugcheckparame; "BugcheckParameter4"
0x140083b85  mov     edx, 4; dwparamID
0x140083b8a  mov     rcx, [rbp+57h+phReportHandle]; hReportHandle
0x140083b8e  call    cs:__imp_WerReportSetParameter
0x140083b95  nop     dword ptr [rax+rax+00h]
0x140083b9a  mov     rcx, [rbp+5Fh]; this
0x140083b9e  test    eax, eax
0x140083ba0  jns     short loc_140083BB3
0x140083ba2  mov     r9d, eax; char *
0x140083ba5  mov     r8, r15; unsigned int
0x140083ba8  mov     edx, 79h ; 'y'; void *
0x140083bad  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140083bb3  lea     rcx, [rbp+57h+pwzValue]; this
0x140083bb7  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x140083bbc  xorps   xmm0, xmm0
0x140083bbf  xor     eax, eax
0x140083bc1  movups  xmmword ptr [rbp+57h+pwzPath], xmm0
0x140083bc5  mov     [rbp+57h+var_78], rax
0x140083bc9  lea     rcx, [rbp+57h+pwzPath]
0x140083bcd  call    ??0?$vector@UVpSubnodeMetadata@VirtualMachine@Config@@V?$allocator@UVpSubnodeMetadata@VirtualMachine@Config@@@std@@@std@@QEAA@XZ; std::vector<Config::VirtualMachine::VpSubnodeMetadata>::vector<Config::VirtualMachine::VpSubnodeMetadata>(void)
0x140083bd2  nop
0x140083bd3  cmp     [rdi+0A0h], r14b
0x140083bda  jz      loc_140083D4B
0x140083be0  mov     ebx, [rdi+94h]
0x140083be6  mov     ecx, [rdi+98h]
0x140083bec  call    ??$EnumToString@W4WindowsCrashPhase@System@Responses@Schema@@$0A@@Marshal@@YAPEBGW4WindowsCrashPhase@System@Responses@Schema@@@Z; Marshal::EnumToString<Schema::Responses::System::WindowsCrashPhase,0>(Schema::Responses::System::WindowsCrashPhase)
0x140083bf1  mov     rdx, rax
0x140083bf4  lea     rcx, [rbp+57h+pwzValue]
0x140083bf8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x140083bfd  mov     r8d, ebx
0x140083c00  lea     rdx, [rbp+57h+pwzValue]
0x140083c04  lea     rcx, [rbp+57h+var_C8]
0x140083c08  call    _lambda_1076b0aedadf1a66c6313478c40a3126___operator__
0x140083c0d  lea     rcx, [rbp+57h+pwzValue]; this
0x140083c11  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x140083c16  mov     al, [rdi+0A0h]
0x140083c1c  test    al, al
0x140083c1e  jnz     short loc_140083C25
0x140083c20  mov     rcx, r12
0x140083c23  int     29h; Win8: RtlFailFast(ecx)
0x140083c25  mov     rcx, [rbp+5Fh]; this
0x140083c29  cmp     [rdi+98h], r12d
0x140083c30  jz      short loc_140083C46
0x140083c32  mov     r9d, 80004004h; char *
0x140083c38  mov     r8, r15; unsigned int
0x140083c3b  mov     edx, 8Ch; void *
0x140083c40  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140083c46  test    al, al
0x140083c48  jnz     short loc_140083C4F
0x140083c4a  mov     rcx, r12
0x140083c4d  int     29h; Win8: RtlFailFast(ecx)
0x140083c4f  lea     rdx, [rdi+58h]
0x140083c53  lea     rcx, [rbp+57h+pwzPath]
0x140083c57  call    ??$_Emplace_one_at_back@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@AEBV21@@Z; std::vector<std::wstring>::_Emplace_one_at_back<std::wstring const &>(std::wstring const &)
0x140083c5c  cmp     [rdi+190h], r14b
0x140083c63  jz      short loc_140083C7E
0x140083c65  cmp     [rdi+188h], r14d
0x140083c6c  jl      short loc_140083C7E
0x140083c6e  lea     rdx, [rdi+168h]
0x140083c75  lea     rcx, [rbp+57h+pwzPath]
0x140083c79  call    ??$_Emplace_one_at_back@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@AEBV21@@Z; std::vector<std::wstring>::_Emplace_one_at_back<std::wstring const &>(std::wstring const &)
0x140083c7e  cmp     [rdi+1C0h], r14b
0x140083c85  jz      short loc_140083CA0
0x140083c87  cmp     [rdi+1B8h], r14d
0x140083c8e  jl      short loc_140083CA0
0x140083c90  lea     rdx, [rdi+198h]
0x140083c97  lea     rcx, [rbp+57h+pwzPath]
0x140083c9b  call    ??$_Emplace_one_at_back@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@AEBV21@@Z; std::vector<std::wstring>::_Emplace_one_at_back<std::wstring const &>(std::wstring const &)
0x140083ca0  mov     al, [rdi+0A0h]
0x140083ca6  test    al, al
0x140083ca8  jnz     short loc_140083CAF
0x140083caa  mov     rcx, r12
0x140083cad  int     29h; Win8: RtlFailFast(ecx)
0x140083caf  mov     r9d, [rdi+88h]
0x140083cb6  test    al, al
0x140083cb8  jnz     short loc_140083CBF
0x140083cba  mov     rcx, r12
0x140083cbd  int     29h; Win8: RtlFailFast(ecx)
0x140083cbf  mov     r8d, [rdi+84h]
0x140083cc6  test    al, al
0x140083cc8  jnz     short loc_140083CCF
0x140083cca  mov     rcx, r12
0x140083ccd  int     29h; Win8: RtlFailFast(ecx)
0x140083ccf  mov     edx, [rdi+80h]
0x140083cd5  test    al, al
0x140083cd7  jnz     short loc_140083CE4
0x140083cd9  mov     rcx, r12
0x140083cdc  int     29h; Win8: RtlFailFast(ecx)
0x140083cde  test    al, al
0x140083ce0  jnz     short loc_140083CE4
0x140083ce2  int     29h; Win8: RtlFailFast(ecx)
0x140083ce4  mov     [rsp+110h+var_E0], r9d
0x140083ce9  mov     dword ptr [rsp+110h+var_E8], r8d
0x140083cee  mov     dword ptr [rsp+110h+var_F0], edx; int
0x140083cf2  mov     r9d, [rdi+7Ch]
0x140083cf6  mov     r8d, [rdi+78h]
0x140083cfa  lea     rdx, aDDDSpDD; "%d.%d.%d SP %d.%d"
0x140083d01  lea     rcx, [rbp+57h+var_60]
0x140083d05  call    ?FormatString@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGZZ; Vml::FormatString(ushort const *,...)
0x140083d0a  cmp     qword ptr [rax+18h], 7
0x140083d0f  jbe     short loc_140083D14
0x140083d11  mov     rax, [rax]
0x140083d14  mov     rdx, rax; value
0x140083d17  lea     rcx, key; "GuestOsVersion"
0x140083d1e  call    cs:__imp_WerRegisterCustomMetadata
0x140083d25  nop     dword ptr [rax+rax+00h]
0x140083d2a  mov     rcx, [rbp+5Fh]; this
0x140083d2e  test    eax, eax
0x140083d30  jns     loc_140083EB9
0x140083d36  mov     r9d, eax; char *
0x140083d39  mov     r8, r15; unsigned int
0x140083d3c  mov     edx, 0A4h; void *
0x140083d41  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140083d46  jmp     loc_140083EB9
0x140083d4b  cmp     [rdi+0F8h], r14b
0x140083d52  jz      loc_140083E95
0x140083d58  mov     ecx, [rdi+0F4h]
0x140083d5e  cmp     ecx, 4
0x140083d61  ja      loc_140083E90
0x140083d67  mov     ebx, [rdi+0F0h]
  ... truncated ...
```
