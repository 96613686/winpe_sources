# CSLSClient::GetResponse(CSLSRequest const &,tagSlsFlags,CCallerIdentity const *,void *,CSLSResponse *,bool *,CSLSClient::RevisionCheck *)

- ea: `0x1801b17b8`
- end: `0x1801b1f95`
- name: `?GetResponse@CSLSClient@@AEAAJAEBVCSLSRequest@@W4tagSlsFlags@@PEBVCCallerIdentity@@PEAXPEAVCSLSResponse@@PEA_NPEAURevisionCheck@1@@Z`
- size: `2013`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1801b1108`

## callees

- `0x180014964`
- `0x180038d00`
- `0x180113ae8`
- `0x1801167bc`
- `0x18012b618`
- `0x18012bed4`
- `0x18012d9d4`
- `0x18012dd74`
- `0x1801affd0`
- `0x1801b00dc`
- `0x1801b17b8`
- `0x1801b1f9c`
- `0x1801b2230`
- `0x1801b2694`
- `0x1801b28d8`
- `0x1801b3694`
- `0x1801b430c`
- `0x1801b43ec`
- `0x1801b4920`
- `0x1801e6a18`
- `0x180238960`
- `0x180240d40`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1801b1c75`
- `OLEAUT32!__imp_SysAllocString` at `0x1801b1c75`
- `OLEAUT32!__imp_SysFreeString` at `0x1801b1c21`
- `OLEAUT32!__imp_SysFreeString` at `0x1801b1cbe`
- `OLEAUT32!__imp_SysFreeString` at `0x1801b1d46`
- `OLEAUT32!__imp_SysFreeString` at `0x1801b1eb4`
- `OLEAUT32!__imp_SysFreeString` at `0x1801b1ecd`
- `OLEAUT32!__imp_SysFreeString` at `0x1801b1c21`
- `OLEAUT32!__imp_SysFreeString` at `0x1801b1cbe`
- `OLEAUT32!__imp_SysFreeString` at `0x1801b1d46`
- `OLEAUT32!__imp_SysFreeString` at `0x1801b1eb4`
- `OLEAUT32!__imp_SysFreeString` at `0x1801b1ecd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1801b193c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1801b1e44`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1801b1e59`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1801b193c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1801b1e44`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1801b1e59`

## string_xrefs

- `0x1801b186c`: `Software\Microsoft\Windows\CurrentVersion\WindowsUpdate\Test`
- `0x1801b19c2`: `Software\Microsoft\Windows\CurrentVersion\WindowsUpdate\Test`
- `0x1801b1a7f`: `Software\Microsoft\Windows\CurrentVersion\WindowsUpdate\Test`
- `0x1801b1a78`: `SLSNoCache`
- `0x1801b1dae`: `ResponsePayloadFilePath`
- `0x1801b1d56`: `Software\Microsoft\Windows\CurrentVersion\WindowsUpdate\Test\SLS`
- `0x1801b1b9d`: `SetCacheData`
- `0x1801b1c4e`: `ExtractEnvIDRevisionID default cache revisionId %d.`
- `0x1801b1a91`: `NoCache override set.`
- `0x1801b1e7a`: `Read local SLS override xml`
- `0x1801b19d4`: `ExpireCache override set.`
- `0x1801b1a35`: `fIsCacheHit[%ls] fContentExpired[%ls] expiration set.`
- `0x1801b1914`: `Get response for service %ws - forceExpire[%ws] asyncRefreshOnExpiry[%ws] (cV = %hs)`
- `0x1801b19bb`: `SlsExpireCache`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSLSClient::GetResponse(
        char *a1,
        __int64 a2,
        char a3,
        struct CCallerIdentity *a4,
        void *a5,
        CSLSResponse *a6,
        _BYTE *a7,
        __int64 a8)
{
  bool v11; // r14
  bool v12; // bl
  __int64 v13; // rcx
  int v14; // eax
  bool v15; // di
  int v16; // r12d
  __int64 v17; // rax
  const wchar_t *v18; // rcx
  const wchar_t *v19; // rdx
  int v20; // eax
  int v21; // esi
  bool v22; // bl
  __int64 v23; // rcx
  DWORD dwHighDateTime; // r15d
  char v25; // si
  const wchar_t *v26; // rcx
  const wchar_t *v27; // rax
  struct sls::RefreshManager *Instance; // rax
  const char *v29; // rsi
  int v30; // eax
  GUID *v31; // r12
  int UrlContent; // esi
  CSLSResponse *v33; // rbx
  void *v34; // r14
  int v35; // eax
  BSTR v36; // rax
  int v37; // ecx
  __int64 v38; // rcx
  OLECHAR *v39; // rbx
  void *v40; // rdi
  const wchar_t *v41; // rax
  struct AADDeviceDataBoundaryInfo *v43; // [rsp+30h] [rbp-D0h]
  __int64 v44; // [rsp+38h] [rbp-C8h]
  bool v45; // [rsp+50h] [rbp-B0h] BYREF
  CSLSResponse *v46; // [rsp+58h] [rbp-A8h]
  void *lpMem[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v48; // [rsp+70h] [rbp-90h]
  CSLSClient *v49; // [rsp+80h] [rbp-80h]
  struct CCallerIdentity *v50; // [rsp+88h] [rbp-78h]
  _BYTE *v51; // [rsp+90h] [rbp-70h]
  char *v52; // [rsp+98h] [rbp-68h]
  void *v53; // [rsp+A0h] [rbp-60h]
  struct _FILETIME v54[8]; // [rsp+B0h] [rbp-50h] BYREF
  _OWORD v55[5]; // [rsp+F0h] [rbp-10h] BYREF
  wchar_t v56[2]; // [rsp+140h] [rbp+40h] BYREF
  OLECHAR *psz; // [rsp+148h] [rbp+48h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+150h] [rbp+50h] BYREF
  GUID rguid; // [rsp+160h] [rbp+60h] BYREF
  wchar_t v60[264]; // [rsp+170h] [rbp+70h] BYREF

  v50 = a4;
  psz = (OLECHAR *)a2;
  v49 = (CSLSClient *)a1;
  v53 = a5;
  v46 = a6;
  v51 = a7;
  v11 = 0;
  SystemTimeAsFileTime = 0;
  v45 = 0;
  memset(v54, 0, sizeof(v54));
  *a7 = 0;
  v12 = 0;
  if ( (unsigned int)AreTestKeysAllowed(1) )
  {
    v14 = RegQueryDwordValueWithDefaultAndRangeCheck(
            v13,
            L"Software\\Microsoft\\Windows\\CurrentVersion\\WindowsUpdate\\Test",
            L"SLSBlockAsyncRefreshOnExpire",
            0,
            0,
            -1);
    v12 = v14 != 0;
    if ( v14 )
      WUTrace(0, 0, 4, 4, 0, L"SLSBlockAsyncRefreshOnExpire override set.");
  }
  rguid = *(GUID *)a2;
  v15 = a3 & 1;
  if ( !v12 )
    v11 = (a3 & 2) != 0;
  v16 = a3 & 8;
  LOBYTE(v56[0]) = v16 != 0;
  v17 = Trace::GuidToString::GuidToString((Trace::GuidToString *)v55, &rguid);
  v52 = a1 + 88;
  v18 = L"False";
  v19 = L"False";
  if ( v11 )
    v19 = L"True";
  if ( v15 )
    v18 = L"True";
  WUTrace(
    0,
    0,
    4,
    4,
    0,
    L"Get response for service %ws - forceExpire[%ws] asyncRefreshOnExpiry[%ws] (cV = %hs)",
    v17,
    v18,
    v19,
    a1 + 88);
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v20 = SlsDatastoreLookup(
          *(struct ISusDatastore **)a1,
          &rguid,
          *(const wchar_t **)(a2 + 32),
          &SystemTimeAsFileTime,
          (struct tagDSSLSData *)v54,
          &v45);
  v21 = v20;
  if ( v20 >= 0 || (unsigned int)(v20 + 2145091552) <= 9 )
  {
    v22 = v45;
  }
  else
  {
    v22 = v45;
    if ( v20 != -2145091577 )
      v22 = 1;
  }
  if ( !v22
    && (unsigned int)AreTestKeysAllowed(1)
    && (unsigned int)RegQueryDwordValueWithDefaultAndRangeCheck(
                       v23,
                       L"Software\\Microsoft\\Windows\\CurrentVersion\\WindowsUpdate\\Test",
                       L"SlsExpireCache",
                       0,
                       0,
                       -1) )
  {
    WUTrace(0, 0, 4, 4, 0, L"ExpireCache override set.");
    v22 = 1;
  }
  dwHighDateTime = v54[5].dwHighDateTime;
  if ( v21 < 0 || (v25 = 1, !v54[5].dwHighDateTime) )
    v25 = 0;
  v26 = L"False";
  v27 = L"False";
  if ( v22 )
    v27 = L"True";
  if ( v25 )
    v26 = L"True";
  WUTrace(0, 0, 4, 5, 0, L"fIsCacheHit[%ls] fContentExpired[%ls] expiration set.", v26, v27);
  if ( !v15
    && (unsigned int)AreTestKeysAllowed(1)
    && (unsigned int)RegQueryDwordValueWithDefaultAndRangeCheck(
                       0,
                       L"Software\\Microsoft\\Windows\\CurrentVersion\\WindowsUpdate\\Test",
                       L"SLSNoCache",
                       0,
                       0,
                       -1) )
  {
    WUTrace(0, 0, 4, 4, 0, L"NoCache override set.");
    v15 = 1;
  }
  if ( v25 )
  {
    if ( !v16 && (v22 || v15) && v11 )
    {
      Instance = sls::RefreshManager::GetInstance();
      v29 = (char *)v49 + 88;
      v30 = sls::RefreshManager::EnqueueRefresh(
              Instance,
              &rguid,
              v50,
              *(struct ISusDatastore **)v49,
              v15,
              (const char *)v49 + 88,
              *((const struct AADDeviceDataBoundaryInfo **)v49 + 28));
      v31 = (GUID *)psz;
      if ( v30 != -2145124333 )
      {
        *(GUID *)lpMem = rguid;
        sls::telemetry::DiscoveryEvent::SendRequestQueuedEvent(
          (struct _GUID *)lpMem,
          *((const wchar_t **)psz + 4),
          v30,
          v56[0],
          v54[3],
          v29);
      }
    }
    else
    {
      v31 = (GUID *)psz;
    }
    UrlContent = CSLSResponse::PopulateFromDataStore(v46, (const struct tagDSSLSData *)v54);
    if ( UrlContent < 0 )
    {
      WUTrace(0, 0, 4, 1, UrlContent, L"PopulateFromDataStore");
      v33 = v46;
      goto LABEL_76;
    }
    if ( (int)CSLSClient::SetCacheData(v49, (const struct tagDSSLSData *)v54) < 0 )
      WUTrace(0, 0, 4, 1, UrlContent, L"SetCacheData");
    if ( !v22 && !v15 )
      goto LABEL_47;
    if ( v11 )
    {
      v34 = 0;
      if ( IsWithinExpiredValidityPeriod(&SystemTimeAsFileTime, &v54[3], dwHighDateTime, *(unsigned __int8 **)&v54[6]) )
      {
LABEL_47:
        *v51 = 1;
        v33 = v46;
        goto LABEL_76;
      }
      dwHighDateTime = v54[5].dwHighDateTime;
    }
    else
    {
      v34 = 0;
    }
    if ( v22 || v15 )
    {
      *(_DWORD *)v56 = 0;
      psz = 0;
      SysFreeString(0);
      psz = 0;
      v35 = ExtractEnvIDRevisionID(dwHighDateTime, *(const char **)&v54[6], &psz, (unsigned int *)v56);
      if ( v35 >= 0 )
      {
        v36 = SysAllocString(psz);
        *(_QWORD *)a8 = v36;
        v37 = *(_DWORD *)v56;
        *(_DWORD *)(a8 + 8) = *(_DWORD *)v56;
        *(_BYTE *)(a8 + 16) = 1;
        LODWORD(v44) = v37;
        WUTrace(0, 0, 4, 4, 0, L"Revision Check is on with Environment ID [%ws] Revision [%d]...", v36, v44);
      }
      else
      {
        *(_BYTE *)(a8 + 16) = 0;
        LODWORD(v43) = *(_DWORD *)v56;
        WUTrace(0, 0, 4, 3, v35, L"ExtractEnvIDRevisionID default cache revisionId %d.", v43);
      }
      SysFreeString(psz);
    }
  }
  else
  {
    v31 = (GUID *)psz;
    v34 = 0;
  }
  if ( v54[7] )
    WUTrace(0, 0, 4, 4, 0, L"Retrieving SLS response from server using ETAG %ws...", *(_QWORD *)&v54[7]);
  else
    WUTrace(0, 0, 4, 4, 0, L"Retrieving SLS response from server...");
  if ( !(unsigned int)AreTestKeysAllowed(1) )
    goto LABEL_75;
  memset(v60, 0, 520);
  SysFreeString(0);
  psz = 0;
  if ( CSusBSTR::Append(
         (CSusBSTR *)&psz,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\WindowsUpdate\\Test\\SLS",
         0x40u) < 0
    || (v56[0] = 92, CSusBSTR::Append((CSusBSTR *)&psz, v56, 1u) < 0)
    || (int)CSusBSTR::Append((CSusBSTR *)&psz, &rguid) < 0 )
  {
    v39 = psz;
    goto LABEL_74;
  }
  v39 = psz;
  if ( (int)RegQueryStringValue(v38, psz, L"ResponsePayloadFilePath", v60, 260) < 0 )
  {
LABEL_74:
    SysFreeString(v39);
LABEL_75:
    LOBYTE(v56[0]) = 0;
    v33 = v46;
    UrlContent = CSLSDownloader::GetUrlContent((CSLSDownloader *)v56, v53, v31, v50, v46, v52);
    goto LABEL_76;
  }
  WUTrace(0, 0, 4, 4, 0, L"local from %ws", v60);
  lpMem[0] = (void *)&CSafeBuffer<unsigned char>::`vftable';
  lpMem[1] = 0;
  v48 = 0;
  v40 = 0;
  memset(v55, 0, 0x40u);
  UrlContent = ReadFileToSafeByteBuffer(v60);
  if ( UrlContent < 0 )
  {
    v34 = lpMem[1];
LABEL_69:
    WUTrace(0, 0, 4, 1, UrlContent, L"Read local SLS override xml");
    goto LABEL_70;
  }
  v40 = lpMem[1];
  v55[0] = *v31;
  GetSystemTimeAsFileTime((LPFILETIME)&v55[1] + 1);
  *(_QWORD *)&v55[3] = v40;
  HIDWORD(v55[2]) = HIDWORD(v48);
  GetSystemTimeAsFileTime((LPFILETIME)&v55[2]);
  UrlContent = CSLSResponse::PopulateFromDataStore(v46, (const struct tagDSSLSData *)v55);
  if ( UrlContent < 0 )
    goto LABEL_69;
