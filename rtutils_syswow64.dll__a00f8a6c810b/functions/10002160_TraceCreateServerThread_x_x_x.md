# TraceCreateServerThread(x,x,x)

- ea: `0x10002160`
- end: `0x100022be`
- name: `_TraceCreateServerThread@12`
- size: `350`
- prototype: ``
- caller_count: `12`
- callee_count: `6`
- tags: ``

## callers

- `0x10002070`
- `0x10002470`
- `0x10002fa0`
- `0x100030b0`
- `0x10005dd0`
- `0x10006270`
- `0x100062d0`
- `0x10006590`
- `0x10006770`
- `0x10006b20`
- `0x10006b80`
- `0x10006e40`

## callees

- `0x10002160`
- `0x100022c4`
- `0x100022f0`
- `0x100027e0`
- `0x10002e60`
- `0x1000976a`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1000545c`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1000545c`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1000220e`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1000220e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10002275`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10005404`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100054a0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10002275`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10005404`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100054a0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x10005482`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x10005482`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x10002173`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x10002173`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1000546b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1000546b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x10005479`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x10005479`

## pseudocode

```c
int __fastcall TraceCreateServerThread(ULONG a1, int a2, int a3)
{
  DWORD TickCount; // eax
  int v5; // esi
  LPCRITICAL_SECTION Server; // ebx
  unsigned int v7; // edi
  int v8; // ecx
  int v9; // edx
  int v10; // edx
  DWORD v11; // eax
  ULONG_PTR *p_SpinCount; // ecx
  ULONG_PTR *v13; // edi
  int v14; // eax
  int v16; // eax
  void *v17; // eax
  int v18; // edx
  DWORD LastError; // edi
  HANDLE v20; // eax
  ULONG v21; // [esp+0h] [ebp-18h]
  ULONG *v22; // [esp+4h] [ebp-14h]
  DWORD ThreadId; // [esp+Ch] [ebp-Ch] BYREF
  ULONG ulMinuend; // [esp+10h] [ebp-8h] BYREF
  int v25; // [esp+14h] [ebp-4h]

  ulMinuend = a1;
  v25 = a2;
  TickCount = GetTickCount();
  v5 = a2;
  ThreadId = 0;
  Server = g_server;
  v7 = TickCount;
  if ( !g_server )
  {
    Server = (LPCRITICAL_SECTION)TraceCreateServer();
    if ( !Server )
      return -1;
  }
  if ( (ulMinuend & 3) != 0 )
    goto LABEL_33;
  v8 = g_traceTime;
  if ( g_traceTime > v7 )
  {
    v8 = v7;
    g_traceTime = v7;
  }
  v9 = a3;
  if ( !a3 && v7 - v8 < 0x7530 )
    goto LABEL_18;
  if ( !v5 )
  {
    AcquireWriteLock(Server);
    v9 = a3;
    v5 = 1;
  }
  if ( g_serverThread )
    goto LABEL_18;
  if ( !v9 )
  {
    if ( ULongSub((ULONG)&ulMinuend, v21, v22) < 0 )
    {
      if ( !v25 )
      {
        Server[1].DebugInfo = 0;
        LeaveCriticalSection(Server);
      }
      return 111;
    }
    v11 = WaitForMultipleObjectsEx(ulMinuend, &g_hWaitHandles + v10, 0, 0, 0);
    g_traceTime = v7;
    if ( v11 == 258 )
      goto LABEL_18;
  }
  g_traceTime = v7;
  p_SpinCount = &Server[22].SpinCount;
  v13 = &Server[12].SpinCount;
  g_posLast = 3;
  if ( &Server[12].SpinCount >= &Server[22].SpinCount )
  {
LABEL_16:
    v14 = 0;
    goto LABEL_17;
  }
  while ( !*v13 )
  {
LABEL_15:
    if ( ++v13 >= p_SpinCount )
      goto LABEL_16;
  }
  if ( (*(_BYTE *)(*v13 + 32) & 1) == 0 )
  {
    TraceEnableClientA(0);
    p_SpinCount = &Server[22].SpinCount;
  }
  v16 = *(_DWORD *)(*v13 + 32);
  if ( (v16 & 6) == 0 )
  {
    if ( (v16 & 8) != 0 )
    {
      v17 = *(void **)(*v13 + 1040);
      v18 = g_posLast++;
      *(&g_hWaitHandles + v18) = v17;
    }
    goto LABEL_15;
  }
  v14 = 1;
LABEL_17:
  if ( !v14 )
  {
LABEL_18:
    if ( v5 )
    {
      if ( !v25 )
      {
        Server[1].DebugInfo = 0;
        LeaveCriticalSection(Server);
      }
    }
    return 0;
  }
LABEL_33:
  if ( !v5 )
    AcquireWriteLock(Server);
  if ( g_serverThread )
  {
    LastError = 0;
  }
  else
  {
    g_moduleRef = IncrementModuleReference();
    if ( g_moduleRef )
    {
      v20 = CreateThread(0, 0, TraceServerThread, Server, 0, &ThreadId);
      g_serverThread = (int)v20;
      if ( v20 )
      {
        CloseHandle(v20);
        LastError = 0;
      }
      else
      {
        LastError = GetLastError();
        FreeLibrary(g_moduleRef);
      }
    }
    else
    {
      LastError = 1003;
    }
  }
  if ( !v25 )
  {
    Server[1].DebugInfo = 0;
    LeaveCriticalSection(Server);
  }
  return LastError;
}

