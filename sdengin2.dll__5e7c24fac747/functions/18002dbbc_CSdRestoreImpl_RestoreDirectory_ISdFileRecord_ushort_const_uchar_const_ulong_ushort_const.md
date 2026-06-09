# CSdRestoreImpl::_RestoreDirectory(ISdFileRecord *,ushort const *,uchar const *,ulong,ushort const *)

- ea: `0x18002dbbc`
- end: `0x18002e514`
- name: `?_RestoreDirectory@CSdRestoreImpl@@AEAAJPEAUISdFileRecord@@PEBGPEBEK1@Z`
- size: `2392`
- prototype: `__int64 __fastcall(CSdRestoreImpl *this, struct ISdFileRecord *, WCHAR *, unsigned __int8 *, unsigned int, wchar_t *String1)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002d470`

## callees

- `0x1800081d8`
- `0x180008200`
- `0x180008240`
- `0x180014394`
- `0x18002dbbc`
- `0x18002e51c`
- `0x18002e68c`
- `0x18006fe84`
- `0x18006ff8c`
- `0x180070564`
- `0x18008f5d0`
- `0x18008f660`
- `0x180098280`
- `0x1800c9830`
- `0x1800cb010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18002de7d`
- `msvcrt!_wcsicmp` at `0x18002de7d`
- `ntdll!NtSetInformationFile` at `0x18002e34d`
- `ntdll!NtSetInformationFile` at `0x18002e34d`
- `ntdll!NtQueryInformationFile` at `0x18002e034`
- `ntdll!NtQueryInformationFile` at `0x18002e034`
- `ntdll!NtCreateFile` at `0x18002df64`
- `ntdll!NtCreateFile` at `0x18002df64`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x18002deca`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x18002deca`
- `ntdll!RtlFreeHeap` at `0x18002e4a4`
- `ntdll!RtlFreeHeap` at `0x18002e4a4`
- `KERNEL32!GetLastError` at `0x18002e10e`
- `KERNEL32!GetLastError` at `0x18002e2e4`
- `KERNEL32!GetLastError` at `0x18002e10e`
- `KERNEL32!GetLastError` at `0x18002e2e4`
- `KERNEL32!CloseHandle` at `0x18002e37d`
- `KERNEL32!CloseHandle` at `0x18002e4c0`
- `KERNEL32!CloseHandle` at `0x18002e4df`
- `KERNEL32!CloseHandle` at `0x18002e37d`
- `KERNEL32!CloseHandle` at `0x18002e4c0`
- `KERNEL32!CloseHandle` at `0x18002e4df`
- `KERNEL32!DeviceIoControl` at `0x18002e26c`
- `KERNEL32!DeviceIoControl` at `0x18002e26c`
- `KERNEL32!SetFileShortNameW` at `0x18002e2da`
- `KERNEL32!SetFileShortNameW` at `0x18002e2da`
- `api-ms-win-security-base-l1-1-0!SetKernelObjectSecurity` at `0x18002e0f2`
- `api-ms-win-security-base-l1-1-0!SetKernelObjectSecurity` at `0x18002e0f2`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18002e06f`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18002e06f`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x18002e0ad`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x18002e0ad`
- `ext-ms-win-advapi32-encryptedfile-l1-1-0!EncryptFileW` at `0x18002e3ec`
- `ext-ms-win-advapi32-encryptedfile-l1-1-0!EncryptFileW` at `0x18002e3ec`
- `ext-ms-win-advapi32-encryptedfile-l1-1-0!DecryptFileW` at `0x18002e412`
- `ext-ms-win-advapi32-encryptedfile-l1-1-0!DecryptFileW` at `0x18002e412`

## string_xrefs

- `0x18002dc08`: `CSdRestoreImpl::_RestoreDirectory`

## pseudocode

