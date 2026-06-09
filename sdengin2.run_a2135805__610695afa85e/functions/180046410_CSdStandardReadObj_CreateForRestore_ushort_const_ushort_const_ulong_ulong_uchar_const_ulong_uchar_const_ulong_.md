# CSdStandardReadObj::CreateForRestore(ushort const *,ushort const *,ulong,ulong,uchar const *,ulong,uchar const *,ulong,ulong,ulong,ulong,int)

- ea: `0x180046410`
- end: `0x180046c81`
- name: `?CreateForRestore@CSdStandardReadObj@@UEAAJPEBG0KKPEBEK1KKKKH@Z`
- size: `2161`
- prototype: `__int64 __fastcall(CSdStandardReadObj *this, const unsigned __int16 *, const unsigned __int16 *, DWORD, DWORD, unsigned __int8 *SecurityDescriptor, unsigned int, unsigned __int8 *, unsigned int, DWORD, DWORD, char, int)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180046410`
- `0x180072e08`
- `0x180072f14`
- `0x1800935fc`
- `0x180093698`
- `0x18009e718`
- `0x18009e904`
- `0x18009ea0c`
- `0x18009f560`
- `0x1800cf552`
- `0x1800cf5c0`
- `0x1800d1010`

## import_xrefs

- `ntdll!NtQueryInformationFile` at `0x1800468bc`
- `ntdll!NtQueryInformationFile` at `0x1800468bc`
- `KERNEL32!CreateFileW` at `0x180046638`
- `KERNEL32!CreateFileW` at `0x180046769`
- `KERNEL32!CreateFileW` at `0x1800467fc`
- `KERNEL32!CreateFileW` at `0x18004696c`
- `KERNEL32!CreateFileW` at `0x180046638`
- `KERNEL32!CreateFileW` at `0x180046769`
- `KERNEL32!CreateFileW` at `0x1800467fc`
- `KERNEL32!CreateFileW` at `0x18004696c`
- `KERNEL32!CloseHandle` at `0x1800467c9`
- `KERNEL32!CloseHandle` at `0x180046818`
- `KERNEL32!CloseHandle` at `0x1800468ff`
- `KERNEL32!CloseHandle` at `0x180046988`
- `KERNEL32!CloseHandle` at `0x180046c01`
- `KERNEL32!CloseHandle` at `0x180046c2f`
- `KERNEL32!CloseHandle` at `0x180046c48`
- `KERNEL32!CloseHandle` at `0x1800467c9`
- `KERNEL32!CloseHandle` at `0x180046818`
- `KERNEL32!CloseHandle` at `0x1800468ff`
- `KERNEL32!CloseHandle` at `0x180046988`
- `KERNEL32!CloseHandle` at `0x180046c01`
- `KERNEL32!CloseHandle` at `0x180046c2f`
- `KERNEL32!CloseHandle` at `0x180046c48`
- `KERNEL32!DeviceIoControl` at `0x1800469f6`
- `KERNEL32!DeviceIoControl` at `0x180046a63`
- `KERNEL32!DeviceIoControl` at `0x1800469f6`
- `KERNEL32!DeviceIoControl` at `0x180046a63`
- `KERNEL32!SetFileTime` at `0x180046aa4`
- `KERNEL32!SetFileTime` at `0x180046aa4`
- `KERNEL32!SetFileShortNameW` at `0x180046865`
- `KERNEL32!SetFileShortNameW` at `0x180046865`
- `api-ms-win-security-base-l1-1-0!SetKernelObjectSecurity` at `0x1800466c1`
- `api-ms-win-security-base-l1-1-0!SetKernelObjectSecurity` at `0x180046b89`
- `api-ms-win-security-base-l1-1-0!SetKernelObjectSecurity` at `0x1800466c1`
- `api-ms-win-security-base-l1-1-0!SetKernelObjectSecurity` at `0x180046b89`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18004667e`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180046af8`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18004667e`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180046af8`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x180046b39`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x180046b39`
- `ole32!CoTaskMemAlloc` at `0x180046bb0`
- `ole32!CoTaskMemAlloc` at `0x180046bb0`
- `ext-ms-win-advapi32-encryptedfile-l1-1-0!DecryptFileW` at `0x180046914`
- `ext-ms-win-advapi32-encryptedfile-l1-1-0!DecryptFileW` at `0x180046914`

## string_xrefs

