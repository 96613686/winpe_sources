# SegLibCreateMultiNbNblUsoClone

- ea: `0x140001594`
- end: `0x140002599`
- name: `SegLibCreateMultiNbNblUsoClone`
- size: `4101`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, installer_update`

## callers

- `0x14000268c`

## callees

- `0x140001430`
- `0x140001594`
- `0x140003e34`
- `0x140004b70`
- `0x140006620`
- `0x140078eac`
- `0x1401baab0`
- `0x1401bbb52`
- `0x1401bbc40`
- `0x1401bbe10`
- `0x1401bbfc0`
- `0x1401bc2c0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140001da1`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140001f6e`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400022ea`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140001da1`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140001f6e`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400022ea`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140001758`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140001758`
- `NDIS!NdisFreeNetBufferListContext` at `0x1400023e1`
- `NDIS!NdisFreeNetBufferListContext` at `0x1400023e1`
- `NDIS!NdisAllocateNetBufferListContext` at `0x1400018d7`
- `NDIS!NdisAllocateNetBufferListContext` at `0x1400018d7`
- `NDIS!NdisFreeFragmentNetBufferList` at `0x1400023f7`
- `NDIS!NdisFreeFragmentNetBufferList` at `0x1400023f7`
- `NDIS!NdisAdvanceNetBufferListDataStart` at `0x1400018b7`
- `NDIS!NdisAdvanceNetBufferListDataStart` at `0x1400018b7`
- `NDIS!NdisCopySendNetBufferListInfo` at `0x14000247e`
- `NDIS!NdisCopySendNetBufferListInfo` at `0x140002527`
- `NDIS!NdisCopySendNetBufferListInfo` at `0x14000247e`
- `NDIS!NdisCopySendNetBufferListInfo` at `0x140002527`
- `NDIS!NdisCopyReceiveNetBufferListInfo` at `0x140002455`
- `NDIS!NdisCopyReceiveNetBufferListInfo` at `0x140002455`
- `NDIS!NdisGetDataBuffer` at `0x140001969`
- `NDIS!NdisGetDataBuffer` at `0x1400019b4`
- `NDIS!NdisGetDataBuffer` at `0x1400019f9`
- `NDIS!NdisGetDataBuffer` at `0x140001969`
- `NDIS!NdisGetDataBuffer` at `0x1400019b4`
- `NDIS!NdisGetDataBuffer` at `0x1400019f9`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x140001995`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x1400019da`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x140001a6d`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x140001a85`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x140001acf`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x140001ae8`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x140001995`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x1400019da`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x140001a6d`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x140001a85`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x140001acf`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x140001ae8`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x140001a16`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x140001b2f`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x140001b48`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x140002430`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x140001a16`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x140001b2f`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x140001b48`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x140002430`
- `NDIS!NdisAllocateFragmentNetBufferList` at `0x14000188e`
- `NDIS!NdisAllocateFragmentNetBufferList` at `0x14000188e`

## pseudocode

