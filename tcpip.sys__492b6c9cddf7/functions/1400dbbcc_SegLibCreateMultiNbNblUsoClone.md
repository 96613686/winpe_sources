# SegLibCreateMultiNbNblUsoClone

- ea: `0x1400dbbcc`
- end: `0x1400dc7bc`
- name: `SegLibCreateMultiNbNblUsoClone`
- size: `3056`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, int, int, int, ULONG, __int64, __int64)`
- caller_count: `3`
- callee_count: `12`
- tags: `authz_impersonation, installer_update`

## callers

- `0x1400dd420`
- `0x1400dd720`
- `0x1401aba64`

## callees

- `0x1400d8c1c`
- `0x1400dac20`
- `0x1400db0dc`
- `0x1400dbbcc`
- `0x1400dc7c4`
- `0x1400dd22c`
- `0x1400dd378`
- `0x1401bf342`
- `0x1401bf390`
- `0x1401bf5c0`
- `0x1401bf640`
- `0x1401bf940`

## import_xrefs

- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400dbd1f`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400dbd1f`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400dc557`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1401ce6fa`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1401ce803`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400dc557`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1401ce6fa`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1401ce803`
- `NDIS!NdisCopyReceiveNetBufferListInfo` at `0x1400dc301`
- `NDIS!NdisCopyReceiveNetBufferListInfo` at `0x1400dc301`
- `NDIS!NdisCopySendNetBufferListInfo` at `0x1400dc08e`
- `NDIS!NdisCopySendNetBufferListInfo` at `0x1400dc331`
- `NDIS!NdisCopySendNetBufferListInfo` at `0x1400dc08e`
- `NDIS!NdisCopySendNetBufferListInfo` at `0x1400dc331`
- `NDIS!NdisAllocateFragmentNetBufferList` at `0x1400dbe0e`
- `NDIS!NdisAllocateFragmentNetBufferList` at `0x1400dbe0e`
- `NDIS!NdisFreeNetBufferListContext` at `0x1400dc7aa`
- `NDIS!NdisFreeNetBufferListContext` at `0x1400dc7aa`
- `NDIS!NdisFreeFragmentNetBufferList` at `0x1401ce92a`
- `NDIS!NdisFreeFragmentNetBufferList` at `0x1401ce92a`
- `NDIS!NdisAdvanceNetBufferListDataStart` at `0x1400dbe32`
- `NDIS!NdisAdvanceNetBufferListDataStart` at `0x1400dbe32`
- `NDIS!NdisGetDataBuffer` at `0x1400dbeba`
- `NDIS!NdisGetDataBuffer` at `0x1401ce466`
- `NDIS!NdisGetDataBuffer` at `0x1401ce4ae`
- `NDIS!NdisGetDataBuffer` at `0x1400dbeba`
- `NDIS!NdisGetDataBuffer` at `0x1401ce466`
- `NDIS!NdisGetDataBuffer` at `0x1401ce4ae`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x1401ce443`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x1401ce48b`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x1401ce4fd`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x1401ce516`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x1401ce55d`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x1401ce577`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x1401ce443`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x1401ce48b`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x1401ce4fd`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x1401ce516`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x1401ce55d`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x1401ce577`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x1401ce4ca`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x1401ce5bf`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x1401ce5d9`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x1401ce90e`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x1401ce4ca`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x1401ce5bf`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x1401ce5d9`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x1401ce90e`

## pseudocode

```c
__int64 __fastcall SegLibCreateMultiNbNblUsoClone(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        char a4,
        __int16 *a5,
        int a6,
        int a7,
        int a8,
        ULONG a9,
        __int64 a10,
        __int64 a11)
{
  __int64 v13; // rbx
  __int16 v14; // r15
  char v15; // r12
  __int16 v16; // r8
  bool v17; // al
  __int64 v18; // rax
  __int64 v19; // rdi
  unsigned int v20; // esi
  unsigned __int64 v21; // rcx
  __int64 v22; // rax
  void *v23; // rsp
  int v24; // r8d
  int v25; // r9d
  bool v26; // cf
  struct _NET_BUFFER_LIST *v27; // rsi
  struct _NET_BUFFER_LIST *v28; // r12
  char v29; // di
  int fixed; // ebx
  __int64 v31; // r8
  unsigned __int16 v32; // r14
  struct _NET_BUFFER_LIST *FragmentNetBufferList; // rax
  unsigned __int8 v34; // di
  struct _NET_BUFFER *FirstNetBuffer; // r13
  unsigned __int16 v36; // cx
  unsigned int v37; // ebx
  char *DataBuffer; // rax
  __int64 v39; // rdx
  ULONG v40; // r14d
  __int64 v41; // r9
  void *v42; // r15
  char v43; // al
  __int64 v44; // r8
  unsigned int v45; // eax
  _QWORD *v46; // rdx
  unsigned int v47; // ebx
  __int64 v48; // r8
  __int64 v49; // rcx
  __int64 v50; // rax
  void *v51; // rdi
  __int64 v52; // rdx
  __int64 v53; // rcx
  unsigned int v54; // eax
  _QWORD *v55; // r8
  unsigned int v56; // ebx
  __int64 v57; // rcx
  __int64 v58; // rdx
  int v59; // r15d
  bool v60; // di
  __int64 v61; // r9
  int v62; // edx
  SLIST_HEADER *Alignment; // rdi
  char v64; // r15
  void *v65; // r14
  _QWORD *v66; // rax
  _DWORD *v67; // rcx
  __int64 v69; // r8
  size_t v70; // rdi
  unsigned int v71; // eax
  __int64 v72; // rdx
  unsigned int v73; // ebx
  __int64 v74; // rcx
  __int64 v75; // rax
  void *v76; // rdx
  PVOID v77; // rbx
  __int64 v78; // rcx
  __int64 v79; // rdx
  __int64 v80; // rcx
  __int64 v81; // rax
  __int64 v82; // rax
  _DWORD *v83; // rax
  __int64 v84; // rax
  __int64 v85; // r8
  __int64 v86; // rax
  __int64 v87; // rax
  __int64 v88; // rax
  __int64 v89; // rax
  __int64 v90; // rdx
  unsigned int v91; // eax
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
  _DWORD *v106; // rax
  int v107; // ecx
  __int64 v108; // rax
  __int64 v109; // rdx
  volatile signed __int32 *v110; // rcx
  __int64 v111; // rdx
  __int64 v112; // rcx
  __int64 v113; // rdx
  int MaximumLength; // [rsp+20h] [rbp-20h]
  ULONG DataOffsetDelta; // [rsp+28h] [rbp-18h]
  char DataBackFill; // [rsp+30h] [rbp-10h]
  char v117; // [rsp+40h] [rbp+0h] BYREF
  char v118; // [rsp+41h] [rbp+1h]
  char v119; // [rsp+42h] [rbp+2h]
  char v120; // [rsp+43h] [rbp+3h]
  unsigned __int8 v121; // [rsp+44h] [rbp+4h]
  bool v122; // [rsp+45h] [rbp+5h]
  char v123; // [rsp+46h] [rbp+6h]
  unsigned __int16 v124; // [rsp+48h] [rbp+8h]
  ULONG Size[3]; // [rsp+4Ch] [rbp+Ch]
  int v126; // [rsp+58h] [rbp+18h]
  void *v127; // [rsp+60h] [rbp+20h]
  void *v128; // [rsp+68h] [rbp+28h]
  ULONG v129[4]; // [rsp+70h] [rbp+30h] BYREF
  __int64 v130; // [rsp+80h] [rbp+40h]
  unsigned __int16 v131; // [rsp+88h] [rbp+48h]
  int v132; // [rsp+8Ch] [rbp+4Ch]
  unsigned int v133; // [rsp+90h] [rbp+50h]
  ULONG v134; // [rsp+94h] [rbp+54h]
  int v135; // [rsp+98h] [rbp+58h]
  void *v136; // [rsp+A0h] [rbp+60h]
  void *v137; // [rsp+A8h] [rbp+68h]
  void *Src; // [rsp+B0h] [rbp+70h]
  __int64 v139; // [rsp+B8h] [rbp+78h]
  __int64 v140; // [rsp+C0h] [rbp+80h]
  _QWORD v141[12]; // [rsp+D0h] [rbp+90h] BYREF

  v139 = a10;
  v140 = a11;
  *(_QWORD *)&Size[1] = a2;
  v123 = a4;
  *(_OWORD *)v129 = 0;
  v130 = 0;
  memset(v141, 0, sizeof(v141));
  v126 = 0;
  v13 = 0;
  LOBYTE(v133) = 0;
  v14 = 0;
  v118 = 0;
  v15 = 1;
  if ( a5 )
  {
    v16 = *a5;
    v17 = ((*((_DWORD *)a5 + 7) - 1) & 0xFFFFFFFD) == 0;
    v122 = v17;
    if ( (v16 & 8) != 0 )
    {
      v13 = *((_QWORD *)a5 + 1);
      v14 = a5[8];
      v15 = *((_BYTE *)a5 + 18);
    }
    if ( !v17 )
    {
      v18 = (unsigned int)*(_QWORD *)(a2 + 320);
      if ( (unsigned int)*(_QWORD *)(a2 + 320) || (v16 & 8) != 0 )
        v118 = 1;
      if ( (v16 & 2) != 0 )
      {
        v118 = *((_BYTE *)a5 + 27);
        if ( v118 == 1 )
        {
          LOBYTE(v18) = *((_BYTE *)a5 + 26);
          v133 = v18;
          v126 = (unsigned __int16)a5[12];
        }
      }
      else if ( !v18 )
      {
        v81 = *(_QWORD *)(a2 + 144);
        if ( (v81 & 0x1C) != 0 )
        {
          v91 = (unsigned int)v81 >> 1;
          LOBYTE(v91) = v91 & 1;
          v118 = 1;
          v133 = v91;
        }
        else
        {
          v118 = 0;
        }
      }
    }
  }
  else
  {
    v122 = 0;
  }
  v19 = *(_QWORD *)(a1 + 8);
  v20 = 4;
  if ( v19 && *(_BYTE *)(v19 + 48) )
    v20 = *(_DWORD *)(v19 + 16);
  v21 = 24LL * v20;
  v22 = v21 + 15;
  if ( v21 + 15 < v21 )
    v22 = 0xFFFFFFFFFFFFFF0LL;
  v23 = alloca(v22 & 0xFFFFFFFFFFFFFFF0uLL);
  LODWORD(v141[0]) = -267522035;
  HIDWORD(v141[1]) = KeGetCurrentProcessorNumberEx(0);
  LODWORD(v141[1]) = 0;
  BYTE4(v141[0]) = 0;
  v141[3] = 0;
  v26 = *(_QWORD *)(v19 + 32) != 0;
  v141[2] = 1;
  memset(&v141[6], 0, 20);
  HIDWORD(v141[5]) = 0;
  LOBYTE(v141[5]) = 0;
  LODWORD(v141[1]) = v26 ? 4 : 0;
  v141[4] = &v141[7];
  if ( &v117 )
  {
    HIDWORD(v141[8]) = v20;
    v141[9] = &v117;
  }
  else
  {
    HIDWORD(v141[8]) = 0;
    v141[9] = 0;
  }
  v141[10] = v19;
  LOBYTE(v24) = v123;
  DataBackFill = v15;
  v27 = 0;
  v28 = *(struct _NET_BUFFER_LIST **)&Size[1];
  v29 = 0;
  fixed = SegLibPvtUsoInitialize((unsigned int)v129, Size[1], v24, v25, v13, v14, DataBackFill);
  if ( fixed < 0 )
  {
LABEL_129:
    v32 = WORD1(v130);
  }
  else
  {
    v32 = WORD1(v130);
    FragmentNetBufferList = NdisAllocateFragmentNetBufferList(v28, 0, 0, WORD1(v130), v129[0], WORD1(v130) + a9, 0, 0);
    v27 = FragmentNetBufferList;
    if ( FragmentNetBufferList )
    {
      NdisAdvanceNetBufferListDataStart(FragmentNetBufferList, a9, 0, 0);
      v34 = BYTE6(v130);
      FirstNetBuffer = v27->FirstNetBuffer;
      v124 = v130 - BYTE6(v130);
      v36 = v32;
      Size[0] = (unsigned __int16)(v32 - v130);
      *(_QWORD *)&Size[1] = v130;
      v134 = (unsigned __int16)v130;
      v119 = 0;
      v117 = 1;
      v137 = 0;
      Src = 0;
      v136 = 0;
      v120 = 0;
      v135 = 0;
      v132 = 0;
      v121 = BYTE6(v130);
      v131 = v32;
      while ( 1 )
      {
        if ( !FirstNetBuffer )
        {
          v60 = v122;
          if ( v122 )
          {
            NdisCopyReceiveNetBufferListInfo(v27, v28);
          }
          else
          {
            if ( NetioCopyNetBufferListQosInformationFnPtr )
            {
              v77 = v28->NetBufferListInfo[3];
              v28->NetBufferListInfo[3] = 0;
              NdisCopySendNetBufferListInfo(v27, v28);
              if ( v77 )
              {
                v28->NetBufferListInfo[3] = v77;
                ((void (__fastcall *)(struct _NET_BUFFER_LIST *, struct _NET_BUFFER_LIST *))NetioCopyNetBufferListQosInformationFnPtr)(
                  v27,
                  v28);
              }
            }
            else
            {
              NdisCopySendNetBufferListInfo(v27, v28);
            }
            v27[1].NdisPoolHandle = 0;
          }
          if ( v118 == 1 )
          {
            v62 = v126;
            Alignment = (SLIST_HEADER *)v27->FirstNetBuffer;
            if ( !(_WORD)v126 )
              LOWORD(v62) = Size[1];
            v64 = v133;
            v126 = v62;
            while ( Alignment )
            {
              LOBYTE(v61) = v123;
              LOBYTE(DataOffsetDelta) = v64;
              LOWORD(MaximumLength) = v62;
              *(_QWORD *)&Size[1] = ((v130 & 0x100000000000000LL) == 0) | (2 * (HIBYTE(v130) & 1u)) | 8LL;
              fixed = SegLibDeferredChecksumPacket(v141, Alignment, Size[1], v61, MaximumLength, DataOffsetDelta);
              if ( fixed < 0 )
                goto LABEL_61;
              Alignment = (SLIST_HEADER *)Alignment->Alignment;
              LOWORD(v62) = v126;
            }
            v27->NetBufferListInfo[0] = 0;
          }
          else if ( !v60 )
          {
            *(_QWORD *)&Size[1] = ((v130 & 0x100000000000000LL) == 0) | (2 * (HIBYTE(v130) & 1u)) | 8LL;
            v27->NetBufferListInfo[0] = (PVOID)Size[1];
          }
          v66 = (_QWORD *)v139;
          fixed = 0;
          v67 = (_DWORD *)v140;
          v27->ParentNetBufferList = v28;
          *v66 = v27;
          *v67 = v32;
          goto LABEL_61;
        }
        v37 = v36;
        DataBuffer = (char *)NdisGetDataBuffer(FirstNetBuffer, v36, 0, 1u, 0);
        v40 = v124;
        v41 = 0;
        v42 = DataBuffer;
        if ( DataBuffer )
        {
          v127 = &DataBuffer[v121];
          v128 = &DataBuffer[LOWORD(Size[1])];
          v43 = v119;
        }
        else
        {
          NdisAdvanceNetBufferDataStart(FirstNetBuffer, v34, 0, 0);
          v127 = NdisGetDataBuffer(FirstNetBuffer, v40, 0, 1u, 0);
          if ( !v127 )
          {
            fixed = -1073741670;
            NdisRetreatNetBufferDataStart(FirstNetBuffer, v34, 0, 0);
LABEL_130:
            v32 = WORD1(v130);
LABEL_61:
            v29 = v117;
            goto LABEL_62;
          }
          NdisAdvanceNetBufferDataStart(FirstNetBuffer, v40, 0, 0);
          v128 = NdisGetDataBuffer(FirstNetBuffer, Size[0], 0, 1u, 0);
          NdisRetreatNetBufferDataStart(FirstNetBuffer, v134, 0, 0);
          v41 = 0;
          if ( !v128 )
          {
            fixed = -1073741670;
            goto LABEL_130;
          }
          v43 = 1;
          v119 = 1;
        }
        if ( !v136 )
        {
          if ( v43 )
          {
            NdisAdvanceNetBufferDataStart(FirstNetBuffer, v34, 0, 0);
            NdisAdvanceNetBufferDataStart(v28->FirstNetBuffer, v34, 0, 0);
            v51 = v127;
            fixed = SegLibPvtDeferredCopyMdlChainData(
                      v141,
                      *(_QWORD *)(v28->Link.Region + 8),
                      *(unsigned int *)(v28->Link.Region + 16),
                      v40,
                      v127);
            if ( fixed < 0 )
              goto LABEL_130;
            NdisAdvanceNetBufferDataStart(FirstNetBuffer, v40, 0, 0);
            NdisAdvanceNetBufferDataStart(v28->FirstNetBuffer, v40, 0, 0);
            v65 = v128;
            fixed = SegLibPvtDeferredCopyMdlChainData(
                      v141,
                      *(_QWORD *)(v28->Link.Region + 8),
                      *(unsigned int *)(v28->Link.Region + 16),
                      Size[0],
                      v128);
            if ( fixed < 0 )
              goto LABEL_130;
            NdisRetreatNetBufferDataStart(FirstNetBuffer, v134, 0, 0);
            NdisRetreatNetBufferDataStart(v28->FirstNetBuffer, v134, 0, 0);
          }
          else
          {
            fixed = SegLibPvtDeferredCopyMdlChainData(
                      v141,
                      *(_QWORD *)(v28->Link.Region + 8),
                      *(unsigned int *)(v28->Link.Region + 16),
                      v37,
                      v42);
            if ( fixed < 0 )
              goto LABEL_130;
            v51 = v127;
            v65 = v128;
          }
          LOBYTE(v31) = 1;
          BLFlushBatchOpContextEx(v141, 0, v31);
          fixed = SegLibPvtUsoParseHeaders(v129, v51, v65);
          if ( fixed < 0 )
          {
            v29 = v117;
            goto LABEL_129;
          }
          v120 = v119;
          v137 = v42;
          Src = v51;
          v136 = v65;
          goto LABEL_35;
        }
        if ( v120 || v43 )
        {
          v44 = v141[10];
          if ( *(_BYTE *)(v141[10] + 1LL) == 1 && !BYTE4(v141[0]) )
          {
            v86 = 0;
            BYTE4(v141[0]) = 1;
            if ( HIDWORD(v141[1]) != -1 )
            {
              v39 = *(_QWORD *)(v141[10] + 24LL);
              if ( v39 )
                v86 = v39 + 20LL * HIDWORD(v141[1]);
            }
            _InterlockedAdd16((volatile signed __int16 *)(v86 + 16), 1u);
            v44 = v141[10];
          }
          v45 = *(_DWORD *)(v44 + 4);
          if ( v45 )
          {
            v46 = (_QWORD *)v141[4];
            v47 = *(_DWORD *)(v141[4] + 8LL);
            if ( v47 >= *(_DWORD *)(v141[4] + 12LL) )
            {
              v47 = 0;
              if ( LODWORD(v141[2]) < v45
                && (v99 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v44 + 64)),
                    v41 = 0,
                    (v46 = v99) != 0) )
              {
                *(_QWORD *)v99 = 0;
                v99[2] = 0;
                v100 = *(_DWORD *)(v141[10] + 8LL);
                *((_QWORD *)v99 + 2) = v99 + 6;
                v99[3] = v100;
                *(_QWORD *)v141[4] = v99;
                ++LODWORD(v141[2]);
                v141[4] = v99;
                if ( *(_BYTE *)(v141[10] + 1LL) == 1 )
                {
                  v101 = 0;
                  if ( HIDWORD(v141[1]) != -1 )
                  {
                    v102 = *(_QWORD *)(v141[10] + 24LL);
                    if ( v102 )
                      v101 = v102 + 20LL * HIDWORD(v141[1]);
                  }
                  _InterlockedAdd16((volatile signed __int16 *)(v101 + 12), 1u);
                  v103 = 0;
                  if ( HIDWORD(v141[1]) != -1 )
                  {
                    v104 = *(_QWORD *)(v141[10] + 24LL);
                    if ( v104 )
                      v103 = (volatile signed __int32 *)(v104 + 20LL * HIDWORD(v141[1]));
                  }
                  _InterlockedAdd(v103, 1u);
                }
              }
              else
              {
                LOBYTE(v46) = 1;
                BLFlushBatchOpContextEx(v141, v46, 0);
                v46 = &v141[7];
                v41 = 0;
              }
            }
            ++HIDWORD(v141[2]);
            ++*((_DWORD *)v46 + 2);
            v48 = v141[10];
            if ( *(_BYTE *)(v141[10] + 1LL) == 1 )
            {
              v87 = 0;
              if ( HIDWORD(v141[1]) != -1 )
              {
                v48 = *(_QWORD *)(v141[10] + 24LL);
                if ( v48 )
                  v87 = v48 + 20LL * HIDWORD(v141[1]);
              }
              _InterlockedAdd16((volatile signed __int16 *)(v87 + 14), 1u);
              v105 = 0;
              if ( HIDWORD(v141[1]) != -1 )
              {
                v48 = *(_QWORD *)(v141[10] + 24LL);
                if ( v48 )
                  v105 = v48 + 20LL * HIDWORD(v141[1]);
              }
              _InterlockedAdd((volatile signed __int32 *)(v105 + 4), 1u);
            }
            v49 = 3LL * v47;
            v50 = v46[2];
            LODWORD(v51) = (_DWORD)v127;
            v52 = (__int64)Src;
            *(_QWORD *)(v50 + 8 * v49) = v127;
            *(_DWORD *)(v50 + 8 * v49 + 16) = (16 * v40) | 1;
            *(_QWORD *)(v50 + 8 * v49 + 8) = v52;
          }
          else
          {
            if ( HIDWORD(v141[2]) )
            {
              LOBYTE(v39) = 1;
              BLFlushBatchOpContextEx(v141, v39, 0);
              v44 = v141[10];
            }
            v78 = LODWORD(v141[1]);
            if ( (v141[1] & 5) == 5 || (v78 = v141[1] & 6, (v141[1] & 6) == 6) )
            {
              (*(void (__fastcall **)(__int64, __int64, __int64, __int64))(v44 + 32))(v78, v39, v44, v41);
              LODWORD(v51) = (_DWORD)v127;
              memmove(v127, Src, v124);
              (*(void (**)(void))(v141[10] + 40LL))();
            }
            else
            {
              LODWORD(v51) = (_DWORD)v127;
              memmove(v127, Src, v124);
            }
          }
          v53 = v141[10];
          if ( *(_BYTE *)(v141[10] + 1LL) == 1 && !BYTE4(v141[0]) )
          {
            v52 = 0xFFFFFFFFLL;
            BYTE4(v141[0]) = 1;
            v88 = 0;
            if ( HIDWORD(v141[1]) != -1 )
            {
              v52 = *(_QWORD *)(v141[10] + 24LL);
              if ( v52 )
                v88 = v52 + 20LL * HIDWORD(v141[1]);
            }
            _InterlockedAdd16((volatile signed __int16 *)(v88 + 16), 1u);
            v53 = v141[10];
          }
          v54 = *(_DWORD *)(v53 + 4);
          if ( v54 )
          {
            v55 = (_QWORD *)v141[4];
            v56 = *(_DWORD *)(v141[4] + 8LL);
            if ( v56 >= *(_DWORD *)(v141[4] + 12LL) )
            {
              v56 = 0;
              if ( LODWORD(v141[2]) < v54
                && (v106 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v53 + 64)), (v55 = v106) != 0) )
              {
                *(_QWORD *)v106 = 0;
                v106[2] = 0;
                v107 = *(_DWORD *)(v141[10] + 8LL);
                *((_QWORD *)v106 + 2) = v106 + 6;
                v106[3] = v107;
                *(_QWORD *)v141[4] = v106;
                ++LODWORD(v141[2]);
                v141[4] = v106;
                if ( *(_BYTE *)(v141[10] + 1LL) == 1 )
                {
                  v108 = 0;
                  if ( HIDWORD(v141[1]) != -1 )
                  {
                    v109 = *(_QWORD *)(v141[10] + 24LL);
                    if ( v109 )
                      v108 = v109 + 20LL * HIDWORD(v141[1]);
                  }
                  _InterlockedAdd16((volatile signed __int16 *)(v108 + 12), 1u);
                  v110 = 0;
                  if ( HIDWORD(v141[1]) != -1 )
                  {
                    v111 = *(_QWORD *)(v141[10] + 24LL);
                    if ( v111 )
                      v110 = (volatile signed __int32 *)(v111 + 20LL * HIDWORD(v141[1]));
                  }
                  _InterlockedAdd(v110, 1u);
                }
              }
              else
              {
                LOBYTE(v52) = 1;
                BLFlushBatchOpContextEx(v141, v52, 0);
                v55 = &v141[7];
              }
            }
            ++HIDWORD(v141[2]);
            ++*((_DWORD *)v55 + 2);
            if ( *(_BYTE *)(v141[10] + 1LL) == 1 )
            {
              v89 = 0;
              if ( HIDWORD(v141[1]) != -1 )
              {
                v90 = *(_QWORD *)(v141[10] + 24LL);
                if ( v90 )
                  v89 = v90 + 20LL * HIDWORD(v141[1]);
              }
              _InterlockedAdd16((volatile signed __int16 *)(v89 + 14), 1u);
              v112 = 0;
              if ( HIDWORD(v141[1]) != -1 )
              {
                v113 = *(_QWORD *)(v141[10] + 24LL);
                if ( v113 )
                  v112 = v113 + 20LL * HIDWORD(v141[1]);
              }
              _InterlockedAdd((volatile signed __int32 *)(v112 + 4), 1u);
            }
            v57 = v55[2];
            v58 = 3LL * v56;
            *(_QWORD *)(v57 + 8 * v58) = v128;
            *(_QWORD *)(v57 + 8 * v58 + 8) = v136;
            *(_DWORD *)(v57 + 8 * v58 + 16) = (16 * Size[0]) | 1;
          }
          else
          {
            if ( HIDWORD(v141[2]) )
            {
              LOBYTE(v52) = 1;
              BLFlushBatchOpContextEx(v141, v52, 0);
              v53 = v141[10];
            }
            v79 = LODWORD(v141[1]);
            if ( (v141[1] & 5) == 5 || (v79 = v141[1] & 6, (v141[1] & 6) == 6) )
            {
              (*(void (__fastcall **)(__int64, __int64, __int64, __int64))(v53 + 32))(v53, v79, v48, v41);
              memmove(v128, v136, Size[0]);
              (*(void (**)(void))(v141[10] + 40LL))();
            }
            else
            {
              memmove(v128, v136, Size[0]);
            }
          }
LABEL_35:
          v32 = WORD1(v130);
          goto LABEL_36;
        }
        v69 = v141[10];
        v32 = WORD1(v130);
        v70 = WORD1(v130);
        if ( *(_BYTE *)(v141[10] + 1LL) == 1 && !BYTE4(v141[0]) )
        {
          BYTE4(v141[0]) = 1;
          v82 = 0;
          if ( HIDWORD(v141[1]) != -1 )
          {
            v39 = *(_QWORD *)(v141[10] + 24LL);
            if ( v39 )
              v82 = v39 + 20LL * HIDWORD(v141[1]);
          }
          _InterlockedAdd16((volatile signed __int16 *)(v82 + 16), 1u);
          v69 = v141[10];
        }
        v71 = *(_DWORD *)(v69 + 4);
        if ( !v71 )
        {
          if ( HIDWORD(v141[2]) )
          {
            LOBYTE(v39) = 1;
            BLFlushBatchOpContextEx(v141, v39, 0);
            v69 = v141[10];
          }
          v80 = LODWORD(v141[1]);
          if ( (v141[1] & 5) == 5 || (v80 = v141[1] & 6, (v141[1] & 6) == 6) )
          {
            (*(void (__fastcall **)(__int64, __int64, __int64, __int64))(v69 + 32))(v80, v39, v69, v41);
            memmove(v42, v137, v70);
            (*(void (**)(void))(v141[10] + 40LL))();
          }
          else
          {
            memmove(v42, v137, v70);
          }
          goto LABEL_69;
        }
        v72 = v141[4];
        v73 = *(_DWORD *)(v141[4] + 8LL);
        if ( v73 >= *(_DWORD *)(v141[4] + 12LL) )
        {
          v73 = 0;
          if ( LODWORD(v141[2]) < v71 )
          {
            v83 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v69 + 64));
            v72 = (__int64)v83;
            if ( v83 )
            {
              *(_QWORD *)v83 = 0;
              v83[2] = 0;
              v92 = *(_DWORD *)(v141[10] + 8LL);
              *((_QWORD *)v83 + 2) = v83 + 6;
              v83[3] = v92;
              *(_QWORD *)v141[4] = v83;
              ++LODWORD(v141[2]);
              v141[4] = v83;
              if ( *(_BYTE *)(v141[10] + 1LL) == 1 )
              {
                v93 = 0;
                if ( HIDWORD(v141[1]) != -1 )
                {
                  v94 = *(_QWORD *)(v141[10] + 24LL);
                  if ( v94 )
                    v93 = v94 + 20LL * HIDWORD(v141[1]);
                }
                _InterlockedAdd16((volatile signed __int16 *)(v93 + 12), 1u);
                v95 = 0;
                if ( HIDWORD(v141[1]) != -1 )
                {
                  v96 = *(_QWORD *)(v141[10] + 24LL);
                  if ( v96 )
                    v95 = (volatile signed __int32 *)(v96 + 20LL * HIDWORD(v141[1]));
                }
                _InterlockedAdd(v95, 1u);
              }
              goto LABEL_67;
            }
            v72 = 1;
          }
          else
          {
            LOBYTE(v72) = 1;
          }
          BLFlushBatchOpContextEx(v141, v72, 0);
          v72 = (__int64)&v141[7];
        }
