# StartDfscRpc

- ea: `0x180006ca0`
- end: `0x180006dfb`
- name: `StartDfscRpc`
- size: `347`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800065c0`

## callees

- `0x180006ca0`

## import_xrefs

- `ntdll!DbgPrint` at `0x180006d61`
- `ntdll!DbgPrint` at `0x180006d8a`
- `ntdll!DbgPrint` at `0x180006d9c`
- `ntdll!DbgPrint` at `0x180006de3`
- `ntdll!DbgPrint` at `0x180006d61`
- `ntdll!DbgPrint` at `0x180006d8a`
- `ntdll!DbgPrint` at `0x180006d9c`
- `ntdll!DbgPrint` at `0x180006de3`
- `RPCRT4!RpcServerUseProtseqW` at `0x180006cc6`
- `RPCRT4!RpcServerUseProtseqW` at `0x180006cc6`
- `RPCRT4!RpcServerRegisterIfEx` at `0x180006d02`
- `RPCRT4!RpcServerRegisterIfEx` at `0x180006d02`
- `RPCRT4!RpcEpRegisterW` at `0x180006d43`
- `RPCRT4!RpcEpRegisterW` at `0x180006d43`
- `RPCRT4!RpcServerInqBindings` at `0x180006d16`
- `RPCRT4!RpcServerInqBindings` at `0x180006d16`
- `RPCRT4!RpcBindingVectorFree` at `0x180006d74`
- `RPCRT4!RpcBindingVectorFree` at `0x180006daf`
- `RPCRT4!RpcBindingVectorFree` at `0x180006d74`
- `RPCRT4!RpcBindingVectorFree` at `0x180006daf`
- `RPCRT4!RpcServerUnregisterIf` at `0x180006dd0`
- `RPCRT4!RpcServerUnregisterIf` at `0x180006dd0`

## string_xrefs

- `0x180006d32`: `DfsDs service`
- `0x180006d93`: `Failed to start DfsDsService with status:%x, error:%x\n`

## pseudocode

```c
__int64 StartDfscRpc()
{
  RPC_STATUS v0; // eax
  unsigned int v1; // ebx
  char v2; // di
  unsigned int v3; // eax
  unsigned int v4; // eax
  RPC_STATUS v6; // eax
  RPC_BINDING_VECTOR *BindingVector; // [rsp+40h] [rbp+8h] BYREF

  BindingVector = 0;
  v0 = RpcServerUseProtseqW((RPC_WSTR)L"ncalrpc", 0xAu, 0);
  v1 = 0;
  if ( v0 != 1740 )
    v1 = v0;
  if ( v1
    || (v1 = RpcServerRegisterIfEx(qword_180035000, 0, 0, 0x31u, 0x4D2u, (RPC_IF_CALLBACK_FN *)DfsDsRpcSecurityCallback)) != 0 )
  {
    v2 = 0;
    DbgPrint("StartDfsDsRpc: RpcServerRegisterIfEx failed: %X\n", v1);
    goto LABEL_13;
  }
  v2 = 1;
  v3 = RpcServerInqBindings(&BindingVector);
  v1 = v3;
  if ( v3 )
  {
    DbgPrint("StartDfsDsRpc: RpcServerInqBindings failed: %X\n", v3);
LABEL_13:
    DbgPrint("Failed to start DfsDsService with status:%x, error:%x\n", 0, v1);
    if ( BindingVector )
    {
      RpcBindingVectorFree(&BindingVector);
      BindingVector = 0;
    }
    if ( v2 )
    {
      v6 = RpcServerUnregisterIf(qword_180035000, 0, 1u);
      if ( v6 )
        DbgPrint("Failed to unregister rpc interface with status %x\n", v6);
    }
    return v1;
  }
  v4 = RpcEpRegisterW(qword_180035000, BindingVector, 0, (RPC_WSTR)L"DfsDs service");
  v1 = v4;
  if ( v4 )
  {
    DbgPrint("StartDfsDsRpc: RpcEpRegister failed: %X\n", v4);
    goto LABEL_13;
  }
  DbgPrint("DfsDs RPC server started.\n");
  if ( BindingVector )
    RpcBindingVectorFree(&BindingVector);
  return 0;
}

