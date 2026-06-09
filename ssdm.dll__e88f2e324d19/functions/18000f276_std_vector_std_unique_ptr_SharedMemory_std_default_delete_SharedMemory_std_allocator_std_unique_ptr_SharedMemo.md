# _std::vector_std::unique_ptr_SharedMemory_std::default_delete_SharedMemory____std::allocator_std::unique_ptr_SharedMemory_std::default_delete_SharedMemory_______::_Reallocate_::_1_::catch$3

- ea: `0x18000f276`
- end: `0x18000f296`
- name: `_std::vector_std::unique_ptr_SharedMemory_std::default_delete_SharedMemory____std::allocator_std::unique_ptr_SharedMemory_std::default_delete_SharedMemory_______::_Reallocate_::_1_::catch$3`
- size: `32`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180002ebc`
- `0x180007810`

## pseudocode

```c
void __fastcall __noreturn std::vector_std::unique_ptr_SharedMemory_std::default_delete_SharedMemory____std::allocator_std::unique_ptr_SharedMemory_std::default_delete_SharedMemory_______::_Reallocate_::_1_::catch_3(
        __int64 a1,
        __int64 a2)
{
  std::_Wrap_alloc<std::allocator<unsigned char>>::deallocate(a1, *(_QWORD *)(a2 + 104));
  throw;
}

```

## disassembly

```asm
0x18000f276  mov     [rsp+arg_8], rdx
0x18000f27b  push    rbp
0x18000f27c  sub     rsp, 30h
0x18000f280  mov     rbp, rdx
0x18000f283  mov     rdx, [rbp+68h]
0x18000f287  call    ?deallocate@?$_Wrap_alloc@V?$allocator@E@std@@@std@@QEAAXPEAE_K@Z; std::_Wrap_alloc<std::allocator<uchar>>::deallocate(uchar *,unsigned __int64)
0x18000f28c  xor     edx, edx; pThrowInfo
0x18000f28e  xor     ecx, ecx; pExceptionObject
0x18000f290  call    _CxxThrowException_0
```
