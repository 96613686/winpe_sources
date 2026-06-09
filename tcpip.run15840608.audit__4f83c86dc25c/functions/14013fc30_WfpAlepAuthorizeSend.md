# WfpAlepAuthorizeSend

- ea: `0x14013fc30`
- end: `0x1401412eb`
- name: `WfpAlepAuthorizeSend`
- size: `5819`
- prototype: `__int64 __usercall@<rax>(PKSPIN_LOCK SpinLock@<rcx>, int, __int64, __int64, __int16, char, char, __int64, __int64, __int16, __int64, __int64, int, char, __int64, __int64, int, int, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64)`
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
  PDEVICE_OBJECT *v36; // rdx
  char v37; // r12
  PDEVICE_OBJECT v38; // rcx
  __int64 inserted; // rdi
  bool v40; // zf
  int v41; // eax
  __int64 v42; // rcx
  char *v43; // rbx
  KSPIN_LOCK v44; // rcx
  KSPIN_LOCK v45; // rcx
  KSPIN_LOCK v46; // rax
  __int64 *v47; // rcx
  __int64 v48; // rax
  __int64 v49; // r12
  size_t v50; // r8
  unsigned __int16 v51; // dx
  __int64 v52; // rax
  _OWORD *v53; // rax
  int v54; // ecx
  __int64 v55; // r12
  __int16 v56; // cx
  __int16 v57; // cx
  __int64 v58; // rdx
  char v59; // cl
  int ProfileIdFromInterface; // eax
  __int64 v61; // r8
  unsigned int v62; // eax
  int v63; // ecx
  int v64; // ecx
  int v65; // r9d
  __int64 v66; // rcx
  int v67; // r8d
  int v68; // edx
  __int64 v69; // rdx
  __int64 v70; // r8
  __int64 v71; // r9
  char v72; // r11
  __int64 v73; // rax
  __int64 OriginalAppId; // r10
  int v75; // r8d
  int v76; // edx
  int v77; // eax
  __int64 v78; // rdx
  int v79; // ecx
  int v80; // eax
  __int64 v81; // rcx
  KSPIN_LOCK v82; // rcx
  unsigned __int16 v83; // r14
  __int64 v84; // rcx
  __int64 v85; // rax
  KSPIN_LOCK v86; // rcx
  int v87; // r8d
  __int64 v88; // rax
  __int64 v89; // r9
  unsigned int v90; // r8d
  bool v91; // al
  bool v92; // r14
  __int64 *v93; // rdx
  __int16 v94; // cx
  __int64 v95; // r14
  __int64 v96; // rax
  __int64 v97; // r9
  __int64 v98; // r8
  __int64 v99; // rdx
  __int64 v100; // rax
  __int64 v101; // rdx
  unsigned int v102; // eax
  unsigned int v103; // eax
  PVOID v104; // r8
  __int128 *v105; // rcx
  __int128 *v106; // rax
  __int128 v107; // xmm0
  __int64 v108; // rcx
  __int64 v109; // r8
  __int64 v110; // rcx
  volatile signed __int32 *v111; // rax
  int v112; // ecx
  __int64 *v113; // r9
  char v114; // al
  __int64 v115; // rcx
  void *v116; // rcx
  void *v117; // rcx
  char *v118; // r14
  PVOID *v119; // r14
  char *v120; // r14
  char *v121; // rbx
  __int64 v123; // [rsp+28h] [rbp-118h]
  char v124; // [rsp+C0h] [rbp-80h]
  char v125; // [rsp+C1h] [rbp-7Fh]
  char v126; // [rsp+C2h] [rbp-7Eh]
  unsigned __int8 v127; // [rsp+C3h] [rbp-7Dh]
  char v128[2]; // [rsp+C4h] [rbp-7Ch] BYREF
  unsigned __int16 v129; // [rsp+C6h] [rbp-7Ah]
  __int16 v130; // [rsp+C8h] [rbp-78h]
  unsigned __int16 v131; // [rsp+CAh] [rbp-76h]
  __int16 v132; // [rsp+CCh] [rbp-74h]
  __int64 v133; // [rsp+D0h] [rbp-70h] BYREF
  int v134; // [rsp+D8h] [rbp-68h] BYREF
  int v135; // [rsp+DCh] [rbp-64h]
  PVOID Entry; // [rsp+E0h] [rbp-60h] BYREF
  __int64 v137; // [rsp+E8h] [rbp-58h]
  __int64 v138; // [rsp+F0h] [rbp-50h]
  __int64 v139; // [rsp+F8h] [rbp-48h]
  __int64 v140; // [rsp+100h] [rbp-40h]
  __int64 v141; // [rsp+108h] [rbp-38h]
  __int64 v142; // [rsp+110h] [rbp-30h] BYREF
  PVOID P; // [rsp+118h] [rbp-28h]
  __int64 v144; // [rsp+120h] [rbp-20h] BYREF
  size_t Size[2]; // [rsp+128h] [rbp-18h] BYREF
  __int64 v146; // [rsp+138h] [rbp-8h]
  PVOID v147; // [rsp+140h] [rbp+0h]
  __int64 v148; // [rsp+148h] [rbp+8h] BYREF
  __int64 v149; // [rsp+150h] [rbp+10h]
  __int64 v150; // [rsp+158h] [rbp+18h]
  void *v151; // [rsp+160h] [rbp+20h] BYREF
  void *v152; // [rsp+168h] [rbp+28h] BYREF
  __int64 v153; // [rsp+170h] [rbp+30h]
  __int64 v154; // [rsp+178h] [rbp+38h] BYREF
  void *v155; // [rsp+180h] [rbp+40h] BYREF
  __int64 v156; // [rsp+188h] [rbp+48h] BYREF
  KSPIN_LOCK v157; // [rsp+190h] [rbp+50h]
  _DWORD *v158; // [rsp+198h] [rbp+58h]
  __int64 v159; // [rsp+1A0h] [rbp+60h] BYREF
  __int64 v160; // [rsp+1A8h] [rbp+68h]
  __int64 v161; // [rsp+1B0h] [rbp+70h] BYREF
  __int64 v162; // [rsp+1B8h] [rbp+78h]
  __int64 v163; // [rsp+1C0h] [rbp+80h] BYREF
  __int64 v164; // [rsp+1C8h] [rbp+88h]
  __int128 v165; // [rsp+1D0h] [rbp+90h] BYREF
  __int128 v166; // [rsp+1E0h] [rbp+A0h] BYREF
  __int64 v167; // [rsp+1F0h] [rbp+B0h]
  __int64 v168; // [rsp+1F8h] [rbp+B8h]
  _DWORD *v169; // [rsp+200h] [rbp+C0h]
  KSPIN_LOCK SpinLocka[59]; // [rsp+208h] [rbp+C8h] BYREF
  __int128 v171; // [rsp+3E0h] [rbp+2A0h] BYREF
  __int128 v172; // [rsp+3F0h] [rbp+2B0h] BYREF

  v30 = a18;
  v130 = a13;
  v33 = 0;
  v34 = 0;
  v149 = a24;
  v35 = 0;
  v146 = a14;
  v158 = a25;
  v132 = a8;
  v150 = a11;
  v139 = a15;
  v124 = a17;
  v140 = a19;
  v141 = a22;
  v144 = a23;
  v153 = a27;
  *(_QWORD *)&v172 = a28;
  v169 = a29;
  v129 = a2;
  *(_QWORD *)&v171 = a30;
  v135 = a5;
  v138 = a6;
  LODWORD(v160) = 0;
  LODWORD(v162) = 0;
  LODWORD(v157) = 0;
  LODWORD(v164) = 0;
  v159 = 0;
  v161 = 0;
  v156 = 0;
  v163 = 0;
  v131 = a4;
  v168 = a18;
  v137 = (__int64)a26;
  v134 = 0;
  v152 = 0;
  Entry = 0;
  v166 = 0;
  v167 = 0;
  v125 = 0;
  v128[0] = 0;
  *(_OWORD *)Size = 0;
  v133 = 0;
  v165 = 0;
  v127 = 0;
  v126 = 0;
  memset(SpinLocka, 0, sizeof(SpinLocka));
  v36 = &WPP_GLOBAL_Control;
  v148 = 0;
  v154 = 0;
  P = 0;
  v155 = 0;
  v147 = 0;
  v151 = 0;
  v142 = 0;
  *a26 = 0;
  if ( !v124 || !v30 || *(_DWORD *)(v30 + 464) && *(_QWORD *)(v30 + 472) )
  {
    KeInitializeSpinLock(SpinLocka);
    v41 = *((_DWORD *)SpinLock + 12);
    LODWORD(SpinLocka[1]) = 0;
    *(_OWORD *)&SpinLocka[2] = 0;
    if ( (v41 & 0x10) != 0 )
      _InterlockedOr((volatile signed __int32 *)&SpinLocka[6], 0x10u);
    if ( KeGetCurrentIrql() < 2u )
    {
      v127 = WfpRaiseIrqlToDispatchLevel();
      v126 = 1;
    }
    LODWORD(v42) = HIDWORD(KeGetPcr()[1].LockArray);
    if ( !*((_BYTE *)gPerProcessorContext + 72 * v42 + 32) )
    {
      v34 = (PVOID)*((_QWORD *)gPerProcessorContext + 9 * v42 + 3);
      v35 = (_DWORD *)*((_QWORD *)gPerProcessorContext + 9 * v42 + 2);
      *((_BYTE *)gPerProcessorContext + 72 * v42 + 32) = 1;
      goto LABEL_27;
    }
    if ( !WfpAllocateFromPerProcessorLookasideList(gIncomingValuesLookasideList, &Entry) )
    {
      if ( !WfpAllocateFromPerProcessorLookasideList(gMetadataLookasideList, &v133) )
      {
        v34 = Entry;
        v35 = (_DWORD *)v133;
LABEL_27:
        memset(v34, 0, 0x2A0u);
        memset(v35, 0, 0x2A8u);
        *((_QWORD *)v35 + 79) = v35 + 156;
        *((_QWORD *)v35 + 78) = v35 + 156;
        v44 = SpinLock[60];
        LOWORD(v165) = v129;
        DWORD1(v165) = *a3;
        *((_QWORD *)&v165 + 1) = v34;
        v160 = *(_QWORD *)(v44 + 16);
        LODWORD(v159) = *(unsigned __int16 *)(v44 + 10);
        *((_DWORD *)v34 + 4 * a3[1]) = 12;
        *((_QWORD *)v34 + 2 * a3[1] + 1) = &v159;
        v45 = SpinLock[61];
        v157 = v45 + 224;
        LODWORD(v156) = *(_DWORD *)(v45 + 72);
        *((_DWORD *)v34 + 4 * a3[2]) = 16;
        *((_QWORD *)v34 + 2 * a3[2] + 1) = &v156;
        v46 = SpinLock[61];
        v47 = *(__int64 **)(v46 + 280);
        if ( v47 )
        {
          if ( (*(_DWORD *)(v46 + 268) & 0x4000) != 0 )
            _InterlockedOr((volatile signed __int32 *)&SpinLocka[6], 0x2000000u);
        }
        else
        {
          v47 = gAleNullSid;
        }
        *((_DWORD *)v34 + 4 * a3[41]) = 16;
        *((_QWORD *)v34 + 2 * a3[41] + 1) = &v156;
        *((_QWORD *)v35 + 70) = SpinLock;
        *((_DWORD *)v34 + 4 * a3[37]) = 13;
        *((_QWORD *)v34 + 2 * a3[37] + 1) = v47;
        v48 = *(_QWORD *)(SpinLock[61] + 144);
        if ( v48 )
        {
          v49 = *(_QWORD *)(*(_QWORD *)(v48 + 8) + 32LL);
          LODWORD(v133) = (unsigned __int16)(*(_WORD *)(v49 + 8) + 2);
          LODWORD(Size[0]) = v133 + 8;
          inserted = WfpPoolAllocNonPaged((unsigned int)(v133 + 8), 1668376129, &Size[1]);
          if ( inserted )
            goto LABEL_173;
          memset((void *)Size[1], 0, LODWORD(Size[0]));
          v50 = (unsigned __int16)v133;
          *(_QWORD *)Size[1] = *(_QWORD *)v49;
          memmove((void *)(Size[1] + 8), *(const void **)(v49 + 16), v50);
          v30 = v168;
        }
        v51 = v131;
        v52 = 2LL * a3[38];
        Entry = 0;
        *((_DWORD *)v34 + 2 * v52) = 12;
        *((_QWORD *)v34 + 2 * a3[38] + 1) = Size;
        v53 = a12;
        *((_OWORD *)v34 + a3[3]) = *a7;
        *((_OWORD *)v34 + a3[7]) = *v53;
        v54 = v135;
        *((_DWORD *)v34 + 4 * a3[6]) = 1;
        *((_BYTE *)v34 + 16 * a3[6] + 8) = v54;
        if ( v51 == 2 )
        {
          if ( v54 != 1 )
          {
LABEL_36:
            v55 = 2;
            v56 = __ROR2__(v132, 8);
            *((_DWORD *)v34 + 4 * a3[5]) = 2;
            *((_WORD *)v34 + 8 * a3[5] + 4) = v56;
            v57 = __ROR2__(v130, 8);
            *((_DWORD *)v34 + 4 * a3[8]) = 2;
            *((_WORD *)v34 + 8 * a3[8] + 4) = v57;
            goto LABEL_37;
          }
        }
        else if ( v51 != 23 || v54 != 58 )
        {
          goto LABEL_36;
        }
        v55 = 2;
        v61 = v146;
        *((_DWORD *)v34 + 4 * a3[5]) = 2;
        *((_WORD *)v34 + 8 * a3[5] + 4) = *(unsigned __int8 *)(v61 + 4);
        *((_DWORD *)v34 + 4 * a3[8]) = 2;
        *((_WORD *)v34 + 8 * a3[8] + 4) = *(unsigned __int8 *)(v61 + 5);
        *((_DWORD *)v34 + 4 * a3[34]) = 2;
        *((_WORD *)v34 + 8 * a3[34] + 4) = *(unsigned __int8 *)(v61 + 4);
        v62 = *(unsigned __int8 *)(v61 + 4);
        if ( v51 == 2 )
        {
          if ( (unsigned __int8)v62 <= 0x12u )
          {
            v63 = 418049;
            if ( _bittest(&v63, v62) )
            {
              *v35 |= 0x8000000u;
              v35[50] = *(_DWORD *)v61;
            }
          }
        }
        else if ( (unsigned __int8)(v62 + 0x80) <= 1u )
        {
          *v35 |= 0x8000000u;
          v35[50] = *(_DWORD *)v61;
        }
LABEL_37:
        v58 = v138;
        *((_DWORD *)v34 + 4 * a3[4]) = 1;
        *((_BYTE *)v34 + 16 * a3[4] + 8) = a9;
        *((_DWORD *)v34 + 4 * a3[12]) = 4;
        *((_QWORD *)v34 + 2 * a3[12] + 1) = &a10;
        *((_DWORD *)v34 + 4 * a3[13]) = 3;
        *((_DWORD *)v34 + 4 * a3[13] + 2) = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v58 + 8) + 48LL) + 12LL);
        *((_DWORD *)v34 + 4 * a3[14]) = 3;
        *((_DWORD *)v34 + 4 * a3[14] + 2) = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v58 + 8) + 48LL) + 16LL);
        v59 = a20;
        *((_DWORD *)v34 + 4 * a3[11]) = 1;
        *((_BYTE *)v34 + 16 * a3[11] + 8) = v59;
        *((_DWORD *)v34 + 4 * a3[19]) = 3;
        *((_DWORD *)v34 + 4 * a3[19] + 2) = *(_DWORD *)(*(_QWORD *)(v58 + 8) + 8LL);
        ProfileIdFromInterface = v139;
        if ( v139 )
        {
          ProfileIdFromInterface = WfpGetProfileIdFromInterface(v139, v58, v58, v141, 0);
          v58 = v138;
        }
        v64 = (int)v169;
        *v169 = ProfileIdFromInterface;
        AlepFillEdgeInterfaceRelatedFields(
          v64,
          (_DWORD)a3,
          0,
          0,
          v139,
          v58,
          v141,
          0,
          a16,
          ProfileIdFromInterface,
          0,
          (__int64)v34);
        if ( *((_DWORD *)v34 + 4 * a3[31]) )
          *(_DWORD *)v171 = *((_DWORD *)v34 + 4 * a3[31] + 2);
        v65 = (unsigned __int16)v130;
        v66 = v139 + 80;
        v67 = v150;
        v68 = v129;
        *((_DWORD *)v34 + 4 * a3[35]) = 4;
        *((_QWORD *)v34 + 2 * a3[35] + 1) = v66;
        if ( WfpAleFindPeerInformationForPeerName((_DWORD)SpinLock, v68, v67, v65, (__int64)&v148) || (v69 = v148) == 0 )
        {
          v71 = 0;
        }
        else
        {
          *((_DWORD *)v34 + 4 * a3[33]) = 12;
          *((_QWORD *)v34 + 2 * a3[33] + 1) = *(_QWORD *)(v69 + 64);
          v71 = *(unsigned __int8 *)(v69 + 2);
        }
        v72 = v124;
        if ( v124 && v30 )
        {
          v73 = v30;
          while ( *(_BYTE *)(v73 + 40) )
          {
            v73 = *(_QWORD *)(v73 + 48);
            if ( !v73 )
            {
              OriginalAppId = 0;
              goto LABEL_59;
            }
          }
          OriginalAppId = AleGetOriginalAppId(v30, v69, v70, v71);
          Entry = (PVOID)OriginalAppId;
        }
        else
        {
          OriginalAppId = 0;
        }
        if ( OriginalAppId )
        {
          v162 = *(_QWORD *)(OriginalAppId + 8);
          LODWORD(v161) = *(unsigned __int16 *)(OriginalAppId + 2);
          *((_DWORD *)v34 + 4 * a3[36]) = 12;
          *((_QWORD *)v34 + 2 * a3[36] + 1) = &v161;
        }
        else
        {
LABEL_59:
          *((_DWORD *)v34 + 4 * a3[36]) = 0;
        }
        v75 = 0;
        *((_DWORD *)v34 + 4 * a3[16]) = 3;
        if ( SpinLock != (PKSPIN_LOCK)-168LL )
        {
          v75 = 2 * (SpinLock[25] & 1);
          if ( (SpinLock[25] & 0x800) != 0 )
            v75 = (2 * (SpinLock[25] & 1)) | 0x10000;
        }
        v76 = v75 | 1;
        if ( !v72 )
          v76 = v75;
        if ( (SpinLock[6] & 0x10) != 0 )
          v76 |= 0x10u;
        v77 = v76 | 0x4000;
        if ( !(_DWORD)v71 )
          v77 = v76;
        v78 = v138;
        v79 = v77 | 0x100000;
        if ( !v30 )
          v79 = v77;
        if ( OriginalAppId )
          v79 |= 0x200000u;
        *((_DWORD *)v34 + 4 * a3[16] + 2) = v79;
        *((_DWORD *)v34 + 4 * a3[40]) = 3;
        *((_DWORD *)v34 + 4 * a3[40] + 2) = ***(_DWORD ***)(v78 + 8);
        v40 = *((_DWORD *)SpinLock + 170) == 1;
        *((_QWORD *)&v166 + 1) = 0;
        v167 = 0;
        *(_QWORD *)&v166 = SpinLocka;
        if ( v40 )
          v35[1] |= 0x80000u;
        *v35 |= 0x80u;
        *((_QWORD *)v35 + 1) = &v166;
        *v35 |= 0x20u;
        v80 = a21;
        *((_QWORD *)v35 + 8) = *(_QWORD *)(SpinLock[60] + 32);
        *v35 |= 0x400u;
        v35[11] = v80;
        *v35 |= 0x800u;
        v81 = v140;
        v35[20] = ***(_DWORD ***)(v78 + 8);
        if ( FeAcquireCompletionHandle(v81, &v142) )
          v142 = FeAcquireGenericCompletionHandle();
        *v35 |= 0x4000u;
        *((_QWORD *)v35 + 13) = v142;
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
        v82 = SpinLock[60];
        v83 = v129;
        v164 = *(_QWORD *)(v82 + 16);
        LODWORD(v163) = *(unsigned __int16 *)(v82 + 10);
        *v35 |= 8u;
        *((_QWORD *)v35 + 6) = &v163;
        *v35 |= 0x10u;
        *((_QWORD *)v35 + 7) = *(_QWORD *)(SpinLock[61] + 64);
        *v35 |= 0x40000u;
        v35[35] = 0;
        WfpAleInitializeAleEpoch(v83, SpinLock + 45);
        if ( (SpinLock[6] & 0x40) == 0 )
          _InterlockedOr((volatile signed __int32 *)SpinLock + 12, 0x40u);
        KfdGetLayerCacheEpoch(v83, &v134);
        *v35 |= 0x8000u;
        v84 = v149;
        *((_QWORD *)v35 + 14) = *(_QWORD *)v149;
        if ( *(_QWORD *)(v84 + 48) )
        {
          *v35 |= 0x4000000u;
          *((_QWORD *)v35 + 24) = *(_QWORD *)(v84 + 48);
        }
        if ( *(_DWORD *)(v84 + 8) )
        {
          *v35 |= 0x20000u;
          v35[30] = *(_DWORD *)(v84 + 8);
        }
        if ( *(_QWORD *)(v84 + 16) )
        {
          *v35 |= 0x10000u;
          *((_QWORD *)v35 + 16) = *(_QWORD *)(v84 + 16);
          v35[34] = *(_DWORD *)(v84 + 24);
        }
        if ( *(_QWORD *)(v84 + 32) )
        {
          *v35 |= 0x800000u;
          *((_QWORD *)v35 + 18) = *(_QWORD *)(v84 + 32);
          v35[38] = *(_DWORD *)(v84 + 40);
        }
        LODWORD(SpinLocka[16]) = 1;
        WORD2(SpinLocka[16]) = 256;
        SpinLocka[17] = 0;
        SpinLocka[18] = 0;
        if ( gAleDebugEnabled )
        {
          v85 = WfpPoolAllocNonPaged(80, 1919247937, &SpinLocka[19]);
          v86 = SpinLocka[19];
          if ( v85 )
            v86 = 0xBADBADFABADBADFAuLL;
          SpinLocka[19] = v86;
          if ( gAleDebugEnabled && v86 != 0xBADBADFABADBADFAuLL )
            _InterlockedIncrement((volatile signed __int32 *)(v86 + 4));
        }
        else
        {
          SpinLocka[19] = 0xBADBADFABADBADFAuLL;
        }
        *(_QWORD *)&v171 = &SpinLocka[16];
        LODWORD(SpinLocka[16]) = (LODWORD(SpinLocka[16]) + 4)
                               ^ (LOBYTE(SpinLocka[16])
                                ^ (unsigned __int8)(LOBYTE(SpinLocka[16]) + 4))
                               & 3;
        KfdAleInitializeFlowTable(&SpinLocka[9], 0);
        if ( !KfdAleAcquireFlowHandleForFlow(SpinLock, SpinLocka, &v154) )
        {
          *v35 |= 2u;
          *((_QWORD *)v35 + 4) = v154;
          if ( v30 )
            *(_QWORD *)(v30 + 504) = v154;
          KfdAleReleaseFlowHandleForFlow(SpinLock);
        }
        v87 = v144;
        *((_BYTE *)v35 + 592) = *(_BYTE *)(SpinLock[61] + 152);
        *(_OWORD *)(v35 + 150) = *(_OWORD *)(SpinLock[61] + 160);
        *((_QWORD *)v35 + 77) = *(_QWORD *)(SpinLock[61] + 176);
        *(_OWORD *)(v35 + 162) = *(_OWORD *)(SpinLock[61] + 192);
        v123 = (__int64)v158;
        *(_OWORD *)(v35 + 166) = *(_OWORD *)(SpinLock[61] + 208);
        v88 = WfpAleClassify((unsigned int)&v165, (_DWORD)v35, v87, 0, (__int64)v128, v123);
        inserted = v88;
        v125 = v128[0];
        if ( v128[0] )
        {
          _InterlockedOr((volatile signed __int32 *)&SpinLocka[6], 0x8000u);
        }
        else if ( v88 )
        {
          goto LABEL_173;
        }
        v36 = 0;
        v89 = v138;
        v90 = 0;
        if ( (*((_DWORD *)SpinLock + 13) & 0x10) == 0 )
          SpinLock[59] = v138;
        if ( (unsigned int)(a20 - 3) > 1 )
        {
          v91 = 0;
          v92 = 0;
          if ( v35[84] )
            v90 = v35[86];
          if ( v35[76] )
            v91 = v35[78] == 1;
          if ( v35[80] )
            v92 = v35[82] == 1;
          if ( !v91 && !v92 )
          {
            inserted = WfpAleInsertRemoteEndpoint(
                         SpinLock,
                         v131,
                         v135,
                         v139,
                         v89,
                         v132,
                         (_DWORD *)v150,
                         v130,
                         v124,
                         v146,
                         v129,
                         v134,
                         1,
                         v141,
                         0,
                         (__int64)SpinLocka,
                         v90,
                         0,
                         1,
                         0,
                         (__int64)v35,
                         (PKSPIN_LOCK *)v137,
                         (_BYTE *)v153);
            if ( inserted )
              goto LABEL_173;
            goto LABEL_134;
          }
          LODWORD(v133) = 0;
          v171 = 0;
          if ( v131 == 2 )
          {
            v93 = &v133;
LABEL_126:
            v94 = 0;
            if ( !v92 )
              v94 = v130;
            inserted = WfpAleInsertRemoteEndpoint(
                         SpinLock,
                         v131,
                         v135,
                         v139,
                         v89,
                         v132,
                         v93,
                         v94,
                         v124,
                         v146,
                         v129,
                         v134,
                         1,
                         v141,
                         0,
                         (__int64)SpinLocka,
                         0,
                         0,
                         1,
                         v92 + 1,
                         (__int64)v35,
                         (PKSPIN_LOCK *)v137,
                         (_BYTE *)v153);
            if ( inserted )
              goto LABEL_173;
            if ( (*((_DWORD *)SpinLock + 12) & 0x80u) == 0 )
              _InterlockedOr((volatile signed __int32 *)SpinLock + 12, 0x80u);
            if ( v92 && (*((_DWORD *)SpinLock + 13) & 0x40000) == 0 )
              _InterlockedOr((volatile signed __int32 *)SpinLock + 13, 0x40000u);
LABEL_134:
            inserted = WfpAleOptionalSetPeerInformation(*(_QWORD *)v137, v148);
            if ( inserted )
              goto LABEL_173;
            v36 = (PDEVICE_OBJECT *)v137;
            if ( (*(_DWORD *)(*(_QWORD *)v137 + 48LL) & 0x4000) != 0 )
            {
              if ( (*(_DWORD *)(*(_QWORD *)v137 + 48LL) & 0x8000) == 0 )
              {
                v95 = *(_QWORD *)v137;
                v96 = v140;
                v97 = (unsigned __int16)v130;
                v98 = v150;
                v99 = v131;
                *(_QWORD *)(v140 + 16) = *(_QWORD *)v137;
                *(_QWORD *)(v95 + 288) = *(_QWORD *)(v96 + 64);
                if ( !WfpAleAcquirePeerInformation(SpinLock, v99, v98, v97, v95 + 256) )
                  _InterlockedOr((volatile signed __int32 *)(v95 + 48), 0x10000u);
                v100 = WfpAllocateFromPerProcessorLookasideList(authorizeContextPPLookasideList, &v152);
                v33 = (__int128 *)v152;
                inserted = v100;
                if ( v100 )
                  goto LABEL_173;
                memset(v152, 0, 0x150u);
                v101 = v149;
                v102 = *(_DWORD *)(v149 + 24);
                if ( !v102 )
                  goto LABEL_143;
                inserted = WfpPoolAllocNonPaged(v102, 1432710209, &v155);
                P = v155;
                if ( !inserted )
                {
                  v101 = v149;
LABEL_143:
                  v103 = *(_DWORD *)(v101 + 40);
                  if ( v103 )
                  {
                    inserted = WfpPoolAllocNonPaged(v103, 1432710209, &v151);
                    if ( inserted )
                    {
                      v37 = 1;
                      v147 = v151;
                      goto LABEL_24;
                    }
                    v104 = v151;
                    v101 = v149;
                  }
                  else
                  {
                    v104 = v147;
                  }
                  v105 = (__int128 *)v140;
                  v106 = v33;
                  do
                  {
                    v106 += 8;
                    v107 = *v105;
                    v105 += 8;
                    *(v106 - 8) = v107;
                    *(v106 - 7) = *(v105 - 7);
                    *(v106 - 6) = *(v105 - 6);
                    *(v106 - 5) = *(v105 - 5);
                    *(v106 - 4) = *(v105 - 4);
                    *(v106 - 3) = *(v105 - 3);
                    *(v106 - 2) = *(v105 - 2);
                    *(v106 - 1) = *(v105 - 1);
                    --v55;
                  }
                  while ( v55 );
                  *v106 = *v105;
                  v106[1] = v105[1];
                  v106[2] = v105[2];
                  v106[3] = v105[3];
                  v106[4] = v105[4];
                  *((_QWORD *)v33 + 35) = v144;
                  *((_QWORD *)v33 + 36) = P;
                  *((_DWORD *)v33 + 74) = *(_DWORD *)(v101 + 24);
                  *((_QWORD *)v33 + 38) = v104;
                  *((_DWORD *)v33 + 78) = *(_DWORD *)(v101 + 40);
                  v108 = *((_QWORD *)v33 + 35);
                  v147 = 0;
                  P = 0;
                  NetioReferenceNetBufferList(v108);
                  inserted = WfpAleSecureSocketAdd(
                               v95,
                               *(unsigned __int16 *)(v95 + 60),
                               (unsigned int)WfpAlepAuthorizeSendSecureCompletion,
                               (_DWORD)v33,
                               v150);
                  if ( inserted )
                    goto LABEL_173;
                  v36 = (PDEVICE_OBJECT *)v137;
                  v33 = 0;
                  _InterlockedOr((volatile signed __int32 *)(*(_QWORD *)v137 + 48LL), 0x8000u);
                  v125 = 1;
                  *(_BYTE *)(v140 + 81) = 1;
                  *(_BYTE *)v172 = 1;
                  _InterlockedOr((volatile signed __int32 *)&(*v36)->Flags, 0x100000u);
                  goto LABEL_170;
                }
LABEL_173:
                v37 = 1;
                goto LABEL_24;
              }
            }
            else if ( !v125 )
            {
              v109 = v140;
              v110 = *(_QWORD *)v137;
              _InterlockedIncrement(*(volatile signed __int32 **)(v140 + 48));
              v111 = *(volatile signed __int32 **)(v109 + 64);
              *(_QWORD *)(v110 + 288) = v111;
              _InterlockedIncrement(v111);
            }
            _InterlockedOr((volatile signed __int32 *)&(*v36)->Flags, 0x100000u);
LABEL_170:
            if ( *(_QWORD *)v137 && Entry )
              _InterlockedOr((volatile signed __int32 *)(*(_QWORD *)v137 + 52LL), 0x10000u);
            goto LABEL_173;
          }
          if ( v131 == 23 )
          {
            v93 = (__int64 *)&v171;
            goto LABEL_126;
          }
LABEL_174:
          __fastfail(5u);
        }
        v112 = v35[72];
        if ( v112 && (v112 != 3 || v35[74] == 1) )
          goto LABEL_170;
        LODWORD(v133) = 0;
        v172 = 0;
        v144 = *(_QWORD *)v146;
        if ( v131 == 2 )
        {
          v113 = &v133;
        }
        else
        {
          if ( v131 != 23 )
            goto LABEL_174;
          v113 = (__int64 *)&v172;
        }
        v114 = 2;
        if ( v35[88] )
          v90 = v35[90];
        if ( v112 )
        {
          v114 = 2;
          if ( v35[74] == 2 )
            v114 = 10;
        }
        LODWORD(v144) = 0;
        inserted = WfpAleInsertRemoteEndpoint(
                     SpinLock,
                     v131,
                     v135,
                     v139,
                     v138,
                     v132,
                     v113,
                     0,
                     v124,
                     (__int64)&v144,
                     v83,
                     v134,
                     1,
                     v141,
                     0,
                     (__int64)SpinLocka,
                     v90,
                     0,
                     v114,
                     0,
                     (__int64)v35,
                     (PKSPIN_LOCK *)v137,
                     (_BYTE *)v153);
        if ( inserted )
          goto LABEL_173;
        if ( (*((_DWORD *)SpinLock + 12) & 0x80u) == 0 )
          _InterlockedOr((volatile signed __int32 *)SpinLock + 12, 0x80u);
        goto LABEL_170;
      }
      v43 = (char *)gIncomingValuesLookasideList
          + 128 * (unsigned __int64)(unsigned int)(HIDWORD(KeGetPcr()[1].LockArray) + 1);
      if ( !v43[176] )
        PplpLazyInitializeLookasideList(gIncomingValuesLookasideList, v43 + 64);
      ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v43 + 64), Entry);
    }
    v37 = 0;
    v35 = 0;
    if ( v126 )
      WfpLowerIrqlFromDispatchLevel(v127);
    v38 = WPP_GLOBAL_Control;
    v40 = WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control;
    inserted = -1073741670;
    goto LABEL_20;
  }
  v37 = 0;
  *v158 = 4097;
  v38 = WPP_GLOBAL_Control;
  inserted = -1073741790;
  v40 = WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control;
