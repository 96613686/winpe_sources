# TracePutsExA(x,x,x)

- ea: `0x100062d0`
- end: `0x10006581`
- name: `_TracePutsExA@12`
- size: `689`
- prototype: `DWORD __stdcall(DWORD dwTraceID, DWORD dwFlags, LPCSTR lpszString)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x10002160`
- `0x10003c20`
- `0x10005d00`
- `0x100062d0`
- `0x100077c0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1000652c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1000652c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x100063d3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x100063d3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x100063cc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x10006525`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x100063cc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x10006525`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x10006456`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x10006477`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x100064b7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x100064d8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x10006456`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x10006477`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x100064b7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x100064d8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10006367`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100063a3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10006367`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100063a3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10006357`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10006396`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10006357`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10006396`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x10006388`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x100063bd`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x100063ee`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x10006401`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x10006540`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x10006553`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x10006388`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x100063bd`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x100063ee`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x10006401`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x10006540`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x10006553`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x10006424`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x10006424`

## pseudocode

```c
DWORD __stdcall TracePutsExA(DWORD dwTraceID, DWORD dwFlags, LPCSTR lpszString)
{
  DWORD v3; // edi
  LPCRITICAL_SECTION v4; // esi
  int v5; // eax
  bool v6; // zf
  int v7; // edi
  DWORD result; // eax
  HANDLE ProcessHeap; // eax
  DWORD v10; // eax
  HRESULT v11; // eax
  DWORD v12; // eax
  DWORD CurrentThreadId; // eax
  DWORD v14; // eax
  int v15; // ecx
  HANDLE v16; // eax
  int wMonth; // [esp-1Ch] [ebp-54h]
  int v18; // [esp-18h] [ebp-50h]
  int wDay; // [esp-18h] [ebp-50h]
  int v20; // [esp-14h] [ebp-4Ch]
  int wHour; // [esp-14h] [ebp-4Ch]
  int v22; // [esp-10h] [ebp-48h]
  int wMinute; // [esp-10h] [ebp-48h]
  int v24; // [esp-Ch] [ebp-44h]
  int wSecond; // [esp-Ch] [ebp-44h]
  int v26; // [esp-8h] [ebp-40h]
  int wMilliseconds; // [esp-8h] [ebp-40h]
  struct _RTL_CRITICAL_SECTION *v28; // [esp-4h] [ebp-3Ch]
  DWORD v30; // [esp+Ch] [ebp-2Ch]
  LPCRITICAL_SECTION v31; // [esp+10h] [ebp-28h]
  volatile signed __int32 *v32; // [esp+14h] [ebp-24h]
  HRESULT v33; // [esp+18h] [ebp-20h]
  char *pszDest; // [esp+1Ch] [ebp-1Ch]
  LPCSTR v35; // [esp+20h] [ebp-18h]
  struct _SYSTEMTIME SystemTime; // [esp+24h] [ebp-14h] BYREF

  v35 = lpszString;
  v30 = 0;
  if ( !dwTraceID || dwTraceID == -1 )
    return 87;
  v3 = dwTraceID ^ 0xDCBA0000;
  if ( (dwTraceID ^ 0xDCBA0000) >= 0x3C )
    return 0;
  if ( !lpszString )
    return 0;
  v4 = g_server;
  v31 = g_server;
  if ( !g_server )
    return 0;
  if ( !g_server[2].LockCount )
    return 1003;
  if ( !g_serverThread )
    TraceCreateServerThread(0);
  v5 = *(&v4[2].SpinCount + v3);
  if ( (dwFlags & 2) != 0 )
    v6 = (dwFlags & v5 & 0xFFFF0000) == 0;
  else
    v6 = v5 == 0;
  if ( v6 )
    return 0;
  v28 = v4;
  _mm_lfence();
  EnterCriticalSection(v28);
  v32 = (volatile signed __int32 *)&v4[1];
  _InterlockedIncrement((volatile signed __int32 *)&v4[1]);
  LeaveCriticalSection(v4);
  v7 = *(&v4[12].SpinCount + v3);
  if ( !v7 )
    goto LABEL_14;
  EnterCriticalSection((LPCRITICAL_SECTION)v7);
  _InterlockedIncrement((volatile signed __int32 *)(v7 + 24));
  LeaveCriticalSection((LPCRITICAL_SECTION)v7);
  if ( (*(_BYTE *)(v7 + 32) & 1) != 0 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v7 + 24), 0xFFFFFFFF) < 0 )
      SetEvent(*(HANDLE *)(v7 + 28));
