# std::_Tree<std::_Tmap_traits<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>::_Insert_at<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *> &,std::_Tree_node<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,void *> *>(bool,std::_Tree_node<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,void *> *,std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *> &,std::_Tree_node<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,void *> *)

- ea: `0x1800133c4`
- end: `0x180013641`
- name: `??$_Insert_at@AEAU?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@PEAU?$_Tree_node@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@PEAX@2@@?$_Tree@V?$_Tmap_traits@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@$0A@@std@@@std@@IEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@1@_NPEAU?$_Tree_node@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@PEAX@1@AEAU?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@1@1@Z`
- size: `637`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180013ae0`
- `0x180013ecc`

## callees

- `0x180001540`
- `0x1800133c4`
- `0x18001ce38`

## pseudocode

```c
_QWORD *__fastcall std::_Tree<std::_Tmap_traits<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>::_Insert_at<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *> &,std::_Tree_node<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,void *> *>(
        _QWORD *a1,
        _QWORD *a2,
        char a3,
        _QWORD *a4,
        int a5,
        __int64 a6)
{
  unsigned __int64 v6; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rdx
  __int64 *v12; // rcx
  __int64 *v13; // r8
  __int64 *v14; // rax
  __int64 *v15; // r8
  __int64 **v16; // rax
  _QWORD *v17; // rcx
  _QWORD *v18; // r8
  __int64 v19; // rax
  _QWORD *v20; // rax
  __int64 v21; // r8
  __int64 v22; // rax
  _QWORD *v23; // rax
  _QWORD *v24; // rax
  __int64 v25; // rax
  __int64 v26; // rcx
  _QWORD *result; // rax

  v6 = a1[1];
  if ( v6 >= 0x555555555555554LL )
  {
    std::_Tree_buy<unsigned short const *>::_Freenode0(0x555555555555554LL, a6);
    std::_Xlength_error("map/set<T> too long");
  }
  a1[1] = v6 + 1;
  *(_QWORD *)(a6 + 8) = a4;
  if ( a4 == (_QWORD *)*a1 )
  {
    *(_QWORD *)(*a1 + 8LL) = a6;
    *(_QWORD *)*a1 = a6;
    v9 = *a1;
LABEL_8:
    *(_QWORD *)(v9 + 16) = a6;
    goto LABEL_9;
  }
  if ( a3 )
  {
    *a4 = a6;
    if ( a4 == *(_QWORD **)*a1 )
      *(_QWORD *)*a1 = a6;
    goto LABEL_9;
  }
  a4[2] = a6;
  v9 = *a1;
  if ( a4 == *(_QWORD **)(*a1 + 16LL) )
    goto LABEL_8;
LABEL_9:
  v10 = *(_QWORD *)(a6 + 8);
  v11 = a6;
  while ( !*(_BYTE *)(v10 + 24) )
  {
    v12 = *(__int64 **)(v11 + 8);
    v13 = (__int64 *)v12[1];
    v14 = (__int64 *)*v13;
    if ( v12 == (__int64 *)*v13 )
    {
      v14 = (__int64 *)v13[2];
      if ( !*((_BYTE *)v14 + 24) )
        goto LABEL_30;
      v15 = (__int64 *)v12[2];
      if ( (__int64 *)v11 == v15 )
      {
        v11 = *(_QWORD *)(v11 + 8);
        v12[2] = *v15;
        if ( !*(_BYTE *)(*v15 + 25) )
          *(_QWORD *)(*v15 + 8) = v12;
        v15[1] = v12[1];
        if ( v12 == *(__int64 **)(*a1 + 8LL) )
        {
          *(_QWORD *)(*a1 + 8LL) = v15;
        }
        else
        {
          v16 = (__int64 **)v12[1];
          if ( v12 == *v16 )
            *v16 = v15;
          else
            v16[2] = v15;
        }
        *v15 = (__int64)v12;
        v12[1] = (__int64)v15;
      }
      *(_BYTE *)(*(_QWORD *)(v11 + 8) + 24LL) = 1;
      *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(v11 + 8) + 8LL) + 24LL) = 0;
      v17 = *(_QWORD **)(*(_QWORD *)(v11 + 8) + 8LL);
      v18 = (_QWORD *)*v17;
      *v17 = *(_QWORD *)(*v17 + 16LL);
      v19 = v18[2];
      if ( !*(_BYTE *)(v19 + 25) )
        *(_QWORD *)(v19 + 8) = v17;
      v18[1] = v17[1];
      if ( v17 == *(_QWORD **)(*a1 + 8LL) )
      {
        *(_QWORD *)(*a1 + 8LL) = v18;
      }
      else
      {
        v20 = (_QWORD *)v17[1];
        if ( v17 == (_QWORD *)v20[2] )
          v20[2] = v18;
        else
          *v20 = v18;
      }
      v18[2] = v17;
    }
    else
    {
      if ( !*((_BYTE *)v14 + 24) )
      {
LABEL_30:
        *((_BYTE *)v12 + 24) = 1;
        *((_BYTE *)v14 + 24) = 1;
        *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(v11 + 8) + 8LL) + 24LL) = 0;
        v11 = *(_QWORD *)(*(_QWORD *)(v11 + 8) + 8LL);
        goto LABEL_49;
      }
      v21 = *v12;
      if ( v11 == *v12 )
      {
        v11 = *(_QWORD *)(v11 + 8);
        *v12 = *(_QWORD *)(v21 + 16);
        v22 = *(_QWORD *)(v21 + 16);
        if ( !*(_BYTE *)(v22 + 25) )
          *(_QWORD *)(v22 + 8) = v12;
        *(_QWORD *)(v21 + 8) = v12[1];
        if ( v12 == *(__int64 **)(*a1 + 8LL) )
        {
          *(_QWORD *)(*a1 + 8LL) = v21;
        }
        else
        {
          v23 = (_QWORD *)v12[1];
          if ( v12 == (__int64 *)v23[2] )
            v23[2] = v21;
          else
            *v23 = v21;
        }
        *(_QWORD *)(v21 + 16) = v12;
        v12[1] = v21;
      }
      *(_BYTE *)(*(_QWORD *)(v11 + 8) + 24LL) = 1;
      *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(v11 + 8) + 8LL) + 24LL) = 0;
      v17 = *(_QWORD **)(*(_QWORD *)(v11 + 8) + 8LL);
      v18 = (_QWORD *)v17[2];
      v17[2] = *v18;
      if ( !*(_BYTE *)(*v18 + 25LL) )
        *(_QWORD *)(*v18 + 8LL) = v17;
      v18[1] = v17[1];
      if ( v17 == *(_QWORD **)(*a1 + 8LL) )
      {
        *(_QWORD *)(*a1 + 8LL) = v18;
      }
      else
      {
        v24 = (_QWORD *)v17[1];
        if ( v17 == (_QWORD *)*v24 )
          *v24 = v18;
        else
          v24[2] = v18;
      }
      *v18 = v17;
    }
    v17[1] = v18;
