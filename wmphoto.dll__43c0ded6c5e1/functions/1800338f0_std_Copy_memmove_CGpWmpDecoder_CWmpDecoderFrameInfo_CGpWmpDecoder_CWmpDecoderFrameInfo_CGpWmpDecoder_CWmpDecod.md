# std::_Copy_memmove<CGpWmpDecoder::CWmpDecoderFrameInfo *,CGpWmpDecoder::CWmpDecoderFrameInfo *>(CGpWmpDecoder::CWmpDecoderFrameInfo *,CGpWmpDecoder::CWmpDecoderFrameInfo *,CGpWmpDecoder::CWmpDecoderFrameInfo *)

- ea: `0x1800338f0`
- end: `0x180033920`
- name: `??$_Copy_memmove@PEAUCWmpDecoderFrameInfo@CGpWmpDecoder@@PEAU12@@std@@YAPEAUCWmpDecoderFrameInfo@CGpWmpDecoder@@PEAU12@00@Z`
- size: `48`
- prototype: `__int64 __fastcall(void *Src, __int64, void *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180034e58`
- `0x18003a2b8`

## callees

- `0x18004363c`

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
0x1800338f0  mov     [rsp+arg_0], rbx
0x1800338f5  push    rdi
0x1800338f6  sub     rsp, 20h
0x1800338fa  mov     rbx, rdx
0x1800338fd  mov     rdi, r8
0x180033900  sub     rbx, rcx
0x180033903  mov     rdx, rcx; Src
0x180033906  mov     r8, rbx; Size
0x180033909  mov     rcx, rdi; void *
0x18003390c  call    memmove_0
0x180033911  lea     rax, [rbx+rdi]
0x180033915  mov     rbx, [rsp+28h+arg_0]
0x18003391a  add     rsp, 20h
0x18003391e  pop     rdi
0x18003391f  retn
```
