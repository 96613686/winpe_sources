# VhdmpiEnableTracking

- ea: `0x1400295e4`
- end: `0x14002a002`
- name: `VhdmpiEnableTracking`
- size: `2590`
- prototype: `__int64 __fastcall(struct _VHD_HANDLE_CONTEXT *, _QWORD *)`
- caller_count: `1`
- callee_count: `24`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14001a1e8`

## callees

- `0x1400191d4`
- `0x14001b7fc`
- `0x14001bc68`
- `0x14001f58c`
- `0x140020874`
- `0x14002227c`
- `0x140023560`
- `0x140029334`
- `0x1400293f8`
- `0x1400294cc`
- `0x1400295e4`
- `0x14002a4e8`
- `0x14002d80c`
- `0x14002da18`
- `0x140035e94`
- `0x140040504`
- `0x140049b60`
- `0x14005d7c0`
- `0x14005d8e0`
- `0x1400a41d0`
- `0x1400a6fa4`
- `0x1400a7078`
- `0x1400a7c58`
- `0x1400c78e0`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14002965f`
- `ntoskrnl!RtlInitUnicodeString` at `0x140029671`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002965f`
- `ntoskrnl!RtlInitUnicodeString` at `0x140029671`
- `ntoskrnl!ExFreePoolWithTag` at `0x140029a67`
- `ntoskrnl!ExFreePoolWithTag` at `0x140029a84`
- `ntoskrnl!ExFreePoolWithTag` at `0x140029a67`
- `ntoskrnl!ExFreePoolWithTag` at `0x140029a84`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140029e2d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140029e2d`
- `ntoskrnl!KeReleaseSpinLock` at `0x140029e58`
- `ntoskrnl!KeReleaseSpinLock` at `0x140029e58`

## string_xrefs

- `0x140029746`: `VhdmpiEnableTracking: Failure getting VhdFilePath. Context = %p. VirtualDisk = %p`
- `0x1400297ae`: `VhdmpiEnableTracking: access is denied. Context = %p. VirtualDisk = %p`
- `0x14002993f`: `VhdmpiEnableTracking: Couldn't create new EnableTracking request from VhdSet. Context = %p. VirtualDisk = %p`
- `0x1400298aa`: `VhdmpiEnableTracking: Incorrect FilePathOffset = %d. Context = %p. VirtualDisk = %p`
- `0x140029bb2`: `VhdmpiEnableTracking: Couldn't get absolute path for the log file. Context = %p. VirtualDisk = %p`
- `0x140029a18`: `VhdmpiEnableTracking: Unable to delete leaf snapshot information (0x%08x).                     Context = %p. VirtualDisk = %p`

## pseudocode

