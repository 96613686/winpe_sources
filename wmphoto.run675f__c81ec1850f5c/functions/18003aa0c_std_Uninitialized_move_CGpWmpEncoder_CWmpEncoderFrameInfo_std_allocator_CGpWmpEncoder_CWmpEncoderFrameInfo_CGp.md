# std::_Uninitialized_move<CGpWmpEncoder::CWmpEncoderFrameInfo *,std::allocator<CGpWmpEncoder::CWmpEncoderFrameInfo>>(CGpWmpEncoder::CWmpEncoderFrameInfo * const,CGpWmpEncoder::CWmpEncoderFrameInfo * const,CGpWmpEncoder::CWmpEncoderFrameInfo *,std::allocator<CGpWmpEncoder::CWmpEncoderFrameInfo> &)

- ea: `0x18003aa0c`
- end: `0x18003aa45`
- name: `??$_Uninitialized_move@PEAUCWmpEncoderFrameInfo@CGpWmpEncoder@@V?$allocator@UCWmpEncoderFrameInfo@CGpWmpEncoder@@@std@@@std@@YAPEAUCWmpEncoderFrameInfo@CGpWmpEncoder@@QEAU12@0PEAU12@AEAV?$allocator@UCWmpEncoderFrameInfo@CGpWmpEncoder@@@0@@Z`
- size: `57`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18003a8ac`

## callees

- `0x180033ea0`

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
0x18003aa0c  mov     [rsp+arg_0], rbx
0x18003aa11  mov     [rsp+arg_8], rsi
0x18003aa16  push    rdi
0x18003aa17  sub     rsp, 20h
0x18003aa1b  mov     rsi, r8
0x18003aa1e  mov     rdi, rdx
0x18003aa21  mov     rbx, rcx
0x18003aa24  call    ??$_Copy_memmove@PEAUCWmpDecoderFrameInfo@CGpWmpDecoder@@PEAU12@@std@@YAPEAUCWmpDecoderFrameInfo@CGpWmpDecoder@@PEAU12@00@Z; std::_Copy_memmove<CGpWmpDecoder::CWmpDecoderFrameInfo *,CGpWmpDecoder::CWmpDecoderFrameInfo *>(CGpWmpDecoder::CWmpDecoderFrameInfo *,CGpWmpDecoder::CWmpDecoderFrameInfo *,CGpWmpDecoder::CWmpDecoderFrameInfo *)
0x18003aa29  sub     rdi, rbx
0x18003aa2c  mov     rbx, [rsp+28h+arg_0]
0x18003aa31  sar     rdi, 3
0x18003aa35  lea     rax, [rsi+rdi*8]
0x18003aa39  mov     rsi, [rsp+28h+arg_8]
0x18003aa3e  add     rsp, 20h
0x18003aa42  pop     rdi
0x18003aa43  retn
```
