# TraceDumpExW

- ea: `0x180004cc0`
- end: `0x18000502b`
- name: `TraceDumpExW`
- size: `875`
- prototype: `DWORD __stdcall(DWORD dwTraceID, DWORD dwFlags, LPBYTE lpbBytes, DWORD dwByteCount, DWORD dwGroupSize, BOOL bAddressPrefix, LPCWSTR lpszPrefix)`
- caller_count: `0`
- callee_count: `10`
- tags: ``

## callees

- `0x180001c20`
- `0x180003bb0`
- `0x180004456`
- `0x180004a2c`
- `0x180004afc`
- `0x180004cc0`
- `0x1800070c4`
- `0x180009694`
- `0x180009810`
- `0x18000a769`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004e1b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004e5c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004e1b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004e5c`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180004e00`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180004e00`

## pseudocode

```c
DWORD __stdcall TraceDumpExW(
        DWORD dwTraceID,
        DWORD dwFlags,
        LPBYTE lpbBytes,
        DWORD dwByteCount,
        DWORD dwGroupSize,
        BOOL bAddressPrefix,
        LPCWSTR lpszPrefix)
{
  DWORD v8; // edi
  __int64 v11; // rbx
  DWORD v12; // esi
  LPCRITICAL_SECTION v13; // r15
  int v14; // eax
  bool v15; // zf
  __int64 v16; // r14
  int v18; // ecx
  int v19; // esi
  DWORD v20; // eax
  HRESULT v21; // eax
  int wHour; // r14d
  DWORD CurrentThreadId; // eax
  DWORD v24; // edx
  DWORD v25; // ebx
  unsigned int v26; // ecx
  __int64 v27; // rbx
  int v28; // ecx
  int v29; // [rsp+20h] [rbp-E0h]
  DWORD v31; // [rsp+50h] [rbp-B0h]
  __int64 v32; // [rsp+58h] [rbp-A8h]
  struct _SYSTEMTIME SystemTime; // [rsp+60h] [rbp-A0h] BYREF
  STRSAFE_LPCWSTR pszSrc[2]; // [rsp+70h] [rbp-90h] BYREF
  wchar_t pszDest; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v36[222]; // [rsp+82h] [rbp-7Eh] BYREF

  pszSrc[0] = lpszPrefix;
  v8 = dwFlags;
  pszDest = 0;
  SystemTime = 0;
  memset_0(v36, 0, sizeof(v36));
  if ( dwTraceID - 1 > 0xFFFFFFFD )
    return 87;
  v11 = dwTraceID ^ 0xDCBA0000;
  if ( (unsigned int)v11 >= 0x3C )
    return 87;
  if ( !lpbBytes )
    return 87;
  if ( !dwByteCount )
    return 87;
  v12 = dwGroupSize;
  if ( ((dwGroupSize - 1) & 0xFFFFFFFC) != 0 || dwGroupSize == 3 )
    return 87;
  v13 = g_server;
  if ( !g_server )
    return 0;
  if ( !g_server[2].DebugInfo )
    return 1003;
  if ( !g_serverThread )
    TraceCreateServerThread(0, 0, 0);
  v14 = *((_DWORD *)&v13[2].SpinCount + v11);
  if ( (v8 & 2) != 0 )
    v15 = (v8 & v14 & 0xFFFF0000) == 0;
  else
    v15 = v14 == 0;
  if ( v15 )
    return 0;
  _mm_lfence();
  AcquireReadLock(v13);
  v16 = *(&v13[8].SpinCount + v11);
  v32 = v16;
  if ( !v16 )
    goto LABEL_16;
  AcquireReadLock(v16);
  if ( (*(_BYTE *)(v16 + 56) & 1) != 0 )
    goto LABEL_38;
  if ( (v8 & 1) == 0 )
  {
    GetLocalTime(&SystemTime);
    if ( (v8 & 4) != 0 )
    {
      wHour = SystemTime.wHour;
      CurrentThreadId = GetCurrentThreadId();
      v29 = wHour;
      v21 = StringCchPrintfW(&pszDest, 0x70u, L"[%03d] %02u:%02u:%02u:%03u: ", CurrentThreadId);
      v16 = v32;
    }
    else
    {
      v19 = SystemTime.wHour;
      v20 = GetCurrentThreadId();
      v29 = v19;
      v21 = StringCchPrintfW(&pszDest, 0x70u, L"[%03d] %02u:%02u:%02u: ", v20);
    }
    if ( v21 < 0 )
      goto LABEL_38;
    v8 = dwFlags;
    v12 = dwGroupSize;
  }
  if ( pszSrc[0] && StringCchCatW(&pszDest, 0x70u, pszSrc[0]) < 0 )
  {
LABEL_38:
    ReleaseReadLock(v16);
LABEL_16:
    ReleaseReadLock(v13);
    return 0;
  }
  v24 = v12 - 1;
  v25 = 0;
  if ( ((v12 - 1) & (unsigned int)lpbBytes) != 0 )
  {
    v26 = v24 & (unsigned int)lpbBytes;
    *(_OWORD *)pszSrc = 0;
    if ( (v24 & (unsigned int)lpbBytes) > dwByteCount )
      v26 = dwByteCount;
    v31 = v26;
    v27 = 16 - v26;
    memcpy_0((char *)pszSrc + v27, lpbBytes, v26);
    v25 = TraceDumpLineW(
            (int)&pszDest,
            v16,
            v8,
            (int)pszSrc,
            v29,
            v12,
            bAddressPrefix,
            (__int64)&lpbBytes[-v27],
            &pszDest);
    if ( dwByteCount >= v31 )
    {
      lpbBytes += v31;
      dwByteCount -= v31;
      goto LABEL_32;
    }
    goto LABEL_38;
  }
LABEL_32:
  if ( dwByteCount )
  {
    while ( dwByteCount >= 0x10 )
    {
      v25 += TraceDumpLineW(v18, v16, v8, (int)lpbBytes, v29, v12, bAddressPrefix, (__int64)lpbBytes, &pszDest);
      lpbBytes += 16;
      dwByteCount -= 16;
      if ( !dwByteCount )
        goto LABEL_37;
    }
    *(_OWORD *)pszSrc = 0;
    memcpy_0(pszSrc, lpbBytes, dwByteCount);
    v25 += TraceDumpLineW(v28, v16, v8, (int)pszSrc, v29, v12, bAddressPrefix, (__int64)lpbBytes, &pszDest);
  }
LABEL_37:
  ReleaseReadLock(v16);
  ReleaseReadLock(v13);
  return v25;
}

