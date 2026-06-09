# SpPolybaseJoinGroup(CCompExecCtxt const &,CSpecProcRuntimeParams const * const,CParamExchange * const,CXVariant * const)

- ea: `0x10122fa50`
- end: `0x10123077e`
- name: `?SpPolybaseJoinGroup@@YAXAEBVCCompExecCtxt@@QEBVCSpecProcRuntimeParams@@QEAVCParamExchange@@QEAVCXVariant@@@Z`
- size: `3374`
- prototype: `void __fastcall(const struct CCompExecCtxt *, const struct CSpecProcRuntimeParams *const, struct CParamExchange *const, struct CXVariant *const)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x100401070`
- `0x100401090`
- `0x1004132a0`
- `0x100430960`
- `0x1005511a0`
- `0x10055a5d0`
- `0x1011ebad0`
- `0x1011ec140`
- `0x10122fa50`

## import_xrefs

- `KERNEL32!lstrcmpiW` at `0x1012305aa`
- `KERNEL32!lstrcmpiW` at `0x1012305aa`
- `ADVAPI32!RegQueryValueExW` at `0x101230075`
- `ADVAPI32!RegQueryValueExW` at `0x101230117`
- `ADVAPI32!RegQueryValueExW` at `0x101230325`
- `ADVAPI32!RegQueryValueExW` at `0x101230365`
- `ADVAPI32!RegQueryValueExW` at `0x101230075`
- `ADVAPI32!RegQueryValueExW` at `0x101230117`
- `ADVAPI32!RegQueryValueExW` at `0x101230325`
- `ADVAPI32!RegQueryValueExW` at `0x101230365`
- `ADVAPI32!RegOpenKeyExW` at `0x101230047`
- `ADVAPI32!RegOpenKeyExW` at `0x10123063f`
- `ADVAPI32!RegOpenKeyExW` at `0x101230047`
- `ADVAPI32!RegOpenKeyExW` at `0x10123063f`
- `ADVAPI32!RegSetValueExW` at `0x10123013d`
- `ADVAPI32!RegSetValueExW` at `0x101230219`
- `ADVAPI32!RegSetValueExW` at `0x1012302b2`
- `ADVAPI32!RegSetValueExW` at `0x101230393`
- `ADVAPI32!RegSetValueExW` at `0x101230451`
- `ADVAPI32!RegSetValueExW` at `0x1012304d6`
- `ADVAPI32!RegSetValueExW` at `0x10123067e`
- `ADVAPI32!RegSetValueExW` at `0x10123013d`
- `ADVAPI32!RegSetValueExW` at `0x101230219`
- `ADVAPI32!RegSetValueExW` at `0x1012302b2`
- `ADVAPI32!RegSetValueExW` at `0x101230393`
- `ADVAPI32!RegSetValueExW` at `0x101230451`
- `ADVAPI32!RegSetValueExW` at `0x1012304d6`
- `ADVAPI32!RegSetValueExW` at `0x10123067e`
- `ADVAPI32!RegCloseKey` at `0x101230151`
- `ADVAPI32!RegCloseKey` at `0x101230187`
- `ADVAPI32!RegCloseKey` at `0x101230229`
- `ADVAPI32!RegCloseKey` at `0x1012302c2`
- `ADVAPI32!RegCloseKey` at `0x1012303a7`
- `ADVAPI32!RegCloseKey` at `0x1012303e4`
- `ADVAPI32!RegCloseKey` at `0x101230461`
- `ADVAPI32!RegCloseKey` at `0x1012304e6`
- `ADVAPI32!RegCloseKey` at `0x101230530`
- `ADVAPI32!RegCloseKey` at `0x10123068e`
- `ADVAPI32!RegCloseKey` at `0x1012306d8`
- `ADVAPI32!RegCloseKey` at `0x101230151`
- `ADVAPI32!RegCloseKey` at `0x101230187`
- `ADVAPI32!RegCloseKey` at `0x101230229`
- `ADVAPI32!RegCloseKey` at `0x1012302c2`
- `ADVAPI32!RegCloseKey` at `0x1012303a7`
- `ADVAPI32!RegCloseKey` at `0x1012303e4`
- `ADVAPI32!RegCloseKey` at `0x101230461`
- `ADVAPI32!RegCloseKey` at `0x1012304e6`
- `ADVAPI32!RegCloseKey` at `0x101230530`
- `ADVAPI32!RegCloseKey` at `0x10123068e`
- `ADVAPI32!RegCloseKey` at `0x1012306d8`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x10123058d`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x1012305df`
- `sqldk!?SOS_OS_OsInfo@@3VOsInfo@@A` at `0x10122fb72`
- `sqldk!?SOS_OS_OsInfo@@3VOsInfo@@A` at `0x10122fbab`
- `sqldk!?SOS_OS_OsInfo@@3VOsInfo@@A` at `0x101230578`
- `sqldk!?GetOperatingSystemName@OsInfo@@QEBAQEB_WXZ` at `0x10122fbb2`
- `sqldk!?GetOperatingSystemName@OsInfo@@QEBAQEB_WXZ` at `0x10122fbb2`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x10122fffd`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x1012305b4`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x1012305f5`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x10122fffd`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x1012305b4`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x1012305f5`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x10123016b`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x1012301a1`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x101230243`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x1012302dc`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x1012303c1`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x1012303fe`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x10123047b`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x101230500`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x101230549`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x1012306a8`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x1012306f5`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x10123016b`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x1012301a1`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x101230243`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x1012302dc`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x1012303c1`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x1012303fe`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x10123047b`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x101230500`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x101230549`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x1012306a8`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x1012306f5`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10122fae3`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10122fb6c`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10122fbfd`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10122fcb0`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10122fce0`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10122fdc4`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10122fe2e`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10122fe7a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10122fea2`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10122feeb`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10122ff84`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1012301d0`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101230270`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101230302`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101230426`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1012304a1`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101230526`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10123056a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1012306ce`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101230716`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10122fae3`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10122fb6c`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10122fbfd`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10122fcb0`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10122fce0`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10122fdc4`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10122fe2e`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10122fe7a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10122fea2`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10122feeb`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10122ff84`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1012301d0`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101230270`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101230302`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101230426`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1012304a1`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101230526`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10123056a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1012306ce`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101230716`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10122ffe2`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1012300e3`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10122ffe2`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1012300e3`
- `sqldk!?IsXPlatInstance@OsInfo@@QEBA?B_NXZ` at `0x10122fb79`
- `sqldk!?IsXPlatInstance@OsInfo@@QEBA?B_NXZ` at `0x10123057f`
- `sqldk!?IsXPlatInstance@OsInfo@@QEBA?B_NXZ` at `0x10122fb79`
- `sqldk!?IsXPlatInstance@OsInfo@@QEBA?B_NXZ` at `0x10123057f`
- `sqldk!SystemThread_TlsIndex` at `0x10122fcf5`
- `sqldk!SystemThread_TlsIndex` at `0x10122ff93`
- `sqldk!SystemThread_TlsIndex` at `0x101230094`
- `sqldk!SystemThread_TlsOffset` at `0x10122fcfe`
- `sqldk!SystemThread_TlsOffset` at `0x10122ff9c`
- `sqldk!SystemThread_TlsOffset` at `0x10123009d`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10122fd19`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10122ffb7`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1012300b8`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10122fd19`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10122ffb7`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1012300b8`
- `sqldk!??_V@YAXPEAX@Z` at `0x1012301da`
- `sqldk!??_V@YAXPEAX@Z` at `0x10123073a`
- `sqldk!??_V@YAXPEAX@Z` at `0x101230744`
- `sqldk!??_V@YAXPEAX@Z` at `0x10123074e`
- `sqldk!??_V@YAXPEAX@Z` at `0x1012301da`
- `sqldk!??_V@YAXPEAX@Z` at `0x10123073a`
- `sqldk!??_V@YAXPEAX@Z` at `0x101230744`
- `sqldk!??_V@YAXPEAX@Z` at `0x10123074e`
- `sqlTsEs!?PwszXvtName@@YAPEB_WE@Z` at `0x10122fe07`
- `sqlTsEs!?PwszXvtName@@YAPEB_WE@Z` at `0x10122fe5a`
- `sqlTsEs!?PwszXvtName@@YAPEB_WE@Z` at `0x10122fe07`
- `sqlTsEs!?PwszXvtName@@YAPEB_WE@Z` at `0x10122fe5a`
- `sqlmin!?FUseReplicatedServerContext@@YA_NXZ` at `0x10122fb28`
- `sqlmin!?FUseReplicatedServerContext@@YA_NXZ` at `0x10122fb28`
- `sqlmin!?IsPolybaseProvisioned@@YA_NXZ` at `0x10122faf9`
- `sqlmin!?IsPolybaseProvisioned@@YA_NXZ` at `0x10122faf9`
- `sqlmin!?GetMasterDbId@@YAGXZ` at `0x10122fc03`
- `sqlmin!?GetMasterDbId@@YAGXZ` at `0x10122fc03`

