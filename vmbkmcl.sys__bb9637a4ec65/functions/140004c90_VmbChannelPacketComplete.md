# VmbChannelPacketComplete

- ea: `0x140004c90`
- end: `0x140004cab`
- name: `VmbChannelPacketComplete`
- size: `27`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140004cc0`

## pseudocode

```c
void __fastcall VmbChannelPacketComplete(__int64 *a1, const void *a2, unsigned int a3)
{
  InCompletePacket(*a1, (__int64)a1, a2, a3);
}

```

## disassembly

```asm
0x140004c90  sub     rsp, 28h
0x140004c94  mov     r9d, r8d
0x140004c97  mov     r8, rdx
0x140004c9a  mov     rdx, rcx
0x140004c9d  mov     rcx, [rcx]
0x140004ca0  call    InCompletePacket
0x140004ca5  add     rsp, 28h
0x140004ca9  retn
```
