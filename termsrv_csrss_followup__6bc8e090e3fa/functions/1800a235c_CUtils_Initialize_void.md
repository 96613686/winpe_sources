# CUtils::Initialize(void)

- ea: `0x1800a235c`
- end: `0x1800a2603`
- name: `?Initialize@CUtils@@SAJXZ`
- size: `679`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18003bc94`

## callees

- `0x180009940`
- `0x180027434`
- `0x180033f60`
- `0x18003444c`
- `0x180034e64`
- `0x1800a0ae0`
- `0x1800a0b34`
- `0x1800a0c18`
- `0x1800a0cb0`
- `0x1800a0d6c`
- `0x1800a12a8`
- `0x1800a235c`
- `0x1800a260c`
- `0x1800cab28`
- `0x1800cabbc`
- `0x1800cac50`

## import_xrefs

- `ntdll!RtlVerifyVersionInfo` at `0x1800a24e2`
- `ntdll!RtlVerifyVersionInfo` at `0x1800a24e2`
- `ntdll!VerSetConditionMask` at `0x1800a24cc`
- `ntdll!VerSetConditionMask` at `0x1800a24cc`
- `ntdll!RtlNtStatusToDosError` at `0x1800a242e`
- `ntdll!RtlNtStatusToDosError` at `0x1800a242e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800a243c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800a243c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a2448`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a256d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a2448`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a256d`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueue` at `0x1800a2555`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueue` at `0x1800a2555`

## string_xrefs

- `0x1800a23e5`: `CUtils::CreateAdminSid failed: 0x%x in %s`
- `0x1800a23c7`: `CUtil::CreateSystemSid failed: 0x%x in %s`
- `0x1800a2417`: `CUtils::CreateNetworkServiceSid failed: 0x%x in %s`
- `0x1800a2400`: `NtCreateAnonymousSid failed: 0x%x in %s`
- `0x1800a2485`: `CUtils::CreateAppContainerSid failed: 0x%x in %s`
- `0x1800a2467`: `CUtils::CreateRdsMsSid failed: 0x%x in %s`
- `0x1800a24a3`: `CUtils::CreateLPACCapabilitySid failed: 0x%x in %s`

## pseudocode

```c
__int64 CUtils::Initialize(void)
{
  int SystemSid; // ebx
  int AnonymousSid; // eax
  void **v2; // rcx
  NTSTATUS RdsMsSid; // eax
  DWORD v4; // eax
  signed int LastError; // eax
  ULONGLONG v6; // rax
  _DWORD *v7; // rax
  _DWORD *v8; // rdi
  signed int v9; // eax
  int v11[4]; // [rsp+20h] [rbp-148h] BYREF
  struct _OSVERSIONINFOEXW VersionInfo; // [rsp+30h] [rbp-138h] BYREF

  v11[0] = 0;
  memset_0(&VersionInfo, 0, sizeof(VersionInfo));
  g_bDebugSpew = 0;
  CUtils::IsAppServerInstalled(v11);
  CUtils::bIsAppCompat = v11[0];
  SystemSid = CUtils::CreateSystemSid(&CUtils::pSystemSid);
  if ( SystemSid >= 0 )
  {
    SystemSid = CUtils::CreateAdminSid(&CUtils::pAdminSid);
    if ( SystemSid >= 0 )
    {
      AnonymousSid = NtCreateAnonymousSid();
      SystemSid = AnonymousSid | 0x10000000;
      if ( AnonymousSid >= 0 )
      {
        SystemSid = CUtils::CreateNetworkServiceSid(v2);
        if ( SystemSid >= 0 )
        {
          RdsMsSid = NtCreateRdsMsSid();
          if ( RdsMsSid >= 0 )
            goto LABEL_14;
          v4 = RtlNtStatusToDosError(RdsMsSid);
          SetLastError(v4);
          LastError = GetLastError();
          SystemSid = LastError;
          if ( LastError > 0 )
            SystemSid = (unsigned __int16)LastError | 0x80070000;
          if ( SystemSid >= 0 )
          {
LABEL_14:
            SystemSid = CUtils::CreateAppContainerSid(&CUtils::pAppContainerSid);
            if ( SystemSid >= 0 )
            {
              SystemSid = CUtils::CreateLPACCapabilitySid(&CUtils::pLPACCapabilitySid);
              if ( SystemSid >= 0 )
              {
                IsPersonalTerminalServicesEnabled();
                VersionInfo.dwOSVersionInfoSize = 284;
                VersionInfo.wProductType = 1;
                v6 = VerSetConditionMask(0, 0x80u, 1u);
                CUtils::bIsClientSKU = RtlVerifyVersionInfo(&VersionInfo, 0x80u, v6) >= 0;
                v7 = operator new(0x80u, (const struct std::nothrow_t *)std::nothrow);
                v8 = v7;
                if ( !v7 )
                {
                  g_pObjectTracker = 0;
                  SystemSid = -2147024882;
LABEL_31:
                  CUtils::Destroy();
                  return (unsigned int)SystemSid;
                }
                *v7 = 0;
                v7[30] = 0;
                *((_QWORD *)v7 + 2) = v7 + 2;
                *((_QWORD *)v7 + 1) = v7 + 2;
                g_pObjectTracker = v7;
                SystemSid = CResource::Initialize((CResource *)(v7 + 6));
                *v8 = SystemSid >= 0;
                if ( SystemSid >= 0 )
                {
                  SystemSid = 0;
                  COpsMonitorBase::g_OpsMonitorTimeQueue = CreateTimerQueue();
                  if ( !COpsMonitorBase::g_OpsMonitorTimeQueue )
                  {
                    v9 = GetLastError();
                    SystemSid = v9;
                    if ( v9 > 0 )
                      SystemSid = (unsigned __int16)v9 | 0x80070000;
                    if ( (g_DebugTraceComponent & 0x40) != 0 )
                      _DbgPrintMessage(2, "COpsMonitorBase::Initialize() failed with 0x%08x", SystemSid);
                  }
                  if ( SystemSid >= 0 )
                    return (unsigned int)SystemSid;
                  _DbgPrintMessage(
                    8,
                    "COpsMonitorBase::Initialize failed: 0x%x in %s",
                    (unsigned int)SystemSid,
                    "CUtils::Initialize");
                }
                else
                {
                  _DbgPrintMessage(
                    8,
                    "Tracker.Initialize failed: 0x%x in %s",
                    (unsigned int)SystemSid,
                    "CUtils::Initialize");
                }
              }
              else
              {
                _DbgPrintMessage(
                  8,
                  "CUtils::CreateLPACCapabilitySid failed: 0x%x in %s",
                  (unsigned int)SystemSid,
                  "CUtils::Initialize");
              }
            }
            else
            {
              _DbgPrintMessage(
                8,
                "CUtils::CreateAppContainerSid failed: 0x%x in %s",
                (unsigned int)SystemSid,
                "CUtils::Initialize");
            }
          }
          else
          {
            _DbgPrintMessage(
              8,
              "CUtils::CreateRdsMsSid failed: 0x%x in %s",
              (unsigned int)SystemSid,
              "CUtils::Initialize");
          }
        }
        else
        {
          _DbgPrintMessage(
            8,
            "CUtils::CreateNetworkServiceSid failed: 0x%x in %s",
            (unsigned int)SystemSid,
            "CUtils::Initialize");
        }
      }
      else
      {
        _DbgPrintMessage(8, "NtCreateAnonymousSid failed: 0x%x in %s", (unsigned int)SystemSid, "CUtils::Initialize");
      }
    }
    else
    {
      _DbgPrintMessage(8, "CUtils::CreateAdminSid failed: 0x%x in %s", (unsigned int)SystemSid, "CUtils::Initialize");
    }
  }
  else
  {
    _DbgPrintMessage(8, "CUtil::CreateSystemSid failed: 0x%x in %s", (unsigned int)SystemSid, "CUtils::Initialize");
  }
  if ( SystemSid < 0 )
    goto LABEL_31;
  return (unsigned int)SystemSid;
}

