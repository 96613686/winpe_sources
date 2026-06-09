# std::_Tree<std::_Tmap_traits<uchar,std::unique_ptr<KEY_MAP_RECORD_CACHE,std::default_delete<KEY_MAP_RECORD_CACHE>>,std::less<uchar>,std::allocator<std::pair<uchar const,std::unique_ptr<KEY_MAP_RECORD_CACHE,std::default_delete<KEY_MAP_RECORD_CACHE>>>>,0>>::_Erase(std::pair<std::_Tree_node<std::pair<uchar const,std::unique_ptr<KEY_MAP_RECORD_CACHE,std::default_delete<KEY_MAP_RECORD_CACHE>>>,void *> *,std::_Tree_node<std::pair<uchar const,std::unique_ptr<KEY_MAP_RECORD_CACHE,std::default_delete<KEY_MAP_RECORD_CACHE>>>,void *> *>)

- ea: `0x180014cbc`
- end: `0x180014d72`
- name: `?_Erase@?$_Tree@V?$_Tmap_traits@EV?$unique_ptr@UKEY_MAP_RECORD_CACHE@@U?$default_delete@UKEY_MAP_RECORD_CACHE@@@std@@@std@@U?$less@E@2@V?$allocator@U?$pair@$$CBEV?$unique_ptr@UKEY_MAP_RECORD_CACHE@@U?$default_delete@UKEY_MAP_RECORD_CACHE@@@std@@@std@@@std@@@2@$0A@@std@@@std@@AEAA_KU?$pair@PEAU?$_Tree_node@U?$pair@$$CBEV?$unique_ptr@UKEY_MAP_RECORD_CACHE@@U?$default_delete@UKEY_MAP_RECORD_CACHE@@@std@@@std@@@std@@PEAX@std@@PEAU12@@2@@Z`
- size: `182`
- prototype: `__int64 __fastcall(__int64 *, __int64 *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800157a0`

## callees

- `0x18000cca0`
- `0x18000cd48`
- `0x18000dd9c`
- `0x180014cbc`
- `0x180014d78`

## pseudocode

```c
__int64 __fastcall std::_Tree<std::_Tmap_traits<unsigned char,std::unique_ptr<KEY_MAP_RECORD_CACHE>,std::less<unsigned char>,std::allocator<std::pair<unsigned char const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>>,0>>::_Erase(
        __int64 *a1,
        __int64 *a2)
{
  __int64 v2; // r9
  __int64 v4; // rbx
  __int64 v5; // rax
  __int64 v6; // rbp
  __int64 v7; // rdi
  __int64 v9; // r9
  __int64 v10; // r9
  char *v11; // rax
  __int64 v12; // rcx
  __int64 v13; // [rsp+40h] [rbp+8h] BYREF
  __int64 v14; // [rsp+48h] [rbp+10h] BYREF

  v2 = *a2;
  v4 = a2[1];
  v5 = *a2;
  v13 = *a2;
  v6 = 0;
  while ( v5 != v4 )
  {
    ++v6;
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned char const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>>>,std::_Iterator_base0>::operator++(&v13);
    v5 = v13;
  }
  v7 = *a1;
  v13 = v2;
  if ( v2 == *(_QWORD *)v7 && *(_BYTE *)(v4 + 25) )
  {
    std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned char const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<unsigned char const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>,void *>>>(
      (__int64)a1,
      (__int64)a1,
      *(__int64 **)(v7 + 8));
    *(_QWORD *)(v7 + 8) = v7;
    *(_QWORD *)v7 = v7;
    *(_QWORD *)(v7 + 16) = v7;
    a1[1] = 0;
  }
  else
  {
    while ( v2 != v4 )
    {
      std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned char const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>>>,std::_Iterator_base0>::operator++(&v13);
      v14 = v9;
      std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned char const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>>>,std::_Iterator_base0>::operator++(&v14);
      v11 = (char *)std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned char const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>>>::_Extract(
                      a1,
                      v10);
      std::_Tree_node<std::pair<unsigned char const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>,void *>::_Freenode<std::allocator<std::_Tree_node<std::pair<unsigned char const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>,void *>>>(
        v12,
        v11);
      v2 = v13;
    }
  }
  return v6;
}

```

## disassembly

