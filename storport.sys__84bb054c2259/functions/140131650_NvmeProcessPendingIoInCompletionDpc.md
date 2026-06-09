# NvmeProcessPendingIoInCompletionDpc

- ea: `0x140131650`
- end: `0x1401333f9`
- name: `NvmeProcessPendingIoInCompletionDpc`
- size: `7593`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x14005ed70`

## callees

- `0x14003ea90`
- `0x140042b60`
- `0x140043ca0`
- `0x140060e90`
- `0x140062190`
- `0x140065dc0`
- `0x140066260`
- `0x140124160`
- `0x14012f040`
- `0x14012f180`
- `0x140131650`
- `0x14014b400`
- `0x14014b440`

## import_xrefs

- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1401321e7`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14013306b`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1401321e7`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14013306b`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140131cfa`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140131d42`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140132a47`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140132a91`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140131cfa`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140131d42`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140132a47`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140132a91`
- `ntoskrnl!PoFxIdleComponent` at `0x140132438`
- `ntoskrnl!PoFxIdleComponent` at `0x140132487`
- `ntoskrnl!PoFxIdleComponent` at `0x140132ccd`
- `ntoskrnl!PoFxIdleComponent` at `0x140132d1c`
- `ntoskrnl!PoFxIdleComponent` at `0x1401332c4`
- `ntoskrnl!PoFxIdleComponent` at `0x140133317`
- `ntoskrnl!PoFxIdleComponent` at `0x140132438`
- `ntoskrnl!PoFxIdleComponent` at `0x140132487`
- `ntoskrnl!PoFxIdleComponent` at `0x140132ccd`
- `ntoskrnl!PoFxIdleComponent` at `0x140132d1c`
- `ntoskrnl!PoFxIdleComponent` at `0x1401332c4`
- `ntoskrnl!PoFxIdleComponent` at `0x140133317`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x140132412`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x140132ca7`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x14013329e`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x140132412`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x140132ca7`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x14013329e`
- `ntoskrnl!KeSetEvent` at `0x14013191f`
- `ntoskrnl!KeSetEvent` at `0x14013267f`
- `ntoskrnl!KeSetEvent` at `0x14013191f`
- `ntoskrnl!KeSetEvent` at `0x14013267f`
- `ntoskrnl!KeLowerIrql` at `0x140131950`
- `ntoskrnl!KeLowerIrql` at `0x140131cbf`
- `ntoskrnl!KeLowerIrql` at `0x14013203d`
- `ntoskrnl!KeLowerIrql` at `0x1401324f3`
- `ntoskrnl!KeLowerIrql` at `0x14013250f`
- `ntoskrnl!KeLowerIrql` at `0x1401326b1`
- `ntoskrnl!KeLowerIrql` at `0x140132a0f`
- `ntoskrnl!KeLowerIrql` at `0x140132eb1`
- `ntoskrnl!KeLowerIrql` at `0x14013335b`
- `ntoskrnl!KeLowerIrql` at `0x140131950`
- `ntoskrnl!KeLowerIrql` at `0x140131cbf`
- `ntoskrnl!KeLowerIrql` at `0x14013203d`
- `ntoskrnl!KeLowerIrql` at `0x1401324f3`
- `ntoskrnl!KeLowerIrql` at `0x14013250f`
- `ntoskrnl!KeLowerIrql` at `0x1401326b1`
- `ntoskrnl!KeLowerIrql` at `0x140132a0f`
- `ntoskrnl!KeLowerIrql` at `0x140132eb1`
- `ntoskrnl!KeLowerIrql` at `0x14013335b`
- `ntoskrnl!KfRaiseIrql` at `0x14013180f`
- `ntoskrnl!KfRaiseIrql` at `0x140131c84`
- `ntoskrnl!KfRaiseIrql` at `0x140131f66`
- `ntoskrnl!KfRaiseIrql` at `0x140132571`
- `ntoskrnl!KfRaiseIrql` at `0x1401329d6`
- `ntoskrnl!KfRaiseIrql` at `0x140132ddc`
- `ntoskrnl!KfRaiseIrql` at `0x14013180f`
- `ntoskrnl!KfRaiseIrql` at `0x140131c84`
- `ntoskrnl!KfRaiseIrql` at `0x140131f66`
- `ntoskrnl!KfRaiseIrql` at `0x140132571`
- `ntoskrnl!KfRaiseIrql` at `0x1401329d6`
- `ntoskrnl!KfRaiseIrql` at `0x140132ddc`
- `ntoskrnl!IoQueueWorkItem` at `0x140131941`
- `ntoskrnl!IoQueueWorkItem` at `0x1401326a1`
- `ntoskrnl!IoQueueWorkItem` at `0x140131941`
- `ntoskrnl!IoQueueWorkItem` at `0x1401326a1`
- `ntoskrnl!IofCompleteRequest` at `0x1401323b5`
- `ntoskrnl!IofCompleteRequest` at `0x140132c4a`
- `ntoskrnl!IofCompleteRequest` at `0x140133241`
- `ntoskrnl!IofCompleteRequest` at `0x1401323b5`
- `ntoskrnl!IofCompleteRequest` at `0x140132c4a`
- `ntoskrnl!IofCompleteRequest` at `0x140133241`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140132460`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140132cf5`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1401332ec`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140132460`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140132cf5`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1401332ec`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14013168c`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14013168c`
- `ntoskrnl!ExQueryDepthSList` at `0x14013188e`
- `ntoskrnl!ExQueryDepthSList` at `0x1401325ee`
- `ntoskrnl!ExQueryDepthSList` at `0x14013188e`
- `ntoskrnl!ExQueryDepthSList` at `0x1401325ee`
- `ntoskrnl!KeQueryUnbiasedInterruptTimePrecise` at `0x1401319c2`
- `ntoskrnl!KeQueryUnbiasedInterruptTimePrecise` at `0x140132720`
- `ntoskrnl!KeQueryUnbiasedInterruptTimePrecise` at `0x1401319c2`
- `ntoskrnl!KeQueryUnbiasedInterruptTimePrecise` at `0x140132720`
- `ntoskrnl!IoRecordIoAttribution` at `0x1401319d9`
- `ntoskrnl!IoRecordIoAttribution` at `0x140132737`
- `ntoskrnl!IoRecordIoAttribution` at `0x1401319d9`
- `ntoskrnl!IoRecordIoAttribution` at `0x140132737`
- `ntoskrnl!IoGetIoAttributionHandle` at `0x140131987`
- `ntoskrnl!IoGetIoAttributionHandle` at `0x1401326e5`
- `ntoskrnl!IoGetIoAttributionHandle` at `0x140131987`
- `ntoskrnl!IoGetIoAttributionHandle` at `0x1401326e5`

## pseudocode

```c
bool __fastcall NvmeProcessPendingIoInCompletionDpc(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  ULONG CurrentProcessorNumber; // eax
  __int64 v6; // rdx
  char v7; // r12
  ULONG v8; // r15d
  __int64 v9; // r14
  unsigned int v10; // r13d
  int v11; // r8d
  unsigned int v12; // edx
  __int64 v13; // rdi
  unsigned int v14; // eax
  _DWORD *v15; // r9
  __int64 v16; // r12
  char v17; // r13
  __int64 v18; // r15
  __int64 v19; // r14
  unsigned int v20; // esi
  unsigned int v21; // edx
  __int64 v22; // rbx
  unsigned int v23; // eax
  __int64 v24; // rax
  KIRQL v26; // bl
  unsigned __int32 v27; // r9d
  signed __int32 v28; // ecx
  ULONG_PTR v29; // rsi
  unsigned int v30; // edx
  unsigned int v31; // r8d
  unsigned int v32; // edx
  __int64 v33; // rcx
  __int64 v34; // rax
  __int64 v35; // rcx
  unsigned __int64 v36; // rdx
  __int64 v37; // rcx
  int v38; // r15d
  unsigned __int8 *v39; // rax
  __int64 v40; // rbx
  ULONG_PTR v41; // r14
  unsigned __int64 v42; // r9
  unsigned __int8 *v43; // rdi
  unsigned __int64 v44; // r8
  char v45; // r10
  __int64 v46; // rbx
  unsigned int v47; // r12d
  unsigned __int64 v48; // r15
  int v49; // r10d
  int v50; // r11d
  __int16 v51; // di
  unsigned __int64 v52; // rbx
  __int16 v53; // r12
  signed __int32 v54; // eax
  int v55; // eax
  int v56; // r9d
  unsigned int v57; // edx
  PSLIST_ENTRY v58; // rbx
  PSLIST_ENTRY v59; // rdi
  __int64 v60; // r12
  unsigned __int8 v61; // di
  __int64 v62; // rbx
  KIRQL v63; // al
  __int64 v64; // rcx
  __int64 v65; // rdx
  __int64 v66; // rbx
  __int64 v67; // rcx
  __int64 v68; // rdx
  __int64 v69; // rcx
  __int64 v70; // rax
  __int64 v71; // rax
  unsigned __int64 v72; // rdi
  unsigned __int64 v73; // r8
  unsigned __int64 v74; // rbx
  unsigned __int64 v75; // r15
  unsigned __int64 v76; // rcx
  __int64 v77; // r8
  char v78; // al
  unsigned __int64 v79; // r10
  unsigned int v80; // eax
  __int64 v81; // rax
  __int64 v82; // rdx
  char v83; // al
  __int64 v84; // rax
  int v85; // ebx
  __int64 v86; // rdi
  unsigned __int64 v87; // r15
  KIRQL v88; // al
  __int64 v89; // rbx
  __int64 v90; // rdx
  __int64 v91; // rcx
  __int64 v92; // rdx
  __int64 v93; // r8
  int v94; // eax
  unsigned __int64 v95; // r15
  unsigned __int64 v96; // rcx
  __int16 v97; // r12
  __int64 v98; // r11
  unsigned int v99; // edx
  char v100; // al
  unsigned __int64 v101; // rax
  unsigned __int64 v102; // r9
  int v103; // r10d
  PSLIST_ENTRY v104; // rax
  __int64 v105; // rax
  __int64 v106; // rcx
  __int64 v107; // r8
  __int64 v108; // r9
  int v109; // eax
  int v110; // eax
  __int64 v111; // rax
  __int64 v112; // rbx
  __int64 v113; // rax
  struct _EX_RUNDOWN_REF_CACHE_AWARE *v114; // rcx
  __int64 v115; // rax
  struct _EX_RUNDOWN_REF_CACHE_AWARE *v116; // rcx
  __int64 v117; // rax
  KIRQL v118; // di
  unsigned __int32 v119; // r9d
  signed __int32 v120; // ecx
  ULONG_PTR v121; // rsi
  unsigned int v122; // edx
  unsigned int v123; // r8d
  unsigned int v124; // edx
  __int64 v125; // rcx
  __int64 v126; // rax
  __int64 v127; // rcx
  __int64 v128; // rdx
  __int64 v129; // rcx
  int v130; // r15d
  unsigned __int8 *v131; // rax
  __int64 v132; // rdi
  ULONG_PTR v133; // r14
  __int64 v134; // rdi
  char v135; // r10
  PSLIST_ENTRY v136; // r13
  __int64 v137; // rbx
  unsigned int v138; // r12d
  unsigned __int64 v139; // r9
  unsigned __int64 v140; // r8
  int v141; // r10d
  int v142; // r11d
  __int16 v143; // di
  unsigned __int64 v144; // rbx
  unsigned __int64 v145; // r13
  __int16 v146; // r12
  signed __int32 v147; // eax
  int v148; // eax
  int v149; // r9d
  unsigned int v150; // edx
  __int64 v151; // rbx
  __int64 v152; // r12
  unsigned __int8 v153; // di
  __int64 v154; // rbx
  KIRQL v155; // r13
  __int64 v156; // rdx
  unsigned __int64 v157; // rbx
  __int64 v158; // rcx
  __int64 v159; // rdx
  __int64 v160; // rcx
  __int64 v161; // rax
  __int64 v162; // rax
  __int64 v163; // rax
  unsigned __int64 Next; // rdi
  unsigned __int64 v165; // r8
  unsigned __int64 v166; // rbx
  unsigned __int64 v167; // r15
  unsigned __int64 v168; // rcx
  __int64 v169; // r8
  char v170; // al
  unsigned __int64 v171; // r10
  unsigned int v172; // eax
  __int64 NVMeSGLBufferContext; // rax
  __int64 v174; // rdx
  __int64 v175; // rax
  __int64 v176; // rbx
  __int64 v177; // rax
  struct _EX_RUNDOWN_REF_CACHE_AWARE *v178; // rcx
  __int64 v179; // rax
  struct _EX_RUNDOWN_REF_CACHE_AWARE *v180; // rcx
  bool v181; // zf
  char v182; // al
  __int64 v183; // rax
  int v184; // ebx
  __int64 v185; // rdi
  __int64 v186; // r15
  KIRQL v187; // r13
  unsigned __int64 v188; // rbx
  __int64 v189; // rdx
  PSLIST_ENTRY v190; // rdi
  __int64 v191; // rcx
  __int64 v192; // rdx
  int v193; // eax
  unsigned __int64 v194; // r12
  unsigned __int64 v195; // rcx
  __int16 v196; // r13
  __int64 v197; // r15
  unsigned int v198; // r8d
  char v199; // al
  unsigned int v200; // eax
  int v201; // r10d
  PSLIST_ENTRY v202; // rax
  unsigned int v203; // r15d
  __int64 NewNVMePrpListBufferEntry; // rax
  __int64 v205; // rcx
  __int64 v206; // r8
  __int64 v207; // r9
  int v208; // eax
  int v209; // eax
  __int64 v210; // rax
  __int64 v211; // rbx
  __int64 v212; // rax
  struct _EX_RUNDOWN_REF_CACHE_AWARE *v213; // rcx
  __int64 v214; // rax
  struct _EX_RUNDOWN_REF_CACHE_AWARE *v215; // rcx
  __int64 v216; // rax
  int v217; // [rsp+28h] [rbp-D8h]
  int v218; // [rsp+38h] [rbp-C8h]
  __int64 v219; // [rsp+40h] [rbp-C0h]
  __int64 v220; // [rsp+40h] [rbp-C0h]
  int v221; // [rsp+48h] [rbp-B8h]
  int v222; // [rsp+48h] [rbp-B8h]
  char v223; // [rsp+60h] [rbp-A0h]
  char v224; // [rsp+60h] [rbp-A0h]
  char v225; // [rsp+62h] [rbp-9Eh]
  bool v226; // [rsp+62h] [rbp-9Eh]
  char v227; // [rsp+62h] [rbp-9Eh]
  bool v228; // [rsp+62h] [rbp-9Eh]
  char v229; // [rsp+63h] [rbp-9Dh]
  char v230; // [rsp+63h] [rbp-9Dh]
  bool v231; // [rsp+64h] [rbp-9Ch] BYREF
  _BYTE v232[11]; // [rsp+65h] [rbp-9Bh] BYREF
  __int64 v233; // [rsp+70h] [rbp-90h]
  int v234; // [rsp+78h] [rbp-88h]
  PSLIST_ENTRY v235; // [rsp+80h] [rbp-80h]
  __int64 v236; // [rsp+88h] [rbp-78h]
  __int64 v237; // [rsp+90h] [rbp-70h]
  int v238; // [rsp+98h] [rbp-68h]
  PSLIST_ENTRY ListEntry; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v240; // [rsp+A8h] [rbp-58h]
  __int64 v241; // [rsp+B0h] [rbp-50h]
  __int64 v242; // [rsp+B8h] [rbp-48h]
  unsigned __int64 v243; // [rsp+C0h] [rbp-40h]
  unsigned __int64 v244; // [rsp+C8h] [rbp-38h]
  __int16 v245[2]; // [rsp+D0h] [rbp-30h] BYREF
  __int16 v246; // [rsp+D4h] [rbp-2Ch] BYREF
  _DWORD *v247; // [rsp+D8h] [rbp-28h]
  __int64 v248; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v249; // [rsp+E8h] [rbp-18h]
  int v250; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v251; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v252; // [rsp+100h] [rbp+0h] BYREF
  __int64 v253; // [rsp+108h] [rbp+8h] BYREF
  __int64 v254; // [rsp+110h] [rbp+10h]
  __int128 v255; // [rsp+118h] [rbp+18h] BYREF
  __int128 v256; // [rsp+128h] [rbp+28h] BYREF

  v249 = a1;
  v233 = a4;
  v240 = a2;
  CurrentProcessorNumber = KeGetCurrentProcessorNumberEx(0);
  v6 = *(_QWORD *)(a1 + 1112);
  v7 = 0;
  v8 = CurrentProcessorNumber;
  *(_DWORD *)&v232[7] = CurrentProcessorNumber;
  v229 = 0;
  v236 = CurrentProcessorNumber;
  v9 = *(_QWORD *)(v6 + 8LL * CurrentProcessorNumber);
  v248 = v9;
  v10 = *(_DWORD *)(v9 + 64);
  v11 = *(_DWORD *)(a1 + 656);
  v247 = g_CpuInfo;
  v238 = v11;
  while ( 2 )
  {
    v12 = v10;
    while ( 1 )
    {
      v13 = *(_QWORD *)(v9 + 8LL * v10 + 264);
      if ( v13 )
      {
        if ( **(_DWORD **)(v13 + 16) )
          goto LABEL_26;
        if ( *(_DWORD *)v13 || *(_DWORD *)(v13 + 48) != *(_DWORD *)(v13 + 52) )
          break;
      }
      if ( v11 != 1 )
      {
        v14 = v10 + 1;
        v10 = 0;
        if ( v14 < *(_DWORD *)(v9 + 4) )
          v10 = v14;
        if ( v12 != v10 )
          continue;
      }
      goto LABEL_11;
    }
    v251 = 0;
    v26 = KfRaiseIrql(2u);
    do
    {
      v27 = *(_DWORD *)(v13 + 52);
      if ( v27 == *(_DWORD *)(v13 + 48) )
      {
        if ( _InterlockedCompareExchange((volatile signed __int32 *)v13, 0, 1) == 1 )
        {
          v117 = *(_QWORD *)(v13 + 24);
          if ( *(_BYTE *)(*(_QWORD *)(v13 + 16) + 20LL) == 1 )
          {
            _InterlockedDecrement((volatile signed __int32 *)(v117 + 956));
            KeLowerIrql(v26);
            goto LABEL_187;
          }
          _InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)(v117 + 16) + 952LL));
        }
        KeLowerIrql(v26);
LABEL_187:
        v11 = v238;
        if ( v238 != 1 )
        {
LABEL_188:
          v37 = ++v10;
          if ( v10 >= *(_DWORD *)(v9 + 4) )
            v10 = 0;
          goto LABEL_190;
        }
LABEL_11:
        v15 = v247;
        v16 = 0;
        *(_DWORD *)(v9 + 64) = v10;
        *(_DWORD *)&v232[3] = 0;
        if ( !v15[3] )
          goto LABEL_26;
        v17 = v229;
        while ( (_DWORD)v16 == v8 )
        {
LABEL_25:
          v16 = (unsigned int)(v16 + 1);
          *(_DWORD *)&v232[3] = v16;
          if ( (unsigned int)v16 >= v15[3] )
            goto LABEL_26;
        }
        v18 = v249;
        v243 = (unsigned int)v16;
        v19 = *(_QWORD *)(*(_QWORD *)(v249 + 1112) + 8 * v16);
        v254 = v19;
        v20 = *(_DWORD *)(v19 + 64);
        v234 = v20;
        while ( 1 )
        {
          v21 = v20;
          while ( 1 )
          {
            v22 = *(_QWORD *)(v19 + 8LL * v20 + 264);
            if ( v22 )
            {
              if ( **(_DWORD **)(v22 + 16) )
                goto LABEL_26;
              if ( *(_DWORD *)v22 || *(_DWORD *)(v22 + 48) != *(_DWORD *)(v22 + 52) )
                break;
            }
            if ( v11 != 1 )
            {
              v23 = v20 + 1;
              v20 = 0;
              if ( v23 != *(_DWORD *)(v19 + 4) )
                v20 = v23;
              v234 = v20;
              if ( v21 != v20 )
                continue;
            }
            goto LABEL_24;
          }
          v248 = 0;
          v118 = KfRaiseIrql(2u);
          do
          {
            v119 = *(_DWORD *)(v22 + 52);
            if ( v119 == *(_DWORD *)(v22 + 48) )
            {
              if ( _InterlockedCompareExchange((volatile signed __int32 *)v22, 0, 1) == 1 )
              {
                v216 = *(_QWORD *)(v22 + 24);
                if ( *(_BYTE *)(*(_QWORD *)(v22 + 16) + 20LL) == 1 )
                  _InterlockedDecrement((volatile signed __int32 *)(v216 + 956));
                else
                  _InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)(v216 + 16) + 952LL));
              }
              KeLowerIrql(v118);
              v130 = -2147483622;
              goto LABEL_361;
            }
            v120 = 0;
            if ( v119 + 1 < *(_DWORD *)(*(_QWORD *)(v22 + 16) + 4LL) )
              v120 = v119 + 1;
          }
          while ( v119 != _InterlockedCompareExchange((volatile signed __int32 *)(v22 + 52), v120, v119) );
          do
            v121 = _InterlockedExchange64((volatile __int64 *)(8LL * v119 + *(_QWORD *)(v22 + 56)), 0);
          while ( !v121 );
          if ( !*(_DWORD *)(*(_QWORD *)(v22 + 16) + 16LL)
            && (*(_DWORD *)v22 == 2
             || ExQueryDepthSList((PSLIST_HEADER)(*(_QWORD *)(v22 + 32) + 16LL * *(unsigned int *)(v22 + 8)))) )
          {
            if ( *(_DWORD *)(v22 + 48) == *(_DWORD *)(v22 + 52)
              || ((v122 = *(_DWORD *)(v22 + 48), v123 = *(_DWORD *)(v22 + 52), v122 != v123)
                ? (v122 <= v123
                 ? ((v125 = *(_QWORD *)(v22 + 24), *(_BYTE *)(*(_QWORD *)(v22 + 16) + 20LL))
                  ? (v126 = *(_QWORD *)(v125 + 1024))
                  : (v126 = *(_QWORD *)(v125 + 256)),
                    v124 = *(_DWORD *)(v126 + 4) - v123 + v122)
                 : (v124 = v122 - v123))
                : (v124 = 0),
                  v124 <= *(_DWORD *)(*(_QWORD *)(v22 + 16) + 8LL)) )
            {
              if ( !_InterlockedCompareExchange((volatile signed __int32 *)(*(_QWORD *)(v22 + 16) + 16LL), 1, 0) )
              {
                v127 = *(_QWORD *)(v22 + 24);
                if ( *(_BYTE *)(*(_QWORD *)(v22 + 16) + 20LL) )
                  IoQueueWorkItem(
                    *(PIO_WORKITEM *)(v127 + 1032),
                    NvmeControllerRefillShadowQueueRoutine,
                    DelayedWorkQueue,
                    *(PVOID *)(v22 + 24));
                else
                  KeSetEvent((PRKEVENT)(v127 + 480), 0, 0);
              }
            }
          }
          KeLowerIrql(v118);
          if ( (*(_BYTE *)(v18 + 136) & 2) != 0 )
          {
            v130 = NvmeNamespaceProcessRequest(*(_QWORD *)(v22 + 24), v121, (unsigned int)v16);
            goto LABEL_301;
          }
          if ( (int)IoGetIoAttributionHandle(v121, &v248) >= 0 )
          {
            v131 = *(unsigned __int8 **)(v121 + 184);
            v132 = v248;
            v255 = 0;
            LODWORD(v255) = 1;
            v256 = 0;
            DWORD1(v255) = *v131 | 0x200;
            *((_QWORD *)&v256 + 1) = KeQueryUnbiasedInterruptTimePrecise((PULONG64)&v256 + 1);
            IoRecordIoAttribution(v132, &v255);
          }
          v133 = *(_QWORD *)(v22 + 24);
          v130 = 0;
          v134 = *(_QWORD *)(v121 + 184);
          v246 = 0;
          LOBYTE(v129) = 0;
          v253 = 0;
          v135 = 0;
          v128 = *(_QWORD *)(v133 + 16);
          v136 = 0;
          v231 = 0;
          LODWORD(ListEntry) = 0;
          v137 = *(_QWORD *)(v134 + 8);
          v138 = v137;
          v139 = HIDWORD(*(_QWORD *)(v128 + 136));
          LOBYTE(v139) = v139 & 1;
          v235 = 0;
          v237 = v128;
          v241 = v139;
          v224 = 0;
          v230 = 0;
          v232[0] = 0;
          if ( v137 == 0x8765432100000003uLL )
          {
            v140 = *(_QWORD *)(v134 + 24);
            v242 = v140;
          }
          else
          {
            v242 = 0;
            v140 = 0;
            if ( v137 == 0xFEDCBA9000000000uLL )
            {
              v136 = *(PSLIST_ENTRY *)(v134 + 24);
              v235 = v136;
            }
          }
          if ( (unsigned int)(*(_DWORD *)(v133 + 96) - 5) <= 1 )
          {
            v231 = 1;
            v130 = -1073741810;
            goto LABEL_251;
          }
          v232[1] = *(_BYTE *)v134;
          v129 = v232[1];
          v227 = v232[1] == 3;
          if ( v140 )
          {
            v141 = v233;
            LOBYTE(v129) = 0;
            v142 = v240;
            v143 = 0;
            v244 = v233;
            v237 = v240;
            v228 = 0;
            LODWORD(v236) = 0;
            if ( !(_BYTE)v139 )
            {
              _InterlockedIncrement16((volatile signed __int16 *)(v140 + 120));
              v224 = 1;
            }
            v128 = 4;
LABEL_229:
            v144 = v140;
            while ( 1 )
            {
              v145 = *(_QWORD *)(v144 + 96);
              v146 = *(_WORD *)(v144 + 34);
              v147 = _InterlockedCompareExchange((volatile signed __int32 *)(v144 + 104), 4, 3);
              if ( (_BYTE)v139 )
              {
                if ( v147 != 3 && _InterlockedCompareExchange((volatile signed __int32 *)(v144 + 104), 4, 1) != 1 )
                  goto LABEL_243;
              }
              else if ( v147 != 3 )
              {
                if ( *(_DWORD *)(v144 + 104) == 1 )
                  ++v143;
                goto LABEL_243;
              }
              v148 = NvmeSendSplitIo(
                       v144,
                       *(_DWORD *)&v232[3],
                       v142,
                       v141,
                       (__int64)&v231,
                       (__int64)&v253,
                       (__int64)&ListEntry,
                       (__int64)&v246,
                       v129);
              v130 = v148;
              if ( v148 == 259 )
              {
                v129 = *(_QWORD *)(v133 + 16);
                HIWORD(v149) = WORD1(v236);
                v141 = 0;
                LOWORD(v149) = v236 + 1;
                v244 = 0;
                v142 = 0;
                v150 = (unsigned __int16)(v236 + 1) % (unsigned int)*(unsigned __int8 *)(v129 + 1730);
                v237 = 0;
                LODWORD(v236) = v149;
                v230 = 1;
                LOBYTE(v129) = v150 == 0;
                v228 = v150 == 0;
              }
              else
              {
                if ( v148 == -2147483631 )
                {
                  _InterlockedCompareExchange((volatile signed __int32 *)(v144 + 104), 3, 4);
                  NvmeNamespaceQueueIo(v133, *(_QWORD *)(v144 + 24), *(unsigned int *)&v232[3]);
                  LOBYTE(v129) = 1;
LABEL_250:
                  v135 = v224;
                  goto LABEL_251;
                }
                if ( !v146 )
                {
                  v231 = 1;
LABEL_249:
                  v129 = 0;
                  goto LABEL_250;
                }
                if ( v231 )
                  goto LABEL_249;
                v141 = v244;
                v142 = v237;
                v129 = v228;
              }
              v139 = v241;
              v128 = 4;
              v140 = v242;
LABEL_243:
              v144 = v145;
              if ( v143 && !v145 )
              {
                v143 = 0;
                goto LABEL_229;
              }
              if ( !v145 )
              {
                LOBYTE(v129) = 1;
                goto LABEL_250;
              }
            }
          }
          v162 = *(_QWORD *)(v128 + 128);
          v139 = *(unsigned int *)(v162 + 208);
          LODWORD(v236) = *(_DWORD *)(v162 + 208);
          if ( (_BYTE)v241 )
          {
            Next = *(_QWORD *)(v134 + 24);
            goto LABEL_314;
          }
          if ( !v136 )
          {
            v165 = *(unsigned int *)(v133 + 64);
            if ( !((unsigned int)v137 % (unsigned int)v165) )
            {
              v166 = *(_QWORD *)(v134 + 24);
              v167 = v166 / v165;
              if ( !(v166 % v165) )
              {
                v168 = *(_QWORD *)(v133 + 432);
                if ( *(_QWORD *)(v134 + 24) / v165 < v168 )
                {
                  v244 = v138 / (unsigned int)v165;
                  if ( v168 - v167 >= v244 )
                  {
                    if ( v138 <= (unsigned int)v139 )
                    {
                      v169 = *(unsigned int *)(v133 + 428);
                      if ( !(_DWORD)v169 )
                        goto LABEL_283;
                      if ( v138 <= (unsigned int)v169 )
                      {
                        v170 = *(_BYTE *)(v133 + 427);
                        v171 = (unsigned int)v169;
                        if ( v170 )
                        {
                          v169 = (unsigned int)(v169 - 1);
                          v139 = (unsigned int)v169 & (unsigned int)v166;
                          v172 = ((unsigned __int64)v138 >> v170)
                               + ((((unsigned int)v169 & v138) + v171 + v139 - 1) >> v170);
                        }
                        else
                        {
                          v139 = v138 / (unsigned __int64)(unsigned int)v169;
                          v169 = v138 % (unsigned int)v169;
                          v172 = v138 / v171 + (v169 + v171 + (unsigned int)(v166 % v171) - 1LL) / v171;
                        }
                        if ( v172 <= 1 )
                        {
LABEL_283:
                          NVMeSGLBufferContext = GetNVMeSGLBufferContext(v237, *(unsigned int *)&v232[3], v169, v139);
                          v235 = (PSLIST_ENTRY)NVMeSGLBufferContext;
                          v174 = NVMeSGLBufferContext;
                          if ( NVMeSGLBufferContext )
                          {
                            v181 = v232[1] == 3;
                            *(_QWORD *)(NVMeSGLBufferContext + 40) = v121;
                            v182 = *(_BYTE *)(NVMeSGLBufferContext + 126) & 0xFE;
                            *(_QWORD *)(v174 + 96) = v166;
                            *(_QWORD *)(v174 + 32) = v133;
                            *(_DWORD *)(v174 + 112) = v244;
                            *(_QWORD *)(v174 + 64) = v233;
                            *(_QWORD *)(v174 + 72) = v240;
                            *(_BYTE *)(v174 + 126) = v182 | v181;
                            *(_QWORD *)(v174 + 104) = v167;
                            *(_DWORD *)(v174 + 116) = v138;
                            *(_QWORD *)(v174 + 56) = *(_QWORD *)(v134 + 24);
                            v183 = *(_QWORD *)(v134 + 8);
                            *(_QWORD *)(v134 + 24) = v174;
                            *(_QWORD *)(v174 + 48) = v183;
                            *(_QWORD *)(v134 + 8) = 0xFEDCBA9000000000uLL;
                            v184 = *(unsigned __int16 *)(v174 + 124);
                            v185 = *(_QWORD *)(v174 + 16);
                            v186 = *(_QWORD *)(*(_QWORD *)(v121 + 8) + 32LL)
                                 + *(unsigned int *)(*(_QWORD *)(v121 + 8) + 44LL);
                            *(_QWORD *)(v174 + 80) = v186;
                            v244 = *(_QWORD *)(v121 + 8);
                            v237 = *(_QWORD *)(v133 + 16);
                            v241 = v186;
                            v187 = KfRaiseIrql(2u);
                            v222 = v184;
                            v188 = v244;
                            v220 = v185;
                            v189 = *(_QWORD *)(v237 + 128);
                            v190 = v235;
                            v191 = *(_QWORD *)(v189 + 1160);
                            v192 = *(_QWORD *)(v189 + 8);
                            v232[1] = v232[1] != 3;
                            LOBYTE(v218) = v232[1];
                            v130 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned __int64, __int64, unsigned int, __int64 (__fastcall *)(), PSLIST_ENTRY, int, __int64, int))(*(_QWORD *)(v191 + 8) + 112LL))(
                                     v191,
                                     v192,
                                     v244,
                                     v186,
                                     v138,
                                     NvmeContinueScatterGatherProcessIO,
                                     v235,
                                     v218,
                                     v220,
                                     v222);
                            if ( v130 == -1073741789 )
                            {
                              LOBYTE(v218) = v232[1];
                              v130 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned __int64, __int64, unsigned int, __int64 (__fastcall *)(), PSLIST_ENTRY, int))(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v237 + 128) + 1160LL) + 8LL) + 88LL))(
                                       *(_QWORD *)(*(_QWORD *)(v237 + 128) + 1160LL),
                                       *(_QWORD *)(*(_QWORD *)(v237 + 128) + 8LL),
                                       v188,
                                       v241,
                                       v138,
                                       NvmeContinueScatterGatherProcessIO,
                                       v190,
                                       v218);
                            }
                            if ( v187 < 2u )
                              KeLowerIrql(v187);
                            v151 = v242;
                            v136 = v190;
                            if ( v130 >= 0 )
                              v130 = 259;
                            goto LABEL_257;
                          }
                          v130 = -1073741670;
