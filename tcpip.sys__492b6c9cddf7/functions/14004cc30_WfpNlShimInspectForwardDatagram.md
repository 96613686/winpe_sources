# WfpNlShimInspectForwardDatagram

- ea: `0x14004cc30`
- end: `0x14004d3e2`
- name: `WfpNlShimInspectForwardDatagram`
- size: `1970`
- prototype: ``
- caller_count: `2`
- callee_count: `21`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14004c5e0`
- `0x14016cf6c`

## callees

- `0x14004ca20`
- `0x14004cc30`
- `0x14004d3e8`
- `0x14004d580`
- `0x1400515e8`
- `0x1400525d0`
- `0x140053850`
- `0x140053910`
- `0x140053f20`
- `0x140088940`
- `0x140135c9c`
- `0x140151d9c`
- `0x14016cd0c`
- `0x14016d748`
- `0x14016d7a0`
- `0x14016da20`
- `0x14016dc60`
- `0x14016ea1c`
- `0x1401bf390`
- `0x1401bf5c0`
- `0x1401bf940`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x14004cd5e`
- `ntoskrnl!KeGetCurrentIrql` at `0x14004cd5e`
- `NETIO!KfdIsLayerEmpty` at `0x14004d085`
- `NETIO!KfdIsLayerEmpty` at `0x14004d085`
- `NETIO!NetioFlowRemoveContext` at `0x1401c3ce0`
- `NETIO!NetioFlowRemoveContext` at `0x1401c3cf6`
- `NETIO!NetioFlowRemoveContext` at `0x1401c3ce0`
- `NETIO!NetioFlowRemoveContext` at `0x1401c3cf6`
- `NETIO!NetioFlowRetrieveContext` at `0x14004cf3d`
- `NETIO!NetioFlowRetrieveContext` at `0x14004cf3d`
- `NETIO!KfdReleaseTerminatingFilters` at `0x14004d24c`
- `NETIO!KfdReleaseTerminatingFilters` at `0x14004d24c`
- `NETIO!KfdReleaseCachedFilters` at `0x14004cf08`
- `NETIO!KfdReleaseCachedFilters` at `0x14004d196`
- `NETIO!KfdReleaseCachedFilters` at `0x14004cf08`
- `NETIO!KfdReleaseCachedFilters` at `0x14004d196`
- `NETIO!KfdClassify` at `0x14004ce9d`
- `NETIO!KfdClassify` at `0x14004d165`
- `NETIO!KfdClassify` at `0x14004ce9d`
- `NETIO!KfdClassify` at `0x14004d165`
- `NETIO!KfdGetLayerCacheEpoch` at `0x1401c3c63`
- `NETIO!KfdGetLayerCacheEpoch` at `0x1401c3c63`

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
    v23 = qword_140227E88;
    if ( (a1 & 0xFFFFFFFB) != 0 )
      v23 = qword_140227E98;
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
      IsLayerEmpty = ((__int64 (__fastcall *)(__int64, _QWORD))qword_140227F38)(v62, *(_QWORD *)(a3 + 64));
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
          if ( !qword_140227F28 || v4 )
          {
            v54 = v4;
          }
          else
          {
            LOBYTE(v58) = *(_BYTE *)(a3 + 12);
            LOBYTE(v57) = 0;
            LOBYTE(a2) = 1;
            v53 = ((__int64 (__fastcall *)(_QWORD, __int64, __int64, _QWORD *, int, int))qword_140227F28)(
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
    if ( !qword_140227F28 )
      goto LABEL_60;
    LOBYTE(v58) = *(_BYTE *)(a3 + 12);
    LOBYTE(v57) = *v13;
    IsLayerEmpty = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64, _QWORD, int, int))qword_140227F28)(
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
0x14004cc30  mov     [rsp-8+arg_8], rbx
0x14004cc35  push    rbp
0x14004cc36  push    rsi
0x14004cc37  push    rdi
0x14004cc38  push    r12
0x14004cc3a  push    r13
0x14004cc3c  push    r14
0x14004cc3e  push    r15
0x14004cc40  lea     rbp, [rsp-2F0h]
0x14004cc48  sub     rsp, 3F0h
0x14004cc4f  mov     rax, cs:__security_cookie
0x14004cc56  xor     rax, rsp
0x14004cc59  mov     [rbp+320h+var_40], rax
0x14004cc60  xorps   xmm0, xmm0
0x14004cc63  mov     [rsp+420h+var_3C8], ecx
0x14004cc67  xor     r13d, r13d
0x14004cc6a  mov     [rsp+420h+var_3D8], r9
0x14004cc6f  xor     eax, eax
0x14004cc71  mov     [rsp+420h+var_3C4], r13d
0x14004cc76  mov     eax, 8
0x14004cc7b  mov     [rsp+420h+var_3DB], r13b
0x14004cc80  mov     r14d, ecx
0x14004cc83  mov     [rsp+420h+var_3DC], r13b
0x14004cc88  test    r14d, r14d
0x14004cc8b  mov     ecx, 0Ah
0x14004cc90  mov     rdi, r8
0x14004cc93  mov     r11, r9
0x14004cc96  cmovnz  ax, cx
0x14004cc9a  mov     r8d, 3
0x14004cca0  xor     ebx, ebx
0x14004cca2  mov     [rsp+420h+var_3D0], eax
0x14004cca6  xor     eax, eax
0x14004cca8  mov     [rbp+320h+var_388], rbx
0x14004ccac  xor     r12b, r12b
0x14004ccaf  mov     [rsp+420h+var_3C0], rax
0x14004ccb4  mov     dword ptr [rsp+420h+var_3B8], eax
0x14004ccb8  mov     word ptr [rsp+420h+var_3B8+4], ax
0x14004ccbd  mov     [rsp+420h+var_3A8], rax
0x14004ccc2  mov     [rbp+320h+var_3A0], rax
0x14004ccc6  mov     [rbp+320h+var_390], rbx
0x14004ccca  mov     byte ptr [rsp+420h+var_3E0], r12b
0x14004cccf  mov     [rbp+320h+var_320], rax
0x14004ccd3  movups  xmmword ptr [rbp+320h+var_360], xmm0
0x14004ccd7  movups  [rbp+320h+var_370], xmm0
0x14004ccdb  movups  xmmword ptr [rbp+320h+var_360+0Ch], xmm0
0x14004ccdf  movups  [rbp+320h+var_380], xmm0
0x14004cce3  movups  [rbp+320h+var_340], xmm0
0x14004cce7  movups  [rbp+320h+var_330], xmm0
0x14004cceb  test    dl, dl
0x14004cced  jnz     loc_14004D2A6
0x14004ccf3  mov     eax, cs:gWfpPacketQueue
0x14004ccf9  test    al, 2
0x14004ccfb  jnz     loc_14004CF56
0x14004cd01  movzx   eax, byte ptr [rdi+1Ch]
0x14004cd05  lea     r15, [rdi+1Ch]
0x14004cd09  neg     al
0x14004cd0b  mov     dword ptr [rbp+320h+var_370], r14d
0x14004cd0f  movzx   eax, byte ptr [rdi+0Ch]
0x14004cd13  lea     r14, [rdi+48h]
0x14004cd17  sbb     edx, edx
0x14004cd19  mov     qword ptr [rbp+320h+var_370+8], rdi
0x14004cd1d  and     edx, 80000h
0x14004cd23  neg     al
0x14004cd25  movzx   eax, byte ptr [r14]
0x14004cd29  sbb     ecx, ecx
0x14004cd2b  and     ecx, 40000h
0x14004cd31  or      edx, ecx
0x14004cd33  neg     al
0x14004cd35  sbb     ecx, ecx
0x14004cd37  and     ecx, 40h
0x14004cd3a  or      edx, ecx
0x14004cd3c  mov     rcx, rdi
0x14004cd3f  mov     [rbp+320h+var_344], edx
0x14004cd42  lea     rdx, [rbp+320h+var_370]
0x14004cd46  call    NlShimFillFwEdgeInfo
0x14004cd4b  mov     rax, [rsp+420h+var_3D8]
0x14004cd50  test    rax, rax
0x14004cd53  jnz     loc_14004CF1A
0x14004cd59  mov     r13d, [rsp+420h+var_3D0]
0x14004cd5e  call    cs:__imp_KeGetCurrentIrql
0x14004cd65  nop     dword ptr [rax+rax+00h]
0x14004cd6a  cmp     al, 2
0x14004cd6c  jnb     short loc_14004CD7C
0x14004cd6e  call    WfpRaiseIrqlToDispatchLevel
0x14004cd73  mov     [rsp+420h+var_3DB], al
0x14004cd77  mov     [rsp+420h+var_3DC], 1
0x14004cd7c  mov     eax, gs:1A4h
0x14004cd84  lea     rdx, [rax+rax*8]
0x14004cd88  mov     rax, cs:gPerProcessorContext
0x14004cd8f  cmp     [rax+rdx*8+20h], bl
0x14004cd93  jnz     loc_14004D2D3
0x14004cd99  mov     r12, [rax+rdx*8+18h]
0x14004cd9e  mov     rbx, [rax+rdx*8+10h]
0x14004cda3  mov     byte ptr [rax+rdx*8+20h], 1
0x14004cda8  xor     edx, edx; Val
0x14004cdaa  mov     [rbp+320h+var_388], rbx
0x14004cdae  mov     r8d, 2A0h; Size
0x14004cdb4  mov     [rsp+420h+var_3A8], r12
0x14004cdb9  mov     rcx, r12; void *
0x14004cdbc  call    memset
0x14004cdc1  xor     edx, edx; Val
0x14004cdc3  mov     r8d, 2A8h; Size
0x14004cdc9  mov     rcx, rbx; void *
0x14004cdcc  call    memset
0x14004cdd1  cmp     [rsp+420h+var_3C8], 0
0x14004cdd6  lea     rax, [rbx+270h]
0x14004cddd  mov     [rax+8], rax
0x14004cde1  lea     rdx, [rbp+320h+var_370]
0x14004cde5  mov     [rax], rax
0x14004cde8  mov     ecx, 2
0x14004cded  mov     eax, 17h
0x14004cdf2  mov     r8, r12
0x14004cdf5  cmovnz  cx, ax
0x14004cdf9  call    NlShimMarshalFwLayerFields
0x14004cdfe  mov     dword ptr [rsp+420h+var_3C0+4], eax
0x14004ce02  mov     word ptr [rsp+420h+var_3C0], r13w
0x14004ce08  mov     [rsp+420h+var_3B8], r12
0x14004ce0d  or      dword ptr [rbx], 800h
0x14004ce13  mov     rax, [rdi+10h]
0x14004ce17  mov     edx, [rbx]
0x14004ce19  mov     rcx, [rax]
0x14004ce1c  mov     eax, [rcx]
0x14004ce1e  mov     [rbx+50h], eax
0x14004ce21  cmp     byte ptr [rdi+0Ch], 0
0x14004ce25  jz      short loc_14004CE2D
0x14004ce27  bts     edx, 14h
0x14004ce2b  mov     [rbx], edx
0x14004ce2d  cmp     byte ptr [r15], 0
0x14004ce31  jz      short loc_14004CE39
0x14004ce33  bts     edx, 15h
0x14004ce37  mov     [rbx], edx
0x14004ce39  mov     rax, [rdi+10h]
0x14004ce3d  mov     rcx, [rax+30h]
0x14004ce41  mov     eax, [rcx+0Ch]
0x14004ce44  mov     [rbx+220h], eax
0x14004ce4a  mov     rax, [rdi+10h]
0x14004ce4e  add     rax, 3Ch ; '<'
0x14004ce52  cmp     [rsp+420h+var_3D8], 0
0x14004ce58  mov     [rbx+228h], rax
0x14004ce5f  lea     rax, [rbp+320h+var_380]
0x14004ce63  mov     qword ptr [rbp+320h+var_380+8], rax
0x14004ce67  lea     rax, [rbp+320h+var_380]
0x14004ce6b  mov     qword ptr [rbp+320h+var_380], rax
0x14004ce6f  jz      short loc_14004CE7C
0x14004ce71  lea     rax, [rbp+320h+var_380]
0x14004ce75  mov     [rbx+200h], rax
0x14004ce7c  mov     r9, [rdi+40h]
0x14004ce80  lea     rax, [rbp+320h+var_340]
0x14004ce84  mov     [rsp+420h+var_3F8], rax
0x14004ce89  lea     rdx, [rsp+420h+var_3C0]
0x14004ce8e  xor     r12d, r12d
0x14004ce91  mov     r8, rbx
0x14004ce94  movzx   ecx, r13w
0x14004ce98  mov     [rsp+420h+var_400], r12
0x14004ce9d  call    cs:__imp_KfdClassify
0x14004cea4  nop     dword ptr [rax+rax+00h]
0x14004cea9  test    eax, eax
0x14004ceab  jnz     loc_14004CFAD
0x14004ceb1  mov     r11, [rsp+420h+var_3D8]
0x14004ceb6  test    r11, r11
0x14004ceb9  jz      loc_14004D189
0x14004cebf  cmp     [rbx+218h], r12d
0x14004cec6  jz      loc_14004D1A7
0x14004cecc  mov     edx, [rbx+210h]
0x14004ced2  lea     rax, [rsp+420h+var_3C0]
0x14004ced7  mov     byte ptr [rsp+420h+var_3F0], r12b
0x14004cedc  lea     r8, [rbp+320h+var_370]
0x14004cee0  mov     [rsp+420h+var_3F8], rax
0x14004cee5  xor     r9d, r9d
0x14004cee8  mov     rax, [rbx+200h]
0x14004ceef  mov     rcx, r11
0x14004cef2  mov     [rsp+420h+var_400], rax
0x14004cef7  call    NlShimCacheMatchedFwLayerFilterList
0x14004cefc  test    eax, eax
0x14004cefe  jns     loc_1401C3D12
0x14004cf04  lea     rcx, [rbp+320h+var_380]
0x14004cf08  call    cs:__imp_KfdReleaseCachedFilters
0x14004cf0f  nop     dword ptr [rax+rax+00h]
0x14004cf14  nop
0x14004cf15  jmp     loc_1401C3D12
0x14004cf1a  cmp     [rax+0B8h], rbx
0x14004cf21  jz      loc_14004CD59
0x14004cf27  lea     r9, [rsp+420h+var_3B0]
0x14004cf2c  mov     [rsp+420h+var_3B0], rbx
0x14004cf31  lea     r8, NlShimReferenceFwLayerCache
0x14004cf38  xor     edx, edx
0x14004cf3a  mov     rcx, rax
0x14004cf3d  call    cs:__imp_NetioFlowRetrieveContext
0x14004cf44  nop     dword ptr [rax+rax+00h]
0x14004cf49  test    eax, eax
0x14004cf4b  jnz     loc_14004CD59
0x14004cf51  jmp     loc_1401C3C46
0x14004cf56  cmp     [rdi+0Ch], bl
0x14004cf59  jnz     loc_14004CD01
0x14004cf5f  cmp     [rdi+48h], bl
0x14004cf62  jnz     loc_14004CD01
0x14004cf68  mov     rcx, cs:qword_140227E88
0x14004cf6f  test    r14d, 0FFFFFFFBh
0x14004cf76  mov     rdx, [rdi+40h]
0x14004cf7a  cmovnz  rcx, cs:qword_140227E98
0x14004cf82  call    WfpIsInjectedByHandle
0x14004cf87  test    al, al
0x14004cf89  jnz     loc_14004CD01
0x14004cf8f  mov     rdx, rdi
0x14004cf92  mov     ecx, r14d
0x14004cf95  call    WfpQueueFwdPacket
0x14004cf9a  test    rax, rax
0x14004cf9d  jnz     loc_14004CD01
0x14004cfa3  mov     eax, 3
0x14004cfa8  jmp     loc_14004D27B
0x14004cfad  xorps   xmm0, xmm0
0x14004cfb0  xor     eax, eax
0x14004cfb2  movups  [rbp+320h+var_340], xmm0
0x14004cfb6  mov     dword ptr [rbp+320h+var_340], 1001h
0x14004cfbd  movups  [rbp+320h+var_330], xmm0
0x14004cfc1  mov     [rbp+320h+var_320], rax
0x14004cfc5  test    byte ptr [rbp+320h+var_330+0Ch], 1
0x14004cfc9  jnz     loc_14004D30E
0x14004cfcf  movzx   ecx, word ptr [rsp+420h+var_3D0]
0x14004cfd4  lea     rdx, [rsp+420h+var_3E0]
0x14004cfd9  mov     [rbx+200h], r12
0x14004cfe0  mov     r13d, 1
0x14004cfe6  mov     r9, [rdi+40h]
0x14004cfea  mov     rax, qword ptr [rbp+320h+var_330]
0x14004cfee  mov     [rbp+320h+var_390], r9
0x14004cff2  mov     [rbp+320h+var_398], rax
0x14004cff6  mov     [rsp+420h+var_3E0], r12w
0x14004cffc  mov     [rbp+320h+var_3A0], 2
0x14004d004  call    DetermineDiscardLayerId
0x14004d009  mov     eax, dword ptr [rbp+320h+var_320]
0x14004d00c  lea     rcx, [rbp+320h+var_2F0]; void *
0x14004d010  movzx   r12d, [rsp+420h+var_3E0]
0x14004d016  xorps   xmm0, xmm0
0x14004d019  mov     [rsp+420h+var_3C4], eax
0x14004d01d  xor     edx, edx; Val
0x14004d01f  xor     eax, eax
0x14004d021  mov     r8d, 2A8h; Size
0x14004d027  mov     [rbp+320h+var_2F8], eax
0x14004d02a  movups  [rbp+320h+var_318], xmm0
0x14004d02e  movups  [rbp+320h+var_308], xmm0
0x14004d032  call    memset
0x14004d037  mov     rax, [rbp+320h+var_390]
0x14004d03b  test    rax, rax
0x14004d03e  jz      loc_14004D329
0x14004d044  mov     rax, [rax+0F8h]
0x14004d04b  mov     rcx, 7FFFFFFFFFFFFFFFh
0x14004d055  and     rax, rcx
0x14004d058  movzx   ecx, word ptr [rsp+420h+var_3D0]
0x14004d05d  lea     r9, [rbp+320h+var_3A0]
0x14004d061  mov     r8, rbx
0x14004d064  mov     [rsp+420h+var_400], rax
0x14004d069  lea     rdx, [rsp+420h+var_3C0]
0x14004d06e  call    IndicateDropAudit
0x14004d073  test    [rsp+420h+var_3C4], 10000000h
0x14004d07b  jnz     loc_14004D3A0
0x14004d081  movzx   ecx, r12w
0x14004d085  call    cs:__imp_KfdIsLayerEmpty
0x14004d08c  nop     dword ptr [rax+rax+00h]
0x14004d091  test    eax, eax
0x14004d093  jnz     loc_14004D179
0x14004d099  xor     r8d, r8d
0x14004d09c  mov     dword ptr [rbp+320h+var_318], 1001h
0x14004d0a3  mov     qword ptr [rbp+320h+var_318+8], r8
0x14004d0a7  mov     qword ptr [rbp+320h+var_308], r8
0x14004d0ab  test    rbx, rbx
0x14004d0ae  jz      short loc_14004D128
0x14004d0b0  and     dword ptr [rbx+4], 0FFFFFFFEh
0x14004d0b4  lea     rcx, [rbp+320h+var_2F0]
0x14004d0b8  mov     rax, rbx
0x14004d0bb  mov     edx, 5
0x14004d0c0  lea     rcx, [rcx+80h]
0x14004d0c7  movups  xmm0, xmmword ptr [rax]
0x14004d0ca  movups  xmm1, xmmword ptr [rax+10h]
0x14004d0ce  lea     rax, [rax+80h]
0x14004d0d5  movups  xmmword ptr [rcx-80h], xmm0
0x14004d0d9  movups  xmm0, xmmword ptr [rax-60h]
0x14004d0dd  movups  xmmword ptr [rcx-70h], xmm1
0x14004d0e1  movups  xmm1, xmmword ptr [rax-50h]
0x14004d0e5  movups  xmmword ptr [rcx-60h], xmm0
0x14004d0e9  movups  xmm0, xmmword ptr [rax-40h]
0x14004d0ed  movups  xmmword ptr [rcx-50h], xmm1
0x14004d0f1  movups  xmm1, xmmword ptr [rax-30h]
0x14004d0f5  movups  xmmword ptr [rcx-40h], xmm0
0x14004d0f9  movups  xmm0, xmmword ptr [rax-20h]
0x14004d0fd  movups  xmmword ptr [rcx-30h], xmm1
0x14004d101  movups  xmm1, xmmword ptr [rax-10h]
0x14004d105  movups  xmmword ptr [rcx-20h], xmm0
0x14004d109  movups  xmmword ptr [rcx-10h], xmm1
0x14004d10d  sub     rdx, r13
0x14004d110  jnz     short loc_14004D0C0
0x14004d112  movups  xmm0, xmmword ptr [rax]
0x14004d115  movups  xmm1, xmmword ptr [rax+10h]
0x14004d119  mov     rax, [rax+20h]
0x14004d11d  movups  xmmword ptr [rcx], xmm0
0x14004d120  movups  xmmword ptr [rcx+10h], xmm1
0x14004d124  mov     [rcx+20h], rax
0x14004d128  mov     eax, dword ptr [rbp+320h+var_3A0]
0x14004d12b  lea     rdx, [rsp+420h+var_3C0]
0x14004d130  mov     r9, [rbp+320h+var_390]
0x14004d134  movzx   ecx, r12w
  ... truncated ...
```