```

## disassembly

```asm
0x180006ca0  mov     [rsp+arg_8], rbx
0x180006ca5  mov     [rsp+arg_10], rsi
0x180006caa  push    rdi
0x180006cab  sub     rsp, 30h
0x180006caf  xor     r8d, r8d; SecurityDescriptor
0x180006cb2  mov     [rsp+38h+BindingVector], 0
0x180006cbb  lea     rcx, String2; "ncalrpc"
0x180006cc2  lea     edx, [r8+0Ah]; MaxCalls
0x180006cc6  call    cs:__imp_RpcServerUseProtseqW
0x180006ccc  xor     ebx, ebx
0x180006cce  cmp     eax, 6CCh
0x180006cd3  cmovnz  ebx, eax
0x180006cd6  test    ebx, ebx
0x180006cd8  jnz     loc_180006D7E
0x180006cde  lea     rax, DfsDsRpcSecurityCallback
0x180006ce5  xor     r8d, r8d; MgrEpv
0x180006ce8  mov     [rsp+38h+IfCallback], rax; IfCallback
0x180006ced  lea     r9d, [rbx+31h]; Flags
0x180006cf1  xor     edx, edx; MgrTypeUuid
0x180006cf3  mov     [rsp+38h+MaxCalls], 4D2h; MaxCalls
0x180006cfb  lea     rcx, qword_180035000; IfSpec
0x180006d02  call    cs:__imp_RpcServerRegisterIfEx
0x180006d08  mov     ebx, eax
0x180006d0a  test    eax, eax
0x180006d0c  jnz     short loc_180006D7E
0x180006d0e  lea     rcx, [rsp+38h+BindingVector]; BindingVector
0x180006d13  mov     dil, 1
0x180006d16  call    cs:__imp_RpcServerInqBindings
0x180006d1c  mov     ebx, eax
0x180006d1e  test    eax, eax
0x180006d20  jz      short loc_180006D2D
0x180006d22  mov     edx, eax
0x180006d24  lea     rcx, aStartdfsdsrpcR; "StartDfsDsRpc: RpcServerInqBindings fai"...
0x180006d2b  jmp     short loc_180006D8A
0x180006d2d  mov     rdx, [rsp+38h+BindingVector]; BindingVector
0x180006d32  lea     r9, Annotation; "DfsDs service"
0x180006d39  xor     r8d, r8d; UuidVector
0x180006d3c  lea     rcx, qword_180035000; IfSpec
0x180006d43  call    cs:__imp_RpcEpRegisterW
0x180006d49  mov     ebx, eax
0x180006d4b  test    eax, eax
0x180006d4d  jz      short loc_180006D5A
0x180006d4f  mov     edx, eax
0x180006d51  lea     rcx, aStartdfsdsrpcR_0; "StartDfsDsRpc: RpcEpRegister failed: %X"...
0x180006d58  jmp     short loc_180006D8A
0x180006d5a  lea     rcx, aDfsdsRpcServer; "DfsDs RPC server started.\n"
0x180006d61  call    cs:__imp_DbgPrint
0x180006d67  cmp     [rsp+38h+BindingVector], 0
0x180006d6d  jz      short loc_180006D7A
0x180006d6f  lea     rcx, [rsp+38h+BindingVector]; BindingVector
0x180006d74  call    cs:__imp_RpcBindingVectorFree
0x180006d7a  xor     eax, eax
0x180006d7c  jmp     short loc_180006DEB
0x180006d7e  xor     dil, dil
0x180006d81  lea     rcx, aStartdfsdsrpcR_1; "StartDfsDsRpc: RpcServerRegisterIfEx fa"...
0x180006d88  mov     edx, ebx
0x180006d8a  call    cs:__imp_DbgPrint
0x180006d90  mov     r8d, ebx
0x180006d93  lea     rcx, aFailedToStartD; "Failed to start DfsDsService with statu"...
0x180006d9a  xor     edx, edx
0x180006d9c  call    cs:__imp_DbgPrint
0x180006da2  cmp     [rsp+38h+BindingVector], 0
0x180006da8  jz      short loc_180006DBE
0x180006daa  lea     rcx, [rsp+38h+BindingVector]; BindingVector
0x180006daf  call    cs:__imp_RpcBindingVectorFree
0x180006db5  mov     [rsp+38h+BindingVector], 0
0x180006dbe  test    dil, dil
0x180006dc1  jz      short loc_180006DE9
0x180006dc3  xor     edx, edx; MgrTypeUuid
0x180006dc5  lea     rcx, qword_180035000; IfSpec
0x180006dcc  lea     r8d, [rdx+1]; WaitForCallsToComplete
0x180006dd0  call    cs:__imp_RpcServerUnregisterIf
0x180006dd6  test    eax, eax
0x180006dd8  jz      short loc_180006DE9
0x180006dda  mov     edx, eax
0x180006ddc  lea     rcx, aFailedToUnregi; "Failed to unregister rpc interface with"...
0x180006de3  call    cs:__imp_DbgPrint
0x180006de9  mov     eax, ebx
0x180006deb  mov     rbx, [rsp+38h+arg_8]
0x180006df0  mov     rsi, [rsp+38h+arg_10]
0x180006df5  add     rsp, 30h
0x180006df9  pop     rdi
0x180006dfa  retn
```
