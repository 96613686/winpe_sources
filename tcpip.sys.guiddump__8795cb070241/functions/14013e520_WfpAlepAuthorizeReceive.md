# WfpAlepAuthorizeReceive

- ea: `0x14013e520`
- end: `0x14013fc26`
- name: `WfpAlepAuthorizeReceive`
- size: `5894`
- prototype: `__int64 __fastcall(PKSPIN_LOCK SpinLock, __int16, unsigned __int16 *, __int16, int, __int64, __int64, _OWORD *, __int16, char, char, __int64, _OWORD *, __int16, __int64, __int64, char, unsigned __int8, int, int, int, int, __int64, int, PKSPIN_LOCK SpinLocka, __int64, _QWORD *, char, char, char, __int64, __int64, _QWORD *, __int64, _DWORD *, _DWORD *)`
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
        __int16 a2,
        unsigned __int16 *a3,
        __int16 a4,
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
  __int64 v55; // r8
  __int64 v56; // r9
  char *v57; // rbx
  char v58; // r15
  unsigned __int8 v59; // r12
  __int64 v60; // rsi
  __int64 *v61; // rdx
  KSPIN_LOCK v62; // rcx
  KSPIN_LOCK v63; // rcx
  __int64 v64; // rax
  __int64 v65; // r12
  size_t v66; // r8
  int v67; // r10d
  PKSPIN_LOCK v68; // rdx
  int v69; // r8d
  _OWORD *v70; // rax
  PKSPIN_LOCK v71; // rcx
  int v72; // r8d
  int v73; // edx
  int v74; // ecx
  int v75; // eax
  int v76; // ecx
  __int16 v77; // cx
  __int64 v78; // rdx
  int v79; // ecx
  int ProfileIdFromPacketInbound; // eax
  __int64 v81; // r8
  unsigned int v82; // eax
  int v83; // ecx
  int v84; // esi
  _DWORD **v85; // r8
  __int64 v86; // r12
  __int64 v87; // rsi
  _BYTE *v88; // rcx
  __int64 v89; // rdx
  const char *v90; // r8
  char v91; // r12
  _BYTE *v92; // rax
  __int64 v93; // rsi
  KSPIN_LOCK v94; // rax
  unsigned int v95; // r8d
  __int64 v96; // r9
  unsigned int v97; // ecx
  __int64 v98; // rax
  int v99; // edx
  void *v100; // rsi
  __int64 *v101; // rcx
  __int64 v102; // rax
  __int64 v103; // rcx
  int v104; // eax
  int v105; // ecx
  __int64 v106; // rcx
  int v107; // eax
  unsigned __int16 v108; // r15
  KSPIN_LOCK v109; // rcx
  int v110; // eax
  _QWORD *v111; // rcx
  int v112; // r9d
  int v113; // r12d
  bool v114; // r15
  __int16 v115; // r10
  int v116; // r8d
  int v117; // edx
  char v118; // r9
  __int64 v119; // r15
  __int64 inserted; // rax
  volatile signed __int32 *v121; // rcx
  __int64 *v122; // rdx
  KSPIN_LOCK v123; // rcx
  KSPIN_LOCK *v124; // rcx
  KSPIN_LOCK v125; // rax
  char v126; // r9
  signed __int32 v127; // edx
  unsigned __int32 v128; // ecx
  void *v129; // r14
  __int64 v130; // rax
  PVOID *v131; // r14
  __int64 v132; // r8
  __int64 v133; // r9
  char *v134; // r14
  __int64 v135; // r8
  __int64 v136; // r9
  char *v137; // rbx
  int v139; // [rsp+20h] [rbp-120h]
  __int64 v140; // [rsp+28h] [rbp-118h]
  unsigned __int8 v141; // [rsp+C0h] [rbp-80h]
  char v142; // [rsp+C1h] [rbp-7Fh]
  char v143; // [rsp+C2h] [rbp-7Eh]
  char v144; // [rsp+C3h] [rbp-7Dh]
  __int16 v145; // [rsp+C4h] [rbp-7Ch]
  __int64 Pool2; // [rsp+C8h] [rbp-78h] BYREF
  __int16 v148; // [rsp+D0h] [rbp-70h]
  __int16 v149; // [rsp+D2h] [rbp-6Eh]
  __int64 v150; // [rsp+D8h] [rbp-68h]
  int v151; // [rsp+E0h] [rbp-60h]
  PVOID Entry; // [rsp+E8h] [rbp-58h] BYREF
  __int64 v153; // [rsp+F0h] [rbp-50h]
  char v154[4]; // [rsp+F8h] [rbp-48h] BYREF
  int v155; // [rsp+FCh] [rbp-44h]
  int v156; // [rsp+100h] [rbp-40h] BYREF
  __int64 v157; // [rsp+108h] [rbp-38h]
  __int64 v158; // [rsp+110h] [rbp-30h] BYREF
  __int64 v159; // [rsp+118h] [rbp-28h] BYREF
  size_t Size[2]; // [rsp+120h] [rbp-20h] BYREF
  _DWORD *v161; // [rsp+130h] [rbp-10h]
  __int64 v162; // [rsp+138h] [rbp-8h] BYREF
  _DWORD *v163; // [rsp+140h] [rbp+0h]
  __int64 v164; // [rsp+148h] [rbp+8h]
  KSPIN_LOCK *v165; // [rsp+150h] [rbp+10h]
  __int64 v166; // [rsp+158h] [rbp+18h]
  __int64 v167; // [rsp+160h] [rbp+20h] BYREF
  KSPIN_LOCK v168; // [rsp+168h] [rbp+28h]
  __int64 v169; // [rsp+170h] [rbp+30h]
  __int64 v170; // [rsp+178h] [rbp+38h]
  __int64 v171; // [rsp+180h] [rbp+40h] BYREF
  __int64 v172; // [rsp+188h] [rbp+48h]
  __int64 v173; // [rsp+190h] [rbp+50h] BYREF
  __int64 v174; // [rsp+198h] [rbp+58h]
  __int64 v175; // [rsp+1A0h] [rbp+60h] BYREF
  __int64 v176; // [rsp+1A8h] [rbp+68h]
  __int64 v177; // [rsp+1B0h] [rbp+70h] BYREF
  __int64 v178; // [rsp+1B8h] [rbp+78h]
  __int128 v179; // [rsp+1C0h] [rbp+80h] BYREF
  __int128 v180; // [rsp+1D0h] [rbp+90h] BYREF
  __int64 v181; // [rsp+1E0h] [rbp+A0h]
  __int64 v182; // [rsp+1E8h] [rbp+A8h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+1F0h] [rbp+B0h] BYREF
  _OWORD Source2[5]; // [rsp+210h] [rbp+D0h] BYREF
  __int128 v185; // [rsp+260h] [rbp+120h] BYREF

  v36 = 0;
  v37 = a23;
  v38 = a35;
  v41 = a36;
  v42 = SpinLocka;
  v164 = a15;
  v151 = a5;
  v150 = a7;
  v145 = a9;
  v166 = a12;
  v148 = a14;
  v182 = a16;
  v143 = a17;
  v155 = a24;
  *(_QWORD *)&v185 = a32;
  v172 = a34;
  v169 = (__int64)a33;
  *a33 = 0;
  LODWORD(v174) = 0;
  LODWORD(v168) = 0;
  LODWORD(v163) = 0;
  LODWORD(v176) = 0;
  LODWORD(v178) = 0;
  v173 = 0;
  v167 = 0;
  v162 = 0;
  v175 = 0;
  v177 = 0;
  v149 = a2;
  v153 = a6;
  v157 = v37;
  v158 = (__int64)v38;
  v161 = v41;
  v165 = 0;
  v170 = 0;
  v156 = 0;
  Entry = 0;
  *(_OWORD *)Size = 0;
  Pool2 = 0;
  v179 = 0;
  v142 = 0;
  v141 = 0;
  v180 = 0;
  v181 = 0;
  v171 = 0;
  v159 = 0;
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
      v45 = **(const void ***)(v150 + 16);
      v46 = **(const void ***)(v36[38] + 16LL);
      if ( a4 == 2 )
        v47 = RtlCompareMemory(v46, v45, 4u) == 4;
      else
        v47 = RtlCompareMemory(v46, v45, 0x10u) == 16;
      if ( !v47 )
        v150 = v36[38];
      v48 = *((_WORD *)v36 + 156);
      v49 = a9;
      v50 = v36[38];
      v36[38] = 0;
      if ( a9 != v48 )
        v49 = v48;
      v170 = v50;
      v51 = (KSPIN_LOCK *)v36[40];
      v36[40] = 0;
      _InterlockedDecrement(&gAleASyncCount);
      v165 = v51;
      v145 = v49;
    }
  }
  if ( KeGetCurrentIrql() < 2u )
  {
    v141 = WfpRaiseIrqlToDispatchLevel();
    v142 = 1;
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
      v144 = 1;
      memset(v53, 0, 0x2A0u);
      memset(v54, 0, 0x2A8u);
      *((_QWORD *)v54 + 79) = v54 + 156;
      v61 = gAleNullSid;
      *((_QWORD *)v54 + 78) = v54 + 156;
      v62 = SpinLock[60];
      LOWORD(v179) = v149;
      DWORD1(v179) = *a3;
      *((_QWORD *)&v179 + 1) = v53;
      v174 = *(_QWORD *)(v62 + 16);
      LODWORD(v173) = *(unsigned __int16 *)(v62 + 10);
      *((_DWORD *)v53 + 4 * a3[1]) = 12;
      *((_QWORD *)v53 + 2 * a3[1] + 1) = &v173;
      v63 = SpinLock[61];
      v168 = v63 + 224;
      LODWORD(v167) = *(_DWORD *)(v63 + 72);
      *((_DWORD *)v53 + 4 * a3[2]) = 16;
      *((_QWORD *)v53 + 2 * a3[2] + 1) = &v167;
      if ( *(_QWORD *)(SpinLock[61] + 280) )
        v61 = *(__int64 **)(SpinLock[61] + 280);
      *((_DWORD *)v53 + 4 * a3[37]) = 13;
      *((_QWORD *)v53 + 2 * a3[37] + 1) = v61;
      *((_DWORD *)v53 + 4 * a3[41]) = 16;
      *((_QWORD *)v53 + 2 * a3[41] + 1) = &v167;
      v64 = *(_QWORD *)(SpinLock[61] + 144);
      if ( v64 )
      {
        v65 = *(_QWORD *)(*(_QWORD *)(v64 + 8) + 32LL);
        LODWORD(Pool2) = (unsigned __int16)(*(_WORD *)(v65 + 8) + 2);
        LODWORD(Size[0]) = Pool2 + 8;
        v60 = WfpPoolAllocNonPaged((unsigned int)(Pool2 + 8), 1668376129, &Size[1]);
        if ( v60 )
          goto LABEL_202;
        memset((void *)Size[1], 0, LODWORD(Size[0]));
        v66 = (unsigned __int16)Pool2;
        *(_QWORD *)Size[1] = *(_QWORD *)v65;
        memmove((void *)(Size[1] + 8), *(const void **)(v65 + 16), v66);
        v38 = (_DWORD *)v158;
        v41 = v161;
      }
      v67 = v151;
      v68 = v42 + 21;
      v69 = 0;
      *((_DWORD *)v53 + 4 * a3[38]) = 12;
      *((_QWORD *)v53 + 2 * a3[38] + 1) = Size;
      v70 = a13;
      *((_OWORD *)v53 + a3[3]) = *a8;
      *((_OWORD *)v53 + a3[7]) = *v70;
      v71 = v42 + 21;
      *((_DWORD *)v53 + 4 * a3[6]) = 1;
      *((_BYTE *)v53 + 16 * a3[6] + 8) = v67;
      if ( !v42 )
        v71 = 0;
      *((_DWORD *)v53 + 4 * a3[16]) = 3;
      if ( v71 )
      {
        if ( v42 )
        {
          v72 = *((_DWORD *)v42 + 50);
        }
        else
        {
          LOBYTE(v72) = MEMORY[0x20];
          v68 = 0;
        }
        v69 = 2 * (v72 & 1);
        if ( (v68[4] & 0x800) != 0 )
          v69 |= 0x10000u;
      }
      v73 = v69 | 1;
      if ( !v143 )
        v73 = v69;
      if ( (SpinLock[6] & 0x10) != 0 )
        v73 |= 0x10u;
      v74 = v73 | 0x400000;
      if ( !a28 )
        v74 = v73;
      v75 = v74 | 0x800000;
      if ( !a29 )
        v75 = v74;
      v76 = v75 | 0x1000000;
      if ( !a30 )
        v76 = v75;
      *((_DWORD *)v53 + 4 * a3[16] + 2) = v76;
      if ( a4 == 2 )
      {
        if ( v67 != 1 )
        {
LABEL_61:
          *((_DWORD *)v53 + 4 * a3[5]) = 2;
          *((_WORD *)v53 + 8 * a3[5] + 4) = __ROR2__(v145, 8);
          v77 = __ROR2__(v148, 8);
          *((_DWORD *)v53 + 4 * a3[8]) = 2;
          *((_WORD *)v53 + 8 * a3[8] + 4) = v77;
          goto LABEL_62;
        }
      }
      else if ( a4 != 23 || v67 != 58 )
      {
        goto LABEL_61;
      }
      v81 = v164;
      *((_DWORD *)v53 + 4 * a3[5]) = 2;
      *((_WORD *)v53 + 8 * a3[5] + 4) = *(unsigned __int8 *)(v81 + 4);
      *((_DWORD *)v53 + 4 * a3[8]) = 2;
      *((_WORD *)v53 + 8 * a3[8] + 4) = *(unsigned __int8 *)(v81 + 5);
      *((_DWORD *)v53 + 4 * a3[34]) = 2;
      *((_WORD *)v53 + 8 * a3[34] + 4) = *(unsigned __int8 *)(v81 + 4);
      v82 = *(unsigned __int8 *)(v81 + 4);
      if ( a4 == 2 )
      {
        if ( (unsigned __int8)v82 <= 0x12u )
        {
          v83 = 418049;
          if ( _bittest(&v83, v82) )
          {
            *v54 |= 0x8000000u;
            v54[50] = *(_DWORD *)v81;
          }
        }
      }
      else if ( (unsigned __int8)(v82 + 0x80) <= 1u )
      {
        *v54 |= 0x8000000u;
        v54[50] = *(_DWORD *)v81;
      }
LABEL_62:
      v78 = v150;
      *((_DWORD *)v53 + 4 * a3[4]) = 1;
      *((_BYTE *)v53 + 16 * a3[4] + 8) = a10;
      *((_DWORD *)v53 + 4 * a3[12]) = 4;
      *((_QWORD *)v53 + 2 * a3[12] + 1) = &a11;
      *((_DWORD *)v53 + 4 * a3[19]) = 3;
      *((_DWORD *)v53 + 4 * a3[19] + 2) = *(_DWORD *)(*(_QWORD *)(v78 + 8) + 8LL);
      *((_DWORD *)v53 + 4 * a3[13]) = 3;
      *((_DWORD *)v53 + 4 * a3[13] + 2) = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v78 + 8) + 48LL) + 12LL);
      *((_DWORD *)v53 + 4 * a3[14]) = 3;
      *((_DWORD *)v53 + 4 * a3[14] + 2) = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v78 + 8) + 48LL) + 16LL);
      v79 = v153;
      if ( v153 )
      {
        if ( *(_DWORD *)(*(_QWORD *)(v153 + 48) + 12LL) == 131 )
        {
          ProfileIdFromPacketInbound = 0;
          if ( !v157 )
            goto LABEL_77;
          goto LABEL_65;
        }
        if ( v157 )
        {
LABEL_65:
          ProfileIdFromPacketInbound = WfpGetProfileIdFromPacketInbound(v153, v157, v157);
          v79 = v153;
          goto LABEL_77;
        }
        ProfileIdFromPacketInbound = *(_DWORD *)(v153 + 56);
      }
      else
      {
        ProfileIdFromPacketInbound = 0;
      }
