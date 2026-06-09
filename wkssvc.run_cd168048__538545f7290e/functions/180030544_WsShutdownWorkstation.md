# WsShutdownWorkstation

- ea: `0x180030544`
- end: `0x1800306fc`
- name: `WsShutdownWorkstation`
- size: `440`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180030710`

## callees

- `0x180006dbc`
- `0x180027f74`
- `0x18002cac8`
- `0x18002e6ac`
- `0x18002ee64`
- `0x18002fca0`
- `0x180030544`

## import_xrefs

- `ntdll!DbgPrint` at `0x1800305a3`
- `ntdll!DbgPrint` at `0x1800305a3`
- `ntdll!RtlDeleteSecurityObject` at `0x1800305da`
- `ntdll!RtlDeleteSecurityObject` at `0x1800305ed`
- `ntdll!RtlDeleteSecurityObject` at `0x180030600`
- `ntdll!RtlDeleteSecurityObject` at `0x1800305da`
- `ntdll!RtlDeleteSecurityObject` at `0x1800305ed`
- `ntdll!RtlDeleteSecurityObject` at `0x180030600`
- `ntdll!RtlDeleteResource` at `0x180030623`
- `ntdll!RtlDeleteResource` at `0x180030623`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030653`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030653`
- `RPCRT4!RpcServerUnregisterIf` at `0x180030588`
- `RPCRT4!RpcServerUnregisterIf` at `0x180030588`
- `SspiCli!LsaDeregisterLogonProcess` at `0x18003063b`
- `SspiCli!LsaDeregisterLogonProcess` at `0x18003063b`
- `api-ms-win-service-private-l1-1-0!I_ScSetServiceBitsW` at `0x180030680`
- `api-ms-win-service-private-l1-1-0!I_ScSetServiceBitsW` at `0x180030680`

## pseudocode

```c
__int64 WsShutdownWorkstation()
{
  int v0; // ebx
  RPC_STATUS v1; // esi
  DWORD v2; // edi
  RPC_STATUS v3; // eax

  v0 = WsInitState;
  v1 = 0;
  v2 = WsInitializeStatusError;
  ++WsGlobalData.dwCheckPoint;
  WsUpdateStatus();
  if ( (v0 & 0x40) != 0 )
    WsShutdownDfs();
  if ( (v0 & 8) != 0 )
  {
    v3 = RpcServerUnregisterIf(qword_180039060, 0, 1u);
    v1 = v3;
    if ( v3 )
      DbgPrint("WKSSVC failed to unregister rpc interface with status %x\n", v3);
  }
  if ( (v0 & 0x100) != 0 )
    StopDfscRPC();
  if ( (v0 & 0x30000000) != 0 )
  {
    if ( (v0 & 0x20000000) != 0 )
      WsDestroyUseStructures();
    if ( (v0 & 0x10000000) != 0 )
    {
      RtlDeleteSecurityObject(&ConfigurationInfoSd);
      RtlDeleteSecurityObject(&MessageSendSd);
      RtlDeleteSecurityObject(&NetApiSd);
    }
  }
  if ( (v0 & 2) != 0 )
    v1 = WsShutdownRedirector();
  if ( (v0 & 0x80u) != 0 )
    RtlDeleteResource(&WsInfo);
  if ( (v0 & 0x20) != 0 )
    LsaDeregisterLogonProcess(LsaHandle);
  if ( (v0 & 1) != 0 )
    CloseHandle(hHandle);
  WJShutdownWorkplaceJoin();
  I_ScSetServiceBitsW(hServiceStatus, 1, 0);
  WsGlobalData.dwCurrentState = 1;
  WsGlobalData.dwControlsAccepted = 0;
  if ( v2 )
  {
    WsGlobalData.dwWin32ExitCode = 1066;
    if ( v2 - 2100 <= 0xED7 )
    {
LABEL_26:
      WsGlobalData.dwServiceSpecificExitCode = v2;
      goto LABEL_27;
    }
LABEL_25:
    WsGlobalData.dwWin32ExitCode = v2;
    goto LABEL_26;
  }
  v2 = 1794;
  if ( v1 == 1794 )
    goto LABEL_25;
  *(_QWORD *)&WsGlobalData.dwWin32ExitCode = 0;
LABEL_27:
  *(_QWORD *)&WsGlobalData.dwCheckPoint = 0;
  return WsUpdateStatus();
}

