# std::_Hash<std::tr1::_Umap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::_Hash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,CaseInsensitiveStringHash,CaseInsensitiveStringEquality>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>>>,0>>::equal_range(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180012858`
- end: `0x180012907`
- name: `?equal_range@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$_Hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCaseInsensitiveStringHash@@UCaseInsensitiveStringEquality@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@2@$0A@@tr1@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@2@@std@@@std@@V12@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z`
- size: `175`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180014490`

## callees

- `0x18000fe1c`
- `0x180011ca0`
- `0x180011d98`
- `0x180012858`

## pseudocode

```c
_QWORD *__fastcall std::_Hash<std::tr1::_Umap_traits<std::wstring,std::vector<std::wstring>,std::_Hash_compare<std::wstring,CaseInsensitiveStringHash,CaseInsensitiveStringEquality>,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>,0>>::equal_range(
        __int64 a1,
        _QWORD *a2,
        __int64 a3)
{
  unsigned __int64 v6; // r15
  _QWORD *i; // rbx
  __int64 v8; // rcx
  _QWORD *v9; // rdi
  __int64 v10; // rcx
  __int64 v11; // rax
  char v13; // [rsp+60h] [rbp+8h] BYREF

  v6 = std::_Hash<std::tr1::_Umap_traits<std::wstring,std::vector<std::wstring>,std::_Hash_compare<std::wstring,CaseInsensitiveStringHash,CaseInsensitiveStringEquality>,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>,0>>::_Hashval(
         a1,
         a3);
  for ( i = *(_QWORD **)(*(_QWORD *)(a1 + 32) + 16 * v6);
        i != *(_QWORD **)std::_Hash<std::tr1::_Umap_traits<std::wstring,std::vector<std::wstring>,std::_Hash_compare<std::wstring,CaseInsensitiveStringHash,CaseInsensitiveStringEquality>,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>,0>>::_End(
                           a1,
                           &v13,
                           v6);
        i = (_QWORD *)*i )
  {
    if ( !std::_Hash_compare<std::wstring,CaseInsensitiveStringHash,CaseInsensitiveStringEquality>::operator()(
            v8,
            (__int64)(i + 2),
            a3) )
    {
      v9 = i;
      while ( i != *(_QWORD **)std::_Hash<std::tr1::_Umap_traits<std::wstring,std::vector<std::wstring>,std::_Hash_compare<std::wstring,CaseInsensitiveStringHash,CaseInsensitiveStringEquality>,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>,0>>::_End(
                                 a1,
                                 &v13,
                                 v6)
           && !std::_Hash_compare<std::wstring,CaseInsensitiveStringHash,CaseInsensitiveStringEquality>::operator()(
                 v10,
                 a3,
                 (__int64)(i + 2)) )
        i = (_QWORD *)*i;
      if ( v9 != i )
      {
        *a2 = v9;
        a2[1] = i;
        return a2;
      }
      break;
    }
  }
  v11 = *(_QWORD *)(a1 + 8);
  *a2 = v11;
  a2[1] = v11;
  return a2;
}

