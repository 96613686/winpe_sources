# SNIInitializeEx

- ea: `0x100424a20`
- end: `0x100424ffa`
- name: `SNIInitializeEx`
- size: `1498`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x100404a00`

## callees

- `0x10041da80`
- `0x100422210`
- `0x100424860`
- `0x100424a20`
- `0x10042b7f0`
- `0x10042b9b0`
- `0x10042c270`
- `0x10042c430`
- `0x100433d30`
- `0x1004349f0`
- `0x100486250`
- `0x100486af0`
- `0x100487cd6`

## import_xrefs

- `KERNEL32!VerifyVersionInfoW` at `0x100424d46`
- `KERNEL32!VerifyVersionInfoW` at `0x100424d46`
- `KERNEL32!GetComputerNameW` at `0x100424b1f`
- `KERNEL32!GetComputerNameW` at `0x100424b1f`
- `KERNEL32!VerSetConditionMask` at `0x100424d06`
- `KERNEL32!VerSetConditionMask` at `0x100424d14`
- `KERNEL32!VerSetConditionMask` at `0x100424d23`
- `KERNEL32!VerSetConditionMask` at `0x100424d32`
- `KERNEL32!VerSetConditionMask` at `0x100424d06`
- `KERNEL32!VerSetConditionMask` at `0x100424d14`
- `KERNEL32!VerSetConditionMask` at `0x100424d23`
- `KERNEL32!VerSetConditionMask` at `0x100424d32`
- `KERNEL32!GetVersionExW` at `0x100424c34`
- `KERNEL32!GetVersionExW` at `0x100424c34`
- `KERNEL32!GetLastError` at `0x100424b2d`
- `KERNEL32!GetLastError` at `0x100424c3e`
- `KERNEL32!GetLastError` at `0x100424b2d`
- `KERNEL32!GetLastError` at `0x100424c3e`
- `sqldk!?IsLinux@OsInfo@@QEBA?B_NXZ` at `0x100424c65`
- `sqldk!?IsLinux@OsInfo@@QEBA?B_NXZ` at `0x100424c65`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x100424c73`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x100424fd2`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x100424c73`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x100424fd2`
- `sqldk!??_V@YAXPEAX@Z` at `0x100424b85`
- `sqldk!??_V@YAXPEAX@Z` at `0x100424b85`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100424f79`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100424f79`
- `sqldk!SystemThread_TlsIndex` at `0x100424f0c`
- `sqldk!SystemThread_TlsOffset` at `0x100424f15`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100424f2e`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100424f2e`
- `sqldk!?SOS_OS_OsInfo@@3VOsInfo@@A` at `0x100424c5e`

## string_xrefs

- `0x100424a5d`: `sql\common\dk\sni\src\sni.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall SNIInitializeEx(
        __int64 a1,
        const enum ProviderNum *a2,
        unsigned int a3,
        const wchar_t *a4,
        int a5,
        _WORD *Src)
{
  unsigned int LastError; // ebx
  int v9; // r8d
  ULONGLONG v11; // rax
  ULONGLONG v12; // rax
  ULONGLONG v13; // rax
  ULONGLONG v14; // rax
  BOOL v15; // ebx
  const wchar_t *v16; // r9
  char v17; // cl
  unsigned int ClusterResourceLibraries; // eax
  __int64 v19; // rax
  __int64 v20; // rbp
  __int64 v21; // rsi
  __int64 v22; // rcx
  struct IMemObj *v23; // rcx
  unsigned __int64 v24; // rax
  wchar_t *v25; // rax
  bool v26; // zf
  char v27; // al
  __int64 v28; // [rsp+20h] [rbp-208h]
  __int64 v29; // [rsp+28h] [rbp-200h]
  __int64 v30; // [rsp+30h] [rbp-1F8h]
  DWORD nSize; // [rsp+50h] [rbp-1D8h] BYREF
  __int64 v32; // [rsp+58h] [rbp-1D0h]
  const char *v33; // [rsp+60h] [rbp-1C8h]
  const char *v34; // [rsp+68h] [rbp-1C0h]
  int v35; // [rsp+70h] [rbp-1B8h]
  const char *v36; // [rsp+78h] [rbp-1B0h]
  const char *v37; // [rsp+80h] [rbp-1A8h]
  int v38; // [rsp+88h] [rbp-1A0h]
  const char *v39; // [rsp+90h] [rbp-198h]
  const char *v40; // [rsp+98h] [rbp-190h]
  int v41; // [rsp+A0h] [rbp-188h]
  _OSVERSIONINFOEXW VersionInformation; // [rsp+B0h] [rbp-178h] BYREF

  v32 = -2;
  v33 = "sql\\common\\dk\\sni\\src\\sni.cpp";
  v34 = "SNIInitializeEx";
  v35 = 2235;
  if ( (g_XeSniPkg_enabledBitmap & 0x40) != 0 )
    SNIXE_SNI_ENTER_ON(
      "sql\\common\\dk\\sni\\src\\sni.cpp",
      "SNIInitializeEx",
      2235,
      L"API|SNIpmo: %p{void*}, rgProviders: %p{ProviderNum*}, cProviders: %d{DWORD}, fSandbox: %d{BOOL}, fUseClusteredList"
       "eners: %d{BOOL}, wszInstanceName: '%ls'",
      a1,
      a2,
      a3,
      (_DWORD)a4,
      a5,
      Src);
  LastError = 0;
  if ( _InterlockedIncrement(&gcSNIInitialized) != 1 )
  {
    if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
      SNIXE_SNI_ERROR_ON(
        "sql\\common\\dk\\sni\\src\\sni.cpp",
        "SNIInitializeEx",
        2321,
        L"ERR|SNIgcSNIInitialized is not true\n");
    goto LABEL_16;
  }
  MakeNodeMask();
  nSize = 255;
  if ( !GetComputerNameW(&gwszComputerName, &nSize) )
  {
    LastError = GetLastError();
    if ( (g_XeSniPkg_enabledBitmap & 2) == 0 )
    {
LABEL_10:
      SNISetLastError(0xAu, LastError, 0xC3B4u);
LABEL_11:
      if ( g_wszInstanceNameCopy )
      {
        operator delete[](g_wszInstanceNameCopy);
        g_wszInstanceNameCopy = 0;
      }
      if ( g_pcsListenerList )
      {
        (**(void (__fastcall ***)(struct CCriticalSectionSOS *, __int64))g_pcsListenerList)(g_pcsListenerList, 1);
        g_pcsListenerList = 0;
      }
      g_NodeMask = 0;
      _InterlockedDecrement(&gcSNIInitialized);
      goto LABEL_16;
    }
    v9 = 2337;
LABEL_9:
    LODWORD(v30) = LastError;
    LODWORD(v29) = 0;
    LODWORD(v28) = 10;
    SNIXE_SNI_ERROR_ON(
      "sql\\common\\dk\\sni\\src\\sni.cpp",
      "SNIInitializeEx",
      v9,
      L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
      v28,
      v29,
      v30);
    goto LABEL_10;
  }
  g_osviSNI.dwOSVersionInfoSize = 284;
  if ( !GetVersionExW(&g_osviSNI) )
  {
    LastError = GetLastError();
    if ( (g_XeSniPkg_enabledBitmap & 2) == 0 )
      goto LABEL_10;
    v9 = 2350;
    goto LABEL_9;
  }
  if ( !OsInfo::IsLinux(SOS_OS_OsInfo) && (*(_BYTE *)(CGlobalTraceFlags::GetUlTraceFlags() + 981) & 0x40) == 0 )
  {
    v36 = "sql\\common\\dk\\sni\\src\\sni.cpp";
    v37 = "FVistaSP1orLater";
    v38 = 2158;
    if ( (g_XeSniPkg_enabledBitmap & 0x40) != 0 )
      SNIXE_SNI_ENTER_ON("sql\\common\\dk\\sni\\src\\sni.cpp", "FVistaSP1orLater", 2158, L"API|SNI\n");
    memset_0(&VersionInformation, 0, sizeof(VersionInformation));
    VersionInformation.dwOSVersionInfoSize = 284;
    *(_QWORD *)&VersionInformation.dwMajorVersion = 6;
    *(_DWORD *)&VersionInformation.wServicePackMajor = 1;
    v11 = VerSetConditionMask(0, 2u, 3u);
    v12 = VerSetConditionMask(v11, 1u, 3u);
    v13 = VerSetConditionMask(v12, 0x20u, 3u);
    v14 = VerSetConditionMask(v13, 0x10u, 3u);
    v15 = VerifyVersionInfoW(&VersionInformation, 0x33u, v14);
    v17 = g_XeSniPkg_enabledBitmap;
    if ( (g_XeSniPkg_enabledBitmap & 0x80u) != 0 )
    {
      SNIXE_SNI_LEAVE_ON("sql\\common\\dk\\sni\\src\\sni.cpp", "FVistaSP1orLater", 2158, v16);
      v17 = g_XeSniPkg_enabledBitmap;
    }
    if ( v15 )
    {
      if ( (v17 & 1) != 0 )
        SNIXE_SNI_TRACE_ON(
          "sql\\common\\dk\\sni\\src\\sni.cpp",
          "SNIInitializeEx",
          2363,
          L"SNIVista versions which supports autotuning.\n");
      Tcp::s_fAutoTuning = 1;
    }
  }
  LastError = CCriticalSectionSOS::Initialize(&g_pcsListenerList);
  if ( LastError )
  {
    if ( (g_XeSniPkg_enabledBitmap & 2) == 0 )
      goto LABEL_10;
    v9 = 2386;
    goto LABEL_9;
  }
  gClusApi = 0;
  qword_100511DC0 = 0;
  v39 = "sql\\common\\dk\\sni\\src\\sni.cpp";
  v40 = "LoadClusterResourceLibraryIfNeeded";
  v41 = 637;
  if ( (g_XeSniPkg_enabledBitmap & 0x40) != 0 )
  {
    LODWORD(v28) = a5;
    SNIXE_SNI_ENTER_ON(
      "sql\\common\\dk\\sni\\src\\sni.cpp",
      "LoadClusterResourceLibraryIfNeeded",
      637,
      L"API|SNIfCluster: %d{BOOL}, pClusterApi: %p{CLUSTER_API*}\n",
      v28,
      &gClusApi);
  }
  ClusterResourceLibraries = LoadClusterResourceLibraries((HMODULE *)&gClusApi);
  LastError = ClusterResourceLibraries;
  g_fUseClusteredListeners = a5 != 0;
  if ( a5 && ClusterResourceLibraries )
  {
    if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
    {
      LODWORD(v30) = ClusterResourceLibraries;
      LODWORD(v29) = 22;
      LODWORD(v28) = 7;
      SNIXE_SNI_ERROR_ON(
        "sql\\common\\dk\\sni\\src\\sni.cpp",
        "LoadClusterResourceLibraryIfNeeded",
        644,
        L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
        v28,
        v29,
        v30);
    }
    SNISetLastError(7u, LastError, 0xC3CAu);
  }
  else
  {
    LastError = 0;
  }
  if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
  {
    LODWORD(v28) = LastError;
    SNIXE_SNI_TRACE_ON(
      "sql\\common\\dk\\sni\\src\\sni.cpp",
      "LoadClusterResourceLibraryIfNeeded",
      654,
      L"RET|SNI%d{WINERR}\n",
      v28);
  }
  if ( (g_XeSniPkg_enabledBitmap & 0x80u) != 0 )
    SNIXE_SNI_LEAVE_ON("sql\\common\\dk\\sni\\src\\sni.cpp", "LoadClusterResourceLibraryIfNeeded", 637, a4);
  if ( LastError )
    goto LABEL_11;
  if ( Src )
  {
    v19 = -1;
    do
      ++v19;
    while ( Src[v19] );
    v20 = (unsigned int)(v19 + 1);
    v21 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v22 = *(_QWORD *)(v21 + 256);
    if ( !v22 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v22 = *(_QWORD *)(v21 + 256);
    }
    v23 = *(struct IMemObj **)(*(_QWORD *)(*(_QWORD *)(v22 + 992) + 56LL) + 8LL);
    v24 = 2LL * (unsigned int)v20;
    if ( !is_mul_ok((unsigned int)v20, 2u) )
      v24 = -1;
    v25 = (wchar_t *)operator new[](v24, v23, 1, "sql\\common\\dk\\sni\\src\\sni.cpp", 2438, 6u);
    g_wszInstanceNameCopy = v25;
    if ( !v25 )
    {
      LastError = 14;
      if ( (g_XeSniPkg_enabledBitmap & 2) == 0 )
        goto LABEL_10;
      v9 = 2442;
      goto LABEL_9;
    }
    memmove(v25, Src, 2 * v20);
  }
  SNI_Provider::InitProviders(a2, a3);
  v26 = (*(_BYTE *)(CGlobalTraceFlags::GetUlTraceFlags() + 1101) & 2) == 0;
  v27 = g_fSNIPacketProtection;
  if ( !v26 )
    v27 = 1;
  g_fSNIPacketProtection = v27;
LABEL_16:
  if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
  {
    LODWORD(v28) = LastError;
    SNIXE_SNI_TRACE_ON("sql\\common\\dk\\sni\\src\\sni.cpp", "SNIInitializeEx", 2524, L"RET|SNI%d{WINERR}\n", v28);
  }
  if ( (g_XeSniPkg_enabledBitmap & 0x80u) != 0 )
    SNIXE_SNI_LEAVE_ON("sql\\common\\dk\\sni\\src\\sni.cpp", "SNIInitializeEx", 2235, a4);
  return LastError;
}

