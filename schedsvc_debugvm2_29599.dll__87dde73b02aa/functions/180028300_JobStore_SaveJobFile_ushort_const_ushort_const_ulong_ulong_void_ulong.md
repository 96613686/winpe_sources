# JobStore::SaveJobFile(ushort const *,ushort const *,ulong,ulong,void *,ulong)

- ea: `0x180028300`
- end: `0x18002888d`
- name: `?SaveJobFile@JobStore@@AEBAJPEBG0KKPEAXK@Z`
- size: `1421`
- prototype: `int(JobStore *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned int, void *, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x180027c30`

## callees

- `0x180025040`
- `0x1800276c0`
- `0x180028300`
- `0x180052584`
- `0x180056794`
- `0x18005b250`
- `0x18006420c`
- `0x1800661a8`
- `0x18007e6d0`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x1800284a9`
- `msvcrt!_wcsnicmp` at `0x1800284a9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800285fa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800285fa`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002867a`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800286a7`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002867a`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800286a7`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x180028611`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x180028611`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002844f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002844f`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x1800285c1`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x1800285c1`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x1800286cb`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x1800286cb`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180028489`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180028489`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x1800284bf`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x1800284bf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028603`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028785`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028603`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028785`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180028352`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180028352`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800287f7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800287f7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002838e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002838e`

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
0x180028300  push    rbp
0x180028302  push    rbx
0x180028303  push    rsi
0x180028304  push    r12
0x180028306  push    r13
0x180028308  push    r14
0x18002830a  push    r15
0x18002830c  lea     rbp, [rsp-1D0h]
0x180028314  sub     rsp, 2D0h
0x18002831b  mov     rax, cs:__security_cookie
0x180028322  xor     rax, rsp
0x180028325  mov     [rbp+200h+var_50], rax
0x18002832c  mov     esi, [rbp+200h+arg_30]
0x180028332  mov     r12, r8
0x180028335  mov     r15d, r9d
0x180028338  mov     r14, rdx
0x18002833b  mov     rbx, rcx
0x18002833e  xor     r13d, r13d
0x180028341  mov     ecx, r13d; uFlags
0x180028344  xor     eax, eax
0x180028346  lock cmpxchg [rbx+5Ch], ecx
0x18002834b  jnz     short loc_18002835A
0x18002834d  mov     ecx, 64h ; 'd'; dwMilliseconds
0x180028352  call    cs:__imp_Sleep
0x180028358  jmp     short loc_180028341
0x18002835a  mov     rax, [rbx+50h]
0x18002835e  cmp     [rax+0B8h], ecx
0x180028364  jz      loc_180028886
0x18002836a  mov     [rsp+300h+var_38], rdi
0x180028372  mov     rbx, r13
0x180028375  mov     rdi, [rbp+200h+arg_28]
0x18002837c  mov     [rsp+300h+var_2B8], rbx
0x180028381  test    rdi, rdi
0x180028384  jz      loc_180028429
0x18002838a  lea     rdx, [rsi+18h]; uBytes
0x18002838e  call    cs:__imp_LocalAlloc
0x180028394  mov     [rsp+300h+var_2B8], rax
0x180028399  mov     rbx, rax
0x18002839c  test    rax, rax
0x18002839f  jnz     short loc_18002841C
0x1800283a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800283a8  lea     rsi, WPP_GLOBAL_Control
0x1800283af  cmp     rcx, rsi
0x1800283b2  jz      short loc_1800283E3
0x1800283b4  test    dword ptr [rcx+1Ch], 40000h
0x1800283bb  jz      short loc_1800283E3
0x1800283bd  cmp     byte ptr [rcx+19h], 2
0x1800283c1  jb      short loc_1800283E3
0x1800283c3  mov     rcx, [rcx+10h]
0x1800283c7  lea     r8, WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids
0x1800283ce  mov     edx, 45h ; 'E'
0x1800283d3  mov     [rsp+300h+dwCreationDisposition], 8007000Eh
0x1800283db  mov     r9, r14
0x1800283de  call    WPP_SF_Sd
0x1800283e3  lea     rcx, [rsp+300h+var_2B8]
0x1800283e8  call    ??1?$AutoLocalPtr@G@tsched@@QEAA@XZ; tsched::AutoLocalPtr<ushort>::~AutoLocalPtr<ushort>(void)
0x1800283ed  mov     eax, 8007000Eh
0x1800283f2  mov     rdi, [rsp+300h+var_38]
0x1800283fa  mov     rcx, [rbp+200h+var_50]
0x180028401  xor     rcx, rsp; StackCookie
0x180028404  call    __security_check_cookie
0x180028409  add     rsp, 2D0h
0x180028410  pop     r15
0x180028412  pop     r14
0x180028414  pop     r13
0x180028416  pop     r12
0x180028418  pop     rsi
0x180028419  pop     rbx
0x18002841a  pop     rbp
0x18002841b  retn
0x18002841c  mov     [rax+8], rdi
0x180028420  lea     eax, [rsi+18h]
0x180028423  mov     [rbx], eax
0x180028425  mov     [rbx+10h], r13d
0x180028429  mov     [rsp+300h+hTemplateFile], r13; hTemplateFile
0x18002842e  mov     r9, rbx; lpSecurityAttributes
0x180028431  mov     [rsp+300h+dwFlagsAndAttributes], 8000080h; dwFlagsAndAttributes
0x180028439  mov     edx, 40000000h; dwDesiredAccess
0x18002843e  mov     r8d, 1; dwShareMode
0x180028444  mov     [rsp+300h+dwCreationDisposition], 4; dwCreationDisposition
0x18002844c  mov     rcx, r14; lpFileName
0x18002844f  call    cs:__imp_CreateFileW
0x180028455  mov     rsi, rax
0x180028458  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002845c  jnz     short loc_180028463
0x18002845e  mov     rdi, rax
0x180028461  jmp     short loc_1800284DA
0x180028463  xorps   xmm0, xmm0
0x180028466  lea     rdx, [rbp+200h+szFilePath]; lpszFilePath
0x18002846a  xor     eax, eax
0x18002846c  xor     r9d, r9d; dwFlags
0x18002846f  mov     r8d, 105h; cchFilePath
0x180028475  mov     [rbp+200h+FileInformation.nFileIndexLow], eax
0x180028478  mov     rcx, rsi; hFile
0x18002847b  movups  xmmword ptr [rsp+300h+FileInformation.dwFileAttributes], xmm0
0x180028480  movups  xmmword ptr [rsp+300h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x180028485  movups  xmmword ptr [rbp+200h+FileInformation.nFileSizeHigh], xmm0
0x180028489  call    cs:__imp_GetFinalPathNameByHandleW
0x18002848f  dec     eax
0x180028491  cmp     eax, 103h
0x180028496  ja      loc_1800285E1
0x18002849c  mov     r8d, 105h; MaxCount
0x1800284a2  lea     rcx, [rbp+200h+szFilePath]; String1
0x1800284a6  mov     rdx, r14; String2
0x1800284a9  call    cs:__imp__wcsnicmp
0x1800284af  test    eax, eax
0x1800284b1  jnz     loc_1800285EE
0x1800284b7  lea     rdx, [rsp+300h+FileInformation]; lpFileInformation
0x1800284bc  mov     rcx, rsi; hFile
0x1800284bf  call    cs:__imp_GetFileInformationByHandle
0x1800284c5  test    eax, eax
0x1800284c7  jz      loc_1800285EE
0x1800284cd  cmp     [rbp+200h+FileInformation.nNumberOfLinks], 1
0x1800284d1  ja      loc_1800285EE
0x1800284d7  mov     rdi, rsi
0x1800284da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800284e1  lea     rsi, WPP_GLOBAL_Control
0x1800284e8  cmp     rcx, rsi
0x1800284eb  jz      short loc_180028547
0x1800284ed  test    dword ptr [rcx+1Ch], 10000h
0x1800284f4  jz      short loc_18002851B
0x1800284f6  cmp     byte ptr [rcx+19h], 4
0x1800284fa  jb      short loc_18002851B
0x1800284fc  mov     rcx, [rcx+10h]
0x180028500  lea     r8, WPP_0318f2e21e573bf245f738540b7f5294_Traceguids
0x180028507  mov     edx, 10h
0x18002850c  mov     r9, rdi
0x18002850f  call    WPP_SF_q
0x180028514  mov     rcx, cs:WPP_GLOBAL_Control
0x18002851b  cmp     rcx, rsi
0x18002851e  jz      short loc_180028547
0x180028520  test    dword ptr [rcx+1Ch], 10000h
0x180028527  jz      short loc_180028547
0x180028529  cmp     byte ptr [rcx+19h], 4
0x18002852d  jb      short loc_180028547
0x18002852f  mov     rcx, [rcx+10h]
0x180028533  lea     r8, WPP_0318f2e21e573bf245f738540b7f5294_Traceguids
0x18002853a  mov     edx, 0Fh
0x18002853f  xor     r9d, r9d
0x180028542  call    WPP_SF_S
0x180028547  mov     [rsp+300h+var_2B0], rdi
0x18002854c  mov     [rsp+300h+var_2A8], r14
0x180028551  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180028555  jnz     loc_18002860E
0x18002855b  call    ?GetLastHrError@tsched@@YAJJ@Z; tsched::GetLastHrError(long)
0x180028560  mov     ebx, eax
0x180028562  mov     rcx, cs:WPP_GLOBAL_Control
0x180028569  cmp     rcx, rsi
0x18002856c  jz      short loc_180028599
0x18002856e  test    dword ptr [rcx+1Ch], 40000h
0x180028575  jz      short loc_180028599
0x180028577  cmp     byte ptr [rcx+19h], 2
0x18002857b  jb      short loc_180028599
0x18002857d  mov     rcx, [rcx+10h]
0x180028581  lea     r8, WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids
0x180028588  mov     edx, 46h ; 'F'
0x18002858d  mov     [rsp+300h+dwCreationDisposition], eax
0x180028591  mov     r9, r14
0x180028594  call    WPP_SF_Sd
0x180028599  cmp     ebx, 80070005h
0x18002859f  jnz     loc_18002886B
0x1800285a5  xorps   xmm0, xmm0
0x1800285a8  lea     r8, [rsp+300h+FileInformation]; lpFileInformation
0x1800285ad  xor     eax, eax
0x1800285af  xor     edx, edx; fInfoLevelId
0x1800285b1  mov     rcx, r14; lpFileName
0x1800285b4  mov     [rbp+200h+FileInformation.nFileSizeHigh], eax
0x1800285b7  movups  xmmword ptr [rsp+300h+FileInformation.dwFileAttributes], xmm0
0x1800285bc  movups  xmmword ptr [rsp+300h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x1800285c1  call    cs:__imp_GetFileAttributesExW
0x1800285c7  test    eax, eax
0x1800285c9  jz      loc_18002886B
0x1800285cf  test    byte ptr [rsp+300h+FileInformation.dwFileAttributes], 10h
0x1800285d4  mov     eax, 0B7h
0x1800285d9  cmovnz  ebx, eax
0x1800285dc  jmp     loc_18002886B
0x1800285e1  call    ?GetLastHrError@tsched@@YAJJ@Z; tsched::GetLastHrError(long)
0x1800285e6  test    eax, eax
0x1800285e8  jns     loc_1800284D7
0x1800285ee  mov     ecx, 5; dwErrCode
0x1800285f3  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x1800285fa  call    cs:__imp_SetLastError
0x180028600  mov     rcx, rsi; hObject
0x180028603  call    cs:__imp_CloseHandle
0x180028609  jmp     loc_1800284DA
0x18002860e  mov     rcx, rdi; hFile
0x180028611  call    cs:__imp_SetEndOfFile
0x180028617  test    eax, eax
0x180028619  jnz     short loc_180028653
0x18002861b  call    ?GetLastHrError@tsched@@YAJJ@Z; tsched::GetLastHrError(long)
0x180028620  mov     ebx, eax
0x180028622  mov     rcx, cs:WPP_GLOBAL_Control
0x180028629  cmp     rcx, rsi
0x18002862c  jz      loc_18002886B
0x180028632  test    dword ptr [rcx+1Ch], 40000h
0x180028639  jz      loc_18002886B
0x18002863f  cmp     byte ptr [rcx+19h], 2
0x180028643  jb      loc_18002886B
0x180028649  mov     edx, 47h ; 'G'
0x18002864e  jmp     loc_180028854
0x180028653  mov     eax, 0FEFFh
0x180028658  mov     [rsp+300h+NumberOfBytesWritten], r13d
0x18002865d  lea     r9, [rsp+300h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180028662  mov     [rsp+300h+Buffer], ax
0x180028667  mov     r8d, 2; nNumberOfBytesToWrite
0x18002866d  mov     qword ptr [rsp+300h+dwCreationDisposition], r13; lpOverlapped
0x180028672  lea     rdx, [rsp+300h+Buffer]; lpBuffer
0x180028677  mov     rcx, rdi; hFile
0x18002867a  call    cs:__imp_WriteFile
0x180028680  test    eax, eax
0x180028682  jz      loc_18002882D
0x180028688  cmp     [rsp+300h+NumberOfBytesWritten], 2
0x18002868d  jnz     loc_18002882D
0x180028693  lea     r8d, [r15+r15]; nNumberOfBytesToWrite
0x180028697  mov     qword ptr [rsp+300h+dwCreationDisposition], r13; lpOverlapped
0x18002869c  lea     r9, [rsp+300h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800286a1  mov     rdx, r12; lpBuffer
0x1800286a4  mov     rcx, rdi; hFile
0x1800286a7  call    cs:__imp_WriteFile
0x1800286ad  test    eax, eax
0x1800286af  jz      loc_180028804
0x1800286b5  mov     eax, [rsp+300h+NumberOfBytesWritten]
0x1800286b9  mov     rcx, r15
0x1800286bc  add     rcx, rcx
0x1800286bf  cmp     rcx, rax
0x1800286c2  jnz     loc_180028804
0x1800286c8  mov     rcx, rdi; hFile
0x1800286cb  call    cs:__imp_FlushFileBuffers
0x1800286d1  test    eax, eax
0x1800286d3  jnz     short loc_18002870D
0x1800286d5  call    ?GetLastHrError@tsched@@YAJJ@Z; tsched::GetLastHrError(long)
0x1800286da  mov     ebx, eax
0x1800286dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800286e3  cmp     rcx, rsi
0x1800286e6  jz      loc_18002886B
0x1800286ec  test    dword ptr [rcx+1Ch], 40000h
0x1800286f3  jz      loc_18002886B
0x1800286f9  cmp     byte ptr [rcx+19h], 2
0x1800286fd  jb      loc_18002886B
0x180028703  mov     edx, 4Ah ; 'J'
0x180028708  jmp     loc_180028854
0x18002870d  mov     rcx, cs:WPP_GLOBAL_Control
0x180028714  cmp     rcx, rsi
0x180028717  jz      short loc_18002874C
0x180028719  test    dword ptr [rcx+1Ch], 40000h
0x180028720  jz      short loc_18002874C
0x180028722  cmp     byte ptr [rcx+19h], 4
0x180028726  jb      short loc_18002874C
0x180028728  mov     rcx, [rcx+10h]
0x18002872c  lea     r8, WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids
0x180028733  mov     edx, 4Bh ; 'K'
0x180028738  mov     [rsp+300h+dwCreationDisposition], r15d
0x18002873d  mov     r9, r14
0x180028740  call    WPP_SF_Sd
0x180028745  mov     rcx, cs:WPP_GLOBAL_Control
0x18002874c  test    rdi, rdi
0x18002874f  jz      short loc_180028790
0x180028751  cmp     rcx, rsi
0x180028754  jz      short loc_180028782
0x180028756  test    dword ptr [rcx+1Ch], 10000h
0x18002875d  jz      short loc_180028782
0x18002875f  cmp     byte ptr [rcx+19h], 4
0x180028763  jb      short loc_180028782
0x180028765  mov     rcx, [rcx+10h]
0x180028769  lea     r8, WPP_0318f2e21e573bf245f738540b7f5294_Traceguids
0x180028770  mov     edx, 0Eh
0x180028775  mov     qword ptr [rsp+300h+dwCreationDisposition], r14
0x18002877a  mov     r9, rdi
0x18002877d  call    WPP_SF_qS
0x180028782  mov     rcx, rdi; hObject
0x180028785  call    cs:__imp_CloseHandle
0x18002878b  mov     r14, r13
0x18002878e  jmp     short loc_1800287BC
0x180028790  cmp     rcx, rsi
0x180028793  jz      short loc_1800287EF
0x180028795  test    dword ptr [rcx+1Ch], 10000h
0x18002879c  jz      short loc_1800287C3
0x18002879e  cmp     byte ptr [rcx+19h], 4
0x1800287a2  jb      short loc_1800287C3
0x1800287a4  mov     rcx, [rcx+10h]
0x1800287a8  lea     r8, WPP_0318f2e21e573bf245f738540b7f5294_Traceguids
0x1800287af  mov     edx, 0Fh
0x1800287b4  mov     r9, r14
0x1800287b7  call    WPP_SF_S
0x1800287bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800287c3  cmp     rcx, rsi
0x1800287c6  jz      short loc_1800287EF
0x1800287c8  test    dword ptr [rcx+1Ch], 10000h
0x1800287cf  jz      short loc_1800287EF
0x1800287d1  cmp     byte ptr [rcx+19h], 4
0x1800287d5  jb      short loc_1800287EF
0x1800287d7  mov     rcx, [rcx+10h]
0x1800287db  lea     r8, WPP_0318f2e21e573bf245f738540b7f5294_Traceguids
0x1800287e2  mov     edx, 0Fh
0x1800287e7  mov     r9, r14
0x1800287ea  call    WPP_SF_S
0x1800287ef  test    rbx, rbx
0x1800287f2  jz      short loc_1800287FD
0x1800287f4  mov     rcx, rbx; hMem
0x1800287f7  call    cs:__imp_LocalFree
  ... truncated ...
```
