# DavCommitUrlCacheEntry

- ea: `0x180019240`
- end: `0x18001944b`
- name: `DavCommitUrlCacheEntry`
- size: `523`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001507c`
- `0x18001832c`

## callees

- `0x18000b7dc`
- `0x180019240`
- `0x18002a7d4`
- `0x18002cfa0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800192ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800193a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800192ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800193a2`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800192d7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800192d7`
- `KERNEL32!SystemTimeToFileTime` at `0x1800192c2`
- `KERNEL32!SystemTimeToFileTime` at `0x1800192e5`
- `KERNEL32!SystemTimeToFileTime` at `0x18001937a`
- `KERNEL32!SystemTimeToFileTime` at `0x1800192c2`
- `KERNEL32!SystemTimeToFileTime` at `0x1800192e5`
- `KERNEL32!SystemTimeToFileTime` at `0x18001937a`
- `WINHTTP!WinHttpCloseHandle` at `0x180019398`
- `WINHTTP!WinHttpCloseHandle` at `0x180019398`
- `WINHTTP!WinHttpQueryHeaders` at `0x1800192b0`
- `WINHTTP!WinHttpQueryHeaders` at `0x180019368`
- `WINHTTP!WinHttpQueryHeaders` at `0x1800192b0`
- `WINHTTP!WinHttpQueryHeaders` at `0x180019368`

## pseudocode

```c
__int64 __fastcall DavCommitUrlCacheEntry(_QWORD *a1)
{
  void *v2; // rcx
  DWORD LastError; // ebx
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  void *v6; // rcx
  void *v7; // rcx
  DWORD dwIndex; // [rsp+40h] [rbp-40h] BYREF
  DWORD dwBufferLength; // [rsp+44h] [rbp-3Ch] BYREF
  struct _FILETIME FileTime; // [rsp+48h] [rbp-38h] BYREF
  struct _FILETIME v12; // [rsp+50h] [rbp-30h] BYREF
  SYSTEMTIME Buffer; // [rsp+58h] [rbp-28h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+68h] [rbp-18h] BYREF

  FileTime = 0;
  v2 = (void *)a1[74];
  v12 = 0;
  dwBufferLength = 16;
  dwIndex = 0;
  Buffer = 0;
  if ( !v2
    || !WinHttpQueryHeaders(v2, 0x4000000Au, 0, &Buffer, &dwBufferLength, &dwIndex)
    || !SystemTimeToFileTime(&Buffer, &FileTime) )
  {
    SystemTime = 0;
    GetSystemTime(&SystemTime);
    if ( !SystemTimeToFileTime(&SystemTime, &FileTime) )
    {
      LastError = GetLastError();
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v5 = 237;
LABEL_23:
        WPP_SF_d(v4[2], v5, WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids, LastError);
        return LastError;
      }
      return LastError;
    }
    *(_QWORD *)&FileTime += 6000000000LL;
  }
  v6 = (void *)a1[74];
  dwBufferLength = 16;
  dwIndex = 0;
  if ( !v6
    || !WinHttpQueryHeaders(v6, 0x4000000Bu, 0, &Buffer, &dwBufferLength, &dwIndex)
    || !SystemTimeToFileTime(&Buffer, &v12) )
  {
    v12 = 0;
  }
  v7 = (void *)a1[74];
  if ( !v7 )
  {
LABEL_19:
    LastError = TfsCommitEntry((_DWORD)v7, a1[73], a1[72], FileTime.dwLowDateTime, *(_QWORD *)&v12);
    if ( LastError )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v5 = 239;
        goto LABEL_23;
      }
    }
    return LastError;
  }
  if ( WinHttpCloseHandle(v7) )
  {
    a1[74] = 0;
    goto LABEL_19;
  }
  LastError = GetLastError();
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v5 = 238;
    goto LABEL_23;
  }
  return LastError;
}

```

## disassembly

