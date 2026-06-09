# StartDfscRpc

- ea: `0x180007290`
- end: `0x180007435`
- name: `StartDfscRpc`
- size: `421`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180006a98`

## callees

- `0x180007290`

## import_xrefs

- `ntdll!DbgPrint` at `0x18000736d`
- `ntdll!DbgPrint` at `0x1800073a5`
- `ntdll!DbgPrint` at `0x1800073bd`
- `ntdll!DbgPrint` at `0x180007416`
- `ntdll!DbgPrint` at `0x18000736d`
- `ntdll!DbgPrint` at `0x1800073a5`
- `ntdll!DbgPrint` at `0x1800073bd`
- `ntdll!DbgPrint` at `0x180007416`
- `RPCRT4!RpcServerUseProtseqW` at `0x1800072b6`
- `RPCRT4!RpcServerUseProtseqW` at `0x1800072b6`
- `RPCRT4!RpcServerRegisterIfEx` at `0x1800072f8`
- `RPCRT4!RpcServerRegisterIfEx` at `0x1800072f8`
- `RPCRT4!RpcEpRegisterW` at `0x180007349`
- `RPCRT4!RpcEpRegisterW` at `0x180007349`
- `RPCRT4!RpcServerInqBindings` at `0x180007316`
- `RPCRT4!RpcServerInqBindings` at `0x180007316`
- `RPCRT4!RpcBindingVectorFree` at `0x180007386`
- `RPCRT4!RpcBindingVectorFree` at `0x1800073d6`
- `RPCRT4!RpcBindingVectorFree` at `0x180007386`
- `RPCRT4!RpcBindingVectorFree` at `0x1800073d6`
- `RPCRT4!RpcServerUnregisterIf` at `0x1800073fd`
- `RPCRT4!RpcServerUnregisterIf` at `0x1800073fd`

## string_xrefs

- `0x180007338`: `DfsDs service`
- `0x1800073b4`: `Failed to start DfsDsService with status:%x, error:%x\n`

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
    || (v1 = RpcServerRegisterIfEx(qword_180038000, 0, 0, 0x31u, 0x4D2u, (RPC_IF_CALLBACK_FN *)DfsDsRpcSecurityCallback)) != 0 )
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
      v6 = RpcServerUnregisterIf(qword_180038000, 0, 1u);
      if ( v6 )
        DbgPrint("Failed to unregister rpc interface with status %x\n", v6);
    }
    return v1;
  }
  v4 = RpcEpRegisterW(qword_180038000, BindingVector, 0, (RPC_WSTR)L"DfsDs service");
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
0x180007290  mov     [rsp+arg_8], rbx
0x180007295  mov     [rsp+arg_10], rsi
0x18000729a  push    rdi
0x18000729b  sub     rsp, 30h
0x18000729f  xor     r8d, r8d; SecurityDescriptor
0x1800072a2  mov     [rsp+38h+BindingVector], 0
0x1800072ab  lea     rcx, String2; "ncalrpc"
0x1800072b2  lea     edx, [r8+0Ah]; MaxCalls
0x1800072b6  call    cs:__imp_RpcServerUseProtseqW
0x1800072bd  nop     dword ptr [rax+rax+00h]
0x1800072c2  xor     ebx, ebx
0x1800072c4  cmp     eax, 6CCh
0x1800072c9  cmovnz  ebx, eax
0x1800072cc  test    ebx, ebx
0x1800072ce  jnz     loc_180007399
0x1800072d4  lea     rax, DfsDsRpcSecurityCallback
0x1800072db  xor     r8d, r8d; MgrEpv
0x1800072de  mov     [rsp+38h+IfCallback], rax; IfCallback
0x1800072e3  lea     r9d, [rbx+31h]; Flags
0x1800072e7  xor     edx, edx; MgrTypeUuid
0x1800072e9  mov     [rsp+38h+MaxCalls], 4D2h; MaxCalls
0x1800072f1  lea     rcx, qword_180038000; IfSpec
0x1800072f8  call    cs:__imp_RpcServerRegisterIfEx
0x1800072ff  nop     dword ptr [rax+rax+00h]
0x180007304  mov     ebx, eax
0x180007306  test    eax, eax
0x180007308  jnz     loc_180007399
0x18000730e  lea     rcx, [rsp+38h+BindingVector]; BindingVector
0x180007313  mov     dil, 1
0x180007316  call    cs:__imp_RpcServerInqBindings
0x18000731d  nop     dword ptr [rax+rax+00h]
0x180007322  mov     ebx, eax
0x180007324  test    eax, eax
0x180007326  jz      short loc_180007333
0x180007328  mov     edx, eax
0x18000732a  lea     rcx, aStartdfsdsrpcR; "StartDfsDsRpc: RpcServerInqBindings fai"...
0x180007331  jmp     short loc_1800073A5
0x180007333  mov     rdx, [rsp+38h+BindingVector]; BindingVector
0x180007338  lea     r9, Annotation; "DfsDs service"
0x18000733f  xor     r8d, r8d; UuidVector
0x180007342  lea     rcx, qword_180038000; IfSpec
0x180007349  call    cs:__imp_RpcEpRegisterW
0x180007350  nop     dword ptr [rax+rax+00h]
0x180007355  mov     ebx, eax
0x180007357  test    eax, eax
0x180007359  jz      short loc_180007366
0x18000735b  mov     edx, eax
0x18000735d  lea     rcx, aStartdfsdsrpcR_0; "StartDfsDsRpc: RpcEpRegister failed: %X"...
0x180007364  jmp     short loc_1800073A5
0x180007366  lea     rcx, aDfsdsRpcServer; "DfsDs RPC server started.\n"
0x18000736d  call    cs:__imp_DbgPrint
0x180007374  nop     dword ptr [rax+rax+00h]
0x180007379  cmp     [rsp+38h+BindingVector], 0
0x18000737f  jz      short loc_180007392
0x180007381  lea     rcx, [rsp+38h+BindingVector]; BindingVector
0x180007386  call    cs:__imp_RpcBindingVectorFree
0x18000738d  nop     dword ptr [rax+rax+00h]
0x180007392  xor     eax, eax
0x180007394  jmp     loc_180007424
0x180007399  xor     dil, dil
0x18000739c  lea     rcx, aStartdfsdsrpcR_1; "StartDfsDsRpc: RpcServerRegisterIfEx fa"...
0x1800073a3  mov     edx, ebx
0x1800073a5  call    cs:__imp_DbgPrint
0x1800073ac  nop     dword ptr [rax+rax+00h]
0x1800073b1  mov     r8d, ebx
0x1800073b4  lea     rcx, aFailedToStartD; "Failed to start DfsDsService with statu"...
0x1800073bb  xor     edx, edx
0x1800073bd  call    cs:__imp_DbgPrint
0x1800073c4  nop     dword ptr [rax+rax+00h]
0x1800073c9  cmp     [rsp+38h+BindingVector], 0
0x1800073cf  jz      short loc_1800073EB
0x1800073d1  lea     rcx, [rsp+38h+BindingVector]; BindingVector
0x1800073d6  call    cs:__imp_RpcBindingVectorFree
0x1800073dd  nop     dword ptr [rax+rax+00h]
0x1800073e2  mov     [rsp+38h+BindingVector], 0
0x1800073eb  test    dil, dil
0x1800073ee  jz      short loc_180007422
0x1800073f0  xor     edx, edx; MgrTypeUuid
0x1800073f2  lea     rcx, qword_180038000; IfSpec
0x1800073f9  lea     r8d, [rdx+1]; WaitForCallsToComplete
0x1800073fd  call    cs:__imp_RpcServerUnregisterIf
0x180007404  nop     dword ptr [rax+rax+00h]
0x180007409  test    eax, eax
0x18000740b  jz      short loc_180007422
0x18000740d  mov     edx, eax
0x18000740f  lea     rcx, aFailedToUnregi; "Failed to unregister rpc interface with"...
0x180007416  call    cs:__imp_DbgPrint
0x18000741d  nop     dword ptr [rax+rax+00h]
0x180007422  mov     eax, ebx
0x180007424  mov     rbx, [rsp+38h+arg_8]
0x180007429  mov     rsi, [rsp+38h+arg_10]
0x18000742e  add     rsp, 30h
0x180007432  pop     rdi
0x180007433  retn
```
