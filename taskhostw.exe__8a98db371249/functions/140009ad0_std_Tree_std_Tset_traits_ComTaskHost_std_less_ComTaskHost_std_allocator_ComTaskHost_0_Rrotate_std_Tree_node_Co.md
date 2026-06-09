# std::_Tree<std::_Tset_traits<ComTaskHost *,std::less<ComTaskHost *>,std::allocator<ComTaskHost *>,0>>::_Rrotate(std::_Tree_node<ComTaskHost *,void *> *)

- ea: `0x140009ad0`
- end: `0x140009b1b`
- name: `?_Rrotate@?$_Tree@V?$_Tset_traits@PEAVComTaskHost@@U?$less@PEAVComTaskHost@@@std@@V?$allocator@PEAVComTaskHost@@@3@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@PEAVComTaskHost@@PEAX@2@@Z`
- size: `75`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400045d0`
- `0x140005340`
- `0x140005650`

## callees

- `0x140009ad0`

## pseudocode

```c
_QWORD *__fastcall std::_Tree<std::_Tset_traits<ComTaskHost *,std::less<ComTaskHost *>,std::allocator<ComTaskHost *>,0>>::_Rrotate(
        __int64 a1,
        _QWORD *a2)
{
  __int64 v2; // r8
  __int64 v3; // rax
  _QWORD *result; // rax

  v2 = *a2;
  *a2 = *(_QWORD *)(*a2 + 16LL);
  v3 = *(_QWORD *)(v2 + 16);
  if ( !*(_BYTE *)(v3 + 25) )
    *(_QWORD *)(v3 + 8) = a2;
  *(_QWORD *)(v2 + 8) = a2[1];
  result = *(_QWORD **)a1;
  if ( a2 == *(_QWORD **)(*(_QWORD *)a1 + 8LL) )
  {
    result[1] = v2;
  }
  else
  {
    result = (_QWORD *)a2[1];
    if ( a2 == (_QWORD *)result[2] )
      result[2] = v2;
    else
      *result = v2;
  }
  *(_QWORD *)(v2 + 16) = a2;
  a2[1] = v2;
  return result;
}

```

## disassembly

```asm
0x140009ad0  mov     r8, [rdx]
0x140009ad3  mov     rax, [r8+10h]
0x140009ad7  mov     [rdx], rax
0x140009ada  mov     rax, [r8+10h]
0x140009ade  cmp     byte ptr [rax+19h], 0
0x140009ae2  jnz     short loc_140009AE8
0x140009ae4  mov     [rax+8], rdx
0x140009ae8  mov     rax, [rdx+8]
0x140009aec  mov     [r8+8], rax
0x140009af0  mov     rax, [rcx]
0x140009af3  cmp     rdx, [rax+8]
0x140009af7  jnz     short loc_140009AFF
0x140009af9  mov     [rax+8], r8
0x140009afd  jmp     short loc_140009B12
0x140009aff  mov     rax, [rdx+8]
0x140009b03  cmp     rdx, [rax+10h]
0x140009b07  jnz     short loc_140009B0F
0x140009b09  mov     [rax+10h], r8
0x140009b0d  jmp     short loc_140009B12
0x140009b0f  mov     [rax], r8
0x140009b12  mov     [r8+10h], rdx
0x140009b16  mov     [rdx+8], r8
0x140009b1a  retn
```
