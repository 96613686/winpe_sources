# VhdmpiScsiCommandWriteUsingToken(VHD_SCSI_STATE *,VHD_SCSI_REQUEST *,VHD_SCSI_ACTION *)

- ea: `0x140045188`
- end: `0x140045a1e`
- name: `?VhdmpiScsiCommandWriteUsingToken@@YAEPEAUVHD_SCSI_STATE@@PEAUVHD_SCSI_REQUEST@@PEAUVHD_SCSI_ACTION@@@Z`
- size: `2198`
- prototype: `unsigned __int8 __fastcall(struct VHD_SCSI_STATE *, struct VHD_SCSI_REQUEST *, struct VHD_SCSI_ACTION *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140043dd0`

## callees

- `0x140014940`
- `0x140023980`
- `0x140036284`
- `0x1400431d4`
- `0x1400437dc`
- `0x140045188`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400459f3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400459f3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400457ba`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400457ba`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400457e4`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400457e4`

## string_xrefs

- `0x140045411`: `VhdmpiScsiCommandWriteUsingToken: BlockDeviceRangeDescriptorListLength too large (%u + 16 > %u)`
- `0x140045462`: `VhdmpiScsiCommandWriteUsingToken: BlockDeviceRangeDescriptorListLength too small (%u < %u)`
- `0x1400454ae`: `VhdmpiScsiCommandWriteUsingToken: RangeListCount too large (%u > %u)`
- `0x14004552a`: `VhdmpiScsiCommandWriteUsingToken: PopulateTokenHeader->Immediate != 0 --- this is not supported`
- `0x140045277`: `VhdmpiScsiCommandWriteUsingToken: buffer too small relative to PARAMETER LIST LENGTH (%u < %u)`
- `0x1400452cf`: `VhdmpiScsiCommandWriteUsingToken: ParameterListLength non-zero, but too small (%u < %u)`
- `0x140045328`: `VhdmpiScsiCommandWriteUsingToken: WriteUsingTokenDataLength too small (%u < %u)`
- `0x1400453b6`: `VhdmpiScsiCommandWriteUsingToken: WriteUsingTokenDataLength too large (%u + 2 > %u)`
- `0x140045219`: `VhdmpiScsiCommandWriteUsingToken: PARAMETER LIST LENGTH of zero not considered an error`
- `0x140045227`: `VhdmpiScsiCommandWriteUsingToken`
- `0x14004528b`: `VhdmpiScsiCommandWriteUsingToken`
- `0x14004533e`: `VhdmpiScsiCommandWriteUsingToken`
- `0x1400454c2`: `VhdmpiScsiCommandWriteUsingToken`
- `0x14004553e`: `VhdmpiScsiCommandWriteUsingToken`
- `0x1400456be`: `VhdmpiScsiCommandWriteUsingToken`
- `0x140045837`: `VhdmpiScsiCommandWriteUsingToken`
- `0x1400458b1`: `VhdmpiScsiCommandWriteUsingToken`
- `0x14004595e`: `VhdmpiScsiCommandWriteUsingToken`
- `0x14004599b`: `Offload Write start (ScsiState:%p, Request:%p TransactionId:%d TokenOffset: %#016I64x) : LBA: start %#016I64x, length %#016I64x, total %#016I64x BYTE: offset: %#016I64x length: %#016I64x, total: %#016I64x`
- `0x14004563b`: `VhdmpiScsiCommandWriteUsingToken: RangeByteLength == 0, setting UpperSrbStatus to SRB_STATUS_ERROR`
- `0x1400456aa`: `VhdmpiScsiCommandWriteUsingToken: VhdmpiAllocateAndInitializeOffloadOp() failed - setting UpperSrbStatus to SRB_STATUS_ERROR`
- `0x140045823`: `VhdmpiScsiCommandWriteUsingToken: VhdmpiOffloadTableInsertLocked returned STATUS_DUPLICATE_OBJECTID`
- `0x14004589d`: `VhdmpiScsiCommandWriteUsingToken: VhdmpiOffloadTableInsertLocked returned STATUS_INSUFFICIENT_RESOURCES`

## pseudocode

