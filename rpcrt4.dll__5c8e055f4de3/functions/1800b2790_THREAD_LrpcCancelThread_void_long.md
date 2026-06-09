# THREAD::LrpcCancelThread(void *,long)

- ea: `0x1800b2790`
- end: `0x1800b28cb`
- name: `?LrpcCancelThread@THREAD@@SAJPEAXJ@Z`
- size: `315`
- prototype: `__int64 __fastcall(void *, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800b2970`
- `0x1800b29c0`

## callees

- `0x18002b7c0`
- `0x1800a0200`
- `0x1800b2790`
- `0x1800d2010`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x1800b2835`
- `ntdll!RtlLeaveCriticalSection` at `0x1800b2835`
- `ntdll!RtlEnterCriticalSection` at `0x1800b27ba`
- `ntdll!RtlEnterCriticalSection` at `0x1800b27ba`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x1800b279b`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x1800b279b`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x1800b28ab`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x1800b28ab`

## pseudocode

```c
__int64 __fastcall THREAD::LrpcCancelThread(void *a1, int Flink_high)
{
  DWORD ThreadId; // eax
  struct _LIST_ENTRY *v4; // rbp
  void **v6; // rbx
  struct _LIST_ENTRY *Flink; // rax
  struct _LIST_ENTRY *v8; // rdi
  signed __int64 Blink; // rbx

  ThreadId = GetThreadId(a1);
  v4 = (struct _LIST_ENTRY *)ThreadId;
  if ( !ThreadId )
    return 5;
  v6 = 0;
  RtlEnterCriticalSection(ThreadListMutex);
  Flink = ThreadListHead.Flink;
  while ( Flink != &ThreadListHead )
  {
    v8 = Flink;
    Flink = Flink->Flink;
    if ( v8[-10].Flink == v4 )
    {
      do
      {
        Blink = (signed __int64)v8[-7].Blink;
        if ( !Blink || (Blink & 3) != 2 )
        {
          v6 = 0;
          goto LABEL_12;
        }
      }
      while ( Blink != _InterlockedCompareExchange64((volatile signed __int64 *)&v8[-7].Blink, Blink | 1, Blink) );
      v6 = (void **)(Blink ^ 2);
      if ( v6 )
      {
        REFERENCED_OBJECT::AddReference((REFERENCED_OBJECT *)v6);
        _InterlockedExchange64((volatile __int64 *)&v8[-7].Blink, (__int64)v8[-7].Blink ^ 1);
      }
LABEL_12:
      if ( Flink_high == -2 )
        Flink_high = HIDWORD(v8[-11].Flink);
      break;
    }
  }
  RtlLeaveCriticalSection(ThreadListMutex);
  if ( !v6 )
    return 1725;
  if ( !Flink_high )
  {
    LRPC_BASE_CCALL::CancelAsyncCall((LRPC_BASE_CCALL *)v6, 1);
LABEL_19:
    (*((void (__fastcall **)(void **))*v6 + 4))(v6);
    return 0;
  }
  LRPC_BASE_CCALL::CancelAsyncCall((LRPC_BASE_CCALL *)v6, 0);
  if ( Flink_high == -1 )
    goto LABEL_19;
  if ( CreateTimerQueueTimer(v6 + 105, 0, LrpcSyncCancelCallback, v6, 1000 * Flink_high, 0, 0) )
    return 0;
  (*((void (__fastcall **)(void **))*v6 + 4))(v6);
  return 14;
}

