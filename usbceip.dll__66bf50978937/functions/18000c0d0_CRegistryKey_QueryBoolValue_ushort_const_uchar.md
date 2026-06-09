# CRegistryKey::QueryBoolValue(ushort const *,uchar &)

- ea: `0x18000c0d0`
- end: `0x18000c10b`
- name: `?QueryBoolValue@CRegistryKey@@QEAAEPEBGAEAE@Z`
- size: `59`
- prototype: `unsigned __int8 __fastcall(CRegistryKey *this, const unsigned __int16 *, bool *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800045d0`
- `0x180006f18`
- `0x1800073b4`

## callees

- `0x18000c0d0`
- `0x18000c114`

## pseudocode

```c
unsigned __int8 __fastcall CRegistryKey::QueryBoolValue(CRegistryKey *this, const unsigned __int16 *a2, bool *a3)
{
  int v5; // [rsp+48h] [rbp+20h] BYREF

  v5 = 0;
  if ( !CRegistryKey::QueryFixedLengthValue(this, a2, 4u, (unsigned __int8 *)&v5) )
    return 0;
  *a3 = v5 != 0;
  return 1;
}

```

## disassembly

```asm
0x18000c0d0  push    rbx
0x18000c0d2  sub     rsp, 20h
0x18000c0d6  mov     rbx, r8
0x18000c0d9  mov     [rsp+28h+arg_18], 0
0x18000c0e1  mov     r8d, 4; unsigned int
0x18000c0e7  lea     r9, [rsp+28h+arg_18]; unsigned __int8 *
0x18000c0ec  call    ?QueryFixedLengthValue@CRegistryKey@@QEAAEPEBGKPEAE@Z; CRegistryKey::QueryFixedLengthValue(ushort const *,ulong,uchar *)
0x18000c0f1  test    al, al
0x18000c0f3  jz      short loc_18000C103
0x18000c0f5  cmp     [rsp+28h+arg_18], 0
0x18000c0fa  setnz   al
0x18000c0fd  mov     [rbx], al
0x18000c0ff  mov     al, 1
0x18000c101  jmp     short loc_18000C105
0x18000c103  xor     al, al
0x18000c105  add     rsp, 20h
0x18000c109  pop     rbx
0x18000c10a  retn
```