LABEL_285:
                          v157 = v243;
                          if ( (*(_BYTE *)(v121 + 151) & 1) != 0 )
                            _InterlockedDecrement(*(volatile signed __int32 **)(*(_QWORD *)(v133 + 696) + 8 * v243));
LABEL_287:
                          *(_DWORD *)(v121 + 48) = v130;
                          IofCompleteRequest((PIRP)v121, 0);
                          v175 = *(_QWORD *)(v133 + 128);
                          if ( !*(_BYTE *)v175 )
                          {
                            v129 = *(_QWORD *)(*(_QWORD *)(v175 + 24) + 8 * v157);
                            if ( _InterlockedExchangeAdd((volatile signed __int32 *)v129, 0xFFFFFFFF) == 1 )
                            {
                              v176 = *(_QWORD *)(*(_QWORD *)(v133 + 16) + 128LL);
                              v177 = *(_QWORD *)(v133 + 128);
                              if ( v177 )
                              {
                                if ( *(_QWORD *)(v177 + 8) )
                                {
                                  v178 = *(struct _EX_RUNDOWN_REF_CACHE_AWARE **)(v177 + 40);
                                  if ( v178 )
                                  {
                                    if ( ExAcquireRundownProtectionCacheAware(v178) )
                                    {
                                      PoFxIdleComponent(**(_QWORD **)(*(_QWORD *)(v133 + 128) + 8LL), 0, 2);
                                      v179 = *(_QWORD *)(v133 + 128);
                                      if ( v179 )
                                      {
                                        if ( *(_QWORD *)(v179 + 8) )
                                        {
                                          v180 = *(struct _EX_RUNDOWN_REF_CACHE_AWARE **)(v179 + 40);
                                          if ( v180 )
                                            ExReleaseRundownProtectionCacheAware(v180);
                                        }
                                      }
                                    }
                                  }
                                }
                              }
                              v129 = *(_QWORD *)(v176 + 168);
                              if ( *(_BYTE *)v129 == 1 )
                                PoFxIdleComponent(**(_QWORD **)(v129 + 8), 0, 2);
                            }
                          }
                          goto LABEL_299;
                        }
                        LODWORD(v139) = v236;
                      }
                    }
                    v193 = NvmeSplitIoParallel(v133, v121, v166, v139, *(int *)&v232[3], v240, v233, (__int64)v232);
                    v151 = v242;
                    v130 = v193;
                    v230 = v232[0];
                    goto LABEL_257;
                  }
                }
              }
            }
            v130 = -1073741811;
            goto LABEL_285;
          }
          v163 = v240;
          Next = (unsigned __int64)v136[6].Next;
          LODWORD(v137) = HIDWORD(v136[7].Next);
          v136[4].Next = (_SLIST_ENTRY *)v233;
          *((_QWORD *)&v136[4].Next + 1) = v163;