- `0x18004648f`: `CSdStandardReadObj::CreateForRestore`

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
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // rcx
  DWORD v26; // r13d
  const WCHAR *v27; // rsi
  __int64 v28; // rcx
  HANDLE v29; // rsi
  __int64 v30; // rcx
  __int64 v31; // rcx
  int v32; // eax
  bool v33; // sf
  unsigned int v34; // eax
  __int64 v35; // rcx
  HANDLE v36; // rsi
  __int64 v37; // rcx
  __int16 v38; // si
  __int64 v39; // rcx
  __int64 v40; // rcx
  __int64 v41; // rcx
  __int64 v42; // rcx
  __int64 v43; // rcx
  SECURITY_INFORMATION v44; // edx
  void *v45; // r15
  size_t v46; // rsi
  void *v47; // rcx
  char *v48; // rcx
  unsigned int v49; // esi
  __int16 InBuffer; // [rsp+40h] [rbp-C0h] BYREF
  int LastFailureAsHRESULT; // [rsp+48h] [rbp-B8h] BYREF
  __int16 v53; // [rsp+4Ch] [rbp-B4h]
  __int16 v54; // [rsp+4Eh] [rbp-B2h]
  int v55; // [rsp+50h] [rbp-B0h]
  WINBOOL bDaclPresent; // [rsp+80h] [rbp-80h] BYREF
  DWORD dwShareMode; // [rsp+84h] [rbp-7Ch]
  DWORD dwDesiredAccess; // [rsp+88h] [rbp-78h]
  DWORD dwFlagsAndAttributes; // [rsp+8Ch] [rbp-74h]
  int v60; // [rsp+90h] [rbp-70h]
  DWORD dwCreationDisposition; // [rsp+94h] [rbp-6Ch]
  DWORD BytesReturned; // [rsp+98h] [rbp-68h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+9Ch] [rbp-64h] BYREF
  WINBOOL bSaclPresent; // [rsp+A0h] [rbp-60h] BYREF
  FILETIME CreationTime; // [rsp+A8h] [rbp-58h] BYREF
  LPCWSTR lpFileName; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v67; // [rsp+B8h] [rbp-48h]
  WINBOOL bSaclDefaulted; // [rsp+C0h] [rbp-40h] BYREF
  _DWORD cb[3]; // [rsp+C4h] [rbp-3Ch]
  PACL pDacl; // [rsp+D0h] [rbp-30h] BYREF
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+D8h] [rbp-28h]
  LPCWSTR lpShortName; // [rsp+E0h] [rbp-20h]
  PACL pSacl; // [rsp+E8h] [rbp-18h] BYREF
  void *Src; // [rsp+F0h] [rbp-10h]
  __int128 v75; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v76; // [rsp+108h] [rbp+8h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+110h] [rbp+10h] BYREF
  int FileInformation; // [rsp+120h] [rbp+20h] BYREF
  __int128 v79; // [rsp+124h] [rbp+24h]
  __int128 v80; // [rsp+134h] [rbp+34h]
  int v81; // [rsp+144h] [rbp+44h]

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
  v75 = 0;
  v76 = 0;
  pDacl = 0;
  pSacl = 0;
  bDaclPresent = 0;
  bSaclPresent = 0;
  bDaclDefaulted = 0;
  bSaclDefaulted = 0;
  lpFileName = (LPCWSTR)qword_1800EE510;
  v67 = 0;
  IoStatusBlock = 0;
  FileInformation = 0;
  v79 = 0;
  v80 = 0;
  v81 = 0;
  v17 = 114;
  if ( !a2 )
  {
    LastFailureAsHRESULT = -2147024809;
    goto LABEL_3;
  }
  v53 = 114;
  v17 = 115;
  if ( *((_QWORD *)this + 5) != -1 )
  {
    LastFailureAsHRESULT = -2130706378;
    goto LABEL_3;
  }
  LastFailureAsHRESULT = 0;
  v53 = 115;
  v18 = pSecurityDescriptor;
  v19 = (unsigned __int8 *)pSecurityDescriptor;
  if ( !pSecurityDescriptor )
    v19 = SecurityDescriptor;
  LastFailureAsHRESULT = CBsString::Set((CBsString *)&lpFileName, a2);
  v17 = 120;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_3;
  v60 = 0;
  v53 = 120;
  v20 = CBsString::ReverseFind((CBsString *)&lpFileName, 0x3Au);
  if ( v20 > 0 && v20 < (unsigned int)v67 )
  {
    v21 = lpFileName;
    if ( lpFileName[v20 + 1] == 92 )
      goto LABEL_15;
    LastFailureAsHRESULT = CBsString::SetLength((CBsString *)&lpFileName, v20);
    v17 = 126;
    if ( LastFailureAsHRESULT < 0 )
      goto LABEL_3;
    v60 = 1;
    v53 = 126;
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
    v53 = 134;
    dwCreationDisposition = 2;
  }
  else
  {
    v22 = 0;
  }
  if ( v60 )
  {
    if ( v18 )
    {
      FileW = (__int64)CreateFileW(v21, 0x40000u, 0, 0, 3u, dwFlagsAndAttributes, 0);
      if ( FileW == -1 )
      {
        LastFailureAsHRESULT = GetLastFailureAsHRESULT(v23);
        v17 = 144;
        goto LABEL_3;
      }
      LastFailureAsHRESULT = 0;
      v53 = 144;
      if ( !GetSecurityDescriptorDacl(v18, &bDaclPresent, &pDacl, &bDaclDefaulted) )
      {
        LastFailureAsHRESULT = GetLastFailureAsHRESULT(v24);
        v17 = 147;
        goto LABEL_3;
      }
      LastFailureAsHRESULT = 0;
      v53 = 147;
      if ( bDaclPresent )
      {
        if ( !SetKernelObjectSecurity((HANDLE)FileW, 4u, v18) )
        {
          LastFailureAsHRESULT = GetLastFailureAsHRESULT(v25);
          v17 = 151;
          goto LABEL_3;
        }
        LastFailureAsHRESULT = 0;
        v53 = 151;
      }
    }
    LastFailureAsHRESULT = (*(__int64 (__fastcall **)(CSdStandardReadObj *, const WCHAR *))(*(_QWORD *)this + 112LL))(
                             this,
                             v21);
    v17 = 160;
    if ( LastFailureAsHRESULT < 0 )
      goto LABEL_3;
    v53 = 160;
  }
  if ( v19 )
  {
    LODWORD(v76) = 0;
    LODWORD(v75) = 24;
    *((_QWORD *)&v75 + 1) = v19;
    v22 = (struct _SECURITY_ATTRIBUTES *)&v75;
  }
  v26 = dwFlagsAndAttributes & 0xFFFFFFF8;
  *((_DWORD *)this + 12) = 0;
  v27 = *(const WCHAR **)&cb[1];
  v15 = (__int64)CreateFileW(*(LPCWSTR *)&cb[1], dwDesiredAccess, dwShareMode, v22, dwCreationDisposition, v26, 0);
  if ( v15 == -1 )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v28);
    v54 = 180;
    v55 = 1;
  }
  else
  {
    LastFailureAsHRESULT = 0;
    v53 = 180;
    *((_DWORD *)this + 12) = 1;
    if ( v19 )
    {
      if ( v15 )
      {
        CloseHandle((HANDLE)v15);
        v15 = -1;
      }
      v29 = CreateFileW(v27, dwDesiredAccess, dwShareMode, v22, 3u, v26, 0);
      v30 = v15 - 1;
      if ( (unsigned __int64)(v15 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle((HANDLE)v15);
      v15 = (__int64)v29;
      if ( v29 == (HANDLE)-1LL )
      {
        LastFailureAsHRESULT = GetLastFailureAsHRESULT(v30);
        v17 = 194;
        goto LABEL_3;
      }
      LastFailureAsHRESULT = 0;
      v53 = 194;
      v27 = *(const WCHAR **)&cb[1];
    }
    if ( lpShortName && !SetFileShortNameW((HANDLE)v15, lpShortName) && (a12 & 1) == 0 )
    {
      v32 = GetLastFailureAsHRESULT(v31);
      if ( v32 == -2147024713 )
        v32 = 0;
      LastFailureAsHRESULT = v32;
      v33 = v32 < 0;
      v17 = 208;
      if ( v33 )
        goto LABEL_3;
      v53 = 208;
    }
    v34 = NtQueryInformationFile((HANDLE)v15, &IoStatusBlock, &FileInformation, 0x28u, FileBasicInformation);
    LastFailureAsHRESULT = HRESULTFromNTSTATUS(v34);
    v17 = 218;
    if ( LastFailureAsHRESULT < 0 )
    {
LABEL_3:
      v54 = v17;
      goto LABEL_91;
    }
    v53 = 218;
    if ( (WORD6(v80) & 0x4000) != 0 )
    {
      if ( (unsigned __int64)(v15 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        CloseHandle((HANDLE)v15);
        v15 = -1;
      }
      if ( !DecryptFileW(v27, 0) )
      {
        LastFailureAsHRESULT = GetLastFailureAsHRESULT(v35);
        v17 = 234;
        goto LABEL_3;
      }
      LastFailureAsHRESULT = 0;
      v53 = 234;
      v36 = CreateFileW(v27, dwDesiredAccess, dwShareMode, v22, 3u, v26, 0);
      v37 = v15 - 1;
      if ( (unsigned __int64)(v15 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle((HANDLE)v15);
      v15 = (__int64)v36;
      if ( v36 == (HANDLE)-1LL )
      {
        LastFailureAsHRESULT = GetLastFailureAsHRESULT(v37);
        v17 = 240;
        goto LABEL_3;
      }
      LastFailureAsHRESULT = 0;
      v53 = 240;
    }
    v38 = dwFlagsAndAttributes;
    if ( (dwFlagsAndAttributes & 0x200) != 0 )
    {
      if ( !DeviceIoControl((HANDLE)v15, 0x900C4u, 0, 0, 0, 0, &BytesReturned, 0) )
      {
        LastFailureAsHRESULT = GetLastFailureAsHRESULT(v39);
        v17 = 245;
        goto LABEL_3;
      }
      LastFailureAsHRESULT = 0;
      v53 = 245;
    }
    if ( (v38 & 0x800) != 0 )
      InBuffer = 1;
    if ( !DeviceIoControl((HANDLE)v15, 0x9C040u, &InBuffer, 2u, 0, 0, &BytesReturned, 0) )
    {
      LastFailureAsHRESULT = GetLastFailureAsHRESULT(v40);
      v17 = 252;
      goto LABEL_3;
    }
    LastFailureAsHRESULT = 0;
    v53 = 252;
    if ( !SetFileTime((HANDLE)v15, &CreationTime, &CreationTime, &CreationTime) )
    {
      LastFailureAsHRESULT = GetLastFailureAsHRESULT(v41);
      v17 = 254;
      goto LABEL_3;
    }
    LastFailureAsHRESULT = 0;
    v53 = 254;
    if ( v19 && !v60 )
    {
      if ( !GetSecurityDescriptorDacl(v19, &bDaclPresent, &pDacl, &bDaclDefaulted) )
      {
        LastFailureAsHRESULT = GetLastFailureAsHRESULT(v42);
        v17 = 258;
        goto LABEL_3;
      }
      LastFailureAsHRESULT = 0;
      v53 = 258;
      if ( !GetSecurityDescriptorSacl(v19, &bSaclPresent, &pSacl, &bSaclDefaulted) )
      {
        LastFailureAsHRESULT = GetLastFailureAsHRESULT(v43);
        v17 = 259;
        goto LABEL_3;
      }
      v44 = 0;
      LastFailureAsHRESULT = 0;
      v53 = 259;
      if ( bDaclPresent )
        v44 = 4;
      if ( bSaclPresent )
        v44 |= 0x18u;
      SetKernelObjectSecurity((HANDLE)v15, v44, v19);
    }
    if ( pSecurityDescriptor )
    {
      v45 = Src;
      if ( Src )
      {
        if ( cb[0] )
        {
          v46 = cb[0];
          v47 = CoTaskMemAlloc(cb[0]);
          *((_QWORD *)this + 7) = v47;
          v17 = 281;
          if ( !v47 )
          {
            LastFailureAsHRESULT = -2147024882;
            goto LABEL_3;
          }
          LastFailureAsHRESULT = 0;
          v53 = 281;
          memcpy_0(v47, v45, v46);
        }
      }
    }
    *((_DWORD *)this + 16) = 0;
    v48 = (char *)*((_QWORD *)this + 5);
    if ( (unsigned __int64)(v48 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v48);
    *((_QWORD *)this + 5) = v15;
    v15 = -1;
  }
LABEL_91:
  v49 = LastFailureAsHRESULT;
  CBsString::_Release((CBsString *)&lpFileName);
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)FileW);
  if ( (unsigned __int64)(v15 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)v15);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT);
  return v49;
}

```

## disassembly

```asm
0x180046410  push    rbp
0x180046412  push    rbx
0x180046413  push    rsi
0x180046414  push    rdi
0x180046415  push    r12
0x180046417  push    r13
0x180046419  push    r14
0x18004641b  push    r15
0x18004641d  lea     rbp, [rsp-58h]
0x180046422  sub     rsp, 158h
0x180046429  mov     rax, cs:__security_cookie
0x180046430  xor     rax, rsp
0x180046433  mov     [rbp+90h+var_48], rax
0x180046437  mov     [rbp+90h+dwDesiredAccess], r9d
0x18004643b  mov     [rbp+90h+lpShortName], r8
0x18004643f  mov     r12, rdx
0x180046442  mov     qword ptr [rbp+90h+cb+4], rdx
0x180046446  mov     r14, rcx
0x180046449  mov     rax, [rbp+90h+arg_38]
0x180046450  mov     [rbp+90h+pSecurityDescriptor], rax
0x180046454  mov     rsi, [rbp+90h+SecurityDescriptor]
0x18004645b  mov     [rbp+90h+Src], rsi
0x18004645f  mov     eax, [rbp+90h+arg_20]
0x180046465  mov     [rbp+90h+dwShareMode], eax
0x180046468  mov     eax, [rbp+90h+arg_30]
0x18004646e  mov     dword ptr [rbp+90h+cb], eax
0x180046471  mov     r13d, [rbp+90h+arg_48]
0x180046478  mov     [rbp+90h+var_FC], r13d
0x18004647c  mov     eax, [rbp+90h+arg_50]
0x180046482  mov     [rbp+90h+var_104], eax
0x180046485  mov     r9d, 1; unsigned __int16
0x18004648b  lea     r8d, [r9+57h]; unsigned __int16
0x18004648f  lea     rdx, aCsdstandardrea_4; "CSdStandardReadObj::CreateForRestore"
0x180046496  lea     rcx, [rsp+190h+var_148]; this
0x18004649b  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1800464a0  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800464a4  mov     rbx, rdx
0x1800464a7  mov     rdi, rdx
0x1800464aa  or      eax, 0FFFFFFFFh
0x1800464ad  mov     [rbp+90h+CreationTime.dwLowDateTime], eax
0x1800464b0  mov     [rbp+90h+CreationTime.dwHighDateTime], eax
0x1800464b3  xor     ecx, ecx
0x1800464b5  mov     [rsp+190h+InBuffer], cx
0x1800464ba  mov     [rbp+90h+BytesReturned], ecx
0x1800464bd  xorps   xmm0, xmm0
0x1800464c0  xor     eax, eax
0x1800464c2  movups  [rbp+90h+var_98], xmm0
0x1800464c6  mov     [rbp+90h+var_88], rax
0x1800464ca  mov     [rbp+90h+pDacl], rcx
0x1800464ce  mov     [rbp+90h+pSacl], rcx
0x1800464d2  mov     [rbp+90h+bDaclPresent], ecx
0x1800464d5  mov     [rbp+90h+bSaclPresent], ecx
0x1800464d8  mov     [rbp+90h+bDaclDefaulted], ecx
0x1800464db  mov     [rbp+90h+bSaclDefaulted], ecx
0x1800464de  lea     rax, qword_1800EE510
0x1800464e5  mov     [rbp+90h+lpFileName], rax
0x1800464e9  mov     [rbp+90h+var_D8], rcx
0x1800464ed  movups  xmmword ptr [rbp+90h+IoStatusBlock], xmm0
0x1800464f1  mov     [rbp+90h+FileInformation], ecx
0x1800464f4  xorps   xmm1, xmm1
0x1800464f7  xor     eax, eax
0x1800464f9  movups  [rbp+90h+var_6C], xmm1
0x1800464fd  movups  [rbp+90h+var_5C], xmm1
0x180046501  mov     [rbp+90h+var_4C], eax
0x180046504  lea     eax, [rdx+73h]
0x180046507  test    r12, r12
0x18004650a  jnz     short loc_18004651E
0x18004650c  mov     [rsp+190h+var_148], 80070057h
0x180046514  mov     [rsp+190h+var_142], ax
0x180046519  jmp     loc_180046C15
0x18004651e  mov     [rsp+190h+var_144], ax
0x180046523  mov     eax, 73h ; 's'
0x180046528  cmp     [r14+28h], rdx
0x18004652c  jz      short loc_180046538
0x18004652e  mov     [rsp+190h+var_148], 81000036h
0x180046536  jmp     short loc_180046514
0x180046538  mov     [rsp+190h+var_148], ecx
0x18004653c  mov     [rsp+190h+var_144], ax
0x180046541  mov     r13, [rbp+90h+pSecurityDescriptor]
0x180046545  mov     r15, r13
0x180046548  test    r13, r13
0x18004654b  cmovz   r15, rsi
0x18004654f  mov     rdx, r12; unsigned __int16 *
0x180046552  lea     rcx, [rbp+90h+lpFileName]; this
0x180046556  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x18004655b  mov     [rsp+190h+var_148], eax
0x18004655f  test    eax, eax
0x180046561  mov     eax, 78h ; 'x'
0x180046566  js      short loc_180046514
0x180046568  mov     [rbp+90h+var_100], 0
0x18004656f  mov     [rsp+190h+var_144], ax
0x180046574  lea     edx, [rax-3Eh]; unsigned __int16
0x180046577  lea     rcx, [rbp+90h+lpFileName]; this
0x18004657b  call    ?ReverseFind@CBsString@@QEBAJG@Z; CBsString::ReverseFind(ushort)
0x180046580  test    eax, eax
0x180046582  jle     short loc_1800465BF
0x180046584  cmp     eax, dword ptr [rbp+90h+var_D8]
0x180046587  jnb     short loc_1800465BF
0x180046589  mov     ecx, eax
0x18004658b  mov     rsi, [rbp+90h+lpFileName]
0x18004658f  cmp     word ptr [rsi+rcx*2+2], 5Ch ; '\'
0x180046595  jz      short loc_1800465C3
0x180046597  mov     edx, eax; unsigned int
0x180046599  lea     rcx, [rbp+90h+lpFileName]; this
0x18004659d  call    ?SetLength@CBsString@@QEAAJK@Z; CBsString::SetLength(ulong)
0x1800465a2  mov     [rsp+190h+var_148], eax
0x1800465a6  test    eax, eax
0x1800465a8  mov     eax, 7Eh ; '~'
0x1800465ad  js      loc_180046514
0x1800465b3  mov     [rbp+90h+var_100], 1
0x1800465ba  mov     [rsp+190h+var_144], ax
0x1800465bf  mov     rsi, [rbp+90h+lpFileName]
0x1800465c3  cmp     [rbp+90h+arg_60], 0
0x1800465ca  jz      short loc_180046600
0x1800465cc  mov     rax, [r14]
0x1800465cf  mov     rdx, r12
0x1800465d2  mov     rcx, r14
0x1800465d5  mov     rax, [rax+70h]
0x1800465d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800465de  mov     [rsp+190h+var_148], eax
0x1800465e2  xor     r12d, r12d
0x1800465e5  test    eax, eax
0x1800465e7  mov     eax, 86h
0x1800465ec  js      loc_180046514
0x1800465f2  mov     [rsp+190h+var_144], ax
0x1800465f7  mov     [rbp+90h+var_FC], 2
0x1800465fe  jmp     short loc_180046603
0x180046600  xor     r12d, r12d
0x180046603  cmp     [rbp+90h+var_100], r12d
0x180046607  jz      loc_18004671B
0x18004660d  test    r13, r13
0x180046610  jz      loc_1800466F3
0x180046616  mov     [rsp+190h+hTemplateFile], r12; hTemplateFile
0x18004661b  mov     eax, [rbp+90h+var_104]
0x18004661e  mov     [rsp+190h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x180046622  mov     [rsp+190h+dwCreationDisposition], 3; dwCreationDisposition
0x18004662a  xor     r9d, r9d; lpSecurityAttributes
0x18004662d  xor     r8d, r8d; dwShareMode
0x180046630  mov     edx, 40000h; dwDesiredAccess
0x180046635  mov     rcx, rsi; lpFileName
0x180046638  call    cs:__imp_CreateFileW
0x18004663f  nop     dword ptr [rax+rax+00h]
0x180046644  mov     rdi, rax
0x180046647  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18004664b  jnz     short loc_180046660
0x18004664d  call    GetLastFailureAsHRESULT
0x180046652  mov     [rsp+190h+var_148], eax
0x180046656  mov     eax, 90h
0x18004665b  jmp     loc_180046514
0x180046660  mov     [rsp+190h+var_148], r12d
0x180046665  mov     eax, 90h
0x18004666a  mov     [rsp+190h+var_144], ax
0x18004666f  lea     r9, [rbp+90h+bDaclDefaulted]; lpbDaclDefaulted
0x180046673  lea     r8, [rbp+90h+pDacl]; pDacl
0x180046677  lea     rdx, [rbp+90h+bDaclPresent]; lpbDaclPresent
0x18004667b  mov     rcx, r13; pSecurityDescriptor
0x18004667e  call    cs:__imp_GetSecurityDescriptorDacl
0x180046685  nop     dword ptr [rax+rax+00h]
0x18004668a  test    eax, eax
0x18004668c  jnz     short loc_1800466A1
0x18004668e  call    GetLastFailureAsHRESULT
0x180046693  mov     [rsp+190h+var_148], eax
0x180046697  mov     eax, 93h
0x18004669c  jmp     loc_180046514
0x1800466a1  mov     [rsp+190h+var_148], r12d
0x1800466a6  mov     eax, 93h
0x1800466ab  mov     [rsp+190h+var_144], ax
0x1800466b0  cmp     [rbp+90h+bDaclPresent], r12d
0x1800466b4  jz      short loc_1800466F3
0x1800466b6  mov     r8, r13; SecurityDescriptor
0x1800466b9  mov     edx, 4; SecurityInformation
0x1800466be  mov     rcx, rdi; Handle
0x1800466c1  call    cs:__imp_SetKernelObjectSecurity
0x1800466c8  nop     dword ptr [rax+rax+00h]
0x1800466cd  test    eax, eax
0x1800466cf  jnz     short loc_1800466E4
0x1800466d1  call    GetLastFailureAsHRESULT
0x1800466d6  mov     [rsp+190h+var_148], eax
0x1800466da  mov     eax, 97h
0x1800466df  jmp     loc_180046514
0x1800466e4  mov     [rsp+190h+var_148], r12d
0x1800466e9  mov     eax, 97h
0x1800466ee  mov     [rsp+190h+var_144], ax
0x1800466f3  mov     rax, [r14]
0x1800466f6  mov     rdx, rsi
0x1800466f9  mov     rcx, r14
0x1800466fc  mov     rax, [rax+70h]
0x180046700  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046705  mov     [rsp+190h+var_148], eax
0x180046709  test    eax, eax
0x18004670b  mov     eax, 0A0h
0x180046710  js      loc_180046514
0x180046716  mov     [rsp+190h+var_144], ax
0x18004671b  test    r15, r15
0x18004671e  jz      short loc_180046733
0x180046720  mov     dword ptr [rbp+90h+var_88], r12d
0x180046724  mov     dword ptr [rbp+90h+var_98], 18h
0x18004672b  mov     qword ptr [rbp+90h+var_98+8], r15
0x18004672f  lea     r12, [rbp+90h+var_98]
0x180046733  mov     r13d, [rbp+90h+var_104]
0x180046737  and     r13d, 0FFFFFFF8h
0x18004673b  mov     dword ptr [r14+30h], 0
0x180046743  mov     [rsp+190h+hTemplateFile], 0; hTemplateFile
0x18004674c  mov     [rsp+190h+dwFlagsAndAttributes], r13d; dwFlagsAndAttributes
0x180046751  mov     eax, [rbp+90h+var_FC]
0x180046754  mov     [rsp+190h+dwCreationDisposition], eax; dwCreationDisposition
0x180046758  mov     r9, r12; lpSecurityAttributes
0x18004675b  mov     r8d, [rbp+90h+dwShareMode]; dwShareMode
0x18004675f  mov     edx, [rbp+90h+dwDesiredAccess]; dwDesiredAccess
0x180046762  mov     rsi, qword ptr [rbp+90h+cb+4]
0x180046766  mov     rcx, rsi; lpFileName
0x180046769  call    cs:__imp_CreateFileW
0x180046770  nop     dword ptr [rax+rax+00h]
0x180046775  mov     rbx, rax
0x180046778  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18004677c  jnz     short loc_18004679E
0x18004677e  call    GetLastFailureAsHRESULT
0x180046783  mov     [rsp+190h+var_148], eax
0x180046787  mov     eax, 0B4h
0x18004678c  mov     [rsp+190h+var_142], ax
0x180046791  mov     [rsp+190h+var_140], 1
0x180046799  jmp     loc_180046C15
0x18004679e  mov     [rsp+190h+var_148], 0
0x1800467a6  mov     eax, 0B4h
0x1800467ab  mov     [rsp+190h+var_144], ax
0x1800467b0  mov     dword ptr [r14+30h], 1
0x1800467b8  test    r15, r15
0x1800467bb  jz      loc_180046856
0x1800467c1  test    rbx, rbx
0x1800467c4  jz      short loc_1800467D9
0x1800467c6  mov     rcx, rbx; hObject
0x1800467c9  call    cs:__imp_CloseHandle
0x1800467d0  nop     dword ptr [rax+rax+00h]
0x1800467d5  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800467d9  mov     [rsp+190h+hTemplateFile], 0; hTemplateFile
0x1800467e2  mov     [rsp+190h+dwFlagsAndAttributes], r13d; dwFlagsAndAttributes
0x1800467e7  mov     [rsp+190h+dwCreationDisposition], 3; dwCreationDisposition
0x1800467ef  mov     r9, r12; lpSecurityAttributes
0x1800467f2  mov     r8d, [rbp+90h+dwShareMode]; dwShareMode
0x1800467f6  mov     edx, [rbp+90h+dwDesiredAccess]; dwDesiredAccess
0x1800467f9  mov     rcx, rsi; lpFileName
0x1800467fc  call    cs:__imp_CreateFileW
0x180046803  nop     dword ptr [rax+rax+00h]
0x180046808  mov     rsi, rax
0x18004680b  lea     rcx, [rbx-1]
0x18004680f  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180046813  ja      short loc_180046824
0x180046815  mov     rcx, rbx; hObject
0x180046818  call    cs:__imp_CloseHandle
0x18004681f  nop     dword ptr [rax+rax+00h]
0x180046824  mov     rbx, rsi
0x180046827  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18004682b  jnz     short loc_180046840
0x18004682d  call    GetLastFailureAsHRESULT
0x180046832  mov     [rsp+190h+var_148], eax
0x180046836  mov     eax, 0C2h
0x18004683b  jmp     loc_180046514
0x180046840  mov     [rsp+190h+var_148], 0
0x180046848  mov     eax, 0C2h
0x18004684d  mov     [rsp+190h+var_144], ax
0x180046852  mov     rsi, qword ptr [rbp+90h+cb+4]
0x180046856  mov     rax, [rbp+90h+lpShortName]
0x18004685a  test    rax, rax
0x18004685d  jz      short loc_1800468A3
0x18004685f  mov     rdx, rax; lpShortName
0x180046862  mov     rcx, rbx; hFile
0x180046865  call    cs:__imp_SetFileShortNameW
0x18004686c  nop     dword ptr [rax+rax+00h]
0x180046871  test    eax, eax
0x180046873  jnz     short loc_1800468A3
0x180046875  test    [rbp+90h+arg_58], 1
0x18004687c  jnz     short loc_1800468A3
0x18004687e  call    GetLastFailureAsHRESULT
0x180046883  xor     ecx, ecx
0x180046885  cmp     eax, 800700B7h
0x18004688a  cmovz   eax, ecx
0x18004688d  mov     [rsp+190h+var_148], eax
0x180046891  test    eax, eax
0x180046893  mov     eax, 0D0h
0x180046898  js      loc_180046514
0x18004689e  mov     [rsp+190h+var_144], ax
0x1800468a3  mov     [rsp+190h+dwCreationDisposition], 4; FileInformationClass
0x1800468ab  mov     r9d, 28h ; '('; Length
0x1800468b1  lea     r8, [rbp+90h+FileInformation]; FileInformation
0x1800468b5  lea     rdx, [rbp+90h+IoStatusBlock]; IoStatusBlock
0x1800468b9  mov     rcx, rbx; FileHandle
0x1800468bc  call    cs:__imp_NtQueryInformationFile
0x1800468c3  nop     dword ptr [rax+rax+00h]
0x1800468c8  mov     ecx, eax
0x1800468ca  call    HRESULTFromNTSTATUS
0x1800468cf  mov     [rsp+190h+var_148], eax
0x1800468d3  test    eax, eax
0x1800468d5  mov     eax, 0DAh
0x1800468da  js      loc_180046514
0x1800468e0  mov     [rsp+190h+var_144], ax
0x1800468e5  test    dword ptr [rbp+90h+var_5C+0Ch], 4000h
0x1800468ec  jz      loc_1800469C4
0x1800468f2  lea     rax, [rbx-1]
0x1800468f6  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800468fa  ja      short loc_18004690F
  ... truncated ...
```
