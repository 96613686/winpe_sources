# WfpAlepReauthorizeInboundConnection

- ea: `0x1400c8f90`
- end: `0x1400ca031`
- name: `WfpAlepReauthorizeInboundConnection`
- size: `4257`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400c8770`

## callees

- `0x14001215c`
- `0x140012f00`
- `0x1400143c0`
- `0x140014480`
- `0x140014974`
- `0x1400162f0`
- `0x140016470`
- `0x1400611c0`
- `0x1400ad6a0`
- `0x1400c8f90`
- `0x1400efdb8`
- `0x14012d2bc`
- `0x140141b90`
- `0x1401c1280`
- `0x1401c1580`

## import_xrefs

- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400c914a`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400c9f5d`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400c9f9d`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400c914a`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400c9f5d`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400c9f9d`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400c9088`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400c9088`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400c9976`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400c9976`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400c9a12`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400c9a12`
- `ntoskrnl!KeQueryInterruptTimePrecise` at `0x1400c9030`
- `ntoskrnl!KeQueryInterruptTimePrecise` at `0x1400c9030`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c9a31`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c9ecb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c9a31`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c9ecb`
- `ntoskrnl!ExAllocatePool2` at `0x1400c97bf`
- `ntoskrnl!ExAllocatePool2` at `0x1400c97bf`
- `NETIO!KfdReleaseTerminatingFilters` at `0x1400c9f0e`
- `NETIO!KfdReleaseTerminatingFilters` at `0x1400c9f0e`

## string_xrefs

- `0x1400c989f`: `WfpAleQueryPeerTokenInformation`
- `0x1400c9905`: `StringCchCopyA`
- `0x1400c9948`: `WfpStringCchCopyA`

## pseudocode

