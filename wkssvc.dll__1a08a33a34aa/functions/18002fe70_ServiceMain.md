# ServiceMain

- ea: `0x18002fe70`
- end: `0x1800302ff`
- name: `ServiceMain`
- size: `1167`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180006a98`
- `0x180006dbc`
- `0x18000c978`
- `0x18000d474`
- `0x18000da34`
- `0x18000e57c`
- `0x180011f1c`
- `0x180012368`
- `0x180024550`
- `0x18002bb68`
- `0x18002fe70`
- `0x180030444`
- `0x180030710`
- `0x180031cac`
- `0x180037010`

## import_xrefs

- `ntdll!DbgPrint` at `0x18002fed6`
- `ntdll!DbgPrint` at `0x18002fef1`
- `ntdll!DbgPrint` at `0x18002fed6`
- `ntdll!DbgPrint` at `0x18002fef1`
- `ntdll!RtlDeregisterWait` at `0x18002ffeb`
- `ntdll!RtlDeregisterWait` at `0x18002ffeb`
- `ntdll!RtlGetPersistedStateLocation` at `0x1800301a1`
- `ntdll!RtlGetPersistedStateLocation` at `0x1800301a1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002ff3e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002ff3e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003014c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003014c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ff78`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ffd6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003005c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ff78`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ffd6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003005c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180030001`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180030015`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180030001`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180030015`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002ffba`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002ffba`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002ff60`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003002b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002ff60`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003002b`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x1800300b4`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x1800300b4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030079`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030079`
- `USERENV!RegisterGPNotification` at `0x18003004c`
- `USERENV!RegisterGPNotification` at `0x18003004c`

## string_xrefs

- `0x1800300fa`: `WKSSVC failed with WsUpdateStatus %x\n`
- `0x180030189`: `\Registry\Machine\SYSTEM\CurrentControlSet\Services\LanmanWorkstation`
- `0x18002feea`: `WKSSVC ServiceMain returned with %x\n`

## pseudocode

