# WsShutdownWorkstation

- ea: `0x18002db4c`
- end: `0x18002dd19`
- name: `WsShutdownWorkstation`
- size: `461`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18002dd20`

## callees

- `0x180006890`
- `0x18002a54c`
- `0x18002bed8`
- `0x18002c59c`
- `0x18002d3d0`
- `0x18002db4c`

## import_xrefs

- `ntdll!DbgPrint` at `0x18002dba4`
- `ntdll!DbgPrint` at `0x18002dc07`
- `ntdll!DbgPrint` at `0x18002dba4`
- `ntdll!DbgPrint` at `0x18002dc07`
- `ntdll!RtlDeleteSecurityObject` at `0x18002dc2d`
- `ntdll!RtlDeleteSecurityObject` at `0x18002dc3a`
- `ntdll!RtlDeleteSecurityObject` at `0x18002dc47`
- `ntdll!RtlDeleteSecurityObject` at `0x18002dc2d`
- `ntdll!RtlDeleteSecurityObject` at `0x18002dc3a`
- `ntdll!RtlDeleteSecurityObject` at `0x18002dc47`
- `ntdll!RtlDeleteResource` at `0x18002dc64`
- `ntdll!RtlDeleteResource` at `0x18002dc64`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002dc88`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002dc88`
- `RPCRT4!RpcEpUnregister` at `0x18002dbd7`
- `RPCRT4!RpcEpUnregister` at `0x18002dbd7`
- `RPCRT4!RpcServerInqBindings` at `0x18002dbbe`
- `RPCRT4!RpcServerInqBindings` at `0x18002dbbe`
- `RPCRT4!RpcBindingVectorFree` at `0x18002dbe2`
- `RPCRT4!RpcBindingVectorFree` at `0x18002dbe2`
- `RPCRT4!RpcServerUnregisterIf` at `0x18002db8f`
- `RPCRT4!RpcServerUnregisterIf` at `0x18002dbf4`
- `RPCRT4!RpcServerUnregisterIf` at `0x18002db8f`
- `RPCRT4!RpcServerUnregisterIf` at `0x18002dbf4`
- `SspiCli!LsaDeregisterLogonProcess` at `0x18002dc76`
- `SspiCli!LsaDeregisterLogonProcess` at `0x18002dc76`
- `api-ms-win-service-private-l1-1-0!I_ScSetServiceBitsW` at `0x18002dcac`
- `api-ms-win-service-private-l1-1-0!I_ScSetServiceBitsW` at `0x18002dcac`

## pseudocode

```c
__int64 WsShutdownWorkstation()
{
  int v0; // ebx
  RPC_STATUS v1; // esi
  DWORD v2; // edi
  RPC_STATUS v3; // eax
  RPC_STATUS v4; // eax
  RPC_BINDING_VECTOR *BindingVector; // [rsp+70h] [rbp+18h] BYREF

  v0 = WsInitState;
  v1 = 0;
  v2 = WsInitializeStatusError;
  ++WsGlobalData.dwCheckPoint;
  WsUpdateStatus();
  if ( (v0 & 0x40) != 0 )
    WsShutdownDfs();
  if ( (v0 & 8) != 0 )
  {
    v3 = RpcServerUnregisterIf(qword_180036060, 0, 1u);
    v1 = v3;
    if ( v3 )
      DbgPrint("WKSSVC failed to unregister rpc interface with status %x\n", v3);
  }
  if ( (v0 & 0x100) != 0 )
  {
    BindingVector = 0;
    if ( !RpcServerInqBindings(&BindingVector) )
    {
      RpcEpUnregister(qword_180035000, BindingVector, 0);
      RpcBindingVectorFree(&BindingVector);
    }
    v4 = RpcServerUnregisterIf(qword_180035000, 0, 1u);
    if ( v4 )
      DbgPrint("StopDfsDsRPC: Failed to unregister rpc interface with status %x\n", v4);
  }
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
  I_ScSetServiceBitsW(hServiceStatus, 1, 0, 1, 0);
  WsGlobalData.dwCurrentState = 1;
  WsGlobalData.dwControlsAccepted = 0;
  if ( v2 )
  {
    WsGlobalData.dwWin32ExitCode = 1066;
    if ( v2 - 2100 <= 0xED7 )
    {
LABEL_29:
      WsGlobalData.dwServiceSpecificExitCode = v2;
      goto LABEL_30;
    }
LABEL_28:
    WsGlobalData.dwWin32ExitCode = v2;
    goto LABEL_29;
  }
  v2 = 1794;
  if ( v1 == 1794 )
    goto LABEL_28;
  *(_QWORD *)&WsGlobalData.dwWin32ExitCode = 0;
LABEL_30:
  *(_QWORD *)&WsGlobalData.dwCheckPoint = 0;
  return WsUpdateStatus();
}

