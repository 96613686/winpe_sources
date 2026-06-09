# VhdmpiScsiCommandPopulateToken(VHD_SCSI_STATE *,VHD_SCSI_REQUEST *,VHD_SCSI_ACTION *)

- ea: `0x140043e60`
- end: `0x1400445c4`
- name: `?VhdmpiScsiCommandPopulateToken@@YAEPEAUVHD_SCSI_STATE@@PEAUVHD_SCSI_REQUEST@@PEAUVHD_SCSI_ACTION@@@Z`
- size: `1892`
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
- `0x140043e60`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14004459a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004459a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004439b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004439b`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400443c1`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400443c1`

## string_xrefs

- `0x140043ef1`: `VhdmpiScsiCommandPopulateToken: PARAMETER LIST LENGTH of zero not considered an error`
- `0x140044558`: `Offload Read start (ScsiState:%p Request:%p TransactionId:%d) : LBA: start %#016I64x, length %#016I64x, total %#016I64x BYTE: offset: %#016I64x length: %#016I64x, total: %#016I64x`
- `0x1400441f0`: `VhdmpiScsiCommandPopulateToken: PopulateTokenHeader->Immediate != 0 --- this is not supported`
- `0x140044312`: `VhdmpiScsiCommandPopulateToken: VhdmpiAllocateAndInitializeOffloadOp() failed - setting UpperSrbStatus to SRB_STATUS_ERROR`
- `0x1400443ff`: `VhdmpiScsiCommandPopulateToken: VhdmpiOffloadTableInsertLocked returned STATUS_DUPLICATE_OBJECTID`
- `0x14004447a`: `VhdmpiScsiCommandPopulateToken: VhdmpiOffloadTableInsertLocked returned STATUS_INSUFFICIENT_RESOURCES`
- `0x140044082`: `VhdmpiScsiCommandPopulateToken: PopulateTokenDataLength too large (%u + 2 > %u)`
- `0x1400440da`: `VhdmpiScsiCommandPopulateToken: BlockDeviceRangeDescriptorListLength too large (%u + 16 > %u)`
- `0x14004412b`: `VhdmpiScsiCommandPopulateToken: BlockDeviceRangeDescriptorListLength too small (%u < %u)`
- `0x1400441b9`: `VhdmpiScsiCommandPopulateToken: RangeListCount too large (%u > %u)`
- `0x140043eff`: `VhdmpiScsiCommandPopulateToken`
- `0x140043f5f`: `VhdmpiScsiCommandPopulateToken`
- `0x14004400e`: `VhdmpiScsiCommandPopulateToken`
- `0x14004413f`: `VhdmpiScsiCommandPopulateToken`
- `0x140044204`: `VhdmpiScsiCommandPopulateToken`
- `0x140044326`: `VhdmpiScsiCommandPopulateToken`
- `0x140044413`: `VhdmpiScsiCommandPopulateToken`
- `0x14004448e`: `VhdmpiScsiCommandPopulateToken`
- `0x140044520`: `VhdmpiScsiCommandPopulateToken`
- `0x140043f4b`: `VhdmpiScsiCommandPopulateToken: buffer too small relative to PARAMETER LIST LENGTH (%u < %u)`
- `0x140043f9f`: `VhdmpiScsiCommandPopulateToken: ParameterListLength non-zero, but too small (%u < %u)`
- `0x140043ff8`: `VhdmpiScsiCommandPopulateToken: PopulateTokenDataLength too small (%u < %u)`

## pseudocode

