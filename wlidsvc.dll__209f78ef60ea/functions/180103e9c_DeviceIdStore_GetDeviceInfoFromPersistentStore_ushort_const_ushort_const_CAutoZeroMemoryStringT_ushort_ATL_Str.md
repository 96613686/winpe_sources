# DeviceIdStore::GetDeviceInfoFromPersistentStore(ushort const *,ushort const *,CAutoZeroMemoryStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CTime &,ATL::CTime &,ATL::CTime &,TpmKeyStateClient &,TpmKeyStateServer &,ulong &,long &,ulong &)

- ea: `0x180103e9c`
- end: `0x180104e98`
- name: `?GetDeviceInfoFromPersistentStore@DeviceIdStore@@SAJPEBG0AEAV?$CAutoZeroMemoryStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@@AEAVCTime@ATL@@22AEAW4TpmKeyStateClient@@AEAW4TpmKeyStateServer@@AEAKAEAJ5@Z`
- size: `4092`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, __int64, __int64, __int64, __int64, BSTR bstrString, __int64)`
- caller_count: `1`
- callee_count: `27`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180071c80`

## callees

- `0x180003994`
- `0x18000c050`
- `0x18000ed04`
- `0x180012f64`
- `0x180013fb4`
- `0x1800151c4`
- `0x180019690`
- `0x180019780`
- `0x18001a530`
- `0x18001a9c0`
- `0x18001cf20`
- `0x180021b28`
- `0x180021bbc`
- `0x1800396e8`
- `0x180039d60`
- `0x180039ee8`
- `0x18003c814`
- `0x1800406a8`
- `0x18005538c`
- `0x180087a84`
- `0x18008916c`
- `0x180089264`
- `0x1801033c0`
- `0x180103e9c`
- `0x180104ea0`
- `0x1801066ac`
- `0x180128010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1801046df`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180104af7`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1801046df`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180104af7`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180104389`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1801043d7`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180104c9a`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180104cb8`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180104389`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1801043d7`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180104c9a`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180104cb8`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x180104139`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x1801041ae`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x180104307`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x18010441c`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x180104460`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x1801044d7`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x180104bb5`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x180104c07`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x180104c52`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x180104cd6`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x180104cf8`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x180104d46`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x180104139`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x1801041ae`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x180104307`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x18010441c`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x180104460`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x1801044d7`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x180104bb5`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x180104c07`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x180104c52`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x180104cd6`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x180104cf8`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x180104d46`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180104146`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1801041bb`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180104314`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180104468`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180104bc2`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180104c14`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180104c5f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180104d00`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180104146`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1801041bb`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180104314`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180104468`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180104bc2`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180104c14`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180104c5f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180104d00`
- `OLEAUT32!__imp_SysFreeString` at `0x180104272`
- `OLEAUT32!__imp_SysFreeString` at `0x180104565`
- `OLEAUT32!__imp_SysFreeString` at `0x1801047ee`
- `OLEAUT32!__imp_SysFreeString` at `0x180104272`
- `OLEAUT32!__imp_SysFreeString` at `0x180104565`
- `OLEAUT32!__imp_SysFreeString` at `0x1801047ee`
- `OLEAUT32!__imp_SysStringLen` at `0x180104125`
- `OLEAUT32!__imp_SysStringLen` at `0x1801041a0`
- `OLEAUT32!__imp_SysStringLen` at `0x1801042f9`
- `OLEAUT32!__imp_SysStringLen` at `0x180104378`
- `OLEAUT32!__imp_SysStringLen` at `0x1801043c6`
- `OLEAUT32!__imp_SysStringLen` at `0x18010440e`
- `OLEAUT32!__imp_SysStringLen` at `0x180104452`
- `OLEAUT32!__imp_SysStringLen` at `0x1801044c9`
- `OLEAUT32!__imp_SysStringLen` at `0x18010488e`
- `OLEAUT32!__imp_SysStringLen` at `0x180104125`
- `OLEAUT32!__imp_SysStringLen` at `0x1801041a0`
- `OLEAUT32!__imp_SysStringLen` at `0x1801042f9`
- `OLEAUT32!__imp_SysStringLen` at `0x180104378`
- `OLEAUT32!__imp_SysStringLen` at `0x1801043c6`
- `OLEAUT32!__imp_SysStringLen` at `0x18010440e`
- `OLEAUT32!__imp_SysStringLen` at `0x180104452`
- `OLEAUT32!__imp_SysStringLen` at `0x1801044c9`
- `OLEAUT32!__imp_SysStringLen` at `0x18010488e`
- `OLEAUT32!__imp_VariantInit` at `0x180103f23`
- `OLEAUT32!__imp_VariantInit` at `0x180103f2e`
- `OLEAUT32!__imp_VariantInit` at `0x180103f39`
- `OLEAUT32!__imp_VariantInit` at `0x180103f44`
- `OLEAUT32!__imp_VariantInit` at `0x180103f52`
- `OLEAUT32!__imp_VariantInit` at `0x180103f60`
- `OLEAUT32!__imp_VariantInit` at `0x180103f6b`
- `OLEAUT32!__imp_VariantInit` at `0x180103f76`
- `OLEAUT32!__imp_VariantInit` at `0x180103f81`
- `OLEAUT32!__imp_VariantInit` at `0x180103f23`
- `OLEAUT32!__imp_VariantInit` at `0x180103f2e`
- `OLEAUT32!__imp_VariantInit` at `0x180103f39`
- `OLEAUT32!__imp_VariantInit` at `0x180103f44`
- `OLEAUT32!__imp_VariantInit` at `0x180103f52`
- `OLEAUT32!__imp_VariantInit` at `0x180103f60`
- `OLEAUT32!__imp_VariantInit` at `0x180103f6b`
- `OLEAUT32!__imp_VariantInit` at `0x180103f76`
- `OLEAUT32!__imp_VariantInit` at `0x180103f81`
- `OLEAUT32!__imp_VariantClear` at `0x180104763`
- `OLEAUT32!__imp_VariantClear` at `0x18010476e`
- `OLEAUT32!__imp_VariantClear` at `0x180104779`
- `OLEAUT32!__imp_VariantClear` at `0x180104787`
- `OLEAUT32!__imp_VariantClear` at `0x180104795`
- `OLEAUT32!__imp_VariantClear` at `0x1801047a0`
- `OLEAUT32!__imp_VariantClear` at `0x1801047ab`
- `OLEAUT32!__imp_VariantClear` at `0x1801047b6`
- `OLEAUT32!__imp_VariantClear` at `0x1801047c4`
- `OLEAUT32!__imp_VariantClear` at `0x180104763`
- `OLEAUT32!__imp_VariantClear` at `0x18010476e`
- `OLEAUT32!__imp_VariantClear` at `0x180104779`
- `OLEAUT32!__imp_VariantClear` at `0x180104787`
- `OLEAUT32!__imp_VariantClear` at `0x180104795`
- `OLEAUT32!__imp_VariantClear` at `0x1801047a0`
- `OLEAUT32!__imp_VariantClear` at `0x1801047ab`
- `OLEAUT32!__imp_VariantClear` at `0x1801047b6`
- `OLEAUT32!__imp_VariantClear` at `0x1801047c4`

## string_xrefs

- `0x180104003`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\deviceidstore.cpp`
- `0x1801040b6`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\deviceidstore.cpp`
- `0x180104168`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\deviceidstore.cpp`
- `0x1801041dd`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\deviceidstore.cpp`
- `0x180104296`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\deviceidstore.cpp`
- `0x180104336`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\deviceidstore.cpp`
- `0x180104489`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\deviceidstore.cpp`
- `0x18010458b`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\deviceidstore.cpp`
- `0x1801045c3`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\deviceidstore.cpp`
- `0x18010464a`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\deviceidstore.cpp`
- `0x180104876`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\deviceidstore.cpp`
- `0x18010490f`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\deviceidstore.cpp`
- `0x18010493c`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\deviceidstore.cpp`
- `0x180104b29`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\deviceidstore.cpp`
- `0x180104be0`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\deviceidstore.cpp`
- `0x180104c32`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\deviceidstore.cpp`
- `0x180104c7d`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\deviceidstore.cpp`
- `0x180104d1d`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\deviceidstore.cpp`
- `0x180104ddb`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\deviceidstore.cpp`
- `0x180104e7f`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\deviceidstore.cpp`
- `0x18010443b`: `LicenseInstallError`
- `0x18010447c`: `Invalid LicenseInstallError %ls`
- `0x180104d10`: `Invalid LicenseInstallError %ls`
- `0x180104b0b`: `hr = PPCRL_E_DEVICEID_XMLLITE_PARSE_ERROR_NAME`
- `0x1801048f3`: `hr = DecryptPasswordAndRewriteIfNeeded(wstrDeviceIDKey, wszUserName, bstrEncryptedPassword, passwordVersion.bstrVal, ctLastUpdatedTime, ctDAInvalidationTime, wstrPwd)`
- `0x180104d75`: `hr = PPCRL_E_DEVICEID_XMLLITE_PARSE_ERROR_PASSWORD`
- `0x180104c25`: `Invalid Last Updated Time set = %ls, errno = %d`
- `0x180104dbf`: `hr = DecryptPasswordAndRewriteIfNeeded(wstrDeviceIDKey, wstrUsername, wstrPassword, passwordVersion, ctLastUpdatedTime, ctDAInvalidationTime, wstrPwd)`

## pseudocode

```c
// Hidden C++ exception states: #wind=34
__int64 __fastcall DeviceIdStore::GetDeviceInfoFromPersistentStore(
        unsigned __int16 *a1,
        unsigned int *a2,
        __int64 a3,
        _QWORD *a4,
        _QWORD *a5,
        _QWORD *a6,
        unsigned int *a7,
        unsigned int *a8,
        int *a9,
        BSTR bstrString,
        int *a11)
{
  _QWORD *v11; // r14
  unsigned __int16 *v13; // rbx
  int v14; // r15d
  unsigned __int8 v15; // dl
  PPTraceStatus *v16; // rcx
  bool v17; // zf
  char v18; // cl
  char v19; // al
  const unsigned __int16 *String; // rax
  _QWORD *v21; // rsi
  BSTR v22; // r13
  int v23; // eax
  __int64 v24; // rdi
  int v25; // eax
  int v26; // eax
  __int64 v27; // rbx
  int v28; // eax
  __int64 v29; // rbx
  __int64 v30; // rsi
  __int64 (__fastcall *v31)(__int64, _QWORD, __int64 *); // r14
  ATL::CComBSTR *v32; // rax
  int v33; // eax
  __int64 v34; // rbx
  unsigned int v35; // eax
  unsigned int v36; // eax
  int v37; // eax
  int v38; // ebx
  int v39; // eax
  __int64 (__fastcall *v40)(__int64, _QWORD, __int64 *); // rsi
  unsigned __int16 *v41; // rbx
  ATL::CComBSTR *v42; // rax
  unsigned __int16 *v43; // rdi
  int v44; // eax
  unsigned int v45; // ebx
  int v46; // eax
  __int64 v47; // r8
  __int64 v48; // r9
  int v50; // eax
  int v51; // eax
  int DeviceInfoUsingXmlLite; // eax
  int v53; // r9d
  const char *v54; // rax
  unsigned int v55; // r8d
  __int64 v56; // rbx
  int v57; // eax
  __int64 v58; // rdi
  __int64 v59; // rbx
  int v60; // eax
  __int64 v61; // rdi
  __int64 v62; // rbx
  int v63; // eax
  __int64 v64; // rdi
  unsigned int v65; // eax
  unsigned int v66; // eax
  int v67; // eax
  BSTR v68; // rbx
  int v69; // edi
  int v70; // eax
  int v71; // eax
  char *v72; // [rsp+28h] [rbp-E0h]
  char *v73; // [rsp+28h] [rbp-E0h]
  __int64 v74; // [rsp+30h] [rbp-D8h]
  __int64 v75; // [rsp+30h] [rbp-D8h]
  __int64 v76; // [rsp+30h] [rbp-D8h]
  __int64 v77; // [rsp+30h] [rbp-D8h]
  __int64 v78; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v79; // [rsp+70h] [rbp-98h] BYREF
  __int64 v80; // [rsp+78h] [rbp-90h] BYREF
  __int64 v81; // [rsp+80h] [rbp-88h] BYREF
  __int64 v82; // [rsp+88h] [rbp-80h] BYREF
  __int64 v83; // [rsp+90h] [rbp-78h] BYREF
  __int64 v84; // [rsp+98h] [rbp-70h] BYREF
  __int64 v85; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v86; // [rsp+A8h] [rbp-60h] BYREF
  unsigned __int16 *v87; // [rsp+B0h] [rbp-58h] BYREF
  BSTR pbstr; // [rsp+B8h] [rbp-50h] BYREF
  __int64 v89; // [rsp+C0h] [rbp-48h] BYREF
  __int64 v90; // [rsp+C8h] [rbp-40h] BYREF
  __int64 v91; // [rsp+D0h] [rbp-38h] BYREF
  __int64 v92; // [rsp+D8h] [rbp-30h] BYREF
  __int64 v93; // [rsp+E0h] [rbp-28h] BYREF
  __int64 v94; // [rsp+E8h] [rbp-20h] BYREF
  __int64 v95; // [rsp+F0h] [rbp-18h] BYREF
  VARIANTARG v96; // [rsp+F8h] [rbp-10h] BYREF
  VARIANTARG v97; // [rsp+110h] [rbp+8h] BYREF
  VARIANTARG v98; // [rsp+128h] [rbp+20h] BYREF
  VARIANTARG v99; // [rsp+140h] [rbp+38h] BYREF
  VARIANTARG v100; // [rsp+158h] [rbp+50h] BYREF
  VARIANTARG v101; // [rsp+170h] [rbp+68h] BYREF
  VARIANTARG v102; // [rsp+188h] [rbp+80h] BYREF
  VARIANTARG v103; // [rsp+1A0h] [rbp+98h] BYREF
  _QWORD v104[3]; // [rsp+1B8h] [rbp+B0h] BYREF
  char v105; // [rsp+1D0h] [rbp+C8h]
  VARIANTARG pvarg; // [rsp+1D8h] [rbp+D0h] BYREF
  _BYTE v107[16]; // [rsp+1F0h] [rbp+E8h] BYREF
  const char *v108[13]; // [rsp+200h] [rbp+F8h] BYREF
  unsigned __int8 v110; // [rsp+280h] [rbp+178h]
  _QWORD *v112; // [rsp+290h] [rbp+188h] BYREF

  v112 = a4;
  v11 = a4;
  v13 = a1;
  v78 = 0;
  v14 = 0;
  v94 = 0;
  v91 = 0;
  v90 = 0;
  v93 = 0;
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v89);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v95);
  pbstr = 0;
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v87);
  v79 = 0;
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v92);
  VariantInit(&pvarg);
  VariantInit(&v99);
  VariantInit(&v98);
  VariantInit(&v97);
  VariantInit(&v103);
  VariantInit(&v102);
  VariantInit(&v101);
  VariantInit(&v96);
  VariantInit(&v100);
  v110 = 0;
  if ( !PPTraceShouldRedact() || (LOBYTE(v16) = 1, v17 = !PPTraceStatus::TraceOnFlag(v16, v15), v19 = v18, v17) )
    v19 = 0;
  v104[1] = a2;
  v104[2] = 0;
  v105 = v19;
  v104[0] = &PPRedactedStringW::`vftable';
  String = PPRedactedStringW::GetString((PPRedactedStringW *)v104);
  CTraceFuncW<long>::CTraceFuncW<long>(
    v108,
    "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\deviceidstore.cpp",
    1320,
    (const char *)&v78,
    "DeviceIdStore::GetDeviceInfoFromPersistentStore",
    L"wstrDeviceIDKey=%ls,wszUserName=%ls",
    v13,
    String);
  PPRedactedStringW::~PPRedactedStringW((PPRedactedStringW *)v104);
  CComCritSecLockWTry<CComAutoCriticalSectionWTry>::CComCritSecLockWTry<CComAutoCriticalSectionWTry>(
    (__int64)v107,
    (struct _RTL_CRITICAL_SECTION *)qword_1801C43A8,
    1);
  *a6 = 0;
  *v11 = 0;
  v21 = a5;
  *a5 = 0;
  *a7 = 0;
  *a8 = 0;
  *a9 = 0;
  v22 = bstrString;
  *(_DWORD *)bstrString = 0;
  if ( !a2 || !*(_WORD *)a2 )
  {
    LODWORD(v78) = -2147024809;
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\deviceidstore.cpp",
      "DeviceIdStore::GetDeviceInfoFromPersistentStore",
      0x538u,
      -2147024809,
      "hr = E_INVALIDARG");
    v43 = a1;
    goto LABEL_53;
  }
  v23 = DeviceIdStore::LoadPersistedDOM(v13, a2, 0, &v94);
  LODWORD(v78) = v23;
  if ( v23 < 0 )
  {
    LODWORD(v72) = v23;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\deviceidstore.cpp",
      0x53Eu,
      L"::LoadPersistedDOM failed with hr = %x",
      v72);
    goto LABEL_70;
  }
  v24 = v94;
  v25 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v94 + 360LL))(v94, &v91);
  LODWORD(v78) = v25;
  if ( v25 < 0 || !v91 )
  {
    LODWORD(v72) = v25;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\deviceidstore.cpp",
      0x546u,
      L"::GetDocumentElement failed with hr = %x",
      v72);
LABEL_70:
    if ( DeviceIdStore::IsXmlLiteSupported() )
    {
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v86);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v85);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v84);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v83);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v82);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v81);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v80);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&bstrString);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v112);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        (__int64 *)&a5,
        a2);
      DeviceInfoUsingXmlLite = DeviceIdStore::GetDeviceInfoUsingXmlLite(
                                 (_DWORD)v13,
                                 (unsigned int)&a5,
                                 (unsigned int)&v86,
                                 (unsigned int)&v92,
                                 (__int64)&v84,
                                 (__int64)&v83,
                                 (__int64)&v85,
                                 (__int64)&v82,
                                 (__int64)&v81,
                                 (__int64)&v80,
                                 (__int64)&bstrString,
                                 (__int64)&v112);
      LODWORD(v78) = DeviceInfoUsingXmlLite;
      v110 = 1;
      if ( DeviceInfoUsingXmlLite < 0 )
      {
        if ( (DeviceInfoUsingXmlLite & 0x1FFF0000) == 0xC0000 )
        {
          LODWORD(v78) = -2147187449;
          v14 = DeviceInfoUsingXmlLite;
        }
        else
        {
          v14 = HIDWORD(v78);
        }
        ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&a5);
        ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v112);
        ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&bstrString);
        ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v80);
        ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v81);
        ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v82);
        ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v83);
        ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v84);
        ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v85);
        ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v86);
        v45 = v78;
        v43 = a1;
LABEL_56:
        if ( !v45 )
          goto LABEL_61;
        goto LABEL_57;
      }
      if ( (unsigned int)_o__wcsicmp(a5, a2) )
      {
        v53 = -2147187448;
        v54 = "hr = PPCRL_E_DEVICEID_XMLLITE_PARSE_ERROR_NAME";
        v55 = 1567;
      }
      else
      {
        v56 = v85;
        if ( *(_DWORD *)(v85 - 16) )
        {
          v57 = _o__wtol(v85);
          v58 = v57;
          if ( !v57 )
          {
            LODWORD(v77) = *(_DWORD *)_o__errno();
            TracePrintW(
              2u,
              "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\deviceidstore.cpp",
              0x627u,
              L"Invalid Hwd Bound Time set = %ls, errno = %d",
              v56,
              v77);
          }
          *a6 = v58;
        }
        v59 = v84;
        if ( *(_DWORD *)(v84 - 16) )
        {
          v60 = _o__wtol(v84);
          v61 = v60;
          if ( !v60 )
          {
            LODWORD(v77) = *(_DWORD *)_o__errno();
            TracePrintW(
              2u,
              "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\deviceidstore.cpp",
              0x632u,
              L"Invalid Last Updated Time set = %ls, errno = %d",
              v59,
              v77);
          }
          *v11 = v61;
        }
        v62 = v83;
        if ( *(_DWORD *)(v83 - 16) )
        {
          v63 = _o__wtol(v83);
          v64 = v63;
          if ( !v63 )
          {
            LODWORD(v77) = *(_DWORD *)_o__errno();
            TracePrintW(
              2u,
              "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\deviceidstore.cpp",
              0x63Du,
              L"Invalid DA Invalidation Time set = %ls, errno = %d",
              v62,
              v77);
          }
          *v21 = v64;
        }
        if ( *(_DWORD *)(v82 - 16) )
        {
          v65 = _o__wtoi(v82);
          if ( v65 <= 7 )
            *a7 = v65;
        }
        if ( *(_DWORD *)(v81 - 16) )
        {
          v66 = _o__wtoi(v81);
          if ( v66 <= 6 )
            *a8 = v66;
        }
        if ( *(_DWORD *)(v80 - 16) )
        {
          v67 = _o__wtol(v80);
          if ( v67 > 0 )
            *a9 = v67;
        }
        v68 = bstrString;
        if ( *((_DWORD *)bstrString - 4) )
        {
          v69 = _o__wtol(bstrString);
          if ( *(_DWORD *)_o__errno() == 34 )
          {
            TracePrintW(
              2u,
              "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\deviceidstore.cpp",
              0x663u,
              L"Invalid LicenseInstallError %ls",
              v68);
            *(_DWORD *)v22 = 0;
          }
          else
          {
            *(_DWORD *)v22 = v69;
          }
        }
        if ( *((_DWORD *)v112 - 4) )
        {
          v70 = _o__wtol(v112);
          if ( v70 > 0 )
            *a11 = v70;
        }
        if ( *a6 || *(_DWORD *)(v92 - 16) )
        {
          v43 = a1;
          v71 = DecryptPasswordAndRewriteIfNeeded(a1, a5, v92, v86, v11, v21, a3);
          LODWORD(v78) = v71;
          if ( v71 < 0 )
            Telemetry::IfFailExit(
              "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\deviceidstore.cpp",
              "DeviceIdStore::GetDeviceInfoFromPersistentStore",
              0x67Au,
              v71,
              "hr = DecryptPasswordAndRewriteIfNeeded(wstrDeviceIDKey, wstrUsername, wstrPassword, passwordVersion, ctLas"
              "tUpdatedTime, ctDAInvalidationTime, wstrPwd)");
          ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&a5);
          ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v112);
          ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&bstrString);
          ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v80);
          ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v81);
          ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v82);
          ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v83);
          ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v84);
          ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v85);
          ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v86);
          goto LABEL_52;
        }
        v53 = -2147187447;
        v54 = "hr = PPCRL_E_DEVICEID_XMLLITE_PARSE_ERROR_PASSWORD";
        v55 = 1655;
      }
      LODWORD(v78) = v53;
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\deviceidstore.cpp",
        "DeviceIdStore::GetDeviceInfoFromPersistentStore",
        v55,
        v53,
        v54);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&a5);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v112);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&bstrString);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v80);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v81);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v82);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v83);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v84);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v85);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v86);
    }
    goto LABEL_51;
  }
  LODWORD(v78) = (*(__int64 (__fastcall **)(__int64, BSTR, VARIANTARG *))(*(_QWORD *)v91 + 352LL))(
                   v91,
                   g_bstrDeviceLastUpdatedTime,
                   &v98);
  if ( SysStringLen(v98.bstrVal) )
  {
    v26 = _o__wtol(v98.llVal);
    v27 = v26;
    if ( !v26 )
    {
      LODWORD(v74) = *(_DWORD *)_o__errno();
      TracePrintW(
        2u,
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\deviceidstore.cpp",
        0x550u,
        L"Invalid Last Bound Time set = %ls, errno = %d",
        v98.llVal,
        v74);
    }
    *v11 = v27;
  }
  LODWORD(v78) = (*(__int64 (__fastcall **)(__int64, BSTR, VARIANTARG *))(*(_QWORD *)v91 + 352LL))(
                   v91,
                   g_bstrDeviceDAInvalidationTime,
                   &v97);
  if ( SysStringLen(v97.bstrVal) )
  {
    v28 = _o__wtol(v97.llVal);
    v29 = v28;
    if ( !v28 )
    {
      LODWORD(v74) = *(_DWORD *)_o__errno();
      TracePrintW(
        2u,
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\deviceidstore.cpp",
        0x55Du,
        L"Invalid DA Invalidation Time set = %ls, errno = %d",
        v97.llVal,
        v74);
    }
    *v21 = v29;
  }
  SanitizeAndEscapeXML(a2, &v89);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::MakeUpper(&v89);
  v30 = v89;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
    &v87,
    L"//%s[@%s='%s']/%s",
    g_bstrDeviceUser,
    g_bstrDeviceUsername,
    v89,
    g_bstrDeviceHardwareInfo);
  v31 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v24 + 296LL);
  v13 = v87;
  v32 = ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, v87);
  LODWORD(v78) = v31(v24, *(_QWORD *)v32, &v93);
  SysFreeString(bstrString);
  if ( (int)v78 < 0 )
  {
    LODWORD(v75) = v78;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\deviceidstore.cpp",
      0x573u,
      L"selectSingleNode for %ls failed with hr = %x",
      v13,
      v75);
    v21 = a5;
    v11 = v112;
    LODWORD(v13) = (_DWORD)a1;
    goto LABEL_70;
  }
  ATL::CComQIPtr<IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>::operator=(&v79, v93);
  if ( v79 )
  {
    (*(void (__fastcall **)(__int64, BSTR, VARIANTARG *))(*(_QWORD *)v79 + 352LL))(
      v79,
      g_bstrDeviceHardwareBoundTime,
      &v99);
    if ( SysStringLen(v99.bstrVal) )
    {
      v33 = _o__wtol(v99.llVal);
      v34 = v33;
      if ( !v33 )
      {
        LODWORD(v75) = *(_DWORD *)_o__errno();
        TracePrintW(
          2u,
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\deviceidstore.cpp",
          0x581u,
          L"Invalid Hwd Bound Time set = %ls, errno = %d",
          v99.llVal,
          v75);
      }
      *a6 = v34;
    }
    (*(void (__fastcall **)(__int64, BSTR, VARIANTARG *))(*(_QWORD *)v79 + 352LL))(
      v79,
      g_bstrDeviceTpmKeyStateClient,
      &v103);
    if ( SysStringLen(v103.bstrVal) )
    {
      v35 = _o__wtoi(v103.llVal);
      if ( v35 <= 7 )
        *a7 = v35;
    }
    (*(void (__fastcall **)(__int64, BSTR, VARIANTARG *))(*(_QWORD *)v79 + 352LL))(
      v79,
      g_bstrDeviceTpmKeyStateServer,
      &v102);
    if ( SysStringLen(v102.bstrVal) )
    {
      v36 = _o__wtoi(v102.llVal);
      if ( v36 <= 6 )
        *a8 = v36;
    }
    (*(void (__fastcall **)(__int64, const wchar_t *, VARIANTARG *))(*(_QWORD *)v79 + 352LL))(
      v79,
      L"LicenseKeySequence",
      &v101);
    if ( SysStringLen(v101.bstrVal) )
    {
      v37 = _o__wtol(v101.llVal);
      if ( v37 > 0 )
        *a9 = v37;
    }
    (*(void (__fastcall **)(__int64, const wchar_t *, VARIANTARG *))(*(_QWORD *)v79 + 352LL))(
      v79,
      L"LicenseInstallError",
      &v96);
    if ( SysStringLen(v96.bstrVal) )
    {
      v38 = _o__wtol(v96.llVal);
      if ( *(_DWORD *)_o__errno() == 34 )
      {
        TracePrintW(
          2u,
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\deviceidstore.cpp",
          0x5AEu,
          L"Invalid LicenseInstallError %ls",
          v96.llVal);
        *(_DWORD *)v22 = 0;
      }
      else
      {
        *(_DWORD *)v22 = v38;
      }
    }
    (*(void (__fastcall **)(__int64, const wchar_t *, VARIANTARG *))(*(_QWORD *)v79 + 352LL))(
      v79,
      L"LicenseKeyVersion",
      &v100);
    if ( SysStringLen(v100.bstrVal) )
    {
      v39 = _o__wtol(v100.llVal);
      if ( v39 > 0 )
        *a11 = v39;
    }
  }
  if ( *a6 )
    goto LABEL_68;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
    &v87,
    L"//%s[@%s='%s']/%s",
    g_bstrDeviceUser,
    g_bstrDeviceUsername,
    v30,
    g_bstrDevicePwd);
  v40 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v24 + 296LL);
  v41 = v87;
  v42 = ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, v87);
  LODWORD(v78) = v40(v24, *(_QWORD *)v42, &v90);
  SysFreeString(bstrString);
  if ( (int)v78 < 0 )
  {
    LODWORD(v76) = v78;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\deviceidstore.cpp",
      0x5CEu,
      L"selectSingleNode for %ls failed with hr = %x",
      v41,
      v76);
LABEL_44:
    v21 = a5;
    v11 = v112;
    LODWORD(v13) = (_DWORD)a1;
    goto LABEL_70;
  }
  if ( (_DWORD)v78 )
  {
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\deviceidstore.cpp",
      0x5D5u,
      L"Encrypted password node is missing from store.");
    goto LABEL_44;
  }
  ATL::CComQIPtr<IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>::operator=(&v79, v90);
  if ( v79 )
  {
    v44 = (*(__int64 (__fastcall **)(__int64, BSTR, VARIANTARG *))(*(_QWORD *)v79 + 352LL))(
            v79,
            g_bstrDevicePwdVersion,
            &pvarg);
    LODWORD(v78) = v44;
    if ( v44 < 0 )
    {
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\deviceidstore.cpp",
        "DeviceIdStore::GetDeviceInfoFromPersistentStore",
        0x5DCu,
        v44,
        "hr = pElement->getAttribute(g_bstrDevicePwdVersion, &passwordVersion)");
LABEL_51:
      v43 = a1;
LABEL_52:
      v14 = HIDWORD(v78);
LABEL_53:
      v45 = v78;
      if ( !(_DWORD)v78 )
        goto LABEL_61;
      if ( (_DWORD)v78 != -2147024882 )
      {
        v14 = v78;
        v45 = -2147187449;
        LODWORD(v78) = -2147187449;
      }
      goto LABEL_56;
    }
    v50 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v90 + 208LL))(v90, &pbstr);
    LODWORD(v78) = v50;
    if ( v50 )
    {
      LODWORD(v73) = v50;
      TracePrintW(
        2u,
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\deviceidstore.cpp",
        0x5E2u,
        L"get_text failed with hr = %x",
        v73);
      goto LABEL_44;
    }
    if ( !SysStringLen(pbstr) )
    {
      TracePrintW(
        2u,
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\deviceidstore.cpp",
        0x5E8u,
        L"Encrypted password is empty in store.");
      goto LABEL_44;
    }
    v43 = a1;
    v51 = DecryptPasswordAndRewriteIfNeeded(a1, a2, pbstr, pvarg.llVal, v112, a5, a3);
    LODWORD(v78) = v51;
    if ( v51 < 0 )
    {
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\deviceidstore.cpp",
        "DeviceIdStore::GetDeviceInfoFromPersistentStore",
        0x5ECu,
        v51,
        "hr = DecryptPasswordAndRewriteIfNeeded(wstrDeviceIDKey, wszUserName, bstrEncryptedPassword, passwordVersion.bstr"
        "Val, ctLastUpdatedTime, ctDAInvalidationTime, wstrPwd)");
      goto LABEL_52;
    }
LABEL_68:
    v45 = 0;
    LODWORD(v78) = 0;
    goto LABEL_61;
  }
  LODWORD(v78) = -2147024882;
  v43 = a1;
  v14 = HIDWORD(v78);
LABEL_57:
  if ( (unsigned int)dword_1801C2080 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1801C2080, 0x400000000000LL) )
  {
    LODWORD(a5) = v14;
    LODWORD(v112) = v78;
    LODWORD(a6) = v110;
    v46 = _o__wcsicmp(v43, L"S-1-5-18");
    LODWORD(a7) = v46 == 0;
    a8 = a2;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v46 == 0,
      (__int64)byte_18019B7DB,
      v47,
      v48,
      (const unsigned __int16 **)&a8,
      (__int64)&a7,
      (__int64)&a6,
      (__int64)&v112,
      (__int64)&a5);
  }
  v45 = v78;
LABEL_61:
  CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>((__int64)v107);
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v108);
  VariantClear(&v100);
  VariantClear(&v96);
  VariantClear(&v101);
  VariantClear(&v102);
  VariantClear(&v103);
  VariantClear(&v97);
  VariantClear(&v98);
  VariantClear(&v99);
  VariantClear(&pvarg);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v92);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v79);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v87);
  SysFreeString(pbstr);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v95);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v89);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v93);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v90);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v91);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v94);
  return v45;
}

```

