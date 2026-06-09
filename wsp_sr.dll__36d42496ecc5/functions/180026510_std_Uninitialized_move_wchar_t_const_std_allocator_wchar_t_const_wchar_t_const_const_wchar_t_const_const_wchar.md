# std::_Uninitialized_move<wchar_t const * *,std::allocator<wchar_t const *>>(wchar_t const * * const,wchar_t const * * const,wchar_t const * *,std::allocator<wchar_t const *> &)

- ea: `0x180026510`
- end: `0x180026548`
- name: `??$_Uninitialized_move@PEAPEB_WV?$allocator@PEB_W@std@@@std@@YAPEAPEB_WQEAPEB_W0PEAPEB_WAEAV?$allocator@PEB_W@0@@Z`
- size: `56`
- prototype: `char *__fastcall(void *, __int64, char *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180026290`

## callees

- `0x180007738`

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
0x180026510  mov     [rsp+arg_0], rbx
0x180026515  mov     [rsp+arg_8], rsi
0x18002651a  push    rdi
0x18002651b  sub     rsp, 20h
0x18002651f  mov     rsi, r8
0x180026522  mov     rdi, rdx
0x180026525  mov     rbx, rcx
0x180026528  call    ??$_Copy_memmove@PEAU_GUID@@PEAU1@@std@@YAPEAU_GUID@@PEAU1@00@Z; std::_Copy_memmove<_GUID *,_GUID *>(_GUID *,_GUID *,_GUID *)
0x18002652d  sub     rdi, rbx
0x180026530  mov     rbx, [rsp+28h+arg_0]
0x180026535  sar     rdi, 3
0x180026539  lea     rax, [rsi+rdi*8]
0x18002653d  mov     rsi, [rsp+28h+arg_8]
0x180026542  add     rsp, 20h
0x180026546  pop     rdi
0x180026547  retn
```
