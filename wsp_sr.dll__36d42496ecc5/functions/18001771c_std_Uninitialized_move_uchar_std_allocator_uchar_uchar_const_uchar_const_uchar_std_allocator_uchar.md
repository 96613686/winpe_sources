# std::_Uninitialized_move<uchar *,std::allocator<uchar>>(uchar * const,uchar * const,uchar *,std::allocator<uchar> &)

- ea: `0x18001771c`
- end: `0x180017750`
- name: `??$_Uninitialized_move@PEAEV?$allocator@E@std@@@std@@YAPEAEQEAE0PEAEAEAV?$allocator@E@0@@Z`
- size: `52`
- prototype: `char *__fastcall(void *, __int64, char *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001755c`

## callees

- `0x180007738`

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
0x18001771c  mov     [rsp+arg_0], rbx
0x180017721  mov     [rsp+arg_8], rsi
0x180017726  push    rdi
0x180017727  sub     rsp, 20h
0x18001772b  mov     rdi, r8
0x18001772e  mov     rsi, rdx
0x180017731  mov     rbx, rcx
0x180017734  call    ??$_Copy_memmove@PEAU_GUID@@PEAU1@@std@@YAPEAU_GUID@@PEAU1@00@Z; std::_Copy_memmove<_GUID *,_GUID *>(_GUID *,_GUID *,_GUID *)
0x180017739  sub     rsi, rbx
0x18001773c  mov     rbx, [rsp+28h+arg_0]
0x180017741  lea     rax, [rdi+rsi]
0x180017745  mov     rsi, [rsp+28h+arg_8]
0x18001774a  add     rsp, 20h
0x18001774e  pop     rdi
0x18001774f  retn
```
