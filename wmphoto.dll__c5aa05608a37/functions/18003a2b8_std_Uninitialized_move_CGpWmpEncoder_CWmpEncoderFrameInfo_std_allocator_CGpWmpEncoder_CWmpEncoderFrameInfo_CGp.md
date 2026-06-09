# std::_Uninitialized_move<CGpWmpEncoder::CWmpEncoderFrameInfo *,std::allocator<CGpWmpEncoder::CWmpEncoderFrameInfo>>(CGpWmpEncoder::CWmpEncoderFrameInfo * const,CGpWmpEncoder::CWmpEncoderFrameInfo * const,CGpWmpEncoder::CWmpEncoderFrameInfo *,std::allocator<CGpWmpEncoder::CWmpEncoderFrameInfo> &)

- ea: `0x18003a2b8`
- end: `0x18003a2f0`
- name: `??$_Uninitialized_move@PEAUCWmpEncoderFrameInfo@CGpWmpEncoder@@V?$allocator@UCWmpEncoderFrameInfo@CGpWmpEncoder@@@std@@@std@@YAPEAUCWmpEncoderFrameInfo@CGpWmpEncoder@@QEAU12@0PEAU12@AEAV?$allocator@UCWmpEncoderFrameInfo@CGpWmpEncoder@@@0@@Z`
- size: `56`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18003a160`

## callees

- `0x1800338f0`

## pseudocode

```c
char *__fastcall std::_Uninitialized_move<CGpWmpEncoder::CWmpEncoderFrameInfo *>(void *a1, __int64 a2, char *a3)
{
  std::_Copy_memmove<CGpWmpDecoder::CWmpDecoderFrameInfo *,CGpWmpDecoder::CWmpDecoderFrameInfo *>(a1, a2, a3);
  return &a3[8 * ((a2 - (__int64)a1) >> 3)];
}

```

## disassembly

```asm
0x18003a2b8  mov     [rsp+arg_0], rbx
0x18003a2bd  mov     [rsp+arg_8], rsi
0x18003a2c2  push    rdi
0x18003a2c3  sub     rsp, 20h
0x18003a2c7  mov     rsi, r8
0x18003a2ca  mov     rdi, rdx
0x18003a2cd  mov     rbx, rcx
0x18003a2d0  call    ??$_Copy_memmove@PEAUCWmpDecoderFrameInfo@CGpWmpDecoder@@PEAU12@@std@@YAPEAUCWmpDecoderFrameInfo@CGpWmpDecoder@@PEAU12@00@Z; std::_Copy_memmove<CGpWmpDecoder::CWmpDecoderFrameInfo *,CGpWmpDecoder::CWmpDecoderFrameInfo *>(CGpWmpDecoder::CWmpDecoderFrameInfo *,CGpWmpDecoder::CWmpDecoderFrameInfo *,CGpWmpDecoder::CWmpDecoderFrameInfo *)
0x18003a2d5  sub     rdi, rbx
0x18003a2d8  mov     rbx, [rsp+28h+arg_0]
0x18003a2dd  sar     rdi, 3
0x18003a2e1  lea     rax, [rsi+rdi*8]
0x18003a2e5  mov     rsi, [rsp+28h+arg_8]
0x18003a2ea  add     rsp, 20h
0x18003a2ee  pop     rdi
0x18003a2ef  retn
```