```c
__int64 __fastcall WfpAlepReauthorizeInboundConnection(
        __int64 a1,
        __int64 a2,
        unsigned __int16 *a3,
        __int16 a4,
        int a5,
        __int64 a6,
        _OWORD *a7,
        __int16 a8,
        unsigned __int8 a9,
        __int64 a10,
        _OWORD *a11,
        __int16 a12,
        __int64 a13,
        char a14,
        __int64 a15,
        __int64 a16,
        unsigned __int8 a17,
        int a18,
        int a19,
        __int64 a20,
        int a21,
        int a22,
        int a23,
        __int64 a24,
        __int64 a25,
        __int64 a26,
        __int64 a27,
        _DWORD *a28,
        _DWORD *a29,
        _DWORD *a30)
{
  __int16 v30; // r12
  PVOID v31; // rdi
  char v32; // r13
  __int16 v34; // r14
  __int64 v36; // rax
  bool v37; // zf
  __int64 v38; // rcx
  _DWORD *v39; // rbx
  char *v40; // rbx
  unsigned __int8 v41; // r15
  char v42; // si
  __int64 v43; // r14
  int v44; // r8d
  __int64 *v45; // rdx
  __int64 v46; // rcx
  __int64 v47; // rcx
  __int64 v48; // rax
  __int64 v49; // rax
  __int64 v50; // r12
  unsigned int v51; // r13d
  __int64 v52; // rax
  int v53; // edx
  __int64 v54; // r9
  int v55; // r8d
  __int64 v56; // rcx
  int v57; // ecx
  int v58; // ecx
  int v59; // ecx
  int v60; // edx
  unsigned int v61; // ecx
  unsigned int v62; // eax
  int v63; // eax
  __int16 v64; // cx
  __int16 v65; // cx
  __int64 v66; // r12
  unsigned __int8 v67; // cl
  int v68; // r9d
  __int64 v69; // r14
  __int64 v70; // rdx
  int v71; // r8d
  __int64 v72; // r13
  int v73; // ecx
  __int64 v74; // rdx
  unsigned int v75; // eax
  int v76; // ecx
  __int64 v77; // r12
  __int64 v78; // r14
  _BYTE *v79; // rcx
  __int64 v80; // rax
  const char *v81; // rdx
  char v82; // r13
  _BYTE *v83; // rax
  __int64 v84; // r14
  unsigned int *v85; // rax
  unsigned int v86; // r8d
  __int64 v87; // r9
  unsigned int v88; // ecx
  __int64 v89; // rax
  int v90; // edx
  void *v91; // r14
  __int64 *v92; // rcx
  __int64 v93; // rax
  __int64 v94; // rcx
  int v95; // eax
  int *v96; // rax
  __int64 v97; // r12
  int v98; // ecx
  __int64 v99; // rcx
  __int64 v100; // rax
  int v101; // eax
  __int64 v102; // rcx
  __int64 inserted; // rax
  _DWORD *v104; // r13
  int v105; // r9d
  int v106; // r8d
  int v107; // r8d
  __int16 v108; // cx
  __int64 v109; // rax
  PVOID *v110; // rsi
  char *v111; // rsi
  char *v112; // rbx
  __int16 v114; // [rsp+68h] [rbp-A0h]
  __int64 Pool2; // [rsp+70h] [rbp-98h] BYREF
  __int64 Size; // [rsp+78h] [rbp-90h]
  size_t Size_8[2]; // [rsp+80h] [rbp-88h] BYREF
  __int64 v118; // [rsp+90h] [rbp-78h] BYREF
  __int64 v119; // [rsp+98h] [rbp-70h] BYREF
  __int64 v120; // [rsp+A0h] [rbp-68h]
  __int64 v121; // [rsp+A8h] [rbp-60h]
  __int64 v122; // [rsp+B0h] [rbp-58h] BYREF
  __int64 v123; // [rsp+B8h] [rbp-50h]
  __int64 v124; // [rsp+C0h] [rbp-48h] BYREF
  __int64 v125; // [rsp+C8h] [rbp-40h]
  __int64 v126; // [rsp+D0h] [rbp-38h] BYREF
  __int64 v127; // [rsp+D8h] [rbp-30h]
  __int64 v128; // [rsp+E0h] [rbp-28h]
  __int64 v129; // [rsp+E8h] [rbp-20h]
  __int64 v130; // [rsp+F0h] [rbp-18h] BYREF
  __int64 v131; // [rsp+F8h] [rbp-10h]
  __int128 v132; // [rsp+100h] [rbp-8h] BYREF
  __int64 *v133; // [rsp+110h] [rbp+8h] BYREF
  __int128 v134; // [rsp+118h] [rbp+10h] BYREF
  __int64 v135; // [rsp+128h] [rbp+20h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+130h] [rbp+28h] BYREF
  PVOID Entry; // [rsp+188h] [rbp+80h] BYREF
  __int16 v138; // [rsp+1A0h] [rbp+98h]

  v138 = a4;
  v30 = a4;
  v31 = 0;
  v32 = 0;
  Entry = 0;
  LODWORD(v127) = 0;
  LODWORD(v123) = 0;
  v34 = a2;
  LODWORD(v120) = 0;
  LODWORD(v131) = 0;
  LODWORD(v125) = 0;
  v126 = 0;
  v122 = 0;
  v119 = 0;
  v130 = 0;
  v124 = 0;
  v114 = 0;
  v135 = 0;
  Pool2 = 0;
  v118 = 0;
  *(_OWORD *)Size_8 = 0;
  v132 = 0;
  v134 = 0;
  if ( dword_140224310 )
    v36 = KeQueryInterruptTimePrecise(&v118, a2);
  else
    v36 = MEMORY[0xFFFFF78000000008];
  v37 = *(_DWORD *)(a1 + 40) == 6;
  v118 = v36;
  v121 = 0;
  if ( !v37 || (*(_DWORD *)(a1 + 48) & 0x10) != 0 )
    Size = a16;
  else
    Size = a1;
  if ( (*(_DWORD *)(a1 + 56) & 1) != 0 )
    v121 = *(_QWORD *)(a1 + 456);
  if ( KeGetCurrentIrql() < 2u )
  {
    v32 = 1;
    LOBYTE(v114) = WfpRaiseIrqlToDispatchLevel();
    HIBYTE(v114) = 1;
  }
  LODWORD(v38) = HIDWORD(KeGetPcr()[1].LockArray);
  if ( !*((_BYTE *)gPerProcessorContext + 72 * v38 + 32) )
  {
    v31 = (PVOID)*((_QWORD *)gPerProcessorContext + 9 * v38 + 3);
    v39 = (_DWORD *)*((_QWORD *)gPerProcessorContext + 9 * v38 + 2);
    *((_BYTE *)gPerProcessorContext + 72 * v38 + 32) = 1;
    goto LABEL_26;
  }
  if ( !WfpAllocateFromPerProcessorLookasideList(gIncomingValuesLookasideList, &Entry) )
  {
    if ( !WfpAllocateFromPerProcessorLookasideList(gMetadataLookasideList, &Pool2) )
    {
      v31 = Entry;
      v39 = (_DWORD *)Pool2;
LABEL_26:
      memset(v31, 0, 0x2A0u);
      memset(v39, 0, 0x2A8u);
      *((_QWORD *)v39 + 79) = v39 + 156;
      v45 = gAleNullSid;
      *((_QWORD *)v39 + 78) = v39 + 156;
      v46 = *(_QWORD *)(a1 + 480);
      DWORD1(v132) = *a3;
      LOWORD(v132) = v34;
      *((_QWORD *)&v132 + 1) = v31;
      v127 = *(_QWORD *)(v46 + 16);
      LODWORD(v126) = *(unsigned __int16 *)(v46 + 10);
      *((_DWORD *)v31 + 4 * a3[1]) = 12;
      *((_QWORD *)v31 + 2 * a3[1] + 1) = &v126;
      v47 = *(_QWORD *)(a1 + 488);
      v123 = v47 + 224;
      LODWORD(v122) = *(_DWORD *)(v47 + 72);
      *((_DWORD *)v31 + 4 * a3[2]) = 16;
      *((_QWORD *)v31 + 2 * a3[2] + 1) = &v122;
      v48 = a3[37];
      if ( *(_QWORD *)(*(_QWORD *)(a1 + 488) + 280LL) )
        v45 = *(__int64 **)(*(_QWORD *)(a1 + 488) + 280LL);
      v133 = v45;
      *((_DWORD *)v31 + 4 * v48) = 13;
      *((_QWORD *)v31 + 2 * a3[37] + 1) = v45;
      *((_DWORD *)v31 + 4 * a3[41]) = 16;
      *((_QWORD *)v31 + 2 * a3[41] + 1) = &v122;
      v49 = *(_QWORD *)(*(_QWORD *)(a1 + 488) + 144LL);
      if ( v49 )
      {
        v50 = *(_QWORD *)(*(_QWORD *)(v49 + 8) + 32LL);
        v51 = (unsigned __int16)(*(_WORD *)(v50 + 8) + 2);
        LODWORD(Size_8[0]) = v51 + 8;
        v43 = WfpPoolAllocNonPaged(v51 + 8, 1668376129, &Size_8[1]);
        if ( v43 )
        {
          v42 = 1;
LABEL_168:
          v41 = v114;
          v32 = HIBYTE(v114);
          goto LABEL_169;
        }
        memset((void *)Size_8[1], 0, LODWORD(Size_8[0]));
        *(_QWORD *)Size_8[1] = *(_QWORD *)v50;
        memmove((void *)(Size_8[1] + 8), *(const void **)(v50 + 16), v51);
        v30 = v138;
      }
      v52 = 2LL * a3[38];
      LOBYTE(Entry) = 1;
      *((_DWORD *)v31 + 2 * v52) = 12;
      *((_QWORD *)v31 + 2 * a3[38] + 1) = Size_8;
      if ( (*(_DWORD *)(a1 + 56) & 1) != 0 )
        WfpAlepAuthInboundFlowSwizzleDestinationInformation((_DWORD)a3, v121, v44, (_DWORD)a7, (__int64)v31);
      else
        *((_OWORD *)v31 + a3[3]) = *a7;
      v53 = 0;
      v54 = a16;
      v55 = a5;
      *((_OWORD *)v31 + a3[7]) = *a11;
      v56 = v54;
      *((_DWORD *)v31 + 4 * a3[6]) = 1;
      *((_BYTE *)v31 + 16 * a3[6] + 8) = v55;
      if ( !v54 )
        v56 = a1;
      *((_DWORD *)v31 + 4 * a3[16]) = 3;
      if ( v56 != -168 )
      {
        v57 = *(_DWORD *)(v56 + 200);
        v53 = 2 * (v57 & 1);
        if ( (v57 & 0x800) != 0 )
          v53 = (2 * (v57 & 1)) | 0x10000;
      }
      v58 = v53 | 1;
      if ( !a14 )
        v58 = v53;
      v59 = v58 | 4;
      v60 = v59 | 0x10;
      if ( (*(_DWORD *)(a1 + 48) & 0x10) == 0 )
        v60 = v59;
      if ( v54 )
        v61 = *(_DWORD *)(v54 + 48);
      else
        v61 = *(_DWORD *)(a1 + 48);
      if ( ((v61 >> 26) & 1) != 0 )
        v60 |= 0x400000u;
      if ( v54 )
        v62 = *(_DWORD *)(v54 + 48);
      else
        v62 = *(_DWORD *)(a1 + 48);
      if ( ((v62 >> 27) & 1) != 0 )
        v60 |= 0x800000u;
      if ( v54 )
        v63 = *(_DWORD *)(v54 + 52);
      else
        v63 = *(_DWORD *)(a1 + 52);
      if ( v63 < 0 )
        v60 |= 0x1000000u;
      *((_DWORD *)v31 + 4 * a3[16] + 2) = v60;
      if ( v30 == 2 )
      {
        if ( v55 != 1 )
        {
LABEL_61:
          if ( (*(_DWORD *)(a1 + 56) & 1) == 0 )
          {
            v64 = __ROR2__(a8, 8);
            *((_DWORD *)v31 + 4 * a3[5]) = 2;
            *((_WORD *)v31 + 8 * a3[5] + 4) = v64;
          }
          v65 = __ROR2__(a12, 8);
          *((_DWORD *)v31 + 4 * a3[8]) = 2;
          *((_WORD *)v31 + 8 * a3[8] + 4) = v65;
          *((_DWORD *)v31 + 4 * a3[34]) = 0;
          goto LABEL_64;
        }
      }
      else if ( v30 != 23 || v55 != 58 )
      {
        goto LABEL_61;
      }
      v74 = a13;
      *((_DWORD *)v31 + 4 * a3[5]) = 2;
      *((_WORD *)v31 + 8 * a3[5] + 4) = *(unsigned __int8 *)(v74 + 4);
      *((_DWORD *)v31 + 4 * a3[8]) = 2;
      *((_WORD *)v31 + 8 * a3[8] + 4) = *(unsigned __int8 *)(v74 + 5);
      *((_DWORD *)v31 + 4 * a3[34]) = 2;
      *((_WORD *)v31 + 8 * a3[34] + 4) = *(unsigned __int8 *)(v54 + 570);
      v75 = *(unsigned __int8 *)(v74 + 4);
      if ( v30 == 2 )
      {
        if ( (unsigned __int8)v75 <= 0x12u )
        {
          v76 = 418049;
          if ( _bittest(&v76, v75) )
          {
            *v39 |= 0x8000000u;
            v39[50] = *(_DWORD *)v74;
          }
        }
      }
      else if ( (unsigned __int8)(v75 + 0x80) <= 1u )
      {
        *v39 |= 0x8000000u;
        v39[50] = *(_DWORD *)v74;
      }
LABEL_64:
      v66 = a10;
      v67 = a9;
      v68 = a23;
      v69 = a20;
      *((_DWORD *)v31 + 4 * a3[4]) = 1;
      v70 = v69;
      v71 = v69;
      v72 = Size;
      *((_BYTE *)v31 + 16 * a3[4] + 8) = v67;
      *((_DWORD *)v31 + 4 * a3[12]) = 4;
      *((_QWORD *)v31 + 2 * a3[12] + 1) = v66 + 16;
      *((_DWORD *)v31 + 4 * a3[19]) = 3;
      *((_DWORD *)v31 + 4 * a3[19] + 2) = *(_DWORD *)(v66 + 8);
      *((_DWORD *)v31 + 4 * a3[13]) = 3;
      *((_DWORD *)v31 + 4 * a3[13] + 2) = *(_DWORD *)(*(_QWORD *)(v66 + 48) + 12LL);
      *((_DWORD *)v31 + 4 * a3[14]) = 3;
      *((_DWORD *)v31 + 4 * a3[14] + 2) = *(_DWORD *)(*(_QWORD *)(v66 + 48) + 16LL);
      v73 = *(_DWORD *)(v72 + 332);
      *a29 = v73;
      if ( v68 )
        v70 = 0;
      if ( v68 != 1 )
        v71 = 0;
      AlepFillEdgeInterfaceRelatedFields(v73, (_DWORD)a3, v71, a25, v70, a6, a24, a21, a21, v73, a22, (__int64)v31);
      if ( *((_DWORD *)v31 + 4 * a3[31]) )
        *a30 = *((_DWORD *)v31 + 4 * a3[31] + 2);
      if ( v69 )
      {
        *((_DWORD *)v31 + 4 * a3[35]) = 4;
        *((_QWORD *)v31 + 2 * a3[35] + 1) = v69 + 80;
      }
      else
      {
        *((_DWORD *)v31 + 4 * a3[35]) = 0;
      }
      if ( !*(_QWORD *)(v72 + 248) )
      {
        LOBYTE(Entry) = 1;
        if ( a14 && a27 )
        {
          v94 = *(_QWORD *)(a27 + 488);
          v120 = v94 + 224;
          v95 = *(_DWORD *)(v94 + 72);
          v92 = &v119;
          LODWORD(v119) = v95;
          *((_DWORD *)v31 + 4 * a3[9]) = 16;
          v93 = a3[9];
          goto LABEL_138;
        }
LABEL_139:
        if ( (*(_DWORD *)(a1 + 48) & 0x2000) != 0 )
        {
          *((_DWORD *)v31 + 4 * a3[17]) = 3;
          *((_DWORD *)v31 + 4 * a3[17] + 2) = *(_DWORD *)(a1 + 508);
        }
        *((_DWORD *)v31 + 4 * a3[18]) = 3;
        *((_DWORD *)v31 + 4 * a3[18] + 2) = *(_DWORD *)(v72 + 296);
        *((_DWORD *)v31 + 4 * a3[40]) = 3;
        *((_DWORD *)v31 + 4 * a3[40] + 2) = **(_DWORD **)v66;
        if ( *(_DWORD *)(a1 + 680) == 1 )
          v39[1] |= 0x80000u;
        *v39 |= 0x80u;
        *((_QWORD *)v39 + 1) = &v134;
        *v39 |= 0x20u;
        *((_QWORD *)v39 + 8) = *(_QWORD *)(*(_QWORD *)(a1 + 480) + 32LL);
        *v39 |= 0x800u;
        v96 = *(int **)v66;
        v97 = a26;
        v98 = *v96;
        LODWORD(v96) = a18;
        v39[20] = v98;
        *v39 |= 4u;
        v39[10] = (_DWORD)v96;
        *v39 |= 0x400u;
        v39[11] = a19;
        v99 = *(_QWORD *)(a1 + 480);
        v125 = *(_QWORD *)(v99 + 16);
        LODWORD(v124) = *(unsigned __int16 *)(v99 + 10);
        *v39 |= 8u;
        *((_QWORD *)v39 + 6) = &v124;
        *v39 |= 0x10u;
        v100 = a15;
        *((_QWORD *)v39 + 7) = *(_QWORD *)(*(_QWORD *)(a1 + 488) + 64LL);
        *v39 |= 2u;
        *((_QWORD *)v39 + 4) = v100;
        *v39 |= 0x40000u;
        v39[35] = a23;
        if ( a16 )
        {
          *(_QWORD *)&v134 = a16;
          v39[70] = *(_DWORD *)(a16 + 44);
          if ( v97 )
          {
LABEL_151:
            *v39 |= 0x8000u;
            *((_QWORD *)v39 + 14) = *(_QWORD *)v97;
            if ( *(_QWORD *)(v97 + 48) )
            {
              *v39 |= 0x4000000u;
              *((_QWORD *)v39 + 24) = *(_QWORD *)(v97 + 48);
            }
            if ( *(_DWORD *)(v97 + 8) )
            {
              *v39 |= 0x20000u;
              v39[30] = *(_DWORD *)(v97 + 8);
            }
            if ( *(_QWORD *)(v97 + 16) )
            {
              *v39 |= 0x10000u;
              *((_QWORD *)v39 + 16) = *(_QWORD *)(v97 + 16);
              v39[34] = *(_DWORD *)(v97 + 24);
            }
            if ( *(_QWORD *)(v97 + 32) )
            {
              *v39 |= 0x800000u;
              *((_QWORD *)v39 + 18) = *(_QWORD *)(v97 + 32);
              v39[38] = *(_DWORD *)(v97 + 40);
            }
          }
        }
        else
        {
          v101 = *(_DWORD *)(a1 + 44);
          *(_QWORD *)&v134 = a1;
          v39[70] = v101;
          if ( v97 )
          {
            v102 = *(_QWORD *)(a1 + 544);
            if ( v102 )
              inserted = WfpAleQueryOrInsertEndpointHandle(v102);
            else
              inserted = 0;
            *(_QWORD *)(v97 + 48) = inserted;
            goto LABEL_151;
          }
        }
        if ( *(_DWORD *)(a1 + 40) == 6 && (*(_DWORD *)(a1 + 48) & 0x10) == 0 )
          *((_QWORD *)v39 + 63) = *(_QWORD *)(a1 + 352);
        v104 = a28;
        v105 = a17;
        v106 = a25;
        *((_BYTE *)v39 + 592) = *(_BYTE *)(*(_QWORD *)(a1 + 488) + 152LL);
        *(_OWORD *)(v39 + 150) = *(_OWORD *)(*(_QWORD *)(a1 + 488) + 160LL);
        *((_QWORD *)v39 + 77) = *(_QWORD *)(*(_QWORD *)(a1 + 488) + 176LL);
        *(_OWORD *)(v39 + 162) = *(_OWORD *)(*(_QWORD *)(a1 + 488) + 192LL);
        *(_OWORD *)(v39 + 166) = *(_OWORD *)(*(_QWORD *)(a1 + 488) + 208LL);
        v43 = WfpAleClassify((unsigned int)&v132, (_DWORD)v39, v106, v105, 0, (__int64)v104);
        if ( !v43 && (*(_DWORD *)(a1 + 56) & 1) != 0 && *v104 != 4097 )
        {
          v43 = WfpAlepAuthInboundFlowSetOriginalAppInfo(
                  (_DWORD)a3,
                  (_DWORD)v31,
                  (_DWORD)v39,
                  v97,
                  (__int64)&v134,
                  v121,
                  (__int64)&v126,
                  (__int64)&v122,
                  (__int64)Size_8,
                  (__int64)&v124,
                  (__int64)&v133);
          if ( !v43 )
          {
            v107 = a25;
            v108 = __ROR2__(a8, 8);
            *((_OWORD *)v31 + a3[3]) = *a7;
            *((_DWORD *)v31 + 4 * a3[5]) = 2;
            *((_WORD *)v31 + 8 * a3[5] + 4) = v108;
            v43 = WfpAleClassify((unsigned int)&v132, (_DWORD)v39, v107, 0, 0, (__int64)v104);
          }
        }
        v42 = (char)Entry;
        goto LABEL_168;
      }
      v129 = 0;
      memset(&LockHandle, 0, sizeof(LockHandle));
      v77 = 0;
      v128 = 0;
      if ( !gAleDebugEnabled )
      {
        v84 = 0;
        goto LABEL_113;
      }
      v78 = 32;
      Pool2 = ExAllocatePool2(64, 32, 1281715265);
      v79 = (_BYTE *)Pool2;
      if ( !Pool2 )
      {
        v77 = -1073741801;
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
          LOBYTE(Entry) = 1;
LABEL_112:
          v84 = Pool2;
LABEL_113:
          KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)v72, &LockHandle);
          while ( *(_DWORD *)(v72 + 8) )
            ;
          v37 = gAleDebugEnabled == 1;
          *(_QWORD *)(v72 + 16) = KeGetCurrentThread();
          if ( v37 && !v77 )
            *(_QWORD *)(v72 + 24) = v84;
          v85 = *(unsigned int **)(v72 + 248);
          v86 = *v85;
          if ( *v85 )
          {
            v87 = *((_QWORD *)v85 + 1);
            v88 = 0;
            do
            {
              v89 = 32LL * v88;
              v90 = *(_DWORD *)(v89 + v87 + 8);
              if ( v90 )
              {
                if ( v90 == 1 )
                  v128 = *(_QWORD *)(v89 + v87 + 24);
              }
              else
              {
                v129 = *(_QWORD *)(v89 + v87 + 24);
              }
              ++v88;
            }
            while ( v88 < v86 );
          }
          v37 = gAleDebugEnabled == 1;
          v91 = 0;
          *(_QWORD *)(v72 + 16) = 0;
          if ( v37 )
          {
            v91 = *(void **)(v72 + 24);
            *(_QWORD *)(v72 + 24) = 0;
          }
          KeReleaseInStackQueuedSpinLock(&LockHandle);
          if ( gAleDebugEnabled == 1 && v91 )
            ExFreePoolWithTag(v91, 0);
          if ( v128 )
          {
            v120 = v128 + 224;
            LODWORD(v119) = *(_DWORD *)(v128 + 72);
            *((_DWORD *)v31 + 4 * a3[9]) = 16;
            *((_QWORD *)v31 + 2 * a3[9] + 1) = &v119;
          }
          v66 = a10;
          if ( v129 )
          {
            v131 = v129 + 224;
            v92 = &v130;
            LODWORD(v130) = *(_DWORD *)(v129 + 72);
            *((_DWORD *)v31 + 4 * a3[10]) = 16;
            v93 = a3[10];
LABEL_138:
            *((_QWORD *)v31 + 2 * v93 + 1) = v92;
            goto LABEL_139;
          }
          goto LABEL_139;
        }
        v79 = (_BYTE *)Pool2;
      }
      LOBYTE(Entry) = 1;
      if ( !v77 )
      {
        v80 = 2147483646;
        LOBYTE(Entry) = 1;
        v81 = "WfpAleQueryPeerTokenInformation";
        do
        {
          if ( !v80 )
            break;
          if ( !*v81 )
            break;
          *v79++ = *v81++;
          --v80;
          --v78;
        }
        while ( v78 );
        v82 = 122;
        if ( v78 )
          v82 = 0;
        v83 = v79 - 1;
        if ( v78 )
          v83 = v79;
        *v83 = 0;
        if ( !v78 )
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
              v82);
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
              v82);
          }
        }
        v72 = Size;
      }
      goto LABEL_112;
    }
    v40 = (char *)gIncomingValuesLookasideList
        + 128 * (unsigned __int64)(unsigned int)(HIDWORD(KeGetPcr()[1].LockArray) + 1);
    if ( !v40[176] )
      PplpLazyInitializeLookasideList(gIncomingValuesLookasideList, v40 + 64);
    ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v40 + 64), Entry);
  }
  v41 = v114;
  v42 = 0;
  v39 = 0;
  if ( v32 )
    WfpLowerIrqlFromDispatchLevel((unsigned __int8)v114);
  v43 = -1073741670;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
  {
    WPP_SF_sd(
      WPP_GLOBAL_Control->AttachedDevice,
      10,
      (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
      (unsigned int)"WfpAlepReauthorizeInboundConnection",
      154);
  }
LABEL_169:
  v109 = WfpAlepAuthTelemetry(0, v118, 1, a9);
  if ( Size_8[1] )
  {
    ExFreePoolWithTag((PVOID)Size_8[1], 0);
    Size_8[1] = 0;
    LODWORD(Size_8[0]) = 0;
  }
  if ( v42 )
  {
    LODWORD(v109) = HIDWORD(KeGetPcr()[1].LockArray);
    v110 = (PVOID *)((char *)gPerProcessorContext + 72 * v109);
    KfdReleaseTerminatingFilters(v39 + 156);
    if ( v31 == v110[3] )
    {
      *((_BYTE *)v110 + 32) = 0;
    }
    else
    {
      v111 = (char *)gMetadataLookasideList
           + 128 * (unsigned __int64)(unsigned int)(HIDWORD(KeGetPcr()[1].LockArray) + 1);
      if ( !v111[176] )
        PplpLazyInitializeLookasideList(gMetadataLookasideList, v111 + 64);
      ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v111 + 64), v39);
      v112 = (char *)gIncomingValuesLookasideList
           + 128 * (unsigned __int64)(unsigned int)(HIDWORD(KeGetPcr()[1].LockArray) + 1);
      if ( !v112[176] )
        PplpLazyInitializeLookasideList(gIncomingValuesLookasideList, v112 + 64);
      ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v112 + 64), v31);
    }
    if ( v32 )
      WfpLowerIrqlFromDispatchLevel(v41);
  }
  if ( v43
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
  {
    WPP_SF_sd(
      WPP_GLOBAL_Control->AttachedDevice,
      15,
      (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
      (unsigned int)"WfpAlepReauthorizeInboundConnection",
      v43);
  }
  return v43;
}

```

