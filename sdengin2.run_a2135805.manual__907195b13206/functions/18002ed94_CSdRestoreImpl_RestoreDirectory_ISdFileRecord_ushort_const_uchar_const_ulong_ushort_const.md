# CSdRestoreImpl::_RestoreDirectory(ISdFileRecord *,ushort const *,uchar const *,ulong,ushort const *)

- ea: `0x18002ed94`
- end: `0x18002f759`
- name: `?_RestoreDirectory@CSdRestoreImpl@@AEAAJPEAUISdFileRecord@@PEBGPEBEK1@Z`
- size: `2501`
- prototype: `int(CSdRestoreImpl *__hidden this, struct ISdFileRecord *, const unsigned __int16 *, const unsigned __int8 *, unsigned int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002e620`

## callees

- `0x180008370`
- `0x1800083a0`
- `0x1800083e4`
- `0x180014c30`
- `0x18002ed94`
- `0x18002f760`
- `0x18002f8e4`
- `0x180072e08`
- `0x180072f14`
- `0x18007351c`
- `0x1800935fc`
- `0x180093698`
- `0x18009c770`
- `0x1800cf5c0`
- `0x1800d1010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18002f055`
- `msvcrt!_wcsicmp` at `0x18002f055`
- `ntdll!NtSetInformationFile` at `0x18002f567`
- `ntdll!NtSetInformationFile` at `0x18002f567`
- `ntdll!NtQueryInformationFile` at `0x18002f21e`
- `ntdll!NtQueryInformationFile` at `0x18002f21e`
- `ntdll!NtCreateFile` at `0x18002f148`
- `ntdll!NtCreateFile` at `0x18002f148`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x18002f0a8`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x18002f0a8`
- `ntdll!RtlFreeHeap` at `0x18002f6d6`
- `ntdll!RtlFreeHeap` at `0x18002f6d6`
- `KERNEL32!GetLastError` at `0x18002f310`
- `KERNEL32!GetLastError` at `0x18002f4f8`
- `KERNEL32!GetLastError` at `0x18002f310`
- `KERNEL32!GetLastError` at `0x18002f4f8`
- `KERNEL32!CloseHandle` at `0x18002f59d`
- `KERNEL32!CloseHandle` at `0x18002f6f8`
- `KERNEL32!CloseHandle` at `0x18002f71d`
- `KERNEL32!CloseHandle` at `0x18002f59d`
- `KERNEL32!CloseHandle` at `0x18002f6f8`
- `KERNEL32!CloseHandle` at `0x18002f71d`
- `KERNEL32!DeviceIoControl` at `0x18002f474`
- `KERNEL32!DeviceIoControl` at `0x18002f474`
- `KERNEL32!SetFileShortNameW` at `0x18002f4e8`
- `KERNEL32!SetFileShortNameW` at `0x18002f4e8`
- `api-ms-win-security-base-l1-1-0!SetKernelObjectSecurity` at `0x18002f2ee`
- `api-ms-win-security-base-l1-1-0!SetKernelObjectSecurity` at `0x18002f2ee`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18002f25f`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18002f25f`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x18002f2a3`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x18002f2a3`
- `ext-ms-win-advapi32-encryptedfile-l1-1-0!EncryptFileW` at `0x18002f612`
- `ext-ms-win-advapi32-encryptedfile-l1-1-0!EncryptFileW` at `0x18002f612`
- `ext-ms-win-advapi32-encryptedfile-l1-1-0!DecryptFileW` at `0x18002f63e`
- `ext-ms-win-advapi32-encryptedfile-l1-1-0!DecryptFileW` at `0x18002f63e`

## string_xrefs