LABEL_14:
    if ( _InterlockedDecrement(v32) < 0 )
      SetEvent((HANDLE)v4[1].LockCount);
    return 0;
  }
  ProcessHeap = GetProcessHeap();
  pszDest = (char *)HeapAlloc(ProcessHeap, 0, 0x1388u);
  if ( !pszDest )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v7 + 24), 0xFFFFFFFF) < 0 )
      SetEvent(*(HANDLE *)(v7 + 28));
    if ( _InterlockedDecrement(v32) < 0 )
      SetEvent((HANDLE)v4[1].LockCount);
    return 8;
  }
  if ( (dwFlags & 1) == 0 )
  {
    GetLocalTime(&SystemTime);
    if ( (dwFlags & 4) != 0 )
    {
      wMilliseconds = SystemTime.wMilliseconds;
      wSecond = SystemTime.wSecond;
      wMinute = SystemTime.wMinute;
      wHour = SystemTime.wHour;
      if ( (dwFlags & 8) != 0 )
      {
        wDay = SystemTime.wDay;
        wMonth = SystemTime.wMonth;
        CurrentThreadId = GetCurrentThreadId();
        v11 = StringCchPrintfA(
                pszDest,
                0x1388u,
                "\r\n[%03d] %02u-%02u %02u:%02u:%02u:%03u: %s",
                CurrentThreadId,
                wMonth,
                wDay,
                wHour,
                wMinute,
                wSecond,
                wMilliseconds,
                lpszString);
      }
      else
      {
        v14 = GetCurrentThreadId();
        v11 = StringCchPrintfA(
                pszDest,
                0x1388u,
                "\r\n[%03d] %02u:%02u:%02u:%03u: %s",
                v14,
                wHour,
                wMinute,
                wSecond,
                wMilliseconds,
                lpszString);
      }
    }
    else
    {
      v26 = SystemTime.wSecond;
      v24 = SystemTime.wMinute;
      v22 = SystemTime.wHour;
      if ( (dwFlags & 8) == 0 )
      {
        v12 = GetCurrentThreadId();
        v11 = StringCchPrintfA(pszDest, 0x1388u, "\r\n[%03d] %02u:%02u:%02u: %s", v12, v22, v24, v26, lpszString);
        goto LABEL_36;
      }
      v20 = SystemTime.wDay;
      v18 = SystemTime.wMonth;
      v10 = GetCurrentThreadId();
      v11 = StringCchPrintfA(
              pszDest,
              0x1388u,
              "\r\n[%03d] %02u-%02u %02u:%02u:%02u: %s",
              v10,
              v18,
              v20,
              v22,
              v24,
              v26,
              lpszString);
    }
    v4 = v31;
LABEL_36:
    v15 = v11;
    v35 = pszDest;
    v11 = (unsigned __int16)v11;
    if ( v15 >= 0 )
      v11 = 0;
    v33 = v11;
    if ( v11 )
      goto LABEL_40;
    goto LABEL_39;
  }
  v33 = 0;
LABEL_39:
  v30 = TraceWriteOutputA(dwFlags, v35);
