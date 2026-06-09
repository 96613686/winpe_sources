# VhdmpiCTLogInitVirtualDiskForTracing(_VHD_VIRTUAL_DISK *,uchar)

- ea: `0x14001f740`
- end: `0x1400200c8`
- name: `?VhdmpiCTLogInitVirtualDiskForTracing@@YAJPEAU_VHD_VIRTUAL_DISK@@E@Z`
- size: `2440`
- prototype: `__int64 __fastcall(struct _VHD_VIRTUAL_DISK *, char)`
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140049b60`
- `0x1400cf084`

## callees

- `0x14001bc30`
- `0x14001f58c`
- `0x14001f740`
- `0x14002227c`
- `0x140023560`
- `0x14002b184`
- `0x140035e94`
- `0x14005d6d2`
- `0x14005d7c0`
- `0x14005dd00`
- `0x14009d9a4`
- `0x14009e1c0`

## import_xrefs

- `ntoskrnl!ZwCreateFile` at `0x14001fcef`
- `ntoskrnl!ZwCreateFile` at `0x14001fcef`
- `ntoskrnl!ZwWriteFile` at `0x14001fe52`
- `ntoskrnl!ZwWriteFile` at `0x14001fe52`
- `ntoskrnl!ZwOpenKey` at `0x14001f84c`
- `ntoskrnl!ZwOpenKey` at `0x14001f9e6`
- `ntoskrnl!ZwOpenKey` at `0x14001f84c`
- `ntoskrnl!ZwOpenKey` at `0x14001f9e6`
- `ntoskrnl!wcsrchr` at `0x14001f909`
- `ntoskrnl!wcsrchr` at `0x14001f928`
- `ntoskrnl!wcsrchr` at `0x14001f988`
- `ntoskrnl!wcsrchr` at `0x14001f909`
- `ntoskrnl!wcsrchr` at `0x14001f928`
- `ntoskrnl!wcsrchr` at `0x14001f988`
- `ntoskrnl!_wcsicmp` at `0x14001f94a`
- `ntoskrnl!_wcsicmp` at `0x14001f964`
- `ntoskrnl!_wcsicmp` at `0x14001f94a`
- `ntoskrnl!_wcsicmp` at `0x14001f964`
- `ntoskrnl!ZwQueryValueKey` at `0x14001fa70`
- `ntoskrnl!ZwQueryValueKey` at `0x14001fbbf`
- `ntoskrnl!ZwQueryValueKey` at `0x14001fc35`
- `ntoskrnl!ZwQueryValueKey` at `0x14001fa70`
- `ntoskrnl!ZwQueryValueKey` at `0x14001fbbf`
- `ntoskrnl!ZwQueryValueKey` at `0x14001fc35`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001f810`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001f9a5`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001fa3c`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001fb95`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001fc6c`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001f810`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001f9a5`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001fa3c`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001fb95`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001fc6c`
- `ntoskrnl!ZwClose` at `0x14001ffb8`
- `ntoskrnl!ZwClose` at `0x14002003b`
- `ntoskrnl!ZwClose` at `0x14002005b`
- `ntoskrnl!ZwClose` at `0x14001ffb8`
- `ntoskrnl!ZwClose` at `0x14002003b`
- `ntoskrnl!ZwClose` at `0x14002005b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001ff9b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002007d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140020096`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001ff9b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002007d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140020096`
- `ntoskrnl!ExAllocatePool2` at `0x14001fbf3`
- `ntoskrnl!ExAllocatePool2` at `0x14001fd20`
- `ntoskrnl!ExAllocatePool2` at `0x14001fbf3`
- `ntoskrnl!ExAllocatePool2` at `0x14001fd20`
- `ntoskrnl!ZwReadFile` at `0x14001fd84`
- `ntoskrnl!ZwReadFile` at `0x14001fd84`

## string_xrefs