```asm
0x180019240  mov     [rsp-8+arg_8], rbx
0x180019245  push    rbp
0x180019246  mov     rbp, rsp
0x180019249  sub     rsp, 80h
0x180019250  mov     rax, cs:__security_cookie
0x180019257  xor     rax, rsp
0x18001925a  mov     [rbp+var_8], rax
0x18001925e  mov     rbx, rcx
0x180019261  mov     qword ptr [rbp+FileTime.dwLowDateTime], 0
0x180019269  mov     rcx, [rcx+250h]; hRequest
0x180019270  xorps   xmm0, xmm0
0x180019273  mov     qword ptr [rbp+var_30.dwLowDateTime], 0
0x18001927b  mov     [rbp+dwBufferLength], 10h
0x180019282  mov     [rbp+dwIndex], 0
0x180019289  movups  [rbp+Buffer], xmm0
0x18001928d  test    rcx, rcx
0x180019290  jz      short loc_1800192CC
0x180019292  lea     rax, [rbp+dwIndex]
0x180019296  xor     r8d, r8d; pwszName
0x180019299  mov     [rsp+80h+lpdwIndex], rax; lpdwIndex
0x18001929e  lea     r9, [rbp+Buffer]; lpBuffer
0x1800192a2  lea     rax, [rbp+dwBufferLength]
0x1800192a6  mov     edx, 4000000Ah; dwInfoLevel
0x1800192ab  mov     [rsp+80h+lpdwBufferLength], rax; lpdwBufferLength
0x1800192b0  call    cs:__imp_WinHttpQueryHeaders
0x1800192b6  test    eax, eax
0x1800192b8  jz      short loc_1800192CC
0x1800192ba  lea     rdx, [rbp+FileTime]; lpFileTime
0x1800192be  lea     rcx, [rbp+Buffer]; lpSystemTime
0x1800192c2  call    cs:__imp_SystemTimeToFileTime
0x1800192c8  test    eax, eax
0x1800192ca  jnz     short loc_180019330
0x1800192cc  xorps   xmm0, xmm0
0x1800192cf  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x1800192d3  movups  xmmword ptr [rbp+SystemTime.wYear], xmm0
0x1800192d7  call    cs:__imp_GetSystemTime
0x1800192dd  lea     rdx, [rbp+FileTime]; lpFileTime
0x1800192e1  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x1800192e5  call    cs:__imp_SystemTimeToFileTime
0x1800192eb  test    eax, eax
0x1800192ed  jnz     short loc_180019322
0x1800192ef  call    cs:__imp_GetLastError
0x1800192f5  mov     ebx, eax
0x1800192f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800192fe  lea     rax, WPP_GLOBAL_Control
0x180019305  cmp     rcx, rax
0x180019308  jz      loc_18001942C
0x18001930e  test    byte ptr [rcx+1Ch], 1
0x180019312  jz      loc_18001942C
0x180019318  mov     edx, 0EDh
0x18001931d  jmp     loc_180019419
0x180019322  mov     rax, 165A0BC00h
0x18001932c  add     qword ptr [rbp+FileTime.dwLowDateTime], rax
0x180019330  mov     rcx, [rbx+250h]; hRequest
0x180019337  mov     [rbp+dwBufferLength], 10h
0x18001933e  mov     [rbp+dwIndex], 0
0x180019345  test    rcx, rcx
0x180019348  jz      short loc_180019384
0x18001934a  lea     rax, [rbp+dwIndex]
0x18001934e  xor     r8d, r8d; pwszName
0x180019351  mov     [rsp+80h+lpdwIndex], rax; lpdwIndex
0x180019356  lea     r9, [rbp+Buffer]; lpBuffer
0x18001935a  lea     rax, [rbp+dwBufferLength]
0x18001935e  mov     edx, 4000000Bh; dwInfoLevel
0x180019363  mov     [rsp+80h+lpdwBufferLength], rax; lpdwBufferLength
0x180019368  call    cs:__imp_WinHttpQueryHeaders
0x18001936e  test    eax, eax
0x180019370  jz      short loc_180019384
0x180019372  lea     rdx, [rbp+var_30]; lpFileTime
0x180019376  lea     rcx, [rbp+Buffer]; lpSystemTime
0x18001937a  call    cs:__imp_SystemTimeToFileTime
0x180019380  test    eax, eax
0x180019382  jnz     short loc_18001938C
0x180019384  mov     qword ptr [rbp+var_30.dwLowDateTime], 0
0x18001938c  mov     rcx, [rbx+250h]; hInternet
0x180019393  test    rcx, rcx
0x180019396  jz      short loc_1800193D5
0x180019398  call    cs:__imp_WinHttpCloseHandle
0x18001939e  test    eax, eax
0x1800193a0  jnz     short loc_1800193CA
0x1800193a2  call    cs:__imp_GetLastError
0x1800193a8  mov     ebx, eax
0x1800193aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800193b1  lea     rax, WPP_GLOBAL_Control
0x1800193b8  cmp     rcx, rax
0x1800193bb  jz      short loc_18001942C
0x1800193bd  test    byte ptr [rcx+1Ch], 1
0x1800193c1  jz      short loc_18001942C
0x1800193c3  mov     edx, 0EEh
0x1800193c8  jmp     short loc_180019419
0x1800193ca  mov     qword ptr [rbx+250h], 0
0x1800193d5  mov     rax, qword ptr [rbp+var_30.dwLowDateTime]
0x1800193d9  mov     r9, qword ptr [rbp+FileTime.dwLowDateTime]
0x1800193dd  mov     r8, [rbx+240h]
0x1800193e4  mov     rdx, [rbx+248h]
0x1800193eb  mov     [rsp+80h+lpdwBufferLength], rax
0x1800193f0  call    TfsCommitEntry
0x1800193f5  mov     ebx, eax
0x1800193f7  test    eax, eax
0x1800193f9  jz      short loc_18001942C
0x1800193fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180019402  lea     rax, WPP_GLOBAL_Control
0x180019409  cmp     rcx, rax
0x18001940c  jz      short loc_18001942C
0x18001940e  test    byte ptr [rcx+1Ch], 1
0x180019412  jz      short loc_18001942C
0x180019414  mov     edx, 0EFh
0x180019419  mov     rcx, [rcx+10h]
0x18001941d  lea     r8, WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids
0x180019424  mov     r9d, ebx
0x180019427  call    WPP_SF_d
0x18001942c  mov     eax, ebx
0x18001942e  mov     rcx, [rbp+var_8]
0x180019432  xor     rcx, rsp; StackCookie
0x180019435  call    __security_check_cookie
0x18001943a  mov     rbx, [rsp+80h+arg_8]
0x180019442  add     rsp, 80h
0x180019449  pop     rbp
0x18001944a  retn
```
