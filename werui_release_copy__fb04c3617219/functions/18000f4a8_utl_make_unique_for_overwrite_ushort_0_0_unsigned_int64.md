# utl::make_unique_for_overwrite<ushort [0],0>(unsigned __int64)

- ea: `0x18000f4a8`
- end: `0x18000f4df`
- name: `??$make_unique_for_overwrite@$$BY0A@G$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@utl@@@0@_K@Z`
- size: `55`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180012d68`

## callees

- `0x18000322c`

## pseudocode

```c
_QWORD *__fastcall utl::make_unique_for_overwrite<unsigned short [0],0>(_QWORD *a1, unsigned __int64 a2)
{
  unsigned __int64 v3; // rax

  v3 = 2 * a2;
  if ( !is_mul_ok(a2, 2u) )
    v3 = -1;
  *a1 = operator new[](v3, (const struct std::nothrow_t *)std::nothrow);
  return a1;
}

```

## disassembly

```asm
0x18000f4a8  push    rbx
0x18000f4aa  sub     rsp, 20h
0x18000f4ae  mov     rbx, rcx
0x18000f4b1  mov     eax, 2
0x18000f4b6  mul     rdx
0x18000f4b9  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000f4c0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000f4c7  cmovb   rax, rcx
0x18000f4cb  mov     rcx, rax; unsigned __int64
0x18000f4ce  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000f4d3  mov     [rbx], rax
0x18000f4d6  mov     rax, rbx
0x18000f4d9  add     rsp, 20h
0x18000f4dd  pop     rbx
0x18000f4de  retn
```