- `0x14001fe97`: `VhdmpiCTLogInitVirtualDiskForTracing: failed to open trace file handle for VHD (0x%I64x). Error 0x%x`
- `0x14001fb68`: `VhdmpiCTLogInitVirtualDiskForTracing: flags enabled in CTTraceFlagsare not compatible with each other 0x%x`
- `0x14001fb8a`: `CTTraceFilePath`
- `0x14001feff`: `VhdmpiCTLogInitVirtualDiskForTracing: failed to open CTTraceFilePath registry key for VHD (0x%I64x). Error 0x%x`
- `0x14001fa25`: `VhdmpiCTLogInitVirtualDiskForTracing: failed to open CT trace registry key for VHD (0x%I64x). Error 0x%x`
- `0x14001ff53`: `VhdmpiCTLogInitVirtualDiskForTracing: failed to open CTTraceFlags registry key for VHD (0x%I64x). Error 0x%x`
- `0x14001f7fc`: `\REGISTRY\MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Virtualization\Replication\CTDiagnostics`
- `0x14001f896`: `VhdmpiCTLogInitVirtualDiskForTracing: failed to open VHD (0x%I64x) trace registry key. Error 0x%x`

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
  int v11; // edx
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
  void *v24; // rcx
  char ResultLength; // [rsp+28h] [rbp-D8h]
  ULONG Length; // [rsp+60h] [rbp-A0h] BYREF
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
  Length = 0;
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
      || (unsigned int)dword_140087708 <= 2
      || !(unsigned __int8)tlgKeywordOn(&dword_140087708, 4096) )
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
    if ( (unsigned int)dword_140087708 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140087708, 4096) )
      goto LABEL_67;
    v11 = 3676;
    v12 = "VhdmpiCTLogInitVirtualDiskForTracing: failed to open CT trace registry key for VHD (0x%I64x). Error 0x%x";
LABEL_8:
    TraceEvents((int)"VhdmpiCTLogInitVirtualDiskForTracing", v11, 2, 4096, v12, (char)a1);