```

## disassembly

```asm
0x180012858  push    rbx
0x18001285a  push    rbp
0x18001285b  push    rsi
0x18001285c  push    rdi
0x18001285d  push    r14
0x18001285f  push    r15
0x180012861  sub     rsp, 28h
0x180012865  mov     rsi, rdx
0x180012868  mov     r14, r8
0x18001286b  mov     rdx, r8
0x18001286e  mov     rbp, rcx
0x180012871  call    ?_Hashval@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$_Hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCaseInsensitiveStringHash@@UCaseInsensitiveStringEquality@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@2@$0A@@tr1@std@@@std@@IEBA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Hash<std::tr1::_Umap_traits<std::wstring,std::vector<std::wstring>,std::_Hash_compare<std::wstring,CaseInsensitiveStringHash,CaseInsensitiveStringEquality>,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>,0>>::_Hashval(std::wstring const &)
0x180012876  mov     rbx, [rbp+20h]
0x18001287a  mov     r9, rax
0x18001287d  add     r9, r9
0x180012880  mov     r15, rax
0x180012883  mov     rbx, [rbx+r9*8]
0x180012887  mov     r8, r15
0x18001288a  lea     rdx, [rsp+58h+arg_0]
0x18001288f  mov     rcx, rbp
0x180012892  call    ?_End@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$_Hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCaseInsensitiveStringHash@@UCaseInsensitiveStringEquality@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@2@$0A@@tr1@std@@@std@@IEAA?AV?$_List_iterator@V?$_List_val@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@2@@std@@@2@_K@Z; std::_Hash<std::tr1::_Umap_traits<std::wstring,std::vector<std::wstring>,std::_Hash_compare<std::wstring,CaseInsensitiveStringHash,CaseInsensitiveStringEquality>,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>,0>>::_End(unsigned __int64)
0x180012897  cmp     rbx, [rax]
0x18001289a  jz      short loc_1800128EC
0x18001289c  lea     rdx, [rbx+10h]
0x1800128a0  mov     r8, r14
0x1800128a3  call    ??R?$_Hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCaseInsensitiveStringHash@@UCaseInsensitiveStringEquality@@@std@@QEBA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@0@Z; std::_Hash_compare<std::wstring,CaseInsensitiveStringHash,CaseInsensitiveStringEquality>::operator()(std::wstring const &,std::wstring const &)
0x1800128a8  test    al, al
0x1800128aa  jz      short loc_1800128B1
0x1800128ac  mov     rbx, [rbx]
0x1800128af  jmp     short loc_180012887
0x1800128b1  mov     rdi, rbx
0x1800128b4  mov     r8, r15
0x1800128b7  lea     rdx, [rsp+58h+arg_0]
0x1800128bc  mov     rcx, rbp
0x1800128bf  call    ?_End@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$_Hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCaseInsensitiveStringHash@@UCaseInsensitiveStringEquality@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@2@$0A@@tr1@std@@@std@@IEAA?AV?$_List_iterator@V?$_List_val@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@2@@std@@@2@_K@Z; std::_Hash<std::tr1::_Umap_traits<std::wstring,std::vector<std::wstring>,std::_Hash_compare<std::wstring,CaseInsensitiveStringHash,CaseInsensitiveStringEquality>,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>,0>>::_End(unsigned __int64)
0x1800128c4  cmp     rbx, [rax]
0x1800128c7  jz      short loc_1800128DE
0x1800128c9  lea     r8, [rbx+10h]
0x1800128cd  mov     rdx, r14
0x1800128d0  call    ??R?$_Hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCaseInsensitiveStringHash@@UCaseInsensitiveStringEquality@@@std@@QEBA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@0@Z; std::_Hash_compare<std::wstring,CaseInsensitiveStringHash,CaseInsensitiveStringEquality>::operator()(std::wstring const &,std::wstring const &)
0x1800128d5  test    al, al
0x1800128d7  jnz     short loc_1800128DE
0x1800128d9  mov     rbx, [rbx]
0x1800128dc  jmp     short loc_1800128B4
0x1800128de  cmp     rdi, rbx
0x1800128e1  jz      short loc_1800128EC
0x1800128e3  mov     [rsi], rdi
0x1800128e6  mov     [rsi+8], rbx
0x1800128ea  jmp     short loc_1800128F7
0x1800128ec  mov     rax, [rbp+8]
0x1800128f0  mov     [rsi], rax
0x1800128f3  mov     [rsi+8], rax
0x1800128f7  mov     rax, rsi
0x1800128fa  add     rsp, 28h
0x1800128fe  pop     r15
0x180012900  pop     r14
0x180012902  pop     rdi
0x180012903  pop     rsi
0x180012904  pop     rbp
0x180012905  pop     rbx
0x180012906  retn
```
