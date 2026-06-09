# InitializeTaskThreadState(void)

- ea: `0x180016030`
- end: `0x1800161b6`
- name: `?InitializeTaskThreadState@@YAPEAVCTaskThreadState@@XZ`
- size: `390`
- prototype: `struct CTaskThreadState *(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180015a30`

## callees

- `0x180016030`
- `0x180034260`
- `0x18008172c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001605f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800160e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001605f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800160e5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016189`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016189`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180016153`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180016153`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180016044`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180016044`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800160d1`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800160d1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001619d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001619d`

## string_xrefs

- `0x1800160b0`: `onecore\com\combase\rpcss\objex\worker.cxx`
- `0x180016136`: `onecore\com\combase\rpcss\objex\worker.cxx`
- `0x18001609b`: `InitializeTaskThreadState`
- `0x180016121`: `InitializeTaskThreadState`

## pseudocode

```c
struct CTaskThreadState *InitializeTaskThreadState(void)
{
  HANDLE EventW; // rsi
  signed int LastError; // eax
  signed int v2; // ebx
  struct _TP_TIMER *ThreadpoolTimer; // rdi
  signed int v4; // eax
  signed int v5; // ebx
  struct CTaskThreadState *result; // rax
  __int64 v7; // [rsp+28h] [rbp-30h]

