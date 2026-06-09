# CSingleIdentity::GetOneTimeCredentialEx(unsigned __int64,ushort const *,ushort const *,ushort const *,ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *,long *,ATL::CTime *)

- ea: `0x18004908c`
- end: `0x180049ede`
- name: `?GetOneTimeCredentialEx@CSingleIdentity@@QEAAJ_KPEBG111AEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@2PEAV23@PEAJPEAVCTime@3@@Z`
- size: `3666`
- prototype: `__int64 __usercall@<rax>(CSingleIdentity *this@<rcx>, __int64, __int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `7`
- callee_count: `54`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800122b0`
- `0x18002104c`
- `0x180049010`
- `0x1800957f4`
- `0x180099a30`
- `0x1800bdba0`
- `0x1800cddc0`

## callees

- `0x180002200`
- `0x18000a354`
- `0x18000ae44`
- `0x18000c050`
- `0x18000c280`
- `0x18000e008`
- `0x18000ed04`
- `0x180011f38`
- `0x180013fb4`
- `0x180014490`
- `0x1800151c4`
- `0x180015860`
- `0x180015fdc`
- `0x180016500`
- `0x180017410`
- `0x1800174f0`
- `0x1800179c0`
- `0x180017af0`
- `0x180017bf0`
- `0x180017d10`
- `0x1800191c0`
- `0x180019690`
- `0x18001a530`
- `0x18001a9c0`
- `0x18001b3b0`
- `0x18001cf20`
- `0x18002457c`
- `0x1800268d0`
- `0x180026bb4`
- `0x180026c18`
- `0x1800277c0`
- `0x180028770`
- `0x18002b370`
- `0x1800306b0`
- `0x180037288`
- `0x18004908c`
- `0x18004fab4`
- `0x180052ca8`
- `0x18005538c`
- `0x18007ecc8`
- `0x180083078`
- `0x180084374`
- `0x1800855a4`
- `0x180086288`
- `0x180087e40`
- `0x18008b9d4`
- `0x1800a3b60`
- `0x1800a4718`
- `0x1800a4778`
- `0x1800d8c7c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180049e50`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180049e50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049c0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049c0e`
- `WINHTTP!WinHttpCrackUrl` at `0x180049c04`
- `WINHTTP!WinHttpCrackUrl` at `0x180049c04`
- `ext-ms-win-msa-device-l1-1-0!MsaDevice_UseXTokenBasedSessionKey` at `0x180049755`
- `ext-ms-win-msa-device-l1-1-0!MsaDevice_UseXTokenBasedSessionKey` at `0x18004985a`
- `ext-ms-win-msa-device-l1-1-0!MsaDevice_UseXTokenBasedSessionKey` at `0x1800498b3`
- `ext-ms-win-msa-device-l1-1-0!MsaDevice_UseXTokenBasedSessionKey` at `0x180049755`
- `ext-ms-win-msa-device-l1-1-0!MsaDevice_UseXTokenBasedSessionKey` at `0x18004985a`
- `ext-ms-win-msa-device-l1-1-0!MsaDevice_UseXTokenBasedSessionKey` at `0x1800498b3`

## string_xrefs

- `0x18004914b`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\singleidentity.cpp`
- `0x180049486`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\singleidentity.cpp`
- `0x1800497d4`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\singleidentity.cpp`
- `0x180049820`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\singleidentity.cpp`
- `0x180049925`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\singleidentity.cpp`
- `0x180049c44`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\singleidentity.cpp`
- `0x180049cd9`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\singleidentity.cpp`
- `0x180049de2`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\singleidentity.cpp`
- `0x180049e85`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\singleidentity.cpp`
- `0x180049530`: `!strToken.IsEmpty()`
- `0x180049674`: `&linkct=%S`
- `0x18004964d`: `hr = WlidsvcUtil::WString2LARGE_INTEGER(wstrLinkId, &liLinkId)`
- `0x1800496a0`: `&linkh=%d`
- `0x18004968a`: `&linkl=%d`
- `0x180049c69`: `urlComponents.lpszHostName != nullptr`
- `0x180049e78`: `Failed to get <PassportSHA1Auth> URL from the config file:  (0x%x)`

## pseudocode

