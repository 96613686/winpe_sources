# WfpAlepAuthorizeSend

- ea: `0x14013fc30`
- end: `0x1401412eb`
- name: `WfpAlepAuthorizeSend`
- size: `5819`
- prototype: `__int64 __fastcall(PKSPIN_LOCK SpinLock, unsigned __int16, unsigned __int16 *, unsigned __int16, int, __int64, _OWORD *, __int16, char, char, __int64, _OWORD *, __int16, __int64, __int64, int, char, __int64, __int64, int, int, __int64, __int64, __int64, _DWORD *, _QWORD *, __int64, __int64, _DWORD *, __int64)`
- caller_count: `1`
- callee_count: `23`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400aed00`

## callees

- `0x14001215c`
- `0x1400143c0`
- `0x140014480`
- `0x140014974`
- `0x140015a70`
- `0x1400162f0`
- `0x140016470`
- `0x14005ff90`
- `0x140061630`
- `0x1400acfc0`
- `0x1400ad6a0`
- `0x1400b1140`
- `0x1400e4064`
- `0x1401014ac`
- `0x140127de8`
- `0x14013b990`
- `0x14013fc30`
- `0x140141b90`
- `0x140150f98`
- `0x140173314`
- `0x1401c0fd0`
- `0x1401c1280`
- `0x1401c1580`

## import_xrefs

- `ntoskrnl!ExFreeToLookasideListEx` at `0x14013ff0f`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1401410f6`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140141222`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140141262`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14013ff0f`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1401410f6`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140141222`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140141262`
- `ntoskrnl!KeGetCurrentIrql` at `0x14013fe61`
- `ntoskrnl!KeGetCurrentIrql` at `0x14013fe61`
- `ntoskrnl!KeInitializeSpinLock` at `0x14013fe34`
- `ntoskrnl!KeInitializeSpinLock` at `0x14013fe34`
- `ntoskrnl!ExFreePoolWithTag` at `0x140141031`
- `ntoskrnl!ExFreePoolWithTag` at `0x140141076`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401410ad`
- `ntoskrnl!ExFreePoolWithTag` at `0x140141110`
- `ntoskrnl!ExFreePoolWithTag` at `0x14014112a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140141031`
- `ntoskrnl!ExFreePoolWithTag` at `0x140141076`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401410ad`
- `ntoskrnl!ExFreePoolWithTag` at `0x140141110`
- `ntoskrnl!ExFreePoolWithTag` at `0x14014112a`
- `NETIO!NetioDereferenceNetBufferList` at `0x14014105c`
- `NETIO!NetioDereferenceNetBufferList` at `0x14014105c`
- `NETIO!NetioReferenceNetBufferList` at `0x140140e0b`
- `NETIO!NetioReferenceNetBufferList` at `0x140140e0b`
- `NETIO!FeReleaseCompletionHandle` at `0x14013ff86`
- `NETIO!FeReleaseCompletionHandle` at `0x14013ff86`
- `NETIO!FeAcquireGenericCompletionHandle` at `0x14014065a`
- `NETIO!FeAcquireGenericCompletionHandle` at `0x14014065a`
- `NETIO!FeAcquireCompletionHandle` at `0x140140649`
- `NETIO!FeAcquireCompletionHandle` at `0x140140649`
- `NETIO!KfdAleInitializeFlowTable` at `0x1401408ae`
- `NETIO!KfdAleInitializeFlowTable` at `0x1401408ae`
- `NETIO!KfdAleNotifyFlowDeletion` at `0x140141190`
- `NETIO!KfdAleNotifyFlowDeletion` at `0x140141190`
- `NETIO!KfdReleaseTerminatingFilters` at `0x1401411d0`
- `NETIO!KfdReleaseTerminatingFilters` at `0x1401411d0`
- `NETIO!KfdAleReleaseFlowHandleForFlow` at `0x1401408f7`
- `NETIO!KfdAleReleaseFlowHandleForFlow` at `0x1401408f7`
- `NETIO!KfdAleAcquireFlowHandleForFlow` at `0x1401408c8`
- `NETIO!KfdAleAcquireFlowHandleForFlow` at `0x1401408c8`
- `NETIO!KfdGetLayerCacheEpoch` at `0x14014071d`
- `NETIO!KfdGetLayerCacheEpoch` at `0x14014071d`

## pseudocode

