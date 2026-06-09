# std::_Ref_count_del<SharedMemory,std::default_delete<SharedMemory>>::_Delete_this(void)

- ea: `0x180007100`
- end: `0x18000711f`
- name: `?_Delete_this@?$_Ref_count_del@VSharedMemory@@U?$default_delete@VSharedMemory@@@std@@@std@@EEAAXXZ`
- size: `31`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180007100`
- `0x180010010`

## pseudocode

```c
__int64 __fastcall std::_Ref_count_del<SharedMemory,std::default_delete<SharedMemory>>::_Delete_this(__int64 a1)
{
  __int64 result; // rax

  if ( a1 )
    return (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 16LL))(a1, 1);
  return result;
}

```

## disassembly

```asm
0x180007100  sub     rsp, 28h
0x180007104  test    rcx, rcx
0x180007107  jz      short loc_18000711A
0x180007109  mov     rax, [rcx]
0x18000710c  mov     edx, 1
0x180007111  mov     rax, [rax+10h]
0x180007115  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000711a  add     rsp, 28h
0x18000711e  retn
```