```c
// Hidden C++ exception states: #wind=32
__int64 __fastcall CSingleIdentity::GetOneTimeCredentialEx(
        CSingleIdentity *this,
        char a2,
        const char *a3,
        _WORD *a4,
        _WORD *a5,
        _WORD *a6,
        LPCWSTR *a7,
        __int64 a8,
        const unsigned __int16 *a9,
        const unsigned __int16 *a10,
        LPSTR *a11)
{
  __int64 v14; // rcx
  __int64 BinaryVersion; // rax
  const char *v16; // rax
  unsigned int v17; // r8d
  __int64 v18; // rdx
  __int64 (__fastcall *v19)(CSingleIdentity *, __int64, const wchar_t **); // rbx
  __int64 *v20; // rax
  int v21; // eax
  __int64 v22; // rbx
  unsigned int TimeSkew; // esi
  int v24; // eax
  unsigned int v25; // r14d
  int v26; // eax
  char v27; // si
  int v28; // ebx
  void ***ServerBuildInfo; // rax
  const unsigned __int16 **v30; // rax
  const unsigned __int16 **RawPUID; // rax
  int v32; // ebx
  __int64 v33; // rcx
  __int64 v34; // r8
  __int64 v35; // r9
  struct CClientConfigDataCacheManager *v36; // rax
  int ServiceURI; // eax
  int v38; // ebx
  LPCWSTR v39; // rax
  signed int LastError; // eax
  _QWORD *PassportSTSHost; // rax
  const char *v42; // rbx
  _QWORD *v43; // rax
  __int64 v44; // rax
  unsigned int OneBoxSSLPort; // ebx
  const char **v46; // rcx
  _QWORD *v47; // rax
  __int64 v48; // rbx
  int v49; // edx
  int v50; // ecx
  unsigned int v51; // ebx
  char *v53; // [rsp+20h] [rbp-E0h]
  char **v54; // [rsp+28h] [rbp-D8h]
  int ServiceToken; // [rsp+60h] [rbp-A0h] BYREF
  void **v56; // [rsp+68h] [rbp-98h] BYREF
  const char *v57; // [rsp+70h] [rbp-90h] BYREF
  int v58[2]; // [rsp+78h] [rbp-88h] BYREF
  const char *v59; // [rsp+80h] [rbp-80h] BYREF
  __int64 v60; // [rsp+88h] [rbp-78h] BYREF
  __int64 v61; // [rsp+90h] [rbp-70h] BYREF
  __int64 v62; // [rsp+98h] [rbp-68h] BYREF
  const wchar_t *v63; // [rsp+A0h] [rbp-60h] BYREF
  const wchar_t *v64; // [rsp+A8h] [rbp-58h] BYREF
  void **v65; // [rsp+B0h] [rbp-50h] BYREF
  unsigned int v66; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v67; // [rsp+C0h] [rbp-40h]
  int v68; // [rsp+C8h] [rbp-38h]
  const unsigned __int16 *v69; // [rsp+D0h] [rbp-30h] BYREF
  const unsigned __int16 *v70; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v71; // [rsp+E0h] [rbp-20h] BYREF
  char v72[8]; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v73; // [rsp+F0h] [rbp-10h]
  __int64 v74; // [rsp+F8h] [rbp-8h]
  __int64 v75; // [rsp+100h] [rbp+0h] BYREF
  __int64 v76; // [rsp+108h] [rbp+8h] BYREF
  $BC2FB811D417144E831EE3AEA4A279C8 UrlComponents; // [rsp+110h] [rbp+10h] BYREF
  unsigned int v78; // [rsp+198h] [rbp+98h]
  unsigned __int8 *v79; // [rsp+1A0h] [rbp+A0h]
  __int64 v80; // [rsp+1C0h] [rbp+C0h] BYREF
  const char *v81[5]; // [rsp+1C8h] [rbp+C8h] BYREF
  void *Block; // [rsp+1F0h] [rbp+F0h] BYREF
  _BYTE v83[136]; // [rsp+1F8h] [rbp+F8h] BYREF
  void *v84; // [rsp+280h] [rbp+180h] BYREF
  _BYTE v85[136]; // [rsp+288h] [rbp+188h] BYREF
  void *v86; // [rsp+310h] [rbp+210h] BYREF
  _BYTE v87[136]; // [rsp+318h] [rbp+218h] BYREF
  void *v88; // [rsp+3A0h] [rbp+2A0h] BYREF
  _BYTE v89[136]; // [rsp+3A8h] [rbp+2A8h] BYREF
  void *v90; // [rsp+430h] [rbp+330h] BYREF
  _BYTE v91[264]; // [rsp+438h] [rbp+338h] BYREF

  v59 = a3;
  v71 = a8;
  v70 = a9;
  v65 = (void **)a10;
  LODWORD(v60) = 0;
  ServiceToken = 0;
  CTraceFuncW<long>::CTraceFuncW<long>(
    v81,
    "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\singleidentity.cpp",
    1000,
    (const char *)&ServiceToken,
    "CSingleIdentity::GetOneTimeCredentialEx",
    (wchar_t *)L"flags=0x%llx, wcszAppId=%ls, wcszTarget=%ls, wcszPolicy=%ls, wcszAdditionalParams=%ls");
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v58);
  ATL::CSimpleStringT<char,0>::Empty(v58);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::AppendFormat(v58, "bver=");
  CClientConfigDataCacheManager::theConfigDataManager();
  BinaryVersion = CClientConfigDataCacheManager::GetBinaryVersion(v14, &v56);
  ATL::CSimpleStringT<char,0>::Append(v58, BinaryVersion);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v56);
  if ( a6 )
  {
    if ( *a6 )
    {
      ATL::CSimpleStringT<char,0>::Append(v58, "&");
      Block = v83;
      ATL::CW2AEX<128>::Init(&Block, a6, 65001);
      ATL::CSimpleStringT<char,0>::Append(v58, Block);
      if ( Block != v83 )
        free(Block);
    }
  }
  if ( a4 && *a4 )
  {
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v57);
    v84 = v85;
    ATL::CW2AEX<128>::Init(&v84, a4, 65001);
    ATL::CSimpleStringT<char,0>::SetString(&v57, v84);
    if ( v84 != v85 )
      free(v84);
    UrlEscapeString(&v57);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::AppendFormat(v58, "&ru=%s", v57);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v57);
  }
  if ( a5 && *a5 )
  {
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v57);
    v86 = v87;
    ATL::CW2AEX<128>::Init(&v86, a5, 65001);
    ATL::CSimpleStringT<char,0>::SetString(&v57, v86);
    if ( v86 != v87 )
      free(v86);
    UrlEscapeString(&v57);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::AppendFormat(v58, "&pl=%s", v57);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v57);
  }
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(
    &v56,
    v59);
  UrlEscapeString(&v56);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::AppendFormat(v58, "&appid=%s", (const char *)v56);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v56);
  if ( (a2 & 2) != 0 )
  {
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(
      &v56,
      "1");
    UrlEscapeString(&v56);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::AppendFormat(
      v58,
      "&loginoptions=%s",
      (const char *)v56);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v56);
  }
  if ( (a2 & 1) != 0 )
  {
    (*(void (__fastcall **)(CSingleIdentity *, void ***))(*(_QWORD *)this + 32LL))(this, &v56);
    UrlEscapeString(&v56);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::AppendFormat(
      v58,
      "&login=%S",
      (const wchar_t *)v56);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v56);
    goto LABEL_89;
  }
  CPPCRLToken::CPPCRLToken((CPPCRLToken *)&UrlComponents);
  v67 = 0;
  v66 = 0;
  v68 = 0;
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v61);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v59);
  ServiceToken = CSingleIdentity::GetServiceToken(this, L"http://Passport.NET/tb", (struct CPPCRLToken *)&UrlComponents);
  if ( ServiceToken < 0 )
  {
    v16 = "SUCCEEDED(hr)";
    v17 = 1076;
LABEL_21:
    ServiceToken = -2147186591;
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\singleidentity.cpp",
      "CSingleIdentity::GetOneTimeCredentialEx",
      v17,
      -2147186591,
      v16);
LABEL_22:
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v59);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v61);
    CBytePtr::Empty((CBytePtr *)&v66);
    CPPCRLToken::~CPPCRLToken((CPPCRLToken *)&UrlComponents);
    goto LABEL_113;
  }
  v18 = *(_QWORD *)CPPCRLToken::GetToken(&UrlComponents, &v56);
  v88 = v89;
  ATL::CW2AEX<128>::Init(&v88, v18, 65001);
  ATL::CSimpleStringT<char,0>::SetString(&v61, v88);
  if ( v88 != v89 )
    free(v88);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v56);
  if ( !*(_DWORD *)(v61 - 16) )
  {
    v16 = "!strToken.IsEmpty()";
    v17 = 1082;
    goto LABEL_21;
  }
  ATL::CSimpleStringT<char,0>::operator=(&v59, &v61);
  UrlEscapeString(&v59);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::AppendFormat(v58, "&da=%hs", v59);
  if ( a11 )
    *a11 = UrlComponents.lpszPassword;
  if ( CSingleIdentity::GetIsLinkedHandle(this) )
  {
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v60);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v64);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v57);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v63);
    v56 = 0;
    v19 = *(__int64 (__fastcall **)(CSingleIdentity *, __int64, const wchar_t **))(*(_QWORD *)this + 64LL);
    v20 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
            (__int64 *)&v69,
            L"CID");
    ServiceToken = v19(this, *v20, &v63);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v69);
    if ( ServiceToken < 0 || !*((_DWORD *)v63 - 4) )
    {
      ServiceToken = -2147186535;
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\singleidentity.cpp",
        "CSingleIdentity::GetOneTimeCredentialEx",
        0x450u,
        -2147186535,
        "SUCCEEDED(hr) && !wstrCID.IsEmpty()");
      goto LABEL_49;
    }
    ServiceToken = CSingleIdentity::GetLinkInfo(this, &v60, &v64, &v57);
    if ( ServiceToken < 0 || !*(_DWORD *)(v60 - 16) )
      goto LABEL_49;
    v21 = WlidsvcUtil::WString2LARGE_INTEGER(&v60, &v56);
    ServiceToken = v21;
    if ( v21 < 0 )
    {
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\singleidentity.cpp",
        "CSingleIdentity::GetOneTimeCredentialEx",
        0x456u,
        v21,
        "hr = WlidsvcUtil::WString2LARGE_INTEGER(wstrLinkId, &liLinkId)");
LABEL_49:
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v63);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v57);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v64);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v60);
      goto LABEL_22;
    }
    UrlEscapeString(&v64);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::AppendFormat(v58, "&linkct=%S", v64);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::AppendFormat(v58, "&linkl=%d", (_DWORD)v56);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::AppendFormat(v58, "&linkh=%d", HIDWORD(v56));
    UrlEscapeString(&v63);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::AppendFormat(v58, "&cid=%S", v63);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v63);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v57);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v64);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v60);
  }
  v22 = *(_QWORD *)v58;
  if ( v70 )
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
      v70,
      *(_QWORD *)v58);
  v56 = &NgcFunctions::`vftable';
  *(_QWORD *)v72 = 0;
  v74 = 0;
  v73 = 0;
  TimeSkew = GetTimeSkew();
  if ( v65 )
    *(_DWORD *)v65 = TimeSkew;
  CBytePtr::Attach((CBytePtr *)&v66, v79, v78, 0);
  v24 = MsaDevice_UseXTokenBasedSessionKey();
  v25 = v66;
  if ( !v24 && !v66 )
  {
    if ( (*(unsigned int (__fastcall **)(CSingleIdentity *))(*(_QWORD *)this + 80LL))(this) == 1
      || (*(unsigned int (__fastcall **)(CSingleIdentity *))(*(_QWORD *)this + 80LL))(this) == 2
      || (*(unsigned int (__fastcall **)(CSingleIdentity *))(*(_QWORD *)this + 80LL))(this) == 3 )
    {
      ServiceToken = -2147188722;
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\singleidentity.cpp",
        "CSingleIdentity::GetOneTimeCredentialEx",
        0x475u,
        -2147188722,
        "!IsDeviceUserType(GetUserType())");
LABEL_47:
      Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>::~Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>((__int64)v72);
      v56 = &INgcFunctions::`vftable';
      goto LABEL_22;
    }
    goto LABEL_54;
  }
  if ( (unsigned int)MsaDevice_UseXTokenBasedSessionKey()
    && (*(unsigned int (__fastcall **)(CSingleIdentity *))(*(_QWORD *)this + 80LL))(this) != 1
    && (*(unsigned int (__fastcall **)(CSingleIdentity *))(*(_QWORD *)this + 80LL))(this) != 2
    && (*(unsigned int (__fastcall **)(CSingleIdentity *))(*(_QWORD *)this + 80LL))(this) != 3 )
  {
LABEL_54:
    ATL::CSimpleStringT<char,0>::operator=(v58, &v61);
    goto LABEL_88;
  }
  if ( (unsigned int)MsaDevice_UseXTokenBasedSessionKey() )
  {
    v65 = &CXboxSignatureProvider::`vftable';
    v26 = LiteCryptUtilities::XboxEncapsulateString(
            (LiteCryptUtilities *)&v56,
            (struct INgcFunctions *)&v65,
            (struct LiteCryptUtilities::IXboxSignatureProvider *)TimeSkew,
            v22,
            v72,
            v54);
  }
  else
  {
    v26 = LiteCryptUtilities::HmacEncapsulateString(&v56, UrlComponents.dwStructSize, v67, v25, TimeSkew, v22, v72);
  }
  ServiceToken = v26;
  if ( v26 < 0 )
  {
    LODWORD(v53) = v26;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\singleidentity.cpp",
      0x499u,
      L" Session key sign failure 0x%x",
      v53);
    if ( (*(unsigned int (__fastcall **)(CSingleIdentity *))(*(_QWORD *)this + 80LL))(this) == 1
      || (*(unsigned int (__fastcall **)(CSingleIdentity *))(*(_QWORD *)this + 80LL))(this) == 2
      || (v27 = 0, (*(unsigned int (__fastcall **)(CSingleIdentity *))(*(_QWORD *)this + 80LL))(this) == 3) )
    {
      v27 = 1;
    }
    v28 = 5;
    if ( (unsigned int)dword_1801C2080 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1801C2080, 0x400000000000LL) )
    {
      ServerBuildInfo = (void ***)CSingleIdentity::GetServerBuildInfo(this, &v62);
      LODWORD(v60) = 1;
      v65 = *ServerBuildInfo;
      if ( v27 == 1 )
      {
        v30 = (const unsigned __int16 **)(*(__int64 (__fastcall **)(CSingleIdentity *, __int64 *))(*(_QWORD *)this + 32LL))(
                                           this,
                                           &v71);
      }
      else
      {
        v30 = (const unsigned __int16 **)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                                           &v76,
                                           &cchOriginalDestLength);
        v28 = 9;
      }
      LODWORD(v60) = v28;
      v70 = *v30;
      if ( v27 == 1 )
      {
        RawPUID = (const unsigned __int16 **)CSingleIdentity::GetRawPUID(this, &v75);
        v32 = v28 | 0x10;
      }
      else
      {
        RawPUID = (const unsigned __int16 **)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                                               &v57,
                                               &cchOriginalDestLength);
        v32 = v28 | 0x20;
      }
      LODWORD(v60) = v32;
      v69 = *RawPUID;
      LODWORD(v64) = (*(__int64 (__fastcall **)(CSingleIdentity *))(*(_QWORD *)this + 56LL))(this);
      LODWORD(v63) = ServiceToken;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        v33,
        (__int64)byte_180199D65,
        v34,
        v35,
        (__int64)&v63,
        (__int64)&v64,
        &v69,
        &v70,
        (const unsigned __int16 **)&v65);
      if ( (v32 & 0x20) != 0 )
      {
        LOBYTE(v32) = v32 & 0xDF;
        ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v57);
      }
      if ( (v32 & 0x10) != 0 )
      {
        LOBYTE(v32) = v32 & 0xEF;
        ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v75);
      }
      if ( (v32 & 8) != 0 )
      {
        LOBYTE(v32) = v32 & 0xF7;
        ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v76);
      }
      if ( (v32 & 4) != 0 )
      {
        LOBYTE(v32) = v32 & 0xFB;
        ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v71);
      }
      if ( (v32 & 2) != 0 )
      {
        LOBYTE(v32) = v32 & 0xFD;
        ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v80);
      }
      if ( (v32 & 1) != 0 )
        ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v62);
    }
    if ( v27 == 1
      && ServiceToken != -2147024774
      && (unsigned int)ErrorHandlingUtilities::CollapseError(ServiceToken) != -2147024882 )
    {
      ServiceToken = -2147187452;
    }
    goto LABEL_47;
  }
  ATL::CSimpleStringT<char,0>::SetString(v58, *(_QWORD *)v72);