```c
__int64 __fastcall VhdmpiEnableTracking(struct _VHD_HANDLE_CONTEXT *a1, _QWORD *a2)
{
  __int64 v2; // r12
  __int64 v3; // rsi
  __int64 v6; // r13
  int v7; // edx
  __int64 v8; // rax
  int EnableTrackingRequest; // edi
  __int64 v10; // rdx
  __int64 v11; // r8
  unsigned int v12; // ebx
  PVOID v13; // r14
  int v14; // r12d
  struct _STORAGE_ENABLE_TRACKING_VIRTUAL_DISK_V2_REQUEST *v15; // rdi
  int v16; // edx
  char *v17; // rax
  __int64 v18; // rdx
  __int64 v19; // r8
  struct _VHDS_STATE *v20; // rcx
  char v21; // r9
  int v23; // ebx
  __int64 v24; // rdx
  __int64 v25; // r8
  bool v26; // zf
  int v27; // eax
  int v28; // ecx
  const wchar_t *v29; // r12
  unsigned int v30; // ebx
  unsigned __int64 v31; // rax
  KIRQL v32; // al
  int v33; // ecx
  const wchar_t *v34; // rdx
  __int64 v35; // r9
  int v36; // eax
  const wchar_t *v37; // rcx
  __int64 v38; // r9
  signed __int32 v39[8]; // [rsp+0h] [rbp-B9h] BYREF
  char *v40; // [rsp+20h] [rbp-99h]
  PUNICODE_STRING v41; // [rsp+28h] [rbp-91h]
  char v42[8]; // [rsp+30h] [rbp-89h]
  int v43[2]; // [rsp+38h] [rbp-81h]
  struct _VHD_HANDLE_CONTEXT *v44; // [rsp+40h] [rbp-79h]
  __int64 v45; // [rsp+48h] [rbp-71h]
  __int64 v46; // [rsp+50h] [rbp-69h] BYREF
  __int64 v47; // [rsp+58h] [rbp-61h] BYREF
  int FeatureFlags; // [rsp+60h] [rbp-59h]
  char v49[4]; // [rsp+64h] [rbp-55h] BYREF
  PVOID P; // [rsp+68h] [rbp-51h] BYREF
  PVOID v51; // [rsp+70h] [rbp-49h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+78h] [rbp-41h] BYREF
  UNICODE_STRING Source; // [rsp+88h] [rbp-31h] BYREF
  struct _UNICODE_STRING v54; // [rsp+98h] [rbp-21h] BYREF
  __int128 v55; // [rsp+A8h] [rbp-11h]
  __int16 v56; // [rsp+B8h] [rbp-1h]
  int v57; // [rsp+BAh] [rbp+1h]
  __int16 v58; // [rsp+BEh] [rbp+5h]
  __int128 Buf1; // [rsp+C0h] [rbp+7h] BYREF

  v2 = a2[23];
  a2[7] = 0;
  v3 = *((_QWORD *)a1 + 7);
  v51 = 0;
  v47 = 0;
  v54 = 0;
  v6 = 0;
  LODWORD(v46) = 1;
  Source = 0;
  *(_DWORD *)v49 = 0;
  DestinationString = 0;
  P = 0;
  Buf1 = 0;
  RtlInitUnicodeString(&DestinationString, 0);
  RtlInitUnicodeString(&Source, 0);
  VhdmpiAcquirePassiveLockShared(v3 + 128);
  if ( (unsigned int)dword_140087708 > 4 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 4) )
  {
    v8 = *(_QWORD *)(v3 + 144);
    *(_QWORD *)v43 = v3;
    *(_QWORD *)v42 = a1;
    TraceEvents(
      (int)"VhdmpiEnableTracking",
      319,
      v7,
      v7,
      "VhdmpiEnableTracking called for file %S. Context = %p. VirtualDisk = %p",
      *(_QWORD *)(v8 + 120));
  }
  EnableTrackingRequest = VhdmpiDuplicateFilePath(0);
  VhdmpiReleasePassiveLockShared(v3 + 128);
  v11 = 0;
  if ( EnableTrackingRequest < 0 )
  {
    if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 4) )
    {
      *(_QWORD *)v42 = v3;
      TraceEvents(
        (int)"VhdmpiEnableTracking",
        336,
        v11 + 2,
        v11 + 4,
        "VhdmpiEnableTracking: Failure getting VhdFilePath. Context = %p. VirtualDisk = %p",
        (char)a1);
    }
    goto LABEL_36;
  }
  if ( (*((_DWORD *)a1 + 1) & 1) != 0 && (*((_DWORD *)a1 + 2) & 0x200000) == 0 )
  {
    if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 4) )
    {
      *(_QWORD *)v42 = v3;
      TraceEvents(
        (int)"VhdmpiEnableTracking",
        353,
        2,
        4,
        "VhdmpiEnableTracking: access is denied. Context = %p. VirtualDisk = %p",
        (char)a1);
    }
    EnableTrackingRequest = -1073741790;
    goto LABEL_36;
  }
  v12 = *(_DWORD *)(v2 + 16);
  if ( v12 < 0x28 )
  {
    if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 4) )
    {
      *(_QWORD *)v42 = v3;
      TraceEvents(
        (int)"VhdmpiEnableTracking",
        372,
        2,
        4,
        "VhdmpiEnableTracking: input buffer too small. Context = %p. VirtualDisk = %p",
        (char)a1);
    }
    EnableTrackingRequest = -1073741306;
    goto LABEL_36;
  }
  v13 = (PVOID)a2[3];
  FeatureFlags = 0;
  v14 = *(_DWORD *)v13;
  if ( *(_DWORD *)v13 == 64 && v12 >= 0x40 )
  {
    v15 = (struct _STORAGE_ENABLE_TRACKING_VIRTUAL_DISK_V2_REQUEST *)v13;
    LOBYTE(v6) = *(_BYTE *)(*((_QWORD *)a1 + 7) + 93LL) != 0;
    if ( !*((_BYTE *)v13 + 32) )
      FeatureFlags = VhdmpiCtGetFeatureFlags((struct _VHD_VIRTUAL_DISK *)v3, *((_DWORD *)v13 + 10));
LABEL_29:
    VhdmpiAcquirePassiveLock(v3 + 1888, v10, v11);
    BYTE2(v46) = 1;
    if ( (_BYTE)v6 )
    {
      EnableTrackingRequest = VhdmpiCtCreateEnableTrackingRequest(
                                a1,
                                v15,
                                (struct _STORAGE_ENABLE_TRACKING_VIRTUAL_DISK_V2_REQUEST **)&v51);
      if ( EnableTrackingRequest < 0 )
      {
        if ( (unsigned int)dword_140087708 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140087708, 4) )
          goto LABEL_35;
        v16 = 433;
        v17 = "VhdmpiEnableTracking: Couldn't create new EnableTracking request from VhdSet. Context = %p. VirtualDisk = %p";
        goto LABEL_34;
      }
    }
    if ( v51 )
    {
      v13 = v51;
      v12 = *(_DWORD *)v51 + *((_DWORD *)v51 + 1);
      if ( v12 < *(_DWORD *)v51 )
      {
        EnableTrackingRequest = -1073741675;
        goto LABEL_35;
      }
    }
    if ( !(unsigned __int8)VhdmpiValidateFileName(
                             (int)v13,
                             v14,
                             v12,
                             *((_DWORD *)v13 + 1),
                             *(_DWORD *)v13,
                             &v54,
                             (char)"VhdmpiEnableTracking: ") )
    {
      EnableTrackingRequest = -1073741811;
      goto LABEL_35;
    }
    EnableTrackingRequest = VhdmpiCtGetAbsoluteLogFilePath(&Source, &v54, &DestinationString.Length);
    if ( EnableTrackingRequest < 0 )
    {
      if ( (unsigned int)dword_140087708 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140087708, 4) )
        goto LABEL_35;
      v16 = 482;
      v17 = "VhdmpiEnableTracking: Couldn't get absolute path for the log file. Context = %p. VirtualDisk = %p";
      goto LABEL_34;
    }
    v23 = VhdmpiCTGetVhdFileTimeAndDataWriteGuid(v3, v49, &Buf1, &P);
    VhdmpiAcquirePassiveLock(v3 + 1872, v24, v25);
    v26 = *(_DWORD *)(v3 + 1856) == 2;
    BYTE1(v46) = 1;
    if ( !v26 )
    {
      if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 4) )
      {
        *(_QWORD *)v42 = v3;
        TraceEvents(
          (int)"VhdmpiEnableTracking",
          515,
          2,
          4,
          "VhdmpiEnableTracking: state is not disabled, Context = %p. VirtualDisk = %p",
          (char)a1);
      }
      EnableTrackingRequest = -1069940701;
      goto LABEL_35;
    }
    if ( *(_BYTE *)(v3 + 2080) )
    {
      if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 4) )
      {
        *(_QWORD *)v42 = v3;
        TraceEvents(
          (int)"VhdmpiEnableTracking",
          532,
          2,
          4,
          "VhdmpiEnableTracking: CT Log operations are not allowed.Context = %p. VirtualDisk = %p",
          (char)a1);
      }
      EnableTrackingRequest = -2147483631;
      goto LABEL_35;
    }
    if ( (_BYTE)v6 && !*((_BYTE *)v13 + 32) )
    {
      EnableTrackingRequest = VhdmpiPrepareAndCommitCdpSnapshot(*((struct _VHDS_STATE **)a1 + 38));
      if ( EnableTrackingRequest < 0 )
      {
        if ( (unsigned int)dword_140087708 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140087708, 4) )
          goto LABEL_35;
        v16 = 566;
        v17 = "VhdmpiEnableTracking: Couldn't persist EnableTracking request in VhdSet. Context = %p. VirtualDisk = %p";
LABEL_34:
        *(_QWORD *)v42 = v3;
        TraceEvents((int)"VhdmpiEnableTracking", v16, 2, 4, v17, (char)a1);
LABEL_35:
        v6 = v47;
        goto LABEL_36;
      }
      BYTE3(v46) = 1;
    }
    v27 = VhdmpiCTLogCreateBackingStore(
            &DestinationString,
            *((_BYTE *)v13 + 32),
            (__int64)v13 + 16,
            (__int64)&VhdmpZeroGuid,
            (struct _VHD_HANDLE_CONTEXT *)((char *)a1 + 248),
            (char *)&v46,
            &v47,
            FeatureFlags);
    v6 = v47;
    EnableTrackingRequest = v27;
    if ( !v47 )
    {
      if ( !(_BYTE)v46 )
        EnableTrackingRequest = -1069940700;
      goto LABEL_36;
    }
    EnableTrackingRequest = VhdmpiCTLogInitVirtualDiskForTracking((struct _VHD_VIRTUAL_DISK *)v3);
    if ( EnableTrackingRequest < 0 )
      goto LABEL_36;
    v29 = L" ";
    if ( !*((_BYTE *)v13 + 32) )
      goto LABEL_92;
    if ( v23 < 0 )
    {
      if ( (Microsoft_Windows_VHDMPEnableBits & 4) != 0 )
      {
        v37 = L" ";
        v38 = *(_QWORD *)(v6 + 32);
        *(_QWORD *)v43 = *(unsigned int *)(v6 + 176);
        if ( P )
          v37 = (const wchar_t *)P;
        McTemplateK0zzqxx_EtwWriteTransfer((_DWORD)v37, v10, (_DWORD)P, v38, (__int64)v37, v23, 0, v43[0]);
      }
      if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 4) )
      {
        *(_QWORD *)v43 = v3;
        *(_QWORD *)v42 = a1;
        TraceEvents(
          (int)"VhdmpiEnableTracking",
          695,
          2,
          4,
          "VhdmpiEnableTracking: NtQueryInformationFile failed with error ... (0x%08x). Context = %p. VirtualDisk = %p",
          v23);
      }
    }
    else
    {
      v30 = *(_DWORD *)v49;
      if ( !*(_BYTE *)(*(_QWORD *)(v3 + 32) + 52LL)
        || (*(_DWORD *)(v6 + 92) & 0xFFFF0000) < 0x20000 && !memcmp((const void *)(v6 + 194), &VhdmpZeroGuid, 0x10u) )
      {
        if ( v30 <= *(_DWORD *)(v6 + 176) )
          goto LABEL_92;
      }
      else if ( !memcmp(&Buf1, (const void *)(v6 + 194), 0x10u) )
      {
LABEL_92:
        v31 = *((_QWORD *)v13 + 1);
        if ( v31 && *(_QWORD *)(v6 + 56) > v31 )
          EnableTrackingRequest = -1069940703;
        goto LABEL_95;
      }
      if ( (Microsoft_Windows_VHDMPEnableBits & 4) != 0 )
      {
        v34 = L" ";
        v35 = *(_QWORD *)(v6 + 32);
        *(_QWORD *)v43 = *(unsigned int *)(v6 + 176);
        if ( P )
          v34 = (const wchar_t *)P;
        McTemplateK0zzqxx_EtwWriteTransfer(v28, (_DWORD)v34, (_DWORD)P, v35, (__int64)v34, 34, v30, v43[0]);
      }
      if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 4) )
      {
        v36 = *(_DWORD *)(v6 + 176);
        v45 = v3;
        v44 = a1;
        v43[0] = -1069940702;
        *(_DWORD *)v42 = v36;
        TraceEvents(
          (int)"VhdmpiEnableTracking",
          667,
          2,
          4,
          "VhdmpiEnableTracking: VHD is changed offline. VHD time:(0x%08x) Logfile time:(0x%08x) Status:(0x%08x)Context ="
          " %p. VirtualDisk = %p",
          v30);
      }
    }
    EnableTrackingRequest = -1069940702;
LABEL_95:
    if ( *((_BYTE *)v13 + 32) )
      *(_QWORD *)(v3 + 2016) = *(_QWORD *)(v6 + 180);
    v32 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v3 + 1864));
    *(_QWORD *)(v3 + 1536) = v6;
    *(_QWORD *)(v6 + 72) = v3;
    _InterlockedOr(v39, 0);
    *(_DWORD *)(v3 + 1856) = 1;
    KeReleaseSpinLock((PKSPIN_LOCK)(v3 + 1864), v32);
    *(_QWORD *)(v3 + 1904) = *((_QWORD *)v13 + 1);
    if ( (Microsoft_Windows_VHDMPEnableBits & 8) != 0 )
    {
      v41 = *(PUNICODE_STRING *)(v6 + 32);
      if ( P )
        LODWORD(v29) = (_DWORD)P;
      McTemplateK0zxz_EtwWriteTransfer(v33, v10, (_DWORD)P, (_DWORD)v29, (_DWORD)v40, (__int64)v41);
    }
    if ( EnableTrackingRequest < 0 )
      VhdmpiCTLogProcessTrackingError(v3, (unsigned int)EnableTrackingRequest);
    EnableTrackingRequest = 0;
    goto LABEL_36;
  }
  if ( v14 == 40 )
  {
    v15 = 0;
    goto LABEL_29;
  }
  if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 4) )
  {
    *(_QWORD *)v43 = v3;
    *(_QWORD *)v42 = a1;
    TraceEvents(
      (int)"VhdmpiEnableTracking",
      394,
      2,
      4,
      "VhdmpiEnableTracking: Incorrect FilePathOffset = %d. Context = %p. VirtualDisk = %p",
      v14);
  }
  EnableTrackingRequest = -1073741811;
LABEL_36:
  VhdmpiFreeFilePath(&DestinationString, v10, v11);
  VhdmpiFreeFilePath(&Source, v18, v19);
  if ( BYTE1(v46) )
    VhdmpiReleasePassiveLock(v3 + 1872);
  if ( BYTE2(v46) )
    VhdmpiReleasePassiveLock(v3 + 1888);
  if ( EnableTrackingRequest < 0 )
  {
    if ( BYTE3(v46) )
    {
      v20 = (struct _VHDS_STATE *)*((_QWORD *)a1 + 38);
      v57 = 0;
      v58 = 0;
      v56 = 3;
      v55 = *(_OWORD *)&VhdmpZeroGuid;
      if ( (int)VhdmpiDeleteSnapshotInternal(v20) < 0
        && (unsigned int)dword_140087708 > 2
        && (unsigned __int8)tlgKeywordOn(&dword_140087708, 4) )
      {
        *(_QWORD *)v43 = v3;
        *(_QWORD *)v42 = a1;
        TraceEvents(
          (int)"VhdmpiEnableTracking",
          798,
          2,
          4,
          "VhdmpiEnableTracking: Unable to delete leaf snapshot information (0x%08x).                     Context = %p. VirtualDisk = %p",
          v21);
      }
    }
    if ( v6 )
      VhdmpiCTLogCloseBackingStore((struct _CTLOG_BACKING_STORE *)v6);
  }
  if ( P )
    ExFreePoolWithTag(P, 0x7A444856u);
  if ( v51 )
    ExFreePoolWithTag(v51, 0x68444856u);
  if ( (unsigned int)dword_140087708 > 4 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 4) )
  {
    *(_QWORD *)v43 = v3;
    *(_QWORD *)v42 = a1;
    TraceEvents(
      (int)"VhdmpiEnableTracking",
      828,
      4,
      4,
      "VhdmpiEnableTracking: leaving... (0x%08x). Context = %p. VirtualDisk = %p",
      EnableTrackingRequest);
  }
  return (unsigned int)EnableTrackingRequest;
}

```

