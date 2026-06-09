# VhdmpiScsiCommandWriteUsingToken(VHD_SCSI_STATE *,VHD_SCSI_REQUEST *,VHD_SCSI_ACTION *)

- ea: `0x140044d98`
- end: `0x14004562e`
- name: `?VhdmpiScsiCommandWriteUsingToken@@YAEPEAUVHD_SCSI_STATE@@PEAUVHD_SCSI_REQUEST@@PEAUVHD_SCSI_ACTION@@@Z`
- size: `2198`
- prototype: `unsigned __int8 __fastcall(struct VHD_SCSI_STATE *, struct VHD_SCSI_REQUEST *, struct VHD_SCSI_ACTION *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400439e0`

## callees

- `0x1400144a0`
- `0x140023560`
- `0x140035e94`
- `0x140042de4`
- `0x1400433ec`
- `0x140044d98`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140045603`
- `ntoskrnl!ExFreePoolWithTag` at `0x140045603`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400453ca`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400453ca`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400453f4`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400453f4`

## string_xrefs

- `0x140044e29`: `VhdmpiScsiCommandWriteUsingToken: PARAMETER LIST LENGTH of zero not considered an error`
- `0x140044e37`: `VhdmpiScsiCommandWriteUsingToken`
- `0x140044e9b`: `VhdmpiScsiCommandWriteUsingToken`
- `0x140044f4e`: `VhdmpiScsiCommandWriteUsingToken`
- `0x1400450d2`: `VhdmpiScsiCommandWriteUsingToken`
- `0x14004514e`: `VhdmpiScsiCommandWriteUsingToken`
- `0x1400452ce`: `VhdmpiScsiCommandWriteUsingToken`
- `0x140045447`: `VhdmpiScsiCommandWriteUsingToken`
- `0x1400454c1`: `VhdmpiScsiCommandWriteUsingToken`
- `0x14004556e`: `VhdmpiScsiCommandWriteUsingToken`
- `0x140044e87`: `VhdmpiScsiCommandWriteUsingToken: buffer too small relative to PARAMETER LIST LENGTH (%u < %u)`
- `0x1400452ba`: `VhdmpiScsiCommandWriteUsingToken: VhdmpiAllocateAndInitializeOffloadOp() failed - setting UpperSrbStatus to SRB_STATUS_ERROR`
- `0x140045433`: `VhdmpiScsiCommandWriteUsingToken: VhdmpiOffloadTableInsertLocked returned STATUS_DUPLICATE_OBJECTID`
- `0x1400454ad`: `VhdmpiScsiCommandWriteUsingToken: VhdmpiOffloadTableInsertLocked returned STATUS_INSUFFICIENT_RESOURCES`
- `0x1400455ab`: `Offload Write start (ScsiState:%p, Request:%p TransactionId:%d TokenOffset: %#016I64x) : LBA: start %#016I64x, length %#016I64x, total %#016I64x BYTE: offset: %#016I64x length: %#016I64x, total: %#016I64x`
- `0x140045072`: `VhdmpiScsiCommandWriteUsingToken: BlockDeviceRangeDescriptorListLength too small (%u < %u)`
- `0x1400450be`: `VhdmpiScsiCommandWriteUsingToken: RangeListCount too large (%u > %u)`
- `0x14004513a`: `VhdmpiScsiCommandWriteUsingToken: PopulateTokenHeader->Immediate != 0 --- this is not supported`
- `0x14004524b`: `VhdmpiScsiCommandWriteUsingToken: RangeByteLength == 0, setting UpperSrbStatus to SRB_STATUS_ERROR`
- `0x140044edf`: `VhdmpiScsiCommandWriteUsingToken: ParameterListLength non-zero, but too small (%u < %u)`
- `0x140044f38`: `VhdmpiScsiCommandWriteUsingToken: WriteUsingTokenDataLength too small (%u < %u)`
- `0x140044fc6`: `VhdmpiScsiCommandWriteUsingToken: WriteUsingTokenDataLength too large (%u + 2 > %u)`
- `0x140045021`: `VhdmpiScsiCommandWriteUsingToken: BlockDeviceRangeDescriptorListLength too large (%u + 16 > %u)`

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
    if ( (unsigned int)dword_140087708 > 5 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 32) )
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
    if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 32) )
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
    if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 32) )
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
    if ( (unsigned int)dword_140087708 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140087708, 32) )
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
    if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 32) )
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
    if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 32) )
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
    if ( (unsigned int)dword_140087708 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140087708, 32) )
      goto LABEL_20;
    v17 = 6525;
    v60 = 16;
    v18 = "VhdmpiScsiCommandWriteUsingToken: BlockDeviceRangeDescriptorListLength too small (%u < %u)";
    goto LABEL_19;
  }
  v26 = (unsigned int)v22 >> 4;
  if ( v26 > 8 )
  {
    if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 32) )
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
    if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 32) )
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
      if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 32) )
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
        if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 32) )
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
        if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 32) )
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
        if ( (unsigned int)dword_140087708 <= 5 )
        {
          v57 = v61;
          v58 = v63;
        }
        else
        {
          v57 = v61;
          v58 = v63;
          if ( (unsigned __int8)tlgKeywordOn(&dword_140087708, 32) )
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
      if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 32) )
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
0x140044d98  mov     rax, rsp
0x140044d9b  mov     [rax+18h], rbx
0x140044d9f  mov     [rax+8], rcx
0x140044da3  push    rbp
0x140044da4  push    rsi
0x140044da5  push    rdi
0x140044da6  push    r12
0x140044da8  push    r13
0x140044daa  push    r14
0x140044dac  push    r15
0x140044dae  sub     rsp, 0C0h
0x140044db5  mov     rdi, [rdx]
0x140044db8  mov     r12, r8
0x140044dbb  mov     qword ptr [rax+20h], 0
0x140044dc3  mov     rsi, rdx
0x140044dc6  mov     r11, rcx
0x140044dc9  mov     al, [rdi+0Ah]
0x140044dcc  mov     byte ptr [rsp+0F8h+arg_8+3], al
0x140044dd3  mov     al, [rdi+0Bh]
0x140044dd6  mov     byte ptr [rsp+0F8h+arg_8+2], al
0x140044ddd  mov     al, [rdi+0Ch]
0x140044de0  mov     byte ptr [rsp+0F8h+arg_8+1], al
0x140044de7  mov     al, [rdi+0Dh]
0x140044dea  mov     byte ptr [rsp+0F8h+arg_8], al
0x140044df1  mov     r9d, [rsp+0F8h+arg_8]
0x140044df9  test    r9d, r9d
0x140044dfc  jnz     short loc_140044E4B
0x140044dfe  mov     eax, cs:dword_140087708
0x140044e04  cmp     eax, 5
0x140044e07  jbe     short loc_140044E43
0x140044e09  lea     edx, [r9+20h]
0x140044e0d  lea     rcx, dword_140087708
0x140044e14  call    _tlgKeywordOn
0x140044e19  test    al, al
0x140044e1b  jz      short loc_140044E43
0x140044e1d  mov     ecx, 190Fh
0x140044e22  lea     r8d, [rdx-1Bh]; int
0x140044e26  mov     r9d, edx; int
0x140044e29  lea     rax, aVhdmpiscsicomm_40; "VhdmpiScsiCommandWriteUsingToken: PARAM"...
0x140044e30  mov     edx, ecx; int
0x140044e32  mov     [rsp+0F8h+var_D8], rax; char *
0x140044e37  lea     rcx, aVhdmpiscsicomm_10; "VhdmpiScsiCommandWriteUsingToken"
0x140044e3e  call    TraceEvents
0x140044e43  mov     bpl, 1
0x140044e46  jmp     loc_14004560F
0x140044e4b  mov     r14d, 2
0x140044e51  cmp     r9d, [rdx+10h]
0x140044e55  jbe     short loc_140044EAF
0x140044e57  mov     eax, cs:dword_140087708
0x140044e5d  cmp     eax, r14d
0x140044e60  jbe     short loc_140044EA7
0x140044e62  lea     edx, [r14+1Eh]
0x140044e66  lea     rcx, dword_140087708
0x140044e6d  call    _tlgKeywordOn
0x140044e72  test    al, al
0x140044e74  jz      short loc_140044EA7
0x140044e76  mov     eax, [rsi+10h]
0x140044e79  mov     ecx, 1921h
0x140044e7e  mov     dword ptr [rsp+0F8h+var_C8], r9d
0x140044e83  mov     dword ptr [rsp+0F8h+var_D0], eax; char
0x140044e87  lea     rax, aVhdmpiscsicomm_47; "VhdmpiScsiCommandWriteUsingToken: buffe"...
0x140044e8e  mov     r9d, edx; int
0x140044e91  mov     [rsp+0F8h+var_D8], rax; char *
0x140044e96  mov     edx, ecx; int
0x140044e98  mov     r8d, r14d; int
0x140044e9b  lea     rcx, aVhdmpiscsicomm_10; "VhdmpiScsiCommandWriteUsingToken"
0x140044ea2  call    TraceEvents
0x140044ea7  mov     bpl, 12h
0x140044eaa  jmp     loc_14004560F
0x140044eaf  mov     r10d, 218h
0x140044eb5  cmp     r9d, r10d
0x140044eb8  jnb     short loc_140044EF2
0x140044eba  mov     eax, cs:dword_140087708
0x140044ec0  cmp     eax, r14d
0x140044ec3  jbe     short loc_140044EA7
0x140044ec5  mov     edx, 20h ; ' '
0x140044eca  lea     rcx, dword_140087708
0x140044ed1  call    _tlgKeywordOn
0x140044ed6  test    al, al
0x140044ed8  jz      short loc_140044EA7
0x140044eda  mov     dword ptr [rsp+0F8h+var_C8], r10d
0x140044edf  lea     rax, aVhdmpiscsicomm_33; "VhdmpiScsiCommandWriteUsingToken: Param"...
0x140044ee6  mov     dword ptr [rsp+0F8h+var_D0], r9d
0x140044eeb  mov     ecx, 192Fh
0x140044ef0  jmp     short loc_140044E8E
0x140044ef2  mov     rbx, [rdx+8]
0x140044ef6  mov     ebp, 226h
0x140044efb  movzx   eax, word ptr [rbx]
0x140044efe  ror     ax, 8
0x140044f02  movzx   r8d, ax
0x140044f06  cmp     r8d, ebp
0x140044f09  jnb     loc_140044F90
0x140044f0f  mov     eax, cs:dword_140087708
0x140044f15  cmp     eax, r14d
0x140044f18  jbe     short loc_140044F5D
0x140044f1a  mov     edx, 20h ; ' '
0x140044f1f  lea     rcx, dword_140087708
0x140044f26  call    _tlgKeywordOn
0x140044f2b  test    al, al
0x140044f2d  jz      short loc_140044F5D
0x140044f2f  mov     ecx, 194Ah
0x140044f34  mov     dword ptr [rsp+0F8h+var_C8], ebp
0x140044f38  lea     rax, aVhdmpiscsicomm_19; "VhdmpiScsiCommandWriteUsingToken: Write"...
0x140044f3f  mov     dword ptr [rsp+0F8h+var_D0], r8d; char
0x140044f44  mov     r9d, edx; int
0x140044f47  mov     edx, ecx; int
0x140044f49  mov     [rsp+0F8h+var_D8], rax; char *
0x140044f4e  lea     rcx, aVhdmpiscsicomm_10; "VhdmpiScsiCommandWriteUsingToken"
0x140044f55  mov     r8d, r14d; int
0x140044f58  call    TraceEvents
0x140044f5d  mov     [rsi+25h], r14b
0x140044f61  xor     eax, eax
0x140044f63  xorps   xmm0, xmm0
0x140044f66  mov     ebp, 4
0x140044f6b  movups  xmmword ptr [rsi+2Ah], xmm0
0x140044f6f  mov     [rsi+3Ah], ax
0x140044f73  mov     word ptr [rsi+29h], 7001h
0x140044f79  mov     al, [rsi+2Ch]
0x140044f7c  and     al, 0F5h
0x140044f7e  or      al, 5
0x140044f80  mov     [rsi+2Ch], al
0x140044f83  mov     byte ptr [rsi+31h], 0Ah
0x140044f87  mov     byte ptr [rsi+36h], 26h ; '&'
0x140044f8b  jmp     loc_14004560F
0x140044f90  lea     rax, [r14+r8]
0x140044f94  cmp     rax, r9
0x140044f97  jbe     short loc_140044FDC
0x140044f99  mov     eax, cs:dword_140087708
0x140044f9f  cmp     eax, r14d
0x140044fa2  jbe     loc_140044EA7
0x140044fa8  mov     edx, 20h ; ' '
0x140044fad  lea     rcx, dword_140087708
0x140044fb4  call    _tlgKeywordOn
0x140044fb9  test    al, al
0x140044fbb  jz      loc_140044EA7
0x140044fc1  mov     dword ptr [rsp+0F8h+var_C8], r9d
0x140044fc6  lea     rax, aVhdmpiscsicomm_18; "VhdmpiScsiCommandWriteUsingToken: Write"...
0x140044fcd  mov     dword ptr [rsp+0F8h+var_D0], r8d
0x140044fd2  mov     ecx, 195Eh
0x140044fd7  jmp     loc_140044E8E
0x140044fdc  movzx   eax, word ptr [rbx+216h]
0x140044fe3  ror     ax, 8
0x140044fe7  movzx   r8d, ax
0x140044feb  lea     rax, [r10+r8]
0x140044fef  cmp     rax, r9
0x140044ff2  jbe     short loc_140045037
0x140044ff4  mov     eax, cs:dword_140087708
0x140044ffa  cmp     eax, r14d
0x140044ffd  jbe     loc_140044EA7
0x140045003  mov     edx, 20h ; ' '
0x140045008  lea     rcx, dword_140087708
0x14004500f  call    _tlgKeywordOn
0x140045014  test    al, al
0x140045016  jz      loc_140044EA7
0x14004501c  mov     dword ptr [rsp+0F8h+var_C8], r9d
0x140045021  lea     rax, aVhdmpiscsicomm_36; "VhdmpiScsiCommandWriteUsingToken: Block"...
0x140045028  mov     dword ptr [rsp+0F8h+var_D0], r8d
0x14004502d  mov     ecx, 1970h
0x140045032  jmp     loc_140044E8E
0x140045037  cmp     r8d, 10h
0x14004503b  jnb     short loc_14004507E
0x14004503d  mov     eax, cs:dword_140087708
0x140045043  cmp     eax, r14d
0x140045046  jbe     loc_140044F5D
0x14004504c  mov     edx, 20h ; ' '
0x140045051  lea     rcx, dword_140087708
0x140045058  call    _tlgKeywordOn
0x14004505d  test    al, al
0x14004505f  jz      loc_140044F5D
0x140045065  mov     ecx, 197Dh
0x14004506a  mov     dword ptr [rsp+0F8h+var_C8], 10h
0x140045072  lea     rax, aVhdmpiscsicomm_8; "VhdmpiScsiCommandWriteUsingToken: Block"...
0x140045079  jmp     loc_140044F3F
0x14004507e  shr     r8d, 4
0x140045082  cmp     r8d, 8
0x140045086  jbe     loc_14004510F
0x14004508c  mov     eax, cs:dword_140087708
0x140045092  cmp     eax, r14d
0x140045095  jbe     short loc_1400450DE
0x140045097  mov     edx, 20h ; ' '
0x14004509c  lea     rcx, dword_140087708
0x1400450a3  call    _tlgKeywordOn
0x1400450a8  test    al, al
0x1400450aa  jz      short loc_1400450DE
0x1400450ac  mov     ecx, 1992h
0x1400450b1  mov     dword ptr [rsp+0F8h+var_C8], 8
0x1400450b9  mov     dword ptr [rsp+0F8h+var_D0], r8d; char
0x1400450be  lea     rax, aVhdmpiscsicomm_11; "VhdmpiScsiCommandWriteUsingToken: Range"...
0x1400450c5  mov     r9d, edx; int
0x1400450c8  mov     [rsp+0F8h+var_D8], rax; char *
0x1400450cd  mov     edx, ecx; int
0x1400450cf  mov     r8d, r14d; int
0x1400450d2  lea     rcx, aVhdmpiscsicomm_10; "VhdmpiScsiCommandWriteUsingToken"
0x1400450d9  call    TraceEvents
0x1400450de  mov     [rsi+25h], r14b
0x1400450e2  xor     eax, eax
0x1400450e4  xorps   xmm0, xmm0
0x1400450e7  mov     bpl, 6
0x1400450ea  movups  xmmword ptr [rsi+2Ah], xmm0
0x1400450ee  mov     [rsi+3Ah], ax
0x1400450f2  mov     word ptr [rsi+29h], 7001h
0x1400450f8  mov     al, [rsi+2Ch]
0x1400450fb  and     al, 0F5h
0x1400450fd  mov     byte ptr [rsi+31h], 0Ah
0x140045101  or      al, 5
0x140045103  mov     byte ptr [rsi+36h], 26h ; '&'
0x140045107  mov     [rsi+2Ch], al
0x14004510a  jmp     loc_14004560F
0x14004510f  test    byte ptr [rbx+2], 1
0x140045113  jz      short loc_140045164
0x140045115  mov     eax, cs:dword_140087708
0x14004511b  cmp     eax, r14d
0x14004511e  jbe     short loc_14004515A
0x140045120  mov     edx, 20h ; ' '
0x140045125  lea     rcx, dword_140087708
0x14004512c  call    _tlgKeywordOn
0x140045131  test    al, al
0x140045133  jz      short loc_14004515A
0x140045135  mov     ecx, 19A9h
0x14004513a  lea     rax, aVhdmpiscsicomm_5; "VhdmpiScsiCommandWriteUsingToken: Popul"...
0x140045141  mov     r9d, edx; int
0x140045144  mov     [rsp+0F8h+var_D8], rax; char *
0x140045149  mov     edx, ecx; int
0x14004514b  mov     r8d, r14d; int
0x14004514e  lea     rcx, aVhdmpiscsicomm_10; "VhdmpiScsiCommandWriteUsingToken"
0x140045155  call    TraceEvents
0x14004515a  mov     ebp, 4
0x14004515f  jmp     loc_14004560F
0x140045164  mov     r13d, [rbx+220h]
0x14004516b  mov     edx, 1
0x140045170  mov     r10, [rbx+218h]
0x140045177  bswap   r10
0x14004517a  mov     [rsp+0F8h+var_50], r10
0x140045182  bswap   r13d
0x140045185  mov     r13d, r13d
0x140045188  cmp     r8d, edx
0x14004518b  jbe     short loc_1400451BD
0x14004518d  mov     r9d, edx
0x140045190  lea     rax, [r10+r13]
0x140045194  add     r9, r9
0x140045197  mov     rcx, [rbx+r9*8+218h]
0x14004519f  bswap   rcx
0x1400451a2  cmp     rax, rcx
0x1400451a5  jnz     short loc_1400451BD
0x1400451a7  mov     eax, [rbx+r9*8+220h]
0x1400451af  inc     edx
0x1400451b1  bswap   eax
0x1400451b3  mov     eax, eax
0x1400451b5  add     r13, rax
0x1400451b8  cmp     edx, r8d
0x1400451bb  jb      short loc_14004518D
0x1400451bd  mov     [rsp+0F8h+var_70], r13
0x1400451c5  mov     r9, r13
0x1400451c8  cmp     edx, r8d
0x1400451cb  jnb     short loc_1400451EF
0x1400451cd  mov     eax, edx
0x1400451cf  inc     edx
0x1400451d1  add     rax, rax
0x1400451d4  mov     eax, [rbx+rax*8+220h]
0x1400451db  bswap   eax
0x1400451dd  mov     eax, eax
0x1400451df  add     r9, rax
0x1400451e2  cmp     edx, r8d
0x1400451e5  jb      short loc_1400451CD
0x1400451e7  mov     [rsp+0F8h+var_70], r9
0x1400451ef  mov     r15d, [r11+40h]
0x1400451f3  mov     edx, 4000000h
0x1400451f8  mov     ecx, r15d
0x1400451fb  mov     [rsp+0F8h+var_78], rdx
0x140045203  mov     rax, r13
0x140045206  shl     rax, cl
0x140045209  cmp     rax, rdx
0x14004520c  ja      short loc_140045257
0x14004520e  mov     [rsp+0F8h+var_78], rax
0x140045216  mov     rdx, rax
0x140045219  test    rax, rax
0x14004521c  jnz     short loc_140045257
0x14004521e  mov     eax, cs:dword_140087708
0x140045224  cmp     eax, r14d
0x140045227  jbe     loc_14004515A
0x14004522d  mov     edx, 20h ; ' '
0x140045232  lea     rcx, dword_140087708
0x140045239  call    _tlgKeywordOn
0x14004523e  test    al, al
0x140045240  jz      loc_14004515A
0x140045246  mov     ecx, 19F2h
0x14004524b  lea     rax, aVhdmpiscsicomm_35; "VhdmpiScsiCommandWriteUsingToken: Range"...
0x140045252  jmp     loc_140045141
0x140045257  mov     r8d, edx; unsigned int
0x14004525a  mov     rax, r10
0x14004525d  shl     rax, cl
0x140045260  mov     rdx, rsi; struct VHD_SCSI_REQUEST *
0x140045263  mov     r9, rax; unsigned __int64
0x140045266  mov     [rsp+0F8h+var_68], rax
0x14004526e  mov     rcx, r11; struct VHD_SCSI_STATE *
0x140045271  call    ?VhdmpiValidateReadWriteScsiParameters@@YAEPEAUVHD_SCSI_STATE@@PEAUVHD_SCSI_REQUEST@@K_K@Z; VhdmpiValidateReadWriteScsiParameters(VHD_SCSI_STATE *,VHD_SCSI_REQUEST *,ulong,unsigned __int64)
0x140045276  mov     bpl, al
0x140045279  cmp     al, 1
0x14004527b  jnz     loc_14004560F
0x140045281  lea     r8, [rsp+0F8h+P]; struct _VHD_OFFLOAD_OP **
  ... truncated ...
```
