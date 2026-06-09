# std::_Copy_memmove<CGpWmpDecoder::CWmpDecoderFrameInfo *,CGpWmpDecoder::CWmpDecoderFrameInfo *>(CGpWmpDecoder::CWmpDecoderFrameInfo *,CGpWmpDecoder::CWmpDecoderFrameInfo *,CGpWmpDecoder::CWmpDecoderFrameInfo *)

- ea: `0x180033ea0`
- end: `0x180033ed1`
- name: `??$_Copy_memmove@PEAUCWmpDecoderFrameInfo@CGpWmpDecoder@@PEAU12@@std@@YAPEAUCWmpDecoderFrameInfo@CGpWmpDecoder@@PEAU12@00@Z`
- size: `49`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180035430`
- `0x18003aa0c`

## callees

- `0x180043e4c`

## pseudocode

```c
__int64 __fastcall std::_Copy_memmove<CGpWmpDecoder::CWmpDecoderFrameInfo *,CGpWmpDecoder::CWmpDecoderFrameInfo *>(
        void *Src,
        __int64 a2,
        void *a3)
{
  __int64 v4; // rbx

  v4 = a2 - (_QWORD)Src;
  memmove_0(a3, Src, a2 - (_QWORD)Src);
  return (__int64)a3 + v4;
}

```

## disassembly

```asm
0x180033ea0  mov     [rsp+arg_0], rbx
0x180033ea5  push    rdi
0x180033ea6  sub     rsp, 20h
0x180033eaa  mov     rbx, rdx
0x180033ead  mov     rdi, r8
0x180033eb0  sub     rbx, rcx
0x180033eb3  mov     rdx, rcx; Src
0x180033eb6  mov     r8, rbx; Size
0x180033eb9  mov     rcx, rdi; void *
0x180033ebc  call    memmove_0
0x180033ec1  lea     rax, [rbx+rdi]
0x180033ec5  mov     rbx, [rsp+28h+arg_0]
0x180033eca  add     rsp, 20h
0x180033ece  pop     rdi
0x180033ecf  retn
```
