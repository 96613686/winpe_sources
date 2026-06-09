# UmpoMain

- ea: `0x18000ed10`
- end: `0x18000f3d5`
- name: `UmpoMain`
- size: `1733`
- prototype: `DWORD()`
- caller_count: `0`
- callee_count: `20`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180001008`
- `0x180002bc0`
- `0x180007ee8`
- `0x18000886c`
- `0x18000a030`
- `0x18000ed10`
- `0x18000f3dc`
- `0x18000f484`
- `0x180010a58`
- `0x180010e38`
- `0x180011790`
- `0x180014f78`
- `0x18001523c`
- `0x180015280`
- `0x180016a3c`
- `0x180017124`
- `0x180017140`
- `0x18001735c`
- `0x1800177bc`
- `0x180019010`

## import_xrefs

- `ntdll!RtlCreateHeap` at `0x18000edd5`
- `ntdll!RtlCreateHeap` at `0x18000edd5`
- `ntdll!RtlIsMultiSessionSku` at `0x18000f291`
- `ntdll!RtlIsMultiSessionSku` at `0x18000f291`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x18000f029`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x18000f029`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18000f2a7`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18000f2a7`
- `ntdll!EtwEventRegister` at `0x18000f0b4`
- `ntdll!EtwEventRegister` at `0x18000f0b4`
- `ntdll!DbgPrint` at `0x18000ed83`
- `ntdll!DbgPrint` at `0x18000ee35`
- `ntdll!DbgPrint` at `0x18000f182`
- `ntdll!DbgPrint` at `0x18000f1d7`
- `ntdll!DbgPrint` at `0x18000f278`
- `ntdll!DbgPrint` at `0x18000f327`
- `ntdll!DbgPrint` at `0x18000ed83`
- `ntdll!DbgPrint` at `0x18000ee35`
- `ntdll!DbgPrint` at `0x18000f182`
- `ntdll!DbgPrint` at `0x18000f1d7`
- `ntdll!DbgPrint` at `0x18000f278`
- `ntdll!DbgPrint` at `0x18000f327`
- `ntdll!NtPowerInformation` at `0x18000ee55`
- `ntdll!NtPowerInformation` at `0x18000ee55`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f377`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f377`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f355`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f355`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ed4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ed4b`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18000eecb`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18000eecb`
- `RPCRT4!RpcStringBindingComposeW` at `0x18000eeb4`
- `RPCRT4!RpcStringBindingComposeW` at `0x18000eeb4`
- `RPCRT4!RpcStringFreeW` at `0x18000eed7`
- `RPCRT4!RpcStringFreeW` at `0x18000eed7`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18000ed39`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18000ed39`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18000f105`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18000f105`
- `ext-ms-win-umpoext-umpo-l1-1-0!ExtensionInit` at `0x18000ef50`
- `ext-ms-win-umpoext-umpo-l1-1-0!ExtensionInit` at `0x18000ef50`
- `ext-ms-win-security-slc-l1-1-0!SLGetWindowsInformationDWORD` at `0x18000ef17`
- `ext-ms-win-security-slc-l1-1-0!SLGetWindowsInformationDWORD` at `0x18000ef17`

## string_xrefs

- `0x18000ed6e`: `RegisterServiceCtrlHandler`
- `0x18000ee1d`: `RtlCreateHeap`

## pseudocode