LABEL_88:
  Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>::~Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>((__int64)v72);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v59);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v61);
  CBytePtr::Empty((CBytePtr *)&v66);
  CPPCRLToken::~CPPCRLToken((CPPCRLToken *)&UrlComponents);
LABEL_89:
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v59);
  memset_0(&UrlComponents, 0, sizeof(UrlComponents));
  UrlComponents.dwStructSize = 104;
  UrlComponents.dwHostNameLength = 1;
  UrlComponents.dwUrlPathLength = 1;
  v36 = CClientConfigDataCacheManager::theConfigDataManager();
  ServiceURI = CClientConfigDataCacheManager::GetServiceURI(v36, L"PassportSHA1Auth", a7);
  ServiceToken = ServiceURI;
  if ( ServiceURI < 0 || !*((_DWORD *)*a7 - 4) )
  {
    LODWORD(v53) = ServiceURI;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\singleidentity.cpp",
      0x4BFu,
      L"Failed to get <PassportSHA1Auth> URL from the config file:  (0x%x)",
      v53);
    goto LABEL_112;
  }
  v38 = *(_DWORD *)(*(_QWORD *)CSingleIdentity::GetPassportSTSHost(this, &v62) - 16LL);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v62);
  v39 = *a7;
  if ( v38 <= 0 )
  {
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\singleidentity.cpp",
      0x4EAu,
      L"GetPassportSTSHost() returned empty host name. Using default URL %ls.",
      v39);
  }
  else
  {
    if ( !WinHttpCrackUrl(*a7, *((_DWORD *)v39 - 4), 0, &UrlComponents) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      ServiceToken = LastError;
      if ( LastError < 0 )
      {
        Telemetry::IfFailExit(
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\singleidentity.cpp",
          "CSingleIdentity::GetOneTimeCredentialEx",
          0x4C5u,
          LastError,
          "hr = HRESULT_FROM_WIN32(GetLastError())");
        goto LABEL_112;
      }
    }
    if ( !UrlComponents.lpszHostName )
    {
      ServiceToken = -2147418113;
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\singleidentity.cpp",
        "CSingleIdentity::GetOneTimeCredentialEx",
        0x4C7u,
        -2147418113,
        "urlComponents.lpszHostName != nullptr");
LABEL_112:
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v59);
      goto LABEL_113;
    }
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v59, UrlComponents.lpszHostName, UrlComponents.dwHostNameLength);
    PassportSTSHost = (_QWORD *)CSingleIdentity::GetPassportSTSHost(this, &v62);
    v42 = v59;
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Replace(
      a7,
      v59,
      *PassportSTSHost);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v62);
    v43 = (_QWORD *)CSingleIdentity::GetPassportSTSHost(this, &v62);
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\singleidentity.cpp",
      0x4CCu,
      L"Changed Host Name from %ls to: %ls.",
      v42,
      *v43);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v62);
    if ( UrlComponents.nPort != 443 )
    {
      v44 = CSingleIdentity::GetPassportSTSHost(this, &v62);
      OneBoxSSLPort = (unsigned __int16)GetOneBoxSSLPort(v44);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v62);
      if ( (_WORD)OneBoxSSLPort )
      {
        ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v57);
        ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v56);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
          &v57,
          L"%d",
          UrlComponents.nPort);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
          &v56,
          L"%d",
          OneBoxSSLPort);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Replace(
          a7,
          v57,
          v56);
        ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v56);
        v46 = &v57;
      }
      else
      {
        v47 = (_QWORD *)CSingleIdentity::GetPassportSTSHost(this, &v62);
        TracePrintW(
          2u,
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\singleidentity.cpp",
          0x4E1u,
          L"Could not get one box SSL port for host %ls",
          *v47);
        v46 = (const char **)&v62;
      }
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v46);
    }
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\singleidentity.cpp",
      0x4E6u,
      L"Final Web Auth URL is: %ls.",
      *a7);
  }
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v59);
  v90 = v91;
  v48 = *(_QWORD *)v58;
  ATL::CA2WEX<128>::Init(&v90, *(_QWORD *)v58, 65001);
  ATL::CSimpleStringT<unsigned short,0>::SetString(v71, v90);
  v50 = (int)v90;
  if ( v90 != v91 )
    free(v90);
  if ( (byte_1801C36C4 & 0x20) != 0 )
    McTemplateU0sqs_EventWriteTransfer(
      v50,
      v49,
      (unsigned int)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\singleidentity.cpp",
      1266,
      v48);
