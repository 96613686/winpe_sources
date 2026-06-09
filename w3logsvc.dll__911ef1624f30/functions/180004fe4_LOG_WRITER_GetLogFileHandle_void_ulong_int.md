# LOG_WRITER::GetLogFileHandle(void * *,ulong,int)

- ea: `0x180004fe4`
- end: `0x180005451`
- name: `?GetLogFileHandle@LOG_WRITER@@AEAAJPEAPEAXKH@Z`
- size: `1133`
- prototype: `__int64 __fastcall(LOG_WRITER *__hidden this, void **, unsigned int, int)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180004bec`
- `0x180005ccc`

## callees

- `0x180004bec`
- `0x180004fe4`
- `0x180005458`
- `0x180005880`
- `0x180005960`
- `0x180005b3c`
- `0x180005f04`
- `0x18000e97a`
- `0x18000e9a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800051d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005291`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800051d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005291`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180005323`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180005333`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180005323`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180005333`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180005359`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180005359`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800053e0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800053e0`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180005430`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180005430`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180005428`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180005428`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x180005287`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x180005287`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800051cb`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800051cb`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1800052f6`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1800052f6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800053ca`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800053ca`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800052b6`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800052b6`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToTzSpecificLocalTime` at `0x1800052e0`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToTzSpecificLocalTime` at `0x1800052e0`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800051f9`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800051f9`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x180005161`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x180005161`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800050f8`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180005103`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800053a4`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800053af`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800050f8`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180005103`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800053a4`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800053af`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800050b3`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800050d9`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800050b3`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800050d9`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x1800050e8`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x180005390`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x1800050e8`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x180005390`
- `iisutil!?EqualsNoCase@STRU@@QEBA_NPEBG@Z` at `0x180005314`
- `iisutil!?EqualsNoCase@STRU@@QEBA_NPEBG@Z` at `0x180005314`

## pseudocode

```c
__int64 __fastcall LOG_WRITER::GetLogFileHandle(LOG_WRITER *this, void **a2, unsigned int a3, int a4)
{
  signed int LogFilePath; // ebx
  DWORD v9; // edi
  signed int NamedSecurityInfoW; // eax
  bool v11; // cc
  int v12; // ebx
  signed int LastError; // eax
  void *v14; // rcx
  __int64 v15; // rax
  HANDLE CurrentProcess; // rbx
  void *v17; // rdi
  HANDLE v18; // rax
  HANDLE v19; // r9
  struct _SYSTEMTIME *v21; // rcx
  __int64 v22; // rax
  PSECURITY_DESCRIPTOR hMem; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE TargetHandle; // [rsp+48h] [rbp-B8h] BYREF
  struct _FILETIME CreationTime; // [rsp+50h] [rbp-B0h] BYREF
  union _LARGE_INTEGER FileSize; // [rsp+58h] [rbp-A8h] BYREF
  PSID ppsidOwner; // [rsp+60h] [rbp-A0h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v29[32]; // [rsp+80h] [rbp-80h] BYREF
  LPCWSTR lpFileName; // [rsp+A0h] [rbp-60h]
  _BYTE v31[56]; // [rsp+B8h] [rbp-48h] BYREF
  SYSTEMTIME UniversalTime; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int16 v33[256]; // [rsp+100h] [rbp+0h] BYREF
  unsigned __int16 v34[256]; // [rsp+300h] [rbp+200h] BYREF

  hMem = 0;
  memset(&SecurityAttributes, 0, sizeof(SecurityAttributes));
  ppsidOwner = 0;
  TargetHandle = (HANDLE)-1LL;
  if ( *((_QWORD *)this + 79) == -1
    || (unsigned int)LOG_WRITER::NeedToRolloverToNewLogFile(this, *((_QWORD *)this + 80), a3) )
  {
    memset_0(v33, 0, sizeof(v33));
    STRU::STRU((STRU *)v29, v33, 0x100u);
    memset_0(v34, 0, sizeof(v34));
    STRU::STRU((STRU *)v31, v34, 0x100u);
    LogFilePath = STRU::Copy((STRU *)v31, (LOG_WRITER *)((char *)this + 16));
    if ( LogFilePath < 0 )
      goto LABEL_7;
    if ( *((_QWORD *)this + 79) != -1 )
      LOG_WRITER::ResetWriter(this);
    LogFilePath = LOG_WRITER::GetLogFilePath(this, (struct STRU *)v29, a3);
    if ( LogFilePath < 0 )
      goto LABEL_7;
    v9 = 1;
    NamedSecurityInfoW = GetNamedSecurityInfoW(*((LPCWSTR *)this + 13), SE_FILE_OBJECT, 1u, &ppsidOwner, 0, 0, 0, &hMem);
    LogFilePath = NamedSecurityInfoW;
    v11 = NamedSecurityInfoW <= 0;
    if ( NamedSecurityInfoW )
      goto LABEL_12;
    SecurityAttributes.nLength = 24;
    SecurityAttributes.lpSecurityDescriptor = hMem;
    SecurityAttributes.bInheritHandle = 0;
    v12 = *((_DWORD *)this + 169) != 0 ? 1 : 5;
    while ( 1 )
    {
      *((_QWORD *)this + 79) = CreateFileW(lpFileName, 4u, 1u, &SecurityAttributes, 4u, 0x80u, 0);
      LastError = GetLastError();
      if ( *((_QWORD *)this + 79) != -1 )
        break;
      if ( !--v12 || LastError == 1307 )
        break;
      v9 *= 5;
      Sleep(v9);
    }
    v14 = (void *)*((_QWORD *)this + 79);
    if ( v14 == (void *)-1LL )
    {
      if ( LastError > 0 )
        LogFilePath = (unsigned __int16)LastError | 0x80070000;
      else
        LogFilePath = LastError;
      if ( LastError == 1307 )
        LOG_WRITER::LogW3LogSvcEvent(this, 3221231481LL, lpFileName, (unsigned int)LogFilePath, 2);
      else
        LOG_WRITER::LogW3LogSvcEvent(this, 3221231475LL, lpFileName, (unsigned int)LogFilePath, 3);
      *((_DWORD *)this + 169) = 1;
      goto LABEL_7;
    }
    *((_DWORD *)this + 169) = 0;
    if ( LastError == 183 )
    {
      CreationTime = 0;
      FileSize.QuadPart = 0;
      if ( !GetFileTime(v14, &CreationTime, 0, 0) )
        goto LABEL_29;
      UniversalTime = 0;
      if ( !FileTimeToSystemTime(&CreationTime, (LPSYSTEMTIME)((char *)this + 648)) )
        goto LABEL_29;
      v15 = *((_QWORD *)this + 1);
      if ( v15 )
      {
        if ( *(_DWORD *)(v15 + 4) == 1 )
        {
          UniversalTime = *(SYSTEMTIME *)((char *)this + 648);
          if ( !SystemTimeToTzSpecificLocalTime(0, &UniversalTime, (LPSYSTEMTIME)((char *)this + 648)) )
            goto LABEL_29;
        }
      }
      if ( !GetFileSizeEx(*((HANDLE *)this + 79), &FileSize) )
        goto LABEL_29;
      *((union _LARGE_INTEGER *)this + 80) = FileSize;
      if ( STRU::EqualsNoCase((STRU *)v31, lpFileName) && !a4 )
      {
LABEL_40:
        LogFilePath = STRU::Copy((LOG_WRITER *)((char *)this + 16), (const struct STRU *)v29);
        if ( LogFilePath >= 0 )
        {
          STRU::~STRU((STRU *)v31);
          STRU::~STRU((STRU *)v29);
LABEL_42:
          *a2 = (void *)*((_QWORD *)this + 79);
          goto LABEL_43;
        }
LABEL_7:
        STRU::~STRU((STRU *)v31);
        STRU::~STRU((STRU *)v29);
        goto LABEL_43;
      }
      CurrentProcess = GetCurrentProcess();
      v17 = (void *)*((_QWORD *)this + 79);
      v18 = GetCurrentProcess();
      if ( !DuplicateHandle(v18, v17, CurrentProcess, &TargetHandle, 0, 0, 2u) )
      {
LABEL_29:
        NamedSecurityInfoW = GetLastError();
        LogFilePath = NamedSecurityInfoW;
        v11 = NamedSecurityInfoW <= 0;
LABEL_12:
        if ( !v11 )
          LogFilePath = (unsigned __int16)NamedSecurityInfoW | 0x80070000;
        goto LABEL_7;
      }
      v19 = TargetHandle;
    }
    else
    {
      v21 = (struct _SYSTEMTIME *)((char *)this + 648);
      v22 = *((_QWORD *)this + 1);
      if ( v22 && *(_DWORD *)(v22 + 4) == 1 )
        GetLocalTime(v21);
      else
        GetSystemTime(v21);
      LogFilePath = LOG_WRITER::UpdateHeaders(this);
      if ( LogFilePath < 0 )
        goto LABEL_7;
      v19 = 0;
    }
    LogFilePath = LOG_WRITER::Flush(this, (LOG_WRITER *)((char *)this + 184), 0, v19);
    if ( LogFilePath < 0 )
      goto LABEL_7;
    goto LABEL_40;
  }
  LogFilePath = 0;
  if ( !a4 )
    goto LABEL_42;
  LogFilePath = LOG_WRITER::Flush(this, (LOG_WRITER *)((char *)this + 184), 0, 0);
  if ( LogFilePath >= 0 )
    goto LABEL_42;
LABEL_43:
  if ( hMem )
  {
    LocalFree(hMem);
    hMem = 0;
  }
  if ( TargetHandle != (HANDLE)-1LL )
    CloseHandle(TargetHandle);
  return (unsigned int)LogFilePath;
}

