# JobStore::SaveJobFile(ushort const *,ushort const *,ulong,ulong,void *,ulong)

- ea: `0x1800231b0`
- end: `0x18002379b`
- name: `?SaveJobFile@JobStore@@AEBAJPEBG0KKPEAXK@Z`
- size: `1515`
- prototype: `int(JobStore *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned int, void *, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x180022aa0`

## callees

- `0x18001fe10`
- `0x1800229a0`
- `0x1800231b0`
- `0x180054c80`
- `0x180059140`
- `0x18005de10`
- `0x180067290`
- `0x18006932c`
- `0x180082a40`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x180023375`
- `msvcrt!_wcsnicmp` at `0x180023375`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800234d8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800234d8`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002356a`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002359d`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002356a`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002359d`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x1800234fb`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x1800234fb`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002330c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002330c`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x180023499`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x180023499`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x1800235c7`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x1800235c7`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18002334f`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18002334f`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x180023391`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x180023391`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800234e7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023687`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800234e7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023687`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180023202`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180023202`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800236ff`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800236ff`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180023244`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180023244`

## pseudocode

```c
__int64 __fastcall JobStore::SaveJobFile(
        JobStore *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned int a4,
        unsigned int a5,
        void *a6,
        unsigned int a7)
{
  __int64 v8; // r15
  struct _SECURITY_ATTRIBUTES *v11; // rbx
  struct _SECURITY_ATTRIBUTES *v12; // rax
  int v14; // edx
  HANDLE FileW; // rsi
  __int64 v16; // rdi
  int v17; // edx
  tsched *v18; // rcx
  _QWORD *v19; // rcx
  unsigned int LastHrError; // eax
  unsigned int v21; // ebx
  int v22; // edx
  tsched *v23; // rcx
  _QWORD *v24; // rcx
  int v25; // edx
  int v26; // edx
  tsched *v27; // rcx
  int v28; // edx
  tsched *v29; // rcx
  int v30; // edx
  tsched *v31; // rcx
  _QWORD *v32; // rcx
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-C0h] BYREF
  __int16 Buffer; // [rsp+44h] [rbp-BCh] BYREF
  struct _SECURITY_ATTRIBUTES *v35; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v36[2]; // [rsp+50h] [rbp-B0h] BYREF
  struct _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR szFilePath[264]; // [rsp+A0h] [rbp-60h] BYREF

  v8 = a4;
  while ( !_InterlockedCompareExchange((volatile signed __int32 *)this + 23, 0, 0) )
    Sleep(0x64u);
  if ( !*(_DWORD *)(*((_QWORD *)this + 10) + 184LL) )
    return 0;
  v11 = 0;
  v35 = 0;
  if ( a6 )
  {
    v12 = (struct _SECURITY_ATTRIBUTES *)LocalAlloc(0, a7 + 24LL);
    v35 = v12;
    v11 = v12;
    if ( !v12 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          69,
          (unsigned int)WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids,
          (_DWORD)a2,
          14);
      }
      tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&v35);
      return 2147942414LL;
    }
    v12->lpSecurityDescriptor = a6;
    v12->nLength = a7 + 24;
    v12->bInheritHandle = 0;
  }
  FileW = CreateFileW(a2, 0x40000000u, 1u, v11, 4u, 0x8000080u, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    v16 = -1;
    goto LABEL_21;
  }
  memset(&FileInformation, 0, sizeof(FileInformation));
  if ( GetFinalPathNameByHandleW(FileW, szFilePath, 0x105u, 0) - 1 > 0x103 )
  {
    if ( (int)tsched::GetLastHrError(v18, v17) >= 0 )
    {
LABEL_20:
      v16 = (__int64)FileW;
      goto LABEL_21;
    }
  }
  else if ( !_wcsnicmp(szFilePath, a2, 0x105u)
         && GetFileInformationByHandle(FileW, &FileInformation)
         && FileInformation.nNumberOfLinks <= 1 )
  {
    goto LABEL_20;
  }
  v16 = -1;
  SetLastError(5u);
  CloseHandle(FileW);
