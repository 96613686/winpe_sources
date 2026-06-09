# std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<uchar const,std::unique_ptr<KEY_MAP_RECORD_CACHE,std::default_delete<KEY_MAP_RECORD_CACHE>>>>>,std::_Iterator_base0>::operator++(void)

- ea: `0x18000dd9c`
- end: `0x18000dde1`
- name: `??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBEV?$unique_ptr@UKEY_MAP_RECORD_CACHE@@U?$default_delete@UKEY_MAP_RECORD_CACHE@@@std@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ`
- size: `69`
- prototype: `__int64 *__fastcall(__int64 *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180014cbc`
- `0x180014d78`

## callees

- `0x18000dd9c`
- `0x180015340`

## pseudocode

```c
__int64 *__fastcall std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned char const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>>>,std::_Iterator_base0>::operator++(
        __int64 *a1)
{
  __int64 *v1; // r8
  __int64 v2; // rcx
  __int64 i; // rax

  v1 = a1;
  v2 = *a1;
  if ( *(_BYTE *)(*(_QWORD *)(v2 + 16) + 25LL) )
  {
    for ( i = *(_QWORD *)(v2 + 8); !*(_BYTE *)(i + 25) && v2 == *(_QWORD *)(i + 16); i = *(_QWORD *)(i + 8) )
    {
      v2 = i;
      *v1 = i;
    }
  }
  else
  {
    i = std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned char const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>>>::_Min(
          *(_QWORD *)(v2 + 16),
          0,
          v1);
  }
  *v1 = i;
  return v1;
}

```

## disassembly

```asm
0x18000dd9c  sub     rsp, 28h
0x18000dda0  mov     r8, rcx
0x18000dda3  xor     edx, edx
0x18000dda5  mov     rcx, [rcx]
0x18000dda8  mov     rax, [rcx+10h]
0x18000ddac  cmp     [rax+19h], dl
0x18000ddaf  jz      short loc_18000DDCE
0x18000ddb1  mov     rax, [rcx+8]
0x18000ddb5  jmp     short loc_18000DDC7
0x18000ddb7  cmp     rcx, [rax+10h]
0x18000ddbb  jnz     short loc_18000DDD6
0x18000ddbd  mov     rcx, rax
0x18000ddc0  mov     [r8], rax
0x18000ddc3  mov     rax, [rax+8]
0x18000ddc7  cmp     [rax+19h], dl
0x18000ddca  jz      short loc_18000DDB7
0x18000ddcc  jmp     short loc_18000DDD6
0x18000ddce  mov     rcx, rax
0x18000ddd1  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBEV?$unique_ptr@UKEY_MAP_RECORD_CACHE@@U?$default_delete@UKEY_MAP_RECORD_CACHE@@@std@@@std@@@std@@@std@@@std@@SAPEAU?$_Tree_node@U?$pair@$$CBEV?$unique_ptr@UKEY_MAP_RECORD_CACHE@@U?$default_delete@UKEY_MAP_RECORD_CACHE@@@std@@@std@@@std@@PEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<uchar const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>>>::_Min(std::_Tree_node<std::pair<uchar const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>,void *> *)
0x18000ddd6  mov     [r8], rax
0x18000ddd9  mov     rax, r8
0x18000dddc  add     rsp, 28h
0x18000dde0  retn
```
