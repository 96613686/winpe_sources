# std::_Tree<std::_Tset_traits<Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessCCvDDPtrByImageId,std::allocator<Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,0>>::_Insert_nohint<Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,std::_Nil>(bool,Microsoft::Windows::Performance::CCvDDCache::CCvDD const * &&,std::_Nil)

- ea: `0x180014048`
- end: `0x18001424c`
- name: `??$_Insert_nohint@PEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@U_Nil@std@@@?$_Tree@V?$_Tset_traits@PEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessCCvDDPtrByImageId@2345@V?$allocator@PEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@$0A@@std@@@std@@IEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@PEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@_N@1@_N$$QEAPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@U_Nil@1@@Z`
- size: `516`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180015e34`

## callees

- `0x180013648`
- `0x180014048`

## pseudocode

```c
__int64 __fastcall std::_Tree<std::_Tset_traits<Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessCCvDDPtrByImageId,std::allocator<Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,0>>::_Insert_nohint<Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,std::_Nil>(
        __int64 ***a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        char a5)
{
  int v7; // r12d
  __int64 **v8; // rdi
  __int64 *v9; // rdx
  __int64 v10; // rsi
  __int64 *v11; // rax
  __int64 v12; // rcx
  unsigned int v13; // r8d
  unsigned int v14; // r8d
  char *v15; // r8
  char *v16; // rcx
  signed __int64 v17; // r8
  int v18; // r9d
  int v19; // r10d
  char v20; // r11
  __int64 *v21; // r9
  __int64 result; // rax
  __int64 j; // rcx
  __int64 *i; // rcx
  __int64 v25; // rdx
  __int64 v26; // r10
  unsigned int v27; // ecx
  unsigned int v28; // ecx
  char *v29; // rdx
  char *v30; // rcx
  signed __int64 v31; // rdx
  int v32; // r10d
  int v33; // r8d
  char v34; // [rsp+60h] [rbp+8h] BYREF

  try
  {
    v7 = (int)a1;
    v8 = *a1;
    v9 = (*a1)[1];
    if ( *((_BYTE *)v9 + 25) )
    {
      v20 = 1;
      v21 = (__int64 *)*a1;
      v11 = (__int64 *)*a1;
    }
    else
    {
      v10 = *(_QWORD *)a4;
      do
      {
        v11 = v9;
        v12 = v9[4];
        v13 = *(_DWORD *)(v12 + 132);
        if ( *(_DWORD *)(v10 + 132) < v13 )
          goto LABEL_16;
        if ( *(_DWORD *)(v10 + 132) > v13 )
          goto LABEL_17;
        v14 = *(_DWORD *)(v12 + 136);
        if ( *(_DWORD *)(v10 + 136) < v14 )
          goto LABEL_16;
        if ( *(_DWORD *)(v10 + 136) > v14 )
          goto LABEL_17;
        v15 = (char *)(v12 + 32);
        if ( *(_QWORD *)(v12 + 56) >= 8u )
          v15 = *(char **)v15;
        v16 = (char *)(v10 + 32);
        if ( *(_QWORD *)(v10 + 56) >= 8u )
          v16 = *(char **)v16;
        v17 = v15 - v16;
        do
        {
          v18 = *(unsigned __int16 *)&v16[v17];
          v19 = *(unsigned __int16 *)v16 - v18;
          if ( v19 )
            break;
          v16 += 2;
        }
        while ( v18 );
        if ( v19 >= 0 )
        {
LABEL_17:
          v20 = 0;
          v9 = (__int64 *)v9[2];
        }
        else
        {
LABEL_16:
          v20 = 1;
          v9 = (__int64 *)*v9;
        }
      }
      while ( !*((_BYTE *)v9 + 25) );
      v21 = v11;
      if ( !v20 )
      {
LABEL_37:
        v25 = *(_QWORD *)a4;
        v26 = v11[4];
        v27 = *(_DWORD *)(*(_QWORD *)a4 + 132LL);
        if ( *(_DWORD *)(v26 + 132) < v27 )
          goto LABEL_50;
        if ( *(_DWORD *)(v26 + 132) > v27 )
          goto LABEL_49;
        v28 = *(_DWORD *)(v25 + 136);
        if ( *(_DWORD *)(v26 + 136) < v28 )
          goto LABEL_50;
        if ( *(_DWORD *)(v26 + 136) > v28 )
          goto LABEL_49;
        v29 = (char *)(v25 + 32);
        if ( *((_QWORD *)v29 + 3) >= 8u )
          v29 = *(char **)v29;
        v30 = (char *)(v26 + 32);
        if ( *(_QWORD *)(v26 + 56) >= 8u )
          v30 = *(char **)v30;
        v31 = v29 - v30;
        do
        {
          v32 = *(unsigned __int16 *)&v30[v31];
          v33 = *(unsigned __int16 *)v30 - v32;
          if ( v33 )
            break;
          v30 += 2;
        }
        while ( v32 );
        if ( v33 < 0 )
        {
LABEL_50:
          *(_QWORD *)a2 = *(_QWORD *)std::_Tree<std::_Tset_traits<unsigned short const *,std::less<unsigned short const *>,std::allocator<unsigned short const *>,0>>::_Insert_at<unsigned short const * const &,std::_Nil>(
                                       v7,
                                       (unsigned int)&v34,
                                       v20,
                                       (_DWORD)v21,
                                       a4);
          *(_BYTE *)(a2 + 8) = 1;
          return a2;
        }
        else
        {
LABEL_49:
          *(_QWORD *)a2 = v11;
          *(_BYTE *)(a2 + 8) = 0;
          return a2;
        }
      }
    }
    if ( v21 == *v8 )
    {
      *(_QWORD *)a2 = *(_QWORD *)std::_Tree<std::_Tset_traits<unsigned short const *,std::less<unsigned short const *>,std::allocator<unsigned short const *>,0>>::_Insert_at<unsigned short const * const &,std::_Nil>(
                                   v7,
                                   (unsigned int)&v34,
                                   1,
                                   (_DWORD)v21,
                                   a4);
      *(_BYTE *)(a2 + 8) = 1;
      return a2;
    }
    if ( *((_BYTE *)v21 + 25) )
    {
      v11 = (__int64 *)v21[2];
    }
    else if ( *(_BYTE *)(*v21 + 25) )
    {
      for ( i = (__int64 *)v21[1]; !*((_BYTE *)i + 25) && v11 == (__int64 *)*i; i = (__int64 *)i[1] )
        v11 = i;
      if ( !*((_BYTE *)v11 + 25) )
        v11 = i;
    }
    else
    {
      v11 = (__int64 *)*v21;
      for ( j = *(_QWORD *)(*v21 + 16); !*(_BYTE *)(j + 25); j = v11[2] )
        v11 = (__int64 *)v11[2];
    }
    goto LABEL_37;
  }
  catch ( ... )
  {
    throw;
  }
  return result;
}

