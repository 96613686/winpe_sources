# InitializeTaskThreadState(void)

- ea: `0x180012038`
- end: `0x180012193`
- name: `?InitializeTaskThreadState@@YAPEAVCTaskThreadState@@XZ`
- size: `347`
- prototype: `struct CTaskThreadState *(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180011a70`

## callees

- `0x180012038`
- `0x180034540`
- `0x18007e3d4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012061`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800120db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012061`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800120db`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012173`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012173`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180012143`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180012143`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001204c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001204c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800120cd`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800120cd`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180012181`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180012181`

## string_xrefs

- `0x1800120ac`: `onecore\com\combase\rpcss\objex\worker.cxx`
- `0x180012126`: `onecore\com\combase\rpcss\objex\worker.cxx`
- `0x180012097`: `InitializeTaskThreadState`
- `0x180012111`: `InitializeTaskThreadState`

## pseudocode

```c
struct CTaskThreadState *InitializeTaskThreadState(void)
{
  HANDLE EventW; // rsi
  signed int LastError; // eax
  int v2; // ebx
  struct _TP_TIMER *ThreadpoolTimer; // rdi
  signed int v4; // eax
  int v5; // ebx
  struct CTaskThreadState *result; // rax

  EventW = CreateEventW(0, 0, 0, 0);
  if ( EventW )
    goto LABEL_9;
  LastError = GetLastError();
  v2 = LastError;
  if ( LastError > 0 )
    v2 = (unsigned __int16)LastError | 0x80070000;
  if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
    ComTraceMessageT<long>(
      (__int64)"onecore\\com\\combase\\rpcss\\objex\\worker.cxx",
      (__int64)"InitializeTaskThreadState",
      0x30Cu,
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
    if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
      ComTraceMessageT<long>(
        (__int64)"onecore\\com\\combase\\rpcss\\objex\\worker.cxx",
        (__int64)"InitializeTaskThreadState",
        0x314u,
        0,
        (__int64)L"%!HRESULT!",
        v5);
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
0x180012038  push    rbx
0x18001203a  push    rsi
0x18001203b  push    rdi
0x18001203c  push    r15
0x18001203e  sub     rsp, 38h
0x180012042  xor     r9d, r9d; lpName
0x180012045  xor     r8d, r8d; bInitialState
0x180012048  xor     edx, edx; bManualReset
0x18001204a  xor     ecx, ecx; lpEventAttributes
0x18001204c  call    cs:__imp_CreateEventW
0x180012052  lea     r15, aHresult; "%!HRESULT!"
0x180012059  mov     rsi, rax
0x18001205c  test    rax, rax
0x18001205f  jnz     short loc_1800120C0
0x180012061  call    cs:__imp_GetLastError
0x180012067  mov     ebx, eax
0x180012069  test    eax, eax
0x18001206b  jle     short loc_180012076
0x18001206d  movzx   ebx, ax
0x180012070  or      ebx, 80070000h
0x180012076  mov     eax, cs:dword_18014E4B8
0x18001207c  test    eax, eax
0x18001207e  jnz     short loc_180012093
0x180012080  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x180012086  jz      short loc_1800120B8
0x180012088  xor     ecx, ecx
0x18001208a  call    IsWppLevelEnabled
0x18001208f  test    al, al
0x180012091  jz      short loc_1800120B8
0x180012093  mov     [rsp+58h+var_30], ebx
0x180012097  lea     rdx, aInitializetask; "InitializeTaskThreadState"
0x18001209e  xor     r9d, r9d
0x1800120a1  mov     [rsp+58h+var_38], r15
0x1800120a6  mov     r8d, 30Ch
0x1800120ac  lea     rcx, aOnecoreComComb_113; "onecore\\com\\combase\\rpcss\\objex\\wo"...
0x1800120b3  call    ??$ComTraceMessageT@J@@YAXPEBD0HW4TraceLevel@@PEBGJ@Z; ComTraceMessageT<long>(char const *,char const *,int,TraceLevel,ushort const *,long)
0x1800120b8  test    ebx, ebx
0x1800120ba  js      loc_180012187
0x1800120c0  xor     r8d, r8d; pcbe
0x1800120c3  lea     rcx, ?TaskOrWorkerThreadTimerCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800120ca  mov     rdx, rsi; pv
0x1800120cd  call    cs:__imp_CreateThreadpoolTimer
0x1800120d3  mov     rdi, rax
0x1800120d6  test    rax, rax
0x1800120d9  jnz     short loc_180012136
0x1800120db  call    cs:__imp_GetLastError
0x1800120e1  mov     ebx, eax
0x1800120e3  test    eax, eax
0x1800120e5  jle     short loc_1800120F0
0x1800120e7  movzx   ebx, ax
0x1800120ea  or      ebx, 80070000h
0x1800120f0  mov     eax, cs:dword_18014E4B8
0x1800120f6  test    eax, eax
0x1800120f8  jnz     short loc_18001210D
0x1800120fa  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x180012100  jz      short loc_180012132
0x180012102  xor     ecx, ecx
0x180012104  call    IsWppLevelEnabled
0x180012109  test    al, al
0x18001210b  jz      short loc_180012132
0x18001210d  mov     [rsp+58h+var_30], ebx
0x180012111  lea     rdx, aInitializetask; "InitializeTaskThreadState"
0x180012118  xor     r9d, r9d
0x18001211b  mov     [rsp+58h+var_38], r15
0x180012120  mov     r8d, 314h
0x180012126  lea     rcx, aOnecoreComComb_113; "onecore\\com\\combase\\rpcss\\objex\\wo"...
0x18001212d  call    ??$ComTraceMessageT@J@@YAXPEBD0HW4TraceLevel@@PEBGJ@Z; ComTraceMessageT<long>(char const *,char const *,int,TraceLevel,ushort const *,long)
0x180012132  test    ebx, ebx
0x180012134  js      short loc_18001216B
0x180012136  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x18001213d  xor     edx, edx; dwFlags
0x18001213f  lea     r8d, [rdx+28h]; dwBytes
0x180012143  call    cs:__imp_HeapAlloc
0x180012149  test    rax, rax
0x18001214c  jz      short loc_18001216B
0x18001214e  mov     qword ptr [rax], 0
0x180012155  mov     qword ptr [rax+8], 0
0x18001215d  mov     byte ptr [rax+10h], 0
0x180012161  mov     [rax+18h], rdi
0x180012165  mov     [rax+20h], rsi
0x180012169  jmp     short loc_180012189
0x18001216b  test    rsi, rsi
0x18001216e  jz      short loc_180012179
0x180012170  mov     rcx, rsi; hObject
0x180012173  call    cs:__imp_CloseHandle
0x180012179  test    rdi, rdi
0x18001217c  jz      short loc_180012187
0x18001217e  mov     rcx, rdi; pti
0x180012181  call    cs:__imp_CloseThreadpoolTimer
0x180012187  xor     eax, eax
0x180012189  add     rsp, 38h
0x18001218d  pop     r15
0x18001218f  pop     rdi
0x180012190  pop     rsi
0x180012191  pop     rbx
0x180012192  retn
```
