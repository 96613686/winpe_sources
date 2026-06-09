# VmsPtNicPvtRscCoalesceNbls

- ea: `0x140022ff0`
- end: `0x140023e5c`
- name: `VmsPtNicPvtRscCoalesceNbls`
- size: `3692`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation`

## callers

- `0x140014a60`

## callees

- `0x1400208d4`
- `0x140021cb0`
- `0x140022ff0`
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

- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400233ee`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400234b3`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400238ed`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400233ee`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400234b3`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400238ed`
- `NDIS!NdisGetDataBuffer` at `0x1400231bb`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x140023b14`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x140023b8d`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x140023d0f`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x140023df9`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x140023b14`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x140023b8d`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x140023d0f`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x140023df9`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x140023baa`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x140023baa`

## pseudocode

```c
__int64 __fastcall VmsPtNicPvtRscCoalesceNbls(__int64 a1, __int64 *a2, unsigned int a3)
{
  _BYTE *v3; // rbp
  __int64 v4; // rbx
  __int64 v5; // rsi
  __int64 *v6; // r13
  int v8; // r8d
  int v9; // r9d
  char v10; // al
  char v11; // cl
  __int64 v12; // r12
  _QWORD *v13; // r14
  __int64 v14; // rax
  __int64 v15; // rbx
  const __m128i *v16; // r15
  unsigned int v17; // esi
  bool v18; // zf
  int v19; // eax
  struct _NET_BUFFER *v20; // rdi
  char v21; // r13
  unsigned int DataLength; // r15d
  unsigned int v23; // eax
  ULONG v24; // r12d
  __int64 v25; // rax
  __int16 v26; // ax
  unsigned int v27; // ecx
  int v28; // eax
  unsigned int v29; // r15d
  int v30; // eax
  int v31; // r14d
  unsigned int CurrentMdlOffset; // eax
  __int16 v33; // ax
  __int64 v34; // r8
  char v35; // di
  __int64 v36; // rdx
  int v37; // edx
  __int64 v38; // rdi
  __int64 v39; // rax
  __int64 v40; // rcx
  __int64 v41; // rdi
  __int64 v42; // rax
  __int64 v43; // rcx
  __int64 v44; // rcx
  __int64 v45; // rax
  __int64 result; // rax
  unsigned int v47; // eax
  __int64 v48; // r15
  __int64 v49; // r14
  __int64 v50; // rdi
  int v51; // r12d
  char v52; // r13
  char v53; // cl
  unsigned __int8 v54; // al
  _BYTE *v55; // rdx
  __int64 v56; // rax
  __int64 *v57; // r12
  __int64 v58; // rcx
  _QWORD *v59; // r12
  __int64 v60; // rdi
  __int64 v61; // rax
  __int64 v62; // rcx
  _BYTE *v63; // rax
  __int64 v64; // rax
  __int16 v65; // ax
  unsigned int v66; // ecx
  __int64 v67; // rax
  __int64 v68; // rax
  __int16 v69; // ax
  unsigned int v70; // ecx
  int v71; // eax
  unsigned int BucketIndex; // eax
  unsigned __int64 v73; // rax
  int v74; // eax
  unsigned int v75; // eax
  unsigned int v76; // eax
  __int16 v77; // ax
  unsigned int v78; // ecx
  _BYTE v79[4]; // [rsp+90h] [rbp+0h] BYREF

  v3 = (_BYTE *)((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL);
  v4 = *(_QWORD *)(a1 + 3312);
  v5 = a3;
  v6 = a2;
  *(_QWORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0xE8) = a2;
  if ( *(_BYTE *)(v4 + 56) )
    *(_DWORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0x28) = *(unsigned __int16 *)(v4 + 58);
  else
    *(_DWORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0x28) = 4789;
  *(_QWORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0xD0) = 0;
  memset(v3 + 240, 0, 0x40u);
  memset(v3 + 320, 0, 0x80u);
  if ( !byte_1401F96A0 )
    return 0;
  v10 = *(_BYTE *)(v4 + 60);
  v11 = *(_BYTE *)(v4 + 61);
  *(_BYTE *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0xC) = v11;
  *(_BYTE *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0x10) = v10;
  if ( v10 )
  {
    if ( v11 )
      return 0;
  }
  v12 = *v6;
  v13 = v3 + 208;
  v14 = *(_QWORD *)(a1 + 1888);
  v15 = 0;
  *(_QWORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0x18) = ((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL)
                                                                      + 208;
  *(_QWORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0x20) = v12;
  v16 = (const __m128i *)((v5 << 7) + *(_QWORD *)(v14 + 9184));
  v17 = 0;
  *(_QWORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0xE0) = v16;
  if ( !v12 )
    goto LABEL_43;
  do
  {
    v18 = *(_WORD *)(v12 + 320) == 0;
    *(_QWORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0xD8) = *(_QWORD *)v12;
    if ( !v18 )
      goto LABEL_30;
    v19 = *(_DWORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0x28);
    v20 = *(struct _NET_BUFFER **)(v12 + 8);
    v21 = 0;
    ++*(_QWORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0x140);
    *(_OWORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0xB0) = 0;
    *(_WORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0xB0) = v19;
    *(_QWORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0xC0) = ((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL)
                                                                        + 256;
    *(_QWORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0x30) = 0;
    *(_DWORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 8) = 14;
    *v3 = 0;
    *(_BYTE *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 4) = 0;
    *(_DWORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0x34) = 326;
    *(_OWORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0x40) = 0;
    *(_OWORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0x50) = 0;
    *(_OWORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0x60) = 0;
    *(_OWORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0x70) = 0;
    *(_OWORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0x80) = 0;
    *(_OWORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0x90) = 0;
    *(_OWORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0xA0) = 0;
    DataLength = v20->DataLength;
    if ( v12 != -296 )
    {
      v23 = *(_DWORD *)(v12 + 300);
      if ( (v23 & 0x400) == 0 )
      {
        v47 = (v23 >> 11) & 0xFFF;
        if ( v47 )
        {
          if ( v47 < DataLength )
            DataLength = v47;
        }
      }
    }
    v24 = 0;
    *(_QWORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0x1F8) = 0;
    if ( DataLength < 0xE )
    {
      v31 = -1073676266;
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
      v31 = -1073741670;
      v21 = 0;
      goto LABEL_18;
    }
    *(_QWORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0x40) = v20;
    v24 = 14;
    *(_DWORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0x54) = v20->DataLength;
    *(_QWORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0x48) = v25;
    *(_DWORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0x58) = DataLength;
    v26 = *(_WORD *)(v25 + 12);
    *(_DWORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0xB4) += 14;
    *(_DWORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0xB8) += 14;
    *(_WORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0x52) = __ROR2__(v26, 8);
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
    v28 = *(unsigned __int16 *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0x52);
    if ( (unsigned __int16)v28 <= 0x600u )
    {
      if ( (unsigned __int16)(v28 - 2) > 0x5DAu )
        goto LABEL_141;
      if ( DataLength < 0x10 )
      {
        v21 = *v3;
        v31 = -1073676266;
        goto LABEL_18;
      }
      v63 = (_BYTE *)((__int64 (__fastcall *)(struct _NET_BUFFER *, __int64, _BYTE *, __int64, _DWORD))NdisGetDataBuffer)(
                       v20,
                       2,
                       v3 + 504,
                       1,
                       0);
      if ( !v63 )
      {
        v21 = *v3;
        v31 = -1073741670;
        goto LABEL_18;
      }
      v31 = 0;
      if ( *v63 != 0xAA || v63[1] != 0xAA )
        goto LABEL_67;
      if ( DataLength < 0x16 )
      {
        v21 = *v3;
        v31 = -1073676266;
        goto LABEL_18;
      }
      v64 = ((__int64 (__fastcall *)(struct _NET_BUFFER *, __int64, _BYTE *, __int64, _DWORD))NdisGetDataBuffer)(
              v20,
              8,
              v3 + 504,
              1,
              0);
      if ( !v64 )
      {
        v21 = *v3;
        v31 = -1073741670;
        goto LABEL_18;
      }
      if ( *(_BYTE *)(v64 + 2) != 3 )
        goto LABEL_67;
      v65 = *(_WORD *)(v64 + 6);
      v24 = 22;
      *(_DWORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0xB8) += 8;
      *(_WORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0x52) = __ROR2__(v65, 8);
      v66 = v20->CurrentMdlOffset + 8;
      if ( v66 >= *(_DWORD *)(v20->Link.Region + 40) )
      {
        NdisAdvanceNetBufferDataStart(v20, 8u, 0, 0);
      }
      else
      {
        v20->DataOffset += 8;
        v20->DataLength -= 8;
        v20->CurrentMdlOffset = v66;
      }
      LOWORD(v28) = *(_WORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0x52);
      if ( (_WORD)v28 != 0x8100 )
        goto LABEL_16;
      if ( DataLength < 0x1A )
      {
        v21 = *v3;
        v31 = -1073676266;
        goto LABEL_18;
      }
      v67 = ((__int64 (__fastcall *)(struct _NET_BUFFER *, __int64, _QWORD, __int64, _DWORD))NdisGetDataBuffer)(
              v20,
              4,
              0,
              1,
              0);
      if ( !v67 )
      {
        v21 = *v3;
        v31 = -1073741670;
        goto LABEL_18;
      }
      v24 = 26;
      goto LABEL_155;
    }
    if ( v28 == 33024 )
    {
      if ( DataLength < 0x12 )
      {
        v21 = *v3;
        v31 = -1073676266;
        goto LABEL_18;
      }
      v67 = ((__int64 (__fastcall *)(struct _NET_BUFFER *, __int64, _QWORD, __int64, _DWORD))NdisGetDataBuffer)(
              v20,
              4,
              0,
              1,
              0);
      if ( !v67 )
      {
        v21 = *v3;
        v31 = -1073741670;
        goto LABEL_18;
      }
      v24 = 18;
LABEL_155:
      v77 = *(_WORD *)(v67 + 2);
      *(_DWORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0xB8) += 4;
      *(_WORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0x52) = __ROR2__(v77, 8);
      v78 = v20->CurrentMdlOffset + 4;
      if ( v78 >= *(_DWORD *)(v20->Link.Region + 40) )
      {
        NdisAdvanceNetBufferDataStart(v20, 4u, 0, 0);
      }
      else
      {
        v20->DataOffset += 4;
        v20->DataLength -= 4;
        v20->CurrentMdlOffset = v78;
      }
      *(_DWORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0xB4) += 4;
      LOWORD(v28) = *(_WORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0x52);
      goto LABEL_16;
    }
    if ( v28 == 34984 )
    {
      if ( DataLength < 0x16 )
      {
        v21 = *v3;
        v31 = -1073676266;
        goto LABEL_18;
      }
      v68 = ((__int64 (__fastcall *)(struct _NET_BUFFER *, __int64, _QWORD, __int64, _DWORD))NdisGetDataBuffer)(
              v20,
              4,
              0,
              1,
              0);
      if ( !v68 )
      {
        v21 = *v3;
        v31 = -1073741670;
        goto LABEL_18;
      }
      v69 = *(_WORD *)(v68 + 2);
      v24 = 18;
      *(_DWORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0xB8) += 4;
      *(_WORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0x52) = __ROR2__(v69, 8);
      v70 = v20->CurrentMdlOffset + 4;
      if ( v70 < *(_DWORD *)(v20->Link.Region + 40) )
      {
        v20->DataOffset += 4;
        v20->DataLength -= 4;
        v20->CurrentMdlOffset = v70;
      }
      else
      {
        NdisAdvanceNetBufferDataStart(v20, 4u, 0, 0);
      }
      *(_DWORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0xB4) += 4;
      if ( *(_WORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0x52) != 0x8100 )
      {
LABEL_141:
        v21 = *v3;
        v31 = -1073676267;
        goto LABEL_18;
      }
      v67 = ((__int64 (__fastcall *)(struct _NET_BUFFER *, __int64, _QWORD, __int64, _DWORD))NdisGetDataBuffer)(
              v20,
              4,
              0,
              1,
              0);
      if ( !v67 )
      {
        v21 = *v3;
        v31 = -1073741670;
        goto LABEL_18;
      }
      v24 = 22;
      goto LABEL_155;
    }
LABEL_16:
    v29 = DataLength - v24;
    *(_BYTE *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0x50) = v24;
    if ( (unsigned __int16)v28 == 2048 )
    {
      v30 = VmsPktParseIPv4Packet(
              (_DWORD)v20,
              v29,
              *(_QWORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0x30),
              (int)v3 + 64,
              (__int64)NdisGetDataBuffer,
              (__int64)VmsPktAdvanceNetBuffer,
              (__int64)VmsPktRetreatNetBuffer,
              (__int64)VmsPktPvtGetLengthNetBuffer,
              1);
      v21 = *v3;
      v31 = v30;
      goto LABEL_18;
    }
    v31 = 0;
    if ( (unsigned __int16)v28 != 34525 )
    {
LABEL_67:
      v21 = 0;
      goto LABEL_18;
    }
    v71 = VmsPktParseIPv6Packet(
            (_DWORD)v20,
            v29,
            *(_QWORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0x30),
            (int)v3 + 64,
            (__int64)NdisGetDataBuffer,
            (__int64)VmsPktAdvanceNetBuffer,
            (__int64)VmsPktRetreatNetBuffer,
            (__int64)VmsPktPvtGetLengthNetBuffer,
            1);
    v21 = *v3;
    v31 = v71;
LABEL_18:
    *(_DWORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0xB8) -= v24;
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
    if ( v31 < 0 )
    {
LABEL_69:
      v35 = *(_BYTE *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 4);
      goto LABEL_25;
    }
    v33 = *(_WORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0x52);
    if ( v33 == 2048 )
    {
      if ( *(_BYTE *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0x7C) != 6 )
        goto LABEL_69;
      v21 = 1;
      tcpxsum(0, *(_QWORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0x70) + 12LL, 4);
      v34 = 4;
      v35 = *(_BYTE *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 4);
      v36 = *(_QWORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0x70) + 16LL;
    }
    else
    {
      if ( v33 != -31011 || *(_BYTE *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0x80) != 6 )
        goto LABEL_69;
      v35 = 1;
      tcpxsum(0, *(_QWORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0x70) + 8LL, 16);
      v34 = 16;
      v36 = *(_QWORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0x70) + 24LL;
    }
    tcpxsum(0, v36, v34);
    *(_DWORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 8) = *(_DWORD *)(((unsigned __int64)v79
                                                                                  & 0xFFFFFFFFFFFFFFC0uLL)
                                                                                 + 0xB4);
    *(_BYTE *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0xF1) = *(_BYTE *)(((unsigned __int64)v79
                                                                                   & 0xFFFFFFFFFFFFFFC0uLL)
                                                                                  + 0xBC);
LABEL_25:
    v18 = *(_BYTE *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0x10) == 0;
    v37 = *(_DWORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 8);
    *(_BYTE *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0xF2) = v37;
    *(_BYTE *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0xF0) = 0;
    if ( (!v18 || !v21) && (*(_BYTE *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0xC) || !v35) )
    {
      v12 = *(_QWORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0x20);
      v13 = *(_QWORD **)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0x18);
LABEL_30:
      if ( v15 )
      {
        do
        {
          v38 = *(_QWORD *)(v15 + 120);
          *(_WORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 4) = 0;
          *(_DWORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 8) = 0;
          if ( *(_BYTE *)(v15 + 56) )
          {
            v39 = RscLibExFlushScu(v15, *(_QWORD *)(v15 + 64), v3 + 4, v3 + 8);
            if ( v39 )
            {
              v40 = *(unsigned __int16 *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 4);
              ++v17;
              *v13 = v39;
              v13 = (_QWORD *)v39;
              if ( (unsigned int)v40 > 1 )
              {
                *(_QWORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0x150) += *(unsigned int *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 8);
                *(_QWORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0x148) += v40;
                ++*(_QWORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0x158);
                BucketIndex = NvLibRscPvtStatsGetBucketIndex();
                ++*(_QWORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0x160 + 8LL * BucketIndex);
              }
            }
            *(_BYTE *)(v15 + 56) = 0;
            *(_DWORD *)(v15 + 60) = 0;
          }
          if ( byte_1401F96A0 == 1 )
            ExFreeToLookasideListEx(&g_NvLibContext, (PVOID)v15);
          v15 = v38;
        }
        while ( v38 );
      }
      v15 = 0;
      *v13 = v12;
      *(_QWORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0x18) = v12;
      goto LABEL_40;
    }
    v48 = *(_QWORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0x20);
    *(_QWORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0x1F0) = 0;
    *(_BYTE *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 4) = 0;
    *(_QWORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0x1F8) = 0;
    *(_OWORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0x1C0) = 0;
    *(_OWORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0x1D0) = 0;
    *(_OWORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0x1E0) = 0;
    if ( !(unsigned __int8)RscLibExIsNBLFitForCoalescing(
                             v48,
                             v37,
                             v8,
                             v9,
                             (__int64)(v3 + 448),
                             (__int64)(v3 + 4),
                             (__int64)(v3 + 244)) )
    {
      v59 = *(_QWORD **)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0x18);
      if ( !*(_BYTE *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 4) )
      {
        if ( v15 )
        {
          do
          {
            v60 = *(_QWORD *)(v15 + 120);
            *(_WORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 4) = 0;
            *(_DWORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 8) = 0;
            if ( *(_BYTE *)(v15 + 56) )
            {
              v61 = RscLibExFlushScu(v15, *(_QWORD *)(v15 + 64), v3 + 4, v3 + 8);
              if ( v61 )
              {
                v62 = *(unsigned __int16 *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 4);
                ++v17;
                *v59 = v61;
                v59 = (_QWORD *)v61;
                if ( (unsigned int)v62 > 1 )
                {
                  *(_QWORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0x150) += *(unsigned int *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 8);
                  *(_QWORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0x148) += v62;
                  ++*(_QWORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0x158);
                  v75 = NvLibRscPvtStatsGetBucketIndex();
                  ++*(_QWORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0x160 + 8LL * v75);
                }
              }
              *(_BYTE *)(v15 + 56) = 0;
              *(_DWORD *)(v15 + 60) = 0;
            }
            if ( byte_1401F96A0 == 1 )
              ExFreeToLookasideListEx(&g_NvLibContext, (PVOID)v15);
            v15 = v60;
          }
          while ( v60 );
        }
        v15 = 0;
      }
      goto LABEL_109;
    }
    v49 = 0;
    v50 = v15;
    if ( !v15 )
      goto LABEL_85;
    v51 = *(_DWORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0xF4);
    v52 = *(_BYTE *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0xF2);
    while ( 1 )
    {
      v53 = 0;
      if ( v51 != *(_DWORD *)(v50 + 60) )
        goto LABEL_112;
      if ( *(_BYTE *)(v50 + 58) != v52 )
        goto LABEL_112;
      v54 = *(_BYTE *)(v50 + 57);
      if ( v54 != *(_BYTE *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0xF1) || v54 > 0xCu )
        goto LABEL_112;
      if ( !memcmp((const void *)(v50 + 72), v3 + 256, 4LL * *(unsigned __int8 *)(v50 + 57)) )
        break;
LABEL_111:
      v53 = 0;
LABEL_112:
      v49 = v50;
      v50 = *(_QWORD *)(v50 + 120);
      if ( !v50 )
        goto LABEL_84;
    }
    v55 = v3 + 448;
    *(_BYTE *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 4) = 0;
    if ( *(_BYTE *)(v50 + 56) )
    {
      if ( (unsigned __int8)RscLibExIsSegmentCoalescableWithScu(v50, v55, v3 + 4) )
      {
        RscLibExCoalesceSegmentWithScu(v50, v3 + 448, v48);
        goto LABEL_82;
      }
      if ( *(_BYTE *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 4) )
        goto LABEL_87;
      goto LABEL_111;
    }
    RscLibExStartNewScu(v50, v55, v48);
LABEL_82:
    v53 = 1;
    if ( !*(_BYTE *)(v50 + 56) )
    {
      *(_BYTE *)(v50 + 56) = 1;
      *(_QWORD *)(v50 + 64) = &VmsRscLayerNvspVSwitchCookie;
      *(_DWORD *)(v50 + 60) = *(_DWORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0xF4);
      *(_BYTE *)(v50 + 58) = *(_BYTE *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0xF2);
      *(_BYTE *)(v50 + 57) = *(_BYTE *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0xF1);
      *(_QWORD *)(v50 + 72) = *(_QWORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0x100);
      *(_OWORD *)(v50 + 80) = *(_OWORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0x108);
      *(_OWORD *)(v50 + 96) = *(_OWORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0x118);
      *(_QWORD *)(v50 + 112) = *(_QWORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0x128);
    }
LABEL_84:
    if ( v53 )
    {
LABEL_94:
      if ( v49 )
        *(_QWORD *)(v49 + 120) = *(_QWORD *)(v50 + 120);
      if ( v50 != v15 )
      {
        *(_QWORD *)(v50 + 120) = v15;
        v15 = v50;
      }
    }
    else
    {
LABEL_85:
      if ( !(unsigned int)NvLibRscPvtAllocateScu(v3 + 504) )
      {
        v50 = *(_QWORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0x1F8);
        v49 = 0;
LABEL_87:
        v18 = *(_BYTE *)(v50 + 56) == 0;
        *(_WORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 4) = 0;
        *(_DWORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 8) = 0;
        if ( !v18 )
        {
          v56 = RscLibExFlushScu(v50, *(_QWORD *)(v50 + 64), v3 + 4, v3 + 8);
          if ( v56 )
          {
            v57 = *(__int64 **)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0x18);
            ++v17;
            v58 = *(unsigned __int16 *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 4);
            *(_QWORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0x18) = v56;
            *v57 = v56;
            if ( (unsigned int)v58 > 1 )
            {
              *(_QWORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0x150) += *(unsigned int *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 8);
              *(_QWORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0x148) += v58;
              ++*(_QWORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0x158);
              v76 = NvLibRscPvtStatsGetBucketIndex();
              ++*(_QWORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0x160 + 8LL * v76);
            }
          }
          *(_BYTE *)(v50 + 56) = 0;
          *(_DWORD *)(v50 + 60) = 0;
        }
        RscLibExStartNewScu(v50, v3 + 448, *(_QWORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0x20));
        if ( !*(_BYTE *)(v50 + 56) )
        {
          *(_BYTE *)(v50 + 56) = 1;
          *(_QWORD *)(v50 + 64) = &VmsRscLayerNvspVSwitchCookie;
          *(_DWORD *)(v50 + 60) = *(_DWORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0xF4);
          *(_BYTE *)(v50 + 58) = *(_BYTE *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0xF2);
          *(_BYTE *)(v50 + 57) = *(_BYTE *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0xF1);
          *(_QWORD *)(v50 + 72) = *(_QWORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0x100);
          *(_OWORD *)(v50 + 80) = *(_OWORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0x108);
          *(_OWORD *)(v50 + 96) = *(_OWORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0x118);
          *(_QWORD *)(v50 + 112) = *(_QWORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0x128);
        }
        goto LABEL_94;
      }
      v59 = *(_QWORD **)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0x18);
LABEL_109:
      *v59 = v48;
      *(_QWORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0x18) = v48;
LABEL_40:
      ++v17;
    }
    v13 = *(_QWORD **)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0x18);
    v12 = *(_QWORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0xD8);
    *(_QWORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0x20) = v12;
  }
  while ( v12 );
  v16 = *(const __m128i **)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0xE0);
  v6 = *(__int64 **)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0xE8);
