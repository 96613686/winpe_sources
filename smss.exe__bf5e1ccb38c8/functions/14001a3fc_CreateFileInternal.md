# CreateFileInternal

- ea: `0x14001a3fc`
- end: `0x14001aba3`
- name: `CreateFileInternal`
- size: `1959`
- prototype: `__int64 __usercall@<rax>(PCWSTR SourceString@<rcx>, __int64, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x14001a39c`
- `0x14001abac`

## callees

- `0x14001a3fc`
- `0x14001ac04`
- `0x14001b33c`
- `0x14001b450`
- `0x14001b67c`
- `0x14001cabc`
- `0x14001cc40`
- `0x14001e010`

## import_xrefs

- `ntdll!NtClose` at `0x14001aa7f`
- `ntdll!NtClose` at `0x14001aacf`
- `ntdll!NtClose` at `0x14001aa7f`
- `ntdll!NtClose` at `0x14001aacf`
- `ntdll!RtlAllocateHeap` at `0x14001a72c`
- `ntdll!RtlAllocateHeap` at `0x14001a72c`
- `ntdll!RtlFreeHeap` at `0x14001a78f`
- `ntdll!RtlFreeHeap` at `0x14001aaf2`
- `ntdll!RtlFreeHeap` at `0x14001ab0f`
- `ntdll!RtlFreeHeap` at `0x14001a78f`
- `ntdll!RtlFreeHeap` at `0x14001aaf2`
- `ntdll!RtlFreeHeap` at `0x14001ab0f`
- `ntdll!RtlInitUnicodeStringEx` at `0x14001a53e`
- `ntdll!RtlInitUnicodeStringEx` at `0x14001a53e`
- `ntdll!NtSetInformationFile` at `0x14001aa74`
- `ntdll!NtSetInformationFile` at `0x14001aab1`
- `ntdll!NtSetInformationFile` at `0x14001aa74`
- `ntdll!NtSetInformationFile` at `0x14001aab1`
- `ntdll!NtQueryInformationFile` at `0x14001a6f8`
- `ntdll!NtQueryInformationFile` at `0x14001a6f8`
- `ntdll!NtCreateFile` at `0x14001a99e`
- `ntdll!NtCreateFile` at `0x14001aa08`
- `ntdll!NtCreateFile` at `0x14001a99e`
- `ntdll!NtCreateFile` at `0x14001aa08`
- `ntdll!RtlSetLastWin32Error` at `0x14001a4d4`
- `ntdll!RtlSetLastWin32Error` at `0x14001a5af`
- `ntdll!RtlSetLastWin32Error` at `0x14001aabf`
- `ntdll!RtlSetLastWin32Error` at `0x14001ab71`
- `ntdll!RtlSetLastWin32Error` at `0x14001a4d4`
- `ntdll!RtlSetLastWin32Error` at `0x14001a5af`
- `ntdll!RtlSetLastWin32Error` at `0x14001aabf`
- `ntdll!RtlSetLastWin32Error` at `0x14001ab71`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U_WithStatus` at `0x14001a590`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U_WithStatus` at `0x14001a590`
- `ntdll!RtlReleaseRelativeName` at `0x14001aad9`
- `ntdll!RtlReleaseRelativeName` at `0x14001aad9`
- `ntdll!SbSelectProcedure` at `0x14001a908`
- `ntdll!SbSelectProcedure` at `0x14001a908`
- `ntdll!NtQueryEaFile` at `0x14001a770`
- `ntdll!NtQueryEaFile` at `0x14001a770`

## pseudocode

