# SclpMigrateHive

- ea: `0x18000c73c`
- end: `0x18000d0d9`
- name: `SclpMigrateHive`
- size: `2461`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, const WCHAR *, void *, __int64, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000b90c`

## callees

- `0x180001c74`
- `0x180001d48`
- `0x180007fb0`
- `0x180008be0`
- `0x180009374`
- `0x180009904`
- `0x18000a524`
- `0x18000c73c`
- `0x1800179e0`

## import_xrefs

- `ntdll!NtSetSecurityObject` at `0x18000cb5f`
- `ntdll!NtSetSecurityObject` at `0x18000cb5f`
- `ntdll!NtClose` at `0x18000cb93`
- `ntdll!NtClose` at `0x18000cc73`
- `ntdll!NtClose` at `0x18000ce69`
- `ntdll!NtClose` at `0x18000cee7`
- `ntdll!NtClose` at `0x18000d06d`
- `ntdll!NtClose` at `0x18000d07d`
- `ntdll!NtClose` at `0x18000d08d`
- `ntdll!NtClose` at `0x18000d09c`
- `ntdll!NtClose` at `0x18000cb93`
- `ntdll!NtClose` at `0x18000cc73`
- `ntdll!NtClose` at `0x18000ce69`
- `ntdll!NtClose` at `0x18000cee7`
- `ntdll!NtClose` at `0x18000d06d`
- `ntdll!NtClose` at `0x18000d07d`
- `ntdll!NtClose` at `0x18000d08d`
- `ntdll!NtClose` at `0x18000d09c`
- `ntdll!NtOpenKey` at `0x18000ca73`
- `ntdll!NtOpenKey` at `0x18000cade`
- `ntdll!NtOpenKey` at `0x18000cbd0`
- `ntdll!NtOpenKey` at `0x18000cea6`
- `ntdll!NtOpenKey` at `0x18000ca73`
- `ntdll!NtOpenKey` at `0x18000cade`
- `ntdll!NtOpenKey` at `0x18000cbd0`
- `ntdll!NtOpenKey` at `0x18000cea6`
- `ntdll!NtFlushKey` at `0x18000d019`
- `ntdll!NtFlushKey` at `0x18000d019`
- `ntdll!NtSaveKeyEx` at `0x18000cd23`
- `ntdll!NtSaveKeyEx` at `0x18000cd23`
- `ntdll!NtCreateFile` at `0x18000ccd9`
- `ntdll!NtCreateFile` at `0x18000cf65`
- `ntdll!NtCreateFile` at `0x18000ccd9`
- `ntdll!NtCreateFile` at `0x18000cf65`
- `ntdll!NtRestoreKey` at `0x18000cfd5`
- `ntdll!NtRestoreKey` at `0x18000cfd5`

## string_xrefs

- `0x18000c8cf`: `\REGISTRY\MACHINE`
- `0x18000c7d1`: `WINDOWS.OLD\WINDOWS\System32\config`
- `0x18000c85a`: `(%lx): Failed to calculate Windows.old's hive path for [%ws]`
- `0x18000c99b`: `(%lx): Failed to calculate excluded hive path`
- `0x18000ca9e`: `(%lx): Error opening old hive key [%ws]`
- `0x18000cb10`: `(%lx): Error opening current hive key [%ws]`
- `0x18000cc0d`: `Error opening excluded key [%ws]: [0x%08X]`
- `0x18000cd07`: `(%lx): Error opening excluded hive file [%ws]`
- `0x18000cd7a`: `(%lx): Error setting default security info to [%ws]`
- `0x18000cdbf`: `(%lx): Error copying security info from [%ws] to [%ws]`
- `0x18000ce1f`: `(%lx): Error copying hive content from [%ws] to [%ws]`
- `0x18000ced1`: `(%lx): Error re-opening excluded key [%ws]`
- `0x18000cf93`: `(%lx): Error re-opening excluded hive file [%ws]`
- `0x18000d02f`: `Successfully restored (by recursive copy) hive content for [%ws]`

## pseudocode

