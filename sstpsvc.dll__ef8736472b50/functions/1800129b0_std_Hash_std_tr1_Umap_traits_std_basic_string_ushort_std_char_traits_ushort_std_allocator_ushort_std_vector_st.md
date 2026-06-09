# std::_Hash<std::tr1::_Umap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::_Hash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,CaseInsensitiveStringHash,CaseInsensitiveStringEquality>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>>>,0>>::_Check_size(void)

- ea: `0x1800129b0`
- end: `0x180012a4d`
- name: `?_Check_size@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$_Hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCaseInsensitiveStringHash@@UCaseInsensitiveStringEquality@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@2@$0A@@tr1@std@@@std@@IEAAXXZ`
- size: `157`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180012dfc`

## callees

- `0x180008540`
- `0x1800129b0`
- `0x1800132dc`

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
0x1800129b0  push    rbx
0x1800129b2  sub     rsp, 20h
0x1800129b6  mov     r8, [rcx+10h]
0x1800129ba  mov     rbx, rcx
0x1800129bd  mov     rdx, [rcx+48h]
0x1800129c1  xorps   xmm0, xmm0
0x1800129c4  test    r8, r8
0x1800129c7  js      short loc_1800129D0
0x1800129c9  cvtsi2ss xmm0, r8
0x1800129ce  jmp     short loc_1800129E6
0x1800129d0  mov     rax, r8
0x1800129d3  and     r8d, 1
0x1800129d7  shr     rax, 1
0x1800129da  or      rax, r8
0x1800129dd  cvtsi2ss xmm0, rax
0x1800129e2  addss   xmm0, xmm0
0x1800129e6  xorps   xmm1, xmm1
0x1800129e9  test    rdx, rdx
0x1800129ec  js      short loc_1800129F5
0x1800129ee  cvtsi2ss xmm1, rdx
0x1800129f3  jmp     short loc_180012A0D
0x1800129f5  mov     rax, rdx
0x1800129f8  mov     rcx, rdx
0x1800129fb  shr     rcx, 1
0x1800129fe  and     eax, 1
0x180012a01  or      rcx, rax
0x180012a04  cvtsi2ss xmm1, rcx
0x180012a09  addss   xmm1, xmm1
0x180012a0d  divss   xmm0, xmm1
0x180012a11  comiss  xmm0, dword ptr [rbx+50h]
0x180012a15  jbe     short loc_180012A46
0x180012a17  xor     eax, eax
0x180012a19  mov     rcx, 0FFFFFFFFFFFFFFFh
0x180012a23  cmp     rdx, rcx
0x180012a26  jnb     short loc_180012A32
0x180012a28  add     rdx, rdx
0x180012a2b  inc     eax
0x180012a2d  cmp     eax, 3
0x180012a30  jl      short loc_180012A19
0x180012a32  mov     rcx, rbx
0x180012a35  call    ?_Init@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$_Hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCaseInsensitiveStringHash@@UCaseInsensitiveStringEquality@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@2@$0A@@tr1@std@@@std@@IEAAX_K@Z; std::_Hash<std::tr1::_Umap_traits<std::wstring,std::vector<std::wstring>,std::_Hash_compare<std::wstring,CaseInsensitiveStringHash,CaseInsensitiveStringEquality>,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>,0>>::_Init(unsigned __int64)
0x180012a3a  mov     rdx, [rbx+8]
0x180012a3e  mov     rcx, rbx
0x180012a41  call    ?_Reinsert@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$_Hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCaseInsensitiveStringHash@@UCaseInsensitiveStringEquality@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@2@$0A@@tr1@std@@@std@@IEAAXV?$_List_iterator@V?$_List_val@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@2@@std@@@2@@Z; std::_Hash<std::tr1::_Umap_traits<std::wstring,std::vector<std::wstring>,std::_Hash_compare<std::wstring,CaseInsensitiveStringHash,CaseInsensitiveStringEquality>,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>,0>>::_Reinsert(std::_List_iterator<std::_List_val<std::pair<std::wstring const,std::vector<std::wstring>>>>)
0x180012a46  add     rsp, 20h
0x180012a4a  pop     rbx
0x180012a4b  retn
```