```c
unsigned __int8 __fastcall VhdmpiScsiCommandWriteUsingToken(
        struct VHD_SCSI_STATE *a1,
        struct VHD_SCSI_REQUEST *a2,
        struct VHD_SCSI_ACTION *a3)
{
  _BYTE *v3; // rdi
  unsigned int v6; // edx
  unsigned __int8 v7; // bp
  unsigned int v8; // edx
  int v9; // r9d
  unsigned int v10; // edx
  int v11; // r9d
  int v12; // r10d
  __int64 v13; // rbx
  __int64 v14; // r8
  unsigned int v15; // edx
  int v16; // r8d
  unsigned __int16 v17; // cx
  char *v18; // rax
  unsigned int v19; // edx
  int v20; // r8d
  int v21; // r9d
  __int64 v22; // r8
  unsigned int v23; // edx
  int v24; // r8d
  int v25; // r9d
  unsigned int v26; // r8d
  unsigned int v27; // edx
  int v28; // r8d
  char v29; // al
  unsigned int v30; // edx
  unsigned int v31; // edx
  unsigned __int64 v32; // r10
  __int64 i; // r13
  __int64 v34; // r9
  __int64 v35; // r9
  __int64 v36; // rax
  int v37; // r15d
  __int64 v38; // rdx
  unsigned int v39; // edx
  struct VHD_SCSI_REQUEST *v40; // rdx
  struct VHD_SCSI_STATE *v41; // r11
  unsigned int v42; // edx
  char *v43; // r15
  char v44; // cl
  __int64 v45; // rdx
  _OWORD *v46; // rcx
  _OWORD *v47; // rax
  __int64 v48; // rdx
  __int128 v49; // xmm1
  KIRQL v50; // bl
  unsigned int v51; // edx
  char v52; // al
  unsigned int v53; // edx
  char v54; // al
  unsigned __int64 v55; // rdi
  unsigned int v56; // edx
  int v57; // ebx
  unsigned __int64 v58; // r14
  int v60; // [rsp+30h] [rbp-C8h]
  __int64 v61; // [rsp+80h] [rbp-78h]
  __int64 v62; // [rsp+88h] [rbp-70h]
  unsigned __int64 v63; // [rsp+90h] [rbp-68h]
  unsigned __int64 v64; // [rsp+98h] [rbp-60h]
  __int64 v65; // [rsp+A0h] [rbp-58h]
  unsigned __int64 v66; // [rsp+A8h] [rbp-50h]
  char *v67; // [rsp+B0h] [rbp-48h]
  unsigned int v69; // [rsp+108h] [rbp+10h]
  int inserted; // [rsp+108h] [rbp+10h]
  PVOID P; // [rsp+118h] [rbp+20h] BYREF

  v3 = *(_BYTE **)a2;
  P = 0;
  HIBYTE(v69) = v3[10];
  BYTE2(v69) = v3[11];
  BYTE1(v69) = v3[12];
  LOBYTE(v69) = v3[13];
  if ( !v69 )
  {
    if ( (unsigned int)dword_1400876D0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 32) )
      TraceEvents(
        "VhdmpiScsiCommandWriteUsingToken",
        0x190Fu,
        v6 - 27,
        v6,
        "VhdmpiScsiCommandWriteUsingToken: PARAMETER LIST LENGTH of zero not considered an error");
    return 1;
  }
  if ( v69 > *((_DWORD *)a2 + 4) )
  {
    if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 32) )
      TraceEvents(
        "VhdmpiScsiCommandWriteUsingToken",
        0x1921u,
        2u,
        v8,
        "VhdmpiScsiCommandWriteUsingToken: buffer too small relative to PARAMETER LIST LENGTH (%u < %u)",
        *((_DWORD *)a2 + 4),
        v9);
    return 18;
  }
  if ( v69 < 0x218 )
  {
    if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 32) )
      TraceEvents(
        "VhdmpiScsiCommandWriteUsingToken",
        0x192Fu,
        2u,
        v10,
        "VhdmpiScsiCommandWriteUsingToken: ParameterListLength non-zero, but too small (%u < %u)",
        v11,
        v12);
    return 18;
  }
  v13 = *((_QWORD *)a2 + 1);
  v14 = (unsigned __int16)__ROR2__(*(_WORD *)v13, 8);
  if ( (unsigned int)v14 < 0x226 )
  {
    if ( (unsigned int)dword_1400876D0 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_1400876D0, 32) )
      goto LABEL_20;
    v17 = 6474;
    v60 = 550;
    v18 = "VhdmpiScsiCommandWriteUsingToken: WriteUsingTokenDataLength too small (%u < %u)";
LABEL_19:
    TraceEvents("VhdmpiScsiCommandWriteUsingToken", v17, 2u, v15, v18, v16, v60);
LABEL_20:
    *((_BYTE *)a2 + 37) = 2;
    v7 = 4;
    *(_OWORD *)((char *)a2 + 42) = 0;
    *((_WORD *)a2 + 29) = 0;
    *(_WORD *)((char *)a2 + 41) = 28673;
    *((_BYTE *)a2 + 44) = *((_BYTE *)a2 + 44) & 0xF0 | 5;
    *((_BYTE *)a2 + 49) = 10;
    *((_BYTE *)a2 + 54) = 38;
    return v7;
  }
  if ( v14 + 2 > (unsigned __int64)v69 )
  {
    if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 32) )
      TraceEvents(
        "VhdmpiScsiCommandWriteUsingToken",
        0x195Eu,
        2u,
        v19,
        "VhdmpiScsiCommandWriteUsingToken: WriteUsingTokenDataLength too large (%u + 2 > %u)",
        v20,
        v21);
    return 18;
  }
  v22 = (unsigned __int16)__ROR2__(*(_WORD *)(v13 + 534), 8);
  if ( v22 + 536 > (unsigned __int64)v69 )
  {
    if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 32) )
      TraceEvents(
        "VhdmpiScsiCommandWriteUsingToken",
        0x1970u,
        2u,
        v23,
        "VhdmpiScsiCommandWriteUsingToken: BlockDeviceRangeDescriptorListLength too large (%u + 16 > %u)",
        v24,
        v25);
    return 18;
  }
  if ( (unsigned int)v22 < 0x10 )
  {
    if ( (unsigned int)dword_1400876D0 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_1400876D0, 32) )
      goto LABEL_20;
    v17 = 6525;
    v60 = 16;
    v18 = "VhdmpiScsiCommandWriteUsingToken: BlockDeviceRangeDescriptorListLength too small (%u < %u)";
    goto LABEL_19;
  }
  v26 = (unsigned int)v22 >> 4;
  if ( v26 > 8 )
  {
    if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 32) )
      TraceEvents(
        "VhdmpiScsiCommandWriteUsingToken",
        0x1992u,
        2u,
        v27,
        "VhdmpiScsiCommandWriteUsingToken: RangeListCount too large (%u > %u)",
        v28,
        8);
    *((_BYTE *)a2 + 37) = 2;
    v7 = 6;
    *(_OWORD *)((char *)a2 + 42) = 0;
    *((_WORD *)a2 + 29) = 0;
    *(_WORD *)((char *)a2 + 41) = 28673;
    v29 = *((_BYTE *)a2 + 44) & 0xF5;
    *((_BYTE *)a2 + 49) = 10;
    *((_BYTE *)a2 + 54) = 38;
    *((_BYTE *)a2 + 44) = v29 | 5;
    return v7;
  }
  if ( (*(_BYTE *)(v13 + 2) & 1) != 0 )
  {
    if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 32) )
      TraceEvents(
        "VhdmpiScsiCommandWriteUsingToken",
        0x19A9u,
        2u,
        v30,
        "VhdmpiScsiCommandWriteUsingToken: PopulateTokenHeader->Immediate != 0 --- this is not supported");
    return 4;
  }
  v31 = 1;
  v32 = _byteswap_uint64(*(_QWORD *)(v13 + 536));
  v66 = v32;
  for ( i = _byteswap_ulong(*(_DWORD *)(v13 + 544)); v31 < v26; i += _byteswap_ulong(*(_DWORD *)(v13 + 8 * v34 + 544)) )
  {
    v34 = 2LL * v31;
    if ( v32 + i != _byteswap_uint64(*(_QWORD *)(v13 + 16LL * v31 + 536)) )
      break;
    ++v31;
  }
  v62 = i;
  v35 = i;
  if ( v31 < v26 )
  {
    do
    {
      v36 = v31++;
      v35 += _byteswap_ulong(*(_DWORD *)(v13 + 16 * v36 + 544));
    }
    while ( v31 < v26 );
    v62 = v35;
  }
  v37 = *((_DWORD *)a1 + 16);
  LODWORD(v38) = 0x4000000;
  v61 = 0x4000000;
  if ( (unsigned __int64)(i << v37) <= 0x4000000 )
  {
    v61 = i << v37;
    v38 = i << v37;
    if ( !(i << v37) )
    {
      if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 32) )
        TraceEvents(
          "VhdmpiScsiCommandWriteUsingToken",
          0x19F2u,
          2u,
          v39,
          "VhdmpiScsiCommandWriteUsingToken: RangeByteLength == 0, setting UpperSrbStatus to SRB_STATUS_ERROR");
      return 4;
    }
  }
  v63 = v32 << v37;
  v7 = VhdmpiValidateReadWriteScsiParameters(a1, a2, v38, v32 << v37);
  if ( v7 == 1 )
  {
    if ( (int)VhdmpiAllocateAndInitializeOffloadOp(v41, v40, (struct _VHD_OFFLOAD_OP **)&P) >= 0 )
    {
      v44 = v37;
      v43 = (char *)P;
      v7 = 4;
      v45 = v62 << v44;
      v46 = (_OWORD *)(v13 + 16);
      v65 = v45;
      *((_BYTE *)P + 51) = v3[6];
      v43[50] = v3[7];
      v43[49] = v3[8];
      v43[48] = v3[9];
      v47 = v43 + 128;
      *((_DWORD *)v43 + 14) = 1;
      *((_QWORD *)v43 + 14) = v45;
      v48 = 4;
      v67 = v43 + 128;
      *((_DWORD *)a2 + 6) = 2;
      *((_QWORD *)a2 + 10) = v43;
      do
      {
        *v47 = *v46;
        v47[1] = v46[1];
        v47[2] = v46[2];
        v47[3] = v46[3];
        v47[4] = v46[4];
        v47[5] = v46[5];
        v47[6] = v46[6];
        v49 = v46[7];
        v46 += 8;
        v47[7] = v49;
        v47 += 8;
        --v48;
      }
      while ( v48 );
      v64 = _byteswap_uint64(*(_QWORD *)(v13 + 8));
      LODWORD(P) = *((_DWORD *)a1 + 16);
      v50 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)a1 + 10);
      inserted = VhdmpiOffloadTableInsertLocked(a1, (struct _VHD_OFFLOAD_OP *)v43);
      KeReleaseSpinLock((PKSPIN_LOCK)a1 + 10, v50);
      if ( inserted == -1073741270 )
      {
        if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 32) )
          TraceEvents(
            "VhdmpiScsiCommandWriteUsingToken",
            0x1A2Au,
            2u,
            v51,
            "VhdmpiScsiCommandWriteUsingToken: VhdmpiOffloadTableInsertLocked returned STATUS_DUPLICATE_OBJECTID");
        *((_BYTE *)a2 + 37) = 2;
        *(_OWORD *)((char *)a2 + 42) = 0;
        *((_WORD *)a2 + 29) = 0;
        *(_WORD *)((char *)a2 + 41) = 28673;
        v52 = *((_BYTE *)a2 + 44) & 0xF5;
        *((_BYTE *)a2 + 49) = 10;
        *((_BYTE *)a2 + 55) = 22;
        *((_BYTE *)a2 + 44) = v52 | 5;
      }
      else if ( inserted == -1073741670 )
      {
        if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 32) )
          TraceEvents(
            "VhdmpiScsiCommandWriteUsingToken",
            0x1A38u,
            2u,
            v53,
            "VhdmpiScsiCommandWriteUsingToken: VhdmpiOffloadTableInsertLocked returned STATUS_INSUFFICIENT_RESOURCES");
        *((_BYTE *)a2 + 37) = 2;
        *(_OWORD *)((char *)a2 + 42) = 0;
        *((_WORD *)a2 + 29) = 0;
        *(_WORD *)((char *)a2 + 41) = 28673;
        v54 = *((_BYTE *)a2 + 44) & 0xFB;
        *((_BYTE *)a2 + 49) = 10;
        *((_WORD *)a2 + 27) = 853;
        *((_BYTE *)a2 + 44) = v54 | 0xB;
      }
      else
      {
        v55 = v64 << (char)P;
        if ( (unsigned int)dword_1400876D0 <= 5 )
        {
          v57 = v61;
          v58 = v63;
        }
        else
        {
          v57 = v61;
          v58 = v63;
          if ( (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 32) )
            TraceEvents(
              "VhdmpiScsiCommandWriteUsingToken",
              0x1A52u,
              v56 - 27,
              v56,
              "Offload Write start (ScsiState:%p, Request:%p TransactionId:%d TokenOffset: %#016I64x) : LBA: start %#016I"
              "64x, length %#016I64x, total %#016I64x BYTE: offset: %#016I64x length: %#016I64x, total: %#016I64x",
              a1,
              a2,
              *((_DWORD *)v43 + 12),
              v55,
              v66,
              i,
              v62,
              v63,
              v61,
              v65);
        }
        v43 = 0;
        *((_DWORD *)a3 + 4) = 4;
        v7 = 0;
        *((_DWORD *)a3 + 3) = 0;
        *((_QWORD *)a3 + 5) = v67;
        *(_QWORD *)a3 = v58;
        *((_DWORD *)a3 + 2) = v57;
        *((_QWORD *)a3 + 6) = v55;
      }
    }
    else
    {
      if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 32) )
        TraceEvents(
          "VhdmpiScsiCommandWriteUsingToken",
          0x1A10u,
          2u,
          v42,
          "VhdmpiScsiCommandWriteUsingToken: VhdmpiAllocateAndInitializeOffloadOp() failed - setting UpperSrbStatus to SRB_STATUS_ERROR");
      v43 = (char *)P;
      v7 = 4;
    }
    if ( v43 )
      ExFreePoolWithTag(v43, 0);
  }
  return v7;
}

```

