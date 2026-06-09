# WfpNlShimInspectForwardDatagram

- ea: `0x1400bdf30`
- end: `0x1400be6e2`
- name: `WfpNlShimInspectForwardDatagram`
- size: `1970`
- prototype: ``
- caller_count: `2`
- callee_count: `21`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400287d0`
- `0x14016ebac`

## callees

- `0x14001215c`
- `0x140013140`
- `0x1400143c0`
- `0x140014480`
- `0x140014a90`
- `0x1400aba10`
- `0x1400bd564`
- `0x1400bdf30`
- `0x1400be6e8`
- `0x1400be880`
- `0x1400bfa90`
- `0x140153db4`
- `0x14016e94c`
- `0x14016f388`
- `0x14016f3e0`
- `0x14016f660`
- `0x14016f8a0`
- `0x14017065c`
- `0x1401c0fd0`
- `0x1401c1200`
- `0x1401c1580`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x1400be05e`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400be05e`
- `NETIO!KfdIsLayerEmpty` at `0x1400be385`
- `NETIO!KfdIsLayerEmpty` at `0x1400be385`
- `NETIO!NetioFlowRemoveContext` at `0x1401cfb7a`
- `NETIO!NetioFlowRemoveContext` at `0x1401cfb90`
- `NETIO!NetioFlowRemoveContext` at `0x1401cfb7a`
- `NETIO!NetioFlowRemoveContext` at `0x1401cfb90`
- `NETIO!NetioFlowRetrieveContext` at `0x1400be23d`
- `NETIO!NetioFlowRetrieveContext` at `0x1400be23d`
- `NETIO!KfdReleaseTerminatingFilters` at `0x1400be54c`
- `NETIO!KfdReleaseTerminatingFilters` at `0x1400be54c`
- `NETIO!KfdReleaseCachedFilters` at `0x1400be208`
- `NETIO!KfdReleaseCachedFilters` at `0x1400be496`
- `NETIO!KfdReleaseCachedFilters` at `0x1400be208`
- `NETIO!KfdReleaseCachedFilters` at `0x1400be496`
- `NETIO!KfdClassify` at `0x1400be19d`
- `NETIO!KfdClassify` at `0x1400be465`
- `NETIO!KfdClassify` at `0x1400be19d`
- `NETIO!KfdClassify` at `0x1400be465`
- `NETIO!KfdGetLayerCacheEpoch` at `0x1401cfafd`
- `NETIO!KfdGetLayerCacheEpoch` at `0x1401cfafd`

## pseudocode

```c
__int64 __fastcall WfpNlShimInspectForwardDatagram(unsigned int a1, __int64 a2, __int64 a3, __int64 a4)
{
  unsigned int v4; // r13d
  int v5; // eax
  __int64 v8; // r11
  __int64 v9; // r8
  __int64 *v10; // rbx
  __int64 IsLayerEmpty; // rax
  unsigned __int8 v12; // r12
  _BYTE *v13; // r15
  bool v14; // cf
  char v15; // al
  _BYTE *v16; // r14
  unsigned __int16 v17; // r13
  __int64 v18; // rax
  void *v19; // r12
  bool v20; // zf
  __int64 v21; // rcx
  int v22; // edx
  HANDLE v23; // rcx
  __int64 v25; // rcx
  unsigned __int16 v26; // r12
  __int64 v27; // rax
  _QWORD *v28; // rcx
  __int64 *v29; // rax
  __int64 v30; // rdx
  __int128 v31; // xmm0
  __int128 v32; // xmm1
  __int128 v33; // xmm0
  __int128 v34; // xmm1
  __int128 v35; // xmm0
  __int128 v36; // xmm1
  __int128 v37; // xmm0
  __int128 v38; // xmm1
  __int128 v39; // xmm0
  __int128 v40; // xmm1
  __int64 v41; // rax
  __int64 v42; // rcx
  unsigned int v43; // esi
  int v44; // ecx
  void **v45; // rdi
  _QWORD *v46; // rsi
  char v47; // r15
  _QWORD *v48; // r14
  __int64 v49; // rbx
  unsigned int v50; // r12d
  int v51; // ecx
  int v52; // r11d
  unsigned int v53; // eax
  unsigned int v54; // ecx
  __int64 v55; // rcx
  _QWORD *v56; // rcx
  int v57; // [rsp+20h] [rbp-E0h]
  int v58; // [rsp+28h] [rbp-D8h]
  __int16 v59[2]; // [rsp+40h] [rbp-C0h] BYREF
  char v60; // [rsp+44h] [rbp-BCh]
  unsigned __int8 v61; // [rsp+45h] [rbp-BBh]
  __int64 v62; // [rsp+48h] [rbp-B8h]
  int v63; // [rsp+50h] [rbp-B0h]
  int v64; // [rsp+54h] [rbp-ACh] BYREF
  unsigned int v65; // [rsp+58h] [rbp-A8h]
  unsigned int v66; // [rsp+5Ch] [rbp-A4h] BYREF
  __int64 v67; // [rsp+60h] [rbp-A0h] BYREF
  void *v68; // [rsp+68h] [rbp-98h]
  __int64 v69; // [rsp+70h] [rbp-90h] BYREF
  void *v70; // [rsp+78h] [rbp-88h]
  __int64 v71; // [rsp+80h] [rbp-80h] BYREF
  __int64 v72; // [rsp+88h] [rbp-78h]
  __int64 *v73; // [rsp+90h] [rbp-70h] BYREF
  __int64 *v74; // [rsp+98h] [rbp-68h]
  __int128 v75; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v76[44]; // [rsp+B0h] [rbp-50h] BYREF
  int v77; // [rsp+DCh] [rbp-24h]
  __int128 v78; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v79; // [rsp+F0h] [rbp-10h]
  __int64 v80; // [rsp+100h] [rbp+0h]
  __int128 v81; // [rsp+108h] [rbp+8h] BYREF
  __int128 v82; // [rsp+118h] [rbp+18h]
  int v83; // [rsp+128h] [rbp+28h]
  _QWORD v84[86]; // [rsp+130h] [rbp+30h] BYREF

  v65 = a1;
  v4 = 0;
  v62 = a4;
  v66 = 0;
  v5 = 8;
  v61 = 0;
  v60 = 0;
  v8 = a4;
  if ( a1 )
    LOWORD(v5) = 10;
  v9 = 3;
  v10 = 0;
  v63 = v5;
  HIDWORD(IsLayerEmpty) = 0;
  v74 = 0;
  v12 = 0;
  v67 = 0;
  LODWORD(v68) = 0;
  WORD2(v68) = 0;
  v70 = 0;
  v71 = 0;
  v73 = 0;
  LOBYTE(v59[0]) = 0;
  v80 = 0;
  memset(v76, 0, sizeof(v76));
  v75 = 0;
  v78 = 0;
  v79 = 0;
  if ( (_BYTE)a2 )
  {
    v16 = (_BYTE *)(a3 + 72);
    v13 = (_BYTE *)(a3 + 28);
    goto LABEL_55;
  }
  if ( (gWfpPacketQueue & 2) != 0 && !*(_BYTE *)(a3 + 12) && !*(_BYTE *)(a3 + 72) )
  {
    v23 = qword_14022BEA8;
    if ( (a1 & 0xFFFFFFFB) != 0 )
      v23 = qword_14022BEB8;
    if ( !(unsigned __int8)WfpIsInjectedByHandle(v23, *(_QWORD *)(a3 + 64), 3) && !WfpQueueFwdPacket(a1, a3) )
      return 3;
  }
  v13 = (_BYTE *)(a3 + 28);
  v14 = *(_BYTE *)(a3 + 28) != 0;
  *(_DWORD *)v76 = a1;
  v15 = *(_BYTE *)(a3 + 12);
  v16 = (_BYTE *)(a3 + 72);
  *(_QWORD *)&v76[8] = a3;
  v77 = (*(_BYTE *)(a3 + 72) != 0 ? 0x40 : 0) | (v15 != 0 ? 0x40000 : 0) | (v14 ? 0x80000 : 0);
  NlShimFillFwEdgeInfo(a3, v76, v9);
  if ( v62
    && *(_QWORD *)(v62 + 184)
    && (v69 = 0, !(unsigned int)NetioFlowRetrieveContext(v62, 0, NlShimReferenceFwLayerCache, &v69))
    && v69 )
  {
    v17 = v63;
    v64 = 0;
    KfdGetLayerCacheEpoch((unsigned __int16)v63, &v64);
    if ( *(_DWORD *)(v69 + 88) == v64 )
    {
      if ( (unsigned __int8)NlShimIsFwLayerCacheHit(v69, v76, 0)
        && (unsigned __int8)NlShimFwLayerDirectClassify(
                              v51,
                              (unsigned __int16)v63,
                              v52,
                              a3,
                              (__int64)v76,
                              0,
                              0,
                              (__int64)&v66) )
      {
        IsLayerEmpty = NLShimDereferenceFwLayerCache(&v69);
        v4 = v66;
LABEL_48:
        v8 = v62;
LABEL_54:
        LODWORD(v9) = 3;
        goto LABEL_55;
      }
    }
    else
    {
      *(_DWORD *)(v69 + 88) = v64;
    }
    NetioFlowRemoveContext(v62, 0);
    NetioFlowRemoveContext(v62, 2);
    NLShimDereferenceFwLayerCache(&v69);
  }
  else
  {
    v17 = v63;
  }
  if ( KeGetCurrentIrql() < 2u )
  {
    v18 = WfpRaiseIrqlToDispatchLevel();
    v61 = v18;
    v60 = 1;
  }
  LODWORD(v18) = HIDWORD(KeGetPcr()[1].LockArray);
  if ( !*((_BYTE *)gPerProcessorContext + 72 * v18 + 32) )
  {
    v19 = (void *)*((_QWORD *)gPerProcessorContext + 9 * v18 + 3);
    v10 = (__int64 *)*((_QWORD *)gPerProcessorContext + 9 * v18 + 2);
    *((_BYTE *)gPerProcessorContext + 72 * v18 + 32) = 1;
    goto LABEL_11;
  }
  if ( WfpAllocateFromPerProcessorLookasideList(gIncomingValuesLookasideList, &v71) )
  {
LABEL_79:
    HIDWORD(IsLayerEmpty) = 0;
    LOBYTE(v59[0]) = 0;
    v10 = 0;
    v70 = 0;
    v74 = 0;
    if ( v60 )
      IsLayerEmpty = WfpLowerIrqlFromDispatchLevel(v61);
    v4 = 1;
    goto LABEL_48;
  }
  if ( WfpAllocateFromPerProcessorLookasideList(gMetadataLookasideList, &v73) )
  {
    PplFreeToLookasideList(gIncomingValuesLookasideList);
    goto LABEL_79;
  }
  v19 = (void *)v71;
  v10 = v73;
LABEL_11:
  v74 = v10;
  v70 = v19;
  memset(v19, 0, 0x2A0u);
  memset(v10, 0, 0x2A8u);
  v20 = v65 == 0;
  v10[79] = (__int64)(v10 + 78);
  v10[78] = (__int64)(v10 + 78);
  v21 = 2;
  if ( !v20 )
    LOWORD(v21) = 23;
  HIDWORD(v67) = NlShimMarshalFwLayerFields(v21, v76, v19);
  LOWORD(v67) = v17;
  v68 = v19;
  *(_DWORD *)v10 |= 0x800u;
  v22 = *(_DWORD *)v10;
  *((_DWORD *)v10 + 20) = ***(_DWORD ***)(a3 + 16);
  if ( *(_BYTE *)(a3 + 12) )
  {
    v22 |= 0x100000u;
    *(_DWORD *)v10 = v22;
  }
  if ( *v13 )
    *(_DWORD *)v10 = v22 | 0x200000;
  *((_DWORD *)v10 + 136) = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a3 + 16) + 48LL) + 12LL);
  v20 = v62 == 0;
  v10[69] = *(_QWORD *)(a3 + 16) + 60LL;
  *((_QWORD *)&v75 + 1) = &v75;
  *(_QWORD *)&v75 = &v75;
  if ( !v20 )
    v10[64] = (__int64)&v75;
  IsLayerEmpty = KfdClassify(v17, &v67, v10, *(_QWORD *)(a3 + 64), 0, &v78);
  if ( !(_DWORD)IsLayerEmpty )
  {
    v8 = v62;
    if ( v62 )
    {
      if ( !*((_DWORD *)v10 + 134) )
        goto LABEL_52;
      if ( (int)NlShimCacheMatchedFwLayerFilterList(
                  v62,
                  *((_DWORD *)v10 + 132),
                  (unsigned int)v76,
                  0,
                  v10[64],
                  (__int64)&v67,
                  0) < 0 )
        KfdReleaseCachedFilters(&v75);
      IsLayerEmpty = ((__int64 (__fastcall *)(__int64, _QWORD))qword_14022BF58)(v62, *(_QWORD *)(a3 + 64));
    }
    else
    {
      if ( !*((_DWORD *)v10 + 134) )
        goto LABEL_52;
      IsLayerEmpty = KfdReleaseCachedFilters(&v75);
    }
    v8 = v62;
LABEL_52:
    if ( (_DWORD)v78 != 4097 )
    {
      v12 = 1;
      v4 = 0;
      LOBYTE(v59[0]) = 1;
      goto LABEL_54;
    }
    goto LABEL_35;
  }
  HIDWORD(IsLayerEmpty) = 0;
  v78 = 0;
  LODWORD(v78) = 4097;
  v79 = 0;
  v80 = 0;