LABEL_67:
    v24 = (void *)*((_QWORD *)a1 + 270);
    if ( v24 )
    {
      ExFreePoolWithTag(v24, 0x68444856u);
      *((_QWORD *)a1 + 270) = v4;
    }
    if ( *v5 != (HANDLE)-1LL )
    {
      ZwClose(*v5);
      *v5 = (HANDLE)-1LL;
    }
    *((_DWORD *)a1 + 536) = 0;
    if ( Status != -1073741772
      && (unsigned int)dword_140087708 > 2
      && (unsigned __int8)tlgKeywordOn(&dword_140087708, 4096) )
    {
      TraceEvents(
        (int)"VhdmpiCTLogInitVirtualDiskForTracing",
        3938,
        2,
        4096,
        "VhdmpiCTLogInitVirtualDiskForTracing: failed with status 0x%x for VHD (0x%I64x).",
        Status);
    }
    Status = (int)v4;
    goto LABEL_76;
  }
  RtlInitUnicodeString(&ValueName, L"CTTraceFlags");
  Status = ZwQueryValueKey(Handle, &ValueName, KeyValuePartialInformation, KeyValueInformation, 0x10u, &Length);
  if ( Status < 0 || Length != 16 || v41 != 4 || v42 != 4 )
  {
    if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 4096) )
      TraceEvents(
        (int)"VhdmpiCTLogInitVirtualDiskForTracing",
        3707,
        2,
        4096,
        "VhdmpiCTLogInitVirtualDiskForTracing: failed to open CTTraceFlags registry key for VHD (0x%I64x). Error 0x%x",
        (char)a1);
    if ( Status < 0 )
      goto LABEL_67;
    goto LABEL_66;
  }
  *((_DWORD *)a1 + 536) = v43;
  if ( a2 && *((char *)a1 + 2144) >= 0 )
  {
    if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 4096) )
      TraceEvents(
        (int)"VhdmpiCTLogInitVirtualDiskForTracing",
        3723,
        2,
        4096,
        "VhdmpiCTLogInitVirtualDiskForTracing: requires always on trace flag, buttracking is always trace flag is not set",
        ResultLength);
    goto LABEL_66;
  }
  v17 = *((_DWORD *)a1 + 536);
  if ( (v17 & 0x80u) != 0 && (v17 & 0x78) != 0 )
  {
    if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 4096) )
      TraceEvents(
        (int)"VhdmpiCTLogInitVirtualDiskForTracing",
        3744,
        2,
        4096,
        "VhdmpiCTLogInitVirtualDiskForTracing: flags enabled in CTTraceFlagsare not compatible with each other 0x%x",
        *((_DWORD *)a1 + 536));
    goto LABEL_66;
  }
  RtlInitUnicodeString(&ValueName, L"CTTraceFilePath");
  v18 = ZwQueryValueKey(Handle, &ValueName, KeyValuePartialInformation, 0, 0, &Length);
  if ( v18 != -1073741789 && v18 != -2147483643 )
    goto LABEL_87;
  Pool2 = ExAllocatePool2(256, Length + 2LL, 1749305430);
  if ( !Pool2 )
  {
LABEL_38:
    Status = -1073741670;
    goto LABEL_67;
  }
  if ( ZwQueryValueKey(Handle, &ValueName, KeyValuePartialInformation, (PVOID)Pool2, Length, &Length) < 0
    || *(_DWORD *)(Pool2 + 4) != 1 )
  {
LABEL_87:
    if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 4096) )
      TraceEvents(
        (int)"VhdmpiCTLogInitVirtualDiskForTracing",
        3796,
        2,
        4096,
        "VhdmpiCTLogInitVirtualDiskForTracing: failed to open CTTraceFilePath registry key for VHD (0x%I64x). Error 0x%x",
        (char)a1);
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
    if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 4096) )
      TraceEvents(
        (int)"VhdmpiCTLogInitVirtualDiskForTracing",
        3839,
        2,
        4096,
        "VhdmpiCTLogInitVirtualDiskForTracing: failed to open trace file handle for VHD (0x%I64x). Error 0x%x",
        (char)a1);
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
0x14001f740  push    rbp
0x14001f742  push    rbx
0x14001f743  push    rsi
0x14001f744  push    rdi
0x14001f745  push    r12
0x14001f747  push    r13
0x14001f749  push    r14
0x14001f74b  push    r15
0x14001f74d  lea     rbp, [rsp-1078h]
0x14001f755  mov     eax, 1178h
0x14001f75a  call    __chkstk_0
0x14001f75f  sub     rsp, rax
0x14001f762  mov     rax, cs:__security_cookie
0x14001f769  xor     rax, rsp
0x14001f76c  mov     [rbp+10B0h+var_50], rax
0x14001f773  xorps   xmm0, xmm0
0x14001f776  mov     r15b, dl
0x14001f779  mov     rsi, rcx
0x14001f77c  xorps   xmm1, xmm1
0x14001f77f  xor     edx, edx; Val
0x14001f781  lea     rcx, [rbp+10B0h+Buffer]; void *
0x14001f785  mov     r8d, 1000h; Size
0x14001f78b  movups  xmmword ptr [rbp+10B0h+var_10C8.Length], xmm0
0x14001f78f  movups  xmmword ptr [rbp+10B0h+var_10B8.Length], xmm1
0x14001f793  movups  xmmword ptr [rbp+10B0h+var_1098.Length], xmm0
0x14001f797  movups  xmmword ptr [rbp+10B0h+var_1098.ObjectName], xmm0
0x14001f79b  movups  xmmword ptr [rbp+10B0h+var_1098.SecurityDescriptor], xmm0
0x14001f79f  movups  xmmword ptr [rbp+10B0h+IoStatusBlock], xmm0
0x14001f7a3  call    memset
0x14001f7a8  xor     ebx, ebx
0x14001f7aa  lea     r13, [rsi+868h]
0x14001f7b1  xorps   xmm0, xmm0
0x14001f7b4  mov     qword ptr [rsp+11B0h+ByteOffset], rbx
0x14001f7b9  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001f7bd  mov     [rsp+11B0h+var_1150], ebx
0x14001f7c1  xorps   xmm1, xmm1
0x14001f7c4  mov     [rsp+11B0h+Handle], rax
0x14001f7c9  mov     r12d, ebx
0x14001f7cc  mov     [rsp+11B0h+KeyHandle], rax
0x14001f7d1  movups  xmmword ptr [rbp+10B0h+ObjectAttributes.Length], xmm0
0x14001f7d5  mov     [rbp+10B0h+Str], rbx
0x14001f7d9  movups  xmmword ptr [rbp+10B0h+ObjectAttributes.ObjectName], xmm0
0x14001f7dd  movups  xmmword ptr [rbp+10B0h+ObjectAttributes.SecurityDescriptor], xmm0
0x14001f7e1  movups  xmmword ptr [rbp+10B0h+DestinationString.Length], xmm0
0x14001f7e5  movups  xmmword ptr [rbp+10B0h+ValueName.Length], xmm1
0x14001f7e9  movups  xmmword ptr [rbp+10B0h+var_10A8], xmm0
0x14001f7ed  cmp     [r13+0], rax
0x14001f7f1  jz      short loc_14001F7FA
0x14001f7f3  xor     eax, eax
0x14001f7f5  jmp     loc_1400200A4
0x14001f7fa  xor     eax, eax
0x14001f7fc  lea     rdx, aRegistryMachin_1; "\\REGISTRY\\MACHINE\\SOFTWARE\\Microsof"...
0x14001f803  lea     rcx, [rbp+10B0h+DestinationString]; DestinationString
0x14001f807  mov     [rsi+860h], eax
0x14001f80d  mov     r14, rbx
0x14001f810  call    cs:__imp_RtlInitUnicodeString
0x14001f817  nop     dword ptr [rax+rax+00h]
0x14001f81c  lea     rax, [rbp+10B0h+DestinationString]
0x14001f820  mov     [rbp+10B0h+ObjectAttributes.Length], 30h ; '0'
0x14001f827  xorps   xmm0, xmm0
0x14001f82a  mov     [rbp+10B0h+ObjectAttributes.ObjectName], rax
0x14001f82e  lea     r8, [rbp+10B0h+ObjectAttributes]; ObjectAttributes
0x14001f832  mov     [rbp+10B0h+ObjectAttributes.RootDirectory], rbx
0x14001f836  mov     edx, 20019h; DesiredAccess
0x14001f83b  mov     [rbp+10B0h+ObjectAttributes.Attributes], 240h
0x14001f842  lea     rcx, [rsp+11B0h+KeyHandle]; KeyHandle
0x14001f847  movdqu  xmmword ptr [rbp+10B0h+ObjectAttributes.SecurityDescriptor], xmm0
0x14001f84c  call    cs:__imp_ZwOpenKey
0x14001f853  nop     dword ptr [rax+rax+00h]
0x14001f858  mov     edi, eax
0x14001f85a  test    eax, eax
0x14001f85c  jns     short loc_14001F8C8
0x14001f85e  cmp     eax, 0C0000034h
0x14001f863  jz      loc_14001FF8A
0x14001f869  mov     eax, cs:dword_140087708
0x14001f86f  cmp     eax, 2
0x14001f872  jbe     loc_14001FF8A
0x14001f878  mov     edx, 1000h
0x14001f87d  lea     rcx, dword_140087708
0x14001f884  call    _tlgKeywordOn
0x14001f889  test    al, al
0x14001f88b  jz      loc_14001FF8A
0x14001f891  mov     edx, 0E1Ah; int
0x14001f896  lea     rax, aVhdmpictlogini_8; "VhdmpiCTLogInitVirtualDiskForTracing: f"...
0x14001f89d  mov     [rsp+11B0h+ShareAccess], edi
0x14001f8a1  lea     rcx, aVhdmpictlogini_3; "VhdmpiCTLogInitVirtualDiskForTracing"
0x14001f8a8  mov     [rsp+11B0h+ResultLength], rsi; char
0x14001f8ad  mov     r9d, 1000h; int
0x14001f8b3  mov     r8d, 2; int
0x14001f8b9  mov     qword ptr [rsp+11B0h+Length], rax; char *
0x14001f8be  call    TraceEvents
0x14001f8c3  jmp     loc_14001FF8A
0x14001f8c8  lea     rbx, [rsi+80h]
0x14001f8cf  mov     rcx, rbx
0x14001f8d2  call    VhdmpiAcquirePassiveLockShared
0x14001f8d7  mov     rcx, [rsi+90h]
0x14001f8de  lea     rdx, [rbp+10B0h+Str]
0x14001f8e2  add     rcx, 48h ; 'H'
0x14001f8e6  call    VhdmpiDuplicateUnicodeStringToString
0x14001f8eb  mov     rcx, rbx
0x14001f8ee  mov     edi, eax
0x14001f8f0  call    VhdmpiReleasePassiveLockShared
0x14001f8f5  mov     r12, [rbp+10B0h+Str]
0x14001f8f9  xor     ebx, ebx
0x14001f8fb  test    edi, edi
0x14001f8fd  js      loc_14001FF8A
0x14001f903  lea     edx, [rbx+5Ch]; Ch
0x14001f906  mov     rcx, r12; Str
0x14001f909  call    cs:__imp_wcsrchr
0x14001f910  nop     dword ptr [rax+rax+00h]
0x14001f915  test    rax, rax
0x14001f918  jz      loc_14001FF85
0x14001f91e  lea     rdi, [rax+2]
0x14001f922  mov     rcx, rdi; Str
0x14001f925  lea     edx, [rbx+2Eh]; Ch
0x14001f928  call    cs:__imp_wcsrchr
0x14001f92f  nop     dword ptr [rax+rax+00h]
0x14001f934  mov     rbx, rax
0x14001f937  test    rax, rax
0x14001f93a  jz      loc_14001FF85
0x14001f940  lea     rdx, aAvhd; ".avhd"
0x14001f947  mov     rcx, rbx; Str1
0x14001f94a  call    cs:__imp__wcsicmp
0x14001f951  nop     dword ptr [rax+rax+00h]
0x14001f956  test    eax, eax
0x14001f958  jz      short loc_14001F97D
0x14001f95a  lea     rdx, aAvhdx; ".avhdx"
0x14001f961  mov     rcx, rbx; Str1
0x14001f964  call    cs:__imp__wcsicmp
0x14001f96b  nop     dword ptr [rax+rax+00h]
0x14001f970  test    eax, eax
0x14001f972  jz      short loc_14001F97D
0x14001f974  xor     eax, eax
0x14001f976  mov     [rbx], ax
0x14001f979  xor     ebx, ebx
0x14001f97b  jmp     short loc_14001F99E
0x14001f97d  xor     eax, eax
0x14001f97f  mov     rcx, rdi; Str
0x14001f982  mov     [rbx], ax
0x14001f985  lea     edx, [rax+5Fh]; Ch
0x14001f988  call    cs:__imp_wcsrchr
0x14001f98f  nop     dword ptr [rax+rax+00h]
0x14001f994  xor     ebx, ebx
0x14001f996  test    rax, rax
0x14001f999  jz      short loc_14001F99E
0x14001f99b  mov     [rax], bx
0x14001f99e  mov     rdx, rdi; SourceString
0x14001f9a1  lea     rcx, [rbp+10B0h+DestinationString]; DestinationString
0x14001f9a5  call    cs:__imp_RtlInitUnicodeString
0x14001f9ac  nop     dword ptr [rax+rax+00h]
0x14001f9b1  mov     rax, [rsp+11B0h+KeyHandle]
0x14001f9b6  lea     r8, [rbp+10B0h+ObjectAttributes]; ObjectAttributes
0x14001f9ba  mov     [rbp+10B0h+ObjectAttributes.RootDirectory], rax
0x14001f9be  lea     rcx, [rsp+11B0h+Handle]; KeyHandle
0x14001f9c3  lea     rax, [rbp+10B0h+DestinationString]
0x14001f9c7  mov     [rbp+10B0h+ObjectAttributes.Length], 30h ; '0'
0x14001f9ce  xorps   xmm0, xmm0
0x14001f9d1  mov     [rbp+10B0h+ObjectAttributes.ObjectName], rax
0x14001f9d5  mov     edx, 20019h; DesiredAccess
0x14001f9da  mov     [rbp+10B0h+ObjectAttributes.Attributes], 240h
0x14001f9e1  movdqu  xmmword ptr [rbp+10B0h+ObjectAttributes.SecurityDescriptor], xmm0
0x14001f9e6  call    cs:__imp_ZwOpenKey
0x14001f9ed  nop     dword ptr [rax+rax+00h]
0x14001f9f2  mov     edi, eax
0x14001f9f4  test    eax, eax
0x14001f9f6  jns     short loc_14001FA31
0x14001f9f8  mov     eax, cs:dword_140087708
0x14001f9fe  cmp     eax, 2
0x14001fa01  jbe     loc_14001FF8A
0x14001fa07  mov     edx, 1000h
0x14001fa0c  lea     rcx, dword_140087708
0x14001fa13  call    _tlgKeywordOn
0x14001fa18  test    al, al
0x14001fa1a  jz      loc_14001FF8A
0x14001fa20  mov     edx, 0E5Ch
0x14001fa25  lea     rax, aVhdmpictlogini_6; "VhdmpiCTLogInitVirtualDiskForTracing: f"...
0x14001fa2c  jmp     loc_14001F89D
0x14001fa31  lea     rdx, aCttraceflags; "CTTraceFlags"
0x14001fa38  lea     rcx, [rbp+10B0h+ValueName]; DestinationString
0x14001fa3c  call    cs:__imp_RtlInitUnicodeString
0x14001fa43  nop     dword ptr [rax+rax+00h]
0x14001fa48  mov     rcx, [rsp+11B0h+Handle]; KeyHandle
0x14001fa4d  lea     rax, [rsp+11B0h+var_1150]
0x14001fa52  mov     [rsp+11B0h+ResultLength], rax; char
0x14001fa57  lea     r9, [rbp+10B0h+KeyValueInformation]; KeyValueInformation
0x14001fa5e  mov     r8d, 2; KeyValueInformationClass
0x14001fa64  mov     [rsp+11B0h+Length], 10h; Length
0x14001fa6c  lea     rdx, [rbp+10B0h+ValueName]; ValueName
0x14001fa70  call    cs:__imp_ZwQueryValueKey
0x14001fa77  nop     dword ptr [rax+rax+00h]
0x14001fa7c  mov     edi, eax
0x14001fa7e  test    eax, eax
0x14001fa80  js      loc_14001FF2F
0x14001fa86  cmp     [rsp+11B0h+var_1150], 10h
0x14001fa8b  jnz     loc_14001FF2F
0x14001fa91  cmp     [rbp+10B0h+var_5C], 4
0x14001fa98  jnz     loc_14001FF2F
0x14001fa9e  cmp     [rbp+10B0h+var_58], 4
0x14001faa5  jnz     loc_14001FF2F
0x14001faab  mov     eax, [rbp+10B0h+var_54]
0x14001fab1  mov     [rsi+860h], eax
0x14001fab7  test    r15b, r15b
0x14001faba  jz      short loc_14001FB1C
0x14001fabc  mov     al, [rsi+860h]
0x14001fac2  test    al, al
0x14001fac4  js      short loc_14001FB1C
0x14001fac6  mov     eax, cs:dword_140087708
0x14001facc  cmp     eax, 2
0x14001facf  jbe     loc_14001FF85
0x14001fad5  mov     edx, 1000h
0x14001fada  lea     rcx, dword_140087708
0x14001fae1  call    _tlgKeywordOn
0x14001fae6  test    al, al
0x14001fae8  jz      loc_14001FF85
0x14001faee  lea     rax, aVhdmpictlogini_5; "VhdmpiCTLogInitVirtualDiskForTracing: r"...
0x14001faf5  mov     edx, 0E8Bh; int
0x14001fafa  mov     r9d, 1000h; int
0x14001fb00  mov     qword ptr [rsp+11B0h+Length], rax; char *
0x14001fb05  mov     r8d, 2; int
0x14001fb0b  lea     rcx, aVhdmpictlogini_3; "VhdmpiCTLogInitVirtualDiskForTracing"
0x14001fb12  call    TraceEvents
0x14001fb17  jmp     loc_14001FF85
0x14001fb1c  mov     eax, [rsi+860h]
0x14001fb22  test    al, al
0x14001fb24  jns     short loc_14001FB8A
0x14001fb26  test    al, 78h
0x14001fb28  jz      short loc_14001FB8A
0x14001fb2a  mov     eax, cs:dword_140087708
0x14001fb30  cmp     eax, 2
0x14001fb33  jbe     loc_14001FF85
0x14001fb39  mov     edx, 1000h
0x14001fb3e  lea     rcx, dword_140087708
0x14001fb45  call    _tlgKeywordOn
0x14001fb4a  test    al, al
0x14001fb4c  jz      loc_14001FF85
0x14001fb52  mov     eax, [rsi+860h]
0x14001fb58  lea     rcx, aVhdmpictlogini_3; "VhdmpiCTLogInitVirtualDiskForTracing"
0x14001fb5f  mov     dword ptr [rsp+11B0h+ResultLength], eax; char
0x14001fb63  mov     edx, 0EA0h; int
0x14001fb68  lea     rax, aVhdmpictlogini_1; "VhdmpiCTLogInitVirtualDiskForTracing: f"...
0x14001fb6f  mov     r9d, 1000h; int
0x14001fb75  mov     r8d, 2; int
0x14001fb7b  mov     qword ptr [rsp+11B0h+Length], rax; char *
0x14001fb80  call    TraceEvents
0x14001fb85  jmp     loc_14001FF85
0x14001fb8a  lea     rdx, aCttracefilepat; "CTTraceFilePath"
0x14001fb91  lea     rcx, [rbp+10B0h+ValueName]; DestinationString
0x14001fb95  call    cs:__imp_RtlInitUnicodeString
0x14001fb9c  nop     dword ptr [rax+rax+00h]
0x14001fba1  mov     rcx, [rsp+11B0h+Handle]; KeyHandle
0x14001fba6  lea     rax, [rsp+11B0h+var_1150]
0x14001fbab  xor     r9d, r9d; KeyValueInformation
0x14001fbae  mov     [rsp+11B0h+ResultLength], rax; ResultLength
0x14001fbb3  lea     rdx, [rbp+10B0h+ValueName]; ValueName
0x14001fbb7  mov     [rsp+11B0h+Length], ebx; Length
0x14001fbbb  lea     r8d, [r9+2]; KeyValueInformationClass
0x14001fbbf  call    cs:__imp_ZwQueryValueKey
0x14001fbc6  nop     dword ptr [rax+rax+00h]
0x14001fbcb  mov     r8d, eax
0x14001fbce  cmp     eax, 0C0000023h
0x14001fbd3  jz      short loc_14001FBE0
0x14001fbd5  cmp     eax, 80000005h
0x14001fbda  jnz     loc_14001FED2
0x14001fbe0  mov     edx, [rsp+11B0h+var_1150]
0x14001fbe4  mov     ecx, 100h
0x14001fbe9  add     rdx, 2
0x14001fbed  mov     r8d, 68444856h
0x14001fbf3  call    cs:__imp_ExAllocatePool2
0x14001fbfa  nop     dword ptr [rax+rax+00h]
0x14001fbff  mov     r14, rax
0x14001fc02  test    rax, rax
0x14001fc05  jnz     short loc_14001FC11
0x14001fc07  mov     edi, 0C000009Ah
0x14001fc0c  jmp     loc_14001FF8A
0x14001fc11  mov     rcx, [rsp+11B0h+Handle]; KeyHandle
0x14001fc16  lea     rax, [rsp+11B0h+var_1150]
0x14001fc1b  mov     [rsp+11B0h+ResultLength], rax; ResultLength
0x14001fc20  lea     rdx, [rbp+10B0h+ValueName]; ValueName
0x14001fc24  mov     eax, [rsp+11B0h+var_1150]
0x14001fc28  mov     r9, r14; KeyValueInformation
0x14001fc2b  mov     r8d, 2; KeyValueInformationClass
0x14001fc31  mov     [rsp+11B0h+Length], eax; Length
0x14001fc35  call    cs:__imp_ZwQueryValueKey
0x14001fc3c  nop     dword ptr [rax+rax+00h]
0x14001fc41  mov     r8d, eax
0x14001fc44  test    eax, eax
0x14001fc46  js      loc_14001FED2
0x14001fc4c  cmp     dword ptr [r14+4], 1
0x14001fc51  jnz     loc_14001FED2
0x14001fc57  mov     ecx, [r14+8]
0x14001fc5b  lea     rdx, [r14+0Ch]; SourceString
0x14001fc5f  shr     rcx, 1
0x14001fc62  mov     [r14+rcx*2+0Ch], bx
0x14001fc68  lea     rcx, [rbp+10B0h+var_10C8]; DestinationString
0x14001fc6c  call    cs:__imp_RtlInitUnicodeString
0x14001fc73  nop     dword ptr [rax+rax+00h]
0x14001fc78  lea     rdx, [rbp+10B0h+var_10B8]; struct _UNICODE_STRING *
0x14001fc7c  lea     rcx, [rbp+10B0h+var_10C8]; struct _UNICODE_STRING *
0x14001fc80  call    VhdmpiCreateNtFilePath
0x14001fc85  mov     edi, eax
  ... truncated ...
```