```c
unsigned __int8 __fastcall VhdmpiScsiCommandPopulateToken(
        struct VHD_SCSI_STATE *a1,
        struct VHD_SCSI_REQUEST *a2,
        struct VHD_SCSI_ACTION *a3)
{
  _BYTE *v3; // rdi
  unsigned int v7; // edx
  unsigned __int8 v8; // bl
  unsigned int v9; // edx
  int v10; // r9d
  unsigned int v11; // edx
  int v12; // r9d
  __int64 v13; // r10
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
  unsigned int v26; // edx
  int v27; // r8d
  char v28; // al
  unsigned int v29; // r8d
  unsigned int v30; // edx
  unsigned int v31; // edx
  unsigned __int64 v32; // r11
  __int64 i; // r12
  __int64 v34; // r9
  __int64 v35; // r9
  __int64 v36; // rax
  int v37; // ecx
  __int64 v38; // r13
  struct VHD_SCSI_REQUEST *v39; // rdx
  unsigned int v40; // edx
  _BYTE *v41; // r14
  KIRQL v42; // bl
  unsigned int v43; // edx
  char v44; // al
  unsigned int v45; // edx
  char v46; // al
  char *v47; // rdi
  unsigned int v48; // edx
  unsigned __int64 v49; // rbx
  int v51; // [rsp+30h] [rbp-98h]
  __int64 v52; // [rsp+70h] [rbp-58h]
  unsigned __int64 v53; // [rsp+78h] [rbp-50h]
  __int64 v54; // [rsp+80h] [rbp-48h]
  unsigned __int64 v55; // [rsp+88h] [rbp-40h]
  unsigned int v57; // [rsp+D8h] [rbp+10h]
  int v58; // [rsp+D8h] [rbp+10h]
  int inserted; // [rsp+D8h] [rbp+10h]
  PVOID P; // [rsp+E8h] [rbp+20h] BYREF

  v3 = *(_BYTE **)a2;
  P = 0;
  HIBYTE(v57) = v3[10];
  BYTE2(v57) = v3[11];
  BYTE1(v57) = v3[12];
  LOBYTE(v57) = v3[13];
  if ( !v57 )
  {
    if ( (unsigned int)dword_140087708 > 5 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 32) )
      TraceEvents(
        "VhdmpiScsiCommandPopulateToken",
        0x177Bu,
        v7 - 27,
        v7,
        "VhdmpiScsiCommandPopulateToken: PARAMETER LIST LENGTH of zero not considered an error");
    return 1;
  }
  if ( v57 > *((_DWORD *)a2 + 4) )
  {
    if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 32) )
      TraceEvents(
        "VhdmpiScsiCommandPopulateToken",
        0x178Du,
        2u,
        v9,
        "VhdmpiScsiCommandPopulateToken: buffer too small relative to PARAMETER LIST LENGTH (%u < %u)",
        *((_DWORD *)a2 + 4),
        v10);
    return 18;
  }
  if ( v57 < 0x10 )
  {
    if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 32) )
      TraceEvents(
        "VhdmpiScsiCommandPopulateToken",
        0x179Bu,
        2u,
        v11,
        "VhdmpiScsiCommandPopulateToken: ParameterListLength non-zero, but too small (%u < %u)",
        v12,
        16);
    return 18;
  }
  v13 = *((_QWORD *)a2 + 1);
  v14 = (unsigned __int16)__ROR2__(*(_WORD *)v13, 8);
  if ( (unsigned int)v14 < 0x1E )
  {
    if ( (unsigned int)dword_140087708 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140087708, 32) )
      goto LABEL_20;
    v17 = 6070;
    v51 = 30;
    v18 = "VhdmpiScsiCommandPopulateToken: PopulateTokenDataLength too small (%u < %u)";
LABEL_19:
    TraceEvents("VhdmpiScsiCommandPopulateToken", v17, 2u, v15, v18, v16, v51);
LABEL_20:
    *((_BYTE *)a2 + 37) = 2;
    v8 = 4;
    *(_OWORD *)((char *)a2 + 42) = 0;
    *((_WORD *)a2 + 29) = 0;
    *(_WORD *)((char *)a2 + 41) = 28673;
    *((_BYTE *)a2 + 44) = *((_BYTE *)a2 + 44) & 0xF0 | 5;
    *((_BYTE *)a2 + 49) = 10;
    *((_BYTE *)a2 + 54) = 38;
    return v8;
  }
  if ( v14 + 2 > (unsigned __int64)v57 )
  {
    if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 32) )
      TraceEvents(
        "VhdmpiScsiCommandPopulateToken",
        0x17CAu,
        2u,
        v19,
        "VhdmpiScsiCommandPopulateToken: PopulateTokenDataLength too large (%u + 2 > %u)",
        v20,
        v21);
    return 18;
  }
  v22 = (unsigned __int16)__ROR2__(*(_WORD *)(v13 + 14), 8);
  if ( v22 + 16 > (unsigned __int64)v57 )
  {
    if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 32) )
      TraceEvents(
        "VhdmpiScsiCommandPopulateToken",
        0x17DCu,
        2u,
        v23,
        "VhdmpiScsiCommandPopulateToken: BlockDeviceRangeDescriptorListLength too large (%u + 16 > %u)",
        v24,
        v25);
    return 18;
  }
  if ( (unsigned int)v22 < 0x10 )
  {
    if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 32) )
      TraceEvents(
        "VhdmpiScsiCommandPopulateToken",
        0x17E8u,
        2u,
        v26,
        "VhdmpiScsiCommandPopulateToken: BlockDeviceRangeDescriptorListLength too small (%u < %u)",
        v27,
        16);
    *((_BYTE *)a2 + 37) = 2;
    *(_OWORD *)((char *)a2 + 42) = 0;
    *((_WORD *)a2 + 29) = 0;
    *(_WORD *)((char *)a2 + 41) = 28673;
    v28 = *((_BYTE *)a2 + 44) & 0xF5;
    *((_BYTE *)a2 + 49) = 10;
    *((_BYTE *)a2 + 54) = 38;
    *((_BYTE *)a2 + 44) = v28 | 5;
    return 4;
  }
  v29 = (unsigned int)v22 >> 4;
  if ( v29 > 8 )
  {
    if ( (unsigned int)dword_140087708 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140087708, 32) )
      goto LABEL_20;
    v17 = 6140;
    v51 = 8;
    v18 = "VhdmpiScsiCommandPopulateToken: RangeListCount too large (%u > %u)";
    goto LABEL_19;
  }
  if ( (*(_BYTE *)(v13 + 2) & 1) != 0 )
  {
    if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 32) )
      TraceEvents(
        "VhdmpiScsiCommandPopulateToken",
        0x1814u,
        2u,
        v30,
        "VhdmpiScsiCommandPopulateToken: PopulateTokenHeader->Immediate != 0 --- this is not supported");
    return 4;
  }
  v31 = 1;
  v32 = _byteswap_uint64(*(_QWORD *)(v13 + 16));
  v55 = v32;
  for ( i = _byteswap_ulong(*(_DWORD *)(v13 + 24)); v31 < v29; i += _byteswap_ulong(*(_DWORD *)(v13 + 8 * v34 + 24)) )
  {
    v34 = 2LL * v31;
    if ( i + v32 != _byteswap_uint64(*(_QWORD *)(v13 + 16LL * v31 + 16)) )
      break;
    ++v31;
  }
  v52 = i;
  v35 = i;
  if ( v31 < v29 )
  {
    do
    {
      v36 = v31++;
      v35 += _byteswap_ulong(*(_DWORD *)(v13 + 16 * v36 + 24));
    }
    while ( v31 < v29 );
    v52 = v35;
  }
  v37 = *((_DWORD *)a1 + 16);
  v38 = 0x4000000;
  v58 = *((_DWORD *)a1 + 16);
  if ( (unsigned __int64)(i << v37) <= 0x4000000 )
  {
    v38 = i << v37;
    if ( !(i << v37) )
      return 1;
  }
  v53 = v32 << v37;
  v8 = VhdmpiValidateReadWriteScsiParameters(a1, a2, v38, v32 << v37);
  if ( v8 == 1 )
  {
    if ( (int)VhdmpiAllocateAndInitializeOffloadOp(a1, v39, (struct _VHD_OFFLOAD_OP **)&P) >= 0 )
    {
      v41 = P;
      *((_BYTE *)P + 51) = v3[6];
      v41[50] = v3[7];
      v41[49] = v3[8];
      v41[48] = v3[9];
      *((_DWORD *)v41 + 14) = 0;
      *((_QWORD *)v41 + 14) = v52 << v58;
      v54 = v52 << v58;
      *((_DWORD *)a2 + 6) = 2;
      *((_QWORD *)a2 + 10) = v41;
      v42 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)a1 + 10);
      inserted = VhdmpiOffloadTableInsertLocked(a1, (struct _VHD_OFFLOAD_OP *)v41);
      KeReleaseSpinLock((PKSPIN_LOCK)a1 + 10, v42);
      if ( inserted == -1073741270 )
      {
        if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 32) )
          TraceEvents(
            "VhdmpiScsiCommandPopulateToken",
            0x1892u,
            2u,
            v43,
            "VhdmpiScsiCommandPopulateToken: VhdmpiOffloadTableInsertLocked returned STATUS_DUPLICATE_OBJECTID");
        *((_BYTE *)a2 + 37) = 2;
        v8 = 4;
        *(_OWORD *)((char *)a2 + 42) = 0;
        *((_WORD *)a2 + 29) = 0;
        *(_WORD *)((char *)a2 + 41) = 28673;
        v44 = *((_BYTE *)a2 + 44) & 0xF5;
        *((_BYTE *)a2 + 49) = 10;
        *((_BYTE *)a2 + 55) = 22;
        *((_BYTE *)a2 + 44) = v44 | 5;
      }
      else if ( inserted == -1073741670 )
      {
        if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 32) )
          TraceEvents(
            "VhdmpiScsiCommandPopulateToken",
            0x18A0u,
            2u,
            v45,
            "VhdmpiScsiCommandPopulateToken: VhdmpiOffloadTableInsertLocked returned STATUS_INSUFFICIENT_RESOURCES");
        *((_BYTE *)a2 + 37) = 2;
        v8 = 4;
        *(_OWORD *)((char *)a2 + 42) = 0;
        *((_WORD *)a2 + 29) = 0;
        *(_WORD *)((char *)a2 + 41) = 28673;
        v46 = *((_BYTE *)a2 + 44) & 0xFB;
        *((_BYTE *)a2 + 49) = 10;
        *((_WORD *)a2 + 27) = 853;
        *((_BYTE *)a2 + 44) = v46 | 0xB;
      }
      else
      {
        v47 = v41 + 128;
        if ( (unsigned int)dword_140087708 <= 5 )
        {
          v49 = v53;
        }
        else
        {
          v49 = v53;
          if ( (unsigned __int8)tlgKeywordOn(&dword_140087708, 32) )
            TraceEvents(
              "VhdmpiScsiCommandPopulateToken",
              0x18B7u,
              v48 - 27,
              v48,
              "Offload Read start (ScsiState:%p Request:%p TransactionId:%d) : LBA: start %#016I64x, length %#016I64x, to"
              "tal %#016I64x BYTE: offset: %#016I64x length: %#016I64x, total: %#016I64x",
              a1,
              a2,
              *((_DWORD *)v41 + 12),
              v55,
              i,
              v52,
              v53,
              v38,
              v54);
        }
        v41 = 0;
        *(_QWORD *)a3 = v49;
        *((_DWORD *)a3 + 3) = 0;
        v8 = 0;
        *((_QWORD *)a3 + 6) = 0;
        *((_DWORD *)a3 + 4) = 5;
        *((_DWORD *)a3 + 2) = v38;
        *((_QWORD *)a3 + 5) = v47;
      }
    }
    else
    {
      if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 32) )
        TraceEvents(
          "VhdmpiScsiCommandPopulateToken",
          0x187Cu,
          2u,
          v40,
          "VhdmpiScsiCommandPopulateToken: VhdmpiAllocateAndInitializeOffloadOp() failed - setting UpperSrbStatus to SRB_STATUS_ERROR");
      v41 = P;
      v8 = 4;
    }
    if ( v41 )
      ExFreePoolWithTag(v41, 0);
  }
  return v8;
}

```