LABEL_35:
  if ( (BYTE12(v79) & 1) == 0 )
  {
    v25 = (unsigned __int16)v63;
    v10[64] = 0;
    v4 = 1;
    v73 = *(__int64 **)(a3 + 64);
    v72 = v79;
    v59[0] = 0;
    v71 = 2;
    DetermineDiscardLayerId(v25, v59);
    v26 = v59[0];
    v66 = v80;
    v83 = 0;
    v81 = 0;
    v82 = 0;
    memset(v84, 0, 0x2A8u);
    if ( v73 )
      v27 = v73[31] & 0x7FFFFFFFFFFFFFFFLL;
    else
      v27 = v10[63];
    IndicateDropAudit((unsigned __int16)v63, (unsigned int)&v67, (_DWORD)v10, (unsigned int)&v71, v27);
    if ( (v66 & 0x10000000) != 0 )
      IndicateVetoAudit((unsigned __int16)v63, &v67, v84, &v71);
    IsLayerEmpty = KfdIsLayerEmpty(v26);
    if ( !(_DWORD)IsLayerEmpty )
    {
      LODWORD(v81) = 4097;
      *((_QWORD *)&v81 + 1) = 0;
      *(_QWORD *)&v82 = 0;
      if ( v10 )
      {
        *((_DWORD *)v10 + 1) &= ~1u;
        v28 = v84;
        v29 = v10;
        v30 = 5;
        do
        {
          v28 += 16;
          v31 = *(_OWORD *)v29;
          v32 = *((_OWORD *)v29 + 1);
          v29 += 16;
          *((_OWORD *)v28 - 8) = v31;
          v33 = *((_OWORD *)v29 - 6);
          *((_OWORD *)v28 - 7) = v32;
          v34 = *((_OWORD *)v29 - 5);
          *((_OWORD *)v28 - 6) = v33;
          v35 = *((_OWORD *)v29 - 4);
          *((_OWORD *)v28 - 5) = v34;
          v36 = *((_OWORD *)v29 - 3);
          *((_OWORD *)v28 - 4) = v35;
          v37 = *((_OWORD *)v29 - 2);
          *((_OWORD *)v28 - 3) = v36;
          v38 = *((_OWORD *)v29 - 1);
          *((_OWORD *)v28 - 2) = v37;
          *((_OWORD *)v28 - 1) = v38;
          --v30;
        }
        while ( v30 );
        v39 = *(_OWORD *)v29;
        v40 = *((_OWORD *)v29 + 1);
        v41 = v29[4];
        *(_OWORD *)v28 = v39;
        *((_OWORD *)v28 + 1) = v40;
        v28[4] = v41;
      }
      LODWORD(v84[0]) |= 1u;
      v84[2] = v71;
      v84[3] = v72;
      LOWORD(v67) = v26;
      IsLayerEmpty = KfdClassify(v26, &v67, v84, v73, 0, &v81);
      if ( (_DWORD)IsLayerEmpty )
        IsLayerEmpty = WfpReportSysErrorAsNtStatus(v42, "KfdClassify", (unsigned int)IsLayerEmpty);
    }
    v12 = 1;
    LOBYTE(v59[0]) = 1;
    goto LABEL_48;
  }
  v8 = v62;
  LODWORD(v9) = 3;
  v12 = 1;
  v4 = 3;
  LOBYTE(v59[0]) = 1;
