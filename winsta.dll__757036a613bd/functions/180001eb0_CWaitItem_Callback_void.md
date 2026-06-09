# CWaitItem::Callback(void)

- ea: `0x180001eb0`
- end: `0x18000205b`
- name: `?Callback@CWaitItem@@MEAAJXZ`
- size: `427`
- prototype: `__int64 __fastcall(CWaitItem *__hidden this)`
- caller_count: `4`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001c70`
- `0x180001e70`
- `0x180028de0`
- `0x180029890`

## callees

- `0x180001eb0`
- `0x180002654`
- `0x180007890`
- `0x180031010`

## import_xrefs

- `ntdll!RtlCaptureStackBackTrace` at `0x180001fcf`
- `ntdll!RtlCaptureStackBackTrace` at `0x180001fcf`
- `ntdll!NtQuerySystemTime` at `0x180001f1f`
- `ntdll!NtQuerySystemTime` at `0x180001f1f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001f6c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001f6c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001ed7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001ed7`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180001ee5`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180001ee5`

## pseudocode

```c
__int64 __fastcall CWaitItem::Callback(CWaitItem *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // r15
  RPC_STATUS v3; // eax
  RPC_STATUS v4; // edi
  _DWORD *v5; // rbx
  __int64 v6; // r14
  char *v8; // rcx
  int Reply; // [rsp+50h] [rbp+30h] BYREF
  ULONG BackTraceHash; // [rsp+58h] [rbp+38h] BYREF

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 1504);
  Reply = -2147467263;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 1504));
  v3 = RpcAsyncCompleteCall((PRPC_ASYNC_STATE)((char *)this + 88), &Reply);
  v4 = v3;
  if ( v3 == 1818 )
  {
    v5 = (_DWORD *)((char *)this + 200);
    v6 = 20LL * (((unsigned __int8)_InterlockedExchangeAdd((volatile signed __int32 *)this + 51, 1u) + 1) & 0xF);
    NtQuerySystemTime((PLARGE_INTEGER)((char *)this + v6 * 4 + 216));
    BackTraceHash = 0;
    if ( g_bCaptureObjectStackTrace == 1 )
      RtlCaptureStackBackTrace(1u, 8u, (PVOID *)((char *)this + v6 * 4 + 224), &BackTraceHash);
    v5[v6 + 2] = *v5;
    *v5 = 4;
    v5[v6 + 3] = 4;
    goto LABEL_5;
  }
  if ( v3 )
  {
    if ( v3 != 1914 )
    {
      v5 = (_DWORD *)((char *)this + 200);
      if ( v3 == 997 )
      {
        _DbgPrintMessage(4, "RPC CallBack called but call status is RPC_S_ASYNC_CALL_PENDING!!!");
        Reply = -2147023899;
      }
      else
      {
        _DbgPrintMessage(4, "RPC CallBack called but call status is unknown - %#x!!!", v3);
        StateTracker<enum CWaitItem::WaitItemCallState>::operator=((char *)this + 200, 4);
        Reply = v4 | 0x10000000;
      }
      goto LABEL_6;
    }
    _DbgPrintMessage(4, "RPC CallBack called with call status RPC_S_INVALID_ASYNC_HANDLE!!!");
    v5 = (_DWORD *)((char *)this + 200);
    StateTracker<enum CWaitItem::WaitItemCallState>::operator=((char *)this + 200, 4);
LABEL_5:
    Reply = -2147024593;
    goto LABEL_6;
  }
  v5 = (_DWORD *)((char *)this + 200);
  v8 = (char *)this + 200;
  if ( *((_DWORD *)this + 50) == 3 )
  {
    StateTracker<enum CWaitItem::WaitItemCallState>::operator=(v8, 4);
    if ( Reply < 0 )
      goto LABEL_6;
    goto LABEL_5;
  }
  StateTracker<enum CWaitItem::WaitItemCallState>::operator=(v8, (unsigned int)(v3 + 1));
  if ( Reply >= 0 )
    Reply = 0;
LABEL_6:
  if ( *v5 == 4 )
    (*(void (__fastcall **)(CWaitItem *))(*(_QWORD *)this + 8LL))(this);
  LeaveCriticalSection(v1);
  return (unsigned int)Reply;
}