LABEL_314:
          v140 = *(unsigned int *)(v133 + 64);
          v128 = (unsigned int)v137 % (unsigned int)v140;
          if ( (unsigned int)v137 % (unsigned int)v140
            || (v128 = Next % v140, v194 = Next / v140, Next % v140)
            || (v195 = *(_QWORD *)(v133 + 432), Next / v140 >= v195)
            || (LODWORD(v128) = (unsigned int)v137 % (unsigned int)v140,
                v196 = (unsigned int)v137 / (unsigned int)v140,
                v195 - v194 < (unsigned int)v137 / (unsigned int)v140) )
          {
            v130 = -1073741811;
            v129 = 0;
            goto LABEL_251;
          }
          v197 = *(_QWORD *)(v133 + 16);
          if ( (unsigned int)v137 > *(_DWORD *)(*(_QWORD *)(v197 + 128) + 208LL) )
            goto LABEL_337;
          v198 = *(_DWORD *)(v133 + 428);
          if ( v198 )
          {
            if ( (unsigned int)v137 > v198 )
              goto LABEL_337;
            v199 = *(_BYTE *)(v133 + 427);
            v200 = v199
                 ? ((unsigned __int64)(unsigned int)v137 >> v199)
                 + ((((v198 - 1) & (unsigned int)v137) + v198 + (unsigned __int64)((v198 - 1) & (unsigned int)Next) - 1) >> v199)
                 : (unsigned int)v137 / v198
                 + (unsigned int)(((unsigned int)v137 % v198 - 1LL + v198 + Next % v198) / v198);
            if ( v200 > 1 )
            {
              LODWORD(v139) = v236;
LABEL_337:
              v209 = NvmeSplitIoParallel(v133, v121, Next, v139, *(int *)&v232[3], v240, v233, (__int64)v232);
              v129 = 0;
              v130 = v209;
              v135 = 0;
              v230 = v232[0];
              goto LABEL_251;
            }
          }
          v201 = 0;
          if ( (((unsigned int)v137
               + ((*(_DWORD *)(*(_QWORD *)(v121 + 8) + 32LL) + *(_DWORD *)(*(_QWORD *)(v121 + 8) + 44LL)) & 0xFFF)
               + 4095LL)
              & 0xFFFFFFFFFFFFF000uLL) <= 0x2000 )
          {
            v203 = *(_DWORD *)&v232[3];
          }
          else
          {
            v202 = ExpInterlockedPopEntrySList(*(PSLIST_HEADER *)(*(_QWORD *)(v197 + 880) + 8 * v243));
            v203 = *(_DWORD *)&v232[3];
            v201 = (int)v202;
            if ( !v202 )
            {
              NewNVMePrpListBufferEntry = AllocateNewNVMePrpListBufferEntry(
                                            *(_QWORD *)(v133 + 16),
                                            *(unsigned int *)&v232[3]);
              v201 = NewNVMePrpListBufferEntry;
              if ( !NewNVMePrpListBufferEntry )
              {
                NvmeNamespaceQueueIo(v133, v121, v203);
                v129 = 0;
                v130 = -2147483631;
                v135 = 0;
                goto LABEL_251;
              }
            }
          }
          v205 = v233;
          if ( v233 )
          {
            LODWORD(v206) = v240;
          }
          else
          {
            v207 = *(_QWORD *)(v133 + 16);
            if ( (*(_BYTE *)(v207 + 136) & 2) != 0 )
            {
              v206 = *(_QWORD *)(v207 + 728) + 192LL * v203;
            }
            else
            {
              v205 = v233;
              LODWORD(v206) = 192 * *(unsigned __int16 *)(*(_QWORD *)(v207 + 872) + 2LL * v203)
                            + *(_DWORD *)(v207 + 728)
                            - 192;
            }
          }
          LOBYTE(v217) = 0;
          v208 = NvmeSubmitIoToSQ(v133, v121, v206, v201, v203, v217, v137, Next, v194, v196, v227, v205);
          v129 = 0;
          v130 = v208;
          v135 = 0;
