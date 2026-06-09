# std::_Uninitialized_move<ushort *,std::allocator<ushort>>(ushort * const,ushort * const,ushort *,std::allocator<ushort> &)

- ea: `0x180008050`
- end: `0x180008088`
- name: `??$_Uninitialized_move@PEAGV?$allocator@G@std@@@std@@YAPEAGQEAG0PEAGAEAV?$allocator@G@0@@Z`
- size: `56`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180007a68`

## callees

- `0x180007814`

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
0x180008050  mov     [rsp+arg_0], rbx
0x180008055  mov     [rsp+arg_8], rsi
0x18000805a  push    rdi
0x18000805b  sub     rsp, 20h
0x18000805f  mov     rsi, r8
0x180008062  mov     rdi, rdx
0x180008065  mov     rbx, rcx
0x180008068  call    ??$_Copy_memmove@PEAU_GUID@@PEAU1@@std@@YAPEAU_GUID@@PEAU1@00@Z; std::_Copy_memmove<_GUID *,_GUID *>(_GUID *,_GUID *,_GUID *)
0x18000806d  sub     rdi, rbx
0x180008070  mov     rbx, [rsp+28h+arg_0]
0x180008075  sar     rdi, 1
0x180008078  lea     rax, [rsi+rdi*2]
0x18000807c  mov     rsi, [rsp+28h+arg_8]
0x180008081  add     rsp, 20h
0x180008085  pop     rdi
0x180008086  retn
```
