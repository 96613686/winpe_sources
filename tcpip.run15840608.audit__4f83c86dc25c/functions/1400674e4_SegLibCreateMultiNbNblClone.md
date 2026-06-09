# SegLibCreateMultiNbNblClone

- ea: `0x1400674e4`
- end: `0x140068177`
- name: `SegLibCreateMultiNbNblClone`
- size: `3219`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, int, int, int, ULONG, __int64, __int64)`
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x140066b44`
- `0x1401ad764`

## callees

- `0x140067038`
- `0x14006712c`
- `0x1400671fc`
- `0x1400674e4`
- `0x140068180`
- `0x140069200`
- `0x1400696bc`
- `0x1401c0f82`
- `0x1401c0fd0`
- `0x1401c1200`
- `0x1401c1280`
- `0x1401c1580`

## import_xrefs

- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140067636`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140067636`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140067f7a`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1401c93d7`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1401c94dc`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140067f7a`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1401c93d7`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1401c94dc`
- `NDIS!NdisCopyReceiveNetBufferListInfo` at `0x140067ca0`
- `NDIS!NdisCopyReceiveNetBufferListInfo` at `0x140067ca0`
- `NDIS!NdisCopySendNetBufferListInfo` at `0x140067aac`
- `NDIS!NdisCopySendNetBufferListInfo` at `0x140067aac`
- `NDIS!NdisAllocateFragmentNetBufferList` at `0x140067723`
- `NDIS!NdisAllocateFragmentNetBufferList` at `0x140067723`
- `NDIS!NdisFreeNetBufferListContext` at `0x140068165`
- `NDIS!NdisFreeNetBufferListContext` at `0x140068165`
- `NDIS!NdisFreeFragmentNetBufferList` at `0x1401c95d9`
- `NDIS!NdisFreeFragmentNetBufferList` at `0x1401c95d9`
- `NDIS!NdisAdvanceNetBufferListDataStart` at `0x140067747`
- `NDIS!NdisAdvanceNetBufferListDataStart` at `0x140067747`
- `NDIS!NdisGetDataBuffer` at `0x1400677ba`
- `NDIS!NdisGetDataBuffer` at `0x140067c57`
- `NDIS!NdisGetDataBuffer` at `0x1401c928e`
- `NDIS!NdisGetDataBuffer` at `0x1400677ba`
- `NDIS!NdisGetDataBuffer` at `0x140067c57`
- `NDIS!NdisGetDataBuffer` at `0x1401c928e`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x140067c35`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x140067d9c`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x140067db8`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x140067df5`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x140067e0d`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x1401c9269`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x140067c35`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x140067d9c`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x140067db8`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x140067df5`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x140067e0d`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x1401c9269`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x140067c80`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x140067e4f`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x140067e6b`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x1401c92b7`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x140067c80`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x140067e4f`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x140067e6b`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x1401c92b7`

## pseudocode