LABEL_40:
  v16 = GetProcessHeap();
  HeapFree(v16, 0, pszDest);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v7 + 24), 0xFFFFFFFF) < 0 )
    SetEvent(*(HANDLE *)(v7 + 28));
  if ( _InterlockedDecrement(v32) < 0 )
    SetEvent((HANDLE)v4[1].LockCount);
  result = v30;
  if ( v33 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x100062d0  mov     edi, edi
0x100062d2  push    ebp
0x100062d3  mov     ebp, esp
0x100062d5  sub     esp, 2Ch
0x100062d8  mov     eax, ___security_cookie
0x100062dd  xor     eax, ebp
0x100062df  mov     [ebp+var_4], eax
0x100062e2  mov     eax, [ebp+lpszString]
0x100062e5  xor     ecx, ecx
0x100062e7  push    ebx
0x100062e8  push    esi
0x100062e9  push    edi
0x100062ea  mov     edi, [ebp+dwTraceID]
0x100062ed  mov     [ebp+var_18], eax
0x100062f0  mov     [ebp+var_2C], ecx
0x100062f3  test    edi, edi
0x100062f5  jz      loc_1000656D
0x100062fb  or      ebx, 0FFFFFFFFh
0x100062fe  cmp     edi, ebx
0x10006300  jz      loc_1000656D
0x10006306  xor     edi, 0DCBA0000h
0x1000630c  cmp     edi, 3Ch ; '<'
0x1000630f  jnb     short loc_1000638E
0x10006311  test    eax, eax
0x10006313  jz      short loc_1000638E
0x10006315  mov     esi, _g_server
0x1000631b  mov     [ebp+var_28], esi
0x1000631e  test    esi, esi
0x10006320  jz      short loc_1000638E
0x10006322  cmp     [esi+34h], ecx
0x10006325  jz      loc_10006566
0x1000632b  cmp     _g_serverThread, ecx
0x10006331  jnz     short loc_1000633B
0x10006333  push    ecx
0x10006334  xor     edx, edx
0x10006336  call    _TraceCreateServerThread@12; TraceCreateServerThread(x,x,x)
0x1000633b  test    byte ptr [ebp+dwFlags], 2
0x1000633f  mov     eax, [esi+edi*4+44h]
0x10006343  jz      short loc_1000634F
0x10006345  and     eax, [ebp+dwFlags]
0x10006348  test    eax, 0FFFF0000h
0x1000634d  jmp     short loc_10006351
0x1000634f  test    eax, eax
0x10006351  jz      short loc_1000638E
0x10006353  push    esi; lpCriticalSection
0x10006354  lfence
0x10006357  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x1000635d  lea     eax, [esi+18h]
0x10006360  mov     [ebp+var_24], eax
0x10006363  lock inc dword ptr [eax]
0x10006366  push    esi; lpCriticalSection
0x10006367  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1000636d  mov     edi, [esi+edi*4+134h]
0x10006374  mov     [ebp+var_20], edi
0x10006377  test    edi, edi
0x10006379  jnz     short loc_10006395
0x1000637b  mov     eax, [ebp+var_24]
0x1000637e  lock xadd [eax], ebx
0x10006382  dec     ebx
0x10006383  jns     short loc_1000638E
0x10006385  push    dword ptr [esi+1Ch]; hEvent
0x10006388  call    ds:__imp__SetEvent@4; SetEvent(x)
0x1000638e  xor     eax, eax
0x10006390  jmp     loc_10006570
0x10006395  push    edi; lpCriticalSection
0x10006396  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x1000639c  lea     eax, [edi+18h]
0x1000639f  lock inc dword ptr [eax]
0x100063a2  push    edi; lpCriticalSection
0x100063a3  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x100063a9  test    byte ptr [edi+20h], 1
0x100063ad  jz      short loc_100063C5
0x100063af  mov     eax, ebx
0x100063b1  lea     edx, [edi+18h]
0x100063b4  lock xadd [edx], eax
0x100063b8  jns     short loc_1000637B
0x100063ba  push    dword ptr [edi+1Ch]; hEvent
0x100063bd  call    ds:__imp__SetEvent@4; SetEvent(x)
0x100063c3  jmp     short loc_1000637B
0x100063c5  push    1388h; dwBytes
0x100063ca  push    0; dwFlags
0x100063cc  call    ds:__imp__GetProcessHeap@0; GetProcessHeap()
0x100063d2  push    eax; hHeap
0x100063d3  call    ds:__imp__HeapAlloc@12; HeapAlloc(x,x,x)
0x100063d9  mov     [ebp+pszDest], eax
0x100063dc  test    eax, eax
0x100063de  jnz     short loc_1000640E
0x100063e0  mov     eax, ebx
0x100063e2  lea     edx, [edi+18h]
0x100063e5  lock xadd [edx], eax
0x100063e9  jns     short loc_100063F4
0x100063eb  push    dword ptr [edi+1Ch]; hEvent
0x100063ee  call    ds:__imp__SetEvent@4; SetEvent(x)
0x100063f4  mov     eax, [ebp+var_24]
0x100063f7  lock xadd [eax], ebx
0x100063fb  dec     ebx
0x100063fc  jns     short loc_10006407
0x100063fe  push    dword ptr [esi+1Ch]; hEvent
0x10006401  call    ds:__imp__SetEvent@4; SetEvent(x)
0x10006407  push    8
0x10006409  jmp     loc_1000656F
0x1000640e  test    byte ptr [ebp+dwFlags], 1
0x10006412  jz      short loc_10006420
0x10006414  mov     [ebp+var_20], 0
0x1000641b  jmp     loc_10006510
0x10006420  lea     eax, [ebp+SystemTime]
0x10006423  push    eax; lpSystemTime
0x10006424  call    ds:__imp__GetLocalTime@4; GetLocalTime(x)
0x1000642a  mov     eax, [ebp+dwFlags]
0x1000642d  push    [ebp+var_18]
0x10006430  and     eax, 8
0x10006433  test    byte ptr [ebp+dwFlags], 4
0x10006437  jnz     short loc_10006495
0x10006439  movzx   ecx, [ebp+SystemTime.wMinute]
0x1000643d  test    eax, eax
0x1000643f  movzx   eax, [ebp+SystemTime.wSecond]
0x10006443  movzx   edx, [ebp+SystemTime.wHour]
0x10006447  push    eax
0x10006448  push    ecx
0x10006449  push    edx
0x1000644a  jz      short loc_10006477
0x1000644c  movzx   esi, [ebp+SystemTime.wDay]
0x10006450  movzx   edi, [ebp+SystemTime.wMonth]
0x10006454  push    esi
0x10006455  push    edi
0x10006456  call    ds:__imp__GetCurrentThreadId@0; GetCurrentThreadId()
0x1000645c  push    eax
0x1000645d  push    offset a03d02u02u02u02_2; "\r\n[%03d] %02u-%02u %02u:%02u:%02u: %s"
0x10006462  push    1388h; cchDest
0x10006467  push    [ebp+pszDest]; pszDest
0x1000646a  call    _StringCchPrintfA
0x1000646f  add     esp, 28h
0x10006472  mov     edi, [ebp+var_20]
0x10006475  jmp     short loc_100064F4
0x10006477  call    ds:__imp__GetCurrentThreadId@0; GetCurrentThreadId()
0x1000647d  push    eax
0x1000647e  push    offset a03d02u02u02uS_0; "\r\n[%03d] %02u:%02u:%02u: %s"
0x10006483  push    1388h; cchDest
0x10006488  push    [ebp+pszDest]; pszDest
0x1000648b  call    _StringCchPrintfA
0x10006490  add     esp, 20h
0x10006493  jmp     short loc_100064F7
0x10006495  movzx   ecx, [ebp+SystemTime.wSecond]
0x10006499  test    eax, eax
0x1000649b  movzx   eax, [ebp+SystemTime.wMilliseconds]
0x1000649f  movzx   edx, [ebp+SystemTime.wMinute]
0x100064a3  movzx   esi, [ebp+SystemTime.wHour]
0x100064a7  push    eax
0x100064a8  push    ecx
0x100064a9  push    edx
0x100064aa  push    esi
0x100064ab  jz      short loc_100064D8
0x100064ad  movzx   edi, [ebp+SystemTime.wDay]
0x100064b1  movzx   ebx, [ebp+SystemTime.wMonth]
0x100064b5  push    edi
0x100064b6  push    ebx
0x100064b7  call    ds:__imp__GetCurrentThreadId@0; GetCurrentThreadId()
0x100064bd  push    eax
0x100064be  push    offset a03d02u02u02u02_1; "\r\n[%03d] %02u-%02u %02u:%02u:%02u:%03"...
0x100064c3  push    1388h; cchDest
0x100064c8  push    [ebp+pszDest]; pszDest
0x100064cb  call    _StringCchPrintfA
0x100064d0  add     esp, 2Ch
0x100064d3  or      ebx, 0FFFFFFFFh
0x100064d6  jmp     short loc_10006472
0x100064d8  call    ds:__imp__GetCurrentThreadId@0; GetCurrentThreadId()
0x100064de  push    eax
0x100064df  push    offset a03d02u02u02u03_1; "\r\n[%03d] %02u:%02u:%02u:%03u: %s"
0x100064e4  push    1388h; cchDest
0x100064e9  push    [ebp+pszDest]; pszDest
0x100064ec  call    _StringCchPrintfA
0x100064f1  add     esp, 24h
0x100064f4  mov     esi, [ebp+var_28]
0x100064f7  mov     ecx, eax
0x100064f9  xor     edx, edx
0x100064fb  mov     eax, [ebp+pszDest]
0x100064fe  test    ecx, ecx
0x10006500  mov     [ebp+var_18], eax
0x10006503  movzx   eax, cx
0x10006506  cmovns  eax, edx
0x10006509  mov     [ebp+var_20], eax
0x1000650c  test    eax, eax
0x1000650e  jnz     short loc_10006520
0x10006510  push    [ebp+var_18]
0x10006513  mov     edx, edi
0x10006515  push    [ebp+dwFlags]
0x10006518  call    _TraceWriteOutputA@16; TraceWriteOutputA(x,x,x,x)
0x1000651d  mov     [ebp+var_2C], eax
0x10006520  push    [ebp+pszDest]; lpMem
0x10006523  push    0; dwFlags
0x10006525  call    ds:__imp__GetProcessHeap@0; GetProcessHeap()
0x1000652b  push    eax; hHeap
0x1000652c  call    ds:__imp__HeapFree@12; HeapFree(x,x,x)
0x10006532  mov     ecx, ebx
0x10006534  lea     edx, [edi+18h]
0x10006537  lock xadd [edx], ecx
0x1000653b  jns     short loc_10006546
0x1000653d  push    dword ptr [edi+1Ch]; hEvent
0x10006540  call    ds:__imp__SetEvent@4; SetEvent(x)
0x10006546  mov     eax, [ebp+var_24]
0x10006549  lock xadd [eax], ebx
0x1000654d  dec     ebx
0x1000654e  jns     short loc_10006559
0x10006550  push    dword ptr [esi+1Ch]; hEvent
0x10006553  call    ds:__imp__SetEvent@4; SetEvent(x)
0x10006559  mov     eax, [ebp+var_2C]
0x1000655c  xor     ecx, ecx
0x1000655e  cmp     [ebp+var_20], ecx
0x10006561  cmovnz  eax, ecx
0x10006564  jmp     short loc_10006570
0x10006566  mov     eax, 3EBh
0x1000656b  jmp     short loc_10006570
0x1000656d  push    57h ; 'W'
0x1000656f  pop     eax
0x10006570  mov     ecx, [ebp+var_4]
0x10006573  pop     edi
0x10006574  pop     esi
0x10006575  xor     ecx, ebp; StackCookie
0x10006577  pop     ebx
0x10006578  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1000657d  leave
0x1000657e  retn    0Ch
```
