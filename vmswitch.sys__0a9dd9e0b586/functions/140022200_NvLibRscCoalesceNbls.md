# NvLibRscCoalesceNbls

- ea: `0x140022200`
- end: `0x140022fe3`
- name: `NvLibRscCoalesceNbls`
- size: `3555`
- prototype: ``
- caller_count: `2`
- callee_count: `15`
- tags: `authz_impersonation`

## callers

- `0x140026000`
- `0x1400327e0`

## callees

- `0x1400208d4`
- `0x140021cb0`
- `0x140022200`
- `0x140023e64`
- `0x140024100`
- `0x1400243c0`
- `0x140024428`
- `0x1400244ec`
- `0x1400245e0`
- `0x140024734`
- `0x1401bbcb0`
- `0x1401bbd20`
- `0x1401bbe80`
- `0x1401bbf20`
- `0x1401bc340`

## import_xrefs

- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400225af`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140022684`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140022b2a`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400225af`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140022684`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140022b2a`
- `NDIS!NdisGetDataBuffer` at `0x140022376`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x140022d39`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x140022d53`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x140022ea1`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x140022f8b`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x140022d39`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x140022d53`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x140022ea1`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x140022f8b`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x140022d70`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x140022d70`

## pseudocode

```c
char __fastcall NvLibRscCoalesceNbls(
        __int64 *a1,
        __int64 a2,
        const __m128i **a3,
        unsigned __int16 a4,
        char a5,
        char a6,
        __int64 a7)
{
  unsigned __int16 *v7; // rbp
  unsigned __int16 v8; // bx
  const __m128i **v9; // r12
  __int64 *v10; // r13
  int v11; // r15d
  _QWORD *v12; // r14
  __int64 v13; // rsi
  bool v14; // zf
  int v15; // r12d
  char v16; // r13
  int v17; // r8d
  int v18; // r9d
  __int64 v19; // rcx
  struct _NET_BUFFER *v20; // rbx
  unsigned int DataLength; // esi
  unsigned int v22; // eax
  int v23; // edi
  ULONG v24; // r14d
  __int64 v25; // rax
  __int16 v26; // ax
  unsigned int v27; // ecx
  int v28; // eax
  unsigned int v29; // esi
  int v30; // eax
  unsigned int CurrentMdlOffset; // eax
  __int16 v32; // ax
  __int64 v33; // r8
  char v34; // bl
  __int64 v35; // rdx
  __m128i *v36; // rbx
  __m128i *v37; // rdi
  __int64 v38; // rax
  __int64 v39; // rcx
  __m128i *v40; // rbx
  const __m128i *v41; // rsi
  __m128i *v42; // rdi
  __int64 v43; // rax
  __int64 v44; // rcx
  const __m128i *v45; // rcx
  __int64 v46; // rax
  __int64 v47; // rdx
  __int64 v48; // rax
  unsigned int v50; // eax
  __int64 v51; // r13
  char IsNBLFitForCoalescing; // al
  const __m128i *v53; // rbx
  const __m128i *v54; // rdi
  int v55; // r14d
  char v56; // r12
  char v57; // cl
  unsigned __int8 v58; // al
  unsigned __int16 *v59; // rdx
  __int64 v60; // rax
  __int64 *v61; // r14
  __int64 v62; // rcx
  const __m128i *v63; // rax
  _QWORD *v64; // r14
  __m128i *v65; // rbx
  __m128i *v66; // rdi
  __int64 v67; // rax
  __int64 v68; // rcx
  _BYTE *v69; // rax
  __int64 v70; // rax
  __int16 v71; // ax
  unsigned int v72; // ecx
  __int64 v73; // rax
  __int64 v74; // rax
  __int16 v75; // ax
  unsigned int v76; // ecx
  unsigned int BucketIndex; // eax
  unsigned __int64 v78; // rax
  int v79; // eax
  unsigned int v80; // eax
  unsigned int v81; // eax
  __int16 v82; // ax
  unsigned int v83; // ecx
  _WORD v84[2]; // [rsp+90h] [rbp+0h] BYREF

  v7 = (unsigned __int16 *)((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL);
  v8 = a4;
  v9 = a3;
  *((_QWORD *)v7 + 3) = a3;
  *((_QWORD *)v7 + 24) = a2;
  v10 = a1;
  *((_QWORD *)v7 + 25) = a1;
  v7[8] = a4;
  *((_QWORD *)v7 + 28) = a7;
  *((_QWORD *)v7 + 26) = 0;
  memset((void *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 240), 0, 0x40u);
  memset((void *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 320), 0, 0x80u);
  if ( !byte_1401F96A0 || !a5 && !a6 )
    return 0;
  v11 = 0;
  v12 = v7 + 104;
  v9[1] = 0;
  v13 = *v10;
  *(_QWORD *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 8) = ((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL)
                                                                   + 208;
  *(_QWORD *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 0x20) = v13;
  if ( !v13 )
    goto LABEL_43;
  do
  {
    v14 = *(_WORD *)(v13 + 320) == 0;
    *(_QWORD *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 0xD8) = *(_QWORD *)v13;
    if ( !v14 )
      goto LABEL_30;
    ++*(_QWORD *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 0x140);
    LOBYTE(v15) = 14;
    *(_QWORD *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 0x28) = 0;
    v16 = 0;
    *(_DWORD *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 4) = 14;
    *(_BYTE *)v7 = 0;
    *(_DWORD *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 0x2C) = 326;
    memset(v7 + 24, 0, 0x88u);
    v19 = *(_QWORD *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 0x20);
    *(_WORD *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 0xA0) = v8;
    v20 = *(struct _NET_BUFFER **)(v13 + 8);
    *(_QWORD *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 0xB0) = ((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL)
                                                                        + 256;
    DataLength = v20->DataLength;
    if ( v19 != -296 )
    {
      v22 = *(_DWORD *)(v19 + 300);
      if ( (v22 & 0x400) == 0 )
      {
        v50 = (v22 >> 11) & 0xFFF;
        if ( v50 )
        {
          if ( v50 < DataLength )
            DataLength = v50;
        }
      }
    }
    v23 = 0;
    *(_QWORD *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 0x1F8) = 0;
    v24 = 0;
    if ( DataLength < 0xE )
    {
      v23 = -1073676266;
      goto LABEL_18;
    }
    v25 = ((__int64 (__fastcall *)(struct _NET_BUFFER *, __int64, _QWORD, __int64, _DWORD))NdisGetDataBuffer)(
            v20,
            14,
            0,
            1,
            0);
    if ( !v25 )
    {
      v23 = -1073741670;
      goto LABEL_17;
    }
    *(_QWORD *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 0x30) = v20;
    v24 = 14;
    *(_DWORD *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 0x44) = v20->DataLength;
    *(_QWORD *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 0x38) = v25;
    *(_DWORD *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 0x48) = DataLength;
    v26 = *(_WORD *)(v25 + 12);
    *(_DWORD *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 0xA4) += 14;
    *(_DWORD *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 0xA8) += 14;
    *(_WORD *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 0x42) = __ROR2__(v26, 8);
    v27 = v20->CurrentMdlOffset + 14;
    if ( v27 >= *(_DWORD *)(v20->Link.Region + 40) )
    {
      NdisAdvanceNetBufferDataStart(v20, 0xEu, 0, 0);
    }
    else
    {
      v20->DataOffset += 14;
      v20->DataLength -= 14;
      v20->CurrentMdlOffset = v27;
    }
    v28 = *(unsigned __int16 *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 0x42);
    if ( (unsigned __int16)v28 <= 0x600u )
    {
      if ( (unsigned __int16)(v28 - 2) > 0x5DAu )
        goto LABEL_142;
      if ( DataLength < 0x10 )
      {
        v23 = -1073676266;
        goto LABEL_17;
      }
      v69 = (_BYTE *)((__int64 (__fastcall *)(struct _NET_BUFFER *, __int64, unsigned __int16 *, __int64, _DWORD))NdisGetDataBuffer)(
                       v20,
                       2,
                       v7 + 252,
                       1,
                       0);
      if ( !v69 )
      {
        v23 = -1073741670;
        goto LABEL_17;
      }
      if ( *v69 != 0xAA || v69[1] != 0xAA )
        goto LABEL_17;
      if ( DataLength < 0x16 )
      {
        v23 = -1073676266;
        goto LABEL_17;
      }
      v70 = ((__int64 (__fastcall *)(struct _NET_BUFFER *, __int64, unsigned __int16 *, __int64, _DWORD))NdisGetDataBuffer)(
              v20,
              8,
              v7 + 252,
              1,
              0);
      if ( !v70 )
      {
        v23 = -1073741670;
        goto LABEL_17;
      }
      if ( *(_BYTE *)(v70 + 2) != 3 )
        goto LABEL_17;
      v71 = *(_WORD *)(v70 + 6);
      v24 = 22;
      *(_DWORD *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 0xA8) += 8;
      *(_WORD *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 0x42) = __ROR2__(v71, 8);
      v72 = v20->CurrentMdlOffset + 8;
      if ( v72 >= *(_DWORD *)(v20->Link.Region + 40) )
      {
        NdisAdvanceNetBufferDataStart(v20, 8u, 0, 0);
      }
      else
      {
        v20->DataOffset += 8;
        v20->DataLength -= 8;
        v20->CurrentMdlOffset = v72;
      }
      LOWORD(v28) = *(_WORD *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 0x42);
      if ( (_WORD)v28 != 0x8100 )
        goto LABEL_14;
      if ( DataLength < 0x1A )
      {
        v23 = -1073676266;
        goto LABEL_17;
      }
      v73 = ((__int64 (__fastcall *)(struct _NET_BUFFER *, __int64, _QWORD, __int64, _DWORD))NdisGetDataBuffer)(
              v20,
              4,
              0,
              1,
              0);
      if ( !v73 )
      {
        v23 = -1073741670;
        goto LABEL_17;
      }
      v24 = 26;
      goto LABEL_157;
    }
    if ( v28 == 33024 )
    {
      if ( DataLength < 0x12 )
      {
        v23 = -1073676266;
        goto LABEL_17;
      }
      v73 = ((__int64 (__fastcall *)(struct _NET_BUFFER *, __int64, _QWORD, __int64, _DWORD))NdisGetDataBuffer)(
              v20,
              4,
              0,
              1,
              0);
      if ( !v73 )
      {
        v23 = -1073741670;
        goto LABEL_17;
      }
      v24 = 18;
      goto LABEL_157;
    }
    if ( v28 == 34984 )
    {
      if ( DataLength < 0x16 )
      {
        v23 = -1073676266;
        goto LABEL_17;
      }
      v74 = ((__int64 (__fastcall *)(struct _NET_BUFFER *, __int64, _QWORD, __int64, _DWORD))NdisGetDataBuffer)(
              v20,
              4,
              0,
              1,
              0);
      if ( !v74 )
      {
        v23 = -1073741670;
        goto LABEL_17;
      }
      v75 = *(_WORD *)(v74 + 2);
      v24 = 18;
      *(_DWORD *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 0xA8) += 4;
      *(_WORD *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 0x42) = __ROR2__(v75, 8);
      v76 = v20->CurrentMdlOffset + 4;
      if ( v76 < *(_DWORD *)(v20->Link.Region + 40) )
      {
        v20->DataOffset += 4;
        v20->DataLength -= 4;
        v20->CurrentMdlOffset = v76;
      }
      else
      {
        NdisAdvanceNetBufferDataStart(v20, 4u, 0, 0);
      }
      *(_DWORD *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 0xA4) += 4;
      if ( *(_WORD *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 0x42) != 0x8100 )
      {
LABEL_142:
        v23 = -1073676267;
        goto LABEL_17;
      }
      v73 = ((__int64 (__fastcall *)(struct _NET_BUFFER *, __int64, _QWORD, __int64, _DWORD))NdisGetDataBuffer)(
              v20,
              4,
              0,
              1,
              0);
      if ( !v73 )
      {
        v23 = -1073741670;
        goto LABEL_17;
      }
      v24 = 22;
LABEL_157:
      v82 = *(_WORD *)(v73 + 2);
      *(_DWORD *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 0xA8) += 4;
      *(_WORD *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 0x42) = __ROR2__(v82, 8);
      v83 = v20->CurrentMdlOffset + 4;
      if ( v83 >= *(_DWORD *)(v20->Link.Region + 40) )
      {
        NdisAdvanceNetBufferDataStart(v20, 4u, 0, 0);
      }
      else
      {
        v20->DataOffset += 4;
        v20->DataLength -= 4;
        v20->CurrentMdlOffset = v83;
      }
      LOWORD(v28) = *(_WORD *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 0x42);
      *(_DWORD *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 0xA4) += 4;
    }
LABEL_14:
    v29 = DataLength - v24;
    *(_BYTE *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 0x40) = v24;
    if ( (unsigned __int16)v28 == 2048 )
    {
      v30 = VmsPktParseIPv4Packet(
              (_DWORD)v20,
              v29,
              *(_QWORD *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 0x28),
              (int)v7 + 48,
              (__int64)NdisGetDataBuffer,
              (__int64)VmsPktAdvanceNetBuffer,
              (__int64)VmsPktRetreatNetBuffer,
              (__int64)VmsPktPvtGetLengthNetBuffer,
              1);
LABEL_16:
      v23 = v30;
LABEL_17:
      v15 = *(_DWORD *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 4);
      goto LABEL_18;
    }
    if ( (unsigned __int16)v28 != 2054 )
    {
      if ( (unsigned __int16)v28 != 34525 )
        goto LABEL_17;
      v30 = VmsPktParseIPv6Packet(
              (_DWORD)v20,
              v29,
              *(_QWORD *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 0x28),
              (int)v7 + 48,
              (__int64)NdisGetDataBuffer,
              (__int64)VmsPktAdvanceNetBuffer,
              (__int64)VmsPktRetreatNetBuffer,
              (__int64)VmsPktPvtGetLengthNetBuffer,
              1);
      goto LABEL_16;
    }
    v15 = *(_DWORD *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 4);
    v23 = 0;
LABEL_18:
    *(_DWORD *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 0xA8) -= v24;
    CurrentMdlOffset = v20->CurrentMdlOffset;
    if ( CurrentMdlOffset < v24 )
    {
      NdisRetreatNetBufferDataStart(v20, v24, 0, 0);
    }
    else
    {
      v20->DataOffset -= v24;
      v20->DataLength += v24;
      v20->CurrentMdlOffset = CurrentMdlOffset - v24;
    }
    if ( v23 < 0 )
    {
LABEL_71:
      v34 = 0;
      goto LABEL_25;
    }
    v32 = *(_WORD *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 0x42);
    if ( v32 == 2048 )
    {
      if ( *(_BYTE *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 0x6C) != 6 )
        goto LABEL_71;
      v16 = 1;
      tcpxsum(0, *(_QWORD *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 0x60) + 12LL, 4);
      v33 = 4;
      v34 = *(_BYTE *)v7;
      v35 = *(_QWORD *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 0x60) + 16LL;
    }
    else
    {
      if ( v32 != -31011 || *(_BYTE *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 0x70) != 6 )
        goto LABEL_71;
      v34 = 1;
      tcpxsum(0, *(_QWORD *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 0x60) + 8LL, 16);
      v33 = 16;
      v35 = *(_QWORD *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 0x60) + 24LL;
    }
    tcpxsum(0, v35, v33);
    v15 = *(_DWORD *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 0xA4);
    *(_BYTE *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 0xF1) = *(_BYTE *)(((unsigned __int64)v84
                                                                                   & 0xFFFFFFFFFFFFFFC0uLL)
                                                                                  + 0xAC);
LABEL_25:
    *(_BYTE *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 0xF2) = v15;
    *(_BYTE *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 0xF0) = 0;
    if ( (!a5 || !v16) && (!a6 || !v34) )
    {
      v9 = *(const __m128i ***)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 0x18);
      v13 = *(_QWORD *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 0x20);
      v12 = *(_QWORD **)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 8);
LABEL_30:
      v36 = (__m128i *)v9[1];
      if ( v36 )
      {
        do
        {
          v37 = (__m128i *)v36[7].m128i_i64[1];
          *v7 = 0;
          *(_DWORD *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 4) = 0;
          if ( v36[3].m128i_i8[8] )
          {
            v38 = RscLibExFlushScu(v36, v36[4].m128i_i64[0], (unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL, v7 + 2);
            if ( v38 )
            {
              v39 = *v7;
              ++v11;
              *v12 = v38;
              v12 = (_QWORD *)v38;
              if ( (unsigned int)v39 > 1 )
              {
                *(_QWORD *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 0x150) += *(unsigned int *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 4);
                *(_QWORD *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 0x148) += v39;
                ++*(_QWORD *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 0x158);
                BucketIndex = NvLibRscPvtStatsGetBucketIndex();
                ++*(_QWORD *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 0x160 + 8LL * BucketIndex);
              }
            }
            v36[3].m128i_i8[8] = 0;
            v36[3].m128i_i32[3] = 0;
          }
          if ( byte_1401F96A0 == 1 )
            ExFreeToLookasideListEx(&g_NvLibContext, v36);
          v36 = v37;
        }
        while ( v37 );
      }
      v9[1] = 0;
      *v12 = v13;
      *(_QWORD *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 8) = v13;
      goto LABEL_40;
    }
    v51 = *(_QWORD *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 0x20);
    *(_QWORD *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 0x1F0) = 0;
    *(_BYTE *)v7 = 0;
    *(_QWORD *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 0x1F8) = 0;
    *(_OWORD *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 0x1C0) = 0;
    *(_OWORD *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 0x1D0) = 0;
    *(_OWORD *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 0x1E0) = 0;
    IsNBLFitForCoalescing = RscLibExIsNBLFitForCoalescing(
                              v51,
                              (unsigned __int8)v15,
                              v17,
                              v18,
                              (__int64)(v7 + 224),
                              (unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL,
                              (__int64)(v7 + 122));
    v9 = *(const __m128i ***)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 0x18);
    if ( !IsNBLFitForCoalescing )
    {
      v64 = *(_QWORD **)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 8);
      if ( !*(_BYTE *)v7 )
      {
        v65 = (__m128i *)v9[1];
        if ( v65 )
        {
          do
          {
            v14 = v65[3].m128i_i8[8] == 0;
            v66 = (__m128i *)v65[7].m128i_i64[1];
            *v7 = 0;
            *(_DWORD *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 4) = 0;
            if ( !v14 )
            {
              v67 = RscLibExFlushScu(v65, v65[4].m128i_i64[0], (unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL, v7 + 2);
              if ( v67 )
              {
                v68 = *v7;
                ++v11;
                *v64 = v67;
                v64 = (_QWORD *)v67;
                if ( (unsigned int)v68 > 1 )
                {
                  *(_QWORD *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 0x150) += *(unsigned int *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 4);
                  *(_QWORD *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 0x148) += v68;
                  ++*(_QWORD *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 0x158);
                  v80 = NvLibRscPvtStatsGetBucketIndex();
                  ++*(_QWORD *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 0x160 + 8LL * v80);
                }
              }
              v65[3].m128i_i8[8] = 0;
              v65[3].m128i_i32[3] = 0;
            }
            if ( byte_1401F96A0 == 1 )
              ExFreeToLookasideListEx(&g_NvLibContext, v65);
            v65 = v66;
          }
          while ( v66 );
        }
        v9[1] = 0;
      }
      goto LABEL_111;
    }
    v53 = v9[1];
    v54 = 0;
    if ( !v53 )
      goto LABEL_87;
    v55 = *(_DWORD *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 0xF4);
    v56 = *(_BYTE *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 0xF2);
    while ( 1 )
    {
      v57 = 0;
      if ( v55 != v53[3].m128i_i32[3] )
        goto LABEL_114;
      if ( v53[3].m128i_i8[10] != v56 )
        goto LABEL_114;
      v58 = v53[3].m128i_u8[9];
      if ( v58 != *(_BYTE *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 0xF1) || v58 > 0xCu )
        goto LABEL_114;
      if ( !memcmp(&v53[4].m128i_u64[1], v7 + 128, 4LL * v53[3].m128i_u8[9]) )
        break;
LABEL_113:
      v57 = 0;
LABEL_114:
      v54 = v53;
      v53 = (const __m128i *)v53[7].m128i_i64[1];
      if ( !v53 )
        goto LABEL_85;
    }
    v59 = v7 + 224;
    *(_BYTE *)v7 = 0;
    if ( v53[3].m128i_i8[8] )
    {
      if ( (unsigned __int8)RscLibExIsSegmentCoalescableWithScu(v53, v59, (unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) )
      {
        RscLibExCoalesceSegmentWithScu(v53, v7 + 224, v51);
        goto LABEL_83;
      }
      if ( *(_BYTE *)v7 )
        goto LABEL_89;
      goto LABEL_113;
    }
    RscLibExStartNewScu(v53, v59, v51);
LABEL_83:
    v57 = 1;
    if ( !v53[3].m128i_i8[8] )
    {
      v53[4].m128i_i64[0] = *(_QWORD *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 0xC0);
      v53[3].m128i_i8[8] = 1;
      v53[3].m128i_i32[3] = *(_DWORD *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 0xF4);
      v53[3].m128i_i8[10] = *(_BYTE *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 0xF2);
      v53[3].m128i_i8[9] = *(_BYTE *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 0xF1);
      v53[4].m128i_i64[1] = *(_QWORD *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 0x100);
      v53[5] = *(const __m128i *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 0x108);
      v53[6] = *(const __m128i *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 0x118);
      v53[7].m128i_i64[0] = *(_QWORD *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 0x128);
    }
LABEL_85:
    if ( v57 )
    {
LABEL_96:
      if ( v54 )
        v54[7].m128i_i64[1] = v53[7].m128i_i64[1];
      v9 = *(const __m128i ***)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 0x18);
      v63 = v9[1];
      if ( v53 != v63 )
      {
        v53[7].m128i_i64[1] = (__int64)v63;
        v9[1] = v53;
      }
    }
    else
    {
      v9 = *(const __m128i ***)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 0x18);
LABEL_87:
      if ( !(unsigned int)NvLibRscPvtAllocateScu(v7 + 252) )
      {
        v53 = *(const __m128i **)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 0x1F8);
        v54 = 0;
LABEL_89:
        v14 = v53[3].m128i_i8[8] == 0;
        *v7 = 0;
        *(_DWORD *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 4) = 0;
        if ( !v14 )
        {
          v60 = RscLibExFlushScu(v53, v53[4].m128i_i64[0], (unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL, v7 + 2);
          if ( v60 )
          {
            v61 = *(__int64 **)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 8);
            ++v11;
            v62 = *v7;
            *(_QWORD *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 8) = v60;
            *v61 = v60;
            if ( (unsigned int)v62 > 1 )
            {
              *(_QWORD *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 0x150) += *(unsigned int *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 4);
              *(_QWORD *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 0x148) += v62;
              ++*(_QWORD *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 0x158);
              v81 = NvLibRscPvtStatsGetBucketIndex();
              ++*(_QWORD *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 0x160 + 8LL * v81);
            }
          }
          v53[3].m128i_i8[8] = 0;
          v53[3].m128i_i32[3] = 0;
        }
        RscLibExStartNewScu(v53, v7 + 224, v51);
        if ( !v53[3].m128i_i8[8] )
        {
          v53[4].m128i_i64[0] = *(_QWORD *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 0xC0);
          v53[3].m128i_i8[8] = 1;
          v53[3].m128i_i32[3] = *(_DWORD *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 0xF4);
          v53[3].m128i_i8[10] = *(_BYTE *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 0xF2);
          v53[3].m128i_i8[9] = *(_BYTE *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 0xF1);
          v53[4].m128i_i64[1] = *(_QWORD *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 0x100);
          v53[5] = *(const __m128i *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 0x108);
          v53[6] = *(const __m128i *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 0x118);
          v53[7].m128i_i64[0] = *(_QWORD *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 0x128);
        }
        goto LABEL_96;
      }
      v64 = *(_QWORD **)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 8);
LABEL_111:
      *v64 = v51;
      *(_QWORD *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 8) = v51;
LABEL_40:
      ++v11;
    }
    v12 = *(_QWORD **)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 8);
    v13 = *(_QWORD *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 0xD8);
    v8 = *(_WORD *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 0x10);
    *(_QWORD *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 0x20) = v13;
  }
  while ( v13 );
  v10 = *(__int64 **)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 0xC8);
LABEL_43:
  v40 = (__m128i *)v9[1];
  v41 = *v9;
  if ( v40 )
  {
    do
    {
      v42 = (__m128i *)v40[7].m128i_i64[1];
      *v7 = 0;
      *(_DWORD *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 4) = 0;
      if ( v40[3].m128i_i8[8] )
      {
        v43 = RscLibExFlushScu(v40, v40[4].m128i_i64[0], (unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL, v7 + 2);
        if ( v43 )
        {
          ++v11;
          *v12 = v43;
          v12 = (_QWORD *)v43;
          if ( v41 )
          {
            v44 = *v7;
            if ( (unsigned int)v44 > 1 )
            {
              v78 = *(unsigned int *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 4);
              v41->m128i_i64[1] += v44;
              v41[1] = _mm_add_epi64(_mm_unpacklo_epi64((__m128i)v78, (__m128i)1uLL), _mm_loadu_si128(v41 + 1));
              v79 = NvLibRscPvtStatsGetBucketIndex();
              ++v41[2].m128i_i64[v79];
            }
          }
        }
        v40[3].m128i_i8[8] = 0;
        v40[3].m128i_i32[3] = 0;
      }
      if ( byte_1401F96A0 == 1 )
        ExFreeToLookasideListEx(&g_NvLibContext, v40);
      v40 = v42;
    }
    while ( v42 );
    v10 = *(__int64 **)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 0xC8);
  }
  v45 = *v9;
  v46 = *(_QWORD *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 0x140);
  v47 = *(_QWORD *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 0x158);
  v9[1] = 0;
  v45->m128i_i64[0] += v46;
  v45->m128i_i64[1] += *(_QWORD *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 0x148);
  v45[1].m128i_i64[0] += *(_QWORD *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 0x150);
  v45[1].m128i_i64[1] += v47;
  v45[2].m128i_i64[0] += *(_QWORD *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 0x160);
  v45[2].m128i_i64[1] += *(_QWORD *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 0x168);
  v45[3].m128i_i64[0] += *(_QWORD *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 0x170);
  v45[3].m128i_i64[1] += *(_QWORD *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 0x178);
  v45[4].m128i_i64[0] += *(_QWORD *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 0x180);
  v45[4].m128i_i64[1] += *(_QWORD *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 0x188);
  if ( v47 )
  {
    v14 = !_BitScanReverse((unsigned int *)&v48, v47);
    *(_DWORD *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 4) = 0;
    if ( v14 )
    {
      v48 = 0;
    }
    else if ( (unsigned int)v48 >= 6 )
    {
      v48 = 5;
    }
    ++v45[5].m128i_i64[v48];
  }
  *v10 = *(_QWORD *)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 0xD0);
  **(_DWORD **)(((unsigned __int64)v84 & 0xFFFFFFFFFFFFFFC0uLL) + 0xE0) = v11;
  return 1;
}

```

