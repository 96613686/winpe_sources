# std::_Tree_temp_node<std::allocator<std::_Tree_node<_bstr_t,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<_bstr_t,void *>>>(void)

- ea: `0x18000bcf4`
- end: `0x18000bd1c`
- name: `??1?$_Tree_temp_node@V?$allocator@U?$_Tree_node@V_bstr_t@@PEAX@std@@@std@@@std@@QEAA@XZ`
- size: `40`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000bab4`

## callees

- `0x180003fec`
- `0x18000bcd0`
- `0x18000bcf4`

## pseudocode

```c
__int64 __fastcall std::_Tree_temp_node<std::allocator<std::_Tree_node<_bstr_t,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<_bstr_t,void *>>>(
        __int64 a1)
{
  __int64 v2; // rcx

  v2 = *(_QWORD *)(a1 + 8);
  if ( v2 )
    _bstr_t::_Free((_bstr_t *)(v2 + 32));
  return std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<_bstr_t,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<_bstr_t,void *>>>(a1);
}

```

## disassembly

```asm
0x18000bcf4  push    rbx
0x18000bcf6  sub     rsp, 20h
0x18000bcfa  mov     rbx, rcx
0x18000bcfd  mov     rcx, [rcx+8]
0x18000bd01  test    rcx, rcx
0x18000bd04  jz      short loc_18000BD0F
0x18000bd06  add     rcx, 20h ; ' '; this
0x18000bd0a  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000bd0f  mov     rcx, rbx
0x18000bd12  add     rsp, 20h
0x18000bd16  pop     rbx
0x18000bd17  jmp     ??1?$_Alloc_construct_ptr@V?$allocator@U?$_Tree_node@V_bstr_t@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<_bstr_t,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<_bstr_t,void *>>>(void)
```
