# CSatelliteGlobalContext::Init(wchar_t const *,bool)

- ea: `0x100404a00`
- end: `0x10040514b`
- name: `?Init@CSatelliteGlobalContext@@SAXPEB_W_N@Z`
- size: `1867`
- prototype: `void __fastcall(const wchar_t *, bool)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1004045e0`

## callees

- `0x100404a00`
- `0x1004051d0`
- `0x100405990`
- `0x10040e0e0`
- `0x10040e8c0`
- `0x10040ea90`
- `0x100424a20`
- `0x10042a070`
- `0x10042b7f0`
- `0x10042c270`
- `0x10042c430`
- `0x100461500`
- `0x1004628c0`
- `0x100486250`
- `0x100486af0`
- `0x100487cd6`
- `0x1004880d0`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x100404cb4`
- `KERNEL32!GetProcAddress` at `0x100404cb4`
- `KERNEL32!GetEnvironmentVariableW` at `0x100404a92`
- `KERNEL32!GetEnvironmentVariableW` at `0x100404a92`
- `KERNEL32!GetModuleFileNameW` at `0x100404e1a`
- `KERNEL32!GetModuleFileNameW` at `0x100404e1a`
- `KERNEL32!GetModuleHandleW` at `0x100404b0c`
- `KERNEL32!GetModuleHandleW` at `0x100404b8b`
- `KERNEL32!GetModuleHandleW` at `0x100404c98`
- `KERNEL32!GetModuleHandleW` at `0x100404deb`
- `KERNEL32!GetModuleHandleW` at `0x100404b0c`
- `KERNEL32!GetModuleHandleW` at `0x100404b8b`
- `KERNEL32!GetModuleHandleW` at `0x100404c98`
- `KERNEL32!GetModuleHandleW` at `0x100404deb`
- `KERNEL32!GetLastError` at `0x100404e24`
- `KERNEL32!GetLastError` at `0x100404e24`
- `sqldk!?KillProcess@SOS_OS@@SAXK@Z` at `0x100404b7c`
- `sqldk!?KillProcess@SOS_OS@@SAXK@Z` at `0x100404c8b`
- `sqldk!?KillProcess@SOS_OS@@SAXK@Z` at `0x100404de3`
- `sqldk!?KillProcess@SOS_OS@@SAXK@Z` at `0x100404f2a`
- `sqldk!?KillProcess@SOS_OS@@SAXK@Z` at `0x100405021`
- `sqldk!?KillProcess@SOS_OS@@SAXK@Z` at `0x100404b7c`
- `sqldk!?KillProcess@SOS_OS@@SAXK@Z` at `0x100404c8b`
- `sqldk!?KillProcess@SOS_OS@@SAXK@Z` at `0x100404de3`
- `sqldk!?KillProcess@SOS_OS@@SAXK@Z` at `0x100404f2a`
- `sqldk!?KillProcess@SOS_OS@@SAXK@Z` at `0x100405021`
- `sqldk!?CreateRingBuffer@SOS_OS@@SAPEAVSOS_RingBuffer@@W4RINGBUFFER_TYPE@@KKKP6AXPEAVSOS_RingBufferRecord@@PEA_W_KPEAPEA_WPEA_K@ZPEAVIMemObj@@@Z` at `0x100405094`
- `sqldk!?CreateRingBuffer@SOS_OS@@SAPEAVSOS_RingBuffer@@W4RINGBUFFER_TYPE@@KKKP6AXPEAVSOS_RingBufferRecord@@PEA_W_KPEAPEA_WPEA_K@ZPEAVIMemObj@@@Z` at `0x100405111`
- `sqldk!?CreateRingBuffer@SOS_OS@@SAPEAVSOS_RingBuffer@@W4RINGBUFFER_TYPE@@KKKP6AXPEAVSOS_RingBufferRecord@@PEA_W_KPEAPEA_WPEA_K@ZPEAVIMemObj@@@Z` at `0x100405094`
- `sqldk!?CreateRingBuffer@SOS_OS@@SAPEAVSOS_RingBuffer@@W4RINGBUFFER_TYPE@@KKKP6AXPEAVSOS_RingBufferRecord@@PEA_W_KPEAPEA_WPEA_K@ZPEAVIMemObj@@@Z` at `0x100405111`
- `sqldk!?SOS_OS_LogUnlocalizedRoutine@@3P6AXPEB_WZZEA` at `0x100404b5e`
- `sqldk!?SOS_OS_LogUnlocalizedRoutine@@3P6AXPEB_WZZEA` at `0x100404c6d`
- `sqldk!?SOS_OS_LogUnlocalizedRoutine@@3P6AXPEB_WZZEA` at `0x100404dc5`
- `sqldk!?SOS_OS_LogUnlocalizedRoutine@@3P6AXPEB_WZZEA` at `0x100404f0c`
- `sqldk!?SOS_OS_LogUnlocalizedRoutine@@3P6AXPEB_WZZEA` at `0x100405013`
- `sqldk!?GetTraceflagProvider@@YAPEAVSqlDkHost_ITraceFlag@@XZ` at `0x100404c23`
- `sqldk!?GetTraceflagProvider@@YAPEAVSqlDkHost_ITraceFlag@@XZ` at `0x100404c23`
- `sqldk!?CreateMemoryClerk@SOS_Node@@SAPEAVMemoryClerk@@PEB_WW4SOSHOST_MEMORYCLERK_TYPE@@W4SOS_CallerType@@@Z` at `0x100404bd1`
- `sqldk!?CreateMemoryClerk@SOS_Node@@SAPEAVMemoryClerk@@PEB_WW4SOSHOST_MEMORYCLERK_TYPE@@W4SOS_CallerType@@@Z` at `0x100404bd1`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x100404b47`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x100404c56`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x100404b47`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x100404c56`
- `sqldk!?CreateMemObject@MemoryObjectFactory@@SAPEAVIMemObj@@W4SOSHOST_MEMOBJ_ID@@KPEAVPageAllocator@@FF@Z` at `0x100404bfa`
- `sqldk!?CreateMemObject@MemoryObjectFactory@@SAPEAVIMemObj@@W4SOSHOST_MEMOBJ_ID@@KPEAVPageAllocator@@FF@Z` at `0x100404bfa`
- `sqldk!SystemThread_TlsIndex` at `0x100405030`
- `sqldk!SystemThread_TlsIndex` at `0x1004050aa`
- `sqldk!SystemThread_TlsOffset` at `0x100405039`
- `sqldk!SystemThread_TlsOffset` at `0x1004050b3`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100405054`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1004050ce`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100405054`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1004050ce`
- `VCRUNTIME140!wcsrchr` at `0x100404e4b`
- `VCRUNTIME140!wcsrchr` at `0x100404e4b`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x100404aff`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x100404aff`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x100404af3`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x100404af3`

## string_xrefs

- `0x100404ea1`: `.xevents.xml`
- `0x100404b05`: `sqlsatellite.dll`
- `0x100404b84`: `sqlsatellite.dll`
- `0x100404c15`: `Failed to create SQL_SATELLITE_RUN_CONTEXT memory clerk object\n`
- `0x100404c0c`: `Failed to create MEMOBJ_SQLEXTENSIBILITY_SATELLITECONTEXT PMO object\n`
- `0x100404c91`: `SqlDK.dll`
- `0x100404f30`: `sql\common\dk\sni\src\sni.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CSatelliteGlobalContext::Init(const wchar_t *a1, char a2)
{
  __int64 v4; // rax
  unsigned int v5; // eax
  HMODULE ModuleHandleW; // rax
  int inited; // eax
  unsigned int v8; // ebx
  wchar_t *OSErrString; // rax
  char v10; // bl
  HMODULE v11; // rax
  signed int v12; // eax
  unsigned int v13; // edi
  struct MemoryClerk *MemoryClerk; // rax
  const wchar_t *v15; // rcx
  struct SqlDkHost_ITraceFlag *TraceflagProvider; // rax
  wchar_t *v17; // rax
  HMODULE v18; // rax
  enum XEGetAPIResult (__high *ProcAddress)(struct XEEngineAPISet *, enum XEGetAPIOption); // rax
  __int64 (__fastcall *v20)(); // rax
  HMODULE v21; // rbx
  int LastError; // eax
  bool v23; // sf
  wchar_t *v24; // rax
  __int64 v25; // rcx
  WCHAR *v26; // rax
  __int64 v27; // rdx
  __int64 v28; // rdi
  WCHAR *v29; // rcx
  __int64 v30; // rax
  char *v31; // r8
  WCHAR v32; // dx
  WCHAR *v33; // rax
  int v34; // eax
  const wchar_t *v35; // r9
  int v36; // ebx
  unsigned int v37; // eax
  __int64 v38; // rbx
  __int64 v39; // rax
  __int64 v40; // rbx
  __int64 v41; // rax
  int v42; // [rsp+20h] [rbp-E0h]
  char v43[8]; // [rsp+20h] [rbp-E0h]
  _DWORD v44[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int16 v45; // [rsp+38h] [rbp-C8h]
  char v46[8]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v47; // [rsp+48h] [rbp-B8h]
  const char *v48; // [rsp+50h] [rbp-B0h]
  const char *v49; // [rsp+58h] [rbp-A8h]
  int v50; // [rsp+60h] [rbp-A0h]
  __int16 v51; // [rsp+70h] [rbp-90h] BYREF
  __int64 v52; // [rsp+78h] [rbp-88h]
  __int64 v53; // [rsp+80h] [rbp-80h]
  __int64 v54; // [rsp+88h] [rbp-78h]
  __int64 v55; // [rsp+90h] [rbp-70h]
  __int64 (__fastcall *v56)(wchar_t *, wchar_t *); // [rsp+98h] [rbp-68h]
  __int16 (__fastcall *v57)(HostErrorReportingManager *__hidden, int); // [rsp+A0h] [rbp-60h]
  __int64 v58; // [rsp+A8h] [rbp-58h]
  __int64 v59; // [rsp+B0h] [rbp-50h]
  __int64 v60; // [rsp+B8h] [rbp-48h]
  __int64 v61; // [rsp+C0h] [rbp-40h]
  __int64 v62; // [rsp+C8h] [rbp-38h]
  __int64 v63; // [rsp+D0h] [rbp-30h]
  __int64 v64; // [rsp+D8h] [rbp-28h]
  __int64 v65; // [rsp+E0h] [rbp-20h]
  __int64 v66; // [rsp+E8h] [rbp-18h]
  __int64 v67; // [rsp+F0h] [rbp-10h]
  __int64 v68; // [rsp+F8h] [rbp-8h]
  __int64 v69; // [rsp+100h] [rbp+0h]
  __int64 v70; // [rsp+108h] [rbp+8h]
  __int64 v71; // [rsp+110h] [rbp+10h]
  __int64 v72; // [rsp+118h] [rbp+18h]
  __int64 v73; // [rsp+120h] [rbp+20h]
  __int64 v74; // [rsp+128h] [rbp+28h]
  __int64 (__fastcall *v75)(); // [rsp+130h] [rbp+30h]
  __int128 v76; // [rsp+138h] [rbp+38h]
  __int128 v77; // [rsp+148h] [rbp+48h]
  char v78[4096]; // [rsp+160h] [rbp+60h] BYREF
  char v79[4096]; // [rsp+1160h] [rbp+1060h] BYREF
  wchar_t Filename[264]; // [rsp+2160h] [rbp+2060h] BYREF
  WCHAR Buffer[264]; // [rsp+2370h] [rbp+2270h] BYREF

  v47 = -2;
  if ( CSatelliteGlobalContext::sm_initialized )
    return;
  memset_0(Buffer, 0, 0x208u);
  if ( a1 && *a1 )
  {
    SetDefaultLogDirectory(a1);
  }
  else if ( GetEnvironmentVariableW(L"SQLSATELLITE_LOG_DIR", Buffer, 0x104u) )
  {
    if ( Buffer[0] )
    {
      v4 = -1;
      do
        ++v4;
      while ( Buffer[v4] );
      v5 = 2 * v4;
      if ( v5 )
      {
        if ( v5 > 0x20AuLL )
        {
          memset_0(qword_100556EA0, 0, 0x20Au);
          *_errno() = 34;
          _invalid_parameter_noinfo();
        }
        else
        {
          memmove(qword_100556EA0, Buffer, v5);
        }
      }
    }
  }
  ModuleHandleW = GetModuleHandleW(L"sqlsatellite.dll");
  inited = InitErrorReporting(&off_1004ED9E8, ModuleHandleW);
  v8 = inited;
  if ( inited < 0 )
  {
    _mm_lfence();
    wprintf(L"InitErrorReporting() failed. ErrorCode: 0x%08lx.\n", (unsigned int)inited);
    _mm_lfence();
    OSErrString = GetOSErrString(v8, (struct ErrorStringHolder *)v78, 0, 0);
    wprintf(L"SQLSatellite_InitErrorLog failed with 0x%08X (%ls)\n", v8, OSErrString);
    SOS_OS_LogUnlocalizedRoutine(L"Running SQLSatellite_Exit, calling SOS_OS::KillProcess with exitcode: %d\n", 2);
    SOS_OS::KillProcess(2u);
  }
  v10 = 1;
  v11 = GetModuleHandleW(L"sqlsatellite.dll");
  v12 = SQLSatellite_BootSOS(
          (enum SOS_RESULT (__high *)(struct SOS_Node *const))&SQLSatellite_InitNodeRoutine,
          (__int64 (*)(void))&SQLSatellite_DefaultConfigureDKRoutine,
          0,
          v11,
          1);
  v13 = v12;
  if ( v12 >= 0 )
  {
    MemoryClerk = (struct MemoryClerk *)SOS_Node::CreateMemoryClerk(L"SQL_SATELLITE_RUN_CONTEXT", 60, 1);
    CSatelliteGlobalContext::sm_memoryClerk = MemoryClerk;
    if ( MemoryClerk )
    {
      LOWORD(v42) = 128;
      CSatelliteGlobalContext::sm_pmo = (wchar_t *)MemoryObjectFactory::CreateMemObject(
                                                     319,
                                                     6,
                                                     (char *)MemoryClerk + 64,
                                                     8,
                                                     v42);
      if ( CSatelliteGlobalContext::sm_pmo )
        goto LABEL_21;
      v15 = L"Failed to create MEMOBJ_SQLEXTENSIBILITY_SATELLITECONTEXT PMO object\n";
    }
    else
    {
      v15 = L"Failed to create SQL_SATELLITE_RUN_CONTEXT memory clerk object\n";
    }
    v10 = 0;
    wprintf(v15);
LABEL_21:
    TraceflagProvider = GetTraceflagProvider();
    (*(void (__fastcall **)(struct SqlDkHost_ITraceFlag *, __int64, _QWORD, _QWORD))(*(_QWORD *)TraceflagProvider + 16LL))(
      TraceflagProvider,
      1260,
      0,
      0);
    if ( v10 )
      goto LABEL_25;
    goto LABEL_24;
  }
  _mm_lfence();
  v17 = GetOSErrString(v12, (struct ErrorStringHolder *)v79, 0, 0);
  wprintf(L"SQLSatellite_BootSOS failed with error 0x%08X (%ls).\n", v13, v17);
LABEL_24:
  SOS_OS_LogUnlocalizedRoutine(L"Running SQLSatellite_Exit, calling SOS_OS::KillProcess with exitcode: %d\n", 3);
  SOS_OS::KillProcess(3u);
LABEL_25:
  v18 = GetModuleHandleW(L"SqlDK.dll");
  if ( !v18 )
    goto LABEL_35;
  ProcAddress = (enum XEGetAPIResult (__high *)(struct XEEngineAPISet *, enum XEGetAPIOption))GetProcAddress(
                                                                                                v18,
                                                                                                "XEGetEngine");
  if ( !ProcAddress )
    goto LABEL_35;
  v44[0] = 655370;
  v44[1] = 1310738;
  v45 = 10;
  if ( !(unsigned int)XE_API::Initialize(ProcAddress, (const struct XEEngineVersion *)v44) )
    goto LABEL_35;
  v51 = 10;
  v52 = 0;
  v53 = 0;
  v54 = 0;
  v55 = 0;
  v56 = XESQLCanonicalizePath;
  v57 = HostErrorReportingManager::SGetLanguageId;
  v58 = 0;
  v59 = 0;
  v60 = 0;
  v61 = 0;
  v62 = 0;
  v63 = 0;
  v64 = 0;
  v65 = 0;
  v66 = 0;
  v67 = 0;
  v68 = 0;
  v69 = 0;
  v70 = 0;
  v71 = 0;
  v72 = 0;
  v73 = 0;
  v74 = 0;
  v20 = XESQLMultiTenantCanonicalizePathDisabled;
  if ( a2 )
    v20 = (__int64 (__fastcall *)())XESQLMultiTenantCanonicalizePath;
  v75 = v20;
  v76 = 0;
  v77 = 0;
  if ( !(unsigned int)qword_100516E80(&v51) || !(unsigned int)XE_PackageManager::StaticInit() )
  {
LABEL_35:
    wprintf(L"Failed to start the XEvent engine\n");
    goto LABEL_36;
  }
  if ( g_registerXePkgCallback && !g_registerXePkgCallback() )
  {
    wprintf(L"Failed to register host XEvent package\n");
LABEL_36:
    SOS_OS_LogUnlocalizedRoutine(L"Running SQLSatellite_Exit, calling SOS_OS::KillProcess with exitcode: %d\n", 4);
    SOS_OS::KillProcess(4u);
  }
  v21 = GetModuleHandleW(0);
  memset_0(Filename, 0, 0x20Au);
  if ( !GetModuleFileNameW(v21, Filename, 0x105u) )
  {
    LastError = GetLastError();
    v23 = LastError < 0;
    if ( LastError <= 0 )
      goto LABEL_58;
    LastError = (unsigned __int16)LastError | 0x80070000;
LABEL_57:
    v23 = LastError < 0;
LABEL_58:
    if ( !v23 )
      goto LABEL_60;
    goto LABEL_59;
  }
  v24 = wcsrchr(Filename, 0x2Eu);
  if ( v24 )
    *v24 = 0;
  v25 = 261;
  v26 = Filename;
  do
  {
    if ( !*v26 )
      break;
    ++v26;
    --v25;
  }
  while ( v25 );
  v27 = 261 - v25;
  if ( !v25 )
    v27 = 0;
  LastError = -2147024809;
  if ( v25 )
  {
    v28 = 261 - v27;
    v29 = &Filename[v27];
    if ( 261 != v27 )
    {
      v30 = 2147483646;
      v31 = (char *)((char *)L".xevents.xml" - (char *)v29);
      do
      {
        if ( !v30 )
          break;
        v32 = *(_WORD *)&v31[(_QWORD)v29];
        if ( !v32 )
          break;
        *v29++ = v32;
        --v30;
        --v28;
      }
      while ( v28 );
    }
    v33 = v29 - 1;
    if ( v28 )
      v33 = v29;
    *v33 = 0;
    LastError = -2147024774;
    if ( v28 )
    {
      LastError = InitXESessions(Filename, 0);
      goto LABEL_57;
    }
  }
LABEL_59:
  _mm_lfence();
  wprintf(L"Failed to start XEVENT sessions. ErrorCode:0x%08lx.\n", (unsigned int)LastError);
  SOS_OS_LogUnlocalizedRoutine(L"Running SQLSatellite_Exit, calling SOS_OS::KillProcess with exitcode: %d\n", 5);
  SOS_OS::KillProcess(5u);
LABEL_60:
  v48 = "sql\\common\\dk\\sni\\src\\sni.cpp";
  v49 = "SNIInitialize";
  v50 = 2530;
  if ( (g_XeSniPkg_enabledBitmap & 0x40) != 0 )
    SNIXE_SNI_ENTER_ON("sql\\common\\dk\\sni\\src\\sni.cpp", "SNIInitialize", 2530, L"API|SNIpmo: %p\n", 0);
  v34 = SNIInitializeEx(0, 0, 0, 0, 0, 0);
  v36 = v34;
  if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
  {
    *(_DWORD *)v43 = v34;
    SNIXE_SNI_TRACE_ON(
      "sql\\common\\dk\\sni\\src\\sni.cpp",
      "SNIInitialize",
      2540,
      L"RET|SNI%d{WINERR}\n",
      *(_QWORD *)v43);
  }
  if ( (g_XeSniPkg_enabledBitmap & 0x80u) != 0 )
    SNIXE_SNI_LEAVE_ON("sql\\common\\dk\\sni\\src\\sni.cpp", "SNIInitialize", 2530, v35);
  if ( v36 )
  {
    wprintf(L"Failed to initialize SNI\n");
    goto LABEL_70;
  }
  v37 = SNISecInitPackageEx(v46, 1, 1);
  if ( v37 )
  {
    wprintf(L"SNISecInitPackage failed. ErrorCode: 0x%x.\n", v37);
LABEL_70:
    SOS_OS_LogUnlocalizedRoutine(L"Running SQLSatellite_Exit, calling SOS_OS::KillProcess with exitcode: %d\n", 6);
    SOS_OS::KillProcess(6u);
  }
  v38 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v39 = *(_QWORD *)(v38 + 256);
  if ( !v39 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v39 = *(_QWORD *)(v38 + 256);
  }
  qword_100556BE8 = *(_QWORD *)(*(_QWORD *)(v39 + 992) + 320LL);
  g_extensibilityErrorRingBuffer = SOS_OS::CreateRingBuffer(68, 48, 128);
  v40 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v41 = *(_QWORD *)(v40 + 256);
  if ( !v41 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v41 = *(_QWORD *)(v40 + 256);
  }
  qword_100556BF8 = *(_QWORD *)(*(_QWORD *)(v41 + 992) + 320LL);
  g_extensibilitySatelliteMessageStateRingBuffer = SOS_OS::CreateRingBuffer(77, 64, 1024);
  CSatelliteGlobalContext::sm_initialized = 1;
}

```

## disassembly

```asm
0x100404a00  push    rbp
0x100404a02  push    rsi
0x100404a03  push    rdi
0x100404a04  push    r14
0x100404a06  push    r15
0x100404a08  lea     rbp, [rsp-2490h]
0x100404a10  mov     eax, 2590h
0x100404a15  call    _alloca_probe
0x100404a1a  sub     rsp, rax
0x100404a1d  mov     [rsp+25B0h+var_2568], 0FFFFFFFFFFFFFFFEh
0x100404a26  mov     [rsp+25B0h+arg_10], rbx
0x100404a2e  mov     rax, cs:__security_cookie
0x100404a35  xor     rax, rsp
0x100404a38  mov     [rbp+24B0h+var_30], rax
0x100404a3f  movzx   esi, dl
0x100404a42  mov     rbx, rcx
0x100404a45  cmp     cs:?sm_initialized@CSatelliteGlobalContext@@0_NA, 0; bool CSatelliteGlobalContext::sm_initialized
0x100404a4c  jnz     loc_100405125
0x100404a52  xor     edx, edx; Val
0x100404a54  mov     r8d, 208h; Size
0x100404a5a  lea     rcx, [rbp+24B0h+Buffer]; void *
0x100404a61  call    memset_0
0x100404a66  test    rbx, rbx
0x100404a69  jz      short loc_100404A7E
0x100404a6b  cmp     word ptr [rbx], 0
0x100404a6f  jz      short loc_100404A7E
0x100404a71  mov     rcx, rbx; Src
0x100404a74  call    ?SetDefaultLogDirectory@@YAXPEB_W@Z; SetDefaultLogDirectory(wchar_t const *)
0x100404a79  jmp     loc_100404B05
0x100404a7e  mov     r8d, 104h; nSize
0x100404a84  lea     rdx, [rbp+24B0h+Buffer]; lpBuffer
0x100404a8b  lea     rcx, Name; "SQLSATELLITE_LOG_DIR"
0x100404a92  call    cs:__imp_GetEnvironmentVariableW
0x100404a98  test    eax, eax
0x100404a9a  jz      short loc_100404B05
0x100404a9c  cmp     [rbp+24B0h+Buffer], 0
0x100404aa4  jz      short loc_100404B05
0x100404aa6  lea     rcx, [rbp+24B0h+Buffer]
0x100404aad  mov     rax, 0FFFFFFFFFFFFFFFFh
0x100404ab4  inc     rax
0x100404ab7  cmp     word ptr [rcx+rax*2], 0
0x100404abc  jnz     short loc_100404AB4
0x100404abe  add     rax, rax
0x100404ac1  mov     r8d, eax; Size
0x100404ac4  test    eax, eax
0x100404ac6  jz      short loc_100404B05
0x100404ac8  lea     rcx, qword_100556EA0; void *
0x100404acf  cmp     r8, 20Ah
0x100404ad6  ja      short loc_100404AE6
0x100404ad8  lea     rdx, [rbp+24B0h+Buffer]; Src
0x100404adf  call    memmove
0x100404ae4  jmp     short loc_100404B05
0x100404ae6  xor     edx, edx; Val
0x100404ae8  mov     r8d, 20Ah; Size
0x100404aee  call    memset_0
0x100404af3  call    cs:__imp__errno
0x100404af9  mov     dword ptr [rax], 22h ; '"'
0x100404aff  call    cs:__imp__invalid_parameter_noinfo
0x100404b05  lea     rcx, ModuleName; "sqlsatellite.dll"
0x100404b0c  call    cs:__imp_GetModuleHandleW
0x100404b12  mov     rdx, rax
0x100404b15  lea     rcx, off_1004ED9E8
0x100404b1c  call    InitErrorReporting
0x100404b21  mov     ebx, eax
0x100404b23  test    eax, eax
0x100404b25  jns     short loc_100404B82
0x100404b27  lfence
0x100404b2a  mov     edx, eax
0x100404b2c  lea     rcx, aIniterrorrepor; "InitErrorReporting() failed. ErrorCode:"...
0x100404b33  call    wprintf
0x100404b38  lfence
0x100404b3b  xor     r9d, r9d
0x100404b3e  xor     r8d, r8d
0x100404b41  lea     rdx, [rbp+24B0h+var_2450]
0x100404b45  mov     ecx, ebx
0x100404b47  call    cs:__imp_?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z; GetOSErrString(ulong,ErrorStringHolder &,void const *,ulong)
0x100404b4d  mov     r8, rax
0x100404b50  mov     edx, ebx
0x100404b52  lea     rcx, aSqlsatelliteIn; "SQLSatellite_InitErrorLog failed with 0"...
0x100404b59  call    wprintf
0x100404b5e  mov     rax, cs:__imp_?SOS_OS_LogUnlocalizedRoutine@@3P6AXPEB_WZZEA; void (*SOS_OS_LogUnlocalizedRoutine)(wchar_t const *,...)
0x100404b65  mov     r8, [rax]
0x100404b68  mov     edx, 2
0x100404b6d  lea     rcx, aRunningSqlsate; "Running SQLSatellite_Exit, calling SOS_"...
0x100404b74  call    r8
0x100404b77  mov     ecx, 2
0x100404b7c  call    cs:__imp_?KillProcess@SOS_OS@@SAXK@Z; SOS_OS::KillProcess(ulong)
0x100404b82  mov     bl, 1
0x100404b84  lea     rcx, ModuleName; "sqlsatellite.dll"
0x100404b8b  call    cs:__imp_GetModuleHandleW
0x100404b91  mov     dword ptr [rsp+25B0h+var_2590], 1; char
0x100404b99  mov     r9, rax; HINSTANCE
0x100404b9c  xor     r8d, r8d; enum SOS_RESULT (__high *)(void)
0x100404b9f  lea     rdx, ?SQLSatellite_DefaultConfigureDKRoutine@@YA?AW4SOS_RESULT@@XZ; enum SOS_RESULT (__high *)(void)
0x100404ba6  lea     rcx, ?SQLSatellite_InitNodeRoutine@@YA?AW4SOS_RESULT@@QEAVSOS_Node@@@Z; enum SOS_RESULT (__high *)(struct SOS_Node *const)
0x100404bad  call    ?SQLSatellite_BootSOS@@YAJP6A?AW4SOS_RESULT@@QEAVSOS_Node@@@ZP6A?AW41@XZ2PEAUHINSTANCE__@@K@Z; SQLSatellite_BootSOS(SOS_RESULT (*)(SOS_Node * const),SOS_RESULT (*)(void),SOS_RESULT (*)(void),HINSTANCE__ *,ulong)
0x100404bb2  mov     edi, eax
0x100404bb4  mov     r15d, 80h
0x100404bba  test    eax, eax
0x100404bbc  js      loc_100404C44
0x100404bc2  lea     edx, [r15-44h]
0x100404bc6  lea     r8d, [r15-7Fh]
0x100404bca  lea     rcx, aSqlSatelliteRu; "SQL_SATELLITE_RUN_CONTEXT"
0x100404bd1  call    cs:__imp_?CreateMemoryClerk@SOS_Node@@SAPEAVMemoryClerk@@PEB_WW4SOSHOST_MEMORYCLERK_TYPE@@W4SOS_CallerType@@@Z; SOS_Node::CreateMemoryClerk(wchar_t const *,SOSHOST_MEMORYCLERK_TYPE,SOS_CallerType)
0x100404bd7  mov     cs:?sm_memoryClerk@CSatelliteGlobalContext@@0PEAVMemoryClerk@@EA, rax; MemoryClerk * CSatelliteGlobalContext::sm_memoryClerk
0x100404bde  test    rax, rax
0x100404be1  jz      short loc_100404C15
0x100404be3  lea     r8, [rax+40h]
0x100404be7  lea     r9d, [r15-78h]
0x100404beb  mov     word ptr [rsp+25B0h+var_2590], r15w
0x100404bf1  lea     edx, [r15-7Ah]
0x100404bf5  mov     ecx, 13Fh
0x100404bfa  call    cs:__imp_?CreateMemObject@MemoryObjectFactory@@SAPEAVIMemObj@@W4SOSHOST_MEMOBJ_ID@@KPEAVPageAllocator@@FF@Z; MemoryObjectFactory::CreateMemObject(SOSHOST_MEMOBJ_ID,ulong,PageAllocator *,short,short)
0x100404c00  mov     cs:?sm_pmo@CSatelliteGlobalContext@@0PEAVIMemObj@@EA, rax; IMemObj * CSatelliteGlobalContext::sm_pmo
0x100404c07  test    rax, rax
0x100404c0a  jnz     short loc_100404C23
0x100404c0c  lea     rcx, aFailedToCreate; "Failed to create MEMOBJ_SQLEXTENSIBILIT"...
0x100404c13  jmp     short loc_100404C1C
0x100404c15  lea     rcx, aFailedToCreate_0; "Failed to create SQL_SATELLITE_RUN_CONT"...
0x100404c1c  xor     bl, bl
0x100404c1e  call    wprintf
0x100404c23  call    cs:__imp_?GetTraceflagProvider@@YAPEAVSqlDkHost_ITraceFlag@@XZ; GetTraceflagProvider(void)
0x100404c29  mov     r10, [rax]
0x100404c2c  xor     r9d, r9d
0x100404c2f  xor     r8d, r8d
0x100404c32  mov     edx, 4ECh
0x100404c37  mov     rcx, rax
0x100404c3a  call    qword ptr [r10+10h]
0x100404c3e  test    bl, bl
0x100404c40  jnz     short loc_100404C91
0x100404c42  jmp     short loc_100404C6D
0x100404c44  lfence
0x100404c47  xor     r9d, r9d
0x100404c4a  xor     r8d, r8d
0x100404c4d  lea     rdx, [rbp+24B0h+var_1450]
0x100404c54  mov     ecx, edi
0x100404c56  call    cs:__imp_?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z; GetOSErrString(ulong,ErrorStringHolder &,void const *,ulong)
0x100404c5c  mov     r8, rax
0x100404c5f  mov     edx, edi
0x100404c61  lea     rcx, aSqlsatelliteBo; "SQLSatellite_BootSOS failed with error "...
0x100404c68  call    wprintf
0x100404c6d  mov     rax, cs:__imp_?SOS_OS_LogUnlocalizedRoutine@@3P6AXPEB_WZZEA; void (*SOS_OS_LogUnlocalizedRoutine)(wchar_t const *,...)
0x100404c74  mov     r8, [rax]
0x100404c77  mov     edx, 3
0x100404c7c  lea     rcx, aRunningSqlsate; "Running SQLSatellite_Exit, calling SOS_"...
0x100404c83  call    r8
0x100404c86  mov     ecx, 3
0x100404c8b  call    cs:__imp_?KillProcess@SOS_OS@@SAXK@Z; SOS_OS::KillProcess(ulong)
0x100404c91  lea     rcx, aSqldkDll_1; "SqlDK.dll"
0x100404c98  call    cs:__imp_GetModuleHandleW
0x100404c9e  xor     r14d, r14d
0x100404ca1  test    rax, rax
0x100404ca4  jz      loc_100404DB9
0x100404caa  lea     rdx, ProcName; "XEGetEngine"
0x100404cb1  mov     rcx, rax; hModule
0x100404cb4  call    cs:__imp_GetProcAddress
0x100404cba  test    rax, rax
0x100404cbd  jz      loc_100404DB9
0x100404cc3  mov     ebx, 0Ah
0x100404cc8  mov     [rsp+25B0h+var_2580], 0A000Ah
0x100404cd0  mov     [rsp+25B0h+var_257C], 140012h
0x100404cd8  mov     [rsp+25B0h+var_2578], bx
0x100404cdd  lea     rdx, [rsp+25B0h+var_2580]; struct XEEngineVersion *
0x100404ce2  mov     rcx, rax; enum XEGetAPIResult (__high *)(struct XEEngineAPISet *, enum XEGetAPIOption)
0x100404ce5  call    ?Initialize@XE_API@@SAHP6A?AW4XEGetAPIResult@@PEAUXEEngineAPISet@@W4XEGetAPIOption@@@ZAEBUXEEngineVersion@@@Z; XE_API::Initialize(XEGetAPIResult (*)(XEEngineAPISet *,XEGetAPIOption),XEEngineVersion const &)
0x100404cea  test    eax, eax
0x100404cec  jz      loc_100404DB9
0x100404cf2  mov     [rsp+25B0h+var_2540], bx
0x100404cf7  mov     [rsp+25B0h+var_2538], r14
0x100404cfc  mov     [rbp+24B0h+var_2530], r14
0x100404d00  mov     [rbp+24B0h+var_2528], r14
0x100404d04  mov     [rbp+24B0h+var_2520], r14
0x100404d08  lea     rax, XESQLCanonicalizePath
0x100404d0f  mov     [rbp+24B0h+var_2518], rax
0x100404d13  lea     rax, ?SGetLanguageId@HostErrorReportingManager@@UEAAFH@Z; HostErrorReportingManager::SGetLanguageId(int)
0x100404d1a  mov     [rbp+24B0h+var_2510], rax
0x100404d1e  mov     [rbp+24B0h+var_2508], r14
0x100404d22  mov     [rbp+24B0h+var_2500], r14
0x100404d26  mov     [rbp+24B0h+var_24F8], r14
0x100404d2a  mov     [rbp+24B0h+var_24F0], r14
0x100404d2e  mov     [rbp+24B0h+var_24E8], r14
0x100404d32  mov     [rbp+24B0h+var_24E0], r14
0x100404d36  mov     [rbp+24B0h+var_24D8], r14
0x100404d3a  mov     [rbp+24B0h+var_24D0], r14
0x100404d3e  mov     [rbp+24B0h+var_24C8], r14
0x100404d42  mov     [rbp+24B0h+var_24C0], r14
0x100404d46  mov     [rbp+24B0h+var_24B8], r14
0x100404d4a  mov     [rbp+24B0h+var_24B0], r14
0x100404d4e  mov     [rbp+24B0h+var_24A8], r14
0x100404d52  mov     [rbp+24B0h+var_24A0], r14
0x100404d56  mov     [rbp+24B0h+var_2498], r14
0x100404d5a  mov     [rbp+24B0h+var_2490], r14
0x100404d5e  mov     [rbp+24B0h+var_2488], r14
0x100404d62  lea     rax, XESQLMultiTenantCanonicalizePathDisabled
0x100404d69  lea     rcx, XESQLMultiTenantCanonicalizePath
0x100404d70  test    sil, sil
0x100404d73  cmovnz  rax, rcx
0x100404d77  mov     [rbp+24B0h+var_2480], rax
0x100404d7b  xorps   xmm0, xmm0
0x100404d7e  movups  [rbp+24B0h+var_2478], xmm0
0x100404d82  movups  [rbp+24B0h+var_2468], xmm0
0x100404d86  lea     rcx, [rsp+25B0h+var_2540]
0x100404d8b  call    cs:qword_100516E80
0x100404d91  test    eax, eax
0x100404d93  jz      short loc_100404DB9
0x100404d95  call    ?StaticInit@XE_PackageManager@@SAHXZ; XE_PackageManager::StaticInit(void)
0x100404d9a  test    eax, eax
0x100404d9c  jz      short loc_100404DB9
0x100404d9e  mov     rax, cs:?g_registerXePkgCallback@@3P6A_NXZEA; bool (*g_registerXePkgCallback)(void)
0x100404da5  test    rax, rax
0x100404da8  jz      short loc_100404DE9
0x100404daa  call    rax ; bool (*g_registerXePkgCallback)(void)
0x100404dac  test    al, al
0x100404dae  jnz     short loc_100404DE9
0x100404db0  lea     rcx, aFailedToRegist; "Failed to register host XEvent package"...
0x100404db7  jmp     short loc_100404DC0
0x100404db9  lea     rcx, aFailedToStartT; "Failed to start the XEvent engine\n"
0x100404dc0  call    wprintf
0x100404dc5  mov     rax, cs:__imp_?SOS_OS_LogUnlocalizedRoutine@@3P6AXPEB_WZZEA; void (*SOS_OS_LogUnlocalizedRoutine)(wchar_t const *,...)
0x100404dcc  mov     r9, [rax]
0x100404dcf  mov     edx, 4
0x100404dd4  lea     rcx, aRunningSqlsate; "Running SQLSatellite_Exit, calling SOS_"...
0x100404ddb  call    r9
0x100404dde  mov     ecx, 4
0x100404de3  call    cs:__imp_?KillProcess@SOS_OS@@SAXK@Z; SOS_OS::KillProcess(ulong)
0x100404de9  xor     ecx, ecx; lpModuleName
0x100404deb  call    cs:__imp_GetModuleHandleW
0x100404df1  mov     rbx, rax
0x100404df4  xor     edx, edx; Val
0x100404df6  mov     r8d, 20Ah; Size
0x100404dfc  lea     rcx, [rbp+24B0h+Filename]; void *
0x100404e03  call    memset_0
0x100404e08  mov     edi, 105h
0x100404e0d  mov     r8d, edi; nSize
0x100404e10  lea     rdx, [rbp+24B0h+Filename]; lpFilename
0x100404e17  mov     rcx, rbx; hModule
0x100404e1a  call    cs:__imp_GetModuleFileNameW
0x100404e20  test    eax, eax
0x100404e22  jnz     short loc_100404E3F
0x100404e24  call    cs:__imp_GetLastError
0x100404e2a  test    eax, eax
0x100404e2c  jle     loc_100404EF9
0x100404e32  movzx   eax, ax
0x100404e35  or      eax, 80070000h
0x100404e3a  jmp     loc_100404EF7
0x100404e3f  mov     edx, 2Eh ; '.'; Ch
0x100404e44  lea     rcx, [rbp+24B0h+Filename]; Str
0x100404e4b  call    cs:__imp_wcsrchr
0x100404e51  test    rax, rax
0x100404e54  jz      short loc_100404E5A
0x100404e56  mov     [rax], r14w
0x100404e5a  mov     rcx, rdi
0x100404e5d  lea     rax, [rbp+24B0h+Filename]
0x100404e64  cmp     [rax], r14w
0x100404e68  jz      short loc_100404E74
0x100404e6a  add     rax, 2
0x100404e6e  sub     rcx, 1
0x100404e72  jnz     short loc_100404E64
0x100404e74  mov     rdx, rdi
0x100404e77  sub     rdx, rcx
0x100404e7a  test    rcx, rcx
0x100404e7d  cmovz   rdx, r14
0x100404e81  mov     eax, 80070057h
0x100404e86  cmovnz  eax, r14d
0x100404e8a  jz      short loc_100404EFB
0x100404e8c  sub     rdi, rdx
0x100404e8f  lea     rcx, [rbp+24B0h+Filename]
0x100404e96  lea     rcx, [rcx+rdx*2]
0x100404e9a  jz      short loc_100404ECF
0x100404e9c  mov     eax, 7FFFFFFEh
0x100404ea1  lea     r8, aXeventsXml; ".xevents.xml"
0x100404ea8  sub     r8, rcx
0x100404eab  nop     dword ptr [rax+rax+00h]
0x100404eb0  test    rax, rax
0x100404eb3  jz      short loc_100404ECF
0x100404eb5  movzx   edx, word ptr [rcx+r8]
0x100404eba  test    dx, dx
0x100404ebd  jz      short loc_100404ECF
0x100404ebf  mov     [rcx], dx
0x100404ec2  add     rcx, 2
0x100404ec6  dec     rax
0x100404ec9  sub     rdi, 1
0x100404ecd  jnz     short loc_100404EB0
0x100404ecf  lea     rax, [rcx-2]
0x100404ed3  test    rdi, rdi
0x100404ed6  cmovnz  rax, rcx
0x100404eda  mov     [rax], r14w
0x100404ede  mov     eax, 8007007Ah
0x100404ee3  cmovnz  eax, r14d
0x100404ee7  jz      short loc_100404EFB
0x100404ee9  xor     edx, edx; wchar_t *
0x100404eeb  lea     rcx, [rbp+24B0h+Filename]; wchar_t *
0x100404ef2  call    ?InitXESessions@@YAJPEB_W0@Z; InitXESessions(wchar_t const *,wchar_t const *)
0x100404ef7  test    eax, eax
0x100404ef9  jns     short loc_100404F30
0x100404efb  lfence
0x100404efe  mov     edx, eax
0x100404f00  lea     rcx, aFailedToStartX; "Failed to start XEVENT sessions. ErrorC"...
0x100404f07  call    wprintf
0x100404f0c  mov     rax, cs:__imp_?SOS_OS_LogUnlocalizedRoutine@@3P6AXPEB_WZZEA; void (*SOS_OS_LogUnlocalizedRoutine)(wchar_t const *,...)
  ... truncated ...
```
