# SM_WORKER::~SM_WORKER(void)

- ea: `0x140002074`
- end: `0x14000221c`
- name: `??1SM_WORKER@@QEAA@XZ`
- size: `424`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1400037dc`

## callees

- `0x140001008`
- `0x140002074`
- `0x14000374c`
- `0x14000a3b8`
- `0x14000d1be`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1400020d6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1400020d6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x14000218b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x14000218b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x1400020cc`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x1400020cc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000210e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000210e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002150`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002150`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1400021ce`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1400021ce`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400020dc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400020dc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140002136`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140002136`

## pseudocode

```c
void __fastcall SM_WORKER::~SM_WORKER(LPCRITICAL_SECTION lpCriticalSection, __int64 a2, __int64 a3, __int64 a4)
{
  struct _TP_WORK *OwningThread; // rcx
  signed __int64 CurrentThreadId; // rcx
  const char *v7; // rbx
  char LastError; // al
  int v9; // ecx
  int v10; // r8d
  int v11; // r9d
  __int64 v12; // rcx
  __int64 v13; // r8
  __int64 v14; // r9
  int v15; // [rsp+50h] [rbp+8h] BYREF
  const char *v16; // [rsp+58h] [rbp+10h] BYREF

  if ( (unsigned int)dword_140014048 > 5 )
  {
    v15 = 141;
    v16 = "SM_WORKER::~SM_WORKER";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (__int64)lpCriticalSection,
      (__int64)word_1400109C2,
      a3,
      a4,
      (const unsigned __int16 **)&v16,
      (__int64)&v15);
  }
  OwningThread = (struct _TP_WORK *)lpCriticalSection[1].OwningThread;
  if ( OwningThread )
  {
    WaitForThreadpoolWorkCallbacks(OwningThread, 0);
    CloseThreadpoolWork((PTP_WORK)lpCriticalSection[1].OwningThread);
  }
  CurrentThreadId = GetCurrentThreadId();
  while ( _InterlockedCompareExchange64((volatile signed __int64 *)&Lock, CurrentThreadId, 0) )
  {
    do
      _mm_pause();
    while ( Lock );
  }
  if ( ReferenceCount )
  {
    if ( ReferenceCount != 1 )
    {
      --ReferenceCount;
      goto LABEL_17;
    }
    if ( CloseHandle(Spaceport) )
    {
      Spaceport = (HANDLE)-1LL;
      CloseThreadpool(Threadpool);
      Threadpool = 0;
      memset_0(&ModuleName, 0, 0x208u);
      McGenEventUnregister_EventUnregister(SpaceApiProvider_Context);
      --ReferenceCount;
      goto LABEL_17;
    }
    v7 = "CloseHandle";
  }
  else
  {
    SetLastError(6u);
    v7 = "ReferenceCount == 0";
  }
  if ( (Microsoft_Windows_StorageSpaces_ApiEnableBits & 1) != 0 )
  {
    LastError = GetLastError();
    McTemplateK0zssq_EventWriteTransfer(
      v9,
      (unsigned int)CleanupApiFailed,
      v10,
      v11,
      (__int64)"SuCleanup",
      (__int64)v7,
      LastError);
  }
LABEL_17:
  _InterlockedExchange64((volatile __int64 *)&Lock, 0);
  DeleteCriticalSection(lpCriticalSection);
  if ( (unsigned int)dword_140014048 > 5 )
  {
    v15 = 154;
    v16 = "SM_WORKER::~SM_WORKER";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v12,
      (__int64)&word_140010786,
      v13,
      v14,
      (const unsigned __int16 **)&v16,
      (__int64)&v15);
  }
}

```

## disassembly

