# NvmeProcessPendingLowPriorityIo

- ea: `0x1400648b0`
- end: `0x140065931`
- name: `NvmeProcessPendingLowPriorityIo`
- size: `4225`
- prototype: ``
- caller_count: `3`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x140064860`
- `0x140068be0`
- `0x1401348c0`

## callees

- `0x14003ea90`
- `0x140042b60`
- `0x140043ca0`
- `0x1400479e0`
- `0x140060e90`
- `0x140062190`
- `0x1400648b0`
- `0x140065dc0`
- `0x140066260`
- `0x1400704bc`
- `0x1400707a0`
- `0x140124160`
- `0x14012f040`
- `0x14012f180`
- `0x14014b400`
- `0x14014b440`

## import_xrefs

- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140065333`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140065333`
- `ntoskrnl!PoFxIdleComponent` at `0x140065025`
- `ntoskrnl!PoFxIdleComponent` at `0x140065074`
- `ntoskrnl!PoFxIdleComponent` at `0x140065025`
- `ntoskrnl!PoFxIdleComponent` at `0x140065074`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x140064fff`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x140064fff`
- `ntoskrnl!KeSetEvent` at `0x140064ab6`
- `ntoskrnl!KeSetEvent` at `0x140064ab6`
- `ntoskrnl!KeLowerIrql` at `0x140064ae7`
- `ntoskrnl!KeLowerIrql` at `0x14006524f`
- `ntoskrnl!KeLowerIrql` at `0x1400652f6`
- `ntoskrnl!KeLowerIrql` at `0x14006572b`
- `ntoskrnl!KeLowerIrql` at `0x140064ae7`
- `ntoskrnl!KeLowerIrql` at `0x14006524f`
- `ntoskrnl!KeLowerIrql` at `0x1400652f6`
- `ntoskrnl!KeLowerIrql` at `0x14006572b`
- `ntoskrnl!KfRaiseIrql` at `0x1400649a0`
- `ntoskrnl!KfRaiseIrql` at `0x140065163`
- `ntoskrnl!KfRaiseIrql` at `0x1400652ba`
- `ntoskrnl!KfRaiseIrql` at `0x1400649a0`
- `ntoskrnl!KfRaiseIrql` at `0x140065163`
- `ntoskrnl!KfRaiseIrql` at `0x1400652ba`
- `ntoskrnl!IoQueueWorkItem` at `0x140064ad8`
- `ntoskrnl!IoQueueWorkItem` at `0x140064ad8`
- `ntoskrnl!IofCompleteRequest` at `0x140064fa2`
- `ntoskrnl!IofCompleteRequest` at `0x14006536e`
- `ntoskrnl!IofCompleteRequest` at `0x1400656b3`
- `ntoskrnl!IofCompleteRequest` at `0x140064fa2`
- `ntoskrnl!IofCompleteRequest` at `0x14006536e`
- `ntoskrnl!IofCompleteRequest` at `0x1400656b3`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14006504d`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14006504d`
- `ntoskrnl!ExQueryDepthSList` at `0x140064a21`
- `ntoskrnl!ExQueryDepthSList` at `0x140064a21`
- `ntoskrnl!KeQueryUnbiasedInterruptTimePrecise` at `0x140064b71`
- `ntoskrnl!KeQueryUnbiasedInterruptTimePrecise` at `0x140064b71`
- `ntoskrnl!IoRecordIoAttribution` at `0x140064b90`
- `ntoskrnl!IoRecordIoAttribution` at `0x140064b90`
- `ntoskrnl!IoGetIoAttributionHandle` at `0x140064b1e`
- `ntoskrnl!IoGetIoAttributionHandle` at `0x140064b1e`

## pseudocode

```c
char __fastcall NvmeProcessPendingLowPriorityIo(_QWORD *a1, __int64 a2, unsigned __int8 a3)
{
  __int64 v3; // r15
  int v4; // r12d
  char *v5; // rdx
  _QWORD *v6; // rbp
  int v7; // esi
  unsigned int v8; // r13d
  unsigned int v9; // r8d
  unsigned int v10; // ecx
  unsigned int *v11; // rbx
  int v12; // eax
  __int64 v13; // r14
  unsigned int v14; // eax
  __int64 v15; // rdi
  KIRQL v16; // bl
  unsigned __int32 v17; // r9d
  signed __int32 v18; // edx
  int v19; // r15d
  ULONG_PTR v20; // rsi
  unsigned int v21; // edx
  unsigned int v22; // r8d
  unsigned int v23; // edx
  __int64 v24; // rcx
  __int64 v25; // rax
  __int64 v26; // rcx
  unsigned __int64 v27; // rdx
  unsigned __int64 v28; // rcx
  __int64 v29; // r9
  unsigned __int8 *v30; // rax
  __int64 v31; // rbx
  ULONG_PTR v32; // rbp
  char *v33; // rdi
  char v34; // r10
  __int64 v35; // r11
  __int64 v36; // rbx
  unsigned int v37; // r12d
  unsigned __int64 v38; // r8
  char v39; // r13
  __int16 v40; // di
  unsigned __int64 v41; // rbx
  unsigned __int64 v42; // r13
  __int16 v43; // r12
  signed __int32 v44; // eax
  int v45; // eax
  int v46; // r9d
  __int64 v47; // rcx
  unsigned int v48; // eax
  unsigned __int64 v49; // rbx
  unsigned int v50; // edi
  __int64 v51; // rax
  unsigned __int64 v52; // r9
  unsigned __int64 v53; // rdi
  unsigned __int64 v54; // r8
  unsigned __int64 v55; // rbx
  unsigned __int64 v56; // r15
  unsigned __int64 v57; // rcx
  unsigned int v58; // ecx
  char v59; // al
  unsigned __int64 v60; // rax
  __int64 NVMeSGLBufferContext; // rax
  __int64 v62; // rdx
  __int64 v63; // rbx
  __int64 v64; // rax
  __int64 v65; // rbx
  __int64 v66; // rax
  struct _EX_RUNDOWN_REF_CACHE_AWARE *v67; // rcx
  __int64 v68; // rax
  struct _EX_RUNDOWN_REF_CACHE_AWARE *v69; // rcx
  char v70; // al
  __int64 v71; // rax
  int v72; // ebx
  __int64 v73; // rdi
  __int64 v74; // r15
  KIRQL v75; // r13
  __int64 v76; // rbx
  __int64 v77; // rdx
  __int64 v78; // rdi
  __int64 v79; // r10
  __int64 v80; // rdx
  __int64 v81; // r13
  __int64 v82; // r12
  unsigned __int8 v83; // di
  __int64 v84; // rbx
  KIRQL v85; // r13
  __int64 v86; // rdx
  __int64 v87; // rbx
  __int64 v88; // rcx
  __int64 v89; // rax
  int v90; // eax
  unsigned __int64 v91; // r15
  unsigned __int64 v92; // r12
  unsigned int v93; // ecx
  char v94; // al
  unsigned __int64 v95; // rax
  unsigned __int64 v96; // r9
  int v97; // r9d
  unsigned int v98; // r13d
  __int64 NVMePrpListBufferEntry; // rax
  __int64 NewNVMePrpListBufferEntry; // rax
  __int64 v101; // r10
  __int64 v102; // r8
  int v103; // eax
  int v104; // eax
  __int64 v105; // rbx
  __int64 v106; // rax
  __int64 v107; // rax
  unsigned int v108; // eax
  __int64 v109; // rcx
  __int64 v110; // rcx
  unsigned int v111; // r8d
  __int64 v112; // rdx
  __int64 v113; // r8
  _DWORD *v114; // rax
  _DWORD *v116; // r9
  __int64 v117; // r8
  _DWORD *v118; // rax
  int v119; // [rsp+28h] [rbp-140h]
  int v120; // [rsp+38h] [rbp-130h]
  __int64 v121; // [rsp+40h] [rbp-128h]
  int v122; // [rsp+48h] [rbp-120h]
  char v123; // [rsp+60h] [rbp-108h]
  char v124; // [rsp+62h] [rbp-106h]
  unsigned __int8 v125; // [rsp+62h] [rbp-106h]
  char v126; // [rsp+63h] [rbp-105h] BYREF
  int v127; // [rsp+64h] [rbp-104h]
  unsigned __int8 v128; // [rsp+68h] [rbp-100h]
  char v129; // [rsp+69h] [rbp-FFh]
  __int64 v130; // [rsp+70h] [rbp-F8h]
  unsigned int v131; // [rsp+78h] [rbp-F0h]
  unsigned __int64 v132; // [rsp+80h] [rbp-E8h]
  unsigned __int64 v133; // [rsp+88h] [rbp-E0h]
  __int16 v134; // [rsp+90h] [rbp-D8h] BYREF
  __int64 v135; // [rsp+98h] [rbp-D0h]
  int v136; // [rsp+A0h] [rbp-C8h]
  __int64 v137; // [rsp+A8h] [rbp-C0h]
  int v138; // [rsp+B0h] [rbp-B8h]
  _DWORD *v139; // [rsp+B8h] [rbp-B0h]
  int v140; // [rsp+C0h] [rbp-A8h] BYREF
  unsigned int v141; // [rsp+C4h] [rbp-A4h]
  __int64 v142; // [rsp+C8h] [rbp-A0h]
  __int64 v143; // [rsp+D0h] [rbp-98h] BYREF
  __int64 v144; // [rsp+D8h] [rbp-90h] BYREF
  __int64 v145; // [rsp+E0h] [rbp-88h]
  _QWORD *v146; // [rsp+E8h] [rbp-80h]
  __int128 v147; // [rsp+F0h] [rbp-78h] BYREF
  unsigned __int64 QpcTimeStamp[2]; // [rsp+100h] [rbp-68h] BYREF

  v3 = a1[33];
  v4 = 0;
  v5 = (char *)g_CpuInfo;
  v6 = a1;
  v146 = a1;
  v7 = 0;
  v128 = a3;
  v8 = *(_DWORD *)(v3 + 44);
  v9 = v8;
  v10 = v8;
  v139 = g_CpuInfo;
  v141 = v8;
  v11 = (unsigned int *)((char *)g_CpuInfo + 8);
  v138 = 0;
  v142 = v3;
  v127 = v8;
  v131 = v8;
  while ( 1 )
  {
LABEL_2:
    v12 = v4;
    if ( v10 != v8 )
      v12 = v7;
    v7 = v12;
    v136 = v12;
    v130 = v8;
    v13 = *(_QWORD *)(v3 + 8LL * v8 + 64);
    if ( *(_DWORD *)v13 || *(_DWORD *)(v13 + 48) != *(_DWORD *)(v13 + 52) )
      break;
    v14 = v8 + 1;
    v8 = 0;
    if ( v14 < *v11 )
      v8 = v14;
    v127 = v8;
    if ( v9 == v8 && v7 == v4 )
      goto LABEL_189;
    v10 = v141;
    v11 = (unsigned int *)(v5 + 8);
  }
  v15 = v6[2];
  v143 = 0;
  v16 = KfRaiseIrql(2u);
  do
  {
    v17 = *(_DWORD *)(v13 + 52);
    if ( v17 == *(_DWORD *)(v13 + 48) )
    {
      if ( _InterlockedCompareExchange((volatile signed __int32 *)v13, 0, 1) == 1 )
      {
        v107 = *(_QWORD *)(v13 + 24);
        if ( *(_BYTE *)(*(_QWORD *)(v13 + 16) + 20LL) == 1 )
          _InterlockedDecrement((volatile signed __int32 *)(v107 + 956));
        else
          _InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)(v107 + 16) + 952LL));
      }
      KeLowerIrql(v16);
      goto LABEL_172;
    }
    v18 = 0;
    if ( v17 + 1 < *(_DWORD *)(*(_QWORD *)(v13 + 16) + 4LL) )
      v18 = v17 + 1;
  }
  while ( v17 != _InterlockedCompareExchange((volatile signed __int32 *)(v13 + 52), v18, v17) );
  v19 = 0;
  do
    v20 = _InterlockedExchange64((volatile __int64 *)(8LL * v17 + *(_QWORD *)(v13 + 56)), 0);
  while ( !v20 );
  if ( !*(_DWORD *)(*(_QWORD *)(v13 + 16) + 16LL)
    && (*(_DWORD *)v13 == 2
     || ExQueryDepthSList((PSLIST_HEADER)(*(_QWORD *)(v13 + 32) + 16LL * *(unsigned int *)(v13 + 8)))) )
  {
    if ( *(_DWORD *)(v13 + 48) == *(_DWORD *)(v13 + 52)
      || ((v21 = *(_DWORD *)(v13 + 48), v22 = *(_DWORD *)(v13 + 52), v21 != v22)
        ? (v21 <= v22
         ? ((v24 = *(_QWORD *)(v13 + 24), *(_BYTE *)(*(_QWORD *)(v13 + 16) + 20LL))
          ? (v25 = *(_QWORD *)(v24 + 1024))
          : (v25 = *(_QWORD *)(v24 + 256)),
            v23 = *(_DWORD *)(v25 + 4) - v22 + v21)
         : (v23 = v21 - v22))
        : (v23 = 0),
          v23 <= *(_DWORD *)(*(_QWORD *)(v13 + 16) + 8LL)) )
    {
      if ( !_InterlockedCompareExchange((volatile signed __int32 *)(*(_QWORD *)(v13 + 16) + 16LL), 1, 0) )
      {
        v26 = *(_QWORD *)(v13 + 24);
        if ( *(_BYTE *)(*(_QWORD *)(v13 + 16) + 20LL) )
          IoQueueWorkItem(
            *(PIO_WORKITEM *)(v26 + 1032),
            NvmeControllerRefillShadowQueueRoutine,
            DelayedWorkQueue,
            *(PVOID *)(v13 + 24));
        else
          KeSetEvent((PRKEVENT)(v26 + 480), 0, 0);
      }
    }
  }
  KeLowerIrql(v16);
  if ( (*(_BYTE *)(v15 + 136) & 2) != 0 )
  {
    v19 = NvmeNamespaceProcessRequest(*(_QWORD *)(v13 + 24), v20, v8);
    goto LABEL_109;
  }
  if ( (int)IoGetIoAttributionHandle(v20, &v143) >= 0 )
  {
    v30 = *(unsigned __int8 **)(v20 + 184);
    v31 = v143;
    v147 = 0;
    LODWORD(v147) = 1;
    *(_OWORD *)QpcTimeStamp = 0;
    DWORD1(v147) = *v30 | 0x200;
    QpcTimeStamp[1] = KeQueryUnbiasedInterruptTimePrecise(&QpcTimeStamp[1]);
    IoRecordIoAttribution(v31, &v147);
  }
  v32 = *(_QWORD *)(v13 + 24);
  v27 = 0;
  v33 = *(char **)(v20 + 184);
  LOBYTE(v29) = 0;
  v126 = 0;
  v34 = 0;
  v134 = 0;
  v35 = *(_QWORD *)(v32 + 16);
  v144 = 0;
  v140 = 0;
  v36 = *((_QWORD *)v33 + 1);
  v37 = v36;
  v38 = HIDWORD(*(_QWORD *)(v35 + 136));
  LOBYTE(v38) = v38 & 1;
  v137 = 0;
  v133 = v38;
  v123 = 0;
  if ( v36 == 0x8765432100000003uLL )
  {
    v28 = *((_QWORD *)v33 + 3);
    v132 = v28;
  }
  else
  {
    v28 = 0;
    v132 = 0;
    if ( v36 == 0xFEDCBA9000000000uLL )
    {
      v27 = *((_QWORD *)v33 + 3);
      v137 = v27;
    }
  }
  if ( (unsigned int)(*(_DWORD *)(v32 + 96) - 5) <= 1 )
  {
    v126 = 1;
    v19 = -1073741810;
    goto LABEL_70;
  }
  v129 = *v33;
  v39 = v129;
  v124 = v129 == 3;
  if ( !v28 )
  {
    v51 = *(_QWORD *)(v35 + 128);
    v52 = *(unsigned int *)(v51 + 208);
    LODWORD(v135) = *(_DWORD *)(v51 + 208);
    if ( (_BYTE)v38 )
    {
      v53 = *((_QWORD *)v33 + 3);
      goto LABEL_137;
    }
    if ( v27 )
    {
      v53 = *(_QWORD *)(v27 + 96);
      LODWORD(v36) = *(_DWORD *)(v27 + 116);
      *(_QWORD *)(v27 + 64) = 0;
      *(_QWORD *)(v27 + 72) = 0;
LABEL_137:
      v38 = *(unsigned int *)(v32 + 64);
      v27 = (unsigned int)v36 % (unsigned int)v38;
      if ( (unsigned int)v36 % (unsigned int)v38
        || (v27 = v53 % v38, v91 = v53 / v38, v53 % v38)
        || (v28 = *(_QWORD *)(v32 + 432), v53 / v38 >= v28)
        || (v28 -= v91,
            LODWORD(v27) = (unsigned int)v36 % (unsigned int)v38,
            v92 = (unsigned int)v36 / (unsigned int)v38,
            v28 < v92) )
      {
        v19 = -1073741811;
        v29 = 0;
        goto LABEL_70;
      }
      if ( (unsigned int)v36 <= *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v32 + 16) + 128LL) + 208LL) )
      {
        v93 = *(_DWORD *)(v32 + 428);
        if ( !v93 )
        {
LABEL_148:
          v97 = 0;
          v98 = v127;
          if ( (((unsigned int)v36
               + ((*(_DWORD *)(*(_QWORD *)(v20 + 8) + 32LL) + *(_DWORD *)(*(_QWORD *)(v20 + 8) + 44LL)) & 0xFFF)
               + 4095LL)
              & 0xFFFFFFFFFFFFF000uLL) <= 0x2000
            || (NVMePrpListBufferEntry = GetNVMePrpListBufferEntry(*(_QWORD *)(v32 + 16), (unsigned int)v127, v38, 0),
                v97 = NVMePrpListBufferEntry,
                NVMePrpListBufferEntry)
            || (NewNVMePrpListBufferEntry = AllocateNewNVMePrpListBufferEntry(*(_QWORD *)(v32 + 16), v98),
                v97 = NewNVMePrpListBufferEntry,
                NewNVMePrpListBufferEntry) )
          {
            v101 = *(_QWORD *)(v32 + 16);
            if ( (*(_BYTE *)(v101 + 136) & 2) != 0 )
              v102 = *(_QWORD *)(v101 + 728) + 192 * v130;
            else
              LODWORD(v102) = 192 * *(unsigned __int16 *)(*(_QWORD *)(v101 + 872) + 2 * v130)
                            + *(_DWORD *)(v101 + 728)
                            - 192;
            LOBYTE(v119) = 0;
            v103 = NvmeSubmitIoToSQ(v32, v20, v102, v97, v98, v119, v36, v53, v91, v92, v124, 0);
            v29 = 0;
            v19 = v103;
            v34 = 0;
          }
          else
          {
            NvmeNamespaceQueueIo(v32, v20, v98);
            v29 = 0;
            v19 = -2147483631;
            v34 = 0;
          }
          goto LABEL_70;
        }
        if ( (unsigned int)v36 <= v93 )
        {
          v94 = *(_BYTE *)(v32 + 427);
          if ( v94 )
          {
            v38 = *(unsigned __int8 *)(v32 + 427);
            v95 = (((unsigned int)v36 & (v93 - 1)) + v93 + (unsigned __int64)((v93 - 1) & (unsigned int)v53) - 1) >> v94;
            v96 = (unsigned int)v36 >> v38;
          }
          else
          {
            v38 = (unsigned int)v36 % (unsigned __int64)v93;
            LODWORD(v96) = (unsigned int)v36 / v93;
            v95 = ((unsigned int)v38 - 1LL + v93 + v53 % v93) / v93;
          }
          if ( (unsigned int)(v96 + v95) <= 1 )
            goto LABEL_148;
          LODWORD(v52) = v135;
        }
      }
      v104 = NvmeSplitIoParallel(v32, v20, v53, v52, v127, 0, 0, 0);
      v29 = 0;
      v19 = v104;
      v34 = 0;
      goto LABEL_70;
    }
    v54 = *(unsigned int *)(v32 + 64);
    if ( (unsigned int)v36 % (unsigned int)v54
      || (v55 = *((_QWORD *)v33 + 3), v56 = v55 / v54, v55 % v54)
      || (v57 = *(_QWORD *)(v32 + 432), *((_QWORD *)v33 + 3) / v54 >= v57)
      || (v133 = v37 / (unsigned int)v54, v57 - v56 < v133) )
    {
      v19 = -1073741811;
      goto LABEL_93;
    }
    if ( v37 <= (unsigned int)v52 )
    {
      v58 = *(_DWORD *)(v32 + 428);
      if ( !v58 )
      {
LABEL_91:
        NVMeSGLBufferContext = GetNVMeSGLBufferContext(v35, (unsigned int)v127, v54, v52);
        v137 = NVMeSGLBufferContext;
        v62 = NVMeSGLBufferContext;
        if ( !NVMeSGLBufferContext )
        {
          v19 = -1073741670;
          goto LABEL_93;
        }
        *(_QWORD *)(NVMeSGLBufferContext + 40) = v20;
        v70 = *(_BYTE *)(NVMeSGLBufferContext + 126);
        *(_QWORD *)(v62 + 96) = v55;
        *(_QWORD *)(v62 + 32) = v32;
        *(_QWORD *)(v62 + 104) = v56;
        *(_DWORD *)(v62 + 112) = v133;
        *(_QWORD *)(v62 + 64) = 0;
        *(_QWORD *)(v62 + 72) = 0;
        *(_BYTE *)(v62 + 126) = v70 & 0xFE | (v39 == 3);
        *(_DWORD *)(v62 + 116) = v37;
        *(_QWORD *)(v62 + 56) = *((_QWORD *)v33 + 3);
        v71 = *((_QWORD *)v33 + 1);
        *((_QWORD *)v33 + 3) = v62;
        *(_QWORD *)(v62 + 48) = v71;
        *((_QWORD *)v33 + 1) = 0xFEDCBA9000000000uLL;
        v72 = *(unsigned __int16 *)(v62 + 124);
        v73 = *(_QWORD *)(v62 + 16);
        v74 = *(_QWORD *)(*(_QWORD *)(v20 + 8) + 32LL) + *(unsigned int *)(*(_QWORD *)(v20 + 8) + 44LL);
        *(_QWORD *)(v62 + 80) = v74;
        v135 = *(_QWORD *)(v20 + 8);
        v133 = *(_QWORD *)(v32 + 16);
        v145 = v74;
        v75 = KfRaiseIrql(2u);
        v122 = v72;
        v76 = v135;
        v121 = v73;
        v77 = *(_QWORD *)(v133 + 128);
        v78 = v137;
        v79 = *(_QWORD *)(v77 + 1160);
        v80 = *(_QWORD *)(v77 + 8);
        v129 = v129 != 3;
        LOBYTE(v120) = v129;
        v19 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int64, unsigned int, __int64 (__fastcall *)(), __int64, int, __int64, int))(*(_QWORD *)(v79 + 8) + 112LL))(
                v79,
                v80,
                v135,
                v74,
                v37,
                NvmeContinueScatterGatherProcessIO,
                v137,
                v120,
                v121,
                v122);
        if ( v19 == -1073741789 )
        {
          LOBYTE(v120) = v129;
          v19 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, __int64, unsigned int, __int64 (__fastcall *)(), __int64, int))(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v133 + 128) + 1160LL) + 8LL) + 88LL))(
                  *(_QWORD *)(*(_QWORD *)(v133 + 128) + 1160LL),
                  *(_QWORD *)(*(_QWORD *)(v133 + 128) + 8LL),
                  v76,
                  v145,
                  v37,
                  NvmeContinueScatterGatherProcessIO,
                  v78,
                  v120);
        }
        if ( v75 < 2u )
          KeLowerIrql(v75);
        v49 = v132;
        if ( v19 >= 0 )
          v19 = 259;
