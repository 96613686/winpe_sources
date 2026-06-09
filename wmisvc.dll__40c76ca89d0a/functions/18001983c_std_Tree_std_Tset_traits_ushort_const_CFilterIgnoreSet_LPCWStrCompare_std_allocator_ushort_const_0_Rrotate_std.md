# std::_Tree<std::_Tset_traits<ushort const *,CFilterIgnoreSet::LPCWStrCompare,std::allocator<ushort const *>,0>>::_Rrotate(std::_Tree_node<ushort const *,void *> *)

- ea: `0x18001983c`
- end: `0x180019887`
- name: `?_Rrotate@?$_Tree@V?$_Tset_traits@PEBGULPCWStrCompare@CFilterIgnoreSet@@V?$allocator@PEBG@std@@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@PEBGPEAX@2@@Z`
- size: `75`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000d0b8`
- `0x18001718c`

## callees

- `0x18001983c`

## pseudocode

```c
_QWORD *__fastcall std::_Tree<std::_Tset_traits<unsigned short const *,CFilterIgnoreSet::LPCWStrCompare,std::allocator<unsigned short const *>,0>>::_Rrotate(
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
0x18001983c  mov     r8, [rdx]
0x18001983f  mov     rax, [r8+10h]
0x180019843  mov     [rdx], rax
0x180019846  mov     rax, [r8+10h]
0x18001984a  cmp     byte ptr [rax+19h], 0
0x18001984e  jnz     short loc_180019854
0x180019850  mov     [rax+8], rdx
0x180019854  mov     rax, [rdx+8]
0x180019858  mov     [r8+8], rax
0x18001985c  mov     rax, [rcx]
0x18001985f  cmp     rdx, [rax+8]
0x180019863  jnz     short loc_18001986B
0x180019865  mov     [rax+8], r8
0x180019869  jmp     short loc_18001987E
0x18001986b  mov     rax, [rdx+8]
0x18001986f  cmp     rdx, [rax+10h]
0x180019873  jnz     short loc_18001987B
0x180019875  mov     [rax+10h], r8
0x180019879  jmp     short loc_18001987E
0x18001987b  mov     [rax], r8
0x18001987e  mov     [r8+10h], rdx
0x180019882  mov     [rdx+8], r8
0x180019886  retn
```
