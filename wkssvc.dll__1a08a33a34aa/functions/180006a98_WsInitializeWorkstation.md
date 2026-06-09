# WsInitializeWorkstation

- ea: `0x180006a98`
- end: `0x180006db4`
- name: `WsInitializeWorkstation`
- size: `796`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18002fe70`

## callees

- `0x180006964`
- `0x180006a98`
- `0x180006dbc`
- `0x180006e0c`
- `0x180006ea0`
- `0x180007224`
- `0x180007290`
- `0x18000743c`

## import_xrefs

- `ntdll!DbgPrint` at `0x180006b32`
- `ntdll!DbgPrint` at `0x180006d1c`
- `ntdll!DbgPrint` at `0x180006b32`
- `ntdll!DbgPrint` at `0x180006d1c`
- `ntdll!RtlNtStatusToDosError` at `0x180006d8f`
- `ntdll!RtlNtStatusToDosError` at `0x180006d8f`
- `ntdll!RtlInitializeResource` at `0x180006b7d`
- `ntdll!RtlInitializeResource` at `0x180006b7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006b15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006bb5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006b15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006bb5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006cba`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006cba`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180006b62`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180006b62`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180006b9d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180006b9d`
- `RPCRT4!RpcServerRegisterIfEx` at `0x180006cfb`
- `RPCRT4!RpcServerRegisterIfEx` at `0x180006cfb`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x180006ca7`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x180006ca7`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180006c7b`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180006c7b`
- `api-ms-win-service-private-l1-1-0!I_ScSetServiceBitsW` at `0x180006d7d`
- `api-ms-win-service-private-l1-1-0!I_ScSetServiceBitsW` at `0x180006d7d`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180006afd`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180006afd`

## string_xrefs

- `0x180006b52`: `WKSSVC failed with WsUpdateStatus %x\n`
- `0x180006b25`: `WKSSVC failed with RegisterServiceCtrlHandler %x\n`
- `0x180006c5d`: `WKSSVC failed with WsCreateApiStructures %x\n`

## pseudocode

```c
DWORD WsInitializeWorkstation()
{
  __int64 LastError; // rbx
  __int64 v1; // rdx
  const CHAR *v2; // rcx
  DWORD result; // eax
  unsigned int updated; // eax
  unsigned int v5; // eax
  unsigned int v6; // eax
  unsigned int v7; // eax
  unsigned int ApiStructures; // eax
  RPC_STATUS v9; // ebx
  RPC_STATUS v10; // edi
  ULONG v11; // eax
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+40h] [rbp+8h] BYREF

  SecurityDescriptor = 0;
  WsGlobalData.dwServiceType = 48;
  *(_QWORD *)&WsGlobalData.dwCurrentState = 2;
  WsGlobalData.dwCheckPoint = 1;
  WsGlobalData.dwWaitHint = 90000;
  *(_QWORD *)&WsGlobalData.dwWin32ExitCode = 0;
  hServiceStatus = RegisterServiceCtrlHandlerExW(L"LanmanWorkstation", WkstaControlHandlerEx, 0);
  if ( !hServiceStatus )
  {
    LastError = GetLastError();
    v1 = LastError;
    v2 = "WKSSVC failed with RegisterServiceCtrlHandler %x\n";
LABEL_3:
    WsInitializeStatusError = LastError;
    DbgPrint(v2, v1);
    return LastError;
  }
  updated = WsUpdateStatus();
  LODWORD(LastError) = updated;
  if ( updated )
  {
    v1 = updated;
    v2 = "WKSSVC failed with WsUpdateStatus %x\n";
    goto LABEL_3;
  }
  InitializeCriticalSection(&WsWorkerCriticalSection);
  WsWorkerCriticalSectionInitialized = 1;
  RtlInitializeResource(&WsInfo);
  WsInitState |= 0x80u;
  hHandle = CreateEventW(0, 1, 0, 0);
  if ( !hHandle )
    goto LABEL_7;
  WsInitState |= 1u;
  v5 = WsInitializeLsa();
  LODWORD(LastError) = v5;
  if ( v5 )
  {
    v1 = v5;
    v2 = "WKSSVC failed with WsInitializeLsa %x\n";
    goto LABEL_3;
  }
  WsInitState |= 0x20u;
  v6 = WsInitializeRedirector();
  LODWORD(LastError) = v6;
  if ( v6 )
  {
    v1 = v6;
    v2 = "WKSSVC failed with WsInitializeRedirector %x\n";
    goto LABEL_3;
  }
  WsInitState |= 2u;
  ++WsGlobalData.dwCheckPoint;
  WsUpdateStatus();
  ++WsGlobalData.dwCheckPoint;
  WsUpdateStatus();
  v7 = WsAddDomains();
  LODWORD(LastError) = v7;
  if ( v7 )
  {
    v1 = v7;
    v2 = "WKSSVC failed with WsAddDomains %x\n";
    goto LABEL_3;
  }
  ++WsGlobalData.dwCheckPoint;
  WsUpdateStatus();
  ApiStructures = WsCreateApiStructures();
  LODWORD(LastError) = ApiStructures;
  if ( ApiStructures )
  {
    v1 = ApiStructures;
    v2 = "WKSSVC failed with WsCreateApiStructures %x\n";
    goto LABEL_3;
  }
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
         L"O:NSG:NSD:(A;;0x12019B;;;AN)(A;;0x12019B;;;WD)(A;;0x1F01FF;;;SY)(A;;0x1F01FF;;;NS)S:(ML;;NW;;;LW)",
         1u,
         &SecurityDescriptor,
         0) )
  {
    v9 = RpcServerUseProtseqEpW((RPC_WSTR)L"ncacn_np", 0xAu, (RPC_WSTR)L"\\PIPE\\wkssvc", SecurityDescriptor);
    LocalFree(SecurityDescriptor);
    v10 = 0;
    if ( v9 != 1740 )
      v10 = v9;
    if ( v10 || (v10 = RpcServerRegisterIfEx(qword_180039060, 0, 0, 0x91u, 0x4D2u, WsRpcSecurityCallback_Old)) != 0 )
    {
      WsInitializeStatusError = v10;
      DbgPrint("WKSSVC failed with StartRpcServer %x\n", v10);
      return v10;
    }
    else
    {
      WsInitState |= 8u;
      if ( !(unsigned int)StartDfscRpc() )
        WsInitState |= 0x100u;
      v11 = WsInitializeDfs();
      LODWORD(LastError) = v11;
      if ( v11 )
      {
        v1 = v11;
        v2 = "WKSSVC failed with WsInitializeDfs %x\n";
        goto LABEL_3;
      }
      WsInitState |= 0x40u;
      I_ScSetServiceBitsW(hServiceStatus, 1, 1);
      return 0;
    }
  }
  else
  {
LABEL_7:
    result = GetLastError();
    WsInitializeStatusError = result;
  }
  return result;
}