LABEL_43:
  if ( v15 )
  {
    do
    {
      v41 = *(_QWORD *)(v15 + 120);
      *(_WORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0xC) = 0;
      *(_DWORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 8) = 0;
      if ( *(_BYTE *)(v15 + 56) )
      {
        v42 = RscLibExFlushScu(v15, *(_QWORD *)(v15 + 64), v3 + 12, v3 + 8);
        if ( v42 )
        {
          ++v17;
          *v13 = v42;
          v13 = (_QWORD *)v42;
          if ( v16 )
          {
            v43 = *(unsigned __int16 *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0xC);
            if ( (unsigned int)v43 > 1 )
            {
              v73 = *(unsigned int *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 8);
              v16->m128i_i64[1] += v43;
              v16[1] = _mm_add_epi64(_mm_unpacklo_epi64((__m128i)v73, (__m128i)1uLL), _mm_loadu_si128(v16 + 1));
              v74 = NvLibRscPvtStatsGetBucketIndex();
              ++v16[2].m128i_i64[v74];
            }
          }
        }
        *(_BYTE *)(v15 + 56) = 0;
        *(_DWORD *)(v15 + 60) = 0;
      }
      if ( byte_1401F96A0 == 1 )
        ExFreeToLookasideListEx(&g_NvLibContext, (PVOID)v15);
      v15 = v41;
    }
    while ( v41 );
  }
  v16->m128i_i64[0] += *(_QWORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0x140);
  v16->m128i_i64[1] += *(_QWORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0x148);
  v16[1].m128i_i64[0] += *(_QWORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0x150);
  v44 = *(_QWORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0x158);
  v16[1].m128i_i64[1] += v44;
  v16[2].m128i_i64[0] += *(_QWORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0x160);
  v16[2].m128i_i64[1] += *(_QWORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0x168);
  v16[3].m128i_i64[0] += *(_QWORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0x170);
  v16[3].m128i_i64[1] += *(_QWORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0x178);
  v16[4].m128i_i64[0] += *(_QWORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0x180);
  v16[4].m128i_i64[1] += *(_QWORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0x188);
  if ( v44 )
  {
    v18 = !_BitScanReverse((unsigned int *)&v45, v44);
    *(_DWORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 8) = 0;
    if ( v18 )
    {
      v45 = 0;
    }
    else if ( (unsigned int)v45 >= 6 )
    {
      v45 = 5;
    }
    ++v16[5].m128i_i64[v45];
  }
  result = v17;
  *v6 = *(_QWORD *)(((unsigned __int64)v79 & 0xFFFFFFFFFFFFFFC0uLL) + 0xD0);
  return result;
}