```c
__int64 __fastcall SclpMigrateHive(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const WCHAR *a4,
        void *a5,
        __int64 a6,
        __int64 a7)
{
  const WCHAR *v11; // rsi
  bool v12; // r15
  int v13; // eax
  NTSTATUS CanonicalMountKeyPath; // ebx
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  int v18; // eax
  __int64 v19; // rcx
  int v20; // eax
  __int64 v21; // rcx
  int UnloadHive; // eax
  __int64 v23; // rcx
  bool v24; // r12
  NTSTATUS v25; // eax
  __int64 v26; // rcx
  __int64 v27; // rcx
  __int64 v28; // rcx
  NTSTATUS v29; // eax
  __int64 v30; // rcx
  __int64 v31; // rcx
  int v32; // r9d
  char *v33; // rax
  __int64 v34; // rcx
  int v35; // r9d
  char *v36; // rax
  NTSTATUS v37; // eax
  __int64 v38; // rcx
  __int64 v39; // rcx
  ULONG ShareAccess[2]; // [rsp+30h] [rbp-D0h]
  ULONG CreateDisposition[2]; // [rsp+38h] [rbp-C8h]
  wchar_t *CreateDispositiona; // [rsp+38h] [rbp-C8h]
  ULONG CreateDispositionb[2]; // [rsp+38h] [rbp-C8h]
  wchar_t *CreateOptions; // [rsp+40h] [rbp-C0h]
  HANDLE FileHandle; // [rsp+60h] [rbp-A0h] BYREF
  HANDLE v47; // [rsp+68h] [rbp-98h] BYREF
  HANDLE Handle; // [rsp+70h] [rbp-90h] BYREF
  const WCHAR *v49; // [rsp+78h] [rbp-88h] BYREF
  void *KeyHandle; // [rsp+80h] [rbp-80h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+88h] [rbp-78h]
  __int64 v52; // [rsp+90h] [rbp-70h]
  __int64 v53; // [rsp+98h] [rbp-68h]
  struct _UNICODE_STRING v54; // [rsp+A0h] [rbp-60h] BYREF
  struct _UNICODE_STRING v55; // [rsp+B0h] [rbp-50h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+C0h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES v57; // [rsp+D0h] [rbp-30h] BYREF
  struct _OBJECT_ATTRIBUTES v58; // [rsp+100h] [rbp+0h] BYREF
  struct _UNICODE_STRING v59; // [rsp+130h] [rbp+30h] BYREF
  struct _UNICODE_STRING v60; // [rsp+140h] [rbp+40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+150h] [rbp+50h] BYREF
  struct _OBJECT_ATTRIBUTES v62; // [rsp+180h] [rbp+80h] BYREF
  wchar_t v63[264]; // [rsp+1B0h] [rbp+B0h] BYREF
  wchar_t v64[264]; // [rsp+3C0h] [rbp+2C0h] BYREF
  wchar_t v65[264]; // [rsp+5D0h] [rbp+4D0h] BYREF

  SecurityDescriptor = a5;
  v53 = a6;
  v52 = a7;
  v49 = 0;
  v11 = 0;
  KeyHandle = 0;
  Handle = 0;
  v47 = 0;
  FileHandle = 0;
  v12 = a4 != 0;
  memset(&ObjectAttributes, 0, 44);
  memset(&v62, 0, 44);
  memset(&v57, 0, 44);
  memset(&v58, 0, 44);
  v59 = 0;
  v60 = 0;
  v54 = 0;
  v55 = 0;
  IoStatusBlock = 0;
  v13 = RtlStringCchPrintfW(v65, 0x104u, L"%ws%ws\\%ws", a2, L"WINDOWS.OLD\\WINDOWS\\System32\\config", a3);
  CanonicalMountKeyPath = v13;
  if ( v13 >= 0 )
  {
    CanonicalMountKeyPath = SclRegGetCanonicalMountKeyPath(v65, &v49);
    if ( CanonicalMountKeyPath >= 0 )
    {
      v18 = RtlStringCchPrintfW(v63, 0x104u, L"%ws\\%ws", L"\\REGISTRY\\MACHINE", a3);
      CanonicalMountKeyPath = v18;
      if ( v18 < 0 )
      {
        if ( a1 )
          v19 = a1 + 1152;
        else
          v19 = 0;
        SclLogGenericMessage(
          v19,
          3,
          (int)SclEvent_Generic_Error,
          2488,
          (__int64)"SclpMigrateHive",
          "(%lx): Failed to calculate full key for the new hive [%ws]",
          v18,
          a3);
      }
    }
    else
    {
      if ( a1 )
        v17 = a1 + 1152;
      else
        v17 = 0;
      SclLogGenericMessage(
        v17,
        3,
        (int)SclEvent_Generic_Error,
        2476,
        (__int64)"SclpMigrateHive",
        "(%lx): Failed to calculate load key for the old hive [%ws]",
        CanonicalMountKeyPath,
        v65);
    }
    v11 = v49;
  }
  else
  {
    v15 = a1 + 1152;
    if ( !a1 )
      v15 = 0;
    SclLogGenericMessage(
      v15,
      3,
      (int)SclEvent_Generic_Error,
      2467,
      (__int64)"SclpMigrateHive",
      "(%lx): Failed to calculate Windows.old's hive path for [%ws]",
      v13,
      a3);
  }
  if ( a4 )
  {
    if ( CanonicalMountKeyPath < 0 )
      goto LABEL_29;
    v20 = RtlStringCchPrintfW(v64, 0x104u, L"%ws%ws", a2, L"WINDOWS\\Panther\\Excluded.hiv");
    CanonicalMountKeyPath = v20;
    if ( v20 < 0 )
    {
      if ( a1 )
        v21 = a1 + 1152;
      else
        v21 = 0;
      SclLogGenericMessage(
        v21,
        3,
        (int)SclEvent_Generic_Error,
        2501,
        (__int64)"SclpMigrateHive",
        "(%lx): Failed to calculate excluded hive path",
        v20);
      goto LABEL_29;
    }
  }
  else if ( CanonicalMountKeyPath < 0 )
  {
    goto LABEL_29;
  }
  LOBYTE(v16) = 1;
  UnloadHive = SclRegLoadUnloadHive(v16, v11, v65);
  CanonicalMountKeyPath = UnloadHive;
  if ( UnloadHive < 0 )
  {
    if ( a1 )
      v23 = a1 + 1152;
    else
      v23 = 0;
    ShareAccess[0] = UnloadHive;
    SclLogGenericMessage(
      v23,
      3,
      (int)SclEvent_Generic_Error,
      2513,
      (__int64)"SclpMigrateHive",
      "(%lx): Error loading old hive [%ws] into [%ws]",
      *(_QWORD *)ShareAccess,
      v65,
      v11);
  }
LABEL_29:
  v24 = CanonicalMountKeyPath >= 0;
  if ( CanonicalMountKeyPath < 0 )
    goto LABEL_106;
  INIT_OBJA_EX((__int64)&ObjectAttributes, &v59, v11, 64, 0);
  v25 = NtOpenKey(&KeyHandle, 0x1020019u, &ObjectAttributes);
  CanonicalMountKeyPath = v25;
  if ( v25 < 0 )
  {
    if ( a1 )
      v26 = a1 + 1152;
    else
      v26 = 0;
    ShareAccess[0] = v25;
    SclLogGenericMessage(
      v26,
      3,
      (int)SclEvent_Generic_Error,
      2527,
      (__int64)"SclpMigrateHive",
      "(%lx): Error opening old hive key [%ws]",
      *(_QWORD *)ShareAccess,
      v11);
    goto LABEL_40;
  }
  INIT_OBJA_EX((__int64)&v62, &v60, v63, 64, 0);
  CanonicalMountKeyPath = NtOpenKey(&Handle, 0x10F003Fu, &v62);
  if ( CanonicalMountKeyPath < 0 )
  {
    if ( a1 )
      v27 = a1 + 1152;
    else
      v27 = 0;
    ShareAccess[0] = CanonicalMountKeyPath;
    SclLogGenericMessage(
      v27,
      3,
      (int)SclEvent_Generic_Error,
      2542,
      (__int64)"SclpMigrateHive",
      "(%lx): Error opening current hive key [%ws]",
      *(_QWORD *)ShareAccess,
      v63);
LABEL_40:
    if ( CanonicalMountKeyPath < 0 )
      goto LABEL_106;
    goto LABEL_41;
  }
  if ( a4 )
  {
    INIT_OBJA_EX((__int64)&v57, &v54, a4, 64, (__int64)Handle);
    v29 = NtOpenKey(&v47, 0xF003Fu, &v57);
    CanonicalMountKeyPath = v29;
    if ( v29 >= 0 )
    {
      INIT_OBJA_EX((__int64)&v58, &v55, v64, 64, 0);
      CanonicalMountKeyPath = NtCreateFile(&FileHandle, 0x120116u, &v58, &IoStatusBlock, 0, 0x80u, 0, 5u, 0x60u, 0, 0);
      if ( CanonicalMountKeyPath < 0 )
      {
        if ( a1 )
          v28 = a1 + 1152;
        else
          v28 = 0;
        v32 = 2608;
        CreateDispositiona = v64;
        v33 = "(%lx): Error opening excluded hive file [%ws]";
        goto LABEL_96;
      }
      CanonicalMountKeyPath = NtSaveKeyEx(v47, FileHandle, 1u);
      if ( CanonicalMountKeyPath < 0 )
      {
        if ( a1 )
          v34 = a1 + 1152;
        else
          v34 = 0;
        v35 = 2619;
        CreateOptions = v64;
        v36 = "(%lx): Error saving excluded key [%ws] to hive file [%ws]";
        *(_QWORD *)CreateDispositionb = a4;
        goto LABEL_80;
      }
      goto LABEL_41;
    }
    if ( v29 != -1073741275 && v29 != -1073741772 )
    {
      if ( a1 )
        v30 = a1 + 1152;
      else
        v30 = 0;
      CreateDisposition[0] = v29;
      SclLogGenericMessage(
        v30,
        3,
        (int)SclEvent_Generic_Error,
        2579,
        (__int64)"SclpMigrateHive",
        "Error opening excluded key [%ws]: [0x%08X]",
        a4,
        *(_QWORD *)CreateDisposition);
      goto LABEL_106;
    }
    if ( a1 )
      v31 = a1 + 1152;
    else
      v31 = 0;
    SclLogGenericMessage(
      v31,
      1,
      (int)SclEvent_Generic_Info,
      2570,
      (__int64)"SclpMigrateHive",
      "Excluded key not found: [%ws]",
      a4);
    v12 = 0;
    CanonicalMountKeyPath = 0;
    goto LABEL_40;
  }
LABEL_41:
  if ( SecurityDescriptor )
  {
    CanonicalMountKeyPath = NtSetSecurityObject(Handle, 4u, SecurityDescriptor);
    if ( CanonicalMountKeyPath < 0 )
    {
      if ( a1 )
        v28 = a1 + 1152;
      else
        v28 = 0;
      v32 = 2633;
      CreateDispositiona = v63;
      v33 = "(%lx): Error setting default security info to [%ws]";
LABEL_96:
      ShareAccess[0] = CanonicalMountKeyPath;
      SclLogGenericMessage(
        v28,
        3,
        (int)SclEvent_Generic_Error,
        v32,
        (__int64)"SclpMigrateHive",
        v33,
        *(_QWORD *)ShareAccess,
        CreateDispositiona);
      goto LABEL_106;
    }
  }
  else
  {
    CanonicalMountKeyPath = SclRegCopySecurityInfo(a1, KeyHandle, Handle);
    if ( CanonicalMountKeyPath < 0 )
    {
      if ( a1 )
        v34 = a1 + 1152;
      else
        v34 = 0;
      v35 = 2644;
      CreateOptions = v63;
      v36 = "(%lx): Error copying security info from [%ws] to [%ws]";
      goto LABEL_79;
    }
  }
  CanonicalMountKeyPath = SclRegCopyKeyRecursiveByHandle(
                            a1,
                            (_DWORD)Handle,
                            (_DWORD)KeyHandle,
                            (unsigned int)v63,
                            (__int64)v11,
                            v53,
                            v52);
  if ( CanonicalMountKeyPath < 0 )
  {
    if ( a1 )
      v34 = a1 + 1152;
    else
      v34 = 0;
    v35 = 2660;
    CreateOptions = v63;
    v36 = "(%lx): Error copying hive content from [%ws] to [%ws]";
LABEL_79:
    *(_QWORD *)CreateDispositionb = v11;
LABEL_80:
    ShareAccess[0] = CanonicalMountKeyPath;
    SclLogGenericMessage(
      v34,
      3,
      (int)SclEvent_Generic_Error,
      v35,
      (__int64)"SclpMigrateHive",
      v36,
      *(_QWORD *)ShareAccess,
      *(_QWORD *)CreateDispositionb,
      CreateOptions);
    goto LABEL_106;
  }
  if ( v12 )
  {
    if ( v47 )
    {
      NtClose(v47);
      v47 = 0;
    }
    INIT_OBJA_EX((__int64)&v57, &v54, a4, 64, (__int64)Handle);
    v37 = NtOpenKey(&v47, 0xF003Fu, &v57);
    CanonicalMountKeyPath = v37;
    if ( v37 < 0 )
    {
      if ( a1 )
        v38 = a1 + 1152;
      else
        v38 = 0;
      ShareAccess[0] = v37;
      SclLogGenericMessage(
        v38,
        3,
        (int)SclEvent_Generic_Error,
        2685,
        (__int64)"SclpMigrateHive",
        "(%lx): Error re-opening excluded key [%ws]",
        *(_QWORD *)ShareAccess,
        a4);
      goto LABEL_106;
    }
    if ( FileHandle )
    {
      NtClose(FileHandle);
      FileHandle = 0;
    }
    INIT_OBJA_EX((__int64)&v58, &v55, v64, 576, 0);
    CanonicalMountKeyPath = NtCreateFile(&FileHandle, 0x120089u, &v58, &IoStatusBlock, 0, 0x80u, 0, 1u, 0x60u, 0, 0);
    if ( CanonicalMountKeyPath < 0 )
    {
      if ( a1 )
        v28 = a1 + 1152;
      else
        v28 = 0;
      v32 = 2717;
      CreateDispositiona = v64;
      v33 = "(%lx): Error re-opening excluded hive file [%ws]";
      goto LABEL_96;
    }
    CanonicalMountKeyPath = NtRestoreKey(v47, FileHandle, 0xCu);
    if ( CanonicalMountKeyPath < 0 )
    {
      if ( a1 )
        v34 = a1 + 1152;
      else
        v34 = 0;
      v35 = 2728;
      CreateOptions = v64;
      v36 = "(%lx): Error saving excluded key [%ws] to hive file [%ws]";
      *(_QWORD *)CreateDispositionb = a4;
      goto LABEL_80;
    }
  }
  NtFlushKey(Handle);
  if ( a1 )
    v39 = a1 + 1152;
  else
    v39 = 0;
  SclLogGenericMessage(
    v39,
    1,
    (int)SclEvent_Generic_Info,
    2738,
    (__int64)"SclpMigrateHive",
    "Successfully restored (by recursive copy) hive content for [%ws]",
    a3);
LABEL_106:
  if ( FileHandle )
    NtClose(FileHandle);
  if ( v47 )
    NtClose(v47);
  if ( Handle )
    NtClose(Handle);
  if ( KeyHandle )
    NtClose(KeyHandle);
  if ( v24 )
    SclRegLoadUnloadHive(0, v11, 0);
  return (unsigned int)CanonicalMountKeyPath;
}

```

