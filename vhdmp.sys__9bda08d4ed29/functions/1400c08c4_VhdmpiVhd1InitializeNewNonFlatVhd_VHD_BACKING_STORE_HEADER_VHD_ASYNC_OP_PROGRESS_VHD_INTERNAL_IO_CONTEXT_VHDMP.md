# VhdmpiVhd1InitializeNewNonFlatVhd(_VHD_BACKING_STORE_HEADER *,_VHD_ASYNC_OP_PROGRESS *,_VHD_INTERNAL_IO_CONTEXT *,_VHDMP_POPULATE_PARAMETERS *,_VHD_DISK_FOOTER_PACKED *)

- ea: `0x1400c08c4`
- end: `0x1400c12f7`
- name: `?VhdmpiVhd1InitializeNewNonFlatVhd@@YAJPEAU_VHD_BACKING_STORE_HEADER@@PEAU_VHD_ASYNC_OP_PROGRESS@@PEAU_VHD_INTERNAL_IO_CONTEXT@@PEAU_VHDMP_POPULATE_PARAMETERS@@PEAU_VHD_DISK_FOOTER_PACKED@@@Z`
- size: `2611`
- prototype: `__int64 __usercall@<rax>(struct _VHD_BACKING_STORE_HEADER *@<rcx>, struct _VHD_ASYNC_OP_PROGRESS *@<rdx>, struct _VHD_INTERNAL_IO_CONTEXT *@<r8>, struct _VHDMP_POPULATE_PARAMETERS *@<r9>, struct _VHD_DISK_FOOTER_PACKED *)`
- caller_count: `1`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x1400c15e0`

## callees

- `0x1400197b0`
- `0x140021d28`
- `0x140023980`
- `0x140026088`
- `0x140033a58`
- `0x140033e58`
- `0x140036284`
- `0x14003c39c`
- `0x14003f110`
- `0x14003f1d4`
- `0x14005dbb0`
- `0x14005de00`
- `0x14005e100`
- `0x1400b2d44`
- `0x1400b6ca4`
- `0x1400c08c4`
- `0x1400e09a4`
- `0x1400e7cf8`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x1400c0a9e`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400c0a9e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c0d64`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c0d91`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c0daa`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c0d64`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c0d91`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c0daa`
- `ntoskrnl!ExAllocatePool2` at `0x1400c0a5c`
- `ntoskrnl!ExAllocatePool2` at `0x1400c0c53`
- `ntoskrnl!ExAllocatePool2` at `0x1400c0cdf`
- `ntoskrnl!ExAllocatePool2` at `0x1400c0a5c`
- `ntoskrnl!ExAllocatePool2` at `0x1400c0c53`
- `ntoskrnl!ExAllocatePool2` at `0x1400c0cdf`

## string_xrefs

- `0x1400c10e6`: `VhdmpiVhd1InitializeNewNonFlatVhd: failed to read from source at offset 0x%I64x(0x%08x).`
- `0x1400c0d3f`: `VhdmpiVhd1InitializeNewNonFlatVhd: create canceled`
- `0x1400c0fde`: `VhdmpiVhd1InitializeNewNonFlatVhd: failed to write dynamic header to offset 0x%I64x(0x%08x).`
- `0x1400c1058`: `Vhdmpivhd1InitializeNewNonFlatVhd: failed to write to offset 0x%I64x(0x%08x).`
- `0x1400c119b`: `VhdmpiVhd1InitializeNewNonFlatVhd: failed to write BAT to offset 0x%I64x(0x%08x).`
- `0x1400c12ba`: `VhdmpiVhd1InitializeNewNonFlatVhd: failed to write footer to offset 0x%I64x(0x%08x).`
- `0x1400c1208`: `VhdmpiVhd1InitializeNewNonFlatVhd: failed to write header to offset 0x%I64x(0x%08x).`
- `0x1400c0bc8`: `VhdmpiVhd1InitializeNewNonFlatVhd: failed to write parent locator to offset 0x%I64x(0x%08x).`

## pseudocode