```

## disassembly

```asm
0x180030544  mov     [rsp+arg_0], rbx
0x180030549  mov     [rsp+arg_8], rsi
0x18003054e  push    rdi
0x18003054f  sub     rsp, 30h
0x180030553  mov     ebx, cs:WsInitState
0x180030559  xor     esi, esi
0x18003055b  mov     edi, cs:WsInitializeStatusError
0x180030561  inc     cs:WsGlobalData.dwCheckPoint
0x180030567  call    WsUpdateStatus
0x18003056c  test    bl, 40h
0x18003056f  jz      short loc_180030576
0x180030571  call    WsShutdownDfs
0x180030576  test    bl, 8
0x180030579  jz      short loc_1800305AF
0x18003057b  xor     edx, edx; MgrTypeUuid
0x18003057d  lea     rcx, qword_180039060; IfSpec
0x180030584  lea     r8d, [rdx+1]; WaitForCallsToComplete
0x180030588  call    cs:__imp_RpcServerUnregisterIf
0x18003058f  nop     dword ptr [rax+rax+00h]
0x180030594  mov     esi, eax
0x180030596  test    eax, eax
0x180030598  jz      short loc_1800305AF
0x18003059a  mov     edx, eax
0x18003059c  lea     rcx, aWkssvcFailedTo; "WKSSVC failed to unregister rpc interfa"...
0x1800305a3  call    cs:__imp_DbgPrint
0x1800305aa  nop     dword ptr [rax+rax+00h]
0x1800305af  bt      ebx, 8
0x1800305b3  jnb     short loc_1800305BA
0x1800305b5  call    StopDfscRPC
0x1800305ba  test    ebx, 30000000h
0x1800305c0  jz      short loc_18003060C
0x1800305c2  bt      ebx, 1Dh
0x1800305c6  jnb     short loc_1800305CD
0x1800305c8  call    WsDestroyUseStructures
0x1800305cd  bt      ebx, 1Ch
0x1800305d1  jnb     short loc_18003060C
0x1800305d3  lea     rcx, ConfigurationInfoSd; ObjectDescriptor
0x1800305da  call    cs:__imp_RtlDeleteSecurityObject
0x1800305e1  nop     dword ptr [rax+rax+00h]
0x1800305e6  lea     rcx, MessageSendSd; ObjectDescriptor
0x1800305ed  call    cs:__imp_RtlDeleteSecurityObject
0x1800305f4  nop     dword ptr [rax+rax+00h]
0x1800305f9  lea     rcx, NetApiSd; ObjectDescriptor
0x180030600  call    cs:__imp_RtlDeleteSecurityObject
0x180030607  nop     dword ptr [rax+rax+00h]
0x18003060c  test    bl, 2
0x18003060f  jz      short loc_180030618
0x180030611  call    WsShutdownRedirector
0x180030616  mov     esi, eax
0x180030618  test    bl, bl
0x18003061a  jns     short loc_18003062F
0x18003061c  lea     rcx, WsInfo; Resource
0x180030623  call    cs:__imp_RtlDeleteResource
0x18003062a  nop     dword ptr [rax+rax+00h]
0x18003062f  test    bl, 20h
0x180030632  jz      short loc_180030647
0x180030634  mov     rcx, cs:LsaHandle; LsaHandle
0x18003063b  call    cs:__imp_LsaDeregisterLogonProcess
0x180030642  nop     dword ptr [rax+rax+00h]
0x180030647  test    bl, 1
0x18003064a  jz      short loc_18003065F
0x18003064c  mov     rcx, cs:hHandle; hObject
0x180030653  call    cs:__imp_CloseHandle
0x18003065a  nop     dword ptr [rax+rax+00h]
0x18003065f  call    WJShutdownWorkplaceJoin
0x180030664  mov     rcx, cs:hServiceStatus
0x18003066b  mov     r9d, 1
0x180030671  mov     edx, r9d
0x180030674  mov     [rsp+38h+var_18], 0
0x18003067d  xor     r8d, r8d
0x180030680  call    cs:__imp_I_ScSetServiceBitsW
0x180030687  nop     dword ptr [rax+rax+00h]
0x18003068c  mov     cs:WsGlobalData.dwCurrentState, 1
0x180030696  mov     cs:WsGlobalData.dwControlsAccepted, 0
0x1800306a0  test    edi, edi
0x1800306a2  jnz     short loc_1800306BA
0x1800306a4  mov     edi, 702h
0x1800306a9  cmp     esi, edi
0x1800306ab  jz      short loc_1800306D1
0x1800306ad  mov     qword ptr cs:WsGlobalData.dwWin32ExitCode, 0
0x1800306b8  jmp     short loc_1800306DD
0x1800306ba  lea     eax, [rdi-834h]
0x1800306c0  mov     cs:WsGlobalData.dwWin32ExitCode, 42Ah
0x1800306ca  cmp     eax, 0ED7h
0x1800306cf  jbe     short loc_1800306D7
0x1800306d1  mov     cs:WsGlobalData.dwWin32ExitCode, edi
0x1800306d7  mov     cs:WsGlobalData.dwServiceSpecificExitCode, edi
0x1800306dd  mov     qword ptr cs:WsGlobalData.dwCheckPoint, 0
0x1800306e8  mov     rbx, [rsp+38h+arg_0]
0x1800306ed  mov     rsi, [rsp+38h+arg_8]
0x1800306f2  add     rsp, 30h
0x1800306f6  pop     rdi
0x1800306f7  jmp     WsUpdateStatus
```
