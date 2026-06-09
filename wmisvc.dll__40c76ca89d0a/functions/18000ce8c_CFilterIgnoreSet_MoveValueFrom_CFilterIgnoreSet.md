# CFilterIgnoreSet::MoveValueFrom(CFilterIgnoreSet &)

- ea: `0x18000ce8c`
- end: `0x18000cfa6`
- name: `?MoveValueFrom@CFilterIgnoreSet@@QEAAJAEAV1@@Z`
- size: `282`
- prototype: `__int64 __fastcall(CFilterIgnoreSet *__hidden this, struct CFilterIgnoreSet *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180017fd8`

## callees

- `0x18000ce8c`
- `0x18000d0b8`
- `0x18000d380`
- `0x1800197f4`

## import_xrefs

- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000cea7`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000cf1a`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000cea7`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000cf1a`

## pseudocode

```c
__int64 __fastcall CFilterIgnoreSet::MoveValueFrom(CFilterIgnoreSet *this, struct CFilterIgnoreSet *a2)
{
  void *v4; // rcx
  _QWORD *v5; // rbx
  _QWORD *v6; // r8
  void *v7; // rbp
  __int64 v8; // rcx
  _QWORD *i; // rax
  _QWORD *v10; // rbx
  bool v11; // zf
  _QWORD *v12; // r8
  __int64 v13; // rcx
  _QWORD *j; // rax
  __int64 v15; // r8
  _BYTE v17[40]; // [rsp+30h] [rbp-28h] BYREF
  __int64 v18; // [rsp+60h] [rbp+8h] BYREF
  __int64 v19; // [rsp+68h] [rbp+10h] BYREF

  v4 = (void *)*((_QWORD *)this + 2);
  if ( v4 )
  {
    CWin32DefaultArena::WbemMemFree(v4);
    *((_QWORD *)this + 2) = 0;
  }
  *((_QWORD *)this + 2) = *((_QWORD *)a2 + 2);
  *((_QWORD *)a2 + 2) = 0;
  v5 = **(_QWORD ***)this;
  while ( v5 != *(_QWORD **)this )
  {
    v6 = v5;
    v7 = (void *)v5[4];
    if ( !*((_BYTE *)v5 + 25) )
    {
      v8 = v5[2];
      if ( *(_BYTE *)(v8 + 25) )
      {
        for ( i = (_QWORD *)v5[1]; !*((_BYTE *)i + 25) && v5 == (_QWORD *)i[2]; i = (_QWORD *)i[1] )
          v5 = i;
      }
      else
      {
        i = std::_Tree_val<std::_Tree_simple_types<unsigned short const *>>::_Min((_QWORD *)v8);
      }
      v5 = i;
    }
    std::_Tree<std::_Tset_traits<unsigned short const *,CFilterIgnoreSet::LPCWStrCompare,std::allocator<unsigned short const *>,0>>::erase(
      this,
      &v18,
      v6);
    CWin32DefaultArena::WbemMemFree(v7);
  }
  v10 = **(_QWORD ***)a2;
  while ( v10 != *(_QWORD **)a2 )
  {
    v11 = *((_BYTE *)v10 + 25) == 0;
    v12 = v10;
    v18 = v10[4];
    if ( v11 )
    {
      v13 = v10[2];
      if ( *(_BYTE *)(v13 + 25) )
      {
        for ( j = (_QWORD *)v10[1]; !*((_BYTE *)j + 25) && v10 == (_QWORD *)j[2]; j = (_QWORD *)j[1] )
          v10 = j;
      }
      else
      {
        j = std::_Tree_val<std::_Tree_simple_types<unsigned short const *>>::_Min((_QWORD *)v13);
      }
      v10 = j;
    }
    std::_Tree<std::_Tset_traits<unsigned short const *,CFilterIgnoreSet::LPCWStrCompare,std::allocator<unsigned short const *>,0>>::erase(
      a2,
      &v19,
      v12);
    std::_Tree<std::_Tset_traits<unsigned short const *,CFilterIgnoreSet::LPCWStrCompare,std::allocator<unsigned short const *>,0>>::_Insert_nohint<unsigned short const * const &,std::_Nil>(
      (__int64)this,
      (__int64)v17,
      v15,
      &v18);
  }
  return 0;
}

```

## disassembly

