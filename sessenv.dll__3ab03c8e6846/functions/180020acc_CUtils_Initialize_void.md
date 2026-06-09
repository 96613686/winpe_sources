# CUtils::Initialize(void)

- ea: `0x180020acc`
- end: `0x180020d92`
- name: `?Initialize@CUtils@@SAJXZ`
- size: `710`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18001d7f4`

## callees

- `0x180003f30`
- `0x18001a280`
- `0x18001a2a4`
- `0x18001ad5c`
- `0x18001ed10`
- `0x18001f948`
- `0x18001f988`
- `0x18001fb54`
- `0x18001ff00`
- `0x180020acc`
- `0x180020fd4`
- `0x180026830`
- `0x180026968`
- `0x1800269f4`
- `0x180026a84`

## import_xrefs

- `ntdll!VerSetConditionMask` at `0x180020c7d`
- `ntdll!VerSetConditionMask` at `0x180020c7d`
- `ntdll!RtlVerifyVersionInfo` at `0x180020c8d`
- `ntdll!RtlVerifyVersionInfo` at `0x180020c8d`
- `ntdll!RtlNtStatusToDosError` at `0x180020b3a`
- `ntdll!RtlNtStatusToDosError` at `0x180020bc4`
- `ntdll!RtlNtStatusToDosError` at `0x180020b3a`
- `ntdll!RtlNtStatusToDosError` at `0x180020bc4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180020b42`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180020bcc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180020b42`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180020bcc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020b48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020bd2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020c22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020d01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020b48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020bd2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020c22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020d01`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueue` at `0x180020cef`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueue` at `0x180020cef`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180020c18`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180020c18`

## string_xrefs

- `0x180020c3c`: `CUtils::CreateLPACCapabilitySid`
- `0x180020c45`: `ConvertStringSidToSidW failed: 0x%x in %s`
- `0x180020b5d`: `CUtil::CreateSystemSid failed: 0x%x in %s`
- `0x180020b7b`: `CUtils::CreateAdminSid failed: 0x%x in %s`
- `0x180020b96`: `NtCreateAnonymousSid failed: 0x%x in %s`
- `0x180020bad`: `CUtils::CreateNetworkServiceSid failed: 0x%x in %s`
- `0x180020be7`: `CUtils::CreateRdsMsSid failed: 0x%x in %s`
- `0x180020bfe`: `CUtils::CreateAppContainerSid failed: 0x%x in %s`
- `0x180020c54`: `CUtils::CreateLPACCapabilitySid failed: 0x%x in %s`

## pseudocode

```c
__int64 CUtils::Initialize(void)
{
  NTSTATUS SystemSid; // eax
  DWORD v1; // eax
  signed int LastError; // eax
  int AdminSid; // ebx
  const char *v4; // rdx
  int AnonymousSid; // eax
  void **v6; // rcx
  NTSTATUS RdsMsSid; // eax
  void **v8; // rcx
  DWORD v9; // eax
  signed int v10; // eax
  signed int v11; // eax
  ULONGLONG v12; // rax
  _DWORD *v13; // rax
  _DWORD *v14; // rdi
  signed int v15; // eax
  int v17[4]; // [rsp+20h] [rbp-148h] BYREF
  _OSVERSIONINFOEXW VersionInfo; // [rsp+30h] [rbp-138h] BYREF

  v17[0] = 0;
  memset_0(&VersionInfo, 0, sizeof(VersionInfo));
  g_bDebugSpew = 0;
  CUtils::IsAppServerInstalled(v17);
  CUtils::bIsAppCompat = v17[0];
  SystemSid = NtCreateSystemSid();
  if ( SystemSid >= 0 )
    goto LABEL_6;
  v1 = RtlNtStatusToDosError(SystemSid);
  SetLastError(v1);
  LastError = GetLastError();
  AdminSid = LastError;
  if ( LastError > 0 )
    AdminSid = (unsigned __int16)LastError | 0x80070000;
  if ( AdminSid >= 0 )
  {
LABEL_6:
    AdminSid = CUtils::CreateAdminSid(&CUtils::pAdminSid);
    if ( AdminSid >= 0 )
    {
      AnonymousSid = NtCreateAnonymousSid();
      AdminSid = AnonymousSid | 0x10000000;
      if ( AnonymousSid >= 0 )
      {
        AdminSid = CUtils::CreateNetworkServiceSid(v6);
        if ( AdminSid >= 0 )
        {
          RdsMsSid = NtCreateRdsMsSid();
          if ( RdsMsSid >= 0 )
            goto LABEL_17;
          v9 = RtlNtStatusToDosError(RdsMsSid);
          SetLastError(v9);
          v10 = GetLastError();
          AdminSid = v10;
          if ( v10 > 0 )
            AdminSid = (unsigned __int16)v10 | 0x80070000;
          if ( AdminSid >= 0 )
          {
LABEL_17:
            AdminSid = CUtils::CreateAppContainerSid(v8);
            if ( AdminSid >= 0 )
            {
              if ( !ConvertStringSidToSidW(
                      L"S-1-15-3-1024-1864111754-776273317-3666925027-2523908081-3792458206-3582472437-4114419977-1582884857",
                      &CUtils::pLPACCapabilitySid) )
              {
                v11 = GetLastError();
                AdminSid = v11;
                if ( v11 > 0 )
                  AdminSid = (unsigned __int16)v11 | 0x80070000;
                if ( AdminSid < 0 )
                {
                  _DbgPrintMessage(
                    8,
                    "ConvertStringSidToSidW failed: 0x%x in %s",
                    AdminSid,
                    "CUtils::CreateLPACCapabilitySid");
                  _DbgPrintMessage(
                    8,
                    "CUtils::CreateLPACCapabilitySid failed: 0x%x in %s",
                    (unsigned int)AdminSid,
                    "CUtils::Initialize");
                  goto LABEL_35;
                }
              }
              IsPersonalTerminalServicesEnabled();
              VersionInfo.dwOSVersionInfoSize = 284;
              VersionInfo.wProductType = 1;
              v12 = VerSetConditionMask(0, 0x80u, 1u);
              RtlVerifyVersionInfo(&VersionInfo, 0x80u, v12);
              v13 = operator new(0x80u, (const struct std::nothrow_t *)std::nothrow);
              v14 = v13;
              if ( !v13 )
              {
                g_pObjectTracker = 0;
                AdminSid = -2147024882;
LABEL_38:
                CUtils::Destroy();
                return (unsigned int)AdminSid;
              }
              *v13 = 0;
              v13[30] = 0;
              *((_QWORD *)v13 + 2) = v13 + 2;
              *((_QWORD *)v13 + 1) = v13 + 2;
              g_pObjectTracker = v13;
              AdminSid = CResource::Initialize((CResource *)(v13 + 6));
              *v14 = AdminSid >= 0;
              if ( AdminSid >= 0 )
              {
                AdminSid = 0;
                COpsMonitorBase::g_OpsMonitorTimeQueue = CreateTimerQueue();
                if ( !COpsMonitorBase::g_OpsMonitorTimeQueue )
                {
                  v15 = GetLastError();
                  AdminSid = v15;
                  if ( v15 > 0 )
                    AdminSid = (unsigned __int16)v15 | 0x80070000;
                  if ( (g_DebugTraceComponent & 0x40) != 0 )
                    _DbgPrintMessage(2, "COpsMonitorBase::Initialize() failed with 0x%08x", AdminSid);
                }
                if ( AdminSid >= 0 )
                  return (unsigned int)AdminSid;
                v4 = "COpsMonitorBase::Initialize failed: 0x%x in %s";
              }
              else
              {
                v4 = "Tracker.Initialize failed: 0x%x in %s";
              }
            }
            else
            {
              v4 = "CUtils::CreateAppContainerSid failed: 0x%x in %s";
            }
          }
          else
          {
            v4 = "CUtils::CreateRdsMsSid failed: 0x%x in %s";
          }
        }
        else
        {
          v4 = "CUtils::CreateNetworkServiceSid failed: 0x%x in %s";
        }
      }
      else
      {
        v4 = "NtCreateAnonymousSid failed: 0x%x in %s";
      }
    }
    else
    {
      v4 = "CUtils::CreateAdminSid failed: 0x%x in %s";
    }
  }
  else
  {
    v4 = "CUtil::CreateSystemSid failed: 0x%x in %s";
  }
  _DbgPrintMessage(8, v4, (unsigned int)AdminSid, "CUtils::Initialize", *(_QWORD *)v17);
LABEL_35:
  if ( AdminSid < 0 )
    goto LABEL_38;
  return (unsigned int)AdminSid;
}

