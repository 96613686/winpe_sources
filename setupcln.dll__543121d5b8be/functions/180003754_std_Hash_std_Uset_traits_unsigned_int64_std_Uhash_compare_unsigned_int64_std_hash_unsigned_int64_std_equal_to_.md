# std::_Hash<std::_Uset_traits<unsigned __int64,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<unsigned __int64>,0>>::_Insert<unsigned __int64 const &,std::_Nil>(unsigned __int64 const &,std::_Nil)

- ea: `0x180003754`
- end: `0x18000388d`
- name: `??$_Insert@AEB_KU_Nil@std@@@?$_Hash@V?$_Uset_traits@_KV?$_Uhash_compare@_KU?$hash@_K@std@@U?$equal_to@_K@2@@std@@V?$allocator@_K@2@$0A@@std@@@std@@IEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@_K@std@@@std@@@std@@_N@1@AEB_KU_Nil@1@@Z`
- size: `313`
- prototype: `__int64 __fastcall(__int64 **, __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800071a8`

## callees

- `0x180001e68`
- `0x180003728`
- `0x180003754`
- `0x180008308`
- `0x1800083ac`
- `0x18000854c`
- `0x180008640`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Uset_traits<unsigned __int64,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<unsigned __int64>,0>>::_Insert<unsigned __int64 const &,std::_Nil>(
        __int64 **a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v5; // r15
  __int64 v6; // rbx
  _QWORD *v7; // r11
  __int64 v9; // rdi
  __int64 v10; // rdx
  __int64 *v11; // rax
  __int64 *v12; // rdi
  __int64 v13; // rdx
  __int64 v14; // rcx
  _QWORD v15[5]; // [rsp+20h] [rbp-28h] BYREF

  v5 = std::_Hash<std::_Uset_traits<unsigned __int64,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<unsigned __int64>,0>>::_Hashval(
         a1,
         a3);
  v6 = *(_QWORD *)std::_Hash<std::_Uset_traits<unsigned __int64,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<unsigned __int64>,0>>::_End(
                    a1,
                    v15,
                    v5);
  while ( v6 != a1[2][2 * v5] )
  {
    v6 = *(_QWORD *)(v6 + 8);
    if ( *v7 == *(_QWORD *)(v6 + 16) )
    {
      *(_QWORD *)a2 = v6;
      *(_BYTE *)(a2 + 8) = 0;
      return a2;
    }
  }
  v9 = **a1;
  v10 = std::_List_buy<unsigned __int64>::_Buynode<unsigned __int64 const &>(2 * v5, v9, *(_QWORD *)(v9 + 8), v7);
  v11 = a1[1];
  if ( v11 == (__int64 *)0xAAAAAAAAAAAAAA9LL )
    std::_Xlength_error("list<T> too long");
  a1[1] = (__int64 *)((char *)v11 + 1);
  *(_QWORD *)(v9 + 8) = v10;
  **(_QWORD **)(v10 + 8) = v10;
  v12 = (__int64 *)**a1;
  v15[0] = v12;
  v13 = *v12;
  if ( v6 != *v12 )
  {
    *(_QWORD *)v12[1] = v13;
    **(_QWORD **)(v13 + 8) = v6;
    **(_QWORD **)(v6 + 8) = v12;
    v14 = *(_QWORD *)(v6 + 8);
    *(_QWORD *)(v6 + 8) = *(_QWORD *)(v13 + 8);
    *(_QWORD *)(v13 + 8) = v12[1];
    v12[1] = v14;
  }
  std::_Hash<std::_Uset_traits<unsigned __int64,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<unsigned __int64>,0>>::_Insert_bucket(
    a1,
    v12,
    v6,
    v5);
  try
  {
    std::_Hash<std::_Uset_traits<unsigned __int64,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<unsigned __int64>,0>>::_Check_size(a1);
  }
  catch ( ... )
  {
    std::_Hash<std::_Uset_traits<unsigned __int64,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<unsigned __int64>,0>>::erase(
      a1,
      v15,
      v15[0]);
    throw;
  }
  *(_QWORD *)a2 = v12;
  *(_BYTE *)(a2 + 8) = 1;
  return a2;
}