LABEL_119:
        v50 = v127;
        goto LABEL_120;
      }
      if ( v37 <= v58 )
      {
        v59 = *(_BYTE *)(v32 + 427);
        if ( v59 )
        {
          v54 = *(unsigned __int8 *)(v32 + 427);
          v60 = ((v37 & (v58 - 1)) + v58 + (unsigned __int64)((v58 - 1) & (unsigned int)v55) - 1) >> v59;
          v52 = v37 >> v54;
        }
        else
        {
          v54 = v37 % (unsigned __int64)v58;
          v52 = v37 / (unsigned __int64)v58;
          v60 = ((unsigned int)v54 - 1LL + v58 + v55 % v58) / v58;
        }
        if ( (unsigned int)(v52 + v60) <= 1 )
          goto LABEL_91;
        LODWORD(v52) = v135;
      }
    }
    v50 = v127;
    v90 = NvmeSplitIoParallel(v32, v20, v55, v52, v127, 0, 0, 0);
    v49 = v132;
    v19 = v90;
    goto LABEL_120;
  }
  LOBYTE(v27) = 0;
  LODWORD(v135) = 0;
  v40 = 0;
  v125 = 0;
  if ( !(_BYTE)v38 )
  {
    _InterlockedIncrement16((volatile signed __int16 *)(v28 + 120));
    v123 = 1;
  }
  v29 = 4;
