# CWdsService::Initialize(void)

- ea: `0x180009da4`
- end: `0x18000a331`
- name: `?Initialize@CWdsService@@QEAAKXZ`
- size: `1421`
- prototype: `unsigned int __fastcall(CWdsService *__hidden this)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18000fa30`

## callees

- `0x180009cdc`
- `0x180009da4`
- `0x18000aa50`
- `0x18000b1ec`
- `0x18000c3b4`
- `0x18000d380`
- `0x18000e310`
- `0x18000e360`
- `0x18000ebe4`
- `0x18000f0dc`
- `0x18000f2c4`
- `0x180012790`
- `0x180013638`
- `0x180013d7c`
- `0x18001ac90`
- `0x18001ad9c`
- `0x18001c12a`
- `0x18001c150`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180009e23`
- `KERNEL32!GetLastError` at `0x180009e7b`
- `KERNEL32!GetLastError` at `0x180009fa1`
- `KERNEL32!GetLastError` at `0x180009fb5`
- `KERNEL32!GetLastError` at `0x180009e23`
- `KERNEL32!GetLastError` at `0x180009e7b`
- `KERNEL32!GetLastError` at `0x180009fa1`
- `KERNEL32!GetLastError` at `0x180009fb5`
- `KERNEL32!LeaveCriticalSection` at `0x18000a214`
- `KERNEL32!LeaveCriticalSection` at `0x18000a214`
- `KERNEL32!EnterCriticalSection` at `0x18000a1c5`
- `KERNEL32!EnterCriticalSection` at `0x18000a1c5`
- `KERNEL32!GetProcessMitigationPolicy` at `0x180009f63`
- `KERNEL32!GetProcessMitigationPolicy` at `0x180009f63`
- `KERNEL32!GetCurrentProcess` at `0x180009f45`
- `KERNEL32!GetCurrentProcess` at `0x180009f45`
- `KERNEL32!SetProcessMitigationPolicy` at `0x180009f91`
- `KERNEL32!SetProcessMitigationPolicy` at `0x180009f91`
- `KERNEL32!CreateEventW` at `0x180009e0f`
- `KERNEL32!CreateEventW` at `0x180009e0f`
- `WS2_32!__imp_WSAGetLastError` at `0x180009ecc`
- `WS2_32!__imp_WSAGetLastError` at `0x180009ecc`
- `WS2_32!__imp_WSAStartup` at `0x180009ebc`
- `WS2_32!__imp_WSAStartup` at `0x180009ebc`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180009ff0`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000a052`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000a080`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180009ff0`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000a052`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000a080`
- `WdsServerCommonLib!?Initialize@CTrace@@QEAAKPEBGH@Z` at `0x180009f08`
- `WdsServerCommonLib!?Initialize@CTrace@@QEAAKPEBGH@Z` at `0x180009f08`
- `WdsServerCommonLib!?Initialize@CEventLog@@QEAAKPEBGG@Z` at `0x18000a0a8`
- `WdsServerCommonLib!?Initialize@CEventLog@@QEAAKPEBGG@Z` at `0x18000a0a8`
- `WdsServerCommonLib!?RegisterServiceCtrlHandlerW@CService@@SAPEAUSERVICE_STATUS_HANDLE__@@PEBGP6AXK@Z@Z` at `0x180009e66`
- `WdsServerCommonLib!?RegisterServiceCtrlHandlerW@CService@@SAPEAUSERVICE_STATUS_HANDLE__@@PEBGP6AXK@Z@Z` at `0x180009e66`
- `WdsServerCommonLib!?InitializeServer@CPerfCounters@@QEAAKAEBU_GUID@@0K@Z` at `0x18000a119`
- `WdsServerCommonLib!?InitializeServer@CPerfCounters@@QEAAKAEBU_GUID@@0K@Z` at `0x18000a119`
- `ntdll!RtlGetVersion` at `0x18000a00e`
- `ntdll!RtlGetVersion` at `0x18000a00e`
- `ntdll!RtlNtStatusToDosError` at `0x18000a062`
- `ntdll!RtlNtStatusToDosError` at `0x18000a062`
- `WdsDiag!WdsDiagInitialize` at `0x18000a0d3`
- `WdsDiag!WdsDiagInitialize` at `0x18000a0d3`

## string_xrefs

- `0x180009fe1`: `Redirection guard failed , go to cleanup and shutdown service`

## pseudocode

```c
__int64 __fastcall CWdsService::Initialize(struct _RTL_CRITICAL_SECTION *this)
{
  int v2; // esi
  __int64 v3; // rbx
  struct _RTL_CRITICAL_SECTION_DEBUG *EventW; // rax
  DWORD LastError; // eax
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r9
  struct SERVICE_STATUS_HANDLE__ *v9; // rax
  __int64 v10; // rdx
  __int64 v11; // r8
  unsigned int Error; // eax
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // rdx
  __int64 v16; // r8
  HANDLE CurrentProcess; // rax
  __int64 v18; // rdx
  __int64 v19; // r8
  DWORD v20; // eax
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // r9
  int Version; // eax
  ULONG v25; // eax
  __int64 v26; // rdx
  __int64 v27; // r8
  __int64 v28; // rdx
  __int64 v29; // r8
  __int64 v30; // rdx
  __int64 v31; // r8
  __int64 v32; // rdx
  __int64 v33; // r8
  __int64 v34; // rdx
  __int64 v35; // r8
  __int64 v36; // rdx
  __int64 v37; // r8
  __int64 v38; // rdx
  __int64 v39; // r8
  unsigned int v40; // eax
  __int64 v41; // rdx
  __int64 v42; // r8
  __int64 v43; // rdx
  __int64 v44; // r8
  __int64 v45; // rdx
  __int64 v46; // r8
  __int64 v47; // rdx
  __int64 v48; // r8
  __int64 v49; // rdx
  __int64 v50; // r8
  __int64 v51; // rdx
  __int64 v52; // r8
  __int64 v53; // rdx
  __int64 v54; // r8
  unsigned int v55; // eax
  __int64 v56; // rdx
  __int64 v57; // r8
  DWORD dwMinorVersion; // [rsp+20h] [rbp-E0h]
  DWORD dwBuildNumber; // [rsp+28h] [rbp-D8h]
  int v61; // [rsp+30h] [rbp-D0h]
  int v62; // [rsp+38h] [rbp-C8h]
  int v63; // [rsp+40h] [rbp-C0h] BYREF
  int v64[3]; // [rsp+44h] [rbp-BCh] BYREF
  _OSVERSIONINFOW VersionInformation; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 v66; // [rsp+164h] [rbp+64h]
  unsigned __int16 v67; // [rsp+166h] [rbp+66h]
  WSAData WSAData; // [rsp+170h] [rbp+70h] BYREF

  v2 = 0;
  v64[0] = 0;
  memset_0(&WSAData, 0, sizeof(WSAData));
  memset_0(&VersionInformation, 0, 0x11Cu);
  McGenEventRegister_EventRegister();
  LODWORD(v3) = 0;
  EventW = (struct _RTL_CRITICAL_SECTION_DEBUG *)CreateEventW(0, 0, 0, 0);
  this->DebugInfo = EventW;
  if ( EventW )
  {
    this->LockCount = 16;
    this->RecursionCount = 2;
    this->OwningThread = (HANDLE)5;
    this->LockSemaphore = 0;
    LODWORD(this->SpinCount) = 240000;
    v9 = CService::RegisterServiceCtrlHandlerW(L"WDSServer", (void (*)(unsigned int))WdsSendControl);
    this[1].DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)v9;
    if ( v9 )
      goto LABEL_6;
    LastError = GetLastError();
    v8 = 541;
  }
  else
  {
    LastError = GetLastError();
    v8 = 521;
  }
  LODWORD(v3) = ElValidateWin32_0(LastError, v6, v7, v8);