## disassembly

```asm
0x140045188  mov     rax, rsp
0x14004518b  mov     [rax+18h], rbx
0x14004518f  mov     [rax+8], rcx
0x140045193  push    rbp
0x140045194  push    rsi
0x140045195  push    rdi
0x140045196  push    r12
0x140045198  push    r13
0x14004519a  push    r14
0x14004519c  push    r15
0x14004519e  sub     rsp, 0C0h
0x1400451a5  mov     rdi, [rdx]
0x1400451a8  mov     r12, r8
0x1400451ab  mov     qword ptr [rax+20h], 0
0x1400451b3  mov     rsi, rdx
0x1400451b6  mov     r11, rcx
0x1400451b9  mov     al, [rdi+0Ah]
0x1400451bc  mov     byte ptr [rsp+0F8h+arg_8+3], al
0x1400451c3  mov     al, [rdi+0Bh]
0x1400451c6  mov     byte ptr [rsp+0F8h+arg_8+2], al
0x1400451cd  mov     al, [rdi+0Ch]
0x1400451d0  mov     byte ptr [rsp+0F8h+arg_8+1], al
0x1400451d7  mov     al, [rdi+0Dh]
0x1400451da  mov     byte ptr [rsp+0F8h+arg_8], al
0x1400451e1  mov     r9d, [rsp+0F8h+arg_8]
0x1400451e9  test    r9d, r9d
0x1400451ec  jnz     short loc_14004523B
0x1400451ee  mov     eax, cs:dword_1400876D0
0x1400451f4  cmp     eax, 5
0x1400451f7  jbe     short loc_140045233
0x1400451f9  lea     edx, [r9+20h]
0x1400451fd  lea     rcx, dword_1400876D0
0x140045204  call    _tlgKeywordOn
0x140045209  test    al, al
0x14004520b  jz      short loc_140045233
0x14004520d  mov     ecx, 190Fh
0x140045212  lea     r8d, [rdx-1Bh]; int
0x140045216  mov     r9d, edx; int
0x140045219  lea     rax, aVhdmpiscsicomm_40; "VhdmpiScsiCommandWriteUsingToken: PARAM"...
0x140045220  mov     edx, ecx; int
0x140045222  mov     [rsp+0F8h+var_D8], rax; char *
0x140045227  lea     rcx, aVhdmpiscsicomm_10; "VhdmpiScsiCommandWriteUsingToken"
0x14004522e  call    TraceEvents
0x140045233  mov     bpl, 1
0x140045236  jmp     loc_1400459FF
0x14004523b  mov     r14d, 2
0x140045241  cmp     r9d, [rdx+10h]
0x140045245  jbe     short loc_14004529F
0x140045247  mov     eax, cs:dword_1400876D0
0x14004524d  cmp     eax, r14d
0x140045250  jbe     short loc_140045297
0x140045252  lea     edx, [r14+1Eh]
0x140045256  lea     rcx, dword_1400876D0
0x14004525d  call    _tlgKeywordOn
0x140045262  test    al, al
0x140045264  jz      short loc_140045297
0x140045266  mov     eax, [rsi+10h]
0x140045269  mov     ecx, 1921h
0x14004526e  mov     dword ptr [rsp+0F8h+var_C8], r9d
0x140045273  mov     dword ptr [rsp+0F8h+var_D0], eax; char
0x140045277  lea     rax, aVhdmpiscsicomm_47; "VhdmpiScsiCommandWriteUsingToken: buffe"...
0x14004527e  mov     r9d, edx; int
0x140045281  mov     [rsp+0F8h+var_D8], rax; char *
0x140045286  mov     edx, ecx; int
0x140045288  mov     r8d, r14d; int
0x14004528b  lea     rcx, aVhdmpiscsicomm_10; "VhdmpiScsiCommandWriteUsingToken"
0x140045292  call    TraceEvents
0x140045297  mov     bpl, 12h
0x14004529a  jmp     loc_1400459FF
0x14004529f  mov     r10d, 218h
0x1400452a5  cmp     r9d, r10d
0x1400452a8  jnb     short loc_1400452E2
0x1400452aa  mov     eax, cs:dword_1400876D0
0x1400452b0  cmp     eax, r14d
0x1400452b3  jbe     short loc_140045297
0x1400452b5  mov     edx, 20h ; ' '
0x1400452ba  lea     rcx, dword_1400876D0
0x1400452c1  call    _tlgKeywordOn
0x1400452c6  test    al, al
0x1400452c8  jz      short loc_140045297
0x1400452ca  mov     dword ptr [rsp+0F8h+var_C8], r10d
0x1400452cf  lea     rax, aVhdmpiscsicomm_33; "VhdmpiScsiCommandWriteUsingToken: Param"...
0x1400452d6  mov     dword ptr [rsp+0F8h+var_D0], r9d
0x1400452db  mov     ecx, 192Fh
0x1400452e0  jmp     short loc_14004527E
0x1400452e2  mov     rbx, [rdx+8]
0x1400452e6  mov     ebp, 226h
0x1400452eb  movzx   eax, word ptr [rbx]
0x1400452ee  ror     ax, 8
0x1400452f2  movzx   r8d, ax
0x1400452f6  cmp     r8d, ebp
0x1400452f9  jnb     loc_140045380
0x1400452ff  mov     eax, cs:dword_1400876D0
0x140045305  cmp     eax, r14d
0x140045308  jbe     short loc_14004534D
0x14004530a  mov     edx, 20h ; ' '
0x14004530f  lea     rcx, dword_1400876D0
0x140045316  call    _tlgKeywordOn
0x14004531b  test    al, al
0x14004531d  jz      short loc_14004534D
0x14004531f  mov     ecx, 194Ah
0x140045324  mov     dword ptr [rsp+0F8h+var_C8], ebp
0x140045328  lea     rax, aVhdmpiscsicomm_19; "VhdmpiScsiCommandWriteUsingToken: Write"...
0x14004532f  mov     dword ptr [rsp+0F8h+var_D0], r8d; char
0x140045334  mov     r9d, edx; int
0x140045337  mov     edx, ecx; int
0x140045339  mov     [rsp+0F8h+var_D8], rax; char *
0x14004533e  lea     rcx, aVhdmpiscsicomm_10; "VhdmpiScsiCommandWriteUsingToken"
0x140045345  mov     r8d, r14d; int
0x140045348  call    TraceEvents
0x14004534d  mov     [rsi+25h], r14b
0x140045351  xor     eax, eax
0x140045353  xorps   xmm0, xmm0
0x140045356  mov     ebp, 4
0x14004535b  movups  xmmword ptr [rsi+2Ah], xmm0
0x14004535f  mov     [rsi+3Ah], ax
0x140045363  mov     word ptr [rsi+29h], 7001h
0x140045369  mov     al, [rsi+2Ch]
0x14004536c  and     al, 0F5h
0x14004536e  or      al, 5
0x140045370  mov     [rsi+2Ch], al
0x140045373  mov     byte ptr [rsi+31h], 0Ah
0x140045377  mov     byte ptr [rsi+36h], 26h ; '&'
0x14004537b  jmp     loc_1400459FF
0x140045380  lea     rax, [r14+r8]
0x140045384  cmp     rax, r9
0x140045387  jbe     short loc_1400453CC
0x140045389  mov     eax, cs:dword_1400876D0
0x14004538f  cmp     eax, r14d
0x140045392  jbe     loc_140045297
0x140045398  mov     edx, 20h ; ' '
0x14004539d  lea     rcx, dword_1400876D0
0x1400453a4  call    _tlgKeywordOn
0x1400453a9  test    al, al
0x1400453ab  jz      loc_140045297
0x1400453b1  mov     dword ptr [rsp+0F8h+var_C8], r9d
0x1400453b6  lea     rax, aVhdmpiscsicomm_18; "VhdmpiScsiCommandWriteUsingToken: Write"...
0x1400453bd  mov     dword ptr [rsp+0F8h+var_D0], r8d
0x1400453c2  mov     ecx, 195Eh
0x1400453c7  jmp     loc_14004527E
0x1400453cc  movzx   eax, word ptr [rbx+216h]
0x1400453d3  ror     ax, 8
0x1400453d7  movzx   r8d, ax
0x1400453db  lea     rax, [r10+r8]
0x1400453df  cmp     rax, r9
0x1400453e2  jbe     short loc_140045427
0x1400453e4  mov     eax, cs:dword_1400876D0
0x1400453ea  cmp     eax, r14d
0x1400453ed  jbe     loc_140045297
0x1400453f3  mov     edx, 20h ; ' '
0x1400453f8  lea     rcx, dword_1400876D0
0x1400453ff  call    _tlgKeywordOn
0x140045404  test    al, al
0x140045406  jz      loc_140045297
0x14004540c  mov     dword ptr [rsp+0F8h+var_C8], r9d
0x140045411  lea     rax, aVhdmpiscsicomm_36; "VhdmpiScsiCommandWriteUsingToken: Block"...
0x140045418  mov     dword ptr [rsp+0F8h+var_D0], r8d
0x14004541d  mov     ecx, 1970h
0x140045422  jmp     loc_14004527E
0x140045427  cmp     r8d, 10h
0x14004542b  jnb     short loc_14004546E
0x14004542d  mov     eax, cs:dword_1400876D0
0x140045433  cmp     eax, r14d
0x140045436  jbe     loc_14004534D
0x14004543c  mov     edx, 20h ; ' '
0x140045441  lea     rcx, dword_1400876D0
0x140045448  call    _tlgKeywordOn
0x14004544d  test    al, al
0x14004544f  jz      loc_14004534D
0x140045455  mov     ecx, 197Dh
0x14004545a  mov     dword ptr [rsp+0F8h+var_C8], 10h
0x140045462  lea     rax, aVhdmpiscsicomm_8; "VhdmpiScsiCommandWriteUsingToken: Block"...
0x140045469  jmp     loc_14004532F
0x14004546e  shr     r8d, 4
0x140045472  cmp     r8d, 8
0x140045476  jbe     loc_1400454FF
0x14004547c  mov     eax, cs:dword_1400876D0
0x140045482  cmp     eax, r14d
0x140045485  jbe     short loc_1400454CE
0x140045487  mov     edx, 20h ; ' '
0x14004548c  lea     rcx, dword_1400876D0
0x140045493  call    _tlgKeywordOn
0x140045498  test    al, al
0x14004549a  jz      short loc_1400454CE
0x14004549c  mov     ecx, 1992h
0x1400454a1  mov     dword ptr [rsp+0F8h+var_C8], 8
0x1400454a9  mov     dword ptr [rsp+0F8h+var_D0], r8d; char
0x1400454ae  lea     rax, aVhdmpiscsicomm_11; "VhdmpiScsiCommandWriteUsingToken: Range"...
0x1400454b5  mov     r9d, edx; int
0x1400454b8  mov     [rsp+0F8h+var_D8], rax; char *
0x1400454bd  mov     edx, ecx; int
0x1400454bf  mov     r8d, r14d; int
0x1400454c2  lea     rcx, aVhdmpiscsicomm_10; "VhdmpiScsiCommandWriteUsingToken"
0x1400454c9  call    TraceEvents
0x1400454ce  mov     [rsi+25h], r14b
0x1400454d2  xor     eax, eax
0x1400454d4  xorps   xmm0, xmm0
0x1400454d7  mov     bpl, 6
0x1400454da  movups  xmmword ptr [rsi+2Ah], xmm0
0x1400454de  mov     [rsi+3Ah], ax
0x1400454e2  mov     word ptr [rsi+29h], 7001h
0x1400454e8  mov     al, [rsi+2Ch]
0x1400454eb  and     al, 0F5h
0x1400454ed  mov     byte ptr [rsi+31h], 0Ah
0x1400454f1  or      al, 5
0x1400454f3  mov     byte ptr [rsi+36h], 26h ; '&'
0x1400454f7  mov     [rsi+2Ch], al
0x1400454fa  jmp     loc_1400459FF
0x1400454ff  test    byte ptr [rbx+2], 1
0x140045503  jz      short loc_140045554
0x140045505  mov     eax, cs:dword_1400876D0
0x14004550b  cmp     eax, r14d
0x14004550e  jbe     short loc_14004554A
0x140045510  mov     edx, 20h ; ' '
0x140045515  lea     rcx, dword_1400876D0
0x14004551c  call    _tlgKeywordOn
0x140045521  test    al, al
0x140045523  jz      short loc_14004554A
0x140045525  mov     ecx, 19A9h
0x14004552a  lea     rax, aVhdmpiscsicomm_5; "VhdmpiScsiCommandWriteUsingToken: Popul"...
0x140045531  mov     r9d, edx; int
0x140045534  mov     [rsp+0F8h+var_D8], rax; char *
0x140045539  mov     edx, ecx; int
0x14004553b  mov     r8d, r14d; int
0x14004553e  lea     rcx, aVhdmpiscsicomm_10; "VhdmpiScsiCommandWriteUsingToken"
0x140045545  call    TraceEvents
0x14004554a  mov     ebp, 4
0x14004554f  jmp     loc_1400459FF
0x140045554  mov     r13d, [rbx+220h]
0x14004555b  mov     edx, 1
0x140045560  mov     r10, [rbx+218h]
0x140045567  bswap   r10
0x14004556a  mov     [rsp+0F8h+var_50], r10
0x140045572  bswap   r13d
0x140045575  mov     r13d, r13d
0x140045578  cmp     r8d, edx
0x14004557b  jbe     short loc_1400455AD
0x14004557d  mov     r9d, edx
0x140045580  lea     rax, [r10+r13]
0x140045584  add     r9, r9
0x140045587  mov     rcx, [rbx+r9*8+218h]
0x14004558f  bswap   rcx
0x140045592  cmp     rax, rcx
0x140045595  jnz     short loc_1400455AD
0x140045597  mov     eax, [rbx+r9*8+220h]
0x14004559f  inc     edx
0x1400455a1  bswap   eax
0x1400455a3  mov     eax, eax
0x1400455a5  add     r13, rax
0x1400455a8  cmp     edx, r8d
0x1400455ab  jb      short loc_14004557D
0x1400455ad  mov     [rsp+0F8h+var_70], r13
0x1400455b5  mov     r9, r13
0x1400455b8  cmp     edx, r8d
0x1400455bb  jnb     short loc_1400455DF
0x1400455bd  mov     eax, edx
0x1400455bf  inc     edx
0x1400455c1  add     rax, rax
0x1400455c4  mov     eax, [rbx+rax*8+220h]
0x1400455cb  bswap   eax
0x1400455cd  mov     eax, eax
0x1400455cf  add     r9, rax
0x1400455d2  cmp     edx, r8d
0x1400455d5  jb      short loc_1400455BD
0x1400455d7  mov     [rsp+0F8h+var_70], r9
0x1400455df  mov     r15d, [r11+40h]
0x1400455e3  mov     edx, 4000000h
0x1400455e8  mov     ecx, r15d
0x1400455eb  mov     [rsp+0F8h+var_78], rdx
0x1400455f3  mov     rax, r13
0x1400455f6  shl     rax, cl
0x1400455f9  cmp     rax, rdx
0x1400455fc  ja      short loc_140045647
0x1400455fe  mov     [rsp+0F8h+var_78], rax
0x140045606  mov     rdx, rax
0x140045609  test    rax, rax
0x14004560c  jnz     short loc_140045647
0x14004560e  mov     eax, cs:dword_1400876D0
0x140045614  cmp     eax, r14d
0x140045617  jbe     loc_14004554A
0x14004561d  mov     edx, 20h ; ' '
0x140045622  lea     rcx, dword_1400876D0
0x140045629  call    _tlgKeywordOn
0x14004562e  test    al, al
0x140045630  jz      loc_14004554A
0x140045636  mov     ecx, 19F2h
0x14004563b  lea     rax, aVhdmpiscsicomm_35; "VhdmpiScsiCommandWriteUsingToken: Range"...
0x140045642  jmp     loc_140045531
0x140045647  mov     r8d, edx; unsigned int
0x14004564a  mov     rax, r10
0x14004564d  shl     rax, cl
0x140045650  mov     rdx, rsi; struct VHD_SCSI_REQUEST *
0x140045653  mov     r9, rax; unsigned __int64
0x140045656  mov     [rsp+0F8h+var_68], rax
0x14004565e  mov     rcx, r11; struct VHD_SCSI_STATE *
0x140045661  call    ?VhdmpiValidateReadWriteScsiParameters@@YAEPEAUVHD_SCSI_STATE@@PEAUVHD_SCSI_REQUEST@@K_K@Z; VhdmpiValidateReadWriteScsiParameters(VHD_SCSI_STATE *,VHD_SCSI_REQUEST *,ulong,unsigned __int64)
0x140045666  mov     bpl, al
0x140045669  cmp     al, 1
0x14004566b  jnz     loc_1400459FF
0x140045671  lea     r8, [rsp+0F8h+P]; struct _VHD_OFFLOAD_OP **
  ... truncated ...
```