## disassembly

```asm
0x140043e60  mov     rax, rsp
0x140043e63  mov     [rax+18h], rbx
0x140043e67  mov     [rax+8], rcx
0x140043e6b  push    rbp
0x140043e6c  push    rsi
0x140043e6d  push    rdi
0x140043e6e  push    r12
0x140043e70  push    r13
0x140043e72  push    r14
0x140043e74  push    r15
0x140043e76  sub     rsp, 90h
0x140043e7d  mov     rdi, [rdx]
0x140043e80  mov     r15, r8
0x140043e83  mov     qword ptr [rax+20h], 0
0x140043e8b  mov     rsi, rdx
0x140043e8e  mov     r14, rcx
0x140043e91  mov     al, [rdi+0Ah]
0x140043e94  mov     byte ptr [rsp+0C8h+arg_8+3], al
0x140043e9b  mov     al, [rdi+0Bh]
0x140043e9e  mov     byte ptr [rsp+0C8h+arg_8+2], al
0x140043ea5  mov     al, [rdi+0Ch]
0x140043ea8  mov     byte ptr [rsp+0C8h+arg_8+1], al
0x140043eaf  mov     al, [rdi+0Dh]
0x140043eb2  mov     byte ptr [rsp+0C8h+arg_8], al
0x140043eb9  mov     r9d, [rsp+0C8h+arg_8]
0x140043ec1  test    r9d, r9d
0x140043ec4  jnz     short loc_140043F12
0x140043ec6  mov     eax, cs:dword_140087708
0x140043ecc  cmp     eax, 5
0x140043ecf  jbe     short loc_140043F0B
0x140043ed1  lea     edx, [r9+20h]
0x140043ed5  lea     rcx, dword_140087708
0x140043edc  call    _tlgKeywordOn
0x140043ee1  test    al, al
0x140043ee3  jz      short loc_140043F0B
0x140043ee5  mov     ecx, 177Bh
0x140043eea  lea     r8d, [rdx-1Bh]; int
0x140043eee  mov     r9d, edx; int
0x140043ef1  lea     rax, aVhdmpiscsicomm_45; "VhdmpiScsiCommandPopulateToken: PARAMET"...
0x140043ef8  mov     edx, ecx; int
0x140043efa  mov     [rsp+0C8h+var_A8], rax; char *
0x140043eff  lea     rcx, aVhdmpiscsicomm_46; "VhdmpiScsiCommandPopulateToken"
0x140043f06  call    TraceEvents
0x140043f0b  mov     bl, 1
0x140043f0d  jmp     loc_1400445A6
0x140043f12  mov     ebp, 2
0x140043f17  cmp     r9d, [rdx+10h]
0x140043f1b  jbe     short loc_140043F72
0x140043f1d  mov     eax, cs:dword_140087708
0x140043f23  cmp     eax, ebp
0x140043f25  jbe     short loc_140043F6B
0x140043f27  lea     edx, [rbp+1Eh]
0x140043f2a  lea     rcx, dword_140087708
0x140043f31  call    _tlgKeywordOn
0x140043f36  test    al, al
0x140043f38  jz      short loc_140043F6B
0x140043f3a  mov     eax, [rsi+10h]
0x140043f3d  mov     ecx, 178Dh
0x140043f42  mov     dword ptr [rsp+0C8h+var_98], r9d
0x140043f47  mov     dword ptr [rsp+0C8h+var_A0], eax; char
0x140043f4b  lea     rax, aVhdmpiscsicomm_13; "VhdmpiScsiCommandPopulateToken: buffer "...
0x140043f52  mov     r9d, edx; int
0x140043f55  mov     [rsp+0C8h+var_A8], rax; char *
0x140043f5a  mov     edx, ecx; int
0x140043f5c  mov     r8d, ebp; int
0x140043f5f  lea     rcx, aVhdmpiscsicomm_46; "VhdmpiScsiCommandPopulateToken"
0x140043f66  call    TraceEvents
0x140043f6b  mov     bl, 12h
0x140043f6d  jmp     loc_1400445A6
0x140043f72  cmp     r9d, 10h
0x140043f76  jnb     short loc_140043FB2
0x140043f78  mov     eax, cs:dword_140087708
0x140043f7e  cmp     eax, ebp
0x140043f80  jbe     short loc_140043F6B
0x140043f82  mov     edx, 20h ; ' '
0x140043f87  lea     rcx, dword_140087708
0x140043f8e  call    _tlgKeywordOn
0x140043f93  test    al, al
0x140043f95  jz      short loc_140043F6B
0x140043f97  mov     dword ptr [rsp+0C8h+var_98], 10h
0x140043f9f  lea     rax, aVhdmpiscsicomm_42; "VhdmpiScsiCommandPopulateToken: Paramet"...
0x140043fa6  mov     dword ptr [rsp+0C8h+var_A0], r9d
0x140043fab  mov     ecx, 179Bh
0x140043fb0  jmp     short loc_140043F52
0x140043fb2  mov     r10, [rdx+8]
0x140043fb6  movzx   eax, word ptr [r10]
0x140043fba  ror     ax, 8
0x140043fbe  movzx   r8d, ax
0x140043fc2  cmp     r8d, 1Eh
0x140043fc6  jnb     loc_14004404D
0x140043fcc  mov     eax, cs:dword_140087708
0x140043fd2  cmp     eax, ebp
0x140043fd4  jbe     short loc_14004401D
0x140043fd6  mov     edx, 20h ; ' '
0x140043fdb  lea     rcx, dword_140087708
0x140043fe2  call    _tlgKeywordOn
0x140043fe7  test    al, al
0x140043fe9  jz      short loc_14004401D
0x140043feb  mov     ecx, 17B6h
0x140043ff0  mov     dword ptr [rsp+0C8h+var_98], 1Eh
0x140043ff8  lea     rax, aVhdmpiscsicomm_9; "VhdmpiScsiCommandPopulateToken: Populat"...
0x140043fff  mov     dword ptr [rsp+0C8h+var_A0], r8d; char
0x140044004  mov     r9d, edx; int
0x140044007  mov     edx, ecx; int
0x140044009  mov     [rsp+0C8h+var_A8], rax; char *
0x14004400e  lea     rcx, aVhdmpiscsicomm_46; "VhdmpiScsiCommandPopulateToken"
0x140044015  mov     r8d, ebp; int
0x140044018  call    TraceEvents
0x14004401d  mov     [rsi+25h], bpl
0x140044021  xor     eax, eax
0x140044023  xorps   xmm0, xmm0
0x140044026  mov     bl, 4
0x140044028  movups  xmmword ptr [rsi+2Ah], xmm0
0x14004402c  mov     [rsi+3Ah], ax
0x140044030  mov     word ptr [rsi+29h], 7001h
0x140044036  mov     al, [rsi+2Ch]
0x140044039  and     al, 0F5h
0x14004403b  or      al, 5
0x14004403d  mov     [rsi+2Ch], al
0x140044040  mov     byte ptr [rsi+31h], 0Ah
0x140044044  mov     byte ptr [rsi+36h], 26h ; '&'
0x140044048  jmp     loc_1400445A6
0x14004404d  lea     rax, [r8+rbp]
0x140044051  cmp     rax, r9
0x140044054  jbe     short loc_140044098
0x140044056  mov     eax, cs:dword_140087708
0x14004405c  cmp     eax, ebp
0x14004405e  jbe     loc_140043F6B
0x140044064  mov     edx, 20h ; ' '
0x140044069  lea     rcx, dword_140087708
0x140044070  call    _tlgKeywordOn
0x140044075  test    al, al
0x140044077  jz      loc_140043F6B
0x14004407d  mov     dword ptr [rsp+0C8h+var_98], r9d
0x140044082  lea     rax, aVhdmpiscsicomm_17; "VhdmpiScsiCommandPopulateToken: Populat"...
0x140044089  mov     dword ptr [rsp+0C8h+var_A0], r8d
0x14004408e  mov     ecx, 17CAh
0x140044093  jmp     loc_140043F52
0x140044098  movzx   eax, word ptr [r10+0Eh]
0x14004409d  ror     ax, 8
0x1400440a1  movzx   r8d, ax
0x1400440a5  lea     rax, [r8+10h]
0x1400440a9  cmp     rax, r9
0x1400440ac  jbe     short loc_1400440F0
0x1400440ae  mov     eax, cs:dword_140087708
0x1400440b4  cmp     eax, ebp
0x1400440b6  jbe     loc_140043F6B
0x1400440bc  mov     edx, 20h ; ' '
0x1400440c1  lea     rcx, dword_140087708
0x1400440c8  call    _tlgKeywordOn
0x1400440cd  test    al, al
0x1400440cf  jz      loc_140043F6B
0x1400440d5  mov     dword ptr [rsp+0C8h+var_98], r9d
0x1400440da  lea     rax, aVhdmpiscsicomm_15; "VhdmpiScsiCommandPopulateToken: BlockDe"...
0x1400440e1  mov     dword ptr [rsp+0C8h+var_A0], r8d
0x1400440e6  mov     ecx, 17DCh
0x1400440eb  jmp     loc_140043F52
0x1400440f0  cmp     r8d, 10h
0x1400440f4  jnb     loc_14004417B
0x1400440fa  mov     eax, cs:dword_140087708
0x140044100  cmp     eax, ebp
0x140044102  jbe     short loc_14004414B
0x140044104  mov     edx, 20h ; ' '
0x140044109  lea     rcx, dword_140087708
0x140044110  call    _tlgKeywordOn
0x140044115  test    al, al
0x140044117  jz      short loc_14004414B
0x140044119  mov     ecx, 17E8h
0x14004411e  mov     dword ptr [rsp+0C8h+var_98], 10h
0x140044126  mov     dword ptr [rsp+0C8h+var_A0], r8d; char
0x14004412b  lea     rax, aVhdmpiscsicomm_44; "VhdmpiScsiCommandPopulateToken: BlockDe"...
0x140044132  mov     r9d, edx; int
0x140044135  mov     [rsp+0C8h+var_A8], rax; char *
0x14004413a  mov     edx, ecx; int
0x14004413c  mov     r8d, ebp; int
0x14004413f  lea     rcx, aVhdmpiscsicomm_46; "VhdmpiScsiCommandPopulateToken"
0x140044146  call    TraceEvents
0x14004414b  mov     [rsi+25h], bpl
0x14004414f  xor     eax, eax
0x140044151  xorps   xmm0, xmm0
0x140044154  movups  xmmword ptr [rsi+2Ah], xmm0
0x140044158  mov     [rsi+3Ah], ax
0x14004415c  mov     word ptr [rsi+29h], 7001h
0x140044162  mov     al, [rsi+2Ch]
0x140044165  and     al, 0F5h
0x140044167  mov     byte ptr [rsi+31h], 0Ah
0x14004416b  or      al, 5
0x14004416d  mov     byte ptr [rsi+36h], 26h ; '&'
0x140044171  mov     [rsi+2Ch], al
0x140044174  mov     bl, 4
0x140044176  jmp     loc_1400445A6
0x14004417b  shr     r8d, 4
0x14004417f  cmp     r8d, 8
0x140044183  jbe     short loc_1400441C5
0x140044185  mov     eax, cs:dword_140087708
0x14004418b  cmp     eax, ebp
0x14004418d  jbe     loc_14004401D
0x140044193  mov     edx, 20h ; ' '
0x140044198  lea     rcx, dword_140087708
0x14004419f  call    _tlgKeywordOn
0x1400441a4  test    al, al
0x1400441a6  jz      loc_14004401D
0x1400441ac  mov     ecx, 17FCh
0x1400441b1  mov     dword ptr [rsp+0C8h+var_98], 8
0x1400441b9  lea     rax, aVhdmpiscsicomm_26; "VhdmpiScsiCommandPopulateToken: RangeLi"...
0x1400441c0  jmp     loc_140043FFF
0x1400441c5  test    byte ptr [r10+2], 1
0x1400441ca  jz      short loc_140044215
0x1400441cc  mov     eax, cs:dword_140087708
0x1400441d2  cmp     eax, ebp
0x1400441d4  jbe     short loc_140044174
0x1400441d6  mov     edx, 20h ; ' '
0x1400441db  lea     rcx, dword_140087708
0x1400441e2  call    _tlgKeywordOn
0x1400441e7  test    al, al
0x1400441e9  jz      short loc_140044174
0x1400441eb  mov     ecx, 1814h
0x1400441f0  lea     rax, aVhdmpiscsicomm_20; "VhdmpiScsiCommandPopulateToken: Populat"...
0x1400441f7  mov     r9d, edx; int
0x1400441fa  mov     [rsp+0C8h+var_A8], rax; char *
0x1400441ff  mov     edx, ecx; int
0x140044201  mov     r8d, ebp; int
0x140044204  lea     rcx, aVhdmpiscsicomm_46; "VhdmpiScsiCommandPopulateToken"
0x14004420b  call    TraceEvents
0x140044210  jmp     loc_140044174
0x140044215  mov     r12d, [r10+18h]
0x140044219  mov     edx, 1
0x14004421e  mov     r11, [r10+10h]
0x140044222  bswap   r11
0x140044225  mov     [rsp+0C8h+var_40], r11
0x14004422d  bswap   r12d
0x140044230  mov     r12d, r12d
0x140044233  cmp     r8d, edx
0x140044236  jbe     short loc_140044262
0x140044238  mov     r9d, edx
0x14004423b  lea     rax, [r12+r11]
0x14004423f  add     r9, r9
0x140044242  mov     rcx, [r10+r9*8+10h]
0x140044247  bswap   rcx
0x14004424a  cmp     rax, rcx
0x14004424d  jnz     short loc_140044262
0x14004424f  mov     eax, [r10+r9*8+18h]
0x140044254  inc     edx
0x140044256  bswap   eax
0x140044258  mov     eax, eax
0x14004425a  add     r12, rax
0x14004425d  cmp     edx, r8d
0x140044260  jb      short loc_140044238
0x140044262  mov     [rsp+0C8h+var_58], r12
0x140044267  mov     r9, r12
0x14004426a  cmp     edx, r8d
0x14004426d  jnb     short loc_14004428C
0x14004426f  mov     eax, edx
0x140044271  inc     edx
0x140044273  add     rax, rax
0x140044276  mov     eax, [r10+rax*8+18h]
0x14004427b  bswap   eax
0x14004427d  mov     eax, eax
0x14004427f  add     r9, rax
0x140044282  cmp     edx, r8d
0x140044285  jb      short loc_14004426F
0x140044287  mov     [rsp+0C8h+var_58], r9
0x14004428c  mov     ecx, [r14+40h]
0x140044290  mov     rax, r12
0x140044293  shl     rax, cl
0x140044296  mov     r13d, 4000000h
0x14004429c  mov     [rsp+0C8h+arg_8], ecx
0x1400442a3  cmp     rax, r13
0x1400442a6  ja      short loc_1400442B4
0x1400442a8  mov     r13, rax
0x1400442ab  test    rax, rax
0x1400442ae  jz      loc_140043F0B
0x1400442b4  mov     rax, r11
0x1400442b7  mov     r8d, r13d; unsigned int
0x1400442ba  shl     rax, cl
0x1400442bd  mov     rdx, rsi; struct VHD_SCSI_REQUEST *
0x1400442c0  mov     r9, rax; unsigned __int64
0x1400442c3  mov     [rsp+0C8h+var_50], rax
0x1400442c8  mov     rcx, r14; struct VHD_SCSI_STATE *
0x1400442cb  call    ?VhdmpiValidateReadWriteScsiParameters@@YAEPEAUVHD_SCSI_STATE@@PEAUVHD_SCSI_REQUEST@@K_K@Z; VhdmpiValidateReadWriteScsiParameters(VHD_SCSI_STATE *,VHD_SCSI_REQUEST *,ulong,unsigned __int64)
0x1400442d0  mov     bl, al
0x1400442d2  cmp     al, 1
0x1400442d4  jnz     loc_1400445A6
0x1400442da  lea     r8, [rsp+0C8h+P]; struct _VHD_OFFLOAD_OP **
0x1400442e2  mov     rcx, r14; struct VHD_SCSI_STATE *
0x1400442e5  call    ?VhdmpiAllocateAndInitializeOffloadOp@@YAJPEAUVHD_SCSI_STATE@@PEAUVHD_SCSI_REQUEST@@PEAPEAU_VHD_OFFLOAD_OP@@@Z; VhdmpiAllocateAndInitializeOffloadOp(VHD_SCSI_STATE *,VHD_SCSI_REQUEST *,_VHD_OFFLOAD_OP * *)
0x1400442ea  test    eax, eax
0x1400442ec  jns     short loc_140044341
0x1400442ee  mov     eax, cs:dword_140087708
0x1400442f4  cmp     eax, ebp
0x1400442f6  jbe     short loc_140044332
0x1400442f8  mov     edx, 20h ; ' '
0x1400442fd  lea     rcx, dword_140087708
0x140044304  call    _tlgKeywordOn
0x140044309  test    al, al
0x14004430b  jz      short loc_140044332
0x14004430d  mov     ecx, 187Ch
0x140044312  lea     rax, aVhdmpiscsicomm_29; "VhdmpiScsiCommandPopulateToken: VhdmpiA"...
0x140044319  mov     r9d, edx; int
0x14004431c  mov     [rsp+0C8h+var_A8], rax; char *
  ... truncated ...
```