LABEL_20:
  if ( !v40 && BYTE1(v38->Timer) >= 2u && (HIDWORD(v38->Timer) & 0x1000) != 0 )
    WPP_SF_sd(
      v38->AttachedDevice,
      10,
      (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
      (unsigned int)"WfpAlepAuthorizeSend",
      inserted);
LABEL_24:
  if ( v142 )
  {
    FeReleaseCompletionHandle(v142, v36);
    v142 = 0;
  }
  if ( Size[1] )
  {
    ExFreePoolWithTag((PVOID)Size[1], 0);
    Size[1] = 0;
    LODWORD(Size[0]) = 0;
  }
  if ( v33 )
  {
    v115 = *((_QWORD *)v33 + 35);
    if ( v115 )
      NetioDereferenceNetBufferList(v115, 0);
    v116 = (void *)*((_QWORD *)v33 + 36);
    if ( v116 )
    {
      ExFreePoolWithTag(v116, 0);
      *((_QWORD *)v33 + 36) = 0xBADBADFABADBADFAuLL;
    }
    v117 = (void *)*((_QWORD *)v33 + 38);
    if ( v117 )
    {
      ExFreePoolWithTag(v117, 0);
      *((_QWORD *)v33 + 38) = 0xBADBADFABADBADFAuLL;
    }
    v118 = (char *)authorizeContextPPLookasideList
         + 128 * (unsigned __int64)(unsigned int)(HIDWORD(KeGetPcr()[1].LockArray) + 1);
    if ( !v118[176] )
      PplpLazyInitializeLookasideList(authorizeContextPPLookasideList, v118 + 64);
    ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v118 + 64), v33);
  }
  if ( P )
    ExFreePoolWithTag(P, 0);
  if ( v147 )
    ExFreePoolWithTag(v147, 0);
  if ( v148 )
  {
    if ( *((_DWORD *)SpinLock + 10) != 6 || (SpinLock[6] & 0x10) != 0 )
    {
      WfpAleReleasePeerInformation();
    }
    else if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v148 + 24), 0xFFFFFFFF) == 1 )
    {
      WfpAlepFreePeerInformation();
    }
  }
  if ( SpinLocka[31] )
    WfpAlepFreePeerTokenInformation(&SpinLocka[31]);
  if ( SpinLocka[12] )
    KfdAleNotifyFlowDeletion(&SpinLocka[9]);
  if ( v125 )
    inserted = 259;
  if ( v37 )
  {
    v119 = (PVOID *)((char *)gPerProcessorContext + 72 * HIDWORD(KeGetPcr()[1].LockArray));
    KfdReleaseTerminatingFilters(v35 + 156);
    if ( v34 == v119[3] )
    {
      *((_BYTE *)v119 + 32) = 0;
    }
    else
    {
      v120 = (char *)gMetadataLookasideList
           + 128 * (unsigned __int64)(unsigned int)(HIDWORD(KeGetPcr()[1].LockArray) + 1);
      if ( !v120[176] )
        PplpLazyInitializeLookasideList(gMetadataLookasideList, v120 + 64);
      ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v120 + 64), v35);
      v121 = (char *)gIncomingValuesLookasideList
           + 128 * (unsigned __int64)(unsigned int)(HIDWORD(KeGetPcr()[1].LockArray) + 1);
      if ( !v121[176] )
        PplpLazyInitializeLookasideList(gIncomingValuesLookasideList, v121 + 64);
      ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v121 + 64), v34);
    }
    if ( v126 )
      WfpLowerIrqlFromDispatchLevel(v127);
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
