# COledbRangeExternalComputation::GetProviderString(wchar_t *,ulong,bool,_GUID *)

- ea: `0x1017000b0`
- end: `0x101701077`
- name: `?GetProviderString@COledbRangeExternalComputation@@SAXPEA_WK_NPEAU_GUID@@@Z`
- size: `4039`
- prototype: `void __fastcall(wchar_t *, unsigned int, bool, struct _GUID *)`
- caller_count: `4`
- callee_count: `10`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1012314a0`
- `0x1012d7140`
- `0x101701080`
- `0x101701440`

## callees

- `0x100401070`
- `0x100401433`
- `0x1004132a0`
- `0x100413360`
- `0x100430960`
- `0x10043c390`
- `0x10043c470`
- `0x100757670`
- `0x1013be860`
- `0x1017000b0`

## import_xrefs

- `KERNEL32!GetEnvironmentVariableW` at `0x101700667`
- `KERNEL32!GetEnvironmentVariableW` at `0x101700703`
- `KERNEL32!GetEnvironmentVariableW` at `0x101700667`
- `KERNEL32!GetEnvironmentVariableW` at `0x101700703`
- `KERNEL32!GetComputerNameW` at `0x101700528`
- `KERNEL32!GetComputerNameW` at `0x101700528`
- `KERNEL32!GetComputerNameExW` at `0x1017005ed`
- `KERNEL32!GetComputerNameExW` at `0x1017005ed`
- `ole32!StringFromGUID2` at `0x101700f92`
- `ole32!StringFromGUID2` at `0x101700f92`
- `secforwarder!BCryptGenRandom` at `0x101700f4f`
- `secforwarder!BCryptGenRandom` at `0x101700f4f`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x101700ceb`
- `sqldk!?SOS_OS_OsInfo@@3VOsInfo@@A` at `0x101700615`
- `sqldk!?SOS_OS_OsInfo@@3VOsInfo@@A` at `0x101700dbb`
- `sqldk!?IsLinux@OsInfo@@QEBA?B_NXZ` at `0x10170061c`
- `sqldk!?IsLinux@OsInfo@@QEBA?B_NXZ` at `0x101700dc2`
- `sqldk!?IsLinux@OsInfo@@QEBA?B_NXZ` at `0x10170061c`
- `sqldk!?IsLinux@OsInfo@@QEBA?B_NXZ` at `0x101700dc2`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x1017002a9`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x1017002a9`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1017002ed`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10170032e`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101700388`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101700410`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10170056a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101700688`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1017007ad`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1017007df`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10170088a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1017008c5`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101700a78`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101700b2d`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101700b5f`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101700c07`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101700c39`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101700ce5`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101700db5`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101700e85`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101700f35`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101700f6e`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101700faf`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101700ff5`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101701047`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1017002ed`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10170032e`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101700388`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101700410`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10170056a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101700688`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1017007ad`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1017007df`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10170088a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1017008c5`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101700a78`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101700b2d`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101700b5f`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101700c07`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101700c39`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101700ce5`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101700db5`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101700e85`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101700f35`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101700f6e`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101700faf`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101700ff5`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101701047`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101700217`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101700281`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1017004fd`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1017005c9`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1017006e6`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101700217`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101700281`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1017004fd`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1017005c9`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1017006e6`
- `sqldk!SystemThread_TlsIndex` at `0x1017001c8`
- `sqldk!SystemThread_TlsIndex` at `0x101700232`
- `sqldk!SystemThread_TlsIndex` at `0x1017004ad`
- `sqldk!SystemThread_TlsIndex` at `0x101700579`
- `sqldk!SystemThread_TlsIndex` at `0x101700697`
- `sqldk!SystemThread_TlsOffset` at `0x1017001d1`
- `sqldk!SystemThread_TlsOffset` at `0x10170023b`
- `sqldk!SystemThread_TlsOffset` at `0x1017004b6`
- `sqldk!SystemThread_TlsOffset` at `0x101700582`
- `sqldk!SystemThread_TlsOffset` at `0x1017006a0`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1017001ec`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101700256`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1017004d2`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10170059e`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1017006bb`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1017001ec`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101700256`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1017004d2`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10170059e`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1017006bb`
- `sqldk!??_V@YAXPEAX@Z` at `0x10170050d`
- `sqldk!??_V@YAXPEAX@Z` at `0x1017007e9`
- `sqldk!??_V@YAXPEAX@Z` at `0x101700fff`
- `sqldk!??_V@YAXPEAX@Z` at `0x10170100b`
- `sqldk!??_V@YAXPEAX@Z` at `0x101701017`
- `sqldk!??_V@YAXPEAX@Z` at `0x101701023`
- `sqldk!??_V@YAXPEAX@Z` at `0x10170050d`
- `sqldk!??_V@YAXPEAX@Z` at `0x1017007e9`
- `sqldk!??_V@YAXPEAX@Z` at `0x101700fff`
- `sqldk!??_V@YAXPEAX@Z` at `0x10170100b`
- `sqldk!??_V@YAXPEAX@Z` at `0x101701017`
- `sqldk!??_V@YAXPEAX@Z` at `0x101701023`
- `sqlTsEs!?CompareStringWEnglishNoCase@@YAHKEPEFB_WH0H@Z` at `0x101700466`
- `sqlTsEs!?CompareStringWEnglishNoCase@@YAHKEPEFB_WH0H@Z` at `0x101700495`
- `sqlTsEs!?CompareStringWEnglishNoCase@@YAHKEPEFB_WH0H@Z` at `0x1017008ed`
- `sqlTsEs!?CompareStringWEnglishNoCase@@YAHKEPEFB_WH0H@Z` at `0x1017009bc`
- `sqlTsEs!?CompareStringWEnglishNoCase@@YAHKEPEFB_WH0H@Z` at `0x101700466`
- `sqlTsEs!?CompareStringWEnglishNoCase@@YAHKEPEFB_WH0H@Z` at `0x101700495`
- `sqlTsEs!?CompareStringWEnglishNoCase@@YAHKEPEFB_WH0H@Z` at `0x1017008ed`
- `sqlTsEs!?CompareStringWEnglishNoCase@@YAHKEPEFB_WH0H@Z` at `0x1017009bc`
- `sqlmin!?FUseReplicatedServerContext@@YA_NXZ` at `0x101700193`
- `sqlmin!?FUseReplicatedServerContext@@YA_NXZ` at `0x101700193`

