# TdxReceiveConnectionTlFlushRequestComplete

- ea: `0x140013ad0`
- end: `0x140013aec`
- name: `TdxReceiveConnectionTlFlushRequestComplete`
- size: `28`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1400047d0`

## string_xrefs

- `0x140013ada`: `TdxReceiveConnectionTlFlushRequestComplete`

## pseudocode

```c
void __fastcall TdxReceiveConnectionTlFlushRequestComplete(__int64 a1)
{
  DbgTdxDereferenceConnection(a1, (__int64)"TdxReceiveConnectionTlFlushRequestComplete", 2733);
}

```

## disassembly

```asm
0x140013ad0  sub     rsp, 28h
0x140013ad4  mov     r8d, 0AADh
0x140013ada  lea     rdx, aTdxreceiveconn; "TdxReceiveConnectionTlFlushRequestCompl"...
0x140013ae1  call    DbgTdxDereferenceConnection
0x140013ae6  add     rsp, 28h
0x140013aea  retn
```
