# std::_Copy_memmove<_GUID *,_GUID *>(_GUID *,_GUID *,_GUID *)

- ea: `0x180007738`
- end: `0x180007768`
- name: `??$_Copy_memmove@PEAU_GUID@@PEAU1@@std@@YAPEAU_GUID@@PEAU1@00@Z`
- size: `48`
- prototype: `__int64 __fastcall(void *Src, __int64, void *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180007f14`
- `0x18001771c`
- `0x180017758`
- `0x180026510`

## callees

- `0x18000295f`

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
0x180007738  mov     [rsp+arg_0], rbx
0x18000773d  push    rdi
0x18000773e  sub     rsp, 20h
0x180007742  mov     rbx, rdx
0x180007745  mov     rdi, r8
0x180007748  sub     rbx, rcx
0x18000774b  mov     rdx, rcx; Src
0x18000774e  mov     r8, rbx; Size
0x180007751  mov     rcx, rdi; void *
0x180007754  call    memmove_0
0x180007759  lea     rax, [rbx+rdi]
0x18000775d  mov     rbx, [rsp+28h+arg_0]
0x180007762  add     rsp, 20h
0x180007766  pop     rdi
0x180007767  retn
```
