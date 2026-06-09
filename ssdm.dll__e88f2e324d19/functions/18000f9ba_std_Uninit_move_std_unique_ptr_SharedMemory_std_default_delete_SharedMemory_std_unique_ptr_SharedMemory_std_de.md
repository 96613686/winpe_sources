# _std::_Uninit_move_std::unique_ptr_SharedMemory_std::default_delete_SharedMemory______std::unique_ptr_SharedMemory_std::default_delete_SharedMemory______std::allocator_std::unique_ptr_SharedMemory_std::default_delete_SharedMemory______std::unique_ptr_SharedMemory_std::default_delete_SharedMemory______::_1_::catch$0

- ea: `0x18000f9ba`
- end: `0x18000f9ea`
- name: `_std::_Uninit_move_std::unique_ptr_SharedMemory_std::default_delete_SharedMemory______std::unique_ptr_SharedMemory_std::default_delete_SharedMemory______std::allocator_std::unique_ptr_SharedMemory_std::default_delete_SharedMemory______std::unique_ptr_SharedMemory_std::default_delete_SharedMemory______::_1_::catch$0`
- size: `48`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180002ebc`
- `0x180004204`
- `0x18000f9ba`

## pseudocode

```c
void __fastcall __noreturn std::_Uninit_move_std::unique_ptr_SharedMemory_std::default_delete_SharedMemory______std::unique_ptr_SharedMemory_std::default_delete_SharedMemory______std::allocator_std::unique_ptr_SharedMemory_std::default_delete_SharedMemory______std::unique_ptr_SharedMemory_std::default_delete_SharedMemory______::_1_::catch_0(
        __int64 a1,
        __int64 a2)
{
  __int64 i; // rbx

  for ( i = *(_QWORD *)(a2 + 72); i != *(_QWORD *)(a2 + 64); i += 8 )
    std::_Wrap_alloc<std::allocator<std::unique_ptr<SharedMemory>>>::destroy<std::unique_ptr<SharedMemory>>(a1, i);
  throw;
}

```

## disassembly

```asm
0x18000f9ba  mov     [rsp+arg_8], rdx
0x18000f9bf  push    rbx
0x18000f9c0  push    rbp
0x18000f9c1  sub     rsp, 28h
0x18000f9c5  mov     rbp, rdx
0x18000f9c8  mov     rbx, [rbp+48h]
0x18000f9cc  jmp     short loc_18000F9DA
0x18000f9ce  mov     rdx, rbx
0x18000f9d1  call    ??$destroy@V?$unique_ptr@VSharedMemory@@U?$default_delete@VSharedMemory@@@std@@@std@@@?$_Wrap_alloc@V?$allocator@V?$unique_ptr@VSharedMemory@@U?$default_delete@VSharedMemory@@@std@@@std@@@std@@@std@@QEAAXPEAV?$unique_ptr@VSharedMemory@@U?$default_delete@VSharedMemory@@@std@@@1@@Z; std::_Wrap_alloc<std::allocator<std::unique_ptr<SharedMemory>>>::destroy<std::unique_ptr<SharedMemory>>(std::unique_ptr<SharedMemory> *)
0x18000f9d6  add     rbx, 8
0x18000f9da  cmp     rbx, [rbp+40h]
0x18000f9de  jnz     short loc_18000F9CE
0x18000f9e0  xor     edx, edx; pThrowInfo
0x18000f9e2  xor     ecx, ecx; pExceptionObject
0x18000f9e4  call    _CxxThrowException_0
```
