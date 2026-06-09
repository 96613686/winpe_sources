# std::_Uninitialized_move<uchar *,std::allocator<uchar>>(uchar * const,uchar * const,uchar *,std::allocator<uchar> &)

- ea: `0x1800174e8`
- end: `0x18001751d`
- name: `??$_Uninitialized_move@PEAEV?$allocator@E@std@@@std@@YAPEAEQEAE0PEAEAEAV?$allocator@E@0@@Z`
- size: `53`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180017320`

## callees

- `0x180007814`

## pseudocode

```c
char *__fastcall std::_Uninitialized_move<unsigned char *>(void *a1, __int64 a2, char *a3)
{
  std::_Copy_memmove<_GUID *,_GUID *>(a1, a2, a3);
  return &a3[a2 - (_QWORD)a1];
}

```

## disassembly

```asm
0x1800174e8  mov     [rsp+arg_0], rbx
0x1800174ed  mov     [rsp+arg_8], rsi
0x1800174f2  push    rdi
0x1800174f3  sub     rsp, 20h
0x1800174f7  mov     rdi, r8
0x1800174fa  mov     rsi, rdx
0x1800174fd  mov     rbx, rcx
0x180017500  call    ??$_Copy_memmove@PEAU_GUID@@PEAU1@@std@@YAPEAU_GUID@@PEAU1@00@Z; std::_Copy_memmove<_GUID *,_GUID *>(_GUID *,_GUID *,_GUID *)
0x180017505  sub     rsi, rbx
0x180017508  mov     rbx, [rsp+28h+arg_0]
0x18001750d  lea     rax, [rdi+rsi]
0x180017511  mov     rsi, [rsp+28h+arg_8]
0x180017516  add     rsp, 20h
0x18001751a  pop     rdi
0x18001751b  retn
```
