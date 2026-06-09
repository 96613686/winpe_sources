# std::_Tree<std::_Tset_traits<ushort const *,CFilterIgnoreSet::LPCWStrCompare,std::allocator<ushort const *>,0>>::~_Tree<std::_Tset_traits<ushort const *,CFilterIgnoreSet::LPCWStrCompare,std::allocator<ushort const *>,0>>(void)

- ea: `0x18001738c`
- end: `0x1800173ba`
- name: `??1?$_Tree@V?$_Tset_traits@PEBGULPCWStrCompare@CFilterIgnoreSet@@V?$allocator@PEBG@std@@$0A@@std@@@std@@QEAA@XZ`
- size: `46`
- prototype: `__int64 __fastcall(_QWORD **)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180017404`
- `0x180017434`
- `0x18001e0e1`
- `0x18001ec2a`

## callees

- `0x1800173c0`
- `0x180019890`

## pseudocode

```c
__int64 __fastcall std::_Tree<std::_Tset_traits<unsigned short const *,CFilterIgnoreSet::LPCWStrCompare,std::allocator<unsigned short const *>,0>>::~_Tree<std::_Tset_traits<unsigned short const *,CFilterIgnoreSet::LPCWStrCompare,std::allocator<unsigned short const *>,0>>(
        _QWORD **a1)
{
  char v3; // [rsp+38h] [rbp+10h] BYREF

  std::_Tree<std::_Tset_traits<unsigned short const *,CFilterIgnoreSet::LPCWStrCompare,std::allocator<unsigned short const *>,0>>::erase(
    a1,
    &v3,
    **a1,
    *a1);
  return std::_Tree_buy<unsigned short const *>::~_Tree_buy<unsigned short const *>(a1);
}

```

## disassembly

```asm
0x18001738c  mov     [rsp+arg_0], rcx
0x180017391  push    rbx
0x180017392  sub     rsp, 20h
0x180017396  mov     rbx, rcx
0x180017399  mov     r8, [rcx]
0x18001739c  mov     r9, r8
0x18001739f  mov     r8, [r8]
0x1800173a2  lea     rdx, [rsp+28h+arg_8]
0x1800173a7  call    ?erase@?$_Tree@V?$_Tset_traits@PEBGULPCWStrCompare@CFilterIgnoreSet@@V?$allocator@PEBG@std@@$0A@@std@@@std@@QEAA?AV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@PEBG@std@@@std@@@2@V32@0@Z; std::_Tree<std::_Tset_traits<ushort const *,CFilterIgnoreSet::LPCWStrCompare,std::allocator<ushort const *>,0>>::erase(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<ushort const *>>>,std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<ushort const *>>>)
0x1800173ac  nop
0x1800173ad  mov     rcx, rbx
0x1800173b0  add     rsp, 20h
0x1800173b4  pop     rbx
0x1800173b5  jmp     ??1?$_Tree_buy@PEBGV?$allocator@PEBG@std@@@std@@QEAA@XZ; std::_Tree_buy<ushort const *>::~_Tree_buy<ushort const *>(void)
```
