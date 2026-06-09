# SegLibCreateMultiNbNblClone

- ea: `0x140002da4`
- end: `0x140003d95`
- name: `SegLibCreateMultiNbNblClone`
- size: `4081`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x14000268c`

## callees

- `0x140002ae8`
- `0x140002bb8`
- `0x140002da4`
- `0x140003e34`
- `0x140004b70`
- `0x140006620`
- `0x1400095bc`
- `0x1401bbbc2`
- `0x1401bbcb0`
- `0x1401bbe80`
- `0x1401bc040`
- `0x1401bc340`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400037ff`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400038cb`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140003aa7`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400037ff`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400038cb`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140003aa7`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140002ed6`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140002ed6`
- `NDIS!NdisFreeNetBufferListContext` at `0x140003d6e`
- `NDIS!NdisFreeNetBufferListContext` at `0x140003d6e`
- `NDIS!NdisAllocateNetBufferListContext` at `0x140003016`
- `NDIS!NdisAllocateNetBufferListContext` at `0x140003016`
- `NDIS!NdisFreeFragmentNetBufferList` at `0x140003d84`
- `NDIS!NdisFreeFragmentNetBufferList` at `0x140003d84`
- `NDIS!NdisAdvanceNetBufferListDataStart` at `0x140002ff6`
- `NDIS!NdisAdvanceNetBufferListDataStart` at `0x140002ff6`
- `NDIS!NdisCopySendNetBufferListInfo` at `0x140003774`
- `NDIS!NdisCopySendNetBufferListInfo` at `0x140003774`
- `NDIS!NdisCopyReceiveNetBufferListInfo` at `0x1400036da`
- `NDIS!NdisCopyReceiveNetBufferListInfo` at `0x1400036da`
- `NDIS!NdisGetDataBuffer` at `0x140003090`
- `NDIS!NdisGetDataBuffer` at `0x1400035e1`
- `NDIS!NdisGetDataBuffer` at `0x140003c3e`
- `NDIS!NdisGetDataBuffer` at `0x140003090`
- `NDIS!NdisGetDataBuffer` at `0x1400035e1`
- `NDIS!NdisGetDataBuffer` at `0x140003c3e`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x14000336e`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x140003386`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x1400033c3`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x1400033db`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x1400035bf`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x140003c1b`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x14000336e`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x140003386`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x1400033c3`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x1400033db`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x1400035bf`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x140003c1b`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x14000341d`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x140003435`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x14000360a`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x140003c68`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x14000341d`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x140003435`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x14000360a`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x140003c68`
- `NDIS!NdisAllocateFragmentNetBufferList` at `0x140002fd3`
- `NDIS!NdisAllocateFragmentNetBufferList` at `0x140002fd3`

## pseudocode

```c
__int64 __fastcall SegLibCreateMultiNbNblClone(
        __int64 a1,
        __int64 a2,
        char a3,
        __int64 a4,
        unsigned __int16 *a5,
        int a6,
        int a7,
        USHORT a8,
        int a9,
        __int64 a10,
        __int64 a11,
        int *a12)
{
  BOOL v14; // r9d
  __int64 v15; // rbx
  __int16 v16; // r13
  bool v17; // r10
  char v18; // di
  unsigned int v19; // eax
  int v20; // r8d
  __int64 v21; // rsi
  unsigned int v22; // r14d
  unsigned __int64 v23; // rcx
  __int64 v24; // rax
  void *v25; // rsp
  ULONG CurrentProcessorNumber; // eax
  int v27; // r8d
  bool v28; // cf
  struct _NET_BUFFER_LIST *v29; // r14
  PNET_BUFFER_LIST v30; // r13
  char v31; // r12
  NDIS_STATUS NetBufferListContext; // esi
  __int64 v33; // r8
  unsigned __int16 v34; // r15
  struct _NET_BUFFER_LIST *FragmentNetBufferList; // rax
  unsigned __int16 v36; // bx
  struct _NET_BUFFER *FirstNetBuffer; // r12
  unsigned __int16 v38; // si
  size_t v39; // rdi
  char *DataBuffer; // rax
  __int64 v41; // rdx
  __int64 v42; // r8
  __int64 v43; // r9
  void *v44; // r15
  unsigned __int8 v45; // cl
  PNET_BUFFER_LIST v46; // rbx
  __int64 v47; // rcx
  __int64 v48; // rax
  unsigned int v49; // eax
  int *v50; // rdx
  unsigned int v51; // ebx
  __int64 v52; // r8
  __int64 v53; // rax
  __int64 v54; // rcx
  __int64 v55; // rcx
  __int64 v56; // rax
  unsigned __int16 *v57; // rdi
  char *v58; // rdx
  __int64 v59; // rcx
  volatile signed __int16 *v60; // rax
  unsigned int v61; // eax
  int *v62; // r8
  unsigned int v63; // ebx
  __int64 v64; // rax
  __int64 v65; // rdx
  __int64 v66; // rcx
  __int64 v67; // rdx
  __int64 v68; // rcx
  __int64 v69; // rdx
  void *v70; // r9
  char v71; // bl
  ULONG v72; // ebx
  int v73; // edi
  NDIS_STATUS v74; // eax
  ULONG v75; // ebx
  __int64 v76; // rcx
  __int64 v77; // rax
  unsigned int v78; // eax
  int *v79; // rdx
  unsigned int v80; // ebx
  __int64 v81; // rax
  __int64 v82; // r8
  __int64 v83; // rcx
  __int64 v84; // r8
  __int64 v85; // rcx
  __int64 v86; // rax
  void *v87; // rdx
  ULONG v88; // ebx
  struct _NET_BUFFER *v89; // rcx
  ULONG v90; // edx
  __int16 v92; // di
  bool v93; // di
  $A748D0D663C15BE980B604C3B1026F20 *Alignment; // rbx
  char v95; // di
  __int16 v96; // r12
  _QWORD *v97; // rax
  _DWORD *v98; // rcx
  __int64 v99; // rax
  _DWORD *v100; // rax
  int v101; // ecx
  __int64 v102; // rax
  __int64 v103; // r8
  volatile signed __int32 *v104; // rcx
  __int64 v105; // r8
  _DWORD *v106; // rax
  int v107; // ecx
  __int64 v108; // rax
  __int64 v109; // rdx
  volatile signed __int32 *v110; // rcx
  __int64 v111; // rdx
  __int64 v112; // rdx
  __int64 v113; // rdx
  _DWORD *v114; // rax
  int v115; // ecx
  __int64 v116; // rax
  __int64 v117; // r8
  volatile signed __int32 *v118; // rcx
  __int64 v119; // r8
  __int64 v120; // rdx
  unsigned int v121; // r10d
  PVOID v122; // rax
  __int16 DataOffsetDeltaa; // [rsp+28h] [rbp-18h]
  ULONG DataOffsetDelta; // [rsp+28h] [rbp-18h]
  char v125; // [rsp+40h] [rbp+0h] BYREF
  char v126; // [rsp+41h] [rbp+1h]
  char v127; // [rsp+42h] [rbp+2h]
  bool v128; // [rsp+43h] [rbp+3h]
  unsigned __int16 v129; // [rsp+44h] [rbp+4h]
  void *v130; // [rsp+48h] [rbp+8h]
  void *v131; // [rsp+50h] [rbp+10h]
  PNET_BUFFER_LIST OriginalNetBufferList; // [rsp+58h] [rbp+18h]
  ULONG Size; // [rsp+60h] [rbp+20h]
  int Size_4; // [rsp+64h] [rbp+24h]
  unsigned int v135; // [rsp+68h] [rbp+28h]
  int v136; // [rsp+6Ch] [rbp+2Ch]
  int v137; // [rsp+70h] [rbp+30h]
  __int16 v138[2]; // [rsp+74h] [rbp+34h]
  ULONG MaximumLength[8]; // [rsp+78h] [rbp+38h] BYREF
  void *v140; // [rsp+98h] [rbp+58h]
  void *Src; // [rsp+A0h] [rbp+60h]
  __int64 v142; // [rsp+A8h] [rbp+68h]
  __int64 v143; // [rsp+B0h] [rbp+70h]
  int v144[24]; // [rsp+C0h] [rbp+80h] BYREF

  OriginalNetBufferList = (PNET_BUFFER_LIST)a2;
  v142 = a10;
  memset(MaximumLength, 0, 28);
  v143 = a11;
  memset(v144, 0, sizeof(v144));
  LOBYTE(v135) = 0;
  LOBYTE(v14) = 0;
  *(_DWORD *)v138 = 0;
  v15 = 0;
  v128 = 0;
  v16 = 0;
  Size_4 = v14;
  v17 = 0;
  v18 = 0;
  if ( a5 )
  {
    v92 = *a5;
    v19 = *a5;
    v17 = ((*((_DWORD *)a5 + 7) - 1) & 0xFFFFFFFD) == 0;
    v128 = v17;
    LOWORD(v19) = v92 & 1;
    if ( (v92 & 1) != 0 )
    {
      v15 = *((_QWORD *)a5 + 1);
      v16 = a5[8];
    }
    v18 = (v92 & 4) != 0;
    if ( (_WORD)v19 )
      goto LABEL_100;
  }
  v19 = *(_DWORD *)(a2 + 160);
  if ( v19 )
  {
LABEL_100:
    if ( !v17 )
    {
      v14 = v18 == 0;
      Size_4 = v14;
    }
    v20 = 1;
  }
  else
  {
    v20 = 0;
  }
  if ( v17 )
  {
LABEL_5:
    if ( !v14 )
      goto LABEL_7;
    goto LABEL_6;
  }
  if ( !a5 || (*(_BYTE *)a5 & 2) == 0 )
  {
    if ( *(_DWORD *)(a2 + 160) )
      goto LABEL_5;
    v99 = *(_QWORD *)(a2 + 144);
    if ( (v99 & 0x1C) == 0 )
    {
      LOBYTE(Size_4) = 0;
      goto LABEL_7;
    }
    LOBYTE(Size_4) = 1;
    v121 = (unsigned int)v99 >> 1;
    LOBYTE(v121) = (v99 & 2) != 0;
    v135 = v121;
    if ( (v99 & 4) != 0 )
      v138[0] = WORD1(v99) & 0x3FF;
    else
      v135 = v121;
LABEL_6:
    v20 |= 2u;
    goto LABEL_7;
  }
  LOBYTE(Size_4) = *((_BYTE *)a5 + 27);
  if ( (_BYTE)Size_4 )
  {
    LOBYTE(v19) = *((_BYTE *)a5 + 26);
    v135 = v19;
    *(_DWORD *)v138 = a5[12];
    goto LABEL_6;
  }
LABEL_7:
  if ( a12 )
    *a12 = v20;
  v21 = qword_140224C88;
  v22 = 4;
  if ( qword_140224C88 && *(_BYTE *)(qword_140224C88 + 48) )
    v22 = *(_DWORD *)(qword_140224C88 + 16);
  v23 = 24LL * v22;
  v24 = v23 + 15;
  if ( v23 + 15 < v23 )
    v24 = 0xFFFFFFFFFFFFFF0LL;
  v25 = alloca(v24 & 0xFFFFFFFFFFFFFFF0uLL);
  if ( a3 != 1 || (v27 = 0, *(_QWORD *)(qword_140224C88 + 32)) )
  {
    v144[0] = -267522035;
    CurrentProcessorNumber = KeGetCurrentProcessorNumberEx(0);
    v27 = 0;
    v144[3] = CurrentProcessorNumber;
    LOBYTE(v144[1]) = 0;
    *(_QWORD *)&v144[6] = 0;
    v14 = 1;
    v144[2] = a3 & 1;
    v28 = *(_QWORD *)(v21 + 32) != 0;
    *(_QWORD *)&v144[4] = 1;
    memset(&v144[11], 0, 24);
    LOBYTE(v144[10]) = 0;
    v144[2] |= v28 ? 4 : 0;
    *(_QWORD *)&v144[8] = &v144[14];
    if ( &v125 )
    {
      v144[17] = v22;
      *(_QWORD *)&v144[18] = &v125;
    }
    else
    {
      v144[17] = 0;
      *(_QWORD *)&v144[18] = 0;
    }
    *(_QWORD *)&v144[20] = v21;
  }
  DataOffsetDeltaa = v16;
  v29 = 0;
  v30 = OriginalNetBufferList;
  v31 = 0;
  LOBYTE(v27) = 14;
  NetBufferListContext = SegLibPvtLsoInitialize(
                           (unsigned int)MaximumLength,
                           (_DWORD)OriginalNetBufferList,
                           v27,
                           v14,
                           v15,
                           DataOffsetDeltaa,
                           v18);
  if ( NetBufferListContext < 0 )
  {
LABEL_184:
    v34 = MaximumLength[6];
  }
  else
  {
    v34 = MaximumLength[6];
    FragmentNetBufferList = NdisAllocateFragmentNetBufferList(
                              v30,
                              0,
                              0,
                              LOWORD(MaximumLength[6]),
                              MaximumLength[0],
                              LOWORD(MaximumLength[6]),
                              0,
                              0);
    v29 = FragmentNetBufferList;
    if ( FragmentNetBufferList )
    {
      NdisAdvanceNetBufferListDataStart(FragmentNetBufferList, 0, 0, 0);
      if ( !a8
        || (NetBufferListContext = NdisAllocateNetBufferListContext(v29, a8, 0, 0x6C6F734Cu), NetBufferListContext >= 0) )
      {
        v36 = HIWORD(MaximumLength[5]);
        FirstNetBuffer = v29->FirstNetBuffer;
        v38 = HIWORD(MaximumLength[5]) - BYTE2(MaximumLength[6]);
        v126 = 0;
        v125 = 1;
        v140 = 0;
        Size = (unsigned __int16)(v34 - HIWORD(MaximumLength[5]));
        Src = 0;
        OriginalNetBufferList = 0;
        v127 = 0;
        v136 = 0;
        v137 = 0;
        v129 = v38;
        while ( FirstNetBuffer )
        {
          v39 = v34;
          DataBuffer = (char *)NdisGetDataBuffer(FirstNetBuffer, v34, 0, 1u, 0);
          v43 = 0;
          v44 = DataBuffer;
          if ( DataBuffer )
          {
            v45 = BYTE2(MaximumLength[6]);
            v131 = &DataBuffer[BYTE2(MaximumLength[6])];
            v130 = &DataBuffer[v36];
          }
          else
          {
            v88 = BYTE2(MaximumLength[6]);
            NdisAdvanceNetBufferDataStart(FirstNetBuffer, BYTE2(MaximumLength[6]), 0, 0);
            v131 = NdisGetDataBuffer(FirstNetBuffer, v38, 0, 1u, 0);
            v89 = FirstNetBuffer;
            if ( !v131 )
            {
              v90 = v88;
LABEL_91:
              NetBufferListContext = -1073741670;
              NdisRetreatNetBufferDataStart(v89, v90, 0, 0);
LABEL_92:
              v34 = MaximumLength[6];
LABEL_93:
              v31 = v125;
              goto LABEL_94;
            }
            NdisAdvanceNetBufferDataStart(FirstNetBuffer, v38, 0, 0);
            v122 = NdisGetDataBuffer(FirstNetBuffer, Size, 0, 1u, 0);
            v90 = HIWORD(MaximumLength[5]);
            v130 = v122;
            v89 = FirstNetBuffer;
            if ( !v122 )
              goto LABEL_91;
            v126 = 1;
            NdisRetreatNetBufferDataStart(FirstNetBuffer, HIWORD(MaximumLength[5]), 0, 0);
            v45 = BYTE2(MaximumLength[6]);
            v43 = 0;
          }
          v46 = OriginalNetBufferList;
          if ( OriginalNetBufferList )
          {
            if ( v127 || v126 )
            {
              v47 = *(_QWORD *)&v144[20];
              if ( *(_BYTE *)(*(_QWORD *)&v144[20] + 1LL) == 1 && !LOBYTE(v144[1]) )
              {
                v48 = 0;
                LOBYTE(v144[1]) = 1;
                if ( v144[3] != -1 )
                {
                  v41 = *(_QWORD *)(*(_QWORD *)&v144[20] + 24LL);
                  if ( v41 )
                    v48 = v41 + 20LL * (unsigned int)v144[3];
                }
                _InterlockedAdd16((volatile signed __int16 *)(v48 + 16), 1u);
                v47 = *(_QWORD *)&v144[20];
              }
              v49 = *(_DWORD *)(v47 + 4);
              if ( v49 )
              {
                v50 = *(int **)&v144[8];
                v51 = *(_DWORD *)(*(_QWORD *)&v144[8] + 8LL);
                if ( v51 >= *(_DWORD *)(*(_QWORD *)&v144[8] + 12LL) )
                {
                  v51 = 0;
                  if ( v144[4] < v49
                    && (v100 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v47 + 64)),
                        v43 = 0,
                        (v50 = v100) != 0) )
                  {
                    *(_QWORD *)v100 = 0;
                    v100[2] = 0;
                    v101 = *(_DWORD *)(*(_QWORD *)&v144[20] + 8LL);
                    *((_QWORD *)v100 + 2) = v100 + 6;
                    v100[3] = v101;
                    **(_QWORD **)&v144[8] = v100;
                    ++v144[4];
                    *(_QWORD *)&v144[8] = v100;
                    if ( *(_BYTE *)(*(_QWORD *)&v144[20] + 1LL) == 1 )
                    {
                      v102 = 0;
                      if ( v144[3] != -1 )
                      {
                        v103 = *(_QWORD *)(*(_QWORD *)&v144[20] + 24LL);
                        if ( v103 )
                          v102 = v103 + 20LL * (unsigned int)v144[3];
                      }
                      _InterlockedAdd16((volatile signed __int16 *)(v102 + 12), 1u);
                      v104 = 0;
                      if ( v144[3] != -1 )
                      {
                        v105 = *(_QWORD *)(*(_QWORD *)&v144[20] + 24LL);
                        if ( v105 )
                          v104 = (volatile signed __int32 *)(v105 + 20LL * (unsigned int)v144[3]);
                      }
                      _InterlockedAdd(v104, 1u);
                    }
                  }
                  else
                  {
                    LOBYTE(v50) = 1;
                    BLFlushBatchOpContextEx(v144, v50, 0);
                    v50 = &v144[14];
                    v43 = 0;
                  }
                }
                ++v144[5];
                ++v50[2];
                v52 = *(_QWORD *)&v144[20];
                if ( *(_BYTE *)(*(_QWORD *)&v144[20] + 1LL) == 1 )
                {
                  v53 = 0;
                  if ( v144[3] != -1 )
                  {
                    v52 = *(_QWORD *)(*(_QWORD *)&v144[20] + 24LL);
                    if ( v52 )
                      v53 = v52 + 20LL * (unsigned int)v144[3];
                  }
                  _InterlockedAdd16((volatile signed __int16 *)(v53 + 14), 1u);
                  v54 = 0;
                  if ( v144[3] != -1 )
                  {
                    v52 = *(_QWORD *)(*(_QWORD *)&v144[20] + 24LL);
                    if ( v52 )
                      v54 = v52 + 20LL * (unsigned int)v144[3];
                  }
                  _InterlockedAdd((volatile signed __int32 *)(v54 + 4), 1u);
                }
                v55 = 3LL * v51;
                v56 = *((_QWORD *)v50 + 2);
                v57 = (unsigned __int16 *)v131;
                v58 = (char *)Src;
                v46 = OriginalNetBufferList;
                *(_QWORD *)(v56 + 8 * v55) = v131;
                *(_DWORD *)(v56 + 8 * v55 + 16) = (16 * v38) | 1;
                *(_QWORD *)(v56 + 8 * v55 + 8) = v58;
              }
              else
              {
                if ( v144[5] )
                {
                  LOBYTE(v41) = 1;
                  BLFlushBatchOpContextEx(v144, v41, 0);
                  v47 = *(_QWORD *)&v144[20];
                }
                v112 = (unsigned int)v144[2];
                if ( (v144[2] & 5) == 5 || (v112 = v144[2] & 6, (v144[2] & 6) == 6) )
                {
                  (*(void (__fastcall **)(__int64, __int64, __int64, __int64))(v47 + 32))(v47, v112, v42, v43);
                  memmove(v131, Src, v129);
                  (*(void (**)(void))(*(_QWORD *)&v144[20] + 40LL))();
                }
                else
                {
                  memmove(v131, Src, v129);
                }
                v57 = (unsigned __int16 *)v131;
              }
              v59 = *(_QWORD *)&v144[20];
              if ( *(_BYTE *)(*(_QWORD *)&v144[20] + 1LL) == 1 && !LOBYTE(v144[1]) )
              {
                v60 = 0;
                LOBYTE(v144[1]) = 1;
                if ( v144[3] != -1 )
                {
                  v58 = *(char **)(*(_QWORD *)&v144[20] + 24LL);
                  if ( v58 )
                    v60 = (volatile signed __int16 *)&v58[20 * v144[3]];
                }
                _InterlockedAdd16(v60 + 8, 1u);
                v59 = *(_QWORD *)&v144[20];
              }
              v61 = *(_DWORD *)(v59 + 4);
              if ( v61 )
              {
                v62 = *(int **)&v144[8];
                v63 = *(_DWORD *)(*(_QWORD *)&v144[8] + 8LL);
                if ( v63 >= *(_DWORD *)(*(_QWORD *)&v144[8] + 12LL) )
                {
                  v63 = 0;
                  if ( v144[4] < v61
                    && (v106 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v59 + 64)), (v62 = v106) != 0) )
                  {
                    *(_QWORD *)v106 = 0;
                    v106[2] = 0;
                    v107 = *(_DWORD *)(*(_QWORD *)&v144[20] + 8LL);
                    *((_QWORD *)v106 + 2) = v106 + 6;
                    v106[3] = v107;
                    **(_QWORD **)&v144[8] = v106;
                    ++v144[4];
                    *(_QWORD *)&v144[8] = v106;
                    if ( *(_BYTE *)(*(_QWORD *)&v144[20] + 1LL) == 1 )
                    {
                      v108 = 0;
                      if ( v144[3] != -1 )
                      {
                        v109 = *(_QWORD *)(*(_QWORD *)&v144[20] + 24LL);
                        if ( v109 )
                          v108 = v109 + 20LL * (unsigned int)v144[3];
                      }
                      _InterlockedAdd16((volatile signed __int16 *)(v108 + 12), 1u);
                      v110 = 0;
                      if ( v144[3] != -1 )
                      {
                        v111 = *(_QWORD *)(*(_QWORD *)&v144[20] + 24LL);
                        if ( v111 )
                          v110 = (volatile signed __int32 *)(v111 + 20LL * (unsigned int)v144[3]);
                      }
                      _InterlockedAdd(v110, 1u);
                    }
                  }
                  else
                  {
                    LOBYTE(v58) = 1;
                    BLFlushBatchOpContextEx(v144, v58, 0);
                    v62 = &v144[14];
                  }
                }
                ++v144[5];
                ++v62[2];
                if ( *(_BYTE *)(*(_QWORD *)&v144[20] + 1LL) == 1 )
                {
                  v64 = 0;
                  if ( v144[3] != -1 )
                  {
                    v65 = *(_QWORD *)(*(_QWORD *)&v144[20] + 24LL);
                    if ( v65 )
                      v64 = v65 + 20LL * (unsigned int)v144[3];
                  }
                  _InterlockedAdd16((volatile signed __int16 *)(v64 + 14), 1u);
                  v66 = 0;
                  if ( v144[3] != -1 )
                  {
                    v67 = *(_QWORD *)(*(_QWORD *)&v144[20] + 24LL);
                    if ( v67 )
                      v66 = v67 + 20LL * (unsigned int)v144[3];
                  }
                  _InterlockedAdd((volatile signed __int32 *)(v66 + 4), 1u);
                }
                v68 = *((_QWORD *)v62 + 2);
                v69 = 3LL * v63;
                *(_QWORD *)(v68 + 8 * v69) = v130;
                *(_QWORD *)(v68 + 8 * v69 + 8) = OriginalNetBufferList;
                *(_DWORD *)(v68 + 8 * v69 + 16) = (16 * Size) | 1;
              }
              else
              {
                if ( v144[5] )
                {
                  LOBYTE(v58) = 1;
                  BLFlushBatchOpContextEx(v144, v58, 0);
                  v59 = *(_QWORD *)&v144[20];
                }
                v113 = (unsigned int)v144[2];
                if ( (v144[2] & 5) == 5 || (v113 = v144[2] & 6, (v144[2] & 6) == 6) )
                {
                  (*(void (__fastcall **)(__int64, __int64, __int64, __int64))(v59 + 32))(v59, v113, v52, v43);
                  memmove(v130, v46, Size);
                  (*(void (**)(void))(*(_QWORD *)&v144[20] + 40LL))();
                }
                else
                {
                  memmove(v130, v46, Size);
                }
              }
            }
            else
            {
              v76 = *(_QWORD *)&v144[20];
              if ( *(_BYTE *)(*(_QWORD *)&v144[20] + 1LL) == 1 && !LOBYTE(v144[1]) )
              {
                v77 = 0;
                LOBYTE(v144[1]) = 1;
                if ( v144[3] != -1 )
                {
                  v41 = *(_QWORD *)(*(_QWORD *)&v144[20] + 24LL);
                  if ( v41 )
                    v77 = v41 + 20LL * (unsigned int)v144[3];
                }
                _InterlockedAdd16((volatile signed __int16 *)(v77 + 16), 1u);
                v76 = *(_QWORD *)&v144[20];
              }
              v78 = *(_DWORD *)(v76 + 4);
              if ( v78 )
              {
                v79 = *(int **)&v144[8];
                v80 = *(_DWORD *)(*(_QWORD *)&v144[8] + 8LL);
                if ( v80 >= *(_DWORD *)(*(_QWORD *)&v144[8] + 12LL) )
                {
                  v80 = 0;
                  if ( v144[4] < v78
                    && (v114 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v76 + 64)), (v79 = v114) != 0) )
                  {
                    *(_QWORD *)v114 = 0;
                    v114[2] = 0;
                    v115 = *(_DWORD *)(*(_QWORD *)&v144[20] + 8LL);
                    *((_QWORD *)v114 + 2) = v114 + 6;
                    v114[3] = v115;
                    **(_QWORD **)&v144[8] = v114;
                    ++v144[4];
                    *(_QWORD *)&v144[8] = v114;
                    if ( *(_BYTE *)(*(_QWORD *)&v144[20] + 1LL) == 1 )
                    {
                      v116 = 0;
                      if ( v144[3] != -1 )
                      {
                        v117 = *(_QWORD *)(*(_QWORD *)&v144[20] + 24LL);
                        if ( v117 )
                          v116 = v117 + 20LL * (unsigned int)v144[3];
                      }
                      _InterlockedAdd16((volatile signed __int16 *)(v116 + 12), 1u);
                      v118 = 0;
                      if ( v144[3] != -1 )
                      {
                        v119 = *(_QWORD *)(*(_QWORD *)&v144[20] + 24LL);
                        if ( v119 )
                          v118 = (volatile signed __int32 *)(v119 + 20LL * (unsigned int)v144[3]);
                      }
                      _InterlockedAdd(v118, 1u);
                    }
                  }
                  else
                  {
                    LOBYTE(v79) = 1;
                    BLFlushBatchOpContextEx(v144, v79, 0);
                    v79 = &v144[14];
                  }
                }
                ++v144[5];
                ++v79[2];
                if ( *(_BYTE *)(*(_QWORD *)&v144[20] + 1LL) == 1 )
                {
                  v81 = 0;
                  if ( v144[3] != -1 )
                  {
                    v82 = *(_QWORD *)(*(_QWORD *)&v144[20] + 24LL);
                    if ( v82 )
                      v81 = v82 + 20LL * (unsigned int)v144[3];
                  }
                  _InterlockedAdd16((volatile signed __int16 *)(v81 + 14), 1u);
                  v83 = 0;
                  if ( v144[3] != -1 )
                  {
                    v84 = *(_QWORD *)(*(_QWORD *)&v144[20] + 24LL);
                    if ( v84 )
                      v83 = v84 + 20LL * (unsigned int)v144[3];
                  }
                  _InterlockedAdd((volatile signed __int32 *)(v83 + 4), 1u);
                }
                v85 = 3LL * v80;
                v86 = *((_QWORD *)v79 + 2);
                v87 = v140;
                *(_QWORD *)(v86 + 8 * v85) = v44;
                *(_DWORD *)(v86 + 8 * v85 + 16) = (16 * v39) | 1;
                v57 = (unsigned __int16 *)v131;
                *(_QWORD *)(v86 + 8 * v85 + 8) = v87;
              }
              else
              {
                if ( v144[5] )
                {
                  LOBYTE(v41) = 1;
                  BLFlushBatchOpContextEx(v144, v41, 0);
                  v76 = *(_QWORD *)&v144[20];
                }
                v120 = (unsigned int)v144[2];
                if ( (v144[2] & 5) == 5 || (v120 = v144[2] & 6, (v144[2] & 6) == 6) )
                {
                  (*(void (__fastcall **)(__int64, __int64, __int64, __int64))(v76 + 32))(v76, v120, v42, v43);
                  memmove(v44, v140, v39);
                  (*(void (**)(void))(*(_QWORD *)&v144[20] + 40LL))();
                }
                else
                {
                  memmove(v44, v140, v39);
                }
                v57 = (unsigned __int16 *)v131;
              }
            }
            v70 = v130;
          }
          else
          {
            v71 = v126;
            if ( v126 )
            {
              v72 = v45;
              NdisAdvanceNetBufferDataStart(FirstNetBuffer, v45, 0, 0);
              NdisAdvanceNetBufferDataStart(v30->FirstNetBuffer, v72, 0, 0);
              v73 = SegLibPvtDeferredCopyMdlChainData(
                      v144,
                      *(_QWORD *)(v30->Link.Region + 8),
                      *(unsigned int *)(v30->Link.Region + 16),
                      v38,
                      v131);
              NdisAdvanceNetBufferDataStart(FirstNetBuffer, v38, 0, 0);
              NdisAdvanceNetBufferDataStart(v30->FirstNetBuffer, v38, 0, 0);
              v74 = SegLibPvtDeferredCopyMdlChainData(
                      v144,
                      *(_QWORD *)(v30->Link.Region + 8),
                      *(unsigned int *)(v30->Link.Region + 16),
                      Size,
                      v130);
              v75 = HIWORD(MaximumLength[5]);
              NetBufferListContext = v74;
              NdisRetreatNetBufferDataStart(FirstNetBuffer, HIWORD(MaximumLength[5]), 0, 0);
              NdisRetreatNetBufferDataStart(v30->FirstNetBuffer, v75, 0, 0);
              if ( v73 < 0 )
                goto LABEL_92;
              v71 = v126;
            }
            else
            {
              NetBufferListContext = SegLibPvtDeferredCopyMdlChainData(
                                       v144,
                                       *(_QWORD *)(v30->Link.Region + 8),
                                       *(unsigned int *)(v30->Link.Region + 16),
                                       (unsigned int)v39,
                                       v44);
            }
            if ( NetBufferListContext < 0 )
              goto LABEL_92;
            LOBYTE(v33) = 1;
            BLFlushBatchOpContextEx(v144, 0, v33);
            NetBufferListContext = SegLibPvtParseHeaders(MaximumLength, v131, v130);
            if ( NetBufferListContext < 0 )
            {
              v31 = v125;
              goto LABEL_184;
            }
            v57 = (unsigned __int16 *)v131;
            v70 = v130;
            v140 = v44;
            Src = v131;
            OriginalNetBufferList = (PNET_BUFFER_LIST)v130;
            v127 = v71;
          }
          SegLibPvtLsoDeferredFixHeaders((__int64)v144, (__int64)MaximumLength, v57, (__int64)v70, v136++, v137);
          FirstNetBuffer = (struct _NET_BUFFER *)FirstNetBuffer->Link.Alignment;
          v36 = HIWORD(MaximumLength[5]);
          v34 = MaximumLength[6];
          v38 = v129;
          v137 += MaximumLength[0];
        }
        v93 = v128;
        NetBufferListContext = 0;
        if ( v128 )
        {
          NdisCopyReceiveNetBufferListInfo(v29, v30);
        }
        else
        {
          NdisCopySendNetBufferListInfo(v29, v30);
          v29->NetBufferListInfo[2] = 0;
        }
        if ( (_BYTE)Size_4 )
        {
          Alignment = ($A748D0D663C15BE980B604C3B1026F20 *)v29->FirstNetBuffer;
          v95 = v135;
          v96 = v138[0];
          while ( Alignment )
          {
            LOBYTE(DataOffsetDelta) = v95;
            OriginalNetBufferList = (PNET_BUFFER_LIST)(((MaximumLength[6] & 0x1000000) == 0)
                                                     | (2
                                                      * (HIBYTE(MaximumLength[6]) & 1
                                                       | ((unsigned __int16)(HIWORD(MaximumLength[5]) & 0x3FF) << 15)))
                                                     | 4LL);
            NetBufferListContext = SegLibDeferredChecksumPacket((int)v144, (int)Alignment, v96, DataOffsetDelta);
            if ( NetBufferListContext < 0 )
              goto LABEL_93;
            Alignment = ($A748D0D663C15BE980B604C3B1026F20 *)Alignment->Link.Alignment;
            NetBufferListContext = 0;
          }
          v29->NetBufferListInfo[0] = 0;
        }
        else if ( !v93 )
        {
          OriginalNetBufferList = (PNET_BUFFER_LIST)(((MaximumLength[6] & 0x1000000) == 0)
                                                   | (2
                                                    * (HIBYTE(MaximumLength[6]) & 1
                                                     | ((unsigned __int16)(v36 & 0x3FF) << 15)))
                                                   | 4LL);
          v29->NetBufferListInfo[0] = OriginalNetBufferList;
        }
        v97 = (_QWORD *)v142;
        v98 = (_DWORD *)v143;
        v29->ParentNetBufferList = v30;
        *v97 = v29;
        *v98 = v34;
        goto LABEL_93;
      }
    }
    else
    {
      NetBufferListContext = -1073741670;
    }
  }