```c
__int64 __fastcall CSdRestoreImpl::_RestoreDirectory(
        CSdRestoreImpl *this,
        struct ISdFileRecord *a2,
        WCHAR *a3,
        unsigned __int8 *a4,
        unsigned int a5,
        wchar_t *String1)
{
  __int64 v10; // rbx
  __int16 v11; // ax
  int FileAttributesTag; // eax
  int v13; // ecx
  __int16 v14; // ax
  bool v15; // cc
  int v16; // eax
  BOOL v17; // ecx
  BOOL v18; // edx
  int v19; // edi
  unsigned int v20; // eax
  NTSTATUS v21; // eax
  unsigned int v22; // eax
  __int64 v23; // rcx
  __int64 v24; // rcx
  SECURITY_INFORMATION v25; // edx
  PVOID *v26; // rcx
  DWORD LastError; // eax
  unsigned int v28; // r8d
  int v29; // r13d
  unsigned int v30; // edx
  PVOID *v31; // rcx
  __int64 v32; // rcx
  __int64 v33; // rcx
  unsigned int v34; // eax
  CSdRestoreImpl *v35; // rcx
  unsigned __int16 v36; // dx
  int v37; // eax
  __int16 v38; // ax
  int v39; // eax
  unsigned int v40; // edi
  unsigned int v42; // [rsp+60h] [rbp-A0h] BYREF
  __int16 InBuffer; // [rsp+64h] [rbp-9Ch] BYREF
  int LastFailureAsHRESULT; // [rsp+68h] [rbp-98h] BYREF
  __int16 v45; // [rsp+6Ch] [rbp-94h]
  __int16 v46; // [rsp+6Eh] [rbp-92h]
  BOOL v47; // [rsp+A0h] [rbp-60h]
  WINBOOL bDaclPresent; // [rsp+A4h] [rbp-5Ch] BYREF
  WINBOOL bSaclPresent; // [rsp+A8h] [rbp-58h] BYREF
  void *FileHandle; // [rsp+B0h] [rbp-50h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+B8h] [rbp-48h] BYREF
  WINBOOL bSaclDefaulted; // [rsp+BCh] [rbp-44h] BYREF
  DWORD BytesReturned; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 *v54; // [rsp+C8h] [rbp-38h] BYREF
  PVOID P[2]; // [rsp+D0h] [rbp-30h] BYREF
  PACL pDacl; // [rsp+E0h] [rbp-20h] BYREF
  PACL pSacl; // [rsp+E8h] [rbp-18h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+F0h] [rbp-10h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+100h] [rbp+0h] BYREF
  int v60; // [rsp+130h] [rbp+30h] BYREF
  __int128 v61; // [rsp+134h] [rbp+34h] BYREF
  ULONG FileAttributes[4]; // [rsp+144h] [rbp+44h]
  int v63; // [rsp+154h] [rbp+54h]
  int FileInformation; // [rsp+158h] [rbp+58h] BYREF
  __int128 v65; // [rsp+15Ch] [rbp+5Ch]
  __int128 v66; // [rsp+16Ch] [rbp+6Ch]
  int v67; // [rsp+17Ch] [rbp+7Ch]
  WCHAR ShortName[16]; // [rsp+180h] [rbp+80h] BYREF

  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&LastFailureAsHRESULT,
    "CSdRestoreImpl::_RestoreDirectory",
    0x107Fu,
    1u);
  v10 = -1;
  BytesReturned = 0;
  InBuffer = 0;
  memset(ShortName, 0, 28);
  v42 = 0;
  v47 = 0;
  *(_OWORD *)P = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  IoStatusBlock = 0;
  FileHandle = (void *)-1LL;
  v60 = 0;
  v61 = 0;
  *(_OWORD *)FileAttributes = 0;
  v63 = 0;
  pDacl = 0;
  pSacl = 0;
  bDaclPresent = 0;
  bSaclPresent = 0;
  bDaclDefaulted = 0;
  bSaclDefaulted = 0;
  FileInformation = 0;
  v65 = 0;
  v66 = 0;
  v67 = 0;
  v11 = 4249;
  if ( !a2 || (v45 = 4249, v11 = 4250, !a3) || (v45 = 4250, v11 = 4251, !String1) )
  {
    LastFailureAsHRESULT = -2147024809;
LABEL_3:
    v46 = v11;
    goto LABEL_103;
  }
  LastFailureAsHRESULT = 0;
  v45 = 4251;
  FileAttributesTag = GetFileAttributesTag(a3);
  v13 = FileAttributesTag;
  if ( FileAttributesTag < 0 )
  {
    v15 = (unsigned int)(FileAttributesTag + 2147024894) <= 1;
    v11 = 4266;
    if ( !v15 )
    {
      LastFailureAsHRESULT = v13;
      goto LABEL_3;
    }
    LastFailureAsHRESULT = 0;
    v45 = 4266;
    LastFailureAsHRESULT = (*(__int64 (__fastcall **)(struct ISdFileRecord *, unsigned int *))(*(_QWORD *)a2 + 128LL))(
                             a2,
                             &v42);
    v11 = 4268;
    if ( LastFailureAsHRESULT < 0 )
      goto LABEL_3;
    v45 = 4268;
    LastFailureAsHRESULT = (*(__int64 (__fastcall **)(struct ISdFileRecord *, int *))(*(_QWORD *)a2 + 64LL))(a2, &v60);
    v11 = 4269;
    if ( LastFailureAsHRESULT < 0 )
      goto LABEL_3;
    v45 = 4269;
    LastFailureAsHRESULT = (*(__int64 (__fastcall **)(struct ISdFileRecord *, char *))(*(_QWORD *)a2 + 120LL))(
                             a2,
                             (char *)&v61 + 4);
    v11 = 4270;
    if ( LastFailureAsHRESULT < 0 )
      goto LABEL_3;
    v45 = 4270;
    LastFailureAsHRESULT = (*(__int64 (__fastcall **)(struct ISdFileRecord *, char *))(*(_QWORD *)a2 + 72LL))(
                             a2,
                             (char *)&v61 + 12);
    v11 = 4271;
    if ( LastFailureAsHRESULT < 0 )
      goto LABEL_3;
    v45 = 4271;
    LastFailureAsHRESULT = (*(__int64 (__fastcall **)(struct ISdFileRecord *, WCHAR *))(*(_QWORD *)a2 + 40LL))(
                             a2,
                             ShortName);
    v11 = 4272;
    if ( LastFailureAsHRESULT < 0 )
      goto LABEL_3;
    v45 = 4272;
    v16 = v42 & 0x1A30A7;
    if ( (v42 & 0x1A30A7) == 0 )
      v16 = 128;
    FileAttributes[3] = v16;
    v17 = _wcsicmp(String1, L"NTFS") == 0;
    v18 = 0;
    if ( *((_DWORD *)this + 14) != 11 )
      v18 = v17;
    v47 = ShortName[0] != 0 && v18;
    v19 = ((v47 + 49152) << 16) | 0x1080000;
    if ( *((_DWORD *)this + 14) == 11 )
      v19 = (v47 + 49152) << 16;
    v20 = RtlDosPathNameToNtPathName_U_WithStatus(a3, P, 0, 0);
    LastFailureAsHRESULT = HRESULTFromNTSTATUS(v20);
    v11 = 4315;
    if ( LastFailureAsHRESULT < 0 )
      goto LABEL_3;
    v45 = 4315;
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 64;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)P;
    ObjectAttributes.SecurityDescriptor = a4;
    ObjectAttributes.SecurityQualityOfService = 0;
    v21 = NtCreateFile(
            &FileHandle,
            v19 | 0x140001,
            &ObjectAttributes,
            &IoStatusBlock,
            0,
            FileAttributes[3],
            3u,
            2u,
            0x4021u,
            0,
            0);
    if ( v21 < 0 )
    {
      LastFailureAsHRESULT = HRESULTFromNTSTATUS((unsigned int)v21);
      if ( LastFailureAsHRESULT < 0 )
      {
        v11 = 4334;
        goto LABEL_3;
      }
    }
    v10 = (__int64)FileHandle;
    FileHandle = (void *)-1LL;
    LastFailureAsHRESULT = 0;
    v45 = 4337;
    v54 = a3;
    LastFailureAsHRESULT = CSxFunctionTracer::_SetContextHelper(
                             (CSxFunctionTracer *)&LastFailureAsHRESULT,
                             hInstance,
                             0x4E8Du,
                             1u,
                             (const unsigned __int16 **)&v54);
    v11 = 4338;
    if ( LastFailureAsHRESULT < 0 )
      goto LABEL_3;
    v45 = 4338;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x80) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 87, &WPP_052bc5b66f273e09fada3dec80af9ee3_Traceguids, a3);
    v22 = NtQueryInformationFile((HANDLE)v10, &IoStatusBlock, &FileInformation, 0x28u, FileBasicInformation);
    LastFailureAsHRESULT = HRESULTFromNTSTATUS(v22);
    v11 = 4351;
    if ( LastFailureAsHRESULT < 0 )
      goto LABEL_3;
    v45 = 4351;
    if ( a4 )
    {
      if ( !GetSecurityDescriptorDacl(a4, &bDaclPresent, &pDacl, &bDaclDefaulted) )
      {
        LastFailureAsHRESULT = GetLastFailureAsHRESULT(v23);
        v11 = 4355;
        goto LABEL_3;
      }
      LastFailureAsHRESULT = 0;
      v45 = 4355;
      if ( !GetSecurityDescriptorSacl(a4, &bSaclPresent, &pSacl, &bSaclDefaulted) )
      {
        LastFailureAsHRESULT = GetLastFailureAsHRESULT(v24);
        v11 = 4356;
        goto LABEL_3;
      }
      v25 = 0;
      LastFailureAsHRESULT = 0;
      v45 = 4356;
      if ( bDaclPresent )
        v25 = 4;
      if ( bSaclPresent )
        v25 |= 0x18u;
      if ( !SetKernelObjectSecurity((HANDLE)v10, v25, a4) )
      {
        v26 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x80) == 0 )
          goto LABEL_49;
        LastError = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 88, &WPP_052bc5b66f273e09fada3dec80af9ee3_Traceguids, LastError);
      }
    }
    v26 = (PVOID *)WPP_GLOBAL_Control;
LABEL_49:
    v28 = v42;
    if ( (v42 & 0x4000) != 0 && (a5 & 0x20000) == 0 )
    {
      if ( v26 != &WPP_GLOBAL_Control && (*((_BYTE *)v26 + 28) & 0x80) != 0 )
      {
        WPP_SF_(v26[2], 89, &WPP_052bc5b66f273e09fada3dec80af9ee3_Traceguids);
        v28 = v42;
      }
      v42 = v28 & 0xFFFFBFFF;
    }
    v54 = a3;
    LastFailureAsHRESULT = CSxFunctionTracer::_SetContextHelper(
                             (CSxFunctionTracer *)&LastFailureAsHRESULT,
                             hInstance,
                             0x4E8Eu,
                             1u,
                             (const unsigned __int16 **)&v54);
    v11 = 4385;
    if ( LastFailureAsHRESULT < 0 )
      goto LABEL_3;
    v29 = 0;
    v45 = 4385;
    v30 = v42;
    if ( (v42 & 0x800) != 0 && (a5 & 0x10) == 0 )
    {
      v31 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x80) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 90, &WPP_052bc5b66f273e09fada3dec80af9ee3_Traceguids);
        v30 = v42;
        v31 = (PVOID *)WPP_GLOBAL_Control;
      }
      v30 &= ~0x800u;
      v42 = v30;
    }
    else
    {
      v31 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( (((unsigned __int16)v30 ^ WORD6(v66)) & 0x800) != 0 )
    {
      if ( (WORD6(v66) & 0x4000) != 0 )
      {
        if ( v31 != &WPP_GLOBAL_Control && (*((_BYTE *)v31 + 28) & 0x80) != 0 )
        {
          WPP_SF_(v31[2], 91, &WPP_052bc5b66f273e09fada3dec80af9ee3_Traceguids);
          v31 = (PVOID *)WPP_GLOBAL_Control;
        }
        v29 = 1;
      }
      else
      {
        InBuffer = (v30 & 0x800) != 0;
        if ( !DeviceIoControl((HANDLE)v10, 0x9C040u, &InBuffer, 2u, 0, 0, &BytesReturned, 0) )
        {
          LastFailureAsHRESULT = GetLastFailureAsHRESULT(v32);
          v11 = 4450;
          goto LABEL_3;
        }
        LastFailureAsHRESULT = 0;
        v45 = 4450;
        v31 = (PVOID *)WPP_GLOBAL_Control;
      }
    }
    if ( v47 )
    {
      if ( !SetFileShortNameW((HANDLE)v10, ShortName) )
      {
        if ( GetLastError() != 183 )
        {
          LastFailureAsHRESULT = GetLastFailureAsHRESULT(v33);
          v11 = 4471;
          goto LABEL_3;
        }
        LastFailureAsHRESULT = 0;
        v45 = 4471;
      }
    }
    else if ( v31 != &WPP_GLOBAL_Control && (*((_BYTE *)v31 + 28) & 0x80) != 0 )
    {
      WPP_SF_(v31[2], 92, &WPP_052bc5b66f273e09fada3dec80af9ee3_Traceguids);
    }
    v34 = NtSetInformationFile((HANDLE)v10, &IoStatusBlock, &v60, 0x28u, FileBasicInformation);
    LastFailureAsHRESULT = HRESULTFromNTSTATUS(v34);
    v11 = 4483;
    if ( LastFailureAsHRESULT < 0 )
      goto LABEL_3;
    v45 = 4483;
    if ( (unsigned __int64)(v10 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      CloseHandle((HANDLE)v10);
      v10 = -1;
    }
    v36 = v42;
    LOBYTE(v35) = (v42 & 0x100) != 0;
    if ( ((unsigned __int8)v35 & ((a5 & 0x40000) != 0)) != 0 )
    {
      v37 = CSdRestoreImpl::_RestoreDirectoryTempAttribute(v35, a3);
      if ( v37 < 0 )
      {
        v35 = (CSdRestoreImpl *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x80) != 0 )
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            93,
            (unsigned int)&WPP_052bc5b66f273e09fada3dec80af9ee3_Traceguids,
            (_DWORD)a3,
            v37);
      }
      v36 = v42;
    }
    if ( ((v36 ^ WORD6(v66)) & 0x4000) != 0 )
    {
      if ( (v36 & 0x4000) != 0 )
      {
        if ( !EncryptFileW(a3) )
        {
          LastFailureAsHRESULT = GetLastFailureAsHRESULT(v35);
          v11 = 4519;
          goto LABEL_3;
        }
        v38 = 4519;
      }
      else
      {
        if ( !DecryptFileW(a3, 0) )
        {
          LastFailureAsHRESULT = GetLastFailureAsHRESULT(v35);
          v11 = 4523;
          goto LABEL_3;
        }
        v38 = 4523;
      }
      v45 = v38;
      LastFailureAsHRESULT = 0;
    }
    if ( v29 )
    {
      v39 = CSdRestoreImpl::_RestoreDirectoryCompression(v35, a3);
      if ( v39 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x80) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          94,
          &WPP_052bc5b66f273e09fada3dec80af9ee3_Traceguids,
          (unsigned int)v39);
    }
    LastFailureAsHRESULT = 0;
    v14 = 4553;
    goto LABEL_102;
  }
  v11 = 4258;
  if ( (v47 & 0x10) == 0 )
  {
    LastFailureAsHRESULT = -2147024891;
    goto LABEL_3;
  }
  LastFailureAsHRESULT = 0;
  v45 = 4258;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 86, &WPP_052bc5b66f273e09fada3dec80af9ee3_Traceguids);
  LastFailureAsHRESULT = 1;
  v14 = 4262;
LABEL_102:
  v45 = v14;
LABEL_103:
  if ( P[1] )
  {
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P[1]);
    P[1] = 0;
  }
  if ( (char *)FileHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    CloseHandle(FileHandle);
    FileHandle = 0;
  }
  v40 = LastFailureAsHRESULT;
  if ( (unsigned __int64)(v10 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)v10);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT);
  return v40;
}

```

