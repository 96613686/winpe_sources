# std::_Tree<std::_Tset_traits<ushort const *,CFilterIgnoreSet::LPCWStrCompare,std::allocator<ushort const *>,0>>::_Lrotate(std::_Tree_node<ushort const *,void *> *)

- ea: `0x1800197a4`
- end: `0x1800197ed`
- name: `?_Lrotate@?$_Tree@V?$_Tset_traits@PEBGULPCWStrCompare@CFilterIgnoreSet@@V?$allocator@PEBG@std@@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@PEBGPEAX@2@@Z`
- size: `73`
- prototype: `_QWORD *__fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000d0b8`
- `0x18001718c`

## callees

- `0x1800197a4`

## pseudocode

```c
_QWORD *__fastcall std::_Tree<std::_Tset_traits<unsigned short const *,CFilterIgnoreSet::LPCWStrCompare,std::allocator<unsigned short const *>,0>>::_Lrotate(
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
0x1800197a4  mov     r8, [rdx+10h]
0x1800197a8  mov     rax, [r8]
0x1800197ab  mov     [rdx+10h], rax
0x1800197af  mov     rax, [r8]
0x1800197b2  cmp     byte ptr [rax+19h], 0
0x1800197b6  jnz     short loc_1800197BC
0x1800197b8  mov     [rax+8], rdx
0x1800197bc  mov     rax, [rdx+8]
0x1800197c0  mov     [r8+8], rax
0x1800197c4  mov     rax, [rcx]
0x1800197c7  cmp     rdx, [rax+8]
0x1800197cb  jnz     short loc_1800197D3
0x1800197cd  mov     [rax+8], r8
0x1800197d1  jmp     short loc_1800197E5
0x1800197d3  mov     rax, [rdx+8]
0x1800197d7  cmp     rdx, [rax]
0x1800197da  jnz     short loc_1800197E1
0x1800197dc  mov     [rax], r8
0x1800197df  jmp     short loc_1800197E5
0x1800197e1  mov     [rax+10h], r8
0x1800197e5  mov     [r8], rdx
0x1800197e8  mov     [rdx+8], r8
0x1800197ec  retn
```
