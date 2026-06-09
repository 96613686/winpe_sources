# TraceDumpExA(x,x,x,x,x,x,x)

- ea: `0x10005dd0`
- end: `0x1000616c`
- name: `_TraceDumpExA@28`
- size: `924`
- prototype: `DWORD __stdcall(DWORD dwTraceID, DWORD dwFlags, LPBYTE lpbBytes, DWORD dwByteCount, DWORD dwGroupSize, BOOL bAddressPrefix, LPCSTR lpszPrefix)`
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x10002160`
- `0x100022c4`
- `0x10002c90`
- `0x10003c20`
- `0x10004567`
- `0x100050c5`
- `0x10005d00`
- `0x10005dd0`
- `0x10007174`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x10005f34`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x10005f5e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x10005f34`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x10005f5e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10005ec0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10005ee9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10005ec0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10005ee9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10005eb3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10005edc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10005eb3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10005edc`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x10005fb0`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x10005fc3`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x10006130`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x10006143`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x10005fb0`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x10005fc3`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x10006130`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x10006143`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x10005f10`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x10005f10`

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
  DWORD v7; // edi
  LPCRITICAL_SECTION v8; // esi
  int v9; // eax
  bool v10; // zf
  int v11; // edi
  DWORD v12; // eax
  HRESULT v13; // eax
  DWORD CurrentThreadId; // eax
  DWORD v16; // eax
  const void *v17; // edx
  char *v18; // ecx
  size_t v19; // ecx
  int v20; // eax
  DWORD v21; // eax
  int v22; // ecx
  int v23; // eax
  int wHour; // [esp-10h] [ebp-C8h]
  int v25; // [esp-Ch] [ebp-C4h]
  int wMinute; // [esp-Ch] [ebp-C4h]
  int v27; // [esp-8h] [ebp-C0h]
  int wSecond; // [esp-8h] [ebp-C0h]
  struct _RTL_CRITICAL_SECTION *v29; // [esp-4h] [ebp-BCh]
  int v30; // [esp-4h] [ebp-BCh]
  int wMilliseconds; // [esp-4h] [ebp-BCh]
  size_t v32; // [esp+0h] [ebp-B8h]
  ULONG v33; // [esp+0h] [ebp-B8h]
  const char *v34; // [esp+4h] [ebp-B4h]
  ULONG *v35; // [esp+4h] [ebp-B4h]
  int v36; // [esp+Ch] [ebp-ACh]
  LPCRITICAL_SECTION v37; // [esp+10h] [ebp-A8h]
  ULONG ulMinuend; // [esp+14h] [ebp-A4h] BYREF
  STRSAFE_LPSTR v39; // [esp+18h] [ebp-A0h]
  void *Src; // [esp+1Ch] [ebp-9Ch]
  DWORD v41; // [esp+20h] [ebp-98h]
  struct _SYSTEMTIME SystemTime; // [esp+24h] [ebp-94h] BYREF
  char pszDest[112]; // [esp+34h] [ebp-84h] BYREF
  int v44; // [esp+A4h] [ebp-14h] BYREF
  int v45; // [esp+A8h] [ebp-10h]
  int v46; // [esp+ACh] [ebp-Ch]
  int v47; // [esp+B0h] [ebp-8h]
  int v48; // [esp+B4h] [ebp-4h] BYREF
  DWORD dwByteCounta; // [esp+CCh] [ebp+14h]

  v39 = (STRSAFE_LPSTR)lpszPrefix;
  Src = lpbBytes;
  memset(pszDest, 0, sizeof(pszDest));
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
      v13 = StringCchPrintfA(
              pszDest,
              0x70u,
              "[%03d] %02u:%02u:%02u:%03u: ",
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
      v13 = StringCchPrintfA(pszDest, 0x70u, "[%03d] %02u:%02u:%02u: ", v12, v25, v27, v30);
    }
    if ( v13 < 0 )
      goto LABEL_26;
  }
  if ( v39 && StringCchCatA(v39, v32, v34) < 0 )
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
  v17 = Src;
  v18 = (char *)((unsigned int)Src & (dwGroupSize - 1));
  if ( v18 )
  {
    if ( (unsigned int)v18 > dwByteCount )
      v18 = (char *)dwByteCount;
    v44 = 0;
    v39 = v18;
    v45 = 0;
    v46 = 0;
    v47 = 0;
    memcpy((void *)((char *)&v48 - v18), Src, (size_t)v18);
    v11 = v36;
    Src = (char *)Src + (_DWORD)v39;
    v41 = TraceDumpLineA(dwFlags, &v44, pszDest, dwGroupSize, bAddressPrefix, (char *)Src - 16, pszDest);
    if ( ULongSub((ULONG)&ulMinuend, v33, v35) < 0 )
      goto LABEL_26;
    v19 = ulMinuend;
    v17 = Src;
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
      ulMinuend = (ULONG)v17 + 16;
      v8 = v37;
      if ( v19 < 0x10 )
        break;
      dwByteCounta = v19 - 16;
      v20 = TraceDumpLineA(dwFlags, v17, pszDest, v16, bAddressPrefix, v17, pszDest);
      v41 += v20;
      v19 = dwByteCounta;
      v17 = (const void *)ulMinuend;
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
    v23 = TraceDumpLineA(dwFlags, &v44, v22, dwGroupSize, bAddressPrefix, Src, pszDest);
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
0x10005dd0  mov     edi, edi
0x10005dd2  push    ebp
0x10005dd3  mov     ebp, esp
0x10005dd5  sub     esp, 0ACh
0x10005ddb  mov     eax, ___security_cookie
0x10005de0  xor     eax, ebp
0x10005de2  mov     [ebp+var_4], eax
0x10005de5  mov     eax, [ebp+lpszPrefix]
0x10005de8  push    ebx
0x10005de9  push    esi; pulResult
0x10005dea  mov     esi, [ebp+lpbBytes]
0x10005ded  push    edi; ulSubtrahend
0x10005dee  mov     edi, [ebp+dwTraceID]
0x10005df1  push    6Fh ; 'o'; Size
0x10005df3  mov     [ebp+var_A0], eax
0x10005df9  lea     eax, [ebp+var_83]
0x10005dff  push    0; Val
0x10005e01  push    eax; void *
0x10005e02  mov     [ebp+Src], esi
0x10005e08  mov     [ebp+pszDest], 0
0x10005e0f  call    _memset
0x10005e14  add     esp, 0Ch
0x10005e17  test    edi, edi
0x10005e19  jz      loc_10006158
0x10005e1f  or      ebx, 0FFFFFFFFh
0x10005e22  cmp     edi, ebx
0x10005e24  jz      loc_10006158
0x10005e2a  xor     edi, 0DCBA0000h
0x10005e30  cmp     edi, 3Ch ; '<'
0x10005e33  jnb     loc_10006158
0x10005e39  test    esi, esi
0x10005e3b  jz      loc_10006158
0x10005e41  cmp     [ebp+dwByteCount], 0
0x10005e45  jz      loc_10006158
0x10005e4b  mov     eax, [ebp+dwGroupSize]
0x10005e4e  cmp     eax, 1
0x10005e51  jz      short loc_10005E61
0x10005e53  cmp     eax, 2
0x10005e56  jz      short loc_10005E61
0x10005e58  cmp     eax, 4
0x10005e5b  jnz     loc_10006158
0x10005e61  mov     esi, _g_server
0x10005e67  mov     [ebp+var_A8], esi
0x10005e6d  test    esi, esi
0x10005e6f  jz      loc_10005FC9
0x10005e75  cmp     dword ptr [esi+34h], 0
0x10005e79  jz      loc_10006151
0x10005e7f  cmp     _g_serverThread, 0
0x10005e86  jnz     short loc_10005E93
0x10005e88  push    0
0x10005e8a  xor     edx, edx
0x10005e8c  xor     ecx, ecx
0x10005e8e  call    _TraceCreateServerThread@12; TraceCreateServerThread(x,x,x)
0x10005e93  test    byte ptr [ebp+dwFlags], 2
0x10005e97  mov     eax, [esi+edi*4+44h]
0x10005e9b  jz      short loc_10005EA7
0x10005e9d  and     eax, [ebp+dwFlags]
0x10005ea0  test    eax, 0FFFF0000h
0x10005ea5  jmp     short loc_10005EA9
0x10005ea7  test    eax, eax
0x10005ea9  jz      loc_10005FC9
0x10005eaf  push    esi; lpCriticalSection
0x10005eb0  lfence
0x10005eb3  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x10005eb9  lea     eax, [esi+18h]
0x10005ebc  lock inc dword ptr [eax]
0x10005ebf  push    esi; lpCriticalSection
0x10005ec0  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10005ec6  mov     edi, [esi+edi*4+134h]
0x10005ecd  mov     [ebp+var_AC], edi
0x10005ed3  test    edi, edi
0x10005ed5  jz      loc_10005FB6
0x10005edb  push    edi; lpCriticalSection
0x10005edc  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x10005ee2  lea     eax, [edi+18h]
0x10005ee5  lock inc dword ptr [eax]
0x10005ee8  push    edi; lpCriticalSection
0x10005ee9  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10005eef  test    byte ptr [edi+20h], 1
0x10005ef3  jnz     loc_10005FA2
0x10005ef9  test    byte ptr [ebp+dwFlags], 1
0x10005efd  mov     [ebp+var_98], 0
0x10005f07  jnz     short loc_10005F85
0x10005f09  lea     eax, [ebp+SystemTime]
0x10005f0f  push    eax; lpSystemTime
0x10005f10  call    ds:__imp__GetLocalTime@4; GetLocalTime(x)
0x10005f16  test    byte ptr [ebp+dwFlags], 4
0x10005f1a  movzx   edx, [ebp+SystemTime.wSecond]
0x10005f21  movzx   ecx, [ebp+SystemTime.wMinute]
0x10005f28  movzx   eax, [ebp+SystemTime.wHour]
0x10005f2f  jnz     short loc_10005F53
0x10005f31  push    edx
0x10005f32  push    ecx
0x10005f33  push    eax
0x10005f34  call    ds:__imp__GetCurrentThreadId@0; GetCurrentThreadId()
0x10005f3a  push    eax
0x10005f3b  push    offset a03d02u02u02u; "[%03d] %02u:%02u:%02u: "
0x10005f40  lea     eax, [ebp+pszDest]
0x10005f46  push    70h ; 'p'; cchDest
0x10005f48  push    eax; pszDest
0x10005f49  call    _StringCchPrintfA
0x10005f4e  add     esp, 1Ch
0x10005f51  jmp     short loc_10005F81
0x10005f53  movzx   esi, [ebp+SystemTime.wMilliseconds]
0x10005f5a  push    esi
0x10005f5b  push    edx
0x10005f5c  push    ecx
0x10005f5d  push    eax
0x10005f5e  call    ds:__imp__GetCurrentThreadId@0; GetCurrentThreadId()
0x10005f64  push    eax
0x10005f65  push    offset a03d02u02u02u03; "[%03d] %02u:%02u:%02u:%03u: "
0x10005f6a  lea     eax, [ebp+pszDest]
0x10005f70  push    70h ; 'p'; cchDest
0x10005f72  push    eax; pszDest
0x10005f73  call    _StringCchPrintfA
0x10005f78  mov     esi, [ebp+var_A8]
0x10005f7e  add     esp, 20h
0x10005f81  test    eax, eax
0x10005f83  js      short loc_10005FA2
0x10005f85  mov     eax, [ebp+var_A0]
0x10005f8b  test    eax, eax
0x10005f8d  jz      short loc_10005FD0
0x10005f8f  push    eax; pszDest
0x10005f90  push    70h ; 'p'
0x10005f92  pop     edx
0x10005f93  lea     ecx, [ebp+pszDest]
0x10005f99  call    _StringCchCatA@12; StringCchCatA(x,x,x)
0x10005f9e  test    eax, eax
0x10005fa0  jns     short loc_10005FD0
0x10005fa2  lea     ecx, [edi+18h]
0x10005fa5  mov     eax, ebx
0x10005fa7  lock xadd [ecx], eax
0x10005fab  jns     short loc_10005FB6
0x10005fad  push    dword ptr [edi+1Ch]; hEvent
0x10005fb0  call    ds:__imp__SetEvent@4; SetEvent(x)
0x10005fb6  lea     eax, [esi+18h]
0x10005fb9  lock xadd [eax], ebx
0x10005fbd  dec     ebx
0x10005fbe  jns     short loc_10005FC9
0x10005fc0  push    dword ptr [esi+1Ch]; hEvent
0x10005fc3  call    ds:__imp__SetEvent@4; SetEvent(x)
0x10005fc9  xor     eax, eax
0x10005fcb  jmp     loc_1000615B
0x10005fd0  mov     eax, [ebp+dwGroupSize]
0x10005fd3  mov     edx, [ebp+Src]
0x10005fd9  lea     ecx, [eax-1]
0x10005fdc  and     ecx, edx
0x10005fde  jz      loc_10006076
0x10005fe4  cmp     ecx, [ebp+dwByteCount]
0x10005fe7  lea     edi, [ebp+var_14]
0x10005fea  cmova   ecx, [ebp+dwByteCount]
0x10005fee  xor     eax, eax
0x10005ff0  stosd
0x10005ff1  push    ecx; Size
0x10005ff2  push    edx; Src
0x10005ff3  mov     [ebp+var_A0], ecx
0x10005ff9  stosd
0x10005ffa  stosd
0x10005ffb  stosd
0x10005ffc  lea     eax, [ebp+var_4]
0x10005fff  sub     eax, ecx
0x10006001  push    eax; void *
0x10006002  call    _memcpy
0x10006007  mov     eax, [ebp+Src]
0x1000600d  lea     ecx, [ebp+pszDest]
0x10006013  add     eax, [ebp+var_A0]
0x10006019  add     esp, 0Ch
0x1000601c  mov     edi, [ebp+var_AC]
0x10006022  mov     edx, edi
0x10006024  mov     [ebp+Src], eax
0x1000602a  add     eax, 0FFFFFFF0h
0x1000602d  push    ecx
0x1000602e  push    eax
0x1000602f  push    [ebp+bAddressPrefix]
0x10006032  lea     eax, [ebp+var_14]
0x10006035  push    [ebp+dwGroupSize]
0x10006038  push    ecx
0x10006039  push    eax
0x1000603a  push    [ebp+dwFlags]
0x1000603d  call    _TraceDumpLineA@36; TraceDumpLineA(x,x,x,x,x,x,x,x,x)
0x10006042  mov     ecx, [ebp+dwByteCount]
0x10006045  mov     edx, [ebp+var_A0]
0x1000604b  mov     [ebp+var_98], eax
0x10006051  lea     eax, [ebp+ulMinuend]
0x10006057  push    eax; ulMinuend
0x10006058  call    _ULongSub@12; ULongSub(x,x,x)
0x1000605d  test    eax, eax
0x1000605f  js      loc_10005FA2
0x10006065  mov     ecx, [ebp+ulMinuend]
0x1000606b  mov     edx, [ebp+Src]
0x10006071  mov     eax, [ebp+dwGroupSize]
0x10006074  jmp     short loc_10006079
0x10006076  mov     ecx, [ebp+dwByteCount]
0x10006079  test    ecx, ecx
0x1000607b  jz      loc_10006122
0x10006081  lea     esi, [edx+10h]
0x10006084  mov     [ebp+ulMinuend], esi
0x1000608a  mov     esi, [ebp+var_A8]
0x10006090  cmp     ecx, 10h
0x10006093  jb      short loc_100060D7
0x10006095  sub     ecx, 10h
0x10006098  mov     [ebp+dwByteCount], ecx
0x1000609b  lea     ecx, [ebp+pszDest]
0x100060a1  push    ecx
0x100060a2  push    edx
0x100060a3  push    [ebp+bAddressPrefix]
0x100060a6  push    eax
0x100060a7  push    ecx
0x100060a8  push    edx
0x100060a9  push    [ebp+dwFlags]
0x100060ac  mov     edx, edi
0x100060ae  call    _TraceDumpLineA@36; TraceDumpLineA(x,x,x,x,x,x,x,x,x)
0x100060b3  add     [ebp+var_98], eax
0x100060b9  mov     ecx, [ebp+dwByteCount]
0x100060bc  mov     edx, [ebp+ulMinuend]
0x100060c2  mov     eax, [ebp+dwGroupSize]
0x100060c5  mov     [ebp+Src], edx
0x100060cb  test    ecx, ecx
0x100060cd  jnz     short loc_10006081
0x100060cf  mov     eax, [ebp+var_98]
0x100060d5  jmp     short loc_1000611C
0x100060d7  xor     eax, eax
0x100060d9  lea     edi, [ebp+var_14]
0x100060dc  stosd
0x100060dd  push    ecx; Size
0x100060de  push    edx; Src
0x100060df  stosd
0x100060e0  stosd
0x100060e1  stosd
0x100060e2  lea     eax, [ebp+var_14]
0x100060e5  push    eax; void *
0x100060e6  call    _memcpy
0x100060eb  mov     edi, [ebp+var_AC]
0x100060f1  lea     eax, [ebp+pszDest]
0x100060f7  add     esp, 0Ch
0x100060fa  mov     edx, edi
0x100060fc  push    eax
0x100060fd  push    [ebp+Src]
0x10006103  lea     eax, [ebp+var_14]
0x10006106  push    [ebp+bAddressPrefix]
0x10006109  push    [ebp+dwGroupSize]
0x1000610c  push    ecx
0x1000610d  push    eax
0x1000610e  push    [ebp+dwFlags]
0x10006111  call    _TraceDumpLineA@36; TraceDumpLineA(x,x,x,x,x,x,x,x,x)
0x10006116  add     eax, [ebp+var_98]
0x1000611c  mov     [ebp+var_98], eax
0x10006122  mov     eax, ebx
0x10006124  lea     ecx, [edi+18h]
0x10006127  lock xadd [ecx], eax
0x1000612b  jns     short loc_10006136
0x1000612d  push    dword ptr [edi+1Ch]; hEvent
0x10006130  call    ds:__imp__SetEvent@4; SetEvent(x)
0x10006136  lea     eax, [esi+18h]
0x10006139  lock xadd [eax], ebx
0x1000613d  dec     ebx
0x1000613e  jns     short loc_10006149
0x10006140  push    dword ptr [esi+1Ch]; hEvent
0x10006143  call    ds:__imp__SetEvent@4; SetEvent(x)
0x10006149  mov     eax, [ebp+var_98]
0x1000614f  jmp     short loc_1000615B
0x10006151  mov     eax, 3EBh
0x10006156  jmp     short loc_1000615B
0x10006158  push    57h ; 'W'
0x1000615a  pop     eax
0x1000615b  mov     ecx, [ebp+var_4]
0x1000615e  pop     edi
0x1000615f  pop     esi
0x10006160  xor     ecx, ebp; StackCookie
0x10006162  pop     ebx
0x10006163  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10006168  leave
0x10006169  retn    1Ch
```