## string_xrefs

- `0x101700950`: `.compute-0-svc`
- `0x10170042e`: `compute-0-0`
- `0x1017002b7`: `%ls\Polybase\Configuration`
- `0x1017008df`: `compute-`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall COledbRangeExternalComputation::GetProviderString(wchar_t *a1, unsigned int a2, char a3, UCHAR *a4)
{
  unsigned __int64 v5; // rsi
  __int64 v7; // rcx
  signed __int64 v8; // r8
  wchar_t v9; // ax
  wchar_t *v10; // rax
  __int64 v11; // rax
  __int64 v12; // rbx
  __int64 v13; // rdx
  void *v14; // r15
  __int64 v15; // rbx
  __int64 v16; // rdx
  wchar_t *v17; // r12
  __int64 v18; // rbx
  struct __crt_locale_pointers *DefaultLocale; // rax
  int v20; // ebx
  unsigned __int64 v21; // rbx
  unsigned __int64 v22; // rdx
  wchar_t *v23; // rcx
  wchar_t v24; // ax
  wchar_t *v25; // rax
  DWORD v26; // esi
  const wchar_t *v27; // r14
  __int64 v28; // r14
  __int64 v29; // rdx
  void *v30; // r14
  __int64 v31; // r14
  __int64 v32; // rdx
  DWORD EnvironmentVariableW; // eax
  __int64 v34; // rsi
  __int64 v35; // rdx
  wchar_t *v36; // rsi
  unsigned __int64 v37; // rcx
  wchar_t *v38; // rax
  unsigned __int64 v39; // r8
  unsigned __int64 v40; // rdx
  wchar_t *v41; // rcx
  __int64 v42; // r8
  char *v43; // r9
  wchar_t v44; // ax
  wchar_t *v45; // rax
  unsigned __int64 v46; // rcx
  wchar_t *v47; // rax
  unsigned __int64 v48; // r8
  unsigned __int64 v49; // rdx
  wchar_t *v50; // rcx
  __int64 v51; // r8
  char *v52; // r9
  wchar_t v53; // ax
  wchar_t *v54; // rax
  wchar_t *v55; // rsi
  unsigned __int64 v56; // rcx
  wchar_t *v57; // rax
  unsigned __int64 v58; // r8
  unsigned __int64 v59; // rdx
  wchar_t *v60; // rcx
  __int64 v61; // r8
  char *v62; // r9
  wchar_t v63; // ax
  wchar_t *v64; // rax
  unsigned __int64 v65; // rcx
  wchar_t *v66; // rax
  unsigned __int64 v67; // r8
  unsigned __int64 v68; // rdx
  wchar_t *v69; // rcx
  __int64 v70; // r8
  char *v71; // r9
  wchar_t v72; // ax
  wchar_t *v73; // rax
  unsigned __int64 v74; // rcx
  wchar_t *v75; // rax
  unsigned __int64 v76; // r8
  unsigned __int64 v77; // rdx
  wchar_t *v78; // rcx
  __int64 v79; // r8
  char *v80; // r9
  wchar_t v81; // ax
  wchar_t *v82; // rax
  unsigned __int64 v83; // rcx
  wchar_t *v84; // rax
  unsigned __int64 v85; // r8
  unsigned __int64 v86; // rdx
  wchar_t *v87; // rcx
  __int64 v88; // r8
  char *v89; // r14
  wchar_t v90; // ax
  wchar_t *v91; // rax
  unsigned __int64 v92; // rcx
  wchar_t *v93; // rax
  __int64 v94; // r8
  unsigned __int64 v95; // rdx
  wchar_t *v96; // rcx
  char *v97; // r9
  wchar_t v98; // ax
  wchar_t *v99; // rax
  unsigned __int64 v100; // rcx
  wchar_t *v101; // rax
  unsigned __int64 v102; // r8
  unsigned __int64 v103; // rdx
  wchar_t *v104; // rcx
  __int64 v105; // r8
  char *v106; // r9
  wchar_t v107; // ax
  wchar_t *v108; // rax
  unsigned __int64 v109; // rcx
  wchar_t *v110; // rax
  unsigned __int64 v111; // r8
  unsigned __int64 v112; // rdx
  wchar_t *v113; // rcx
  __int64 v114; // r8
  char *v115; // r9
  wchar_t v116; // ax
  wchar_t *v117; // rax
  unsigned __int64 v118; // rcx
  wchar_t *v119; // rax
  unsigned __int64 v120; // r8
  unsigned __int64 v121; // rdx
  wchar_t *v122; // rcx
  __int64 v123; // r8
  char *v124; // r9
  wchar_t v125; // ax
  wchar_t *v126; // rax
  const GUID *v127; // r14
  __int64 v128; // rax
  bool ComputerName; // [rsp+30h] [rbp-D0h]
  DWORD v130; // [rsp+34h] [rbp-CCh] BYREF
  LPWSTR lpBuffer; // [rsp+38h] [rbp-C8h]
  DWORD v132; // [rsp+40h] [rbp-C0h] BYREF
  DWORD nSize; // [rsp+44h] [rbp-BCh] BYREF
  HKEY v134; // [rsp+48h] [rbp-B8h] BYREF
  void *v135; // [rsp+50h] [rbp-B0h]
  wchar_t *v136; // [rsp+58h] [rbp-A8h]
  unsigned __int64 v137; // [rsp+60h] [rbp-A0h]
  PUCHAR pbBuffer; // [rsp+68h] [rbp-98h]
  void *v139; // [rsp+70h] [rbp-90h]
  __int64 v140; // [rsp+78h] [rbp-88h]
  void *v141; // [rsp+80h] [rbp-80h]
  wchar_t *v142; // [rsp+88h] [rbp-78h]
  LPWSTR v143; // [rsp+90h] [rbp-70h]
  wchar_t *v144; // [rsp+98h] [rbp-68h]
  wchar_t sz[264]; // [rsp+A0h] [rbp-60h] BYREF

  v140 = -2;
  pbBuffer = a4;
  v5 = a2;
  CPolybaseFeatureManager::MaybeInitPolybaseMode((CPolybaseFeatureManager *)&g_PolybaseFeatureManager);
  if ( dword_102EF7EC8 == 3 )
  {
    v7 = (unsigned int)v5;
    if ( v5 - 1 > 0x7FFFFFFE )
    {
      if ( (_DWORD)v5 )
        *a1 = 0;
    }
    else
    {
      v8 = (char *)L"InternalSharedMemory" - (char *)a1;
      do
      {
        if ( !(20LL - (unsigned int)v5 + v7) )
          break;
        v9 = *(wchar_t *)((char *)a1 + v8);
        if ( !v9 )
          break;
        *a1++ = v9;
        --v7;
      }
      while ( v7 );
      v10 = a1 - 1;
      if ( v7 )
        v10 = a1;
      *v10 = 0;
    }
    return;
  }
  if ( !CPolybaseFeatureManager::IsPolybaseProvisioned((CPolybaseFeatureManager *)&g_PolybaseFeatureManager, 1)
    || (FUseReplicatedServerContext() ? (v11 = qword_102ECFB00 + 28520) : (v11 = qword_102ECFB00 + 14864),
        !*(_BYTE *)(v11 + 13645)) )
  {
    ex_raise(74, 3, 16, 4, L"MSOLEDBSQL");
    return;
  }
  v12 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v13 = *(_QWORD *)(v12 + 256);
  if ( !v13 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v13 = *(_QWORD *)(v12 + 256);
  }
  v14 = operator new[](0x20Au, *(struct IMemObj **)(v13 + 1000), "sql\\ntdbms\\msql\\utils\\oledbrng.cpp", 7927, 3u);
  v139 = v14;
  v141 = v14;
  v15 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v16 = *(_QWORD *)(v15 + 256);
  if ( !v16 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v16 = *(_QWORD *)(v15 + 256);
  }
  v17 = (wchar_t *)operator new[](
                     0x20Au,
                     *(struct IMemObj **)(v16 + 1000),
                     "sql\\ntdbms\\msql\\utils\\oledbrng.cpp",
                     7928,
                     3u);
  v136 = v17;
  v142 = v17;
  v132 = 522;
  v18 = qword_102ECFB00 + 47954;
  DefaultLocale = GetDefaultLocale();
  v20 = StringCchPrintf_lW((wchar_t *)v14, 0x105u, L"%ls\\Polybase\\Configuration", DefaultLocale, v18);
  if ( v20 < 0 )
    ex_raise(74, 3, 16, 9, L"MSOLEDBSQL");
  if ( (unsigned int)IniRegOpenKeyExW(-2147483646, (int)v14, 0, 131097, &v134) )
    ex_raise(74, 3, 16, 10, L"MSOLEDBSQL");
  if ( (unsigned int)IniRegQueryValueExW((int)v134, (int)L"DmsControlChannelHostname", 0, 0, (LPBYTE)v17, &v132) )
  {
    IniRegCloseKey(v134);
  }
  else
  {
    IniRegCloseKey(v134);
    if ( v20 >= 0 )
      goto LABEL_29;
  }
  ex_raise(74, 3, 16, 5, L"MSOLEDBSQL");
LABEL_29:
  v21 = v5;
  if ( v5 - 1 > 0x7FFFFFFE )
  {
    if ( (_DWORD)v5 )
      *a1 = 0;
    goto LABEL_40;
  }
  v22 = v5;
  v23 = a1;
  do
  {
    if ( !(v22 + 7 - v5) )
      break;
    v24 = *(wchar_t *)((char *)v23 + (char *)L"Server=" - (char *)a1);
    if ( !v24 )
      break;
    *v23++ = v24;
    --v22;
  }
  while ( v22 );
  v25 = v23 - 1;
  if ( v22 )
    v25 = v23;
  *v25 = 0;
  if ( !v22 )
LABEL_40:
    ex_raise(74, 3, 16, 6, L"MSOLEDBSQL");
  v135 = 0;
  nSize = 0;
  v26 = v132 >> 1;
  if ( a3 )
  {
    v17 = (wchar_t *)L"compute-0-0";
    v26 = 12;
  }
  else
  {
    v27 = v136;
    if ( CompareStringWEnglishNoCase(1u, 0, v136, (unsigned __int64)(int)v132 >> 1, L"localhost", 9) == 2
      || CompareStringWEnglishNoCase(1u, 0, v27, (unsigned __int64)(int)v132 >> 1, L"127.0.0.1", 9) == 2 )
    {
      v28 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v29 = *(_QWORD *)(v28 + 256);
      if ( !v29 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v29 = *(_QWORD *)(v28 + 256);
      }
      v30 = operator new[](0x20u, *(struct IMemObj **)(v29 + 1000), "sql\\ntdbms\\msql\\utils\\oledbrng.cpp", 8003, 3u);
      if ( v30 )
        operator delete[](0);
      v135 = v30;
      nSize = 16;
      if ( GetComputerNameW((LPWSTR)v30, &nSize) )
      {
        v17 = (wchar_t *)v30;
        v26 = nSize;
      }
    }
  }
  v137 = v26;
  if ( (int)StringCchCatNW(a1, v21, v17, v26) < 0 )
    ex_raise(74, 3, 16, 7, L"MSOLEDBSQL");
  v31 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v32 = *(_QWORD *)(v31 + 256);
  if ( !v32 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v32 = *(_QWORD *)(v31 + 256);
  }
  lpBuffer = (LPWSTR)operator new[](
                       0x202u,
                       *(struct IMemObj **)(v32 + 1000),
                       "sql\\ntdbms\\msql\\utils\\oledbrng.cpp",
                       8025,
                       3u);
  v143 = lpBuffer;
  v130 = 257;
  ComputerName = GetComputerNameExW(ComputerNameDnsDomain, lpBuffer, &v130);
  if ( *(_BYTE *)(qword_102ECFB00 + 48768) && OsInfo::IsLinux(SOS_OS_OsInfo) )
  {
    if ( *(_BYTE *)(qword_102ECFB00 + 48768) && *(_BYTE *)(qword_102ECFB00 + 48777) )
    {
      if ( !ComputerName )
      {
        EnvironmentVariableW = GetEnvironmentVariableW(L"MSSQL_DOMAIN", lpBuffer, v130);
        if ( EnvironmentVariableW > v130 )
          ex_raise(74, 3, 16, 12, L"MSOLEDBSQL");
        v34 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
        v35 = *(_QWORD *)(v34 + 256);
        if ( !v35 )
        {
          SystemThread::MakeMiniSOSThread(0);
          v35 = *(_QWORD *)(v34 + 256);
        }
        v36 = (wchar_t *)operator new[](
                           0x82u,
                           *(struct IMemObj **)(v35 + 1000),
                           "sql\\ntdbms\\msql\\utils\\oledbrng.cpp",
                           8060,
                           3u);
        v144 = v36;
        if ( GetEnvironmentVariableW(L"MSSQL_SUBDOMAIN", v36, 0x41u) )
        {
          if ( v21 - 1 > 0x7FFFFFFE )
            goto LABEL_81;
          v37 = v21;
          v38 = a1;
          do
          {
            if ( !*v38 )
              break;
            ++v38;
            --v37;
          }
          while ( v37 );
          v39 = v37 ? v21 - v37 : 0LL;
          if ( !v37 )
            goto LABEL_81;
          v40 = v21 - v39;
          v41 = &a1[v39];
          if ( v21 != v39 )
          {
            v42 = 2;
            v43 = (char *)((char *)L"." - (char *)v41);
            do
            {
              if ( !v42 )
                break;
              v44 = *(wchar_t *)((char *)v41 + (_QWORD)v43);
              if ( !v44 )
                break;
              *v41++ = v44;
              --v42;
              --v40;
            }
            while ( v40 );
          }
          v45 = v41 - 1;
          if ( v40 )
            v45 = v41;
          *v45 = 0;
          if ( !v40 )
LABEL_81:
            ex_raise(74, 3, 16, 2, L"MSOLEDBSQL");
          if ( (int)StringCchCatNW(a1, v21, v36, 0x41u) < 0 )
            ex_raise(74, 3, 16, 3, L"MSOLEDBSQL");
        }
        operator delete[](v36);
      }
      if ( v21 - 1 > 0x7FFFFFFE )
        goto LABEL_101;
      v46 = v21;
      v47 = a1;
      do
      {
        if ( !*v47 )
          break;
        ++v47;
        --v46;
      }
      while ( v46 );
      v48 = v46 ? v21 - v46 : 0LL;
      if ( !v46 )
        goto LABEL_101;
      v49 = v21 - v48;
      v50 = &a1[v48];
      if ( v21 != v48 )
      {
        v51 = 2;
        v52 = (char *)((char *)L"." - (char *)v50);
        do
        {
          if ( !v51 )
            break;
          v53 = *(wchar_t *)((char *)v50 + (_QWORD)v52);
          if ( !v53 )
            break;
          *v50++ = v53;
          --v51;
          --v49;
        }
        while ( v49 );
      }
      v54 = v50 - 1;
      if ( v49 )
        v54 = v50;
      *v54 = 0;
      if ( !v49 )
LABEL_101:
        ex_raise(74, 3, 16, 26, L"MSOLEDBSQL");
      v55 = lpBuffer;
      if ( (int)StringCchCatNW(a1, v21, lpBuffer, v130) < 0 )
        ex_raise(74, 3, 16, 27, L"MSOLEDBSQL");
      goto LABEL_141;
    }
    if ( CompareStringWEnglishNoCase(0x80000001, 0, L"compute-", 8, v17, v26) == 2 )
    {
      if ( v21 - 1 > 0x7FFFFFFE )
        goto LABEL_121;
      v56 = v21;
      v57 = a1;
      do
      {
        if ( !*v57 )
          break;
        ++v57;
        --v56;
      }
      while ( v56 );
      v58 = v56 ? v21 - v56 : 0LL;
      if ( !v56 )
        goto LABEL_121;
      v59 = v21 - v58;
      v60 = &a1[v58];
      if ( v21 != v58 )
      {
        v61 = 15;
        v62 = (char *)((char *)L".compute-0-svc" - (char *)v60);
        do
        {
          if ( !v61 )
            break;
          v63 = *(wchar_t *)((char *)v60 + (_QWORD)v62);
          if ( !v63 )
            break;
          *v60++ = v63;
          --v61;
          --v59;
        }
        while ( v59 );
      }
      v64 = v60 - 1;
      if ( v59 )
        v64 = v60;
      *v64 = 0;
      if ( !v59 )
LABEL_121:
        ex_raise(74, 3, 16, 28, L"MSOLEDBSQL");
    }
    else if ( CompareStringWEnglishNoCase(0x80000001, 0, L"master-", 7, v17, v26) == 2 )
    {
      if ( v21 - 1 > 0x7FFFFFFE )
        goto LABEL_139;
      v65 = v21;
      v66 = a1;
      do
      {
        if ( !*v66 )
          break;
        ++v66;
        --v65;
      }
      while ( v65 );
      v67 = v65 ? v21 - v65 : 0LL;
      if ( !v65 )
        goto LABEL_139;
      v68 = v21 - v67;
      v69 = &a1[v67];
      if ( v21 != v67 )
      {
        v70 = 12;
        v71 = (char *)((char *)L".master-svc" - (char *)v69);
        do
        {
          if ( !v70 )
            break;
          v72 = *(wchar_t *)((char *)v69 + (_QWORD)v71);
          if ( !v72 )
            break;
          *v69++ = v72;
          --v70;
          --v68;
        }
        while ( v68 );
      }
      v73 = v69 - 1;
      if ( v68 )
        v73 = v69;
      *v73 = 0;
      if ( !v68 )
LABEL_139:
        ex_raise(74, 3, 16, 29, L"MSOLEDBSQL");
    }
  }
  v55 = lpBuffer;
LABEL_141:
  if ( v21 - 1 > 0x7FFFFFFE )
    goto LABEL_157;
  v74 = v21;
  v75 = a1;
  do
  {
    if ( !*v75 )
      break;
    ++v75;
    --v74;
  }
  while ( v74 );
  v76 = v74 ? v21 - v74 : 0LL;
  if ( !v74 )
    goto LABEL_157;
  v77 = v21 - v76;
  v78 = &a1[v76];
  if ( v21 != v76 )
  {
    v79 = 26;
    v80 = (char *)((char *)L",17001;ServerSPN=DWENGSvc/" - (char *)v78);
    do
    {
      if ( !v79 )
        break;
      v81 = *(wchar_t *)((char *)v78 + (_QWORD)v80);
      if ( !v81 )
        break;
      *v78++ = v81;
      --v79;
      --v77;
    }
    while ( v77 );
  }
  v82 = v78 - 1;
  if ( v77 )
    v82 = v78;
  *v82 = 0;
  if ( !v77 )
LABEL_157:
    ex_raise(74, 3, 16, 14, L"MSOLEDBSQL");
  if ( (int)StringCchCatNW(a1, v21, v17, v137) < 0 )
    ex_raise(74, 3, 16, 17, L"MSOLEDBSQL");
  if ( ComputerName )
  {
    if ( v21 - 1 > 0x7FFFFFFE )
      goto LABEL_177;
    v83 = v21;
    v84 = a1;
    do
    {
      if ( !*v84 )
        break;
      ++v84;
      --v83;
    }
    while ( v83 );
    v85 = v83 ? v21 - v83 : 0LL;
    if ( !v83 )
      goto LABEL_177;
    v86 = v21 - v85;
    v87 = &a1[v85];
    if ( v21 != v85 )
    {
      v88 = 1;
      v89 = (char *)((char *)L"." - (char *)v87);
      do
      {
        if ( !v88 )
          break;
        v90 = *(wchar_t *)((char *)v87 + (_QWORD)v89);
        if ( !v90 )
          break;
        *v87++ = v90;
        --v88;
        --v86;
      }
      while ( v86 );
    }
    v91 = v87 - 1;
    if ( v86 )
      v91 = v87;
    *v91 = 0;
    if ( !v86 )
LABEL_177:
      ex_raise(74, 3, 16, 24, L"MSOLEDBSQL");
    if ( (int)StringCchCatNW(a1, v21, v55, v130) < 0 )
      ex_raise(74, 3, 16, 25, L"MSOLEDBSQL");
  }
  if ( v21 - 1 > 0x7FFFFFFE )
    goto LABEL_196;
  v92 = v21;
  v93 = a1;
  do
  {
    if ( !*v93 )
      break;
    ++v93;
    --v92;
  }
  while ( v92 );
  v94 = v92 ? v21 - v92 : 0LL;
  if ( !v92 )
    goto LABEL_196;
  v95 = v21 - v94;
  v96 = &a1[v94];
  if ( v21 != v94 )
  {
    v94 = 18;
    v97 = (char *)((char *)L":17001;Timeout=60;" - (char *)v96);
    do
    {
      if ( !v94 )
        break;
      v98 = *(wchar_t *)((char *)v96 + (_QWORD)v97);
      if ( !v98 )
        break;
      *v96++ = v98;
      --v94;
      --v95;
    }
    while ( v95 );
  }
  v99 = v96 - 1;
  if ( v95 )
    v99 = v96;
  *v99 = 0;
  if ( !v95 )
LABEL_196:
    ex_raise(74, 3, 16, 8, L"MSOLEDBSQL");
  if ( *(_BYTE *)((*(__int64 (__fastcall **)(struct IServerConfiguration *, unsigned __int64, __int64))(*(_QWORD *)s_pServerConf + 504LL))(
                    s_pServerConf,
                    v95,
                    v94)
                + 1337) )
  {
    if ( v21 - 1 > 0x7FFFFFFE )
      goto LABEL_214;
    v100 = v21;
    v101 = a1;
    do
    {
      if ( !*v101 )
        break;
      ++v101;
      --v100;
    }
    while ( v100 );
    v102 = v100 ? v21 - v100 : 0LL;
    if ( !v100 )
      goto LABEL_214;
    v103 = v21 - v102;
    v104 = &a1[v102];
    if ( v21 != v102 )
    {
      v105 = 12;
      v106 = (char *)((char *)L"Encrypt=Yes;" - (char *)v104);
      do
      {
        if ( !v105 )
          break;
        v107 = *(wchar_t *)((char *)v104 + (_QWORD)v106);
        if ( !v107 )
          break;
        *v104++ = v107;
        --v105;
        --v103;
      }
      while ( v103 );
    }
    v108 = v104 - 1;
    if ( v103 )
      v108 = v104;
    *v108 = 0;
    if ( !v103 )
LABEL_214:
      ex_raise(74, 3, 16, 11, L"MSOLEDBSQL");
    if ( !OsInfo::IsLinux(SOS_OS_OsInfo) || !*(_BYTE *)(qword_102ECFB00 + 48768) )
    {
      if ( v21 - 1 > 0x7FFFFFFE )
        goto LABEL_233;
      v109 = v21;
      v110 = a1;
      do
      {
        if ( !*v110 )
          break;
        ++v110;
        --v109;
      }
      while ( v109 );
      v111 = v109 ? v21 - v109 : 0LL;
      if ( !v109 )
        goto LABEL_233;
      v112 = v21 - v111;
      v113 = &a1[v111];
      if ( v21 != v111 )
      {
        v114 = 27;
        v115 = (char *)((char *)L"TrustServerCertificate=Yes;" - (char *)v113);
        do
        {
          if ( !v114 )
            break;
          v116 = *(wchar_t *)((char *)v113 + (_QWORD)v115);
          if ( !v116 )
            break;
          *v113++ = v116;
          --v114;
          --v112;
        }
        while ( v112 );
      }
      v117 = v113 - 1;
      if ( v112 )
        v117 = v113;
      *v117 = 0;
      if ( !v112 )
LABEL_233:
        ex_raise(74, 3, 16, 23, L"MSOLEDBSQL");
    }
  }
  if ( v21 - 1 > 0x7FFFFFFE )
    goto LABEL_250;
  v118 = v21;
  v119 = a1;
  do
  {
    if ( !*v119 )
      break;
    ++v119;
    --v118;
  }
  while ( v118 );
  v120 = v118 ? v21 - v118 : 0LL;
  if ( !v118 )
    goto LABEL_250;
  v121 = v21 - v120;
  v122 = &a1[v120];
  if ( v21 != v120 )
  {
    v123 = 4;
    v124 = (char *)((char *)L"APP=" - (char *)v122);
    do
    {
      if ( !v123 )
        break;
      v125 = *(wchar_t *)((char *)v122 + (_QWORD)v124);
      if ( !v125 )
        break;
      *v122++ = v125;
      --v123;
      --v121;
    }
    while ( v121 );
  }
  v126 = v122 - 1;
  if ( v121 )
    v126 = v122;
  *v126 = 0;
  if ( !v121 )
LABEL_250:
    ex_raise(74, 3, 16, 19, L"MSOLEDBSQL");
  v127 = (const GUID *)pbBuffer;
  if ( BCryptGenRandom(0, pbBuffer, 0x10u, 2u) < 0 )
    ex_raise(74, 3, 16, 20, L"MSOLEDBSQL");
  memset_0(sz, 0, 0x208u);
  if ( !StringFromGUID2(v127, sz, 260) )
    ex_raise(74, 3, 16, 21, L"MSOLEDBSQL");
  v128 = -1;
  do
    ++v128;
  while ( sz[v128] );
  if ( (int)StringCchCatNW(a1, v21, sz, (unsigned int)v128) < 0 )
    ex_raise(74, 3, 16, 22, L"MSOLEDBSQL");
  operator delete[](v55);
  operator delete[](v135);
  operator delete[](v136);
  operator delete[](v139);
}

