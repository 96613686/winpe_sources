# SuInitialize(void)

- ea: `0x140009328`
- end: `0x1400095b5`
- name: `?SuInitialize@@YAHXZ`
- size: `653`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x140002524`

## callees

- `0x140003728`
- `0x14000374c`
- `0x140009328`
- `0x14000a3b8`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x14000942b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x14000942b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x140009530`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x140009530`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x140009463`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x140009463`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x140009451`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x140009451`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140009400`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140009400`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400093ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140009546`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400093ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140009546`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1400093cb`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1400093cb`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1400093f8`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140009597`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1400093f8`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140009597`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x140009423`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x140009423`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140009344`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140009344`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140009505`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140009505`

## string_xrefs

- `0x14000943d`: `CreateThreadpool`
- `0x140009476`: `SetThreadpoolThreadMinimum`
- `0x14000951f`: `CreateFile`

## pseudocode

```c
__int64 SuInitialize(void)
{
  __int64 v0; // rdx
  signed __int64 CurrentThreadId; // rcx
  unsigned int v2; // ebx
  BOOL ModuleHandle; // r15d
  struct _TP_POOL *Threadpool; // rax
  const char *v5; // rsi
  char LastError; // al
  int v7; // ecx
  int v8; // r8d
  int v9; // r9d
  HMODULE phModule; // [rsp+48h] [rbp-30h] BYREF
  char v12; // [rsp+50h] [rbp-28h]
  HMODULE hModule; // [rsp+80h] [rbp+8h]

  hModule = 0;
  CurrentThreadId = GetCurrentThreadId();
  while ( _InterlockedCompareExchange64((volatile signed __int64 *)&Lock, CurrentThreadId, 0) )
  {
    do
      _mm_pause();
    while ( Lock );
  }
  if ( ReferenceCount )
  {
    v2 = 1;
    ++ReferenceCount;
    goto LABEL_22;
  }
  McGenEventRegister_EventRegister(SpaceApiProvider, v0, SpaceApiProvider_Context, SpaceApiProvider_Context);
  phModule = 0;
  v12 = 1;
  ModuleHandle = GetModuleHandleExW(4u, (LPCWSTR)&Spaceport, &phModule);
  if ( v12 )
    hModule = phModule;
  if ( ModuleHandle )
    GetModuleFileNameW(hModule, &ModuleName, 0x104u);
  Threadpool = CreateThreadpool(0);
  ::Threadpool = Threadpool;
  if ( Threadpool )
  {
    SetThreadpoolThreadMaximum(Threadpool, 0x80u);
    v2 = SetThreadpoolThreadMinimum(::Threadpool, 1u);
    Threadpool = ::Threadpool;
    if ( v2 )
    {
      ThreadpoolEnv.Version = 3;
      *(_OWORD *)&ThreadpoolEnv.RaceDll = 0;
      ThreadpoolEnv.CleanupGroup = 0;
      ThreadpoolEnv.CleanupGroupCancelCallback = 0;
      ThreadpoolEnv.FinalizationCallback = 0;
      ThreadpoolEnv.u.Flags = 0;
      ThreadpoolEnv.CallbackPriority = TP_CALLBACK_PRIORITY_NORMAL;
      ThreadpoolEnv.Size = 72;
      ThreadpoolEnv.Pool = ::Threadpool;
      Spaceport = CreateFileW(L"\\\\.\\Spaceport", 0xC0000000, 3u, 0, 3u, 0x40000000u, 0);
      if ( Spaceport != (HANDLE)-1LL )
      {
        ++ReferenceCount;
        goto LABEL_22;
      }
      Threadpool = ::Threadpool;
      v5 = "CreateFile";
    }
    else
    {
      v5 = "SetThreadpoolThreadMinimum";
    }
  }
  else
  {
    v5 = "CreateThreadpool";
  }
  v2 = 0;
  if ( Threadpool )
  {
    CloseThreadpool(Threadpool);
    ::Threadpool = 0;
  }
  if ( (Microsoft_Windows_StorageSpaces_ApiEnableBits & 1) != 0 )
  {
    LastError = GetLastError();
    McTemplateK0zssq_EventWriteTransfer(
      v7,
      (unsigned int)InitializeApiFailed,
      v8,
      v9,
      (__int64)"SuInitialize",
      (__int64)v5,
      LastError);
  }
  McGenEventUnregister_EventUnregister(SpaceApiProvider_Context);
LABEL_22:
  _InterlockedExchange64((volatile __int64 *)&Lock, 0);
  if ( hModule )
    FreeLibrary(hModule);
  return v2;
}

