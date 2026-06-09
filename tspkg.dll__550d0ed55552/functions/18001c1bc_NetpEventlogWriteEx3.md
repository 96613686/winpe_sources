# NetpEventlogWriteEx3

- ea: `0x18001c1bc`
- end: `0x18001c525`
- name: `NetpEventlogWriteEx3`
- size: `873`
- prototype: `__int64 __usercall@<rax>(LPCRITICAL_SECTION lpCriticalSection@<rcx>, int, int, int, LPCWSTR *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001b810`

## callees

- `0x18000b550`
- `0x18000c174`
- `0x18001c1bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c1ec`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c1ec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c4ff`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c4ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c34f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c395`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c34f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c395`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001c42c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001c42c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c264`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c264`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001c224`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001c467`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001c224`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001c467`
- `api-ms-win-eventlog-legacy-l1-1-0!ReportEventW` at `0x18001c38b`
- `api-ms-win-eventlog-legacy-l1-1-0!ReportEventW` at `0x18001c38b`
- `api-ms-win-eventlog-legacy-l1-1-0!RegisterEventSourceW` at `0x18001c341`
- `api-ms-win-eventlog-legacy-l1-1-0!RegisterEventSourceW` at `0x18001c341`
- `api-ms-win-eventlog-legacy-l1-1-0!DeregisterEventSource` at `0x18001c3a5`
- `api-ms-win-eventlog-legacy-l1-1-0!DeregisterEventSource` at `0x18001c3a5`

## pseudocode

```c
__int64 __fastcall NetpEventlogWriteEx3(
        LPCRITICAL_SECTION lpCriticalSection,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        int a6,
        int a7,
        LPCWSTR *lpStrings)
{
  LPCRITICAL_SECTION v9; // rsi
  struct _RTL_CRITICAL_SECTION *DebugInfo; // rdi
  __int64 OwningThread_low; // rbp
  struct _RTL_CRITICAL_SECTION *v12; // r14
  HANDLE OwningThread; // rbx
  PRTL_CRITICAL_SECTION_DEBUG v14; // rax
  struct _RTL_CRITICAL_SECTION **v15; // rcx
  unsigned int v16; // edx
  char *v17; // rcx
  LPCWSTR v18; // r8
  bool v19; // zf
  signed __int64 v20; // r8
  int v21; // eax
  int v22; // r9d
  PRTL_CRITICAL_SECTION_DEBUG v23; // rax
  struct _RTL_CRITICAL_SECTION **v24; // rcx
  PRTL_CRITICAL_SECTION_DEBUG v25; // rax
  DWORD LastError; // ebp
  HANDLE v27; // rax
  void *v28; // rbx
  unsigned int v29; // ecx
  signed int v30; // edx
  unsigned int i; // r9d
  unsigned int v32; // r8d
  LPCWSTR v33; // r10
  __int64 v34; // rax
  unsigned int v35; // edx
  __int64 v36; // r12
  HLOCAL v37; // rax
  __int64 v38; // rdi
  PRTL_CRITICAL_SECTION_DEBUG *v39; // rbx
  LPCWSTR *v40; // rsi
  wchar_t *v41; // r15
  __int64 j; // r14
  PRTL_CRITICAL_SECTION_DEBUG v43; // rax
  __int64 v44; // rax
  LPCRITICAL_SECTION v45; // rsi
  PRTL_CRITICAL_SECTION_DEBUG v46; // rax
  struct _FILETIME SystemTimeAsFileTime; // [rsp+50h] [rbp-68h] BYREF
  LPCWSTR *v49; // [rsp+58h] [rbp-60h]

  v49 = lpStrings;
  EnterCriticalSection(lpCriticalSection);
  v9 = lpCriticalSection + 1;
  DebugInfo = (struct _RTL_CRITICAL_SECTION *)lpCriticalSection[1].DebugInfo;
  if ( DebugInfo != &lpCriticalSection[1] )
  {
    do
    {
      OwningThread_low = LODWORD(lpCriticalSection[1].OwningThread);
      v12 = (struct _RTL_CRITICAL_SECTION *)DebugInfo->DebugInfo;
      SystemTimeAsFileTime = 0;
      if ( (_DWORD)OwningThread_low == -1
        || (OwningThread = DebugInfo->OwningThread,
            GetSystemTimeAsFileTime(&SystemTimeAsFileTime),
            (__int64)(*(_QWORD *)&SystemTimeAsFileTime - (_QWORD)OwningThread) >= 0)
        && *(_QWORD *)&SystemTimeAsFileTime - (_QWORD)OwningThread <= 10000 * OwningThread_low )
      {
        if ( LODWORD(DebugInfo->LockSemaphore) == 6041
          && HIDWORD(DebugInfo->LockSemaphore) == 1
          && !LODWORD(DebugInfo[1].DebugInfo)
          && !LODWORD(DebugInfo[1].OwningThread)
          && LODWORD(DebugInfo[1].SpinCount) == 2
          && !DebugInfo->SpinCount )
        {
          v16 = 0;
          while ( 1 )
          {
            v17 = (char *)*((_QWORD *)DebugInfo[1].LockSemaphore + v16);
            v18 = lpStrings[v16];
            if ( v17 )
            {
              if ( !v18 )
                break;
              v20 = (char *)v18 - v17;
              do
              {
                v21 = *(unsigned __int16 *)&v17[v20];
                v22 = *(unsigned __int16 *)v17 - v21;
                if ( v22 )
                  break;
                v17 += 2;
              }
              while ( v21 );
              v19 = v22 == 0;
            }
            else
            {
              v19 = v18 == 0;
            }
            if ( !v19 )
              break;
            if ( ++v16 >= 2 )
            {
              if ( v16 == 2 )
              {
                v23 = DebugInfo->DebugInfo;
                if ( DebugInfo->DebugInfo->CriticalSection != DebugInfo )
                  goto LABEL_61;
                v24 = *(struct _RTL_CRITICAL_SECTION ***)&DebugInfo->LockCount;
                if ( *v24 != DebugInfo )
                  goto LABEL_61;
                *v24 = (struct _RTL_CRITICAL_SECTION *)v23;
                v23->CriticalSection = (struct _RTL_CRITICAL_SECTION *)v24;
                v25 = v9->DebugInfo;
                if ( v9->DebugInfo->CriticalSection != v9 )
                  goto LABEL_61;
                DebugInfo->DebugInfo = v25;
                LastError = 183;
                *(_QWORD *)&DebugInfo->LockCount = v9;
                v25->CriticalSection = DebugInfo;
                v9->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)DebugInfo;
                ++HIDWORD(DebugInfo[1].SpinCount);
                goto LABEL_63;
              }
              break;
            }
          }
        }
      }
      else
      {
        v14 = DebugInfo->DebugInfo;
        if ( DebugInfo->DebugInfo->CriticalSection != DebugInfo )
          goto LABEL_61;
        v15 = *(struct _RTL_CRITICAL_SECTION ***)&DebugInfo->LockCount;
        if ( *v15 != DebugInfo )
          goto LABEL_61;
        *v15 = (struct _RTL_CRITICAL_SECTION *)v14;
        v14->CriticalSection = (struct _RTL_CRITICAL_SECTION *)v15;
        LocalFree(DebugInfo);
      }
      DebugInfo = v12;
    }
    while ( v12 != v9 );
  }
  v27 = RegisterEventSourceW(0, (LPCWSTR)lpCriticalSection[1].LockSemaphore);
  v28 = v27;
  if ( v27 )
  {
    if ( ReportEventW(v27, 1u, 0, 0x1799u, 0, 2u, 0, lpStrings, 0) )
      LastError = 0;
    else
      LastError = GetLastError();
    DeregisterEventSource(v28);
  }
  else
  {
    LastError = GetLastError();
  }
  if ( LastError )
    goto LABEL_63;
  v29 = 80;
  v30 = 0;
  for ( i = 0; i < 2; ++i )
  {
    if ( v30 < 0 )
      goto LABEL_63;
    v32 = v29 + 8;
    if ( v29 + 8 < v29 )
    {
      v29 = -1;
LABEL_49:
      v30 = -1073741675;
      continue;
    }
    v29 += 8;
    v30 = 0;
    v33 = lpStrings[i];
    if ( !v33 )
      continue;
    v34 = -1;
    do
      ++v34;
    while ( v33[v34] );
    v35 = v32 + 2 * v34;
    v29 = -1;
    if ( v35 < v32 )
      goto LABEL_49;
    if ( v35 + 2 >= v35 )
      v29 = v35 + 2;
    v30 = v35 + 2 < v35 ? 0xC0000095 : 0;
  }
  if ( v30 >= 0 )
  {
    v36 = v29;
    v37 = LocalAlloc(0, v29);
    v38 = 0;
    v39 = (PRTL_CRITICAL_SECTION_DEBUG *)v37;
    if ( v37 )
    {
      *((_DWORD *)v37 + 6) = 6041;
      *((_DWORD *)v37 + 7) = 1;
      *((_QWORD *)v37 + 4) = 0;
      *((_DWORD *)v37 + 10) = 0;
      *((_DWORD *)v37 + 14) = 0;
      *((_DWORD *)v37 + 18) = 2;
      *((_DWORD *)v37 + 19) = 1;
      GetSystemTimeAsFileTime((LPFILETIME)v37 + 2);
      v40 = v49;
      v39[8] = (PRTL_CRITICAL_SECTION_DEBUG)(v39 + 10);
      v41 = (wchar_t *)(v39 + 12);
      for ( j = 0; j != 2; ++j )
      {
        v43 = v39[8];
        if ( v40[j] )
        {
          *(_QWORD *)((char *)&v43->Type + v38 * 8) = v41;
          wcscpy_s(v41, ((unsigned __int64)v39 + v36 - (_QWORD)v41) >> 1, v40[v38]);
          v44 = -1;
          do
            ++v44;
          while ( v40[v38][v44] );
          v41 += v44 + 1;
        }
        else
        {
          *(_QWORD *)((char *)&v43->Type + v38 * 8) = 0;
        }
        ++v38;
      }
      v45 = lpCriticalSection + 1;
      v46 = lpCriticalSection[1].DebugInfo;
      if ( v46->CriticalSection != &lpCriticalSection[1] )
LABEL_61:
        __fastfail(3u);
      *v39 = v46;
      v39[1] = (PRTL_CRITICAL_SECTION_DEBUG)v45;
      v46->CriticalSection = (struct _RTL_CRITICAL_SECTION *)v39;
      v45->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)v39;
    }
  }