## disassembly

```asm
0x140022200  mov     [rsp-8+arg_8], rbx
0x140022205  push    rbp
0x140022206  push    rsi
0x140022207  push    rdi
0x140022208  push    r12
0x14002220a  push    r13
0x14002220c  push    r14
0x14002220e  push    r15
0x140022210  sub     rsp, 2A0h
0x140022217  lea     rbp, [rsp+90h]
0x14002221f  and     rbp, 0FFFFFFFFFFFFFFC0h
0x140022223  mov     rax, cs:__security_cookie
0x14002222a  xor     rax, rsp
0x14002222d  mov     [rbp+240h+var_40], rax
0x140022234  mov     rax, [rsp+2D0h+arg_30]
0x14002223c  movzx   ebx, r9w
0x140022240  mov     r12, r8
0x140022243  mov     [rbp+240h+var_228], r8
0x140022247  mov     [rbp+240h+var_180], rdx
0x14002224e  mov     r13, rcx
0x140022251  mov     [rbp+240h+var_178], rcx
0x140022258  xor     edx, edx; Val
0x14002225a  mov     r8d, 40h ; '@'; Size
0x140022260  mov     [rbp+240h+var_230], bx
0x140022264  lea     rcx, [rbp+240h+var_150]; void *
0x14002226b  mov     [rbp+240h+var_160], rax
0x140022272  mov     [rbp+240h+var_170], 0
0x14002227d  call    memset
0x140022282  xor     edx, edx; Val
0x140022284  lea     rcx, [rbp+240h+var_100]; void *
0x14002228b  mov     r8d, 80h; Size
0x140022291  call    memset
0x140022296  cmp     cs:byte_1401F96A0, 0
0x14002229d  jz      loc_140022B82
0x1400222a3  cmp     [rsp+2D0h+arg_20], 0
0x1400222ab  jz      loc_140022B74
0x1400222b1  xor     r15d, r15d
0x1400222b4  lea     r14, [rbp+240h+var_170]
0x1400222bb  mov     [r12+8], r15
0x1400222c0  mov     rsi, [r13+0]
0x1400222c4  mov     [rbp+240h+var_238], r14
0x1400222c8  mov     [rbp+240h+var_220], rsi
0x1400222cc  test    rsi, rsi
0x1400222cf  jz      loc_1400225FC
0x1400222d5  cmp     word ptr [rsi+140h], 0
0x1400222dd  mov     rax, [rsi]
0x1400222e0  mov     [rbp+240h+var_168], rax
0x1400222e7  jnz     loc_140022546
0x1400222ed  inc     [rbp+240h+var_100]
0x1400222f4  lea     rcx, [rbp+240h+var_210]; void *
0x1400222f8  mov     r12d, 0Eh
0x1400222fe  mov     [rbp+240h+var_218], 0
0x140022306  xor     r13b, r13b
0x140022309  mov     [rbp+240h+var_23C], r12d
0x14002230d  xor     edx, edx; Val
0x14002230f  mov     byte ptr [rbp+240h+var_240], r13b
0x140022313  mov     r8d, 88h; Size
0x140022319  mov     dword ptr [rbp+240h+var_218+4], 146h
0x140022320  call    memset
0x140022325  mov     rcx, [rbp+240h+var_220]
0x140022329  lea     rax, [rbp+240h+Buf2]
0x140022330  mov     [rbp+240h+var_1A0], bx
0x140022337  mov     rbx, [rsi+8]
0x14002233b  mov     [rbp+240h+var_190], rax
0x140022342  lea     rax, [rcx+128h]
0x140022349  mov     esi, [rbx+18h]
0x14002234c  test    rax, rax
0x14002234f  jz      short loc_140022361
0x140022351  mov     eax, [rcx+12Ch]
0x140022357  bt      eax, 0Ah
0x14002235b  jnb     loc_14002278A
0x140022361  xor     edi, edi
0x140022363  mov     [rbp+240h+var_48], rdi
0x14002236a  mov     r14d, edi
0x14002236d  cmp     esi, r12d
0x140022370  jb      loc_140022F99
0x140022376  mov     r12, cs:__imp_NdisGetDataBuffer
0x14002237d  mov     r9d, 1
0x140022383  mov     rax, r12
0x140022386  mov     dword ptr [rsp+2D0h+var_2B0], edi
0x14002238a  xor     r8d, r8d
0x14002238d  mov     edx, 0Eh
0x140022392  mov     rcx, rbx
0x140022395  call    _guard_dispatch_icall
0x14002239a  mov     rcx, rax
0x14002239d  test    rax, rax
0x1400223a0  jz      loc_140022780
0x1400223a6  mov     [rbp+240h+var_210], rbx
0x1400223aa  mov     r14d, 0Eh
0x1400223b0  mov     eax, [rbx+18h]
0x1400223b3  mov     [rbp+240h+var_1FC], eax
0x1400223b6  mov     [rbp+240h+var_208], rcx
0x1400223ba  mov     [rbp+240h+var_1F8], esi
0x1400223bd  movzx   eax, word ptr [rcx+0Ch]
0x1400223c1  add     [rbp+240h+var_19C], 0Eh
0x1400223c8  add     [rbp+240h+var_198], r14d
0x1400223cf  ror     ax, 8
0x1400223d3  mov     [rbp+240h+var_1FE], ax
0x1400223d7  mov     rax, [rbx+8]
0x1400223db  mov     ecx, [rbx+10h]
0x1400223de  add     ecx, r14d
0x1400223e1  cmp     ecx, [rax+28h]
0x1400223e4  jnb     loc_140022D47
0x1400223ea  add     [rbx+28h], r14d
0x1400223ee  add     dword ptr [rbx+18h], 0FFFFFFF2h
0x1400223f2  mov     [rbx+10h], ecx
0x1400223f5  movzx   eax, [rbp+240h+var_1FE]
0x1400223f9  mov     ecx, 600h
0x1400223fe  cmp     ax, cx
0x140022401  jbe     loc_140022B89
0x140022407  cmp     eax, 8100h
0x14002240c  jz      loc_1400227A2
0x140022412  cmp     eax, 88A8h
0x140022417  jz      loc_140022CD4
0x14002241d  sub     esi, r14d
0x140022420  movzx   ecx, ax
0x140022423  mov     [rbp+240h+var_200], r14b
0x140022427  cmp     ecx, 800h
0x14002242d  jnz     loc_1400227B5
0x140022433  mov     r8, [rbp+240h+var_218]
0x140022437  lea     rax, VmsPktPvtGetLengthNetBuffer
0x14002243e  mov     [rsp+2D0h+var_290], 1
0x140022445  lea     r9, [rbp+240h+var_210]
0x140022449  mov     [rsp+2D0h+var_298], rax
0x14002244e  mov     edx, esi
0x140022450  lea     rax, VmsPktRetreatNetBuffer
0x140022457  mov     rcx, rbx
0x14002245a  mov     [rsp+2D0h+var_2A0], rax
0x14002245f  lea     rax, VmsPktAdvanceNetBuffer
0x140022466  mov     [rsp+2D0h+var_2A8], rax
0x14002246b  mov     [rsp+2D0h+var_2B0], r12
0x140022470  call    VmsPktParseIPv4Packet
0x140022475  mov     edi, eax
0x140022477  mov     r12d, [rbp+240h+var_23C]
0x14002247b  xor     esi, esi
0x14002247d  sub     [rbp+240h+var_198], r14d
0x140022484  mov     eax, [rbx+10h]
0x140022487  cmp     eax, r14d
0x14002248a  jb      loc_140022D64
0x140022490  sub     [rbx+28h], r14d
0x140022494  sub     eax, r14d
0x140022497  add     [rbx+18h], r14d
0x14002249b  mov     [rbx+10h], eax
0x14002249e  test    edi, edi
0x1400224a0  js      loc_140022822
0x1400224a6  movzx   eax, [rbp+240h+var_1FE]
0x1400224aa  mov     ecx, 800h
0x1400224af  cmp     ax, cx
0x1400224b2  jnz     loc_140022814
0x1400224b8  cmp     [rbp+240h+var_1D4], 6
0x1400224bc  jnz     loc_140022822
0x1400224c2  mov     rdx, [rbp+240h+var_1E0]
0x1400224c6  xor     ecx, ecx
0x1400224c8  add     rdx, 0Ch
0x1400224cc  mov     r8d, 4
0x1400224d2  mov     r13b, 1
0x1400224d5  call    tcpxsum
0x1400224da  mov     rdx, [rbp+240h+var_1E0]
0x1400224de  mov     r8d, 4
0x1400224e4  movzx   ebx, byte ptr [rbp+240h+var_240]
0x1400224e8  add     rdx, 10h
0x1400224ec  xor     ecx, ecx
0x1400224ee  call    tcpxsum
0x1400224f3  movzx   eax, [rbp+240h+var_194]
0x1400224fa  mov     r12d, [rbp+240h+var_19C]
0x140022501  mov     [rbp+240h+var_14F], al
0x140022507  cmp     [rsp+2D0h+arg_20], 0
0x14002250f  mov     [rbp+240h+var_14E], r12b
0x140022516  mov     [rbp+240h+var_150], 0
0x14002251d  jz      short loc_140022528
0x14002251f  test    r13b, r13b
0x140022522  jnz     loc_14002282B
0x140022528  cmp     [rsp+2D0h+arg_28], 0
0x140022530  jz      short loc_14002253A
0x140022532  test    bl, bl
0x140022534  jnz     loc_14002282B
0x14002253a  mov     r12, [rbp+240h+var_228]
0x14002253e  mov     rsi, [rbp+240h+var_220]
0x140022542  mov     r14, [rbp+240h+var_238]
0x140022546  mov     rbx, [r12+8]
0x14002254b  test    rbx, rbx
0x14002254e  jz      short loc_1400225C3
0x140022550  mov     rdi, [rbx+78h]
0x140022554  xor     eax, eax
0x140022556  mov     [rbp+240h+var_240], ax
0x14002255a  mov     [rbp+240h+var_23C], eax
0x14002255d  cmp     [rbx+38h], al
0x140022560  jz      short loc_14002259C
0x140022562  mov     rdx, [rbx+40h]
0x140022566  lea     r9, [rbp+240h+var_23C]
0x14002256a  lea     r8, [rbp+240h+var_240]
0x14002256e  mov     rcx, rbx
0x140022571  call    RscLibExFlushScu
0x140022576  test    rax, rax
0x140022579  jz      short loc_140022591
0x14002257b  movzx   ecx, [rbp+240h+var_240]
0x14002257f  inc     r15d
0x140022582  mov     [r14], rax
0x140022585  mov     r14, rax
0x140022588  cmp     ecx, 1
0x14002258b  ja      loc_140022E67
0x140022591  mov     byte ptr [rbx+38h], 0
0x140022595  mov     dword ptr [rbx+3Ch], 0
0x14002259c  cmp     cs:byte_1401F96A0, 1
0x1400225a3  jnz     short loc_1400225BB
0x1400225a5  mov     rdx, rbx; Entry
0x1400225a8  lea     rcx, g_NvLibContext; Lookaside
0x1400225af  call    cs:__imp_ExFreeToLookasideListEx
0x1400225b6  nop     dword ptr [rax+rax+00h]
0x1400225bb  mov     rbx, rdi
0x1400225be  test    rdi, rdi
0x1400225c1  jnz     short loc_140022550
0x1400225c3  mov     qword ptr [r12+8], 0
0x1400225cc  mov     [r14], rsi
0x1400225cf  mov     [rbp+240h+var_238], rsi
0x1400225d3  inc     r15d
0x1400225d6  mov     rax, [rbp+240h+var_168]
0x1400225dd  mov     r14, [rbp+240h+var_238]
0x1400225e1  mov     rsi, rax
0x1400225e4  movzx   ebx, [rbp+240h+var_230]
0x1400225e8  mov     [rbp+240h+var_220], rax
0x1400225ec  test    rax, rax
0x1400225ef  jnz     loc_1400222D5
0x1400225f5  mov     r13, [rbp+240h+var_178]
0x1400225fc  mov     rbx, [r12+8]
0x140022601  mov     rsi, [r12]
0x140022605  test    rbx, rbx
0x140022608  jz      loc_14002269F
0x14002260e  mov     r13d, 1
0x140022614  nop     dword ptr [rax+00h]
0x140022618  nop     dword ptr [rax+rax+00000000h]
0x140022620  mov     rdi, [rbx+78h]
0x140022624  xor     eax, eax
0x140022626  mov     [rbp+240h+var_240], ax
0x14002262a  mov     [rbp+240h+var_23C], eax
0x14002262d  cmp     [rbx+38h], al
0x140022630  jz      short loc_140022671
0x140022632  mov     rdx, [rbx+40h]
0x140022636  lea     r9, [rbp+240h+var_23C]
0x14002263a  lea     r8, [rbp+240h+var_240]
0x14002263e  mov     rcx, rbx
0x140022641  call    RscLibExFlushScu
0x140022646  test    rax, rax
0x140022649  jz      short loc_140022666
0x14002264b  inc     r15d
0x14002264e  mov     [r14], rax
0x140022651  mov     r14, rax
0x140022654  test    rsi, rsi
0x140022657  jz      short loc_140022666
0x140022659  movzx   ecx, [rbp+240h+var_240]
0x14002265d  cmp     ecx, r13d
0x140022660  ja      loc_140022EB2
0x140022666  mov     byte ptr [rbx+38h], 0
0x14002266a  mov     dword ptr [rbx+3Ch], 0
0x140022671  cmp     cs:byte_1401F96A0, r13b
0x140022678  jnz     short loc_140022690
0x14002267a  mov     rdx, rbx; Entry
0x14002267d  lea     rcx, g_NvLibContext; Lookaside
0x140022684  call    cs:__imp_ExFreeToLookasideListEx
0x14002268b  nop     dword ptr [rax+rax+00h]
0x140022690  mov     rbx, rdi
0x140022693  test    rdi, rdi
0x140022696  jnz     short loc_140022620
0x140022698  mov     r13, [rbp+240h+var_178]
0x14002269f  mov     rcx, [r12]
0x1400226a3  mov     rax, [rbp+240h+var_100]
0x1400226aa  mov     rdx, [rbp+240h+var_E8]
0x1400226b1  mov     qword ptr [r12+8], 0
0x1400226ba  add     [rcx], rax
0x1400226bd  mov     rax, [rbp+240h+var_F8]
0x1400226c4  add     [rcx+8], rax
0x1400226c8  mov     rax, [rbp+240h+var_F0]
0x1400226cf  add     [rcx+10h], rax
0x1400226d3  add     [rcx+18h], rdx
0x1400226d7  mov     rax, [rbp+240h+var_E0]
0x1400226de  add     [rcx+20h], rax
0x1400226e2  mov     rax, [rbp+240h+var_D8]
0x1400226e9  add     [rcx+28h], rax
0x1400226ed  mov     rax, [rbp+240h+var_D0]
0x1400226f4  add     [rcx+30h], rax
0x1400226f8  mov     rax, [rbp+240h+var_C8]
0x1400226ff  add     [rcx+38h], rax
0x140022703  mov     rax, [rbp+240h+var_C0]
0x14002270a  add     [rcx+40h], rax
0x14002270e  mov     rax, [rbp+240h+var_B8]
0x140022715  add     [rcx+48h], rax
0x140022719  test    rdx, rdx
0x14002271c  jz      short loc_14002273E
0x14002271e  bsr     eax, edx
0x140022721  mov     [rbp+240h+var_23C], 0
0x140022728  jz      loc_140022FDC
0x14002272e  cmp     eax, 6
0x140022731  mov     edx, 5
0x140022736  cmovnb  eax, edx
0x140022739  inc     qword ptr [rcx+rax*8+50h]
0x14002273e  mov     rax, [rbp+240h+var_170]
0x140022745  mov     [r13+0], rax
0x140022749  mov     rax, [rbp+240h+var_160]
0x140022750  mov     [rax], r15d
0x140022753  mov     al, 1
  ... truncated ...
```
