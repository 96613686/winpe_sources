# NvmeSendSplitIo

- ea: `0x140060e90`
- end: `0x140062189`
- name: `NvmeSendSplitIo`
- size: `4857`
- prototype: ``
- caller_count: `7`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x14004cbb0`
- `0x140051870`
- `0x140062190`
- `0x1400648b0`
- `0x14012f8c0`
- `0x140131650`
- `0x140133400`

## callees

- `0x140043ca0`
- `0x140044f10`
- `0x140060e90`
- `0x140066260`
- `0x140134390`
- `0x1401344c0`
- `0x14014b400`
- `0x14014b440`

## import_xrefs

- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x1400617d3`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x140061932`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x1400617d3`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x140061932`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140060fa8`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1400615ca`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1400616a5`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140060fa8`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1400615ca`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1400616a5`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140061636`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1400617f5`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140061636`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1400617f5`
- `ntoskrnl!EtwWriteEx` at `0x14006156e`
- `ntoskrnl!EtwWriteEx` at `0x14006156e`
- `ntoskrnl!KeFlushIoBuffers` at `0x140061e77`
- `ntoskrnl!KeFlushIoBuffers` at `0x140061e77`
- `ntoskrnl!KeLowerIrql` at `0x140061f1c`
- `ntoskrnl!KeLowerIrql` at `0x140061f1c`
- `ntoskrnl!KfRaiseIrql` at `0x140061054`
- `ntoskrnl!KfRaiseIrql` at `0x140061054`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400620b8`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400620b8`
- `ntoskrnl!ExQueryDepthSList` at `0x14006119a`
- `ntoskrnl!ExQueryDepthSList` at `0x14006119a`
- `ntoskrnl!KeQuerySystemTimePrecise` at `0x14006213e`
- `ntoskrnl!KeQuerySystemTimePrecise` at `0x14006213e`
- `HAL!KeQueryPerformanceCounter` at `0x140061924`
- `HAL!KeQueryPerformanceCounter` at `0x140061924`

## string_xrefs

- `0x14006142b`: `Command ID`
- `0x140061491`: `Free command ID count`

## pseudocode

```c
__int64 __fastcall NvmeSendSplitIo(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        unsigned __int16 *a4,
        bool *a5,
        __int64 *a6,
        _DWORD *a7,
        unsigned __int16 *a8,
        char a9)
{
  PSLIST_ENTRY v9; // rsi
  __int64 v10; // rdi
  __int64 v11; // rbx
  __int64 v13; // r9
  __int64 v14; // r13
  __int64 v15; // r10
  __int64 v16; // rdx
  __int64 v17; // rax
  int v18; // ecx
  char *v19; // r8
  bool v20; // zf
  __int64 v21; // rax
  unsigned __int64 v22; // r13
  signed __int32 v23; // edx
  __int64 v24; // r8
  __int64 v25; // rdx
  __int64 v26; // rbx
  unsigned int v27; // esi
  unsigned int v28; // ebx
  int v29; // esi
  int v30; // edx
  unsigned __int16 Next_high; // r15
  USHORT DepthSList; // ax
  __int64 v33; // r9
  unsigned __int64 v34; // rcx
  __int64 v35; // r10
  __int64 v36; // rax
  const wchar_t *v37; // rdx
  unsigned int v38; // eax
  __int64 v39; // rcx
  const wchar_t *v40; // r8
  __int64 v41; // rcx
  __int64 v42; // rax
  int v43; // eax
  const int *v44; // r8
  const int *v45; // rdx
  __int64 v46; // rax
  int v47; // eax
  const int *v48; // rax
  __int64 v49; // rax
  __int64 v50; // rax
  __int64 v51; // r9
  __int64 v52; // r8
  signed __int32 v53; // ecx
  signed __int32 v54; // r12d
  PSLIST_ENTRY v55; // r9
  signed __int16 v56; // r8
  __int64 v57; // r13
  unsigned int v58; // ecx
  unsigned int v59; // eax
  unsigned int v60; // r14d
  __int64 v61; // rbx
  unsigned int v62; // r15d
  unsigned __int64 v63; // rax
  __int64 *v64; // rcx
  __int64 v65; // r12
  __int64 v66; // r11
  unsigned __int64 v67; // r14
  __int16 v68; // cx
  __int64 v69; // rdx
  __int64 v70; // rbx
  ULONGLONG UnbiasedInterruptTime; // rax
  unsigned int v72; // ecx
  unsigned int v73; // edx
  __int64 v74; // rdx
  signed __int32 v75; // eax
  unsigned int v76; // esi
  __int64 v77; // rbx
  char v78; // bl
  char v79; // r14
  LARGE_INTEGER PerformanceCounter; // rax
  __int64 v81; // rax
  __int64 v82; // rbx
  __int64 v83; // rax
  _OWORD *v84; // rcx
  unsigned int v85; // r8d
  int v86; // r11d
  int v87; // r10d
  int v88; // r9d
  __int64 v89; // rax
  __int64 v90; // rcx
  unsigned __int64 v91; // r8
  unsigned int v92; // eax
  __int64 v93; // r10
  __int64 v94; // r11
  PSLIST_ENTRY v95; // rdx
  __int64 v96; // rbx
  __m128i *Next; // r9
  unsigned int v98; // r8d
  __m128i v99; // xmm0
  __int64 v100; // rax
  __int64 v101; // rax
  unsigned int v102; // r11d
  unsigned int *v103; // r9
  _SLIST_ENTRY *v104; // r14
  unsigned int v105; // r12d
  char **v106; // r13
  char **v107; // r8
  unsigned int v108; // ebx
  unsigned int v109; // esi
  char **v110; // r15
  unsigned int v111; // edi
  char *v112; // r10
  __int64 v113; // r9
  char **v114; // rdx
  int v115; // ecx
  unsigned int v116; // r9d
  __int64 v117; // r13
  __int16 v118; // cx
  unsigned __int16 v119; // dx
  __int64 v120; // rcx
  __int64 v121; // rcx
  signed __int16 v122; // bx
  __int64 v123; // r12
  unsigned __int16 v124; // bx
  __int64 v125; // r10
  _QWORD *v126; // rcx
  __int64 v127; // rax
  void (__fastcall *v128)(_QWORD, __int64, bool); // rax
  int v129; // edx
  _WORD *v130; // rcx
  _BYTE **v131; // rcx
  __int16 v133; // cx
  __int64 v134; // rax
  __int64 v135; // rbx
  __int64 v136; // rdx
  unsigned int v137; // r8d
  __int64 v138; // rcx
  __int64 v139; // rdx
  __int64 v140; // rsi
  signed __int32 v141; // r15d
  _QWORD *v142; // rcx
  GUID v143; // xmm0
  signed __int32 v144[6]; // [rsp+8h] [rbp-100h] BYREF
  unsigned __int16 v145; // [rsp+48h] [rbp-C0h]
  unsigned int v146; // [rsp+4Ch] [rbp-BCh]
  bool v147; // [rsp+50h] [rbp-B8h]
  KIRQL v148; // [rsp+51h] [rbp-B7h]
  __int64 v149; // [rsp+58h] [rbp-B0h]
  int v150; // [rsp+60h] [rbp-A8h]
  char v151; // [rsp+64h] [rbp-A4h]
  char v152; // [rsp+65h] [rbp-A3h]
  unsigned __int16 v153; // [rsp+66h] [rbp-A2h]
  __int64 v154; // [rsp+68h] [rbp-A0h]
  PSLIST_ENTRY NewNVMePrpListBufferEntry; // [rsp+70h] [rbp-98h] BYREF
  __int64 v156; // [rsp+78h] [rbp-90h]
  unsigned __int64 v157; // [rsp+80h] [rbp-88h] BYREF
  unsigned __int16 v158; // [rsp+88h] [rbp-80h]
  unsigned int *v159; // [rsp+90h] [rbp-78h] BYREF
  __int64 v160; // [rsp+98h] [rbp-70h] BYREF
  char *v161; // [rsp+A0h] [rbp-68h] BYREF
  unsigned __int64 v162; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v163; // [rsp+B0h] [rbp-58h] BYREF
  __int64 v164; // [rsp+B8h] [rbp-50h]
  __int64 v165; // [rsp+C0h] [rbp-48h] BYREF
  __int64 *v166; // [rsp+C8h] [rbp-40h]
  unsigned __int16 *v167; // [rsp+D0h] [rbp-38h]
  _DWORD *v168; // [rsp+D8h] [rbp-30h]
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+E0h] [rbp-28h] BYREF
  GUID ActivityId; // [rsp+F0h] [rbp-18h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+118h] [rbp+10h] BYREF
  __int64 v172; // [rsp+128h] [rbp+20h]
  __int64 v173; // [rsp+130h] [rbp+28h]
  const wchar_t *v174; // [rsp+138h] [rbp+30h]
  int v175; // [rsp+140h] [rbp+38h]
  int v176; // [rsp+144h] [rbp+3Ch]
  const int *v177; // [rsp+148h] [rbp+40h]
  int v178; // [rsp+150h] [rbp+48h]
  int v179; // [rsp+154h] [rbp+4Ch]
  __int64 v180; // [rsp+158h] [rbp+50h]
  __int64 v181; // [rsp+160h] [rbp+58h]
  __int64 v182; // [rsp+168h] [rbp+60h]
  __int64 v183; // [rsp+170h] [rbp+68h]
  const int *v184; // [rsp+178h] [rbp+70h]
  int v185; // [rsp+180h] [rbp+78h]
  int v186; // [rsp+184h] [rbp+7Ch]
  __int64 v187; // [rsp+188h] [rbp+80h]
  int v188; // [rsp+190h] [rbp+88h]
  int v189; // [rsp+194h] [rbp+8Ch]
  __int64 v190; // [rsp+198h] [rbp+90h]
  int v191; // [rsp+1A0h] [rbp+98h]
  int v192; // [rsp+1A4h] [rbp+9Ch]
  const wchar_t *v193; // [rsp+1A8h] [rbp+A0h]
  __int64 v194; // [rsp+1B0h] [rbp+A8h]
  const wchar_t *v195; // [rsp+1B8h] [rbp+B0h]
  __int64 v196; // [rsp+1C0h] [rbp+B8h]
  unsigned __int64 *v197; // [rsp+1C8h] [rbp+C0h]
  __int64 v198; // [rsp+1D0h] [rbp+C8h]
  const wchar_t *v199; // [rsp+1D8h] [rbp+D0h]
  __int64 v200; // [rsp+1E0h] [rbp+D8h]
  __int64 *v201; // [rsp+1E8h] [rbp+E0h]
  __int64 v202; // [rsp+1F0h] [rbp+E8h]
  const wchar_t *v203; // [rsp+1F8h] [rbp+F0h]
  __int64 v204; // [rsp+200h] [rbp+F8h]
  __int64 *v205; // [rsp+208h] [rbp+100h]
  __int64 v206; // [rsp+210h] [rbp+108h]
  const wchar_t *v207; // [rsp+218h] [rbp+110h]
  __int64 v208; // [rsp+220h] [rbp+118h]
  __int64 *v209; // [rsp+228h] [rbp+120h]
  __int64 v210; // [rsp+230h] [rbp+128h]
  const wchar_t *v211; // [rsp+238h] [rbp+130h]
  __int64 v212; // [rsp+240h] [rbp+138h]
  unsigned int **v213; // [rsp+248h] [rbp+140h]
  __int64 v214; // [rsp+250h] [rbp+148h]
  const wchar_t *v215; // [rsp+258h] [rbp+150h]
  __int64 v216; // [rsp+260h] [rbp+158h]
  unsigned __int64 *v217; // [rsp+268h] [rbp+160h]
  __int64 v218; // [rsp+270h] [rbp+168h]
  const wchar_t *v219; // [rsp+278h] [rbp+170h]
  __int64 v220; // [rsp+280h] [rbp+178h]
  PSLIST_ENTRY *p_NewNVMePrpListBufferEntry; // [rsp+288h] [rbp+180h]
  __int64 v222; // [rsp+290h] [rbp+188h]
  const wchar_t *v223; // [rsp+298h] [rbp+190h]
  __int64 v224; // [rsp+2A0h] [rbp+198h]
  __int64 *v225; // [rsp+2A8h] [rbp+1A0h]
  __int64 v226; // [rsp+2B0h] [rbp+1A8h]

  v9 = 0;
  v166 = a6;
  v10 = a3;
  v168 = a7;
  v167 = a8;
  v11 = a1;
  v13 = *(_QWORD *)(a1 + 16);
  v14 = *(unsigned int *)(a1 + 52);
  v15 = a2;
  v164 = a1;
  v16 = *(_QWORD *)(v13 + 16);
  v160 = a3;
  v152 = *(_BYTE *)(v16 + 1728);
  v157 = *(_QWORD *)(v16 + 136);
  v158 = *(_WORD *)(a1 + 34);
  LOWORD(v150) = *(_WORD *)(a1 + 32);
  v17 = *(_QWORD *)(a1 + 24);
  v18 = *(_DWORD *)(a1 + 56);
  v146 = v15;
  v19 = *(char **)(v17 + 184);
  NewNVMePrpListBufferEntry = 0;
  v149 = v13;
  v161 = v19;
  v20 = *v19 == 3;
  v151 = *v19;
  v21 = *((_QWORD *)v19 + 3);
  v147 = v20;
  v156 = v21;
  v22 = ((unsigned __int64)(v18 & 0xFFF) + v14 + 4095) >> 12;
  v162 = v22;
  if ( (unsigned int)v22 > 2 )
  {
    NewNVMePrpListBufferEntry = ExpInterlockedPopEntrySList(*(PSLIST_HEADER *)(*(_QWORD *)(v16 + 880) + 8 * v15));
    v9 = NewNVMePrpListBufferEntry;
    if ( !NewNVMePrpListBufferEntry )
    {
      NewNVMePrpListBufferEntry = (PSLIST_ENTRY)AllocateNewNVMePrpListBufferEntry(*(_QWORD *)(v149 + 16), v146);
      v9 = NewNVMePrpListBufferEntry;
      if ( !NewNVMePrpListBufferEntry )
      {
        v23 = -1073741670;
        v148 = 0;
        LOBYTE(v145) = 0;
LABEL_60:
        v52 = v156;
        *(_DWORD *)(v11 + 112) = v23;
        _InterlockedExchange((volatile __int32 *)(v11 + 104), 5);
        v150 = v23;
        _InterlockedCompareExchange((volatile signed __int32 *)(v52 + 112), v23, 0);
        v53 = *(unsigned __int16 *)(v52 + 32);
        v54 = _InterlockedIncrement((volatile signed __int32 *)(v52 + 116));
        v27 = v23;
        if ( a5 )
          *a5 = v54 >= v53;
        goto LABEL_96;
      }
    }
    LODWORD(v15) = v146;
    v13 = v149;
  }
  if ( !a4 )
  {
    v24 = *(_QWORD *)(v13 + 16);
    if ( (*(_BYTE *)(v24 + 136) & 2) != 0 )
      v10 = *(_QWORD *)(v24 + 728) + 192LL * (unsigned int)v15;
    else
      v10 = 192LL * *(unsigned __int16 *)(*(_QWORD *)(v24 + 872) + 2LL * (unsigned int)v15)
          + *(_QWORD *)(v24 + 728)
          - 192LL;
    v160 = v10;
  }
  v148 = KfRaiseIrql(2u);
  LOBYTE(v145) = 1;
  _InterlockedIncrement((volatile signed __int32 *)(v10 + 128));
  if ( *(_BYTE *)(*(_QWORD *)(v10 + 88) + 1252LL) )
  {
    _InterlockedDecrement((volatile signed __int32 *)(v10 + 128));
    if ( v9 )
      FreeNVMePrpListBufferEntry(*(_QWORD *)(v149 + 16), v146);
    v23 = -1073741810;
    goto LABEL_60;
  }
  if ( *(_DWORD *)(*(_QWORD *)(v10 + 88) + 948LL) )
  {
    _InterlockedDecrement((volatile signed __int32 *)(v10 + 128));
    if ( _InterlockedCompareExchange((volatile signed __int32 *)(v11 + 104), 3, 1) != 1
      || _interlockedbittestandset((volatile signed __int32 *)(v156 + 108), 0) )
    {
      v26 = v149;
    }
    else
    {
      v25 = *(_QWORD *)(v11 + 24);
      v26 = v149;
      NvmeNamespaceQueueIo(v149, v25, v146);
    }
    if ( v9 )
      FreeNVMePrpListBufferEntry(*(_QWORD *)(v26 + 16), v146);
    v27 = -2147483631;
    goto LABEL_96;
  }
  v28 = *(_DWORD *)(v10 + 124);
  if ( a4 )
  {
    while ( 1 )
    {
      v30 = 0;
      v153 = *(_WORD *)(v10 + 142);
      LOWORD(v29) = v153;
      if ( (unsigned __int16)(v153 + 1) < v28 )
        LOWORD(v30) = v153 + 1;
      LODWORD(v154) = v30;
      if ( (_WORD)v30 == *(_WORD *)(v10 + 140) )
        break;
      if ( _InterlockedCompareExchange16((volatile signed __int16 *)(v10 + 142), v30, v153) == v153 )
      {
        Next_high = *a4;
        goto LABEL_80;
      }
    }
    _InterlockedDecrement((volatile signed __int32 *)(v10 + 128));
    if ( NewNVMePrpListBufferEntry )
      FreeNVMePrpListBufferEntry(*(_QWORD *)(v149 + 16), v146);
    DepthSList = ExQueryDepthSList((PSLIST_HEADER)(v10 + 64));
    v33 = *(_QWORD *)(v149 + 16);
    v34 = 0x800000000002000LL;
    v163 = DepthSList;
    ActivityId = 0;
    NewNVMePrpListBufferEntry = (PSLIST_ENTRY)*(unsigned int *)(v33 + 8);
    v157 = *(unsigned __int16 *)(v33 + 26);
    v159 = (unsigned int *)*(unsigned __int16 *)(v33 + 22);
    v160 = *a4;
    v165 = *(unsigned __int16 *)(v10 + 142);
    v161 = (char *)*(unsigned __int16 *)(v10 + 140);
    v162 = *(unsigned __int16 *)(v10 + 136);
    v20 = (*(_BYTE *)(v33 + 136) & 2) == 0;
    v35 = *(_QWORD *)(v33 + 128);
    *(_QWORD *)&EventDescriptor.Id = EventNVMeControllerError;
    if ( !v20 )
      v34 = 0x80000000000A000LL;
    EventDescriptor.Keyword = v34;
    v36 = *(_QWORD *)(v35 + 16);
    v37 = *(const wchar_t **)(v36 + 48);
    if ( v37 )
    {
      v38 = *(unsigned __int16 *)(v36 + 40);
      if ( (_WORD)v38 )
      {
        LODWORD(v39) = v38 >> 1;
        if ( v38 >> 1 )
        {
          while ( 1 )
          {
            v39 = (unsigned int)(v39 - 1);
            v40 = &v37[v39];
            if ( *v40 == 92 )
              break;
            if ( !(_DWORD)v39 )
              goto LABEL_41;
          }
          if ( v40 )
            v37 = v40 + 1;
        }
      }
    }
LABEL_41:
    *(_QWORD *)&UserData.Size = 4;
    UserData.Ptr = v35 + 56;
    v173 = 16;
    v172 = v35 + 1048;
    v41 = -1;
    if ( v37 )
    {
      v42 = -1;
      do
        v20 = v37[++v42] == 0;
      while ( !v20 );
      v43 = 2 * v42 + 2;
    }
    else
    {
      v43 = 10;
      v37 = L"NULL";
    }
    v44 = *(const int **)(v33 + 792);
    v174 = v37;
    v45 = &dword_140157D94;
    v175 = v43;
    v176 = 0;
    if ( v44 )
    {
      v46 = -1;
      do
        ++v46;
      while ( *((_BYTE *)v44 + v46) );
      v47 = v46 + 1;
    }
    else
    {
      v47 = 1;
      v44 = &dword_140157D94;
    }
    v178 = v47;
    v180 = v33 + 4;
    v182 = v33 + 744;
    v48 = *(const int **)(v33 + 752);
    v177 = v44;
    v179 = 0;
    if ( v48 )
      v45 = v48;
    v181 = 2;
    v49 = -1;
    v183 = 1;
    do
      ++v49;
    while ( *((_BYTE *)v45 + v49) );
    v184 = v45;
    v185 = v49 + 1;
    v187 = v33 + 800;
    v50 = -1;
    v186 = 0;
    do
      ++v50;
    while ( *(_BYTE *)(v33 + 800 + v50) );
    v189 = 0;
    v51 = v33 + 841;
    v188 = v50 + 1;
    v190 = v51;
    do
      v20 = *(_BYTE *)(v51 + v41++ + 1) == 0;
    while ( !v20 );
    v192 = 0;
    v191 = v41 + 1;
    v194 = 74;
    v193 = L"Failed to get free slot for split IO";
    v196 = 12;
    v195 = L"SQ ID";
    v197 = &v162;
    v199 = L"SQ head";
    v201 = (__int64 *)&v161;
    v203 = L"SQ tail";
    v205 = &v165;
    v207 = L"Command ID";
    v209 = &v160;
    v211 = L"IO SQ count";
    v213 = &v159;
    v215 = L"IO CQ count";
    v217 = &v157;
    v219 = L"Queue depth";
    p_NewNVMePrpListBufferEntry = &NewNVMePrpListBufferEntry;
    v223 = L"Free command ID count";
    v225 = &v163;
    v198 = 8;
    v200 = 16;
    v202 = 8;
    v204 = 16;
    v206 = 8;
    v208 = 22;
    v210 = 8;
    v212 = 24;
    v214 = 8;
    v216 = 24;
    v218 = 8;
    v220 = 24;
    v222 = 8;
    v224 = 44;
    v226 = 8;
    EtwWriteEx(StorPortEventProvider_Context, &EventDescriptor, 0, 1u, &ActivityId, 0, 0x1Au, &UserData);
    v11 = v164;
    v23 = -1073741595;
    goto LABEL_60;
  }
  v55 = ExpInterlockedPopEntrySList((PSLIST_HEADER)(v10 + 64));
  if ( v55 )
  {
    _InterlockedOr(v144, 0);
    do
    {
      v56 = 0;
      v153 = *(_WORD *)(v10 + 142);
      v29 = v153;
      if ( (unsigned __int16)(v153 + 1) < v28 )
        v56 = v153 + 1;
      if ( v56 == *(_WORD *)(v10 + 140) )
      {
        ExpInterlockedPushEntrySList((PSLIST_HEADER)(v10 + 64), v55);
        goto LABEL_70;
      }
    }
    while ( _InterlockedCompareExchange16((volatile signed __int16 *)(v10 + 142), v56, v153) != v29 );
LABEL_79:
    Next_high = HIWORD(v55[3].Next);
    LOWORD(v154) = v56;
LABEL_80:
    v63 = HIDWORD(v157);
    LOBYTE(v63) = BYTE4(v157) & 1;
    v20 = (v157 & 0x100000000LL) == 0;
    v145 = Next_high;
    v157 = v63;
    if ( !v20 )
    {
      v64 = v166;
      if ( v166 )
      {
        if ( *v166 && *v166 != v10 )
        {
          _InterlockedIncrement((volatile signed __int32 *)(v10 + 156));
          _InterlockedDecrement((volatile signed __int32 *)(v10 + 128));
          NvmeRingSQDoorbellForBatchingSplitIo(*(_QWORD *)(v149 + 16), *v64, *v168, *v167, 0);
          _InterlockedIncrement((volatile signed __int32 *)(v10 + 128));
          _InterlockedDecrement((volatile signed __int32 *)(v10 + 156));
        }
      }
    }
    v65 = v164;
    v66 = v149;
    v67 = (unsigned __int64)Next_high << 7;
    _InterlockedExchange((volatile __int32 *)(v164 + 104), 2);
    v68 = *(_WORD *)(v66 + 668);
    v69 = *(_QWORD *)(v10 + 32);
    v162 = v67;
    if ( v68 )
    {
      *(_WORD *)(v69 + v67 + 58) = v68;
      v70 = *(_QWORD *)(v10 + 32);
      UnbiasedInterruptTime = KeQueryUnbiasedInterruptTime();
      v66 = v149;
      *(_QWORD *)(v70 + v67 + 64) = UnbiasedInterruptTime;
    }
    else
    {
      *(_WORD *)(v69 + v67 + 58) = *(_WORD *)(v66 + 424);
      *(_QWORD *)(*(_QWORD *)(v10 + 32) + v67 + 64) = **(_QWORD **)(*(_QWORD *)(*(_QWORD *)(v10 + 88) + 1312LL) + 40LL);
    }
    *(_DWORD *)(v67 + *(_QWORD *)(v10 + 32) + 88) = *(_DWORD *)(v66 + 56);
    if ( (*(_DWORD *)(*(_QWORD *)(v66 + 624) + 4LL) & 1) != 0 )
    {
      if ( UseQPCTime )
        PerformanceCounter = KeQueryPerformanceCounter(0);
      else
        PerformanceCounter.QuadPart = KeQueryUnbiasedInterruptTime();
      v66 = v149;
      *(LARGE_INTEGER *)(v67 + *(_QWORD *)(v10 + 32) + 72) = PerformanceCounter;
    }
    v81 = *(_QWORD *)(v10 + 24);
    *(_QWORD *)&EventDescriptor.Id = 16LL * (unsigned __int16)v29;
    v82 = *(_QWORD *)(*(_QWORD *)&EventDescriptor.Id + v81);
    v83 = *(_QWORD *)(v10 + 32);
    v165 = v82;
    if ( (*(_BYTE *)(v67 + v83 + 60) & 4) != 0 )
    {
      v84 = *(_OWORD **)(*(_QWORD *)(v10 + 24) + 16LL * (unsigned __int16)v29);
      *v84 = 0;
      v84[1] = 0;
      v84[2] = 0;
      v84[3] = 0;
    }
    if ( v151 == 3 )
    {
      v85 = *(_DWORD *)(v66 + 64);
      v86 = *(_DWORD *)(v66 + 56);
      v87 = 0;
      v88 = *(_DWORD *)(v65 + 52) / v85;
      v89 = *(_QWORD *)(v65 + 40);
      *(_BYTE *)v82 = 2;
    }
    else
    {
      if ( FUAEnabled && (v161[2] & 4) != 0 )
        v87 = 0x40000000;
      else
        v87 = 0;
      v85 = *(_DWORD *)(v66 + 64);
      v86 = *(_DWORD *)(v66 + 56);
      v88 = *(_DWORD *)(v65 + 52) / v85;
      v89 = *(_QWORD *)(v65 + 40);
      *(_BYTE *)v82 = 1;
      *(_WORD *)(v82 + 54) = 0;
      *(_DWORD *)(v82 + 48) &= 0xFF0FFFFF;
    }
    *(_DWORD *)v82 &= 0xFFFFFCFF;
    v90 = v85;
    v91 = v157;
    *(_WORD *)(v82 + 48) = v88 - 1;
    *(_DWORD *)(v82 + 48) &= 0xC3FFFFFF;
    *(_QWORD *)(v82 + 40) = v89 / v90;
    v92 = *(_DWORD *)(v82 + 48) & 0xBFFFFFFF;
    *(_WORD *)(v82 + 2) = Next_high;
    *(_DWORD *)(v82 + 4) = v86;
    *(_QWORD *)(v82 + 16) = 0;
    *(_DWORD *)(v82 + 48) = (v87 | v92) & 0x7FFFFFFF;
    *(_BYTE *)(v82 + 52) = 0;
    *(_QWORD *)(v82 + 56) = 0;
    if ( (_BYTE)v91 )
    {
      v93 = *(unsigned int *)(v65 + 60);
      v94 = *(_QWORD *)(*(_QWORD *)(v65 + 24) + 8LL) + 48LL;
      *(_QWORD *)(v82 + 24) = *(unsigned int *)(v65 + 56) + (*(_QWORD *)(v94 + 8 * v93) << 12);
      if ( (_DWORD)v22 == 1 )
      {
LABEL_118:
        v95 = NewNVMePrpListBufferEntry;
        *(_BYTE *)(v67 + *(_QWORD *)(v10 + 32) + 60) = 8;
        goto LABEL_162;
      }
      if ( (_DWORD)v22 == 2 )
      {
        *(_QWORD *)(v82 + 32) = *(_QWORD *)(v94 + 8LL * (unsigned int)(v93 + 1)) << 12;
        goto LABEL_118;
      }
      v96 = (unsigned int)(v22 - 1);
      if ( (unsigned int)v22 > 1 )
      {
        Next = (__m128i *)NewNVMePrpListBufferEntry[1].Next;
        v98 = 1;
        if ( (unsigned int)v96 < 8
          || (unsigned __int64)&Next->m128i_u64[1] <= v94 + 8 * (unsigned __int64)(unsigned int)(v93 + v96)
          && (unsigned __int64)Next + 8 * v96 >= v94 + 8 * (unsigned __int64)(unsigned int)(v93 + 1) )
        {
          goto LABEL_217;
        }
        do
        {
          *Next = _mm_slli_epi64(_mm_loadu_si128((const __m128i *)(v94 + 8LL * (v98 + (unsigned int)v93))), 0xCu);
          Next[1] = _mm_slli_epi64(_mm_loadu_si128((const __m128i *)(v94 + 8LL * (v98 + (_DWORD)v93 + 2))), 0xCu);
          v99 = _mm_loadu_si128((const __m128i *)(v94 + 8LL * (v98 + (_DWORD)v93 + 4)));
          v100 = v98 + (_DWORD)v93 + 6;
          v98 += 8;
          Next[2] = _mm_slli_epi64(v99, 0xCu);
          Next[3] = _mm_slli_epi64(_mm_loadu_si128((const __m128i *)(v94 + 8 * v100)), 0xCu);
          Next += 4;
        }
        while ( v98 < (unsigned int)v22 - (((_BYTE)v22 - 1) & 7) );
        if ( v98 < (unsigned int)v22 )
        {
LABEL_217:
          do
          {
            v101 = v98 + (unsigned int)v93;
            ++v98;
            Next = (__m128i *)((char *)Next + 8);
            Next[-1].m128i_i64[1] = *(_QWORD *)(v94 + 8 * v101) << 12;
          }
          while ( v98 < (unsigned int)v22 );
        }
        v91 = v157;
      }
      v95 = NewNVMePrpListBufferEntry;
      v67 = v162;
      *(_QWORD *)(v165 + 32) = *((_QWORD *)&NewNVMePrpListBufferEntry[1].Next + 1);
      LODWORD(v95[2].Next) = v96;
      *(_BYTE *)(v67 + *(_QWORD *)(v10 + 32) + 60) = 8;
    }
    else
    {
      v102 = 0;
      v95 = NewNVMePrpListBufferEntry;
      v103 = *(unsigned int **)(*(_QWORD *)(v65 + 88) + 24LL);
      v159 = v103;
      if ( NewNVMePrpListBufferEntry )
      {
        v104 = NewNVMePrpListBufferEntry[1].Next;
        v105 = WORD2(NewNVMePrpListBufferEntry[2].Next) + 1;
        v161 = (char *)*((_QWORD *)&NewNVMePrpListBufferEntry[1].Next + 1);
      }
      else
      {
        v161 = 0;
        v104 = 0;
        v105 = 2;
      }
      if ( *v103 )
      {
        v106 = (char **)(v82 + 24);
        v107 = (char **)(v82 + 24);
        v108 = 0;
        v109 = 0;
        v110 = (char **)(v165 + 32);
        v111 = *(_DWORD *)(v164 + 52);
        do
        {
          v112 = *(char **)&v103[6 * v109 + 4];
          v113 = v103[6 * v109 + 6];
          if ( v113 + (__int64)v112 % 4096 > 4096 )
          {
            if ( (_DWORD)v113 )
            {
              v114 = v110;
              do
              {
                *v107 = v112;
                v115 = (unsigned __int16)v112 & 0xFFF;
                v116 = v115 + v113;
                v108 += 4096 - v115;
                if ( v116 <= 0x1000 )
                  break;
                if ( v107 == v106 )
                {
                  v107 = v114;
                }
                else if ( v107 == v114 )
                {
                  if ( v104 )
                    v107 = (char **)(&v104->Next + 1);
                }
                else
                {
                  ++v107;
                }
                if ( ++v102 >= v105 || v108 >= v111 )
                  goto LABEL_157;
                v114 = v110;
                v112 += (unsigned int)(4096 - v115);
                LODWORD(v113) = v116 - 4096;
              }
              while ( (_DWORD)v113 );
            }
            v103 = v159;
          }
          else
          {
            v103 = v159;
            *v107 = v112;
            v108 += v103[6 * v109 + 6];
          }
          if ( v107 == v106 )
          {
            v107 = v110;
          }
          else if ( v107 == v110 )
          {
            if ( v104 )
              v107 = (char **)(&v104->Next + 1);
          }
          else
          {
            ++v107;
          }
          if ( ++v102 >= v105 )
            break;
          if ( v108 >= v111 )
            break;
          ++v109;
        }
        while ( v109 < *v103 );
LABEL_157:
        v10 = v160;
        LOWORD(v29) = v153;
        v95 = NewNVMePrpListBufferEntry;
        v91 = v157;
        if ( v102 > 2 )
        {
          v104->Next = (_SLIST_ENTRY *)*v110;
          *v110 = v161;
        }
      }
      if ( v95 )
        LODWORD(v95[2].Next) = v102 - 1;
      v67 = v162;
      *(_BYTE *)(v162 + *(_QWORD *)(v10 + 32) + 60) = -120;
    }
LABEL_162:
    v117 = v164;
    *(_BYTE *)(v67 + *(_QWORD *)(v10 + 32) + 61) = 0;
    *(_QWORD *)(*(_QWORD *)(v10 + 32) + v67 + 24) = *(_QWORD *)(v117 + 24);
    v118 = v146;
    *(_QWORD *)(*(_QWORD *)(v10 + 32) + v67 + 40) = v117;
    *(_WORD *)(*(_QWORD *)(v10 + 32) + v67 + 56) = v29;
    *(_QWORD *)(*(_QWORD *)(v10 + 32) + v67 + 16) = v95;
    v119 = v145;
    *(_WORD *)(*(_QWORD *)(v10 + 32) + v67 + 52) = v118;
    *(_DWORD *)(*(_QWORD *)(v10 + 32) + v67 + 48) = *(_DWORD *)(v117 + 52);
    v120 = *(_QWORD *)&EventDescriptor.Id;
    *(_QWORD *)(*(_QWORD *)(v10 + 32) + v67 + 32) = 0;
    *(_WORD *)(v120 + *(_QWORD *)(v10 + 24) + 8) = v119;
    v121 = v156;
    v122 = _InterlockedExchangeAdd16((volatile signed __int16 *)(v156 + 122), 1u);
    v123 = v149;
    v124 = v122 + 1;
    if ( v124 == 1 )
    {
      *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(v117 + 24) + 184LL) + 3LL) |= 1u;
      if ( (_BYTE)v91 )
      {
        v125 = *(_QWORD *)(*(_QWORD *)(v117 + 24) + 8LL);
        if ( v125 )
        {
          v126 = (_QWORD *)(*(_QWORD *)(*(_QWORD *)(v123 + 16) + 128LL) + 1160LL);
          if ( *(_QWORD *)(*(_QWORD *)(v123 + 16) + 128LL) != -1160 )
          {
            if ( *v126 )
            {
              v127 = *(_QWORD *)(*v126 + 8LL);
              if ( v127 )
              {
                if ( *(int *)(*(_QWORD *)(*(_QWORD *)(v123 + 16) + 128LL) + 1188LL) >= 3
                  && (v128 = *(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(v127 + 240)) != 0 )
                {
                  v128(*v126, v125, v147);
                }
                else
                {
                  LOBYTE(v91) = 1;
                  KeFlushIoBuffers(v125, v147, v91);
                }
              }
            }
          }
        }
      }
      v121 = v156;
    }
    if ( v124 >= *(_WORD *)(v117 + 32) && (*(_DWORD *)(v121 + 108) & 1) != 0 )
      *(_DWORD *)(v121 + 108) &= ~1u;
    _InterlockedOr(v144, 0);
    v129 = 0;
    *(_BYTE *)(*(_QWORD *)(v10 + 32) + v67 + 60) |= 1u;
    _InterlockedDecrement((volatile signed __int32 *)(v10 + 128));
    if ( (unsigned __int16)(v29 + 1) != *(_DWORD *)(v10 + 124) )
      v129 = (unsigned __int16)(v29 + 1);
    if ( (_BYTE)v157 )
    {
      if ( !a9 && v158 + 1 != (unsigned __int16)v150 )
      {
        v79 = 0;
        v130 = v167;
        *v166 = v10;
        *v168 = v129;
        *v130 = v154;
LABEL_182:
        v27 = 259;
LABEL_183:
        KeLowerIrql(v148);
        goto LABEL_184;
      }
      if ( v166 )
        *v166 = 0;
    }
    _InterlockedOr(v144, 0);
    v133 = v154;
    v79 = 1;
    if ( *(_WORD *)(v10 + 142) == (_WORD)v154 )
    {
      while ( _InterlockedCompareExchange((volatile signed __int32 *)(v10 + 132), 1, 0) )
      {
        if ( *(_WORD *)(v10 + 142) != v133 )
          goto LABEL_182;
      }
      while ( *(_DWORD *)(v10 + 128) )
        _InterlockedOr(v144, 0);
      if ( *(_WORD *)(v10 + 142) == v133 )
      {
        if ( v152 == 1 )
        {
          v134 = *(_QWORD *)(v123 + 16);
          LODWORD(v163) = v129;
          (*(void (__fastcall **)(__int64, _QWORD, __int64, _QWORD, __int64 *))(*(_QWORD *)(v134 + 128) + 536LL))(
            *(_QWORD *)(v134 + 1648) + 64LL,
            *(unsigned int *)(v10 + 16),
            4,
            0,
            &v163);
        }
        else
        {
          **(_DWORD **)(v10 + 16) = v129;
          _InterlockedOr(v144, 0);
        }
      }
      _InterlockedOr(v144, 0);
      _InterlockedExchange((volatile __int32 *)(v10 + 132), 0);
      v135 = *(_QWORD *)(v123 + 16);
      if ( (*(_BYTE *)(v135 + 1384) & 1) != 0 )
      {
        ActivityId.Data1 = *(_DWORD *)(v10 + 136);
        *(_QWORD *)ActivityId.Data4 = *(_QWORD *)(v117 + 24);
        *(_DWORD *)&ActivityId.Data2 = *(_DWORD *)v165;
        if ( v135 )
        {
          if ( *(_DWORD *)v135 == 1314276178 )
          {
            v136 = *(_QWORD *)(*(_QWORD *)(v135 + 1392) + 8LL * KeGetCurrentProcessorNumberEx(0));
            v137 = *(_DWORD *)(v136 + 12);
            _InterlockedOr(v144, 0);
            if ( v137 )
            {
              v138 = v136 + 64;
              if ( v136 != -64 )
              {
                v139 = _InterlockedIncrement((volatile signed __int32 *)v136) % v137;
                v140 = v138 + ((unsigned __int64)(unsigned int)v139 << 6);
                if ( (*(_DWORD *)(v135 + 1360) & 1) != 0 )
                  v141 = _InterlockedIncrement((volatile signed __int32 *)(v135 + 1408));
                else
                  v141 = v139;
                *(_DWORD *)(v140 + 4) = v141;
                v142 = (_QWORD *)(v140 + 8);
                *(_DWORD *)v140 = 0x20000;
                if ( (*(_DWORD *)(v135 + 1360) & 2) != 0 )
                {
                  KeQuerySystemTimePrecise(v142, v139);
                  *(GUID *)(v140 + 16) = ActivityId;
                }
                else
                {
                  v143 = ActivityId;
                  *v142 = MEMORY[0xFFFFF78000000014];
                  *(GUID *)(v140 + 16) = v143;
                }
                *(_OWORD *)(v140 + 32) = 0;
              }
            }
          }
        }
      }
    }
    goto LABEL_182;
  }