LABEL_6:
  if ( (unsigned int)ElValidateWin32_0((unsigned int)v3, v10, v11, 191) )
    goto LABEL_39;
  CWdsService::UpdateProgress((CWdsService *)this);
  if ( WSAStartup(2u, &WSAData) )
  {
    Error = WSAGetLastError();
    LODWORD(v3) = ElValidateWin32_0(Error, v13, v14, 201);
    goto LABEL_39;
  }
  CWdsService::UpdateProgress((CWdsService *)this);
  v3 = CTrace::Initialize((CTrace *)qword_180039310, L"WDSServer", 0);
  if ( (unsigned int)ElValidateWin32_0(v3, v15, v16, 211) )
    goto LABEL_39;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_4055748921>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_4055748921>::GetImpl'::`2'::impl) )
  {
    v63 = 0;
    LODWORD(v3) = 0;
    CurrentProcess = GetCurrentProcess();
    if ( (unsigned int)GetProcessMitigationPolicy(CurrentProcess, 16, &v63) )
    {
      if ( (v63 & 1) != 0 || (v63 |= 1u, (unsigned int)SetProcessMitigationPolicy(16, &v63)) )
      {
LABEL_17:
        if ( (unsigned int)ElValidateWin32_0((unsigned int)v3, v18, v19, 217) )
        {
          CTrace::Trace(
            (CTrace *)qword_180039310,
            0x80000u,
            L"Redirection guard failed , go to cleanup and shutdown service");
          goto LABEL_39;
        }
        goto LABEL_19;
      }
      v20 = GetLastError();
      v23 = 143;
    }
    else
    {
      v20 = GetLastError();
      v23 = 149;
    }
    LODWORD(v3) = ElValidateWin32_0(v20, v21, v22, v23);
    goto LABEL_17;
  }