```

## disassembly

```asm
0x180014048  push    rdi
0x18001404a  push    r12
0x18001404c  push    r15
0x18001404e  sub     rsp, 40h
0x180014052  mov     [rsp+58h+var_28], 0FFFFFFFFFFFFFFFEh
0x18001405b  mov     [rsp+58h+arg_8], rbx
0x180014060  mov     [rsp+58h+arg_10], rsi
0x180014065  mov     r15, r9
0x180014068  mov     rbx, rdx
0x18001406b  mov     r12, rcx
0x18001406e  mov     rdi, [rcx]
0x180014071  mov     rdx, [rdi+8]
0x180014075  cmp     byte ptr [rdx+19h], 0
0x180014079  jnz     loc_18001410B
0x18001407f  mov     rsi, [r9]
0x180014082  mov     rax, rdx
0x180014085  mov     rcx, [rdx+20h]
0x180014089  mov     r8d, [rcx+84h]
0x180014090  cmp     [rsi+84h], r8d
0x180014097  jb      short loc_1800140E8
0x180014099  ja      short loc_1800140F0
0x18001409b  mov     r8d, [rcx+88h]
0x1800140a2  cmp     [rsi+88h], r8d
0x1800140a9  jb      short loc_1800140E8
0x1800140ab  ja      short loc_1800140F0
0x1800140ad  lea     r8, [rcx+20h]
0x1800140b1  cmp     qword ptr [rcx+38h], 8
0x1800140b6  jb      short loc_1800140BB
0x1800140b8  mov     r8, [r8]
0x1800140bb  lea     rcx, [rsi+20h]
0x1800140bf  cmp     qword ptr [rsi+38h], 8
0x1800140c4  jb      short loc_1800140C9
0x1800140c6  mov     rcx, [rcx]
0x1800140c9  sub     r8, rcx
0x1800140cc  movzx   r10d, word ptr [rcx]
0x1800140d0  movzx   r9d, word ptr [rcx+r8]
0x1800140d5  sub     r10d, r9d
0x1800140d8  jnz     short loc_1800140E3
0x1800140da  add     rcx, 2
0x1800140de  test    r9d, r9d
0x1800140e1  jnz     short loc_1800140CC
0x1800140e3  test    r10d, r10d
0x1800140e6  jns     short loc_1800140F0
0x1800140e8  mov     r11b, 1
0x1800140eb  mov     rdx, [rdx]
0x1800140ee  jmp     short loc_1800140F7
0x1800140f0  xor     r11b, r11b
0x1800140f3  mov     rdx, [rdx+10h]
0x1800140f7  cmp     byte ptr [rdx+19h], 0
0x1800140fb  jz      short loc_180014082
0x1800140fd  mov     r9, rax
0x180014100  test    r11b, r11b
0x180014103  jz      loc_18001419A
0x180014109  jmp     short loc_180014114
0x18001410b  mov     r11b, 1
0x18001410e  mov     r9, rdi
0x180014111  mov     rax, rdi
0x180014114  cmp     r9, [rdi]
0x180014117  jnz     short loc_18001414B
0x180014119  mov     al, [rsp+58h+arg_20]
0x180014120  mov     [rsp+58h+var_30], al
0x180014124  mov     [rsp+58h+var_38], r15
0x180014129  mov     r8b, 1
0x18001412c  lea     rdx, [rsp+58h+arg_0]
0x180014131  mov     rcx, r12
0x180014134  call    ??$_Insert_at@AEBQEBGU_Nil@std@@@?$_Tree@V?$_Tset_traits@PEBGU?$less@PEBG@std@@V?$allocator@PEBG@2@$0A@@std@@@std@@IEAA?AV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@PEBG@std@@@std@@@1@_NPEAU?$_Tree_node@PEBGPEAX@1@AEBQEBGU_Nil@1@@Z; std::_Tree<std::_Tset_traits<ushort const *,std::less<ushort const *>,std::allocator<ushort const *>,0>>::_Insert_at<ushort const * const &,std::_Nil>(bool,std::_Tree_node<ushort const *,void *> *,ushort const * const &,std::_Nil)
0x180014139  mov     rax, [rax]
0x18001413c  mov     [rbx], rax
0x18001413f  mov     byte ptr [rbx+8], 1
0x180014143  mov     rax, rbx
0x180014146  jmp     loc_180014237
0x18001414b  cmp     byte ptr [r9+19h], 0
0x180014150  jz      short loc_180014158
0x180014152  mov     rax, [r9+10h]
0x180014156  jmp     short loc_18001419A
0x180014158  mov     rcx, [r9]
0x18001415b  cmp     byte ptr [rcx+19h], 0
0x18001415f  jnz     short loc_18001417A
0x180014161  mov     rax, rcx
0x180014164  mov     rcx, [rcx+10h]
0x180014168  jmp     short loc_180014172
0x18001416a  mov     rax, [rax+10h]
0x18001416e  mov     rcx, [rax+10h]
0x180014172  cmp     byte ptr [rcx+19h], 0
0x180014176  jz      short loc_18001416A
0x180014178  jmp     short loc_18001419A
0x18001417a  mov     rcx, [r9+8]
0x18001417e  jmp     short loc_18001418C
0x180014180  cmp     rax, [rcx]
0x180014183  jnz     short loc_180014192
0x180014185  mov     rax, rcx
0x180014188  mov     rcx, [rcx+8]
0x18001418c  cmp     byte ptr [rcx+19h], 0
0x180014190  jz      short loc_180014180
0x180014192  cmp     byte ptr [rax+19h], 0
0x180014196  cmovz   rax, rcx
0x18001419a  mov     rdx, [r15]
0x18001419d  mov     r10, [rax+20h]
0x1800141a1  mov     ecx, [rdx+84h]
0x1800141a7  cmp     [r10+84h], ecx
0x1800141ae  jb      short loc_18001420A
0x1800141b0  ja      short loc_1800141FE
0x1800141b2  mov     ecx, [rdx+88h]
0x1800141b8  cmp     [r10+88h], ecx
0x1800141bf  jb      short loc_18001420A
0x1800141c1  ja      short loc_1800141FE
0x1800141c3  add     rdx, 20h ; ' '
0x1800141c7  cmp     qword ptr [rdx+18h], 8
0x1800141cc  jb      short loc_1800141D1
0x1800141ce  mov     rdx, [rdx]
0x1800141d1  lea     rcx, [r10+20h]
0x1800141d5  cmp     qword ptr [rcx+18h], 8
0x1800141da  jb      short loc_1800141DF
0x1800141dc  mov     rcx, [rcx]
0x1800141df  sub     rdx, rcx
0x1800141e2  movzx   r8d, word ptr [rcx]
0x1800141e6  movzx   r10d, word ptr [rcx+rdx]
0x1800141eb  sub     r8d, r10d
0x1800141ee  jnz     short loc_1800141F9
0x1800141f0  add     rcx, 2
0x1800141f4  test    r10d, r10d
0x1800141f7  jnz     short loc_1800141E2
0x1800141f9  test    r8d, r8d
0x1800141fc  js      short loc_18001420A
0x1800141fe  mov     [rbx], rax
0x180014201  mov     byte ptr [rbx+8], 0
0x180014205  mov     rax, rbx
0x180014208  jmp     short loc_180014237
0x18001420a  mov     al, [rsp+58h+arg_20]
0x180014211  mov     [rsp+58h+var_30], al
0x180014215  mov     [rsp+58h+var_38], r15
0x18001421a  mov     r8b, r11b
0x18001421d  lea     rdx, [rsp+58h+arg_0]
0x180014222  mov     rcx, r12
0x180014225  call    ??$_Insert_at@AEBQEBGU_Nil@std@@@?$_Tree@V?$_Tset_traits@PEBGU?$less@PEBG@std@@V?$allocator@PEBG@2@$0A@@std@@@std@@IEAA?AV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@PEBG@std@@@std@@@1@_NPEAU?$_Tree_node@PEBGPEAX@1@AEBQEBGU_Nil@1@@Z; std::_Tree<std::_Tset_traits<ushort const *,std::less<ushort const *>,std::allocator<ushort const *>,0>>::_Insert_at<ushort const * const &,std::_Nil>(bool,std::_Tree_node<ushort const *,void *> *,ushort const * const &,std::_Nil)
0x18001422a  mov     rax, [rax]
0x18001422d  mov     [rbx], rax
0x180014230  mov     byte ptr [rbx+8], 1
0x180014234  mov     rax, rbx
0x180014237  mov     rbx, [rsp+58h+arg_8]
0x18001423c  mov     rsi, [rsp+58h+arg_10]
0x180014241  add     rsp, 40h
0x180014245  pop     r15
0x180014247  pop     r12
0x180014249  pop     rdi
0x18001424a  retn
```
