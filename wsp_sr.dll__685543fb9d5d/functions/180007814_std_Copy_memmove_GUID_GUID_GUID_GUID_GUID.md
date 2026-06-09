# std::_Copy_memmove<_GUID *,_GUID *>(_GUID *,_GUID *,_GUID *)

- ea: `0x180007814`
- end: `0x180007845`
- name: `??$_Copy_memmove@PEAU_GUID@@PEAU1@@std@@YAPEAU_GUID@@PEAU1@00@Z`
- size: `49`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180008050`
- `0x1800174e8`
- `0x180017524`
- `0x180026854`

## callees

- `0x18000298f`

## pseudocode

```c
__int64 __fastcall std::_Copy_memmove<_GUID *,_GUID *>(void *Src, __int64 a2, void *a3)
{
  __int64 v4; // rbx

  v4 = a2 - (_QWORD)Src;
  memmove_0(a3, Src, a2 - (_QWORD)Src);
  return (__int64)a3 + v4;
}

```

## disassembly

```asm
0x180007814  mov     [rsp+arg_0], rbx
0x180007819  push    rdi
0x18000781a  sub     rsp, 20h
0x18000781e  mov     rbx, rdx
0x180007821  mov     rdi, r8
0x180007824  sub     rbx, rcx
0x180007827  mov     rdx, rcx; Src
0x18000782a  mov     r8, rbx; Size
0x18000782d  mov     rcx, rdi; void *
0x180007830  call    memmove_0
0x180007835  lea     rax, [rbx+rdi]
0x180007839  mov     rbx, [rsp+28h+arg_0]
0x18000783e  add     rsp, 20h
0x180007842  pop     rdi
0x180007843  retn
```