```c
__int64 __fastcall CreateFileInternal(PCWSTR SourceString, int a2, ULONG a3, int a4, __int64 a5, char a6)
{
  ULONG EaLength; // r13d
  int v7; // r15d
  int v9; // esi
  unsigned int v10; // edi
  ULONG v12; // r12d
  NTSTATUS inited; // eax
  HANDLE ContainingDirectory; // rax
  int v15; // edx
  int v16; // esi
  unsigned int v17; // ecx
  __int64 v18; // rcx
  void *EaBuffer; // rsi
  char *v20; // rcx
  ULONG v21; // r14d
  PVOID Heap; // rax
  NTSTATUS v23; // r15d
  int IsEnabledDeviceUsageNoInline; // eax
  ULONG v25; // r8d
  ULONG v26; // r8d
  int v27; // r14d
  NTSTATUS v28; // ebx
  void (__fastcall *v29)(ULONG *); // rax
  int v30; // edi
  ACCESS_MASK v31; // r15d
  ULONG v32; // eax
  int v33; // eax
  ULONG v34; // ecx
  ULONG v35; // ecx
  bool v36; // [rsp+60h] [rbp-A0h]
  ULONG CreateOptions; // [rsp+64h] [rbp-9Ch] BYREF
  void *FileHandle; // [rsp+68h] [rbp-98h] BYREF
  ULONG FileAttributes; // [rsp+70h] [rbp-90h]
  int v40; // [rsp+74h] [rbp-8Ch] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+78h] [rbp-88h] BYREF
  ULONG FileInformation; // [rsp+88h] [rbp-78h] BYREF
  int v43; // [rsp+8Ch] [rbp-74h]
  ULONG ShareAccess; // [rsp+90h] [rbp-70h]
  int v45; // [rsp+94h] [rbp-6Ch]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+98h] [rbp-68h] BYREF
  int v47; // [rsp+A8h] [rbp-58h]
  __int64 v48; // [rsp+B0h] [rbp-50h] BYREF
  HANDLE Handle; // [rsp+B8h] [rbp-48h]
  _RTL_RELATIVE_NAME_U RelativeName; // [rsp+C0h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+E0h] [rbp-20h] BYREF
  PVOID BaseAddress; // [rsp+110h] [rbp+10h]
  __int64 v53; // [rsp+118h] [rbp+18h] BYREF
  int v54; // [rsp+120h] [rbp+20h]
  int v55; // [rsp+198h] [rbp+98h]

  EaLength = 0;
  v43 = a4;
  ShareAccess = a3;
  v47 = a2;
  CreateOptions = 0;
  v48 = 0;
  v7 = a2;
  FileInformation = 0;
  v53 = 0;
  v54 = 0;
  FileHandle = (void *)-1LL;
  Handle = (HANDLE)-1LL;
  memset(&ObjectAttributes, 0, 44);
  DestinationString = 0;
  IoStatusBlock = 0;
  memset(&RelativeName, 0, sizeof(RelativeName));
  if ( a5 )
  {
    if ( *(_DWORD *)a5 < 0x20u )
    {
LABEL_19:
      BaseSetLastNTError(3221225485LL);
      return -1;
    }
    v9 = *(_DWORD *)(a5 + 12);
    v10 = *(_DWORD *)(a5 + 8);
    FileAttributes = *(_DWORD *)(a5 + 4);
  }
  else
  {
    v9 = 0;
    FileAttributes = 0;
    v10 = 0;
  }
  if ( (a6 & 3) != 0 )
  {
    v36 = 0;
  }
  else
  {
    v36 = (v10 & 0x10000) != 0;
    if ( (v10 & 0x10000) != 0 )
    {
      if ( !a2 || (a3 & 4) != 0 )
      {
        RtlSetLastWin32Error(0xA0u);
        return -1;
      }
    }
    else
    {
      v36 = 0;
    }
  }
  if ( a4 == 1 )
  {
    v12 = 2;
  }
  else if ( a4 == 2 )
  {
    v12 = 5;
  }
  else
  {
    if ( a4 != 3 )
    {
      if ( a4 == 4 )
      {
        v12 = 3;
        goto LABEL_24;
      }
      if ( a4 != 5 || (a2 & 0x40000000) == 0 )
        goto LABEL_19;
    }
    v12 = 1;
  }
LABEL_24:
  inited = RtlInitUnicodeStringEx(&DestinationString, SourceString);
  if ( inited < 0 )
    goto LABEL_25;
  if ( DestinationString.Length <= 1u
    || (v45 = 1, SourceString[((unsigned __int64)DestinationString.Length >> 1) - 1] != 92) )
  {
    v45 = 0;
  }
  CreateOptions = 0;
  inited = RtlDosPathNameToRelativeNtPathName_U_WithStatus(SourceString, &DestinationString, 0, &RelativeName);
  if ( inited < 0 )
  {
    if ( inited != -1073741801 && inited != -1073741670 )
    {
      RtlSetLastWin32Error(3u);
      return -1;
    }
LABEL_25:
    BaseSetLastNTError((unsigned int)inited);
    return -1;
  }
  BaseAddress = DestinationString.Buffer;
  if ( RelativeName.RelativeName.Length )
  {
    DestinationString = RelativeName.RelativeName;
    ContainingDirectory = RelativeName.ContainingDirectory;
  }
  else
  {
    ContainingDirectory = 0;
    RelativeName.ContainingDirectory = 0;
  }
  ObjectAttributes.RootDirectory = ContainingDirectory;
  ObjectAttributes.Length = 48;
  v40 = v10 & 0x1000000;
  ObjectAttributes.SecurityDescriptor = 0;
  v15 = (v10 >> 6) & 0x800;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Attributes = v15 | ((v10 & 0x1000000) == 0 ? 0x40 : 0);
  if ( (v9 & 0x100000) != 0 )
  {
    v16 = v9 & 0xF0000;
    LOBYTE(v54) = (v16 & 0x40000) != 0;
    v17 = v16 & 0xFFFBFFFF;
    if ( (v16 & 0x40000) == 0 )
      v17 = v16;
    if ( (v17 & 0x80000) != 0 )
    {
      BYTE1(v54) = 1;
      v17 &= ~0x80000u;
    }
    else
    {
      BYTE1(v54) = 0;
    }
    HIDWORD(v53) = HIWORD(v17);
  }
  else
  {
    LOWORD(v54) = 257;
    HIDWORD(v53) = 2;
  }
  LODWORD(v53) = 12;
  ObjectAttributes.SecurityQualityOfService = &v53;
  if ( a5
    && (v18 = *(_QWORD *)(a5 + 16)) != 0
    && (ObjectAttributes.SecurityDescriptor = *(PVOID *)(v18 + 8), *(_DWORD *)(v18 + 16)) )
  {
    EaBuffer = 0;
    ObjectAttributes.Attributes = v15 | ((v10 & 0x1000000) != 0 ? 2 : 66);
  }
  else
  {
    EaBuffer = 0;
    if ( !a5 )
      goto LABEL_60;
  }
  v20 = *(char **)(a5 + 24);
  if ( (unsigned __int64)(v20 - 1) > 0xFFFFFFFFFFFFFFFDuLL
    || NtQueryInformationFile(v20, &IoStatusBlock, &FileInformation, 4u, FileEaInformation) < 0
    || (v21 = FileInformation) == 0 )
  {
LABEL_60:
    IsEnabledDeviceUsageNoInline = Feature_TimestampsOnCreate__private_IsEnabledDeviceUsageNoInline();
    v25 = CreateOptions;
    if ( IsEnabledDeviceUsageNoInline )
      v25 = ((v10 & 0x8000) << 14) | CreateOptions;
    v26 = ((v10 & 0x2000000) != 0 ? 0x4000 : 0)
        | ~(v10 >> 25) & 0x20
        | ((int)v10 >> 31) & 2
        | ((v10 & 0x40000
          | ((v10 & 0x800000 | ((v10 & 0x10000000 | ((v10 & 0x8000000 | (v10 >> 1) & 0x10000000) >> 8)) >> 12)) >> 3)) >> 2)
        | v25;
    CreateOptions = v26;
    if ( (HIWORD(KeGetPcr()->NtTib.Self[109].StackLimit) & 0x800) != 0 )
    {
      v26 |= 0x40000u;
      CreateOptions = v26;
    }
    v27 = v10 & 0x4000000;
    if ( (v10 & 0x4000000) != 0 )
    {
      v26 |= 0x1000u;
      CreateOptions = v26;
      v7 |= 0x10000u;
    }
    if ( (v10 & 0x200000) != 0 )
    {
      v26 |= 0x200000u;
      CreateOptions = v26;
    }
    if ( (v10 & 0x100000) != 0 )
    {
      v26 |= 0x400000u;
      CreateOptions = v26;
    }
    if ( (v10 & 0x2000000) != 0 )
    {
      if ( (FileAttributes & 0x10) == 0 || !v40 || v12 != 2 )
      {
LABEL_78:
        v55 = a6 & 2;
        if ( v55 )
        {
          CreateOptions = v26 | 0x20000;
        }
        else
        {
          v29 = (void (__fastcall *)(ULONG *))SbSelectProcedure(2880154539LL, 1, "kLsE");
          if ( v29 )
            v29(&CreateOptions);
        }
        v30 = v43;
        if ( v36 && ((v43 - 1) & 0xFFFFFFFC) == 0 && v43 != 3 )
        {
          v28 = BasepOpenParentDirectoryNoRedirection(&DestinationString);
          if ( v28 < 0 )
            goto LABEL_105;
        }
        v31 = v7 | 0x100080;
        FileAttributes &= 0xDAFFA7u;
        v28 = NtCreateFile(
                &FileHandle,
                v31,
                &ObjectAttributes,
                &IoStatusBlock,
                0,
                FileAttributes,
                ShareAccess,
                v12,
                CreateOptions,
                EaBuffer,
                EaLength);
        if ( v28 == -1073741790 )
        {
          if ( v55 )
            goto LABEL_92;
          v32 = CreateOptions;
          if ( (CreateOptions & 0x20000) == 0 || (ShareAccess & 1) != 0 )
            goto LABEL_92;
          CreateOptions &= ~0x20000u;
          v28 = NtCreateFile(
                  &FileHandle,
                  v31,
                  &ObjectAttributes,
                  &IoStatusBlock,
                  0,
                  FileAttributes,
                  ShareAccess,
                  v12,
                  v32 & 0xFFFDFFFF,
                  EaBuffer,
                  EaLength);
        }
        if ( v28 < 0 )
        {
LABEL_92:
          FileHandle = (void *)-1LL;
          goto LABEL_105;
        }
        if ( v36 )
        {
          v33 = (CreateOptions & 1) != 0
              ? BasepGetDirectoryRedirectionStatus(DestinationString.Buffer)
              : BasepGetFileRedirectionStatus(DestinationString.Buffer, FileHandle);
          v28 = v33;
          if ( v33 < 0 )
          {
            if ( v27 )
            {
              v40 = 8;
              NtSetInformationFile(FileHandle, &IoStatusBlock, &v40, 4u, (FILE_INFORMATION_CLASS)64);
            }
            goto LABEL_100;
          }
        }
        if ( v30 == 5 )
        {
          v48 = 0;
          v28 = NtSetInformationFile(FileHandle, &IoStatusBlock, &v48, 8u, FileAllocationInformation);
          if ( v28 < 0 )
          {
LABEL_100:
            NtClose(FileHandle);
            goto LABEL_92;
          }
        }
        else if ( v30 == 2 && IoStatusBlock.Information == 3 || v30 == 4 && IoStatusBlock.Information == 1 )
        {
          v34 = 183;
          goto LABEL_104;
        }
        v34 = 0;
LABEL_104:
        RtlSetLastWin32Error(v34);
LABEL_105:
        if ( Handle != (HANDLE)-1LL )
          NtClose(Handle);
        goto LABEL_107;
      }
      v26 |= 1u;
    }
    else
    {
      v26 |= 0x40u;
    }
    CreateOptions = v26;
    goto LABEL_78;
  }
  while ( 1 )
  {
    v21 *= 2;
    Heap = RtlAllocateHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), KernelBaseGlobalData, v21);
    EaBuffer = Heap;
    if ( !Heap )
      break;
    v23 = NtQueryEaFile(*(HANDLE *)(a5 + 24), &IoStatusBlock, Heap, v21, 0, 0, 0, 0, 1u);
    if ( v23 >= 0 )
    {
      EaLength = IoStatusBlock.Information;
    }
    else
    {
      RtlFreeHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, EaBuffer);
      EaBuffer = 0;
      EaLength = 0;
      IoStatusBlock.Information = 0;
    }
    if ( v23 != -2147483643 && v23 != -1073741789 )
    {
      v7 = v47;
      goto LABEL_60;
    }
  }
  v28 = -1073741801;
LABEL_107:
  RtlReleaseRelativeName(&RelativeName);
  RtlFreeHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, BaseAddress);
  if ( EaBuffer )
    RtlFreeHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, EaBuffer);
  if ( v28 >= 0 )
    return (__int64)FileHandle;
  BaseSetLastNTError((unsigned int)v28);
  if ( v28 == -1073741771 )
  {
    v35 = 80;
LABEL_120:
    RtlSetLastWin32Error(v35);
    return (__int64)FileHandle;
  }
  if ( v28 == -1073741638 )
  {
    v35 = 3;
    if ( !v45 )
      v35 = 5;
    goto LABEL_120;
  }
  return (__int64)FileHandle;
}

```

