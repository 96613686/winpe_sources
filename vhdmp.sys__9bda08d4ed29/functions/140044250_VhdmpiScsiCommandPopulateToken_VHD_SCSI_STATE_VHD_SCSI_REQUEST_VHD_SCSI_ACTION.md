# VhdmpiScsiCommandPopulateToken(VHD_SCSI_STATE *,VHD_SCSI_REQUEST *,VHD_SCSI_ACTION *)

- ea: `0x140044250`
- end: `0x1400449b4`
- name: `?VhdmpiScsiCommandPopulateToken@@YAEPEAUVHD_SCSI_STATE@@PEAUVHD_SCSI_REQUEST@@PEAUVHD_SCSI_ACTION@@@Z`
- size: `1892`
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
- `0x140044250`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14004498a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004498a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004478b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004478b`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400447b1`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400447b1`

## string_xrefs

- `0x1400443e8`: `VhdmpiScsiCommandPopulateToken: PopulateTokenDataLength too small (%u < %u)`
- `0x140044472`: `VhdmpiScsiCommandPopulateToken: PopulateTokenDataLength too large (%u + 2 > %u)`
- `0x1400444ca`: `VhdmpiScsiCommandPopulateToken: BlockDeviceRangeDescriptorListLength too large (%u + 16 > %u)`
- `0x14004451b`: `VhdmpiScsiCommandPopulateToken: BlockDeviceRangeDescriptorListLength too small (%u < %u)`
- `0x1400442e1`: `VhdmpiScsiCommandPopulateToken: PARAMETER LIST LENGTH of zero not considered an error`
- `0x1400442ef`: `VhdmpiScsiCommandPopulateToken`
- `0x14004434f`: `VhdmpiScsiCommandPopulateToken`
- `0x1400443fe`: `VhdmpiScsiCommandPopulateToken`
- `0x14004452f`: `VhdmpiScsiCommandPopulateToken`
- `0x1400445f4`: `VhdmpiScsiCommandPopulateToken`
- `0x140044716`: `VhdmpiScsiCommandPopulateToken`
- `0x140044803`: `VhdmpiScsiCommandPopulateToken`
- `0x14004487e`: `VhdmpiScsiCommandPopulateToken`
- `0x140044910`: `VhdmpiScsiCommandPopulateToken`
- `0x14004433b`: `VhdmpiScsiCommandPopulateToken: buffer too small relative to PARAMETER LIST LENGTH (%u < %u)`
- `0x14004438f`: `VhdmpiScsiCommandPopulateToken: ParameterListLength non-zero, but too small (%u < %u)`
- `0x14004486a`: `VhdmpiScsiCommandPopulateToken: VhdmpiOffloadTableInsertLocked returned STATUS_INSUFFICIENT_RESOURCES`
- `0x140044948`: `Offload Read start (ScsiState:%p Request:%p TransactionId:%d) : LBA: start %#016I64x, length %#016I64x, total %#016I64x BYTE: offset: %#016I64x length: %#016I64x, total: %#016I64x`
- `0x1400445a9`: `VhdmpiScsiCommandPopulateToken: RangeListCount too large (%u > %u)`
- `0x1400445e0`: `VhdmpiScsiCommandPopulateToken: PopulateTokenHeader->Immediate != 0 --- this is not supported`
- `0x140044702`: `VhdmpiScsiCommandPopulateToken: VhdmpiAllocateAndInitializeOffloadOp() failed - setting UpperSrbStatus to SRB_STATUS_ERROR`
- `0x1400447ef`: `VhdmpiScsiCommandPopulateToken: VhdmpiOffloadTableInsertLocked returned STATUS_DUPLICATE_OBJECTID`

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
    if ( (unsigned int)dword_1400876D0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 32) )
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
    if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 32) )
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
    if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 32) )
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
    if ( (unsigned int)dword_1400876D0 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_1400876D0, 32) )
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
    if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 32) )
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
    if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 32) )
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
    if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 32) )
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
    if ( (unsigned int)dword_1400876D0 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_1400876D0, 32) )
      goto LABEL_20;
    v17 = 6140;
    v51 = 8;
    v18 = "VhdmpiScsiCommandPopulateToken: RangeListCount too large (%u > %u)";
    goto LABEL_19;
  }
  if ( (*(_BYTE *)(v13 + 2) & 1) != 0 )
  {
    if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 32) )
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
        if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 32) )
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
        if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 32) )
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
        if ( (unsigned int)dword_1400876D0 <= 5 )
        {
          v49 = v53;
        }
        else
        {
          v49 = v53;
          if ( (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 32) )
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
      if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 32) )
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
0x140044250  mov     rax, rsp
0x140044253  mov     [rax+18h], rbx
0x140044257  mov     [rax+8], rcx
0x14004425b  push    rbp
0x14004425c  push    rsi
0x14004425d  push    rdi
0x14004425e  push    r12
0x140044260  push    r13
0x140044262  push    r14
0x140044264  push    r15
0x140044266  sub     rsp, 90h
0x14004426d  mov     rdi, [rdx]
0x140044270  mov     r15, r8
0x140044273  mov     qword ptr [rax+20h], 0
0x14004427b  mov     rsi, rdx
0x14004427e  mov     r14, rcx
0x140044281  mov     al, [rdi+0Ah]
0x140044284  mov     byte ptr [rsp+0C8h+arg_8+3], al
0x14004428b  mov     al, [rdi+0Bh]
0x14004428e  mov     byte ptr [rsp+0C8h+arg_8+2], al
0x140044295  mov     al, [rdi+0Ch]
0x140044298  mov     byte ptr [rsp+0C8h+arg_8+1], al
0x14004429f  mov     al, [rdi+0Dh]
0x1400442a2  mov     byte ptr [rsp+0C8h+arg_8], al
0x1400442a9  mov     r9d, [rsp+0C8h+arg_8]
0x1400442b1  test    r9d, r9d
0x1400442b4  jnz     short loc_140044302
0x1400442b6  mov     eax, cs:dword_1400876D0
0x1400442bc  cmp     eax, 5
0x1400442bf  jbe     short loc_1400442FB
0x1400442c1  lea     edx, [r9+20h]
0x1400442c5  lea     rcx, dword_1400876D0
0x1400442cc  call    _tlgKeywordOn
0x1400442d1  test    al, al
0x1400442d3  jz      short loc_1400442FB
0x1400442d5  mov     ecx, 177Bh
0x1400442da  lea     r8d, [rdx-1Bh]; int
0x1400442de  mov     r9d, edx; int
0x1400442e1  lea     rax, aVhdmpiscsicomm_45; "VhdmpiScsiCommandPopulateToken: PARAMET"...
0x1400442e8  mov     edx, ecx; int
0x1400442ea  mov     [rsp+0C8h+var_A8], rax; char *
0x1400442ef  lea     rcx, aVhdmpiscsicomm_46; "VhdmpiScsiCommandPopulateToken"
0x1400442f6  call    TraceEvents
0x1400442fb  mov     bl, 1
0x1400442fd  jmp     loc_140044996
0x140044302  mov     ebp, 2
0x140044307  cmp     r9d, [rdx+10h]
0x14004430b  jbe     short loc_140044362
0x14004430d  mov     eax, cs:dword_1400876D0
0x140044313  cmp     eax, ebp
0x140044315  jbe     short loc_14004435B
0x140044317  lea     edx, [rbp+1Eh]
0x14004431a  lea     rcx, dword_1400876D0
0x140044321  call    _tlgKeywordOn
0x140044326  test    al, al
0x140044328  jz      short loc_14004435B
0x14004432a  mov     eax, [rsi+10h]
0x14004432d  mov     ecx, 178Dh
0x140044332  mov     dword ptr [rsp+0C8h+var_98], r9d
0x140044337  mov     dword ptr [rsp+0C8h+var_A0], eax; char
0x14004433b  lea     rax, aVhdmpiscsicomm_13; "VhdmpiScsiCommandPopulateToken: buffer "...
0x140044342  mov     r9d, edx; int
0x140044345  mov     [rsp+0C8h+var_A8], rax; char *
0x14004434a  mov     edx, ecx; int
0x14004434c  mov     r8d, ebp; int
0x14004434f  lea     rcx, aVhdmpiscsicomm_46; "VhdmpiScsiCommandPopulateToken"
0x140044356  call    TraceEvents
0x14004435b  mov     bl, 12h
0x14004435d  jmp     loc_140044996
0x140044362  cmp     r9d, 10h
0x140044366  jnb     short loc_1400443A2
0x140044368  mov     eax, cs:dword_1400876D0
0x14004436e  cmp     eax, ebp
0x140044370  jbe     short loc_14004435B
0x140044372  mov     edx, 20h ; ' '
0x140044377  lea     rcx, dword_1400876D0
0x14004437e  call    _tlgKeywordOn
0x140044383  test    al, al
0x140044385  jz      short loc_14004435B
0x140044387  mov     dword ptr [rsp+0C8h+var_98], 10h
0x14004438f  lea     rax, aVhdmpiscsicomm_42; "VhdmpiScsiCommandPopulateToken: Paramet"...
0x140044396  mov     dword ptr [rsp+0C8h+var_A0], r9d
0x14004439b  mov     ecx, 179Bh
0x1400443a0  jmp     short loc_140044342
0x1400443a2  mov     r10, [rdx+8]
0x1400443a6  movzx   eax, word ptr [r10]
0x1400443aa  ror     ax, 8
0x1400443ae  movzx   r8d, ax
0x1400443b2  cmp     r8d, 1Eh
0x1400443b6  jnb     loc_14004443D
0x1400443bc  mov     eax, cs:dword_1400876D0
0x1400443c2  cmp     eax, ebp
0x1400443c4  jbe     short loc_14004440D
0x1400443c6  mov     edx, 20h ; ' '
0x1400443cb  lea     rcx, dword_1400876D0
0x1400443d2  call    _tlgKeywordOn
0x1400443d7  test    al, al
0x1400443d9  jz      short loc_14004440D
0x1400443db  mov     ecx, 17B6h
0x1400443e0  mov     dword ptr [rsp+0C8h+var_98], 1Eh
0x1400443e8  lea     rax, aVhdmpiscsicomm_9; "VhdmpiScsiCommandPopulateToken: Populat"...
0x1400443ef  mov     dword ptr [rsp+0C8h+var_A0], r8d; char
0x1400443f4  mov     r9d, edx; int
0x1400443f7  mov     edx, ecx; int
0x1400443f9  mov     [rsp+0C8h+var_A8], rax; char *
0x1400443fe  lea     rcx, aVhdmpiscsicomm_46; "VhdmpiScsiCommandPopulateToken"
0x140044405  mov     r8d, ebp; int
0x140044408  call    TraceEvents
0x14004440d  mov     [rsi+25h], bpl
0x140044411  xor     eax, eax
0x140044413  xorps   xmm0, xmm0
0x140044416  mov     bl, 4
0x140044418  movups  xmmword ptr [rsi+2Ah], xmm0
0x14004441c  mov     [rsi+3Ah], ax
0x140044420  mov     word ptr [rsi+29h], 7001h
0x140044426  mov     al, [rsi+2Ch]
0x140044429  and     al, 0F5h
0x14004442b  or      al, 5
0x14004442d  mov     [rsi+2Ch], al
0x140044430  mov     byte ptr [rsi+31h], 0Ah
0x140044434  mov     byte ptr [rsi+36h], 26h ; '&'
0x140044438  jmp     loc_140044996
0x14004443d  lea     rax, [r8+rbp]
0x140044441  cmp     rax, r9
0x140044444  jbe     short loc_140044488
0x140044446  mov     eax, cs:dword_1400876D0
0x14004444c  cmp     eax, ebp
0x14004444e  jbe     loc_14004435B
0x140044454  mov     edx, 20h ; ' '
0x140044459  lea     rcx, dword_1400876D0
0x140044460  call    _tlgKeywordOn
0x140044465  test    al, al
0x140044467  jz      loc_14004435B
0x14004446d  mov     dword ptr [rsp+0C8h+var_98], r9d
0x140044472  lea     rax, aVhdmpiscsicomm_17; "VhdmpiScsiCommandPopulateToken: Populat"...
0x140044479  mov     dword ptr [rsp+0C8h+var_A0], r8d
0x14004447e  mov     ecx, 17CAh
0x140044483  jmp     loc_140044342
0x140044488  movzx   eax, word ptr [r10+0Eh]
0x14004448d  ror     ax, 8
0x140044491  movzx   r8d, ax
0x140044495  lea     rax, [r8+10h]
0x140044499  cmp     rax, r9
0x14004449c  jbe     short loc_1400444E0
0x14004449e  mov     eax, cs:dword_1400876D0
0x1400444a4  cmp     eax, ebp
0x1400444a6  jbe     loc_14004435B
0x1400444ac  mov     edx, 20h ; ' '
0x1400444b1  lea     rcx, dword_1400876D0
0x1400444b8  call    _tlgKeywordOn
0x1400444bd  test    al, al
0x1400444bf  jz      loc_14004435B
0x1400444c5  mov     dword ptr [rsp+0C8h+var_98], r9d
0x1400444ca  lea     rax, aVhdmpiscsicomm_15; "VhdmpiScsiCommandPopulateToken: BlockDe"...
0x1400444d1  mov     dword ptr [rsp+0C8h+var_A0], r8d
0x1400444d6  mov     ecx, 17DCh
0x1400444db  jmp     loc_140044342
0x1400444e0  cmp     r8d, 10h
0x1400444e4  jnb     loc_14004456B
0x1400444ea  mov     eax, cs:dword_1400876D0
0x1400444f0  cmp     eax, ebp
0x1400444f2  jbe     short loc_14004453B
0x1400444f4  mov     edx, 20h ; ' '
0x1400444f9  lea     rcx, dword_1400876D0
0x140044500  call    _tlgKeywordOn
0x140044505  test    al, al
0x140044507  jz      short loc_14004453B
0x140044509  mov     ecx, 17E8h
0x14004450e  mov     dword ptr [rsp+0C8h+var_98], 10h
0x140044516  mov     dword ptr [rsp+0C8h+var_A0], r8d; char
0x14004451b  lea     rax, aVhdmpiscsicomm_44; "VhdmpiScsiCommandPopulateToken: BlockDe"...
0x140044522  mov     r9d, edx; int
0x140044525  mov     [rsp+0C8h+var_A8], rax; char *
0x14004452a  mov     edx, ecx; int
0x14004452c  mov     r8d, ebp; int
0x14004452f  lea     rcx, aVhdmpiscsicomm_46; "VhdmpiScsiCommandPopulateToken"
0x140044536  call    TraceEvents
0x14004453b  mov     [rsi+25h], bpl
0x14004453f  xor     eax, eax
0x140044541  xorps   xmm0, xmm0
0x140044544  movups  xmmword ptr [rsi+2Ah], xmm0
0x140044548  mov     [rsi+3Ah], ax
0x14004454c  mov     word ptr [rsi+29h], 7001h
0x140044552  mov     al, [rsi+2Ch]
0x140044555  and     al, 0F5h
0x140044557  mov     byte ptr [rsi+31h], 0Ah
0x14004455b  or      al, 5
0x14004455d  mov     byte ptr [rsi+36h], 26h ; '&'
0x140044561  mov     [rsi+2Ch], al
0x140044564  mov     bl, 4
0x140044566  jmp     loc_140044996
0x14004456b  shr     r8d, 4
0x14004456f  cmp     r8d, 8
0x140044573  jbe     short loc_1400445B5
0x140044575  mov     eax, cs:dword_1400876D0
0x14004457b  cmp     eax, ebp
0x14004457d  jbe     loc_14004440D
0x140044583  mov     edx, 20h ; ' '
0x140044588  lea     rcx, dword_1400876D0
0x14004458f  call    _tlgKeywordOn
0x140044594  test    al, al
0x140044596  jz      loc_14004440D
0x14004459c  mov     ecx, 17FCh
0x1400445a1  mov     dword ptr [rsp+0C8h+var_98], 8
0x1400445a9  lea     rax, aVhdmpiscsicomm_26; "VhdmpiScsiCommandPopulateToken: RangeLi"...
0x1400445b0  jmp     loc_1400443EF
0x1400445b5  test    byte ptr [r10+2], 1
0x1400445ba  jz      short loc_140044605
0x1400445bc  mov     eax, cs:dword_1400876D0
0x1400445c2  cmp     eax, ebp
0x1400445c4  jbe     short loc_140044564
0x1400445c6  mov     edx, 20h ; ' '
0x1400445cb  lea     rcx, dword_1400876D0
0x1400445d2  call    _tlgKeywordOn
0x1400445d7  test    al, al
0x1400445d9  jz      short loc_140044564
0x1400445db  mov     ecx, 1814h
0x1400445e0  lea     rax, aVhdmpiscsicomm_20; "VhdmpiScsiCommandPopulateToken: Populat"...
0x1400445e7  mov     r9d, edx; int
0x1400445ea  mov     [rsp+0C8h+var_A8], rax; char *
0x1400445ef  mov     edx, ecx; int
0x1400445f1  mov     r8d, ebp; int
0x1400445f4  lea     rcx, aVhdmpiscsicomm_46; "VhdmpiScsiCommandPopulateToken"
0x1400445fb  call    TraceEvents
0x140044600  jmp     loc_140044564
0x140044605  mov     r12d, [r10+18h]
0x140044609  mov     edx, 1
0x14004460e  mov     r11, [r10+10h]
0x140044612  bswap   r11
0x140044615  mov     [rsp+0C8h+var_40], r11
0x14004461d  bswap   r12d
0x140044620  mov     r12d, r12d
0x140044623  cmp     r8d, edx
0x140044626  jbe     short loc_140044652
0x140044628  mov     r9d, edx
0x14004462b  lea     rax, [r12+r11]
0x14004462f  add     r9, r9
0x140044632  mov     rcx, [r10+r9*8+10h]
0x140044637  bswap   rcx
0x14004463a  cmp     rax, rcx
0x14004463d  jnz     short loc_140044652
0x14004463f  mov     eax, [r10+r9*8+18h]
0x140044644  inc     edx
0x140044646  bswap   eax
0x140044648  mov     eax, eax
0x14004464a  add     r12, rax
0x14004464d  cmp     edx, r8d
0x140044650  jb      short loc_140044628
0x140044652  mov     [rsp+0C8h+var_58], r12
0x140044657  mov     r9, r12
0x14004465a  cmp     edx, r8d
0x14004465d  jnb     short loc_14004467C
0x14004465f  mov     eax, edx
0x140044661  inc     edx
0x140044663  add     rax, rax
0x140044666  mov     eax, [r10+rax*8+18h]
0x14004466b  bswap   eax
0x14004466d  mov     eax, eax
0x14004466f  add     r9, rax
0x140044672  cmp     edx, r8d
0x140044675  jb      short loc_14004465F
0x140044677  mov     [rsp+0C8h+var_58], r9
0x14004467c  mov     ecx, [r14+40h]
0x140044680  mov     rax, r12
0x140044683  shl     rax, cl
0x140044686  mov     r13d, 4000000h
0x14004468c  mov     [rsp+0C8h+arg_8], ecx
0x140044693  cmp     rax, r13
0x140044696  ja      short loc_1400446A4
0x140044698  mov     r13, rax
0x14004469b  test    rax, rax
0x14004469e  jz      loc_1400442FB
0x1400446a4  mov     rax, r11
0x1400446a7  mov     r8d, r13d; unsigned int
0x1400446aa  shl     rax, cl
0x1400446ad  mov     rdx, rsi; struct VHD_SCSI_REQUEST *
0x1400446b0  mov     r9, rax; unsigned __int64
0x1400446b3  mov     [rsp+0C8h+var_50], rax
0x1400446b8  mov     rcx, r14; struct VHD_SCSI_STATE *
0x1400446bb  call    ?VhdmpiValidateReadWriteScsiParameters@@YAEPEAUVHD_SCSI_STATE@@PEAUVHD_SCSI_REQUEST@@K_K@Z; VhdmpiValidateReadWriteScsiParameters(VHD_SCSI_STATE *,VHD_SCSI_REQUEST *,ulong,unsigned __int64)
0x1400446c0  mov     bl, al
0x1400446c2  cmp     al, 1
0x1400446c4  jnz     loc_140044996
0x1400446ca  lea     r8, [rsp+0C8h+P]; struct _VHD_OFFLOAD_OP **
0x1400446d2  mov     rcx, r14; struct VHD_SCSI_STATE *
0x1400446d5  call    ?VhdmpiAllocateAndInitializeOffloadOp@@YAJPEAUVHD_SCSI_STATE@@PEAUVHD_SCSI_REQUEST@@PEAPEAU_VHD_OFFLOAD_OP@@@Z; VhdmpiAllocateAndInitializeOffloadOp(VHD_SCSI_STATE *,VHD_SCSI_REQUEST *,_VHD_OFFLOAD_OP * *)
0x1400446da  test    eax, eax
0x1400446dc  jns     short loc_140044731
0x1400446de  mov     eax, cs:dword_1400876D0
0x1400446e4  cmp     eax, ebp
0x1400446e6  jbe     short loc_140044722
0x1400446e8  mov     edx, 20h ; ' '
0x1400446ed  lea     rcx, dword_1400876D0
0x1400446f4  call    _tlgKeywordOn
0x1400446f9  test    al, al
0x1400446fb  jz      short loc_140044722
0x1400446fd  mov     ecx, 187Ch
0x140044702  lea     rax, aVhdmpiscsicomm_29; "VhdmpiScsiCommandPopulateToken: VhdmpiA"...
0x140044709  mov     r9d, edx; int
0x14004470c  mov     [rsp+0C8h+var_A8], rax; char *
  ... truncated ...
```