```

## disassembly

```asm
0x180004cc0  mov     [rsp-8+arg_8], rbx
0x180004cc5  push    rbp
0x180004cc6  push    rsi
0x180004cc7  push    rdi
0x180004cc8  push    r12
0x180004cca  push    r13
0x180004ccc  push    r14
0x180004cce  push    r15
0x180004cd0  lea     rbp, [rsp-70h]
0x180004cd5  sub     rsp, 170h
0x180004cdc  mov     rax, cs:__security_cookie
0x180004ce3  xor     rax, rsp
0x180004ce6  mov     [rbp+0A0h+var_40], rax
0x180004cea  mov     rax, [rbp+0A0h+lpszPrefix]
0x180004cf1  mov     r12, r8
0x180004cf4  mov     [rsp+1A0h+pszSrc], rax
0x180004cf9  mov     edi, edx
0x180004cfb  xor     eax, eax
0x180004cfd  mov     [rsp+1A0h+var_150], edx
0x180004d01  mov     ebx, ecx
0x180004d03  mov     [rbp+0A0h+pszDest], ax
0x180004d07  xorps   xmm0, xmm0
0x180004d0a  lea     rcx, [rbp+0A0h+var_11E]; void *
0x180004d0e  xor     edx, edx; Val
0x180004d10  mov     r8d, 0DEh; Size
0x180004d16  mov     r13d, r9d
0x180004d19  movups  xmmword ptr [rsp+1A0h+SystemTime.wYear], xmm0
0x180004d1e  call    memset_0
0x180004d23  lea     eax, [rbx-1]
0x180004d26  cmp     eax, 0FFFFFFFDh
0x180004d29  ja      loc_180004FFF
0x180004d2f  xor     ebx, 0DCBA0000h
0x180004d35  cmp     ebx, 3Ch ; '<'
0x180004d38  jnb     loc_180004FFF
0x180004d3e  test    r12, r12
0x180004d41  jz      loc_180004FFF
0x180004d47  test    r13d, r13d
0x180004d4a  jz      loc_180004FFF
0x180004d50  mov     esi, [rbp+0A0h+dwGroupSize]
0x180004d56  lea     eax, [rsi-1]
0x180004d59  test    eax, 0FFFFFFFCh
0x180004d5e  jnz     loc_180004FFF
0x180004d64  cmp     esi, 3
0x180004d67  jz      loc_180004FFF
0x180004d6d  mov     r15, cs:g_server
0x180004d74  test    r15, r15
0x180004d77  jz      short loc_180004DD7
0x180004d79  cmp     qword ptr [r15+50h], 0
0x180004d7e  jz      loc_180004FF8
0x180004d84  cmp     cs:g_serverThread, 0
0x180004d8c  jnz     short loc_180004D9A
0x180004d8e  xor     r8d, r8d
0x180004d91  xor     edx, edx
0x180004d93  xor     ecx, ecx
0x180004d95  call    TraceCreateServerThread
0x180004d9a  mov     eax, [r15+rbx*4+70h]
0x180004d9f  test    dil, 2
0x180004da3  jz      short loc_180004DAE
0x180004da5  and     eax, edi
0x180004da7  test    eax, 0FFFF0000h
0x180004dac  jmp     short loc_180004DB0
0x180004dae  test    eax, eax
0x180004db0  jz      short loc_180004DD7
0x180004db2  lfence
0x180004db5  mov     rcx, r15
0x180004db8  call    AcquireReadLock
0x180004dbd  mov     r14, [r15+rbx*8+160h]
0x180004dc5  mov     [rsp+1A0h+var_148], r14
0x180004dca  test    r14, r14
0x180004dcd  jnz     short loc_180004DDE
0x180004dcf  mov     rcx, r15
0x180004dd2  call    ReleaseReadLock
0x180004dd7  xor     eax, eax
0x180004dd9  jmp     loc_180005004
0x180004dde  mov     rcx, r14
0x180004de1  call    AcquireReadLock
0x180004de6  test    byte ptr [r14+38h], 1
0x180004deb  jnz     loc_180004FEB
0x180004df1  test    dil, 1
0x180004df5  jnz     loc_180004EA2
0x180004dfb  lea     rcx, [rsp+1A0h+SystemTime]; lpSystemTime
0x180004e00  call    cs:__imp_GetLocalTime
0x180004e06  test    dil, 4
0x180004e0a  jnz     short loc_180004E47
0x180004e0c  movzx   ebx, [rsp+1A0h+SystemTime.wSecond]
0x180004e11  movzx   edi, [rsp+1A0h+SystemTime.wMinute]
0x180004e16  movzx   esi, [rsp+1A0h+SystemTime.wHour]
0x180004e1b  call    cs:__imp_GetCurrentThreadId
0x180004e21  mov     [rsp+1A0h+var_170], ebx
0x180004e25  lea     r8, a03d02u02u02u_0; "[%03d] %02u:%02u:%02u: "
0x180004e2c  mov     r9d, eax
0x180004e2f  mov     [rsp+1A0h+var_178], edi
0x180004e33  mov     edx, 70h ; 'p'; cchDest
0x180004e38  mov     [rsp+1A0h+var_180], esi
0x180004e3c  lea     rcx, [rbp+0A0h+pszDest]; pszDest
0x180004e40  call    StringCchPrintfW
0x180004e45  jmp     short loc_180004E90
0x180004e47  movzx   ebx, [rsp+1A0h+SystemTime.wMilliseconds]
0x180004e4c  movzx   edi, [rsp+1A0h+SystemTime.wSecond]
0x180004e51  movzx   esi, [rsp+1A0h+SystemTime.wMinute]
0x180004e56  movzx   r14d, [rsp+1A0h+SystemTime.wHour]
0x180004e5c  call    cs:__imp_GetCurrentThreadId
0x180004e62  mov     dword ptr [rsp+1A0h+var_168], ebx
0x180004e66  lea     r8, a03d02u02u02u03_0; "[%03d] %02u:%02u:%02u:%03u: "
0x180004e6d  mov     [rsp+1A0h+var_170], edi
0x180004e71  lea     rcx, [rbp+0A0h+pszDest]; pszDest
0x180004e75  mov     r9d, eax
0x180004e78  mov     [rsp+1A0h+var_178], esi
0x180004e7c  mov     edx, 70h ; 'p'; cchDest
0x180004e81  mov     [rsp+1A0h+var_180], r14d; int
0x180004e86  call    StringCchPrintfW
0x180004e8b  mov     r14, [rsp+1A0h+var_148]
0x180004e90  test    eax, eax
0x180004e92  js      loc_180004FEB
0x180004e98  mov     edi, [rsp+1A0h+var_150]
0x180004e9c  mov     esi, [rbp+0A0h+dwGroupSize]
0x180004ea2  mov     rax, [rsp+1A0h+pszSrc]
0x180004ea7  test    rax, rax
0x180004eaa  jz      short loc_180004EC5
0x180004eac  mov     r8, rax; pszSrc
0x180004eaf  lea     rcx, [rbp+0A0h+pszDest]; pszDest
0x180004eb3  mov     edx, 70h ; 'p'; cchDest
0x180004eb8  call    StringCchCatW
0x180004ebd  test    eax, eax
0x180004ebf  js      loc_180004FEB
0x180004ec5  lea     edx, [rsi-1]
0x180004ec8  xor     ebx, ebx
0x180004eca  mov     eax, edx
0x180004ecc  test    r12, rax
0x180004ecf  jz      short loc_180004F4A
0x180004ed1  mov     ecx, r12d
0x180004ed4  mov     ebx, 10h
0x180004ed9  and     ecx, edx
0x180004edb  xorps   xmm0, xmm0
0x180004ede  cmp     ecx, r13d
0x180004ee1  mov     rdx, r12; Src
0x180004ee4  movups  xmmword ptr [rsp+1A0h+pszSrc], xmm0
0x180004ee9  cmova   ecx, r13d
0x180004eed  mov     [rsp+1A0h+var_150], ecx
0x180004ef1  sub     ebx, ecx
0x180004ef3  mov     r8d, ecx; Size
0x180004ef6  lea     rcx, [rsp+1A0h+pszSrc]
0x180004efb  add     rcx, rbx; void *
0x180004efe  call    memcpy_0
0x180004f03  lea     rcx, [rbp+0A0h+pszDest]; int
0x180004f07  mov     rax, r12
0x180004f0a  mov     [rsp+1A0h+var_160], rcx; pszSrc
0x180004f0f  lea     r9, [rsp+1A0h+pszSrc]; int
0x180004f14  sub     rax, rbx
0x180004f17  mov     r8d, edi; int
0x180004f1a  mov     [rsp+1A0h+var_168], rax; __int64
0x180004f1f  mov     rdx, r14; int
0x180004f22  mov     eax, [rbp+0A0h+bAddressPrefix]
0x180004f28  mov     [rsp+1A0h+var_170], eax; int
0x180004f2c  mov     [rsp+1A0h+var_178], esi; int
0x180004f30  call    TraceDumpLineW
0x180004f35  mov     ebx, eax
0x180004f37  mov     eax, [rsp+1A0h+var_150]
0x180004f3b  cmp     r13d, eax
0x180004f3e  jb      loc_180004FEB
0x180004f44  add     r12, rax
0x180004f47  sub     r13d, eax
0x180004f4a  test    r13d, r13d
0x180004f4d  jz      loc_180004FD7
0x180004f53  cmp     r13d, 10h
0x180004f57  jb      short loc_180004F91
0x180004f59  lea     rax, [rbp+0A0h+pszDest]
0x180004f5d  mov     r9, r12; int
0x180004f60  mov     [rsp+1A0h+var_160], rax; pszSrc
0x180004f65  mov     r8d, edi; int
0x180004f68  mov     eax, [rbp+0A0h+bAddressPrefix]
0x180004f6e  mov     rdx, r14; int
0x180004f71  mov     [rsp+1A0h+var_168], r12; __int64
0x180004f76  mov     [rsp+1A0h+var_170], eax; int
0x180004f7a  mov     [rsp+1A0h+var_178], esi; int
0x180004f7e  call    TraceDumpLineW
0x180004f83  add     ebx, eax
0x180004f85  add     r12, 10h
0x180004f89  add     r13d, 0FFFFFFF0h
0x180004f8d  jnz     short loc_180004F53
0x180004f8f  jmp     short loc_180004FD7
0x180004f91  xorps   xmm0, xmm0
0x180004f94  mov     r8d, r13d; Size
0x180004f97  mov     rdx, r12; Src
0x180004f9a  lea     rcx, [rsp+1A0h+pszSrc]; void *
0x180004f9f  movups  xmmword ptr [rsp+1A0h+pszSrc], xmm0
0x180004fa4  call    memcpy_0
0x180004fa9  lea     rax, [rbp+0A0h+pszDest]
0x180004fad  mov     r8d, edi; int
0x180004fb0  mov     [rsp+1A0h+var_160], rax; pszSrc
0x180004fb5  lea     r9, [rsp+1A0h+pszSrc]; int
0x180004fba  mov     eax, [rbp+0A0h+bAddressPrefix]
0x180004fc0  mov     rdx, r14; int
0x180004fc3  mov     [rsp+1A0h+var_168], r12; __int64
0x180004fc8  mov     [rsp+1A0h+var_170], eax; int
0x180004fcc  mov     [rsp+1A0h+var_178], esi; int
0x180004fd0  call    TraceDumpLineW
0x180004fd5  add     ebx, eax
0x180004fd7  mov     rcx, r14
0x180004fda  call    ReleaseReadLock
0x180004fdf  mov     rcx, r15
0x180004fe2  call    ReleaseReadLock
0x180004fe7  mov     eax, ebx
0x180004fe9  jmp     short loc_180005004
0x180004feb  mov     rcx, r14
0x180004fee  call    ReleaseReadLock
0x180004ff3  jmp     loc_180004DCF
0x180004ff8  mov     eax, 3EBh
0x180004ffd  jmp     short loc_180005004
0x180004fff  mov     eax, 57h ; 'W'
0x180005004  mov     rcx, [rbp+0A0h+var_40]
0x180005008  xor     rcx, rsp; StackCookie
0x18000500b  call    __security_check_cookie
0x180005010  mov     rbx, [rsp+1A0h+arg_8]
0x180005018  add     rsp, 170h
0x18000501f  pop     r15
0x180005021  pop     r14
0x180005023  pop     r13
0x180005025  pop     r12
0x180005027  pop     rdi
0x180005028  pop     rsi
0x180005029  pop     rbp
0x18000502a  retn
```