LABEL_67:
        ++HIDWORD(v141[2]);
        ++*(_DWORD *)(v72 + 8);
        if ( *(_BYTE *)(v141[10] + 1LL) == 1 )
        {
          v84 = 0;
          if ( HIDWORD(v141[1]) != -1 )
          {
            v85 = *(_QWORD *)(v141[10] + 24LL);
            if ( v85 )
              v84 = v85 + 20LL * HIDWORD(v141[1]);
          }
          _InterlockedAdd16((volatile signed __int16 *)(v84 + 14), 1u);
          v97 = 0;
          if ( HIDWORD(v141[1]) != -1 )
          {
            v98 = *(_QWORD *)(v141[10] + 24LL);
            if ( v98 )
              v97 = v98 + 20LL * HIDWORD(v141[1]);
          }
          _InterlockedAdd((volatile signed __int32 *)(v97 + 4), 1u);
        }
        v74 = 3LL * v73;
        v75 = *(_QWORD *)(v72 + 16);
        v76 = v137;
        *(_QWORD *)(v75 + 8 * v74) = v42;
        *(_DWORD *)(v75 + 8 * v74 + 16) = (16 * v70) | 1;
        *(_QWORD *)(v75 + 8 * v74 + 8) = v76;
LABEL_69:
        LODWORD(v51) = (_DWORD)v127;
