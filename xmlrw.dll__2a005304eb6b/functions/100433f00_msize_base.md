# _msize_base

- ea: `0x100433f00`
- end: `0x100433f39`
- name: `_msize_base`
- size: `57`
- prototype: `size_t __cdecl(void *Block)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x10043043c`

## callees

- `0x10042e5d8`
- `0x10042e738`
- `0x100433f00`

## import_xrefs

- `KERNEL32!HeapSize` at `0x100433f32`

## pseudocode

```c
size_t __cdecl msize_base(void *Block)
{
  if ( Block )
    return HeapSize(_acrt_heap, 0, Block);
  *errno() = 22;
  invalid_parameter_noinfo();
  return -1;
}

```

## disassembly

```asm
0x100433f00  sub     rsp, 28h
0x100433f04  test    rcx, rcx
0x100433f07  jnz     short loc_100433F22
0x100433f09  call    _errno
0x100433f0e  mov     dword ptr [rax], 16h
0x100433f14  call    _invalid_parameter_noinfo
0x100433f19  or      rax, 0FFFFFFFFFFFFFFFFh
0x100433f1d  add     rsp, 28h
0x100433f21  retn
0x100433f22  mov     r8, rcx
0x100433f25  xor     edx, edx
0x100433f27  mov     rcx, cs:__acrt_heap
0x100433f2e  add     rsp, 28h
0x100433f32  jmp     cs:__imp_HeapSize
```
