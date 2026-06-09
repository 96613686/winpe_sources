# TraceVprintfInternalA(x,x,x,x)

- ea: `0x10003000`
- end: `0x10003074`
- name: `_TraceVprintfInternalA@16`
- size: `116`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x10002fa0`
- `0x10006270`
- `0x10006590`

## callees

- `0x10003000`
- `0x10003c20`
- `0x10005d00`
- `0x10005d42`
- `0x100077c0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1000592e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x10005aa2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x10005ac6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1000592e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x10005aa2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x10005ac6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x10005859`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x100058e5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x10005859`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x100058e5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x10005852`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x100058de`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x10005927`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x10005a9b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x10005abf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x10005852`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x100058de`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x10005927`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x10005a9b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x10005abf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1000597c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1000599d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x100059dd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x100059fe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1000597c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1000599d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x100059dd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x100059fe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100057e1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10005815`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100057e1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10005815`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x100057d1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10005805`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x100057d1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10005805`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x10005877`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1000588e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x10005906`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x10005919`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x10005a6a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x10005a80`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x10005877`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1000588e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x10005906`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x10005919`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x10005a6a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x10005a80`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x1000594c`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x1000594c`

## pseudocode

```c
int __fastcall TraceVprintfInternalA(int a1, int a2, char *a3, size_t a4)
{
  int v4; // ebx
  LPCRITICAL_SECTION v6; // esi
  int v7; // eax
  int v9; // edi
  bool v10; // sf
  int v11; // edi
  HANDLE ProcessHeap; // eax
  HRESULT v13; // eax
  int v14; // ecx
  HANDLE v15; // eax
  HANDLE v16; // eax
  DWORD v17; // eax
  HRESULT v18; // eax
  DWORD v19; // eax
  DWORD CurrentThreadId; // eax
  DWORD v21; // eax
  int v22; // ecx
  HRESULT v23; // eax
  int v24; // ebx
  HANDLE v25; // eax
  HANDLE v26; // eax
  int wMonth; // [esp-1Ch] [ebp-64h]
  int v28; // [esp-18h] [ebp-60h]
  int wDay; // [esp-18h] [ebp-60h]
  int v30; // [esp-14h] [ebp-5Ch]
  int wHour; // [esp-14h] [ebp-5Ch]
  int v32; // [esp-10h] [ebp-58h]
  int wMinute; // [esp-10h] [ebp-58h]
  int v34; // [esp-Ch] [ebp-54h]
  int wSecond; // [esp-Ch] [ebp-54h]
  int v36; // [esp-8h] [ebp-50h]
  int wMilliseconds; // [esp-8h] [ebp-50h]
  const char *v38; // [esp+0h] [ebp-48h]
  va_list v39; // [esp+4h] [ebp-44h]
  int v40; // [esp+Ch] [ebp-3Ch]
  volatile signed __int32 *v41; // [esp+10h] [ebp-38h]
  int v43; // [esp+1Ch] [ebp-2Ch]
  volatile signed __int32 *v44; // [esp+20h] [ebp-28h]
  int v45; // [esp+24h] [ebp-24h]
  void *v46; // [esp+28h] [ebp-20h]
  void *lpMem; // [esp+30h] [ebp-18h]
  struct _SYSTEMTIME SystemTime; // [esp+34h] [ebp-14h] BYREF

  v45 = 0;
  v40 = 0;
  v4 = a2;
  if ( !a3 )
    return 0;
  v6 = g_server;
  if ( !g_server || !g_server[2].LockCount )
    return 0;
  v7 = *(&g_server[2].SpinCount + a1);
  if ( (a2 & 2) != 0 )
  {
    if ( (a2 & v7 & 0xFFFF0000) == 0 )
      return 0;
  }
  else if ( !v7 )
  {
    return 0;
  }
  EnterCriticalSection(g_server);
  v44 = (volatile signed __int32 *)&v6[1];
  _InterlockedIncrement((volatile signed __int32 *)&v6[1]);
  LeaveCriticalSection(v6);
  v9 = *(&v6[12].SpinCount + a1);
  v43 = v9;
  if ( !v9 )
  {
    v10 = _InterlockedExchangeAdd((volatile signed __int32 *)&v6[1], 0xFFFFFFFF) < 0;
    goto LABEL_19;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)v9);
  v41 = (volatile signed __int32 *)(v9 + 24);
  _InterlockedIncrement((volatile signed __int32 *)(v9 + 24));
  LeaveCriticalSection((LPCRITICAL_SECTION)v9);
  if ( (*(_BYTE *)(v9 + 32) & 1) != 0 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v9 + 24), 0xFFFFFFFF) >= 0 )
      goto LABEL_18;
    goto LABEL_17;
  }
  lpMem = (void *)_InterlockedExchange((volatile __int32 *)&g_FormatBuffer, 0);
  if ( lpMem )
  {
    v11 = 1;
    v45 = 1;
  }
  else
  {
    ProcessHeap = GetProcessHeap();
    lpMem = HeapAlloc(ProcessHeap, 0, 0x1388u);
    if ( !lpMem )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v9 + 24), 0xFFFFFFFF) >= 0 )
      {
LABEL_18:
        v10 = _InterlockedDecrement(v44) < 0;
LABEL_19:
        if ( v10 )
          SetEvent((HANDLE)v6[1].LockCount);
        return 0;
      }
LABEL_17:
      SetEvent(*(HANDLE *)(v9 + 28));
      goto LABEL_18;
    }
    v11 = 0;
  }
  v46 = (void *)_InterlockedExchange((volatile __int32 *)&g_PrintBuffer, 0);
  if ( v46 )
  {
    v40 = 1;
  }
  else
  {
    v15 = GetProcessHeap();
    v46 = HeapAlloc(v15, 0, 0x1388u);
    if ( !v46 )
    {
      if ( _InterlockedExchangeAdd(v41, 0xFFFFFFFF) < 0 )
        SetEvent(*(HANDLE *)(v43 + 28));
      if ( _InterlockedDecrement(v44) < 0 )
        SetEvent((HANDLE)v6[1].LockCount);
      if ( v11 )
      {
        _InterlockedExchange((volatile __int32 *)&g_FormatBuffer, (__int32)lpMem);
      }
      else
      {
        v16 = GetProcessHeap();
        HeapFree(v16, 0, lpMem);
      }
      return 0;
    }
  }
  if ( (v4 & 1) != 0 )
  {
    v13 = StringCbVPrintfA(a3, a4, v38, v39);
    v14 = (unsigned __int16)v13;
    if ( v13 >= 0 )
      v14 = 0;
LABEL_49:
    if ( !v14 )
      goto LABEL_50;
LABEL_51:
    v24 = 0;
    goto LABEL_52;
  }
  GetLocalTime(&SystemTime);
  if ( (v4 & 4) != 0 )
  {
    wMilliseconds = SystemTime.wMilliseconds;
    wSecond = SystemTime.wSecond;
    wMinute = SystemTime.wMinute;
    wHour = SystemTime.wHour;
    if ( (v4 & 8) != 0 )
    {
      wDay = SystemTime.wDay;
      wMonth = SystemTime.wMonth;
      CurrentThreadId = GetCurrentThreadId();
      v18 = StringCchPrintfA(
              (STRSAFE_LPSTR)lpMem,
              0x1388u,
              "\r\n[%03d] %02u-%02u %02u:%02u:%02u:%03u: %s",
              CurrentThreadId,
              wMonth,
              wDay,
              wHour,
              wMinute,
              wSecond,
              wMilliseconds,
              a3);
      v4 = a2;
    }
    else
    {
      v21 = GetCurrentThreadId();
      v18 = StringCchPrintfA(
              (STRSAFE_LPSTR)lpMem,
              0x1388u,
              "\r\n[%03d] %02u:%02u:%02u:%03u: %s",
              v21,
              wHour,
              wMinute,
              wSecond,
              wMilliseconds,
              a3);
    }
  }
  else
  {
    v36 = SystemTime.wSecond;
    v34 = SystemTime.wMinute;
    v32 = SystemTime.wHour;
    if ( (v4 & 8) == 0 )
    {
      v19 = GetCurrentThreadId();
      v18 = StringCchPrintfA((STRSAFE_LPSTR)lpMem, 0x1388u, "\r\n[%03d] %02u:%02u:%02u: %s", v19, v32, v34, v36, a3);
      goto LABEL_44;
    }
    v30 = SystemTime.wDay;
    v28 = SystemTime.wMonth;
    v17 = GetCurrentThreadId();
    v18 = StringCchPrintfA(
            (STRSAFE_LPSTR)lpMem,
            0x1388u,
            "\r\n[%03d] %02u-%02u %02u:%02u:%02u: %s",
            v17,
            v28,
            v30,
            v32,
            v34,
            v36,
            a3);
    v4 = a2;
  }
  v11 = v45;
LABEL_44:
  v22 = (unsigned __int16)v18;
  if ( v18 >= 0 )
    v22 = 0;
  if ( v22 )
    goto LABEL_51;
  v23 = StringCbVPrintfA((STRSAFE_LPSTR)lpMem, a4, v38, v39);
  if ( v23 < 0 )
  {
    v14 = (unsigned __int16)v23;
    goto LABEL_49;
  }
LABEL_50:
  v24 = TraceWriteOutputA(v4, v46);
LABEL_52:
  if ( _InterlockedExchangeAdd(v41, 0xFFFFFFFF) < 0 )
    SetEvent(*(HANDLE *)(v43 + 28));
  if ( _InterlockedDecrement(v44) < 0 )
    SetEvent((HANDLE)v6[1].LockCount);
  if ( v11 )
  {
    _InterlockedExchange((volatile __int32 *)&g_FormatBuffer, (__int32)lpMem);
  }
  else
  {
    v25 = GetProcessHeap();
    HeapFree(v25, 0, lpMem);
  }
  if ( v40 )
  {
    _InterlockedExchange((volatile __int32 *)&g_PrintBuffer, (__int32)v46);
  }
  else
  {
    v26 = GetProcessHeap();
    HeapFree(v26, 0, v46);
  }
  return v24;
}

```

