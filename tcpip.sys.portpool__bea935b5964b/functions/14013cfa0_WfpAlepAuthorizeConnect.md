# WfpAlepAuthorizeConnect

- ea: `0x14013cfa0`
- end: `0x14013e516`
- name: `WfpAlepAuthorizeConnect`
- size: `5494`
- prototype: `__int64 __fastcall(__int64, unsigned __int16, unsigned __int16 *, __int64, _OWORD *, __int16, char, char, __int64, _OWORD *, unsigned __int16, __int64, __int64, __int128 *, int, unsigned __int8, __int64, __int64, __int64, _DWORD *, _DWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `21`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14001c4b0`

## callees

- `0x14001215c`
- `0x140012f00`
- `0x1400143c0`
- `0x140014480`
- `0x140014974`
- `0x140015a70`
- `0x140016470`
- `0x14006150c`
- `0x14009f27c`
- `0x1400ad6a0`
- `0x1400e4064`
- `0x1400ffa98`
- `0x1401014ac`
- `0x1401163cc`
- `0x14013b990`
- `0x14013cfa0`
- `0x140141b90`
- `0x140150f98`
- `0x14015200c`
- `0x140173314`
- `0x1401c1580`

## import_xrefs

- `ntoskrnl!ExFreeToLookasideListEx` at `0x14013d297`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14013e44c`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14013e48c`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14013d297`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14013e44c`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14013e48c`
- `ntoskrnl!KeGetCurrentIrql` at `0x14013d1e5`
- `ntoskrnl!KeGetCurrentIrql` at `0x14013d1e5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14013dfb1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14013e310`
- `ntoskrnl!ExFreePoolWithTag` at `0x14013dfb1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14013e310`
- `NETIO!WfpCalloutDiagTraceRedirectedAuthConnect` at `0x14013e365`
- `NETIO!WfpCalloutDiagTraceRedirectedAuthConnect` at `0x14013e365`
- `NETIO!FeReleaseCompletionHandle` at `0x14013d329`
- `NETIO!FeReleaseCompletionHandle` at `0x14013d329`
- `NETIO!FeAcquireGenericCompletionHandle` at `0x14013dcab`
- `NETIO!FeAcquireGenericCompletionHandle` at `0x14013dcab`
- `NETIO!FeAcquireCompletionHandle` at `0x14013dc9a`
- `NETIO!FeAcquireCompletionHandle` at `0x14013dc9a`
- `NETIO!KfdAleAcquireEndpointContextFromFlow` at `0x14013d41a`
- `NETIO!KfdAleAcquireEndpointContextFromFlow` at `0x14013d41a`
- `NETIO!KfdReleaseTerminatingFilters` at `0x14013e3fd`
- `NETIO!KfdReleaseTerminatingFilters` at `0x14013e3fd`
- `NETIO!KfdAleReleaseFlowHandleForFlow` at `0x14013def5`
- `NETIO!KfdAleReleaseFlowHandleForFlow` at `0x14013e387`
- `NETIO!KfdAleReleaseFlowHandleForFlow` at `0x14013def5`
- `NETIO!KfdAleReleaseFlowHandleForFlow` at `0x14013e387`
- `NETIO!KfdAleAcquireFlowHandleForFlow` at `0x14013deb6`
- `NETIO!KfdAleAcquireFlowHandleForFlow` at `0x14013deb6`
- `NETIO!KfdGetLayerCacheEpoch` at `0x14013d134`
- `NETIO!KfdGetLayerCacheEpoch` at `0x14013d134`

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
  __int64 v24; // r8
  __int128 *v25; // r14
  __int64 v26; // rdx
  __int64 v27; // r13
  char *v28; // r15
  __int64 v29; // rax
  _DWORD *v30; // rdi
  __int64 PeerInformationForPeerName; // rbx
  char v32; // r12
  __int64 v33; // rcx
  __int64 v34; // r8
  __int64 v35; // r9
  char *v36; // rbx
  __int64 v37; // rax
  __int64 v38; // rax
  BOOL v39; // edx
  __int64 v40; // rcx
  __int64 v41; // rax
  __int64 v42; // rax
  __int64 v43; // rcx
  __int64 v44; // rax
  __int64 v45; // rcx
  __int64 v46; // rax
  bool v47; // zf
  __int64 v48; // rax
  __int64 v49; // r9
  int v50; // edx
  __int64 v51; // rcx
  void *v52; // rax
  __int64 v53; // rcx
  __int64 v54; // rax
  int v55; // eax
  __int128 v56; // xmm6
  __int128 v57; // xmm7
  __int128 v58; // xmm8
  int v59; // r8d
  __int64 *v60; // rdx
  __int64 v61; // rax
  __int64 v62; // rbx
  __int64 v63; // rax
  __int64 v64; // rdx
  int ProfileIdFromInterface; // eax
  int v66; // ecx
  __int64 v67; // rcx
  __int64 i; // rcx
  __int64 v69; // rdx
  int v70; // r8d
  int v71; // ecx
  int v72; // eax
  int v73; // edx
  int v74; // ecx
  __int64 v75; // r9
  __int64 v76; // rcx
  __int64 v77; // rcx
  __int64 v78; // rcx
  __int64 inserted; // rax
  int v80; // eax
  __int64 v81; // rax
  __int64 v82; // rax
  __int64 v83; // rcx
  __int64 v84; // rax
  __int64 v85; // rax
  __int64 v86; // rbx
  __int64 v87; // rcx
  _DWORD *v88; // r8
  __int64 v89; // rcx
  __int64 v90; // rcx
  __int64 v91; // rcx
  __int64 v92; // rax
  int v93; // eax
  __int64 v94; // rax
  char v95; // dl
  __int64 v96; // rcx
  __int128 v97; // xmm0
  __int128 v98; // xmm1
  __int128 v99; // xmm2
  __int64 *v100; // rdx
  __int64 v101; // rax
  _BYTE *v102; // r12
  __int64 v103; // r9
  __int64 v104; // rcx
  __int128 *v105; // rax
  __int128 v106; // xmm0
  __int64 v107; // rax
  __int64 v108; // r14
  PVOID *v109; // rsi
  __int64 v110; // r8
  __int64 v111; // r9
  char *v112; // rsi
  __int64 v113; // r8
  __int64 v114; // r9
  char *v115; // rdi
  __int64 v117; // [rsp+28h] [rbp-E0h]
  __int64 v118; // [rsp+30h] [rbp-D8h]
  char v119; // [rsp+68h] [rbp-A0h]
  bool v120; // [rsp+69h] [rbp-9Fh]
  __int16 v121; // [rsp+6Ah] [rbp-9Eh]
  char v122; // [rsp+6Ch] [rbp-9Ch]
  unsigned __int16 v123; // [rsp+6Eh] [rbp-9Ah]
  BOOL v124; // [rsp+70h] [rbp-98h] BYREF
  unsigned __int16 v125; // [rsp+74h] [rbp-94h]
  PVOID Entry; // [rsp+78h] [rbp-90h] BYREF
  __int64 v127; // [rsp+80h] [rbp-88h] BYREF
  __int64 v128; // [rsp+88h] [rbp-80h]
  _DWORD *v129; // [rsp+90h] [rbp-78h] BYREF
  __int64 v130; // [rsp+98h] [rbp-70h]
  __int64 v131; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v132; // [rsp+A8h] [rbp-60h]
  __int64 v133; // [rsp+B0h] [rbp-58h] BYREF
  PVOID P[2]; // [rsp+B8h] [rbp-50h] BYREF
  _DWORD *v135; // [rsp+C8h] [rbp-40h]
  __int64 v136; // [rsp+D0h] [rbp-38h]
  __int64 v137; // [rsp+D8h] [rbp-30h]
  __int64 v138; // [rsp+E0h] [rbp-28h] BYREF
  __int64 v139; // [rsp+E8h] [rbp-20h] BYREF
  __int64 v140; // [rsp+F0h] [rbp-18h]
  __int128 v141; // [rsp+F8h] [rbp-10h] BYREF
  __int64 v142; // [rsp+108h] [rbp+0h]
  __int64 v143; // [rsp+110h] [rbp+8h]
  __int64 v144; // [rsp+118h] [rbp+10h] BYREF
  _OWORD *v145; // [rsp+120h] [rbp+18h]
  _DWORD *v146; // [rsp+128h] [rbp+20h]
  __int128 *v147; // [rsp+130h] [rbp+28h] BYREF
  __int64 v148; // [rsp+138h] [rbp+30h]
  __int64 v149; // [rsp+140h] [rbp+38h]
  __int64 v150; // [rsp+148h] [rbp+40h]
  __int64 v151; // [rsp+150h] [rbp+48h] BYREF
  __int64 v152; // [rsp+158h] [rbp+50h] BYREF
  __int64 v153; // [rsp+160h] [rbp+58h]
  __int64 v154; // [rsp+168h] [rbp+60h] BYREF
  __int64 v155; // [rsp+170h] [rbp+68h]
  __int64 v156; // [rsp+178h] [rbp+70h] BYREF
  __int64 v157; // [rsp+180h] [rbp+78h]
  __int64 v158; // [rsp+188h] [rbp+80h] BYREF
  __int64 v159; // [rsp+190h] [rbp+88h]
  __int64 v160; // [rsp+198h] [rbp+90h] BYREF
  __int64 v161; // [rsp+1A0h] [rbp+98h]
  __int128 v162; // [rsp+1A8h] [rbp+A0h] BYREF
  __int64 v163; // [rsp+1B8h] [rbp+B0h]
  _DWORD *v164; // [rsp+1C0h] [rbp+B8h]
  __int128 v165; // [rsp+1C8h] [rbp+C0h]
  __int128 v166; // [rsp+1D8h] [rbp+D0h]
  __int128 v167; // [rsp+1E8h] [rbp+E0h]

  v24 = a2;
  v25 = a14;
  v136 = a9;
  v145 = a10;
  v123 = a11;
  v148 = a12;
  v142 = a13;
  v137 = a18;
  v164 = a21;
  v146 = a22;
  v125 = a2;
  v26 = 0;
  v27 = 0;
  v119 = 0;
  v28 = 0;
  v29 = *(_QWORD *)(a1 + 448);
  v30 = 0;
  v143 = a4;
  v150 = v29;
  PeerInformationForPeerName = 0;
  v135 = a20;
  v147 = 0;
  v138 = 0;
  Entry = 0;
  v129 = 0;
  v121 = 0;
  v130 = 0;
  *(_OWORD *)P = 0;
  v133 = 0;
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
  v124 = 0;
  *(_WORD *)(a1 + 416) = v24;
  KfdGetLayerCacheEpoch((unsigned __int16)v24, &v124);
  *(_DWORD *)(a1 + 408) = v124;
  if ( a15 && (*(_DWORD *)(a1 + 48) & 0x4000) == 0 && !gAleEnableNameOnSecureSocket )
    goto LABEL_194;
  v151 = 0;
  LODWORD(v140) = 0;
  LODWORD(v155) = 0;
  LODWORD(v132) = 0;
  LODWORD(v159) = 0;
  LODWORD(v161) = 0;
  LODWORD(v157) = 0;
  LODWORD(v128) = 0;
  v139 = 0;
  v154 = 0;
  v131 = 0;
  v158 = 0;
  v160 = 0;
  v156 = 0;
  v127 = 0;
  v162 = 0;
  v163 = 0;
  v141 = 0;
  v152 = 0;
  v165 = 0;
  v144 = 0;
  v166 = 0;
  v167 = 0;
  if ( KeGetCurrentIrql() < 2u )
  {
    HIBYTE(v121) = WfpRaiseIrqlToDispatchLevel();
    LOBYTE(v121) = 1;
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
    if ( !WfpAllocateFromPerProcessorLookasideList(gMetadataLookasideList, &v129) )
    {
      v28 = (char *)Entry;
      v30 = v129;
LABEL_31:
      memset(v28, 0, 0x2A0u);
      memset(v30, 0, 0x2A8u);
      *((_QWORD *)v30 + 79) = v30 + 156;
      *((_QWORD *)v30 + 78) = v30 + 156;
      if ( (*(_DWORD *)(a1 + 52) & 0x10000) == 0
        || (*(_DWORD *)(a1 + 52) & 0x2000) != 0 && (*(_DWORD *)(a1 + 48) & 0x1000000) != 0 )
      {
        v119 = 1;
        if ( (*(_DWORD *)(a1 + 52) & 0x2000) != 0 && (*(_DWORD *)(a1 + 52) & 0x10000) == 0 )
          v27 = v150;
      }
      else
      {
        v37 = *(_QWORD *)(a1 + 448);
        if ( !v37 )
        {
          *v135 = 4097;
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
        v119 = 1;
        do
        {
          v27 = v37;
          v37 = *(_QWORD *)(v37 + 48);
        }
        while ( v37 );
        v38 = KfdAleAcquireEndpointContextFromFlow(*(_QWORD *)(v27 + 504), v26);
        v130 = v38;
        PeerInformationForPeerName = v38;
        if ( v38 )
          v27 = *(_QWORD *)(v38 + 448);
      }
      if ( (*(_DWORD *)(a1 + 52) & 0x2000) == 0
        || (*(_DWORD *)(a1 + 52) & 0x10000) != 0
        || (*(_DWORD *)(a1 + 48) & 0x1000000) != 0
        || (LODWORD(v129) = 1, !v27) )
      {
        LODWORD(v129) = 0;
      }
      v39 = (*(_DWORD *)(a1 + 52) & 0x10000) != 0
         && (*(_DWORD *)(a1 + 48) & 0x1000000) == 0
         && PeerInformationForPeerName
         && v27;
      v40 = *(_QWORD *)(a1 + 480);
      LOWORD(v141) = v125;
      DWORD1(v141) = *a3;
      *((_QWORD *)&v141 + 1) = v28;
      v140 = *(_QWORD *)(v40 + 16);
      LODWORD(v139) = *(unsigned __int16 *)(v40 + 10);
      v41 = 2LL * a3[1];
      v124 = v39;
      *(_DWORD *)&v28[8 * v41] = 12;
      *(_QWORD *)&v28[16 * a3[1] + 8] = &v139;
      if ( v39 )
      {
        v132 = *(_QWORD *)(PeerInformationForPeerName + 488) + 224LL;
        LODWORD(v131) = *(_DWORD *)(*(_QWORD *)(PeerInformationForPeerName + 488) + 72LL);
        v42 = *(_QWORD *)(PeerInformationForPeerName + 488);
        Entry = *(PVOID *)(v42 + 280);
        v43 = *(_QWORD *)(v42 + 144);
        if ( v43 )
        {
          PeerInformationForPeerName = WfpAleMarshalFqbnValue(*(_QWORD *)(*(_QWORD *)(v43 + 8) + 32LL), P);
          if ( PeerInformationForPeerName )
            goto LABEL_194;
          PeerInformationForPeerName = v130;
        }
        v44 = *(_QWORD *)(PeerInformationForPeerName + 728);
        if ( v44 )
          v128 = v44 + 104;
        else
          v128 = 0;
        v45 = *(_QWORD *)(PeerInformationForPeerName + 728);
        if ( v45 )
        {
          v46 = -1;
          do
            v47 = *(_WORD *)(v45 + 2 * v46++ + 106) == 0;
          while ( !v47 );
          LODWORD(v127) = 2 * v46 + 2;
        }
        else
        {
          LODWORD(v127) = 0;
        }
        v48 = *(_QWORD *)(PeerInformationForPeerName + 488);
        v49 = *(_QWORD *)(PeerInformationForPeerName + 728);
        v50 = *(unsigned __int16 *)(PeerInformationForPeerName + 60);
      }
      else
      {
        v51 = *(_QWORD *)(a1 + 488);
        v132 = v51 + 224;
        LODWORD(v131) = *(_DWORD *)(v51 + 72);
        v52 = *(void **)(v51 + 280);
        v53 = *(_QWORD *)(v51 + 144);
        Entry = v52;
        if ( v53 )
        {
          PeerInformationForPeerName = WfpAleMarshalFqbnValue(*(_QWORD *)(*(_QWORD *)(v53 + 8) + 32LL), P);
          if ( PeerInformationForPeerName )
            goto LABEL_194;
        }
        v49 = *(_QWORD *)(a1 + 728);
        if ( v49 )
        {
          v54 = -1;
          v128 = v49 + 104;
          do
            v47 = *(_WORD *)(v49 + 104 + 2 * v54++ + 2) == 0;
          while ( !v47 );
          v55 = 2 * v54 + 2;
        }
        else
        {
          v55 = 0;
          v128 = 0;
        }
        v50 = *(unsigned __int16 *)(a1 + 60);
        LODWORD(v127) = v55;
        v48 = *(_QWORD *)(a1 + 488);
      }
      v56 = *(_OWORD *)(v48 + 160);
      v57 = *(_OWORD *)(v48 + 192);
      v122 = *(_BYTE *)(v48 + 152);
      v58 = *(_OWORD *)(v48 + 208);
      v153 = *(_QWORD *)(v48 + 176);
      WfpAleLogEndpointNrtRecordInfo(v136, v50, v140, v49, (__int64)&v141);
      v60 = (__int64 *)Entry;
      if ( Entry )
      {
        if ( (*(_DWORD *)(v132 + 44) & 0x4000) != 0 )
          _InterlockedOr((volatile signed __int32 *)(a1 + 48), 0x2000000u);
      }
      else
      {
        v60 = gAleNullSid;
      }
      *(_DWORD *)&v28[16 * a3[41]] = 16;
      *(_QWORD *)&v28[16 * a3[41] + 8] = &v131;
      *(_DWORD *)&v28[16 * a3[39]] = 12;
      *(_QWORD *)&v28[16 * a3[39] + 8] = &v127;
      *(_DWORD *)&v28[16 * a3[2]] = 16;
      *(_QWORD *)&v28[16 * a3[2] + 8] = &v131;
      *(_DWORD *)&v28[16 * a3[37]] = 13;
      *(_QWORD *)&v28[16 * a3[37] + 8] = v60;
      *(_DWORD *)&v28[16 * a3[38]] = 12;
      *(_QWORD *)&v28[16 * a3[38] + 8] = P;
      v47 = (_DWORD)v129 == 0;
      *(_OWORD *)&v28[16 * a3[3]] = *a5;
      if ( !v47 || v124 )
      {
        if ( *(_WORD *)(v27 + 72) == 23 )
          v120 = !*(_WORD *)(v27 + 80)
              && !*(_WORD *)(v27 + 82)
              && !*(_WORD *)(v27 + 84)
              && !*(_WORD *)(v27 + 86)
              && !*(_WORD *)(v27 + 88)
              && !*(_WORD *)(v27 + 90)
              && !*(_WORD *)(v27 + 92)
              && *(_WORD *)(v27 + 94) == 256;
        else
          v120 = *(_BYTE *)(v27 + 76) == 127;
        PeerInformationForPeerName = WfpAlepAuthOutboundFlowSwizzleDestinationInformation(
                                       (_DWORD)a3,
                                       v27,
                                       v59,
                                       (_DWORD)v145,
                                       (__int64)v28);
        if ( PeerInformationForPeerName )
          goto LABEL_194;
        LODWORD(Entry) = a16;
        a16 = v120;
      }
      else
      {
        v61 = 2LL * a3[7];
        LODWORD(Entry) = 0;
        *(_OWORD *)&v28[8 * v61] = *v145;
        *(_DWORD *)&v28[16 * a3[8]] = 2;
        *(_WORD *)&v28[16 * a3[8] + 8] = __ROR2__(v123, 8);
      }
      v62 = 0;
      v63 = 2LL * a3[6];
      v64 = v143;
      v149 = 0;
      *(_DWORD *)&v28[8 * v63] = 1;
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
      *(_DWORD *)&v28[16 * a3[13] + 8] = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v64 + 8) + 48LL) + 12LL);
      *(_DWORD *)&v28[16 * a3[14]] = 3;
      *(_DWORD *)&v28[16 * a3[14] + 8] = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v64 + 8) + 48LL) + 16LL);
      *(_DWORD *)&v28[16 * a3[19]] = 3;
      *(_DWORD *)&v28[16 * a3[19] + 8] = *(_DWORD *)(*(_QWORD *)(v64 + 8) + 8LL);
      if ( v142 )
      {
        ProfileIdFromInterface = WfpGetProfileIdFromInterface(v142, v64, v64, v148, 0);
        v64 = v143;
      }
      else
      {
        ProfileIdFromInterface = 0;
      }
      v66 = (int)v164;
      *v164 = ProfileIdFromInterface;
      AlepFillEdgeInterfaceRelatedFields(
        v66,
        (_DWORD)a3,
        0,
        0,
        v142,
        v64,
        v148,
        0,
        0,
        ProfileIdFromInterface,
        0,
        (__int64)v28);
      if ( *(_DWORD *)&v28[16 * a3[31]] )
        *v146 = *(_DWORD *)&v28[16 * a3[31] + 8];
      v67 = v142;
      *(_DWORD *)&v28[16 * a3[34]] = 0;
      if ( v67 )
      {
        *(_DWORD *)&v28[16 * a3[35]] = 4;
        *(_QWORD *)&v28[16 * a3[35] + 8] = v67 + 80;
      }
      else
      {
        *(_DWORD *)&v28[16 * a3[35]] = 0;
      }
      if ( *(_QWORD *)(a1 + 448) && (*(_DWORD *)(a1 + 52) & 0x10000) != 0 )
      {
        for ( i = *(_QWORD *)(a1 + 448); *(_QWORD *)(i + 48); i = *(_QWORD *)(i + 48) )
          ;
        v62 = *(_QWORD *)(i + 56);
        v149 = v62;
      }
      if ( v62 )
      {
        v155 = *(_QWORD *)(v62 + 8);
        LODWORD(v154) = *(unsigned __int16 *)(v62 + 2);
        *(_DWORD *)&v28[16 * a3[36]] = 12;
        *(_QWORD *)&v28[16 * a3[36] + 8] = &v154;
      }
      else
      {
        *(_DWORD *)&v28[16 * a3[36]] = 0;
      }
      PeerInformationForPeerName = WfpAleFindPeerInformationForPeerName(a1, v125, v136, v123, (__int64)&v138);
      if ( PeerInformationForPeerName )
        goto LABEL_194;
      v69 = v138;
      v70 = 0;
      if ( v138 )
      {
        *(_DWORD *)&v28[16 * a3[33]] = 12;
        *(_QWORD *)&v28[16 * a3[33] + 8] = *(_QWORD *)(v69 + 64);
        v70 = *(unsigned __int8 *)(v69 + 2);
      }
      v71 = 0;
      *(_DWORD *)&v28[16 * a3[16]] = 3;
      if ( a1 != -168 )
      {
        v71 = 2 * (*(_DWORD *)(a1 + 200) & 1);
        if ( (*(_DWORD *)(a1 + 200) & 0x800) != 0 )
          v71 |= 0x10000u;
      }
      v72 = v71 | 1;
      if ( !a16 )
        v72 = v71;
      v73 = v72 | 0x4000;
      if ( !v70 )
        v73 = v72;
      if ( (*(_DWORD *)(a1 + 52) & 0x2000) != 0 )
        v73 |= 0x100000u;
      v74 = v73 | 0x200000;
      if ( !v149 )
        v74 = v73;
      v47 = (_DWORD)v129 == 0;
      *(_DWORD *)&v28[16 * a3[16] + 8] = v74;
      if ( !v47 || v124 )
        *(_DWORD *)&v28[16 * a3[16] + 8] |= 0x2000000u;
      v75 = v143;
      *(_DWORD *)&v28[16 * a3[40]] = 3;
      *(_DWORD *)&v28[16 * a3[40] + 8] = ***(_DWORD ***)(v75 + 8);
      *((_QWORD *)&v162 + 1) = 1;
      v163 = 0;
      *(_QWORD *)&v162 = a1;
      *((_QWORD *)v30 + 70) = a1;
      if ( *(_DWORD *)(a1 + 680) == 1 )
        v30[1] |= 0x80000u;
      *v30 |= 0x80u;
      *((_QWORD *)v30 + 1) = &v162;
      *v30 |= 0x20u;
      *((_QWORD *)v30 + 8) = *(_QWORD *)(*(_QWORD *)(a1 + 480) + 32LL);
      *v30 |= 0x800u;
      v30[20] = ***(_DWORD ***)(v75 + 8);
      if ( FeAcquireCompletionHandle(v25, &v133) )
        v133 = FeAcquireGenericCompletionHandle();
      *v30 |= 0x4000u;
      *((_QWORD *)v30 + 13) = v133;
      v76 = *(_QWORD *)(a1 + 480);
      v157 = *(_QWORD *)(v76 + 16);
      LODWORD(v156) = *(unsigned __int16 *)(v76 + 10);
      *v30 |= 8u;
      *((_QWORD *)v30 + 6) = &v156;
      *v30 |= 0x10u;
      *((_QWORD *)v30 + 7) = *(_QWORD *)(*(_QWORD *)(a1 + 488) + 64LL);
      *v30 |= 0x40000u;
      v30[35] = 0;
      if ( (*(_DWORD *)(a1 + 52) & 0x2000) != 0 )
      {
        v77 = v150;
        *v30 |= 0x20000000u;
        *((_QWORD *)v30 + 26) = v77 + 72;
        if ( *(_DWORD *)(v77 + 464) )
        {
          *v30 |= 0x10000000u;
          v30[51] = *(_DWORD *)(v77 + 464);
        }
        *v30 |= 0x40000000u;
        *((_QWORD *)v30 + 27) = v77;
      }
      if ( *(_QWORD *)(a1 + 248) )
      {
        WfpAleQueryPeerTokenInformation(a1, &v152, &v151);
        if ( v151 )
        {
          v159 = v151 + 224;
          LODWORD(v158) = *(_DWORD *)(v151 + 72);
          *(_DWORD *)&v28[16 * a3[9]] = 16;
          *(_QWORD *)&v28[16 * a3[9] + 8] = &v158;
        }
        if ( v152 )
        {
          v161 = v152 + 224;
          LODWORD(v160) = *(_DWORD *)(v152 + 72);
          *(_DWORD *)&v28[16 * a3[10]] = 16;
          *(_QWORD *)&v28[16 * a3[10] + 8] = &v160;
        }
      }
      v78 = *(_QWORD *)(a1 + 544);
      if ( v78 )
        inserted = WfpAleQueryOrInsertEndpointHandle(v78);
      else
        inserted = 0;
      *v30 |= 0x8000u;
      *((_QWORD *)v30 + 14) = a17;
      if ( inserted )
      {
        *v30 |= 0x4000000u;
        *((_QWORD *)v30 + 24) = inserted;
      }
      v80 = DWORD2(v165);
      if ( DWORD2(v165) )
      {
        *v30 |= 0x20000u;
        v30[30] = v80;
      }
      v81 = v166;
      if ( (_QWORD)v166 )
      {
        *v30 |= 0x10000u;
        *((_QWORD *)v30 + 16) = v81;
        v30[34] = DWORD2(v166);
      }
      v82 = v167;
      if ( (_QWORD)v167 )
      {
        *v30 |= 0x800000u;
        *((_QWORD *)v30 + 18) = v82;
        v30[38] = DWORD2(v167);
      }
      *((_QWORD *)v30 + 34) = a19;
      *((_QWORD *)v30 + 63) = *(_QWORD *)(a1 + 352);
      if ( !KfdAleAcquireFlowHandleForFlow(a1, 0, &v144) )
      {
        *v30 |= 2u;
        *((_QWORD *)v30 + 4) = v144;
        if ( (*(_DWORD *)(a1 + 52) & 0x2000) != 0 )
        {
          v83 = *(_QWORD *)(a1 + 448);
          if ( v83 )
            *(_QWORD *)(v83 + 504) = v144;
        }
        KfdAleReleaseFlowHandleForFlow(a1);
      }
      *((_BYTE *)v30 + 592) = v122;
      v84 = v153;
      *(_OWORD *)(v30 + 150) = v56;
      *((_QWORD *)v30 + 77) = v84;
      v118 = (__int64)v135;
      v85 = v137;
      *(_OWORD *)(v30 + 162) = v57;
      *(_OWORD *)(v30 + 166) = v58;
      PeerInformationForPeerName = WfpAleClassify((unsigned int)&v141, (_DWORD)v30, 0, 0, v85, v118);
      if ( PeerInformationForPeerName )
        goto LABEL_194;
      v86 = (__int64)v135;
      if ( *v135 != 4097 && ((_DWORD)v129 || v124) )
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
        v87 = *(_QWORD *)(a1 + 488);
        v132 = v87 + 224;
        LODWORD(v131) = *(_DWORD *)(v87 + 72);
        v88 = *(_DWORD **)(v87 + 280);
        v89 = *(_QWORD *)(v87 + 144);
        v146 = v88;
        if ( v89 )
        {
          PeerInformationForPeerName = WfpAleMarshalFqbnValue(*(_QWORD *)(*(_QWORD *)(v89 + 8) + 32LL), P);
          if ( PeerInformationForPeerName )
            goto LABEL_194;
          v88 = v146;
          v86 = (__int64)v135;
        }
        v90 = *(_QWORD *)(a1 + 728);
        if ( v90 )
        {
          v91 = v90 + 104;
          v92 = -1;
          v128 = v91;
          do
            v47 = *(_WORD *)(v91 + 2 * v92++ + 2) == 0;
          while ( !v47 );
          v93 = 2 * v92 + 2;
        }
        else
        {
          v93 = 0;
          v128 = 0;
        }
        LODWORD(v127) = v93;
        v94 = *(_QWORD *)(a1 + 488);
        v95 = *(_BYTE *)(v94 + 152);
        v96 = *(_QWORD *)(v94 + 176);
        v97 = *(_OWORD *)(v94 + 160);
        v98 = *(_OWORD *)(v94 + 192);
        v99 = *(_OWORD *)(v94 + 208);
        *(_DWORD *)&v28[16 * a3[2]] = 16;
        *(_QWORD *)&v28[16 * a3[2] + 8] = &v131;
        *((_BYTE *)v30 + 592) = v95;
        v100 = gAleNullSid;
        *(_OWORD *)(v30 + 150) = v97;
        *((_QWORD *)v30 + 77) = v96;
        if ( v88 )
          v100 = (__int64 *)v88;
        *(_OWORD *)(v30 + 162) = v98;
        *(_OWORD *)(v30 + 166) = v99;
        *(_DWORD *)&v28[16 * a3[37]] = 13;
        *(_QWORD *)&v28[16 * a3[37] + 8] = v100;
        *(_DWORD *)&v28[16 * a3[39]] = 12;
        *(_QWORD *)&v28[16 * a3[39] + 8] = &v127;
        WfpAleLogEndpointNrtRecordInfo(
          v136,
          *(unsigned __int16 *)(a1 + 60),
          v140,
          *(_QWORD *)(a1 + 728),
          (__int64)&v141);
        *(_DWORD *)&v28[16 * a3[38]] = 12;
        *(_QWORD *)&v28[16 * a3[38] + 8] = P;
        *(_OWORD *)&v28[16 * a3[7]] = *v145;
        *(_DWORD *)&v28[16 * a3[8]] = 2;
        v101 = a3[8];
        v102 = (_BYTE *)v137;
        v117 = v137;
        *(_WORD *)&v28[16 * v101 + 8] = __ROR2__(v123, 8);
        PeerInformationForPeerName = WfpAleClassify((unsigned int)&v141, (_DWORD)v30, 0, 0, v117, v86);
        if ( PeerInformationForPeerName )
          goto LABEL_194;
      }
      else
      {
        v102 = (_BYTE *)v137;
      }
      PeerInformationForPeerName = WfpAleProcessPostClassifySocketOptions(a1, v30);
      if ( !PeerInformationForPeerName )
      {
        PeerInformationForPeerName = WfpAleOptionalSetPeerInformation(a1, v138);
        if ( !PeerInformationForPeerName )
        {
          if ( (*(_DWORD *)(a1 + 48) & 0x4000) == 0 )
            goto LABEL_192;
          PeerInformationForPeerName = WfpAllocateFromPerProcessorLookasideList(authorizeContextPPLookasideList, &v147);
          if ( !PeerInformationForPeerName )
          {
            v103 = (__int64)v147;
            v104 = 2;
            v105 = v147;
            do
            {
              v105 += 8;
              v106 = *v25;
              v25 += 8;
              *(v105 - 8) = v106;
              *(v105 - 7) = *(v25 - 7);
              *(v105 - 6) = *(v25 - 6);
              *(v105 - 5) = *(v25 - 5);
              *(v105 - 4) = *(v25 - 4);
              *(v105 - 3) = *(v25 - 3);
              *(v105 - 2) = *(v25 - 2);
              *(v105 - 1) = *(v25 - 1);
              --v104;
            }
            while ( v104 );
            *v105 = *v25;
            v105[1] = v25[1];
            v105[2] = v25[2];
            v105[3] = v25[3];
            v105[4] = v25[4];
            PeerInformationForPeerName = WfpAleSecureSocketAdd(
                                           a1,
                                           *(_WORD *)(a1 + 60),
                                           (__int64)WfpAlepAuthorizeConnectSecureCompletion,
                                           v103,
                                           0);
            if ( !PeerInformationForPeerName )
            {
              *v102 = 1;
LABEL_192:
              if ( (*(_DWORD *)(a1 + 48) & 0x40) == 0 )
                _InterlockedOr((volatile signed __int32 *)(a1 + 48), 0x40u);
            }
          }
        }
      }
LABEL_194:
      v32 = v119;
      goto LABEL_28;
    }
    v36 = (char *)gIncomingValuesLookasideList
        + 128 * (unsigned __int64)(unsigned int)(HIDWORD(KeGetPcr()[1].LockArray) + 1);
    if ( !v36[176] )
      PplpLazyInitializeLookasideList(gIncomingValuesLookasideList, v36 + 64, v34, v35);
    ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v36 + 64), Entry);
  }
  v32 = 0;
  v30 = 0;
  if ( (_BYTE)v121 )
    WfpLowerIrqlFromDispatchLevel(HIBYTE(v121));
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
  if ( v133 )
  {
    FeReleaseCompletionHandle(v133, v26);
    v133 = 0;
  }
  if ( P[1] )
  {
    ExFreePoolWithTag(P[1], 0);
    P[1] = 0;
    LODWORD(P[0]) = 0;
  }
  v107 = (unsigned int)dword_1402242A0;
  if ( (unsigned int)dword_1402242A0 > 3 && (HIDWORD(v107) = HIDWORD(qword_1402242B0), (qword_1402242B0 & 4) != 0) )
  {
    v108 = v130;
    v107 = qword_1402242B8 & 4;
    if ( v107 == qword_1402242B8 )
      v107 = WfpCalloutDiagTraceRedirectedAuthConnect(a1, v130, a17, v27, PeerInformationForPeerName);
  }
  else
  {
    v108 = v130;
  }
  if ( v108 )
    v107 = KfdAleReleaseFlowHandleForFlow(v108);
  if ( v138 )
  {
    if ( *(_DWORD *)(a1 + 40) != 6 || (*(_DWORD *)(a1 + 48) & 0x10) != 0 )
    {
      v107 = WfpAleReleasePeerInformation();
    }
    else
    {
      v107 = (unsigned int)_InterlockedExchangeAdd((volatile signed __int32 *)(v138 + 24), 0xFFFFFFFF);
      if ( (_DWORD)v107 == 1 )
        v107 = WfpAlepFreePeerInformation();
    }
  }
  if ( v32 )
  {
    LODWORD(v107) = HIDWORD(KeGetPcr()[1].LockArray);
    v109 = (PVOID *)((char *)gPerProcessorContext + 72 * v107);
    KfdReleaseTerminatingFilters(v30 + 156, 9 * v107, v24);
    if ( v28 == v109[3] )
    {
      *((_BYTE *)v109 + 32) = 0;
    }
    else
    {
      v112 = (char *)gMetadataLookasideList
           + 128 * (unsigned __int64)(unsigned int)(HIDWORD(KeGetPcr()[1].LockArray) + 1);
      if ( !v112[176] )
        PplpLazyInitializeLookasideList(gMetadataLookasideList, v112 + 64, v110, v111);
      ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v112 + 64), v30);
      v115 = (char *)gIncomingValuesLookasideList
           + 128 * (unsigned __int64)(unsigned int)(HIDWORD(KeGetPcr()[1].LockArray) + 1);
      if ( !v115[176] )
        PplpLazyInitializeLookasideList(gIncomingValuesLookasideList, v115 + 64, v113, v114);
      ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v115 + 64), v28);
    }
    if ( (_BYTE)v121 )
      WfpLowerIrqlFromDispatchLevel(HIBYTE(v121));
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
0x14013cfa0  mov     rax, rsp
0x14013cfa3  push    rbp
0x14013cfa4  push    rbx
0x14013cfa5  lea     rbp, [rax-178h]
0x14013cfac  sub     rsp, 268h
0x14013cfb3  mov     [rax-18h], rsi
0x14013cfb7  xorps   xmm0, xmm0
0x14013cfba  mov     [rax-20h], rdi
0x14013cfbe  mov     rsi, rcx
0x14013cfc1  mov     rcx, [rbp+170h+arg_98]
0x14013cfc8  mov     [rax-28h], r12
0x14013cfcc  mov     r12, r8
0x14013cfcf  mov     [rax-30h], r13
0x14013cfd3  movzx   r8d, dx
0x14013cfd7  mov     [rax-38h], r14
0x14013cfdb  mov     r14, [rbp+170h+arg_68]
0x14013cfe2  mov     [rax-40h], r15
0x14013cfe6  mov     rax, [rbp+170h+arg_40]
0x14013cfed  mov     [rbp+170h+var_1A8], rax
0x14013cff1  mov     rax, [rbp+170h+arg_48]
0x14013cff8  mov     [rbp+170h+var_158], rax
0x14013cffc  movzx   eax, [rbp+170h+arg_50]
0x14013d003  mov     [rsp+66h], ax
0x14013d008  mov     rax, [rbp+170h+arg_58]
0x14013d00f  mov     [rbp+170h+var_140], rax
0x14013d013  mov     rax, [rbp+170h+arg_60]
0x14013d01a  mov     [rbp+170h+var_170], rax
0x14013d01e  mov     rax, [rbp+170h+arg_88]
0x14013d025  mov     [rbp+170h+var_1A0], rax
0x14013d029  mov     rax, [rbp+170h+arg_A0]
0x14013d030  mov     [rbp+170h+var_B8], rax
0x14013d037  mov     rax, [rbp+170h+arg_A8]
0x14013d03e  mov     [rbp+170h+var_150], rax
0x14013d042  xor     al, al
0x14013d044  mov     word ptr [rsp+270h+var_208+4], dx
0x14013d049  xor     edx, edx
0x14013d04b  mov     r13d, edx
0x14013d04e  mov     byte ptr [rsp+270h+var_210], al
0x14013d052  mov     r15d, edx
0x14013d055  mov     rax, [rsi+1C0h]
0x14013d05c  mov     edi, edx
0x14013d05e  mov     [rbp+170h+var_168], r9
0x14013d062  lea     r9, WPP_GLOBAL_Control
0x14013d069  mov     [rbp+170h+var_130], rax
0x14013d06d  mov     ebx, edx
0x14013d06f  mov     [rbp+170h+var_1B0], rcx
0x14013d073  mov     [rbp+170h+var_148], rdx
0x14013d077  mov     [rbp+170h+var_198], rdx
0x14013d07b  mov     [rsp+270h+Entry], rdx
0x14013d080  mov     [rbp+170h+var_1E8], rdx
0x14013d084  mov     byte ptr [rsp+270h+var_210+3], dl
0x14013d088  mov     byte ptr [rsp+270h+var_210+2], dl
0x14013d08c  mov     [rbp+170h+var_1E0], rdx
0x14013d090  movups  xmmword ptr [rbp+170h+P], xmm0
0x14013d094  mov     [rbp+170h+var_1C8], rdx
0x14013d098  cmp     [rbp+170h+arg_78], dl
0x14013d09e  jz      short loc_14013D106
0x14013d0a0  test    rax, rax
0x14013d0a3  jz      short loc_14013D106
0x14013d0a5  cmp     [rax+1D0h], edx
0x14013d0ab  jz      short loc_14013D0B6
0x14013d0ad  cmp     [rax+1D8h], rdx
0x14013d0b4  jnz     short loc_14013D106
0x14013d0b6  mov     dword ptr [rcx], 1001h
0x14013d0bc  mov     rcx, cs:WPP_GLOBAL_Control
0x14013d0c3  mov     rbx, 0FFFFFFFFC0000022h
0x14013d0ca  cmp     rcx, r9
0x14013d0cd  jz      short loc_14013D0FE
0x14013d0cf  cmp     byte ptr [rcx+29h], 2
0x14013d0d3  jb      short loc_14013D0FE
0x14013d0d5  test    dword ptr [rcx+2Ch], 1000h
0x14013d0dc  jz      short loc_14013D0FE
0x14013d0de  mov     rcx, [rcx+18h]
0x14013d0e2  lea     r9, aWfpalepauthori_7; "WfpAlepAuthorizeConnect"
0x14013d0e9  mov     edx, 0Ah
0x14013d0ee  mov     dword ptr [rsp+270h+var_250], ebx
0x14013d0f2  lea     r8, WPP_dc97c17fd6903ad537f842808d057dba_Traceguids
0x14013d0f9  call    WPP_SF_sd
0x14013d0fe  xor     r12b, r12b
0x14013d101  jmp     loc_14013D31C
0x14013d106  movaps  [rsp+270h+var_58+8], xmm6
0x14013d10e  movzx   ecx, r8w
0x14013d112  mov     dword ptr [rsp+270h+var_208], edx
0x14013d116  lea     rdx, [rsp+270h+var_208]
0x14013d11b  movaps  [rsp+270h+var_68+8], xmm7
0x14013d123  movaps  [rsp+270h+var_78+8], xmm8
0x14013d12c  mov     [rsi+1A0h], r8w
0x14013d134  call    cs:__imp_KfdGetLayerCacheEpoch
0x14013d13b  nop     dword ptr [rax+rax+00h]
0x14013d140  mov     eax, dword ptr [rsp+270h+var_208]
0x14013d144  mov     [rsi+198h], eax
0x14013d14a  cmp     [rbp+170h+arg_70], ebx
0x14013d150  jz      short loc_14013D167
0x14013d152  mov     eax, [rsi+30h]
0x14013d155  bt      eax, 0Eh
0x14013d159  jb      short loc_14013D167
0x14013d15b  cmp     cs:gAleEnableNameOnSecureSocket, ebx
0x14013d161  jz      loc_14013E2F7
0x14013d167  xor     eax, eax
0x14013d169  mov     [rbp+170h+var_128], rdi
0x14013d16d  xorps   xmm0, xmm0
0x14013d170  mov     qword ptr [rbp+170h+var_18C], rax
0x14013d174  mov     qword ptr [rbp+170h+var_10C], rax
0x14013d178  mov     qword ptr [rbp+170h+var_1D4], rax
0x14013d17c  mov     qword ptr [rbp+170h+var_EC], rax
0x14013d183  mov     qword ptr [rbp+170h+var_DC], rax
0x14013d18a  mov     qword ptr [rbp+170h+var_FC], rax
0x14013d18e  mov     [rsp+270h+var_1F8+4], rax
0x14013d193  mov     [rbp-20h], rax
0x14013d197  mov     [rbp+60h], rax
0x14013d19b  mov     [rbp-68h], rax
0x14013d19f  mov     [rbp+80h], rax
0x14013d1a6  mov     [rbp+90h], rax
0x14013d1ad  mov     [rbp+70h], rax
0x14013d1b1  mov     [rsp+270h+var_1F8], rax
0x14013d1b6  movups  [rbp+170h+var_D0], xmm0
0x14013d1bd  mov     [rbp+170h+var_C0], rax
0x14013d1c4  movups  [rbp+170h+var_180], xmm0
0x14013d1c8  mov     [rbp+170h+var_120], rdi
0x14013d1cc  movups  [rbp+170h+var_B0], xmm0
0x14013d1d3  mov     [rbp+170h+var_160], rdi
0x14013d1d7  movups  [rbp+170h+var_A0], xmm0
0x14013d1de  movups  [rbp+170h+var_90], xmm0
0x14013d1e5  call    cs:__imp_KeGetCurrentIrql
0x14013d1ec  nop     dword ptr [rax+rax+00h]
0x14013d1f1  cmp     al, 2
0x14013d1f3  jnb     short loc_14013D203
0x14013d1f5  call    WfpRaiseIrqlToDispatchLevel
0x14013d1fa  mov     byte ptr [rsp+270h+var_210+3], al
0x14013d1fe  mov     byte ptr [rsp+270h+var_210+2], 1
0x14013d203  mov     ecx, gs:1A4h
0x14013d20b  lea     r8, [rcx+rcx*8]
0x14013d20f  mov     rcx, cs:gPerProcessorContext
0x14013d216  cmp     [rcx+r8*8+20h], dil
0x14013d21b  jnz     short loc_14013D232
0x14013d21d  mov     r15, [rcx+r8*8+18h]
0x14013d222  mov     rdi, [rcx+r8*8+10h]
0x14013d227  mov     byte ptr [rcx+r8*8+20h], 1
0x14013d22d  jmp     loc_14013D34A
0x14013d232  mov     rcx, cs:gIncomingValuesLookasideList
0x14013d239  lea     rdx, [rsp+270h+Entry]
0x14013d23e  call    WfpAllocateFromPerProcessorLookasideList
0x14013d243  test    rax, rax
0x14013d246  jnz     short loc_14013D2A3
0x14013d248  mov     rcx, cs:gMetadataLookasideList
0x14013d24f  lea     rdx, [rbp+170h+var_1E8]
0x14013d253  call    WfpAllocateFromPerProcessorLookasideList
0x14013d258  test    rax, rax
0x14013d25b  jz      loc_14013D341
0x14013d261  mov     eax, gs:1A4h
0x14013d269  mov     rcx, cs:gIncomingValuesLookasideList
0x14013d270  lea     ebx, [rax+1]
0x14013d273  shl     rbx, 7
0x14013d277  add     rbx, rcx
0x14013d27a  movzx   eax, byte ptr [rbx+0B0h]
0x14013d281  test    al, al
0x14013d283  jnz     short loc_14013D28E
0x14013d285  lea     rdx, [rbx+40h]
0x14013d289  call    PplpLazyInitializeLookasideList
0x14013d28e  mov     rdx, [rsp+270h+Entry]; Entry
0x14013d293  lea     rcx, [rbx+40h]; Lookaside
0x14013d297  call    cs:__imp_ExFreeToLookasideListEx
0x14013d29e  nop     dword ptr [rax+rax+00h]
0x14013d2a3  xor     r12b, r12b
0x14013d2a6  mov     rdi, r15
0x14013d2a9  cmp     byte ptr [rsp+270h+var_210+2], r13b
0x14013d2ae  jz      short loc_14013D2BA
0x14013d2b0  movzx   ecx, byte ptr [rsp+270h+var_210+3]
0x14013d2b5  call    WfpLowerIrqlFromDispatchLevel
0x14013d2ba  mov     rcx, cs:WPP_GLOBAL_Control
0x14013d2c1  lea     rax, WPP_GLOBAL_Control
0x14013d2c8  mov     rbx, 0FFFFFFFFC000009Ah
0x14013d2cf  cmp     rcx, rax
0x14013d2d2  jz      short loc_14013D303
0x14013d2d4  cmp     byte ptr [rcx+29h], 2
0x14013d2d8  jb      short loc_14013D303
0x14013d2da  test    dword ptr [rcx+2Ch], 1000h
0x14013d2e1  jz      short loc_14013D303
0x14013d2e3  mov     rcx, [rcx+18h]
0x14013d2e7  lea     r9, aWfpalepauthori_7; "WfpAlepAuthorizeConnect"
0x14013d2ee  mov     edx, 0Ah
0x14013d2f3  mov     dword ptr [rsp+270h+var_250], ebx
0x14013d2f7  lea     r8, WPP_dc97c17fd6903ad537f842808d057dba_Traceguids
0x14013d2fe  call    WPP_SF_sd
0x14013d303  movaps  xmm7, [rsp+270h+var_68+8]
0x14013d30b  movaps  xmm6, [rsp+270h+var_58+8]
0x14013d313  movaps  xmm8, [rsp+270h+var_78+8]
0x14013d31c  mov     rcx, [rbp+170h+var_1C8]
0x14013d320  test    rcx, rcx
0x14013d323  jz      loc_14013E302
0x14013d329  call    cs:__imp_FeReleaseCompletionHandle
0x14013d330  nop     dword ptr [rax+rax+00h]
0x14013d335  xor     r14d, r14d
0x14013d338  mov     [rbp+170h+var_1C8], r14
0x14013d33c  jmp     loc_14013E305
0x14013d341  mov     r15, [rsp+270h+Entry]
0x14013d346  mov     rdi, [rbp+170h+var_1E8]
0x14013d34a  xor     edx, edx; Val
0x14013d34c  mov     r8d, 2A0h; Size
0x14013d352  mov     rcx, r15; void *
0x14013d355  call    memset
0x14013d35a  xor     edx, edx; Val
0x14013d35c  mov     r8d, 2A8h; Size
0x14013d362  mov     rcx, rdi; void *
0x14013d365  call    memset
0x14013d36a  lea     rax, [rdi+270h]
0x14013d371  mov     [rax+8], rax
0x14013d375  mov     [rax], rax
0x14013d378  mov     eax, [rsi+34h]
0x14013d37b  bt      eax, 10h
0x14013d37f  jnb     loc_14013D43B
0x14013d385  mov     eax, [rsi+34h]
0x14013d388  bt      eax, 0Dh
0x14013d38c  jnb     short loc_14013D39B
0x14013d38e  mov     eax, [rsi+30h]
0x14013d391  bt      eax, 18h
0x14013d395  jb      loc_14013D43B
0x14013d39b  mov     rax, [rsi+1C0h]
0x14013d3a2  test    rax, rax
0x14013d3a5  jnz     short loc_14013D402
0x14013d3a7  mov     rax, [rbp+170h+var_1B0]
0x14013d3ab  mov     dword ptr [rax], 1001h
0x14013d3b1  mov     rcx, cs:WPP_GLOBAL_Control
0x14013d3b8  lea     rax, WPP_GLOBAL_Control
0x14013d3bf  mov     rbx, 0FFFFFFFFC0000022h
0x14013d3c6  cmp     rcx, rax
0x14013d3c9  jz      short loc_14013D3FA
0x14013d3cb  cmp     byte ptr [rcx+29h], 2
0x14013d3cf  jb      short loc_14013D3FA
0x14013d3d1  test    dword ptr [rcx+2Ch], 1000h
0x14013d3d8  jz      short loc_14013D3FA
0x14013d3da  mov     rcx, [rcx+18h]
0x14013d3de  lea     r9, aWfpalepauthori_7; "WfpAlepAuthorizeConnect"
0x14013d3e5  mov     edx, 0Ah
0x14013d3ea  mov     dword ptr [rsp+270h+var_250], ebx
0x14013d3ee  lea     r8, WPP_dc97c17fd6903ad537f842808d057dba_Traceguids
0x14013d3f5  call    WPP_SF_sd
0x14013d3fa  mov     r12b, 1
0x14013d3fd  jmp     loc_14013D303
0x14013d402  mov     byte ptr [rsp+270h+var_210], 1
0x14013d407  mov     r13, rax
0x14013d40a  mov     rax, [rax+30h]
0x14013d40e  test    rax, rax
0x14013d411  jnz     short loc_14013D407
0x14013d413  mov     rcx, [r13+1F8h]
0x14013d41a  call    cs:__imp_KfdAleAcquireEndpointContextFromFlow
0x14013d421  nop     dword ptr [rax+rax+00h]
0x14013d426  mov     [rbp+170h+var_1E0], rax
0x14013d42a  mov     rbx, rax
0x14013d42d  test    rax, rax
0x14013d430  jz      short loc_14013D456
0x14013d432  mov     r13, [rax+1C0h]
0x14013d439  jmp     short loc_14013D456
0x14013d43b  mov     eax, [rsi+34h]
0x14013d43e  mov     byte ptr [rsp+270h+var_210], 1
0x14013d443  bt      eax, 0Dh
0x14013d447  jnb     short loc_14013D456
0x14013d449  mov     eax, [rsi+34h]
0x14013d44c  bt      eax, 10h
0x14013d450  jb      short loc_14013D456
0x14013d452  mov     r13, [rbp+170h+var_130]
0x14013d456  mov     eax, [rsi+34h]
0x14013d459  bt      eax, 0Dh
0x14013d45d  jnb     short loc_14013D47D
0x14013d45f  mov     eax, [rsi+34h]
0x14013d462  bt      eax, 10h
0x14013d466  jb      short loc_14013D47D
0x14013d468  mov     eax, [rsi+30h]
0x14013d46b  bt      eax, 18h
0x14013d46f  jb      short loc_14013D47D
0x14013d471  mov     dword ptr [rbp+170h+var_1E8], 1
0x14013d478  test    r13, r13
0x14013d47b  jnz     short loc_14013D484
0x14013d47d  mov     dword ptr [rbp+170h+var_1E8], 0
0x14013d484  mov     eax, [rsi+34h]
0x14013d487  bt      eax, 10h
0x14013d48b  jnb     short loc_14013D4A7
0x14013d48d  mov     eax, [rsi+30h]
0x14013d490  bt      eax, 18h
0x14013d494  jb      short loc_14013D4A7
0x14013d496  test    rbx, rbx
0x14013d499  jz      short loc_14013D4A7
0x14013d49b  test    r13, r13
0x14013d49e  jz      short loc_14013D4A7
0x14013d4a0  mov     edx, 1
0x14013d4a5  jmp     short loc_14013D4A9
0x14013d4a7  xor     edx, edx
0x14013d4a9  mov     rcx, [rsi+1E0h]
0x14013d4b0  movzx   eax, word ptr [rsp+270h+var_208+4]
0x14013d4b5  mov     word ptr [rbp+170h+var_180], ax
0x14013d4b9  movzx   eax, word ptr [r12]
0x14013d4be  mov     dword ptr [rbp+170h+var_180+4], eax
0x14013d4c1  mov     qword ptr [rbp+170h+var_180+8], r15
0x14013d4c5  mov     rax, [rcx+10h]
0x14013d4c9  mov     qword ptr [rbp+170h+var_18C+4], rax
0x14013d4cd  movzx   eax, word ptr [rcx+0Ah]
0x14013d4d1  lea     rcx, [rbp+170h+var_190]
0x14013d4d5  mov     [rbp+170h+var_190], eax
0x14013d4d8  movzx   eax, word ptr [r12+2]
0x14013d4de  add     rax, rax
  ... truncated ...
```
