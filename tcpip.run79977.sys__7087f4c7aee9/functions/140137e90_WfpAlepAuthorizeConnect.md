# WfpAlepAuthorizeConnect

- ea: `0x140137e90`
- end: `0x140139406`
- name: `WfpAlepAuthorizeConnect`
- size: `5494`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400cce90`

## callees

- `0x140051888`
- `0x140052630`
- `0x140053af0`
- `0x140053bb0`
- `0x1400540a4`
- `0x1400551a0`
- `0x140055ac0`
- `0x140073ca0`
- `0x14008b220`
- `0x1400ddad4`
- `0x1400e4fe8`
- `0x1400f78e8`
- `0x1400f84bc`
- `0x14010c80c`
- `0x140136830`
- `0x140137e90`
- `0x14013ca80`
- `0x14014f398`
- `0x14015040c`
- `0x140171754`
- `0x1401bfa80`

## import_xrefs

- `ntoskrnl!ExFreeToLookasideListEx` at `0x140138187`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14013933c`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14013937c`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140138187`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14013933c`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14013937c`
- `ntoskrnl!KeGetCurrentIrql` at `0x1401380d5`
- `ntoskrnl!KeGetCurrentIrql` at `0x1401380d5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140138ea1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140139200`
- `ntoskrnl!ExFreePoolWithTag` at `0x140138ea1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140139200`
- `NETIO!WfpCalloutDiagTraceRedirectedAuthConnect` at `0x140139255`
- `NETIO!WfpCalloutDiagTraceRedirectedAuthConnect` at `0x140139255`
- `NETIO!FeReleaseCompletionHandle` at `0x140138219`
- `NETIO!FeReleaseCompletionHandle` at `0x140138219`
- `NETIO!FeAcquireGenericCompletionHandle` at `0x140138b9b`
- `NETIO!FeAcquireGenericCompletionHandle` at `0x140138b9b`
- `NETIO!FeAcquireCompletionHandle` at `0x140138b8a`
- `NETIO!FeAcquireCompletionHandle` at `0x140138b8a`
- `NETIO!KfdAleAcquireEndpointContextFromFlow` at `0x14013830a`
- `NETIO!KfdAleAcquireEndpointContextFromFlow` at `0x14013830a`
- `NETIO!KfdReleaseTerminatingFilters` at `0x1401392ed`
- `NETIO!KfdReleaseTerminatingFilters` at `0x1401392ed`
- `NETIO!KfdAleReleaseFlowHandleForFlow` at `0x140138de5`
- `NETIO!KfdAleReleaseFlowHandleForFlow` at `0x140139277`
- `NETIO!KfdAleReleaseFlowHandleForFlow` at `0x140138de5`
- `NETIO!KfdAleReleaseFlowHandleForFlow` at `0x140139277`
- `NETIO!KfdAleAcquireFlowHandleForFlow` at `0x140138da6`
- `NETIO!KfdAleAcquireFlowHandleForFlow` at `0x140138da6`
- `NETIO!KfdGetLayerCacheEpoch` at `0x140138024`
- `NETIO!KfdGetLayerCacheEpoch` at `0x140138024`

## pseudocode

