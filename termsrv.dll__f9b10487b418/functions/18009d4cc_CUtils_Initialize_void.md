# CUtils::Initialize(void)

- ea: `0x18009d4cc`
- end: `0x18009d748`
- name: `?Initialize@CUtils@@SAJXZ`
- size: `636`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180039bf0`

## callees

- `0x18000a210`
- `0x180025fc4`
- `0x1800321f0`
- `0x1800326dc`
- `0x1800330c4`
- `0x18009c828`
- `0x18009c868`
- `0x18009c940`
- `0x18009c9cc`
- `0x18009ca6c`
- `0x18009cef4`
- `0x18009d4cc`
- `0x18009d750`
- `0x1800c4a74`
- `0x1800c4b00`
- `0x1800c4b90`

## import_xrefs

- `ntdll!RtlVerifyVersionInfo` at `0x18009d63a`
- `ntdll!RtlVerifyVersionInfo` at `0x18009d63a`
- `ntdll!VerSetConditionMask` at `0x18009d62a`
- `ntdll!VerSetConditionMask` at `0x18009d62a`
- `ntdll!RtlNtStatusToDosError` at `0x18009d59e`
- `ntdll!RtlNtStatusToDosError` at `0x18009d59e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009d5a6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009d5a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009d5ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009d6b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009d5ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009d6b9`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueue` at `0x18009d6a7`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueue` at `0x18009d6a7`

## string_xrefs

- `0x18009d537`: `CUtil::CreateSystemSid failed: 0x%x in %s`
- `0x18009d570`: `NtCreateAnonymousSid failed: 0x%x in %s`
- `0x18009d555`: `CUtils::CreateAdminSid failed: 0x%x in %s`
- `0x18009d5c5`: `CUtils::CreateRdsMsSid failed: 0x%x in %s`
- `0x18009d587`: `CUtils::CreateNetworkServiceSid failed: 0x%x in %s`
- `0x18009d601`: `CUtils::CreateLPACCapabilitySid failed: 0x%x in %s`
- `0x18009d5e3`: `CUtils::CreateAppContainerSid failed: 0x%x in %s`

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
0x18009d4cc  mov     [rsp+arg_0], rbx
0x18009d4d1  push    rdi
0x18009d4d2  sub     rsp, 160h
0x18009d4d9  mov     rax, cs:__security_cookie
0x18009d4e0  xor     rax, rsp
0x18009d4e3  mov     [rsp+168h+var_18], rax
0x18009d4eb  mov     edi, 11Ch
0x18009d4f0  mov     [rsp+168h+var_148], 0
0x18009d4f8  mov     r8d, edi; Size
0x18009d4fb  lea     rcx, [rsp+168h+VersionInfo]; void *
0x18009d500  xor     edx, edx; Val
0x18009d502  call    memset_0
0x18009d507  lea     rcx, [rsp+168h+var_148]; int *
0x18009d50c  mov     cs:?g_bDebugSpew@@3HA, 0; int g_bDebugSpew
0x18009d516  call    ?IsAppServerInstalled@CUtils@@SAJAEAH@Z; CUtils::IsAppServerInstalled(int &)
0x18009d51b  mov     eax, [rsp+168h+var_148]
0x18009d51f  lea     rcx, ?pSystemSid@CUtils@@0PEAXEA; void **
0x18009d526  mov     cs:?bIsAppCompat@CUtils@@0HA, eax; int CUtils::bIsAppCompat
0x18009d52c  call    ?CreateSystemSid@CUtils@@SAJPEAPEAX@Z; CUtils::CreateSystemSid(void * *)
0x18009d531  mov     ebx, eax
0x18009d533  test    eax, eax
0x18009d535  jns     short loc_18009D543
0x18009d537  lea     rdx, aCutilCreatesys; "CUtil::CreateSystemSid failed: 0x%x in "...
0x18009d53e  jmp     loc_18009D6F6
0x18009d543  lea     rcx, ?pAdminSid@CUtils@@0PEAXEA; void **
0x18009d54a  call    ?CreateAdminSid@CUtils@@SAJPEAPEAX@Z; CUtils::CreateAdminSid(void * *)
0x18009d54f  mov     ebx, eax
0x18009d551  test    eax, eax
0x18009d553  jns     short loc_18009D561
0x18009d555  lea     rdx, aCutilsCreatead; "CUtils::CreateAdminSid failed: 0x%x in "...
0x18009d55c  jmp     loc_18009D6F6
0x18009d561  call    NtCreateAnonymousSid
0x18009d566  mov     ebx, eax
0x18009d568  or      ebx, 10000000h
0x18009d56e  jge     short loc_18009D57C
0x18009d570  lea     rdx, aNtcreateanonym; "NtCreateAnonymousSid failed: 0x%x in %s"
0x18009d577  jmp     loc_18009D6F6
0x18009d57c  call    ?CreateNetworkServiceSid@CUtils@@SAJPEAPEAX@Z; CUtils::CreateNetworkServiceSid(void * *)
0x18009d581  mov     ebx, eax
0x18009d583  test    eax, eax
0x18009d585  jns     short loc_18009D593
0x18009d587  lea     rdx, aCutilsCreatene; "CUtils::CreateNetworkServiceSid failed:"...
0x18009d58e  jmp     loc_18009D6F6
0x18009d593  call    NtCreateRdsMsSid
0x18009d598  test    eax, eax
0x18009d59a  jns     short loc_18009D5D1
0x18009d59c  mov     ecx, eax; Status
0x18009d59e  call    cs:__imp_RtlNtStatusToDosError
0x18009d5a4  mov     ecx, eax; dwErrCode
0x18009d5a6  call    cs:__imp_SetLastError
0x18009d5ac  call    cs:__imp_GetLastError
0x18009d5b2  mov     ebx, eax
0x18009d5b4  test    eax, eax
0x18009d5b6  jle     short loc_18009D5C1
0x18009d5b8  movzx   ebx, ax
0x18009d5bb  or      ebx, 80070000h
0x18009d5c1  test    ebx, ebx
0x18009d5c3  jns     short loc_18009D5D1
0x18009d5c5  lea     rdx, aCutilsCreaterd; "CUtils::CreateRdsMsSid failed: 0x%x in "...
0x18009d5cc  jmp     loc_18009D6F6
0x18009d5d1  lea     rcx, ?pAppContainerSid@CUtils@@0PEAXEA; pSid
0x18009d5d8  call    ?CreateAppContainerSid@CUtils@@SAJPEAPEAX@Z; CUtils::CreateAppContainerSid(void * *)
0x18009d5dd  mov     ebx, eax
0x18009d5df  test    eax, eax
0x18009d5e1  jns     short loc_18009D5EF
0x18009d5e3  lea     rdx, aCutilsCreateap; "CUtils::CreateAppContainerSid failed: 0"...
0x18009d5ea  jmp     loc_18009D6F6
0x18009d5ef  lea     rcx, ?pLPACCapabilitySid@CUtils@@0PEAXEA; Sid
0x18009d5f6  call    ?CreateLPACCapabilitySid@CUtils@@SAJPEAPEAX@Z; CUtils::CreateLPACCapabilitySid(void * *)
0x18009d5fb  mov     ebx, eax
0x18009d5fd  test    eax, eax
0x18009d5ff  jns     short loc_18009D60D
0x18009d601  lea     rdx, aCutilsCreatelp; "CUtils::CreateLPACCapabilitySid failed:"...
0x18009d608  jmp     loc_18009D6F6
0x18009d60d  call    IsPersonalTerminalServicesEnabled
0x18009d612  mov     ebx, 80h
0x18009d617  mov     [rsp+168h+VersionInfo.dwOSVersionInfoSize], edi
0x18009d61b  mov     edx, ebx; TypeMask
0x18009d61d  mov     [rsp+168h+VersionInfo.wProductType], 1
0x18009d625  mov     r8b, 1; Condition
0x18009d628  xor     ecx, ecx; ConditionMask
0x18009d62a  call    cs:__imp_VerSetConditionMask
0x18009d630  mov     edx, ebx; TypeMask
0x18009d632  lea     rcx, [rsp+168h+VersionInfo]; VersionInfo
0x18009d637  mov     r8, rax; ConditionMask
0x18009d63a  call    cs:__imp_RtlVerifyVersionInfo
0x18009d640  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18009d647  mov     ecx, ebx; unsigned __int64
0x18009d649  not     eax
0x18009d64b  shr     eax, 1Fh
0x18009d64e  mov     cs:?bIsClientSKU@CUtils@@0HA, eax; int CUtils::bIsClientSKU
0x18009d654  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18009d659  mov     rdi, rax
0x18009d65c  test    rax, rax
0x18009d65f  jz      loc_18009D710
0x18009d665  mov     dword ptr [rax], 0
0x18009d66b  lea     rcx, [rax+8]
0x18009d66f  mov     dword ptr [rax+78h], 0
0x18009d676  mov     [rcx+8], rcx
0x18009d67a  mov     [rcx], rcx
0x18009d67d  lea     rcx, [rax+18h]; this
0x18009d681  mov     cs:?g_pObjectTracker@@3PEAVCObjectTracker@@EA, rax; CObjectTracker * g_pObjectTracker
0x18009d688  call    ?Initialize@CResource@@QEAAJXZ; CResource::Initialize(void)
0x18009d68d  mov     ecx, eax
0x18009d68f  mov     ebx, eax
0x18009d691  not     ecx
0x18009d693  shr     ecx, 1Fh
0x18009d696  mov     [rdi], ecx
0x18009d698  test    eax, eax
0x18009d69a  jns     short loc_18009D6A5
0x18009d69c  lea     rdx, aTrackerInitial; "Tracker.Initialize failed: 0x%x in %s"
0x18009d6a3  jmp     short loc_18009D6F6
0x18009d6a5  xor     ebx, ebx
0x18009d6a7  call    cs:__imp_CreateTimerQueue
0x18009d6ad  mov     cs:?g_OpsMonitorTimeQueue@COpsMonitorBase@@0PEAXEA, rax; void * COpsMonitorBase::g_OpsMonitorTimeQueue
0x18009d6b4  test    rax, rax
0x18009d6b7  jnz     short loc_18009D6EB
0x18009d6b9  call    cs:__imp_GetLastError
0x18009d6bf  mov     ebx, eax
0x18009d6c1  test    eax, eax
0x18009d6c3  jle     short loc_18009D6CE
0x18009d6c5  movzx   ebx, ax
0x18009d6c8  or      ebx, 80070000h
0x18009d6ce  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 40h; ulong g_DebugTraceComponent
0x18009d6d5  jz      short loc_18009D6EB
0x18009d6d7  mov     r8d, ebx
0x18009d6da  lea     rdx, aCopsmonitorbas; "COpsMonitorBase::Initialize() failed wi"...
0x18009d6e1  mov     ecx, 2; int
0x18009d6e6  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18009d6eb  test    ebx, ebx
0x18009d6ed  jns     short loc_18009D725
0x18009d6ef  lea     rdx, aCopsmonitorbas_1; "COpsMonitorBase::Initialize failed: 0x%"...
0x18009d6f6  mov     ecx, 8; int
0x18009d6fb  lea     r9, aCutilsInitiali; "CUtils::Initialize"
0x18009d702  mov     r8d, ebx
0x18009d705  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18009d70a  test    ebx, ebx
0x18009d70c  jns     short loc_18009D725
0x18009d70e  jmp     short loc_18009D720
0x18009d710  mov     cs:?g_pObjectTracker@@3PEAVCObjectTracker@@EA, 0; CObjectTracker * g_pObjectTracker
0x18009d71b  mov     ebx, 8007000Eh
0x18009d720  call    ?Destroy@CUtils@@SAXXZ; CUtils::Destroy(void)
0x18009d725  mov     eax, ebx
0x18009d727  mov     rcx, [rsp+168h+var_18]
0x18009d72f  xor     rcx, rsp; StackCookie
0x18009d732  call    __security_check_cookie
0x18009d737  mov     rbx, [rsp+168h+arg_0]
0x18009d73f  add     rsp, 160h
0x18009d746  pop     rdi
0x18009d747  retn
```