LABEL_251:
          v151 = v242;
          if ( !(_BYTE)v241 && v135 )
            _InterlockedDecrement16((volatile signed __int16 *)(v242 + 120));
          v136 = v235;
          if ( !(_BYTE)v129 && v151 )
            _interlockedbittestandreset((volatile signed __int32 *)(v151 + 108), 0);
LABEL_257:
          if ( v130 == -2147483631 || v130 >= 1 )
            goto LABEL_299;
          if ( v136 )
          {
            v152 = *((_QWORD *)&v136[1].Next + 1);
            if ( v152 )
            {
              v153 = *((_BYTE *)&v136[7].Next + 14) & 1;
              v154 = *(_QWORD *)(*(_QWORD *)(v133 + 16) + 128LL);
              v155 = KfRaiseIrql(2u);
              (*(void (__fastcall **)(_QWORD, __int64, _QWORD))(*(_QWORD *)(*(_QWORD *)(v154 + 1160) + 8LL) + 96LL))(
                *(_QWORD *)(v154 + 1160),
                v152,
                v153 ^ 1u);
              if ( v155 < 2u )
                KeLowerIrql(v155);
              v136 = v235;
            }
            v156 = *((_QWORD *)&v136[5].Next + 1);
            v157 = v243;
            if ( v156 )
            {
              v158 = *(_QWORD *)(v133 + 16);
              *(_QWORD *)(v156 + 88) = 0;
              *(_DWORD *)(v156 + 108) = 0;
              *(_DWORD *)(v156 + 104) = 0;
              ExpInterlockedPushEntrySList(*(PSLIST_HEADER *)(*(_QWORD *)(v158 + 888) + 8 * v157), (PSLIST_ENTRY)v156);
            }
            v159 = *(_QWORD *)(v133 + 16);
            v160 = *(_QWORD *)(*((_QWORD *)&v136[2].Next + 1) + 184LL);
            *(_QWORD *)(v160 + 8) = v136[3].Next;
            *(_QWORD *)(v160 + 24) = *((_QWORD *)&v136[3].Next + 1);
            v161 = *((unsigned int *)&v136[7].Next + 2);
            *((_QWORD *)&v136[1].Next + 1) = 0;
            *((_QWORD *)&v136[5].Next + 1) = 0;
            *((_BYTE *)&v136[7].Next + 14) = 0;
            ExpInterlockedPushEntrySList(*(PSLIST_HEADER *)(*(_QWORD *)(v159 + 896) + 8 * v161), v136);
            if ( (*(_BYTE *)(v121 + 151) & 1) != 0 )
              _InterlockedDecrement(*(volatile signed __int32 **)(*(_QWORD *)(v133 + 696) + 8 * v157));
            goto LABEL_287;
          }
          if ( !v151 )
            goto LABEL_285;
          if ( v231 )
          {
            FreeAllSglAndContextInChainedSplitIoContext(*(_QWORD *)(v133 + 16), v151, v140, v139);
            v16 = *(unsigned int *)&v232[3];
            FreeNVMeChainedIoSplitContext(*(_QWORD *)(v133 + 16), *(unsigned int *)&v232[3], v151, v121);
            if ( (*(_BYTE *)(v121 + 151) & 1) != 0 )
              _InterlockedDecrement(*(volatile signed __int32 **)(*(_QWORD *)(v133 + 696) + 8 * v16));
            *(_DWORD *)(v121 + 48) = v130;
            IofCompleteRequest((PIRP)v121, 0);
            v210 = *(_QWORD *)(v133 + 128);
            if ( !*(_BYTE *)v210 )
            {
              v129 = *(_QWORD *)(*(_QWORD *)(v210 + 24) + 8LL * (unsigned int)v16);
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)v129, 0xFFFFFFFF) == 1 )
              {
                v211 = *(_QWORD *)(*(_QWORD *)(v133 + 16) + 128LL);
                v212 = *(_QWORD *)(v133 + 128);
                if ( v212 )
                {
                  if ( *(_QWORD *)(v212 + 8) )
                  {
                    v213 = *(struct _EX_RUNDOWN_REF_CACHE_AWARE **)(v212 + 40);
                    if ( v213 )
                    {
                      if ( ExAcquireRundownProtectionCacheAware(v213) )
                      {
                        PoFxIdleComponent(**(_QWORD **)(*(_QWORD *)(v133 + 128) + 8LL), 0, 2);
                        v214 = *(_QWORD *)(v133 + 128);
                        if ( v214 )
                        {
                          if ( *(_QWORD *)(v214 + 8) )
                          {
                            v215 = *(struct _EX_RUNDOWN_REF_CACHE_AWARE **)(v214 + 40);
                            if ( v215 )
                              ExReleaseRundownProtectionCacheAware(v215);
                          }
                        }
                      }
                    }
                  }
                }
                v129 = *(_QWORD *)(v211 + 168);
                if ( *(_BYTE *)v129 == 1 )
                  PoFxIdleComponent(**(_QWORD **)(v129 + 8), 0, 2);
              }
            }
            goto LABEL_300;
          }