```

## disassembly

```asm
0x180001eb0  mov     [rsp-28h+arg_10], rbx
0x180001eb5  push    rbp
0x180001eb6  push    rsi
0x180001eb7  push    rdi
0x180001eb8  push    r14
0x180001eba  push    r15
0x180001ebc  mov     rbp, rsp
0x180001ebf  sub     rsp, 20h
0x180001ec3  lea     r15, [rcx+5E0h]
0x180001eca  mov     [rbp+Reply], 80004001h
0x180001ed1  mov     rsi, rcx
0x180001ed4  mov     rcx, r15; lpCriticalSection
0x180001ed7  call    cs:__imp_EnterCriticalSection
0x180001edd  lea     rcx, [rsi+58h]; pAsync
0x180001ee1  lea     rdx, [rbp+Reply]; Reply
0x180001ee5  call    cs:__imp_RpcAsyncCompleteCall
0x180001eeb  mov     edi, eax
0x180001eed  cmp     eax, 71Ah
0x180001ef2  jnz     loc_180001F86
0x180001ef8  mov     edi, 1
0x180001efd  lea     rbx, [rsi+0C8h]
0x180001f04  mov     eax, edi
0x180001f06  lock xadd [rbx+4], eax
0x180001f0b  add     eax, edi
0x180001f0d  lea     rcx, [rbx+10h]
0x180001f11  and     eax, 0Fh
0x180001f14  lea     r14, [rax+rax*4]
0x180001f18  shl     r14, 4
0x180001f1c  add     rcx, r14; SystemTime
0x180001f1f  call    cs:__imp_NtQuerySystemTime
0x180001f25  cmp     cs:?g_bCaptureObjectStackTrace@@3HA, edi; int g_bCaptureObjectStackTrace
0x180001f2b  mov     [rbp+BackTraceHash], 0
0x180001f32  jz      loc_180001FBD
0x180001f38  mov     eax, [rbx]
0x180001f3a  mov     [r14+rbx+8], eax
0x180001f3f  mov     dword ptr [rbx], 4
0x180001f45  mov     dword ptr [r14+rbx+0Ch], 4
0x180001f4e  mov     [rbp+Reply], 8007012Fh
0x180001f55  cmp     dword ptr [rbx], 4
0x180001f58  jnz     short loc_180001F69
0x180001f5a  mov     rax, [rsi]
0x180001f5d  mov     rcx, rsi
0x180001f60  mov     rax, [rax+8]
0x180001f64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f69  mov     rcx, r15; lpCriticalSection
0x180001f6c  call    cs:__imp_LeaveCriticalSection
0x180001f72  mov     eax, [rbp+Reply]
0x180001f75  mov     rbx, [rsp+20h+arg_10]
0x180001f7a  add     rsp, 20h
0x180001f7e  pop     r15
0x180001f80  pop     r14
0x180001f82  pop     rdi
0x180001f83  pop     rsi
0x180001f84  pop     rbp
0x180001f85  retn
0x180001f86  test    edi, edi
0x180001f88  jnz     short loc_180001FDA
0x180001f8a  lea     rbx, [rsi+0C8h]
0x180001f91  cmp     dword ptr [rbx], 3
0x180001f94  mov     rcx, rbx
0x180001f97  jz      short loc_180001FAB
0x180001f99  lea     edx, [rdi+1]
0x180001f9c  call    ??4?$StateTracker@W4WaitItemCallState@CWaitItem@@@@QEAA?AW4WaitItemCallState@CWaitItem@@W412@@Z; StateTracker<CWaitItem::WaitItemCallState>::operator=(CWaitItem::WaitItemCallState)
0x180001fa1  cmp     [rbp+Reply], edi
0x180001fa4  jl      short loc_180001F55
0x180001fa6  mov     [rbp+Reply], edi
0x180001fa9  jmp     short loc_180001F55
0x180001fab  mov     edx, 4
0x180001fb0  call    ??4?$StateTracker@W4WaitItemCallState@CWaitItem@@@@QEAA?AW4WaitItemCallState@CWaitItem@@W412@@Z; StateTracker<CWaitItem::WaitItemCallState>::operator=(CWaitItem::WaitItemCallState)
0x180001fb5  cmp     [rbp+Reply], 0
0x180001fb9  jl      short loc_180001F55
0x180001fbb  jmp     short loc_180001F4E
0x180001fbd  lea     r8, [rbx+18h]
0x180001fc1  mov     edx, 8; FramesToCapture
0x180001fc6  add     r8, r14; BackTrace
0x180001fc9  lea     r9, [rbp+BackTraceHash]; BackTraceHash
0x180001fcd  mov     ecx, edi; FramesToSkip
0x180001fcf  call    cs:__imp_RtlCaptureStackBackTrace
0x180001fd5  jmp     loc_180001F38
0x180001fda  mov     ecx, 4; int
0x180001fdf  cmp     edi, 77Ah
0x180001fe5  jnz     short loc_18000200C
0x180001fe7  lea     rdx, aRpcCallbackCal; "RPC CallBack called with call status RP"...
0x180001fee  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180001ff3  lea     rbx, [rsi+0C8h]
0x180001ffa  mov     edx, 4
0x180001fff  mov     rcx, rbx
0x180002002  call    ??4?$StateTracker@W4WaitItemCallState@CWaitItem@@@@QEAA?AW4WaitItemCallState@CWaitItem@@W412@@Z; StateTracker<CWaitItem::WaitItemCallState>::operator=(CWaitItem::WaitItemCallState)
0x180002007  jmp     loc_180001F4E
0x18000200c  lea     rbx, [rsi+0C8h]
0x180002013  cmp     edi, 3E5h
0x180002019  jnz     short loc_180002033
0x18000201b  lea     rdx, aRpcCallbackCal_1; "RPC CallBack called but call status is "...
0x180002022  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180002027  mov     [rbp+Reply], 800703E5h
0x18000202e  jmp     loc_180001F55
0x180002033  mov     r8d, edi
0x180002036  lea     rdx, aRpcCallbackCal_0; "RPC CallBack called but call status is "...
0x18000203d  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180002042  mov     edx, 4
0x180002047  mov     rcx, rbx
0x18000204a  call    ??4?$StateTracker@W4WaitItemCallState@CWaitItem@@@@QEAA?AW4WaitItemCallState@CWaitItem@@W412@@Z; StateTracker<CWaitItem::WaitItemCallState>::operator=(CWaitItem::WaitItemCallState)
0x18000204f  bts     edi, 1Ch
0x180002053  mov     [rbp+Reply], edi
0x180002056  jmp     loc_180001F55
```
