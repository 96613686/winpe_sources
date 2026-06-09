# std::_Tree<std::_Tmap_traits<_GUID,CWcnWfdGoPeer const *,GuidCompare,std::allocator<std::pair<_GUID const,CWcnWfdGoPeer const *>>,0>>::erase(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,CWcnWfdGoPeer const *>>>>)

- ea: `0x18000fe00`
- end: `0x180010283`
- name: `?erase@?$_Tree@V?$_Tmap_traits@U_GUID@@PEBVCWcnWfdGoPeer@@UGuidCompare@@V?$allocator@U?$pair@$$CBU_GUID@@PEBVCWcnWfdGoPeer@@@std@@@std@@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@PEBVCWcnWfdGoPeer@@@std@@@std@@@std@@@2@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@PEBVCWcnWfdGoPeer@@@std@@@std@@@std@@@2@@Z`
- size: `1155`
- prototype: `__int64 **__fastcall(_QWORD *, __int64 **, __int64 *)`
- caller_count: `6`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000dcc8`
- `0x18000eac0`
- `0x18000f258`
- `0x18000fd10`
- `0x18003a0c8`
- `0x18004e7c8`

## callees

- `0x1800015fc`
- `0x18000fe00`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001024f`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001024f`

## pseudocode

```c
__int64 **__fastcall std::_Tree<std::_Tmap_traits<_GUID,CWcnWfdGoPeer const *,GuidCompare,std::allocator<std::pair<_GUID const,CWcnWfdGoPeer const *>>,0>>::erase(
        _QWORD *a1,
        __int64 **a2,
        __int64 *a3)
{
  __int64 *v5; // r10
  __int64 *v6; // rsi
  __int64 *v7; // r9
  __int64 *v8; // r11
  char v9; // dl
  __int64 *v10; // rcx
  __int64 *i; // rbx
  __int64 ***v12; // rcx
  __int64 **v13; // rdx
  __int64 **v14; // r8
  __int64 *v15; // rcx
  __int64 **v16; // rcx
  __int64 *v17; // rax
  _BYTE *v18; // r8
  __int64 **v19; // rax
  __int64 **v20; // rax
  char v21; // cl
  __int64 *v22; // rcx
  __int64 *v23; // rcx
  __int64 ***v24; // rax
  __int64 v25; // r8
  __int64 v26; // rax
  __int64 *v27; // rcx
  __int64 v28; // rax
  __int64 *v29; // rax
  __int64 v30; // r8
  _QWORD *v31; // rax
  __int64 *v32; // rcx
  __int64 ***v33; // rax
  __int64 **v34; // r8
  __int64 **v35; // rax
  __int64 v36; // rax
  __int64 *v37; // rax
  __int64 v38; // rax

  if ( *((_BYTE *)a3 + 25) )
    std::_Xout_of_range("invalid map/set<T> iterator");
  v5 = a3 + 2;
  v6 = a3;
  v7 = (__int64 *)a3[2];
  v8 = a3;
  v9 = *((_BYTE *)v7 + 25);
  if ( v9 )
  {
    v12 = (__int64 ***)(a3 + 1);
    for ( i = (__int64 *)a3[1]; !*((_BYTE *)i + 25) && a3 == (__int64 *)i[2]; i = (__int64 *)i[1] )
      a3 = i;
  }
  else
  {
    v10 = (__int64 *)*v7;
    if ( *(_BYTE *)(*v7 + 25) )
    {
      i = (__int64 *)a3[2];
    }
    else
    {
      do
      {
        i = v10;
        v10 = (__int64 *)*v10;
      }
      while ( !*((_BYTE *)v10 + 25) );
    }
    v12 = (__int64 ***)(a3 + 1);
  }
  if ( *(_BYTE *)(*v6 + 25) )
    goto LABEL_16;
  if ( v9 )
  {
    v7 = (__int64 *)*v6;
LABEL_16:
    v13 = *v12;
    if ( !*((_BYTE *)v7 + 25) )
      v7[1] = (__int64)v13;
    if ( *(__int64 **)(*a1 + 8LL) == v6 )
    {
      *(_QWORD *)(*a1 + 8LL) = v7;
    }
    else if ( *v13 == v6 )
    {
      *v13 = v7;
    }
    else
    {
      v13[2] = v7;
    }
    if ( *(__int64 **)*a1 == v6 )
    {
      if ( *((_BYTE *)v7 + 25) )
      {
        v14 = v13;
      }
      else
      {
        v15 = (__int64 *)*v7;
        if ( *(_BYTE *)(*v7 + 25) )
        {
          v14 = (__int64 **)v7;
        }
        else
        {
          do
          {
            v14 = (__int64 **)v15;
            v15 = (__int64 *)*v15;
          }
          while ( !*((_BYTE *)v15 + 25) );
        }
      }
      *(_QWORD *)*a1 = v14;
    }
    if ( *(__int64 **)(*a1 + 16LL) == v6 )
    {
      if ( *((_BYTE *)v7 + 25) )
      {
        v16 = v13;
      }
      else
      {
        v17 = (__int64 *)v7[2];
        v16 = (__int64 **)v7;
        while ( !*((_BYTE *)v17 + 25) )
        {
          v16 = (__int64 **)v16[2];
          v17 = v16[2];
        }
      }
      *(_QWORD *)(*a1 + 16LL) = v16;
    }
    v18 = v8 + 3;
    goto LABEL_50;
  }
  v7 = (__int64 *)i[2];
  if ( i == v6 )
    goto LABEL_16;
  *(_QWORD *)(*v6 + 8) = i;
  *i = *v6;
  if ( i == (__int64 *)*v5 )
  {
    v13 = (__int64 **)i;
  }
  else
  {
    v13 = (__int64 **)i[1];
    if ( !*((_BYTE *)v7 + 25) )
      v7[1] = (__int64)v13;
    *v13 = v7;
    i[2] = *v5;
    *(_QWORD *)(*v5 + 8) = i;
  }
  if ( *(__int64 **)(*a1 + 8LL) == v6 )
  {
    *(_QWORD *)(*a1 + 8LL) = i;
  }
  else
  {
    v19 = *v12;
    if ( **v12 == v6 )
      *v19 = i;
    else
      v19[2] = i;
  }
  v20 = *v12;
  v18 = v6 + 3;
  v21 = *((_BYTE *)i + 24);
  i[1] = (__int64)v20;
  *((_BYTE *)i + 24) = *((_BYTE *)v6 + 24);
  *((_BYTE *)v6 + 24) = v21;
LABEL_50:
  if ( *v18 != 1 )
    goto LABEL_118;
  while ( v7 != *(__int64 **)(*a1 + 8LL) && *((_BYTE *)v7 + 24) == 1 )
  {
    v22 = *v13;
    if ( v7 == *v13 )
    {
      v22 = v13[2];
      if ( !*((_BYTE *)v22 + 24) )
      {
        *((_BYTE *)v22 + 24) = 1;
        v23 = v13[2];
        *((_BYTE *)v13 + 24) = 0;
        v13[2] = (__int64 *)*v23;
        if ( !*(_BYTE *)(*v23 + 25) )
          *(_QWORD *)(*v23 + 8) = v13;
        v23[1] = (__int64)v13[1];
        if ( v13 == *(__int64 ***)(*a1 + 8LL) )
        {
          *(_QWORD *)(*a1 + 8LL) = v23;
        }
        else
        {
          v24 = (__int64 ***)v13[1];
          if ( v13 == *v24 )
            *v24 = (__int64 **)v23;
          else
            v24[2] = (__int64 **)v23;
        }
        *v23 = (__int64)v13;
        v13[1] = v23;
        v22 = v13[2];
      }
      if ( !*((_BYTE *)v22 + 25) )
      {
        if ( *(_BYTE *)(*v22 + 24) != 1 || *(_BYTE *)(v22[2] + 24) != 1 )
        {
          if ( *(_BYTE *)(v22[2] + 24) == 1 )
          {
            *(_BYTE *)(*v22 + 24) = 1;
            v25 = *v22;
            *((_BYTE *)v22 + 24) = 0;
            *v22 = *(_QWORD *)(v25 + 16);
            v26 = *(_QWORD *)(v25 + 16);
            if ( !*(_BYTE *)(v26 + 25) )
              *(_QWORD *)(v26 + 8) = v22;
            *(_QWORD *)(v25 + 8) = v22[1];
            if ( v22 == *(__int64 **)(*a1 + 8LL) )
            {
              *(_QWORD *)(*a1 + 8LL) = v25;
            }
            else
            {
              v31 = (_QWORD *)v22[1];
              if ( v22 == (__int64 *)v31[2] )
                v31[2] = v25;
              else
                *v31 = v25;
            }
            *(_QWORD *)(v25 + 16) = v22;
            v22[1] = v25;
            v22 = v13[2];
          }
          *((_BYTE *)v22 + 24) = *((_BYTE *)v13 + 24);
          *((_BYTE *)v13 + 24) = 1;
          *(_BYTE *)(v22[2] + 24) = 1;
          v32 = v13[2];
          v13[2] = (__int64 *)*v32;
          if ( !*(_BYTE *)(*v32 + 25) )
            *(_QWORD *)(*v32 + 8) = v13;
          v32[1] = (__int64)v13[1];
          if ( v13 == *(__int64 ***)(*a1 + 8LL) )
          {
            *(_QWORD *)(*a1 + 8LL) = v32;
          }
          else
          {
            v33 = (__int64 ***)v13[1];
            if ( v13 == *v33 )
              *v33 = (__int64 **)v32;
            else
              v33[2] = (__int64 **)v32;
          }
          *v32 = (__int64)v13;
LABEL_116:
          v13[1] = v32;
          break;
        }
LABEL_83:
        *((_BYTE *)v22 + 24) = 0;
      }
    }
    else
    {
      if ( !*((_BYTE *)v22 + 24) )
      {
        *((_BYTE *)v22 + 24) = 1;
        v27 = *v13;
        *((_BYTE *)v13 + 24) = 0;
        *v13 = (__int64 *)v27[2];
        v28 = v27[2];
        if ( !*(_BYTE *)(v28 + 25) )
          *(_QWORD *)(v28 + 8) = v13;
        v27[1] = (__int64)v13[1];
        if ( v13 == *(__int64 ***)(*a1 + 8LL) )
        {
          *(_QWORD *)(*a1 + 8LL) = v27;
        }
        else
        {
          v29 = v13[1];
          if ( v13 == (__int64 **)v29[2] )
            v29[2] = (__int64)v27;
          else
            *v29 = (__int64)v27;
        }
        v27[2] = (__int64)v13;
        v13[1] = v27;
        v22 = *v13;
      }
      if ( !*((_BYTE *)v22 + 25) )
      {
        v30 = v22[2];
        if ( *(_BYTE *)(v30 + 24) != 1 || *(_BYTE *)(*v22 + 24) != 1 )
        {
          if ( *(_BYTE *)(*v22 + 24) == 1 )
          {
            *(_BYTE *)(v30 + 24) = 1;
            v34 = (__int64 **)v22[2];
            *((_BYTE *)v22 + 24) = 0;
            v22[2] = (__int64)*v34;
            if ( !*((_BYTE *)*v34 + 25) )
              (*v34)[1] = (__int64)v22;
            v34[1] = (__int64 *)v22[1];
            if ( v22 == *(__int64 **)(*a1 + 8LL) )
            {
              *(_QWORD *)(*a1 + 8LL) = v34;
            }
            else
            {
              v35 = (__int64 **)v22[1];
              if ( v22 == *v35 )
                *v35 = (__int64 *)v34;
              else
                v35[2] = (__int64 *)v34;
            }
            *v34 = v22;
            v22[1] = (__int64)v34;
            v22 = *v13;
          }
          *((_BYTE *)v22 + 24) = *((_BYTE *)v13 + 24);
          *((_BYTE *)v13 + 24) = 1;
          *(_BYTE *)(*v22 + 24) = 1;
          v32 = *v13;
          *v13 = (__int64 *)(*v13)[2];
          v36 = v32[2];
          if ( !*(_BYTE *)(v36 + 25) )
            *(_QWORD *)(v36 + 8) = v13;
          v32[1] = (__int64)v13[1];
          if ( v13 == *(__int64 ***)(*a1 + 8LL) )
          {
            *(_QWORD *)(*a1 + 8LL) = v32;
          }
          else
          {
            v37 = v13[1];
            if ( v13 == (__int64 **)v37[2] )
              v37[2] = (__int64)v32;
            else
              *v37 = (__int64)v32;
          }
          v32[2] = (__int64)v13;
          goto LABEL_116;
        }
        goto LABEL_83;
      }
    }
    v7 = (__int64 *)v13;
    v13 = (__int64 **)v13[1];
  }
  *((_BYTE *)v7 + 24) = 1;
LABEL_118:
  operator delete(v6);
  v38 = a1[1];
  if ( v38 )
    a1[1] = v38 - 1;
  *a2 = i;
  return a2;
}

