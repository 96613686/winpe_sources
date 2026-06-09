# TraceVprintfInternalW(x,x,x,x)

- ea: `0x100020d0`
- end: `0x1000214e`
- name: `_TraceVprintfInternalW@16`
- size: `126`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x10002070`
- `0x10006b20`
- `0x10006e40`

## callees

- `0x100020d0`
- `0x10003c20`
- `0x100065eb`
- `0x10006616`
- `0x100081de`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x10005229`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1000539d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x100053c1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x10005229`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1000539d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x100053c1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x10005154`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x100051e0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x10005154`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x100051e0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1000514d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x100051d9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x10005222`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x10005396`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x100053ba`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1000514d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x100051d9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x10005222`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x10005396`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x100053ba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x10005277`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x10005298`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x100052d8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x100052f9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x10005277`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x10005298`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x100052d8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x100052f9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100050dc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10005110`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100050dc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10005110`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x100050cc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10005100`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x100050cc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10005100`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x10005172`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x10005189`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x10005201`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x10005214`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x10005365`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1000537b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x10005172`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x10005189`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x10005201`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x10005214`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x10005365`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1000537b`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x10005247`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x10005247`

## pseudocode

```c
int __fastcall TraceVprintfInternalW(int a1, int a2, wchar_t *a3, size_t a4)
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
  const wchar_t *v38; // [esp+0h] [ebp-48h]
  va_list v39; // [esp+4h] [ebp-44h]
  int v40; // [esp+Ch] [ebp-3Ch]
  volatile signed __int32 *v41; // [esp+10h] [ebp-38h]
  int v43; // [esp+1Ch] [ebp-2Ch]
  volatile signed __int32 *v44; // [esp+20h] [ebp-28h]
  int v45; // [esp+24h] [ebp-24h]
  void *v46; // [esp+28h] [ebp-20h]
  void *lpMem; // [esp+30h] [ebp-18h]
  _SYSTEMTIME SystemTime; // [esp+34h] [ebp-14h] BYREF

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
    v13 = StringCbVPrintfW(a3, a4, v38, v39);
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
      v18 = StringCbPrintfW(
              (STRSAFE_LPWSTR)lpMem,
              0x1388u,
              L"\r\n[%03d] %02u-%02u %02u:%02u:%02u:%03u: %s",
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
      v18 = StringCbPrintfW(
              (STRSAFE_LPWSTR)lpMem,
              0x1388u,
              L"\r\n[%03d] %02u:%02u:%02u:%03u: %s",
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
      v18 = StringCbPrintfW((STRSAFE_LPWSTR)lpMem, 0x1388u, L"\r\n[%03d] %02u:%02u:%02u: %s", v19, v32, v34, v36, a3);
      goto LABEL_44;
    }
    v30 = SystemTime.wDay;
    v28 = SystemTime.wMonth;
    v17 = GetCurrentThreadId();
    v18 = StringCbPrintfW(
            (STRSAFE_LPWSTR)lpMem,
            0x1388u,
            L"\r\n[%03d] %02u-%02u %02u:%02u:%02u: %s",
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
  v23 = StringCbVPrintfW((STRSAFE_LPWSTR)lpMem, a4, v38, v39);
  if ( v23 < 0 )
  {
    v14 = (unsigned __int16)v23;
    goto LABEL_49;
  }
LABEL_50:
  v24 = TraceWriteOutputW(v4, v46);
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
0x100020d0  mov     edi, edi
0x100020d2  push    ebp
0x100020d3  mov     ebp, esp
0x100020d5  sub     esp, 3Ch
0x100020d8  mov     eax, ___security_cookie
0x100020dd  xor     eax, ebp
0x100020df  mov     [ebp+var_4], eax
0x100020e2  mov     eax, [ebp+arg_0]
0x100020e5  mov     [ebp+pszDest], eax
0x100020e8  mov     [ebp+var_24], 0
0x100020ef  mov     [ebp+var_3C], 0
0x100020f6  push    ebx
0x100020f7  mov     ebx, edx
0x100020f9  mov     [ebp+var_30], ebx
0x100020fc  push    esi; argList
0x100020fd  push    edi; pszFormat
0x100020fe  mov     edi, ecx
0x10002100  mov     ecx, [ebp+arg_4]
0x10002103  mov     [ebp+cbDest], ecx
0x10002106  test    eax, eax
0x10002108  jz      short loc_10002130
0x1000210a  mov     esi, _g_server
0x10002110  test    esi, esi
0x10002112  jz      short loc_10002130
0x10002114  cmp     dword ptr [esi+34h], 0
0x10002118  jz      short loc_10002130
0x1000211a  mov     eax, [esi+edi*4+44h]
0x1000211e  test    bl, 2
0x10002121  jz      short loc_10002145
0x10002123  and     eax, ebx
0x10002125  test    eax, 0FFFF0000h
0x1000212a  jnz     loc_100050CB
0x10002130  xor     eax, eax
0x10002132  mov     ecx, [ebp+var_4]
0x10002135  pop     edi
0x10002136  pop     esi
0x10002137  xor     ecx, ebp; StackCookie
0x10002139  pop     ebx
0x1000213a  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1000213f  mov     esp, ebp
0x10002141  pop     ebp
0x10002142  retn    8
0x10002145  test    eax, eax
0x10002147  jz      short loc_10002130
0x10002149  jmp     loc_100050CB
0x100050cb  push    esi; lpCriticalSection
0x100050cc  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x100050d2  lea     eax, [esi+18h]
0x100050d5  mov     [ebp+var_28], eax
0x100050d8  lock inc dword ptr [eax]
0x100050db  push    esi; lpCriticalSection
0x100050dc  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x100050e2  mov     edi, [esi+edi*4+134h]
0x100050e9  mov     [ebp+var_2C], edi
0x100050ec  test    edi, edi
0x100050ee  jnz     short loc_100050FF
0x100050f0  or      eax, 0FFFFFFFFh
0x100050f3  lea     ecx, [esi+18h]
0x100050f6  lock xadd [ecx], eax
0x100050fa  jmp     loc_10005180
0x100050ff  push    edi; lpCriticalSection
0x10005100  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x10005106  lea     eax, [edi+18h]
0x10005109  mov     [ebp+var_38], eax
0x1000510c  lock inc dword ptr [eax]
0x1000510f  push    edi; lpCriticalSection
0x10005110  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10005116  test    byte ptr [edi+20h], 1
0x1000511a  jz      short loc_1000512C
0x1000511c  or      ebx, 0FFFFFFFFh
0x1000511f  lea     edx, [edi+18h]
0x10005122  mov     eax, ebx
0x10005124  lock xadd [edx], eax
0x10005128  js      short loc_1000516F
0x1000512a  jmp     short loc_10005178
0x1000512c  xor     eax, eax
0x1000512e  mov     ecx, offset _g_FormatBuffer
0x10005133  xchg    eax, [ecx]
0x10005135  mov     [ebp+lpMem], eax
0x10005138  test    eax, eax
0x1000513a  jz      short loc_10005146
0x1000513c  mov     edi, 1
0x10005141  mov     [ebp+var_24], edi
0x10005144  jmp     short loc_10005196
0x10005146  push    1388h; dwBytes
0x1000514b  push    0; dwFlags
0x1000514d  call    ds:__imp__GetProcessHeap@0; GetProcessHeap()
0x10005153  push    eax; hHeap
0x10005154  call    ds:__imp__HeapAlloc@12; HeapAlloc(x,x,x)
0x1000515a  mov     [ebp+lpMem], eax
0x1000515d  test    eax, eax
0x1000515f  jnz     short loc_10005194
0x10005161  or      ebx, 0FFFFFFFFh
0x10005164  lea     edx, [edi+18h]
0x10005167  mov     eax, ebx
0x10005169  lock xadd [edx], eax
0x1000516d  jns     short loc_10005178
0x1000516f  push    dword ptr [edi+1Ch]; hEvent
0x10005172  call    ds:__imp__SetEvent@4; SetEvent(x)
0x10005178  mov     ecx, [ebp+var_28]
0x1000517b  lock xadd [ecx], ebx
0x1000517f  dec     ebx
0x10005180  jns     loc_10002130
0x10005186  push    dword ptr [esi+1Ch]; hEvent
0x10005189  call    ds:__imp__SetEvent@4; SetEvent(x)
0x1000518f  jmp     loc_10002130
0x10005194  xor     edi, edi
0x10005196  xor     eax, eax
0x10005198  mov     ecx, offset _g_PrintBuffer
0x1000519d  xchg    eax, [ecx]
0x1000519f  mov     [ebp+var_20], eax
0x100051a2  test    eax, eax
0x100051a4  jz      short loc_100051D2
0x100051a6  mov     [ebp+var_3C], 1
0x100051ad  test    bl, 1
0x100051b0  jz      loc_10005243
0x100051b6  push    [ebp+cbDest]; cbDest
0x100051b9  mov     ecx, eax
0x100051bb  push    [ebp+pszDest]; pszDest
0x100051be  call    _StringCbVPrintfW@16; StringCbVPrintfW(x,x,x,x)
0x100051c3  xor     edx, edx
0x100051c5  movzx   ecx, ax
0x100051c8  test    eax, eax
0x100051ca  cmovns  ecx, edx
0x100051cd  jmp     loc_1000533B
0x100051d2  push    1388h; dwBytes
0x100051d7  push    0; dwFlags
0x100051d9  call    ds:__imp__GetProcessHeap@0; GetProcessHeap()
0x100051df  push    eax; hHeap
0x100051e0  call    ds:__imp__HeapAlloc@12; HeapAlloc(x,x,x)
0x100051e6  mov     [ebp+var_20], eax
0x100051e9  test    eax, eax
0x100051eb  jnz     short loc_100051AD
0x100051ed  mov     edx, [ebp+var_38]
0x100051f0  or      ebx, 0FFFFFFFFh
0x100051f3  mov     eax, ebx
0x100051f5  lock xadd [edx], eax
0x100051f9  jns     short loc_10005207
0x100051fb  mov     edx, [ebp+var_2C]
0x100051fe  push    dword ptr [edx+1Ch]; hEvent
0x10005201  call    ds:__imp__SetEvent@4; SetEvent(x)
0x10005207  mov     ecx, [ebp+var_28]
0x1000520a  lock xadd [ecx], ebx
0x1000520e  dec     ebx
0x1000520f  jns     short loc_1000521A
0x10005211  push    dword ptr [esi+1Ch]; hEvent
0x10005214  call    ds:__imp__SetEvent@4; SetEvent(x)
0x1000521a  test    edi, edi
0x1000521c  jnz     short loc_10005234
0x1000521e  push    [ebp+lpMem]; lpMem
0x10005221  push    edi; dwFlags
0x10005222  call    ds:__imp__GetProcessHeap@0; GetProcessHeap()
0x10005228  push    eax; hHeap
0x10005229  call    ds:__imp__HeapFree@12; HeapFree(x,x,x)
0x1000522f  jmp     loc_10002130
0x10005234  mov     eax, [ebp+lpMem]
0x10005237  mov     ecx, offset _g_FormatBuffer
0x1000523c  xchg    eax, [ecx]
0x1000523e  jmp     loc_10002130
0x10005243  lea     eax, [ebp+SystemTime]
0x10005246  push    eax; lpSystemTime
0x10005247  call    ds:__imp__GetLocalTime@4; GetLocalTime(x)
0x1000524d  push    [ebp+pszDest]
0x10005250  mov     eax, ebx
0x10005252  and     eax, 8
0x10005255  test    bl, 4
0x10005258  jnz     short loc_100052B6
0x1000525a  movzx   ecx, [ebp+SystemTime.wMinute]
0x1000525e  test    eax, eax
0x10005260  movzx   eax, [ebp+SystemTime.wSecond]
0x10005264  movzx   edx, [ebp+SystemTime.wHour]
0x10005268  push    eax
0x10005269  push    ecx
0x1000526a  push    edx
0x1000526b  jz      short loc_10005298
0x1000526d  movzx   edi, [ebp+SystemTime.wDay]
0x10005271  movzx   ebx, [ebp+SystemTime.wMonth]
0x10005275  push    edi
0x10005276  push    ebx
0x10005277  call    ds:__imp__GetCurrentThreadId@0; GetCurrentThreadId()
0x1000527d  push    eax
0x1000527e  push    offset a03d02u02u02u02_0; "\r\n[%03d] %02u-%02u %02u:%02u:%02u: %s"
0x10005283  push    1388h; cbDest
0x10005288  push    [ebp+lpMem]; pszDest
0x1000528b  call    _StringCbPrintfW
0x10005290  mov     ebx, [ebp+var_30]
0x10005293  add     esp, 28h
0x10005296  jmp     short loc_10005315
0x10005298  call    ds:__imp__GetCurrentThreadId@0; GetCurrentThreadId()
0x1000529e  push    eax
0x1000529f  push    offset a03d02u02u02uS; "\r\n[%03d] %02u:%02u:%02u: %s"
0x100052a4  push    1388h; cbDest
0x100052a9  push    [ebp+lpMem]; pszDest
0x100052ac  call    _StringCbPrintfW
0x100052b1  add     esp, 20h
0x100052b4  jmp     short loc_10005318
0x100052b6  movzx   ecx, [ebp+SystemTime.wSecond]
0x100052ba  test    eax, eax
0x100052bc  movzx   eax, [ebp+SystemTime.wMilliseconds]
0x100052c0  movzx   edx, [ebp+SystemTime.wMinute]
0x100052c4  movzx   edi, [ebp+SystemTime.wHour]
0x100052c8  push    eax
0x100052c9  push    ecx
0x100052ca  push    edx
0x100052cb  push    edi
0x100052cc  jz      short loc_100052F9
0x100052ce  movzx   ebx, [ebp+SystemTime.wDay]
0x100052d2  movzx   eax, [ebp+SystemTime.wMonth]
0x100052d6  push    ebx
0x100052d7  push    eax
0x100052d8  call    ds:__imp__GetCurrentThreadId@0; GetCurrentThreadId()
0x100052de  push    eax
0x100052df  push    offset a03d02u02u02u02; "\r\n[%03d] %02u-%02u %02u:%02u:%02u:%03"...
0x100052e4  push    1388h; cbDest
0x100052e9  push    [ebp+lpMem]; pszDest
0x100052ec  call    _StringCbPrintfW
0x100052f1  mov     ebx, [ebp+var_30]
0x100052f4  add     esp, 2Ch
0x100052f7  jmp     short loc_10005315
0x100052f9  call    ds:__imp__GetCurrentThreadId@0; GetCurrentThreadId()
0x100052ff  push    eax
0x10005300  push    offset a03d02u02u02u03_2; "\r\n[%03d] %02u:%02u:%02u:%03u: %s"
0x10005305  push    1388h; cbDest
0x1000530a  push    [ebp+lpMem]; pszDest
0x1000530d  call    _StringCbPrintfW
0x10005312  add     esp, 24h
0x10005315  mov     edi, [ebp+var_24]
0x10005318  xor     edx, edx
0x1000531a  movzx   ecx, ax
0x1000531d  test    eax, eax
0x1000531f  cmovns  ecx, edx
0x10005322  test    ecx, ecx
0x10005324  jnz     short loc_1000534F
0x10005326  push    [ebp+cbDest]; cbDest
0x10005329  mov     ecx, [ebp+var_20]
0x1000532c  push    [ebp+lpMem]; pszDest
0x1000532f  call    _StringCbVPrintfW@16; StringCbVPrintfW(x,x,x,x)
0x10005334  test    eax, eax
0x10005336  jns     short loc_1000533F
0x10005338  movzx   ecx, ax
0x1000533b  test    ecx, ecx
0x1000533d  jnz     short loc_1000534F
0x1000533f  push    [ebp+var_20]
0x10005342  mov     edx, [ebp+var_2C]
0x10005345  push    ebx
0x10005346  call    _TraceWriteOutputW@16; TraceWriteOutputW(x,x,x,x)
0x1000534b  mov     ebx, eax
0x1000534d  jmp     short loc_10005351
0x1000534f  xor     ebx, ebx
0x10005351  mov     edx, [ebp+var_38]
0x10005354  or      eax, 0FFFFFFFFh
0x10005357  mov     ecx, eax
0x10005359  lock xadd [edx], ecx
0x1000535d  jns     short loc_1000536E
0x1000535f  mov     eax, [ebp+var_2C]
0x10005362  push    dword ptr [eax+1Ch]; hEvent
0x10005365  call    ds:__imp__SetEvent@4; SetEvent(x)
0x1000536b  or      eax, 0FFFFFFFFh
0x1000536e  mov     ecx, [ebp+var_28]
0x10005371  lock xadd [ecx], eax
0x10005375  dec     eax
0x10005376  jns     short loc_10005381
0x10005378  push    dword ptr [esi+1Ch]; hEvent
0x1000537b  call    ds:__imp__SetEvent@4; SetEvent(x)
0x10005381  test    edi, edi
0x10005383  jz      short loc_10005391
0x10005385  mov     eax, [ebp+lpMem]
0x10005388  mov     ecx, offset _g_FormatBuffer
0x1000538d  xchg    eax, [ecx]
0x1000538f  jmp     short loc_100053A3
0x10005391  push    [ebp+lpMem]; lpMem
0x10005394  push    0; dwFlags
0x10005396  call    ds:__imp__GetProcessHeap@0; GetProcessHeap()
0x1000539c  push    eax; hHeap
0x1000539d  call    ds:__imp__HeapFree@12; HeapFree(x,x,x)
0x100053a3  cmp     [ebp+var_3C], 0
0x100053a7  jz      short loc_100053B5
0x100053a9  mov     eax, [ebp+var_20]
0x100053ac  mov     ecx, offset _g_PrintBuffer
0x100053b1  xchg    eax, [ecx]
0x100053b3  jmp     short loc_100053C7
0x100053b5  push    [ebp+var_20]; lpMem
0x100053b8  push    0; dwFlags
0x100053ba  call    ds:__imp__GetProcessHeap@0; GetProcessHeap()
0x100053c0  push    eax; hHeap
0x100053c1  call    ds:__imp__HeapFree@12; HeapFree(x,x,x)
0x100053c7  mov     eax, ebx
0x100053c9  jmp     loc_10002132
```