```c
__int64 __fastcall VhdmpiVhd1InitializeNewNonFlatVhd(
        struct _VHD_BACKING_STORE_HEADER *a1,
        struct _VHD_ASYNC_OP_PROGRESS *a2,
        struct _VHD_INTERNAL_IO_CONTEXT *a3,
        struct _VHDMP_POPULATE_PARAMETERS *a4,
        struct _VHD_DISK_FOOTER_PACKED *a5)
{
  unsigned __int64 v5; // r15
  __int64 v7; // rbx
  __int64 v8; // r12
  __int64 v9; // rax
  int v10; // edi
  struct _VHDMP_POPULATE_PARAMETERS *v11; // rsi
  unsigned int v12; // edx
  __int128 v13; // xmm0
  const UNICODE_STRING *v14; // rdi
  int v15; // r14d
  unsigned int v16; // ebx
  void *v17; // rsi
  int AsyncOpOverrideStatus; // ebx
  unsigned int v19; // edi
  size_t Length; // r8
  __int64 v21; // r14
  unsigned __int64 v22; // r14
  size_t v23; // rbx
  void *v24; // rax
  unsigned __int64 v25; // r14
  struct _VHD_ASYNC_OP_CONTEXT *v26; // rcx
  __int64 v27; // r8
  unsigned int v28; // r9d
  unsigned __int16 v29; // dx
  PVOID v30; // rcx
  unsigned __int64 v32; // r12
  unsigned __int64 v33; // rsi
  unsigned __int64 v34; // r15
  unsigned __int64 v35; // rsi
  unsigned int v36; // edx
  unsigned __int8 *v37; // rbx
  struct _VHD_BACKING_STORE_HEADER *v38; // rcx
  unsigned int v39; // esi
  __int64 v40; // r15
  unsigned int v41; // esi
  struct _VHD_ASYNC_OP_CONTEXT **v42; // rdx
  unsigned int v43; // r9d
  unsigned int v44; // r9d
  unsigned int v45; // r9d
  char v46; // al
  unsigned int v47; // r9d
  unsigned __int64 v48; // r15
  unsigned int v49; // edx
  char *v50; // rax
  unsigned __int16 v51; // cx
  void *v52; // r15
  int VhdFileSize; // eax
  __int64 v54; // r11
  __int64 v55; // r11
  __int64 v56; // r14
  char v57[8]; // [rsp+28h] [rbp-D8h]
  __int64 v58; // [rsp+30h] [rbp-D0h]
  unsigned __int8 v59; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int8 v60[7]; // [rsp+41h] [rbp-BFh] BYREF
  PVOID P; // [rsp+48h] [rbp-B8h]
  unsigned int v62; // [rsp+50h] [rbp-B0h]
  void *Pool2; // [rsp+58h] [rbp-A8h]
  unsigned int v64; // [rsp+60h] [rbp-A0h]
  struct _VHD_INTERNAL_IO_CONTEXT *v65; // [rsp+68h] [rbp-98h]
  struct _VHDMP_POPULATE_PARAMETERS *v66; // [rsp+70h] [rbp-90h]
  PVOID v67; // [rsp+78h] [rbp-88h]
  struct _VHD_ASYNC_OP_PROGRESS *v68; // [rsp+80h] [rbp-80h]
  unsigned __int64 v69; // [rsp+88h] [rbp-78h]
  char v70[8]; // [rsp+90h] [rbp-70h]
  struct _UNICODE_STRING DestinationString; // [rsp+98h] [rbp-68h] BYREF
  __int64 v72; // [rsp+A8h] [rbp-58h] BYREF
  unsigned int v73[2]; // [rsp+B0h] [rbp-50h]
  unsigned int v74[2]; // [rsp+B8h] [rbp-48h]
  void *v75; // [rsp+C0h] [rbp-40h]
  _QWORD v76[128]; // [rsp+D0h] [rbp-30h] BYREF

  v5 = *((unsigned int *)a4 + 1);
  v7 = *((_QWORD *)a4 + 7);
  v75 = a5;
  v8 = 4096;
  v68 = a2;
  if ( (_DWORD)v5 != 0x200000 )
    v8 = 512;
  v65 = a3;
  *((_DWORD *)a1 + 481) = v8;
  v9 = *((_QWORD *)a4 + 6) - 1LL;
  v66 = a4;
  v72 = 0;
  v60[0] = 0;
  v59 = 0;
  v64 = v5;
  v69 = (~(v5 - 1) & (v5 + v9)) / v5;
  v62 = v8;
  *(_QWORD *)v73 = v5;
  v10 = v69;
  v11 = a4;
  DestinationString = 0;
  memset(v76, 0, sizeof(v76));
  qmemcpy(v76, "cxsparse", 8);
  HIDWORD(v76[3]) = _byteswap_ulong(v69);
  LODWORD(v76[4]) = _byteswap_ulong(v5);
  v76[1] = -1;
  LODWORD(v76[3]) = 256;
  if ( (unsigned int)dword_1400876D0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 8) )
    TraceEvents(
      "VhdmpiVhd1InitializeNewNonFlatVhd",
      0x2F0u,
      5u,
      v12,
      "VhdmpiVhd1InitializeNewNonFlatVhd: VirtualSize=0x%016I64X BlockSize=0x%08X MaxTableEntries=0x%016I64X",
      *((_QWORD *)v11 + 6),
      v5,
      v69);
  if ( v7 )
  {
    v13 = *(_OWORD *)(v7 + 1996);
    v14 = (const UNICODE_STRING *)(v7 + 72);
    v67 = 0;
    *(_OWORD *)&v76[5] = v13;
    v15 = ~(v8 - 1);
    LODWORD(v76[7]) = _byteswap_ulong(*(_DWORD *)(v7 + 1952));
    v16 = v15 & (v8 + *(unsigned __int16 *)(v7 + 72) + 11);
    Pool2 = (void *)ExAllocatePool2(64, v16, 2051295318);
    v17 = Pool2;
    if ( !Pool2 )
    {
      AsyncOpOverrideStatus = -1073741670;
      goto LABEL_38;
    }
    DestinationString.Buffer = (PWSTR)Pool2;
    if ( v16 > 0xFFFE )
      LOWORD(v16) = -2;
    DestinationString.Length = 0;
    DestinationString.MaximumLength = v16;
    RtlCopyUnicodeString(&DestinationString, v14);
    if ( (int)VhdmpiMakeLongPathDecorationAppropriate(&DestinationString) < 0 )
    {
      AsyncOpOverrideStatus = -1073741562;
      goto LABEL_38;
    }
    LODWORD(v76[72]) = 1969959511;
    v19 = v15 & (v8 + DestinationString.Length - 1);
    HIDWORD(v76[72]) = _byteswap_ulong(v19);
    v76[74] = _byteswap_uint64(((unsigned int)v8 + 1535LL) & ~(v8 - 1));
    Length = 512;
    LODWORD(v76[73]) = _byteswap_ulong(DestinationString.Length);
    if ( DestinationString.Length <= 0x200u )
      Length = DestinationString.Length;
    memmove(&v76[8], DestinationString.Buffer, Length);
    if ( (unsigned int)dword_1400876D0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 8) )
      TraceEvents(
        "VhdmpiVhd1InitializeNewNonFlatVhd",
        0x368u,
        5u,
        8u,
        "VhdmpiVhd1InitializeNewNonFlatVhd: writing locator @ FillOffset: 0x%I64x",
        ((unsigned int)v8 + 1535LL) & ~(v8 - 1));
    AsyncOpOverrideStatus = VhdmpiMetadataSynchronousIo(
                              (struct _VHD_BACKING_STORE_HEADER *)((char *)a1 + 72),
                              a1,
                              4u,
                              Pool2,
                              v19,
                              ((unsigned int)v8 + 1535LL) & ~(v8 - 1));
    if ( AsyncOpOverrideStatus < 0 )
    {
      if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 8) )
        TraceEvents(
          "VhdmpiVhd1InitializeNewNonFlatVhd",
          0x377u,
          2u,
          8u,
          "VhdmpiVhd1InitializeNewNonFlatVhd: failed to write parent locator to offset 0x%I64x(0x%08x).",
          ((unsigned int)v8 + 1535LL) & ~(v8 - 1),
          AsyncOpOverrideStatus);
      goto LABEL_37;
    }
    v21 = v19;
    v10 = v69;
    v22 = (((unsigned int)v8 + 1535LL) & ~(v8 - 1)) + v21;
    v11 = v66;
  }
  else
  {
    Pool2 = 0;
    v22 = 1536;
  }
  v76[2] = _byteswap_uint64(v22);
  HIDWORD(v76[4]) = _byteswap_ulong(VhdmpiCalculateSparseHeaderChecksum((struct _VHD_DYNAMIC_DISK_HEADER_PACKED *)v76));
  v23 = (-(int)v8 & (unsigned int)(v8 + v22 + 4 * v10 - 1)) - (unsigned int)v22;
  *(_QWORD *)v74 = v23;
  v24 = (void *)ExAllocatePool2(256, v23, 1648642134);
  v67 = v24;
  if ( !v24 )
    goto LABEL_25;
  *(_QWORD *)v70 = v22;
  memset(v24, 255, v23);
  v25 = v23 + v22;
  if ( !*((_QWORD *)v11 + 11) )
  {
    P = 0;
    if ( !*((_QWORD *)v11 + 12) )
      goto LABEL_64;
  }
  AsyncOpOverrideStatus = VhdmpiInitializeInternalIoContext(v65, 0);
  if ( AsyncOpOverrideStatus < 0 )
    goto LABEL_37;
  P = (PVOID)ExAllocatePool2(64, (unsigned int)(v5 + 2 * v8), 1430538326);
  if ( P )
  {
    v26 = *(struct _VHD_ASYNC_OP_CONTEXT **)v68;
    *((_QWORD *)v68 + 2) = v69;
    AsyncOpOverrideStatus = VhdmpiGetAsyncOpOverrideStatus(v26);
    if ( AsyncOpOverrideStatus < 0 )
    {
      if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 8) )
      {
        v29 = 1045;
LABEL_34:
        TraceEvents(
          "VhdmpiVhd1InitializeNewNonFlatVhd",
          v29,
          2u,
          v28,
          "VhdmpiVhd1InitializeNewNonFlatVhd: create canceled");
      }
LABEL_35:
      v30 = P;
LABEL_36:
      ExFreePoolWithTag(v30, 0x55444856u);
      goto LABEL_37;
    }
    v32 = 0;
    if ( v27 )
    {
      do
      {
        v33 = *((_QWORD *)v11 + 13);
        v34 = v32 * *(_QWORD *)v73;
        if ( v32 * *(_QWORD *)v73 >= v33 )
          break;
        v35 = v33 - v34;
        if ( *(_QWORD *)v73 < v35 )
          LODWORD(v35) = v73[0];
        AsyncOpOverrideStatus = VhdmpiReadFromSource(
                                  *((_QWORD *)v66 + 11),
                                  *((_QWORD *)v66 + 12),
                                  v32 * *(_QWORD *)v73,
                                  (unsigned int)v35,
                                  v65,
                                  2,
                                  *((_QWORD *)v66 + 10));
        if ( AsyncOpOverrideStatus < 0 )
        {
          if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 8) )
          {
            LODWORD(v58) = AsyncOpOverrideStatus;
            TraceEvents(
              "VhdmpiVhd1InitializeNewNonFlatVhd",
              0x439u,
              2u,
              v45,
              "VhdmpiVhd1InitializeNewNonFlatVhd: failed to read from source at offset 0x%I64x(0x%08x).",
              v34,
              v58);
          }
          goto LABEL_35;
        }
        if ( (unsigned int)v35 < v64 )
          VhdmpiMarkInternalIoBufferMissing(v65, (unsigned int)v35, v64 - (unsigned int)v35);
        AsyncOpOverrideStatus = VhdmpiGetAsyncOpOverrideStatus(*(struct _VHD_ASYNC_OP_CONTEXT **)v68);
        if ( AsyncOpOverrideStatus < 0 )
        {
          if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 8) )
          {
            v29 = 1103;
            goto LABEL_34;
          }
          goto LABEL_35;
        }
        v37 = (unsigned __int8 *)P + v62;
        VhdmpiConstructPresenceBitmapForIoContext(v65, v36, v37 - 512, v60, &v59);
        if ( v59
          || v60[0]
          && *(_DWORD *)v66 == 2
          && ((v38 = (struct _VHD_BACKING_STORE_HEADER *)*((_QWORD *)v66 + 7)) == 0
           || VhdmpiVhd1IsAnyPortionOfRangeDefinedInChain(v38, v34, v35)) )
        {
          v39 = v64;
          AsyncOpOverrideStatus = VhdmpiConstructDataForIoContext(v65, v64, v37);
          if ( AsyncOpOverrideStatus < 0 )
            goto LABEL_35;
          v40 = v62;
          v41 = v62 + v39;
          AsyncOpOverrideStatus = VhdmpiMetadataSynchronousIo(
                                    (struct _VHD_BACKING_STORE_HEADER *)((char *)a1 + 72),
                                    a1,
                                    4u,
                                    P,
                                    v41 + v62,
                                    v25);
          if ( AsyncOpOverrideStatus < 0 )
          {
            if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 8) )
            {
              LODWORD(v58) = AsyncOpOverrideStatus;
              TraceEvents(
                "VhdmpiVhd1InitializeNewNonFlatVhd",
                0x481u,
                2u,
                v44,
                "Vhdmpivhd1InitializeNewNonFlatVhd: failed to write to offset 0x%I64x(0x%08x).",
                v25,
                v58);
            }
            goto LABEL_35;
          }
          *((_DWORD *)v67 + v32) = _byteswap_ulong((v25 + v40 - 512) >> 9);
          v25 += v41;
        }
        v42 = (struct _VHD_ASYNC_OP_CONTEXT **)v68;
        if ( v32 > *((_QWORD *)v68 + 1) )
          *((_QWORD *)v68 + 1) = v32;
        AsyncOpOverrideStatus = VhdmpiGetAsyncOpOverrideStatus(*v42);
        if ( AsyncOpOverrideStatus < 0 )
        {
          if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 8) )
          {
            v29 = 1184;
            goto LABEL_34;
          }
          goto LABEL_35;
        }
        v11 = v66;
        ++v32;
      }
      while ( v32 < v69 );
    }
    LODWORD(v8) = v62;
LABEL_64:
    AsyncOpOverrideStatus = VhdmpiMetadataSynchronousIo(
                              (struct _VHD_BACKING_STORE_HEADER *)((char *)a1 + 72),
                              a1,
                              4u,
                              v76,
                              0x400u,
                              0x200u);
    if ( AsyncOpOverrideStatus < 0 )
    {
      if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 8) )
      {
        LODWORD(v58) = AsyncOpOverrideStatus;
        TraceEvents(
          "VhdmpiVhd1InitializeNewNonFlatVhd",
          0x4B6u,
          2u,
          v43,
          "VhdmpiVhd1InitializeNewNonFlatVhd: failed to write dynamic header to offset 0x%I64x(0x%08x).",
          512,
          v58);
      }
      goto LABEL_102;
    }
    if ( (unsigned int)dword_1400876D0 <= 5 )
    {
      v48 = *(_QWORD *)v70;
    }
    else
    {
      v46 = tlgKeywordOn(&dword_1400876D0, 8);
      v48 = *(_QWORD *)v70;
      if ( v46 )
        TraceEvents(
          "VhdmpiVhd1InitializeNewNonFlatVhd",
          0x4C2u,
          v47 - 3,
          v47,
          "VhdmpiVhd1InitializeNewNonFlatVhd: writing BAT @ 0x%I64x",
          *(_QWORD *)v70);
    }
    AsyncOpOverrideStatus = VhdmpiMetadataSynchronousIo(
                              (struct _VHD_BACKING_STORE_HEADER *)((char *)a1 + 72),
                              a1,
                              4u,
                              v67,
                              v74[0],
                              v48);
    if ( AsyncOpOverrideStatus >= 0 )
    {
      v52 = v75;
      AsyncOpOverrideStatus = VhdmpiMetadataSynchronousIo(
                                (struct _VHD_BACKING_STORE_HEADER *)((char *)a1 + 72),
                                a1,
                                4u,
                                v75,
                                0x200u,
                                0);
      if ( AsyncOpOverrideStatus >= 0 )
      {
        VhdFileSize = VhdmpiGetVhdFileSize(a1, &v72);
        v54 = v72;
        if ( VhdFileSize < 0 )
          v54 = 0;
        v55 = ~(*((unsigned int *)a1 + 481) - 1LL) & (*((unsigned int *)a1 + 481) + v54 - 1);
        if ( (unsigned int)v8 + v25 - 512 >= v55 - 512 )
          v55 = (unsigned int)v8 + v25;
        v56 = v55 - 512;
        AsyncOpOverrideStatus = VhdmpiMetadataSynchronousIo(
                                  (struct _VHD_BACKING_STORE_HEADER *)((char *)a1 + 72),
                                  a1,
                                  4u,
                                  v52,
                                  0x200u,
                                  v55 - 512);
        if ( AsyncOpOverrideStatus >= 0
          || (unsigned int)dword_1400876D0 <= 2
          || !(unsigned __int8)tlgKeywordOn(&dword_1400876D0, 8) )
        {
LABEL_102:
          v30 = P;
          if ( !P )
            goto LABEL_37;
          goto LABEL_36;
        }
        LODWORD(v58) = AsyncOpOverrideStatus;
        v50 = "VhdmpiVhd1InitializeNewNonFlatVhd: failed to write footer to offset 0x%I64x(0x%08x).";
        *(_QWORD *)v57 = v56;
        v51 = 1323;
      }
      else
      {
        if ( (unsigned int)dword_1400876D0 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_1400876D0, 8) )
          goto LABEL_102;
        LODWORD(v58) = AsyncOpOverrideStatus;
        v50 = "VhdmpiVhd1InitializeNewNonFlatVhd: failed to write header to offset 0x%I64x(0x%08x).";
        *(_QWORD *)v57 = 0;
        v51 = 1256;
      }
    }
    else
    {
      if ( (unsigned int)dword_1400876D0 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_1400876D0, 8) )
        goto LABEL_102;
      LODWORD(v58) = AsyncOpOverrideStatus;
      v50 = "VhdmpiVhd1InitializeNewNonFlatVhd: failed to write BAT to offset 0x%I64x(0x%08x).";
      *(_QWORD *)v57 = v48;
      v51 = 1232;
    }
    TraceEvents("VhdmpiVhd1InitializeNewNonFlatVhd", v51, 2u, v49, v50, *(_QWORD *)v57, v58);
    goto LABEL_102;
  }
LABEL_25:
  AsyncOpOverrideStatus = -1073741670;
LABEL_37:
  v17 = Pool2;
LABEL_38:
  VhdmpiCleanupInternalIoContext(v65);
  if ( v67 )
    ExFreePoolWithTag(v67, 0x62444856u);
  if ( v17 )
    ExFreePoolWithTag(v17, 0x7A444856u);
  return (unsigned int)AsyncOpOverrideStatus;
}

```

