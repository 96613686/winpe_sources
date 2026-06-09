# PipeTryReadSingle

- ea: `0x140001560`
- end: `0x14000181e`
- name: `PipeTryReadSingle`
- size: `702`
- prototype: `__int64 __fastcall(__int64, __int64, char, _DWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1400026f0`

## callees

- `0x140001560`
- `0x140002560`
- `0x1400155c8`
- `0x1400164d8`

## pseudocode

```c
__int64 __fastcall PipeTryReadSingle(__int64 a1, __int64 a2, char a3, _DWORD *a4)
{
  __int64 v4; // r10
  int v6; // edx
  __int64 v7; // rsi
  unsigned int v8; // ebx
  unsigned int v9; // r11d
  int v13; // edx
  unsigned int v14; // r8d
  int v15; // edx
  unsigned int v16; // edx
  __int64 v17; // rbx
  unsigned int v18; // ecx
  unsigned int v19; // eax
  unsigned int v20; // edx
  __int64 v21; // r9
  unsigned int v22; // ecx
  unsigned int v23; // eax
  unsigned int v24; // ecx
  __int64 v26; // r11
  unsigned __int64 *v27; // rsi
  unsigned int v28; // r8d
  unsigned __int64 v29; // rcx
  unsigned __int64 v30; // rdx
  unsigned int v31; // ebx
  int v32; // r9d
  signed __int32 v33[8]; // [rsp+0h] [rbp-78h] BYREF
  __int128 v34; // [rsp+30h] [rbp-48h]

  v4 = (unsigned int)*a4;
  v6 = *(_DWORD *)(a1 + 128);
  v7 = 0;
  v8 = *(_DWORD *)(a1 + 104);
  v9 = 0;
  v34 = 0;
  if ( v6 == (_DWORD)v4 )
  {
    if ( !(unsigned __int8)PkpValidatePointer(v8, **(unsigned int **)(a1 + 88)) )
      goto LABEL_22;
    *(_DWORD *)(a1 + 128) = v6;
    if ( v6 == (_DWORD)v4 )
    {
      *(_DWORD *)(*(_QWORD *)(a1 + 88) + 8LL) = 0;
      _InterlockedOr(v33, 0);
      v13 = *(_DWORD *)(a1 + 128);
      v14 = *(_DWORD *)(a1 + 104);
      if ( v13 == (_DWORD)v4 )
      {
        if ( !(unsigned __int8)PkpValidatePointer(v14, **(unsigned int **)(a1 + 88)) )
          goto LABEL_22;
        *(_DWORD *)(a1 + 128) = v13;
        if ( v13 == (_DWORD)v4 )
        {
          v15 = -1073741807;
          goto LABEL_23;
        }
      }
      v16 = v13 - v4;
      if ( v16 >= v14 )
        v16 += v14;
      v17 = v4 + *(_QWORD *)(a1 + 96);
      v18 = 8 * *(unsigned __int16 *)(v17 + 4);
      if ( v18 >= 0x10 && v18 + 8 <= v16 )
      {
        v19 = v4 + v18 + 8;
        v7 = v4 + *(_QWORD *)(a1 + 96);
        LODWORD(v4) = v19 - v14;
        if ( v19 < v14 )
          LODWORD(v4) = v19;
        WORD1(v34) = HIWORD(*(_DWORD *)v17);
        v15 = 0;
        v9 = v18;
        goto LABEL_23;
      }
LABEL_22:
      v15 = -1073741566;
      goto LABEL_23;
    }
  }
  v20 = v6 - v4;
  if ( v20 >= v8 )
    v20 += v8;
  v21 = v4 + *(_QWORD *)(a1 + 96);
  v22 = 8 * *(unsigned __int16 *)(v21 + 4);
  if ( v22 < 0x10 || v22 + 8 > v20 )
    goto LABEL_22;
  v23 = v4 + v22 + 8;
  v7 = v4 + *(_QWORD *)(a1 + 96);
  v9 = 8 * *(unsigned __int16 *)(v21 + 4);
  LODWORD(v4) = v23 - v8;
  if ( v23 < v8 )
    LODWORD(v4) = v23;
  WORD1(v34) = HIWORD(*(_DWORD *)v21);
  v15 = 0;
LABEL_23:
  if ( v15 < 0 )
    return (unsigned int)v15;
  v24 = 8 * WORD1(v34);
  if ( v24 > v9 )
    return 3221225730LL;
  v26 = v9 - v24;
  v27 = (unsigned __int64 *)(v24 + v7);
  v28 = *(_DWORD *)(*(_QWORD *)(a2 + 184) + 8LL) - *(_DWORD *)(a2 + 56);
  if ( !*(_BYTE *)(a1 + 272) )
  {
    v31 = v26;
    if ( v28 >= (unsigned int)v26 )
    {
      *a4 = v4;
      v15 = 0;
      goto LABEL_41;
    }
    return (unsigned int)-1073741789;
  }
  if ( (unsigned int)v26 < 8 )
    return 3221225730LL;
  v29 = *v27;
  _InterlockedOr(v33, 0);
  if ( (_DWORD)v29 == 1 )
  {
    LODWORD(v30) = 0;
    v31 = HIDWORD(v29);
  }
  else
  {
    if ( (_DWORD)v29 != 2 )
      return 3221225730LL;
    v31 = WORD2(v29);
    v30 = HIWORD(v29);
  }
  v32 = v30;
  if ( v26 - 8 < (unsigned __int64)(unsigned int)v30
    || (unsigned int)v26 - (unsigned __int64)(unsigned int)v30 - 8 < v31
    || v31 > 0x4000 )
  {
    return 3221225730LL;
  }
  if ( v28 < v31 )
  {
    if ( a3 )
    {
      *(_DWORD *)v27 = 2;
      *((_WORD *)v27 + 2) = v31 - v28;
      *((_WORD *)v27 + 3) = v28 + v30;
      v31 = v28;
      v15 = -2147483643;
      LODWORD(v27) = v32 + (_DWORD)v27 + 8;
      goto LABEL_41;
    }
    return (unsigned int)-1073741789;
  }
  v15 = 0;
  *a4 = v4;
  LODWORD(v27) = v32 + (_DWORD)v27 + 8;
LABEL_41:
  if ( v31 )
  {
    v15 = PipeMapChainedMdl(*(PMDL *)(a2 + 8));
    if ( v15 >= 0 )
    {
      v15 = PipeReadWriteChainedMdl(*(_QWORD *)(a2 + 8), *(_DWORD *)(a2 + 56), (_DWORD)v27, v31, 1);
      if ( v15 >= 0 )
      {
        *(_QWORD *)(a2 + 56) += v31;
        **(_QWORD **)(a1 + 264) += v31;
        ++*(_QWORD *)(*(_QWORD *)(a1 + 264) + 16LL);
        return (unsigned int)v15;
      }
    }
  }
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x140001560  push    rbx
0x140001562  push    rbp
0x140001563  push    rsi
0x140001564  push    rdi
0x140001565  push    r14
0x140001567  push    r15
0x140001569  sub     rsp, 48h
0x14000156d  mov     r10d, [r9]
0x140001570  mov     rbp, rdx
0x140001573  mov     edx, [rcx+80h]
0x140001579  xor     esi, esi
0x14000157b  mov     ebx, [rcx+68h]
0x14000157e  xor     r11d, r11d
0x140001581  xorps   xmm0, xmm0
0x140001584  mov     r14, r9
0x140001587  movzx   r15d, r8b
0x14000158b  mov     rdi, rcx
0x14000158e  movups  [rsp+78h+var_48], xmm0
0x140001593  cmp     edx, r10d
0x140001596  jnz     loc_140001658
0x14000159c  mov     rax, [rcx+58h]
0x1400015a0  mov     ecx, ebx
0x1400015a2  mov     edx, [rax]
0x1400015a4  call    PkpValidatePointer
0x1400015a9  test    al, al
0x1400015ab  jz      loc_1400016A9
0x1400015b1  mov     [rdi+80h], edx
0x1400015b7  cmp     edx, r10d
0x1400015ba  jnz     loc_140001658
0x1400015c0  mov     rax, [rdi+58h]
0x1400015c4  mov     [rax+8], esi
0x1400015c7  lock or [rsp+78h+var_78], esi
0x1400015cb  mov     edx, [rdi+80h]
0x1400015d1  mov     r8d, [rdi+68h]
0x1400015d5  cmp     edx, r10d
0x1400015d8  jnz     short loc_140001605
0x1400015da  mov     rax, [rdi+58h]
0x1400015de  mov     ecx, r8d
0x1400015e1  mov     edx, [rax]
0x1400015e3  call    PkpValidatePointer
0x1400015e8  test    al, al
0x1400015ea  jz      loc_1400016A9
0x1400015f0  mov     [rdi+80h], edx
0x1400015f6  cmp     edx, r10d
0x1400015f9  jnz     short loc_140001605
0x1400015fb  mov     edx, 0C0000011h
0x140001600  jmp     loc_1400016AE
0x140001605  mov     rbx, [rdi+60h]
0x140001609  sub     edx, r10d
0x14000160c  cmp     edx, r8d
0x14000160f  lea     eax, [rdx+r8]
0x140001613  cmovnb  edx, eax
0x140001616  add     rbx, r10
0x140001619  movzx   eax, word ptr [rbx+4]
0x14000161d  mov     r9d, [rbx]
0x140001620  nop
0x140001621  lea     ecx, ds:0[rax*8]
0x140001628  cmp     ecx, 10h
0x14000162b  jb      short loc_1400016A9
0x14000162d  lea     eax, [rcx+8]
0x140001630  cmp     eax, edx
0x140001632  ja      short loc_1400016A9
0x140001634  add     eax, r10d
0x140001637  mov     rsi, rbx
0x14000163a  mov     r10d, eax
0x14000163d  sub     r10d, r8d
0x140001640  cmp     eax, r8d
0x140001643  cmovb   r10d, eax
0x140001647  shr     r9d, 10h
0x14000164b  mov     word ptr [rsp+78h+var_48+2], r9w
0x140001651  xor     edx, edx
0x140001653  mov     r11d, ecx
0x140001656  jmp     short loc_1400016AE
0x140001658  mov     r9, [rdi+60h]
0x14000165c  sub     edx, r10d
0x14000165f  cmp     edx, ebx
0x140001661  lea     eax, [rdx+rbx]
0x140001664  cmovnb  edx, eax
0x140001667  add     r9, r10
0x14000166a  movzx   eax, word ptr [r9+4]
0x14000166f  mov     r8d, [r9]
0x140001672  nop
0x140001673  lea     ecx, ds:0[rax*8]
0x14000167a  cmp     ecx, 10h
0x14000167d  jb      short loc_1400016A9
0x14000167f  lea     eax, [rcx+8]
0x140001682  cmp     eax, edx
0x140001684  ja      short loc_1400016A9
0x140001686  add     eax, r10d
0x140001689  mov     rsi, r9
0x14000168c  mov     r10d, eax
0x14000168f  mov     r11d, ecx
0x140001692  sub     r10d, ebx
0x140001695  cmp     eax, ebx
0x140001697  cmovb   r10d, eax
0x14000169b  shr     r8d, 10h
0x14000169f  mov     word ptr [rsp+78h+var_48+2], r8w
0x1400016a5  xor     edx, edx
0x1400016a7  jmp     short loc_1400016AE
0x1400016a9  mov     edx, 0C0000102h
0x1400016ae  test    edx, edx
0x1400016b0  js      loc_14000180E
0x1400016b6  movzx   ecx, word ptr [rsp+78h+var_48+2]
0x1400016bb  shl     ecx, 3
0x1400016be  cmp     ecx, r11d
0x1400016c1  jbe     short loc_1400016D8
0x1400016c3  mov     edx, 0C0000102h
0x1400016c8  mov     eax, edx
0x1400016ca  add     rsp, 48h
0x1400016ce  pop     r15
0x1400016d0  pop     r14
0x1400016d2  pop     rdi
0x1400016d3  pop     rsi
0x1400016d4  pop     rbp
0x1400016d5  pop     rbx
0x1400016d6  retn
0x1400016d8  mov     eax, ecx
0x1400016da  sub     r11d, ecx
0x1400016dd  add     rsi, rax
0x1400016e0  mov     rax, [rbp+0B8h]
0x1400016e7  mov     r8d, [rax+8]
0x1400016eb  sub     r8d, [rbp+38h]
0x1400016ef  cmp     byte ptr [rdi+110h], 0
0x1400016f6  jz      loc_14000179F
0x1400016fc  cmp     r11d, 8
0x140001700  jb      short loc_1400016C3
0x140001702  mov     rcx, [rsi]
0x140001705  lock or [rsp+78h+var_78], 0
0x14000170a  cmp     ecx, 1
0x14000170d  jnz     short loc_140001719
0x14000170f  xor     edx, edx
0x140001711  shr     rcx, 20h
0x140001715  mov     ebx, ecx
0x140001717  jmp     short loc_14000172F
0x140001719  cmp     ecx, 2
0x14000171c  jnz     short loc_1400016C3
0x14000171e  mov     rax, rcx
0x140001721  mov     rdx, rcx
0x140001724  shr     rax, 20h
0x140001728  movzx   ebx, ax
0x14000172b  shr     rdx, 30h
0x14000172f  mov     r9d, edx
0x140001732  lea     rax, [r11-8]
0x140001736  mov     ecx, r11d
0x140001739  cmp     rax, r9
0x14000173c  jb      short loc_1400016C3
0x14000173e  sub     rcx, r9
0x140001741  mov     eax, ebx
0x140001743  sub     rcx, 8
0x140001747  cmp     rcx, rax
0x14000174a  jb      loc_1400016C3
0x140001750  cmp     ebx, 4000h
0x140001756  ja      loc_1400016C3
0x14000175c  cmp     r8d, ebx
0x14000175f  jb      short loc_14000176F
0x140001761  xor     edx, edx
0x140001763  mov     [r14], r10d
0x140001766  add     rsi, 8
0x14000176a  add     rsi, r9
0x14000176d  jmp     short loc_1400017AC
0x14000176f  test    r15b, r15b
0x140001772  jz      loc_140001809
0x140001778  sub     bx, r8w
0x14000177c  mov     dword ptr [rsi], 2
0x140001782  add     dx, r8w
0x140001786  mov     [rsi+4], bx
0x14000178a  mov     [rsi+6], dx
0x14000178e  mov     ebx, r8d
0x140001791  add     rsi, 8
0x140001795  mov     edx, 80000005h
0x14000179a  add     rsi, r9
0x14000179d  jmp     short loc_1400017AC
0x14000179f  mov     ebx, r11d
0x1400017a2  cmp     r8d, r11d
0x1400017a5  jb      short loc_140001809
0x1400017a7  mov     [r14], r10d
0x1400017aa  xor     edx, edx
0x1400017ac  test    ebx, ebx
0x1400017ae  jz      short loc_14000180E
0x1400017b0  mov     rcx, [rbp+8]; MemoryDescriptorList
0x1400017b4  call    PipeMapChainedMdl
0x1400017b9  mov     edx, eax
0x1400017bb  test    eax, eax
0x1400017bd  js      short loc_14000180E
0x1400017bf  nop
0x1400017c0  mov     [rsp+78h+var_58], 1
0x1400017c5  mov     edx, [rbp+38h]
0x1400017c8  mov     r9d, ebx
0x1400017cb  mov     rcx, [rbp+8]
0x1400017cf  mov     r8, rsi
0x1400017d2  call    PipeReadWriteChainedMdl
0x1400017d7  mov     edx, eax
0x1400017d9  nop
0x1400017da  test    eax, eax
0x1400017dc  js      short loc_14000180E
0x1400017de  mov     ecx, ebx
0x1400017e0  add     [rbp+38h], rcx
0x1400017e4  mov     rax, [rdi+108h]
0x1400017eb  add     [rax], rcx
0x1400017ee  mov     rax, [rdi+108h]
0x1400017f5  inc     qword ptr [rax+10h]
0x1400017f9  mov     eax, edx
0x1400017fb  add     rsp, 48h
0x1400017ff  pop     r15
0x140001801  pop     r14
0x140001803  pop     rdi
0x140001804  pop     rsi
0x140001805  pop     rbp
0x140001806  pop     rbx
0x140001807  retn
0x140001809  mov     edx, 0C0000023h
0x14000180e  mov     eax, edx
0x140001810  add     rsp, 48h
0x140001814  pop     r15
0x140001816  pop     r14
0x140001818  pop     rdi
0x140001819  pop     rsi
0x14000181a  pop     rbp
0x14000181b  pop     rbx
0x14000181c  retn
```