```

## disassembly

```asm
0x10002160  mov     edi, edi
0x10002162  push    ebp
0x10002163  mov     ebp, esp
0x10002165  sub     esp, 0Ch
0x10002168  push    ebx
0x10002169  push    esi; pulResult
0x1000216a  mov     ebx, edx
0x1000216c  mov     [ebp+ulMinuend], ecx
0x1000216f  push    edi; ulSubtrahend
0x10002170  mov     [ebp+var_4], ebx
0x10002173  call    ds:__imp__GetTickCount@0; GetTickCount()
0x10002179  mov     esi, ebx
0x1000217b  mov     [ebp+ThreadId], 0
0x10002182  mov     ebx, _g_server
0x10002188  mov     edi, eax
0x1000218a  test    ebx, ebx
0x1000218c  jz      loc_100053CE
0x10002192  test    byte ptr [ebp+ulMinuend], 3
0x10002196  jnz     loc_1000541E
0x1000219c  mov     ecx, _g_traceTime
0x100021a2  cmp     ecx, edi
0x100021a4  ja      loc_100053E5
0x100021aa  mov     edx, [ebp+arg_0]
0x100021ad  test    edx, edx
0x100021af  jnz     short loc_100021C0
0x100021b1  mov     eax, edi
0x100021b3  sub     eax, ecx
0x100021b5  cmp     eax, 7530h
0x100021ba  jb      loc_10002258
0x100021c0  test    esi, esi
0x100021c2  jnz     short loc_100021D3
0x100021c4  mov     ecx, ebx; lpCriticalSection
0x100021c6  call    _AcquireWriteLock@4; AcquireWriteLock(x)
0x100021cb  mov     edx, [ebp+arg_0]
0x100021ce  mov     esi, 1
0x100021d3  cmp     _g_serverThread, 0
0x100021da  jnz     short loc_10002258
0x100021dc  test    edx, edx
0x100021de  jnz     short loc_10002221
0x100021e0  mov     ecx, _g_posLast
0x100021e6  lea     eax, [ebp+ulMinuend]
0x100021e9  mov     edx, _g_posBase
0x100021ef  push    eax; ulMinuend
0x100021f0  call    _ULongSub@12; ULongSub(x,x,x)
0x100021f5  test    eax, eax
0x100021f7  js      loc_100053F2
0x100021fd  push    0; bAlertable
0x100021ff  push    0; dwMilliseconds
0x10002201  push    0; bWaitAll
0x10002203  lea     eax, _g_hWaitHandles[edx*4]
0x1000220a  push    eax; lpHandles
0x1000220b  push    [ebp+ulMinuend]; nCount
0x1000220e  call    ds:__imp__WaitForMultipleObjectsEx@20; WaitForMultipleObjectsEx(x,x,x,x,x)
0x10002214  mov     _g_traceTime, edi
0x1000221a  cmp     eax, 102h
0x1000221f  jz      short loc_10002258
0x10002221  mov     _g_traceTime, edi
0x10002227  lea     ecx, [ebx+224h]
0x1000222d  lea     edi, [ebx+134h]
0x10002233  mov     _g_posLast, 3
0x1000223d  cmp     edi, ecx
0x1000223f  jnb     short loc_1000224E
0x10002241  mov     edx, [edi]
0x10002243  test    edx, edx
0x10002245  jnz     short loc_1000227D
0x10002247  add     edi, 4
0x1000224a  cmp     edi, ecx
0x1000224c  jb      short loc_10002241
0x1000224e  xor     eax, eax
0x10002250  test    eax, eax
0x10002252  jnz     loc_1000541E
0x10002258  test    esi, esi
0x1000225a  jnz     short loc_10002267
0x1000225c  xor     eax, eax
0x1000225e  pop     edi
0x1000225f  pop     esi
0x10002260  pop     ebx
0x10002261  mov     esp, ebp
0x10002263  pop     ebp
0x10002264  retn    4
0x10002267  cmp     [ebp+var_4], 0
0x1000226b  jnz     short loc_1000225C
0x1000226d  push    ebx; lpCriticalSection
0x1000226e  mov     dword ptr [ebx+18h], 0
0x10002275  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1000227b  jmp     short loc_1000225C
0x1000227d  test    byte ptr [edx+20h], 1
0x10002281  jnz     short loc_10002292
0x10002283  push    0
0x10002285  mov     ecx, ebx
0x10002287  call    _TraceEnableClientA@12; TraceEnableClientA(x,x,x)
0x1000228c  lea     ecx, [ebx+224h]
0x10002292  mov     edx, [edi]
0x10002294  mov     eax, [edx+20h]
0x10002297  test    al, 6
0x10002299  jnz     loc_10005414
0x1000229f  test    al, 8
0x100022a1  jz      short loc_10002247
0x100022a3  mov     eax, [edx+410h]
0x100022a9  mov     edx, _g_posLast
0x100022af  inc     _g_posLast
0x100022b5  mov     _g_hWaitHandles[edx*4], eax
0x100022bc  jmp     short loc_10002247
0x100053ce  call    _TraceCreateServer@4; TraceCreateServer(x)
0x100053d3  mov     ebx, eax
0x100053d5  test    ebx, ebx
0x100053d7  jnz     loc_10002192
0x100053dd  or      eax, 0FFFFFFFFh
0x100053e0  jmp     loc_1000225E
0x100053e5  mov     ecx, edi
0x100053e7  mov     _g_traceTime, ecx
0x100053ed  jmp     loc_100021AA
0x100053f2  test    esi, esi
0x100053f4  jz      short loc_1000540A
0x100053f6  cmp     [ebp+var_4], 0
0x100053fa  jnz     short loc_1000540A
0x100053fc  push    ebx; lpCriticalSection
0x100053fd  mov     dword ptr [ebx+18h], 0
0x10005404  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1000540a  mov     eax, 6Fh ; 'o'
0x1000540f  jmp     loc_1000225E
0x10005414  mov     eax, 1
0x10005419  jmp     loc_10002250
0x1000541e  test    esi, esi
0x10005420  jnz     short loc_1000542E
0x10005422  mov     ecx, ebx; lpCriticalSection
0x10005424  call    _AcquireWriteLock@4; AcquireWriteLock(x)
0x10005429  mov     esi, 1
0x1000542e  cmp     _g_serverThread, 0
0x10005435  jnz     short loc_10005490
0x10005437  call    _IncrementModuleReference@0; IncrementModuleReference()
0x1000543c  mov     _g_moduleRef, eax
0x10005441  test    eax, eax
0x10005443  jnz     short loc_1000544C
0x10005445  mov     edi, 3EBh
0x1000544a  jmp     short loc_1000548A
0x1000544c  lea     eax, [ebp+ThreadId]
0x1000544f  push    eax; lpThreadId
0x10005450  push    0; dwCreationFlags
0x10005452  push    ebx; lpParameter
0x10005453  push    offset _TraceServerThread@4; lpStartAddress
0x10005458  push    0; dwStackSize
0x1000545a  push    0; lpThreadAttributes
0x1000545c  call    ds:__imp__CreateThread@24; CreateThread(x,x,x,x,x,x)
0x10005462  mov     _g_serverThread, eax
0x10005467  test    eax, eax
0x10005469  jnz     short loc_10005481
0x1000546b  call    ds:__imp__GetLastError@0; GetLastError()
0x10005471  push    _g_moduleRef; hLibModule
0x10005477  mov     edi, eax
0x10005479  call    ds:__imp__FreeLibrary@4; FreeLibrary(x)
0x1000547f  jmp     short loc_1000548A
0x10005481  push    eax; hObject
0x10005482  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x10005488  xor     edi, edi
0x1000548a  test    esi, esi
0x1000548c  jnz     short loc_10005492
0x1000548e  jmp     short loc_100054A6
0x10005490  xor     edi, edi
0x10005492  cmp     [ebp+var_4], 0
0x10005496  jnz     short loc_100054A6
0x10005498  push    ebx; lpCriticalSection
0x10005499  mov     dword ptr [ebx+18h], 0
0x100054a0  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x100054a6  mov     eax, edi
0x100054a8  jmp     loc_1000225E
```