```

## disassembly

```asm
0x1800b2790  push    rbx
0x1800b2792  push    rbp
0x1800b2793  push    rsi
0x1800b2794  push    rdi
0x1800b2795  sub     rsp, 48h
0x1800b2799  mov     esi, edx
0x1800b279b  call    cs:__imp_GetThreadId
0x1800b27a1  mov     ebp, eax
0x1800b27a3  test    eax, eax
0x1800b27a5  jnz     short loc_1800B27B1
0x1800b27a7  mov     eax, 5
0x1800b27ac  jmp     loc_1800B2875
0x1800b27b1  mov     rcx, cs:?ThreadListMutex@@3PEAVMUTEX@@EA; CriticalSection
0x1800b27b8  xor     ebx, ebx
0x1800b27ba  call    cs:__imp_RtlEnterCriticalSection
0x1800b27c0  mov     rax, cs:?ThreadListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY ThreadListHead
0x1800b27c7  lea     rcx, ?ThreadListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY ThreadListHead
0x1800b27ce  cmp     rax, rcx
0x1800b27d1  jz      short loc_1800B282E
0x1800b27d3  mov     rdi, rax
0x1800b27d6  mov     rax, [rax]
0x1800b27d9  cmp     [rdi-0A0h], rbp
0x1800b27e0  jnz     short loc_1800B27C7
0x1800b27e2  mov     rbx, [rdi-68h]
0x1800b27e6  test    rbx, rbx
0x1800b27e9  jz      short loc_1800B2821
0x1800b27eb  mov     al, bl
0x1800b27ed  and     al, 3
0x1800b27ef  cmp     al, 2
0x1800b27f1  jnz     short loc_1800B2821
0x1800b27f3  mov     rcx, rbx
0x1800b27f6  mov     rax, rbx
0x1800b27f9  or      rcx, 1
0x1800b27fd  lock cmpxchg [rdi-68h], rcx
0x1800b2803  jnz     short loc_1800B27E2
0x1800b2805  xor     rbx, 2
0x1800b2809  jz      short loc_1800B2823
0x1800b280b  mov     rcx, rbx; this
0x1800b280e  call    ?AddReference@REFERENCED_OBJECT@@QEAAHXZ; REFERENCED_OBJECT::AddReference(void)
0x1800b2813  mov     rax, [rdi-68h]
0x1800b2817  xor     rax, 1
0x1800b281b  xchg    rax, [rdi-68h]
0x1800b281f  jmp     short loc_1800B2823
0x1800b2821  xor     ebx, ebx
0x1800b2823  cmp     esi, 0FFFFFFFEh
0x1800b2826  jnz     short loc_1800B282E
0x1800b2828  mov     esi, [rdi-0ACh]
0x1800b282e  mov     rcx, cs:?ThreadListMutex@@3PEAVMUTEX@@EA; CriticalSection
0x1800b2835  call    cs:__imp_RtlLeaveCriticalSection
0x1800b283b  test    rbx, rbx
0x1800b283e  jnz     short loc_1800B2847
0x1800b2840  mov     eax, 6BDh
0x1800b2845  jmp     short loc_1800B2875
0x1800b2847  mov     rcx, rbx; this
0x1800b284a  test    esi, esi
0x1800b284c  jnz     short loc_1800B2858
0x1800b284e  lea     edx, [rsi+1]; int
0x1800b2851  call    ?CancelAsyncCall@LRPC_BASE_CCALL@@UEAAJH@Z; LRPC_BASE_CCALL::CancelAsyncCall(int)
0x1800b2856  jmp     short loc_1800B2864
0x1800b2858  xor     edx, edx; int
0x1800b285a  call    ?CancelAsyncCall@LRPC_BASE_CCALL@@UEAAJH@Z; LRPC_BASE_CCALL::CancelAsyncCall(int)
0x1800b285f  cmp     esi, 0FFFFFFFFh
0x1800b2862  jnz     short loc_1800B287E
0x1800b2864  mov     rax, [rbx]
0x1800b2867  mov     rcx, rbx
0x1800b286a  mov     rax, [rax+20h]
0x1800b286e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b2873  xor     eax, eax
0x1800b2875  add     rsp, 48h
0x1800b2879  pop     rdi
0x1800b287a  pop     rsi
0x1800b287b  pop     rbp
0x1800b287c  pop     rbx
0x1800b287d  retn
0x1800b287e  imul    eax, esi, 3E8h
0x1800b2884  lea     rcx, [rbx+348h]; phNewTimer
0x1800b288b  mov     [rsp+68h+Flags], 0; Flags
0x1800b2893  lea     r8, ?LrpcSyncCancelCallback@@YAXPEAXE@Z; Callback
0x1800b289a  mov     [rsp+68h+Period], 0; Period
0x1800b28a2  mov     r9, rbx; Parameter
0x1800b28a5  xor     edx, edx; TimerQueue
0x1800b28a7  mov     [rsp+68h+DueTime], eax; DueTime
0x1800b28ab  call    cs:__imp_CreateTimerQueueTimer
0x1800b28b1  test    eax, eax
0x1800b28b3  jnz     short loc_1800B2873
0x1800b28b5  mov     rax, [rbx]
0x1800b28b8  mov     rcx, rbx
0x1800b28bb  mov     rax, [rax+20h]
0x1800b28bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b28c4  mov     eax, 0Eh
0x1800b28c9  jmp     short loc_1800B2875
```
