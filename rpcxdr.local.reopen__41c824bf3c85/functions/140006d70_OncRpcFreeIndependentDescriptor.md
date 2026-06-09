# OncRpcFreeIndependentDescriptor

- ea: `0x140006d70`
- end: `0x140006d7f`
- name: `OncRpcFreeIndependentDescriptor`
- size: `15`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140001f78`

## pseudocode

```c
void __fastcall OncRpcFreeIndependentDescriptor(void *a1)
{
  OncRpcBufMgrpDestroyBufferDescriptor(a1);
}

```

## disassembly

```asm
0x140006d70  sub     rsp, 28h
0x140006d74  call    OncRpcBufMgrpDestroyBufferDescriptor
0x140006d79  add     rsp, 28h
0x140006d7d  retn
```