```c
__int64 ServiceMain()
{
  unsigned int LastError; // ebx
  HANDLE EventW; // rax
  HANDLE v3; // rax
  unsigned int updated; // eax
  DWORD v5; // eax
  int PersistedStateLocation; // eax
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  int v9; // [rsp+80h] [rbp+18h] BYREF

  WsInitState = 0;
  WsIsTerminationHandlerRunning = 0;
  WsWorkerCriticalSectionInitialized = 0;
  RegNotifyInfo = 0;
  dword_180051540 = 0;
  xmmword_180051548 = 0;
  if ( (unsigned int)WitnessInitialize() )
    WitnessTerminate();
  else
    WitnessClientEngineInitialized = 1;
  LastError = WsInitializeWorkstation();
  if ( LastError )
  {
    DbgPrint("WKSSVC failed to initialize workstation %x\n", (unsigned int)WsInitState);
LABEL_6:
    WsInitializeStatusError = LastError;
    DbgPrint("WKSSVC ServiceMain returned with %x\n", LastError);
    return WsTerminationNotify(0, 0);
  }
  LastError = WsAllocConfigName();
  if ( LastError )
    goto LABEL_6;
  LastError = RegOpenKeyExW(HKEY_LOCAL_MACHINE, RegPathToWatch, 0, 0x20019u, &ConfigHandle);
  if ( LastError )
    goto LABEL_6;
  ConfigHandleOpened = 1;
  EventW = CreateEventW(0, 0, 0, 0);
  RegistryChangeEvent = EventW;
  if ( !EventW )
    goto LABEL_10;
  RegNotifyInfo = (__int64)EventW;
  *((_QWORD *)&xmmword_180051548 + 1) = ConfigHandle;
  dword_180051540 = -1;
  *(_QWORD *)&xmmword_180051548 = 0;
  EnterCriticalSection(&WsWorkerCriticalSection);
  if ( !(unsigned int)WsReInitChangeNotify(&RegNotifyInfo) )
  {
    LastError = GetLastError();
    RtlDeregisterWait(TerminateWorkItem);
    TerminateWorkItem = 0;
    LeaveCriticalSection(&WsWorkerCriticalSection);
    goto LABEL_6;
  }
  LeaveCriticalSection(&WsWorkerCriticalSection);
  v3 = CreateEventW(0, 0, 0, 0);
  MachineGroupPolicyChangeEvent = v3;
  if ( !v3 )
    goto LABEL_10;
  if ( RegisterGPNotification(v3, 1) )
  {
    RegisteredForMachineGroupPolicyChangeNotifications = 1;
    if ( RegisterWaitForSingleObject(
           &MachineGroupPolicyChangeWaitObject,
           MachineGroupPolicyChangeEvent,
           WsOnMachineGroupPolicyChanged,
           0,
           0xFFFFFFFF,
           0) )
    {
      WaitingForMachineGroupPolicyChanges = 1;
      goto LABEL_19;
    }
LABEL_10:
    LastError = GetLastError();
    goto LABEL_6;
  }
  LastError = GetLastError();
  if ( LastError != 1 )
    goto LABEL_6;
  CloseHandle(MachineGroupPolicyChangeEvent);
  MachineGroupPolicyChangeEvent = 0;
LABEL_19:
  WsGlobalData.dwCurrentState = 4;
  WsGlobalData.dwControlsAccepted = 67;
  *(_QWORD *)&WsGlobalData.dwCheckPoint = 0;
  updated = WsUpdateStatus();
  LastError = updated;
  if ( updated )
  {
    WsInitializeStatusError = updated;
    DbgPrint("WKSSVC failed with WsUpdateStatus %x\n", updated);
    goto LABEL_6;
  }
  v5 = (*(__int64 (__fastcall **)(HANDLE *, const WCHAR *, HANDLE, __int64 (__fastcall *)(_QWORD, _QWORD), _QWORD, int))(WsLmsvcsGlobalData + 192))(
         &TerminateWorkItem,
         L"LanmanWorkstation",
         hHandle,
         WsTerminationNotify,
         0,
         24);
  LastError = v5;
  if ( v5 )
  {
    SetLastError(v5);
    DbgPrint("WKSSVC/RegisterStopCallback failed. Error: %d\n", LastError);
    goto LABEL_6;
  }
  v9 = 0;
  PersistedStateLocation = RtlGetPersistedStateLocation(
                             L"LanmanWorkstation",
                             0,
                             L"\\Registry\\Machine\\SYSTEM\\CurrentControlSet\\Services\\LanmanWorkstation",
                             0,
                             WsData,
                             260,
                             &v9);
  if ( PersistedStateLocation < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      goto LABEL_6;
    }
    v8 = 10;
    goto LABEL_28;
  }
  PersistedStateLocation = RtlStringCchPrintfW(&Path, 260, L"%ws\\%ws", WsData, L"ClientCertificateMappings");
  if ( PersistedStateLocation < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      goto LABEL_6;
    }
    v8 = 11;
    goto LABEL_28;
  }
  PersistedStateLocation = WsQueryRegistrySubkeySecurityDescriptor(&pSecurityDescriptor, WsData);
  LastError = PersistedStateLocation;
  if ( PersistedStateLocation )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      goto LABEL_6;
    }
    v8 = 12;
    goto LABEL_28;
  }
  PersistedStateLocation = WsRestoreCertificateMappings();
  LastError = PersistedStateLocation;
  if ( PersistedStateLocation )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      goto LABEL_6;
    }
    v8 = 13;
LABEL_28:
    WPP_SF_d(v7[2], v8, WPP_31e0dc789b9f3c2c04382f436cbfec2a_Traceguids, (unsigned int)PersistedStateLocation);
    goto LABEL_6;
  }
  WsRestoreGlobalMappingsFromRegistry();
  return WJInitializeWorkplaceJoin();
}

```

## disassembly

