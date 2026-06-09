# TraceDumpExA

- ea: `0x1800030d0`
- end: `0x180003449`
- name: `TraceDumpExA`
- size: `889`
- prototype: `DWORD __stdcall(DWORD dwTraceID, DWORD dwFlags, LPBYTE lpbBytes, DWORD dwByteCount, DWORD dwGroupSize, BOOL bAddressPrefix, LPCSTR lpszPrefix)`
- caller_count: `0`
- callee_count: `10`
- tags: ``

## callees

- `0x180001c20`
- `0x180002830`
- `0x180003040`
- `0x1800030d0`
- `0x180003bb0`
- `0x180004456`
- `0x180006158`
- `0x180009694`
- `0x180009810`
- `0x18000a769`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003231`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003272`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003231`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003272`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180003216`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180003216`

## pseudocode

```c
DWORD __stdcall TraceDumpExA(
        DWORD dwTraceID,
        DWORD dwFlags,
        LPBYTE lpbBytes,
        DWORD dwByteCount,
        DWORD dwGroupSize,
        BOOL bAddressPrefix,
        LPCSTR lpszPrefix)
{
  const char *v7; // r14
  __int64 v12; // rbx
  LPCRITICAL_SECTION v13; // rdi
  int v14; // eax
  __int64 v15; // rsi
  int v16; // ecx
  int v17; // ebx
  int v18; // edi
  int v19; // esi
  DWORD v20; // eax
  HRESULT v21; // eax
  int wMilliseconds; // ebx
  int wSecond; // edi
  int wMinute; // esi
  int wHour; // r14d
  DWORD CurrentThreadId; // eax
  DWORD v27; // ebx
  DWORD v28; // edx
  unsigned int v29; // ecx
  __int64 v30; // rbx
  int v31; // ecx
  int v33; // [rsp+20h] [rbp-E0h]
  LPCRITICAL_SECTION v34; // [rsp+50h] [rbp-B0h]
  DWORD v35; // [rsp+50h] [rbp-B0h]
  __int64 v36; // [rsp+58h] [rbp-A8h]
  struct _SYSTEMTIME SystemTime; // [rsp+60h] [rbp-A0h] BYREF
  int v38[4]; // [rsp+70h] [rbp-90h] BYREF
  char pszDest; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v40[111]; // [rsp+81h] [rbp-7Fh] BYREF

  v7 = lpszPrefix;
  *(_QWORD *)v38 = lpszPrefix;
  pszDest = 0;
  SystemTime = 0;
  memset_0(v40, 0, sizeof(v40));
  if ( dwTraceID - 1 > 0xFFFFFFFD )
    return 87;
  v12 = dwTraceID ^ 0xDCBA0000;
  if ( (unsigned int)v12 >= 0x3C
    || !lpbBytes
    || !dwByteCount
    || ((dwGroupSize - 1) & 0xFFFFFFFC) != 0
    || dwGroupSize == 3 )
  {
    return 87;
  }
  v13 = g_server;
  v34 = g_server;
  if ( !g_server )
    return 0;
  if ( !g_server[2].DebugInfo )
    return 1003;
  if ( !g_serverThread )
    TraceCreateServerThread(0, 0, 0);
  v14 = *((_DWORD *)&v13[2].SpinCount + v12);
  if ( (dwFlags & 2) == 0 )
  {
    if ( v14 )
      goto LABEL_15;
    return 0;
  }
  if ( (dwFlags & v14 & 0xFFFF0000) == 0 )
    return 0;
LABEL_15:
  _mm_lfence();
  AcquireReadLock(v13);
  v15 = *(&v13[8].SpinCount + v12);
  v36 = v15;
  if ( !v15 )
  {
LABEL_36:
    ReleaseReadLock(v13);
    return 0;
  }
  AcquireReadLock(v15);
  if ( (*(_BYTE *)(v15 + 56) & 1) != 0 )
    goto LABEL_35;
  if ( (dwFlags & 1) == 0 )
  {
    GetLocalTime(&SystemTime);
    if ( (dwFlags & 4) != 0 )
    {
      wMilliseconds = SystemTime.wMilliseconds;
      wSecond = SystemTime.wSecond;
      wMinute = SystemTime.wMinute;
      wHour = SystemTime.wHour;
      CurrentThreadId = GetCurrentThreadId();
      v21 = StringCbPrintfA(
              &pszDest,
              0x70u,
              "[%03d] %02u:%02u:%02u:%03u: ",
              CurrentThreadId,
              wHour,
              wMinute,
              wSecond,
              wMilliseconds);
      v7 = *(const char **)v38;
    }
    else
    {
      v17 = SystemTime.wSecond;
      v18 = SystemTime.wMinute;
      v19 = SystemTime.wHour;
      v20 = GetCurrentThreadId();
      v21 = StringCbPrintfA(&pszDest, 0x70u, "[%03d] %02u:%02u:%02u: ", v20, v19, v18, v17);
    }
    v13 = v34;
    v15 = v36;
    if ( v21 < 0 )
      goto LABEL_35;
  }
  if ( v7 && StringCchCatA(&pszDest, 0x70u, v7) < 0 )
  {
LABEL_35:
    ReleaseReadLock(v15);
    goto LABEL_36;
  }
  v27 = 0;
  v28 = dwGroupSize - 1;
  if ( ((dwGroupSize - 1) & (unsigned int)lpbBytes) != 0 )
  {
    v29 = v28 & (unsigned int)lpbBytes;
    *(_OWORD *)v38 = 0;
    if ( (v28 & (unsigned int)lpbBytes) > dwByteCount )
      v29 = dwByteCount;
    v35 = v29;
    v30 = 16 - v29;
    memcpy_0((char *)v38 + v30, lpbBytes, v29);
    v27 = TraceDumpLineA(
            (int)&pszDest,
            v15,
            dwFlags,
            (int)v38,
            v33,
            dwGroupSize,
            bAddressPrefix,
            (__int64)&lpbBytes[-v30],
            &pszDest);
    if ( dwByteCount >= v35 )
    {
      lpbBytes += v35;
      dwByteCount -= v35;
      goto LABEL_29;
    }
    goto LABEL_35;
  }
LABEL_29:
  if ( dwByteCount )
  {
    while ( dwByteCount >= 0x10 )
    {
      v27 += TraceDumpLineA(
               v16,
               v15,
               dwFlags,
               (int)lpbBytes,
               v33,
               dwGroupSize,
               bAddressPrefix,
               (__int64)lpbBytes,
               &pszDest);
      lpbBytes += 16;
      dwByteCount -= 16;
      if ( !dwByteCount )
        goto LABEL_34;
    }
    *(_OWORD *)v38 = 0;
    memcpy_0(v38, lpbBytes, dwByteCount);
    v27 += TraceDumpLineA(v31, v15, dwFlags, (int)v38, v33, dwGroupSize, bAddressPrefix, (__int64)lpbBytes, &pszDest);
  }
LABEL_34:
  ReleaseReadLock(v15);
  ReleaseReadLock(v13);
  return v27;
}

```