- `0x18002ede0`: `CSdRestoreImpl::_RestoreDirectory`

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
  __int64 v13; // r9
  int v14; // ecx
  __int16 v15; // ax
  bool v16; // cc
  int v17; // eax
  BOOL v18; // ecx
  BOOL v19; // edx
  int v20; // edi
  unsigned int v21; // eax
  NTSTATUS v22; // eax
  unsigned int v23; // eax
  __int64 v24; // r9
  __int64 v25; // rcx
  __int64 v26; // rcx
  SECURITY_INFORMATION v27; // edx
  PVOID *v28; // rcx
  DWORD LastError; // eax
  unsigned int v30; // r8d
  __int64 v31; // r9
  int v32; // r13d
  unsigned int v33; // edx
  PVOID *v34; // rcx
  __int64 v35; // rcx
  __int64 v36; // rcx
  unsigned int v37; // eax
  CSdRestoreImpl *v38; // rcx
  unsigned __int16 v39; // dx
  int v40; // eax
  __int16 v41; // ax
  int v42; // eax
  unsigned int v43; // edi
  unsigned int v45; // [rsp+60h] [rbp-A0h] BYREF
  __int16 InBuffer; // [rsp+64h] [rbp-9Ch] BYREF
  int LastFailureAsHRESULT; // [rsp+68h] [rbp-98h] BYREF
  __int16 v48; // [rsp+6Ch] [rbp-94h]
  __int16 v49; // [rsp+6Eh] [rbp-92h]
  BOOL v50; // [rsp+A0h] [rbp-60h]
  WINBOOL bDaclPresent; // [rsp+A4h] [rbp-5Ch] BYREF
  WINBOOL bSaclPresent; // [rsp+A8h] [rbp-58h] BYREF
  void *FileHandle; // [rsp+B0h] [rbp-50h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+B8h] [rbp-48h] BYREF
  WINBOOL bSaclDefaulted; // [rsp+BCh] [rbp-44h] BYREF
  DWORD BytesReturned; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 *v57; // [rsp+C8h] [rbp-38h] BYREF
  PVOID P[2]; // [rsp+D0h] [rbp-30h] BYREF
  PACL pDacl; // [rsp+E0h] [rbp-20h] BYREF
  PACL pSacl; // [rsp+E8h] [rbp-18h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+F0h] [rbp-10h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+100h] [rbp+0h] BYREF
  int v63; // [rsp+130h] [rbp+30h] BYREF
  __int128 v64; // [rsp+134h] [rbp+34h] BYREF
  ULONG FileAttributes[4]; // [rsp+144h] [rbp+44h]
  int v66; // [rsp+154h] [rbp+54h]
  int FileInformation; // [rsp+158h] [rbp+58h] BYREF
  __int128 v68; // [rsp+15Ch] [rbp+5Ch]
  __int128 v69; // [rsp+16Ch] [rbp+6Ch]
  int v70; // [rsp+17Ch] [rbp+7Ch]
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
  v45 = 0;
  v50 = 0;
  *(_OWORD *)P = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  IoStatusBlock = 0;
  FileHandle = (void *)-1LL;
  v63 = 0;
  v64 = 0;
  *(_OWORD *)FileAttributes = 0;
  v66 = 0;
  pDacl = 0;
  pSacl = 0;
  bDaclPresent = 0;
  bSaclPresent = 0;
  bDaclDefaulted = 0;
  bSaclDefaulted = 0;
  FileInformation = 0;
  v68 = 0;
  v69 = 0;
  v70 = 0;
  v11 = 4249;
  if ( !a2 || (v48 = 4249, v11 = 4250, !a3) || (v48 = 4250, v11 = 4251, !String1) )
  {
    LastFailureAsHRESULT = -2147024809;
LABEL_3:
    v49 = v11;
    goto LABEL_103;
  }
  LastFailureAsHRESULT = 0;
  v48 = 4251;
  FileAttributesTag = GetFileAttributesTag(a3);
  v14 = FileAttributesTag;
  if ( FileAttributesTag < 0 )
  {
    v16 = (unsigned int)(FileAttributesTag + 2147024894) <= 1;
    v11 = 4266;
    if ( !v16 )
    {
      LastFailureAsHRESULT = v14;
      goto LABEL_3;
    }
    LastFailureAsHRESULT = 0;
    v48 = 4266;
    LastFailureAsHRESULT = (*(__int64 (__fastcall **)(struct ISdFileRecord *, unsigned int *))(*(_QWORD *)a2 + 128LL))(
                             a2,
                             &v45);
    v11 = 4268;
    if ( LastFailureAsHRESULT < 0 )
      goto LABEL_3;
    v48 = 4268;
    LastFailureAsHRESULT = (*(__int64 (__fastcall **)(struct ISdFileRecord *, int *))(*(_QWORD *)a2 + 64LL))(a2, &v63);
    v11 = 4269;
    if ( LastFailureAsHRESULT < 0 )
      goto LABEL_3;
    v48 = 4269;
    LastFailureAsHRESULT = (*(__int64 (__fastcall **)(struct ISdFileRecord *, char *))(*(_QWORD *)a2 + 120LL))(
                             a2,
                             (char *)&v64 + 4);
    v11 = 4270;
    if ( LastFailureAsHRESULT < 0 )
      goto LABEL_3;
    v48 = 4270;
    LastFailureAsHRESULT = (*(__int64 (__fastcall **)(struct ISdFileRecord *, char *))(*(_QWORD *)a2 + 72LL))(
                             a2,
                             (char *)&v64 + 12);
    v11 = 4271;
    if ( LastFailureAsHRESULT < 0 )
      goto LABEL_3;
    v48 = 4271;
    LastFailureAsHRESULT = (*(__int64 (__fastcall **)(struct ISdFileRecord *, WCHAR *))(*(_QWORD *)a2 + 40LL))(
                             a2,
                             ShortName);
    v11 = 4272;
    if ( LastFailureAsHRESULT < 0 )
      goto LABEL_3;
    v48 = 4272;
    v17 = v45 & 0x1A30A7;
    if ( (v45 & 0x1A30A7) == 0 )
      v17 = 128;
    FileAttributes[3] = v17;
    v18 = _wcsicmp(String1, L"NTFS") == 0;
    v19 = 0;
    if ( *((_DWORD *)this + 14) != 11 )
      v19 = v18;
    v50 = ShortName[0] != 0 && v19;
    v20 = ((v50 + 49152) << 16) | 0x1080000;
    if ( *((_DWORD *)this + 14) == 11 )
      v20 = (v50 + 49152) << 16;
    v21 = RtlDosPathNameToNtPathName_U_WithStatus(a3, P, 0, 0);
    LastFailureAsHRESULT = HRESULTFromNTSTATUS(v21);
    v11 = 4315;
    if ( LastFailureAsHRESULT < 0 )
      goto LABEL_3;
    v48 = 4315;
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 64;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)P;
    ObjectAttributes.SecurityDescriptor = a4;
    ObjectAttributes.SecurityQualityOfService = 0;
    v22 = NtCreateFile(
            &FileHandle,
            v20 | 0x140001,
            &ObjectAttributes,
            &IoStatusBlock,
            0,
            FileAttributes[3],
            3u,
            2u,
            0x4021u,
            0,
            0);
    if ( v22 < 0 )
    {
      LastFailureAsHRESULT = HRESULTFromNTSTATUS((unsigned int)v22);
      if ( LastFailureAsHRESULT < 0 )
      {
        v11 = 4334;
        goto LABEL_3;
      }
    }
    v10 = (__int64)FileHandle;
    FileHandle = (void *)-1LL;
    LastFailureAsHRESULT = 0;
    v48 = 4337;
    v57 = a3;
    LastFailureAsHRESULT = CSxFunctionTracer::_SetContextHelper(
                             (CSxFunctionTracer *)&LastFailureAsHRESULT,
                             hInstance,
                             0x4E8Du,
                             1u,
                             (const unsigned __int16 **)&v57);
    v11 = 4338;
    if ( LastFailureAsHRESULT < 0 )
      goto LABEL_3;
    v48 = 4338;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x80) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 87, &WPP_052bc5b66f273e09fada3dec80af9ee3_Traceguids, a3);
    v23 = NtQueryInformationFile((HANDLE)v10, &IoStatusBlock, &FileInformation, 0x28u, FileBasicInformation);
    LastFailureAsHRESULT = HRESULTFromNTSTATUS(v23);
    v11 = 4351;
    if ( LastFailureAsHRESULT < 0 )
      goto LABEL_3;
    v48 = 4351;
    if ( a4 )
    {
      if ( !GetSecurityDescriptorDacl(a4, &bDaclPresent, &pDacl, &bDaclDefaulted) )
      {
        LastFailureAsHRESULT = GetLastFailureAsHRESULT(v25);
        v11 = 4355;
        goto LABEL_3;
      }
      LastFailureAsHRESULT = 0;
      v48 = 4355;
      if ( !GetSecurityDescriptorSacl(a4, &bSaclPresent, &pSacl, &bSaclDefaulted) )
      {
        LastFailureAsHRESULT = GetLastFailureAsHRESULT(v26);
        v11 = 4356;
        goto LABEL_3;
      }
      v27 = 0;
      LastFailureAsHRESULT = 0;
      v48 = 4356;
      if ( bDaclPresent )
        v27 = 4;
      if ( bSaclPresent )
        v27 |= 0x18u;
      if ( !SetKernelObjectSecurity((HANDLE)v10, v27, a4) )
      {
        v28 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x80) == 0 )
          goto LABEL_49;
        LastError = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 88, &WPP_052bc5b66f273e09fada3dec80af9ee3_Traceguids, LastError);
      }
    }
    v28 = (PVOID *)WPP_GLOBAL_Control;
