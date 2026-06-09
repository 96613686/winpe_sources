# VhdmpiEnableTracking

- ea: `0x140029b04`
- end: `0x14002a522`
- name: `VhdmpiEnableTracking`
- size: `2590`
- prototype: `__int64 __fastcall(struct _VHD_HANDLE_CONTEXT *)`
- caller_count: `1`
- callee_count: `24`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14001a608`

## callees

- `0x140019674`
- `0x14001bc1c`
- `0x14001c088`
- `0x14001f9ac`
- `0x140020c94`
- `0x14002269c`
- `0x140023980`
- `0x140029854`
- `0x140029918`
- `0x1400299ec`
- `0x140029b04`
- `0x14002aa08`
- `0x14002dcc4`
- `0x14002ded0`
- `0x140036284`
- `0x1400408f4`
- `0x140049f50`
- `0x14005dbb0`
- `0x14005dce0`
- `0x1400a41d0`
- `0x1400a6fa4`
- `0x1400a7078`
- `0x1400a7c58`
- `0x1400c78d0`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140029b7f`
- `ntoskrnl!RtlInitUnicodeString` at `0x140029b91`
- `ntoskrnl!RtlInitUnicodeString` at `0x140029b7f`
- `ntoskrnl!RtlInitUnicodeString` at `0x140029b91`
- `ntoskrnl!ExFreePoolWithTag` at `0x140029f87`
- `ntoskrnl!ExFreePoolWithTag` at `0x140029fa4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140029f87`
- `ntoskrnl!ExFreePoolWithTag` at `0x140029fa4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002a34d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002a34d`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002a378`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002a378`

## string_xrefs

- `0x140029cce`: `VhdmpiEnableTracking: access is denied. Context = %p. VirtualDisk = %p`
- `0x140029c66`: `VhdmpiEnableTracking: Failure getting VhdFilePath. Context = %p. VirtualDisk = %p`
- `0x140029dca`: `VhdmpiEnableTracking: Incorrect FilePathOffset = %d. Context = %p. VirtualDisk = %p`
- `0x140029e5f`: `VhdmpiEnableTracking: Couldn't create new EnableTracking request from VhdSet. Context = %p. VirtualDisk = %p`
- `0x14002a0d2`: `VhdmpiEnableTracking: Couldn't get absolute path for the log file. Context = %p. VirtualDisk = %p`
- `0x140029f38`: `VhdmpiEnableTracking: Unable to delete leaf snapshot information (0x%08x).                     Context = %p. VirtualDisk = %p`

## pseudocode

