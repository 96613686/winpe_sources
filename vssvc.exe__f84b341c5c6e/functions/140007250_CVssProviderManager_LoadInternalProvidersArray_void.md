# CVssProviderManager::LoadInternalProvidersArray(void)

- ea: `0x140007250`
- end: `0x140007a0d`
- name: `?LoadInternalProvidersArray@CVssProviderManager@@SAXXZ`
- size: `1981`
- prototype: `void(void)`
- caller_count: `5`
- callee_count: `16`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140016db0`
- `0x14001818c`
- `0x14001cafc`
- `0x140055e00`
- `0x140056164`

## callees

- `0x140006020`
- `0x140007250`
- `0x140008a3c`
- `0x140010170`
- `0x1400137c0`
- `0x1400139c0`
- `0x140013cb0`
- `0x140015e38`
- `0x14001e91c`
- `0x1400376e0`
- `0x140049ec4`
- `0x140069108`
- `0x140091560`
- `0x14009166c`
- `0x1400921dc`
- `0x14009ddc0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400078be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400078be`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000757a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000757a`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x14000766a`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x14000766a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400078b0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400078b0`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14000732f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14000732f`
- `VssTrace!__imp_VssTraceMessage` at `0x140007453`
- `VssTrace!__imp_VssTraceMessage` at `0x140007453`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140007393`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140007393`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x140007381`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x140007381`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400079d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400079d9`

## string_xrefs

