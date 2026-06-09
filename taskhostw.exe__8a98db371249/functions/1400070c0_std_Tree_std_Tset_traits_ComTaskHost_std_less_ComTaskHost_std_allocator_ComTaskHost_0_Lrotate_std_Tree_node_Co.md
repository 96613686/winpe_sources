# std::_Tree<std::_Tset_traits<ComTaskHost *,std::less<ComTaskHost *>,std::allocator<ComTaskHost *>,0>>::_Lrotate(std::_Tree_node<ComTaskHost *,void *> *)

- ea: `0x1400070c0`
- end: `0x140007109`
- name: `?_Lrotate@?$_Tree@V?$_Tset_traits@PEAVComTaskHost@@U?$less@PEAVComTaskHost@@@std@@V?$allocator@PEAVComTaskHost@@@3@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@PEAVComTaskHost@@PEAX@2@@Z`
- size: `73`
- prototype: `_QWORD *__fastcall(__int64, __int64)`
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400045d0`
- `0x140005340`
- `0x140005650`

## callees

- `0x1400070c0`

## pseudocode

```c
_QWORD *__fastcall std::_Tree<std::_Tset_traits<ComTaskHost *,std::less<ComTaskHost *>,std::allocator<ComTaskHost *>,0>>::_Lrotate(
        __int64 a1,
        __int64 a2)
{
  _QWORD *v2; // r8
  _QWORD *result; // rax

  v2 = *(_QWORD **)(a2 + 16);
  *(_QWORD *)(a2 + 16) = *v2;
  if ( !*(_BYTE *)(*v2 + 25LL) )
    *(_QWORD *)(*v2 + 8LL) = a2;
  v2[1] = *(_QWORD *)(a2 + 8);
  result = *(_QWORD **)a1;
  if ( a2 == *(_QWORD *)(*(_QWORD *)a1 + 8LL) )
  {
    result[1] = v2;
  }
  else
  {
    result = *(_QWORD **)(a2 + 8);
    if ( a2 == *result )
      *result = v2;
    else
      result[2] = v2;
  }
  *v2 = a2;
  *(_QWORD *)(a2 + 8) = v2;
  return result;
}

```

## disassembly

```asm
0x1400070c0  mov     r8, [rdx+10h]
0x1400070c4  mov     rax, [r8]
0x1400070c7  mov     [rdx+10h], rax
0x1400070cb  mov     rax, [r8]
0x1400070ce  cmp     byte ptr [rax+19h], 0
0x1400070d2  jnz     short loc_1400070D8
0x1400070d4  mov     [rax+8], rdx
0x1400070d8  mov     rax, [rdx+8]
0x1400070dc  mov     [r8+8], rax
0x1400070e0  mov     rax, [rcx]
0x1400070e3  cmp     rdx, [rax+8]
0x1400070e7  jnz     short loc_1400070EF
0x1400070e9  mov     [rax+8], r8
0x1400070ed  jmp     short loc_140007101
0x1400070ef  mov     rax, [rdx+8]
0x1400070f3  cmp     rdx, [rax]
0x1400070f6  jnz     short loc_1400070FD
0x1400070f8  mov     [rax], r8
0x1400070fb  jmp     short loc_140007101
0x1400070fd  mov     [rax+10h], r8
0x140007101  mov     [r8], rdx
0x140007104  mov     [rdx+8], r8
0x140007108  retn
```
