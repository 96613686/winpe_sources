# OncRpcCreateOutboundGssContext

- ea: `0x140006bb0`
- end: `0x140006bbf`
- name: `OncRpcCreateOutboundGssContext`
- size: `15`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140008d78`

## pseudocode

```c
__int64 __fastcall OncRpcCreateOutboundGssContext(__int64 a1, _QWORD *a2, int a3, void **a4)
{
  return OncRpcSeCreateOutboundGssContext(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x140006bb0  sub     rsp, 28h
0x140006bb4  call    OncRpcSeCreateOutboundGssContext
0x140006bb9  add     rsp, 28h
0x140006bbd  retn
```
