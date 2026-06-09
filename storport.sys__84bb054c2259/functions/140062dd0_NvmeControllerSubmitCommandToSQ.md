# NvmeControllerSubmitCommandToSQ

- ea: `0x140062dd0`
- end: `0x140063c6b`
- name: `NvmeControllerSubmitCommandToSQ`
- size: `3739`
- prototype: `__int64 __usercall@<rax>(PVOID SystemArgument2@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140062cc0`

## callees

- `0x140062dd0`
- `0x140066100`
- `0x1401344c0`
- `0x140135f28`
- `0x14014b400`
- `0x14014b440`

## import_xrefs

- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x140063867`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x140063867`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1400633df`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140063462`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140063548`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1400633df`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140063462`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140063548`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14006344a`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1400634cc`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1400635d5`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14006344a`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1400634cc`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1400635d5`
- `ntoskrnl!PoFxIdleComponent` at `0x140063bfb`
- `ntoskrnl!PoFxIdleComponent` at `0x140063bfb`
- `ntoskrnl!EtwWriteEx` at `0x14006339c`
- `ntoskrnl!EtwWriteEx` at `0x14006339c`
- `ntoskrnl!KeLowerIrql` at `0x140062f2e`
- `ntoskrnl!KeLowerIrql` at `0x140063ba7`
- `ntoskrnl!KeLowerIrql` at `0x140062f2e`
- `ntoskrnl!KeLowerIrql` at `0x140063ba7`
- `ntoskrnl!KfRaiseIrql` at `0x140062e36`
- `ntoskrnl!KfRaiseIrql` at `0x140062e36`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140063ad3`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140063ad3`
- `ntoskrnl!ExQueryDepthSList` at `0x140062fef`
- `ntoskrnl!ExQueryDepthSList` at `0x140062fef`
- `ntoskrnl!KeQuerySystemTimePrecise` at `0x140063b65`
- `ntoskrnl!KeQuerySystemTimePrecise` at `0x140063b65`
- `HAL!KeQueryPerformanceCounter` at `0x140063859`
- `HAL!KeQueryPerformanceCounter` at `0x140063859`

## string_xrefs

- `0x14006325a`: `Command ID`
- `0x1400632c1`: `Free command ID count`
- `0x1400631f4`: `Failed to get free slot for non-read/write command`

## pseudocode