## disassembly

```asm
0x18002dbbc  push    rbp
0x18002dbbe  push    rbx
0x18002dbbf  push    rsi
0x18002dbc0  push    rdi
0x18002dbc1  push    r12
0x18002dbc3  push    r13
0x18002dbc5  push    r14
0x18002dbc7  push    r15
0x18002dbc9  lea     rbp, [rsp-0B8h]
0x18002dbd1  sub     rsp, 1B8h
0x18002dbd8  mov     rax, cs:__security_cookie
0x18002dbdf  xor     rax, rsp
0x18002dbe2  mov     [rbp+0F0h+var_50], rax
0x18002dbe9  mov     r12, r9
0x18002dbec  mov     r15, r8
0x18002dbef  mov     rdi, rdx
0x18002dbf2  mov     r13, rcx
0x18002dbf5  mov     rsi, [rbp+0F0h+String1]
0x18002dbfc  mov     r9d, 1; unsigned __int16
0x18002dc02  mov     r8d, 107Fh; unsigned __int16
0x18002dc08  lea     rdx, aCsdrestoreimpl_51; "CSdRestoreImpl::_RestoreDirectory"
0x18002dc0f  lea     rcx, [rsp+1F0h+var_188]; this
0x18002dc14  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18002dc19  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18002dc1d  mov     rbx, rcx
0x18002dc20  xor     r14d, r14d
0x18002dc23  mov     [rbp+0F0h+BytesReturned], r14d
0x18002dc27  mov     [rsp+1F0h+InBuffer], r14w
0x18002dc2d  mov     [rbp+0F0h+ShortName], r14w
0x18002dc35  xorps   xmm0, xmm0
0x18002dc38  xor     eax, eax
0x18002dc3a  movups  xmmword ptr [rbp+0F0h+var_6E], xmm0
0x18002dc41  movups  xmmword ptr [rbp+0F0h+var_6E+0Ah], xmm0
0x18002dc48  mov     [rsp+1F0h+var_190], r14d
0x18002dc4d  mov     [rbp+0F0h+var_150], r14d
0x18002dc51  movups  xmmword ptr [rbp+0F0h+P], xmm0
0x18002dc55  xorps   xmm1, xmm1
0x18002dc58  movups  xmmword ptr [rbp+0F0h+ObjectAttributes.Length], xmm1
0x18002dc5c  movups  xmmword ptr [rbp+0F0h+ObjectAttributes.ObjectName], xmm1
0x18002dc60  movups  xmmword ptr [rbp+0F0h+ObjectAttributes.SecurityDescriptor], xmm1
0x18002dc64  movups  xmmword ptr [rbp+0F0h+IoStatusBlock], xmm0
0x18002dc68  mov     [rbp+0F0h+FileHandle], rcx
0x18002dc6c  mov     [rbp+0F0h+var_C0], r14d
0x18002dc70  movups  [rbp+0F0h+var_BC], xmm0
0x18002dc74  movups  xmmword ptr [rbp+0F0h+var_AC], xmm0
0x18002dc78  mov     [rbp+0F0h+var_9C], eax
0x18002dc7b  mov     [rbp+0F0h+pDacl], r14
0x18002dc7f  mov     [rbp+0F0h+pSacl], r14
0x18002dc83  mov     [rbp+0F0h+bDaclPresent], r14d
0x18002dc87  mov     [rbp+0F0h+bSaclPresent], r14d
0x18002dc8b  mov     [rbp+0F0h+bDaclDefaulted], r14d
0x18002dc8f  mov     [rbp+0F0h+bSaclDefaulted], r14d
0x18002dc93  mov     [rbp+0F0h+FileInformation], r14d
0x18002dc97  movups  [rbp+0F0h+var_94], xmm0
0x18002dc9b  movups  [rbp+0F0h+var_84], xmm0
0x18002dc9f  mov     [rbp+0F0h+var_74], eax
0x18002dca2  mov     eax, 1099h
0x18002dca7  test    rdi, rdi
0x18002dcaa  jnz     short loc_18002DCBE
0x18002dcac  mov     [rsp+1F0h+var_188], 80070057h
0x18002dcb4  mov     [rsp+1F0h+var_182], ax
0x18002dcb9  jmp     loc_18002E48A
0x18002dcbe  mov     [rsp+1F0h+var_184], ax
0x18002dcc3  mov     eax, 109Ah
0x18002dcc8  test    r15, r15
0x18002dccb  jz      short loc_18002DCAC
0x18002dccd  mov     [rsp+1F0h+var_184], ax
0x18002dcd2  mov     eax, 109Bh
0x18002dcd7  test    rsi, rsi
0x18002dcda  jz      short loc_18002DCAC
0x18002dcdc  mov     [rsp+1F0h+var_188], r14d
0x18002dce1  mov     [rsp+1F0h+var_184], ax
0x18002dce6  xor     r9d, r9d
0x18002dce9  xor     r8d, r8d
0x18002dcec  lea     rdx, [rbp+0F0h+var_150]
0x18002dcf0  mov     rcx, r15; lpFileName
0x18002dcf3  call    _GetFileAttributesTag
0x18002dcf8  mov     ecx, eax
0x18002dcfa  test    eax, eax
0x18002dcfc  js      short loc_18002DD63
0x18002dcfe  mov     eax, 10A2h
0x18002dd03  test    byte ptr [rbp+0F0h+var_150], 10h
0x18002dd07  jnz     short loc_18002DD13
0x18002dd09  mov     [rsp+1F0h+var_188], 80070005h
0x18002dd11  jmp     short loc_18002DCB4
0x18002dd13  mov     [rsp+1F0h+var_188], r14d
0x18002dd18  mov     [rsp+1F0h+var_184], ax
0x18002dd1d  lea     rdi, WPP_GLOBAL_Control
0x18002dd24  mov     rcx, cs:WPP_GLOBAL_Control
0x18002dd2b  cmp     rcx, rdi
0x18002dd2e  jz      short loc_18002DD50
0x18002dd30  mov     r14d, 80h
0x18002dd36  test    [rcx+1Ch], r14b
0x18002dd3a  jz      short loc_18002DD50
0x18002dd3c  lea     edx, [r14-2Ah]
0x18002dd40  lea     r8, WPP_052bc5b66f273e09fada3dec80af9ee3_Traceguids
0x18002dd47  mov     rcx, [rcx+10h]
0x18002dd4b  call    WPP_SF_
0x18002dd50  mov     edx, 1
0x18002dd55  mov     [rsp+1F0h+var_188], edx
0x18002dd59  mov     eax, 10A6h
0x18002dd5e  jmp     loc_18002E485
0x18002dd63  add     eax, 7FF8FFFEh
0x18002dd68  mov     edx, 1
0x18002dd6d  cmp     eax, edx
0x18002dd6f  mov     eax, 10AAh
0x18002dd74  jbe     short loc_18002DD7F
0x18002dd76  mov     [rsp+1F0h+var_188], ecx
0x18002dd7a  jmp     loc_18002DCB4
0x18002dd7f  mov     [rsp+1F0h+var_188], r14d
0x18002dd84  mov     [rsp+1F0h+var_184], ax
0x18002dd89  mov     rax, [rdi]
0x18002dd8c  lea     rdx, [rsp+1F0h+var_190]
0x18002dd91  mov     rcx, rdi
0x18002dd94  mov     rax, [rax+80h]
0x18002dd9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dda0  mov     [rsp+1F0h+var_188], eax
0x18002dda4  test    eax, eax
0x18002dda6  mov     eax, 10ACh
0x18002ddab  js      loc_18002DCB4
0x18002ddb1  mov     [rsp+1F0h+var_184], ax
0x18002ddb6  mov     rax, [rdi]
0x18002ddb9  lea     rdx, [rbp+0F0h+var_C0]
0x18002ddbd  mov     rcx, rdi
0x18002ddc0  mov     rax, [rax+40h]
0x18002ddc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ddc9  mov     [rsp+1F0h+var_188], eax
0x18002ddcd  test    eax, eax
0x18002ddcf  mov     eax, 10ADh
0x18002ddd4  js      loc_18002DCB4
0x18002ddda  mov     [rsp+1F0h+var_184], ax
0x18002dddf  mov     rax, [rdi]
0x18002dde2  lea     rdx, [rbp+0F0h+var_BC+4]
0x18002dde6  mov     rcx, rdi
0x18002dde9  mov     rax, [rax+78h]
0x18002dded  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ddf2  mov     [rsp+1F0h+var_188], eax
0x18002ddf6  test    eax, eax
0x18002ddf8  mov     eax, 10AEh
0x18002ddfd  js      loc_18002DCB4
0x18002de03  mov     [rsp+1F0h+var_184], ax
0x18002de08  mov     rax, [rdi]
0x18002de0b  lea     rdx, [rbp+0F0h+var_BC+0Ch]
0x18002de0f  mov     rcx, rdi
0x18002de12  mov     rax, [rax+48h]
0x18002de16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002de1b  mov     [rsp+1F0h+var_188], eax
0x18002de1f  test    eax, eax
0x18002de21  mov     eax, 10AFh
0x18002de26  js      loc_18002DCB4
0x18002de2c  mov     [rsp+1F0h+var_184], ax
0x18002de31  mov     rax, [rdi]
0x18002de34  lea     rdx, [rbp+0F0h+ShortName]
0x18002de3b  mov     rcx, rdi
0x18002de3e  mov     rax, [rax+28h]
0x18002de42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002de47  mov     [rsp+1F0h+var_188], eax
0x18002de4b  test    eax, eax
0x18002de4d  mov     eax, 10B0h
0x18002de52  js      loc_18002DCB4
0x18002de58  mov     [rsp+1F0h+var_184], ax
0x18002de5d  mov     eax, [rsp+1F0h+var_190]
0x18002de61  and     eax, 1A30A7h
0x18002de66  mov     r14d, 80h
0x18002de6c  cmovz   eax, r14d
0x18002de70  mov     [rbp+0F0h+var_AC+0Ch], eax
0x18002de73  lea     rdx, aNtfs; "NTFS"
0x18002de7a  mov     rcx, rsi; String1
0x18002de7d  call    cs:__imp__wcsicmp
0x18002de83  xor     ecx, ecx
0x18002de85  test    eax, eax
0x18002de87  setz    cl
0x18002de8a  xor     edx, edx
0x18002de8c  cmp     dword ptr [r13+38h], 0Bh
0x18002de91  cmovnz  edx, ecx
0x18002de94  movzx   eax, [rbp+0F0h+ShortName]
0x18002de9b  neg     ax
0x18002de9e  sbb     eax, eax
0x18002dea0  and     eax, edx
0x18002dea2  mov     [rbp+0F0h+var_150], eax
0x18002dea5  add     eax, 0C000h
0x18002deaa  shl     eax, 10h
0x18002dead  mov     edi, eax
0x18002deaf  or      edi, 1080000h
0x18002deb5  cmp     dword ptr [r13+38h], 0Bh
0x18002deba  cmovz   edi, eax
0x18002debd  xor     r9d, r9d
0x18002dec0  xor     r8d, r8d
0x18002dec3  lea     rdx, [rbp+0F0h+P]
0x18002dec7  mov     rcx, r15
0x18002deca  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x18002ded0  mov     ecx, eax
0x18002ded2  call    HRESULTFromNTSTATUS
0x18002ded7  mov     [rsp+1F0h+var_188], eax
0x18002dedb  test    eax, eax
0x18002dedd  mov     eax, 10DBh
0x18002dee2  js      loc_18002DCB4
0x18002dee8  mov     [rsp+1F0h+var_184], ax
0x18002deed  mov     [rbp+0F0h+ObjectAttributes.Length], 30h ; '0'
0x18002def4  mov     [rbp+0F0h+ObjectAttributes.RootDirectory], 0
0x18002defc  mov     [rbp+0F0h+ObjectAttributes.Attributes], 40h ; '@'
0x18002df03  lea     rax, [rbp+0F0h+P]
0x18002df07  mov     [rbp+0F0h+ObjectAttributes.ObjectName], rax
0x18002df0b  mov     [rbp+0F0h+ObjectAttributes.SecurityDescriptor], r12
0x18002df0f  mov     [rbp+0F0h+ObjectAttributes.SecurityQualityOfService], 0
0x18002df17  or      edi, 140001h
0x18002df1d  mov     [rsp+1F0h+EaLength], 0; EaLength
0x18002df25  mov     [rsp+1F0h+EaBuffer], 0; EaBuffer
0x18002df2e  mov     [rsp+1F0h+CreateOptions], 4021h; CreateOptions
0x18002df36  mov     [rsp+1F0h+CreateDisposition], 2; CreateDisposition
0x18002df3e  mov     [rsp+1F0h+ShareAccess], 3; ShareAccess
0x18002df46  mov     eax, [rbp+0F0h+var_AC+0Ch]
0x18002df49  mov     [rsp+1F0h+FileAttributes], eax; FileAttributes
0x18002df4d  mov     [rsp+1F0h+AllocationSize], 0; AllocationSize
0x18002df56  lea     r9, [rbp+0F0h+IoStatusBlock]; IoStatusBlock
0x18002df5a  lea     r8, [rbp+0F0h+ObjectAttributes]; ObjectAttributes
0x18002df5e  mov     edx, edi; DesiredAccess
0x18002df60  lea     rcx, [rbp+0F0h+FileHandle]; FileHandle
0x18002df64  call    cs:__imp_NtCreateFile
0x18002df6a  test    eax, eax
0x18002df6c  jns     short loc_18002DF87
0x18002df6e  mov     ecx, eax
0x18002df70  call    HRESULTFromNTSTATUS
0x18002df75  mov     [rsp+1F0h+var_188], eax
0x18002df79  test    eax, eax
0x18002df7b  jns     short loc_18002DF87
0x18002df7d  mov     eax, 10EEh
0x18002df82  jmp     loc_18002DCB4
0x18002df87  mov     rbx, [rbp+0F0h+FileHandle]
0x18002df8b  mov     [rbp+0F0h+FileHandle], 0FFFFFFFFFFFFFFFFh
0x18002df93  mov     [rsp+1F0h+var_188], 0
0x18002df9b  mov     eax, 10F1h
0x18002dfa0  mov     [rsp+1F0h+var_184], ax
0x18002dfa5  mov     [rbp+0F0h+var_128], r15
0x18002dfa9  lea     rax, [rbp+0F0h+var_128]
0x18002dfad  mov     [rsp+1F0h+AllocationSize], rax; unsigned __int16 **
0x18002dfb2  mov     r13d, 1
0x18002dfb8  mov     r9d, r13d; unsigned int
0x18002dfbb  mov     r8d, 4E8Dh; unsigned int
0x18002dfc1  mov     rdx, cs:hInstance; HINSTANCE
0x18002dfc8  lea     rcx, [rsp+1F0h+var_188]; this
0x18002dfcd  call    ?_SetContextHelper@CSxFunctionTracer@@AEAAJPEAUHINSTANCE__@@KKPEAPEBG@Z; CSxFunctionTracer::_SetContextHelper(HINSTANCE__ *,ulong,ulong,ushort const * *)
0x18002dfd2  mov     [rsp+1F0h+var_188], eax
0x18002dfd6  test    eax, eax
0x18002dfd8  mov     eax, 10F2h
0x18002dfdd  js      loc_18002DCB4
0x18002dfe3  mov     [rsp+1F0h+var_184], ax
0x18002dfe8  lea     rdi, WPP_GLOBAL_Control
0x18002dfef  lea     rsi, WPP_052bc5b66f273e09fada3dec80af9ee3_Traceguids
0x18002dff6  mov     rcx, cs:WPP_GLOBAL_Control
0x18002dffd  cmp     rcx, rdi
0x18002e000  jz      short loc_18002E01B
0x18002e002  test    [rcx+1Ch], r14b
0x18002e006  jz      short loc_18002E01B
0x18002e008  lea     edx, [r13+56h]
0x18002e00c  mov     r9, r15
0x18002e00f  mov     r8, rsi
0x18002e012  mov     rcx, [rcx+10h]
0x18002e016  call    WPP_SF_S
0x18002e01b  mov     dword ptr [rsp+1F0h+AllocationSize], 4; FileInformationClass
0x18002e023  mov     r9d, 28h ; '('; Length
0x18002e029  lea     r8, [rbp+0F0h+FileInformation]; FileInformation
0x18002e02d  lea     rdx, [rbp+0F0h+IoStatusBlock]; IoStatusBlock
0x18002e031  mov     rcx, rbx; FileHandle
0x18002e034  call    cs:__imp_NtQueryInformationFile
0x18002e03a  mov     ecx, eax
0x18002e03c  call    HRESULTFromNTSTATUS
0x18002e041  mov     [rsp+1F0h+var_188], eax
0x18002e045  test    eax, eax
0x18002e047  mov     eax, 10FFh
0x18002e04c  js      loc_18002DCB4
0x18002e052  mov     [rsp+1F0h+var_184], ax
0x18002e057  test    r12, r12
0x18002e05a  jz      loc_18002E12F
0x18002e060  lea     r9, [rbp+0F0h+bDaclDefaulted]; lpbDaclDefaulted
0x18002e064  lea     r8, [rbp+0F0h+pDacl]; pDacl
0x18002e068  lea     rdx, [rbp+0F0h+bDaclPresent]; lpbDaclPresent
0x18002e06c  mov     rcx, r12; pSecurityDescriptor
0x18002e06f  call    cs:__imp_GetSecurityDescriptorDacl
0x18002e075  test    eax, eax
0x18002e077  jnz     short loc_18002E08C
0x18002e079  call    GetLastFailureAsHRESULT
0x18002e07e  mov     [rsp+1F0h+var_188], eax
0x18002e082  mov     eax, 1103h
0x18002e087  jmp     loc_18002DCB4
0x18002e08c  mov     [rsp+1F0h+var_188], 0
0x18002e094  mov     eax, 1103h
0x18002e099  mov     [rsp+1F0h+var_184], ax
0x18002e09e  lea     r9, [rbp+0F0h+bSaclDefaulted]; lpbSaclDefaulted
0x18002e0a2  lea     r8, [rbp+0F0h+pSacl]; pSacl
0x18002e0a6  lea     rdx, [rbp+0F0h+bSaclPresent]; lpbSaclPresent
0x18002e0aa  mov     rcx, r12; pSecurityDescriptor
0x18002e0ad  call    cs:__imp_GetSecurityDescriptorSacl
0x18002e0b3  test    eax, eax
0x18002e0b5  jnz     short loc_18002E0CA
0x18002e0b7  call    GetLastFailureAsHRESULT
0x18002e0bc  mov     [rsp+1F0h+var_188], eax
0x18002e0c0  mov     eax, 1104h
0x18002e0c5  jmp     loc_18002DCB4
0x18002e0ca  xor     edx, edx
  ... truncated ...
```