```

## disassembly

```asm
0x18002db4c  push    rbx
0x18002db4e  push    rsi
0x18002db4f  push    rdi
0x18002db50  push    r14
0x18002db52  sub     rsp, 38h
0x18002db56  mov     ebx, cs:WsInitState
0x18002db5c  xor     esi, esi
0x18002db5e  mov     edi, cs:WsInitializeStatusError
0x18002db64  lea     r14d, [rsi+1]
0x18002db68  add     cs:WsGlobalData.dwCheckPoint, r14d
0x18002db6f  call    WsUpdateStatus
0x18002db74  test    bl, 40h
0x18002db77  jz      short loc_18002DB7E
0x18002db79  call    WsShutdownDfs
0x18002db7e  test    bl, 8
0x18002db81  jz      short loc_18002DBAA
0x18002db83  mov     r8d, r14d; WaitForCallsToComplete
0x18002db86  lea     rcx, qword_180036060; IfSpec
0x18002db8d  xor     edx, edx; MgrTypeUuid
0x18002db8f  call    cs:__imp_RpcServerUnregisterIf
0x18002db95  mov     esi, eax
0x18002db97  test    eax, eax
0x18002db99  jz      short loc_18002DBAA
0x18002db9b  mov     edx, eax
0x18002db9d  lea     rcx, aWkssvcFailedTo; "WKSSVC failed to unregister rpc interfa"...
0x18002dba4  call    cs:__imp_DbgPrint
0x18002dbaa  bt      ebx, 8
0x18002dbae  jnb     short loc_18002DC0D
0x18002dbb0  lea     rcx, [rsp+58h+BindingVector]; BindingVector
0x18002dbb5  mov     [rsp+58h+BindingVector], 0
0x18002dbbe  call    cs:__imp_RpcServerInqBindings
0x18002dbc4  test    eax, eax
0x18002dbc6  jnz     short loc_18002DBE8
0x18002dbc8  mov     rdx, [rsp+58h+BindingVector]; BindingVector
0x18002dbcd  lea     rcx, qword_180035000; IfSpec
0x18002dbd4  xor     r8d, r8d; UuidVector
0x18002dbd7  call    cs:__imp_RpcEpUnregister
0x18002dbdd  lea     rcx, [rsp+58h+BindingVector]; BindingVector
0x18002dbe2  call    cs:__imp_RpcBindingVectorFree
0x18002dbe8  mov     r8d, r14d; WaitForCallsToComplete
0x18002dbeb  lea     rcx, qword_180035000; IfSpec
0x18002dbf2  xor     edx, edx; MgrTypeUuid
0x18002dbf4  call    cs:__imp_RpcServerUnregisterIf
0x18002dbfa  test    eax, eax
0x18002dbfc  jz      short loc_18002DC0D
0x18002dbfe  mov     edx, eax
0x18002dc00  lea     rcx, aStopdfsdsrpcFa; "StopDfsDsRPC: Failed to unregister rpc "...
0x18002dc07  call    cs:__imp_DbgPrint
0x18002dc0d  test    ebx, 30000000h
0x18002dc13  jz      short loc_18002DC4D
0x18002dc15  bt      ebx, 1Dh
0x18002dc19  jnb     short loc_18002DC20
0x18002dc1b  call    WsDestroyUseStructures
0x18002dc20  bt      ebx, 1Ch
0x18002dc24  jnb     short loc_18002DC4D
0x18002dc26  lea     rcx, ConfigurationInfoSd; ObjectDescriptor
0x18002dc2d  call    cs:__imp_RtlDeleteSecurityObject
0x18002dc33  lea     rcx, MessageSendSd; ObjectDescriptor
0x18002dc3a  call    cs:__imp_RtlDeleteSecurityObject
0x18002dc40  lea     rcx, NetApiSd; ObjectDescriptor
0x18002dc47  call    cs:__imp_RtlDeleteSecurityObject
0x18002dc4d  test    bl, 2
0x18002dc50  jz      short loc_18002DC59
0x18002dc52  call    WsShutdownRedirector
0x18002dc57  mov     esi, eax
0x18002dc59  test    bl, bl
0x18002dc5b  jns     short loc_18002DC6A
0x18002dc5d  lea     rcx, WsInfo; Resource
0x18002dc64  call    cs:__imp_RtlDeleteResource
0x18002dc6a  test    bl, 20h
0x18002dc6d  jz      short loc_18002DC7C
0x18002dc6f  mov     rcx, cs:LsaHandle; LsaHandle
0x18002dc76  call    cs:__imp_LsaDeregisterLogonProcess
0x18002dc7c  test    r14b, bl
0x18002dc7f  jz      short loc_18002DC8E
0x18002dc81  mov     rcx, cs:hHandle; hObject
0x18002dc88  call    cs:__imp_CloseHandle
0x18002dc8e  call    WJShutdownWorkplaceJoin
0x18002dc93  mov     rcx, cs:hServiceStatus
0x18002dc9a  mov     r9d, r14d
0x18002dc9d  xor     r8d, r8d
0x18002dca0  mov     [rsp+58h+var_38], 0
0x18002dca9  mov     edx, r14d
0x18002dcac  call    cs:__imp_I_ScSetServiceBitsW
0x18002dcb2  mov     cs:WsGlobalData.dwCurrentState, r14d
0x18002dcb9  mov     cs:WsGlobalData.dwControlsAccepted, 0
0x18002dcc3  test    edi, edi
0x18002dcc5  jnz     short loc_18002DCDD
0x18002dcc7  mov     edi, 702h
0x18002dccc  cmp     esi, edi
0x18002dcce  jz      short loc_18002DCF4
0x18002dcd0  mov     qword ptr cs:WsGlobalData.dwWin32ExitCode, 0
0x18002dcdb  jmp     short loc_18002DD00
0x18002dcdd  lea     eax, [rdi-834h]
0x18002dce3  mov     cs:WsGlobalData.dwWin32ExitCode, 42Ah
0x18002dced  cmp     eax, 0ED7h
0x18002dcf2  jbe     short loc_18002DCFA
0x18002dcf4  mov     cs:WsGlobalData.dwWin32ExitCode, edi
0x18002dcfa  mov     cs:WsGlobalData.dwServiceSpecificExitCode, edi
0x18002dd00  mov     qword ptr cs:WsGlobalData.dwCheckPoint, 0
0x18002dd0b  add     rsp, 38h
0x18002dd0f  pop     r14
0x18002dd11  pop     rdi
0x18002dd12  pop     rsi
0x18002dd13  pop     rbx
0x18002dd14  jmp     WsUpdateStatus
```
