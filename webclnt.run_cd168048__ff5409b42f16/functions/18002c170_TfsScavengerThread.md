# TfsScavengerThread

- ea: `0x18002c170`
- end: `0x18002c440`
- name: `TfsScavengerThread`
- size: `720`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18000b7dc`
- `0x18002bfa4`
- `0x18002c170`
- `0x18002c94c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c1da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c266`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c1da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c266`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c422`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c422`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002c357`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002c381`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002c3b1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002c3e1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002c3fa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002c413`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002c357`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002c381`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002c3b1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002c3e1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002c3fa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002c413`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002c2ba`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002c31e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002c344`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002c360`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002c38a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002c3ba`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002c2ba`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002c31e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002c344`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002c360`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002c38a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002c3ba`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002c301`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002c301`
- `KERNEL32!CreateWaitableTimerW` at `0x18002c1aa`
- `KERNEL32!CreateWaitableTimerW` at `0x18002c1aa`
- `KERNEL32!WaitForMultipleObjects` at `0x18002c298`
- `KERNEL32!WaitForMultipleObjects` at `0x18002c298`
- `KERNEL32!SetWaitableTimerEx` at `0x18002c242`
- `KERNEL32!SetWaitableTimerEx` at `0x18002c242`

## pseudocode

```c
__int64 __fastcall TfsScavengerThread(PVOID Parameter)
{
  HANDLE v1; // r10
  __int64 v2; // rbx
  DWORD LastError; // eax
  __int64 v4; // rbx
  DWORD v5; // eax
  DWORD v6; // r9d
  DWORD v7; // ecx
  DWORD v8; // eax
  DWORD v9; // ebx
  DWORD v10; // eax
  __int64 i; // rbx
  HANDLE Handles; // [rsp+40h] [rbp-28h] BYREF
  HANDLE hObject; // [rsp+48h] [rbp-20h]
  LARGE_INTEGER DueTime; // [rsp+78h] [rbp+10h] BYREF

  DueTime.QuadPart = 0;
  Handles = TfsShutdownEvent;
  hObject = CreateWaitableTimerW(0, 1, 0);
  v1 = hObject;
  if ( hObject )
  {
    DueTime.QuadPart = -10000000LL * (unsigned int)TfsScavengerThreadInterval;
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v2 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    LastError = GetLastError();
    WPP_SF_d(v2, 28, WPP_5f1a3cf1cc213e2c9d1db611a3b6a3c0_Traceguids, LastError);
    v1 = hObject;
  }
  while ( 1 )
  {
    if ( !v1 )
      goto LABEL_11;
    if ( !SetWaitableTimerEx(v1, &DueTime, 0, 0, 0, 0, 0x1F4u) )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v4 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        v5 = GetLastError();
        WPP_SF_d(v4, 29, WPP_5f1a3cf1cc213e2c9d1db611a3b6a3c0_Traceguids, v5);
      }
LABEL_11:
      v6 = 1000 * TfsScavengerThreadInterval;
      v7 = 1;
      goto LABEL_12;
    }
    v6 = -1;
    v7 = 2;
LABEL_12:
    v8 = WaitForMultipleObjects(v7, &Handles, 0, v6);
    v9 = v8;
    if ( !v8 )
      break;
    v10 = v8 - 1;
    if ( !v10 || v10 == 257 )
    {
      EnterCriticalSection(&TfsGlobalLock);
      if ( TfsShutdownInitiated )
      {
        v9 = 0;
LABEL_33:
        LeaveCriticalSection(&TfsGlobalLock);
        goto LABEL_35;
      }
    }
    else
    {
      EnterCriticalSection(&TfsGlobalLock);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_5f1a3cf1cc213e2c9d1db611a3b6a3c0_Traceguids, v9);
      if ( TfsShutdownInitiated )
        goto LABEL_33;
      Sleep(1000 * TfsScavengerThreadInterval);
    }
    for ( i = TfsStoreList; (__int64 *)i != &TfsStoreList; i = *(_QWORD *)i )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)(i + 56));
      TfsScavengeStoreEntries(i, 0);
      LeaveCriticalSection((LPCRITICAL_SECTION)(i + 56));
      EnterCriticalSection((LPCRITICAL_SECTION)(i + 56));
      if ( (unsigned int)TfsStoreNeedsScavenging(i, 1) )
        TfsScavengeStoreEntries(i, 1);
      LeaveCriticalSection((LPCRITICAL_SECTION)(i + 56));
      EnterCriticalSection((LPCRITICAL_SECTION)(i + 56));
      if ( (unsigned int)TfsStoreNeedsScavenging(i, 2) )
        TfsScavengeStoreEntries(i, 2);
      LeaveCriticalSection((LPCRITICAL_SECTION)(i + 56));
      EnterCriticalSection((LPCRITICAL_SECTION)(i + 56));
      if ( (unsigned int)TfsStoreNeedsScavenging(i, 3) )
        TfsScavengeStoreEntries(i, 3);
      LeaveCriticalSection((LPCRITICAL_SECTION)(i + 56));
    }
    LeaveCriticalSection(&TfsGlobalLock);
    v1 = hObject;
  }
  v9 = 0;
LABEL_35:
  CloseHandle(hObject);
  return v9;
}

```