```c
__int64 __fastcall WfpAlepAuthorizeConnect(
        __int64 a1,
        unsigned __int16 a2,
        unsigned __int16 *a3,
        __int64 a4,
        _OWORD *a5,
        __int16 a6,
        char a7,
        char a8,
        __int64 a9,
        _OWORD *a10,
        unsigned __int16 a11,
        __int64 a12,
        __int64 a13,
        __int128 *a14,
        int a15,
        unsigned __int8 a16,
        __int64 a17,
        __int64 a18,
        __int64 a19,
        _DWORD *a20,
        _DWORD *a21,
        _DWORD *a22)
{
  __int128 *v25; // r14
  __int64 v26; // rdx
  __int64 v27; // r13
  char *v28; // r15
  __int64 v29; // rax
  _DWORD *v30; // rdi
  __int64 PeerInformationForPeerName; // rbx
  char v32; // r12
  __int64 v33; // rcx
  char *v34; // rbx
  __int64 v35; // rax
  __int64 v36; // rax
  BOOL v37; // edx
  __int64 v38; // rcx
  __int64 v39; // rax
  __int64 v40; // rax
  __int64 v41; // rcx
  __int64 v42; // rax
  __int64 v43; // rcx
  __int64 v44; // rax
  bool v45; // zf
  __int64 v46; // rax
  __int64 v47; // r9
  int v48; // edx
  __int64 v49; // rcx
  void *v50; // rax
  __int64 v51; // rcx
  __int64 v52; // rax
  int v53; // eax
  __int128 v54; // xmm6
  __int128 v55; // xmm7
  __int128 v56; // xmm8
  int v57; // r8d
  PVOID v58; // rdx
  __int64 v59; // rax
  __int64 v60; // rbx
  __int64 v61; // rax
  __int64 v62; // rdx
  int ProfileIdFromInterface; // eax
  int v64; // ecx
  __int64 v65; // rcx
  __int64 i; // rcx
  __int64 v67; // rdx
  int v68; // r8d
  int v69; // ecx
  int v70; // eax
  int v71; // edx
  int v72; // ecx
  __int64 v73; // r9
  __int64 v74; // rcx
  __int64 v75; // rcx
  __int64 inserted; // rax
  int v77; // eax
  __int64 v78; // rax
  __int64 v79; // rax
  __int64 v80; // rcx
  __int64 v81; // rax
  __int64 v82; // rax
  __int64 v83; // rbx
  __int64 v84; // rcx
  _DWORD *v85; // r8
  __int64 v86; // rcx
  __int64 v87; // rcx
  __int64 v88; // rcx
  __int64 v89; // rax
  int v90; // eax
  __int64 v91; // rax
  char v92; // dl
  __int64 v93; // rcx
  __int128 v94; // xmm0
  __int128 v95; // xmm1
  __int128 v96; // xmm2
  void *v97; // rdx
  __int64 v98; // rax
  _BYTE *v99; // r12
  int v100; // r9d
  __int64 v101; // rcx
  __int128 *v102; // rax
  __int128 v103; // xmm0
  __int64 v104; // rax
  __int64 v105; // r14
  PVOID *v106; // rsi
  char *v107; // rsi
  char *v108; // rdi
  __int64 v110; // [rsp+28h] [rbp-E0h]
  __int64 v111; // [rsp+30h] [rbp-D8h]
  char v112; // [rsp+68h] [rbp-A0h]
  bool v113; // [rsp+69h] [rbp-9Fh]
  __int16 v114; // [rsp+6Ah] [rbp-9Eh]
  char v115; // [rsp+6Ch] [rbp-9Ch]
  unsigned __int16 v116; // [rsp+6Eh] [rbp-9Ah]
  BOOL v117; // [rsp+70h] [rbp-98h] BYREF
  unsigned __int16 v118; // [rsp+74h] [rbp-94h]
  PVOID Entry; // [rsp+78h] [rbp-90h] BYREF
  __int64 v120; // [rsp+80h] [rbp-88h] BYREF
  __int64 v121; // [rsp+88h] [rbp-80h]
  _DWORD *v122; // [rsp+90h] [rbp-78h] BYREF
  __int64 v123; // [rsp+98h] [rbp-70h]
  __int64 v124; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v125; // [rsp+A8h] [rbp-60h]
  __int64 v126; // [rsp+B0h] [rbp-58h] BYREF
  PVOID P[2]; // [rsp+B8h] [rbp-50h] BYREF
  _DWORD *v128; // [rsp+C8h] [rbp-40h]
  __int64 v129; // [rsp+D0h] [rbp-38h]
  __int64 v130; // [rsp+D8h] [rbp-30h]
  __int64 v131; // [rsp+E0h] [rbp-28h] BYREF
  __int64 v132; // [rsp+E8h] [rbp-20h] BYREF
  __int64 v133; // [rsp+F0h] [rbp-18h]
  __int128 v134; // [rsp+F8h] [rbp-10h] BYREF
  __int64 v135; // [rsp+108h] [rbp+0h]
  __int64 v136; // [rsp+110h] [rbp+8h]
  __int64 v137; // [rsp+118h] [rbp+10h] BYREF
  _OWORD *v138; // [rsp+120h] [rbp+18h]
  _DWORD *v139; // [rsp+128h] [rbp+20h]
  __int128 *v140; // [rsp+130h] [rbp+28h] BYREF
  __int64 v141; // [rsp+138h] [rbp+30h]
  __int64 v142; // [rsp+140h] [rbp+38h]
  __int64 v143; // [rsp+148h] [rbp+40h]
  __int64 v144; // [rsp+150h] [rbp+48h] BYREF
  __int64 v145; // [rsp+158h] [rbp+50h] BYREF
  __int64 v146; // [rsp+160h] [rbp+58h]
  __int64 v147; // [rsp+168h] [rbp+60h] BYREF
  __int64 v148; // [rsp+170h] [rbp+68h]
  __int64 v149; // [rsp+178h] [rbp+70h] BYREF
  __int64 v150; // [rsp+180h] [rbp+78h]
  __int64 v151; // [rsp+188h] [rbp+80h] BYREF
  __int64 v152; // [rsp+190h] [rbp+88h]
  __int64 v153; // [rsp+198h] [rbp+90h] BYREF
  __int64 v154; // [rsp+1A0h] [rbp+98h]
  __int128 v155; // [rsp+1A8h] [rbp+A0h] BYREF
  __int64 v156; // [rsp+1B8h] [rbp+B0h]
  _DWORD *v157; // [rsp+1C0h] [rbp+B8h]
  __int128 v158; // [rsp+1C8h] [rbp+C0h]
  __int128 v159; // [rsp+1D8h] [rbp+D0h]
  __int128 v160; // [rsp+1E8h] [rbp+E0h]

  v25 = a14;
  v129 = a9;
  v138 = a10;
  v116 = a11;
  v141 = a12;
  v135 = a13;
  v130 = a18;
  v157 = a21;
  v139 = a22;
  v118 = a2;
  v26 = 0;
  v27 = 0;
  v112 = 0;
  v28 = 0;
  v29 = *(_QWORD *)(a1 + 448);
  v30 = 0;
  v136 = a4;
  v143 = v29;
  PeerInformationForPeerName = 0;
  v128 = a20;
  v140 = 0;
  v131 = 0;
  Entry = 0;
  v122 = 0;
  v114 = 0;
  v123 = 0;
  *(_OWORD *)P = 0;
  v126 = 0;
  if ( a16 && v29 && (!*(_DWORD *)(v29 + 464) || !*(_QWORD *)(v29 + 472)) )
  {
    *a20 = 4097;
    PeerInformationForPeerName = -1073741790;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
    {
      WPP_SF_sd(
        WPP_GLOBAL_Control->AttachedDevice,
        10,
        (unsigned int)&WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
        (unsigned int)"WfpAlepAuthorizeConnect",
        34);
    }
    v32 = 0;
    goto LABEL_28;
  }
  v117 = 0;
  *(_WORD *)(a1 + 416) = a2;
  KfdGetLayerCacheEpoch(a2, &v117);
  *(_DWORD *)(a1 + 408) = v117;
  if ( a15 && (*(_DWORD *)(a1 + 48) & 0x4000) == 0 && !gAleEnableNameOnSecureSocket )
    goto LABEL_194;
  v144 = 0;
  LODWORD(v133) = 0;
  LODWORD(v148) = 0;
  LODWORD(v125) = 0;
  LODWORD(v152) = 0;
  LODWORD(v154) = 0;
  LODWORD(v150) = 0;
  LODWORD(v121) = 0;
  v132 = 0;
  v147 = 0;
  v124 = 0;
  v151 = 0;
  v153 = 0;
  v149 = 0;
  v120 = 0;
  v155 = 0;
  v156 = 0;
  v134 = 0;
  v145 = 0;
  v158 = 0;
  v137 = 0;
  v159 = 0;
  v160 = 0;
  if ( KeGetCurrentIrql() < 2u )
  {
    HIBYTE(v114) = WfpRaiseIrqlToDispatchLevel();
    LOBYTE(v114) = 1;
  }
  LODWORD(v33) = HIDWORD(KeGetPcr()[1].LockArray);
  if ( !*((_BYTE *)gPerProcessorContext + 72 * v33 + 32) )
  {
    v28 = (char *)*((_QWORD *)gPerProcessorContext + 9 * v33 + 3);
    v30 = (_DWORD *)*((_QWORD *)gPerProcessorContext + 9 * v33 + 2);
    *((_BYTE *)gPerProcessorContext + 72 * v33 + 32) = 1;
    goto LABEL_31;
  }
  if ( !WfpAllocateFromPerProcessorLookasideList(gIncomingValuesLookasideList, &Entry) )
  {
    if ( !WfpAllocateFromPerProcessorLookasideList(gMetadataLookasideList, &v122) )
    {
      v28 = (char *)Entry;
      v30 = v122;
LABEL_31:
      memset(v28, 0, 0x2A0u);
      memset(v30, 0, 0x2A8u);
      *((_QWORD *)v30 + 79) = v30 + 156;
      *((_QWORD *)v30 + 78) = v30 + 156;
      if ( (*(_DWORD *)(a1 + 52) & 0x10000) == 0
        || (*(_DWORD *)(a1 + 52) & 0x2000) != 0 && (*(_DWORD *)(a1 + 48) & 0x1000000) != 0 )
      {
        v112 = 1;
        if ( (*(_DWORD *)(a1 + 52) & 0x2000) != 0 && (*(_DWORD *)(a1 + 52) & 0x10000) == 0 )
          v27 = v143;
      }
      else
      {
        v35 = *(_QWORD *)(a1 + 448);
        if ( !v35 )
        {
          *v128 = 4097;
          PeerInformationForPeerName = -1073741790;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
          {
            WPP_SF_sd(
              WPP_GLOBAL_Control->AttachedDevice,
              10,
              (unsigned int)&WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
              (unsigned int)"WfpAlepAuthorizeConnect",
              34);
          }
          v32 = 1;
          goto LABEL_28;
        }
        v112 = 1;
        do
        {
          v27 = v35;
          v35 = *(_QWORD *)(v35 + 48);
        }
        while ( v35 );
        v36 = KfdAleAcquireEndpointContextFromFlow(*(_QWORD *)(v27 + 504));
        v123 = v36;
        PeerInformationForPeerName = v36;
        if ( v36 )
          v27 = *(_QWORD *)(v36 + 448);
      }
      if ( (*(_DWORD *)(a1 + 52) & 0x2000) == 0
        || (*(_DWORD *)(a1 + 52) & 0x10000) != 0
        || (*(_DWORD *)(a1 + 48) & 0x1000000) != 0
        || (LODWORD(v122) = 1, !v27) )
      {
        LODWORD(v122) = 0;
      }
      v37 = (*(_DWORD *)(a1 + 52) & 0x10000) != 0
         && (*(_DWORD *)(a1 + 48) & 0x1000000) == 0
         && PeerInformationForPeerName
         && v27;
      v38 = *(_QWORD *)(a1 + 480);
      LOWORD(v134) = v118;
      DWORD1(v134) = *a3;
      *((_QWORD *)&v134 + 1) = v28;
      v133 = *(_QWORD *)(v38 + 16);
      LODWORD(v132) = *(unsigned __int16 *)(v38 + 10);
      v39 = 2LL * a3[1];
      v117 = v37;
      *(_DWORD *)&v28[8 * v39] = 12;
      *(_QWORD *)&v28[16 * a3[1] + 8] = &v132;
      if ( v37 )
      {
        v125 = *(_QWORD *)(PeerInformationForPeerName + 488) + 224LL;
        LODWORD(v124) = *(_DWORD *)(*(_QWORD *)(PeerInformationForPeerName + 488) + 72LL);
        v40 = *(_QWORD *)(PeerInformationForPeerName + 488);
        Entry = *(PVOID *)(v40 + 280);
        v41 = *(_QWORD *)(v40 + 144);
        if ( v41 )
        {
          PeerInformationForPeerName = WfpAleMarshalFqbnValue(*(_QWORD *)(*(_QWORD *)(v41 + 8) + 32LL), P);
          if ( PeerInformationForPeerName )
            goto LABEL_194;
          PeerInformationForPeerName = v123;
        }
        v42 = *(_QWORD *)(PeerInformationForPeerName + 728);
        if ( v42 )
          v121 = v42 + 104;
        else
          v121 = 0;
        v43 = *(_QWORD *)(PeerInformationForPeerName + 728);
        if ( v43 )
        {
          v44 = -1;
          do
            v45 = *(_WORD *)(v43 + 2 * v44++ + 106) == 0;
          while ( !v45 );
          LODWORD(v120) = 2 * v44 + 2;
        }
        else
        {
          LODWORD(v120) = 0;
        }
        v46 = *(_QWORD *)(PeerInformationForPeerName + 488);
        v47 = *(_QWORD *)(PeerInformationForPeerName + 728);
        v48 = *(unsigned __int16 *)(PeerInformationForPeerName + 60);
      }
      else
      {
        v49 = *(_QWORD *)(a1 + 488);
        v125 = v49 + 224;
        LODWORD(v124) = *(_DWORD *)(v49 + 72);
        v50 = *(void **)(v49 + 280);
        v51 = *(_QWORD *)(v49 + 144);
        Entry = v50;
        if ( v51 )
        {
          PeerInformationForPeerName = WfpAleMarshalFqbnValue(*(_QWORD *)(*(_QWORD *)(v51 + 8) + 32LL), P);
          if ( PeerInformationForPeerName )
            goto LABEL_194;
        }
        v47 = *(_QWORD *)(a1 + 728);
        if ( v47 )
        {
          v52 = -1;
          v121 = v47 + 104;
          do
            v45 = *(_WORD *)(v47 + 104 + 2 * v52++ + 2) == 0;
          while ( !v45 );
          v53 = 2 * v52 + 2;
        }
        else
        {
          v53 = 0;
          v121 = 0;
        }
        v48 = *(unsigned __int16 *)(a1 + 60);
        LODWORD(v120) = v53;
        v46 = *(_QWORD *)(a1 + 488);
      }
      v54 = *(_OWORD *)(v46 + 160);
      v55 = *(_OWORD *)(v46 + 192);
      v115 = *(_BYTE *)(v46 + 152);
      v56 = *(_OWORD *)(v46 + 208);
      v146 = *(_QWORD *)(v46 + 176);
      WfpAleLogEndpointNrtRecordInfo(v129, v48, v133, v47, (__int64)&v134);
      v58 = Entry;
      if ( Entry )
      {
        if ( (*(_DWORD *)(v125 + 44) & 0x4000) != 0 )
          _InterlockedOr((volatile signed __int32 *)(a1 + 48), 0x2000000u);
      }
      else
      {
        v58 = &gAleNullSid;
      }
      *(_DWORD *)&v28[16 * a3[41]] = 16;
      *(_QWORD *)&v28[16 * a3[41] + 8] = &v124;
      *(_DWORD *)&v28[16 * a3[39]] = 12;
      *(_QWORD *)&v28[16 * a3[39] + 8] = &v120;
      *(_DWORD *)&v28[16 * a3[2]] = 16;
      *(_QWORD *)&v28[16 * a3[2] + 8] = &v124;
      *(_DWORD *)&v28[16 * a3[37]] = 13;
      *(_QWORD *)&v28[16 * a3[37] + 8] = v58;
      *(_DWORD *)&v28[16 * a3[38]] = 12;
      *(_QWORD *)&v28[16 * a3[38] + 8] = P;
      v45 = (_DWORD)v122 == 0;
      *(_OWORD *)&v28[16 * a3[3]] = *a5;
      if ( !v45 || v117 )
      {
        if ( *(_WORD *)(v27 + 72) == 23 )
          v113 = !*(_WORD *)(v27 + 80)
              && !*(_WORD *)(v27 + 82)
              && !*(_WORD *)(v27 + 84)
              && !*(_WORD *)(v27 + 86)
              && !*(_WORD *)(v27 + 88)
              && !*(_WORD *)(v27 + 90)
              && !*(_WORD *)(v27 + 92)
              && *(_WORD *)(v27 + 94) == 256;
        else
          v113 = *(_BYTE *)(v27 + 76) == 127;
        PeerInformationForPeerName = WfpAlepAuthOutboundFlowSwizzleDestinationInformation(
                                       (_DWORD)a3,
                                       v27,
                                       v57,
                                       (_DWORD)v138,
                                       (__int64)v28);
        if ( PeerInformationForPeerName )
          goto LABEL_194;
        LODWORD(Entry) = a16;
        a16 = v113;
      }
      else
      {
        v59 = 2LL * a3[7];
        LODWORD(Entry) = 0;
        *(_OWORD *)&v28[8 * v59] = *v138;
        *(_DWORD *)&v28[16 * a3[8]] = 2;
        *(_WORD *)&v28[16 * a3[8] + 8] = __ROR2__(v116, 8);
      }
      v60 = 0;
      v61 = 2LL * a3[6];
      v62 = v136;
      v142 = 0;
      *(_DWORD *)&v28[8 * v61] = 1;
      v28[16 * a3[6] + 8] = *(_BYTE *)(a1 + 40);
      *(_DWORD *)&v28[16 * a3[5]] = 2;
      *(_WORD *)&v28[16 * a3[5] + 8] = __ROR2__(a6, 8);
      *(_DWORD *)&v28[16 * a3[4]] = 1;
      v28[16 * a3[4] + 8] = a7;
      *(_DWORD *)&v28[16 * a3[11]] = 1;
      v28[16 * a3[11] + 8] = a7;
      *(_DWORD *)&v28[16 * a3[12]] = 4;
      *(_QWORD *)&v28[16 * a3[12] + 8] = &a8;
      *(_DWORD *)&v28[16 * a3[13]] = 3;
      *(_DWORD *)&v28[16 * a3[13] + 8] = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v62 + 8) + 48LL) + 12LL);
      *(_DWORD *)&v28[16 * a3[14]] = 3;
      *(_DWORD *)&v28[16 * a3[14] + 8] = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v62 + 8) + 48LL) + 16LL);
      *(_DWORD *)&v28[16 * a3[19]] = 3;
      *(_DWORD *)&v28[16 * a3[19] + 8] = *(_DWORD *)(*(_QWORD *)(v62 + 8) + 8LL);
      if ( v135 )
      {
        ProfileIdFromInterface = WfpGetProfileIdFromInterface(v135, v62, v62, v141, 0);
        v62 = v136;
      }
      else
      {
        ProfileIdFromInterface = 0;
      }
      v64 = (int)v157;
      *v157 = ProfileIdFromInterface;
      AlepFillEdgeInterfaceRelatedFields(
        v64,
        (_DWORD)a3,
        0,
        0,
        v135,
        v62,
        v141,
        0,
        0,
        ProfileIdFromInterface,
        0,
        (__int64)v28);
      if ( *(_DWORD *)&v28[16 * a3[31]] )
        *v139 = *(_DWORD *)&v28[16 * a3[31] + 8];
      v65 = v135;
      *(_DWORD *)&v28[16 * a3[34]] = 0;
      if ( v65 )
      {
        *(_DWORD *)&v28[16 * a3[35]] = 4;
        *(_QWORD *)&v28[16 * a3[35] + 8] = v65 + 80;
      }
      else
      {
        *(_DWORD *)&v28[16 * a3[35]] = 0;
      }
      if ( *(_QWORD *)(a1 + 448) && (*(_DWORD *)(a1 + 52) & 0x10000) != 0 )
      {
        for ( i = *(_QWORD *)(a1 + 448); *(_QWORD *)(i + 48); i = *(_QWORD *)(i + 48) )
          ;
        v60 = *(_QWORD *)(i + 56);
        v142 = v60;
      }
      if ( v60 )
      {
        v148 = *(_QWORD *)(v60 + 8);
        LODWORD(v147) = *(unsigned __int16 *)(v60 + 2);
        *(_DWORD *)&v28[16 * a3[36]] = 12;
        *(_QWORD *)&v28[16 * a3[36] + 8] = &v147;
      }
      else
      {
        *(_DWORD *)&v28[16 * a3[36]] = 0;
      }
      PeerInformationForPeerName = WfpAleFindPeerInformationForPeerName(a1, v118, v129, v116, (__int64)&v131);
      if ( PeerInformationForPeerName )
        goto LABEL_194;
      v67 = v131;
      v68 = 0;
      if ( v131 )
      {
        *(_DWORD *)&v28[16 * a3[33]] = 12;
        *(_QWORD *)&v28[16 * a3[33] + 8] = *(_QWORD *)(v67 + 64);
        v68 = *(unsigned __int8 *)(v67 + 2);
      }
      v69 = 0;
      *(_DWORD *)&v28[16 * a3[16]] = 3;
      if ( a1 != -168 )
      {
        v69 = 2 * (*(_DWORD *)(a1 + 200) & 1);
        if ( (*(_DWORD *)(a1 + 200) & 0x800) != 0 )
          v69 |= 0x10000u;
      }
      v70 = v69 | 1;
      if ( !a16 )
        v70 = v69;
      v71 = v70 | 0x4000;
      if ( !v68 )
        v71 = v70;
      if ( (*(_DWORD *)(a1 + 52) & 0x2000) != 0 )
        v71 |= 0x100000u;
      v72 = v71 | 0x200000;
      if ( !v142 )
        v72 = v71;
      v45 = (_DWORD)v122 == 0;
      *(_DWORD *)&v28[16 * a3[16] + 8] = v72;
      if ( !v45 || v117 )
        *(_DWORD *)&v28[16 * a3[16] + 8] |= 0x2000000u;
      v73 = v136;
      *(_DWORD *)&v28[16 * a3[40]] = 3;
      *(_DWORD *)&v28[16 * a3[40] + 8] = ***(_DWORD ***)(v73 + 8);
      *((_QWORD *)&v155 + 1) = 1;
      v156 = 0;
      *(_QWORD *)&v155 = a1;
      *((_QWORD *)v30 + 70) = a1;
      if ( *(_DWORD *)(a1 + 680) == 1 )
        v30[1] |= 0x80000u;
      *v30 |= 0x80u;
      *((_QWORD *)v30 + 1) = &v155;
      *v30 |= 0x20u;
      *((_QWORD *)v30 + 8) = *(_QWORD *)(*(_QWORD *)(a1 + 480) + 32LL);
      *v30 |= 0x800u;
      v30[20] = ***(_DWORD ***)(v73 + 8);
      if ( FeAcquireCompletionHandle(v25, &v126) )
        v126 = FeAcquireGenericCompletionHandle();
      *v30 |= 0x4000u;
      *((_QWORD *)v30 + 13) = v126;
      v74 = *(_QWORD *)(a1 + 480);
      v150 = *(_QWORD *)(v74 + 16);
      LODWORD(v149) = *(unsigned __int16 *)(v74 + 10);
      *v30 |= 8u;
      *((_QWORD *)v30 + 6) = &v149;
      *v30 |= 0x10u;
      *((_QWORD *)v30 + 7) = *(_QWORD *)(*(_QWORD *)(a1 + 488) + 64LL);
      *v30 |= 0x40000u;
      v30[35] = 0;
      if ( (*(_DWORD *)(a1 + 52) & 0x2000) != 0 )
      {
        v75 = v143;
        *v30 |= 0x20000000u;
        *((_QWORD *)v30 + 26) = v75 + 72;
        if ( *(_DWORD *)(v75 + 464) )
        {
          *v30 |= 0x10000000u;
          v30[51] = *(_DWORD *)(v75 + 464);
        }
        *v30 |= 0x40000000u;
        *((_QWORD *)v30 + 27) = v75;
      }
      if ( *(_QWORD *)(a1 + 248) )
      {
        WfpAleQueryPeerTokenInformation(a1, &v145, &v144);
        if ( v144 )
        {
          v152 = v144 + 224;
          LODWORD(v151) = *(_DWORD *)(v144 + 72);
          *(_DWORD *)&v28[16 * a3[9]] = 16;
          *(_QWORD *)&v28[16 * a3[9] + 8] = &v151;
        }
        if ( v145 )
        {
          v154 = v145 + 224;
          LODWORD(v153) = *(_DWORD *)(v145 + 72);
          *(_DWORD *)&v28[16 * a3[10]] = 16;
          *(_QWORD *)&v28[16 * a3[10] + 8] = &v153;
        }
      }
      if ( *(_QWORD *)(a1 + 544) )
        inserted = WfpAleQueryOrInsertEndpointHandle();
      else
        inserted = 0;
      *v30 |= 0x8000u;
      *((_QWORD *)v30 + 14) = a17;
      if ( inserted )
      {
        *v30 |= 0x4000000u;
        *((_QWORD *)v30 + 24) = inserted;
      }
      v77 = DWORD2(v158);
      if ( DWORD2(v158) )
      {
        *v30 |= 0x20000u;
        v30[30] = v77;
      }
      v78 = v159;
      if ( (_QWORD)v159 )
      {
        *v30 |= 0x10000u;
        *((_QWORD *)v30 + 16) = v78;
        v30[34] = DWORD2(v159);
      }
      v79 = v160;
      if ( (_QWORD)v160 )
      {
        *v30 |= 0x800000u;
        *((_QWORD *)v30 + 18) = v79;
        v30[38] = DWORD2(v160);
      }
      *((_QWORD *)v30 + 34) = a19;
      *((_QWORD *)v30 + 63) = *(_QWORD *)(a1 + 352);
      if ( !KfdAleAcquireFlowHandleForFlow(a1, 0, &v137) )
      {
        *v30 |= 2u;
        *((_QWORD *)v30 + 4) = v137;
        if ( (*(_DWORD *)(a1 + 52) & 0x2000) != 0 )
        {
          v80 = *(_QWORD *)(a1 + 448);
          if ( v80 )
            *(_QWORD *)(v80 + 504) = v137;
        }
        KfdAleReleaseFlowHandleForFlow(a1);
      }
      *((_BYTE *)v30 + 592) = v115;
      v81 = v146;
      *(_OWORD *)(v30 + 150) = v54;
      *((_QWORD *)v30 + 77) = v81;
      v111 = (__int64)v128;
      v82 = v130;
      *(_OWORD *)(v30 + 162) = v55;
      *(_OWORD *)(v30 + 166) = v56;
      PeerInformationForPeerName = WfpAleClassify((unsigned int)&v134, (_DWORD)v30, 0, 0, v82, v111);
      if ( PeerInformationForPeerName )
        goto LABEL_194;
      v83 = (__int64)v128;
      if ( *v128 != 4097 && ((_DWORD)v122 || v117) )
      {
        if ( (_DWORD)Entry )
          *(_DWORD *)&v28[16 * a3[16] + 8] |= 1u;
        *(_DWORD *)&v28[16 * a3[16] + 8] &= ~0x2000000u;
        if ( P[1] )
        {
          ExFreePoolWithTag(P[1], 0);
          P[1] = 0;
          LODWORD(P[0]) = 0;
        }
        v84 = *(_QWORD *)(a1 + 488);
        v125 = v84 + 224;
        LODWORD(v124) = *(_DWORD *)(v84 + 72);
        v85 = *(_DWORD **)(v84 + 280);
        v86 = *(_QWORD *)(v84 + 144);
        v139 = v85;
        if ( v86 )
        {
          PeerInformationForPeerName = WfpAleMarshalFqbnValue(*(_QWORD *)(*(_QWORD *)(v86 + 8) + 32LL), P);
          if ( PeerInformationForPeerName )
            goto LABEL_194;
          v85 = v139;
          v83 = (__int64)v128;
        }
        v87 = *(_QWORD *)(a1 + 728);
        if ( v87 )
        {
          v88 = v87 + 104;
          v89 = -1;
          v121 = v88;
          do
            v45 = *(_WORD *)(v88 + 2 * v89++ + 2) == 0;
          while ( !v45 );
          v90 = 2 * v89 + 2;
        }
        else
        {
          v90 = 0;
          v121 = 0;
        }
        LODWORD(v120) = v90;
        v91 = *(_QWORD *)(a1 + 488);
        v92 = *(_BYTE *)(v91 + 152);
        v93 = *(_QWORD *)(v91 + 176);
        v94 = *(_OWORD *)(v91 + 160);
        v95 = *(_OWORD *)(v91 + 192);
        v96 = *(_OWORD *)(v91 + 208);
        *(_DWORD *)&v28[16 * a3[2]] = 16;
        *(_QWORD *)&v28[16 * a3[2] + 8] = &v124;
        *((_BYTE *)v30 + 592) = v92;
        v97 = &gAleNullSid;
        *(_OWORD *)(v30 + 150) = v94;
        *((_QWORD *)v30 + 77) = v93;
        if ( v85 )
          v97 = v85;
        *(_OWORD *)(v30 + 162) = v95;
        *(_OWORD *)(v30 + 166) = v96;
        *(_DWORD *)&v28[16 * a3[37]] = 13;
        *(_QWORD *)&v28[16 * a3[37] + 8] = v97;
        *(_DWORD *)&v28[16 * a3[39]] = 12;
        *(_QWORD *)&v28[16 * a3[39] + 8] = &v120;
        WfpAleLogEndpointNrtRecordInfo(
          v129,
          *(unsigned __int16 *)(a1 + 60),
          v133,
          *(_QWORD *)(a1 + 728),
          (__int64)&v134);
        *(_DWORD *)&v28[16 * a3[38]] = 12;
        *(_QWORD *)&v28[16 * a3[38] + 8] = P;
        *(_OWORD *)&v28[16 * a3[7]] = *v138;
        *(_DWORD *)&v28[16 * a3[8]] = 2;
        v98 = a3[8];
        v99 = (_BYTE *)v130;
        v110 = v130;
        *(_WORD *)&v28[16 * v98 + 8] = __ROR2__(v116, 8);
        PeerInformationForPeerName = WfpAleClassify((unsigned int)&v134, (_DWORD)v30, 0, 0, v110, v83);
        if ( PeerInformationForPeerName )
          goto LABEL_194;
      }
      else
      {
        v99 = (_BYTE *)v130;
      }
      PeerInformationForPeerName = WfpAleProcessPostClassifySocketOptions(a1, v30);
      if ( !PeerInformationForPeerName )
      {
        PeerInformationForPeerName = WfpAleOptionalSetPeerInformation(a1, v131);
        if ( !PeerInformationForPeerName )
        {
          if ( (*(_DWORD *)(a1 + 48) & 0x4000) == 0 )
            goto LABEL_192;
          PeerInformationForPeerName = WfpAllocateFromPerProcessorLookasideList(authorizeContextPPLookasideList, &v140);
          if ( !PeerInformationForPeerName )
          {
            v100 = (int)v140;
            v101 = 2;
            v102 = v140;
            do
            {
              v102 += 8;
              v103 = *v25;
              v25 += 8;
              *(v102 - 8) = v103;
              *(v102 - 7) = *(v25 - 7);
              *(v102 - 6) = *(v25 - 6);
              *(v102 - 5) = *(v25 - 5);
              *(v102 - 4) = *(v25 - 4);
              *(v102 - 3) = *(v25 - 3);
              *(v102 - 2) = *(v25 - 2);
              *(v102 - 1) = *(v25 - 1);
              --v101;
            }
            while ( v101 );
            *v102 = *v25;
            v102[1] = v25[1];
            v102[2] = v25[2];
            v102[3] = v25[3];
            v102[4] = v25[4];
            PeerInformationForPeerName = WfpAleSecureSocketAdd(
                                           a1,
                                           *(unsigned __int16 *)(a1 + 60),
                                           (unsigned int)WfpAlepAuthorizeConnectSecureCompletion,
                                           v100,
                                           0);
            if ( !PeerInformationForPeerName )
            {
              *v99 = 1;
LABEL_192:
              if ( (*(_DWORD *)(a1 + 48) & 0x40) == 0 )
                _InterlockedOr((volatile signed __int32 *)(a1 + 48), 0x40u);
            }
          }
        }
      }
LABEL_194:
      v32 = v112;
      goto LABEL_28;
    }
    v34 = (char *)gIncomingValuesLookasideList
        + 128 * (unsigned __int64)(unsigned int)(HIDWORD(KeGetPcr()[1].LockArray) + 1);
    if ( !v34[176] )
      PplpLazyInitializeLookasideList(gIncomingValuesLookasideList, v34 + 64);
    ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v34 + 64), Entry);
  }
  v32 = 0;
  v30 = 0;
  if ( (_BYTE)v114 )
    WfpLowerIrqlFromDispatchLevel(HIBYTE(v114));
  PeerInformationForPeerName = -1073741670;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
  {
    WPP_SF_sd(
      WPP_GLOBAL_Control->AttachedDevice,
      10,
      (unsigned int)&WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
      (unsigned int)"WfpAlepAuthorizeConnect",
      154);
  }
LABEL_28:
  if ( v126 )
  {
    FeReleaseCompletionHandle(v126, v26);
    v126 = 0;
  }
  if ( P[1] )
  {
    ExFreePoolWithTag(P[1], 0);
    P[1] = 0;
    LODWORD(P[0]) = 0;
  }
  v104 = (unsigned int)dword_1402202D8;
  if ( (unsigned int)dword_1402202D8 > 3 && (HIDWORD(v104) = HIDWORD(qword_1402202E8), (qword_1402202E8 & 4) != 0) )
  {
    v105 = v123;
    v104 = qword_1402202F0 & 4;
    if ( v104 == qword_1402202F0 )
      v104 = WfpCalloutDiagTraceRedirectedAuthConnect(a1, v123, a17, v27, PeerInformationForPeerName);
  }
  else
  {
    v105 = v123;
  }
  if ( v105 )
    v104 = KfdAleReleaseFlowHandleForFlow(v105);
  if ( v131 )
  {
    if ( *(_DWORD *)(a1 + 40) != 6 || (*(_DWORD *)(a1 + 48) & 0x10) != 0 )
    {
      v104 = WfpAleReleasePeerInformation();
    }
    else
    {
      v104 = (unsigned int)_InterlockedExchangeAdd((volatile signed __int32 *)(v131 + 24), 0xFFFFFFFF);
      if ( (_DWORD)v104 == 1 )
        v104 = WfpAlepFreePeerInformation();
    }
  }
  if ( v32 )
  {
    LODWORD(v104) = HIDWORD(KeGetPcr()[1].LockArray);
    v106 = (PVOID *)((char *)gPerProcessorContext + 72 * v104);
    KfdReleaseTerminatingFilters(v30 + 156);
    if ( v28 == v106[3] )
    {
      *((_BYTE *)v106 + 32) = 0;
    }
    else
    {
      v107 = (char *)gMetadataLookasideList
           + 128 * (unsigned __int64)(unsigned int)(HIDWORD(KeGetPcr()[1].LockArray) + 1);
      if ( !v107[176] )
        PplpLazyInitializeLookasideList(gMetadataLookasideList, v107 + 64);
      ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v107 + 64), v30);
      v108 = (char *)gIncomingValuesLookasideList
           + 128 * (unsigned __int64)(unsigned int)(HIDWORD(KeGetPcr()[1].LockArray) + 1);
      if ( !v108[176] )
        PplpLazyInitializeLookasideList(gIncomingValuesLookasideList, v108 + 64);
      ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v108 + 64), v28);
    }
    if ( (_BYTE)v114 )
      WfpLowerIrqlFromDispatchLevel(HIBYTE(v114));
  }
  if ( PeerInformationForPeerName
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
  {
    WPP_SF_sd(
      WPP_GLOBAL_Control->AttachedDevice,
      15,
      (unsigned int)&WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
      (unsigned int)"WfpAlepAuthorizeConnect",
      PeerInformationForPeerName);
  }
  return PeerInformationForPeerName;
}

```