```c
__int64 __fastcall WfpAlepAuthorizeSend(
        PKSPIN_LOCK SpinLock,
        unsigned __int16 a2,
        unsigned __int16 *a3,
        unsigned __int16 a4,
        int a5,
        __int64 a6,
        _OWORD *a7,
        __int16 a8,
        char a9,
        char a10,
        __int64 a11,
        _OWORD *a12,
        __int16 a13,
        __int64 a14,
        __int64 a15,
        int a16,
        char a17,
        __int64 a18,
        __int64 a19,
        int a20,
        int a21,
        __int64 a22,
        __int64 a23,
        __int64 a24,
        _DWORD *a25,
        _QWORD *a26,
        __int64 a27,
        __int64 a28,
        _DWORD *a29,
        __int64 a30)
{
  __int64 v30; // rdi
  __int128 *v33; // r13
  PVOID v34; // rsi
  _DWORD *v35; // rbx
  __int64 v36; // r8
  __int64 v37; // r9
  PDEVICE_OBJECT *v38; // rdx
  char v39; // r12
  PDEVICE_OBJECT v40; // rcx
  __int64 inserted; // rdi
  bool v42; // zf
  int v43; // eax
  __int64 v44; // rcx
  __int64 v45; // r8
  __int64 v46; // r9
  char *v47; // rbx
  KSPIN_LOCK v48; // rcx
  KSPIN_LOCK v49; // rcx
  KSPIN_LOCK v50; // rax
  __int64 *v51; // rcx
  __int64 v52; // rax
  __int64 v53; // r12
  size_t v54; // r8
  unsigned __int16 v55; // dx
  __int64 v56; // rax
  _OWORD *v57; // rax
  int v58; // ecx
  __int64 v59; // r12
  __int16 v60; // cx
  __int16 v61; // cx
  __int64 v62; // rdx
  char v63; // cl
  int ProfileIdFromInterface; // eax
  __int64 v65; // r8
  unsigned int v66; // eax
  int v67; // ecx
  int v68; // ecx
  int v69; // r9d
  __int64 v70; // rcx
  int v71; // r8d
  int v72; // edx
  __int64 v73; // rdx
  __int64 v74; // r8
  __int64 v75; // r9
  char v76; // r11
  __int64 v77; // rax
  __int64 OriginalAppId; // r10
  int v79; // r8d
  int v80; // edx
  int v81; // eax
  __int64 v82; // rdx
  int v83; // ecx
  int v84; // eax
  __int64 v85; // rcx
  KSPIN_LOCK v86; // rcx
  unsigned __int16 v87; // r14
  __int64 v88; // rcx
  __int64 v89; // rax
  KSPIN_LOCK v90; // rcx
  int v91; // r8d
  __int64 v92; // rax
  bool v93; // al
  bool v94; // r14
  __int64 *v95; // rdx
  __int16 v96; // cx
  __int64 v97; // r14
  __int64 v98; // rax
  __int64 v99; // r9
  __int64 v100; // r8
  __int64 v101; // rdx
  __int64 v102; // rax
  __int64 v103; // rdx
  unsigned int v104; // eax
  unsigned int v105; // eax
  PVOID v106; // r8
  __int128 *v107; // rcx
  __int128 *v108; // rax
  __int128 v109; // xmm0
  __int64 v110; // rcx
  __int64 v111; // rcx
  volatile signed __int32 *v112; // rax
  int v113; // ecx
  __int64 *v114; // r9
  char v115; // al
  __int64 v116; // rcx
  void *v117; // rcx
  void *v118; // rcx
  char *v119; // r14
  __int64 LockArray_high; // rax
  PVOID *v121; // r14
  __int64 v122; // r8
  __int64 v123; // r9
  char *v124; // r14
  __int64 v125; // r8
  __int64 v126; // r9
  char *v127; // rbx
  __int64 v129; // [rsp+28h] [rbp-118h]
  char v130; // [rsp+C0h] [rbp-80h]
  char v131; // [rsp+C1h] [rbp-7Fh]
  char v132; // [rsp+C2h] [rbp-7Eh]
  unsigned __int8 v133; // [rsp+C3h] [rbp-7Dh]
  unsigned __int8 v134[2]; // [rsp+C4h] [rbp-7Ch] BYREF
  unsigned __int16 v135; // [rsp+C6h] [rbp-7Ah]
  __int16 v136; // [rsp+C8h] [rbp-78h]
  unsigned __int16 v137; // [rsp+CAh] [rbp-76h]
  __int16 v138; // [rsp+CCh] [rbp-74h]
  __int64 v139; // [rsp+D0h] [rbp-70h] BYREF
  int v140; // [rsp+D8h] [rbp-68h] BYREF
  int v141; // [rsp+DCh] [rbp-64h]
  PVOID Entry; // [rsp+E0h] [rbp-60h] BYREF
  __int64 v143; // [rsp+E8h] [rbp-58h]
  __int64 v144; // [rsp+F0h] [rbp-50h]
  __int64 v145; // [rsp+F8h] [rbp-48h]
  __int64 v146; // [rsp+100h] [rbp-40h]
  __int64 v147; // [rsp+108h] [rbp-38h]
  __int64 v148; // [rsp+110h] [rbp-30h] BYREF
  PVOID P; // [rsp+118h] [rbp-28h]
  __int64 v150; // [rsp+120h] [rbp-20h] BYREF
  size_t Size[2]; // [rsp+128h] [rbp-18h] BYREF
  __int64 v152; // [rsp+138h] [rbp-8h]
  PVOID v153; // [rsp+140h] [rbp+0h]
  __int64 v154; // [rsp+148h] [rbp+8h] BYREF
  __int64 v155; // [rsp+150h] [rbp+10h]
  __int64 v156; // [rsp+158h] [rbp+18h]
  void *v157; // [rsp+160h] [rbp+20h] BYREF
  void *v158; // [rsp+168h] [rbp+28h] BYREF
  __int64 v159; // [rsp+170h] [rbp+30h]
  __int64 v160; // [rsp+178h] [rbp+38h] BYREF
  void *v161; // [rsp+180h] [rbp+40h] BYREF
  __int64 v162; // [rsp+188h] [rbp+48h] BYREF
  KSPIN_LOCK v163; // [rsp+190h] [rbp+50h]
  _DWORD *v164; // [rsp+198h] [rbp+58h]
  __int64 v165; // [rsp+1A0h] [rbp+60h] BYREF
  __int64 v166; // [rsp+1A8h] [rbp+68h]
  __int64 v167; // [rsp+1B0h] [rbp+70h] BYREF
  __int64 v168; // [rsp+1B8h] [rbp+78h]
  __int64 v169; // [rsp+1C0h] [rbp+80h] BYREF
  __int64 v170; // [rsp+1C8h] [rbp+88h]
  __int128 v171; // [rsp+1D0h] [rbp+90h] BYREF
  __int128 v172; // [rsp+1E0h] [rbp+A0h] BYREF
  __int64 v173; // [rsp+1F0h] [rbp+B0h]
  __int64 v174; // [rsp+1F8h] [rbp+B8h]
  _DWORD *v175; // [rsp+200h] [rbp+C0h]
  KSPIN_LOCK SpinLocka[59]; // [rsp+208h] [rbp+C8h] BYREF
  __int128 v177; // [rsp+3E0h] [rbp+2A0h] BYREF
  __int128 v178; // [rsp+3F0h] [rbp+2B0h] BYREF

  v30 = a18;
  v136 = a13;
  v33 = 0;
  v34 = 0;
  v155 = a24;
  v35 = 0;
  v152 = a14;
  v164 = a25;
  v138 = a8;
  v156 = a11;
  v145 = a15;
  v130 = a17;
  v146 = a19;
  v147 = a22;
  v150 = a23;
  v159 = a27;
  *(_QWORD *)&v178 = a28;
  v175 = a29;
  v135 = a2;
  *(_QWORD *)&v177 = a30;
  v141 = a5;
  v144 = a6;
  LODWORD(v166) = 0;
  LODWORD(v168) = 0;
  LODWORD(v163) = 0;
  LODWORD(v170) = 0;
  v165 = 0;
  v167 = 0;
  v162 = 0;
  v169 = 0;
  v137 = a4;
  v174 = a18;
  v143 = (__int64)a26;
  v140 = 0;
  v158 = 0;
  Entry = 0;
  v172 = 0;
  v173 = 0;
  v131 = 0;
  v134[0] = 0;
  *(_OWORD *)Size = 0;
  v139 = 0;
  v171 = 0;
  v133 = 0;
  v132 = 0;
  memset(SpinLocka, 0, sizeof(SpinLocka));
  v38 = &WPP_GLOBAL_Control;
  v154 = 0;
  v160 = 0;
  P = 0;
  v161 = 0;
  v153 = 0;
  v157 = 0;
  v148 = 0;
  *a26 = 0;
  if ( !v130 || !v30 || *(_DWORD *)(v30 + 464) && *(_QWORD *)(v30 + 472) )
  {
    KeInitializeSpinLock(SpinLocka);
    v43 = *((_DWORD *)SpinLock + 12);
    LODWORD(SpinLocka[1]) = 0;
    *(_OWORD *)&SpinLocka[2] = 0;
    if ( (v43 & 0x10) != 0 )
      _InterlockedOr((volatile signed __int32 *)&SpinLocka[6], 0x10u);
    if ( KeGetCurrentIrql() < 2u )
    {
      v133 = WfpRaiseIrqlToDispatchLevel();
      v132 = 1;
    }
    LODWORD(v44) = HIDWORD(KeGetPcr()[1].LockArray);
    if ( !*((_BYTE *)gPerProcessorContext + 72 * v44 + 32) )
    {
      v34 = (PVOID)*((_QWORD *)gPerProcessorContext + 9 * v44 + 3);
      v35 = (_DWORD *)*((_QWORD *)gPerProcessorContext + 9 * v44 + 2);
      *((_BYTE *)gPerProcessorContext + 72 * v44 + 32) = 1;
      goto LABEL_27;
    }
    if ( !WfpAllocateFromPerProcessorLookasideList(gIncomingValuesLookasideList, &Entry) )
    {
      if ( !WfpAllocateFromPerProcessorLookasideList(gMetadataLookasideList, &v139) )
      {
        v34 = Entry;
        v35 = (_DWORD *)v139;
LABEL_27:
        memset(v34, 0, 0x2A0u);
        memset(v35, 0, 0x2A8u);
        *((_QWORD *)v35 + 79) = v35 + 156;
        *((_QWORD *)v35 + 78) = v35 + 156;
        v48 = SpinLock[60];
        LOWORD(v171) = v135;
        DWORD1(v171) = *a3;
        *((_QWORD *)&v171 + 1) = v34;
        v166 = *(_QWORD *)(v48 + 16);
        LODWORD(v165) = *(unsigned __int16 *)(v48 + 10);
        *((_DWORD *)v34 + 4 * a3[1]) = 12;
        *((_QWORD *)v34 + 2 * a3[1] + 1) = &v165;
        v49 = SpinLock[61];
        v163 = v49 + 224;
        LODWORD(v162) = *(_DWORD *)(v49 + 72);
        *((_DWORD *)v34 + 4 * a3[2]) = 16;
        *((_QWORD *)v34 + 2 * a3[2] + 1) = &v162;
        v50 = SpinLock[61];
        v51 = *(__int64 **)(v50 + 280);
        if ( v51 )
        {
          if ( (*(_DWORD *)(v50 + 268) & 0x4000) != 0 )
            _InterlockedOr((volatile signed __int32 *)&SpinLocka[6], 0x2000000u);
        }
        else
        {
          v51 = gAleNullSid;
        }
        *((_DWORD *)v34 + 4 * a3[41]) = 16;
        *((_QWORD *)v34 + 2 * a3[41] + 1) = &v162;
        *((_QWORD *)v35 + 70) = SpinLock;
        *((_DWORD *)v34 + 4 * a3[37]) = 13;
        *((_QWORD *)v34 + 2 * a3[37] + 1) = v51;
        v52 = *(_QWORD *)(SpinLock[61] + 144);
        if ( v52 )
        {
          v53 = *(_QWORD *)(*(_QWORD *)(v52 + 8) + 32LL);
          LODWORD(v139) = (unsigned __int16)(*(_WORD *)(v53 + 8) + 2);
          LODWORD(Size[0]) = v139 + 8;
          inserted = WfpPoolAllocNonPaged((unsigned int)(v139 + 8), 1668376129, &Size[1]);
          if ( inserted )
            goto LABEL_173;
          memset((void *)Size[1], 0, LODWORD(Size[0]));
          v54 = (unsigned __int16)v139;
          *(_QWORD *)Size[1] = *(_QWORD *)v53;
          memmove((void *)(Size[1] + 8), *(const void **)(v53 + 16), v54);
          v30 = v174;
        }
        v55 = v137;
        v56 = 2LL * a3[38];
        Entry = 0;
        *((_DWORD *)v34 + 2 * v56) = 12;
        *((_QWORD *)v34 + 2 * a3[38] + 1) = Size;
        v57 = a12;
        *((_OWORD *)v34 + a3[3]) = *a7;
        *((_OWORD *)v34 + a3[7]) = *v57;
        v58 = v141;
        *((_DWORD *)v34 + 4 * a3[6]) = 1;
        *((_BYTE *)v34 + 16 * a3[6] + 8) = v58;
        if ( v55 == 2 )
        {
          if ( v58 != 1 )
          {
LABEL_36:
            v59 = 2;
            v60 = __ROR2__(v138, 8);
            *((_DWORD *)v34 + 4 * a3[5]) = 2;
            *((_WORD *)v34 + 8 * a3[5] + 4) = v60;
            v61 = __ROR2__(v136, 8);
            *((_DWORD *)v34 + 4 * a3[8]) = 2;
            *((_WORD *)v34 + 8 * a3[8] + 4) = v61;
            goto LABEL_37;
          }
        }
        else if ( v55 != 23 || v58 != 58 )
        {
          goto LABEL_36;
        }
        v59 = 2;
        v65 = v152;
        *((_DWORD *)v34 + 4 * a3[5]) = 2;
        *((_WORD *)v34 + 8 * a3[5] + 4) = *(unsigned __int8 *)(v65 + 4);
        *((_DWORD *)v34 + 4 * a3[8]) = 2;
        *((_WORD *)v34 + 8 * a3[8] + 4) = *(unsigned __int8 *)(v65 + 5);
        *((_DWORD *)v34 + 4 * a3[34]) = 2;
        *((_WORD *)v34 + 8 * a3[34] + 4) = *(unsigned __int8 *)(v65 + 4);
        v66 = *(unsigned __int8 *)(v65 + 4);
        if ( v55 == 2 )
        {
          if ( (unsigned __int8)v66 <= 0x12u )
          {
            v67 = 418049;
            if ( _bittest(&v67, v66) )
            {
              *v35 |= 0x8000000u;
              v35[50] = *(_DWORD *)v65;
            }
          }
        }
        else if ( (unsigned __int8)(v66 + 0x80) <= 1u )
        {
          *v35 |= 0x8000000u;
          v35[50] = *(_DWORD *)v65;
        }
LABEL_37:
        v62 = v144;
        *((_DWORD *)v34 + 4 * a3[4]) = 1;
        *((_BYTE *)v34 + 16 * a3[4] + 8) = a9;
        *((_DWORD *)v34 + 4 * a3[12]) = 4;
        *((_QWORD *)v34 + 2 * a3[12] + 1) = &a10;
        *((_DWORD *)v34 + 4 * a3[13]) = 3;
        *((_DWORD *)v34 + 4 * a3[13] + 2) = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v62 + 8) + 48LL) + 12LL);
        *((_DWORD *)v34 + 4 * a3[14]) = 3;
        *((_DWORD *)v34 + 4 * a3[14] + 2) = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v62 + 8) + 48LL) + 16LL);
        v63 = a20;
        *((_DWORD *)v34 + 4 * a3[11]) = 1;
        *((_BYTE *)v34 + 16 * a3[11] + 8) = v63;
        *((_DWORD *)v34 + 4 * a3[19]) = 3;
        *((_DWORD *)v34 + 4 * a3[19] + 2) = *(_DWORD *)(*(_QWORD *)(v62 + 8) + 8LL);
        ProfileIdFromInterface = v145;
        if ( v145 )
        {
          ProfileIdFromInterface = WfpGetProfileIdFromInterface(v145, v62, v62, v147, 0);
          v62 = v144;
        }
        v68 = (int)v175;
        *v175 = ProfileIdFromInterface;
        AlepFillEdgeInterfaceRelatedFields(
          v68,
          (_DWORD)a3,
          0,
          0,
          v145,
          v62,
          v147,
          0,
          a16,
          ProfileIdFromInterface,
          0,
          (__int64)v34);
        if ( *((_DWORD *)v34 + 4 * a3[31]) )
          *(_DWORD *)v177 = *((_DWORD *)v34 + 4 * a3[31] + 2);
        v69 = (unsigned __int16)v136;
        v70 = v145 + 80;
        v71 = v156;
        v72 = v135;
        *((_DWORD *)v34 + 4 * a3[35]) = 4;
        *((_QWORD *)v34 + 2 * a3[35] + 1) = v70;
        if ( WfpAleFindPeerInformationForPeerName((_DWORD)SpinLock, v72, v71, v69, (__int64)&v154) || (v73 = v154) == 0 )
        {
          v75 = 0;
        }
        else
        {
          *((_DWORD *)v34 + 4 * a3[33]) = 12;
          *((_QWORD *)v34 + 2 * a3[33] + 1) = *(_QWORD *)(v73 + 64);
          v75 = *(unsigned __int8 *)(v73 + 2);
        }
        v76 = v130;
        if ( v130 && v30 )
        {
          v77 = v30;
          while ( *(_BYTE *)(v77 + 40) )
          {
            v77 = *(_QWORD *)(v77 + 48);
            if ( !v77 )
            {
              OriginalAppId = 0;
              goto LABEL_59;
            }
          }
          OriginalAppId = AleGetOriginalAppId(v30, v73, v74, v75);
          Entry = (PVOID)OriginalAppId;
        }
        else
        {
          OriginalAppId = 0;
        }
        if ( OriginalAppId )
        {
          v168 = *(_QWORD *)(OriginalAppId + 8);
          LODWORD(v167) = *(unsigned __int16 *)(OriginalAppId + 2);
          *((_DWORD *)v34 + 4 * a3[36]) = 12;
          *((_QWORD *)v34 + 2 * a3[36] + 1) = &v167;
        }
        else
        {
LABEL_59:
          *((_DWORD *)v34 + 4 * a3[36]) = 0;
        }
        v79 = 0;
        *((_DWORD *)v34 + 4 * a3[16]) = 3;
        if ( SpinLock != (PKSPIN_LOCK)-168LL )
        {
          v79 = 2 * (SpinLock[25] & 1);
          if ( (SpinLock[25] & 0x800) != 0 )
            v79 = (2 * (SpinLock[25] & 1)) | 0x10000;
        }
        v80 = v79 | 1;
        if ( !v76 )
          v80 = v79;
        if ( (SpinLock[6] & 0x10) != 0 )
          v80 |= 0x10u;
        v81 = v80 | 0x4000;
        if ( !(_DWORD)v75 )
          v81 = v80;
        v82 = v144;
        v83 = v81 | 0x100000;
        if ( !v30 )
          v83 = v81;
        if ( OriginalAppId )
          v83 |= 0x200000u;
        *((_DWORD *)v34 + 4 * a3[16] + 2) = v83;
        *((_DWORD *)v34 + 4 * a3[40]) = 3;
        *((_DWORD *)v34 + 4 * a3[40] + 2) = ***(_DWORD ***)(v82 + 8);
        v42 = *((_DWORD *)SpinLock + 170) == 1;
        *((_QWORD *)&v172 + 1) = 0;
        v173 = 0;
        *(_QWORD *)&v172 = SpinLocka;
        if ( v42 )
          v35[1] |= 0x80000u;
        *v35 |= 0x80u;
        *((_QWORD *)v35 + 1) = &v172;
        *v35 |= 0x20u;
        v84 = a21;
        *((_QWORD *)v35 + 8) = *(_QWORD *)(SpinLock[60] + 32);
        *v35 |= 0x400u;
        v35[11] = v84;
        *v35 |= 0x800u;
        v85 = v146;
        v35[20] = ***(_DWORD ***)(v82 + 8);
        if ( FeAcquireCompletionHandle(v85, &v148) )
          v148 = FeAcquireGenericCompletionHandle();
        *v35 |= 0x4000u;
        *((_QWORD *)v35 + 13) = v148;
        if ( v30 )
        {
          *v35 |= 0x20000000u;
          *((_QWORD *)v35 + 26) = v30 + 72;
          if ( *(_DWORD *)(v30 + 464) )
          {
            *v35 |= 0x10000000u;
            v35[51] = *(_DWORD *)(v30 + 464);
          }
        }
        v86 = SpinLock[60];
        v87 = v135;
        v170 = *(_QWORD *)(v86 + 16);
        LODWORD(v169) = *(unsigned __int16 *)(v86 + 10);
        *v35 |= 8u;
        *((_QWORD *)v35 + 6) = &v169;
        *v35 |= 0x10u;
        *((_QWORD *)v35 + 7) = *(_QWORD *)(SpinLock[61] + 64);
        *v35 |= 0x40000u;
        v35[35] = 0;
        WfpAleInitializeAleEpoch(v87, SpinLock + 45);
        if ( (SpinLock[6] & 0x40) == 0 )
          _InterlockedOr((volatile signed __int32 *)SpinLock + 12, 0x40u);
        KfdGetLayerCacheEpoch(v87, &v140);
        *v35 |= 0x8000u;
        v88 = v155;
        *((_QWORD *)v35 + 14) = *(_QWORD *)v155;
        if ( *(_QWORD *)(v88 + 48) )
        {
          *v35 |= 0x4000000u;
          *((_QWORD *)v35 + 24) = *(_QWORD *)(v88 + 48);
        }
        if ( *(_DWORD *)(v88 + 8) )
        {
          *v35 |= 0x20000u;
          v35[30] = *(_DWORD *)(v88 + 8);
        }
        if ( *(_QWORD *)(v88 + 16) )
        {
          *v35 |= 0x10000u;
          *((_QWORD *)v35 + 16) = *(_QWORD *)(v88 + 16);
          v35[34] = *(_DWORD *)(v88 + 24);
        }
        if ( *(_QWORD *)(v88 + 32) )
        {
          *v35 |= 0x800000u;
          *((_QWORD *)v35 + 18) = *(_QWORD *)(v88 + 32);
          v35[38] = *(_DWORD *)(v88 + 40);
        }
        LODWORD(SpinLocka[16]) = 1;
        WORD2(SpinLocka[16]) = 256;
        SpinLocka[17] = 0;
        SpinLocka[18] = 0;
        if ( gAleDebugEnabled )
        {
          v89 = WfpPoolAllocNonPaged(80, 1919247937, &SpinLocka[19]);
          v90 = SpinLocka[19];
          if ( v89 )
            v90 = 0xBADBADFABADBADFAuLL;
          SpinLocka[19] = v90;
          if ( gAleDebugEnabled && v90 != 0xBADBADFABADBADFAuLL )
            _InterlockedIncrement((volatile signed __int32 *)(v90 + 4));
        }
        else
        {
          SpinLocka[19] = 0xBADBADFABADBADFAuLL;
        }
        *(_QWORD *)&v177 = &SpinLocka[16];
        LODWORD(SpinLocka[16]) = (LODWORD(SpinLocka[16]) + 4)
                               ^ (LOBYTE(SpinLocka[16])
                                ^ (unsigned __int8)(LOBYTE(SpinLocka[16]) + 4))
                               & 3;
        KfdAleInitializeFlowTable(&SpinLocka[9], 0);
        if ( !KfdAleAcquireFlowHandleForFlow(SpinLock, SpinLocka, &v160) )
        {
          *v35 |= 2u;
          *((_QWORD *)v35 + 4) = v160;
          if ( v30 )
            *(_QWORD *)(v30 + 504) = v160;
          KfdAleReleaseFlowHandleForFlow(SpinLock);
        }
        v91 = v150;
        *((_BYTE *)v35 + 592) = *(_BYTE *)(SpinLock[61] + 152);
        *(_OWORD *)(v35 + 150) = *(_OWORD *)(SpinLock[61] + 160);
        *((_QWORD *)v35 + 77) = *(_QWORD *)(SpinLock[61] + 176);
        *(_OWORD *)(v35 + 162) = *(_OWORD *)(SpinLock[61] + 192);
        v129 = (__int64)v164;
        *(_OWORD *)(v35 + 166) = *(_OWORD *)(SpinLock[61] + 208);
        v92 = WfpAleClassify((unsigned int)&v171, (_DWORD)v35, v91, 0, (__int64)v134, v129);
        v37 = v134[0];
        inserted = v92;
        v131 = v134[0];
        if ( v134[0] )
        {
          _InterlockedOr((volatile signed __int32 *)&SpinLocka[6], 0x8000u);
        }
        else if ( v92 )
        {
          goto LABEL_173;
        }
        v38 = 0;
        v37 = v144;
        v36 = 0;
        if ( (*((_DWORD *)SpinLock + 13) & 0x10) == 0 )
          SpinLock[59] = v144;
        if ( (unsigned int)(a20 - 3) > 1 )
        {
          v93 = 0;
          v94 = 0;
          if ( v35[84] )
            LODWORD(v36) = v35[86];
          if ( v35[76] )
            v93 = v35[78] == 1;
          if ( v35[80] )
            v94 = v35[82] == 1;
          if ( !v93 && !v94 )
          {
            inserted = WfpAleInsertRemoteEndpoint(
                         SpinLock,
                         v37,
                         v138,
                         v156,
                         v136,
                         v130,
                         v152,
                         v135,
                         v140,
                         1,
                         v147,
                         0,
                         (__int64)SpinLocka,
                         v36,
                         0,
                         1,
                         0,
                         (__int64)v35,
                         v143,
                         v159);
            if ( inserted )
              goto LABEL_173;
            goto LABEL_134;
          }
          LODWORD(v139) = 0;
          v177 = 0;
          if ( v137 == 2 )
          {
            v95 = &v139;
LABEL_126:
            v96 = 0;
            if ( !v94 )
              v96 = v136;
            inserted = WfpAleInsertRemoteEndpoint(
                         SpinLock,
                         v37,
                         v138,
                         (__int64)v95,
                         v96,
                         v130,
                         v152,
                         v135,
                         v140,
                         1,
                         v147,
                         0,
                         (__int64)SpinLocka,
                         0,
                         0,
                         1,
                         v94 + 1,
                         (__int64)v35,
                         v143,
                         v159);
            if ( inserted )
              goto LABEL_173;
            if ( (*((_DWORD *)SpinLock + 12) & 0x80u) == 0 )
              _InterlockedOr((volatile signed __int32 *)SpinLock + 12, 0x80u);
            if ( v94 && (*((_DWORD *)SpinLock + 13) & 0x40000) == 0 )
              _InterlockedOr((volatile signed __int32 *)SpinLock + 13, 0x40000u);
LABEL_134:
            inserted = WfpAleOptionalSetPeerInformation(*(_QWORD *)v143, v154);
            if ( inserted )
              goto LABEL_173;
            v38 = (PDEVICE_OBJECT *)v143;
            if ( (*(_DWORD *)(*(_QWORD *)v143 + 48LL) & 0x4000) != 0 )
            {
              if ( (*(_DWORD *)(*(_QWORD *)v143 + 48LL) & 0x8000) == 0 )
              {
                v97 = *(_QWORD *)v143;
                v98 = v146;
                v99 = (unsigned __int16)v136;
                v100 = v156;
                v101 = v137;
                *(_QWORD *)(v146 + 16) = *(_QWORD *)v143;
                *(_QWORD *)(v97 + 288) = *(_QWORD *)(v98 + 64);
                if ( !WfpAleAcquirePeerInformation(SpinLock, v101, v100, v99, v97 + 256) )
                  _InterlockedOr((volatile signed __int32 *)(v97 + 48), 0x10000u);
                v102 = WfpAllocateFromPerProcessorLookasideList(authorizeContextPPLookasideList, &v158);
                v33 = (__int128 *)v158;
                inserted = v102;
                if ( v102 )
                  goto LABEL_173;
                memset(v158, 0, 0x150u);
                v103 = v155;
                v104 = *(_DWORD *)(v155 + 24);
                if ( !v104 )
                  goto LABEL_143;
                inserted = WfpPoolAllocNonPaged(v104, 1432710209, &v161);
                P = v161;
                if ( !inserted )
                {
                  v103 = v155;
LABEL_143:
                  v105 = *(_DWORD *)(v103 + 40);
                  if ( v105 )
                  {
                    inserted = WfpPoolAllocNonPaged(v105, 1432710209, &v157);
                    if ( inserted )
                    {
                      v39 = 1;
                      v153 = v157;
                      goto LABEL_24;
                    }
                    v106 = v157;
                    v103 = v155;
                  }
                  else
                  {
                    v106 = v153;
                  }
                  v107 = (__int128 *)v146;
                  v108 = v33;
                  do
                  {
                    v108 += 8;
                    v109 = *v107;
                    v107 += 8;
                    *(v108 - 8) = v109;
                    *(v108 - 7) = *(v107 - 7);
                    *(v108 - 6) = *(v107 - 6);
                    *(v108 - 5) = *(v107 - 5);
                    *(v108 - 4) = *(v107 - 4);
                    *(v108 - 3) = *(v107 - 3);
                    *(v108 - 2) = *(v107 - 2);
                    *(v108 - 1) = *(v107 - 1);
                    --v59;
                  }
                  while ( v59 );
                  *v108 = *v107;
                  v108[1] = v107[1];
                  v108[2] = v107[2];
                  v108[3] = v107[3];
                  v108[4] = v107[4];
                  *((_QWORD *)v33 + 35) = v150;
                  *((_QWORD *)v33 + 36) = P;
                  *((_DWORD *)v33 + 74) = *(_DWORD *)(v103 + 24);
                  *((_QWORD *)v33 + 38) = v106;
                  *((_DWORD *)v33 + 78) = *(_DWORD *)(v103 + 40);
                  v110 = *((_QWORD *)v33 + 35);
                  v153 = 0;
                  P = 0;
                  NetioReferenceNetBufferList(v110);
                  inserted = WfpAleSecureSocketAdd(
                               v97,
                               *(unsigned __int16 *)(v97 + 60),
                               (unsigned int)WfpAlepAuthorizeSendSecureCompletion,
                               (_DWORD)v33,
                               v156);
                  if ( inserted )
                    goto LABEL_173;
                  v38 = (PDEVICE_OBJECT *)v143;
                  v33 = 0;
                  _InterlockedOr((volatile signed __int32 *)(*(_QWORD *)v143 + 48LL), 0x8000u);
                  v131 = 1;
                  *(_BYTE *)(v146 + 81) = 1;
                  *(_BYTE *)v178 = 1;
                  _InterlockedOr((volatile signed __int32 *)&(*v38)->Flags, 0x100000u);
                  goto LABEL_170;
                }
LABEL_173:
                v39 = 1;
                goto LABEL_24;
              }
            }
            else if ( !v131 )
            {
              v36 = v146;
              v111 = *(_QWORD *)v143;
              _InterlockedIncrement(*(volatile signed __int32 **)(v146 + 48));
              v112 = *(volatile signed __int32 **)(v36 + 64);
              *(_QWORD *)(v111 + 288) = v112;
              _InterlockedIncrement(v112);
            }
            _InterlockedOr((volatile signed __int32 *)&(*v38)->Flags, 0x100000u);
LABEL_170:
            if ( *(_QWORD *)v143 && Entry )
              _InterlockedOr((volatile signed __int32 *)(*(_QWORD *)v143 + 52LL), 0x10000u);
            goto LABEL_173;
          }
          if ( v137 == 23 )
          {
            v95 = (__int64 *)&v177;
            goto LABEL_126;
          }
LABEL_174:
          __fastfail(5u);
        }
        v113 = v35[72];
        if ( v113 && (v113 != 3 || v35[74] == 1) )
          goto LABEL_170;
        LODWORD(v139) = 0;
        v178 = 0;
        v150 = *(_QWORD *)v152;
        if ( v137 == 2 )
        {
          v114 = &v139;
        }
        else
        {
          if ( v137 != 23 )
            goto LABEL_174;
          v114 = (__int64 *)&v178;
        }
        v115 = 2;
        if ( v35[88] )
          LODWORD(v36) = v35[90];
        if ( v113 )
        {
          v115 = 2;
          if ( v35[74] == 2 )
            v115 = 10;
        }
        LODWORD(v150) = 0;
        inserted = WfpAleInsertRemoteEndpoint(
                     SpinLock,
                     v144,
                     v138,
                     (__int64)v114,
                     0,
                     v130,
                     (__int64)&v150,
                     v87,
                     v140,
                     1,
                     v147,
                     0,
                     (__int64)SpinLocka,
                     v36,
                     0,
                     v115,
                     0,
                     (__int64)v35,
                     v143,
                     v159);
        if ( inserted )
          goto LABEL_173;
        if ( (*((_DWORD *)SpinLock + 12) & 0x80u) == 0 )
          _InterlockedOr((volatile signed __int32 *)SpinLock + 12, 0x80u);
        goto LABEL_170;
      }
      v47 = (char *)gIncomingValuesLookasideList
          + 128 * (unsigned __int64)(unsigned int)(HIDWORD(KeGetPcr()[1].LockArray) + 1);
      if ( !v47[176] )
        PplpLazyInitializeLookasideList(gIncomingValuesLookasideList, v47 + 64, v45, v46);
      ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v47 + 64), Entry);
    }
    v39 = 0;
    v35 = 0;
    if ( v132 )
      WfpLowerIrqlFromDispatchLevel(v133);
    v40 = WPP_GLOBAL_Control;
    v42 = WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control;
    inserted = -1073741670;
    goto LABEL_20;
  }
  v39 = 0;
  *v164 = 4097;
  v40 = WPP_GLOBAL_Control;
  inserted = -1073741790;
  v42 = WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control;
LABEL_20:
  if ( !v42 && BYTE1(v40->Timer) >= 2u && (HIDWORD(v40->Timer) & 0x1000) != 0 )
    WPP_SF_sd(
      v40->AttachedDevice,
      10,
      (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
      (unsigned int)"WfpAlepAuthorizeSend",
      inserted);
LABEL_24:
  if ( v148 )
  {
    FeReleaseCompletionHandle(v148, v38);
    v148 = 0;
  }
  if ( Size[1] )
  {
    ExFreePoolWithTag((PVOID)Size[1], 0);
    Size[1] = 0;
    LODWORD(Size[0]) = 0;
  }
  if ( v33 )
  {
    v116 = *((_QWORD *)v33 + 35);
    if ( v116 )
      NetioDereferenceNetBufferList(v116, 0);
    v117 = (void *)*((_QWORD *)v33 + 36);
    if ( v117 )
    {
      ExFreePoolWithTag(v117, 0);
      *((_QWORD *)v33 + 36) = 0xBADBADFABADBADFAuLL;
    }
    v118 = (void *)*((_QWORD *)v33 + 38);
    if ( v118 )
    {
      ExFreePoolWithTag(v118, 0);
      *((_QWORD *)v33 + 38) = 0xBADBADFABADBADFAuLL;
    }
    v119 = (char *)authorizeContextPPLookasideList
         + 128 * (unsigned __int64)(unsigned int)(HIDWORD(KeGetPcr()[1].LockArray) + 1);
    if ( !v119[176] )
      PplpLazyInitializeLookasideList(authorizeContextPPLookasideList, v119 + 64, v36, v37);
    ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v119 + 64), v33);
  }
  if ( P )
    ExFreePoolWithTag(P, 0);
  if ( v153 )
    ExFreePoolWithTag(v153, 0);
  if ( v154 )
  {
    if ( *((_DWORD *)SpinLock + 10) != 6 || (SpinLock[6] & 0x10) != 0 )
    {
      WfpAleReleasePeerInformation();
    }
    else if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v154 + 24), 0xFFFFFFFF) == 1 )
    {
      WfpAlepFreePeerInformation();
    }
  }
  if ( SpinLocka[31] )
    WfpAlepFreePeerTokenInformation(&SpinLocka[31]);
  if ( SpinLocka[12] )
    KfdAleNotifyFlowDeletion(&SpinLocka[9]);
  if ( v131 )
    inserted = 259;
  if ( v39 )
  {
    LockArray_high = HIDWORD(KeGetPcr()[1].LockArray);
    v121 = (PVOID *)((char *)gPerProcessorContext + 72 * LockArray_high);
    KfdReleaseTerminatingFilters(v35 + 156, 9 * LockArray_high, v36);
    if ( v34 == v121[3] )
    {
      *((_BYTE *)v121 + 32) = 0;
    }
    else
    {
      v124 = (char *)gMetadataLookasideList
           + 128 * (unsigned __int64)(unsigned int)(HIDWORD(KeGetPcr()[1].LockArray) + 1);
      if ( !v124[176] )
        PplpLazyInitializeLookasideList(gMetadataLookasideList, v124 + 64, v122, v123);
      ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v124 + 64), v35);
      v127 = (char *)gIncomingValuesLookasideList
           + 128 * (unsigned __int64)(unsigned int)(HIDWORD(KeGetPcr()[1].LockArray) + 1);
      if ( !v127[176] )
        PplpLazyInitializeLookasideList(gIncomingValuesLookasideList, v127 + 64, v125, v126);
      ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v127 + 64), v34);
    }
    if ( v132 )
      WfpLowerIrqlFromDispatchLevel(v133);
  }
  if ( inserted
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
  {
    WPP_SF_sd(
      WPP_GLOBAL_Control->AttachedDevice,
      15,
      (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
      (unsigned int)"WfpAlepAuthorizeSend",
      inserted);
  }
  return inserted;
}

```