```

## disassembly

```asm
0x100424a20  push    rbx
0x100424a22  push    rbp
0x100424a23  push    rsi
0x100424a24  push    rdi
0x100424a25  push    r12
0x100424a27  push    r13
0x100424a29  push    r14
0x100424a2b  push    r15
0x100424a2d  sub     rsp, 1E8h
0x100424a34  mov     [rsp+228h+var_1D0], 0FFFFFFFFFFFFFFFEh
0x100424a3d  mov     rax, cs:__security_cookie
0x100424a44  xor     rax, rsp
0x100424a47  mov     [rsp+228h+var_58], rax
0x100424a4f  mov     r15d, r8d
0x100424a52  mov     r14, rdx
0x100424a55  mov     rdi, [rsp+228h+Src]
0x100424a5d  lea     r12, aSqlCommonDkSni_13; "sql\\common\\dk\\sni\\src\\sni.cpp"
0x100424a64  mov     [rsp+228h+var_1C8], r12
0x100424a69  lea     rbp, aSniinitializee; "SNIInitializeEx"
0x100424a70  mov     [rsp+228h+var_1C0], rbp
0x100424a75  mov     [rsp+228h+var_1B8], 8BBh
0x100424a7d  mov     esi, [rsp+228h+arg_20]
0x100424a84  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 40h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100424a8b  jz      short loc_100424AC2
0x100424a8d  mov     [rsp+228h+var_1E0], rdi
0x100424a92  mov     [rsp+228h+var_1E8], esi
0x100424a96  mov     [rsp+228h+var_1F0], r9d
0x100424a9b  mov     dword ptr [rsp+228h+var_1F8], r8d
0x100424aa0  mov     [rsp+228h+var_200], rdx
0x100424aa5  mov     [rsp+228h+var_208], rcx
0x100424aaa  lea     r9, aApiSnipmoPVoid; "API|SNIpmo: %p{void*}, rgProviders: %p{"...
0x100424ab1  mov     r8d, 8BBh; int
0x100424ab7  mov     rdx, rbp; char *
0x100424aba  mov     rcx, r12; char *
0x100424abd  call    ?SNIXE_SNI_ENTER_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ENTER_ON(char const *,char const *,int,wchar_t const *,...)
0x100424ac2  xor     r13d, r13d
0x100424ac5  mov     ebx, r13d
0x100424ac8  mov     eax, 1
0x100424acd  lock xadd cs:?gcSNIInitialized@@3JA, eax; long gcSNIInitialized
0x100424ad5  inc     eax
0x100424ad7  cmp     eax, 1
0x100424ada  jz      short loc_100424B06
0x100424adc  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100424ae3  jz      loc_100424BBD
0x100424ae9  lea     r9, aErrSnigcsniini; "ERR|SNIgcSNIInitialized is not true\n"
0x100424af0  mov     r8d, 911h; int
0x100424af6  mov     rdx, rbp; char *
0x100424af9  mov     rcx, r12; char *
0x100424afc  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x100424b01  jmp     loc_100424BBD
0x100424b06  call    ?MakeNodeMask@@YAXXZ; MakeNodeMask(void)
0x100424b0b  mov     [rsp+228h+nSize], 0FFh
0x100424b13  lea     rdx, [rsp+228h+nSize]; nSize
0x100424b18  lea     rcx, ?gwszComputerName@@3PA_WA; lpBuffer
0x100424b1f  call    cs:__imp_GetComputerNameW
0x100424b25  test    eax, eax
0x100424b27  jnz     loc_100424C23
0x100424b2d  call    cs:__imp_GetLastError
0x100424b33  mov     ebx, eax
0x100424b35  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100424b3c  jz      short loc_100424B67
0x100424b3e  mov     r8d, 921h; int
0x100424b44  mov     dword ptr [rsp+228h+var_1F8], ebx
0x100424b48  mov     dword ptr [rsp+228h+var_200], r13d
0x100424b4d  lea     r9, aErrSniprovider; "ERR|SNIProviderNum: %d{ProviderNum}, SN"...
0x100424b54  mov     dword ptr [rsp+228h+var_208], 0Ah
0x100424b5c  mov     rdx, rbp; char *
0x100424b5f  mov     rcx, r12; char *
0x100424b62  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x100424b67  mov     r8d, 0C3B4h
0x100424b6d  mov     edx, ebx
0x100424b6f  mov     ecx, 0Ah
0x100424b74  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x100424b79  mov     rcx, cs:?g_wszInstanceNameCopy@@3PEA_WEA; wchar_t * g_wszInstanceNameCopy
0x100424b80  test    rcx, rcx
0x100424b83  jz      short loc_100424B92
0x100424b85  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x100424b8b  mov     cs:?g_wszInstanceNameCopy@@3PEA_WEA, r13; wchar_t * g_wszInstanceNameCopy
0x100424b92  mov     rcx, cs:?g_pcsListenerList@@3PEAVCCriticalSectionSOS@@EA; CCriticalSectionSOS * g_pcsListenerList
0x100424b99  test    rcx, rcx
0x100424b9c  jz      short loc_100424BAF
0x100424b9e  mov     rax, [rcx]
0x100424ba1  mov     edx, 1
0x100424ba6  call    qword ptr [rax]
0x100424ba8  mov     cs:?g_pcsListenerList@@3PEAVCCriticalSectionSOS@@EA, r13; CCriticalSectionSOS * g_pcsListenerList
0x100424baf  mov     cs:?g_NodeMask@@3_KA, r13; unsigned __int64 g_NodeMask
0x100424bb6  lock dec cs:?gcSNIInitialized@@3JA; long gcSNIInitialized
0x100424bbd  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100424bc4  jz      short loc_100424BE3
0x100424bc6  mov     dword ptr [rsp+228h+var_208], ebx
0x100424bca  lea     r9, aRetSniDWinerr; "RET|SNI%d{WINERR}\n"
0x100424bd1  mov     r8d, 9DCh; int
0x100424bd7  mov     rdx, rbp; char *
0x100424bda  mov     rcx, r12; char *
0x100424bdd  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x100424be2  nop
0x100424be3  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 80h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100424bea  jz      short loc_100424BFD
0x100424bec  mov     r8d, 8BBh; int
0x100424bf2  mov     rdx, rbp; char *
0x100424bf5  mov     rcx, r12; char *
0x100424bf8  call    ?SNIXE_SNI_LEAVE_ON@@YAXPEBD0HPEB_W@Z; SNIXE_SNI_LEAVE_ON(char const *,char const *,int,wchar_t const *)
0x100424bfd  mov     eax, ebx
0x100424bff  mov     rcx, [rsp+228h+var_58]
0x100424c07  xor     rcx, rsp; StackCookie
0x100424c0a  call    __security_check_cookie
0x100424c0f  add     rsp, 1E8h
0x100424c16  pop     r15
0x100424c18  pop     r14
0x100424c1a  pop     r13
0x100424c1c  pop     r12
0x100424c1e  pop     rdi
0x100424c1f  pop     rsi
0x100424c20  pop     rbp
0x100424c21  pop     rbx
0x100424c22  retn
0x100424c23  mov     cs:?g_osviSNI@@3U_OSVERSIONINFOEXW@@A.dwOSVersionInfoSize, 11Ch; _OSVERSIONINFOEXW g_osviSNI ...
0x100424c2d  lea     rcx, ?g_osviSNI@@3U_OSVERSIONINFOEXW@@A; lpVersionInformation
0x100424c34  call    cs:__imp_GetVersionExW
0x100424c3a  test    eax, eax
0x100424c3c  jnz     short loc_100424C5E
0x100424c3e  call    cs:__imp_GetLastError
0x100424c44  mov     ebx, eax
0x100424c46  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100424c4d  jz      loc_100424B67
0x100424c53  mov     r8d, 92Eh
0x100424c59  jmp     loc_100424B44
0x100424c5e  mov     rcx, cs:__imp_?SOS_OS_OsInfo@@3VOsInfo@@A; OsInfo SOS_OS_OsInfo
0x100424c65  call    cs:__imp_?IsLinux@OsInfo@@QEBA?B_NXZ; OsInfo::IsLinux(void)
0x100424c6b  test    al, al
0x100424c6d  jnz     loc_100424D9F
0x100424c73  call    cs:__imp_?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ; CGlobalTraceFlags::GetUlTraceFlags(void)
0x100424c79  test    byte ptr [rax+3D5h], 40h
0x100424c80  jnz     loc_100424D9F
0x100424c86  mov     [rsp+228h+var_1B0], r12
0x100424c8b  lea     rax, aFvistasp1orlat; "FVistaSP1orLater"
0x100424c92  mov     [rsp+228h+var_1A8], rax
0x100424c9a  mov     [rsp+228h+var_1A0], 86Eh
0x100424ca5  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 40h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100424cac  jz      short loc_100424CC6
0x100424cae  lea     r9, aApiSni_0; "API|SNI\n"
0x100424cb5  mov     r8d, 86Eh; int
0x100424cbb  mov     rdx, rax; char *
0x100424cbe  mov     rcx, r12; char *
0x100424cc1  call    ?SNIXE_SNI_ENTER_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ENTER_ON(char const *,char const *,int,wchar_t const *,...)
0x100424cc6  xor     edx, edx; Val
0x100424cc8  mov     r8d, 11Ch; Size
0x100424cce  lea     rcx, [rsp+228h+VersionInformation]; void *
0x100424cd6  call    memset_0
0x100424cdb  mov     [rsp+228h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x100424ce6  mov     qword ptr [rsp+228h+VersionInformation.dwMajorVersion], 6
0x100424cf2  mov     ebx, 1
0x100424cf7  mov     dword ptr [rsp+228h+VersionInformation.wServicePackMajor], ebx
0x100424cfe  mov     r8b, 3; Condition
0x100424d01  lea     edx, [rbx+1]; TypeMask
0x100424d04  xor     ecx, ecx; ConditionMask
0x100424d06  call    cs:__imp_VerSetConditionMask
0x100424d0c  mov     r8b, 3; Condition
0x100424d0f  mov     edx, ebx; TypeMask
0x100424d11  mov     rcx, rax; ConditionMask
0x100424d14  call    cs:__imp_VerSetConditionMask
0x100424d1a  mov     r8b, 3; Condition
0x100424d1d  lea     edx, [rbx+1Fh]; TypeMask
0x100424d20  mov     rcx, rax; ConditionMask
0x100424d23  call    cs:__imp_VerSetConditionMask
0x100424d29  mov     r8b, 3; Condition
0x100424d2c  lea     edx, [rbx+0Fh]; TypeMask
0x100424d2f  mov     rcx, rax; ConditionMask
0x100424d32  call    cs:__imp_VerSetConditionMask
0x100424d38  mov     r8, rax; dwlConditionMask
0x100424d3b  lea     edx, [rbx+32h]; dwTypeMask
0x100424d3e  lea     rcx, [rsp+228h+VersionInformation]; lpVersionInformation
0x100424d46  call    cs:__imp_VerifyVersionInfoW
0x100424d4c  mov     ebx, eax
0x100424d4e  mov     ecx, cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100424d54  test    cl, cl
0x100424d56  jns     short loc_100424D73
0x100424d58  mov     r8d, 86Eh; int
0x100424d5e  lea     rdx, aFvistasp1orlat; "FVistaSP1orLater"
0x100424d65  mov     rcx, r12; char *
0x100424d68  call    ?SNIXE_SNI_LEAVE_ON@@YAXPEBD0HPEB_W@Z; SNIXE_SNI_LEAVE_ON(char const *,char const *,int,wchar_t const *)
0x100424d6d  mov     ecx, cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100424d73  test    ebx, ebx
0x100424d75  jz      short loc_100424D9F
0x100424d77  test    cl, 1
0x100424d7a  jz      short loc_100424D94
0x100424d7c  lea     r9, aSnivistaVersio; "SNIVista versions which supports autotu"...
0x100424d83  mov     r8d, 93Bh; int
0x100424d89  mov     rdx, rbp; char *
0x100424d8c  mov     rcx, r12; char *
0x100424d8f  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x100424d94  mov     eax, 1
0x100424d99  mov     cs:?s_fAutoTuning@Tcp@@2HA, eax; int Tcp::s_fAutoTuning
0x100424d9f  lea     rcx, ?g_pcsListenerList@@3PEAVCCriticalSectionSOS@@EA; struct CCriticalSectionSOS **
0x100424da6  call    ?Initialize@CCriticalSectionSOS@@SAKPEAPEAV1@@Z; CCriticalSectionSOS::Initialize(CCriticalSectionSOS * *)
0x100424dab  mov     ebx, eax
0x100424dad  test    eax, eax
0x100424daf  jz      short loc_100424DC9
0x100424db1  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100424db8  jz      loc_100424B67
0x100424dbe  mov     r8d, 952h
0x100424dc4  jmp     loc_100424B44
0x100424dc9  mov     cs:?gClusApi@@3UCLUSTER_API@@A, r13; CLUSTER_API gClusApi
0x100424dd0  mov     cs:qword_100511DC0, r13
0x100424dd7  mov     [rsp+228h+var_198], r12
0x100424ddf  lea     rax, aLoadclusterres_0; "LoadClusterResourceLibraryIfNeeded"
0x100424de6  mov     [rsp+228h+var_190], rax
0x100424dee  mov     [rsp+228h+var_188], 27Dh
0x100424df9  lea     rbx, ?gClusApi@@3UCLUSTER_API@@A; CLUSTER_API gClusApi
0x100424e00  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 40h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100424e07  jz      short loc_100424E2A
0x100424e09  mov     [rsp+228h+var_200], rbx
0x100424e0e  mov     dword ptr [rsp+228h+var_208], esi
0x100424e12  lea     r9, aApiSnifcluster; "API|SNIfCluster: %d{BOOL}, pClusterApi:"...
0x100424e19  mov     r8d, 27Dh; int
0x100424e1f  mov     rdx, rax; char *
0x100424e22  mov     rcx, r12; char *
0x100424e25  call    ?SNIXE_SNI_ENTER_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ENTER_ON(char const *,char const *,int,wchar_t const *,...)
0x100424e2a  mov     rcx, rbx; struct CLUSTER_API *
0x100424e2d  call    ?LoadClusterResourceLibraries@@YAKPEAUCLUSTER_API@@@Z; LoadClusterResourceLibraries(CLUSTER_API *)
0x100424e32  mov     ebx, eax
0x100424e34  test    esi, esi
0x100424e36  setnz   cs:?g_fUseClusteredListeners@@3_NA; bool g_fUseClusteredListeners
0x100424e3d  test    esi, esi
0x100424e3f  jz      short loc_100424E92
0x100424e41  test    eax, eax
0x100424e43  jz      short loc_100424E92
0x100424e45  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100424e4c  jz      short loc_100424E7E
0x100424e4e  mov     dword ptr [rsp+228h+var_1F8], eax
0x100424e52  mov     dword ptr [rsp+228h+var_200], 16h
0x100424e5a  mov     dword ptr [rsp+228h+var_208], 7
0x100424e62  lea     r9, aErrSniprovider; "ERR|SNIProviderNum: %d{ProviderNum}, SN"...
0x100424e69  mov     r8d, 284h; int
0x100424e6f  lea     rdx, aLoadclusterres_0; "LoadClusterResourceLibraryIfNeeded"
0x100424e76  mov     rcx, r12; char *
0x100424e79  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x100424e7e  mov     r8d, 0C3CAh
0x100424e84  mov     edx, ebx
0x100424e86  mov     ecx, 7
0x100424e8b  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x100424e90  jmp     short loc_100424E95
0x100424e92  mov     ebx, r13d
0x100424e95  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100424e9c  jz      short loc_100424EBF
0x100424e9e  mov     dword ptr [rsp+228h+var_208], ebx
0x100424ea2  lea     r9, aRetSniDWinerr; "RET|SNI%d{WINERR}\n"
0x100424ea9  mov     r8d, 28Eh; int
0x100424eaf  lea     rdx, aLoadclusterres_0; "LoadClusterResourceLibraryIfNeeded"
0x100424eb6  mov     rcx, r12; char *
0x100424eb9  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x100424ebe  nop
0x100424ebf  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 80h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100424ec6  jz      short loc_100424EDD
0x100424ec8  mov     r8d, 27Dh; int
0x100424ece  lea     rdx, aLoadclusterres_0; "LoadClusterResourceLibraryIfNeeded"
0x100424ed5  mov     rcx, r12; char *
0x100424ed8  call    ?SNIXE_SNI_LEAVE_ON@@YAXPEBD0HPEB_W@Z; SNIXE_SNI_LEAVE_ON(char const *,char const *,int,wchar_t const *)
0x100424edd  test    ebx, ebx
0x100424edf  jnz     loc_100424B79
0x100424ee5  test    rdi, rdi
0x100424ee8  jz      loc_100424FC7
0x100424eee  mov     rax, 0FFFFFFFFFFFFFFFFh
0x100424ef5  lea     rax, [rax+1]
0x100424ef9  cmp     word ptr [rdi+rax*2], 0
0x100424efe  jnz     short loc_100424EF5
0x100424f00  lea     ebp, [rax+1]
0x100424f03  mov     rdx, gs:58h
0x100424f0c  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100424f13  mov     ecx, [rax]
0x100424f15  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100424f1c  mov     esi, [rax]
0x100424f1e  add     rsi, [rdx+rcx*8]
0x100424f22  mov     rcx, [rsi+100h]
0x100424f29  test    rcx, rcx
0x100424f2c  jnz     short loc_100424F3B
0x100424f2e  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100424f34  mov     rcx, [rsi+100h]
0x100424f3b  mov     rcx, [rcx+3E0h]
0x100424f42  mov     rdx, [rcx+38h]
0x100424f46  mov     rcx, [rdx+8]
0x100424f4a  mov     esi, ebp
0x100424f4c  mov     eax, 2
0x100424f51  mul     rsi
0x100424f54  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x100424f5b  cmovo   rax, rdx
0x100424f5f  mov     byte ptr [rsp+228h+var_200], 6
0x100424f64  mov     dword ptr [rsp+228h+var_208], 986h
0x100424f6c  mov     r9, r12
0x100424f6f  lea     r8d, [rdx+2]
0x100424f73  mov     rdx, rcx
0x100424f76  mov     rcx, rax
0x100424f79  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new[](unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x100424f7f  mov     cs:?g_wszInstanceNameCopy@@3PEA_WEA, rax; wchar_t * g_wszInstanceNameCopy
0x100424f86  test    rax, rax
0x100424f89  jnz     short loc_100424FAD
0x100424f8b  lea     ebx, [rax+0Eh]
0x100424f8e  lea     rbp, aSniinitializee; "SNIInitializeEx"
0x100424f95  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100424f9c  jz      loc_100424B67
  ... truncated ...
```
