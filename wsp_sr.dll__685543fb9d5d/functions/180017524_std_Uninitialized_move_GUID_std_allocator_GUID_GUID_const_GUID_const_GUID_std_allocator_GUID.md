# std::_Uninitialized_move<_GUID *,std::allocator<_GUID>>(_GUID * const,_GUID * const,_GUID *,std::allocator<_GUID> &)

- ea: `0x180017524`
- end: `0x18001755d`
- name: `??$_Uninitialized_move@PEAU_GUID@@V?$allocator@U_GUID@@@std@@@std@@YAPEAU_GUID@@QEAU1@0PEAU1@AEAV?$allocator@U_GUID@@@0@@Z`
- size: `57`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180017140`

## callees

- `0x180007814`

## pseudocode

```c
char *__fastcall std::_Uninitialized_move<_GUID *>(void *a1, __int64 a2, char *a3)
{
  std::_Copy_memmove<_GUID *,_GUID *>(a1, a2, a3);
  return &a3[(a2 - (_QWORD)a1) & 0xFFFFFFFFFFFFFFF0uLL];
}

```

## disassembly

```asm
0x180017524  mov     [rsp+arg_0], rbx
0x180017529  mov     [rsp+arg_8], rsi
0x18001752e  push    rdi
0x18001752f  sub     rsp, 20h
0x180017533  mov     rdi, r8
0x180017536  mov     rsi, rdx
0x180017539  mov     rbx, rcx
0x18001753c  call    ??$_Copy_memmove@PEAU_GUID@@PEAU1@@std@@YAPEAU_GUID@@PEAU1@00@Z; std::_Copy_memmove<_GUID *,_GUID *>(_GUID *,_GUID *,_GUID *)
0x180017541  sub     rsi, rbx
0x180017544  mov     rbx, [rsp+28h+arg_0]
0x180017549  and     rsi, 0FFFFFFFFFFFFFFF0h
0x18001754d  lea     rax, [rdi+rsi]
0x180017551  mov     rsi, [rsp+28h+arg_8]
0x180017556  add     rsp, 20h
0x18001755a  pop     rdi
0x18001755b  retn
```
