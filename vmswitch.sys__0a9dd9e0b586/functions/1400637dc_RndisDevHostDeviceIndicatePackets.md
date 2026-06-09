# RndisDevHostDeviceIndicatePackets

- ea: `0x1400637dc`
- end: `0x140064a98`
- name: `RndisDevHostDeviceIndicatePackets`
- size: `4796`
- prototype: `__int64 __fastcall(_QWORD *, _QWORD *, __int64, int, unsigned __int8, unsigned __int16)`
- caller_count: `1`
- callee_count: `27`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x140063704`

## callees

- `0x1400025a0`
- `0x140006620`
- `0x140006b00`
- `0x14000c824`
- `0x140027a64`
- `0x140027efc`
- `0x140033fa0`
- `0x140034130`
- `0x1400341b4`
- `0x1400478b0`
- `0x140047ad0`
- `0x14004900c`
- `0x14004bfc0`
- `0x14005664c`
- `0x1400572dc`
- `0x1400573e4`
- `0x140057adc`
- `0x140062760`
- `0x1400637dc`
- `0x1400762cc`
- `0x14008497c`
- `0x1401ac478`
- `0x1401bbbc2`
- `0x1401bbcb0`
- `0x1401bbe80`
- `0x1401bc040`
- `0x1401bc340`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14006413d`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140064650`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14006413d`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140064650`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140063a69`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140063b79`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140063a69`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140063b79`
- `ntoskrnl!KeReleaseSpinLock` at `0x140063e92`
- `ntoskrnl!KeReleaseSpinLock` at `0x140064a1a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140063e92`
- `ntoskrnl!KeReleaseSpinLock` at `0x140064a1a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140063cd4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400649fb`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140063cd4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400649fb`

## string_xrefs

- `0x1400648d5`: `numPacketsCombined > 0`

## pseudocode