## disassembly

```asm
0x1400c8f90  mov     rax, rsp
0x1400c8f93  mov     [rax+20h], r9w
0x1400c8f98  push    rbp
0x1400c8f99  push    r12
0x1400c8f9b  push    r14
0x1400c8f9d  lea     rbp, [rax-78h]
0x1400c8fa1  sub     rsp, 160h
0x1400c8fa8  mov     [rax-20h], rsi
0x1400c8fac  xorps   xmm0, xmm0
0x1400c8faf  mov     [rax-28h], rdi
0x1400c8fb3  movzx   r12d, r9w
0x1400c8fb7  mov     [rax-30h], r13
0x1400c8fbb  xor     edi, edi
0x1400c8fbd  mov     [rax-38h], r15
0x1400c8fc1  xor     r13b, r13b
0x1400c8fc4  xor     eax, eax
0x1400c8fc6  mov     [rbp+70h+Entry], rdi
0x1400c8fcd  mov     qword ptr [rbp+70h+var_A4], rax
0x1400c8fd1  mov     rsi, r8
0x1400c8fd4  mov     qword ptr [rbp+70h+var_C4], rax
0x1400c8fd8  movzx   r14d, dx
0x1400c8fdc  mov     qword ptr [rbp+70h+var_DC], rax
0x1400c8fe0  mov     r15, rcx
0x1400c8fe3  mov     qword ptr [rbp+70h+var_84], rax
0x1400c8fe7  mov     qword ptr [rbp+70h+var_B4], rax
0x1400c8feb  mov     [rbp-38h], rax
0x1400c8fef  mov     [rbp-58h], rax
0x1400c8ff3  mov     [rbp-70h], rax
0x1400c8ff7  mov     [rbp-18h], rax
0x1400c8ffb  mov     [rbp-48h], rax
0x1400c8fff  mov     byte ptr [rsp+170h+var_110], al
0x1400c9003  mov     [rbp+70h+var_50], rax
0x1400c9007  mov     eax, cs:dword_140224310
0x1400c900d  mov     [rsp+170h+var_108], rdi
0x1400c9012  mov     byte ptr [rsp+170h+var_110+1], r13b
0x1400c9017  mov     [rbp+70h+var_E8], rdi
0x1400c901b  movups  xmmword ptr [rsp+170h+Size+8], xmm0
0x1400c9020  movups  [rbp+70h+var_78], xmm0
0x1400c9024  movups  [rbp+70h+var_60], xmm0
0x1400c9028  test    eax, eax
0x1400c902a  jz      short loc_1400C903E
0x1400c902c  lea     rcx, [rbp+70h+var_E8]
0x1400c9030  call    cs:__imp_KeQueryInterruptTimePrecise
0x1400c9037  nop     dword ptr [rax+rax+00h]
0x1400c903c  jmp     short loc_1400C904B
0x1400c903e  mov     rax, 0FFFFF78000000008h
0x1400c9048  mov     rax, [rax]
0x1400c904b  cmp     dword ptr [r15+28h], 6
0x1400c9050  mov     [rbp+70h+var_E8], rax
0x1400c9054  mov     [rbp+70h+var_D0], rdi
0x1400c9058  jnz     short loc_1400C9069
0x1400c905a  mov     eax, [r15+30h]
0x1400c905e  test    al, 10h
0x1400c9060  jnz     short loc_1400C9069
0x1400c9062  mov     [rsp+170h+Size], r15
0x1400c9067  jmp     short loc_1400C9075
0x1400c9069  mov     rax, [rbp+70h+arg_78]
0x1400c9070  mov     [rsp+170h+Size], rax
0x1400c9075  mov     eax, [r15+38h]
0x1400c9079  test    al, 1
0x1400c907b  jz      short loc_1400C9088
0x1400c907d  mov     rax, [r15+1C8h]
0x1400c9084  mov     [rbp+70h+var_D0], rax
0x1400c9088  call    cs:__imp_KeGetCurrentIrql
0x1400c908f  nop     dword ptr [rax+rax+00h]
0x1400c9094  cmp     al, 2
0x1400c9096  jnb     short loc_1400C90A9
0x1400c9098  call    WfpRaiseIrqlToDispatchLevel
0x1400c909d  mov     r13b, 1
0x1400c90a0  mov     byte ptr [rsp+170h+var_110], al
0x1400c90a4  mov     byte ptr [rsp+170h+var_110+1], r13b
0x1400c90a9  mov     ecx, gs:1A4h
0x1400c90b1  mov     [rsp+170h+arg_8], rbx
0x1400c90b9  lea     r8, [rcx+rcx*8]
0x1400c90bd  mov     rcx, cs:gPerProcessorContext
0x1400c90c4  cmp     [rcx+r8*8+20h], dil
0x1400c90c9  jnz     short loc_1400C90E0
0x1400c90cb  mov     rdi, [rcx+r8*8+18h]
0x1400c90d0  mov     rbx, [rcx+r8*8+10h]
0x1400c90d5  mov     byte ptr [rcx+r8*8+20h], 1
0x1400c90db  jmp     loc_1400C91D7
0x1400c90e0  mov     rcx, cs:gIncomingValuesLookasideList
0x1400c90e7  lea     rdx, [rbp+70h+Entry]
0x1400c90ee  call    WfpAllocateFromPerProcessorLookasideList
0x1400c90f3  test    rax, rax
0x1400c90f6  jnz     short loc_1400C9156
0x1400c90f8  mov     rcx, cs:gMetadataLookasideList
0x1400c90ff  lea     rdx, [rsp+170h+var_108]
0x1400c9104  call    WfpAllocateFromPerProcessorLookasideList
0x1400c9109  test    rax, rax
0x1400c910c  jz      loc_1400C91CB
0x1400c9112  mov     eax, gs:1A4h
0x1400c911a  mov     rcx, cs:gIncomingValuesLookasideList
0x1400c9121  lea     ebx, [rax+1]
0x1400c9124  shl     rbx, 7
0x1400c9128  add     rbx, rcx
0x1400c912b  movzx   eax, byte ptr [rbx+0B0h]
0x1400c9132  test    al, al
0x1400c9134  jnz     short loc_1400C913F
0x1400c9136  lea     rdx, [rbx+40h]
0x1400c913a  call    PplpLazyInitializeLookasideList
0x1400c913f  mov     rdx, [rbp+70h+Entry]; Entry
0x1400c9146  lea     rcx, [rbx+40h]; Lookaside
0x1400c914a  call    cs:__imp_ExFreeToLookasideListEx
0x1400c9151  nop     dword ptr [rax+rax+00h]
0x1400c9156  movzx   r15d, byte ptr [rsp+170h+var_110]
0x1400c915c  xor     sil, sil
0x1400c915f  mov     rbx, rdi
0x1400c9162  test    r13b, r13b
0x1400c9165  jz      short loc_1400C9170
0x1400c9167  movzx   ecx, r15b
0x1400c916b  call    WfpLowerIrqlFromDispatchLevel
0x1400c9170  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c9177  lea     r12, WPP_GLOBAL_Control
0x1400c917e  mov     r14, 0FFFFFFFFC000009Ah
0x1400c9185  cmp     rcx, r12
0x1400c9188  jz      loc_1400C9EA7
0x1400c918e  cmp     byte ptr [rcx+29h], 2
0x1400c9192  jb      loc_1400C9EA7
0x1400c9198  test    dword ptr [rcx+2Ch], 1000h
0x1400c919f  jz      loc_1400C9EA7
0x1400c91a5  mov     rcx, [rcx+18h]
0x1400c91a9  lea     r9, aWfpalepreautho_0; "WfpAlepReauthorizeInboundConnection"
0x1400c91b0  mov     edx, 0Ah
0x1400c91b5  mov     dword ptr [rsp+170h+var_150], r14d
0x1400c91ba  lea     r8, WPP_dc97c17fd6903ad537f842808d057dba_Traceguids
0x1400c91c1  call    WPP_SF_sd
0x1400c91c6  jmp     loc_1400C9EA7
0x1400c91cb  mov     rdi, [rbp+70h+Entry]
0x1400c91d2  mov     rbx, [rsp+170h+var_108]
0x1400c91d7  xor     edx, edx; Val
0x1400c91d9  mov     r8d, 2A0h; Size
0x1400c91df  mov     rcx, rdi; void *
0x1400c91e2  call    memset
0x1400c91e7  xor     edx, edx; Val
0x1400c91e9  mov     r8d, 2A8h; Size
0x1400c91ef  mov     rcx, rbx; void *
0x1400c91f2  call    memset
0x1400c91f7  lea     rax, [rbx+270h]
0x1400c91fe  mov     [rax+8], rax
0x1400c9202  lea     rdx, gAleNullSid
0x1400c9209  mov     [rax], rax
0x1400c920c  mov     rcx, [r15+1E0h]
0x1400c9213  movzx   eax, word ptr [rsi]
0x1400c9216  mov     dword ptr [rbp+70h+var_78+4], eax
0x1400c9219  mov     word ptr [rbp+70h+var_78], r14w
0x1400c921e  mov     qword ptr [rbp+70h+var_78+8], rdi
0x1400c9222  mov     rax, [rcx+10h]
0x1400c9226  mov     qword ptr [rbp+70h+var_A4+4], rax
0x1400c922a  movzx   eax, word ptr [rcx+0Ah]
0x1400c922e  lea     rcx, [rbp+70h+var_A8]
0x1400c9232  mov     [rbp+70h+var_A8], eax
0x1400c9235  movzx   eax, word ptr [rsi+2]
0x1400c9239  add     rax, rax
0x1400c923c  mov     dword ptr [rdi+rax*8], 0Ch
0x1400c9243  movzx   eax, word ptr [rsi+2]
0x1400c9247  add     rax, rax
0x1400c924a  mov     [rdi+rax*8+8], rcx
0x1400c924f  mov     rcx, [r15+1E8h]
0x1400c9256  lea     rax, [rcx+0E0h]
0x1400c925d  mov     qword ptr [rbp+70h+var_C4+4], rax
0x1400c9261  mov     eax, [rcx+48h]
0x1400c9264  lea     rcx, [rbp+70h+var_C8]
0x1400c9268  mov     [rbp+70h+var_C8], eax
0x1400c926b  movzx   eax, word ptr [rsi+4]
0x1400c926f  add     rax, rax
0x1400c9272  mov     dword ptr [rdi+rax*8], 10h
0x1400c9279  movzx   eax, word ptr [rsi+4]
0x1400c927d  add     rax, rax
0x1400c9280  mov     [rdi+rax*8+8], rcx
0x1400c9285  mov     rax, [r15+1E8h]
0x1400c928c  mov     rcx, [rax+118h]
0x1400c9293  movzx   eax, word ptr [rsi+4Ah]
0x1400c9297  test    rcx, rcx
0x1400c929a  cmovnz  rdx, rcx
0x1400c929e  add     rax, rax
0x1400c92a1  lea     rcx, [rbp+70h+var_C8]
0x1400c92a5  mov     [rbp+70h+var_68], rdx
0x1400c92a9  mov     dword ptr [rdi+rax*8], 0Dh
0x1400c92b0  movzx   eax, word ptr [rsi+4Ah]
0x1400c92b4  add     rax, rax
0x1400c92b7  mov     [rdi+rax*8+8], rdx
0x1400c92bc  movzx   eax, word ptr [rsi+52h]
0x1400c92c0  add     rax, rax
0x1400c92c3  mov     dword ptr [rdi+rax*8], 10h
0x1400c92ca  movzx   eax, word ptr [rsi+52h]
0x1400c92ce  add     rax, rax
0x1400c92d1  mov     [rdi+rax*8+8], rcx
0x1400c92d6  mov     rax, [r15+1E8h]
0x1400c92dd  mov     rax, [rax+90h]
0x1400c92e4  test    rax, rax
0x1400c92e7  jz      short loc_1400C935B
0x1400c92e9  mov     rax, [rax+8]
0x1400c92ed  lea     r8, [rbp+70h+P]
0x1400c92f1  mov     edx, 63716641h
0x1400c92f6  mov     r12, [rax+20h]
0x1400c92fa  movzx   eax, word ptr [r12+8]
0x1400c9300  add     ax, 2
0x1400c9304  movzx   r13d, ax
0x1400c9308  lea     eax, [r13+8]
0x1400c930c  mov     ecx, eax
0x1400c930e  mov     dword ptr [rsp+170h+Size+8], eax
0x1400c9312  call    WfpPoolAllocNonPaged
0x1400c9317  mov     r14, rax
0x1400c931a  test    rax, rax
0x1400c931d  jnz     loc_1400C93A3
0x1400c9323  mov     r8d, dword ptr [rsp+170h+Size+8]; Size
0x1400c9328  xor     edx, edx; Val
0x1400c932a  mov     rcx, [rbp+70h+P]; void *
0x1400c932e  call    memset
0x1400c9333  mov     rcx, [r12]
0x1400c9337  mov     r8d, r13d; Size
0x1400c933a  mov     rax, [rbp+70h+P]
0x1400c933e  mov     [rax], rcx
0x1400c9341  mov     rcx, [rbp+70h+P]
0x1400c9345  mov     rdx, [r12+10h]; Src
0x1400c934a  add     rcx, 8; void *
0x1400c934e  call    memmove
0x1400c9353  movzx   r12d, [rbp+70h+arg_18]
0x1400c935b  movzx   eax, word ptr [rsi+4Ch]
0x1400c935f  lea     rcx, [rsp+170h+Size+8]
0x1400c9364  add     rax, rax
0x1400c9367  mov     byte ptr [rbp+70h+Entry], 1
0x1400c936e  mov     dword ptr [rdi+rax*8], 0Ch
0x1400c9375  movzx   eax, word ptr [rsi+4Ch]
0x1400c9379  add     rax, rax
0x1400c937c  mov     [rdi+rax*8+8], rcx
0x1400c9381  mov     eax, [r15+38h]
0x1400c9385  test    al, 1
0x1400c9387  jz      short loc_1400C93AB
0x1400c9389  mov     r9, [rbp+70h+arg_30]
0x1400c9390  mov     rcx, rsi
0x1400c9393  mov     rdx, [rbp+70h+var_D0]
0x1400c9397  mov     [rsp+170h+var_150], rdi
0x1400c939c  call    WfpAlepAuthInboundFlowSwizzleDestinationInformation
0x1400c93a1  jmp     short loc_1400C93C0
0x1400c93a3  mov     sil, 1
0x1400c93a6  jmp     loc_1400C9E94
0x1400c93ab  movzx   eax, word ptr [rsi+6]
0x1400c93af  mov     rcx, [rbp+70h+arg_30]
0x1400c93b6  add     rax, rax
0x1400c93b9  movups  xmm0, xmmword ptr [rcx]
0x1400c93bc  movups  xmmword ptr [rdi+rax*8], xmm0
0x1400c93c0  movzx   ecx, word ptr [rsi+0Eh]
0x1400c93c4  xor     edx, edx
0x1400c93c6  mov     rax, [rbp+70h+arg_50]
0x1400c93cd  add     rcx, rcx
0x1400c93d0  mov     r9, [rbp+70h+arg_78]
0x1400c93d7  mov     r8d, [rbp+70h+arg_20]
0x1400c93de  movups  xmm0, xmmword ptr [rax]
0x1400c93e1  movups  xmmword ptr [rdi+rcx*8], xmm0
0x1400c93e5  movzx   eax, word ptr [rsi+0Ch]
0x1400c93e9  mov     rcx, r9
0x1400c93ec  add     rax, rax
0x1400c93ef  mov     dword ptr [rdi+rax*8], 1
0x1400c93f6  movzx   eax, word ptr [rsi+0Ch]
0x1400c93fa  add     rax, rax
0x1400c93fd  mov     [rdi+rax*8+8], r8b
0x1400c9402  movzx   eax, word ptr [rsi+20h]
0x1400c9406  add     rax, rax
0x1400c9409  test    r9, r9
0x1400c940c  cmovz   rcx, r15
0x1400c9410  mov     dword ptr [rdi+rax*8], 3
0x1400c9417  lea     rax, [rcx+0A8h]
0x1400c941e  test    rax, rax
0x1400c9421  jz      short loc_1400C943D
0x1400c9423  mov     ecx, [rcx+0C8h]
0x1400c9429  mov     edx, ecx
0x1400c942b  and     edx, 1
0x1400c942e  add     edx, edx
0x1400c9430  mov     eax, edx
0x1400c9432  bts     eax, 10h
0x1400c9436  bt      ecx, 0Bh
0x1400c943a  cmovb   edx, eax
0x1400c943d  mov     eax, [r15+30h]
0x1400c9441  mov     ecx, edx
0x1400c9443  or      ecx, 1
0x1400c9446  cmp     [rbp+70h+arg_68], 0
0x1400c944d  cmovz   ecx, edx
0x1400c9450  or      ecx, 4
0x1400c9453  mov     edx, ecx
0x1400c9455  or      edx, 10h
0x1400c9458  test    al, 10h
0x1400c945a  cmovz   edx, ecx
0x1400c945d  test    r9, r9
0x1400c9460  jz      short loc_1400C9468
0x1400c9462  mov     ecx, [r9+30h]
0x1400c9466  jmp     short loc_1400C946C
0x1400c9468  mov     ecx, [r15+30h]
0x1400c946c  shr     ecx, 1Ah
0x1400c946f  mov     eax, edx
0x1400c9471  bts     eax, 16h
0x1400c9475  and     ecx, 1
0x1400c9478  test    ecx, ecx
0x1400c947a  cmovnz  edx, eax
0x1400c947d  test    r9, r9
0x1400c9480  jz      short loc_1400C9488
0x1400c9482  mov     eax, [r9+30h]
0x1400c9486  jmp     short loc_1400C948C
0x1400c9488  mov     eax, [r15+30h]
  ... truncated ...
```