## disassembly

```asm
0x18000c73c  push    rbp
0x18000c73e  push    rbx
0x18000c73f  push    rsi
0x18000c740  push    rdi
0x18000c741  push    r12
0x18000c743  push    r13
0x18000c745  push    r14
0x18000c747  push    r15
0x18000c749  lea     rbp, [rsp-6F8h]
0x18000c751  sub     rsp, 7F8h
0x18000c758  mov     rax, cs:__security_cookie
0x18000c75f  xor     rax, rsp
0x18000c762  mov     [rbp+730h+var_50], rax
0x18000c769  mov     rax, [rbp+730h+arg_20]
0x18000c770  xorps   xmm0, xmm0
0x18000c773  mov     [rbp+730h+SecurityDescriptor], rax
0x18000c777  xorps   xmm1, xmm1
0x18000c77a  mov     rax, [rbp+730h+arg_28]
0x18000c781  mov     r14, r9
0x18000c784  mov     [rbp+730h+var_798], rax
0x18000c788  mov     r13, r8
0x18000c78b  mov     rax, [rbp+730h+arg_30]
0x18000c792  mov     r12, rdx
0x18000c795  mov     [rbp+730h+var_7A0], rax
0x18000c799  mov     rdi, rcx
0x18000c79c  xor     eax, eax
0x18000c79e  mov     qword ptr [rsp+830h+FileAttributes], r8
0x18000c7a3  test    r9, r9
0x18000c7a6  mov     [rsp+830h+var_7B8], rax
0x18000c7ab  mov     esi, eax
0x18000c7ad  mov     [rbp+730h+KeyHandle], rax
0x18000c7b1  mov     [rsp+830h+Handle], rax
0x18000c7b6  lea     r8, aWsWsWs; "%ws%ws\\%ws"
0x18000c7bd  mov     [rsp+830h+var_7C8], rax
0x18000c7c2  lea     rcx, [rbp+730h+var_260]
0x18000c7c9  mov     [rsp+830h+FileHandle], rax
0x18000c7ce  mov     r9, rdx
0x18000c7d1  lea     rax, aWindowsOldWind; "WINDOWS.OLD\\WINDOWS\\System32\\config"
0x18000c7d8  mov     edx, 104h
0x18000c7dd  movups  xmmword ptr [rbp+730h+ObjectAttributes.ObjectName], xmm0
0x18000c7e1  setnz   r15b
0x18000c7e5  mov     [rsp+830h+AllocationSize], rax
0x18000c7ea  movups  xmmword ptr [rbp+730h+var_6B0.ObjectName], xmm0
0x18000c7f1  movups  xmmword ptr [rbp+730h+var_760.ObjectName], xmm0
0x18000c7f5  movups  xmmword ptr [rbp+730h+var_730.ObjectName], xmm0
0x18000c7f9  movups  xmmword ptr [rbp+730h+ObjectAttributes.Length], xmm0
0x18000c7fd  movups  xmmword ptr [rbp+730h+ObjectAttributes+1Ch], xmm0
0x18000c801  movups  xmmword ptr [rbp+730h+var_6B0.Length], xmm0
0x18000c808  movups  xmmword ptr [rbp+730h+var_6B0+1Ch], xmm0
0x18000c80f  movups  xmmword ptr [rbp+730h+var_760.Length], xmm0
0x18000c813  movups  xmmword ptr [rbp+730h+var_760+1Ch], xmm0
0x18000c817  movups  xmmword ptr [rbp+730h+var_730.Length], xmm0
0x18000c81b  movups  xmmword ptr [rbp+730h+var_730+1Ch], xmm0
0x18000c81f  movups  [rbp+730h+var_700], xmm0
0x18000c823  movups  [rbp+730h+var_6F0], xmm1
0x18000c827  movups  [rbp+730h+var_790], xmm0
0x18000c82b  movups  [rbp+730h+var_780], xmm1
0x18000c82f  movups  xmmword ptr [rbp+730h+IoStatusBlock], xmm0
0x18000c833  call    RtlStringCchPrintfW
0x18000c838  lea     r8, aSclpmigratehiv; "SclpMigrateHive"
0x18000c83f  mov     ebx, eax
0x18000c841  test    eax, eax
0x18000c843  jns     short loc_18000C889
0x18000c845  xor     edx, edx
0x18000c847  mov     qword ptr [rsp+830h+CreateDisposition], r13
0x18000c84c  mov     [rsp+830h+ShareAccess], eax
0x18000c850  lea     rcx, [rdi+480h]
0x18000c857  test    rdi, rdi
0x18000c85a  lea     rax, aLxFailedToCalc_1; "(%lx): Failed to calculate Windows.old'"...
0x18000c861  mov     qword ptr [rsp+830h+FileAttributes], rax
0x18000c866  mov     r9d, 9A3h
0x18000c86c  cmovz   rcx, rdx
0x18000c870  mov     [rsp+830h+AllocationSize], r8
0x18000c875  lea     r8, SclEvent_Generic_Error
0x18000c87c  lea     edx, [rsi+3]
0x18000c87f  call    SclLogGenericMessage
0x18000c884  jmp     loc_18000C946
0x18000c889  lea     rdx, [rsp+830h+var_7B8]
0x18000c88e  lea     rcx, [rbp+730h+var_260]
0x18000c895  call    SclRegGetCanonicalMountKeyPath
0x18000c89a  mov     ebx, eax
0x18000c89c  test    eax, eax
0x18000c89e  jns     short loc_18000C8CF
0x18000c8a0  test    rdi, rdi
0x18000c8a3  jz      short loc_18000C8AE
0x18000c8a5  lea     rcx, [rdi+480h]
0x18000c8ac  jmp     short loc_18000C8B0
0x18000c8ae  xor     ecx, ecx
0x18000c8b0  lea     rax, [rbp+730h+var_260]
0x18000c8b7  mov     r9d, 9ACh
0x18000c8bd  mov     qword ptr [rsp+830h+CreateDisposition], rax
0x18000c8c2  lea     rax, aLxFailedToCalc_2; "(%lx): Failed to calculate load key for"...
0x18000c8c9  mov     [rsp+830h+ShareAccess], ebx
0x18000c8cd  jmp     short loc_18000C91F
0x18000c8cf  lea     r9, aRegistryMachin_1; "\\REGISTRY\\MACHINE"
0x18000c8d6  mov     [rsp+830h+AllocationSize], r13
0x18000c8db  lea     r8, aWsWs_0; "%ws\\%ws"
0x18000c8e2  mov     edx, 104h
0x18000c8e7  lea     rcx, [rbp+730h+var_680]
0x18000c8ee  call    RtlStringCchPrintfW
0x18000c8f3  mov     ebx, eax
0x18000c8f5  test    eax, eax
0x18000c8f7  jns     short loc_18000C941
0x18000c8f9  test    rdi, rdi
0x18000c8fc  jz      short loc_18000C907
0x18000c8fe  lea     rcx, [rdi+480h]
0x18000c905  jmp     short loc_18000C909
0x18000c907  xor     ecx, ecx
0x18000c909  mov     qword ptr [rsp+830h+CreateDisposition], r13
0x18000c90e  mov     r9d, 9B8h
0x18000c914  mov     [rsp+830h+ShareAccess], eax
0x18000c918  lea     rax, aLxFailedToCalc_0; "(%lx): Failed to calculate full key for"...
0x18000c91f  mov     qword ptr [rsp+830h+FileAttributes], rax
0x18000c924  lea     r8, SclEvent_Generic_Error
0x18000c92b  lea     rax, aSclpmigratehiv; "SclpMigrateHive"
0x18000c932  mov     edx, 3
0x18000c937  mov     [rsp+830h+AllocationSize], rax
0x18000c93c  call    SclLogGenericMessage
0x18000c941  mov     rsi, [rsp+830h+var_7B8]
0x18000c946  test    r14, r14
0x18000c949  jz      short loc_18000C9C5
0x18000c94b  test    ebx, ebx
0x18000c94d  js      loc_18000CA34
0x18000c953  lea     rax, aWindowsPanther; "WINDOWS\\Panther\\Excluded.hiv"
0x18000c95a  mov     r9, r12
0x18000c95d  lea     r8, aWsWs; "%ws%ws"
0x18000c964  mov     [rsp+830h+AllocationSize], rax
0x18000c969  mov     edx, 104h
0x18000c96e  lea     rcx, [rbp+730h+var_470]
0x18000c975  call    RtlStringCchPrintfW
0x18000c97a  mov     ebx, eax
0x18000c97c  test    eax, eax
0x18000c97e  jns     short loc_18000C9C9
0x18000c980  test    rdi, rdi
0x18000c983  jz      short loc_18000C98E
0x18000c985  lea     rcx, [rdi+480h]
0x18000c98c  jmp     short loc_18000C990
0x18000c98e  xor     ecx, ecx
0x18000c990  mov     [rsp+830h+ShareAccess], eax
0x18000c994  lea     r8, SclEvent_Generic_Error
0x18000c99b  lea     rax, aLxFailedToCalc; "(%lx): Failed to calculate excluded hiv"...
0x18000c9a2  mov     r9d, 9C5h
0x18000c9a8  mov     qword ptr [rsp+830h+FileAttributes], rax
0x18000c9ad  mov     edx, 3
0x18000c9b2  lea     rax, aSclpmigratehiv; "SclpMigrateHive"
0x18000c9b9  mov     [rsp+830h+AllocationSize], rax
0x18000c9be  call    SclLogGenericMessage
0x18000c9c3  jmp     short loc_18000CA34
0x18000c9c5  test    ebx, ebx
0x18000c9c7  js      short loc_18000CA34
0x18000c9c9  lea     r8, [rbp+730h+var_260]
0x18000c9d0  mov     rdx, rsi
0x18000c9d3  mov     cl, 1
0x18000c9d5  call    SclRegLoadUnloadHive
0x18000c9da  mov     ebx, eax
0x18000c9dc  test    eax, eax
0x18000c9de  jns     short loc_18000CA34
0x18000c9e0  test    rdi, rdi
0x18000c9e3  jz      short loc_18000C9EE
0x18000c9e5  lea     rcx, [rdi+480h]
0x18000c9ec  jmp     short loc_18000C9F0
0x18000c9ee  xor     ecx, ecx
0x18000c9f0  mov     qword ptr [rsp+830h+CreateOptions], rsi
0x18000c9f5  lea     rax, [rbp+730h+var_260]
0x18000c9fc  mov     qword ptr [rsp+830h+CreateDisposition], rax
0x18000ca01  lea     r8, SclEvent_Generic_Error
0x18000ca08  lea     rax, aLxErrorLoading; "(%lx): Error loading old hive [%ws] int"...
0x18000ca0f  mov     [rsp+830h+ShareAccess], ebx
0x18000ca13  mov     qword ptr [rsp+830h+FileAttributes], rax
0x18000ca18  mov     r9d, 9D1h
0x18000ca1e  lea     rax, aSclpmigratehiv; "SclpMigrateHive"
0x18000ca25  mov     edx, 3
0x18000ca2a  mov     [rsp+830h+AllocationSize], rax
0x18000ca2f  call    SclLogGenericMessage
0x18000ca34  mov     r12d, ebx
0x18000ca37  shr     r12d, 1Fh
0x18000ca3b  xor     r12b, 1
0x18000ca3f  test    ebx, ebx
0x18000ca41  js      loc_18000D063
0x18000ca47  mov     r9d, 40h ; '@'
0x18000ca4d  mov     [rsp+830h+AllocationSize], 0
0x18000ca56  mov     r8, rsi
0x18000ca59  lea     rdx, [rbp+730h+var_700]
0x18000ca5d  lea     rcx, [rbp+730h+ObjectAttributes]
0x18000ca61  call    INIT_OBJA_EX
0x18000ca66  lea     r8, [rbp+730h+ObjectAttributes]; ObjectAttributes
0x18000ca6a  mov     edx, 1020019h; DesiredAccess
0x18000ca6f  lea     rcx, [rbp+730h+KeyHandle]; KeyHandle
0x18000ca73  call    cs:__imp_NtOpenKey
0x18000ca79  mov     ebx, eax
0x18000ca7b  test    eax, eax
0x18000ca7d  jns     short loc_18000CAA7
0x18000ca7f  test    rdi, rdi
0x18000ca82  jz      short loc_18000CA8D
0x18000ca84  lea     rcx, [rdi+480h]
0x18000ca8b  jmp     short loc_18000CA8F
0x18000ca8d  xor     ecx, ecx
0x18000ca8f  mov     qword ptr [rsp+830h+CreateDisposition], rsi
0x18000ca94  mov     r9d, 9DFh
0x18000ca9a  mov     [rsp+830h+ShareAccess], eax
0x18000ca9e  lea     rax, aLxErrorOpening_1; "(%lx): Error opening old hive key [%ws]"
0x18000caa5  jmp     short loc_18000CB1B
0x18000caa7  mov     r9d, 40h ; '@'
0x18000caad  mov     [rsp+830h+AllocationSize], 0
0x18000cab6  lea     r8, [rbp+730h+var_680]
0x18000cabd  lea     rdx, [rbp+730h+var_6F0]
0x18000cac1  lea     rcx, [rbp+730h+var_6B0]
0x18000cac8  call    INIT_OBJA_EX
0x18000cacd  lea     r8, [rbp+730h+var_6B0]; ObjectAttributes
0x18000cad4  mov     edx, 10F003Fh; DesiredAccess
0x18000cad9  lea     rcx, [rsp+830h+Handle]; KeyHandle
0x18000cade  call    cs:__imp_NtOpenKey
0x18000cae4  mov     ebx, eax
0x18000cae6  test    eax, eax
0x18000cae8  jns     loc_18000CB84
0x18000caee  test    rdi, rdi
0x18000caf1  jz      short loc_18000CAFC
0x18000caf3  lea     rcx, [rdi+480h]
0x18000cafa  jmp     short loc_18000CAFE
0x18000cafc  xor     ecx, ecx
0x18000cafe  lea     rax, [rbp+730h+var_680]
0x18000cb05  mov     r9d, 9EEh
0x18000cb0b  mov     qword ptr [rsp+830h+CreateDisposition], rax
0x18000cb10  lea     rax, aLxErrorOpening_0; "(%lx): Error opening current hive key ["...
0x18000cb17  mov     [rsp+830h+ShareAccess], ebx
0x18000cb1b  mov     qword ptr [rsp+830h+FileAttributes], rax
0x18000cb20  lea     r8, SclEvent_Generic_Error
0x18000cb27  lea     rax, aSclpmigratehiv; "SclpMigrateHive"
0x18000cb2e  mov     edx, 3
0x18000cb33  mov     [rsp+830h+AllocationSize], rax
0x18000cb38  call    SclLogGenericMessage
0x18000cb3d  test    ebx, ebx
0x18000cb3f  js      loc_18000D063
0x18000cb45  mov     rax, [rbp+730h+SecurityDescriptor]
0x18000cb49  test    rax, rax
0x18000cb4c  jz      loc_18000CD86
0x18000cb52  mov     rcx, [rsp+830h+Handle]; Handle
0x18000cb57  mov     r8, rax; SecurityDescriptor
0x18000cb5a  mov     edx, 4; SecurityInformation
0x18000cb5f  call    cs:__imp_NtSetSecurityObject
0x18000cb65  mov     ebx, eax
0x18000cb67  test    eax, eax
0x18000cb69  jns     loc_18000CDC8
0x18000cb6f  test    rdi, rdi
0x18000cb72  jz      loc_18000CD66
0x18000cb78  lea     rcx, [rdi+480h]
0x18000cb7f  jmp     loc_18000CD68
0x18000cb84  test    r14, r14
0x18000cb87  jz      short loc_18000CB45
0x18000cb89  mov     rcx, [rsp+830h+var_7C8]; Handle
0x18000cb8e  test    rcx, rcx
0x18000cb91  jz      short loc_18000CBA2
0x18000cb93  call    cs:__imp_NtClose
0x18000cb99  mov     [rsp+830h+var_7C8], 0
0x18000cba2  mov     rax, [rsp+830h+Handle]
0x18000cba7  lea     rdx, [rbp+730h+var_790]
0x18000cbab  mov     r9d, 40h ; '@'
0x18000cbb1  mov     [rsp+830h+AllocationSize], rax
0x18000cbb6  mov     r8, r14
0x18000cbb9  lea     rcx, [rbp+730h+var_760]
0x18000cbbd  call    INIT_OBJA_EX
0x18000cbc2  lea     r8, [rbp+730h+var_760]; ObjectAttributes
0x18000cbc6  mov     edx, 0F003Fh; DesiredAccess
0x18000cbcb  lea     rcx, [rsp+830h+var_7C8]; KeyHandle
0x18000cbd0  call    cs:__imp_NtOpenKey
0x18000cbd6  mov     ebx, eax
0x18000cbd8  test    eax, eax
0x18000cbda  jns     loc_18000CC67
0x18000cbe0  cmp     eax, 0C0000225h
0x18000cbe5  jz      short loc_18000CC19
0x18000cbe7  cmp     eax, 0C0000034h
0x18000cbec  jz      short loc_18000CC19
0x18000cbee  test    rdi, rdi
0x18000cbf1  jz      short loc_18000CBFC
0x18000cbf3  lea     rcx, [rdi+480h]
0x18000cbfa  jmp     short loc_18000CBFE
0x18000cbfc  xor     ecx, ecx
0x18000cbfe  mov     [rsp+830h+CreateDisposition], eax
0x18000cc02  mov     r9d, 0A13h
0x18000cc08  mov     qword ptr [rsp+830h+ShareAccess], r14
0x18000cc0d  lea     rax, aErrorOpeningEx; "Error opening excluded key [%ws]: [0x%0"...
0x18000cc14  jmp     loc_18000CF9E
0x18000cc19  test    rdi, rdi
0x18000cc1c  jz      short loc_18000CC27
0x18000cc1e  lea     rcx, [rdi+480h]
0x18000cc25  jmp     short loc_18000CC29
0x18000cc27  xor     ecx, ecx
0x18000cc29  lea     rax, aExcludedKeyNot; "Excluded key not found: [%ws]"
0x18000cc30  mov     qword ptr [rsp+830h+ShareAccess], r14
0x18000cc35  mov     qword ptr [rsp+830h+FileAttributes], rax
0x18000cc3a  lea     r8, SclEvent_Generic_Info
0x18000cc41  lea     rax, aSclpmigratehiv; "SclpMigrateHive"
0x18000cc48  mov     r9d, 0A0Ah
0x18000cc4e  mov     edx, 1
0x18000cc53  mov     [rsp+830h+AllocationSize], rax
0x18000cc58  call    SclLogGenericMessage
0x18000cc5d  xor     r15b, r15b
0x18000cc60  xor     ebx, ebx
0x18000cc62  jmp     loc_18000CB3D
0x18000cc67  mov     rcx, [rsp+830h+FileHandle]; Handle
  ... truncated ...
```