LABEL_70:
  _InterlockedDecrement((volatile signed __int32 *)(v10 + 128));
  v57 = *(_QWORD *)(v10 + 88);
  v58 = *(unsigned __int16 *)(v57 + 22);
  if ( v58 != 1 )
  {
    v59 = *(unsigned __int16 *)(v10 + 136);
    LODWORD(v154) = v59 - 1;
    v60 = v59 % v58;
    if ( v59 % v58 < v58 )
    {
      do
      {
        v61 = *(_QWORD *)(*(_QWORD *)(v10 + 88) + 728LL) + 192LL * v60;
        _InterlockedIncrement((volatile signed __int32 *)(v61 + 128));
        v62 = *(_DWORD *)(v61 + 124);
        v55 = ExpInterlockedPopEntrySList((PSLIST_HEADER)(v61 + 64));
        if ( v55 )
        {
          _InterlockedOr(v144, 0);
          while ( 1 )
          {
            v56 = 0;
            v153 = *(_WORD *)(v61 + 142);
            v29 = v153;
            if ( (unsigned __int16)(v153 + 1) < v62 )
              v56 = v153 + 1;
            if ( v56 == *(_WORD *)(v61 + 140) )
              break;
            if ( _InterlockedCompareExchange16((volatile signed __int16 *)(v61 + 142), v56, v153) == v29 )
            {
              LODWORD(v22) = v162;
              v10 = v61;
              v160 = v61;
              goto LABEL_79;
            }
          }
          ExpInterlockedPushEntrySList((PSLIST_HEADER)(v61 + 64), v55);
        }
        v72 = *(unsigned __int16 *)(v57 + 22);
        _InterlockedDecrement((volatile signed __int32 *)(v61 + 128));
        v73 = (v60 + 1) % v72;
        v60 = v73;
      }
      while ( v73 != (_DWORD)v154 && v73 < *(unsigned __int16 *)(v57 + 22) );
    }
  }
  v74 = v164;
  v75 = _InterlockedCompareExchange((volatile signed __int32 *)(v164 + 104), 3, 1);
  v76 = v146;
  v77 = v149;
  if ( v75 == 1 && !_interlockedbittestandset((volatile signed __int32 *)(v156 + 108), 0) )
    NvmeNamespaceQueueIo(v77, *(_QWORD *)(v74 + 24), v76);
  if ( NewNVMePrpListBufferEntry )
    FreeNVMePrpListBufferEntry(*(_QWORD *)(v77 + 16), v76);
  v150 = -2147483631;
  v27 = -2147483631;
