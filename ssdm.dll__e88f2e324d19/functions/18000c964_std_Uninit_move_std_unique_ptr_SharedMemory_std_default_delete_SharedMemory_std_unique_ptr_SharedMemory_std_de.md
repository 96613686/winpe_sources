# std::_Uninit_move<std::unique_ptr<SharedMemory,std::default_delete<SharedMemory>> *,std::unique_ptr<SharedMemory,std::default_delete<SharedMemory>> *,std::allocator<std::unique_ptr<SharedMemory,std::default_delete<SharedMemory>>>,std::unique_ptr<SharedMemory,std::default_delete<SharedMemory>>>(std::unique_ptr<SharedMemory,std::default_delete<SharedMemory>> *,std::unique_ptr<SharedMemory,std::default_delete<SharedMemory>> *,std::unique_ptr<SharedMemory,std::default_delete<SharedMemory>> *,std::_Wrap_alloc<std::allocator<std::unique_ptr<SharedMemory,std::default_delete<SharedMemory>>>> &,std::unique_ptr<SharedMemory,std::default_delete<SharedMemory>> *,std::_Nonscalar_ptr_iterator_tag)

- ea: `0x18000c964`
- end: `0x18000c9a0`
- name: `??$_Uninit_move@PEAV?$unique_ptr@VSharedMemory@@U?$default_delete@VSharedMemory@@@std@@@std@@PEAV12@V?$allocator@V?$unique_ptr@VSharedMemory@@U?$default_delete@VSharedMemory@@@std@@@std@@@2@V12@@std@@YAPEAV?$unique_ptr@VSharedMemory@@U?$default_delete@VSharedMemory@@@std@@@0@PEAV10@00AEAU?$_Wrap_alloc@V?$allocator@V?$unique_ptr@VSharedMemory@@U?$default_delete@VSharedMemory@@@std@@@std@@@std@@@0@0U_Nonscalar_ptr_iterator_tag@0@@Z`
- size: `60`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000d654`

## callees

- `0x18000c964`

## pseudocode

```c
_QWORD *__fastcall std::_Uninit_move<std::unique_ptr<SharedMemory> *,std::unique_ptr<SharedMemory> *,std::allocator<std::unique_ptr<SharedMemory>>,std::unique_ptr<SharedMemory>>(
        __int64 *a1,
        __int64 *a2,
        _QWORD *a3)
{
  __int64 v3; // rax

  while ( a1 != a2 )
  {
    v3 = *a1;
    *a1 = 0;
    *a3++ = v3;
    ++a1;
  }
  return a3;
}

```

## disassembly

```asm
0x18000c964  mov     [rsp+arg_18], r9
0x18000c969  mov     [rsp+arg_10], r8
0x18000c96e  sub     rsp, 28h
0x18000c972  mov     [rsp+28h+arg_18], r8
0x18000c977  jmp     short loc_18000C993
0x18000c979  mov     rax, [rcx]
0x18000c97c  mov     qword ptr [rcx], 0
0x18000c983  mov     [r8], rax
0x18000c986  add     r8, 8
0x18000c98a  mov     [rsp+28h+arg_10], r8
0x18000c98f  add     rcx, 8
0x18000c993  cmp     rcx, rdx
0x18000c996  jnz     short loc_18000C979
0x18000c998  mov     rax, r8
0x18000c99b  add     rsp, 28h
0x18000c99f  retn
```
