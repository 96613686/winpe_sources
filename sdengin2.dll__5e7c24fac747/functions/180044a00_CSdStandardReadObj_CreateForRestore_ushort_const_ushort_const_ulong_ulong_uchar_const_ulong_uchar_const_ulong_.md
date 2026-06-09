# CSdStandardReadObj::CreateForRestore(ushort const *,ushort const *,ulong,ulong,uchar const *,ulong,uchar const *,ulong,ulong,ulong,ulong,int)

- ea: `0x180044a00`
- end: `0x1800451e6`
- name: `?CreateForRestore@CSdStandardReadObj@@UEAAJPEBG0KKPEBEK1KKKKH@Z`
- size: `2022`
- prototype: `__int64 __fastcall(CSdStandardReadObj *this, const unsigned __int16 *, const unsigned __int16 *, DWORD, DWORD, unsigned __int8 *SecurityDescriptor, unsigned int, unsigned __int8 *, unsigned int, DWORD, DWORD, char, int)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180044a00`
- `0x18006fe84`
- `0x18006ff8c`
- `0x18008f5d0`
- `0x18008f660`
- `0x18009a08c`
- `0x18009a24c`
- `0x18009a354`
- `0x18009ae34`
- `0x1800c97c2`
- `0x1800c9830`
- `0x1800cb010`

## import_xrefs

- `ntdll!NtQueryInformationFile` at `0x180044e7c`
- `ntdll!NtQueryInformationFile` at `0x180044e7c`
- `KERNEL32!CreateFileW` at `0x180044c28`
- `KERNEL32!CreateFileW` at `0x180044d47`
- `KERNEL32!CreateFileW` at `0x180044dce`
- `KERNEL32!CreateFileW` at `0x180044f1a`
- `KERNEL32!CreateFileW` at `0x180044c28`
- `KERNEL32!CreateFileW` at `0x180044d47`
- `KERNEL32!CreateFileW` at `0x180044dce`
- `KERNEL32!CreateFileW` at `0x180044f1a`
- `KERNEL32!CloseHandle` at `0x180044da1`
- `KERNEL32!CloseHandle` at `0x180044de4`
- `KERNEL32!CloseHandle` at `0x180044eb9`
- `KERNEL32!CloseHandle` at `0x180044f30`
- `KERNEL32!CloseHandle` at `0x180045179`
- `KERNEL32!CloseHandle` at `0x1800451a1`
- `KERNEL32!CloseHandle` at `0x1800451b4`
- `KERNEL32!CloseHandle` at `0x180044da1`
- `KERNEL32!CloseHandle` at `0x180044de4`
- `KERNEL32!CloseHandle` at `0x180044eb9`
- `KERNEL32!CloseHandle` at `0x180044f30`
- `KERNEL32!CloseHandle` at `0x180045179`
- `KERNEL32!CloseHandle` at `0x1800451a1`
- `KERNEL32!CloseHandle` at `0x1800451b4`
- `KERNEL32!DeviceIoControl` at `0x180044f98`
- `KERNEL32!DeviceIoControl` at `0x180044fff`
- `KERNEL32!DeviceIoControl` at `0x180044f98`
- `KERNEL32!DeviceIoControl` at `0x180044fff`
- `KERNEL32!SetFileTime` at `0x18004503a`
- `KERNEL32!SetFileTime` at `0x18004503a`
- `KERNEL32!SetFileShortNameW` at `0x180044e2b`
- `KERNEL32!SetFileShortNameW` at `0x180044e2b`
- `api-ms-win-security-base-l1-1-0!SetKernelObjectSecurity` at `0x180044ca5`
- `api-ms-win-security-base-l1-1-0!SetKernelObjectSecurity` at `0x18004510d`
- `api-ms-win-security-base-l1-1-0!SetKernelObjectSecurity` at `0x180044ca5`
- `api-ms-win-security-base-l1-1-0!SetKernelObjectSecurity` at `0x18004510d`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180044c68`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180045088`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180044c68`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180045088`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x1800450c3`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x1800450c3`
- `ole32!CoTaskMemAlloc` at `0x18004512e`
- `ole32!CoTaskMemAlloc` at `0x18004512e`
- `ext-ms-win-advapi32-encryptedfile-l1-1-0!DecryptFileW` at `0x180044ec8`
- `ext-ms-win-advapi32-encryptedfile-l1-1-0!DecryptFileW` at `0x180044ec8`

## string_xrefs

- `0x180044a7f`: `CSdStandardReadObj::CreateForRestore`

## pseudocode

