# WepHostTearDownRPCServer(void)

- ea: `0x180002620`
- end: `0x18000266b`
- name: `?WepHostTearDownRPCServer@@YAXXZ`
- size: `75`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1800030b8`
- `0x1800036b0`

## import_xrefs

- `RPCRT4!RpcServerUnregisterIfEx` at `0x180002631`
- `RPCRT4!RpcServerUnregisterIfEx` at `0x180002631`
- `RPCRT4!RpcEpUnregister` at `0x180002648`
- `RPCRT4!RpcEpUnregister` at `0x180002648`
- `RPCRT4!RpcBindingVectorFree` at `0x180002655`
- `RPCRT4!RpcBindingVectorFree` at `0x180002655`

## pseudocode

```c
void WepHostTearDownRPCServer(void)
{
  RpcServerUnregisterIfEx(qword_180005410, 0, 1);
  RpcEpUnregister(qword_180005410, g_pBindingVector, 0);
  RpcBindingVectorFree(&g_pBindingVector);
  g_pBindingVector = 0;
}

```

## disassembly

```asm
0x180002620  sub     rsp, 28h
0x180002624  xor     edx, edx; MgrTypeUuid
0x180002626  lea     rcx, qword_180005410; IfSpec
0x18000262d  lea     r8d, [rdx+1]; RundownContextHandles
0x180002631  call    cs:__imp_RpcServerUnregisterIfEx
0x180002637  mov     rdx, cs:?g_pBindingVector@@3PEAU_RPC_BINDING_VECTOR@@EA; BindingVector
0x18000263e  lea     rcx, qword_180005410; IfSpec
0x180002645  xor     r8d, r8d; UuidVector
0x180002648  call    cs:__imp_RpcEpUnregister
0x18000264e  lea     rcx, ?g_pBindingVector@@3PEAU_RPC_BINDING_VECTOR@@EA; BindingVector
0x180002655  call    cs:__imp_RpcBindingVectorFree
0x18000265b  mov     cs:?g_pBindingVector@@3PEAU_RPC_BINDING_VECTOR@@EA, 0; _RPC_BINDING_VECTOR * g_pBindingVector
0x180002666  add     rsp, 28h
0x18000266a  retn
```
