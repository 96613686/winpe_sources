# core::slice::copy_from_slice_impl_usize_

- ea: `0x1400132c0`
- end: `0x1400132f2`
- name: `core::slice::copy_from_slice_impl_usize_`
- size: `50`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140013320`

## callees

- `0x1400132c0`
- `0x140017b00`
- `0x1400187f0`

## pseudocode

```c
void *__fastcall core::slice::copy_from_slice_impl_usize_(void *a1, __int64 a2, const void *a3, __int64 a4)
{
  if ( a2 != a4 )
    RNvNvNtCs9MWeMO1rkJG_4core5slice20copy_from_slice_impl17len_mismatch_fail(a2, a4, &off_14001C070, a4);
  return memmove(a1, a3, 8 * a2);
}

```

## disassembly

```asm
0x1400132c0  sub     rsp, 28h
0x1400132c4  mov     rax, rdx
0x1400132c7  cmp     rdx, r9
0x1400132ca  jnz     short loc_1400132DF
0x1400132cc  shl     rax, 3
0x1400132d0  mov     rdx, r8; Src
0x1400132d3  mov     r8, rax; Size
0x1400132d6  add     rsp, 28h
0x1400132da  jmp     memmove
0x1400132df  lea     r8, off_14001C070; "seh_unwind\\src\\lib.rs"
0x1400132e6  mov     rcx, rax
0x1400132e9  mov     rdx, r9
0x1400132ec  call    _RNvNvNtCs9MWeMO1rkJG_4core5slice20copy_from_slice_impl17len_mismatch_fail
```