LABEL_77:
      *v38 = ProfileIdFromPacketInbound;
      v84 = v157;
      AlepFillEdgeInterfaceRelatedFields(
        v79,
        (_DWORD)a3,
        v79,
        v157,
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
      v85 = (_DWORD **)v153;
      *((_DWORD *)v53 + 4 * a3[35]) = 4;
      *((_QWORD *)v53 + 2 * a3[35] + 1) = v85 + 10;
      if ( !v42[31] )
      {
        if ( v143 && a31 )
        {
          v103 = *(_QWORD *)(a31 + 488);
          v163 = (_DWORD *)(v103 + 224);
          v104 = *(_DWORD *)(v103 + 72);
          v101 = &v162;
          LODWORD(v162) = v104;
          *((_DWORD *)v53 + 4 * a3[9]) = 16;
          v102 = a3[9];
          goto LABEL_136;
        }
LABEL_137:
        v105 = v155;
        *((_DWORD *)v53 + 4 * a3[18]) = 3;
        *((_DWORD *)v53 + 4 * a3[18] + 2) = v105;
        if ( (SpinLock[6] & 0x2000) != 0 )
        {
          *((_DWORD *)v53 + 4 * a3[17]) = 3;
          *((_DWORD *)v53 + 4 * a3[17] + 2) = *((_DWORD *)SpinLock + 127);
        }
        *((_DWORD *)v53 + 4 * a3[40]) = 3;
        *((_DWORD *)v53 + 4 * a3[40] + 2) = **v85;
        v47 = *((_DWORD *)SpinLock + 170) == 1;
        v181 = 0;
        v180 = (unsigned __int64)v42;
        if ( v47 )
          v54[1] |= 0x80000u;
        *v54 |= 0x80u;
        v106 = v182;
        *((_QWORD *)v54 + 1) = &v180;
        *v54 |= 0x20u;
        v107 = a19;
        *((_QWORD *)v54 + 8) = *(_QWORD *)(SpinLock[60] + 32);
        *v54 |= 4u;
        v54[10] = v107;
        *v54 |= 0x400u;
        v54[11] = a20;
        *v54 |= 0x800u;
        v54[20] = **v85;
        if ( FeAcquireCompletionHandle(v106, &v159) )
          v159 = FeAcquireGenericCompletionHandle();
        *v54 |= 0x4000u;
        v108 = v149;
        *((_QWORD *)v54 + 13) = v159;
        v109 = SpinLock[60];
        LODWORD(Pool2) = 0;
        v178 = *(_QWORD *)(v109 + 16);
        LODWORD(v177) = *(unsigned __int16 *)(v109 + 10);
        *v54 |= 8u;
        *((_QWORD *)v54 + 6) = &v177;
        *v54 |= 0x10u;
        v110 = a22;
        *((_QWORD *)v54 + 7) = *(_QWORD *)(SpinLock[61] + 64);
        v54[70] = v110;
        *v54 |= 0x40000u;
        v54[35] = 1;
        *((_WORD *)SpinLock + 208) = v108;
        KfdGetLayerCacheEpoch(v108, &Pool2);
        *((_DWORD *)SpinLock + 102) = Pool2;
        if ( (SpinLock[6] & 0x40) == 0 )
          _InterlockedOr((volatile signed __int32 *)SpinLock + 12, 0x40u);
        KfdGetLayerCacheEpoch(v108, &v156);
        *v54 |= 0x8000u;
        v111 = a27;
        *((_QWORD *)v54 + 14) = *a27;
        if ( v111[6] )
        {
          *v54 |= 0x4000000u;
          *((_QWORD *)v54 + 24) = v111[6];
        }
        if ( *((_DWORD *)v111 + 2) )
        {
          *v54 |= 0x20000u;
          v54[30] = *((_DWORD *)v111 + 2);
        }
        if ( v111[2] )
        {
          *v54 |= 0x10000u;
          *((_QWORD *)v54 + 16) = v111[2];
          v54[34] = *((_DWORD *)v111 + 6);
        }
        if ( v111[4] )
        {
          *v54 |= 0x800000u;
          *((_QWORD *)v54 + 18) = v111[4];
          v54[38] = *((_DWORD *)v111 + 10);
        }
        WfpAleInitializeWaitRef_1(v42 + 16);
        WfpAleReferenceEndpointNoLock_0(v42);
        KfdAleInitializeFlowTable(v42 + 9, 0);
        if ( !KfdAleAcquireFlowHandleForFlow(SpinLock, v42, &v171) )
        {
          *v54 |= 2u;
          *((_QWORD *)v54 + 4) = v171;
          KfdAleReleaseFlowHandleForFlow(SpinLock);
        }
        v112 = a18;
        *((_BYTE *)v54 + 592) = *(_BYTE *)(SpinLock[61] + 152);
        *(_OWORD *)(v54 + 150) = *(_OWORD *)(SpinLock[61] + 160);
        *((_QWORD *)v54 + 77) = *(_QWORD *)(SpinLock[61] + 176);
        *(_OWORD *)(v54 + 162) = *(_OWORD *)(SpinLock[61] + 192);
        v140 = v185;
        *(_OWORD *)(v54 + 166) = *(_OWORD *)(SpinLock[61] + 208);
        v60 = WfpAleClassify((unsigned int)&v179, (_DWORD)v54, v84, v112, (__int64)v154, v140);
        if ( v60 )
          goto LABEL_202;
        v113 = 0;
        v114 = 0;
        if ( a28 )
        {
          _InterlockedOr((volatile signed __int32 *)v42 + 12, 0x4000000u);
        }
        else if ( a29 )
        {
          _InterlockedOr((volatile signed __int32 *)v42 + 12, 0x8000000u);
        }
        v115 = a4;
        if ( a4 == 2 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10000) != 0 )
          {
            v139 = (unsigned __int16)__ROR2__(v145, 8);
            WPP_SF__IPV4_d_IPV4_dd(
              WPP_GLOBAL_Control->AttachedDevice,
              v139,
              (unsigned __int16)__ROR2__(v148, 8),
              **(_QWORD **)(v150 + 16),
              v139,
              v166);
LABEL_169:
            v115 = a4;
          }
        }
        else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
               && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u
               && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10000) != 0 )
        {
          v116 = (unsigned __int16)__ROR2__(v148, 8);
          v117 = (unsigned __int16)__ROR2__(v145, 8);
          WPP_SF__IPV6_d_IPV6_dd(
            WPP_GLOBAL_Control->AttachedDevice,
            v117,
            v116,
            **(_QWORD **)(v150 + 16),
            v117,
            v166,
            v116,
            v151);
          goto LABEL_169;
        }
        if ( v165 && v165 != SpinLock )
          SpinLock = v165;
        v55 = v150;
        if ( *(_DWORD *)(v150 + 24) == 1 )
        {
          if ( v54[84] )
            v113 = v54[86];
          v118 = 1;
          if ( v54[80] )
            v114 = v54[82] == 1;
        }
        else
        {
          v118 = 1;
        }
        if ( (SpinLock[6] & 0x40) != 0 && *(_DWORD *)(v150 + 24) == 1 && !v114 )
        {
          if ( v54[84] )
            v113 = v54[86];
          v119 = v169;
          inserted = WfpAleInsertRemoteEndpoint(
                       SpinLock,
                       v150,
                       v145,
                       v166,
                       v148,
                       v143,
                       v164,
                       v149,
                       v156,
                       0,
                       0,
                       v157,
                       (__int64)v42,
                       v113,
                       v155,
                       1,
                       0,
                       0,
                       v169,
                       v172);
          v59 = v141;
          v60 = inserted;
          if ( !inserted )
          {
            v121 = *(volatile signed __int32 **)(a26 + 16);
            *(_QWORD *)(*(_QWORD *)v119 + 288LL) = v121;
            _InterlockedIncrement(v121);
          }
          goto LABEL_203;
        }
        if ( (unsigned int)(*(_DWORD *)(v150 + 24) - 3) <= 1 || v114 )
        {
          LODWORD(Pool2) = 0;
          v185 = 0;
          v158 = *(_QWORD *)v164;
          if ( v115 == 2 )
          {
            v122 = &Pool2;
          }
          else
          {
            if ( v115 != 23 )
              goto LABEL_222;
            v122 = (__int64 *)&v185;
          }
          if ( v54[88] )
            v113 = v54[90];
          if ( !v114 )
            v118 = 4;
          LODWORD(v158) = 0;
          v60 = WfpAleInsertRemoteEndpoint(
                  SpinLock,
                  v150,
                  v145,
                  (__int64)v122,
                  0,
                  v143,
                  (__int64)&v158,
                  v149,
                  v156,
                  0,
                  0,
                  v157,
                  (__int64)v42,
                  v113,
                  v155,
                  v118,
                  2 * v114,
                  0,
                  v169,
                  v172);
          if ( !v60 )
          {
            if ( (*((_DWORD *)SpinLock + 12) & 0x80u) == 0 )
              _InterlockedOr((volatile signed __int32 *)SpinLock + 12, 0x80u);
            if ( v114 )
            {
              v58 = v142;
              v59 = v141;
              if ( (*((_DWORD *)SpinLock + 13) & 0x40000) == 0 )
                _InterlockedOr((volatile signed __int32 *)SpinLock + 13, 0x40000u);
              goto LABEL_204;
            }
          }
        }