LABEL_113:
  v51 = ServiceToken;
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v58);
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v81);
  return v51;
}

```

## disassembly

```asm
0x18004908c  push    rbp
0x18004908e  push    rbx
0x18004908f  push    rsi
0x180049090  push    rdi
0x180049091  push    r12
0x180049093  push    r13
0x180049095  push    r14
0x180049097  push    r15
0x180049099  lea     rbp, [rsp-458h]
0x1800490a1  sub     rsp, 558h
0x1800490a8  mov     rax, cs:__security_cookie
0x1800490af  xor     rax, rsp
0x1800490b2  mov     [rbp+490h+var_50], rax
0x1800490b9  mov     rbx, r9
0x1800490bc  mov     rax, r8
0x1800490bf  mov     [rbp+490h+var_510], rax
0x1800490c3  mov     r12, rdx
0x1800490c6  mov     rdi, rcx
0x1800490c9  mov     r15, [rbp+490h+arg_30]
0x1800490d0  mov     rsi, [rbp+490h+arg_20]
0x1800490d7  mov     r14, [rbp+490h+arg_28]
0x1800490de  mov     rcx, [rbp+490h+arg_38]
0x1800490e5  mov     [rbp+490h+var_4B0], rcx
0x1800490e9  mov     rcx, [rbp+490h+arg_40]
0x1800490f0  mov     [rbp+490h+var_4B8], rcx
0x1800490f4  mov     rdx, [rbp+490h+arg_48]
0x1800490fb  mov     [rbp+490h+var_4E0], rdx
0x1800490ff  mov     r13, [rbp+490h+arg_50]
0x180049106  xor     ecx, ecx
0x180049108  mov     dword ptr [rbp+490h+var_508], ecx
0x18004910b  mov     [rsp+590h+var_530], ecx
0x18004910f  mov     [rsp+590h+var_540], r14
0x180049114  mov     [rsp+590h+var_548], rsi
0x180049119  mov     [rsp+590h+var_550], rbx
0x18004911e  mov     [rsp+590h+var_558], rax
0x180049123  mov     [rsp+590h+var_560], r12
0x180049128  lea     rax, aFlags0xLlxWcsz; "flags=0x%llx, wcszAppId=%ls, wcszTarget"...
0x18004912f  mov     [rsp+590h+var_568], rax; char **
0x180049134  lea     rax, aCsingleidentit_48; "CSingleIdentity::GetOneTimeCredentialEx"
0x18004913b  mov     [rsp+590h+var_570], rax
0x180049140  lea     r9, [rsp+590h+var_530]
0x180049145  mov     r8d, 3E8h
0x18004914b  lea     rdx, aOnecoreuapDsEx_24; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x180049152  lea     rcx, [rbp+490h+var_3C8]
0x180049159  call    ??0?$CTraceFuncW@J@@QEAA@PEBDKAEAJ0PEBGZZ; CTraceFuncW<long>::CTraceFuncW<long>(char const *,ulong,long &,char const *,ushort const *,...)
0x18004915e  nop
0x18004915f  lea     rcx, [rsp+590h+var_518]
0x180049164  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180049169  nop
0x18004916a  lea     rcx, [rsp+590h+var_518]
0x18004916f  call    ?Empty@?$CSimpleStringT@D$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<char,0>::Empty(void)
0x180049174  lea     rdx, aBver; "bver="
0x18004917b  lea     rcx, [rsp+590h+var_518]
0x180049180  call    ?AppendFormat@?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAAXPEBDZZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::AppendFormat(char const *,...)
0x180049185  call    ?theConfigDataManager@CClientConfigDataCacheManager@@SAAEAV1@XZ; CClientConfigDataCacheManager::theConfigDataManager(void)
0x18004918a  lea     rdx, [rsp+590h+var_528]
0x18004918f  call    ?GetBinaryVersion@CClientConfigDataCacheManager@@QEAA?AV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@XZ; CClientConfigDataCacheManager::GetBinaryVersion(void)
0x180049194  nop
0x180049195  mov     rdx, rax
0x180049198  lea     rcx, [rsp+590h+var_518]
0x18004919d  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXAEBV12@@Z; ATL::CSimpleStringT<char,0>::Append(ATL::CSimpleStringT<char,0> const &)
0x1800491a2  nop
0x1800491a3  lea     rcx, [rsp+590h+var_528]
0x1800491a8  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800491ad  xor     eax, eax
0x1800491af  test    r14, r14
0x1800491b2  jz      short loc_180049219
0x1800491b4  cmp     [r14], ax
0x1800491b8  jz      short loc_180049219
0x1800491ba  lea     rdx, asc_18015EB10; "&"
0x1800491c1  lea     rcx, [rsp+590h+var_518]
0x1800491c6  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBD@Z; ATL::CSimpleStringT<char,0>::Append(char const *)
0x1800491cb  lea     rax, [rbp+490h+var_398]
0x1800491d2  mov     [rbp+490h+Block], rax
0x1800491d9  mov     r8d, 0FDE9h
0x1800491df  mov     rdx, r14
0x1800491e2  lea     rcx, [rbp+490h+Block]
0x1800491e9  call    ?Init@?$CW2AEX@$0IA@@ATL@@AEAAXPEBGI@Z; ATL::CW2AEX<128>::Init(ushort const *,uint)
0x1800491ee  nop
0x1800491ef  mov     rdx, [rbp+490h+Block]
0x1800491f6  lea     rcx, [rsp+590h+var_518]
0x1800491fb  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBD@Z; ATL::CSimpleStringT<char,0>::Append(char const *)
0x180049200  nop
0x180049201  mov     rcx, [rbp+490h+Block]; Block
0x180049208  lea     rax, [rbp+490h+var_398]
0x18004920f  cmp     rcx, rax
0x180049212  jz      short loc_180049219
0x180049214  call    free
0x180049219  xor     r14d, r14d
0x18004921c  test    rbx, rbx
0x18004921f  jz      loc_1800492B3
0x180049225  cmp     [rbx], r14w
0x180049229  jz      loc_1800492B3
0x18004922f  lea     rcx, [rsp+590h+var_520]
0x180049234  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180049239  nop
0x18004923a  lea     rax, [rbp+490h+var_308]
0x180049241  mov     [rbp+490h+var_310], rax
0x180049248  mov     r8d, 0FDE9h
0x18004924e  mov     rdx, rbx
0x180049251  lea     rcx, [rbp+490h+var_310]
0x180049258  call    ?Init@?$CW2AEX@$0IA@@ATL@@AEAAXPEBGI@Z; ATL::CW2AEX<128>::Init(ushort const *,uint)
0x18004925d  nop
0x18004925e  mov     rdx, [rbp+490h+var_310]
0x180049265  lea     rcx, [rsp+590h+var_520]
0x18004926a  call    ?SetString@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBD@Z; ATL::CSimpleStringT<char,0>::SetString(char const *)
0x18004926f  nop
0x180049270  mov     rcx, [rbp+490h+var_310]; Block
0x180049277  lea     rax, [rbp+490h+var_308]
0x18004927e  cmp     rcx, rax
0x180049281  jz      short loc_180049288
0x180049283  call    free
0x180049288  lea     rcx, [rsp+590h+var_520]
0x18004928d  call    ?UrlEscapeString@@YAXAEAV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@@Z; UrlEscapeString(ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> &)
0x180049292  mov     r8, [rsp+590h+var_520]
0x180049297  lea     rdx, aRuS; "&ru=%s"
0x18004929e  lea     rcx, [rsp+590h+var_518]
0x1800492a3  call    ?AppendFormat@?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAAXPEBDZZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::AppendFormat(char const *,...)
0x1800492a8  nop
0x1800492a9  lea     rcx, [rsp+590h+var_520]
0x1800492ae  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800492b3  test    rsi, rsi
0x1800492b6  jz      loc_18004934A
0x1800492bc  cmp     [rsi], r14w
0x1800492c0  jz      loc_18004934A
0x1800492c6  lea     rcx, [rsp+590h+var_520]
0x1800492cb  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800492d0  nop
0x1800492d1  lea     rax, [rbp+490h+var_278]
0x1800492d8  mov     [rbp+490h+var_280], rax
0x1800492df  mov     r8d, 0FDE9h
0x1800492e5  mov     rdx, rsi
0x1800492e8  lea     rcx, [rbp+490h+var_280]
0x1800492ef  call    ?Init@?$CW2AEX@$0IA@@ATL@@AEAAXPEBGI@Z; ATL::CW2AEX<128>::Init(ushort const *,uint)
0x1800492f4  nop
0x1800492f5  mov     rdx, [rbp+490h+var_280]
0x1800492fc  lea     rcx, [rsp+590h+var_520]
0x180049301  call    ?SetString@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBD@Z; ATL::CSimpleStringT<char,0>::SetString(char const *)
0x180049306  nop
0x180049307  mov     rcx, [rbp+490h+var_280]; Block
0x18004930e  lea     rax, [rbp+490h+var_278]
0x180049315  cmp     rcx, rax
0x180049318  jz      short loc_18004931F
0x18004931a  call    free
0x18004931f  lea     rcx, [rsp+590h+var_520]
0x180049324  call    ?UrlEscapeString@@YAXAEAV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@@Z; UrlEscapeString(ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> &)
0x180049329  mov     r8, [rsp+590h+var_520]
0x18004932e  lea     rdx, aPlS; "&pl=%s"
0x180049335  lea     rcx, [rsp+590h+var_518]
0x18004933a  call    ?AppendFormat@?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAAXPEBDZZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::AppendFormat(char const *,...)
0x18004933f  nop
0x180049340  lea     rcx, [rsp+590h+var_520]
0x180049345  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18004934a  mov     rdx, [rbp+490h+var_510]
0x18004934e  lea     rcx, [rsp+590h+var_528]
0x180049353  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(ushort const *)
0x180049358  nop
0x180049359  lea     rcx, [rsp+590h+var_528]
0x18004935e  call    ?UrlEscapeString@@YAXAEAV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@@Z; UrlEscapeString(ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> &)
0x180049363  mov     r8, [rsp+590h+var_528]
0x180049368  lea     rdx, aAppidS; "&appid=%s"
0x18004936f  lea     rcx, [rsp+590h+var_518]
0x180049374  call    ?AppendFormat@?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAAXPEBDZZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::AppendFormat(char const *,...)
0x180049379  nop
0x18004937a  lea     rcx, [rsp+590h+var_528]
0x18004937f  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180049384  mov     r14d, 2
0x18004938a  test    r14b, r12b
0x18004938d  jz      short loc_1800493CC
0x18004938f  lea     rdx, a1_0; "1"
0x180049396  lea     rcx, [rsp+590h+var_528]
0x18004939b  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@PEBD@Z; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(char const *)
0x1800493a0  nop
0x1800493a1  lea     rcx, [rsp+590h+var_528]
0x1800493a6  call    ?UrlEscapeString@@YAXAEAV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@@Z; UrlEscapeString(ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> &)
0x1800493ab  mov     r8, [rsp+590h+var_528]
0x1800493b0  lea     rdx, aLoginoptionsS; "&loginoptions=%s"
0x1800493b7  lea     rcx, [rsp+590h+var_518]
0x1800493bc  call    ?AppendFormat@?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAAXPEBDZZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::AppendFormat(char const *,...)
0x1800493c1  nop
0x1800493c2  lea     rcx, [rsp+590h+var_528]
0x1800493c7  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800493cc  test    r12b, 1
0x1800493d0  jz      short loc_18004941A
0x1800493d2  mov     rax, [rdi]
0x1800493d5  lea     rdx, [rsp+590h+var_528]
0x1800493da  mov     rcx, rdi
0x1800493dd  mov     rax, [rax+20h]
0x1800493e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800493e6  nop
0x1800493e7  lea     rcx, [rsp+590h+var_528]
0x1800493ec  call    ?UrlEscapeString@@YAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; UrlEscapeString(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x1800493f1  mov     r8, [rsp+590h+var_528]
0x1800493f6  lea     rdx, aLoginS; "&login=%S"
0x1800493fd  lea     rcx, [rsp+590h+var_518]
0x180049402  call    ?AppendFormat@?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAAXPEBDZZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::AppendFormat(char const *,...)
0x180049407  nop
0x180049408  lea     rcx, [rsp+590h+var_528]
0x18004940d  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180049412  xor     r12d, r12d
0x180049415  jmp     loc_180049B73
0x18004941a  lea     rcx, [rbp+490h+UrlComponents]; this
0x18004941e  call    ??0CPPCRLToken@@QEAA@XZ; CPPCRLToken::CPPCRLToken(void)
0x180049423  nop
0x180049424  xor     r12d, r12d
0x180049427  mov     [rbp+490h+var_4D0], r12
0x18004942b  mov     [rbp+490h+var_4D8], r12d
0x18004942f  mov     [rbp+490h+var_4C8], r12d
0x180049433  lea     rcx, [rbp+490h+var_500]
0x180049437  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18004943c  nop
0x18004943d  lea     rcx, [rbp+490h+var_510]
0x180049441  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180049446  nop
0x180049447  lea     r8, [rbp+490h+UrlComponents]; struct CPPCRLToken *
0x18004944b  lea     rdx, aHttpPassportNe_2; "http://Passport.NET/tb"
0x180049452  mov     rcx, rdi; this
0x180049455  call    ?GetServiceToken@CSingleIdentity@@QEAAJPEBGAEAVCPPCRLToken@@@Z; CSingleIdentity::GetServiceToken(ushort const *,CPPCRLToken &)
0x18004945a  mov     [rsp+590h+var_530], eax
0x18004945e  test    eax, eax
0x180049460  jns     short loc_1800494BF
0x180049462  lea     rax, aSucceededHr; "SUCCEEDED(hr)"
0x180049469  mov     r8d, 434h; unsigned int
0x18004946f  mov     r9d, 80048861h; int
0x180049475  mov     [rsp+590h+var_570], rax; char *
0x18004947a  mov     [rsp+590h+var_530], r9d
0x18004947f  lea     rdx, aCsingleidentit_48; "CSingleIdentity::GetOneTimeCredentialEx"
0x180049486  lea     rcx, aOnecoreuapDsEx_24; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18004948d  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x180049492  nop
0x180049493  lea     rcx, [rbp+490h+var_510]
0x180049497  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18004949c  nop
0x18004949d  lea     rcx, [rbp+490h+var_500]
0x1800494a1  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800494a6  nop
0x1800494a7  lea     rcx, [rbp+490h+var_4D8]; this
0x1800494ab  call    ?Empty@CBytePtr@@QEAAXXZ; CBytePtr::Empty(void)
0x1800494b0  nop
0x1800494b1  lea     rcx, [rbp+490h+UrlComponents]; this
0x1800494b5  call    ??1CPPCRLToken@@QEAA@XZ; CPPCRLToken::~CPPCRLToken(void)
0x1800494ba  jmp     loc_180049E9E
0x1800494bf  lea     rdx, [rsp+590h+var_528]
0x1800494c4  lea     rcx, [rbp+490h+UrlComponents]
0x1800494c8  call    ?GetToken@CPPCRLToken@@QEBA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@XZ; CPPCRLToken::GetToken(void)
0x1800494cd  nop
0x1800494ce  mov     rdx, [rax]
0x1800494d1  lea     rax, [rbp+490h+var_1E8]
0x1800494d8  mov     [rbp+490h+var_1F0], rax
0x1800494df  mov     r8d, 0FDE9h
0x1800494e5  lea     rcx, [rbp+490h+var_1F0]
0x1800494ec  call    ?Init@?$CW2AEX@$0IA@@ATL@@AEAAXPEBGI@Z; ATL::CW2AEX<128>::Init(ushort const *,uint)
0x1800494f1  nop
0x1800494f2  mov     rdx, [rbp+490h+var_1F0]
0x1800494f9  lea     rcx, [rbp+490h+var_500]
0x1800494fd  call    ?SetString@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBD@Z; ATL::CSimpleStringT<char,0>::SetString(char const *)
0x180049502  nop
0x180049503  mov     rcx, [rbp+490h+var_1F0]; Block
0x18004950a  lea     rax, [rbp+490h+var_1E8]
0x180049511  cmp     rcx, rax
0x180049514  jz      short loc_18004951C
0x180049516  call    free
0x18004951b  nop
0x18004951c  lea     rcx, [rsp+590h+var_528]
0x180049521  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180049526  mov     rax, [rbp+490h+var_500]
0x18004952a  cmp     [rax-10h], r12d
0x18004952e  jnz     short loc_180049542
0x180049530  lea     rax, aStrtokenIsempt; "!strToken.IsEmpty()"
0x180049537  mov     r8d, 43Ah
0x18004953d  jmp     loc_18004946F
0x180049542  lea     rdx, [rbp+490h+var_500]
0x180049546  lea     rcx, [rbp+490h+var_510]
0x18004954a  call    ??4?$CSimpleStringT@D$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<char,0>::operator=(ATL::CSimpleStringT<char,0> const &)
0x18004954f  lea     rcx, [rbp+490h+var_510]
0x180049553  call    ?UrlEscapeString@@YAXAEAV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@@Z; UrlEscapeString(ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> &)
0x180049558  mov     r8, [rbp+490h+var_510]
0x18004955c  lea     rdx, aDaHs; "&da=%hs"
0x180049563  lea     rcx, [rsp+590h+var_518]
0x180049568  call    ?AppendFormat@?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAAXPEBDZZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::AppendFormat(char const *,...)
0x18004956d  test    r13, r13
0x180049570  jz      short loc_18004957A
0x180049572  mov     rax, [rbp+490h+UrlComponents.lpszPassword]
0x180049576  mov     [r13+0], rax
0x18004957a  mov     rcx, rdi; this
0x18004957d  call    ?GetIsLinkedHandle@CSingleIdentity@@QEAA_NXZ; CSingleIdentity::GetIsLinkedHandle(void)
0x180049582  test    al, al
0x180049584  jz      loc_1800496F8
0x18004958a  lea     rcx, [rbp+490h+var_508]
0x18004958e  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180049593  nop
0x180049594  lea     rcx, [rbp+490h+var_4E8]
0x180049598  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18004959d  nop
0x18004959e  lea     rcx, [rsp+590h+var_520]
0x1800495a3  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800495a8  nop
0x1800495a9  lea     rcx, [rbp+490h+var_4F0]
0x1800495ad  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800495b2  nop
  ... truncated ...
```