LABEL_36:
        v59 = v135;
        fixed = SegLibPvtUsoDeferredFixHeaders(
                  (unsigned int)v141,
                  (unsigned int)v129,
                  (_DWORD)v51,
                  (_DWORD)v128,
                  v135,
                  v132);
        if ( fixed < 0 )
          goto LABEL_61;
        FirstNetBuffer = (struct _NET_BUFFER *)FirstNetBuffer->Link.Alignment;
        v34 = v121;
        v36 = v131;
        v135 = v59 + 1;
        v132 += v129[0];
      }
    }
    fixed = -1073741670;
  }
LABEL_62:
  LOBYTE(v31) = 1;
  BLFlushBatchOpContextEx(v141, 0, v31);
  if ( fixed < 0 && v27 )
  {
    if ( v29 == 1 )
      NdisFreeNetBufferListContext(v27, 0);
    NdisFreeFragmentNetBufferList(v27, v32, 0);
  }
  return (unsigned int)fixed;
}

```

## disassembly

```asm
0x1400dbbcc  push    rbp
0x1400dbbce  push    rsi
0x1400dbbcf  push    rdi
0x1400dbbd0  push    r12
0x1400dbbd2  push    r13
0x1400dbbd4  push    r14
0x1400dbbd6  push    r15
0x1400dbbd8  sub     rsp, 140h
0x1400dbbdf  lea     rbp, [rsp+40h]
0x1400dbbe4  mov     [rbp+130h+arg_0], rbx
0x1400dbbeb  mov     rax, cs:__security_cookie
0x1400dbbf2  xor     rax, rbp
0x1400dbbf5  mov     [rbp+130h+var_40], rax
0x1400dbbfc  mov     rax, [rbp+130h+arg_48]
0x1400dbc03  mov     rsi, rdx
0x1400dbc06  mov     r13d, [rbp+130h+arg_40]
0x1400dbc0d  mov     rdi, rcx
0x1400dbc10  mov     [rbp+130h+var_B8], rax
0x1400dbc14  lea     rcx, [rbp+130h+var_A0]; void *
0x1400dbc1b  mov     rax, [rbp+130h+arg_50]
0x1400dbc22  xorps   xmm0, xmm0
0x1400dbc25  mov     [rbp+130h+var_B0], rax
0x1400dbc2c  xor     eax, eax
0x1400dbc2e  mov     qword ptr [rbp+130h+Size+4], rdx
0x1400dbc32  xor     edx, edx; Val
0x1400dbc34  mov     [rbp+130h+var_12A], r9b
0x1400dbc38  movups  xmmword ptr [rbp+130h+var_100], xmm0
0x1400dbc3c  lea     r8d, [rax+60h]; Size
0x1400dbc40  mov     [rbp+130h+var_F0], rax
0x1400dbc44  call    memset
0x1400dbc49  mov     rcx, [rbp+130h+arg_20]
0x1400dbc50  xor     r9d, r9d
0x1400dbc53  mov     [rbp+130h+var_118], r9d
0x1400dbc57  mov     ebx, r9d
0x1400dbc5a  mov     byte ptr [rbp+130h+var_E0], r9b
0x1400dbc5e  mov     r15d, r9d
0x1400dbc61  mov     [rbp+130h+var_12F], r9b
0x1400dbc65  mov     r11d, 0FFFFFFFFh
0x1400dbc6b  lea     r10d, [r9+1]
0x1400dbc6f  lea     r14d, [r9+8]
0x1400dbc73  mov     r12b, r10b
0x1400dbc76  test    rcx, rcx
0x1400dbc79  jz      loc_1400DC4A5
0x1400dbc7f  mov     eax, [rcx+1Ch]
0x1400dbc82  movzx   r8d, word ptr [rcx]
0x1400dbc86  sub     eax, r10d
0x1400dbc89  test    eax, 0FFFFFFFDh
0x1400dbc8e  movzx   edx, r8w
0x1400dbc92  setz    al
0x1400dbc95  mov     [rbp+130h+var_12B], al
0x1400dbc98  and     dx, r14w
0x1400dbc9c  jnz     loc_1400DC44C
0x1400dbca2  test    al, al
0x1400dbca4  jnz     short loc_1400DBCCD
0x1400dbca6  mov     rax, [rsi+140h]
0x1400dbcad  and     rax, r11
0x1400dbcb0  jz      loc_1400DC45E
0x1400dbcb6  mov     [rbp+130h+var_12F], r10b
0x1400dbcba  test    r8b, 2
0x1400dbcbe  jnz     loc_1400DC46C
0x1400dbcc4  test    rax, rax
0x1400dbcc7  jz      loc_1400DC48D
0x1400dbccd  mov     rdi, [rdi+8]
0x1400dbcd1  mov     esi, 4
0x1400dbcd6  test    rdi, rdi
0x1400dbcd9  jz      short loc_1400DBCE5
0x1400dbcdb  cmp     [rdi+30h], r9b
0x1400dbcdf  jnz     loc_1400DC4AE
0x1400dbce5  mov     eax, esi
0x1400dbce7  lea     rcx, [rax+rax*2]
0x1400dbceb  shl     rcx, 3
0x1400dbcef  lea     rax, [rcx+0Fh]
0x1400dbcf3  cmp     rax, rcx
0x1400dbcf6  ja      short loc_1400DBD02
0x1400dbcf8  mov     rax, 0FFFFFFFFFFFFFF0h
0x1400dbd02  and     rax, 0FFFFFFFFFFFFFFF0h
0x1400dbd06  call    __chkstk_0
0x1400dbd0b  sub     rsp, rax
0x1400dbd0e  mov     [rbp+130h+var_A0], 0F00DF00Dh
0x1400dbd18  xor     ecx, ecx; ProcNumber
0x1400dbd1a  lea     r14, [rsp+170h+var_130]
0x1400dbd1f  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1400dbd26  nop     dword ptr [rax+rax+00h]
0x1400dbd2b  xor     edx, edx
0x1400dbd2d  mov     [rbp+130h+var_94], eax
0x1400dbd33  mov     [rbp+130h+var_98], edx
0x1400dbd39  mov     [rbp+130h+var_9C], dl
0x1400dbd3f  mov     [rbp+130h+var_88], rdx
0x1400dbd46  mov     rax, [rdi+20h]
0x1400dbd4a  neg     rax
0x1400dbd4d  mov     [rbp+130h+var_90], 1
0x1400dbd58  lea     rax, [rbp+130h+var_68]
0x1400dbd5f  mov     [rbp+130h+var_70], rdx
0x1400dbd66  sbb     ecx, ecx
0x1400dbd68  mov     [rbp+130h+var_74], edx
0x1400dbd6e  and     ecx, 4
0x1400dbd71  mov     [rbp+130h+var_78], dl
0x1400dbd77  mov     [rbp+130h+var_98], ecx
0x1400dbd7d  mov     [rbp+130h+var_68], rdx
0x1400dbd84  mov     [rbp+130h+var_60], edx
0x1400dbd8a  mov     [rbp+130h+var_80], rax
0x1400dbd91  test    r14, r14
0x1400dbd94  jz      loc_1400DC2EF
0x1400dbd9a  mov     [rbp+130h+var_5C], esi
0x1400dbda0  mov     [rbp+130h+var_58], r14
0x1400dbda7  mov     [rbp+130h+var_50], rdi
0x1400dbdae  mov     r8b, [rbp+130h+var_12A]
0x1400dbdb2  lea     rcx, [rbp+130h+var_100]
0x1400dbdb6  mov     [rsp+170h+DataBackFill], r12b
0x1400dbdbb  mov     rsi, rdx
0x1400dbdbe  mov     r12, qword ptr [rbp+130h+Size+4]
0x1400dbdc2  mov     dil, dl
0x1400dbdc5  mov     rdx, r12
0x1400dbdc8  mov     word ptr [rsp+170h+DataOffsetDelta], r15w
0x1400dbdce  mov     qword ptr [rsp+170h+MaximumLength], rbx
0x1400dbdd3  call    SegLibPvtUsoInitialize
0x1400dbdd8  xor     r15d, r15d
0x1400dbddb  mov     ebx, eax
0x1400dbddd  test    eax, eax
0x1400dbddf  js      loc_1400DC77F
0x1400dbde5  movzx   r14d, word ptr [rbp+130h+var_F0+2]
0x1400dbdea  xor     r8d, r8d; NetBufferPool
0x1400dbded  mov     [rsp+170h+AllocateFragmentFlags], r15d; AllocateFragmentFlags
0x1400dbdf2  mov     r9d, r14d; StartOffset
0x1400dbdf5  mov     dword ptr [rsp+170h+DataBackFill], r15d; DataBackFill
0x1400dbdfa  xor     edx, edx; NetBufferListPool
0x1400dbdfc  mov     rcx, r12; OriginalNetBufferList
0x1400dbdff  lea     eax, [r14+r13]
0x1400dbe03  mov     [rsp+170h+DataOffsetDelta], eax; DataOffsetDelta
0x1400dbe07  mov     eax, [rbp+130h+var_100]
0x1400dbe0a  mov     [rsp+170h+MaximumLength], eax; MaximumLength
0x1400dbe0e  call    cs:__imp_NdisAllocateFragmentNetBufferList
0x1400dbe15  nop     dword ptr [rax+rax+00h]
0x1400dbe1a  mov     rsi, rax
0x1400dbe1d  test    rax, rax
0x1400dbe20  jz      loc_1400DC4B6
0x1400dbe26  xor     r9d, r9d; FreeMdlMdlHandler
0x1400dbe29  xor     r8d, r8d; FreeMdl
0x1400dbe2c  mov     edx, r13d; DataOffsetDelta
0x1400dbe2f  mov     rcx, rax; NetBufferList
0x1400dbe32  call    cs:__imp_NdisAdvanceNetBufferListDataStart
0x1400dbe39  nop     dword ptr [rax+rax+00h]
0x1400dbe3e  mov     rbx, [rbp+130h+var_F0]
0x1400dbe42  movzx   eax, r14w
0x1400dbe46  movzx   edi, byte ptr [rbp+130h+var_F0+6]
0x1400dbe4a  movzx   ecx, bx
0x1400dbe4d  mov     r13, [rsi+8]
0x1400dbe51  sub     cx, di
0x1400dbe54  sub     ax, bx
0x1400dbe57  mov     [rbp+130h+var_128], cx
0x1400dbe5b  movzx   eax, ax
0x1400dbe5e  movzx   ecx, r14w
0x1400dbe62  mov     dword ptr [rbp+130h+Size], eax
0x1400dbe65  movzx   eax, bx
0x1400dbe68  mov     qword ptr [rbp+130h+Size+4], rbx
0x1400dbe6c  lea     ebx, [r15+1]
0x1400dbe70  mov     [rbp+130h+var_DC], eax
0x1400dbe73  mov     [rbp+130h+var_12E], r15b
0x1400dbe77  mov     [rbp+130h+var_130], 1
0x1400dbe7b  mov     [rbp+130h+var_C8], r15
0x1400dbe7f  mov     [rbp+130h+Src], r15
0x1400dbe83  mov     [rbp+130h+var_D0], r15
0x1400dbe87  mov     [rbp+130h+var_12D], r15b
0x1400dbe8b  mov     [rbp+130h+var_D8], r15d
0x1400dbe8f  mov     [rbp+130h+var_E4], r15d
0x1400dbe93  mov     [rbp+130h+var_12C], dil
0x1400dbe97  mov     [rbp+130h+var_E8], cx
0x1400dbe9b  test    r13, r13
0x1400dbe9e  jz      loc_1400DC06E
0x1400dbea4  movzx   ebx, cx
0x1400dbea7  mov     r9d, 1; AlignMultiple
0x1400dbead  mov     edx, ebx; BytesNeeded
0x1400dbeaf  mov     [rsp+170h+MaximumLength], r15d; AlignOffset
0x1400dbeb4  xor     r8d, r8d; Storage
0x1400dbeb7  mov     rcx, r13; NetBuffer
0x1400dbeba  call    cs:__imp_NdisGetDataBuffer
0x1400dbec1  nop     dword ptr [rax+rax+00h]
0x1400dbec6  movzx   r14d, [rbp+130h+var_128]
0x1400dbecb  xor     r9d, r9d; FreeMdlHandler
0x1400dbece  movzx   edi, dil
0x1400dbed2  mov     r15, rax
0x1400dbed5  test    rax, rax
0x1400dbed8  jz      loc_1401CE43B
0x1400dbede  movzx   eax, [rbp+130h+var_12C]
0x1400dbee2  lea     r10d, [r9+1]
0x1400dbee6  add     rax, r15
0x1400dbee9  mov     [rbp+130h+var_110], rax
0x1400dbeed  movzx   eax, word ptr [rbp+130h+Size+4]
0x1400dbef1  add     rax, r15
0x1400dbef4  mov     [rbp+130h+var_108], rax
0x1400dbef8  mov     al, [rbp+130h+var_12E]
0x1400dbefb  cmp     [rbp+130h+var_D0], r9
0x1400dbeff  jz      loc_1400DC17C
0x1400dbf05  cmp     [rbp+130h+var_12D], r9b
0x1400dbf09  jnz     short loc_1400DBF13
0x1400dbf0b  test    al, al
0x1400dbf0d  jz      loc_1400DC26B
0x1400dbf13  mov     r8, [rbp+130h+var_50]
0x1400dbf1a  mov     r15d, 1
0x1400dbf20  mov     edi, 0FFFFFFFFh
0x1400dbf25  cmp     [r8+1], r15b
0x1400dbf29  jz      loc_1400DC5A9
0x1400dbf2f  mov     eax, [r8+4]
0x1400dbf33  test    eax, eax
0x1400dbf35  jz      loc_1400DC384
0x1400dbf3b  mov     rdx, [rbp+130h+var_80]
0x1400dbf42  mov     ebx, [rdx+8]
0x1400dbf45  cmp     ebx, [rdx+0Ch]
0x1400dbf48  jnb     loc_1400DC11F
0x1400dbf4e  add     dword ptr [rbp+130h+var_90+4], r15d
0x1400dbf55  add     [rdx+8], r15d
0x1400dbf59  mov     r8, [rbp+130h+var_50]
0x1400dbf60  cmp     [r8+1], r15b
0x1400dbf64  jz      loc_1400DC63D
0x1400dbf6a  mov     eax, ebx
0x1400dbf6c  lea     rcx, [rax+rax*2]
0x1400dbf70  mov     rax, [rdx+10h]
0x1400dbf74  mov     rdi, [rbp+130h+var_110]
0x1400dbf78  mov     rdx, [rbp+130h+Src]
0x1400dbf7c  shl     r14d, 4
0x1400dbf80  or      r14d, r15d
0x1400dbf83  mov     [rax+rcx*8], rdi
0x1400dbf87  mov     [rax+rcx*8+10h], r14d
0x1400dbf8c  mov     [rax+rcx*8+8], rdx
0x1400dbf91  mov     rcx, [rbp+130h+var_50]
0x1400dbf98  xor     r14d, r14d
0x1400dbf9b  cmp     [rcx+1], r15b
0x1400dbf9f  jz      loc_1400DC66C
0x1400dbfa5  mov     eax, [rcx+4]
0x1400dbfa8  test    eax, eax
0x1400dbfaa  jz      loc_1400DC3CA
0x1400dbfb0  mov     r8, [rbp+130h+var_80]
0x1400dbfb7  mov     ebx, [r8+8]
0x1400dbfbb  cmp     ebx, [r8+0Ch]
0x1400dbfbf  jnb     loc_1400DC14F
0x1400dbfc5  mov     r9d, 0FFFFFFFFh
0x1400dbfcb  add     dword ptr [rbp+130h+var_90+4], r15d
0x1400dbfd2  add     [r8+8], r15d
0x1400dbfd6  mov     rdx, [rbp+130h+var_50]
0x1400dbfdd  cmp     [rdx+1], r15b
0x1400dbfe1  jz      loc_1400DC701
0x1400dbfe7  mov     rcx, [r8+10h]
0x1400dbfeb  mov     eax, ebx
0x1400dbfed  lea     rdx, [rax+rax*2]
0x1400dbff1  mov     rax, [rbp+130h+var_108]
0x1400dbff5  mov     [rcx+rdx*8], rax
0x1400dbff9  mov     rax, [rbp+130h+var_D0]
0x1400dbffd  mov     [rcx+rdx*8+8], rax
0x1400dc002  mov     eax, dword ptr [rbp+130h+Size]
0x1400dc005  shl     eax, 4
0x1400dc008  or      eax, r15d
0x1400dc00b  mov     [rcx+rdx*8+10h], eax
0x1400dc00f  movzx   r14d, word ptr [rbp+130h+var_F0+2]
0x1400dc014  mov     eax, [rbp+130h+var_E4]
0x1400dc017  lea     rdx, [rbp+130h+var_100]
0x1400dc01b  mov     r15d, [rbp+130h+var_D8]
0x1400dc01f  lea     rcx, [rbp+130h+var_A0]
0x1400dc026  mov     r9, [rbp+130h+var_108]
0x1400dc02a  mov     r8, rdi
0x1400dc02d  mov     [rsp+170h+DataOffsetDelta], eax
0x1400dc031  mov     [rsp+170h+MaximumLength], r15d
0x1400dc036  call    SegLibPvtUsoDeferredFixHeaders
0x1400dc03b  mov     ebx, eax
0x1400dc03d  test    eax, eax
0x1400dc03f  js      loc_1400DC21C
0x1400dc045  mov     edx, [rbp+130h+var_E4]
0x1400dc048  mov     ebx, 1
0x1400dc04d  add     edx, [rbp+130h+var_100]
0x1400dc050  add     r15d, ebx
0x1400dc053  mov     r13, [r13+0]
0x1400dc057  mov     dil, [rbp+130h+var_12C]
0x1400dc05b  movzx   ecx, [rbp+130h+var_E8]
0x1400dc05f  mov     [rbp+130h+var_D8], r15d
0x1400dc063  xor     r15d, r15d
0x1400dc066  mov     [rbp+130h+var_E4], edx
0x1400dc069  jmp     loc_1400DBE9B
0x1400dc06e  mov     dil, [rbp+130h+var_12B]
0x1400dc072  mov     rdx, r12; SrcNetBufferList
0x1400dc075  mov     rcx, rsi; DestNetBufferList
0x1400dc078  cmp     dil, bl
0x1400dc07b  jz      loc_1400DC301
0x1400dc081  cmp     cs:NetioCopyNetBufferListQosInformationFnPtr, r15
0x1400dc088  jnz     loc_1400DC321
0x1400dc08e  call    cs:__imp_NdisCopySendNetBufferListInfo
0x1400dc095  nop     dword ptr [rax+rax+00h]
0x1400dc09a  mov     [rsi+140h], r15
0x1400dc0a1  cmp     [rbp+130h+var_12F], bl
0x1400dc0a4  jnz     loc_1400DC1F8
0x1400dc0aa  mov     edx, [rbp+130h+var_118]
0x1400dc0ad  test    dx, dx
0x1400dc0b0  mov     rdi, [rsi+8]
0x1400dc0b4  cmovz   dx, word ptr [rbp+130h+Size+4]
0x1400dc0b9  xor     r13d, r13d
0x1400dc0bc  mov     r15d, [rbp+130h+var_E0]
0x1400dc0c0  mov     [rbp+130h+var_118], edx
0x1400dc0c3  test    rdi, rdi
0x1400dc0c6  jz      loc_1400DC312
0x1400dc0cc  mov     al, byte ptr [rbp+130h+var_F0+7]
0x1400dc0cf  movzx   ecx, byte ptr [rbp+130h+var_F0+7]
0x1400dc0d3  not     al
  ... truncated ...
```