LABEL_202:
        v59 = v141;
LABEL_203:
        v58 = v142;
        goto LABEL_204;
      }
      v86 = 0;
      memset(&LockHandle, 0, sizeof(LockHandle));
      v158 = 0;
      v161 = 0;
      if ( !gAleDebugEnabled )
      {
        v93 = 0;
        goto LABEL_111;
      }
      v87 = 32;
      Entry = 0;
      Pool2 = ExAllocatePool2(64, 32, 1281715265);
      v88 = (_BYTE *)Pool2;
      if ( !Pool2 )
      {
        v86 = -1073741801;
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
          v93 = Pool2;
LABEL_111:
          KeAcquireInStackQueuedSpinLock(v42, &LockHandle);
          while ( *((_DWORD *)v42 + 2) )
            ;
          v47 = gAleDebugEnabled == 1;
          v42[2] = (KSPIN_LOCK)KeGetCurrentThread();
          if ( v47 && !v86 )
            v42[3] = v93;
          v94 = v42[31];
          v95 = *(_DWORD *)v94;
          if ( *(_DWORD *)v94 )
          {
            v96 = *(_QWORD *)(v94 + 8);
            v97 = 0;
            do
            {
              v98 = 32LL * v97;
              v99 = *(_DWORD *)(v98 + v96 + 8);
              if ( v99 )
              {
                if ( v99 == 1 )
                  v161 = *(_DWORD **)(v98 + v96 + 24);
              }
              else
              {
                v158 = *(_QWORD *)(v98 + v96 + 24);
              }
              ++v97;
            }
            while ( v97 < v95 );
          }
          v100 = 0;
          v42[2] = 0;
          if ( gAleDebugEnabled == 1 )
          {
            v100 = (void *)v42[3];
            v42[3] = 0;
          }
          KeReleaseInStackQueuedSpinLock(&LockHandle);
          if ( gAleDebugEnabled == 1 && v100 )
            ExFreePoolWithTag(v100, 0);
          if ( v161 )
          {
            v163 = v161 + 56;
            LODWORD(v162) = v161[18];
            *((_DWORD *)v53 + 4 * a3[9]) = 16;
            *((_QWORD *)v53 + 2 * a3[9] + 1) = &v162;
          }
          v85 = (_DWORD **)v153;
          v84 = v157;
          if ( v158 )
          {
            v176 = v158 + 224;
            v101 = &v175;
            LODWORD(v175) = *(_DWORD *)(v158 + 72);
            *((_DWORD *)v53 + 4 * a3[10]) = 16;
            v102 = a3[10];
LABEL_136:
            *((_QWORD *)v53 + 2 * v102 + 1) = v101;
            goto LABEL_137;
          }
          goto LABEL_137;
        }
        v88 = (_BYTE *)Pool2;
      }
      if ( !v86 )
      {
        v89 = 2147483646;
        v90 = "WfpAleQueryPeerTokenInformation";
        do
        {
          if ( !v89 )
            break;
          if ( !*v90 )
            break;
          *v88++ = *v90++;
          --v89;
          --v87;
        }
        while ( v87 );
        v91 = 122;
        if ( v87 )
          v91 = 0;
        v92 = v88 - 1;
        if ( v87 )
          v92 = v88;
        *v92 = 0;
        if ( !v87 )
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
              v91);
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
              v91);
          }
        }
        v86 = (__int64)Entry;
      }
      goto LABEL_110;
    }
    v57 = (char *)gIncomingValuesLookasideList
        + 128 * (unsigned __int64)(unsigned int)(HIDWORD(KeGetPcr()[1].LockArray) + 1);
    if ( !v57[176] )
      PplpLazyInitializeLookasideList(gIncomingValuesLookasideList, v57 + 64, gIncomingValuesLookasideList, v56);
    ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v57 + 64), Entry);
  }
  v58 = v142;
  v53 = 0;
  v59 = v141;
  v54 = 0;
  v144 = 0;
  if ( v142 )
    WfpLowerIrqlFromDispatchLevel(v141);
  v60 = -1073741670;
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
  if ( v159 )
  {
    FeReleaseCompletionHandle();
    v159 = 0;
  }
  if ( Size[1] )
  {
    ExFreePoolWithTag((PVOID)Size[1], 0);
    Size[1] = 0;
    LODWORD(Size[0]) = 0;
  }
  if ( v42[31] )
    WfpAlepFreePeerTokenInformation(v42 + 31);
  v123 = v42[32];
  if ( v123 )
  {
    if ( *(_BYTE *)(v123 + 72) )
    {
      WfpAleReleasePeerInformation();
    }
    else if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v123 + 24), 0xFFFFFFFF) == 1 )
    {
      WfpAlepFreePeerInformation();
    }
    v42[32] = 0;
  }
  if ( v42[12] )
    KfdAleNotifyFlowDeletion(v42 + 9);
  v124 = v165;
  if ( v165 )
  {
    if ( gAleDebugEnabled )
    {
      v125 = v165[19];
      if ( v125 != 0xBADBADFABADBADFAuLL && _InterlockedDecrement((volatile signed __int32 *)(v125 + 48)) < 0 )
LABEL_222:
        __fastfail(5u);
    }
    v150 = (__int64)(v124 + 16);
    v126 = *((_BYTE *)v124 + 132);
    do
    {
      v128 = *(_DWORD *)v150 & 3 | (4 * (*(_DWORD *)v150 >> 2) - 4);
      if ( v126 && v128 < 4 )
        v128 |= 2u;
      v55 = v150;
      v127 = *(_DWORD *)v150;
    }
    while ( v127 != _InterlockedCompareExchange((volatile signed __int32 *)v150, v128, v127) );
    if ( v128 < 4 && (v128 & 3) != 1 )
    {
      v129 = *(void **)(v150 + 24);
      (*(void (__fastcall **)(_QWORD))(v150 + 16))(*(_QWORD *)(v150 + 8));
      if ( gAleDebugEnabled )
      {
        if ( v129 != (void *)0xBADBADFABADBADFALL && v129 )
          ExFreePoolWithTag(v129, 0);
      }
    }
  }
  HIDWORD(v130) = HIDWORD(v170);
  if ( v170 )
    v130 = IppDereferenceLocalAddress(v170);
  if ( v144 )
  {
    LODWORD(v130) = HIDWORD(KeGetPcr()[1].LockArray);
    v131 = (PVOID *)((char *)gPerProcessorContext + 72 * v130);
    KfdReleaseTerminatingFilters(v54 + 156, 9 * v130, v55);
    if ( v53 == v131[3] )
    {
      *((_BYTE *)v131 + 32) = 0;
    }
    else
    {
      v134 = (char *)gMetadataLookasideList
           + 128 * (unsigned __int64)(unsigned int)(HIDWORD(KeGetPcr()[1].LockArray) + 1);
      if ( !v134[176] )
        PplpLazyInitializeLookasideList(gMetadataLookasideList, v134 + 64, v132, v133);
      ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v134 + 64), v54);
      v137 = (char *)gIncomingValuesLookasideList
           + 128 * (unsigned __int64)(unsigned int)(HIDWORD(KeGetPcr()[1].LockArray) + 1);
      if ( !v137[176] )
        PplpLazyInitializeLookasideList(gIncomingValuesLookasideList, v137 + 64, v135, v136);
      ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v137 + 64), v53);
    }
    if ( v58 )
      WfpLowerIrqlFromDispatchLevel(v59);
  }
  if ( v60
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
  {
    WPP_SF_sd(
      WPP_GLOBAL_Control->AttachedDevice,
      15,
      (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
      (unsigned int)"WfpAlepAuthorizeReceive",
      v60);
  }
  return v60;
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