LABEL_48:
  v41 = v28;
  while ( 1 )
  {
    v42 = *(_QWORD *)(v41 + 96);
    v43 = *(_WORD *)(v41 + 34);
    v44 = _InterlockedCompareExchange((volatile signed __int32 *)(v41 + 104), 4, 3);
    if ( (_BYTE)v38 )
    {
      if ( v44 != 3 && _InterlockedCompareExchange((volatile signed __int32 *)(v41 + 104), 4, 1) != 1 )
        goto LABEL_62;
    }
    else if ( v44 != 3 )
    {
      if ( *(_DWORD *)(v41 + 104) == 1 )
        ++v40;
      goto LABEL_62;
    }
    v45 = NvmeSendSplitIo(v41, v127, 0, 0, (__int64)&v126, (__int64)&v144, (__int64)&v140, (__int64)&v134, v27);
    v19 = v45;
    if ( v45 != 259 )
      break;
    HIWORD(v46) = WORD1(v135);
    v47 = *(_QWORD *)(v32 + 16);
    LOWORD(v46) = v135 + 1;
    v48 = (unsigned __int16)(v135 + 1);
    LODWORD(v135) = v46;
    v27 = v48 % *(unsigned __int8 *)(v47 + 1730);
    LOBYTE(v27) = v48 % *(unsigned __int8 *)(v47 + 1730) == 0;
    v125 = v27;
LABEL_61:
    v38 = v133;
    v29 = 4;
    v28 = v132;
LABEL_62:
    v41 = v42;
    if ( v40 && !v42 )
    {
      v40 = 0;
      goto LABEL_48;
    }
    if ( !v42 )
    {
      LOBYTE(v29) = 1;
      goto LABEL_69;
    }
  }
  if ( v45 != -2147483631 )
  {
    if ( !v43 )
    {
      v126 = 1;
LABEL_68:
      v29 = 0;
      goto LABEL_69;
    }
    if ( v126 )
      goto LABEL_68;
    v27 = v125;
    goto LABEL_61;
  }
  _InterlockedCompareExchange((volatile signed __int32 *)(v41 + 104), 3, 4);
  NvmeNamespaceQueueIo(v32, *(_QWORD *)(v41 + 24), (unsigned int)v127);
  LOBYTE(v29) = 1;