LABEL_49:
    v10 = *(_QWORD *)(v11 + 8);
  }
  v25 = *a1;
  *a2 = a6;
  v26 = *(_QWORD *)(v25 + 8);
  result = a2;
  *(_BYTE *)(v26 + 24) = 1;
  return result;
}

```

## disassembly

```asm
0x1800133c4  mov     [rsp+arg_0], rbx
0x1800133c9  push    rdi
0x1800133ca  sub     rsp, 20h
0x1800133ce  mov     rax, [rcx+8]
0x1800133d2  mov     r11, rcx
0x1800133d5  mov     rcx, 555555555555554h
0x1800133df  mov     r10, r9
0x1800133e2  mov     rbx, rdx
0x1800133e5  cmp     rax, rcx
0x1800133e8  jnb     loc_18001362A
0x1800133ee  mov     r9, [rsp+28h+arg_28]
0x1800133f3  inc     rax
0x1800133f6  mov     [r11+8], rax
0x1800133fa  xor     edi, edi
0x1800133fc  mov     [r9+8], r10
0x180013400  mov     rax, [r11]
0x180013403  cmp     r10, rax
0x180013406  jnz     short loc_180013417
0x180013408  mov     [rax+8], r9
0x18001340c  mov     rax, [r11]
0x18001340f  mov     [rax], r9
0x180013412  mov     rax, [r11]
0x180013415  jmp     short loc_180013439
0x180013417  test    r8b, r8b
0x18001341a  jz      short loc_18001342C
0x18001341c  mov     [r10], r9
0x18001341f  mov     rax, [r11]
0x180013422  cmp     r10, [rax]
0x180013425  jnz     short loc_18001343D
0x180013427  mov     [rax], r9
0x18001342a  jmp     short loc_18001343D
0x18001342c  mov     [r10+10h], r9
0x180013430  mov     rax, [r11]
0x180013433  cmp     r10, [rax+10h]
0x180013437  jnz     short loc_18001343D
0x180013439  mov     [rax+10h], r9
0x18001343d  mov     rax, [r9+8]
0x180013441  mov     rdx, r9
0x180013444  jmp     loc_180013603
0x180013449  mov     rcx, [rdx+8]
0x18001344d  mov     r8, [rcx+8]
0x180013451  mov     rax, [r8]
0x180013454  cmp     rcx, rax
0x180013457  jnz     loc_180013522
0x18001345d  mov     rax, [r8+10h]
0x180013461  cmp     [rax+18h], dil
0x180013465  jz      loc_180013528
0x18001346b  mov     r8, [rcx+10h]
0x18001346f  cmp     rdx, r8
0x180013472  jnz     short loc_1800134BB
0x180013474  mov     rax, [r8]
0x180013477  mov     rdx, rcx
0x18001347a  mov     [rcx+10h], rax
0x18001347e  mov     rax, [r8]
0x180013481  cmp     [rax+19h], dil
0x180013485  jnz     short loc_18001348B
0x180013487  mov     [rax+8], rcx
0x18001348b  mov     rax, [rcx+8]
0x18001348f  mov     [r8+8], rax
0x180013493  mov     rax, [r11]
0x180013496  cmp     rcx, [rax+8]
0x18001349a  jnz     short loc_1800134A2
0x18001349c  mov     [rax+8], r8
0x1800134a0  jmp     short loc_1800134B4
0x1800134a2  mov     rax, [rcx+8]
0x1800134a6  cmp     rcx, [rax]
0x1800134a9  jnz     short loc_1800134B0
0x1800134ab  mov     [rax], r8
0x1800134ae  jmp     short loc_1800134B4
0x1800134b0  mov     [rax+10h], r8
0x1800134b4  mov     [r8], rcx
0x1800134b7  mov     [rcx+8], r8
0x1800134bb  mov     rax, [rdx+8]
0x1800134bf  mov     byte ptr [rax+18h], 1
0x1800134c3  mov     rax, [rdx+8]
0x1800134c7  mov     rcx, [rax+8]
0x1800134cb  mov     [rcx+18h], dil
0x1800134cf  mov     rax, [rdx+8]
0x1800134d3  mov     rcx, [rax+8]
0x1800134d7  mov     r8, [rcx]
0x1800134da  mov     rax, [r8+10h]
0x1800134de  mov     [rcx], rax
0x1800134e1  mov     rax, [r8+10h]
0x1800134e5  cmp     [rax+19h], dil
0x1800134e9  jnz     short loc_1800134EF
0x1800134eb  mov     [rax+8], rcx
0x1800134ef  mov     rax, [rcx+8]
0x1800134f3  mov     [r8+8], rax
0x1800134f7  mov     rax, [r11]
0x1800134fa  cmp     rcx, [rax+8]
0x1800134fe  jnz     short loc_180013506
0x180013500  mov     [rax+8], r8
0x180013504  jmp     short loc_180013519
0x180013506  mov     rax, [rcx+8]
0x18001350a  cmp     rcx, [rax+10h]
0x18001350e  jnz     short loc_180013516
0x180013510  mov     [rax+10h], r8
0x180013514  jmp     short loc_180013519
0x180013516  mov     [rax], r8
0x180013519  mov     [r8+10h], rcx
0x18001351d  jmp     loc_1800135FB
0x180013522  cmp     [rax+18h], dil
0x180013526  jnz     short loc_180013549
0x180013528  mov     byte ptr [rcx+18h], 1
0x18001352c  mov     byte ptr [rax+18h], 1
0x180013530  mov     rax, [rdx+8]
0x180013534  mov     rcx, [rax+8]
0x180013538  mov     [rcx+18h], dil
0x18001353c  mov     rax, [rdx+8]
0x180013540  mov     rdx, [rax+8]
0x180013544  jmp     loc_1800135FF
0x180013549  mov     r8, [rcx]
0x18001354c  cmp     rdx, r8
0x18001354f  jnz     short loc_18001359B
0x180013551  mov     rax, [r8+10h]
0x180013555  mov     rdx, rcx
0x180013558  mov     [rcx], rax
0x18001355b  mov     rax, [r8+10h]
0x18001355f  cmp     [rax+19h], dil
0x180013563  jnz     short loc_180013569
0x180013565  mov     [rax+8], rcx
0x180013569  mov     rax, [rcx+8]
0x18001356d  mov     [r8+8], rax
0x180013571  mov     rax, [r11]
0x180013574  cmp     rcx, [rax+8]
0x180013578  jnz     short loc_180013580
0x18001357a  mov     [rax+8], r8
0x18001357e  jmp     short loc_180013593
0x180013580  mov     rax, [rcx+8]
0x180013584  cmp     rcx, [rax+10h]
0x180013588  jnz     short loc_180013590
0x18001358a  mov     [rax+10h], r8
0x18001358e  jmp     short loc_180013593
0x180013590  mov     [rax], r8
0x180013593  mov     [r8+10h], rcx
0x180013597  mov     [rcx+8], r8
0x18001359b  mov     rax, [rdx+8]
0x18001359f  mov     byte ptr [rax+18h], 1
0x1800135a3  mov     rax, [rdx+8]
0x1800135a7  mov     rcx, [rax+8]
0x1800135ab  mov     [rcx+18h], dil
0x1800135af  mov     rax, [rdx+8]
0x1800135b3  mov     rcx, [rax+8]
0x1800135b7  mov     r8, [rcx+10h]
0x1800135bb  mov     rax, [r8]
0x1800135be  mov     [rcx+10h], rax
0x1800135c2  mov     rax, [r8]
0x1800135c5  cmp     [rax+19h], dil
0x1800135c9  jnz     short loc_1800135CF
0x1800135cb  mov     [rax+8], rcx
0x1800135cf  mov     rax, [rcx+8]
0x1800135d3  mov     [r8+8], rax
0x1800135d7  mov     rax, [r11]
0x1800135da  cmp     rcx, [rax+8]
0x1800135de  jnz     short loc_1800135E6
0x1800135e0  mov     [rax+8], r8
0x1800135e4  jmp     short loc_1800135F8
0x1800135e6  mov     rax, [rcx+8]
0x1800135ea  cmp     rcx, [rax]
0x1800135ed  jnz     short loc_1800135F4
0x1800135ef  mov     [rax], r8
0x1800135f2  jmp     short loc_1800135F8
0x1800135f4  mov     [rax+10h], r8
0x1800135f8  mov     [r8], rcx
0x1800135fb  mov     [rcx+8], r8
0x1800135ff  mov     rax, [rdx+8]
0x180013603  cmp     [rax+18h], dil
0x180013607  jz      loc_180013449
0x18001360d  mov     rax, [r11]
0x180013610  mov     [rbx], r9
0x180013613  mov     rcx, [rax+8]
0x180013617  mov     rax, rbx
0x18001361a  mov     rbx, [rsp+28h+arg_0]
0x18001361f  mov     byte ptr [rcx+18h], 1
0x180013623  add     rsp, 20h
0x180013627  pop     rdi
0x180013628  retn
0x18001362a  mov     rdx, [rsp+28h+arg_28]
0x18001362f  call    ?_Freenode0@?$_Tree_buy@PEBGV?$allocator@PEBG@std@@@std@@QEAAXPEAU?$_Tree_node@PEBGPEAX@2@@Z; std::_Tree_buy<ushort const *>::_Freenode0(std::_Tree_node<ushort const *,void *> *)
0x180013634  lea     rcx, aMapSetTTooLong; "map/set<T> too long"
0x18001363b  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
