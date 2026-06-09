# TracePutsExA

- ea: `0x1800046c0`
- end: `0x1800049c1`
- name: `TracePutsExA`
- size: `769`
- prototype: `DWORD __stdcall(DWORD dwTraceID, DWORD dwFlags, LPCSTR lpszString)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180001c20`
- `0x180003040`
- `0x180003bb0`
- `0x1800046c0`
- `0x180006794`
- `0x180009694`
- `0x180009810`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800047ae`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800047ae`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000479d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000495d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000479d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000495d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000496b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000496b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004821`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004862`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800048b4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800048fb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004821`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004862`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800048b4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800048fb`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x1800047f2`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x1800047f2`

## pseudocode

```c
DWORD __stdcall TracePutsExA(DWORD dwTraceID, DWORD dwFlags, LPCSTR lpszString)
{
  const char *v3; // r12
  DWORD v4; // esi
  __int64 v5; // rbx
  LPCRITICAL_SECTION v6; // r13
  int v7; // eax
  bool v8; // zf
  __int64 v9; // rbx
  DWORD v11; // edi
  HANDLE ProcessHeap; // rax
  char *v13; // r15
  DWORD v14; // r14d
  __int64 v15; // rcx
  int v16; // eax
  int v17; // ebx
  int v18; // edi
  int v19; // esi
  int v20; // r14d
  int v21; // r15d
  DWORD v22; // eax
  unsigned int v23; // eax
  DWORD v24; // eax
  int wMilliseconds; // ebx
  int wSecond; // edi
  int wMinute; // esi
  int wHour; // r14d
  int wDay; // r15d
  int wMonth; // r12d
  DWORD CurrentThreadId; // r9d
  DWORD v32; // eax
  int v33; // edi
  HANDLE v34; // rax
  int v35; // [rsp+20h] [rbp-59h]
  int v36; // [rsp+28h] [rbp-51h]
  char *pszDest; // [rsp+68h] [rbp-11h]
  __int64 v40; // [rsp+78h] [rbp-1h]
  struct _SYSTEMTIME SystemTime; // [rsp+80h] [rbp+7h] BYREF

  v3 = lpszString;
  v4 = dwFlags;
  SystemTime = 0;
  if ( dwTraceID - 1 > 0xFFFFFFFD )
    return 87;
  v5 = dwTraceID ^ 0xDCBA0000;
  if ( (unsigned int)v5 >= 0x3C )
    return 0;
  if ( !lpszString )
    return 0;
  v6 = g_server;
  if ( !g_server )
    return 0;
  if ( !g_server[2].DebugInfo )
    return 1003;
  if ( !g_serverThread )
    TraceCreateServerThread(0, 0, 0);
  v7 = *((_DWORD *)&v6[2].SpinCount + v5);
  if ( (v4 & 2) != 0 )
    v8 = (v4 & v7 & 0xFFFF0000) == 0;
  else
    v8 = v7 == 0;
  if ( v8 )
    return 0;
  _mm_lfence();
  AcquireReadLock(v6);
  v9 = *(&v6[8].SpinCount + v5);
  v40 = v9;
  if ( !v9 )
  {
    ReleaseReadLock(v6);
    return 0;
  }
  AcquireReadLock(v9);
  if ( (*(_BYTE *)(v9 + 56) & 1) != 0 )
  {
    v11 = 0;
LABEL_19:
    ReleaseReadLock(v9);
    ReleaseReadLock(v6);
    return v11;
  }
  ProcessHeap = GetProcessHeap();
  pszDest = (char *)HeapAlloc(ProcessHeap, 0, 0x1388u);
  v13 = pszDest;
  if ( !pszDest )
  {
    v11 = 8;
    goto LABEL_19;
  }
  v14 = 0;
  if ( (v4 & 1) == 0 )
  {
    GetLocalTime(&SystemTime);
    v16 = v4 & 8;
    if ( (v4 & 4) != 0 )
    {
      wMilliseconds = SystemTime.wMilliseconds;
      wSecond = SystemTime.wSecond;
      wMinute = SystemTime.wMinute;
      wHour = SystemTime.wHour;
      if ( v16 )
      {
        wDay = SystemTime.wDay;
        wMonth = SystemTime.wMonth;
        CurrentThreadId = GetCurrentThreadId();
        v36 = wDay;
        v13 = pszDest;
        v23 = StringCbPrintfA(
                pszDest,
                0x1388u,
                "\r\n[%03d] %02u-%02u %02u:%02u:%02u:%03u: %s",
                CurrentThreadId,
                wMonth,
                v36,
                wHour,
                wMinute,
                wSecond,
                wMilliseconds,
                lpszString);
      }
      else
      {
        v32 = GetCurrentThreadId();
        v23 = StringCbPrintfA(
                pszDest,
                0x1388u,
                "\r\n[%03d] %02u:%02u:%02u:%03u: %s",
                v32,
                wHour,
                wMinute,
                wSecond,
                wMilliseconds,
                v3);
      }
    }
    else
    {
      v17 = SystemTime.wSecond;
      v18 = SystemTime.wMinute;
      v19 = SystemTime.wHour;
      if ( !v16 )
      {
        v24 = GetCurrentThreadId();
        v23 = StringCbPrintfA(pszDest, 0x1388u, "\r\n[%03d] %02u:%02u:%02u: %s", v24, v19, v18, v17, v3);
LABEL_30:
        v9 = v40;
        v15 = v23;
        v4 = dwFlags;
        v3 = v13;
        goto LABEL_31;
      }
      v20 = SystemTime.wDay;
      v21 = SystemTime.wMonth;
      v22 = GetCurrentThreadId();
      v35 = v21;
      v13 = pszDest;
      v23 = StringCbPrintfA(
              pszDest,
              0x1388u,
              "\r\n[%03d] %02u-%02u %02u:%02u:%02u: %s",
              v22,
              v35,
              v20,
              v19,
              v18,
              v17,
              v3);
    }
    v14 = 0;
    goto LABEL_30;
  }
  v15 = 0;
LABEL_31:
  v33 = (unsigned __int16)v15;
  if ( (int)v15 >= 0 )
    v33 = 0;
  if ( !v33 )
    v14 = TraceWriteOutputA(v15, v9, v4, v3);
  v34 = GetProcessHeap();
  HeapFree(v34, 0, v13);
  ReleaseReadLock(v9);
  ReleaseReadLock(v6);
  if ( v33 )
    return 0;
  return v14;
}