```asm
0x18002fe70  push    rbx
0x18002fe72  push    rbp
0x18002fe73  push    rsi
0x18002fe74  push    rdi
0x18002fe75  sub     rsp, 48h
0x18002fe79  xor     edi, edi
0x18002fe7b  xorps   xmm0, xmm0
0x18002fe7e  mov     cs:WsInitState, edi
0x18002fe84  mov     cs:WsIsTerminationHandlerRunning, edi
0x18002fe8a  mov     cs:WsWorkerCriticalSectionInitialized, edi
0x18002fe90  mov     cs:RegNotifyInfo, rdi
0x18002fe97  mov     cs:dword_180051540, edi
0x18002fe9d  movdqu  cs:xmmword_180051548, xmm0
0x18002fea5  call    WitnessInitialize
0x18002feaa  lea     esi, [rdi+1]
0x18002fead  test    eax, eax
0x18002feaf  jz      short loc_18002FEB8
0x18002feb1  call    WitnessTerminate
0x18002feb6  jmp     short loc_18002FEBE
0x18002feb8  mov     cs:WitnessClientEngineInitialized, esi
0x18002febe  call    WsInitializeWorkstation
0x18002fec3  mov     ebx, eax
0x18002fec5  test    eax, eax
0x18002fec7  jz      short loc_18002FF10
0x18002fec9  mov     edx, cs:WsInitState
0x18002fecf  lea     rcx, aWkssvcFailedTo_0; "WKSSVC failed to initialize workstation"...
0x18002fed6  call    cs:__imp_DbgPrint
0x18002fedd  nop     dword ptr [rax+rax+00h]
0x18002fee2  mov     edx, ebx
0x18002fee4  mov     cs:WsInitializeStatusError, ebx
0x18002feea  lea     rcx, aWkssvcServicem; "WKSSVC ServiceMain returned with %x\n"
0x18002fef1  call    cs:__imp_DbgPrint
0x18002fef8  nop     dword ptr [rax+rax+00h]
0x18002fefd  xor     edx, edx
0x18002feff  xor     ecx, ecx
0x18002ff01  call    WsTerminationNotify
0x18002ff06  add     rsp, 48h
0x18002ff0a  pop     rdi
0x18002ff0b  pop     rsi
0x18002ff0c  pop     rbp
0x18002ff0d  pop     rbx
0x18002ff0e  retn
0x18002ff10  call    WsAllocConfigName
0x18002ff15  mov     ebx, eax
0x18002ff17  test    eax, eax
0x18002ff19  jnz     short loc_18002FEE2
0x18002ff1b  mov     rdx, cs:RegPathToWatch; lpSubKey
0x18002ff22  lea     rax, ConfigHandle
0x18002ff29  mov     r9d, 20019h; samDesired
0x18002ff2f  mov     [rsp+68h+phkResult], rax; phkResult
0x18002ff34  xor     r8d, r8d; ulOptions
0x18002ff37  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002ff3e  call    cs:__imp_RegOpenKeyExW
0x18002ff45  nop     dword ptr [rax+rax+00h]
0x18002ff4a  mov     ebx, eax
0x18002ff4c  test    eax, eax
0x18002ff4e  jnz     short loc_18002FEE2
0x18002ff50  xor     r9d, r9d; lpName
0x18002ff53  mov     cs:ConfigHandleOpened, esi
0x18002ff59  xor     r8d, r8d; bInitialState
0x18002ff5c  xor     edx, edx; bManualReset
0x18002ff5e  xor     ecx, ecx; lpEventAttributes
0x18002ff60  call    cs:__imp_CreateEventW
0x18002ff67  nop     dword ptr [rax+rax+00h]
0x18002ff6c  mov     cs:RegistryChangeEvent, rax
0x18002ff73  test    rax, rax
0x18002ff76  jnz     short loc_18002FF8B
0x18002ff78  call    cs:__imp_GetLastError
0x18002ff7f  nop     dword ptr [rax+rax+00h]
0x18002ff84  mov     ebx, eax
0x18002ff86  jmp     loc_18002FEE2
0x18002ff8b  mov     cs:RegNotifyInfo, rax
0x18002ff92  lea     rbp, WsWorkerCriticalSection
0x18002ff99  mov     rax, cs:ConfigHandle
0x18002ffa0  or      ebx, 0FFFFFFFFh
0x18002ffa3  mov     rcx, rbp; lpCriticalSection
0x18002ffa6  mov     qword ptr cs:xmmword_180051548+8, rax
0x18002ffad  mov     cs:dword_180051540, ebx
0x18002ffb3  mov     qword ptr cs:xmmword_180051548, rdi
0x18002ffba  call    cs:__imp_EnterCriticalSection
0x18002ffc1  nop     dword ptr [rax+rax+00h]
0x18002ffc6  lea     rcx, RegNotifyInfo; pvContext
0x18002ffcd  call    WsReInitChangeNotify
0x18002ffd2  test    eax, eax
0x18002ffd4  jnz     short loc_180030012
0x18002ffd6  call    cs:__imp_GetLastError
0x18002ffdd  nop     dword ptr [rax+rax+00h]
0x18002ffe2  mov     rcx, cs:TerminateWorkItem; hWaitHandle
0x18002ffe9  mov     ebx, eax
0x18002ffeb  call    cs:__imp_RtlDeregisterWait
0x18002fff2  nop     dword ptr [rax+rax+00h]
0x18002fff7  mov     rcx, rbp; lpCriticalSection
0x18002fffa  mov     cs:TerminateWorkItem, rdi
0x180030001  call    cs:__imp_LeaveCriticalSection
0x180030008  nop     dword ptr [rax+rax+00h]
0x18003000d  jmp     loc_18002FEE2
0x180030012  mov     rcx, rbp; lpCriticalSection
0x180030015  call    cs:__imp_LeaveCriticalSection
0x18003001c  nop     dword ptr [rax+rax+00h]
0x180030021  xor     r9d, r9d; lpName
0x180030024  xor     r8d, r8d; bInitialState
0x180030027  xor     edx, edx; bManualReset
0x180030029  xor     ecx, ecx; lpEventAttributes
0x18003002b  call    cs:__imp_CreateEventW
0x180030032  nop     dword ptr [rax+rax+00h]
0x180030037  mov     cs:MachineGroupPolicyChangeEvent, rax
0x18003003e  test    rax, rax
0x180030041  jz      loc_18002FF78
0x180030047  mov     edx, esi; bMachine
0x180030049  mov     rcx, rax; hEvent
0x18003004c  call    cs:__imp_RegisterGPNotification
0x180030053  nop     dword ptr [rax+rax+00h]
0x180030058  test    eax, eax
0x18003005a  jnz     short loc_18003008E
0x18003005c  call    cs:__imp_GetLastError
0x180030063  nop     dword ptr [rax+rax+00h]
0x180030068  mov     ebx, eax
0x18003006a  cmp     eax, esi
0x18003006c  jnz     loc_18002FEE2
0x180030072  mov     rcx, cs:MachineGroupPolicyChangeEvent; hObject
0x180030079  call    cs:__imp_CloseHandle
0x180030080  nop     dword ptr [rax+rax+00h]
0x180030085  mov     cs:MachineGroupPolicyChangeEvent, rdi
0x18003008c  jmp     short loc_1800300CE
0x18003008e  mov     rdx, cs:MachineGroupPolicyChangeEvent; hObject
0x180030095  lea     r8, WsOnMachineGroupPolicyChanged; Callback
0x18003009c  mov     [rsp+68h+dwFlags], edi; dwFlags
0x1800300a0  lea     rcx, MachineGroupPolicyChangeWaitObject; phNewWaitObject
0x1800300a7  xor     r9d, r9d; Context
0x1800300aa  mov     dword ptr [rsp+68h+phkResult], ebx; dwMilliseconds
0x1800300ae  mov     cs:RegisteredForMachineGroupPolicyChangeNotifications, esi
0x1800300b4  call    cs:__imp_RegisterWaitForSingleObject
0x1800300bb  nop     dword ptr [rax+rax+00h]
0x1800300c0  test    eax, eax
0x1800300c2  jz      loc_18002FF78
0x1800300c8  mov     cs:WaitingForMachineGroupPolicyChanges, esi
0x1800300ce  mov     cs:WsGlobalData.dwCurrentState, 4
0x1800300d8  mov     cs:WsGlobalData.dwControlsAccepted, 43h ; 'C'
0x1800300e2  mov     qword ptr cs:WsGlobalData.dwCheckPoint, rdi
0x1800300e9  call    WsUpdateStatus
0x1800300ee  mov     ebx, eax
0x1800300f0  test    eax, eax
0x1800300f2  jz      short loc_180030108
0x1800300f4  mov     cs:WsInitializeStatusError, eax
0x1800300fa  lea     rcx, aWkssvcFailedWi_4; "WKSSVC failed with WsUpdateStatus %x\n"
0x180030101  mov     edx, eax
0x180030103  jmp     loc_18002FED6
0x180030108  mov     rax, cs:WsLmsvcsGlobalData
0x18003010f  lea     r9, WsTerminationNotify
0x180030116  mov     r8, cs:hHandle
0x18003011d  lea     rdx, aLanmanworkstat; "LanmanWorkstation"
0x180030124  mov     [rsp+68h+dwFlags], 18h
0x18003012c  lea     rcx, TerminateWorkItem
0x180030133  mov     [rsp+68h+phkResult], rdi
0x180030138  mov     rax, [rax+0C0h]
0x18003013f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030144  mov     ebx, eax
0x180030146  test    eax, eax
0x180030148  jz      short loc_180030166
0x18003014a  mov     ecx, eax; dwErrCode
0x18003014c  call    cs:__imp_SetLastError
0x180030153  nop     dword ptr [rax+rax+00h]
0x180030158  mov     edx, ebx
0x18003015a  lea     rcx, aWkssvcRegister; "WKSSVC/RegisterStopCallback failed. Err"...
0x180030161  jmp     loc_18002FED6
0x180030166  lea     rax, [rsp+68h+arg_10]
0x18003016e  mov     [rsp+68h+arg_10], edi
0x180030175  mov     [rsp+68h+var_38], rax
0x18003017a  lea     rbp, WsData
0x180030181  mov     [rsp+68h+dwFlags], 104h
0x180030189  lea     r8, aRegistryMachin; "\\Registry\\Machine\\SYSTEM\\CurrentCon"...
0x180030190  xor     r9d, r9d
0x180030193  mov     [rsp+68h+phkResult], rbp
0x180030198  xor     edx, edx
0x18003019a  lea     rcx, aLanmanworkstat; "LanmanWorkstation"
0x1800301a1  call    cs:__imp_RtlGetPersistedStateLocation
0x1800301a8  nop     dword ptr [rax+rax+00h]
0x1800301ad  test    eax, eax
0x1800301af  jns     short loc_1800301F9
0x1800301b1  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800301b8  lea     rdx, WPP_GLOBAL_Control
0x1800301bf  cmp     rcx, rdx
0x1800301c2  jz      loc_18002FEE2
0x1800301c8  test    [rcx+1Ch], sil
0x1800301cc  jz      loc_18002FEE2
0x1800301d2  cmp     [rcx+19h], sil
0x1800301d6  jb      loc_18002FEE2
0x1800301dc  mov     edx, 0Ah
0x1800301e1  mov     rcx, [rcx+10h]
0x1800301e5  lea     r8, WPP_31e0dc789b9f3c2c04382f436cbfec2a_Traceguids
0x1800301ec  mov     r9d, eax
0x1800301ef  call    WPP_SF_d
0x1800301f4  jmp     loc_18002FEE2
0x1800301f9  lea     rax, aClientcertific; "ClientCertificateMappings"
0x180030200  mov     r9, rbp
0x180030203  lea     r8, aWsWs_1; "%ws\\%ws"
0x18003020a  mov     [rsp+68h+phkResult], rax
0x18003020f  mov     edx, 104h
0x180030214  lea     rcx, Path
0x18003021b  call    RtlStringCchPrintfW
0x180030220  test    eax, eax
0x180030222  jns     short loc_180030256
0x180030224  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18003022b  lea     rdx, WPP_GLOBAL_Control
0x180030232  cmp     rcx, rdx
0x180030235  jz      loc_18002FEE2
0x18003023b  test    [rcx+1Ch], sil
0x18003023f  jz      loc_18002FEE2
0x180030245  cmp     [rcx+19h], sil
0x180030249  jb      loc_18002FEE2
0x18003024f  mov     edx, 0Bh
0x180030254  jmp     short loc_1800301E1
0x180030256  mov     rdx, rbp
0x180030259  lea     rcx, pSecurityDescriptor
0x180030260  call    WsQueryRegistrySubkeySecurityDescriptor
0x180030265  mov     ebx, eax
0x180030267  test    eax, eax
0x180030269  jz      short loc_1800302B3
0x18003026b  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180030272  lea     rdx, WPP_GLOBAL_Control
0x180030279  cmp     rcx, rdx
0x18003027c  jz      loc_18002FEE2
0x180030282  test    [rcx+1Ch], sil
0x180030286  jz      loc_18002FEE2
0x18003028c  cmp     [rcx+19h], sil
0x180030290  jb      loc_18002FEE2
0x180030296  mov     edx, 0Ch
0x18003029b  mov     rcx, [rcx+10h]
0x18003029f  lea     r8, WPP_31e0dc789b9f3c2c04382f436cbfec2a_Traceguids
0x1800302a6  mov     r9d, eax
0x1800302a9  call    WPP_SF_d
0x1800302ae  jmp     loc_18002FEE2
0x1800302b3  call    WsRestoreCertificateMappings
0x1800302b8  mov     ebx, eax
0x1800302ba  test    eax, eax
0x1800302bc  jz      short loc_1800302F0
0x1800302be  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800302c5  lea     rdx, WPP_GLOBAL_Control
0x1800302cc  cmp     rcx, rdx
0x1800302cf  jz      loc_18002FEE2
0x1800302d5  test    [rcx+1Ch], sil
0x1800302d9  jz      loc_18002FEE2
0x1800302df  cmp     [rcx+19h], sil
0x1800302e3  jb      loc_18002FEE2
0x1800302e9  mov     edx, 0Dh
0x1800302ee  jmp     short loc_18003029B
0x1800302f0  call    WsRestoreGlobalMappingsFromRegistry
0x1800302f5  call    WJInitializeWorkplaceJoin
0x1800302fa  jmp     loc_18002FF06
```
