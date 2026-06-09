# VmsNblGenerateToeplitzRssHash

- ea: `0x1400211c0`
- end: `0x140021ca7`
- name: `VmsNblGenerateToeplitzRssHash`
- size: `2791`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140014a60`
- `0x140026000`
- `0x140081450`
- `0x1400913d0`

## callees

- `0x1400208d4`
- `0x1400211c0`
- `0x140021cb0`
- `0x14008ac10`
- `0x1401bbcb0`
- `0x1401bbe80`

## import_xrefs

- `NDIS!NdisGetDataBuffer` at `0x14002131b`
- `NDIS!NdisGetDataBuffer` at `0x140021410`
- `NDIS!NdisGetDataBuffer` at `0x1400216e0`
- `NDIS!NdisGetDataBuffer` at `0x1400217a3`
- `NDIS!NdisGetDataBuffer` at `0x1400217f5`
- `NDIS!NdisGetDataBuffer` at `0x14002187d`
- `NDIS!NdisGetDataBuffer` at `0x1400218fa`
- `NDIS!NdisGetDataBuffer` at `0x140021a1a`
- `NDIS!NdisGetDataBuffer` at `0x140021a6e`
- `NDIS!NdisGetDataBuffer` at `0x140021a90`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x14002195e`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x14002197a`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x140021b02`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x140021be8`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x14002195e`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x14002197a`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x140021b02`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x140021be8`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x140021997`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x140021997`
- `NETIO!RtlComputeToeplitzHash` at `0x1400214e1`
- `NETIO!RtlComputeToeplitzHash` at `0x1400214fd`
- `NETIO!RtlComputeToeplitzHash` at `0x14002152f`
- `NETIO!RtlComputeToeplitzHash` at `0x140021556`
- `NETIO!RtlComputeToeplitzHash` at `0x1400214e1`
- `NETIO!RtlComputeToeplitzHash` at `0x1400214fd`
- `NETIO!RtlComputeToeplitzHash` at `0x14002152f`
- `NETIO!RtlComputeToeplitzHash` at `0x140021556`

## pseudocode

```c
NDIS_STATUS __fastcall VmsNblGenerateToeplitzRssHash(__int64 *a1, char a2, __int16 a3, __int64 a4)
{
  __int64 *v4; // rdi
  __int64 v6; // rbx
  NDIS_STATUS result; // eax
  __int16 v8; // r12
  char v9; // r13
  struct _NET_BUFFER *v10; // rsi
  unsigned int v11; // r14d
  unsigned int DataLength; // r14d
  __int64 v13; // rax
  __int16 v14; // ax
  unsigned int v15; // ecx
  unsigned __int16 v16; // cx
  unsigned int v17; // r14d
  int v18; // eax
  int v19; // ecx
  ULONG v20; // r14d
  ULONG v21; // eax
  unsigned int v22; // r14d
  __int64 v23; // rdx
  int v24; // esi
  __int64 v25; // rax
  int v26; // esi
  int v27; // r14d
  int v28; // ecx
  __int64 v29; // rax
  __int64 v30; // rax
  _BYTE *v31; // rax
  __int64 v32; // rax
  __int16 v33; // ax
  unsigned int CurrentMdlOffset; // ecx
  unsigned int v35; // ecx
  __int64 v36; // rax
  __int64 v37; // rax
  __int16 v38; // ax
  unsigned int v39; // ecx
  unsigned int v40; // ecx
  __int64 v41; // rax
  __int64 v42; // rax
  unsigned int v43; // ecx
  unsigned int v44; // ecx
  ULONG v45; // eax
  char v46; // [rsp+50h] [rbp-B0h]
  char v47; // [rsp+51h] [rbp-AFh]
  int v48; // [rsp+54h] [rbp-ACh]
  __int16 v49; // [rsp+58h] [rbp-A8h]
  __int16 v50; // [rsp+5Ch] [rbp-A4h] BYREF
  __int16 v51; // [rsp+60h] [rbp-A0h] BYREF
  ULONG DataOffsetDelta[2]; // [rsp+68h] [rbp-98h]
  __int128 v53; // [rsp+70h] [rbp-90h] BYREF
  __int128 v54; // [rsp+80h] [rbp-80h]
  __int128 v55; // [rsp+90h] [rbp-70h]
  __int128 v56; // [rsp+A0h] [rbp-60h]
  __int128 v57; // [rsp+B0h] [rbp-50h]
  __int128 v58; // [rsp+C0h] [rbp-40h]
  __int128 v59; // [rsp+D0h] [rbp-30h]
  __int128 v60; // [rsp+E0h] [rbp-20h]
  __int64 v61; // [rsp+F0h] [rbp-10h]
  __int64 v62; // [rsp+100h] [rbp+0h] BYREF
  _UNKNOWN *retaddr; // [rsp+148h] [rbp+48h]

  v49 = a3;
  v47 = a2;
  v61 = 0;
  v4 = a1;
  v50 = 0;
  v51 = 0;
  v53 = 0;
  v54 = 0;
  v55 = 0;
  v56 = 0;
  v57 = 0;
  v58 = 0;
  v59 = 0;
  v60 = 0;
  if ( (VmsDiagnosticFlags & 1) != 0 )
  {
    if ( a1 )
    {
      v29 = a1[36];
      if ( v29 )
      {
        v30 = *(_QWORD *)(v29 + 16);
        if ( v30 )
        {
          *(_DWORD *)(v30 + 184) = 83;
          *(_QWORD *)(v30 + 176) = "VmsNblGenerateToeplitzRssHash";
          *(_QWORD *)(v30 + 168) = retaddr;
        }
      }
    }
  }
  v6 = *(_QWORD *)(a4 + 8);
  result = *(unsigned __int8 *)(a4 + 40);
  v8 = v6;
  *(_QWORD *)DataOffsetDelta = v6;
  v46 = result;
  if ( VmsDisableUDPvRss )
  {
    v9 = DataOffsetDelta[1];
  }
  else
  {
    v8 = v6 | 0xC000;
    DataOffsetDelta[1] = HIDWORD(v6) | 0x46;
    v9 = BYTE4(v6) | 0x46;
    LODWORD(v6) = DataOffsetDelta[0];
  }
  if ( a1 )
  {
    do
    {
      if ( !a2 && v4[27] )
        goto LABEL_34;
      v60 = 0;
      v61 = 0;
      LOWORD(v60) = a3;
      v53 = 0;
      v54 = 0;
      v55 = 0;
      v56 = 0;
      v57 = 0;
      v58 = 0;
      v59 = 0;
      v10 = (struct _NET_BUFFER *)v4[1];
      if ( v4 == (__int64 *)-296LL
        || (v11 = *((_DWORD *)v4 + 75), (v11 & 0x400) != 0)
        || (DataLength = (v11 >> 11) & 0xFFF) == 0 )
      {
        DataLength = v10->DataLength;
      }
      else if ( DataLength >= v10->DataLength )
      {
        DataLength = v10->DataLength;
      }
      DataOffsetDelta[0] = 0;
      v62 = 0;
      if ( DataLength < 0xE )
      {
        v19 = -1073676266;
        v48 = -1073676266;
        goto LABEL_19;
      }
      v13 = ((__int64 (__fastcall *)(struct _NET_BUFFER *, __int64, _QWORD, __int64, _DWORD))NdisGetDataBuffer)(
              v10,
              14,
              0,
              1,
              0);
      if ( !v13 )
      {
        v19 = -1073741670;
        v48 = -1073741670;
        goto LABEL_19;
      }
      *(_QWORD *)&v53 = v10;
      DWORD1(v54) = v10->DataLength;
      *((_QWORD *)&v53 + 1) = v13;
      DWORD2(v54) = DataLength;
      v14 = *(_WORD *)(v13 + 12);
      DWORD1(v60) += 14;
      WORD1(v54) = __ROR2__(v14, 8);
      DWORD2(v60) += 14;
      v15 = v10->CurrentMdlOffset + 14;
      DataOffsetDelta[0] = 14;
      if ( v15 >= *(_DWORD *)(v10->Link.Region + 40) )
      {
        NdisAdvanceNetBufferDataStart(v10, 0xEu, 0, 0);
      }
      else
      {
        v10->DataOffset += 14;
        v10->DataLength -= 14;
        v10->CurrentMdlOffset = v15;
      }
      v16 = WORD1(v54);
      if ( WORD1(v54) <= 0x600u )
      {
        if ( (unsigned __int16)(WORD1(v54) - 2) > 0x5DAu )
          goto LABEL_85;
        if ( DataLength < 0x10 )
        {
          v19 = -1073676266;
          v48 = -1073676266;
          goto LABEL_19;
        }
        v31 = (_BYTE *)((__int64 (__fastcall *)(struct _NET_BUFFER *, __int64, __int64 *, __int64, _DWORD))NdisGetDataBuffer)(
                         v10,
                         2,
                         &v62,
                         1,
                         0);
        if ( !v31 )
        {
          v19 = -1073741670;
          v48 = -1073741670;
          goto LABEL_19;
        }
        v19 = 0;
        v48 = 0;
        if ( *v31 != 0xAA || v31[1] != 0xAA )
          goto LABEL_19;
        if ( DataLength < 0x16 )
        {
          v19 = -1073676266;
          v48 = -1073676266;
          goto LABEL_19;
        }
        v32 = ((__int64 (__fastcall *)(struct _NET_BUFFER *, __int64, __int64 *, __int64, _DWORD))NdisGetDataBuffer)(
                v10,
                8,
                &v62,
                1,
                0);
        if ( !v32 )
        {
          v19 = -1073741670;
          v48 = -1073741670;
          goto LABEL_19;
        }
        if ( *(_BYTE *)(v32 + 2) != 3 )
        {
          v19 = 0;
          goto LABEL_19;
        }
        v33 = *(_WORD *)(v32 + 6);
        DWORD2(v60) += 8;
        WORD1(v54) = __ROR2__(v33, 8);
        CurrentMdlOffset = v10->CurrentMdlOffset;
        DataOffsetDelta[0] = 22;
        v35 = CurrentMdlOffset + 8;
        if ( v35 >= *(_DWORD *)(v10->Link.Region + 40) )
        {
          NdisAdvanceNetBufferDataStart(v10, 8u, 0, 0);
        }
        else
        {
          v10->DataOffset += 8;
          v10->DataLength -= 8;
          v10->CurrentMdlOffset = v35;
        }
        v16 = WORD1(v54);
        if ( WORD1(v54) != 0x8100 )
          goto LABEL_16;
        if ( DataLength < 0x1A )
        {
          v19 = -1073676266;
          v48 = -1073676266;
          goto LABEL_19;
        }
        v36 = ((__int64 (__fastcall *)(struct _NET_BUFFER *, __int64, _QWORD, __int64, _DWORD))NdisGetDataBuffer)(
                v10,
                4,
                0,
                1,
                0);
        if ( !v36 )
        {
          v19 = -1073741670;
          v48 = -1073741670;
          goto LABEL_19;
        }
        WORD1(v54) = __ROR2__(*(_WORD *)(v36 + 2), 8);
        v45 = 26;
      }
      else if ( WORD1(v54) == 33024 )
      {
        if ( DataLength < 0x12 )
        {
          v19 = -1073676266;
          v48 = -1073676266;
          goto LABEL_19;
        }
        v42 = ((__int64 (__fastcall *)(struct _NET_BUFFER *, __int64, _QWORD, __int64, _DWORD))NdisGetDataBuffer)(
                v10,
                4,
                0,
                1,
                0);
        if ( !v42 )
        {
          v19 = -1073741670;
          v48 = -1073741670;
          goto LABEL_19;
        }
        WORD1(v54) = __ROR2__(*(_WORD *)(v42 + 2), 8);
        v45 = 18;
      }
      else
      {
        if ( WORD1(v54) != 34984 )
          goto LABEL_16;
        if ( DataLength < 0x16 )
        {
          v19 = -1073676266;
          v48 = -1073676266;
          goto LABEL_19;
        }
        v37 = ((__int64 (__fastcall *)(struct _NET_BUFFER *, __int64, _QWORD, __int64, _DWORD))NdisGetDataBuffer)(
                v10,
                4,
                0,
                1,
                0);
        if ( !v37 )
        {
          v19 = -1073741670;
          v48 = -1073741670;
          goto LABEL_19;
        }
        v38 = *(_WORD *)(v37 + 2);
        DWORD2(v60) += 4;
        WORD1(v54) = __ROR2__(v38, 8);
        v39 = v10->CurrentMdlOffset;
        DataOffsetDelta[0] = 18;
        v40 = v39 + 4;
        if ( v40 < *(_DWORD *)(v10->Link.Region + 40) )
        {
          v10->DataOffset += 4;
          v10->DataLength -= 4;
          v10->CurrentMdlOffset = v40;
        }
        else
        {
          NdisAdvanceNetBufferDataStart(v10, 4u, 0, 0);
        }
        DWORD1(v60) += 4;
        if ( WORD1(v54) != 0x8100 )
        {
LABEL_85:
          v19 = -1073676267;
          v48 = -1073676267;
          goto LABEL_19;
        }
        v41 = ((__int64 (__fastcall *)(struct _NET_BUFFER *, __int64, _QWORD, __int64, _DWORD))NdisGetDataBuffer)(
                v10,
                4,
                0,
                1,
                0);
        if ( !v41 )
        {
          v19 = -1073741670;
          v48 = -1073741670;
          goto LABEL_19;
        }
        WORD1(v54) = __ROR2__(*(_WORD *)(v41 + 2), 8);
        v45 = 22;
      }
      DWORD2(v60) += 4;
      v43 = v10->CurrentMdlOffset;
      DataOffsetDelta[0] = v45;
      v44 = v43 + 4;
      if ( v44 >= *(_DWORD *)(v10->Link.Region + 40) )
      {
        NdisAdvanceNetBufferDataStart(v10, 4u, 0, 0);
      }
      else
      {
        v10->DataOffset += 4;
        v10->DataLength -= 4;
        v10->CurrentMdlOffset = v44;
      }
      DWORD1(v60) += 4;
      v16 = WORD1(v54);
LABEL_16:
      v17 = DataLength - DataOffsetDelta[0];
      LOBYTE(v54) = DataOffsetDelta[0];
      v18 = v16;
      v19 = 0;
      v48 = 0;
      switch ( v18 )
      {
        case 2048:
          if ( (v9 & 2) != 0 )
          {
            v19 = VmsPktParseIPv4Packet(
                    (_DWORD)v10,
                    v17,
                    v6,
                    (unsigned int)&v53,
                    (__int64)NdisGetDataBuffer,
                    (__int64)VmsPktAdvanceNetBuffer,
                    (__int64)VmsPktRetreatNetBuffer,
                    (__int64)VmsPktPvtGetLengthNetBuffer,
                    1);
            v48 = v19;
          }
          break;
        case 2054:
          if ( (v9 & 8) != 0 )
          {
            v19 = VmsPktParseArpPacket(v10, v17, &v53, NdisGetDataBuffer);
            v48 = v19;
          }
          break;
        case 34525:
          v48 = 0;
          if ( (v9 & 4) != 0 )
          {
            v19 = VmsPktParseIPv6Packet(
                    (_DWORD)v10,
                    v17,
                    v6,
                    (unsigned int)&v53,
                    (__int64)NdisGetDataBuffer,
                    (__int64)VmsPktAdvanceNetBuffer,
                    (__int64)VmsPktRetreatNetBuffer,
                    (__int64)VmsPktPvtGetLengthNetBuffer,
                    1);
            v48 = v19;
          }
          break;
      }
LABEL_19:
      v20 = DataOffsetDelta[0];
      DWORD2(v60) -= DataOffsetDelta[0];
      v21 = v10->CurrentMdlOffset;
      if ( v21 < DataOffsetDelta[0] )
      {
        result = NdisRetreatNetBufferDataStart(v10, DataOffsetDelta[0], 0, 0);
        v19 = v48;
      }
      else
      {
        v10->DataOffset -= DataOffsetDelta[0];
        result = v21 - v20;
        v10->DataLength += v20;
        v10->CurrentMdlOffset = result;
      }
      if ( v19 < 0 )
      {
        a2 = v47;
        a3 = v49;
        if ( v46 )
          _InterlockedIncrement64((volatile signed __int64 *)(a4 + 96));
        goto LABEL_34;
      }
      result = WORD1(v54);
      if ( WORD1(v54) == 2048 )
      {
        v22 = 4;
        v23 = v56 + 12;
        result = v56 + 16;
        v62 = v56 + 16;
        if ( (_BYTE)v57 )
          goto LABEL_98;
        result = BYTE12(v56);
        if ( (v8 & 0x200) != 0 && BYTE12(v56) == 6 )
        {
          v50 = __ROR2__(WORD5(v57), 8);
          v51 = __ROR2__(WORD6(v57), 8);
          DataOffsetDelta[0] = 512;
          if ( v46 )
            _InterlockedIncrement64((volatile signed __int64 *)(a4 + 56));
          goto LABEL_30;
        }
        if ( (v8 & 0x4000) == 0 || BYTE12(v56) != 17 )
        {
LABEL_98:
          if ( (v8 & 0x100) == 0 )
          {
            a2 = v47;
            a3 = v49;
            if ( v46 )
              _InterlockedIncrement64((volatile signed __int64 *)(a4 + 104));
            goto LABEL_34;
          }
          DataOffsetDelta[0] = 256;
          if ( v46 )
            _InterlockedIncrement64((volatile signed __int64 *)(a4 + 48));
          goto LABEL_30;
        }
        v50 = __ROR2__(WORD5(v57), 8);
        v51 = __ROR2__(WORD6(v57), 8);
        DataOffsetDelta[0] = 512;
        if ( v46 )
          _InterlockedIncrement64((volatile signed __int64 *)(a4 + 64));
LABEL_30:
        v24 = RtlComputeToeplitzHash(a4 + 16, v23, v22, 0);
        v25 = v24 ^ (unsigned int)RtlComputeToeplitzHash(a4 + 16, v62, v22, v22);
        if ( (DataOffsetDelta[0] & 0xD200) != 0 )
        {
          v26 = 2 * v22;
          v27 = v25 ^ RtlComputeToeplitzHash(a4 + 16, &v50, 2, 2 * v22);
          v25 = v27 ^ (unsigned int)RtlComputeToeplitzHash(a4 + 16, &v51, 2, (unsigned int)(v26 + 2));
        }
        v28 = *((_DWORD *)v4 + 54);
        v4[26] = v25;
        result = DataOffsetDelta[0];
        v4[27] = DataOffsetDelta[0] | (unsigned __int64)(v28 & 0xFF000000) | 1;
        goto LABEL_33;
      }
      if ( WORD1(v54) == 0x86DD )
      {
        v22 = 16;
        v23 = v56 + 8;
        result = v56 + 24;
        v62 = v56 + 24;
        if ( BYTE1(v57) )
          goto LABEL_106;
        result = (unsigned __int8)v57;
        if ( (v8 & 0x1000) != 0 && (_BYTE)v57 == 6 )
        {
          v50 = __ROR2__(WORD5(v57), 8);
          v51 = __ROR2__(WORD6(v57), 8);
          DataOffsetDelta[0] = 4096;
          if ( v46 )
            _InterlockedIncrement64((volatile signed __int64 *)(a4 + 80));
          goto LABEL_30;
        }
        if ( (v8 & 0x8000) == 0 || (_BYTE)v57 != 17 )
        {
LABEL_106:
          if ( (v8 & 0x400) == 0 )
          {
            a2 = v47;
            a3 = v49;
            if ( v46 )
              _InterlockedIncrement64((volatile signed __int64 *)(a4 + 112));
            goto LABEL_34;
          }
          DataOffsetDelta[0] = 1024;
          if ( v46 )
            _InterlockedIncrement64((volatile signed __int64 *)(a4 + 72));
          goto LABEL_30;
        }
        v50 = __ROR2__(WORD5(v57), 8);
        v51 = __ROR2__(WORD6(v57), 8);
        DataOffsetDelta[0] = 4096;
        if ( v46 )
          _InterlockedIncrement64((volatile signed __int64 *)(a4 + 88));
        goto LABEL_30;
      }
LABEL_33:
      a3 = v49;
      a2 = v47;
LABEL_34:
      v4 = (__int64 *)*v4;
    }
    while ( v4 );
  }
  return result;
}

