# std::_Uninitialized_move<ushort *,std::allocator<ushort>>(ushort * const,ushort * const,ushort *,std::allocator<ushort> &)

- ea: `0x180007f14`
- end: `0x180007f4b`
- name: `??$_Uninitialized_move@PEAGV?$allocator@G@std@@@std@@YAPEAGQEAG0PEAGAEAV?$allocator@G@0@@Z`
- size: `55`
- prototype: `char *__fastcall(void *, __int64, char *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180007988`

## callees

- `0x180007738`

## pseudocode

```c
char *__fastcall std::_Uninitialized_move<unsigned short *>(void *a1, __int64 a2, char *a3)
{
  std::_Copy_memmove<_GUID *,_GUID *>(a1, a2, a3);
  return &a3[2 * ((a2 - (__int64)a1) >> 1)];
}

```

## disassembly

```asm
0x180007f14  mov     [rsp+arg_0], rbx
0x180007f19  mov     [rsp+arg_8], rsi
0x180007f1e  push    rdi
0x180007f1f  sub     rsp, 20h
0x180007f23  mov     rsi, r8
0x180007f26  mov     rdi, rdx
0x180007f29  mov     rbx, rcx
0x180007f2c  call    ??$_Copy_memmove@PEAU_GUID@@PEAU1@@std@@YAPEAU_GUID@@PEAU1@00@Z; std::_Copy_memmove<_GUID *,_GUID *>(_GUID *,_GUID *,_GUID *)
0x180007f31  sub     rdi, rbx
0x180007f34  mov     rbx, [rsp+28h+arg_0]
0x180007f39  sar     rdi, 1
0x180007f3c  lea     rax, [rsi+rdi*2]
0x180007f40  mov     rsi, [rsp+28h+arg_8]
0x180007f45  add     rsp, 20h
0x180007f49  pop     rdi
0x180007f4a  retn
```