```

## disassembly

```asm
0x18000fe00  push    rbx
0x18000fe02  push    rbp
0x18000fe03  push    rsi
0x18000fe04  push    rdi
0x18000fe05  push    r14
0x18000fe07  sub     rsp, 20h
0x18000fe0b  xor     ebp, ebp
0x18000fe0d  mov     r14, rdx
0x18000fe10  mov     rdi, rcx
0x18000fe13  cmp     [r8+19h], bpl
0x18000fe17  jnz     loc_180010276
0x18000fe1d  lea     r10, [r8+10h]
0x18000fe21  mov     rsi, r8
0x18000fe24  mov     r9, [r10]
0x18000fe27  mov     r11, r8
0x18000fe2a  mov     dl, [r9+19h]
0x18000fe2e  test    dl, dl
0x18000fe30  jnz     short loc_18000FE55
0x18000fe32  mov     rcx, [r9]
0x18000fe35  cmp     [rcx+19h], bpl
0x18000fe39  jnz     short loc_18000FE4C
0x18000fe3b  mov     rax, [rcx]
0x18000fe3e  mov     rbx, rcx
0x18000fe41  mov     rcx, rax
0x18000fe44  cmp     [rax+19h], bpl
0x18000fe48  jz      short loc_18000FE3B
0x18000fe4a  jmp     short loc_18000FE4F
0x18000fe4c  mov     rbx, r9
0x18000fe4f  lea     rcx, [r8+8]
0x18000fe53  jmp     short loc_18000FE71
0x18000fe55  lea     rcx, [r8+8]
0x18000fe59  mov     rbx, [rcx]
0x18000fe5c  jmp     short loc_18000FE6B
0x18000fe5e  cmp     r8, [rbx+10h]
0x18000fe62  jnz     short loc_18000FE71
0x18000fe64  mov     r8, rbx
0x18000fe67  mov     rbx, [rbx+8]
0x18000fe6b  cmp     [rbx+19h], bpl
0x18000fe6f  jz      short loc_18000FE5E
0x18000fe71  mov     rax, [rsi]
0x18000fe74  cmp     [rax+19h], bpl
0x18000fe78  jnz     short loc_18000FE90
0x18000fe7a  test    dl, dl
0x18000fe7c  jz      short loc_18000FE83
0x18000fe7e  mov     r9, rax
0x18000fe81  jmp     short loc_18000FE90
0x18000fe83  mov     r9, [rbx+10h]
0x18000fe87  cmp     rbx, rsi
0x18000fe8a  jnz     loc_18000FF22
0x18000fe90  mov     rdx, [rcx]
0x18000fe93  cmp     [r9+19h], bpl
0x18000fe97  jnz     short loc_18000FE9D
0x18000fe99  mov     [r9+8], rdx
0x18000fe9d  mov     rax, [rdi]
0x18000fea0  cmp     [rax+8], rsi
0x18000fea4  jnz     short loc_18000FEAC
0x18000fea6  mov     [rax+8], r9
0x18000feaa  jmp     short loc_18000FEBA
0x18000feac  cmp     [rdx], rsi
0x18000feaf  jnz     short loc_18000FEB6
0x18000feb1  mov     [rdx], r9
0x18000feb4  jmp     short loc_18000FEBA
0x18000feb6  mov     [rdx+10h], r9
0x18000feba  mov     r10, [rdi]
0x18000febd  cmp     [r10], rsi
0x18000fec0  jnz     short loc_18000FEED
0x18000fec2  cmp     [r9+19h], bpl
0x18000fec6  jz      short loc_18000FECD
0x18000fec8  mov     r8, rdx
0x18000fecb  jmp     short loc_18000FEEA
0x18000fecd  mov     rcx, [r9]
0x18000fed0  cmp     [rcx+19h], bpl
0x18000fed4  jnz     short loc_18000FEE7
0x18000fed6  mov     rax, [rcx]
0x18000fed9  mov     r8, rcx
0x18000fedc  mov     rcx, rax
0x18000fedf  cmp     [rax+19h], bpl
0x18000fee3  jz      short loc_18000FED6
0x18000fee5  jmp     short loc_18000FEEA
0x18000fee7  mov     r8, r9
0x18000feea  mov     [r10], r8
0x18000feed  mov     r8, [rdi]
0x18000fef0  cmp     [r8+10h], rsi
0x18000fef4  jnz     short loc_18000FF1C
0x18000fef6  cmp     [r9+19h], bpl
0x18000fefa  jz      short loc_18000FF01
0x18000fefc  mov     rcx, rdx
0x18000feff  jmp     short loc_18000FF18
0x18000ff01  mov     rax, [r9+10h]
0x18000ff05  mov     rcx, r9
0x18000ff08  jmp     short loc_18000FF12
0x18000ff0a  mov     rcx, [rcx+10h]
0x18000ff0e  mov     rax, [rcx+10h]
0x18000ff12  cmp     [rax+19h], bpl
0x18000ff16  jz      short loc_18000FF0A
0x18000ff18  mov     [r8+10h], rcx
0x18000ff1c  lea     r8, [r11+18h]
0x18000ff20  jmp     short loc_18000FF8C
0x18000ff22  mov     [rax+8], rbx
0x18000ff26  mov     rax, [rsi]
0x18000ff29  mov     [rbx], rax
0x18000ff2c  cmp     rbx, [r10]
0x18000ff2f  jnz     short loc_18000FF36
0x18000ff31  mov     rdx, rbx
0x18000ff34  jmp     short loc_18000FF55
0x18000ff36  mov     rdx, [rbx+8]
0x18000ff3a  cmp     [r9+19h], bpl
0x18000ff3e  jnz     short loc_18000FF44
0x18000ff40  mov     [r9+8], rdx
0x18000ff44  mov     [rdx], r9
0x18000ff47  mov     rax, [r10]
0x18000ff4a  mov     [rbx+10h], rax
0x18000ff4e  mov     rax, [r10]
0x18000ff51  mov     [rax+8], rbx
0x18000ff55  mov     rax, [rdi]
0x18000ff58  cmp     [rax+8], rsi
0x18000ff5c  jnz     short loc_18000FF64
0x18000ff5e  mov     [rax+8], rbx
0x18000ff62  jmp     short loc_18000FF75
0x18000ff64  mov     rax, [rcx]
0x18000ff67  cmp     [rax], rsi
0x18000ff6a  jnz     short loc_18000FF71
0x18000ff6c  mov     [rax], rbx
0x18000ff6f  jmp     short loc_18000FF75
0x18000ff71  mov     [rax+10h], rbx
0x18000ff75  mov     rax, [rcx]
0x18000ff78  lea     r8, [rsi+18h]
0x18000ff7c  mov     cl, [rbx+18h]
0x18000ff7f  mov     [rbx+8], rax
0x18000ff83  mov     al, [r8]
0x18000ff86  mov     [rbx+18h], al
0x18000ff89  mov     [r8], cl
0x18000ff8c  mov     r11b, 1
0x18000ff8f  cmp     [r8], r11b
0x18000ff92  jnz     loc_18001024C
0x18000ff98  jmp     loc_180010105
0x18000ff9d  cmp     [r9+18h], r11b
0x18000ffa1  jnz     loc_180010248
0x18000ffa7  mov     rcx, [rdx]
0x18000ffaa  cmp     r9, rcx
0x18000ffad  jnz     loc_18001007E
0x18000ffb3  mov     rcx, [rdx+10h]
0x18000ffb7  cmp     [rcx+18h], bpl
0x18000ffbb  jnz     short loc_180010011
0x18000ffbd  mov     [rcx+18h], r11b
0x18000ffc1  mov     rcx, [rdx+10h]
0x18000ffc5  mov     [rdx+18h], bpl
0x18000ffc9  mov     rax, [rcx]
0x18000ffcc  mov     [rdx+10h], rax
0x18000ffd0  mov     rax, [rcx]
0x18000ffd3  cmp     [rax+19h], bpl
0x18000ffd7  jnz     short loc_18000FFDD
0x18000ffd9  mov     [rax+8], rdx
0x18000ffdd  mov     rax, [rdx+8]
0x18000ffe1  mov     [rcx+8], rax
0x18000ffe5  mov     rax, [rdi]
0x18000ffe8  cmp     rdx, [rax+8]
0x18000ffec  jnz     short loc_18000FFF4
0x18000ffee  mov     [rax+8], rcx
0x18000fff2  jmp     short loc_180010006
0x18000fff4  mov     rax, [rdx+8]
0x18000fff8  cmp     rdx, [rax]
0x18000fffb  jnz     short loc_180010002
0x18000fffd  mov     [rax], rcx
0x180010000  jmp     short loc_180010006
0x180010002  mov     [rax+10h], rcx
0x180010006  mov     [rcx], rdx
0x180010009  mov     [rdx+8], rcx
0x18001000d  mov     rcx, [rdx+10h]
0x180010011  cmp     [rcx+19h], bpl
0x180010015  jnz     loc_1800100FE
0x18001001b  mov     r10, [rcx]
0x18001001e  cmp     [r10+18h], r11b
0x180010022  jnz     short loc_180010032
0x180010024  mov     rax, [rcx+10h]
0x180010028  cmp     [rax+18h], r11b
0x18001002c  jz      loc_1800100FA
0x180010032  mov     rax, [rcx+10h]
0x180010036  cmp     [rax+18h], r11b
0x18001003a  jnz     loc_180010136
0x180010040  mov     [r10+18h], r11b
0x180010044  mov     r8, [rcx]
0x180010047  mov     [rcx+18h], bpl
0x18001004b  mov     rax, [r8+10h]
0x18001004f  mov     [rcx], rax
0x180010052  mov     rax, [r8+10h]
0x180010056  cmp     [rax+19h], bpl
0x18001005a  jnz     short loc_180010060
0x18001005c  mov     [rax+8], rcx
0x180010060  mov     rax, [rcx+8]
0x180010064  mov     [r8+8], rax
0x180010068  mov     rax, [rdi]
0x18001006b  cmp     rcx, [rax+8]
0x18001006f  jnz     loc_180010117
0x180010075  mov     [rax+8], r8
0x180010079  jmp     loc_18001012A
0x18001007e  cmp     [rcx+18h], bpl
0x180010082  jnz     short loc_1800100D9
0x180010084  mov     [rcx+18h], r11b
0x180010088  mov     rcx, [rdx]
0x18001008b  mov     [rdx+18h], bpl
0x18001008f  mov     rax, [rcx+10h]
0x180010093  mov     [rdx], rax
0x180010096  mov     rax, [rcx+10h]
0x18001009a  cmp     [rax+19h], bpl
0x18001009e  jnz     short loc_1800100A4
0x1800100a0  mov     [rax+8], rdx
0x1800100a4  mov     rax, [rdx+8]
0x1800100a8  mov     [rcx+8], rax
0x1800100ac  mov     rax, [rdi]
0x1800100af  cmp     rdx, [rax+8]
0x1800100b3  jnz     short loc_1800100BB
0x1800100b5  mov     [rax+8], rcx
0x1800100b9  jmp     short loc_1800100CE
0x1800100bb  mov     rax, [rdx+8]
0x1800100bf  cmp     rdx, [rax+10h]
0x1800100c3  jnz     short loc_1800100CB
0x1800100c5  mov     [rax+10h], rcx
0x1800100c9  jmp     short loc_1800100CE
0x1800100cb  mov     [rax], rcx
0x1800100ce  mov     [rcx+10h], rdx
0x1800100d2  mov     [rdx+8], rcx
0x1800100d6  mov     rcx, [rdx]
0x1800100d9  cmp     [rcx+19h], bpl
0x1800100dd  jnz     short loc_1800100FE
0x1800100df  mov     r8, [rcx+10h]
0x1800100e3  cmp     [r8+18h], r11b
0x1800100e7  jnz     loc_180010191
0x1800100ed  mov     rax, [rcx]
0x1800100f0  cmp     [rax+18h], r11b
0x1800100f4  jnz     loc_180010191
0x1800100fa  mov     [rcx+18h], bpl
0x1800100fe  mov     r9, rdx
0x180010101  mov     rdx, [rdx+8]
0x180010105  mov     rax, [rdi]
0x180010108  cmp     r9, [rax+8]
0x18001010c  jnz     loc_18000FF9D
0x180010112  jmp     loc_180010248
0x180010117  mov     rax, [rcx+8]
0x18001011b  cmp     rcx, [rax+10h]
0x18001011f  jnz     short loc_180010127
0x180010121  mov     [rax+10h], r8
0x180010125  jmp     short loc_18001012A
0x180010127  mov     [rax], r8
0x18001012a  mov     [r8+10h], rcx
0x18001012e  mov     [rcx+8], r8
0x180010132  mov     rcx, [rdx+10h]
0x180010136  mov     al, [rdx+18h]
0x180010139  mov     [rcx+18h], al
0x18001013c  mov     [rdx+18h], r11b
0x180010140  mov     rax, [rcx+10h]
0x180010144  mov     [rax+18h], r11b
0x180010148  mov     rcx, [rdx+10h]
0x18001014c  mov     rax, [rcx]
0x18001014f  mov     [rdx+10h], rax
0x180010153  mov     rax, [rcx]
0x180010156  cmp     [rax+19h], bpl
0x18001015a  jnz     short loc_180010160
0x18001015c  mov     [rax+8], rdx
0x180010160  mov     rax, [rdx+8]
0x180010164  mov     [rcx+8], rax
0x180010168  mov     rax, [rdi]
0x18001016b  cmp     rdx, [rax+8]
0x18001016f  jnz     short loc_180010177
0x180010171  mov     [rax+8], rcx
0x180010175  jmp     short loc_180010189
0x180010177  mov     rax, [rdx+8]
0x18001017b  cmp     rdx, [rax]
0x18001017e  jnz     short loc_180010185
0x180010180  mov     [rax], rcx
0x180010183  jmp     short loc_180010189
0x180010185  mov     [rax+10h], rcx
0x180010189  mov     [rcx], rdx
0x18001018c  jmp     loc_180010244
0x180010191  mov     rax, [rcx]
0x180010194  cmp     [rax+18h], r11b
0x180010198  jnz     short loc_1800101ED
0x18001019a  mov     [r8+18h], r11b
0x18001019e  mov     r8, [rcx+10h]
0x1800101a2  mov     [rcx+18h], bpl
0x1800101a6  mov     rax, [r8]
0x1800101a9  mov     [rcx+10h], rax
0x1800101ad  mov     rax, [r8]
0x1800101b0  cmp     [rax+19h], bpl
0x1800101b4  jnz     short loc_1800101BA
0x1800101b6  mov     [rax+8], rcx
0x1800101ba  mov     rax, [rcx+8]
0x1800101be  mov     [r8+8], rax
0x1800101c2  mov     rax, [rdi]
0x1800101c5  cmp     rcx, [rax+8]
0x1800101c9  jnz     short loc_1800101D1
0x1800101cb  mov     [rax+8], r8
0x1800101cf  jmp     short loc_1800101E3
0x1800101d1  mov     rax, [rcx+8]
0x1800101d5  cmp     rcx, [rax]
0x1800101d8  jnz     short loc_1800101DF
0x1800101da  mov     [rax], r8
0x1800101dd  jmp     short loc_1800101E3
0x1800101df  mov     [rax+10h], r8
0x1800101e3  mov     [r8], rcx
  ... truncated ...
```