```

## disassembly

```asm
0x180004fe4  mov     [rsp-8+arg_18], rbx
0x180004fe9  push    rbp
0x180004fea  push    rsi
0x180004feb  push    rdi
0x180004fec  push    r12
0x180004fee  push    r13
0x180004ff0  push    r14
0x180004ff2  push    r15
0x180004ff4  lea     rbp, [rsp-410h]
0x180004ffc  sub     rsp, 510h
0x180005003  mov     rax, cs:__security_cookie
0x18000500a  xor     rax, rsp
0x18000500d  mov     [rbp+440h+var_40], rax
0x180005014  mov     r14d, r9d
0x180005017  mov     edi, r8d
0x18000501a  mov     r12, rdx
0x18000501d  mov     rsi, rcx
0x180005020  xor     r13d, r13d
0x180005023  mov     [rsp+540h+hMem], r13
0x180005028  xorps   xmm0, xmm0
0x18000502b  xor     eax, eax
0x18000502d  movups  xmmword ptr [rsp+540h+SecurityAttributes.nLength], xmm0
0x180005032  mov     qword ptr [rsp+540h+SecurityAttributes.bInheritHandle], rax
0x180005037  mov     [rsp+540h+ppsidOwner], r13
0x18000503c  mov     [rsp+540h+TargetHandle], 0FFFFFFFFFFFFFFFFh
0x180005045  cmp     qword ptr [rcx+278h], 0FFFFFFFFFFFFFFFFh
0x18000504d  jz      short loc_18000508F
0x18000504f  mov     rdx, [rcx+280h]; unsigned __int64
0x180005056  call    ?NeedToRolloverToNewLogFile@LOG_WRITER@@AEAAH_KK@Z; LOG_WRITER::NeedToRolloverToNewLogFile(unsigned __int64,ulong)
0x18000505b  test    eax, eax
0x18000505d  jnz     short loc_18000508F
0x18000505f  mov     ebx, r13d
0x180005062  test    r14d, r14d
0x180005065  jz      loc_1800053B5
0x18000506b  lea     rdx, [rsi+0B8h]; struct STRA *
0x180005072  xor     r9d, r9d; void *
0x180005075  xor     r8d, r8d; int
0x180005078  mov     rcx, rsi; this
0x18000507b  call    ?Flush@LOG_WRITER@@AEAAJPEAVSTRA@@HPEAX@Z; LOG_WRITER::Flush(STRA *,int,void *)
0x180005080  mov     ebx, eax
0x180005082  test    eax, eax
0x180005084  jns     loc_1800053B5
0x18000508a  jmp     loc_1800053C0
0x18000508f  mov     r15d, 200h
0x180005095  mov     r8d, r15d; Size
0x180005098  xor     edx, edx; Val
0x18000509a  lea     rcx, [rbp+440h+var_440]; void *
0x18000509e  call    memset_0
0x1800050a3  mov     ebx, 100h
0x1800050a8  mov     r8d, ebx
0x1800050ab  lea     rdx, [rbp+440h+var_440]
0x1800050af  lea     rcx, [rbp+440h+var_4C0]
0x1800050b3  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x1800050b9  nop
0x1800050ba  mov     r8d, r15d; Size
0x1800050bd  xor     edx, edx; Val
0x1800050bf  lea     rcx, [rbp+440h+var_240]; void *
0x1800050c6  call    memset_0
0x1800050cb  mov     r8d, ebx
0x1800050ce  lea     rdx, [rbp+440h+var_240]
0x1800050d5  lea     rcx, [rbp+440h+var_488]
0x1800050d9  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x1800050df  nop
0x1800050e0  lea     rdx, [rsi+10h]
0x1800050e4  lea     rcx, [rbp+440h+var_488]
0x1800050e8  call    cs:__imp_?Copy@STRU@@QEAAJAEBV1@@Z; STRU::Copy(STRU const &)
0x1800050ee  mov     ebx, eax
0x1800050f0  test    eax, eax
0x1800050f2  jns     short loc_18000510E
0x1800050f4  lea     rcx, [rbp+440h+var_488]
0x1800050f8  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800050fe  nop
0x1800050ff  lea     rcx, [rbp+440h+var_4C0]
0x180005103  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180005109  jmp     loc_1800053C0
0x18000510e  cmp     qword ptr [rsi+278h], 0FFFFFFFFFFFFFFFFh
0x180005116  jz      short loc_180005120
0x180005118  mov     rcx, rsi; this
0x18000511b  call    ?ResetWriter@LOG_WRITER@@AEAAXXZ; LOG_WRITER::ResetWriter(void)
0x180005120  mov     r8d, edi; unsigned int
0x180005123  lea     rdx, [rbp+440h+var_4C0]; struct STRU *
0x180005127  mov     rcx, rsi; this
0x18000512a  call    ?GetLogFilePath@LOG_WRITER@@AEAAJPEAVSTRU@@K@Z; LOG_WRITER::GetLogFilePath(STRU *,ulong)
0x18000512f  mov     ebx, eax
0x180005131  test    eax, eax
0x180005133  js      short loc_1800050F4
0x180005135  lea     rax, [rsp+540h+hMem]
0x18000513a  mov     [rsp+540h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x18000513f  mov     [rsp+540h+ppSacl], r13; ppSacl
0x180005144  mov     [rsp+540h+ppDacl], r13; ppDacl
0x180005149  mov     [rsp+540h+ppsidGroup], r13; ppsidGroup
0x18000514e  lea     r9, [rsp+540h+ppsidOwner]; ppsidOwner
0x180005153  mov     edi, 1
0x180005158  mov     r8d, edi; SecurityInfo
0x18000515b  mov     edx, edi; ObjectType
0x18000515d  mov     rcx, [rsi+68h]; pObjectName
0x180005161  call    cs:__imp_GetNamedSecurityInfoW
0x180005167  mov     ebx, eax
0x180005169  test    eax, eax
0x18000516b  jz      short loc_18000517D
0x18000516d  jle     short loc_1800050F4
0x18000516f  movzx   ebx, ax
0x180005172  or      ebx, 80070000h
0x180005178  jmp     loc_1800050F4
0x18000517d  mov     [rsp+540h+SecurityAttributes.nLength], 18h
0x180005185  mov     rax, [rsp+540h+hMem]
0x18000518a  mov     [rsp+540h+SecurityAttributes.lpSecurityDescriptor], rax
0x18000518f  mov     [rsp+540h+SecurityAttributes.bInheritHandle], r13d
0x180005194  mov     eax, [rsi+2A4h]
0x18000519a  neg     eax
0x18000519c  sbb     ebx, ebx
0x18000519e  and     ebx, 0FFFFFFFCh
0x1800051a1  add     ebx, 5
0x1800051a4  mov     [rsp+540h+ppSacl], r13; hTemplateFile
0x1800051a9  mov     dword ptr [rsp+540h+ppDacl], 80h; dwFlagsAndAttributes
0x1800051b1  mov     dword ptr [rsp+540h+ppsidGroup], 4; dwCreationDisposition
0x1800051b9  lea     r9, [rsp+540h+SecurityAttributes]; lpSecurityAttributes
0x1800051be  mov     edx, 4; dwDesiredAccess
0x1800051c3  lea     r8d, [rdx-3]; dwShareMode
0x1800051c7  mov     rcx, [rbp+440h+lpFileName]; lpFileName
0x1800051cb  call    cs:__imp_CreateFileW
0x1800051d1  mov     [rsi+278h], rax
0x1800051d8  call    cs:__imp_GetLastError
0x1800051de  cmp     qword ptr [rsi+278h], 0FFFFFFFFFFFFFFFFh
0x1800051e6  jnz     short loc_180005201
0x1800051e8  add     ebx, 0FFFFFFFFh
0x1800051eb  jz      short loc_180005201
0x1800051ed  cmp     eax, 51Bh
0x1800051f2  jz      short loc_180005201
0x1800051f4  lea     edi, [rdi+rdi*4]
0x1800051f7  mov     ecx, edi; dwMilliseconds
0x1800051f9  call    cs:__imp_Sleep
0x1800051ff  jmp     short loc_1800051A4
0x180005201  mov     rcx, [rsi+278h]; hFile
0x180005208  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000520c  jnz     short loc_180005260
0x18000520e  test    eax, eax
0x180005210  jg      short loc_180005216
0x180005212  mov     ebx, eax
0x180005214  jmp     short loc_18000521F
0x180005216  movzx   ebx, ax
0x180005219  or      ebx, 80070000h
0x18000521f  mov     r9d, ebx
0x180005222  mov     r8, [rbp+440h+lpFileName]
0x180005226  mov     rcx, rsi
0x180005229  cmp     eax, 51Bh
0x18000522e  jnz     short loc_18000523F
0x180005230  mov     dword ptr [rsp+540h+ppsidGroup], 2
0x180005238  mov     edx, 0C0001779h
0x18000523d  jmp     short loc_18000524C
0x18000523f  mov     dword ptr [rsp+540h+ppsidGroup], 3
0x180005247  mov     edx, 0C0001773h
0x18000524c  call    ?LogW3LogSvcEvent@LOG_WRITER@@AEAAXKPEBGKW4LOG_SVC_EVENT@@@Z; LOG_WRITER::LogW3LogSvcEvent(ulong,ushort const *,ulong,LOG_SVC_EVENT)
0x180005251  mov     dword ptr [rsi+2A4h], 1
0x18000525b  jmp     loc_1800050F4
0x180005260  mov     [rsi+2A4h], r13d
0x180005267  cmp     eax, 0B7h
0x18000526c  jnz     loc_180005412
0x180005272  mov     qword ptr [rsp+540h+CreationTime.dwLowDateTime], r13
0x180005277  mov     qword ptr [rsp+540h+FileSize], r13
0x18000527c  xor     r9d, r9d; lpLastWriteTime
0x18000527f  xor     r8d, r8d; lpLastAccessTime
0x180005282  lea     rdx, [rsp+540h+CreationTime]; lpCreationTime
0x180005287  call    cs:__imp_GetFileTime
0x18000528d  test    eax, eax
0x18000528f  jnz     short loc_1800052A0
0x180005291  call    cs:__imp_GetLastError
0x180005297  mov     ebx, eax
0x180005299  test    eax, eax
0x18000529b  jmp     loc_18000516D
0x1800052a0  lea     rbx, [rsi+288h]
0x1800052a7  xorps   xmm0, xmm0
0x1800052aa  movups  xmmword ptr [rbp+440h+UniversalTime.wYear], xmm0
0x1800052ae  mov     rdx, rbx; lpSystemTime
0x1800052b1  lea     rcx, [rsp+540h+CreationTime]; lpFileTime
0x1800052b6  call    cs:__imp_FileTimeToSystemTime
0x1800052bc  test    eax, eax
0x1800052be  jz      short loc_180005291
0x1800052c0  mov     rax, [rsi+8]
0x1800052c4  test    rax, rax
0x1800052c7  jz      short loc_1800052EA
0x1800052c9  cmp     dword ptr [rax+4], 1
0x1800052cd  jnz     short loc_1800052EA
0x1800052cf  movups  xmm0, xmmword ptr [rbx]
0x1800052d2  movdqu  xmmword ptr [rbp+440h+UniversalTime.wYear], xmm0
0x1800052d7  mov     r8, rbx; lpLocalTime
0x1800052da  lea     rdx, [rbp+440h+UniversalTime]; lpUniversalTime
0x1800052de  xor     ecx, ecx; lpTimeZoneInformation
0x1800052e0  call    cs:__imp_SystemTimeToTzSpecificLocalTime
0x1800052e6  test    eax, eax
0x1800052e8  jz      short loc_180005291
0x1800052ea  lea     rdx, [rsp+540h+FileSize]; lpFileSize
0x1800052ef  mov     rcx, [rsi+278h]; hFile
0x1800052f6  call    cs:__imp_GetFileSizeEx
0x1800052fc  test    eax, eax
0x1800052fe  jz      short loc_180005291
0x180005300  mov     rax, qword ptr [rsp+540h+FileSize]
0x180005305  mov     [rsi+280h], rax
0x18000530c  mov     rdx, [rbp+440h+lpFileName]
0x180005310  lea     rcx, [rbp+440h+var_488]
0x180005314  call    cs:__imp_?EqualsNoCase@STRU@@QEBA_NPEBG@Z; STRU::EqualsNoCase(ushort const *)
0x18000531a  test    al, al
0x18000531c  jz      short loc_180005323
0x18000531e  test    r14d, r14d
0x180005321  jz      short loc_180005388
0x180005323  call    cs:__imp_GetCurrentProcess
0x180005329  mov     rbx, rax
0x18000532c  mov     rdi, [rsi+278h]
0x180005333  call    cs:__imp_GetCurrentProcess
0x180005339  mov     dword ptr [rsp+540h+ppSacl], 2; dwOptions
0x180005341  mov     dword ptr [rsp+540h+ppDacl], r13d; bInheritHandle
0x180005346  mov     dword ptr [rsp+540h+ppsidGroup], r13d; dwDesiredAccess
0x18000534b  lea     r9, [rsp+540h+TargetHandle]; lpTargetHandle
0x180005350  mov     r8, rbx; hTargetProcessHandle
0x180005353  mov     rdx, rdi; hSourceHandle
0x180005356  mov     rcx, rax; hSourceProcessHandle
0x180005359  call    cs:__imp_DuplicateHandle
0x18000535f  test    eax, eax
0x180005361  jz      loc_180005291
0x180005367  mov     r9, [rsp+540h+TargetHandle]; void *
0x18000536c  lea     rdx, [rsi+0B8h]; struct STRA *
0x180005373  xor     r8d, r8d; int
0x180005376  mov     rcx, rsi; this
0x180005379  call    ?Flush@LOG_WRITER@@AEAAJPEAVSTRA@@HPEAX@Z; LOG_WRITER::Flush(STRA *,int,void *)
0x18000537e  mov     ebx, eax
0x180005380  test    eax, eax
0x180005382  js      loc_1800050F4
0x180005388  lea     rdx, [rbp+440h+var_4C0]
0x18000538c  lea     rcx, [rsi+10h]
0x180005390  call    cs:__imp_?Copy@STRU@@QEAAJAEBV1@@Z; STRU::Copy(STRU const &)
0x180005396  mov     ebx, eax
0x180005398  lea     rcx, [rbp+440h+var_488]
0x18000539c  test    eax, eax
0x18000539e  js      loc_1800050F8
0x1800053a4  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800053aa  nop
0x1800053ab  lea     rcx, [rbp+440h+var_4C0]
0x1800053af  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800053b5  mov     rax, [rsi+278h]
0x1800053bc  mov     [r12], rax
0x1800053c0  mov     rcx, [rsp+540h+hMem]; hMem
0x1800053c5  test    rcx, rcx
0x1800053c8  jz      short loc_1800053D5
0x1800053ca  call    cs:__imp_LocalFree
0x1800053d0  mov     [rsp+540h+hMem], r13
0x1800053d5  mov     rcx, [rsp+540h+TargetHandle]; hObject
0x1800053da  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800053de  jz      short loc_1800053E6
0x1800053e0  call    cs:__imp_CloseHandle
0x1800053e6  mov     eax, ebx
0x1800053e8  mov     rcx, [rbp+440h+var_40]
0x1800053ef  xor     rcx, rsp; StackCookie
0x1800053f2  call    __security_check_cookie
0x1800053f7  mov     rbx, [rsp+540h+arg_18]
0x1800053ff  add     rsp, 510h
0x180005406  pop     r15
0x180005408  pop     r14
0x18000540a  pop     r13
0x18000540c  pop     r12
0x18000540e  pop     rdi
0x18000540f  pop     rsi
0x180005410  pop     rbp
0x180005411  retn
0x180005412  lea     rcx, [rsi+288h]; lpSystemTime
0x180005419  mov     rax, [rsi+8]
0x18000541d  test    rax, rax
0x180005420  jz      short loc_180005430
0x180005422  cmp     dword ptr [rax+4], 1
0x180005426  jnz     short loc_180005430
0x180005428  call    cs:__imp_GetLocalTime
0x18000542e  jmp     short loc_180005436
0x180005430  call    cs:__imp_GetSystemTime
0x180005436  mov     rcx, rsi; this
0x180005439  call    ?UpdateHeaders@LOG_WRITER@@AEAAJXZ; LOG_WRITER::UpdateHeaders(void)
0x18000543e  mov     ebx, eax
0x180005440  test    eax, eax
0x180005442  js      loc_1800050F4
0x180005448  xor     r9d, r9d
0x18000544b  jmp     loc_18000536C
```
