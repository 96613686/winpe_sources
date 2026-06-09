# WfpNlShimInspectvSwitchForwardDatagram

- ea: `0x14016fe78`
- end: `0x140170654`
- name: `WfpNlShimInspectvSwitchForwardDatagram`
- size: `2012`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config`

## callers

- `0x14010cc60`

## callees

- `0x1400dc890`
- `0x1400dca00`
- `0x1400f71c0`
- `0x1400fdec0`
- `0x14016f388`
- `0x14016f3e0`
- `0x14016f58c`
- `0x14016f660`
- `0x14016f91c`
- `0x14016fcac`
- `0x14016fdf4`
- `0x14016fe78`
- `0x1401c0fd0`
- `0x1401c1580`

## import_xrefs

- `NETIO!NetioDereferenceNetBufferList` at `0x1401705c2`
- `NETIO!NetioDereferenceNetBufferList` at `0x1401705f4`
- `NETIO!NetioDereferenceNetBufferList` at `0x1401705c2`
- `NETIO!NetioDereferenceNetBufferList` at `0x1401705f4`
- `NETIO!NetioReferenceNetBufferList` at `0x14016ffff`
- `NETIO!NetioReferenceNetBufferList` at `0x140170016`
- `NETIO!NetioReferenceNetBufferList` at `0x14016ffff`
- `NETIO!NetioReferenceNetBufferList` at `0x140170016`
- `NETIO!NetioFlowRemoveContext` at `0x1401701fd`
- `NETIO!NetioFlowRemoveContext` at `0x1401701fd`
- `NETIO!NetioFlowRetrieveContext` at `0x14017010e`
- `NETIO!NetioFlowRetrieveContext` at `0x14017010e`
- `NETIO!KfdReleaseCachedFilters` at `0x14017040a`
- `NETIO!KfdReleaseCachedFilters` at `0x14017040a`
- `NETIO!KfdClassify` at `0x140170354`
- `NETIO!KfdClassify` at `0x140170354`
- `NETIO!KfdGetLayerCacheEpoch` at `0x140170138`
- `NETIO!KfdGetLayerCacheEpoch` at `0x140170138`
- `fwpkclnt!FwppvSwitchGetDestinationInterface` at `0x1401700b1`
- `fwpkclnt!FwppvSwitchGetDestinationInterface` at `0x1401704c2`
- `fwpkclnt!FwppvSwitchGetDestinationInterface` at `0x1401700b1`
- `fwpkclnt!FwppvSwitchGetDestinationInterface` at `0x1401704c2`
- `fwpkclnt!FwppDereferencevSwitchNblContext` at `0x1401705a8`
- `fwpkclnt!FwppDereferencevSwitchNblContext` at `0x1401705e2`
- `fwpkclnt!FwppDereferencevSwitchNblContext` at `0x1401705a8`
- `fwpkclnt!FwppDereferencevSwitchNblContext` at `0x1401705e2`
- `fwpkclnt!FwppReferencevSwitchNblContext` at `0x14016ffde`
- `fwpkclnt!FwppReferencevSwitchNblContext` at `0x14016fff0`
- `fwpkclnt!FwppReferencevSwitchNblContext` at `0x140170025`
- `fwpkclnt!FwppReferencevSwitchNblContext` at `0x14016ffde`
- `fwpkclnt!FwppReferencevSwitchNblContext` at `0x14016fff0`
- `fwpkclnt!FwppReferencevSwitchNblContext` at `0x140170025`
- `fwpkclnt!FwppGetvSwitchNblContext` at `0x14016ff7c`
- `fwpkclnt!FwppGetvSwitchNblContext` at `0x140170572`
- `fwpkclnt!FwppGetvSwitchNblContext` at `0x14016ff7c`
- `fwpkclnt!FwppGetvSwitchNblContext` at `0x140170572`
- `fwpkclnt!FwppNetBufferListAssociateContext` at `0x14016ffc6`
- `fwpkclnt!FwppNetBufferListAssociateContext` at `0x14016ffc6`

## pseudocode

```c
__int64 __fastcall WfpNlShimInspectvSwitchForwardDatagram(
        int a1,
        __int64 a2,
        int a3,
        int a4,
        __int16 a5,
        __int16 a6,
        __int64 a7,
        __int64 a8)
{
  int v8; // r13d
  unsigned int v9; // ebx
  bool v10; // zf
  int v12; // eax
  unsigned __int16 v13; // r12
  _QWORD *v14; // rsi
  __int64 v15; // rax
  __int64 v16; // rdx
  bool v17; // al
  unsigned int *v18; // r15
  __int64 DestinationInterface; // r13
  unsigned int v20; // esi
  int v21; // r10d
  unsigned int v22; // r9d
  char v23; // r12
  int v24; // ecx
  char v25; // al
  __int64 v26; // r8
  _QWORD *v27; // rax
  __int64 v28; // r9
  unsigned int v29; // eax
  char v30; // al
  int v31; // r9d
  __int64 v32; // r8
  int v33; // edx
  unsigned int i; // esi
  unsigned int v35; // eax
  int v36; // r8d
  _QWORD *v37; // rsi
  int v38; // r15d
  _QWORD *v39; // r14
  __int64 v40; // rax
  int v41; // ecx
  bool v43; // [rsp+80h] [rbp-80h]
  char v44; // [rsp+81h] [rbp-7Fh]
  char StorageForClassifyValues; // [rsp+82h] [rbp-7Eh]
  char v46; // [rsp+83h] [rbp-7Dh] BYREF
  _BYTE v47[4]; // [rsp+84h] [rbp-7Ch] BYREF
  int v48; // [rsp+88h] [rbp-78h]
  unsigned int v49; // [rsp+8Ch] [rbp-74h] BYREF
  int v50; // [rsp+90h] [rbp-70h]
  void *v51; // [rsp+98h] [rbp-68h] BYREF
  int v52; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v53; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v54; // [rsp+B0h] [rbp-50h]
  __int64 v55; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v56; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v57; // [rsp+C8h] [rbp-38h]
  int v58; // [rsp+D0h] [rbp-30h]
  int v59; // [rsp+D4h] [rbp-2Ch]
  int v60; // [rsp+D8h] [rbp-28h]
  __int128 v61; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v62; // [rsp+F0h] [rbp-10h] BYREF
  int v63; // [rsp+F8h] [rbp-8h]
  __int64 v64; // [rsp+100h] [rbp+0h] BYREF
  int v65; // [rsp+108h] [rbp+8h]
  __int64 v66; // [rsp+110h] [rbp+10h] BYREF
  int v67; // [rsp+118h] [rbp+18h]
  __int64 v68; // [rsp+120h] [rbp+20h] BYREF
  int v69; // [rsp+128h] [rbp+28h]
  _DWORD v70[4]; // [rsp+130h] [rbp+30h] BYREF
  __int128 v71; // [rsp+140h] [rbp+40h] BYREF
  __int128 v72; // [rsp+150h] [rbp+50h]
  __int64 v73; // [rsp+160h] [rbp+60h]

  LOBYTE(v8) = 0;
  v54 = a8;
  v58 = a4;
  v9 = 1;
  v10 = *(_BYTE *)(a7 + 73) == 0;
  v69 = 0;
  v67 = 0;
  v65 = 0;
  v63 = 0;
  memset(v70, 0, 12);
  v68 = 0;
  v66 = 0;
  v64 = 0;
  v62 = 0;
  v56 = 0;
  LODWORD(v57) = 0;
  WORD2(v57) = 0;
  v55 = 0;
  v51 = 0;
  StorageForClassifyValues = 0;
  LODWORD(v73) = 0;
  v12 = 1;
  v59 = a3;
  v60 = a1;
  v49 = 1;
  v48 = v8;
  v61 = 0;
  v46 = 0;
  v47[0] = 0;
  v71 = 0;
  v72 = 0;
  if ( v10 )
    v12 = *(_DWORD *)(a7 + 12);
  v50 = v12;
  if ( a1 )
  {
    v13 = 75;
    if ( v12 != 1 )
      v13 = 77;
  }
  else
  {
    v13 = 74;
    if ( v12 != 1 )
      v13 = 76;
  }
  v14 = *(_QWORD **)(a2 + 64);
  if ( *(_BYTE *)(a2 + 72) )
  {
    while ( 1 )
    {
      if ( !v14 )
        goto LABEL_16;
      v15 = FwppGetvSwitchNblContext(v14);
      if ( !v15 )
      {
        if ( FwppNetBufferListAssociateContext(
               1,
               v14,
               0xFFFF,
               a7,
               2,
               0,
               0,
               0,
               NlShimvSwitchNetBufferListEventNotifyFn,
               0) )
        {
          v23 = 1;
          goto LABEL_93;
        }
        FwppReferencevSwitchNblContext(a7);
        v15 = a7;
      }
      FwppReferencevSwitchNblContext(v15);
      NetioReferenceNetBufferList(v14);
      v14 = (_QWORD *)*v14;
    }
  }
  NetioReferenceNetBufferList(*(_QWORD *)(a2 + 64));
  FwppReferencevSwitchNblContext(a7);
LABEL_16:
  v16 = *(_QWORD *)(a7 + 56);
  v17 = 0;
  v18 = 0;
  v43 = 0;
  DestinationInterface = 0;
  v20 = 0;
  if ( v16 && !*(_BYTE *)(a7 + 73) )
  {
    v21 = *(_DWORD *)(v16 + 12);
    v22 = *(_DWORD *)(v16 + 8);
    v43 = v21 == 1;
    if ( v22 )
    {
      do
      {
        if ( (*(_BYTE *)(v20 * *(_DWORD *)(v16 + 4) + *(_QWORD *)(v16 + 16) + 6LL) & 1) == 0 )
          break;
        ++v20;
      }
      while ( v20 < v22 );
    }
    if ( v20 == v21 )
    {
      LOBYTE(v8) = v48;
      v9 = 0;
      *(_DWORD *)(a7 + 68) = 0;
      v23 = 1;
      goto LABEL_93;
    }
    v18 = (unsigned int *)(*(_QWORD *)(v16 + 16) + *(_DWORD *)(v16 + 4) * v20);
    DestinationInterface = FwppvSwitchGetDestinationInterface(
                             *(_QWORD *)(a7 + 136),
                             *v18,
                             *((unsigned __int16 *)v18 + 2));
    v17 = v43;
  }
  if ( *(_BYTE *)(a2 + 72)
    || v50 != 1 && !v17
    || !v54
    || !*(_QWORD *)(v54 + 200)
    || (v53 = 0, (unsigned int)NetioFlowRetrieveContext(v54, 1, NlShimReferenceFwLayerCache, &v53))
    || !v53 )
  {
LABEL_46:
    StorageForClassifyValues = WfpShimGetStorageForClassifyValues(&v55, &v51, v47, &v46);
    if ( !StorageForClassifyValues )
    {
      LOBYTE(v8) = v48;
      v23 = 1;
      v9 = 1;
      goto LABEL_93;
    }
    v49 = 0;
    v44 = 0;
    while ( 1 )
    {
      HIDWORD(v56) = NlShimMarshalvSwitchFwLayerFields(
                       v60,
                       a2,
                       v59,
                       v58,
                       a5,
                       a6,
                       a7,
                       DestinationInterface,
                       v50,
                       (__int64)v70,
                       (__int64)&v68,
                       (__int64)&v66,
                       (__int64)&v64,
                       (__int64)&v62,
                       v55);
      v57 = v55;
      LOWORD(v56) = v13;
      memset(v51, 0, 0x2A8u);
      LOBYTE(v26) = v44;
      v27 = (char *)v51 + 624;
      *((_QWORD *)v51 + 79) = (char *)v51 + 624;
      *v27 = v27;
      NlShimSetvSwitchLayerMetadata(a7, DestinationInterface, v26);
      if ( !*(_BYTE *)(a2 + 72) && v54 && (v50 == 1 || v43) )
      {
        *((_QWORD *)&v61 + 1) = &v61;
        *(_QWORD *)&v61 = &v61;
        *(_QWORD *)(v28 + 512) = &v61;
      }
      if ( (unsigned int)KfdClassify(v13, &v56, v51, *(_QWORD *)(a2 + 64), 0, &v71) )
      {
        v71 = 0;
        LODWORD(v71) = 4097;
        v72 = 0;
        v73 = 0;
      }
      else
      {
        v29 = WfpShimClassifyOutToIpFilterAction(&v71);
        WfpNlShimCheckIfPacketAbsorbed(v29, *(_QWORD *)(a2 + 64));
        if ( (_DWORD)v71 == 4097 )
        {
          v30 = v48;
          if ( (BYTE12(v72) & 1) == 0 )
            v30 = 1;
          LOBYTE(v48) = v30;
        }
        if ( !*(_BYTE *)(a2 + 72) && v54 && *((_DWORD *)v51 + 134) && (v50 == 1 || v43) )
        {
          v31 = DestinationInterface ? *(_DWORD *)(DestinationInterface + 1040) : 0;
          if ( (int)NlShimCacheMatchedFwLayerFilterList(
                      v54,
                      *((_DWORD *)v51 + 132),
                      0,
                      v31,
                      *((_QWORD *)v51 + 64),
                      (__int64)&v56,
                      1) < 0 )
            KfdReleaseCachedFilters(&v61);
        }
      }
      if ( *(_QWORD *)(a7 + 56) )
      {
        if ( (_DWORD)v71 == 4097 )
        {
          if ( (BYTE12(v72) & 1) == 0 )
            *(_BYTE *)(a7 + 64) = 1;
          if ( (unsigned int)NlShimExcludeDestinationForNblChain(a7, *(_QWORD *)(a2 + 64), v20) )
          {
LABEL_91:
            LOBYTE(v8) = v48;
            v23 = 1;
            goto LABEL_93;
          }
        }
        else
        {
          ++v49;
        }
        v32 = *(_QWORD *)(a7 + 56);
        v33 = -1;
        for ( i = v20 + 1; i < *(_DWORD *)(v32 + 8); ++i )
        {
          if ( (*(_BYTE *)(*(_DWORD *)(v32 + 4) * i + *(_QWORD *)(v32 + 16) + 6LL) & 1) == 0 )
          {
            v33 = i;
            break;
          }
        }
        v20 = v33;
        if ( v33 == -1 )
        {
          v18 = 0;
        }
        else
        {
          v18 = (unsigned int *)(*(_QWORD *)(v32 + 16) + (unsigned int)(*(_DWORD *)(v32 + 4) * v33));
          DestinationInterface = FwppvSwitchGetDestinationInterface(
                                   *(_QWORD *)(a7 + 136),
                                   *v18,
                                   *((unsigned __int16 *)v18 + 2));
          v44 = 1;
        }
      }
      v35 = WfpShimClassifyOutToIpFilterAction(&v71);
      v9 = v35;
      if ( v35 )
      {
        if ( v49 )
        {
          v9 = 0;
        }
        else if ( v35 == 1 )
        {
          v36 = (int)v51;
          *((_QWORD *)v51 + 64) = 0;
          ShimIndicateDiscardNoClassify(v13, (unsigned int)&v56, v36, *(_QWORD *)(a2 + 64), 0, v72, 0);
        }
      }
      if ( !v18 )
        goto LABEL_91;
    }
  }
  v52 = 0;
  KfdGetLayerCacheEpoch(v13, &v52);
  if ( *(_DWORD *)(v53 + 88) != v52 )
  {
    *(_DWORD *)(v53 + 88) = v52;
LABEL_45:
    NetioFlowRemoveContext(v54, 1);
    NLShimDereferenceFwLayerCache(&v53);
    goto LABEL_46;
  }
  if ( DestinationInterface )
    v24 = *(_DWORD *)(DestinationInterface + 1040);
  else
    v24 = 0;
  if ( *(_DWORD *)(v53 + 24) != v24 )
    goto LABEL_45;
  v25 = NlShimFwLayerDirectClassify((unsigned int)&v49, v13, v53, a2, 0, a7, DestinationInterface, (__int64)&v49);
  v9 = v49;
  if ( !v25 )
    goto LABEL_45;
  WfpNlShimCheckIfPacketAbsorbed(v49, *(_QWORD *)(a2 + 64));
  v23 = 1;
  v8 = (unsigned __int8)v48;
  if ( v9 == 1 )
    v8 = 1;
  v48 = v8;
  if ( v18 && v9 )
  {
    *(_BYTE *)(a7 + 64) = 1;
    NlShimExcludeDestinationForNblChain(a7, *(_QWORD *)(a2 + 64), v20);
  }
  NLShimDereferenceFwLayerCache(&v53);
LABEL_93:
  if ( *(_BYTE *)(a2 + 72) )
  {
    v37 = *(_QWORD **)(a2 + 64);
    v38 = v9;
    v39 = v37;
    if ( v37 )
    {
      do
      {
        v37 = (_QWORD *)*v37;
        v40 = FwppGetvSwitchNblContext(v39);
        if ( v9 != 3 )
        {
          *v39 = 0;
          v10 = v23 == 0;
          v41 = v9;
          v23 = 0;
          if ( v10 )
            v41 = v38;
          v38 = v41;
          if ( v41 != v9 )
          {
            v9 = 1;
            v38 = 1;
          }
        }
        FwppDereferencevSwitchNblContext(v40);
        *((_DWORD *)v39 + 34) &= ~0x800000u;
        NetioDereferenceNetBufferList(v39, 0);
        v39 = v37;
      }
      while ( v37 );
      LOBYTE(v8) = v48;
    }
    v9 = v38;
  }
  else
  {
    FwppDereferencevSwitchNblContext(a7);
    NetioDereferenceNetBufferList(*(_QWORD *)(a2 + 64), 0);
  }
  if ( StorageForClassifyValues )
    WfpShimReturnStorageForClassifyValues(&v55, &v51, v47, &v46);
  if ( v9 == 1 )
    *(_DWORD *)(a7 + 68) = (_BYTE)v8 != 0 ? -1073741790 : -1073741670;
  return v9;
}

