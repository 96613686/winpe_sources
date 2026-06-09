# CoalesceSelectiveNaksIntoGroups

- ea: `0x14000e03c`
- end: `0x14000e807`
- name: `CoalesceSelectiveNaksIntoGroups`
- size: `1995`
- prototype: `__int64 __fastcall(__int64, unsigned __int8)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x140012efc`

## callees

- `0x140005038`
- `0x140005068`
- `0x140008388`
- `0x1400090f8`
- `0x140009f50`
- `0x14000c624`
- `0x14000ca08`
- `0x14000e03c`
- `0x14000f0a0`
- `0x1400142e8`
- `0x1400156d0`
- `0x14001c8f4`
- `0x14001d300`

## import_xrefs

- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14000e148`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14000e148`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14000e23a`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14000e23a`

## pseudocode

```c
__int64 __fastcall CoalesceSelectiveNaksIntoGroups(__int64 a1, unsigned __int8 a2)
{
  __int64 v2; // r12
  int v4; // r13d
  int v5; // ebx
  _DWORD *v6; // rax
  int v7; // r15d
  int v8; // esi
  unsigned int v9; // r14d
  __int64 v10; // rcx
  unsigned int v11; // r13d
  int v13; // ecx
  char *v14; // rbx
  char *v15; // rax
  unsigned __int16 v16; // r10
  unsigned __int8 v17; // dl
  unsigned __int8 v18; // r8
  __int64 v19; // rax
  unsigned __int8 v20; // r11
  _QWORD *v21; // rax
  __int64 v22; // r9
  _QWORD *v23; // rcx
  __int64 v24; // rcx
  unsigned __int16 v25; // ax
  unsigned __int8 v26; // al
  __int64 v27; // rax
  int v28; // eax
  int v29; // edx
  __int64 v30; // rax
  unsigned int v31; // esi
  __int64 v32; // rdx
  __int64 v33; // rax
  _DWORD *v34; // r8
  int v35; // edx
  __int64 v36; // rcx
  char *i; // rsi
  _QWORD *v38; // rax
  __int64 v39; // rdx
  _QWORD *v40; // rcx
  __int64 v41; // rcx
  unsigned __int16 v42; // ax
  unsigned __int8 v43; // al
  __int64 v44; // rax
  __int64 v45; // rdx
  __int64 v46; // rcx
  int v47; // edx
  int v48; // r8d
  int v49; // edx
  unsigned int v50; // ecx
  __int64 v51; // rcx
  __int64 v52; // rax
  __int64 v53; // r8
  int v54; // r9d
  unsigned int v55; // edx
  __int64 v56; // rcx
  __int64 v57; // r9
  int v58; // edx
  int v59; // r8d
  int v60; // eax
  size_t Size; // [rsp+40h] [rbp-38h]
  __int128 v62; // [rsp+48h] [rbp-30h] BYREF
  _OWORD v63[2]; // [rsp+58h] [rbp-20h] BYREF
  int v64; // [rsp+C0h] [rbp+48h]
  int v65; // [rsp+C0h] [rbp+48h]
  unsigned int RandomInteger; // [rsp+C8h] [rbp+50h] BYREF
  int v67; // [rsp+D0h] [rbp+58h]
  int v68; // [rsp+D8h] [rbp+60h]

  v2 = a2;
  v63[0] = 0;
  v4 = a2;
  v5 = a2 - 1;
  v62 = 0;
  AdjustReceiveBufferLists(a1);
  v6 = *(_DWORD **)(a1 + 48);
  v67 = ~v5;
  v7 = v6[16];
  v8 = ~v5 & v6[15];
  v64 = v6[14];
  RandomInteger = v8 + v2 - 1;
  v9 = CheckAndAddNakRequests(a1, (int *)&RandomInteger, 0, 1, 0);
  if ( (v9 & 0x80000000) != 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 78, WPP_9481eaf791d131fecb736b68b85870ad_Traceguids, v9);
    return v9;
  }
  v65 = v67 & v64;
  *(_DWORD *)(*(_QWORD *)(a1 + 48) + 64LL) = v7;
  Size = (unsigned int)(40 * v5 + 136);
  ExInitializeNPagedLookasideList(
    (PNPAGED_LOOKASIDE_LIST)(*(_QWORD *)(a1 + 48) + 576LL),
    0,
    0,
    0x200u,
    Size,
    0x326D6750u,
    *(unsigned __int16 *)(*(_QWORD *)(a1 + 48) + 288LL) / v4);
  v10 = *(_QWORD *)(a1 + 48);
  v11 = RandomInteger;
  if ( (int)(*(_DWORD *)(v10 + 56) - RandomInteger) <= 0 )
  {
    v13 = *(_DWORD *)(*(_QWORD *)(v10 + 24) + 56LL) & 0x10;
    v68 = v13 != 0 ? 50 : 750;
    RandomInteger = GetRandomInteger(v13 != 0 ? 2 : 50, v13 != 0 ? 20 : 100);
    v14 = 0;
    *((_QWORD *)&v63[0] + 1) = v63;
    *(_QWORD *)&v63[0] = v63;
    *((_QWORD *)&v62 + 1) = &v62;
    *(_QWORD *)&v62 = &v62;
    while ( v8 - v65 >= 0 )
    {
      v15 = (char *)ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(*(_QWORD *)(a1 + 48) + 576LL));
      v14 = v15;
      if ( !v15 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 80, WPP_9481eaf791d131fecb736b68b85870ad_Traceguids);
        v9 = -1073741670;
        goto LABEL_40;
      }
      memset(v15, 0, Size);
      *((_QWORD *)v14 + 11) = v14 + 80;
      *((_QWORD *)v14 + 10) = v14 + 80;
      *((_QWORD *)v14 + 9) = v14 + 64;
      *((_QWORD *)v14 + 8) = v14 + 64;
      v14[57] = v2;
      v14[62] = v2;
      *((_DWORD *)v14 + 4) = v8;
      v16 = *(_WORD *)(a1 + 154);
      if ( (_BYTE)v2 )
      {
        v17 = 0;
        v18 = v2;
        do
        {
          v19 = v17++;
          v14[40 * v19 + 117] = v18;
          v18 = v14[62];
        }
        while ( v17 < v18 );
      }
      v20 = 0;
      while ( (int)(v11 - v8) >= 0 )
      {
        v21 = (_QWORD *)(*(_QWORD *)(a1 + 48) + 136LL);
        if ( (_QWORD *)*v21 == v21 )
          break;
        v22 = *(_QWORD *)(*(_QWORD *)(a1 + 48) + 144LL);
        if ( *(_QWORD **)v22 != v21 )
          goto LABEL_70;
        v23 = *(_QWORD **)(v22 + 8);
        if ( *v23 != v22 )
          goto LABEL_70;
        *(_QWORD *)(*(_QWORD *)(a1 + 48) + 144LL) = v23;
        *v23 = v21;
        if ( !*(_BYTE *)(v22 + 58) )
          RemovePendingReceiverEntry((_QWORD *)v22);
        if ( *(_QWORD *)(v22 + 96) )
        {
          ++v14[58];
          v24 = 5LL * v20;
          *(_OWORD *)&v14[8 * v24 + 96] = *(_OWORD *)(v22 + 96);
          *(_OWORD *)&v14[8 * v24 + 112] = *(_OWORD *)(v22 + 112);
          *(_QWORD *)&v14[8 * v24 + 128] = *(_QWORD *)(v22 + 128);
          v14[8 * v24 + 116] = v11 - v8;
          v14[40 * (v11 - v8) + 117] = v20++;
          --*(_BYTE *)(v22 + 58);
          *(_QWORD *)(v22 + 96) = 0;
          *(_DWORD *)(v22 + 132) = 0;
          v25 = *(_WORD *)(v22 + 54);
          if ( v25 >= v16 )
            v25 = v16;
          v16 = v25;
          v26 = *(_BYTE *)(v22 + 61);
          if ( v26 && v26 < (unsigned __int8)v2 && v14[57] == (_BYTE)v2 )
            v14[57] = v26;
        }
        v27 = v62;
        if ( *(__int128 **)(v62 + 8) != &v62 )
          goto LABEL_70;
        *(_QWORD *)v22 = v62;
        *(_QWORD *)(v22 + 8) = &v62;
        --v11;
        *(_QWORD *)(v27 + 8) = v22;
        *(_QWORD *)&v62 = v22;
      }
      *((_WORD *)v14 + 27) = v16;
      RemoveRedundantNaks(a1, v14, 0);
      v28 = (unsigned __int8)v14[57];
      v29 = (unsigned __int8)v14[58];
      if ( (unsigned __int8)v29 < (unsigned __int8)v28 )
        *((_QWORD *)v14 + 3) = (char *)WPP_MAIN_CB.Dpc.SystemArgument1 + RandomInteger / (v28 - v29) / 0x14;
      v30 = *(_QWORD *)&v63[0];
      if ( *(_OWORD **)(*(_QWORD *)&v63[0] + 8LL) != v63 )
LABEL_70:
        __fastfail(3u);
      *(_QWORD *)v14 = *(_QWORD *)&v63[0];
      *((_QWORD *)v14 + 1) = v63;
      v8 -= v2;
      *(_QWORD *)(v30 + 8) = v14;
      *(_QWORD *)&v63[0] = v14;
    }
    if ( !v14 || (v34 = v14 + 16, v35 = *((_DWORD *)v14 + 4), v35 != v65) )
    {
LABEL_40:
      v31 = RandomInteger;
      goto LABEL_41;
    }
    v36 = *(_QWORD *)(a1 + 48);
    if ( *(_DWORD *)(v36 + 56) - v35 > 0 )
    {
      v14[63] = *(_BYTE *)(v36 + 56) - v35;
      *(_DWORD *)(*(_QWORD *)(a1 + 48) + 56LL) = v35;
    }
    for ( i = v14 + 63; *i; *(_QWORD *)&v62 = v39 )
    {
      v38 = (_QWORD *)(*(_QWORD *)(a1 + 48) + 120LL);
      if ( (_QWORD *)*v38 == v38 )
        break;
      v39 = *(_QWORD *)(*(_QWORD *)(a1 + 48) + 128LL);
      if ( *(_QWORD **)v39 != v38 )
        goto LABEL_70;
      v40 = *(_QWORD **)(v39 + 8);
      if ( *v40 != v39 )
        goto LABEL_70;
      *(_QWORD *)(*(_QWORD *)(a1 + 48) + 128LL) = v40;
      *v40 = v38;
      --*(_DWORD *)(*(_QWORD *)(a1 + 48) + 272LL);
      --*(_DWORD *)(*(_QWORD *)(a1 + 48) + 264LL);
      ++*(_DWORD *)(*(_QWORD *)(a1 + 48) + 268LL);
      --*i;
      v41 = 5LL * (unsigned __int8)v14[58];
      *(_OWORD *)&v14[8 * v41 + 96] = *(_OWORD *)(v39 + 96);
      *(_OWORD *)&v14[8 * v41 + 112] = *(_OWORD *)(v39 + 112);
      *(_QWORD *)&v14[8 * v41 + 128] = *(_QWORD *)(v39 + 128);
      v14[40 * (unsigned __int8)v14[58] + 116] = *i;
      v14[40 * (unsigned __int8)*i + 117] = v14[58]++;
      v42 = *(_WORD *)(v39 + 54);
      if ( v42 < *((_WORD *)v14 + 27) )
        *((_WORD *)v14 + 27) = v42;
      v43 = *(_BYTE *)(v39 + 61);
      if ( v43 && v43 < (unsigned __int8)v2 && v14[57] == (_BYTE)v2 )
        v14[57] = v43;
      --*(_BYTE *)(v39 + 58);
      *(_QWORD *)(v39 + 96) = 0;
      *(_DWORD *)(v39 + 132) = 0;
      v44 = v62;
      if ( *(__int128 **)(v62 + 8) != &v62 )
        goto LABEL_70;
      *(_QWORD *)v39 = v62;
      *(_QWORD *)(v39 + 8) = &v62;
      *(_QWORD *)(v44 + 8) = v39;
    }
    v45 = *(_QWORD *)(a1 + 48);
    if ( *(_DWORD *)(v45 + 52) - *v34 >= 0 )
      *(_DWORD *)(v45 + 52) = *v34;
    v46 = *(_QWORD *)(a1 + 48);
    v47 = *(_DWORD *)(v46 + 56);
    if ( *(_DWORD *)(v46 + 48) - v47 > 0 )
      *(_DWORD *)(v46 + 48) = v47;
    RemoveRedundantNaks(a1, v14, 0);
    v48 = (unsigned __int8)*i;
    v49 = (unsigned __int8)v14[58];
    v50 = (unsigned __int8)v14[57];
    v31 = RandomInteger;
    if ( v48 + v49 < v50 )
      *((_QWORD *)v14 + 3) = (char *)WPP_MAIN_CB.Dpc.SystemArgument1 + RandomInteger / (v50 - v48 - v49) / 0x14;
    else
      *((_QWORD *)v14 + 3) = 0;
LABEL_41:
    if ( *(_OWORD **)&v63[0] != v63 )
    {
      *(_QWORD *)(*(_QWORD *)&v63[0] + 8LL) = *(_QWORD *)(*(_QWORD *)(a1 + 48) + 144LL);
      **((_QWORD **)&v63[0] + 1) = *(_QWORD *)(a1 + 48) + 136LL;
      **(_QWORD **)(*(_QWORD *)(a1 + 48) + 144LL) = *(_QWORD *)&v63[0];
      *(_QWORD *)(*(_QWORD *)(a1 + 48) + 144LL) = *((_QWORD *)&v63[0] + 1);
    }
    while ( 1 )
    {
      v32 = v62;
      if ( (__int128 *)v62 == &v62 )
        break;
      if ( *(__int128 **)(v62 + 8) != &v62 )
        goto LABEL_70;
      v33 = *(_QWORD *)v62;
      if ( *(_QWORD *)(*(_QWORD *)v62 + 8LL) != (_QWORD)v62 )
        goto LABEL_70;
      *(_QWORD *)&v62 = *(_QWORD *)v62;
      *(_QWORD *)(v33 + 8) = &v62;
      FreeNakContext(a1, v32);
    }
    *(_WORD *)(*(_QWORD *)(a1 + 48) + 230LL) = *((unsigned __int8 *)gFECLog2 + v2);
    v51 = *(_QWORD *)(a1 + 48);
    v52 = v51 + 136;
    v53 = *(_QWORD *)(v51 + 136);
    while ( v53 != v52 )
    {
      v54 = *(unsigned __int8 *)(v53 + 58);
      v55 = *(unsigned __int8 *)(v53 + 57);
      if ( v54 + (unsigned int)*(unsigned __int8 *)(v53 + 59) < v55
        && v54 + (unsigned int)*(unsigned __int8 *)(v53 + 63) < v55 )
      {
        AppendPendingReceiverEntry(v51, v53);
      }
      v51 = *(_QWORD *)(a1 + 48);
      v53 = *(_QWORD *)v53;
      v52 = v51 + 136;
    }
    AdjustReceiveBufferLists(a1);
    v56 = *(_QWORD *)(a1 + 48);
    if ( *(_QWORD *)(v56 + 136) == v56 + 136 )
    {
      if ( *(_QWORD *)(v56 + 120) == v56 + 120 )
      {
        v57 = 0;
        goto LABEL_85;
      }
      v57 = *(_QWORD *)(v56 + 128);
    }
    else
    {
      v57 = *(_QWORD *)(v56 + 144);
      v58 = *(unsigned __int8 *)(v57 + 57);
      v59 = *(unsigned __int8 *)(v57 + 58);
      if ( (unsigned __int8)v59 < (unsigned __int8)v58 )
      {
        *(_QWORD *)(v57 + 24) = (char *)WPP_MAIN_CB.Dpc.SystemArgument1 + (v68 + v31 / (v58 - v59)) / 0x14;
        v56 = *(_QWORD *)(a1 + 48);
      }
    }
    if ( v57 )
    {
      *(_DWORD *)(v56 + 60) = *(_DWORD *)(v57 + 16);
LABEL_86:
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      {
        if ( v57 )
          v60 = *(unsigned __int8 *)(v57 + 63);
        else
          v60 = 0;
        WPP_SF_ddddd(
          WPP_GLOBAL_Control->AttachedDevice,
          81,
          *(unsigned int *)(*(_QWORD *)(a1 + 48) + 56LL),
          *(unsigned int *)(*(_QWORD *)(a1 + 48) + 52LL),
          *(_DWORD *)(*(_QWORD *)(a1 + 48) + 56LL),
          v60,
          v65,
          *(_DWORD *)(*(_QWORD *)(a1 + 48) + 60LL));
      }
      return v9;
    }
LABEL_85:
    *(_DWORD *)(v56 + 60) &= v67;
    goto LABEL_86;
  }
  *(_DWORD *)(v10 + 60) = v8;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    WPP_SF_dddd(
      WPP_GLOBAL_Control->AttachedDevice,
      79,
      WPP_9481eaf791d131fecb736b68b85870ad_Traceguids,
      *(unsigned int *)(*(_QWORD *)(a1 + 48) + 52LL),
      *(_DWORD *)(*(_QWORD *)(a1 + 48) + 56LL),
      v65,
      *(_DWORD *)(*(_QWORD *)(a1 + 48) + 60LL));
  return 0;
}

```

