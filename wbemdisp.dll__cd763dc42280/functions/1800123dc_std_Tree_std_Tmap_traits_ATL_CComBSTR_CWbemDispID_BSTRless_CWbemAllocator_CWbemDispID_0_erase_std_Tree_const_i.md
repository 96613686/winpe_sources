# std::_Tree<std::_Tmap_traits<ATL::CComBSTR,CWbemDispID,BSTRless,CWbemAllocator<CWbemDispID>,0>>::erase(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CComBSTR const,CWbemDispID>>>>)

- ea: `0x1800123dc`
- end: `0x1800126b5`
- name: `?erase@?$_Tree@V?$_Tmap_traits@VCComBSTR@ATL@@VCWbemDispID@@UBSTRless@@V?$CWbemAllocator@VCWbemDispID@@@@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVCComBSTR@ATL@@VCWbemDispID@@@std@@@std@@@std@@@2@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVCComBSTR@ATL@@VCWbemDispID@@@std@@@std@@@std@@@2@@Z`
- size: `729`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180012340`

## callees

- `0x1800123dc`
- `0x180013750`
- `0x18001900c`
- `0x18001905c`
- `0x18001a8b4`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18001267f`
- `OLEAUT32!__imp_SysFreeString` at `0x18001267f`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180012689`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180012689`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void ***__fastcall std::_Tree<std::_Tmap_traits<ATL::CComBSTR,CWbemDispID,BSTRless,CWbemAllocator<CWbemDispID>,0>>::erase(
        __int64 **a1,
        void ***a2,
        void **a3)
{
  char *v5; // rdi
  void **v6; // rbp
  _QWORD *v7; // r14
  void **v8; // r10
  char v9; // r9
  void ***v10; // r11
  void **i; // rbx
  void **v12; // r9
  __int64 *v13; // r8
  __int64 v14; // rax
  void **v15; // rcx
  _BYTE *j; // rax
  _BYTE *v17; // rdx
  _QWORD *v18; // rax
  char v19; // cl
  char v20; // r11
  char *v21; // rdx
  __int64 v22; // rcx
  __int64 *v23; // rax

  if ( *((_BYTE *)a3 + 25) )
    std::_Xout_of_range("invalid map/set<T> iterator");
  v5 = (char *)a3;
  v6 = a3;
  v7 = a3 + 2;
  v8 = (void **)a3[2];
  v9 = *((_BYTE *)v8 + 25);
  v10 = (void ***)(a3 + 1);
  if ( v9 )
  {
    for ( i = *v10; !*((_BYTE *)i + 25) && a3 == i[2]; i = (void **)i[1] )
      a3 = i;
  }
  else
  {
    i = (void **)std::_Tree_val<std::_Tree_simple_types<std::pair<long const,CSWbemRefreshableItem *>>>::_Min(a3[2]);
  }
  if ( *(_BYTE *)(*(_QWORD *)v5 + 25LL) )
    goto LABEL_13;
  if ( v9 )
  {
    v8 = *(void ***)v5;
LABEL_13:
    v12 = *v10;
    if ( !*((_BYTE *)v8 + 25) )
      v8[1] = v12;
    if ( (char *)(*a1)[1] == v5 )
    {
      (*a1)[1] = (__int64)v8;
    }
    else if ( *v12 == v5 )
    {
      *v12 = v8;
    }
    else
    {
      v12[2] = v8;
    }
    v13 = *a1;
    if ( (char *)**a1 == v5 )
    {
      if ( *((_BYTE *)v8 + 25) )
        v14 = (__int64)v12;
      else
        v14 = std::_Tree_val<std::_Tree_simple_types<std::pair<long const,CSWbemRefreshableItem *>>>::_Min(v8);
      *v13 = v14;
    }
    if ( (char *)(*a1)[2] == v5 )
    {
      if ( *((_BYTE *)v8 + 25) )
      {
        v15 = v12;
      }
      else
      {
        v15 = v8;
        for ( j = v8[2]; !j[25]; j = v15[2] )
          v15 = (void **)v15[2];
      }
      (*a1)[2] = (__int64)v15;
    }
    v17 = v6 + 3;
    goto LABEL_44;
  }
  v8 = (void **)i[2];
  if ( i == (void **)v5 )
    goto LABEL_13;
  *(_QWORD *)(*(_QWORD *)v5 + 8LL) = i;
  *i = *(void **)v5;
  if ( i == (void **)*v7 )
  {
    v12 = i;
  }
  else
  {
    v12 = (void **)i[1];
    if ( !*((_BYTE *)v8 + 25) )
      v8[1] = v12;
    *v12 = v8;
    i[2] = (void *)*v7;
    *(_QWORD *)(*v7 + 8LL) = i;
  }
  if ( (char *)(*a1)[1] == v5 )
  {
    (*a1)[1] = (__int64)i;
  }
  else
  {
    v18 = *v10;
    if ( **v10 == v5 )
      *v18 = i;
    else
      v18[2] = i;
  }
  i[1] = *v10;
  v17 = v5 + 24;
  v19 = *((_BYTE *)i + 24);
  *((_BYTE *)i + 24) = v5[24];
  v5[24] = v19;
LABEL_44:
  v20 = 1;
  if ( *v17 != 1 )
    goto LABEL_67;
  while ( v8 != (void **)(*a1)[1] && *((_BYTE *)v8 + 24) == v20 )
  {
    v21 = (char *)*v12;
    if ( v8 == *v12 )
    {
      v21 = (char *)v12[2];
      if ( !v21[24] )
      {
        v21[24] = v20;
        *((_BYTE *)v12 + 24) = 0;
        std::_Tree<std::_Tmap_traits<ATL::CComBSTR,CWbemDispID,BSTRless,CWbemAllocator<CWbemDispID>,0>>::_Lrotate(a1);
        v21 = (char *)v12[2];
      }
      if ( !v21[25] )
      {
        if ( *(_BYTE *)(*(_QWORD *)v21 + 24LL) != v20 || *(_BYTE *)(*((_QWORD *)v21 + 2) + 24LL) != v20 )
        {
          if ( *(_BYTE *)(*((_QWORD *)v21 + 2) + 24LL) == v20 )
          {
            *(_BYTE *)(*(_QWORD *)v21 + 24LL) = v20;
            v21[24] = 0;
            std::_Tree<std::_Tmap_traits<long,CSWbemRefreshableItem *,std::less<long>,CWbemAllocator<CSWbemRefreshableItem *>,0>>::_Rrotate(
              a1,
              v21);
            v21 = (char *)v12[2];
          }
          v21[24] = *((_BYTE *)v12 + 24);
          *((_BYTE *)v12 + 24) = v20;
          *(_BYTE *)(*((_QWORD *)v21 + 2) + 24LL) = v20;
          std::_Tree<std::_Tmap_traits<ATL::CComBSTR,CWbemDispID,BSTRless,CWbemAllocator<CWbemDispID>,0>>::_Lrotate(a1);
          break;
        }
LABEL_61:
        v21[24] = 0;
      }
    }
    else
    {
      if ( !v21[24] )
      {
        v21[24] = v20;
        *((_BYTE *)v12 + 24) = 0;
        std::_Tree<std::_Tmap_traits<long,CSWbemRefreshableItem *,std::less<long>,CWbemAllocator<CSWbemRefreshableItem *>,0>>::_Rrotate(
          a1,
          v12);
        v21 = (char *)*v12;
      }
      if ( !v21[25] )
      {
        v22 = *((_QWORD *)v21 + 2);
        if ( *(_BYTE *)(v22 + 24) != v20 || *(_BYTE *)(*(_QWORD *)v21 + 24LL) != v20 )
        {
          if ( *(_BYTE *)(*(_QWORD *)v21 + 24LL) == v20 )
          {
            *(_BYTE *)(v22 + 24) = v20;
            v21[24] = 0;
            std::_Tree<std::_Tmap_traits<ATL::CComBSTR,CWbemDispID,BSTRless,CWbemAllocator<CWbemDispID>,0>>::_Lrotate(a1);
            v21 = (char *)*v12;
          }
          v21[24] = *((_BYTE *)v12 + 24);
          *((_BYTE *)v12 + 24) = v20;
          *(_BYTE *)(*(_QWORD *)v21 + 24LL) = v20;
          std::_Tree<std::_Tmap_traits<long,CSWbemRefreshableItem *,std::less<long>,CWbemAllocator<CSWbemRefreshableItem *>,0>>::_Rrotate(
            a1,
            v12);
          break;
        }
        goto LABEL_61;
      }
    }
    v8 = v12;
    v12 = (void **)v12[1];
  }
  *((_BYTE *)v8 + 24) = v20;
LABEL_67:
  *((_QWORD *)v5 + 5) = &CWbemDispID::`vftable';
  SysFreeString(*((BSTR *)v5 + 4));
  CWin32DefaultArena::WbemMemFree(v5);
  v23 = a1[1];
  if ( v23 )
    a1[1] = (__int64 *)((char *)v23 - 1);
  *a2 = i;
  return a2;
}

```

## disassembly

```asm
0x1800123dc  push    rbx
0x1800123de  push    rbp
0x1800123df  push    rsi
0x1800123e0  push    rdi
0x1800123e1  push    r12
0x1800123e3  push    r14
0x1800123e5  push    r15
0x1800123e7  sub     rsp, 20h
0x1800123eb  mov     r15, rdx
0x1800123ee  mov     rsi, rcx
0x1800123f1  xor     r12d, r12d
0x1800123f4  cmp     [r8+19h], r12b
0x1800123f8  jz      short loc_180012407
0x1800123fa  lea     rcx, aInvalidMapSetT; "invalid map/set<T> iterator"
0x180012401  call    ?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x180012407  mov     rdi, r8
0x18001240a  mov     rbp, r8
0x18001240d  lea     r14, [r8+10h]
0x180012411  mov     r10, [r14]
0x180012414  mov     r9b, [r10+19h]
0x180012418  lea     r11, [r8+8]
0x18001241c  test    r9b, r9b
0x18001241f  jnz     short loc_18001242E
0x180012421  mov     rcx, r10
0x180012424  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBJPEAVCSWbemRefreshableItem@@@std@@@std@@@std@@SAPEAU?$_Tree_node@U?$pair@$$CBJPEAVCSWbemRefreshableItem@@@std@@PEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<long const,CSWbemRefreshableItem *>>>::_Min(std::_Tree_node<std::pair<long const,CSWbemRefreshableItem *>,void *> *)
0x180012429  mov     rbx, rax
0x18001242c  jmp     short loc_180012446
0x18001242e  mov     rbx, [r11]
0x180012431  jmp     short loc_180012440
0x180012433  cmp     r8, [rbx+10h]
0x180012437  jnz     short loc_180012446
0x180012439  mov     r8, rbx
0x18001243c  mov     rbx, [rbx+8]
0x180012440  cmp     [rbx+19h], r12b
0x180012444  jz      short loc_180012433
0x180012446  mov     rax, [rdi]
0x180012449  cmp     [rax+19h], r12b
0x18001244d  jnz     short loc_180012462
0x18001244f  test    r9b, r9b
0x180012452  jz      short loc_180012459
0x180012454  mov     r10, rax
0x180012457  jmp     short loc_180012462
0x180012459  mov     r10, [rbx+10h]
0x18001245d  cmp     rbx, rdi
0x180012460  jnz     short loc_1800124DF
0x180012462  mov     r9, [r11]
0x180012465  cmp     [r10+19h], r12b
0x180012469  jnz     short loc_18001246F
0x18001246b  mov     [r10+8], r9
0x18001246f  mov     rax, [rsi]
0x180012472  cmp     [rax+8], rdi
0x180012476  jnz     short loc_18001247E
0x180012478  mov     [rax+8], r10
0x18001247c  jmp     short loc_18001248C
0x18001247e  cmp     [r9], rdi
0x180012481  jnz     short loc_180012488
0x180012483  mov     [r9], r10
0x180012486  jmp     short loc_18001248C
0x180012488  mov     [r9+10h], r10
0x18001248c  mov     r8, [rsi]
0x18001248f  cmp     [r8], rdi
0x180012492  jnz     short loc_1800124AA
0x180012494  cmp     [r10+19h], r12b
0x180012498  jz      short loc_18001249F
0x18001249a  mov     rax, r9
0x18001249d  jmp     short loc_1800124A7
0x18001249f  mov     rcx, r10
0x1800124a2  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBJPEAVCSWbemRefreshableItem@@@std@@@std@@@std@@SAPEAU?$_Tree_node@U?$pair@$$CBJPEAVCSWbemRefreshableItem@@@std@@PEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<long const,CSWbemRefreshableItem *>>>::_Min(std::_Tree_node<std::pair<long const,CSWbemRefreshableItem *>,void *> *)
0x1800124a7  mov     [r8], rax
0x1800124aa  mov     rdx, [rsi]
0x1800124ad  cmp     [rdx+10h], rdi
0x1800124b1  jnz     short loc_1800124D9
0x1800124b3  cmp     [r10+19h], r12b
0x1800124b7  jz      short loc_1800124BE
0x1800124b9  mov     rcx, r9
0x1800124bc  jmp     short loc_1800124D5
0x1800124be  mov     rcx, r10
0x1800124c1  mov     rax, [r10+10h]
0x1800124c5  jmp     short loc_1800124CF
0x1800124c7  mov     rcx, [rcx+10h]
0x1800124cb  mov     rax, [rcx+10h]
0x1800124cf  cmp     [rax+19h], r12b
0x1800124d3  jz      short loc_1800124C7
0x1800124d5  mov     [rdx+10h], rcx
0x1800124d9  lea     rdx, [rbp+18h]
0x1800124dd  jmp     short loc_180012547
0x1800124df  mov     [rax+8], rbx
0x1800124e3  mov     rax, [rdi]
0x1800124e6  mov     [rbx], rax
0x1800124e9  cmp     rbx, [r14]
0x1800124ec  jnz     short loc_1800124F3
0x1800124ee  mov     r9, rbx
0x1800124f1  jmp     short loc_180012512
0x1800124f3  mov     r9, [rbx+8]
0x1800124f7  cmp     [r10+19h], r12b
0x1800124fb  jnz     short loc_180012501
0x1800124fd  mov     [r10+8], r9
0x180012501  mov     [r9], r10
0x180012504  mov     rax, [r14]
0x180012507  mov     [rbx+10h], rax
0x18001250b  mov     rax, [r14]
0x18001250e  mov     [rax+8], rbx
0x180012512  mov     rax, [rsi]
0x180012515  cmp     [rax+8], rdi
0x180012519  jnz     short loc_180012521
0x18001251b  mov     [rax+8], rbx
0x18001251f  jmp     short loc_180012532
0x180012521  mov     rax, [r11]
0x180012524  cmp     [rax], rdi
0x180012527  jnz     short loc_18001252E
0x180012529  mov     [rax], rbx
0x18001252c  jmp     short loc_180012532
0x18001252e  mov     [rax+10h], rbx
0x180012532  mov     rax, [r11]
0x180012535  mov     [rbx+8], rax
0x180012539  lea     rdx, [rdi+18h]
0x18001253d  mov     cl, [rbx+18h]
0x180012540  mov     al, [rdx]
0x180012542  mov     [rbx+18h], al
0x180012545  mov     [rdx], cl
0x180012547  mov     r11b, 1
0x18001254a  cmp     [rdx], r11b
0x18001254d  jnz     loc_180012670
0x180012553  mov     rax, [rsi]
0x180012556  cmp     r10, [rax+8]
0x18001255a  jz      loc_18001266C
0x180012560  cmp     [r10+18h], r11b
0x180012564  jnz     loc_18001266C
0x18001256a  mov     rdx, [r9]
0x18001256d  cmp     r10, rdx
0x180012570  jnz     short loc_1800125EE
0x180012572  mov     rdx, [r9+10h]
0x180012576  cmp     [rdx+18h], r12b
0x18001257a  jnz     short loc_180012593
0x18001257c  mov     [rdx+18h], r11b
0x180012580  mov     [r9+18h], r12b
0x180012584  mov     rdx, r9
0x180012587  mov     rcx, rsi
0x18001258a  call    ?_Lrotate@?$_Tree@V?$_Tmap_traits@VCComBSTR@ATL@@VCWbemDispID@@UBSTRless@@V?$CWbemAllocator@VCWbemDispID@@@@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@U?$pair@$$CBVCComBSTR@ATL@@VCWbemDispID@@@std@@PEAX@2@@Z; std::_Tree<std::_Tmap_traits<ATL::CComBSTR,CWbemDispID,BSTRless,CWbemAllocator<CWbemDispID>,0>>::_Lrotate(std::_Tree_node<std::pair<ATL::CComBSTR const,CWbemDispID>,void *> *)
0x18001258f  mov     rdx, [r9+10h]
0x180012593  cmp     [rdx+19h], r12b
0x180012597  jnz     loc_180012627
0x18001259d  mov     r8, [rdx]
0x1800125a0  cmp     [r8+18h], r11b
0x1800125a4  jnz     short loc_1800125B0
0x1800125a6  mov     rax, [rdx+10h]
0x1800125aa  cmp     [rax+18h], r11b
0x1800125ae  jz      short loc_180012623
0x1800125b0  mov     rax, [rdx+10h]
0x1800125b4  cmp     [rax+18h], r11b
0x1800125b8  jnz     short loc_1800125CE
0x1800125ba  mov     [r8+18h], r11b
0x1800125be  mov     [rdx+18h], r12b
0x1800125c2  mov     rcx, rsi
0x1800125c5  call    ?_Rrotate@?$_Tree@V?$_Tmap_traits@JPEAVCSWbemRefreshableItem@@U?$less@J@std@@V?$CWbemAllocator@PEAVCSWbemRefreshableItem@@@@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@U?$pair@$$CBJPEAVCSWbemRefreshableItem@@@std@@PEAX@2@@Z; std::_Tree<std::_Tmap_traits<long,CSWbemRefreshableItem *,std::less<long>,CWbemAllocator<CSWbemRefreshableItem *>,0>>::_Rrotate(std::_Tree_node<std::pair<long const,CSWbemRefreshableItem *>,void *> *)
0x1800125ca  mov     rdx, [r9+10h]
0x1800125ce  mov     al, [r9+18h]
0x1800125d2  mov     [rdx+18h], al
0x1800125d5  mov     [r9+18h], r11b
0x1800125d9  mov     rax, [rdx+10h]
0x1800125dd  mov     [rax+18h], r11b
0x1800125e1  mov     rdx, r9
0x1800125e4  mov     rcx, rsi
0x1800125e7  call    ?_Lrotate@?$_Tree@V?$_Tmap_traits@VCComBSTR@ATL@@VCWbemDispID@@UBSTRless@@V?$CWbemAllocator@VCWbemDispID@@@@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@U?$pair@$$CBVCComBSTR@ATL@@VCWbemDispID@@@std@@PEAX@2@@Z; std::_Tree<std::_Tmap_traits<ATL::CComBSTR,CWbemDispID,BSTRless,CWbemAllocator<CWbemDispID>,0>>::_Lrotate(std::_Tree_node<std::pair<ATL::CComBSTR const,CWbemDispID>,void *> *)
0x1800125ec  jmp     short loc_18001266C
0x1800125ee  cmp     [rdx+18h], r12b
0x1800125f2  jnz     short loc_18001260A
0x1800125f4  mov     [rdx+18h], r11b
0x1800125f8  mov     [r9+18h], r12b
0x1800125fc  mov     rdx, r9
0x1800125ff  mov     rcx, rsi
0x180012602  call    ?_Rrotate@?$_Tree@V?$_Tmap_traits@JPEAVCSWbemRefreshableItem@@U?$less@J@std@@V?$CWbemAllocator@PEAVCSWbemRefreshableItem@@@@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@U?$pair@$$CBJPEAVCSWbemRefreshableItem@@@std@@PEAX@2@@Z; std::_Tree<std::_Tmap_traits<long,CSWbemRefreshableItem *,std::less<long>,CWbemAllocator<CSWbemRefreshableItem *>,0>>::_Rrotate(std::_Tree_node<std::pair<long const,CSWbemRefreshableItem *>,void *> *)
0x180012607  mov     rdx, [r9]
0x18001260a  cmp     [rdx+19h], r12b
0x18001260e  jnz     short loc_180012627
0x180012610  mov     rcx, [rdx+10h]
0x180012614  cmp     [rcx+18h], r11b
0x180012618  jnz     short loc_180012633
0x18001261a  mov     rax, [rdx]
0x18001261d  cmp     [rax+18h], r11b
0x180012621  jnz     short loc_180012633
0x180012623  mov     [rdx+18h], r12b
0x180012627  mov     r10, r9
0x18001262a  mov     r9, [r9+8]
0x18001262e  jmp     loc_180012553
0x180012633  mov     rax, [rdx]
0x180012636  cmp     [rax+18h], r11b
0x18001263a  jnz     short loc_18001264F
0x18001263c  mov     [rcx+18h], r11b
0x180012640  mov     [rdx+18h], r12b
0x180012644  mov     rcx, rsi
0x180012647  call    ?_Lrotate@?$_Tree@V?$_Tmap_traits@VCComBSTR@ATL@@VCWbemDispID@@UBSTRless@@V?$CWbemAllocator@VCWbemDispID@@@@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@U?$pair@$$CBVCComBSTR@ATL@@VCWbemDispID@@@std@@PEAX@2@@Z; std::_Tree<std::_Tmap_traits<ATL::CComBSTR,CWbemDispID,BSTRless,CWbemAllocator<CWbemDispID>,0>>::_Lrotate(std::_Tree_node<std::pair<ATL::CComBSTR const,CWbemDispID>,void *> *)
0x18001264c  mov     rdx, [r9]
0x18001264f  mov     al, [r9+18h]
0x180012653  mov     [rdx+18h], al
0x180012656  mov     [r9+18h], r11b
0x18001265a  mov     rax, [rdx]
0x18001265d  mov     [rax+18h], r11b
0x180012661  mov     rdx, r9
0x180012664  mov     rcx, rsi
0x180012667  call    ?_Rrotate@?$_Tree@V?$_Tmap_traits@JPEAVCSWbemRefreshableItem@@U?$less@J@std@@V?$CWbemAllocator@PEAVCSWbemRefreshableItem@@@@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@U?$pair@$$CBJPEAVCSWbemRefreshableItem@@@std@@PEAX@2@@Z; std::_Tree<std::_Tmap_traits<long,CSWbemRefreshableItem *,std::less<long>,CWbemAllocator<CSWbemRefreshableItem *>,0>>::_Rrotate(std::_Tree_node<std::pair<long const,CSWbemRefreshableItem *>,void *> *)
0x18001266c  mov     [r10+18h], r11b
0x180012670  lea     rax, ??_7CWbemDispID@@6B@; const CWbemDispID::`vftable'
0x180012677  mov     [rdi+28h], rax
0x18001267b  mov     rcx, [rdi+20h]; bstrString
0x18001267f  call    cs:__imp_SysFreeString
0x180012685  nop
0x180012686  mov     rcx, rdi
0x180012689  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18001268f  nop
0x180012690  mov     rax, [rsi+8]
0x180012694  test    rax, rax
0x180012697  jz      short loc_1800126A0
0x180012699  dec     rax
0x18001269c  mov     [rsi+8], rax
0x1800126a0  mov     [r15], rbx
0x1800126a3  mov     rax, r15
0x1800126a6  add     rsp, 20h
0x1800126aa  pop     r15
0x1800126ac  pop     r14
0x1800126ae  pop     r12
0x1800126b0  pop     rdi
0x1800126b1  pop     rsi
0x1800126b2  pop     rbp
0x1800126b3  pop     rbx
0x1800126b4  retn
```
