# __Trace::Trace(char,char const *,char * &)

- ea: `0x18001a84c`
- end: `0x18001ac34`
- name: `?Trace@__Trace@@QEAAHDPEBDAEAPEAD@Z`
- size: `1000`
- prototype: `int(__Trace *__hidden this, char, const char *, char **)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x18000ede0`
- `0x18001a7f0`

## callees

- `0x180013564`
- `0x180014120`
- `0x18001a84c`
- `0x18001ac3c`
- `0x18001ac90`
- `0x18001b090`
- `0x180027f1c`
- `0x180028bf0`
- `0x18002ed08`
- `0x180044310`

## import_xrefs

- `msvcrt!asctime` at `0x18001a901`
- `msvcrt!asctime` at `0x18001a901`
- `msvcrt!localtime` at `0x18001a8e1`
- `msvcrt!localtime` at `0x18001a8e1`
- `msvcrt!time` at `0x18001a8d3`
- `msvcrt!time` at `0x18001a8d3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001a8b8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001a8b8`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001aa3e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001aa3e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001a96a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001a96a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001aa79`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001aa79`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18001aa34`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18001aa34`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall __Trace::Trace(__Trace *this, unsigned __int8 a2, const char *a3, char **a4)
{
  __int64 logfile; // rax
  void *v6; // r12
  __int64 v7; // r15
  HANDLE v8; // rbx
  struct tm *v9; // rax
  __int64 v10; // rdi
  char *v11; // rax
  __int64 v12; // rcx
  char *v13; // rdx
  char v14; // r8
  unsigned int v15; // edi
  char *v16; // rax
  __int64 v17; // rax
  DWORD TickCount; // eax
  char *v19; // rsi
  signed int v20; // eax
  unsigned int v21; // edi
  int v22; // r14d
  size_t *v23; // r8
  __int64 v24; // rcx
  HRESULT v25; // edi
  DWORD v26; // r8d
  char *v27; // rax
  char i; // cl
  unsigned __int64 v30; // rax
  signed int v31; // eax
  unsigned int v32; // edi
  DWORD NumberOfBytesWritten; // [rsp+30h] [rbp-59h] BYREF
  __int64 v34; // [rsp+38h] [rbp-51h] BYREF
  time_t Time; // [rsp+40h] [rbp-49h] BYREF
  va_list *v36; // [rsp+48h] [rbp-41h]
  HANDLE v37; // [rsp+50h] [rbp-39h]
  char v38[64]; // [rsp+60h] [rbp-29h] BYREF

  v36 = a4;
  logfile = __Trace::get_logfile(
              this,
              (const unsigned __int16 *)(&__Trace::m_szLogFileNames)[(char)(a2 < 0x14u ? a2 : 0)]);
  v6 = (void *)logfile;
  v7 = -1;
  if ( logfile == -1 )
    return 0;
  v34 = logfile;
  if ( WaitForSingleObject(hObject, 0xFFFFFFFF) == -1 )
  {
    CCloseMe::~CCloseMe((CCloseMe *)&v34);
    return 0;
  }
  v8 = hObject;
  v37 = hObject;
  Time = time(0);
  v9 = localtime(&Time);
  if ( v9 )
  {
    v10 = 2147483646;
    v11 = asctime(v9);
    v12 = 64;
    v13 = v38;
    do
    {
      if ( !v10 )
        break;
      v14 = *v11;
      if ( !*v11 )
        break;
      ++v11;
      *v13++ = v14;
      --v10;
      --v12;
    }
    while ( v12 );
    v15 = v12 == 0 ? 0x8007007A : 0;
    v16 = v13 - 1;
    if ( v12 )
      v16 = v13;
    *v16 = 0;
    if ( !v12 )
    {
      CMemoryLog::Write((CMemoryLog *)&unk_18006A9C0, v15);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_a66c463c75c73635afca8e74831cc57c_Traceguids, v15);
      }
    }
    v17 = -1;
    do
      ++v17;
    while ( v38[v17] );
    if ( (int)v17 < 64 )
    {
      v30 = (int)v17 - 1LL;
      if ( v30 >= 0x40 )
        _report_rangecheckfailure(v38);
      v38[v30] = 0;
    }
  }
  else
  {
    v31 = StringCchCopyA(v38, 0x40u, "??");
    v32 = v31;
    if ( v31 < 0 )
    {
      CMemoryLog::Write((CMemoryLog *)&unk_18006A9C0, v31);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_a66c463c75c73635afca8e74831cc57c_Traceguids, v32);
      }
    }
  }
  TickCount = GetTickCount();
  v19 = byte_180068D96;
  v20 = StringCchPrintfA(byte_180068D96, 0x800u, "(%s.%d) : ", v38, TickCount);
  v21 = v20;
  if ( v20 < 0 )
  {
    CMemoryLog::Write((CMemoryLog *)&unk_18006A9C0, v20);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_a66c463c75c73635afca8e74831cc57c_Traceguids, v21);
    }
  }
  do
    ++v7;
  while ( byte_180068D96[v7] );
  v22 = 2048 - v7;
  v23 = (size_t *)&byte_180068D96[(int)v7];
  if ( 2048 == (_DWORD)v7 )
  {
    v24 = 0;
LABEL_47:
    v25 = -2147024809;
    if ( v24 )
      *(_BYTE *)v23 = 0;
    goto LABEL_49;
  }
  v24 = v22;
  if ( (unsigned __int64)v22 > 0x7FFFFFFF )
    goto LABEL_47;
  v25 = StringVPrintfWorkerA(&byte_180068D96[(int)v7], v22, v23, a3, *v36);
  if ( v25 < 0 )
  {
LABEL_49:
    CMemoryLog::Write((CMemoryLog *)&unk_18006A9C0, v25);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        26,
        &WPP_a66c463c75c73635afca8e74831cc57c_Traceguids,
        (unsigned int)v25);
    }
  }
  v26 = 0;
  v27 = (char *)&unk_180069596;
  for ( i = byte_180068D96[0]; i; i = *v19 )
  {
    if ( i == 10 )
    {
      *v27++ = 13;
      ++v26;
      *v27 = 10;
    }
    else
    {
      *v27 = i;
    }
    ++v19;
    ++v27;
    ++v26;
  }
  *v27 = 0;
  NumberOfBytesWritten = 0;
  WriteFile(v6, &unk_180069596, v26, &NumberOfBytesWritten, 0);
  ReleaseMutex(v8);
  if ( v6 )
    CloseHandle(v6);
  return 1;
}