```c
__int64 __fastcall VhdmpiEnableTracking(struct _VHD_HANDLE_CONTEXT *a1, _QWORD *a2)
{
  __int64 v2; // r12
  __int64 v3; // rsi
  __int64 v6; // r13
  unsigned int v7; // edx
  int EnableTrackingRequest; // edi
  int v9; // r8d
  unsigned int v10; // ebx
  PVOID v11; // r14
  unsigned int v12; // r12d
  struct _STORAGE_ENABLE_TRACKING_VIRTUAL_DISK_V2_REQUEST *v13; // rdi
  struct _VHDS_STATE *v14; // rcx
  int v15; // r9d
  int v17; // ebx
  bool v18; // zf
  int v19; // eax
  int v20; // edx
  int v21; // ecx
  const wchar_t *v22; // r12
  unsigned int v23; // ebx
  unsigned __int64 v24; // rax
  KIRQL v25; // al
  int v26; // edx
  int v27; // ecx
  const wchar_t *v28; // rdx
  __int64 v29; // r9
  const wchar_t *v30; // rcx
  __int64 v31; // r9
  signed __int32 v32[8]; // [rsp+0h] [rbp-B9h] BYREF
  char *v33; // [rsp+20h] [rbp-99h]
  PUNICODE_STRING v34; // [rsp+28h] [rbp-91h]
  int v35[2]; // [rsp+38h] [rbp-81h]
  __int64 v36; // [rsp+50h] [rbp-69h] BYREF
  __int64 v37; // [rsp+58h] [rbp-61h] BYREF
  int FeatureFlags; // [rsp+60h] [rbp-59h]
  char v39[4]; // [rsp+64h] [rbp-55h] BYREF
  PVOID P; // [rsp+68h] [rbp-51h] BYREF
  PVOID v41; // [rsp+70h] [rbp-49h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+78h] [rbp-41h] BYREF
  UNICODE_STRING Source; // [rsp+88h] [rbp-31h] BYREF
  struct _UNICODE_STRING v44; // [rsp+98h] [rbp-21h] BYREF
  __int128 v45; // [rsp+A8h] [rbp-11h]
  __int16 v46; // [rsp+B8h] [rbp-1h]
  int v47; // [rsp+BAh] [rbp+1h]
  __int16 v48; // [rsp+BEh] [rbp+5h]
  __int128 Buf1; // [rsp+C0h] [rbp+7h] BYREF

  v2 = a2[23];
  a2[7] = 0;
  v3 = *((_QWORD *)a1 + 7);
  v41 = 0;
  v37 = 0;
  v44 = 0;
  v6 = 0;
  LODWORD(v36) = 1;
  Source = 0;
  *(_DWORD *)v39 = 0;
  DestinationString = 0;
  P = 0;
  Buf1 = 0;
  RtlInitUnicodeString(&DestinationString, 0);
  RtlInitUnicodeString(&Source, 0);
  VhdmpiAcquirePassiveLockShared(v3 + 128);
  if ( (unsigned int)dword_1400876D0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 4) )
    TraceEvents(
      "VhdmpiEnableTracking",
      0x13Fu,
      v7,
      v7,
      "VhdmpiEnableTracking called for file %S. Context = %p. VirtualDisk = %p",
      *(const wchar_t **)(*(_QWORD *)(v3 + 144) + 120LL),
      a1,
      (const void *)v3);
  EnableTrackingRequest = VhdmpiDuplicateFilePath(0);
  VhdmpiReleasePassiveLockShared(v3 + 128);
  if ( EnableTrackingRequest < 0 )
  {
    if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 4) )
      TraceEvents(
        "VhdmpiEnableTracking",
        0x150u,
        v9 + 2,
        v9 + 4,
        "VhdmpiEnableTracking: Failure getting VhdFilePath. Context = %p. VirtualDisk = %p",
        a1,
        (const void *)v3);
    goto LABEL_35;
  }
  if ( (*((_DWORD *)a1 + 1) & 1) != 0 && (*((_DWORD *)a1 + 2) & 0x200000) == 0 )
  {
    if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 4) )
      TraceEvents(
        "VhdmpiEnableTracking",
        0x161u,
        2u,
        4u,
        "VhdmpiEnableTracking: access is denied. Context = %p. VirtualDisk = %p",
        a1,
        (const void *)v3);
    EnableTrackingRequest = -1073741790;
    goto LABEL_35;
  }
  v10 = *(_DWORD *)(v2 + 16);
  if ( v10 < 0x28 )
  {
    if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 4) )
      TraceEvents(
        "VhdmpiEnableTracking",
        0x174u,
        2u,
        4u,
        "VhdmpiEnableTracking: input buffer too small. Context = %p. VirtualDisk = %p",
        a1,
        (const void *)v3);
    EnableTrackingRequest = -1073741306;
    goto LABEL_35;
  }
  v11 = (PVOID)a2[3];
  FeatureFlags = 0;
  v12 = *(_DWORD *)v11;
  if ( *(_DWORD *)v11 == 64 && v10 >= 0x40 )
  {
    v13 = (struct _STORAGE_ENABLE_TRACKING_VIRTUAL_DISK_V2_REQUEST *)v11;
    LOBYTE(v6) = *(_BYTE *)(*((_QWORD *)a1 + 7) + 93LL) != 0;
    if ( !*((_BYTE *)v11 + 32) )
      FeatureFlags = VhdmpiCtGetFeatureFlags((struct _VHD_VIRTUAL_DISK *)v3, *((_DWORD *)v11 + 10));
LABEL_29:
    VhdmpiAcquirePassiveLock(v3 + 1888);
    BYTE2(v36) = 1;
    if ( (_BYTE)v6 )
    {
      EnableTrackingRequest = VhdmpiCtCreateEnableTrackingRequest(
                                a1,
                                v13,
                                (struct _STORAGE_ENABLE_TRACKING_VIRTUAL_DISK_V2_REQUEST **)&v41);
      if ( EnableTrackingRequest < 0 )
      {
        if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 4) )
          TraceEvents(
            "VhdmpiEnableTracking",
            0x1B1u,
            2u,
            4u,
            "VhdmpiEnableTracking: Couldn't create new EnableTracking request from VhdSet. Context = %p. VirtualDisk = %p",
            a1,
            v3);
        goto LABEL_34;
      }
    }
    if ( v41 )
    {
      v11 = v41;
      v10 = *(_DWORD *)v41 + *((_DWORD *)v41 + 1);
      if ( v10 < *(_DWORD *)v41 )
      {
        EnableTrackingRequest = -1073741675;
LABEL_34:
        v6 = v37;
        goto LABEL_35;
      }
    }
    if ( !VhdmpiValidateFileName(
            (__int64)v11,
            v12,
            v10,
            *((_DWORD *)v11 + 1),
            *(_DWORD *)v11,
            &v44,
            (char)"VhdmpiEnableTracking: ") )
    {
      EnableTrackingRequest = -1073741811;
      goto LABEL_34;
    }
    EnableTrackingRequest = VhdmpiCtGetAbsoluteLogFilePath(&Source, &v44, &DestinationString.Length);
    if ( EnableTrackingRequest < 0 )
    {
      if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 4) )
        TraceEvents(
          "VhdmpiEnableTracking",
          0x1E2u,
          2u,
          4u,
          "VhdmpiEnableTracking: Couldn't get absolute path for the log file. Context = %p. VirtualDisk = %p",
          a1,
          v3);
      goto LABEL_34;
    }
    v17 = VhdmpiCTGetVhdFileTimeAndDataWriteGuid(v3, v39, &Buf1, &P);
    VhdmpiAcquirePassiveLock(v3 + 1872);
    v18 = *(_DWORD *)(v3 + 1856) == 2;
    BYTE1(v36) = 1;
    if ( !v18 )
    {
      if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 4) )
        TraceEvents(
          "VhdmpiEnableTracking",
          0x203u,
          2u,
          4u,
          "VhdmpiEnableTracking: state is not disabled, Context = %p. VirtualDisk = %p",
          a1,
          (const void *)v3);
      EnableTrackingRequest = -1069940701;
      goto LABEL_34;
    }
    if ( *(_BYTE *)(v3 + 2080) )
    {
      if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 4) )
        TraceEvents(
          "VhdmpiEnableTracking",
          0x214u,
          2u,
          4u,
          "VhdmpiEnableTracking: CT Log operations are not allowed.Context = %p. VirtualDisk = %p",
          a1,
          (const void *)v3);
      EnableTrackingRequest = -2147483631;
      goto LABEL_34;
    }
    if ( (_BYTE)v6 && !*((_BYTE *)v11 + 32) )
    {
      EnableTrackingRequest = VhdmpiPrepareAndCommitCdpSnapshot(*((struct _VHDS_STATE **)a1 + 38));
      if ( EnableTrackingRequest < 0 )
      {
        if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 4) )
          TraceEvents(
            "VhdmpiEnableTracking",
            0x236u,
            2u,
            4u,
            "VhdmpiEnableTracking: Couldn't persist EnableTracking request in VhdSet. Context = %p. VirtualDisk = %p",
            a1,
            v3);
        goto LABEL_34;
      }
      BYTE3(v36) = 1;
    }
    v19 = VhdmpiCTLogCreateBackingStore(
            &DestinationString,
            *((_BYTE *)v11 + 32),
            (__int64)v11 + 16,
            (__int64)&VhdmpZeroGuid,
            (struct _VHD_HANDLE_CONTEXT *)((char *)a1 + 248),
            (char *)&v36,
            (const void **)&v37,
            FeatureFlags);
    v6 = v37;
    EnableTrackingRequest = v19;
    if ( !v37 )
    {
      if ( !(_BYTE)v36 )
        EnableTrackingRequest = -1069940700;
      goto LABEL_35;
    }
    EnableTrackingRequest = VhdmpiCTLogInitVirtualDiskForTracking((struct _VHD_VIRTUAL_DISK *)v3);
    if ( EnableTrackingRequest < 0 )
      goto LABEL_35;
    v22 = L" ";
    if ( !*((_BYTE *)v11 + 32) )
      goto LABEL_91;
    if ( v17 < 0 )
    {
      if ( (Microsoft_Windows_VHDMPEnableBits & 4) != 0 )
      {
        v30 = L" ";
        v31 = *(_QWORD *)(v6 + 32);
        *(_QWORD *)v35 = *(unsigned int *)(v6 + 176);
        if ( P )
          v30 = (const wchar_t *)P;
        McTemplateK0zzqxx_EtwWriteTransfer((_DWORD)v30, v20, (_DWORD)P, v31, (__int64)v30, v17, 0, v35[0]);
      }
      if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 4) )
        TraceEvents(
          "VhdmpiEnableTracking",
          0x2B7u,
          2u,
          4u,
          "VhdmpiEnableTracking: NtQueryInformationFile failed with error ... (0x%08x). Context = %p. VirtualDisk = %p",
          v17,
          a1,
          (const void *)v3);
    }
    else
    {
      v23 = *(_DWORD *)v39;
      if ( !*(_BYTE *)(*(_QWORD *)(v3 + 32) + 52LL)
        || (*(_DWORD *)(v6 + 92) & 0xFFFF0000) < 0x20000 && !memcmp((const void *)(v6 + 194), &VhdmpZeroGuid, 0x10u) )
      {
        if ( v23 <= *(_DWORD *)(v6 + 176) )
          goto LABEL_91;
      }
      else if ( !memcmp(&Buf1, (const void *)(v6 + 194), 0x10u) )
      {
LABEL_91:
        v24 = *((_QWORD *)v11 + 1);
        if ( v24 && *(_QWORD *)(v6 + 56) > v24 )
          EnableTrackingRequest = -1069940703;
        goto LABEL_94;
      }
      if ( (Microsoft_Windows_VHDMPEnableBits & 4) != 0 )
      {
        v28 = L" ";
        v29 = *(_QWORD *)(v6 + 32);
        *(_QWORD *)v35 = *(unsigned int *)(v6 + 176);
        if ( P )
          v28 = (const wchar_t *)P;
        McTemplateK0zzqxx_EtwWriteTransfer(v21, (_DWORD)v28, (_DWORD)P, v29, (__int64)v28, 34, v23, v35[0]);
      }
      if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 4) )
        TraceEvents(
          "VhdmpiEnableTracking",
          0x29Bu,
          2u,
          4u,
          "VhdmpiEnableTracking: VHD is changed offline. VHD time:(0x%08x) Logfile time:(0x%08x) Status:(0x%08x)Context ="
          " %p. VirtualDisk = %p",
          v23,
          *(_DWORD *)(v6 + 176),
          -1069940702,
          a1,
          (const void *)v3);
    }
    EnableTrackingRequest = -1069940702;
LABEL_94:
    if ( *((_BYTE *)v11 + 32) )
      *(_QWORD *)(v3 + 2016) = *(_QWORD *)(v6 + 180);
    v25 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v3 + 1864));
    *(_QWORD *)(v3 + 1536) = v6;
    *(_QWORD *)(v6 + 72) = v3;
    _InterlockedOr(v32, 0);
    *(_DWORD *)(v3 + 1856) = 1;
    KeReleaseSpinLock((PKSPIN_LOCK)(v3 + 1864), v25);
    *(_QWORD *)(v3 + 1904) = *((_QWORD *)v11 + 1);
    if ( (Microsoft_Windows_VHDMPEnableBits & 8) != 0 )
    {
      v34 = *(PUNICODE_STRING *)(v6 + 32);
      if ( P )
        LODWORD(v22) = (_DWORD)P;
      McTemplateK0zxz_EtwWriteTransfer(v27, v26, (_DWORD)P, (_DWORD)v22, (_DWORD)v33, (__int64)v34);
    }
    if ( EnableTrackingRequest < 0 )
      VhdmpiCTLogProcessTrackingError(v3, (unsigned int)EnableTrackingRequest);
    EnableTrackingRequest = 0;
    goto LABEL_35;
  }
  if ( v12 == 40 )
  {
    v13 = 0;
    goto LABEL_29;
  }
  if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 4) )
    TraceEvents(
      "VhdmpiEnableTracking",
      0x18Au,
      2u,
      4u,
      "VhdmpiEnableTracking: Incorrect FilePathOffset = %d. Context = %p. VirtualDisk = %p",
      v12,
      a1,
      (const void *)v3);
  EnableTrackingRequest = -1073741811;
LABEL_35:
  VhdmpiFreeFilePath(&DestinationString);
  VhdmpiFreeFilePath(&Source);
  if ( BYTE1(v36) )
    VhdmpiReleasePassiveLock(v3 + 1872);
  if ( BYTE2(v36) )
    VhdmpiReleasePassiveLock(v3 + 1888);
  if ( EnableTrackingRequest < 0 )
  {
    if ( BYTE3(v36) )
    {
      v14 = (struct _VHDS_STATE *)*((_QWORD *)a1 + 38);
      v47 = 0;
      v48 = 0;
      v46 = 3;
      v45 = *(_OWORD *)&VhdmpZeroGuid;
      if ( (int)VhdmpiDeleteSnapshotInternal(v14) < 0
        && (unsigned int)dword_1400876D0 > 2
        && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 4) )
      {
        TraceEvents(
          "VhdmpiEnableTracking",
          0x31Eu,
          2u,
          4u,
          "VhdmpiEnableTracking: Unable to delete leaf snapshot information (0x%08x).                     Context = %p. VirtualDisk = %p",
          v15,
          a1,
          (const void *)v3);
      }
    }
    if ( v6 )
      VhdmpiCTLogCloseBackingStore((struct _CTLOG_BACKING_STORE *)v6);
  }
  if ( P )
    ExFreePoolWithTag(P, 0x7A444856u);
  if ( v41 )
    ExFreePoolWithTag(v41, 0x68444856u);
  if ( (unsigned int)dword_1400876D0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 4) )
    TraceEvents(
      "VhdmpiEnableTracking",
      0x33Cu,
      4u,
      4u,
      "VhdmpiEnableTracking: leaving... (0x%08x). Context = %p. VirtualDisk = %p",
      EnableTrackingRequest,
      a1,
      (const void *)v3);
  return (unsigned int)EnableTrackingRequest;
}

```