```

## disassembly

```asm
0x1800046c0  mov     [rsp-8+arg_8], rbx
0x1800046c5  push    rbp
0x1800046c6  push    rsi
0x1800046c7  push    rdi
0x1800046c8  push    r12
0x1800046ca  push    r13
0x1800046cc  push    r14
0x1800046ce  push    r15
0x1800046d0  lea     rbp, [rsp-27h]
0x1800046d5  sub     rsp, 0A0h
0x1800046dc  mov     rax, cs:__security_cookie
0x1800046e3  xor     rax, rsp
0x1800046e6  mov     [rbp+57h+var_40], rax
0x1800046ea  lea     eax, [rcx-1]
0x1800046ed  mov     [rbp+57h+var_60], r8
0x1800046f1  mov     [rbp+57h+var_6C], edx
0x1800046f4  xorps   xmm0, xmm0
0x1800046f7  mov     r12, r8
0x1800046fa  mov     esi, edx
0x1800046fc  mov     ebx, ecx
0x1800046fe  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x180004702  cmp     eax, 0FFFFFFFDh
0x180004705  ja      loc_180004995
0x18000470b  xor     ebx, 0DCBA0000h
0x180004711  cmp     ebx, 3Ch ; '<'
0x180004714  jnb     short loc_180004784
0x180004716  test    r8, r8
0x180004719  jz      short loc_180004784
0x18000471b  mov     r13, cs:g_server
0x180004722  test    r13, r13
0x180004725  jz      short loc_180004784
0x180004727  cmp     qword ptr [r13+50h], 0
0x18000472c  jz      loc_18000498E
0x180004732  cmp     cs:g_serverThread, 0
0x18000473a  jnz     short loc_180004748
0x18000473c  xor     r8d, r8d
0x18000473f  xor     edx, edx
0x180004741  xor     ecx, ecx
0x180004743  call    TraceCreateServerThread
0x180004748  mov     eax, [r13+rbx*4+70h]
0x18000474d  test    sil, 2
0x180004751  jz      short loc_18000475C
0x180004753  and     eax, esi
0x180004755  test    eax, 0FFFF0000h
0x18000475a  jmp     short loc_18000475E
0x18000475c  test    eax, eax
0x18000475e  jz      short loc_180004784
0x180004760  lfence
0x180004763  mov     rcx, r13
0x180004766  call    AcquireReadLock
0x18000476b  mov     rbx, [r13+rbx*8+160h]
0x180004773  mov     [rbp+57h+var_58], rbx
0x180004777  test    rbx, rbx
0x18000477a  jnz     short loc_18000478B
0x18000477c  mov     rcx, r13
0x18000477f  call    ReleaseReadLock
0x180004784  xor     eax, eax
0x180004786  jmp     loc_18000499A
0x18000478b  mov     rcx, rbx
0x18000478e  call    AcquireReadLock
0x180004793  test    byte ptr [rbx+38h], 1
0x180004797  jz      short loc_18000479D
0x180004799  xor     edi, edi
0x18000479b  jmp     short loc_1800047C3
0x18000479d  call    cs:__imp_GetProcessHeap
0x1800047a3  xor     edx, edx; dwFlags
0x1800047a5  mov     r8d, 1388h; dwBytes
0x1800047ab  mov     rcx, rax; hHeap
0x1800047ae  call    cs:__imp_HeapAlloc
0x1800047b4  mov     [rbp+57h+pszDest], rax
0x1800047b8  mov     r15, rax
0x1800047bb  test    rax, rax
0x1800047be  jnz     short loc_1800047DA
0x1800047c0  lea     edi, [rax+8]
0x1800047c3  mov     rcx, rbx
0x1800047c6  call    ReleaseReadLock
0x1800047cb  mov     rcx, r13
0x1800047ce  call    ReleaseReadLock
0x1800047d3  mov     eax, edi
0x1800047d5  jmp     loc_18000499A
0x1800047da  xor     r14d, r14d
0x1800047dd  mov     [rbp+57h+var_70], r14d
0x1800047e1  test    sil, 1
0x1800047e5  jz      short loc_1800047EE
0x1800047e7  xor     ecx, ecx
0x1800047e9  jmp     loc_18000493E
0x1800047ee  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x1800047f2  call    cs:__imp_GetLocalTime
0x1800047f8  mov     eax, esi
0x1800047fa  and     eax, 8
0x1800047fd  test    sil, 4
0x180004801  jnz     loc_180004895
0x180004807  movzx   ebx, [rbp+57h+SystemTime.wSecond]
0x18000480b  movzx   edi, [rbp+57h+SystemTime.wMinute]
0x18000480f  movzx   esi, [rbp+57h+SystemTime.wHour]
0x180004813  test    eax, eax
0x180004815  jz      short loc_180004862
0x180004817  movzx   r14d, [rbp+57h+SystemTime.wDay]
0x18000481c  movzx   r15d, [rbp+57h+SystemTime.wMonth]
0x180004821  call    cs:__imp_GetCurrentThreadId
0x180004827  mov     [rsp+0D0h+var_88], r12
0x18000482c  lea     r8, pszFormat; "\r\n[%03d] %02u-%02u %02u:%02u:%02u: %s"
0x180004833  mov     dword ptr [rsp+0D0h+var_90], ebx
0x180004837  mov     r9d, eax
0x18000483a  mov     dword ptr [rsp+0D0h+var_98], edi
0x18000483e  mov     edx, 1388h; cbDest
0x180004843  mov     [rsp+0D0h+var_A0], esi
0x180004847  mov     [rsp+0D0h+var_A8], r14d
0x18000484c  mov     [rsp+0D0h+var_B0], r15d
0x180004851  mov     r15, [rbp+57h+pszDest]
0x180004855  mov     rcx, r15; pszDest
0x180004858  call    StringCbPrintfA
0x18000485d  jmp     loc_18000492E
0x180004862  call    cs:__imp_GetCurrentThreadId
0x180004868  mov     [rsp+0D0h+var_98], r12
0x18000486d  lea     r8, a03d02u02u02uS_0; "\r\n[%03d] %02u:%02u:%02u: %s"
0x180004874  mov     [rsp+0D0h+var_A0], ebx
0x180004878  mov     r9d, eax
0x18000487b  mov     [rsp+0D0h+var_A8], edi
0x18000487f  mov     edx, 1388h; cbDest
0x180004884  mov     rcx, r15; pszDest
0x180004887  mov     [rsp+0D0h+var_B0], esi
0x18000488b  call    StringCbPrintfA
0x180004890  jmp     loc_180004932
0x180004895  movzx   ebx, [rbp+57h+SystemTime.wMilliseconds]
0x180004899  movzx   edi, [rbp+57h+SystemTime.wSecond]
0x18000489d  movzx   esi, [rbp+57h+SystemTime.wMinute]
0x1800048a1  movzx   r14d, [rbp+57h+SystemTime.wHour]
0x1800048a6  test    eax, eax
0x1800048a8  jz      short loc_1800048FB
0x1800048aa  movzx   r15d, [rbp+57h+SystemTime.wDay]
0x1800048af  movzx   r12d, [rbp+57h+SystemTime.wMonth]
0x1800048b4  call    cs:__imp_GetCurrentThreadId
0x1800048ba  lea     r8, a03d02u02u02u02_1; "\r\n[%03d] %02u-%02u %02u:%02u:%02u:%03"...
0x1800048c1  mov     edx, 1388h; cbDest
0x1800048c6  mov     r9d, eax
0x1800048c9  mov     rax, [rbp+57h+var_60]
0x1800048cd  mov     [rsp+0D0h+var_80], rax
0x1800048d2  mov     dword ptr [rsp+0D0h+var_88], ebx
0x1800048d6  mov     dword ptr [rsp+0D0h+var_90], edi
0x1800048da  mov     dword ptr [rsp+0D0h+var_98], esi
0x1800048de  mov     [rsp+0D0h+var_A0], r14d
0x1800048e3  mov     [rsp+0D0h+var_A8], r15d
0x1800048e8  mov     r15, [rbp+57h+pszDest]
0x1800048ec  mov     rcx, r15; pszDest
0x1800048ef  mov     [rsp+0D0h+var_B0], r12d
0x1800048f4  call    StringCbPrintfA
0x1800048f9  jmp     short loc_18000492E
0x1800048fb  call    cs:__imp_GetCurrentThreadId
0x180004901  mov     [rsp+0D0h+var_90], r12
0x180004906  lea     r8, a03d02u02u02u03_1; "\r\n[%03d] %02u:%02u:%02u:%03u: %s"
0x18000490d  mov     dword ptr [rsp+0D0h+var_98], ebx
0x180004911  mov     r9d, eax
0x180004914  mov     [rsp+0D0h+var_A0], edi
0x180004918  mov     edx, 1388h; cbDest
0x18000491d  mov     [rsp+0D0h+var_A8], esi
0x180004921  mov     rcx, r15; pszDest
0x180004924  mov     [rsp+0D0h+var_B0], r14d
0x180004929  call    StringCbPrintfA
0x18000492e  mov     r14d, [rbp+57h+var_70]
0x180004932  mov     rbx, [rbp+57h+var_58]
0x180004936  mov     ecx, eax
0x180004938  mov     esi, [rbp+57h+var_6C]
0x18000493b  mov     r12, r15
0x18000493e  xor     eax, eax
0x180004940  movzx   edi, cx
0x180004943  test    ecx, ecx
0x180004945  cmovns  edi, eax
0x180004948  test    edi, edi
0x18000494a  jnz     short loc_18000495D
0x18000494c  mov     r9, r12
0x18000494f  mov     r8d, esi
0x180004952  mov     rdx, rbx
0x180004955  call    TraceWriteOutputA
0x18000495a  mov     r14d, eax
0x18000495d  call    cs:__imp_GetProcessHeap
0x180004963  mov     r8, r15; lpMem
0x180004966  xor     edx, edx; dwFlags
0x180004968  mov     rcx, rax; hHeap
0x18000496b  call    cs:__imp_HeapFree
0x180004971  mov     rcx, rbx
0x180004974  call    ReleaseReadLock
0x180004979  mov     rcx, r13
0x18000497c  call    ReleaseReadLock
0x180004981  xor     ecx, ecx
0x180004983  test    edi, edi
0x180004985  cmovnz  r14d, ecx
0x180004989  mov     eax, r14d
0x18000498c  jmp     short loc_18000499A
0x18000498e  mov     eax, 3EBh
0x180004993  jmp     short loc_18000499A
0x180004995  mov     eax, 57h ; 'W'
0x18000499a  mov     rcx, [rbp+57h+var_40]
0x18000499e  xor     rcx, rsp; StackCookie
0x1800049a1  call    __security_check_cookie
0x1800049a6  mov     rbx, [rsp+0D0h+arg_8]
0x1800049ae  add     rsp, 0A0h
0x1800049b5  pop     r15
0x1800049b7  pop     r14
0x1800049b9  pop     r13
0x1800049bb  pop     r12
0x1800049bd  pop     rdi
0x1800049be  pop     rsi
0x1800049bf  pop     rbp
0x1800049c0  retn
```