LABEL_96:
  v78 = v145;
  if ( v166 && *v166 )
  {
    v79 = 1;
    NvmeRingSQDoorbellForBatchingSplitIo(*(_QWORD *)(v149 + 16), *v166, *v168, *v167, v145 ^ 1);
  }
  else
  {
    v79 = 0;
  }
  if ( v78 )
    goto LABEL_183;
LABEL_184:
  if ( v79 )
  {
    v131 = *(_BYTE ***)(v149 + 16);
    if ( *v131[217] )
      NvmeStartIoPolling(v131);
  }
  return v27;
}

```

## disassembly

```asm
0x140060e90  mov     r11, rsp
0x140060e93  push    rbp
0x140060e94  push    rsi
0x140060e95  push    rdi
0x140060e96  lea     rbp, [r11-268h]
0x140060e9d  sub     rsp, 350h
0x140060ea4  mov     rax, cs:__security_cookie
0x140060eab  xor     rax, rsp
0x140060eae  mov     [rbp+260h+var_60], rax
0x140060eb5  mov     rax, [rbp+260h+arg_28]
0x140060ebc  xor     esi, esi
0x140060ebe  mov     [rbp+260h+var_2A0], rax
0x140060ec2  mov     rdi, r8
0x140060ec5  mov     rax, [rbp+260h+arg_30]
0x140060ecc  mov     [rbp+260h+var_290], rax
0x140060ed0  mov     rax, [rbp+260h+arg_38]
0x140060ed7  mov     [rbp+260h+var_298], rax
0x140060edb  mov     [r11-20h], rbx
0x140060edf  mov     rbx, rcx
0x140060ee2  mov     [r11-28h], r12
0x140060ee6  mov     r12d, 1
0x140060eec  mov     [r11-30h], r13
0x140060ef0  mov     [r11-38h], r14
0x140060ef4  mov     r14, r9
0x140060ef7  mov     r9, [rcx+10h]
0x140060efb  mov     r13d, [rbx+34h]
0x140060eff  mov     r10d, edx
0x140060f02  mov     [rbp+260h+var_2B0], rcx
0x140060f06  mov     rdx, [r9+10h]
0x140060f0a  mov     [r11-40h], r15
0x140060f0e  mov     r15, [rbp+260h+arg_20]
0x140060f15  mov     [rbp+260h+var_2D0], r8
0x140060f19  movzx   eax, byte ptr [rdx+6C0h]
0x140060f20  mov     [rsp+360h+var_303], al
0x140060f24  mov     rax, [rdx+88h]
0x140060f2b  mov     [rsp+78h], rax
0x140060f30  movzx   eax, word ptr [rcx+22h]
0x140060f34  mov     [rbp+260h+var_2E0], ax
0x140060f38  movzx   eax, word ptr [rcx+20h]
0x140060f3c  mov     word ptr [rsp+360h+var_308], ax
0x140060f41  mov     rax, [rcx+18h]
0x140060f45  mov     ecx, [rcx+38h]
0x140060f48  movaps  xmmword ptr [r11-58h], xmm6
0x140060f4d  mov     [rsp+360h+var_31C], r10d
0x140060f52  mov     r8, [rax+0B8h]
0x140060f59  mov     [rsp+360h+var_2F8], rsi
0x140060f5e  mov     qword ptr [rsp+360h+var_310], r9
0x140060f63  mov     [rbp+260h+var_2C8], r8
0x140060f67  movzx   eax, byte ptr [r8]
0x140060f6b  cmp     al, 3
0x140060f6d  mov     [rsp+360h+var_304], al
0x140060f71  mov     rax, [r8+18h]
0x140060f75  setz    byte ptr [rsp+360h+var_318]
0x140060f7a  mov     [rsp+360h+var_2F0], rax
0x140060f7f  add     r13, 0FFFh
0x140060f86  and     ecx, 0FFFh
0x140060f8c  add     r13, rcx
0x140060f8f  shr     r13, 0Ch
0x140060f93  mov     [rbp+260h+var_2C0], r13
0x140060f97  cmp     r13d, 2
0x140060f9b  jbe     short loc_140061000
0x140060f9d  mov     rcx, [rdx+370h]
0x140060fa4  mov     rcx, [rcx+r10*8]; ListHead
0x140060fa8  call    cs:__imp_ExpInterlockedPopEntrySList
0x140060faf  nop     dword ptr [rax+rax+00h]
0x140060fb4  mov     [rsp+360h+var_2F8], rax
0x140060fb9  mov     rsi, rax
0x140060fbc  test    rax, rax
0x140060fbf  jnz     short loc_140060FF6
0x140060fc1  mov     rsi, qword ptr [rsp+360h+var_310]
0x140060fc6  mov     edx, [rsp+360h+var_31C]
0x140060fca  mov     rcx, [rsi+10h]
0x140060fce  call    AllocateNewNVMePrpListBufferEntry
0x140060fd3  mov     [rsp+360h+var_2F8], rax
0x140060fd8  mov     rsi, rax
0x140060fdb  test    rax, rax
0x140060fde  jnz     short loc_140060FF6
0x140060fe0  xor     edi, edi
0x140060fe2  mov     edx, 0C000009Ah
0x140060fe7  mov     byte ptr [rsp+360h+var_318+1], dil
0x140060fec  mov     [rsp+360h+var_320], dil
0x140060ff1  jmp     loc_140061583
0x140060ff6  mov     r10d, [rsp+360h+var_31C]
0x140060ffb  mov     r9, qword ptr [rsp+360h+var_310]
0x140061000  test    r14, r14
0x140061003  jnz     short loc_140061052
0x140061005  mov     r8, [r9+10h]
0x140061009  test    byte ptr [r8+88h], 2
0x140061011  jz      short loc_140061027
0x140061013  mov     eax, r10d
0x140061016  lea     rdi, [rax+rax*2]
0x14006101a  shl     rdi, 6
0x14006101e  add     rdi, [r8+2D8h]
0x140061025  jmp     short loc_14006104E
0x140061027  mov     rax, [r8+368h]
0x14006102e  mov     rdi, [r8+2D8h]
0x140061035  mov     ecx, r10d
0x140061038  add     rdi, 0FFFFFFFFFFFFFF40h
0x14006103f  movzx   ecx, word ptr [rax+rcx*2]
0x140061043  lea     rdx, [rcx+rcx*2]
0x140061047  shl     rdx, 6
0x14006104b  add     rdi, rdx
0x14006104e  mov     [rbp+260h+var_2D0], rdi
0x140061052  mov     cl, 2; NewIrql
0x140061054  call    cs:__imp_KfRaiseIrql
0x14006105b  nop     dword ptr [rax+rax+00h]
0x140061060  mov     byte ptr [rsp+360h+var_318+1], al
0x140061064  mov     [rsp+360h+var_320], r12b
0x140061069  lock inc dword ptr [rdi+80h]
0x140061070  mov     rcx, [rdi+58h]
0x140061074  movzx   edx, byte ptr [rcx+4E4h]
0x14006107b  test    dl, dl
0x14006107d  jz      short loc_1400610AA
0x14006107f  lock dec dword ptr [rdi+80h]
0x140061086  test    rsi, rsi
0x140061089  jz      short loc_1400610A0
0x14006108b  mov     edx, [rsp+360h+var_31C]
0x14006108f  mov     r8, rsi
0x140061092  mov     rsi, qword ptr [rsp+360h+var_310]
0x140061097  mov     rcx, [rsi+10h]
0x14006109b  call    FreeNVMePrpListBufferEntry
0x1400610a0  mov     edx, 0C000000Eh
0x1400610a5  jmp     loc_140061583
0x1400610aa  mov     rax, [rdi+58h]
0x1400610ae  cmp     dword ptr [rax+3B4h], 0
0x1400610b5  jz      short loc_140061118
0x1400610b7  lock dec dword ptr [rdi+80h]
0x1400610be  mov     ecx, 3
0x1400610c3  mov     rax, r12
0x1400610c6  lock cmpxchg [rbx+68h], ecx
0x1400610cb  mov     r14d, [rsp+360h+var_31C]
0x1400610d0  jnz     short loc_1400610F5
0x1400610d2  mov     rax, [rsp+360h+var_2F0]
0x1400610d7  lock bts dword ptr [rax+6Ch], 0
0x1400610dd  jb      short loc_1400610F5
0x1400610df  mov     rdx, [rbx+18h]
0x1400610e3  mov     r8d, r14d
0x1400610e6  mov     rbx, qword ptr [rsp+360h+var_310]
0x1400610eb  mov     rcx, rbx
0x1400610ee  call    NvmeNamespaceQueueIo
0x1400610f3  jmp     short loc_1400610FA
0x1400610f5  mov     rbx, qword ptr [rsp+360h+var_310]
0x1400610fa  test    rsi, rsi
0x1400610fd  jz      short loc_14006110E
0x1400610ff  mov     rcx, [rbx+10h]
0x140061103  mov     r8, rsi
0x140061106  mov     edx, r14d
0x140061109  call    FreeNVMePrpListBufferEntry
0x14006110e  mov     esi, 80000011h
0x140061113  jmp     loc_140061884
0x140061118  mov     ebx, [rdi+7Ch]
0x14006111b  test    r14, r14
0x14006111e  jz      loc_1400615C6
0x140061124  nop     dword ptr [rax+00h]
0x140061128  nop     dword ptr [rax+rax+00000000h]
0x140061130  movzx   esi, word ptr [rdi+8Eh]
0x140061137  xor     edx, edx
0x140061139  mov     [rsp+360h+var_302], si
0x14006113e  lea     eax, [rsi+1]
0x140061141  movzx   ecx, ax
0x140061144  cmp     ecx, ebx
0x140061146  cmovb   dx, cx
0x14006114a  mov     dword ptr [rsp+360h+var_300], edx
0x14006114e  cmp     dx, [rdi+8Ch]
0x140061155  jz      short loc_140061173
0x140061157  movzx   eax, si
0x14006115a  lock cmpxchg [rdi+8Eh], dx
0x140061163  movsx   ecx, ax
0x140061166  cmp     ecx, esi
0x140061168  jnz     short loc_140061130
0x14006116a  movzx   r15d, word ptr [r14]
0x14006116e  jmp     loc_140061725
0x140061173  lock dec dword ptr [rdi+80h]
0x14006117a  mov     r8, [rsp+360h+var_2F8]
0x14006117f  mov     rsi, qword ptr [rsp+360h+var_310]
0x140061184  test    r8, r8
0x140061187  jz      short loc_140061196
0x140061189  mov     edx, [rsp+360h+var_31C]
0x14006118d  mov     rcx, [rsi+10h]
0x140061191  call    FreeNVMePrpListBufferEntry
0x140061196  lea     rcx, [rdi+40h]; SListHead
0x14006119a  call    cs:__imp_ExQueryDepthSList
0x1400611a1  nop     dword ptr [rax+rax+00h]
0x1400611a6  mov     r9, [rsi+10h]
0x1400611aa  mov     rcx, 800000000002000h
0x1400611b4  movzx   eax, ax
0x1400611b7  xorps   xmm0, xmm0
0x1400611ba  mov     [rbp+260h+var_2B8], rax
0x1400611be  movups  xmmword ptr [rbp+260h+var_278.Data1], xmm0
0x1400611c2  mov     eax, [r9+8]
0x1400611c6  mov     [rsp+360h+var_2F8], rax
0x1400611cb  movzx   eax, word ptr [r9+1Ah]
0x1400611d0  mov     [rsp+78h], rax
0x1400611d5  movzx   eax, word ptr [r9+16h]
0x1400611da  mov     [rbp+260h+var_2D8], rax
0x1400611de  movzx   eax, word ptr [r14]
0x1400611e2  mov     [rbp+260h+var_2D0], rax
0x1400611e6  movzx   eax, word ptr [rdi+8Eh]
0x1400611ed  mov     [rbp+260h+var_2A8], rax
0x1400611f1  movzx   eax, word ptr [rdi+8Ch]
0x1400611f8  mov     [rbp+260h+var_2C8], rax
0x1400611fc  movzx   eax, word ptr [rdi+88h]
0x140061203  mov     [rbp+260h+var_2C0], rax
0x140061207  mov     rax, cs:EventNVMeControllerError
0x14006120e  test    byte ptr [r9+88h], 2
0x140061216  mov     r10, [r9+80h]
0x14006121d  mov     qword ptr [rbp+260h+EventDescriptor.Id], rax
0x140061221  mov     rax, 80000000000A000h
0x14006122b  cmovnz  rcx, rax
0x14006122f  mov     [rbp+260h+EventDescriptor.Keyword], rcx
0x140061233  mov     rax, [r10+10h]
0x140061237  mov     rdx, [rax+30h]
0x14006123b  test    rdx, rdx
0x14006123e  jz      short loc_14006126C
0x140061240  movzx   eax, word ptr [rax+28h]
0x140061244  test    ax, ax
0x140061247  jz      short loc_14006126C
0x140061249  mov     ecx, eax
0x14006124b  shr     ecx, 1
0x14006124d  jz      short loc_14006126C
0x14006124f  nop
0x140061250  dec     ecx
0x140061252  cmp     word ptr [rdx+rcx*2], 5Ch ; '\'
0x140061257  lea     r8, [rdx+rcx*2]
0x14006125b  jz      short loc_140061263
0x14006125d  test    ecx, ecx
0x14006125f  jnz     short loc_140061250
0x140061261  jmp     short loc_14006126C
0x140061263  test    r8, r8
0x140061266  jz      short loc_14006126C
0x140061268  lea     rdx, [r8+2]
0x14006126c  lea     rax, [r10+38h]
0x140061270  mov     qword ptr [rbp+260h+var_250.Size], 4
0x140061278  mov     [rbp+260h+var_250.Ptr], rax
0x14006127c  xor     r11d, r11d
0x14006127f  mov     [rbp+260h+var_238], 10h
0x140061287  lea     rax, [r10+418h]
0x14006128e  mov     [rbp+260h+var_240], rax
0x140061292  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x140061299  test    rdx, rdx
0x14006129c  jz      short loc_1400612B6
0x14006129e  mov     rax, rcx
0x1400612a1  cmp     [rdx+rax*2+2], r11w
0x1400612a7  lea     rax, [rax+1]
0x1400612ab  jnz     short loc_1400612A1
0x1400612ad  lea     eax, ds:2[rax*2]
0x1400612b4  jmp     short loc_1400612C2
0x1400612b6  mov     eax, 0Ah
0x1400612bb  lea     rdx, aNull_0; "NULL"
0x1400612c2  mov     r8, [r9+318h]
0x1400612c9  mov     [rbp+260h+var_230], rdx
0x1400612cd  lea     rdx, dword_140157D94
0x1400612d4  mov     [rbp+260h+var_228], eax
0x1400612d7  mov     [rbp+260h+var_224], r11d
0x1400612db  test    r8, r8
0x1400612de  jz      short loc_1400612F1
0x1400612e0  mov     rax, rcx
0x1400612e3  inc     rax
0x1400612e6  cmp     [r8+rax], r11b
0x1400612ea  jnz     short loc_1400612E3
0x1400612ec  inc     rax
0x1400612ef  jmp     short loc_1400612F7
0x1400612f1  mov     rax, r12
0x1400612f4  mov     r8, rdx
0x1400612f7  mov     [rbp+260h+var_218], eax
0x1400612fa  lea     rax, [r9+4]
0x1400612fe  mov     [rbp+260h+var_210], rax
0x140061302  lea     rax, [r9+2E8h]
0x140061309  mov     [rbp+260h+var_200], rax
0x14006130d  mov     rax, [r9+2F0h]
0x140061314  test    rax, rax
0x140061317  mov     [rbp+260h+var_220], r8
0x14006131b  mov     [rbp+260h+var_214], r11d
0x14006131f  cmovnz  rdx, rax
0x140061323  mov     [rbp+260h+var_208], 2
0x14006132b  mov     rax, rcx
0x14006132e  mov     [rbp+260h+var_1F8], r12
0x140061332  inc     rax
0x140061335  cmp     [rdx+rax], r11b
0x140061339  jnz     short loc_140061332
0x14006133b  inc     eax
0x14006133d  mov     [rbp+260h+var_1F0], rdx
0x140061341  lea     rdx, [r9+320h]
0x140061348  mov     [rbp+260h+var_1E8], eax
0x14006134b  mov     [rbp+260h+var_1E0], rdx
0x140061352  mov     rax, rcx
0x140061355  mov     [rbp+260h+var_1E4], r11d
0x140061359  nop     dword ptr [rax+00000000h]
0x140061360  inc     rax
0x140061363  cmp     [rdx+rax], r11b
0x140061367  jnz     short loc_140061360
0x140061369  inc     eax
0x14006136b  mov     [rbp+260h+var_1D4], r11d
0x140061372  add     r9, 349h
0x140061379  mov     [rbp+260h+var_1D8], eax
0x14006137f  mov     [rbp+260h+var_1D0], r9
0x140061386  nop     word ptr [rax+rax+00000000h]
0x140061390  cmp     [r9+rcx+1], r11b
0x140061395  lea     rcx, [rcx+1]
0x140061399  jnz     short loc_140061390
  ... truncated ...
```