```c
__int64 __fastcall NvmeControllerSubmitCommandToSQ(
        _BYTE *SystemArgument2,
        __int64 *a2,
        __int64 a3,
        unsigned int a4,
        unsigned __int16 *a5)
{
  _BYTE **v5; // r13
  int v7; // eax
  __int64 v8; // r12
  __int64 v10; // rax
  __int64 v11; // rsi
  __int64 v12; // rax
  char v13; // r14
  unsigned int v14; // edi
  unsigned int v15; // edx
  __int16 v16; // si
  int v17; // r14d
  signed __int16 v18; // r12
  unsigned __int16 Next_high; // di
  __int64 v20; // rax
  __int16 v21; // r9
  __int64 v22; // r8
  __int64 v23; // rcx
  unsigned __int64 v24; // r13
  __int64 v25; // rdx
  int v26; // eax
  USHORT DepthSList; // ax
  bool v28; // zf
  unsigned __int64 v29; // rcx
  _BYTE *v30; // r9
  __int64 v31; // rax
  const wchar_t *v32; // rdx
  unsigned int v33; // eax
  __int64 v34; // rcx
  const wchar_t *v35; // r8
  __int64 v36; // rax
  int v37; // eax
  const int *v38; // rcx
  const int *v39; // rdx
  __int64 v40; // rax
  int v41; // eax
  const int *v42; // rax
  __int64 v43; // rax
  __int64 v44; // rax
  __int64 v45; // rax
  int v46; // eax
  unsigned int v47; // edi
  union _SLIST_HEADER *v48; // rcx
  PSLIST_ENTRY v49; // r8
  signed __int16 v50; // dx
  PSLIST_ENTRY v51; // r8
  signed __int16 v52; // dx
  char v53; // al
  unsigned int v54; // ecx
  unsigned int v55; // eax
  unsigned int v56; // r13d
  __int64 v57; // rdi
  PSLIST_ENTRY v58; // r11
  unsigned int v59; // r10d
  int v60; // r9d
  signed __int16 v61; // r8
  __int64 v62; // r8
  unsigned int v63; // ecx
  unsigned int v64; // edx
  __int64 v65; // rax
  __int64 v66; // rax
  __int64 v67; // rax
  _DWORD *v68; // rcx
  LARGE_INTEGER PerformanceCounter; // rax
  _OWORD *v70; // rdx
  _OWORD *v71; // rcx
  char v72; // r8
  __int64 v73; // rax
  unsigned __int64 v74; // r9
  int v75; // edx
  __int64 v76; // rcx
  __int16 v77; // r12
  __int64 v78; // rdx
  unsigned int v79; // r8d
  __int64 v80; // rcx
  __int64 v81; // rdx
  __int64 v82; // r14
  signed __int32 v83; // edi
  _QWORD *v84; // rcx
  _BYTE *v85; // r8
  __int64 v86; // rax
  signed __int32 v88[6]; // [rsp+8h] [rbp-100h] BYREF
  KIRQL v89; // [rsp+48h] [rbp-C0h]
  char v90; // [rsp+49h] [rbp-BFh]
  unsigned int v91; // [rsp+4Ch] [rbp-BCh]
  __int64 v92; // [rsp+50h] [rbp-B8h] BYREF
  _BYTE *v93; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v94; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v95; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v96; // [rsp+70h] [rbp-98h] BYREF
  __int64 v97; // [rsp+78h] [rbp-90h] BYREF
  __int64 v98; // [rsp+80h] [rbp-88h] BYREF
  __int64 v99; // [rsp+88h] [rbp-80h] BYREF
  GUID ActivityId; // [rsp+90h] [rbp-78h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+B0h] [rbp-58h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+C8h] [rbp-40h] BYREF
  _BYTE *v103; // [rsp+D8h] [rbp-30h]
  __int64 v104; // [rsp+E0h] [rbp-28h]
  const wchar_t *v105; // [rsp+E8h] [rbp-20h]
  int v106; // [rsp+F0h] [rbp-18h]
  int v107; // [rsp+F4h] [rbp-14h]
  const int *v108; // [rsp+F8h] [rbp-10h]
  int v109; // [rsp+100h] [rbp-8h]
  int v110; // [rsp+104h] [rbp-4h]
  char *v111; // [rsp+108h] [rbp+0h]
  __int64 v112; // [rsp+110h] [rbp+8h]
  _BYTE **v113; // [rsp+118h] [rbp+10h]
  __int64 v114; // [rsp+120h] [rbp+18h]
  const int *v115; // [rsp+128h] [rbp+20h]
  int v116; // [rsp+130h] [rbp+28h]
  int v117; // [rsp+134h] [rbp+2Ch]
  _BYTE **v118; // [rsp+138h] [rbp+30h]
  int v119; // [rsp+140h] [rbp+38h]
  int v120; // [rsp+144h] [rbp+3Ch]
  char *v121; // [rsp+148h] [rbp+40h]
  int v122; // [rsp+150h] [rbp+48h]
  int v123; // [rsp+154h] [rbp+4Ch]
  const wchar_t *v124; // [rsp+158h] [rbp+50h]
  __int64 v125; // [rsp+160h] [rbp+58h]
  const wchar_t *v126; // [rsp+168h] [rbp+60h]
  __int64 v127; // [rsp+170h] [rbp+68h]
  _BYTE **v128; // [rsp+178h] [rbp+70h]
  __int64 v129; // [rsp+180h] [rbp+78h]
  const wchar_t *v130; // [rsp+188h] [rbp+80h]
  __int64 v131; // [rsp+190h] [rbp+88h]
  __int64 *v132; // [rsp+198h] [rbp+90h]
  __int64 v133; // [rsp+1A0h] [rbp+98h]
  const wchar_t *v134; // [rsp+1A8h] [rbp+A0h]
  __int64 v135; // [rsp+1B0h] [rbp+A8h]
  __int64 *v136; // [rsp+1B8h] [rbp+B0h]
  __int64 v137; // [rsp+1C0h] [rbp+B8h]
  const wchar_t *v138; // [rsp+1C8h] [rbp+C0h]
  __int64 v139; // [rsp+1D0h] [rbp+C8h]
  __int64 *v140; // [rsp+1D8h] [rbp+D0h]
  __int64 v141; // [rsp+1E0h] [rbp+D8h]
  const wchar_t *v142; // [rsp+1E8h] [rbp+E0h]
  __int64 v143; // [rsp+1F0h] [rbp+E8h]
  __int64 *v144; // [rsp+1F8h] [rbp+F0h]
  __int64 v145; // [rsp+200h] [rbp+F8h]
  const wchar_t *v146; // [rsp+208h] [rbp+100h]
  __int64 v147; // [rsp+210h] [rbp+108h]
  __int64 *v148; // [rsp+218h] [rbp+110h]
  __int64 v149; // [rsp+220h] [rbp+118h]
  const wchar_t *v150; // [rsp+228h] [rbp+120h]
  __int64 v151; // [rsp+230h] [rbp+128h]
  __int64 *v152; // [rsp+238h] [rbp+130h]
  __int64 v153; // [rsp+240h] [rbp+138h]
  const wchar_t *v154; // [rsp+248h] [rbp+140h]
  __int64 v155; // [rsp+250h] [rbp+148h]
  __int64 *v156; // [rsp+258h] [rbp+150h]
  __int64 v157; // [rsp+260h] [rbp+158h]

  v5 = (_BYTE **)SystemArgument2;
  v90 = SystemArgument2[1728];
  v7 = *((_DWORD *)a2 + 16);
  v8 = a4;
  v93 = SystemArgument2;
  LODWORD(v95) = v7;
  v91 = a4;
  v89 = KfRaiseIrql(2u);
  _InterlockedIncrement((volatile signed __int32 *)(a3 + 128));
  if ( **(_QWORD **)(*(_QWORD *)(a3 + 88) + 1312LL) == 1 )
  {
    _InterlockedDecrement((volatile signed __int32 *)(a3 + 128));
    v10 = *a2;
    v11 = *(_QWORD *)(a3 + 88);
    if ( *a2 && *(_QWORD *)(v10 + 4184) && (*(_DWORD *)(v10 + 4256) & 0x10000) == 0 )
    {
      v12 = *(_QWORD *)(*(_QWORD *)(*a2 + 4184) + 184LL);
      *(_BYTE *)(v12 + 3) |= 1u;
    }
    if ( (*(_DWORD *)(*a2 + 4256) & 0x100) != 0 )
    {
      NvmeControllerProcessIsolatedCommandAsync((PVOID)v11);
LABEL_12:
      v14 = -2147483631;
      KeLowerIrql(v89);
      goto LABEL_146;
    }
    goto LABEL_8;
  }
  if ( a5 )
  {
    v15 = *(_DWORD *)(a3 + 124);
    HIBYTE(v16) = 0;
    while ( 1 )
    {
      v17 = *(unsigned __int16 *)(a3 + 142);
      v18 = 0;
      if ( (unsigned __int16)(v17 + 1) < v15 )
        v18 = v17 + 1;
      if ( v18 == *(_WORD *)(a3 + 140) )
        break;
      if ( _InterlockedCompareExchange16((volatile signed __int16 *)(a3 + 142), v18, v17) == v17 )
      {
        Next_high = *a5;
        goto LABEL_20;
      }
    }
    _InterlockedDecrement((volatile signed __int32 *)(a3 + 128));
    DepthSList = ExQueryDepthSList((PSLIST_HEADER)(a3 + 64));
    v28 = ((_BYTE)v5[17] & 2) == 0;
    v29 = 0x800000000002000LL;
    v30 = v5[16];
    v96 = DepthSList;
    v99 = *((unsigned int *)v5 + 2);
    v98 = *((unsigned __int16 *)v5 + 13);
    v92 = *((unsigned __int16 *)v5 + 11);
    v95 = *a5;
    v97 = *(unsigned __int16 *)(a3 + 142);
    v94 = *(unsigned __int16 *)(a3 + 140);
    v93 = (_BYTE *)*(unsigned __int16 *)(a3 + 136);
    *(_QWORD *)&EventDescriptor.Id = EventNVMeControllerError;
    if ( !v28 )
      v29 = 0x80000000000A000LL;
    EventDescriptor.Keyword = v29;
    ActivityId = 0;
    v31 = *((_QWORD *)v30 + 2);
    v32 = *(const wchar_t **)(v31 + 48);
    if ( v32 )
    {
      v33 = *(unsigned __int16 *)(v31 + 40);
      if ( (_WORD)v33 )
      {
        LODWORD(v34) = v33 >> 1;
        if ( v33 >> 1 )
        {
          while ( 1 )
          {
            v34 = (unsigned int)(v34 - 1);
            v35 = &v32[v34];
            if ( *v35 == 92 )
              break;
            if ( !(_DWORD)v34 )
              goto LABEL_32;
          }
          if ( v35 )
            v32 = v35 + 1;
        }
      }
    }
LABEL_32:
    *(_QWORD *)&UserData.Size = 4;
    UserData.Ptr = (unsigned __int64)(v30 + 56);
    v103 = v30 + 1048;
    v104 = 16;
    if ( v32 )
    {
      v36 = -1;
      do
        v28 = v32[++v36] == 0;
      while ( !v28 );
      v37 = 2 * v36 + 2;
    }
    else
    {
      v37 = 10;
      v32 = L"NULL";
    }
    v105 = v32;
    v38 = &dword_140157D94;
    v39 = (const int *)v5[99];
    v106 = v37;
    v107 = 0;
    if ( v39 )
    {
      v40 = -1;
      do
        ++v40;
      while ( *((_BYTE *)v39 + v40) );
      v41 = v40 + 1;
    }
    else
    {
      v41 = 1;
      v39 = &dword_140157D94;
    }
    v109 = v41;
    v111 = (char *)v5 + 4;
    v113 = v5 + 93;
    v42 = (const int *)v5[94];
    v108 = v39;
    v110 = 0;
    if ( v42 )
      v38 = v42;
    v112 = 2;
    v43 = -1;
    v114 = 1;
    do
      ++v43;
    while ( *((_BYTE *)v38 + v43) );
    v115 = v38;
    v116 = v43 + 1;
    v118 = v5 + 100;
    v44 = -1;
    v117 = 0;
    do
      ++v44;
    while ( *((_BYTE *)v5 + v44 + 800) );
    v120 = 0;
    v119 = v44 + 1;
    v45 = -1;
    v121 = (char *)v5 + 841;
    do
      ++v45;
    while ( *((_BYTE *)v5 + v45 + 841) );
    v123 = 0;
    v122 = v45 + 1;
    v125 = 102;
    v124 = L"Failed to get free slot for non-read/write command";
    v127 = 12;
    v126 = L"SQ ID";
    v128 = &v93;
    v130 = L"SQ head";
    v132 = &v94;
    v134 = L"SQ tail";
    v136 = &v97;
    v138 = L"Command ID";
    v140 = &v95;
    v142 = L"IO SQ count";
    v144 = &v92;
    v146 = L"IO CQ count";
    v148 = &v98;
    v150 = L"Queue depth";
    v152 = &v99;
    v154 = L"Free command ID count";
    v156 = &v96;
    v129 = 8;
    v131 = 16;
    v133 = 8;
    v135 = 16;
    v137 = 8;
    v139 = 22;
    v141 = 8;
    v143 = 24;
    v145 = 8;
    v147 = 24;
    v149 = 8;
    v151 = 24;
    v153 = 8;
    v155 = 44;
    v157 = 8;
    EtwWriteEx(StorPortEventProvider_Context, &EventDescriptor, 0, 1u, &ActivityId, 0, 0x1Au, &UserData);
    v14 = -1073741595;
    v46 = *(_DWORD *)(*a2 + 4256) >> 11;
    LOBYTE(v46) = (*(_DWORD *)(*a2 + 4256) & 0x800) == 0;
    LODWORD(v92) = v46;
    goto LABEL_142;
  }
  v47 = *(_DWORD *)(a3 + 124);
  v48 = (union _SLIST_HEADER *)(a3 + 64);
  if ( (*(_DWORD *)(*a2 + 4256) & 1) != 0 )
  {
    v49 = ExpInterlockedPopEntrySList(v48);
    if ( v49 )
    {
      _InterlockedOr(v88, 0);
      HIBYTE(v16) = 0;
      while ( 1 )
      {
        v17 = *(unsigned __int16 *)(a3 + 142);
        v50 = 0;
        if ( (unsigned __int16)(v17 + 1) < v47 )
          v50 = v17 + 1;
        if ( v50 == *(_WORD *)(a3 + 140) )
          break;
        if ( _InterlockedCompareExchange16((volatile signed __int16 *)(a3 + 142), v50, v17) == v17 )
        {
          Next_high = HIWORD(v49[3].Next);
          v18 = v50;
          goto LABEL_20;
        }
      }
      ExpInterlockedPushEntrySList((PSLIST_HEADER)(a3 + 64), v49);
    }
    _InterlockedDecrement((volatile signed __int32 *)(a3 + 128));
LABEL_85:
    v65 = *a2;
    v11 = *(_QWORD *)(a3 + 88);
    if ( *a2 && *(_QWORD *)(v65 + 4184) && (*(_DWORD *)(v65 + 4256) & 0x10000) == 0 )
    {
      v66 = *(_QWORD *)(*(_QWORD *)(*a2 + 4184) + 184LL);
      *(_BYTE *)(v66 + 3) |= 1u;
    }
    if ( (*(_DWORD *)(*a2 + 4256) & 0x100) != 0 )
    {
      NvmeControllerProcessIsolatedCommandAsync((PVOID)v11);
      goto LABEL_12;
    }
    v8 = v91;
LABEL_8:
    v13 = *(_DWORD *)(*a2 + 4256) & 1;
    StorPushRequestToDeviceQueue(*(_QWORD *)(v11 + 1024), (unsigned int)v8, a2);
    _InterlockedOr(v88, 0);
    if ( !_InterlockedCompareExchange(*(volatile signed __int32 **)(*(_QWORD *)(v11 + 1024) + 8 * v8 + 64), 1, 0) )
      _InterlockedIncrement((volatile signed __int32 *)(v11 + 956));
    if ( !v13 )
      _InterlockedIncrement((volatile signed __int32 *)(v11 + 960));
    goto LABEL_12;
  }
  HIBYTE(v16) = 0;
  v51 = ExpInterlockedPopEntrySList(v48);
  if ( v51 )
  {
    _InterlockedOr(v88, 0);
    while ( 1 )
    {
      v17 = *(unsigned __int16 *)(a3 + 142);
      v52 = 0;
      if ( (unsigned __int16)(v17 + 1) < v47 )
        v52 = v17 + 1;
      if ( v52 == *(_WORD *)(a3 + 140) )
        break;
      if ( _InterlockedCompareExchange16((volatile signed __int16 *)(a3 + 142), v52, v17) == v17 )
      {
        Next_high = HIWORD(v51[3].Next);
        v18 = v52;
        v53 = 1;
        goto LABEL_84;
      }
    }
    ExpInterlockedPushEntrySList((PSLIST_HEADER)(a3 + 64), v51);
  }
  LODWORD(v92) = 0;
  LOWORD(v17) = 0;
  _InterlockedDecrement((volatile signed __int32 *)(a3 + 128));
  v18 = 0;
  Next_high = 0;
  v96 = *(_QWORD *)(a3 + 88);
  v54 = *(unsigned __int16 *)(v96 + 22);
  if ( v54 != 1 )
  {
    v55 = *(unsigned __int16 *)(a3 + 136);
    LODWORD(v94) = v55 - 1;
    v56 = v55 % v54;
    if ( v55 % v54 < v54 )
    {
      do
      {
        v57 = *(_QWORD *)(*(_QWORD *)(a3 + 88) + 728LL) + 192LL * v56;
        _InterlockedIncrement((volatile signed __int32 *)(v57 + 128));
        LODWORD(v97) = *(_DWORD *)(v57 + 124);
        v58 = ExpInterlockedPopEntrySList((PSLIST_HEADER)(v57 + 64));
        if ( v58 )
        {
          _InterlockedOr(v88, 0);
          v59 = v97;
          while ( 1 )
          {
            v60 = *(unsigned __int16 *)(v57 + 142);
            v61 = 0;
            if ( (unsigned __int16)(v60 + 1) < v59 )
              v61 = v60 + 1;
            if ( v61 == *(_WORD *)(v57 + 140) )
              break;
            if ( _InterlockedCompareExchange16((volatile signed __int16 *)(v57 + 142), v61, v60) == v60 )
            {
              a3 = v57;
              v5 = (_BYTE **)v93;
              LOWORD(v17) = v60;
              LODWORD(v92) = HIWORD(v58[3].Next);
              v18 = v61;
              Next_high = v92;
              v53 = 1;
              goto LABEL_84;
            }
          }
          ExpInterlockedPushEntrySList((PSLIST_HEADER)(v57 + 64), v58);
        }
        v62 = v96;
        v63 = *(unsigned __int16 *)(v96 + 22);
        _InterlockedDecrement((volatile signed __int32 *)(v57 + 128));
        v64 = (v56 + 1) % v63;
        v56 = v64;
      }
      while ( v64 != (_DWORD)v94 && v64 < *(unsigned __int16 *)(v62 + 22) );
      Next_high = v92;
    }
    v5 = (_BYTE **)v93;
  }
  v53 = 0;
LABEL_84:
  if ( !v53 )
    goto LABEL_85;
LABEL_20:
  v20 = *a2;
  v21 = v91;
  LODWORD(v95) = v95 & 4;
  *((_DWORD *)a2 + 20) = v91;
  v22 = *(_QWORD *)(v20 + 4184);
  v23 = *(_QWORD *)(a3 + 32);
  LOWORD(v20) = *((_WORD *)a2 + 34);
  v24 = (unsigned __int64)Next_high << 7;
  LOBYTE(v92) = 0;
  v96 = v22;
  *(_WORD *)(v23 + v24 + 58) = v20;
  v25 = *(_QWORD *)(*a2 + 4216);
  if ( v25 )
    v26 = *(_DWORD *)(v25 + 56);
  else
    v26 = 0;
  *(_DWORD *)(*(_QWORD *)(a3 + 32) + v24 + 88) = v26;
  *(_QWORD *)(*(_QWORD *)(a3 + 32) + v24 + 64) = **(_QWORD **)(*(_QWORD *)(*(_QWORD *)(a3 + 88) + 1312LL) + 40LL);
  _interlockedbittestandset((volatile signed __int32 *)(*a2 + 4256), 3u);
  *(_DWORD *)(*a2 + 4268) = 0;
  *(_QWORD *)(*(_QWORD *)(a3 + 32) + v24 + 24) = v22;
  *(_WORD *)(*(_QWORD *)(a3 + 32) + v24 + 56) = v17;
  *(_QWORD *)(*(_QWORD *)(a3 + 32) + v24 + 16) = 0;
  *(_WORD *)(*(_QWORD *)(a3 + 32) + v24 + 52) = v21;
  *(_DWORD *)(*(_QWORD *)(a3 + 32) + v24 + 48) = *(_DWORD *)(*a2 + 4248);
  *(_QWORD *)(*(_QWORD *)(a3 + 32) + v24 + 40) = 0;
  *(_QWORD *)(*(_QWORD *)(a3 + 32) + v24 + 32) = *(_QWORD *)(*a2 + 4192);
  *(_QWORD *)(*(_QWORD *)(a3 + 32) + v24 + 40) = *(_QWORD *)(*a2 + 4200);
  *(_BYTE *)(*(_QWORD *)(a3 + 32) + v24 + 60) = 0;
  *(_BYTE *)(*(_QWORD *)(a3 + 32) + v24 + 61) = 0;
  *(_BYTE *)(*(_QWORD *)(a3 + 32) + v24 + 60) |= 2u;
  if ( (*(_DWORD *)(*a2 + 4256) & 0x40) != 0 )
    *(_BYTE *)(*(_QWORD *)(a3 + 32) + v24 + 60) |= 0x10u;
  if ( (*(_DWORD *)(*a2 + 4256) & 0x100) != 0 )
    *(_BYTE *)(*(_QWORD *)(a3 + 32) + v24 + 60) |= 0x20u;
  if ( (*(_DWORD *)(*a2 + 4256) & 0x800) == 0 )
  {
    if ( (*(_DWORD *)(*a2 + 4256) & 0x1000) != 0 )
    {
      LOBYTE(v92) = 1;
    }
    else
    {
      *(_QWORD *)(*(_QWORD *)(a3 + 32) + v24 + 80) = a2;
      *(_BYTE *)(*(_QWORD *)(a3 + 32) + v24 + 61) |= 1u;
    }
  }
  v67 = *(_QWORD *)(a3 + 32);
  if ( !*(_WORD *)(v67 + v24 + 58) )
    *(_BYTE *)(*(_QWORD *)(a3 + 32) + v24 + 60) = *(_BYTE *)(v67 + v24 + 60) | 0x40;
  if ( (*(_DWORD *)(*a2 + 4256) & 0x10000) != 0 )
    *(_BYTE *)(*(_QWORD *)(a3 + 32) + v24 + 61) |= 2u;
  v28 = UseQPCTime == 0;
  v68 = (_DWORD *)*a2;
  *((_WORD *)a2 + 35) = *(_WORD *)(a3 + 136);
  *((_DWORD *)a2 + 21) = v68[1024];
  *((_DWORD *)a2 + 22) = v68[1034];
  *((_DWORD *)a2 + 23) = v68[1035];
  if ( v28 )
    PerformanceCounter.QuadPart = KeQueryUnbiasedInterruptTime();
  else
    PerformanceCounter = KeQueryPerformanceCounter(0);
  a2[12] = PerformanceCounter.QuadPart;
  *(_BYTE *)(*(_QWORD *)(a3 + 32) + v24 + 60) |= 4u;
  *(_WORD *)(*a2 + 4098) = Next_high;
  v70 = (_OWORD *)*a2;
  v71 = *(_OWORD **)(*(_QWORD *)(a3 + 24) + 16LL * (unsigned __int16)v17);
  *v71 = *(_OWORD *)(*a2 + 4096);
  v71[1] = v70[257];
  v71[2] = v70[258];
  v71[3] = v70[259];
  *(_WORD *)(*(_QWORD *)(a3 + 24) + 16LL * (unsigned __int16)v17 + 8) = Next_high;
  v72 = v90;
  if ( v90 == 1 )
  {
    v73 = *(_QWORD *)(a3 + 56);
    if ( v73 )
    {
      v74 = (unsigned __int64)(unsigned __int16)v17 << 6;
      *(_OWORD *)(v73 + v74) = 0;
      *(_OWORD *)(v73 + v74 + 16) = 0;
      *(_OWORD *)(v73 + v74 + 32) = 0;
      *(_OWORD *)(v73 + v74 + 48) = 0;
      *(_DWORD *)(v74 + *(_QWORD *)(a3 + 56)) = 1;
      *(_DWORD *)(v74 + *(_QWORD *)(a3 + 56) + 8) = *(unsigned __int16 *)(a3 + 136);
      *(_DWORD *)(v74 + *(_QWORD *)(a3 + 56) + 12) = (unsigned __int16)v17;
      *(_QWORD *)(v74 + *(_QWORD *)(a3 + 56) + 16) = *(_QWORD *)(*a2 + 4160);
    }
  }
  if ( v96 && (*(_DWORD *)(*a2 + 4256) & 0x10000) == 0 )
    *(_BYTE *)(*(_QWORD *)(v96 + 184) + 3LL) |= 1u;
  _InterlockedOr(v88, 0);
  v75 = 0;
  _interlockedbittestandset((volatile signed __int32 *)(*a2 + 4256), 0xEu);
  *(_BYTE *)(*(_QWORD *)(a3 + 32) + v24 + 60) |= 1u;
  _InterlockedDecrement((volatile signed __int32 *)(a3 + 128));
  if ( (unsigned __int16)(v17 + 1) != *(_DWORD *)(a3 + 124) )
    v75 = (unsigned __int16)(v17 + 1);
  if ( (_DWORD)v95 && (_BYTE)v92 )
    _InterlockedDecrement16((volatile signed __int16 *)(*a2 + 4264));
  _InterlockedOr(v88, 0);
  if ( *(_WORD *)(a3 + 142) == v18 )
  {
    while ( _InterlockedCompareExchange((volatile signed __int32 *)(a3 + 132), 1, 0) )
    {
      if ( *(_WORD *)(a3 + 142) != v18 )
        goto LABEL_122;
    }
    while ( *(_DWORD *)(a3 + 128) )
      _InterlockedOr(v88, 0);
    if ( *(_WORD *)(a3 + 142) == v18 )
    {
      if ( v72 == 1 )
      {
        v5 = (_BYTE **)v93;
        LODWORD(v94) = v75;
        (*(void (__fastcall **)(__int64, _QWORD, __int64, _QWORD, __int64 *))(*((_QWORD *)v93 + 16) + 536LL))(
          *((_QWORD *)v93 + 206) + 64LL,
          *(unsigned int *)(a3 + 16),
          4,
          0,
          &v94);
LABEL_130:
        _InterlockedOr(v88, 0);
        _InterlockedExchange((volatile __int32 *)(a3 + 132), 0);
        if ( ((_BYTE)v5[173] & 4) != 0 )
        {
          v28 = *(_DWORD *)v5 == 1314276178;
          v76 = *a2;
          v77 = *(_WORD *)(a3 + 136);
          HIWORD(ActivityId.Data1) = *(_WORD *)(a3 + 138);
          *(_QWORD *)ActivityId.Data4 = *(_QWORD *)(v76 + 4184);
          *(_DWORD *)&ActivityId.Data2 = *(_DWORD *)(v76 + 4096);
          LOWORD(ActivityId.Data1) = v77;
          if ( v28 )
          {
            v78 = *(_QWORD *)&v5[174][8 * KeGetCurrentProcessorNumberEx(0)];
            v79 = *(_DWORD *)(v78 + 12);
            _InterlockedOr(v88, 0);
            if ( v79 )
            {
              v80 = v78 + 64;
              if ( v78 != -64 )
              {
                v81 = _InterlockedIncrement((volatile signed __int32 *)v78) % v79;
                v82 = v80 + ((unsigned __int64)(unsigned int)v81 << 6);
                if ( ((_DWORD)v5[170] & 1) != 0 )
                  v83 = _InterlockedIncrement((volatile signed __int32 *)v5 + 352);
                else
                  v83 = v81;
                *(_DWORD *)(v82 + 4) = v83;
                v84 = (_QWORD *)(v82 + 8);
                *(_WORD *)v82 = 0;
                LOBYTE(v16) = v77 != 0;
                *(_WORD *)(v82 + 2) = v16;
                if ( ((_DWORD)v5[170] & 2) != 0 )
                  KeQuerySystemTimePrecise(v84, v81);
                else
                  *v84 = MEMORY[0xFFFFF78000000014];
                *(GUID *)(v82 + 16) = ActivityId;
                *(_OWORD *)(v82 + 32) = 0;
              }
            }
          }
        }
        goto LABEL_141;
      }
      **(_DWORD **)(a3 + 16) = v75;
      _InterlockedOr(v88, 0);
    }
    v5 = (_BYTE **)v93;
    goto LABEL_130;
  }
LABEL_122:
  v5 = (_BYTE **)v93;
LABEL_141:
  v14 = 259;
LABEL_142:
  KeLowerIrql(v89);
  if ( (_BYTE)v92 )
  {
    v85 = v5[16];
    v86 = *((_QWORD *)v85 + 21);
    if ( *(_BYTE *)v86 == 1
      && _InterlockedExchangeAdd(*(volatile signed __int32 **)(*(_QWORD *)(v86 + 16) + 8LL * v91), 0xFFFFFFFF) == 1 )
    {
      PoFxIdleComponent(**(_QWORD **)(*((_QWORD *)v85 + 21) + 8LL), 0, 2);
    }
  }
LABEL_146:
  if ( *v5[217] && *(_WORD *)(a3 + 136) )
    NvmeStartIoPolling(v5);
  return v14;
}

```

