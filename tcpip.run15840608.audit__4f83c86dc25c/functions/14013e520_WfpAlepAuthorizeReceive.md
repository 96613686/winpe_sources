# WfpAlepAuthorizeReceive

- ea: `0x14013e520`
- end: `0x14013fc26`
- name: `WfpAlepAuthorizeReceive`
- size: `5894`
- prototype: `__int64 __usercall@<rax>(PKSPIN_LOCK SpinLock@<rcx>, int, __int64, __int64, __int64, __int16, char, char, __int64, __int64, __int16, __int64, __int64, char, char, int, int, int, int, __int64, int, PKSPIN_LOCK, __int64, __int64, char, char, char, __int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `24`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400adf8c`

## callees

- `0x14001215c`
- `0x1400143c0`
- `0x140014480`
- `0x140014974`
- `0x1400162f0`
- `0x140016470`
- `0x14005ff90`
- `0x140061630`
- `0x140072e40`
- `0x1400730c0`
- `0x1400ad6a0`
- `0x1400e4064`
- `0x1400ff2c8`
- `0x14010854c`
- `0x140131214`
- `0x14013e520`
- `0x140141b90`
- `0x140150f98`
- `0x140174e84`
- `0x140174f08`
- `0x1401c0fd0`
- `0x1401c1200`
- `0x1401c1280`
- `0x1401c1580`

## import_xrefs

- `ntoskrnl!MmBadPointer` at `0x14013e697`
- `ntoskrnl!MmBadPointer` at `0x14013e6ac`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14013e8a3`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14013fb5e`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14013fb9e`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14013e8a3`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14013fb5e`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14013fb9e`
- `ntoskrnl!KeGetCurrentIrql` at `0x14013e7f1`
- `ntoskrnl!KeGetCurrentIrql` at `0x14013e7f1`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14013f09b`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14013f09b`
- `ntoskrnl!RtlCompareMemory` at `0x14013e713`
- `ntoskrnl!RtlCompareMemory` at `0x14013e773`
- `ntoskrnl!RtlCompareMemory` at `0x14013e78b`
- `ntoskrnl!RtlCompareMemory` at `0x14013e713`
- `ntoskrnl!RtlCompareMemory` at `0x14013e773`
- `ntoskrnl!RtlCompareMemory` at `0x14013e78b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14013f14a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14013f14a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14013f169`
- `ntoskrnl!ExFreePoolWithTag` at `0x14013f97f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14013fac7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14013f169`
- `ntoskrnl!ExFreePoolWithTag` at `0x14013f97f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14013fac7`
- `ntoskrnl!ExAllocatePool2` at `0x14013eef6`
- `ntoskrnl!ExAllocatePool2` at `0x14013eef6`
- `NETIO!WfpNblInfoGet` at `0x14013e683`
- `NETIO!WfpNblInfoGet` at `0x14013e683`
- `NETIO!FeReleaseCompletionHandle` at `0x14013f95c`
- `NETIO!FeReleaseCompletionHandle` at `0x14013f95c`
- `NETIO!FeAcquireGenericCompletionHandle` at `0x14013f338`
- `NETIO!FeAcquireGenericCompletionHandle` at `0x14013f338`
- `NETIO!FeAcquireCompletionHandle` at `0x14013f327`
- `NETIO!FeAcquireCompletionHandle` at `0x14013f327`
- `NETIO!KfdAleInitializeFlowTable` at `0x14013f493`
- `NETIO!KfdAleInitializeFlowTable` at `0x14013f493`
- `NETIO!KfdAleNotifyFlowDeletion` at `0x14013f9ec`
- `NETIO!KfdAleNotifyFlowDeletion` at `0x14013f9ec`
- `NETIO!KfdReleaseTerminatingFilters` at `0x14013fb0c`
- `NETIO!KfdReleaseTerminatingFilters` at `0x14013fb0c`
- `NETIO!KfdAleReleaseFlowHandleForFlow` at `0x14013f4c8`
- `NETIO!KfdAleReleaseFlowHandleForFlow` at `0x14013f4c8`
- `NETIO!KfdAleAcquireFlowHandleForFlow` at `0x14013f4a9`
- `NETIO!KfdAleAcquireFlowHandleForFlow` at `0x14013f4a9`
- `NETIO!KfdGetLayerCacheEpoch` at `0x14013f3c1`
- `NETIO!KfdGetLayerCacheEpoch` at `0x14013f3ed`
- `NETIO!KfdGetLayerCacheEpoch` at `0x14013f3c1`
- `NETIO!KfdGetLayerCacheEpoch` at `0x14013f3ed`

## string_xrefs

- `0x14013efc5`: `WfpAleQueryPeerTokenInformation`
- `0x14013f029`: `StringCchCopyA`
- `0x14013f06c`: `WfpStringCchCopyA`

## pseudocode