## disassembly

```asm
0x14013fc30  push    rbp
0x14013fc32  push    rbx
0x14013fc33  push    rsi
0x14013fc34  push    rdi
0x14013fc35  push    r12
0x14013fc37  push    r13
0x14013fc39  push    r14
0x14013fc3b  push    r15
0x14013fc3d  lea     rbp, [rsp-2D8h]
0x14013fc45  sub     rsp, 418h
0x14013fc4c  mov     rax, cs:__security_cookie
0x14013fc53  xor     rax, rsp
0x14013fc56  mov     [rbp+310h+var_50], rax
0x14013fc5d  movzx   eax, [rbp+310h+arg_60]
0x14013fc64  xorps   xmm0, xmm0
0x14013fc67  mov     rdi, [rbp+310h+arg_88]
0x14013fc6e  mov     r14, r8
0x14013fc71  mov     r8d, [rbp+310h+arg_20]
0x14013fc78  mov     r15, rcx
0x14013fc7b  mov     r12, [rbp+310h+arg_C8]
0x14013fc82  lea     rcx, [rbp+310h+SpinLock]; void *
0x14013fc89  mov     [rbp+310h+var_388], ax
0x14013fc8d  xor     r13d, r13d
0x14013fc90  mov     rax, [rbp+310h+arg_B8]
0x14013fc97  xor     esi, esi
0x14013fc99  mov     [rbp+310h+var_300], rax
0x14013fc9d  xor     ebx, ebx
0x14013fc9f  mov     rax, [rbp+310h+arg_68]
0x14013fca6  mov     [rbp+310h+var_318], rax
0x14013fcaa  mov     rax, [rbp+310h+arg_C0]
0x14013fcb1  mov     [rbp+310h+var_2B8], rax
0x14013fcb5  movzx   eax, [rbp+310h+arg_38]
0x14013fcbc  mov     [rbp+310h+var_384], ax
0x14013fcc0  mov     rax, [rbp+310h+arg_50]
0x14013fcc7  mov     [rbp+310h+var_2F8], rax
0x14013fccb  mov     rax, [rbp+310h+arg_70]
0x14013fcd2  mov     [rbp+310h+var_358], rax
0x14013fcd6  movzx   eax, [rbp+310h+arg_80]
0x14013fcdd  mov     [rbp+310h+var_390], al
0x14013fce0  mov     rax, [rbp+310h+arg_90]
0x14013fce7  mov     [rbp+310h+var_350], rax
0x14013fceb  mov     rax, [rbp+310h+arg_A8]
0x14013fcf2  mov     [rbp+310h+var_348], rax
0x14013fcf6  mov     rax, [rbp+310h+arg_B0]
0x14013fcfd  mov     [rbp+310h+var_330], rax
0x14013fd01  mov     rax, [rbp+310h+arg_D0]
0x14013fd08  mov     [rbp+310h+var_2E0], rax
0x14013fd0c  mov     rax, [rbp+310h+arg_D8]
0x14013fd13  mov     qword ptr [rbp+310h+var_60], rax
0x14013fd1a  mov     rax, [rbp+310h+arg_E0]
0x14013fd21  mov     [rbp+310h+var_250], rax
0x14013fd28  mov     rax, [rbp+310h+arg_E8]
0x14013fd2f  mov     [rbp+310h+var_38A], dx
0x14013fd33  mov     rdx, [rbp+310h+arg_28]
0x14013fd3a  mov     qword ptr [rbp+310h+var_70], rax
0x14013fd41  xor     eax, eax
0x14013fd43  mov     [rbp+310h+var_374], r8d
0x14013fd47  mov     r8d, 1D8h; Size
0x14013fd4d  mov     [rbp+310h+var_360], rdx
0x14013fd51  xor     edx, edx; Val
0x14013fd53  mov     qword ptr [rbp+310h+var_2AC], rax
0x14013fd57  mov     qword ptr [rbp+310h+var_29C], rax
0x14013fd5b  mov     qword ptr [rbp+310h+var_2C4], rax
0x14013fd5f  mov     qword ptr [rbp+310h+var_28C], rax
0x14013fd66  mov     [rbp+60h], rax
0x14013fd6a  mov     [rbp+70h], rax
0x14013fd6e  mov     [rbp+48h], rax
0x14013fd72  mov     [rbp+80h], rax
0x14013fd79  mov     [rbp+310h+var_386], r9w
0x14013fd7e  mov     [rbp+310h+var_258], rdi
0x14013fd85  mov     [rbp+310h+var_368], r12
0x14013fd89  mov     [rbp+310h+var_378], 0
0x14013fd90  mov     [rbp+310h+var_2E8], r13
0x14013fd94  mov     [rbp+310h+Entry], rsi
0x14013fd98  movups  [rbp+310h+var_270], xmm0
0x14013fd9f  mov     [rbp+310h+var_260], rax
0x14013fda6  mov     [rbp+310h+var_38F], al
0x14013fda9  mov     [rbp+310h+var_38C], al
0x14013fdac  movups  xmmword ptr [rbp+310h+Size], xmm0
0x14013fdb0  mov     [rbp+310h+var_380], rbx
0x14013fdb4  movups  [rbp+310h+var_280], xmm0
0x14013fdbb  mov     [rbp+310h+var_38D], al
0x14013fdbe  mov     [rbp+310h+var_38E], al
0x14013fdc1  call    memset
0x14013fdc6  xor     ecx, ecx
0x14013fdc8  lea     rdx, WPP_GLOBAL_Control
0x14013fdcf  mov     [rbp+310h+var_308], rcx
0x14013fdd3  mov     [rbp+310h+var_2D8], rcx
0x14013fdd7  mov     [rbp+310h+P], rcx
0x14013fddb  mov     [rbp+310h+var_2D0], rcx
0x14013fddf  mov     [rbp+310h+var_310], rcx
0x14013fde3  mov     [rbp+310h+var_2F0], rcx
0x14013fde7  mov     [rbp+310h+var_340], rcx
0x14013fdeb  mov     [r12], rcx
0x14013fdef  cmp     [rbp+310h+var_390], cl
0x14013fdf2  jz      short loc_14013FE2D
0x14013fdf4  test    rdi, rdi
0x14013fdf7  jz      short loc_14013FE2D
0x14013fdf9  cmp     [rdi+1D0h], ecx
0x14013fdff  jz      short loc_14013FE0A
0x14013fe01  cmp     [rdi+1D8h], rcx
0x14013fe08  jnz     short loc_14013FE2D
0x14013fe0a  mov     rax, [rbp+310h+var_2B8]
0x14013fe0e  xor     r12b, r12b
0x14013fe11  mov     dword ptr [rax], 1001h
0x14013fe17  mov     rcx, cs:WPP_GLOBAL_Control
0x14013fe1e  mov     rdi, 0FFFFFFFFC0000022h
0x14013fe25  cmp     rcx, rdx
0x14013fe28  jmp     loc_14013FF48
0x14013fe2d  lea     rcx, [rbp+310h+SpinLock]; SpinLock
0x14013fe34  call    cs:__imp_KeInitializeSpinLock
0x14013fe3b  nop     dword ptr [rax+rax+00h]
0x14013fe40  mov     eax, [r15+30h]
0x14013fe44  xorps   xmm0, xmm0
0x14013fe47  mov     [rbp+310h+var_240], ebx
0x14013fe4d  movdqu  [rbp+310h+var_238], xmm0
0x14013fe55  test    al, 10h
0x14013fe57  jz      short loc_14013FE61
0x14013fe59  lock or [rbp+310h+var_218], 10h
0x14013fe61  call    cs:__imp_KeGetCurrentIrql
0x14013fe68  nop     dword ptr [rax+rax+00h]
0x14013fe6d  cmp     al, 2
0x14013fe6f  jnb     short loc_14013FE7D
0x14013fe71  call    WfpRaiseIrqlToDispatchLevel
0x14013fe76  mov     [rbp+310h+var_38D], al
0x14013fe79  mov     [rbp+310h+var_38E], 1
0x14013fe7d  mov     ecx, gs:1A4h
0x14013fe85  lea     r8, [rcx+rcx*8]
0x14013fe89  mov     rcx, cs:gPerProcessorContext
0x14013fe90  cmp     [rcx+r8*8+20h], bl
0x14013fe95  jnz     short loc_14013FEAC
0x14013fe97  mov     rsi, [rcx+r8*8+18h]
0x14013fe9c  mov     rbx, [rcx+r8*8+10h]
0x14013fea1  mov     byte ptr [rcx+r8*8+20h], 1
0x14013fea7  jmp     loc_14013FFA6
0x14013feac  mov     rcx, cs:gIncomingValuesLookasideList
0x14013feb3  lea     rdx, [rbp+310h+Entry]
0x14013feb7  call    WfpAllocateFromPerProcessorLookasideList
0x14013febc  test    rax, rax
0x14013febf  jnz     short loc_14013FF1B
0x14013fec1  mov     rcx, cs:gMetadataLookasideList
0x14013fec8  lea     rdx, [rbp+310h+var_380]
0x14013fecc  call    WfpAllocateFromPerProcessorLookasideList
0x14013fed1  test    rax, rax
0x14013fed4  jz      loc_14013FF9E
0x14013feda  mov     eax, gs:1A4h
0x14013fee2  mov     rcx, cs:gIncomingValuesLookasideList
0x14013fee9  lea     ebx, [rax+1]
0x14013feec  shl     rbx, 7
0x14013fef0  add     rbx, rcx
0x14013fef3  movzx   eax, byte ptr [rbx+0B0h]
0x14013fefa  test    al, al
0x14013fefc  jnz     short loc_14013FF07
0x14013fefe  lea     rdx, [rbx+40h]
0x14013ff02  call    PplpLazyInitializeLookasideList
0x14013ff07  mov     rdx, [rbp+310h+Entry]; Entry
0x14013ff0b  lea     rcx, [rbx+40h]; Lookaside
0x14013ff0f  call    cs:__imp_ExFreeToLookasideListEx
0x14013ff16  nop     dword ptr [rax+rax+00h]
0x14013ff1b  xor     r12b, r12b
0x14013ff1e  mov     rbx, rsi
0x14013ff21  cmp     [rbp+310h+var_38E], r13b
0x14013ff25  jz      short loc_14013FF30
0x14013ff27  movzx   ecx, [rbp+310h+var_38D]
0x14013ff2b  call    WfpLowerIrqlFromDispatchLevel
0x14013ff30  mov     rcx, cs:WPP_GLOBAL_Control
0x14013ff37  lea     rax, WPP_GLOBAL_Control
0x14013ff3e  cmp     rcx, rax
0x14013ff41  mov     rdi, 0FFFFFFFFC000009Ah
0x14013ff48  jz      short loc_14013FF79
0x14013ff4a  cmp     byte ptr [rcx+29h], 2
0x14013ff4e  jb      short loc_14013FF79
0x14013ff50  test    dword ptr [rcx+2Ch], 1000h
0x14013ff57  jz      short loc_14013FF79
0x14013ff59  mov     rcx, [rcx+18h]
0x14013ff5d  lea     r9, aWfpalepauthori_2; "WfpAlepAuthorizeSend"
0x14013ff64  lea     r8, WPP_dc97c17fd6903ad537f842808d057dba_Traceguids
0x14013ff6b  mov     dword ptr [rsp+450h+var_430], edi
0x14013ff6f  mov     edx, 0Ah
0x14013ff74  call    WPP_SF_sd
0x14013ff79  mov     rcx, [rbp+310h+var_340]
0x14013ff7d  test    rcx, rcx
0x14013ff80  jz      loc_140141023
0x14013ff86  call    cs:__imp_FeReleaseCompletionHandle
0x14013ff8d  nop     dword ptr [rax+rax+00h]
0x14013ff92  xor     r14d, r14d
0x14013ff95  mov     [rbp+310h+var_340], r14
0x14013ff99  jmp     loc_140141026
0x14013ff9e  mov     rsi, [rbp+310h+Entry]
0x14013ffa2  mov     rbx, [rbp+310h+var_380]
0x14013ffa6  xor     edx, edx; Val
0x14013ffa8  mov     r8d, 2A0h; Size
0x14013ffae  mov     rcx, rsi; void *
0x14013ffb1  call    memset
0x14013ffb6  xor     edx, edx; Val
0x14013ffb8  mov     r8d, 2A8h; Size
0x14013ffbe  mov     rcx, rbx; void *
0x14013ffc1  call    memset
0x14013ffc6  lea     rax, [rbx+270h]
0x14013ffcd  mov     [rax+8], rax
0x14013ffd1  mov     [rax], rax
0x14013ffd4  mov     rcx, [r15+1E0h]
0x14013ffdb  movzx   eax, [rbp+310h+var_38A]
0x14013ffdf  mov     word ptr [rbp+310h+var_280], ax
0x14013ffe6  movzx   eax, word ptr [r14]
0x14013ffea  mov     dword ptr [rbp+310h+var_280+4], eax
0x14013fff0  mov     qword ptr [rbp+310h+var_280+8], rsi
0x14013fff7  mov     rax, [rcx+10h]
0x14013fffb  mov     qword ptr [rbp+310h+var_2AC+4], rax
0x14013ffff  movzx   eax, word ptr [rcx+0Ah]
0x140140003  lea     rcx, [rbp+310h+var_2B0]
0x140140007  mov     [rbp+310h+var_2B0], eax
0x14014000a  movzx   eax, word ptr [r14+2]
0x14014000f  add     rax, rax
0x140140012  mov     dword ptr [rsi+rax*8], 0Ch
0x140140019  movzx   eax, word ptr [r14+2]
0x14014001e  add     rax, rax
0x140140021  mov     [rsi+rax*8+8], rcx
0x140140026  mov     rcx, [r15+1E8h]
0x14014002d  lea     rax, [rcx+0E0h]
0x140140034  mov     qword ptr [rbp+310h+var_2C4+4], rax
0x140140038  mov     eax, [rcx+48h]
0x14014003b  lea     rcx, [rbp+310h+var_2C8]
0x14014003f  mov     [rbp+310h+var_2C8], eax
0x140140042  movzx   eax, word ptr [r14+4]
0x140140047  add     rax, rax
0x14014004a  mov     dword ptr [rsi+rax*8], 10h
0x140140051  movzx   eax, word ptr [r14+4]
0x140140056  add     rax, rax
0x140140059  mov     [rsi+rax*8+8], rcx
0x14014005e  mov     rax, [r15+1E8h]
0x140140065  mov     rcx, [rax+118h]
0x14014006c  test    rcx, rcx
0x14014006f  jnz     short loc_14014007A
0x140140071  lea     rcx, gAleNullSid
0x140140078  jmp     short loc_140140091
0x14014007a  test    dword ptr [rax+10Ch], 4000h
0x140140084  jz      short loc_140140091
0x140140086  lock or [rbp+310h+var_218], 2000000h
0x140140091  movzx   eax, word ptr [r14+52h]
0x140140096  lea     rdx, [rbp+310h+var_2C8]
0x14014009a  add     rax, rax
0x14014009d  mov     dword ptr [rsi+rax*8], 10h
0x1401400a4  movzx   eax, word ptr [r14+52h]
0x1401400a9  add     rax, rax
0x1401400ac  mov     [rsi+rax*8+8], rdx
0x1401400b1  mov     [rbx+230h], r15
0x1401400b8  movzx   eax, word ptr [r14+4Ah]
0x1401400bd  add     rax, rax
0x1401400c0  mov     dword ptr [rsi+rax*8], 0Dh
0x1401400c7  movzx   eax, word ptr [r14+4Ah]
0x1401400cc  add     rax, rax
0x1401400cf  mov     [rsi+rax*8+8], rcx
0x1401400d4  mov     rax, [r15+1E8h]
0x1401400db  mov     rax, [rax+90h]
0x1401400e2  test    rax, rax
0x1401400e5  jz      short loc_140140159
0x1401400e7  mov     rax, [rax+8]
0x1401400eb  lea     r8, [rbp+310h+Size+8]
0x1401400ef  mov     edx, 63716641h
0x1401400f4  mov     r12, [rax+20h]
0x1401400f8  movzx   eax, word ptr [r12+8]
0x1401400fe  add     ax, 2
0x140140102  movzx   eax, ax
0x140140105  mov     dword ptr [rbp+310h+var_380], eax
0x140140108  add     eax, 8
0x14014010b  mov     ecx, eax
0x14014010d  mov     dword ptr [rbp+310h+Size], eax
0x140140110  call    WfpPoolAllocNonPaged
0x140140115  mov     rdi, rax
0x140140118  test    rax, rax
0x14014011b  jnz     loc_140141014
0x140140121  mov     r8d, dword ptr [rbp+310h+Size]; Size
0x140140125  xor     edx, edx; Val
0x140140127  mov     rcx, [rbp+310h+Size+8]; void *
0x14014012b  call    memset
0x140140130  mov     rcx, [r12]
0x140140134  mov     rax, [rbp+310h+Size+8]
0x140140138  movzx   r8d, word ptr [rbp+310h+var_380]; Size
0x14014013d  mov     [rax], rcx
0x140140140  mov     rcx, [rbp+310h+Size+8]
0x140140144  mov     rdx, [r12+10h]; Src
0x140140149  add     rcx, 8; void *
0x14014014d  call    memmove
0x140140152  mov     rdi, [rbp+310h+var_258]
0x140140159  movzx   eax, word ptr [r14+4Ch]
0x14014015e  xor     ecx, ecx
0x140140160  movzx   edx, [rbp+310h+var_386]
0x140140164  add     rax, rax
0x140140167  mov     [rbp+310h+Entry], rcx
0x14014016b  mov     r9d, 1
0x140140171  lea     rcx, [rbp+310h+Size]
0x140140175  mov     dword ptr [rsi+rax*8], 0Ch
0x14014017c  movzx   eax, word ptr [r14+4Ch]
0x140140181  add     rax, rax
0x140140184  mov     [rsi+rax*8+8], rcx
0x140140189  movzx   ecx, word ptr [r14+6]
0x14014018e  mov     rax, [rbp+310h+arg_30]
0x140140195  add     rcx, rcx
0x140140198  movups  xmm0, xmmword ptr [rax]
  ... truncated ...
```
