# UmpoInternalDataAccessorToString

- ea: `0x18000ab60`
- end: `0x18000aba8`
- name: `UmpoInternalDataAccessorToString`
- size: `72`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180005cb4`
- `0x18000681c`
- `0x18000b9b8`
- `0x18000cb4c`
- `0x1800127cc`

## callees

- `0x18000ab60`
- `0x18000f3dc`

## pseudocode

```c
__int64 __fastcall UmpoInternalDataAccessorToString(unsigned int a1)
{
  __int64 v1; // rbx

  if ( a1 > 0x18 )
    return 0;
  v1 = 2LL * (int)a1;
  if ( LODWORD(AccessorToStringTable[2 * (int)a1]) != a1 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  return AccessorToStringTable[v1 + 1];
}

```

## disassembly

```asm
0x18000ab60  sub     rsp, 28h
0x18000ab64  test    ecx, ecx
0x18000ab66  js      short loc_18000AB9D
0x18000ab68  cmp     ecx, 19h
0x18000ab6b  jnb     short loc_18000AB9D
0x18000ab6d  mov     [rsp+28h+arg_0], rbx
0x18000ab72  movsxd  rbx, ecx
0x18000ab75  add     rbx, rbx
0x18000ab78  mov     [rsp+28h+var_8], rdi
0x18000ab7d  lea     rdi, AccessorToStringTable
0x18000ab84  cmp     [rdi+rbx*8], ecx
0x18000ab87  jnz     short loc_18000ABA1
0x18000ab89  mov     rax, [rdi+rbx*8+8]
0x18000ab8e  mov     rdi, [rsp+28h+var_8]
0x18000ab93  mov     rbx, [rsp+28h+arg_0]
0x18000ab98  add     rsp, 28h
0x18000ab9c  retn
0x18000ab9d  xor     eax, eax
0x18000ab9f  jmp     short loc_18000AB98
0x18000aba1  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000aba6  jmp     short loc_18000AB89
```