```

## disassembly

```asm
0x140022ff0  mov     [rsp-8+arg_18], rbx
0x140022ff5  push    rbp
0x140022ff6  push    rsi
0x140022ff7  push    rdi
0x140022ff8  push    r12
0x140022ffa  push    r13
0x140022ffc  push    r14
0x140022ffe  push    r15
0x140023000  sub     rsp, 2A0h
0x140023007  lea     rbp, [rsp+90h]
0x14002300f  and     rbp, 0FFFFFFFFFFFFFFC0h
0x140023013  mov     rax, cs:__security_cookie
0x14002301a  xor     rax, rsp
0x14002301d  mov     [rbp+240h+var_40], rax
0x140023024  mov     rbx, [rcx+0CF0h]
0x14002302b  xor     r14d, r14d
0x14002302e  mov     esi, r8d
0x140023031  mov     r13, rdx
0x140023034  mov     [rbp+240h+var_158], rdx
0x14002303b  mov     rdi, rcx
0x14002303e  cmp     [rbx+38h], r14b
0x140023042  jnz     loc_140023603
0x140023048  mov     [rbp+240h+var_218], 12B5h
0x14002304f  xor     edx, edx; Val
0x140023051  mov     [rbp+240h+var_170], r14
0x140023058  mov     r8d, 40h ; '@'; Size
0x14002305e  lea     rcx, [rbp+240h+var_150]; void *
0x140023065  call    memset
0x14002306a  xor     edx, edx; Val
0x14002306c  lea     rcx, [rbp+240h+var_100]; void *
0x140023073  mov     r8d, 80h; Size
0x140023079  call    memset
0x14002307e  cmp     cs:byte_1401F96A0, r14b
0x140023085  jz      loc_14002393A
0x14002308b  movzx   eax, byte ptr [rbx+3Ch]
0x14002308f  movzx   ecx, byte ptr [rbx+3Dh]
0x140023093  mov     byte ptr [rbp+240h+var_234], cl
0x140023096  mov     [rbp+240h+var_230], al
0x140023099  test    al, al
0x14002309b  jnz     loc_140023932
0x1400230a1  mov     r12, [r13+0]
0x1400230a5  lea     r14, [rbp+240h+var_170]
0x1400230ac  mov     rax, [rdi+760h]
0x1400230b3  xor     ebx, ebx
0x1400230b5  shl     rsi, 7
0x1400230b9  mov     ecx, 1
0x1400230be  mov     [rbp+240h+var_228], r14
0x1400230c2  mov     [rbp+240h+var_220], r12
0x1400230c6  mov     r15, [rax+23E0h]
0x1400230cd  add     r15, rsi
0x1400230d0  xor     esi, esi
0x1400230d2  mov     [rbp+240h+var_160], r15
0x1400230d9  test    r12, r12
0x1400230dc  jz      loc_140023437
0x1400230e2  jmp     short loc_1400230F5
0x1400230f0  mov     ecx, 1
0x1400230f5  cmp     word ptr [r12+140h], 0
0x1400230ff  mov     rax, [r12]
0x140023103  mov     [rbp+240h+var_168], rax
0x14002310a  jnz     loc_14002338A
0x140023110  mov     eax, [rbp+240h+var_218]
0x140023113  xorps   xmm0, xmm0
0x140023116  mov     rdi, [r12+8]
0x14002311b  xor     r13b, r13b
0x14002311e  inc     [rbp+240h+var_100]
0x140023125  movups  [rbp+240h+var_190], xmm0
0x14002312c  mov     word ptr [rbp+240h+var_190], ax
0x140023133  lea     rax, [rbp+240h+Buf2]
0x14002313a  mov     [rbp+240h+var_180], rax
0x140023141  lea     rax, [r12+128h]
0x140023149  mov     [rbp+240h+var_210], 0
0x140023151  mov     [rbp+240h+var_238], 0Eh
0x140023158  mov     [rbp+240h+var_240], r13b
0x14002315c  mov     byte ptr [rbp+240h+var_23C], r13b
0x140023160  mov     dword ptr [rbp+240h+var_210+4], 146h
0x140023167  movups  [rbp+240h+var_200], xmm0
0x14002316b  movups  [rbp+240h+var_1F0], xmm0
0x14002316f  movups  [rbp+240h+var_1E0], xmm0
0x140023173  movups  [rbp+240h+var_1D0], xmm0
0x140023177  movups  [rbp+240h+var_1C0], xmm0
0x14002317e  movups  [rbp+240h+var_1B0], xmm0
0x140023185  movups  [rbp+240h+var_1A0], xmm0
0x14002318c  mov     r15d, [rdi+18h]
0x140023190  test    rax, rax
0x140023193  jz      short loc_1400231A7
0x140023195  mov     eax, [r12+12Ch]
0x14002319d  bt      eax, 0Ah
0x1400231a1  jnb     loc_1400235A0
0x1400231a7  xor     r12d, r12d
0x1400231aa  mov     [rbp+240h+var_48], r12
0x1400231b1  cmp     r15d, 0Eh
0x1400231b5  jb      loc_140023E07
0x1400231bb  mov     r13, cs:__imp_NdisGetDataBuffer
0x1400231c2  mov     r9d, ecx
0x1400231c5  mov     rax, r13
0x1400231c8  mov     dword ptr [rsp+2D0h+var_2B0], r12d
0x1400231cd  xor     r8d, r8d
0x1400231d0  mov     edx, 0Eh
0x1400231d5  mov     rcx, rdi
0x1400231d8  call    _guard_dispatch_icall
0x1400231dd  mov     rcx, rax
0x1400231e0  test    rax, rax
0x1400231e3  jz      loc_140023591
0x1400231e9  mov     qword ptr [rbp+240h+var_200], rdi
0x1400231ed  mov     r12d, 0Eh
0x1400231f3  mov     eax, [rdi+18h]
0x1400231f6  mov     dword ptr [rbp+240h+var_1F0+4], eax
0x1400231f9  mov     qword ptr [rbp+240h+var_200+8], rcx
0x1400231fd  mov     dword ptr [rbp+240h+var_1F0+8], r15d
0x140023201  movzx   eax, word ptr [rcx+0Ch]
0x140023205  add     dword ptr [rbp+240h+var_190+4], 0Eh
0x14002320c  add     dword ptr [rbp+240h+var_190+8], r12d
0x140023213  ror     ax, 8
0x140023217  mov     word ptr [rbp+240h+var_1F0+2], ax
0x14002321b  mov     rax, [rdi+8]
0x14002321f  mov     ecx, [rdi+10h]
0x140023222  add     ecx, r12d
0x140023225  cmp     ecx, [rax+28h]
0x140023228  jnb     loc_140023B81
0x14002322e  add     [rdi+28h], r12d
0x140023232  add     dword ptr [rdi+18h], 0FFFFFFF2h
0x140023236  mov     [rdi+10h], ecx
0x140023239  movzx   eax, word ptr [rbp+240h+var_1F0+2]
0x14002323d  mov     ecx, 600h
0x140023242  cmp     ax, cx
0x140023245  jbe     loc_140023942
0x14002324b  cmp     eax, 8100h
0x140023250  jz      loc_1400235BA
0x140023256  cmp     eax, 88A8h
0x14002325b  jz      loc_140023AA6
0x140023261  mov     r14d, 1
0x140023267  sub     r15d, r12d
0x14002326a  movzx   ecx, ax
0x14002326d  mov     byte ptr [rbp+240h+var_1F0], r12b
0x140023271  cmp     ecx, 800h
0x140023277  jnz     loc_1400235D4
0x14002327d  mov     r8, [rbp+240h+var_210]
0x140023281  lea     rax, VmsPktPvtGetLengthNetBuffer
0x140023288  mov     [rsp+2D0h+var_290], r14w
0x14002328e  lea     r9, [rbp+240h+var_200]
0x140023292  mov     [rsp+2D0h+var_298], rax
0x140023297  mov     edx, r15d
0x14002329a  lea     rax, VmsPktRetreatNetBuffer
0x1400232a1  mov     rcx, rdi
0x1400232a4  mov     [rsp+2D0h+var_2A0], rax
0x1400232a9  lea     rax, VmsPktAdvanceNetBuffer
0x1400232b0  mov     [rsp+2D0h+var_2A8], rax
0x1400232b5  mov     [rsp+2D0h+var_2B0], r13
0x1400232ba  call    VmsPktParseIPv4Packet
0x1400232bf  movzx   r13d, [rbp+240h+var_240]
0x1400232c4  mov     r14d, eax
0x1400232c7  sub     dword ptr [rbp+240h+var_190+8], r12d
0x1400232ce  mov     eax, [rdi+10h]
0x1400232d1  cmp     eax, r12d
0x1400232d4  jb      loc_140023B9E
0x1400232da  sub     [rdi+28h], r12d
0x1400232de  sub     eax, r12d
0x1400232e1  add     [rdi+18h], r12d
0x1400232e5  mov     [rdi+10h], eax
0x1400232e8  test    r14d, r14d
0x1400232eb  js      loc_1400235FA
0x1400232f1  movzx   eax, word ptr [rbp+240h+var_1F0+2]
0x1400232f5  mov     ecx, 800h
0x1400232fa  cmp     ax, cx
0x1400232fd  jnz     loc_1400235EC
0x140023303  cmp     byte ptr [rbp+240h+var_1D0+0Ch], 6
0x140023307  jnz     loc_1400235FA
0x14002330d  mov     rdx, qword ptr [rbp+240h+var_1D0]
0x140023311  xor     ecx, ecx
0x140023313  add     rdx, 0Ch
0x140023317  mov     r8d, 4
0x14002331d  mov     r13b, 1
0x140023320  call    tcpxsum
0x140023325  mov     rdx, qword ptr [rbp+240h+var_1D0]
0x140023329  mov     r8d, 4
0x14002332f  movzx   edi, byte ptr [rbp+240h+var_23C]
0x140023333  add     rdx, 10h
0x140023337  xor     ecx, ecx
0x140023339  call    tcpxsum
0x14002333e  mov     eax, dword ptr [rbp+240h+var_190+4]
0x140023344  mov     [rbp+240h+var_238], eax
0x140023347  movzx   eax, byte ptr [rbp+240h+var_190+0Ch]
0x14002334e  mov     [rbp+240h+var_14F], al
0x140023354  cmp     [rbp+240h+var_230], 0
0x140023358  mov     edx, [rbp+240h+var_238]
0x14002335b  mov     [rbp+240h+var_14E], dl
0x140023361  mov     [rbp+240h+var_150], 0
0x140023368  jnz     short loc_140023373
0x14002336a  test    r13b, r13b
0x14002336d  jnz     loc_14002360F
0x140023373  cmp     byte ptr [rbp+240h+var_234], 0
0x140023377  jnz     short loc_140023382
0x140023379  test    dil, dil
0x14002337c  jnz     loc_14002360F
0x140023382  mov     r12, [rbp+240h+var_220]
0x140023386  mov     r14, [rbp+240h+var_228]
0x14002338a  xor     r13d, r13d
0x14002338d  test    rbx, rbx
0x140023390  jz      short loc_140023402
0x140023392  mov     rdi, [rbx+78h]
0x140023396  mov     [rbp+240h+var_23C], r13w
0x14002339b  mov     [rbp+240h+var_238], r13d
0x14002339f  cmp     [rbx+38h], r13b
0x1400233a3  jz      short loc_1400233DB
0x1400233a5  mov     rdx, [rbx+40h]
0x1400233a9  lea     r9, [rbp+240h+var_238]
0x1400233ad  lea     r8, [rbp+240h+var_23C]
0x1400233b1  mov     rcx, rbx
0x1400233b4  call    RscLibExFlushScu
0x1400233b9  test    rax, rax
0x1400233bc  jz      short loc_1400233D3
0x1400233be  movzx   ecx, [rbp+240h+var_23C]
0x1400233c2  inc     esi
0x1400233c4  mov     [r14], rax
0x1400233c7  mov     r14, rax
0x1400233ca  cmp     ecx, 1
0x1400233cd  ja      loc_140023CD5
0x1400233d3  mov     [rbx+38h], r13b
0x1400233d7  mov     [rbx+3Ch], r13d
0x1400233db  cmp     cs:byte_1401F96A0, 1
0x1400233e2  jnz     short loc_1400233FA
0x1400233e4  mov     rdx, rbx; Entry
0x1400233e7  lea     rcx, g_NvLibContext; Lookaside
0x1400233ee  call    cs:__imp_ExFreeToLookasideListEx
0x1400233f5  nop     dword ptr [rax+rax+00h]
0x1400233fa  mov     rbx, rdi
0x1400233fd  test    rdi, rdi
0x140023400  jnz     short loc_140023392
0x140023402  mov     rbx, r13
0x140023405  mov     [r14], r12
0x140023408  mov     [rbp+240h+var_228], r12
0x14002340c  inc     esi
0x14002340e  mov     rax, [rbp+240h+var_168]
0x140023415  mov     r14, [rbp+240h+var_228]
0x140023419  mov     r12, rax
0x14002341c  mov     [rbp+240h+var_220], rax
0x140023420  test    rax, rax
0x140023423  jnz     loc_1400230F0
0x140023429  mov     r15, [rbp+240h+var_160]
0x140023430  mov     r13, [rbp+240h+var_158]
0x140023437  test    rbx, rbx
0x14002343a  jz      loc_1400234C7
0x140023440  mov     r12d, 1
0x140023446  nop     word ptr [rax+rax+00000000h]
0x140023450  mov     rdi, [rbx+78h]
0x140023454  xor     eax, eax
0x140023456  mov     [rbp+240h+var_234], ax
0x14002345a  mov     [rbp+240h+var_238], eax
0x14002345d  cmp     [rbx+38h], al
0x140023460  jz      short loc_1400234A0
0x140023462  mov     rdx, [rbx+40h]
0x140023466  lea     r9, [rbp+240h+var_238]
0x14002346a  lea     r8, [rbp+240h+var_234]
0x14002346e  mov     rcx, rbx
0x140023471  call    RscLibExFlushScu
0x140023476  test    rax, rax
0x140023479  jz      short loc_140023495
0x14002347b  inc     esi
0x14002347d  mov     [r14], rax
0x140023480  mov     r14, rax
0x140023483  test    r15, r15
0x140023486  jz      short loc_140023495
0x140023488  movzx   ecx, [rbp+240h+var_234]
0x14002348c  cmp     ecx, r12d
0x14002348f  ja      loc_140023D20
0x140023495  mov     byte ptr [rbx+38h], 0
0x140023499  mov     dword ptr [rbx+3Ch], 0
0x1400234a0  cmp     cs:byte_1401F96A0, r12b
0x1400234a7  jnz     short loc_1400234BF
0x1400234a9  mov     rdx, rbx; Entry
0x1400234ac  lea     rcx, g_NvLibContext; Lookaside
0x1400234b3  call    cs:__imp_ExFreeToLookasideListEx
0x1400234ba  nop     dword ptr [rax+rax+00h]
0x1400234bf  mov     rbx, rdi
0x1400234c2  test    rdi, rdi
0x1400234c5  jnz     short loc_140023450
0x1400234c7  mov     rax, [rbp+240h+var_100]
0x1400234ce  add     [r15], rax
0x1400234d1  mov     rax, [rbp+240h+var_F8]
0x1400234d8  add     [r15+8], rax
0x1400234dc  mov     rax, [rbp+240h+var_F0]
0x1400234e3  add     [r15+10h], rax
0x1400234e7  mov     rcx, [rbp+240h+var_E8]
0x1400234ee  add     [r15+18h], rcx
0x1400234f2  mov     rax, [rbp+240h+var_E0]
0x1400234f9  add     [r15+20h], rax
0x1400234fd  mov     rax, [rbp+240h+var_D8]
0x140023504  add     [r15+28h], rax
0x140023508  mov     rax, [rbp+240h+var_D0]
0x14002350f  add     [r15+30h], rax
0x140023513  mov     rax, [rbp+240h+var_C8]
0x14002351a  add     [r15+38h], rax
0x14002351e  mov     rax, [rbp+240h+var_C0]
0x140023525  add     [r15+40h], rax
0x140023529  mov     rax, [rbp+240h+var_B8]
0x140023530  add     [r15+48h], rax
0x140023534  test    rcx, rcx
0x140023537  jz      short loc_140023559
0x140023539  bsr     eax, ecx
0x14002353c  mov     [rbp+240h+var_238], 0
  ... truncated ...
```
