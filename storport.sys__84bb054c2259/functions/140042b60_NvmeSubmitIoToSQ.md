# NvmeSubmitIoToSQ

- ea: `0x140042b60`
- end: `0x140043c95`
- name: `NvmeSubmitIoToSQ`
- size: `4405`
- prototype: ``
- caller_count: `7`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14004cbb0`
- `0x140051870`
- `0x1400604a0`
- `0x1400648b0`
- `0x14012f8c0`
- `0x140131650`
- `0x140133400`

## callees

- `0x140042b60`
- `0x140043ca0`
- `0x140044f10`
- `0x1401344c0`
- `0x14014b400`
- `0x14014b440`

## import_xrefs

- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x140043382`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14004343f`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x140043382`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14004343f`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1400431ce`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1400432a7`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1400431ce`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1400432a7`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140043236`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1400433a1`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140043236`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1400433a1`
- `ntoskrnl!EtwWriteEx` at `0x1400431b4`
- `ntoskrnl!EtwWriteEx` at `0x1400431b4`
- `ntoskrnl!KeFlushIoBuffers` at `0x140043785`
- `ntoskrnl!KeFlushIoBuffers` at `0x140043785`
- `ntoskrnl!KeLowerIrql` at `0x140042cbd`
- `ntoskrnl!KeLowerIrql` at `0x140042d44`
- `ntoskrnl!KeLowerIrql` at `0x140042de0`
- `ntoskrnl!KeLowerIrql` at `0x140043c5a`
- `ntoskrnl!KeLowerIrql` at `0x140042cbd`
- `ntoskrnl!KeLowerIrql` at `0x140042d44`
- `ntoskrnl!KeLowerIrql` at `0x140042de0`
- `ntoskrnl!KeLowerIrql` at `0x140043c5a`
- `ntoskrnl!KfRaiseIrql` at `0x140042c66`
- `ntoskrnl!KfRaiseIrql` at `0x140042c66`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140043bb2`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140043bb2`
- `ntoskrnl!ExQueryDepthSList` at `0x140042df0`
- `ntoskrnl!ExQueryDepthSList` at `0x140042df0`
- `ntoskrnl!KeQueryUnbiasedInterruptTimePrecise` at `0x140043497`
- `ntoskrnl!KeQueryUnbiasedInterruptTimePrecise` at `0x140043497`
- `ntoskrnl!IoRecordIoAttribution` at `0x1400434b5`
- `ntoskrnl!IoRecordIoAttribution` at `0x1400434b5`
- `ntoskrnl!IoGetIoAttributionHandle` at `0x140043460`
- `ntoskrnl!IoGetIoAttributionHandle` at `0x140043460`
- `ntoskrnl!KeQuerySystemTimePrecise` at `0x140043c26`
- `ntoskrnl!KeQuerySystemTimePrecise` at `0x140043c26`
- `HAL!KeQueryPerformanceCounter` at `0x140043431`
- `HAL!KeQueryPerformanceCounter` at `0x140043431`

## string_xrefs

- `0x14004306f`: `Command ID`
- `0x1400430d6`: `Free command ID count`

## pseudocode

```c
__int64 __fastcall NvmeSubmitIoToSQ(
        __int64 a1,
        unsigned __int64 a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5,
        int a6,
        unsigned int a7,
        __int64 a8,
        int a9,
        __int16 a10,
        unsigned __int8 a11,
        unsigned __int16 *a12)
{
  __int64 v13; // rdi
  _DWORD *v15; // rdx
  __int64 v16; // r13
  unsigned __int64 v17; // r15
  unsigned __int64 v18; // rdx
  __int64 v19; // r12
  __int64 v20; // rax
  char v21; // cl
  __int64 v22; // rcx
  __int64 v23; // rsi
  __int64 v25; // rdi
  unsigned int v26; // ebx
  int v27; // esi
  int v28; // edx
  unsigned __int16 Next_high; // ax
  USHORT DepthSList; // ax
  __int64 v31; // r9
  unsigned __int64 v32; // rcx
  bool v33; // zf
  __int64 v34; // r10
  __int64 v35; // rax
  const wchar_t *v36; // rdx
  unsigned int v37; // eax
  __int64 v38; // rcx
  const wchar_t *v39; // r8
  __int64 v40; // rcx
  __int64 v41; // rax
  int v42; // eax
  const int *v43; // r8
  const int *v44; // rdx
  __int64 v45; // rax
  int v46; // eax
  const int *v47; // rax
  __int64 v48; // rax
  __int64 v49; // rax
  __int64 v50; // r9
  PSLIST_ENTRY v51; // r9
  int v52; // r8d
  __int64 v53; // r13
  unsigned int v54; // ecx
  unsigned int v55; // eax
  unsigned int v56; // ebx
  unsigned int v57; // r14d
  unsigned __int64 v58; // r14
  __int64 v59; // rax
  _OWORD *v60; // rdx
  __int64 v61; // rbx
  __int64 v62; // rcx
  __int16 v63; // ax
  __int64 v64; // rbx
  unsigned int v65; // ecx
  unsigned int v66; // edx
  LARGE_INTEGER PerformanceCounter; // rax
  unsigned __int64 v68; // r14
  unsigned __int8 *v69; // rax
  __int64 v70; // rbx
  ULONG64 UnbiasedInterruptTimePrecise; // rax
  __int64 v72; // rax
  unsigned __int8 v73; // r11
  __int64 v74; // rcx
  __int64 v75; // r10
  unsigned int v76; // edx
  __int64 v77; // r8
  int v78; // r9d
  char v79; // bl
  __int64 v80; // rdx
  __int64 v81; // r10
  __int64 v82; // r11
  __m128i *v83; // r9
  __m128i v84; // xmm0
  __int64 v85; // rax
  __int64 v86; // rax
  __int64 v87; // rcx
  __int64 v88; // r13
  _QWORD *v89; // rcx
  __int64 v90; // rax
  void (__fastcall *v91)(_QWORD, _QWORD, _QWORD); // rax
  unsigned int v92; // r11d
  __int64 v93; // r8
  unsigned int *v94; // rcx
  _QWORD *v95; // r14
  unsigned int v96; // r12d
  _QWORD *v97; // r13
  unsigned int v98; // ebx
  _QWORD *v99; // r8
  _QWORD *v100; // r15
  unsigned int v101; // edi
  unsigned int *v102; // rsi
  __int64 v103; // r10
  __int64 v104; // r9
  _QWORD *v105; // rdx
  int v106; // ecx
  unsigned int v107; // r9d
  __int64 v108; // rcx
  __int64 v109; // r8
  __int64 v110; // rcx
  unsigned __int64 v111; // r10
  __int64 v112; // rdx
  char v113; // r11
  __int64 v114; // rax
  unsigned __int64 v115; // r9
  __int64 v116; // rcx
  int v117; // edx
  __int16 v118; // cx
  __int64 v119; // rax
  __int64 v120; // rbx
  __int64 v121; // rdx
  unsigned int v122; // ecx
  __int64 v123; // r8
  __int64 v124; // rdx
  __int64 v125; // rsi
  signed __int32 v126; // ecx
  _QWORD *v127; // rcx
  _BYTE **v128; // rcx
  signed __int32 v129[8]; // [rsp+0h] [rbp-100h] BYREF
  KIRQL v130; // [rsp+40h] [rbp-C0h]
  unsigned __int16 v131; // [rsp+42h] [rbp-BEh]
  char v132; // [rsp+44h] [rbp-BCh]
  char v133; // [rsp+45h] [rbp-BBh]
  unsigned __int16 v134; // [rsp+46h] [rbp-BAh]
  int v135; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v136; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v137; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v138; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int64 v139; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int64 v140; // [rsp+70h] [rbp-90h] BYREF
  __int64 v141; // [rsp+78h] [rbp-88h] BYREF
  __int64 v142; // [rsp+80h] [rbp-80h] BYREF
  __int64 v143; // [rsp+88h] [rbp-78h] BYREF
  __int64 v144; // [rsp+90h] [rbp-70h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+98h] [rbp-68h] BYREF
  __int128 v146; // [rsp+A8h] [rbp-58h] BYREF
  GUID ActivityId; // [rsp+B8h] [rbp-48h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v149; // [rsp+E0h] [rbp-20h]
  __int64 v150; // [rsp+E8h] [rbp-18h]
  const wchar_t *v151; // [rsp+F0h] [rbp-10h]
  int v152; // [rsp+F8h] [rbp-8h]
  int v153; // [rsp+FCh] [rbp-4h]
  const int *v154; // [rsp+100h] [rbp+0h]
  int v155; // [rsp+108h] [rbp+8h]
  int v156; // [rsp+10Ch] [rbp+Ch]
  __int64 v157; // [rsp+110h] [rbp+10h]
  __int64 v158; // [rsp+118h] [rbp+18h]
  __int64 v159; // [rsp+120h] [rbp+20h]
  __int64 v160; // [rsp+128h] [rbp+28h]
  const int *v161; // [rsp+130h] [rbp+30h]
  int v162; // [rsp+138h] [rbp+38h]
  int v163; // [rsp+13Ch] [rbp+3Ch]
  __int64 v164; // [rsp+140h] [rbp+40h]
  int v165; // [rsp+148h] [rbp+48h]
  int v166; // [rsp+14Ch] [rbp+4Ch]
  __int64 v167; // [rsp+150h] [rbp+50h]
  int v168; // [rsp+158h] [rbp+58h]
  int v169; // [rsp+15Ch] [rbp+5Ch]
  const wchar_t *v170; // [rsp+160h] [rbp+60h]
  __int64 v171; // [rsp+168h] [rbp+68h]
  const wchar_t *v172; // [rsp+170h] [rbp+70h]
  __int64 v173; // [rsp+178h] [rbp+78h]
  __int64 *v174; // [rsp+180h] [rbp+80h]
  __int64 v175; // [rsp+188h] [rbp+88h]
  const wchar_t *v176; // [rsp+190h] [rbp+90h]
  __int64 v177; // [rsp+198h] [rbp+98h]
  unsigned __int64 *v178; // [rsp+1A0h] [rbp+A0h]
  __int64 v179; // [rsp+1A8h] [rbp+A8h]
  const wchar_t *v180; // [rsp+1B0h] [rbp+B0h]
  __int64 v181; // [rsp+1B8h] [rbp+B8h]
  __int64 *v182; // [rsp+1C0h] [rbp+C0h]
  __int64 v183; // [rsp+1C8h] [rbp+C8h]
  const wchar_t *v184; // [rsp+1D0h] [rbp+D0h]
  __int64 v185; // [rsp+1D8h] [rbp+D8h]
  __int64 *v186; // [rsp+1E0h] [rbp+E0h]
  __int64 v187; // [rsp+1E8h] [rbp+E8h]
  const wchar_t *v188; // [rsp+1F0h] [rbp+F0h]
  __int64 v189; // [rsp+1F8h] [rbp+F8h]
  unsigned __int64 *v190; // [rsp+200h] [rbp+100h]
  __int64 v191; // [rsp+208h] [rbp+108h]
  const wchar_t *v192; // [rsp+210h] [rbp+110h]
  __int64 v193; // [rsp+218h] [rbp+118h]
  __int64 *v194; // [rsp+220h] [rbp+120h]
  __int64 v195; // [rsp+228h] [rbp+128h]
  const wchar_t *v196; // [rsp+230h] [rbp+130h]
  __int64 v197; // [rsp+238h] [rbp+138h]
  __int64 *v198; // [rsp+240h] [rbp+140h]
  __int64 v199; // [rsp+248h] [rbp+148h]
  const wchar_t *v200; // [rsp+250h] [rbp+150h]
  __int64 v201; // [rsp+258h] [rbp+158h]
  __int64 *v202; // [rsp+260h] [rbp+160h]
  __int64 v203; // [rsp+268h] [rbp+168h]

  v136 = a1;
  v13 = a3;
  v143 = a3;
  v139 = a2;
  v15 = *(_DWORD **)(a2 + 8);
  v144 = 0;
  v137 = a4;
  v16 = (unsigned int)v15[11];
  v17 = ((v15[11] & 0xFFF) + (unsigned __int64)a7 + 4095) >> 12;
  v140 = v17;
  if ( !(_DWORD)v17 )
    return 3221225488LL;
  v18 = ((((_WORD)v16 + (unsigned __int16)v15[8]) & 0xFFF) + (unsigned __int64)(unsigned int)v15[10] + 4095) >> 12;
  if ( (unsigned int)v16 < 0x1000 )
  {
    v19 = 0;
  }
  else
  {
    v19 = (unsigned int)v16 >> 12;
    v16 = (unsigned int)v16 - ((unsigned int)v16 >> 12 << 12);
  }
  v141 = v16;
  if ( (int)v19 + (int)v17 > (unsigned int)v18 )
    return 3221225488LL;
  v20 = *(_QWORD *)(a1 + 16);
  v21 = *(_BYTE *)(v20 + 1728);
  LOBYTE(v20) = *(_BYTE *)(v20 + 1729);
  v133 = v21;
  v142 = *(_QWORD *)(a2 + 184);
  v132 = v20;
  v130 = KfRaiseIrql(2u);
  _InterlockedIncrement((volatile signed __int32 *)(v13 + 128));
  v22 = *(_QWORD *)(v13 + 88);
  v23 = v13 + 88;
  v138 = v13 + 88;
  if ( *(_BYTE *)(v22 + 1252) )
  {
    _InterlockedDecrement((volatile signed __int32 *)(v13 + 128));
    if ( v137 )
      FreeNVMePrpListBufferEntry(*(_QWORD *)(a1 + 16), a5);
    KeLowerIrql(v130);
    return 3221225486LL;
  }
  if ( *(_DWORD *)(*(_QWORD *)v23 + 948LL) )
  {
    _InterlockedDecrement((volatile signed __int32 *)(v13 + 128));
LABEL_12:
    v25 = v136;
    NvmeNamespaceQueueIo(v136, v139, a5);
    if ( v137 )
      FreeNVMePrpListBufferEntry(*(_QWORD *)(v25 + 16), a5);
    KeLowerIrql(v130);
    return 2147483665LL;
  }
  v26 = *(_DWORD *)(v13 + 124);
  if ( !a12 )
  {
    v51 = ExpInterlockedPopEntrySList((PSLIST_HEADER)(v13 + 64));
    if ( !v51 )
    {
LABEL_60:
      _InterlockedDecrement((volatile signed __int32 *)(v13 + 128));
      v53 = *(_QWORD *)v23;
      v54 = *(unsigned __int16 *)(*(_QWORD *)v23 + 22LL);
      if ( v54 != 1 )
      {
        v55 = *(unsigned __int16 *)(v13 + 136);
        v135 = v55 - 1;
        v56 = v55 % v54;
        if ( v55 % v54 < v54 )
        {
          do
          {
            v13 = *(_QWORD *)(*(_QWORD *)v23 + 728LL) + 192LL * v56;
            v143 = v13;
            _InterlockedIncrement((volatile signed __int32 *)(v13 + 128));
            v57 = *(_DWORD *)(v13 + 124);
            v51 = ExpInterlockedPopEntrySList((PSLIST_HEADER)(v13 + 64));
            if ( v51 )
            {
              _InterlockedOr(v129, 0);
              while ( 1 )
              {
                v52 = 0;
                v134 = *(_WORD *)(v13 + 142);
                v27 = v134;
                if ( (unsigned __int16)(v134 + 1) < v57 )
                  LOWORD(v52) = v134 + 1;
                if ( (_WORD)v52 == *(_WORD *)(v13 + 140) )
                  break;
                if ( _InterlockedCompareExchange16((volatile signed __int16 *)(v13 + 142), v52, v134) == v27 )
                {
                  LODWORD(v17) = v140;
                  LODWORD(v16) = v141;
                  goto LABEL_69;
                }
              }
              ExpInterlockedPushEntrySList((PSLIST_HEADER)(v13 + 64), v51);
              v23 = v138;
            }
            v65 = *(unsigned __int16 *)(v53 + 22);
            _InterlockedDecrement((volatile signed __int32 *)(v13 + 128));
            v66 = (v56 + 1) % v65;
            v56 = v66;
          }
          while ( v66 != v135 && v66 < *(unsigned __int16 *)(v53 + 22) );
        }
      }
      goto LABEL_12;
    }
    _InterlockedOr(v129, 0);
    do
    {
      v52 = 0;
      v134 = *(_WORD *)(v13 + 142);
      v27 = v134;
      if ( (unsigned __int16)(v134 + 1) < v26 )
        LOWORD(v52) = v134 + 1;
      if ( (_WORD)v52 == *(_WORD *)(v13 + 140) )
      {
        ExpInterlockedPushEntrySList((PSLIST_HEADER)(v13 + 64), v51);
        v23 = v138;
        goto LABEL_60;
      }
    }
    while ( _InterlockedCompareExchange16((volatile signed __int16 *)(v13 + 142), v52, v134) != v27 );
LABEL_69:
    Next_high = HIWORD(v51[3].Next);
    v135 = v52;
LABEL_70:
    v58 = (unsigned __int64)Next_high << 7;
    v131 = Next_high;
    v59 = *(_QWORD *)(v13 + 32);
    *(_QWORD *)&ActivityId.Data1 = v58;
    if ( (*(_BYTE *)(v59 + v58 + 60) & 4) != 0 )
    {
      v60 = *(_OWORD **)(*(_QWORD *)(v13 + 24) + 16LL * (unsigned __int16)v27);
      *v60 = 0;
      v60[1] = 0;
      v60[2] = 0;
      v60[3] = 0;
    }
    v61 = v136;
    v62 = *(_QWORD *)(v13 + 32);
    v63 = *(_WORD *)(v136 + 668);
    if ( v63 )
    {
      *(_WORD *)(v62 + v58 + 58) = v63;
      v64 = *(_QWORD *)(v13 + 32);
      *(_QWORD *)(v64 + v58 + 64) = KeQueryUnbiasedInterruptTime();
      v61 = v136;
    }
    else
    {
      *(_WORD *)(v62 + v58 + 58) = *(_WORD *)(v136 + 424);
      *(_QWORD *)(*(_QWORD *)(v13 + 32) + v58 + 64) = **(_QWORD **)(*(_QWORD *)(*(_QWORD *)(v13 + 88) + 1312LL) + 40LL);
    }
    *(_DWORD *)(*(_QWORD *)(v13 + 32) + v58 + 88) = *(_DWORD *)(v61 + 56);
    if ( (*(_DWORD *)(*(_QWORD *)(v61 + 624) + 4LL) & 1) != 0 )
    {
      if ( UseQPCTime )
        PerformanceCounter = KeQueryPerformanceCounter(0);
      else
        PerformanceCounter.QuadPart = KeQueryUnbiasedInterruptTime();
      *(LARGE_INTEGER *)(*(_QWORD *)(v13 + 32) + v58 + 72) = PerformanceCounter;
    }
    v68 = v139;
    if ( (int)IoGetIoAttributionHandle(v139, &v144) >= 0 )
    {
      v69 = *(unsigned __int8 **)(v68 + 184);
      v70 = v144;
      EventDescriptor = 0;
      *(_DWORD *)&EventDescriptor.Id = 1;
      v146 = 0;
      *(_DWORD *)&EventDescriptor.Level = *v69;
      UnbiasedInterruptTimePrecise = KeQueryUnbiasedInterruptTimePrecise((PULONG64)&v146 + 1);
      *(_DWORD *)&EventDescriptor.Level |= 0x100u;
      *((_QWORD *)&v146 + 1) = UnbiasedInterruptTimePrecise;
      IoRecordIoAttribution(v70, &EventDescriptor);
      v61 = v136;
    }
    v72 = *(_QWORD *)(v13 + 24);
    v73 = a11;
    *(_QWORD *)&EventDescriptor.Id = 16LL * (unsigned __int16)v27;
    v74 = *(_QWORD *)(*(_QWORD *)&EventDescriptor.Id + v72);
    v75 = v74;
    v138 = v74;
    *(_WORD *)(v74 + 2) = v131;
    if ( a11 )
    {
      v76 = *(_DWORD *)(v61 + 64);
      v77 = 0;
      v78 = *(_DWORD *)(v61 + 56);
      *(_BYTE *)v74 = 2;
    }
    else
    {
      if ( FUAEnabled && (*(_BYTE *)(v142 + 2) & 4) != 0 )
        v77 = 0x40000000;
      else
        v77 = 0;
      v78 = *(_DWORD *)(v61 + 56);
      v76 = *(_DWORD *)(v61 + 64);
      *(_BYTE *)v74 = 1;
      *(_WORD *)(v74 + 54) = 0;
      *(_DWORD *)(v74 + 48) &= 0xFF0FFFFF;
    }
    *(_DWORD *)v74 &= 0xFFFFFCFF;
    v79 = 0;
    *(_DWORD *)(v74 + 4) = v78;
    *(_QWORD *)(v74 + 16) = 0;
    *(_BYTE *)(v74 + 52) = 0;
    *(_QWORD *)(v74 + 40) = a8 / v76;
    *(_QWORD *)(v74 + 56) = 0;
    *(_WORD *)(v74 + 48) = a10 - 1;
    *(_DWORD *)(v74 + 48) = v77 & 0x7FFFFFFF | *(_DWORD *)(v74 + 48) & 0x3FFFFFF;
    if ( v132 )
    {
      if ( _bittest64((const signed __int64 *)(*(_QWORD *)(v136 + 16) + 136LL), 0x20u) )
      {
        v80 = v138;
        v81 = *(_QWORD *)(v68 + 8) + 48LL;
        *(_QWORD *)(v138 + 24) = (unsigned int)v16 + (*(_QWORD *)(v81 + 8 * v19) << 12);
        if ( (_DWORD)v17 == 1 )
        {
LABEL_109:
          v88 = v136;
          if ( *(_QWORD *)(v68 + 8) )
          {
            v89 = (_QWORD *)(*(_QWORD *)(*(_QWORD *)(v136 + 16) + 128LL) + 1160LL);
            if ( *(_QWORD *)(*(_QWORD *)(v136 + 16) + 128LL) != -1160 )
            {
              if ( *v89 )
              {
                v90 = *(_QWORD *)(*v89 + 8LL);
                if ( v90 )
                {
                  if ( *(int *)(*(_QWORD *)(*(_QWORD *)(v136 + 16) + 128LL) + 1188LL) >= 3
                    && (v91 = *(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(v90 + 240)) != 0 )
                  {
                    v91(*v89, *(_QWORD *)(v68 + 8), v73);
                  }
                  else
                  {
                    LOBYTE(v77) = 1;
                    KeFlushIoBuffers(*(_QWORD *)(v68 + 8), v73, v77);
                  }
                }
              }
            }
          }
          goto LABEL_151;
        }
        if ( (_DWORD)v17 == 2 )
        {
          *(_QWORD *)(v80 + 32) = *(_QWORD *)(v81 + 8LL * (unsigned int)(v19 + 1)) << 12;
          goto LABEL_109;
        }
        v82 = (unsigned int)(v17 - 1);
        if ( (unsigned int)v17 > 1 )
        {
          LODWORD(v77) = 1;
          v83 = *(__m128i **)(v137 + 16);
          if ( (unsigned int)v82 < 8 )
            goto LABEL_105;
          if ( (unsigned __int64)&v83->m128i_u64[1] <= v81 + 8 * (unsigned __int64)(unsigned int)(v82 + v19)
            && (unsigned __int64)v83 + 8 * v82 >= v81 + 8 * (unsigned __int64)(unsigned int)(v19 + 1) )
          {
            goto LABEL_104;
          }
          do
          {
            *v83 = _mm_slli_epi64(_mm_loadu_si128((const __m128i *)(v81 + 8LL * (unsigned int)(v77 + v19))), 0xCu);
            v83[1] = _mm_slli_epi64(_mm_loadu_si128((const __m128i *)(v81 + 8LL * (unsigned int)(v77 + v19 + 2))), 0xCu);
            v84 = _mm_loadu_si128((const __m128i *)(v81 + 8LL * (unsigned int)(v77 + v19 + 4)));
            v85 = (unsigned int)(v77 + v19 + 6);
            v77 = (unsigned int)(v77 + 8);
            v83[2] = _mm_slli_epi64(v84, 0xCu);
            v83[3] = _mm_slli_epi64(_mm_loadu_si128((const __m128i *)(v81 + 8 * v85)), 0xCu);
            v83 += 4;
          }
          while ( (unsigned int)v77 < (unsigned int)v17 - (((_BYTE)v17 - 1) & 7) );
          LODWORD(v17) = v140;
          if ( (unsigned int)v77 < (unsigned int)v140 )
          {
LABEL_104:
            v80 = v138;
            do
            {
LABEL_105:
              v86 = (unsigned int)(v77 + v19);
              v77 = (unsigned int)(v77 + 1);
              v83 = (__m128i *)((char *)v83 + 8);
              v83[-1].m128i_i64[1] = *(_QWORD *)(v81 + 8 * v86) << 12;
            }
            while ( (unsigned int)v77 < (unsigned int)v17 );
            goto LABEL_108;
          }
          v80 = v138;
        }
LABEL_108:
        v87 = v137;
        v68 = v139;
        *(_QWORD *)(v80 + 32) = *(_QWORD *)(v137 + 24);
        *(_DWORD *)(v87 + 32) = v82;
        v73 = a11;
        goto LABEL_109;
      }
      v92 = 0;
      v93 = v137;
      v94 = *(unsigned int **)(*(_QWORD *)(v142 + 24) + 24LL);
      if ( v137 )
      {
        v95 = *(_QWORD **)(v137 + 16);
        v96 = *(unsigned __int16 *)(v137 + 36) + 1;
        v140 = *(_QWORD *)(v137 + 24);
      }
      else
      {
        v140 = 0;
        v95 = 0;
        v96 = 2;
      }
      if ( *v94 )
      {
        v97 = (_QWORD *)(v75 + 24);
        v98 = 0;
        v99 = (_QWORD *)(v75 + 24);
        v100 = (_QWORD *)(v75 + 32);
        v101 = 0;
        v102 = v94;
        do
        {
          v103 = *(_QWORD *)&v102[6 * v101 + 4];
          v104 = v102[6 * v101 + 6];
          if ( v104 + v103 % 4096 > 4096 )
          {
            if ( (_DWORD)v104 )
            {
              v105 = v100;
              do
              {
                *v99 = v103;
                v106 = v103 & 0xFFF;
                v107 = v106 + v104;
                v98 += 4096 - v106;
                if ( v107 <= 0x1000 )
                  break;
                if ( v99 == v97 )
                {
                  v99 = v105;
                }
                else if ( v99 == v105 )
                {
                  if ( v95 )
                    v99 = v95 + 1;
                }
                else
                {
                  ++v99;
                }
                if ( ++v92 >= v96 || v98 >= a7 )
                  goto LABEL_145;
                v105 = v100;
                v103 += (unsigned int)(4096 - v106);
                LODWORD(v104) = v107 - 4096;
              }
              while ( (_DWORD)v104 );
            }
          }
          else
          {
            *v99 = v103;
            v98 += v102[6 * v101 + 6];
          }
          if ( v99 == v97 )
          {
            v99 = v100;
          }
          else if ( v99 == v100 )
          {
            if ( v95 )
              v99 = v95 + 1;
          }
          else
          {
            ++v99;
          }
          if ( ++v92 >= v96 )
            break;
          if ( v98 >= a7 )
            break;
          ++v101;
        }
        while ( v101 < *v102 );
LABEL_145:
        v13 = v143;
        LOWORD(v27) = v134;
        v93 = v137;
        if ( v92 > 2 )
        {
          v108 = v138;
          *v95 = *(_QWORD *)(v138 + 32);
          *(_QWORD *)(v108 + 32) = v140;
        }
      }
      if ( v93 )
        *(_DWORD *)(v93 + 32) = v92 - 1;
      v79 = 0x80;
    }
    v88 = v136;
LABEL_151:
    v109 = *(_QWORD *)&ActivityId.Data1;
    v110 = v137;
    v111 = v139;
    v112 = *(_QWORD *)&EventDescriptor.Id;
    v113 = v133;
    *(_BYTE *)(*(_QWORD *)&ActivityId.Data1 + *(_QWORD *)(v13 + 32) + 60LL) = v79;
    *(_BYTE *)(v109 + *(_QWORD *)(v13 + 32) + 61) = 0;
    *(_QWORD *)(v109 + *(_QWORD *)(v13 + 32) + 24) = v111;
    *(_WORD *)(v109 + *(_QWORD *)(v13 + 32) + 56) = v27;
    *(_QWORD *)(v109 + *(_QWORD *)(v13 + 32) + 16) = v110;
    *(_WORD *)(v109 + *(_QWORD *)(v13 + 32) + 52) = a5;
    *(_DWORD *)(v109 + *(_QWORD *)(v13 + 32) + 48) = a7;
    LOWORD(v110) = v131;
    *(_QWORD *)(v109 + *(_QWORD *)(v13 + 32) + 40) = 0;
    *(_QWORD *)(v109 + *(_QWORD *)(v13 + 32) + 32) = 0;
    *(_QWORD *)(v109 + *(_QWORD *)(v13 + 32) + 40) = 0;
    *(_WORD *)(v112 + *(_QWORD *)(v13 + 24) + 8) = v110;
    if ( v113 == 1 )
    {
      v114 = *(_QWORD *)(v13 + 56);
      if ( v114 )
      {
        v115 = (unsigned __int64)(unsigned __int16)v27 << 6;
        *(_OWORD *)(v115 + v114) = 0;
        *(_OWORD *)(v115 + v114 + 16) = 0;
        *(_OWORD *)(v115 + v114 + 32) = 0;
        *(_OWORD *)(v115 + v114 + 48) = 0;
        *(_DWORD *)(v115 + *(_QWORD *)(v13 + 56)) = 1;
        *(_DWORD *)(v115 + *(_QWORD *)(v13 + 56) + 8) = *(unsigned __int16 *)(v13 + 136);
        *(_DWORD *)(v115 + *(_QWORD *)(v13 + 56) + 12) = (unsigned __int16)v27;
        *(_QWORD *)(v115 + *(_QWORD *)(v13 + 56) + 40) |= 1uLL;
        *(_QWORD *)(*(_QWORD *)(v13 + 56) + v115 + 40) = *(_QWORD *)(*(_QWORD *)(v13 + 56) + v115 + 40)
                                                       & 0xFFFFFFFFFFFFFFFDuLL
                                                       | ((*(_DWORD *)(v111 + 16) & 0x42) != 0 ? 2 : 0);
        v116 = *(_QWORD *)(v13 + 56);
        if ( *(char *)(v109 + *(_QWORD *)(v13 + 32) + 60) >= 0 )
          *(_QWORD *)(v115 + v116 + 32) = *(_QWORD *)(v111 + 8);
        else
          *(_QWORD *)(v115 + v116 + 24) = *(_QWORD *)(*(_QWORD *)(v142 + 24) + 24LL);
      }
    }
    *(_BYTE *)(*(_QWORD *)(v111 + 184) + 3LL) |= 1u;
    _InterlockedOr(v129, 0);
    v117 = 0;
    *(_BYTE *)(*(_QWORD *)(v13 + 32) + v109 + 60) |= 1u;
    _InterlockedDecrement((volatile signed __int32 *)(v13 + 128));
    if ( (unsigned __int16)(v27 + 1) != *(_DWORD *)(v13 + 124) )
      v117 = (unsigned __int16)(v27 + 1);
    _InterlockedOr(v129, 0);
    v118 = v135;
    if ( *(_WORD *)(v13 + 142) == (_WORD)v135 )
    {
      while ( _InterlockedCompareExchange((volatile signed __int32 *)(v13 + 132), 1, 0) )
      {
        if ( *(_WORD *)(v13 + 142) != v118 )
          goto LABEL_179;
      }
      while ( *(_DWORD *)(v13 + 128) )
        _InterlockedOr(v129, 0);
      if ( *(_WORD *)(v13 + 142) == v118 )
      {
        if ( v113 == 1 )
        {
          v119 = *(_QWORD *)(v88 + 16);
          v135 = v117;
          (*(void (__fastcall **)(__int64, _QWORD, __int64, _QWORD, int *))(*(_QWORD *)(v119 + 128) + 536LL))(
            *(_QWORD *)(v119 + 1648) + 64LL,
            *(unsigned int *)(v13 + 16),
            4,
            0,
            &v135);
          v111 = v139;
        }
        else
        {
          **(_DWORD **)(v13 + 16) = v117;
          _InterlockedOr(v129, 0);
        }
      }
      _InterlockedOr(v129, 0);
      _InterlockedExchange((volatile __int32 *)(v13 + 132), 0);
      v120 = *(_QWORD *)(v88 + 16);
      if ( (*(_BYTE *)(v120 + 1384) & 1) != 0 )
      {
        EventDescriptor.Id = *(_WORD *)(v13 + 136);
        *(_WORD *)&EventDescriptor.Version = *(_WORD *)(v13 + 138);
        EventDescriptor.Keyword = v111;
        *(_DWORD *)&EventDescriptor.Level = *(_DWORD *)v138;
        if ( v120 )
        {
          if ( *(_DWORD *)v120 == 1314276178 )
          {
            v121 = *(_QWORD *)(*(_QWORD *)(v120 + 1392) + 8LL * KeGetCurrentProcessorNumberEx(0));
            v122 = *(_DWORD *)(v121 + 12);
            _InterlockedOr(v129, 0);
            if ( v122 )
            {
              v123 = v121 + 64;
              if ( v121 != -64 )
              {
                v124 = _InterlockedIncrement((volatile signed __int32 *)v121) % v122;
                v125 = v123 + ((unsigned __int64)(unsigned int)v124 << 6);
                v126 = v124;
                if ( (*(_DWORD *)(v120 + 1360) & 1) != 0 )
                  v126 = _InterlockedIncrement((volatile signed __int32 *)(v120 + 1408));
                *(_DWORD *)(v125 + 4) = v126;
                v127 = (_QWORD *)(v125 + 8);
                *(_DWORD *)v125 = 0x10000;
                if ( (*(_DWORD *)(v120 + 1360) & 2) != 0 )
                  KeQuerySystemTimePrecise(v127, v124);
                else
                  *v127 = MEMORY[0xFFFFF78000000014];
                *(EVENT_DESCRIPTOR *)(v125 + 16) = EventDescriptor;
                *(_OWORD *)(v125 + 32) = 0;
              }
            }
          }
        }
      }
    }
LABEL_179:
    KeLowerIrql(v130);
    v128 = *(_BYTE ***)(v88 + 16);
    if ( *v128[217] )
      NvmeStartIoPolling(v128);
    return 259;
  }
  while ( 1 )
  {
    v28 = 0;
    v134 = *(_WORD *)(v13 + 142);
    LOWORD(v27) = v134;
    if ( (unsigned __int16)(v134 + 1) < v26 )
      LOWORD(v28) = v134 + 1;
    v135 = v28;
    if ( (_WORD)v28 == *(_WORD *)(v13 + 140) )
      break;
    if ( _InterlockedCompareExchange16((volatile signed __int16 *)(v13 + 142), v28, v134) == v134 )
    {
      Next_high = *a12;
      goto LABEL_70;
    }
  }
  _InterlockedDecrement((volatile signed __int32 *)(v13 + 128));
  if ( v137 )
    FreeNVMePrpListBufferEntry(*(_QWORD *)(v136 + 16), a5);
  KeLowerIrql(v130);
  DepthSList = ExQueryDepthSList((PSLIST_HEADER)(v13 + 64));
  v31 = *(_QWORD *)(v136 + 16);
  v32 = 0x800000000002000LL;
  v136 = DepthSList;
  ActivityId = 0;
  v137 = *(unsigned int *)(v31 + 8);
  v138 = *(unsigned __int16 *)(v31 + 26);
  v139 = *(unsigned __int16 *)(v31 + 22);
  v142 = *a12;
  v141 = *(unsigned __int16 *)(v13 + 142);
  v140 = *(unsigned __int16 *)(v13 + 140);
  v143 = *(unsigned __int16 *)(v13 + 136);
  v33 = (*(_BYTE *)(v31 + 136) & 2) == 0;
  v34 = *(_QWORD *)(v31 + 128);
  *(_QWORD *)&EventDescriptor.Id = EventNVMeControllerError;
  if ( !v33 )
    v32 = 0x80000000000A000LL;
  EventDescriptor.Keyword = v32;
  v35 = *(_QWORD *)(v34 + 16);
  v36 = *(const wchar_t **)(v35 + 48);
  if ( v36 )
  {
    v37 = *(unsigned __int16 *)(v35 + 40);
    if ( (_WORD)v37 )
    {
      LODWORD(v38) = v37 >> 1;
      if ( v37 >> 1 )
      {
        while ( 1 )
        {
          v38 = (unsigned int)(v38 - 1);
          v39 = &v36[v38];
          if ( *v39 == 92 )
            break;
          if ( !(_DWORD)v38 )
            goto LABEL_33;
        }
        if ( v39 )
          v36 = v39 + 1;
      }
    }
  }
LABEL_33:
  *(_QWORD *)&UserData.Size = 4;
  UserData.Ptr = v34 + 56;
  v150 = 16;
  v149 = v34 + 1048;
  v40 = -1;
  if ( v36 )
  {
    v41 = -1;
    do
      v33 = v36[++v41] == 0;
    while ( !v33 );
    v42 = 2 * v41 + 2;
  }
  else
  {
    v42 = 10;
    v36 = L"NULL";
  }
  v43 = *(const int **)(v31 + 792);
  v151 = v36;
  v44 = &dword_140157D94;
  v152 = v42;
  v153 = 0;
  if ( v43 )
  {
    v45 = -1;
    do
      ++v45;
    while ( *((_BYTE *)v43 + v45) );
    v46 = v45 + 1;
  }
  else
  {
    v46 = 1;
    v43 = &dword_140157D94;
  }
  v155 = v46;
  v157 = v31 + 4;
  v159 = v31 + 744;
  v47 = *(const int **)(v31 + 752);
  v154 = v43;
  v156 = 0;
  if ( v47 )
    v44 = v47;
  v158 = 2;
  v48 = -1;
  v160 = 1;
  do
    ++v48;
  while ( *((_BYTE *)v44 + v48) );
  v161 = v44;
  v162 = v48 + 1;
  v164 = v31 + 800;
  v49 = -1;
  v163 = 0;
  do
    ++v49;
  while ( *(_BYTE *)(v31 + 800 + v49) );
  v166 = 0;
  v50 = v31 + 841;
  v165 = v49 + 1;
  v167 = v50;
  do
    v33 = *(_BYTE *)(v50 + v40++ + 1) == 0;
  while ( !v33 );
  v169 = 0;
  v168 = v40 + 1;
  v171 = 48;
  v170 = L"Failed to get free slot";
  v173 = 12;
  v172 = L"SQ ID";
  v174 = &v143;
  v176 = L"SQ head";
  v178 = &v140;
  v180 = L"SQ tail";
  v182 = &v141;
  v184 = L"Command ID";
  v186 = &v142;
  v188 = L"IO SQ count";
  v190 = &v139;
  v192 = L"IO CQ count";
  v194 = &v138;
  v196 = L"Queue depth";
  v198 = &v137;
  v200 = L"Free command ID count";
  v202 = &v136;
  v175 = 8;
  v177 = 16;
  v179 = 8;
  v181 = 16;
  v183 = 8;
  v185 = 22;
  v187 = 8;
  v189 = 24;
  v191 = 8;
  v193 = 24;
  v195 = 8;
  v197 = 24;
  v199 = 8;
  v201 = 44;
  v203 = 8;
  EtwWriteEx(StorPortEventProvider_Context, &EventDescriptor, 0, 1u, &ActivityId, 0, 0x1Au, &UserData);
  return 3221225701LL;
}

```

## disassembly

```asm
0x140042b60  push    rbp
0x140042b62  push    rbx
0x140042b63  push    rdi
0x140042b64  push    r12
0x140042b66  push    r13
0x140042b68  push    r14
0x140042b6a  push    r15
0x140042b6c  lea     rbp, [rsp-1F0h]
0x140042b74  sub     rsp, 2F0h
0x140042b7b  mov     rax, cs:__security_cookie
0x140042b82  xor     rax, rsp
0x140042b85  mov     [rbp+220h+var_60], rax
0x140042b8c  mov     r15d, [rbp+220h+arg_30]
0x140042b93  mov     rbx, rcx
0x140042b96  mov     r14, [rbp+220h+arg_58]
0x140042b9d  add     r15, 0FFFh
0x140042ba4  mov     [rsp+320h+var_2D0], rcx
0x140042ba9  mov     rdi, r8
0x140042bac  mov     [rbp+220h+var_298], r8
0x140042bb0  mov     r8, rdx
0x140042bb3  mov     [rsp+320h+var_2B8], rdx
0x140042bb8  mov     rdx, [rdx+8]
0x140042bbc  mov     [rbp+220h+var_290], 0
0x140042bc4  mov     [rsp+320h+var_2C8], r9
0x140042bc9  mov     r13d, [rdx+2Ch]
0x140042bcd  mov     ecx, r13d
0x140042bd0  and     ecx, 0FFFh
0x140042bd6  add     r15, rcx
0x140042bd9  shr     r15, 0Ch
0x140042bdd  mov     [rsp+320h+var_2B0], r15
0x140042be2  test    r15d, r15d
0x140042be5  jz      loc_140043C8B
0x140042beb  mov     ecx, [rdx+20h]
0x140042bee  mov     edx, [rdx+28h]
0x140042bf1  add     ecx, r13d
0x140042bf4  add     rdx, 0FFFh
0x140042bfb  and     ecx, 0FFFh
0x140042c01  add     rdx, rcx
0x140042c04  shr     rdx, 0Ch
0x140042c08  cmp     r13d, 1000h
0x140042c0f  jb      short loc_140042C23
0x140042c11  mov     r12d, r13d
0x140042c14  shr     r12d, 0Ch
0x140042c18  mov     eax, r12d
0x140042c1b  shl     eax, 0Ch
0x140042c1e  sub     r13d, eax
0x140042c21  jmp     short loc_140042C26
0x140042c23  xor     r12d, r12d
0x140042c26  lea     eax, [r12+r15]
0x140042c2a  mov     [rsp+320h+var_2A8], r13
0x140042c2f  cmp     eax, edx
0x140042c31  ja      loc_140043C8B
0x140042c37  mov     rax, [rbx+10h]
0x140042c3b  mov     [rsp+320h+var_38], rsi
0x140042c43  movzx   ecx, byte ptr [rax+6C0h]
0x140042c4a  movzx   eax, byte ptr [rax+6C1h]
0x140042c51  mov     [rsp+320h+var_2DB], cl
0x140042c55  mov     rcx, [r8+0B8h]
0x140042c5c  mov     [rbp+220h+var_2A0], rcx
0x140042c60  mov     cl, 2; NewIrql
0x140042c62  mov     [rsp+320h+var_2DC], al
0x140042c66  call    cs:__imp_KfRaiseIrql
0x140042c6d  nop     dword ptr [rax+rax+00h]
0x140042c72  mov     [rsp+320h+var_2E0], al
0x140042c76  lock inc dword ptr [rdi+80h]
0x140042c7d  mov     rcx, [rdi+58h]
0x140042c81  lea     rsi, [rdi+58h]
0x140042c85  mov     [rsp+320h+var_2C0], rsi
0x140042c8a  movzx   edx, byte ptr [rcx+4E4h]
0x140042c91  test    dl, dl
0x140042c93  jz      short loc_140042CF9
0x140042c95  lock dec dword ptr [rdi+80h]
0x140042c9c  mov     rax, [rsp+320h+var_2C8]
0x140042ca1  test    rax, rax
0x140042ca4  jz      short loc_140042CB8
0x140042ca6  mov     edx, [rbp+220h+arg_20]
0x140042cac  mov     r8, rax
0x140042caf  mov     rcx, [rbx+10h]
0x140042cb3  call    FreeNVMePrpListBufferEntry
0x140042cb8  movzx   ecx, [rsp+320h+var_2E0]; NewIrql
0x140042cbd  call    cs:__imp_KeLowerIrql
0x140042cc4  nop     dword ptr [rax+rax+00h]
0x140042cc9  mov     eax, 0C000000Eh
0x140042cce  mov     rsi, [rsp+320h+var_38]
0x140042cd6  mov     rcx, [rbp+220h+var_60]
0x140042cdd  xor     rcx, rsp; StackCookie
0x140042ce0  call    __security_check_cookie
0x140042ce5  add     rsp, 2F0h
0x140042cec  pop     r15
0x140042cee  pop     r14
0x140042cf0  pop     r13
0x140042cf2  pop     r12
0x140042cf4  pop     rdi
0x140042cf5  pop     rbx
0x140042cf6  pop     rbp
0x140042cf7  retn
0x140042cf9  mov     rax, [rsi]
0x140042cfc  cmp     dword ptr [rax+3B4h], 0
0x140042d03  jz      short loc_140042D5A
0x140042d05  lock dec dword ptr [rdi+80h]
0x140042d0c  mov     rdi, [rsp+320h+var_2D0]
0x140042d11  mov     ebx, [rbp+220h+arg_20]
0x140042d17  mov     rcx, rdi
0x140042d1a  mov     rdx, [rsp+320h+var_2B8]
0x140042d1f  mov     r8d, ebx
0x140042d22  call    NvmeNamespaceQueueIo
0x140042d27  mov     rax, [rsp+320h+var_2C8]
0x140042d2c  test    rax, rax
0x140042d2f  jz      short loc_140042D3F
0x140042d31  mov     rcx, [rdi+10h]
0x140042d35  mov     r8, rax
0x140042d38  mov     edx, ebx
0x140042d3a  call    FreeNVMePrpListBufferEntry
0x140042d3f  movzx   ecx, [rsp+320h+var_2E0]; NewIrql
0x140042d44  call    cs:__imp_KeLowerIrql
0x140042d4b  nop     dword ptr [rax+rax+00h]
0x140042d50  mov     eax, 80000011h
0x140042d55  jmp     loc_140042CCE
0x140042d5a  mov     ebx, [rdi+7Ch]
0x140042d5d  test    r14, r14
0x140042d60  jz      loc_1400431CA
0x140042d66  nop     word ptr [rax+rax+00000000h]
0x140042d70  movzx   esi, word ptr [rdi+8Eh]
0x140042d77  xor     edx, edx
0x140042d79  mov     [rsp+320h+var_2DA], si
0x140042d7e  lea     eax, [rsi+1]
0x140042d81  movzx   ecx, ax
0x140042d84  cmp     ecx, ebx
0x140042d86  cmovb   dx, cx
0x140042d8a  mov     [rsp+320h+var_2D8], edx
0x140042d8e  cmp     dx, [rdi+8Ch]
0x140042d95  jz      short loc_140042DB3
0x140042d97  movzx   eax, si
0x140042d9a  lock cmpxchg [rdi+8Eh], dx
0x140042da3  movsx   ecx, ax
0x140042da6  cmp     ecx, esi
0x140042da8  jnz     short loc_140042D70
0x140042daa  movzx   eax, word ptr [r14]
0x140042dae  jmp     loc_140043323
0x140042db3  lock dec dword ptr [rdi+80h]
0x140042dba  mov     rax, [rsp+320h+var_2C8]
0x140042dbf  mov     rbx, [rsp+320h+var_2D0]
0x140042dc4  test    rax, rax
0x140042dc7  jz      short loc_140042DDB
0x140042dc9  mov     edx, [rbp+220h+arg_20]
0x140042dcf  mov     r8, rax
0x140042dd2  mov     rcx, [rbx+10h]
0x140042dd6  call    FreeNVMePrpListBufferEntry
0x140042ddb  movzx   ecx, [rsp+320h+var_2E0]; NewIrql
0x140042de0  call    cs:__imp_KeLowerIrql
0x140042de7  nop     dword ptr [rax+rax+00h]
0x140042dec  lea     rcx, [rdi+40h]; SListHead
0x140042df0  call    cs:__imp_ExQueryDepthSList
0x140042df7  nop     dword ptr [rax+rax+00h]
0x140042dfc  mov     r9, [rbx+10h]
0x140042e00  mov     rcx, 800000000002000h
0x140042e0a  movzx   eax, ax
0x140042e0d  xorps   xmm0, xmm0
0x140042e10  mov     [rsp+320h+var_2D0], rax
0x140042e15  movups  xmmword ptr [rbp+220h+var_268.Data1], xmm0
0x140042e19  mov     eax, [r9+8]
0x140042e1d  mov     [rsp+320h+var_2C8], rax
0x140042e22  movzx   eax, word ptr [r9+1Ah]
0x140042e27  mov     [rsp+320h+var_2C0], rax
0x140042e2c  movzx   eax, word ptr [r9+16h]
0x140042e31  mov     [rsp+320h+var_2B8], rax
0x140042e36  movzx   eax, word ptr [r14]
0x140042e3a  mov     [rbp+220h+var_2A0], rax
0x140042e3e  movzx   eax, word ptr [rdi+8Eh]
0x140042e45  mov     [rsp+320h+var_2A8], rax
0x140042e4a  movzx   eax, word ptr [rdi+8Ch]
0x140042e51  mov     [rsp+320h+var_2B0], rax
0x140042e56  movzx   eax, word ptr [rdi+88h]
0x140042e5d  mov     [rbp+220h+var_298], rax
0x140042e61  mov     rax, cs:EventNVMeControllerError
0x140042e68  test    byte ptr [r9+88h], 2
0x140042e70  mov     r10, [r9+80h]
0x140042e77  mov     qword ptr [rbp+220h+EventDescriptor.Id], rax
0x140042e7b  mov     rax, 80000000000A000h
0x140042e85  cmovnz  rcx, rax
0x140042e89  mov     [rbp+220h+EventDescriptor.Keyword], rcx
0x140042e8d  mov     rax, [r10+10h]
0x140042e91  mov     rdx, [rax+30h]
0x140042e95  test    rdx, rdx
0x140042e98  jz      short loc_140042ECC
0x140042e9a  movzx   eax, word ptr [rax+28h]
0x140042e9e  test    ax, ax
0x140042ea1  jz      short loc_140042ECC
0x140042ea3  mov     ecx, eax
0x140042ea5  shr     ecx, 1
0x140042ea7  jz      short loc_140042ECC
0x140042ea9  nop     dword ptr [rax+00000000h]
0x140042eb0  dec     ecx
0x140042eb2  cmp     word ptr [rdx+rcx*2], 5Ch ; '\'
0x140042eb7  lea     r8, [rdx+rcx*2]
0x140042ebb  jz      short loc_140042EC3
0x140042ebd  test    ecx, ecx
0x140042ebf  jnz     short loc_140042EB0
0x140042ec1  jmp     short loc_140042ECC
0x140042ec3  test    r8, r8
0x140042ec6  jz      short loc_140042ECC
0x140042ec8  lea     rdx, [r8+2]
0x140042ecc  lea     rax, [r10+38h]
0x140042ed0  mov     qword ptr [rbp+220h+var_250.Size], 4
0x140042ed8  mov     [rbp+220h+var_250.Ptr], rax
0x140042edc  xor     r11d, r11d
0x140042edf  mov     [rbp+220h+var_238], 10h
0x140042ee7  lea     rax, [r10+418h]
0x140042eee  mov     [rbp+220h+var_240], rax
0x140042ef2  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x140042ef9  test    rdx, rdx
0x140042efc  jz      short loc_140042F16
0x140042efe  mov     rax, rcx
0x140042f01  cmp     [rdx+rax*2+2], r11w
0x140042f07  lea     rax, [rax+1]
0x140042f0b  jnz     short loc_140042F01
0x140042f0d  lea     eax, ds:2[rax*2]
0x140042f14  jmp     short loc_140042F22
0x140042f16  mov     eax, 0Ah
0x140042f1b  lea     rdx, aNull_0; "NULL"
0x140042f22  mov     r8, [r9+318h]
0x140042f29  mov     [rbp+220h+var_230], rdx
0x140042f2d  lea     rdx, dword_140157D94
0x140042f34  mov     [rbp+220h+var_228], eax
0x140042f37  mov     [rbp+220h+var_224], r11d
0x140042f3b  test    r8, r8
0x140042f3e  jz      short loc_140042F51
0x140042f40  mov     rax, rcx
0x140042f43  inc     rax
0x140042f46  cmp     [r8+rax], r11b
0x140042f4a  jnz     short loc_140042F43
0x140042f4c  inc     rax
0x140042f4f  jmp     short loc_140042F59
0x140042f51  mov     eax, 1
0x140042f56  mov     r8, rdx
0x140042f59  mov     [rbp+220h+var_218], eax
0x140042f5c  lea     rax, [r9+4]
0x140042f60  mov     [rbp+220h+var_210], rax
0x140042f64  lea     rax, [r9+2E8h]
0x140042f6b  mov     [rbp+220h+var_200], rax
0x140042f6f  mov     rax, [r9+2F0h]
0x140042f76  test    rax, rax
0x140042f79  mov     [rbp+220h+var_220], r8
0x140042f7d  mov     [rbp+220h+var_214], r11d
0x140042f81  cmovnz  rdx, rax
0x140042f85  mov     [rbp+220h+var_208], 2
0x140042f8d  mov     rax, rcx
0x140042f90  mov     [rbp+220h+var_1F8], 1
0x140042f98  nop     dword ptr [rax+rax+00000000h]
0x140042fa0  inc     rax
0x140042fa3  cmp     [rdx+rax], r11b
0x140042fa7  jnz     short loc_140042FA0
0x140042fa9  inc     eax
0x140042fab  mov     [rbp+220h+var_1F0], rdx
0x140042faf  lea     rdx, [r9+320h]
0x140042fb6  mov     [rbp+220h+var_1E8], eax
0x140042fb9  mov     [rbp+220h+var_1E0], rdx
0x140042fbd  mov     rax, rcx
0x140042fc0  mov     [rbp+220h+var_1E4], r11d
0x140042fc4  inc     rax
0x140042fc7  cmp     [rdx+rax], r11b
0x140042fcb  jnz     short loc_140042FC4
0x140042fcd  inc     eax
0x140042fcf  mov     [rbp+220h+var_1D4], r11d
0x140042fd3  add     r9, 349h
0x140042fda  mov     [rbp+220h+var_1D8], eax
0x140042fdd  mov     [rbp+220h+var_1D0], r9
0x140042fe1  cmp     [r9+rcx+1], r11b
0x140042fe6  lea     rcx, [rcx+1]
0x140042fea  jnz     short loc_140042FE1
0x140042fec  lea     eax, [rcx+1]
0x140042fef  mov     [rbp+220h+var_1C4], r11d
0x140042ff3  mov     rcx, cs:StorPortEventProvider_Context; RegHandle
0x140042ffa  lea     rdx, [rbp+220h+EventDescriptor]; EventDescriptor
0x140042ffe  mov     [rbp+220h+var_1C8], eax
0x140043001  mov     r9d, 1; Flags
0x140043007  lea     rax, aFailedToGetFre_1; "Failed to get free slot"
0x14004300e  mov     [rbp+220h+var_1B8], 30h ; '0'
0x140043016  mov     [rbp+220h+var_1C0], rax
0x14004301a  xor     r8d, r8d; Filter
0x14004301d  lea     rax, aSqId; "SQ ID"
0x140043024  mov     [rbp+220h+var_1A8], 0Ch
0x14004302c  mov     [rbp+220h+var_1B0], rax
0x140043030  lea     rax, [rbp+220h+var_298]
0x140043034  mov     [rbp+220h+var_1A0], rax
0x14004303b  lea     rax, aSqHead_0; "SQ head"
0x140043042  mov     [rbp+220h+var_190], rax
0x140043049  lea     rax, [rsp+320h+var_2B0]
0x14004304e  mov     [rbp+220h+var_180], rax
0x140043055  lea     rax, aSqTail_0; "SQ tail"
0x14004305c  mov     [rbp+220h+var_170], rax
0x140043063  lea     rax, [rsp+320h+var_2A8]
0x140043068  mov     [rbp+220h+var_160], rax
0x14004306f  lea     rax, aCommandId; "Command ID"
0x140043076  mov     [rbp+220h+var_150], rax
0x14004307d  lea     rax, [rbp+220h+var_2A0]
0x140043081  mov     [rbp+220h+var_140], rax
0x140043088  lea     rax, aIoSqCount; "IO SQ count"
0x14004308f  mov     [rbp+220h+var_130], rax
0x140043096  lea     rax, [rsp+320h+var_2B8]
  ... truncated ...
```