```c
DWORD UmpoMain()
{
  DWORD result; // eax
  unsigned int v1; // ebx
  const char *v2; // r8
  unsigned __int8 IsProcessInVAILContainer; // al
  int PlatformRole; // eax
  unsigned int v5; // eax
  __int64 (*v6)(void); // rax
  __int64 (*v7)(void); // rax
  int Lock; // [rsp+20h] [rbp-20h]
  _DWORD v9[4]; // [rsp+30h] [rbp-10h] BYREF
  unsigned __int8 OutputBuffer; // [rsp+70h] [rbp+30h] BYREF
  RPC_WSTR StringBinding; // [rsp+78h] [rbp+38h] BYREF

  OutputBuffer = 0;
  v9[0] = 0;
  UmpoHandle = RegisterServiceCtrlHandlerExW(L"Power", UmpoControlHandler, 0);
  if ( UmpoHandle )
  {
    *(_QWORD *)&UmpoStatus.dwCurrentState = 0;
    *(_QWORD *)&UmpoStatus.dwWin32ExitCode = 0;
    *(_QWORD *)&UmpoStatus.dwCheckPoint = 0;
    UmpoStatus.dwServiceType = 32;
    UmpoSetStatus(2, 0, 3000, 0);
    UmpoHeapHandle = RtlCreateHeap(2u, 0, 0, 0, 0, 0);
    if ( UmpoHeapHandle || (UmpoHeapHandle = NtCurrentPeb()->ProcessHeap) != 0 )
    {
      if ( NtPowerInformation((POWER_INFORMATION_LEVEL)66, 0, 0, &OutputBuffer, 1u) < 0 )
        MicrosoftTelemetryAssertTriggeredNoArgs();
      UmpoAoAc = OutputBuffer;
      IsProcessInVAILContainer = UmpoIsProcessInVAILContainer();
      UmpoInVAILContainer = IsProcessInVAILContainer;
      if ( IsProcessInVAILContainer
        && ((StringBinding = 0,
             UmpoHvPowerRequestClientInitialized = 1,
             (v1 = RpcStringBindingComposeW(
                     0,
                     (RPC_WSTR)L"ncacn_hvsocket",
                     (RPC_WSTR)L"parent",
                     (RPC_WSTR)L"42011404-0324-4cd0-b565-ed6806063ecc",
                     0,
                     &StringBinding)) != 0)
         || (v1 = RpcBindingFromStringBindingW(StringBinding, &UmpoHvRpcPowerRequestClientHandle),
             RpcStringFreeW(&StringBinding),
             v1)) )
      {
        MicrosoftTelemetryAssertTriggeredNoArgs();
        if ( (UmpoDebug & 1) != 0 )
        {
          Lock = 383;
          v2 = "UmpoHvPowerRequestRpcClientInit()";
          goto LABEL_8;
        }
      }
      else
      {
        LODWORD(StringBinding) = 0;
        if ( SLGetWindowsInformationDWORD(L"Power-UltimatePerformanceScheme-Enabled", (DWORD *)&StringBinding) >= 0 )
        {
          if ( (_DWORD)StringBinding )
          {
            PlatformRole = UmpoInternalGetPlatformRole();
            if ( PlatformRole != 2 && PlatformRole != 8 )
              UmpoUltimatePerfSchemeAllowed = 1;
          }
        }
        if ( IsExtensionInitPresent() )
          ExtensionInit(&UmpoExtensions);
        v5 = UmpoNotifyInit(0);
        v1 = v5;
        if ( v5 )
        {
          if ( (UmpoDebug & 1) != 0 )
            DbgPrint("%s: [%s] Error %08x, line %d\n", "UmpoMain", "UmpoNotifyInit(0)", v5, 406);
          return UmpoMainStop(v1);
        }
        UmpoPowerRequestInit(0);
        v1 = UmpoAlpcInit();
        if ( v1 )
        {
          if ( (UmpoDebug & 1) != 0 )
          {
            Lock = 422;
            v2 = "UmpoAlpcInit()";
            goto LABEL_8;
          }
        }
        else
        {
          v1 = UmpoRpcServerInit();
          if ( v1 )
          {
            if ( (UmpoDebug & 1) != 0 )
            {
              Lock = 432;
              v2 = "UmpoRPCServerInit()";
              goto LABEL_8;
            }
          }
          else
          {
            v1 = UmpoInternalPowerPolicyInit();
            if ( v1 )
            {
              if ( (UmpoDebug & 1) != 0 )
              {
                Lock = 442;
                v2 = "UmpoInternalPowerPolicyInit";
                goto LABEL_8;
              }
            }
            else
            {
              v1 = UmpoSmartPresenceInit(v9);
              if ( !v1 || (unsigned int)RtlGetCurrentServiceSessionId() )
              {
                UmpoInitSmartSuspend();
                if ( qword_1800246A0 && (v1 = qword_1800246A0()) != 0 )
                {
                  if ( (UmpoDebug & 1) != 0 )
                  {
                    Lock = 467;
                    v2 = "EXT(GroupPolicyInit)";
                    goto LABEL_8;
                  }
                }
                else
                {
                  UmpoPowerRequestInit(1);
                  v1 = EtwEventRegister(UMPO_ETW_PROVIDER, UmpoControlCallback, 0, &UmpoProviderHandle);
                  if ( v1 )
                  {
                    UmpoProviderHandle = 0;
                    if ( (UmpoDebug & 1) != 0 )
                    {
                      Lock = 484;
                      v2 = "UmpoDiagInit";
                      goto LABEL_8;
                    }
                  }
                  else
                  {
                    EventSetInformation(
                      UmpoProviderHandle,
                      2,
                      &`EnableManifestedProviderForMicrosoftTelemetry'::`2'::Traits,
                      (unsigned __int16)`EnableManifestedProviderForMicrosoftTelemetry'::`2'::Traits);
                    TraceLoggingRegisterEx_EventRegister_EventSetInformation();
                    v1 = UmpoNotifyInit(1);
                    if ( !v1 )
                    {
                      if ( UmpoExtensions )
                      {
                        v1 = UmpoExtensions();
                        if ( v1 )
                        {
                          if ( (UmpoDebug & 1) != 0 )
                            DbgPrint("%s: [%s] Error %08x, line %d\n", "UmpoMain", "EXT(DimEngineStart)", v1, 505);
                        }
                      }
                      if ( !UmpoIsServerSku() )
                      {
                        if ( qword_1800246F8 )
                        {
                          v1 = qword_1800246F8();
                          if ( v1 )
                          {
                            if ( (UmpoDebug & 1) != 0 )
                              DbgPrint(
                                "%s: [%s] Error %08x, line %d\n",
                                "UmpoMain",
                                "EXT(StartSleepStudyTracing)",
                                v1,
                                519);
                            v1 = 0;
                          }
                        }
                        v6 = (__int64 (*)(void))qword_180024748;
                        if ( qword_180024748 )
                        {
                          if ( UmpoInVAILContainer )
                          {
                            MicrosoftTelemetryAssertTriggeredNoArgs();
                            v6 = (__int64 (*)(void))qword_180024748;
                          }
                          v1 = v6();
                          if ( v1 )
                          {
                            if ( (UmpoDebug & 1) != 0 )
                            {
                              Lock = 536;
                              v2 = "EXT(HvRpcPowerRequestServerInit)";
                              goto LABEL_8;
                            }
                            return UmpoMainStop(v1);
                          }
                        }
                        if ( (unsigned int)Feature_WISEBatteryDischargeTimeEstimate__private_IsEnabledDeviceUsageNoInline() )
                        {
                          if ( qword_180024758 )
                          {
                            v1 = qword_180024758();
                            if ( v1 )
                            {
                              if ( (UmpoDebug & 1) != 0 )
                                DbgPrint(
                                  "%s: [%s] Error %08x, line %d\n",
                                  "UmpoMain",
                                  "EXT(BatteryIntelligenceInit)",
                                  v1,
                                  553);
                              v1 = 0;
                            }
                          }
                        }
                        if ( qword_180024738 )
                          qword_180024738();
                      }
                      if ( (unsigned __int8)RtlIsMultiSessionSku()
                        || (LODWORD(StringBinding) = 0,
                            RtlGetDeviceFamilyInfoEnum(0, &StringBinding, 0),
                            (_DWORD)StringBinding == 16)
                        && (unsigned __int8)UmpoIsProcessInHost() )
                      {
                        if ( UmpoAoAc )
                        {
                          v7 = (__int64 (*)(void))qword_180024710;
                          if ( qword_180024710 )
                          {
                            if ( !qword_180024730 )
                            {
                              MicrosoftTelemetryAssertTriggeredNoArgs();
                              v7 = (__int64 (*)(void))qword_180024710;
                            }
                            v1 = v7();
                            if ( v1 )
                            {
                              ((void (*)(void))qword_180024730)();
                              if ( (UmpoDebug & 1) != 0 )
                                DbgPrint("%s: [%s] Error %08x, line %d\n", "UmpoMain", "AdaptiveStandbyInit", v1, 589);
                              v1 = 0;
                            }
                          }
                        }
                      }
                      UmpoSetStatus(4, 0, 0, v9[0]);
                      if ( byte_180024FA8 != 1 )
                        MicrosoftTelemetryAssertTriggeredNoArgs();
                      EnterCriticalSection(&UmpoSchemeLock);
                      UmpoNotifyKernelAllPowerPolicyChanged(0);
                      if ( byte_180024FA8 != 1 )
                        MicrosoftTelemetryAssertTriggeredNoArgs();
                      LeaveCriticalSection(&UmpoSchemeLock);
                      UmpoPowerRequestInit(2);
                      result = (unsigned int)qword_180024698;
                      if ( !qword_180024698 )
                      {
                        if ( !v1 )
                          return result;
                        return UmpoMainStop(v1);
                      }
                      result = qword_180024698();
                      v1 = result;
                      if ( !result )
                        return result;
                      if ( (UmpoDebug & 1) != 0 )
                      {
                        Lock = 623;
                        v2 = "EXT(RegisterDeviceInterfaces)";
                        goto LABEL_8;
                      }
                      return UmpoMainStop(v1);
                    }
                    if ( (UmpoDebug & 1) != 0 )
                    {
                      Lock = 494;
                      v2 = "UmpoNotifyInit(1)";
                      goto LABEL_8;
                    }
                  }
                }
              }
              else if ( (UmpoDebug & 1) != 0 )
              {
                Lock = 454;
                v2 = "UmpoSmartPresenceInit";
                goto LABEL_8;
              }
            }
          }
        }
      }
    }
    else
    {
      v1 = 8;
      if ( (UmpoDebug & 1) != 0 )
      {
        Lock = 351;
        v2 = "RtlCreateHeap";
LABEL_8:
        DbgPrint("%s: [%s] Error %08x, line %d\n", "UmpoMain", v2, v1, Lock);
      }
    }
    return UmpoMainStop(v1);
  }
  result = GetLastError();
  if ( (UmpoDebug & 1) != 0 )
    return DbgPrint("%s: [%s] Error %08x, line %d\n", "UmpoMain", "RegisterServiceCtrlHandler", result, 329);
  return result;
}

