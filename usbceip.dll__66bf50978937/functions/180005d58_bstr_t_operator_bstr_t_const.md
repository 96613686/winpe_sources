# _bstr_t::operator=(_bstr_t const &)

- ea: `0x180005d58`
- end: `0x180005d8d`
- name: `??4_bstr_t@@QEAAAEAV0@AEBV0@@Z`
- size: `53`
- prototype: `_bstr_t *__fastcall(_bstr_t *, __int64)`
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x180005e94`
- `0x180006c28`
- `0x180007754`
- `0x180007b44`
- `0x180008730`
- `0x180009260`
- `0x18000b5c8`
- `0x18000b96c`

## callees

- `0x180003fec`
- `0x180005d58`

## pseudocode

```c
_bstr_t *__fastcall _bstr_t::operator=(_bstr_t *a1, __int64 a2)
{
  if ( *(_QWORD *)a2 )
    _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)a2 + 16LL));
  _bstr_t::_Free(a1);
  *(_QWORD *)a1 = *(_QWORD *)a2;
  return a1;
}

```

## disassembly

```asm
0x180005d58  mov     [rsp+arg_0], rbx
0x180005d5d  push    rdi
0x180005d5e  sub     rsp, 20h
0x180005d62  mov     rax, [rdx]
0x180005d65  mov     rdi, rdx
0x180005d68  mov     rbx, rcx
0x180005d6b  test    rax, rax
0x180005d6e  jz      short loc_180005D74
0x180005d70  lock inc dword ptr [rax+10h]
0x180005d74  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180005d79  mov     rax, [rdi]
0x180005d7c  mov     [rbx], rax
0x180005d7f  mov     rax, rbx
0x180005d82  mov     rbx, [rsp+28h+arg_0]
0x180005d87  add     rsp, 20h
0x180005d8b  pop     rdi
0x180005d8c  retn
```