LABEL_69:
  v34 = v123;
LABEL_70:
  v49 = v132;
  if ( !(_BYTE)v133 && v34 )
    _InterlockedDecrement16((volatile signed __int16 *)(v132 + 120));
  if ( (_BYTE)v29 )
    goto LABEL_119;
  v50 = v127;
  if ( v49 )
    _interlockedbittestandreset((volatile signed __int32 *)(v49 + 108), 0);
LABEL_120:
  if ( v19 == -2147483631 || v19 >= 1 )
    goto LABEL_108;
  v81 = v137;
  if ( v137 )
  {
    v82 = *(_QWORD *)(v137 + 24);
    if ( v82 )
    {
      v83 = *(_BYTE *)(v137 + 126) & 1;
      v84 = *(_QWORD *)(*(_QWORD *)(v32 + 16) + 128LL);
      v85 = KfRaiseIrql(2u);
      (*(void (__fastcall **)(_QWORD, __int64, _QWORD))(*(_QWORD *)(*(_QWORD *)(v84 + 1160) + 8LL) + 96LL))(
        *(_QWORD *)(v84 + 1160),
        v82,
        v83 ^ 1u);
      if ( v85 < 2u )
        KeLowerIrql(v85);
      v81 = v137;
    }
    v86 = *(_QWORD *)(v81 + 88);
    v87 = v130;
    if ( v86 )
    {
      v88 = *(_QWORD *)(v32 + 16);
      *(_QWORD *)(v86 + 88) = 0;
      *(_DWORD *)(v86 + 108) = 0;
      *(_DWORD *)(v86 + 104) = 0;
      ExpInterlockedPushEntrySList(*(PSLIST_HEADER *)(*(_QWORD *)(v88 + 888) + 8 * v87), (PSLIST_ENTRY)v86);
    }
    LOBYTE(v38) = 1;
    FreeNVMeSGLBufferContext(*(_QWORD *)(v32 + 16), v81, v38);
    if ( (*(_BYTE *)(v20 + 151) & 1) != 0 )
      _InterlockedDecrement(*(volatile signed __int32 **)(*(_QWORD *)(v32 + 696) + 8 * v87));
    *(_DWORD *)(v20 + 48) = v19;
    IofCompleteRequest((PIRP)v20, 0);
    v89 = *(_QWORD *)(v32 + 128);
    if ( !*(_BYTE *)v89 )
    {
      v28 = *(_QWORD *)(*(_QWORD *)(v89 + 24) + 8 * v87);
      goto LABEL_97;
    }
    goto LABEL_108;
  }
  if ( v49 )
  {
    if ( v126 )
    {
      FreeAllSglAndContextInChainedSplitIoContext(*(_QWORD *)(v32 + 16), v49, v38, v29);
      FreeNVMeChainedIoSplitContext(*(_QWORD *)(v32 + 16), v50, v49, v20);
      v105 = v130;
      if ( (*(_BYTE *)(v20 + 151) & 1) != 0 )
        _InterlockedDecrement(*(volatile signed __int32 **)(*(_QWORD *)(v32 + 696) + 8 * v130));
      *(_DWORD *)(v20 + 48) = v19;
      IofCompleteRequest((PIRP)v20, 0);
      v106 = *(_QWORD *)(v32 + 128);
      if ( !*(_BYTE *)v106 )
      {
        v28 = *(_QWORD *)(*(_QWORD *)(v106 + 24) + 8 * v105);
        goto LABEL_97;
      }
    }
    goto LABEL_108;
  }