LABEL_21:
  v19 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_0318f2e21e573bf245f738540b7f5294_Traceguids, v16);
      v19 = WPP_GLOBAL_Control;
    }
    if ( v19 != &WPP_GLOBAL_Control && (*((_DWORD *)v19 + 7) & 0x10000) != 0 && *((_BYTE *)v19 + 25) >= 4u )
      WPP_SF_S(v19[2], 15, WPP_0318f2e21e573bf245f738540b7f5294_Traceguids, 0);
  }
  v36[0] = v16;
  v36[1] = a2;
  if ( v16 == -1 )
  {
    LastHrError = tsched::GetLastHrError((tsched *)v19, v14);
    v21 = LastHrError;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        70,
        (unsigned int)WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids,
        (_DWORD)a2,
        LastHrError);
    }
    if ( v21 == -2147024891 )
    {
      memset(&FileInformation, 0, 36);
      if ( GetFileAttributesExW(a2, GetFileExInfoStandard, &FileInformation) )
      {
        if ( (FileInformation.dwFileAttributes & 0x10) != 0 )
          v21 = 183;
      }
    }
    goto LABEL_86;
  }
  if ( !SetEndOfFile((HANDLE)v16) )
  {
    v21 = tsched::GetLastHrError(v23, v22);
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_86;
    }
    v25 = 71;
LABEL_85:
    WPP_SF_Sd(v24[2], v25, (unsigned int)WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids, (_DWORD)a2, v21);
LABEL_86:
    tsched::JobsAutoHandle::Close((tsched::JobsAutoHandle *)v36);
    tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&v35);
    return v21;
  }
  NumberOfBytesWritten = 0;
  Buffer = -257;
  if ( !WriteFile((HANDLE)v16, &Buffer, 2u, &NumberOfBytesWritten, 0) || NumberOfBytesWritten != 2 )
  {
    v21 = tsched::GetLastHrError(v27, v26);
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_86;
    }
    v25 = 72;
    goto LABEL_85;
  }
  if ( !WriteFile((HANDLE)v16, a3, 2 * v8, &NumberOfBytesWritten, 0)
    || (v29 = (tsched *)(2 * v8), 2 * v8 != NumberOfBytesWritten) )
  {
    v21 = tsched::GetLastHrError(v29, v28);
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_86;
    }
    v25 = 73;
    goto LABEL_85;
  }
  if ( !FlushFileBuffers((HANDLE)v16) )
  {
    v21 = tsched::GetLastHrError(v31, v30);
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_86;
    }
    v25 = 74;
    goto LABEL_85;
  }
  v32 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      75,
      (unsigned int)WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids,
      (_DWORD)a2,
      v8);
    v32 = WPP_GLOBAL_Control;
  }
  if ( v16 )
  {
    if ( v32 != &WPP_GLOBAL_Control && (*((_DWORD *)v32 + 7) & 0x10000) != 0 && *((_BYTE *)v32 + 25) >= 4u )
      WPP_SF_qS(v32[2], 14, (unsigned int)WPP_0318f2e21e573bf245f738540b7f5294_Traceguids, v16, (__int64)a2);
    CloseHandle((HANDLE)v16);
    a2 = 0;
    goto LABEL_69;
  }
  if ( v32 != &WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)v32 + 7) & 0x10000) == 0 || *((_BYTE *)v32 + 25) < 4u )
    {
LABEL_70:
      if ( v32 != &WPP_GLOBAL_Control && (*((_DWORD *)v32 + 7) & 0x10000) != 0 && *((_BYTE *)v32 + 25) >= 4u )
        WPP_SF_S(v32[2], 15, WPP_0318f2e21e573bf245f738540b7f5294_Traceguids, a2);
      goto LABEL_74;
    }
    WPP_SF_S(v32[2], 15, WPP_0318f2e21e573bf245f738540b7f5294_Traceguids, a2);
LABEL_69:
    v32 = WPP_GLOBAL_Control;
    goto LABEL_70;
  }
LABEL_74:
  if ( v11 )
    LocalFree(v11);
  return 0;
}

