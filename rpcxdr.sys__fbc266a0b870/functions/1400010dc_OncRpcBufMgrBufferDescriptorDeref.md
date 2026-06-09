# OncRpcBufMgrBufferDescriptorDeref

- ea: `0x1400010dc`
- end: `0x1400010f8`
- name: `OncRpcBufMgrBufferDescriptorDeref`
- size: `28`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x14000127c`
- `0x140006e60`
- `0x140010904`
- `0x14001143c`

## callees

- `0x1400010dc`
- `0x140001f78`

## pseudocode

```c
void __fastcall OncRpcBufMgrBufferDescriptorDeref(volatile signed __int32 *a1)
{
  if ( _InterlockedExchangeAdd(a1 + 1, 0xFFFFFFFF) == 1 )
    OncRpcBufMgrpDestroyBufferDescriptor((PVOID)a1);
}

```

## disassembly

```asm
0x1400010dc  sub     rsp, 28h
0x1400010e0  or      eax, 0FFFFFFFFh
0x1400010e3  lock xadd [rcx+4], eax
0x1400010e8  cmp     eax, 1
0x1400010eb  jnz     short loc_1400010F2
0x1400010ed  call    OncRpcBufMgrpDestroyBufferDescriptor
0x1400010f2  add     rsp, 28h
0x1400010f6  retn
```