- `0x1400074b9`: `SYSTEM\CurrentControlSet\Services\VSS`
- `0x1400075f5`: `SYSTEM\CurrentControlSet\Services\VSS`
- `0x140007707`: `SYSTEM\CurrentControlSet\Services\VSS`
- `0x140007601`: `RegOpenKeyExW(HKLM,%s\%s,0,KEY_ALL_ACCESS,&ptr)`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void CVssProviderManager::LoadInternalProvidersArray(void)
{
  int v0; // eax
  _DWORD *v1; // rcx
  int v2; // eax
  char *v3; // rax
  _DWORD *v4; // rdx
  LSTATUS v5; // eax
  unsigned int v6; // ebx
  char v7; // cl
  DWORD i; // eax
  LSTATUS v9; // eax
  unsigned int v10; // ebx
  int ProviderProperties; // ebx
  LSTATUS v12; // eax
  DWORD LastError; // ebx
  unsigned int v14; // ebx
  void *v15; // rbx
  PHKEY phkResult; // [rsp+20h] [rbp-3C8h]
  PFILETIME lpftLastWriteTime; // [rsp+38h] [rbp-3B0h]
  char v18; // [rsp+50h] [rbp-398h]
  int v19; // [rsp+54h] [rbp-394h]
  DWORD v20; // [rsp+54h] [rbp-394h]
  LPVOID pv; // [rsp+58h] [rbp-390h] BYREF
  DWORD cchName; // [rsp+60h] [rbp-388h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-380h] BYREF
  const unsigned __int16 *v24; // [rsp+78h] [rbp-370h] BYREF
  const unsigned __int16 *v25; // [rsp+80h] [rbp-368h]
  const unsigned __int16 *v26; // [rsp+88h] [rbp-360h]
  int v27; // [rsp+90h] [rbp-358h]
  int v28; // [rsp+94h] [rbp-354h]
  int v29; // [rsp+98h] [rbp-350h]
  _BYTE v30[120]; // [rsp+A0h] [rbp-348h] BYREF
  int v31; // [rsp+118h] [rbp-2D0h]
  unsigned __int64 v32; // [rsp+120h] [rbp-2C8h] BYREF
  int v33; // [rsp+128h] [rbp-2C0h]
  const unsigned __int16 *v34; // [rsp+130h] [rbp-2B8h]
  const unsigned __int16 *v35; // [rsp+138h] [rbp-2B0h]
  unsigned int v36; // [rsp+140h] [rbp-2A8h]
  unsigned int v37; // [rsp+144h] [rbp-2A4h]
  const unsigned __int16 *v38; // [rsp+148h] [rbp-2A0h]
  unsigned int v39; // [rsp+150h] [rbp-298h]
  DWORD TickCount; // [rsp+154h] [rbp-294h]
  int v41; // [rsp+158h] [rbp-290h]
  __int128 v42; // [rsp+160h] [rbp-288h]
  __int128 v43; // [rsp+170h] [rbp-278h]
  _DWORD *v44; // [rsp+180h] [rbp-268h]
  struct _FILETIME ftLastWriteTime; // [rsp+190h] [rbp-258h] BYREF
  int v46; // [rsp+198h] [rbp-250h] BYREF
  const std::exception *v47; // [rsp+1A0h] [rbp-248h] BYREF
  _com_error *v48; // [rsp+1A8h] [rbp-240h] BYREF
  WCHAR SubKey[256]; // [rsp+1B0h] [rbp-238h] BYREF

  v24 = L"base\\stor\\vss\\modules\\coord\\src\\provmgr.cxx";
  v25 = L"CVssProviderManager::LoadInternalProvidersArray";
  v26 = L"CORPRVMC";
  v27 = 999;
  v28 = 1;
  v29 = 255;
  v31 = 0x1000000;
  memset_0(v30, 0, sizeof(v30));
  v33 = 0;
  v38 = L"CVssProviderManager::LoadInternalProvidersArray";
  v34 = L"base\\stor\\vss\\modules\\coord\\src\\provmgr.cxx";
  v35 = L"CORPRVMC";
  v36 = 999;
  v37 = 1;
  TickCount = GetTickCount();
  v41 = 255;
  v32 = 0xFFFFFFFF00000000uLL;
  v44 = 0;
  v42 = 0;
  v43 = 0;
  pv = 0;
  if ( (int)VssGetTracingContextPerThread(&pv) < 0 )
  {
    v1 = v44;
  }
  else
  {
    v0 = VssSetTracingContextPerThread(&v32);
    v1 = v44;
    if ( v0 >= 0 )
      v1 = pv;
    v44 = v1;
  }
  if ( v1 )
    v39 = v1[12] + 1;
  else
    v39 = 0;
  v2 = 160;
  if ( v41 != 255 )
    v2 = v41;
  v19 = v2;
  if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled((CVssFunctionTracer *)&v32) )
    VssTraceMessage(v34, v35, v36, v39, v37, v38, L"ENTER", v19, 0);
  CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)&v24);
  pv = 0;
  hKey = 0;
  ftLastWriteTime = 0;
  if ( !CVssProviderManager::m_pProvidersArray )
  {
    try
    {
      v3 = (char *)operator new(0x20u);
      ATL::CSimpleArray<CVssSnapshotShareInfo,ATL::CSimpleArrayEqualHelper<CVssSnapshotShareInfo>>::CSimpleArray<CVssSnapshotShareInfo,ATL::CSimpleArrayEqualHelper<CVssSnapshotShareInfo>>(v3 + 8);
      v4[6] = 0;
      *(_QWORD *)v4 = &VSS_OBJECT_PROP_Array::`vftable';
      CVssProviderManager::m_pProvidersArray = v4;
      v33 = StringCchPrintfW(SubKey, 0x100u, L"%s\\%s", L"SYSTEM\\CurrentControlSet\\Services\\VSS", L"Providers");
      if ( v33 < 0 )
      {
        v24 = L"base\\stor\\vss\\modules\\coord\\src\\provmgr.cxx";
        v25 = L"CVssProviderManager::LoadInternalProvidersArray";
        v26 = L"CORPRVMC";
        v27 = 1024;
        v28 = 1;
        v29 = 255;
        v31 = 0x1000000;
        memset_0(v30, 0, sizeof(v30));
        CVssFunctionTracer::TranslateGenericError(&v32, &v24, (unsigned int)v33, L"StringCchPrintfW()");
      }
      v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &hKey);
      v6 = v5;
      if ( v5 )
      {
        if ( v5 > 0 )
          v6 = (unsigned __int16)v5 | 0x80070000;
        v24 = L"base\\stor\\vss\\modules\\coord\\src\\provmgr.cxx";
        v25 = L"CVssProviderManager::LoadInternalProvidersArray";
        v26 = L"CORPRVMC";
        v27 = 1033;
        v28 = 1;
        v29 = 255;
        v31 = 0x1000000;
        memset_0(v30, 0, sizeof(v30));
        CVssFunctionTracer::TranslateGenericError(
          &v32,
          &v24,
          v6,
          L"RegOpenKeyExW(HKLM,%s\\%s,0,KEY_ALL_ACCESS,&ptr)",
          L"SYSTEM\\CurrentControlSet\\Services\\VSS",
          L"Providers");
      }
      v7 = 0;
      v18 = 0;
      for ( i = 0; ; i = v20 + 1 )
      {
        v20 = i;
        if ( v7 )
          break;
        cchName = 256;
        v9 = RegEnumKeyExW(hKey, i, SubKey, &cchName, 0, 0, 0, &ftLastWriteTime);
        v10 = v9;
        if ( v9 )
        {
          if ( v9 != 259 )
          {
            if ( v9 > 0 )
              v10 = (unsigned __int16)v9 | 0x80070000;
            v24 = L"base\\stor\\vss\\modules\\coord\\src\\provmgr.cxx";
            v25 = L"CVssProviderManager::LoadInternalProvidersArray";
            v26 = L"CORPRVMC";
            v27 = 1094;
            v28 = 1;
            v29 = 255;
            v31 = 0x1000000;
            memset_0(v30, 0, sizeof(v30));
            LODWORD(lpftLastWriteTime) = v20;
            CVssFunctionTracer::TranslateGenericError(
              &v32,
              &v24,
              v10,
              L"RegEnumKeyExW(HKLM\\%s\\%s,%s,%d,...)",
              L"SYSTEM\\CurrentControlSet\\Services\\VSS",
              L"Providers",
              SubKey,
              lpftLastWriteTime);
          }
          v7 = 1;
          v18 = 1;
        }
        else
        {
          ProviderProperties = CVssProviderManager::GetProviderProperties(
                                 hKey,
                                 SubKey,
                                 (struct VSS_OBJECT_PROP_Ptr *)&pv);
          v33 = ProviderProperties;
          if ( ProviderProperties >= 0 )
          {
            if ( !(unsigned int)ATL::CSimpleArray<_HRESOURCE *,ATL::CSimpleArrayEqualHelper<_HRESOURCE *>>::Add(
                                  (char *)CVssProviderManager::m_pProvidersArray + 8,
                                  &pv) )
            {
              v24 = L"base\\stor\\vss\\modules\\coord\\src\\provmgr.cxx";
              v25 = L"CVssProviderManager::LoadInternalProvidersArray";
              v26 = L"CORPRVMC";
              v27 = 1079;
              v28 = 1;
              v29 = 255;
              v31 = 0x1000000;
              memset_0(v30, 0, sizeof(v30));
              CVssFunctionTracer::Throw(&v32, &v24, 2147942414LL, L"Cannot add element to the array");
            }
            pv = 0;
          }
          else
          {
            v24 = L"base\\stor\\vss\\modules\\coord\\src\\provmgr.cxx";
            v25 = L"CVssProviderManager::LoadInternalProvidersArray";
            v26 = L"CORPRVMC";
            v27 = 1066;
            v28 = 1;
            v29 = 255;
            v31 = 0x1000000;
            memset_0(v30, 0, sizeof(v30));
            LODWORD(phkResult) = ProviderProperties;
            CVssFunctionTracer::Trace(
              &v32,
              &v24,
              L"Error on getting Provider properties for %s. [0x%08lx]",
              SubKey,
              phkResult);
            v33 = 0;
          }
          v7 = v18;
        }
      }
    }
    catch ( long v46 )
    {
      CVssFunctionTracer::HandleHresultException(
        (CVssFunctionTracer *)&v32,
        v46,
        L"base\\stor\\vss\\modules\\coord\\src\\provmgr.cxx",
        L"CORPRVMC",
        L"CVssProviderManager::LoadInternalProvidersArray",
        0x44Eu,
        v37);
    }
    catch ( _com_error *v48 )
    {
      CVssFunctionTracer::HandleComException(
        (CVssFunctionTracer *)&v32,
        v48,
        L"base\\stor\\vss\\modules\\coord\\src\\provmgr.cxx",
        L"CORPRVMC",
        L"CVssProviderManager::LoadInternalProvidersArray",
        0x44Eu,
        v37);
    }
    catch ( std::bad_alloc )
    {
      CVssFunctionTracer::HandleStdBadAllocException(
        (CVssFunctionTracer *)&v32,
        L"base\\stor\\vss\\modules\\coord\\src\\provmgr.cxx",
        L"CORPRVMC",
        L"CVssProviderManager::LoadInternalProvidersArray",
        0x44Eu,
        v37);
    }
    catch ( const std::exception *v47 )
    {
      CVssFunctionTracer::HandleStdGenericException(
        (CVssFunctionTracer *)&v32,
        v47,
        L"base\\stor\\vss\\modules\\coord\\src\\provmgr.cxx",
        L"CORPRVMC",
        L"CVssProviderManager::LoadInternalProvidersArray",
        0x44Eu,
        v37);
    }
  }
  if ( hKey )
    v12 = RegCloseKey(hKey);
  else
    v12 = 0;
  if ( v12 )
  {
    LastError = GetLastError();
    v24 = L"base\\stor\\vss\\modules\\coord\\src\\provmgr.cxx";
    v25 = L"CVssProviderManager::LoadInternalProvidersArray";
    v26 = L"CORPRVMC";
    v27 = 1107;
    v28 = 1;
    v29 = 255;
    v31 = 0x1000000;
    memset_0(v30, 0, sizeof(v30));
    CVssFunctionTracer::Trace(&v32, &v24, L"Error closing the hKeyProviders key. [0x%08lx]", LastError);
  }
  if ( v33 < 0 )
  {
    CVssProviderManager::UnloadInternalProvidersArray();
    v14 = v33;
    v24 = L"base\\stor\\vss\\modules\\coord\\src\\provmgr.cxx";
    v25 = L"CVssProviderManager::LoadInternalProvidersArray";
    v26 = L"CORPRVMC";
    v27 = 1114;
    v28 = 1;
    v29 = 255;
    v31 = 0x1000000;
    memset_0(v30, 0, sizeof(v30));
    LODWORD(phkResult) = v14;
    CVssFunctionTracer::Throw(&v32, &v24, v14, L"Cannot load the internal providers array [0x%08lx]", phkResult);
  }
  v15 = pv;
  if ( pv )
  {
    VSS_OBJECT_PROP_Copy::destroy((struct _VSS_OBJECT_PROP *)pv);
    CoTaskMemFree(v15);
  }
  CVssFunctionTracer::~CVssFunctionTracer((LPVOID *)&v32);
}

```

## disassembly

```asm
0x140007250  push    rbx
0x140007252  push    rdi
0x140007253  push    r12
0x140007255  push    r13
0x140007257  push    r15
0x140007259  sub     rsp, 3C0h
0x140007260  mov     rax, cs:__security_cookie
0x140007267  xor     rax, rsp
0x14000726a  mov     [rsp+3E8h+var_38], rax
0x140007272  lea     r15, aBaseStorVssMod_13; "base\\stor\\vss\\modules\\coord\\src\\p"...
0x140007279  mov     [rsp+3E8h+var_370], r15
0x14000727e  lea     r12, aCvssproviderma_18; "CVssProviderManager::LoadInternalProvid"...
0x140007285  mov     [rsp+3E8h+var_368], r12
0x14000728d  lea     r13, aCorprvmc; "CORPRVMC"
0x140007294  mov     [rsp+3E8h+var_360], r13
0x14000729c  mov     [rsp+3E8h+var_358], 3E7h
0x1400072a7  mov     [rsp+3E8h+var_354], 1
0x1400072b2  mov     [rsp+3E8h+var_350], 0FFh
0x1400072bd  xor     edi, edi
0x1400072bf  mov     [rsp+3E8h+var_2D0], 1000000h
0x1400072ca  lea     ebx, [rdi+78h]
0x1400072cd  mov     r8d, ebx; Size
0x1400072d0  xor     edx, edx; Val
0x1400072d2  lea     rcx, [rsp+3E8h+var_348]; void *
0x1400072da  call    memset_0
0x1400072df  mov     [rsp+3E8h+var_2C0], edi
0x1400072e6  mov     rax, [rsp+3E8h+var_368]
0x1400072ee  mov     [rsp+3E8h+var_2A0], rax
0x1400072f6  mov     rax, [rsp+3E8h+var_370]
0x1400072fb  mov     [rsp+3E8h+var_2B8], rax
0x140007303  mov     rax, [rsp+3E8h+var_360]
0x14000730b  mov     [rsp+3E8h+var_2B0], rax
0x140007313  mov     eax, [rsp+3E8h+var_358]
0x14000731a  mov     [rsp+3E8h+var_2A8], eax
0x140007321  mov     eax, [rsp+3E8h+var_354]
0x140007328  mov     [rsp+3E8h+var_2A4], eax
0x14000732f  call    cs:__imp_GetTickCount
0x140007335  mov     [rsp+3E8h+var_294], eax
0x14000733c  mov     [rsp+3E8h+var_2C4], 0FFFFFFFFh
0x140007347  mov     eax, [rsp+3E8h+var_350]
0x14000734e  mov     [rsp+3E8h+var_290], eax
0x140007355  mov     [rsp+3E8h+var_2C8], edi
0x14000735c  mov     [rsp+3E8h+var_268], rdi
0x140007364  xorps   xmm0, xmm0
0x140007367  movups  [rsp+3E8h+var_288], xmm0
0x14000736f  movups  [rsp+3E8h+var_278], xmm0
0x140007377  mov     [rsp+3E8h+pv], rdi
0x14000737c  lea     rcx, [rsp+3E8h+pv]
0x140007381  call    cs:__imp_VssGetTracingContextPerThread
0x140007387  test    eax, eax
0x140007389  js      short loc_1400073B3
0x14000738b  lea     rcx, [rsp+3E8h+var_2C8]
0x140007393  call    cs:__imp_VssSetTracingContextPerThread
0x140007399  mov     rcx, [rsp+3E8h+var_268]
0x1400073a1  test    eax, eax
0x1400073a3  cmovns  rcx, [rsp+3E8h+pv]
0x1400073a9  mov     [rsp+3E8h+var_268], rcx
0x1400073b1  jmp     short loc_1400073BB
0x1400073b3  mov     rcx, [rsp+3E8h+var_268]
0x1400073bb  test    rcx, rcx
0x1400073be  jz      short loc_1400073CE
0x1400073c0  mov     eax, [rcx+30h]
0x1400073c3  inc     eax
0x1400073c5  mov     [rsp+3E8h+var_298], eax
0x1400073cc  jmp     short loc_1400073D5
0x1400073ce  mov     [rsp+3E8h+var_298], edi
0x1400073d5  mov     eax, 0A0h
0x1400073da  cmp     [rsp+3E8h+var_290], 0FFh
0x1400073e5  cmovnz  eax, [rsp+3E8h+var_290]
0x1400073ed  mov     [rsp+3E8h+var_394], eax
0x1400073f1  lea     rcx, [rsp+3E8h+var_2C8]; this
0x1400073f9  call    ?IsTracingEnabled@CVssFunctionTracer@@QEAAHXZ; CVssFunctionTracer::IsTracingEnabled(void)
0x1400073fe  test    eax, eax
0x140007400  jz      short loc_140007459
0x140007402  mov     [rsp+3E8h+var_3A8], rdi
0x140007407  mov     eax, [rsp+3E8h+var_394]
0x14000740b  mov     dword ptr [rsp+3E8h+lpftLastWriteTime], eax
0x14000740f  lea     rax, aEnter; "ENTER"
0x140007416  mov     [rsp+3E8h+lpcchClass], rax
0x14000741b  mov     rax, [rsp+3E8h+var_2A0]
0x140007423  mov     [rsp+3E8h+lpClass], rax
0x140007428  mov     eax, [rsp+3E8h+var_2A4]
0x14000742f  mov     dword ptr [rsp+3E8h+phkResult], eax
0x140007433  mov     r9d, [rsp+3E8h+var_298]
0x14000743b  mov     r8d, [rsp+3E8h+var_2A8]
0x140007443  mov     rdx, [rsp+3E8h+var_2B0]
0x14000744b  mov     rcx, [rsp+3E8h+var_2B8]
0x140007453  call    cs:__imp_VssTraceMessage
0x140007459  lea     rcx, [rsp+3E8h+var_370]; this
0x14000745e  call    ??1CVssDebugInfo@@QEAA@XZ; CVssDebugInfo::~CVssDebugInfo(void)
0x140007463  nop
0x140007464  mov     [rsp+3E8h+pv], rdi
0x140007469  mov     [rsp+3E8h+hKey], rdi
0x14000746e  mov     qword ptr [rsp+3E8h+ftLastWriteTime.dwLowDateTime], rdi
0x140007476  cmp     cs:?m_pProvidersArray@CVssProviderManager@@0PEAVVSS_OBJECT_PROP_Array@@EA, rdi; VSS_OBJECT_PROP_Array * CVssProviderManager::m_pProvidersArray
0x14000747d  jnz     loc_140007887
0x140007483  mov     ecx, 20h ; ' '; Size
0x140007488  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000748d  mov     rdx, rax
0x140007490  lea     rcx, [rax+8]
0x140007494  call    ??0?$CSimpleArray@UCVssSnapshotShareInfo@@V?$CSimpleArrayEqualHelper@UCVssSnapshotShareInfo@@@ATL@@@ATL@@QEAA@XZ; ATL::CSimpleArray<CVssSnapshotShareInfo,ATL::CSimpleArrayEqualHelper<CVssSnapshotShareInfo>>::CSimpleArray<CVssSnapshotShareInfo,ATL::CSimpleArrayEqualHelper<CVssSnapshotShareInfo>>(void)
0x140007499  mov     [rdx+18h], edi
0x14000749c  lea     rax, ??_7VSS_OBJECT_PROP_Array@@6B@; const VSS_OBJECT_PROP_Array::`vftable'
0x1400074a3  mov     [rdx], rax
0x1400074a6  mov     cs:?m_pProvidersArray@CVssProviderManager@@0PEAVVSS_OBJECT_PROP_Array@@EA, rdx; VSS_OBJECT_PROP_Array * CVssProviderManager::m_pProvidersArray
0x1400074ad  lea     rax, aProviders; "Providers"
0x1400074b4  mov     [rsp+3E8h+phkResult], rax
0x1400074b9  lea     r9, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Services\\VS"...
0x1400074c0  lea     r8, aSS; "%s\\%s"
0x1400074c7  mov     edx, 100h; unsigned __int64
0x1400074cc  lea     rcx, [rsp+3E8h+SubKey]; unsigned __int16 *
0x1400074d4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400074d9  mov     [rsp+3E8h+var_2C0], eax
0x1400074e0  test    eax, eax
0x1400074e2  jns     short loc_140007558
0x1400074e4  mov     [rsp+3E8h+var_370], r15
0x1400074e9  mov     [rsp+3E8h+var_368], r12
0x1400074f1  mov     [rsp+3E8h+var_360], r13
0x1400074f9  mov     [rsp+3E8h+var_358], 400h
0x140007504  mov     [rsp+3E8h+var_354], 1
0x14000750f  mov     [rsp+3E8h+var_350], 0FFh
0x14000751a  mov     [rsp+3E8h+var_2D0], 1000000h
0x140007525  mov     r8, rbx; Size
0x140007528  xor     edx, edx; Val
0x14000752a  lea     rcx, [rsp+3E8h+var_348]; void *
0x140007532  call    memset_0
0x140007537  lea     r9, aStringcchprint_14; "StringCchPrintfW()"
0x14000753e  mov     r8d, [rsp+3E8h+var_2C0]
0x140007546  lea     rdx, [rsp+3E8h+var_370]
0x14000754b  lea     rcx, [rsp+3E8h+var_2C8]
0x140007553  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
0x140007558  lea     rax, [rsp+3E8h+hKey]
0x14000755d  mov     [rsp+3E8h+phkResult], rax; phkResult
0x140007562  mov     r9d, 20019h; samDesired
0x140007568  xor     r8d, r8d; ulOptions
0x14000756b  lea     rdx, [rsp+3E8h+SubKey]; lpSubKey
0x140007573  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14000757a  call    cs:__imp_RegOpenKeyExW
0x140007580  mov     ebx, eax
0x140007582  test    eax, eax
0x140007584  jz      loc_14000761D
0x14000758a  jle     short loc_140007595
0x14000758c  movzx   ebx, ax
0x14000758f  or      ebx, 80070000h
0x140007595  mov     [rsp+3E8h+var_370], r15
0x14000759a  mov     [rsp+3E8h+var_368], r12
0x1400075a2  mov     [rsp+3E8h+var_360], r13
0x1400075aa  mov     [rsp+3E8h+var_358], 409h
0x1400075b5  mov     [rsp+3E8h+var_354], 1
0x1400075c0  mov     [rsp+3E8h+var_350], 0FFh
0x1400075cb  mov     [rsp+3E8h+var_2D0], 1000000h
0x1400075d6  xor     edx, edx; Val
0x1400075d8  lea     r8d, [rdx+78h]; Size
0x1400075dc  lea     rcx, [rsp+3E8h+var_348]; void *
0x1400075e4  call    memset_0
0x1400075e9  lea     rax, aProviders; "Providers"
0x1400075f0  mov     [rsp+3E8h+lpClass], rax
0x1400075f5  lea     rax, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Services\\VS"...
0x1400075fc  mov     [rsp+3E8h+phkResult], rax
0x140007601  lea     r9, aRegopenkeyexwH; "RegOpenKeyExW(HKLM,%s\\%s,0,KEY_ALL_ACC"...
0x140007608  mov     r8d, ebx
0x14000760b  lea     rdx, [rsp+3E8h+var_370]
0x140007610  lea     rcx, [rsp+3E8h+var_2C8]
0x140007618  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
0x14000761d  mov     cl, dil
0x140007620  mov     [rsp+3E8h+var_398], cl
0x140007624  mov     eax, edi
0x140007626  mov     [rsp+3E8h+var_394], eax
0x14000762a  test    cl, cl
0x14000762c  jnz     loc_140007887
0x140007632  mov     [rsp+3E8h+cchName], 100h
0x14000763a  lea     rcx, [rsp+3E8h+ftLastWriteTime]
0x140007642  mov     [rsp+3E8h+lpftLastWriteTime], rcx; lpftLastWriteTime
0x140007647  mov     [rsp+3E8h+lpcchClass], rdi; lpcchClass
0x14000764c  mov     [rsp+3E8h+lpClass], rdi; lpClass
0x140007651  mov     [rsp+3E8h+phkResult], rdi; lpReserved
0x140007656  lea     r9, [rsp+3E8h+cchName]; lpcchName
0x14000765b  lea     r8, [rsp+3E8h+SubKey]; lpName
0x140007663  mov     edx, eax; dwIndex
0x140007665  mov     rcx, [rsp+3E8h+hKey]; hKey
0x14000766a  call    cs:__imp_RegEnumKeyExW
0x140007670  mov     ebx, eax
0x140007672  test    eax, eax
0x140007674  jz      loc_14000773A
0x14000767a  cmp     eax, 103h
0x14000767f  jz      loc_14000772F
0x140007685  test    eax, eax
0x140007687  jle     short loc_140007692
0x140007689  movzx   ebx, ax
0x14000768c  or      ebx, 80070000h
0x140007692  mov     [rsp+3E8h+var_370], r15
0x140007697  mov     [rsp+3E8h+var_368], r12
0x14000769f  mov     [rsp+3E8h+var_360], r13
0x1400076a7  mov     [rsp+3E8h+var_358], 446h
0x1400076b2  mov     [rsp+3E8h+var_354], 1
0x1400076bd  mov     [rsp+3E8h+var_350], 0FFh
0x1400076c8  mov     [rsp+3E8h+var_2D0], 1000000h
0x1400076d3  xor     edx, edx; Val
0x1400076d5  lea     r8d, [rdx+78h]; Size
0x1400076d9  lea     rcx, [rsp+3E8h+var_348]; void *
0x1400076e1  call    memset_0
0x1400076e6  mov     eax, [rsp+3E8h+var_394]
0x1400076ea  mov     dword ptr [rsp+3E8h+lpftLastWriteTime], eax
0x1400076ee  lea     rax, [rsp+3E8h+SubKey]
0x1400076f6  mov     [rsp+3E8h+lpcchClass], rax
0x1400076fb  lea     rax, aProviders; "Providers"
0x140007702  mov     [rsp+3E8h+lpClass], rax
0x140007707  lea     rax, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Services\\VS"...
0x14000770e  mov     [rsp+3E8h+phkResult], rax
0x140007713  lea     r9, aRegenumkeyexwH; "RegEnumKeyExW(HKLM\\%s\\%s,%s,%d,...)"
0x14000771a  mov     r8d, ebx
0x14000771d  lea     rdx, [rsp+3E8h+var_370]
0x140007722  lea     rcx, [rsp+3E8h+var_2C8]
0x14000772a  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
0x14000772f  mov     cl, 1
0x140007731  mov     [rsp+3E8h+var_398], cl
0x140007735  jmp     loc_14000787C
0x14000773a  lea     r8, [rsp+3E8h+pv]; struct VSS_OBJECT_PROP_Ptr *
0x14000773f  lea     rdx, [rsp+3E8h+SubKey]; unsigned __int16 *
0x140007747  mov     rcx, [rsp+3E8h+hKey]; HKEY
0x14000774c  call    ?GetProviderProperties@CVssProviderManager@@CAJPEAUHKEY__@@PEBGAEAVVSS_OBJECT_PROP_Ptr@@@Z; CVssProviderManager::GetProviderProperties(HKEY__ *,ushort const *,VSS_OBJECT_PROP_Ptr &)
0x140007751  mov     ebx, eax
0x140007753  mov     [rsp+3E8h+var_2C0], eax
0x14000775a  test    eax, eax
0x14000775c  jns     loc_1400077E7
0x140007762  mov     [rsp+3E8h+var_370], r15
0x140007767  mov     [rsp+3E8h+var_368], r12
0x14000776f  mov     [rsp+3E8h+var_360], r13
0x140007777  mov     [rsp+3E8h+var_358], 42Ah
0x140007782  mov     [rsp+3E8h+var_354], 1
0x14000778d  mov     [rsp+3E8h+var_350], 0FFh
0x140007798  mov     [rsp+3E8h+var_2D0], 1000000h
0x1400077a3  xor     edx, edx; Val
0x1400077a5  lea     r8d, [rdx+78h]; Size
0x1400077a9  lea     rcx, [rsp+3E8h+var_348]; void *
0x1400077b1  call    memset_0
0x1400077b6  mov     dword ptr [rsp+3E8h+phkResult], ebx
0x1400077ba  lea     r9, [rsp+3E8h+SubKey]
0x1400077c2  lea     r8, aErrorOnGetting; "Error on getting Provider properties fo"...
0x1400077c9  lea     rdx, [rsp+3E8h+var_370]
0x1400077ce  lea     rcx, [rsp+3E8h+var_2C8]
0x1400077d6  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x1400077db  mov     [rsp+3E8h+var_2C0], edi
0x1400077e2  jmp     loc_140007878
0x1400077e7  mov     rcx, cs:?m_pProvidersArray@CVssProviderManager@@0PEAVVSS_OBJECT_PROP_Array@@EA; VSS_OBJECT_PROP_Array * CVssProviderManager::m_pProvidersArray
0x1400077ee  add     rcx, 8
0x1400077f2  lea     rdx, [rsp+3E8h+pv]
0x1400077f7  call    ?Add@?$CSimpleArray@PEAU_HRESOURCE@@V?$CSimpleArrayEqualHelper@PEAU_HRESOURCE@@@ATL@@@ATL@@QEAAHAEBQEAU_HRESOURCE@@@Z; ATL::CSimpleArray<_HRESOURCE *,ATL::CSimpleArrayEqualHelper<_HRESOURCE *>>::Add(_HRESOURCE * const &)
0x1400077fc  test    eax, eax
0x1400077fe  jnz     short loc_140007873
0x140007800  mov     [rsp+3E8h+var_370], r15
0x140007805  mov     [rsp+3E8h+var_368], r12
0x14000780d  mov     [rsp+3E8h+var_360], r13
0x140007815  mov     [rsp+3E8h+var_358], 437h
0x140007820  mov     [rsp+3E8h+var_354], 1
0x14000782b  mov     [rsp+3E8h+var_350], 0FFh
0x140007836  mov     [rsp+3E8h+var_2D0], 1000000h
0x140007841  xor     edx, edx; Val
0x140007843  lea     r8d, [rax+78h]; Size
0x140007847  lea     rcx, [rsp+3E8h+var_348]; void *
0x14000784f  call    memset_0
0x140007854  lea     r9, aCannotAddEleme; "Cannot add element to the array"
0x14000785b  mov     r8d, 8007000Eh
0x140007861  lea     rdx, [rsp+3E8h+var_370]
0x140007866  lea     rcx, [rsp+3E8h+var_2C8]
0x14000786e  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x140007873  mov     [rsp+3E8h+pv], rdi
0x140007878  mov     cl, [rsp+3E8h+var_398]
0x14000787c  mov     eax, [rsp+3E8h+var_394]
0x140007880  inc     eax
0x140007882  jmp     loc_140007626
0x140007887  jmp     short loc_1400078A6
0x140007889  jmp     short loc_14000788F
0x14000788b  jmp     short loc_14000788F
0x14000788d  jmp     short $+2
0x14000788f  xor     edi, edi
0x140007891  lea     r13, aCorprvmc; "CORPRVMC"
0x140007898  lea     r12, aCvssproviderma_18; "CVssProviderManager::LoadInternalProvid"...
0x14000789f  lea     r15, aBaseStorVssMod_13; "base\\stor\\vss\\modules\\coord\\src\\p"...
0x1400078a6  mov     rcx, [rsp+3E8h+hKey]; hKey
0x1400078ab  test    rcx, rcx
0x1400078ae  jz      short loc_1400078B8
0x1400078b0  call    cs:__imp_RegCloseKey
0x1400078b6  jmp     short loc_1400078BA
0x1400078b8  mov     eax, edi
0x1400078ba  test    eax, eax
0x1400078bc  jz      short loc_140007936
0x1400078be  call    cs:__imp_GetLastError
0x1400078c4  mov     ebx, eax
0x1400078c6  mov     [rsp+3E8h+var_370], r15
0x1400078cb  mov     [rsp+3E8h+var_368], r12
0x1400078d3  mov     [rsp+3E8h+var_360], r13
0x1400078db  mov     [rsp+3E8h+var_358], 453h
0x1400078e6  mov     [rsp+3E8h+var_354], 1
0x1400078f1  mov     [rsp+3E8h+var_350], 0FFh
0x1400078fc  mov     [rsp+3E8h+var_2D0], 1000000h
0x140007907  xor     edx, edx; Val
0x140007909  lea     r8d, [rdx+78h]; Size
0x14000790d  lea     rcx, [rsp+3E8h+var_348]; void *
0x140007915  call    memset_0
  ... truncated ...
```