```c
__int64 __fastcall CSdStandardReadObj::CreateForRestore(
        CSdStandardReadObj *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        DWORD a4,
        DWORD a5,
        unsigned __int8 *SecurityDescriptor,
        unsigned int a7,
        unsigned __int8 *a8,
        unsigned int a9,
        DWORD a10,
        DWORD a11,
        char a12,
        int a13)
{
  __int64 v15; // rbx
  __int64 FileW; // rdi
  __int16 v17; // ax
  PSECURITY_DESCRIPTOR v18; // r13
  unsigned __int8 *v19; // r15
  signed int v20; // eax
  const WCHAR *v21; // rsi
  struct _SECURITY_ATTRIBUTES *v22; // r12
  DWORD v23; // r13d
  const WCHAR *v24; // rsi
  HANDLE v25; // rsi
  int v26; // eax
  bool v27; // sf
  unsigned int v28; // eax
  HANDLE v29; // rsi
  __int16 v30; // si
  SECURITY_INFORMATION v31; // edx
  void *v32; // r15
  size_t v33; // rsi
  void *v34; // rcx
  char *v35; // rcx
  unsigned int v36; // esi
  __int16 InBuffer; // [rsp+40h] [rbp-C0h] BYREF
  int LastFailureAsHRESULT; // [rsp+48h] [rbp-B8h] BYREF
  __int16 v40; // [rsp+4Ch] [rbp-B4h]
  __int16 v41; // [rsp+4Eh] [rbp-B2h]
  int v42; // [rsp+50h] [rbp-B0h]
  WINBOOL bDaclPresent; // [rsp+80h] [rbp-80h] BYREF
  DWORD dwShareMode; // [rsp+84h] [rbp-7Ch]
  DWORD dwDesiredAccess; // [rsp+88h] [rbp-78h]
  DWORD dwFlagsAndAttributes; // [rsp+8Ch] [rbp-74h]
  int v47; // [rsp+90h] [rbp-70h]
  DWORD dwCreationDisposition; // [rsp+94h] [rbp-6Ch]
  DWORD BytesReturned; // [rsp+98h] [rbp-68h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+9Ch] [rbp-64h] BYREF
  WINBOOL bSaclPresent; // [rsp+A0h] [rbp-60h] BYREF
  FILETIME CreationTime; // [rsp+A8h] [rbp-58h] BYREF
  LPCWSTR lpFileName; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v54; // [rsp+B8h] [rbp-48h]
  WINBOOL bSaclDefaulted; // [rsp+C0h] [rbp-40h] BYREF
  _DWORD cb[3]; // [rsp+C4h] [rbp-3Ch]
  PACL pDacl; // [rsp+D0h] [rbp-30h] BYREF
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+D8h] [rbp-28h]
  LPCWSTR lpShortName; // [rsp+E0h] [rbp-20h]
  PACL pSacl; // [rsp+E8h] [rbp-18h] BYREF
  void *Src; // [rsp+F0h] [rbp-10h]
  __int128 v62; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v63; // [rsp+108h] [rbp+8h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+110h] [rbp+10h] BYREF
  int FileInformation; // [rsp+120h] [rbp+20h] BYREF
  __int128 v66; // [rsp+124h] [rbp+24h]
  __int128 v67; // [rsp+134h] [rbp+34h]
  int v68; // [rsp+144h] [rbp+44h]

  dwDesiredAccess = a4;
  lpShortName = a3;
  *(_QWORD *)&cb[1] = a2;
  pSecurityDescriptor = a8;
  Src = SecurityDescriptor;
  dwShareMode = a5;
  cb[0] = a7;
  dwCreationDisposition = a10;
  dwFlagsAndAttributes = a11;
  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&LastFailureAsHRESULT,
    "CSdStandardReadObj::CreateForRestore",
    0x58u,
    1u);
  v15 = -1;
  FileW = -1;
  CreationTime.dwLowDateTime = -1;
  CreationTime.dwHighDateTime = -1;
  InBuffer = 0;
  BytesReturned = 0;
  v62 = 0;
  v63 = 0;
  pDacl = 0;
  pSacl = 0;
  bDaclPresent = 0;
  bSaclPresent = 0;
  bDaclDefaulted = 0;
  bSaclDefaulted = 0;
  lpFileName = (LPCWSTR)qword_1800E8530;
  v54 = 0;
  IoStatusBlock = 0;
  FileInformation = 0;
  v66 = 0;
  v67 = 0;
  v68 = 0;
  v17 = 114;
  if ( !a2 )
  {
    LastFailureAsHRESULT = -2147024809;
    goto LABEL_3;
  }
  v40 = 114;
  v17 = 115;
  if ( *((_QWORD *)this + 5) != -1 )
  {
    LastFailureAsHRESULT = -2130706378;
    goto LABEL_3;
  }
  LastFailureAsHRESULT = 0;
  v40 = 115;
  v18 = pSecurityDescriptor;
  v19 = (unsigned __int8 *)pSecurityDescriptor;
  if ( !pSecurityDescriptor )
    v19 = SecurityDescriptor;
  LastFailureAsHRESULT = CBsString::Set((CBsString *)&lpFileName, a2);
  v17 = 120;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_3;
  v47 = 0;
  v40 = 120;
  v20 = CBsString::ReverseFind((CBsString *)&lpFileName, 0x3Au);
  if ( v20 > 0 && v20 < (unsigned int)v54 )
  {
    v21 = lpFileName;
    if ( lpFileName[v20 + 1] == 92 )
      goto LABEL_15;
    LastFailureAsHRESULT = CBsString::SetLength((CBsString *)&lpFileName, v20);
    v17 = 126;
    if ( LastFailureAsHRESULT < 0 )
      goto LABEL_3;
    v47 = 1;
    v40 = 126;
  }
  v21 = lpFileName;
LABEL_15:
  if ( a13 )
  {
    LastFailureAsHRESULT = (*(__int64 (__fastcall **)(CSdStandardReadObj *, const unsigned __int16 *))(*(_QWORD *)this + 112LL))(
                             this,
                             a2);
    v22 = 0;
    v17 = 134;
    if ( LastFailureAsHRESULT < 0 )
      goto LABEL_3;
    v40 = 134;
    dwCreationDisposition = 2;
  }
  else
  {
    v22 = 0;
  }
  if ( v47 )
  {
    if ( v18 )
    {
      FileW = (__int64)CreateFileW(v21, 0x40000u, 0, 0, 3u, dwFlagsAndAttributes, 0);
      if ( FileW == -1 )
      {
        LastFailureAsHRESULT = GetLastFailureAsHRESULT();
        v17 = 144;
        goto LABEL_3;
      }
      LastFailureAsHRESULT = 0;
      v40 = 144;
      if ( !GetSecurityDescriptorDacl(v18, &bDaclPresent, &pDacl, &bDaclDefaulted) )
      {
        LastFailureAsHRESULT = GetLastFailureAsHRESULT();
        v17 = 147;
        goto LABEL_3;
      }
      LastFailureAsHRESULT = 0;
      v40 = 147;
      if ( bDaclPresent )
      {
        if ( !SetKernelObjectSecurity((HANDLE)FileW, 4u, v18) )
        {
          LastFailureAsHRESULT = GetLastFailureAsHRESULT();
          v17 = 151;
          goto LABEL_3;
        }
        LastFailureAsHRESULT = 0;
        v40 = 151;
      }
    }
    LastFailureAsHRESULT = (*(__int64 (__fastcall **)(CSdStandardReadObj *, const WCHAR *))(*(_QWORD *)this + 112LL))(
                             this,
                             v21);
    v17 = 160;
    if ( LastFailureAsHRESULT < 0 )
      goto LABEL_3;
    v40 = 160;
  }
  if ( v19 )
  {
    LODWORD(v63) = 0;
    LODWORD(v62) = 24;
    *((_QWORD *)&v62 + 1) = v19;
    v22 = (struct _SECURITY_ATTRIBUTES *)&v62;
  }
  v23 = dwFlagsAndAttributes & 0xFFFFFFF8;
  *((_DWORD *)this + 12) = 0;
  v24 = *(const WCHAR **)&cb[1];
  v15 = (__int64)CreateFileW(*(LPCWSTR *)&cb[1], dwDesiredAccess, dwShareMode, v22, dwCreationDisposition, v23, 0);
  if ( v15 == -1 )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT();
    v41 = 180;
    v42 = 1;
  }
  else
  {
    LastFailureAsHRESULT = 0;
    v40 = 180;
    *((_DWORD *)this + 12) = 1;
    if ( v19 )
    {
      if ( v15 )
      {
        CloseHandle((HANDLE)v15);
        v15 = -1;
      }
      v25 = CreateFileW(v24, dwDesiredAccess, dwShareMode, v22, 3u, v23, 0);
      if ( (unsigned __int64)(v15 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle((HANDLE)v15);
      v15 = (__int64)v25;
      if ( v25 == (HANDLE)-1LL )
      {
        LastFailureAsHRESULT = GetLastFailureAsHRESULT();
        v17 = 194;
        goto LABEL_3;
      }
      LastFailureAsHRESULT = 0;
      v40 = 194;
      v24 = *(const WCHAR **)&cb[1];
    }
    if ( lpShortName && !SetFileShortNameW((HANDLE)v15, lpShortName) && (a12 & 1) == 0 )
    {
      v26 = GetLastFailureAsHRESULT();
      if ( v26 == -2147024713 )
        v26 = 0;
      LastFailureAsHRESULT = v26;
      v27 = v26 < 0;
      v17 = 208;
      if ( v27 )
        goto LABEL_3;
      v40 = 208;
    }
    v28 = NtQueryInformationFile((HANDLE)v15, &IoStatusBlock, &FileInformation, 0x28u, FileBasicInformation);
    LastFailureAsHRESULT = HRESULTFromNTSTATUS(v28);
    v17 = 218;
    if ( LastFailureAsHRESULT < 0 )
    {
LABEL_3:
      v41 = v17;
      goto LABEL_91;
    }
    v40 = 218;
    if ( (WORD6(v67) & 0x4000) != 0 )
    {
      if ( (unsigned __int64)(v15 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        CloseHandle((HANDLE)v15);
        v15 = -1;
      }
      if ( !DecryptFileW(v24, 0) )
      {
        LastFailureAsHRESULT = GetLastFailureAsHRESULT();
        v17 = 234;
        goto LABEL_3;
      }
      LastFailureAsHRESULT = 0;
      v40 = 234;
      v29 = CreateFileW(v24, dwDesiredAccess, dwShareMode, v22, 3u, v23, 0);
      if ( (unsigned __int64)(v15 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle((HANDLE)v15);
      v15 = (__int64)v29;
      if ( v29 == (HANDLE)-1LL )
      {
        LastFailureAsHRESULT = GetLastFailureAsHRESULT();
        v17 = 240;
        goto LABEL_3;
      }
      LastFailureAsHRESULT = 0;
      v40 = 240;
    }
    v30 = dwFlagsAndAttributes;
    if ( (dwFlagsAndAttributes & 0x200) != 0 )
    {
      if ( !DeviceIoControl((HANDLE)v15, 0x900C4u, 0, 0, 0, 0, &BytesReturned, 0) )
      {
        LastFailureAsHRESULT = GetLastFailureAsHRESULT();
        v17 = 245;
        goto LABEL_3;
      }
      LastFailureAsHRESULT = 0;
      v40 = 245;
    }
    if ( (v30 & 0x800) != 0 )
      InBuffer = 1;
    if ( !DeviceIoControl((HANDLE)v15, 0x9C040u, &InBuffer, 2u, 0, 0, &BytesReturned, 0) )
    {
      LastFailureAsHRESULT = GetLastFailureAsHRESULT();
      v17 = 252;
      goto LABEL_3;
    }
    LastFailureAsHRESULT = 0;
    v40 = 252;
    if ( !SetFileTime((HANDLE)v15, &CreationTime, &CreationTime, &CreationTime) )
    {
      LastFailureAsHRESULT = GetLastFailureAsHRESULT();
      v17 = 254;
      goto LABEL_3;
    }
    LastFailureAsHRESULT = 0;
    v40 = 254;
    if ( v19 && !v47 )
    {
      if ( !GetSecurityDescriptorDacl(v19, &bDaclPresent, &pDacl, &bDaclDefaulted) )
      {
        LastFailureAsHRESULT = GetLastFailureAsHRESULT();
        v17 = 258;
        goto LABEL_3;
      }
      LastFailureAsHRESULT = 0;
      v40 = 258;
      if ( !GetSecurityDescriptorSacl(v19, &bSaclPresent, &pSacl, &bSaclDefaulted) )
      {
        LastFailureAsHRESULT = GetLastFailureAsHRESULT();
        v17 = 259;
        goto LABEL_3;
      }
      v31 = 0;
      LastFailureAsHRESULT = 0;
      v40 = 259;
      if ( bDaclPresent )
        v31 = 4;
      if ( bSaclPresent )
        v31 |= 0x18u;
      SetKernelObjectSecurity((HANDLE)v15, v31, v19);
    }
    if ( pSecurityDescriptor )
    {
      v32 = Src;
      if ( Src )
      {
        if ( cb[0] )
        {
          v33 = cb[0];
          v34 = CoTaskMemAlloc(cb[0]);
          *((_QWORD *)this + 7) = v34;
          v17 = 281;
          if ( !v34 )
          {
            LastFailureAsHRESULT = -2147024882;
            goto LABEL_3;
          }
          LastFailureAsHRESULT = 0;
          v40 = 281;
          memcpy_0(v34, v32, v33);
        }
      }
    }
    *((_DWORD *)this + 16) = 0;
    v35 = (char *)*((_QWORD *)this + 5);
    if ( (unsigned __int64)(v35 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v35);
    *((_QWORD *)this + 5) = v15;
    v15 = -1;
  }
LABEL_91:
  v36 = LastFailureAsHRESULT;
  CBsString::_Release((CBsString *)&lpFileName);
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)FileW);
  if ( (unsigned __int64)(v15 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)v15);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT);
  return v36;
}

```