## disassembly

```asm
0x140062dd0  mov     r11, rsp
0x140062dd3  push    rbp
0x140062dd4  push    rbx
0x140062dd5  push    rdi
0x140062dd6  push    r12
0x140062dd8  push    r13
0x140062dda  lea     rbp, [r11-218h]
0x140062de1  sub     rsp, 2F0h
0x140062de8  mov     rax, cs:__security_cookie
0x140062def  xor     rax, rsp
0x140062df2  mov     [rbp+210h+var_60], rax
0x140062df9  movzx   eax, byte ptr [rcx+6C0h]
0x140062e00  mov     r13, rcx
0x140062e03  mov     rdi, [rbp+210h+arg_20]
0x140062e0a  mov     rbx, r8
0x140062e0d  mov     [r11-30h], rsi
0x140062e11  mov     byte ptr [rsp+310h+var_2D0+1], al
0x140062e15  mov     eax, [rdx+40h]
0x140062e18  mov     [r11-38h], r14
0x140062e1c  mov     r12d, r9d
0x140062e1f  mov     [rsp+310h+var_2C0], rcx
0x140062e24  mov     cl, 2; NewIrql
0x140062e26  mov     [r11-40h], r15
0x140062e2a  mov     r15, rdx
0x140062e2d  mov     dword ptr [rsp+310h+var_2B0], eax
0x140062e31  mov     dword ptr [rsp+310h+var_2D0+4], r12d
0x140062e36  call    cs:__imp_KfRaiseIrql
0x140062e3d  nop     dword ptr [rax+rax+00h]
0x140062e42  mov     byte ptr [rsp+310h+var_2D0], al
0x140062e46  lock inc dword ptr [rbx+80h]
0x140062e4d  mov     rcx, [rbx+58h]
0x140062e51  mov     rdx, [rcx+520h]
0x140062e58  mov     ecx, [rdx]
0x140062e5a  cmp     ecx, 1
0x140062e5d  jnz     loc_140062F3F
0x140062e63  mov     rcx, [rbx+58h]
0x140062e67  mov     rdx, [rcx+520h]
0x140062e6e  mov     ecx, [rdx+4]
0x140062e71  test    ecx, ecx
0x140062e73  jnz     loc_140062F3F
0x140062e79  lock dec dword ptr [rbx+80h]
0x140062e80  mov     rax, [r15]
0x140062e83  mov     rsi, [rbx+58h]
0x140062e87  test    rax, rax
0x140062e8a  jz      short loc_140062EB7
0x140062e8c  cmp     qword ptr [rax+1058h], 0
0x140062e94  jz      short loc_140062EB7
0x140062e96  mov     eax, [rax+10A0h]
0x140062e9c  bt      eax, 10h
0x140062ea0  jb      short loc_140062EB7
0x140062ea2  mov     rax, [r15]
0x140062ea5  mov     rcx, [rax+1058h]
0x140062eac  mov     rax, [rcx+0B8h]
0x140062eb3  or      byte ptr [rax+3], 1
0x140062eb7  mov     rax, [r15]
0x140062eba  mov     ecx, [rax+10A0h]
0x140062ec0  bt      ecx, 8
0x140062ec4  jnb     short loc_140062ED3
0x140062ec6  mov     rdx, r15
0x140062ec9  mov     rcx, rsi; Context
0x140062ecc  call    NvmeControllerProcessIsolatedCommandAsync
0x140062ed1  jmp     short loc_140062F24
0x140062ed3  mov     rax, [r15]
0x140062ed6  mov     r8, r15
0x140062ed9  mov     edx, r12d
0x140062edc  mov     r14d, [rax+10A0h]
0x140062ee3  mov     rcx, [rsi+400h]
0x140062eea  and     r14b, 1
0x140062eee  call    StorPushRequestToDeviceQueue
0x140062ef3  lock or dword ptr [rsp+0], 0
0x140062ef8  mov     rcx, [rsi+400h]
0x140062eff  xor     eax, eax
0x140062f01  mov     edi, 1
0x140062f06  mov     rcx, [rcx+r12*8+40h]
0x140062f0b  lock cmpxchg [rcx], edi
0x140062f0f  jnz     short loc_140062F18
0x140062f11  lock inc dword ptr [rsi+3BCh]
0x140062f18  test    r14b, r14b
0x140062f1b  jnz     short loc_140062F24
0x140062f1d  lock inc dword ptr [rsi+3C0h]
0x140062f24  movzx   ecx, byte ptr [rsp+310h+var_2D0]; NewIrql
0x140062f29  mov     edi, 80000011h
0x140062f2e  call    cs:__imp_KeLowerIrql
0x140062f35  nop     dword ptr [rax+rax+00h]
0x140062f3a  jmp     loc_140063C0E
0x140062f3f  test    rdi, rdi
0x140062f42  jz      loc_1400633C6
0x140062f48  mov     edx, [rbx+7Ch]
0x140062f4b  xor     esi, esi
0x140062f4d  nop     dword ptr [rax]
0x140062f50  movzx   r14d, word ptr [rbx+8Eh]
0x140062f58  mov     r12d, esi
0x140062f5b  lea     eax, [r14+1]
0x140062f5f  movzx   ecx, ax
0x140062f62  cmp     ecx, edx
0x140062f64  cmovb   r12w, cx
0x140062f69  cmp     r12w, [rbx+8Ch]
0x140062f71  jz      short loc_140062FE4
0x140062f73  movzx   eax, r14w
0x140062f77  lock cmpxchg [rbx+8Eh], r12w
0x140062f81  movsx   ecx, ax
0x140062f84  cmp     ecx, r14d
0x140062f87  jnz     short loc_140062F50
0x140062f89  movzx   edi, word ptr [rdi]
0x140062f8c  mov     rax, [r15]
0x140062f8f  mov     r9d, dword ptr [rsp+310h+var_2D0+4]
0x140062f94  and     dword ptr [rsp+310h+var_2B0], 4
0x140062f99  mov     [r15+50h], r9d
0x140062f9d  mov     r8, [rax+1058h]
0x140062fa4  mov     rcx, [rbx+20h]
0x140062fa8  movzx   eax, word ptr [r15+44h]
0x140062fad  movzx   r13d, di
0x140062fb1  shl     r13, 7
0x140062fb5  mov     byte ptr [rsp+310h+var_2C8], 0
0x140062fba  mov     [rsp+310h+var_2A8], r8
0x140062fbf  mov     [rcx+r13+3Ah], ax
0x140062fc5  mov     rax, [r15]
0x140062fc8  mov     rcx, [rbx+20h]
0x140062fcc  mov     rdx, [rax+1078h]
0x140062fd3  test    rdx, rdx
0x140062fd6  jz      loc_140063688
0x140062fdc  mov     eax, [rdx+38h]
0x140062fdf  jmp     loc_14006368A
0x140062fe4  lock dec dword ptr [rbx+80h]
0x140062feb  lea     rcx, [rbx+40h]; SListHead
0x140062fef  call    cs:__imp_ExQueryDepthSList
0x140062ff6  nop     dword ptr [rax+rax+00h]
0x140062ffb  test    byte ptr [r13+88h], 2
0x140063003  mov     rcx, 800000000002000h
0x14006300d  mov     r9, [r13+80h]
0x140063014  xorps   xmm0, xmm0
0x140063017  movzx   eax, ax
0x14006301a  mov     [rsp+310h+var_2A8], rax
0x14006301f  mov     eax, [r13+8]
0x140063023  mov     [rbp+210h+var_290], rax
0x140063027  movzx   eax, word ptr [r13+1Ah]
0x14006302c  mov     [rsp+310h+var_298], rax
0x140063031  movzx   eax, word ptr [r13+16h]
0x140063036  mov     [rsp+310h+var_2C8], rax
0x14006303b  movzx   eax, word ptr [rdi]
0x14006303e  mov     [rsp+310h+var_2B0], rax
0x140063043  movzx   eax, word ptr [rbx+8Eh]
0x14006304a  mov     [rsp+310h+var_2A0], rax
0x14006304f  movzx   eax, word ptr [rbx+8Ch]
0x140063056  mov     [rsp+310h+var_2B8], rax
0x14006305b  movzx   eax, word ptr [rbx+88h]
0x140063062  mov     [rsp+310h+var_2C0], rax
0x140063067  mov     rax, cs:EventNVMeControllerError
0x14006306e  mov     qword ptr [rbp+210h+EventDescriptor.Id], rax
0x140063072  mov     rax, 80000000000A000h
0x14006307c  cmovnz  rcx, rax
0x140063080  mov     [rbp+210h+EventDescriptor.Keyword], rcx
0x140063084  movups  xmmword ptr [rbp+210h+var_288.Data1], xmm0
0x140063088  mov     rax, [r9+10h]
0x14006308c  mov     rdx, [rax+30h]
0x140063090  test    rdx, rdx
0x140063093  jz      short loc_1400630CC
0x140063095  movzx   eax, word ptr [rax+28h]
0x140063099  test    ax, ax
0x14006309c  jz      short loc_1400630CC
0x14006309e  mov     ecx, eax
0x1400630a0  shr     ecx, 1
0x1400630a2  jz      short loc_1400630CC
0x1400630a4  nop     dword ptr [rax+00h]
0x1400630a8  nop     dword ptr [rax+rax+00000000h]
0x1400630b0  dec     ecx
0x1400630b2  cmp     word ptr [rdx+rcx*2], 5Ch ; '\'
0x1400630b7  lea     r8, [rdx+rcx*2]
0x1400630bb  jz      short loc_1400630C3
0x1400630bd  test    ecx, ecx
0x1400630bf  jnz     short loc_1400630B0
0x1400630c1  jmp     short loc_1400630CC
0x1400630c3  test    r8, r8
0x1400630c6  jz      short loc_1400630CC
0x1400630c8  lea     rdx, [r8+2]
0x1400630cc  mov     qword ptr [rbp+210h+var_250.Size], 4
0x1400630d4  lea     rax, [r9+38h]
0x1400630d8  mov     [rbp+210h+var_250.Ptr], rax
0x1400630dc  lea     rax, [r9+418h]
0x1400630e3  mov     [rbp+210h+var_240], rax
0x1400630e7  mov     r14, 0FFFFFFFFFFFFFFFFh
0x1400630ee  mov     [rbp+210h+var_238], 10h
0x1400630f6  test    rdx, rdx
0x1400630f9  jz      short loc_140063114
0x1400630fb  mov     rax, r14
0x1400630fe  xchg    ax, ax
0x140063100  cmp     [rdx+rax*2+2], si
0x140063105  lea     rax, [rax+1]
0x140063109  jnz     short loc_140063100
0x14006310b  lea     eax, ds:2[rax*2]
0x140063112  jmp     short loc_140063120
0x140063114  mov     eax, 0Ah
0x140063119  lea     rdx, aNull_0; "NULL"
0x140063120  mov     [rbp+210h+var_230], rdx
0x140063124  lea     rcx, dword_140157D94
0x14006312b  mov     rdx, [r13+318h]
0x140063132  mov     edi, 1
0x140063137  mov     [rbp+210h+var_228], eax
0x14006313a  mov     [rbp+210h+var_224], esi
0x14006313d  test    rdx, rdx
0x140063140  jz      short loc_140063153
0x140063142  mov     rax, r14
0x140063145  inc     rax
0x140063148  cmp     [rdx+rax], sil
0x14006314c  jnz     short loc_140063145
0x14006314e  inc     rax
0x140063151  jmp     short loc_140063159
0x140063153  mov     rax, rdi
0x140063156  mov     rdx, rcx
0x140063159  mov     [rbp+210h+var_218], eax
0x14006315c  lea     rax, [r13+4]
0x140063160  mov     [rbp+210h+var_210], rax
0x140063164  lea     rax, [r13+2E8h]
0x14006316b  mov     [rbp+210h+var_200], rax
0x14006316f  mov     rax, [r13+2F0h]
0x140063176  test    rax, rax
0x140063179  mov     [rbp+210h+var_220], rdx
0x14006317d  mov     [rbp+210h+var_214], esi
0x140063180  cmovnz  rcx, rax
0x140063184  mov     [rbp+210h+var_208], 2
0x14006318c  mov     rax, r14
0x14006318f  mov     [rbp+210h+var_1F8], rdi
0x140063193  inc     rax
0x140063196  cmp     [rcx+rax], sil
0x14006319a  jnz     short loc_140063193
0x14006319c  inc     eax
0x14006319e  mov     [rbp+210h+var_1F0], rcx
0x1400631a2  lea     rcx, [r13+320h]
0x1400631a9  mov     [rbp+210h+var_1E8], eax
0x1400631ac  mov     [rbp+210h+var_1E0], rcx
0x1400631b0  mov     rax, r14
0x1400631b3  mov     [rbp+210h+var_1E4], esi
0x1400631b6  inc     rax
0x1400631b9  cmp     [rcx+rax], sil
0x1400631bd  jnz     short loc_1400631B6
0x1400631bf  inc     eax
0x1400631c1  mov     [rbp+210h+var_1D4], esi
0x1400631c4  lea     rcx, [r13+349h]
0x1400631cb  mov     [rbp+210h+var_1D8], eax
0x1400631ce  mov     rax, r14
0x1400631d1  mov     [rbp+210h+var_1D0], rcx
0x1400631d5  inc     rax
0x1400631d8  cmp     [rcx+rax], sil
0x1400631dc  jnz     short loc_1400631D5
0x1400631de  mov     rcx, cs:StorPortEventProvider_Context; RegHandle
0x1400631e5  lea     rdx, [rbp+210h+EventDescriptor]; EventDescriptor
0x1400631e9  inc     eax
0x1400631eb  mov     [rbp+210h+var_1C4], esi
0x1400631ee  mov     [rbp+210h+var_1C8], eax
0x1400631f1  mov     r9d, edi; Flags
0x1400631f4  lea     rax, aFailedToGetFre; "Failed to get free slot for non-read/wr"...
0x1400631fb  mov     [rbp+210h+var_1B8], 66h ; 'f'
0x140063203  mov     [rbp+210h+var_1C0], rax
0x140063207  xor     r8d, r8d; Filter
0x14006320a  lea     rax, aSqId; "SQ ID"
0x140063211  mov     [rbp+210h+var_1A8], 0Ch
0x140063219  mov     [rbp+210h+var_1B0], rax
0x14006321d  lea     rax, [rsp+310h+var_2C0]
0x140063222  mov     [rbp+210h+var_1A0], rax
0x140063226  lea     rax, aSqHead_0; "SQ head"
0x14006322d  mov     [rbp+210h+var_190], rax
0x140063234  lea     rax, [rsp+310h+var_2B8]
0x140063239  mov     [rbp+210h+var_180], rax
0x140063240  lea     rax, aSqTail_0; "SQ tail"
0x140063247  mov     [rbp+210h+var_170], rax
0x14006324e  lea     rax, [rsp+310h+var_2A0]
0x140063253  mov     [rbp+210h+var_160], rax
0x14006325a  lea     rax, aCommandId; "Command ID"
0x140063261  mov     [rbp+210h+var_150], rax
0x140063268  lea     rax, [rsp+310h+var_2B0]
0x14006326d  mov     [rbp+210h+var_140], rax
0x140063274  lea     rax, aIoSqCount; "IO SQ count"
0x14006327b  mov     [rbp+210h+var_130], rax
0x140063282  lea     rax, [rsp+310h+var_2C8]
0x140063287  mov     [rbp+210h+var_120], rax
0x14006328e  lea     rax, aIoCqCount; "IO CQ count"
0x140063295  mov     [rbp+210h+var_110], rax
0x14006329c  lea     rax, [rsp+310h+var_298]
0x1400632a1  mov     [rbp+210h+var_100], rax
0x1400632a8  lea     rax, aQueueDepth; "Queue depth"
0x1400632af  mov     [rbp+210h+var_F0], rax
0x1400632b6  lea     rax, [rbp+210h+var_290]
0x1400632ba  mov     [rbp+210h+var_E0], rax
0x1400632c1  lea     rax, aFreeCommandIdC; "Free command ID count"
0x1400632c8  mov     [rbp+210h+var_D0], rax
0x1400632cf  lea     rax, [rsp+310h+var_2A8]
0x1400632d4  mov     [rbp+210h+var_C0], rax
0x1400632db  lea     rax, [rbp+210h+var_250]
0x1400632df  mov     [rsp+310h+UserData], rax; UserData
0x1400632e4  lea     rax, [rbp+210h+var_288]
0x1400632e8  mov     [rsp+310h+UserDataCount], 1Ah; UserDataCount
0x1400632f0  mov     [rsp+310h+RelatedActivityId], rsi; RelatedActivityId
0x1400632f5  mov     [rsp+310h+ActivityId], rax; ActivityId
0x1400632fa  mov     [rbp+210h+var_198], 8
0x140063302  mov     [rbp+210h+var_188], 10h
0x14006330d  mov     [rbp+210h+var_178], 8
0x140063318  mov     [rbp+210h+var_168], 10h
0x140063323  mov     [rbp+210h+var_158], 8
0x14006332e  mov     [rbp+210h+var_148], 16h
0x140063339  mov     [rbp+210h+var_138], 8
  ... truncated ...
```
