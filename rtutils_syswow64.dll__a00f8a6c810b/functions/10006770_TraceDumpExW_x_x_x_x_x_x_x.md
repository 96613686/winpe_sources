# TraceDumpExW(x,x,x,x,x,x,x)

- ea: `0x10006770`
- end: `0x10006b10`
- name: `_TraceDumpExW@28`
- size: `928`
- prototype: `DWORD __stdcall(DWORD dwTraceID, DWORD dwFlags, LPBYTE lpbBytes, DWORD dwByteCount, DWORD dwGroupSize, BOOL bAddressPrefix, LPCWSTR lpszPrefix)`
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x10002160`
- `0x100022c4`
- `0x100036b5`
- `0x10003c20`
- `0x10004567`
- `0x100050c5`
- `0x10006636`
- `0x10006770`
- `0x10007bcc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x100068d8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x10006902`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x100068d8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x10006902`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10006864`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1000688d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10006864`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1000688d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10006857`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10006880`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10006857`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10006880`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x10006954`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x10006967`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x10006ad4`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x10006ae7`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x10006954`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x10006967`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x10006ad4`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x10006ae7`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x100068b4`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x100068b4`

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
  DWORD v7; // edi
  LPCRITICAL_SECTION v8; // esi
  int v9; // eax
  bool v10; // zf
  int v11; // edi
  DWORD v12; // eax
  HRESULT v13; // eax
  DWORD CurrentThreadId; // eax
  DWORD v16; // eax
  wchar_t *v17; // edx
  wchar_t *v18; // ecx
  size_t v19; // ecx
  int v20; // eax
  DWORD v21; // eax
  int v22; // ecx
  int v23; // eax
  int wHour; // [esp-10h] [ebp-138h]
  int v25; // [esp-Ch] [ebp-134h]
  int wMinute; // [esp-Ch] [ebp-134h]
  int v27; // [esp-8h] [ebp-130h]
  int wSecond; // [esp-8h] [ebp-130h]
  struct _RTL_CRITICAL_SECTION *v29; // [esp-4h] [ebp-12Ch]
  int v30; // [esp-4h] [ebp-12Ch]
  int wMilliseconds; // [esp-4h] [ebp-12Ch]
  size_t v32; // [esp+0h] [ebp-128h]
  ULONG v33; // [esp+0h] [ebp-128h]
  const wchar_t *v34; // [esp+4h] [ebp-124h]
  ULONG *v35; // [esp+4h] [ebp-124h]
  int v36; // [esp+Ch] [ebp-11Ch]
  LPCRITICAL_SECTION v37; // [esp+10h] [ebp-118h]
  ULONG ulMinuend; // [esp+14h] [ebp-114h] BYREF
  STRSAFE_LPWSTR v39; // [esp+18h] [ebp-110h]
  void *Src; // [esp+1Ch] [ebp-10Ch]
  DWORD v41; // [esp+20h] [ebp-108h]
  struct _SYSTEMTIME SystemTime; // [esp+24h] [ebp-104h] BYREF
  wchar_t pszDest[112]; // [esp+34h] [ebp-F4h] BYREF
  int v44; // [esp+114h] [ebp-14h] BYREF
  int v45; // [esp+118h] [ebp-10h]
  int v46; // [esp+11Ch] [ebp-Ch]
  int v47; // [esp+120h] [ebp-8h]
  int v48; // [esp+124h] [ebp-4h] BYREF
  DWORD dwByteCounta; // [esp+13Ch] [ebp+14h]

  v39 = (STRSAFE_LPWSTR)lpszPrefix;
  memset(pszDest, 0, sizeof(pszDest));
  Src = lpbBytes;
  if ( !dwTraceID )
    return 87;
  if ( dwTraceID == -1 )
    return 87;
  v7 = dwTraceID ^ 0xDCBA0000;
  if ( (dwTraceID ^ 0xDCBA0000) >= 0x3C
    || !lpbBytes
    || !dwByteCount
    || dwGroupSize != 1 && dwGroupSize != 2 && dwGroupSize != 4 )
  {
    return 87;
  }
  v8 = g_server;
  v37 = g_server;
  if ( !g_server )
    return 0;
  if ( !g_server[2].LockCount )
    return 1003;
  if ( !g_serverThread )
    TraceCreateServerThread(0);
  v9 = *(&v8[2].SpinCount + v7);
  if ( (dwFlags & 2) != 0 )
    v10 = (dwFlags & v9 & 0xFFFF0000) == 0;
  else
    v10 = v9 == 0;
  if ( v10 )
    return 0;
  v29 = v8;
  _mm_lfence();
  EnterCriticalSection(v29);
  _InterlockedIncrement((volatile signed __int32 *)&v8[1]);
  LeaveCriticalSection(v8);
  v11 = *(&v8[12].SpinCount + v7);
  v36 = v11;
  if ( !v11 )
    goto LABEL_28;
  EnterCriticalSection((LPCRITICAL_SECTION)v11);
  _InterlockedIncrement((volatile signed __int32 *)(v11 + 24));
  LeaveCriticalSection((LPCRITICAL_SECTION)v11);
  if ( (*(_BYTE *)(v11 + 32) & 1) != 0 )
    goto LABEL_26;
  v41 = 0;
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
      v13 = StringCchPrintfW(
              pszDest,
              0x70u,
              L"[%03d] %02u:%02u:%02u:%03u: ",
              CurrentThreadId,
              wHour,
              wMinute,
              wSecond,
              wMilliseconds);
      v8 = v37;
    }
    else
    {
      v30 = SystemTime.wSecond;
      v27 = SystemTime.wMinute;
      v25 = SystemTime.wHour;
      v12 = GetCurrentThreadId();
      v13 = StringCchPrintfW(pszDest, 0x70u, L"[%03d] %02u:%02u:%02u: ", v12, v25, v27, v30);
    }
    if ( v13 < 0 )
      goto LABEL_26;
  }
  if ( v39 && StringCchCatW(v39, v32, v34) < 0 )
  {
LABEL_26:
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v11 + 24), 0xFFFFFFFF) < 0 )
      SetEvent(*(HANDLE *)(v11 + 28));
