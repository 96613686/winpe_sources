# THREAD::LrpcCancelThread(void *,long)

- ea: `0x1800b6600`
- end: `0x1800b6754`
- name: `?LrpcCancelThread@THREAD@@SAJPEAXJ@Z`
- size: `340`
- prototype: `__int64 __fastcall(void *, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800b6810`
- `0x1800b6860`

## callees

- `0x18002cab0`
- `0x1800a3890`
- `0x1800b6600`
- `0x1800d7010`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x1800b66b1`
- `ntdll!RtlLeaveCriticalSection` at `0x1800b66b1`
- `ntdll!RtlEnterCriticalSection` at `0x1800b6630`
- `ntdll!RtlEnterCriticalSection` at `0x1800b6630`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x1800b660b`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x1800b660b`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x1800b672e`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x1800b672e`

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
0x1800b6600  push    rbx
0x1800b6602  push    rbp
0x1800b6603  push    rsi
0x1800b6604  push    rdi
0x1800b6605  sub     rsp, 48h
0x1800b6609  mov     esi, edx
0x1800b660b  call    cs:__imp_GetThreadId
0x1800b6612  nop     dword ptr [rax+rax+00h]
0x1800b6617  mov     ebp, eax
0x1800b6619  test    eax, eax
0x1800b661b  jnz     short loc_1800B6627
0x1800b661d  mov     eax, 5
0x1800b6622  jmp     loc_1800B66F7
0x1800b6627  mov     rcx, cs:?ThreadListMutex@@3PEAVMUTEX@@EA; CriticalSection
0x1800b662e  xor     ebx, ebx
0x1800b6630  call    cs:__imp_RtlEnterCriticalSection
0x1800b6637  nop     dword ptr [rax+rax+00h]
0x1800b663c  mov     rax, cs:?ThreadListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY ThreadListHead
0x1800b6643  lea     rcx, ?ThreadListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY ThreadListHead
0x1800b664a  cmp     rax, rcx
0x1800b664d  jz      short loc_1800B66AA
0x1800b664f  mov     rdi, rax
0x1800b6652  mov     rax, [rax]
0x1800b6655  cmp     [rdi-0A0h], rbp
0x1800b665c  jnz     short loc_1800B6643
0x1800b665e  mov     rbx, [rdi-68h]
0x1800b6662  test    rbx, rbx
0x1800b6665  jz      short loc_1800B669D
0x1800b6667  mov     al, bl
0x1800b6669  and     al, 3
0x1800b666b  cmp     al, 2
0x1800b666d  jnz     short loc_1800B669D
0x1800b666f  mov     rcx, rbx
0x1800b6672  mov     rax, rbx
0x1800b6675  or      rcx, 1
0x1800b6679  lock cmpxchg [rdi-68h], rcx
0x1800b667f  jnz     short loc_1800B665E
0x1800b6681  xor     rbx, 2
0x1800b6685  jz      short loc_1800B669F
0x1800b6687  mov     rcx, rbx; this
0x1800b668a  call    ?AddReference@REFERENCED_OBJECT@@QEAAHXZ; REFERENCED_OBJECT::AddReference(void)
0x1800b668f  mov     rax, [rdi-68h]
0x1800b6693  xor     rax, 1
0x1800b6697  xchg    rax, [rdi-68h]
0x1800b669b  jmp     short loc_1800B669F
0x1800b669d  xor     ebx, ebx
0x1800b669f  cmp     esi, 0FFFFFFFEh
0x1800b66a2  jnz     short loc_1800B66AA
0x1800b66a4  mov     esi, [rdi-0ACh]
0x1800b66aa  mov     rcx, cs:?ThreadListMutex@@3PEAVMUTEX@@EA; CriticalSection
0x1800b66b1  call    cs:__imp_RtlLeaveCriticalSection
0x1800b66b8  nop     dword ptr [rax+rax+00h]
0x1800b66bd  test    rbx, rbx
0x1800b66c0  jnz     short loc_1800B66C9
0x1800b66c2  mov     eax, 6BDh
0x1800b66c7  jmp     short loc_1800B66F7
0x1800b66c9  mov     rcx, rbx; this
0x1800b66cc  test    esi, esi
0x1800b66ce  jnz     short loc_1800B66DA
0x1800b66d0  lea     edx, [rsi+1]; int
0x1800b66d3  call    ?CancelAsyncCall@LRPC_BASE_CCALL@@UEAAJH@Z; LRPC_BASE_CCALL::CancelAsyncCall(int)
0x1800b66d8  jmp     short loc_1800B66E6
0x1800b66da  xor     edx, edx; int
0x1800b66dc  call    ?CancelAsyncCall@LRPC_BASE_CCALL@@UEAAJH@Z; LRPC_BASE_CCALL::CancelAsyncCall(int)
0x1800b66e1  cmp     esi, 0FFFFFFFFh
0x1800b66e4  jnz     short loc_1800B6701
0x1800b66e6  mov     rax, [rbx]
0x1800b66e9  mov     rcx, rbx
0x1800b66ec  mov     rax, [rax+20h]
0x1800b66f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b66f5  xor     eax, eax
0x1800b66f7  add     rsp, 48h
0x1800b66fb  pop     rdi
0x1800b66fc  pop     rsi
0x1800b66fd  pop     rbp
0x1800b66fe  pop     rbx
0x1800b66ff  retn
0x1800b6701  imul    eax, esi, 3E8h
0x1800b6707  lea     rcx, [rbx+348h]; phNewTimer
0x1800b670e  mov     [rsp+68h+Flags], 0; Flags
0x1800b6716  lea     r8, ?LrpcSyncCancelCallback@@YAXPEAXE@Z; Callback
0x1800b671d  mov     [rsp+68h+Period], 0; Period
0x1800b6725  mov     r9, rbx; Parameter
0x1800b6728  xor     edx, edx; TimerQueue
0x1800b672a  mov     [rsp+68h+DueTime], eax; DueTime
0x1800b672e  call    cs:__imp_CreateTimerQueueTimer
0x1800b6735  nop     dword ptr [rax+rax+00h]
0x1800b673a  test    eax, eax
0x1800b673c  jnz     short loc_1800B66F5
0x1800b673e  mov     rax, [rbx]
0x1800b6741  mov     rcx, rbx
0x1800b6744  mov     rax, [rax+20h]
0x1800b6748  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b674d  mov     eax, 0Eh
0x1800b6752  jmp     short loc_1800B66F7
```