```

## disassembly

```asm
0x14016fe78  push    rbp
0x14016fe7a  push    rbx
0x14016fe7b  push    rsi
0x14016fe7c  push    rdi
0x14016fe7d  push    r12
0x14016fe7f  push    r13
0x14016fe81  push    r14
0x14016fe83  push    r15
0x14016fe85  lea     rbp, [rsp-78h]
0x14016fe8a  sub     rsp, 178h
0x14016fe91  mov     rax, cs:__security_cookie
0x14016fe98  xor     rax, rsp
0x14016fe9b  mov     [rbp+0B0h+var_48], rax
0x14016fe9f  mov     rax, [rbp+0B0h+arg_38]
0x14016fea6  xor     r13b, r13b
0x14016fea9  mov     rdi, [rbp+0B0h+arg_30]
0x14016feb0  xorps   xmm0, xmm0
0x14016feb3  mov     [rbp+0B0h+var_100], rax
0x14016feb7  mov     r15d, 1
0x14016febd  xor     eax, eax
0x14016febf  mov     [rbp+0B0h+var_E0], r9d
0x14016fec3  mov     [rbp+0B0h+var_7C], rax
0x14016fec7  mov     ebx, r15d
0x14016feca  cmp     [rdi+49h], al
0x14016fecd  mov     r14, rdx
0x14016fed0  mov     [rbp+0B0h+var_8C], rax
0x14016fed4  mov     [rbp+0B0h+var_9C], rax
0x14016fed8  mov     [rbp+0B0h+var_AC], rax
0x14016fedc  mov     [rbp+0B0h+var_BC], rax
0x14016fee0  mov     [rbp+30h], rax
0x14016fee4  mov     [rbp+20h], rax
0x14016fee8  mov     [rbp+10h], rax
0x14016feec  mov     [rbp+0], rax
0x14016fef0  mov     [rbp-10h], rax
0x14016fef4  mov     [rbp+0B0h+var_F0], rax
0x14016fef8  mov     dword ptr [rbp+0B0h+var_E8], eax
0x14016fefb  mov     word ptr [rbp+0B0h+var_E8+4], ax
0x14016feff  mov     [rbp+0B0h+var_F8], rax
0x14016ff03  mov     [rbp+0B0h+var_118], rax
0x14016ff07  mov     [rbp+0B0h+var_12E], al
0x14016ff0a  mov     dword ptr [rbp+0B0h+var_50], eax
0x14016ff0d  mov     eax, r15d
0x14016ff10  mov     [rbp+0B0h+var_DC], r8d
0x14016ff14  mov     [rbp+0B0h+var_D8], ecx
0x14016ff17  mov     [rbp+0B0h+var_124], ebx
0x14016ff1a  mov     [rbp+0B0h+var_128], r13d
0x14016ff1e  movups  [rbp+0B0h+var_D0], xmm0
0x14016ff22  mov     [rbp+0B0h+var_12D], r13b
0x14016ff26  mov     [rbp+0B0h+var_12C], r13b
0x14016ff2a  movups  [rbp+0B0h+var_70], xmm0
0x14016ff2e  movups  [rbp+0B0h+var_60], xmm0
0x14016ff32  jnz     short loc_14016FF37
0x14016ff34  mov     eax, [rdi+0Ch]
0x14016ff37  mov     [rbp+0B0h+var_120], eax
0x14016ff3a  test    ecx, ecx
0x14016ff3c  jnz     short loc_14016FF51
0x14016ff3e  mov     ecx, 4Ch ; 'L'
0x14016ff43  cmp     eax, r15d
0x14016ff46  lea     r12d, [rcx-2]
0x14016ff4a  cmovnz  r12w, cx
0x14016ff4f  jmp     short loc_14016FF62
0x14016ff51  mov     r12d, 4Bh ; 'K'
0x14016ff57  cmp     eax, r15d
0x14016ff5a  jz      short loc_14016FF62
0x14016ff5c  mov     r12d, 4Dh ; 'M'
0x14016ff62  cmp     byte ptr [rdx+48h], 0
0x14016ff66  mov     rsi, [rdx+40h]
0x14016ff6a  jz      loc_140170013
0x14016ff70  test    rsi, rsi
0x14016ff73  jz      loc_140170031
0x14016ff79  mov     rcx, rsi
0x14016ff7c  call    cs:__imp_FwppGetvSwitchNblContext
0x14016ff83  nop     dword ptr [rax+rax+00h]
0x14016ff88  xor     ecx, ecx
0x14016ff8a  test    rax, rax
0x14016ff8d  jnz     short loc_14016FFED
0x14016ff8f  mov     dword ptr [rsp+1B0h+var_168], ecx
0x14016ff93  lea     rax, NlShimvSwitchNetBufferListEventNotifyFn
0x14016ff9a  mov     [rsp+1B0h+var_170], rax
0x14016ff9f  mov     r8d, 0FFFFh
0x14016ffa5  mov     [rsp+1B0h+var_178], rcx
0x14016ffaa  mov     r9, rdi
0x14016ffad  mov     [rsp+1B0h+var_180], rcx
0x14016ffb2  mov     rdx, rsi
0x14016ffb5  mov     [rsp+1B0h+var_188], rcx
0x14016ffba  mov     ecx, r15d
0x14016ffbd  mov     [rsp+1B0h+var_190], 2
0x14016ffc6  call    cs:__imp_FwppNetBufferListAssociateContext
0x14016ffcd  nop     dword ptr [rax+rax+00h]
0x14016ffd2  test    rax, rax
0x14016ffd5  jnz     loc_140170549
0x14016ffdb  mov     rcx, rdi
0x14016ffde  call    cs:__imp_FwppReferencevSwitchNblContext
0x14016ffe5  nop     dword ptr [rax+rax+00h]
0x14016ffea  mov     rax, rdi
0x14016ffed  mov     rcx, rax
0x14016fff0  call    cs:__imp_FwppReferencevSwitchNblContext
0x14016fff7  nop     dword ptr [rax+rax+00h]
0x14016fffc  mov     rcx, rsi
0x14016ffff  call    cs:__imp_NetioReferenceNetBufferList
0x140170006  nop     dword ptr [rax+rax+00h]
0x14017000b  mov     rsi, [rsi]
0x14017000e  jmp     loc_14016FF70
0x140170013  mov     rcx, rsi
0x140170016  call    cs:__imp_NetioReferenceNetBufferList
0x14017001d  nop     dword ptr [rax+rax+00h]
0x140170022  mov     rcx, rdi
0x140170025  call    cs:__imp_FwppReferencevSwitchNblContext
0x14017002c  nop     dword ptr [rax+rax+00h]
0x140170031  mov     rdx, [rdi+38h]
0x140170035  xor     al, al
0x140170037  xor     r15d, r15d
0x14017003a  mov     [rbp+0B0h+var_130], al
0x14017003d  xor     r13d, r13d
0x140170040  xor     esi, esi
0x140170042  test    rdx, rdx
0x140170045  jz      short loc_1401700C3
0x140170047  cmp     [rdi+49h], al
0x14017004a  jnz     short loc_1401700C3
0x14017004c  mov     r10d, [rdx+0Ch]
0x140170050  mov     r15d, ebx
0x140170053  mov     r9d, [rdx+8]
0x140170057  cmp     r10d, ebx
0x14017005a  setz    [rbp+0B0h+var_130]
0x14017005e  test    r9d, r9d
0x140170061  jz      short loc_140170080
0x140170063  mov     r11d, [rdx+4]
0x140170067  mov     r8, [rdx+10h]
0x14017006b  mov     eax, r11d
0x14017006e  imul    eax, esi
0x140170071  test    [rax+r8+6], r15b
0x140170076  jz      short loc_140170080
0x140170078  add     esi, r15d
0x14017007b  cmp     esi, r9d
0x14017007e  jb      short loc_14017006B
0x140170080  cmp     esi, r10d
0x140170083  jnz     short loc_140170096
0x140170085  mov     r13d, [rbp+0B0h+var_128]
0x140170089  xor     ebx, ebx
0x14017008b  mov     [rdi+44h], ebx
0x14017008e  mov     r12d, r15d
0x140170091  jmp     loc_14017054C
0x140170096  mov     rcx, [rdi+88h]
0x14017009d  mov     r15d, esi
0x1401700a0  imul    r15d, [rdx+4]
0x1401700a5  add     r15, [rdx+10h]
0x1401700a9  movzx   r8d, word ptr [r15+4]
0x1401700ae  mov     edx, [r15]
0x1401700b1  call    cs:__imp_FwppvSwitchGetDestinationInterface
0x1401700b8  nop     dword ptr [rax+rax+00h]
0x1401700bd  mov     r13, rax
0x1401700c0  mov     al, [rbp+0B0h+var_130]
0x1401700c3  cmp     byte ptr [r14+48h], 0
0x1401700c8  jnz     loc_140170212
0x1401700ce  cmp     [rbp+0B0h+var_120], ebx
0x1401700d1  jz      short loc_1401700DB
0x1401700d3  test    al, al
0x1401700d5  jz      loc_140170212
0x1401700db  mov     rax, [rbp+0B0h+var_100]
0x1401700df  test    rax, rax
0x1401700e2  jz      loc_140170212
0x1401700e8  cmp     qword ptr [rax+0C8h], 0
0x1401700f0  jz      loc_140170212
0x1401700f6  lea     r9, [rbp+0B0h+var_108]
0x1401700fa  mov     [rbp+0B0h+var_108], 0
0x140170102  lea     r8, NlShimReferenceFwLayerCache
0x140170109  mov     edx, ebx
0x14017010b  mov     rcx, rax
0x14017010e  call    cs:__imp_NetioFlowRetrieveContext
0x140170115  nop     dword ptr [rax+rax+00h]
0x14017011a  test    eax, eax
0x14017011c  jnz     loc_140170212
0x140170122  cmp     [rbp+0B0h+var_108], 0
0x140170127  jz      loc_140170212
0x14017012d  lea     rdx, [rbp+0B0h+var_110]
0x140170131  mov     [rbp+0B0h+var_110], eax
0x140170134  movzx   ecx, r12w
0x140170138  call    cs:__imp_KfdGetLayerCacheEpoch
0x14017013f  nop     dword ptr [rax+rax+00h]
0x140170144  mov     rax, [rbp+0B0h+var_108]
0x140170148  mov     ecx, [rbp+0B0h+var_110]
0x14017014b  cmp     [rax+58h], ecx
0x14017014e  jnz     loc_1401701F4
0x140170154  test    r13, r13
0x140170157  jz      short loc_140170162
0x140170159  mov     ecx, [r13+410h]
0x140170160  jmp     short loc_140170164
0x140170162  xor     ecx, ecx
0x140170164  cmp     [rax+18h], ecx
0x140170167  jnz     loc_1401701ED
0x14017016d  lea     rcx, [rbp+0B0h+var_124]
0x140170171  mov     r9, r14
0x140170174  mov     [rsp+1B0h+var_178], rcx
0x140170179  mov     r8, rax
0x14017017c  mov     [rsp+1B0h+var_180], r13
0x140170181  movzx   edx, r12w
0x140170185  mov     [rsp+1B0h+var_188], rdi
0x14017018a  mov     [rsp+1B0h+var_190], 0
0x140170193  call    NlShimFwLayerDirectClassify
0x140170198  mov     ebx, [rbp+0B0h+var_124]
0x14017019b  test    al, al
0x14017019d  jz      short loc_1401701ED
0x14017019f  mov     rdx, [r14+40h]
0x1401701a3  mov     ecx, ebx
0x1401701a5  call    WfpNlShimCheckIfPacketAbsorbed
0x1401701aa  mov     r13d, [rbp+0B0h+var_128]
0x1401701ae  mov     r12d, 1
0x1401701b4  cmp     ebx, r12d
0x1401701b7  movzx   r13d, r13b
0x1401701bb  cmovz   r13d, r12d
0x1401701bf  mov     [rbp+0B0h+var_128], r13d
0x1401701c3  test    r15, r15
0x1401701c6  jz      short loc_1401701DF
0x1401701c8  test    ebx, ebx
0x1401701ca  jz      short loc_1401701DF
0x1401701cc  mov     [rdi+40h], r12b
0x1401701d0  mov     r8d, esi
0x1401701d3  mov     rdx, [r14+40h]
0x1401701d7  mov     rcx, rdi
0x1401701da  call    NlShimExcludeDestinationForNblChain
0x1401701df  lea     rcx, [rbp+0B0h+var_108]
0x1401701e3  call    NLShimDereferenceFwLayerCache
0x1401701e8  jmp     loc_14017054C
0x1401701ed  mov     edx, 1
0x1401701f2  jmp     short loc_1401701F9
0x1401701f4  mov     [rax+58h], ecx
0x1401701f7  mov     edx, ebx
0x1401701f9  mov     rcx, [rbp+0B0h+var_100]
0x1401701fd  call    cs:__imp_NetioFlowRemoveContext
0x140170204  nop     dword ptr [rax+rax+00h]
0x140170209  lea     rcx, [rbp+0B0h+var_108]
0x14017020d  call    NLShimDereferenceFwLayerCache
0x140170212  lea     r9, [rbp+0B0h+var_12D]
0x140170216  lea     r8, [rbp+0B0h+var_12C]
0x14017021a  lea     rdx, [rbp+0B0h+var_118]
0x14017021e  lea     rcx, [rbp+0B0h+var_F8]
0x140170222  call    WfpShimGetStorageForClassifyValues
0x140170227  mov     [rbp+0B0h+var_12E], al
0x14017022a  test    al, al
0x14017022c  jnz     short loc_140170240
0x14017022e  mov     r13d, [rbp+0B0h+var_128]
0x140170232  mov     r12d, 1
0x140170238  mov     ebx, r12d
0x14017023b  jmp     loc_14017054C
0x140170240  mov     [rbp+0B0h+var_124], 0
0x140170247  mov     [rbp+0B0h+var_12F], 0
0x14017024b  mov     rax, [rbp+0B0h+var_F8]
0x14017024f  mov     rdx, r14
0x140170252  mov     r9d, [rbp+0B0h+var_E0]
0x140170256  mov     r8d, [rbp+0B0h+var_DC]
0x14017025a  mov     ecx, [rbp+0B0h+var_D8]
0x14017025d  mov     [rsp+1B0h+var_140], rax
0x140170262  lea     rax, [rbp+0B0h+var_C0]
0x140170266  mov     [rsp+1B0h+var_148], rax
0x14017026b  lea     rax, [rbp+0B0h+var_B0]
0x14017026f  mov     [rsp+1B0h+var_150], rax
0x140170274  lea     rax, [rbp+0B0h+var_A0]
0x140170278  mov     [rsp+1B0h+var_158], rax
0x14017027d  lea     rax, [rbp+0B0h+var_90]
0x140170281  mov     [rsp+1B0h+var_160], rax
0x140170286  lea     rax, [rbp+0B0h+var_80]
0x14017028a  mov     [rsp+1B0h+var_168], rax
0x14017028f  mov     eax, [rbp+0B0h+var_120]
0x140170292  mov     dword ptr [rsp+1B0h+var_170], eax
0x140170296  movzx   eax, [rbp+0B0h+arg_28]
0x14017029d  mov     [rsp+1B0h+var_178], r13
0x1401702a2  mov     [rsp+1B0h+var_180], rdi
0x1401702a7  mov     word ptr [rsp+1B0h+var_188], ax
0x1401702ac  movzx   eax, [rbp+0B0h+arg_20]
0x1401702b3  mov     word ptr [rsp+1B0h+var_190], ax
0x1401702b8  call    NlShimMarshalvSwitchFwLayerFields
0x1401702bd  mov     rcx, [rbp+0B0h+var_118]; void *
0x1401702c1  xor     edx, edx; Val
0x1401702c3  mov     dword ptr [rbp+0B0h+var_F0+4], eax
0x1401702c6  mov     r8d, 2A8h; Size
0x1401702cc  mov     rax, [rbp+0B0h+var_F8]
0x1401702d0  mov     [rbp+0B0h+var_E8], rax
0x1401702d4  mov     word ptr [rbp+0B0h+var_F0], r12w
0x1401702d9  call    memset
0x1401702de  mov     r9, [rbp+0B0h+var_118]
0x1401702e2  mov     rdx, r13
0x1401702e5  mov     r8b, [rbp+0B0h+var_12F]
0x1401702e9  mov     rcx, rdi
0x1401702ec  lea     rax, [r9+270h]
0x1401702f3  mov     [r9+278h], rax
0x1401702fa  mov     [rax], rax
0x1401702fd  call    NlShimSetvSwitchLayerMetadata
0x140170302  xor     ecx, ecx
0x140170304  cmp     [r14+48h], cl
0x140170308  jnz     short loc_140170336
0x14017030a  cmp     [rbp+0B0h+var_100], rcx
0x14017030e  jz      short loc_140170336
0x140170310  cmp     [rbp+0B0h+var_120], 1
0x140170314  jz      short loc_14017031B
0x140170316  cmp     [rbp+0B0h+var_130], cl
0x140170319  jz      short loc_140170336
0x14017031b  lea     rax, [rbp+0B0h+var_D0]
0x14017031f  mov     qword ptr [rbp+0B0h+var_D0+8], rax
0x140170323  lea     rax, [rbp+0B0h+var_D0]
0x140170327  mov     qword ptr [rbp+0B0h+var_D0], rax
  ... truncated ...
```