LABEL_299:
          LODWORD(v16) = *(_DWORD *)&v232[3];
LABEL_300:
          v19 = v254;
          v17 = v230;
LABEL_301:
          if ( v130 == 259 )
            goto LABEL_192;
          v20 = v234;
LABEL_361:
          if ( v17 )
            goto LABEL_192;
          if ( v130 == -2147483631 )
            goto LABEL_26;
          if ( v130 == -2147483622 )
          {
            v11 = v238;
            if ( v238 == 1 )
            {
LABEL_24:
              v8 = *(_DWORD *)&v232[7];
              v15 = v247;
              goto LABEL_25;
            }
          }
          else if ( v238 == 1 )
          {
            goto LABEL_370;
          }
          v129 = ++v20;
          if ( v20 >= *(_DWORD *)(v19 + 4) )
            v20 = 0;
          v234 = v20;
LABEL_370:
          LOBYTE(v128) = 5;
          LOBYTE(v129) = 10;
          if ( (unsigned __int8)StorCheckDpcWatchdogTimerExpire(v129, v128) )
            goto LABEL_26;
          v11 = v238;
          v18 = v249;
        }
      }
      v28 = 0;
      if ( v27 + 1 < *(_DWORD *)(*(_QWORD *)(v13 + 16) + 4LL) )
        v28 = v27 + 1;
    }
    while ( v27 != _InterlockedCompareExchange((volatile signed __int32 *)(v13 + 52), v28, v27) );
    do
      v29 = _InterlockedExchange64((volatile __int64 *)(8LL * v27 + *(_QWORD *)(v13 + 56)), 0);
    while ( !v29 );
    if ( !*(_DWORD *)(*(_QWORD *)(v13 + 16) + 16LL)
      && (*(_DWORD *)v13 == 2
       || ExQueryDepthSList((PSLIST_HEADER)(*(_QWORD *)(v13 + 32) + 16LL * *(unsigned int *)(v13 + 8)))) )
    {
      if ( *(_DWORD *)(v13 + 48) == *(_DWORD *)(v13 + 52)
        || ((v30 = *(_DWORD *)(v13 + 48), v31 = *(_DWORD *)(v13 + 52), v30 != v31)
          ? (v30 <= v31
           ? ((v33 = *(_QWORD *)(v13 + 24), *(_BYTE *)(*(_QWORD *)(v13 + 16) + 20LL))
            ? (v34 = *(_QWORD *)(v33 + 1024))
            : (v34 = *(_QWORD *)(v33 + 256)),
              v32 = *(_DWORD *)(v34 + 4) - v31 + v30)
           : (v32 = v30 - v31))
          : (v32 = 0),
            v32 <= *(_DWORD *)(*(_QWORD *)(v13 + 16) + 8LL)) )
      {
        if ( !_InterlockedCompareExchange((volatile signed __int32 *)(*(_QWORD *)(v13 + 16) + 16LL), 1, 0) )
        {
          v35 = *(_QWORD *)(v13 + 24);
          if ( *(_BYTE *)(*(_QWORD *)(v13 + 16) + 20LL) )
            IoQueueWorkItem(
              *(PIO_WORKITEM *)(v35 + 1032),
              NvmeControllerRefillShadowQueueRoutine,
              DelayedWorkQueue,
              *(PVOID *)(v13 + 24));
          else
            KeSetEvent((PRKEVENT)(v35 + 480), 0, 0);
        }
      }
    }
    KeLowerIrql(v26);
    if ( (*(_BYTE *)(v249 + 136) & 2) != 0 )
    {
      v38 = NvmeNamespaceProcessRequest(*(_QWORD *)(v13 + 24), v29, v8);
      goto LABEL_175;
    }
    if ( (int)IoGetIoAttributionHandle(v29, &v251) >= 0 )
    {
      v39 = *(unsigned __int8 **)(v29 + 184);
      v40 = v251;
      v255 = 0;
      LODWORD(v255) = 1;
      v256 = 0;
      DWORD1(v255) = *v39 | 0x200;
      *((_QWORD *)&v256 + 1) = KeQueryUnbiasedInterruptTimePrecise((PULONG64)&v256 + 1);
      IoRecordIoAttribution(v40, &v255);
    }
    v41 = *(_QWORD *)(v13 + 24);
    v42 = 0;
    v43 = *(unsigned __int8 **)(v29 + 184);
    v36 = 0;
    v245[0] = 0;
    v232[2] = 0;
    LOBYTE(v37) = 0;
    v44 = *(_QWORD *)(v41 + 16);
    v45 = 0;
    v252 = 0;
    v250 = 0;
    v46 = *((_QWORD *)v43 + 1);
    v47 = v46;
    v48 = HIDWORD(*(_QWORD *)(v44 + 136));
    LOBYTE(v48) = v48 & 1;
    ListEntry = 0;
    v237 = v44;
    v243 = v48;
    v223 = 0;
    v229 = 0;
    v232[0] = 0;
    if ( v46 == 0x8765432100000003uLL )
    {
      v42 = *((_QWORD *)v43 + 3);
      v235 = (PSLIST_ENTRY)v42;
    }
    else
    {
      v235 = 0;
      if ( v46 == 0xFEDCBA9000000000uLL )
      {
        v36 = *((_QWORD *)v43 + 3);
        ListEntry = (PSLIST_ENTRY)v36;
      }
    }
    if ( (unsigned int)(*(_DWORD *)(v41 + 96) - 5) <= 1 )
    {
      v232[2] = 1;
      v38 = -1073741810;
      goto LABEL_86;
    }
    v225 = *v43;
    v37 = *v43;
    v231 = *v43 == 3;
    if ( !v42 )
    {
      v71 = *(_QWORD *)(v44 + 128);
      v42 = *(unsigned int *)(v71 + 208);
      v234 = *(_DWORD *)(v71 + 208);
      if ( (_BYTE)v48 )
      {
        v72 = *((_QWORD *)v43 + 3);
        goto LABEL_132;
      }
      if ( v36 )
      {
        v72 = *(_QWORD *)(v36 + 96);
        LODWORD(v46) = *(_DWORD *)(v36 + 116);
        *(_QWORD *)(v36 + 64) = v233;
        *(_QWORD *)(v36 + 72) = v240;
LABEL_132:
        v44 = *(unsigned int *)(v41 + 64);
        v36 = (unsigned int)v46 % (unsigned int)v44;
        if ( (unsigned int)v46 % (unsigned int)v44
          || (v36 = v72 % v44, v95 = v72 / v44, v72 % v44)
          || (v96 = *(_QWORD *)(v41 + 432), v72 / v44 >= v96)
          || (LODWORD(v36) = (unsigned int)v46 % (unsigned int)v44,
              v97 = (unsigned int)v46 / (unsigned int)v44,
              v96 - v95 < (unsigned int)v46 / (unsigned int)v44) )
        {
          v38 = -1073741811;
          v37 = 0;
          goto LABEL_86;
        }
        v98 = *(_QWORD *)(v41 + 16);
        if ( (unsigned int)v46 <= *(_DWORD *)(*(_QWORD *)(v98 + 128) + 208LL) )
        {
          v99 = *(_DWORD *)(v41 + 428);
          if ( !v99 )
          {
LABEL_143:
            v103 = 0;
            if ( (((unsigned int)v46
                 + ((*(_DWORD *)(*(_QWORD *)(v29 + 8) + 32LL) + *(_DWORD *)(*(_QWORD *)(v29 + 8) + 44LL)) & 0xFFF)
                 + 4095LL)
                & 0xFFFFFFFFFFFFF000uLL) <= 0x2000
              || (v104 = ExpInterlockedPopEntrySList(*(PSLIST_HEADER *)(*(_QWORD *)(v98 + 880) + 8 * v236)),
                  v103 = (int)v104,
                  v104)
              || (v105 = AllocateNewNVMePrpListBufferEntry(*(_QWORD *)(v41 + 16), *(unsigned int *)&v232[7]),
                  v103 = v105,
                  v105) )
            {
              v106 = v233;
              if ( v233 )
              {
                LODWORD(v107) = v240;
              }
              else
              {
                v108 = *(_QWORD *)(v41 + 16);
                if ( (*(_BYTE *)(v108 + 136) & 2) != 0 )
                {
                  v107 = *(_QWORD *)(v108 + 728) + 192 * v236;
                }
                else
                {
                  v106 = v233;
                  LODWORD(v107) = 192 * *(unsigned __int16 *)(*(_QWORD *)(v108 + 872) + 2 * v236)
                                + *(_DWORD *)(v108 + 728)
                                - 192;
                }
              }
              LOBYTE(v217) = 0;
              v109 = NvmeSubmitIoToSQ(v41, v29, v107, v103, *(_DWORD *)&v232[7], v217, v46, v72, v95, v97, v231, v106);
              v37 = 0;
              v38 = v109;
              v45 = 0;
            }
            else
            {
              NvmeNamespaceQueueIo(v41, v29, *(unsigned int *)&v232[7]);
              v37 = 0;
              v38 = -2147483631;
              v45 = 0;
            }
            goto LABEL_86;
          }
          if ( (unsigned int)v46 <= v99 )
          {
            v100 = *(_BYTE *)(v41 + 427);
            if ( v100 )
            {
              v101 = (((unsigned int)v46 & (v99 - 1)) + v99 + (unsigned __int64)((v99 - 1) & (unsigned int)v72) - 1) >> v100;
              v102 = (unsigned __int64)(unsigned int)v46 >> *(_BYTE *)(v41 + 427);
            }
            else
            {
              LODWORD(v102) = (unsigned int)v46 / v99;
              v101 = ((unsigned int)v46 % v99 - 1LL + v99 + v72 % v99) / v99;
            }
            if ( (unsigned int)(v102 + v101) <= 1 )
              goto LABEL_143;
            LODWORD(v42) = v234;
          }
        }
        v110 = NvmeSplitIoParallel(v41, v29, v72, v42, *(int *)&v232[7], v240, v233, (__int64)v232);
        v37 = 0;
        v38 = v110;
        v45 = 0;
        v229 = v232[0];
        goto LABEL_86;
      }
      v73 = *(unsigned int *)(v41 + 64);
      if ( (unsigned int)v46 % (unsigned int)v73
        || (v74 = *((_QWORD *)v43 + 3), v75 = v74 / v73, v74 % v73)
        || (v76 = *(_QWORD *)(v41 + 432), *((_QWORD *)v43 + 3) / v73 >= v76)
        || (v244 = v47 / (unsigned int)v73, v76 - v75 < v244) )
      {
        v38 = -1073741811;
        goto LABEL_160;
      }
      if ( v47 <= (unsigned int)v42 )
      {
        v77 = *(unsigned int *)(v41 + 428);
        if ( !(_DWORD)v77 )
        {
LABEL_119:
          v81 = GetNVMeSGLBufferContext(v237, *(unsigned int *)&v232[7], v77, v42);
          ListEntry = (PSLIST_ENTRY)v81;
          v82 = v81;
          if ( v81 )
          {
            *(_QWORD *)(v81 + 40) = v29;
            v83 = *(_BYTE *)(v81 + 126) & 0xFE;
            *(_QWORD *)(v82 + 96) = v74;
            *(_QWORD *)(v82 + 32) = v41;
            *(_DWORD *)(v82 + 112) = v244;
            *(_QWORD *)(v82 + 64) = v233;
            *(_QWORD *)(v82 + 72) = v240;
            *(_BYTE *)(v82 + 126) = v83 | (v225 == 3);
            *(_QWORD *)(v82 + 104) = v75;
            *(_DWORD *)(v82 + 116) = v47;
            *(_QWORD *)(v82 + 56) = *((_QWORD *)v43 + 3);
            v84 = *((_QWORD *)v43 + 1);
            *((_QWORD *)v43 + 3) = v82;
            *(_QWORD *)(v82 + 48) = v84;
            *((_QWORD *)v43 + 1) = 0xFEDCBA9000000000uLL;
            v85 = *(unsigned __int16 *)(v82 + 124);
            v86 = *(_QWORD *)(v82 + 16);
            v87 = *(_QWORD *)(*(_QWORD *)(v29 + 8) + 32LL) + *(unsigned int *)(*(_QWORD *)(v29 + 8) + 44LL);
            *(_QWORD *)(v82 + 80) = v87;
            v237 = *(_QWORD *)(v29 + 8);
            v241 = *(_QWORD *)(v41 + 16);
            v244 = v87;
            v88 = KfRaiseIrql(2u);
            v221 = v85;
            v89 = v237;
            v90 = *(_QWORD *)(v241 + 128);
            v219 = v86;
            v59 = ListEntry;
            LOBYTE(v218) = v225 != 3;
            v91 = *(_QWORD *)(v90 + 1160);
            v92 = *(_QWORD *)(v90 + 8);
            v231 = v88;
            v93 = *(_QWORD *)(v91 + 8);
            v232[1] = v225 != 3;
            v38 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, unsigned __int64, unsigned int, __int64 (__fastcall *)(), PSLIST_ENTRY, int, __int64, int))(v93 + 112))(
                    v91,
                    v92,
                    v237,
                    v87,
                    v47,
                    NvmeContinueScatterGatherProcessIO,
                    ListEntry,
                    v218,
                    v219,
                    v221);
            if ( v38 == -1073741789 )
            {
              LOBYTE(v218) = v232[1];
              v38 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, unsigned __int64, unsigned int, __int64 (__fastcall *)(), PSLIST_ENTRY, int))(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v241 + 128) + 1160LL) + 8LL) + 88LL))(
                      *(_QWORD *)(*(_QWORD *)(v241 + 128) + 1160LL),
                      *(_QWORD *)(*(_QWORD *)(v241 + 128) + 8LL),
                      v89,
                      v244,
                      v47,
                      NvmeContinueScatterGatherProcessIO,
                      v59,
                      v218);
            }
            if ( (unsigned __int8)v231 < 2u )
              KeLowerIrql(v231);
            v58 = v235;
            if ( v38 >= 0 )
              v38 = 259;
            goto LABEL_93;
          }
          v38 = -1073741670;
          goto LABEL_160;
        }
        if ( v47 <= (unsigned int)v77 )
        {
          v78 = *(_BYTE *)(v41 + 427);
          v79 = (unsigned int)v77;
          if ( v78 )
          {
            v77 = (unsigned int)(v77 - 1);
            v42 = (unsigned int)v77 & (unsigned int)v74;
            v80 = ((unsigned __int64)v47 >> v78) + ((((unsigned int)v77 & v47) + v79 + v42 - 1) >> v78);
          }
          else
          {
            v42 = v47 / (unsigned __int64)(unsigned int)v77;
            v77 = v47 % (unsigned int)v77;
            v80 = v47 / v79 + (v77 + v79 + (unsigned int)(v74 % v79) - 1LL) / v79;
          }
          if ( v80 <= 1 )
            goto LABEL_119;
          LODWORD(v42) = v234;
        }
      }
      v94 = NvmeSplitIoParallel(v41, v29, v74, v42, *(int *)&v232[7], v240, v233, (__int64)v232);
      v58 = v235;
      v38 = v94;
      v229 = v232[0];
      goto LABEL_92;
    }
    v36 = v243;
    v38 = 0;
    v49 = v233;
    LOBYTE(v37) = 0;
    v50 = v240;
    v51 = 0;
    v241 = v233;
    v242 = v240;
    v226 = 0;
    v234 = 0;
    if ( !(_BYTE)v243 )
    {
      _InterlockedIncrement16((volatile signed __int16 *)(v42 + 120));
      v223 = 1;
    }
    v44 = 4;