## disassembly

```asm
0x14001a3fc  mov     [rsp-8+arg_18], rbx
0x14001a401  push    rbp
0x14001a402  push    rsi
0x14001a403  push    rdi
0x14001a404  push    r12
0x14001a406  push    r13
0x14001a408  push    r14
0x14001a40a  push    r15
0x14001a40c  lea     rbp, [rsp-30h]
0x14001a411  sub     rsp, 130h
0x14001a418  mov     rax, cs:__security_cookie
0x14001a41f  xor     rax, rsp
0x14001a422  mov     [rbp+60h+var_38], rax
0x14001a426  mov     rbx, [rbp+60h+arg_20]
0x14001a42d  xorps   xmm0, xmm0
0x14001a430  xor     r13d, r13d
0x14001a433  mov     [rbp+60h+var_D4], r9d
0x14001a437  xor     eax, eax
0x14001a439  mov     [rbp+60h+ShareAccess], r8d
0x14001a43d  or      r12, 0FFFFFFFFFFFFFFFFh
0x14001a441  mov     [rbp+60h+var_B8], edx
0x14001a444  mov     [rsp+160h+CreateOptions], r13d
0x14001a449  xorps   xmm1, xmm1
0x14001a44c  mov     [rbp+60h+var_B0], r13
0x14001a450  mov     r15d, edx
0x14001a453  mov     [rbp+60h+FileInformation], r13d
0x14001a457  mov     r14, rcx
0x14001a45a  mov     [rbp+60h+var_48], rax
0x14001a45e  mov     [rbp+60h+var_40], eax
0x14001a461  mov     [rsp+160h+FileHandle], r12
0x14001a466  mov     [rbp+60h+Handle], r12
0x14001a46a  movups  xmmword ptr [rbp+60h+ObjectAttributes.ObjectName], xmm0
0x14001a46e  movups  xmmword ptr [rbp+60h+ObjectAttributes+1Ch], xmm0
0x14001a472  movups  xmmword ptr [rbp+60h+ObjectAttributes.Length], xmm0
0x14001a476  movups  xmmword ptr [rsp+160h+DestinationString.Length], xmm0
0x14001a47b  movups  xmmword ptr [rbp+60h+IoStatusBlock], xmm1
0x14001a47f  movups  xmmword ptr [rbp+60h+RelativeName.RelativeName.Length], xmm0
0x14001a483  movups  xmmword ptr [rbp+60h+RelativeName.ContainingDirectory], xmm0
0x14001a487  test    rbx, rbx
0x14001a48a  jz      short loc_14001A4A0
0x14001a48c  cmp     dword ptr [rbx], 20h ; ' '
0x14001a48f  jb      short loc_14001A50F
0x14001a491  mov     eax, [rbx+4]
0x14001a494  mov     esi, [rbx+0Ch]
0x14001a497  mov     edi, [rbx+8]
0x14001a49a  mov     [rsp+160h+FileAttributes], eax
0x14001a49e  jmp     short loc_14001A4AB
0x14001a4a0  mov     esi, r13d
0x14001a4a3  mov     [rsp+160h+FileAttributes], r13d
0x14001a4a8  mov     edi, r13d
0x14001a4ab  test    byte ptr [rbp+60h+arg_28], 3
0x14001a4b2  jnz     short loc_14001A4E8
0x14001a4b4  bt      edi, 10h
0x14001a4b8  setb    cl
0x14001a4bb  mov     [rsp+160h+var_100], cl
0x14001a4bf  bt      edi, 10h
0x14001a4c3  jnb     short loc_14001A4E2
0x14001a4c5  test    edx, edx
0x14001a4c7  jz      short loc_14001A4CF
0x14001a4c9  test    r8b, 4
0x14001a4cd  jz      short loc_14001A4ED
0x14001a4cf  mov     ecx, 0A0h; LastError
0x14001a4d4  call    cs:__imp_RtlSetLastWin32Error
0x14001a4da  mov     rax, r12
0x14001a4dd  jmp     loc_14001AB7C
0x14001a4e2  mov     [rsp+160h+var_100], cl
0x14001a4e6  jmp     short loc_14001A4ED
0x14001a4e8  mov     [rsp+160h+var_100], r13b
0x14001a4ed  mov     eax, r9d
0x14001a4f0  mov     ecx, 1
0x14001a4f5  sub     eax, ecx
0x14001a4f7  jz      short loc_14001A530
0x14001a4f9  sub     eax, ecx
0x14001a4fb  jz      short loc_14001A528
0x14001a4fd  sub     eax, ecx
0x14001a4ff  jz      short loc_14001A523
0x14001a501  sub     eax, ecx
0x14001a503  jz      short loc_14001A51B
0x14001a505  cmp     eax, ecx
0x14001a507  jnz     short loc_14001A50F
0x14001a509  bt      edx, 1Eh
0x14001a50d  jb      short loc_14001A523
0x14001a50f  mov     ecx, 0C000000Dh
0x14001a514  call    BaseSetLastNTError
0x14001a519  jmp     short loc_14001A4DA
0x14001a51b  mov     r12d, 3
0x14001a521  jmp     short loc_14001A536
0x14001a523  mov     r12d, ecx
0x14001a526  jmp     short loc_14001A536
0x14001a528  mov     r12d, 5
0x14001a52e  jmp     short loc_14001A536
0x14001a530  mov     r12d, 2
0x14001a536  mov     rdx, r14; SourceString
0x14001a539  lea     rcx, [rsp+160h+DestinationString]; DestinationString
0x14001a53e  call    cs:__imp_RtlInitUnicodeStringEx
0x14001a544  test    eax, eax
0x14001a546  jns     short loc_14001A558
0x14001a548  mov     ecx, eax
0x14001a54a  call    BaseSetLastNTError
0x14001a54f  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001a553  jmp     loc_14001AB7C
0x14001a558  mov     ecx, 1
0x14001a55d  cmp     [rsp+160h+DestinationString.Length], cx
0x14001a562  jbe     short loc_14001A578
0x14001a564  movzx   eax, [rsp+160h+DestinationString.Length]
0x14001a569  shr     rax, 1
0x14001a56c  mov     [rbp+60h+var_CC], ecx
0x14001a56f  cmp     word ptr [r14+rax*2-2], 5Ch ; '\'
0x14001a576  jz      short loc_14001A57C
0x14001a578  mov     [rbp+60h+var_CC], r13d
0x14001a57c  lea     r9, [rbp+60h+RelativeName]
0x14001a580  mov     [rsp+160h+CreateOptions], r13d
0x14001a585  xor     r8d, r8d
0x14001a588  lea     rdx, [rsp+160h+DestinationString]
0x14001a58d  mov     rcx, r14
0x14001a590  call    cs:__imp_RtlDosPathNameToRelativeNtPathName_U_WithStatus
0x14001a596  test    eax, eax
0x14001a598  jns     short loc_14001A5B7
0x14001a59a  mov     ebx, 0C0000017h
0x14001a59f  cmp     eax, ebx
0x14001a5a1  jz      short loc_14001A548
0x14001a5a3  cmp     eax, 0C000009Ah
0x14001a5a8  jz      short loc_14001A548
0x14001a5aa  mov     ecx, 3; LastError
0x14001a5af  call    cs:__imp_RtlSetLastWin32Error
0x14001a5b5  jmp     short loc_14001A54F
0x14001a5b7  mov     rax, [rbp+60h+DestinationString.Buffer]
0x14001a5bb  mov     [rbp+60h+BaseAddress], rax
0x14001a5bf  movzx   eax, [rbp+60h+RelativeName.RelativeName.Length]
0x14001a5c3  test    ax, ax
0x14001a5c6  jz      short loc_14001A5EB
0x14001a5c8  mov     [rsp+160h+DestinationString.Length], ax
0x14001a5cd  mov     eax, dword ptr [rbp+60h+RelativeName.RelativeName.MaximumLength]
0x14001a5d0  mov     dword ptr [rsp+160h+DestinationString.MaximumLength], eax
0x14001a5d4  movzx   eax, word ptr [rbp+60h+RelativeName.RelativeName+6]
0x14001a5d8  mov     word ptr [rsp+160h+DestinationString+6], ax
0x14001a5dd  mov     rax, [rbp+60h+RelativeName.RelativeName.Buffer]
0x14001a5e1  mov     [rbp+60h+DestinationString.Buffer], rax
0x14001a5e5  mov     rax, [rbp+60h+RelativeName.ContainingDirectory]
0x14001a5e9  jmp     short loc_14001A5F2
0x14001a5eb  mov     rax, r13
0x14001a5ee  mov     [rbp+60h+RelativeName.ContainingDirectory], rax
0x14001a5f2  mov     [rbp+60h+ObjectAttributes.RootDirectory], rax
0x14001a5f6  mov     r8d, edi
0x14001a5f9  and     r8d, 1000000h
0x14001a600  mov     [rbp+60h+ObjectAttributes.Length], 30h ; '0'
0x14001a607  mov     eax, r8d
0x14001a60a  mov     [rsp+160h+var_EC], r8d
0x14001a60f  mov     edx, edi
0x14001a611  mov     [rbp+60h+ObjectAttributes.SecurityDescriptor], r13
0x14001a615  shr     edx, 6
0x14001a618  mov     r14d, 800h
0x14001a61e  and     edx, r14d
0x14001a621  neg     eax
0x14001a623  lea     rax, [rsp+160h+DestinationString]
0x14001a628  sbb     ecx, ecx
0x14001a62a  mov     [rbp+60h+ObjectAttributes.ObjectName], rax
0x14001a62e  not     ecx
0x14001a630  and     ecx, 40h
0x14001a633  or      ecx, edx
0x14001a635  mov     [rbp+60h+ObjectAttributes.Attributes], ecx
0x14001a638  bt      esi, 14h
0x14001a63c  jnb     short loc_14001A675
0x14001a63e  and     esi, 0F0000h
0x14001a644  bt      esi, 12h
0x14001a648  mov     ecx, esi
0x14001a64a  setb    byte ptr [rbp+60h+var_40]
0x14001a64e  btr     ecx, 12h
0x14001a652  bt      esi, 12h
0x14001a656  cmovnb  ecx, esi
0x14001a659  bt      ecx, 13h
0x14001a65d  jnb     short loc_14001A669
0x14001a65f  mov     byte ptr [rbp+60h+var_40+1], 1
0x14001a663  btr     ecx, 13h
0x14001a667  jmp     short loc_14001A66D
0x14001a669  mov     byte ptr [rbp+60h+var_40+1], r13b
0x14001a66d  shr     ecx, 10h
0x14001a670  mov     dword ptr [rbp+60h+var_48+4], ecx
0x14001a673  jmp     short loc_14001A682
0x14001a675  mov     word ptr [rbp+60h+var_40], 101h
0x14001a67b  mov     dword ptr [rbp+60h+var_48+4], 2
0x14001a682  mov     dword ptr [rbp+60h+var_48], 0Ch
0x14001a689  lea     rax, [rbp+60h+var_48]
0x14001a68d  mov     [rbp+60h+ObjectAttributes.SecurityQualityOfService], rax
0x14001a691  test    rbx, rbx
0x14001a694  jz      short loc_14001A6C4
0x14001a696  mov     rcx, [rbx+10h]
0x14001a69a  test    rcx, rcx
0x14001a69d  jz      short loc_14001A6C4
0x14001a69f  mov     rax, [rcx+8]
0x14001a6a3  mov     [rbp+60h+ObjectAttributes.SecurityDescriptor], rax
0x14001a6a7  cmp     [rcx+10h], r13d
0x14001a6ab  jz      short loc_14001A6C4
0x14001a6ad  mov     eax, r8d
0x14001a6b0  mov     rsi, r13
0x14001a6b3  neg     eax
0x14001a6b5  sbb     ecx, ecx
0x14001a6b7  and     ecx, 0FFFFFFC0h
0x14001a6ba  add     ecx, 42h ; 'B'
0x14001a6bd  or      ecx, edx
0x14001a6bf  mov     [rbp+60h+ObjectAttributes.Attributes], ecx
0x14001a6c2  jmp     short loc_14001A6D0
0x14001a6c4  mov     rsi, r13
0x14001a6c7  test    rbx, rbx
0x14001a6ca  jz      loc_14001A7C8
0x14001a6d0  mov     rcx, [rbx+18h]; FileHandle
0x14001a6d4  lea     rax, [rcx-1]
0x14001a6d8  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14001a6dc  ja      loc_14001A7C8
0x14001a6e2  mov     r9d, 4; Length
0x14001a6e8  mov     [rsp+160h+FileInformationClass], 7; FileInformationClass
0x14001a6f0  lea     r8, [rbp+60h+FileInformation]; FileInformation
0x14001a6f4  lea     rdx, [rbp+60h+IoStatusBlock]; IoStatusBlock
0x14001a6f8  call    cs:__imp_NtQueryInformationFile
0x14001a6fe  test    eax, eax
0x14001a700  js      loc_14001A7C8
0x14001a706  mov     r14d, [rbp+60h+FileInformation]
0x14001a70a  test    r14d, r14d
0x14001a70d  jz      loc_14001A7C2
0x14001a713  mov     rcx, gs:60h
0x14001a71c  add     r14d, r14d
0x14001a71f  mov     edx, cs:KernelBaseGlobalData; Flags
0x14001a725  mov     r8d, r14d; Size
0x14001a728  mov     rcx, [rcx+30h]; HeapHandle
0x14001a72c  call    cs:__imp_RtlAllocateHeap
0x14001a732  mov     rsi, rax
0x14001a735  test    rax, rax
0x14001a738  jz      loc_14001A8B6
0x14001a73e  mov     rcx, [rbx+18h]; FileHandle
0x14001a742  lea     rdx, [rbp+60h+IoStatusBlock]; IoStatusBlock
0x14001a746  mov     [rsp+160h+RestartScan], 1; RestartScan
0x14001a74b  mov     r9d, r14d; Length
0x14001a74e  mov     [rsp+160h+EaIndex], 0; EaIndex
0x14001a757  mov     r8, rax; Buffer
0x14001a75a  mov     [rsp+160h+EaListLength], 0; EaListLength
0x14001a762  mov     [rsp+160h+EaList], 0; EaList
0x14001a76b  mov     byte ptr [rsp+160h+FileInformationClass], 0; ReturnSingleEntry
0x14001a770  call    cs:__imp_NtQueryEaFile
0x14001a776  mov     r15d, eax
0x14001a779  test    eax, eax
0x14001a77b  jns     short loc_14001A7A0
0x14001a77d  mov     rcx, gs:60h
0x14001a786  mov     r8, rsi; BaseAddress
0x14001a789  xor     edx, edx; Flags
0x14001a78b  mov     rcx, [rcx+30h]; HeapHandle
0x14001a78f  call    cs:__imp_RtlFreeHeap
0x14001a795  xor     esi, esi
0x14001a797  xor     r13d, r13d
0x14001a79a  mov     [rbp+60h+IoStatusBlock.Information], r13
0x14001a79e  jmp     short loc_14001A7A4
0x14001a7a0  mov     r13, [rbp+60h+IoStatusBlock.Information]
0x14001a7a4  cmp     r15d, 80000005h
0x14001a7ab  jz      loc_14001A713
0x14001a7b1  cmp     r15d, 0C0000023h
0x14001a7b8  jz      loc_14001A713
0x14001a7be  mov     r15d, [rbp+60h+var_B8]
0x14001a7c2  mov     r14d, 800h
0x14001a7c8  call    Feature_TimestampsOnCreate__private_IsEnabledDeviceUsageNoInline
0x14001a7cd  mov     r8d, [rsp+160h+CreateOptions]
0x14001a7d2  test    eax, eax
0x14001a7d4  jz      short loc_14001A7E3
0x14001a7d6  mov     eax, edi
0x14001a7d8  and     eax, 8000h
0x14001a7dd  shl     eax, 0Eh
0x14001a7e0  or      r8d, eax
0x14001a7e3  mov     ecx, 10000000h
0x14001a7e8  mov     eax, edi
0x14001a7ea  and     eax, 8000000h
0x14001a7ef  mov     edx, edi
0x14001a7f1  shr     edx, 1
0x14001a7f3  mov     r9d, edi
0x14001a7f6  and     edx, ecx
0x14001a7f8  and     r9d, 2000000h
0x14001a7ff  or      edx, eax
0x14001a801  mov     eax, edi
0x14001a803  and     eax, ecx
0x14001a805  shr     edx, 8
0x14001a808  or      edx, eax
0x14001a80a  mov     eax, edi
0x14001a80c  and     eax, 800000h
0x14001a811  shr     edx, 0Ch
0x14001a814  or      edx, eax
0x14001a816  mov     eax, edi
0x14001a818  and     eax, 40000h
0x14001a81d  shr     edx, 3
0x14001a820  or      edx, eax
0x14001a822  mov     eax, edi
0x14001a824  sar     eax, 1Fh
0x14001a827  and     eax, 2
0x14001a82a  shr     edx, 2
0x14001a82d  or      edx, eax
0x14001a82f  mov     eax, edi
0x14001a831  shr     eax, 19h
0x14001a834  not     eax
0x14001a836  and     eax, 20h
0x14001a839  or      edx, eax
0x14001a83b  mov     eax, r9d
0x14001a83e  neg     eax
0x14001a840  sbb     ecx, ecx
0x14001a842  and     ecx, 4000h
  ... truncated ...
```
