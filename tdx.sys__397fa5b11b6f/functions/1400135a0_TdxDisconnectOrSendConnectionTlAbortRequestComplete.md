# TdxDisconnectOrSendConnectionTlAbortRequestComplete

- ea: `0x1400135a0`
- end: `0x1400135d1`
- name: `TdxDisconnectOrSendConnectionTlAbortRequestComplete`
- size: `49`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140013460`

## callees

- `0x1400047d0`
- `0x14000fc90`

## string_xrefs

- `0x1400135a6`: `TdxDisconnectOrSendConnectionTlAbortRequestComplete`
- `0x1400135bb`: `TdxDisconnectOrSendConnectionTlAbortRequestComplete`

## pseudocode

```c
void __fastcall TdxDisconnectOrSendConnectionTlAbortRequestComplete(__int64 a1)
{
  TdxTraceConnectionRoutine(a1, "TdxDisconnectOrSendConnectionTlAbortRequestComplete");
  DbgTdxDereferenceConnection(a1, (__int64)"TdxDisconnectOrSendConnectionTlAbortRequestComplete", 2253);
}

```

## disassembly

```asm
0x1400135a0  push    rbx
0x1400135a2  sub     rsp, 20h
0x1400135a6  lea     rdx, aTdxdisconnecto_0; "TdxDisconnectOrSendConnectionTlAbortReq"...
0x1400135ad  mov     rbx, rcx
0x1400135b0  call    TdxTraceConnectionRoutine
0x1400135b5  mov     r8d, 8CDh
0x1400135bb  lea     rdx, aTdxdisconnecto_0; "TdxDisconnectOrSendConnectionTlAbortReq"...
0x1400135c2  mov     rcx, rbx
0x1400135c5  call    DbgTdxDereferenceConnection
0x1400135ca  add     rsp, 20h
0x1400135ce  pop     rbx
0x1400135cf  retn
```