## disassembly

```asm
0x10003000  mov     edi, edi
0x10003002  push    ebp
0x10003003  mov     ebp, esp
0x10003005  sub     esp, 3Ch
0x10003008  mov     eax, ___security_cookie
0x1000300d  xor     eax, ebp
0x1000300f  mov     [ebp+var_4], eax
0x10003012  mov     eax, [ebp+arg_0]
0x10003015  mov     [ebp+pszDest], eax
0x10003018  mov     [ebp+var_24], 0
0x1000301f  mov     [ebp+var_3C], 0
0x10003026  push    ebx
0x10003027  mov     ebx, edx
0x10003029  mov     [ebp+var_30], ebx
0x1000302c  push    esi; argList
0x1000302d  push    edi; pszFormat
0x1000302e  mov     edi, ecx
0x10003030  mov     ecx, [ebp+arg_4]
0x10003033  mov     [ebp+cbDest], ecx
0x10003036  test    eax, eax
0x10003038  jz      short loc_1000305F
0x1000303a  mov     esi, _g_server
0x10003040  test    esi, esi
0x10003042  jz      short loc_1000305F
0x10003044  cmp     dword ptr [esi+34h], 0
0x10003048  jz      short loc_1000305F
0x1000304a  mov     eax, [esi+edi*4+44h]
0x1000304e  test    bl, 2
0x10003051  jnz     loc_100057C3
0x10003057  test    eax, eax
0x10003059  jnz     loc_100057D0
0x1000305f  xor     eax, eax
0x10003061  mov     ecx, [ebp+var_4]
0x10003064  pop     edi
0x10003065  pop     esi
0x10003066  xor     ecx, ebp; StackCookie
0x10003068  pop     ebx
0x10003069  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1000306e  mov     esp, ebp
0x10003070  pop     ebp
0x10003071  retn    8
0x100057c3  and     eax, ebx
0x100057c5  test    eax, 0FFFF0000h
0x100057ca  jz      loc_1000305F
0x100057d0  push    esi; lpCriticalSection
0x100057d1  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x100057d7  lea     eax, [esi+18h]
0x100057da  mov     [ebp+var_28], eax
0x100057dd  lock inc dword ptr [eax]
0x100057e0  push    esi; lpCriticalSection
0x100057e1  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x100057e7  mov     edi, [esi+edi*4+134h]
0x100057ee  mov     [ebp+var_2C], edi
0x100057f1  test    edi, edi
0x100057f3  jnz     short loc_10005804
0x100057f5  or      eax, 0FFFFFFFFh
0x100057f8  lea     ecx, [esi+18h]
0x100057fb  lock xadd [ecx], eax
0x100057ff  jmp     loc_10005885
0x10005804  push    edi; lpCriticalSection
0x10005805  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x1000580b  lea     eax, [edi+18h]
0x1000580e  mov     [ebp+var_38], eax
0x10005811  lock inc dword ptr [eax]
0x10005814  push    edi; lpCriticalSection
0x10005815  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1000581b  test    byte ptr [edi+20h], 1
0x1000581f  jz      short loc_10005831
0x10005821  or      ebx, 0FFFFFFFFh
0x10005824  lea     edx, [edi+18h]
0x10005827  mov     eax, ebx
0x10005829  lock xadd [edx], eax
0x1000582d  js      short loc_10005874
0x1000582f  jmp     short loc_1000587D
0x10005831  xor     eax, eax
0x10005833  mov     ecx, offset _g_FormatBuffer
0x10005838  xchg    eax, [ecx]
0x1000583a  mov     [ebp+lpMem], eax
0x1000583d  test    eax, eax
0x1000583f  jz      short loc_1000584B
0x10005841  mov     edi, 1
0x10005846  mov     [ebp+var_24], edi
0x10005849  jmp     short loc_1000589B
0x1000584b  push    1388h; dwBytes
0x10005850  push    0; dwFlags
0x10005852  call    ds:__imp__GetProcessHeap@0; GetProcessHeap()
0x10005858  push    eax; hHeap
0x10005859  call    ds:__imp__HeapAlloc@12; HeapAlloc(x,x,x)
0x1000585f  mov     [ebp+lpMem], eax
0x10005862  test    eax, eax
0x10005864  jnz     short loc_10005899
0x10005866  or      ebx, 0FFFFFFFFh
0x10005869  lea     edx, [edi+18h]
0x1000586c  mov     eax, ebx
0x1000586e  lock xadd [edx], eax
0x10005872  jns     short loc_1000587D
0x10005874  push    dword ptr [edi+1Ch]; hEvent
0x10005877  call    ds:__imp__SetEvent@4; SetEvent(x)
0x1000587d  mov     ecx, [ebp+var_28]
0x10005880  lock xadd [ecx], ebx
0x10005884  dec     ebx
0x10005885  jns     loc_1000305F
0x1000588b  push    dword ptr [esi+1Ch]; hEvent
0x1000588e  call    ds:__imp__SetEvent@4; SetEvent(x)
0x10005894  jmp     loc_1000305F
0x10005899  xor     edi, edi
0x1000589b  xor     eax, eax
0x1000589d  mov     ecx, offset _g_PrintBuffer
0x100058a2  xchg    eax, [ecx]
0x100058a4  mov     [ebp+var_20], eax
0x100058a7  test    eax, eax
0x100058a9  jz      short loc_100058D7
0x100058ab  mov     [ebp+var_3C], 1
0x100058b2  test    bl, 1
0x100058b5  jz      loc_10005948
0x100058bb  push    [ebp+cbDest]; cbDest
0x100058be  mov     ecx, eax
0x100058c0  push    [ebp+pszDest]; pszDest
0x100058c3  call    _StringCbVPrintfA@16; StringCbVPrintfA(x,x,x,x)
0x100058c8  xor     edx, edx
0x100058ca  movzx   ecx, ax
0x100058cd  test    eax, eax
0x100058cf  cmovns  ecx, edx
0x100058d2  jmp     loc_10005A40
0x100058d7  push    1388h; dwBytes
0x100058dc  push    0; dwFlags
0x100058de  call    ds:__imp__GetProcessHeap@0; GetProcessHeap()
0x100058e4  push    eax; hHeap
0x100058e5  call    ds:__imp__HeapAlloc@12; HeapAlloc(x,x,x)
0x100058eb  mov     [ebp+var_20], eax
0x100058ee  test    eax, eax
0x100058f0  jnz     short loc_100058B2
0x100058f2  mov     edx, [ebp+var_38]
0x100058f5  or      ebx, 0FFFFFFFFh
0x100058f8  mov     eax, ebx
0x100058fa  lock xadd [edx], eax
0x100058fe  jns     short loc_1000590C
0x10005900  mov     edx, [ebp+var_2C]
0x10005903  push    dword ptr [edx+1Ch]; hEvent
0x10005906  call    ds:__imp__SetEvent@4; SetEvent(x)
0x1000590c  mov     ecx, [ebp+var_28]
0x1000590f  lock xadd [ecx], ebx
0x10005913  dec     ebx
0x10005914  jns     short loc_1000591F
0x10005916  push    dword ptr [esi+1Ch]; hEvent
0x10005919  call    ds:__imp__SetEvent@4; SetEvent(x)
0x1000591f  test    edi, edi
0x10005921  jnz     short loc_10005939
0x10005923  push    [ebp+lpMem]; lpMem
0x10005926  push    edi; dwFlags
0x10005927  call    ds:__imp__GetProcessHeap@0; GetProcessHeap()
0x1000592d  push    eax; hHeap
0x1000592e  call    ds:__imp__HeapFree@12; HeapFree(x,x,x)
0x10005934  jmp     loc_1000305F
0x10005939  mov     eax, [ebp+lpMem]
0x1000593c  mov     ecx, offset _g_FormatBuffer
0x10005941  xchg    eax, [ecx]
0x10005943  jmp     loc_1000305F
0x10005948  lea     eax, [ebp+SystemTime]
0x1000594b  push    eax; lpSystemTime
0x1000594c  call    ds:__imp__GetLocalTime@4; GetLocalTime(x)
0x10005952  push    [ebp+pszDest]
0x10005955  mov     eax, ebx
0x10005957  and     eax, 8
0x1000595a  test    bl, 4
0x1000595d  jnz     short loc_100059BB
0x1000595f  movzx   ecx, [ebp+SystemTime.wMinute]
0x10005963  test    eax, eax
0x10005965  movzx   eax, [ebp+SystemTime.wSecond]
0x10005969  movzx   edx, [ebp+SystemTime.wHour]
0x1000596d  push    eax
0x1000596e  push    ecx
0x1000596f  push    edx
0x10005970  jz      short loc_1000599D
0x10005972  movzx   edi, [ebp+SystemTime.wDay]
0x10005976  movzx   ebx, [ebp+SystemTime.wMonth]
0x1000597a  push    edi
0x1000597b  push    ebx
0x1000597c  call    ds:__imp__GetCurrentThreadId@0; GetCurrentThreadId()
0x10005982  push    eax
0x10005983  push    offset a03d02u02u02u02_2; "\r\n[%03d] %02u-%02u %02u:%02u:%02u: %s"
0x10005988  push    1388h; cchDest
0x1000598d  push    [ebp+lpMem]; pszDest
0x10005990  call    _StringCchPrintfA
0x10005995  mov     ebx, [ebp+var_30]
0x10005998  add     esp, 28h
0x1000599b  jmp     short loc_10005A1A
0x1000599d  call    ds:__imp__GetCurrentThreadId@0; GetCurrentThreadId()
0x100059a3  push    eax
0x100059a4  push    offset a03d02u02u02uS_0; "\r\n[%03d] %02u:%02u:%02u: %s"
0x100059a9  push    1388h; cchDest
0x100059ae  push    [ebp+lpMem]; pszDest
0x100059b1  call    _StringCchPrintfA
0x100059b6  add     esp, 20h
0x100059b9  jmp     short loc_10005A1D
0x100059bb  movzx   ecx, [ebp+SystemTime.wSecond]
0x100059bf  test    eax, eax
0x100059c1  movzx   eax, [ebp+SystemTime.wMilliseconds]
0x100059c5  movzx   edx, [ebp+SystemTime.wMinute]
0x100059c9  movzx   edi, [ebp+SystemTime.wHour]
0x100059cd  push    eax
0x100059ce  push    ecx
0x100059cf  push    edx
0x100059d0  push    edi
0x100059d1  jz      short loc_100059FE
0x100059d3  movzx   ebx, [ebp+SystemTime.wDay]
0x100059d7  movzx   eax, [ebp+SystemTime.wMonth]
0x100059db  push    ebx
0x100059dc  push    eax
0x100059dd  call    ds:__imp__GetCurrentThreadId@0; GetCurrentThreadId()
0x100059e3  push    eax
0x100059e4  push    offset a03d02u02u02u02_1; "\r\n[%03d] %02u-%02u %02u:%02u:%02u:%03"...
0x100059e9  push    1388h; cchDest
0x100059ee  push    [ebp+lpMem]; pszDest
0x100059f1  call    _StringCchPrintfA
0x100059f6  mov     ebx, [ebp+var_30]
0x100059f9  add     esp, 2Ch
0x100059fc  jmp     short loc_10005A1A
0x100059fe  call    ds:__imp__GetCurrentThreadId@0; GetCurrentThreadId()
0x10005a04  push    eax
0x10005a05  push    offset a03d02u02u02u03_1; "\r\n[%03d] %02u:%02u:%02u:%03u: %s"
0x10005a0a  push    1388h; cchDest
0x10005a0f  push    [ebp+lpMem]; pszDest
0x10005a12  call    _StringCchPrintfA
0x10005a17  add     esp, 24h
0x10005a1a  mov     edi, [ebp+var_24]
0x10005a1d  xor     edx, edx
0x10005a1f  movzx   ecx, ax
0x10005a22  test    eax, eax
0x10005a24  cmovns  ecx, edx
0x10005a27  test    ecx, ecx
0x10005a29  jnz     short loc_10005A54
0x10005a2b  push    [ebp+cbDest]; cbDest
0x10005a2e  mov     ecx, [ebp+var_20]
0x10005a31  push    [ebp+lpMem]; pszDest
0x10005a34  call    _StringCbVPrintfA@16; StringCbVPrintfA(x,x,x,x)
0x10005a39  test    eax, eax
0x10005a3b  jns     short loc_10005A44
0x10005a3d  movzx   ecx, ax
0x10005a40  test    ecx, ecx
0x10005a42  jnz     short loc_10005A54
0x10005a44  push    [ebp+var_20]
0x10005a47  mov     edx, [ebp+var_2C]
0x10005a4a  push    ebx
0x10005a4b  call    _TraceWriteOutputA@16; TraceWriteOutputA(x,x,x,x)
0x10005a50  mov     ebx, eax
0x10005a52  jmp     short loc_10005A56
0x10005a54  xor     ebx, ebx
0x10005a56  mov     edx, [ebp+var_38]
0x10005a59  or      eax, 0FFFFFFFFh
0x10005a5c  mov     ecx, eax
0x10005a5e  lock xadd [edx], ecx
0x10005a62  jns     short loc_10005A73
0x10005a64  mov     eax, [ebp+var_2C]
0x10005a67  push    dword ptr [eax+1Ch]; hEvent
0x10005a6a  call    ds:__imp__SetEvent@4; SetEvent(x)
0x10005a70  or      eax, 0FFFFFFFFh
0x10005a73  mov     ecx, [ebp+var_28]
0x10005a76  lock xadd [ecx], eax
0x10005a7a  dec     eax
0x10005a7b  jns     short loc_10005A86
0x10005a7d  push    dword ptr [esi+1Ch]; hEvent
0x10005a80  call    ds:__imp__SetEvent@4; SetEvent(x)
0x10005a86  test    edi, edi
0x10005a88  jz      short loc_10005A96
0x10005a8a  mov     eax, [ebp+lpMem]
0x10005a8d  mov     ecx, offset _g_FormatBuffer
0x10005a92  xchg    eax, [ecx]
0x10005a94  jmp     short loc_10005AA8
0x10005a96  push    [ebp+lpMem]; lpMem
0x10005a99  push    0; dwFlags
0x10005a9b  call    ds:__imp__GetProcessHeap@0; GetProcessHeap()
0x10005aa1  push    eax; hHeap
0x10005aa2  call    ds:__imp__HeapFree@12; HeapFree(x,x,x)
0x10005aa8  cmp     [ebp+var_3C], 0
0x10005aac  jz      short loc_10005ABA
0x10005aae  mov     eax, [ebp+var_20]
0x10005ab1  mov     ecx, offset _g_PrintBuffer
0x10005ab6  xchg    eax, [ecx]
0x10005ab8  jmp     short loc_10005ACC
0x10005aba  push    [ebp+var_20]; lpMem
0x10005abd  push    0; dwFlags
0x10005abf  call    ds:__imp__GetProcessHeap@0; GetProcessHeap()
0x10005ac5  push    eax; hHeap
0x10005ac6  call    ds:__imp__HeapFree@12; HeapFree(x,x,x)
0x10005acc  mov     eax, ebx
0x10005ace  jmp     loc_10003061
```
