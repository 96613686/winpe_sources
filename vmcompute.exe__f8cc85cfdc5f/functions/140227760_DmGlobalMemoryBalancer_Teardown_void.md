# DmGlobalMemoryBalancer::Teardown(void)

- ea: `0x140227760`
- end: `0x140227837`
- name: `?Teardown@DmGlobalMemoryBalancer@@AEAAXXZ`
- size: `215`
- prototype: `void __fastcall(DmGlobalMemoryBalancer *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140225cfc`
- `0x140227d14`

## callees

- `0x1400dd128`
- `0x140105634`
- `0x140224b2c`
- `0x140227760`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1402277ba`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1402277ba`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14022778f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14022778f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1402277a7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1402277a7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1402277dd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1402277dd`

## pseudocode

```c
void __fastcall DmGlobalMemoryBalancer::Teardown(DmGlobalMemoryBalancer *this)
{
  void *v2; // rcx
  _BYTE *v3; // rsi
  void *const *v4; // rax
  unsigned int MemoryPartitionIdFromHandle; // eax
  const char *v6; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( *((_QWORD *)this + 17) )
  {
    _InterlockedExchange((volatile __int32 *)this + 36, -1);
    SetThreadpoolTimer(*((PTP_TIMER *)this + 17), 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(*((PTP_TIMER *)this + 17), 1);
    CloseThreadpoolTimer(*((PTP_TIMER *)this + 17));
    *((_QWORD *)this + 17) = 0;
  }
  v2 = (void *)*((_QWORD *)this + 44);
  if ( v2 )
  {
    CloseHandle(v2);
    *((_QWORD *)this + 44) = 0;
  }
  v3 = (char *)this + 96;
  if ( *((_BYTE *)this + 96) )
  {
    try
    {
      v4 = (void *const *)std::optional<void *>::value();
      MemoryPartitionIdFromHandle = DmGlobalMemoryBalancer::GetMemoryPartitionIdFromHandle(this, *v4);
      DmGlobalMemoryBalancer::DecrementPartitionRefCount(this, MemoryPartitionIdFromHandle);
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x175,
        (unsigned int)"onecore\\vm\\compute\\management\\resources\\dm\\lib\\dmglobalmemorybalancer.cpp",
        v6);
      v3 = (char *)this + 96;
    }
    *v3 = 0;
  }
}

```

## disassembly

```asm
0x140227760  mov     [rsp+arg_8], rbx
0x140227765  push    rsi
0x140227766  sub     rsp, 20h
0x14022776a  mov     rbx, rcx
0x14022776d  cmp     qword ptr [rcx+88h], 0
0x140227775  jz      short loc_1402277D1
0x140227777  or      eax, 0FFFFFFFFh
0x14022777a  xchg    eax, [rcx+90h]
0x140227780  xor     r9d, r9d; msWindowLength
0x140227783  xor     r8d, r8d; msPeriod
0x140227786  xor     edx, edx; pftDueTime
0x140227788  mov     rcx, [rcx+88h]; pti
0x14022778f  call    cs:__imp_SetThreadpoolTimer
0x140227796  nop     dword ptr [rax+rax+00h]
0x14022779b  mov     edx, 1; fCancelPendingCallbacks
0x1402277a0  mov     rcx, [rbx+88h]; pti
0x1402277a7  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1402277ae  nop     dword ptr [rax+rax+00h]
0x1402277b3  mov     rcx, [rbx+88h]; pti
0x1402277ba  call    cs:__imp_CloseThreadpoolTimer
0x1402277c1  nop     dword ptr [rax+rax+00h]
0x1402277c6  mov     qword ptr [rbx+88h], 0
0x1402277d1  mov     rcx, [rbx+160h]; hObject
0x1402277d8  test    rcx, rcx
0x1402277db  jz      short loc_1402277F4
0x1402277dd  call    cs:__imp_CloseHandle
0x1402277e4  nop     dword ptr [rax+rax+00h]
0x1402277e9  mov     qword ptr [rbx+160h], 0
0x1402277f4  lea     rsi, [rbx+60h]
0x1402277f8  mov     [rsp+28h+arg_0], rsi
0x1402277fd  cmp     byte ptr [rsi], 0
0x140227800  jz      short loc_14022782B
0x140227802  lea     rcx, [rbx+58h]
0x140227806  call    ?value@?$optional@PEAX@std@@QEGAAAEAPEAXXZ; std::optional<void *>::value(void)
0x14022780b  mov     rdx, [rax]; void *
0x14022780e  mov     rcx, rbx; this
0x140227811  call    ?GetMemoryPartitionIdFromHandle@DmGlobalMemoryBalancer@@AEBAKQEAX@Z; DmGlobalMemoryBalancer::GetMemoryPartitionIdFromHandle(void * const)
0x140227816  mov     edx, eax; unsigned int
0x140227818  mov     rcx, rbx; this
0x14022781b  call    ?DecrementPartitionRefCount@DmGlobalMemoryBalancer@@AEAAXK@Z; DmGlobalMemoryBalancer::DecrementPartitionRefCount(ulong)
0x140227820  nop
0x140227821  jmp     short loc_140227828
0x140227823  mov     rsi, [rsp+28h+arg_0]
0x140227828  mov     byte ptr [rsi], 0
0x14022782b  mov     rbx, [rsp+28h+arg_8]
0x140227830  add     rsp, 20h
0x140227834  pop     rsi
0x140227835  retn
```