```

## disassembly

```asm
0x1800a235c  mov     [rsp+arg_0], rbx
0x1800a2361  push    rdi
0x1800a2362  sub     rsp, 160h
0x1800a2369  mov     rax, cs:__security_cookie
0x1800a2370  xor     rax, rsp
0x1800a2373  mov     [rsp+168h+var_18], rax
0x1800a237b  mov     edi, 11Ch
0x1800a2380  mov     [rsp+168h+var_148], 0
0x1800a2388  mov     r8d, edi; Size
0x1800a238b  lea     rcx, [rsp+168h+VersionInfo]; void *
0x1800a2390  xor     edx, edx; Val
0x1800a2392  call    memset_0
0x1800a2397  lea     rcx, [rsp+168h+var_148]; int *
0x1800a239c  mov     cs:?g_bDebugSpew@@3HA, 0; int g_bDebugSpew
0x1800a23a6  call    ?IsAppServerInstalled@CUtils@@SAJAEAH@Z; CUtils::IsAppServerInstalled(int &)
0x1800a23ab  mov     eax, [rsp+168h+var_148]
0x1800a23af  lea     rcx, ?pSystemSid@CUtils@@0PEAXEA; void **
0x1800a23b6  mov     cs:?bIsAppCompat@CUtils@@0HA, eax; int CUtils::bIsAppCompat
0x1800a23bc  call    ?CreateSystemSid@CUtils@@SAJPEAPEAX@Z; CUtils::CreateSystemSid(void * *)
0x1800a23c1  mov     ebx, eax
0x1800a23c3  test    eax, eax
0x1800a23c5  jns     short loc_1800A23D3
0x1800a23c7  lea     rdx, aCutilCreatesys; "CUtil::CreateSystemSid failed: 0x%x in "...
0x1800a23ce  jmp     loc_1800A25B0
0x1800a23d3  lea     rcx, ?pAdminSid@CUtils@@0PEAXEA; void **
0x1800a23da  call    ?CreateAdminSid@CUtils@@SAJPEAPEAX@Z; CUtils::CreateAdminSid(void * *)
0x1800a23df  mov     ebx, eax
0x1800a23e1  test    eax, eax
0x1800a23e3  jns     short loc_1800A23F1
0x1800a23e5  lea     rdx, aCutilsCreatead; "CUtils::CreateAdminSid failed: 0x%x in "...
0x1800a23ec  jmp     loc_1800A25B0
0x1800a23f1  call    NtCreateAnonymousSid
0x1800a23f6  mov     ebx, eax
0x1800a23f8  or      ebx, 10000000h
0x1800a23fe  jge     short loc_1800A240C
0x1800a2400  lea     rdx, aNtcreateanonym; "NtCreateAnonymousSid failed: 0x%x in %s"
0x1800a2407  jmp     loc_1800A25B0
0x1800a240c  call    ?CreateNetworkServiceSid@CUtils@@SAJPEAPEAX@Z; CUtils::CreateNetworkServiceSid(void * *)
0x1800a2411  mov     ebx, eax
0x1800a2413  test    eax, eax
0x1800a2415  jns     short loc_1800A2423
0x1800a2417  lea     rdx, aCutilsCreatene; "CUtils::CreateNetworkServiceSid failed:"...
0x1800a241e  jmp     loc_1800A25B0
0x1800a2423  call    NtCreateRdsMsSid
0x1800a2428  test    eax, eax
0x1800a242a  jns     short loc_1800A2473
0x1800a242c  mov     ecx, eax; Status
0x1800a242e  call    cs:__imp_RtlNtStatusToDosError
0x1800a2435  nop     dword ptr [rax+rax+00h]
0x1800a243a  mov     ecx, eax; dwErrCode
0x1800a243c  call    cs:__imp_SetLastError
0x1800a2443  nop     dword ptr [rax+rax+00h]
0x1800a2448  call    cs:__imp_GetLastError
0x1800a244f  nop     dword ptr [rax+rax+00h]
0x1800a2454  mov     ebx, eax
0x1800a2456  test    eax, eax
0x1800a2458  jle     short loc_1800A2463
0x1800a245a  movzx   ebx, ax
0x1800a245d  or      ebx, 80070000h
0x1800a2463  test    ebx, ebx
0x1800a2465  jns     short loc_1800A2473
0x1800a2467  lea     rdx, aCutilsCreaterd; "CUtils::CreateRdsMsSid failed: 0x%x in "...
0x1800a246e  jmp     loc_1800A25B0
0x1800a2473  lea     rcx, ?pAppContainerSid@CUtils@@0PEAXEA; pSid
0x1800a247a  call    ?CreateAppContainerSid@CUtils@@SAJPEAPEAX@Z; CUtils::CreateAppContainerSid(void * *)
0x1800a247f  mov     ebx, eax
0x1800a2481  test    eax, eax
0x1800a2483  jns     short loc_1800A2491
0x1800a2485  lea     rdx, aCutilsCreateap; "CUtils::CreateAppContainerSid failed: 0"...
0x1800a248c  jmp     loc_1800A25B0
0x1800a2491  lea     rcx, ?pLPACCapabilitySid@CUtils@@0PEAXEA; Sid
0x1800a2498  call    ?CreateLPACCapabilitySid@CUtils@@SAJPEAPEAX@Z; CUtils::CreateLPACCapabilitySid(void * *)
0x1800a249d  mov     ebx, eax
0x1800a249f  test    eax, eax
0x1800a24a1  jns     short loc_1800A24AF
0x1800a24a3  lea     rdx, aCutilsCreatelp; "CUtils::CreateLPACCapabilitySid failed:"...
0x1800a24aa  jmp     loc_1800A25B0
0x1800a24af  call    IsPersonalTerminalServicesEnabled
0x1800a24b4  mov     ebx, 80h
0x1800a24b9  mov     [rsp+168h+VersionInfo.dwOSVersionInfoSize], edi
0x1800a24bd  mov     edx, ebx; TypeMask
0x1800a24bf  mov     [rsp+168h+VersionInfo.wProductType], 1
0x1800a24c7  mov     r8b, 1; Condition
0x1800a24ca  xor     ecx, ecx; ConditionMask
0x1800a24cc  call    cs:__imp_VerSetConditionMask
0x1800a24d3  nop     dword ptr [rax+rax+00h]
0x1800a24d8  mov     edx, ebx; TypeMask
0x1800a24da  lea     rcx, [rsp+168h+VersionInfo]; VersionInfo
0x1800a24df  mov     r8, rax; ConditionMask
0x1800a24e2  call    cs:__imp_RtlVerifyVersionInfo
0x1800a24e9  nop     dword ptr [rax+rax+00h]
0x1800a24ee  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800a24f5  mov     ecx, ebx; unsigned __int64
0x1800a24f7  not     eax
0x1800a24f9  shr     eax, 1Fh
0x1800a24fc  mov     cs:?bIsClientSKU@CUtils@@0HA, eax; int CUtils::bIsClientSKU
0x1800a2502  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800a2507  mov     rdi, rax
0x1800a250a  test    rax, rax
0x1800a250d  jz      loc_1800A25CA
0x1800a2513  mov     dword ptr [rax], 0
0x1800a2519  lea     rcx, [rax+8]
0x1800a251d  mov     dword ptr [rax+78h], 0
0x1800a2524  mov     [rcx+8], rcx
0x1800a2528  mov     [rcx], rcx
0x1800a252b  lea     rcx, [rax+18h]; this
0x1800a252f  mov     cs:?g_pObjectTracker@@3PEAVCObjectTracker@@EA, rax; CObjectTracker * g_pObjectTracker
0x1800a2536  call    ?Initialize@CResource@@QEAAJXZ; CResource::Initialize(void)
0x1800a253b  mov     ecx, eax
0x1800a253d  mov     ebx, eax
0x1800a253f  not     ecx
0x1800a2541  shr     ecx, 1Fh
0x1800a2544  mov     [rdi], ecx
0x1800a2546  test    eax, eax
0x1800a2548  jns     short loc_1800A2553
0x1800a254a  lea     rdx, aTrackerInitial; "Tracker.Initialize failed: 0x%x in %s"
0x1800a2551  jmp     short loc_1800A25B0
0x1800a2553  xor     ebx, ebx
0x1800a2555  call    cs:__imp_CreateTimerQueue
0x1800a255c  nop     dword ptr [rax+rax+00h]
0x1800a2561  mov     cs:?g_OpsMonitorTimeQueue@COpsMonitorBase@@0PEAXEA, rax; void * COpsMonitorBase::g_OpsMonitorTimeQueue
0x1800a2568  test    rax, rax
0x1800a256b  jnz     short loc_1800A25A5
0x1800a256d  call    cs:__imp_GetLastError
0x1800a2574  nop     dword ptr [rax+rax+00h]
0x1800a2579  mov     ebx, eax
0x1800a257b  test    eax, eax
0x1800a257d  jle     short loc_1800A2588
0x1800a257f  movzx   ebx, ax
0x1800a2582  or      ebx, 80070000h
0x1800a2588  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 40h; ulong g_DebugTraceComponent
0x1800a258f  jz      short loc_1800A25A5
0x1800a2591  mov     r8d, ebx
0x1800a2594  lea     rdx, aCopsmonitorbas; "COpsMonitorBase::Initialize() failed wi"...
0x1800a259b  mov     ecx, 2; int
0x1800a25a0  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800a25a5  test    ebx, ebx
0x1800a25a7  jns     short loc_1800A25DF
0x1800a25a9  lea     rdx, aCopsmonitorbas_1; "COpsMonitorBase::Initialize failed: 0x%"...
0x1800a25b0  mov     ecx, 8; int
0x1800a25b5  lea     r9, aCutilsInitiali; "CUtils::Initialize"
0x1800a25bc  mov     r8d, ebx
0x1800a25bf  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800a25c4  test    ebx, ebx
0x1800a25c6  jns     short loc_1800A25DF
0x1800a25c8  jmp     short loc_1800A25DA
0x1800a25ca  mov     cs:?g_pObjectTracker@@3PEAVCObjectTracker@@EA, 0; CObjectTracker * g_pObjectTracker
0x1800a25d5  mov     ebx, 8007000Eh
0x1800a25da  call    ?Destroy@CUtils@@SAXXZ; CUtils::Destroy(void)
0x1800a25df  mov     eax, ebx
0x1800a25e1  mov     rcx, [rsp+168h+var_18]
0x1800a25e9  xor     rcx, rsp; StackCookie
0x1800a25ec  call    __security_check_cookie
0x1800a25f1  mov     rbx, [rsp+168h+arg_0]
0x1800a25f9  add     rsp, 160h
0x1800a2600  pop     rdi
0x1800a2601  retn
```
