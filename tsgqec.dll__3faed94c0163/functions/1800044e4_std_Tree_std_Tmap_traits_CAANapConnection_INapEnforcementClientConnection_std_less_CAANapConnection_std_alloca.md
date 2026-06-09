# std::_Tree<std::_Tmap_traits<CAANapConnection *,INapEnforcementClientConnection *,std::less<CAANapConnection *>,std::allocator<std::pair<CAANapConnection * const,INapEnforcementClientConnection *>>,0>>::erase(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<CAANapConnection * const,INapEnforcementClientConnection *>>>>)

- ea: `0x1800044e4`
- end: `0x180004967`
- name: `?erase@?$_Tree@V?$_Tmap_traits@PEAVCAANapConnection@@PEAUINapEnforcementClientConnection@@U?$less@PEAVCAANapConnection@@@std@@V?$allocator@U?$pair@QEAVCAANapConnection@@PEAUINapEnforcementClientConnection@@@std@@@4@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAVCAANapConnection@@PEAUINapEnforcementClientConnection@@@std@@@std@@@std@@@2@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAVCAANapConnection@@PEAUINapEnforcementClientConnection@@@std@@@std@@@std@@@2@@Z`
- size: `1155`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180003b60`

## callees

- `0x1800016e4`
- `0x1800044e4`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180004933`
- `msvcrt!??3@YAXPEAX@Z` at `0x180004933`

## pseudocode

