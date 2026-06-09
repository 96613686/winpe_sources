# std::_Uninitialized_move<CGpWmpDecoder::CWmpDecoderFrameInfo *,std::allocator<CGpWmpDecoder::CWmpDecoderFrameInfo>>(CGpWmpDecoder::CWmpDecoderFrameInfo * const,CGpWmpDecoder::CWmpDecoderFrameInfo * const,CGpWmpDecoder::CWmpDecoderFrameInfo *,std::allocator<CGpWmpDecoder::CWmpDecoderFrameInfo> &)

- ea: `0x180035430`
- end: `0x180035469`
- name: `??$_Uninitialized_move@PEAUCWmpDecoderFrameInfo@CGpWmpDecoder@@V?$allocator@UCWmpDecoderFrameInfo@CGpWmpDecoder@@@std@@@std@@YAPEAUCWmpDecoderFrameInfo@CGpWmpDecoder@@QEAU12@0PEAU12@AEAV?$allocator@UCWmpDecoderFrameInfo@CGpWmpDecoder@@@0@@Z`
- size: `57`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18003855c`

## callees

- `0x180033ea0`

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
0x180035430  mov     [rsp+arg_0], rbx
0x180035435  mov     [rsp+arg_8], rsi
0x18003543a  push    rdi
0x18003543b  sub     rsp, 20h
0x18003543f  mov     rdi, r8
0x180035442  mov     rsi, rdx
0x180035445  mov     rbx, rcx
0x180035448  call    ??$_Copy_memmove@PEAUCWmpDecoderFrameInfo@CGpWmpDecoder@@PEAU12@@std@@YAPEAUCWmpDecoderFrameInfo@CGpWmpDecoder@@PEAU12@00@Z; std::_Copy_memmove<CGpWmpDecoder::CWmpDecoderFrameInfo *,CGpWmpDecoder::CWmpDecoderFrameInfo *>(CGpWmpDecoder::CWmpDecoderFrameInfo *,CGpWmpDecoder::CWmpDecoderFrameInfo *,CGpWmpDecoder::CWmpDecoderFrameInfo *)
0x18003544d  sub     rsi, rbx
0x180035450  mov     rbx, [rsp+28h+arg_0]
0x180035455  and     rsi, 0FFFFFFFFFFFFFFF0h
0x180035459  lea     rax, [rdi+rsi]
0x18003545d  mov     rsi, [rsp+28h+arg_8]
0x180035462  add     rsp, 20h
0x180035466  pop     rdi
0x180035467  retn
```
