# WfpAlepAuthorizeConnect

- ea: `0x140137d00`
- end: `0x140139276`
- name: `WfpAlepAuthorizeConnect`
- size: `5494`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400cd0b0`

## callees

- `0x1400515e8`
- `0x140052390`
- `0x140053850`
- `0x140053910`
- `0x140053e04`
- `0x140054f00`
- `0x140055820`
- `0x140073a00`
- `0x14008a370`
- `0x1400ddcf4`
- `0x1400e5208`
- `0x1400f79f8`
- `0x1400f85cc`
- `0x14010c6cc`
- `0x1401366f0`
- `0x140137d00`
- `0x14013c8f0`
- `0x14014f258`
- `0x1401502cc`
- `0x140171614`
- `0x1401bf940`

## import_xrefs

- `ntoskrnl!ExFreeToLookasideListEx` at `0x140137ff7`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1401391ac`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1401391ec`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140137ff7`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1401391ac`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1401391ec`
- `ntoskrnl!KeGetCurrentIrql` at `0x140137f45`
- `ntoskrnl!KeGetCurrentIrql` at `0x140137f45`
- `ntoskrnl!ExFreePoolWithTag` at `0x140138d11`
- `ntoskrnl!ExFreePoolWithTag` at `0x140139070`
- `ntoskrnl!ExFreePoolWithTag` at `0x140138d11`
- `ntoskrnl!ExFreePoolWithTag` at `0x140139070`
- `NETIO!WfpCalloutDiagTraceRedirectedAuthConnect` at `0x1401390c5`
- `NETIO!WfpCalloutDiagTraceRedirectedAuthConnect` at `0x1401390c5`
- `NETIO!FeReleaseCompletionHandle` at `0x140138089`
- `NETIO!FeReleaseCompletionHandle` at `0x140138089`
- `NETIO!FeAcquireGenericCompletionHandle` at `0x140138a0b`
- `NETIO!FeAcquireGenericCompletionHandle` at `0x140138a0b`
- `NETIO!FeAcquireCompletionHandle` at `0x1401389fa`
- `NETIO!FeAcquireCompletionHandle` at `0x1401389fa`
- `NETIO!KfdAleAcquireEndpointContextFromFlow` at `0x14013817a`
- `NETIO!KfdAleAcquireEndpointContextFromFlow` at `0x14013817a`
- `NETIO!KfdReleaseTerminatingFilters` at `0x14013915d`
- `NETIO!KfdReleaseTerminatingFilters` at `0x14013915d`
- `NETIO!KfdAleReleaseFlowHandleForFlow` at `0x140138c55`
- `NETIO!KfdAleReleaseFlowHandleForFlow` at `0x1401390e7`
- `NETIO!KfdAleReleaseFlowHandleForFlow` at `0x140138c55`
- `NETIO!KfdAleReleaseFlowHandleForFlow` at `0x1401390e7`
- `NETIO!KfdAleAcquireFlowHandleForFlow` at `0x140138c16`
- `NETIO!KfdAleAcquireFlowHandleForFlow` at `0x140138c16`
- `NETIO!KfdGetLayerCacheEpoch` at `0x140137e94`
- `NETIO!KfdGetLayerCacheEpoch` at `0x140137e94`

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
  __int64 *v58; // rdx
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
  __int64 *v97; // rdx
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
        (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
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
              (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
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
      v58 = (__int64 *)Entry;
      if ( Entry )
      {
        if ( (*(_DWORD *)(v125 + 44) & 0x4000) != 0 )
          _InterlockedOr((volatile signed __int32 *)(a1 + 48), 0x2000000u);
      }
      else
      {
        v58 = gAleNullSid;
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
        v97 = gAleNullSid;
        *(_OWORD *)(v30 + 150) = v94;
        *((_QWORD *)v30 + 77) = v93;
        if ( v85 )
          v97 = (__int64 *)v85;
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
      (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
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
  v104 = (unsigned int)dword_1402202A0;
  if ( (unsigned int)dword_1402202A0 > 3 && (HIDWORD(v104) = HIDWORD(qword_1402202B0), (qword_1402202B0 & 4) != 0) )
  {
    v105 = v123;
    v104 = qword_1402202B8 & 4;
    if ( v104 == qword_1402202B8 )
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
      (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
      (unsigned int)"WfpAlepAuthorizeConnect",
      PeerInformationForPeerName);
  }
  return PeerInformationForPeerName;
}

```

## disassembly

```asm
0x140137d00  mov     rax, rsp
0x140137d03  push    rbp
0x140137d04  push    rbx
0x140137d05  lea     rbp, [rax-178h]
0x140137d0c  sub     rsp, 268h
0x140137d13  mov     [rax-18h], rsi
0x140137d17  xorps   xmm0, xmm0
0x140137d1a  mov     [rax-20h], rdi
0x140137d1e  mov     rsi, rcx
0x140137d21  mov     rcx, [rbp+170h+arg_98]
0x140137d28  mov     [rax-28h], r12
0x140137d2c  mov     r12, r8
0x140137d2f  mov     [rax-30h], r13
0x140137d33  movzx   r8d, dx
0x140137d37  mov     [rax-38h], r14
0x140137d3b  mov     r14, [rbp+170h+arg_68]
0x140137d42  mov     [rax-40h], r15
0x140137d46  mov     rax, [rbp+170h+arg_40]
0x140137d4d  mov     [rbp+170h+var_1A8], rax
0x140137d51  mov     rax, [rbp+170h+arg_48]
0x140137d58  mov     [rbp+170h+var_158], rax
0x140137d5c  movzx   eax, [rbp+170h+arg_50]
0x140137d63  mov     [rsp+66h], ax
0x140137d68  mov     rax, [rbp+170h+arg_58]
0x140137d6f  mov     [rbp+170h+var_140], rax
0x140137d73  mov     rax, [rbp+170h+arg_60]
0x140137d7a  mov     [rbp+170h+var_170], rax
0x140137d7e  mov     rax, [rbp+170h+arg_88]
0x140137d85  mov     [rbp+170h+var_1A0], rax
0x140137d89  mov     rax, [rbp+170h+arg_A0]
0x140137d90  mov     [rbp+170h+var_B8], rax
0x140137d97  mov     rax, [rbp+170h+arg_A8]
0x140137d9e  mov     [rbp+170h+var_150], rax
0x140137da2  xor     al, al
0x140137da4  mov     word ptr [rsp+270h+var_208+4], dx
0x140137da9  xor     edx, edx
0x140137dab  mov     r13d, edx
0x140137dae  mov     byte ptr [rsp+270h+var_210], al
0x140137db2  mov     r15d, edx
0x140137db5  mov     rax, [rsi+1C0h]
0x140137dbc  mov     edi, edx
0x140137dbe  mov     [rbp+170h+var_168], r9
0x140137dc2  lea     r9, WPP_GLOBAL_Control
0x140137dc9  mov     [rbp+170h+var_130], rax
0x140137dcd  mov     ebx, edx
0x140137dcf  mov     [rbp+170h+var_1B0], rcx
0x140137dd3  mov     [rbp+170h+var_148], rdx
0x140137dd7  mov     [rbp+170h+var_198], rdx
0x140137ddb  mov     [rsp+270h+Entry], rdx
0x140137de0  mov     [rbp+170h+var_1E8], rdx
0x140137de4  mov     byte ptr [rsp+270h+var_210+3], dl
0x140137de8  mov     byte ptr [rsp+270h+var_210+2], dl
0x140137dec  mov     [rbp+170h+var_1E0], rdx
0x140137df0  movups  xmmword ptr [rbp+170h+P], xmm0
0x140137df4  mov     [rbp+170h+var_1C8], rdx
0x140137df8  cmp     [rbp+170h+arg_78], dl
0x140137dfe  jz      short loc_140137E66
0x140137e00  test    rax, rax
0x140137e03  jz      short loc_140137E66
0x140137e05  cmp     [rax+1D0h], edx
0x140137e0b  jz      short loc_140137E16
0x140137e0d  cmp     [rax+1D8h], rdx
0x140137e14  jnz     short loc_140137E66
0x140137e16  mov     dword ptr [rcx], 1001h
0x140137e1c  mov     rcx, cs:WPP_GLOBAL_Control
0x140137e23  mov     rbx, 0FFFFFFFFC0000022h
0x140137e2a  cmp     rcx, r9
0x140137e2d  jz      short loc_140137E5E
0x140137e2f  cmp     byte ptr [rcx+29h], 2
0x140137e33  jb      short loc_140137E5E
0x140137e35  test    dword ptr [rcx+2Ch], 1000h
0x140137e3c  jz      short loc_140137E5E
0x140137e3e  mov     rcx, [rcx+18h]
0x140137e42  lea     r9, aWfpalepauthori_7; "WfpAlepAuthorizeConnect"
0x140137e49  mov     edx, 0Ah
0x140137e4e  mov     dword ptr [rsp+270h+var_250], ebx
0x140137e52  lea     r8, WPP_dc97c17fd6903ad537f842808d057dba_Traceguids
0x140137e59  call    WPP_SF_sd
0x140137e5e  xor     r12b, r12b
0x140137e61  jmp     loc_14013807C
0x140137e66  movaps  [rsp+270h+var_58+8], xmm6
0x140137e6e  movzx   ecx, r8w
0x140137e72  mov     dword ptr [rsp+270h+var_208], edx
0x140137e76  lea     rdx, [rsp+270h+var_208]
0x140137e7b  movaps  [rsp+270h+var_68+8], xmm7
0x140137e83  movaps  [rsp+270h+var_78+8], xmm8
0x140137e8c  mov     [rsi+1A0h], r8w
0x140137e94  call    cs:__imp_KfdGetLayerCacheEpoch
0x140137e9b  nop     dword ptr [rax+rax+00h]
0x140137ea0  mov     eax, dword ptr [rsp+270h+var_208]
0x140137ea4  mov     [rsi+198h], eax
0x140137eaa  cmp     [rbp+170h+arg_70], ebx
0x140137eb0  jz      short loc_140137EC7
0x140137eb2  mov     eax, [rsi+30h]
0x140137eb5  bt      eax, 0Eh
0x140137eb9  jb      short loc_140137EC7
0x140137ebb  cmp     cs:gAleEnableNameOnSecureSocket, ebx
0x140137ec1  jz      loc_140139057
0x140137ec7  xor     eax, eax
0x140137ec9  mov     [rbp+170h+var_128], rdi
0x140137ecd  xorps   xmm0, xmm0
0x140137ed0  mov     qword ptr [rbp+170h+var_18C], rax
0x140137ed4  mov     qword ptr [rbp+170h+var_10C], rax
0x140137ed8  mov     qword ptr [rbp+170h+var_1D4], rax
0x140137edc  mov     qword ptr [rbp+170h+var_EC], rax
0x140137ee3  mov     qword ptr [rbp+170h+var_DC], rax
0x140137eea  mov     qword ptr [rbp+170h+var_FC], rax
0x140137eee  mov     [rsp+270h+var_1F8+4], rax
0x140137ef3  mov     [rbp-20h], rax
0x140137ef7  mov     [rbp+60h], rax
0x140137efb  mov     [rbp-68h], rax
0x140137eff  mov     [rbp+80h], rax
0x140137f06  mov     [rbp+90h], rax
0x140137f0d  mov     [rbp+70h], rax
0x140137f11  mov     [rsp+270h+var_1F8], rax
0x140137f16  movups  [rbp+170h+var_D0], xmm0
0x140137f1d  mov     [rbp+170h+var_C0], rax
0x140137f24  movups  [rbp+170h+var_180], xmm0
0x140137f28  mov     [rbp+170h+var_120], rdi
0x140137f2c  movups  [rbp+170h+var_B0], xmm0
0x140137f33  mov     [rbp+170h+var_160], rdi
0x140137f37  movups  [rbp+170h+var_A0], xmm0
0x140137f3e  movups  [rbp+170h+var_90], xmm0
0x140137f45  call    cs:__imp_KeGetCurrentIrql
0x140137f4c  nop     dword ptr [rax+rax+00h]
0x140137f51  cmp     al, 2
0x140137f53  jnb     short loc_140137F63
0x140137f55  call    WfpRaiseIrqlToDispatchLevel
0x140137f5a  mov     byte ptr [rsp+270h+var_210+3], al
0x140137f5e  mov     byte ptr [rsp+270h+var_210+2], 1
0x140137f63  mov     ecx, gs:1A4h
0x140137f6b  lea     r8, [rcx+rcx*8]
0x140137f6f  mov     rcx, cs:gPerProcessorContext
0x140137f76  cmp     [rcx+r8*8+20h], dil
0x140137f7b  jnz     short loc_140137F92
0x140137f7d  mov     r15, [rcx+r8*8+18h]
0x140137f82  mov     rdi, [rcx+r8*8+10h]
0x140137f87  mov     byte ptr [rcx+r8*8+20h], 1
0x140137f8d  jmp     loc_1401380AA
0x140137f92  mov     rcx, cs:gIncomingValuesLookasideList
0x140137f99  lea     rdx, [rsp+270h+Entry]
0x140137f9e  call    WfpAllocateFromPerProcessorLookasideList
0x140137fa3  test    rax, rax
0x140137fa6  jnz     short loc_140138003
0x140137fa8  mov     rcx, cs:gMetadataLookasideList
0x140137faf  lea     rdx, [rbp+170h+var_1E8]
0x140137fb3  call    WfpAllocateFromPerProcessorLookasideList
0x140137fb8  test    rax, rax
0x140137fbb  jz      loc_1401380A1
0x140137fc1  mov     eax, gs:1A4h
0x140137fc9  mov     rcx, cs:gIncomingValuesLookasideList
0x140137fd0  lea     ebx, [rax+1]
0x140137fd3  shl     rbx, 7
0x140137fd7  add     rbx, rcx
0x140137fda  movzx   eax, byte ptr [rbx+0B0h]
0x140137fe1  test    al, al
0x140137fe3  jnz     short loc_140137FEE
0x140137fe5  lea     rdx, [rbx+40h]
0x140137fe9  call    PplpLazyInitializeLookasideList
0x140137fee  mov     rdx, [rsp+270h+Entry]; Entry
0x140137ff3  lea     rcx, [rbx+40h]; Lookaside
0x140137ff7  call    cs:__imp_ExFreeToLookasideListEx
0x140137ffe  nop     dword ptr [rax+rax+00h]
0x140138003  xor     r12b, r12b
0x140138006  mov     rdi, r15
0x140138009  cmp     byte ptr [rsp+270h+var_210+2], r13b
0x14013800e  jz      short loc_14013801A
0x140138010  movzx   ecx, byte ptr [rsp+270h+var_210+3]
0x140138015  call    WfpLowerIrqlFromDispatchLevel
0x14013801a  mov     rcx, cs:WPP_GLOBAL_Control
0x140138021  lea     rax, WPP_GLOBAL_Control
0x140138028  mov     rbx, 0FFFFFFFFC000009Ah
0x14013802f  cmp     rcx, rax
0x140138032  jz      short loc_140138063
0x140138034  cmp     byte ptr [rcx+29h], 2
0x140138038  jb      short loc_140138063
0x14013803a  test    dword ptr [rcx+2Ch], 1000h
0x140138041  jz      short loc_140138063
0x140138043  mov     rcx, [rcx+18h]
0x140138047  lea     r9, aWfpalepauthori_7; "WfpAlepAuthorizeConnect"
0x14013804e  mov     edx, 0Ah
0x140138053  mov     dword ptr [rsp+270h+var_250], ebx
0x140138057  lea     r8, WPP_dc97c17fd6903ad537f842808d057dba_Traceguids
0x14013805e  call    WPP_SF_sd
0x140138063  movaps  xmm7, [rsp+270h+var_68+8]
0x14013806b  movaps  xmm6, [rsp+270h+var_58+8]
0x140138073  movaps  xmm8, [rsp+270h+var_78+8]
0x14013807c  mov     rcx, [rbp+170h+var_1C8]
0x140138080  test    rcx, rcx
0x140138083  jz      loc_140139062
0x140138089  call    cs:__imp_FeReleaseCompletionHandle
0x140138090  nop     dword ptr [rax+rax+00h]
0x140138095  xor     r14d, r14d
0x140138098  mov     [rbp+170h+var_1C8], r14
0x14013809c  jmp     loc_140139065
0x1401380a1  mov     r15, [rsp+270h+Entry]
0x1401380a6  mov     rdi, [rbp+170h+var_1E8]
0x1401380aa  xor     edx, edx; Val
0x1401380ac  mov     r8d, 2A0h; Size
0x1401380b2  mov     rcx, r15; void *
0x1401380b5  call    memset
0x1401380ba  xor     edx, edx; Val
0x1401380bc  mov     r8d, 2A8h; Size
0x1401380c2  mov     rcx, rdi; void *
0x1401380c5  call    memset
0x1401380ca  lea     rax, [rdi+270h]
0x1401380d1  mov     [rax+8], rax
0x1401380d5  mov     [rax], rax
0x1401380d8  mov     eax, [rsi+34h]
0x1401380db  bt      eax, 10h
0x1401380df  jnb     loc_14013819B
0x1401380e5  mov     eax, [rsi+34h]
0x1401380e8  bt      eax, 0Dh
0x1401380ec  jnb     short loc_1401380FB
0x1401380ee  mov     eax, [rsi+30h]
0x1401380f1  bt      eax, 18h
0x1401380f5  jb      loc_14013819B
0x1401380fb  mov     rax, [rsi+1C0h]
0x140138102  test    rax, rax
0x140138105  jnz     short loc_140138162
0x140138107  mov     rax, [rbp+170h+var_1B0]
0x14013810b  mov     dword ptr [rax], 1001h
0x140138111  mov     rcx, cs:WPP_GLOBAL_Control
0x140138118  lea     rax, WPP_GLOBAL_Control
0x14013811f  mov     rbx, 0FFFFFFFFC0000022h
0x140138126  cmp     rcx, rax
0x140138129  jz      short loc_14013815A
0x14013812b  cmp     byte ptr [rcx+29h], 2
0x14013812f  jb      short loc_14013815A
0x140138131  test    dword ptr [rcx+2Ch], 1000h
0x140138138  jz      short loc_14013815A
0x14013813a  mov     rcx, [rcx+18h]
0x14013813e  lea     r9, aWfpalepauthori_7; "WfpAlepAuthorizeConnect"
0x140138145  mov     edx, 0Ah
0x14013814a  mov     dword ptr [rsp+270h+var_250], ebx
0x14013814e  lea     r8, WPP_dc97c17fd6903ad537f842808d057dba_Traceguids
0x140138155  call    WPP_SF_sd
0x14013815a  mov     r12b, 1
0x14013815d  jmp     loc_140138063
0x140138162  mov     byte ptr [rsp+270h+var_210], 1
0x140138167  mov     r13, rax
0x14013816a  mov     rax, [rax+30h]
0x14013816e  test    rax, rax
0x140138171  jnz     short loc_140138167
0x140138173  mov     rcx, [r13+1F8h]
0x14013817a  call    cs:__imp_KfdAleAcquireEndpointContextFromFlow
0x140138181  nop     dword ptr [rax+rax+00h]
0x140138186  mov     [rbp+170h+var_1E0], rax
0x14013818a  mov     rbx, rax
0x14013818d  test    rax, rax
0x140138190  jz      short loc_1401381B6
0x140138192  mov     r13, [rax+1C0h]
0x140138199  jmp     short loc_1401381B6
0x14013819b  mov     eax, [rsi+34h]
0x14013819e  mov     byte ptr [rsp+270h+var_210], 1
0x1401381a3  bt      eax, 0Dh
0x1401381a7  jnb     short loc_1401381B6
0x1401381a9  mov     eax, [rsi+34h]
0x1401381ac  bt      eax, 10h
0x1401381b0  jb      short loc_1401381B6
0x1401381b2  mov     r13, [rbp+170h+var_130]
0x1401381b6  mov     eax, [rsi+34h]
0x1401381b9  bt      eax, 0Dh
0x1401381bd  jnb     short loc_1401381DD
0x1401381bf  mov     eax, [rsi+34h]
0x1401381c2  bt      eax, 10h
0x1401381c6  jb      short loc_1401381DD
0x1401381c8  mov     eax, [rsi+30h]
0x1401381cb  bt      eax, 18h
0x1401381cf  jb      short loc_1401381DD
0x1401381d1  mov     dword ptr [rbp+170h+var_1E8], 1
0x1401381d8  test    r13, r13
0x1401381db  jnz     short loc_1401381E4
0x1401381dd  mov     dword ptr [rbp+170h+var_1E8], 0
0x1401381e4  mov     eax, [rsi+34h]
0x1401381e7  bt      eax, 10h
0x1401381eb  jnb     short loc_140138207
0x1401381ed  mov     eax, [rsi+30h]
0x1401381f0  bt      eax, 18h
0x1401381f4  jb      short loc_140138207
0x1401381f6  test    rbx, rbx
0x1401381f9  jz      short loc_140138207
0x1401381fb  test    r13, r13
0x1401381fe  jz      short loc_140138207
0x140138200  mov     edx, 1
0x140138205  jmp     short loc_140138209
0x140138207  xor     edx, edx
0x140138209  mov     rcx, [rsi+1E0h]
0x140138210  movzx   eax, word ptr [rsp+270h+var_208+4]
0x140138215  mov     word ptr [rbp+170h+var_180], ax
0x140138219  movzx   eax, word ptr [r12]
0x14013821e  mov     dword ptr [rbp+170h+var_180+4], eax
0x140138221  mov     qword ptr [rbp+170h+var_180+8], r15
0x140138225  mov     rax, [rcx+10h]
0x140138229  mov     qword ptr [rbp+170h+var_18C+4], rax
0x14013822d  movzx   eax, word ptr [rcx+0Ah]
0x140138231  lea     rcx, [rbp+170h+var_190]
0x140138235  mov     [rbp+170h+var_190], eax
0x140138238  movzx   eax, word ptr [r12+2]
0x14013823e  add     rax, rax
  ... truncated ...
```
