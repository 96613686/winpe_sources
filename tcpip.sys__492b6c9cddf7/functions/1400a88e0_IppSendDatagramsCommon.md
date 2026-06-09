# IppSendDatagramsCommon

- ea: `0x1400a88e0`
- end: `0x1400ab728`
- name: `IppSendDatagramsCommon`
- size: `11848`
- prototype: ``
- caller_count: `4`
- callee_count: `40`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x140095860`
- `0x1400a88a4`
- `0x14013ecc0`
- `0x14013eef0`

## callees

- `0x140014c50`
- `0x140026ec0`
- `0x1400288f0`
- `0x14002a900`
- `0x14004ec50`
- `0x1400525d0`
- `0x140053d70`
- `0x140053e04`
- `0x140053e98`
- `0x1400585d0`
- `0x140058980`
- `0x1400590d0`
- `0x1400665b0`
- `0x140068d10`
- `0x140069150`
- `0x14006a450`
- `0x14006a4d0`
- `0x14006e130`
- `0x14007e460`
- `0x14007ff8c`
- `0x140095900`
- `0x1400a88e0`
- `0x1400c35e0`
- `0x1400c3cb8`
- `0x1400c4160`
- `0x1400c42d4`
- `0x1400c8414`
- `0x1400d2f30`
- `0x1400d76e0`
- `0x1400e27a0`
- `0x1400eef80`
- `0x1400fccf0`
- `0x1400fd434`
- `0x14010b6b0`
- `0x140119bd0`
- `0x140127908`
- `0x14014cdc4`
- `0x1401bf5c0`
- `0x1401bf640`
- `0x1401bf940`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x1400a8970`
- `ntoskrnl!KfRaiseIrql` at `0x1400a8970`
- `ntoskrnl!KeLowerIrql` at `0x1400ab700`
- `ntoskrnl!KeLowerIrql` at `0x1400ab700`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1400a8a95`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1400a8a95`
- `ntoskrnl!ExAllocatePool3` at `0x1400a91f4`
- `ntoskrnl!ExAllocatePool3` at `0x1400a92de`
- `ntoskrnl!ExAllocatePool3` at `0x1400a9a69`
- `ntoskrnl!ExAllocatePool3` at `0x1400a9b46`
- `ntoskrnl!ExAllocatePool3` at `0x1400a91f4`
- `ntoskrnl!ExAllocatePool3` at `0x1400a92de`
- `ntoskrnl!ExAllocatePool3` at `0x1400a9a69`
- `ntoskrnl!ExAllocatePool3` at `0x1400a9b46`
- `ntoskrnl!RtlCompareMemory` at `0x1400aa24e`
- `ntoskrnl!RtlCompareMemory` at `0x1400aa24e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400aa6f7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400aa70e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400aa6f7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400aa70e`
- `NETIO!KfdIsLayerEmpty` at `0x1400aac83`
- `NETIO!KfdIsLayerEmpty` at `0x1400aacb3`
- `NETIO!KfdIsLayerEmpty` at `0x1400aac83`
- `NETIO!KfdIsLayerEmpty` at `0x1400aacb3`
- `NETIO!NetioDereferenceNetBufferListChain` at `0x1400a8b19`
- `NETIO!NetioDereferenceNetBufferListChain` at `0x1400a8b19`
- `NETIO!NetioQueryNetBufferListTrafficClass2` at `0x1400aa76a`
- `NETIO!NetioQueryNetBufferListTrafficClass2` at `0x1400aa76a`
- `NETIO!NetioPhComputePseudoHeaderChecksum` at `0x1400aa441`
- `NETIO!NetioPhComputePseudoHeaderChecksum` at `0x1400aa441`
- `NDIS!NdisNblTrackerTransferOwnership` at `0x1400aa5d2`
- `NDIS!NdisNblTrackerTransferOwnership` at `0x1400aa63f`
- `NDIS!NdisNblTrackerTransferOwnership` at `0x1400aa5d2`
- `NDIS!NdisNblTrackerTransferOwnership` at `0x1400aa63f`

## string_xrefs

- `0x1400a9421`: `routing header copy 3 (IPNG)`
- `0x1400a9c71`: `routing header copy 3 (IPNG)`
- `0x1400a9407`: `hop by hop options copy 3 (IPNG)`
- `0x1400a9c55`: `hop by hop options copy 3 (IPNG)`
- `0x1400aa100`: `join path arguments (IPNG)`

## pseudocode

