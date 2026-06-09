# std::_Copy_memmove_n<_GUID *,_GUID *>(_GUID *,unsigned __int64,_GUID *)

- ea: `0x180017348`
- end: `0x180017379`
- name: `??$_Copy_memmove_n@PEAU_GUID@@PEAU1@@std@@YAPEAU_GUID@@PEAU1@_K0@Z`
- size: `49`
- prototype: `__int64 __fastcall(void *Src, __int64, void *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180017248`

## callees

- `0x18000295f`

## pseudocode

```c
__int64 __fastcall std::_Copy_memmove_n<_GUID *,_GUID *>(void *Src, __int64 a2, void *a3)
{
  __int64 v4; // rbx

  v4 = 16 * a2;
  memmove_0(a3, Src, 16 * a2);
  return (__int64)a3 + v4;
}

```

## disassembly

```asm
0x180017348  mov     [rsp+arg_0], rbx
0x18001734d  push    rdi
0x18001734e  sub     rsp, 20h
0x180017352  mov     rbx, rdx
0x180017355  mov     rdi, r8
0x180017358  shl     rbx, 4
0x18001735c  mov     rdx, rcx; Src
0x18001735f  mov     r8, rbx; Size
0x180017362  mov     rcx, rdi; void *
0x180017365  call    memmove_0
0x18001736a  lea     rax, [rbx+rdi]
0x18001736e  mov     rbx, [rsp+28h+arg_0]
0x180017373  add     rsp, 20h
0x180017377  pop     rdi
0x180017378  retn
```