LABEL_55:
  if ( *v16 )
  {
    v46 = *(_QWORD **)(a3 + 64);
    if ( v4 == 3 )
    {
      for ( IsLayerEmpty = *(_QWORD *)(a3 + 64); v46; IsLayerEmpty = (__int64)v46 )
      {
        v46 = (_QWORD *)*v46;
        *(_DWORD *)(IsLayerEmpty + 136) &= ~0x800000u;
      }
    }
    else
    {
      v64 = v4;
      LODWORD(v9) = v4;
      v47 = 1;
      v48 = v46;
      if ( v46 )
      {
        v49 = v62;
        v50 = v65;
        do
        {
          v46 = (_QWORD *)*v46;
          *v48 = 0;
          if ( !qword_14022BF48 || v4 )
          {
            v54 = v4;
          }
          else
          {
            LOBYTE(v58) = *(_BYTE *)(a3 + 12);
            LOBYTE(v57) = 0;
            LOBYTE(a2) = 1;
            v53 = ((__int64 (__fastcall *)(_QWORD, __int64, __int64, _QWORD *, int, int))qword_14022BF48)(
                    v50,
                    a2,
                    v49,
                    v48,
                    v57,
                    v58);
            LODWORD(v9) = v64;
            v54 = v53;
          }
          IsLayerEmpty = v54;
          if ( !v47 )
            IsLayerEmpty = (unsigned int)v9;
          v47 = 0;
          v64 = IsLayerEmpty;
          LODWORD(v9) = IsLayerEmpty;
          if ( (_DWORD)IsLayerEmpty != v54 )
          {
            v4 = 1;
            LODWORD(v9) = 1;
            v64 = 1;
          }
          *((_DWORD *)v48 + 34) &= ~0x800000u;
          v48 = v46;
        }
        while ( v46 );
        v10 = v74;
        v12 = v59[0];
      }
    }
    v43 = v65;
    v4 = v9;
  }
  else
  {
    if ( v4 )
      goto LABEL_62;
    v43 = v65;
    if ( !qword_14022BF48 )
      goto LABEL_60;
    LOBYTE(v58) = *(_BYTE *)(a3 + 12);
    LOBYTE(v57) = *v13;
    IsLayerEmpty = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64, _QWORD, int, int))qword_14022BF48)(
                     v65,
                     0,
                     v8,
                     *(_QWORD *)(a3 + 64),
                     v57,
                     v58);
    v4 = IsLayerEmpty;
  }
  if ( !v4 )
  {
LABEL_60:
    if ( (BYTE8(v79) & 1) != 0 )
    {
      IsLayerEmpty = *(_QWORD *)(a3 + 64);
      v44 = *(_DWORD *)(IsLayerEmpty + 136);
      if ( (v44 & 0x4000000) != 0 && (v44 & 0x8000000) == 0 && !*(_BYTE *)(a3 + 28) )
      {
        v55 = *(_QWORD *)(a3 + 16);
        if ( !v55 )
          goto LABEL_113;
        if ( *(_DWORD *)(*(_QWORD *)(v55 + 48) + 12LL) != 23 )
          goto LABEL_113;
        v56 = (_QWORD *)(v55 + 60);
        if ( !v56 )
          goto LABEL_113;
        IsLayerEmpty = *v56 - RasInterfaceGuid;
        if ( *v56 == RasInterfaceGuid )
          IsLayerEmpty = v56[1] + 0x425BEAF79FFF0B46LL;
        if ( IsLayerEmpty )
        {
LABEL_113:
          IsLayerEmpty = WfpNlShimLogShimPacketDrop(v12, v43, a3, (unsigned int)&v67, (__int64)v10, v63);
          v4 = 1;
        }
      }
    }
  }
