# std::_Tree<std::_Tset_traits<ushort const *,CFilterIgnoreSet::LPCWStrCompare,std::allocator<ushort const *>,0>>::_Insert_at<ushort const * const &,std::_Nil>(bool,std::_Tree_node<ushort const *,void *> *,ushort const * const &,std::_Nil)

- ea: `0x18001718c`
- end: `0x1800172f6`
- name: `??$_Insert_at@AEBQEBGU_Nil@std@@@?$_Tree@V?$_Tset_traits@PEBGULPCWStrCompare@CFilterIgnoreSet@@V?$allocator@PEBG@std@@$0A@@std@@@std@@IEAA?AV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@PEBG@std@@@std@@@1@_NPEAU?$_Tree_node@PEBGPEAX@1@AEBQEBGU_Nil@1@@Z`
- size: `362`
- prototype: `__int64 *__fastcall(_QWORD *, __int64 *, char, __int64 *, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000d380`

## callees

- `0x18000fb18`
- `0x180017160`
- `0x18001718c`
- `0x1800197a4`
- `0x18001983c`

## pseudocode

```c
__int64 *__fastcall std::_Tree<std::_Tset_traits<unsigned short const *,CFilterIgnoreSet::LPCWStrCompare,std::allocator<unsigned short const *>,0>>::_Insert_at<unsigned short const * const &,std::_Nil>(
        _QWORD *a1,
        __int64 *a2,
        char a3,
        __int64 *a4,
        __int64 a5)
{
  __int64 v9; // rax
  __int64 v10; // r8
  __int64 v11; // r10
  char v12; // r11
  __int64 v13; // rax
  __int64 v14; // r9
  __int64 v15; // rdx
  __int64 *v16; // rcx
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rcx
  __int64 *result; // rax

  if ( a1[1] >= 0x666666666666665uLL )
    std::_Xlength_error("map/set<T> too long");
  v9 = std::_Tree_buy<unsigned short const *>::_Buynode<unsigned short const * const &>(a1, a5);
  ++a1[1];
  v11 = v9;
  v12 = 0;
  *(_QWORD *)(v9 + 8) = a4;
  if ( a4 == (__int64 *)*a1 )
  {
    *(_QWORD *)(*a1 + 8LL) = v9;
    *(_QWORD *)*a1 = v9;
    *(_QWORD *)(*a1 + 16LL) = v9;
  }
  else if ( a3 )
  {
    *a4 = v9;
    if ( a4 == *(__int64 **)*a1 )
      *(_QWORD *)*a1 = v9;
  }
  else
  {
    a4[2] = v9;
    if ( a4 == *(__int64 **)(*a1 + 16LL) )
      *(_QWORD *)(*a1 + 16LL) = v9;
  }
  v13 = *(_QWORD *)(v9 + 8);
  v14 = v11;
  while ( *(_BYTE *)(v13 + 24) == v12 )
  {
    v15 = *(_QWORD *)(v14 + 8);
    v16 = *(__int64 **)(v15 + 8);
    v17 = *v16;
    if ( v15 == *v16 )
    {
      v17 = v16[2];
      if ( *(_BYTE *)(v17 + 24) == v12 )
        goto LABEL_17;
      if ( v14 == *(_QWORD *)(v15 + 16) )
        std::_Tree<std::_Tset_traits<unsigned short const *,CFilterIgnoreSet::LPCWStrCompare,std::allocator<unsigned short const *>,0>>::_Lrotate(
          a1,
          v15);
      *(_BYTE *)(*(_QWORD *)(v14 + 8) + 24LL) = 1;
      *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(v14 + 8) + 8LL) + 24LL) = v12;
      std::_Tree<std::_Tset_traits<unsigned short const *,CFilterIgnoreSet::LPCWStrCompare,std::allocator<unsigned short const *>,0>>::_Rrotate(
        a1,
        *(_QWORD *)(*(_QWORD *)(v14 + 8) + 8LL),
        v10,
        v14);
    }
    else
    {
      if ( *(_BYTE *)(v17 + 24) == v12 )
      {
LABEL_17:
        *(_BYTE *)(v15 + 24) = 1;
        *(_BYTE *)(v17 + 24) = 1;
        *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(v14 + 8) + 8LL) + 24LL) = v12;
        v14 = *(_QWORD *)(*(_QWORD *)(v14 + 8) + 8LL);
        goto LABEL_21;
      }
      if ( v14 == *(_QWORD *)v15 )
        std::_Tree<std::_Tset_traits<unsigned short const *,CFilterIgnoreSet::LPCWStrCompare,std::allocator<unsigned short const *>,0>>::_Rrotate(
          a1,
          v15,
          v10,
          *(_QWORD *)(v14 + 8));
      *(_BYTE *)(*(_QWORD *)(v14 + 8) + 24LL) = 1;
      *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(v14 + 8) + 8LL) + 24LL) = v12;
      std::_Tree<std::_Tset_traits<unsigned short const *,CFilterIgnoreSet::LPCWStrCompare,std::allocator<unsigned short const *>,0>>::_Lrotate(
        a1,
        *(_QWORD *)(*(_QWORD *)(v14 + 8) + 8LL));
    }
LABEL_21:
    v13 = *(_QWORD *)(v14 + 8);
  }
  v18 = *a1;
  *a2 = v11;
  v19 = *(_QWORD *)(v18 + 8);
  result = a2;
  *(_BYTE *)(v19 + 24) = 1;
  return result;
}

```

