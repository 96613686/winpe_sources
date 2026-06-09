# WfpNlShimInspectForwardDatagram

- ea: `0x14004ced0`
- end: `0x14004d682`
- name: `WfpNlShimInspectForwardDatagram`
- size: `1970`
- prototype: ``
- caller_count: `2`
- callee_count: `21`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14004c880`
- `0x14016d0ac`

## callees

- `0x14004ccc0`
- `0x14004ced0`
- `0x14004d688`
- `0x14004d820`
- `0x140051888`
- `0x140052870`
- `0x140053af0`
- `0x140053bb0`
- `0x1400541c0`
- `0x1400897f0`
- `0x140135ddc`
- `0x140151edc`
- `0x14016ce4c`
- `0x14016d888`
- `0x14016d8e0`
- `0x14016db60`
- `0x14016dda0`
- `0x14016eb5c`
- `0x1401bf4d0`
- `0x1401bf700`
- `0x1401bfa80`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x14004cffe`
- `ntoskrnl!KeGetCurrentIrql` at `0x14004cffe`
- `NETIO!KfdIsLayerEmpty` at `0x14004d325`
- `NETIO!KfdIsLayerEmpty` at `0x14004d325`
- `NETIO!NetioFlowRemoveContext` at `0x1401c3e20`
- `NETIO!NetioFlowRemoveContext` at `0x1401c3e36`
- `NETIO!NetioFlowRemoveContext` at `0x1401c3e20`
- `NETIO!NetioFlowRemoveContext` at `0x1401c3e36`
- `NETIO!NetioFlowRetrieveContext` at `0x14004d1dd`
- `NETIO!NetioFlowRetrieveContext` at `0x14004d1dd`
- `NETIO!KfdReleaseTerminatingFilters` at `0x14004d4ec`
- `NETIO!KfdReleaseTerminatingFilters` at `0x14004d4ec`
- `NETIO!KfdReleaseCachedFilters` at `0x14004d1a8`
- `NETIO!KfdReleaseCachedFilters` at `0x14004d436`
- `NETIO!KfdReleaseCachedFilters` at `0x14004d1a8`
- `NETIO!KfdReleaseCachedFilters` at `0x14004d436`
- `NETIO!KfdClassify` at `0x14004d13d`
- `NETIO!KfdClassify` at `0x14004d405`
- `NETIO!KfdClassify` at `0x14004d13d`
- `NETIO!KfdClassify` at `0x14004d405`
- `NETIO!KfdGetLayerCacheEpoch` at `0x1401c3da3`
- `NETIO!KfdGetLayerCacheEpoch` at `0x1401c3da3`

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
    v23 = qword_140227E08;
    if ( (a1 & 0xFFFFFFFB) != 0 )
      v23 = qword_140227E18;
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
      IsLayerEmpty = ((__int64 (__fastcall *)(__int64, _QWORD))qword_140227EB8)(v62, *(_QWORD *)(a3 + 64));
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
          if ( !qword_140227EA8 || v4 )
          {
            v54 = v4;
          }
          else
          {
            LOBYTE(v58) = *(_BYTE *)(a3 + 12);
            LOBYTE(v57) = 0;
            LOBYTE(a2) = 1;
            v53 = ((__int64 (__fastcall *)(_QWORD, __int64, __int64, _QWORD *, int, int))qword_140227EA8)(
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
    if ( !qword_140227EA8 )
      goto LABEL_60;
    LOBYTE(v58) = *(_BYTE *)(a3 + 12);
    LOBYTE(v57) = *v13;
    IsLayerEmpty = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64, _QWORD, int, int))qword_140227EA8)(
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
0x14004ced0  mov     [rsp-8+arg_8], rbx
0x14004ced5  push    rbp
0x14004ced6  push    rsi
0x14004ced7  push    rdi
0x14004ced8  push    r12
0x14004ceda  push    r13
0x14004cedc  push    r14
0x14004cede  push    r15
0x14004cee0  lea     rbp, [rsp-2F0h]
0x14004cee8  sub     rsp, 3F0h
0x14004ceef  mov     rax, cs:__security_cookie
0x14004cef6  xor     rax, rsp
0x14004cef9  mov     [rbp+320h+var_40], rax
0x14004cf00  xorps   xmm0, xmm0
0x14004cf03  mov     [rsp+420h+var_3C8], ecx
0x14004cf07  xor     r13d, r13d
0x14004cf0a  mov     [rsp+420h+var_3D8], r9
0x14004cf0f  xor     eax, eax
0x14004cf11  mov     [rsp+420h+var_3C4], r13d
0x14004cf16  mov     eax, 8
0x14004cf1b  mov     [rsp+420h+var_3DB], r13b
0x14004cf20  mov     r14d, ecx
0x14004cf23  mov     [rsp+420h+var_3DC], r13b
0x14004cf28  test    r14d, r14d
0x14004cf2b  mov     ecx, 0Ah
0x14004cf30  mov     rdi, r8
0x14004cf33  mov     r11, r9
0x14004cf36  cmovnz  ax, cx
0x14004cf3a  mov     r8d, 3
0x14004cf40  xor     ebx, ebx
0x14004cf42  mov     [rsp+420h+var_3D0], eax
0x14004cf46  xor     eax, eax
0x14004cf48  mov     [rbp+320h+var_388], rbx
0x14004cf4c  xor     r12b, r12b
0x14004cf4f  mov     [rsp+420h+var_3C0], rax
0x14004cf54  mov     dword ptr [rsp+420h+var_3B8], eax
0x14004cf58  mov     word ptr [rsp+420h+var_3B8+4], ax
0x14004cf5d  mov     [rsp+420h+var_3A8], rax
0x14004cf62  mov     [rbp+320h+var_3A0], rax
0x14004cf66  mov     [rbp+320h+var_390], rbx
0x14004cf6a  mov     byte ptr [rsp+420h+var_3E0], r12b
0x14004cf6f  mov     [rbp+320h+var_320], rax
0x14004cf73  movups  xmmword ptr [rbp+320h+var_360], xmm0
0x14004cf77  movups  [rbp+320h+var_370], xmm0
0x14004cf7b  movups  xmmword ptr [rbp+320h+var_360+0Ch], xmm0
0x14004cf7f  movups  [rbp+320h+var_380], xmm0
0x14004cf83  movups  [rbp+320h+var_340], xmm0
0x14004cf87  movups  [rbp+320h+var_330], xmm0
0x14004cf8b  test    dl, dl
0x14004cf8d  jnz     loc_14004D546
0x14004cf93  mov     eax, cs:gWfpPacketQueue
0x14004cf99  test    al, 2
0x14004cf9b  jnz     loc_14004D1F6
0x14004cfa1  movzx   eax, byte ptr [rdi+1Ch]
0x14004cfa5  lea     r15, [rdi+1Ch]
0x14004cfa9  neg     al
0x14004cfab  mov     dword ptr [rbp+320h+var_370], r14d
0x14004cfaf  movzx   eax, byte ptr [rdi+0Ch]
0x14004cfb3  lea     r14, [rdi+48h]
0x14004cfb7  sbb     edx, edx
0x14004cfb9  mov     qword ptr [rbp+320h+var_370+8], rdi
0x14004cfbd  and     edx, 80000h
0x14004cfc3  neg     al
0x14004cfc5  movzx   eax, byte ptr [r14]
0x14004cfc9  sbb     ecx, ecx
0x14004cfcb  and     ecx, 40000h
0x14004cfd1  or      edx, ecx
0x14004cfd3  neg     al
0x14004cfd5  sbb     ecx, ecx
0x14004cfd7  and     ecx, 40h
0x14004cfda  or      edx, ecx
0x14004cfdc  mov     rcx, rdi
0x14004cfdf  mov     [rbp+320h+var_344], edx
0x14004cfe2  lea     rdx, [rbp+320h+var_370]
0x14004cfe6  call    NlShimFillFwEdgeInfo
0x14004cfeb  mov     rax, [rsp+420h+var_3D8]
0x14004cff0  test    rax, rax
0x14004cff3  jnz     loc_14004D1BA
0x14004cff9  mov     r13d, [rsp+420h+var_3D0]
0x14004cffe  call    cs:__imp_KeGetCurrentIrql
0x14004d005  nop     dword ptr [rax+rax+00h]
0x14004d00a  cmp     al, 2
0x14004d00c  jnb     short loc_14004D01C
0x14004d00e  call    WfpRaiseIrqlToDispatchLevel
0x14004d013  mov     [rsp+420h+var_3DB], al
0x14004d017  mov     [rsp+420h+var_3DC], 1
0x14004d01c  mov     eax, gs:1A4h
0x14004d024  lea     rdx, [rax+rax*8]
0x14004d028  mov     rax, cs:gPerProcessorContext
0x14004d02f  cmp     [rax+rdx*8+20h], bl
0x14004d033  jnz     loc_14004D573
0x14004d039  mov     r12, [rax+rdx*8+18h]
0x14004d03e  mov     rbx, [rax+rdx*8+10h]
0x14004d043  mov     byte ptr [rax+rdx*8+20h], 1
0x14004d048  xor     edx, edx; Val
0x14004d04a  mov     [rbp+320h+var_388], rbx
0x14004d04e  mov     r8d, 2A0h; Size
0x14004d054  mov     [rsp+420h+var_3A8], r12
0x14004d059  mov     rcx, r12; void *
0x14004d05c  call    memset
0x14004d061  xor     edx, edx; Val
0x14004d063  mov     r8d, 2A8h; Size
0x14004d069  mov     rcx, rbx; void *
0x14004d06c  call    memset
0x14004d071  cmp     [rsp+420h+var_3C8], 0
0x14004d076  lea     rax, [rbx+270h]
0x14004d07d  mov     [rax+8], rax
0x14004d081  lea     rdx, [rbp+320h+var_370]
0x14004d085  mov     [rax], rax
0x14004d088  mov     ecx, 2
0x14004d08d  mov     eax, 17h
0x14004d092  mov     r8, r12
0x14004d095  cmovnz  cx, ax
0x14004d099  call    NlShimMarshalFwLayerFields
0x14004d09e  mov     dword ptr [rsp+420h+var_3C0+4], eax
0x14004d0a2  mov     word ptr [rsp+420h+var_3C0], r13w
0x14004d0a8  mov     [rsp+420h+var_3B8], r12
0x14004d0ad  or      dword ptr [rbx], 800h
0x14004d0b3  mov     rax, [rdi+10h]
0x14004d0b7  mov     edx, [rbx]
0x14004d0b9  mov     rcx, [rax]
0x14004d0bc  mov     eax, [rcx]
0x14004d0be  mov     [rbx+50h], eax
0x14004d0c1  cmp     byte ptr [rdi+0Ch], 0
0x14004d0c5  jz      short loc_14004D0CD
0x14004d0c7  bts     edx, 14h
0x14004d0cb  mov     [rbx], edx
0x14004d0cd  cmp     byte ptr [r15], 0
0x14004d0d1  jz      short loc_14004D0D9
0x14004d0d3  bts     edx, 15h
0x14004d0d7  mov     [rbx], edx
0x14004d0d9  mov     rax, [rdi+10h]
0x14004d0dd  mov     rcx, [rax+30h]
0x14004d0e1  mov     eax, [rcx+0Ch]
0x14004d0e4  mov     [rbx+220h], eax
0x14004d0ea  mov     rax, [rdi+10h]
0x14004d0ee  add     rax, 3Ch ; '<'
0x14004d0f2  cmp     [rsp+420h+var_3D8], 0
0x14004d0f8  mov     [rbx+228h], rax
0x14004d0ff  lea     rax, [rbp+320h+var_380]
0x14004d103  mov     qword ptr [rbp+320h+var_380+8], rax
0x14004d107  lea     rax, [rbp+320h+var_380]
0x14004d10b  mov     qword ptr [rbp+320h+var_380], rax
0x14004d10f  jz      short loc_14004D11C
0x14004d111  lea     rax, [rbp+320h+var_380]
0x14004d115  mov     [rbx+200h], rax
0x14004d11c  mov     r9, [rdi+40h]
0x14004d120  lea     rax, [rbp+320h+var_340]
0x14004d124  mov     [rsp+420h+var_3F8], rax
0x14004d129  lea     rdx, [rsp+420h+var_3C0]
0x14004d12e  xor     r12d, r12d
0x14004d131  mov     r8, rbx
0x14004d134  movzx   ecx, r13w
0x14004d138  mov     [rsp+420h+var_400], r12
0x14004d13d  call    cs:__imp_KfdClassify
0x14004d144  nop     dword ptr [rax+rax+00h]
0x14004d149  test    eax, eax
0x14004d14b  jnz     loc_14004D24D
0x14004d151  mov     r11, [rsp+420h+var_3D8]
0x14004d156  test    r11, r11
0x14004d159  jz      loc_14004D429
0x14004d15f  cmp     [rbx+218h], r12d
0x14004d166  jz      loc_14004D447
0x14004d16c  mov     edx, [rbx+210h]
0x14004d172  lea     rax, [rsp+420h+var_3C0]
0x14004d177  mov     byte ptr [rsp+420h+var_3F0], r12b
0x14004d17c  lea     r8, [rbp+320h+var_370]
0x14004d180  mov     [rsp+420h+var_3F8], rax
0x14004d185  xor     r9d, r9d
0x14004d188  mov     rax, [rbx+200h]
0x14004d18f  mov     rcx, r11
0x14004d192  mov     [rsp+420h+var_400], rax
0x14004d197  call    NlShimCacheMatchedFwLayerFilterList
0x14004d19c  test    eax, eax
0x14004d19e  jns     loc_1401C3E52
0x14004d1a4  lea     rcx, [rbp+320h+var_380]
0x14004d1a8  call    cs:__imp_KfdReleaseCachedFilters
0x14004d1af  nop     dword ptr [rax+rax+00h]
0x14004d1b4  nop
0x14004d1b5  jmp     loc_1401C3E52
0x14004d1ba  cmp     [rax+0B8h], rbx
0x14004d1c1  jz      loc_14004CFF9
0x14004d1c7  lea     r9, [rsp+420h+var_3B0]
0x14004d1cc  mov     [rsp+420h+var_3B0], rbx
0x14004d1d1  lea     r8, NlShimReferenceFwLayerCache
0x14004d1d8  xor     edx, edx
0x14004d1da  mov     rcx, rax
0x14004d1dd  call    cs:__imp_NetioFlowRetrieveContext
0x14004d1e4  nop     dword ptr [rax+rax+00h]
0x14004d1e9  test    eax, eax
0x14004d1eb  jnz     loc_14004CFF9
0x14004d1f1  jmp     loc_1401C3D86
0x14004d1f6  cmp     [rdi+0Ch], bl
0x14004d1f9  jnz     loc_14004CFA1
0x14004d1ff  cmp     [rdi+48h], bl
0x14004d202  jnz     loc_14004CFA1
0x14004d208  mov     rcx, cs:qword_140227E08
0x14004d20f  test    r14d, 0FFFFFFFBh
0x14004d216  mov     rdx, [rdi+40h]
0x14004d21a  cmovnz  rcx, cs:qword_140227E18
0x14004d222  call    WfpIsInjectedByHandle
0x14004d227  test    al, al
0x14004d229  jnz     loc_14004CFA1
0x14004d22f  mov     rdx, rdi
0x14004d232  mov     ecx, r14d
0x14004d235  call    WfpQueueFwdPacket
0x14004d23a  test    rax, rax
0x14004d23d  jnz     loc_14004CFA1
0x14004d243  mov     eax, 3
0x14004d248  jmp     loc_14004D51B
0x14004d24d  xorps   xmm0, xmm0
0x14004d250  xor     eax, eax
0x14004d252  movups  [rbp+320h+var_340], xmm0
0x14004d256  mov     dword ptr [rbp+320h+var_340], 1001h
0x14004d25d  movups  [rbp+320h+var_330], xmm0
0x14004d261  mov     [rbp+320h+var_320], rax
0x14004d265  test    byte ptr [rbp+320h+var_330+0Ch], 1
0x14004d269  jnz     loc_14004D5AE
0x14004d26f  movzx   ecx, word ptr [rsp+420h+var_3D0]
0x14004d274  lea     rdx, [rsp+420h+var_3E0]
0x14004d279  mov     [rbx+200h], r12
0x14004d280  mov     r13d, 1
0x14004d286  mov     r9, [rdi+40h]
0x14004d28a  mov     rax, qword ptr [rbp+320h+var_330]
0x14004d28e  mov     [rbp+320h+var_390], r9
0x14004d292  mov     [rbp+320h+var_398], rax
0x14004d296  mov     [rsp+420h+var_3E0], r12w
0x14004d29c  mov     [rbp+320h+var_3A0], 2
0x14004d2a4  call    DetermineDiscardLayerId
0x14004d2a9  mov     eax, dword ptr [rbp+320h+var_320]
0x14004d2ac  lea     rcx, [rbp+320h+var_2F0]; void *
0x14004d2b0  movzx   r12d, [rsp+420h+var_3E0]
0x14004d2b6  xorps   xmm0, xmm0
0x14004d2b9  mov     [rsp+420h+var_3C4], eax
0x14004d2bd  xor     edx, edx; Val
0x14004d2bf  xor     eax, eax
0x14004d2c1  mov     r8d, 2A8h; Size
0x14004d2c7  mov     [rbp+320h+var_2F8], eax
0x14004d2ca  movups  [rbp+320h+var_318], xmm0
0x14004d2ce  movups  [rbp+320h+var_308], xmm0
0x14004d2d2  call    memset
0x14004d2d7  mov     rax, [rbp+320h+var_390]
0x14004d2db  test    rax, rax
0x14004d2de  jz      loc_14004D5C9
0x14004d2e4  mov     rax, [rax+0F8h]
0x14004d2eb  mov     rcx, 7FFFFFFFFFFFFFFFh
0x14004d2f5  and     rax, rcx
0x14004d2f8  movzx   ecx, word ptr [rsp+420h+var_3D0]
0x14004d2fd  lea     r9, [rbp+320h+var_3A0]
0x14004d301  mov     r8, rbx
0x14004d304  mov     [rsp+420h+var_400], rax
0x14004d309  lea     rdx, [rsp+420h+var_3C0]
0x14004d30e  call    IndicateDropAudit
0x14004d313  test    [rsp+420h+var_3C4], 10000000h
0x14004d31b  jnz     loc_14004D640
0x14004d321  movzx   ecx, r12w
0x14004d325  call    cs:__imp_KfdIsLayerEmpty
0x14004d32c  nop     dword ptr [rax+rax+00h]
0x14004d331  test    eax, eax
0x14004d333  jnz     loc_14004D419
0x14004d339  xor     r8d, r8d
0x14004d33c  mov     dword ptr [rbp+320h+var_318], 1001h
0x14004d343  mov     qword ptr [rbp+320h+var_318+8], r8
0x14004d347  mov     qword ptr [rbp+320h+var_308], r8
0x14004d34b  test    rbx, rbx
0x14004d34e  jz      short loc_14004D3C8
0x14004d350  and     dword ptr [rbx+4], 0FFFFFFFEh
0x14004d354  lea     rcx, [rbp+320h+var_2F0]
0x14004d358  mov     rax, rbx
0x14004d35b  mov     edx, 5
0x14004d360  lea     rcx, [rcx+80h]
0x14004d367  movups  xmm0, xmmword ptr [rax]
0x14004d36a  movups  xmm1, xmmword ptr [rax+10h]
0x14004d36e  lea     rax, [rax+80h]
0x14004d375  movups  xmmword ptr [rcx-80h], xmm0
0x14004d379  movups  xmm0, xmmword ptr [rax-60h]
0x14004d37d  movups  xmmword ptr [rcx-70h], xmm1
0x14004d381  movups  xmm1, xmmword ptr [rax-50h]
0x14004d385  movups  xmmword ptr [rcx-60h], xmm0
0x14004d389  movups  xmm0, xmmword ptr [rax-40h]
0x14004d38d  movups  xmmword ptr [rcx-50h], xmm1
0x14004d391  movups  xmm1, xmmword ptr [rax-30h]
0x14004d395  movups  xmmword ptr [rcx-40h], xmm0
0x14004d399  movups  xmm0, xmmword ptr [rax-20h]
0x14004d39d  movups  xmmword ptr [rcx-30h], xmm1
0x14004d3a1  movups  xmm1, xmmword ptr [rax-10h]
0x14004d3a5  movups  xmmword ptr [rcx-20h], xmm0
0x14004d3a9  movups  xmmword ptr [rcx-10h], xmm1
0x14004d3ad  sub     rdx, r13
0x14004d3b0  jnz     short loc_14004D360
0x14004d3b2  movups  xmm0, xmmword ptr [rax]
0x14004d3b5  movups  xmm1, xmmword ptr [rax+10h]
0x14004d3b9  mov     rax, [rax+20h]
0x14004d3bd  movups  xmmword ptr [rcx], xmm0
0x14004d3c0  movups  xmmword ptr [rcx+10h], xmm1
0x14004d3c4  mov     [rcx+20h], rax
0x14004d3c8  mov     eax, dword ptr [rbp+320h+var_3A0]
0x14004d3cb  lea     rdx, [rsp+420h+var_3C0]
0x14004d3d0  mov     r9, [rbp+320h+var_390]
0x14004d3d4  movzx   ecx, r12w
  ... truncated ...
```