```asm
0x140002074  mov     r11, rsp
0x140002077  mov     [r11+18h], rbx
0x14000207b  mov     [r11+20h], rsi
0x14000207f  push    rdi
0x140002080  sub     rsp, 40h
0x140002084  mov     eax, cs:dword_140014048
0x14000208a  lea     rsi, aSmWorkerSmWork_0; "SM_WORKER::~SM_WORKER"
0x140002091  mov     rdi, rcx
0x140002094  cmp     eax, 5
0x140002097  jbe     short loc_1400020C1
0x140002099  lea     rax, [r11+8]
0x14000209d  mov     [rsp+48h+arg_0], 8Dh
0x1400020a5  mov     [r11-20h], rax
0x1400020a9  lea     rdx, word_1400109C2
0x1400020b0  lea     rax, [r11+10h]
0x1400020b4  mov     [r11+10h], rsi
0x1400020b8  mov     [r11-28h], rax
0x1400020bc  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1400020c1  mov     rcx, [rdi+38h]; pwk
0x1400020c5  test    rcx, rcx
0x1400020c8  jz      short loc_1400020DC
0x1400020ca  xor     edx, edx; fCancelPendingCallbacks
0x1400020cc  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x1400020d2  mov     rcx, [rdi+38h]; pwk
0x1400020d6  call    cs:__imp_CloseThreadpoolWork
0x1400020dc  call    cs:__imp_GetCurrentThreadId
0x1400020e2  mov     ecx, eax
0x1400020e4  jmp     short loc_1400020F4
0x1400020e6  pause
0x1400020e8  mov     rax, cs:?Lock@@3PEAXEA; void * Lock
0x1400020ef  test    rax, rax
0x1400020f2  jnz     short loc_1400020E6
0x1400020f4  xor     eax, eax
0x1400020f6  lock cmpxchg cs:?Lock@@3PEAXEA, rcx; void * Lock
0x1400020ff  jnz     short loc_1400020E6
0x140002101  mov     eax, cs:?ReferenceCount@@3KA; ulong ReferenceCount
0x140002107  test    eax, eax
0x140002109  jnz     short loc_14000211D
0x14000210b  lea     ecx, [rax+6]; dwErrCode
0x14000210e  call    cs:__imp_SetLastError
0x140002114  lea     rbx, aReferencecount; "ReferenceCount == 0"
0x14000211b  jmp     short loc_140002147
0x14000211d  cmp     eax, 1
0x140002120  jz      short loc_14000212F
0x140002122  dec     eax
0x140002124  mov     cs:?ReferenceCount@@3KA, eax; ulong ReferenceCount
0x14000212a  jmp     loc_1400021C2
0x14000212f  mov     rcx, cs:?Spaceport@@3PEAXEA; hObject
0x140002136  call    cs:__imp_CloseHandle
0x14000213c  test    eax, eax
0x14000213e  jnz     short loc_140002179
0x140002140  lea     rbx, aClosehandle; "CloseHandle"
0x140002147  test    cs:Microsoft_Windows_StorageSpaces_ApiEnableBits, 1
0x14000214e  jz      short loc_1400021C2
0x140002150  call    cs:__imp_GetLastError
0x140002156  mov     [rsp+48h+var_18], eax
0x14000215a  lea     rdx, CleanupApiFailed
0x140002161  lea     rax, aSucleanup; "SuCleanup"
0x140002168  mov     [rsp+48h+var_20], rbx
0x14000216d  mov     [rsp+48h+var_28], rax
0x140002172  call    McTemplateK0zssq_EventWriteTransfer
0x140002177  jmp     short loc_1400021C2
0x140002179  mov     rcx, cs:?Threadpool@@3PEAU_TP_POOL@@EA; ptpp
0x140002180  mov     cs:?Spaceport@@3PEAXEA, 0FFFFFFFFFFFFFFFFh; void * Spaceport
0x14000218b  call    cs:__imp_CloseThreadpool
0x140002191  xor     edx, edx; Val
0x140002193  mov     cs:?Threadpool@@3PEAU_TP_POOL@@EA, 0; _TP_POOL * Threadpool
0x14000219e  mov     r8d, 208h; Size
0x1400021a4  lea     rcx, ?ModuleName@@3PAGA; void *
0x1400021ab  call    memset_0
0x1400021b0  lea     rcx, SpaceApiProvider_Context
0x1400021b7  call    McGenEventUnregister_EventUnregister
0x1400021bc  dec     cs:?ReferenceCount@@3KA; ulong ReferenceCount
0x1400021c2  xor     eax, eax
0x1400021c4  mov     rcx, rdi; lpCriticalSection
0x1400021c7  xchg    rax, cs:?Lock@@3PEAXEA; void * Lock
0x1400021ce  call    cs:__imp_DeleteCriticalSection
0x1400021d4  mov     eax, cs:dword_140014048
0x1400021da  cmp     eax, 5
0x1400021dd  jbe     short loc_14000220C
0x1400021df  lea     rax, [rsp+48h+arg_0]
0x1400021e4  mov     [rsp+48h+arg_0], 9Ah
0x1400021ec  mov     [rsp+48h+var_20], rax
0x1400021f1  lea     rdx, word_140010786
0x1400021f8  lea     rax, [rsp+48h+arg_8]
0x1400021fd  mov     [rsp+48h+arg_8], rsi
0x140002202  mov     [rsp+48h+var_28], rax
0x140002207  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x14000220c  mov     rbx, [rsp+48h+arg_10]
0x140002211  mov     rsi, [rsp+48h+arg_18]
0x140002216  add     rsp, 40h
0x14000221a  pop     rdi
0x14000221b  retn
```