LABEL_19:
  VersionInformation.dwOSVersionInfoSize = 284;
  Version = RtlGetVersion(&VersionInformation);
  if ( Version < 0 )
  {
    v25 = RtlNtStatusToDosError(Version);
    CTrace::Trace(
      (CTrace *)qword_180039310,
      0x40000u,
      L"Failed to query OS version information, system error code: %u",
      v25);
  }
  else
  {
    v62 = v67;
    v61 = v66;
    dwBuildNumber = VersionInformation.dwBuildNumber;
    dwMinorVersion = VersionInformation.dwMinorVersion;
    CTrace::Trace(
      (CTrace *)qword_180039310,
      0x20000u,
      L"Running on OS version %u.%u build %u sp %u.%u",
      VersionInformation.dwMajorVersion,
      dwMinorVersion,
      dwBuildNumber,
      v61,
      v62);
  }
  CWdsService::UpdateProgress((CWdsService *)this);
  v3 = CEventLog::Initialize((CEventLog *)qword_180039300, L"WDSServer", 0x100u);
  if ( !(unsigned int)ElValidateWin32_0(v3, v26, v27, 249) )
  {
    CWdsService::UpdateProgress((CWdsService *)this);
    LODWORD(v3) = WdsDiagInitialize();
    if ( !(unsigned int)ElValidateWin32_0((unsigned int)v3, v28, v29, 258) )
    {
      CWdsService::UpdateProgress((CWdsService *)this);
      LODWORD(v3) = CPerfCounters::InitializeServer(
                      (CPerfCounters *)&g_PerfCounters,
                      (const struct _GUID *)qword_1800219F8,
                      (const struct _GUID *)qword_1800219E8,
                      0x28u);
      if ( !(unsigned int)ElValidateWin32_0((unsigned int)v3, v30, v31, 267) )
      {
        CWdsService::UpdateProgress((CWdsService *)this);
        LODWORD(v3) = CWorkItemHandler::Initialize((CWorkItemHandler *)&this[1679].LockCount);
        if ( !(unsigned int)ElValidateWin32_0((unsigned int)v3, v32, v33, 276) )
        {
          CWdsService::UpdateProgress((CWdsService *)this);
          LODWORD(v3) = CInterfaceHandler::Initialize((CInterfaceHandler *)&this[1].LockCount);
          if ( !(unsigned int)ElValidateWin32_0((unsigned int)v3, v34, v35, 285) )
          {
            CWdsService::UpdateProgress((CWdsService *)this);
            LODWORD(v3) = WdsVssWriterPreinitialize();
            if ( !(unsigned int)ElValidateWin32_0((unsigned int)v3, v36, v37, 295) )
            {
              CWdsService::UpdateProgress((CWdsService *)this);
              EnterCriticalSection(this + 1683);
              LODWORD(v3) = CWdsService::ReadServerDuid((CWdsService *)this);
              if ( (_DWORD)v3 )
              {
                v40 = 0;
                if ( (_DWORD)v3 != 2 )
                  v40 = v3;
                LODWORD(v3) = v40;
                if ( !(unsigned int)ElValidateWin32_0(v40, v38, v39, 1447) )
                {
                  LODWORD(v3) = CWdsService::RegenerateServerDuid((CWdsService *)this);
                  ElValidateWin32_0((unsigned int)v3, v41, v42, 1450);
                }
              }
              LeaveCriticalSection(this + 1683);
              if ( !(unsigned int)ElValidateWin32_0((unsigned int)v3, v43, v44, 304) )
              {
                LODWORD(v3) = CWdsProvidersHandler::Initialize((CWdsProvidersHandler *)&this[1676].OwningThread);
                if ( !(unsigned int)ElValidateWin32_0((unsigned int)v3, v45, v46, 310) )
                {
                  CWdsService::UpdateProgress((CWdsService *)this);
                  LODWORD(v3) = WdsVssWriterInitialize();
                  if ( !(unsigned int)ElValidateWin32_0((unsigned int)v3, v47, v48, 318) )
                  {
                    CWdsService::UpdateProgress((CWdsService *)this);
                    LODWORD(v3) = CTimer<CWdsService>::Initialize(&this[1681].LockSemaphore);
                    if ( !(unsigned int)ElValidateWin32_0((unsigned int)v3, v49, v50, 326) )
                    {
                      CWdsService::UpdateProgress((CWdsService *)this);
                      LODWORD(v3) = CWdsService::UpdateSettings((CWdsService *)this);
                      if ( !(unsigned int)ElValidateWin32_0((unsigned int)v3, v51, v52, 334) )
                      {
                        CWdsService::UpdateProgress((CWdsService *)this);
                        LODWORD(v3) = CWdsService::OnStart((CWdsService *)this, v64);
                        ElValidateWin32_0((unsigned int)v3, v53, v54, 342);
                        v2 = v64[0];
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_39:
  v55 = CWdsService::Shutdown((CWdsService *)this, v2, v3);
  ElValidateWin32_0(v55, v56, v57, 348);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180009da4  mov     [rsp-8+arg_8], rbx
0x180009da9  mov     [rsp-8+arg_10], rsi
0x180009dae  push    rbp
0x180009daf  push    rdi
0x180009db0  push    r14
0x180009db2  lea     rbp, [rsp-220h]
0x180009dba  sub     rsp, 320h
0x180009dc1  mov     rax, cs:__security_cookie
0x180009dc8  xor     rax, rsp
0x180009dcb  mov     [rbp+230h+var_20], rax
0x180009dd2  mov     rdi, rcx
0x180009dd5  xor     esi, esi
0x180009dd7  lea     rcx, [rbp+230h+WSAData]; void *
0x180009ddb  mov     [rsp+330h+var_2EC], esi
0x180009ddf  xor     edx, edx; Val
0x180009de1  mov     r8d, 198h; Size
0x180009de7  call    memset_0
0x180009dec  xor     edx, edx; Val
0x180009dee  lea     rcx, [rsp+330h+VersionInformation]; void *
0x180009df3  mov     r8d, 11Ch; Size
0x180009df9  call    memset_0
0x180009dfe  call    McGenEventRegister_EventRegister
0x180009e03  xor     r9d, r9d; lpName
0x180009e06  xor     r8d, r8d; bInitialState
0x180009e09  xor     edx, edx; bManualReset
0x180009e0b  xor     ecx, ecx; lpEventAttributes
0x180009e0d  mov     ebx, esi
0x180009e0f  call    cs:__imp_CreateEventW
0x180009e16  nop     dword ptr [rax+rax+00h]
0x180009e1b  mov     [rdi], rax
0x180009e1e  test    rax, rax
0x180009e21  jnz     short loc_180009E37
0x180009e23  call    cs:__imp_GetLastError
0x180009e2a  nop     dword ptr [rax+rax+00h]
0x180009e2f  mov     r9d, 209h
0x180009e35  jmp     short loc_180009E8D
0x180009e37  lea     rdx, WdsSendControl
0x180009e3e  mov     dword ptr [rdi+8], 10h
0x180009e45  lea     rcx, aWdsserver; "WDSServer"
0x180009e4c  mov     dword ptr [rdi+0Ch], 2
0x180009e53  mov     qword ptr [rdi+10h], 5
0x180009e5b  mov     [rdi+18h], rsi
0x180009e5f  mov     dword ptr [rdi+20h], 3A980h
0x180009e66  call    cs:__imp_?RegisterServiceCtrlHandlerW@CService@@SAPEAUSERVICE_STATUS_HANDLE__@@PEBGP6AXK@Z@Z; CService::RegisterServiceCtrlHandlerW(ushort const *,void (*)(ulong))
0x180009e6d  nop     dword ptr [rax+rax+00h]
0x180009e72  mov     [rdi+28h], rax
0x180009e76  test    rax, rax
0x180009e79  jnz     short loc_180009E96
0x180009e7b  call    cs:__imp_GetLastError
0x180009e82  nop     dword ptr [rax+rax+00h]
0x180009e87  mov     r9d, 21Dh
0x180009e8d  mov     ecx, eax
0x180009e8f  call    ElValidateWin32_0
0x180009e94  mov     ebx, eax
0x180009e96  mov     r9d, 0BFh
0x180009e9c  mov     ecx, ebx
0x180009e9e  call    ElValidateWin32_0
0x180009ea3  test    eax, eax
0x180009ea5  jnz     loc_18000A2ED
0x180009eab  mov     rcx, rdi; this
0x180009eae  call    ?UpdateProgress@CWdsService@@QEAAKXZ; CWdsService::UpdateProgress(void)
0x180009eb3  mov     ecx, 2; wVersionRequested
0x180009eb8  lea     rdx, [rbp+230h+WSAData]; lpWSAData
0x180009ebc  call    cs:__imp_WSAStartup
0x180009ec3  nop     dword ptr [rax+rax+00h]
0x180009ec8  test    eax, eax
0x180009eca  jz      short loc_180009EEC
0x180009ecc  call    cs:__imp_WSAGetLastError
0x180009ed3  nop     dword ptr [rax+rax+00h]
0x180009ed8  mov     ecx, eax
0x180009eda  mov     r9d, 0C9h
0x180009ee0  call    ElValidateWin32_0
0x180009ee5  mov     ebx, eax
0x180009ee7  jmp     loc_18000A2ED
0x180009eec  mov     rcx, rdi; this
0x180009eef  call    ?UpdateProgress@CWdsService@@QEAAKXZ; CWdsService::UpdateProgress(void)
0x180009ef4  lea     r14, qword_180039310
0x180009efb  xor     r8d, r8d
0x180009efe  mov     rcx, r14
0x180009f01  lea     rdx, aWdsserver; "WDSServer"
0x180009f08  call    cs:__imp_?Initialize@CTrace@@QEAAKPEBGH@Z; CTrace::Initialize(ushort const *,int)
0x180009f0f  nop     dword ptr [rax+rax+00h]
0x180009f14  mov     ecx, eax
0x180009f16  mov     r9d, 0D3h
0x180009f1c  mov     ebx, eax
0x180009f1e  call    ElValidateWin32_0
0x180009f23  test    eax, eax
0x180009f25  jnz     loc_18000A2ED
0x180009f2b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_4055748921@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_4055748921@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_4055748921> `wil::Feature<__WilFeatureTraits_Feature_4055748921>::GetImpl(void)'::`2'::impl
0x180009f32  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_4055748921@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_4055748921>::__private_IsEnabled(void)
0x180009f37  test    al, al
0x180009f39  jz      loc_18000A001
0x180009f3f  mov     [rsp+330h+var_2F0], esi
0x180009f43  mov     ebx, esi
0x180009f45  call    cs:__imp_GetCurrentProcess
0x180009f4c  nop     dword ptr [rax+rax+00h]
0x180009f51  mov     r9d, 4
0x180009f57  lea     r8, [rsp+330h+var_2F0]
0x180009f5c  mov     rcx, rax
0x180009f5f  lea     edx, [r9+0Ch]
0x180009f63  call    cs:__imp_GetProcessMitigationPolicy
0x180009f6a  nop     dword ptr [rax+rax+00h]
0x180009f6f  test    eax, eax
0x180009f71  jz      short loc_180009FB5
0x180009f73  mov     eax, [rsp+330h+var_2F0]
0x180009f77  test    al, 1
0x180009f79  jnz     short loc_180009FD0
0x180009f7b  mov     r8d, 4
0x180009f81  lea     rdx, [rsp+330h+var_2F0]
0x180009f86  or      eax, 1
0x180009f89  mov     [rsp+330h+var_2F0], eax
0x180009f8d  lea     ecx, [r8+0Ch]
0x180009f91  call    cs:__imp_SetProcessMitigationPolicy
0x180009f98  nop     dword ptr [rax+rax+00h]
0x180009f9d  test    eax, eax
0x180009f9f  jnz     short loc_180009FD0
0x180009fa1  call    cs:__imp_GetLastError
0x180009fa8  nop     dword ptr [rax+rax+00h]
0x180009fad  mov     r9d, 8Fh
0x180009fb3  jmp     short loc_180009FC7
0x180009fb5  call    cs:__imp_GetLastError
0x180009fbc  nop     dword ptr [rax+rax+00h]
0x180009fc1  mov     r9d, 95h
0x180009fc7  mov     ecx, eax
0x180009fc9  call    ElValidateWin32_0
0x180009fce  mov     ebx, eax
0x180009fd0  mov     r9d, 0D9h
0x180009fd6  mov     ecx, ebx
0x180009fd8  call    ElValidateWin32_0
0x180009fdd  test    eax, eax
0x180009fdf  jz      short loc_18000A001
0x180009fe1  lea     r8, aRedirectionGua; "Redirection guard failed , go to cleanu"...
0x180009fe8  mov     edx, 80000h
0x180009fed  mov     rcx, r14
0x180009ff0  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x180009ff7  nop     dword ptr [rax+rax+00h]
0x180009ffc  jmp     loc_18000A2ED
0x18000a001  lea     rcx, [rsp+330h+VersionInformation]; lpVersionInformation
0x18000a006  mov     [rsp+330h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x18000a00e  call    cs:__imp_RtlGetVersion
0x18000a015  nop     dword ptr [rax+rax+00h]
0x18000a01a  test    eax, eax
0x18000a01c  js      short loc_18000A060
0x18000a01e  movzx   eax, [rbp+230h+var_1CA]
0x18000a022  lea     r8, aRunningOnOsVer; "Running on OS version %u.%u build %u sp"...
0x18000a029  movzx   ecx, [rbp+230h+var_1CC]
0x18000a02d  mov     edx, 20000h
0x18000a032  mov     r9d, [rsp+330h+VersionInformation.dwMajorVersion]
0x18000a037  mov     [rsp+330h+var_2F8], eax
0x18000a03b  mov     eax, [rsp+330h+VersionInformation.dwBuildNumber]
0x18000a03f  mov     [rsp+330h+var_300], ecx
0x18000a043  mov     rcx, r14
0x18000a046  mov     [rsp+330h+var_308], eax
0x18000a04a  mov     eax, [rsp+330h+VersionInformation.dwMinorVersion]
0x18000a04e  mov     [rsp+330h+var_310], eax
0x18000a052  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18000a059  nop     dword ptr [rax+rax+00h]
0x18000a05e  jmp     short loc_18000A08C
0x18000a060  mov     ecx, eax; Status
0x18000a062  call    cs:__imp_RtlNtStatusToDosError
0x18000a069  nop     dword ptr [rax+rax+00h]
0x18000a06e  lea     r8, aFailedToQueryO; "Failed to query OS version information,"...
0x18000a075  mov     edx, 40000h
0x18000a07a  mov     r9d, eax
0x18000a07d  mov     rcx, r14
0x18000a080  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18000a087  nop     dword ptr [rax+rax+00h]
0x18000a08c  mov     rcx, rdi; this
0x18000a08f  call    ?UpdateProgress@CWdsService@@QEAAKXZ; CWdsService::UpdateProgress(void)
0x18000a094  mov     r8d, 100h
0x18000a09a  lea     rdx, aWdsserver; "WDSServer"
0x18000a0a1  lea     rcx, qword_180039300
0x18000a0a8  call    cs:__imp_?Initialize@CEventLog@@QEAAKPEBGG@Z; CEventLog::Initialize(ushort const *,ushort)
0x18000a0af  nop     dword ptr [rax+rax+00h]
0x18000a0b4  mov     ecx, eax
0x18000a0b6  mov     r9d, 0F9h
0x18000a0bc  mov     ebx, eax
0x18000a0be  call    ElValidateWin32_0
0x18000a0c3  test    eax, eax
0x18000a0c5  jnz     loc_18000A2ED
0x18000a0cb  mov     rcx, rdi; this
0x18000a0ce  call    ?UpdateProgress@CWdsService@@QEAAKXZ; CWdsService::UpdateProgress(void)
0x18000a0d3  call    cs:__imp_?WdsDiagInitialize@@YAKXZ; WdsDiagInitialize(void)
0x18000a0da  nop     dword ptr [rax+rax+00h]
0x18000a0df  mov     ecx, eax
0x18000a0e1  mov     r9d, 102h
0x18000a0e7  mov     ebx, eax
0x18000a0e9  call    ElValidateWin32_0
0x18000a0ee  test    eax, eax
0x18000a0f0  jnz     loc_18000A2ED
0x18000a0f6  mov     rcx, rdi; this
0x18000a0f9  call    ?UpdateProgress@CWdsService@@QEAAKXZ; CWdsService::UpdateProgress(void)
0x18000a0fe  mov     r9d, 28h ; '('
0x18000a104  lea     r8, qword_1800219E8
0x18000a10b  lea     rdx, qword_1800219F8
0x18000a112  lea     rcx, ?g_PerfCounters@@3VCWdsPerfCounters@@A; CWdsPerfCounters g_PerfCounters
0x18000a119  call    cs:__imp_?InitializeServer@CPerfCounters@@QEAAKAEBU_GUID@@0K@Z; CPerfCounters::InitializeServer(_GUID const &,_GUID const &,ulong)
0x18000a120  nop     dword ptr [rax+rax+00h]
0x18000a125  mov     ecx, eax
0x18000a127  mov     r9d, 10Bh
0x18000a12d  mov     ebx, eax
0x18000a12f  call    ElValidateWin32_0
0x18000a134  test    eax, eax
0x18000a136  jnz     loc_18000A2ED
0x18000a13c  mov     rcx, rdi; this
0x18000a13f  call    ?UpdateProgress@CWdsService@@QEAAKXZ; CWdsService::UpdateProgress(void)
0x18000a144  lea     rcx, [rdi+10660h]; this
0x18000a14b  call    ?Initialize@CWorkItemHandler@@QEAAKXZ; CWorkItemHandler::Initialize(void)
0x18000a150  mov     r9d, 114h
0x18000a156  mov     ecx, eax
0x18000a158  mov     ebx, eax
0x18000a15a  call    ElValidateWin32_0
0x18000a15f  test    eax, eax
0x18000a161  jnz     loc_18000A2ED
0x18000a167  mov     rcx, rdi; this
0x18000a16a  call    ?UpdateProgress@CWdsService@@QEAAKXZ; CWdsService::UpdateProgress(void)
0x18000a16f  lea     rcx, [rdi+30h]; this
0x18000a173  call    ?Initialize@CInterfaceHandler@@QEAAKXZ; CInterfaceHandler::Initialize(void)
0x18000a178  mov     r9d, 11Dh
0x18000a17e  mov     ecx, eax
0x18000a180  mov     ebx, eax
0x18000a182  call    ElValidateWin32_0
0x18000a187  test    eax, eax
0x18000a189  jnz     loc_18000A2ED
0x18000a18f  mov     rcx, rdi; this
0x18000a192  call    ?UpdateProgress@CWdsService@@QEAAKXZ; CWdsService::UpdateProgress(void)
0x18000a197  call    ?WdsVssWriterPreinitialize@@YAKXZ; WdsVssWriterPreinitialize(void)
0x18000a19c  mov     r9d, 127h
0x18000a1a2  mov     ecx, eax
0x18000a1a4  mov     ebx, eax
0x18000a1a6  call    ElValidateWin32_0
0x18000a1ab  test    eax, eax
0x18000a1ad  jnz     loc_18000A2ED
0x18000a1b3  mov     rcx, rdi; this
0x18000a1b6  call    ?UpdateProgress@CWdsService@@QEAAKXZ; CWdsService::UpdateProgress(void)
0x18000a1bb  lea     r14, [rdi+106F8h]
0x18000a1c2  mov     rcx, r14; lpCriticalSection
0x18000a1c5  call    cs:__imp_EnterCriticalSection
0x18000a1cc  nop     dword ptr [rax+rax+00h]
0x18000a1d1  mov     rcx, rdi; this
0x18000a1d4  call    ?ReadServerDuid@CWdsService@@AEAAKXZ; CWdsService::ReadServerDuid(void)
0x18000a1d9  mov     ebx, eax
0x18000a1db  test    eax, eax
0x18000a1dd  jz      short loc_18000A211
0x18000a1df  cmp     ebx, 2
0x18000a1e2  mov     eax, esi
0x18000a1e4  mov     r9d, 5A7h
0x18000a1ea  cmovnz  eax, ebx
0x18000a1ed  mov     ecx, eax
0x18000a1ef  mov     ebx, eax
0x18000a1f1  call    ElValidateWin32_0
0x18000a1f6  test    eax, eax
0x18000a1f8  jnz     short loc_18000A211
0x18000a1fa  mov     rcx, rdi; this
0x18000a1fd  call    ?RegenerateServerDuid@CWdsService@@AEAAKXZ; CWdsService::RegenerateServerDuid(void)
0x18000a202  mov     r9d, 5AAh
0x18000a208  mov     ecx, eax
0x18000a20a  mov     ebx, eax
0x18000a20c  call    ElValidateWin32_0
0x18000a211  mov     rcx, r14; lpCriticalSection
0x18000a214  call    cs:__imp_LeaveCriticalSection
0x18000a21b  nop     dword ptr [rax+rax+00h]
0x18000a220  mov     r9d, 130h
0x18000a226  mov     ecx, ebx
0x18000a228  call    ElValidateWin32_0
0x18000a22d  test    eax, eax
0x18000a22f  jnz     loc_18000A2ED
0x18000a235  lea     rcx, [rdi+105F0h]; this
0x18000a23c  call    ?Initialize@CWdsProvidersHandler@@QEAAKXZ; CWdsProvidersHandler::Initialize(void)
0x18000a241  mov     r9d, 136h
0x18000a247  mov     ecx, eax
0x18000a249  mov     ebx, eax
0x18000a24b  call    ElValidateWin32_0
0x18000a250  test    eax, eax
0x18000a252  jnz     loc_18000A2ED
0x18000a258  mov     rcx, rdi; this
0x18000a25b  call    ?UpdateProgress@CWdsService@@QEAAKXZ; CWdsService::UpdateProgress(void)
0x18000a260  call    ?WdsVssWriterInitialize@@YAKXZ; WdsVssWriterInitialize(void)
0x18000a265  mov     r9d, 13Eh
0x18000a26b  mov     ecx, eax
0x18000a26d  mov     ebx, eax
0x18000a26f  call    ElValidateWin32_0
0x18000a274  test    eax, eax
0x18000a276  jnz     short loc_18000A2ED
0x18000a278  mov     rcx, rdi; this
0x18000a27b  call    ?UpdateProgress@CWdsService@@QEAAKXZ; CWdsService::UpdateProgress(void)
0x18000a280  lea     rcx, [rdi+106C0h]; Parameter
0x18000a287  mov     rdx, rdi
0x18000a28a  call    ?Initialize@?$CTimer@VCWdsService@@@@QEAAKPEAVCWdsService@@PEAXKK1K@Z; CTimer<CWdsService>::Initialize(CWdsService *,void *,ulong,ulong,void *,ulong)
0x18000a28f  mov     r9d, 146h
0x18000a295  mov     ecx, eax
0x18000a297  mov     ebx, eax
0x18000a299  call    ElValidateWin32_0
0x18000a29e  test    eax, eax
0x18000a2a0  jnz     short loc_18000A2ED
0x18000a2a2  mov     rcx, rdi; this
0x18000a2a5  call    ?UpdateProgress@CWdsService@@QEAAKXZ; CWdsService::UpdateProgress(void)
0x18000a2aa  mov     rcx, rdi; this
0x18000a2ad  call    ?UpdateSettings@CWdsService@@AEAAKXZ; CWdsService::UpdateSettings(void)
0x18000a2b2  mov     r9d, 14Eh
  ... truncated ...
```