## disassembly

```asm
0x140137e90  mov     rax, rsp
0x140137e93  push    rbp
0x140137e94  push    rbx
0x140137e95  lea     rbp, [rax-178h]
0x140137e9c  sub     rsp, 268h
0x140137ea3  mov     [rax-18h], rsi
0x140137ea7  xorps   xmm0, xmm0
0x140137eaa  mov     [rax-20h], rdi
0x140137eae  mov     rsi, rcx
0x140137eb1  mov     rcx, [rbp+170h+arg_98]
0x140137eb8  mov     [rax-28h], r12
0x140137ebc  mov     r12, r8
0x140137ebf  mov     [rax-30h], r13
0x140137ec3  movzx   r8d, dx
0x140137ec7  mov     [rax-38h], r14
0x140137ecb  mov     r14, [rbp+170h+arg_68]
0x140137ed2  mov     [rax-40h], r15
0x140137ed6  mov     rax, [rbp+170h+arg_40]
0x140137edd  mov     [rbp+170h+var_1A8], rax
0x140137ee1  mov     rax, [rbp+170h+arg_48]
0x140137ee8  mov     [rbp+170h+var_158], rax
0x140137eec  movzx   eax, [rbp+170h+arg_50]
0x140137ef3  mov     [rsp+66h], ax
0x140137ef8  mov     rax, [rbp+170h+arg_58]
0x140137eff  mov     [rbp+170h+var_140], rax
0x140137f03  mov     rax, [rbp+170h+arg_60]
0x140137f0a  mov     [rbp+170h+var_170], rax
0x140137f0e  mov     rax, [rbp+170h+arg_88]
0x140137f15  mov     [rbp+170h+var_1A0], rax
0x140137f19  mov     rax, [rbp+170h+arg_A0]
0x140137f20  mov     [rbp+170h+var_B8], rax
0x140137f27  mov     rax, [rbp+170h+arg_A8]
0x140137f2e  mov     [rbp+170h+var_150], rax
0x140137f32  xor     al, al
0x140137f34  mov     word ptr [rsp+270h+var_208+4], dx
0x140137f39  xor     edx, edx
0x140137f3b  mov     r13d, edx
0x140137f3e  mov     byte ptr [rsp+270h+var_210], al
0x140137f42  mov     r15d, edx
0x140137f45  mov     rax, [rsi+1C0h]
0x140137f4c  mov     edi, edx
0x140137f4e  mov     [rbp+170h+var_168], r9
0x140137f52  lea     r9, WPP_GLOBAL_Control
0x140137f59  mov     [rbp+170h+var_130], rax
0x140137f5d  mov     ebx, edx
0x140137f5f  mov     [rbp+170h+var_1B0], rcx
0x140137f63  mov     [rbp+170h+var_148], rdx
0x140137f67  mov     [rbp+170h+var_198], rdx
0x140137f6b  mov     [rsp+270h+Entry], rdx
0x140137f70  mov     [rbp+170h+var_1E8], rdx
0x140137f74  mov     byte ptr [rsp+270h+var_210+3], dl
0x140137f78  mov     byte ptr [rsp+270h+var_210+2], dl
0x140137f7c  mov     [rbp+170h+var_1E0], rdx
0x140137f80  movups  xmmword ptr [rbp+170h+P], xmm0
0x140137f84  mov     [rbp+170h+var_1C8], rdx
0x140137f88  cmp     [rbp+170h+arg_78], dl
0x140137f8e  jz      short loc_140137FF6
0x140137f90  test    rax, rax
0x140137f93  jz      short loc_140137FF6
0x140137f95  cmp     [rax+1D0h], edx
0x140137f9b  jz      short loc_140137FA6
0x140137f9d  cmp     [rax+1D8h], rdx
0x140137fa4  jnz     short loc_140137FF6
0x140137fa6  mov     dword ptr [rcx], 1001h
0x140137fac  mov     rcx, cs:WPP_GLOBAL_Control
0x140137fb3  mov     rbx, 0FFFFFFFFC0000022h
0x140137fba  cmp     rcx, r9
0x140137fbd  jz      short loc_140137FEE
0x140137fbf  cmp     byte ptr [rcx+29h], 2
0x140137fc3  jb      short loc_140137FEE
0x140137fc5  test    dword ptr [rcx+2Ch], 1000h
0x140137fcc  jz      short loc_140137FEE
0x140137fce  mov     rcx, [rcx+18h]
0x140137fd2  lea     r9, aWfpalepauthori_7; "WfpAlepAuthorizeConnect"
0x140137fd9  mov     edx, 0Ah
0x140137fde  mov     dword ptr [rsp+270h+var_250], ebx
0x140137fe2  lea     r8, WPP_dc97c17fd6903ad537f842808d057dba_Traceguids
0x140137fe9  call    WPP_SF_sd
0x140137fee  xor     r12b, r12b
0x140137ff1  jmp     loc_14013820C
0x140137ff6  movaps  [rsp+270h+var_58+8], xmm6
0x140137ffe  movzx   ecx, r8w
0x140138002  mov     dword ptr [rsp+270h+var_208], edx
0x140138006  lea     rdx, [rsp+270h+var_208]
0x14013800b  movaps  [rsp+270h+var_68+8], xmm7
0x140138013  movaps  [rsp+270h+var_78+8], xmm8
0x14013801c  mov     [rsi+1A0h], r8w
0x140138024  call    cs:__imp_KfdGetLayerCacheEpoch
0x14013802b  nop     dword ptr [rax+rax+00h]
0x140138030  mov     eax, dword ptr [rsp+270h+var_208]
0x140138034  mov     [rsi+198h], eax
0x14013803a  cmp     [rbp+170h+arg_70], ebx
0x140138040  jz      short loc_140138057
0x140138042  mov     eax, [rsi+30h]
0x140138045  bt      eax, 0Eh
0x140138049  jb      short loc_140138057
0x14013804b  cmp     cs:gAleEnableNameOnSecureSocket, ebx
0x140138051  jz      loc_1401391E7
0x140138057  xor     eax, eax
0x140138059  mov     [rbp+170h+var_128], rdi
0x14013805d  xorps   xmm0, xmm0
0x140138060  mov     qword ptr [rbp+170h+var_18C], rax
0x140138064  mov     qword ptr [rbp+170h+var_10C], rax
0x140138068  mov     qword ptr [rbp+170h+var_1D4], rax
0x14013806c  mov     qword ptr [rbp+170h+var_EC], rax
0x140138073  mov     qword ptr [rbp+170h+var_DC], rax
0x14013807a  mov     qword ptr [rbp+170h+var_FC], rax
0x14013807e  mov     [rsp+270h+var_1F8+4], rax
0x140138083  mov     [rbp-20h], rax
0x140138087  mov     [rbp+60h], rax
0x14013808b  mov     [rbp-68h], rax
0x14013808f  mov     [rbp+80h], rax
0x140138096  mov     [rbp+90h], rax
0x14013809d  mov     [rbp+70h], rax
0x1401380a1  mov     [rsp+270h+var_1F8], rax
0x1401380a6  movups  [rbp+170h+var_D0], xmm0
0x1401380ad  mov     [rbp+170h+var_C0], rax
0x1401380b4  movups  [rbp+170h+var_180], xmm0
0x1401380b8  mov     [rbp+170h+var_120], rdi
0x1401380bc  movups  [rbp+170h+var_B0], xmm0
0x1401380c3  mov     [rbp+170h+var_160], rdi
0x1401380c7  movups  [rbp+170h+var_A0], xmm0
0x1401380ce  movups  [rbp+170h+var_90], xmm0
0x1401380d5  call    cs:__imp_KeGetCurrentIrql
0x1401380dc  nop     dword ptr [rax+rax+00h]
0x1401380e1  cmp     al, 2
0x1401380e3  jnb     short loc_1401380F3
0x1401380e5  call    WfpRaiseIrqlToDispatchLevel
0x1401380ea  mov     byte ptr [rsp+270h+var_210+3], al
0x1401380ee  mov     byte ptr [rsp+270h+var_210+2], 1
0x1401380f3  mov     ecx, gs:1A4h
0x1401380fb  lea     r8, [rcx+rcx*8]
0x1401380ff  mov     rcx, cs:gPerProcessorContext
0x140138106  cmp     [rcx+r8*8+20h], dil
0x14013810b  jnz     short loc_140138122
0x14013810d  mov     r15, [rcx+r8*8+18h]
0x140138112  mov     rdi, [rcx+r8*8+10h]
0x140138117  mov     byte ptr [rcx+r8*8+20h], 1
0x14013811d  jmp     loc_14013823A
0x140138122  mov     rcx, cs:gIncomingValuesLookasideList
0x140138129  lea     rdx, [rsp+270h+Entry]
0x14013812e  call    WfpAllocateFromPerProcessorLookasideList
0x140138133  test    rax, rax
0x140138136  jnz     short loc_140138193
0x140138138  mov     rcx, cs:gMetadataLookasideList
0x14013813f  lea     rdx, [rbp+170h+var_1E8]
0x140138143  call    WfpAllocateFromPerProcessorLookasideList
0x140138148  test    rax, rax
0x14013814b  jz      loc_140138231
0x140138151  mov     eax, gs:1A4h
0x140138159  mov     rcx, cs:gIncomingValuesLookasideList
0x140138160  lea     ebx, [rax+1]
0x140138163  shl     rbx, 7
0x140138167  add     rbx, rcx
0x14013816a  movzx   eax, byte ptr [rbx+0B0h]
0x140138171  test    al, al
0x140138173  jnz     short loc_14013817E
0x140138175  lea     rdx, [rbx+40h]
0x140138179  call    PplpLazyInitializeLookasideList
0x14013817e  mov     rdx, [rsp+270h+Entry]; Entry
0x140138183  lea     rcx, [rbx+40h]; Lookaside
0x140138187  call    cs:__imp_ExFreeToLookasideListEx
0x14013818e  nop     dword ptr [rax+rax+00h]
0x140138193  xor     r12b, r12b
0x140138196  mov     rdi, r15
0x140138199  cmp     byte ptr [rsp+270h+var_210+2], r13b
0x14013819e  jz      short loc_1401381AA
0x1401381a0  movzx   ecx, byte ptr [rsp+270h+var_210+3]
0x1401381a5  call    WfpLowerIrqlFromDispatchLevel
0x1401381aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1401381b1  lea     rax, WPP_GLOBAL_Control
0x1401381b8  mov     rbx, 0FFFFFFFFC000009Ah
0x1401381bf  cmp     rcx, rax
0x1401381c2  jz      short loc_1401381F3
0x1401381c4  cmp     byte ptr [rcx+29h], 2
0x1401381c8  jb      short loc_1401381F3
0x1401381ca  test    dword ptr [rcx+2Ch], 1000h
0x1401381d1  jz      short loc_1401381F3
0x1401381d3  mov     rcx, [rcx+18h]
0x1401381d7  lea     r9, aWfpalepauthori_7; "WfpAlepAuthorizeConnect"
0x1401381de  mov     edx, 0Ah
0x1401381e3  mov     dword ptr [rsp+270h+var_250], ebx
0x1401381e7  lea     r8, WPP_dc97c17fd6903ad537f842808d057dba_Traceguids
0x1401381ee  call    WPP_SF_sd
0x1401381f3  movaps  xmm7, [rsp+270h+var_68+8]
0x1401381fb  movaps  xmm6, [rsp+270h+var_58+8]
0x140138203  movaps  xmm8, [rsp+270h+var_78+8]
0x14013820c  mov     rcx, [rbp+170h+var_1C8]
0x140138210  test    rcx, rcx
0x140138213  jz      loc_1401391F2
0x140138219  call    cs:__imp_FeReleaseCompletionHandle
0x140138220  nop     dword ptr [rax+rax+00h]
0x140138225  xor     r14d, r14d
0x140138228  mov     [rbp+170h+var_1C8], r14
0x14013822c  jmp     loc_1401391F5
0x140138231  mov     r15, [rsp+270h+Entry]
0x140138236  mov     rdi, [rbp+170h+var_1E8]
0x14013823a  xor     edx, edx; Val
0x14013823c  mov     r8d, 2A0h; Size
0x140138242  mov     rcx, r15; void *
0x140138245  call    memset
0x14013824a  xor     edx, edx; Val
0x14013824c  mov     r8d, 2A8h; Size
0x140138252  mov     rcx, rdi; void *
0x140138255  call    memset
0x14013825a  lea     rax, [rdi+270h]
0x140138261  mov     [rax+8], rax
0x140138265  mov     [rax], rax
0x140138268  mov     eax, [rsi+34h]
0x14013826b  bt      eax, 10h
0x14013826f  jnb     loc_14013832B
0x140138275  mov     eax, [rsi+34h]
0x140138278  bt      eax, 0Dh
0x14013827c  jnb     short loc_14013828B
0x14013827e  mov     eax, [rsi+30h]
0x140138281  bt      eax, 18h
0x140138285  jb      loc_14013832B
0x14013828b  mov     rax, [rsi+1C0h]
0x140138292  test    rax, rax
0x140138295  jnz     short loc_1401382F2
0x140138297  mov     rax, [rbp+170h+var_1B0]
0x14013829b  mov     dword ptr [rax], 1001h
0x1401382a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1401382a8  lea     rax, WPP_GLOBAL_Control
0x1401382af  mov     rbx, 0FFFFFFFFC0000022h
0x1401382b6  cmp     rcx, rax
0x1401382b9  jz      short loc_1401382EA
0x1401382bb  cmp     byte ptr [rcx+29h], 2
0x1401382bf  jb      short loc_1401382EA
0x1401382c1  test    dword ptr [rcx+2Ch], 1000h
0x1401382c8  jz      short loc_1401382EA
0x1401382ca  mov     rcx, [rcx+18h]
0x1401382ce  lea     r9, aWfpalepauthori_7; "WfpAlepAuthorizeConnect"
0x1401382d5  mov     edx, 0Ah
0x1401382da  mov     dword ptr [rsp+270h+var_250], ebx
0x1401382de  lea     r8, WPP_dc97c17fd6903ad537f842808d057dba_Traceguids
0x1401382e5  call    WPP_SF_sd
0x1401382ea  mov     r12b, 1
0x1401382ed  jmp     loc_1401381F3
0x1401382f2  mov     byte ptr [rsp+270h+var_210], 1
0x1401382f7  mov     r13, rax
0x1401382fa  mov     rax, [rax+30h]
0x1401382fe  test    rax, rax
0x140138301  jnz     short loc_1401382F7
0x140138303  mov     rcx, [r13+1F8h]
0x14013830a  call    cs:__imp_KfdAleAcquireEndpointContextFromFlow
0x140138311  nop     dword ptr [rax+rax+00h]
0x140138316  mov     [rbp+170h+var_1E0], rax
0x14013831a  mov     rbx, rax
0x14013831d  test    rax, rax
0x140138320  jz      short loc_140138346
0x140138322  mov     r13, [rax+1C0h]
0x140138329  jmp     short loc_140138346
0x14013832b  mov     eax, [rsi+34h]
0x14013832e  mov     byte ptr [rsp+270h+var_210], 1
0x140138333  bt      eax, 0Dh
0x140138337  jnb     short loc_140138346
0x140138339  mov     eax, [rsi+34h]
0x14013833c  bt      eax, 10h
0x140138340  jb      short loc_140138346
0x140138342  mov     r13, [rbp+170h+var_130]
0x140138346  mov     eax, [rsi+34h]
0x140138349  bt      eax, 0Dh
0x14013834d  jnb     short loc_14013836D
0x14013834f  mov     eax, [rsi+34h]
0x140138352  bt      eax, 10h
0x140138356  jb      short loc_14013836D
0x140138358  mov     eax, [rsi+30h]
0x14013835b  bt      eax, 18h
0x14013835f  jb      short loc_14013836D
0x140138361  mov     dword ptr [rbp+170h+var_1E8], 1
0x140138368  test    r13, r13
0x14013836b  jnz     short loc_140138374
0x14013836d  mov     dword ptr [rbp+170h+var_1E8], 0
0x140138374  mov     eax, [rsi+34h]
0x140138377  bt      eax, 10h
0x14013837b  jnb     short loc_140138397
0x14013837d  mov     eax, [rsi+30h]
0x140138380  bt      eax, 18h
0x140138384  jb      short loc_140138397
0x140138386  test    rbx, rbx
0x140138389  jz      short loc_140138397
0x14013838b  test    r13, r13
0x14013838e  jz      short loc_140138397
0x140138390  mov     edx, 1
0x140138395  jmp     short loc_140138399
0x140138397  xor     edx, edx
0x140138399  mov     rcx, [rsi+1E0h]
0x1401383a0  movzx   eax, word ptr [rsp+270h+var_208+4]
0x1401383a5  mov     word ptr [rbp+170h+var_180], ax
0x1401383a9  movzx   eax, word ptr [r12]
0x1401383ae  mov     dword ptr [rbp+170h+var_180+4], eax
0x1401383b1  mov     qword ptr [rbp+170h+var_180+8], r15
0x1401383b5  mov     rax, [rcx+10h]
0x1401383b9  mov     qword ptr [rbp+170h+var_18C+4], rax
0x1401383bd  movzx   eax, word ptr [rcx+0Ah]
0x1401383c1  lea     rcx, [rbp+170h+var_190]
0x1401383c5  mov     [rbp+170h+var_190], eax
0x1401383c8  movzx   eax, word ptr [r12+2]
0x1401383ce  add     rax, rax
  ... truncated ...
```