```c
__int64 __fastcall WfpAlepAuthorizeReceive(
        PKSPIN_LOCK SpinLock,
        unsigned __int16 a2,
        unsigned __int16 *a3,
        unsigned __int16 a4,
        int a5,
        __int64 a6,
        __int64 a7,
        _OWORD *a8,
        __int16 a9,
        char a10,
        char a11,
        __int64 a12,
        _OWORD *a13,
        __int16 a14,
        __int64 a15,
        __int64 a16,
        char a17,
        unsigned __int8 a18,
        int a19,
        int a20,
        int a21,
        int a22,
        __int64 a23,
        int a24,
        PKSPIN_LOCK SpinLocka,
        __int64 a26,
        _QWORD *a27,
        char a28,
        char a29,
        char a30,
        __int64 a31,
        __int64 a32,
        _QWORD *a33,
        __int64 a34,
        _DWORD *a35,
        _DWORD *a36)
{
  _QWORD *v36; // rbx
  __int64 v37; // rdi
  _DWORD *v38; // rsi
  _DWORD *v41; // r12
  PKSPIN_LOCK v42; // r13
  _QWORD *v43; // rdx
  _QWORD *v44; // rcx
  const void *v45; // rdx
  const void *v46; // rcx
  bool v47; // zf
  __int16 v48; // ax
  __int16 v49; // di
  __int64 v50; // rdx
  KSPIN_LOCK *v51; // rax
  __int64 v52; // rcx
  PVOID v53; // rdi
  _DWORD *v54; // rbx
  char *v55; // rbx
  char v56; // r15
  unsigned __int8 v57; // r12
  __int64 v58; // rsi
  __int64 *v59; // rdx
  KSPIN_LOCK v60; // rcx
  KSPIN_LOCK v61; // rcx
  __int64 v62; // rax
  __int64 v63; // r12
  size_t v64; // r8
  int v65; // r10d
  PKSPIN_LOCK v66; // rdx
  int v67; // r8d
  _OWORD *v68; // rax
  PKSPIN_LOCK v69; // rcx
  int v70; // r8d
  int v71; // edx
  int v72; // ecx
  int v73; // eax
  int v74; // ecx
  __int16 v75; // cx
  __int64 v76; // rdx
  int v77; // ecx
  int ProfileIdFromPacketInbound; // eax
  __int64 v79; // r8
  unsigned int v80; // eax
  int v81; // ecx
  int v82; // esi
  _DWORD **v83; // r8
  __int64 v84; // r12
  __int64 v85; // rsi
  _BYTE *v86; // rcx
  __int64 v87; // rdx
  const char *v88; // r8
  char v89; // r12
  _BYTE *v90; // rax
  __int64 v91; // rsi
  KSPIN_LOCK v92; // rax
  unsigned int v93; // r8d
  __int64 v94; // r9
  unsigned int v95; // ecx
  __int64 v96; // rax
  int v97; // edx
  void *v98; // rsi
  __int64 *v99; // rcx
  __int64 v100; // rax
  __int64 v101; // rcx
  int v102; // eax
  int v103; // ecx
  __int64 v104; // rcx
  int v105; // eax
  unsigned __int16 v106; // r15
  KSPIN_LOCK v107; // rcx
  int v108; // eax
  _QWORD *v109; // rcx
  int v110; // r9d
  unsigned int v111; // r12d
  bool v112; // r15
  unsigned __int16 v113; // r10
  int v114; // r8d
  int v115; // edx
  char v116; // r9
  __int64 v117; // r15
  __int64 inserted; // rax
  volatile signed __int32 *v119; // rcx
  __int64 *v120; // rdx
  KSPIN_LOCK v121; // rcx
  KSPIN_LOCK *v122; // rcx
  KSPIN_LOCK v123; // rax
  char v124; // r9
  signed __int32 v125; // edx
  unsigned __int32 v126; // ecx
  void *v127; // r14
  __int64 v128; // rax
  PVOID *v129; // r14
  char *v130; // r14
  char *v131; // rbx
  int v133; // [rsp+20h] [rbp-120h]
  __int64 v134; // [rsp+28h] [rbp-118h]
  unsigned __int8 v135; // [rsp+C0h] [rbp-80h]
  char v136; // [rsp+C1h] [rbp-7Fh]
  char v137; // [rsp+C2h] [rbp-7Eh]
  char v138; // [rsp+C3h] [rbp-7Dh]
  __int16 v139; // [rsp+C4h] [rbp-7Ch]
  __int64 Pool2; // [rsp+C8h] [rbp-78h] BYREF
  __int16 v142; // [rsp+D0h] [rbp-70h]
  unsigned __int16 v143; // [rsp+D2h] [rbp-6Eh]
  __int64 v144; // [rsp+D8h] [rbp-68h]
  int v145; // [rsp+E0h] [rbp-60h]
  PVOID Entry; // [rsp+E8h] [rbp-58h] BYREF
  __int64 v147; // [rsp+F0h] [rbp-50h]
  char v148[4]; // [rsp+F8h] [rbp-48h] BYREF
  int v149; // [rsp+FCh] [rbp-44h]
  int v150; // [rsp+100h] [rbp-40h] BYREF
  __int64 v151; // [rsp+108h] [rbp-38h]
  __int64 v152; // [rsp+110h] [rbp-30h] BYREF
  __int64 v153; // [rsp+118h] [rbp-28h] BYREF
  size_t Size[2]; // [rsp+120h] [rbp-20h] BYREF
  _DWORD *v155; // [rsp+130h] [rbp-10h]
  __int64 v156; // [rsp+138h] [rbp-8h] BYREF
  _DWORD *v157; // [rsp+140h] [rbp+0h]
  __int64 v158; // [rsp+148h] [rbp+8h]
  KSPIN_LOCK *v159; // [rsp+150h] [rbp+10h]
  __int64 v160; // [rsp+158h] [rbp+18h]
  __int64 v161; // [rsp+160h] [rbp+20h] BYREF
  KSPIN_LOCK v162; // [rsp+168h] [rbp+28h]
  __int64 v163; // [rsp+170h] [rbp+30h]
  __int64 v164; // [rsp+178h] [rbp+38h]
  __int64 v165; // [rsp+180h] [rbp+40h] BYREF
  __int64 v166; // [rsp+188h] [rbp+48h]
  __int64 v167; // [rsp+190h] [rbp+50h] BYREF
  __int64 v168; // [rsp+198h] [rbp+58h]
  __int64 v169; // [rsp+1A0h] [rbp+60h] BYREF
  __int64 v170; // [rsp+1A8h] [rbp+68h]
  __int64 v171; // [rsp+1B0h] [rbp+70h] BYREF
  __int64 v172; // [rsp+1B8h] [rbp+78h]
  __int128 v173; // [rsp+1C0h] [rbp+80h] BYREF
  __int128 v174; // [rsp+1D0h] [rbp+90h] BYREF
  __int64 v175; // [rsp+1E0h] [rbp+A0h]
  __int64 v176; // [rsp+1E8h] [rbp+A8h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+1F0h] [rbp+B0h] BYREF
  _OWORD Source2[5]; // [rsp+210h] [rbp+D0h] BYREF
  __int128 v179; // [rsp+260h] [rbp+120h] BYREF

  v36 = 0;
  v37 = a23;
  v38 = a35;
  v41 = a36;
  v42 = SpinLocka;
  v158 = a15;
  v145 = a5;
  v144 = a7;
  v139 = a9;
  v160 = a12;
  v142 = a14;
  v176 = a16;
  v137 = a17;
  v149 = a24;
  *(_QWORD *)&v179 = a32;
  v166 = a34;
  v163 = (__int64)a33;
  *a33 = 0;
  LODWORD(v168) = 0;
  LODWORD(v162) = 0;
  LODWORD(v157) = 0;
  LODWORD(v170) = 0;
  LODWORD(v172) = 0;
  v167 = 0;
  v161 = 0;
  v156 = 0;
  v169 = 0;
  v171 = 0;
  v143 = a2;
  v147 = a6;
  v151 = v37;
  v152 = (__int64)v38;
  v155 = v41;
  v159 = 0;
  v164 = 0;
  v150 = 0;
  Entry = 0;
  *(_OWORD *)Size = 0;
  Pool2 = 0;
  v173 = 0;
  v136 = 0;
  v135 = 0;
  v174 = 0;
  v175 = 0;
  v165 = 0;
  v153 = 0;
  v43 = (_QWORD *)WfpNblInfoGet(v37);
  if ( !v43 || (v44 = MmBadPointer, v43 == MmBadPointer) )
  {
    v44 = MmBadPointer;
    if ( v43 == MmBadPointer )
      v36 = MmBadPointer;
  }
  else
  {
    v36 = (_QWORD *)v43[1];
  }
  if ( v37 && v36 && v36 != v44 )
  {
    memset(Source2, 0, sizeof(Source2));
    if ( RtlCompareMemory(v36 + 23, Source2, 0x50u) != 80 )
    {
      WfpAleTransferAleIpsecContext(v36 + 23, v42 + 21);
      _InterlockedDecrement(&gAleASyncCount);
    }
    if ( v36[40] )
    {
      v45 = **(const void ***)(v144 + 16);
      v46 = **(const void ***)(v36[38] + 16LL);
      if ( a4 == 2 )
        v47 = RtlCompareMemory(v46, v45, 4u) == 4;
      else
        v47 = RtlCompareMemory(v46, v45, 0x10u) == 16;
      if ( !v47 )
        v144 = v36[38];
      v48 = *((_WORD *)v36 + 156);
      v49 = a9;
      v50 = v36[38];
      v36[38] = 0;
      if ( a9 != v48 )
        v49 = v48;
      v164 = v50;
      v51 = (KSPIN_LOCK *)v36[40];
      v36[40] = 0;
      _InterlockedDecrement(&gAleASyncCount);
      v159 = v51;
      v139 = v49;
    }
  }
  if ( KeGetCurrentIrql() < 2u )
  {
    v135 = WfpRaiseIrqlToDispatchLevel();
    v136 = 1;
  }
  LODWORD(v52) = HIDWORD(KeGetPcr()[1].LockArray);
  if ( !*((_BYTE *)gPerProcessorContext + 72 * v52 + 32) )
  {
    v53 = (PVOID)*((_QWORD *)gPerProcessorContext + 9 * v52 + 3);
    v54 = (_DWORD *)*((_QWORD *)gPerProcessorContext + 9 * v52 + 2);
    *((_BYTE *)gPerProcessorContext + 72 * v52 + 32) = 1;
    goto LABEL_36;
  }
  if ( !WfpAllocateFromPerProcessorLookasideList(gIncomingValuesLookasideList, &Entry) )
  {
    if ( !WfpAllocateFromPerProcessorLookasideList(gMetadataLookasideList, &Pool2) )
    {
      v53 = Entry;
      v54 = (_DWORD *)Pool2;
LABEL_36:
      v138 = 1;
      memset(v53, 0, 0x2A0u);
      memset(v54, 0, 0x2A8u);
      *((_QWORD *)v54 + 79) = v54 + 156;
      v59 = gAleNullSid;
      *((_QWORD *)v54 + 78) = v54 + 156;
      v60 = SpinLock[60];
      LOWORD(v173) = v143;
      DWORD1(v173) = *a3;
      *((_QWORD *)&v173 + 1) = v53;
      v168 = *(_QWORD *)(v60 + 16);
      LODWORD(v167) = *(unsigned __int16 *)(v60 + 10);
      *((_DWORD *)v53 + 4 * a3[1]) = 12;
      *((_QWORD *)v53 + 2 * a3[1] + 1) = &v167;
      v61 = SpinLock[61];
      v162 = v61 + 224;
      LODWORD(v161) = *(_DWORD *)(v61 + 72);
      *((_DWORD *)v53 + 4 * a3[2]) = 16;
      *((_QWORD *)v53 + 2 * a3[2] + 1) = &v161;
      if ( *(_QWORD *)(SpinLock[61] + 280) )
        v59 = *(__int64 **)(SpinLock[61] + 280);
      *((_DWORD *)v53 + 4 * a3[37]) = 13;
      *((_QWORD *)v53 + 2 * a3[37] + 1) = v59;
      *((_DWORD *)v53 + 4 * a3[41]) = 16;
      *((_QWORD *)v53 + 2 * a3[41] + 1) = &v161;
      v62 = *(_QWORD *)(SpinLock[61] + 144);
      if ( v62 )
      {
        v63 = *(_QWORD *)(*(_QWORD *)(v62 + 8) + 32LL);
        LODWORD(Pool2) = (unsigned __int16)(*(_WORD *)(v63 + 8) + 2);
        LODWORD(Size[0]) = Pool2 + 8;
        v58 = WfpPoolAllocNonPaged((unsigned int)(Pool2 + 8), 1668376129, &Size[1]);
        if ( v58 )
          goto LABEL_202;
        memset((void *)Size[1], 0, LODWORD(Size[0]));
        v64 = (unsigned __int16)Pool2;
        *(_QWORD *)Size[1] = *(_QWORD *)v63;
        memmove((void *)(Size[1] + 8), *(const void **)(v63 + 16), v64);
        v38 = (_DWORD *)v152;
        v41 = v155;
      }
      v65 = v145;
      v66 = v42 + 21;
      v67 = 0;
      *((_DWORD *)v53 + 4 * a3[38]) = 12;
      *((_QWORD *)v53 + 2 * a3[38] + 1) = Size;
      v68 = a13;
      *((_OWORD *)v53 + a3[3]) = *a8;
      *((_OWORD *)v53 + a3[7]) = *v68;
      v69 = v42 + 21;
      *((_DWORD *)v53 + 4 * a3[6]) = 1;
      *((_BYTE *)v53 + 16 * a3[6] + 8) = v65;
      if ( !v42 )
        v69 = 0;
      *((_DWORD *)v53 + 4 * a3[16]) = 3;
      if ( v69 )
      {
        if ( v42 )
        {
          v70 = *((_DWORD *)v42 + 50);
        }
        else
        {
          LOBYTE(v70) = MEMORY[0x20];
          v66 = 0;
        }
        v67 = 2 * (v70 & 1);
        if ( (v66[4] & 0x800) != 0 )
          v67 |= 0x10000u;
      }
      v71 = v67 | 1;
      if ( !v137 )
        v71 = v67;
      if ( (SpinLock[6] & 0x10) != 0 )
        v71 |= 0x10u;
      v72 = v71 | 0x400000;
      if ( !a28 )
        v72 = v71;
      v73 = v72 | 0x800000;
      if ( !a29 )
        v73 = v72;
      v74 = v73 | 0x1000000;
      if ( !a30 )
        v74 = v73;
      *((_DWORD *)v53 + 4 * a3[16] + 2) = v74;
      if ( a4 == 2 )
      {
        if ( v65 != 1 )
        {
LABEL_61:
          *((_DWORD *)v53 + 4 * a3[5]) = 2;
          *((_WORD *)v53 + 8 * a3[5] + 4) = __ROR2__(v139, 8);
          v75 = __ROR2__(v142, 8);
          *((_DWORD *)v53 + 4 * a3[8]) = 2;
          *((_WORD *)v53 + 8 * a3[8] + 4) = v75;
          goto LABEL_62;
        }
      }
      else if ( a4 != 23 || v65 != 58 )
      {
        goto LABEL_61;
      }
      v79 = v158;
      *((_DWORD *)v53 + 4 * a3[5]) = 2;
      *((_WORD *)v53 + 8 * a3[5] + 4) = *(unsigned __int8 *)(v79 + 4);
      *((_DWORD *)v53 + 4 * a3[8]) = 2;
      *((_WORD *)v53 + 8 * a3[8] + 4) = *(unsigned __int8 *)(v79 + 5);
      *((_DWORD *)v53 + 4 * a3[34]) = 2;
      *((_WORD *)v53 + 8 * a3[34] + 4) = *(unsigned __int8 *)(v79 + 4);
      v80 = *(unsigned __int8 *)(v79 + 4);
      if ( a4 == 2 )
      {
        if ( (unsigned __int8)v80 <= 0x12u )
        {
          v81 = 418049;
          if ( _bittest(&v81, v80) )
          {
            *v54 |= 0x8000000u;
            v54[50] = *(_DWORD *)v79;
          }
        }
      }
      else if ( (unsigned __int8)(v80 + 0x80) <= 1u )
      {
        *v54 |= 0x8000000u;
        v54[50] = *(_DWORD *)v79;
      }
LABEL_62:
      v76 = v144;
      *((_DWORD *)v53 + 4 * a3[4]) = 1;
      *((_BYTE *)v53 + 16 * a3[4] + 8) = a10;
      *((_DWORD *)v53 + 4 * a3[12]) = 4;
      *((_QWORD *)v53 + 2 * a3[12] + 1) = &a11;
      *((_DWORD *)v53 + 4 * a3[19]) = 3;
      *((_DWORD *)v53 + 4 * a3[19] + 2) = *(_DWORD *)(*(_QWORD *)(v76 + 8) + 8LL);
      *((_DWORD *)v53 + 4 * a3[13]) = 3;
      *((_DWORD *)v53 + 4 * a3[13] + 2) = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v76 + 8) + 48LL) + 12LL);
      *((_DWORD *)v53 + 4 * a3[14]) = 3;
      *((_DWORD *)v53 + 4 * a3[14] + 2) = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v76 + 8) + 48LL) + 16LL);
      v77 = v147;
      if ( v147 )
      {
        if ( *(_DWORD *)(*(_QWORD *)(v147 + 48) + 12LL) == 131 )
        {
          ProfileIdFromPacketInbound = 0;
          if ( !v151 )
            goto LABEL_77;
          goto LABEL_65;
        }
        if ( v151 )
        {
LABEL_65:
          ProfileIdFromPacketInbound = WfpGetProfileIdFromPacketInbound(v147, v151, v151);
          v77 = v147;
          goto LABEL_77;
        }
        ProfileIdFromPacketInbound = *(_DWORD *)(v147 + 56);
      }
      else
      {
        ProfileIdFromPacketInbound = 0;
      }
LABEL_77:
      *v38 = ProfileIdFromPacketInbound;
      v82 = v151;
      AlepFillEdgeInterfaceRelatedFields(
        v77,
        (_DWORD)a3,
        v77,
        v151,
        0,
        0,
        0,
        a21,
        0,
        ProfileIdFromPacketInbound,
        0,
        (__int64)v53);
      if ( *((_DWORD *)v53 + 4 * a3[31]) )
        *v41 = *((_DWORD *)v53 + 4 * a3[31] + 2);
      v83 = (_DWORD **)v147;
      *((_DWORD *)v53 + 4 * a3[35]) = 4;
      *((_QWORD *)v53 + 2 * a3[35] + 1) = v83 + 10;
      if ( !v42[31] )
      {
        if ( v137 && a31 )
        {
          v101 = *(_QWORD *)(a31 + 488);
          v157 = (_DWORD *)(v101 + 224);
          v102 = *(_DWORD *)(v101 + 72);
          v99 = &v156;
          LODWORD(v156) = v102;
          *((_DWORD *)v53 + 4 * a3[9]) = 16;
          v100 = a3[9];
          goto LABEL_136;
        }
LABEL_137:
        v103 = v149;
        *((_DWORD *)v53 + 4 * a3[18]) = 3;
        *((_DWORD *)v53 + 4 * a3[18] + 2) = v103;
        if ( (SpinLock[6] & 0x2000) != 0 )
        {
          *((_DWORD *)v53 + 4 * a3[17]) = 3;
          *((_DWORD *)v53 + 4 * a3[17] + 2) = *((_DWORD *)SpinLock + 127);
        }
        *((_DWORD *)v53 + 4 * a3[40]) = 3;
        *((_DWORD *)v53 + 4 * a3[40] + 2) = **v83;
        v47 = *((_DWORD *)SpinLock + 170) == 1;
        v175 = 0;
        v174 = (unsigned __int64)v42;
        if ( v47 )
          v54[1] |= 0x80000u;
        *v54 |= 0x80u;
        v104 = v176;
        *((_QWORD *)v54 + 1) = &v174;
        *v54 |= 0x20u;
        v105 = a19;
        *((_QWORD *)v54 + 8) = *(_QWORD *)(SpinLock[60] + 32);
        *v54 |= 4u;
        v54[10] = v105;
        *v54 |= 0x400u;
        v54[11] = a20;
        *v54 |= 0x800u;
        v54[20] = **v83;
        if ( FeAcquireCompletionHandle(v104, &v153) )
          v153 = FeAcquireGenericCompletionHandle();
        *v54 |= 0x4000u;
        v106 = v143;
        *((_QWORD *)v54 + 13) = v153;
        v107 = SpinLock[60];
        LODWORD(Pool2) = 0;
        v172 = *(_QWORD *)(v107 + 16);
        LODWORD(v171) = *(unsigned __int16 *)(v107 + 10);
        *v54 |= 8u;
        *((_QWORD *)v54 + 6) = &v171;
        *v54 |= 0x10u;
        v108 = a22;
        *((_QWORD *)v54 + 7) = *(_QWORD *)(SpinLock[61] + 64);
        v54[70] = v108;
        *v54 |= 0x40000u;
        v54[35] = 1;
        *((_WORD *)SpinLock + 208) = v106;
        KfdGetLayerCacheEpoch(v106, &Pool2);
        *((_DWORD *)SpinLock + 102) = Pool2;
        if ( (SpinLock[6] & 0x40) == 0 )
          _InterlockedOr((volatile signed __int32 *)SpinLock + 12, 0x40u);
        KfdGetLayerCacheEpoch(v106, &v150);
        *v54 |= 0x8000u;
        v109 = a27;
        *((_QWORD *)v54 + 14) = *a27;
        if ( v109[6] )
        {
          *v54 |= 0x4000000u;
          *((_QWORD *)v54 + 24) = v109[6];
        }
        if ( *((_DWORD *)v109 + 2) )
        {
          *v54 |= 0x20000u;
          v54[30] = *((_DWORD *)v109 + 2);
        }
        if ( v109[2] )
        {
          *v54 |= 0x10000u;
          *((_QWORD *)v54 + 16) = v109[2];
          v54[34] = *((_DWORD *)v109 + 6);
        }
        if ( v109[4] )
        {
          *v54 |= 0x800000u;
          *((_QWORD *)v54 + 18) = v109[4];
          v54[38] = *((_DWORD *)v109 + 10);
        }
        WfpAleInitializeWaitRef_1(v42 + 16);
        WfpAleReferenceEndpointNoLock_0(v42);
        KfdAleInitializeFlowTable(v42 + 9, 0);
        if ( !KfdAleAcquireFlowHandleForFlow(SpinLock, v42, &v165) )
        {
          *v54 |= 2u;
          *((_QWORD *)v54 + 4) = v165;
          KfdAleReleaseFlowHandleForFlow(SpinLock);
        }
        v110 = a18;
        *((_BYTE *)v54 + 592) = *(_BYTE *)(SpinLock[61] + 152);
        *(_OWORD *)(v54 + 150) = *(_OWORD *)(SpinLock[61] + 160);
        *((_QWORD *)v54 + 77) = *(_QWORD *)(SpinLock[61] + 176);
        *(_OWORD *)(v54 + 162) = *(_OWORD *)(SpinLock[61] + 192);
        v134 = v179;
        *(_OWORD *)(v54 + 166) = *(_OWORD *)(SpinLock[61] + 208);
        v58 = WfpAleClassify((unsigned int)&v173, (_DWORD)v54, v82, v110, (__int64)v148, v134);
        if ( v58 )
          goto LABEL_202;
        v111 = 0;
        v112 = 0;
        if ( a28 )
        {
          _InterlockedOr((volatile signed __int32 *)v42 + 12, 0x4000000u);
        }
        else if ( a29 )
        {
          _InterlockedOr((volatile signed __int32 *)v42 + 12, 0x8000000u);
        }
        v113 = a4;
        if ( a4 == 2 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10000) != 0 )
          {
            v133 = (unsigned __int16)__ROR2__(v139, 8);
            WPP_SF__IPV4_d_IPV4_dd(
              WPP_GLOBAL_Control->AttachedDevice,
              v133,
              (unsigned __int16)__ROR2__(v142, 8),
              **(_QWORD **)(v144 + 16),
              v133,
              v160);
LABEL_169:
            v113 = a4;
          }
        }
        else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
               && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u
               && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10000) != 0 )
        {
          v114 = (unsigned __int16)__ROR2__(v142, 8);
          v115 = (unsigned __int16)__ROR2__(v139, 8);
          WPP_SF__IPV6_d_IPV6_dd(
            WPP_GLOBAL_Control->AttachedDevice,
            v115,
            v114,
            **(_QWORD **)(v144 + 16),
            v115,
            v160,
            v114,
            v145);
          goto LABEL_169;
        }
        if ( v159 && v159 != SpinLock )
          SpinLock = v159;
        if ( *(_DWORD *)(v144 + 24) == 1 )
        {
          if ( v54[84] )
            v111 = v54[86];
          v116 = 1;
          if ( v54[80] )
            v112 = v54[82] == 1;
        }
        else
        {
          v116 = 1;
        }
        if ( (SpinLock[6] & 0x40) != 0 && *(_DWORD *)(v144 + 24) == 1 && !v112 )
        {
          if ( v54[84] )
            v111 = v54[86];
          v117 = v163;
          inserted = WfpAleInsertRemoteEndpoint(
                       SpinLock,
                       v113,
                       v145,
                       v147,
                       v144,
                       v139,
                       (_DWORD *)v160,
                       v142,
                       v137,
                       v158,
                       v143,
                       v150,
                       0,
                       0,
                       v151,
                       (__int64)v42,
                       v111,
                       v149,
                       1,
                       0,
                       0,
                       (PKSPIN_LOCK *)v163,
                       (_BYTE *)v166);
          v57 = v135;
          v58 = inserted;
          if ( !inserted )
          {
            v119 = *(volatile signed __int32 **)(a26 + 16);
            *(_QWORD *)(*(_QWORD *)v117 + 288LL) = v119;
            _InterlockedIncrement(v119);
          }
          goto LABEL_203;
        }
        if ( (unsigned int)(*(_DWORD *)(v144 + 24) - 3) <= 1 || v112 )
        {
          LODWORD(Pool2) = 0;
          v179 = 0;
          v152 = *(_QWORD *)v158;
          if ( v113 == 2 )
          {
            v120 = &Pool2;
          }
          else
          {
            if ( v113 != 23 )
              goto LABEL_222;
            v120 = (__int64 *)&v179;
          }
          if ( v54[88] )
            v111 = v54[90];
          if ( !v112 )
            v116 = 4;
          LODWORD(v152) = 0;
          v58 = WfpAleInsertRemoteEndpoint(
                  SpinLock,
                  v113,
                  v145,
                  v147,
                  v144,
                  v139,
                  v120,
                  0,
                  v137,
                  (__int64)&v152,
                  v143,
                  v150,
                  0,
                  0,
                  v151,
                  (__int64)v42,
                  v111,
                  v149,
                  v116,
                  2 * v112,
                  0,
                  (PKSPIN_LOCK *)v163,
                  (_BYTE *)v166);
          if ( !v58 )
          {
            if ( (*((_DWORD *)SpinLock + 12) & 0x80u) == 0 )
              _InterlockedOr((volatile signed __int32 *)SpinLock + 12, 0x80u);
            if ( v112 )
            {
              v56 = v136;
              v57 = v135;
              if ( (*((_DWORD *)SpinLock + 13) & 0x40000) == 0 )
                _InterlockedOr((volatile signed __int32 *)SpinLock + 13, 0x40000u);
              goto LABEL_204;
            }
          }
        }
LABEL_202:
        v57 = v135;
LABEL_203:
        v56 = v136;
        goto LABEL_204;
      }
      v84 = 0;
      memset(&LockHandle, 0, sizeof(LockHandle));
      v152 = 0;
      v155 = 0;
      if ( !gAleDebugEnabled )
      {
        v91 = 0;
        goto LABEL_111;
      }
      v85 = 32;
      Entry = 0;
      Pool2 = ExAllocatePool2(64, 32, 1281715265);
      v86 = (_BYTE *)Pool2;
      if ( !Pool2 )
      {
        v84 = -1073741801;
        Entry = (PVOID)-1073741801LL;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
        {
          WPP_SF_sd(
            WPP_GLOBAL_Control->AttachedDevice,
            10,
            (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
            (unsigned int)"ExAllocatePool2",
            23);
        }
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
        {
          WPP_SF_sd(
            WPP_GLOBAL_Control->AttachedDevice,
            15,
            (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
            (unsigned int)"WfpPoolAllocNonPaged",
            23);
LABEL_110:
          v91 = Pool2;
LABEL_111:
          KeAcquireInStackQueuedSpinLock(v42, &LockHandle);
          while ( *((_DWORD *)v42 + 2) )
            ;
          v47 = gAleDebugEnabled == 1;
          v42[2] = (KSPIN_LOCK)KeGetCurrentThread();
          if ( v47 && !v84 )
            v42[3] = v91;
          v92 = v42[31];
          v93 = *(_DWORD *)v92;
          if ( *(_DWORD *)v92 )
          {
            v94 = *(_QWORD *)(v92 + 8);
            v95 = 0;
            do
            {
              v96 = 32LL * v95;
              v97 = *(_DWORD *)(v96 + v94 + 8);
              if ( v97 )
              {
                if ( v97 == 1 )
                  v155 = *(_DWORD **)(v96 + v94 + 24);
              }
              else
              {
                v152 = *(_QWORD *)(v96 + v94 + 24);
              }
              ++v95;
            }
            while ( v95 < v93 );
          }
          v98 = 0;
          v42[2] = 0;
          if ( gAleDebugEnabled == 1 )
          {
            v98 = (void *)v42[3];
            v42[3] = 0;
          }
          KeReleaseInStackQueuedSpinLock(&LockHandle);
          if ( gAleDebugEnabled == 1 && v98 )
            ExFreePoolWithTag(v98, 0);
          if ( v155 )
          {
            v157 = v155 + 56;
            LODWORD(v156) = v155[18];
            *((_DWORD *)v53 + 4 * a3[9]) = 16;
            *((_QWORD *)v53 + 2 * a3[9] + 1) = &v156;
          }
          v83 = (_DWORD **)v147;
          v82 = v151;
          if ( v152 )
          {
            v170 = v152 + 224;
            v99 = &v169;
            LODWORD(v169) = *(_DWORD *)(v152 + 72);
            *((_DWORD *)v53 + 4 * a3[10]) = 16;
            v100 = a3[10];
LABEL_136:
            *((_QWORD *)v53 + 2 * v100 + 1) = v99;
            goto LABEL_137;
          }
          goto LABEL_137;
        }
        v86 = (_BYTE *)Pool2;
      }
      if ( !v84 )
      {
        v87 = 2147483646;
        v88 = "WfpAleQueryPeerTokenInformation";
        do
        {
          if ( !v87 )
            break;
          if ( !*v88 )
            break;
          *v86++ = *v88++;
          --v87;
          --v85;
        }
        while ( v85 );
        v89 = 122;
        if ( v85 )
          v89 = 0;
        v90 = v86 - 1;
        if ( v85 )
          v90 = v86;
        *v90 = 0;
        if ( !v85 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
          {
            WPP_SF_sd(
              WPP_GLOBAL_Control->AttachedDevice,
              13,
              (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
              (unsigned int)"StringCchCopyA",
              v89);
          }
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
          {
            WPP_SF_sd(
              WPP_GLOBAL_Control->AttachedDevice,
              15,
              (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
              (unsigned int)"WfpStringCchCopyA",
              v89);
          }
        }
        v84 = (__int64)Entry;
      }
      goto LABEL_110;
    }
    v55 = (char *)gIncomingValuesLookasideList
        + 128 * (unsigned __int64)(unsigned int)(HIDWORD(KeGetPcr()[1].LockArray) + 1);
    if ( !v55[176] )
      PplpLazyInitializeLookasideList(gIncomingValuesLookasideList, v55 + 64);
    ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v55 + 64), Entry);
  }
  v56 = v136;
  v53 = 0;
  v57 = v135;
  v54 = 0;
  v138 = 0;
  if ( v136 )
    WfpLowerIrqlFromDispatchLevel(v135);
  v58 = -1073741670;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
  {
    WPP_SF_sd(
      WPP_GLOBAL_Control->AttachedDevice,
      10,
      (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
      (unsigned int)"WfpAlepAuthorizeReceive",
      154);
  }
LABEL_204:
  if ( v153 )
  {
    FeReleaseCompletionHandle();
    v153 = 0;
  }
  if ( Size[1] )
  {
    ExFreePoolWithTag((PVOID)Size[1], 0);
    Size[1] = 0;
    LODWORD(Size[0]) = 0;
  }
  if ( v42[31] )
    WfpAlepFreePeerTokenInformation();
  v121 = v42[32];
  if ( v121 )
  {
    if ( *(_BYTE *)(v121 + 72) )
    {
      WfpAleReleasePeerInformation();
    }
    else if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v121 + 24), 0xFFFFFFFF) == 1 )
    {
      WfpAlepFreePeerInformation();
    }
    v42[32] = 0;
  }
  if ( v42[12] )
    KfdAleNotifyFlowDeletion(v42 + 9);
  v122 = v159;
  if ( v159 )
  {
    if ( gAleDebugEnabled )
    {
      v123 = v159[19];
      if ( v123 != 0xBADBADFABADBADFAuLL && _InterlockedDecrement((volatile signed __int32 *)(v123 + 48)) < 0 )
LABEL_222:
        __fastfail(5u);
    }
    v144 = (__int64)(v122 + 16);
    v124 = *((_BYTE *)v122 + 132);
    do
    {
      v126 = *(_DWORD *)v144 & 3 | (4 * (*(_DWORD *)v144 >> 2) - 4);
      if ( v124 && v126 < 4 )
        v126 |= 2u;
      v125 = *(_DWORD *)v144;
    }
    while ( v125 != _InterlockedCompareExchange((volatile signed __int32 *)v144, v126, v125) );
    if ( v126 < 4 && (v126 & 3) != 1 )
    {
      v127 = *(void **)(v144 + 24);
      (*(void (__fastcall **)(_QWORD))(v144 + 16))(*(_QWORD *)(v144 + 8));
      if ( gAleDebugEnabled )
      {
        if ( v127 != (void *)0xBADBADFABADBADFALL && v127 )
          ExFreePoolWithTag(v127, 0);
      }
    }
  }
  HIDWORD(v128) = HIDWORD(v164);
  if ( v164 )
    v128 = IppDereferenceLocalAddress(v164);
  if ( v138 )
  {
    LODWORD(v128) = HIDWORD(KeGetPcr()[1].LockArray);
    v129 = (PVOID *)((char *)gPerProcessorContext + 72 * v128);
    KfdReleaseTerminatingFilters(v54 + 156);
    if ( v53 == v129[3] )
    {
      *((_BYTE *)v129 + 32) = 0;
    }
    else
    {
      v130 = (char *)gMetadataLookasideList
           + 128 * (unsigned __int64)(unsigned int)(HIDWORD(KeGetPcr()[1].LockArray) + 1);
      if ( !v130[176] )
        PplpLazyInitializeLookasideList(gMetadataLookasideList, v130 + 64);
      ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v130 + 64), v54);
      v131 = (char *)gIncomingValuesLookasideList
           + 128 * (unsigned __int64)(unsigned int)(HIDWORD(KeGetPcr()[1].LockArray) + 1);
      if ( !v131[176] )
        PplpLazyInitializeLookasideList(gIncomingValuesLookasideList, v131 + 64);
      ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v131 + 64), v53);
    }
    if ( v56 )
      WfpLowerIrqlFromDispatchLevel(v57);
  }
  if ( v58
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
  {
    WPP_SF_sd(
      WPP_GLOBAL_Control->AttachedDevice,
      15,
      (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
      (unsigned int)"WfpAlepAuthorizeReceive",
      v58);
  }
  return v58;
}

```