```

## disassembly

```asm
0x1800231b0  push    rbp
0x1800231b2  push    rbx
0x1800231b3  push    rsi
0x1800231b4  push    r12
0x1800231b6  push    r13
0x1800231b8  push    r14
0x1800231ba  push    r15
0x1800231bc  lea     rbp, [rsp-1D0h]
0x1800231c4  sub     rsp, 2D0h
0x1800231cb  mov     rax, cs:__security_cookie
0x1800231d2  xor     rax, rsp
0x1800231d5  mov     [rbp+200h+var_50], rax
0x1800231dc  mov     esi, [rbp+200h+arg_30]
0x1800231e2  mov     r12, r8
0x1800231e5  mov     r15d, r9d
0x1800231e8  mov     r14, rdx
0x1800231eb  mov     rbx, rcx
0x1800231ee  xor     r13d, r13d
0x1800231f1  mov     ecx, r13d; uFlags
0x1800231f4  xor     eax, eax
0x1800231f6  lock cmpxchg [rbx+5Ch], ecx
0x1800231fb  jnz     short loc_180023210
0x1800231fd  mov     ecx, 64h ; 'd'; dwMilliseconds
0x180023202  call    cs:__imp_Sleep
0x180023209  nop     dword ptr [rax+rax+00h]
0x18002320e  jmp     short loc_1800231F1
0x180023210  mov     rax, [rbx+50h]
0x180023214  cmp     [rax+0B8h], ecx
0x18002321a  jz      loc_180023794
0x180023220  mov     [rsp+300h+var_38], rdi
0x180023228  mov     rbx, r13
0x18002322b  mov     rdi, [rbp+200h+arg_28]
0x180023232  mov     [rsp+300h+var_2B8], rbx
0x180023237  test    rdi, rdi
0x18002323a  jz      loc_1800232E6
0x180023240  lea     rdx, [rsi+18h]; uBytes
0x180023244  call    cs:__imp_LocalAlloc
0x18002324b  nop     dword ptr [rax+rax+00h]
0x180023250  mov     [rsp+300h+var_2B8], rax
0x180023255  mov     rbx, rax
0x180023258  test    rax, rax
0x18002325b  jnz     short loc_1800232D9
0x18002325d  mov     rcx, cs:WPP_GLOBAL_Control
0x180023264  lea     rsi, WPP_GLOBAL_Control
0x18002326b  cmp     rcx, rsi
0x18002326e  jz      short loc_18002329F
0x180023270  test    dword ptr [rcx+1Ch], 40000h
0x180023277  jz      short loc_18002329F
0x180023279  cmp     byte ptr [rcx+19h], 2
0x18002327d  jb      short loc_18002329F
0x18002327f  mov     rcx, [rcx+10h]
0x180023283  lea     r8, WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids
0x18002328a  mov     edx, 45h ; 'E'
0x18002328f  mov     [rsp+300h+dwCreationDisposition], 8007000Eh
0x180023297  mov     r9, r14
0x18002329a  call    WPP_SF_Sd
0x18002329f  lea     rcx, [rsp+300h+var_2B8]
0x1800232a4  call    ??1?$AutoLocalPtr@G@tsched@@QEAA@XZ; tsched::AutoLocalPtr<ushort>::~AutoLocalPtr<ushort>(void)
0x1800232a9  mov     eax, 8007000Eh
0x1800232ae  mov     rdi, [rsp+300h+var_38]
0x1800232b6  mov     rcx, [rbp+200h+var_50]
0x1800232bd  xor     rcx, rsp; StackCookie
0x1800232c0  call    __security_check_cookie
0x1800232c5  add     rsp, 2D0h
0x1800232cc  pop     r15
0x1800232ce  pop     r14
0x1800232d0  pop     r13
0x1800232d2  pop     r12
0x1800232d4  pop     rsi
0x1800232d5  pop     rbx
0x1800232d6  pop     rbp
0x1800232d7  retn
0x1800232d9  mov     [rax+8], rdi
0x1800232dd  lea     eax, [rsi+18h]
0x1800232e0  mov     [rbx], eax
0x1800232e2  mov     [rbx+10h], r13d
0x1800232e6  mov     [rsp+300h+hTemplateFile], r13; hTemplateFile
0x1800232eb  mov     r9, rbx; lpSecurityAttributes
0x1800232ee  mov     [rsp+300h+dwFlagsAndAttributes], 8000080h; dwFlagsAndAttributes
0x1800232f6  mov     edx, 40000000h; dwDesiredAccess
0x1800232fb  mov     r8d, 1; dwShareMode
0x180023301  mov     [rsp+300h+dwCreationDisposition], 4; dwCreationDisposition
0x180023309  mov     rcx, r14; lpFileName
0x18002330c  call    cs:__imp_CreateFileW
0x180023313  nop     dword ptr [rax+rax+00h]
0x180023318  mov     rsi, rax
0x18002331b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002331f  jnz     short loc_180023329
0x180023321  mov     rdi, rax
0x180023324  jmp     loc_1800233B2
0x180023329  xorps   xmm0, xmm0
0x18002332c  lea     rdx, [rbp+200h+szFilePath]; lpszFilePath
0x180023330  xor     eax, eax
0x180023332  xor     r9d, r9d; dwFlags
0x180023335  mov     r8d, 105h; cchFilePath
0x18002333b  mov     [rbp+200h+FileInformation.nFileIndexLow], eax
0x18002333e  mov     rcx, rsi; hFile
0x180023341  movups  xmmword ptr [rsp+300h+FileInformation.dwFileAttributes], xmm0
0x180023346  movups  xmmword ptr [rsp+300h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x18002334b  movups  xmmword ptr [rbp+200h+FileInformation.nFileSizeHigh], xmm0
0x18002334f  call    cs:__imp_GetFinalPathNameByHandleW
0x180023356  nop     dword ptr [rax+rax+00h]
0x18002335b  dec     eax
0x18002335d  cmp     eax, 103h
0x180023362  ja      loc_1800234BF
0x180023368  mov     r8d, 105h; MaxCount
0x18002336e  lea     rcx, [rbp+200h+szFilePath]; String1
0x180023372  mov     rdx, r14; String2
0x180023375  call    cs:__imp__wcsnicmp
0x18002337c  nop     dword ptr [rax+rax+00h]
0x180023381  test    eax, eax
0x180023383  jnz     loc_1800234CC
0x180023389  lea     rdx, [rsp+300h+FileInformation]; lpFileInformation
0x18002338e  mov     rcx, rsi; hFile
0x180023391  call    cs:__imp_GetFileInformationByHandle
0x180023398  nop     dword ptr [rax+rax+00h]
0x18002339d  test    eax, eax
0x18002339f  jz      loc_1800234CC
0x1800233a5  cmp     [rbp+200h+FileInformation.nNumberOfLinks], 1
0x1800233a9  ja      loc_1800234CC
0x1800233af  mov     rdi, rsi
0x1800233b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800233b9  lea     rsi, WPP_GLOBAL_Control
0x1800233c0  cmp     rcx, rsi
0x1800233c3  jz      short loc_18002341F
0x1800233c5  test    dword ptr [rcx+1Ch], 10000h
0x1800233cc  jz      short loc_1800233F3
0x1800233ce  cmp     byte ptr [rcx+19h], 4
0x1800233d2  jb      short loc_1800233F3
0x1800233d4  mov     rcx, [rcx+10h]
0x1800233d8  lea     r8, WPP_0318f2e21e573bf245f738540b7f5294_Traceguids
0x1800233df  mov     edx, 10h
0x1800233e4  mov     r9, rdi
0x1800233e7  call    WPP_SF_q
0x1800233ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1800233f3  cmp     rcx, rsi
0x1800233f6  jz      short loc_18002341F
0x1800233f8  test    dword ptr [rcx+1Ch], 10000h
0x1800233ff  jz      short loc_18002341F
0x180023401  cmp     byte ptr [rcx+19h], 4
0x180023405  jb      short loc_18002341F
0x180023407  mov     rcx, [rcx+10h]
0x18002340b  lea     r8, WPP_0318f2e21e573bf245f738540b7f5294_Traceguids
0x180023412  mov     edx, 0Fh
0x180023417  xor     r9d, r9d
0x18002341a  call    WPP_SF_S
0x18002341f  mov     [rsp+300h+var_2B0], rdi
0x180023424  mov     [rsp+300h+var_2A8], r14
0x180023429  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18002342d  jnz     loc_1800234F8
0x180023433  call    ?GetLastHrError@tsched@@YAJJ@Z; tsched::GetLastHrError(long)
0x180023438  mov     ebx, eax
0x18002343a  mov     rcx, cs:WPP_GLOBAL_Control
0x180023441  cmp     rcx, rsi
0x180023444  jz      short loc_180023471
0x180023446  test    dword ptr [rcx+1Ch], 40000h
0x18002344d  jz      short loc_180023471
0x18002344f  cmp     byte ptr [rcx+19h], 2
0x180023453  jb      short loc_180023471
0x180023455  mov     rcx, [rcx+10h]
0x180023459  lea     r8, WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids
0x180023460  mov     edx, 46h ; 'F'
0x180023465  mov     [rsp+300h+dwCreationDisposition], eax
0x180023469  mov     r9, r14
0x18002346c  call    WPP_SF_Sd
0x180023471  cmp     ebx, 80070005h
0x180023477  jnz     loc_180023779
0x18002347d  xorps   xmm0, xmm0
0x180023480  lea     r8, [rsp+300h+FileInformation]; lpFileInformation
0x180023485  xor     eax, eax
0x180023487  xor     edx, edx; fInfoLevelId
0x180023489  mov     rcx, r14; lpFileName
0x18002348c  mov     [rbp+200h+FileInformation.nFileSizeHigh], eax
0x18002348f  movups  xmmword ptr [rsp+300h+FileInformation.dwFileAttributes], xmm0
0x180023494  movups  xmmword ptr [rsp+300h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x180023499  call    cs:__imp_GetFileAttributesExW
0x1800234a0  nop     dword ptr [rax+rax+00h]
0x1800234a5  test    eax, eax
0x1800234a7  jz      loc_180023779
0x1800234ad  test    byte ptr [rsp+300h+FileInformation.dwFileAttributes], 10h
0x1800234b2  mov     eax, 0B7h
0x1800234b7  cmovnz  ebx, eax
0x1800234ba  jmp     loc_180023779
0x1800234bf  call    ?GetLastHrError@tsched@@YAJJ@Z; tsched::GetLastHrError(long)
0x1800234c4  test    eax, eax
0x1800234c6  jns     loc_1800233AF
0x1800234cc  mov     ecx, 5; dwErrCode
0x1800234d1  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x1800234d8  call    cs:__imp_SetLastError
0x1800234df  nop     dword ptr [rax+rax+00h]
0x1800234e4  mov     rcx, rsi; hObject
0x1800234e7  call    cs:__imp_CloseHandle
0x1800234ee  nop     dword ptr [rax+rax+00h]
0x1800234f3  jmp     loc_1800233B2
0x1800234f8  mov     rcx, rdi; hFile
0x1800234fb  call    cs:__imp_SetEndOfFile
0x180023502  nop     dword ptr [rax+rax+00h]
0x180023507  test    eax, eax
0x180023509  jnz     short loc_180023543
0x18002350b  call    ?GetLastHrError@tsched@@YAJJ@Z; tsched::GetLastHrError(long)
0x180023510  mov     ebx, eax
0x180023512  mov     rcx, cs:WPP_GLOBAL_Control
0x180023519  cmp     rcx, rsi
0x18002351c  jz      loc_180023779
0x180023522  test    dword ptr [rcx+1Ch], 40000h
0x180023529  jz      loc_180023779
0x18002352f  cmp     byte ptr [rcx+19h], 2
0x180023533  jb      loc_180023779
0x180023539  mov     edx, 47h ; 'G'
0x18002353e  jmp     loc_180023762
0x180023543  mov     eax, 0FEFFh
0x180023548  mov     [rsp+300h+NumberOfBytesWritten], r13d
0x18002354d  lea     r9, [rsp+300h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180023552  mov     [rsp+300h+Buffer], ax
0x180023557  mov     r8d, 2; nNumberOfBytesToWrite
0x18002355d  mov     qword ptr [rsp+300h+dwCreationDisposition], r13; lpOverlapped
0x180023562  lea     rdx, [rsp+300h+Buffer]; lpBuffer
0x180023567  mov     rcx, rdi; hFile
0x18002356a  call    cs:__imp_WriteFile
0x180023571  nop     dword ptr [rax+rax+00h]
0x180023576  test    eax, eax
0x180023578  jz      loc_18002373B
0x18002357e  cmp     [rsp+300h+NumberOfBytesWritten], 2
0x180023583  jnz     loc_18002373B
0x180023589  lea     r8d, [r15+r15]; nNumberOfBytesToWrite
0x18002358d  mov     qword ptr [rsp+300h+dwCreationDisposition], r13; lpOverlapped
0x180023592  lea     r9, [rsp+300h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180023597  mov     rdx, r12; lpBuffer
0x18002359a  mov     rcx, rdi; hFile
0x18002359d  call    cs:__imp_WriteFile
0x1800235a4  nop     dword ptr [rax+rax+00h]
0x1800235a9  test    eax, eax
0x1800235ab  jz      loc_180023712
0x1800235b1  mov     eax, [rsp+300h+NumberOfBytesWritten]
0x1800235b5  mov     rcx, r15
0x1800235b8  add     rcx, rcx
0x1800235bb  cmp     rcx, rax
0x1800235be  jnz     loc_180023712
0x1800235c4  mov     rcx, rdi; hFile
0x1800235c7  call    cs:__imp_FlushFileBuffers
0x1800235ce  nop     dword ptr [rax+rax+00h]
0x1800235d3  test    eax, eax
0x1800235d5  jnz     short loc_18002360F
0x1800235d7  call    ?GetLastHrError@tsched@@YAJJ@Z; tsched::GetLastHrError(long)
0x1800235dc  mov     ebx, eax
0x1800235de  mov     rcx, cs:WPP_GLOBAL_Control
0x1800235e5  cmp     rcx, rsi
0x1800235e8  jz      loc_180023779
0x1800235ee  test    dword ptr [rcx+1Ch], 40000h
0x1800235f5  jz      loc_180023779
0x1800235fb  cmp     byte ptr [rcx+19h], 2
0x1800235ff  jb      loc_180023779
0x180023605  mov     edx, 4Ah ; 'J'
0x18002360a  jmp     loc_180023762
0x18002360f  mov     rcx, cs:WPP_GLOBAL_Control
0x180023616  cmp     rcx, rsi
0x180023619  jz      short loc_18002364E
0x18002361b  test    dword ptr [rcx+1Ch], 40000h
0x180023622  jz      short loc_18002364E
0x180023624  cmp     byte ptr [rcx+19h], 4
0x180023628  jb      short loc_18002364E
0x18002362a  mov     rcx, [rcx+10h]
0x18002362e  lea     r8, WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids
0x180023635  mov     edx, 4Bh ; 'K'
0x18002363a  mov     [rsp+300h+dwCreationDisposition], r15d
0x18002363f  mov     r9, r14
0x180023642  call    WPP_SF_Sd
0x180023647  mov     rcx, cs:WPP_GLOBAL_Control
0x18002364e  test    rdi, rdi
0x180023651  jz      short loc_180023698
0x180023653  cmp     rcx, rsi
0x180023656  jz      short loc_180023684
0x180023658  test    dword ptr [rcx+1Ch], 10000h
0x18002365f  jz      short loc_180023684
0x180023661  cmp     byte ptr [rcx+19h], 4
0x180023665  jb      short loc_180023684
0x180023667  mov     rcx, [rcx+10h]
0x18002366b  lea     r8, WPP_0318f2e21e573bf245f738540b7f5294_Traceguids
0x180023672  mov     edx, 0Eh
0x180023677  mov     qword ptr [rsp+300h+dwCreationDisposition], r14
0x18002367c  mov     r9, rdi
0x18002367f  call    WPP_SF_qS
0x180023684  mov     rcx, rdi; hObject
0x180023687  call    cs:__imp_CloseHandle
0x18002368e  nop     dword ptr [rax+rax+00h]
0x180023693  mov     r14, r13
0x180023696  jmp     short loc_1800236C4
0x180023698  cmp     rcx, rsi
0x18002369b  jz      short loc_1800236F7
0x18002369d  test    dword ptr [rcx+1Ch], 10000h
0x1800236a4  jz      short loc_1800236CB
0x1800236a6  cmp     byte ptr [rcx+19h], 4
0x1800236aa  jb      short loc_1800236CB
0x1800236ac  mov     rcx, [rcx+10h]
0x1800236b0  lea     r8, WPP_0318f2e21e573bf245f738540b7f5294_Traceguids
0x1800236b7  mov     edx, 0Fh
0x1800236bc  mov     r9, r14
0x1800236bf  call    WPP_SF_S
0x1800236c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800236cb  cmp     rcx, rsi
  ... truncated ...
```
