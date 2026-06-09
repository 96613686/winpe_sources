# VhdmpiCTLogInitVirtualDiskForTracing(_VHD_VIRTUAL_DISK *,uchar)

- ea: `0x14001fb60`
- end: `0x1400204e8`
- name: `?VhdmpiCTLogInitVirtualDiskForTracing@@YAJPEAU_VHD_VIRTUAL_DISK@@E@Z`
- size: `2440`
- prototype: `__int64 __fastcall(struct _VHD_VIRTUAL_DISK *, unsigned __int8)`
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140049f50`
- `0x1400cf014`

## callees

- `0x14001c050`
- `0x14001f9ac`
- `0x14001fb60`
- `0x14002269c`
- `0x140023980`
- `0x14002b6a4`
- `0x140036284`
- `0x14005dac2`
- `0x14005dbb0`
- `0x14005e100`
- `0x14009d9a4`
- `0x14009e1c0`

## import_xrefs

- `ntoskrnl!ZwCreateFile` at `0x14002010f`
- `ntoskrnl!ZwCreateFile` at `0x14002010f`
- `ntoskrnl!ZwWriteFile` at `0x140020272`
- `ntoskrnl!ZwWriteFile` at `0x140020272`
- `ntoskrnl!ZwOpenKey` at `0x14001fc6c`
- `ntoskrnl!ZwOpenKey` at `0x14001fe06`
- `ntoskrnl!ZwOpenKey` at `0x14001fc6c`
- `ntoskrnl!ZwOpenKey` at `0x14001fe06`
- `ntoskrnl!wcsrchr` at `0x14001fd29`
- `ntoskrnl!wcsrchr` at `0x14001fd48`
- `ntoskrnl!wcsrchr` at `0x14001fda8`
- `ntoskrnl!wcsrchr` at `0x14001fd29`
- `ntoskrnl!wcsrchr` at `0x14001fd48`
- `ntoskrnl!wcsrchr` at `0x14001fda8`
- `ntoskrnl!_wcsicmp` at `0x14001fd6a`
- `ntoskrnl!_wcsicmp` at `0x14001fd84`
- `ntoskrnl!_wcsicmp` at `0x14001fd6a`
- `ntoskrnl!_wcsicmp` at `0x14001fd84`
- `ntoskrnl!ZwQueryValueKey` at `0x14001fe90`
- `ntoskrnl!ZwQueryValueKey` at `0x14001ffdf`
- `ntoskrnl!ZwQueryValueKey` at `0x140020055`
- `ntoskrnl!ZwQueryValueKey` at `0x14001fe90`
- `ntoskrnl!ZwQueryValueKey` at `0x14001ffdf`
- `ntoskrnl!ZwQueryValueKey` at `0x140020055`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001fc30`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001fdc5`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001fe5c`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001ffb5`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002008c`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001fc30`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001fdc5`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001fe5c`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001ffb5`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002008c`
- `ntoskrnl!ZwClose` at `0x1400203d8`
- `ntoskrnl!ZwClose` at `0x14002045b`
- `ntoskrnl!ZwClose` at `0x14002047b`
- `ntoskrnl!ZwClose` at `0x1400203d8`
- `ntoskrnl!ZwClose` at `0x14002045b`
- `ntoskrnl!ZwClose` at `0x14002047b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400203bb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002049d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400204b6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400203bb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002049d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400204b6`
- `ntoskrnl!ExAllocatePool2` at `0x140020013`
- `ntoskrnl!ExAllocatePool2` at `0x140020140`
- `ntoskrnl!ExAllocatePool2` at `0x140020013`
- `ntoskrnl!ExAllocatePool2` at `0x140020140`
- `ntoskrnl!ZwReadFile` at `0x1400201a4`
- `ntoskrnl!ZwReadFile` at `0x1400201a4`

## string_xrefs

- `0x14001fcb6`: `VhdmpiCTLogInitVirtualDiskForTracing: failed to open VHD (0x%I64x) trace registry key. Error 0x%x`
- `0x14001fe45`: `VhdmpiCTLogInitVirtualDiskForTracing: failed to open CT trace registry key for VHD (0x%I64x). Error 0x%x`
- `0x14001fc1c`: `\REGISTRY\MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Virtualization\Replication\CTDiagnostics`
- `0x14002031f`: `VhdmpiCTLogInitVirtualDiskForTracing: failed to open CTTraceFilePath registry key for VHD (0x%I64x). Error 0x%x`
- `0x1400202b7`: `VhdmpiCTLogInitVirtualDiskForTracing: failed to open trace file handle for VHD (0x%I64x). Error 0x%x`
- `0x140020373`: `VhdmpiCTLogInitVirtualDiskForTracing: failed to open CTTraceFlags registry key for VHD (0x%I64x). Error 0x%x`
- `0x14001ff88`: `VhdmpiCTLogInitVirtualDiskForTracing: flags enabled in CTTraceFlagsare not compatible with each other 0x%x`
- `0x14001ffaa`: `CTTraceFilePath`

## pseudocode

```c
__int64 __fastcall VhdmpiCTLogInitVirtualDiskForTracing(struct _VHD_VIRTUAL_DISK *a1, char a2)
{
  const wchar_t *v4; // rbx
  HANDLE *v5; // r13
  wchar_t *v6; // r12
  __int64 Pool2; // r14
  NTSTATUS v9; // eax
  NTSTATUS Status; // edi
  unsigned __int16 v11; // dx
  char *v12; // rax
  wchar_t *v13; // rax
  const wchar_t *v14; // rdi
  wchar_t *v15; // rax
  wchar_t *v16; // rax
  int v17; // eax
  NTSTATUS v18; // eax
  __int64 v19; // rax
  HANDLE v20; // rcx
  int v21; // eax
  unsigned __int64 v22; // rax
  HANDLE v23; // rcx
  int v24; // r8d
  void *v25; // rcx
  ULONG ResultLength; // [rsp+60h] [rbp-A0h] BYREF
  HANDLE Handle; // [rsp+68h] [rbp-98h] BYREF
  union _LARGE_INTEGER ByteOffset; // [rsp+70h] [rbp-90h] BYREF
  void *KeyHandle; // [rsp+78h] [rbp-88h] BYREF
  wchar_t *Str; // [rsp+80h] [rbp-80h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+88h] [rbp-78h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+98h] [rbp-68h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+A8h] [rbp-58h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+B8h] [rbp-48h] BYREF
  struct _UNICODE_STRING v35; // [rsp+E8h] [rbp-18h] BYREF
  struct _UNICODE_STRING v36; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v37[2]; // [rsp+108h] [rbp+8h] BYREF
  struct _OBJECT_ATTRIBUTES v38; // [rsp+118h] [rbp+18h] BYREF
  _DWORD Buffer[1024]; // [rsp+150h] [rbp+50h] BYREF
  _BYTE KeyValueInformation[4]; // [rsp+1150h] [rbp+1050h] BYREF
  int v41; // [rsp+1154h] [rbp+1054h]
  int v42; // [rsp+1158h] [rbp+1058h]
  int v43; // [rsp+115Ch] [rbp+105Ch]

  v35 = 0;
  v36 = 0;
  memset(&v38, 0, sizeof(v38));
  IoStatusBlock = 0;
  memset(Buffer, 0, sizeof(Buffer));
  v4 = 0;
  v5 = (HANDLE *)((char *)a1 + 2152);
  ByteOffset.QuadPart = 0;
  ResultLength = 0;
  Handle = (HANDLE)-1LL;
  v6 = 0;
  KeyHandle = (void *)-1LL;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  Str = 0;
  DestinationString = 0;
  ValueName = 0;
  *(_OWORD *)v37 = 0;
  if ( *((_QWORD *)a1 + 269) != -1 )
    return 0;
  *((_DWORD *)a1 + 536) = 0;
  Pool2 = 0;
  RtlInitUnicodeString(
    &DestinationString,
    L"\\REGISTRY\\MACHINE\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Virtualization\\Replication\\CTDiagnostics");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v9 = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  Status = v9;
  if ( v9 < 0 )
  {
    if ( v9 == -1073741772
      || (unsigned int)dword_1400876D0 <= 2
      || !(unsigned __int8)tlgKeywordOn(&dword_1400876D0, 4096) )
    {
      goto LABEL_67;
    }
    v11 = 3610;
    v12 = "VhdmpiCTLogInitVirtualDiskForTracing: failed to open VHD (0x%I64x) trace registry key. Error 0x%x";
    goto LABEL_8;
  }
  VhdmpiAcquirePassiveLockShared((char *)a1 + 128);
  Status = VhdmpiDuplicateUnicodeStringToString(*((_QWORD *)a1 + 18) + 72LL, &Str);
  VhdmpiReleasePassiveLockShared((char *)a1 + 128);
  v6 = Str;
  v4 = 0;
  if ( Status < 0 )
    goto LABEL_67;
  v13 = wcsrchr(Str, 0x5Cu);
  if ( !v13 || (v14 = v13 + 1, v15 = wcsrchr(v13 + 1, 0x2Eu), (v4 = v15) == 0) )
  {
LABEL_66:
    Status = -1073741823;
    goto LABEL_67;
  }
  if ( _wcsicmp(v15, L".avhd") && _wcsicmp(v4, L".avhdx") )
  {
    *v4 = 0;
    v4 = 0;
  }
  else
  {
    *v4 = 0;
    v16 = wcsrchr(v14, 0x5Fu);
    v4 = 0;
    if ( v16 )
      *v16 = 0;
  }
  RtlInitUnicodeString(&DestinationString, v14);
  ObjectAttributes.RootDirectory = KeyHandle;
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  Status = ZwOpenKey(&Handle, 0x20019u, &ObjectAttributes);
  if ( Status < 0 )
  {
    if ( (unsigned int)dword_1400876D0 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_1400876D0, 4096) )
      goto LABEL_67;
    v11 = 3676;
    v12 = "VhdmpiCTLogInitVirtualDiskForTracing: failed to open CT trace registry key for VHD (0x%I64x). Error 0x%x";
LABEL_8:
    TraceEvents("VhdmpiCTLogInitVirtualDiskForTracing", v11, 2u, 0x1000u, v12, a1, Status);
LABEL_67:
    v25 = (void *)*((_QWORD *)a1 + 270);
    if ( v25 )
    {
      ExFreePoolWithTag(v25, 0x68444856u);
      *((_QWORD *)a1 + 270) = v4;
    }
    if ( *v5 != (HANDLE)-1LL )
    {
      ZwClose(*v5);
      *v5 = (HANDLE)-1LL;
    }
    *((_DWORD *)a1 + 536) = 0;
    if ( Status != -1073741772
      && (unsigned int)dword_1400876D0 > 2
      && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 4096) )
    {
      TraceEvents(
        "VhdmpiCTLogInitVirtualDiskForTracing",
        0xF62u,
        2u,
        0x1000u,
        "VhdmpiCTLogInitVirtualDiskForTracing: failed with status 0x%x for VHD (0x%I64x).",
        Status,
        a1);
    }
    Status = (int)v4;
    goto LABEL_76;
  }
  RtlInitUnicodeString(&ValueName, L"CTTraceFlags");
  Status = ZwQueryValueKey(Handle, &ValueName, KeyValuePartialInformation, KeyValueInformation, 0x10u, &ResultLength);
  if ( Status < 0 || ResultLength != 16 || v41 != 4 || v42 != 4 )
  {
    if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 4096) )
      TraceEvents(
        "VhdmpiCTLogInitVirtualDiskForTracing",
        0xE7Bu,
        2u,
        0x1000u,
        "VhdmpiCTLogInitVirtualDiskForTracing: failed to open CTTraceFlags registry key for VHD (0x%I64x). Error 0x%x",
        a1,
        Status);
    if ( Status < 0 )
      goto LABEL_67;
    goto LABEL_66;
  }
  *((_DWORD *)a1 + 536) = v43;
  if ( a2 && *((char *)a1 + 2144) >= 0 )
  {
    if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 4096) )
      TraceEvents(
        "VhdmpiCTLogInitVirtualDiskForTracing",
        0xE8Bu,
        2u,
        0x1000u,
        "VhdmpiCTLogInitVirtualDiskForTracing: requires always on trace flag, buttracking is always trace flag is not set");
    goto LABEL_66;
  }
  v17 = *((_DWORD *)a1 + 536);
  if ( (v17 & 0x80u) != 0 && (v17 & 0x78) != 0 )
  {
    if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 4096) )
      TraceEvents(
        "VhdmpiCTLogInitVirtualDiskForTracing",
        0xEA0u,
        2u,
        0x1000u,
        "VhdmpiCTLogInitVirtualDiskForTracing: flags enabled in CTTraceFlagsare not compatible with each other 0x%x",
        *((_DWORD *)a1 + 536));
    goto LABEL_66;
  }
  RtlInitUnicodeString(&ValueName, L"CTTraceFilePath");
  v18 = ZwQueryValueKey(Handle, &ValueName, KeyValuePartialInformation, 0, 0, &ResultLength);
  if ( v18 != -1073741789 && v18 != -2147483643 )
    goto LABEL_87;
  Pool2 = ExAllocatePool2(256, ResultLength + 2LL, 1749305430);
  if ( !Pool2 )
  {
LABEL_38:
    Status = -1073741670;
    goto LABEL_67;
  }
  if ( ZwQueryValueKey(Handle, &ValueName, KeyValuePartialInformation, (PVOID)Pool2, ResultLength, &ResultLength) < 0
    || *(_DWORD *)(Pool2 + 4) != 1 )
  {
LABEL_87:
    if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 4096) )
      TraceEvents(
        "VhdmpiCTLogInitVirtualDiskForTracing",
        0xED4u,
        2u,
        0x1000u,
        "VhdmpiCTLogInitVirtualDiskForTracing: failed to open CTTraceFilePath registry key for VHD (0x%I64x). Error 0x%x",
        a1,
        v24);
    goto LABEL_66;
  }
  *(_WORD *)(Pool2 + 2 * ((unsigned __int64)*(unsigned int *)(Pool2 + 8) >> 1) + 12) = 0;
  RtlInitUnicodeString(&v35, (PCWSTR)(Pool2 + 12));
  Status = VhdmpiCreateNtFilePath(&v35, &v36);
  if ( Status < 0 )
    goto LABEL_67;
  v38.Length = 48;
  v38.RootDirectory = 0;
  v38.Attributes = 1600;
  v38.ObjectName = &v36;
  *(_OWORD *)&v38.SecurityDescriptor = 0;
  Status = ZwCreateFile((PHANDLE)a1 + 269, 0xC0100000, &v38, &IoStatusBlock, 0, 0x80u, 1u, 3u, 0x60u, 0, 0);
  if ( Status < 0 || (Status = IoStatusBlock.Status, IoStatusBlock.Status < 0) )
  {
    if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 4096) )
      TraceEvents(
        "VhdmpiCTLogInitVirtualDiskForTracing",
        0xEFFu,
        2u,
        0x1000u,
        "VhdmpiCTLogInitVirtualDiskForTracing: failed to open trace file handle for VHD (0x%I64x). Error 0x%x",
        a1,
        Status);
  }
  else
  {
    v19 = ExAllocatePool2(72, 4096, 1749305430);
    *((_QWORD *)a1 + 270) = v19;
    if ( !v19 )
      goto LABEL_38;
    v20 = *v5;
    *((_QWORD *)a1 + 272) = 0;
    *((_QWORD *)a1 + 271) = 0;
    ByteOffset.QuadPart = 0;
    Status = ZwReadFile(v20, 0, 0, 0, &IoStatusBlock, Buffer, 0x1000u, &ByteOffset, 0);
    if ( Status >= 0 && IoStatusBlock.Status >= 0 )
    {
      v21 = VhdmpiCalculateChecksum(Buffer, 4096, &Buffer[10]);
      if ( Buffer[10] == v21 )
      {
        v22 = *(_QWORD *)&Buffer[11];
        if ( *(_QWORD *)&Buffer[11] )
        {
          *((_QWORD *)a1 + 272) = *(_QWORD *)&Buffer[11];
          if ( v22 > 0x1000 )
            *((_QWORD *)a1 + 271) = v22 - 4096;
          goto LABEL_76;
        }
      }
    }
    memset(Buffer, 0, sizeof(Buffer));
    VhdmpiPopulatedLogFileHeader(Buffer, (__int64)v37, (__int64)v37, 0);
    v23 = *v5;
    ByteOffset.QuadPart = 0;
    Status = ZwWriteFile(v23, 0, 0, 0, &IoStatusBlock, Buffer, 0x1000u, &ByteOffset, 0);
    if ( Status >= 0 )
      Status = IoStatusBlock.Status;
    *((_QWORD *)a1 + 272) += 4096LL;
  }
  if ( Status < 0 )
    goto LABEL_67;