```c
__int64 __fastcall SegLibCreateMultiNbNblClone(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        char a4,
        unsigned __int16 *a5,
        int a6,
        int a7,
        int a8,
        ULONG a9,
        __int64 a10,
        __int64 a11)
{
  __int64 v13; // rbx
  __int16 v14; // r12
  bool v15; // r8
  char v16; // di
  unsigned int v17; // eax
  __int64 v18; // rsi
  unsigned int v19; // r14d
  unsigned __int64 v20; // rcx
  __int64 v21; // rax
  void *v22; // rsp
  int v23; // r8d
  int v24; // r9d
  bool v25; // cf
  struct _NET_BUFFER_LIST *v26; // r14
  PNET_BUFFER_LIST v27; // rbx
  int v28; // esi
  __int64 v29; // r8
  unsigned __int16 v30; // r15
  struct _NET_BUFFER_LIST *FragmentNetBufferList; // rax
  struct _NET_BUFFER *FirstNetBuffer; // r13
  bool v33; // r12
  size_t v34; // rdi
  char *DataBuffer; // rax
  __int64 v36; // rdx
  ULONG v37; // esi
  void *v38; // r15
  unsigned __int8 v39; // cl
  __int64 v40; // rcx
  unsigned int v41; // eax
  _QWORD *v42; // rdx
  unsigned int v43; // ebx
  __int64 v44; // rcx
  __int64 v45; // rax
  unsigned __int16 *v46; // rdi
  char *v47; // rdx
  bool v48; // bl
  __int64 v49; // rcx
  unsigned int v50; // eax
  _QWORD *v51; // r8
  unsigned int v52; // ebx
  __int64 v53; // rcx
  __int64 v54; // rdx
  void *v55; // r9
  __int64 v56; // rcx
  unsigned int v57; // eax
  __int64 v58; // rdx
  unsigned int v59; // ebx
  __int64 v60; // rcx
  __int64 v61; // rax
  void *v62; // rdx
  __int64 v63; // r9
  SLIST_HEADER *Alignment; // rbx
  char v65; // di
  __int16 v66; // r12
  _QWORD *v67; // rax
  _DWORD *v68; // rcx
  ULONG v70; // ebx
  struct _NET_BUFFER *v71; // rcx
  ULONG v72; // edx
  ULONG v73; // ebx
  ULONG v74; // edx
  PNET_BUFFER_LIST v75; // rbx
  int v76; // edi
  int v77; // eax
  __int64 v78; // rax
  __int16 v79; // di
  __int64 v80; // rax
  _DWORD *v81; // rax
  __int64 v82; // rax
  __int64 v83; // r8
  __int64 v84; // rax
  __int64 v85; // rax
  __int64 v86; // r8
  volatile signed __int16 *v87; // rax
  __int64 v88; // rax
  __int64 v89; // rdx
  unsigned int v90; // r9d
  PVOID v91; // rax
  int v92; // ecx
  __int64 v93; // rax
  __int64 v94; // r8
  volatile signed __int32 *v95; // rcx
  __int64 v96; // r8
  __int64 v97; // rcx
  __int64 v98; // r8
  _DWORD *v99; // rax
  int v100; // ecx
  __int64 v101; // rax
  __int64 v102; // r8
  volatile signed __int32 *v103; // rcx
  __int64 v104; // r8
  __int64 v105; // rcx
  __int64 v106; // r8
  _DWORD *v107; // rax
  int v108; // ecx
  __int64 v109; // rax
  __int64 v110; // rdx
  volatile signed __int32 *v111; // rcx
  __int64 v112; // rdx
  __int64 v113; // rcx
  __int64 v114; // rdx
  __int64 MaximumLengtha; // [rsp+20h] [rbp-20h]
  int MaximumLength; // [rsp+20h] [rbp-20h]
  ULONG DataOffsetDelta; // [rsp+28h] [rbp-18h]
  bool v118; // [rsp+40h] [rbp+0h] BYREF
  char v119; // [rsp+41h] [rbp+1h]
  char v120; // [rsp+42h] [rbp+2h]
  char v121; // [rsp+43h] [rbp+3h]
  char v122; // [rsp+44h] [rbp+4h]
  char v123; // [rsp+45h] [rbp+5h]
  unsigned __int16 v124; // [rsp+46h] [rbp+6h]
  void *v125; // [rsp+48h] [rbp+8h]
  void *v126; // [rsp+50h] [rbp+10h]
  size_t Size; // [rsp+58h] [rbp+18h]
  void *Src; // [rsp+60h] [rbp+20h]
  unsigned int v129; // [rsp+68h] [rbp+28h]
  ULONG v130[8]; // [rsp+70h] [rbp+30h] BYREF
  int v131; // [rsp+90h] [rbp+50h]
  int v132; // [rsp+94h] [rbp+54h]
  int v133; // [rsp+98h] [rbp+58h]
  PNET_BUFFER_LIST OriginalNetBufferList; // [rsp+A0h] [rbp+60h]
  void *v135; // [rsp+A8h] [rbp+68h]
  void *v136; // [rsp+B0h] [rbp+70h]
  __int64 v137; // [rsp+B8h] [rbp+78h]
  __int64 v138; // [rsp+C0h] [rbp+80h]
  _QWORD v139[12]; // [rsp+D0h] [rbp+90h] BYREF

  OriginalNetBufferList = (PNET_BUFFER_LIST)a2;
  v137 = a10;
  memset(v130, 0, 28);
  v122 = a4;
  v138 = a11;
  memset(v139, 0, sizeof(v139));
  LOBYTE(v129) = 0;
  v13 = 0;
  v133 = 0;
  v14 = 0;
  v118 = 0;
  v15 = 0;
  v119 = 0;
  v16 = 0;
  if ( a5 )
  {
    v79 = *a5;
    v17 = *a5;
    v15 = ((*((_DWORD *)a5 + 7) - 1) & 0xFFFFFFFD) == 0;
    v118 = v15;
    LOWORD(v17) = v79 & 1;
    if ( (v79 & 1) != 0 )
    {
      v13 = *((_QWORD *)a5 + 1);
      v14 = a5[8];
    }
    v16 = (v79 & 4) != 0;
    if ( (_WORD)v17 )
      goto LABEL_3;
  }
  v17 = *(_DWORD *)(a2 + 160);
  if ( v17 )
  {
LABEL_3:
    if ( !v15 )
    {
      if ( !v16 )
        v119 = 1;
      goto LABEL_6;
    }
  }
  else if ( !v15 )
  {
LABEL_6:
    if ( a5 && (*(_BYTE *)a5 & 2) != 0 )
    {
      v119 = *((_BYTE *)a5 + 27);
      if ( v119 )
      {
        LOBYTE(v17) = *((_BYTE *)a5 + 26);
        v129 = v17;
        v133 = a5[12];
      }
    }
    else if ( !*(_DWORD *)(a2 + 160) )
    {
      v78 = *(_QWORD *)(a2 + 144);
      if ( (v78 & 0x1C) != 0 )
      {
        v119 = 1;
        v90 = (unsigned int)v78 >> 1;
        LOBYTE(v90) = (v78 & 2) != 0;
        v129 = v90;
        if ( (v78 & 4) != 0 )
          LOWORD(v133) = WORD1(v78) & 0x3FF;
        else
          v129 = v90;
      }
      else
      {
        v119 = 0;
      }
    }
  }
  v18 = *(_QWORD *)(a1 + 8);
  v19 = 4;
  if ( v18 && *(_BYTE *)(v18 + 48) )
    v19 = *(_DWORD *)(v18 + 16);
  v20 = 24LL * v19;
  v21 = v20 + 15;
  if ( v20 + 15 < v20 )
    v21 = 0xFFFFFFFFFFFFFF0LL;
  v22 = alloca(v21 & 0xFFFFFFFFFFFFFFF0uLL);
  LODWORD(v139[0]) = -267522035;
  HIDWORD(v139[1]) = KeGetCurrentProcessorNumberEx(0);
  LODWORD(v139[1]) = 0;
  BYTE4(v139[0]) = 0;
  v139[3] = 0;
  v25 = *(_QWORD *)(v18 + 32) != 0;
  v139[2] = 1;
  memset(&v139[6], 0, 20);
  HIDWORD(v139[5]) = 0;
  LOBYTE(v139[5]) = 0;
  LODWORD(v139[1]) = v25 ? 4 : 0;
  v139[4] = &v139[7];
  if ( &v118 )
  {
    HIDWORD(v139[8]) = v19;
    v139[9] = &v118;
  }
  else
  {
    HIDWORD(v139[8]) = 0;
    v139[9] = 0;
  }
  v139[10] = v18;
  LOBYTE(v23) = v122;
  v26 = 0;
  v123 = 0;
  MaximumLengtha = v13;
  v27 = OriginalNetBufferList;
  v28 = SegLibPvtLsoInitialize((unsigned int)v130, (_DWORD)OriginalNetBufferList, v23, v24, MaximumLengtha, v14, v16);
  if ( v28 < 0 )
  {
LABEL_74:
    v30 = v130[6];
    goto LABEL_63;
  }
  v30 = v130[6];
  FragmentNetBufferList = NdisAllocateFragmentNetBufferList(
                            v27,
                            0,
                            0,
                            LOWORD(v130[6]),
                            v130[0],
                            LOWORD(v130[6]) + a9,
                            0,
                            0);
  v26 = FragmentNetBufferList;
  if ( !FragmentNetBufferList )
  {
    v28 = -1073741670;
    goto LABEL_63;
  }
  NdisAdvanceNetBufferListDataStart(FragmentNetBufferList, a9, 0, 0);
  FirstNetBuffer = v26->FirstNetBuffer;
  v33 = v118;
  v28 = 0;
  v120 = 0;
  v136 = 0;
  Src = 0;
  v135 = 0;
  v121 = 0;
  v131 = 0;
  v132 = 0;
  v123 = 1;
  v124 = HIWORD(v130[5]) - BYTE2(v130[6]);
  LODWORD(Size) = (unsigned __int16)(v30 - HIWORD(v130[5]));
  while ( FirstNetBuffer )
  {
    v34 = v30;
    DataBuffer = (char *)NdisGetDataBuffer(FirstNetBuffer, v30, 0, 1u, 0);
    v37 = v124;
    v38 = DataBuffer;
    if ( DataBuffer )
    {
      v39 = BYTE2(v130[6]);
      v126 = &DataBuffer[BYTE2(v130[6])];
      v125 = &DataBuffer[HIWORD(v130[5])];
    }
    else
    {
      v70 = BYTE2(v130[6]);
      NdisAdvanceNetBufferDataStart(FirstNetBuffer, BYTE2(v130[6]), 0, 0);
      v126 = NdisGetDataBuffer(FirstNetBuffer, v37, 0, 1u, 0);
      v71 = FirstNetBuffer;
      if ( !v126 )
      {
        v72 = v70;
LABEL_73:
        v28 = -1073741670;
        NdisRetreatNetBufferDataStart(v71, v72, 0, 0);
        goto LABEL_74;
      }
      NdisAdvanceNetBufferDataStart(FirstNetBuffer, v37, 0, 0);
      v91 = NdisGetDataBuffer(FirstNetBuffer, Size, 0, 1u, 0);
      v72 = HIWORD(v130[5]);
      v125 = v91;
      v71 = FirstNetBuffer;
      if ( !v91 )
        goto LABEL_73;
      v120 = 1;
      NdisRetreatNetBufferDataStart(FirstNetBuffer, HIWORD(v130[5]), 0, 0);
      v39 = BYTE2(v130[6]);
      v27 = OriginalNetBufferList;
    }
    if ( v135 )
    {
      if ( v121 || v120 )
      {
        v40 = v139[10];
        if ( *(_BYTE *)(v139[10] + 1LL) == 1 && !BYTE4(v139[0]) )
        {
          v84 = 0;
          BYTE4(v139[0]) = 1;
          if ( HIDWORD(v139[1]) != -1 )
          {
            v36 = *(_QWORD *)(v139[10] + 24LL);
            if ( v36 )
              v84 = v36 + 20LL * HIDWORD(v139[1]);
          }
          _InterlockedAdd16((volatile signed __int16 *)(v84 + 16), 1u);
          v40 = v139[10];
        }
        v41 = *(_DWORD *)(v40 + 4);
        if ( v41 )
        {
          v42 = (_QWORD *)v139[4];
          v43 = *(_DWORD *)(v139[4] + 8LL);
          if ( v43 >= *(_DWORD *)(v139[4] + 12LL) )
          {
            v43 = 0;
            if ( LODWORD(v139[2]) < v41
              && (v99 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v40 + 64)), (v42 = v99) != 0) )
            {
              *(_QWORD *)v99 = 0;
              v99[2] = 0;
              v100 = *(_DWORD *)(v139[10] + 8LL);
              *((_QWORD *)v99 + 2) = v99 + 6;
              v99[3] = v100;
              *(_QWORD *)v139[4] = v99;
              ++LODWORD(v139[2]);
              v139[4] = v99;
              if ( *(_BYTE *)(v139[10] + 1LL) == 1 )
              {
                v101 = 0;
                if ( HIDWORD(v139[1]) != -1 )
                {
                  v102 = *(_QWORD *)(v139[10] + 24LL);
                  if ( v102 )
                    v101 = v102 + 20LL * HIDWORD(v139[1]);
                }
                _InterlockedAdd16((volatile signed __int16 *)(v101 + 12), 1u);
                v103 = 0;
                if ( HIDWORD(v139[1]) != -1 )
                {
                  v104 = *(_QWORD *)(v139[10] + 24LL);
                  if ( v104 )
                    v103 = (volatile signed __int32 *)(v104 + 20LL * HIDWORD(v139[1]));
                }
                _InterlockedAdd(v103, 1u);
              }
            }
            else
            {
              LOBYTE(v42) = 1;
              BLFlushBatchOpContextEx(v139, v42, 0);
              v42 = &v139[7];
            }
          }
          ++HIDWORD(v139[2]);
          ++*((_DWORD *)v42 + 2);
          if ( *(_BYTE *)(v139[10] + 1LL) == 1 )
          {
            v85 = 0;
            if ( HIDWORD(v139[1]) != -1 )
            {
              v86 = *(_QWORD *)(v139[10] + 24LL);
              if ( v86 )
                v85 = v86 + 20LL * HIDWORD(v139[1]);
            }
            _InterlockedAdd16((volatile signed __int16 *)(v85 + 14), 1u);
            v105 = 0;
            if ( HIDWORD(v139[1]) != -1 )
            {
              v106 = *(_QWORD *)(v139[10] + 24LL);
              if ( v106 )
                v105 = v106 + 20LL * HIDWORD(v139[1]);
            }
            _InterlockedAdd((volatile signed __int32 *)(v105 + 4), 1u);
          }
          v44 = 3LL * v43;
          v45 = v42[2];
          v46 = (unsigned __int16 *)v126;
          v47 = (char *)Src;
          v48 = v118;
          *(_QWORD *)(v45 + 8 * v44) = v126;
          *(_DWORD *)(v45 + 8 * v44 + 16) = (16 * v37) | 1;
          v28 = 0;
          *(_QWORD *)(v45 + 8 * v44 + 8) = v47;
        }
        else
        {
          v28 = 0;
          if ( HIDWORD(v139[2]) )
          {
            LOBYTE(v36) = 1;
            BLFlushBatchOpContextEx(v139, v36, 0);
            v40 = v139[10];
          }
          if ( (v139[1] & 5) == 5 || (v139[1] & 6) == 6 )
          {
            (*(void (**)(void))(v40 + 32))();
            memmove(v126, Src, v124);
            (*(void (**)(void))(v139[10] + 40LL))();
          }
          else
          {
            memmove(v126, Src, v124);
          }
          v48 = v118;
          v46 = (unsigned __int16 *)v126;
        }
        v49 = v139[10];
        if ( *(_BYTE *)(v139[10] + 1LL) == 1 && !BYTE4(v139[0]) )
        {
          v87 = 0;
          BYTE4(v139[0]) = 1;
          if ( HIDWORD(v139[1]) != -1 )
          {
            v47 = *(char **)(v139[10] + 24LL);
            if ( v47 )
              v87 = (volatile signed __int16 *)&v47[20 * HIDWORD(v139[1])];
          }
          _InterlockedAdd16(v87 + 8, 1u);
          v49 = v139[10];
        }
        v50 = *(_DWORD *)(v49 + 4);
        if ( v50 )
        {
          v51 = (_QWORD *)v139[4];
          v52 = *(_DWORD *)(v139[4] + 8LL);
          if ( v52 >= *(_DWORD *)(v139[4] + 12LL) )
          {
            v52 = 0;
            if ( LODWORD(v139[2]) < v50
              && (v107 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v49 + 64)), (v51 = v107) != 0) )
            {
              *(_QWORD *)v107 = 0;
              v107[2] = 0;
              v108 = *(_DWORD *)(v139[10] + 8LL);
              *((_QWORD *)v107 + 2) = v107 + 6;
              v107[3] = v108;
              *(_QWORD *)v139[4] = v107;
              ++LODWORD(v139[2]);
              v139[4] = v107;
              if ( *(_BYTE *)(v139[10] + 1LL) == 1 )
              {
                v109 = 0;
                if ( HIDWORD(v139[1]) != -1 )
                {
                  v110 = *(_QWORD *)(v139[10] + 24LL);
                  if ( v110 )
                    v109 = v110 + 20LL * HIDWORD(v139[1]);
                }
                _InterlockedAdd16((volatile signed __int16 *)(v109 + 12), 1u);
                v111 = 0;
                if ( HIDWORD(v139[1]) != -1 )
                {
                  v112 = *(_QWORD *)(v139[10] + 24LL);
                  if ( v112 )
                    v111 = (volatile signed __int32 *)(v112 + 20LL * HIDWORD(v139[1]));
                }
                _InterlockedAdd(v111, 1u);
              }
            }
            else
            {
              LOBYTE(v47) = 1;
              BLFlushBatchOpContextEx(v139, v47, 0);
              v51 = &v139[7];
            }
          }
          ++HIDWORD(v139[2]);
          ++*((_DWORD *)v51 + 2);
          if ( *(_BYTE *)(v139[10] + 1LL) == 1 )
          {
            v88 = 0;
            if ( HIDWORD(v139[1]) != -1 )
            {
              v89 = *(_QWORD *)(v139[10] + 24LL);
              if ( v89 )
                v88 = v89 + 20LL * HIDWORD(v139[1]);
            }
            _InterlockedAdd16((volatile signed __int16 *)(v88 + 14), 1u);
            v113 = 0;
            if ( HIDWORD(v139[1]) != -1 )
            {
              v114 = *(_QWORD *)(v139[10] + 24LL);
              if ( v114 )
                v113 = v114 + 20LL * HIDWORD(v139[1]);
            }
            _InterlockedAdd((volatile signed __int32 *)(v113 + 4), 1u);
          }
          v53 = v51[2];
          v54 = 3LL * v52;
          *(_QWORD *)(v53 + 8 * v54) = v125;
          *(_QWORD *)(v53 + 8 * v54 + 8) = v135;
          v33 = v118;
          *(_DWORD *)(v53 + 8 * v54 + 16) = (16 * Size) | 1;
        }
        else
        {
          v118 = v48;
          if ( HIDWORD(v139[2]) )
          {
            LOBYTE(v47) = 1;
            BLFlushBatchOpContextEx(v139, v47, 0);
            v49 = v139[10];
          }
          if ( (v139[1] & 5) == 5 || (v139[1] & 6) == 6 )
          {
            (*(void (**)(void))(v49 + 32))();
            memmove(v125, v135, (unsigned int)Size);
            (*(void (**)(void))(v139[10] + 40LL))();
            v118 = v48;
          }
          else
          {
            memmove(v125, v135, (unsigned int)Size);
          }
          v33 = v48;
        }
        goto LABEL_37;
      }
      v56 = v139[10];
      v28 = 0;
      if ( *(_BYTE *)(v139[10] + 1LL) == 1 && !BYTE4(v139[0]) )
      {
        v80 = 0;
        BYTE4(v139[0]) = 1;
        if ( HIDWORD(v139[1]) != -1 )
        {
          v36 = *(_QWORD *)(v139[10] + 24LL);
          if ( v36 )
            v80 = v36 + 20LL * HIDWORD(v139[1]);
        }
        _InterlockedAdd16((volatile signed __int16 *)(v80 + 16), 1u);
        v56 = v139[10];
      }
      v57 = *(_DWORD *)(v56 + 4);
      if ( v57 )
      {
        v58 = v139[4];
        v59 = *(_DWORD *)(v139[4] + 8LL);
        if ( v59 < *(_DWORD *)(v139[4] + 12LL) )
          goto LABEL_46;
        v59 = 0;
        if ( LODWORD(v139[2]) >= v57 )
        {
          LOBYTE(v58) = 1;
          goto LABEL_68;
        }
        v81 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v56 + 64));
        v58 = (__int64)v81;
        if ( v81 )
        {
          *(_QWORD *)v81 = 0;
          v81[2] = 0;
          v92 = *(_DWORD *)(v139[10] + 8LL);
          *((_QWORD *)v81 + 2) = v81 + 6;
          v81[3] = v92;
          *(_QWORD *)v139[4] = v81;
          ++LODWORD(v139[2]);
          v139[4] = v81;
          if ( *(_BYTE *)(v139[10] + 1LL) == 1 )
          {
            v93 = 0;
            if ( HIDWORD(v139[1]) != -1 )
            {
              v94 = *(_QWORD *)(v139[10] + 24LL);
              if ( v94 )
                v93 = v94 + 20LL * HIDWORD(v139[1]);
            }
            _InterlockedAdd16((volatile signed __int16 *)(v93 + 12), 1u);
            v95 = 0;
            if ( HIDWORD(v139[1]) != -1 )
            {
              v96 = *(_QWORD *)(v139[10] + 24LL);
              if ( v96 )
                v95 = (volatile signed __int32 *)(v96 + 20LL * HIDWORD(v139[1]));
            }
            _InterlockedAdd(v95, 1u);
          }
        }
        else
        {
          v58 = 1;
LABEL_68:
          BLFlushBatchOpContextEx(v139, v58, 0);
          v58 = (__int64)&v139[7];
        }
LABEL_46:
        ++HIDWORD(v139[2]);
        ++*(_DWORD *)(v58 + 8);
        if ( *(_BYTE *)(v139[10] + 1LL) == 1 )
        {
          v82 = 0;
          if ( HIDWORD(v139[1]) != -1 )
          {
            v83 = *(_QWORD *)(v139[10] + 24LL);
            if ( v83 )
              v82 = v83 + 20LL * HIDWORD(v139[1]);
          }
          _InterlockedAdd16((volatile signed __int16 *)(v82 + 14), 1u);
          v97 = 0;
          if ( HIDWORD(v139[1]) != -1 )
          {
            v98 = *(_QWORD *)(v139[10] + 24LL);
            if ( v98 )
              v97 = v98 + 20LL * HIDWORD(v139[1]);
          }
          _InterlockedAdd((volatile signed __int32 *)(v97 + 4), 1u);
        }
        v60 = 3LL * v59;
        v61 = *(_QWORD *)(v58 + 16);
        v62 = v136;
        *(_QWORD *)(v61 + 8 * v60) = v38;
        *(_DWORD *)(v61 + 8 * v60 + 16) = (16 * v34) | 1;
        *(_QWORD *)(v61 + 8 * v60 + 8) = v62;
      }
      else
      {
        if ( HIDWORD(v139[2]) )
        {
          LOBYTE(v36) = 1;
          BLFlushBatchOpContextEx(v139, v36, 0);
          v56 = v139[10];
        }
        if ( (v139[1] & 5) == 5 || (v139[1] & 6) == 6 )
        {
          (*(void (**)(void))(v56 + 32))();
          memmove(v38, v136, v34);
          (*(void (**)(void))(v139[10] + 40LL))();
          v118 = v33;
        }
        else
        {
          memmove(v38, v136, v34);
          v33 = v118;
        }
      }
      v46 = (unsigned __int16 *)v126;
LABEL_37:
      v55 = v125;
      goto LABEL_38;
    }
    if ( v120 )
    {
      v73 = v39;
      NdisAdvanceNetBufferDataStart(FirstNetBuffer, v39, 0, 0);
      v74 = v73;
      v75 = OriginalNetBufferList;
      NdisAdvanceNetBufferDataStart(OriginalNetBufferList->FirstNetBuffer, v74, 0, 0);
      v76 = SegLibPvtDeferredCopyMdlChainData(
              v139,
              *(_QWORD *)(v75->Link.Region + 8),
              *(unsigned int *)(v75->Link.Region + 16),
              v37,
              v126);
      NdisAdvanceNetBufferDataStart(FirstNetBuffer, v37, 0, 0);
      NdisAdvanceNetBufferDataStart(v75->FirstNetBuffer, v37, 0, 0);
      v77 = SegLibPvtDeferredCopyMdlChainData(
              v139,
              *(_QWORD *)(v75->Link.Region + 8),
              *(unsigned int *)(v75->Link.Region + 16),
              (unsigned int)Size,
              v125);
      LODWORD(v75) = HIWORD(v130[5]);
      v28 = v77;
      NdisRetreatNetBufferDataStart(FirstNetBuffer, HIWORD(v130[5]), 0, 0);
      NdisRetreatNetBufferDataStart(OriginalNetBufferList->FirstNetBuffer, (ULONG)v75, 0, 0);
      if ( v76 < 0 )
        goto LABEL_74;
    }
    else
    {
      v28 = SegLibPvtDeferredCopyMdlChainData(
              v139,
              *(_QWORD *)(v27->Link.Region + 8),
              *(unsigned int *)(v27->Link.Region + 16),
              (unsigned int)v34,
              v38);
    }
    if ( v28 < 0 )
      goto LABEL_74;
    LOBYTE(v29) = 1;
    BLFlushBatchOpContextEx(v139, 0, v29);
    v28 = SegLibPvtParseHeaders(v130, v126, v125);
    if ( v28 < 0 )
      goto LABEL_74;
    v46 = (unsigned __int16 *)v126;
    v28 = 0;
    v55 = v125;
    Src = v126;
    v135 = v125;
    v121 = v120;
    v136 = v38;
LABEL_38:
    SegLibPvtLsoDeferredFixHeaders((__int64)v139, (__int64)v130, v46, (__int64)v55, v131++, v132);
    FirstNetBuffer = (struct _NET_BUFFER *)FirstNetBuffer->Link.Alignment;
    v27 = OriginalNetBufferList;
    v30 = v130[6];
    v132 += v130[0];
  }
  if ( v33 )
  {
    NdisCopyReceiveNetBufferListInfo(v26, v27);
  }
  else
  {
    NdisCopySendNetBufferListInfo(v26, v27);
    v26->NetBufferListInfo[2] = 0;
  }
  if ( v119 )
  {
    Alignment = (SLIST_HEADER *)v26->FirstNetBuffer;
    v65 = v129;
    v66 = v133;
    while ( Alignment )
    {
      LOBYTE(v63) = v122;
      LOBYTE(DataOffsetDelta) = v65;
      LOWORD(MaximumLength) = v66;
      Src = (void *)(((v130[6] & 0x1000000) == 0)
                   | (2 * (HIBYTE(v130[6]) & 1 | ((unsigned __int16)(HIWORD(v130[5]) & 0x3FF) << 15)))
                   | 4LL);
      v28 = SegLibDeferredChecksumPacket(v139, Alignment, Src, v63, MaximumLength, DataOffsetDelta);
      if ( v28 < 0 )
        goto LABEL_63;
      Alignment = (SLIST_HEADER *)Alignment->Alignment;
      v28 = 0;
    }
    v27 = OriginalNetBufferList;
    v26->NetBufferListInfo[0] = 0;
  }
  else if ( !v33 )
  {
    Src = (void *)(((v130[6] & 0x1000000) == 0)
                 | (2 * (HIBYTE(v130[6]) & 1 | ((unsigned __int16)(HIWORD(v130[5]) & 0x3FF) << 15)))
                 | 4LL);
    v26->NetBufferListInfo[0] = Src;
  }
  v67 = (_QWORD *)v137;
  v68 = (_DWORD *)v138;
  v26->ParentNetBufferList = v27;
  *v67 = v26;
  *v68 = v30;
LABEL_63:
  LOBYTE(v29) = 1;
  BLFlushBatchOpContextEx(v139, 0, v29);
  if ( v28 < 0 && v26 )
  {
    if ( v123 )
      NdisFreeNetBufferListContext(v26, 0);
    NdisFreeFragmentNetBufferList(v26, v30, 0);
  }
  return (unsigned int)v28;
}

```