LABEL_93:
  v63 = 8 * v130;
  if ( (*(_BYTE *)(v20 + 151) & 1) != 0 )
    _InterlockedDecrement(*(volatile signed __int32 **)(*(_QWORD *)(v32 + 696) + 8 * v130));
  *(_DWORD *)(v20 + 48) = v19;
  IofCompleteRequest((PIRP)v20, 0);
  v64 = *(_QWORD *)(v32 + 128);
  if ( !*(_BYTE *)v64 )
  {
    v28 = *(_QWORD *)(*(_QWORD *)(v64 + 24) + v63);
LABEL_97:
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v28, 0xFFFFFFFF) == 1 )
    {
      v65 = *(_QWORD *)(*(_QWORD *)(v32 + 16) + 128LL);
      v66 = *(_QWORD *)(v32 + 128);
      if ( v66 )
      {
        if ( *(_QWORD *)(v66 + 8) )
        {
          v67 = *(struct _EX_RUNDOWN_REF_CACHE_AWARE **)(v66 + 40);
          if ( v67 )
          {
            if ( ExAcquireRundownProtectionCacheAware(v67) )
            {
              PoFxIdleComponent(**(_QWORD **)(*(_QWORD *)(v32 + 128) + 8LL), 0, 2);
              v68 = *(_QWORD *)(v32 + 128);
              if ( v68 )
              {
                if ( *(_QWORD *)(v68 + 8) )
                {
                  v69 = *(struct _EX_RUNDOWN_REF_CACHE_AWARE **)(v68 + 40);
                  if ( v69 )
                    ExReleaseRundownProtectionCacheAware(v69);
                }
              }
            }
          }
        }
      }
      v28 = *(_QWORD *)(v65 + 168);
      if ( *(_BYTE *)v28 == 1 )
        PoFxIdleComponent(**(_QWORD **)(v28 + 8), 0, 2);
    }
  }