LABEL_28:
    if ( _InterlockedDecrement((volatile signed __int32 *)&v8[1]) < 0 )
      SetEvent((HANDLE)v8[1].LockCount);
    return 0;
  }
  v16 = dwGroupSize;
  v17 = (wchar_t *)Src;
  v18 = (wchar_t *)((unsigned int)Src & (dwGroupSize - 1));
  if ( v18 )
  {
    if ( (unsigned int)v18 > dwByteCount )
      v18 = (wchar_t *)dwByteCount;
    v44 = 0;
    v39 = v18;
    v45 = 0;
    v46 = 0;
    v47 = 0;
    memcpy((void *)((char *)&v48 - (char *)v18), Src, (size_t)v18);
    v11 = v36;
    Src = (char *)Src + (_DWORD)v39;
    v41 = TraceDumpLineW(
            (int)pszDest,
            v36,
            dwFlags,
            (wchar_t *)&v44,
            (int)pszDest,
            dwGroupSize,
            bAddressPrefix,
            (unsigned int)Src - 16,
            pszDest);
    if ( ULongSub((ULONG)&ulMinuend, v33, v35) < 0 )
      goto LABEL_26;
    v19 = ulMinuend;
    v17 = (wchar_t *)Src;
    v16 = dwGroupSize;
  }
  else
  {
    v19 = dwByteCount;
  }
  if ( v19 )
  {
    while ( 1 )
    {
      ulMinuend = (ULONG)(v17 + 8);
      v8 = v37;
      if ( v19 < 0x10 )
        break;
      dwByteCounta = v19 - 16;
      v20 = TraceDumpLineW(
              (int)pszDest,
              v11,
              dwFlags,
              v17,
              (int)pszDest,
              v16,
              bAddressPrefix,
              (unsigned int)v17,
              pszDest);
      v41 += v20;
      v19 = dwByteCounta;
      v17 = (wchar_t *)ulMinuend;
      v16 = dwGroupSize;
      Src = (void *)ulMinuend;
      if ( !dwByteCounta )
      {
        v21 = v41;
        goto LABEL_42;
      }
    }
    v44 = 0;
    v45 = 0;
    v46 = 0;
    v47 = 0;
    memcpy(&v44, v17, v19);
    v11 = v36;
    v23 = TraceDumpLineW(
            v22,
            v36,
            dwFlags,
            (wchar_t *)&v44,
            v22,
            dwGroupSize,
            bAddressPrefix,
            (unsigned int)Src,
            pszDest);
    v21 = v41 + v23;
LABEL_42:
    v41 = v21;
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v11 + 24), 0xFFFFFFFF) < 0 )
    SetEvent(*(HANDLE *)(v11 + 28));
  if ( _InterlockedDecrement((volatile signed __int32 *)&v8[1]) < 0 )
    SetEvent((HANDLE)v8[1].LockCount);
  return v41;
}