```c
__int64 __fastcall RndisDevHostDeviceIndicatePackets(
        _QWORD *a1,
        _QWORD *a2,
        __int64 a3,
        int a4,
        unsigned __int8 a5,
        unsigned __int16 a6)
{
  const char *v8; // rdx
  char v9; // r11
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rsi
  __int64 v13; // r15
  __int64 v14; // rax
  int v15; // ecx
  __int64 v16; // rdi
  __int64 v17; // r10
  unsigned int v18; // ebx
  __int64 v19; // r10
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rax
  unsigned __int8 v23; // bl
  __int64 v24; // rax
  __int64 v25; // rax
  unsigned __int64 v26; // rax
  void *v27; // rsp
  __int64 v28; // r8
  ULONG CurrentProcessorNumber; // eax
  __int64 v30; // rbx
  unsigned __int64 v31; // rax
  unsigned __int64 v32; // rax
  void *v33; // rsp
  char v34; // r12
  void *v35; // rsp
  char v36; // r12
  int LsoHint; // r15d
  _QWORD *v38; // rbx
  unsigned int v39; // ebx
  __int64 v40; // rsi
  KIRQL v41; // al
  int v42; // edx
  int v43; // r8d
  _QWORD *v44; // r15
  __int16 v45; // cx
  int v46; // r12d
  __int64 v47; // rax
  int SubAllocations; // ecx
  char v49; // r12
  int v50; // eax
  int v51; // r9d
  unsigned int v52; // eax
  __int64 *v53; // r12
  _QWORD *v54; // rax
  __int64 *v55; // r8
  unsigned int v56; // eax
  int v57; // r11d
  unsigned int v58; // r12d
  _QWORD *v59; // rcx
  __int16 v60; // ax
  char v61; // dl
  char v62; // r15
  __int64 v63; // rax
  __int64 v64; // rax
  unsigned int v65; // eax
  void *v66; // r10
  int v67; // r11d
  unsigned int v68; // r12d
  void *v69; // rax
  int v70; // ecx
  unsigned int v71; // r15d
  _QWORD *v72; // rax
  _QWORD *v73; // r8
  __int64 v74; // rdx
  int v75; // r15d
  char v76; // r9
  __int64 v77; // rcx
  __int64 v78; // r8
  __int64 **v79; // rdx
  __int64 v80; // r12
  __int64 v81; // rdx
  __int64 v82; // r9
  __int64 v83; // r10
  unsigned int v84; // eax
  int v85; // ecx
  int v86; // r9d
  void *v87; // r10
  __int64 v88; // rcx
  __int64 v89; // rax
  unsigned int v90; // eax
  char v91; // al
  __int16 v92; // cx
  char v93; // dl
  char v94; // dl
  __int64 v95; // rdx
  unsigned int v96; // r12d
  _DWORD *v97; // rax
  int v98; // ecx
  __int64 v99; // rax
  __int64 v100; // r8
  volatile signed __int32 *v101; // rcx
  __int64 v102; // r8
  __int64 v103; // rax
  __int64 v104; // r8
  __int64 v105; // rcx
  __int64 v106; // r8
  __int64 v107; // rcx
  __int64 v108; // rax
  int v109; // edx
  int *v110; // rcx
  int *v111; // rcx
  int v112; // edx
  __int64 v113; // r15
  int v114; // edx
  int v115; // ecx
  int v116; // r9d
  __int64 *v117; // rsi
  KIRQL v118; // bl
  _QWORD *v120; // rbx
  unsigned int v121; // [rsp+20h] [rbp-70h]
  int v122; // [rsp+38h] [rbp-58h]
  char v123; // [rsp+90h] [rbp+0h] BYREF
  char v124; // [rsp+91h] [rbp+1h] BYREF
  KIRQL NewIrql; // [rsp+92h] [rbp+2h]
  bool v126; // [rsp+93h] [rbp+3h]
  char v127; // [rsp+94h] [rbp+4h]
  char v128; // [rsp+95h] [rbp+5h]
  char v129; // [rsp+96h] [rbp+6h]
  __int16 v130; // [rsp+98h] [rbp+8h] BYREF
  unsigned int v131; // [rsp+9Ch] [rbp+Ch]
  char v132; // [rsp+A0h] [rbp+10h]
  unsigned int v133; // [rsp+A4h] [rbp+14h]
  _QWORD *v134; // [rsp+A8h] [rbp+18h]
  int v135; // [rsp+B0h] [rbp+20h]
  int v136; // [rsp+B4h] [rbp+24h] BYREF
  void *Src; // [rsp+B8h] [rbp+28h]
  size_t Size; // [rsp+C0h] [rbp+30h]
  __int64 *v139; // [rsp+C8h] [rbp+38h] BYREF
  int v140; // [rsp+D0h] [rbp+40h]
  int v141; // [rsp+D4h] [rbp+44h]
  unsigned int v142; // [rsp+D8h] [rbp+48h] BYREF
  int v143; // [rsp+DCh] [rbp+4Ch]
  void *v144; // [rsp+E0h] [rbp+50h]
  _QWORD *v145; // [rsp+E8h] [rbp+58h]
  __int64 **v146; // [rsp+F0h] [rbp+60h]
  __int64 *v147; // [rsp+F8h] [rbp+68h] BYREF
  __int64 *v148; // [rsp+100h] [rbp+70h] BYREF
  int v149; // [rsp+108h] [rbp+78h] BYREF
  __int128 v150; // [rsp+110h] [rbp+80h] BYREF
  __int128 v151; // [rsp+120h] [rbp+90h] BYREF
  __int64 v152; // [rsp+130h] [rbp+A0h] BYREF
  __int64 v153; // [rsp+138h] [rbp+A8h] BYREF
  __int64 v154; // [rsp+140h] [rbp+B0h] BYREF
  int v155; // [rsp+148h] [rbp+B8h]
  __int128 v156; // [rsp+150h] [rbp+C0h] BYREF
  __int128 v157; // [rsp+160h] [rbp+D0h]
  __int64 v158; // [rsp+170h] [rbp+E0h]
  __int128 v159; // [rsp+178h] [rbp+E8h] BYREF
  __int64 v160; // [rsp+188h] [rbp+F8h]
  _QWORD v161[12]; // [rsp+190h] [rbp+100h] BYREF
  int v162[24]; // [rsp+1F0h] [rbp+160h] BYREF
  _QWORD v163[16]; // [rsp+250h] [rbp+1C0h] BYREF
  _UNKNOWN *retaddr; // [rsp+318h] [rbp+288h]

  v145 = a2;
  v153 = 0;
  v148 = 0;
  v139 = 0;
  v135 = a4;
  memset(v163, 0, sizeof(v163));
  v154 = 0;
  v142 = 0;
  v127 = 0;
  v136 = 0;
  v149 = 0;
  v123 = 0;
  v133 = 0;
  v130 = 0;
  memset(v162, 0, sizeof(v162));
  memset(v161, 0, sizeof(v161));
  v9 = 1;
  v129 = 0;
  if ( (VmsDiagnosticFlags & 1) != 0 )
  {
    if ( a2 )
    {
      v10 = a2[36];
      if ( v10 )
      {
        v11 = *(_QWORD *)(v10 + 16);
        if ( v11 )
        {
          v8 = "RndisDevHostDeviceIndicatePackets";
          *(_DWORD *)(v11 + 184) = 3562;
          *(_QWORD *)(v11 + 176) = "RndisDevHostDeviceIndicatePackets";
          *(_QWORD *)(v11 + 168) = retaddr;
        }
      }
    }
  }
  v12 = *a1;
  v13 = 4;
  v147 = 0;
  v14 = *(_QWORD *)(v12 + 680);
  v15 = *(_DWORD *)(v12 + 856);
  v16 = *(_QWORD *)(v12 + 564);
  v158 = v14;
  v140 = v15;
  if ( v14 )
  {
    v17 = *(_QWORD *)(v14 + 1984);
    v18 = *(_DWORD *)(v12 + 604);
    v127 = *(_BYTE *)(v14 + 1877);
    v133 = v18;
    if ( v17 )
    {
      LOBYTE(v8) = *(_BYTE *)(v17 + 6364);
      VmsOmNicGetRuntimeRscSettings(v14 + 3954, v8, &v130);
      if ( !(_BYTE)v130 || (v123 = v9, !HIBYTE(v130)) )
        v123 = 0;
      if ( (BYTE1(v16) & (unsigned __int8)v9) == 0 || v18 < 4 || (v129 = v9, !*(_BYTE *)(v19 + 12000)) )
        v129 = 0;
    }
  }
  if ( byte_1401F96F0 )
    v13 = HIDWORD(qword_1401F96CC);
  v156 = 0;
  v157 = 0;
  if ( ((unsigned __int8)VmsDiagnosticFlags & (unsigned __int8)v9) != 0 )
  {
    if ( a2 )
    {
      v20 = a2[36];
      if ( v20 )
      {
        v21 = *(_QWORD *)(v20 + 16);
        if ( v21 )
        {
          *(_DWORD *)(v21 + 184) = 75;
          *(_QWORD *)(v21 + 176) = "VmsNblIsSourceNicUntrusted";
          *(_QWORD *)(v21 + 168) = retaddr;
        }
      }
    }
  }
  v22 = a2[36];
  v23 = 0;
  if ( v22 )
  {
    v24 = *(_QWORD *)(v22 + 16);
    if ( v24 )
    {
      v25 = *(_QWORD *)(v24 + 24);
      if ( v25 )
      {
        if ( *(_DWORD *)(v25 + 1872) == 3 && !*(_BYTE *)(v25 + 1877) )
          v23 = v9;
      }
    }
  }
  v26 = 24 * v13 + 15;
  if ( v26 <= 24 * v13 )
    v26 = 0xFFFFFFFFFFFFFF0LL;
  v27 = alloca(v26 & 0xFFFFFFFFFFFFFFF0uLL);
  if ( v23 != 1 || (v28 = qword_1401F96E0) != 0 )
  {
    v162[0] = -267522035;
    CurrentProcessorNumber = KeGetCurrentProcessorNumberEx(0);
    v28 = qword_1401F96E0;
    v162[3] = CurrentProcessorNumber;
    LOBYTE(v162[1]) = 0;
    *(_QWORD *)&v162[6] = 0;
    *(_QWORD *)&v162[4] = 1;
    v162[2] = v23 | (qword_1401F96E0 != 0 ? 4 : 0);
    memset(&v162[11], 0, 24);
    LOBYTE(v162[10]) = 0;
    *(_QWORD *)&v162[8] = &v162[14];
    if ( &v123 )
    {
      v162[17] = v13;
      *(_QWORD *)&v162[18] = &v123;
    }
    else
    {
      v162[17] = 0;
      *(_QWORD *)&v162[18] = 0;
    }
    *(_QWORD *)&v162[20] = &g_BatchLibContext;
  }
  v30 = 4;
  if ( byte_1401F96F0 )
    v30 = HIDWORD(qword_1401F96CC);
  v31 = 24 * v30 + 15;
  if ( v31 <= 24 * v30 )
    v31 = 0xFFFFFFFFFFFFFF0LL;
  v32 = v31 & 0xFFFFFFFFFFFFFFF0uLL;
  v33 = alloca(v32);
  v34 = v127;
  v35 = alloca(v32);
  if ( v127 || v28 )
  {
    LODWORD(v161[0]) = -267522035;
    HIDWORD(v161[1]) = KeGetCurrentProcessorNumberEx(0);
    v161[3] = v162;
    BYTE4(v161[0]) = 0;
    v161[2] = 1;
    v161[4] = &v161[7];
    memset(&v161[6], 0, 20);
    LODWORD(v161[1]) = (v34 == 0 ? 2 : 0) | (qword_1401F96E0 != 0 ? 4 : 0);
    HIDWORD(v161[5]) = 0;
    LOBYTE(v161[5]) = 0;
    if ( &v123 )
    {
      HIDWORD(v161[8]) = v30;
      v161[9] = &v123;
    }
    else
    {
      HIDWORD(v161[8]) = 0;
      v161[9] = 0;
    }
    v161[10] = &g_BatchLibContext;
  }
  v160 = VmsVmNicTryAcquireChannelOrPrimaryForSend(v12, &a6);
  if ( !v160 )
  {
    v36 = (char)v145;
    LsoHint = -1073741661;
    v38 = v145;
    do
    {
      v121 = -1073741661;
      ((void (__fastcall *)(_QWORD, _QWORD *, __int64))a1[3])(*a1, v38, 1);
      v38 = (_QWORD *)*v38;
    }
    while ( v38 );
    goto LABEL_211;
  }
  v39 = v135;
  v40 = 0;
  v146 = &v147;
  v143 = 0;
  Src = 0;
  if ( !VmsIsRscOverVmBusEnabled || (v16 & 0x80u) == 0LL || !v123 || (v128 = 1, v133 < 2) )
    v128 = 0;
  v41 = KeAcquireSpinLockRaiseToDpc(a1 + 13);
  v44 = v145;
  NewIrql = v41;
LABEL_56:
  v45 = *((_WORD *)v44 + 160);
  LOBYTE(v43) = 14;
  v123 = 0;
  v46 = 1;
  v124 = 14;
  v150 = 0;
  v151 = 0;
  if ( v128 == 1 )
  {
    if ( v45 )
    {
      v123 = 1;
      v46 = 3;
    }
    else
    {
      v47 = v44[20];
      if ( v47 && (v47 & 0x40000000) != 0 )
      {
        v123 = 1;
        LOWORD(v150) = 4;
        v46 = 3;
      }
    }
LABEL_65:
    HIDWORD(v151) = 2 - (a5 != 0);
    SubAllocations = SegLibOffloadIteratorInitialize((unsigned int)v163, (_DWORD)v44, v43, (unsigned int)&v150, v46, 0);
    if ( SubAllocations >= 0 )
    {
      v49 = v123;
      while ( 1 )
      {
        v50 = SegLibOffloadIteratorPacketSize(v163);
        LOBYTE(v51) = v49;
        SubAllocations = RndisDevHostInternalAllocateSubAllocations(
                           (_DWORD)a1,
                           v50,
                           v140,
                           v51,
                           (__int64)&v136,
                           (__int64)&v148,
                           (__int64)&v139);
        if ( SubAllocations < 0 )
          break;
        *v146 = v148;
        v146 = (__int64 **)v139;
        v52 = SegLibOffloadIteratorPacketSize(v163);
        if ( !(unsigned __int8)SegLibOffloadIteratorNext(v163, v52) )
        {
          v44 = (_QWORD *)*v44;
          if ( v44 )
            goto LABEL_56;
          goto LABEL_72;
        }
      }
    }
    goto LABEL_71;
  }
  if ( !v45 )
    goto LABEL_65;
  SubAllocations = NvLibRscGetLsoHint((_DWORD)v44, v42, (unsigned int)&v150 + 8, (unsigned int)&v124, (__int64)&v151);
  if ( SubAllocations >= 0 )
  {
    LOWORD(v150) = v150 | 1;
    LOBYTE(v43) = v124;
    goto LABEL_65;
  }
LABEL_71:
  v121 = SubAllocations;
  ((void (__fastcall *)(_QWORD, _QWORD *, __int64, _QWORD))a1[3])(*a1, v44, 1, 0);
LABEL_72:
  KeReleaseSpinLock(a1 + 13, NewIrql);
  v36 = (char)v145;
  v134 = v145;
  NewIrql = 1;
  v123 = 0;
  v126 = 0;
  v148 = 0;
  v141 = v135;
  if ( !v147 )
    goto LABEL_210;
  v53 = v147;
  v54 = a1 + 32;
  do
  {
    LsoHint = RndisDevDeviceAcquireOperation(v54, &v153, a6);
    if ( LsoHint < 0 )
    {
      v120 = v145;
      do
      {
        v121 = LsoHint;
        ((void (__fastcall *)(_QWORD, _QWORD *, __int64))a1[3])(*a1, v120, 1);
        v120 = (_QWORD *)*v120;
      }
      while ( v120 );
LABEL_216:
      v36 = (char)v145;
      goto LABEL_211;
    }
    v56 = 0;
    v139 = v53;
    v133 = 0;
    v136 = 0;
    if ( *((_DWORD *)a1 + 11) )
    {
      v57 = 1;
      while ( 1 )
      {
        if ( !v53 || v56 > *((_DWORD *)a1 + 10) && NewIrql == (_BYTE)v57 )
          goto LABEL_201;
        v58 = *((_DWORD *)v53 + 3) - v140;
        if ( NewIrql )
          break;
LABEL_101:
        v152 = v163[5];
        v65 = SegLibOffloadIteratorPacketSize(v163);
        if ( v65 > v58 )
          v65 = v58;
        v68 = v65 + v140;
        v131 = v65;
        LODWORD(Size) = v65 + v140;
        v69 = (void *)(*((unsigned int *)v139 + 4) + a1[7]);
        v144 = v69;
        if ( v127 == (_BYTE)v66 )
        {
          v70 = dword_1401F9940;
          Src = v66;
          if ( v68 <= dword_1401F9940 )
          {
            v71 = DWORD1(v156) % VmsVmBatchCopyRndisBatchSize;
            if ( !(DWORD1(v156) % VmsVmBatchCopyRndisBatchSize) )
            {
              v72 = ExAllocateFromNPagedLookasideList(&stru_1401F9980);
              LOBYTE(v66) = 0;
              v67 = 1;
              v73 = v72;
              if ( v72 )
              {
                if ( (VmsDiagnosticFlags & 2) != 0 )
                {
                  v74 = 5440LL * (unsigned int)v156;
                  _InterlockedAdd16((volatile signed __int16 *)((char *)VmsPlanCpuTable + v74 + 504), 1u);
                  _InterlockedAdd((volatile signed __int32 *)((char *)VmsPlanCpuTable + v74 + 488), 1u);
                }
                *v72 = 0;
                if ( DWORD1(v156) )
                  **((_QWORD **)&v157 + 1) = v72;
                else
                  *(_QWORD *)&v157 = v72;
                v70 = dword_1401F9940;
                *((_QWORD *)&v157 + 1) = v72;
LABEL_114:
                DWORD1(v156) += v67;
                Src = (char *)v73 + v70 * v71 + 8;
                memset(Src, 0, v68);
                LOBYTE(v66) = 0;
                LOBYTE(v67) = 1;
                if ( (VmsDiagnosticFlags & 2) != 0 && !BYTE8(v156) )
                {
                  BYTE8(v156) = 1;
                  _InterlockedAdd16((volatile signed __int16 *)VmsPlanCpuTable + 2720 * (unsigned int)v156 + 251, 1u);
                }
              }
              LODWORD(v69) = (_DWORD)v144;
              goto LABEL_118;
            }
            v73 = (_QWORD *)*((_QWORD *)&v157 + 1);
            goto LABEL_114;
          }
        }
LABEL_118:
        v75 = (int)v69;
        if ( Src )
          v75 = (int)Src;
        if ( NewIrql != (_BYTE)v66 && v126 || (v76 = (char)v66, !v126) )
          v76 = v67;
        v124 = v76;
        if ( v129 != (_BYTE)v66 )
          v40 = v134[44];
        if ( (v16 & 0x40) != 0 )
          v77 = v134[38] & 0xFFFFFF;
        else
          v77 = 0;
        if ( (v16 & 0x200) != 0 )
          v78 = v134[31];
        else
          v78 = 0;
        if ( !v123 || (v79 = &v148, !v126) )
          LODWORD(v79) = 0;
        v80 = RndisDevHostInternalPrepareRndisPacketMessage(
                v75,
                (_DWORD)v79,
                (unsigned int)&v154,
                (unsigned int)&v142,
                Size,
                v131,
                v76,
                v141 & (unsigned int)v152,
                v163[10],
                v163[11],
                v78,
                v77,
                *((_DWORD *)v134 + 52),
                *((_DWORD *)v134 + 54),
                (unsigned __int64)&v163[12] & -(__int64)(v123 != 0),
                v123 != 0 ? v163[13] : 0,
                *((_DWORD *)v134 + 48),
                v40);
        LsoHint = SegLibDeferredOffloadIteratorCopyPacket((int)v162);
        if ( LsoHint < 0 )
        {
LABEL_200:
          v121 = LsoHint;
          ((void (__fastcall *)(_QWORD, _QWORD *, __int64))a1[3])(*a1, v134, 1);
          goto LABEL_201;
        }
        if ( v124 )
        {
          v82 = v142;
          v83 = v154;
          v159 = 0;
          v84 = *(_DWORD *)(v142 + v154);
          v152 = v84;
          if ( !v123 )
          {
            *(_QWORD *)&v159 = v80;
            LOBYTE(v130) = (v84 & 0x24) != 0;
            DWORD2(v159) = v131;
            v81 = v84 & 9;
            v132 = (v84 & 9) != 0;
            v124 = (v84 & 0x12) != 0;
            if ( (v84 & 0x24) == 0 || (v84 & 9) == 0 && (v84 & 0x12) == 0 )
            {
              v85 = (v39 >> 3) & 1;
              v81 = v39 >> 5;
              v155 = v85;
              LOBYTE(v81) = (v39 & 0x20) != 0;
              LODWORD(v146) = v81;
              if ( (v39 & 0x20) != 0 || (_BYTE)v85 || (v39 & 0x10) != 0 )
              {
                BLFlushBatchOpContextEx(v162, 0, 1);
                LOBYTE(v86) = (_BYTE)v146;
                VncChecksumVerifyHeaders(
                  (unsigned int)v162,
                  (unsigned int)&v159,
                  0,
                  v86,
                  v155,
                  (v39 & 0x10) != 0,
                  v130,
                  v132,
                  v124,
                  (__int64)&v152,
                  v158);
                v84 = v152;
                v82 = v142;
                v83 = v154;
              }
            }
            v84 &= v39;
          }
          *(_DWORD *)(v82 + v83) = v84;
        }
        v87 = Src;
        if ( Src )
        {
          v88 = v161[10];
          if ( *(_BYTE *)(v161[10] + 1LL) == 1 && !BYTE4(v161[0]) )
          {
            v89 = 0;
            BYTE4(v161[0]) = 1;
            if ( HIDWORD(v161[1]) != -1 )
            {
              v81 = *(_QWORD *)(v161[10] + 24LL);
              if ( v81 )
                v89 = v81 + 20LL * HIDWORD(v161[1]);
            }
            _InterlockedAdd16((volatile signed __int16 *)(v89 + 16), 1u);
            v88 = v161[10];
          }
          v90 = *(_DWORD *)(v88 + 4);
          if ( !v90 )
          {
            if ( HIDWORD(v161[2]) )
            {
              LOBYTE(v81) = 1;
              BLFlushBatchOpContextEx(v161, v81, 0);
              v88 = v161[10];
              v87 = Src;
            }
            if ( (v161[1] & 5) == 5 || (v161[1] & 6) == 6 )
            {
              (*(void (**)(void))(v88 + 32))();
              memmove(v144, Src, (unsigned int)Size);
              (*(void (**)(void))(v161[10] + 40LL))();
            }
            else
            {
              memmove(v144, v87, (unsigned int)Size);
            }
            goto LABEL_160;
          }
          v95 = v161[4];
          v96 = *(_DWORD *)(v161[4] + 8LL);
          if ( v96 >= *(_DWORD *)(v161[4] + 12LL) )
          {
            v96 = 0;
            if ( LODWORD(v161[2]) >= v90 )
            {
              LOBYTE(v95) = 1;
              goto LABEL_168;
            }
            v97 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v88 + 64));
            v95 = (__int64)v97;
            if ( v97 )
            {
              *(_QWORD *)v97 = 0;
              v97[2] = 0;
              v98 = *(_DWORD *)(v161[10] + 8LL);
              *((_QWORD *)v97 + 2) = v97 + 6;
              v97[3] = v98;
              *(_QWORD *)v161[4] = v97;
              ++LODWORD(v161[2]);
              v161[4] = v97;
              if ( *(_BYTE *)(v161[10] + 1LL) == 1 )
              {
                v99 = 0;
                if ( HIDWORD(v161[1]) != -1 )
                {
                  v100 = *(_QWORD *)(v161[10] + 24LL);
                  if ( v100 )
                    v99 = v100 + 20LL * HIDWORD(v161[1]);
                }
                _InterlockedAdd16((volatile signed __int16 *)(v99 + 12), 1u);
                v101 = 0;
                if ( HIDWORD(v161[1]) != -1 )
                {
                  v102 = *(_QWORD *)(v161[10] + 24LL);
                  if ( v102 )
                    v101 = (volatile signed __int32 *)(v102 + 20LL * HIDWORD(v161[1]));
                }
                _InterlockedAdd(v101, 1u);
              }
            }
            else
            {
              v95 = 1;
LABEL_168:
              BLFlushBatchOpContextEx(v161, v95, 0);
              v95 = (__int64)&v161[7];
            }
            v87 = Src;
          }
          ++HIDWORD(v161[2]);
          ++*(_DWORD *)(v95 + 8);
          if ( *(_BYTE *)(v161[10] + 1LL) == 1 )
          {
            v103 = 0;
            if ( HIDWORD(v161[1]) != -1 )
            {
              v104 = *(_QWORD *)(v161[10] + 24LL);
              if ( v104 )
                v103 = v104 + 20LL * HIDWORD(v161[1]);
            }
            _InterlockedAdd16((volatile signed __int16 *)(v103 + 14), 1u);
            v105 = 0;
            if ( HIDWORD(v161[1]) != -1 )
            {
              v106 = *(_QWORD *)(v161[10] + 24LL);
              if ( v106 )
                v105 = v106 + 20LL * HIDWORD(v161[1]);
            }
            _InterlockedAdd((volatile signed __int32 *)(v105 + 4), 1u);
          }
          v107 = 3LL * v96;
          v108 = *(_QWORD *)(v95 + 16);
          v109 = (16 * Size) | 1;
          *(_QWORD *)(v108 + 8 * v107) = v144;
          *(_DWORD *)(v108 + 8 * v107 + 16) = v109;
          *(_QWORD *)(v108 + 8 * v107 + 8) = v87;
        }
LABEL_160:
        v91 = SegLibOffloadIteratorNext(v163, v131);
        v55 = v148;
        if ( !v148 )
          goto LABEL_192;
        v92 = v143;
        *(_BYTE *)v148 = v57;
        *((_WORD *)v55 + 1) = v92;
        if ( !v126 )
          goto LABEL_192;
        v93 = v57 | *((_BYTE *)v55 + 1);
        *((_BYTE *)v55 + 1) = v93;
        if ( NewIrql )
        {
          v94 = v93 | 2;
LABEL_191:
          *((_BYTE *)v55 + 1) = v94;
          goto LABEL_192;
        }
        if ( !v91 )
        {
          v94 = v93 | 4;
          goto LABEL_191;
        }
LABEL_192:
        v146 = (__int64 **)v139;
        NewIrql = 0;
        v53 = (__int64 *)*v139;
        v139 = (__int64 *)*v139;
        if ( !v91 )
        {
          if ( ++v136 >= (unsigned int)VmsVmMaxNBLsPerFlush )
          {
            v110 = (int *)v161;
            LOBYTE(v55) = v57;
            if ( v127 )
              v110 = v162;
            BLFlushBatchOpContextEx(v110, 0, v55);
            VncFlushBatchRndisContext(&v156);
            v136 = 0;
            v57 = 1;
          }
          NewIrql = v57;
          v134 = (_QWORD *)*v134;
        }
        v56 = v57 + v133;
        v133 = v56;
        if ( v56 >= *((_DWORD *)a1 + 11) )
          goto LABEL_201;
      }
      v59 = v134;
      if ( !v134 )
        goto LABEL_201;
      v60 = *((_WORD *)v134 + 160);
      v61 = 0;
      v62 = 14;
      v123 = 0;
      v124 = 14;
      v150 = 0;
      v126 = 0;
      v151 = 0;
      v148 = 0;
      v131 = 0;
      if ( v128 != (_BYTE)v57 )
      {
        v141 = v135;
        if ( v60 )
        {
          LsoHint = NvLibRscGetLsoHint((_DWORD)v134, v135, (unsigned int)&v150 + 8, (unsigned int)&v124, (__int64)&v151);
          if ( LsoHint < 0 )
            goto LABEL_200;
          v62 = v124;
          v57 = 1;
          LOWORD(v150) = v150 | 1;
          v59 = v134;
        }
        goto LABEL_94;
      }
      if ( !v60 )
      {
        v63 = v134[20];
        if ( !v63 || (v63 & 0x40000000) == 0 )
          goto LABEL_88;
        LOWORD(v150) = 4;
      }
      v64 = v134[1];
      v61 = v57;
      v123 = v57;
      v131 = 2;
      v126 = *(_DWORD *)(v64 + 24) > v58;
LABEL_88:
      LODWORD(v55) = 424;
      if ( !v61 )
        LODWORD(v55) = v135;
      v141 = (int)v55;
LABEL_94:
      if ( a5 )
      {
        HIDWORD(v151) = v57;
      }
      else
      {
        VncGetTxChecksumOffloadInfo(v59, (char *)&v151 + 8, &v150);
        HIDWORD(v151) = 2;
      }
      LOBYTE(v55) = v62;
      LsoHint = SegLibOffloadIteratorInitialize(
                  (unsigned int)v163,
                  (_DWORD)v134,
                  (_DWORD)v55,
                  (unsigned int)&v150,
                  v131,
                  (__int64)&v149);
      if ( LsoHint < 0 )
        goto LABEL_200;
      if ( (v149 & 2) != 0 )
        VmsNblHelperIncrementSuccessCsoStats(v134, ((unsigned __int64)&v150 + 8) & -(__int64)((v150 & 1) != 0), 0, v158);
      LOWORD(v143) = v143 + 1;
      goto LABEL_101;
    }
LABEL_201:
    v111 = (int *)v161;
    LOBYTE(v55) = 1;
    if ( v127 )
      v111 = v162;
    BLFlushBatchOpContextEx(v111, 0, v55);
    VncFlushBatchRndisContext(&v156);
    v163[7] &= -(__int64)(NewIrql != 0);
    if ( LsoHint < 0 )
    {
      RndisDevDeviceReleaseOperation(a1 + 32, v153);
      goto LABEL_216;
    }
    if ( !v133 )
    {
      WPP_RECORDER_SF_s(
        VmsIfrLog,
        v112,
        19,
        64,
        (__int64)WPP_da01b6527bcc3df100ab88c9816e11cf_Traceguids,
        (__int64)"numPacketsCombined > 0");
      MicrosoftTelemetryAssertTriggeredNoArgsKM();
    }
    v113 = v153;
    *v146 = 0;
    v53 = v139;
    *(_QWORD *)(v113 + 904) = v147;
    v147 = v53;
    if ( a6 == 0xFFFF )
    {
      WPP_RECORDER_SF_s(
        VmsIfrLog,
        v112,
        19,
        65,
        (__int64)WPP_da01b6527bcc3df100ab88c9816e11cf_Traceguids,
        (__int64)"ChannelIndex < 0xFFFF");
      MicrosoftTelemetryAssertTriggeredNoArgsKM();
    }
    v121 = a6 | 0xFFFF0000;
    ((void (__fastcall *)(_QWORD, _QWORD, __int64, _QWORD))a1[2])(*a1, *(_QWORD *)(v113 + 904), v113, 0);
    v54 = a1 + 32;
  }
  while ( v139 );
  v36 = (char)v145;
LABEL_210:
  LsoHint = 0;
LABEL_211:
  VmsVmNicReleaseChannel(v160);
  if ( LsoHint < 0 )
  {
    WPP_RECORDER_SF_qqLDdLd(v115, v114, a5, v116, v121, (char)a1, v36, v122, v135, a5, a6, LsoHint);
    v117 = v147;
    if ( v147 )
    {
      v118 = KeAcquireSpinLockRaiseToDpc(a1 + 13);
      RndisDevHostInternalFreeSubAllocation(a1, v117);
      KeReleaseSpinLock(a1 + 13, v118);
    }
  }
  return (unsigned int)LsoHint;
}

```

