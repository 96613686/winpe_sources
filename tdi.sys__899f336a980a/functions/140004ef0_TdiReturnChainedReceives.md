# TdiReturnChainedReceives

- ea: `0x140004ef0`
- end: `0x140004f06`
- name: `TdiReturnChainedReceives`
- size: `22`
- prototype: `void __stdcall(PVOID *TsduDescriptors, ULONG NumberOfTsdus)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `NDIS!NdisReturnPackets` at `0x140004ef4`
- `NDIS!NdisReturnPackets` at `0x140004ef4`

## pseudocode

```c
void __stdcall TdiReturnChainedReceives(PVOID *TsduDescriptors, ULONG NumberOfTsdus)
{
  NdisReturnPackets(TsduDescriptors, NumberOfTsdus);
}

```

## disassembly

```asm
0x140004ef0  sub     rsp, 28h
0x140004ef4  call    cs:__imp_NdisReturnPackets
0x140004efb  nop     dword ptr [rax+rax+00h]
0x140004f00  add     rsp, 28h
0x140004f04  retn
```