## disassembly

```asm
0x14013e520  push    rbp
0x14013e522  push    rbx
0x14013e523  push    rsi
0x14013e524  push    rdi
0x14013e525  push    r12
0x14013e527  push    r13
0x14013e529  push    r14
0x14013e52b  push    r15
0x14013e52d  lea     rbp, [rsp-148h]
0x14013e535  sub     rsp, 288h
0x14013e53c  mov     rax, cs:__security_cookie
0x14013e543  xor     rax, rsp
0x14013e546  mov     [rbp+180h+var_50], rax
0x14013e54d  mov     rax, [rbp+180h+arg_70]
0x14013e554  xor     ebx, ebx
0x14013e556  mov     rdi, [rbp+180h+arg_B0]
0x14013e55d  xorps   xmm0, xmm0
0x14013e560  mov     rsi, [rbp+180h+arg_110]
0x14013e567  mov     r14, rcx
0x14013e56a  mov     rcx, [rbp+180h+arg_100]
0x14013e571  mov     r15, r8
0x14013e574  mov     r12, [rbp+180h+arg_118]
0x14013e57b  mov     r13, [rbp+180h+SpinLock]
0x14013e582  mov     [rbp+180h+var_178], rax
0x14013e586  mov     eax, [rbp+180h+arg_20]
0x14013e58c  mov     [rbp+180h+var_1E0], eax
0x14013e58f  mov     rax, [rbp+180h+arg_30]
0x14013e596  mov     [rbp+180h+var_1E8], rax
0x14013e59a  movzx   eax, [rbp+180h+arg_40]
0x14013e5a1  mov     [rbp+180h+var_1FC], ax
0x14013e5a5  mov     rax, [rbp+180h+arg_58]
0x14013e5ac  mov     [rbp+180h+var_168], rax
0x14013e5b0  movzx   eax, [rbp+180h+arg_68]
0x14013e5b7  mov     [rbp+180h+var_1F0], ax
0x14013e5bb  mov     rax, [rbp+180h+arg_78]
0x14013e5c2  mov     [rbp+180h+var_D8], rax
0x14013e5c9  movzx   eax, [rbp+180h+arg_80]
0x14013e5d0  mov     [rbp+180h+var_1FE], al
0x14013e5d3  mov     eax, [rbp+180h+arg_B8]
0x14013e5d9  mov     [rbp+180h+var_1C4], eax
0x14013e5dc  mov     rax, [rbp+180h+arg_F8]
0x14013e5e3  mov     qword ptr [rbp+180h+var_60], rax
0x14013e5ea  mov     rax, [rbp+180h+arg_108]
0x14013e5f1  mov     [rbp+180h+var_138], rax
0x14013e5f5  xor     eax, eax
0x14013e5f7  mov     [rbp+180h+var_1FA], r9w
0x14013e5fc  mov     r9, [rbp+180h+arg_28]
0x14013e603  mov     [rbp+180h+var_150], rcx
0x14013e607  mov     [rcx], rbx
0x14013e60a  mov     rcx, rdi
0x14013e60d  mov     qword ptr [rbp+180h+var_12C], rax
0x14013e611  mov     qword ptr [rbp+180h+var_15C], rax
0x14013e615  mov     qword ptr [rbp+180h+var_184], rax
0x14013e619  mov     qword ptr [rbp+180h+var_11C], rax
0x14013e61d  mov     qword ptr [rbp+180h+var_10C], rax
0x14013e621  mov     [rbp+50h], rax
0x14013e625  mov     [rbp+20h], rax
0x14013e629  mov     [rbp-8], rax
0x14013e62d  mov     [rbp+60h], rax
0x14013e631  mov     [rbp+70h], rax
0x14013e635  mov     [rbp+180h+var_1EE], dx
0x14013e639  mov     [rbp+180h+var_1D0], r9
0x14013e63d  mov     [rbp+180h+var_1B8], rdi
0x14013e641  mov     [rbp+180h+var_1B0], rsi
0x14013e645  mov     [rbp+180h+var_190], r12
0x14013e649  mov     [rbp+180h+var_170], rbx
0x14013e64d  mov     [rbp+180h+var_148], rbx
0x14013e651  mov     [rbp+180h+var_1C0], ebx
0x14013e654  mov     [rbp+180h+Entry], rbx
0x14013e658  movups  xmmword ptr [rbp+180h+Size], xmm0
0x14013e65c  mov     [rbp+180h+var_1F8], rbx
0x14013e660  movups  [rbp+180h+var_100], xmm0
0x14013e667  mov     [rbp+180h+var_1FF], al
0x14013e66a  mov     [rbp+180h+var_200], al
0x14013e66d  movups  [rbp+180h+var_F0], xmm0
0x14013e674  mov     [rbp+180h+var_E0], rax
0x14013e67b  mov     [rbp+180h+var_140], rbx
0x14013e67f  mov     [rbp+180h+var_1A8], rbx
0x14013e683  call    cs:__imp_WfpNblInfoGet
0x14013e68a  nop     dword ptr [rax+rax+00h]
0x14013e68f  mov     rdx, rax
0x14013e692  test    rax, rax
0x14013e695  jz      short loc_14013E6AC
0x14013e697  mov     rax, cs:MmBadPointer
0x14013e69e  mov     rcx, [rax]
0x14013e6a1  cmp     rdx, rcx
0x14013e6a4  jz      short loc_14013E6AC
0x14013e6a6  mov     rbx, [rdx+8]
0x14013e6aa  jmp     short loc_14013E6BE
0x14013e6ac  mov     rax, cs:MmBadPointer
0x14013e6b3  mov     rcx, [rax]
0x14013e6b6  cmp     rdx, rcx
0x14013e6b9  jnz     short loc_14013E6BE
0x14013e6bb  mov     rbx, rcx
0x14013e6be  test    rdi, rdi
0x14013e6c1  jz      loc_14013E7F1
0x14013e6c7  test    rbx, rbx
0x14013e6ca  jz      loc_14013E7F1
0x14013e6d0  cmp     rbx, rcx
0x14013e6d3  jz      loc_14013E7F1
0x14013e6d9  xorps   xmm0, xmm0
0x14013e6dc  lea     rdx, [rbp+180h+Source2]; Source2
0x14013e6e3  mov     r8d, 50h ; 'P'; Length
0x14013e6e9  lea     rcx, [rbx+0B8h]; Source1
0x14013e6f0  movups  [rbp+180h+Source2], xmm0
0x14013e6f7  movups  [rbp+180h+var_A0], xmm0
0x14013e6fe  movups  [rbp+180h+var_90], xmm0
0x14013e705  movups  [rbp+180h+var_80], xmm0
0x14013e70c  movups  [rbp+180h+var_70], xmm0
0x14013e713  call    cs:__imp_RtlCompareMemory
0x14013e71a  nop     dword ptr [rax+rax+00h]
0x14013e71f  cmp     rax, 50h ; 'P'
0x14013e723  jz      short loc_14013E73F
0x14013e725  lea     rdx, [r13+0A8h]
0x14013e72c  lea     rcx, [rbx+0B8h]
0x14013e733  call    WfpAleTransferAleIpsecContext
0x14013e738  lock dec cs:gAleASyncCount
0x14013e73f  cmp     qword ptr [rbx+140h], 0
0x14013e747  jz      loc_14013E7F1
0x14013e74d  cmp     [rbp+180h+var_1FA], 2
0x14013e752  mov     r9, [rbp+180h+var_1E8]
0x14013e756  mov     rax, [r9+10h]
0x14013e75a  mov     rdx, [rax]; Source2
0x14013e75d  mov     rax, [rbx+130h]
0x14013e764  mov     rcx, [rax+10h]
0x14013e768  mov     rcx, [rcx]; Source1
0x14013e76b  jnz     short loc_14013E785
0x14013e76d  mov     r8d, 4; Length
0x14013e773  call    cs:__imp_RtlCompareMemory
0x14013e77a  nop     dword ptr [rax+rax+00h]
0x14013e77f  cmp     rax, 4
0x14013e783  jmp     short loc_14013E79B
0x14013e785  mov     r8d, 10h; Length
0x14013e78b  call    cs:__imp_RtlCompareMemory
0x14013e792  nop     dword ptr [rax+rax+00h]
0x14013e797  cmp     rax, 10h
0x14013e79b  jz      short loc_14013E7A8
0x14013e79d  mov     rax, [rbx+130h]
0x14013e7a4  mov     [rbp+180h+var_1E8], rax
0x14013e7a8  movzx   eax, word ptr [rbx+138h]
0x14013e7af  movzx   edi, [rbp+180h+var_1FC]
0x14013e7b3  mov     rdx, [rbx+130h]
0x14013e7ba  cmp     di, ax
0x14013e7bd  mov     qword ptr [rbx+130h], 0
0x14013e7c8  cmovnz  di, ax
0x14013e7cc  mov     [rbp+180h+var_148], rdx
0x14013e7d0  mov     rax, [rbx+140h]
0x14013e7d7  mov     qword ptr [rbx+140h], 0
0x14013e7e2  lock dec cs:gAleASyncCount
0x14013e7e9  mov     [rbp+180h+var_170], rax
0x14013e7ed  mov     [rbp+180h+var_1FC], di
0x14013e7f1  call    cs:__imp_KeGetCurrentIrql
0x14013e7f8  nop     dword ptr [rax+rax+00h]
0x14013e7fd  cmp     al, 2
0x14013e7ff  jnb     short loc_14013E80D
0x14013e801  call    WfpRaiseIrqlToDispatchLevel
0x14013e806  mov     [rbp+180h+var_200], al
0x14013e809  mov     [rbp+180h+var_1FF], 1
0x14013e80d  mov     ecx, gs:1A4h
0x14013e815  lea     r8, [rcx+rcx*8]
0x14013e819  mov     rcx, cs:gPerProcessorContext
0x14013e820  cmp     byte ptr [rcx+r8*8+20h], 0
0x14013e826  jnz     short loc_14013E83D
0x14013e828  mov     rdi, [rcx+r8*8+18h]
0x14013e82d  mov     rbx, [rcx+r8*8+10h]
0x14013e832  mov     byte ptr [rcx+r8*8+20h], 1
0x14013e838  jmp     loc_14013E931
0x14013e83d  mov     rcx, cs:gIncomingValuesLookasideList
0x14013e844  lea     rdx, [rbp+180h+Entry]
0x14013e848  call    WfpAllocateFromPerProcessorLookasideList
0x14013e84d  test    rax, rax
0x14013e850  jnz     short loc_14013E8AF
0x14013e852  mov     rcx, cs:gMetadataLookasideList
0x14013e859  lea     rdx, [rbp+180h+var_1F8]
0x14013e85d  call    WfpAllocateFromPerProcessorLookasideList
0x14013e862  test    rax, rax
0x14013e865  jz      loc_14013E929
0x14013e86b  mov     eax, gs:1A4h
0x14013e873  mov     r8, cs:gIncomingValuesLookasideList
0x14013e87a  lea     ebx, [rax+1]
0x14013e87d  shl     rbx, 7
0x14013e881  add     rbx, r8
0x14013e884  movzx   eax, byte ptr [rbx+0B0h]
0x14013e88b  test    al, al
0x14013e88d  jnz     short loc_14013E89B
0x14013e88f  lea     rdx, [rbx+40h]
0x14013e893  mov     rcx, r8
0x14013e896  call    PplpLazyInitializeLookasideList
0x14013e89b  mov     rdx, [rbp+180h+Entry]; Entry
0x14013e89f  lea     rcx, [rbx+40h]; Lookaside
0x14013e8a3  call    cs:__imp_ExFreeToLookasideListEx
0x14013e8aa  nop     dword ptr [rax+rax+00h]
0x14013e8af  movzx   r15d, [rbp+180h+var_1FF]
0x14013e8b4  xor     edi, edi
0x14013e8b6  movzx   r12d, [rbp+180h+var_200]
0x14013e8bb  mov     ebx, edi
0x14013e8bd  mov     [rbp+180h+var_1FD], dil
0x14013e8c1  test    r15b, r15b
0x14013e8c4  jz      short loc_14013E8CF
0x14013e8c6  movzx   ecx, r12b
0x14013e8ca  call    WfpLowerIrqlFromDispatchLevel
0x14013e8cf  mov     rcx, cs:WPP_GLOBAL_Control
0x14013e8d6  lea     rax, WPP_GLOBAL_Control
0x14013e8dd  mov     rsi, 0FFFFFFFFC000009Ah
0x14013e8e4  cmp     rcx, rax
0x14013e8e7  jz      loc_14013F953
0x14013e8ed  cmp     byte ptr [rcx+29h], 2
0x14013e8f1  jb      loc_14013F953
0x14013e8f7  test    dword ptr [rcx+2Ch], 1000h
0x14013e8fe  jz      loc_14013F953
0x14013e904  mov     rcx, [rcx+18h]
0x14013e908  lea     r9, aWfpalepauthori_5; "WfpAlepAuthorizeReceive"
0x14013e90f  mov     edx, 0Ah
0x14013e914  mov     dword ptr [rsp+2C0h+var_2A0], esi
0x14013e918  lea     r8, WPP_dc97c17fd6903ad537f842808d057dba_Traceguids
0x14013e91f  call    WPP_SF_sd
0x14013e924  jmp     loc_14013F953
0x14013e929  mov     rdi, [rbp+180h+Entry]
0x14013e92d  mov     rbx, [rbp+180h+var_1F8]
0x14013e931  xor     edx, edx; Val
0x14013e933  mov     [rbp+180h+var_1FD], 1
0x14013e937  mov     r8d, 2A0h; Size
0x14013e93d  mov     rcx, rdi; void *
0x14013e940  call    memset
0x14013e945  xor     edx, edx; Val
0x14013e947  mov     r8d, 2A8h; Size
0x14013e94d  mov     rcx, rbx; void *
0x14013e950  call    memset
0x14013e955  lea     rax, [rbx+270h]
0x14013e95c  mov     [rax+8], rax
0x14013e960  lea     rdx, gAleNullSid
0x14013e967  mov     [rax], rax
0x14013e96a  mov     rcx, [r14+1E0h]
0x14013e971  movzx   eax, [rbp+180h+var_1EE]
0x14013e975  mov     word ptr [rbp+180h+var_100], ax
0x14013e97c  movzx   eax, word ptr [r15]
0x14013e980  mov     dword ptr [rbp+180h+var_100+4], eax
0x14013e986  mov     qword ptr [rbp+180h+var_100+8], rdi
0x14013e98d  mov     rax, [rcx+10h]
0x14013e991  mov     qword ptr [rbp+180h+var_12C+4], rax
0x14013e995  movzx   eax, word ptr [rcx+0Ah]
0x14013e999  lea     rcx, [rbp+180h+var_130]
0x14013e99d  mov     [rbp+180h+var_130], eax
0x14013e9a0  movzx   eax, word ptr [r15+2]
0x14013e9a5  add     rax, rax
0x14013e9a8  mov     dword ptr [rdi+rax*8], 0Ch
0x14013e9af  movzx   eax, word ptr [r15+2]
0x14013e9b4  add     rax, rax
0x14013e9b7  mov     [rdi+rax*8+8], rcx
0x14013e9bc  mov     rcx, [r14+1E8h]
0x14013e9c3  lea     rax, [rcx+0E0h]
0x14013e9ca  mov     qword ptr [rbp+180h+var_15C+4], rax
0x14013e9ce  mov     eax, [rcx+48h]
0x14013e9d1  lea     rcx, [rbp+180h+var_160]
0x14013e9d5  mov     [rbp+180h+var_160], eax
0x14013e9d8  movzx   eax, word ptr [r15+4]
0x14013e9dd  add     rax, rax
0x14013e9e0  mov     dword ptr [rdi+rax*8], 10h
0x14013e9e7  movzx   eax, word ptr [r15+4]
0x14013e9ec  add     rax, rax
0x14013e9ef  mov     [rdi+rax*8+8], rcx
0x14013e9f4  mov     rax, [r14+1E8h]
0x14013e9fb  mov     rcx, [rax+118h]
0x14013ea02  movzx   eax, word ptr [r15+4Ah]
0x14013ea07  test    rcx, rcx
0x14013ea0a  cmovnz  rdx, rcx
0x14013ea0e  add     rax, rax
0x14013ea11  lea     rcx, [rbp+180h+var_160]
0x14013ea15  mov     dword ptr [rdi+rax*8], 0Dh
0x14013ea1c  movzx   eax, word ptr [r15+4Ah]
0x14013ea21  add     rax, rax
0x14013ea24  mov     [rdi+rax*8+8], rdx
0x14013ea29  movzx   eax, word ptr [r15+52h]
0x14013ea2e  add     rax, rax
0x14013ea31  mov     dword ptr [rdi+rax*8], 10h
0x14013ea38  movzx   eax, word ptr [r15+52h]
0x14013ea3d  add     rax, rax
0x14013ea40  mov     [rdi+rax*8+8], rcx
0x14013ea45  mov     rax, [r14+1E8h]
0x14013ea4c  mov     rax, [rax+90h]
0x14013ea53  test    rax, rax
0x14013ea56  jz      short loc_14013EACB
0x14013ea58  mov     rax, [rax+8]
0x14013ea5c  lea     r8, [rbp+180h+Size+8]
0x14013ea60  mov     edx, 63716641h
0x14013ea65  mov     r12, [rax+20h]
0x14013ea69  movzx   eax, word ptr [r12+8]
0x14013ea6f  add     ax, 2
0x14013ea73  movzx   eax, ax
0x14013ea76  mov     dword ptr [rbp+180h+var_1F8], eax
0x14013ea79  add     eax, 8
0x14013ea7c  mov     ecx, eax
0x14013ea7e  mov     dword ptr [rbp+180h+Size], eax
0x14013ea81  call    WfpPoolAllocNonPaged
0x14013ea86  mov     rsi, rax
0x14013ea89  test    rax, rax
0x14013ea8c  jnz     loc_14013F949
0x14013ea92  mov     r8d, dword ptr [rbp+180h+Size]; Size
0x14013ea96  xor     edx, edx; Val
0x14013ea98  mov     rcx, [rbp+180h+Size+8]; void *
  ... truncated ...
```