```c
__int64 __fastcall SegLibCreateMultiNbNblUsoClone(
        __int64 a1,
        struct _NET_BUFFER_LIST *a2,
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
  __int64 v14; // rbx
  __int16 v15; // r12
  int v16; // r8d
  char v17; // r13
  int v18; // eax
  __int64 v19; // rax
  void *v20; // rax
  int v21; // r9d
  int v22; // ecx
  int v23; // eax
  __int64 v24; // rdi
  unsigned int v25; // esi
  unsigned __int64 v26; // rcx
  __int64 v27; // rax
  void *v28; // rsp
  bool v29; // cf
  unsigned int v30; // r9d
  PNET_BUFFER_LIST v31; // r13
  struct _NET_BUFFER_LIST *v32; // rsi
  char v33; // r14
  NDIS_STATUS fixed; // ebx
  __int64 v35; // r8
  unsigned __int16 v36; // r12
  struct _NET_BUFFER_LIST *FragmentNetBufferList; // rax
  unsigned __int8 v38; // di
  struct _NET_BUFFER *FirstNetBuffer; // rcx
  unsigned __int16 v40; // r14
  unsigned __int16 v41; // dx
  unsigned int v42; // ebx
  char *DataBuffer; // rax
  __int64 v44; // rdx
  void *v45; // r15
  char v46; // al
  struct _NET_BUFFER *v47; // rdi
  void *v48; // rdi
  void *v49; // r12
  int v50; // edi
  __int64 v51; // r8
  __int64 v52; // rax
  unsigned int v53; // eax
  int *v54; // rdx
  unsigned int v55; // ebx
  __int64 v56; // rax
  __int64 v57; // r8
  __int64 v58; // rcx
  __int64 v59; // r8
  __int64 v60; // rcx
  __int64 v61; // rax
  void *v62; // rdx
  _DWORD *v63; // rax
  int v64; // ecx
  __int64 v65; // rax
  __int64 v66; // r8
  volatile signed __int32 *v67; // rcx
  __int64 v68; // r8
  __int64 v69; // r8
  __int64 v70; // rax
  unsigned int v71; // eax
  __int64 v72; // rdx
  int *v73; // rdx
  unsigned int v74; // ebx
  _DWORD *v75; // rax
  int v76; // ecx
  __int64 v77; // rax
  __int64 v78; // r8
  volatile signed __int32 *v79; // rcx
  __int64 v80; // r8
  __int64 v81; // rax
  __int64 v82; // r8
  __int64 v83; // rcx
  __int64 v84; // r8
  __int64 v85; // rcx
  __int64 v86; // rax
  __int64 v87; // rcx
  __int64 v88; // rax
  unsigned int v89; // eax
  int *v90; // r8
  unsigned int v91; // ebx
  __int64 v92; // rax
  __int64 v93; // rdx
  __int64 v94; // rcx
  __int64 v95; // rdx
  __int64 v96; // rcx
  __int64 v97; // rdx
  int v98; // r15d
  _DWORD *v99; // rax
  int v100; // ecx
  __int64 v101; // rax
  __int64 v102; // rdx
  volatile signed __int32 *v103; // rcx
  __int64 v104; // rdx
  bool v106; // di
  void *v107; // rbx
  int v108; // edx
  $A748D0D663C15BE980B604C3B1026F20 *Alignment; // rdi
  char v110; // r14
  _QWORD *v111; // rax
  _DWORD *v112; // rcx
  ULONG DataOffsetDelta; // [rsp+28h] [rbp-18h]
  char DataBackFill; // [rsp+30h] [rbp-10h]
  char v115; // [rsp+40h] [rbp+0h] BYREF
  char v116; // [rsp+41h] [rbp+1h]
  char v117; // [rsp+42h] [rbp+2h]
  char v118; // [rsp+43h] [rbp+3h]
  unsigned __int8 v119; // [rsp+44h] [rbp+4h]
  bool v120; // [rsp+45h] [rbp+5h]
  unsigned __int16 v121; // [rsp+46h] [rbp+6h]
  ULONG BytesNeeded; // [rsp+48h] [rbp+8h]
  void *v123; // [rsp+50h] [rbp+10h]
  PNET_BUFFER NetBuffer; // [rsp+58h] [rbp+18h]
  PNET_BUFFER_LIST OriginalNetBufferList; // [rsp+60h] [rbp+20h]
  int v126; // [rsp+68h] [rbp+28h]
  void *v127; // [rsp+70h] [rbp+30h]
  unsigned __int16 v128; // [rsp+78h] [rbp+38h]
  int v129; // [rsp+7Ch] [rbp+3Ch]
  int v130; // [rsp+80h] [rbp+40h]
  ULONG v131; // [rsp+84h] [rbp+44h]
  int v132; // [rsp+88h] [rbp+48h]
  void *v133; // [rsp+90h] [rbp+50h]
  ULONG MaximumLength[4]; // [rsp+98h] [rbp+58h] BYREF
  struct _NET_BUFFER_LIST *v135; // [rsp+A8h] [rbp+68h]
  void *Src; // [rsp+B0h] [rbp+70h]
  void *v137; // [rsp+B8h] [rbp+78h]
  __int64 v138; // [rsp+C0h] [rbp+80h]
  __int64 v139; // [rsp+C8h] [rbp+88h]
  int v140[24]; // [rsp+D0h] [rbp+90h] BYREF

  v138 = a10;
  v139 = a11;
  OriginalNetBufferList = a2;
  *(_OWORD *)MaximumLength = 0;
  v135 = 0;
  memset(v140, 0, sizeof(v140));
  v126 = 0;
  v14 = 0;
  LOBYTE(v130) = 0;
  v15 = 0;
  v116 = 0;
  LOBYTE(v16) = 0;
  v17 = 1;
  if ( !a5 )
  {
    v120 = 0;
    goto LABEL_15;
  }
  v16 = *a5;
  v18 = *((_DWORD *)a5 + 7) - 1;
  v120 = (v18 & 0xFFFFFFFD) == 0;
  if ( (v16 & 8) != 0 )
  {
    v14 = *((_QWORD *)a5 + 1);
    v15 = a5[8];
    v17 = *((_BYTE *)a5 + 18);
  }
  if ( (v18 & 0xFFFFFFFD) == 0 )
  {
LABEL_14:
    LOBYTE(v16) = 0;
    goto LABEL_15;
  }
  v19 = (unsigned int)a2->NetBufferListInfo[22];
  if ( (unsigned int)a2->NetBufferListInfo[22] || (v16 & 8) != 0 )
    v116 = 1;
  if ( (v16 & 2) == 0 )
  {
    if ( v19 )
    {
      LOBYTE(v16) = v116;
      goto LABEL_15;
    }
    v20 = a2->NetBufferListInfo[0];
    if ( ((unsigned __int8)v20 & 0x1C) != 0 )
    {
      v116 = 1;
      v30 = (unsigned int)v20 >> 1;
      LOBYTE(v16) = 1;
      LOBYTE(v30) = ((unsigned __int8)v20 & 2) != 0;
      v130 = v30;
      goto LABEL_15;
    }
    v116 = 0;
    goto LABEL_14;
  }
  LOBYTE(v16) = *((_BYTE *)a5 + 27);
  v116 = v16;
  if ( (_BYTE)v16 == 1 )
  {
    LOBYTE(v19) = *((_BYTE *)a5 + 26);
    v130 = v19;
    v126 = a5[12];
  }
LABEL_15:
  v21 = 4;
  if ( LODWORD(a2->NetBufferListInfo[22]) || (v22 = 0, (*(_BYTE *)a5 & 8) != 0) )
    v22 = 4;
  v23 = v22 | 2;
  if ( (_BYTE)v16 != 1 )
    v23 = v22;
  if ( a12 )
    *a12 = v23;
  v24 = qword_140224C88;
  v25 = 4;
  if ( qword_140224C88 && *(_BYTE *)(qword_140224C88 + 48) )
    v25 = *(_DWORD *)(qword_140224C88 + 16);
  v26 = 24LL * v25;
  v27 = v26 + 15;
  if ( v26 + 15 < v26 )
    v27 = 0xFFFFFFFFFFFFFF0LL;
  v28 = alloca(v27 & 0xFFFFFFFFFFFFFFF0uLL);
  if ( a3 != 1 || *(_QWORD *)(qword_140224C88 + 32) )
  {
    v140[0] = -267522035;
    v140[3] = KeGetCurrentProcessorNumberEx(0);
    LOBYTE(v140[1]) = 0;
    *(_QWORD *)&v140[6] = 0;
    v16 = 1;
    v140[2] = a3 & 1;
    v29 = *(_QWORD *)(v24 + 32) != 0;
    *(_QWORD *)&v140[4] = 1;
    *(_QWORD *)&v140[8] = &v140[14];
    v140[2] |= v29 ? 4 : 0;
    memset(&v140[11], 0, 24);
    LOBYTE(v140[10]) = 0;
    if ( &v115 )
    {
      v140[17] = v25;
      *(_QWORD *)&v140[18] = &v115;
    }
    else
    {
      v140[17] = 0;
      *(_QWORD *)&v140[18] = 0;
    }
    *(_QWORD *)&v140[20] = v24;
  }
  DataBackFill = v17;
  v31 = OriginalNetBufferList;
  v32 = 0;
  v33 = 0;
  fixed = SegLibPvtUsoInitialize(
            (unsigned int)MaximumLength,
            (_DWORD)OriginalNetBufferList,
            v16,
            v21,
            v14,
            v15,
            DataBackFill);
  if ( fixed < 0 )
  {
LABEL_190:
    v36 = WORD1(v135);
    goto LABEL_165;
  }
  v36 = WORD1(v135);
  FragmentNetBufferList = NdisAllocateFragmentNetBufferList(v31, 0, 0, WORD1(v135), MaximumLength[0], WORD1(v135), 0, 0);
  v32 = FragmentNetBufferList;
  if ( !FragmentNetBufferList )
  {
    fixed = -1073741670;
    goto LABEL_165;
  }
  NdisAdvanceNetBufferListDataStart(FragmentNetBufferList, 0, 0, 0);
  if ( !a8 || (fixed = NdisAllocateNetBufferListContext(v32, a8, 0, 0x6C6F734Cu), fixed >= 0) )
  {
    v38 = BYTE6(v135);
    FirstNetBuffer = v32->FirstNetBuffer;
    v40 = (_WORD)v135 - BYTE6(v135);
    v117 = 0;
    v41 = v36;
    BytesNeeded = (unsigned __int16)(v36 - (_WORD)v135);
    v131 = (unsigned __int16)v135;
    v115 = 1;
    Src = 0;
    v137 = 0;
    v133 = 0;
    v118 = 0;
    v132 = 0;
    v129 = 0;
    v119 = BYTE6(v135);
    OriginalNetBufferList = v135;
    v121 = v40;
    v128 = v36;
    while ( 1 )
    {
      NetBuffer = FirstNetBuffer;
      if ( !FirstNetBuffer )
      {
        v106 = v120;
        if ( v120 )
        {
          NdisCopyReceiveNetBufferListInfo(v32, v31);
        }
        else
        {
          if ( NetioCopyNetBufferListQosInformationFnPtr )
          {
            v107 = v31->NetBufferListInfo[3];
            v31->NetBufferListInfo[3] = 0;
            NdisCopySendNetBufferListInfo(v32, v31);
            if ( v107 )
            {
              v31->NetBufferListInfo[3] = v107;
              ((void (__fastcall *)(struct _NET_BUFFER_LIST *, PNET_BUFFER_LIST))NetioCopyNetBufferListQosInformationFnPtr)(
                v32,
                v31);
            }
          }
          else
          {
            NdisCopySendNetBufferListInfo(v32, v31);
          }
          v32->NetBufferListInfo[22] = 0;
        }
        if ( v116 == 1 )
        {
          v108 = v126;
          Alignment = ($A748D0D663C15BE980B604C3B1026F20 *)v32->FirstNetBuffer;
          if ( !(_WORD)v126 )
            LOWORD(v108) = (_WORD)OriginalNetBufferList;
          v110 = v130;
          v126 = v108;
          while ( Alignment )
          {
            LOBYTE(DataOffsetDelta) = v110;
            OriginalNetBufferList = (PNET_BUFFER_LIST)(((HIBYTE(v135) & 1) == 0) | (2 * (HIBYTE(v135) & 1u)) | 8LL);
            fixed = SegLibDeferredChecksumPacket((int)v140, (int)Alignment, v108, DataOffsetDelta);
            if ( fixed < 0 )
              goto LABEL_164;
            Alignment = ($A748D0D663C15BE980B604C3B1026F20 *)Alignment->Link.Alignment;
            LOWORD(v108) = v126;
          }
          v32->NetBufferListInfo[0] = 0;
        }
        else if ( !v106 )
        {
          OriginalNetBufferList = (PNET_BUFFER_LIST)(((HIBYTE(v135) & 1) == 0) | (2 * (HIBYTE(v135) & 1u)) | 8LL);
          v32->NetBufferListInfo[0] = OriginalNetBufferList;
        }
        v111 = (_QWORD *)v138;
        fixed = 0;
        v112 = (_DWORD *)v139;
        v32->ParentNetBufferList = v31;
        *v111 = v32;
        *v112 = v36;
LABEL_164:
        v33 = v115;
        goto LABEL_165;
      }
      v42 = v41;
      DataBuffer = (char *)NdisGetDataBuffer(FirstNetBuffer, v41, 0, 1u, 0);
      v45 = DataBuffer;
      if ( DataBuffer )
      {
        v123 = &DataBuffer[v119];
        v127 = &DataBuffer[(unsigned __int16)OriginalNetBufferList];
        v46 = v117;
      }
      else
      {
        NdisAdvanceNetBufferDataStart(NetBuffer, v38, 0, 0);
        v123 = NdisGetDataBuffer(NetBuffer, v40, 0, 1u, 0);
        if ( !v123 )
        {
          fixed = -1073741670;
          NdisRetreatNetBufferDataStart(NetBuffer, v38, 0, 0);
          goto LABEL_164;
        }
        NdisAdvanceNetBufferDataStart(NetBuffer, v40, 0, 0);
        v127 = NdisGetDataBuffer(NetBuffer, BytesNeeded, 0, 1u, 0);
        NdisRetreatNetBufferDataStart(NetBuffer, v131, 0, 0);
        if ( !v127 )
        {
          fixed = -1073741670;
          goto LABEL_164;
        }
        v46 = 1;
        v117 = 1;
      }
      if ( !v133 )
        break;
      if ( !v118 && !v46 )
      {
        v51 = *(_QWORD *)&v140[20];
        if ( *(_BYTE *)(*(_QWORD *)&v140[20] + 1LL) == 1 && !LOBYTE(v140[1]) )
        {
          LOBYTE(v140[1]) = 1;
          v52 = 0;
          if ( v140[3] != -1 )
          {
            v44 = *(_QWORD *)(*(_QWORD *)&v140[20] + 24LL);
            if ( v44 )
              v52 = v44 + 20LL * (unsigned int)v140[3];
          }
          _InterlockedAdd16((volatile signed __int16 *)(v52 + 16), 1u);
          v51 = *(_QWORD *)&v140[20];
        }
        v53 = *(_DWORD *)(v51 + 4);
        if ( v53 )
        {
          v54 = *(int **)&v140[8];
          v55 = *(_DWORD *)(*(_QWORD *)&v140[8] + 8LL);
          if ( v55 >= *(_DWORD *)(*(_QWORD *)&v140[8] + 12LL) )
          {
            v55 = 0;
            if ( v140[4] < v53
              && (v63 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v51 + 64)), (v54 = v63) != 0) )
            {
              *(_QWORD *)v63 = 0;
              v63[2] = 0;
              v64 = *(_DWORD *)(*(_QWORD *)&v140[20] + 8LL);
              *((_QWORD *)v63 + 2) = v63 + 6;
              v63[3] = v64;
              **(_QWORD **)&v140[8] = v63;
              ++v140[4];
              *(_QWORD *)&v140[8] = v63;
              if ( *(_BYTE *)(*(_QWORD *)&v140[20] + 1LL) == 1 )
              {
                v65 = 0;
                if ( v140[3] != -1 )
                {
                  v66 = *(_QWORD *)(*(_QWORD *)&v140[20] + 24LL);
                  if ( v66 )
                    v65 = v66 + 20LL * (unsigned int)v140[3];
                }
                _InterlockedAdd16((volatile signed __int16 *)(v65 + 12), 1u);
                v67 = 0;
                if ( v140[3] != -1 )
                {
                  v68 = *(_QWORD *)(*(_QWORD *)&v140[20] + 24LL);
                  if ( v68 )
                    v67 = (volatile signed __int32 *)(v68 + 20LL * (unsigned int)v140[3]);
                }
                _InterlockedAdd(v67, 1u);
              }
            }
            else
            {
              LOBYTE(v54) = 1;
              BLFlushBatchOpContextEx(v140, v54, 0);
              v54 = &v140[14];
            }
          }
          ++v140[5];
          ++v54[2];
          if ( *(_BYTE *)(*(_QWORD *)&v140[20] + 1LL) == 1 )
          {
            v56 = 0;
            if ( v140[3] != -1 )
            {
              v57 = *(_QWORD *)(*(_QWORD *)&v140[20] + 24LL);
              if ( v57 )
                v56 = v57 + 20LL * (unsigned int)v140[3];
            }
            _InterlockedAdd16((volatile signed __int16 *)(v56 + 14), 1u);
            v58 = 0;
            if ( v140[3] != -1 )
            {
              v59 = *(_QWORD *)(*(_QWORD *)&v140[20] + 24LL);
              if ( v59 )
                v58 = v59 + 20LL * (unsigned int)v140[3];
            }
            _InterlockedAdd((volatile signed __int32 *)(v58 + 4), 1u);
          }
          v60 = 3LL * v55;
          v61 = *((_QWORD *)v54 + 2);
          v62 = Src;
          *(_QWORD *)(v61 + 8 * v60) = v45;
          *(_DWORD *)(v61 + 8 * v60 + 16) = (16 * v36) | 1;
          *(_QWORD *)(v61 + 8 * v60 + 8) = v62;
        }
        else
        {
          if ( v140[5] )
          {
            LOBYTE(v44) = 1;
            BLFlushBatchOpContextEx(v140, v44, 0);
            v51 = *(_QWORD *)&v140[20];
          }
          if ( (v140[2] & 5) == 5 || (v140[2] & 6) == 6 )
          {
            (*(void (**)(void))(v51 + 32))();
            memmove(v45, Src, v36);
            (*(void (**)(void))(*(_QWORD *)&v140[20] + 40LL))();
          }
          else
          {
            memmove(v45, Src, v36);
          }
        }
LABEL_56:
        v50 = (int)v123;
        goto LABEL_152;
      }
      v69 = *(_QWORD *)&v140[20];
      if ( *(_BYTE *)(*(_QWORD *)&v140[20] + 1LL) == 1 && !LOBYTE(v140[1]) )
      {
        v70 = 0;
        LOBYTE(v140[1]) = 1;
        if ( v140[3] != -1 )
        {
          v44 = *(_QWORD *)(*(_QWORD *)&v140[20] + 24LL);
          if ( v44 )
            v70 = v44 + 20LL * (unsigned int)v140[3];
        }
        _InterlockedAdd16((volatile signed __int16 *)(v70 + 16), 1u);
        v69 = *(_QWORD *)&v140[20];
      }
      v71 = *(_DWORD *)(v69 + 4);
      if ( v71 )
      {
        v73 = *(int **)&v140[8];
        v74 = *(_DWORD *)(*(_QWORD *)&v140[8] + 8LL);
        if ( v74 >= *(_DWORD *)(*(_QWORD *)&v140[8] + 12LL) )
        {
          v74 = 0;
          if ( v140[4] < v71
            && (v75 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v69 + 64)), (v73 = v75) != 0) )
          {
            *(_QWORD *)v75 = 0;
            v75[2] = 0;
            v76 = *(_DWORD *)(*(_QWORD *)&v140[20] + 8LL);
            *((_QWORD *)v75 + 2) = v75 + 6;
            v75[3] = v76;
            **(_QWORD **)&v140[8] = v75;
            ++v140[4];
            *(_QWORD *)&v140[8] = v75;
            if ( *(_BYTE *)(*(_QWORD *)&v140[20] + 1LL) == 1 )
            {
              v77 = 0;
              if ( v140[3] != -1 )
              {
                v78 = *(_QWORD *)(*(_QWORD *)&v140[20] + 24LL);
                if ( v78 )
                  v77 = v78 + 20LL * (unsigned int)v140[3];
              }
              _InterlockedAdd16((volatile signed __int16 *)(v77 + 12), 1u);
              v79 = 0;
              if ( v140[3] != -1 )
              {
                v80 = *(_QWORD *)(*(_QWORD *)&v140[20] + 24LL);
                if ( v80 )
                  v79 = (volatile signed __int32 *)(v80 + 20LL * (unsigned int)v140[3]);
              }
              _InterlockedAdd(v79, 1u);
            }
          }
          else
          {
            LOBYTE(v73) = 1;
            BLFlushBatchOpContextEx(v140, v73, 0);
            v73 = &v140[14];
          }
        }
        ++v140[5];
        ++v73[2];
        if ( *(_BYTE *)(*(_QWORD *)&v140[20] + 1LL) == 1 )
        {
          v81 = 0;
          if ( v140[3] != -1 )
          {
            v82 = *(_QWORD *)(*(_QWORD *)&v140[20] + 24LL);
            if ( v82 )
              v81 = v82 + 20LL * (unsigned int)v140[3];
          }
          _InterlockedAdd16((volatile signed __int16 *)(v81 + 14), 1u);
          v83 = 0;
          if ( v140[3] != -1 )
          {
            v84 = *(_QWORD *)(*(_QWORD *)&v140[20] + 24LL);
            if ( v84 )
              v83 = v84 + 20LL * (unsigned int)v140[3];
          }
          _InterlockedAdd((volatile signed __int32 *)(v83 + 4), 1u);
        }
        v85 = 3LL * v74;
        v86 = *((_QWORD *)v73 + 2);
        v50 = (int)v123;
        v72 = (__int64)v137;
        *(_QWORD *)(v86 + 8 * v85) = v123;
        *(_DWORD *)(v86 + 8 * v85 + 16) = (16 * v40) | 1;
        *(_QWORD *)(v86 + 8 * v85 + 8) = v72;
      }
      else
      {
        if ( v140[5] )
        {
          LOBYTE(v44) = 1;
          BLFlushBatchOpContextEx(v140, v44, 0);
          v69 = *(_QWORD *)&v140[20];
        }
        if ( (v140[2] & 5) == 5 || (v140[2] & 6) == 6 )
        {
          (*(void (**)(void))(v69 + 32))();
          v50 = (int)v123;
          memmove(v123, v137, v121);
          (*(void (**)(void))(*(_QWORD *)&v140[20] + 40LL))();
        }
        else
        {
          v50 = (int)v123;
          memmove(v123, v137, v121);
        }
      }
      v87 = *(_QWORD *)&v140[20];
      if ( *(_BYTE *)(*(_QWORD *)&v140[20] + 1LL) == 1 && !LOBYTE(v140[1]) )
      {
        v72 = 0xFFFFFFFFLL;
        LOBYTE(v140[1]) = 1;
        v88 = 0;
        if ( v140[3] != -1 )
        {
          v72 = *(_QWORD *)(*(_QWORD *)&v140[20] + 24LL);
          if ( v72 )
            v88 = v72 + 20LL * (unsigned int)v140[3];
        }
        _InterlockedAdd16((volatile signed __int16 *)(v88 + 16), 1u);
        v87 = *(_QWORD *)&v140[20];
      }
      v89 = *(_DWORD *)(v87 + 4);
      if ( v89 )
      {
        v90 = *(int **)&v140[8];
        v91 = *(_DWORD *)(*(_QWORD *)&v140[8] + 8LL);
        if ( v91 >= *(_DWORD *)(*(_QWORD *)&v140[8] + 12LL) )
        {
          v91 = 0;
          if ( v140[4] < v89
            && (v99 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v87 + 64)), (v90 = v99) != 0) )
          {
            *(_QWORD *)v99 = 0;
            v99[2] = 0;
            v100 = *(_DWORD *)(*(_QWORD *)&v140[20] + 8LL);
            *((_QWORD *)v99 + 2) = v99 + 6;
            v99[3] = v100;
            **(_QWORD **)&v140[8] = v99;
            ++v140[4];
            *(_QWORD *)&v140[8] = v99;
            if ( *(_BYTE *)(*(_QWORD *)&v140[20] + 1LL) == 1 )
            {
              v101 = 0;
              if ( v140[3] != -1 )
              {
                v102 = *(_QWORD *)(*(_QWORD *)&v140[20] + 24LL);
                if ( v102 )
                  v101 = v102 + 20LL * (unsigned int)v140[3];
              }
              _InterlockedAdd16((volatile signed __int16 *)(v101 + 12), 1u);
              v103 = 0;
              if ( v140[3] != -1 )
              {
                v104 = *(_QWORD *)(*(_QWORD *)&v140[20] + 24LL);
                if ( v104 )
                  v103 = (volatile signed __int32 *)(v104 + 20LL * (unsigned int)v140[3]);
              }
              _InterlockedAdd(v103, 1u);
            }
          }
          else
          {
            LOBYTE(v72) = 1;
            BLFlushBatchOpContextEx(v140, v72, 0);
            v90 = &v140[14];
          }
        }
        ++v140[5];
        ++v90[2];
        if ( *(_BYTE *)(*(_QWORD *)&v140[20] + 1LL) == 1 )
        {
          v92 = 0;
          if ( v140[3] != -1 )
          {
            v93 = *(_QWORD *)(*(_QWORD *)&v140[20] + 24LL);
            if ( v93 )
              v92 = v93 + 20LL * (unsigned int)v140[3];
          }
          _InterlockedAdd16((volatile signed __int16 *)(v92 + 14), 1u);
          v94 = 0;
          if ( v140[3] != -1 )
          {
            v95 = *(_QWORD *)(*(_QWORD *)&v140[20] + 24LL);
            if ( v95 )
              v94 = v95 + 20LL * (unsigned int)v140[3];
          }
          _InterlockedAdd((volatile signed __int32 *)(v94 + 4), 1u);
        }
        v96 = *((_QWORD *)v90 + 2);
        v97 = 3LL * v91;
        *(_QWORD *)(v96 + 8 * v97) = v127;
        *(_QWORD *)(v96 + 8 * v97 + 8) = v133;
        *(_DWORD *)(v96 + 8 * v97 + 16) = (16 * BytesNeeded) | 1;
      }
      else
      {
        if ( v140[5] )
        {
          LOBYTE(v72) = 1;
          BLFlushBatchOpContextEx(v140, v72, 0);
          v87 = *(_QWORD *)&v140[20];
        }
        if ( (v140[2] & 5) == 5 || (v140[2] & 6) == 6 )
        {
          (*(void (**)(void))(v87 + 32))();
          memmove(v127, v133, BytesNeeded);
          (*(void (**)(void))(*(_QWORD *)&v140[20] + 40LL))();
        }
        else
        {
          memmove(v127, v133, BytesNeeded);
        }
      }
LABEL_152:
      v98 = v132;
      fixed = SegLibPvtUsoDeferredFixHeaders(
                (unsigned int)v140,
                (unsigned int)MaximumLength,
                v50,
                (_DWORD)v127,
                v132,
                v129);
      if ( fixed < 0 )
        goto LABEL_164;
      v40 = v121;
      v38 = v119;
      v129 += MaximumLength[0];
      FirstNetBuffer = (struct _NET_BUFFER *)NetBuffer->Link.Alignment;
      v41 = v128;
      v132 = v98 + 1;
    }
    if ( v46 )
    {
      NdisAdvanceNetBufferDataStart(NetBuffer, v38, 0, 0);
      NdisAdvanceNetBufferDataStart(v31->FirstNetBuffer, v38, 0, 0);
      fixed = SegLibPvtDeferredCopyMdlChainData(
                v140,
                *(_QWORD *)(v31->Link.Region + 8),
                *(unsigned int *)(v31->Link.Region + 16),
                v40,
                v123);
      if ( fixed < 0 )
        goto LABEL_164;
      v47 = NetBuffer;
      NdisAdvanceNetBufferDataStart(NetBuffer, v40, 0, 0);
      NdisAdvanceNetBufferDataStart(v31->FirstNetBuffer, v40, 0, 0);
      fixed = SegLibPvtDeferredCopyMdlChainData(
                v140,
                *(_QWORD *)(v31->Link.Region + 8),
                *(unsigned int *)(v31->Link.Region + 16),
                BytesNeeded,
                v127);
      if ( fixed < 0 )
        goto LABEL_164;
      NdisRetreatNetBufferDataStart(v47, v131, 0, 0);
      NdisRetreatNetBufferDataStart(v31->FirstNetBuffer, v131, 0, 0);
    }
    else
    {
      fixed = SegLibPvtDeferredCopyMdlChainData(
                v140,
                *(_QWORD *)(v31->Link.Region + 8),
                *(unsigned int *)(v31->Link.Region + 16),
                v42,
                v45);
      if ( fixed < 0 )
        goto LABEL_164;
    }
    v33 = 1;
    LOBYTE(v35) = 1;
    BLFlushBatchOpContextEx(v140, 0, v35);
    v48 = v127;
    v49 = v123;
    fixed = SegLibPvtUsoParseHeaders(MaximumLength, v123, v127);
    if ( fixed < 0 )
      goto LABEL_190;
    v137 = v49;
    v36 = WORD1(v135);
    v118 = v117;
    Src = v45;
    v133 = v48;
    goto LABEL_56;
  }
LABEL_165:
  LOBYTE(v35) = 1;
  BLFlushBatchOpContextEx(v140, 0, v35);
  if ( fixed < 0 && v32 )
  {
    if ( v33 == 1 )
      NdisFreeNetBufferListContext(v32, a8);
    NdisFreeFragmentNetBufferList(v32, v36, 0);
  }
  return (unsigned int)fixed;
}

```

