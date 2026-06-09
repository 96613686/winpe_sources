# std::_Hash<std::_Uset_traits<unsigned __int64,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<unsigned __int64>,0>>::_Insert_bucket(std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<unsigned __int64>>,std::_Iterator_base0>,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<unsigned __int64>>,std::_Iterator_base0>,unsigned __int64)

- ea: `0x180008640`
- end: `0x180008690`
- name: `?_Insert_bucket@?$_Hash@V?$_Uset_traits@_KV?$_Uhash_compare@_KU?$hash@_K@std@@U?$equal_to@_K@2@@std@@V?$allocator@_K@2@$0A@@std@@@std@@IEAAXV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@_K@std@@@std@@U_Iterator_base0@2@@2@0_K@Z`
- size: `80`
- prototype: `__int64 *__fastcall(__int64 **, __int64, __int64 *, __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180003754`
- `0x180003894`

## callees

- `0x180008640`

## pseudocode

```c
__int64 *__fastcall std::_Hash<std::_Uset_traits<unsigned __int64,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<unsigned __int64>,0>>::_Insert_bucket(
        __int64 **a1,
        __int64 a2,
        __int64 *a3,
        __int64 a4)
{
  __int64 *v4; // r10
  __int64 v5; // r9
  __int64 *result; // rax
  __int64 v8; // rcx
  __int64 *v9; // rdx

  v4 = a1[2];
  v5 = 2 * a4;
  result = (__int64 *)v4[v5];
  if ( result == *a1 )
  {
    v4[v5] = a2;
    result = a1[2];
    result[v5 + 1] = a2;
  }
  else if ( result == a3 )
  {
    v4[v5] = a2;
  }
  else
  {
    result = (__int64 *)v4[v5 + 1];
    v8 = *result;
    v4[v5 + 1] = *result;
    if ( v8 != a2 )
    {
      v9 = a1[2];
      result = (__int64 *)v9[v5 + 1];
      v9[v5 + 1] = result[1];
    }
  }
  return result;
}

```

## disassembly

```asm
0x180008640  mov     r10, [rcx+10h]
0x180008644  add     r9, r9
0x180008647  mov     r11, rcx
0x18000864a  mov     rax, [r10+r9*8]
0x18000864e  cmp     rax, [rcx]
0x180008651  jnz     short loc_180008661
0x180008653  mov     [r10+r9*8], rdx
0x180008657  mov     rax, [rcx+10h]
0x18000865b  mov     [rax+r9*8+8], rdx
0x180008660  retn
0x180008661  cmp     rax, r8
0x180008664  jnz     short loc_18000866B
0x180008666  mov     [r10+r9*8], rdx
0x18000866a  retn
0x18000866b  mov     rax, [r10+r9*8+8]
0x180008670  mov     rcx, [rax]
0x180008673  mov     [r10+r9*8+8], rcx
0x180008678  cmp     rcx, rdx
0x18000867b  jz      short locret_18000868F
0x18000867d  mov     rdx, [r11+10h]
0x180008681  mov     rax, [rdx+r9*8+8]
0x180008686  mov     rcx, [rax+8]
0x18000868a  mov     [rdx+r9*8+8], rcx
0x18000868f  retn
```
