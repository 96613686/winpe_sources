# HTTP2PingOriginator::SetNewPingInterval(ulong)

- ea: `0x18001964c`
- end: `0x180019773`
- name: `?SetNewPingInterval@HTTP2PingOriginator@@QEAAJK@Z`
- size: `295`
- prototype: `__int64 __fastcall(HTTP2PingOriginator *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x18000ba10`
- `0x180019330`
- `0x180019490`

## callees

- `0x1800043d8`
- `0x180005428`
- `0x1800097b4`
- `0x180009d58`
- `0x18001964c`
- `0x18001e7b4`

## import_xrefs

- `KERNEL32!CreateThreadpoolTimer` at `0x1800196a4`
- `KERNEL32!CreateThreadpoolTimer` at `0x1800196a4`
- `KERNEL32!IsThreadpoolTimerSet` at `0x1800196d4`
- `KERNEL32!IsThreadpoolTimerSet` at `0x1800196d4`
- `KERNEL32!SetThreadpoolTimer` at `0x18001973b`
- `KERNEL32!SetThreadpoolTimer` at `0x18001973b`
- `KERNEL32!CloseThreadpoolTimer` at `0x18001976b`
- `KERNEL32!CloseThreadpoolTimer` at `0x18001976b`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800196eb`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800196eb`
- `RPCRT4!I_RpcAllocate` at `0x1800196bb`
- `RPCRT4!I_RpcAllocate` at `0x1800196bb`

## pseudocode