```

## disassembly

```asm
0x140009328  mov     rax, rsp
0x14000932b  mov     [rax+18h], rbx
0x14000932f  mov     [rax+20h], rbp
0x140009333  push    rsi
0x140009334  push    r14
0x140009336  push    r15
0x140009338  sub     rsp, 60h
0x14000933c  mov     qword ptr [rax+8], 0
0x140009344  call    cs:__imp_GetCurrentThreadId
0x14000934a  mov     ecx, eax
0x14000934c  jmp     short loc_14000935C
0x14000934e  pause
0x140009350  mov     rax, cs:?Lock@@3PEAXEA; void * Lock
0x140009357  test    rax, rax
0x14000935a  jnz     short loc_14000934E
0x14000935c  xor     eax, eax
0x14000935e  lock cmpxchg cs:?Lock@@3PEAXEA, rcx; void * Lock
0x140009367  jnz     short loc_14000934E
0x140009369  mov     eax, cs:?ReferenceCount@@3KA; ulong ReferenceCount
0x14000936f  test    eax, eax
0x140009371  jz      short loc_140009385
0x140009373  inc     eax
0x140009375  mov     ebx, 1
0x14000937a  mov     cs:?ReferenceCount@@3KA, eax; ulong ReferenceCount
0x140009380  jmp     loc_140009581
0x140009385  lea     r9, SpaceApiProvider_Context
0x14000938c  lea     r8, SpaceApiProvider_Context
0x140009393  lea     rcx, SpaceApiProvider
0x14000939a  call    McGenEventRegister_EventRegister
0x14000939f  lea     rax, [rsp+78h+hModule]
0x1400093a7  mov     [rsp+78h+phModule], 0
0x1400093b0  lea     r8, [rsp+78h+phModule]; phModule
0x1400093b5  mov     [rsp+78h+var_38], rax
0x1400093ba  lea     rdx, ?Spaceport@@3PEAXEA; lpModuleName
0x1400093c1  mov     [rsp+78h+var_28], 1
0x1400093c6  mov     ecx, 4; dwFlags
0x1400093cb  call    cs:__imp_GetModuleHandleExW
0x1400093d1  cmp     [rsp+78h+var_28], 0
0x1400093d6  mov     r15d, eax
0x1400093d9  jz      short loc_140009409
0x1400093db  mov     rsi, [rsp+78h+var_38]
0x1400093e0  mov     r14, [rsp+78h+phModule]
0x1400093e5  mov     rbp, [rsi]
0x1400093e8  test    rbp, rbp
0x1400093eb  jz      short loc_140009406
0x1400093ed  call    cs:__imp_GetLastError
0x1400093f3  mov     rcx, rbp; hLibModule
0x1400093f6  mov     ebx, eax
0x1400093f8  call    cs:__imp_FreeLibrary
0x1400093fe  mov     ecx, ebx; dwErrCode
0x140009400  call    cs:__imp_SetLastError
0x140009406  mov     [rsi], r14
0x140009409  test    r15d, r15d
0x14000940c  jz      short loc_140009429
0x14000940e  mov     rcx, [rsp+78h+hModule]; hModule
0x140009416  lea     rdx, ?ModuleName@@3PAGA; lpFilename
0x14000941d  mov     r8d, 104h; nSize
0x140009423  call    cs:__imp_GetModuleFileNameW
0x140009429  xor     ecx, ecx; reserved
0x14000942b  call    cs:__imp_CreateThreadpool
0x140009431  mov     cs:?Threadpool@@3PEAU_TP_POOL@@EA, rax; _TP_POOL * Threadpool
0x140009438  test    rax, rax
0x14000943b  jnz     short loc_140009449
0x14000943d  lea     rsi, aCreatethreadpo; "CreateThreadpool"
0x140009444  jmp     loc_140009526
0x140009449  mov     edx, 80h; cthrdMost
0x14000944e  mov     rcx, rax; ptpp
0x140009451  call    cs:__imp_SetThreadpoolThreadMaximum
0x140009457  mov     rcx, cs:?Threadpool@@3PEAU_TP_POOL@@EA; ptpp
0x14000945e  mov     edx, 1; cthrdMic
0x140009463  call    cs:__imp_SetThreadpoolThreadMinimum
0x140009469  mov     ebx, eax
0x14000946b  test    eax, eax
0x14000946d  mov     rax, cs:?Threadpool@@3PEAU_TP_POOL@@EA; _TP_POOL * Threadpool
0x140009474  jnz     short loc_140009482
0x140009476  lea     rsi, aSetthreadpoolt; "SetThreadpoolThreadMinimum"
0x14000947d  jmp     loc_140009526
0x140009482  mov     r8d, 3; dwShareMode
0x140009488  mov     [rsp+78h+hTemplateFile], 0; hTemplateFile
0x140009491  xorps   xmm0, xmm0
0x140009494  mov     [rsp+78h+dwFlagsAndAttributes], 40000000h; dwFlagsAndAttributes
0x14000949c  xor     r9d, r9d; lpSecurityAttributes
0x14000949f  mov     cs:?ThreadpoolEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.Version, r8d; _TP_CALLBACK_ENVIRON_V3 ThreadpoolEnv ...
0x1400094a6  mov     edx, 0C0000000h; dwDesiredAccess
0x1400094ab  movdqa  xmmword ptr cs:?ThreadpoolEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.RaceDll, xmm0; _TP_CALLBACK_ENVIRON_V3 ThreadpoolEnv ...
0x1400094b3  lea     rcx, FileName; "\\\\.\\Spaceport"
0x1400094ba  mov     [rsp+78h+dwCreationDisposition], r8d; dwCreationDisposition
0x1400094bf  mov     cs:?ThreadpoolEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.CleanupGroup, 0; _TP_CALLBACK_ENVIRON_V3 ThreadpoolEnv ...
0x1400094ca  mov     cs:?ThreadpoolEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.CleanupGroupCancelCallback, 0; _TP_CALLBACK_ENVIRON_V3 ThreadpoolEnv ...
0x1400094d5  mov     cs:?ThreadpoolEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.FinalizationCallback, 0; _TP_CALLBACK_ENVIRON_V3 ThreadpoolEnv ...
0x1400094e0  mov     dword ptr cs:?ThreadpoolEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.u, 0; _TP_CALLBACK_ENVIRON_V3 ThreadpoolEnv ...
0x1400094ea  mov     cs:?ThreadpoolEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.CallbackPriority, 1; _TP_CALLBACK_ENVIRON_V3 ThreadpoolEnv ...
0x1400094f4  mov     cs:?ThreadpoolEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.Size, 48h ; 'H'; _TP_CALLBACK_ENVIRON_V3 ThreadpoolEnv ...
0x1400094fe  mov     cs:?ThreadpoolEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.Pool, rax; _TP_CALLBACK_ENVIRON_V3 ThreadpoolEnv ...
0x140009505  call    cs:__imp_CreateFileW
0x14000950b  mov     cs:?Spaceport@@3PEAXEA, rax; void * Spaceport
0x140009512  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140009516  jnz     short loc_14000957B
0x140009518  mov     rax, cs:?Threadpool@@3PEAU_TP_POOL@@EA; _TP_POOL * Threadpool
0x14000951f  lea     rsi, aCreatefile; "CreateFile"
0x140009526  xor     ebx, ebx
0x140009528  test    rax, rax
0x14000952b  jz      short loc_14000953D
0x14000952d  mov     rcx, rax; ptpp
0x140009530  call    cs:__imp_CloseThreadpool
0x140009536  mov     cs:?Threadpool@@3PEAU_TP_POOL@@EA, rbx; _TP_POOL * Threadpool
0x14000953d  test    cs:Microsoft_Windows_StorageSpaces_ApiEnableBits, 1
0x140009544  jz      short loc_14000956D
0x140009546  call    cs:__imp_GetLastError
0x14000954c  mov     dword ptr [rsp+78h+hTemplateFile], eax
0x140009550  lea     rdx, InitializeApiFailed
0x140009557  lea     rax, aSuinitialize; "SuInitialize"
0x14000955e  mov     qword ptr [rsp+78h+dwFlagsAndAttributes], rsi
0x140009563  mov     qword ptr [rsp+78h+dwCreationDisposition], rax
0x140009568  call    McTemplateK0zssq_EventWriteTransfer
0x14000956d  lea     rcx, SpaceApiProvider_Context
0x140009574  call    McGenEventUnregister_EventUnregister
0x140009579  jmp     short loc_140009581
0x14000957b  inc     cs:?ReferenceCount@@3KA; ulong ReferenceCount
0x140009581  xor     ecx, ecx
0x140009583  xchg    rcx, cs:?Lock@@3PEAXEA; void * Lock
0x14000958a  mov     rcx, [rsp+78h+hModule]; hLibModule
0x140009592  test    rcx, rcx
0x140009595  jz      short loc_14000959D
0x140009597  call    cs:__imp_FreeLibrary
0x14000959d  lea     r11, [rsp+78h+var_18]
0x1400095a2  mov     eax, ebx
0x1400095a4  mov     rbx, [r11+30h]
0x1400095a8  mov     rbp, [r11+38h]
0x1400095ac  mov     rsp, r11
0x1400095af  pop     r15
0x1400095b1  pop     r14
0x1400095b3  pop     rsi
0x1400095b4  retn
```