LABEL_64:
    v52 = v42;
    while ( 1 )
    {
      v53 = *(_WORD *)(v52 + 34);
      v237 = *(_QWORD *)(v52 + 96);
      v54 = _InterlockedCompareExchange((volatile signed __int32 *)(v52 + 104), 4, 3);
      if ( (_BYTE)v36 )
      {
        if ( v54 != 3 && _InterlockedCompareExchange((volatile signed __int32 *)(v52 + 104), 4, 1) != 1 )
          goto LABEL_78;
      }
      else if ( v54 != 3 )
      {
        if ( *(_DWORD *)(v52 + 104) == 1 )
          ++v51;
        goto LABEL_78;
      }
      v55 = NvmeSendSplitIo(
              v52,
              *(_DWORD *)&v232[7],
              v50,
              v49,
              (__int64)&v232[2],
              (__int64)&v252,
              (__int64)&v250,
              (__int64)v245,
              v37);
      v38 = v55;
      if ( v55 != 259 )
        break;
      v37 = *(_QWORD *)(v41 + 16);
      HIWORD(v56) = HIWORD(v234);
      v49 = 0;
      LOWORD(v56) = v234 + 1;
      v241 = 0;
      v50 = 0;
      v57 = (unsigned __int16)(v234 + 1) % (unsigned int)*(unsigned __int8 *)(v37 + 1730);
      v242 = 0;
      v234 = v56;
      v229 = 1;
      LOBYTE(v37) = v57 == 0;
      v226 = v57 == 0;
LABEL_77:
      v36 = v243;
      v44 = 4;
      v42 = (unsigned __int64)v235;
LABEL_78:
      v52 = v237;
      if ( v51 )
      {
        if ( !v237 )
        {
          v51 = 0;
          goto LABEL_64;
        }
      }
      else if ( !v237 )
      {
        LOBYTE(v37) = 1;
        goto LABEL_85;
      }
    }
    if ( v55 != -2147483631 )
    {
      if ( !v53 )
      {
        v232[2] = 1;
LABEL_84:
        v37 = 0;
        goto LABEL_85;
      }
      if ( v232[2] )
        goto LABEL_84;
      v49 = v241;
      v50 = v242;
      v37 = v226;
      goto LABEL_77;
    }
    _InterlockedCompareExchange((volatile signed __int32 *)(v52 + 104), 3, 4);
    NvmeNamespaceQueueIo(v41, *(_QWORD *)(v52 + 24), *(unsigned int *)&v232[7]);
    LOBYTE(v37) = 1;
LABEL_85:
    v45 = v223;
LABEL_86:
    v58 = v235;
    if ( !(_BYTE)v243 && v45 )
      _InterlockedDecrement16((volatile signed __int16 *)&v235[7].Next + 4);
    if ( !(_BYTE)v37 && v58 )
      _interlockedbittestandreset((volatile signed __int32 *)&v58[6].Next + 3, 0);
LABEL_92:
    v59 = ListEntry;