## disassembly

```asm
0x1800030d0  push    rbp
0x1800030d2  push    rbx
0x1800030d3  push    r12
0x1800030d5  push    r13
0x1800030d7  push    r14
0x1800030d9  push    r15
0x1800030db  lea     rbp, [rsp-8]
0x1800030e0  sub     rsp, 108h
0x1800030e7  mov     rax, cs:__security_cookie
0x1800030ee  xor     rax, rsp
0x1800030f1  mov     [rbp+30h+var_40], rax
0x1800030f5  mov     r14, [rbp+30h+lpszPrefix]
0x1800030f9  mov     r12, r8
0x1800030fc  mov     r13d, edx
0x1800030ff  mov     qword ptr [rsp+130h+var_C0], r14
0x180003104  mov     ebx, ecx
0x180003106  mov     [rbp+30h+pszDest], 0
0x18000310a  xorps   xmm0, xmm0
0x18000310d  lea     rcx, [rbp+30h+var_AF]; void *
0x180003111  xor     edx, edx; Val
0x180003113  mov     r8d, 6Fh ; 'o'; Size
0x180003119  movups  xmmword ptr [rsp+130h+SystemTime.wYear], xmm0
0x18000311e  mov     r15d, r9d
0x180003121  call    memset_0
0x180003126  lea     eax, [rbx-1]
0x180003129  cmp     eax, 0FFFFFFFDh
0x18000312c  ja      loc_180003442
0x180003132  xor     ebx, 0DCBA0000h
0x180003138  cmp     ebx, 3Ch ; '<'
0x18000313b  jnb     loc_180003442
0x180003141  test    r12, r12
0x180003144  jz      loc_180003442
0x18000314a  test    r15d, r15d
0x18000314d  jz      loc_180003442
0x180003153  mov     ecx, [rbp+30h+dwGroupSize]
0x180003156  lea     eax, [rcx-1]
0x180003159  test    eax, 0FFFFFFFCh
0x18000315e  jnz     loc_180003442
0x180003164  cmp     ecx, 3
0x180003167  jz      loc_180003442
0x18000316d  mov     [rsp+130h+var_30], rdi
0x180003175  mov     rdi, cs:g_server
0x18000317c  mov     [rsp+130h+arg_8], rsi
0x180003184  mov     [rsp+130h+var_E0], rdi
0x180003189  test    rdi, rdi
0x18000318c  jz      loc_180003437
0x180003192  cmp     qword ptr [rdi+50h], 0
0x180003197  jz      loc_18000343B
0x18000319d  cmp     cs:g_serverThread, 0
0x1800031a5  jnz     short loc_1800031B3
0x1800031a7  xor     r8d, r8d
0x1800031aa  xor     edx, edx
0x1800031ac  xor     ecx, ecx
0x1800031ae  call    TraceCreateServerThread
0x1800031b3  mov     eax, [rdi+rbx*4+70h]
0x1800031b7  test    r13b, 2
0x1800031bb  jz      short loc_1800031CC
0x1800031bd  and     eax, r13d
0x1800031c0  test    eax, 0FFFF0000h
0x1800031c5  jnz     short loc_1800031D4
0x1800031c7  jmp     loc_180003437
0x1800031cc  test    eax, eax
0x1800031ce  jz      loc_180003437
0x1800031d4  lfence
0x1800031d7  mov     rcx, rdi
0x1800031da  call    AcquireReadLock
0x1800031df  mov     rsi, [rdi+rbx*8+160h]
0x1800031e7  mov     [rsp+130h+var_D8], rsi
0x1800031ec  test    rsi, rsi
0x1800031ef  jz      loc_18000342F
0x1800031f5  mov     rcx, rsi
0x1800031f8  call    AcquireReadLock
0x1800031fd  test    byte ptr [rsi+38h], 1
0x180003201  jnz     loc_180003427
0x180003207  test    r13b, 1
0x18000320b  jnz     loc_1800032B8
0x180003211  lea     rcx, [rsp+130h+SystemTime]; lpSystemTime
0x180003216  call    cs:__imp_GetLocalTime
0x18000321c  test    r13b, 4
0x180003220  jnz     short loc_18000325D
0x180003222  movzx   ebx, [rsp+130h+SystemTime.wSecond]
0x180003227  movzx   edi, [rsp+130h+SystemTime.wMinute]
0x18000322c  movzx   esi, [rsp+130h+SystemTime.wHour]
0x180003231  call    cs:__imp_GetCurrentThreadId
0x180003237  mov     [rsp+130h+var_100], ebx
0x18000323b  lea     r8, a03d02u02u02u; "[%03d] %02u:%02u:%02u: "
0x180003242  mov     r9d, eax
0x180003245  mov     [rsp+130h+var_108], edi
0x180003249  mov     edx, 70h ; 'p'; cbDest
0x18000324e  mov     [rsp+130h+var_110], esi
0x180003252  lea     rcx, [rbp+30h+pszDest]; pszDest
0x180003256  call    StringCbPrintfA
0x18000325b  jmp     short loc_1800032A6
0x18000325d  movzx   ebx, [rsp+130h+SystemTime.wMilliseconds]
0x180003262  movzx   edi, [rsp+130h+SystemTime.wSecond]
0x180003267  movzx   esi, [rsp+130h+SystemTime.wMinute]
0x18000326c  movzx   r14d, [rsp+130h+SystemTime.wHour]
0x180003272  call    cs:__imp_GetCurrentThreadId
0x180003278  mov     dword ptr [rsp+130h+var_F8], ebx
0x18000327c  lea     r8, a03d02u02u02u03; "[%03d] %02u:%02u:%02u:%03u: "
0x180003283  mov     [rsp+130h+var_100], edi
0x180003287  lea     rcx, [rbp+30h+pszDest]; pszDest
0x18000328b  mov     r9d, eax
0x18000328e  mov     [rsp+130h+var_108], esi
0x180003292  mov     edx, 70h ; 'p'; cbDest
0x180003297  mov     [rsp+130h+var_110], r14d; int
0x18000329c  call    StringCbPrintfA
0x1800032a1  mov     r14, qword ptr [rsp+130h+var_C0]
0x1800032a6  mov     rdi, [rsp+130h+var_E0]
0x1800032ab  mov     rsi, [rsp+130h+var_D8]
0x1800032b0  test    eax, eax
0x1800032b2  js      loc_180003427
0x1800032b8  test    r14, r14
0x1800032bb  jz      short loc_1800032D6
0x1800032bd  mov     r8, r14; pszSrc
0x1800032c0  lea     rcx, [rbp+30h+pszDest]; pszDest
0x1800032c4  mov     edx, 70h ; 'p'; cchDest
0x1800032c9  call    StringCchCatA
0x1800032ce  test    eax, eax
0x1800032d0  js      loc_180003427
0x1800032d6  mov     r14d, [rbp+30h+dwGroupSize]
0x1800032da  xor     ebx, ebx
0x1800032dc  lea     edx, [r14-1]
0x1800032e0  mov     eax, edx
0x1800032e2  test    r12, rax
0x1800032e5  jz      short loc_18000335E
0x1800032e7  mov     ecx, r12d
0x1800032ea  mov     ebx, 10h
0x1800032ef  and     ecx, edx
0x1800032f1  xorps   xmm0, xmm0
0x1800032f4  cmp     ecx, r15d
0x1800032f7  mov     rdx, r12; Src
0x1800032fa  movups  xmmword ptr [rsp+130h+var_C0], xmm0
0x1800032ff  cmova   ecx, r15d
0x180003303  mov     dword ptr [rsp+130h+var_E0], ecx
0x180003307  sub     ebx, ecx
0x180003309  mov     r8d, ecx; Size
0x18000330c  lea     rcx, [rsp+130h+var_C0]
0x180003311  add     rcx, rbx; void *
0x180003314  call    memcpy_0
0x180003319  lea     rcx, [rbp+30h+pszDest]; int
0x18000331d  mov     rax, r12
0x180003320  mov     [rsp+130h+pszSrc], rcx; pszSrc
0x180003325  lea     r9, [rsp+130h+var_C0]; int
0x18000332a  sub     rax, rbx
0x18000332d  mov     r8d, r13d; int
0x180003330  mov     [rsp+130h+var_F8], rax; __int64
0x180003335  mov     rdx, rsi; int
0x180003338  mov     eax, [rbp+30h+bAddressPrefix]
0x18000333b  mov     [rsp+130h+var_100], eax; int
0x18000333f  mov     [rsp+130h+var_108], r14d; int
0x180003344  call    TraceDumpLineA
0x180003349  mov     ebx, eax
0x18000334b  mov     eax, dword ptr [rsp+130h+var_E0]
0x18000334f  cmp     r15d, eax
0x180003352  jb      loc_180003427
0x180003358  add     r12, rax
0x18000335b  sub     r15d, eax
0x18000335e  test    r15d, r15d
0x180003361  jz      loc_1800033E7
0x180003367  cmp     r15d, 10h
0x18000336b  jb      short loc_1800033A3
0x18000336d  lea     rax, [rbp+30h+pszDest]
0x180003371  mov     r9, r12; int
0x180003374  mov     [rsp+130h+pszSrc], rax; pszSrc
0x180003379  mov     r8d, r13d; int
0x18000337c  mov     eax, [rbp+30h+bAddressPrefix]
0x18000337f  mov     rdx, rsi; int
0x180003382  mov     [rsp+130h+var_F8], r12; __int64
0x180003387  mov     [rsp+130h+var_100], eax; int
0x18000338b  mov     [rsp+130h+var_108], r14d; int
0x180003390  call    TraceDumpLineA
0x180003395  add     ebx, eax
0x180003397  add     r12, 10h
0x18000339b  add     r15d, 0FFFFFFF0h
0x18000339f  jnz     short loc_180003367
0x1800033a1  jmp     short loc_1800033E7
0x1800033a3  xorps   xmm0, xmm0
0x1800033a6  mov     r8d, r15d; Size
0x1800033a9  mov     rdx, r12; Src
0x1800033ac  lea     rcx, [rsp+130h+var_C0]; void *
0x1800033b1  movups  xmmword ptr [rsp+130h+var_C0], xmm0
0x1800033b6  call    memcpy_0
0x1800033bb  lea     rax, [rbp+30h+pszDest]
0x1800033bf  mov     r8d, r13d; int
0x1800033c2  mov     [rsp+130h+pszSrc], rax; pszSrc
0x1800033c7  lea     r9, [rsp+130h+var_C0]; int
0x1800033cc  mov     eax, [rbp+30h+bAddressPrefix]
0x1800033cf  mov     rdx, rsi; int
0x1800033d2  mov     [rsp+130h+var_F8], r12; __int64
0x1800033d7  mov     [rsp+130h+var_100], eax; int
0x1800033db  mov     [rsp+130h+var_108], r14d; int
0x1800033e0  call    TraceDumpLineA
0x1800033e5  add     ebx, eax
0x1800033e7  mov     rcx, rsi
0x1800033ea  call    ReleaseReadLock
0x1800033ef  mov     rcx, rdi
0x1800033f2  call    ReleaseReadLock
0x1800033f7  mov     eax, ebx
0x1800033f9  mov     rsi, [rsp+130h+arg_8]
0x180003401  mov     rdi, [rsp+130h+var_30]
0x180003409  mov     rcx, [rbp+30h+var_40]
0x18000340d  xor     rcx, rsp; StackCookie
0x180003410  call    __security_check_cookie
0x180003415  add     rsp, 108h
0x18000341c  pop     r15
0x18000341e  pop     r14
0x180003420  pop     r13
0x180003422  pop     r12
0x180003424  pop     rbx
0x180003425  pop     rbp
0x180003426  retn
0x180003427  mov     rcx, rsi
0x18000342a  call    ReleaseReadLock
0x18000342f  mov     rcx, rdi
0x180003432  call    ReleaseReadLock
0x180003437  xor     eax, eax
0x180003439  jmp     short loc_1800033F9
0x18000343b  mov     eax, 3EBh
0x180003440  jmp     short loc_1800033F9
0x180003442  mov     eax, 57h ; 'W'
0x180003447  jmp     short loc_180003409
```