## disassembly

```asm
0x1400637dc  push    rbp
0x1400637de  push    rbx
0x1400637df  push    rsi
0x1400637e0  push    rdi
0x1400637e1  push    r12
0x1400637e3  push    r14
0x1400637e5  push    r15
0x1400637e7  sub     rsp, 2E0h
0x1400637ee  lea     rbp, [rsp+90h]
0x1400637f6  mov     rax, cs:__security_cookie
0x1400637fd  xor     rax, rbp
0x140063800  mov     [rbp+280h+var_40], rax
0x140063807  xor     edi, edi
0x140063809  mov     [rbp+280h+var_228], rdx
0x14006380d  mov     r12, rdx
0x140063810  mov     [rbp+280h+var_1D8], rdi
0x140063817  mov     r14, rcx
0x14006381a  mov     [rbp+280h+var_210], rdi
0x14006381e  xor     edx, edx; Val
0x140063820  mov     [rbp+280h+var_248], rdi
0x140063824  lea     rcx, [rbp+280h+var_C0]; void *
0x14006382b  mov     [rbp+280h+var_260], r9d
0x14006382f  mov     r8d, 80h; Size
0x140063835  call    memset
0x14006383a  lea     ebx, [rdi+60h]
0x14006383d  mov     [rbp+280h+var_1D0], rdi
0x140063844  mov     r8d, ebx; Size
0x140063847  mov     [rbp+280h+var_238], edi
0x14006384a  xor     edx, edx; Val
0x14006384c  mov     [rbp+280h+var_27C], dil
0x140063850  lea     rcx, [rbp+280h+var_120]; void *
0x140063857  mov     [rbp+280h+var_25C], edi
0x14006385a  mov     [rbp+280h+var_208], edi
0x14006385d  mov     [rbp+280h+var_280], dil
0x140063861  mov     [rbp+280h+var_26C], edi
0x140063864  mov     [rbp+280h+var_278], di
0x140063868  call    memset
0x14006386d  mov     r8d, ebx; Size
0x140063870  lea     rcx, [rbp+280h+var_180]; void *
0x140063877  xor     edx, edx; Val
0x140063879  call    memset
0x14006387e  mov     eax, cs:VmsDiagnosticFlags
0x140063884  lea     r11d, [rdi+1]
0x140063888  mov     rcx, [rbp+288h]
0x14006388f  xor     r9d, r9d
0x140063892  mov     [rbp+280h+var_27A], r9b
0x140063896  test    r11b, al
0x140063899  jz      short loc_1400638D5
0x14006389b  test    r12, r12
0x14006389e  jz      short loc_1400638D5
0x1400638a0  mov     rax, [r12+120h]
0x1400638a8  test    rax, rax
0x1400638ab  jz      short loc_1400638D5
0x1400638ad  mov     rax, [rax+10h]
0x1400638b1  test    rax, rax
0x1400638b4  jz      short loc_1400638D5
0x1400638b6  lea     rdx, aRndisdevhostde_2; "RndisDevHostDeviceIndicatePackets"
0x1400638bd  mov     dword ptr [rax+0B8h], 0DEAh
0x1400638c7  mov     [rax+0B0h], rdx
0x1400638ce  mov     [rax+0A8h], rcx
0x1400638d5  mov     rsi, [r14]
0x1400638d8  mov     r15d, 4
0x1400638de  mov     [rbp+280h+var_218], r9
0x1400638e2  mov     rax, [rsi+2A8h]
0x1400638e9  mov     ecx, [rsi+358h]
0x1400638ef  mov     rdi, [rsi+234h]
0x1400638f6  mov     [rbp+280h+var_1A0], rax
0x1400638fd  mov     [rbp+280h+var_240], ecx
0x140063900  test    rax, rax
0x140063903  jz      short loc_140063973
0x140063905  mov     r10, [rax+7C0h]
0x14006390c  mov     cl, [rax+755h]
0x140063912  mov     ebx, [rsi+25Ch]
0x140063918  mov     [rbp+280h+var_27C], cl
0x14006391b  mov     [rbp+280h+var_26C], ebx
0x14006391e  test    r10, r10
0x140063921  jz      short loc_140063973
0x140063923  mov     dl, [r10+18DCh]
0x14006392a  lea     rcx, [rax+0F72h]
0x140063931  lea     r8, [rbp+280h+var_278]
0x140063935  call    VmsOmNicGetRuntimeRscSettings
0x14006393a  xor     r9d, r9d
0x14006393d  cmp     byte ptr [rbp+280h+var_278], r9b
0x140063941  jz      short loc_14006394D
0x140063943  mov     [rbp+280h+var_280], r11b
0x140063947  cmp     byte ptr [rbp+280h+var_278+1], r9b
0x14006394b  jnz     short loc_140063951
0x14006394d  mov     [rbp+280h+var_280], r9b
0x140063951  mov     rax, rdi
0x140063954  shr     rax, 8
0x140063958  test    r11b, al
0x14006395b  jz      short loc_14006396F
0x14006395d  cmp     ebx, r15d
0x140063960  jb      short loc_14006396F
0x140063962  mov     [rbp+280h+var_27A], r11b
0x140063966  cmp     [r10+2EE0h], r9b
0x14006396d  jnz     short loc_140063973
0x14006396f  mov     [rbp+280h+var_27A], r9b
0x140063973  cmp     cs:byte_1401F96F0, r9b
0x14006397a  xorps   xmm0, xmm0
0x14006397d  mov     eax, cs:VmsDiagnosticFlags
0x140063983  cmovnz  r15d, dword ptr cs:qword_1401F96CC+4
0x14006398b  mov     rcx, [rbp+288h]
0x140063992  movups  [rbp+280h+var_1C0], xmm0
0x140063999  movups  [rbp+280h+var_1B0], xmm0
0x1400639a0  test    r11b, al
0x1400639a3  jz      short loc_1400639DF
0x1400639a5  test    r12, r12
0x1400639a8  jz      short loc_1400639DF
0x1400639aa  mov     rax, [r12+120h]
0x1400639b2  test    rax, rax
0x1400639b5  jz      short loc_1400639DF
0x1400639b7  mov     rax, [rax+10h]
0x1400639bb  test    rax, rax
0x1400639be  jz      short loc_1400639DF
0x1400639c0  lea     rdx, aVmsnblissource; "VmsNblIsSourceNicUntrusted"
0x1400639c7  mov     dword ptr [rax+0B8h], 4Bh ; 'K'
0x1400639d1  mov     [rax+0B0h], rdx
0x1400639d8  mov     [rax+0A8h], rcx
0x1400639df  mov     rax, [r12+120h]
0x1400639e7  mov     bl, r9b
0x1400639ea  test    rax, rax
0x1400639ed  jz      short loc_140063A16
0x1400639ef  mov     rax, [rax+10h]
0x1400639f3  test    rax, rax
0x1400639f6  jz      short loc_140063A16
0x1400639f8  mov     rax, [rax+18h]
0x1400639fc  test    rax, rax
0x1400639ff  jz      short loc_140063A16
0x140063a01  cmp     dword ptr [rax+750h], 3
0x140063a08  jnz     short loc_140063A16
0x140063a0a  cmp     [rax+755h], r9b
0x140063a11  jnz     short loc_140063A16
0x140063a13  mov     bl, r11b
0x140063a16  lea     rcx, [r15+r15*2]
0x140063a1a  mov     rdx, 0FFFFFFFFFFFFFF0h
0x140063a24  shl     rcx, 3
0x140063a28  lea     rax, [rcx+0Fh]
0x140063a2c  cmp     rax, rcx
0x140063a2f  ja      short loc_140063A34
0x140063a31  mov     rax, rdx
0x140063a34  and     rax, 0FFFFFFFFFFFFFFF0h
0x140063a38  call    __chkstk_0
0x140063a3d  sub     rsp, rax
0x140063a40  lea     r12, [rsp+310h+var_280]
0x140063a48  cmp     bl, 1
0x140063a4b  jnz     short loc_140063A5D
0x140063a4d  mov     r8, cs:qword_1401F96E0
0x140063a54  test    r8, r8
0x140063a57  jz      loc_140063B20
0x140063a5d  xor     ecx, ecx; ProcNumber
0x140063a5f  mov     [rbp+280h+var_120], 0F00DF00Dh
0x140063a69  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140063a70  nop     dword ptr [rax+rax+00h]
0x140063a75  mov     r8, cs:qword_1401F96E0
0x140063a7c  xor     r9d, r9d
0x140063a7f  mov     [rbp+280h+var_114], eax
0x140063a85  mov     rax, r8
0x140063a88  neg     rax
0x140063a8b  movzx   edx, bl
0x140063a8e  lea     rax, [rbp+280h+var_E8]
0x140063a95  mov     [rbp+280h+var_11C], r9b
0x140063a9c  sbb     ecx, ecx
0x140063a9e  mov     [rbp+280h+var_108], r9
0x140063aa5  and     ecx, 4
0x140063aa8  mov     [rbp+280h+var_110], 1
0x140063ab3  or      ecx, edx
0x140063ab5  mov     [rbp+280h+var_F0], r9
0x140063abc  mov     [rbp+280h+var_118], ecx
0x140063ac2  mov     [rbp+280h+var_F4], r9d
0x140063ac9  mov     [rbp+280h+var_F8], r9b
0x140063ad0  mov     [rbp+280h+var_E8], r9
0x140063ad7  mov     [rbp+280h+var_E0], r9d
0x140063ade  mov     [rbp+280h+var_100], rax
0x140063ae5  test    r12, r12
0x140063ae8  jz      short loc_140063AFA
0x140063aea  mov     [rbp+280h+var_DC], r15d
0x140063af1  mov     [rbp+280h+var_D8], r12
0x140063af8  jmp     short loc_140063B08
0x140063afa  mov     [rbp+280h+var_DC], r9d
0x140063b01  mov     [rbp+280h+var_D8], r9
0x140063b08  lea     rax, g_BatchLibContext
0x140063b0f  mov     rdx, 0FFFFFFFFFFFFFF0h
0x140063b19  mov     [rbp+280h+var_D0], rax
0x140063b20  cmp     cs:byte_1401F96F0, r9b
0x140063b27  mov     ebx, 4
0x140063b2c  cmovnz  ebx, dword ptr cs:qword_1401F96CC+4
0x140063b33  lea     rcx, [rbx+rbx*2]
0x140063b37  shl     rcx, 3
0x140063b3b  lea     rax, [rcx+0Fh]
0x140063b3f  cmp     rax, rcx
0x140063b42  ja      short loc_140063B47
0x140063b44  mov     rax, rdx
0x140063b47  and     rax, 0FFFFFFFFFFFFFFF0h
0x140063b4b  call    __chkstk_0
0x140063b50  mov     r12b, [rbp+280h+var_27C]
0x140063b54  sub     rsp, rax
0x140063b57  lea     r15, [rsp+310h+var_280]
0x140063b5f  test    r12b, r12b
0x140063b62  jnz     short loc_140063B6D
0x140063b64  test    r8, r8
0x140063b67  jz      loc_140063C34
0x140063b6d  xor     ecx, ecx; ProcNumber
0x140063b6f  mov     [rbp+280h+var_180], 0F00DF00Dh
0x140063b79  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140063b80  nop     dword ptr [rax+rax+00h]
0x140063b85  mov     [rbp+280h+var_174], eax
0x140063b8b  lea     rax, [rbp+280h+var_120]
0x140063b92  mov     [rbp+280h+var_168], rax
0x140063b99  mov     al, r12b
0x140063b9c  neg     al
0x140063b9e  mov     [rbp+280h+var_17C], 0
0x140063ba5  mov     rax, cs:qword_1401F96E0
0x140063bac  sbb     edx, edx
0x140063bae  mov     [rbp+280h+var_170], 1
0x140063bb9  not     edx
0x140063bbb  and     edx, 2
0x140063bbe  neg     rax
0x140063bc1  lea     rax, [rbp+280h+var_148]
0x140063bc8  sbb     ecx, ecx
0x140063bca  mov     [rbp+280h+var_160], rax
0x140063bd1  xor     r12d, r12d
0x140063bd4  and     ecx, 4
0x140063bd7  or      ecx, edx
0x140063bd9  mov     [rbp+280h+var_150], r12
0x140063be0  mov     [rbp+280h+var_178], ecx
0x140063be6  mov     [rbp+280h+var_154], r12d
0x140063bed  mov     [rbp+280h+var_158], r12b
0x140063bf4  mov     [rbp+280h+var_148], r12
0x140063bfb  mov     [rbp+280h+var_140], r12d
0x140063c02  test    r15, r15
0x140063c05  jz      short loc_140063C16
0x140063c07  mov     [rbp+280h+var_13C], ebx
0x140063c0d  mov     [rbp+280h+var_138], r15
0x140063c14  jmp     short loc_140063C24
0x140063c16  mov     [rbp+280h+var_13C], r12d
0x140063c1d  mov     [rbp+280h+var_138], r12
0x140063c24  lea     rax, g_BatchLibContext
0x140063c2b  mov     [rbp+280h+var_130], rax
0x140063c32  jmp     short loc_140063C37
0x140063c34  xor     r12d, r12d
0x140063c37  lea     rdx, [rbp+280h+arg_28]
0x140063c3e  mov     rcx, rsi
0x140063c41  call    VmsVmNicTryAcquireChannelOrPrimaryForSend
0x140063c46  mov     [rbp+280h+var_188], rax
0x140063c4d  test    rax, rax
0x140063c50  jnz     short loc_140063C8F
0x140063c52  mov     r12, [rbp+280h+var_228]
0x140063c56  mov     r15d, 0C00000A3h
0x140063c5c  mov     rbx, r12
0x140063c5f  mov     rax, [r14+18h]
0x140063c63  xor     r9d, r9d
0x140063c66  mov     rcx, [r14]
0x140063c69  mov     rdx, rbx
0x140063c6c  mov     dword ptr [rsp+310h+var_2E8], 0E0002076h
0x140063c74  mov     dword ptr [rsp+310h+var_2F0], r15d
0x140063c79  lea     r8d, [r9+1]
0x140063c7d  call    _guard_dispatch_icall
0x140063c82  mov     rbx, [rbx]
0x140063c85  test    rbx, rbx
0x140063c88  jnz     short loc_140063C5F
0x140063c8a  jmp     loc_1400649A7
0x140063c8f  cmp     cs:VmsIsRscOverVmBusEnabled, r12b
0x140063c96  lea     rax, [rbp+280h+var_218]
0x140063c9a  mov     ebx, [rbp+280h+var_260]
0x140063c9d  mov     rsi, r12
0x140063ca0  mov     [rbp+280h+var_220], rax
0x140063ca4  mov     [rbp+280h+var_234], r12d
0x140063ca8  mov     [rbp+280h+Src], r12
0x140063cac  jz      short loc_140063CCC
0x140063cae  mov     al, dil
0x140063cb1  mov     ecx, 1
0x140063cb6  shr     al, 7
0x140063cb9  test    cl, al
0x140063cbb  jz      short loc_140063CCC
0x140063cbd  cmp     [rbp+280h+var_280], r12b
0x140063cc1  jz      short loc_140063CCC
0x140063cc3  cmp     [rbp+280h+var_26C], 2
0x140063cc7  mov     [rbp+280h+var_27B], cl
0x140063cca  jnb     short loc_140063CD0
0x140063ccc  mov     [rbp+280h+var_27B], r12b
0x140063cd0  lea     rcx, [r14+68h]; SpinLock
0x140063cd4  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140063cdb  nop     dword ptr [rax+rax+00h]
0x140063ce0  mov     r15, [rbp+280h+var_228]
0x140063ce4  mov     [rbp+280h+NewIrql], al
0x140063ce7  movzx   ecx, word ptr [r15+140h]
0x140063cef  mov     r9d, 1
0x140063cf5  xorps   xmm0, xmm0
0x140063cf8  mov     r8b, 0Eh
0x140063cfb  mov     [rbp+280h+var_280], r12b
0x140063cff  mov     r12d, r9d
0x140063d02  mov     [rbp+280h+var_27F], r8b
0x140063d06  movups  [rbp+280h+var_200], xmm0
0x140063d0d  movups  [rbp+280h+var_1F0], xmm0
0x140063d14  cmp     [rbp+280h+var_27B], r9b
0x140063d18  jnz     short loc_140063D51
0x140063d1a  test    cx, cx
0x140063d1d  jz      short loc_140063D29
0x140063d1f  mov     [rbp+280h+var_280], r9b
  ... truncated ...
```