## disassembly

```asm
0x1400295e4  mov     [rsp-8+arg_10], rbx
0x1400295e9  push    rbp
0x1400295ea  push    rsi
0x1400295eb  push    rdi
0x1400295ec  push    r12
0x1400295ee  push    r13
0x1400295f0  push    r14
0x1400295f2  push    r15
0x1400295f4  lea     rbp, [rsp-27h]
0x1400295f9  sub     rsp, 0E0h
0x140029600  mov     rax, cs:__security_cookie
0x140029607  xor     rax, rsp
0x14002960a  mov     [rbp+57h+var_40], rax
0x14002960e  mov     r12, [rdx+0B8h]
0x140029615  xor     edi, edi
0x140029617  mov     [rdx+38h], rdi
0x14002961b  xorps   xmm0, xmm0
0x14002961e  mov     rsi, [rcx+38h]
0x140029622  xorps   xmm1, xmm1
0x140029625  mov     r14, rdx
0x140029628  mov     [rbp+57h+var_A0], rdi
0x14002962c  mov     r15, rcx
0x14002962f  mov     [rbp+57h+var_B8], rdi
0x140029633  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140029637  mov     byte ptr [rbp+57h+var_C0+1], dil
0x14002963b  xor     edx, edx; SourceString
0x14002963d  mov     byte ptr [rbp+57h+var_C0+2], dil
0x140029641  movups  xmmword ptr [rbp+57h+var_78.Length], xmm0
0x140029645  mov     r13d, edi
0x140029648  mov     byte ptr [rbp+57h+var_C0], 1
0x14002964c  movups  xmmword ptr [rbp+57h+Source.Length], xmm1
0x140029650  mov     dword ptr [rbp+57h+var_AC], edi
0x140029653  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140029657  mov     [rbp+57h+P], rdi
0x14002965b  movups  [rbp+57h+Buf1], xmm1
0x14002965f  call    cs:__imp_RtlInitUnicodeString
0x140029666  nop     dword ptr [rax+rax+00h]
0x14002966b  xor     edx, edx; SourceString
0x14002966d  lea     rcx, [rbp+57h+Source]; DestinationString
0x140029671  call    cs:__imp_RtlInitUnicodeString
0x140029678  nop     dword ptr [rax+rax+00h]
0x14002967d  lea     rbx, [rsi+80h]
0x140029684  mov     byte ptr [rbp+57h+var_C0+3], dil
0x140029688  mov     rcx, rbx
0x14002968b  call    VhdmpiAcquirePassiveLockShared
0x140029690  mov     eax, cs:dword_140087708
0x140029696  lea     edx, [rdi+4]
0x140029699  cmp     eax, edx
0x14002969b  jbe     short loc_1400296EC
0x14002969d  lea     rcx, dword_140087708
0x1400296a4  call    _tlgKeywordOn
0x1400296a9  test    al, al
0x1400296ab  jz      short loc_1400296EC
0x1400296ad  mov     rax, [rsi+90h]
0x1400296b4  mov     ecx, 13Fh
0x1400296b9  mov     qword ptr [rsp+110h+var_D8], rsi
0x1400296be  mov     r9d, edx; int
0x1400296c1  mov     qword ptr [rsp+110h+var_E0], r15
0x1400296c6  mov     r8d, edx; int
0x1400296c9  mov     edx, ecx; int
0x1400296cb  lea     rcx, aVhdmpienabletr_4; "VhdmpiEnableTracking"
0x1400296d2  mov     rax, [rax+78h]
0x1400296d6  mov     [rsp+110h+var_E8], rax; char
0x1400296db  lea     rax, aVhdmpienabletr_14; "VhdmpiEnableTracking called for file %S"...
0x1400296e2  mov     [rsp+110h+var_F0], rax; char *
0x1400296e7  call    TraceEvents
0x1400296ec  mov     rdx, [rsi+90h]
0x1400296f3  lea     r9, [rbp+57h+Source]
0x1400296f7  add     rdx, 48h ; 'H'
0x1400296fb  xor     r8d, r8d
0x1400296fe  xor     ecx, ecx; Source
0x140029700  call    VhdmpiDuplicateFilePath
0x140029705  mov     rcx, rbx
0x140029708  mov     edi, eax
0x14002970a  call    VhdmpiReleasePassiveLockShared
0x14002970f  xor     r8d, r8d
0x140029712  test    edi, edi
0x140029714  jns     short loc_140029771
0x140029716  mov     ecx, cs:dword_140087708
0x14002971c  cmp     ecx, 2
0x14002971f  jbe     loc_14002996F
0x140029725  lea     edx, [r8+4]
0x140029729  lea     rcx, dword_140087708
0x140029730  call    _tlgKeywordOn
0x140029735  test    al, al
0x140029737  jz      loc_14002996F
0x14002973d  lea     r9d, [r8+4]; int
0x140029741  mov     qword ptr [rsp+110h+var_E0], rsi
0x140029746  lea     rax, aVhdmpienabletr; "VhdmpiEnableTracking: Failure getting V"...
0x14002974d  mov     [rsp+110h+var_E8], r15; char
0x140029752  lea     r8d, [r9-2]; int
0x140029756  mov     [rsp+110h+var_F0], rax; char *
0x14002975b  mov     edx, 150h; int
0x140029760  lea     rcx, aVhdmpienabletr_4; "VhdmpiEnableTracking"
0x140029767  call    TraceEvents
0x14002976c  jmp     loc_14002996F
0x140029771  mov     eax, [r15+4]
0x140029775  test    al, 1
0x140029777  jz      short loc_1400297DE
0x140029779  test    dword ptr [r15+8], 200000h
0x140029781  jnz     short loc_1400297DE
0x140029783  mov     eax, cs:dword_140087708
0x140029789  cmp     eax, 2
0x14002978c  jbe     short loc_1400297D4
0x14002978e  mov     edx, 4
0x140029793  lea     rcx, dword_140087708
0x14002979a  call    _tlgKeywordOn
0x14002979f  test    al, al
0x1400297a1  jz      short loc_1400297D4
0x1400297a3  mov     r9d, 4; int
0x1400297a9  mov     qword ptr [rsp+110h+var_E0], rsi
0x1400297ae  lea     rax, aVhdmpienabletr_13; "VhdmpiEnableTracking: access is denied."...
0x1400297b5  mov     [rsp+110h+var_E8], r15; char
0x1400297ba  mov     edx, 161h; int
0x1400297bf  mov     [rsp+110h+var_F0], rax; char *
0x1400297c4  lea     rcx, aVhdmpienabletr_4; "VhdmpiEnableTracking"
0x1400297cb  lea     r8d, [r9-2]; int
0x1400297cf  call    TraceEvents
0x1400297d4  mov     edi, 0C0000022h
0x1400297d9  jmp     loc_14002996F
0x1400297de  mov     ebx, [r12+10h]
0x1400297e3  cmp     ebx, 28h ; '('
0x1400297e6  jnb     short loc_140029843
0x1400297e8  mov     eax, cs:dword_140087708
0x1400297ee  cmp     eax, 2
0x1400297f1  jbe     short loc_140029839
0x1400297f3  mov     edx, 4
0x1400297f8  lea     rcx, dword_140087708
0x1400297ff  call    _tlgKeywordOn
0x140029804  test    al, al
0x140029806  jz      short loc_140029839
0x140029808  mov     r9d, 4; int
0x14002980e  mov     qword ptr [rsp+110h+var_E0], rsi
0x140029813  lea     rax, aVhdmpienabletr_5; "VhdmpiEnableTracking: input buffer too "...
0x14002981a  mov     [rsp+110h+var_E8], r15; char
0x14002981f  mov     edx, 174h; int
0x140029824  mov     [rsp+110h+var_F0], rax; char *
0x140029829  lea     rcx, aVhdmpienabletr_4; "VhdmpiEnableTracking"
0x140029830  lea     r8d, [r9-2]; int
0x140029834  call    TraceEvents
0x140029839  mov     edi, 0C0000206h
0x14002983e  jmp     loc_14002996F
0x140029843  mov     r14, [r14+18h]
0x140029847  mov     [rbp+57h+var_B0], r8d
0x14002984b  mov     r12d, [r14]
0x14002984e  cmp     r12d, 40h ; '@'
0x140029852  jnz     short loc_14002987F
0x140029854  cmp     ebx, r12d
0x140029857  jb      short loc_14002987F
0x140029859  mov     rax, [r15+38h]
0x14002985d  mov     rdi, r14
0x140029860  cmp     [rax+5Dh], r8b
0x140029864  setnz   r13b
0x140029868  cmp     [r14+20h], r8b
0x14002986c  jnz     short loc_1400298E8
0x14002986e  mov     edx, [r14+28h]; unsigned int
0x140029872  mov     rcx, rsi; struct _VHD_VIRTUAL_DISK *
0x140029875  call    ?VhdmpiCtGetFeatureFlags@@YAKPEAU_VHD_VIRTUAL_DISK@@K@Z; VhdmpiCtGetFeatureFlags(_VHD_VIRTUAL_DISK *,ulong)
0x14002987a  mov     [rbp+57h+var_B0], eax
0x14002987d  jmp     short loc_1400298E8
0x14002987f  cmp     r12d, 28h ; '('
0x140029883  jz      short loc_1400298E5
0x140029885  mov     eax, cs:dword_140087708
0x14002988b  cmp     eax, 2
0x14002988e  jbe     short loc_1400298DB
0x140029890  mov     edx, 4
0x140029895  lea     rcx, dword_140087708
0x14002989c  call    _tlgKeywordOn
0x1400298a1  test    al, al
0x1400298a3  jz      short loc_1400298DB
0x1400298a5  mov     qword ptr [rsp+110h+var_D8], rsi
0x1400298aa  lea     rax, aVhdmpienabletr_12; "VhdmpiEnableTracking: Incorrect FilePat"...
0x1400298b1  mov     r9d, 4; int
0x1400298b7  mov     qword ptr [rsp+110h+var_E0], r15
0x1400298bc  mov     edx, 18Ah; int
0x1400298c1  mov     dword ptr [rsp+110h+var_E8], r12d; char
0x1400298c6  lea     rcx, aVhdmpienabletr_4; "VhdmpiEnableTracking"
0x1400298cd  mov     [rsp+110h+var_F0], rax; char *
0x1400298d2  lea     r8d, [r9-2]; int
0x1400298d6  call    TraceEvents
0x1400298db  mov     edi, 0C000000Dh
0x1400298e0  jmp     loc_14002996F
0x1400298e5  mov     rdi, r8
0x1400298e8  lea     rcx, [rsi+760h]
0x1400298ef  call    VhdmpiAcquirePassiveLock
0x1400298f4  mov     byte ptr [rbp+57h+var_C0+2], 1
0x1400298f8  test    r13b, r13b
0x1400298fb  jz      loc_140029B0E
0x140029901  lea     r8, [rbp+57h+var_A0]; struct _STORAGE_ENABLE_TRACKING_VIRTUAL_DISK_V2_REQUEST **
0x140029905  mov     rdx, rdi; struct _STORAGE_ENABLE_TRACKING_VIRTUAL_DISK_V2_REQUEST *
0x140029908  mov     rcx, r15; struct _VHD_HANDLE_CONTEXT *
0x14002990b  call    ?VhdmpiCtCreateEnableTrackingRequest@@YAJPEAU_VHD_HANDLE_CONTEXT@@PEAU_STORAGE_ENABLE_TRACKING_VIRTUAL_DISK_V2_REQUEST@@PEAPEAU2@@Z; VhdmpiCtCreateEnableTrackingRequest(_VHD_HANDLE_CONTEXT *,_STORAGE_ENABLE_TRACKING_VIRTUAL_DISK_V2_REQUEST *,_STORAGE_ENABLE_TRACKING_VIRTUAL_DISK_V2_REQUEST * *)
0x140029910  mov     edi, eax
0x140029912  test    eax, eax
0x140029914  jns     loc_140029B0E
0x14002991a  mov     eax, cs:dword_140087708
0x140029920  cmp     eax, 2
0x140029923  jbe     short loc_14002996B
0x140029925  mov     edx, 4
0x14002992a  lea     rcx, dword_140087708
0x140029931  call    _tlgKeywordOn
0x140029936  test    al, al
0x140029938  jz      short loc_14002996B
0x14002993a  mov     edx, 1B1h; int
0x14002993f  lea     rax, aVhdmpienabletr_9; "VhdmpiEnableTracking: Couldn't create n"...
0x140029946  mov     r9d, 4; int
0x14002994c  mov     qword ptr [rsp+110h+var_E0], rsi
0x140029951  mov     [rsp+110h+var_E8], r15; char
0x140029956  lea     rcx, aVhdmpienabletr_4; "VhdmpiEnableTracking"
0x14002995d  mov     [rsp+110h+var_F0], rax; char *
0x140029962  lea     r8d, [r9-2]; int
0x140029966  call    TraceEvents
0x14002996b  mov     r13, [rbp+57h+var_B8]
0x14002996f  lea     rcx, [rbp+57h+DestinationString]
0x140029973  call    VhdmpiFreeFilePath
0x140029978  lea     rcx, [rbp+57h+Source]
0x14002997c  call    VhdmpiFreeFilePath
0x140029981  cmp     byte ptr [rbp+57h+var_C0+1], 0
0x140029985  jz      short loc_140029993
0x140029987  lea     rcx, [rsi+750h]
0x14002998e  call    VhdmpiReleasePassiveLock
0x140029993  cmp     byte ptr [rbp+57h+var_C0+2], 0
0x140029997  jz      short loc_1400299A5
0x140029999  lea     rcx, [rsi+760h]
0x1400299a0  call    VhdmpiReleasePassiveLock
0x1400299a5  test    edi, edi
0x1400299a7  jns     loc_140029A56
0x1400299ad  cmp     byte ptr [rbp+57h+var_C0+3], 0
0x1400299b1  jz      loc_140029A49
0x1400299b7  movups  xmm0, cs:VhdmpZeroGuid
0x1400299be  mov     rcx, [r15+130h]; struct _VHDS_STATE *
0x1400299c5  lea     rdx, [rbp+57h+var_68]
0x1400299c9  xor     eax, eax
0x1400299cb  mov     [rbp+57h+var_56], 0
0x1400299d2  mov     [rbp+57h+var_52], ax
0x1400299d6  mov     r8b, 1
0x1400299d9  mov     eax, 3
0x1400299de  mov     [rbp+57h+var_58], ax
0x1400299e2  movdqu  [rbp+57h+var_68], xmm0
0x1400299e7  call    VhdmpiDeleteSnapshotInternal
0x1400299ec  mov     r9d, eax
0x1400299ef  test    eax, eax
0x1400299f1  jns     short loc_140029A49
0x1400299f3  mov     ecx, cs:dword_140087708
0x1400299f9  cmp     ecx, 2
0x1400299fc  jbe     short loc_140029A49
0x1400299fe  mov     edx, 4
0x140029a03  lea     rcx, dword_140087708
0x140029a0a  call    _tlgKeywordOn
0x140029a0f  test    al, al
0x140029a11  jz      short loc_140029A49
0x140029a13  mov     qword ptr [rsp+110h+var_D8], rsi
0x140029a18  lea     rax, aVhdmpienabletr_3; "VhdmpiEnableTracking: Unable to delete "...
0x140029a1f  mov     qword ptr [rsp+110h+var_E0], r15
0x140029a24  lea     rcx, aVhdmpienabletr_4; "VhdmpiEnableTracking"
0x140029a2b  mov     dword ptr [rsp+110h+var_E8], r9d; char
0x140029a30  mov     edx, 31Eh; int
0x140029a35  mov     r9d, 4; int
0x140029a3b  mov     [rsp+110h+var_F0], rax; char *
0x140029a40  lea     r8d, [r9-2]; int
0x140029a44  call    TraceEvents
0x140029a49  test    r13, r13
0x140029a4c  jz      short loc_140029A56
0x140029a4e  mov     rcx, r13; struct _CTLOG_BACKING_STORE *
0x140029a51  call    VhdmpiCTLogCloseBackingStore
0x140029a56  mov     r8, [rbp+57h+P]
0x140029a5a  test    r8, r8
0x140029a5d  jz      short loc_140029A73
0x140029a5f  mov     edx, 7A444856h; Tag
0x140029a64  mov     rcx, r8; P
0x140029a67  call    cs:__imp_ExFreePoolWithTag
0x140029a6e  nop     dword ptr [rax+rax+00h]
0x140029a73  mov     rax, [rbp+57h+var_A0]
0x140029a77  test    rax, rax
0x140029a7a  jz      short loc_140029A90
0x140029a7c  mov     edx, 68444856h; Tag
0x140029a81  mov     rcx, rax; P
0x140029a84  call    cs:__imp_ExFreePoolWithTag
0x140029a8b  nop     dword ptr [rax+rax+00h]
0x140029a90  mov     eax, cs:dword_140087708
0x140029a96  cmp     eax, 4
0x140029a99  jbe     short loc_140029AE4
0x140029a9b  mov     edx, 4
0x140029aa0  lea     rcx, dword_140087708
0x140029aa7  call    _tlgKeywordOn
0x140029aac  test    al, al
0x140029aae  jz      short loc_140029AE4
0x140029ab0  mov     qword ptr [rsp+110h+var_D8], rsi
0x140029ab5  lea     rax, aVhdmpienabletr_11; "VhdmpiEnableTracking: leaving... (0x%08"...
0x140029abc  mov     r9d, 4; int
0x140029ac2  mov     qword ptr [rsp+110h+var_E0], r15
0x140029ac7  mov     dword ptr [rsp+110h+var_E8], edi; char
0x140029acb  lea     rcx, aVhdmpienabletr_4; "VhdmpiEnableTracking"
0x140029ad2  mov     r8d, r9d; int
0x140029ad5  mov     [rsp+110h+var_F0], rax; char *
0x140029ada  mov     edx, 33Ch; int
0x140029adf  call    TraceEvents
0x140029ae4  mov     eax, edi
0x140029ae6  mov     rcx, [rbp+57h+var_40]
0x140029aea  xor     rcx, rsp; StackCookie
  ... truncated ...
```
