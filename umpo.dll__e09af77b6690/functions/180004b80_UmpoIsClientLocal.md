# UmpoIsClientLocal

- ea: `0x180004b80`
- end: `0x180004bbb`
- name: `UmpoIsClientLocal`
- size: `59`
- prototype: `BOOL()`
- caller_count: `32`
- callee_count: `1`
- tags: ``

## callers

- `0x180001580`
- `0x180002530`
- `0x180002e90`
- `0x180003070`
- `0x180003150`
- `0x180003640`
- `0x180004760`
- `0x180004830`
- `0x180009fd0`
- `0x18000c780`
- `0x18000ca70`
- `0x18000d7c0`
- `0x18000d880`
- `0x18000d940`
- `0x18000e640`
- `0x18000e950`
- `0x18000ebf0`
- `0x18000eca0`
- `0x180014610`
- `0x180014670`
- `0x1800146c0`
- `0x1800147b0`
- `0x180014810`
- `0x180014950`
- `0x180014a00`
- `0x180014a90`
- `0x180014ad0`
- `0x180014c80`
- `0x180014d60`
- `0x180014dd0`
- `0x180014e50`
- `0x180015150`

## callees

- `0x180004b80`

## import_xrefs

- `RPCRT4!I_RpcBindingIsClientLocal` at `0x180004b93`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x180004b93`

## pseudocode

```c
BOOL UmpoIsClientLocal()
{
  RPC_STATUS IsClientLocal; // eax
  unsigned int ClientLocalFlag; // [rsp+30h] [rbp+8h] BYREF

  ClientLocalFlag = 0;
  IsClientLocal = I_RpcBindingIsClientLocal(0, &ClientLocalFlag);
  if ( IsClientLocal )
    return IsClientLocal == 1725;
  else
    return ClientLocalFlag != 0;
}

```

## disassembly

```asm
0x180004b80  sub     rsp, 28h
0x180004b84  lea     rdx, [rsp+28h+ClientLocalFlag]; ClientLocalFlag
0x180004b89  mov     [rsp+28h+ClientLocalFlag], 0
0x180004b91  xor     ecx, ecx; BindingHandle
0x180004b93  call    cs:__imp_I_RpcBindingIsClientLocal
0x180004b99  test    eax, eax
0x180004b9b  jnz     short loc_180004BA9
0x180004b9d  cmp     [rsp+28h+ClientLocalFlag], eax
0x180004ba1  setnz   al
0x180004ba4  add     rsp, 28h
0x180004ba8  retn
0x180004ba9  cmp     eax, 6BDh
0x180004bae  jnz     short loc_180004BB7
0x180004bb0  mov     eax, 1
0x180004bb5  jmp     short loc_180004BA4
0x180004bb7  xor     eax, eax
0x180004bb9  jmp     short loc_180004BA4
```