```c
void IppSendDatagramsCommon(char a1, char a2, __int64 a3, __int64 a4, ...)
{
  BOOL v4; // r15d
  _QWORD *v5; // rsi
  __int64 v6; // r14
  unsigned __int64 v8; // rbx
  int *v9; // r13
  KIRQL v10; // r12
  __int64 v11; // rax
  int *v12; // r9
  __int64 v13; // rcx
  _DWORD *v14; // rdx
  __int64 v15; // r8
  __int64 v16; // rcx
  char *v17; // rbx
  __int64 v18; // rdx
  __int64 v19; // r8
  unsigned __int64 v20; // rbx
  KIRQL v21; // cl
  char v22; // cl
  char v23; // r8
  int v24; // eax
  int *v25; // rdx
  unsigned __int16 v26; // r12
  unsigned __int64 v27; // rdx
  unsigned __int64 v28; // rcx
  int NextHopAndSource; // r15d
  int v30; // r14d
  __int64 v31; // r8
  char PacketCount; // al
  int v33; // r8d
  int v34; // r9d
  char v35; // al
  int v36; // r8d
  int v37; // r9d
  const void *v38; // rdx
  char v39; // bl
  int v40; // eax
  int *v41; // r14
  int v42; // r9d
  char v43; // al
  int v44; // r8d
  int v45; // r9d
  int v46; // r8d
  int v47; // r9d
  __int64 v48; // r10
  unsigned __int64 *v49; // r12
  unsigned __int64 v50; // r8
  unsigned __int64 v51; // rax
  unsigned __int64 v52; // rax
  __int64 v53; // r11
  int v54; // eax
  int v55; // r9d
  unsigned __int64 v56; // kr10_8
  unsigned int v57; // eax
  int v58; // r8d
  char *v59; // rax
  __int64 v60; // r8
  char *v61; // rbx
  char *v62; // rax
  char *v63; // rbx
  char *v64; // rax
  char *v65; // rax
  unsigned int v66; // r9d
  int v67; // r8d
  const wchar_t *v68; // r9
  int v69; // eax
  int v70; // ecx
  char v71; // al
  int v72; // r8d
  int v73; // r9d
  char v74; // al
  int v75; // r8d
  int v76; // r9d
  int v77; // eax
  __int64 v78; // rbx
  _QWORD *v79; // rbx
  __int64 v80; // r14
  int v81; // r15d
  int v82; // eax
  int v83; // eax
  char v84; // al
  int v85; // r8d
  int v86; // r9d
  int v87; // r8d
  int v88; // r9d
  __int64 v89; // r12
  unsigned __int64 *v90; // r12
  unsigned __int64 v91; // r8
  unsigned __int64 v92; // rax
  unsigned __int64 v93; // rax
  int v94; // eax
  unsigned int v95; // eax
  int v96; // eax
  char *v97; // rax
  __int64 v98; // r8
  char *v99; // rbx
  int v100; // eax
  char *v101; // rax
  char *v102; // rbx
  unsigned int v103; // r9d
  int v104; // r8d
  const wchar_t *v105; // r9
  int v106; // eax
  int v107; // ecx
  char v108; // al
  int v109; // r8d
  int v110; // r9d
  __int64 v111; // r11
  char v112; // al
  unsigned __int16 v113; // r10
  int v114; // r8d
  int v115; // r9d
  __int64 v116; // r11
  int v117; // eax
  char *v118; // rdx
  int v119; // eax
  __int64 v120; // rcx
  __int64 v121; // rax
  int **v122; // r12
  __int64 v123; // rdx
  __int64 NextHopFromPath; // rax
  int *v125; // r15
  __int64 v126; // r12
  _QWORD *v127; // rcx
  unsigned int v128; // ebx
  __int64 Path; // rax
  __int64 v130; // rax
  _QWORD *v131; // rax
  __int64 v132; // rax
  _OWORD *v133; // r12
  __int64 v134; // r8
  _OWORD *v135; // rdx
  _QWORD *v136; // rcx
  __int64 v137; // rax
  SIZE_T v138; // rbx
  __int64 v139; // r9
  __int64 *v140; // rdx
  unsigned int i; // eax
  int v142; // ecx
  int v143; // eax
  __int64 v144; // rcx
  char v145; // dl
  __int64 v146; // rdx
  __int64 v147; // rcx
  int v148; // edx
  unsigned int v149; // eax
  __int64 v150; // rax
  int v151; // eax
  int v152; // eax
  __int64 v153; // r14
  int v154; // ebx
  int IsEnabledDeviceUsageNoInline; // eax
  __int64 v156; // rdx
  bool v157; // di
  __int64 v158; // rcx
  int *v159; // rax
  unsigned __int8 v160; // al
  unsigned __int16 v161; // r12
  char v162; // al
  int v163; // r8d
  int v164; // r9d
  char v165; // al
  int v166; // r8d
  int v167; // r9d
  char v168; // al
  int v169; // r8d
  int v170; // r9d
  int v171; // r8d
  int v172; // r9d
  __int64 v173; // r15
  __int64 *v174; // rbx
  __int64 v175; // r14
  int v176; // eax
  __int64 v177; // rax
  int v178; // r9d
  char v179; // al
  int v180; // r9d
  unsigned int v181; // r12d
  int v182; // eax
  int v183; // eax
  bool v184; // zf
  char v185; // al
  char v186; // al
  unsigned __int16 v187; // r10
  int v188; // r9d
  __int64 v189; // r12
  char v190; // al
  unsigned __int16 v191; // r10
  int v192; // r9d
  char v193; // al
  int v194; // r9d
  unsigned __int16 v195; // r10
  int v196; // r8d
  int v197; // r9d
  char v198; // al
  int v199; // r9d
  char v200; // r10
  unsigned __int16 v201; // r11
  int v202; // r8d
  int v203; // r9d
  char v204; // r10
  char v205; // al
  unsigned __int16 v206; // r10
  int v207; // r9d
  int v208; // r8d
  int v209; // r12d
  unsigned int v210; // r8d
  char v211; // al
  unsigned __int16 v212; // r10
  int v213; // r9d
  char v214; // al
  int v215; // r9d
  int v216; // eax
  int v217; // ecx
  int *v218; // rbx
  _DWORD *v219; // r15
  char v220; // al
  unsigned __int16 v221; // r10
  int v222; // r9d
  char v223; // al
  unsigned __int16 v224; // r10
  int v225; // r9d
  char v226; // al
  int v227; // r8d
  int v228; // r9d
  char v229; // r10
  char v230; // r11
  __int64 v231; // rdi
  int v232; // r8d
  int v233; // r9d
  int v234; // r10d
  __int64 v235; // r11
  __int64 v236; // rcx
  void *Src; // [rsp+20h] [rbp-E0h]
  void *Srca; // [rsp+20h] [rbp-E0h]
  char v239; // [rsp+60h] [rbp-A0h]
  char v240; // [rsp+68h] [rbp-98h]
  char v241; // [rsp+68h] [rbp-98h]
  char v242; // [rsp+68h] [rbp-98h]
  char v243; // [rsp+68h] [rbp-98h]
  char v244; // [rsp+68h] [rbp-98h]
  char v245; // [rsp+68h] [rbp-98h]
  char v246; // [rsp+68h] [rbp-98h]
  char v247; // [rsp+80h] [rbp-80h]
  char v248; // [rsp+81h] [rbp-7Fh]
  char v249; // [rsp+82h] [rbp-7Eh] BYREF
  unsigned __int8 v250; // [rsp+83h] [rbp-7Dh] BYREF
  _WORD v251[2]; // [rsp+84h] [rbp-7Ch] BYREF
  unsigned __int16 v252; // [rsp+88h] [rbp-78h] BYREF
  int *v253; // [rsp+90h] [rbp-70h]
  char v254; // [rsp+98h] [rbp-68h]
  unsigned __int64 v255; // [rsp+A0h] [rbp-60h]
  __int64 v256; // [rsp+A8h] [rbp-58h]
  unsigned __int64 v257; // [rsp+B0h] [rbp-50h]
  __int64 v258; // [rsp+B8h] [rbp-48h]
  KIRQL v259; // [rsp+C0h] [rbp-40h]
  unsigned __int16 v260; // [rsp+C4h] [rbp-3Ch] BYREF
  unsigned __int16 v261[2]; // [rsp+C8h] [rbp-38h] BYREF
  BOOL v262; // [rsp+CCh] [rbp-34h]
  PVOID P[2]; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v264; // [rsp+E0h] [rbp-20h]
  __int128 v265; // [rsp+F0h] [rbp-10h]
  __int64 v266; // [rsp+100h] [rbp+0h]
  int v267; // [rsp+108h] [rbp+8h]
  __int64 v268; // [rsp+110h] [rbp+10h]
  void *v269; // [rsp+118h] [rbp+18h]
  __int128 v270; // [rsp+120h] [rbp+20h] BYREF
  __int128 v271; // [rsp+130h] [rbp+30h] BYREF
  unsigned __int64 v272; // [rsp+140h] [rbp+40h]
  _QWORD *v273; // [rsp+148h] [rbp+48h]
  __int64 v274; // [rsp+150h] [rbp+50h]
  __int64 v275; // [rsp+158h] [rbp+58h]
  __int128 v276; // [rsp+160h] [rbp+60h] BYREF
  __int128 v277; // [rsp+170h] [rbp+70h]
  __int128 v278; // [rsp+180h] [rbp+80h]
  __int128 v279; // [rsp+190h] [rbp+90h]
  __int128 v280; // [rsp+1A0h] [rbp+A0h]
  __int128 v281; // [rsp+1B0h] [rbp+B0h]
  __int64 v282; // [rsp+1C0h] [rbp+C0h]
  unsigned int v283; // [rsp+210h] [rbp+110h] BYREF
  __int64 v284; // [rsp+220h] [rbp+120h]
  __int64 v285; // [rsp+228h] [rbp+128h]
  __int64 v286; // [rsp+230h] [rbp+130h] BYREF
  va_list va; // [rsp+230h] [rbp+130h]
  va_list va1; // [rsp+238h] [rbp+138h] BYREF

  va_start(va1, a4);
  va_start(va, a4);
  v286 = va_arg(va1, _QWORD);
  v285 = a4;
  v284 = a3;
  LOBYTE(v283) = a1;
  v5 = (_QWORD *)v286;
  LOBYTE(v4) = 0;
  v282 = 0;
  v6 = a3;
  v262 = v4;
  v8 = *(_QWORD *)v286;
  v9 = 0;
  v267 = *(unsigned __int16 *)(v286 + 48);
  v257 = v8;
  v276 = 0;
  v277 = 0;
  v278 = 0;
  v279 = 0;
  v280 = 0;
  v281 = 0;
  *(_OWORD *)P = 0;
  v264 = 0;
  v265 = 0;
  v259 = KfRaiseIrql(2u);
  v10 = v259;
  LODWORD(v11) = HIDWORD(KeGetPcr()[1].LockArray);
  v274 = v11;
  v275 = 8 * v11;
  v12 = (int *)*((_QWORD *)SendPerProcessorState + v11);
  v268 = (__int64)v12;
  if ( *((_BYTE *)v5 + 188) && IppBatchPerProcState )
  {
    v13 = 80;
    if ( (int *)v6 != &Ipv4Global )
      v13 = 88;
    v14 = *(_DWORD **)(v13 + *((_QWORD *)IppBatchPerProcState + v11));
    v15 = (unsigned int)*v14;
    if ( (unsigned int)v15 < IppMaxBatchSize )
    {
      *v14 = v15 + 1;
      v9 = &v14[84 * v15 + 2];
    }
    LOBYTE(v4) = v9 != 0;
    v262 = v9 != 0;
  }
  v16 = *v12;
  if ( (int)v16 >= 3 )
  {
    if ( !v4 )
    {
      v17 = (char *)IppControlPool + 128 * (unsigned __int64)(unsigned int)(HIDWORD(KeGetPcr()[1].LockArray) + 1);
      if ( !v17[176] )
        PplpLazyInitializeLookasideList(IppControlPool, v17 + 64);
      v9 = (int *)ExAllocateFromLookasideListEx((PLOOKASIDE_LIST_EX)(v17 + 64));
      if ( !v9 )
      {
        if ( SBYTE3(WPP_MAIN_CB.Reserved) < 0 )
          McTemplateK0z_EtwWriteTransfer(
            &MICROSOFT_TCPIP_PROVIDER_Context,
            TCPIP_MEMORY_FAILURES,
            v19,
            L"control (IPNG)");
        v20 = v257;
        *(_DWORD *)(v257 + 140) = -1073741670;
        if ( SBYTE6(WPP_MAIN_CB.Reserved) < 0 || byte_140225C70 )
          IppLogSendDatagramsDiscard(v284, (_DWORD)v5, 0, v20, 264, -536854176);
        LOBYTE(v18) = 1;
        NetioDereferenceNetBufferListChain(v20, v18);
        v21 = v10;
        goto LABEL_551;
      }
      v8 = v257;
    }
    v254 = 1;
    v269 = 0;
  }
  else
  {
    v254 = 0;
    if ( !v4 )
      v9 = &v12[84 * v16 + 2];
    *v12 = v16 + 1;
    v269 = &v12[40 * v16 + 254];
  }
  memset(v9, 0, 0x150u);
  v22 = *((_BYTE *)v9 + 88);
  v23 = *((_BYTE *)v9 + 185);
  *((_BYTE *)v9 + 184) |= 0x10u;
  LODWORD(v256) = -1;
  v9[9] = -1;
  v9[10] = 255;
  v9[27] = -1;
  *((_QWORD *)v9 + 1) = v8;
  *((_BYTE *)v9 + 88) = v22 ^ (v22 ^ (2 * a2)) & 4;
  *((_BYTE *)v9 + 185) = (v23 | 0x40) ^ ((v23 | 0x40) ^ (2 * a2)) & 8;
  *((_BYTE *)v9 + 186) ^= ((2 * a2) ^ *((_BYTE *)v9 + 186)) & 0x40;
  if ( (Feature_5988_5730__private_featureState & 0x10) != 0 )
    v24 = Feature_5988_5730__private_featureState & 1;
  else
    v24 = ((__int64 (*)(void))Feature_5988_5730__private_IsEnabledDeviceUsageNoInline)();
  if ( v24 )
  {
    *((_QWORD *)&v264 + 1) = 0xFFFFFFFFFFLL;
    LODWORD(v265) = -1;
    v248 = 2 * (a2 & 2);
    BYTE4(v265) = v248;
    v6 = v284;
    HIDWORD(v256) = 255;
  }
  else
  {
    v248 = BYTE4(v265);
    v256 = *((_QWORD *)&v264 + 1);
  }
  *((_BYTE *)v9 + 186) ^= (*((_BYTE *)v9 + 186) ^ (4 * *((_BYTE *)v5 + 184))) & 4;
  v25 = (int *)v5[2];
  v26 = *(_WORD *)(v6 + 28);
  v258 = v26;
  if ( v25 )
  {
    NextHopAndSource = 0;
    v247 = 0;
    switch ( *((_WORD *)v5 + 28) )
    {
      case 1:
        goto LABEL_42;
      case 6:
      case 0x11:
        v9[47] = *v25;
        break;
      case 0x3A:
LABEL_42:
        *(_QWORD *)(v9 + 47) = *(_QWORD *)v25;
        break;
    }
    v9[49] = *((_DWORD *)v5 + 15);
    goto LABEL_44;
  }
  NextHopAndSource = IppProcessRawData(v6, v5, v9);
  if ( NextHopAndSource < 0 )
  {
    v30 = 269;
    v31 = 3758113121LL;
    goto LABEL_371;
  }
  v247 = 1;
  if ( (BYTE2(WPP_MAIN_CB.Reserved) & 0x40) != 0 )
  {
    if ( v26 == 2 )
    {
      PacketCount = IppGetPacketCount(*v5);
      McTemplateK0pqqqqqbr5qbr7qqq_EtwWriteTransfer(
        *((unsigned __int16 *)v5 + 28),
        (unsigned int)TCPIP_SEND_SLOW_PATH,
        v33,
        v34,
        *((_WORD *)v5 + 28),
        2,
        0,
        0,
        0,
        0,
        0,
        0,
        20,
        PacketCount,
        4);
    }
    else if ( (BYTE2(WPP_MAIN_CB.Reserved) & 0x40) != 0 )
    {
      v35 = IppGetPacketCount(*v5);
      McTemplateK0pqqqqqbr5qbr7qqq_EtwWriteTransfer(
        v26,
        (unsigned int)TCPIP_SEND_SLOW_PATH,
        v36,
        v37,
        *((_WORD *)v5 + 28),
        v26,
        0,
        0,
        0,
        0,
        0,
        0,
        20,
        v35,
        6);
    }
  }
LABEL_44:
  v38 = (const void *)v5[18];
  v39 = 0;
  LOBYTE(v283) = 0;
  if ( !v38 )
    v38 = *(const void **)(v5[4] + 16LL);
  memmove(v9 + 58, v38, *(unsigned __int16 *)(*(_QWORD *)(v6 + 16) + 6LL));
  if ( (Feature_5988_5730__private_featureState & 0x10) != 0 )
    v40 = Feature_5988_5730__private_featureState & 1;
  else
    v40 = ((__int64 (*)(void))Feature_5988_5730__private_IsEnabledDeviceUsageNoInline)();
  v28 = *((unsigned int *)v5 + 18);
  v41 = (int *)(v5 + 9);
  v253 = (int *)(v5 + 9);
  v42 = 0xFFFF;
  if ( v40 )
  {
    if ( (_DWORD)v28 )
    {
      v184 = (v9[46] & 2) == 0;
      v253 = (int *)(v5 + 9);
      if ( !v184 )
      {
LABEL_60:
        LOBYTE(v286) = BYTE12(v265);
        goto LABEL_157;
      }
      v48 = v5[1];
      v49 = (unsigned __int64 *)v5[10];
      NextHopAndSource = 0;
      v255 = v28;
      v266 = v48;
      v50 = v28;
      v251[0] = 0;
      v260 = 0;
      v249 = 0;
      v270 = 0;
      if ( v28 < 0x10 )
      {
        v26 = v258;
        LOBYTE(v286) = BYTE12(v265);
        goto LABEL_157;
      }
      LOBYTE(v286) = BYTE12(v265);
      while ( 1 )
      {
        v51 = *v49;
        if ( *v49 < 0x10 )
          break;
        v27 = v51 - 16;
        v52 = (v51 - 16 + 23) & 0xFFFFFFFFFFFFFFF8uLL;
        v272 = v52;
        if ( v52 < 0x10 || v50 < v52 )
        {
          v55 = 2;
          goto LABEL_139;
        }
        v53 = v284;
        v54 = *((_DWORD *)v49 + 2);
        if ( v54 == *(_DWORD *)(v284 + 24) )
        {
          v56 = v28;
          v28 = 0x140000000uLL;
          switch ( *((_DWORD *)v49 + 3) )
          {
            case 1:
              v39 |= 1u;
              LOBYTE(v283) = v39;
              if ( P[0] || !v27 )
                break;
              NextHopAndSource = (*(__int64 (__fastcall **)(__int64 *, unsigned __int64, unsigned __int16 *, _WORD *, char *))(v284 + 232))(
                                   (__int64 *)v49 + 2,
                                   v27,
                                   &v260,
                                   v251,
                                   &v249);
              v28 = v249 & 1;
              v27 = (unsigned int)(2 * v28);
              LOBYTE(v27) = v286 & 0xFD | (2 * v28);
              LOBYTE(v286) = v27;
              BYTE12(v265) = v27;
              if ( NextHopAndSource < 0 )
              {
                v55 = 8;
                goto LABEL_140;
              }
              v270 = 1u;
              v59 = (char *)ExAllocatePool3(66, v251[0], 1735290953, &v270, 1);
              v61 = v59;
              if ( !v59 )
              {
                if ( SBYTE3(WPP_MAIN_CB.Reserved) < 0 )
                {
                  v68 = L"hop by hop options copy 3 (IPNG)";
                  goto LABEL_134;
                }
                goto LABEL_135;
              }
              memmove(v59, v49 + 2, v251[0]);
              v50 = v255;
              v48 = v266;
              WORD4(v265) = v251[0];
              v28 = v260;
              P[0] = v61;
              if ( v260 )
                *(_QWORD *)&v264 = &v61[v260];
              goto LABEL_106;
            case 3:
            case 0x27:
              if ( HIDWORD(v256) != 255 )
                break;
              if ( v27 < 4 )
                goto LABEL_125;
              v57 = *((_DWORD *)v49 + 4);
              if ( v57 > 0xFF )
              {
                v55 = 7;
                goto LABEL_139;
              }
              if ( (v49[2] & 3) == 3 )
                goto LABEL_127;
              v28 = v257;
              v27 = *(_QWORD *)(v257 + 8);
              if ( v27 )
              {
                v58 = 0;
                if ( (v49[2] & 3) == 0 )
                  v58 = 4;
                do
                {
                  v28 = v58 | v57 & 3 ^ *(_DWORD *)(v27 + 92) & 0xFFFFFFF8;
                  *(_DWORD *)(v27 + 92) = v28;
                  v27 = *(_QWORD *)v27;
                }
                while ( v27 );
                v50 = v255;
              }
              if ( ((((unsigned __int8)v57 >> 2) - 48) & 0xF7) == 0 && v48 && (*(_DWORD *)(v48 + 56) & 8) == 0 )
              {
                NextHopAndSource = -1073741790;
                v55 = 11;
                goto LABEL_140;
              }
              NextHopAndSource = 0;
              if ( !*(_BYTE *)(v53 + 19731) )
              {
                HIDWORD(v256) = (unsigned __int8)v57 >> 2;
                HIDWORD(v264) = HIDWORD(v256);
              }
              break;
            case 0xE:
              v39 |= 1u;
              if ( (BYTE5(v265) & 8) != 0 )
                break;
              if ( v27 < 4 )
                goto LABEL_125;
              LOBYTE(v28) = *((_DWORD *)v49 + 4) != 0 ? 4 : 0;
              v248 = v248 & 0xFB | v28;
              BYTE5(v265) |= 8u;
              BYTE4(v265) = v248;
              break;
            case 0x13:
            case 0x33:
              break;
            case 0x15:
              if ( (_DWORD)v256 != -1 )
                break;
              if ( v27 < 4 )
                goto LABEL_125;
              LODWORD(v256) = *((_DWORD *)v49 + 4);
              DWORD2(v264) = v256;
              if ( (unsigned int)v256 <= 0xFF )
                break;
              v55 = 6;
              goto LABEL_139;
            case 0x20:
              v39 |= 1u;
              LOBYTE(v283) = v39;
              if ( P[1] || !v27 )
                break;
              NextHopAndSource = (*(__int64 (__fastcall **)(__int64 *, unsigned __int64, _WORD *, char *))(v284 + 328))(
                                   (__int64 *)v49 + 2,
                                   v27,
                                   v251,
                                   &v249);
              v28 = v249 & 1;
              v27 = (unsigned int)(2 * v28);
              LOBYTE(v27) = v286 & 0xFD | (2 * v28);
              LOBYTE(v286) = v27;
              BYTE12(v265) = v27;
              if ( NextHopAndSource < 0 )
              {
                v55 = 9;
                goto LABEL_140;
              }
              v270 = 1u;
              v62 = (char *)ExAllocatePool3(66, v251[0], 1735290953, &v270, 1);
              v63 = v62;
              if ( !v62 )
              {
                if ( SBYTE3(WPP_MAIN_CB.Reserved) < 0 )
                {
                  v68 = L"routing header copy 3 (IPNG)";
LABEL_134:
                  McTemplateK0z_EtwWriteTransfer(&MICROSOFT_TCPIP_PROVIDER_Context, TCPIP_MEMORY_FAILURES, v60, v68);
                }
LABEL_135:
                NextHopAndSource = -1073741670;
                v30 = 268;
                v31 = 3758113122LL;
                goto LABEL_370;
              }
              memmove(v62, v49 + 2, v251[0]);
              v28 = (unsigned __int64)&Ipv4Global;
              v50 = v255;
              v48 = v266;
              P[1] = v63;
              WORD5(v265) = v251[0];
              if ( (int *)v284 == &Ipv4Global )
              {
                if ( v251[0] <= 3u )
                {
LABEL_106:
                  v39 = v283;
                }
                else
                {
                  v64 = v63 + 3;
                  v39 = v283;
                  *(_QWORD *)&v264 = v64;
                }
              }
              else
              {
                v65 = v63 + 8;
                v39 = v283;
                *(_QWORD *)&v264 = v65;
              }
              break;
            case 0x32:
              if ( !v257 )
                break;
              if ( v27 < 4 )
              {
LABEL_125:
                v55 = 5;
                goto LABEL_139;
              }
              v66 = *((_DWORD *)v49 + 4);
              if ( v66 >= 3 )
              {
LABEL_127:
                v55 = 10;
                goto LABEL_139;
              }
              v27 = *(_QWORD *)(v257 + 8);
              if ( v27 )
              {
                v67 = 0;
                if ( (v66 & 3) == 0 )
                  v67 = 4;
                do
                {
                  v28 = v67
                      | (*(_DWORD *)(v27 + 92)
                       ^ ((unsigned __int8)*(_DWORD *)(v27 + 92)
                        ^ (unsigned __int8)v66)
                       & 3)
                      & 0xFFFFFFFB;
                  *(_DWORD *)(v27 + 92) = v28;
                  v27 = *(_QWORD *)v27;
                }
                while ( v27 );
                v50 = v255;
              }
              NextHopAndSource = 0;
              break;
            case 0x3C:
              v39 |= 1u;
              break;
            default:
              v28 = v56;
              v55 = 3;
              goto LABEL_139;
          }
        }
        else if ( v54 == 0xFFFF )
        {
          if ( *((_DWORD *)v49 + 3) != 12299 )
            goto LABEL_72;
        }
        else if ( v54 != 17 || *((_DWORD *)v49 + 3) != 2 )
        {
LABEL_72:
          v55 = 4;
          goto LABEL_139;
        }
        v50 -= v272;
        v255 = v50;
        if ( v50 < 0x10 )
          goto LABEL_145;
        v49 = (unsigned __int64 *)((char *)v49 + v272);
      }
      v55 = 1;
LABEL_139:
      NextHopAndSource = -1073741811;
LABEL_140:
      if ( (*((_BYTE *)&WPP_MAIN_CB.Reserved + 13) & 4) != 0 )
      {
        if ( v49 )
        {
          v69 = *((_DWORD *)v49 + 3);
          v70 = *((_DWORD *)v49 + 2);
        }
        else
        {
          LOBYTE(v69) = 0;
          LOBYTE(v70) = 0;
        }
        McTemplateK0qqq_EtwWriteTransfer(
          (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
          (unsigned int)TCPIP_IP_INVALID_ANCILLARY_DATA,
          (unsigned int)MICROSOFT_TCPIP_PROVIDER,
          v55,
          v70,
          v69);
      }
LABEL_145:
      if ( NextHopAndSource < 0 )
      {
        v30 = 268;
        v31 = 3758113122LL;
        goto LABEL_370;
      }
      v26 = v258;
      if ( v39 )
      {
        v247 = 1;
        if ( (BYTE2(WPP_MAIN_CB.Reserved) & 0x40) != 0 )
        {
          if ( (_WORD)v258 == 2 )
          {
            v71 = IppGetPacketCount(*v5);
            McTemplateK0pqqqqqbr5qbr7qqq_EtwWriteTransfer(
              *((unsigned __int16 *)v5 + 28),
              (unsigned int)TCPIP_SEND_SLOW_PATH,
              v72,
              v73,
              *((_WORD *)v5 + 28),
              2,
              0,
              0,
              0,
              0,
              0,
              0,
              21,
              v71,
              4);
            v41 = v253;
            LOBYTE(v283) = v39;
            goto LABEL_157;
          }
          if ( (BYTE2(WPP_MAIN_CB.Reserved) & 0x40) != 0 )
          {
            v74 = IppGetPacketCount(*v5);
            McTemplateK0pqqqqqbr5qbr7qqq_EtwWriteTransfer(
              v26,
              (unsigned int)TCPIP_SEND_SLOW_PATH,
              v75,
              v76,
              *((_WORD *)v5 + 28),
              v26,
              0,
              0,
              0,
              0,
              0,
              0,
              21,
              v74,
              6);
          }
        }
      }
      v41 = v253;
      LOBYTE(v283) = v39;
    }
    else
    {
      LOBYTE(v286) = BYTE12(v265);
    }
  }
  else
  {
    if ( (_DWORD)v28 )
    {
      if ( (BYTE2(WPP_MAIN_CB.Reserved) & 0x40) != 0 )
      {
        if ( v26 == 2 )
        {
          v43 = IppGetPacketCount(*v5);
          McTemplateK0pqqqqqbr5qbr7qqq_EtwWriteTransfer(
            *((unsigned __int16 *)v5 + 28),
            (unsigned int)TCPIP_SEND_SLOW_PATH,
            v44,
            v45,
            *((_WORD *)v5 + 28),
            2,
            0,
            0,
            0,
            0,
            0,
            0,
            21,
            v43,
            4);
        }
        else if ( (BYTE2(WPP_MAIN_CB.Reserved) & 0x40) != 0 )
        {
          v240 = IppGetPacketCount(*v5);
          McTemplateK0pqqqqqbr5qbr7qqq_EtwWriteTransfer(
            v26,
            (unsigned int)TCPIP_SEND_SLOW_PATH,
            v46,
            v47,
            *((_WORD *)v5 + 28),
            v26,
            0,
            0,
            0,
            0,
            0,
            0,
            21,
            v240,
            6);
        }
      }
      LOBYTE(v42) = 1;
      NextHopAndSource = IppProcessAncillaryData(v284, v5[10], *v41, v42, v9);
      if ( NextHopAndSource < 0 )
      {
        v30 = 268;
        v31 = 3758113122LL;
        goto LABEL_370;
      }
      v247 = 1;
      goto LABEL_60;
    }
    LOBYTE(v286) = BYTE12(v265);
  }
  v253 = v41;
LABEL_157:
  v266 = 0;
  if ( (Feature_5988_5730__private_featureState & 0x10) != 0 )
    v77 = Feature_5988_5730__private_featureState & 1;
  else
    v77 = ((__int64 (*)(void))Feature_5988_5730__private_IsEnabledDeviceUsageNoInline)();
  if ( v77 )
  {
    v80 = v5[3];
    v79 = v5 + 3;
    if ( v80 && (v9[46] & 2) == 0 )
    {
      v81 = v284;
      v82 = (*(__int64 (__fastcall **)(int *))(v284 + 176))(v9 + 58);
      NextHopAndSource = IppParseSessionState(v81, v80, v82, 0, (__int64)P, 0);
      if ( NextHopAndSource < 0 )
      {
        v30 = 270;
        v31 = 3758113123LL;
        goto LABEL_370;
      }
      v79 = v5 + 3;
      LOBYTE(v286) = BYTE12(v265);
      v248 = BYTE4(v265);
      v256 = *((_QWORD *)&v264 + 1);
      v266 = v80;
    }
    v41 = v253;
    goto LABEL_172;
  }
  v78 = v5[3];
  if ( !v78 )
  {
    v79 = v5 + 3;
LABEL_172:
    v253 = v41;
    goto LABEL_173;
  }
  NextHopAndSource = IppProcessSessionState(v284, v5[3], v9);
  if ( NextHopAndSource < 0 )
  {
    v30 = 270;
    v31 = 3758113123LL;
    goto LABEL_370;
  }
  v266 = v78;
  v79 = v5 + 3;
LABEL_173:
  if ( (Feature_5988_5730__private_featureState & 0x10) != 0 )
    v83 = Feature_5988_5730__private_featureState & 1;
  else
    v83 = ((__int64 (*)(void))Feature_5988_5730__private_IsEnabledDeviceUsageNoInline)();
  if ( v83 )
  {
    v28 = *((unsigned int *)v5 + 42);
    v253 = v41;
    v273 = v79;
    if ( (_DWORD)v28 && (v9[46] & 2) == 0 )
    {
      v90 = (unsigned __int64 *)v5[22];
      v255 = v28;
      v252 = 0;
      v91 = (unsigned int)v28;
      v261[0] = 0;
      NextHopAndSource = 0;
      v250 = 0;
      v271 = 0;
      if ( v28 < 0x10 )
      {
        v253 = v41;
      }
      else
      {
        while ( 1 )
        {
          v92 = *v90;
          if ( *v90 < 0x10 )
            break;
          v27 = v92 - 16;
          v93 = (v92 - 16 + 23) & 0xFFFFFFFFFFFFFFF8uLL;
          v272 = v93;
          if ( v93 < 0x10 || v91 < v93 )
          {
            v27 = 2;
            goto LABEL_250;
          }
          v94 = *((_DWORD *)v90 + 2);
          if ( v94 == *(_DWORD *)(v284 + 24) )
          {
            switch ( *((_DWORD *)v90 + 3) )
            {
              case 1:
                LOBYTE(v283) = v283 | 1;
                if ( P[0] || !v27 )
                  break;
                v96 = (*(__int64 (__fastcall **)(__int64 *, unsigned __int64, unsigned __int16 *, unsigned __int16 *, unsigned __int8 *))(v284 + 232))(
                        (__int64 *)v90 + 2,
                        v27,
                        v261,
                        &v252,
                        &v250);
                v28 = v250;
                NextHopAndSource = v96;
                LOBYTE(v28) = v286 & 0xFD | (2 * (v250 & 1));
                LOBYTE(v286) = v28;
                BYTE12(v265) = v28;
                if ( v96 < 0 )
                {
                  v27 = 8;
                  goto LABEL_251;
                }
                v271 = 1u;
                v97 = (char *)ExAllocatePool3(66, v252, 1735290953, &v271, 1);
                v99 = v97;
                if ( !v97 )
                {
                  if ( SBYTE3(WPP_MAIN_CB.Reserved) < 0 )
                  {
                    v105 = L"hop by hop options copy 3 (IPNG)";
                    goto LABEL_244;
                  }
                  goto LABEL_245;
                }
                memmove(v97, v90 + 2, v252);
                v91 = v255;
                WORD4(v265) = v252;
                v28 = v261[0];
                P[0] = v99;
                if ( v261[0] )
                  *(_QWORD *)&v264 = &v99[v261[0]];
                break;
              case 3:
              case 0x27:
                if ( HIDWORD(v256) != 255 )
                  break;
                if ( v27 < 4 )
                  goto LABEL_237;
                v95 = *((_DWORD *)v90 + 4);
                LODWORD(v255) = v95;
                if ( v95 > 0xFF )
                {
                  v27 = 7;
                  goto LABEL_250;
                }
                BYTE12(v264) = v95;
                *(_WORD *)((char *)&v264 + 13) = *(_WORD *)((char *)&v255 + 1);
                HIBYTE(v264) = BYTE3(v255);
                HIDWORD(v256) = HIDWORD(v264);
                break;
              case 0xE:
                LOBYTE(v283) = v283 | 1;
                if ( (BYTE5(v265) & 8) != 0 )
                  break;
                if ( v27 < 4 )
                  goto LABEL_237;
                LOBYTE(v28) = v248 & 0xFB | (*((_DWORD *)v90 + 4) != 0 ? 4 : 0);
                v248 = v28;
                BYTE5(v265) |= 8u;
                BYTE4(v265) = v28;
                break;
              case 0x13:
              case 0x33:
                break;
              case 0x15:
                if ( (_DWORD)v256 != -1 )
                  break;
                if ( v27 < 4 )
                  goto LABEL_237;
                LODWORD(v256) = *((_DWORD *)v90 + 4);
                DWORD2(v264) = v256;
                if ( (unsigned int)v256 <= 0xFF )
                  break;
                v27 = 6;
                goto LABEL_250;
              case 0x20:
                LOBYTE(v283) = v283 | 1;
                if ( P[1] || !v27 )
                  break;
                v100 = (*(__int64 (__fastcall **)(__int64 *, unsigned __int64, unsigned __int16 *, unsigned __int8 *))(v284 + 328))(
                         (__int64 *)v90 + 2,
                         v27,
                         &v252,
                         &v250);
                v28 = v250;
                NextHopAndSource = v100;
                LOBYTE(v28) = v286 & 0xFD | (2 * (v250 & 1));
                LOBYTE(v286) = v28;
                BYTE12(v265) = v28;
                if ( v100 < 0 )
                {
                  v27 = 9;
                  goto LABEL_251;
                }
                v271 = 1u;
                v101 = (char *)ExAllocatePool3(66, v252, 1735290953, &v271, 1);
                v102 = v101;
                if ( !v101 )
                {
                  if ( SBYTE3(WPP_MAIN_CB.Reserved) < 0 )
                  {
                    v105 = L"routing header copy 3 (IPNG)";
LABEL_244:
                    McTemplateK0z_EtwWriteTransfer(&MICROSOFT_TCPIP_PROVIDER_Context, TCPIP_MEMORY_FAILURES, v98, v105);
                  }
LABEL_245:
                  NextHopAndSource = -1073741670;
                  v30 = 268;
                  v31 = 3758113124LL;
LABEL_370:
                  v8 = v257;
LABEL_371:
                  LODWORD(v89) = v284;
LABEL_372:
                  if ( SBYTE6(WPP_MAIN_CB.Reserved) < 0 || byte_140225C70 )
                    IppLogSendDatagramsDiscard(v89, (_DWORD)v5, (_DWORD)v9, v8, v30, v31);
                  *(_DWORD *)(v8 + 140) = NextHopAndSource;
                  if ( (Feature_5988_5730__private_featureState & 0x10) != 0 )
                    IsEnabledDeviceUsageNoInline = Feature_5988_5730__private_featureState & 1;
                  else
                    IsEnabledDeviceUsageNoInline = Feature_5988_5730__private_IsEnabledDeviceUsageNoInline(
                                                     v28,
                                                     v27,
                                                     v31);
                  if ( IsEnabledDeviceUsageNoInline )
                  {
                    if ( P[0] )
                      ExFreePoolWithTag(P[0], 0);
                    if ( P[1] )
                      ExFreePoolWithTag(P[1], 0);
                  }
                  IppCleanupSendState(v9, v27, v31);
                  LOBYTE(v156) = 1;
                  IppCompleteAndFreePacketList(v9, v156);
                  v157 = v262;
LABEL_537:
                  v218 = (int *)v284;
LABEL_538:
                  v219 = (_DWORD *)v268;
                  goto LABEL_539;
                }
                memmove(v101, v90 + 2, v252);
                v28 = (unsigned __int64)&Ipv4Global;
                v91 = v255;
                P[1] = v102;
                WORD5(v265) = v252;
                if ( (int *)v284 == &Ipv4Global )
                {
                  if ( v252 > 3u )
                    *(_QWORD *)&v264 = v102 + 3;
                }
                else
                {
                  *(_QWORD *)&v264 = v102 + 8;
                }
                break;
              case 0x32:
                if ( !v257 )
                  break;
                if ( v27 < 4 )
                {
LABEL_237:
                  v27 = 5;
                  goto LABEL_250;
                }
                v103 = *((_DWORD *)v90 + 4);
                if ( v103 >= 3 )
                {
                  v27 = 10;
                  goto LABEL_250;
                }
                v27 = *(_QWORD *)(v257 + 8);
                if ( v27 )
                {
                  v104 = 0;
                  if ( (v103 & 3) == 0 )
                    v104 = 4;
                  do
                  {
                    v28 = v104
                        | (*(_DWORD *)(v27 + 92)
                         ^ ((unsigned __int8)*(_DWORD *)(v27 + 92)
                          ^ (unsigned __int8)v103)
                         & 3)
                        & 0xFFFFFFFB;
                    *(_DWORD *)(v27 + 92) = v28;
                    v27 = *(_QWORD *)v27;
                  }
                  while ( v27 );
                  v91 = v255;
                }
                NextHopAndSource = 0;
                break;
              case 0x3C:
                LOBYTE(v283) = v283 | 1;
                break;
              default:
                v27 = 3;
                goto LABEL_250;
            }
          }
          else if ( v94 == 0xFFFF )
          {
            if ( *((_DWORD *)v90 + 3) != 12299 )
              goto LABEL_195;
          }
          else if ( v94 != 17 || *((_DWORD *)v90 + 3) != 2 )
          {
LABEL_195:
            v27 = 4;
            goto LABEL_250;
          }
          v91 -= v272;
          v255 = v91;
          if ( v91 < 0x10 )
            goto LABEL_256;
          v90 = (unsigned __int64 *)((char *)v90 + v272);
        }
        v27 = 1;
LABEL_250:
        NextHopAndSource = -1073741811;
LABEL_251:
        if ( (*((_BYTE *)&WPP_MAIN_CB.Reserved + 13) & 4) != 0 )
        {
          if ( v90 )
          {
            v106 = *((_DWORD *)v90 + 3);
            v107 = *((_DWORD *)v90 + 2);
          }
          else
          {
            LOBYTE(v106) = 0;
            LOBYTE(v107) = 0;
          }
          McTemplateK0qqq_EtwWriteTransfer(
            (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
            (unsigned int)TCPIP_IP_INVALID_ANCILLARY_DATA,
            (unsigned int)MICROSOFT_TCPIP_PROVIDER,
            v27,
            v107,
            v106);
        }
LABEL_256:
        if ( NextHopAndSource < 0 )
        {
          v30 = 268;
          v31 = 3758113124LL;
          goto LABEL_370;
        }
        v79 = v273;
      }
      if ( (_BYTE)v283 )
      {
        v247 = 1;
        if ( (BYTE2(WPP_MAIN_CB.Reserved) & 0x40) != 0 )
        {
          if ( (_WORD)v258 == 2 )
          {
            v108 = IppGetPacketCount(*v5);
            McTemplateK0pqqqqqbr5qbr7qqq_EtwWriteTransfer(
              *((unsigned __int16 *)v5 + 28),
              (unsigned int)TCPIP_SEND_SLOW_PATH,
              v109,
              v110,
              *((_WORD *)v5 + 28),
              2,
              v111,
              v111,
              v111,
              v111,
              v111,
              v111,
              22,
              v108,
              4);
          }
          else if ( (BYTE2(WPP_MAIN_CB.Reserved) & 0x40) != 0 )
          {
            v112 = IppGetPacketCount(*v5);
            McTemplateK0pqqqqqbr5qbr7qqq_EtwWriteTransfer(
              v113,
              (unsigned int)TCPIP_SEND_SLOW_PATH,
              v114,
              v115,
              *((_WORD *)v5 + 28),
              v113,
              v116,
              v116,
              v116,
              v116,
              v116,
              v116,
              22,
              v112,
              6);
          }
        }
      }
      goto LABEL_267;
    }
LABEL_266:
    v253 = v41;
LABEL_267:
    v89 = v284;
    goto LABEL_268;
  }
  if ( !*((_DWORD *)v5 + 42) )
    goto LABEL_266;
  if ( (BYTE2(WPP_MAIN_CB.Reserved) & 0x40) != 0 )
  {
    if ( v26 == 2 )
    {
      v84 = IppGetPacketCount(*v5);
      McTemplateK0pqqqqqbr5qbr7qqq_EtwWriteTransfer(
        *((unsigned __int16 *)v5 + 28),
        (unsigned int)TCPIP_SEND_SLOW_PATH,
        v85,
        v86,
        *((_WORD *)v5 + 28),
        2,
        0,
        0,
        0,
        0,
        0,
        0,
        22,
        v84,
        4);
    }
    else if ( (BYTE2(WPP_MAIN_CB.Reserved) & 0x40) != 0 )
    {
      v241 = IppGetPacketCount(*v5);
      McTemplateK0pqqqqqbr5qbr7qqq_EtwWriteTransfer(
        v26,
        (unsigned int)TCPIP_SEND_SLOW_PATH,
        v87,
        v88,
        *((_WORD *)v5 + 28),
        v26,
        0,
        0,
        0,
        0,
        0,
        0,
        22,
        v241,
        6);
    }
  }
  v89 = v284;
  NextHopAndSource = IppProcessAncillaryData(v284, v5[22], *((_DWORD *)v5 + 42), 0, v9);
  if ( NextHopAndSource < 0 )
  {
    v8 = v257;
    v30 = 268;
    v31 = 3758113124LL;
    goto LABEL_372;
  }
  v247 = 1;
LABEL_268:
  v30 = 294;
  if ( (Feature_5988_5730__private_featureState & 0x10) != 0 )
    v117 = Feature_5988_5730__private_featureState & 1;
  else
    v117 = ((__int64 (*)(void))Feature_5988_5730__private_IsEnabledDeviceUsageNoInline)();
  if ( v117 )
  {
    IppMoveParsedDataToControl(P, v9);
    v256 = *((_QWORD *)&v264 + 1);
  }
  v118 = (char *)*((_QWORD *)v9 + 31);
  if ( !v118 )
  {
    *((_QWORD *)v9 + 31) = v9 + 58;
    v118 = (char *)(v9 + 58);
  }
  v119 = *((unsigned __int16 *)v5 + 28);
  v9[8] = v119;
  v120 = v5[4];
  *((_QWORD *)v9 + 26) = v120;
  if ( v120 )
  {
    *((_QWORD *)v9 + 28) = *(_QWORD *)v120;
    v121 = v5[5];
    if ( v121 )
    {
      *((_QWORD *)v9 + 27) = v121;
      v122 = (int **)(v9 + 54);
    }
    else
    {
      v123 = *(unsigned int *)(**(_QWORD **)(*(_QWORD *)v120 + 8LL) + 20LL);
      if ( (_DWORD)v123 != *(_DWORD *)(*((_QWORD *)v9 + 26) + 24LL) )
        IppValidatePath(*((_QWORD *)v9 + 26));
      NextHopFromPath = IppGetNextHopFromPath(*((_QWORD *)v9 + 26), v123);
      *((_QWORD *)v9 + 27) = NextHopFromPath;
      if ( !NextHopFromPath )
      {
        NextHopAndSource = -1073741275;
        v31 = 3758113125LL;
        goto LABEL_314;
      }
      *((_BYTE *)v9 + 184) |= 0x80u;
      v122 = (int **)(v9 + 54);
    }
  }
  else
  {
    if ( !v5[5] )
    {
      v125 = v253;
      if ( v119 == 6 && !*v253 && (v126 = v5[14]) != 0 )
      {
        v127 = *(_QWORD **)(v126 + 8);
        v283 = *((_DWORD *)v5 + 34);
        v286 = 0;
        if ( (unsigned __int8)IppCanonicalizeScopeId(*v127, v118, &v283) )
        {
          NextHopAndSource = IppValidateRouteLookup(
                               **(_QWORD **)(v126 + 8),
                               *((_QWORD *)v9 + 31),
                               (unsigned int)&v283,
                               *(_QWORD *)(v126 + 8),
                               v126);
          if ( NextHopAndSource >= 0 )
          {
            v128 = v283;
            Path = IppFindPath(**(_QWORD **)(v126 + 8), 0, *((_QWORD *)v9 + 31), v283, *(_QWORD *)(v126 + 8), v126);
            *((_QWORD *)v9 + 26) = Path;
            if ( Path )
            {
              *((_BYTE *)v9 + 184) |= 0x20u;
              v130 = IppGetNextHopFromPath(Path, v9 + 54);
              v122 = (int **)(v9 + 54);
              *((_QWORD *)v9 + 27) = v130;
              if ( v130 )
              {
                v131 = (_QWORD *)*((_QWORD *)v9 + 26);
                *((_BYTE *)v9 + 184) |= 0x80u;
                *((_QWORD *)v9 + 28) = *v131;
                goto LABEL_309;
              }
              NextHopAndSource = -1073741275;
              v31 = 3758113128LL;
            }
            else
            {
              NextHopAndSource = IppFindNextHopAndSource(
                                   **(_QWORD **)(v126 + 8),
                                   *(_QWORD *)(v126 + 8),
                                   *((_QWORD *)v9 + 31),
                                   v128,
                                   v126,
                                   v9 + 54,
                                   (__int64 *)va,
                                   0,
                                   0);
              if ( NextHopAndSource >= 0 )
              {
                v132 = v286;
                v122 = (int **)(v9 + 54);
                *((_BYTE *)v9 + 184) |= 0xC0u;
                *((_QWORD *)v9 + 28) = v132;
                goto LABEL_309;
              }
              v31 = 3758113129LL;
            }
          }
          else
          {
            v31 = 3758113127LL;
          }
        }
        else
        {
          NextHopAndSource = -1073741305;
          v31 = 3758113126LL;
        }
      }
      else
      {
        v133 = v269;
        if ( !v269 )
        {
          v269 = (void *)PplAllocateFromLookasideList(IppJoinPathArgsPool);
          v133 = v269;
          if ( !v269 )
          {
            if ( SBYTE3(WPP_MAIN_CB.Reserved) < 0 )
              McTemplateK0z_EtwWriteTransfer(
                &MICROSOFT_TCPIP_PROVIDER_Context,
                TCPIP_MEMORY_FAILURES,
                v134,
                L"join path arguments (IPNG)");
            NextHopAndSource = -1073741670;
            v30 = 264;
            v31 = 3758113130LL;
            goto LABEL_313;
          }
        }
        memset(v133, 0, 0xA0u);
        v135 = v133;
        *v133 = *(_OWORD *)(v5 + 19);
        *((_QWORD *)v133 + 2) = *v79;
        *((_DWORD *)v133 + 6) = *v125;
        *((_QWORD *)v133 + 4) = v5[10];
        *(_OWORD *)((char *)v133 + 40) = *((_OWORD *)v5 + 6);
        *((_DWORD *)v133 + 14) = *((_DWORD *)v5 + 34);
        *((_QWORD *)v133 + 8) = *((_QWORD *)v9 + 31);
        *(_OWORD *)((char *)v133 + 72) = *((_OWORD *)v5 + 7);
        *((_QWORD *)v133 + 11) = v5[16];
        v89 = v284;
        NextHopAndSource = IppJoinPath(v284, v135);
        if ( NextHopAndSource < 0 )
        {
          v31 = 3758113131LL;
          goto LABEL_314;
        }
        v136 = (_QWORD *)*((_QWORD *)v269 + 15);
        *((_BYTE *)v9 + 184) |= 0x20u;
        *((_QWORD *)v9 + 26) = v136;
        *((_QWORD *)v9 + 28) = *v136;
        v137 = ((__int64 (*)(void))IppGetNextHopFromPath)();
        v122 = (int **)(v9 + 54);
        *((_QWORD *)v9 + 27) = v137;
        if ( v137 )
        {
          *((_BYTE *)v9 + 184) |= 0x80u;
          goto LABEL_309;
        }
        NextHopAndSource = -1073741275;
        v31 = 3758113132LL;
      }
LABEL_313:
      v89 = v284;
LABEL_314:
      v8 = v257;
      v139 = *(_QWORD *)(v257 + 160);
      v140 = *(__int64 **)(v257 + 8);
      if ( (_DWORD)v139 || *(_DWORD *)(v257 + 320) )
      {
        if ( !v139 )
          LODWORD(v139) = *(_DWORD *)(v257 + 320);
        i = (((unsigned int)v139 & 0xFFFFF) + *((_DWORD *)v140 + 21) - 1) / ((unsigned int)v139 & 0xFFFFF);
      }
      else
      {
        for ( i = 0; v140; ++i )
          v140 = (__int64 *)*v140;
      }
      v28 = *(_QWORD *)(v89 + 20264);
      v27 = 192 * v274;
      *(_DWORD *)(v28 + 192 * v274 + 148) += i;
      if ( v30 == 294 )
        v30 = 267;
      goto LABEL_372;
    }
    v122 = (int **)(v9 + 54);
    *((_QWORD *)v9 + 28) = v5[14];
    *((_QWORD *)v9 + 27) = v5[5];
  }
LABEL_309:
  if ( (*((_BYTE *)v9 + 185) & 0x10) != 0 && **v122 == 1701736521 )
  {
    v138 = *(unsigned __int16 *)(*(_QWORD *)(v284 + 16) + 6LL);
    if ( RtlCompareMemory(*v122 + 42, *((const void **)v9 + 31), v138) != v138 )
    {
      NextHopAndSource = -1073741811;
      v31 = 3758113133LL;
      goto LABEL_313;
    }
  }
  if ( *((_WORD *)v9 + 25) || *((_WORD *)v9 + 24) )
  {
    v28 = *(_QWORD *)(*v5 + 160LL);
    v27 = *((_QWORD *)*v122 + 1);
    if ( (_DWORD)v28 && (v28 & 0x40000000) == 0 && (*(_DWORD *)(v27 + 836) & 0xC) != 4 )
    {
      NextHopAndSource = -1073741637;
      v30 = 266;
      v31 = 3758113134LL;
      goto LABEL_370;
    }
    if ( *(_DWORD *)(*v5 + 320LL) && (*(_DWORD *)(v27 + 892) & 3) != 1 )
    {
      NextHopAndSource = -1073741637;
      v30 = 266;
      v31 = 3758113135LL;
      goto LABEL_370;
    }
  }
  *((_QWORD *)v9 + 25) = **(_QWORD **)(*((_QWORD *)v9 + 28) + 8LL);
  v142 = **v122;
  if ( v142 == 1634496585 || v142 == 1701736521 )
    v143 = (*v122)[6];
  else
    v143 = 3;
  v144 = *((unsigned __int8 *)v9 + 187);
  v9[64] = v143;
  v145 = *((_BYTE *)v5 + 192);
  *((_BYTE *)v9 + 187) = v144 ^ (v144 ^ (2 * v145)) & 2;
  if ( (v145 & 1) != 0 )
  {
    v146 = *((_QWORD *)v9 + 1);
    v144 = *(_QWORD *)(v146 + 320);
    if ( (_DWORD)v144 )
    {
      *(_DWORD *)(v146 + 320) = v144 & 0xC00FFFFF;
      if ( !v9[11] )
      {
        v147 = **(_QWORD **)(*((_QWORD *)v9 + 28) + 16LL);
        if ( !v147 || (v148 = v9[8], v148 == 1) )
          v149 = 0;
        else
          v149 = NetioPhComputePseudoHeaderChecksum(
                   v147,
                   v9 + 58,
                   *(unsigned __int16 *)(*(_QWORD *)(v284 + 16) + 6LL),
                   0,
                   v148);
        IppFillChecksumAtOffset(
          (unsigned __int16)(v149 + HIWORD(v149) + ((unsigned int)((unsigned __int16)v149 + HIWORD(v149)) >> 16)),
          6,
          *(_QWORD *)(*((_QWORD *)v9 + 1) + 8LL));
      }
      v150 = *((_QWORD *)v9 + 1);
      v144 = 0xFFFF;
      *((_WORD *)v9 + 46) = -1;
      v267 = 0xFFFF;
      *(_QWORD *)(v150 + 144) = 0;
    }
  }
  IppProcessDefaults(v144, *((unsigned __int16 *)v5 + 32), *((unsigned __int16 *)v5 + 28), v9);
  if ( !*((_BYTE *)v5 + 186) )
  {
    *(_QWORD *)&v276 = *((_QWORD *)v9 + 28);
    *((_QWORD *)&v276 + 1) = v9 + 58;
    LODWORD(v277) = v9[64];
    *((_QWORD *)&v277 + 1) = *v122;
    *(_QWORD *)&v278 = *((_QWORD *)*v122 + 1);
    if ( **v122 == 1701736521 )
      v151 = *(_DWORD *)(*((_QWORD *)*v122 + 2) + 24LL);
    else
      v151 = 0;
    DWORD2(v278) = v151;
    if ( **v122 != 1634496585 )
      goto LABEL_353;
    v152 = v9[64];
    if ( v152 == 3 )
    {
      if ( (*((_BYTE *)v9 + 186) & 0x10) == 0 )
      {
LABEL_353:
        BYTE12(v278) = 0;
        goto LABEL_354;
      }
    }
    else if ( v152 == 4 && (*((_BYTE *)v9 + 186) & 0x20) == 0 )
    {
      goto LABEL_353;
    }
    BYTE12(v278) = 1;
LABEL_354:
    *((_QWORD *)&v279 + 1) = *((_QWORD *)v9 + 26);
    LODWORD(v280) = *((_DWORD *)v5 + 34);
    *((_QWORD *)&v280 + 1) = v5[10];
    LODWORD(v281) = *v253;
    *((_QWORD *)&v281 + 1) = *((_QWORD *)v9 + 8);
    LODWORD(v282) = v9[11];
    if ( v9[8] != 6 || (v184 = v5[2] == 0, BYTE4(v281) = 1, v184) )
      BYTE4(v281) = 0;
    *(_QWORD *)&v279 = *((_QWORD *)v9 + 1);
    if ( TcpipNblTrackerEnabled )
    {
      LODWORD(Src) = 0;
      NdisNblTrackerTransferOwnership(*((_QWORD *)v9 + 1), 0, WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink, 163, Src);
    }
    v153 = v284;
    v154 = IppInspectLocalDatagramsOut(*(unsigned int *)(v284 + 24), &v276, (unsigned int)v9[8], v285, v9 + 47, v9[49]);
    if ( v154 == 3 )
      goto LABEL_368;
    if ( TcpipNblTrackerEnabled )
    {
      LODWORD(Srca) = 0;
      NdisNblTrackerTransferOwnership(*((_QWORD *)v9 + 1), 0, *(_QWORD *)(v153 + 23032), 164, Srca);
    }
    if ( v154 >= 1 )
    {
      if ( (unsigned int)(v154 - 1) <= 1 )
      {
        NextHopAndSource = -1073741285;
        v30 = 9;
LABEL_369:
        v31 = 3758113136LL;
        goto LABEL_370;
      }
LABEL_368:
      v30 = 257;
      goto LABEL_369;
    }
  }
  if ( (*((_BYTE *)v9 + 186) & 2) != 0 )
    goto LABEL_389;
  v158 = *((_QWORD *)v9 + 1);
  if ( *(_QWORD *)(v158 + 168) )
  {
    v159 = *v122;
    LOBYTE(v283) = 0;
    v160 = NetioQueryNetBufferListTrafficClass2(
             v158,
             *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v159 + 1) + 48LL) + 56LL),
             &v283);
    if ( !(_BYTE)v283 )
    {
      *((_BYTE *)v9 + 186) |= 2u;
      v9[10] = v160;
    }
  }
  if ( (*((_BYTE *)v9 + 186) & 2) != 0 )
  {
LABEL_389:
    v161 = v258;
    v247 = 1;
    if ( (BYTE2(WPP_MAIN_CB.Reserved) & 0x40) != 0 )
    {
      if ( (_WORD)v258 == 2 )
      {
        v162 = IppGetPacketCount(*v5);
        McTemplateK0pqqqqqbr5qbr7qqq_EtwWriteTransfer(
          *((unsigned __int16 *)v5 + 28),
          (unsigned int)TCPIP_SEND_SLOW_PATH,
          v163,
          v164,
          *((_WORD *)v5 + 28),
          2,
          0,
          0,
          0,
          0,
          0,
          0,
          23,
          v162,
          4);
      }
      else if ( (BYTE2(WPP_MAIN_CB.Reserved) & 0x40) != 0 )
      {
        v165 = IppGetPacketCount(*v5);
        McTemplateK0pqqqqqbr5qbr7qqq_EtwWriteTransfer(
          v161,
          (unsigned int)TCPIP_SEND_SLOW_PATH,
          v166,
          v167,
          *((_WORD *)v5 + 28),
          v161,
          0,
          0,
          0,
          0,
          0,
          0,
          23,
          v165,
          6);
      }
    }
  }
  else
  {
    v161 = v258;
  }
  if ( !*((_BYTE *)v5 + 185) )
    goto LABEL_534;
  if ( (*(_DWORD *)(*((_QWORD *)v9 + 1) + 136LL) & 0x400000) != 0 )
  {
    if ( (BYTE2(WPP_MAIN_CB.Reserved) & 0x40) != 0 )
    {
      if ( v161 == 2 )
      {
        v168 = IppGetPacketCount(*v5);
        McTemplateK0pqqqqqbr5qbr7qqq_EtwWriteTransfer(
          *((unsigned __int16 *)v5 + 28),
          (unsigned int)TCPIP_SEND_SLOW_PATH,
          v169,
          v170,
          *((_WORD *)v5 + 28),
          2,
          0,
          0,
          0,
          0,
          0,
          0,
          24,
          v168,
          4);
      }
      else if ( (BYTE2(WPP_MAIN_CB.Reserved) & 0x40) != 0 )
      {
        v242 = IppGetPacketCount(*v5);
        McTemplateK0pqqqqqbr5qbr7qqq_EtwWriteTransfer(
          v161,
          (unsigned int)TCPIP_SEND_SLOW_PATH,
          v171,
          v172,
          *((_WORD *)v5 + 28),
          v161,
          0,
          0,
          0,
          0,
          0,
          0,
          24,
          v242,
          6);
      }
    }
    goto LABEL_534;
  }
  v173 = v5[5];
  v174 = (__int64 *)v5[4];
  if ( !v173 || !v174 )
  {
    if ( (BYTE2(WPP_MAIN_CB.Reserved) & 0x40) != 0 )
    {
      if ( v161 == 2 )
      {
        v226 = IppGetPacketCount(*v5);
        McTemplateK0pqqqqqbr5qbr7qqq_EtwWriteTransfer(
          *((unsigned __int16 *)v5 + 28),
          (unsigned int)TCPIP_SEND_SLOW_PATH,
          v227,
          v228,
          *((_WORD *)v5 + 28),
          2,
          v230,
          v229,
          0,
          0,
          0,
          0,
          12,
          v226,
          4);
      }
      else if ( (BYTE2(WPP_MAIN_CB.Reserved) & 0x40) != 0 )
      {
        if ( v174 )
          v231 = **(_QWORD **)(*v174 + 16);
        else
          v231 = 0;
        v246 = IppGetPacketCount(*v5);
        McTemplateK0pqqqqqbr5qbr7qqq_EtwWriteTransfer(
          v161,
          (unsigned int)TCPIP_SEND_SLOW_PATH,
          v232,
          v233,
          *((_WORD *)v5 + 28),
          v161,
          0,
          0,
          v234,
          v231,
          v234,
          v235,
          12,
          v246,
          6);
      }
    }
    goto LABEL_534;
  }
  v175 = *(_QWORD *)(v173 + 8);
  if ( *(_DWORD *)v173 == 1701736521 )
  {
    v176 = *(_DWORD *)(v173 + 24);
    if ( v176 == 1 )
    {
      if ( (unsigned __int8)IppDoesNeighborNeedResolution(v5[5], *(_QWORD *)(v173 + 8)) )
      {
        if ( *(_DWORD *)(v173 + 28) < 2u )
        {
LABEL_413:
          if ( (BYTE2(WPP_MAIN_CB.Reserved) & 0x40) == 0 )
          {
LABEL_534:
            v157 = v262;
            v9[24] = *((_DWORD *)v5 + 13);
            *((_WORD *)v9 + 46) = v267;
            *((_WORD *)v9 + 52) = *((_WORD *)v5 + 28);
            v9[25] = *((_DWORD *)v5 + 17);
            if ( !v157
              || (int)IppBatchSendPacket(
                        v9,
                        *((unsigned __int8 *)v5 + 189),
                        *((unsigned __int8 *)v5 + 190),
                        *((unsigned __int8 *)v5 + 191)) < 0 )
            {
              IppPacketizeDatagrams((int)v9);
            }
            goto LABEL_537;
          }
          if ( v161 != 2 )
          {
            if ( (BYTE2(WPP_MAIN_CB.Reserved) & 0x40) != 0 )
            {
              v179 = IppGetPacketCount(*v5);
              McTemplateK0pqqqqqbr5qbr7qqq_EtwWriteTransfer(
                v161,
                (unsigned int)TCPIP_SEND_SLOW_PATH,
                *((unsigned __int16 *)v5 + 28),
                v180,
                *((_WORD *)v5 + 28),
                v161,
                0,
                0,
                16,
                **(_QWORD **)(*v174 + 16),
                16,
                v174[2],
                12,
                v179,
                6);
            }
            goto LABEL_534;
          }
          v243 = IppGetPacketCount(*v5);
          v239 = 12;
LABEL_416:
          McTemplateK0pqqqqqbr5qbr7qqq_EtwWriteTransfer(
            **(_QWORD **)(*v174 + 16),
            (unsigned int)TCPIP_SEND_SLOW_PATH,
            v174[2],
            v178,
            *((_WORD *)v5 + 28),
            2,
            ***(_DWORD ***)(*v174 + 16),
            *(_DWORD *)v174[2],
            0,
            0,
            0,
            0,
            v239,
            v243,
            4);
          goto LABEL_534;
        }
        IppResolveNeighbor(v173, 0, 0, 0);
      }
    }
    else
    {
      if ( v176 != 3 )
        goto LABEL_413;
      if ( *(_DWORD *)(v173 + 28) != 6 )
        goto LABEL_413;
      if ( *(int *)(v284 + 19696) < 1 )
        goto LABEL_413;
      v177 = *(_QWORD *)(*v174 + 8);
      if ( v175 != v177 || (*(_BYTE *)(v177 + 394) & 8) != 0 || *(_DWORD *)(v175 + 40) > 1u || !v9[9] )
        goto LABEL_413;
    }
    v181 = *(_DWORD *)(v173 + 24);
    LOBYTE(v283) = 0;
  }
  else
  {
    if ( *(_DWORD *)(v173 + 24) != 1 || !*((_BYTE *)v5 + 187) )
      goto LABEL_413;
    LOBYTE(v283) = 1;
    v181 = 1;
  }
  LODWORD(v255) = v181;
  if ( (Feature_5988_5730__private_featureState & 0x10) != 0 )
    v182 = Feature_5988_5730__private_featureState & 1;
  else
    v182 = ((__int64 (*)(void))Feature_5988_5730__private_IsEnabledDeviceUsageNoInline)();
  if ( v182 )
  {
    if ( !(unsigned __int8)IsSessionStateFastPathCompatible(v266, v181) )
    {
      v185 = BYTE2(WPP_MAIN_CB.Reserved) & 0x40;
      if ( (BYTE2(WPP_MAIN_CB.Reserved) & 0x40) == 0 )
        goto LABEL_534;
      if ( (_WORD)v258 == 2 )
      {
LABEL_438:
        v243 = IppGetPacketCount(*v5);
        v239 = 16;
        goto LABEL_416;
      }
LABEL_439:
      if ( v185 )
      {
        v186 = IppGetPacketCount(*v5);
        McTemplateK0pqqqqqbr5qbr7qqq_EtwWriteTransfer(
          v187,
          (unsigned int)TCPIP_SEND_SLOW_PATH,
          *((unsigned __int16 *)v5 + 28),
          v188,
          *((_WORD *)v5 + 28),
          v187,
          0,
          0,
          16,
          **(_QWORD **)(*v174 + 16),
          16,
          v174[2],
          16,
          v186,
          6);
      }
      goto LABEL_534;
    }
  }
  else if ( v266 )
  {
    v183 = *(_DWORD *)(v266 + 44) >> 8;
    if ( v181 == 1 )
    {
      v184 = (v183 & 0x10) == 0;
    }
    else
    {
      if ( v181 != 3 )
        goto LABEL_436;
      v184 = (v183 & 0x20) == 0;
    }
    if ( v184 )
    {
LABEL_436:
      v185 = BYTE2(WPP_MAIN_CB.Reserved) & 0x40;
      if ( (BYTE2(WPP_MAIN_CB.Reserved) & 0x40) == 0 )
        goto LABEL_534;
      if ( (_WORD)v258 == 2 )
        goto LABEL_438;
      goto LABEL_439;
    }
  }
  v189 = 18 * (v258 & 1);
  v286 = v189;
  if ( !(unsigned int)KfdIsLayerEmpty(*(unsigned __int16 *)((char *)qword_140220B48 + v189 + 2))
    || *(_DWORD *)v5[5] == 1634496585
    && !(unsigned int)KfdIsLayerEmpty(*(unsigned __int16 *)((char *)qword_140220B48 + v189)) )
  {
    if ( (BYTE2(WPP_MAIN_CB.Reserved) & 0x40) == 0 )
      goto LABEL_534;
    if ( (_WORD)v258 != 2 )
    {
      if ( (BYTE2(WPP_MAIN_CB.Reserved) & 0x40) != 0 )
      {
        v223 = IppGetPacketCount(*v5);
        McTemplateK0pqqqqqbr5qbr7qqq_EtwWriteTransfer(
          v224,
          (unsigned int)TCPIP_SEND_SLOW_PATH,
          *((unsigned __int16 *)v5 + 28),
          v225,
          *((_WORD *)v5 + 28),
          v224,
          0,
          0,
          16,
          **(_QWORD **)(*v174 + 16),
          16,
          v174[2],
          11,
          v223,
          6);
      }
      goto LABEL_534;
    }
    v243 = IppGetPacketCount(*v5);
    v239 = 11;
    goto LABEL_416;
  }
  if ( !(_BYTE)v283 )
  {
    if ( *(_DWORD *)(*(_QWORD *)(v175 + 48) + 12LL) != 6 )
    {
      if ( (BYTE2(WPP_MAIN_CB.Reserved) & 0x40) == 0 )
        goto LABEL_534;
      if ( (_WORD)v258 != 2 )
      {
        if ( (BYTE2(WPP_MAIN_CB.Reserved) & 0x40) != 0 )
        {
          v190 = IppGetPacketCount(*v5);
          McTemplateK0pqqqqqbr5qbr7qqq_EtwWriteTransfer(
            v191,
            (unsigned int)TCPIP_SEND_SLOW_PATH,
            *((unsigned __int16 *)v5 + 28),
            v192,
            *((_WORD *)v5 + 28),
            v191,
            0,
            0,
            16,
            **(_QWORD **)(*v174 + 16),
            16,
            v174[2],
            25,
            v190,
            6);
        }
        goto LABEL_534;
      }
      v243 = IppGetPacketCount(*v5);
      v239 = 25;
      goto LABEL_416;
    }
    if ( *((_WORD *)v5 + 28) == 6 )
    {
      if ( (*(_BYTE *)(v175 + 128) & 0x20) == 0 )
      {
        if ( (BYTE2(WPP_MAIN_CB.Reserved) & 0x40) != 0 )
        {
          if ( (_WORD)v258 == 2 )
          {
            v193 = IppGetPacketCount(*v5);
            McTemplateK0pqqqqqbr5qbr7qqq_EtwWriteTransfer(
              **(_QWORD **)(*v174 + 16),
              (unsigned int)TCPIP_SEND_SLOW_PATH,
              v174[2],
              v194,
              6,
              2,
              ***(_DWORD ***)(*v174 + 16),
              *(_DWORD *)v174[2],
              0,
              0,
              0,
              0,
              1,
              v193,
              4);
          }
          else if ( (BYTE2(WPP_MAIN_CB.Reserved) & 0x40) != 0 )
          {
            v244 = IppGetPacketCount(*v5);
            McTemplateK0pqqqqqbr5qbr7qqq_EtwWriteTransfer(
              v195,
              (unsigned int)TCPIP_SEND_SLOW_PATH,
              v196,
              v197,
              6,
              v195,
              0,
              0,
              16,
              **(_QWORD **)(*v174 + 16),
              16,
              v174[2],
              1,
              v244,
              6);
          }
        }
        goto LABEL_534;
      }
    }
    else if ( (*(_BYTE *)(v175 + 395) & 4) == 0 )
    {
      if ( (BYTE2(WPP_MAIN_CB.Reserved) & 0x40) != 0 )
      {
        if ( (_WORD)v258 == 2 )
        {
          v198 = IppGetPacketCount(*v5);
          McTemplateK0pqqqqqbr5qbr7qqq_EtwWriteTransfer(
            **(_QWORD **)(*v174 + 16),
            (unsigned int)TCPIP_SEND_SLOW_PATH,
            v174[2],
            v199,
            v200,
            2,
            ***(_DWORD ***)(*v174 + 16),
            *(_DWORD *)v174[2],
            0,
            0,
            0,
            0,
            2,
            v198,
            4);
        }
        else if ( (BYTE2(WPP_MAIN_CB.Reserved) & 0x40) != 0 )
        {
          v245 = IppGetPacketCount(*v5);
          McTemplateK0pqqqqqbr5qbr7qqq_EtwWriteTransfer(
            v201,
            (unsigned int)TCPIP_SEND_SLOW_PATH,
            v202,
            v203,
            v204,
            v201,
            0,
            0,
            16,
            **(_QWORD **)(*v174 + 16),
            16,
            v174[2],
            2,
            v245,
            6);
        }
      }
      goto LABEL_534;
    }
  }
  if ( *(_DWORD *)(v175 + 416) )
  {
    if ( (BYTE2(WPP_MAIN_CB.Reserved) & 0x40) == 0 )
      goto LABEL_534;
    if ( (_WORD)v258 != 2 )
    {
      if ( (BYTE2(WPP_MAIN_CB.Reserved) & 0x40) != 0 )
      {
        v205 = IppGetPacketCount(*v5);
        McTemplateK0pqqqqqbr5qbr7qqq_EtwWriteTransfer(
          v206,
          (unsigned int)TCPIP_SEND_SLOW_PATH,
          *((unsigned __int16 *)v5 + 28),
          v207,
          *((_WORD *)v5 + 28),
          v206,
          0,
          0,
          16,
          **(_QWORD **)(*v174 + 16),
          16,
          v174[2],
          14,
          v205,
          6);
      }
      goto LABEL_534;
    }
    v243 = IppGetPacketCount(*v5);
    v239 = 14;
    goto LABEL_416;
  }
  if ( !v257 || *(_QWORD *)v257 || *(_QWORD *)(v257 + 112) || !*(_QWORD *)(v257 + 8) || *(_DWORD *)(v257 + 140) )
  {
    if ( (BYTE2(WPP_MAIN_CB.Reserved) & 0x40) == 0 )
      goto LABEL_534;
    if ( (_WORD)v258 != 2 )
    {
      if ( (BYTE2(WPP_MAIN_CB.Reserved) & 0x40) != 0 )
      {
        v220 = IppGetPacketCount(*v5);
        McTemplateK0pqqqqqbr5qbr7qqq_EtwWriteTransfer(
          v221,
          (unsigned int)TCPIP_SEND_SLOW_PATH,
          *((unsigned __int16 *)v5 + 28),
          v222,
          *((_WORD *)v5 + 28),
          v221,
          0,
          0,
          16,
          **(_QWORD **)(*v174 + 16),
          16,
          v174[2],
          26,
          v220,
          6);
      }
      goto LABEL_534;
    }
    v243 = IppGetPacketCount(*v5);
    v239 = 26;
    goto LABEL_416;
  }
  v208 = (unsigned __int8)byte_140220B42[v286];
  v209 = *(unsigned __int16 *)(v284 + 28);
  LODWORD(v286) = v208;
  if ( (_BYTE)v283 )
  {
    if ( (unsigned int)WfpTlShimInspectFastLoopbackSendDatagram(v5[1], (unsigned __int16)v209, v257) )
    {
      if ( (BYTE2(WPP_MAIN_CB.Reserved) & 0x40) == 0 )
        goto LABEL_534;
      if ( v209 != 2 )
      {
        if ( (BYTE2(WPP_MAIN_CB.Reserved) & 0x40) != 0 )
        {
          v214 = IppGetPacketCount(*v5);
          McTemplateK0pqqqqqbr5qbr7qqq_EtwWriteTransfer(
            *v174,
            (unsigned int)TCPIP_SEND_SLOW_PATH,
            *((unsigned __int16 *)v5 + 28),
            v215,
            *((_WORD *)v5 + 28),
            v209,
            0,
            0,
            16,
            **(_QWORD **)(*v174 + 16),
            16,
            v174[2],
            28,
            v214,
            6);
        }
        goto LABEL_534;
      }
      v243 = IppGetPacketCount(*v5);
      v239 = 28;
      goto LABEL_416;
    }
  }
  else
  {
    if ( *((_DWORD *)v174 + 28) < *(_DWORD *)(*(_QWORD *)(v173 + 16) + 92LL) )
    {
      if ( (int *)v284 != &Ipv4Global || (v210 = 240, (v174[5] & 8) != 0) )
        v210 = *(_DWORD *)(v175 + 444);
      if ( (unsigned int)(MEMORY[0xFFFFF78000000008] / 0x2710uLL / 0x1F4) - *((_DWORD *)v174 + 29) >= v210 )
        goto LABEL_488;
      v208 = v286;
    }
    if ( *((_WORD *)v5 + 28) == 17
      && (unsigned __int8)IppIsFragNeededForNbl(v257, (unsigned int)(*((_DWORD *)v174 + 28) - v208)) )
    {
LABEL_488:
      if ( (BYTE2(WPP_MAIN_CB.Reserved) & 0x40) == 0 )
        goto LABEL_534;
      if ( v209 != 2 )
      {
        if ( (BYTE2(WPP_MAIN_CB.Reserved) & 0x40) != 0 )
        {
          v211 = IppGetPacketCount(*v5);
          McTemplateK0pqqqqqbr5qbr7qqq_EtwWriteTransfer(
            *v174,
            (unsigned int)TCPIP_SEND_SLOW_PATH,
            v212,
            v213,
            v212,
            v209,
            0,
            0,
            16,
            **(_QWORD **)(*v174 + 16),
            16,
            v174[2],
            4,
            v211,
            6);
        }
        goto LABEL_534;
      }
      v243 = IppGetPacketCount(*v5);
      v239 = 4;
      goto LABEL_416;
    }
  }
  if ( v247 )
    goto LABEL_534;
  if ( (Feature_5988_5730__private_featureState & 0x10) != 0 )
    v216 = Feature_5988_5730__private_featureState & 1;
  else
    v216 = ((__int64 (*)(void))Feature_5988_5730__private_IsEnabledDeviceUsageNoInline)();
  if ( v216 )
  {
    if ( (_DWORD)v256 == -1 )
    {
      if ( (_DWORD)v255 == 3 )
      {
        DWORD2(v264) = 1;
      }
      else if ( *(_BYTE *)(v175 + 448) )
      {
        DWORD2(v264) = *(unsigned __int8 *)(v175 + 448);
      }
      else
      {
        DWORD2(v264) = *(unsigned __int8 *)(*(_QWORD *)v175 + 65LL);
      }
    }
    v217 = HIDWORD(v256);
    if ( HIDWORD(v256) == 255 )
      v217 = 0;
    HIDWORD(v264) = v217;
  }
  v218 = (int *)v284;
  if ( !(_BYTE)v283 )
  {
    IpNlpFastContinueSendDatagrams(0, v286, v175, (_DWORD)v5, v284, v173, a2, v9[9], 0, (__int64)P);
    v157 = v262;
    goto LABEL_538;
  }
  v9[24] = *((_DWORD *)v5 + 13);
  *((_WORD *)v9 + 46) = v267;
  IppPreparePacketChecksum(v218, v9);
  v219 = (_DWORD *)v268;
  IpNlpFastContinueSendLoopbackDatagrams(0, v286, v175, (int)v5, (__int64)v218, a2, v9[9], v268, v9, (__int64)P);
  v157 = v262;
LABEL_539:
  if ( v254 )
  {
    if ( !v157 )
      PplFreeToLookasideList(IppControlPool);
    if ( v269 )
      PplFreeToLookasideList(IppJoinPathArgsPool);
  }
  else
  {
    --*v219;
  }
  if ( v157 && IppBatchPerProcState )
  {
    v236 = 80;
    if ( v218 != &Ipv4Global )
      v236 = 88;
    --**(_DWORD **)(v236 + *(_QWORD *)((char *)IppBatchPerProcState + v275));
  }
  v21 = v259;
LABEL_551:
  KeLowerIrql(v21);
}

```

