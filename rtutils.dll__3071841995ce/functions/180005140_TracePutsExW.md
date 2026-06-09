# TracePutsExW

- ea: `0x180005140`
- end: `0x180005441`
- name: `TracePutsExW`
- size: `769`
- prototype: `DWORD __stdcall(DWORD dwTraceID, DWORD dwFlags, LPCWSTR lpszString)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180001c20`
- `0x180003bb0`
- `0x1800049c8`
- `0x180005140`
- `0x1800078b0`
- `0x180009694`
- `0x180009810`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000522e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000522e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000521d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800053dd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000521d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800053dd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800053eb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800053eb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800052a1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800052e2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005334`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000537b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800052a1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800052e2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005334`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000537b`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180005272`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180005272`

## pseudocode

```c
DWORD __stdcall TracePutsExW(DWORD dwTraceID, DWORD dwFlags, LPCWSTR lpszString)
{
  const WCHAR *v3; // r12
  DWORD v4; // esi
  __int64 v5; // rbx
  LPCRITICAL_SECTION v6; // r13
  int v7; // eax
  bool v8; // zf
  __int64 v9; // rbx
  DWORD v11; // edi
  HANDLE ProcessHeap; // rax
  wchar_t *v13; // r15
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
  __int64 CurrentThreadId; // r9
  DWORD v32; // eax
  int v33; // edi
  HANDLE v34; // rax
  int v35; // [rsp+20h] [rbp-59h]
  int v36; // [rsp+28h] [rbp-51h]
  wchar_t *pszDest; // [rsp+68h] [rbp-11h]
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
  pszDest = (wchar_t *)HeapAlloc(ProcessHeap, 0, 0x1388u);
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
        v23 = StringCbPrintfW(
                pszDest,
                0x1388u,
                L"\r\n[%03d] %02u-%02u %02u:%02u:%02u:%03u: %s",
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
        v23 = StringCbPrintfW(
                pszDest,
                0x1388u,
                L"\r\n[%03d] %02u:%02u:%02u:%03u: %s",
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
        v23 = StringCbPrintfW(pszDest, 0x1388u, L"\r\n[%03d] %02u:%02u:%02u: %s", v24, v19, v18, v17, v3);
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
      v23 = StringCbPrintfW(
              pszDest,
              0x1388u,
              L"\r\n[%03d] %02u-%02u %02u:%02u:%02u: %s",
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
    v14 = TraceWriteOutputW(v15, v9, v4, v3);
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
0x180005140  mov     [rsp-8+arg_8], rbx
0x180005145  push    rbp
0x180005146  push    rsi
0x180005147  push    rdi
0x180005148  push    r12
0x18000514a  push    r13
0x18000514c  push    r14
0x18000514e  push    r15
0x180005150  lea     rbp, [rsp-27h]
0x180005155  sub     rsp, 0A0h
0x18000515c  mov     rax, cs:__security_cookie
0x180005163  xor     rax, rsp
0x180005166  mov     [rbp+57h+var_40], rax
0x18000516a  lea     eax, [rcx-1]
0x18000516d  mov     [rbp+57h+var_60], r8
0x180005171  mov     [rbp+57h+var_6C], edx
0x180005174  xorps   xmm0, xmm0
0x180005177  mov     r12, r8
0x18000517a  mov     esi, edx
0x18000517c  mov     ebx, ecx
0x18000517e  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x180005182  cmp     eax, 0FFFFFFFDh
0x180005185  ja      loc_180005415
0x18000518b  xor     ebx, 0DCBA0000h
0x180005191  cmp     ebx, 3Ch ; '<'
0x180005194  jnb     short loc_180005204
0x180005196  test    r8, r8
0x180005199  jz      short loc_180005204
0x18000519b  mov     r13, cs:g_server
0x1800051a2  test    r13, r13
0x1800051a5  jz      short loc_180005204
0x1800051a7  cmp     qword ptr [r13+50h], 0
0x1800051ac  jz      loc_18000540E
0x1800051b2  cmp     cs:g_serverThread, 0
0x1800051ba  jnz     short loc_1800051C8
0x1800051bc  xor     r8d, r8d
0x1800051bf  xor     edx, edx
0x1800051c1  xor     ecx, ecx
0x1800051c3  call    TraceCreateServerThread
0x1800051c8  mov     eax, [r13+rbx*4+70h]
0x1800051cd  test    sil, 2
0x1800051d1  jz      short loc_1800051DC
0x1800051d3  and     eax, esi
0x1800051d5  test    eax, 0FFFF0000h
0x1800051da  jmp     short loc_1800051DE
0x1800051dc  test    eax, eax
0x1800051de  jz      short loc_180005204
0x1800051e0  lfence
0x1800051e3  mov     rcx, r13
0x1800051e6  call    AcquireReadLock
0x1800051eb  mov     rbx, [r13+rbx*8+160h]
0x1800051f3  mov     [rbp+57h+var_58], rbx
0x1800051f7  test    rbx, rbx
0x1800051fa  jnz     short loc_18000520B
0x1800051fc  mov     rcx, r13
0x1800051ff  call    ReleaseReadLock
0x180005204  xor     eax, eax
0x180005206  jmp     loc_18000541A
0x18000520b  mov     rcx, rbx
0x18000520e  call    AcquireReadLock
0x180005213  test    byte ptr [rbx+38h], 1
0x180005217  jz      short loc_18000521D
0x180005219  xor     edi, edi
0x18000521b  jmp     short loc_180005243
0x18000521d  call    cs:__imp_GetProcessHeap
0x180005223  xor     edx, edx; dwFlags
0x180005225  mov     r8d, 1388h; dwBytes
0x18000522b  mov     rcx, rax; hHeap
0x18000522e  call    cs:__imp_HeapAlloc
0x180005234  mov     [rbp+57h+pszDest], rax
0x180005238  mov     r15, rax
0x18000523b  test    rax, rax
0x18000523e  jnz     short loc_18000525A
0x180005240  lea     edi, [rax+8]
0x180005243  mov     rcx, rbx
0x180005246  call    ReleaseReadLock
0x18000524b  mov     rcx, r13
0x18000524e  call    ReleaseReadLock
0x180005253  mov     eax, edi
0x180005255  jmp     loc_18000541A
0x18000525a  xor     r14d, r14d
0x18000525d  mov     [rbp+57h+var_70], r14d
0x180005261  test    sil, 1
0x180005265  jz      short loc_18000526E
0x180005267  xor     ecx, ecx
0x180005269  jmp     loc_1800053BE
0x18000526e  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x180005272  call    cs:__imp_GetLocalTime
0x180005278  mov     eax, esi
0x18000527a  and     eax, 8
0x18000527d  test    sil, 4
0x180005281  jnz     loc_180005315
0x180005287  movzx   ebx, [rbp+57h+SystemTime.wSecond]
0x18000528b  movzx   edi, [rbp+57h+SystemTime.wMinute]
0x18000528f  movzx   esi, [rbp+57h+SystemTime.wHour]
0x180005293  test    eax, eax
0x180005295  jz      short loc_1800052E2
0x180005297  movzx   r14d, [rbp+57h+SystemTime.wDay]
0x18000529c  movzx   r15d, [rbp+57h+SystemTime.wMonth]
0x1800052a1  call    cs:__imp_GetCurrentThreadId
0x1800052a7  mov     [rsp+0D0h+var_88], r12
0x1800052ac  lea     r8, a03d02u02u02u02; "\r\n[%03d] %02u-%02u %02u:%02u:%02u: %s"
0x1800052b3  mov     dword ptr [rsp+0D0h+var_90], ebx
0x1800052b7  mov     r9d, eax
0x1800052ba  mov     dword ptr [rsp+0D0h+var_98], edi
0x1800052be  mov     edx, 1388h; cbDest
0x1800052c3  mov     [rsp+0D0h+var_A0], esi
0x1800052c7  mov     [rsp+0D0h+var_A8], r14d
0x1800052cc  mov     [rsp+0D0h+var_B0], r15d
0x1800052d1  mov     r15, [rbp+57h+pszDest]
0x1800052d5  mov     rcx, r15; pszDest
0x1800052d8  call    StringCbPrintfW
0x1800052dd  jmp     loc_1800053AE
0x1800052e2  call    cs:__imp_GetCurrentThreadId
0x1800052e8  mov     [rsp+0D0h+var_98], r12
0x1800052ed  lea     r8, a03d02u02u02uS; "\r\n[%03d] %02u:%02u:%02u: %s"
0x1800052f4  mov     [rsp+0D0h+var_A0], ebx
0x1800052f8  mov     r9d, eax
0x1800052fb  mov     [rsp+0D0h+var_A8], edi
0x1800052ff  mov     edx, 1388h; cbDest
0x180005304  mov     rcx, r15; pszDest
0x180005307  mov     [rsp+0D0h+var_B0], esi
0x18000530b  call    StringCbPrintfW
0x180005310  jmp     loc_1800053B2
0x180005315  movzx   ebx, [rbp+57h+SystemTime.wMilliseconds]
0x180005319  movzx   edi, [rbp+57h+SystemTime.wSecond]
0x18000531d  movzx   esi, [rbp+57h+SystemTime.wMinute]
0x180005321  movzx   r14d, [rbp+57h+SystemTime.wHour]
0x180005326  test    eax, eax
0x180005328  jz      short loc_18000537B
0x18000532a  movzx   r15d, [rbp+57h+SystemTime.wDay]
0x18000532f  movzx   r12d, [rbp+57h+SystemTime.wMonth]
0x180005334  call    cs:__imp_GetCurrentThreadId
0x18000533a  lea     r8, a03d02u02u02u02_0; "\r\n[%03d] %02u-%02u %02u:%02u:%02u:%03"...
0x180005341  mov     edx, 1388h; cbDest
0x180005346  mov     r9d, eax
0x180005349  mov     rax, [rbp+57h+var_60]
0x18000534d  mov     [rsp+0D0h+var_80], rax
0x180005352  mov     dword ptr [rsp+0D0h+var_88], ebx
0x180005356  mov     dword ptr [rsp+0D0h+var_90], edi
0x18000535a  mov     dword ptr [rsp+0D0h+var_98], esi
0x18000535e  mov     [rsp+0D0h+var_A0], r14d
0x180005363  mov     [rsp+0D0h+var_A8], r15d
0x180005368  mov     r15, [rbp+57h+pszDest]
0x18000536c  mov     rcx, r15; pszDest
0x18000536f  mov     [rsp+0D0h+var_B0], r12d
0x180005374  call    StringCbPrintfW
0x180005379  jmp     short loc_1800053AE
0x18000537b  call    cs:__imp_GetCurrentThreadId
0x180005381  mov     [rsp+0D0h+var_90], r12
0x180005386  lea     r8, a03d02u02u02u03_2; "\r\n[%03d] %02u:%02u:%02u:%03u: %s"
0x18000538d  mov     dword ptr [rsp+0D0h+var_98], ebx
0x180005391  mov     r9d, eax
0x180005394  mov     [rsp+0D0h+var_A0], edi
0x180005398  mov     edx, 1388h; cbDest
0x18000539d  mov     [rsp+0D0h+var_A8], esi
0x1800053a1  mov     rcx, r15; pszDest
0x1800053a4  mov     [rsp+0D0h+var_B0], r14d
0x1800053a9  call    StringCbPrintfW
0x1800053ae  mov     r14d, [rbp+57h+var_70]
0x1800053b2  mov     rbx, [rbp+57h+var_58]
0x1800053b6  mov     ecx, eax
0x1800053b8  mov     esi, [rbp+57h+var_6C]
0x1800053bb  mov     r12, r15
0x1800053be  xor     eax, eax
0x1800053c0  movzx   edi, cx
0x1800053c3  test    ecx, ecx
0x1800053c5  cmovns  edi, eax
0x1800053c8  test    edi, edi
0x1800053ca  jnz     short loc_1800053DD
0x1800053cc  mov     r9, r12
0x1800053cf  mov     r8d, esi
0x1800053d2  mov     rdx, rbx
0x1800053d5  call    TraceWriteOutputW
0x1800053da  mov     r14d, eax
0x1800053dd  call    cs:__imp_GetProcessHeap
0x1800053e3  mov     r8, r15; lpMem
0x1800053e6  xor     edx, edx; dwFlags
0x1800053e8  mov     rcx, rax; hHeap
0x1800053eb  call    cs:__imp_HeapFree
0x1800053f1  mov     rcx, rbx
0x1800053f4  call    ReleaseReadLock
0x1800053f9  mov     rcx, r13
0x1800053fc  call    ReleaseReadLock
0x180005401  xor     ecx, ecx
0x180005403  test    edi, edi
0x180005405  cmovnz  r14d, ecx
0x180005409  mov     eax, r14d
0x18000540c  jmp     short loc_18000541A
0x18000540e  mov     eax, 3EBh
0x180005413  jmp     short loc_18000541A
0x180005415  mov     eax, 57h ; 'W'
0x18000541a  mov     rcx, [rbp+57h+var_40]
0x18000541e  xor     rcx, rsp; StackCookie
0x180005421  call    __security_check_cookie
0x180005426  mov     rbx, [rsp+0D0h+arg_8]
0x18000542e  add     rsp, 0A0h
0x180005435  pop     r15
0x180005437  pop     r14
0x180005439  pop     r13
0x18000543b  pop     r12
0x18000543d  pop     rdi
0x18000543e  pop     rsi
0x18000543f  pop     rbp
0x180005440  retn
```
