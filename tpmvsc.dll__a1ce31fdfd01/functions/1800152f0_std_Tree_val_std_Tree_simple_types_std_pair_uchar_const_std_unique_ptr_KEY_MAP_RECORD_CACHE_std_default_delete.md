# std::_Tree_val<std::_Tree_simple_types<std::pair<uchar const,std::unique_ptr<KEY_MAP_RECORD_CACHE,std::default_delete<KEY_MAP_RECORD_CACHE>>>>>::_Lrotate(std::_Tree_node<std::pair<uchar const,std::unique_ptr<KEY_MAP_RECORD_CACHE,std::default_delete<KEY_MAP_RECORD_CACHE>>>,void *> *)

- ea: `0x1800152f0`
- end: `0x180015339`
- name: `?_Lrotate@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBEV?$unique_ptr@UKEY_MAP_RECORD_CACHE@@U?$default_delete@UKEY_MAP_RECORD_CACHE@@@std@@@std@@@std@@@std@@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CBEV?$unique_ptr@UKEY_MAP_RECORD_CACHE@@U?$default_delete@UKEY_MAP_RECORD_CACHE@@@std@@@std@@@std@@PEAX@2@@Z`
- size: `73`
- prototype: `_QWORD *__fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180014d78`
- `0x1800151a0`

## callees

- `0x1800152f0`

## pseudocode

```c
_QWORD *__fastcall std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned char const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>>>::_Lrotate(
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
0x1800152f0  mov     r8, [rdx+10h]
0x1800152f4  mov     rax, [r8]
0x1800152f7  mov     [rdx+10h], rax
0x1800152fb  mov     rax, [r8]
0x1800152fe  cmp     byte ptr [rax+19h], 0
0x180015302  jnz     short loc_180015308
0x180015304  mov     [rax+8], rdx
0x180015308  mov     rax, [rdx+8]
0x18001530c  mov     [r8+8], rax
0x180015310  mov     rax, [rcx]
0x180015313  cmp     rdx, [rax+8]
0x180015317  jnz     short loc_18001531F
0x180015319  mov     [rax+8], r8
0x18001531d  jmp     short loc_180015331
0x18001531f  mov     rax, [rdx+8]
0x180015323  cmp     rdx, [rax]
0x180015326  jnz     short loc_18001532D
0x180015328  mov     [rax], r8
0x18001532b  jmp     short loc_180015331
0x18001532d  mov     [rax+10h], r8
0x180015331  mov     [r8], rdx
0x180015334  mov     [rdx+8], r8
0x180015338  retn
```