```

## disassembly

```asm
0x18001a84c  mov     [rsp-8+arg_0], rbx
0x18001a851  push    rbp
0x18001a852  push    rsi
0x18001a853  push    rdi
0x18001a854  push    r12
0x18001a856  push    r13
0x18001a858  push    r14
0x18001a85a  push    r15
0x18001a85c  lea     rbp, [rsp-27h]
0x18001a861  sub     rsp, 0B0h
0x18001a868  mov     rax, cs:__security_cookie
0x18001a86f  xor     rax, rsp
0x18001a872  mov     [rbp+57h+var_40], rax
0x18001a876  mov     [rbp+57h+var_98], r9
0x18001a87a  mov     r13, r8
0x18001a87d  cmp     dl, 14h
0x18001a880  sbb     al, al
0x18001a882  and     al, dl
0x18001a884  movsx   rdx, al
0x18001a888  lea     rax, ?m_szLogFileNames@__Trace@@2PAPEBGA; ushort const * near * __Trace::m_szLogFileNames
0x18001a88f  mov     rdx, [rax+rdx*8]; unsigned __int16 *
0x18001a893  call    ?get_logfile@__Trace@@QEAAPEAXPEBG@Z; __Trace::get_logfile(ushort const *)
0x18001a898  mov     r12, rax
0x18001a89b  or      r15, 0FFFFFFFFFFFFFFFFh
0x18001a89f  cmp     rax, r15
0x18001a8a2  jz      loc_18001AAB0
0x18001a8a8  mov     [rbp+57h+var_A8], rax
0x18001a8ac  or      ebx, 0FFFFFFFFh
0x18001a8af  mov     edx, ebx; dwMilliseconds
0x18001a8b1  mov     rcx, cs:hObject; hHandle
0x18001a8b8  call    cs:__imp_WaitForSingleObject
0x18001a8be  cmp     eax, ebx
0x18001a8c0  jz      loc_18001AAA7
0x18001a8c6  mov     rbx, cs:hObject
0x18001a8cd  mov     [rbp+57h+var_90], rbx
0x18001a8d1  xor     ecx, ecx; Time
0x18001a8d3  call    cs:__imp_time
0x18001a8d9  mov     [rbp+57h+Time], rax
0x18001a8dd  lea     rcx, [rbp+57h+Time]; Time
0x18001a8e1  call    cs:__imp_localtime
0x18001a8e7  lea     r14, WPP_GLOBAL_Control
0x18001a8ee  xor     esi, esi
0x18001a8f0  test    rax, rax
0x18001a8f3  jz      loc_18001AB09
0x18001a8f9  mov     edi, 7FFFFFFEh
0x18001a8fe  mov     rcx, rax; Tm
0x18001a901  call    cs:__imp_asctime
0x18001a907  lea     ecx, [rsi+40h]
0x18001a90a  lea     rdx, [rbp+57h+var_80]
0x18001a90e  test    rdi, rdi
0x18001a911  jz      short loc_18001A92D
0x18001a913  mov     r8b, [rax]
0x18001a916  test    r8b, r8b
0x18001a919  jz      short loc_18001A92D
0x18001a91b  inc     rax
0x18001a91e  mov     [rdx], r8b
0x18001a921  inc     rdx
0x18001a924  dec     rdi
0x18001a927  sub     rcx, 1
0x18001a92b  jnz     short loc_18001A90E
0x18001a92d  mov     rax, rcx
0x18001a930  neg     rax
0x18001a933  sbb     edi, edi
0x18001a935  not     edi
0x18001a937  and     edi, 8007007Ah
0x18001a93d  lea     rax, [rdx-1]
0x18001a941  test    rcx, rcx
0x18001a944  cmovnz  rax, rdx
0x18001a948  mov     [rax], sil
0x18001a94b  jz      loc_18001AAB4
0x18001a951  lea     rcx, [rbp+57h+var_80]
0x18001a955  mov     rax, r15
0x18001a958  inc     rax
0x18001a95b  cmp     [rcx+rax], sil
0x18001a95f  jnz     short loc_18001A958
0x18001a961  cmp     eax, 40h ; '@'
0x18001a964  jl      loc_18001AA92
0x18001a96a  call    cs:__imp_GetTickCount
0x18001a970  mov     dword ptr [rsp+0E0h+argList], eax
0x18001a974  lea     r9, [rbp+57h+var_80]
0x18001a978  lea     r8, aSD; "(%s.%d) : "
0x18001a97f  mov     r14d, 800h
0x18001a985  mov     edx, r14d; unsigned __int64
0x18001a988  lea     rsi, byte_180068D96
0x18001a98f  mov     rcx, rsi; char *
0x18001a992  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18001a997  mov     edi, eax
0x18001a999  test    eax, eax
0x18001a99b  js      loc_18001AB77
0x18001a9a1  inc     r15
0x18001a9a4  cmp     byte ptr [rsi+r15], 0
0x18001a9a9  jnz     short loc_18001A9A1
0x18001a9ab  sub     r14d, r15d
0x18001a9ae  movsxd  r8, r15d
0x18001a9b1  lea     r8, [r8+rsi]; pcchNewDestLength
0x18001a9b5  jz      loc_18001ABCD
0x18001a9bb  movsxd  rcx, r14d
0x18001a9be  cmp     rcx, 7FFFFFFFh
0x18001a9c5  ja      loc_18001ABCF
0x18001a9cb  mov     rax, [rbp+57h+var_98]
0x18001a9cf  mov     rax, [rax]
0x18001a9d2  mov     [rsp+0E0h+argList], rax; argList
0x18001a9d7  mov     r9, r13; pszFormat
0x18001a9da  mov     rdx, rcx; cchDest
0x18001a9dd  mov     rcx, r8; pszDest
0x18001a9e0  call    StringVPrintfWorkerA
0x18001a9e5  mov     edi, eax
0x18001a9e7  test    eax, eax
0x18001a9e9  js      loc_18001ABDD
0x18001a9ef  xor     r8d, r8d; nNumberOfBytesToWrite
0x18001a9f2  lea     rdx, unk_180069596; lpBuffer
0x18001a9f9  mov     rax, rdx
0x18001a9fc  mov     cl, cs:byte_180068D96
0x18001aa02  test    cl, cl
0x18001aa04  jz      short loc_18001AA1A
0x18001aa06  cmp     cl, 0Ah
0x18001aa09  jz      short loc_18001AA81
0x18001aa0b  mov     [rax], cl
0x18001aa0d  inc     rsi
0x18001aa10  inc     rax
0x18001aa13  inc     r8d
0x18001aa16  mov     cl, [rsi]
0x18001aa18  jmp     short loc_18001AA02
0x18001aa1a  mov     byte ptr [rax], 0
0x18001aa1d  mov     [rbp+57h+NumberOfBytesWritten], 0
0x18001aa24  mov     [rsp+0E0h+argList], 0; lpOverlapped
0x18001aa2d  lea     r9, [rbp+57h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18001aa31  mov     rcx, r12; hFile
0x18001aa34  call    cs:__imp_WriteFile
0x18001aa3a  nop
0x18001aa3b  mov     rcx, rbx; hMutex
0x18001aa3e  call    cs:__imp_ReleaseMutex
0x18001aa44  nop
0x18001aa45  test    r12, r12
0x18001aa48  jnz     short loc_18001AA76
0x18001aa4a  mov     eax, 1
0x18001aa4f  mov     rcx, [rbp+57h+var_40]
0x18001aa53  xor     rcx, rsp; StackCookie
0x18001aa56  call    __security_check_cookie
0x18001aa5b  mov     rbx, [rsp+0E0h+arg_0]
0x18001aa63  add     rsp, 0B0h
0x18001aa6a  pop     r15
0x18001aa6c  pop     r14
0x18001aa6e  pop     r13
0x18001aa70  pop     r12
0x18001aa72  pop     rdi
0x18001aa73  pop     rsi
0x18001aa74  pop     rbp
0x18001aa75  retn
0x18001aa76  mov     rcx, r12; hObject
0x18001aa79  call    cs:__imp_CloseHandle
0x18001aa7f  jmp     short loc_18001AA4A
0x18001aa81  mov     byte ptr [rax], 0Dh
0x18001aa84  inc     rax
0x18001aa87  inc     r8d
0x18001aa8a  mov     byte ptr [rax], 0Ah
0x18001aa8d  jmp     loc_18001AA0D
0x18001aa92  cdqe
0x18001aa94  dec     rax
0x18001aa97  cmp     rax, 40h ; '@'
0x18001aa9b  jnb     short loc_18001AB03
0x18001aa9d  mov     [rbp+rax+57h+var_80], sil
0x18001aaa2  jmp     loc_18001A96A
0x18001aaa7  lea     rcx, [rbp+57h+var_A8]; this
0x18001aaab  call    ??1CCloseMe@@QEAA@XZ; CCloseMe::~CCloseMe(void)
0x18001aab0  xor     eax, eax
0x18001aab2  jmp     short loc_18001AA4F
0x18001aab4  mov     edx, edi; int
0x18001aab6  lea     rcx, unk_18006A9C0; this
0x18001aabd  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001aac2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001aac9  cmp     rcx, r14
0x18001aacc  jz      loc_18001A951
0x18001aad2  test    byte ptr [rcx+1Ch], 1
0x18001aad6  jz      loc_18001A951
0x18001aadc  cmp     byte ptr [rcx+19h], 2
0x18001aae0  jb      loc_18001A951
0x18001aae6  mov     edx, 17h
0x18001aaeb  mov     r9d, edi
0x18001aaee  lea     r8, WPP_a66c463c75c73635afca8e74831cc57c_Traceguids
0x18001aaf5  mov     rcx, [rcx+10h]
0x18001aaf9  call    WPP_SF_D
0x18001aafe  jmp     loc_18001A951
0x18001ab03  call    __report_rangecheckfailure
0x18001ab09  lea     r8, asc_18004D808; "??"
0x18001ab10  mov     edx, 40h ; '@'; unsigned __int64
0x18001ab15  lea     rcx, [rbp+57h+var_80]; char *
0x18001ab19  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x18001ab1e  mov     edi, eax
0x18001ab20  test    eax, eax
0x18001ab22  jns     loc_18001A96A
0x18001ab28  mov     edx, eax; int
0x18001ab2a  lea     rcx, unk_18006A9C0; this
0x18001ab31  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001ab36  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ab3d  cmp     rcx, r14
0x18001ab40  jz      loc_18001A96A
0x18001ab46  test    byte ptr [rcx+1Ch], 1
0x18001ab4a  jz      loc_18001A96A
0x18001ab50  cmp     byte ptr [rcx+19h], 2
0x18001ab54  jb      loc_18001A96A
0x18001ab5a  mov     edx, 18h
0x18001ab5f  mov     r9d, edi
0x18001ab62  lea     r8, WPP_a66c463c75c73635afca8e74831cc57c_Traceguids
0x18001ab69  mov     rcx, [rcx+10h]
0x18001ab6d  call    WPP_SF_D
0x18001ab72  jmp     loc_18001A96A
0x18001ab77  mov     edx, edi; int
0x18001ab79  lea     rcx, unk_18006A9C0; this
0x18001ab80  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001ab85  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ab8c  lea     rax, WPP_GLOBAL_Control
0x18001ab93  cmp     rcx, rax
0x18001ab96  jz      loc_18001A9A1
0x18001ab9c  test    byte ptr [rcx+1Ch], 1
0x18001aba0  jz      loc_18001A9A1
0x18001aba6  cmp     byte ptr [rcx+19h], 2
0x18001abaa  jb      loc_18001A9A1
0x18001abb0  mov     edx, 19h
0x18001abb5  mov     r9d, edi
0x18001abb8  lea     r8, WPP_a66c463c75c73635afca8e74831cc57c_Traceguids
0x18001abbf  mov     rcx, [rcx+10h]
0x18001abc3  call    WPP_SF_D
0x18001abc8  jmp     loc_18001A9A1
0x18001abcd  xor     ecx, ecx
0x18001abcf  mov     edi, 80070057h
0x18001abd4  test    rcx, rcx
0x18001abd7  jz      short loc_18001ABDD
0x18001abd9  mov     byte ptr [r8], 0
0x18001abdd  mov     edx, edi; int
0x18001abdf  lea     rcx, unk_18006A9C0; this
0x18001abe6  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001abeb  mov     rcx, cs:WPP_GLOBAL_Control
0x18001abf2  lea     rax, WPP_GLOBAL_Control
0x18001abf9  cmp     rcx, rax
0x18001abfc  jz      loc_18001A9EF
0x18001ac02  test    byte ptr [rcx+1Ch], 1
0x18001ac06  jz      loc_18001A9EF
0x18001ac0c  cmp     byte ptr [rcx+19h], 2
0x18001ac10  jb      loc_18001A9EF
0x18001ac16  mov     edx, 1Ah
0x18001ac1b  mov     r9d, edi
0x18001ac1e  lea     r8, WPP_a66c463c75c73635afca8e74831cc57c_Traceguids
0x18001ac25  mov     rcx, [rcx+10h]
0x18001ac29  call    WPP_SF_D
0x18001ac2e  jmp     loc_18001A9EF
```
