# KmclpFreeCompletionRoutine

- ea: `0x14000a380`
- end: `0x14000a38f`
- name: `KmclpFreeCompletionRoutine`
- size: `15`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14000a6d0`

## pseudocode

```c
void __fastcall KmclpFreeCompletionRoutine(_DWORD *a1)
{
  VmbPacketFree(a1);
}

```

## disassembly

```asm
0x14000a380  sub     rsp, 28h
0x14000a384  call    VmbPacketFree
0x14000a389  add     rsp, 28h
0x14000a38d  retn
```
