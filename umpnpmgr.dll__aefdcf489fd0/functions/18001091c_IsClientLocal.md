# IsClientLocal

- ea: `0x18001091c`
- end: `0x180010957`
- name: `IsClientLocal`
- size: `59`
- prototype: `BOOL()`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x18000bc30`
- `0x18000fd90`
- `0x1800121f0`
- `0x1800144b0`
- `0x1800146d0`
- `0x1800148a0`

## callees

- `0x18001091c`

## import_xrefs

- `RPCRT4!I_RpcBindingIsClientLocal` at `0x18001092f`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x18001092f`

## pseudocode

```c
BOOL IsClientLocal()
{
  RPC_STATUS v0; // eax
  unsigned int ClientLocalFlag; // [rsp+30h] [rbp+8h] BYREF

  ClientLocalFlag = 0;
  v0 = I_RpcBindingIsClientLocal(0, &ClientLocalFlag);
  if ( v0 == 1725 )
    return 1;
  if ( v0 )
    return 0;
  return ClientLocalFlag != 0;
}

```

## disassembly

```asm
0x18001091c  sub     rsp, 28h
0x180010920  lea     rdx, [rsp+28h+ClientLocalFlag]; ClientLocalFlag
0x180010925  mov     [rsp+28h+ClientLocalFlag], 0
0x18001092d  xor     ecx, ecx; BindingHandle
0x18001092f  call    cs:__imp_I_RpcBindingIsClientLocal
0x180010935  cmp     eax, 6BDh
0x18001093a  jz      short loc_18001094D
0x18001093c  test    eax, eax
0x18001093e  jnz     short loc_180010949
0x180010940  cmp     [rsp+28h+ClientLocalFlag], eax
0x180010944  setnz   al
0x180010947  jmp     short loc_180010952
0x180010949  xor     eax, eax
0x18001094b  jmp     short loc_180010952
0x18001094d  mov     eax, 1
0x180010952  add     rsp, 28h
0x180010956  retn
```
