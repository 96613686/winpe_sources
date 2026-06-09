# XdrBytesLeft

- ea: `0x1400059f8`
- end: `0x140005a2e`
- name: `XdrBytesLeft`
- size: `54`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x140003dbc`
- `0x1400042c4`
- `0x14000b624`
- `0x14000bf88`
- `0x140015408`

## callees

- `0x140001340`
- `0x14000225c`
- `0x1400059f8`

## pseudocode

```c
__int64 __fastcall XdrBytesLeft(__int64 a1)
{
  _DWORD *NextBufferDescriptor; // r10
  __int64 v2; // r10
  __int64 v3; // r11
  unsigned int v4; // r9d

  NextBufferDescriptor = *(_DWORD **)(a1 + 72);
  do
  {
    OncRpcBufMgrGetDescriptorValidLengthRemaining(NextBufferDescriptor);
    NextBufferDescriptor = (_DWORD *)OncRpcBufMgrGetNextBufferDescriptor(v3, v2);
  }
  while ( NextBufferDescriptor );
  return v4;
}

```

## disassembly

```asm
0x1400059f8  sub     rsp, 28h
0x1400059fc  mov     r10, [rcx+48h]
0x140005a00  lea     r11, [rcx+20h]
0x140005a04  xor     r9d, r9d
0x140005a07  mov     rcx, r10
0x140005a0a  call    OncRpcBufMgrGetDescriptorValidLengthRemaining
0x140005a0f  mov     rdx, r10
0x140005a12  mov     rcx, r11
0x140005a15  add     r9d, eax
0x140005a18  call    OncRpcBufMgrGetNextBufferDescriptor
0x140005a1d  mov     r10, rax
0x140005a20  test    rax, rax
0x140005a23  jnz     short loc_140005A07
0x140005a25  mov     eax, r9d
0x140005a28  add     rsp, 28h
0x140005a2c  retn
```
