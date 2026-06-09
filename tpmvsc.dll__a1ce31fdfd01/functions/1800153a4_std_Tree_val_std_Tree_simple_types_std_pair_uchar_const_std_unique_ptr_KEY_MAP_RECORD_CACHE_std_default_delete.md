# std::_Tree_val<std::_Tree_simple_types<std::pair<uchar const,std::unique_ptr<KEY_MAP_RECORD_CACHE,std::default_delete<KEY_MAP_RECORD_CACHE>>>>>::_Rrotate(std::_Tree_node<std::pair<uchar const,std::unique_ptr<KEY_MAP_RECORD_CACHE,std::default_delete<KEY_MAP_RECORD_CACHE>>>,void *> *)

- ea: `0x1800153a4`
- end: `0x1800153ef`
- name: `?_Rrotate@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBEV?$unique_ptr@UKEY_MAP_RECORD_CACHE@@U?$default_delete@UKEY_MAP_RECORD_CACHE@@@std@@@std@@@std@@@std@@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CBEV?$unique_ptr@UKEY_MAP_RECORD_CACHE@@U?$default_delete@UKEY_MAP_RECORD_CACHE@@@std@@@std@@@std@@PEAX@2@@Z`
- size: `75`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180014d78`
- `0x1800151a0`

## callees

- `0x1800153a4`

## pseudocode

```c
_QWORD *__fastcall std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned char const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>>>::_Rrotate(
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
0x1800153a4  mov     r8, [rdx]
0x1800153a7  mov     rax, [r8+10h]
0x1800153ab  mov     [rdx], rax
0x1800153ae  mov     rax, [r8+10h]
0x1800153b2  cmp     byte ptr [rax+19h], 0
0x1800153b6  jnz     short loc_1800153BC
0x1800153b8  mov     [rax+8], rdx
0x1800153bc  mov     rax, [rdx+8]
0x1800153c0  mov     [r8+8], rax
0x1800153c4  mov     rax, [rcx]
0x1800153c7  cmp     rdx, [rax+8]
0x1800153cb  jnz     short loc_1800153D3
0x1800153cd  mov     [rax+8], r8
0x1800153d1  jmp     short loc_1800153E6
0x1800153d3  mov     rax, [rdx+8]
0x1800153d7  cmp     rdx, [rax+10h]
0x1800153db  jnz     short loc_1800153E3
0x1800153dd  mov     [rax+10h], r8
0x1800153e1  jmp     short loc_1800153E6
0x1800153e3  mov     [rax], r8
0x1800153e6  mov     [r8+10h], rdx
0x1800153ea  mov     [rdx+8], r8
0x1800153ee  retn
```
