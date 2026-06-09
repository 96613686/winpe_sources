# std::_Uninitialized_move<_GUID *,std::allocator<_GUID>>(_GUID * const,_GUID * const,_GUID *,std::allocator<_GUID> &)

- ea: `0x180017758`
- end: `0x180017790`
- name: `??$_Uninitialized_move@PEAU_GUID@@V?$allocator@U_GUID@@@std@@@std@@YAPEAU_GUID@@QEAU1@0PEAU1@AEAV?$allocator@U_GUID@@@0@@Z`
- size: `56`
- prototype: `char *__fastcall(void *, __int64, char *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180017380`

## callees

- `0x180007738`

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
0x180017758  mov     [rsp+arg_0], rbx
0x18001775d  mov     [rsp+arg_8], rsi
0x180017762  push    rdi
0x180017763  sub     rsp, 20h
0x180017767  mov     rdi, r8
0x18001776a  mov     rsi, rdx
0x18001776d  mov     rbx, rcx
0x180017770  call    ??$_Copy_memmove@PEAU_GUID@@PEAU1@@std@@YAPEAU_GUID@@PEAU1@00@Z; std::_Copy_memmove<_GUID *,_GUID *>(_GUID *,_GUID *,_GUID *)
0x180017775  sub     rsi, rbx
0x180017778  mov     rbx, [rsp+28h+arg_0]
0x18001777d  and     rsi, 0FFFFFFFFFFFFFFF0h
0x180017781  lea     rax, [rdi+rsi]
0x180017785  mov     rsi, [rsp+28h+arg_8]
0x18001778a  add     rsp, 20h
0x18001778e  pop     rdi
0x18001778f  retn
```
