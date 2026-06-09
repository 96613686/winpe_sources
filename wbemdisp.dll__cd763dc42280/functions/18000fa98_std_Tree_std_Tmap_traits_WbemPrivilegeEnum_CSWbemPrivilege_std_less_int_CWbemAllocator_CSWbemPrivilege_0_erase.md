# std::_Tree<std::_Tmap_traits<WbemPrivilegeEnum,CSWbemPrivilege *,std::less<int>,CWbemAllocator<CSWbemPrivilege *>,0>>::erase(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<WbemPrivilegeEnum const,CSWbemPrivilege *>>>>)

- ea: `0x18000fa98`
- end: `0x18000fd5b`
- name: `?erase@?$_Tree@V?$_Tmap_traits@W4WbemPrivilegeEnum@@PEAVCSWbemPrivilege@@U?$less@H@std@@V?$CWbemAllocator@PEAVCSWbemPrivilege@@@@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4WbemPrivilegeEnum@@PEAVCSWbemPrivilege@@@std@@@std@@@std@@@2@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4WbemPrivilegeEnum@@PEAVCSWbemPrivilege@@@std@@@std@@@std@@@2@@Z`
- size: `707`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000f7d0`
- `0x18000f920`
- `0x18001a280`
- `0x18001c6e0`

## callees

- `0x18000fa98`
- `0x180013920`
- `0x18001900c`
- `0x18001905c`
- `0x18001a8b4`

## import_xrefs

- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000fd2f`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000fd2f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 **__fastcall std::_Tree<std::_Tmap_traits<enum WbemPrivilegeEnum,CSWbemPrivilege *,std::less<int>,CWbemAllocator<CSWbemPrivilege *>,0>>::erase(
        __int64 ***a1,
        __int64 **a2,
        __int64 *a3)
{
  __int64 *v5; // r14
  __int64 *v6; // rbp
  __int64 *v7; // rsi
  __int64 v8; // r10
  char v9; // r9
  __int64 **v10; // r11
  __int64 *i; // rbx
  __int64 *v12; // r9
  __int64 **v13; // r8
  __int64 *v14; // rax
  __int64 v15; // rcx
  __int64 j; // rax
  _BYTE *v17; // rdx
  _QWORD *v18; // rax
  char v19; // cl
  char v20; // r11
  __int64 v21; // rdx
  __int64 v22; // rcx
  __int64 **v23; // rax

  if ( *((_BYTE *)a3 + 25) )
    std::_Xout_of_range("invalid map/set<T> iterator");
  v5 = a3;
  v6 = a3;
  v7 = a3 + 2;
  v8 = a3[2];
  v9 = *(_BYTE *)(v8 + 25);
  v10 = (__int64 **)(a3 + 1);
  if ( v9 )
  {
    for ( i = *v10; !*((_BYTE *)i + 25) && a3 == (__int64 *)i[2]; i = (__int64 *)i[1] )
      a3 = i;
  }
  else
  {
    i = std::_Tree_val<std::_Tree_simple_types<std::pair<enum WbemPrivilegeEnum const,CSWbemPrivilege *>>>::_Min((__int64 *)a3[2]);
  }
  if ( *(_BYTE *)(*v5 + 25) )
    goto LABEL_13;
  if ( v9 )
  {
    v8 = *v5;
LABEL_13:
    v12 = *v10;
    if ( !*(_BYTE *)(v8 + 25) )
      *(_QWORD *)(v8 + 8) = v12;
    if ( (*a1)[1] == v5 )
    {
      (*a1)[1] = (__int64 *)v8;
    }
    else if ( (__int64 *)*v12 == v5 )
    {
      *v12 = v8;
    }
    else
    {
      v12[2] = v8;
    }
    v13 = *a1;
    if ( **a1 == v5 )
    {
      if ( *(_BYTE *)(v8 + 25) )
        v14 = v12;
      else
        v14 = std::_Tree_val<std::_Tree_simple_types<std::pair<enum WbemPrivilegeEnum const,CSWbemPrivilege *>>>::_Min((__int64 *)v8);
      *v13 = v14;
    }
    if ( (*a1)[2] == v5 )
    {
      if ( *(_BYTE *)(v8 + 25) )
      {
        v15 = (__int64)v12;
      }
      else
      {
        v15 = v8;
        for ( j = *(_QWORD *)(v8 + 16); !*(_BYTE *)(j + 25); j = *(_QWORD *)(v15 + 16) )
          v15 = *(_QWORD *)(v15 + 16);
      }
      (*a1)[2] = (__int64 *)v15;
    }
    v17 = v6 + 3;
    goto LABEL_44;
  }
  v8 = i[2];
  if ( i == v5 )
    goto LABEL_13;
  *(_QWORD *)(*v5 + 8) = i;
  *i = *v5;
  if ( i == (__int64 *)*v7 )
  {
    v12 = i;
  }
  else
  {
    v12 = (__int64 *)i[1];
    if ( !*(_BYTE *)(v8 + 25) )
      *(_QWORD *)(v8 + 8) = v12;
    *v12 = v8;
    i[2] = *v7;
    *(_QWORD *)(*v7 + 8) = i;
  }
  if ( (*a1)[1] == v5 )
  {
    (*a1)[1] = i;
  }
  else
  {
    v18 = *v10;
    if ( (__int64 *)**v10 == v5 )
      *v18 = i;
    else
      v18[2] = i;
  }
  i[1] = (__int64)*v10;
  v17 = v5 + 3;
  v19 = *((_BYTE *)i + 24);
  *((_BYTE *)i + 24) = *((_BYTE *)v5 + 24);
  *((_BYTE *)v5 + 24) = v19;
LABEL_44:
  v20 = 1;
  if ( *v17 != 1 )
    goto LABEL_67;
  while ( (__int64 *)v8 != (*a1)[1] && *(_BYTE *)(v8 + 24) == v20 )
  {
    v21 = *v12;
    if ( v8 == *v12 )
    {
      v21 = v12[2];
      if ( !*(_BYTE *)(v21 + 24) )
      {
        *(_BYTE *)(v21 + 24) = v20;
        *((_BYTE *)v12 + 24) = 0;
        std::_Tree<std::_Tmap_traits<ATL::CComBSTR,CWbemDispID,BSTRless,CWbemAllocator<CWbemDispID>,0>>::_Lrotate(a1);
        v21 = v12[2];
      }
      if ( !*(_BYTE *)(v21 + 25) )
      {
        if ( *(_BYTE *)(*(_QWORD *)v21 + 24LL) != v20 || *(_BYTE *)(*(_QWORD *)(v21 + 16) + 24LL) != v20 )
        {
          if ( *(_BYTE *)(*(_QWORD *)(v21 + 16) + 24LL) == v20 )
          {
            *(_BYTE *)(*(_QWORD *)v21 + 24LL) = v20;
            *(_BYTE *)(v21 + 24) = 0;
            std::_Tree<std::_Tmap_traits<long,CSWbemRefreshableItem *,std::less<long>,CWbemAllocator<CSWbemRefreshableItem *>,0>>::_Rrotate(
              a1,
              v21);
            v21 = v12[2];
          }
          *(_BYTE *)(v21 + 24) = *((_BYTE *)v12 + 24);
          *((_BYTE *)v12 + 24) = v20;
          *(_BYTE *)(*(_QWORD *)(v21 + 16) + 24LL) = v20;
          std::_Tree<std::_Tmap_traits<ATL::CComBSTR,CWbemDispID,BSTRless,CWbemAllocator<CWbemDispID>,0>>::_Lrotate(a1);
          break;
        }
LABEL_61:
        *(_BYTE *)(v21 + 24) = 0;
      }
    }
    else
    {
      if ( !*(_BYTE *)(v21 + 24) )
      {
        *(_BYTE *)(v21 + 24) = v20;
        *((_BYTE *)v12 + 24) = 0;
        std::_Tree<std::_Tmap_traits<long,CSWbemRefreshableItem *,std::less<long>,CWbemAllocator<CSWbemRefreshableItem *>,0>>::_Rrotate(
          a1,
          v12);
        v21 = *v12;
      }
      if ( !*(_BYTE *)(v21 + 25) )
      {
        v22 = *(_QWORD *)(v21 + 16);
        if ( *(_BYTE *)(v22 + 24) != v20 || *(_BYTE *)(*(_QWORD *)v21 + 24LL) != v20 )
        {
          if ( *(_BYTE *)(*(_QWORD *)v21 + 24LL) == v20 )
          {
            *(_BYTE *)(v22 + 24) = v20;
            *(_BYTE *)(v21 + 24) = 0;
            std::_Tree<std::_Tmap_traits<ATL::CComBSTR,CWbemDispID,BSTRless,CWbemAllocator<CWbemDispID>,0>>::_Lrotate(a1);
            v21 = *v12;
          }
          *(_BYTE *)(v21 + 24) = *((_BYTE *)v12 + 24);
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
    v8 = (__int64)v12;
    v12 = (__int64 *)v12[1];
  }
  *(_BYTE *)(v8 + 24) = v20;
LABEL_67:
  CWin32DefaultArena::WbemMemFree(v5);
  v23 = a1[1];
  if ( v23 )
    a1[1] = (__int64 **)((char *)v23 - 1);
  *a2 = i;
  return a2;
}

```

## disassembly

```asm
0x18000fa98  push    rbx
0x18000fa9a  push    rbp
0x18000fa9b  push    rsi
0x18000fa9c  push    rdi
0x18000fa9d  push    r12
0x18000fa9f  push    r14
0x18000faa1  push    r15
0x18000faa3  sub     rsp, 20h
0x18000faa7  mov     r15, rdx
0x18000faaa  mov     rdi, rcx
0x18000faad  xor     r12d, r12d
0x18000fab0  cmp     [r8+19h], r12b
0x18000fab4  jz      short loc_18000FAC3
0x18000fab6  lea     rcx, aInvalidMapSetT; "invalid map/set<T> iterator"
0x18000fabd  call    ?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x18000fac3  mov     r14, r8
0x18000fac6  mov     rbp, r8
0x18000fac9  lea     rsi, [r8+10h]
0x18000facd  mov     r10, [rsi]
0x18000fad0  mov     r9b, [r10+19h]
0x18000fad4  lea     r11, [r8+8]
0x18000fad8  test    r9b, r9b
0x18000fadb  jnz     short loc_18000FAEA
0x18000fadd  mov     rcx, r10
0x18000fae0  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4WbemPrivilegeEnum@@PEAVCSWbemPrivilege@@@std@@@std@@@std@@SAPEAU?$_Tree_node@U?$pair@$$CBW4WbemPrivilegeEnum@@PEAVCSWbemPrivilege@@@std@@PEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<WbemPrivilegeEnum const,CSWbemPrivilege *>>>::_Min(std::_Tree_node<std::pair<WbemPrivilegeEnum const,CSWbemPrivilege *>,void *> *)
0x18000fae5  mov     rbx, rax
0x18000fae8  jmp     short loc_18000FB02
0x18000faea  mov     rbx, [r11]
0x18000faed  jmp     short loc_18000FAFC
0x18000faef  cmp     r8, [rbx+10h]
0x18000faf3  jnz     short loc_18000FB02
0x18000faf5  mov     r8, rbx
0x18000faf8  mov     rbx, [rbx+8]
0x18000fafc  cmp     [rbx+19h], r12b
0x18000fb00  jz      short loc_18000FAEF
0x18000fb02  mov     rax, [r14]
0x18000fb05  cmp     [rax+19h], r12b
0x18000fb09  jnz     short loc_18000FB1E
0x18000fb0b  test    r9b, r9b
0x18000fb0e  jz      short loc_18000FB15
0x18000fb10  mov     r10, rax
0x18000fb13  jmp     short loc_18000FB1E
0x18000fb15  mov     r10, [rbx+10h]
0x18000fb19  cmp     rbx, r14
0x18000fb1c  jnz     short loc_18000FB9B
0x18000fb1e  mov     r9, [r11]
0x18000fb21  cmp     [r10+19h], r12b
0x18000fb25  jnz     short loc_18000FB2B
0x18000fb27  mov     [r10+8], r9
0x18000fb2b  mov     rax, [rdi]
0x18000fb2e  cmp     [rax+8], r14
0x18000fb32  jnz     short loc_18000FB3A
0x18000fb34  mov     [rax+8], r10
0x18000fb38  jmp     short loc_18000FB48
0x18000fb3a  cmp     [r9], r14
0x18000fb3d  jnz     short loc_18000FB44
0x18000fb3f  mov     [r9], r10
0x18000fb42  jmp     short loc_18000FB48
0x18000fb44  mov     [r9+10h], r10
0x18000fb48  mov     r8, [rdi]
0x18000fb4b  cmp     [r8], r14
0x18000fb4e  jnz     short loc_18000FB66
0x18000fb50  cmp     [r10+19h], r12b
0x18000fb54  jz      short loc_18000FB5B
0x18000fb56  mov     rax, r9
0x18000fb59  jmp     short loc_18000FB63
0x18000fb5b  mov     rcx, r10
0x18000fb5e  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4WbemPrivilegeEnum@@PEAVCSWbemPrivilege@@@std@@@std@@@std@@SAPEAU?$_Tree_node@U?$pair@$$CBW4WbemPrivilegeEnum@@PEAVCSWbemPrivilege@@@std@@PEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<WbemPrivilegeEnum const,CSWbemPrivilege *>>>::_Min(std::_Tree_node<std::pair<WbemPrivilegeEnum const,CSWbemPrivilege *>,void *> *)
0x18000fb63  mov     [r8], rax
0x18000fb66  mov     rdx, [rdi]
0x18000fb69  cmp     [rdx+10h], r14
0x18000fb6d  jnz     short loc_18000FB95
0x18000fb6f  cmp     [r10+19h], r12b
0x18000fb73  jz      short loc_18000FB7A
0x18000fb75  mov     rcx, r9
0x18000fb78  jmp     short loc_18000FB91
0x18000fb7a  mov     rcx, r10
0x18000fb7d  mov     rax, [r10+10h]
0x18000fb81  jmp     short loc_18000FB8B
0x18000fb83  mov     rcx, [rcx+10h]
0x18000fb87  mov     rax, [rcx+10h]
0x18000fb8b  cmp     [rax+19h], r12b
0x18000fb8f  jz      short loc_18000FB83
0x18000fb91  mov     [rdx+10h], rcx
0x18000fb95  lea     rdx, [rbp+18h]
0x18000fb99  jmp     short loc_18000FC03
0x18000fb9b  mov     [rax+8], rbx
0x18000fb9f  mov     rax, [r14]
0x18000fba2  mov     [rbx], rax
0x18000fba5  cmp     rbx, [rsi]
0x18000fba8  jnz     short loc_18000FBAF
0x18000fbaa  mov     r9, rbx
0x18000fbad  jmp     short loc_18000FBCE
0x18000fbaf  mov     r9, [rbx+8]
0x18000fbb3  cmp     [r10+19h], r12b
0x18000fbb7  jnz     short loc_18000FBBD
0x18000fbb9  mov     [r10+8], r9
0x18000fbbd  mov     [r9], r10
0x18000fbc0  mov     rax, [rsi]
0x18000fbc3  mov     [rbx+10h], rax
0x18000fbc7  mov     rax, [rsi]
0x18000fbca  mov     [rax+8], rbx
0x18000fbce  mov     rax, [rdi]
0x18000fbd1  cmp     [rax+8], r14
0x18000fbd5  jnz     short loc_18000FBDD
0x18000fbd7  mov     [rax+8], rbx
0x18000fbdb  jmp     short loc_18000FBEE
0x18000fbdd  mov     rax, [r11]
0x18000fbe0  cmp     [rax], r14
0x18000fbe3  jnz     short loc_18000FBEA
0x18000fbe5  mov     [rax], rbx
0x18000fbe8  jmp     short loc_18000FBEE
0x18000fbea  mov     [rax+10h], rbx
0x18000fbee  mov     rax, [r11]
0x18000fbf1  mov     [rbx+8], rax
0x18000fbf5  lea     rdx, [r14+18h]
0x18000fbf9  mov     cl, [rbx+18h]
0x18000fbfc  mov     al, [rdx]
0x18000fbfe  mov     [rbx+18h], al
0x18000fc01  mov     [rdx], cl
0x18000fc03  mov     r11b, 1
0x18000fc06  cmp     [rdx], r11b
0x18000fc09  jnz     loc_18000FD2C
0x18000fc0f  mov     rax, [rdi]
0x18000fc12  cmp     r10, [rax+8]
0x18000fc16  jz      loc_18000FD28
0x18000fc1c  cmp     [r10+18h], r11b
0x18000fc20  jnz     loc_18000FD28
0x18000fc26  mov     rdx, [r9]
0x18000fc29  cmp     r10, rdx
0x18000fc2c  jnz     short loc_18000FCAA
0x18000fc2e  mov     rdx, [r9+10h]
0x18000fc32  cmp     [rdx+18h], r12b
0x18000fc36  jnz     short loc_18000FC4F
0x18000fc38  mov     [rdx+18h], r11b
0x18000fc3c  mov     [r9+18h], r12b
0x18000fc40  mov     rdx, r9
0x18000fc43  mov     rcx, rdi
0x18000fc46  call    ?_Lrotate@?$_Tree@V?$_Tmap_traits@VCComBSTR@ATL@@VCWbemDispID@@UBSTRless@@V?$CWbemAllocator@VCWbemDispID@@@@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@U?$pair@$$CBVCComBSTR@ATL@@VCWbemDispID@@@std@@PEAX@2@@Z; std::_Tree<std::_Tmap_traits<ATL::CComBSTR,CWbemDispID,BSTRless,CWbemAllocator<CWbemDispID>,0>>::_Lrotate(std::_Tree_node<std::pair<ATL::CComBSTR const,CWbemDispID>,void *> *)
0x18000fc4b  mov     rdx, [r9+10h]
0x18000fc4f  cmp     [rdx+19h], r12b
0x18000fc53  jnz     loc_18000FCE3
0x18000fc59  mov     r8, [rdx]
0x18000fc5c  cmp     [r8+18h], r11b
0x18000fc60  jnz     short loc_18000FC6C
0x18000fc62  mov     rax, [rdx+10h]
0x18000fc66  cmp     [rax+18h], r11b
0x18000fc6a  jz      short loc_18000FCDF
0x18000fc6c  mov     rax, [rdx+10h]
0x18000fc70  cmp     [rax+18h], r11b
0x18000fc74  jnz     short loc_18000FC8A
0x18000fc76  mov     [r8+18h], r11b
0x18000fc7a  mov     [rdx+18h], r12b
0x18000fc7e  mov     rcx, rdi
0x18000fc81  call    ?_Rrotate@?$_Tree@V?$_Tmap_traits@JPEAVCSWbemRefreshableItem@@U?$less@J@std@@V?$CWbemAllocator@PEAVCSWbemRefreshableItem@@@@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@U?$pair@$$CBJPEAVCSWbemRefreshableItem@@@std@@PEAX@2@@Z; std::_Tree<std::_Tmap_traits<long,CSWbemRefreshableItem *,std::less<long>,CWbemAllocator<CSWbemRefreshableItem *>,0>>::_Rrotate(std::_Tree_node<std::pair<long const,CSWbemRefreshableItem *>,void *> *)
0x18000fc86  mov     rdx, [r9+10h]
0x18000fc8a  mov     al, [r9+18h]
0x18000fc8e  mov     [rdx+18h], al
0x18000fc91  mov     [r9+18h], r11b
0x18000fc95  mov     rax, [rdx+10h]
0x18000fc99  mov     [rax+18h], r11b
0x18000fc9d  mov     rdx, r9
0x18000fca0  mov     rcx, rdi
0x18000fca3  call    ?_Lrotate@?$_Tree@V?$_Tmap_traits@VCComBSTR@ATL@@VCWbemDispID@@UBSTRless@@V?$CWbemAllocator@VCWbemDispID@@@@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@U?$pair@$$CBVCComBSTR@ATL@@VCWbemDispID@@@std@@PEAX@2@@Z; std::_Tree<std::_Tmap_traits<ATL::CComBSTR,CWbemDispID,BSTRless,CWbemAllocator<CWbemDispID>,0>>::_Lrotate(std::_Tree_node<std::pair<ATL::CComBSTR const,CWbemDispID>,void *> *)
0x18000fca8  jmp     short loc_18000FD28
0x18000fcaa  cmp     [rdx+18h], r12b
0x18000fcae  jnz     short loc_18000FCC6
0x18000fcb0  mov     [rdx+18h], r11b
0x18000fcb4  mov     [r9+18h], r12b
0x18000fcb8  mov     rdx, r9
0x18000fcbb  mov     rcx, rdi
0x18000fcbe  call    ?_Rrotate@?$_Tree@V?$_Tmap_traits@JPEAVCSWbemRefreshableItem@@U?$less@J@std@@V?$CWbemAllocator@PEAVCSWbemRefreshableItem@@@@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@U?$pair@$$CBJPEAVCSWbemRefreshableItem@@@std@@PEAX@2@@Z; std::_Tree<std::_Tmap_traits<long,CSWbemRefreshableItem *,std::less<long>,CWbemAllocator<CSWbemRefreshableItem *>,0>>::_Rrotate(std::_Tree_node<std::pair<long const,CSWbemRefreshableItem *>,void *> *)
0x18000fcc3  mov     rdx, [r9]
0x18000fcc6  cmp     [rdx+19h], r12b
0x18000fcca  jnz     short loc_18000FCE3
0x18000fccc  mov     rcx, [rdx+10h]
0x18000fcd0  cmp     [rcx+18h], r11b
0x18000fcd4  jnz     short loc_18000FCEF
0x18000fcd6  mov     rax, [rdx]
0x18000fcd9  cmp     [rax+18h], r11b
0x18000fcdd  jnz     short loc_18000FCEF
0x18000fcdf  mov     [rdx+18h], r12b
0x18000fce3  mov     r10, r9
0x18000fce6  mov     r9, [r9+8]
0x18000fcea  jmp     loc_18000FC0F
0x18000fcef  mov     rax, [rdx]
0x18000fcf2  cmp     [rax+18h], r11b
0x18000fcf6  jnz     short loc_18000FD0B
0x18000fcf8  mov     [rcx+18h], r11b
0x18000fcfc  mov     [rdx+18h], r12b
0x18000fd00  mov     rcx, rdi
0x18000fd03  call    ?_Lrotate@?$_Tree@V?$_Tmap_traits@VCComBSTR@ATL@@VCWbemDispID@@UBSTRless@@V?$CWbemAllocator@VCWbemDispID@@@@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@U?$pair@$$CBVCComBSTR@ATL@@VCWbemDispID@@@std@@PEAX@2@@Z; std::_Tree<std::_Tmap_traits<ATL::CComBSTR,CWbemDispID,BSTRless,CWbemAllocator<CWbemDispID>,0>>::_Lrotate(std::_Tree_node<std::pair<ATL::CComBSTR const,CWbemDispID>,void *> *)
0x18000fd08  mov     rdx, [r9]
0x18000fd0b  mov     al, [r9+18h]
0x18000fd0f  mov     [rdx+18h], al
0x18000fd12  mov     [r9+18h], r11b
0x18000fd16  mov     rax, [rdx]
0x18000fd19  mov     [rax+18h], r11b
0x18000fd1d  mov     rdx, r9
0x18000fd20  mov     rcx, rdi
0x18000fd23  call    ?_Rrotate@?$_Tree@V?$_Tmap_traits@JPEAVCSWbemRefreshableItem@@U?$less@J@std@@V?$CWbemAllocator@PEAVCSWbemRefreshableItem@@@@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@U?$pair@$$CBJPEAVCSWbemRefreshableItem@@@std@@PEAX@2@@Z; std::_Tree<std::_Tmap_traits<long,CSWbemRefreshableItem *,std::less<long>,CWbemAllocator<CSWbemRefreshableItem *>,0>>::_Rrotate(std::_Tree_node<std::pair<long const,CSWbemRefreshableItem *>,void *> *)
0x18000fd28  mov     [r10+18h], r11b
0x18000fd2c  mov     rcx, r14
0x18000fd2f  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18000fd35  nop
0x18000fd36  mov     rax, [rdi+8]
0x18000fd3a  test    rax, rax
0x18000fd3d  jz      short loc_18000FD46
0x18000fd3f  dec     rax
0x18000fd42  mov     [rdi+8], rax
0x18000fd46  mov     [r15], rbx
0x18000fd49  mov     rax, r15
0x18000fd4c  add     rsp, 20h
0x18000fd50  pop     r15
0x18000fd52  pop     r14
0x18000fd54  pop     r12
0x18000fd56  pop     rdi
0x18000fd57  pop     rsi
0x18000fd58  pop     rbp
0x18000fd59  pop     rbx
0x18000fd5a  retn
```