## disassembly

```asm
0x14000e03c  push    rbp
0x14000e03e  push    rbx
0x14000e03f  push    rsi
0x14000e040  push    rdi
0x14000e041  push    r12
0x14000e043  push    r13
0x14000e045  push    r14
0x14000e047  push    r15
0x14000e049  mov     rbp, rsp
0x14000e04c  sub     rsp, 78h
0x14000e050  movzx   r12d, dl
0x14000e054  xorps   xmm0, xmm0
0x14000e057  xorps   xmm1, xmm1
0x14000e05a  mov     rdi, rcx
0x14000e05d  movups  [rbp+var_20], xmm0
0x14000e061  mov     r13d, r12d
0x14000e064  lea     ebx, [r12-1]
0x14000e069  movups  [rbp+var_30], xmm1
0x14000e06d  call    AdjustReceiveBufferLists
0x14000e072  mov     rax, [rdi+30h]
0x14000e076  lea     rdx, [rbp+arg_8]
0x14000e07a  mov     ecx, ebx
0x14000e07c  mov     byte ptr [rsp+78h+Size], 0
0x14000e081  not     ecx
0x14000e083  mov     r9d, 1
0x14000e089  mov     [rbp+arg_10], ecx
0x14000e08c  mov     r8d, [rax+38h]
0x14000e090  mov     esi, [rax+3Ch]
0x14000e093  mov     r15d, [rax+40h]
0x14000e097  and     esi, ecx
0x14000e099  lea     eax, [r12-1]
0x14000e09e  mov     [rbp+arg_0], r8d
0x14000e0a2  add     eax, esi
0x14000e0a4  xor     r8d, r8d
0x14000e0a7  mov     rcx, rdi
0x14000e0aa  mov     [rbp+arg_8], eax
0x14000e0ad  call    CheckAndAddNakRequests
0x14000e0b2  mov     r14d, eax
0x14000e0b5  test    eax, eax
0x14000e0b7  jns     short loc_14000E0F8
0x14000e0b9  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e0c0  lea     r15, WPP_GLOBAL_Control
0x14000e0c7  cmp     rcx, r15
0x14000e0ca  jz      loc_14000E7F2
0x14000e0d0  mov     eax, [rcx+2Ch]
0x14000e0d3  test    al, 2
0x14000e0d5  jz      loc_14000E7F2
0x14000e0db  mov     rcx, [rcx+18h]
0x14000e0df  lea     r8, WPP_9481eaf791d131fecb736b68b85870ad_Traceguids
0x14000e0e6  mov     edx, 4Eh ; 'N'
0x14000e0eb  mov     r9d, r14d
0x14000e0ee  call    WPP_SF_d
0x14000e0f3  jmp     loc_14000E7F2
0x14000e0f8  mov     eax, [rbp+arg_10]
0x14000e0fb  mov     r9d, 200h; Flags
0x14000e101  and     [rbp+arg_0], eax
0x14000e104  mov     rax, [rdi+30h]
0x14000e108  mov     [rax+40h], r15d
0x14000e10c  lea     eax, [rbx+rbx*4]
0x14000e10f  mov     rcx, [rdi+30h]
0x14000e113  lea     r8d, ds:88h[rax*8]
0x14000e11b  mov     [rbp+var_38], r8
0x14000e11f  movzx   eax, word ptr [rcx+120h]
0x14000e126  add     rcx, 240h; Lookaside
0x14000e12d  cdq
0x14000e12e  idiv    r13d
0x14000e131  xor     edx, edx; Allocate
0x14000e133  mov     [rsp+78h+Depth], ax; Depth
0x14000e138  mov     [rsp+78h+Tag], 326D6750h; Tag
0x14000e140  mov     [rsp+78h+Size], r8; Size
0x14000e145  xor     r8d, r8d; Free
0x14000e148  call    cs:__imp_ExInitializeNPagedLookasideList
0x14000e14f  nop     dword ptr [rax+rax+00h]
0x14000e154  mov     rcx, [rdi+30h]
0x14000e158  mov     r13d, [rbp+arg_8]
0x14000e15c  mov     eax, [rcx+38h]
0x14000e15f  sub     eax, r13d
0x14000e162  test    eax, eax
0x14000e164  jle     short loc_14000E1C0
0x14000e166  mov     [rcx+3Ch], esi
0x14000e169  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e170  lea     r15, WPP_GLOBAL_Control
0x14000e177  cmp     rcx, r15
0x14000e17a  jz      short loc_14000E1B9
0x14000e17c  mov     eax, [rcx+2Ch]
0x14000e17f  test    al, 4
0x14000e181  jz      short loc_14000E1B9
0x14000e183  mov     r9, [rdi+30h]
0x14000e187  mov     edx, 4Fh ; 'O'
0x14000e18c  mov     r8d, [rbp+arg_0]
0x14000e190  mov     rcx, [rcx+18h]
0x14000e194  mov     eax, [r9+3Ch]
0x14000e198  mov     dword ptr [rsp+78h+Depth], eax
0x14000e19c  mov     eax, [r9+38h]
0x14000e1a0  mov     r9d, [r9+34h]
0x14000e1a4  mov     [rsp+78h+Tag], r8d
0x14000e1a9  lea     r8, WPP_9481eaf791d131fecb736b68b85870ad_Traceguids
0x14000e1b0  mov     dword ptr [rsp+78h+Size], eax
0x14000e1b4  call    WPP_SF_dddd
0x14000e1b9  xor     eax, eax
0x14000e1bb  jmp     loc_14000E7F5
0x14000e1c0  mov     rax, [rcx+18h]
0x14000e1c4  mov     ecx, [rax+38h]
0x14000e1c7  and     ecx, 10h
0x14000e1ca  mov     eax, ecx
0x14000e1cc  neg     eax
0x14000e1ce  sbb     eax, eax
0x14000e1d0  and     eax, 0FFFFFD44h
0x14000e1d5  add     eax, 2EEh
0x14000e1da  mov     [rbp+arg_18], eax
0x14000e1dd  mov     eax, ecx
0x14000e1df  neg     eax
0x14000e1e1  sbb     edx, edx
0x14000e1e3  and     edx, 0FFFFFFB0h
0x14000e1e6  add     edx, 64h ; 'd'
0x14000e1e9  neg     ecx
0x14000e1eb  sbb     ecx, ecx
0x14000e1ed  and     ecx, 0FFFFFFD0h
0x14000e1f0  add     ecx, 32h ; '2'
0x14000e1f3  call    GetRandomInteger
0x14000e1f8  mov     [rbp+arg_8], eax
0x14000e1fb  xor     ebx, ebx
0x14000e1fd  lea     rax, [rbp+var_20]
0x14000e201  mov     qword ptr [rbp+var_20+8], rax
0x14000e205  lea     rax, [rbp+var_20]
0x14000e209  mov     qword ptr [rbp+var_20], rax
0x14000e20d  lea     rax, [rbp+var_30]
0x14000e211  mov     qword ptr [rbp+var_30+8], rax
0x14000e215  lea     rax, [rbp+var_30]
0x14000e219  mov     qword ptr [rbp+var_30], rax
0x14000e21d  mov     ecx, [rbp+arg_0]
0x14000e220  lea     r15, WPP_GLOBAL_Control
0x14000e227  cmp     esi, ecx
0x14000e229  js      loc_14000E4EB
0x14000e22f  mov     rcx, [rdi+30h]
0x14000e233  add     rcx, 240h; Lookaside
0x14000e23a  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14000e241  nop     dword ptr [rax+rax+00h]
0x14000e246  mov     rbx, rax
0x14000e249  test    rax, rax
0x14000e24c  jz      loc_14000E426
0x14000e252  mov     r8, [rbp+var_38]; Size
0x14000e256  xor     edx, edx; Val
0x14000e258  mov     rcx, rax; void *
0x14000e25b  call    memset
0x14000e260  lea     rcx, [rbx+50h]
0x14000e264  xor     r15d, r15d
0x14000e267  mov     [rbx+58h], rcx
0x14000e26b  mov     [rcx], rcx
0x14000e26e  lea     rcx, [rbx+40h]
0x14000e272  mov     [rbx+48h], rcx
0x14000e276  mov     [rcx], rcx
0x14000e279  mov     [rbx+39h], r12b
0x14000e27d  mov     [rbx+3Eh], r12b
0x14000e281  mov     [rbx+10h], esi
0x14000e284  movzx   r10d, word ptr [rdi+9Ah]
0x14000e28c  test    r12b, r12b
0x14000e28f  jz      short loc_14000E2AE
0x14000e291  mov     dl, r15b
0x14000e294  mov     r8b, r12b
0x14000e297  movzx   eax, dl
0x14000e29a  inc     dl
0x14000e29c  lea     rcx, [rax+rax*4]
0x14000e2a0  mov     [rbx+rcx*8+75h], r8b
0x14000e2a5  mov     r8b, [rbx+3Eh]
0x14000e2a9  cmp     dl, r8b
0x14000e2ac  jb      short loc_14000E297
0x14000e2ae  mov     r11b, r15b
0x14000e2b1  jmp     loc_14000E3AD
0x14000e2b6  mov     rax, [rdi+30h]
0x14000e2ba  add     rax, 88h
0x14000e2c0  cmp     [rax], rax
0x14000e2c3  jz      loc_14000E3B6
0x14000e2c9  mov     r9, [rax+8]
0x14000e2cd  cmp     [r9], rax
0x14000e2d0  jnz     loc_14000E6A9
0x14000e2d6  mov     rcx, [r9+8]
0x14000e2da  cmp     [rcx], r9
0x14000e2dd  jnz     loc_14000E6A9
0x14000e2e3  mov     [rax+8], rcx
0x14000e2e7  mov     [rcx], rax
0x14000e2ea  cmp     [r9+3Ah], r15b
0x14000e2ee  jnz     short loc_14000E2F8
0x14000e2f0  mov     rcx, r9
0x14000e2f3  call    RemovePendingReceiverEntry
0x14000e2f8  cmp     [r9+60h], r15
0x14000e2fc  jz      loc_14000E385
0x14000e302  inc     byte ptr [rbx+3Ah]
0x14000e305  movups  xmm0, xmmword ptr [r9+60h]
0x14000e30a  movzx   eax, r11b
0x14000e30e  lea     rcx, [rax+rax*4]
0x14000e312  mov     al, r13b
0x14000e315  movups  xmmword ptr [rbx+rcx*8+60h], xmm0
0x14000e31a  sub     al, sil
0x14000e31d  movups  xmm1, xmmword ptr [r9+70h]
0x14000e322  movups  xmmword ptr [rbx+rcx*8+70h], xmm1
0x14000e327  movsd   xmm0, qword ptr [r9+80h]
0x14000e330  movsd   qword ptr [rbx+rcx*8+80h], xmm0
0x14000e339  mov     [rbx+rcx*8+74h], al
0x14000e33d  mov     eax, r13d
0x14000e340  sub     eax, esi
0x14000e342  lea     rcx, [rax+rax*4]
0x14000e346  mov     [rbx+rcx*8+75h], r11b
0x14000e34b  inc     r11b
0x14000e34e  dec     byte ptr [r9+3Ah]
0x14000e352  mov     [r9+60h], r15
0x14000e356  mov     [r9+84h], r15d
0x14000e35d  movzx   eax, word ptr [r9+36h]
0x14000e362  cmp     ax, r10w
0x14000e366  cmovnb  ax, r10w
0x14000e36b  movzx   r10d, ax
0x14000e36f  mov     al, [r9+3Dh]
0x14000e373  test    al, al
0x14000e375  jz      short loc_14000E385
0x14000e377  cmp     al, r12b
0x14000e37a  jnb     short loc_14000E385
0x14000e37c  cmp     [rbx+39h], r12b
0x14000e380  jnz     short loc_14000E385
0x14000e382  mov     [rbx+39h], al
0x14000e385  mov     rax, qword ptr [rbp+var_30]
0x14000e389  lea     rcx, [rbp+var_30]
0x14000e38d  cmp     [rax+8], rcx
0x14000e391  jnz     loc_14000E6A9
0x14000e397  mov     [r9], rax
0x14000e39a  lea     rcx, [rbp+var_30]
0x14000e39e  mov     [r9+8], rcx
0x14000e3a2  dec     r13d
0x14000e3a5  mov     [rax+8], r9
0x14000e3a9  mov     qword ptr [rbp+var_30], r9
0x14000e3ad  cmp     r13d, esi
0x14000e3b0  jns     loc_14000E2B6
0x14000e3b6  xor     r8d, r8d
0x14000e3b9  mov     [rbx+36h], r10w
0x14000e3be  mov     rdx, rbx
0x14000e3c1  mov     rcx, rdi
0x14000e3c4  call    RemoveRedundantNaks
0x14000e3c9  movzx   eax, byte ptr [rbx+39h]
0x14000e3cd  movzx   edx, byte ptr [rbx+3Ah]
0x14000e3d1  cmp     dl, al
0x14000e3d3  jnb     short loc_14000E3F9
0x14000e3d5  mov     ecx, eax
0x14000e3d7  mov     eax, [rbp+arg_8]
0x14000e3da  sub     ecx, edx
0x14000e3dc  xor     edx, edx
0x14000e3de  div     ecx
0x14000e3e0  mov     ecx, eax
0x14000e3e2  mov     eax, 0CCCCCCCDh
0x14000e3e7  mul     ecx
0x14000e3e9  shr     edx, 4
0x14000e3ec  mov     eax, edx
0x14000e3ee  add     rax, cs:WPP_MAIN_CB.Dpc.SystemArgument1
0x14000e3f5  mov     [rbx+18h], rax
0x14000e3f9  mov     rax, qword ptr [rbp+var_20]
0x14000e3fd  lea     rcx, [rbp+var_20]
0x14000e401  cmp     [rax+8], rcx
0x14000e405  jnz     loc_14000E6A9
0x14000e40b  mov     [rbx], rax
0x14000e40e  lea     rcx, [rbp+var_20]
0x14000e412  mov     [rbx+8], rcx
0x14000e416  sub     esi, r12d
0x14000e419  mov     [rax+8], rbx
0x14000e41d  mov     qword ptr [rbp+var_20], rbx
0x14000e421  jmp     loc_14000E21D
0x14000e426  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e42d  cmp     rcx, r15
0x14000e430  jz      short loc_14000E44E
0x14000e432  mov     eax, [rcx+2Ch]
0x14000e435  test    al, 2
0x14000e437  jz      short loc_14000E44E
0x14000e439  mov     rcx, [rcx+18h]
0x14000e43d  lea     r8, WPP_9481eaf791d131fecb736b68b85870ad_Traceguids
0x14000e444  mov     edx, 50h ; 'P'
0x14000e449  call    WPP_SF_
0x14000e44e  mov     r14d, 0C000009Ah
0x14000e454  xor     r13d, r13d
0x14000e457  mov     esi, [rbp+arg_8]
0x14000e45a  mov     rdx, qword ptr [rbp+var_20]
0x14000e45e  lea     rax, [rbp+var_20]
0x14000e462  cmp     rdx, rax
0x14000e465  jz      short loc_14000E4A9
0x14000e467  mov     rax, [rdi+30h]
0x14000e46b  mov     rcx, [rax+90h]
0x14000e472  mov     [rdx+8], rcx
0x14000e476  mov     rax, qword ptr [rbp+var_20+8]
0x14000e47a  mov     rcx, [rdi+30h]
0x14000e47e  add     rcx, 88h
0x14000e485  mov     [rax], rcx
0x14000e488  mov     rax, [rdi+30h]
0x14000e48c  mov     rcx, [rax+90h]
0x14000e493  mov     rax, qword ptr [rbp+var_20]
0x14000e497  mov     [rcx], rax
0x14000e49a  mov     rcx, [rdi+30h]
0x14000e49e  mov     rax, qword ptr [rbp+var_20+8]
0x14000e4a2  mov     [rcx+90h], rax
0x14000e4a9  mov     rdx, qword ptr [rbp+var_30]
0x14000e4ad  lea     rax, [rbp+var_30]
0x14000e4b1  cmp     rdx, rax
0x14000e4b4  jz      loc_14000E6B0
0x14000e4ba  lea     rax, [rbp+var_30]
0x14000e4be  cmp     [rdx+8], rax
  ... truncated ...
```
