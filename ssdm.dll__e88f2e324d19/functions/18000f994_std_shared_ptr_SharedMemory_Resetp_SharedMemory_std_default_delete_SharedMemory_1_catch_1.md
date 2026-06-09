# _std::shared_ptr_SharedMemory_::_Resetp_SharedMemory_std::default_delete_SharedMemory____::_1_::catch$1

- ea: `0x18000f994`
- end: `0x18000f9b4`
- name: `_std::shared_ptr_SharedMemory_::_Resetp_SharedMemory_std::default_delete_SharedMemory____::_1_::catch$1`
- size: `32`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180002ebc`
- `0x180005550`

## pseudocode

```c
void __fastcall __noreturn std::shared_ptr_SharedMemory_::_Resetp_SharedMemory_std::default_delete_SharedMemory____::_1_::catch_1(
        __int64 a1,
        __int64 a2)
{
  std::default_delete<SharedMemory>::operator()(a1, *(_QWORD *)(a2 + 72));
  throw;
}

```

## disassembly

```asm
0x18000f994  mov     [rsp+arg_8], rdx
0x18000f999  push    rbp
0x18000f99a  sub     rsp, 20h
0x18000f99e  mov     rbp, rdx
0x18000f9a1  mov     rdx, [rbp+48h]
0x18000f9a5  call    ??R?$default_delete@VSharedMemory@@@std@@QEBAXPEAVSharedMemory@@@Z; std::default_delete<SharedMemory>::operator()(SharedMemory *)
0x18000f9aa  xor     edx, edx; pThrowInfo
0x18000f9ac  xor     ecx, ecx; pExceptionObject
0x18000f9ae  call    _CxxThrowException_0
```