LABEL_62:
  if ( v12 )
  {
    LODWORD(IsLayerEmpty) = HIDWORD(KeGetPcr()[1].LockArray);
    v45 = (void **)((char *)gPerProcessorContext + 72 * IsLayerEmpty);
    KfdReleaseTerminatingFilters(v10 + 78);
    if ( v70 == v45[3] )
    {
      *((_BYTE *)v45 + 32) = 0;
    }
    else
    {
      PplFreeToLookasideList(gMetadataLookasideList);
      PplFreeToLookasideList(gIncomingValuesLookasideList);
    }
    if ( v60 )
      WfpLowerIrqlFromDispatchLevel(v61);
  }
  return v4;
}

```

## disassembly

```asm
0x1400bdf30  mov     [rsp-8+arg_8], rbx
0x1400bdf35  push    rbp
0x1400bdf36  push    rsi
0x1400bdf37  push    rdi
0x1400bdf38  push    r12
0x1400bdf3a  push    r13
0x1400bdf3c  push    r14
0x1400bdf3e  push    r15
0x1400bdf40  lea     rbp, [rsp-2F0h]
0x1400bdf48  sub     rsp, 3F0h
0x1400bdf4f  mov     rax, cs:__security_cookie
0x1400bdf56  xor     rax, rsp
0x1400bdf59  mov     [rbp+320h+var_40], rax
0x1400bdf60  xorps   xmm0, xmm0
0x1400bdf63  mov     [rsp+420h+var_3C8], ecx
0x1400bdf67  xor     r13d, r13d
0x1400bdf6a  mov     [rsp+420h+var_3D8], r9
0x1400bdf6f  xor     eax, eax
0x1400bdf71  mov     [rsp+420h+var_3C4], r13d
0x1400bdf76  mov     eax, 8
0x1400bdf7b  mov     [rsp+420h+var_3DB], r13b
0x1400bdf80  mov     r14d, ecx
0x1400bdf83  mov     [rsp+420h+var_3DC], r13b
0x1400bdf88  test    r14d, r14d
0x1400bdf8b  mov     ecx, 0Ah
0x1400bdf90  mov     rdi, r8
0x1400bdf93  mov     r11, r9
0x1400bdf96  cmovnz  ax, cx
0x1400bdf9a  mov     r8d, 3
0x1400bdfa0  xor     ebx, ebx
0x1400bdfa2  mov     [rsp+420h+var_3D0], eax
0x1400bdfa6  xor     eax, eax
0x1400bdfa8  mov     [rbp+320h+var_388], rbx
0x1400bdfac  xor     r12b, r12b
0x1400bdfaf  mov     [rsp+420h+var_3C0], rax
0x1400bdfb4  mov     dword ptr [rsp+420h+var_3B8], eax
0x1400bdfb8  mov     word ptr [rsp+420h+var_3B8+4], ax
0x1400bdfbd  mov     [rsp+420h+var_3A8], rax
0x1400bdfc2  mov     [rbp+320h+var_3A0], rax
0x1400bdfc6  mov     [rbp+320h+var_390], rbx
0x1400bdfca  mov     byte ptr [rsp+420h+var_3E0], r12b
0x1400bdfcf  mov     [rbp+320h+var_320], rax
0x1400bdfd3  movups  xmmword ptr [rbp+320h+var_360], xmm0
0x1400bdfd7  movups  [rbp+320h+var_370], xmm0
0x1400bdfdb  movups  xmmword ptr [rbp+320h+var_360+0Ch], xmm0
0x1400bdfdf  movups  [rbp+320h+var_380], xmm0
0x1400bdfe3  movups  [rbp+320h+var_340], xmm0
0x1400bdfe7  movups  [rbp+320h+var_330], xmm0
0x1400bdfeb  test    dl, dl
0x1400bdfed  jnz     loc_1400BE5A6
0x1400bdff3  mov     eax, cs:gWfpPacketQueue
0x1400bdff9  test    al, 2
0x1400bdffb  jnz     loc_1400BE256
0x1400be001  movzx   eax, byte ptr [rdi+1Ch]
0x1400be005  lea     r15, [rdi+1Ch]
0x1400be009  neg     al
0x1400be00b  mov     dword ptr [rbp+320h+var_370], r14d
0x1400be00f  movzx   eax, byte ptr [rdi+0Ch]
0x1400be013  lea     r14, [rdi+48h]
0x1400be017  sbb     edx, edx
0x1400be019  mov     qword ptr [rbp+320h+var_370+8], rdi
0x1400be01d  and     edx, 80000h
0x1400be023  neg     al
0x1400be025  movzx   eax, byte ptr [r14]
0x1400be029  sbb     ecx, ecx
0x1400be02b  and     ecx, 40000h
0x1400be031  or      edx, ecx
0x1400be033  neg     al
0x1400be035  sbb     ecx, ecx
0x1400be037  and     ecx, 40h
0x1400be03a  or      edx, ecx
0x1400be03c  mov     rcx, rdi
0x1400be03f  mov     [rbp+320h+var_344], edx
0x1400be042  lea     rdx, [rbp+320h+var_370]
0x1400be046  call    NlShimFillFwEdgeInfo
0x1400be04b  mov     rax, [rsp+420h+var_3D8]
0x1400be050  test    rax, rax
0x1400be053  jnz     loc_1400BE21A
0x1400be059  mov     r13d, [rsp+420h+var_3D0]
0x1400be05e  call    cs:__imp_KeGetCurrentIrql
0x1400be065  nop     dword ptr [rax+rax+00h]
0x1400be06a  cmp     al, 2
0x1400be06c  jnb     short loc_1400BE07C
0x1400be06e  call    WfpRaiseIrqlToDispatchLevel
0x1400be073  mov     [rsp+420h+var_3DB], al
0x1400be077  mov     [rsp+420h+var_3DC], 1
0x1400be07c  mov     eax, gs:1A4h
0x1400be084  lea     rdx, [rax+rax*8]
0x1400be088  mov     rax, cs:gPerProcessorContext
0x1400be08f  cmp     [rax+rdx*8+20h], bl
0x1400be093  jnz     loc_1400BE5D3
0x1400be099  mov     r12, [rax+rdx*8+18h]
0x1400be09e  mov     rbx, [rax+rdx*8+10h]
0x1400be0a3  mov     byte ptr [rax+rdx*8+20h], 1
0x1400be0a8  xor     edx, edx; Val
0x1400be0aa  mov     [rbp+320h+var_388], rbx
0x1400be0ae  mov     r8d, 2A0h; Size
0x1400be0b4  mov     [rsp+420h+var_3A8], r12
0x1400be0b9  mov     rcx, r12; void *
0x1400be0bc  call    memset
0x1400be0c1  xor     edx, edx; Val
0x1400be0c3  mov     r8d, 2A8h; Size
0x1400be0c9  mov     rcx, rbx; void *
0x1400be0cc  call    memset
0x1400be0d1  cmp     [rsp+420h+var_3C8], 0
0x1400be0d6  lea     rax, [rbx+270h]
0x1400be0dd  mov     [rax+8], rax
0x1400be0e1  lea     rdx, [rbp+320h+var_370]
0x1400be0e5  mov     [rax], rax
0x1400be0e8  mov     ecx, 2
0x1400be0ed  mov     eax, 17h
0x1400be0f2  mov     r8, r12
0x1400be0f5  cmovnz  cx, ax
0x1400be0f9  call    NlShimMarshalFwLayerFields
0x1400be0fe  mov     dword ptr [rsp+420h+var_3C0+4], eax
0x1400be102  mov     word ptr [rsp+420h+var_3C0], r13w
0x1400be108  mov     [rsp+420h+var_3B8], r12
0x1400be10d  or      dword ptr [rbx], 800h
0x1400be113  mov     rax, [rdi+10h]
0x1400be117  mov     edx, [rbx]
0x1400be119  mov     rcx, [rax]
0x1400be11c  mov     eax, [rcx]
0x1400be11e  mov     [rbx+50h], eax
0x1400be121  cmp     byte ptr [rdi+0Ch], 0
0x1400be125  jz      short loc_1400BE12D
0x1400be127  bts     edx, 14h
0x1400be12b  mov     [rbx], edx
0x1400be12d  cmp     byte ptr [r15], 0
0x1400be131  jz      short loc_1400BE139
0x1400be133  bts     edx, 15h
0x1400be137  mov     [rbx], edx
0x1400be139  mov     rax, [rdi+10h]
0x1400be13d  mov     rcx, [rax+30h]
0x1400be141  mov     eax, [rcx+0Ch]
0x1400be144  mov     [rbx+220h], eax
0x1400be14a  mov     rax, [rdi+10h]
0x1400be14e  add     rax, 3Ch ; '<'
0x1400be152  cmp     [rsp+420h+var_3D8], 0
0x1400be158  mov     [rbx+228h], rax
0x1400be15f  lea     rax, [rbp+320h+var_380]
0x1400be163  mov     qword ptr [rbp+320h+var_380+8], rax
0x1400be167  lea     rax, [rbp+320h+var_380]
0x1400be16b  mov     qword ptr [rbp+320h+var_380], rax
0x1400be16f  jz      short loc_1400BE17C
0x1400be171  lea     rax, [rbp+320h+var_380]
0x1400be175  mov     [rbx+200h], rax
0x1400be17c  mov     r9, [rdi+40h]
0x1400be180  lea     rax, [rbp+320h+var_340]
0x1400be184  mov     [rsp+420h+var_3F8], rax
0x1400be189  lea     rdx, [rsp+420h+var_3C0]
0x1400be18e  xor     r12d, r12d
0x1400be191  mov     r8, rbx
0x1400be194  movzx   ecx, r13w
0x1400be198  mov     [rsp+420h+var_400], r12
0x1400be19d  call    cs:__imp_KfdClassify
0x1400be1a4  nop     dword ptr [rax+rax+00h]
0x1400be1a9  test    eax, eax
0x1400be1ab  jnz     loc_1400BE2AD
0x1400be1b1  mov     r11, [rsp+420h+var_3D8]
0x1400be1b6  test    r11, r11
0x1400be1b9  jz      loc_1400BE489
0x1400be1bf  cmp     [rbx+218h], r12d
0x1400be1c6  jz      loc_1400BE4A7
0x1400be1cc  mov     edx, [rbx+210h]
0x1400be1d2  lea     rax, [rsp+420h+var_3C0]
0x1400be1d7  mov     byte ptr [rsp+420h+var_3F0], r12b
0x1400be1dc  lea     r8, [rbp+320h+var_370]
0x1400be1e0  mov     [rsp+420h+var_3F8], rax
0x1400be1e5  xor     r9d, r9d
0x1400be1e8  mov     rax, [rbx+200h]
0x1400be1ef  mov     rcx, r11
0x1400be1f2  mov     [rsp+420h+var_400], rax
0x1400be1f7  call    NlShimCacheMatchedFwLayerFilterList
0x1400be1fc  test    eax, eax
0x1400be1fe  jns     loc_1401CFBAC
0x1400be204  lea     rcx, [rbp+320h+var_380]
0x1400be208  call    cs:__imp_KfdReleaseCachedFilters
0x1400be20f  nop     dword ptr [rax+rax+00h]
0x1400be214  nop
0x1400be215  jmp     loc_1401CFBAC
0x1400be21a  cmp     [rax+0B8h], rbx
0x1400be221  jz      loc_1400BE059
0x1400be227  lea     r9, [rsp+420h+var_3B0]
0x1400be22c  mov     [rsp+420h+var_3B0], rbx
0x1400be231  lea     r8, NlShimReferenceFwLayerCache
0x1400be238  xor     edx, edx
0x1400be23a  mov     rcx, rax
0x1400be23d  call    cs:__imp_NetioFlowRetrieveContext
0x1400be244  nop     dword ptr [rax+rax+00h]
0x1400be249  test    eax, eax
0x1400be24b  jnz     loc_1400BE059
0x1400be251  jmp     loc_1401CFAE0
0x1400be256  cmp     [rdi+0Ch], bl
0x1400be259  jnz     loc_1400BE001
0x1400be25f  cmp     [rdi+48h], bl
0x1400be262  jnz     loc_1400BE001
0x1400be268  mov     rcx, cs:qword_14022BEA8
0x1400be26f  test    r14d, 0FFFFFFFBh
0x1400be276  mov     rdx, [rdi+40h]
0x1400be27a  cmovnz  rcx, cs:qword_14022BEB8
0x1400be282  call    WfpIsInjectedByHandle
0x1400be287  test    al, al
0x1400be289  jnz     loc_1400BE001
0x1400be28f  mov     rdx, rdi
0x1400be292  mov     ecx, r14d
0x1400be295  call    WfpQueueFwdPacket
0x1400be29a  test    rax, rax
0x1400be29d  jnz     loc_1400BE001
0x1400be2a3  mov     eax, 3
0x1400be2a8  jmp     loc_1400BE57B
0x1400be2ad  xorps   xmm0, xmm0
0x1400be2b0  xor     eax, eax
0x1400be2b2  movups  [rbp+320h+var_340], xmm0
0x1400be2b6  mov     dword ptr [rbp+320h+var_340], 1001h
0x1400be2bd  movups  [rbp+320h+var_330], xmm0
0x1400be2c1  mov     [rbp+320h+var_320], rax
0x1400be2c5  test    byte ptr [rbp+320h+var_330+0Ch], 1
0x1400be2c9  jnz     loc_1400BE60E
0x1400be2cf  movzx   ecx, word ptr [rsp+420h+var_3D0]
0x1400be2d4  lea     rdx, [rsp+420h+var_3E0]
0x1400be2d9  mov     [rbx+200h], r12
0x1400be2e0  mov     r13d, 1
0x1400be2e6  mov     r9, [rdi+40h]
0x1400be2ea  mov     rax, qword ptr [rbp+320h+var_330]
0x1400be2ee  mov     [rbp+320h+var_390], r9
0x1400be2f2  mov     [rbp+320h+var_398], rax
0x1400be2f6  mov     [rsp+420h+var_3E0], r12w
0x1400be2fc  mov     [rbp+320h+var_3A0], 2
0x1400be304  call    DetermineDiscardLayerId
0x1400be309  mov     eax, dword ptr [rbp+320h+var_320]
0x1400be30c  lea     rcx, [rbp+320h+var_2F0]; void *
0x1400be310  movzx   r12d, [rsp+420h+var_3E0]
0x1400be316  xorps   xmm0, xmm0
0x1400be319  mov     [rsp+420h+var_3C4], eax
0x1400be31d  xor     edx, edx; Val
0x1400be31f  xor     eax, eax
0x1400be321  mov     r8d, 2A8h; Size
0x1400be327  mov     [rbp+320h+var_2F8], eax
0x1400be32a  movups  [rbp+320h+var_318], xmm0
0x1400be32e  movups  [rbp+320h+var_308], xmm0
0x1400be332  call    memset
0x1400be337  mov     rax, [rbp+320h+var_390]
0x1400be33b  test    rax, rax
0x1400be33e  jz      loc_1400BE629
0x1400be344  mov     rax, [rax+0F8h]
0x1400be34b  mov     rcx, 7FFFFFFFFFFFFFFFh
0x1400be355  and     rax, rcx
0x1400be358  movzx   ecx, word ptr [rsp+420h+var_3D0]
0x1400be35d  lea     r9, [rbp+320h+var_3A0]
0x1400be361  mov     r8, rbx
0x1400be364  mov     [rsp+420h+var_400], rax
0x1400be369  lea     rdx, [rsp+420h+var_3C0]
0x1400be36e  call    IndicateDropAudit
0x1400be373  test    [rsp+420h+var_3C4], 10000000h
0x1400be37b  jnz     loc_1400BE6A0
0x1400be381  movzx   ecx, r12w
0x1400be385  call    cs:__imp_KfdIsLayerEmpty
0x1400be38c  nop     dword ptr [rax+rax+00h]
0x1400be391  test    eax, eax
0x1400be393  jnz     loc_1400BE479
0x1400be399  xor     r8d, r8d
0x1400be39c  mov     dword ptr [rbp+320h+var_318], 1001h
0x1400be3a3  mov     qword ptr [rbp+320h+var_318+8], r8
0x1400be3a7  mov     qword ptr [rbp+320h+var_308], r8
0x1400be3ab  test    rbx, rbx
0x1400be3ae  jz      short loc_1400BE428
0x1400be3b0  and     dword ptr [rbx+4], 0FFFFFFFEh
0x1400be3b4  lea     rcx, [rbp+320h+var_2F0]
0x1400be3b8  mov     rax, rbx
0x1400be3bb  mov     edx, 5
0x1400be3c0  lea     rcx, [rcx+80h]
0x1400be3c7  movups  xmm0, xmmword ptr [rax]
0x1400be3ca  movups  xmm1, xmmword ptr [rax+10h]
0x1400be3ce  lea     rax, [rax+80h]
0x1400be3d5  movups  xmmword ptr [rcx-80h], xmm0
0x1400be3d9  movups  xmm0, xmmword ptr [rax-60h]
0x1400be3dd  movups  xmmword ptr [rcx-70h], xmm1
0x1400be3e1  movups  xmm1, xmmword ptr [rax-50h]
0x1400be3e5  movups  xmmword ptr [rcx-60h], xmm0
0x1400be3e9  movups  xmm0, xmmword ptr [rax-40h]
0x1400be3ed  movups  xmmword ptr [rcx-50h], xmm1
0x1400be3f1  movups  xmm1, xmmword ptr [rax-30h]
0x1400be3f5  movups  xmmword ptr [rcx-40h], xmm0
0x1400be3f9  movups  xmm0, xmmword ptr [rax-20h]
0x1400be3fd  movups  xmmword ptr [rcx-30h], xmm1
0x1400be401  movups  xmm1, xmmword ptr [rax-10h]
0x1400be405  movups  xmmword ptr [rcx-20h], xmm0
0x1400be409  movups  xmmword ptr [rcx-10h], xmm1
0x1400be40d  sub     rdx, r13
0x1400be410  jnz     short loc_1400BE3C0
0x1400be412  movups  xmm0, xmmword ptr [rax]
0x1400be415  movups  xmm1, xmmword ptr [rax+10h]
0x1400be419  mov     rax, [rax+20h]
0x1400be41d  movups  xmmword ptr [rcx], xmm0
0x1400be420  movups  xmmword ptr [rcx+10h], xmm1
0x1400be424  mov     [rcx+20h], rax
0x1400be428  mov     eax, dword ptr [rbp+320h+var_3A0]
0x1400be42b  lea     rdx, [rsp+420h+var_3C0]
0x1400be430  mov     r9, [rbp+320h+var_390]
0x1400be434  movzx   ecx, r12w
  ... truncated ...
```
