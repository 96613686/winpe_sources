# std::_Copy_memmove_n<_GUID *,_GUID *>(_GUID *,unsigned __int64,_GUID *)

- ea: `0x180017108`
- end: `0x18001713a`
- name: `??$_Copy_memmove_n@PEAU_GUID@@PEAU1@@std@@YAPEAU_GUID@@PEAU1@_K0@Z`
- size: `50`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180017994`

## callees

- `0x18000298f`

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
0x180017108  mov     [rsp+arg_0], rbx
0x18001710d  push    rdi
0x18001710e  sub     rsp, 20h
0x180017112  mov     rbx, rdx
0x180017115  mov     rdi, r8
0x180017118  shl     rbx, 4
0x18001711c  mov     rdx, rcx; Src
0x18001711f  mov     r8, rbx; Size
0x180017122  mov     rcx, rdi; void *
0x180017125  call    memmove_0
0x18001712a  lea     rax, [rbx+rdi]
0x18001712e  mov     rbx, [rsp+28h+arg_0]
0x180017133  add     rsp, 20h
0x180017137  pop     rdi
0x180017138  retn
```