## string_xrefs

- `0x1012305bd`: `SYSTEM\CurrentControlSet\Services\SQLPBENGINE`
- `0x101230603`: `SYSTEM\CurrentControlSet\Services\SQLPBENGINE`
- `0x101230006`: `\Polybase\Configuration`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall SpPolybaseJoinGroup(
        const struct CCompExecCtxt *a1,
        __int64 **a2,
        struct CParamExchange *const a3,
        struct CXVariant *const a4)
{
  __int64 v7; // rax
  __int64 v8; // rsi
  const wchar_t *OperatingSystemName; // rax
  __int64 v10; // rdx
  unsigned __int16 MasterDbId; // ax
  __int64 v12; // r15
  __int64 v13; // rdi
  __int64 v14; // rax
  struct IMemObj *v15; // r12
  const struct CXVariant *v16; // rax
  BYTE *v17; // rax
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rax
  __int64 v21; // rdi
  char v22; // dl
  unsigned __int8 v23; // cl
  const wchar_t *v24; // rax
  const wchar_t *v25; // rax
  unsigned int v26; // r13d
  const struct CXVariant *v27; // rax
  BYTE *v28; // rax
  __int64 v29; // rcx
  __int64 v30; // rbx
  __int64 v31; // rdx
  wchar_t *v32; // r15
  __int64 v33; // rbx
  struct __crt_locale_pointers *DefaultLocale; // rax
  LSTATUS v35; // eax
  LSTATUS v36; // ebx
  __int64 v37; // rbx
  __int64 v38; // rdx
  BYTE *v39; // rbx
  LSTATUS v40; // edi
  LSTATUS v41; // edi
  BYTE *v42; // rdi
  __int64 v43; // rax
  LSTATUS v44; // ebx
  wchar_t *v45; // rax
  BYTE *v46; // rbx
  LSTATUS v47; // esi
  wchar_t *v48; // rax
  LSTATUS v49; // esi
  LSTATUS v50; // esi
  LSTATUS v51; // esi
  wchar_t *v52; // rax
  LSTATUS v53; // esi
  wchar_t *v54; // rax
  wchar_t *OSErrString; // rax
  const WCHAR *v56; // rax
  struct __crt_locale_pointers *v57; // rax
  __int64 v58; // rsi
  struct __crt_locale_pointers *v59; // rax
  LSTATUS v60; // eax
  LSTATUS v61; // r12d
  LSTATUS v62; // esi
  wchar_t *v63; // rax
  wchar_t *v64; // rax
  PHKEY phkResult; // [rsp+20h] [rbp-120h]
  PHKEY phkResulta; // [rsp+20h] [rbp-120h]
  wchar_t *v67; // [rsp+30h] [rbp-110h]
  wchar_t *v68; // [rsp+30h] [rbp-110h]
  wchar_t *v69; // [rsp+30h] [rbp-110h]
  wchar_t *v70; // [rsp+30h] [rbp-110h]
  HKEY hKey; // [rsp+C0h] [rbp-80h] BYREF
  DWORD cbData; // [rsp+C8h] [rbp-78h] BYREF
  DWORD Type; // [rsp+CCh] [rbp-74h] BYREF
  BYTE v74[4]; // [rsp+D0h] [rbp-70h] BYREF
  BYTE Data[4]; // [rsp+D4h] [rbp-6Ch] BYREF
  BYTE *lpData; // [rsp+D8h] [rbp-68h]
  BYTE *v77; // [rsp+E0h] [rbp-60h]
  HKEY v78; // [rsp+E8h] [rbp-58h] BYREF
  DWORD v79; // [rsp+F0h] [rbp-50h] BYREF
  __int64 v80; // [rsp+F8h] [rbp-48h]
  wchar_t *v81; // [rsp+100h] [rbp-40h]
  BYTE *v82; // [rsp+108h] [rbp-38h]
  _BYTE v83[4096]; // [rsp+110h] [rbp-30h] BYREF

