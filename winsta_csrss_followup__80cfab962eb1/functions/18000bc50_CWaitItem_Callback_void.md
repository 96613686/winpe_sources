# CWaitItem::Callback(void)

- ea: `0x18000bc50`
- end: `0x18000be1a`
- name: `?Callback@CWaitItem@@MEAAJXZ`
- size: `458`
- prototype: `__int64 __fastcall(CWaitItem *__hidden this)`
- caller_count: `4`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000b9e0`
- `0x18000bc00`
- `0x18002a9c0`
- `0x18002b4d0`

## callees

- `0x180005b40`
- `0x18000bc50`
- `0x18000c478`
- `0x180034010`

## import_xrefs

- `ntdll!RtlCaptureStackBackTrace` at `0x18000bd88`
- `ntdll!RtlCaptureStackBackTrace` at `0x18000bd88`
- `ntdll!NtQuerySystemTime` at `0x18000bccb`
- `ntdll!NtQuerySystemTime` at `0x18000bccb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000bd1e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000bd1e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000bc77`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000bc77`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18000bc8b`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18000bc8b`

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
0x18000bc50  mov     [rsp-28h+arg_10], rbx
0x18000bc55  push    rbp
0x18000bc56  push    rsi
0x18000bc57  push    rdi
0x18000bc58  push    r14
0x18000bc5a  push    r15
0x18000bc5c  mov     rbp, rsp
0x18000bc5f  sub     rsp, 20h
0x18000bc63  lea     r15, [rcx+5E0h]
0x18000bc6a  mov     [rbp+Reply], 80004001h
0x18000bc71  mov     rsi, rcx
0x18000bc74  mov     rcx, r15; lpCriticalSection
0x18000bc77  call    cs:__imp_EnterCriticalSection
0x18000bc7e  nop     dword ptr [rax+rax+00h]
0x18000bc83  lea     rcx, [rsi+58h]; pAsync
0x18000bc87  lea     rdx, [rbp+Reply]; Reply
0x18000bc8b  call    cs:__imp_RpcAsyncCompleteCall
0x18000bc92  nop     dword ptr [rax+rax+00h]
0x18000bc97  mov     edi, eax
0x18000bc99  cmp     eax, 71Ah
0x18000bc9e  jnz     loc_18000BD3F
0x18000bca4  mov     edi, 1
0x18000bca9  lea     rbx, [rsi+0C8h]
0x18000bcb0  mov     eax, edi
0x18000bcb2  lock xadd [rbx+4], eax
0x18000bcb7  add     eax, edi
0x18000bcb9  lea     rcx, [rbx+10h]
0x18000bcbd  and     eax, 0Fh
0x18000bcc0  lea     r14, [rax+rax*4]
0x18000bcc4  shl     r14, 4
0x18000bcc8  add     rcx, r14; SystemTime
0x18000bccb  call    cs:__imp_NtQuerySystemTime
0x18000bcd2  nop     dword ptr [rax+rax+00h]
0x18000bcd7  cmp     cs:?g_bCaptureObjectStackTrace@@3HA, edi; int g_bCaptureObjectStackTrace
0x18000bcdd  mov     [rbp+BackTraceHash], 0
0x18000bce4  jz      loc_18000BD76
0x18000bcea  mov     eax, [rbx]
0x18000bcec  mov     [r14+rbx+8], eax
0x18000bcf1  mov     dword ptr [rbx], 4
0x18000bcf7  mov     dword ptr [r14+rbx+0Ch], 4
0x18000bd00  mov     [rbp+Reply], 8007012Fh
0x18000bd07  cmp     dword ptr [rbx], 4
0x18000bd0a  jnz     short loc_18000BD1B
0x18000bd0c  mov     rax, [rsi]
0x18000bd0f  mov     rcx, rsi
0x18000bd12  mov     rax, [rax+8]
0x18000bd16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd1b  mov     rcx, r15; lpCriticalSection
0x18000bd1e  call    cs:__imp_LeaveCriticalSection
0x18000bd25  nop     dword ptr [rax+rax+00h]
0x18000bd2a  mov     eax, [rbp+Reply]
0x18000bd2d  mov     rbx, [rsp+20h+arg_10]
0x18000bd32  add     rsp, 20h
0x18000bd36  pop     r15
0x18000bd38  pop     r14
0x18000bd3a  pop     rdi
0x18000bd3b  pop     rsi
0x18000bd3c  pop     rbp
0x18000bd3d  retn
0x18000bd3f  test    edi, edi
0x18000bd41  jnz     short loc_18000BD99
0x18000bd43  lea     rbx, [rsi+0C8h]
0x18000bd4a  cmp     dword ptr [rbx], 3
0x18000bd4d  mov     rcx, rbx
0x18000bd50  jz      short loc_18000BD64
0x18000bd52  lea     edx, [rdi+1]
0x18000bd55  call    ??4?$StateTracker@W4WaitItemCallState@CWaitItem@@@@QEAA?AW4WaitItemCallState@CWaitItem@@W412@@Z; StateTracker<CWaitItem::WaitItemCallState>::operator=(CWaitItem::WaitItemCallState)
0x18000bd5a  cmp     [rbp+Reply], edi
0x18000bd5d  jl      short loc_18000BD07
0x18000bd5f  mov     [rbp+Reply], edi
0x18000bd62  jmp     short loc_18000BD07
0x18000bd64  mov     edx, 4
0x18000bd69  call    ??4?$StateTracker@W4WaitItemCallState@CWaitItem@@@@QEAA?AW4WaitItemCallState@CWaitItem@@W412@@Z; StateTracker<CWaitItem::WaitItemCallState>::operator=(CWaitItem::WaitItemCallState)
0x18000bd6e  cmp     [rbp+Reply], 0
0x18000bd72  jl      short loc_18000BD07
0x18000bd74  jmp     short loc_18000BD00
0x18000bd76  lea     r8, [rbx+18h]
0x18000bd7a  mov     edx, 8; FramesToCapture
0x18000bd7f  add     r8, r14; BackTrace
0x18000bd82  lea     r9, [rbp+BackTraceHash]; BackTraceHash
0x18000bd86  mov     ecx, edi; FramesToSkip
0x18000bd88  call    cs:__imp_RtlCaptureStackBackTrace
0x18000bd8f  nop     dword ptr [rax+rax+00h]
0x18000bd94  jmp     loc_18000BCEA
0x18000bd99  mov     ecx, 4; int
0x18000bd9e  cmp     edi, 77Ah
0x18000bda4  jnz     short loc_18000BDCB
0x18000bda6  lea     rdx, aRpcCallbackCal; "RPC CallBack called with call status RP"...
0x18000bdad  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000bdb2  lea     rbx, [rsi+0C8h]
0x18000bdb9  mov     edx, 4
0x18000bdbe  mov     rcx, rbx
0x18000bdc1  call    ??4?$StateTracker@W4WaitItemCallState@CWaitItem@@@@QEAA?AW4WaitItemCallState@CWaitItem@@W412@@Z; StateTracker<CWaitItem::WaitItemCallState>::operator=(CWaitItem::WaitItemCallState)
0x18000bdc6  jmp     loc_18000BD00
0x18000bdcb  lea     rbx, [rsi+0C8h]
0x18000bdd2  cmp     edi, 3E5h
0x18000bdd8  jnz     short loc_18000BDF2
0x18000bdda  lea     rdx, aRpcCallbackCal_1; "RPC CallBack called but call status is "...
0x18000bde1  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000bde6  mov     [rbp+Reply], 800703E5h
0x18000bded  jmp     loc_18000BD07
0x18000bdf2  mov     r8d, edi
0x18000bdf5  lea     rdx, aRpcCallbackCal_0; "RPC CallBack called but call status is "...
0x18000bdfc  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000be01  mov     edx, 4
0x18000be06  mov     rcx, rbx
0x18000be09  call    ??4?$StateTracker@W4WaitItemCallState@CWaitItem@@@@QEAA?AW4WaitItemCallState@CWaitItem@@W412@@Z; StateTracker<CWaitItem::WaitItemCallState>::operator=(CWaitItem::WaitItemCallState)
0x18000be0e  bts     edi, 1Ch
0x18000be12  mov     [rbp+Reply], edi
0x18000be15  jmp     loc_18000BD07
```