```

## disassembly

```asm
0x180006a98  mov     rax, rsp
0x180006a9b  mov     [rax+10h], rbx
0x180006a9f  mov     [rax+18h], rdi
0x180006aa3  mov     [rax+8], rcx
0x180006aa7  push    r14
0x180006aa9  sub     rsp, 30h
0x180006aad  mov     qword ptr [rax+8], 0
0x180006ab5  mov     cs:WsGlobalData.dwServiceType, 30h ; '0'
0x180006abf  mov     qword ptr cs:WsGlobalData.dwCurrentState, 2
0x180006aca  mov     r14d, 1
0x180006ad0  mov     cs:WsGlobalData.dwCheckPoint, r14d
0x180006ad7  mov     cs:WsGlobalData.dwWaitHint, 15F90h
0x180006ae1  mov     qword ptr cs:WsGlobalData.dwWin32ExitCode, 0
0x180006aec  xor     r8d, r8d; lpContext
0x180006aef  lea     rdx, WkstaControlHandlerEx; lpHandlerProc
0x180006af6  lea     rcx, aLanmanworkstat; "LanmanWorkstation"
0x180006afd  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x180006b04  nop     dword ptr [rax+rax+00h]
0x180006b09  mov     cs:hServiceStatus, rax
0x180006b10  test    rax, rax
0x180006b13  jnz     short loc_180006B45
0x180006b15  call    cs:__imp_GetLastError
0x180006b1c  nop     dword ptr [rax+rax+00h]
0x180006b21  mov     ebx, eax
0x180006b23  mov     edx, eax
0x180006b25  lea     rcx, aWkssvcFailedWi; "WKSSVC failed with RegisterServiceCtrlH"...
0x180006b2c  mov     cs:WsInitializeStatusError, ebx
0x180006b32  call    cs:__imp_DbgPrint
0x180006b39  nop     dword ptr [rax+rax+00h]
0x180006b3e  mov     eax, ebx
0x180006b40  jmp     loc_180006DA2
0x180006b45  call    WsUpdateStatus
0x180006b4a  mov     ebx, eax
0x180006b4c  test    eax, eax
0x180006b4e  jz      short loc_180006B5B
0x180006b50  mov     edx, eax
0x180006b52  lea     rcx, aWkssvcFailedWi_4; "WKSSVC failed with WsUpdateStatus %x\n"
0x180006b59  jmp     short loc_180006B2C
0x180006b5b  lea     rcx, WsWorkerCriticalSection; lpCriticalSection
0x180006b62  call    cs:__imp_InitializeCriticalSection
0x180006b69  nop     dword ptr [rax+rax+00h]
0x180006b6e  nop
0x180006b6f  mov     cs:WsWorkerCriticalSectionInitialized, r14d
0x180006b76  lea     rcx, WsInfo; Resource
0x180006b7d  call    cs:__imp_RtlInitializeResource
0x180006b84  nop     dword ptr [rax+rax+00h]
0x180006b89  nop
0x180006b8a  bts     cs:WsInitState, 7
0x180006b92  xor     r9d, r9d; lpName
0x180006b95  xor     r8d, r8d; bInitialState
0x180006b98  mov     edx, r14d; bManualReset
0x180006b9b  xor     ecx, ecx; lpEventAttributes
0x180006b9d  call    cs:__imp_CreateEventW
0x180006ba4  nop     dword ptr [rax+rax+00h]
0x180006ba9  mov     cs:hHandle, rax
0x180006bb0  test    rax, rax
0x180006bb3  jnz     short loc_180006BCC
0x180006bb5  call    cs:__imp_GetLastError
0x180006bbc  nop     dword ptr [rax+rax+00h]
0x180006bc1  mov     cs:WsInitializeStatusError, eax
0x180006bc7  jmp     loc_180006DA2
0x180006bcc  or      cs:WsInitState, r14d
0x180006bd3  call    WsInitializeLsa
0x180006bd8  mov     ebx, eax
0x180006bda  test    eax, eax
0x180006bdc  jz      short loc_180006BEC
0x180006bde  mov     edx, eax
0x180006be0  lea     rcx, aWkssvcFailedWi_2; "WKSSVC failed with WsInitializeLsa %x\n"
0x180006be7  jmp     loc_180006B2C
0x180006bec  or      cs:WsInitState, 20h
0x180006bf3  call    WsInitializeRedirector
0x180006bf8  mov     ebx, eax
0x180006bfa  test    eax, eax
0x180006bfc  jz      short loc_180006C0C
0x180006bfe  mov     edx, eax
0x180006c00  lea     rcx, aWkssvcFailedWi_1; "WKSSVC failed with WsInitializeRedirect"...
0x180006c07  jmp     loc_180006B2C
0x180006c0c  or      cs:WsInitState, 2
0x180006c13  add     cs:WsGlobalData.dwCheckPoint, r14d
0x180006c1a  call    WsUpdateStatus
0x180006c1f  add     cs:WsGlobalData.dwCheckPoint, r14d
0x180006c26  call    WsUpdateStatus
0x180006c2b  call    WsAddDomains
0x180006c30  mov     ebx, eax
0x180006c32  test    eax, eax
0x180006c34  jz      short loc_180006C44
0x180006c36  mov     edx, eax
0x180006c38  lea     rcx, aWkssvcFailedWi_3; "WKSSVC failed with WsAddDomains %x\n"
0x180006c3f  jmp     loc_180006B2C
0x180006c44  add     cs:WsGlobalData.dwCheckPoint, r14d
0x180006c4b  call    WsUpdateStatus
0x180006c50  call    WsCreateApiStructures
0x180006c55  mov     ebx, eax
0x180006c57  test    eax, eax
0x180006c59  jz      short loc_180006C69
0x180006c5b  mov     edx, eax
0x180006c5d  lea     rcx, aWkssvcFailedWi_6; "WKSSVC failed with WsCreateApiStructure"...
0x180006c64  jmp     loc_180006B2C
0x180006c69  xor     r9d, r9d; SecurityDescriptorSize
0x180006c6c  lea     r8, [rsp+38h+SecurityDescriptor]; SecurityDescriptor
0x180006c71  mov     edx, r14d; StringSDRevision
0x180006c74  lea     rcx, StringSecurityDescriptor; "O:NSG:NSD:(A;;0x12019B;;;AN)(A;;0x12019"...
0x180006c7b  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180006c82  nop     dword ptr [rax+rax+00h]
0x180006c87  test    eax, eax
0x180006c89  jz      loc_180006BB5
0x180006c8f  mov     r9, [rsp+38h+SecurityDescriptor]; SecurityDescriptor
0x180006c94  lea     r8, Endpoint; "\\PIPE\\wkssvc"
0x180006c9b  mov     edx, 0Ah; MaxCalls
0x180006ca0  lea     rcx, Protseq; "ncacn_np"
0x180006ca7  call    cs:__imp_RpcServerUseProtseqEpW
0x180006cae  nop     dword ptr [rax+rax+00h]
0x180006cb3  mov     ebx, eax
0x180006cb5  mov     rcx, [rsp+38h+SecurityDescriptor]; hMem
0x180006cba  call    cs:__imp_LocalFree
0x180006cc1  nop     dword ptr [rax+rax+00h]
0x180006cc6  xor     edi, edi
0x180006cc8  cmp     ebx, 6CCh
0x180006cce  cmovnz  edi, ebx
0x180006cd1  test    edi, edi
0x180006cd3  jnz     short loc_180006D0D
0x180006cd5  lea     rax, WsRpcSecurityCallback_Old
0x180006cdc  mov     [rsp+38h+IfCallback], rax; IfCallback
0x180006ce1  mov     [rsp+38h+MaxCalls], 4D2h; MaxCalls
0x180006ce9  mov     r9d, 91h; Flags
0x180006cef  xor     r8d, r8d; MgrEpv
0x180006cf2  xor     edx, edx; MgrTypeUuid
0x180006cf4  lea     rcx, qword_180039060; IfSpec
0x180006cfb  call    cs:__imp_RpcServerRegisterIfEx
0x180006d02  nop     dword ptr [rax+rax+00h]
0x180006d07  mov     edi, eax
0x180006d09  test    eax, eax
0x180006d0b  jz      short loc_180006D2C
0x180006d0d  mov     cs:WsInitializeStatusError, edi
0x180006d13  mov     edx, edi
0x180006d15  lea     rcx, aWkssvcFailedWi_0; "WKSSVC failed with StartRpcServer %x\n"
0x180006d1c  call    cs:__imp_DbgPrint
0x180006d23  nop     dword ptr [rax+rax+00h]
0x180006d28  mov     eax, edi
0x180006d2a  jmp     short loc_180006DA2
0x180006d2c  or      cs:WsInitState, 8
0x180006d33  call    StartDfscRpc
0x180006d38  test    eax, eax
0x180006d3a  jnz     short loc_180006D44
0x180006d3c  bts     cs:WsInitState, 8
0x180006d44  call    WsInitializeDfs
0x180006d49  mov     ebx, eax
0x180006d4b  test    eax, eax
0x180006d4d  jz      short loc_180006D5D
0x180006d4f  mov     edx, eax
0x180006d51  lea     rcx, aWkssvcFailedWi_5; "WKSSVC failed with WsInitializeDfs %x\n"
0x180006d58  jmp     loc_180006B2C
0x180006d5d  or      cs:WsInitState, 40h
0x180006d64  mov     qword ptr [rsp+38h+MaxCalls], 0
0x180006d6d  mov     r9d, r14d
0x180006d70  mov     r8d, r14d
0x180006d73  mov     edx, r14d
0x180006d76  mov     rcx, cs:hServiceStatus
0x180006d7d  call    cs:__imp_I_ScSetServiceBitsW
0x180006d84  nop     dword ptr [rax+rax+00h]
0x180006d89  xor     eax, eax
0x180006d8b  jmp     short loc_180006DA2
0x180006d8d  mov     ecx, eax; Status
0x180006d8f  call    cs:__imp_RtlNtStatusToDosError
0x180006d96  nop     dword ptr [rax+rax+00h]
0x180006d9b  jmp     short loc_180006DA2
0x180006d9d  mov     eax, 8
0x180006da2  mov     rbx, [rsp+38h+arg_8]
0x180006da7  mov     rdi, [rsp+38h+arg_10]
0x180006dac  add     rsp, 30h
0x180006db0  pop     r14
0x180006db2  retn
```