LABEL_93:
    if ( v38 != -2147483631 && v38 < 1 )
    {
      if ( v59 )
      {
        v60 = *((_QWORD *)&v59[1].Next + 1);
        if ( v60 )
        {
          v61 = *((_BYTE *)&v59[7].Next + 14) & 1;
          v62 = *(_QWORD *)(*(_QWORD *)(v41 + 16) + 128LL);
          v63 = KfRaiseIrql(2u);
          v64 = *(_QWORD *)(v62 + 1160);
          v232[1] = v63;
          (*(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)(v64 + 8) + 96LL))(v64, v60, v61 ^ 1u);
          if ( v232[1] < 2u )
            KeLowerIrql(v232[1]);
          v59 = ListEntry;
        }
        v65 = *((_QWORD *)&v59[5].Next + 1);
        v66 = v236;
        if ( v65 )
        {
          v67 = *(_QWORD *)(v41 + 16);
          *(_QWORD *)(v65 + 88) = 0;
          *(_DWORD *)(v65 + 108) = 0;
          *(_DWORD *)(v65 + 104) = 0;
          ExpInterlockedPushEntrySList(*(PSLIST_HEADER *)(*(_QWORD *)(v67 + 888) + 8 * v66), (PSLIST_ENTRY)v65);
        }
        v68 = *(_QWORD *)(v41 + 16);
        v69 = *(_QWORD *)(*((_QWORD *)&v59[2].Next + 1) + 184LL);
        *(_QWORD *)(v69 + 8) = v59[3].Next;
        *(_QWORD *)(v69 + 24) = *((_QWORD *)&v59[3].Next + 1);
        v70 = *((unsigned int *)&v59[7].Next + 2);
        *((_QWORD *)&v59[1].Next + 1) = 0;
        *((_QWORD *)&v59[5].Next + 1) = 0;
        *((_BYTE *)&v59[7].Next + 14) = 0;
        ExpInterlockedPushEntrySList(*(PSLIST_HEADER *)(*(_QWORD *)(v68 + 896) + 8 * v70), v59);
        if ( (*(_BYTE *)(v29 + 151) & 1) != 0 )
          _InterlockedDecrement(*(volatile signed __int32 **)(*(_QWORD *)(v41 + 696) + 8 * v66));
        goto LABEL_162;
      }
      if ( v58 )
      {
        if ( v232[2] )
        {
          FreeAllSglAndContextInChainedSplitIoContext(*(_QWORD *)(v41 + 16), v58, v44, v42);
          FreeNVMeChainedIoSplitContext(*(_QWORD *)(v41 + 16), *(unsigned int *)&v232[7], v58, v29);
          goto LABEL_160;
        }
      }
      else
      {
LABEL_160:
        v66 = v236;
        if ( (*(_BYTE *)(v29 + 151) & 1) != 0 )
          _InterlockedDecrement(*(volatile signed __int32 **)(*(_QWORD *)(v41 + 696) + 8 * v236));
LABEL_162:
        *(_DWORD *)(v29 + 48) = v38;
        IofCompleteRequest((PIRP)v29, 0);
        v111 = *(_QWORD *)(v41 + 128);
        if ( !*(_BYTE *)v111 )
        {
          v37 = *(_QWORD *)(*(_QWORD *)(v111 + 24) + 8 * v66);
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)v37, 0xFFFFFFFF) == 1 )
          {
            v112 = *(_QWORD *)(*(_QWORD *)(v41 + 16) + 128LL);
            v113 = *(_QWORD *)(v41 + 128);
            if ( v113 )
            {
              if ( *(_QWORD *)(v113 + 8) )
              {
                v114 = *(struct _EX_RUNDOWN_REF_CACHE_AWARE **)(v113 + 40);
                if ( v114 )
                {
                  if ( ExAcquireRundownProtectionCacheAware(v114) )
                  {
                    PoFxIdleComponent(**(_QWORD **)(*(_QWORD *)(v41 + 128) + 8LL), 0, 2);
                    v115 = *(_QWORD *)(v41 + 128);
                    if ( v115 )
                    {
                      if ( *(_QWORD *)(v115 + 8) )
                      {
                        v116 = *(struct _EX_RUNDOWN_REF_CACHE_AWARE **)(v115 + 40);
                        if ( v116 )
                          ExReleaseRundownProtectionCacheAware(v116);
                      }
                    }
                  }
                }
              }
            }
            v37 = *(_QWORD *)(v112 + 168);
            if ( *(_BYTE *)v37 == 1 )
              PoFxIdleComponent(**(_QWORD **)(v37 + 8), 0, 2);
          }
        }
      }
    }
    v9 = v248;
    v7 = v229;
LABEL_175:
    if ( v38 == 259 || v7 )
    {
LABEL_192:
      v24 = 0;
      return v24 == 0;
    }
    if ( v38 == -2147483631 )
      break;
    if ( v38 == -2147483622 )
    {
      v8 = *(_DWORD *)&v232[7];
      goto LABEL_187;
    }
    if ( v238 != 1 )
      goto LABEL_188;
LABEL_190:
    LOBYTE(v36) = 5;
    LOBYTE(v37) = 10;
    if ( !(unsigned __int8)StorCheckDpcWatchdogTimerExpire(v37, v36) )
    {
      v11 = v238;
      v8 = *(_DWORD *)&v232[7];
      continue;
    }
    break;
  }
LABEL_26:
  v24 = v233;
  return v24 == 0;
}