## disassembly

```asm
0x180044a00  push    rbp
0x180044a02  push    rbx
0x180044a03  push    rsi
0x180044a04  push    rdi
0x180044a05  push    r12
0x180044a07  push    r13
0x180044a09  push    r14
0x180044a0b  push    r15
0x180044a0d  lea     rbp, [rsp-58h]
0x180044a12  sub     rsp, 158h
0x180044a19  mov     rax, cs:__security_cookie
0x180044a20  xor     rax, rsp
0x180044a23  mov     [rbp+90h+var_48], rax
0x180044a27  mov     [rbp+90h+dwDesiredAccess], r9d
0x180044a2b  mov     [rbp+90h+lpShortName], r8
0x180044a2f  mov     r12, rdx
0x180044a32  mov     qword ptr [rbp+90h+cb+4], rdx
0x180044a36  mov     r14, rcx
0x180044a39  mov     rax, [rbp+90h+arg_38]
0x180044a40  mov     [rbp+90h+pSecurityDescriptor], rax
0x180044a44  mov     rsi, [rbp+90h+SecurityDescriptor]
0x180044a4b  mov     [rbp+90h+Src], rsi
0x180044a4f  mov     eax, [rbp+90h+arg_20]
0x180044a55  mov     [rbp+90h+dwShareMode], eax
0x180044a58  mov     eax, [rbp+90h+arg_30]
0x180044a5e  mov     dword ptr [rbp+90h+cb], eax
0x180044a61  mov     r13d, [rbp+90h+arg_48]
0x180044a68  mov     [rbp+90h+var_FC], r13d
0x180044a6c  mov     eax, [rbp+90h+arg_50]
0x180044a72  mov     [rbp+90h+var_104], eax
0x180044a75  mov     r9d, 1; unsigned __int16
0x180044a7b  lea     r8d, [r9+57h]; unsigned __int16
0x180044a7f  lea     rdx, aCsdstandardrea_4; "CSdStandardReadObj::CreateForRestore"
0x180044a86  lea     rcx, [rsp+190h+var_148]; this
0x180044a8b  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180044a90  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180044a94  mov     rbx, rdx
0x180044a97  mov     rdi, rdx
0x180044a9a  or      eax, 0FFFFFFFFh
0x180044a9d  mov     [rbp+90h+CreationTime.dwLowDateTime], eax
0x180044aa0  mov     [rbp+90h+CreationTime.dwHighDateTime], eax
0x180044aa3  xor     ecx, ecx
0x180044aa5  mov     [rsp+190h+InBuffer], cx
0x180044aaa  mov     [rbp+90h+BytesReturned], ecx
0x180044aad  xorps   xmm0, xmm0
0x180044ab0  xor     eax, eax
0x180044ab2  movups  [rbp+90h+var_98], xmm0
0x180044ab6  mov     [rbp+90h+var_88], rax
0x180044aba  mov     [rbp+90h+pDacl], rcx
0x180044abe  mov     [rbp+90h+pSacl], rcx
0x180044ac2  mov     [rbp+90h+bDaclPresent], ecx
0x180044ac5  mov     [rbp+90h+bSaclPresent], ecx
0x180044ac8  mov     [rbp+90h+bDaclDefaulted], ecx
0x180044acb  mov     [rbp+90h+bSaclDefaulted], ecx
0x180044ace  lea     rax, qword_1800E8530
0x180044ad5  mov     [rbp+90h+lpFileName], rax
0x180044ad9  mov     [rbp+90h+var_D8], rcx
0x180044add  movups  xmmword ptr [rbp+90h+IoStatusBlock], xmm0
0x180044ae1  mov     [rbp+90h+FileInformation], ecx
0x180044ae4  xorps   xmm1, xmm1
0x180044ae7  xor     eax, eax
0x180044ae9  movups  [rbp+90h+var_6C], xmm1
0x180044aed  movups  [rbp+90h+var_5C], xmm1
0x180044af1  mov     [rbp+90h+var_4C], eax
0x180044af4  lea     eax, [rdx+73h]
0x180044af7  test    r12, r12
0x180044afa  jnz     short loc_180044B0E
0x180044afc  mov     [rsp+190h+var_148], 80070057h
0x180044b04  mov     [rsp+190h+var_142], ax
0x180044b09  jmp     loc_180045187
0x180044b0e  mov     [rsp+190h+var_144], ax
0x180044b13  mov     eax, 73h ; 's'
0x180044b18  cmp     [r14+28h], rdx
0x180044b1c  jz      short loc_180044B28
0x180044b1e  mov     [rsp+190h+var_148], 81000036h
0x180044b26  jmp     short loc_180044B04
0x180044b28  mov     [rsp+190h+var_148], ecx
0x180044b2c  mov     [rsp+190h+var_144], ax
0x180044b31  mov     r13, [rbp+90h+pSecurityDescriptor]
0x180044b35  mov     r15, r13
0x180044b38  test    r13, r13
0x180044b3b  cmovz   r15, rsi
0x180044b3f  mov     rdx, r12; unsigned __int16 *
0x180044b42  lea     rcx, [rbp+90h+lpFileName]; this
0x180044b46  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x180044b4b  mov     [rsp+190h+var_148], eax
0x180044b4f  test    eax, eax
0x180044b51  mov     eax, 78h ; 'x'
0x180044b56  js      short loc_180044B04
0x180044b58  mov     [rbp+90h+var_100], 0
0x180044b5f  mov     [rsp+190h+var_144], ax
0x180044b64  lea     edx, [rax-3Eh]; unsigned __int16
0x180044b67  lea     rcx, [rbp+90h+lpFileName]; this
0x180044b6b  call    ?ReverseFind@CBsString@@QEBAJG@Z; CBsString::ReverseFind(ushort)
0x180044b70  test    eax, eax
0x180044b72  jle     short loc_180044BAF
0x180044b74  cmp     eax, dword ptr [rbp+90h+var_D8]
0x180044b77  jnb     short loc_180044BAF
0x180044b79  mov     ecx, eax
0x180044b7b  mov     rsi, [rbp+90h+lpFileName]
0x180044b7f  cmp     word ptr [rsi+rcx*2+2], 5Ch ; '\'
0x180044b85  jz      short loc_180044BB3
0x180044b87  mov     edx, eax; unsigned int
0x180044b89  lea     rcx, [rbp+90h+lpFileName]; this
0x180044b8d  call    ?SetLength@CBsString@@QEAAJK@Z; CBsString::SetLength(ulong)
0x180044b92  mov     [rsp+190h+var_148], eax
0x180044b96  test    eax, eax
0x180044b98  mov     eax, 7Eh ; '~'
0x180044b9d  js      loc_180044B04
0x180044ba3  mov     [rbp+90h+var_100], 1
0x180044baa  mov     [rsp+190h+var_144], ax
0x180044baf  mov     rsi, [rbp+90h+lpFileName]
0x180044bb3  cmp     [rbp+90h+arg_60], 0
0x180044bba  jz      short loc_180044BF0
0x180044bbc  mov     rax, [r14]
0x180044bbf  mov     rdx, r12
0x180044bc2  mov     rcx, r14
0x180044bc5  mov     rax, [rax+70h]
0x180044bc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044bce  mov     [rsp+190h+var_148], eax
0x180044bd2  xor     r12d, r12d
0x180044bd5  test    eax, eax
0x180044bd7  mov     eax, 86h
0x180044bdc  js      loc_180044B04
0x180044be2  mov     [rsp+190h+var_144], ax
0x180044be7  mov     [rbp+90h+var_FC], 2
0x180044bee  jmp     short loc_180044BF3
0x180044bf0  xor     r12d, r12d
0x180044bf3  cmp     [rbp+90h+var_100], r12d
0x180044bf7  jz      loc_180044CF9
0x180044bfd  test    r13, r13
0x180044c00  jz      loc_180044CD1
0x180044c06  mov     [rsp+190h+hTemplateFile], r12; hTemplateFile
0x180044c0b  mov     eax, [rbp+90h+var_104]
0x180044c0e  mov     [rsp+190h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x180044c12  mov     [rsp+190h+dwCreationDisposition], 3; dwCreationDisposition
0x180044c1a  xor     r9d, r9d; lpSecurityAttributes
0x180044c1d  xor     r8d, r8d; dwShareMode
0x180044c20  mov     edx, 40000h; dwDesiredAccess
0x180044c25  mov     rcx, rsi; lpFileName
0x180044c28  call    cs:__imp_CreateFileW
0x180044c2e  mov     rdi, rax
0x180044c31  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180044c35  jnz     short loc_180044C4A
0x180044c37  call    GetLastFailureAsHRESULT
0x180044c3c  mov     [rsp+190h+var_148], eax
0x180044c40  mov     eax, 90h
0x180044c45  jmp     loc_180044B04
0x180044c4a  mov     [rsp+190h+var_148], r12d
0x180044c4f  mov     eax, 90h
0x180044c54  mov     [rsp+190h+var_144], ax
0x180044c59  lea     r9, [rbp+90h+bDaclDefaulted]; lpbDaclDefaulted
0x180044c5d  lea     r8, [rbp+90h+pDacl]; pDacl
0x180044c61  lea     rdx, [rbp+90h+bDaclPresent]; lpbDaclPresent
0x180044c65  mov     rcx, r13; pSecurityDescriptor
0x180044c68  call    cs:__imp_GetSecurityDescriptorDacl
0x180044c6e  test    eax, eax
0x180044c70  jnz     short loc_180044C85
0x180044c72  call    GetLastFailureAsHRESULT
0x180044c77  mov     [rsp+190h+var_148], eax
0x180044c7b  mov     eax, 93h
0x180044c80  jmp     loc_180044B04
0x180044c85  mov     [rsp+190h+var_148], r12d
0x180044c8a  mov     eax, 93h
0x180044c8f  mov     [rsp+190h+var_144], ax
0x180044c94  cmp     [rbp+90h+bDaclPresent], r12d
0x180044c98  jz      short loc_180044CD1
0x180044c9a  mov     r8, r13; SecurityDescriptor
0x180044c9d  mov     edx, 4; SecurityInformation
0x180044ca2  mov     rcx, rdi; Handle
0x180044ca5  call    cs:__imp_SetKernelObjectSecurity
0x180044cab  test    eax, eax
0x180044cad  jnz     short loc_180044CC2
0x180044caf  call    GetLastFailureAsHRESULT
0x180044cb4  mov     [rsp+190h+var_148], eax
0x180044cb8  mov     eax, 97h
0x180044cbd  jmp     loc_180044B04
0x180044cc2  mov     [rsp+190h+var_148], r12d
0x180044cc7  mov     eax, 97h
0x180044ccc  mov     [rsp+190h+var_144], ax
0x180044cd1  mov     rax, [r14]
0x180044cd4  mov     rdx, rsi
0x180044cd7  mov     rcx, r14
0x180044cda  mov     rax, [rax+70h]
0x180044cde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044ce3  mov     [rsp+190h+var_148], eax
0x180044ce7  test    eax, eax
0x180044ce9  mov     eax, 0A0h
0x180044cee  js      loc_180044B04
0x180044cf4  mov     [rsp+190h+var_144], ax
0x180044cf9  test    r15, r15
0x180044cfc  jz      short loc_180044D11
0x180044cfe  mov     dword ptr [rbp+90h+var_88], r12d
0x180044d02  mov     dword ptr [rbp+90h+var_98], 18h
0x180044d09  mov     qword ptr [rbp+90h+var_98+8], r15
0x180044d0d  lea     r12, [rbp+90h+var_98]
0x180044d11  mov     r13d, [rbp+90h+var_104]
0x180044d15  and     r13d, 0FFFFFFF8h
0x180044d19  mov     dword ptr [r14+30h], 0
0x180044d21  mov     [rsp+190h+hTemplateFile], 0; hTemplateFile
0x180044d2a  mov     [rsp+190h+dwFlagsAndAttributes], r13d; dwFlagsAndAttributes
0x180044d2f  mov     eax, [rbp+90h+var_FC]
0x180044d32  mov     [rsp+190h+dwCreationDisposition], eax; dwCreationDisposition
0x180044d36  mov     r9, r12; lpSecurityAttributes
0x180044d39  mov     r8d, [rbp+90h+dwShareMode]; dwShareMode
0x180044d3d  mov     edx, [rbp+90h+dwDesiredAccess]; dwDesiredAccess
0x180044d40  mov     rsi, qword ptr [rbp+90h+cb+4]
0x180044d44  mov     rcx, rsi; lpFileName
0x180044d47  call    cs:__imp_CreateFileW
0x180044d4d  mov     rbx, rax
0x180044d50  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180044d54  jnz     short loc_180044D76
0x180044d56  call    GetLastFailureAsHRESULT
0x180044d5b  mov     [rsp+190h+var_148], eax
0x180044d5f  mov     eax, 0B4h
0x180044d64  mov     [rsp+190h+var_142], ax
0x180044d69  mov     [rsp+190h+var_140], 1
0x180044d71  jmp     loc_180045187
0x180044d76  mov     [rsp+190h+var_148], 0
0x180044d7e  mov     eax, 0B4h
0x180044d83  mov     [rsp+190h+var_144], ax
0x180044d88  mov     dword ptr [r14+30h], 1
0x180044d90  test    r15, r15
0x180044d93  jz      loc_180044E1C
0x180044d99  test    rbx, rbx
0x180044d9c  jz      short loc_180044DAB
0x180044d9e  mov     rcx, rbx; hObject
0x180044da1  call    cs:__imp_CloseHandle
0x180044da7  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180044dab  mov     [rsp+190h+hTemplateFile], 0; hTemplateFile
0x180044db4  mov     [rsp+190h+dwFlagsAndAttributes], r13d; dwFlagsAndAttributes
0x180044db9  mov     [rsp+190h+dwCreationDisposition], 3; dwCreationDisposition
0x180044dc1  mov     r9, r12; lpSecurityAttributes
0x180044dc4  mov     r8d, [rbp+90h+dwShareMode]; dwShareMode
0x180044dc8  mov     edx, [rbp+90h+dwDesiredAccess]; dwDesiredAccess
0x180044dcb  mov     rcx, rsi; lpFileName
0x180044dce  call    cs:__imp_CreateFileW
0x180044dd4  mov     rsi, rax
0x180044dd7  lea     rcx, [rbx-1]
0x180044ddb  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180044ddf  ja      short loc_180044DEA
0x180044de1  mov     rcx, rbx; hObject
0x180044de4  call    cs:__imp_CloseHandle
0x180044dea  mov     rbx, rsi
0x180044ded  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180044df1  jnz     short loc_180044E06
0x180044df3  call    GetLastFailureAsHRESULT
0x180044df8  mov     [rsp+190h+var_148], eax
0x180044dfc  mov     eax, 0C2h
0x180044e01  jmp     loc_180044B04
0x180044e06  mov     [rsp+190h+var_148], 0
0x180044e0e  mov     eax, 0C2h
0x180044e13  mov     [rsp+190h+var_144], ax
0x180044e18  mov     rsi, qword ptr [rbp+90h+cb+4]
0x180044e1c  mov     rax, [rbp+90h+lpShortName]
0x180044e20  test    rax, rax
0x180044e23  jz      short loc_180044E63
0x180044e25  mov     rdx, rax; lpShortName
0x180044e28  mov     rcx, rbx; hFile
0x180044e2b  call    cs:__imp_SetFileShortNameW
0x180044e31  test    eax, eax
0x180044e33  jnz     short loc_180044E63
0x180044e35  test    [rbp+90h+arg_58], 1
0x180044e3c  jnz     short loc_180044E63
0x180044e3e  call    GetLastFailureAsHRESULT
0x180044e43  xor     ecx, ecx
0x180044e45  cmp     eax, 800700B7h
0x180044e4a  cmovz   eax, ecx
0x180044e4d  mov     [rsp+190h+var_148], eax
0x180044e51  test    eax, eax
0x180044e53  mov     eax, 0D0h
0x180044e58  js      loc_180044B04
0x180044e5e  mov     [rsp+190h+var_144], ax
0x180044e63  mov     [rsp+190h+dwCreationDisposition], 4; FileInformationClass
0x180044e6b  mov     r9d, 28h ; '('; Length
0x180044e71  lea     r8, [rbp+90h+FileInformation]; FileInformation
0x180044e75  lea     rdx, [rbp+90h+IoStatusBlock]; IoStatusBlock
0x180044e79  mov     rcx, rbx; FileHandle
0x180044e7c  call    cs:__imp_NtQueryInformationFile
0x180044e82  mov     ecx, eax
0x180044e84  call    HRESULTFromNTSTATUS
0x180044e89  mov     [rsp+190h+var_148], eax
0x180044e8d  test    eax, eax
0x180044e8f  mov     eax, 0DAh
0x180044e94  js      loc_180044B04
0x180044e9a  mov     [rsp+190h+var_144], ax
0x180044e9f  test    dword ptr [rbp+90h+var_5C+0Ch], 4000h
0x180044ea6  jz      loc_180044F66
0x180044eac  lea     rax, [rbx-1]
0x180044eb0  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180044eb4  ja      short loc_180044EC3
0x180044eb6  mov     rcx, rbx; hObject
0x180044eb9  call    cs:__imp_CloseHandle
0x180044ebf  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180044ec3  xor     edx, edx; dwReserved
0x180044ec5  mov     rcx, rsi; lpFileName
0x180044ec8  call    cs:__imp_DecryptFileW
0x180044ece  test    eax, eax
0x180044ed0  jnz     short loc_180044EE5
0x180044ed2  call    GetLastFailureAsHRESULT
  ... truncated ...
```