  v80 = -2;
  if ( *((_BYTE *)qword_102EF3550 + 1200) || (*((_BYTE *)qword_102ECFB10 + 1712) & 0x10) != 0 )
  {
    *((_DWORD *)a4 + 2) = 40514;
    ex_raise(405, 14, 16, 201, off_102ED36B0);
  }
  if ( *(_BYTE *)(qword_102ECFB00 + 48768) )
  {
    if ( !IsPolybaseProvisioned() )
    {
      *((_DWORD *)a4 + 2) = 46932;
      ex_raise(469, 32, 16, 2);
    }
  }
  else if ( !CPolybaseFeatureManager::IsPolybaseProvisioned((CPolybaseFeatureManager *)&g_PolybaseFeatureManager, 1)
         || (FUseReplicatedServerContext() ? (v7 = qword_102ECFB00 + 28520) : (v7 = qword_102ECFB00 + 14864),
             !*(_BYTE *)(v7 + 13645)) )
  {
    *((_DWORD *)a4 + 2) = 46903;
    ex_raise(469, 3, 16, 1);
  }
  v8 = -1;
  if ( OsInfo::IsXPlatInstance(SOS_OS_OsInfo)
    && (!*(_BYTE *)(qword_102ECFB00 + 48768) || !*(_BYTE *)(qword_102ECFB00 + 48773)) )
  {
    *((_DWORD *)a4 + 2) = 2817;
    OperatingSystemName = OsInfo::GetOperatingSystemName(SOS_OS_OsInfo);
    v10 = -1;
    do
      ++v10;
    while ( OperatingSystemName[v10] );
    LODWORD(phkResult) = (unsigned __int16)word_102ED36B8;
    ex_raise(28, 17, 16, 1, phkResult, off_102ED36B0, 2 * v10, OperatingSystemName);
  }
  MasterDbId = GetMasterDbId();
  if ( !(unsigned __int8)ISECManager::AccessCheckWithAuditState(0, MasterDbId, 0, 24, 51) )
    ex_raise(152, 47, 16, 1);
  if ( !a3 || *((_DWORD *)a3 + 7) - *((_DWORD *)a3 + 10) != 3 )
  {
    *((_DWORD *)a4 + 2) = 46910;
    ex_raise(469, 10, 16, 1);
  }
  v12 = **a2;
  v13 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v14 = *(_QWORD *)(v13 + 256);
  if ( !v14 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v14 = *(_QWORD *)(v13 + 256);
  }
  v15 = *(struct IMemObj **)(v14 + 1000);
  lpData = 0;
  v16 = (const struct CXVariant *)VerifySpecProcParam(
                                    (_DWORD)a3,
                                    0,
                                    0,
                                    v12,
                                    0,
                                    0,
                                    (__int64)CTypeInfo::FStringOrWString,
                                    -1);
  v17 = (BYTE *)ConvertXVariantToString(
                  v16,
                  *(const struct CTypeInfo **)(*(_QWORD *)(*((_QWORD *)a3 + 2) + 8LL * *((int *)a3 + 10)) + 24LL),
                  v15);
  lpData = v17;
  v18 = -1;
  do
    ++v18;
  while ( *(_WORD *)&v17[2 * v18] );
  if ( (unsigned int)v18 > 0xFF )
  {
    *((_DWORD *)a4 + 2) = 46911;
    ex_raise(469, 11, 16, 87, L"@head_node_address", L"nvarchar(255)");
  }
  v19 = *((int *)a3 + 10);
  if ( *((_DWORD *)a3 + 7) - (int)v19 > 1 )
  {
    v21 = *(_QWORD *)(*((_QWORD *)a3 + 2) + 8 * v19 + 8);
    v22 = **(_BYTE **)(v21 + 24);
    v23 = CTypeInfo::tiI4;
    if ( v22 != (_BYTE)CTypeInfo::tiI4 && v22 != 31 )
    {
      v24 = PwszXvtName(CTypeInfo::tiI4);
      ex_raise(2, 14, 16, 1, L"@dms_control_channel_port", v24);
      v23 = CTypeInfo::tiI4;
    }
    if ( **(_BYTE **)(v21 + 8) == 3 && (BYTE1(CTypeInfo::tiI4) & 1) != 0 )
    {
      v25 = PwszXvtName(v23);
      ex_raise(2, 14, 16, 1, L"@dms_control_channel_port", v25);
    }
    if ( (*(_BYTE *)v21 & 1) != 0 )
    {
      LODWORD(phkResulta) = 50;
      ex_raise(81, 62, 16, 1, phkResulta, L"@dms_control_channel_port");
    }
    v20 = *(_QWORD *)(v21 + 8);
  }
  else
  {
    v20 = 0;
  }
  v26 = *(_DWORD *)(v20 + 8);
  if ( v26 > 0xFFFF )
  {
    *((_DWORD *)a4 + 2) = 46911;
    ex_raise(469, 11, 16, 87, L"@dms_control_channel_port", L"unsigned int(16)");
  }
  v77 = 0;
  v27 = (const struct CXVariant *)VerifySpecProcParam(
                                    (_DWORD)a3,
                                    2,
                                    0,
                                    v12,
                                    0,
                                    0,
                                    (__int64)CTypeInfo::FStringOrWString,
                                    -1);
  v28 = (BYTE *)ConvertXVariantToString(
                  v27,
                  *(const struct CTypeInfo **)(*(_QWORD *)(*((_QWORD *)a3 + 2) + 8LL * *((int *)a3 + 10) + 16) + 24LL),
                  v15);
  v77 = v28;
  v29 = -1;
  do
    ++v29;
  while ( *(_WORD *)&v28[2 * v29] );
  if ( (unsigned int)v29 > 0x10 )
  {
    *((_DWORD *)a4 + 2) = 46911;
    ex_raise(469, 11, 16, 87, L"@head_node_sql_server_instance_name", L"nvarchar(16)");
  }
  v30 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v31 = *(_QWORD *)(v30 + 256);
  if ( !v31 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v31 = *(_QWORD *)(v30 + 256);
  }
  v32 = (wchar_t *)operator new[](
                     0x20Au,
                     *(struct IMemObj **)(v31 + 1000),
                     "sql\\ntdbms\\msql\\proc\\specproc.cpp",
                     9648,
                     3u);
  v81 = v32;
  v33 = qword_102ECFB00 + 47954;
  DefaultLocale = GetDefaultLocale();
  StringCchPrintf_lW(v32, 0x105u, L"%ls%ls", DefaultLocale, v33, L"\\Polybase\\Configuration");
  v35 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v32, 0, 3u, &hKey);
  v36 = v35;
  if ( v35 )
  {
    *((_DWORD *)a4 + 2) = 46909;
    OSErrString = GetOSErrString(v35, (struct ErrorStringHolder *)v83, 0, 0);
    ex_raise(469, 9, 16, v36, v32, OSErrString);
    v42 = lpData;
    v46 = v77;
  }
  else
  {
    if ( RegQueryValueExW(hKey, L"OriginalDmsControlChannelHostname", 0, 0, 0, 0) == 2 )
    {
      v37 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v38 = *(_QWORD *)(v37 + 256);
      if ( !v38 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v38 = *(_QWORD *)(v37 + 256);
      }
      v39 = (BYTE *)operator new[](
                      0x1FEu,
                      *(struct IMemObj **)(v38 + 1000),
                      "sql\\ntdbms\\msql\\proc\\specproc.cpp",
                      9676,
                      3u);
      v82 = v39;
      cbData = 255;
      v40 = RegQueryValueExW(hKey, L"DmsControlChannelHostname", 0, &Type, v39, &cbData);
      if ( v40 )
      {
        RegCloseKey(hKey);
        *((_DWORD *)a4 + 2) = 46906;
        v68 = GetOSErrString(v40, (struct ErrorStringHolder *)v83, 0, 0);
        ex_raise(469, 6, 16, v40, L"DmsControlChannelHostname", v32, v68);
      }
      else
      {
        v41 = RegSetValueExW(hKey, L"OriginalDmsControlChannelHostname", 0, 1u, v39, cbData);
        if ( v41 )
        {
          RegCloseKey(hKey);
          *((_DWORD *)a4 + 2) = 46908;
          v67 = GetOSErrString(v41, (struct ErrorStringHolder *)v83, 0, 0);
          ex_raise(469, 8, 16, v41, L"OriginalDmsControlChannelHostname", v32, v67);
        }
      }
      operator delete[](v39);
    }
    v42 = lpData;
    v43 = -1;
    do
      ++v43;
    while ( *(_WORD *)&lpData[2 * v43] );
    v44 = RegSetValueExW(hKey, L"DmsControlChannelHostname", 0, 1u, lpData, 2 * v43 + 2);
    if ( v44 )
    {
      RegCloseKey(hKey);
      *((_DWORD *)a4 + 2) = 46908;
      v45 = GetOSErrString(v44, (struct ErrorStringHolder *)v83, 0, 0);
      ex_raise(469, 8, 16, v44, L"DmsControlChannelHostname", v32, v45);
    }
    v46 = v77;
    do
      ++v8;
    while ( *(_WORD *)&v77[2 * v8] );
    v47 = RegSetValueExW(hKey, L"CtlSqlInstanceName", 0, 1u, v77, 2 * v8 + 2);
    if ( v47 )
    {
      RegCloseKey(hKey);
      *((_DWORD *)a4 + 2) = 46908;
      v48 = GetOSErrString(v47, (struct ErrorStringHolder *)v83, 0, 0);
      ex_raise(469, 8, 16, v47, L"CtlSqlInstanceName", v32, v48);
    }
    if ( RegQueryValueExW(hKey, L"OriginalDmsControlChannelPort", 0, 0, 0, 0) == 2 )
    {
      Type = 0;
      cbData = 4;
      v49 = RegQueryValueExW(hKey, L"DmsControlChannelPort", 0, &v79, (LPBYTE)&Type, &cbData);
      if ( v49 )
      {
        RegCloseKey(hKey);
        *((_DWORD *)a4 + 2) = 46906;
        v70 = GetOSErrString(v49, (struct ErrorStringHolder *)v83, 0, 0);
        ex_raise(469, 6, 16, v49, L"DmsControlChannelPort", v32, v70);
      }
      else
      {
        v50 = RegSetValueExW(hKey, L"OriginalDmsControlChannelPort", 0, 4u, (const BYTE *)&Type, cbData);
        if ( v50 )
        {
          RegCloseKey(hKey);
          *((_DWORD *)a4 + 2) = 46908;
          v69 = GetOSErrString(v50, (struct ErrorStringHolder *)v83, 0, 0);
          ex_raise(469, 8, 16, v50, L"OriginalDmsControlChannelPort", v32, v69);
        }
      }
    }
    *(_DWORD *)Data = v26;
    v51 = RegSetValueExW(hKey, L"DmsControlChannelPort", 0, 4u, Data, 4u);
    if ( v51 )
    {
      RegCloseKey(hKey);
      *((_DWORD *)a4 + 2) = 46908;
      v52 = GetOSErrString(v51, (struct ErrorStringHolder *)v83, 0, 0);
      ex_raise(469, 8, 16, v51, L"DmsControlChannelPort", v32, v52);
    }
    *(_DWORD *)v74 = 2;
    v53 = RegSetValueExW(hKey, L"NodeRole", 0, 4u, v74, 4u);
    if ( v53 )
    {
      RegCloseKey(hKey);
      *((_DWORD *)a4 + 2) = 46908;
      v54 = GetOSErrString(v53, (struct ErrorStringHolder *)v83, 0, 0);
      ex_raise(469, 8, 16, v53, L"NodeRole", v32, v54);
    }
    RegCloseKey(hKey);
  }
  if ( !OsInfo::IsXPlatInstance(SOS_OS_OsInfo) )
  {
    v56 = (const WCHAR *)(*(__int64 (__fastcall **)(struct IServerConfiguration *))(*(_QWORD *)s_pServerConf + 224LL))(s_pServerConf);
    if ( lstrcmpiW(v56, L"MSSQLSERVER") )
    {
      v58 = (*(__int64 (__fastcall **)(struct IServerConfiguration *))(*(_QWORD *)s_pServerConf + 224LL))(s_pServerConf);
      v59 = GetDefaultLocale();
      StringCchPrintf_lW(v32, 0x105u, L"%ls$%ls", v59, L"SYSTEM\\CurrentControlSet\\Services\\SQLPBENGINE", v58);
    }
    else
    {
      v57 = GetDefaultLocale();
      StringCchPrintf_lW(v32, 0x105u, L"%ls", v57, L"SYSTEM\\CurrentControlSet\\Services\\SQLPBENGINE");
    }
    v60 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v32, 0, 2u, &v78);
    v61 = v60;
    if ( v60 )
    {
      *((_DWORD *)a4 + 2) = 46909;
      v64 = GetOSErrString(v60, (struct ErrorStringHolder *)v83, 0, 0);
      ex_raise(469, 9, 16, v61, L"SYSTEM\\CurrentControlSet\\Services\\SQLPBENGINE", v64);
    }
    else
    {
      *(_DWORD *)v74 = 4;
      v62 = RegSetValueExW(v78, L"Start", 0, 4u, v74, 4u);
      if ( v62 )
      {
        RegCloseKey(v78);
        *((_DWORD *)a4 + 2) = 46908;
        v63 = GetOSErrString(v62, (struct ErrorStringHolder *)v83, 0, 0);
        ex_raise(469, 8, 16, v62, L"Start", v32, v63);
      }
      RegCloseKey(v78);
    }
  }
  ex_callprint(46901, 10, 1);
  *((_DWORD *)a4 + 2) = 0;
  operator delete[](v32);
  operator delete[](v46);
  operator delete[](v42);
}

