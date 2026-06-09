# WfpNlShimInspectvSwitchForwardDatagram

- ea: `0x14016e238`
- end: `0x14016ea14`
- name: `WfpNlShimInspectvSwitchForwardDatagram`
- size: `2012`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config`

## callers

- `0x1401229e4`

## callees

- `0x14008a760`
- `0x1400ca750`
- `0x1400ca8c0`
- `0x1400efed0`
- `0x14016d748`
- `0x14016d7a0`
- `0x14016d94c`
- `0x14016da20`
- `0x14016dcdc`
- `0x14016e06c`
- `0x14016e1b4`
- `0x14016e238`
- `0x1401bf390`
- `0x1401bf940`

## import_xrefs

- `NETIO!NetioDereferenceNetBufferList` at `0x14016e982`
- `NETIO!NetioDereferenceNetBufferList` at `0x14016e9b4`
- `NETIO!NetioDereferenceNetBufferList` at `0x14016e982`
- `NETIO!NetioDereferenceNetBufferList` at `0x14016e9b4`
- `NETIO!NetioReferenceNetBufferList` at `0x14016e3bf`
- `NETIO!NetioReferenceNetBufferList` at `0x14016e3d6`
- `NETIO!NetioReferenceNetBufferList` at `0x14016e3bf`
- `NETIO!NetioReferenceNetBufferList` at `0x14016e3d6`
- `NETIO!NetioFlowRemoveContext` at `0x14016e5bd`
- `NETIO!NetioFlowRemoveContext` at `0x14016e5bd`
- `NETIO!NetioFlowRetrieveContext` at `0x14016e4ce`
- `NETIO!NetioFlowRetrieveContext` at `0x14016e4ce`
- `NETIO!KfdReleaseCachedFilters` at `0x14016e7ca`
- `NETIO!KfdReleaseCachedFilters` at `0x14016e7ca`
- `NETIO!KfdClassify` at `0x14016e714`
- `NETIO!KfdClassify` at `0x14016e714`
- `NETIO!KfdGetLayerCacheEpoch` at `0x14016e4f8`
- `NETIO!KfdGetLayerCacheEpoch` at `0x14016e4f8`
- `fwpkclnt!FwppvSwitchGetDestinationInterface` at `0x14016e471`
- `fwpkclnt!FwppvSwitchGetDestinationInterface` at `0x14016e882`
- `fwpkclnt!FwppvSwitchGetDestinationInterface` at `0x14016e471`
- `fwpkclnt!FwppvSwitchGetDestinationInterface` at `0x14016e882`
- `fwpkclnt!FwppDereferencevSwitchNblContext` at `0x14016e968`
- `fwpkclnt!FwppDereferencevSwitchNblContext` at `0x14016e9a2`
- `fwpkclnt!FwppDereferencevSwitchNblContext` at `0x14016e968`
- `fwpkclnt!FwppDereferencevSwitchNblContext` at `0x14016e9a2`
- `fwpkclnt!FwppReferencevSwitchNblContext` at `0x14016e39e`
- `fwpkclnt!FwppReferencevSwitchNblContext` at `0x14016e3b0`
- `fwpkclnt!FwppReferencevSwitchNblContext` at `0x14016e3e5`
- `fwpkclnt!FwppReferencevSwitchNblContext` at `0x14016e39e`
- `fwpkclnt!FwppReferencevSwitchNblContext` at `0x14016e3b0`
- `fwpkclnt!FwppReferencevSwitchNblContext` at `0x14016e3e5`
- `fwpkclnt!FwppGetvSwitchNblContext` at `0x14016e33c`
- `fwpkclnt!FwppGetvSwitchNblContext` at `0x14016e932`
- `fwpkclnt!FwppGetvSwitchNblContext` at `0x14016e33c`
- `fwpkclnt!FwppGetvSwitchNblContext` at `0x14016e932`
- `fwpkclnt!FwppNetBufferListAssociateContext` at `0x14016e386`
- `fwpkclnt!FwppNetBufferListAssociateContext` at `0x14016e386`

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
0x14016e238  push    rbp
0x14016e23a  push    rbx
0x14016e23b  push    rsi
0x14016e23c  push    rdi
0x14016e23d  push    r12
0x14016e23f  push    r13
0x14016e241  push    r14
0x14016e243  push    r15
0x14016e245  lea     rbp, [rsp-78h]
0x14016e24a  sub     rsp, 178h
0x14016e251  mov     rax, cs:__security_cookie
0x14016e258  xor     rax, rsp
0x14016e25b  mov     [rbp+0B0h+var_48], rax
0x14016e25f  mov     rax, [rbp+0B0h+arg_38]
0x14016e266  xor     r13b, r13b
0x14016e269  mov     rdi, [rbp+0B0h+arg_30]
0x14016e270  xorps   xmm0, xmm0
0x14016e273  mov     [rbp+0B0h+var_100], rax
0x14016e277  mov     r15d, 1
0x14016e27d  xor     eax, eax
0x14016e27f  mov     [rbp+0B0h+var_E0], r9d
0x14016e283  mov     [rbp+0B0h+var_7C], rax
0x14016e287  mov     ebx, r15d
0x14016e28a  cmp     [rdi+49h], al
0x14016e28d  mov     r14, rdx
0x14016e290  mov     [rbp+0B0h+var_8C], rax
0x14016e294  mov     [rbp+0B0h+var_9C], rax
0x14016e298  mov     [rbp+0B0h+var_AC], rax
0x14016e29c  mov     [rbp+0B0h+var_BC], rax
0x14016e2a0  mov     [rbp+30h], rax
0x14016e2a4  mov     [rbp+20h], rax
0x14016e2a8  mov     [rbp+10h], rax
0x14016e2ac  mov     [rbp+0], rax
0x14016e2b0  mov     [rbp-10h], rax
0x14016e2b4  mov     [rbp+0B0h+var_F0], rax
0x14016e2b8  mov     dword ptr [rbp+0B0h+var_E8], eax
0x14016e2bb  mov     word ptr [rbp+0B0h+var_E8+4], ax
0x14016e2bf  mov     [rbp+0B0h+var_F8], rax
0x14016e2c3  mov     [rbp+0B0h+var_118], rax
0x14016e2c7  mov     [rbp+0B0h+var_12E], al
0x14016e2ca  mov     dword ptr [rbp+0B0h+var_50], eax
0x14016e2cd  mov     eax, r15d
0x14016e2d0  mov     [rbp+0B0h+var_DC], r8d
0x14016e2d4  mov     [rbp+0B0h+var_D8], ecx
0x14016e2d7  mov     [rbp+0B0h+var_124], ebx
0x14016e2da  mov     [rbp+0B0h+var_128], r13d
0x14016e2de  movups  [rbp+0B0h+var_D0], xmm0
0x14016e2e2  mov     [rbp+0B0h+var_12D], r13b
0x14016e2e6  mov     [rbp+0B0h+var_12C], r13b
0x14016e2ea  movups  [rbp+0B0h+var_70], xmm0
0x14016e2ee  movups  [rbp+0B0h+var_60], xmm0
0x14016e2f2  jnz     short loc_14016E2F7
0x14016e2f4  mov     eax, [rdi+0Ch]
0x14016e2f7  mov     [rbp+0B0h+var_120], eax
0x14016e2fa  test    ecx, ecx
0x14016e2fc  jnz     short loc_14016E311
0x14016e2fe  mov     ecx, 4Ch ; 'L'
0x14016e303  cmp     eax, r15d
0x14016e306  lea     r12d, [rcx-2]
0x14016e30a  cmovnz  r12w, cx
0x14016e30f  jmp     short loc_14016E322
0x14016e311  mov     r12d, 4Bh ; 'K'
0x14016e317  cmp     eax, r15d
0x14016e31a  jz      short loc_14016E322
0x14016e31c  mov     r12d, 4Dh ; 'M'
0x14016e322  cmp     byte ptr [rdx+48h], 0
0x14016e326  mov     rsi, [rdx+40h]
0x14016e32a  jz      loc_14016E3D3
0x14016e330  test    rsi, rsi
0x14016e333  jz      loc_14016E3F1
0x14016e339  mov     rcx, rsi
0x14016e33c  call    cs:__imp_FwppGetvSwitchNblContext
0x14016e343  nop     dword ptr [rax+rax+00h]
0x14016e348  xor     ecx, ecx
0x14016e34a  test    rax, rax
0x14016e34d  jnz     short loc_14016E3AD
0x14016e34f  mov     dword ptr [rsp+1B0h+var_168], ecx
0x14016e353  lea     rax, NlShimvSwitchNetBufferListEventNotifyFn
0x14016e35a  mov     [rsp+1B0h+var_170], rax
0x14016e35f  mov     r8d, 0FFFFh
0x14016e365  mov     [rsp+1B0h+var_178], rcx
0x14016e36a  mov     r9, rdi
0x14016e36d  mov     [rsp+1B0h+var_180], rcx
0x14016e372  mov     rdx, rsi
0x14016e375  mov     [rsp+1B0h+var_188], rcx
0x14016e37a  mov     ecx, r15d
0x14016e37d  mov     [rsp+1B0h+var_190], 2
0x14016e386  call    cs:__imp_FwppNetBufferListAssociateContext
0x14016e38d  nop     dword ptr [rax+rax+00h]
0x14016e392  test    rax, rax
0x14016e395  jnz     loc_14016E909
0x14016e39b  mov     rcx, rdi
0x14016e39e  call    cs:__imp_FwppReferencevSwitchNblContext
0x14016e3a5  nop     dword ptr [rax+rax+00h]
0x14016e3aa  mov     rax, rdi
0x14016e3ad  mov     rcx, rax
0x14016e3b0  call    cs:__imp_FwppReferencevSwitchNblContext
0x14016e3b7  nop     dword ptr [rax+rax+00h]
0x14016e3bc  mov     rcx, rsi
0x14016e3bf  call    cs:__imp_NetioReferenceNetBufferList
0x14016e3c6  nop     dword ptr [rax+rax+00h]
0x14016e3cb  mov     rsi, [rsi]
0x14016e3ce  jmp     loc_14016E330
0x14016e3d3  mov     rcx, rsi
0x14016e3d6  call    cs:__imp_NetioReferenceNetBufferList
0x14016e3dd  nop     dword ptr [rax+rax+00h]
0x14016e3e2  mov     rcx, rdi
0x14016e3e5  call    cs:__imp_FwppReferencevSwitchNblContext
0x14016e3ec  nop     dword ptr [rax+rax+00h]
0x14016e3f1  mov     rdx, [rdi+38h]
0x14016e3f5  xor     al, al
0x14016e3f7  xor     r15d, r15d
0x14016e3fa  mov     [rbp+0B0h+var_130], al
0x14016e3fd  xor     r13d, r13d
0x14016e400  xor     esi, esi
0x14016e402  test    rdx, rdx
0x14016e405  jz      short loc_14016E483
0x14016e407  cmp     [rdi+49h], al
0x14016e40a  jnz     short loc_14016E483
0x14016e40c  mov     r10d, [rdx+0Ch]
0x14016e410  mov     r15d, ebx
0x14016e413  mov     r9d, [rdx+8]
0x14016e417  cmp     r10d, ebx
0x14016e41a  setz    [rbp+0B0h+var_130]
0x14016e41e  test    r9d, r9d
0x14016e421  jz      short loc_14016E440
0x14016e423  mov     r11d, [rdx+4]
0x14016e427  mov     r8, [rdx+10h]
0x14016e42b  mov     eax, r11d
0x14016e42e  imul    eax, esi
0x14016e431  test    [rax+r8+6], r15b
0x14016e436  jz      short loc_14016E440
0x14016e438  add     esi, r15d
0x14016e43b  cmp     esi, r9d
0x14016e43e  jb      short loc_14016E42B
0x14016e440  cmp     esi, r10d
0x14016e443  jnz     short loc_14016E456
0x14016e445  mov     r13d, [rbp+0B0h+var_128]
0x14016e449  xor     ebx, ebx
0x14016e44b  mov     [rdi+44h], ebx
0x14016e44e  mov     r12d, r15d
0x14016e451  jmp     loc_14016E90C
0x14016e456  mov     rcx, [rdi+88h]
0x14016e45d  mov     r15d, esi
0x14016e460  imul    r15d, [rdx+4]
0x14016e465  add     r15, [rdx+10h]
0x14016e469  movzx   r8d, word ptr [r15+4]
0x14016e46e  mov     edx, [r15]
0x14016e471  call    cs:__imp_FwppvSwitchGetDestinationInterface
0x14016e478  nop     dword ptr [rax+rax+00h]
0x14016e47d  mov     r13, rax
0x14016e480  mov     al, [rbp+0B0h+var_130]
0x14016e483  cmp     byte ptr [r14+48h], 0
0x14016e488  jnz     loc_14016E5D2
0x14016e48e  cmp     [rbp+0B0h+var_120], ebx
0x14016e491  jz      short loc_14016E49B
0x14016e493  test    al, al
0x14016e495  jz      loc_14016E5D2
0x14016e49b  mov     rax, [rbp+0B0h+var_100]
0x14016e49f  test    rax, rax
0x14016e4a2  jz      loc_14016E5D2
0x14016e4a8  cmp     qword ptr [rax+0C8h], 0
0x14016e4b0  jz      loc_14016E5D2
0x14016e4b6  lea     r9, [rbp+0B0h+var_108]
0x14016e4ba  mov     [rbp+0B0h+var_108], 0
0x14016e4c2  lea     r8, NlShimReferenceFwLayerCache
0x14016e4c9  mov     edx, ebx
0x14016e4cb  mov     rcx, rax
0x14016e4ce  call    cs:__imp_NetioFlowRetrieveContext
0x14016e4d5  nop     dword ptr [rax+rax+00h]
0x14016e4da  test    eax, eax
0x14016e4dc  jnz     loc_14016E5D2
0x14016e4e2  cmp     [rbp+0B0h+var_108], 0
0x14016e4e7  jz      loc_14016E5D2
0x14016e4ed  lea     rdx, [rbp+0B0h+var_110]
0x14016e4f1  mov     [rbp+0B0h+var_110], eax
0x14016e4f4  movzx   ecx, r12w
0x14016e4f8  call    cs:__imp_KfdGetLayerCacheEpoch
0x14016e4ff  nop     dword ptr [rax+rax+00h]
0x14016e504  mov     rax, [rbp+0B0h+var_108]
0x14016e508  mov     ecx, [rbp+0B0h+var_110]
0x14016e50b  cmp     [rax+58h], ecx
0x14016e50e  jnz     loc_14016E5B4
0x14016e514  test    r13, r13
0x14016e517  jz      short loc_14016E522
0x14016e519  mov     ecx, [r13+410h]
0x14016e520  jmp     short loc_14016E524
0x14016e522  xor     ecx, ecx
0x14016e524  cmp     [rax+18h], ecx
0x14016e527  jnz     loc_14016E5AD
0x14016e52d  lea     rcx, [rbp+0B0h+var_124]
0x14016e531  mov     r9, r14
0x14016e534  mov     [rsp+1B0h+var_178], rcx
0x14016e539  mov     r8, rax
0x14016e53c  mov     [rsp+1B0h+var_180], r13
0x14016e541  movzx   edx, r12w
0x14016e545  mov     [rsp+1B0h+var_188], rdi
0x14016e54a  mov     [rsp+1B0h+var_190], 0
0x14016e553  call    NlShimFwLayerDirectClassify
0x14016e558  mov     ebx, [rbp+0B0h+var_124]
0x14016e55b  test    al, al
0x14016e55d  jz      short loc_14016E5AD
0x14016e55f  mov     rdx, [r14+40h]
0x14016e563  mov     ecx, ebx
0x14016e565  call    WfpNlShimCheckIfPacketAbsorbed
0x14016e56a  mov     r13d, [rbp+0B0h+var_128]
0x14016e56e  mov     r12d, 1
0x14016e574  cmp     ebx, r12d
0x14016e577  movzx   r13d, r13b
0x14016e57b  cmovz   r13d, r12d
0x14016e57f  mov     [rbp+0B0h+var_128], r13d
0x14016e583  test    r15, r15
0x14016e586  jz      short loc_14016E59F
0x14016e588  test    ebx, ebx
0x14016e58a  jz      short loc_14016E59F
0x14016e58c  mov     [rdi+40h], r12b
0x14016e590  mov     r8d, esi
0x14016e593  mov     rdx, [r14+40h]
0x14016e597  mov     rcx, rdi
0x14016e59a  call    NlShimExcludeDestinationForNblChain
0x14016e59f  lea     rcx, [rbp+0B0h+var_108]
0x14016e5a3  call    NLShimDereferenceFwLayerCache
0x14016e5a8  jmp     loc_14016E90C
0x14016e5ad  mov     edx, 1
0x14016e5b2  jmp     short loc_14016E5B9
0x14016e5b4  mov     [rax+58h], ecx
0x14016e5b7  mov     edx, ebx
0x14016e5b9  mov     rcx, [rbp+0B0h+var_100]
0x14016e5bd  call    cs:__imp_NetioFlowRemoveContext
0x14016e5c4  nop     dword ptr [rax+rax+00h]
0x14016e5c9  lea     rcx, [rbp+0B0h+var_108]
0x14016e5cd  call    NLShimDereferenceFwLayerCache
0x14016e5d2  lea     r9, [rbp+0B0h+var_12D]
0x14016e5d6  lea     r8, [rbp+0B0h+var_12C]
0x14016e5da  lea     rdx, [rbp+0B0h+var_118]
0x14016e5de  lea     rcx, [rbp+0B0h+var_F8]
0x14016e5e2  call    WfpShimGetStorageForClassifyValues
0x14016e5e7  mov     [rbp+0B0h+var_12E], al
0x14016e5ea  test    al, al
0x14016e5ec  jnz     short loc_14016E600
0x14016e5ee  mov     r13d, [rbp+0B0h+var_128]
0x14016e5f2  mov     r12d, 1
0x14016e5f8  mov     ebx, r12d
0x14016e5fb  jmp     loc_14016E90C
0x14016e600  mov     [rbp+0B0h+var_124], 0
0x14016e607  mov     [rbp+0B0h+var_12F], 0
0x14016e60b  mov     rax, [rbp+0B0h+var_F8]
0x14016e60f  mov     rdx, r14
0x14016e612  mov     r9d, [rbp+0B0h+var_E0]
0x14016e616  mov     r8d, [rbp+0B0h+var_DC]
0x14016e61a  mov     ecx, [rbp+0B0h+var_D8]
0x14016e61d  mov     [rsp+1B0h+var_140], rax
0x14016e622  lea     rax, [rbp+0B0h+var_C0]
0x14016e626  mov     [rsp+1B0h+var_148], rax
0x14016e62b  lea     rax, [rbp+0B0h+var_B0]
0x14016e62f  mov     [rsp+1B0h+var_150], rax
0x14016e634  lea     rax, [rbp+0B0h+var_A0]
0x14016e638  mov     [rsp+1B0h+var_158], rax
0x14016e63d  lea     rax, [rbp+0B0h+var_90]
0x14016e641  mov     [rsp+1B0h+var_160], rax
0x14016e646  lea     rax, [rbp+0B0h+var_80]
0x14016e64a  mov     [rsp+1B0h+var_168], rax
0x14016e64f  mov     eax, [rbp+0B0h+var_120]
0x14016e652  mov     dword ptr [rsp+1B0h+var_170], eax
0x14016e656  movzx   eax, [rbp+0B0h+arg_28]
0x14016e65d  mov     [rsp+1B0h+var_178], r13
0x14016e662  mov     [rsp+1B0h+var_180], rdi
0x14016e667  mov     word ptr [rsp+1B0h+var_188], ax
0x14016e66c  movzx   eax, [rbp+0B0h+arg_20]
0x14016e673  mov     word ptr [rsp+1B0h+var_190], ax
0x14016e678  call    NlShimMarshalvSwitchFwLayerFields
0x14016e67d  mov     rcx, [rbp+0B0h+var_118]; void *
0x14016e681  xor     edx, edx; Val
0x14016e683  mov     dword ptr [rbp+0B0h+var_F0+4], eax
0x14016e686  mov     r8d, 2A8h; Size
0x14016e68c  mov     rax, [rbp+0B0h+var_F8]
0x14016e690  mov     [rbp+0B0h+var_E8], rax
0x14016e694  mov     word ptr [rbp+0B0h+var_F0], r12w
0x14016e699  call    memset
0x14016e69e  mov     r9, [rbp+0B0h+var_118]
0x14016e6a2  mov     rdx, r13
0x14016e6a5  mov     r8b, [rbp+0B0h+var_12F]
0x14016e6a9  mov     rcx, rdi
0x14016e6ac  lea     rax, [r9+270h]
0x14016e6b3  mov     [r9+278h], rax
0x14016e6ba  mov     [rax], rax
0x14016e6bd  call    NlShimSetvSwitchLayerMetadata
0x14016e6c2  xor     ecx, ecx
0x14016e6c4  cmp     [r14+48h], cl
0x14016e6c8  jnz     short loc_14016E6F6
0x14016e6ca  cmp     [rbp+0B0h+var_100], rcx
0x14016e6ce  jz      short loc_14016E6F6
0x14016e6d0  cmp     [rbp+0B0h+var_120], 1
0x14016e6d4  jz      short loc_14016E6DB
0x14016e6d6  cmp     [rbp+0B0h+var_130], cl
0x14016e6d9  jz      short loc_14016E6F6
0x14016e6db  lea     rax, [rbp+0B0h+var_D0]
0x14016e6df  mov     qword ptr [rbp+0B0h+var_D0+8], rax
0x14016e6e3  lea     rax, [rbp+0B0h+var_D0]
0x14016e6e7  mov     qword ptr [rbp+0B0h+var_D0], rax
  ... truncated ...
```