```asm
0x18000ce8c  mov     [rsp+arg_10], rbx
0x18000ce91  push    rbp
0x18000ce92  push    rsi
0x18000ce93  push    rdi
0x18000ce94  sub     rsp, 40h
0x18000ce98  mov     rdi, rcx
0x18000ce9b  mov     rsi, rdx
0x18000ce9e  mov     rcx, [rcx+10h]
0x18000cea2  test    rcx, rcx
0x18000cea5  jz      short loc_18000CEB5
0x18000cea7  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18000cead  mov     qword ptr [rdi+10h], 0
0x18000ceb5  mov     rax, [rsi+10h]
0x18000ceb9  mov     [rdi+10h], rax
0x18000cebd  mov     qword ptr [rsi+10h], 0
0x18000cec5  mov     rbx, [rdi]
0x18000cec8  mov     rbx, [rbx]
0x18000cecb  cmp     rbx, [rdi]
0x18000cece  jz      short loc_18000CF22
0x18000ced0  cmp     byte ptr [rbx+19h], 0
0x18000ced4  mov     r8, rbx
0x18000ced7  mov     rbp, [rbx+20h]
0x18000cedb  jnz     short loc_18000CF0A
0x18000cedd  mov     rcx, [rbx+10h]
0x18000cee1  cmp     byte ptr [rcx+19h], 0
0x18000cee5  jnz     short loc_18000CEEE
0x18000cee7  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@PEBG@std@@@std@@SAPEAU?$_Tree_node@PEBGPEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<ushort const *>>::_Min(std::_Tree_node<ushort const *,void *> *)
0x18000ceec  jmp     short loc_18000CF07
0x18000ceee  mov     rax, [rbx+8]
0x18000cef2  jmp     short loc_18000CF01
0x18000cef4  cmp     rbx, [rax+10h]
0x18000cef8  jnz     short loc_18000CF07
0x18000cefa  mov     rbx, rax
0x18000cefd  mov     rax, [rax+8]
0x18000cf01  cmp     byte ptr [rax+19h], 0
0x18000cf05  jz      short loc_18000CEF4
0x18000cf07  mov     rbx, rax
0x18000cf0a  lea     rdx, [rsp+58h+arg_0]
0x18000cf0f  mov     rcx, rdi
0x18000cf12  call    ?erase@?$_Tree@V?$_Tset_traits@PEBGULPCWStrCompare@CFilterIgnoreSet@@V?$allocator@PEBG@std@@$0A@@std@@@std@@QEAA?AV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@PEBG@std@@@std@@@2@V32@@Z; std::_Tree<std::_Tset_traits<ushort const *,CFilterIgnoreSet::LPCWStrCompare,std::allocator<ushort const *>,0>>::erase(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<ushort const *>>>)
0x18000cf17  mov     rcx, rbp
0x18000cf1a  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18000cf20  jmp     short loc_18000CECB
0x18000cf22  mov     rbx, [rsi]
0x18000cf25  mov     rbx, [rbx]
0x18000cf28  cmp     rbx, [rsi]
0x18000cf2b  jz      short loc_18000CF97
0x18000cf2d  cmp     byte ptr [rbx+19h], 0
0x18000cf31  mov     r8, rbx
0x18000cf34  mov     rax, [rbx+20h]
0x18000cf38  mov     [rsp+58h+arg_0], rax
0x18000cf3d  jnz     short loc_18000CF6C
0x18000cf3f  mov     rcx, [rbx+10h]
0x18000cf43  cmp     byte ptr [rcx+19h], 0
0x18000cf47  jnz     short loc_18000CF50
0x18000cf49  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@PEBG@std@@@std@@SAPEAU?$_Tree_node@PEBGPEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<ushort const *>>::_Min(std::_Tree_node<ushort const *,void *> *)
0x18000cf4e  jmp     short loc_18000CF69
0x18000cf50  mov     rax, [rbx+8]
0x18000cf54  jmp     short loc_18000CF63
0x18000cf56  cmp     rbx, [rax+10h]
0x18000cf5a  jnz     short loc_18000CF69
0x18000cf5c  mov     rbx, rax
0x18000cf5f  mov     rax, [rax+8]
0x18000cf63  cmp     byte ptr [rax+19h], 0
0x18000cf67  jz      short loc_18000CF56
0x18000cf69  mov     rbx, rax
0x18000cf6c  lea     rdx, [rsp+58h+arg_8]
0x18000cf71  mov     rcx, rsi
0x18000cf74  call    ?erase@?$_Tree@V?$_Tset_traits@PEBGULPCWStrCompare@CFilterIgnoreSet@@V?$allocator@PEBG@std@@$0A@@std@@@std@@QEAA?AV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@PEBG@std@@@std@@@2@V32@@Z; std::_Tree<std::_Tset_traits<ushort const *,CFilterIgnoreSet::LPCWStrCompare,std::allocator<ushort const *>,0>>::erase(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<ushort const *>>>)
0x18000cf79  mov     al, cs:byte_180032D30
0x18000cf7f  lea     r9, [rsp+58h+arg_0]
0x18000cf84  lea     rdx, [rsp+58h+var_28]
0x18000cf89  mov     [rsp+58h+var_38], al
0x18000cf8d  mov     rcx, rdi
0x18000cf90  call    ??$_Insert_nohint@AEBQEBGU_Nil@std@@@?$_Tree@V?$_Tset_traits@PEBGULPCWStrCompare@CFilterIgnoreSet@@V?$allocator@PEBG@std@@$0A@@std@@@std@@IEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@PEBG@std@@@std@@@std@@_N@1@_NAEBQEBGU_Nil@1@@Z; std::_Tree<std::_Tset_traits<ushort const *,CFilterIgnoreSet::LPCWStrCompare,std::allocator<ushort const *>,0>>::_Insert_nohint<ushort const * const &,std::_Nil>(bool,ushort const * const &,std::_Nil)
0x18000cf95  jmp     short loc_18000CF28
0x18000cf97  mov     rbx, [rsp+58h+arg_10]
0x18000cf9c  xor     eax, eax
0x18000cf9e  add     rsp, 40h
0x18000cfa2  pop     rdi
0x18000cfa3  pop     rsi
0x18000cfa4  pop     rbp
0x18000cfa5  retn
```
