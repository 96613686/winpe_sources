# std::_Tree_val<std::_Tree_simple_types<std::pair<uchar const,std::unique_ptr<KEY_MAP_RECORD_CACHE,std::default_delete<KEY_MAP_RECORD_CACHE>>>>>::_Min(std::_Tree_node<std::pair<uchar const,std::unique_ptr<KEY_MAP_RECORD_CACHE,std::default_delete<KEY_MAP_RECORD_CACHE>>>,void *> *)

- ea: `0x180015340`
- end: `0x18001535c`
- name: `?_Min@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBEV?$unique_ptr@UKEY_MAP_RECORD_CACHE@@U?$default_delete@UKEY_MAP_RECORD_CACHE@@@std@@@std@@@std@@@std@@@std@@SAPEAU?$_Tree_node@U?$pair@$$CBEV?$unique_ptr@UKEY_MAP_RECORD_CACHE@@U?$default_delete@UKEY_MAP_RECORD_CACHE@@@std@@@std@@@std@@PEAX@2@PEAU32@@Z`
- size: `28`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000dd9c`
- `0x180014d78`

## callees

- `0x180015340`

## pseudocode

```c
_QWORD *__fastcall std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned char const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>>>::_Min(
        _QWORD *a1)
{
  __int64 *v1; // rdx

  v1 = (__int64 *)*a1;
  if ( !*(_BYTE *)(*a1 + 25LL) )
  {
    do
    {
      a1 = v1;
      v1 = (__int64 *)*v1;
    }
    while ( !*((_BYTE *)v1 + 25) );
  }
  return a1;
}

```

## disassembly

```asm
0x180015340  mov     rdx, [rcx]
0x180015343  cmp     byte ptr [rdx+19h], 0
0x180015347  jnz     short loc_180015358
0x180015349  mov     rax, [rdx]
0x18001534c  mov     rcx, rdx
0x18001534f  mov     rdx, rax
0x180015352  cmp     byte ptr [rax+19h], 0
0x180015356  jz      short loc_180015349
0x180015358  mov     rax, rcx
0x18001535b  retn
```