```

## disassembly

```asm
0x180003754  mov     [rsp+arg_8], rbx
0x180003759  mov     [rsp+arg_10], rsi
0x18000375e  mov     [rsp+arg_0], rcx
0x180003763  push    rdi
0x180003764  push    r14
0x180003766  push    r15
0x180003768  sub     rsp, 30h
0x18000376c  mov     r11, r8
0x18000376f  mov     rsi, rdx
0x180003772  mov     r14, rcx
0x180003775  mov     rdx, r8
0x180003778  call    ?_Hashval@?$_Hash@V?$_Uset_traits@_KV?$_Uhash_compare@_KU?$hash@_K@std@@U?$equal_to@_K@2@@std@@V?$allocator@_K@2@$0A@@std@@@std@@IEBA_KAEB_K@Z; std::_Hash<std::_Uset_traits<unsigned __int64,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<unsigned __int64>,0>>::_Hashval(unsigned __int64 const &)
0x18000377d  mov     r15, rax
0x180003780  mov     r8, rax
0x180003783  lea     rdx, [rsp+48h+var_28]
0x180003788  mov     rcx, r14
0x18000378b  call    ?_End@?$_Hash@V?$_Uset_traits@_KV?$_Uhash_compare@_KU?$hash@_K@std@@U?$equal_to@_K@2@@std@@V?$allocator@_K@2@$0A@@std@@@std@@IEAA?AV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@_K@std@@@std@@U_Iterator_base0@2@@2@_K@Z; std::_Hash<std::_Uset_traits<unsigned __int64,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<unsigned __int64>,0>>::_End(unsigned __int64)
0x180003790  mov     rbx, [rax]
0x180003793  mov     rcx, r15
0x180003796  add     rcx, rcx
0x180003799  mov     rax, [r14+10h]
0x18000379d  mov     rdx, [rax+rcx*8]
0x1800037a1  cmp     rbx, rdx
0x1800037a4  jz      short loc_1800037C5
0x1800037a6  mov     rax, [rbx+8]
0x1800037aa  mov     rbx, rax
0x1800037ad  mov     rax, [rax+10h]
0x1800037b1  cmp     [r11], rax
0x1800037b4  jnz     short loc_1800037A1
0x1800037b6  mov     [rsi], rbx
0x1800037b9  mov     byte ptr [rsi+8], 0
0x1800037bd  mov     rax, rsi
0x1800037c0  jmp     loc_180003878
0x1800037c5  mov     rax, [r14]
0x1800037c8  mov     rdi, [rax]
0x1800037cb  mov     r9, r11
0x1800037ce  mov     r8, [rdi+8]
0x1800037d2  mov     rdx, rdi
0x1800037d5  call    ??$_Buynode@AEB_K@?$_List_buy@_KV?$allocator@_K@std@@@std@@QEAAPEAU?$_List_node@_KPEAX@1@PEAU21@0AEB_K@Z; std::_List_buy<unsigned __int64>::_Buynode<unsigned __int64 const &>(std::_List_node<unsigned __int64,void *> *,std::_List_node<unsigned __int64,void *> *,unsigned __int64 const &)
0x1800037da  mov     rdx, rax
0x1800037dd  mov     rax, [r14+8]
0x1800037e1  mov     rcx, 0AAAAAAAAAAAAAA9h
0x1800037eb  sub     rcx, rax
0x1800037ee  cmp     rcx, 1
0x1800037f2  jnb     short loc_180003801
0x1800037f4  lea     rcx, aListTTooLong; "list<T> too long"
0x1800037fb  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180003801  inc     rax
0x180003804  mov     [r14+8], rax
0x180003808  mov     [rdi+8], rdx
0x18000380c  mov     rax, [rdx+8]
0x180003810  mov     [rax], rdx
0x180003813  mov     rdi, [r14]
0x180003816  mov     rdi, [rdi]
0x180003819  mov     [rsp+48h+var_28], rdi
0x18000381e  mov     rdx, [rdi]
0x180003821  cmp     rbx, rdx
0x180003824  jz      short loc_180003853
0x180003826  mov     rax, [rdi+8]
0x18000382a  mov     [rax], rdx
0x18000382d  mov     rax, [rdx+8]
0x180003831  mov     [rax], rbx
0x180003834  mov     rax, [rbx+8]
0x180003838  mov     [rax], rdi
0x18000383b  mov     rcx, [rbx+8]
0x18000383f  mov     rax, [rdx+8]
0x180003843  mov     [rbx+8], rax
0x180003847  mov     rax, [rdi+8]
0x18000384b  mov     [rdx+8], rax
0x18000384f  mov     [rdi+8], rcx
0x180003853  mov     r9, r15
0x180003856  mov     r8, rbx
0x180003859  mov     rdx, rdi
0x18000385c  mov     rcx, r14
0x18000385f  call    ?_Insert_bucket@?$_Hash@V?$_Uset_traits@_KV?$_Uhash_compare@_KU?$hash@_K@std@@U?$equal_to@_K@2@@std@@V?$allocator@_K@2@$0A@@std@@@std@@IEAAXV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@_K@std@@@std@@U_Iterator_base0@2@@2@0_K@Z; std::_Hash<std::_Uset_traits<unsigned __int64,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<unsigned __int64>,0>>::_Insert_bucket(std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<unsigned __int64>>,std::_Iterator_base0>,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<unsigned __int64>>,std::_Iterator_base0>,unsigned __int64)
0x180003864  nop
0x180003865  mov     rcx, r14
0x180003868  call    ?_Check_size@?$_Hash@V?$_Uset_traits@_KV?$_Uhash_compare@_KU?$hash@_K@std@@U?$equal_to@_K@2@@std@@V?$allocator@_K@2@$0A@@std@@@std@@IEAAXXZ; std::_Hash<std::_Uset_traits<unsigned __int64,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<unsigned __int64>,0>>::_Check_size(void)
0x18000386d  nop
0x18000386e  mov     [rsi], rdi
0x180003871  mov     byte ptr [rsi+8], 1
0x180003875  mov     rax, rsi
0x180003878  mov     rbx, [rsp+48h+arg_8]
0x18000387d  mov     rsi, [rsp+48h+arg_10]
0x180003882  add     rsp, 30h
0x180003886  pop     r15
0x180003888  pop     r14
0x18000388a  pop     rdi
0x18000388b  retn
```