LABEL_94:
  LOBYTE(v33) = 1;
  BLFlushBatchOpContextEx(v144, 0, v33);
  if ( NetBufferListContext < 0 && v29 )
  {
    if ( v31 )
      NdisFreeNetBufferListContext(v29, a8);
    NdisFreeFragmentNetBufferList(v29, v34, 0);
  }
  return (unsigned int)NetBufferListContext;
}

```

## disassembly

```asm
0x140002da4  push    rbp
0x140002da6  push    rbx
0x140002da7  push    rsi
0x140002da8  push    rdi
0x140002da9  push    r12
0x140002dab  push    r13
0x140002dad  push    r14
0x140002daf  push    r15
0x140002db1  sub     rsp, 138h
0x140002db8  lea     rbp, [rsp+40h]
0x140002dbd  mov     rax, cs:__security_cookie
0x140002dc4  xor     rax, rbp
0x140002dc7  mov     [rbp+130h+var_50], rax
0x140002dce  mov     rax, [rbp+130h+arg_48]
0x140002dd5  lea     rcx, [rbp+130h+var_B0]; void *
0x140002ddc  mov     rsi, [rbp+130h+arg_58]
0x140002de3  xorps   xmm0, xmm0
0x140002de6  mov     r14, rdx
0x140002de9  mov     [rbp+130h+OriginalNetBufferList], rdx
0x140002ded  xor     edx, edx; Val
0x140002def  mov     [rbp+130h+var_C8], rax
0x140002df3  mov     rax, [rbp+130h+arg_50]
0x140002dfa  movzx   r12d, r8b
0x140002dfe  movups  xmmword ptr [rbp+130h+var_F8], xmm0
0x140002e02  lea     r8d, [rdx+60h]; Size
0x140002e06  mov     [rbp+130h+var_C0], rax
0x140002e0a  movups  xmmword ptr [rbp+130h+var_F8+0Ch], xmm0
0x140002e0e  call    memset
0x140002e13  mov     rdx, [rbp+130h+arg_20]
0x140002e1a  xor     r11d, r11d
0x140002e1d  mov     byte ptr [rbp+130h+var_108], r11b
0x140002e21  mov     r9b, r11b
0x140002e24  mov     dword ptr [rbp+130h+var_FC], r11d
0x140002e28  mov     ebx, r11d
0x140002e2b  mov     [rbp+130h+var_12D], r11b
0x140002e2f  mov     r13d, r11d
0x140002e32  mov     dword ptr [rbp+130h+Size+4], r9d
0x140002e36  lea     r15d, [r11+1]
0x140002e3a  mov     r10b, r11b
0x140002e3d  mov     dil, r11b
0x140002e40  test    rdx, rdx
0x140002e43  jnz     loc_140003671
0x140002e49  mov     eax, [r14+0A0h]
0x140002e50  test    eax, eax
0x140002e52  jnz     loc_1400036A9
0x140002e58  mov     r8d, r11d
0x140002e5b  test    r10b, r10b
0x140002e5e  jz      loc_1400037B8
0x140002e64  test    r9b, r9b
0x140002e67  jz      short loc_140002E6D
0x140002e69  or      r8d, 2
0x140002e6d  test    rsi, rsi
0x140002e70  jz      short loc_140002E75
0x140002e72  mov     [rsi], r8d
0x140002e75  mov     rsi, cs:qword_140224C88
0x140002e7c  mov     r14d, 4
0x140002e82  test    rsi, rsi
0x140002e85  jz      short loc_140002E91
0x140002e87  cmp     [rsi+30h], r11b
0x140002e8b  jz      short loc_140002E91
0x140002e8d  mov     r14d, [rsi+10h]
0x140002e91  mov     eax, r14d
0x140002e94  lea     rcx, [rax+rax*2]
0x140002e98  shl     rcx, 3
0x140002e9c  lea     rax, [rcx+0Fh]
0x140002ea0  cmp     rax, rcx
0x140002ea3  ja      short loc_140002EAF
0x140002ea5  mov     rax, 0FFFFFFFFFFFFFF0h
0x140002eaf  and     rax, 0FFFFFFFFFFFFFFF0h
0x140002eb3  call    __chkstk_0
0x140002eb8  sub     rsp, rax
0x140002ebb  lea     r15, [rsp+170h+var_130]
0x140002ec0  cmp     r12b, 1
0x140002ec4  jz      loc_140003762
0x140002eca  xor     ecx, ecx; ProcNumber
0x140002ecc  mov     [rbp+130h+var_B0], 0F00DF00Dh
0x140002ed6  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140002edd  nop     dword ptr [rax+rax+00h]
0x140002ee2  xor     r8d, r8d
0x140002ee5  mov     [rbp+130h+var_A4], eax
0x140002eeb  mov     edx, r12d
0x140002eee  mov     [rbp+130h+var_AC], r8b
0x140002ef5  mov     [rbp+130h+var_98], r8
0x140002efc  lea     r9d, [r8+1]
0x140002f00  and     edx, r9d
0x140002f03  mov     [rbp+130h+var_A8], edx
0x140002f09  mov     rax, [rsi+20h]
0x140002f0d  neg     rax
0x140002f10  mov     [rbp+130h+var_A0], r9
0x140002f17  lea     rax, [rbp+130h+var_78]
0x140002f1e  mov     [rbp+130h+var_80], r8
0x140002f25  sbb     ecx, ecx
0x140002f27  mov     [rbp+130h+var_84], r8d
0x140002f2e  and     ecx, 4
0x140002f31  mov     [rbp+130h+var_88], r8b
0x140002f38  or      ecx, edx
0x140002f3a  mov     [rbp+130h+var_78], r8
0x140002f41  mov     [rbp+130h+var_A8], ecx
0x140002f47  mov     [rbp+130h+var_70], r8d
0x140002f4e  mov     [rbp+130h+var_90], rax
0x140002f55  test    r15, r15
0x140002f58  jz      loc_14000365E
0x140002f5e  mov     [rbp+130h+var_6C], r14d
0x140002f65  mov     [rbp+130h+var_68], r15
0x140002f6c  mov     [rbp+130h+var_60], rsi
0x140002f73  mov     byte ptr [rsp+170h+DataBackFill], dil
0x140002f78  lea     rcx, [rbp+130h+var_F8]
0x140002f7c  mov     word ptr [rsp+170h+DataOffsetDelta], r13w
0x140002f82  mov     r14, r8
0x140002f85  mov     r13, [rbp+130h+OriginalNetBufferList]
0x140002f89  mov     r12b, r8b
0x140002f8c  mov     rdx, r13
0x140002f8f  mov     qword ptr [rsp+170h+MaximumLength], rbx
0x140002f94  mov     r8b, 0Eh
0x140002f97  call    SegLibPvtLsoInitialize
0x140002f9c  movzx   ebx, [rbp+130h+arg_38]
0x140002fa3  xor     edi, edi
0x140002fa5  mov     esi, eax
0x140002fa7  test    eax, eax
0x140002fa9  js      loc_140003D4C
0x140002faf  movzx   r15d, [rbp+130h+var_E0]
0x140002fb4  xor     r8d, r8d; NetBufferPool
0x140002fb7  mov     eax, [rbp+130h+var_F8]
0x140002fba  mov     r9d, r15d; StartOffset
0x140002fbd  mov     [rsp+170h+AllocateFragmentFlags], edi; AllocateFragmentFlags
0x140002fc1  xor     edx, edx; NetBufferListPool
0x140002fc3  mov     [rsp+170h+DataBackFill], edi; DataBackFill
0x140002fc7  mov     rcx, r13; OriginalNetBufferList
0x140002fca  mov     [rsp+170h+DataOffsetDelta], r15d; DataOffsetDelta
0x140002fcf  mov     [rsp+170h+MaximumLength], eax; MaximumLength
0x140002fd3  call    cs:__imp_NdisAllocateFragmentNetBufferList
0x140002fda  nop     dword ptr [rax+rax+00h]
0x140002fdf  mov     r14, rax
0x140002fe2  test    rax, rax
0x140002fe5  jz      loc_140003C0F
0x140002feb  xor     r9d, r9d; FreeMdlMdlHandler
0x140002fee  xor     r8d, r8d; FreeMdl
0x140002ff1  xor     edx, edx; DataOffsetDelta
0x140002ff3  mov     rcx, rax; NetBufferList
0x140002ff6  call    cs:__imp_NdisAdvanceNetBufferListDataStart
0x140002ffd  nop     dword ptr [rax+rax+00h]
0x140003002  test    bx, bx
0x140003005  jz      short loc_14000302C
0x140003007  xor     r8d, r8d; ContextBackFill
0x14000300a  mov     r9d, 6C6F734Ch; PoolTag
0x140003010  movzx   edx, bx; ContextSize
0x140003013  mov     rcx, r14; NetBufferList
0x140003016  call    cs:__imp_NdisAllocateNetBufferListContext
0x14000301d  nop     dword ptr [rax+rax+00h]
0x140003022  mov     esi, eax
0x140003024  test    eax, eax
0x140003026  js      loc_14000361F
0x14000302c  movzx   eax, [rbp+130h+var_DE]
0x140003030  movzx   ebx, [rbp+130h+var_E2]
0x140003034  mov     r12, [r14+8]
0x140003038  movzx   esi, bx
0x14000303b  sub     si, ax
0x14000303e  mov     [rbp+130h+var_12F], dil
0x140003042  movzx   eax, r15w
0x140003046  mov     [rbp+130h+var_130], 1
0x14000304a  sub     ax, bx
0x14000304d  mov     [rbp+130h+var_D8], rdi
0x140003051  movzx   eax, ax
0x140003054  mov     dword ptr [rbp+130h+Size], eax
0x140003057  mov     [rbp+130h+Src], rdi
0x14000305b  mov     [rbp+130h+OriginalNetBufferList], rdi
0x14000305f  mov     [rbp+130h+var_12E], dil
0x140003063  mov     [rbp+130h+var_104], edi
0x140003066  mov     [rbp+130h+var_100], edi
0x140003069  mov     [rbp+130h+var_12C], si
0x14000306d  test    r12, r12
0x140003070  jz      loc_1400036C5
0x140003076  movzx   edi, r15w
0x14000307a  mov     r9d, 1; AlignMultiple
0x140003080  mov     edx, edi; BytesNeeded
0x140003082  mov     [rsp+170h+MaximumLength], 0; AlignOffset
0x14000308a  xor     r8d, r8d; Storage
0x14000308d  mov     rcx, r12; NetBuffer
0x140003090  call    cs:__imp_NdisGetDataBuffer
0x140003097  nop     dword ptr [rax+rax+00h]
0x14000309c  xor     r9d, r9d; FreeMdlHandler
0x14000309f  movzx   esi, si
0x1400030a2  mov     r15, rax
0x1400030a5  test    rax, rax
0x1400030a8  jz      loc_1400035B3
0x1400030ae  movzx   ecx, [rbp+130h+var_DE]
0x1400030b2  add     rax, rcx
0x1400030b5  movzx   ebx, bx
0x1400030b8  add     rbx, r15
0x1400030bb  mov     [rbp+130h+var_120], rax
0x1400030bf  mov     [rbp+130h+var_128], rbx
0x1400030c3  mov     rbx, [rbp+130h+OriginalNetBufferList]
0x1400030c7  test    rbx, rbx
0x1400030ca  jz      loc_140003332
0x1400030d0  cmp     [rbp+130h+var_12E], r9b
0x1400030d4  jz      loc_1400034A2
0x1400030da  mov     rcx, [rbp+130h+var_60]
0x1400030e1  mov     r15d, 1
0x1400030e7  or      edi, 0FFFFFFFFh
0x1400030ea  cmp     [rcx+1], r15b
0x1400030ee  jnz     short loc_14000312F
0x1400030f0  cmp     [rbp+130h+var_AC], r9b
0x1400030f7  jnz     short loc_14000312F
0x1400030f9  mov     rax, r9
0x1400030fc  mov     [rbp+130h+var_AC], r15b
0x140003103  cmp     [rbp+130h+var_A4], edi
0x140003109  jz      short loc_140003122
0x14000310b  mov     rdx, [rcx+18h]
0x14000310f  test    rdx, rdx
0x140003112  jz      short loc_140003122
0x140003114  mov     eax, [rbp+130h+var_A4]
0x14000311a  lea     rcx, [rax+rax*4]
0x14000311e  lea     rax, [rdx+rcx*4]
0x140003122  lock add [rax+10h], r15w
0x140003128  mov     rcx, [rbp+130h+var_60]
0x14000312f  mov     eax, [rcx+4]
0x140003132  test    eax, eax
0x140003134  jz      loc_140003984
0x14000313a  mov     rdx, [rbp+130h+var_90]
0x140003141  mov     ebx, [rdx+8]
0x140003144  cmp     ebx, [rdx+0Ch]
0x140003147  jnb     loc_1400037EC
0x14000314d  add     dword ptr [rbp+130h+var_A0+4], r15d
0x140003154  add     [rdx+8], r15d
0x140003158  mov     r8, [rbp+130h+var_60]
0x14000315f  cmp     [r8+1], r15b
0x140003163  jnz     short loc_1400031BB
0x140003165  mov     rax, r9
0x140003168  cmp     [rbp+130h+var_A4], edi
0x14000316e  jz      short loc_140003187
0x140003170  mov     r8, [r8+18h]
0x140003174  test    r8, r8
0x140003177  jz      short loc_140003187
0x140003179  mov     eax, [rbp+130h+var_A4]
0x14000317f  lea     rcx, [rax+rax*4]
0x140003183  lea     rax, [r8+rcx*4]
0x140003187  lock add [rax+0Eh], r15w
0x14000318d  mov     rcx, r9
0x140003190  cmp     [rbp+130h+var_A4], edi
0x140003196  jz      short loc_1400031B6
0x140003198  mov     rax, [rbp+130h+var_60]
0x14000319f  mov     r8, [rax+18h]
0x1400031a3  test    r8, r8
0x1400031a6  jz      short loc_1400031B6
0x1400031a8  mov     eax, [rbp+130h+var_A4]
0x1400031ae  lea     rcx, [rax+rax*4]
0x1400031b2  lea     rcx, [r8+rcx*4]
0x1400031b6  lock add [rcx+4], r15d
0x1400031bb  mov     eax, ebx
0x1400031bd  lea     rcx, [rax+rax*2]
0x1400031c1  mov     rax, [rdx+10h]
0x1400031c5  mov     rdi, [rbp+130h+var_120]
0x1400031c9  mov     rdx, [rbp+130h+Src]
0x1400031cd  mov     rbx, [rbp+130h+OriginalNetBufferList]
0x1400031d1  shl     esi, 4
0x1400031d4  or      esi, r15d
0x1400031d7  mov     [rax+rcx*8], rdi
0x1400031db  mov     [rax+rcx*8+10h], esi
0x1400031df  mov     [rax+rcx*8+8], rdx
0x1400031e4  mov     rcx, [rbp+130h+var_60]
0x1400031eb  xor     esi, esi
0x1400031ed  cmp     [rcx+1], r15b
0x1400031f1  jnz     short loc_140003232
0x1400031f3  cmp     [rbp+130h+var_AC], sil
0x1400031fa  jnz     short loc_140003232
0x1400031fc  cmp     [rbp+130h+var_A4], 0FFFFFFFFh
0x140003203  mov     eax, esi
0x140003205  mov     [rbp+130h+var_AC], r15b
0x14000320c  jz      short loc_140003225
0x14000320e  mov     rdx, [rcx+18h]
0x140003212  test    rdx, rdx
0x140003215  jz      short loc_140003225
0x140003217  mov     eax, [rbp+130h+var_A4]
0x14000321d  lea     rcx, [rax+rax*4]
0x140003221  lea     rax, [rdx+rcx*4]
0x140003225  lock add [rax+10h], r15w
0x14000322b  mov     rcx, [rbp+130h+var_60]
0x140003232  mov     eax, [rcx+4]
0x140003235  test    eax, eax
0x140003237  jz      loc_1400039E0
0x14000323d  mov     r8, [rbp+130h+var_90]
0x140003244  mov     ebx, [r8+8]
0x140003248  cmp     ebx, [r8+0Ch]
0x14000324c  jnb     loc_1400038B9
0x140003252  add     dword ptr [rbp+130h+var_A0+4], r15d
0x140003259  add     [r8+8], r15d
0x14000325d  mov     rdx, [rbp+130h+var_60]
0x140003264  cmp     [rdx+1], r15b
0x140003268  jnz     short loc_1400032C2
0x14000326a  cmp     [rbp+130h+var_A4], 0FFFFFFFFh
0x140003271  mov     rax, rsi
0x140003274  jz      short loc_14000328D
0x140003276  mov     rdx, [rdx+18h]
0x14000327a  test    rdx, rdx
0x14000327d  jz      short loc_14000328D
0x14000327f  mov     eax, [rbp+130h+var_A4]
0x140003285  lea     rcx, [rax+rax*4]
0x140003289  lea     rax, [rdx+rcx*4]
0x14000328d  lock add [rax+0Eh], r15w
0x140003293  cmp     [rbp+130h+var_A4], 0FFFFFFFFh
  ... truncated ...
```
