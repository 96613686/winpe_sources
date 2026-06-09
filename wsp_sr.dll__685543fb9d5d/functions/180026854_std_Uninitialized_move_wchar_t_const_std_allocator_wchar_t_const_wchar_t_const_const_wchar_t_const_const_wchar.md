# std::_Uninitialized_move<wchar_t const * *,std::allocator<wchar_t const *>>(wchar_t const * * const,wchar_t const * * const,wchar_t const * *,std::allocator<wchar_t const *> &)

- ea: `0x180026854`
- end: `0x18002688d`
- name: `??$_Uninitialized_move@PEAPEB_WV?$allocator@PEB_W@std@@@std@@YAPEAPEB_WQEAPEB_W0PEAPEB_WAEAV?$allocator@PEB_W@0@@Z`
- size: `57`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800265d0`

## callees

- `0x180007814`

## pseudocode

```c
char *__fastcall std::_Uninitialized_move<wchar_t const * *>(void *a1, __int64 a2, char *a3)
{
  std::_Copy_memmove<_GUID *,_GUID *>(a1, a2, a3);
  return &a3[8 * ((a2 - (__int64)a1) >> 3)];
}

```

## disassembly

```asm
0x180026854  mov     [rsp+arg_0], rbx
0x180026859  mov     [rsp+arg_8], rsi
0x18002685e  push    rdi
0x18002685f  sub     rsp, 20h
0x180026863  mov     rsi, r8
0x180026866  mov     rdi, rdx
0x180026869  mov     rbx, rcx
0x18002686c  call    ??$_Copy_memmove@PEAU_GUID@@PEAU1@@std@@YAPEAU_GUID@@PEAU1@00@Z; std::_Copy_memmove<_GUID *,_GUID *>(_GUID *,_GUID *,_GUID *)
0x180026871  sub     rdi, rbx
0x180026874  mov     rbx, [rsp+28h+arg_0]
0x180026879  sar     rdi, 3
0x18002687d  lea     rax, [rsi+rdi*8]
0x180026881  mov     rsi, [rsp+28h+arg_8]
0x180026886  add     rsp, 20h
0x18002688a  pop     rdi
0x18002688b  retn
```
