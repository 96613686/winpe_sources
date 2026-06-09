# std::_Wrap_alloc<std::allocator<uchar>>::deallocate(uchar *,unsigned __int64)

- ea: `0x180003d68`
- end: `0x180003d70`
- name: `?deallocate@?$_Wrap_alloc@V?$allocator@E@std@@@std@@QEAAXPEAE_K@Z`
- size: `8`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18000be70`
- `0x18000bfe6`
- `0x18000c660`
- `0x18000c686`

## callees

- `0x1800026c0`

## pseudocode

```c
void __fastcall std::_Wrap_alloc<std::allocator<unsigned char>>::deallocate(__int64 a1, void *a2)
{
  operator delete(a2);
}

```

## disassembly

```asm
0x180003d68  mov     rcx, rdx; void *
0x180003d6b  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