```

## disassembly

```asm
0x1400211c0  push    rbp
0x1400211c2  push    rbx
0x1400211c3  push    rdi
0x1400211c4  push    r15
0x1400211c6  lea     rbp, [rsp-28h]
0x1400211cb  sub     rsp, 128h
0x1400211d2  mov     rax, cs:__security_cookie
0x1400211d9  xor     rax, rsp
0x1400211dc  mov     [rbp+40h+var_38], rax
0x1400211e0  xorps   xmm0, xmm0
0x1400211e3  mov     [rsp+140h+var_E8], r8w
0x1400211e9  xor     eax, eax
0x1400211eb  mov     [rsp+140h+var_EF], dl
0x1400211ef  mov     [rbp+40h+var_50], rax
0x1400211f3  mov     rdi, rcx
0x1400211f6  mov     rcx, [rbp+48h]
0x1400211fa  mov     r15, r9
0x1400211fd  mov     [rsp+140h+var_E4], ax
0x140021202  mov     [rsp+140h+var_E0], ax
0x140021207  mov     eax, cs:VmsDiagnosticFlags
0x14002120d  movups  [rsp+140h+var_D0], xmm0
0x140021212  movups  [rbp+40h+var_C0], xmm0
0x140021216  movups  [rbp+40h+var_B0], xmm0
0x14002121a  movups  [rbp+40h+var_A0], xmm0
0x14002121e  movups  [rbp+40h+var_90], xmm0
0x140021222  movups  [rbp+40h+var_80], xmm0
0x140021226  movups  [rbp+40h+var_70], xmm0
0x14002122a  movups  [rbp+40h+var_60], xmm0
0x14002122e  test    al, 1
0x140021230  jnz     loc_1400215E3
0x140021236  cmp     cs:VmsDisableUDPvRss, 0
0x14002123d  mov     rbx, [r15+8]
0x140021241  movzx   eax, byte ptr [r15+28h]
0x140021246  mov     [rsp+140h+var_20], r12
0x14002124e  mov     r12d, ebx
0x140021251  mov     qword ptr [rsp+140h+DataOffsetDelta], rbx
0x140021256  mov     [rsp+140h+var_F0], al
0x14002125a  mov     [rsp+140h+var_28], r13
0x140021262  jnz     loc_140021B13
0x140021268  shr     rbx, 20h
0x14002126c  or      r12d, 0C000h
0x140021273  or      ebx, 46h
0x140021276  mov     [rsp+140h+DataOffsetDelta+4], ebx
0x14002127a  mov     r13d, ebx
0x14002127d  mov     rbx, qword ptr [rsp+140h+DataOffsetDelta]
0x140021282  test    rdi, rdi
0x140021285  jz      loc_1400215B9
0x14002128b  mov     [rsp+140h+arg_8], rsi
0x140021293  mov     r9d, 1
0x140021299  mov     [rsp+140h+var_30], r14
0x1400212a1  test    dl, dl
0x1400212a3  jz      loc_14002162D
0x1400212a9  xorps   xmm0, xmm0
0x1400212ac  xor     eax, eax
0x1400212ae  movups  [rbp+40h+var_60], xmm0
0x1400212b2  mov     [rbp+40h+var_50], rax
0x1400212b6  lea     rax, [rdi+128h]
0x1400212bd  mov     word ptr [rbp+40h+var_60], r8w
0x1400212c2  movups  [rsp+140h+var_D0], xmm0
0x1400212c7  movups  [rbp+40h+var_C0], xmm0
0x1400212cb  movups  [rbp+40h+var_B0], xmm0
0x1400212cf  movups  [rbp+40h+var_A0], xmm0
0x1400212d3  movups  [rbp+40h+var_90], xmm0
0x1400212d7  movups  [rbp+40h+var_80], xmm0
0x1400212db  movups  [rbp+40h+var_70], xmm0
0x1400212df  mov     rsi, [rdi+8]
0x1400212e3  mov     ecx, [rsi+18h]
0x1400212e6  test    rax, rax
0x1400212e9  jz      short loc_1400212FD
0x1400212eb  mov     r14d, [rdi+12Ch]
0x1400212f2  bt      r14d, 0Ah
0x1400212f7  jnb     loc_14002164E
0x1400212fd  mov     r14d, ecx
0x140021300  xor     eax, eax
0x140021302  mov     [rsp+140h+DataOffsetDelta], eax
0x140021306  mov     [rbp+40h+var_40], rax
0x14002130a  cmp     r14d, 0Eh
0x14002130e  jb      loc_140021BF6
0x140021314  mov     dword ptr [rsp+140h+var_120], eax
0x140021318  xor     r8d, r8d
0x14002131b  mov     rax, cs:__imp_NdisGetDataBuffer
0x140021322  mov     edx, 0Eh
0x140021327  mov     rcx, rsi
0x14002132a  call    _guard_dispatch_icall
0x14002132f  mov     rcx, rax
0x140021332  test    rax, rax
0x140021335  jz      loc_140021640
0x14002133b  mov     qword ptr [rsp+140h+var_D0], rsi
0x140021340  mov     eax, [rsi+18h]
0x140021343  mov     dword ptr [rbp+40h+var_C0+4], eax
0x140021346  mov     qword ptr [rsp+140h+var_D0+8], rcx
0x14002134b  mov     dword ptr [rbp+40h+var_C0+8], r14d
0x14002134f  movzx   eax, word ptr [rcx+0Ch]
0x140021353  add     dword ptr [rbp+40h+var_60+4], 0Eh
0x140021357  ror     ax, 8
0x14002135b  mov     word ptr [rbp+40h+var_C0+2], ax
0x14002135f  mov     eax, 0Eh
0x140021364  add     dword ptr [rbp+40h+var_60+8], eax
0x140021367  mov     ecx, [rsi+10h]
0x14002136a  add     ecx, eax
0x14002136c  mov     [rsp+140h+DataOffsetDelta], eax
0x140021370  mov     rax, [rsi+8]
0x140021374  cmp     ecx, [rax+28h]
0x140021377  jnb     loc_14002196C
0x14002137d  add     dword ptr [rsi+28h], 0Eh
0x140021381  add     dword ptr [rsi+18h], 0FFFFFFF2h
0x140021385  mov     [rsi+10h], ecx
0x140021388  movzx   ecx, word ptr [rbp+40h+var_C0+2]
0x14002138c  mov     eax, 600h
0x140021391  cmp     cx, ax
0x140021394  jbe     loc_140021787
0x14002139a  mov     eax, ecx
0x14002139c  cmp     ecx, 8100h
0x1400213a2  jz      loc_14002166B
0x1400213a8  cmp     eax, 88A8h
0x1400213ad  jz      loc_1400218F0
0x1400213b3  mov     eax, [rsp+140h+DataOffsetDelta]
0x1400213b7  sub     r14d, eax
0x1400213ba  mov     byte ptr [rbp+40h+var_C0], al
0x1400213bd  movzx   eax, cx
0x1400213c0  xor     ecx, ecx
0x1400213c2  mov     [rsp+140h+var_EC], ecx
0x1400213c6  cmp     eax, 800h
0x1400213cb  jnz     loc_140021683
0x1400213d1  test    r13b, 2
0x1400213d5  jz      short loc_140021427
0x1400213d7  mov     [rsp+140h+var_100], 1
0x1400213de  lea     rax, VmsPktPvtGetLengthNetBuffer
0x1400213e5  mov     [rsp+140h+var_108], rax
0x1400213ea  lea     r9, [rsp+140h+var_D0]
0x1400213ef  lea     rax, VmsPktRetreatNetBuffer
0x1400213f6  mov     r8, rbx
0x1400213f9  mov     [rsp+140h+var_110], rax
0x1400213fe  mov     edx, r14d
0x140021401  lea     rax, VmsPktAdvanceNetBuffer
0x140021408  mov     rcx, rsi
0x14002140b  mov     [rsp+140h+var_118], rax
0x140021410  mov     rax, cs:__imp_NdisGetDataBuffer
0x140021417  mov     [rsp+140h+var_120], rax
0x14002141c  call    VmsPktParseIPv4Packet
0x140021421  mov     ecx, eax
0x140021423  mov     [rsp+140h+var_EC], eax
0x140021427  mov     r14d, [rsp+140h+DataOffsetDelta]
0x14002142c  sub     dword ptr [rbp+40h+var_60+8], r14d
0x140021430  mov     eax, [rsi+10h]
0x140021433  cmp     eax, r14d
0x140021436  jb      loc_14002198B
0x14002143c  sub     [rsi+28h], r14d
0x140021440  sub     eax, r14d
0x140021443  add     [rsi+18h], r14d
0x140021447  mov     [rsi+10h], eax
0x14002144a  test    ecx, ecx
0x14002144c  js      loc_140021B26
0x140021452  movzx   eax, word ptr [rbp+40h+var_C0+2]
0x140021456  mov     ecx, 800h
0x14002145b  cmp     cx, ax
0x14002145e  jnz     loc_1400216FC
0x140021464  mov     rax, qword ptr [rbp+40h+var_A0]
0x140021468  mov     r14d, 4
0x14002146e  lea     rdx, [rax+0Ch]
0x140021472  add     rax, 10h
0x140021476  cmp     byte ptr [rbp+40h+var_90], 0
0x14002147a  mov     [rbp+40h+var_40], rax
0x14002147e  jnz     loc_140021ACC
0x140021484  movzx   eax, byte ptr [rbp+40h+var_A0+0Ch]
0x140021488  bt      r12d, 9
0x14002148d  jnb     short loc_140021497
0x14002148f  cmp     al, 6
0x140021491  jz      loc_1400218B9
0x140021497  bt      r12d, 0Eh
0x14002149c  jnb     loc_140021ACC
0x1400214a2  cmp     al, 11h
0x1400214a4  jnz     loc_140021ACC
0x1400214aa  movzx   eax, word ptr [rbp+40h+var_90+0Ah]
0x1400214ae  ror     ax, 8
0x1400214b2  mov     [rsp+140h+var_E4], ax
0x1400214b7  movzx   eax, word ptr [rbp+40h+var_90+0Ch]
0x1400214bb  ror     ax, 8
0x1400214bf  cmp     [rsp+140h+var_F0], 0
0x1400214c4  mov     [rsp+140h+var_E0], ax
0x1400214c9  mov     [rsp+140h+DataOffsetDelta], 200h
0x1400214d1  jnz     loc_140021C51
0x1400214d7  xor     r9d, r9d
0x1400214da  lea     rcx, [r15+10h]
0x1400214de  mov     r8d, r14d
0x1400214e1  call    cs:__imp_RtlComputeToeplitzHash
0x1400214e8  nop     dword ptr [rax+rax+00h]
0x1400214ed  mov     rdx, [rbp+40h+var_40]
0x1400214f1  lea     rcx, [r15+10h]
0x1400214f5  mov     r9d, r14d
0x1400214f8  mov     r8d, r14d
0x1400214fb  mov     esi, eax
0x1400214fd  call    cs:__imp_RtlComputeToeplitzHash
0x140021504  nop     dword ptr [rax+rax+00h]
0x140021509  xor     eax, esi
0x14002150b  test    [rsp+140h+DataOffsetDelta], 0D200h
0x140021513  mov     [rsp+140h+var_EC], eax
0x140021517  jz      short loc_140021565
0x140021519  lea     esi, [r14+r14]
0x14002151d  mov     r8d, 2
0x140021523  mov     r9d, esi
0x140021526  lea     rdx, [rsp+140h+var_E4]
0x14002152b  lea     rcx, [r15+10h]
0x14002152f  call    cs:__imp_RtlComputeToeplitzHash
0x140021536  nop     dword ptr [rax+rax+00h]
0x14002153b  lea     r9d, [rsi+2]
0x14002153f  mov     r8d, 2
0x140021545  mov     r14d, eax
0x140021548  lea     rdx, [rsp+140h+var_E0]
0x14002154d  xor     r14d, [rsp+140h+var_EC]
0x140021552  lea     rcx, [r15+10h]
0x140021556  call    cs:__imp_RtlComputeToeplitzHash
0x14002155d  nop     dword ptr [rax+rax+00h]
0x140021562  xor     eax, r14d
0x140021565  mov     ecx, [rdi+0D8h]
0x14002156b  mov     [rdi+0D0h], rax
0x140021572  mov     eax, 0FF000000h
0x140021577  and     rcx, rax
0x14002157a  mov     eax, [rsp+140h+DataOffsetDelta]
0x14002157e  or      rcx, rax
0x140021581  or      rcx, 1
0x140021585  mov     [rdi+0D8h], rcx
0x14002158c  movzx   r8d, [rsp+140h+var_E8]
0x140021592  mov     r9d, 1
0x140021598  movzx   edx, [rsp+140h+var_EF]
0x14002159d  mov     rdi, [rdi]
0x1400215a0  test    rdi, rdi
0x1400215a3  jnz     loc_1400212A1
0x1400215a9  mov     r14, [rsp+140h+var_30]
0x1400215b1  mov     rsi, [rsp+140h+arg_8]
0x1400215b9  mov     r13, [rsp+140h+var_28]
0x1400215c1  mov     r12, [rsp+140h+var_20]
0x1400215c9  mov     rcx, [rbp+40h+var_38]
0x1400215cd  xor     rcx, rsp; StackCookie
0x1400215d0  call    __security_check_cookie
0x1400215d5  add     rsp, 128h
0x1400215dc  pop     r15
0x1400215de  pop     rdi
0x1400215df  pop     rbx
0x1400215e0  pop     rbp
0x1400215e1  retn
0x1400215e3  test    rdi, rdi
0x1400215e6  jz      loc_140021236
0x1400215ec  mov     rax, [rdi+120h]
0x1400215f3  test    rax, rax
0x1400215f6  jz      loc_140021236
0x1400215fc  mov     rax, [rax+10h]
0x140021600  test    rax, rax
0x140021603  jz      loc_140021236
0x140021609  lea     r9, aVmsnblgenerate; "VmsNblGenerateToeplitzRssHash"
0x140021610  mov     dword ptr [rax+0B8h], 53h ; 'S'
0x14002161a  mov     [rax+0B0h], r9
0x140021621  mov     [rax+0A8h], rcx
0x140021628  jmp     loc_140021236
0x14002162d  cmp     qword ptr [rdi+0D8h], 0
0x140021635  jnz     loc_14002159D
0x14002163b  jmp     loc_1400212A9
0x140021640  mov     ecx, 0C000009Ah
0x140021645  mov     [rsp+140h+var_EC], ecx
0x140021649  jmp     loc_140021427
0x14002164e  shr     r14d, 0Bh
0x140021652  and     r14d, 0FFFh
0x140021659  jz      loc_1400212FD
0x14002165f  cmp     r14d, ecx
0x140021662  cmovnb  r14d, ecx
0x140021666  jmp     loc_140021300
0x14002166b  cmp     r14d, 12h
0x14002166f  jnb     loc_140021A90
0x140021675  mov     ecx, 0C0010016h
0x14002167a  mov     [rsp+140h+var_EC], ecx
0x14002167e  jmp     loc_140021427
0x140021683  cmp     eax, 806h
0x140021688  jz      loc_140021A64
0x14002168e  cmp     eax, 86DDh
0x140021693  jnz     loc_140021427
0x140021699  mov     [rsp+140h+var_EC], ecx
0x14002169d  test    r13b, 4
0x1400216a1  jz      loc_140021427
0x1400216a7  mov     [rsp+140h+var_100], 1
0x1400216ae  lea     rax, VmsPktPvtGetLengthNetBuffer
0x1400216b5  mov     [rsp+140h+var_108], rax
0x1400216ba  lea     r9, [rsp+140h+var_D0]
0x1400216bf  lea     rax, VmsPktRetreatNetBuffer
0x1400216c6  mov     r8, rbx
0x1400216c9  mov     [rsp+140h+var_110], rax
0x1400216ce  mov     edx, r14d
0x1400216d1  lea     rax, VmsPktAdvanceNetBuffer
0x1400216d8  mov     rcx, rsi
0x1400216db  mov     [rsp+140h+var_118], rax
0x1400216e0  mov     rax, cs:__imp_NdisGetDataBuffer
0x1400216e7  mov     [rsp+140h+var_120], rax
0x1400216ec  call    VmsPktParseIPv6Packet
0x1400216f1  mov     ecx, eax
0x1400216f3  mov     [rsp+140h+var_EC], eax
0x1400216f7  jmp     loc_140021427
0x1400216fc  mov     ecx, 86DDh
0x140021701  cmp     cx, ax
0x140021704  jnz     loc_14002158C
0x14002170a  mov     rax, qword ptr [rbp+40h+var_A0]
0x14002170e  mov     r14d, 10h
  ... truncated ...
```
