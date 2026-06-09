# CUMRDPService::Start(void)

- ea: `0x18000e8f0`
- end: `0x18000ee49`
- name: `?Start@CUMRDPService@@QEAAXXZ`
- size: `1369`
- prototype: `void __fastcall(CUMRDPService *__hidden this)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, loader_planting, service_task, installer_update`

## callers

- `0x18000e830`

## callees

- `0x180002920`
- `0x18000b8f8`
- `0x18000bd04`
- `0x18000bd44`
- `0x18000e140`
- `0x18000e8f0`
- `0x18000ee50`
- `0x18000efdc`
- `0x18000f75c`
- `0x18000f79c`
- `0x180019594`
- `0x180019edc`
- `0x18001bb30`
- `0x180027720`
- `0x18002db68`
- `0x18002e42c`
- `0x1800313a8`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ea3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eb71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ec81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ea3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eb71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ec81`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000ea84`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000ea84`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000ee3e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000ee3e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000e942`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000eaa9`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000eac3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000e942`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000eaa9`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000eac3`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000eb3b`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000ec53`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000eb3b`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000ec53`
- `ntdll!EtwEventRegister` at `0x18000e927`
- `ntdll!EtwEventRegister` at `0x18000e997`
- `ntdll!EtwEventRegister` at `0x18000e927`
- `ntdll!EtwEventRegister` at `0x18000e997`
- `ntdll!EtwEventUnregister` at `0x18000e964`
- `ntdll!EtwEventUnregister` at `0x18000e964`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18000ea30`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18000ea30`

## string_xrefs

- `0x18000ea29`: `UmrdpService`
- `0x18000edf3`: `UmrdpService`
- `0x18000ed6c`: `TerminalServices-DeviceRedirection-Licenses-PnpRedirectionAllowed`
- `0x18000edb4`: `TerminalServices-DeviceRedirection-Licenses-CameraRedirectionAllowed`

## pseudocode