## disassembly

```asm
0x1400a88e0  mov     [rsp-8+arg_8], rbx
0x1400a88e5  mov     [rsp-8+arg_18], r9
0x1400a88ea  mov     [rsp-8+arg_10], r8
0x1400a88ef  mov     byte ptr [rsp-8+arg_0], cl
0x1400a88f3  push    rbp
0x1400a88f4  push    rsi
0x1400a88f5  push    rdi
0x1400a88f6  push    r12
0x1400a88f8  push    r13
0x1400a88fa  push    r14
0x1400a88fc  push    r15
0x1400a88fe  lea     rbp, [rsp-0D0h]
0x1400a8906  sub     rsp, 1D0h
0x1400a890d  mov     rsi, [rbp+100h+arg_20]
0x1400a8914  xorps   xmm0, xmm0
0x1400a8917  xor     eax, eax
0x1400a8919  xor     r15b, r15b
0x1400a891c  mov     [rbp+100h+var_40], rax
0x1400a8923  mov     cl, 2; NewIrql
0x1400a8925  mov     r14, r8
0x1400a8928  mov     [rbp+100h+var_134], r15d
0x1400a892c  movzx   eax, word ptr [rsi+30h]
0x1400a8930  movzx   edi, dl
0x1400a8933  mov     rbx, [rsi]
0x1400a8936  xor     r13d, r13d
0x1400a8939  mov     [rbp+100h+var_F8], eax
0x1400a893c  mov     [rbp+100h+var_150], rbx
0x1400a8940  movups  [rbp+100h+var_A0], xmm0
0x1400a8944  movups  [rbp+100h+var_90], xmm0
0x1400a8948  movups  [rbp+100h+var_80], xmm0
0x1400a894f  movups  [rbp+100h+var_70], xmm0
0x1400a8956  movups  [rbp+100h+var_60], xmm0
0x1400a895d  movups  [rbp+100h+var_50], xmm0
0x1400a8964  movups  xmmword ptr [rbp+100h+P], xmm0
0x1400a8968  movups  [rbp+100h+var_120], xmm0
0x1400a896c  movups  [rbp+100h+var_110], xmm0
0x1400a8970  call    cs:__imp_KfRaiseIrql
0x1400a8977  nop     dword ptr [rax+rax+00h]
0x1400a897c  mov     [rbp+100h+var_140], al
0x1400a897f  lea     r8, Ipv4Global
0x1400a8986  movzx   r12d, al
0x1400a898a  mov     r11d, 58h ; 'X'
0x1400a8990  mov     eax, gs:1A4h
0x1400a8998  mov     r10d, 1
0x1400a899e  mov     [rbp+100h+var_B0], rax
0x1400a89a2  lea     rdx, ds:0[rax*8]
0x1400a89aa  mov     rax, cs:SendPerProcessorState
0x1400a89b1  mov     [rbp+100h+var_A8], rdx
0x1400a89b5  mov     r9, [rdx+rax]
0x1400a89b9  mov     [rbp+100h+var_F0], r9
0x1400a89bd  cmp     [rsi+0BCh], r13b
0x1400a89c4  jz      short loc_1400A8A15
0x1400a89c6  mov     rax, cs:IppBatchPerProcState
0x1400a89cd  test    rax, rax
0x1400a89d0  jz      short loc_1400A8A15
0x1400a89d2  mov     rax, [rdx+rax]
0x1400a89d6  cmp     r14, r8
0x1400a89d9  mov     ecx, 50h ; 'P'
0x1400a89de  cmovnz  ecx, r11d
0x1400a89e2  mov     rdx, [rcx+rax]
0x1400a89e6  mov     r8d, [rdx]
0x1400a89e9  cmp     r8d, cs:IppMaxBatchSize
0x1400a89f0  jnb     short loc_1400A8A06
0x1400a89f2  imul    r13, r8, 150h
0x1400a89f9  lea     eax, [r8+1]
0x1400a89fd  add     r13, 8
0x1400a8a01  mov     [rdx], eax
0x1400a8a03  add     r13, rdx
0x1400a8a06  test    r13, r13
0x1400a8a09  movzx   r15d, r15b
0x1400a8a0d  cmovnz  r15d, r10d
0x1400a8a11  mov     [rbp+100h+var_134], r15d
0x1400a8a15  movsxd  rcx, dword ptr [r9]
0x1400a8a18  cmp     ecx, 3
0x1400a8a1b  jge     short loc_1400A8A58
0x1400a8a1d  mov     [rbp+100h+var_168], 0
0x1400a8a21  mov     rdx, rcx
0x1400a8a24  test    r15b, r15b
0x1400a8a27  jnz     short loc_1400A8A37
0x1400a8a29  imul    r13, rdx, 150h
0x1400a8a30  add     r13, 8
0x1400a8a34  add     r13, r9
0x1400a8a37  lea     r15, [rcx+rcx*4]
0x1400a8a3b  shl     r15, 5
0x1400a8a3f  lea     eax, [rcx+1]
0x1400a8a42  add     r15, 3F8h
0x1400a8a49  mov     [r9], eax
0x1400a8a4c  add     r15, r9
0x1400a8a4f  mov     [rbp+100h+var_E8], r15
0x1400a8a53  jmp     loc_1400A8B3C
0x1400a8a58  test    r15b, r15b
0x1400a8a5b  jnz     loc_1400A8B32
0x1400a8a61  mov     eax, gs:1A4h
0x1400a8a69  mov     r8, cs:IppControlPool
0x1400a8a70  lea     ebx, [rax+1]
0x1400a8a73  shl     rbx, 7
0x1400a8a77  add     rbx, r8
0x1400a8a7a  movzx   eax, byte ptr [rbx+0B0h]
0x1400a8a81  test    al, al
0x1400a8a83  jnz     short loc_1400A8A91
0x1400a8a85  lea     rdx, [rbx+40h]
0x1400a8a89  mov     rcx, r8
0x1400a8a8c  call    PplpLazyInitializeLookasideList
0x1400a8a91  lea     rcx, [rbx+40h]; Lookaside
0x1400a8a95  call    cs:__imp_ExAllocateFromLookasideListEx
0x1400a8a9c  nop     dword ptr [rax+rax+00h]
0x1400a8aa1  mov     r13, rax
0x1400a8aa4  test    rax, rax
0x1400a8aa7  jnz     loc_1400A8B2E
0x1400a8aad  cmp     byte ptr cs:WPP_MAIN_CB.Reserved+3, al
0x1400a8ab3  jge     short loc_1400A8ACF
0x1400a8ab5  lea     r9, aControlIpng; "control (IPNG)"
0x1400a8abc  lea     rdx, TCPIP_MEMORY_FAILURES
0x1400a8ac3  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x1400a8aca  call    McTemplateK0z_EtwWriteTransfer
0x1400a8acf  mov     rbx, [rbp+100h+var_150]
0x1400a8ad3  mov     dword ptr [rbx+8Ch], 0C000009Ah
0x1400a8add  cmp     byte ptr cs:WPP_MAIN_CB.Reserved+6, 0
0x1400a8ae4  jl      short loc_1400A8AEF
0x1400a8ae6  cmp     cs:byte_140225C70, 0
0x1400a8aed  jz      short loc_1400A8B14
0x1400a8aef  mov     rcx, [rbp+100h+arg_10]
0x1400a8af6  mov     r9, rbx
0x1400a8af9  mov     dword ptr [rsp+200h+var_1D8], 0E0004160h
0x1400a8b01  mov     r8, r13
0x1400a8b04  mov     rdx, rsi
0x1400a8b07  mov     dword ptr [rsp+200h+Src], 108h
0x1400a8b0f  call    IppLogSendDatagramsDiscard
0x1400a8b14  mov     dl, 1
0x1400a8b16  mov     rcx, rbx
0x1400a8b19  call    cs:__imp_NetioDereferenceNetBufferListChain
0x1400a8b20  nop     dword ptr [rax+rax+00h]
0x1400a8b25  movzx   ecx, r12b
0x1400a8b29  jmp     loc_1400AB700
0x1400a8b2e  mov     rbx, [rbp+100h+var_150]
0x1400a8b32  xor     ecx, ecx
0x1400a8b34  mov     [rbp+100h+var_168], 1
0x1400a8b38  mov     [rbp+100h+var_E8], rcx
0x1400a8b3c  xor     edx, edx; Val
0x1400a8b3e  mov     r8d, 150h; Size
0x1400a8b44  mov     rcx, r13; void *
0x1400a8b47  call    memset
0x1400a8b4c  movzx   ecx, byte ptr [r13+58h]
0x1400a8b51  mov     r9d, 0FFFFFFFFh
0x1400a8b57  movzx   r8d, byte ptr [r13+0B9h]
0x1400a8b5f  movzx   edx, dil
0x1400a8b63  or      byte ptr [r13+0B8h], 10h
0x1400a8b6b  add     dl, dl
0x1400a8b6d  or      r8b, 40h
0x1400a8b71  mov     dword ptr [rbp+100h+var_158], r9d
0x1400a8b75  movzx   eax, dl
0x1400a8b78  mov     [r13+24h], r9d
0x1400a8b7c  xor     al, cl
0x1400a8b7e  mov     dword ptr [r13+28h], 0FFh
0x1400a8b86  and     al, 4
0x1400a8b88  mov     dword ptr [r13+6Ch], 0FFFFFFFFh
0x1400a8b90  xor     al, cl
0x1400a8b92  mov     [r13+8], rbx
0x1400a8b96  mov     [r13+58h], al
0x1400a8b9a  movzx   eax, dl
0x1400a8b9d  xor     al, r8b
0x1400a8ba0  and     al, 8
0x1400a8ba2  xor     al, r8b
0x1400a8ba5  mov     [r13+0B9h], al
0x1400a8bac  movzx   eax, byte ptr [r13+0BAh]
0x1400a8bb4  movzx   ecx, al
0x1400a8bb7  xor     cl, dl
0x1400a8bb9  and     cl, 40h
0x1400a8bbc  xor     cl, al
0x1400a8bbe  mov     [r13+0BAh], cl
0x1400a8bc5  mov     eax, cs:Feature_5988_5730__private_featureState
0x1400a8bcb  test    al, 10h
0x1400a8bcd  jz      short loc_1400A8BD4
0x1400a8bcf  and     eax, 1
0x1400a8bd2  jmp     short loc_1400A8BDF
0x1400a8bd4  call    Feature_5988_5730__private_IsEnabledDeviceUsageNoInline
0x1400a8bd9  mov     r9d, 0FFFFFFFFh
0x1400a8bdf  test    eax, eax
0x1400a8be1  jz      short loc_1400A8C18
0x1400a8be3  movzx   r14d, dil
0x1400a8be7  mov     dword ptr [rbp+100h+var_120+8], r9d
0x1400a8beb  and     r14b, 2
0x1400a8bef  mov     dword ptr [rbp+100h+var_110], 0FFFFFFFFh
0x1400a8bf6  add     r14b, r14b
0x1400a8bf9  mov     r8d, 0FFh
0x1400a8bff  mov     [rbp+100h+var_17F], r14b
0x1400a8c03  mov     byte ptr [rbp+100h+var_110+4], r14b
0x1400a8c07  mov     r14, [rbp+100h+arg_10]
0x1400a8c0e  mov     dword ptr [rbp+100h+var_158+4], r8d
0x1400a8c12  mov     dword ptr [rbp+100h+var_120+0Ch], r8d
0x1400a8c16  jmp     short loc_1400A8C2B
0x1400a8c18  movzx   eax, byte ptr [rbp+100h+var_110+4]
0x1400a8c1c  mov     [rbp+100h+var_17F], al
0x1400a8c1f  mov     eax, dword ptr [rbp+100h+var_120+0Ch]
0x1400a8c22  mov     dword ptr [rbp+100h+var_158+4], eax
0x1400a8c25  mov     eax, dword ptr [rbp+100h+var_120+8]
0x1400a8c28  mov     dword ptr [rbp+100h+var_158], eax
0x1400a8c2b  movzx   eax, byte ptr [r13+0BAh]
0x1400a8c33  movzx   ecx, byte ptr [rsi+0B8h]
0x1400a8c3a  shl     cl, 2
0x1400a8c3d  xor     cl, al
0x1400a8c3f  and     cl, 4
0x1400a8c42  xor     cl, al
0x1400a8c44  mov     [r13+0BAh], cl
0x1400a8c4b  mov     rdx, [rsi+10h]
0x1400a8c4f  movzx   r12d, word ptr [r14+1Ch]
0x1400a8c54  mov     [rbp+100h+var_148], r12
0x1400a8c58  test    rdx, rdx
0x1400a8c5b  jnz     loc_1400A8D5E
0x1400a8c61  mov     r8, r13
0x1400a8c64  mov     rdx, rsi
0x1400a8c67  mov     rcx, r14
0x1400a8c6a  call    IppProcessRawData
0x1400a8c6f  mov     r15d, eax
0x1400a8c72  test    eax, eax
0x1400a8c74  jns     short loc_1400A8C87
0x1400a8c76  mov     r14d, 10Dh
0x1400a8c7c  mov     r8d, 0E0004161h
0x1400a8c82  jmp     loc_1400AA699
0x1400a8c87  movzx   eax, byte ptr cs:WPP_MAIN_CB.Reserved+2
0x1400a8c8e  mov     [rbp+100h+var_180], 1
0x1400a8c92  and     al, 40h
0x1400a8c94  jz      loc_1400A8D91
0x1400a8c9a  cmp     r12w, 2
0x1400a8c9f  jnz     short loc_1400A8CFD
0x1400a8ca1  mov     r9, [rsi]
0x1400a8ca4  mov     rcx, r9
0x1400a8ca7  call    IppGetPacketCount
0x1400a8cac  movzx   ecx, word ptr [rsi+38h]
0x1400a8cb0  lea     rdx, TCPIP_SEND_SLOW_PATH
0x1400a8cb7  mov     [rsp+200h+var_190], 4
0x1400a8cbf  mov     dword ptr [rsp+200h+var_198], eax
0x1400a8cc3  xor     eax, eax
0x1400a8cc5  mov     dword ptr [rsp+200h+var_1A0], 14h
0x1400a8ccd  mov     [rsp+200h+var_1A8], rax
0x1400a8cd2  mov     [rsp+200h+var_1B0], eax
0x1400a8cd6  mov     [rsp+200h+var_1B8], rax
0x1400a8cdb  mov     dword ptr [rsp+200h+var_1C0], eax
0x1400a8cdf  mov     dword ptr [rsp+200h+var_1C8], eax
0x1400a8ce3  mov     [rsp+200h+var_1D0], eax
0x1400a8ce7  mov     dword ptr [rsp+200h+var_1D8], 2
0x1400a8cef  mov     dword ptr [rsp+200h+Src], ecx
0x1400a8cf3  call    McTemplateK0pqqqqqbr5qbr7qqq_EtwWriteTransfer
0x1400a8cf8  jmp     loc_1400A8D91
0x1400a8cfd  test    al, al
0x1400a8cff  jz      loc_1400A8D91
0x1400a8d05  mov     r9, [rsi]
0x1400a8d08  mov     rcx, r9
0x1400a8d0b  call    IppGetPacketCount
0x1400a8d10  movzx   edx, word ptr [rsi+38h]
0x1400a8d14  mov     [rsp+200h+var_190], 6
0x1400a8d1c  mov     dword ptr [rsp+200h+var_198], eax
0x1400a8d20  xor     eax, eax
0x1400a8d22  mov     dword ptr [rsp+200h+var_1A0], 14h
0x1400a8d2a  mov     [rsp+200h+var_1A8], rax
0x1400a8d2f  mov     [rsp+200h+var_1B0], eax
0x1400a8d33  mov     [rsp+200h+var_1B8], rax
0x1400a8d38  mov     dword ptr [rsp+200h+var_1C0], eax
0x1400a8d3c  mov     dword ptr [rsp+200h+var_1C8], eax
0x1400a8d40  mov     [rsp+200h+var_1D0], eax
0x1400a8d44  movzx   ecx, r12w
0x1400a8d48  mov     dword ptr [rsp+200h+var_1D8], ecx
0x1400a8d4c  mov     dword ptr [rsp+200h+Src], edx
0x1400a8d50  lea     rdx, TCPIP_SEND_SLOW_PATH
0x1400a8d57  call    McTemplateK0pqqqqqbr5qbr7qqq_EtwWriteTransfer
0x1400a8d5c  jmp     short loc_1400A8D91
0x1400a8d5e  movzx   ecx, word ptr [rsi+38h]
0x1400a8d62  xor     r15d, r15d
0x1400a8d65  mov     [rbp+100h+var_180], r15b
0x1400a8d69  sub     ecx, 1
0x1400a8d6c  jz      short loc_1400A8D7D
0x1400a8d6e  sub     ecx, 5
0x1400a8d71  jz      short loc_1400A8DD1
0x1400a8d73  sub     ecx, 0Bh
0x1400a8d76  jz      short loc_1400A8DD1
0x1400a8d78  cmp     ecx, 29h ; ')'
0x1400a8d7b  jnz     short loc_1400A8D87
0x1400a8d7d  mov     rax, [rdx]
0x1400a8d80  mov     [r13+0BCh], rax
0x1400a8d87  mov     eax, [rsi+3Ch]
0x1400a8d8a  mov     [r13+0C4h], eax
0x1400a8d91  mov     rdx, [rsi+90h]
0x1400a8d98  xor     bl, bl
0x1400a8d9a  mov     byte ptr [rbp+100h+arg_0], bl
0x1400a8da0  test    rdx, rdx
0x1400a8da3  jnz     short loc_1400A8DAD
0x1400a8da5  mov     rax, [rsi+20h]
0x1400a8da9  mov     rdx, [rax+10h]; Src
0x1400a8dad  mov     rax, [r14+10h]
0x1400a8db1  lea     rcx, [r13+0E8h]; void *
0x1400a8db8  movzx   r8d, word ptr [rax+6]; Size
0x1400a8dbd  call    memmove
0x1400a8dc2  mov     eax, cs:Feature_5988_5730__private_featureState
0x1400a8dc8  test    al, 10h
0x1400a8dca  jz      short loc_1400A8DDC
0x1400a8dcc  and     eax, 1
0x1400a8dcf  jmp     short loc_1400A8DE1
0x1400a8dd1  mov     eax, [rdx]
0x1400a8dd3  mov     [r13+0BCh], eax
0x1400a8dda  jmp     short loc_1400A8D87
  ... truncated ...
```