```

## disassembly

```asm
0x10006770  mov     edi, edi
0x10006772  push    ebp
0x10006773  mov     ebp, esp
0x10006775  sub     esp, 11Ch
0x1000677b  mov     eax, ___security_cookie
0x10006780  xor     eax, ebp
0x10006782  mov     [ebp+var_4], eax
0x10006785  mov     eax, [ebp+lpszPrefix]
0x10006788  push    ebx
0x10006789  push    esi; pulResult
0x1000678a  mov     esi, [ebp+lpbBytes]
0x1000678d  push    edi; ulSubtrahend
0x1000678e  mov     edi, [ebp+dwTraceID]
0x10006791  mov     [ebp+var_110], eax
0x10006797  xor     eax, eax
0x10006799  push    0DEh; Size
0x1000679e  push    eax; Val
0x1000679f  mov     [ebp+pszDest], ax
0x100067a6  lea     eax, [ebp+var_F2]
0x100067ac  push    eax; void *
0x100067ad  mov     [ebp+Src], esi
0x100067b3  call    _memset
0x100067b8  add     esp, 0Ch
0x100067bb  test    edi, edi
0x100067bd  jz      loc_10006AFC
0x100067c3  or      ebx, 0FFFFFFFFh
0x100067c6  cmp     edi, ebx
0x100067c8  jz      loc_10006AFC
0x100067ce  xor     edi, 0DCBA0000h
0x100067d4  cmp     edi, 3Ch ; '<'
0x100067d7  jnb     loc_10006AFC
0x100067dd  test    esi, esi
0x100067df  jz      loc_10006AFC
0x100067e5  cmp     [ebp+dwByteCount], 0
0x100067e9  jz      loc_10006AFC
0x100067ef  mov     eax, [ebp+dwGroupSize]
0x100067f2  cmp     eax, 1
0x100067f5  jz      short loc_10006805
0x100067f7  cmp     eax, 2
0x100067fa  jz      short loc_10006805
0x100067fc  cmp     eax, 4
0x100067ff  jnz     loc_10006AFC
0x10006805  mov     esi, _g_server
0x1000680b  mov     [ebp+var_118], esi
0x10006811  test    esi, esi
0x10006813  jz      loc_1000696D
0x10006819  cmp     dword ptr [esi+34h], 0
0x1000681d  jz      loc_10006AF5
0x10006823  cmp     _g_serverThread, 0
0x1000682a  jnz     short loc_10006837
0x1000682c  push    0
0x1000682e  xor     edx, edx
0x10006830  xor     ecx, ecx
0x10006832  call    _TraceCreateServerThread@12; TraceCreateServerThread(x,x,x)
0x10006837  test    byte ptr [ebp+dwFlags], 2
0x1000683b  mov     eax, [esi+edi*4+44h]
0x1000683f  jz      short loc_1000684B
0x10006841  and     eax, [ebp+dwFlags]
0x10006844  test    eax, 0FFFF0000h
0x10006849  jmp     short loc_1000684D
0x1000684b  test    eax, eax
0x1000684d  jz      loc_1000696D
0x10006853  push    esi; lpCriticalSection
0x10006854  lfence
0x10006857  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x1000685d  lea     eax, [esi+18h]
0x10006860  lock inc dword ptr [eax]
0x10006863  push    esi; lpCriticalSection
0x10006864  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1000686a  mov     edi, [esi+edi*4+134h]
0x10006871  mov     [ebp+var_11C], edi
0x10006877  test    edi, edi
0x10006879  jz      loc_1000695A
0x1000687f  push    edi; lpCriticalSection
0x10006880  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x10006886  lea     eax, [edi+18h]
0x10006889  lock inc dword ptr [eax]
0x1000688c  push    edi; lpCriticalSection
0x1000688d  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10006893  test    byte ptr [edi+20h], 1
0x10006897  jnz     loc_10006946
0x1000689d  test    byte ptr [ebp+dwFlags], 1
0x100068a1  mov     [ebp+var_108], 0
0x100068ab  jnz     short loc_10006929
0x100068ad  lea     eax, [ebp+SystemTime]
0x100068b3  push    eax; lpSystemTime
0x100068b4  call    ds:__imp__GetLocalTime@4; GetLocalTime(x)
0x100068ba  test    byte ptr [ebp+dwFlags], 4
0x100068be  movzx   edx, [ebp+SystemTime.wSecond]
0x100068c5  movzx   ecx, [ebp+SystemTime.wMinute]
0x100068cc  movzx   eax, [ebp+SystemTime.wHour]
0x100068d3  jnz     short loc_100068F7
0x100068d5  push    edx
0x100068d6  push    ecx
0x100068d7  push    eax
0x100068d8  call    ds:__imp__GetCurrentThreadId@0; GetCurrentThreadId()
0x100068de  push    eax
0x100068df  push    offset a03d02u02u02u_0; "[%03d] %02u:%02u:%02u: "
0x100068e4  lea     eax, [ebp+pszDest]
0x100068ea  push    70h ; 'p'; cchDest
0x100068ec  push    eax; pszDest
0x100068ed  call    _StringCchPrintfW
0x100068f2  add     esp, 1Ch
0x100068f5  jmp     short loc_10006925
0x100068f7  movzx   esi, [ebp+SystemTime.wMilliseconds]
0x100068fe  push    esi
0x100068ff  push    edx
0x10006900  push    ecx
0x10006901  push    eax
0x10006902  call    ds:__imp__GetCurrentThreadId@0; GetCurrentThreadId()
0x10006908  push    eax
0x10006909  push    offset a03d02u02u02u03_0; "[%03d] %02u:%02u:%02u:%03u: "
0x1000690e  lea     eax, [ebp+pszDest]
0x10006914  push    70h ; 'p'; cchDest
0x10006916  push    eax; pszDest
0x10006917  call    _StringCchPrintfW
0x1000691c  mov     esi, [ebp+var_118]
0x10006922  add     esp, 20h
0x10006925  test    eax, eax
0x10006927  js      short loc_10006946
0x10006929  mov     eax, [ebp+var_110]
0x1000692f  test    eax, eax
0x10006931  jz      short loc_10006974
0x10006933  push    eax; pszDest
0x10006934  push    70h ; 'p'
0x10006936  pop     edx
0x10006937  lea     ecx, [ebp+pszDest]
0x1000693d  call    _StringCchCatW@12; StringCchCatW(x,x,x)
0x10006942  test    eax, eax
0x10006944  jns     short loc_10006974
0x10006946  lea     ecx, [edi+18h]
0x10006949  mov     eax, ebx
0x1000694b  lock xadd [ecx], eax
0x1000694f  jns     short loc_1000695A
0x10006951  push    dword ptr [edi+1Ch]; hEvent
0x10006954  call    ds:__imp__SetEvent@4; SetEvent(x)
0x1000695a  lea     eax, [esi+18h]
0x1000695d  lock xadd [eax], ebx
0x10006961  dec     ebx
0x10006962  jns     short loc_1000696D
0x10006964  push    dword ptr [esi+1Ch]; hEvent
0x10006967  call    ds:__imp__SetEvent@4; SetEvent(x)
0x1000696d  xor     eax, eax
0x1000696f  jmp     loc_10006AFF
0x10006974  mov     eax, [ebp+dwGroupSize]
0x10006977  mov     edx, [ebp+Src]
0x1000697d  lea     ecx, [eax-1]
0x10006980  and     ecx, edx
0x10006982  jz      loc_10006A1A
0x10006988  cmp     ecx, [ebp+dwByteCount]
0x1000698b  lea     edi, [ebp+var_14]
0x1000698e  cmova   ecx, [ebp+dwByteCount]
0x10006992  xor     eax, eax
0x10006994  stosd
0x10006995  push    ecx; Size
0x10006996  push    edx; Src
0x10006997  mov     [ebp+var_110], ecx
0x1000699d  stosd
0x1000699e  stosd
0x1000699f  stosd
0x100069a0  lea     eax, [ebp+var_4]
0x100069a3  sub     eax, ecx
0x100069a5  push    eax; void *
0x100069a6  call    _memcpy
0x100069ab  mov     eax, [ebp+Src]
0x100069b1  lea     ecx, [ebp+pszDest]
0x100069b7  add     eax, [ebp+var_110]
0x100069bd  add     esp, 0Ch
0x100069c0  mov     edi, [ebp+var_11C]
0x100069c6  mov     edx, edi
0x100069c8  mov     [ebp+Src], eax
0x100069ce  add     eax, 0FFFFFFF0h
0x100069d1  push    ecx
0x100069d2  push    eax
0x100069d3  push    [ebp+bAddressPrefix]
0x100069d6  lea     eax, [ebp+var_14]
0x100069d9  push    [ebp+dwGroupSize]
0x100069dc  push    ecx
0x100069dd  push    eax
0x100069de  push    [ebp+dwFlags]
0x100069e1  call    _TraceDumpLineW@36; TraceDumpLineW(x,x,x,x,x,x,x,x,x)
0x100069e6  mov     ecx, [ebp+dwByteCount]
0x100069e9  mov     edx, [ebp+var_110]
0x100069ef  mov     [ebp+var_108], eax
0x100069f5  lea     eax, [ebp+ulMinuend]
0x100069fb  push    eax; ulMinuend
0x100069fc  call    _ULongSub@12; ULongSub(x,x,x)
0x10006a01  test    eax, eax
0x10006a03  js      loc_10006946
0x10006a09  mov     ecx, [ebp+ulMinuend]
0x10006a0f  mov     edx, [ebp+Src]
0x10006a15  mov     eax, [ebp+dwGroupSize]
0x10006a18  jmp     short loc_10006A1D
0x10006a1a  mov     ecx, [ebp+dwByteCount]
0x10006a1d  test    ecx, ecx
0x10006a1f  jz      loc_10006AC6
0x10006a25  lea     esi, [edx+10h]
0x10006a28  mov     [ebp+ulMinuend], esi
0x10006a2e  mov     esi, [ebp+var_118]
0x10006a34  cmp     ecx, 10h
0x10006a37  jb      short loc_10006A7B
0x10006a39  sub     ecx, 10h
0x10006a3c  mov     [ebp+dwByteCount], ecx
0x10006a3f  lea     ecx, [ebp+pszDest]
0x10006a45  push    ecx
0x10006a46  push    edx
0x10006a47  push    [ebp+bAddressPrefix]
0x10006a4a  push    eax
0x10006a4b  push    ecx
0x10006a4c  push    edx
0x10006a4d  push    [ebp+dwFlags]
0x10006a50  mov     edx, edi
0x10006a52  call    _TraceDumpLineW@36; TraceDumpLineW(x,x,x,x,x,x,x,x,x)
0x10006a57  add     [ebp+var_108], eax
0x10006a5d  mov     ecx, [ebp+dwByteCount]
0x10006a60  mov     edx, [ebp+ulMinuend]
0x10006a66  mov     eax, [ebp+dwGroupSize]
0x10006a69  mov     [ebp+Src], edx
0x10006a6f  test    ecx, ecx
0x10006a71  jnz     short loc_10006A25
0x10006a73  mov     eax, [ebp+var_108]
0x10006a79  jmp     short loc_10006AC0
0x10006a7b  xor     eax, eax
0x10006a7d  lea     edi, [ebp+var_14]
0x10006a80  stosd
0x10006a81  push    ecx; Size
0x10006a82  push    edx; Src
0x10006a83  stosd
0x10006a84  stosd
0x10006a85  stosd
0x10006a86  lea     eax, [ebp+var_14]
0x10006a89  push    eax; void *
0x10006a8a  call    _memcpy
0x10006a8f  mov     edi, [ebp+var_11C]
0x10006a95  lea     eax, [ebp+pszDest]
0x10006a9b  add     esp, 0Ch
0x10006a9e  mov     edx, edi
0x10006aa0  push    eax
0x10006aa1  push    [ebp+Src]
0x10006aa7  lea     eax, [ebp+var_14]
0x10006aaa  push    [ebp+bAddressPrefix]
0x10006aad  push    [ebp+dwGroupSize]
0x10006ab0  push    ecx
0x10006ab1  push    eax
0x10006ab2  push    [ebp+dwFlags]
0x10006ab5  call    _TraceDumpLineW@36; TraceDumpLineW(x,x,x,x,x,x,x,x,x)
0x10006aba  add     eax, [ebp+var_108]
0x10006ac0  mov     [ebp+var_108], eax
0x10006ac6  mov     eax, ebx
0x10006ac8  lea     ecx, [edi+18h]
0x10006acb  lock xadd [ecx], eax
0x10006acf  jns     short loc_10006ADA
0x10006ad1  push    dword ptr [edi+1Ch]; hEvent
0x10006ad4  call    ds:__imp__SetEvent@4; SetEvent(x)
0x10006ada  lea     eax, [esi+18h]
0x10006add  lock xadd [eax], ebx
0x10006ae1  dec     ebx
0x10006ae2  jns     short loc_10006AED
0x10006ae4  push    dword ptr [esi+1Ch]; hEvent
0x10006ae7  call    ds:__imp__SetEvent@4; SetEvent(x)
0x10006aed  mov     eax, [ebp+var_108]
0x10006af3  jmp     short loc_10006AFF
0x10006af5  mov     eax, 3EBh
0x10006afa  jmp     short loc_10006AFF
0x10006afc  push    57h ; 'W'
0x10006afe  pop     eax
0x10006aff  mov     ecx, [ebp+var_4]
0x10006b02  pop     edi
0x10006b03  pop     esi
0x10006b04  xor     ecx, ebp; StackCookie
0x10006b06  pop     ebx
0x10006b07  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10006b0c  leave
0x10006b0d  retn    1Ch
```