```

## disassembly

```asm
0x10122fa50  push    rbp
0x10122fa52  push    rsi
0x10122fa53  push    rdi
0x10122fa54  push    r12
0x10122fa56  push    r13
0x10122fa58  push    r14
0x10122fa5a  push    r15
0x10122fa5c  lea     rbp, [rsp-0FE0h]
0x10122fa64  mov     eax, 1120h
0x10122fa69  call    _alloca_probe
0x10122fa6e  sub     rsp, rax
0x10122fa71  mov     [rbp+1010h+var_1058], 0FFFFFFFFFFFFFFFEh
0x10122fa79  mov     [rsp+1150h+arg_0], rbx
0x10122fa81  mov     rax, cs:__security_cookie
0x10122fa88  xor     rax, rsp
0x10122fa8b  mov     [rbp+1010h+var_40], rax
0x10122fa92  mov     r14, r9
0x10122fa95  mov     rbx, r8
0x10122fa98  mov     rdi, rdx
0x10122fa9b  mov     rax, cs:qword_102EF3550
0x10122faa2  cmp     byte ptr [rax+4B0h], 0
0x10122faa9  jnz     short loc_10122FABB
0x10122faab  mov     rax, cs:qword_102ECFB10
0x10122fab2  test    byte ptr [rax+6B0h], 10h
0x10122fab9  jz      short loc_10122FAE9
0x10122fabb  mov     dword ptr [r9+8], 9E42h
0x10122fac3  mov     rax, cs:off_102ED36B0; "sp_polybase_join_group"
0x10122faca  mov     [rsp+1150h+phkResult], rax
0x10122facf  mov     edx, 0Eh
0x10122fad4  mov     ecx, 195h
0x10122fad9  mov     r9d, 0C9h
0x10122fadf  lea     r8d, [rdx+2]
0x10122fae3  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x10122fae9  mov     rax, cs:qword_102ECFB00
0x10122faf0  cmp     byte ptr [rax+0BE80h], 0
0x10122faf7  jz      short loc_10122FB16
0x10122faf9  call    cs:__imp_?IsPolybaseProvisioned@@YA_NXZ; IsPolybaseProvisioned(void)
0x10122faff  test    al, al
0x10122fb01  jnz     short loc_10122FB72
0x10122fb03  mov     dword ptr [r14+8], 0B754h
0x10122fb0b  mov     edx, 20h ; ' '
0x10122fb10  lea     r9d, [rdx-1Eh]
0x10122fb14  jmp     short loc_10122FB61
0x10122fb16  mov     dl, 1; bool
0x10122fb18  lea     rcx, ?g_PolybaseFeatureManager@@3VCPolybaseFeatureManager@@A; this
0x10122fb1f  call    ?IsPolybaseProvisioned@CPolybaseFeatureManager@@QEAA_N_N@Z; CPolybaseFeatureManager::IsPolybaseProvisioned(bool)
0x10122fb24  test    al, al
0x10122fb26  jz      short loc_10122FB50
0x10122fb28  call    cs:__imp_?FUseReplicatedServerContext@@YA_NXZ; FUseReplicatedServerContext(void)
0x10122fb2e  test    al, al
0x10122fb30  mov     rax, cs:qword_102ECFB00
0x10122fb37  jnz     short loc_10122FB41
0x10122fb39  add     rax, 3A10h
0x10122fb3f  jmp     short loc_10122FB47
0x10122fb41  add     rax, 6F68h
0x10122fb47  cmp     byte ptr [rax+354Dh], 0
0x10122fb4e  jnz     short loc_10122FB72
0x10122fb50  mov     dword ptr [r14+8], 0B737h
0x10122fb58  mov     edx, 3
0x10122fb5d  lea     r9d, [rdx-2]
0x10122fb61  mov     r8d, 10h
0x10122fb67  mov     ecx, 1D5h
0x10122fb6c  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x10122fb72  mov     rcx, cs:__imp_?SOS_OS_OsInfo@@3VOsInfo@@A; OsInfo SOS_OS_OsInfo
0x10122fb79  call    cs:__imp_?IsXPlatInstance@OsInfo@@QEBA?B_NXZ; OsInfo::IsXPlatInstance(void)
0x10122fb7f  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x10122fb86  test    al, al
0x10122fb88  jz      short loc_10122FC03
0x10122fb8a  mov     rax, cs:qword_102ECFB00
0x10122fb91  cmp     byte ptr [rax+0BE80h], 0
0x10122fb98  jz      short loc_10122FBA3
0x10122fb9a  cmp     byte ptr [rax+0BE85h], 0
0x10122fba1  jnz     short loc_10122FC03
0x10122fba3  mov     dword ptr [r14+8], 0B01h
0x10122fbab  mov     rcx, cs:__imp_?SOS_OS_OsInfo@@3VOsInfo@@A; OsInfo SOS_OS_OsInfo
0x10122fbb2  call    cs:__imp_?GetOperatingSystemName@OsInfo@@QEBAQEB_WXZ; OsInfo::GetOperatingSystemName(void)
0x10122fbb8  mov     rdx, rsi
0x10122fbbb  nop     dword ptr [rax+rax+00h]
0x10122fbc0  inc     rdx
0x10122fbc3  cmp     word ptr [rax+rdx*2], 0
0x10122fbc8  jnz     short loc_10122FBC0
0x10122fbca  add     rdx, rdx
0x10122fbcd  movzx   ecx, cs:word_102ED36B8
0x10122fbd4  mov     [rsp+1150h+var_1118], rax
0x10122fbd9  mov     dword ptr [rsp+1150h+var_1120], edx
0x10122fbdd  mov     rax, cs:off_102ED36B0; "sp_polybase_join_group"
0x10122fbe4  mov     [rsp+1150h+lpcbData], rax
0x10122fbe9  mov     dword ptr [rsp+1150h+phkResult], ecx
0x10122fbed  mov     edx, 11h
0x10122fbf2  lea     ecx, [rdx+0Bh]
0x10122fbf5  lea     r9d, [rdx-10h]
0x10122fbf9  lea     r8d, [rdx-1]
0x10122fbfd  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x10122fc03  call    cs:__imp_?GetMasterDbId@@YAGXZ; GetMasterDbId(void)
0x10122fc09  movzx   edx, ax
0x10122fc0c  xor     r13d, r13d
0x10122fc0f  mov     [rsp+1150h+var_1098], r13
0x10122fc17  mov     [rsp+1150h+var_10A0], r13
0x10122fc1f  mov     [rsp+1150h+var_10A8], r13
0x10122fc27  mov     [rsp+1150h+var_10B0], r13d
0x10122fc2f  mov     [rsp+1150h+var_10B8], r13d
0x10122fc37  mov     [rsp+1150h+var_10C0], r13b
0x10122fc3f  mov     [rsp+1150h+var_10C8], r13d
0x10122fc47  mov     [rsp+1150h+var_10D0], r13d
0x10122fc4f  mov     [rsp+1150h+var_10D8], r13d
0x10122fc54  mov     [rsp+1150h+var_10E0], 0FFFFFFFFh
0x10122fc5c  mov     [rsp+1150h+var_10E8], r13d
0x10122fc61  mov     [rsp+1150h+var_10F0], r13d
0x10122fc66  mov     [rsp+1150h+var_10F8], r13
0x10122fc6b  mov     [rsp+1150h+var_1100], r13d
0x10122fc70  mov     [rsp+1150h+var_1108], 1Eh
0x10122fc78  mov     [rsp+1150h+var_1110], r13
0x10122fc7d  mov     [rsp+1150h+var_1118], r13
0x10122fc82  mov     byte ptr [rsp+1150h+var_1120], 1
0x10122fc87  mov     dword ptr [rsp+1150h+phkResult], 33h ; '3'
0x10122fc8f  lea     r9d, [r13+18h]
0x10122fc93  xor     r8d, r8d
0x10122fc96  xor     ecx, ecx
0x10122fc98  call    ?AccessCheckWithAuditState@ISECManager@@SAEPEAUIMetadataAccessor@@KKW4ESECObjectClass@@W4ESECPermissionAction@@AEAEEPEAVIUserToken@@PEAVISecContextToken@@1KPEAKKKKHW4MDObjectType@@JEHH6PEA_NPEAVCExternalPermissionCheckContext@@@Z; ISECManager::AccessCheckWithAuditState(IMetadataAccessor *,ulong,ulong,ESECObjectClass,ESECPermissionAction,uchar &,uchar,IUserToken *,ISecContextToken *,ESECObjectClass,ulong,ulong *,ulong,ulong,ulong,int,MDObjectType,long,uchar,int,int,ulong *,bool *,CExternalPermissionCheckContext *)
0x10122fc9d  test    al, al
0x10122fc9f  jnz     short loc_10122FCB6
0x10122fca1  lea     edx, [r13+2Fh]
0x10122fca5  lea     ecx, [rdx+69h]
0x10122fca8  lea     r9d, [r13+1]
0x10122fcac  lea     r8d, [r13+10h]
0x10122fcb0  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x10122fcb6  test    rbx, rbx
0x10122fcb9  jz      short loc_10122FCC6
0x10122fcbb  mov     eax, [rbx+1Ch]
0x10122fcbe  sub     eax, [rbx+28h]
0x10122fcc1  cmp     eax, 3
0x10122fcc4  jz      short loc_10122FCE6
0x10122fcc6  mov     dword ptr [r14+8], 0B73Eh
0x10122fcce  mov     edx, 0Ah
0x10122fcd3  mov     ecx, 1D5h
0x10122fcd8  lea     r9d, [rdx-9]
0x10122fcdc  lea     r8d, [rdx+6]
0x10122fce0  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x10122fce6  mov     rax, [rdi]
0x10122fce9  mov     r15, [rax]
0x10122fcec  mov     rdx, gs:58h
0x10122fcf5  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10122fcfc  mov     ecx, [rax]
0x10122fcfe  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10122fd05  mov     edi, [rax]
0x10122fd07  add     rdi, [rdx+rcx*8]
0x10122fd0b  mov     rax, [rdi+100h]
0x10122fd12  test    rax, rax
0x10122fd15  jnz     short loc_10122FD26
0x10122fd17  xor     ecx, ecx
0x10122fd19  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10122fd1f  mov     rax, [rdi+100h]
0x10122fd26  mov     r12, [rax+3E8h]
0x10122fd2d  mov     [rbp+1010h+lpData], r13
0x10122fd31  mov     dword ptr [rsp+1150h+var_1118], esi
0x10122fd35  lea     rax, ?FStringOrWString@CTypeInfo@@QEBA_NXZ; CTypeInfo::FStringOrWString(void)
0x10122fd3c  mov     [rsp+1150h+var_1120], rax
0x10122fd41  mov     dword ptr [rsp+1150h+lpcbData], r13d
0x10122fd46  mov     dword ptr [rsp+1150h+phkResult], r13d
0x10122fd4b  mov     r9, r15
0x10122fd4e  xor     r8d, r8d
0x10122fd51  xor     edx, edx
0x10122fd53  mov     rcx, rbx
0x10122fd56  call    ?VerifySpecProcParam@@YAPEAVCXVariant@@PEAVCParamExchange@@HEPEB_WHHP8CTypeInfo@@EBA_NXZH@Z; VerifySpecProcParam(CParamExchange *,int,uchar,wchar_t const *,int,int,bool (CTypeInfo::*)(void),int)
0x10122fd5b  movsxd  rdx, dword ptr [rbx+28h]
0x10122fd5f  mov     rcx, [rbx+10h]
0x10122fd63  mov     rdx, [rcx+rdx*8]
0x10122fd67  mov     r8, r12; struct IMemObj *
0x10122fd6a  mov     rdx, [rdx+18h]; struct CTypeInfo *
0x10122fd6e  mov     rcx, rax; struct CXVariant *
0x10122fd71  call    ?ConvertXVariantToString@@YAPEA_WPEBVCXVariant@@PEBVCTypeInfo@@PEAVIMemObj@@@Z; ConvertXVariantToString(CXVariant const *,CTypeInfo const *,IMemObj *)
0x10122fd76  mov     [rbp+1010h+lpData], rax
0x10122fd7a  mov     rcx, rsi
0x10122fd7d  nop     dword ptr [rax]
0x10122fd80  inc     rcx
0x10122fd83  cmp     word ptr [rax+rcx*2], 0
0x10122fd88  jnz     short loc_10122FD80
0x10122fd8a  cmp     ecx, 0FFh
0x10122fd90  jbe     short loc_10122FDCA
0x10122fd92  mov     dword ptr [r14+8], 0B73Fh
0x10122fd9a  lea     rax, aNvarchar255; "nvarchar(255)"
0x10122fda1  mov     [rsp+1150h+lpcbData], rax
0x10122fda6  lea     rax, aHeadNodeAddres; "@head_node_address"
0x10122fdad  mov     [rsp+1150h+phkResult], rax
0x10122fdb2  mov     edx, 0Bh
0x10122fdb7  mov     ecx, 1D5h
0x10122fdbc  lea     r9d, [rdx+4Ch]
0x10122fdc0  lea     r8d, [rdx+5]
0x10122fdc4  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x10122fdca  movsxd  rcx, dword ptr [rbx+28h]
0x10122fdce  mov     eax, [rbx+1Ch]
0x10122fdd1  sub     eax, ecx
0x10122fdd3  lea     rdx, aDmsControlChan; "@dms_control_channel_port"
0x10122fdda  cmp     eax, 1
0x10122fddd  jg      short loc_10122FDE7
0x10122fddf  mov     rax, r13
0x10122fde2  jmp     loc_10122FEB3
0x10122fde7  mov     rax, [rbx+10h]
0x10122fdeb  mov     rdi, [rax+rcx*8+8]
0x10122fdf0  mov     rax, [rdi+18h]
0x10122fdf4  movzx   edx, byte ptr [rax]
0x10122fdf7  movzx   ecx, byte ptr cs:?tiI4@CTypeInfo@@2V1@B; CTypeInfo const CTypeInfo::tiI4
0x10122fdfe  cmp     dl, cl
0x10122fe00  jz      short loc_10122FE3D
0x10122fe02  cmp     dl, 1Fh
0x10122fe05  jz      short loc_10122FE3D
0x10122fe07  call    cs:__imp_?PwszXvtName@@YAPEB_WE@Z; PwszXvtName(uchar)
0x10122fe0d  mov     [rsp+1150h+lpcbData], rax
0x10122fe12  lea     r13, aDmsControlChan; "@dms_control_channel_port"
0x10122fe19  mov     [rsp+1150h+phkResult], r13
0x10122fe1e  mov     edx, 0Eh
0x10122fe23  lea     ecx, [rdx-0Ch]
0x10122fe26  lea     r9d, [rdx-0Dh]
0x10122fe2a  lea     r8d, [rdx+2]
0x10122fe2e  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x10122fe34  movzx   ecx, byte ptr cs:?tiI4@CTypeInfo@@2V1@B; CTypeInfo const CTypeInfo::tiI4
0x10122fe3b  jmp     short loc_10122FE44
0x10122fe3d  lea     r13, aDmsControlChan; "@dms_control_channel_port"
0x10122fe44  mov     rax, [rdi+8]
0x10122fe48  cmp     byte ptr [rax], 3
0x10122fe4b  jnz     short loc_10122FE80
0x10122fe4d  movzx   eax, byte ptr cs:?tiI4@CTypeInfo@@2V1@B+1; CTypeInfo const CTypeInfo::tiI4
0x10122fe54  not     al
0x10122fe56  test    al, 1
0x10122fe58  jnz     short loc_10122FE80
0x10122fe5a  call    cs:__imp_?PwszXvtName@@YAPEB_WE@Z; PwszXvtName(uchar)
0x10122fe60  mov     [rsp+1150h+lpcbData], rax
0x10122fe65  mov     [rsp+1150h+phkResult], r13
0x10122fe6a  mov     edx, 0Eh
0x10122fe6f  lea     ecx, [rdx-0Ch]
0x10122fe72  lea     r9d, [rdx-0Dh]
0x10122fe76  lea     r8d, [rdx+2]
0x10122fe7a  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x10122fe80  test    byte ptr [rdi], 1
0x10122fe83  jz      short loc_10122FEA8
0x10122fe85  mov     [rsp+1150h+lpcbData], r13
0x10122fe8a  mov     dword ptr [rsp+1150h+phkResult], 32h ; '2'
0x10122fe92  mov     edx, 3Eh ; '>'
0x10122fe97  lea     ecx, [rdx+13h]
0x10122fe9a  lea     r9d, [rdx-3Dh]
0x10122fe9e  lea     r8d, [rdx-2Eh]
0x10122fea2  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x10122fea8  mov     rax, [rdi+8]
0x10122feac  lea     rdx, aDmsControlChan; "@dms_control_channel_port"
0x10122feb3  mov     r13d, [rax+8]
0x10122feb7  cmp     r13d, 0FFFFh
0x10122febe  jbe     short loc_10122FEF1
0x10122fec0  mov     dword ptr [r14+8], 0B73Fh
0x10122fec8  lea     rax, aUnsignedInt16; "unsigned int(16)"
0x10122fecf  mov     [rsp+1150h+lpcbData], rax
0x10122fed4  mov     [rsp+1150h+phkResult], rdx
0x10122fed9  mov     edx, 0Bh
0x10122fede  mov     ecx, 1D5h
0x10122fee3  lea     r9d, [rdx+4Ch]
0x10122fee7  lea     r8d, [rdx+5]
0x10122feeb  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x10122fef1  xor     edi, edi
0x10122fef3  mov     [rbp+1010h+var_1070], rdi
0x10122fef7  mov     dword ptr [rsp+1150h+var_1118], esi
0x10122fefb  lea     rax, ?FStringOrWString@CTypeInfo@@QEBA_NXZ; CTypeInfo::FStringOrWString(void)
0x10122ff02  mov     [rsp+1150h+var_1120], rax
0x10122ff07  mov     dword ptr [rsp+1150h+lpcbData], edi
0x10122ff0b  mov     dword ptr [rsp+1150h+phkResult], edi
0x10122ff0f  mov     r9, r15
0x10122ff12  xor     r8d, r8d
0x10122ff15  lea     edx, [rdi+2]
0x10122ff18  mov     rcx, rbx
0x10122ff1b  call    ?VerifySpecProcParam@@YAPEAVCXVariant@@PEAVCParamExchange@@HEPEB_WHHP8CTypeInfo@@EBA_NXZH@Z; VerifySpecProcParam(CParamExchange *,int,uchar,wchar_t const *,int,int,bool (CTypeInfo::*)(void),int)
0x10122ff20  movsxd  rdx, dword ptr [rbx+28h]
0x10122ff24  mov     rcx, [rbx+10h]
0x10122ff28  mov     rdx, [rcx+rdx*8+10h]
0x10122ff2d  mov     r8, r12; struct IMemObj *
0x10122ff30  mov     rdx, [rdx+18h]; struct CTypeInfo *
0x10122ff34  mov     rcx, rax; struct CXVariant *
0x10122ff37  call    ?ConvertXVariantToString@@YAPEA_WPEBVCXVariant@@PEBVCTypeInfo@@PEAVIMemObj@@@Z; ConvertXVariantToString(CXVariant const *,CTypeInfo const *,IMemObj *)
0x10122ff3c  mov     [rbp+1010h+var_1070], rax
0x10122ff40  mov     rcx, rsi
0x10122ff43  inc     rcx
0x10122ff46  cmp     word ptr [rax+rcx*2], 0
0x10122ff4b  jnz     short loc_10122FF43
0x10122ff4d  cmp     ecx, 10h
0x10122ff50  jbe     short loc_10122FF8A
0x10122ff52  mov     dword ptr [r14+8], 0B73Fh
0x10122ff5a  lea     rax, aNvarchar16; "nvarchar(16)"
0x10122ff61  mov     [rsp+1150h+lpcbData], rax
0x10122ff66  lea     rax, aHeadNodeSqlSer; "@head_node_sql_server_instance_name"
0x10122ff6d  mov     [rsp+1150h+phkResult], rax
0x10122ff72  mov     edx, 0Bh
0x10122ff77  mov     ecx, 1D5h
0x10122ff7c  lea     r9d, [rdx+4Ch]
0x10122ff80  lea     r8d, [rdx+5]
0x10122ff84  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x10122ff8a  mov     rdx, gs:58h
0x10122ff93  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10122ff9a  mov     ecx, [rax]
0x10122ff9c  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10122ffa3  mov     ebx, [rax]
0x10122ffa5  add     rbx, [rdx+rcx*8]
0x10122ffa9  mov     rdx, [rbx+100h]
0x10122ffb0  test    rdx, rdx
  ... truncated ...
```