```c
__int64 __fastcall HTTP2PingOriginator::SetNewPingInterval(HTTP2PingOriginator *this, int a2)
{
  HTTP2Channel *v3; // rcx
  __int64 result; // rax
  PTP_TIMER *v5; // rax
  struct _TP_TIMER *ThreadpoolTimer; // rdi
  __int64 v7; // r8
  struct _FILETIME SystemTimeAsFileTime; // [rsp+30h] [rbp+8h] BYREF
  struct _FILETIME v9; // [rsp+40h] [rbp+18h]

  *((_DWORD *)this + 9) = a2;
  *((_DWORD *)this + 14) = 0;
  v3 = (HTTP2Channel *)*((_QWORD *)this + 3);
  SystemTimeAsFileTime = 0;
  result = HTTP2Channel::BeginSimpleSubmitAsync(v3);
  if ( !(_DWORD)result )
  {
    v5 = (PTP_TIMER *)*((_QWORD *)this + 5);
    if ( !v5 )
    {
      if ( !(unsigned int)RPC_THREAD_POOL::InitializeCallbackEnvironmentIfNecessary() )
      {
        ThreadpoolTimer = CreateThreadpoolTimer(HTTP2PingTimerCallback, this, RPC_THREAD_POOL::CallbackEnvironment);
        if ( ThreadpoolTimer )
        {
          v5 = (PTP_TIMER *)I_RpcAllocate(8u);
          if ( v5 )
          {
            *v5 = ThreadpoolTimer;
            *((_QWORD *)this + 5) = v5;
            goto LABEL_7;
          }
          *((_QWORD *)this + 5) = 0;
          CloseThreadpoolTimer(ThreadpoolTimer);
        }
      }
      return 0;
    }
LABEL_7:
    if ( IsThreadpoolTimerSet(*v5) )
      HTTP2PingOriginator::DisablePingsInternal(this);
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v7 = *((unsigned int *)this + 9);
    *(_QWORD *)&SystemTimeAsFileTime += 10000 * v7;
    v9 = SystemTimeAsFileTime;
    SetThreadpoolTimer(**((PTP_TIMER **)this + 5), &SystemTimeAsFileTime, v7, (unsigned int)v7 >> 1);
    HTTP2Channel::AddReference(*((HTTP2Channel **)this + 3));
    HTTP2Channel::FinishSubmitAsync(*((HTTP2Channel **)this + 3));
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18001964c  mov     [rsp+arg_8], rbx
0x180019651  push    rdi
0x180019652  sub     rsp, 20h
0x180019656  mov     rbx, rcx
0x180019659  mov     [rcx+24h], edx
0x18001965c  mov     dword ptr [rcx+38h], 0
0x180019663  mov     rcx, [rcx+18h]; this
0x180019667  mov     qword ptr [rsp+28h+SystemTimeAsFileTime.dwLowDateTime], 0
0x180019670  call    ?BeginSimpleSubmitAsync@HTTP2Channel@@QEAAJXZ; HTTP2Channel::BeginSimpleSubmitAsync(void)
0x180019675  test    eax, eax
0x180019677  jnz     loc_180019755
0x18001967d  mov     rax, [rbx+28h]
0x180019681  test    rax, rax
0x180019684  jnz     short loc_1800196D1
0x180019686  call    ?InitializeCallbackEnvironmentIfNecessary@RPC_THREAD_POOL@@CAJXZ; RPC_THREAD_POOL::InitializeCallbackEnvironmentIfNecessary(void)
0x18001968b  test    eax, eax
0x18001968d  jnz     loc_180019753
0x180019693  mov     r8, cs:?CallbackEnvironment@RPC_THREAD_POOL@@0REAU_TP_CALLBACK_ENVIRON_V3@@EA; pcbe
0x18001969a  lea     rcx, ?HTTP2PingTimerCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800196a1  mov     rdx, rbx; pv
0x1800196a4  call    cs:__imp_CreateThreadpoolTimer
0x1800196aa  mov     rdi, rax
0x1800196ad  test    rax, rax
0x1800196b0  jz      loc_180019753
0x1800196b6  mov     ecx, 8; Size
0x1800196bb  call    cs:__imp_I_RpcAllocate
0x1800196c1  test    rax, rax
0x1800196c4  jz      loc_180019760
0x1800196ca  mov     [rax], rdi
0x1800196cd  mov     [rbx+28h], rax
0x1800196d1  mov     rcx, [rax]; pti
0x1800196d4  call    cs:__imp_IsThreadpoolTimerSet
0x1800196da  test    eax, eax
0x1800196dc  jz      short loc_1800196E6
0x1800196de  mov     rcx, rbx; this
0x1800196e1  call    ?DisablePingsInternal@HTTP2PingOriginator@@AEAAXXZ; HTTP2PingOriginator::DisablePingsInternal(void)
0x1800196e6  lea     rcx, [rsp+28h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800196eb  call    cs:__imp_GetSystemTimeAsFileTime
0x1800196f1  mov     eax, [rsp+28h+SystemTimeAsFileTime.dwHighDateTime]
0x1800196f5  lea     rdx, [rsp+28h+SystemTimeAsFileTime]; pftDueTime
0x1800196fa  mov     r8d, [rbx+24h]; msPeriod
0x1800196fe  mov     dword ptr [rsp+28h+arg_10+4], eax
0x180019702  mov     r9d, r8d
0x180019705  mov     eax, [rsp+28h+SystemTimeAsFileTime.dwLowDateTime]
0x180019709  mov     dword ptr [rsp+28h+arg_10], eax
0x18001970d  mov     rax, [rsp+28h+arg_10]
0x180019712  imul    rcx, r8, 2710h
0x180019719  shr     r9d, 1; msWindowLength
0x18001971c  add     rax, rcx
0x18001971f  mov     [rsp+28h+arg_10], rax
0x180019724  mov     ecx, dword ptr [rsp+28h+arg_10]
0x180019728  mov     [rsp+28h+SystemTimeAsFileTime.dwLowDateTime], ecx
0x18001972c  mov     rcx, [rbx+28h]
0x180019730  shr     rax, 20h
0x180019734  mov     [rsp+28h+SystemTimeAsFileTime.dwHighDateTime], eax
0x180019738  mov     rcx, [rcx]; pti
0x18001973b  call    cs:__imp_SetThreadpoolTimer
0x180019741  mov     rcx, [rbx+18h]; this
0x180019745  call    ?AddReference@HTTP2Channel@@QEAAXXZ; HTTP2Channel::AddReference(void)
0x18001974a  mov     rcx, [rbx+18h]; this
0x18001974e  call    ?FinishSubmitAsync@HTTP2Channel@@QEAAXXZ; HTTP2Channel::FinishSubmitAsync(void)
0x180019753  xor     eax, eax
0x180019755  mov     rbx, [rsp+28h+arg_8]
0x18001975a  add     rsp, 20h
0x18001975e  pop     rdi
0x18001975f  retn
0x180019760  mov     rcx, rdi; pti
0x180019763  mov     qword ptr [rbx+28h], 0
0x18001976b  call    cs:__imp_CloseThreadpoolTimer
0x180019771  jmp     short loc_180019753
```