```

## disassembly

```asm
0x180020acc  mov     [rsp+arg_0], rbx
0x180020ad1  mov     [rsp+arg_8], rbp
0x180020ad6  push    rdi
0x180020ad7  sub     rsp, 160h
0x180020ade  mov     rax, cs:__security_cookie
0x180020ae5  xor     rax, rsp
0x180020ae8  mov     [rsp+168h+var_18], rax
0x180020af0  mov     edi, 11Ch
0x180020af5  mov     [rsp+168h+var_148], 0
0x180020afd  mov     r8d, edi; Size
0x180020b00  lea     rcx, [rsp+168h+VersionInfo]; void *
0x180020b05  xor     edx, edx; Val
0x180020b07  call    memset_0
0x180020b0c  lea     rcx, [rsp+168h+var_148]; int *
0x180020b11  mov     cs:?g_bDebugSpew@@3HA, 0; int g_bDebugSpew
0x180020b1b  call    ?IsAppServerInstalled@CUtils@@SAJAEAH@Z; CUtils::IsAppServerInstalled(int &)
0x180020b20  mov     eax, [rsp+168h+var_148]
0x180020b24  mov     cs:?bIsAppCompat@CUtils@@0HA, eax; int CUtils::bIsAppCompat
0x180020b2a  call    NtCreateSystemSid
0x180020b2f  mov     ebp, 80070000h
0x180020b34  test    eax, eax
0x180020b36  jns     short loc_180020B69
0x180020b38  mov     ecx, eax; Status
0x180020b3a  call    cs:__imp_RtlNtStatusToDosError
0x180020b40  mov     ecx, eax; dwErrCode
0x180020b42  call    cs:__imp_SetLastError
0x180020b48  call    cs:__imp_GetLastError
0x180020b4e  mov     ebx, eax
0x180020b50  test    eax, eax
0x180020b52  jle     short loc_180020B59
0x180020b54  movzx   ebx, ax
0x180020b57  or      ebx, ebp
0x180020b59  test    ebx, ebx
0x180020b5b  jns     short loc_180020B69
0x180020b5d  lea     rdx, aCutilCreatesys; "CUtil::CreateSystemSid failed: 0x%x in "...
0x180020b64  jmp     loc_180020D3A
0x180020b69  lea     rcx, ?pAdminSid@CUtils@@0PEAXEA; void **
0x180020b70  call    ?CreateAdminSid@CUtils@@SAJPEAPEAX@Z; CUtils::CreateAdminSid(void * *)
0x180020b75  mov     ebx, eax
0x180020b77  test    eax, eax
0x180020b79  jns     short loc_180020B87
0x180020b7b  lea     rdx, aCutilsCreatead; "CUtils::CreateAdminSid failed: 0x%x in "...
0x180020b82  jmp     loc_180020D3A
0x180020b87  call    NtCreateAnonymousSid
0x180020b8c  mov     ebx, eax
0x180020b8e  or      ebx, 10000000h
0x180020b94  jge     short loc_180020BA2
0x180020b96  lea     rdx, aNtcreateanonym; "NtCreateAnonymousSid failed: 0x%x in %s"
0x180020b9d  jmp     loc_180020D3A
0x180020ba2  call    ?CreateNetworkServiceSid@CUtils@@SAJPEAPEAX@Z; CUtils::CreateNetworkServiceSid(void * *)
0x180020ba7  mov     ebx, eax
0x180020ba9  test    eax, eax
0x180020bab  jns     short loc_180020BB9
0x180020bad  lea     rdx, aCutilsCreatene; "CUtils::CreateNetworkServiceSid failed:"...
0x180020bb4  jmp     loc_180020D3A
0x180020bb9  call    NtCreateRdsMsSid
0x180020bbe  test    eax, eax
0x180020bc0  jns     short loc_180020BF3
0x180020bc2  mov     ecx, eax; Status
0x180020bc4  call    cs:__imp_RtlNtStatusToDosError
0x180020bca  mov     ecx, eax; dwErrCode
0x180020bcc  call    cs:__imp_SetLastError
0x180020bd2  call    cs:__imp_GetLastError
0x180020bd8  mov     ebx, eax
0x180020bda  test    eax, eax
0x180020bdc  jle     short loc_180020BE3
0x180020bde  movzx   ebx, ax
0x180020be1  or      ebx, ebp
0x180020be3  test    ebx, ebx
0x180020be5  jns     short loc_180020BF3
0x180020be7  lea     rdx, aCutilsCreaterd; "CUtils::CreateRdsMsSid failed: 0x%x in "...
0x180020bee  jmp     loc_180020D3A
0x180020bf3  call    ?CreateAppContainerSid@CUtils@@SAJPEAPEAX@Z; CUtils::CreateAppContainerSid(void * *)
0x180020bf8  mov     ebx, eax
0x180020bfa  test    eax, eax
0x180020bfc  jns     short loc_180020C0A
0x180020bfe  lea     rdx, aCutilsCreateap; "CUtils::CreateAppContainerSid failed: 0"...
0x180020c05  jmp     loc_180020D3A
0x180020c0a  lea     rdx, ?pLPACCapabilitySid@CUtils@@0PEAXEA; Sid
0x180020c11  lea     rcx, StringSid; "S-1-15-3-1024-1864111754-776273317-3666"...
0x180020c18  call    cs:__imp_ConvertStringSidToSidW
0x180020c1e  test    eax, eax
0x180020c20  jnz     short loc_180020C60
0x180020c22  call    cs:__imp_GetLastError
0x180020c28  mov     ebx, eax
0x180020c2a  test    eax, eax
0x180020c2c  jle     short loc_180020C33
0x180020c2e  movzx   ebx, ax
0x180020c31  or      ebx, ebp
0x180020c33  test    ebx, ebx
0x180020c35  jns     short loc_180020C60
0x180020c37  mov     edi, 8
0x180020c3c  lea     r9, aCutilsCreatelp_0; "CUtils::CreateLPACCapabilitySid"
0x180020c43  mov     ecx, edi; int
0x180020c45  lea     rdx, aConvertstrings_2; "ConvertStringSidToSidW failed: 0x%x in "...
0x180020c4c  mov     r8d, ebx
0x180020c4f  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180020c54  lea     rdx, aCutilsCreatelp; "CUtils::CreateLPACCapabilitySid failed:"...
0x180020c5b  jmp     loc_180020D3F
0x180020c60  call    IsPersonalTerminalServicesEnabled
0x180020c65  mov     ebx, 80h
0x180020c6a  mov     [rsp+168h+VersionInfo.dwOSVersionInfoSize], edi
0x180020c6e  mov     edx, ebx; TypeMask
0x180020c70  mov     [rsp+168h+VersionInfo.wProductType], 1
0x180020c78  mov     r8b, 1; Condition
0x180020c7b  xor     ecx, ecx; ConditionMask
0x180020c7d  call    cs:__imp_VerSetConditionMask
0x180020c83  mov     edx, ebx; TypeMask
0x180020c85  lea     rcx, [rsp+168h+VersionInfo]; VersionInfo
0x180020c8a  mov     r8, rax; ConditionMask
0x180020c8d  call    cs:__imp_RtlVerifyVersionInfo
0x180020c93  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180020c9a  mov     ecx, ebx; unsigned __int64
0x180020c9c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180020ca1  mov     rdi, rax
0x180020ca4  test    rax, rax
0x180020ca7  jz      loc_180020D56
0x180020cad  mov     dword ptr [rax], 0
0x180020cb3  lea     rcx, [rax+8]
0x180020cb7  mov     dword ptr [rax+78h], 0
0x180020cbe  mov     [rcx+8], rcx
0x180020cc2  mov     [rcx], rcx
0x180020cc5  lea     rcx, [rax+18h]; this
0x180020cc9  mov     cs:?g_pObjectTracker@@3PEAVCObjectTracker@@EA, rax; CObjectTracker * g_pObjectTracker
0x180020cd0  call    ?Initialize@CResource@@QEAAJXZ; CResource::Initialize(void)
0x180020cd5  mov     ecx, eax
0x180020cd7  mov     ebx, eax
0x180020cd9  not     ecx
0x180020cdb  shr     ecx, 1Fh
0x180020cde  mov     [rdi], ecx
0x180020ce0  test    eax, eax
0x180020ce2  jns     short loc_180020CED
0x180020ce4  lea     rdx, aTrackerInitial; "Tracker.Initialize failed: 0x%x in %s"
0x180020ceb  jmp     short loc_180020D3A
0x180020ced  xor     ebx, ebx
0x180020cef  call    cs:__imp_CreateTimerQueue
0x180020cf5  mov     cs:?g_OpsMonitorTimeQueue@COpsMonitorBase@@0PEAXEA, rax; void * COpsMonitorBase::g_OpsMonitorTimeQueue
0x180020cfc  test    rax, rax
0x180020cff  jnz     short loc_180020D2F
0x180020d01  call    cs:__imp_GetLastError
0x180020d07  mov     ebx, eax
0x180020d09  test    eax, eax
0x180020d0b  jle     short loc_180020D12
0x180020d0d  movzx   ebx, ax
0x180020d10  or      ebx, ebp
0x180020d12  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 40h; ulong g_DebugTraceComponent
0x180020d19  jz      short loc_180020D2F
0x180020d1b  mov     r8d, ebx
0x180020d1e  lea     rdx, aCopsmonitorbas; "COpsMonitorBase::Initialize() failed wi"...
0x180020d25  mov     ecx, 2; int
0x180020d2a  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180020d2f  test    ebx, ebx
0x180020d31  jns     short loc_180020D6B
0x180020d33  lea     rdx, aCopsmonitorbas_1; "COpsMonitorBase::Initialize failed: 0x%"...
0x180020d3a  mov     edi, 8
0x180020d3f  lea     r9, aCutilsInitiali; "CUtils::Initialize"
0x180020d46  mov     r8d, ebx
0x180020d49  mov     ecx, edi; int
0x180020d4b  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180020d50  test    ebx, ebx
0x180020d52  jns     short loc_180020D6B
0x180020d54  jmp     short loc_180020D66
0x180020d56  mov     cs:?g_pObjectTracker@@3PEAVCObjectTracker@@EA, 0; CObjectTracker * g_pObjectTracker
0x180020d61  mov     ebx, 8007000Eh
0x180020d66  call    ?Destroy@CUtils@@SAXXZ; CUtils::Destroy(void)
0x180020d6b  mov     eax, ebx
0x180020d6d  mov     rcx, [rsp+168h+var_18]
0x180020d75  xor     rcx, rsp; StackCookie
0x180020d78  call    __security_check_cookie
0x180020d7d  lea     r11, [rsp+168h+var_8]
0x180020d85  mov     rbx, [r11+10h]
0x180020d89  mov     rbp, [r11+18h]
0x180020d8d  mov     rsp, r11
0x180020d90  pop     rdi
0x180020d91  retn
```
