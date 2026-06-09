# VhdmpiVhd1InitializeNewNonFlatVhd(_VHD_BACKING_STORE_HEADER *,_VHD_ASYNC_OP_PROGRESS *,_VHD_INTERNAL_IO_CONTEXT *,_VHDMP_POPULATE_PARAMETERS *,_VHD_DISK_FOOTER_PACKED *)

- ea: `0x1400c08d4`
- end: `0x1400c1307`
- name: `?VhdmpiVhd1InitializeNewNonFlatVhd@@YAJPEAU_VHD_BACKING_STORE_HEADER@@PEAU_VHD_ASYNC_OP_PROGRESS@@PEAU_VHD_INTERNAL_IO_CONTEXT@@PEAU_VHDMP_POPULATE_PARAMETERS@@PEAU_VHD_DISK_FOOTER_PACKED@@@Z`
- size: `2611`
- prototype: `__int64 __usercall@<rax>(struct _VHD_BACKING_STORE_HEADER *@<rcx>, struct _VHD_ASYNC_OP_PROGRESS *@<rdx>, struct _VHD_INTERNAL_IO_CONTEXT *@<r8>, struct _VHDMP_POPULATE_PARAMETERS *@<r9>, struct _VHD_DISK_FOOTER_PACKED *)`
- caller_count: `1`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x1400c15f0`

## callees

- `0x140019310`
- `0x140021908`
- `0x140023560`
- `0x140025c68`
- `0x140033598`
- `0x140033998`
- `0x140035e94`
- `0x14003bfac`
- `0x14003ed20`
- `0x14003ede4`
- `0x14005d7c0`
- `0x14005da00`
- `0x14005dd00`
- `0x1400b2d44`
- `0x1400b6cbc`
- `0x1400c08d4`
- `0x1400e0a14`
- `0x1400e7d68`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x1400c0aae`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400c0aae`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c0d74`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c0da1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c0dba`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c0d74`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c0da1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c0dba`
- `ntoskrnl!ExAllocatePool2` at `0x1400c0a6c`
- `ntoskrnl!ExAllocatePool2` at `0x1400c0c63`
- `ntoskrnl!ExAllocatePool2` at `0x1400c0cef`
- `ntoskrnl!ExAllocatePool2` at `0x1400c0a6c`
- `ntoskrnl!ExAllocatePool2` at `0x1400c0c63`
- `ntoskrnl!ExAllocatePool2` at `0x1400c0cef`

## string_xrefs

- `0x1400c1218`: `VhdmpiVhd1InitializeNewNonFlatVhd: failed to write header to offset 0x%I64x(0x%08x).`
- `0x1400c11ab`: `VhdmpiVhd1InitializeNewNonFlatVhd: failed to write BAT to offset 0x%I64x(0x%08x).`
- `0x1400c12ca`: `VhdmpiVhd1InitializeNewNonFlatVhd: failed to write footer to offset 0x%I64x(0x%08x).`
- `0x1400c0d4f`: `VhdmpiVhd1InitializeNewNonFlatVhd: create canceled`
- `0x1400c0bd8`: `VhdmpiVhd1InitializeNewNonFlatVhd: failed to write parent locator to offset 0x%I64x(0x%08x).`
- `0x1400c1068`: `Vhdmpivhd1InitializeNewNonFlatVhd: failed to write to offset 0x%I64x(0x%08x).`
- `0x1400c10f6`: `VhdmpiVhd1InitializeNewNonFlatVhd: failed to read from source at offset 0x%I64x(0x%08x).`
- `0x1400c0fee`: `VhdmpiVhd1InitializeNewNonFlatVhd: failed to write dynamic header to offset 0x%I64x(0x%08x).`

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
  if ( (unsigned int)dword_140087708 > 5 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 8) )
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
    if ( (unsigned int)dword_140087708 > 5 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 8) )
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
      if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 8) )
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
      if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 8) )
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
          if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 8) )
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
          if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 8) )
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
            if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 8) )
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
          if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 8) )
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
      if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 8) )
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
    if ( (unsigned int)dword_140087708 <= 5 )
    {
      v48 = *(_QWORD *)v70;
    }
    else
    {
      v46 = tlgKeywordOn(&dword_140087708, 8);
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
          || (unsigned int)dword_140087708 <= 2
          || !(unsigned __int8)tlgKeywordOn(&dword_140087708, 8) )
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
        if ( (unsigned int)dword_140087708 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140087708, 8) )
          goto LABEL_102;
        LODWORD(v58) = AsyncOpOverrideStatus;
        v50 = "VhdmpiVhd1InitializeNewNonFlatVhd: failed to write header to offset 0x%I64x(0x%08x).";
        *(_QWORD *)v57 = 0;
        v51 = 1256;
      }
    }
    else
    {
      if ( (unsigned int)dword_140087708 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140087708, 8) )
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
0x1400c08d4  push    rbp
0x1400c08d6  push    rbx
0x1400c08d7  push    rsi
0x1400c08d8  push    rdi
0x1400c08d9  push    r12
0x1400c08db  push    r13
0x1400c08dd  push    r14
0x1400c08df  push    r15
0x1400c08e1  lea     rbp, [rsp-3E8h]
0x1400c08e9  sub     rsp, 4E8h
0x1400c08f0  mov     rax, cs:__security_cookie
0x1400c08f7  xor     rax, rsp
0x1400c08fa  mov     [rbp+420h+var_50], rax
0x1400c0901  mov     r15d, [r9+4]
0x1400c0905  xor     r14d, r14d
0x1400c0908  mov     rax, [rbp+420h+arg_20]
0x1400c090f  mov     r13, rcx
0x1400c0912  mov     rbx, [r9+38h]
0x1400c0916  cmp     r15d, 200000h
0x1400c091d  mov     [rbp+420h+var_460], rax
0x1400c0921  mov     r12d, 1000h
0x1400c0927  mov     [rbp+420h+var_4A0], rdx
0x1400c092b  mov     eax, 200h
0x1400c0930  cmovnz  r12d, eax
0x1400c0934  mov     [rsp+520h+var_4B8], r8
0x1400c0939  mov     [rcx+784h], r12d
0x1400c0940  xor     edx, edx
0x1400c0942  mov     rax, [r9+30h]
0x1400c0946  lea     rcx, [r15-1]
0x1400c094a  dec     rax
0x1400c094d  mov     [rsp+520h+var_4B0], r9
0x1400c0952  add     rax, r15
0x1400c0955  mov     [rbp+420h+var_478], r14
0x1400c0959  not     rcx
0x1400c095c  mov     [rsp+520h+var_4DF], r14b
0x1400c0961  and     rax, rcx
0x1400c0964  mov     [rsp+520h+var_4E0], r14b
0x1400c0969  div     r15
0x1400c096c  xorps   xmm0, xmm0
0x1400c096f  mov     [rsp+520h+var_4C0], r15d
0x1400c0974  xor     edx, edx; Val
0x1400c0976  mov     [rbp+420h+var_498], rax
0x1400c097a  mov     r8d, 400h; Size
0x1400c0980  mov     [rsp+520h+var_4D0], r12d
0x1400c0985  lea     rcx, [rbp+420h+var_450]; void *
0x1400c0989  mov     qword ptr [rbp+420h+var_470], r15
0x1400c098d  mov     rdi, rax
0x1400c0990  mov     rsi, r9
0x1400c0993  movups  xmmword ptr [rbp+420h+DestinationString.Length], xmm0
0x1400c0997  call    memset
0x1400c099c  mov     eax, edi
0x1400c099e  mov     [rbp+420h+var_450], 70737863h
0x1400c09a5  bswap   eax
0x1400c09a7  mov     [rbp+420h+var_434], eax
0x1400c09aa  lea     edx, [r14+8]
0x1400c09ae  mov     eax, r15d
0x1400c09b1  mov     [rbp+420h+var_44C], 65737261h
0x1400c09b8  bswap   eax
0x1400c09ba  mov     [rbp+420h+var_430], eax
0x1400c09bd  mov     eax, cs:dword_140087708
0x1400c09c3  mov     [rbp+420h+var_448], 0FFFFFFFFFFFFFFFFh
0x1400c09cb  mov     [rbp+420h+var_438], 100h
0x1400c09d2  cmp     eax, 5
0x1400c09d5  jbe     short loc_1400C0A20
0x1400c09d7  lea     rcx, dword_140087708
0x1400c09de  call    _tlgKeywordOn
0x1400c09e3  test    al, al
0x1400c09e5  jz      short loc_1400C0A20
0x1400c09e7  mov     rax, [rsi+30h]
0x1400c09eb  lea     r8d, [r14+5]; int
0x1400c09ef  mov     [rsp+520h+var_4E8], rdi
0x1400c09f4  mov     ecx, 2F0h
0x1400c09f9  mov     dword ptr [rsp+520h+var_4F0], r15d
0x1400c09fe  mov     r9d, edx; int
0x1400c0a01  mov     qword ptr [rsp+520h+var_4F8], rax; char
0x1400c0a06  mov     edx, ecx; int
0x1400c0a08  lea     rax, aVhdmpivhd1init_13; "VhdmpiVhd1InitializeNewNonFlatVhd: Virt"...
0x1400c0a0f  lea     rcx, aVhdmpivhd1init_18; "VhdmpiVhd1InitializeNewNonFlatVhd"
0x1400c0a16  mov     [rsp+520h+var_500], rax; char *
0x1400c0a1b  call    TraceEvents
0x1400c0a20  test    rbx, rbx
0x1400c0a23  jz      loc_1400C0C16
0x1400c0a29  movups  xmm0, xmmword ptr [rbx+7CCh]
0x1400c0a30  lea     rdi, [rbx+48h]
0x1400c0a34  mov     [rsp+520h+var_4A8], r14
0x1400c0a39  lea     r14d, [r12-1]
0x1400c0a3e  mov     r8d, 7A444856h
0x1400c0a44  movdqu  [rbp+420h+var_428], xmm0
0x1400c0a49  mov     eax, [rbx+7A0h]
0x1400c0a4f  not     r14d
0x1400c0a52  bswap   eax
0x1400c0a54  mov     [rbp+420h+var_418], eax
0x1400c0a57  movzx   ecx, word ptr [rdi]
0x1400c0a5a  add     ecx, 0Bh
0x1400c0a5d  add     ecx, r12d
0x1400c0a60  and     ecx, r14d
0x1400c0a63  mov     ebx, ecx
0x1400c0a65  mov     edx, ecx
0x1400c0a67  mov     ecx, 40h ; '@'
0x1400c0a6c  call    cs:__imp_ExAllocatePool2
0x1400c0a73  nop     dword ptr [rax+rax+00h]
0x1400c0a78  mov     [rsp+520h+var_4C8], rax
0x1400c0a7d  mov     rsi, rax
0x1400c0a80  test    rax, rax
0x1400c0a83  jnz     short loc_1400C0A8F
0x1400c0a85  mov     ebx, 0C000009Ah
0x1400c0a8a  jmp     loc_1400C0D85
0x1400c0a8f  mov     eax, 0FFFEh
0x1400c0a94  mov     [rbp+420h+DestinationString.Buffer], rsi
0x1400c0a98  cmp     ebx, eax
0x1400c0a9a  lea     rcx, [rbp+420h+DestinationString]; DestinationString
0x1400c0a9e  mov     rdx, rdi; SourceString
0x1400c0aa1  cmova   ebx, eax
0x1400c0aa4  xor     eax, eax
0x1400c0aa6  mov     [rbp+420h+DestinationString.Length], ax
0x1400c0aaa  mov     [rbp+420h+DestinationString.MaximumLength], bx
0x1400c0aae  call    cs:__imp_RtlCopyUnicodeString
0x1400c0ab5  nop     dword ptr [rax+rax+00h]
0x1400c0aba  lea     rcx, [rbp+420h+DestinationString]
0x1400c0abe  call    VhdmpiMakeLongPathDecorationAppropriate
0x1400c0ac3  test    eax, eax
0x1400c0ac5  jns     short loc_1400C0AD1
0x1400c0ac7  mov     ebx, 0C0000106h
0x1400c0acc  jmp     loc_1400C0D85
0x1400c0ad1  movzx   edx, [rbp+420h+DestinationString.Length]
0x1400c0ad5  lea     rsi, [r12-1]
0x1400c0ada  mov     eax, r12d
0x1400c0add  not     rsi
0x1400c0ae0  add     rax, 5FFh
0x1400c0ae6  mov     [rbp+420h+var_210], 756B3257h
0x1400c0af0  and     rsi, rax
0x1400c0af3  mov     ecx, edx
0x1400c0af5  lea     edi, [rdx-1]
0x1400c0af8  add     edi, r12d
0x1400c0afb  and     edi, r14d
0x1400c0afe  mov     eax, edi
0x1400c0b00  bswap   eax
0x1400c0b02  mov     [rbp+420h+var_20C], eax
0x1400c0b08  mov     rax, rsi
0x1400c0b0b  bswap   rax
0x1400c0b0e  mov     [rbp+420h+var_200], rax
0x1400c0b15  mov     eax, 200h
0x1400c0b1a  mov     r8d, eax
0x1400c0b1d  bswap   ecx
0x1400c0b1f  mov     [rbp+420h+var_208], ecx
0x1400c0b25  cmp     ax, dx
0x1400c0b28  jb      short loc_1400C0B2D
0x1400c0b2a  mov     r8d, edx; Size
0x1400c0b2d  mov     rdx, [rbp+420h+DestinationString.Buffer]; Src
0x1400c0b31  lea     rcx, [rbp+420h+var_410]; void *
0x1400c0b35  call    memmove
0x1400c0b3a  mov     eax, cs:dword_140087708
0x1400c0b40  mov     r14d, 8
0x1400c0b46  cmp     eax, 5
0x1400c0b49  jbe     short loc_1400C0B87
0x1400c0b4b  mov     edx, r14d
0x1400c0b4e  lea     rcx, dword_140087708
0x1400c0b55  call    _tlgKeywordOn
0x1400c0b5a  test    al, al
0x1400c0b5c  jz      short loc_1400C0B87
0x1400c0b5e  lea     rax, aVhdmpivhd1init_17; "VhdmpiVhd1InitializeNewNonFlatVhd: writ"...
0x1400c0b65  mov     qword ptr [rsp+520h+var_4F8], rsi; char
0x1400c0b6a  mov     edx, 368h; int
0x1400c0b6f  mov     [rsp+520h+var_500], rax; char *
0x1400c0b74  mov     r9d, r14d; int
0x1400c0b77  lea     r8d, [r14-3]; int
0x1400c0b7b  lea     rcx, aVhdmpivhd1init_18; "VhdmpiVhd1InitializeNewNonFlatVhd"
0x1400c0b82  call    TraceEvents
0x1400c0b87  mov     r9, [rsp+520h+var_4C8]; void *
0x1400c0b8c  lea     rcx, [r13+48h]; struct _VHD_FILE_WRAPPER *
0x1400c0b90  mov     qword ptr [rsp+520h+var_4F8], rsi; unsigned __int64
0x1400c0b95  mov     r8b, 4; unsigned __int8
0x1400c0b98  mov     rdx, r13; struct _VHD_BACKING_STORE_HEADER *
0x1400c0b9b  mov     dword ptr [rsp+520h+var_500], edi; unsigned int
0x1400c0b9f  call    ?VhdmpiMetadataSynchronousIo@@YAJPEAU_VHD_FILE_WRAPPER@@PEAU_VHD_BACKING_STORE_HEADER@@EPEAXK_K@Z; VhdmpiMetadataSynchronousIo(_VHD_FILE_WRAPPER *,_VHD_BACKING_STORE_HEADER *,uchar,void *,ulong,unsigned __int64)
0x1400c0ba4  mov     ebx, eax
0x1400c0ba6  test    eax, eax
0x1400c0ba8  jns     short loc_1400C0C05
0x1400c0baa  mov     ecx, cs:dword_140087708
0x1400c0bb0  mov     edi, 2
0x1400c0bb5  cmp     ecx, edi
0x1400c0bb7  jbe     loc_1400C0D80
0x1400c0bbd  mov     rdx, r14
0x1400c0bc0  lea     rcx, dword_140087708
0x1400c0bc7  call    _tlgKeywordOn
0x1400c0bcc  test    al, al
0x1400c0bce  jz      loc_1400C0D80
0x1400c0bd4  mov     dword ptr [rsp+520h+var_4F0], ebx
0x1400c0bd8  lea     rax, aVhdmpivhd1init_3; "VhdmpiVhd1InitializeNewNonFlatVhd: fail"...
0x1400c0bdf  mov     qword ptr [rsp+520h+var_4F8], rsi; char
0x1400c0be4  lea     rcx, aVhdmpivhd1init_18; "VhdmpiVhd1InitializeNewNonFlatVhd"
0x1400c0beb  mov     edx, 377h; int
0x1400c0bf0  mov     [rsp+520h+var_500], rax; char *
0x1400c0bf5  mov     r9d, r14d; int
0x1400c0bf8  mov     r8d, edi; int
0x1400c0bfb  call    TraceEvents
0x1400c0c00  jmp     loc_1400C0D80
0x1400c0c05  mov     r14d, edi
0x1400c0c08  mov     rdi, [rbp+420h+var_498]
0x1400c0c0c  add     r14, rsi
0x1400c0c0f  mov     rsi, [rsp+520h+var_4B0]
0x1400c0c14  jmp     short loc_1400C0C21
0x1400c0c16  mov     [rsp+520h+var_4C8], r14
0x1400c0c1b  mov     r14d, 600h
0x1400c0c21  mov     rax, r14
0x1400c0c24  lea     rcx, [rbp+420h+var_450]; struct _VHD_DYNAMIC_DISK_HEADER_PACKED *
0x1400c0c28  bswap   rax
0x1400c0c2b  mov     [rbp+420h+var_440], rax
0x1400c0c2f  call    ?VhdmpiCalculateSparseHeaderChecksum@@YAKPEAU_VHD_DYNAMIC_DISK_HEADER_PACKED@@@Z; VhdmpiCalculateSparseHeaderChecksum(_VHD_DYNAMIC_DISK_HEADER_PACKED *)
0x1400c0c34  bswap   eax
0x1400c0c36  mov     [rbp+420h+var_42C], eax
0x1400c0c39  lea     ecx, ds:0FFFFFFFFFFFFFFFFh[rdi*4]
0x1400c0c40  add     ecx, r14d
0x1400c0c43  mov     eax, r12d
0x1400c0c46  add     ecx, r12d
0x1400c0c49  neg     eax
0x1400c0c4b  and     ecx, eax
0x1400c0c4d  mov     r8d, 62444856h
0x1400c0c53  sub     ecx, r14d
0x1400c0c56  mov     ebx, ecx
0x1400c0c58  mov     edx, ecx
0x1400c0c5a  mov     ecx, 100h
0x1400c0c5f  mov     qword ptr [rbp+420h+var_468], rbx
0x1400c0c63  call    cs:__imp_ExAllocatePool2
0x1400c0c6a  nop     dword ptr [rax+rax+00h]
0x1400c0c6f  mov     [rsp+520h+var_4A8], rax
0x1400c0c74  test    rax, rax
0x1400c0c77  jnz     short loc_1400C0C83
0x1400c0c79  mov     ebx, 0C000009Ah
0x1400c0c7e  jmp     loc_1400C0D80
0x1400c0c83  mov     r8, rbx; Size
0x1400c0c86  mov     qword ptr [rbp+420h+var_490], r14
0x1400c0c8a  mov     edx, 0FFh; Val
0x1400c0c8f  mov     rcx, rax; void *
0x1400c0c92  call    memset
0x1400c0c97  mov     rax, [rsi+58h]
0x1400c0c9b  xor     ecx, ecx
0x1400c0c9d  add     r14, rbx
0x1400c0ca0  mov     edi, 2
0x1400c0ca5  test    rax, rax
0x1400c0ca8  jnz     short loc_1400C0CBC
0x1400c0caa  mov     [rsp+520h+P], rcx
0x1400c0caf  cmp     [rsi+60h], rcx
0x1400c0cb3  jz      loc_1400C0F8C
0x1400c0cb9  test    rax, rax
0x1400c0cbc  mov     r9, [rsi+48h]
0x1400c0cc0  setnz   r8b
0x1400c0cc4  mov     [rsp+520h+var_500], rcx; __int64
0x1400c0cc9  mov     edx, r15d
0x1400c0ccc  mov     rcx, [rsp+520h+var_4B8]; void *
0x1400c0cd1  call    VhdmpiInitializeInternalIoContext
0x1400c0cd6  mov     ebx, eax
0x1400c0cd8  test    eax, eax
0x1400c0cda  js      loc_1400C0D80
0x1400c0ce0  lea     edx, [r15+r12*2]
0x1400c0ce4  mov     ecx, 40h ; '@'
0x1400c0ce9  mov     r8d, 55444856h
0x1400c0cef  call    cs:__imp_ExAllocatePool2
0x1400c0cf6  nop     dword ptr [rax+rax+00h]
0x1400c0cfb  mov     [rsp+520h+P], rax
0x1400c0d00  test    rax, rax
0x1400c0d03  jz      loc_1400C0C79
0x1400c0d09  mov     rdx, [rbp+420h+var_4A0]
0x1400c0d0d  mov     r8, [rbp+420h+var_498]
0x1400c0d11  mov     rcx, [rdx]; struct _VHD_ASYNC_OP_CONTEXT *
0x1400c0d14  mov     [rdx+10h], r8
0x1400c0d18  call    ?VhdmpiGetAsyncOpOverrideStatus@@YAJPEAU_VHD_ASYNC_OP_CONTEXT@@@Z; VhdmpiGetAsyncOpOverrideStatus(_VHD_ASYNC_OP_CONTEXT *)
0x1400c0d1d  mov     ebx, eax
0x1400c0d1f  test    eax, eax
0x1400c0d21  jns     loc_1400C0DEC
0x1400c0d27  mov     eax, cs:dword_140087708
0x1400c0d2d  cmp     eax, edi
0x1400c0d2f  jbe     short loc_1400C0D6A
0x1400c0d31  mov     r9d, 8
0x1400c0d37  lea     rcx, dword_140087708
0x1400c0d3e  mov     edx, r9d
0x1400c0d41  call    _tlgKeywordOn
0x1400c0d46  test    al, al
0x1400c0d48  jz      short loc_1400C0D6A
0x1400c0d4a  mov     edx, 415h; int
0x1400c0d4f  lea     rax, aVhdmpivhd1init; "VhdmpiVhd1InitializeNewNonFlatVhd: crea"...
0x1400c0d56  mov     r8d, edi; int
0x1400c0d59  lea     rcx, aVhdmpivhd1init_18; "VhdmpiVhd1InitializeNewNonFlatVhd"
0x1400c0d60  mov     [rsp+520h+var_500], rax; char *
0x1400c0d65  call    TraceEvents
0x1400c0d6a  mov     rcx, [rsp+520h+P]; P
0x1400c0d6f  mov     edx, 55444856h; Tag
0x1400c0d74  call    cs:__imp_ExFreePoolWithTag
0x1400c0d7b  nop     dword ptr [rax+rax+00h]
0x1400c0d80  mov     rsi, [rsp+520h+var_4C8]
0x1400c0d85  mov     rcx, [rsp+520h+var_4B8]; void *
0x1400c0d8a  call    VhdmpiCleanupInternalIoContext
0x1400c0d8f  mov     rax, [rsp+520h+var_4A8]
0x1400c0d94  test    rax, rax
0x1400c0d97  jz      short loc_1400C0DAD
0x1400c0d99  mov     edx, 62444856h; Tag
0x1400c0d9e  mov     rcx, rax; P
0x1400c0da1  call    cs:__imp_ExFreePoolWithTag
0x1400c0da8  nop     dword ptr [rax+rax+00h]
0x1400c0dad  test    rsi, rsi
  ... truncated ...
```