LABEL_70:
  if ( v40 )
    SusFree(v40);
  SusFree(v34);
  SysFreeString(v39);
  v33 = v46;
LABEL_76:
  CSLSClient::FreeSLSData((struct tagDSSLSData *)v54);
  if ( UrlContent >= 0 )
  {
    v41 = L"was not";
    if ( *((_BYTE *)v33 + 28) )
      v41 = L"was";
    WUTrace(0, 0, 4, 5, 0, L"GetResponse succeeded. The file %ws downloaded.", v41);
  }
  else
  {
    WUTrace("CSLSClient::GetResponse", 660, 4, 1, UrlContent, L"Method failed");
  }
  return (unsigned int)UrlContent;
}

```

## disassembly

```asm
0x1801b17b8  push    rbp
0x1801b17ba  push    rbx
0x1801b17bb  push    rsi
0x1801b17bc  push    rdi
0x1801b17bd  push    r12
0x1801b17bf  push    r13
0x1801b17c1  push    r14
0x1801b17c3  push    r15
0x1801b17c5  lea     rbp, [rsp-298h]
0x1801b17cd  sub     rsp, 398h
0x1801b17d4  mov     rax, cs:__security_cookie
0x1801b17db  xor     rax, rsp
0x1801b17de  mov     [rbp+2D0h+var_50], rax
0x1801b17e5  mov     [rbp+2D0h+var_348], r9
0x1801b17e9  mov     r12d, r8d
0x1801b17ec  mov     rsi, rdx
0x1801b17ef  mov     [rbp+2D0h+psz], rdx
0x1801b17f3  mov     r15, rcx
0x1801b17f6  mov     [rbp+2D0h+var_350], rcx
0x1801b17fa  mov     r13, [rbp+2D0h+arg_38]
0x1801b1801  mov     rax, [rbp+2D0h+arg_20]
0x1801b1808  mov     [rbp+2D0h+var_330], rax
0x1801b180c  mov     rax, [rbp+2D0h+arg_28]
0x1801b1813  mov     [rsp+3D0h+var_378], rax
0x1801b1818  mov     rbx, [rbp+2D0h+arg_30]
0x1801b181f  mov     [rbp+2D0h+var_340], rbx
0x1801b1823  xor     r14d, r14d
0x1801b1826  mov     qword ptr [rbp+2D0h+SystemTimeAsFileTime.dwLowDateTime], r14
0x1801b182a  mov     [rsp+3D0h+var_380], r14b
0x1801b182f  xor     edx, edx; Val
0x1801b1831  lea     r8d, [r14+40h]; Size
0x1801b1835  lea     rcx, [rbp+2D0h+var_320]; void *
0x1801b1839  call    memset
0x1801b183e  mov     [rbx], r14b
0x1801b1841  mov     bl, r14b
0x1801b1844  lea     ecx, [r14+1]; bool
0x1801b1848  call    ?AreTestKeysAllowed@@YAH_N@Z; AreTestKeysAllowed(bool)
0x1801b184d  lea     edi, [r14+4]
0x1801b1851  test    eax, eax
0x1801b1853  jz      short loc_1801B18A1
0x1801b1855  mov     dword ptr [rsp+3D0h+var_3A8], 0FFFFFFFFh
0x1801b185d  mov     [rsp+3D0h+var_3B0.dwLowDateTime], r14d
0x1801b1862  xor     r9d, r9d
0x1801b1865  lea     r8, ?c_szRegSLSBlockAsyncRefreshOnExpiry@@3QB_WB; "SLSBlockAsyncRefreshOnExpire"
0x1801b186c  lea     rdx, ?c_szRegWUTest@@3QB_WB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1801b1873  call    ?RegQueryDwordValueWithDefaultAndRangeCheck@@YAKPEAUHKEY__@@PEB_W1KKKW4RegistryHiveType@@@Z; RegQueryDwordValueWithDefaultAndRangeCheck(HKEY__ *,wchar_t const *,wchar_t const *,ulong,ulong,ulong,RegistryHiveType)
0x1801b1878  test    eax, eax
0x1801b187a  setnz   bl
0x1801b187d  test    eax, eax
0x1801b187f  jz      short loc_1801B18A1
0x1801b1881  lea     rax, aSlsblockasyncr; "SLSBlockAsyncRefreshOnExpire override s"...
0x1801b1888  mov     [rsp+3D0h+var_3A8], rax
0x1801b188d  mov     qword ptr [rsp+3D0h+var_3B0.dwLowDateTime], r14
0x1801b1892  mov     r9d, edi
0x1801b1895  mov     r8d, edi
0x1801b1898  xor     edx, edx
0x1801b189a  xor     ecx, ecx
0x1801b189c  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1801b18a1  movups  xmm0, xmmword ptr [rsi]
0x1801b18a4  movdqu  xmmword ptr [rbp+2D0h+rguid.Data1], xmm0
0x1801b18a9  mov     dil, r12b
0x1801b18ac  mov     eax, 1
0x1801b18b1  and     dil, al
0x1801b18b4  test    bl, bl
0x1801b18b6  jnz     short loc_1801B18C1
0x1801b18b8  mov     r14d, r12d
0x1801b18bb  shr     r14d, 1
0x1801b18be  and     r14b, al
0x1801b18c1  and     r12d, 8
0x1801b18c5  setnz   byte ptr [rbp+2D0h+var_290]
0x1801b18c9  lea     rdx, [rbp+2D0h+rguid]; struct _GUID *
0x1801b18cd  lea     rcx, [rbp+2D0h+var_2E0]; this
0x1801b18d1  call    ??0GuidToString@Trace@@QEAA@AEBU_GUID@@@Z; Trace::GuidToString::GuidToString(_GUID const &)
0x1801b18d6  lea     r8, [r15+58h]
0x1801b18da  mov     [rbp+2D0h+var_338], r8
0x1801b18de  lea     r10, aTrue_8; "True"
0x1801b18e5  lea     rcx, aFalse_6; "False"
0x1801b18ec  mov     rdx, rcx
0x1801b18ef  xor     r9d, r9d
0x1801b18f2  test    r14b, r14b
0x1801b18f5  cmovnz  rdx, r10
0x1801b18f9  test    dil, dil
0x1801b18fc  cmovnz  rcx, r10
0x1801b1900  mov     [rsp+3D0h+var_388], r8
0x1801b1905  mov     [rsp+3D0h+var_390], rdx
0x1801b190a  mov     [rsp+3D0h+var_398], rcx
0x1801b190f  mov     [rsp+3D0h+var_3A0], rax
0x1801b1914  lea     rax, aGetResponseFor; "Get response for service %ws - forceExp"...
0x1801b191b  mov     [rsp+3D0h+var_3A8], rax
0x1801b1920  mov     qword ptr [rsp+3D0h+var_3B0.dwLowDateTime], r9
0x1801b1925  lea     eax, [r9+4]
0x1801b1929  mov     r9d, eax
0x1801b192c  mov     r8d, eax
0x1801b192f  xor     edx, edx
0x1801b1931  xor     ecx, ecx
0x1801b1933  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1801b1938  lea     rcx, [rbp+2D0h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1801b193c  call    cs:__imp_GetSystemTimeAsFileTime
0x1801b1942  lea     rax, [rsp+3D0h+var_380]
0x1801b1947  mov     [rsp+3D0h+var_3A8], rax; bool *
0x1801b194c  lea     rax, [rbp+2D0h+var_320]
0x1801b1950  mov     qword ptr [rsp+3D0h+var_3B0.dwLowDateTime], rax; struct tagDSSLSData *
0x1801b1955  lea     r9, [rbp+2D0h+SystemTimeAsFileTime]; struct _FILETIME *
0x1801b1959  mov     r8, [rsi+20h]; wchar_t *
0x1801b195d  lea     rdx, [rbp+2D0h+rguid]; struct _GUID *
0x1801b1961  mov     rcx, [r15]; struct ISusDatastore *
0x1801b1964  call    ?SlsDatastoreLookup@@YAJPEAUISusDatastore@@AEBU_GUID@@PEB_WAEBU_FILETIME@@AEAUtagDSSLSData@@PEA_N@Z; SlsDatastoreLookup(ISusDatastore *,_GUID const &,wchar_t const *,_FILETIME const &,tagDSSLSData &,bool *)
0x1801b1969  mov     esi, eax
0x1801b196b  xor     edx, edx
0x1801b196d  test    eax, eax
0x1801b196f  jns     short loc_1801B1990
0x1801b1971  lea     ecx, [rax+7FDB7FE0h]
0x1801b1977  cmp     ecx, 9
0x1801b197a  jbe     short loc_1801B1990
0x1801b197c  movzx   ebx, [rsp+3D0h+var_380]
0x1801b1981  cmp     eax, 80248007h
0x1801b1986  lea     r15d, [rdx+1]
0x1801b198a  cmovnz  ebx, r15d
0x1801b198e  jmp     short loc_1801B199A
0x1801b1990  mov     bl, [rsp+3D0h+var_380]
0x1801b1994  mov     r15d, 1
0x1801b199a  test    bl, bl
0x1801b199c  jnz     short loc_1801B19FA
0x1801b199e  mov     cl, r15b; bool
0x1801b19a1  call    ?AreTestKeysAllowed@@YAH_N@Z; AreTestKeysAllowed(bool)
0x1801b19a6  xor     edx, edx
0x1801b19a8  test    eax, eax
0x1801b19aa  jz      short loc_1801B19FA
0x1801b19ac  mov     dword ptr [rsp+3D0h+var_3A8], 0FFFFFFFFh
0x1801b19b4  mov     [rsp+3D0h+var_3B0.dwLowDateTime], edx
0x1801b19b8  xor     r9d, r9d
0x1801b19bb  lea     r8, aSlsexpirecache; "SlsExpireCache"
0x1801b19c2  lea     rdx, ?c_szRegWUTest@@3QB_WB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1801b19c9  call    ?RegQueryDwordValueWithDefaultAndRangeCheck@@YAKPEAUHKEY__@@PEB_W1KKKW4RegistryHiveType@@@Z; RegQueryDwordValueWithDefaultAndRangeCheck(HKEY__ *,wchar_t const *,wchar_t const *,ulong,ulong,ulong,RegistryHiveType)
0x1801b19ce  xor     edx, edx
0x1801b19d0  test    eax, eax
0x1801b19d2  jz      short loc_1801B19FA
0x1801b19d4  lea     rax, aExpirecacheOve; "ExpireCache override set."
0x1801b19db  mov     [rsp+3D0h+var_3A8], rax
0x1801b19e0  mov     qword ptr [rsp+3D0h+var_3B0.dwLowDateTime], rdx
0x1801b19e5  lea     eax, [rdx+4]
0x1801b19e8  mov     r9d, eax
0x1801b19eb  mov     r8d, eax
0x1801b19ee  xor     ecx, ecx
0x1801b19f0  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1801b19f5  mov     bl, r15b
0x1801b19f8  xor     edx, edx
0x1801b19fa  mov     r15d, [rbp+2D0h+var_2F4]
0x1801b19fe  test    esi, esi
0x1801b1a00  js      short loc_1801B1A0A
0x1801b1a02  test    r15d, r15d
0x1801b1a05  mov     sil, 1
0x1801b1a08  jnz     short loc_1801B1A0D
0x1801b1a0a  mov     sil, dl
0x1801b1a0d  lea     rcx, aFalse_6; "False"
0x1801b1a14  mov     rax, rcx
0x1801b1a17  test    bl, bl
0x1801b1a19  lea     r8, aTrue_8; "True"
0x1801b1a20  cmovnz  rax, r8
0x1801b1a24  test    sil, sil
0x1801b1a27  cmovnz  rcx, r8
0x1801b1a2b  mov     [rsp+3D0h+var_398], rax
0x1801b1a30  mov     [rsp+3D0h+var_3A0], rcx
0x1801b1a35  lea     rax, aFiscachehitLsF; "fIsCacheHit[%ls] fContentExpired[%ls] e"...
0x1801b1a3c  mov     [rsp+3D0h+var_3A8], rax
0x1801b1a41  mov     qword ptr [rsp+3D0h+var_3B0.dwLowDateTime], rdx
0x1801b1a46  xor     edx, edx
0x1801b1a48  xor     ecx, ecx
0x1801b1a4a  lea     r9d, [rdx+5]
0x1801b1a4e  lea     r8d, [rdx+4]
0x1801b1a52  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1801b1a57  test    dil, dil
0x1801b1a5a  jnz     short loc_1801B1AB5
0x1801b1a5c  mov     cl, 1; bool
0x1801b1a5e  call    ?AreTestKeysAllowed@@YAH_N@Z; AreTestKeysAllowed(bool)
0x1801b1a63  xor     ecx, ecx
0x1801b1a65  test    eax, eax
0x1801b1a67  jz      short loc_1801B1AB5
0x1801b1a69  mov     dword ptr [rsp+3D0h+var_3A8], 0FFFFFFFFh
0x1801b1a71  mov     [rsp+3D0h+var_3B0.dwLowDateTime], ecx
0x1801b1a75  xor     r9d, r9d
0x1801b1a78  lea     r8, ?c_szRegSLSNoCache@@3QB_WB; "SLSNoCache"
0x1801b1a7f  lea     rdx, ?c_szRegWUTest@@3QB_WB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1801b1a86  call    ?RegQueryDwordValueWithDefaultAndRangeCheck@@YAKPEAUHKEY__@@PEB_W1KKKW4RegistryHiveType@@@Z; RegQueryDwordValueWithDefaultAndRangeCheck(HKEY__ *,wchar_t const *,wchar_t const *,ulong,ulong,ulong,RegistryHiveType)
0x1801b1a8b  xor     ecx, ecx
0x1801b1a8d  test    eax, eax
0x1801b1a8f  jz      short loc_1801B1AB5
0x1801b1a91  lea     rax, aNocacheOverrid; "NoCache override set."
0x1801b1a98  mov     [rsp+3D0h+var_3A8], rax
0x1801b1a9d  mov     qword ptr [rsp+3D0h+var_3B0.dwLowDateTime], rcx
0x1801b1aa2  lea     eax, [rcx+4]
0x1801b1aa5  mov     r9d, eax
0x1801b1aa8  mov     r8d, eax
0x1801b1aab  xor     edx, edx
0x1801b1aad  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1801b1ab2  mov     dil, 1
0x1801b1ab5  test    sil, sil
0x1801b1ab8  jz      loc_1801B1CC6
0x1801b1abe  test    r12d, r12d
0x1801b1ac1  jnz     short loc_1801B1B42
0x1801b1ac3  test    bl, bl
0x1801b1ac5  jnz     short loc_1801B1ACC
0x1801b1ac7  test    dil, dil
0x1801b1aca  jz      short loc_1801B1B42
0x1801b1acc  test    r14b, r14b
0x1801b1acf  jz      short loc_1801B1B42
0x1801b1ad1  call    ?GetInstance@RefreshManager@sls@@SAAEAV12@XZ; sls::RefreshManager::GetInstance(void)
0x1801b1ad6  mov     rdx, [rbp+2D0h+var_350]
0x1801b1ada  mov     rcx, [rdx+0E0h]
0x1801b1ae1  mov     [rsp+3D0h+var_3A0], rcx; struct AADDeviceDataBoundaryInfo *
0x1801b1ae6  lea     rsi, [rdx+58h]
0x1801b1aea  mov     [rsp+3D0h+var_3A8], rsi; char *
0x1801b1aef  mov     byte ptr [rsp+3D0h+var_3B0.dwLowDateTime], dil; bool
0x1801b1af4  mov     r9, [rdx]; struct ISusDatastore *
0x1801b1af7  mov     r8, [rbp+2D0h+var_348]; struct CCallerIdentity *
0x1801b1afb  lea     rdx, [rbp+2D0h+rguid]; struct _GUID *
0x1801b1aff  mov     rcx, rax; Parameter
0x1801b1b02  call    ?EnqueueRefresh@RefreshManager@sls@@QEAAJAEBU_GUID@@PEBVCCallerIdentity@@PEAUISusDatastore@@_NPEBDPEBVAADDeviceDataBoundaryInfo@@@Z; sls::RefreshManager::EnqueueRefresh(_GUID const &,CCallerIdentity const *,ISusDatastore *,bool,char const *,AADDeviceDataBoundaryInfo const *)
0x1801b1b07  mov     r12, [rbp+2D0h+psz]
0x1801b1b0b  cmp     eax, 80240013h
0x1801b1b10  jz      short loc_1801B1B46
0x1801b1b12  movaps  xmm0, xmmword ptr [rbp+2D0h+rguid.Data1]
0x1801b1b16  movdqa  xmmword ptr [rsp+3D0h+lpMem], xmm0
0x1801b1b1c  mov     [rsp+3D0h+var_3A8], rsi; char *
0x1801b1b21  mov     rcx, qword ptr [rbp+2D0h+var_308.dwLowDateTime]
0x1801b1b25  mov     qword ptr [rsp+3D0h+var_3B0.dwLowDateTime], rcx; struct _FILETIME
0x1801b1b2a  mov     r9b, byte ptr [rbp+2D0h+var_290]; bool
0x1801b1b2e  mov     r8d, eax; int
0x1801b1b31  mov     rdx, [r12+20h]; wchar_t *
0x1801b1b36  lea     rcx, [rsp+3D0h+lpMem]; struct _GUID *
0x1801b1b3b  call    ?SendRequestQueuedEvent@DiscoveryEvent@telemetry@sls@@SAXU_GUID@@PEB_WJ_NU_FILETIME@@PEBD@Z; sls::telemetry::DiscoveryEvent::SendRequestQueuedEvent(_GUID,wchar_t const *,long,bool,_FILETIME,char const *)
0x1801b1b40  jmp     short loc_1801B1B46
0x1801b1b42  mov     r12, [rbp+2D0h+psz]
0x1801b1b46  lea     rdx, [rbp+2D0h+var_320]; struct tagDSSLSData *
0x1801b1b4a  mov     rcx, [rsp+3D0h+var_378]; this
0x1801b1b4f  call    ?PopulateFromDataStore@CSLSResponse@@QEAAJAEBUtagDSSLSData@@@Z; CSLSResponse::PopulateFromDataStore(tagDSSLSData const &)
0x1801b1b54  mov     esi, eax
0x1801b1b56  test    eax, eax
0x1801b1b58  jns     short loc_1801B1B8C
0x1801b1b5a  lea     rax, aPopulatefromda; "PopulateFromDataStore"
0x1801b1b61  mov     [rsp+3D0h+var_3A8], rax
0x1801b1b66  mov     [rsp+3D0h+var_3B0.dwLowDateTime], esi
0x1801b1b6a  mov     edi, 1
0x1801b1b6f  mov     r9d, edi
0x1801b1b72  lea     r13d, [rdi+3]
0x1801b1b76  mov     r8d, r13d
0x1801b1b79  xor     edx, edx
0x1801b1b7b  xor     ecx, ecx
0x1801b1b7d  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1801b1b82  mov     rbx, [rsp+3D0h+var_378]
0x1801b1b87  jmp     loc_1801B1F00
0x1801b1b8c  lea     rdx, [rbp+2D0h+var_320]; struct tagDSSLSData *
0x1801b1b90  mov     rcx, [rbp+2D0h+var_350]; this
0x1801b1b94  call    ?SetCacheData@CSLSClient@@AEAAJAEBUtagDSSLSData@@@Z; CSLSClient::SetCacheData(tagDSSLSData const &)
0x1801b1b99  test    eax, eax
0x1801b1b9b  jns     short loc_1801B1BBE
0x1801b1b9d  lea     rax, aSetcachedata; "SetCacheData"
0x1801b1ba4  mov     [rsp+3D0h+var_3A8], rax
0x1801b1ba9  mov     [rsp+3D0h+var_3B0.dwLowDateTime], esi
0x1801b1bad  xor     edx, edx
0x1801b1baf  xor     ecx, ecx
0x1801b1bb1  lea     r9d, [rdx+1]
0x1801b1bb5  lea     r8d, [rdx+4]
0x1801b1bb9  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1801b1bbe  test    bl, bl
0x1801b1bc0  jnz     short loc_1801B1BC7
0x1801b1bc2  test    dil, dil
0x1801b1bc5  jz      short loc_1801B1BE7
0x1801b1bc7  test    r14b, r14b
0x1801b1bca  jz      short loc_1801B1C07
0x1801b1bcc  mov     r9, [rbp+2D0h+var_2F0]; unsigned __int8 *
0x1801b1bd0  mov     r8d, r15d; unsigned int
0x1801b1bd3  lea     rdx, [rbp+2D0h+var_308]; struct _FILETIME *
0x1801b1bd7  lea     rcx, [rbp+2D0h+SystemTimeAsFileTime]; struct _FILETIME *
0x1801b1bdb  call    ?IsWithinExpiredValidityPeriod@@YA_NAEBU_FILETIME@@0KPEAE@Z; IsWithinExpiredValidityPeriod(_FILETIME const &,_FILETIME const &,ulong,uchar *)
0x1801b1be0  xor     r14d, r14d
0x1801b1be3  test    al, al
0x1801b1be5  jz      short loc_1801B1C01
0x1801b1be7  mov     rax, [rbp+2D0h+var_340]
0x1801b1beb  mov     edi, 1
0x1801b1bf0  mov     [rax], dil
0x1801b1bf3  mov     rbx, [rsp+3D0h+var_378]
0x1801b1bf8  lea     r13d, [rdi+3]
0x1801b1bfc  jmp     loc_1801B1F00
0x1801b1c01  mov     r15d, [rbp+2D0h+var_2F4]
0x1801b1c05  jmp     short loc_1801B1C0A
0x1801b1c07  xor     r14d, r14d
0x1801b1c0a  test    bl, bl
0x1801b1c0c  jnz     short loc_1801B1C17
0x1801b1c0e  test    dil, dil
0x1801b1c11  jz      loc_1801B1CCD
0x1801b1c17  mov     dword ptr [rbp+2D0h+var_290], r14d
0x1801b1c1b  mov     [rbp+2D0h+psz], r14
0x1801b1c1f  xor     ecx, ecx; bstrString
0x1801b1c21  call    cs:__imp_SysFreeString
0x1801b1c27  mov     [rbp+2D0h+psz], r14
0x1801b1c2b  lea     r9, [rbp+2D0h+var_290]; unsigned int *
0x1801b1c2f  lea     r8, [rbp+2D0h+psz]; wchar_t **
0x1801b1c33  mov     rdx, [rbp+2D0h+var_2F0]; char *
0x1801b1c37  mov     ecx, r15d; unsigned int
  ... truncated ...
```