LABEL_108:
  v8 = v127;
  v6 = v146;
  v4 = v138;
LABEL_109:
  if ( v19 == 259 || !v19 )
  {
    v7 = v136;
    ++v4;
    v3 = v142;
    v138 = v4;
LABEL_172:
    v108 = v8 + 1;
    v8 = 0;
    v11 = v139 + 2;
    if ( v108 < v139[2] )
      v8 = v108;
    v127 = v8;
    if ( v131 == v8 && v7 == v4 )
    {
LABEL_189:
      *(_DWORD *)(v3 + 44) = v8;
      goto LABEL_190;
    }
    LOBYTE(v27) = 99;
    LOBYTE(v28) = 98;
    if ( (unsigned __int8)StorCheckDpcWatchdogTimerExpire(v28, v27) )
      goto LABEL_200;
    v109 = *(_QWORD *)(v6[16] + 8LL);
    if ( !v109 || *(_BYTE *)(v109 + 64) )
    {
      v110 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v6[2] + 128LL) + 168LL) + 8LL);
      if ( !v110 || *(_BYTE *)(v110 + 64) )
      {
        if ( !v128 && *(_DWORD *)(v6[33] + 40LL) )
          goto LABEL_200;
        v111 = *((_DWORD *)g_CpuInfo + 3);
        if ( v111 )
        {
          v112 = 0;
          while ( !**(_DWORD **)(v6[87] + 8 * v112) )
          {
            v112 = (unsigned int)(v112 + 1);
            if ( (unsigned int)v112 >= v111 )
              goto LABEL_187;
          }
LABEL_200:
          v116 = g_CpuInfo;
          v117 = 0;
          for ( *(_DWORD *)(v3 + 44) = v8; (unsigned int)v117 < v116[3]; v117 = (unsigned int)(v117 + 1) )
          {
            v118 = *(_DWORD **)(*(_QWORD *)(*(_QWORD *)(v13 + 24) + 264LL) + 8 * v117 + 64);
            if ( v118 )
            {
              if ( *v118 || v118[12] != v118[13] )
                goto LABEL_199;
            }
          }
LABEL_190:
          if ( v128 )
            _InterlockedExchange((volatile __int32 *)(v6[33] + 40LL), 0);
          v113 = 0;
          if ( !*((_DWORD *)g_CpuInfo + 3) )
            return 0;
          while ( 1 )
          {
            v114 = *(_DWORD **)(*(_QWORD *)(*(_QWORD *)(v13 + 24) + 264LL) + 8 * v113 + 64);
            if ( v114 )
            {
              if ( *v114 || v114[12] != v114[13] )
                break;
            }
            v113 = (unsigned int)(v113 + 1);
            if ( (unsigned int)v113 >= *((_DWORD *)g_CpuInfo + 3) )
              return 0;
          }
          NvmeSetLowPriorityIoTimer(*(_QWORD *)(v13 + 24), -120000, 0);
          return 1;
        }
      }
LABEL_187:
      v127 = v8;
    }
    v5 = (char *)v139;
    v9 = v131;
    v10 = v141;
    goto LABEL_2;
  }
  if ( v19 != -2147483631 )
  {
    v7 = v136;
    v3 = v142;
    goto LABEL_172;
  }
  *(_DWORD *)(v142 + 44) = v8;
LABEL_199:
  NvmeSetLowPriorityIoTimer(v6, -120000, v128);
  return 1;
}