## disassembly

```asm
0x18002c170  mov     r11, rsp
0x18002c173  mov     [r11+8], rbx
0x18002c177  mov     [r11+18h], rbp
0x18002c17b  push    rdi
0x18002c17c  push    r12
0x18002c17e  push    r13
0x18002c180  sub     rsp, 50h
0x18002c184  mov     rax, cs:TfsShutdownEvent
0x18002c18b  xor     r8d, r8d; lpTimerName
0x18002c18e  xor     ecx, ecx; lpTimerAttributes
0x18002c190  mov     qword ptr [r11-20h], 0
0x18002c198  mov     qword ptr [r11+10h], 0
0x18002c1a0  mov     [r11-28h], rax
0x18002c1a4  lea     ebp, [r8+1]
0x18002c1a8  mov     edx, ebp; bManualReset
0x18002c1aa  call    cs:__imp_CreateWaitableTimerW
0x18002c1b0  mov     [rsp+68h+hObject], rax
0x18002c1b5  mov     r10, rax
0x18002c1b8  lea     r12, WPP_GLOBAL_Control
0x18002c1bf  test    rax, rax
0x18002c1c2  jnz     short loc_18002C1FC
0x18002c1c4  mov     rbx, cs:WPP_GLOBAL_Control
0x18002c1cb  cmp     rbx, r12
0x18002c1ce  jz      short loc_18002C20E
0x18002c1d0  test    [rbx+1Ch], bpl
0x18002c1d4  jz      short loc_18002C20E
0x18002c1d6  mov     rbx, [rbx+10h]
0x18002c1da  call    cs:__imp_GetLastError
0x18002c1e0  lea     edx, [rbp+1Bh]
0x18002c1e3  mov     rcx, rbx
0x18002c1e6  mov     r9d, eax
0x18002c1e9  lea     r8, WPP_5f1a3cf1cc213e2c9d1db611a3b6a3c0_Traceguids
0x18002c1f0  call    WPP_SF_d
0x18002c1f5  mov     r10, [rsp+68h+hObject]
0x18002c1fa  jmp     short loc_18002C20E
0x18002c1fc  mov     eax, cs:TfsScavengerThreadInterval
0x18002c202  imul    rcx, rax, 0FFFFFFFFFF676980h
0x18002c209  mov     qword ptr [rsp+68h+DueTime], rcx
0x18002c20e  lea     r13, TfsStoreList
0x18002c215  test    r10, r10
0x18002c218  jz      short loc_18002C283
0x18002c21a  mov     [rsp+68h+TolerableDelay], 1F4h; TolerableDelay
0x18002c222  lea     rdx, [rsp+68h+DueTime]; lpDueTime
0x18002c227  mov     [rsp+68h+WakeContext], 0; WakeContext
0x18002c230  xor     r9d, r9d; pfnCompletionRoutine
0x18002c233  xor     r8d, r8d; lPeriod
0x18002c236  mov     [rsp+68h+lpArgToCompletionRoutine], 0; lpArgToCompletionRoutine
0x18002c23f  mov     rcx, r10; hTimer
0x18002c242  call    cs:__imp_SetWaitableTimerEx
0x18002c248  test    eax, eax
0x18002c24a  jnz     loc_18002C309
0x18002c250  mov     rbx, cs:WPP_GLOBAL_Control
0x18002c257  cmp     rbx, r12
0x18002c25a  jz      short loc_18002C283
0x18002c25c  test    [rbx+1Ch], bpl
0x18002c260  jz      short loc_18002C283
0x18002c262  mov     rbx, [rbx+10h]
0x18002c266  call    cs:__imp_GetLastError
0x18002c26c  mov     edx, 1Dh
0x18002c271  lea     r8, WPP_5f1a3cf1cc213e2c9d1db611a3b6a3c0_Traceguids
0x18002c278  mov     r9d, eax
0x18002c27b  mov     rcx, rbx
0x18002c27e  call    WPP_SF_d
0x18002c283  imul    r9d, cs:TfsScavengerThreadInterval, 3E8h; dwMilliseconds
0x18002c28e  mov     ecx, ebp; nCount
0x18002c290  xor     r8d, r8d; bWaitAll
0x18002c293  lea     rdx, [rsp+68h+Handles]; lpHandles
0x18002c298  call    cs:__imp_WaitForMultipleObjects
0x18002c29e  mov     ebx, eax
0x18002c2a0  test    eax, eax
0x18002c2a2  jz      loc_18002C41B
0x18002c2a8  sub     eax, ebp
0x18002c2aa  jz      short loc_18002C317
0x18002c2ac  cmp     eax, 101h
0x18002c2b1  jz      short loc_18002C317
0x18002c2b3  lea     rcx, TfsGlobalLock; lpCriticalSection
0x18002c2ba  call    cs:__imp_EnterCriticalSection
0x18002c2c0  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c2c7  cmp     rcx, r12
0x18002c2ca  jz      short loc_18002C2EA
0x18002c2cc  test    [rcx+1Ch], bpl
0x18002c2d0  jz      short loc_18002C2EA
0x18002c2d2  mov     rcx, [rcx+10h]
0x18002c2d6  lea     r8, WPP_5f1a3cf1cc213e2c9d1db611a3b6a3c0_Traceguids
0x18002c2dd  mov     edx, 1Eh
0x18002c2e2  mov     r9d, ebx
0x18002c2e5  call    WPP_SF_d
0x18002c2ea  cmp     cs:TfsShutdownInitiated, 0
0x18002c2f1  jnz     loc_18002C40C
0x18002c2f7  imul    ecx, cs:TfsScavengerThreadInterval, 3E8h; dwMilliseconds
0x18002c301  call    cs:__imp_Sleep
0x18002c307  jmp     short loc_18002C331
0x18002c309  or      r9d, 0FFFFFFFFh
0x18002c30d  mov     ecx, 2
0x18002c312  jmp     loc_18002C290
0x18002c317  lea     rcx, TfsGlobalLock; lpCriticalSection
0x18002c31e  call    cs:__imp_EnterCriticalSection
0x18002c324  cmp     cs:TfsShutdownInitiated, 0
0x18002c32b  jnz     loc_18002C40A
0x18002c331  mov     rbx, cs:TfsStoreList
0x18002c338  jmp     loc_18002C3EA
0x18002c33d  lea     rdi, [rbx+38h]
0x18002c341  mov     rcx, rdi; lpCriticalSection
0x18002c344  call    cs:__imp_EnterCriticalSection
0x18002c34a  xor     edx, edx
0x18002c34c  mov     rcx, rbx
0x18002c34f  call    TfsScavengeStoreEntries
0x18002c354  mov     rcx, rdi; lpCriticalSection
0x18002c357  call    cs:__imp_LeaveCriticalSection
0x18002c35d  mov     rcx, rdi; lpCriticalSection
0x18002c360  call    cs:__imp_EnterCriticalSection
0x18002c366  mov     edx, ebp
0x18002c368  mov     rcx, rbx
0x18002c36b  call    TfsStoreNeedsScavenging
0x18002c370  test    eax, eax
0x18002c372  jz      short loc_18002C37E
0x18002c374  mov     edx, ebp
0x18002c376  mov     rcx, rbx
0x18002c379  call    TfsScavengeStoreEntries
0x18002c37e  mov     rcx, rdi; lpCriticalSection
0x18002c381  call    cs:__imp_LeaveCriticalSection
0x18002c387  mov     rcx, rdi; lpCriticalSection
0x18002c38a  call    cs:__imp_EnterCriticalSection
0x18002c390  mov     edx, 2
0x18002c395  mov     rcx, rbx
0x18002c398  call    TfsStoreNeedsScavenging
0x18002c39d  test    eax, eax
0x18002c39f  jz      short loc_18002C3AE
0x18002c3a1  mov     edx, 2
0x18002c3a6  mov     rcx, rbx
0x18002c3a9  call    TfsScavengeStoreEntries
0x18002c3ae  mov     rcx, rdi; lpCriticalSection
0x18002c3b1  call    cs:__imp_LeaveCriticalSection
0x18002c3b7  mov     rcx, rdi; lpCriticalSection
0x18002c3ba  call    cs:__imp_EnterCriticalSection
0x18002c3c0  mov     edx, 3
0x18002c3c5  mov     rcx, rbx
0x18002c3c8  call    TfsStoreNeedsScavenging
0x18002c3cd  test    eax, eax
0x18002c3cf  jz      short loc_18002C3DE
0x18002c3d1  mov     edx, 3
0x18002c3d6  mov     rcx, rbx
0x18002c3d9  call    TfsScavengeStoreEntries
0x18002c3de  mov     rcx, rdi; lpCriticalSection
0x18002c3e1  call    cs:__imp_LeaveCriticalSection
0x18002c3e7  mov     rbx, [rbx]
0x18002c3ea  cmp     rbx, r13
0x18002c3ed  jnz     loc_18002C33D
0x18002c3f3  lea     rcx, TfsGlobalLock; lpCriticalSection
0x18002c3fa  call    cs:__imp_LeaveCriticalSection
0x18002c400  mov     r10, [rsp+68h+hObject]
0x18002c405  jmp     loc_18002C215
0x18002c40a  xor     ebx, ebx
0x18002c40c  lea     rcx, TfsGlobalLock; lpCriticalSection
0x18002c413  call    cs:__imp_LeaveCriticalSection
0x18002c419  jmp     short loc_18002C41D
0x18002c41b  xor     ebx, ebx
0x18002c41d  mov     rcx, [rsp+68h+hObject]; hObject
0x18002c422  call    cs:__imp_CloseHandle
0x18002c428  lea     r11, [rsp+68h+var_18]
0x18002c42d  mov     eax, ebx
0x18002c42f  mov     rbx, [r11+20h]
0x18002c433  mov     rbp, [r11+30h]
0x18002c437  mov     rsp, r11
0x18002c43a  pop     r13
0x18002c43c  pop     r12
0x18002c43e  pop     rdi
0x18002c43f  retn
```