LABEL_63:
  LeaveCriticalSection(lpCriticalSection);
  return LastError;
}

```

## disassembly

```asm
0x18001c1bc  push    rbx
0x18001c1be  push    rbp
0x18001c1bf  push    rsi
0x18001c1c0  push    rdi
0x18001c1c1  push    r12
0x18001c1c3  push    r13
0x18001c1c5  push    r14
0x18001c1c7  push    r15
0x18001c1c9  sub     rsp, 78h
0x18001c1cd  mov     rax, cs:__security_cookie
0x18001c1d4  xor     rax, rsp
0x18001c1d7  mov     [rsp+0B8h+var_58], rax
0x18001c1dc  mov     r15, [rsp+0B8h+arg_38]
0x18001c1e4  mov     r13, rcx
0x18001c1e7  mov     [rsp+0B8h+var_60], r15
0x18001c1ec  call    cs:__imp_EnterCriticalSection
0x18001c1f2  lea     rsi, [r13+28h]
0x18001c1f6  xor     r12d, r12d
0x18001c1f9  mov     rdi, [rsi]
0x18001c1fc  lea     r11d, [r12+2]
0x18001c201  cmp     rdi, rsi
0x18001c204  jz      loc_18001C33B
0x18001c20a  mov     ebp, [r13+38h]
0x18001c20e  mov     r14, [rdi]
0x18001c211  mov     qword ptr [rsp+0B8h+SystemTimeAsFileTime.dwLowDateTime], r12
0x18001c216  cmp     ebp, 0FFFFFFFFh
0x18001c219  jz      short loc_18001C272
0x18001c21b  mov     rbx, [rdi+10h]
0x18001c21f  lea     rcx, [rsp+0B8h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18001c224  call    cs:__imp_GetSystemTimeAsFileTime
0x18001c22a  mov     rdx, qword ptr [rsp+0B8h+SystemTimeAsFileTime.dwLowDateTime]
0x18001c22f  sub     rdx, rbx
0x18001c232  js      short loc_18001C240
0x18001c234  imul    rcx, rbp, 2710h
0x18001c23b  cmp     rdx, rcx
0x18001c23e  jle     short loc_18001C26C
0x18001c240  mov     rax, [rdi]
0x18001c243  cmp     [rax+8], rdi
0x18001c247  jnz     loc_18001C4E7
0x18001c24d  mov     rcx, [rdi+8]
0x18001c251  cmp     [rcx], rdi
0x18001c254  jnz     loc_18001C4E7
0x18001c25a  mov     [rcx], rax
0x18001c25d  mov     [rax+8], rcx
0x18001c261  mov     rcx, rdi; hMem
0x18001c264  call    cs:__imp_LocalFree
0x18001c26a  jmp     short loc_18001C2DF
0x18001c26c  mov     r11d, 2
0x18001c272  cmp     dword ptr [rdi+18h], 1799h
0x18001c279  jnz     short loc_18001C2DF
0x18001c27b  cmp     dword ptr [rdi+1Ch], 1
0x18001c27f  jnz     short loc_18001C2DF
0x18001c281  cmp     [rdi+28h], r12d
0x18001c285  jnz     short loc_18001C2DF
0x18001c287  cmp     [rdi+38h], r12d
0x18001c28b  jnz     short loc_18001C2DF
0x18001c28d  cmp     [rdi+48h], r11d
0x18001c291  jnz     short loc_18001C2DF
0x18001c293  cmp     [rdi+20h], r12
0x18001c297  jnz     short loc_18001C2DF
0x18001c299  mov     r10, [rdi+40h]
0x18001c29d  mov     edx, r12d
0x18001c2a0  mov     eax, edx
0x18001c2a2  mov     rcx, [r10+rax*8]
0x18001c2a6  mov     r8, [r15+rax*8]
0x18001c2aa  test    rcx, rcx
0x18001c2ad  jnz     short loc_18001C2B4
0x18001c2af  test    r8, r8
0x18001c2b2  jmp     short loc_18001C2D4
0x18001c2b4  test    r8, r8
0x18001c2b7  jz      short loc_18001C2DF
0x18001c2b9  sub     r8, rcx
0x18001c2bc  movzx   r9d, word ptr [rcx]
0x18001c2c0  movzx   eax, word ptr [rcx+r8]
0x18001c2c5  sub     r9d, eax
0x18001c2c8  jnz     short loc_18001C2D1
0x18001c2ca  add     rcx, r11
0x18001c2cd  test    eax, eax
0x18001c2cf  jnz     short loc_18001C2BC
0x18001c2d1  test    r9d, r9d
0x18001c2d4  jnz     short loc_18001C2DF
0x18001c2d6  inc     edx
0x18001c2d8  cmp     edx, r11d
0x18001c2db  jb      short loc_18001C2A0
0x18001c2dd  jz      short loc_18001C2F2
0x18001c2df  mov     rdi, r14
0x18001c2e2  cmp     r14, rsi
0x18001c2e5  jz      short loc_18001C33B
0x18001c2e7  mov     r11d, 2
0x18001c2ed  jmp     loc_18001C20A
0x18001c2f2  mov     rax, [rdi]
0x18001c2f5  cmp     [rax+8], rdi
0x18001c2f9  jnz     loc_18001C4E7
0x18001c2ff  mov     rcx, [rdi+8]
0x18001c303  cmp     [rcx], rdi
0x18001c306  jnz     loc_18001C4E7
0x18001c30c  mov     [rcx], rax
0x18001c30f  mov     [rax+8], rcx
0x18001c313  mov     rax, [rsi]
0x18001c316  cmp     [rax+8], rsi
0x18001c31a  jnz     loc_18001C4E7
0x18001c320  mov     [rdi], rax
0x18001c323  mov     ebp, 0B7h
0x18001c328  mov     [rdi+8], rsi
0x18001c32c  mov     [rax+8], rdi
0x18001c330  mov     [rsi], rdi
0x18001c333  inc     dword ptr [rdi+4Ch]
0x18001c336  jmp     loc_18001C4FC
0x18001c33b  mov     rdx, [r13+40h]; lpSourceName
0x18001c33f  xor     ecx, ecx; lpUNCServerName
0x18001c341  call    cs:__imp_RegisterEventSourceW
0x18001c347  mov     rbx, rax
0x18001c34a  test    rax, rax
0x18001c34d  jnz     short loc_18001C35D
0x18001c34f  call    cs:__imp_GetLastError
0x18001c355  mov     ebp, eax
0x18001c357  lea     r14d, [rbx+2]
0x18001c35b  jmp     short loc_18001C3AB
0x18001c35d  mov     [rsp+0B8h+lpRawData], r12; lpRawData
0x18001c362  xor     r8d, r8d; wCategory
0x18001c365  mov     [rsp+0B8h+lpStrings], r15; lpStrings
0x18001c36a  mov     r9d, 1799h; dwEventID
0x18001c370  mov     [rsp+0B8h+dwDataSize], r12d; dwDataSize
0x18001c375  mov     rcx, rbx; hEventLog
0x18001c378  lea     r14d, [r8+2]
0x18001c37c  mov     [rsp+0B8h+wNumStrings], r14w; wNumStrings
0x18001c382  lea     edx, [r8+1]; wType
0x18001c386  mov     [rsp+0B8h+lpUserSid], r12; lpUserSid
0x18001c38b  call    cs:__imp_ReportEventW
0x18001c391  test    eax, eax
0x18001c393  jnz     short loc_18001C39F
0x18001c395  call    cs:__imp_GetLastError
0x18001c39b  mov     ebp, eax
0x18001c39d  jmp     short loc_18001C3A2
0x18001c39f  mov     ebp, r12d
0x18001c3a2  mov     rcx, rbx; hEventLog
0x18001c3a5  call    cs:__imp_DeregisterEventSource
0x18001c3ab  test    ebp, ebp
0x18001c3ad  jnz     loc_18001C4FC
0x18001c3b3  lea     ecx, [rbp+50h]
0x18001c3b6  mov     edx, r12d
0x18001c3b9  mov     r9d, r12d
0x18001c3bc  mov     r11d, 0C0000095h
0x18001c3c2  or      ebx, 0FFFFFFFFh
0x18001c3c5  test    edx, edx
0x18001c3c7  js      loc_18001C4FC
0x18001c3cd  lea     r8d, [rcx+8]
0x18001c3d1  cmp     r8d, ecx
0x18001c3d4  jb      short loc_18001C410
0x18001c3d6  mov     eax, r9d
0x18001c3d9  mov     ecx, r8d
0x18001c3dc  mov     edx, r12d
0x18001c3df  mov     r10, [r15+rax*8]
0x18001c3e3  test    r10, r10
0x18001c3e6  jz      short loc_18001C415
0x18001c3e8  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001c3ec  inc     rax
0x18001c3ef  cmp     [r10+rax*2], r12w
0x18001c3f4  jnz     short loc_18001C3EC
0x18001c3f6  lea     edx, [r8+rax*2]
0x18001c3fa  mov     ecx, ebx
0x18001c3fc  cmp     edx, r8d
0x18001c3ff  jb      short loc_18001C412
0x18001c401  lea     eax, [rdx+2]
0x18001c404  cmp     eax, edx
0x18001c406  cmovnb  ecx, eax
0x18001c409  sbb     edx, edx
0x18001c40b  and     edx, r11d
0x18001c40e  jmp     short loc_18001C415
0x18001c410  mov     ecx, ebx
0x18001c412  mov     edx, r11d
0x18001c415  inc     r9d
0x18001c418  cmp     r9d, r14d
0x18001c41b  jb      short loc_18001C3C5
0x18001c41d  test    edx, edx
0x18001c41f  js      loc_18001C4FC
0x18001c425  mov     r12d, ecx
0x18001c428  mov     edx, ecx; uBytes
0x18001c42a  xor     ecx, ecx; uFlags
0x18001c42c  call    cs:__imp_LocalAlloc
0x18001c432  xor     edi, edi
0x18001c434  mov     rbx, rax
0x18001c437  test    rax, rax
0x18001c43a  jz      loc_18001C4FC
0x18001c440  lea     rcx, [rax+10h]; lpSystemTimeAsFileTime
0x18001c444  mov     dword ptr [rax+18h], 1799h
0x18001c44b  mov     dword ptr [rax+1Ch], 1
0x18001c452  mov     [rax+20h], rdi
0x18001c456  mov     [rax+28h], edi
0x18001c459  mov     [rax+38h], edi
0x18001c45c  mov     [rax+48h], r14d
0x18001c460  mov     dword ptr [rax+4Ch], 1
0x18001c467  call    cs:__imp_GetSystemTimeAsFileTime
0x18001c46d  mov     rsi, [rsp+0B8h+var_60]
0x18001c472  lea     rax, [rbx+50h]
0x18001c476  mov     [rbx+40h], rax
0x18001c47a  lea     r15, [rax+10h]
0x18001c47e  mov     r14d, edi
0x18001c481  cmp     qword ptr [rsi+r14*8], 0
0x18001c486  mov     rax, [rbx+40h]
0x18001c48a  jnz     short loc_18001C496
0x18001c48c  mov     qword ptr [rdi+rax], 0
0x18001c494  jmp     short loc_18001C4CD
0x18001c496  mov     [rdi+rax], r15
0x18001c49a  mov     rdx, r12
0x18001c49d  mov     r8, [rsi+rdi]; Source
0x18001c4a1  sub     rdx, r15
0x18001c4a4  add     rdx, rbx
0x18001c4a7  mov     rcx, r15; Destination
0x18001c4aa  shr     rdx, 1; SizeInWords
0x18001c4ad  call    wcscpy_s
0x18001c4b2  mov     rcx, [rsi+rdi]
0x18001c4b6  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001c4ba  xor     edx, edx
0x18001c4bc  inc     rax
0x18001c4bf  cmp     [rcx+rax*2], dx
0x18001c4c3  jnz     short loc_18001C4BC
0x18001c4c5  lea     r15, [r15+rax*2]
0x18001c4c9  add     r15, 2
0x18001c4cd  inc     r14
0x18001c4d0  add     rdi, 8
0x18001c4d4  cmp     r14, 2
0x18001c4d8  jnz     short loc_18001C481
0x18001c4da  lea     rsi, [r13+28h]
0x18001c4de  mov     rax, [rsi]
0x18001c4e1  cmp     [rax+8], rsi
0x18001c4e5  jz      short loc_18001C4EE
0x18001c4e7  mov     ecx, 3
0x18001c4ec  int     29h; Win8: RtlFailFast(ecx)
0x18001c4ee  mov     [rbx], rax
0x18001c4f1  mov     [rbx+8], rsi
0x18001c4f5  mov     [rax+8], rbx
0x18001c4f9  mov     [rsi], rbx
0x18001c4fc  mov     rcx, r13; lpCriticalSection
0x18001c4ff  call    cs:__imp_LeaveCriticalSection
0x18001c505  mov     eax, ebp
0x18001c507  mov     rcx, [rsp+0B8h+var_58]
0x18001c50c  xor     rcx, rsp; StackCookie
0x18001c50f  call    __security_check_cookie
0x18001c514  add     rsp, 78h
0x18001c518  pop     r15
0x18001c51a  pop     r14
0x18001c51c  pop     r13
0x18001c51e  pop     r12
0x18001c520  pop     rdi
0x18001c521  pop     rsi
0x18001c522  pop     rbp
0x18001c523  pop     rbx
0x18001c524  retn
```