## disassembly

```asm
0x180103e9c  mov     rax, rsp
0x180103e9f  mov     [rax+20h], r9
0x180103ea3  mov     [rax+18h], r8
0x180103ea7  mov     [rax+8], rcx
0x180103eab  push    rbp
0x180103eac  push    rbx
0x180103ead  push    rsi
0x180103eae  push    rdi
0x180103eaf  push    r12
0x180103eb1  push    r13
0x180103eb3  push    r14
0x180103eb5  push    r15
0x180103eb7  lea     rbp, [rax-168h]
0x180103ebe  sub     rsp, 228h
0x180103ec5  mov     r14, r9
0x180103ec8  mov     r12, rdx
0x180103ecb  mov     rbx, rcx
0x180103ece  xor     edi, edi
0x180103ed0  mov     dword ptr [rsp+260h+var_200], edi
0x180103ed4  mov     r15d, edi
0x180103ed7  mov     dword ptr [rsp+260h+var_200+4], edi
0x180103edb  mov     [rbp+160h+var_180], rdi
0x180103edf  mov     [rbp+160h+var_198], rdi
0x180103ee3  mov     [rbp+160h+var_1A0], rdi
0x180103ee7  mov     [rbp+160h+var_188], rdi
0x180103eeb  lea     rcx, [rbp+160h+var_1A8]
0x180103eef  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180103ef4  nop
0x180103ef5  lea     rcx, [rbp+160h+var_178]
0x180103ef9  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180103efe  nop
0x180103eff  mov     [rbp+160h+pbstr], rdi
0x180103f03  lea     rcx, [rbp+160h+var_1B8]
0x180103f07  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180103f0c  nop
0x180103f0d  mov     [rsp+260h+var_1F8], rdi
0x180103f12  lea     rcx, [rbp+160h+var_190]
0x180103f16  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180103f1b  nop
0x180103f1c  lea     rcx, [rbp+160h+pvarg]; pvarg
0x180103f23  call    cs:__imp_VariantInit
0x180103f29  nop
0x180103f2a  lea     rcx, [rbp+160h+var_128]; pvarg
0x180103f2e  call    cs:__imp_VariantInit
0x180103f34  nop
0x180103f35  lea     rcx, [rbp+160h+var_140]; pvarg
0x180103f39  call    cs:__imp_VariantInit
0x180103f3f  nop
0x180103f40  lea     rcx, [rbp+160h+var_158]; pvarg
0x180103f44  call    cs:__imp_VariantInit
0x180103f4a  nop
0x180103f4b  lea     rcx, [rbp+160h+var_C8]; pvarg
0x180103f52  call    cs:__imp_VariantInit
0x180103f58  nop
0x180103f59  lea     rcx, [rbp+160h+var_E0]; pvarg
0x180103f60  call    cs:__imp_VariantInit
0x180103f66  nop
0x180103f67  lea     rcx, [rbp+160h+var_F8]; pvarg
0x180103f6b  call    cs:__imp_VariantInit
0x180103f71  nop
0x180103f72  lea     rcx, [rbp+160h+var_170]; pvarg
0x180103f76  call    cs:__imp_VariantInit
0x180103f7c  nop
0x180103f7d  lea     rcx, [rbp+160h+var_110]; pvarg
0x180103f81  call    cs:__imp_VariantInit
0x180103f87  nop
0x180103f88  mov     [rbp+160h+arg_8], dil
0x180103f8f  call    ?PPTraceShouldRedact@@YA_NXZ; PPTraceShouldRedact(void)
0x180103f94  test    al, al
0x180103f96  jz      short loc_180103FA5
0x180103f98  mov     cl, 1; this
0x180103f9a  call    ?TraceOnFlag@PPTraceStatus@@YA_NE@Z; PPTraceStatus::TraceOnFlag(uchar)
0x180103f9f  test    al, al
0x180103fa1  mov     al, cl
0x180103fa3  jnz     short loc_180103FA8
0x180103fa5  mov     al, dil
0x180103fa8  mov     [rbp+160h+var_A8], r12
0x180103faf  mov     [rbp+160h+var_A0], rdi
0x180103fb6  mov     [rbp+160h+var_98], al
0x180103fbc  lea     rax, ??_7PPRedactedStringW@@6B@; const PPRedactedStringW::`vftable'
0x180103fc3  mov     [rbp+160h+var_B0], rax
0x180103fca  lea     rcx, [rbp+160h+var_B0]; this
0x180103fd1  call    ?GetString@PPRedactedStringW@@QEAAPEBGXZ; PPRedactedStringW::GetString(void)
0x180103fd6  mov     [rsp+260h+var_228], rax
0x180103fdb  mov     [rsp+260h+var_230], rbx
0x180103fe0  lea     rax, aWstrdeviceidke_3; "wstrDeviceIDKey=%ls,wszUserName=%ls"
0x180103fe7  mov     [rsp+260h+var_238], rax
0x180103fec  lea     rax, aDeviceidstoreG_3; "DeviceIdStore::GetDeviceInfoFromPersist"...
0x180103ff3  mov     [rsp+260h+var_240], rax
0x180103ff8  lea     r9, [rsp+260h+var_200]
0x180103ffd  mov     r8d, 528h
0x180104003  lea     rdx, aOnecoreuapDsEx_105; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18010400a  lea     rcx, [rbp+160h+var_68]
0x180104011  call    ??0?$CTraceFuncW@J@@QEAA@PEBDKAEAJ0PEBGZZ; CTraceFuncW<long>::CTraceFuncW<long>(char const *,ulong,long &,char const *,ushort const *,...)
0x180104016  nop
0x180104017  lea     rcx, [rbp+160h+var_B0]; this
0x18010401e  call    ??1PPRedactedStringW@@QEAA@XZ; PPRedactedStringW::~PPRedactedStringW(void)
0x180104023  mov     r8b, 1
0x180104026  lea     rdx, qword_1801C43A8
0x18010402d  lea     rcx, [rbp+160h+var_78]
0x180104034  call    ??0?$CComCritSecLockWTry@VCComAutoCriticalSectionWTry@@@@QEAA@AEAVCComAutoCriticalSectionWTry@@_N@Z; CComCritSecLockWTry<CComAutoCriticalSectionWTry>::CComCritSecLockWTry<CComAutoCriticalSectionWTry>(CComAutoCriticalSectionWTry &,bool)
0x180104039  nop
0x18010403a  mov     rax, [rbp+160h+arg_28]
0x180104041  mov     [rax], rdi
0x180104044  mov     [r14], rdi
0x180104047  mov     rsi, [rbp+160h+arg_20]
0x18010404e  mov     [rsi], rdi
0x180104051  mov     rax, [rbp+160h+arg_30]
0x180104058  mov     [rax], edi
0x18010405a  mov     rax, [rbp+160h+arg_38]
0x180104061  mov     [rax], edi
0x180104063  mov     rax, [rbp+160h+arg_40]
0x18010406a  mov     [rax], edi
0x18010406c  mov     r13, [rbp+160h+bstrString]
0x180104073  mov     [r13+0], edi
0x180104077  test    r12, r12
0x18010407a  jz      loc_180104E5B
0x180104080  cmp     [r12], di
0x180104085  jz      loc_180104E5B
0x18010408b  lea     r9, [rbp+160h+var_180]
0x18010408f  xor     r8d, r8d
0x180104092  mov     rdx, r12
0x180104095  mov     rcx, rbx
0x180104098  call    ?LoadPersistedDOM@DeviceIdStore@@CAJPEBG0_NAEAV?$CComPtr@UIXMLDOMDocument@@@ATL@@@Z; DeviceIdStore::LoadPersistedDOM(ushort const *,ushort const *,bool,ATL::CComPtr<IXMLDOMDocument> &)
0x18010409d  mov     dword ptr [rsp+260h+var_200], eax
0x1801040a1  test    eax, eax
0x1801040a3  jns     short loc_1801040D0
0x1801040a5  mov     dword ptr [rsp+260h+var_240], eax
0x1801040a9  lea     r9, aLoadpersistedd; "::LoadPersistedDOM failed with hr = %x"
0x1801040b0  mov     r8d, 53Eh; unsigned int
0x1801040b6  lea     rdx, aOnecoreuapDsEx_105; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1801040bd  mov     r15d, 2
0x1801040c3  mov     ecx, r15d; unsigned __int8
0x1801040c6  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1801040cb  jmp     loc_180104953
0x1801040d0  mov     rdi, [rbp+160h+var_180]
0x1801040d4  mov     rax, [rdi]
0x1801040d7  lea     rdx, [rbp+160h+var_198]
0x1801040db  mov     rcx, rdi
0x1801040de  mov     rax, [rax+168h]
0x1801040e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801040ea  mov     dword ptr [rsp+260h+var_200], eax
0x1801040ee  test    eax, eax
0x1801040f0  js      loc_18010492B
0x1801040f6  mov     rcx, [rbp+160h+var_198]
0x1801040fa  test    rcx, rcx
0x1801040fd  jz      loc_18010492B
0x180104103  mov     rax, [rcx]
0x180104106  lea     r8, [rbp+160h+var_140]
0x18010410a  mov     rdx, cs:?g_bstrDeviceLastUpdatedTime@@3VCComBSTR@ATL@@A; ATL::CComBSTR g_bstrDeviceLastUpdatedTime
0x180104111  mov     rax, [rax+160h]
0x180104118  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010411d  mov     dword ptr [rsp+260h+var_200], eax
0x180104121  mov     rcx, qword ptr [rbp+160h+var_140+8]; pbstr
0x180104125  call    cs:__imp_SysStringLen
0x18010412b  mov     r15d, 2
0x180104131  test    eax, eax
0x180104133  jz      short loc_18010417A
0x180104135  mov     rcx, qword ptr [rbp+160h+var_140+8]
0x180104139  call    cs:__imp__o__wtol
0x18010413f  movsxd  rbx, eax
0x180104142  test    eax, eax
0x180104144  jnz     short loc_180104177
0x180104146  call    cs:__imp__o__errno
0x18010414c  mov     ecx, [rax]
0x18010414e  mov     dword ptr [rsp+260h+var_238], ecx
0x180104152  mov     rcx, qword ptr [rbp+160h+var_140+8]
0x180104156  mov     [rsp+260h+var_240], rcx
0x18010415b  lea     r9, aInvalidLastBou; "Invalid Last Bound Time set = %ls, errn"...
0x180104162  mov     r8d, 550h; unsigned int
0x180104168  lea     rdx, aOnecoreuapDsEx_105; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18010416f  mov     ecx, r15d; unsigned __int8
0x180104172  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180104177  mov     [r14], rbx
0x18010417a  mov     rcx, [rbp+160h+var_198]
0x18010417e  mov     rax, [rcx]
0x180104181  lea     r8, [rbp+160h+var_158]
0x180104185  mov     rdx, cs:?g_bstrDeviceDAInvalidationTime@@3VCComBSTR@ATL@@A; ATL::CComBSTR g_bstrDeviceDAInvalidationTime
0x18010418c  mov     rax, [rax+160h]
0x180104193  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180104198  mov     dword ptr [rsp+260h+var_200], eax
0x18010419c  mov     rcx, qword ptr [rbp+160h+var_158+8]; pbstr
0x1801041a0  call    cs:__imp_SysStringLen
0x1801041a6  test    eax, eax
0x1801041a8  jz      short loc_1801041EF
0x1801041aa  mov     rcx, qword ptr [rbp+160h+var_158+8]
0x1801041ae  call    cs:__imp__o__wtol
0x1801041b4  movsxd  rbx, eax
0x1801041b7  test    eax, eax
0x1801041b9  jnz     short loc_1801041EC
0x1801041bb  call    cs:__imp__o__errno
0x1801041c1  mov     ecx, [rax]
0x1801041c3  mov     dword ptr [rsp+260h+var_238], ecx
0x1801041c7  mov     rcx, qword ptr [rbp+160h+var_158+8]
0x1801041cb  mov     [rsp+260h+var_240], rcx
0x1801041d0  lea     r9, aInvalidDaInval; "Invalid DA Invalidation Time set = %ls,"...
0x1801041d7  mov     r8d, 55Dh; unsigned int
0x1801041dd  lea     rdx, aOnecoreuapDsEx_105; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1801041e4  mov     ecx, r15d; unsigned __int8
0x1801041e7  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1801041ec  mov     [rsi], rbx
0x1801041ef  lea     rdx, [rbp+160h+var_1A8]
0x1801041f3  mov     rcx, r12
0x1801041f6  call    ?SanitizeAndEscapeXML@@YAXPEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; SanitizeAndEscapeXML(ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x1801041fb  lea     rcx, [rbp+160h+var_1A8]
0x1801041ff  call    ?MakeUpper@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV12@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::MakeUpper(void)
0x180104204  mov     rax, cs:?g_bstrDeviceHardwareInfo@@3VCComBSTR@ATL@@A; ATL::CComBSTR g_bstrDeviceHardwareInfo
0x18010420b  mov     [rsp+260h+var_238], rax
0x180104210  mov     rsi, [rbp+160h+var_1A8]
0x180104214  mov     [rsp+260h+var_240], rsi
0x180104219  mov     r9, cs:?g_bstrDeviceUsername@@3VCComBSTR@ATL@@A; ATL::CComBSTR g_bstrDeviceUsername
0x180104220  mov     r8, cs:?g_bstrDeviceUser@@3VCComBSTR@ATL@@A; ATL::CComBSTR g_bstrDeviceUser
0x180104227  lea     rdx, aSSSS; "//%s[@%s='%s']/%s"
0x18010422e  lea     rcx, [rbp+160h+var_1B8]
0x180104232  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x180104237  mov     rax, [rdi]
0x18010423a  mov     r14, [rax+128h]
0x180104241  mov     rbx, [rbp+160h+var_1B8]
0x180104245  mov     rdx, rbx; unsigned __int16 *
0x180104248  lea     rcx, [rbp+160h+bstrString]; this
0x18010424f  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x180104254  nop
0x180104255  lea     r8, [rbp+160h+var_188]
0x180104259  mov     rdx, [rax]
0x18010425c  mov     rcx, rdi
0x18010425f  mov     rax, r14
0x180104262  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180104267  mov     dword ptr [rsp+260h+var_200], eax
0x18010426b  mov     rcx, [rbp+160h+bstrString]; bstrString
0x180104272  call    cs:__imp_SysFreeString
0x180104278  mov     eax, dword ptr [rsp+260h+var_200]
0x18010427c  test    eax, eax
0x18010427e  jns     short loc_1801042BF
0x180104280  mov     dword ptr [rsp+260h+var_238], eax
0x180104284  mov     [rsp+260h+var_240], rbx
0x180104289  lea     r9, aSelectsingleno; "selectSingleNode for %ls failed with hr"...
0x180104290  mov     r8d, 573h; unsigned int
0x180104296  lea     rdx, aOnecoreuapDsEx_105; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18010429d  mov     ecx, r15d; unsigned __int8
0x1801042a0  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1801042a5  mov     rsi, [rbp+160h+arg_20]
0x1801042ac  mov     r14, [rbp+160h+arg_18]
0x1801042b3  mov     rbx, [rbp+160h+arg_0]
0x1801042ba  jmp     loc_180104951
0x1801042bf  mov     rdx, [rbp+160h+var_188]
0x1801042c3  lea     rcx, [rsp+260h+var_1F8]
0x1801042c8  call    ??4?$CComQIPtr@UIXMLDOMElement@@$1?_GUID_2933bf86_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@ATL@@QEAAPEAUIXMLDOMElement@@PEAUIUnknown@@@Z; ATL::CComQIPtr<IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>::operator=(IUnknown *)
0x1801042cd  mov     rcx, [rsp+260h+var_1F8]
0x1801042d2  test    rcx, rcx
0x1801042d5  jz      loc_1801044EA
0x1801042db  mov     rax, [rcx]
0x1801042de  lea     r8, [rbp+160h+var_128]
0x1801042e2  mov     rdx, cs:?g_bstrDeviceHardwareBoundTime@@3VCComBSTR@ATL@@A; ATL::CComBSTR g_bstrDeviceHardwareBoundTime
0x1801042e9  mov     rax, [rax+160h]
0x1801042f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801042f5  mov     rcx, qword ptr [rbp+160h+var_128+8]; pbstr
0x1801042f9  call    cs:__imp_SysStringLen
0x1801042ff  test    eax, eax
0x180104301  jz      short loc_18010434F
0x180104303  mov     rcx, qword ptr [rbp+160h+var_128+8]
0x180104307  call    cs:__imp__o__wtol
0x18010430d  movsxd  rbx, eax
0x180104310  test    eax, eax
0x180104312  jnz     short loc_180104345
0x180104314  call    cs:__imp__o__errno
0x18010431a  mov     ecx, [rax]
0x18010431c  mov     dword ptr [rsp+260h+var_238], ecx
0x180104320  mov     rcx, qword ptr [rbp+160h+var_128+8]
0x180104324  mov     [rsp+260h+var_240], rcx
0x180104329  lea     r9, aInvalidHwdBoun; "Invalid Hwd Bound Time set = %ls, errno"...
0x180104330  mov     r8d, 581h; unsigned int
0x180104336  lea     rdx, aOnecoreuapDsEx_105; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18010433d  mov     ecx, r15d; unsigned __int8
0x180104340  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180104345  mov     rcx, [rbp+160h+arg_28]
0x18010434c  mov     [rcx], rbx
0x18010434f  mov     rcx, [rsp+260h+var_1F8]
0x180104354  mov     rax, [rcx]
0x180104357  lea     r8, [rbp+160h+var_C8]
0x18010435e  mov     rdx, cs:?g_bstrDeviceTpmKeyStateClient@@3VCComBSTR@ATL@@A; ATL::CComBSTR g_bstrDeviceTpmKeyStateClient
0x180104365  mov     rax, [rax+160h]
0x18010436c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180104371  mov     rcx, qword ptr [rbp+160h+var_C8+8]; pbstr
0x180104378  call    cs:__imp_SysStringLen
0x18010437e  test    eax, eax
0x180104380  jz      short loc_18010439D
0x180104382  mov     rcx, qword ptr [rbp+160h+var_C8+8]
0x180104389  call    cs:__imp__o__wtoi
0x18010438f  cmp     eax, 7
0x180104392  ja      short loc_18010439D
0x180104394  mov     rcx, [rbp+160h+arg_30]
0x18010439b  mov     [rcx], eax
0x18010439d  mov     rcx, [rsp+260h+var_1F8]
0x1801043a2  mov     rax, [rcx]
0x1801043a5  lea     r8, [rbp+160h+var_E0]
0x1801043ac  mov     rdx, cs:?g_bstrDeviceTpmKeyStateServer@@3VCComBSTR@ATL@@A; ATL::CComBSTR g_bstrDeviceTpmKeyStateServer
0x1801043b3  mov     rax, [rax+160h]
0x1801043ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801043bf  mov     rcx, qword ptr [rbp+160h+var_E0+8]; pbstr
0x1801043c6  call    cs:__imp_SysStringLen
  ... truncated ...
```