  EventW = CreateEventW(0, 0, 0, 0);
  if ( EventW )
    goto LABEL_9;
  LastError = GetLastError();
  v2 = LastError;
  if ( LastError > 0 )
    v2 = (unsigned __int16)LastError | 0x80070000;
  if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
    ComTraceMessageT<long>(
      (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\worker.cxx",
      (unsigned int)"InitializeTaskThreadState",
      780,
      0,
      (__int64)L"%!HRESULT!",
      v2);
  if ( v2 >= 0 )
  {
LABEL_9:
    ThreadpoolTimer = CreateThreadpoolTimer(TaskOrWorkerThreadTimerCallback, EventW, 0);
    if ( ThreadpoolTimer )
      goto LABEL_26;
    v4 = GetLastError();
    v5 = v4;
    if ( v4 > 0 )
      v5 = (unsigned __int16)v4 | 0x80070000;
    if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
    {
      LODWORD(v7) = v5;
      ComTraceMessageT<long>(
        (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\worker.cxx",
        (unsigned int)"InitializeTaskThreadState",
        788,
        0,
        (__int64)L"%!HRESULT!",
        v7);
    }
    if ( v5 >= 0 )
    {
LABEL_26:
      result = (struct CTaskThreadState *)HeapAlloc(g_hHeap, 0, 0x28u);
      if ( result )
      {
        *(_QWORD *)result = 0;
        *((_QWORD *)result + 1) = 0;
        *((_BYTE *)result + 16) = 0;
        *((_QWORD *)result + 3) = ThreadpoolTimer;
        *((_QWORD *)result + 4) = EventW;
        return result;
      }
    }
    if ( EventW )
      CloseHandle(EventW);
    if ( ThreadpoolTimer )
      CloseThreadpoolTimer(ThreadpoolTimer);
  }
  return 0;
}

```

## disassembly

```asm
0x180016030  push    rbx
0x180016032  push    rsi
0x180016033  push    rdi
0x180016034  push    r15
0x180016036  sub     rsp, 38h
0x18001603a  xor     r9d, r9d; lpName
0x18001603d  xor     r8d, r8d; bInitialState
0x180016040  xor     edx, edx; bManualReset
0x180016042  xor     ecx, ecx; lpEventAttributes
0x180016044  call    cs:__imp_CreateEventW
0x18001604b  nop     dword ptr [rax+rax+00h]
0x180016050  lea     r15, aHresult; "%!HRESULT!"
0x180016057  mov     rsi, rax
0x18001605a  test    rax, rax
0x18001605d  jnz     short loc_1800160C4
0x18001605f  call    cs:__imp_GetLastError
0x180016066  nop     dword ptr [rax+rax+00h]
0x18001606b  mov     ebx, eax
0x18001606d  test    eax, eax
0x18001606f  jle     short loc_18001607A
0x180016071  movzx   ebx, ax
0x180016074  or      ebx, 80070000h
0x18001607a  mov     eax, cs:dword_1801574B8
0x180016080  test    eax, eax
0x180016082  jnz     short loc_180016097
0x180016084  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x18001608a  jz      short loc_1800160BC
0x18001608c  xor     ecx, ecx
0x18001608e  call    IsWppLevelEnabled
0x180016093  test    al, al
0x180016095  jz      short loc_1800160BC
0x180016097  mov     dword ptr [rsp+58h+var_30], ebx
0x18001609b  lea     rdx, aInitializetask; "InitializeTaskThreadState"
0x1800160a2  xor     r9d, r9d
0x1800160a5  mov     [rsp+58h+var_38], r15
0x1800160aa  mov     r8d, 30Ch
0x1800160b0  lea     rcx, aOnecoreComComb_113; "onecore\\com\\combase\\rpcss\\objex\\wo"...
0x1800160b7  call    ??$ComTraceMessageT@J@@YAXPEBD0HW4TraceLevel@@PEBGJ@Z; ComTraceMessageT<long>(char const *,char const *,int,TraceLevel,ushort const *,long)
0x1800160bc  test    ebx, ebx
0x1800160be  js      loc_1800161A9
0x1800160c4  xor     r8d, r8d; pcbe
0x1800160c7  lea     rcx, ?TaskOrWorkerThreadTimerCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800160ce  mov     rdx, rsi; pv
0x1800160d1  call    cs:__imp_CreateThreadpoolTimer
0x1800160d8  nop     dword ptr [rax+rax+00h]
0x1800160dd  mov     rdi, rax
0x1800160e0  test    rax, rax
0x1800160e3  jnz     short loc_180016146
0x1800160e5  call    cs:__imp_GetLastError
0x1800160ec  nop     dword ptr [rax+rax+00h]
0x1800160f1  mov     ebx, eax
0x1800160f3  test    eax, eax
0x1800160f5  jle     short loc_180016100
0x1800160f7  movzx   ebx, ax
0x1800160fa  or      ebx, 80070000h
0x180016100  mov     eax, cs:dword_1801574B8
0x180016106  test    eax, eax
0x180016108  jnz     short loc_18001611D
0x18001610a  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x180016110  jz      short loc_180016142
0x180016112  xor     ecx, ecx
0x180016114  call    IsWppLevelEnabled
0x180016119  test    al, al
0x18001611b  jz      short loc_180016142
0x18001611d  mov     dword ptr [rsp+58h+var_30], ebx
0x180016121  lea     rdx, aInitializetask; "InitializeTaskThreadState"
0x180016128  xor     r9d, r9d
0x18001612b  mov     [rsp+58h+var_38], r15
0x180016130  mov     r8d, 314h
0x180016136  lea     rcx, aOnecoreComComb_113; "onecore\\com\\combase\\rpcss\\objex\\wo"...
0x18001613d  call    ??$ComTraceMessageT@J@@YAXPEBD0HW4TraceLevel@@PEBGJ@Z; ComTraceMessageT<long>(char const *,char const *,int,TraceLevel,ushort const *,long)
0x180016142  test    ebx, ebx
0x180016144  js      short loc_180016181
0x180016146  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x18001614d  xor     edx, edx; dwFlags
0x18001614f  lea     r8d, [rdx+28h]; dwBytes
0x180016153  call    cs:__imp_HeapAlloc
0x18001615a  nop     dword ptr [rax+rax+00h]
0x18001615f  test    rax, rax
0x180016162  jz      short loc_180016181
0x180016164  mov     qword ptr [rax], 0
0x18001616b  mov     qword ptr [rax+8], 0
0x180016173  mov     byte ptr [rax+10h], 0
0x180016177  mov     [rax+18h], rdi
0x18001617b  mov     [rax+20h], rsi
0x18001617f  jmp     short loc_1800161AB
0x180016181  test    rsi, rsi
0x180016184  jz      short loc_180016195
0x180016186  mov     rcx, rsi; hObject
0x180016189  call    cs:__imp_CloseHandle
0x180016190  nop     dword ptr [rax+rax+00h]
0x180016195  test    rdi, rdi
0x180016198  jz      short loc_1800161A9
0x18001619a  mov     rcx, rdi; pti
0x18001619d  call    cs:__imp_CloseThreadpoolTimer
0x1800161a4  nop     dword ptr [rax+rax+00h]
0x1800161a9  xor     eax, eax
0x1800161ab  add     rsp, 38h
0x1800161af  pop     r15
0x1800161b1  pop     rdi
0x1800161b2  pop     rsi
0x1800161b3  pop     rbx
0x1800161b4  retn
```