## disassembly

```asm
0x1400674e4  push    rbp
0x1400674e6  push    rsi
0x1400674e7  push    rdi
0x1400674e8  push    r12
0x1400674ea  push    r13
0x1400674ec  push    r14
0x1400674ee  push    r15
0x1400674f0  sub     rsp, 140h
0x1400674f7  lea     rbp, [rsp+40h]
0x1400674fc  mov     [rbp+130h+arg_0], rbx
0x140067503  mov     rax, cs:__security_cookie
0x14006750a  xor     rax, rbp
0x14006750d  mov     [rbp+130h+var_40], rax
0x140067514  mov     rax, [rbp+130h+arg_48]
0x14006751b  xorps   xmm0, xmm0
0x14006751e  mov     r13d, [rbp+130h+arg_40]
0x140067525  mov     r14, rdx
0x140067528  mov     [rbp+130h+OriginalNetBufferList], rdx
0x14006752c  mov     rsi, rcx
0x14006752f  xor     edx, edx; Val
0x140067531  mov     [rbp+130h+var_B8], rax
0x140067535  mov     rax, [rbp+130h+arg_50]
0x14006753c  lea     rcx, [rbp+130h+var_A0]; void *
0x140067543  movups  xmmword ptr [rbp+130h+var_100], xmm0
0x140067547  mov     [rbp+130h+var_12C], r9b
0x14006754b  lea     r8d, [rdx+60h]; Size
0x14006754f  mov     [rbp+130h+var_B0], rax
0x140067556  movups  xmmword ptr [rbp+130h+var_100+0Ch], xmm0
0x14006755a  call    memset
0x14006755f  mov     rdx, [rbp+130h+arg_20]
0x140067566  xor     r10d, r10d
0x140067569  mov     byte ptr [rbp+130h+var_108], r10b
0x14006756d  mov     ebx, r10d
0x140067570  mov     [rbp+130h+var_D8], r10d
0x140067574  mov     r12d, r10d
0x140067577  mov     [rbp+130h+var_130], r10b
0x14006757b  mov     r8b, r10b
0x14006757e  mov     [rbp+130h+var_12F], r10b
0x140067582  lea     r11d, [r10+1]
0x140067586  mov     dil, r10b
0x140067589  mov     r15d, 3FFh
0x14006758f  test    rdx, rdx
0x140067592  jnz     loc_140067EA9
0x140067598  mov     eax, [r14+0A0h]
0x14006759f  test    eax, eax
0x1400675a1  jz      short loc_1400675DD
0x1400675a3  test    r8b, r8b
0x1400675a6  jnz     short loc_1400675E2
0x1400675a8  test    dil, dil
0x1400675ab  jnz     short loc_1400675B1
0x1400675ad  mov     [rbp+130h+var_12F], r11b
0x1400675b1  test    rdx, rdx
0x1400675b4  jz      loc_140067E84
0x1400675ba  mov     al, [rdx]
0x1400675bc  test    al, 2
0x1400675be  jz      loc_140067E84
0x1400675c4  mov     cl, [rdx+1Bh]
0x1400675c7  mov     [rbp+130h+var_12F], cl
0x1400675ca  test    cl, cl
0x1400675cc  jz      short loc_1400675E2
0x1400675ce  mov     al, [rdx+1Ah]
0x1400675d1  mov     [rbp+130h+var_108], eax
0x1400675d4  movzx   eax, word ptr [rdx+18h]
0x1400675d8  mov     [rbp+130h+var_D8], eax
0x1400675db  jmp     short loc_1400675E2
0x1400675dd  test    r8b, r8b
0x1400675e0  jz      short loc_1400675B1
0x1400675e2  mov     rsi, [rsi+8]
0x1400675e6  mov     r14d, 4
0x1400675ec  test    rsi, rsi
0x1400675ef  jz      short loc_1400675FB
0x1400675f1  cmp     [rsi+30h], r10b
0x1400675f5  jnz     loc_140067EDA
0x1400675fb  mov     eax, r14d
0x1400675fe  lea     rcx, [rax+rax*2]
0x140067602  shl     rcx, 3
0x140067606  lea     rax, [rcx+0Fh]
0x14006760a  cmp     rax, rcx
0x14006760d  ja      short loc_140067619
0x14006760f  mov     rax, 0FFFFFFFFFFFFFF0h
0x140067619  and     rax, 0FFFFFFFFFFFFFFF0h
0x14006761d  call    __chkstk_0
0x140067622  sub     rsp, rax
0x140067625  mov     [rbp+130h+var_A0], 0F00DF00Dh
0x14006762f  xor     ecx, ecx; ProcNumber
0x140067631  lea     r15, [rsp+170h+var_130]
0x140067636  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14006763d  nop     dword ptr [rax+rax+00h]
0x140067642  xor     edx, edx
0x140067644  mov     [rbp+130h+var_94], eax
0x14006764a  mov     [rbp+130h+var_98], edx
0x140067650  mov     [rbp+130h+var_9C], dl
0x140067656  mov     [rbp+130h+var_88], rdx
0x14006765d  mov     rax, [rsi+20h]
0x140067661  neg     rax
0x140067664  mov     [rbp+130h+var_90], 1
0x14006766f  lea     rax, [rbp+130h+var_68]
0x140067676  mov     [rbp+130h+var_70], rdx
0x14006767d  sbb     ecx, ecx
0x14006767f  mov     [rbp+130h+var_74], edx
0x140067685  and     ecx, 4
0x140067688  mov     [rbp+130h+var_78], dl
0x14006768e  mov     [rbp+130h+var_98], ecx
0x140067694  mov     [rbp+130h+var_68], rdx
0x14006769b  mov     [rbp+130h+var_60], edx
0x1400676a1  mov     [rbp+130h+var_80], rax
0x1400676a8  test    r15, r15
0x1400676ab  jz      loc_140067B9F
0x1400676b1  mov     [rbp+130h+var_5C], r14d
0x1400676b8  mov     [rbp+130h+var_58], r15
0x1400676bf  mov     [rbp+130h+var_50], rsi
0x1400676c6  mov     r8b, [rbp+130h+var_12C]
0x1400676ca  lea     rcx, [rbp+130h+var_100]
0x1400676ce  mov     byte ptr [rsp+170h+DataBackFill], dil
0x1400676d3  mov     r14, rdx
0x1400676d6  mov     [rbp+130h+var_12B], dl
0x1400676d9  mov     word ptr [rsp+170h+DataOffsetDelta], r12w
0x1400676df  mov     qword ptr [rsp+170h+MaximumLength], rbx
0x1400676e4  mov     rbx, [rbp+130h+OriginalNetBufferList]
0x1400676e8  mov     rdx, rbx
0x1400676eb  call    SegLibPvtLsoInitialize
0x1400676f0  xor     edi, edi
0x1400676f2  mov     esi, eax
0x1400676f4  test    eax, eax
0x1400676f6  js      loc_140067C8C
0x1400676fc  movzx   r15d, [rbp+130h+var_E8]
0x140067701  xor     r8d, r8d; NetBufferPool
0x140067704  mov     [rsp+170h+AllocateFragmentFlags], edi; AllocateFragmentFlags
0x140067708  mov     r9d, r15d; StartOffset
0x14006770b  mov     [rsp+170h+DataBackFill], edi; DataBackFill
0x14006770f  xor     edx, edx; NetBufferListPool
0x140067711  mov     rcx, rbx; OriginalNetBufferList
0x140067714  lea     eax, [r15+r13]
0x140067718  mov     [rsp+170h+DataOffsetDelta], eax; DataOffsetDelta
0x14006771c  mov     eax, [rbp+130h+var_100]
0x14006771f  mov     [rsp+170h+MaximumLength], eax; MaximumLength
0x140067723  call    cs:__imp_NdisAllocateFragmentNetBufferList
0x14006772a  nop     dword ptr [rax+rax+00h]
0x14006772f  mov     r14, rax
0x140067732  test    rax, rax
0x140067735  jz      loc_140067C96
0x14006773b  xor     r9d, r9d; FreeMdlMdlHandler
0x14006773e  xor     r8d, r8d; FreeMdl
0x140067741  mov     edx, r13d; DataOffsetDelta
0x140067744  mov     rcx, rax; NetBufferList
0x140067747  call    cs:__imp_NdisAdvanceNetBufferListDataStart
0x14006774e  nop     dword ptr [rax+rax+00h]
0x140067753  movzx   eax, [rbp+130h+var_E6]
0x140067757  movzx   ecx, [rbp+130h+var_EA]
0x14006775b  mov     r13, [r14+8]
0x14006775f  sub     cx, ax
0x140067762  mov     r12b, [rbp+130h+var_130]
0x140067766  movzx   eax, r15w
0x14006776a  sub     ax, [rbp+130h+var_EA]
0x14006776e  xor     esi, esi
0x140067770  movzx   eax, ax
0x140067773  mov     [rbp+130h+var_12E], dil
0x140067777  mov     [rbp+130h+var_C0], rdi
0x14006777b  mov     [rbp+130h+Src], rdi
0x14006777f  mov     [rbp+130h+var_C8], rdi
0x140067783  mov     [rbp+130h+var_12D], dil
0x140067787  mov     [rbp+130h+var_E0], edi
0x14006778a  mov     [rbp+130h+var_DC], edi
0x14006778d  lea     edi, [rsi+1]
0x140067790  mov     [rbp+130h+var_12B], 1
0x140067794  mov     [rbp+130h+var_12A], cx
0x140067798  mov     dword ptr [rbp+130h+Size], eax
0x14006779b  test    r13, r13
0x14006779e  jz      loc_140067A9D
0x1400677a4  movzx   edi, r15w
0x1400677a8  mov     r9d, 1; AlignMultiple
0x1400677ae  mov     edx, edi; BytesNeeded
0x1400677b0  mov     [rsp+170h+MaximumLength], esi; AlignOffset
0x1400677b4  xor     r8d, r8d; Storage
0x1400677b7  mov     rcx, r13; NetBuffer
0x1400677ba  call    cs:__imp_NdisGetDataBuffer
0x1400677c1  nop     dword ptr [rax+rax+00h]
0x1400677c6  movzx   esi, [rbp+130h+var_12A]
0x1400677ca  mov     r15, rax
0x1400677cd  test    rax, rax
0x1400677d0  jz      loc_140067C26
0x1400677d6  movzx   ecx, [rbp+130h+var_E6]
0x1400677da  add     rax, rcx
0x1400677dd  mov     [rbp+130h+var_120], rax
0x1400677e1  movzx   eax, [rbp+130h+var_EA]
0x1400677e5  add     rax, r15
0x1400677e8  mov     [rbp+130h+var_128], rax
0x1400677ec  cmp     [rbp+130h+var_C8], 0
0x1400677f1  jz      loc_140067A1C
0x1400677f7  cmp     [rbp+130h+var_12D], 0
0x1400677fb  jnz     short loc_140067807
0x1400677fd  cmp     [rbp+130h+var_12E], 0
0x140067801  jz      loc_14006799F
0x140067807  mov     rcx, [rbp+130h+var_50]
0x14006780e  mov     r12d, 1
0x140067814  or      r15d, 0FFFFFFFFh
0x140067818  cmp     [rcx+1], r12b
0x14006781c  jz      loc_140067FC9
0x140067822  mov     eax, [rcx+4]
0x140067825  test    eax, eax
0x140067827  jz      loc_140067CB1
0x14006782d  mov     rdx, [rbp+130h+var_80]
0x140067834  mov     ebx, [rdx+8]
0x140067837  cmp     ebx, [rdx+0Ch]
0x14006783a  jnb     loc_140067947
0x140067840  add     dword ptr [rbp+130h+var_90+4], r12d
0x140067847  add     [rdx+8], r12d
0x14006784b  mov     r8, [rbp+130h+var_50]
0x140067852  cmp     [r8+1], r12b
0x140067856  jz      loc_14006805A
0x14006785c  mov     eax, ebx
0x14006785e  lea     rcx, [rax+rax*2]
0x140067862  mov     rax, [rdx+10h]
0x140067866  mov     rdi, [rbp+130h+var_120]
0x14006786a  mov     rdx, [rbp+130h+Src]
0x14006786e  mov     bl, [rbp+130h+var_130]
0x140067871  shl     esi, 4
0x140067874  or      esi, r12d
0x140067877  mov     [rax+rcx*8], rdi
0x14006787b  mov     [rax+rcx*8+10h], esi
0x14006787f  xor     esi, esi
0x140067881  mov     [rax+rcx*8+8], rdx
0x140067886  mov     rcx, [rbp+130h+var_50]
0x14006788d  cmp     [rcx+1], r12b
0x140067891  jz      loc_140068089
0x140067897  mov     eax, [rcx+4]
0x14006789a  test    eax, eax
0x14006789c  jz      loc_140067CFF
0x1400678a2  mov     r8, [rbp+130h+var_80]
0x1400678a9  mov     ebx, [r8+8]
0x1400678ad  cmp     ebx, [r8+0Ch]
0x1400678b1  jnb     loc_140067973
0x1400678b7  add     dword ptr [rbp+130h+var_90+4], r12d
0x1400678be  add     [r8+8], r12d
0x1400678c2  mov     rdx, [rbp+130h+var_50]
0x1400678c9  cmp     [rdx+1], r12b
0x1400678cd  jz      loc_14006811D
0x1400678d3  mov     rcx, [r8+10h]
0x1400678d7  mov     eax, ebx
0x1400678d9  lea     rdx, [rax+rax*2]
0x1400678dd  mov     rax, [rbp+130h+var_128]
0x1400678e1  mov     [rcx+rdx*8], rax
0x1400678e5  mov     rax, [rbp+130h+var_C8]
0x1400678e9  mov     [rcx+rdx*8+8], rax
0x1400678ee  mov     eax, dword ptr [rbp+130h+Size]
0x1400678f1  shl     eax, 4
0x1400678f4  or      eax, r12d
0x1400678f7  mov     r12b, [rbp+130h+var_130]
0x1400678fb  mov     [rcx+rdx*8+10h], eax
0x1400678ff  mov     r9, [rbp+130h+var_128]
0x140067903  mov     eax, [rbp+130h+var_DC]
0x140067906  lea     rdx, [rbp+130h+var_100]
0x14006790a  mov     [rsp+170h+DataOffsetDelta], eax
0x14006790e  lea     rcx, [rbp+130h+var_A0]
0x140067915  mov     eax, [rbp+130h+var_E0]
0x140067918  mov     r8, rdi
0x14006791b  mov     [rsp+170h+MaximumLength], eax
0x14006791f  call    SegLibPvtLsoDeferredFixHeaders
0x140067924  mov     edx, [rbp+130h+var_DC]
0x140067927  mov     edi, 1
0x14006792c  add     [rbp+130h+var_E0], edi
0x14006792f  add     edx, [rbp+130h+var_100]
0x140067932  mov     r13, [r13+0]
0x140067936  mov     rbx, [rbp+130h+OriginalNetBufferList]
0x14006793a  movzx   r15d, [rbp+130h+var_E8]
0x14006793f  mov     [rbp+130h+var_DC], edx
0x140067942  jmp     loc_14006779B
0x140067947  xor     ebx, ebx
0x140067949  cmp     dword ptr [rbp+130h+var_90], eax
0x14006794f  jb      loc_1401C93D3
0x140067955  xor     r8d, r8d
0x140067958  lea     rcx, [rbp+130h+var_A0]
0x14006795f  mov     dl, r12b
0x140067962  call    BLFlushBatchOpContextEx
0x140067967  lea     rdx, [rbp+130h+var_68]
0x14006796e  jmp     loc_140067840
0x140067973  mov     ebx, esi
0x140067975  cmp     dword ptr [rbp+130h+var_90], eax
0x14006797b  jb      loc_1401C94D8
0x140067981  xor     r8d, r8d
0x140067984  lea     rcx, [rbp+130h+var_A0]
0x14006798b  mov     dl, r12b
0x14006798e  call    BLFlushBatchOpContextEx
0x140067993  lea     r8, [rbp+130h+var_68]
0x14006799a  jmp     loc_1400678B7
0x14006799f  mov     rcx, [rbp+130h+var_50]
0x1400679a6  mov     r9d, 1
0x1400679ac  xor     esi, esi
0x1400679ae  cmp     [rcx+1], r9b
0x1400679b2  jz      loc_140067EE3
0x1400679b8  mov     eax, [rcx+4]
0x1400679bb  test    eax, eax
0x1400679bd  jz      loc_140067D46
0x1400679c3  mov     rdx, [rbp+130h+var_80]
0x1400679ca  mov     ebx, [rdx+8]
0x1400679cd  cmp     ebx, [rdx+0Ch]
0x1400679d0  jnb     loc_140067BB1
0x1400679d6  add     dword ptr [rbp+130h+var_90+4], r9d
0x1400679dd  add     [rdx+8], r9d
0x1400679e1  mov     r8, [rbp+130h+var_50]
  ... truncated ...
```