LABEL_49:
    v30 = v45;
    if ( (v45 & 0x4000) != 0 && (a5 & 0x20000) == 0 )
    {
      if ( v28 != &WPP_GLOBAL_Control && (*((_BYTE *)v28 + 28) & 0x80) != 0 )
      {
        WPP_SF_(v28[2], 89, &WPP_052bc5b66f273e09fada3dec80af9ee3_Traceguids, v24);
        v30 = v45;
      }
      v45 = v30 & 0xFFFFBFFF;
    }
    v57 = a3;
    LastFailureAsHRESULT = CSxFunctionTracer::_SetContextHelper(
                             (CSxFunctionTracer *)&LastFailureAsHRESULT,
                             hInstance,
                             0x4E8Eu,
                             1u,
                             (const unsigned __int16 **)&v57);
    v11 = 4385;
    if ( LastFailureAsHRESULT < 0 )
      goto LABEL_3;
    v32 = 0;
    v48 = 4385;
    v33 = v45;
    if ( (v45 & 0x800) != 0 && (a5 & 0x10) == 0 )
    {
      v34 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x80) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 90, &WPP_052bc5b66f273e09fada3dec80af9ee3_Traceguids, v31);
        v33 = v45;
        v34 = (PVOID *)WPP_GLOBAL_Control;
      }
      v33 &= ~0x800u;
      v45 = v33;
    }
    else
    {
      v34 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( (((unsigned __int16)v33 ^ WORD6(v69)) & 0x800) != 0 )
    {
      if ( (WORD6(v69) & 0x4000) != 0 )
      {
        if ( v34 != &WPP_GLOBAL_Control && (*((_BYTE *)v34 + 28) & 0x80) != 0 )
        {
          WPP_SF_(v34[2], 91, &WPP_052bc5b66f273e09fada3dec80af9ee3_Traceguids, v31);
          v34 = (PVOID *)WPP_GLOBAL_Control;
        }
        v32 = 1;
      }
      else
      {
        InBuffer = (v33 & 0x800) != 0;
        if ( !DeviceIoControl((HANDLE)v10, 0x9C040u, &InBuffer, 2u, 0, 0, &BytesReturned, 0) )
        {
          LastFailureAsHRESULT = GetLastFailureAsHRESULT(v35);
          v11 = 4450;
          goto LABEL_3;
        }
        LastFailureAsHRESULT = 0;
        v48 = 4450;
        v34 = (PVOID *)WPP_GLOBAL_Control;
      }
    }
    if ( v50 )
    {
      if ( !SetFileShortNameW((HANDLE)v10, ShortName) )
      {
        if ( GetLastError() != 183 )
        {
          LastFailureAsHRESULT = GetLastFailureAsHRESULT(v36);
          v11 = 4471;
          goto LABEL_3;
        }
        LastFailureAsHRESULT = 0;
        v48 = 4471;
      }
    }
    else if ( v34 != &WPP_GLOBAL_Control && (*((_BYTE *)v34 + 28) & 0x80) != 0 )
    {
      WPP_SF_(v34[2], 92, &WPP_052bc5b66f273e09fada3dec80af9ee3_Traceguids, v31);
    }
    v37 = NtSetInformationFile((HANDLE)v10, &IoStatusBlock, &v63, 0x28u, FileBasicInformation);
    LastFailureAsHRESULT = HRESULTFromNTSTATUS(v37);
    v11 = 4483;
    if ( LastFailureAsHRESULT < 0 )
      goto LABEL_3;
    v48 = 4483;
    if ( (unsigned __int64)(v10 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      CloseHandle((HANDLE)v10);
      v10 = -1;
    }
    v39 = v45;
    LOBYTE(v38) = (v45 & 0x100) != 0;
    if ( ((unsigned __int8)v38 & ((a5 & 0x40000) != 0)) != 0 )
    {
      v40 = CSdRestoreImpl::_RestoreDirectoryTempAttribute(v38, a3);
      if ( v40 < 0 )
      {
        v38 = (CSdRestoreImpl *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x80) != 0 )
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            93,
            (unsigned int)&WPP_052bc5b66f273e09fada3dec80af9ee3_Traceguids,
            (_DWORD)a3,
            v40);
      }
      v39 = v45;
    }
    if ( ((v39 ^ WORD6(v69)) & 0x4000) != 0 )
    {
      if ( (v39 & 0x4000) != 0 )
      {
        if ( !EncryptFileW(a3) )
        {
          LastFailureAsHRESULT = GetLastFailureAsHRESULT(v38);
          v11 = 4519;
          goto LABEL_3;
        }
        v41 = 4519;
      }
      else
      {
        if ( !DecryptFileW(a3, 0) )
        {
          LastFailureAsHRESULT = GetLastFailureAsHRESULT(v38);
          v11 = 4523;
          goto LABEL_3;
        }
        v41 = 4523;
      }
      v48 = v41;
      LastFailureAsHRESULT = 0;
    }
    if ( v32 )
    {
      v42 = CSdRestoreImpl::_RestoreDirectoryCompression(v38, a3);
      if ( v42 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x80) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          94,
          &WPP_052bc5b66f273e09fada3dec80af9ee3_Traceguids,
          (unsigned int)v42);
    }
    LastFailureAsHRESULT = 0;
    v15 = 4553;
    goto LABEL_102;
  }
  v11 = 4258;
  if ( (v50 & 0x10) == 0 )
  {
    LastFailureAsHRESULT = -2147024891;
    goto LABEL_3;
  }
  LastFailureAsHRESULT = 0;
  v48 = 4258;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 86, &WPP_052bc5b66f273e09fada3dec80af9ee3_Traceguids, v13);
  LastFailureAsHRESULT = 1;
  v15 = 4262;