```

## disassembly

```asm
0x18000ed10  mov     [rsp-18h+arg_0], rbx
0x18000ed15  push    rbp
0x18000ed16  push    rsi
0x18000ed17  push    rdi
0x18000ed18  mov     rbp, rsp
0x18000ed1b  sub     rsp, 40h
0x18000ed1f  xor     esi, esi
0x18000ed21  lea     rdx, UmpoControlHandler; lpHandlerProc
0x18000ed28  xor     r8d, r8d; lpContext
0x18000ed2b  mov     [rbp+OutputBuffer], sil
0x18000ed2f  lea     rcx, ServiceName; "Power"
0x18000ed36  mov     [rbp+var_10], esi
0x18000ed39  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x18000ed3f  mov     cs:UmpoHandle, rax
0x18000ed46  test    rax, rax
0x18000ed49  jnz     short loc_18000ED8E
0x18000ed4b  call    cs:__imp_GetLastError
0x18000ed51  mov     ecx, cs:UmpoDebug
0x18000ed57  lea     edi, [rsi+1]
0x18000ed5a  test    dil, cl
0x18000ed5d  jz      loc_18000F3C8
0x18000ed63  mov     r9d, eax
0x18000ed66  mov     dword ptr [rsp+40h+Lock], 149h
0x18000ed6e  lea     r8, aRegisterservic; "RegisterServiceCtrlHandler"
0x18000ed75  lea     rdx, aUmpomain_0; "UmpoMain"
0x18000ed7c  lea     rcx, aSSError08xLine; "%s: [%s] Error %08x, line %d\n"
0x18000ed83  call    cs:__imp_DbgPrint
0x18000ed89  jmp     loc_18000F3C8
0x18000ed8e  xor     edx, edx
0x18000ed90  mov     qword ptr cs:UmpoStatus.dwCurrentState, rsi
0x18000ed97  xor     r9d, r9d
0x18000ed9a  mov     qword ptr cs:UmpoStatus.dwWin32ExitCode, rsi
0x18000eda1  mov     r8d, 0BB8h
0x18000eda7  mov     qword ptr cs:UmpoStatus.dwCheckPoint, rsi
0x18000edae  mov     cs:UmpoStatus.dwServiceType, 20h ; ' '
0x18000edb8  lea     ecx, [rdx+2]
0x18000edbb  call    UmpoSetStatus
0x18000edc0  xor     edx, edx; BaseAddress
0x18000edc2  mov     [rsp+40h+Parameters], rsi; Parameters
0x18000edc7  xor     r9d, r9d; SizeToCommit
0x18000edca  mov     [rsp+40h+Lock], rsi; Lock
0x18000edcf  xor     r8d, r8d; SizeToReserve
0x18000edd2  lea     ecx, [rdx+2]; Flags
0x18000edd5  call    cs:__imp_RtlCreateHeap
0x18000eddb  mov     cs:UmpoHeapHandle, rax
0x18000ede2  test    rax, rax
0x18000ede5  jnz     short loc_18000EE40
0x18000ede7  mov     rax, gs:60h
0x18000edf0  mov     rcx, [rax+30h]
0x18000edf4  mov     cs:UmpoHeapHandle, rcx
0x18000edfb  test    rcx, rcx
0x18000edfe  jnz     short loc_18000EE40
0x18000ee00  mov     eax, cs:UmpoDebug
0x18000ee06  lea     edi, [rcx+1]
0x18000ee09  lea     ebx, [rcx+8]
0x18000ee0c  test    dil, al
0x18000ee0f  jz      loc_18000F3C1
0x18000ee15  mov     dword ptr [rsp+40h+Lock], 15Fh
0x18000ee1d  lea     r8, aRtlcreateheap; "RtlCreateHeap"
0x18000ee24  mov     r9d, ebx
0x18000ee27  lea     rdx, aUmpomain_0; "UmpoMain"
0x18000ee2e  lea     rcx, aSSError08xLine; "%s: [%s] Error %08x, line %d\n"
0x18000ee35  call    cs:__imp_DbgPrint
0x18000ee3b  jmp     loc_18000F3C1
0x18000ee40  mov     edi, 1
0x18000ee45  lea     r9, [rbp+OutputBuffer]; OutputBuffer
0x18000ee49  xor     r8d, r8d; InputBufferLength
0x18000ee4c  mov     dword ptr [rsp+40h+Lock], edi; OutputBufferLength
0x18000ee50  xor     edx, edx; InputBuffer
0x18000ee52  lea     ecx, [rdi+41h]; PowerInformationLevel
0x18000ee55  call    cs:__imp_NtPowerInformation
0x18000ee5b  test    eax, eax
0x18000ee5d  jns     short loc_18000EE64
0x18000ee5f  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000ee64  movzx   eax, [rbp+OutputBuffer]
0x18000ee68  mov     cs:UmpoAoAc, eax
0x18000ee6e  call    UmpoIsProcessInVAILContainer
0x18000ee73  movzx   eax, al
0x18000ee76  mov     cs:UmpoInVAILContainer, eax
0x18000ee7c  test    eax, eax
0x18000ee7e  jz      loc_18000EF09
0x18000ee84  lea     rax, [rbp+StringBinding]
0x18000ee88  mov     [rbp+StringBinding], rsi
0x18000ee8c  mov     [rsp+40h+Parameters], rax; StringBinding
0x18000ee91  lea     r9, Endpoint; "42011404-0324-4cd0-b565-ed6806063ecc"
0x18000ee98  lea     r8, NetworkAddr; "parent"
0x18000ee9f  mov     [rsp+40h+Lock], rsi; Options
0x18000eea4  lea     rdx, ProtSeq; "ncacn_hvsocket"
0x18000eeab  mov     cs:UmpoHvPowerRequestClientInitialized, dil
0x18000eeb2  xor     ecx, ecx; ObjUuid
0x18000eeb4  call    cs:__imp_RpcStringBindingComposeW
0x18000eeba  mov     ebx, eax
0x18000eebc  test    eax, eax
0x18000eebe  jnz     short loc_18000EEE1
0x18000eec0  mov     rcx, [rbp+StringBinding]; StringBinding
0x18000eec4  lea     rdx, UmpoHvRpcPowerRequestClientHandle; Binding
0x18000eecb  call    cs:__imp_RpcBindingFromStringBindingW
0x18000eed1  lea     rcx, [rbp+StringBinding]; String
0x18000eed5  mov     ebx, eax
0x18000eed7  call    cs:__imp_RpcStringFreeW
0x18000eedd  test    ebx, ebx
0x18000eedf  jz      short loc_18000EF09
0x18000eee1  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000eee6  mov     eax, cs:UmpoDebug
0x18000eeec  test    dil, al
0x18000eeef  jz      loc_18000F3C1
0x18000eef5  mov     dword ptr [rsp+40h+Lock], 17Fh
0x18000eefd  lea     r8, aUmpohvpowerreq; "UmpoHvPowerRequestRpcClientInit()"
0x18000ef04  jmp     loc_18000EE24
0x18000ef09  lea     rdx, [rbp+StringBinding]; pdwValue
0x18000ef0d  mov     dword ptr [rbp+StringBinding], esi
0x18000ef10  lea     rcx, pwszValueName; "Power-UltimatePerformanceScheme-Enabled"
0x18000ef17  call    cs:__imp_SLGetWindowsInformationDWORD
0x18000ef1d  test    eax, eax
0x18000ef1f  js      short loc_18000EF40
0x18000ef21  cmp     dword ptr [rbp+StringBinding], esi
0x18000ef24  jz      short loc_18000EF40
0x18000ef26  call    UmpoInternalGetPlatformRole
0x18000ef2b  cmp     eax, 2
0x18000ef2e  jz      short loc_18000EF40
0x18000ef30  mov     ebx, 8
0x18000ef35  cmp     eax, ebx
0x18000ef37  jz      short loc_18000EF40
0x18000ef39  mov     cs:UmpoUltimatePerfSchemeAllowed, dil
0x18000ef40  call    IsExtensionInitPresent
0x18000ef45  test    al, al
0x18000ef47  jz      short loc_18000EF56
0x18000ef49  lea     rcx, UmpoExtensions
0x18000ef50  call    cs:__imp_ExtensionInit
0x18000ef56  xor     ecx, ecx
0x18000ef58  call    UmpoNotifyInit
0x18000ef5d  mov     ebx, eax
0x18000ef5f  test    eax, eax
0x18000ef61  jz      short loc_18000EF89
0x18000ef63  mov     ecx, cs:UmpoDebug
0x18000ef69  test    dil, cl
0x18000ef6c  jz      loc_18000F3C1
0x18000ef72  mov     dword ptr [rsp+40h+Lock], 196h
0x18000ef7a  lea     r8, aUmponotifyinit; "UmpoNotifyInit(0)"
0x18000ef81  mov     r9d, eax
0x18000ef84  jmp     loc_18000EE27
0x18000ef89  xor     ecx, ecx
0x18000ef8b  call    UmpoPowerRequestInit
0x18000ef90  call    UmpoAlpcInit
0x18000ef95  mov     ebx, eax
0x18000ef97  test    eax, eax
0x18000ef99  jz      short loc_18000EFBE
0x18000ef9b  mov     eax, cs:UmpoDebug
0x18000efa1  test    dil, al
0x18000efa4  jz      loc_18000F3C1
0x18000efaa  mov     dword ptr [rsp+40h+Lock], 1A6h
0x18000efb2  lea     r8, aUmpoalpcinit; "UmpoAlpcInit()"
0x18000efb9  jmp     loc_18000EE24
0x18000efbe  call    UmpoRpcServerInit
0x18000efc3  mov     ebx, eax
0x18000efc5  test    eax, eax
0x18000efc7  jz      short loc_18000EFEC
0x18000efc9  mov     eax, cs:UmpoDebug
0x18000efcf  test    dil, al
0x18000efd2  jz      loc_18000F3C1
0x18000efd8  mov     dword ptr [rsp+40h+Lock], 1B0h
0x18000efe0  lea     r8, aUmporpcserveri; "UmpoRPCServerInit()"
0x18000efe7  jmp     loc_18000EE24
0x18000efec  call    UmpoInternalPowerPolicyInit
0x18000eff1  mov     ebx, eax
0x18000eff3  test    eax, eax
0x18000eff5  jz      short loc_18000F01A
0x18000eff7  mov     eax, cs:UmpoDebug
0x18000effd  test    dil, al
0x18000f000  jz      loc_18000F3C1
0x18000f006  mov     dword ptr [rsp+40h+Lock], 1BAh
0x18000f00e  lea     r8, aUmpointernalpo; "UmpoInternalPowerPolicyInit"
0x18000f015  jmp     loc_18000EE24
0x18000f01a  lea     rcx, [rbp+var_10]
0x18000f01e  call    UmpoSmartPresenceInit
0x18000f023  mov     ebx, eax
0x18000f025  test    eax, eax
0x18000f027  jz      short loc_18000F056
0x18000f029  call    cs:__imp_RtlGetCurrentServiceSessionId
0x18000f02f  test    eax, eax
0x18000f031  jnz     short loc_18000F056
0x18000f033  mov     eax, cs:UmpoDebug
0x18000f039  test    dil, al
0x18000f03c  jz      loc_18000F3C1
0x18000f042  mov     dword ptr [rsp+40h+Lock], 1C6h
0x18000f04a  lea     r8, aUmposmartprese_1; "UmpoSmartPresenceInit"
0x18000f051  jmp     loc_18000EE24
0x18000f056  call    UmpoInitSmartSuspend
0x18000f05b  mov     rax, cs:qword_1800246A0
0x18000f062  test    rax, rax
0x18000f065  jz      short loc_18000F095
0x18000f067  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f06c  mov     ebx, eax
0x18000f06e  test    eax, eax
0x18000f070  jz      short loc_18000F095
0x18000f072  mov     eax, cs:UmpoDebug
0x18000f078  test    dil, al
0x18000f07b  jz      loc_18000F3C1
0x18000f081  mov     dword ptr [rsp+40h+Lock], 1D3h
0x18000f089  lea     r8, aExtGrouppolicy; "EXT(GroupPolicyInit)"
0x18000f090  jmp     loc_18000EE24
0x18000f095  mov     ecx, edi
0x18000f097  call    UmpoPowerRequestInit
0x18000f09c  lea     r9, UmpoProviderHandle
0x18000f0a3  xor     r8d, r8d
0x18000f0a6  lea     rdx, UmpoControlCallback
0x18000f0ad  lea     rcx, UMPO_ETW_PROVIDER
0x18000f0b4  call    cs:__imp_EtwEventRegister
0x18000f0ba  mov     ebx, eax
0x18000f0bc  test    eax, eax
0x18000f0be  jz      short loc_18000F0EA
0x18000f0c0  mov     eax, cs:UmpoDebug
0x18000f0c6  mov     cs:UmpoProviderHandle, rsi
0x18000f0cd  test    dil, al
0x18000f0d0  jz      loc_18000F3C1
0x18000f0d6  mov     dword ptr [rsp+40h+Lock], 1E4h
0x18000f0de  lea     r8, aUmpodiaginit; "UmpoDiagInit"
0x18000f0e5  jmp     loc_18000EE24
0x18000f0ea  movzx   r9d, cs:?Traits@?1??EnableManifestedProviderForMicrosoftTelemetry@@9@9; `EnableManifestedProviderForMicrosoftTelemetry'::`2'::Traits
0x18000f0f2  lea     r8, ?Traits@?1??EnableManifestedProviderForMicrosoftTelemetry@@9@9; `EnableManifestedProviderForMicrosoftTelemetry'::`2'::Traits
0x18000f0f9  mov     rcx, cs:UmpoProviderHandle
0x18000f100  mov     edx, 2
0x18000f105  call    cs:__imp_EventSetInformation
0x18000f10b  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18000f110  mov     ecx, edi
0x18000f112  call    UmpoNotifyInit
0x18000f117  mov     ebx, eax
0x18000f119  test    eax, eax
0x18000f11b  jz      short loc_18000F140
0x18000f11d  mov     eax, cs:UmpoDebug
0x18000f123  test    dil, al
0x18000f126  jz      loc_18000F3C1
0x18000f12c  mov     dword ptr [rsp+40h+Lock], 1EEh
0x18000f134  lea     r8, aUmponotifyinit_0; "UmpoNotifyInit(1)"
0x18000f13b  jmp     loc_18000EE24
0x18000f140  mov     rax, cs:UmpoExtensions
0x18000f147  test    rax, rax
0x18000f14a  jz      short loc_18000F188
0x18000f14c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f151  mov     ebx, eax
0x18000f153  test    eax, eax
0x18000f155  jz      short loc_18000F188
0x18000f157  mov     eax, cs:UmpoDebug
0x18000f15d  test    dil, al
0x18000f160  jz      short loc_18000F188
0x18000f162  mov     r9d, ebx
0x18000f165  mov     dword ptr [rsp+40h+Lock], 1F9h
0x18000f16d  lea     r8, aExtDimenginest; "EXT(DimEngineStart)"
0x18000f174  lea     rdx, aUmpomain_0; "UmpoMain"
0x18000f17b  lea     rcx, aSSError08xLine; "%s: [%s] Error %08x, line %d\n"
0x18000f182  call    cs:__imp_DbgPrint
0x18000f188  call    UmpoIsServerSku
0x18000f18d  test    al, al
0x18000f18f  jnz     loc_18000F291
0x18000f195  mov     rax, cs:qword_1800246F8
0x18000f19c  test    rax, rax
0x18000f19f  jz      short loc_18000F1DF
0x18000f1a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f1a6  mov     ebx, eax
0x18000f1a8  test    eax, eax
0x18000f1aa  jz      short loc_18000F1DF
0x18000f1ac  mov     eax, cs:UmpoDebug
0x18000f1b2  test    dil, al
0x18000f1b5  jz      short loc_18000F1DD
0x18000f1b7  mov     r9d, ebx
0x18000f1ba  mov     dword ptr [rsp+40h+Lock], 207h
0x18000f1c2  lea     r8, aExtStartsleeps; "EXT(StartSleepStudyTracing)"
0x18000f1c9  lea     rdx, aUmpomain_0; "UmpoMain"
0x18000f1d0  lea     rcx, aSSError08xLine; "%s: [%s] Error %08x, line %d\n"
0x18000f1d7  call    cs:__imp_DbgPrint
0x18000f1dd  mov     ebx, esi
0x18000f1df  mov     rax, cs:qword_180024748
0x18000f1e6  test    rax, rax
0x18000f1e9  jz      short loc_18000F22D
0x18000f1eb  cmp     cs:UmpoInVAILContainer, esi
0x18000f1f1  jz      short loc_18000F1FF
0x18000f1f3  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000f1f8  mov     rax, cs:qword_180024748
0x18000f1ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f204  mov     ebx, eax
0x18000f206  test    eax, eax
0x18000f208  jz      short loc_18000F22D
0x18000f20a  mov     eax, cs:UmpoDebug
0x18000f210  test    dil, al
0x18000f213  jz      loc_18000F3C1
0x18000f219  mov     dword ptr [rsp+40h+Lock], 218h
0x18000f221  lea     r8, aExtHvrpcpowerr; "EXT(HvRpcPowerRequestServerInit)"
0x18000f228  jmp     loc_18000EE24
0x18000f22d  call    Feature_WISEBatteryDischargeTimeEstimate__private_IsEnabledDeviceUsageNoInline
0x18000f232  test    eax, eax
0x18000f234  jz      short loc_18000F280
0x18000f236  mov     rax, cs:qword_180024758
0x18000f23d  test    rax, rax
0x18000f240  jz      short loc_18000F280
0x18000f242  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f247  mov     ebx, eax
0x18000f249  test    eax, eax
0x18000f24b  jz      short loc_18000F280
0x18000f24d  mov     eax, cs:UmpoDebug
0x18000f253  test    dil, al
  ... truncated ...
```