```asm
0x180014cbc  mov     [rsp+arg_10], rbx
0x180014cc1  push    rbp
0x180014cc2  push    rsi
0x180014cc3  push    rdi
0x180014cc4  sub     rsp, 20h
0x180014cc8  mov     r9, [rdx]
0x180014ccb  mov     rsi, rcx
0x180014cce  mov     rbx, [rdx+8]
0x180014cd2  mov     rax, r9
0x180014cd5  mov     [rsp+38h+arg_0], rax
0x180014cda  xor     ebp, ebp
0x180014cdc  cmp     rax, rbx
0x180014cdf  jz      short loc_180014CF5
0x180014ce1  inc     rbp
0x180014ce4  lea     rcx, [rsp+38h+arg_0]
0x180014ce9  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBEV?$unique_ptr@UKEY_MAP_RECORD_CACHE@@U?$default_delete@UKEY_MAP_RECORD_CACHE@@@std@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<uchar const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>>>,std::_Iterator_base0>::operator++(void)
0x180014cee  mov     rax, [rsp+38h+arg_0]
0x180014cf3  jmp     short loc_180014CDC
0x180014cf5  mov     rdi, [rsi]
0x180014cf8  mov     [rsp+38h+arg_0], r9
0x180014cfd  cmp     r9, [rdi]
0x180014d00  jnz     short loc_180014D3A
0x180014d02  cmp     byte ptr [rbx+19h], 0
0x180014d06  jz      short loc_180014D3A
0x180014d08  mov     r8, [rdi+8]
0x180014d0c  mov     rdx, rsi
0x180014d0f  mov     rcx, rsi
0x180014d12  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBEV?$unique_ptr@UKEY_MAP_RECORD_CACHE@@U?$default_delete@UKEY_MAP_RECORD_CACHE@@@std@@@std@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBEV?$unique_ptr@UKEY_MAP_RECORD_CACHE@@U?$default_delete@UKEY_MAP_RECORD_CACHE@@@std@@@std@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBEV?$unique_ptr@UKEY_MAP_RECORD_CACHE@@U?$default_delete@UKEY_MAP_RECORD_CACHE@@@std@@@std@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBEV?$unique_ptr@UKEY_MAP_RECORD_CACHE@@U?$default_delete@UKEY_MAP_RECORD_CACHE@@@std@@@std@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<uchar const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<uchar const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>,void *>>>(std::allocator<std::_Tree_node<std::pair<uchar const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>,void *>> &,std::_Tree_node<std::pair<uchar const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>,void *> *)
0x180014d17  mov     [rdi+8], rdi
0x180014d1b  mov     [rdi], rdi
0x180014d1e  mov     [rdi+10h], rdi
0x180014d22  mov     qword ptr [rsi+8], 0
0x180014d2a  mov     rbx, [rsp+38h+arg_10]
0x180014d2f  mov     rax, rbp
0x180014d32  add     rsp, 20h
0x180014d36  pop     rdi
0x180014d37  pop     rsi
0x180014d38  pop     rbp
0x180014d39  retn
0x180014d3a  cmp     r9, rbx
0x180014d3d  jz      short loc_180014D2A
0x180014d3f  lea     rcx, [rsp+38h+arg_0]
0x180014d44  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBEV?$unique_ptr@UKEY_MAP_RECORD_CACHE@@U?$default_delete@UKEY_MAP_RECORD_CACHE@@@std@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<uchar const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>>>,std::_Iterator_base0>::operator++(void)
0x180014d49  lea     rcx, [rsp+38h+arg_8]
0x180014d4e  mov     [rsp+38h+arg_8], r9
0x180014d53  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBEV?$unique_ptr@UKEY_MAP_RECORD_CACHE@@U?$default_delete@UKEY_MAP_RECORD_CACHE@@@std@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<uchar const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>>>,std::_Iterator_base0>::operator++(void)
0x180014d58  mov     rdx, r9
0x180014d5b  mov     rcx, rsi
0x180014d5e  call    ?_Extract@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBEV?$unique_ptr@UKEY_MAP_RECORD_CACHE@@U?$default_delete@UKEY_MAP_RECORD_CACHE@@@std@@@std@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBEV?$unique_ptr@UKEY_MAP_RECORD_CACHE@@U?$default_delete@UKEY_MAP_RECORD_CACHE@@@std@@@std@@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBEV?$unique_ptr@UKEY_MAP_RECORD_CACHE@@U?$default_delete@UKEY_MAP_RECORD_CACHE@@@std@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<uchar const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<uchar const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>>>,std::_Iterator_base0>)
0x180014d63  mov     rdx, rax
0x180014d66  call    ??$_Freenode@V?$allocator@U?$_Tree_node@U?$pair@$$CBEV?$unique_ptr@UKEY_MAP_RECORD_CACHE@@U?$default_delete@UKEY_MAP_RECORD_CACHE@@@std@@@std@@@std@@PEAX@std@@@std@@@?$_Tree_node@U?$pair@$$CBEV?$unique_ptr@UKEY_MAP_RECORD_CACHE@@U?$default_delete@UKEY_MAP_RECORD_CACHE@@@std@@@std@@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBEV?$unique_ptr@UKEY_MAP_RECORD_CACHE@@U?$default_delete@UKEY_MAP_RECORD_CACHE@@@std@@@std@@@std@@PEAX@std@@@1@PEAU01@@Z; std::_Tree_node<std::pair<uchar const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>,void *>::_Freenode<std::allocator<std::_Tree_node<std::pair<uchar const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>,void *>>>(std::allocator<std::_Tree_node<std::pair<uchar const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>,void *>> &,std::_Tree_node<std::pair<uchar const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>,void *> *)
0x180014d6b  mov     r9, [rsp+38h+arg_0]
0x180014d70  jmp     short loc_180014D3A
```