```

## disassembly

```asm
0x1400648b0  push    rbx
0x1400648b2  push    rbp
0x1400648b3  push    rsi
0x1400648b4  push    rdi
0x1400648b5  push    r12
0x1400648b7  push    r13
0x1400648b9  push    r14
0x1400648bb  push    r15
0x1400648bd  sub     rsp, 128h
0x1400648c4  mov     rax, cs:__security_cookie
0x1400648cb  xor     rax, rsp
0x1400648ce  mov     [rsp+168h+var_58], rax
0x1400648d6  mov     r15, [rcx+108h]
0x1400648dd  xor     r12d, r12d
0x1400648e0  mov     rdx, cs:g_CpuInfo
0x1400648e7  mov     rbp, rcx
0x1400648ea  mov     [rsp+168h+var_80], rcx
0x1400648f2  xor     esi, esi
0x1400648f4  mov     [rsp+168h+var_100], r8b
0x1400648f9  mov     r13d, [r15+2Ch]
0x1400648fd  mov     r8d, r13d
0x140064900  mov     ecx, r13d
0x140064903  mov     [rsp+168h+var_B0], rdx
0x14006490b  mov     [rsp+168h+var_A4], ecx
0x140064912  lea     rbx, [rdx+8]
0x140064916  mov     [rsp+168h+var_B8], r12d
0x14006491e  mov     [rsp+168h+var_A0], r15
0x140064926  mov     [rsp+168h+var_104], r13d
0x14006492b  mov     [rsp+168h+var_F0], r13d
0x140064930  cmp     ecx, r13d
0x140064933  mov     eax, r12d
0x140064936  cmovnz  eax, esi
0x140064939  mov     esi, eax
0x14006493b  mov     [rsp+168h+var_C8], eax
0x140064942  mov     eax, r13d
0x140064945  mov     [rsp+168h+var_F8], rax
0x14006494a  mov     r14, [r15+rax*8+40h]
0x14006494f  cmp     dword ptr [r14], 0
0x140064953  jnz     short loc_14006498E
0x140064955  mov     ecx, [r14+34h]
0x140064959  mov     eax, [r14+30h]
0x14006495d  cmp     eax, ecx
0x14006495f  jnz     short loc_14006498E
0x140064961  lea     eax, [r13+1]
0x140064965  xor     r13d, r13d
0x140064968  cmp     eax, [rbx]
0x14006496a  cmovb   r13d, eax
0x14006496e  mov     [rsp+168h+var_104], r13d
0x140064973  cmp     r8d, r13d
0x140064976  jnz     short loc_140064981
0x140064978  cmp     esi, r12d
0x14006497b  jz      loc_140065812
0x140064981  mov     ecx, [rsp+168h+var_A4]
0x140064988  lea     rbx, [rdx+8]
0x14006498c  jmp     short loc_140064930
0x14006498e  mov     rdi, [rbp+10h]
0x140064992  mov     cl, 2; NewIrql
0x140064994  mov     [rsp+168h+var_98], 0
0x1400649a0  call    cs:__imp_KfRaiseIrql
0x1400649a7  nop     dword ptr [rax+rax+00h]
0x1400649ac  movzx   ebx, al
0x1400649af  nop
0x1400649b0  mov     r9d, [r14+34h]
0x1400649b4  mov     ecx, [r14+30h]
0x1400649b8  cmp     r9d, ecx
0x1400649bb  jz      loc_1400656F8
0x1400649c1  mov     rax, [r14+10h]
0x1400649c5  lea     r8d, [r9+1]
0x1400649c9  xor     edx, edx
0x1400649cb  cmp     r8d, [rax+4]
0x1400649cf  mov     eax, r9d
0x1400649d2  cmovb   edx, r8d
0x1400649d6  lock cmpxchg [r14+34h], edx
0x1400649dc  jnz     short loc_1400649B0
0x1400649de  mov     ecx, r9d
0x1400649e1  shl     rcx, 3
0x1400649e5  xor     r15d, r15d
0x1400649e8  nop     dword ptr [rax+rax+00000000h]
0x1400649f0  mov     rax, [r14+38h]
0x1400649f4  mov     rsi, r15
0x1400649f7  xchg    rsi, [rcx+rax]
0x1400649fb  test    rsi, rsi
0x1400649fe  jz      short loc_1400649F0
0x140064a00  mov     rax, [r14+10h]
0x140064a04  mov     ecx, [rax+10h]
0x140064a07  test    ecx, ecx
0x140064a09  jnz     loc_140064AE4
0x140064a0f  cmp     dword ptr [r14], 2
0x140064a13  jz      short loc_140064A36
0x140064a15  mov     ecx, [r14+8]
0x140064a19  shl     rcx, 4
0x140064a1d  add     rcx, [r14+20h]; SListHead
0x140064a21  call    cs:__imp_ExQueryDepthSList
0x140064a28  nop     dword ptr [rax+rax+00h]
0x140064a2d  test    ax, ax
0x140064a30  jz      loc_140064AE4
0x140064a36  mov     ecx, [r14+34h]
0x140064a3a  mov     eax, [r14+30h]
0x140064a3e  cmp     eax, ecx
0x140064a40  jz      short loc_140064A8A
0x140064a42  mov     edx, [r14+30h]
0x140064a46  mov     r8d, [r14+34h]
0x140064a4a  cmp     edx, r8d
0x140064a4d  jnz     short loc_140064A54
0x140064a4f  mov     edx, r15d
0x140064a52  jmp     short loc_140064A81
0x140064a54  jbe     short loc_140064A5B
0x140064a56  sub     edx, r8d
0x140064a59  jmp     short loc_140064A81
0x140064a5b  mov     rax, [r14+10h]
0x140064a5f  mov     rcx, [r14+18h]
0x140064a63  cmp     [rax+14h], r15b
0x140064a67  jnz     short loc_140064A72
0x140064a69  mov     rax, [rcx+100h]
0x140064a70  jmp     short loc_140064A79
0x140064a72  mov     rax, [rcx+400h]
0x140064a79  mov     ecx, [rax+4]
0x140064a7c  sub     ecx, r8d
0x140064a7f  add     edx, ecx
0x140064a81  mov     rax, [r14+10h]
0x140064a85  cmp     edx, [rax+8]
0x140064a88  ja      short loc_140064AE4
0x140064a8a  mov     rcx, [r14+10h]
0x140064a8e  xor     eax, eax
0x140064a90  mov     edx, 1
0x140064a95  lock cmpxchg [rcx+10h], edx
0x140064a9a  jnz     short loc_140064AE4
0x140064a9c  mov     rax, [r14+10h]
0x140064aa0  mov     rcx, [r14+18h]
0x140064aa4  cmp     [rax+14h], r15b
0x140064aa8  jnz     short loc_140064AC4
0x140064aaa  add     rcx, 1E0h; Event
0x140064ab1  xor     r8d, r8d; Wait
0x140064ab4  xor     edx, edx; Increment
0x140064ab6  call    cs:__imp_KeSetEvent
0x140064abd  nop     dword ptr [rax+rax+00h]
0x140064ac2  jmp     short loc_140064AE4
0x140064ac4  mov     r9, rcx; Context
0x140064ac7  mov     r8d, edx; QueueType
0x140064aca  mov     rcx, [rcx+408h]; IoWorkItem
0x140064ad1  lea     rdx, NvmeControllerRefillShadowQueueRoutine; WorkerRoutine
0x140064ad8  call    cs:__imp_IoQueueWorkItem
0x140064adf  nop     dword ptr [rax+rax+00h]
0x140064ae4  movzx   ecx, bl; NewIrql
0x140064ae7  call    cs:__imp_KeLowerIrql
0x140064aee  nop     dword ptr [rax+rax+00h]
0x140064af3  test    byte ptr [rdi+88h], 2
0x140064afa  jz      short loc_140064B13
0x140064afc  mov     rcx, [r14+18h]
0x140064b00  mov     r8d, r13d
0x140064b03  mov     rdx, rsi
0x140064b06  call    NvmeNamespaceProcessRequest
0x140064b0b  mov     r15d, eax
0x140064b0e  jmp     loc_140065095
0x140064b13  lea     rdx, [rsp+168h+var_98]
0x140064b1b  mov     rcx, rsi
0x140064b1e  call    cs:__imp_IoGetIoAttributionHandle
0x140064b25  nop     dword ptr [rax+rax+00h]
0x140064b2a  test    eax, eax
0x140064b2c  js      short loc_140064B9C
0x140064b2e  mov     rax, [rsi+0B8h]
0x140064b35  xorps   xmm0, xmm0
0x140064b38  mov     rbx, [rsp+168h+var_98]
0x140064b40  movups  [rsp+168h+var_78], xmm0
0x140064b48  mov     dword ptr [rsp+168h+var_78], 1
0x140064b53  movups  xmmword ptr [rsp+168h+QpcTimeStamp], xmm0
0x140064b5b  movzx   ecx, byte ptr [rax]
0x140064b5e  bts     ecx, 9
0x140064b62  mov     dword ptr [rsp+168h+var_78+4], ecx
0x140064b69  lea     rcx, [rsp+168h+QpcTimeStamp+8]; QpcTimeStamp
0x140064b71  call    cs:__imp_KeQueryUnbiasedInterruptTimePrecise
0x140064b78  nop     dword ptr [rax+rax+00h]
0x140064b7d  lea     rdx, [rsp+168h+var_78]
0x140064b85  mov     rcx, rbx
0x140064b88  mov     [rsp+168h+QpcTimeStamp+8], rax
0x140064b90  call    cs:__imp_IoRecordIoAttribution
0x140064b97  nop     dword ptr [rax+rax+00h]
0x140064b9c  mov     rbp, [r14+18h]
0x140064ba0  mov     rdx, r15
0x140064ba3  mov     rdi, [rsi+0B8h]
0x140064baa  xor     r9b, r9b
0x140064bad  mov     [rsp+168h+var_105], dl
0x140064bb1  xor     r10b, r10b
0x140064bb4  mov     [rsp+168h+var_D8], r15w
0x140064bbd  mov     rax, 8765432100000003h
0x140064bc7  mov     r11, [rbp+10h]
0x140064bcb  mov     [rsp+168h+var_90], r15
0x140064bd3  mov     [rsp+168h+var_A8], r15d
0x140064bdb  mov     rbx, [rdi+8]
0x140064bdf  mov     r8, [r11+88h]
0x140064be6  mov     r12d, ebx
0x140064be9  shr     r8, 20h
0x140064bed  and     r8b, 1
0x140064bf1  mov     [rsp+168h+var_C0], rdx
0x140064bf9  mov     [rsp+168h+var_107], r9b
0x140064bfe  mov     [rsp+168h+var_E0], r8
0x140064c06  mov     [rsp+168h+var_108], r10b
0x140064c0b  cmp     rbx, rax
0x140064c0e  jnz     short loc_140064C1E
0x140064c10  mov     rcx, [rdi+18h]
0x140064c14  mov     [rsp+168h+var_E8], rcx
0x140064c1c  jmp     short loc_140064C44
0x140064c1e  mov     rax, 0FEDCBA9000000000h
0x140064c28  mov     rcx, r15
0x140064c2b  mov     [rsp+168h+var_E8], rcx
0x140064c33  cmp     rbx, rax
0x140064c36  jnz     short loc_140064C44
0x140064c38  mov     rdx, [rdi+18h]
0x140064c3c  mov     [rsp+168h+var_C0], rdx
0x140064c44  mov     eax, [rbp+60h]
0x140064c47  sub     eax, 5
0x140064c4a  cmp     eax, 1
0x140064c4d  jbe     loc_14006564D
0x140064c53  movzx   r13d, byte ptr [rdi]
0x140064c57  cmp     r13b, 3
0x140064c5b  mov     [rsp+168h+var_FF], r13b
0x140064c60  setz    [rsp+168h+var_106]
0x140064c65  test    rcx, rcx
0x140064c68  jz      loc_140064E38
0x140064c6e  xor     dl, dl
0x140064c70  mov     dword ptr [rsp+168h+var_D0], r15d
0x140064c78  xor     edi, edi
0x140064c7a  mov     [rsp+168h+var_106], dl
0x140064c7e  test    r8b, r8b
0x140064c81  jnz     short loc_140064C8D
0x140064c83  lock inc word ptr [rcx+78h]
0x140064c88  mov     [rsp+168h+var_108], 1
0x140064c8d  mov     r9d, 4
0x140064c93  mov     rbx, rcx
0x140064c96  nop     word ptr [rax+rax+00000000h]
0x140064ca0  mov     r13, [rbx+60h]
0x140064ca4  mov     eax, 3
0x140064ca9  movzx   r12d, word ptr [rbx+22h]
0x140064cae  lock cmpxchg [rbx+68h], r9d
0x140064cb4  test    r8b, r8b
0x140064cb7  jnz     short loc_140064CD2
0x140064cb9  cmp     eax, 3
0x140064cbc  jz      short loc_140064CE8
0x140064cbe  mov     eax, [rbx+68h]
0x140064cc1  cmp     eax, 1
0x140064cc4  jnz     loc_140064DA0
0x140064cca  inc     di
0x140064ccd  jmp     loc_140064DA0
0x140064cd2  cmp     eax, 3
0x140064cd5  jz      short loc_140064CE8
0x140064cd7  mov     eax, 1
0x140064cdc  lock cmpxchg [rbx+68h], r9d
0x140064ce2  jnz     loc_140064DA0
0x140064ce8  mov     byte ptr [rsp+168h+var_128], dl
0x140064cec  lea     rax, [rsp+168h+var_D8]
0x140064cf4  mov     edx, [rsp+168h+var_104]
0x140064cf8  xor     r9d, r9d
0x140064cfb  mov     [rsp+168h+var_130], rax
0x140064d00  xor     r8d, r8d
0x140064d03  lea     rax, [rsp+168h+var_A8]
0x140064d0b  mov     rcx, rbx
0x140064d0e  mov     qword ptr [rsp+168h+var_138], rax
0x140064d13  lea     rax, [rsp+168h+var_90]
0x140064d1b  mov     qword ptr [rsp+168h+var_140], rax
0x140064d20  lea     rax, [rsp+168h+var_105]
0x140064d25  mov     [rsp+168h+var_148], rax
0x140064d2a  call    NvmeSendSplitIo
0x140064d2f  mov     r15d, eax
0x140064d32  cmp     eax, 103h
0x140064d37  jnz     short loc_140064D6D
0x140064d39  mov     r9d, dword ptr [rsp+168h+var_D0]
0x140064d41  xor     edx, edx
0x140064d43  mov     rcx, [rbp+10h]
0x140064d47  inc     r9w
0x140064d4b  movzx   eax, r9w
0x140064d4f  mov     dword ptr [rsp+168h+var_D0], r9d
0x140064d57  movzx   r8d, byte ptr [rcx+6C2h]
0x140064d5f  div     r8d
0x140064d62  test    edx, edx
0x140064d64  setz    dl
0x140064d67  mov     [rsp+168h+var_106], dl
0x140064d6b  jmp     short loc_140064D8A
0x140064d6d  cmp     eax, 80000011h
0x140064d72  jz      loc_140064E13
0x140064d78  test    r12w, r12w
0x140064d7c  jz      short loc_140064DC5
0x140064d7e  cmp     [rsp+168h+var_105], 0
0x140064d83  jnz     short loc_140064DCA
0x140064d85  movzx   edx, [rsp+168h+var_106]
0x140064d8a  mov     r8, [rsp+168h+var_E0]
0x140064d92  mov     r9d, 4
0x140064d98  mov     rcx, [rsp+168h+var_E8]
0x140064da0  mov     rbx, r13
0x140064da3  test    di, di
0x140064da6  jz      short loc_140064DB7
0x140064da8  test    r13, r13
0x140064dab  jnz     short loc_140064DB7
0x140064dad  xor     eax, eax
0x140064daf  movzx   edi, ax
0x140064db2  jmp     loc_140064C93
0x140064db7  test    rbx, rbx
0x140064dba  jnz     loc_140064CA0
0x140064dc0  mov     r9b, 1
0x140064dc3  jmp     short loc_140064DD0
0x140064dc5  mov     [rsp+168h+var_105], 1
  ... truncated ...
```