## disassembly

```asm
0x140001594  push    rbp
0x140001596  push    rbx
0x140001597  push    rsi
0x140001598  push    rdi
0x140001599  push    r12
0x14000159b  push    r13
0x14000159d  push    r14
0x14000159f  push    r15
0x1400015a1  sub     rsp, 148h
0x1400015a8  lea     rbp, [rsp+40h]
0x1400015ad  mov     rax, cs:__security_cookie
0x1400015b4  xor     rax, rbp
0x1400015b7  mov     [rbp+140h+var_50], rax
0x1400015be  mov     rax, [rbp+140h+arg_48]
0x1400015c5  lea     rcx, [rbp+140h+var_B0]; void *
0x1400015cc  mov     rdi, [rbp+140h+arg_58]
0x1400015d3  mov     rsi, rdx
0x1400015d6  mov     [rbp+140h+var_C0], rax
0x1400015dd  xorps   xmm0, xmm0
0x1400015e0  mov     rax, [rbp+140h+arg_50]
0x1400015e7  mov     [rbp+140h+var_B8], rax
0x1400015ee  xor     eax, eax
0x1400015f0  movzx   r15d, r8b
0x1400015f4  mov     [rbp+140h+OriginalNetBufferList], rdx
0x1400015f8  xor     edx, edx; Val
0x1400015fa  movups  xmmword ptr [rbp+140h+var_E8], xmm0
0x1400015fe  lea     r8d, [rax+60h]; Size
0x140001602  mov     [rbp+140h+var_D8], rax
0x140001606  call    memset
0x14000160b  mov     rdx, [rbp+140h+arg_20]
0x140001612  xor     r10d, r10d
0x140001615  mov     [rbp+140h+var_118], r10d
0x140001619  mov     ebx, r10d
0x14000161c  mov     byte ptr [rbp+140h+var_100], r10b
0x140001620  mov     r12d, r10d
0x140001623  mov     [rbp+140h+var_13F], r10b
0x140001627  mov     r8b, r10b
0x14000162a  lea     r11d, [r10+1]
0x14000162e  mov     r14d, 0FFFFFFFFh
0x140001634  mov     r13b, r11b
0x140001637  test    rdx, rdx
0x14000163a  jz      loc_140001805
0x140001640  mov     eax, [rdx+1Ch]
0x140001643  movzx   r8d, word ptr [rdx]
0x140001647  sub     eax, r11d
0x14000164a  test    eax, 0FFFFFFFDh
0x14000164f  movzx   ecx, r8w
0x140001653  setz    r9b
0x140001657  mov     [rbp+140h+var_13B], r9b
0x14000165b  and     cx, 8
0x14000165f  jz      short loc_14000166E
0x140001661  mov     rbx, [rdx+8]
0x140001665  movzx   r12d, word ptr [rdx+10h]
0x14000166a  mov     r13b, [rdx+12h]
0x14000166e  test    r9b, r9b
0x140001671  jnz     short loc_1400016C6
0x140001673  mov     rax, [rsi+140h]
0x14000167a  and     rax, r14
0x14000167d  jnz     short loc_140001684
0x14000167f  test    cx, cx
0x140001682  jz      short loc_140001688
0x140001684  mov     [rbp+140h+var_13F], r11b
0x140001688  test    r8b, 2
0x14000168c  jz      short loc_1400016AA
0x14000168e  mov     r8b, [rdx+1Bh]
0x140001692  mov     [rbp+140h+var_13F], r8b
0x140001696  cmp     r8b, r11b
0x140001699  jnz     short loc_1400016C9
0x14000169b  mov     al, [rdx+1Ah]
0x14000169e  mov     [rbp+140h+var_100], eax
0x1400016a1  movzx   eax, word ptr [rdx+18h]
0x1400016a5  mov     [rbp+140h+var_118], eax
0x1400016a8  jmp     short loc_1400016C9
0x1400016aa  test    rax, rax
0x1400016ad  jnz     loc_14000180E
0x1400016b3  mov     rax, [rsi+90h]
0x1400016ba  test    al, 1Ch
0x1400016bc  jnz     loc_1400017EC
0x1400016c2  mov     [rbp+140h+var_13F], r10b
0x1400016c6  mov     r8b, r10b
0x1400016c9  mov     r9d, 4
0x1400016cf  cmp     [rsi+140h], r10d
0x1400016d6  jnz     short loc_1400016E0
0x1400016d8  test    byte ptr [rdx], 8
0x1400016db  mov     ecx, r10d
0x1400016de  jz      short loc_1400016E3
0x1400016e0  mov     ecx, r9d
0x1400016e3  mov     eax, ecx
0x1400016e5  or      eax, 2
0x1400016e8  cmp     r8b, r11b
0x1400016eb  cmovnz  eax, ecx
0x1400016ee  test    rdi, rdi
0x1400016f1  jz      short loc_1400016F5
0x1400016f3  mov     [rdi], eax
0x1400016f5  mov     rdi, cs:qword_140224C88
0x1400016fc  mov     esi, r9d
0x1400016ff  test    rdi, rdi
0x140001702  jz      short loc_14000170D
0x140001704  cmp     [rdi+30h], r10b
0x140001708  jz      short loc_14000170D
0x14000170a  mov     esi, [rdi+10h]
0x14000170d  mov     eax, esi
0x14000170f  lea     rcx, [rax+rax*2]
0x140001713  shl     rcx, 3
0x140001717  lea     rax, [rcx+0Fh]
0x14000171b  cmp     rax, rcx
0x14000171e  ja      short loc_14000172A
0x140001720  mov     rax, 0FFFFFFFFFFFFFF0h
0x14000172a  and     rax, 0FFFFFFFFFFFFFFF0h
0x14000172e  call    __chkstk_0
0x140001733  sub     rsp, rax
0x140001736  lea     r14, [rsp+180h+var_140]
0x14000173b  cmp     r15b, 1
0x14000173f  jnz     short loc_14000174C
0x140001741  cmp     qword ptr [rdi+20h], 0
0x140001746  jz      loc_14000182E
0x14000174c  xor     ecx, ecx; ProcNumber
0x14000174e  mov     [rbp+140h+var_B0], 0F00DF00Dh
0x140001758  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14000175f  nop     dword ptr [rax+rax+00h]
0x140001764  mov     [rbp+140h+var_A4], eax
0x14000176a  mov     edx, r15d
0x14000176d  xor     eax, eax
0x14000176f  mov     [rbp+140h+var_AC], al
0x140001775  mov     [rbp+140h+var_98], rax
0x14000177c  lea     r8d, [rax+1]
0x140001780  and     edx, r8d
0x140001783  mov     [rbp+140h+var_A8], edx
0x140001789  mov     rax, [rdi+20h]
0x14000178d  neg     rax
0x140001790  mov     [rbp+140h+var_A0], r8
0x140001797  lea     rax, [rbp+140h+var_78]
0x14000179e  sbb     ecx, ecx
0x1400017a0  mov     [rbp+140h+var_90], rax
0x1400017a7  xor     r15d, r15d
0x1400017aa  and     ecx, 4
0x1400017ad  or      ecx, edx
0x1400017af  mov     [rbp+140h+var_80], r15
0x1400017b6  mov     [rbp+140h+var_A8], ecx
0x1400017bc  mov     [rbp+140h+var_84], r15d
0x1400017c3  mov     [rbp+140h+var_88], r15b
0x1400017ca  mov     [rbp+140h+var_78], r15
0x1400017d1  mov     [rbp+140h+var_70], r15d
0x1400017d8  test    r14, r14
0x1400017db  jz      short loc_140001817
0x1400017dd  mov     [rbp+140h+var_6C], esi
0x1400017e3  mov     [rbp+140h+var_68], r14
0x1400017ea  jmp     short loc_140001825
0x1400017ec  mov     r9d, eax
0x1400017ef  mov     [rbp+140h+var_13F], r11b
0x1400017f3  shr     r9d, 1
0x1400017f6  mov     r8b, r11b
0x1400017f9  and     r9b, r11b
0x1400017fc  mov     [rbp+140h+var_100], r9d
0x140001800  jmp     loc_1400016C9
0x140001805  mov     [rbp+140h+var_13B], r10b
0x140001809  jmp     loc_1400016C9
0x14000180e  mov     r8b, [rbp+140h+var_13F]
0x140001812  jmp     loc_1400016C9
0x140001817  mov     [rbp+140h+var_6C], r15d
0x14000181e  mov     [rbp+140h+var_68], r15
0x140001825  mov     [rbp+140h+var_60], rdi
0x14000182c  jmp     short loc_140001831
0x14000182e  xor     r15d, r15d
0x140001831  mov     [rsp+180h+DataBackFill], r13b
0x140001836  lea     rcx, [rbp+140h+var_E8]
0x14000183a  mov     r13, [rbp+140h+OriginalNetBufferList]
0x14000183e  mov     rsi, r15
0x140001841  mov     rdx, r13
0x140001844  mov     word ptr [rsp+180h+DataOffsetDelta], r12w
0x14000184a  mov     r14b, r15b
0x14000184d  mov     qword ptr [rsp+180h+MaximumLength], rbx
0x140001852  call    SegLibPvtUsoInitialize
0x140001857  movzx   edi, [rbp+140h+arg_38]
0x14000185e  mov     ebx, eax
0x140001860  test    eax, eax
0x140001862  js      loc_14000258F
0x140001868  movzx   r12d, word ptr [rbp+140h+var_D8+2]
0x14000186d  xor     r8d, r8d; NetBufferPool
0x140001870  mov     eax, [rbp+140h+var_E8]
0x140001873  mov     r9d, r12d; StartOffset
0x140001876  mov     [rsp+180h+AllocateFragmentFlags], r15d; AllocateFragmentFlags
0x14000187b  xor     edx, edx; NetBufferListPool
0x14000187d  mov     dword ptr [rsp+180h+DataBackFill], r15d; DataBackFill
0x140001882  mov     rcx, r13; OriginalNetBufferList
0x140001885  mov     [rsp+180h+DataOffsetDelta], r12d; DataOffsetDelta
0x14000188a  mov     [rsp+180h+MaximumLength], eax; MaximumLength
0x14000188e  call    cs:__imp_NdisAllocateFragmentNetBufferList
0x140001895  nop     dword ptr [rax+rax+00h]
0x14000189a  mov     rsi, rax
0x14000189d  test    rax, rax
0x1400018a0  jnz     short loc_1400018AC
0x1400018a2  mov     ebx, 0C000009Ah
0x1400018a7  jmp     loc_1400023B3
0x1400018ac  xor     r9d, r9d; FreeMdlMdlHandler
0x1400018af  xor     r8d, r8d; FreeMdl
0x1400018b2  xor     edx, edx; DataOffsetDelta
0x1400018b4  mov     rcx, rsi; NetBufferList
0x1400018b7  call    cs:__imp_NdisAdvanceNetBufferListDataStart
0x1400018be  nop     dword ptr [rax+rax+00h]
0x1400018c3  test    di, di
0x1400018c6  jz      short loc_1400018ED
0x1400018c8  xor     r8d, r8d; ContextBackFill
0x1400018cb  mov     r9d, 6C6F734Ch; PoolTag
0x1400018d1  movzx   edx, di; ContextSize
0x1400018d4  mov     rcx, rsi; NetBufferList
0x1400018d7  call    cs:__imp_NdisAllocateNetBufferListContext
0x1400018de  nop     dword ptr [rax+rax+00h]
0x1400018e3  mov     ebx, eax
0x1400018e5  test    eax, eax
0x1400018e7  js      loc_1400023B3
0x1400018ed  mov     rbx, [rbp+140h+var_D8]
0x1400018f1  movzx   eax, r12w
0x1400018f5  movzx   edi, byte ptr [rbp+140h+var_D8+6]
0x1400018f9  movzx   r14d, bx
0x1400018fd  mov     rcx, [rsi+8]; NetBuffer
0x140001901  sub     r14w, di
0x140001905  sub     ax, bx
0x140001908  mov     [rbp+140h+var_13E], r15b
0x14000190c  movzx   eax, ax
0x14000190f  movzx   edx, r12w
0x140001913  mov     [rbp+140h+BytesNeeded], eax
0x140001916  movzx   eax, bx
0x140001919  mov     [rbp+140h+var_FC], eax
0x14000191c  mov     [rbp+140h+var_140], 1
0x140001920  mov     [rbp+140h+Src], r15
0x140001924  mov     [rbp+140h+var_C8], r15
0x140001928  mov     [rbp+140h+var_F0], r15
0x14000192c  mov     [rbp+140h+var_13D], r15b
0x140001930  mov     [rbp+140h+var_F8], r15d
0x140001934  mov     [rbp+140h+var_104], r15d
0x140001938  mov     [rbp+140h+var_13C], dil
0x14000193c  mov     [rbp+140h+OriginalNetBufferList], rbx
0x140001940  mov     [rbp+140h+var_13A], r14w
0x140001945  mov     [rbp+140h+var_108], dx
0x140001949  mov     [rbp+140h+NetBuffer], rcx
0x14000194d  test    rcx, rcx
0x140001950  jz      loc_140002441
0x140001956  movzx   ebx, dx
0x140001959  mov     r9d, 1; AlignMultiple
0x14000195f  mov     edx, ebx; BytesNeeded
0x140001961  mov     [rsp+180h+MaximumLength], r15d; AlignOffset
0x140001966  xor     r8d, r8d; Storage
0x140001969  call    cs:__imp_NdisGetDataBuffer
0x140001970  nop     dword ptr [rax+rax+00h]
0x140001975  xor     r9d, r9d; FreeMdlHandler
0x140001978  movzx   edi, dil
0x14000197c  movzx   r14d, r14w
0x140001980  mov     r15, rax
0x140001983  test    rax, rax
0x140001986  jnz     loc_140001A36
0x14000198c  mov     rcx, [rbp+140h+NetBuffer]; NetBuffer
0x140001990  xor     r8d, r8d; FreeMdl
0x140001993  mov     edx, edi; DataOffsetDelta
0x140001995  call    cs:__imp_NdisAdvanceNetBufferDataStart
0x14000199c  nop     dword ptr [rax+rax+00h]
0x1400019a1  mov     rcx, [rbp+140h+NetBuffer]; NetBuffer
0x1400019a5  lea     r9d, [r15+1]; AlignMultiple
0x1400019a9  xor     r8d, r8d; Storage
0x1400019ac  mov     [rsp+180h+MaximumLength], r15d; AlignOffset
0x1400019b1  mov     edx, r14d; BytesNeeded
0x1400019b4  call    cs:__imp_NdisGetDataBuffer
0x1400019bb  nop     dword ptr [rax+rax+00h]
0x1400019c0  mov     rcx, [rbp+140h+NetBuffer]; NetBuffer
0x1400019c4  xor     r9d, r9d; AllocateMdlHandler
0x1400019c7  xor     r8d, r8d; DataBackFill
0x1400019ca  mov     [rbp+140h+var_130], rax
0x1400019ce  test    rax, rax
0x1400019d1  jz      loc_140002429
0x1400019d7  mov     edx, r14d; DataOffsetDelta
0x1400019da  call    cs:__imp_NdisAdvanceNetBufferDataStart
0x1400019e1  nop     dword ptr [rax+rax+00h]
0x1400019e6  mov     edx, [rbp+140h+BytesNeeded]; BytesNeeded
0x1400019e9  lea     r9d, [r15+1]; AlignMultiple
0x1400019ed  mov     rcx, [rbp+140h+NetBuffer]; NetBuffer
0x1400019f1  xor     r8d, r8d; Storage
0x1400019f4  mov     [rsp+180h+MaximumLength], r15d; AlignOffset
0x1400019f9  call    cs:__imp_NdisGetDataBuffer
0x140001a00  nop     dword ptr [rax+rax+00h]
0x140001a05  mov     edx, [rbp+140h+var_FC]; DataOffsetDelta
0x140001a08  xor     r9d, r9d; AllocateMdlHandler
0x140001a0b  mov     rcx, [rbp+140h+NetBuffer]; NetBuffer
0x140001a0f  xor     r8d, r8d; DataBackFill
0x140001a12  mov     [rbp+140h+var_110], rax
0x140001a16  call    cs:__imp_NdisRetreatNetBufferDataStart
0x140001a1d  nop     dword ptr [rax+rax+00h]
0x140001a22  xor     r9d, r9d
0x140001a25  cmp     [rbp+140h+var_110], r9
0x140001a29  jz      loc_1400023AA
0x140001a2f  mov     al, 1
0x140001a31  mov     [rbp+140h+var_13E], al
0x140001a34  jmp     short loc_140001A4F
0x140001a36  movzx   eax, [rbp+140h+var_13C]
0x140001a3a  add     rax, r15
0x140001a3d  mov     [rbp+140h+var_130], rax
0x140001a41  movzx   eax, word ptr [rbp+140h+OriginalNetBufferList]
0x140001a45  add     rax, r15
0x140001a48  mov     [rbp+140h+var_110], rax
0x140001a4c  mov     al, [rbp+140h+var_13E]
0x140001a4f  cmp     [rbp+140h+var_F0], r9
  ... truncated ...
```