```

## disassembly

```asm
0x140131650  mov     [rsp-8+arg_10], rbx
0x140131655  push    rbp
0x140131656  push    rsi
0x140131657  push    rdi
0x140131658  push    r12
0x14013165a  push    r13
0x14013165c  push    r14
0x14013165e  push    r15
0x140131660  lea     rbp, [rsp-40h]
0x140131665  sub     rsp, 140h
0x14013166c  mov     rax, cs:__security_cookie
0x140131673  xor     rax, rsp
0x140131676  mov     [rbp+70h+var_38], rax
0x14013167a  mov     rbx, rcx
0x14013167d  mov     [rbp+70h+var_88], rcx
0x140131681  xor     ecx, ecx; ProcNumber
0x140131683  mov     [rsp+170h+var_100], r9
0x140131688  mov     [rbp+70h+var_C8], rdx
0x14013168c  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140131693  nop     dword ptr [rax+rax+00h]
0x140131698  mov     rdx, [rbx+458h]
0x14013169f  xor     r12b, r12b
0x1401316a2  mov     r15d, eax
0x1401316a5  mov     dword ptr [rsp+170h+var_10B+7], r15d
0x1401316aa  mov     [rsp+170h+var_10D], r12b
0x1401316af  mov     [rbp+70h+var_E8], r15
0x1401316b3  mov     r14, [rdx+r15*8]
0x1401316b7  mov     [rbp+70h+var_90], r14
0x1401316bb  mov     r13d, [r14+40h]
0x1401316bf  mov     rax, cs:g_CpuInfo
0x1401316c6  mov     r8d, [rbx+290h]
0x1401316cd  mov     [rbp+70h+var_98], rax
0x1401316d1  mov     [rbp+70h+var_D8], r8d
0x1401316d5  mov     esi, 1
0x1401316da  mov     edx, r13d
0x1401316dd  nop     dword ptr [rax]
0x1401316e0  mov     eax, r13d
0x1401316e3  mov     rdi, [r14+rax*8+108h]
0x1401316eb  test    rdi, rdi
0x1401316ee  jz      short loc_140131714
0x1401316f0  mov     rax, [rdi+10h]
0x1401316f4  cmp     dword ptr [rax], 0
0x1401316f7  jnz     loc_1401317F4
0x1401316fd  cmp     dword ptr [rdi], 0
0x140131700  jnz     loc_140131805
0x140131706  mov     ecx, [rdi+34h]
0x140131709  mov     eax, [rdi+30h]
0x14013170c  cmp     eax, ecx
0x14013170e  jnz     loc_140131805
0x140131714  cmp     r8d, 1
0x140131718  jz      short loc_14013172E
0x14013171a  lea     eax, [r13+1]
0x14013171e  xor     r13d, r13d
0x140131721  cmp     eax, [r14+4]
0x140131725  cmovb   r13d, eax
0x140131729  cmp     edx, r13d
0x14013172c  jnz     short loc_1401316E0
0x14013172e  mov     r9, [rbp+70h+var_98]
0x140131732  xor     r12d, r12d
0x140131735  mov     [r14+40h], r13d
0x140131739  mov     dword ptr [rsp+170h+var_10B+3], r12d
0x14013173e  cmp     [r9+0Ch], r12d
0x140131742  jbe     loc_1401317F4
0x140131748  movzx   r13d, [rsp+170h+var_10D]
0x14013174e  xchg    ax, ax
0x140131750  cmp     r12d, r15d
0x140131753  jz      loc_1401317E2
0x140131759  mov     r15, [rbp+70h+var_88]
0x14013175d  mov     ecx, r12d
0x140131760  mov     [rbp+70h+var_B0], rcx
0x140131764  mov     rax, [r15+458h]
0x14013176b  mov     r14, [rax+r12*8]
0x14013176f  mov     [rbp+70h+var_60], r14
0x140131773  mov     esi, [r14+40h]
0x140131777  mov     [rsp+170h+var_F8], esi
0x14013177b  nop     dword ptr [rax+rax+00h]
0x140131780  mov     edx, esi
0x140131782  nop     dword ptr [rax+00h]
0x140131786  nop     word ptr [rax+rax+00000000h]
0x140131790  mov     ebx, esi
0x140131792  mov     rbx, [r14+rbx*8+108h]
0x14013179a  test    rbx, rbx
0x14013179d  jz      short loc_1401317BF
0x14013179f  mov     rax, [rbx+10h]
0x1401317a3  cmp     dword ptr [rax], 0
0x1401317a6  jnz     short loc_1401317F4
0x1401317a8  cmp     dword ptr [rbx], 0
0x1401317ab  jnz     loc_140132567
0x1401317b1  mov     ecx, [rbx+34h]
0x1401317b4  mov     eax, [rbx+30h]
0x1401317b7  cmp     eax, ecx
0x1401317b9  jnz     loc_140132567
0x1401317bf  cmp     r8d, 1
0x1401317c3  jz      short loc_1401317D9
0x1401317c5  lea     eax, [rsi+1]
0x1401317c8  xor     esi, esi
0x1401317ca  cmp     eax, [r14+4]
0x1401317ce  cmovnz  esi, eax
0x1401317d1  mov     [rsp+170h+var_F8], esi
0x1401317d5  cmp     edx, esi
0x1401317d7  jnz     short loc_140131790
0x1401317d9  mov     r15d, dword ptr [rsp+170h+var_10B+7]
0x1401317de  mov     r9, [rbp+70h+var_98]
0x1401317e2  inc     r12d
0x1401317e5  mov     dword ptr [rsp+170h+var_10B+3], r12d
0x1401317ea  cmp     r12d, [r9+0Ch]
0x1401317ee  jb      loc_140131750
0x1401317f4  mov     rax, [rsp+170h+var_100]
0x1401317f9  test    rax, rax
0x1401317fc  setz    al
0x1401317ff  jmp     loc_1401333D2
0x140131805  mov     cl, 2; NewIrql
0x140131807  mov     [rbp+70h+var_78], 0
0x14013180f  call    cs:__imp_KfRaiseIrql
0x140131816  nop     dword ptr [rax+rax+00h]
0x14013181b  movzx   ebx, al
0x14013181e  xchg    ax, ax
0x140131820  mov     r9d, [rdi+34h]
0x140131824  mov     ecx, [rdi+30h]
0x140131827  cmp     r9d, ecx
0x14013182a  jz      loc_1401324D1
0x140131830  mov     rcx, [rdi+10h]
0x140131834  lea     r8d, [r9+1]
0x140131838  mov     eax, r9d
0x14013183b  mov     edx, [rcx+4]
0x14013183e  xor     ecx, ecx
0x140131840  cmp     r8d, edx
0x140131843  cmovb   ecx, r8d
0x140131847  lock cmpxchg [rdi+34h], ecx
0x14013184c  jnz     short loc_140131820
0x14013184e  mov     ecx, r9d
0x140131851  shl     rcx, 3
0x140131855  nop     word ptr [rax+rax+00000000h]
0x140131860  mov     rax, [rdi+38h]
0x140131864  xor     esi, esi
0x140131866  xchg    rsi, [rcx+rax]
0x14013186a  test    rsi, rsi
0x14013186d  jz      short loc_140131860
0x14013186f  mov     rax, [rdi+10h]
0x140131873  mov     ecx, [rax+10h]
0x140131876  test    ecx, ecx
0x140131878  jnz     loc_14013194D
0x14013187e  cmp     dword ptr [rdi], 2
0x140131881  jz      short loc_1401318A3
0x140131883  mov     ecx, [rdi+8]
0x140131886  shl     rcx, 4
0x14013188a  add     rcx, [rdi+20h]; SListHead
0x14013188e  call    cs:__imp_ExQueryDepthSList
0x140131895  nop     dword ptr [rax+rax+00h]
0x14013189a  test    ax, ax
0x14013189d  jz      loc_14013194D
0x1401318a3  mov     ecx, [rdi+34h]
0x1401318a6  mov     eax, [rdi+30h]
0x1401318a9  cmp     eax, ecx
0x1401318ab  jz      short loc_1401318F3
0x1401318ad  mov     edx, [rdi+30h]
0x1401318b0  mov     r8d, [rdi+34h]
0x1401318b4  cmp     edx, r8d
0x1401318b7  jnz     short loc_1401318BD
0x1401318b9  xor     edx, edx
0x1401318bb  jmp     short loc_1401318EA
0x1401318bd  jbe     short loc_1401318C4
0x1401318bf  sub     edx, r8d
0x1401318c2  jmp     short loc_1401318EA
0x1401318c4  mov     rax, [rdi+10h]
0x1401318c8  mov     rcx, [rdi+18h]
0x1401318cc  cmp     byte ptr [rax+14h], 0
0x1401318d0  jnz     short loc_1401318DB
0x1401318d2  mov     rax, [rcx+100h]
0x1401318d9  jmp     short loc_1401318E2
0x1401318db  mov     rax, [rcx+400h]
0x1401318e2  mov     ecx, [rax+4]
0x1401318e5  sub     ecx, r8d
0x1401318e8  add     edx, ecx
0x1401318ea  mov     rax, [rdi+10h]
0x1401318ee  cmp     edx, [rax+8]
0x1401318f1  ja      short loc_14013194D
0x1401318f3  mov     rcx, [rdi+10h]
0x1401318f7  xor     eax, eax
0x1401318f9  mov     edx, 1
0x1401318fe  lock cmpxchg [rcx+10h], edx
0x140131903  jnz     short loc_14013194D
0x140131905  mov     rax, [rdi+10h]
0x140131909  mov     rcx, [rdi+18h]
0x14013190d  cmp     byte ptr [rax+14h], 0
0x140131911  jnz     short loc_14013192D
0x140131913  add     rcx, 1E0h; Event
0x14013191a  xor     r8d, r8d; Wait
0x14013191d  xor     edx, edx; Increment
0x14013191f  call    cs:__imp_KeSetEvent
0x140131926  nop     dword ptr [rax+rax+00h]
0x14013192b  jmp     short loc_14013194D
0x14013192d  mov     r9, rcx; Context
0x140131930  mov     r8d, edx; QueueType
0x140131933  mov     rcx, [rcx+408h]; IoWorkItem
0x14013193a  lea     rdx, NvmeControllerRefillShadowQueueRoutine; WorkerRoutine
0x140131941  call    cs:__imp_IoQueueWorkItem
0x140131948  nop     dword ptr [rax+rax+00h]
0x14013194d  movzx   ecx, bl; NewIrql
0x140131950  call    cs:__imp_KeLowerIrql
0x140131957  nop     dword ptr [rax+rax+00h]
0x14013195c  mov     rcx, [rbp+70h+var_88]
0x140131960  test    byte ptr [rcx+88h], 2
0x140131967  jz      short loc_140131980
0x140131969  mov     rcx, [rdi+18h]
0x14013196d  mov     r8d, r15d
0x140131970  mov     rdx, rsi
0x140131973  call    NvmeNamespaceProcessRequest
0x140131978  mov     r15d, eax
0x14013197b  jmp     loc_14013249D
0x140131980  lea     rdx, [rbp+70h+var_78]
0x140131984  mov     rcx, rsi
0x140131987  call    cs:__imp_IoGetIoAttributionHandle
0x14013198e  nop     dword ptr [rax+rax+00h]
0x140131993  test    eax, eax
0x140131995  js      short loc_1401319E5
0x140131997  mov     rax, [rsi+0B8h]
0x14013199e  lea     rcx, [rbp+70h+QpcTimeStamp]; QpcTimeStamp
0x1401319a2  mov     rbx, [rbp+70h+var_78]
0x1401319a6  xorps   xmm0, xmm0
0x1401319a9  movups  [rbp+70h+var_58], xmm0
0x1401319ad  mov     dword ptr [rbp+70h+var_58], 1
0x1401319b4  movups  xmmword ptr [rbp+28h], xmm0
0x1401319b8  movzx   edx, byte ptr [rax]
0x1401319bb  bts     edx, 9
0x1401319bf  mov     dword ptr [rbp+70h+var_58+4], edx
0x1401319c2  call    cs:__imp_KeQueryUnbiasedInterruptTimePrecise
0x1401319c9  nop     dword ptr [rax+rax+00h]
0x1401319ce  lea     rdx, [rbp+70h+var_58]
0x1401319d2  mov     rcx, rbx
0x1401319d5  mov     [rbp+70h+QpcTimeStamp], rax
0x1401319d9  call    cs:__imp_IoRecordIoAttribution
0x1401319e0  nop     dword ptr [rax+rax+00h]
0x1401319e5  mov     r14, [rdi+18h]
0x1401319e9  xor     r9d, r9d
0x1401319ec  mov     rdi, [rsi+0B8h]
0x1401319f3  xor     r11b, r11b
0x1401319f6  mov     edx, r9d
0x1401319f9  mov     [rbp+70h+var_A0], r9w
0x1401319fe  mov     [rsp+170h+var_10B+2], dl
0x140131a02  xor     cl, cl
0x140131a04  mov     r8, [r14+10h]
0x140131a08  xor     r10b, r10b
0x140131a0b  mov     [rbp+70h+var_70], r9
0x140131a0f  mov     rax, 8765432100000003h
0x140131a19  mov     [rbp+70h+var_80], r9d
0x140131a1d  mov     rbx, [rdi+8]
0x140131a21  mov     r15, [r8+88h]
0x140131a28  mov     r12d, ebx
0x140131a2b  shr     r15, 20h
0x140131a2f  and     r15b, 1
0x140131a33  mov     [rbp+70h+ListEntry], rdx
0x140131a37  mov     [rsp+170h+var_10F], cl
0x140131a3b  mov     [rbp+70h+var_E0], r8
0x140131a3f  mov     [rbp+70h+var_B0], r15
0x140131a43  mov     [rsp+170h+var_110], r10b
0x140131a48  mov     [rsp+170h+var_10D], r11b
0x140131a4d  mov     [rsp+170h+var_10B], r11b
0x140131a52  cmp     rbx, rax
0x140131a55  jnz     short loc_140131A61
0x140131a57  mov     r9, [rdi+18h]
0x140131a5b  mov     [rbp+70h+var_F0], r9
0x140131a5f  jmp     short loc_140131A7C
0x140131a61  mov     rax, 0FEDCBA9000000000h
0x140131a6b  mov     [rbp+70h+var_F0], r9
0x140131a6f  cmp     rbx, rax
0x140131a72  jnz     short loc_140131A7C
0x140131a74  mov     rdx, [rdi+18h]
0x140131a78  mov     [rbp+70h+ListEntry], rdx
0x140131a7c  mov     eax, [r14+60h]
0x140131a80  sub     eax, 5
0x140131a83  cmp     eax, 1
0x140131a86  jbe     loc_140132352
0x140131a8c  movzx   ecx, byte ptr [rdi]
0x140131a8f  cmp     cl, 3
0x140131a92  mov     [rsp+170h+var_10E], cl
0x140131a96  setz    [rsp+170h+var_10C]
0x140131a9b  test    r9, r9
0x140131a9e  jz      loc_140131D95
0x140131aa4  mov     rdx, [rbp+70h+var_B0]
0x140131aa8  xor     r15d, r15d
0x140131aab  mov     r10, [rsp+170h+var_100]
0x140131ab0  xor     cl, cl
0x140131ab2  mov     r11, [rbp+70h+var_C8]
0x140131ab6  xor     edi, edi
0x140131ab8  mov     [rbp+70h+var_C0], r10
0x140131abc  mov     [rbp+70h+var_B8], r11
0x140131ac0  mov     [rsp+170h+var_10E], cl
0x140131ac4  mov     [rsp+170h+var_F8], r15d
0x140131ac9  test    dl, dl
0x140131acb  jnz     short loc_140131AD8
0x140131acd  lock inc word ptr [r9+78h]
0x140131ad3  mov     [rsp+170h+var_110], 1
0x140131ad8  mov     r8d, 4
0x140131ade  mov     rbx, r9
0x140131ae1  mov     rax, [rbx+60h]
0x140131ae5  movzx   r12d, word ptr [rbx+22h]
0x140131aea  mov     [rbp+70h+var_E0], rax
0x140131aee  mov     eax, 3
0x140131af3  lock cmpxchg [rbx+68h], r8d
  ... truncated ...
```