## disassembly

```asm
0x140029b04  mov     [rsp-8+arg_10], rbx
0x140029b09  push    rbp
0x140029b0a  push    rsi
0x140029b0b  push    rdi
0x140029b0c  push    r12
0x140029b0e  push    r13
0x140029b10  push    r14
0x140029b12  push    r15
0x140029b14  lea     rbp, [rsp-27h]
0x140029b19  sub     rsp, 0E0h
0x140029b20  mov     rax, cs:__security_cookie
0x140029b27  xor     rax, rsp
0x140029b2a  mov     [rbp+57h+var_40], rax
0x140029b2e  mov     r12, [rdx+0B8h]
0x140029b35  xor     edi, edi
0x140029b37  mov     [rdx+38h], rdi
0x140029b3b  xorps   xmm0, xmm0
0x140029b3e  mov     rsi, [rcx+38h]
0x140029b42  xorps   xmm1, xmm1
0x140029b45  mov     r14, rdx
0x140029b48  mov     [rbp+57h+var_A0], rdi
0x140029b4c  mov     r15, rcx
0x140029b4f  mov     [rbp+57h+var_B8], rdi
0x140029b53  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140029b57  mov     byte ptr [rbp+57h+var_C0+1], dil
0x140029b5b  xor     edx, edx; SourceString
0x140029b5d  mov     byte ptr [rbp+57h+var_C0+2], dil
0x140029b61  movups  xmmword ptr [rbp+57h+var_78.Length], xmm0
0x140029b65  mov     r13d, edi
0x140029b68  mov     byte ptr [rbp+57h+var_C0], 1
0x140029b6c  movups  xmmword ptr [rbp+57h+Source.Length], xmm1
0x140029b70  mov     dword ptr [rbp+57h+var_AC], edi
0x140029b73  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140029b77  mov     [rbp+57h+P], rdi
0x140029b7b  movups  [rbp+57h+Buf1], xmm1
0x140029b7f  call    cs:__imp_RtlInitUnicodeString
0x140029b86  nop     dword ptr [rax+rax+00h]
0x140029b8b  xor     edx, edx; SourceString
0x140029b8d  lea     rcx, [rbp+57h+Source]; DestinationString
0x140029b91  call    cs:__imp_RtlInitUnicodeString
0x140029b98  nop     dword ptr [rax+rax+00h]
0x140029b9d  lea     rbx, [rsi+80h]
0x140029ba4  mov     byte ptr [rbp+57h+var_C0+3], dil
0x140029ba8  mov     rcx, rbx
0x140029bab  call    VhdmpiAcquirePassiveLockShared
0x140029bb0  mov     eax, cs:dword_1400876D0
0x140029bb6  lea     edx, [rdi+4]
0x140029bb9  cmp     eax, edx
0x140029bbb  jbe     short loc_140029C0C
0x140029bbd  lea     rcx, dword_1400876D0
0x140029bc4  call    _tlgKeywordOn
0x140029bc9  test    al, al
0x140029bcb  jz      short loc_140029C0C
0x140029bcd  mov     rax, [rsi+90h]
0x140029bd4  mov     ecx, 13Fh
0x140029bd9  mov     qword ptr [rsp+110h+var_D8], rsi
0x140029bde  mov     r9d, edx; int
0x140029be1  mov     qword ptr [rsp+110h+var_E0], r15
0x140029be6  mov     r8d, edx; int
0x140029be9  mov     edx, ecx; int
0x140029beb  lea     rcx, aVhdmpienabletr_4; "VhdmpiEnableTracking"
0x140029bf2  mov     rax, [rax+78h]
0x140029bf6  mov     [rsp+110h+var_E8], rax; char
0x140029bfb  lea     rax, aVhdmpienabletr_14; "VhdmpiEnableTracking called for file %S"...
0x140029c02  mov     [rsp+110h+var_F0], rax; char *
0x140029c07  call    TraceEvents
0x140029c0c  mov     rdx, [rsi+90h]
0x140029c13  lea     r9, [rbp+57h+Source]
0x140029c17  add     rdx, 48h ; 'H'
0x140029c1b  xor     r8d, r8d
0x140029c1e  xor     ecx, ecx; Source
0x140029c20  call    VhdmpiDuplicateFilePath
0x140029c25  mov     rcx, rbx
0x140029c28  mov     edi, eax
0x140029c2a  call    VhdmpiReleasePassiveLockShared
0x140029c2f  xor     r8d, r8d
0x140029c32  test    edi, edi
0x140029c34  jns     short loc_140029C91
0x140029c36  mov     ecx, cs:dword_1400876D0
0x140029c3c  cmp     ecx, 2
0x140029c3f  jbe     loc_140029E8F
0x140029c45  lea     edx, [r8+4]
0x140029c49  lea     rcx, dword_1400876D0
0x140029c50  call    _tlgKeywordOn
0x140029c55  test    al, al
0x140029c57  jz      loc_140029E8F
0x140029c5d  lea     r9d, [r8+4]; int
0x140029c61  mov     qword ptr [rsp+110h+var_E0], rsi
0x140029c66  lea     rax, aVhdmpienabletr; "VhdmpiEnableTracking: Failure getting V"...
0x140029c6d  mov     [rsp+110h+var_E8], r15; char
0x140029c72  lea     r8d, [r9-2]; int
0x140029c76  mov     [rsp+110h+var_F0], rax; char *
0x140029c7b  mov     edx, 150h; int
0x140029c80  lea     rcx, aVhdmpienabletr_4; "VhdmpiEnableTracking"
0x140029c87  call    TraceEvents
0x140029c8c  jmp     loc_140029E8F
0x140029c91  mov     eax, [r15+4]
0x140029c95  test    al, 1
0x140029c97  jz      short loc_140029CFE
0x140029c99  test    dword ptr [r15+8], 200000h
0x140029ca1  jnz     short loc_140029CFE
0x140029ca3  mov     eax, cs:dword_1400876D0
0x140029ca9  cmp     eax, 2
0x140029cac  jbe     short loc_140029CF4
0x140029cae  mov     edx, 4
0x140029cb3  lea     rcx, dword_1400876D0
0x140029cba  call    _tlgKeywordOn
0x140029cbf  test    al, al
0x140029cc1  jz      short loc_140029CF4
0x140029cc3  mov     r9d, 4; int
0x140029cc9  mov     qword ptr [rsp+110h+var_E0], rsi
0x140029cce  lea     rax, aVhdmpienabletr_13; "VhdmpiEnableTracking: access is denied."...
0x140029cd5  mov     [rsp+110h+var_E8], r15; char
0x140029cda  mov     edx, 161h; int
0x140029cdf  mov     [rsp+110h+var_F0], rax; char *
0x140029ce4  lea     rcx, aVhdmpienabletr_4; "VhdmpiEnableTracking"
0x140029ceb  lea     r8d, [r9-2]; int
0x140029cef  call    TraceEvents
0x140029cf4  mov     edi, 0C0000022h
0x140029cf9  jmp     loc_140029E8F
0x140029cfe  mov     ebx, [r12+10h]
0x140029d03  cmp     ebx, 28h ; '('
0x140029d06  jnb     short loc_140029D63
0x140029d08  mov     eax, cs:dword_1400876D0
0x140029d0e  cmp     eax, 2
0x140029d11  jbe     short loc_140029D59
0x140029d13  mov     edx, 4
0x140029d18  lea     rcx, dword_1400876D0
0x140029d1f  call    _tlgKeywordOn
0x140029d24  test    al, al
0x140029d26  jz      short loc_140029D59
0x140029d28  mov     r9d, 4; int
0x140029d2e  mov     qword ptr [rsp+110h+var_E0], rsi
0x140029d33  lea     rax, aVhdmpienabletr_5; "VhdmpiEnableTracking: input buffer too "...
0x140029d3a  mov     [rsp+110h+var_E8], r15; char
0x140029d3f  mov     edx, 174h; int
0x140029d44  mov     [rsp+110h+var_F0], rax; char *
0x140029d49  lea     rcx, aVhdmpienabletr_4; "VhdmpiEnableTracking"
0x140029d50  lea     r8d, [r9-2]; int
0x140029d54  call    TraceEvents
0x140029d59  mov     edi, 0C0000206h
0x140029d5e  jmp     loc_140029E8F
0x140029d63  mov     r14, [r14+18h]
0x140029d67  mov     [rbp+57h+var_B0], r8d
0x140029d6b  mov     r12d, [r14]
0x140029d6e  cmp     r12d, 40h ; '@'
0x140029d72  jnz     short loc_140029D9F
0x140029d74  cmp     ebx, r12d
0x140029d77  jb      short loc_140029D9F
0x140029d79  mov     rax, [r15+38h]
0x140029d7d  mov     rdi, r14
0x140029d80  cmp     [rax+5Dh], r8b
0x140029d84  setnz   r13b
0x140029d88  cmp     [r14+20h], r8b
0x140029d8c  jnz     short loc_140029E08
0x140029d8e  mov     edx, [r14+28h]; unsigned int
0x140029d92  mov     rcx, rsi; struct _VHD_VIRTUAL_DISK *
0x140029d95  call    ?VhdmpiCtGetFeatureFlags@@YAKPEAU_VHD_VIRTUAL_DISK@@K@Z; VhdmpiCtGetFeatureFlags(_VHD_VIRTUAL_DISK *,ulong)
0x140029d9a  mov     [rbp+57h+var_B0], eax
0x140029d9d  jmp     short loc_140029E08
0x140029d9f  cmp     r12d, 28h ; '('
0x140029da3  jz      short loc_140029E05
0x140029da5  mov     eax, cs:dword_1400876D0
0x140029dab  cmp     eax, 2
0x140029dae  jbe     short loc_140029DFB
0x140029db0  mov     edx, 4
0x140029db5  lea     rcx, dword_1400876D0
0x140029dbc  call    _tlgKeywordOn
0x140029dc1  test    al, al
0x140029dc3  jz      short loc_140029DFB
0x140029dc5  mov     qword ptr [rsp+110h+var_D8], rsi
0x140029dca  lea     rax, aVhdmpienabletr_12; "VhdmpiEnableTracking: Incorrect FilePat"...
0x140029dd1  mov     r9d, 4; int
0x140029dd7  mov     qword ptr [rsp+110h+var_E0], r15
0x140029ddc  mov     edx, 18Ah; int
0x140029de1  mov     dword ptr [rsp+110h+var_E8], r12d; char
0x140029de6  lea     rcx, aVhdmpienabletr_4; "VhdmpiEnableTracking"
0x140029ded  mov     [rsp+110h+var_F0], rax; char *
0x140029df2  lea     r8d, [r9-2]; int
0x140029df6  call    TraceEvents
0x140029dfb  mov     edi, 0C000000Dh
0x140029e00  jmp     loc_140029E8F
0x140029e05  mov     rdi, r8
0x140029e08  lea     rcx, [rsi+760h]
0x140029e0f  call    VhdmpiAcquirePassiveLock
0x140029e14  mov     byte ptr [rbp+57h+var_C0+2], 1
0x140029e18  test    r13b, r13b
0x140029e1b  jz      loc_14002A02E
0x140029e21  lea     r8, [rbp+57h+var_A0]; struct _STORAGE_ENABLE_TRACKING_VIRTUAL_DISK_V2_REQUEST **
0x140029e25  mov     rdx, rdi; struct _STORAGE_ENABLE_TRACKING_VIRTUAL_DISK_V2_REQUEST *
0x140029e28  mov     rcx, r15; struct _VHD_HANDLE_CONTEXT *
0x140029e2b  call    ?VhdmpiCtCreateEnableTrackingRequest@@YAJPEAU_VHD_HANDLE_CONTEXT@@PEAU_STORAGE_ENABLE_TRACKING_VIRTUAL_DISK_V2_REQUEST@@PEAPEAU2@@Z; VhdmpiCtCreateEnableTrackingRequest(_VHD_HANDLE_CONTEXT *,_STORAGE_ENABLE_TRACKING_VIRTUAL_DISK_V2_REQUEST *,_STORAGE_ENABLE_TRACKING_VIRTUAL_DISK_V2_REQUEST * *)
0x140029e30  mov     edi, eax
0x140029e32  test    eax, eax
0x140029e34  jns     loc_14002A02E
0x140029e3a  mov     eax, cs:dword_1400876D0
0x140029e40  cmp     eax, 2
0x140029e43  jbe     short loc_140029E8B
0x140029e45  mov     edx, 4
0x140029e4a  lea     rcx, dword_1400876D0
0x140029e51  call    _tlgKeywordOn
0x140029e56  test    al, al
0x140029e58  jz      short loc_140029E8B
0x140029e5a  mov     edx, 1B1h; int
0x140029e5f  lea     rax, aVhdmpienabletr_9; "VhdmpiEnableTracking: Couldn't create n"...
0x140029e66  mov     r9d, 4; int
0x140029e6c  mov     qword ptr [rsp+110h+var_E0], rsi
0x140029e71  mov     [rsp+110h+var_E8], r15; char
0x140029e76  lea     rcx, aVhdmpienabletr_4; "VhdmpiEnableTracking"
0x140029e7d  mov     [rsp+110h+var_F0], rax; char *
0x140029e82  lea     r8d, [r9-2]; int
0x140029e86  call    TraceEvents
0x140029e8b  mov     r13, [rbp+57h+var_B8]
0x140029e8f  lea     rcx, [rbp+57h+DestinationString]
0x140029e93  call    VhdmpiFreeFilePath
0x140029e98  lea     rcx, [rbp+57h+Source]
0x140029e9c  call    VhdmpiFreeFilePath
0x140029ea1  cmp     byte ptr [rbp+57h+var_C0+1], 0
0x140029ea5  jz      short loc_140029EB3
0x140029ea7  lea     rcx, [rsi+750h]
0x140029eae  call    VhdmpiReleasePassiveLock
0x140029eb3  cmp     byte ptr [rbp+57h+var_C0+2], 0
0x140029eb7  jz      short loc_140029EC5
0x140029eb9  lea     rcx, [rsi+760h]
0x140029ec0  call    VhdmpiReleasePassiveLock
0x140029ec5  test    edi, edi
0x140029ec7  jns     loc_140029F76
0x140029ecd  cmp     byte ptr [rbp+57h+var_C0+3], 0
0x140029ed1  jz      loc_140029F69
0x140029ed7  movups  xmm0, cs:VhdmpZeroGuid
0x140029ede  mov     rcx, [r15+130h]; struct _VHDS_STATE *
0x140029ee5  lea     rdx, [rbp+57h+var_68]
0x140029ee9  xor     eax, eax
0x140029eeb  mov     [rbp+57h+var_56], 0
0x140029ef2  mov     [rbp+57h+var_52], ax
0x140029ef6  mov     r8b, 1
0x140029ef9  mov     eax, 3
0x140029efe  mov     [rbp+57h+var_58], ax
0x140029f02  movdqu  [rbp+57h+var_68], xmm0
0x140029f07  call    VhdmpiDeleteSnapshotInternal
0x140029f0c  mov     r9d, eax
0x140029f0f  test    eax, eax
0x140029f11  jns     short loc_140029F69
0x140029f13  mov     ecx, cs:dword_1400876D0
0x140029f19  cmp     ecx, 2
0x140029f1c  jbe     short loc_140029F69
0x140029f1e  mov     edx, 4
0x140029f23  lea     rcx, dword_1400876D0
0x140029f2a  call    _tlgKeywordOn
0x140029f2f  test    al, al
0x140029f31  jz      short loc_140029F69
0x140029f33  mov     qword ptr [rsp+110h+var_D8], rsi
0x140029f38  lea     rax, aVhdmpienabletr_3; "VhdmpiEnableTracking: Unable to delete "...
0x140029f3f  mov     qword ptr [rsp+110h+var_E0], r15
0x140029f44  lea     rcx, aVhdmpienabletr_4; "VhdmpiEnableTracking"
0x140029f4b  mov     dword ptr [rsp+110h+var_E8], r9d; char
0x140029f50  mov     edx, 31Eh; int
0x140029f55  mov     r9d, 4; int
0x140029f5b  mov     [rsp+110h+var_F0], rax; char *
0x140029f60  lea     r8d, [r9-2]; int
0x140029f64  call    TraceEvents
0x140029f69  test    r13, r13
0x140029f6c  jz      short loc_140029F76
0x140029f6e  mov     rcx, r13; struct _CTLOG_BACKING_STORE *
0x140029f71  call    VhdmpiCTLogCloseBackingStore
0x140029f76  mov     r8, [rbp+57h+P]
0x140029f7a  test    r8, r8
0x140029f7d  jz      short loc_140029F93
0x140029f7f  mov     edx, 7A444856h; Tag
0x140029f84  mov     rcx, r8; P
0x140029f87  call    cs:__imp_ExFreePoolWithTag
0x140029f8e  nop     dword ptr [rax+rax+00h]
0x140029f93  mov     rax, [rbp+57h+var_A0]
0x140029f97  test    rax, rax
0x140029f9a  jz      short loc_140029FB0
0x140029f9c  mov     edx, 68444856h; Tag
0x140029fa1  mov     rcx, rax; P
0x140029fa4  call    cs:__imp_ExFreePoolWithTag
0x140029fab  nop     dword ptr [rax+rax+00h]
0x140029fb0  mov     eax, cs:dword_1400876D0
0x140029fb6  cmp     eax, 4
0x140029fb9  jbe     short loc_14002A004
0x140029fbb  mov     edx, 4
0x140029fc0  lea     rcx, dword_1400876D0
0x140029fc7  call    _tlgKeywordOn
0x140029fcc  test    al, al
0x140029fce  jz      short loc_14002A004
0x140029fd0  mov     qword ptr [rsp+110h+var_D8], rsi
0x140029fd5  lea     rax, aVhdmpienabletr_11; "VhdmpiEnableTracking: leaving... (0x%08"...
0x140029fdc  mov     r9d, 4; int
0x140029fe2  mov     qword ptr [rsp+110h+var_E0], r15
0x140029fe7  mov     dword ptr [rsp+110h+var_E8], edi; char
0x140029feb  lea     rcx, aVhdmpienabletr_4; "VhdmpiEnableTracking"
0x140029ff2  mov     r8d, r9d; int
0x140029ff5  mov     [rsp+110h+var_F0], rax; char *
0x140029ffa  mov     edx, 33Ch; int
0x140029fff  call    TraceEvents
0x14002a004  mov     eax, edi
0x14002a006  mov     rcx, [rbp+57h+var_40]
0x14002a00a  xor     rcx, rsp; StackCookie
  ... truncated ...
```