## disassembly

```asm
0x18001718c  push    rbx
0x18001718e  push    rsi
0x18001718f  push    rdi
0x180017190  push    r14
0x180017192  sub     rsp, 28h
0x180017196  mov     rax, 666666666666665h
0x1800171a0  mov     rdi, r9
0x1800171a3  mov     sil, r8b
0x1800171a6  mov     r14, rdx
0x1800171a9  mov     rbx, rcx
0x1800171ac  cmp     [rcx+8], rax
0x1800171b0  jb      short loc_1800171BF
0x1800171b2  lea     rcx, aMapSetTTooLong; "map/set<T> too long"
0x1800171b9  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x1800171bf  mov     rdx, [rsp+48h+arg_20]
0x1800171c4  call    ??$_Buynode@AEBQEBG@?$_Tree_buy@PEBGV?$allocator@PEBG@std@@@std@@QEAAPEAU?$_Tree_node@PEBGPEAX@1@AEBQEBG@Z; std::_Tree_buy<ushort const *>::_Buynode<ushort const * const &>(ushort const * const &)
0x1800171c9  inc     qword ptr [rbx+8]
0x1800171cd  mov     r10, rax
0x1800171d0  xor     r11d, r11d
0x1800171d3  mov     [rax+8], rdi
0x1800171d7  mov     rax, [rbx]
0x1800171da  cmp     rdi, rax
0x1800171dd  jnz     short loc_1800171F2
0x1800171df  mov     [rax+8], r10
0x1800171e3  mov     rcx, [rbx]
0x1800171e6  mov     [rcx], r10
0x1800171e9  mov     rcx, [rbx]
0x1800171ec  mov     [rcx+10h], r10
0x1800171f0  jmp     short loc_180017218
0x1800171f2  test    sil, sil
0x1800171f5  jz      short loc_180017207
0x1800171f7  mov     [rdi], r10
0x1800171fa  mov     rax, [rbx]
0x1800171fd  cmp     rdi, [rax]
0x180017200  jnz     short loc_180017218
0x180017202  mov     [rax], r10
0x180017205  jmp     short loc_180017218
0x180017207  mov     [rdi+10h], r10
0x18001720b  mov     rax, [rbx]
0x18001720e  cmp     rdi, [rax+10h]
0x180017212  jnz     short loc_180017218
0x180017214  mov     [rax+10h], r10
0x180017218  mov     rax, [r10+8]
0x18001721c  mov     r9, r10
0x18001721f  jmp     loc_1800172D1
0x180017224  mov     rdx, [r9+8]
0x180017228  mov     rcx, [rdx+8]
0x18001722c  mov     rax, [rcx]
0x18001722f  cmp     rdx, rax
0x180017232  jnz     short loc_180017275
0x180017234  mov     rax, [rcx+10h]
0x180017238  cmp     [rax+18h], r11b
0x18001723c  jz      short loc_18001727B
0x18001723e  cmp     r9, [rdx+10h]
0x180017242  jnz     short loc_18001724F
0x180017244  mov     rcx, rbx
0x180017247  mov     r9, rdx
0x18001724a  call    ?_Lrotate@?$_Tree@V?$_Tset_traits@PEBGULPCWStrCompare@CFilterIgnoreSet@@V?$allocator@PEBG@std@@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@PEBGPEAX@2@@Z; std::_Tree<std::_Tset_traits<ushort const *,CFilterIgnoreSet::LPCWStrCompare,std::allocator<ushort const *>,0>>::_Lrotate(std::_Tree_node<ushort const *,void *> *)
0x18001724f  mov     rax, [r9+8]
0x180017253  mov     byte ptr [rax+18h], 1
0x180017257  mov     rax, [r9+8]
0x18001725b  mov     rcx, [rax+8]
0x18001725f  mov     [rcx+18h], r11b
0x180017263  mov     rcx, rbx
0x180017266  mov     rdx, [r9+8]
0x18001726a  mov     rdx, [rdx+8]
0x18001726e  call    ?_Rrotate@?$_Tree@V?$_Tset_traits@PEBGULPCWStrCompare@CFilterIgnoreSet@@V?$allocator@PEBG@std@@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@PEBGPEAX@2@@Z; std::_Tree<std::_Tset_traits<ushort const *,CFilterIgnoreSet::LPCWStrCompare,std::allocator<ushort const *>,0>>::_Rrotate(std::_Tree_node<ushort const *,void *> *)
0x180017273  jmp     short loc_1800172CD
0x180017275  cmp     [rax+18h], r11b
0x180017279  jnz     short loc_180017299
0x18001727b  mov     byte ptr [rdx+18h], 1
0x18001727f  mov     byte ptr [rax+18h], 1
0x180017283  mov     rax, [r9+8]
0x180017287  mov     rcx, [rax+8]
0x18001728b  mov     [rcx+18h], r11b
0x18001728f  mov     rax, [r9+8]
0x180017293  mov     r9, [rax+8]
0x180017297  jmp     short loc_1800172CD
0x180017299  cmp     r9, [rdx]
0x18001729c  jnz     short loc_1800172A9
0x18001729e  mov     rcx, rbx
0x1800172a1  mov     r9, rdx
0x1800172a4  call    ?_Rrotate@?$_Tree@V?$_Tset_traits@PEBGULPCWStrCompare@CFilterIgnoreSet@@V?$allocator@PEBG@std@@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@PEBGPEAX@2@@Z; std::_Tree<std::_Tset_traits<ushort const *,CFilterIgnoreSet::LPCWStrCompare,std::allocator<ushort const *>,0>>::_Rrotate(std::_Tree_node<ushort const *,void *> *)
0x1800172a9  mov     rax, [r9+8]
0x1800172ad  mov     byte ptr [rax+18h], 1
0x1800172b1  mov     rax, [r9+8]
0x1800172b5  mov     rcx, [rax+8]
0x1800172b9  mov     [rcx+18h], r11b
0x1800172bd  mov     rcx, rbx
0x1800172c0  mov     rdx, [r9+8]
0x1800172c4  mov     rdx, [rdx+8]
0x1800172c8  call    ?_Lrotate@?$_Tree@V?$_Tset_traits@PEBGULPCWStrCompare@CFilterIgnoreSet@@V?$allocator@PEBG@std@@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@PEBGPEAX@2@@Z; std::_Tree<std::_Tset_traits<ushort const *,CFilterIgnoreSet::LPCWStrCompare,std::allocator<ushort const *>,0>>::_Lrotate(std::_Tree_node<ushort const *,void *> *)
0x1800172cd  mov     rax, [r9+8]
0x1800172d1  cmp     [rax+18h], r11b
0x1800172d5  jz      loc_180017224
0x1800172db  mov     rax, [rbx]
0x1800172de  mov     [r14], r10
0x1800172e1  mov     rcx, [rax+8]
0x1800172e5  mov     rax, r14
0x1800172e8  mov     byte ptr [rcx+18h], 1
0x1800172ec  add     rsp, 28h
0x1800172f0  pop     r14
0x1800172f2  pop     rdi
0x1800172f3  pop     rsi
0x1800172f4  pop     rbx
0x1800172f5  retn
```
