# utl::make_unique_for_overwrite<wchar_t [0],0>(unsigned __int64)

- ea: `0x180003b58`
- end: `0x180003b8f`
- name: `??$make_unique_for_overwrite@$$BY0A@_W$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@0@_K@Z`
- size: `55`
- prototype: `_QWORD *__fastcall(_QWORD *, unsigned __int64)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180003b98`
- `0x180004420`
- `0x18000462c`
- `0x180004e1c`
- `0x180005a9c`
- `0x180005d24`

## callees

- `0x180001cec`

## pseudocode

```c
_QWORD *__fastcall utl::make_unique_for_overwrite<wchar_t [0],0>(_QWORD *a1, unsigned __int64 a2)
{
  unsigned __int64 v3; // rax

  v3 = 2 * a2;
  if ( !is_mul_ok(a2, 2u) )
    v3 = -1;
  *a1 = operator new[](v3, (const struct std::nothrow_t *)&std::nothrow);
  return a1;
}

```

## disassembly

```asm
0x180003b58  push    rbx
0x180003b5a  sub     rsp, 20h
0x180003b5e  mov     rbx, rcx
0x180003b61  mov     eax, 2
0x180003b66  mul     rdx
0x180003b69  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180003b70  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180003b77  cmovb   rax, rcx
0x180003b7b  mov     rcx, rax; unsigned __int64
0x180003b7e  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180003b83  mov     [rbx], rax
0x180003b86  mov     rax, rbx
0x180003b89  add     rsp, 20h
0x180003b8d  pop     rbx
0x180003b8e  retn
```