```c
void __fastcall CUMRDPService::Start(CUMRDPService *this)
{
  CUMRDPService *v1; // rdi
  HANDLE EventW; // rax
  SERVICE_STATUS_HANDLE v3; // rax
  unsigned int v4; // r8d
  HANDLE v5; // rax
  HANDLE v6; // rax
  HINSTANCE v7; // rcx
  HANDLE Thread; // rax
  DWORD LastError; // ebx
  unsigned int v10; // eax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v12; // eax
  DWORD v13; // ebx
  _QWORD *v14; // r14
  DWORD v15; // ebx
  unsigned int v16; // eax
  unsigned int v17; // eax
  __int64 v18; // rdx
  unsigned int v19; // eax
  struct IServiceExtensionHelper *v20; // rdx
  HINSTANCE v21; // rcx
  CUMRDPService *v22; // rcx
  unsigned int v23; // r8d
  unsigned int dwCreationFlags; // [rsp+20h] [rbp-38h]
  CUMRDPService *ThreadId; // [rsp+60h] [rbp+8h] BYREF

  v1 = g_pService;
  ThreadId = g_pService;
  EtwEventRegister(S_umrdpService, 0, 0, &qword_18005DE60);
  *((_DWORD *)v1 + 13) = 1;
  EventW = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)v1 + 34) = EventW;
  if ( !EventW )
    goto LABEL_8;
  if ( qword_18005DCA0 )
  {
    EtwEventUnregister();
    qword_18005DCA0 = 0;
  }
  CrimsonHelper::s_instance = PnP_Redirector_Event_Provider;
  if ( !(unsigned int)EtwEventRegister(&CrimsonHelper::s_instance, 0, 0, &qword_18005DCA0) )
    byte_18005DCA8 = 1;
  qword_18005DC60 = (__int64)TRACE_INF;
  qword_18005DC68 = (__int64)TRACE_WRN;
  qword_18005DC70 = (__int64)TRACE_ERR;
  qword_18005DC78 = (__int64)TRACE_FATAL;
  qword_18005DC80 = (__int64)TRACE_ALV;
  qword_18005DC88 = (__int64)TRACE_ENT;
  qword_18005DC90 = (__int64)TRACE_EXIT;
  qword_18005DC98 = (__int64)TRACE_DUMP;
  byte_18005DCA9 = 1;
  v3 = RegisterServiceCtrlHandlerExW(L"UmrdpService", CUMRDPService::staticHandler, v1);
  *((_QWORD *)v1 + 2) = v3;
  if ( !v3 )
  {
    GetLastError();
LABEL_8:
    CUMRDPService::Stop(v1);
    return;
  }
  CUMRDPService::UpdateStatus(v1, 2u, v4, 0x3A8u, dwCreationFlags);
  if ( !*((_DWORD *)v1 + 66) )
  {
    InitializeCriticalSection((LPCRITICAL_SECTION)((char *)v1 + 224));
    *((_DWORD *)v1 + 66) = 1;
  }
  v5 = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)v1 + 11) = v5;
  if ( !v5 )
    goto LABEL_8;
  v6 = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)v1 + 38) = v6;
  if ( !v6
    || !(unsigned int)TSNUTL_LoadTsNotifyResources(v7)
    || (int)CListTree<CUMRDPService::CSessionListHelper>::FinalConstruct((char *)v1 + 104) < 0
    || (int)CDrNotify::CreateInstance((struct CDrNotify **)v1 + 9) < 0 )
  {
    goto LABEL_8;
  }
  if ( *((_QWORD *)v1 + 12) )
  {
    if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
      && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_D(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL), 17, "\r7\n", CurrentThreadActivityIdPrefix);
    }
  }
  else
  {
    LODWORD(ThreadId) = 0;
    Thread = CreateThread(0, 0, CUMRDPService::staticCleanupTSPrintersThreadProc, 0, 0, (LPDWORD)&ThreadId);
    *((_QWORD *)v1 + 12) = Thread;
    if ( !Thread
      && *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
      && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
    {
      LastError = GetLastError();
      v10 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL), 16, "\r7\n", v10, LastError);
    }
  }
  v12 = IsRemoveTSUSBPhantomDevnodesEnabled();
  *((_DWORD *)v1 + 74) = v12;
  if ( !v12 )
  {
    if ( *(unsigned int **)&WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) == 0
      || *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) < 2u )
    {
      goto LABEL_49;
    }
    v17 = RdpWppGetCurrentThreadActivityIdPrefix();
    v18 = 21;
    goto LABEL_48;
  }
  v13 = g_lSessionDisconnectTSUSBDevnodesCleanupThreadCount;
  if ( !g_lSessionDisconnectTSUSBDevnodesCleanupThreadCount )
  {
    if ( !g_hServiceStartupTSUSBDevnodesCleanupThread )
    {
      LODWORD(ThreadId) = g_lSessionDisconnectTSUSBDevnodesCleanupThreadCount;
      v14 = operator new(g_lSessionDisconnectTSUSBDevnodesCleanupThreadCount + 8);
      *v14 = *((_QWORD *)v1 + 38);
      g_hServiceStartupTSUSBDevnodesCleanupThread = CreateThread(
                                                      0,
                                                      0,
                                                      CUMRDPService::staticServiceStartupTSUSBDevnodesCleanupThreadProc,
                                                      v14,
                                                      v13,
                                                      (LPDWORD)&ThreadId);
      if ( !g_hServiceStartupTSUSBDevnodesCleanupThread )
      {
        if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
          && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
        {
          v15 = GetLastError();
          v16 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_Dd(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL), 18, "\r7\n", v16, v15);
        }
        operator delete(v14);
      }
      goto LABEL_49;
    }
    if ( *(unsigned int **)&WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) == 0
      || *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) < 2u )
    {
      goto LABEL_49;
    }
    v17 = RdpWppGetCurrentThreadActivityIdPrefix();
    v18 = 19;
LABEL_48:
    WPP_SF_D(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL), v18, "\r7\n", v17);
    goto LABEL_49;
  }
  if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
    && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
  {
    v19 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Dd(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL), 20, "\r7\n", v19, v13);
  }
LABEL_49:
  if ( (unsigned int)IsAdvancedDeviceRedirectionEnabled(L"TerminalServices-DeviceRedirection-Licenses-PnpRedirectionAllowed") )
  {
    if ( (unsigned int)CreateRdrPnpManager((struct IRdrPnpManager **)v1 + 8)
      || (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)v1 + 8) + 24LL))(*((_QWORD *)v1 + 8)) )
    {
      goto LABEL_8;
    }
    CreateUsbServiceExtension(v1, (struct IServiceExtension **)v1 + 36);
  }
  if ( (unsigned int)IsAdvancedDeviceRedirectionEnabled(L"TerminalServices-DeviceRedirection-Licenses-CameraRedirectionAllowed") )
    CreateRDCameraServiceExtension(v21, v20, (struct IServiceExtension **)v1 + 39);
  if ( (*((unsigned int (__fastcall **)(__int64, const WCHAR *, _QWORD, void (__fastcall *)(void *, unsigned __int8)))g_svcsGlobals
        + 24))(
         (__int64)v1 + 80,
         L"UmrdpService",
         *((_QWORD *)v1 + 11),
         CUMRDPService::staticStopServiceCallback)
    || (unsigned int)CUMRDPService::StartPrnDrvRpcServer(v22) )
  {
    goto LABEL_8;
  }
  *((_DWORD *)v1 + 14) = 1;
  CUMRDPService::UpdateStatus(v1, 4u, v23, 0, (unsigned int)v1);
  *((_DWORD *)v1 + 70) = 0;
  SetEvent(*((HANDLE *)v1 + 34));
}

```

