# std::_Hash<std::_Umap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::unique_ptr<ActionPlugin,std::default_delete<ActionPlugin>>,std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::unique_ptr<ActionPlugin,std::default_delete<ActionPlugin>>>>,0>>::_Find_last<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,unsigned __int64)

- ea: `0x180018114`
- end: `0x1800181ab`
- name: `??$_Find_last@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VActionPlugin@@U?$default_delete@VActionPlugin@@@std@@@2@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VActionPlugin@@U?$default_delete@VActionPlugin@@@std@@@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VActionPlugin@@U?$default_delete@VActionPlugin@@@std@@@2@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@_K@Z`
- size: `151`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *, __int64, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800181b4`
- `0x180018c10`
- `0x180025dcc`

## callees

- `0x180018114`
- `0x18001997c`

## pseudocode

```c
_QWORD *__fastcall std::_Hash<std::_Umap_traits<std::wstring,std::unique_ptr<ActionPlugin>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::unique_ptr<ActionPlugin>>>,0>>::_Find_last<std::wstring>(
        _QWORD *a1,
        _QWORD *a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v5; // r8
  _QWORD *v7; // rdx
  _QWORD *v8; // rdi
  _QWORD *v9; // rbp
  const wchar_t *v10; // rdx
  size_t v11; // r8
  const wchar_t *v12; // rcx

  v5 = a1[3];
  v7 = (_QWORD *)a1[1];
  v8 = *(_QWORD **)(v5 + 16 * (a4 & a1[6]) + 8);
  if ( v8 == v7 )
  {
    *a2 = v7;
  }
  else
  {
    v9 = *(_QWORD **)(v5 + 16 * (a4 & a1[6]));
    while ( 1 )
    {
      v10 = (const wchar_t *)(v8 + 2);
      if ( v8[5] > 7u )
        v10 = *(const wchar_t **)v10;
      v11 = *(_QWORD *)(a3 + 16);
      if ( *(_QWORD *)(a3 + 24) <= 7u )
        v12 = (const wchar_t *)a3;
      else
        v12 = *(const wchar_t **)a3;
      if ( v11 == v8[4] && (!v11 || !wmemcmp(v12, v10, v11)) )
      {
        *a2 = *v8;
        a2[1] = v8;
        return a2;
      }
      if ( v8 == v9 )
        break;
      v8 = (_QWORD *)v8[1];
    }
    *a2 = v8;
  }
  a2[1] = 0;
  return a2;
}

```

## disassembly

```asm
0x180018114  push    rbx
0x180018116  push    rbp
0x180018117  push    rsi
0x180018118  push    rdi
0x180018119  sub     rsp, 28h
0x18001811d  mov     rax, [rcx+30h]
0x180018121  mov     rsi, r8
0x180018124  mov     r8, [rcx+18h]
0x180018128  and     rax, r9
0x18001812b  add     rax, rax
0x18001812e  mov     rbx, rdx
0x180018131  mov     rdx, [rcx+8]
0x180018135  mov     rdi, [r8+rax*8+8]
0x18001813a  cmp     rdi, rdx
0x18001813d  jnz     short loc_180018144
0x18001813f  mov     [rbx], rdx
0x180018142  jmp     short loc_180018197
0x180018144  mov     rbp, [r8+rax*8]
0x180018148  cmp     qword ptr [rdi+28h], 7
0x18001814d  lea     rdx, [rdi+10h]
0x180018151  jbe     short loc_180018156
0x180018153  mov     rdx, [rdx]; S2
0x180018156  cmp     qword ptr [rsi+18h], 7
0x18001815b  mov     r8, [rsi+10h]; N
0x18001815f  jbe     short loc_180018166
0x180018161  mov     rcx, [rsi]
0x180018164  jmp     short loc_180018169
0x180018166  mov     rcx, rsi; S1
0x180018169  cmp     r8, [rdi+20h]
0x18001816d  jnz     short loc_18001817D
0x18001816f  test    r8, r8
0x180018172  jz      short loc_180018188
0x180018174  call    wmemcmp
0x180018179  test    eax, eax
0x18001817b  jz      short loc_180018188
0x18001817d  cmp     rdi, rbp
0x180018180  jz      short loc_180018194
0x180018182  mov     rdi, [rdi+8]
0x180018186  jmp     short loc_180018148
0x180018188  mov     rax, [rdi]
0x18001818b  mov     [rbx], rax
0x18001818e  mov     [rbx+8], rdi
0x180018192  jmp     short loc_18001819F
0x180018194  mov     [rbx], rdi
0x180018197  mov     qword ptr [rbx+8], 0
0x18001819f  mov     rax, rbx
0x1800181a2  add     rsp, 28h
0x1800181a6  pop     rdi
0x1800181a7  pop     rsi
0x1800181a8  pop     rbp
0x1800181a9  pop     rbx
0x1800181aa  retn
```