LABEL_76:
  if ( Handle != (HANDLE)-1LL )
  {
    ZwClose(Handle);
    Handle = (HANDLE)-1LL;
  }
  if ( KeyHandle != (void *)-1LL )
  {
    ZwClose(KeyHandle);
    KeyHandle = (void *)-1LL;
  }
  if ( Pool2 )
    ExFreePoolWithTag((PVOID)Pool2, 0x68444856u);
  if ( v6 )
    ExFreePoolWithTag(v6, 0x7A444856u);
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x14001fb60  push    rbp
0x14001fb62  push    rbx
0x14001fb63  push    rsi
0x14001fb64  push    rdi
0x14001fb65  push    r12
0x14001fb67  push    r13
0x14001fb69  push    r14
0x14001fb6b  push    r15
0x14001fb6d  lea     rbp, [rsp-1078h]
0x14001fb75  mov     eax, 1178h
0x14001fb7a  call    __chkstk_0
0x14001fb7f  sub     rsp, rax
0x14001fb82  mov     rax, cs:__security_cookie
0x14001fb89  xor     rax, rsp
0x14001fb8c  mov     [rbp+10B0h+var_50], rax
0x14001fb93  xorps   xmm0, xmm0
0x14001fb96  mov     r15b, dl
0x14001fb99  mov     rsi, rcx
0x14001fb9c  xorps   xmm1, xmm1
0x14001fb9f  xor     edx, edx; Val
0x14001fba1  lea     rcx, [rbp+10B0h+Buffer]; void *
0x14001fba5  mov     r8d, 1000h; Size
0x14001fbab  movups  xmmword ptr [rbp+10B0h+var_10C8.Length], xmm0
0x14001fbaf  movups  xmmword ptr [rbp+10B0h+var_10B8.Length], xmm1
0x14001fbb3  movups  xmmword ptr [rbp+10B0h+var_1098.Length], xmm0
0x14001fbb7  movups  xmmword ptr [rbp+10B0h+var_1098.ObjectName], xmm0
0x14001fbbb  movups  xmmword ptr [rbp+10B0h+var_1098.SecurityDescriptor], xmm0
0x14001fbbf  movups  xmmword ptr [rbp+10B0h+IoStatusBlock], xmm0
0x14001fbc3  call    memset
0x14001fbc8  xor     ebx, ebx
0x14001fbca  lea     r13, [rsi+868h]
0x14001fbd1  xorps   xmm0, xmm0
0x14001fbd4  mov     qword ptr [rsp+11B0h+ByteOffset], rbx
0x14001fbd9  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001fbdd  mov     [rsp+11B0h+var_1150], ebx
0x14001fbe1  xorps   xmm1, xmm1
0x14001fbe4  mov     [rsp+11B0h+Handle], rax
0x14001fbe9  mov     r12d, ebx
0x14001fbec  mov     [rsp+11B0h+KeyHandle], rax
0x14001fbf1  movups  xmmword ptr [rbp+10B0h+ObjectAttributes.Length], xmm0
0x14001fbf5  mov     [rbp+10B0h+Str], rbx
0x14001fbf9  movups  xmmword ptr [rbp+10B0h+ObjectAttributes.ObjectName], xmm0
0x14001fbfd  movups  xmmword ptr [rbp+10B0h+ObjectAttributes.SecurityDescriptor], xmm0
0x14001fc01  movups  xmmword ptr [rbp+10B0h+DestinationString.Length], xmm0
0x14001fc05  movups  xmmword ptr [rbp+10B0h+ValueName.Length], xmm1
0x14001fc09  movups  xmmword ptr [rbp+10B0h+var_10A8], xmm0
0x14001fc0d  cmp     [r13+0], rax
0x14001fc11  jz      short loc_14001FC1A
0x14001fc13  xor     eax, eax
0x14001fc15  jmp     loc_1400204C4
0x14001fc1a  xor     eax, eax
0x14001fc1c  lea     rdx, aRegistryMachin_1; "\\REGISTRY\\MACHINE\\SOFTWARE\\Microsof"...
0x14001fc23  lea     rcx, [rbp+10B0h+DestinationString]; DestinationString
0x14001fc27  mov     [rsi+860h], eax
0x14001fc2d  mov     r14, rbx
0x14001fc30  call    cs:__imp_RtlInitUnicodeString
0x14001fc37  nop     dword ptr [rax+rax+00h]
0x14001fc3c  lea     rax, [rbp+10B0h+DestinationString]
0x14001fc40  mov     [rbp+10B0h+ObjectAttributes.Length], 30h ; '0'
0x14001fc47  xorps   xmm0, xmm0
0x14001fc4a  mov     [rbp+10B0h+ObjectAttributes.ObjectName], rax
0x14001fc4e  lea     r8, [rbp+10B0h+ObjectAttributes]; ObjectAttributes
0x14001fc52  mov     [rbp+10B0h+ObjectAttributes.RootDirectory], rbx
0x14001fc56  mov     edx, 20019h; DesiredAccess
0x14001fc5b  mov     [rbp+10B0h+ObjectAttributes.Attributes], 240h
0x14001fc62  lea     rcx, [rsp+11B0h+KeyHandle]; KeyHandle
0x14001fc67  movdqu  xmmword ptr [rbp+10B0h+ObjectAttributes.SecurityDescriptor], xmm0
0x14001fc6c  call    cs:__imp_ZwOpenKey
0x14001fc73  nop     dword ptr [rax+rax+00h]
0x14001fc78  mov     edi, eax
0x14001fc7a  test    eax, eax
0x14001fc7c  jns     short loc_14001FCE8
0x14001fc7e  cmp     eax, 0C0000034h
0x14001fc83  jz      loc_1400203AA
0x14001fc89  mov     eax, cs:dword_1400876D0
0x14001fc8f  cmp     eax, 2
0x14001fc92  jbe     loc_1400203AA
0x14001fc98  mov     edx, 1000h
0x14001fc9d  lea     rcx, dword_1400876D0
0x14001fca4  call    _tlgKeywordOn
0x14001fca9  test    al, al
0x14001fcab  jz      loc_1400203AA
0x14001fcb1  mov     edx, 0E1Ah; int
0x14001fcb6  lea     rax, aVhdmpictlogini_8; "VhdmpiCTLogInitVirtualDiskForTracing: f"...
0x14001fcbd  mov     [rsp+11B0h+ShareAccess], edi
0x14001fcc1  lea     rcx, aVhdmpictlogini_3; "VhdmpiCTLogInitVirtualDiskForTracing"
0x14001fcc8  mov     [rsp+11B0h+ResultLength], rsi; char
0x14001fccd  mov     r9d, 1000h; int
0x14001fcd3  mov     r8d, 2; int
0x14001fcd9  mov     qword ptr [rsp+11B0h+Length], rax; char *
0x14001fcde  call    TraceEvents
0x14001fce3  jmp     loc_1400203AA
0x14001fce8  lea     rbx, [rsi+80h]
0x14001fcef  mov     rcx, rbx
0x14001fcf2  call    VhdmpiAcquirePassiveLockShared
0x14001fcf7  mov     rcx, [rsi+90h]
0x14001fcfe  lea     rdx, [rbp+10B0h+Str]
0x14001fd02  add     rcx, 48h ; 'H'
0x14001fd06  call    VhdmpiDuplicateUnicodeStringToString
0x14001fd0b  mov     rcx, rbx
0x14001fd0e  mov     edi, eax
0x14001fd10  call    VhdmpiReleasePassiveLockShared
0x14001fd15  mov     r12, [rbp+10B0h+Str]
0x14001fd19  xor     ebx, ebx
0x14001fd1b  test    edi, edi
0x14001fd1d  js      loc_1400203AA
0x14001fd23  lea     edx, [rbx+5Ch]; Ch
0x14001fd26  mov     rcx, r12; Str
0x14001fd29  call    cs:__imp_wcsrchr
0x14001fd30  nop     dword ptr [rax+rax+00h]
0x14001fd35  test    rax, rax
0x14001fd38  jz      loc_1400203A5
0x14001fd3e  lea     rdi, [rax+2]
0x14001fd42  mov     rcx, rdi; Str
0x14001fd45  lea     edx, [rbx+2Eh]; Ch
0x14001fd48  call    cs:__imp_wcsrchr
0x14001fd4f  nop     dword ptr [rax+rax+00h]
0x14001fd54  mov     rbx, rax
0x14001fd57  test    rax, rax
0x14001fd5a  jz      loc_1400203A5
0x14001fd60  lea     rdx, aAvhd; ".avhd"
0x14001fd67  mov     rcx, rbx; Str1
0x14001fd6a  call    cs:__imp__wcsicmp
0x14001fd71  nop     dword ptr [rax+rax+00h]
0x14001fd76  test    eax, eax
0x14001fd78  jz      short loc_14001FD9D
0x14001fd7a  lea     rdx, aAvhdx; ".avhdx"
0x14001fd81  mov     rcx, rbx; Str1
0x14001fd84  call    cs:__imp__wcsicmp
0x14001fd8b  nop     dword ptr [rax+rax+00h]
0x14001fd90  test    eax, eax
0x14001fd92  jz      short loc_14001FD9D
0x14001fd94  xor     eax, eax
0x14001fd96  mov     [rbx], ax
0x14001fd99  xor     ebx, ebx
0x14001fd9b  jmp     short loc_14001FDBE
0x14001fd9d  xor     eax, eax
0x14001fd9f  mov     rcx, rdi; Str
0x14001fda2  mov     [rbx], ax
0x14001fda5  lea     edx, [rax+5Fh]; Ch
0x14001fda8  call    cs:__imp_wcsrchr
0x14001fdaf  nop     dword ptr [rax+rax+00h]
0x14001fdb4  xor     ebx, ebx
0x14001fdb6  test    rax, rax
0x14001fdb9  jz      short loc_14001FDBE
0x14001fdbb  mov     [rax], bx
0x14001fdbe  mov     rdx, rdi; SourceString
0x14001fdc1  lea     rcx, [rbp+10B0h+DestinationString]; DestinationString
0x14001fdc5  call    cs:__imp_RtlInitUnicodeString
0x14001fdcc  nop     dword ptr [rax+rax+00h]
0x14001fdd1  mov     rax, [rsp+11B0h+KeyHandle]
0x14001fdd6  lea     r8, [rbp+10B0h+ObjectAttributes]; ObjectAttributes
0x14001fdda  mov     [rbp+10B0h+ObjectAttributes.RootDirectory], rax
0x14001fdde  lea     rcx, [rsp+11B0h+Handle]; KeyHandle
0x14001fde3  lea     rax, [rbp+10B0h+DestinationString]
0x14001fde7  mov     [rbp+10B0h+ObjectAttributes.Length], 30h ; '0'
0x14001fdee  xorps   xmm0, xmm0
0x14001fdf1  mov     [rbp+10B0h+ObjectAttributes.ObjectName], rax
0x14001fdf5  mov     edx, 20019h; DesiredAccess
0x14001fdfa  mov     [rbp+10B0h+ObjectAttributes.Attributes], 240h
0x14001fe01  movdqu  xmmword ptr [rbp+10B0h+ObjectAttributes.SecurityDescriptor], xmm0
0x14001fe06  call    cs:__imp_ZwOpenKey
0x14001fe0d  nop     dword ptr [rax+rax+00h]
0x14001fe12  mov     edi, eax
0x14001fe14  test    eax, eax
0x14001fe16  jns     short loc_14001FE51
0x14001fe18  mov     eax, cs:dword_1400876D0
0x14001fe1e  cmp     eax, 2
0x14001fe21  jbe     loc_1400203AA
0x14001fe27  mov     edx, 1000h
0x14001fe2c  lea     rcx, dword_1400876D0
0x14001fe33  call    _tlgKeywordOn
0x14001fe38  test    al, al
0x14001fe3a  jz      loc_1400203AA
0x14001fe40  mov     edx, 0E5Ch
0x14001fe45  lea     rax, aVhdmpictlogini_6; "VhdmpiCTLogInitVirtualDiskForTracing: f"...
0x14001fe4c  jmp     loc_14001FCBD
0x14001fe51  lea     rdx, aCttraceflags; "CTTraceFlags"
0x14001fe58  lea     rcx, [rbp+10B0h+ValueName]; DestinationString
0x14001fe5c  call    cs:__imp_RtlInitUnicodeString
0x14001fe63  nop     dword ptr [rax+rax+00h]
0x14001fe68  mov     rcx, [rsp+11B0h+Handle]; KeyHandle
0x14001fe6d  lea     rax, [rsp+11B0h+var_1150]
0x14001fe72  mov     [rsp+11B0h+ResultLength], rax; char
0x14001fe77  lea     r9, [rbp+10B0h+KeyValueInformation]; KeyValueInformation
0x14001fe7e  mov     r8d, 2; KeyValueInformationClass
0x14001fe84  mov     [rsp+11B0h+Length], 10h; Length
0x14001fe8c  lea     rdx, [rbp+10B0h+ValueName]; ValueName
0x14001fe90  call    cs:__imp_ZwQueryValueKey
0x14001fe97  nop     dword ptr [rax+rax+00h]
0x14001fe9c  mov     edi, eax
0x14001fe9e  test    eax, eax
0x14001fea0  js      loc_14002034F
0x14001fea6  cmp     [rsp+11B0h+var_1150], 10h
0x14001feab  jnz     loc_14002034F
0x14001feb1  cmp     [rbp+10B0h+var_5C], 4
0x14001feb8  jnz     loc_14002034F
0x14001febe  cmp     [rbp+10B0h+var_58], 4
0x14001fec5  jnz     loc_14002034F
0x14001fecb  mov     eax, [rbp+10B0h+var_54]
0x14001fed1  mov     [rsi+860h], eax
0x14001fed7  test    r15b, r15b
0x14001feda  jz      short loc_14001FF3C
0x14001fedc  mov     al, [rsi+860h]
0x14001fee2  test    al, al
0x14001fee4  js      short loc_14001FF3C
0x14001fee6  mov     eax, cs:dword_1400876D0
0x14001feec  cmp     eax, 2
0x14001feef  jbe     loc_1400203A5
0x14001fef5  mov     edx, 1000h
0x14001fefa  lea     rcx, dword_1400876D0
0x14001ff01  call    _tlgKeywordOn
0x14001ff06  test    al, al
0x14001ff08  jz      loc_1400203A5
0x14001ff0e  lea     rax, aVhdmpictlogini_5; "VhdmpiCTLogInitVirtualDiskForTracing: r"...
0x14001ff15  mov     edx, 0E8Bh; int
0x14001ff1a  mov     r9d, 1000h; int
0x14001ff20  mov     qword ptr [rsp+11B0h+Length], rax; char *
0x14001ff25  mov     r8d, 2; int
0x14001ff2b  lea     rcx, aVhdmpictlogini_3; "VhdmpiCTLogInitVirtualDiskForTracing"
0x14001ff32  call    TraceEvents
0x14001ff37  jmp     loc_1400203A5
0x14001ff3c  mov     eax, [rsi+860h]
0x14001ff42  test    al, al
0x14001ff44  jns     short loc_14001FFAA
0x14001ff46  test    al, 78h
0x14001ff48  jz      short loc_14001FFAA
0x14001ff4a  mov     eax, cs:dword_1400876D0
0x14001ff50  cmp     eax, 2
0x14001ff53  jbe     loc_1400203A5
0x14001ff59  mov     edx, 1000h
0x14001ff5e  lea     rcx, dword_1400876D0
0x14001ff65  call    _tlgKeywordOn
0x14001ff6a  test    al, al
0x14001ff6c  jz      loc_1400203A5
0x14001ff72  mov     eax, [rsi+860h]
0x14001ff78  lea     rcx, aVhdmpictlogini_3; "VhdmpiCTLogInitVirtualDiskForTracing"
0x14001ff7f  mov     dword ptr [rsp+11B0h+ResultLength], eax; char
0x14001ff83  mov     edx, 0EA0h; int
0x14001ff88  lea     rax, aVhdmpictlogini_1; "VhdmpiCTLogInitVirtualDiskForTracing: f"...
0x14001ff8f  mov     r9d, 1000h; int
0x14001ff95  mov     r8d, 2; int
0x14001ff9b  mov     qword ptr [rsp+11B0h+Length], rax; char *
0x14001ffa0  call    TraceEvents
0x14001ffa5  jmp     loc_1400203A5
0x14001ffaa  lea     rdx, aCttracefilepat; "CTTraceFilePath"
0x14001ffb1  lea     rcx, [rbp+10B0h+ValueName]; DestinationString
0x14001ffb5  call    cs:__imp_RtlInitUnicodeString
0x14001ffbc  nop     dword ptr [rax+rax+00h]
0x14001ffc1  mov     rcx, [rsp+11B0h+Handle]; KeyHandle
0x14001ffc6  lea     rax, [rsp+11B0h+var_1150]
0x14001ffcb  xor     r9d, r9d; KeyValueInformation
0x14001ffce  mov     [rsp+11B0h+ResultLength], rax; ResultLength
0x14001ffd3  lea     rdx, [rbp+10B0h+ValueName]; ValueName
0x14001ffd7  mov     [rsp+11B0h+Length], ebx; Length
0x14001ffdb  lea     r8d, [r9+2]; KeyValueInformationClass
0x14001ffdf  call    cs:__imp_ZwQueryValueKey
0x14001ffe6  nop     dword ptr [rax+rax+00h]
0x14001ffeb  mov     r8d, eax
0x14001ffee  cmp     eax, 0C0000023h
0x14001fff3  jz      short loc_140020000
0x14001fff5  cmp     eax, 80000005h
0x14001fffa  jnz     loc_1400202F2
0x140020000  mov     edx, [rsp+11B0h+var_1150]
0x140020004  mov     ecx, 100h
0x140020009  add     rdx, 2
0x14002000d  mov     r8d, 68444856h
0x140020013  call    cs:__imp_ExAllocatePool2
0x14002001a  nop     dword ptr [rax+rax+00h]
0x14002001f  mov     r14, rax
0x140020022  test    rax, rax
0x140020025  jnz     short loc_140020031
0x140020027  mov     edi, 0C000009Ah
0x14002002c  jmp     loc_1400203AA
0x140020031  mov     rcx, [rsp+11B0h+Handle]; KeyHandle
0x140020036  lea     rax, [rsp+11B0h+var_1150]
0x14002003b  mov     [rsp+11B0h+ResultLength], rax; ResultLength
0x140020040  lea     rdx, [rbp+10B0h+ValueName]; ValueName
0x140020044  mov     eax, [rsp+11B0h+var_1150]
0x140020048  mov     r9, r14; KeyValueInformation
0x14002004b  mov     r8d, 2; KeyValueInformationClass
0x140020051  mov     [rsp+11B0h+Length], eax; Length
0x140020055  call    cs:__imp_ZwQueryValueKey
0x14002005c  nop     dword ptr [rax+rax+00h]
0x140020061  mov     r8d, eax
0x140020064  test    eax, eax
0x140020066  js      loc_1400202F2
0x14002006c  cmp     dword ptr [r14+4], 1
0x140020071  jnz     loc_1400202F2
0x140020077  mov     ecx, [r14+8]
0x14002007b  lea     rdx, [r14+0Ch]; SourceString
0x14002007f  shr     rcx, 1
0x140020082  mov     [r14+rcx*2+0Ch], bx
0x140020088  lea     rcx, [rbp+10B0h+var_10C8]; DestinationString
0x14002008c  call    cs:__imp_RtlInitUnicodeString
0x140020093  nop     dword ptr [rax+rax+00h]
0x140020098  lea     rdx, [rbp+10B0h+var_10B8]; struct _UNICODE_STRING *
0x14002009c  lea     rcx, [rbp+10B0h+var_10C8]; struct _UNICODE_STRING *
0x1400200a0  call    VhdmpiCreateNtFilePath
0x1400200a5  mov     edi, eax
  ... truncated ...
```