LABEL_102:
  v48 = v15;
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
  v43 = LastFailureAsHRESULT;
  if ( (unsigned __int64)(v10 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)v10);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT);
  return v43;
}

```

## disassembly

```asm
0x18002ed94  push    rbp
0x18002ed96  push    rbx
0x18002ed97  push    rsi
0x18002ed98  push    rdi
0x18002ed99  push    r12
0x18002ed9b  push    r13
0x18002ed9d  push    r14
0x18002ed9f  push    r15
0x18002eda1  lea     rbp, [rsp-0B8h]
0x18002eda9  sub     rsp, 1B8h
0x18002edb0  mov     rax, cs:__security_cookie
0x18002edb7  xor     rax, rsp
0x18002edba  mov     [rbp+0F0h+var_50], rax
0x18002edc1  mov     r12, r9
0x18002edc4  mov     r15, r8
0x18002edc7  mov     rdi, rdx
0x18002edca  mov     r13, rcx
0x18002edcd  mov     rsi, [rbp+0F0h+String1]
0x18002edd4  mov     r9d, 1; unsigned __int16
0x18002edda  mov     r8d, 107Fh; unsigned __int16
0x18002ede0  lea     rdx, aCsdrestoreimpl_51; "CSdRestoreImpl::_RestoreDirectory"
0x18002ede7  lea     rcx, [rsp+1F0h+var_188]; this
0x18002edec  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18002edf1  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18002edf5  mov     rbx, rcx
0x18002edf8  xor     r14d, r14d
0x18002edfb  mov     [rbp+0F0h+BytesReturned], r14d
0x18002edff  mov     [rsp+1F0h+InBuffer], r14w
0x18002ee05  mov     [rbp+0F0h+ShortName], r14w
0x18002ee0d  xorps   xmm0, xmm0
0x18002ee10  xor     eax, eax
0x18002ee12  movups  xmmword ptr [rbp+0F0h+var_6E], xmm0
0x18002ee19  movups  xmmword ptr [rbp+0F0h+var_6E+0Ah], xmm0
0x18002ee20  mov     [rsp+1F0h+var_190], r14d
0x18002ee25  mov     [rbp+0F0h+var_150], r14d
0x18002ee29  movups  xmmword ptr [rbp+0F0h+P], xmm0
0x18002ee2d  xorps   xmm1, xmm1
0x18002ee30  movups  xmmword ptr [rbp+0F0h+ObjectAttributes.Length], xmm1
0x18002ee34  movups  xmmword ptr [rbp+0F0h+ObjectAttributes.ObjectName], xmm1
0x18002ee38  movups  xmmword ptr [rbp+0F0h+ObjectAttributes.SecurityDescriptor], xmm1
0x18002ee3c  movups  xmmword ptr [rbp+0F0h+IoStatusBlock], xmm0
0x18002ee40  mov     [rbp+0F0h+FileHandle], rcx
0x18002ee44  mov     [rbp+0F0h+var_C0], r14d
0x18002ee48  movups  [rbp+0F0h+var_BC], xmm0
0x18002ee4c  movups  xmmword ptr [rbp+0F0h+var_AC], xmm0
0x18002ee50  mov     [rbp+0F0h+var_9C], eax
0x18002ee53  mov     [rbp+0F0h+pDacl], r14
0x18002ee57  mov     [rbp+0F0h+pSacl], r14
0x18002ee5b  mov     [rbp+0F0h+bDaclPresent], r14d
0x18002ee5f  mov     [rbp+0F0h+bSaclPresent], r14d
0x18002ee63  mov     [rbp+0F0h+bDaclDefaulted], r14d
0x18002ee67  mov     [rbp+0F0h+bSaclDefaulted], r14d
0x18002ee6b  mov     [rbp+0F0h+FileInformation], r14d
0x18002ee6f  movups  [rbp+0F0h+var_94], xmm0
0x18002ee73  movups  [rbp+0F0h+var_84], xmm0
0x18002ee77  mov     [rbp+0F0h+var_74], eax
0x18002ee7a  mov     eax, 1099h
0x18002ee7f  test    rdi, rdi
0x18002ee82  jnz     short loc_18002EE96
0x18002ee84  mov     [rsp+1F0h+var_188], 80070057h
0x18002ee8c  mov     [rsp+1F0h+var_182], ax
0x18002ee91  jmp     loc_18002F6BC
0x18002ee96  mov     [rsp+1F0h+var_184], ax
0x18002ee9b  mov     eax, 109Ah
0x18002eea0  test    r15, r15
0x18002eea3  jz      short loc_18002EE84
0x18002eea5  mov     [rsp+1F0h+var_184], ax
0x18002eeaa  mov     eax, 109Bh
0x18002eeaf  test    rsi, rsi
0x18002eeb2  jz      short loc_18002EE84
0x18002eeb4  mov     [rsp+1F0h+var_188], r14d
0x18002eeb9  mov     [rsp+1F0h+var_184], ax
0x18002eebe  xor     r9d, r9d
0x18002eec1  xor     r8d, r8d
0x18002eec4  lea     rdx, [rbp+0F0h+var_150]
0x18002eec8  mov     rcx, r15; lpFileName
0x18002eecb  call    _GetFileAttributesTag
0x18002eed0  mov     ecx, eax
0x18002eed2  test    eax, eax
0x18002eed4  js      short loc_18002EF3B
0x18002eed6  mov     eax, 10A2h
0x18002eedb  test    byte ptr [rbp+0F0h+var_150], 10h
0x18002eedf  jnz     short loc_18002EEEB
0x18002eee1  mov     [rsp+1F0h+var_188], 80070005h
0x18002eee9  jmp     short loc_18002EE8C
0x18002eeeb  mov     [rsp+1F0h+var_188], r14d
0x18002eef0  mov     [rsp+1F0h+var_184], ax
0x18002eef5  lea     rdi, WPP_GLOBAL_Control
0x18002eefc  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ef03  cmp     rcx, rdi
0x18002ef06  jz      short loc_18002EF28
0x18002ef08  mov     r14d, 80h
0x18002ef0e  test    [rcx+1Ch], r14b
0x18002ef12  jz      short loc_18002EF28
0x18002ef14  lea     edx, [r14-2Ah]
0x18002ef18  lea     r8, WPP_052bc5b66f273e09fada3dec80af9ee3_Traceguids
0x18002ef1f  mov     rcx, [rcx+10h]
0x18002ef23  call    WPP_SF_
0x18002ef28  mov     edx, 1
0x18002ef2d  mov     [rsp+1F0h+var_188], edx
0x18002ef31  mov     eax, 10A6h
0x18002ef36  jmp     loc_18002F6B7
0x18002ef3b  add     eax, 7FF8FFFEh
0x18002ef40  mov     edx, 1
0x18002ef45  cmp     eax, edx
0x18002ef47  mov     eax, 10AAh
0x18002ef4c  jbe     short loc_18002EF57
0x18002ef4e  mov     [rsp+1F0h+var_188], ecx
0x18002ef52  jmp     loc_18002EE8C
0x18002ef57  mov     [rsp+1F0h+var_188], r14d
0x18002ef5c  mov     [rsp+1F0h+var_184], ax
0x18002ef61  mov     rax, [rdi]
0x18002ef64  lea     rdx, [rsp+1F0h+var_190]
0x18002ef69  mov     rcx, rdi
0x18002ef6c  mov     rax, [rax+80h]
0x18002ef73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ef78  mov     [rsp+1F0h+var_188], eax
0x18002ef7c  test    eax, eax
0x18002ef7e  mov     eax, 10ACh
0x18002ef83  js      loc_18002EE8C
0x18002ef89  mov     [rsp+1F0h+var_184], ax
0x18002ef8e  mov     rax, [rdi]
0x18002ef91  lea     rdx, [rbp+0F0h+var_C0]
0x18002ef95  mov     rcx, rdi
0x18002ef98  mov     rax, [rax+40h]
0x18002ef9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002efa1  mov     [rsp+1F0h+var_188], eax
0x18002efa5  test    eax, eax
0x18002efa7  mov     eax, 10ADh
0x18002efac  js      loc_18002EE8C
0x18002efb2  mov     [rsp+1F0h+var_184], ax
0x18002efb7  mov     rax, [rdi]
0x18002efba  lea     rdx, [rbp+0F0h+var_BC+4]
0x18002efbe  mov     rcx, rdi
0x18002efc1  mov     rax, [rax+78h]
0x18002efc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002efca  mov     [rsp+1F0h+var_188], eax
0x18002efce  test    eax, eax
0x18002efd0  mov     eax, 10AEh
0x18002efd5  js      loc_18002EE8C
0x18002efdb  mov     [rsp+1F0h+var_184], ax
0x18002efe0  mov     rax, [rdi]
0x18002efe3  lea     rdx, [rbp+0F0h+var_BC+0Ch]
0x18002efe7  mov     rcx, rdi
0x18002efea  mov     rax, [rax+48h]
0x18002efee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eff3  mov     [rsp+1F0h+var_188], eax
0x18002eff7  test    eax, eax
0x18002eff9  mov     eax, 10AFh
0x18002effe  js      loc_18002EE8C
0x18002f004  mov     [rsp+1F0h+var_184], ax
0x18002f009  mov     rax, [rdi]
0x18002f00c  lea     rdx, [rbp+0F0h+ShortName]
0x18002f013  mov     rcx, rdi
0x18002f016  mov     rax, [rax+28h]
0x18002f01a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f01f  mov     [rsp+1F0h+var_188], eax
0x18002f023  test    eax, eax
0x18002f025  mov     eax, 10B0h
0x18002f02a  js      loc_18002EE8C
0x18002f030  mov     [rsp+1F0h+var_184], ax
0x18002f035  mov     eax, [rsp+1F0h+var_190]
0x18002f039  and     eax, 1A30A7h
0x18002f03e  mov     r14d, 80h
0x18002f044  cmovz   eax, r14d
0x18002f048  mov     [rbp+0F0h+var_AC+0Ch], eax
0x18002f04b  lea     rdx, aNtfs; "NTFS"
0x18002f052  mov     rcx, rsi; String1
0x18002f055  call    cs:__imp__wcsicmp
0x18002f05c  nop     dword ptr [rax+rax+00h]
0x18002f061  xor     ecx, ecx
0x18002f063  test    eax, eax
0x18002f065  setz    cl
0x18002f068  xor     edx, edx
0x18002f06a  cmp     dword ptr [r13+38h], 0Bh
0x18002f06f  cmovnz  edx, ecx
0x18002f072  movzx   eax, [rbp+0F0h+ShortName]
0x18002f079  neg     ax
0x18002f07c  sbb     eax, eax
0x18002f07e  and     eax, edx
0x18002f080  mov     [rbp+0F0h+var_150], eax
0x18002f083  add     eax, 0C000h
0x18002f088  shl     eax, 10h
0x18002f08b  mov     edi, eax
0x18002f08d  or      edi, 1080000h
0x18002f093  cmp     dword ptr [r13+38h], 0Bh
0x18002f098  cmovz   edi, eax
0x18002f09b  xor     r9d, r9d
0x18002f09e  xor     r8d, r8d
0x18002f0a1  lea     rdx, [rbp+0F0h+P]
0x18002f0a5  mov     rcx, r15
0x18002f0a8  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x18002f0af  nop     dword ptr [rax+rax+00h]
0x18002f0b4  mov     ecx, eax
0x18002f0b6  call    HRESULTFromNTSTATUS
0x18002f0bb  mov     [rsp+1F0h+var_188], eax
0x18002f0bf  test    eax, eax
0x18002f0c1  mov     eax, 10DBh
0x18002f0c6  js      loc_18002EE8C
0x18002f0cc  mov     [rsp+1F0h+var_184], ax
0x18002f0d1  mov     [rbp+0F0h+ObjectAttributes.Length], 30h ; '0'
0x18002f0d8  mov     [rbp+0F0h+ObjectAttributes.RootDirectory], 0
0x18002f0e0  mov     [rbp+0F0h+ObjectAttributes.Attributes], 40h ; '@'
0x18002f0e7  lea     rax, [rbp+0F0h+P]
0x18002f0eb  mov     [rbp+0F0h+ObjectAttributes.ObjectName], rax
0x18002f0ef  mov     [rbp+0F0h+ObjectAttributes.SecurityDescriptor], r12
0x18002f0f3  mov     [rbp+0F0h+ObjectAttributes.SecurityQualityOfService], 0
0x18002f0fb  or      edi, 140001h
0x18002f101  mov     [rsp+1F0h+EaLength], 0; EaLength
0x18002f109  mov     [rsp+1F0h+EaBuffer], 0; EaBuffer
0x18002f112  mov     [rsp+1F0h+CreateOptions], 4021h; CreateOptions
0x18002f11a  mov     [rsp+1F0h+CreateDisposition], 2; CreateDisposition
0x18002f122  mov     [rsp+1F0h+ShareAccess], 3; ShareAccess
0x18002f12a  mov     eax, [rbp+0F0h+var_AC+0Ch]
0x18002f12d  mov     [rsp+1F0h+FileAttributes], eax; FileAttributes
0x18002f131  mov     [rsp+1F0h+AllocationSize], 0; AllocationSize
0x18002f13a  lea     r9, [rbp+0F0h+IoStatusBlock]; IoStatusBlock
0x18002f13e  lea     r8, [rbp+0F0h+ObjectAttributes]; ObjectAttributes
0x18002f142  mov     edx, edi; DesiredAccess
0x18002f144  lea     rcx, [rbp+0F0h+FileHandle]; FileHandle
0x18002f148  call    cs:__imp_NtCreateFile
0x18002f14f  nop     dword ptr [rax+rax+00h]
0x18002f154  test    eax, eax
0x18002f156  jns     short loc_18002F171
0x18002f158  mov     ecx, eax
0x18002f15a  call    HRESULTFromNTSTATUS
0x18002f15f  mov     [rsp+1F0h+var_188], eax
0x18002f163  test    eax, eax
0x18002f165  jns     short loc_18002F171
0x18002f167  mov     eax, 10EEh
0x18002f16c  jmp     loc_18002EE8C
0x18002f171  mov     rbx, [rbp+0F0h+FileHandle]
0x18002f175  mov     [rbp+0F0h+FileHandle], 0FFFFFFFFFFFFFFFFh
0x18002f17d  mov     [rsp+1F0h+var_188], 0
0x18002f185  mov     eax, 10F1h
0x18002f18a  mov     [rsp+1F0h+var_184], ax
0x18002f18f  mov     [rbp+0F0h+var_128], r15
0x18002f193  lea     rax, [rbp+0F0h+var_128]
0x18002f197  mov     [rsp+1F0h+AllocationSize], rax; unsigned __int16 **
0x18002f19c  mov     r13d, 1
0x18002f1a2  mov     r9d, r13d; unsigned int
0x18002f1a5  mov     r8d, 4E8Dh; unsigned int
0x18002f1ab  mov     rdx, cs:hInstance; HINSTANCE
0x18002f1b2  lea     rcx, [rsp+1F0h+var_188]; this
0x18002f1b7  call    ?_SetContextHelper@CSxFunctionTracer@@AEAAJPEAUHINSTANCE__@@KKPEAPEBG@Z; CSxFunctionTracer::_SetContextHelper(HINSTANCE__ *,ulong,ulong,ushort const * *)
0x18002f1bc  mov     [rsp+1F0h+var_188], eax
0x18002f1c0  test    eax, eax
0x18002f1c2  mov     eax, 10F2h
0x18002f1c7  js      loc_18002EE8C
0x18002f1cd  mov     [rsp+1F0h+var_184], ax
0x18002f1d2  lea     rdi, WPP_GLOBAL_Control
0x18002f1d9  lea     rsi, WPP_052bc5b66f273e09fada3dec80af9ee3_Traceguids
0x18002f1e0  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f1e7  cmp     rcx, rdi
0x18002f1ea  jz      short loc_18002F205
0x18002f1ec  test    [rcx+1Ch], r14b
0x18002f1f0  jz      short loc_18002F205
0x18002f1f2  lea     edx, [r13+56h]
0x18002f1f6  mov     r9, r15
0x18002f1f9  mov     r8, rsi
0x18002f1fc  mov     rcx, [rcx+10h]
0x18002f200  call    WPP_SF_S
0x18002f205  mov     dword ptr [rsp+1F0h+AllocationSize], 4; FileInformationClass
0x18002f20d  mov     r9d, 28h ; '('; Length
0x18002f213  lea     r8, [rbp+0F0h+FileInformation]; FileInformation
0x18002f217  lea     rdx, [rbp+0F0h+IoStatusBlock]; IoStatusBlock
0x18002f21b  mov     rcx, rbx; FileHandle
0x18002f21e  call    cs:__imp_NtQueryInformationFile
0x18002f225  nop     dword ptr [rax+rax+00h]
0x18002f22a  mov     ecx, eax
0x18002f22c  call    HRESULTFromNTSTATUS
0x18002f231  mov     [rsp+1F0h+var_188], eax
0x18002f235  test    eax, eax
0x18002f237  mov     eax, 10FFh
0x18002f23c  js      loc_18002EE8C
0x18002f242  mov     [rsp+1F0h+var_184], ax
0x18002f247  test    r12, r12
0x18002f24a  jz      loc_18002F337
0x18002f250  lea     r9, [rbp+0F0h+bDaclDefaulted]; lpbDaclDefaulted
0x18002f254  lea     r8, [rbp+0F0h+pDacl]; pDacl
0x18002f258  lea     rdx, [rbp+0F0h+bDaclPresent]; lpbDaclPresent
0x18002f25c  mov     rcx, r12; pSecurityDescriptor
0x18002f25f  call    cs:__imp_GetSecurityDescriptorDacl
0x18002f266  nop     dword ptr [rax+rax+00h]
0x18002f26b  test    eax, eax
0x18002f26d  jnz     short loc_18002F282
0x18002f26f  call    GetLastFailureAsHRESULT
0x18002f274  mov     [rsp+1F0h+var_188], eax
0x18002f278  mov     eax, 1103h
0x18002f27d  jmp     loc_18002EE8C
0x18002f282  mov     [rsp+1F0h+var_188], 0
0x18002f28a  mov     eax, 1103h
0x18002f28f  mov     [rsp+1F0h+var_184], ax
0x18002f294  lea     r9, [rbp+0F0h+bSaclDefaulted]; lpbSaclDefaulted
0x18002f298  lea     r8, [rbp+0F0h+pSacl]; pSacl
0x18002f29c  lea     rdx, [rbp+0F0h+bSaclPresent]; lpbSaclPresent
0x18002f2a0  mov     rcx, r12; pSecurityDescriptor
0x18002f2a3  call    cs:__imp_GetSecurityDescriptorSacl
0x18002f2aa  nop     dword ptr [rax+rax+00h]
0x18002f2af  test    eax, eax
  ... truncated ...
```
