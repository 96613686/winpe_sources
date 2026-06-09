# std::_Uninitialized_move<CGpWmpDecoder::CWmpDecoderFrameInfo *,std::allocator<CGpWmpDecoder::CWmpDecoderFrameInfo>>(CGpWmpDecoder::CWmpDecoderFrameInfo * const,CGpWmpDecoder::CWmpDecoderFrameInfo * const,CGpWmpDecoder::CWmpDecoderFrameInfo *,std::allocator<CGpWmpDecoder::CWmpDecoderFrameInfo> &)

- ea: `0x180034e58`
- end: `0x180034e90`
- name: `??$_Uninitialized_move@PEAUCWmpDecoderFrameInfo@CGpWmpDecoder@@V?$allocator@UCWmpDecoderFrameInfo@CGpWmpDecoder@@@std@@@std@@YAPEAUCWmpDecoderFrameInfo@CGpWmpDecoder@@QEAU12@0PEAU12@AEAV?$allocator@UCWmpDecoderFrameInfo@CGpWmpDecoder@@@0@@Z`
- size: `56`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180037f28`

## callees

- `0x1800338f0`

## pseudocode

```c
char *__fastcall std::_Uninitialized_move<CGpWmpDecoder::CWmpDecoderFrameInfo *>(void *a1, __int64 a2, char *a3)
{
  std::_Copy_memmove<CGpWmpDecoder::CWmpDecoderFrameInfo *,CGpWmpDecoder::CWmpDecoderFrameInfo *>(a1, a2, a3);
  return &a3[(a2 - (_QWORD)a1) & 0xFFFFFFFFFFFFFFF0uLL];
}

```

## disassembly

```asm
0x180034e58  mov     [rsp+arg_0], rbx
0x180034e5d  mov     [rsp+arg_8], rsi
0x180034e62  push    rdi
0x180034e63  sub     rsp, 20h
0x180034e67  mov     rdi, r8
0x180034e6a  mov     rsi, rdx
0x180034e6d  mov     rbx, rcx
0x180034e70  call    ??$_Copy_memmove@PEAUCWmpDecoderFrameInfo@CGpWmpDecoder@@PEAU12@@std@@YAPEAUCWmpDecoderFrameInfo@CGpWmpDecoder@@PEAU12@00@Z; std::_Copy_memmove<CGpWmpDecoder::CWmpDecoderFrameInfo *,CGpWmpDecoder::CWmpDecoderFrameInfo *>(CGpWmpDecoder::CWmpDecoderFrameInfo *,CGpWmpDecoder::CWmpDecoderFrameInfo *,CGpWmpDecoder::CWmpDecoderFrameInfo *)
0x180034e75  sub     rsi, rbx
0x180034e78  mov     rbx, [rsp+28h+arg_0]
0x180034e7d  and     rsi, 0FFFFFFFFFFFFFFF0h
0x180034e81  lea     rax, [rdi+rsi]
0x180034e85  mov     rsi, [rsp+28h+arg_8]
0x180034e8a  add     rsp, 20h
0x180034e8e  pop     rdi
0x180034e8f  retn
```
