# OncRpcBufMgrGetLastBufferDescriptor

- ea: `0x140008968`
- end: `0x14000897e`
- name: `OncRpcBufMgrGetLastBufferDescriptor`
- size: `22`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x14000993c`
- `0x14000a814`
- `0x14000aac4`

## callees

- `0x140008968`

## pseudocode

```c
__int64 __fastcall OncRpcBufMgrGetLastBufferDescriptor(__int64 a1)
{
  if ( *(_QWORD *)(a1 + 24) == a1 + 24 )
    return 0;
  else
    return *(_QWORD *)(a1 + 32) - 24LL;
}

```

## disassembly

```asm
0x140008968  lea     rax, [rcx+18h]
0x14000896c  cmp     [rax], rax
0x14000896f  jnz     short loc_140008975
0x140008971  xor     eax, eax
0x140008973  retn
0x140008975  mov     rax, [rcx+20h]
0x140008979  sub     rax, 18h
0x14000897d  retn
```
