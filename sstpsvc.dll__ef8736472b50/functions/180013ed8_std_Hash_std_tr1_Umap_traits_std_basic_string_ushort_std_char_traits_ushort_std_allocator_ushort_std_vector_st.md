# std::_Hash<std::tr1::_Umap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::_Hash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,CaseInsensitiveStringHash,CaseInsensitiveStringEquality>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>>>,0>>::lower_bound(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180013ed8`
- end: `0x180013f62`
- name: `?lower_bound@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$_Hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCaseInsensitiveStringHash@@UCaseInsensitiveStringEquality@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@2@$0A@@tr1@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@2@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z`
- size: `138`
- prototype: ``
- caller_count: `5`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180010b08`
- `0x1800142b8`
- `0x180014900`
- `0x1800151e0`
- `0x180015500`

## callees

- `0x180010c08`
- `0x180012c3c`
- `0x180012d3c`
- `0x180013ed8`

## pseudocode

```c
_QWORD *__fastcall std::_Hash<std::tr1::_Umap_traits<std::wstring,std::vector<std::wstring>,std::_Hash_compare<std::wstring,CaseInsensitiveStringHash,CaseInsensitiveStringEquality>,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>,0>>::lower_bound(
        __int64 a1,
        _QWORD *a2,
        __int64 a3)
{
  __int64 v6; // r15
  _QWORD *i; // rbx
  __int64 v8; // rcx
  __int64 v9; // rcx
  char v11; // [rsp+60h] [rbp+8h] BYREF

  v6 = std::_Hash<std::tr1::_Umap_traits<std::wstring,std::vector<std::wstring>,std::_Hash_compare<std::wstring,CaseInsensitiveStringHash,CaseInsensitiveStringEquality>,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>,0>>::_Hashval(
         a1,
         a3);
  for ( i = *(_QWORD **)(*(_QWORD *)(a1 + 32) + 16 * v6); ; i = (_QWORD *)*i )
  {
    if ( i == *(_QWORD **)std::_Hash<std::tr1::_Umap_traits<std::wstring,std::vector<std::wstring>,std::_Hash_compare<std::wstring,CaseInsensitiveStringHash,CaseInsensitiveStringEquality>,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>,0>>::_End(
                            a1,
                            &v11,
                            v6) )
    {
      *a2 = *(_QWORD *)(a1 + 8);
      return a2;
    }
    if ( !(unsigned __int8)std::_Hash_compare<std::wstring,CaseInsensitiveStringHash,CaseInsensitiveStringEquality>::operator()(
                             v8,
                             i + 2,
                             a3) )
      break;
  }
  if ( (unsigned __int8)std::_Hash_compare<std::wstring,CaseInsensitiveStringHash,CaseInsensitiveStringEquality>::operator()(
                          v9,
                          a3,
                          i + 2) )
    i = *(_QWORD **)(a1 + 8);
  *a2 = i;
  return a2;
}

```

## disassembly

```asm
0x180013ed8  push    rbx
0x180013eda  push    rbp
0x180013edb  push    rsi
0x180013edc  push    rdi
0x180013edd  push    r14
0x180013edf  push    r15
0x180013ee1  sub     rsp, 28h
0x180013ee5  mov     rdi, rdx
0x180013ee8  mov     r14, r8
0x180013eeb  mov     rdx, r8
0x180013eee  mov     rsi, rcx
0x180013ef1  call    ?_Hashval@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$_Hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCaseInsensitiveStringHash@@UCaseInsensitiveStringEquality@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@2@$0A@@tr1@std@@@std@@IEBA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Hash<std::tr1::_Umap_traits<std::wstring,std::vector<std::wstring>,std::_Hash_compare<std::wstring,CaseInsensitiveStringHash,CaseInsensitiveStringEquality>,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>,0>>::_Hashval(std::wstring const &)
0x180013ef6  mov     r9, [rsi+20h]
0x180013efa  mov     r10, rax
0x180013efd  add     r10, r10
0x180013f00  mov     r15, rax
0x180013f03  mov     rbx, [r9+r10*8]
0x180013f07  mov     r8, r15
0x180013f0a  lea     rdx, [rsp+58h+arg_0]
0x180013f0f  mov     rcx, rsi
0x180013f12  call    ?_End@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$_Hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCaseInsensitiveStringHash@@UCaseInsensitiveStringEquality@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@2@$0A@@tr1@std@@@std@@IEAA?AV?$_List_iterator@V?$_List_val@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@2@@std@@@2@_K@Z; std::_Hash<std::tr1::_Umap_traits<std::wstring,std::vector<std::wstring>,std::_Hash_compare<std::wstring,CaseInsensitiveStringHash,CaseInsensitiveStringEquality>,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>,0>>::_End(unsigned __int64)
0x180013f17  cmp     rbx, [rax]
0x180013f1a  jz      short loc_180013F4A
0x180013f1c  mov     r8, r14
0x180013f1f  lea     rdx, [rbx+10h]
0x180013f23  call    ??R?$_Hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCaseInsensitiveStringHash@@UCaseInsensitiveStringEquality@@@std@@QEBA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@0@Z; std::_Hash_compare<std::wstring,CaseInsensitiveStringHash,CaseInsensitiveStringEquality>::operator()(std::wstring const &,std::wstring const &)
0x180013f28  test    al, al
0x180013f2a  jz      short loc_180013F31
0x180013f2c  mov     rbx, [rbx]
0x180013f2f  jmp     short loc_180013F07
0x180013f31  lea     r8, [rbx+10h]
0x180013f35  mov     rdx, r14
0x180013f38  call    ??R?$_Hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCaseInsensitiveStringHash@@UCaseInsensitiveStringEquality@@@std@@QEBA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@0@Z; std::_Hash_compare<std::wstring,CaseInsensitiveStringHash,CaseInsensitiveStringEquality>::operator()(std::wstring const &,std::wstring const &)
0x180013f3d  test    al, al
0x180013f3f  jz      short loc_180013F45
0x180013f41  mov     rbx, [rsi+8]
0x180013f45  mov     [rdi], rbx
0x180013f48  jmp     short loc_180013F51
0x180013f4a  mov     rax, [rsi+8]
0x180013f4e  mov     [rdi], rax
0x180013f51  mov     rax, rdi
0x180013f54  add     rsp, 28h
0x180013f58  pop     r15
0x180013f5a  pop     r14
0x180013f5c  pop     rdi
0x180013f5d  pop     rsi
0x180013f5e  pop     rbp
0x180013f5f  pop     rbx
0x180013f60  retn
```