## disassembly

```asm
0x1400c08c4  push    rbp
0x1400c08c6  push    rbx
0x1400c08c7  push    rsi
0x1400c08c8  push    rdi
0x1400c08c9  push    r12
0x1400c08cb  push    r13
0x1400c08cd  push    r14
0x1400c08cf  push    r15
0x1400c08d1  lea     rbp, [rsp-3E8h]
0x1400c08d9  sub     rsp, 4E8h
0x1400c08e0  mov     rax, cs:__security_cookie
0x1400c08e7  xor     rax, rsp
0x1400c08ea  mov     [rbp+420h+var_50], rax
0x1400c08f1  mov     r15d, [r9+4]
0x1400c08f5  xor     r14d, r14d
0x1400c08f8  mov     rax, [rbp+420h+arg_20]
0x1400c08ff  mov     r13, rcx
0x1400c0902  mov     rbx, [r9+38h]
0x1400c0906  cmp     r15d, 200000h
0x1400c090d  mov     [rbp+420h+var_460], rax
0x1400c0911  mov     r12d, 1000h
0x1400c0917  mov     [rbp+420h+var_4A0], rdx
0x1400c091b  mov     eax, 200h
0x1400c0920  cmovnz  r12d, eax
0x1400c0924  mov     [rsp+520h+var_4B8], r8
0x1400c0929  mov     [rcx+784h], r12d
0x1400c0930  xor     edx, edx
0x1400c0932  mov     rax, [r9+30h]
0x1400c0936  lea     rcx, [r15-1]
0x1400c093a  dec     rax
0x1400c093d  mov     [rsp+520h+var_4B0], r9
0x1400c0942  add     rax, r15
0x1400c0945  mov     [rbp+420h+var_478], r14
0x1400c0949  not     rcx
0x1400c094c  mov     [rsp+520h+var_4DF], r14b
0x1400c0951  and     rax, rcx
0x1400c0954  mov     [rsp+520h+var_4E0], r14b
0x1400c0959  div     r15
0x1400c095c  xorps   xmm0, xmm0
0x1400c095f  mov     [rsp+520h+var_4C0], r15d
0x1400c0964  xor     edx, edx; Val
0x1400c0966  mov     [rbp+420h+var_498], rax
0x1400c096a  mov     r8d, 400h; Size
0x1400c0970  mov     [rsp+520h+var_4D0], r12d
0x1400c0975  lea     rcx, [rbp+420h+var_450]; void *
0x1400c0979  mov     qword ptr [rbp+420h+var_470], r15
0x1400c097d  mov     rdi, rax
0x1400c0980  mov     rsi, r9
0x1400c0983  movups  xmmword ptr [rbp+420h+DestinationString.Length], xmm0
0x1400c0987  call    memset
0x1400c098c  mov     eax, edi
0x1400c098e  mov     [rbp+420h+var_450], 70737863h
0x1400c0995  bswap   eax
0x1400c0997  mov     [rbp+420h+var_434], eax
0x1400c099a  lea     edx, [r14+8]
0x1400c099e  mov     eax, r15d
0x1400c09a1  mov     [rbp+420h+var_44C], 65737261h
0x1400c09a8  bswap   eax
0x1400c09aa  mov     [rbp+420h+var_430], eax
0x1400c09ad  mov     eax, cs:dword_1400876D0
0x1400c09b3  mov     [rbp+420h+var_448], 0FFFFFFFFFFFFFFFFh
0x1400c09bb  mov     [rbp+420h+var_438], 100h
0x1400c09c2  cmp     eax, 5
0x1400c09c5  jbe     short loc_1400C0A10
0x1400c09c7  lea     rcx, dword_1400876D0
0x1400c09ce  call    _tlgKeywordOn
0x1400c09d3  test    al, al
0x1400c09d5  jz      short loc_1400C0A10
0x1400c09d7  mov     rax, [rsi+30h]
0x1400c09db  lea     r8d, [r14+5]; int
0x1400c09df  mov     [rsp+520h+var_4E8], rdi
0x1400c09e4  mov     ecx, 2F0h
0x1400c09e9  mov     dword ptr [rsp+520h+var_4F0], r15d
0x1400c09ee  mov     r9d, edx; int
0x1400c09f1  mov     qword ptr [rsp+520h+var_4F8], rax; char
0x1400c09f6  mov     edx, ecx; int
0x1400c09f8  lea     rax, aVhdmpivhd1init_13; "VhdmpiVhd1InitializeNewNonFlatVhd: Virt"...
0x1400c09ff  lea     rcx, aVhdmpivhd1init_18; "VhdmpiVhd1InitializeNewNonFlatVhd"
0x1400c0a06  mov     [rsp+520h+var_500], rax; char *
0x1400c0a0b  call    TraceEvents
0x1400c0a10  test    rbx, rbx
0x1400c0a13  jz      loc_1400C0C06
0x1400c0a19  movups  xmm0, xmmword ptr [rbx+7CCh]
0x1400c0a20  lea     rdi, [rbx+48h]
0x1400c0a24  mov     [rsp+520h+var_4A8], r14
0x1400c0a29  lea     r14d, [r12-1]
0x1400c0a2e  mov     r8d, 7A444856h
0x1400c0a34  movdqu  [rbp+420h+var_428], xmm0
0x1400c0a39  mov     eax, [rbx+7A0h]
0x1400c0a3f  not     r14d
0x1400c0a42  bswap   eax
0x1400c0a44  mov     [rbp+420h+var_418], eax
0x1400c0a47  movzx   ecx, word ptr [rdi]
0x1400c0a4a  add     ecx, 0Bh
0x1400c0a4d  add     ecx, r12d
0x1400c0a50  and     ecx, r14d
0x1400c0a53  mov     ebx, ecx
0x1400c0a55  mov     edx, ecx
0x1400c0a57  mov     ecx, 40h ; '@'
0x1400c0a5c  call    cs:__imp_ExAllocatePool2
0x1400c0a63  nop     dword ptr [rax+rax+00h]
0x1400c0a68  mov     [rsp+520h+var_4C8], rax
0x1400c0a6d  mov     rsi, rax
0x1400c0a70  test    rax, rax
0x1400c0a73  jnz     short loc_1400C0A7F
0x1400c0a75  mov     ebx, 0C000009Ah
0x1400c0a7a  jmp     loc_1400C0D75
0x1400c0a7f  mov     eax, 0FFFEh
0x1400c0a84  mov     [rbp+420h+DestinationString.Buffer], rsi
0x1400c0a88  cmp     ebx, eax
0x1400c0a8a  lea     rcx, [rbp+420h+DestinationString]; DestinationString
0x1400c0a8e  mov     rdx, rdi; SourceString
0x1400c0a91  cmova   ebx, eax
0x1400c0a94  xor     eax, eax
0x1400c0a96  mov     [rbp+420h+DestinationString.Length], ax
0x1400c0a9a  mov     [rbp+420h+DestinationString.MaximumLength], bx
0x1400c0a9e  call    cs:__imp_RtlCopyUnicodeString
0x1400c0aa5  nop     dword ptr [rax+rax+00h]
0x1400c0aaa  lea     rcx, [rbp+420h+DestinationString]
0x1400c0aae  call    VhdmpiMakeLongPathDecorationAppropriate
0x1400c0ab3  test    eax, eax
0x1400c0ab5  jns     short loc_1400C0AC1
0x1400c0ab7  mov     ebx, 0C0000106h
0x1400c0abc  jmp     loc_1400C0D75
0x1400c0ac1  movzx   edx, [rbp+420h+DestinationString.Length]
0x1400c0ac5  lea     rsi, [r12-1]
0x1400c0aca  mov     eax, r12d
0x1400c0acd  not     rsi
0x1400c0ad0  add     rax, 5FFh
0x1400c0ad6  mov     [rbp+420h+var_210], 756B3257h
0x1400c0ae0  and     rsi, rax
0x1400c0ae3  mov     ecx, edx
0x1400c0ae5  lea     edi, [rdx-1]
0x1400c0ae8  add     edi, r12d
0x1400c0aeb  and     edi, r14d
0x1400c0aee  mov     eax, edi
0x1400c0af0  bswap   eax
0x1400c0af2  mov     [rbp+420h+var_20C], eax
0x1400c0af8  mov     rax, rsi
0x1400c0afb  bswap   rax
0x1400c0afe  mov     [rbp+420h+var_200], rax
0x1400c0b05  mov     eax, 200h
0x1400c0b0a  mov     r8d, eax
0x1400c0b0d  bswap   ecx
0x1400c0b0f  mov     [rbp+420h+var_208], ecx
0x1400c0b15  cmp     ax, dx
0x1400c0b18  jb      short loc_1400C0B1D
0x1400c0b1a  mov     r8d, edx; Size
0x1400c0b1d  mov     rdx, [rbp+420h+DestinationString.Buffer]; Src
0x1400c0b21  lea     rcx, [rbp+420h+var_410]; void *
0x1400c0b25  call    memmove
0x1400c0b2a  mov     eax, cs:dword_1400876D0
0x1400c0b30  mov     r14d, 8
0x1400c0b36  cmp     eax, 5
0x1400c0b39  jbe     short loc_1400C0B77
0x1400c0b3b  mov     edx, r14d
0x1400c0b3e  lea     rcx, dword_1400876D0
0x1400c0b45  call    _tlgKeywordOn
0x1400c0b4a  test    al, al
0x1400c0b4c  jz      short loc_1400C0B77
0x1400c0b4e  lea     rax, aVhdmpivhd1init_17; "VhdmpiVhd1InitializeNewNonFlatVhd: writ"...
0x1400c0b55  mov     qword ptr [rsp+520h+var_4F8], rsi; char
0x1400c0b5a  mov     edx, 368h; int
0x1400c0b5f  mov     [rsp+520h+var_500], rax; char *
0x1400c0b64  mov     r9d, r14d; int
0x1400c0b67  lea     r8d, [r14-3]; int
0x1400c0b6b  lea     rcx, aVhdmpivhd1init_18; "VhdmpiVhd1InitializeNewNonFlatVhd"
0x1400c0b72  call    TraceEvents
0x1400c0b77  mov     r9, [rsp+520h+var_4C8]; void *
0x1400c0b7c  lea     rcx, [r13+48h]; struct _VHD_FILE_WRAPPER *
0x1400c0b80  mov     qword ptr [rsp+520h+var_4F8], rsi; unsigned __int64
0x1400c0b85  mov     r8b, 4; unsigned __int8
0x1400c0b88  mov     rdx, r13; struct _VHD_BACKING_STORE_HEADER *
0x1400c0b8b  mov     dword ptr [rsp+520h+var_500], edi; unsigned int
0x1400c0b8f  call    ?VhdmpiMetadataSynchronousIo@@YAJPEAU_VHD_FILE_WRAPPER@@PEAU_VHD_BACKING_STORE_HEADER@@EPEAXK_K@Z; VhdmpiMetadataSynchronousIo(_VHD_FILE_WRAPPER *,_VHD_BACKING_STORE_HEADER *,uchar,void *,ulong,unsigned __int64)
0x1400c0b94  mov     ebx, eax
0x1400c0b96  test    eax, eax
0x1400c0b98  jns     short loc_1400C0BF5
0x1400c0b9a  mov     ecx, cs:dword_1400876D0
0x1400c0ba0  mov     edi, 2
0x1400c0ba5  cmp     ecx, edi
0x1400c0ba7  jbe     loc_1400C0D70
0x1400c0bad  mov     rdx, r14
0x1400c0bb0  lea     rcx, dword_1400876D0
0x1400c0bb7  call    _tlgKeywordOn
0x1400c0bbc  test    al, al
0x1400c0bbe  jz      loc_1400C0D70
0x1400c0bc4  mov     dword ptr [rsp+520h+var_4F0], ebx
0x1400c0bc8  lea     rax, aVhdmpivhd1init_3; "VhdmpiVhd1InitializeNewNonFlatVhd: fail"...
0x1400c0bcf  mov     qword ptr [rsp+520h+var_4F8], rsi; char
0x1400c0bd4  lea     rcx, aVhdmpivhd1init_18; "VhdmpiVhd1InitializeNewNonFlatVhd"
0x1400c0bdb  mov     edx, 377h; int
0x1400c0be0  mov     [rsp+520h+var_500], rax; char *
0x1400c0be5  mov     r9d, r14d; int
0x1400c0be8  mov     r8d, edi; int
0x1400c0beb  call    TraceEvents
0x1400c0bf0  jmp     loc_1400C0D70
0x1400c0bf5  mov     r14d, edi
0x1400c0bf8  mov     rdi, [rbp+420h+var_498]
0x1400c0bfc  add     r14, rsi
0x1400c0bff  mov     rsi, [rsp+520h+var_4B0]
0x1400c0c04  jmp     short loc_1400C0C11
0x1400c0c06  mov     [rsp+520h+var_4C8], r14
0x1400c0c0b  mov     r14d, 600h
0x1400c0c11  mov     rax, r14
0x1400c0c14  lea     rcx, [rbp+420h+var_450]; struct _VHD_DYNAMIC_DISK_HEADER_PACKED *
0x1400c0c18  bswap   rax
0x1400c0c1b  mov     [rbp+420h+var_440], rax
0x1400c0c1f  call    ?VhdmpiCalculateSparseHeaderChecksum@@YAKPEAU_VHD_DYNAMIC_DISK_HEADER_PACKED@@@Z; VhdmpiCalculateSparseHeaderChecksum(_VHD_DYNAMIC_DISK_HEADER_PACKED *)
0x1400c0c24  bswap   eax
0x1400c0c26  mov     [rbp+420h+var_42C], eax
0x1400c0c29  lea     ecx, ds:0FFFFFFFFFFFFFFFFh[rdi*4]
0x1400c0c30  add     ecx, r14d
0x1400c0c33  mov     eax, r12d
0x1400c0c36  add     ecx, r12d
0x1400c0c39  neg     eax
0x1400c0c3b  and     ecx, eax
0x1400c0c3d  mov     r8d, 62444856h
0x1400c0c43  sub     ecx, r14d
0x1400c0c46  mov     ebx, ecx
0x1400c0c48  mov     edx, ecx
0x1400c0c4a  mov     ecx, 100h
0x1400c0c4f  mov     qword ptr [rbp+420h+var_468], rbx
0x1400c0c53  call    cs:__imp_ExAllocatePool2
0x1400c0c5a  nop     dword ptr [rax+rax+00h]
0x1400c0c5f  mov     [rsp+520h+var_4A8], rax
0x1400c0c64  test    rax, rax
0x1400c0c67  jnz     short loc_1400C0C73
0x1400c0c69  mov     ebx, 0C000009Ah
0x1400c0c6e  jmp     loc_1400C0D70
0x1400c0c73  mov     r8, rbx; Size
0x1400c0c76  mov     qword ptr [rbp+420h+var_490], r14
0x1400c0c7a  mov     edx, 0FFh; Val
0x1400c0c7f  mov     rcx, rax; void *
0x1400c0c82  call    memset
0x1400c0c87  mov     rax, [rsi+58h]
0x1400c0c8b  xor     ecx, ecx
0x1400c0c8d  add     r14, rbx
0x1400c0c90  mov     edi, 2
0x1400c0c95  test    rax, rax
0x1400c0c98  jnz     short loc_1400C0CAC
0x1400c0c9a  mov     [rsp+520h+P], rcx
0x1400c0c9f  cmp     [rsi+60h], rcx
0x1400c0ca3  jz      loc_1400C0F7C
0x1400c0ca9  test    rax, rax
0x1400c0cac  mov     r9, [rsi+48h]
0x1400c0cb0  setnz   r8b
0x1400c0cb4  mov     [rsp+520h+var_500], rcx; __int64
0x1400c0cb9  mov     edx, r15d
0x1400c0cbc  mov     rcx, [rsp+520h+var_4B8]; void *
0x1400c0cc1  call    VhdmpiInitializeInternalIoContext
0x1400c0cc6  mov     ebx, eax
0x1400c0cc8  test    eax, eax
0x1400c0cca  js      loc_1400C0D70
0x1400c0cd0  lea     edx, [r15+r12*2]
0x1400c0cd4  mov     ecx, 40h ; '@'
0x1400c0cd9  mov     r8d, 55444856h
0x1400c0cdf  call    cs:__imp_ExAllocatePool2
0x1400c0ce6  nop     dword ptr [rax+rax+00h]
0x1400c0ceb  mov     [rsp+520h+P], rax
0x1400c0cf0  test    rax, rax
0x1400c0cf3  jz      loc_1400C0C69
0x1400c0cf9  mov     rdx, [rbp+420h+var_4A0]
0x1400c0cfd  mov     r8, [rbp+420h+var_498]
0x1400c0d01  mov     rcx, [rdx]; struct _VHD_ASYNC_OP_CONTEXT *
0x1400c0d04  mov     [rdx+10h], r8
0x1400c0d08  call    ?VhdmpiGetAsyncOpOverrideStatus@@YAJPEAU_VHD_ASYNC_OP_CONTEXT@@@Z; VhdmpiGetAsyncOpOverrideStatus(_VHD_ASYNC_OP_CONTEXT *)
0x1400c0d0d  mov     ebx, eax
0x1400c0d0f  test    eax, eax
0x1400c0d11  jns     loc_1400C0DDC
0x1400c0d17  mov     eax, cs:dword_1400876D0
0x1400c0d1d  cmp     eax, edi
0x1400c0d1f  jbe     short loc_1400C0D5A
0x1400c0d21  mov     r9d, 8
0x1400c0d27  lea     rcx, dword_1400876D0
0x1400c0d2e  mov     edx, r9d
0x1400c0d31  call    _tlgKeywordOn
0x1400c0d36  test    al, al
0x1400c0d38  jz      short loc_1400C0D5A
0x1400c0d3a  mov     edx, 415h; int
0x1400c0d3f  lea     rax, aVhdmpivhd1init; "VhdmpiVhd1InitializeNewNonFlatVhd: crea"...
0x1400c0d46  mov     r8d, edi; int
0x1400c0d49  lea     rcx, aVhdmpivhd1init_18; "VhdmpiVhd1InitializeNewNonFlatVhd"
0x1400c0d50  mov     [rsp+520h+var_500], rax; char *
0x1400c0d55  call    TraceEvents
0x1400c0d5a  mov     rcx, [rsp+520h+P]; P
0x1400c0d5f  mov     edx, 55444856h; Tag
0x1400c0d64  call    cs:__imp_ExFreePoolWithTag
0x1400c0d6b  nop     dword ptr [rax+rax+00h]
0x1400c0d70  mov     rsi, [rsp+520h+var_4C8]
0x1400c0d75  mov     rcx, [rsp+520h+var_4B8]; void *
0x1400c0d7a  call    VhdmpiCleanupInternalIoContext
0x1400c0d7f  mov     rax, [rsp+520h+var_4A8]
0x1400c0d84  test    rax, rax
0x1400c0d87  jz      short loc_1400C0D9D
0x1400c0d89  mov     edx, 62444856h; Tag
0x1400c0d8e  mov     rcx, rax; P
0x1400c0d91  call    cs:__imp_ExFreePoolWithTag
0x1400c0d98  nop     dword ptr [rax+rax+00h]
0x1400c0d9d  test    rsi, rsi
  ... truncated ...
```