```

## disassembly

```asm
0x1017000b0  push    rbp
0x1017000b2  push    rsi
0x1017000b3  push    rdi
0x1017000b4  push    r12
0x1017000b6  push    r13
0x1017000b8  push    r14
0x1017000ba  push    r15
0x1017000bc  lea     rbp, [rsp-1C0h]
0x1017000c4  sub     rsp, 2C0h
0x1017000cb  mov     [rsp+2F0h+var_278], 0FFFFFFFFFFFFFFFEh
0x1017000d4  mov     [rsp+2F0h+arg_10], rbx
0x1017000dc  mov     rax, cs:__security_cookie
0x1017000e3  xor     rax, rsp
0x1017000e6  mov     [rbp+1F0h+var_40], rax
0x1017000ed  mov     [rsp+2F0h+pbBuffer], r9
0x1017000f2  movzx   r14d, r8b
0x1017000f6  mov     esi, edx
0x1017000f8  mov     rdi, rcx
0x1017000fb  lea     rcx, ?g_PolybaseFeatureManager@@3VCPolybaseFeatureManager@@A; this
0x101700102  call    ?MaybeInitPolybaseMode@CPolybaseFeatureManager@@AEAAXXZ; CPolybaseFeatureManager::MaybeInitPolybaseMode(void)
0x101700107  mov     eax, cs:dword_102EF7EC8
0x10170010d  cmp     eax, 3
0x101700110  jnz     short loc_10170017D
0x101700112  mov     ecx, esi
0x101700114  lea     rax, [rsi-1]
0x101700118  cmp     rax, 7FFFFFFEh
0x10170011e  ja      short loc_101700169
0x101700120  mov     edx, 14h
0x101700125  sub     rdx, rcx
0x101700128  lea     r8, aInternalshared; "InternalSharedMemory"
0x10170012f  sub     r8, rdi
0x101700132  lea     rax, [rdx+rcx]
0x101700136  test    rax, rax
0x101700139  jz      short loc_101700152
0x10170013b  movzx   eax, word ptr [r8+rdi]
0x101700140  test    ax, ax
0x101700143  jz      short loc_101700152
0x101700145  mov     [rdi], ax
0x101700148  add     rdi, 2
0x10170014c  sub     rcx, 1
0x101700150  jnz     short loc_101700132
0x101700152  lea     rax, [rdi-2]
0x101700156  test    rcx, rcx
0x101700159  cmovnz  rax, rdi
0x10170015d  xor     r15d, r15d
0x101700160  mov     [rax], r15w
0x101700164  jmp     loc_10170104D
0x101700169  test    esi, esi
0x10170016b  jz      loc_10170104D
0x101700171  xor     r15d, r15d
0x101700174  mov     [rdi], r15w
0x101700178  jmp     loc_10170104D
0x10170017d  mov     dl, 1; bool
0x10170017f  lea     rcx, ?g_PolybaseFeatureManager@@3VCPolybaseFeatureManager@@A; this
0x101700186  call    ?IsPolybaseProvisioned@CPolybaseFeatureManager@@QEAA_N_N@Z; CPolybaseFeatureManager::IsPolybaseProvisioned(bool)
0x10170018b  test    al, al
0x10170018d  jz      loc_10170102B
0x101700193  call    cs:__imp_?FUseReplicatedServerContext@@YA_NXZ; FUseReplicatedServerContext(void)
0x101700199  test    al, al
0x10170019b  mov     rax, cs:qword_102ECFB00
0x1017001a2  jnz     short loc_1017001AC
0x1017001a4  add     rax, 3A10h
0x1017001aa  jmp     short loc_1017001B2
0x1017001ac  add     rax, 6F68h
0x1017001b2  cmp     byte ptr [rax+354Dh], 0
0x1017001b9  jz      loc_10170102B
0x1017001bf  mov     rdx, gs:58h
0x1017001c8  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1017001cf  mov     ecx, [rax]
0x1017001d1  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1017001d8  mov     ebx, [rax]
0x1017001da  add     rbx, [rdx+rcx*8]
0x1017001de  mov     rdx, [rbx+100h]
0x1017001e5  test    rdx, rdx
0x1017001e8  jnz     short loc_1017001F9
0x1017001ea  xor     ecx, ecx
0x1017001ec  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1017001f2  mov     rdx, [rbx+100h]
0x1017001f9  mov     byte ptr [rsp+2F0h+var_2D0], 3
0x1017001fe  mov     r9d, 1EF7h
0x101700204  lea     r8, aSqlNtdbmsMsqlU_2; "sql\\ntdbms\\msql\\utils\\oledbrng.cpp"
0x10170020b  mov     rdx, [rdx+3E8h]
0x101700212  mov     ecx, 20Ah
0x101700217  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x10170021d  mov     r15, rax
0x101700220  mov     [rsp+2F0h+var_280], rax
0x101700225  mov     [rbp+1F0h+var_270], rax
0x101700229  mov     r8, gs:58h
0x101700232  mov     rcx, cs:__imp_SystemThread_TlsIndex
0x101700239  mov     edx, [rcx]
0x10170023b  mov     rcx, cs:__imp_SystemThread_TlsOffset
0x101700242  mov     ebx, [rcx]
0x101700244  add     rbx, [r8+rdx*8]
0x101700248  mov     rdx, [rbx+100h]
0x10170024f  test    rdx, rdx
0x101700252  jnz     short loc_101700263
0x101700254  xor     ecx, ecx
0x101700256  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10170025c  mov     rdx, [rbx+100h]
0x101700263  mov     byte ptr [rsp+2F0h+var_2D0], 3
0x101700268  mov     r9d, 1EF8h
0x10170026e  lea     r8, aSqlNtdbmsMsqlU_2; "sql\\ntdbms\\msql\\utils\\oledbrng.cpp"
0x101700275  mov     rdx, [rdx+3E8h]
0x10170027c  mov     ecx, 20Ah
0x101700281  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x101700287  mov     r12, rax
0x10170028a  mov     [rsp+2F0h+var_298], rax
0x10170028f  mov     [rbp+1F0h+var_268], rax
0x101700293  mov     [rsp+2F0h+var_2B0], 20Ah
0x10170029b  mov     rbx, cs:qword_102ECFB00
0x1017002a2  add     rbx, 0BB52h
0x1017002a9  call    cs:__imp_?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ; GetDefaultLocale(void)
0x1017002af  mov     r9, rax; struct __crt_locale_pointers *
0x1017002b2  mov     [rsp+2F0h+var_2D0], rbx
0x1017002b7  lea     r8, aLsPolybaseConf; "%ls\\Polybase\\Configuration"
0x1017002be  mov     edx, 105h; unsigned __int64
0x1017002c3  mov     rcx, r15; wchar_t *
0x1017002c6  call    ?StringCchPrintf_lW@@YAJPEA_W_KPEB_WPEAU__crt_locale_pointers@@ZZ; StringCchPrintf_lW(wchar_t *,unsigned __int64,wchar_t const *,__crt_locale_pointers *,...)
0x1017002cb  mov     ebx, eax
0x1017002cd  lea     r13, aMsoledbsql; "MSOLEDBSQL"
0x1017002d4  test    eax, eax
0x1017002d6  jns     short loc_1017002F3
0x1017002d8  mov     [rsp+2F0h+var_2D0], r13
0x1017002dd  mov     edx, 3
0x1017002e2  lea     ecx, [rdx+47h]
0x1017002e5  lea     r9d, [rdx+6]
0x1017002e9  lea     r8d, [rdx+0Dh]
0x1017002ed  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x1017002f3  lea     rax, [rsp+2F0h+var_2A8]
0x1017002f8  mov     [rsp+2F0h+var_2D0], rax; PHKEY
0x1017002fd  mov     r9d, 20019h; int
0x101700303  xor     r8d, r8d; int
0x101700306  mov     rdx, r15; int
0x101700309  mov     rcx, 0FFFFFFFF80000002h; int
0x101700310  call    IniRegOpenKeyExW
0x101700315  test    eax, eax
0x101700317  jz      short loc_101700334
0x101700319  mov     [rsp+2F0h+var_2D0], r13
0x10170031e  mov     edx, 3
0x101700323  lea     ecx, [rdx+47h]
0x101700326  lea     r9d, [rdx+7]
0x10170032a  lea     r8d, [rdx+0Dh]
0x10170032e  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x101700334  lea     rax, [rsp+2F0h+var_2B0]
0x101700339  mov     [rsp+2F0h+var_2C8], rax; LPDWORD
0x10170033e  mov     [rsp+2F0h+var_2D0], r12; LPBYTE
0x101700343  xor     r9d, r9d; int
0x101700346  xor     r8d, r8d; int
0x101700349  lea     rdx, aDmscontrolchan_0; "DmsControlChannelHostname"
0x101700350  mov     rcx, [rsp+2F0h+var_2A8]; int
0x101700355  call    IniRegQueryValueExW
0x10170035a  mov     rcx, [rsp+2F0h+var_2A8]
0x10170035f  test    eax, eax
0x101700361  jz      short loc_10170036A
0x101700363  call    IniRegCloseKey
0x101700368  jmp     short loc_101700373
0x10170036a  call    IniRegCloseKey
0x10170036f  test    ebx, ebx
0x101700371  jns     short loc_10170038E
0x101700373  mov     [rsp+2F0h+var_2D0], r13
0x101700378  mov     edx, 3
0x10170037d  lea     ecx, [rdx+47h]
0x101700380  lea     r9d, [rdx+2]
0x101700384  lea     r8d, [rdx+0Dh]
0x101700388  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x10170038e  mov     rbx, rsi
0x101700391  lea     rax, [rsi-1]
0x101700395  xor     r15d, r15d
0x101700398  cmp     rax, 7FFFFFFEh
0x10170039e  ja      short loc_1017003F3
0x1017003a0  mov     rdx, rbx
0x1017003a3  mov     rcx, rdi
0x1017003a6  mov     r8d, 7
0x1017003ac  sub     r8, rbx
0x1017003af  lea     r9, aServer_1; "Server="
0x1017003b6  sub     r9, rdi
0x1017003b9  nop     dword ptr [rax+00000000h]
0x1017003c0  lea     rax, [rdx+r8]
0x1017003c4  test    rax, rax
0x1017003c7  jz      short loc_1017003E0
0x1017003c9  movzx   eax, word ptr [r9+rcx]
0x1017003ce  test    ax, ax
0x1017003d1  jz      short loc_1017003E0
0x1017003d3  mov     [rcx], ax
0x1017003d6  add     rcx, 2
0x1017003da  sub     rdx, 1
0x1017003de  jnz     short loc_1017003C0
0x1017003e0  lea     rax, [rcx-2]
0x1017003e4  test    rdx, rdx
0x1017003e7  cmovnz  rax, rcx
0x1017003eb  mov     [rax], r15w
0x1017003ef  jnz     short loc_101700416
0x1017003f1  jmp     short loc_1017003FB
0x1017003f3  test    esi, esi
0x1017003f5  jz      short loc_1017003FB
0x1017003f7  mov     [rdi], r15w
0x1017003fb  mov     [rsp+2F0h+var_2D0], r13
0x101700400  mov     edx, 3
0x101700405  lea     ecx, [rdx+47h]
0x101700408  lea     r9d, [rdx+3]
0x10170040c  lea     r8d, [rdx+0Dh]
0x101700410  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x101700416  mov     [rsp+2F0h+var_2A0], r15
0x10170041b  mov     [rsp+2F0h+nSize], r15d
0x101700420  movsxd  rax, [rsp+2F0h+var_2B0]
0x101700425  mov     esi, eax
0x101700427  shr     esi, 1
0x101700429  test    r14b, r14b
0x10170042c  jz      short loc_10170043F
0x10170042e  lea     r12, aCompute00; "compute-0-0"
0x101700435  mov     esi, 0Ch
0x10170043a  jmp     loc_101700539
0x10170043f  mov     r9, rax
0x101700442  shr     r9, 1
0x101700445  mov     dword ptr [rsp+2F0h+var_2C8], 9
0x10170044d  lea     rcx, aLocalhost; "localhost"
0x101700454  mov     [rsp+2F0h+var_2D0], rcx
0x101700459  mov     r14, [rsp+2F0h+var_298]
0x10170045e  mov     r8, r14
0x101700461  xor     edx, edx
0x101700463  lea     ecx, [rdx+1]
0x101700466  call    cs:__imp_?CompareStringWEnglishNoCase@@YAHKEPEFB_WH0H@Z; CompareStringWEnglishNoCase(ulong,uchar,wchar_t const *,int,wchar_t const *,int)
0x10170046c  cmp     eax, 2
0x10170046f  jz      short loc_1017004A4
0x101700471  movsxd  r9, [rsp+2F0h+var_2B0]
0x101700476  shr     r9, 1
0x101700479  mov     dword ptr [rsp+2F0h+var_2C8], 9
0x101700481  lea     rcx, a127001; "127.0.0.1"
0x101700488  mov     [rsp+2F0h+var_2D0], rcx
0x10170048d  mov     r8, r14
0x101700490  xor     edx, edx
0x101700492  lea     ecx, [rdx+1]
0x101700495  call    cs:__imp_?CompareStringWEnglishNoCase@@YAHKEPEFB_WH0H@Z; CompareStringWEnglishNoCase(ulong,uchar,wchar_t const *,int,wchar_t const *,int)
0x10170049b  cmp     eax, 2
0x10170049e  jnz     loc_101700539
0x1017004a4  mov     rdx, gs:58h
0x1017004ad  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1017004b4  mov     ecx, [rax]
0x1017004b6  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1017004bd  mov     r14d, [rax]
0x1017004c0  add     r14, [rdx+rcx*8]
0x1017004c4  mov     rdx, [r14+100h]
0x1017004cb  test    rdx, rdx
0x1017004ce  jnz     short loc_1017004DF
0x1017004d0  xor     ecx, ecx
0x1017004d2  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1017004d8  mov     rdx, [r14+100h]
0x1017004df  mov     byte ptr [rsp+2F0h+var_2D0], 3
0x1017004e4  mov     r9d, 1F43h
0x1017004ea  lea     r8, aSqlNtdbmsMsqlU_2; "sql\\ntdbms\\msql\\utils\\oledbrng.cpp"
0x1017004f1  mov     rdx, [rdx+3E8h]
0x1017004f8  mov     ecx, 20h ; ' '
0x1017004fd  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x101700503  mov     r14, rax
0x101700506  test    rax, rax
0x101700509  jz      short loc_101700513
0x10170050b  xor     ecx, ecx
0x10170050d  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x101700513  mov     [rsp+2F0h+var_2A0], r14
0x101700518  mov     [rsp+2F0h+nSize], 10h
0x101700520  lea     rdx, [rsp+2F0h+nSize]; nSize
0x101700525  mov     rcx, r14; lpBuffer
0x101700528  call    cs:__imp_GetComputerNameW
0x10170052e  test    eax, eax
0x101700530  jz      short loc_101700539
0x101700532  mov     r12, r14
0x101700535  mov     esi, [rsp+2F0h+nSize]
0x101700539  mov     eax, esi
0x10170053b  mov     [rsp+2F0h+var_290], rax
0x101700540  mov     r9d, esi; unsigned __int64
0x101700543  mov     r8, r12; wchar_t *
0x101700546  mov     rdx, rbx; unsigned __int64
0x101700549  mov     rcx, rdi; wchar_t *
0x10170054c  call    ?StringCchCatNW@@YAJPEA_W_KPEB_W1@Z; StringCchCatNW(wchar_t *,unsigned __int64,wchar_t const *,unsigned __int64)
0x101700551  test    eax, eax
0x101700553  jns     short loc_101700570
0x101700555  mov     [rsp+2F0h+var_2D0], r13
0x10170055a  mov     edx, 3
0x10170055f  lea     ecx, [rdx+47h]
0x101700562  lea     r9d, [rdx+4]
0x101700566  lea     r8d, [rdx+0Dh]
0x10170056a  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x101700570  mov     rdx, gs:58h
0x101700579  mov     rax, cs:__imp_SystemThread_TlsIndex
0x101700580  mov     ecx, [rax]
0x101700582  mov     rax, cs:__imp_SystemThread_TlsOffset
0x101700589  mov     r14d, [rax]
0x10170058c  add     r14, [rdx+rcx*8]
0x101700590  mov     rdx, [r14+100h]
0x101700597  test    rdx, rdx
0x10170059a  jnz     short loc_1017005AB
0x10170059c  xor     ecx, ecx
0x10170059e  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1017005a4  mov     rdx, [r14+100h]
0x1017005ab  mov     byte ptr [rsp+2F0h+var_2D0], 3
0x1017005b0  mov     r9d, 1F59h
0x1017005b6  lea     r8, aSqlNtdbmsMsqlU_2; "sql\\ntdbms\\msql\\utils\\oledbrng.cpp"
0x1017005bd  mov     rdx, [rdx+3E8h]
0x1017005c4  mov     ecx, 202h
0x1017005c9  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
  ... truncated ...
```