## disassembly

```asm
0x18000e8f0  mov     [rsp+arg_8], rbx
0x18000e8f5  mov     [rsp+arg_10], rsi
0x18000e8fa  mov     [rsp+ThreadId], rcx
0x18000e8ff  push    rdi
0x18000e900  push    r12
0x18000e902  push    r14
0x18000e904  sub     rsp, 40h
0x18000e908  mov     rdi, cs:?g_pService@@3PEAVCUMRDPService@@EA; CUMRDPService * g_pService
0x18000e90f  mov     [rsp+58h+ThreadId], rdi
0x18000e914  lea     r9, qword_18005DE60
0x18000e91b  xor     r8d, r8d
0x18000e91e  xor     edx, edx
0x18000e920  lea     rcx, S_umrdpService
0x18000e927  call    cs:__imp_EtwEventRegister
0x18000e92d  mov     r12d, 1
0x18000e933  mov     [rdi+34h], r12d
0x18000e937  xor     r9d, r9d; lpName
0x18000e93a  xor     r8d, r8d; bInitialState
0x18000e93d  mov     edx, r12d; bManualReset
0x18000e940  xor     ecx, ecx; lpEventAttributes
0x18000e942  call    cs:__imp_CreateEventW
0x18000e948  mov     [rdi+110h], rax
0x18000e94f  test    rax, rax
0x18000e952  jz      loc_18000EA45
0x18000e958  mov     rcx, cs:qword_18005DCA0
0x18000e95f  test    rcx, rcx
0x18000e962  jz      short loc_18000E975
0x18000e964  call    cs:__imp_EtwEventUnregister
0x18000e96a  mov     cs:qword_18005DCA0, 0
0x18000e975  movups  xmm0, cs:PnP_Redirector_Event_Provider
0x18000e97c  movdqu  cs:?s_instance@CrimsonHelper@@0V1@A, xmm0; CrimsonHelper CrimsonHelper::s_instance
0x18000e984  lea     r9, qword_18005DCA0
0x18000e98b  xor     r8d, r8d
0x18000e98e  xor     edx, edx
0x18000e990  lea     rcx, ?s_instance@CrimsonHelper@@0V1@A; CrimsonHelper CrimsonHelper::s_instance
0x18000e997  call    cs:__imp_EtwEventRegister
0x18000e99d  test    eax, eax
0x18000e99f  jnz     short loc_18000E9A8
0x18000e9a1  mov     cs:byte_18005DCA8, r12b
0x18000e9a8  lea     rax, TRACE_INF
0x18000e9af  mov     cs:qword_18005DC60, rax
0x18000e9b6  lea     rax, TRACE_WRN
0x18000e9bd  mov     cs:qword_18005DC68, rax
0x18000e9c4  lea     rax, TRACE_ERR
0x18000e9cb  mov     cs:qword_18005DC70, rax
0x18000e9d2  lea     rax, TRACE_FATAL
0x18000e9d9  mov     cs:qword_18005DC78, rax
0x18000e9e0  lea     rax, TRACE_ALV
0x18000e9e7  mov     cs:qword_18005DC80, rax
0x18000e9ee  lea     rax, TRACE_ENT
0x18000e9f5  mov     cs:qword_18005DC88, rax
0x18000e9fc  lea     rax, TRACE_EXIT
0x18000ea03  mov     cs:qword_18005DC90, rax
0x18000ea0a  lea     rax, TRACE_DUMP
0x18000ea11  mov     cs:qword_18005DC98, rax
0x18000ea18  mov     cs:byte_18005DCA9, r12b
0x18000ea1f  mov     r8, rdi; lpContext
0x18000ea22  lea     rdx, ?staticHandler@CUMRDPService@@CAKKKPEAX0@Z; lpHandlerProc
0x18000ea29  lea     rcx, ServiceName; "UmrdpService"
0x18000ea30  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x18000ea36  mov     [rdi+10h], rax
0x18000ea3a  test    rax, rax
0x18000ea3d  jnz     short loc_18000EA61
0x18000ea3f  call    cs:__imp_GetLastError
0x18000ea45  mov     rcx, rdi; this
0x18000ea48  call    ?Stop@CUMRDPService@@QEAAXXZ; CUMRDPService::Stop(void)
0x18000ea4d  mov     rbx, [rsp+58h+arg_8]
0x18000ea52  mov     rsi, [rsp+58h+arg_10]
0x18000ea57  add     rsp, 40h
0x18000ea5b  pop     r14
0x18000ea5d  pop     r12
0x18000ea5f  pop     rdi
0x18000ea60  retn
0x18000ea61  mov     edx, 2; unsigned int
0x18000ea66  mov     r9d, 3A8h; unsigned int
0x18000ea6c  mov     rcx, rdi; this
0x18000ea6f  call    ?UpdateStatus@CUMRDPService@@AEAAHKKKK@Z; CUMRDPService::UpdateStatus(ulong,ulong,ulong,ulong)
0x18000ea74  cmp     dword ptr [rdi+108h], 0
0x18000ea7b  jnz     short loc_18000EA9F
0x18000ea7d  lea     rcx, [rdi+0E0h]; lpCriticalSection
0x18000ea84  call    cs:__imp_InitializeCriticalSection
0x18000ea8a  mov     [rdi+108h], r12d
0x18000ea91  jmp     short loc_18000EA9F
0x18000ea93  mov     rcx, [rsp+58h+ThreadId]; this
0x18000ea98  call    ?Stop@CUMRDPService@@QEAAXXZ; CUMRDPService::Stop(void)
0x18000ea9d  jmp     short loc_18000EA4D
0x18000ea9f  xor     r9d, r9d; lpName
0x18000eaa2  xor     r8d, r8d; bInitialState
0x18000eaa5  xor     edx, edx; bManualReset
0x18000eaa7  xor     ecx, ecx; lpEventAttributes
0x18000eaa9  call    cs:__imp_CreateEventW
0x18000eaaf  mov     [rdi+58h], rax
0x18000eab3  test    rax, rax
0x18000eab6  jz      short loc_18000EA45
0x18000eab8  xor     r9d, r9d; lpName
0x18000eabb  xor     r8d, r8d; bInitialState
0x18000eabe  mov     edx, r12d; bManualReset
0x18000eac1  xor     ecx, ecx; lpEventAttributes
0x18000eac3  call    cs:__imp_CreateEventW
0x18000eac9  mov     [rdi+130h], rax
0x18000ead0  test    rax, rax
0x18000ead3  jz      loc_18000EA45
0x18000ead9  call    ?TSNUTL_LoadTsNotifyResources@@YAHPEAUHINSTANCE__@@@Z; TSNUTL_LoadTsNotifyResources(HINSTANCE__ *)
0x18000eade  test    eax, eax
0x18000eae0  jz      loc_18000EA45
0x18000eae6  lea     rcx, [rdi+68h]; TableContext
0x18000eaea  call    ?FinalConstruct@?$CListTree@VCSessionListHelper@CUMRDPService@@@@QEAAJXZ; CListTree<CUMRDPService::CSessionListHelper>::FinalConstruct(void)
0x18000eaef  test    eax, eax
0x18000eaf1  js      loc_18000EA45
0x18000eaf7  lea     rcx, [rdi+48h]; struct CDrNotify **
0x18000eafb  call    ?CreateInstance@CDrNotify@@SAJPEAPEAV1@@Z; CDrNotify::CreateInstance(CDrNotify * *)
0x18000eb00  test    eax, eax
0x18000eb02  js      loc_18000EA45
0x18000eb08  cmp     qword ptr [rdi+60h], 0
0x18000eb0d  jnz     loc_18000EBAC
0x18000eb13  mov     dword ptr [rsp+58h+ThreadId], 0
0x18000eb1b  lea     rax, [rsp+58h+ThreadId]
0x18000eb20  mov     [rsp+58h+lpThreadId], rax; lpThreadId
0x18000eb25  mov     [rsp+58h+dwCreationFlags], 0; dwCreationFlags
0x18000eb2d  xor     r9d, r9d; lpParameter
0x18000eb30  lea     r8, ?staticCleanupTSPrintersThreadProc@CUMRDPService@@CAKPEAX@Z; lpStartAddress
0x18000eb37  xor     edx, edx; dwStackSize
0x18000eb39  xor     ecx, ecx; lpThreadAttributes
0x18000eb3b  call    cs:__imp_CreateThread
0x18000eb41  mov     [rdi+60h], rax
0x18000eb45  test    rax, rax
0x18000eb48  jnz     short loc_18000EBA3
0x18000eb4a  lea     rsi, WPP_GLOBAL_Control
0x18000eb51  mov     rax, cs:WPP_GLOBAL_Control
0x18000eb58  cmp     rax, rsi
0x18000eb5b  jz      loc_18000EBEF
0x18000eb61  test    [rax+1Ch], r12b
0x18000eb65  jz      loc_18000EBEF
0x18000eb6b  cmp     byte ptr [rax+19h], 2
0x18000eb6f  jb      short loc_18000EBEF
0x18000eb71  call    cs:__imp_GetLastError
0x18000eb77  mov     ebx, eax
0x18000eb79  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18000eb7e  mov     edx, 10h
0x18000eb83  mov     [rsp+58h+dwCreationFlags], ebx
0x18000eb87  mov     r9d, eax
0x18000eb8a  lea     r8, WPP_000a370d3c4f3de49ddf5e962b0a3f31_Traceguids; "\r7\n"
0x18000eb91  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eb98  mov     rcx, [rcx+10h]
0x18000eb9c  call    WPP_SF_Dd
0x18000eba1  jmp     short loc_18000EBEF
0x18000eba3  lea     rsi, WPP_GLOBAL_Control
0x18000ebaa  jmp     short loc_18000EBEF
0x18000ebac  lea     rsi, WPP_GLOBAL_Control
0x18000ebb3  mov     rax, cs:WPP_GLOBAL_Control
0x18000ebba  cmp     rax, rsi
0x18000ebbd  jz      short loc_18000EBEF
0x18000ebbf  test    [rax+1Ch], r12b
0x18000ebc3  jz      short loc_18000EBEF
0x18000ebc5  cmp     byte ptr [rax+19h], 2
0x18000ebc9  jb      short loc_18000EBEF
0x18000ebcb  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18000ebd0  mov     edx, 11h
0x18000ebd5  mov     r9d, eax
0x18000ebd8  lea     r8, WPP_000a370d3c4f3de49ddf5e962b0a3f31_Traceguids; "\r7\n"
0x18000ebdf  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ebe6  mov     rcx, [rcx+10h]
0x18000ebea  call    WPP_SF_D
0x18000ebef  call    ?IsRemoveTSUSBPhantomDevnodesEnabled@@YAHXZ; IsRemoveTSUSBPhantomDevnodesEnabled(void)
0x18000ebf4  mov     [rdi+128h], eax
0x18000ebfa  test    eax, eax
0x18000ebfc  jz      loc_18000ED30
0x18000ec02  mov     ebx, cs:?g_lSessionDisconnectTSUSBDevnodesCleanupThreadCount@@3JA; long g_lSessionDisconnectTSUSBDevnodesCleanupThreadCount
0x18000ec08  test    ebx, ebx
0x18000ec0a  jnz     loc_18000ECEE
0x18000ec10  cmp     cs:?g_hServiceStartupTSUSBDevnodesCleanupThread@@3PEAXEA, 0; void * g_hServiceStartupTSUSBDevnodesCleanupThread
0x18000ec18  jnz     loc_18000ECBE
0x18000ec1e  mov     dword ptr [rsp+58h+ThreadId], ebx
0x18000ec22  lea     ecx, [rbx+8]; Size
0x18000ec25  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000ec2a  mov     r14, rax
0x18000ec2d  mov     rcx, [rdi+130h]
0x18000ec34  mov     [rax], rcx
0x18000ec37  lea     rax, [rsp+58h+ThreadId]
0x18000ec3c  mov     [rsp+58h+lpThreadId], rax; lpThreadId
0x18000ec41  mov     [rsp+58h+dwCreationFlags], ebx; dwCreationFlags
0x18000ec45  mov     r9, r14; lpParameter
0x18000ec48  lea     r8, ?staticServiceStartupTSUSBDevnodesCleanupThreadProc@CUMRDPService@@CAKPEAX@Z; lpStartAddress
0x18000ec4f  xor     edx, edx; dwStackSize
0x18000ec51  xor     ecx, ecx; lpThreadAttributes
0x18000ec53  call    cs:__imp_CreateThread
0x18000ec59  mov     cs:?g_hServiceStartupTSUSBDevnodesCleanupThread@@3PEAXEA, rax; void * g_hServiceStartupTSUSBDevnodesCleanupThread
0x18000ec60  test    rax, rax
0x18000ec63  jnz     loc_18000ED6C
0x18000ec69  mov     rax, cs:WPP_GLOBAL_Control
0x18000ec70  cmp     rax, rsi
0x18000ec73  jz      short loc_18000ECB1
0x18000ec75  test    [rax+1Ch], r12b
0x18000ec79  jz      short loc_18000ECB1
0x18000ec7b  cmp     byte ptr [rax+19h], 2
0x18000ec7f  jb      short loc_18000ECB1
0x18000ec81  call    cs:__imp_GetLastError
0x18000ec87  mov     ebx, eax
0x18000ec89  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18000ec8e  mov     edx, 12h
0x18000ec93  mov     [rsp+58h+dwCreationFlags], ebx
0x18000ec97  mov     r9d, eax
0x18000ec9a  lea     r8, WPP_000a370d3c4f3de49ddf5e962b0a3f31_Traceguids; "\r7\n"
0x18000eca1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eca8  mov     rcx, [rcx+10h]
0x18000ecac  call    WPP_SF_Dd
0x18000ecb1  mov     rcx, r14; Block
0x18000ecb4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000ecb9  jmp     loc_18000ED6C
0x18000ecbe  mov     rax, cs:WPP_GLOBAL_Control
0x18000ecc5  cmp     rax, rsi
0x18000ecc8  jz      loc_18000ED6C
0x18000ecce  test    [rax+1Ch], r12b
0x18000ecd2  jz      loc_18000ED6C
0x18000ecd8  cmp     byte ptr [rax+19h], 2
0x18000ecdc  jb      loc_18000ED6C
0x18000ece2  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18000ece7  mov     edx, 13h
0x18000ecec  jmp     short loc_18000ED52
0x18000ecee  mov     rax, cs:WPP_GLOBAL_Control
0x18000ecf5  cmp     rax, rsi
0x18000ecf8  jz      short loc_18000ED6C
0x18000ecfa  test    [rax+1Ch], r12b
0x18000ecfe  jz      short loc_18000ED6C
0x18000ed00  cmp     byte ptr [rax+19h], 2
0x18000ed04  jb      short loc_18000ED6C
0x18000ed06  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18000ed0b  mov     edx, 14h
0x18000ed10  mov     [rsp+58h+dwCreationFlags], ebx
0x18000ed14  mov     r9d, eax
0x18000ed17  lea     r8, WPP_000a370d3c4f3de49ddf5e962b0a3f31_Traceguids; "\r7\n"
0x18000ed1e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ed25  mov     rcx, [rcx+10h]
0x18000ed29  call    WPP_SF_Dd
0x18000ed2e  jmp     short loc_18000ED6C
0x18000ed30  mov     rax, cs:WPP_GLOBAL_Control
0x18000ed37  cmp     rax, rsi
0x18000ed3a  jz      short loc_18000ED6C
0x18000ed3c  test    [rax+1Ch], r12b
0x18000ed40  jz      short loc_18000ED6C
0x18000ed42  cmp     byte ptr [rax+19h], 2
0x18000ed46  jb      short loc_18000ED6C
0x18000ed48  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18000ed4d  mov     edx, 15h
0x18000ed52  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ed59  mov     r9d, eax
0x18000ed5c  lea     r8, WPP_000a370d3c4f3de49ddf5e962b0a3f31_Traceguids; "\r7\n"
0x18000ed63  mov     rcx, [rcx+10h]
0x18000ed67  call    WPP_SF_D
0x18000ed6c  lea     rcx, aTerminalservic_0; "TerminalServices-DeviceRedirection-Lice"...
0x18000ed73  call    ?IsAdvancedDeviceRedirectionEnabled@@YAHPEBG@Z; IsAdvancedDeviceRedirectionEnabled(ushort const *)
0x18000ed78  test    eax, eax
0x18000ed7a  jz      short loc_18000EDB4
0x18000ed7c  lea     rcx, [rdi+40h]; struct IRdrPnpManager **
0x18000ed80  call    ?CreateRdrPnpManager@@YAJPEAPEAVIRdrPnpManager@@@Z; CreateRdrPnpManager(IRdrPnpManager * *)
0x18000ed85  test    eax, eax
0x18000ed87  jnz     loc_18000EA45
0x18000ed8d  mov     rcx, [rdi+40h]
0x18000ed91  mov     rax, [rcx]
0x18000ed94  mov     rax, [rax+18h]
0x18000ed98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ed9d  test    eax, eax
0x18000ed9f  jnz     loc_18000EA45
0x18000eda5  lea     rdx, [rdi+120h]; struct IServiceExtension **
0x18000edac  mov     rcx, rdi; struct IServiceExtensionHelper *
0x18000edaf  call    ?CreateUsbServiceExtension@@YAJPEAUIServiceExtensionHelper@@PEAPEAUIServiceExtension@@@Z; CreateUsbServiceExtension(IServiceExtensionHelper *,IServiceExtension * *)
0x18000edb4  lea     rcx, aTerminalservic; "TerminalServices-DeviceRedirection-Lice"...
0x18000edbb  call    ?IsAdvancedDeviceRedirectionEnabled@@YAHPEBG@Z; IsAdvancedDeviceRedirectionEnabled(ushort const *)
0x18000edc0  test    eax, eax
0x18000edc2  jz      short loc_18000EDD0
0x18000edc4  lea     r8, [rdi+138h]; struct IServiceExtension **
0x18000edcb  call    ?CreateRDCameraServiceExtension@@YAJPEAUHINSTANCE__@@PEAUIServiceExtensionHelper@@PEAPEAUIServiceExtension@@@Z; CreateRDCameraServiceExtension(HINSTANCE__ *,IServiceExtensionHelper *,IServiceExtension * *)
0x18000edd0  lea     rcx, [rdi+50h]
0x18000edd4  mov     rax, cs:?g_svcsGlobals@@3PEAU_SVCHOST_GLOBAL_DATA@@EA; _SVCHOST_GLOBAL_DATA * g_svcsGlobals
0x18000eddb  mov     dword ptr [rsp+58h+lpThreadId], 8
0x18000ede3  mov     qword ptr [rsp+58h+dwCreationFlags], rdi; unsigned int
0x18000ede8  lea     r9, ?staticStopServiceCallback@CUMRDPService@@CAXPEAXE@Z; CUMRDPService::staticStopServiceCallback(void *,uchar)
0x18000edef  mov     r8, [rdi+58h]
0x18000edf3  lea     rdx, ServiceName; "UmrdpService"
0x18000edfa  mov     rax, [rax+0C0h]
0x18000ee01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ee06  test    eax, eax
0x18000ee08  jnz     loc_18000EA45
0x18000ee0e  call    ?StartPrnDrvRpcServer@CUMRDPService@@AEAAJXZ; CUMRDPService::StartPrnDrvRpcServer(void)
0x18000ee13  test    eax, eax
0x18000ee15  jnz     loc_18000EA45
0x18000ee1b  mov     [rdi+38h], r12d
0x18000ee1f  xor     r9d, r9d; unsigned int
0x18000ee22  lea     edx, [rax+4]; unsigned int
0x18000ee25  mov     rcx, rdi; this
0x18000ee28  call    ?UpdateStatus@CUMRDPService@@AEAAHKKKK@Z; CUMRDPService::UpdateStatus(ulong,ulong,ulong,ulong)
0x18000ee2d  mov     dword ptr [rdi+118h], 0
0x18000ee37  mov     rcx, [rdi+110h]; hEvent
0x18000ee3e  call    cs:__imp_SetEvent
0x18000ee44  jmp     loc_18000EA4D
```
