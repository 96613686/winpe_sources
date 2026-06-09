# TracePutsExW(x,x,x)

- ea: `0x10006b80`
- end: `0x10006e31`
- name: `_TracePutsExW@12`
- size: `689`
- prototype: `DWORD __stdcall(DWORD dwTraceID, DWORD dwFlags, LPCWSTR lpszString)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x10002160`
- `0x10003c20`
- `0x100065eb`
- `0x10006b80`
- `0x100081de`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x10006ddc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x10006ddc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x10006c83`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x10006c83`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x10006c7c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x10006dd5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x10006c7c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x10006dd5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x10006d06`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x10006d27`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x10006d67`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x10006d88`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x10006d06`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x10006d27`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x10006d67`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x10006d88`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10006c17`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10006c53`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10006c17`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10006c53`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10006c07`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10006c46`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10006c07`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10006c46`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x10006c38`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x10006c6d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x10006c9e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x10006cb1`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x10006df0`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x10006e03`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x10006c38`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x10006c6d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x10006c9e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x10006cb1`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x10006df0`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x10006e03`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x10006cd4`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x10006cd4`

## pseudocode

```c
DWORD __stdcall TracePutsExW(DWORD dwTraceID, DWORD dwFlags, LPCWSTR lpszString)
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
  wchar_t *pszDest; // [esp+1Ch] [ebp-1Ch]
  LPCWSTR v35; // [esp+20h] [ebp-18h]
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
  pszDest = (wchar_t *)HeapAlloc(ProcessHeap, 0, 0x1388u);
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
        v11 = StringCbPrintfW(
                pszDest,
                0x1388u,
                L"\r\n[%03d] %02u-%02u %02u:%02u:%02u:%03u: %s",
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
        v11 = StringCbPrintfW(
                pszDest,
                0x1388u,
                L"\r\n[%03d] %02u:%02u:%02u:%03u: %s",
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
        v11 = StringCbPrintfW(pszDest, 0x1388u, L"\r\n[%03d] %02u:%02u:%02u: %s", v12, v22, v24, v26, lpszString);
        goto LABEL_36;
      }
      v20 = SystemTime.wDay;
      v18 = SystemTime.wMonth;
      v10 = GetCurrentThreadId();
      v11 = StringCbPrintfW(
              pszDest,
              0x1388u,
              L"\r\n[%03d] %02u-%02u %02u:%02u:%02u: %s",
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
  v30 = TraceWriteOutputW(dwFlags, v35);
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
0x10006b80  mov     edi, edi
0x10006b82  push    ebp
0x10006b83  mov     ebp, esp
0x10006b85  sub     esp, 2Ch
0x10006b88  mov     eax, ___security_cookie
0x10006b8d  xor     eax, ebp
0x10006b8f  mov     [ebp+var_4], eax
0x10006b92  mov     eax, [ebp+lpszString]
0x10006b95  xor     ecx, ecx
0x10006b97  push    ebx
0x10006b98  push    esi
0x10006b99  push    edi
0x10006b9a  mov     edi, [ebp+dwTraceID]
0x10006b9d  mov     [ebp+var_18], eax
0x10006ba0  mov     [ebp+var_2C], ecx
0x10006ba3  test    edi, edi
0x10006ba5  jz      loc_10006E1D
0x10006bab  or      ebx, 0FFFFFFFFh
0x10006bae  cmp     edi, ebx
0x10006bb0  jz      loc_10006E1D
0x10006bb6  xor     edi, 0DCBA0000h
0x10006bbc  cmp     edi, 3Ch ; '<'
0x10006bbf  jnb     short loc_10006C3E
0x10006bc1  test    eax, eax
0x10006bc3  jz      short loc_10006C3E
0x10006bc5  mov     esi, _g_server
0x10006bcb  mov     [ebp+var_28], esi
0x10006bce  test    esi, esi
0x10006bd0  jz      short loc_10006C3E
0x10006bd2  cmp     [esi+34h], ecx
0x10006bd5  jz      loc_10006E16
0x10006bdb  cmp     _g_serverThread, ecx
0x10006be1  jnz     short loc_10006BEB
0x10006be3  push    ecx
0x10006be4  xor     edx, edx
0x10006be6  call    _TraceCreateServerThread@12; TraceCreateServerThread(x,x,x)
0x10006beb  test    byte ptr [ebp+dwFlags], 2
0x10006bef  mov     eax, [esi+edi*4+44h]
0x10006bf3  jz      short loc_10006BFF
0x10006bf5  and     eax, [ebp+dwFlags]
0x10006bf8  test    eax, 0FFFF0000h
0x10006bfd  jmp     short loc_10006C01
0x10006bff  test    eax, eax
0x10006c01  jz      short loc_10006C3E
0x10006c03  push    esi; lpCriticalSection
0x10006c04  lfence
0x10006c07  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x10006c0d  lea     eax, [esi+18h]
0x10006c10  mov     [ebp+var_24], eax
0x10006c13  lock inc dword ptr [eax]
0x10006c16  push    esi; lpCriticalSection
0x10006c17  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10006c1d  mov     edi, [esi+edi*4+134h]
0x10006c24  mov     [ebp+var_20], edi
0x10006c27  test    edi, edi
0x10006c29  jnz     short loc_10006C45
0x10006c2b  mov     eax, [ebp+var_24]
0x10006c2e  lock xadd [eax], ebx
0x10006c32  dec     ebx
0x10006c33  jns     short loc_10006C3E
0x10006c35  push    dword ptr [esi+1Ch]; hEvent
0x10006c38  call    ds:__imp__SetEvent@4; SetEvent(x)
0x10006c3e  xor     eax, eax
0x10006c40  jmp     loc_10006E20
0x10006c45  push    edi; lpCriticalSection
0x10006c46  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x10006c4c  lea     eax, [edi+18h]
0x10006c4f  lock inc dword ptr [eax]
0x10006c52  push    edi; lpCriticalSection
0x10006c53  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10006c59  test    byte ptr [edi+20h], 1
0x10006c5d  jz      short loc_10006C75
0x10006c5f  mov     eax, ebx
0x10006c61  lea     edx, [edi+18h]
0x10006c64  lock xadd [edx], eax
0x10006c68  jns     short loc_10006C2B
0x10006c6a  push    dword ptr [edi+1Ch]; hEvent
0x10006c6d  call    ds:__imp__SetEvent@4; SetEvent(x)
0x10006c73  jmp     short loc_10006C2B
0x10006c75  push    1388h; dwBytes
0x10006c7a  push    0; dwFlags
0x10006c7c  call    ds:__imp__GetProcessHeap@0; GetProcessHeap()
0x10006c82  push    eax; hHeap
0x10006c83  call    ds:__imp__HeapAlloc@12; HeapAlloc(x,x,x)
0x10006c89  mov     [ebp+pszDest], eax
0x10006c8c  test    eax, eax
0x10006c8e  jnz     short loc_10006CBE
0x10006c90  mov     eax, ebx
0x10006c92  lea     edx, [edi+18h]
0x10006c95  lock xadd [edx], eax
0x10006c99  jns     short loc_10006CA4
0x10006c9b  push    dword ptr [edi+1Ch]; hEvent
0x10006c9e  call    ds:__imp__SetEvent@4; SetEvent(x)
0x10006ca4  mov     eax, [ebp+var_24]
0x10006ca7  lock xadd [eax], ebx
0x10006cab  dec     ebx
0x10006cac  jns     short loc_10006CB7
0x10006cae  push    dword ptr [esi+1Ch]; hEvent
0x10006cb1  call    ds:__imp__SetEvent@4; SetEvent(x)
0x10006cb7  push    8
0x10006cb9  jmp     loc_10006E1F
0x10006cbe  test    byte ptr [ebp+dwFlags], 1
0x10006cc2  jz      short loc_10006CD0
0x10006cc4  mov     [ebp+var_20], 0
0x10006ccb  jmp     loc_10006DC0
0x10006cd0  lea     eax, [ebp+SystemTime]
0x10006cd3  push    eax; lpSystemTime
0x10006cd4  call    ds:__imp__GetLocalTime@4; GetLocalTime(x)
0x10006cda  mov     eax, [ebp+dwFlags]
0x10006cdd  push    [ebp+var_18]
0x10006ce0  and     eax, 8
0x10006ce3  test    byte ptr [ebp+dwFlags], 4
0x10006ce7  jnz     short loc_10006D45
0x10006ce9  movzx   ecx, [ebp+SystemTime.wMinute]
0x10006ced  test    eax, eax
0x10006cef  movzx   eax, [ebp+SystemTime.wSecond]
0x10006cf3  movzx   edx, [ebp+SystemTime.wHour]
0x10006cf7  push    eax
0x10006cf8  push    ecx
0x10006cf9  push    edx
0x10006cfa  jz      short loc_10006D27
0x10006cfc  movzx   esi, [ebp+SystemTime.wDay]
0x10006d00  movzx   edi, [ebp+SystemTime.wMonth]
0x10006d04  push    esi
0x10006d05  push    edi
0x10006d06  call    ds:__imp__GetCurrentThreadId@0; GetCurrentThreadId()
0x10006d0c  push    eax
0x10006d0d  push    offset a03d02u02u02u02_0; "\r\n[%03d] %02u-%02u %02u:%02u:%02u: %s"
0x10006d12  push    1388h; cbDest
0x10006d17  push    [ebp+pszDest]; pszDest
0x10006d1a  call    _StringCbPrintfW
0x10006d1f  add     esp, 28h
0x10006d22  mov     edi, [ebp+var_20]
0x10006d25  jmp     short loc_10006DA4
0x10006d27  call    ds:__imp__GetCurrentThreadId@0; GetCurrentThreadId()
0x10006d2d  push    eax
0x10006d2e  push    offset a03d02u02u02uS; "\r\n[%03d] %02u:%02u:%02u: %s"
0x10006d33  push    1388h; cbDest
0x10006d38  push    [ebp+pszDest]; pszDest
0x10006d3b  call    _StringCbPrintfW
0x10006d40  add     esp, 20h
0x10006d43  jmp     short loc_10006DA7
0x10006d45  movzx   ecx, [ebp+SystemTime.wSecond]
0x10006d49  test    eax, eax
0x10006d4b  movzx   eax, [ebp+SystemTime.wMilliseconds]
0x10006d4f  movzx   edx, [ebp+SystemTime.wMinute]
0x10006d53  movzx   esi, [ebp+SystemTime.wHour]
0x10006d57  push    eax
0x10006d58  push    ecx
0x10006d59  push    edx
0x10006d5a  push    esi
0x10006d5b  jz      short loc_10006D88
0x10006d5d  movzx   edi, [ebp+SystemTime.wDay]
0x10006d61  movzx   ebx, [ebp+SystemTime.wMonth]
0x10006d65  push    edi
0x10006d66  push    ebx
0x10006d67  call    ds:__imp__GetCurrentThreadId@0; GetCurrentThreadId()
0x10006d6d  push    eax
0x10006d6e  push    offset a03d02u02u02u02; "\r\n[%03d] %02u-%02u %02u:%02u:%02u:%03"...
0x10006d73  push    1388h; cbDest
0x10006d78  push    [ebp+pszDest]; pszDest
0x10006d7b  call    _StringCbPrintfW
0x10006d80  add     esp, 2Ch
0x10006d83  or      ebx, 0FFFFFFFFh
0x10006d86  jmp     short loc_10006D22
0x10006d88  call    ds:__imp__GetCurrentThreadId@0; GetCurrentThreadId()
0x10006d8e  push    eax
0x10006d8f  push    offset a03d02u02u02u03_2; "\r\n[%03d] %02u:%02u:%02u:%03u: %s"
0x10006d94  push    1388h; cbDest
0x10006d99  push    [ebp+pszDest]; pszDest
0x10006d9c  call    _StringCbPrintfW
0x10006da1  add     esp, 24h
0x10006da4  mov     esi, [ebp+var_28]
0x10006da7  mov     ecx, eax
0x10006da9  xor     edx, edx
0x10006dab  mov     eax, [ebp+pszDest]
0x10006dae  test    ecx, ecx
0x10006db0  mov     [ebp+var_18], eax
0x10006db3  movzx   eax, cx
0x10006db6  cmovns  eax, edx
0x10006db9  mov     [ebp+var_20], eax
0x10006dbc  test    eax, eax
0x10006dbe  jnz     short loc_10006DD0
0x10006dc0  push    [ebp+var_18]
0x10006dc3  mov     edx, edi
0x10006dc5  push    [ebp+dwFlags]
0x10006dc8  call    _TraceWriteOutputW@16; TraceWriteOutputW(x,x,x,x)
0x10006dcd  mov     [ebp+var_2C], eax
0x10006dd0  push    [ebp+pszDest]; lpMem
0x10006dd3  push    0; dwFlags
0x10006dd5  call    ds:__imp__GetProcessHeap@0; GetProcessHeap()
0x10006ddb  push    eax; hHeap
0x10006ddc  call    ds:__imp__HeapFree@12; HeapFree(x,x,x)
0x10006de2  mov     ecx, ebx
0x10006de4  lea     edx, [edi+18h]
0x10006de7  lock xadd [edx], ecx
0x10006deb  jns     short loc_10006DF6
0x10006ded  push    dword ptr [edi+1Ch]; hEvent
0x10006df0  call    ds:__imp__SetEvent@4; SetEvent(x)
0x10006df6  mov     eax, [ebp+var_24]
0x10006df9  lock xadd [eax], ebx
0x10006dfd  dec     ebx
0x10006dfe  jns     short loc_10006E09
0x10006e00  push    dword ptr [esi+1Ch]; hEvent
0x10006e03  call    ds:__imp__SetEvent@4; SetEvent(x)
0x10006e09  mov     eax, [ebp+var_2C]
0x10006e0c  xor     ecx, ecx
0x10006e0e  cmp     [ebp+var_20], ecx
0x10006e11  cmovnz  eax, ecx
0x10006e14  jmp     short loc_10006E20
0x10006e16  mov     eax, 3EBh
0x10006e1b  jmp     short loc_10006E20
0x10006e1d  push    57h ; 'W'
0x10006e1f  pop     eax
0x10006e20  mov     ecx, [ebp+var_4]
0x10006e23  pop     edi
0x10006e24  pop     esi
0x10006e25  xor     ecx, ebp; StackCookie
0x10006e27  pop     ebx
0x10006e28  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10006e2d  leave
0x10006e2e  retn    0Ch
```
