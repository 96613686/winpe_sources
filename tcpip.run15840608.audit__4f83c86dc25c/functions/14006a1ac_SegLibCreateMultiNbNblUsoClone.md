# SegLibCreateMultiNbNblUsoClone

- ea: `0x14006a1ac`
- end: `0x14006ad9c`
- name: `SegLibCreateMultiNbNblUsoClone`
- size: `3056`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, int, int, int, ULONG, __int64, __int64)`
- caller_count: `3`
- callee_count: `12`
- tags: `authz_impersonation, installer_update`

## callers

- `0x14006ba00`
- `0x14012f1d0`
- `0x1401ad764`

## callees

- `0x1400671fc`
- `0x140069200`
- `0x1400696bc`
- `0x14006a1ac`
- `0x14006ada4`
- `0x14006b80c`
- `0x14006b958`
- `0x1401c0f82`
- `0x1401c0fd0`
- `0x1401c1200`
- `0x1401c1280`
- `0x1401c1580`

## import_xrefs

- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14006a2ff`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14006a2ff`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14006ab37`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1401ca40c`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1401ca515`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14006ab37`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1401ca40c`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1401ca515`
- `NDIS!NdisCopyReceiveNetBufferListInfo` at `0x14006a8e1`
- `NDIS!NdisCopyReceiveNetBufferListInfo` at `0x14006a8e1`
- `NDIS!NdisCopySendNetBufferListInfo` at `0x14006a66e`
- `NDIS!NdisCopySendNetBufferListInfo` at `0x14006a911`
- `NDIS!NdisCopySendNetBufferListInfo` at `0x14006a66e`
- `NDIS!NdisCopySendNetBufferListInfo` at `0x14006a911`
- `NDIS!NdisAllocateFragmentNetBufferList` at `0x14006a3ee`
- `NDIS!NdisAllocateFragmentNetBufferList` at `0x14006a3ee`
- `NDIS!NdisFreeNetBufferListContext` at `0x14006ad8a`
- `NDIS!NdisFreeNetBufferListContext` at `0x14006ad8a`
- `NDIS!NdisFreeFragmentNetBufferList` at `0x1401ca63c`
- `NDIS!NdisFreeFragmentNetBufferList` at `0x1401ca63c`
- `NDIS!NdisAdvanceNetBufferListDataStart` at `0x14006a412`
- `NDIS!NdisAdvanceNetBufferListDataStart` at `0x14006a412`
- `NDIS!NdisGetDataBuffer` at `0x14006a49a`
- `NDIS!NdisGetDataBuffer` at `0x1401ca178`
- `NDIS!NdisGetDataBuffer` at `0x1401ca1c0`
- `NDIS!NdisGetDataBuffer` at `0x14006a49a`
- `NDIS!NdisGetDataBuffer` at `0x1401ca178`
- `NDIS!NdisGetDataBuffer` at `0x1401ca1c0`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x1401ca155`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x1401ca19d`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x1401ca20f`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x1401ca228`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x1401ca26f`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x1401ca289`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x1401ca155`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x1401ca19d`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x1401ca20f`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x1401ca228`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x1401ca26f`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x1401ca289`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x1401ca1dc`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x1401ca2d1`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x1401ca2eb`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x1401ca620`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x1401ca1dc`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x1401ca2d1`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x1401ca2eb`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x1401ca620`

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
0x14006a1ac  push    rbp
0x14006a1ae  push    rsi
0x14006a1af  push    rdi
0x14006a1b0  push    r12
0x14006a1b2  push    r13
0x14006a1b4  push    r14
0x14006a1b6  push    r15
0x14006a1b8  sub     rsp, 140h
0x14006a1bf  lea     rbp, [rsp+40h]
0x14006a1c4  mov     [rbp+130h+arg_0], rbx
0x14006a1cb  mov     rax, cs:__security_cookie
0x14006a1d2  xor     rax, rbp
0x14006a1d5  mov     [rbp+130h+var_40], rax
0x14006a1dc  mov     rax, [rbp+130h+arg_48]
0x14006a1e3  mov     rsi, rdx
0x14006a1e6  mov     r13d, [rbp+130h+arg_40]
0x14006a1ed  mov     rdi, rcx
0x14006a1f0  mov     [rbp+130h+var_B8], rax
0x14006a1f4  lea     rcx, [rbp+130h+var_A0]; void *
0x14006a1fb  mov     rax, [rbp+130h+arg_50]
0x14006a202  xorps   xmm0, xmm0
0x14006a205  mov     [rbp+130h+var_B0], rax
0x14006a20c  xor     eax, eax
0x14006a20e  mov     qword ptr [rbp+130h+Size+4], rdx
0x14006a212  xor     edx, edx; Val
0x14006a214  mov     [rbp+130h+var_12A], r9b
0x14006a218  movups  xmmword ptr [rbp+130h+var_100], xmm0
0x14006a21c  lea     r8d, [rax+60h]; Size
0x14006a220  mov     [rbp+130h+var_F0], rax
0x14006a224  call    memset
0x14006a229  mov     rcx, [rbp+130h+arg_20]
0x14006a230  xor     r9d, r9d
0x14006a233  mov     [rbp+130h+var_118], r9d
0x14006a237  mov     ebx, r9d
0x14006a23a  mov     byte ptr [rbp+130h+var_E0], r9b
0x14006a23e  mov     r15d, r9d
0x14006a241  mov     [rbp+130h+var_12F], r9b
0x14006a245  mov     r11d, 0FFFFFFFFh
0x14006a24b  lea     r10d, [r9+1]
0x14006a24f  lea     r14d, [r9+8]
0x14006a253  mov     r12b, r10b
0x14006a256  test    rcx, rcx
0x14006a259  jz      loc_14006AA85
0x14006a25f  mov     eax, [rcx+1Ch]
0x14006a262  movzx   r8d, word ptr [rcx]
0x14006a266  sub     eax, r10d
0x14006a269  test    eax, 0FFFFFFFDh
0x14006a26e  movzx   edx, r8w
0x14006a272  setz    al
0x14006a275  mov     [rbp+130h+var_12B], al
0x14006a278  and     dx, r14w
0x14006a27c  jnz     loc_14006AA2C
0x14006a282  test    al, al
0x14006a284  jnz     short loc_14006A2AD
0x14006a286  mov     rax, [rsi+140h]
0x14006a28d  and     rax, r11
0x14006a290  jz      loc_14006AA3E
0x14006a296  mov     [rbp+130h+var_12F], r10b
0x14006a29a  test    r8b, 2
0x14006a29e  jnz     loc_14006AA4C
0x14006a2a4  test    rax, rax
0x14006a2a7  jz      loc_14006AA6D
0x14006a2ad  mov     rdi, [rdi+8]
0x14006a2b1  mov     esi, 4
0x14006a2b6  test    rdi, rdi
0x14006a2b9  jz      short loc_14006A2C5
0x14006a2bb  cmp     [rdi+30h], r9b
0x14006a2bf  jnz     loc_14006AA8E
0x14006a2c5  mov     eax, esi
0x14006a2c7  lea     rcx, [rax+rax*2]
0x14006a2cb  shl     rcx, 3
0x14006a2cf  lea     rax, [rcx+0Fh]
0x14006a2d3  cmp     rax, rcx
0x14006a2d6  ja      short loc_14006A2E2
0x14006a2d8  mov     rax, 0FFFFFFFFFFFFFF0h
0x14006a2e2  and     rax, 0FFFFFFFFFFFFFFF0h
0x14006a2e6  call    __chkstk_0
0x14006a2eb  sub     rsp, rax
0x14006a2ee  mov     [rbp+130h+var_A0], 0F00DF00Dh
0x14006a2f8  xor     ecx, ecx; ProcNumber
0x14006a2fa  lea     r14, [rsp+170h+var_130]
0x14006a2ff  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14006a306  nop     dword ptr [rax+rax+00h]
0x14006a30b  xor     edx, edx
0x14006a30d  mov     [rbp+130h+var_94], eax
0x14006a313  mov     [rbp+130h+var_98], edx
0x14006a319  mov     [rbp+130h+var_9C], dl
0x14006a31f  mov     [rbp+130h+var_88], rdx
0x14006a326  mov     rax, [rdi+20h]
0x14006a32a  neg     rax
0x14006a32d  mov     [rbp+130h+var_90], 1
0x14006a338  lea     rax, [rbp+130h+var_68]
0x14006a33f  mov     [rbp+130h+var_70], rdx
0x14006a346  sbb     ecx, ecx
0x14006a348  mov     [rbp+130h+var_74], edx
0x14006a34e  and     ecx, 4
0x14006a351  mov     [rbp+130h+var_78], dl
0x14006a357  mov     [rbp+130h+var_98], ecx
0x14006a35d  mov     [rbp+130h+var_68], rdx
0x14006a364  mov     [rbp+130h+var_60], edx
0x14006a36a  mov     [rbp+130h+var_80], rax
0x14006a371  test    r14, r14
0x14006a374  jz      loc_14006A8CF
0x14006a37a  mov     [rbp+130h+var_5C], esi
0x14006a380  mov     [rbp+130h+var_58], r14
0x14006a387  mov     [rbp+130h+var_50], rdi
0x14006a38e  mov     r8b, [rbp+130h+var_12A]
0x14006a392  lea     rcx, [rbp+130h+var_100]
0x14006a396  mov     [rsp+170h+DataBackFill], r12b
0x14006a39b  mov     rsi, rdx
0x14006a39e  mov     r12, qword ptr [rbp+130h+Size+4]
0x14006a3a2  mov     dil, dl
0x14006a3a5  mov     rdx, r12
0x14006a3a8  mov     word ptr [rsp+170h+DataOffsetDelta], r15w
0x14006a3ae  mov     qword ptr [rsp+170h+MaximumLength], rbx
0x14006a3b3  call    SegLibPvtUsoInitialize
0x14006a3b8  xor     r15d, r15d
0x14006a3bb  mov     ebx, eax
0x14006a3bd  test    eax, eax
0x14006a3bf  js      loc_14006AD5F
0x14006a3c5  movzx   r14d, word ptr [rbp+130h+var_F0+2]
0x14006a3ca  xor     r8d, r8d; NetBufferPool
0x14006a3cd  mov     [rsp+170h+AllocateFragmentFlags], r15d; AllocateFragmentFlags
0x14006a3d2  mov     r9d, r14d; StartOffset
0x14006a3d5  mov     dword ptr [rsp+170h+DataBackFill], r15d; DataBackFill
0x14006a3da  xor     edx, edx; NetBufferListPool
0x14006a3dc  mov     rcx, r12; OriginalNetBufferList
0x14006a3df  lea     eax, [r14+r13]
0x14006a3e3  mov     [rsp+170h+DataOffsetDelta], eax; DataOffsetDelta
0x14006a3e7  mov     eax, [rbp+130h+var_100]
0x14006a3ea  mov     [rsp+170h+MaximumLength], eax; MaximumLength
0x14006a3ee  call    cs:__imp_NdisAllocateFragmentNetBufferList
0x14006a3f5  nop     dword ptr [rax+rax+00h]
0x14006a3fa  mov     rsi, rax
0x14006a3fd  test    rax, rax
0x14006a400  jz      loc_14006AA96
0x14006a406  xor     r9d, r9d; FreeMdlMdlHandler
0x14006a409  xor     r8d, r8d; FreeMdl
0x14006a40c  mov     edx, r13d; DataOffsetDelta
0x14006a40f  mov     rcx, rax; NetBufferList
0x14006a412  call    cs:__imp_NdisAdvanceNetBufferListDataStart
0x14006a419  nop     dword ptr [rax+rax+00h]
0x14006a41e  mov     rbx, [rbp+130h+var_F0]
0x14006a422  movzx   eax, r14w
0x14006a426  movzx   edi, byte ptr [rbp+130h+var_F0+6]
0x14006a42a  movzx   ecx, bx
0x14006a42d  mov     r13, [rsi+8]
0x14006a431  sub     cx, di
0x14006a434  sub     ax, bx
0x14006a437  mov     [rbp+130h+var_128], cx
0x14006a43b  movzx   eax, ax
0x14006a43e  movzx   ecx, r14w
0x14006a442  mov     dword ptr [rbp+130h+Size], eax
0x14006a445  movzx   eax, bx
0x14006a448  mov     qword ptr [rbp+130h+Size+4], rbx
0x14006a44c  lea     ebx, [r15+1]
0x14006a450  mov     [rbp+130h+var_DC], eax
0x14006a453  mov     [rbp+130h+var_12E], r15b
0x14006a457  mov     [rbp+130h+var_130], 1
0x14006a45b  mov     [rbp+130h+var_C8], r15
0x14006a45f  mov     [rbp+130h+Src], r15
0x14006a463  mov     [rbp+130h+var_D0], r15
0x14006a467  mov     [rbp+130h+var_12D], r15b
0x14006a46b  mov     [rbp+130h+var_D8], r15d
0x14006a46f  mov     [rbp+130h+var_E4], r15d
0x14006a473  mov     [rbp+130h+var_12C], dil
0x14006a477  mov     [rbp+130h+var_E8], cx
0x14006a47b  test    r13, r13
0x14006a47e  jz      loc_14006A64E
0x14006a484  movzx   ebx, cx
0x14006a487  mov     r9d, 1; AlignMultiple
0x14006a48d  mov     edx, ebx; BytesNeeded
0x14006a48f  mov     [rsp+170h+MaximumLength], r15d; AlignOffset
0x14006a494  xor     r8d, r8d; Storage
0x14006a497  mov     rcx, r13; NetBuffer
0x14006a49a  call    cs:__imp_NdisGetDataBuffer
0x14006a4a1  nop     dword ptr [rax+rax+00h]
0x14006a4a6  movzx   r14d, [rbp+130h+var_128]
0x14006a4ab  xor     r9d, r9d; FreeMdlHandler
0x14006a4ae  movzx   edi, dil
0x14006a4b2  mov     r15, rax
0x14006a4b5  test    rax, rax
0x14006a4b8  jz      loc_1401CA14D
0x14006a4be  movzx   eax, [rbp+130h+var_12C]
0x14006a4c2  lea     r10d, [r9+1]
0x14006a4c6  add     rax, r15
0x14006a4c9  mov     [rbp+130h+var_110], rax
0x14006a4cd  movzx   eax, word ptr [rbp+130h+Size+4]
0x14006a4d1  add     rax, r15
0x14006a4d4  mov     [rbp+130h+var_108], rax
0x14006a4d8  mov     al, [rbp+130h+var_12E]
0x14006a4db  cmp     [rbp+130h+var_D0], r9
0x14006a4df  jz      loc_14006A75C
0x14006a4e5  cmp     [rbp+130h+var_12D], r9b
0x14006a4e9  jnz     short loc_14006A4F3
0x14006a4eb  test    al, al
0x14006a4ed  jz      loc_14006A84B
0x14006a4f3  mov     r8, [rbp+130h+var_50]
0x14006a4fa  mov     r15d, 1
0x14006a500  mov     edi, 0FFFFFFFFh
0x14006a505  cmp     [r8+1], r15b
0x14006a509  jz      loc_14006AB89
0x14006a50f  mov     eax, [r8+4]
0x14006a513  test    eax, eax
0x14006a515  jz      loc_14006A964
0x14006a51b  mov     rdx, [rbp+130h+var_80]
0x14006a522  mov     ebx, [rdx+8]
0x14006a525  cmp     ebx, [rdx+0Ch]
0x14006a528  jnb     loc_14006A6FF
0x14006a52e  add     dword ptr [rbp+130h+var_90+4], r15d
0x14006a535  add     [rdx+8], r15d
0x14006a539  mov     r8, [rbp+130h+var_50]
0x14006a540  cmp     [r8+1], r15b
0x14006a544  jz      loc_14006AC1D
0x14006a54a  mov     eax, ebx
0x14006a54c  lea     rcx, [rax+rax*2]
0x14006a550  mov     rax, [rdx+10h]
0x14006a554  mov     rdi, [rbp+130h+var_110]
0x14006a558  mov     rdx, [rbp+130h+Src]
0x14006a55c  shl     r14d, 4
0x14006a560  or      r14d, r15d
0x14006a563  mov     [rax+rcx*8], rdi
0x14006a567  mov     [rax+rcx*8+10h], r14d
0x14006a56c  mov     [rax+rcx*8+8], rdx
0x14006a571  mov     rcx, [rbp+130h+var_50]
0x14006a578  xor     r14d, r14d
0x14006a57b  cmp     [rcx+1], r15b
0x14006a57f  jz      loc_14006AC4C
0x14006a585  mov     eax, [rcx+4]
0x14006a588  test    eax, eax
0x14006a58a  jz      loc_14006A9AA
0x14006a590  mov     r8, [rbp+130h+var_80]
0x14006a597  mov     ebx, [r8+8]
0x14006a59b  cmp     ebx, [r8+0Ch]
0x14006a59f  jnb     loc_14006A72F
0x14006a5a5  mov     r9d, 0FFFFFFFFh
0x14006a5ab  add     dword ptr [rbp+130h+var_90+4], r15d
0x14006a5b2  add     [r8+8], r15d
0x14006a5b6  mov     rdx, [rbp+130h+var_50]
0x14006a5bd  cmp     [rdx+1], r15b
0x14006a5c1  jz      loc_14006ACE1
0x14006a5c7  mov     rcx, [r8+10h]
0x14006a5cb  mov     eax, ebx
0x14006a5cd  lea     rdx, [rax+rax*2]
0x14006a5d1  mov     rax, [rbp+130h+var_108]
0x14006a5d5  mov     [rcx+rdx*8], rax
0x14006a5d9  mov     rax, [rbp+130h+var_D0]
0x14006a5dd  mov     [rcx+rdx*8+8], rax
0x14006a5e2  mov     eax, dword ptr [rbp+130h+Size]
0x14006a5e5  shl     eax, 4
0x14006a5e8  or      eax, r15d
0x14006a5eb  mov     [rcx+rdx*8+10h], eax
0x14006a5ef  movzx   r14d, word ptr [rbp+130h+var_F0+2]
0x14006a5f4  mov     eax, [rbp+130h+var_E4]
0x14006a5f7  lea     rdx, [rbp+130h+var_100]
0x14006a5fb  mov     r15d, [rbp+130h+var_D8]
0x14006a5ff  lea     rcx, [rbp+130h+var_A0]
0x14006a606  mov     r9, [rbp+130h+var_108]
0x14006a60a  mov     r8, rdi
0x14006a60d  mov     [rsp+170h+DataOffsetDelta], eax
0x14006a611  mov     [rsp+170h+MaximumLength], r15d
0x14006a616  call    SegLibPvtUsoDeferredFixHeaders
0x14006a61b  mov     ebx, eax
0x14006a61d  test    eax, eax
0x14006a61f  js      loc_14006A7FC
0x14006a625  mov     edx, [rbp+130h+var_E4]
0x14006a628  mov     ebx, 1
0x14006a62d  add     edx, [rbp+130h+var_100]
0x14006a630  add     r15d, ebx
0x14006a633  mov     r13, [r13+0]
0x14006a637  mov     dil, [rbp+130h+var_12C]
0x14006a63b  movzx   ecx, [rbp+130h+var_E8]
0x14006a63f  mov     [rbp+130h+var_D8], r15d
0x14006a643  xor     r15d, r15d
0x14006a646  mov     [rbp+130h+var_E4], edx
0x14006a649  jmp     loc_14006A47B
0x14006a64e  mov     dil, [rbp+130h+var_12B]
0x14006a652  mov     rdx, r12; SrcNetBufferList
0x14006a655  mov     rcx, rsi; DestNetBufferList
0x14006a658  cmp     dil, bl
0x14006a65b  jz      loc_14006A8E1
0x14006a661  cmp     cs:NetioCopyNetBufferListQosInformationFnPtr, r15
0x14006a668  jnz     loc_14006A901
0x14006a66e  call    cs:__imp_NdisCopySendNetBufferListInfo
0x14006a675  nop     dword ptr [rax+rax+00h]
0x14006a67a  mov     [rsi+140h], r15
0x14006a681  cmp     [rbp+130h+var_12F], bl
0x14006a684  jnz     loc_14006A7D8
0x14006a68a  mov     edx, [rbp+130h+var_118]
0x14006a68d  test    dx, dx
0x14006a690  mov     rdi, [rsi+8]
0x14006a694  cmovz   dx, word ptr [rbp+130h+Size+4]
0x14006a699  xor     r13d, r13d
0x14006a69c  mov     r15d, [rbp+130h+var_E0]
0x14006a6a0  mov     [rbp+130h+var_118], edx
0x14006a6a3  test    rdi, rdi
0x14006a6a6  jz      loc_14006A8F2
0x14006a6ac  mov     al, byte ptr [rbp+130h+var_F0+7]
0x14006a6af  movzx   ecx, byte ptr [rbp+130h+var_F0+7]
0x14006a6b3  not     al
  ... truncated ...
```
