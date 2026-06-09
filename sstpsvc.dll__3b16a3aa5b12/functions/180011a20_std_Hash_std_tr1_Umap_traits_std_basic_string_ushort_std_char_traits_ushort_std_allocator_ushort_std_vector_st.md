# std::_Hash<std::tr1::_Umap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::_Hash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,CaseInsensitiveStringHash,CaseInsensitiveStringEquality>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>>>,0>>::_Check_size(void)

- ea: `0x180011a20`
- end: `0x180011abc`
- name: `?_Check_size@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$_Hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCaseInsensitiveStringHash@@UCaseInsensitiveStringEquality@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@2@$0A@@tr1@std@@@std@@IEAAXXZ`
- size: `156`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180011e50`

## callees

- `0x180007d60`
- `0x180011a20`
- `0x180012320`

## pseudocode

```c
void __fastcall std::_Hash<std::tr1::_Umap_traits<std::wstring,std::vector<std::wstring>,std::_Hash_compare<std::wstring,CaseInsensitiveStringHash,CaseInsensitiveStringEquality>,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>,0>>::_Check_size(
        __int64 a1)
{
  __int64 v1; // r8
  unsigned __int64 v3; // rdx
  float v4; // xmm0_4
  __int64 v5; // rax
  float v6; // xmm1_4
  int i; // eax

  v1 = *(_QWORD *)(a1 + 16);
  v3 = *(_QWORD *)(a1 + 72);
  if ( v1 < 0 )
  {
    v5 = *(_QWORD *)(a1 + 16) & 1LL | (*(_QWORD *)(a1 + 16) >> 1);
    v4 = (float)(int)v5 + (float)(int)v5;
  }
  else
  {
    v4 = (float)(int)v1;
  }
  if ( (v3 & 0x8000000000000000uLL) != 0LL )
    v6 = (float)(int)(*(_DWORD *)(a1 + 72) & 1 | (v3 >> 1)) + (float)(int)(*(_DWORD *)(a1 + 72) & 1 | (v3 >> 1));
  else
    v6 = (float)(int)v3;
  if ( (float)(v4 / v6) > *(float *)(a1 + 80) )
  {
    for ( i = 0; i < 3; ++i )
    {
      if ( v3 >= 0xFFFFFFFFFFFFFFFLL )
        break;
      v3 *= 2LL;
    }
    std::_Hash<std::tr1::_Umap_traits<std::wstring,std::vector<std::wstring>,std::_Hash_compare<std::wstring,CaseInsensitiveStringHash,CaseInsensitiveStringEquality>,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>,0>>::_Init(
      (_QWORD *)a1,
      v3);
    std::_Hash<std::tr1::_Umap_traits<std::wstring,std::vector<std::wstring>,std::_Hash_compare<std::wstring,CaseInsensitiveStringHash,CaseInsensitiveStringEquality>,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>,0>>::_Reinsert(
      a1,
      *(_QWORD *)(a1 + 8));
  }
}

```

## disassembly

```asm
0x180011a20  push    rbx
0x180011a22  sub     rsp, 20h
0x180011a26  mov     r8, [rcx+10h]
0x180011a2a  mov     rbx, rcx
0x180011a2d  mov     rdx, [rcx+48h]
0x180011a31  xorps   xmm0, xmm0
0x180011a34  test    r8, r8
0x180011a37  js      short loc_180011A40
0x180011a39  cvtsi2ss xmm0, r8
0x180011a3e  jmp     short loc_180011A56
0x180011a40  mov     rax, r8
0x180011a43  and     r8d, 1
0x180011a47  shr     rax, 1
0x180011a4a  or      rax, r8
0x180011a4d  cvtsi2ss xmm0, rax
0x180011a52  addss   xmm0, xmm0
0x180011a56  xorps   xmm1, xmm1
0x180011a59  test    rdx, rdx
0x180011a5c  js      short loc_180011A65
0x180011a5e  cvtsi2ss xmm1, rdx
0x180011a63  jmp     short loc_180011A7D
0x180011a65  mov     rax, rdx
0x180011a68  mov     rcx, rdx
0x180011a6b  shr     rcx, 1
0x180011a6e  and     eax, 1
0x180011a71  or      rcx, rax
0x180011a74  cvtsi2ss xmm1, rcx
0x180011a79  addss   xmm1, xmm1
0x180011a7d  divss   xmm0, xmm1
0x180011a81  comiss  xmm0, dword ptr [rbx+50h]
0x180011a85  jbe     short loc_180011AB6
0x180011a87  xor     eax, eax
0x180011a89  mov     rcx, 0FFFFFFFFFFFFFFFh
0x180011a93  cmp     rdx, rcx
0x180011a96  jnb     short loc_180011AA2
0x180011a98  add     rdx, rdx
0x180011a9b  inc     eax
0x180011a9d  cmp     eax, 3
0x180011aa0  jl      short loc_180011A89
0x180011aa2  mov     rcx, rbx
0x180011aa5  call    ?_Init@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$_Hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCaseInsensitiveStringHash@@UCaseInsensitiveStringEquality@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@2@$0A@@tr1@std@@@std@@IEAAX_K@Z; std::_Hash<std::tr1::_Umap_traits<std::wstring,std::vector<std::wstring>,std::_Hash_compare<std::wstring,CaseInsensitiveStringHash,CaseInsensitiveStringEquality>,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>,0>>::_Init(unsigned __int64)
0x180011aaa  mov     rdx, [rbx+8]
0x180011aae  mov     rcx, rbx
0x180011ab1  call    ?_Reinsert@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$_Hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCaseInsensitiveStringHash@@UCaseInsensitiveStringEquality@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@2@$0A@@tr1@std@@@std@@IEAAXV?$_List_iterator@V?$_List_val@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@2@@std@@@2@@Z; std::_Hash<std::tr1::_Umap_traits<std::wstring,std::vector<std::wstring>,std::_Hash_compare<std::wstring,CaseInsensitiveStringHash,CaseInsensitiveStringEquality>,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>,0>>::_Reinsert(std::_List_iterator<std::_List_val<std::pair<std::wstring const,std::vector<std::wstring>>>>)
0x180011ab6  add     rsp, 20h
0x180011aba  pop     rbx
0x180011abb  retn
```
