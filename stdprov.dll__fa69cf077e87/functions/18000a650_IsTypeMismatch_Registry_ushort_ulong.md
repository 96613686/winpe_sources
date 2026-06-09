# IsTypeMismatch(Registry &,ushort *,ulong)

- ea: `0x18000a650`
- end: `0x18000a683`
- name: `?IsTypeMismatch@@YAHAEAVRegistry@@PEAGK@Z`
- size: `51`
- prototype: `_BOOL8 __fastcall(struct Registry *, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180012fe0`

## callees

- `0x18000a650`

## import_xrefs

- `wbemcomn!?GetType@Registry@@QEAAHPEBGPEAK@Z` at `0x18000a666`
- `wbemcomn!?GetType@Registry@@QEAAHPEBGPEAK@Z` at `0x18000a666`

## pseudocode

```c
_BOOL8 __fastcall IsTypeMismatch(struct Registry *a1, unsigned __int16 *a2, int a3)
{
  unsigned int v5; // [rsp+48h] [rbp+20h] BYREF

  v5 = 0;
  return !Registry::GetType(a1, a2, &v5) && a3 != v5;
}

```

## disassembly

```asm
0x18000a650  push    rbx
0x18000a652  sub     rsp, 20h
0x18000a656  mov     ebx, r8d
0x18000a659  mov     [rsp+28h+arg_18], 0
0x18000a661  lea     r8, [rsp+28h+arg_18]
0x18000a666  call    cs:__imp_?GetType@Registry@@QEAAHPEBGPEAK@Z; Registry::GetType(ushort const *,ulong *)
0x18000a66c  test    eax, eax
0x18000a66e  jz      short loc_18000A678
0x18000a670  xor     eax, eax
0x18000a672  add     rsp, 20h
0x18000a676  pop     rbx
0x18000a677  retn
0x18000a678  xor     eax, eax
0x18000a67a  cmp     ebx, [rsp+28h+arg_18]
0x18000a67e  setnz   al
0x18000a681  jmp     short loc_18000A672
```
