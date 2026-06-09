# std::_Tree_val<std::_Tree_simple_types<std::pair<uchar const,std::unique_ptr<KEY_MAP_RECORD_CACHE,std::default_delete<KEY_MAP_RECORD_CACHE>>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<uchar const,std::unique_ptr<KEY_MAP_RECORD_CACHE,std::default_delete<KEY_MAP_RECORD_CACHE>>>,void *>>>(std::allocator<std::_Tree_node<std::pair<uchar const,std::unique_ptr<KEY_MAP_RECORD_CACHE,std::default_delete<KEY_MAP_RECORD_CACHE>>>,void *>> &,std::_Tree_node<std::pair<uchar const,std::unique_ptr<KEY_MAP_RECORD_CACHE,std::default_delete<KEY_MAP_RECORD_CACHE>>>,void *> *)

- ea: `0x18000cca0`
- end: `0x18000ccef`
- name: `??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBEV?$unique_ptr@UKEY_MAP_RECORD_CACHE@@U?$default_delete@UKEY_MAP_RECORD_CACHE@@@std@@@std@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBEV?$unique_ptr@UKEY_MAP_RECORD_CACHE@@U?$default_delete@UKEY_MAP_RECORD_CACHE@@@std@@@std@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBEV?$unique_ptr@UKEY_MAP_RECORD_CACHE@@U?$default_delete@UKEY_MAP_RECORD_CACHE@@@std@@@std@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBEV?$unique_ptr@UKEY_MAP_RECORD_CACHE@@U?$default_delete@UKEY_MAP_RECORD_CACHE@@@std@@@std@@@std@@PEAX@1@@Z`
- size: `79`
- prototype: `__int64 __fastcall(__int64, __int64, __int64 *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000cca0`
- `0x180014cbc`
- `0x1800273d8`

## callees

- `0x18000cca0`
- `0x18000cd48`

## pseudocode

```c
__int64 __fastcall std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned char const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<unsigned char const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>,void *>>>(
        __int64 a1,
        __int64 a2,
        __int64 *a3)
{
  __int64 *i; // rbx
  __int64 *v6; // rdx
  __int64 v7; // rcx
  __int64 result; // rax

  for ( i = a3;
        !*((_BYTE *)i + 25);
        result = std::_Tree_node<std::pair<unsigned char const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>,void *>::_Freenode<std::allocator<std::_Tree_node<std::pair<unsigned char const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>,void *>>>(
                   v7,
                   v6) )
  {
    std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned char const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<unsigned char const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>,void *>>>(
      a1,
      a2,
      i[2]);
    v6 = i;
    i = (__int64 *)*i;
  }
  return result;
}

```

## disassembly

```asm
0x18000cca0  mov     [rsp+arg_0], rbx
0x18000cca5  mov     [rsp+arg_8], rsi
0x18000ccaa  push    rdi
0x18000ccab  sub     rsp, 20h
0x18000ccaf  cmp     byte ptr [r8+19h], 0
0x18000ccb4  mov     rbx, r8
0x18000ccb7  mov     rdi, rdx
0x18000ccba  mov     rsi, rcx
0x18000ccbd  jnz     short loc_18000CCDF
0x18000ccbf  mov     r8, [rbx+10h]
0x18000ccc3  mov     rdx, rdi
0x18000ccc6  mov     rcx, rsi
0x18000ccc9  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBEV?$unique_ptr@UKEY_MAP_RECORD_CACHE@@U?$default_delete@UKEY_MAP_RECORD_CACHE@@@std@@@std@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBEV?$unique_ptr@UKEY_MAP_RECORD_CACHE@@U?$default_delete@UKEY_MAP_RECORD_CACHE@@@std@@@std@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBEV?$unique_ptr@UKEY_MAP_RECORD_CACHE@@U?$default_delete@UKEY_MAP_RECORD_CACHE@@@std@@@std@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBEV?$unique_ptr@UKEY_MAP_RECORD_CACHE@@U?$default_delete@UKEY_MAP_RECORD_CACHE@@@std@@@std@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<uchar const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<uchar const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>,void *>>>(std::allocator<std::_Tree_node<std::pair<uchar const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>,void *>> &,std::_Tree_node<std::pair<uchar const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>,void *> *)
0x18000ccce  mov     rdx, rbx
0x18000ccd1  mov     rbx, [rbx]
0x18000ccd4  call    ??$_Freenode@V?$allocator@U?$_Tree_node@U?$pair@$$CBEV?$unique_ptr@UKEY_MAP_RECORD_CACHE@@U?$default_delete@UKEY_MAP_RECORD_CACHE@@@std@@@std@@@std@@PEAX@std@@@std@@@?$_Tree_node@U?$pair@$$CBEV?$unique_ptr@UKEY_MAP_RECORD_CACHE@@U?$default_delete@UKEY_MAP_RECORD_CACHE@@@std@@@std@@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBEV?$unique_ptr@UKEY_MAP_RECORD_CACHE@@U?$default_delete@UKEY_MAP_RECORD_CACHE@@@std@@@std@@@std@@PEAX@std@@@1@PEAU01@@Z; std::_Tree_node<std::pair<uchar const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>,void *>::_Freenode<std::allocator<std::_Tree_node<std::pair<uchar const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>,void *>>>(std::allocator<std::_Tree_node<std::pair<uchar const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>,void *>> &,std::_Tree_node<std::pair<uchar const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>,void *> *)
0x18000ccd9  cmp     byte ptr [rbx+19h], 0
0x18000ccdd  jz      short loc_18000CCBF
0x18000ccdf  mov     rbx, [rsp+28h+arg_0]
0x18000cce4  mov     rsi, [rsp+28h+arg_8]
0x18000cce9  add     rsp, 20h
0x18000cced  pop     rdi
0x18000ccee  retn
```