```c
__int64 **__fastcall std::_Tree<std::_Tmap_traits<CAANapConnection *,INapEnforcementClientConnection *,std::less<CAANapConnection *>,std::allocator<std::pair<CAANapConnection * const,INapEnforcementClientConnection *>>,0>>::erase(
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
0x1800044e4  push    rbx
0x1800044e6  push    rbp
0x1800044e7  push    rsi
0x1800044e8  push    rdi
0x1800044e9  push    r14
0x1800044eb  sub     rsp, 20h
0x1800044ef  xor     ebp, ebp
0x1800044f1  mov     r14, rdx
0x1800044f4  mov     rdi, rcx
0x1800044f7  cmp     [r8+19h], bpl
0x1800044fb  jnz     loc_18000495A
0x180004501  lea     r10, [r8+10h]
0x180004505  mov     rsi, r8
0x180004508  mov     r9, [r10]
0x18000450b  mov     r11, r8
0x18000450e  mov     dl, [r9+19h]
0x180004512  test    dl, dl
0x180004514  jnz     short loc_180004539
0x180004516  mov     rcx, [r9]
0x180004519  cmp     [rcx+19h], bpl
0x18000451d  jnz     short loc_180004530
0x18000451f  mov     rax, [rcx]
0x180004522  mov     rbx, rcx
0x180004525  mov     rcx, rax
0x180004528  cmp     [rax+19h], bpl
0x18000452c  jz      short loc_18000451F
0x18000452e  jmp     short loc_180004533
0x180004530  mov     rbx, r9
0x180004533  lea     rcx, [r8+8]
0x180004537  jmp     short loc_180004555
0x180004539  lea     rcx, [r8+8]
0x18000453d  mov     rbx, [rcx]
0x180004540  jmp     short loc_18000454F
0x180004542  cmp     r8, [rbx+10h]
0x180004546  jnz     short loc_180004555
0x180004548  mov     r8, rbx
0x18000454b  mov     rbx, [rbx+8]
0x18000454f  cmp     [rbx+19h], bpl
0x180004553  jz      short loc_180004542
0x180004555  mov     rax, [rsi]
0x180004558  cmp     [rax+19h], bpl
0x18000455c  jnz     short loc_180004574
0x18000455e  test    dl, dl
0x180004560  jz      short loc_180004567
0x180004562  mov     r9, rax
0x180004565  jmp     short loc_180004574
0x180004567  mov     r9, [rbx+10h]
0x18000456b  cmp     rbx, rsi
0x18000456e  jnz     loc_180004606
0x180004574  mov     rdx, [rcx]
0x180004577  cmp     [r9+19h], bpl
0x18000457b  jnz     short loc_180004581
0x18000457d  mov     [r9+8], rdx
0x180004581  mov     rax, [rdi]
0x180004584  cmp     [rax+8], rsi
0x180004588  jnz     short loc_180004590
0x18000458a  mov     [rax+8], r9
0x18000458e  jmp     short loc_18000459E
0x180004590  cmp     [rdx], rsi
0x180004593  jnz     short loc_18000459A
0x180004595  mov     [rdx], r9
0x180004598  jmp     short loc_18000459E
0x18000459a  mov     [rdx+10h], r9
0x18000459e  mov     r10, [rdi]
0x1800045a1  cmp     [r10], rsi
0x1800045a4  jnz     short loc_1800045D1
0x1800045a6  cmp     [r9+19h], bpl
0x1800045aa  jz      short loc_1800045B1
0x1800045ac  mov     r8, rdx
0x1800045af  jmp     short loc_1800045CE
0x1800045b1  mov     rcx, [r9]
0x1800045b4  cmp     [rcx+19h], bpl
0x1800045b8  jnz     short loc_1800045CB
0x1800045ba  mov     rax, [rcx]
0x1800045bd  mov     r8, rcx
0x1800045c0  mov     rcx, rax
0x1800045c3  cmp     [rax+19h], bpl
0x1800045c7  jz      short loc_1800045BA
0x1800045c9  jmp     short loc_1800045CE
0x1800045cb  mov     r8, r9
0x1800045ce  mov     [r10], r8
0x1800045d1  mov     r8, [rdi]
0x1800045d4  cmp     [r8+10h], rsi
0x1800045d8  jnz     short loc_180004600
0x1800045da  cmp     [r9+19h], bpl
0x1800045de  jz      short loc_1800045E5
0x1800045e0  mov     rcx, rdx
0x1800045e3  jmp     short loc_1800045FC
0x1800045e5  mov     rax, [r9+10h]
0x1800045e9  mov     rcx, r9
0x1800045ec  jmp     short loc_1800045F6
0x1800045ee  mov     rcx, [rcx+10h]
0x1800045f2  mov     rax, [rcx+10h]
0x1800045f6  cmp     [rax+19h], bpl
0x1800045fa  jz      short loc_1800045EE
0x1800045fc  mov     [r8+10h], rcx
0x180004600  lea     r8, [r11+18h]
0x180004604  jmp     short loc_180004670
0x180004606  mov     [rax+8], rbx
0x18000460a  mov     rax, [rsi]
0x18000460d  mov     [rbx], rax
0x180004610  cmp     rbx, [r10]
0x180004613  jnz     short loc_18000461A
0x180004615  mov     rdx, rbx
0x180004618  jmp     short loc_180004639
0x18000461a  mov     rdx, [rbx+8]
0x18000461e  cmp     [r9+19h], bpl
0x180004622  jnz     short loc_180004628
0x180004624  mov     [r9+8], rdx
0x180004628  mov     [rdx], r9
0x18000462b  mov     rax, [r10]
0x18000462e  mov     [rbx+10h], rax
0x180004632  mov     rax, [r10]
0x180004635  mov     [rax+8], rbx
0x180004639  mov     rax, [rdi]
0x18000463c  cmp     [rax+8], rsi
0x180004640  jnz     short loc_180004648
0x180004642  mov     [rax+8], rbx
0x180004646  jmp     short loc_180004659
0x180004648  mov     rax, [rcx]
0x18000464b  cmp     [rax], rsi
0x18000464e  jnz     short loc_180004655
0x180004650  mov     [rax], rbx
0x180004653  jmp     short loc_180004659
0x180004655  mov     [rax+10h], rbx
0x180004659  mov     rax, [rcx]
0x18000465c  lea     r8, [rsi+18h]
0x180004660  mov     cl, [rbx+18h]
0x180004663  mov     [rbx+8], rax
0x180004667  mov     al, [r8]
0x18000466a  mov     [rbx+18h], al
0x18000466d  mov     [r8], cl
0x180004670  mov     r11b, 1
0x180004673  cmp     [r8], r11b
0x180004676  jnz     loc_180004930
0x18000467c  jmp     loc_1800047E9
0x180004681  cmp     [r9+18h], r11b
0x180004685  jnz     loc_18000492C
0x18000468b  mov     rcx, [rdx]
0x18000468e  cmp     r9, rcx
0x180004691  jnz     loc_180004762
0x180004697  mov     rcx, [rdx+10h]
0x18000469b  cmp     [rcx+18h], bpl
0x18000469f  jnz     short loc_1800046F5
0x1800046a1  mov     [rcx+18h], r11b
0x1800046a5  mov     rcx, [rdx+10h]
0x1800046a9  mov     [rdx+18h], bpl
0x1800046ad  mov     rax, [rcx]
0x1800046b0  mov     [rdx+10h], rax
0x1800046b4  mov     rax, [rcx]
0x1800046b7  cmp     [rax+19h], bpl
0x1800046bb  jnz     short loc_1800046C1
0x1800046bd  mov     [rax+8], rdx
0x1800046c1  mov     rax, [rdx+8]
0x1800046c5  mov     [rcx+8], rax
0x1800046c9  mov     rax, [rdi]
0x1800046cc  cmp     rdx, [rax+8]
0x1800046d0  jnz     short loc_1800046D8
0x1800046d2  mov     [rax+8], rcx
0x1800046d6  jmp     short loc_1800046EA
0x1800046d8  mov     rax, [rdx+8]
0x1800046dc  cmp     rdx, [rax]
0x1800046df  jnz     short loc_1800046E6
0x1800046e1  mov     [rax], rcx
0x1800046e4  jmp     short loc_1800046EA
0x1800046e6  mov     [rax+10h], rcx
0x1800046ea  mov     [rcx], rdx
0x1800046ed  mov     [rdx+8], rcx
0x1800046f1  mov     rcx, [rdx+10h]
0x1800046f5  cmp     [rcx+19h], bpl
0x1800046f9  jnz     loc_1800047E2
0x1800046ff  mov     r10, [rcx]
0x180004702  cmp     [r10+18h], r11b
0x180004706  jnz     short loc_180004716
0x180004708  mov     rax, [rcx+10h]
0x18000470c  cmp     [rax+18h], r11b
0x180004710  jz      loc_1800047DE
0x180004716  mov     rax, [rcx+10h]
0x18000471a  cmp     [rax+18h], r11b
0x18000471e  jnz     loc_18000481A
0x180004724  mov     [r10+18h], r11b
0x180004728  mov     r8, [rcx]
0x18000472b  mov     [rcx+18h], bpl
0x18000472f  mov     rax, [r8+10h]
0x180004733  mov     [rcx], rax
0x180004736  mov     rax, [r8+10h]
0x18000473a  cmp     [rax+19h], bpl
0x18000473e  jnz     short loc_180004744
0x180004740  mov     [rax+8], rcx
0x180004744  mov     rax, [rcx+8]
0x180004748  mov     [r8+8], rax
0x18000474c  mov     rax, [rdi]
0x18000474f  cmp     rcx, [rax+8]
0x180004753  jnz     loc_1800047FB
0x180004759  mov     [rax+8], r8
0x18000475d  jmp     loc_18000480E
0x180004762  cmp     [rcx+18h], bpl
0x180004766  jnz     short loc_1800047BD
0x180004768  mov     [rcx+18h], r11b
0x18000476c  mov     rcx, [rdx]
0x18000476f  mov     [rdx+18h], bpl
0x180004773  mov     rax, [rcx+10h]
0x180004777  mov     [rdx], rax
0x18000477a  mov     rax, [rcx+10h]
0x18000477e  cmp     [rax+19h], bpl
0x180004782  jnz     short loc_180004788
0x180004784  mov     [rax+8], rdx
0x180004788  mov     rax, [rdx+8]
0x18000478c  mov     [rcx+8], rax
0x180004790  mov     rax, [rdi]
0x180004793  cmp     rdx, [rax+8]
0x180004797  jnz     short loc_18000479F
0x180004799  mov     [rax+8], rcx
0x18000479d  jmp     short loc_1800047B2
0x18000479f  mov     rax, [rdx+8]
0x1800047a3  cmp     rdx, [rax+10h]
0x1800047a7  jnz     short loc_1800047AF
0x1800047a9  mov     [rax+10h], rcx
0x1800047ad  jmp     short loc_1800047B2
0x1800047af  mov     [rax], rcx
0x1800047b2  mov     [rcx+10h], rdx
0x1800047b6  mov     [rdx+8], rcx
0x1800047ba  mov     rcx, [rdx]
0x1800047bd  cmp     [rcx+19h], bpl
0x1800047c1  jnz     short loc_1800047E2
0x1800047c3  mov     r8, [rcx+10h]
0x1800047c7  cmp     [r8+18h], r11b
0x1800047cb  jnz     loc_180004875
0x1800047d1  mov     rax, [rcx]
0x1800047d4  cmp     [rax+18h], r11b
0x1800047d8  jnz     loc_180004875
0x1800047de  mov     [rcx+18h], bpl
0x1800047e2  mov     r9, rdx
0x1800047e5  mov     rdx, [rdx+8]
0x1800047e9  mov     rax, [rdi]
0x1800047ec  cmp     r9, [rax+8]
0x1800047f0  jnz     loc_180004681
0x1800047f6  jmp     loc_18000492C
0x1800047fb  mov     rax, [rcx+8]
0x1800047ff  cmp     rcx, [rax+10h]
0x180004803  jnz     short loc_18000480B
0x180004805  mov     [rax+10h], r8
0x180004809  jmp     short loc_18000480E
0x18000480b  mov     [rax], r8
0x18000480e  mov     [r8+10h], rcx
0x180004812  mov     [rcx+8], r8
0x180004816  mov     rcx, [rdx+10h]
0x18000481a  mov     al, [rdx+18h]
0x18000481d  mov     [rcx+18h], al
0x180004820  mov     [rdx+18h], r11b
0x180004824  mov     rax, [rcx+10h]
0x180004828  mov     [rax+18h], r11b
0x18000482c  mov     rcx, [rdx+10h]
0x180004830  mov     rax, [rcx]
0x180004833  mov     [rdx+10h], rax
0x180004837  mov     rax, [rcx]
0x18000483a  cmp     [rax+19h], bpl
0x18000483e  jnz     short loc_180004844
0x180004840  mov     [rax+8], rdx
0x180004844  mov     rax, [rdx+8]
0x180004848  mov     [rcx+8], rax
0x18000484c  mov     rax, [rdi]
0x18000484f  cmp     rdx, [rax+8]
0x180004853  jnz     short loc_18000485B
0x180004855  mov     [rax+8], rcx
0x180004859  jmp     short loc_18000486D
0x18000485b  mov     rax, [rdx+8]
0x18000485f  cmp     rdx, [rax]
0x180004862  jnz     short loc_180004869
0x180004864  mov     [rax], rcx
0x180004867  jmp     short loc_18000486D
0x180004869  mov     [rax+10h], rcx
0x18000486d  mov     [rcx], rdx
0x180004870  jmp     loc_180004928
0x180004875  mov     rax, [rcx]
0x180004878  cmp     [rax+18h], r11b
0x18000487c  jnz     short loc_1800048D1
0x18000487e  mov     [r8+18h], r11b
0x180004882  mov     r8, [rcx+10h]
0x180004886  mov     [rcx+18h], bpl
0x18000488a  mov     rax, [r8]
0x18000488d  mov     [rcx+10h], rax
0x180004891  mov     rax, [r8]
0x180004894  cmp     [rax+19h], bpl
0x180004898  jnz     short loc_18000489E
0x18000489a  mov     [rax+8], rcx
0x18000489e  mov     rax, [rcx+8]
0x1800048a2  mov     [r8+8], rax
0x1800048a6  mov     rax, [rdi]
0x1800048a9  cmp     rcx, [rax+8]
0x1800048ad  jnz     short loc_1800048B5
0x1800048af  mov     [rax+8], r8
0x1800048b3  jmp     short loc_1800048C7
0x1800048b5  mov     rax, [rcx+8]
0x1800048b9  cmp     rcx, [rax]
0x1800048bc  jnz     short loc_1800048C3
0x1800048be  mov     [rax], r8
0x1800048c1  jmp     short loc_1800048C7
0x1800048c3  mov     [rax+10h], r8
0x1800048c7  mov     [r8], rcx
  ... truncated ...
```
