# CThreadTaskRegister::RegisterWithService(void)

- ea: `0x1800169e0`
- end: `0x180016a3b`
- name: `?RegisterWithService@CThreadTaskRegister@@QEAAJXZ`
- size: `91`
- prototype: `__int64 __fastcall(CThreadTaskRegister *__hidden this)`
- caller_count: `9`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x1800056c8`
- `0x180014fd0`
- `0x180018480`
- `0x1800293ac`
- `0x180029cdc`
- `0x180029dec`
- `0x180029eec`
- `0x18002a650`
- `0x18002e610`

## callees

- `0x1800169e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800169f9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800169f9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016a0f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016a26`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016a0f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016a26`

## pseudocode

```c
__int64 __fastcall CThreadTaskRegister::RegisterWithService(CThreadTaskRegister *this)
{
  __int64 result; // rax

  if ( !XProcHelpers::g_fInitialized )
    return 2147500037LL;
  EnterCriticalSection(&stru_18003E3B8);
  if ( XProcHelpers::g_fShuttingDown )
  {
    LeaveCriticalSection(&stru_18003E3B8);
    return 2147500037LL;
  }
  ++XProcHelpers::g_cActiveThread;
  LeaveCriticalSection(&stru_18003E3B8);
  result = 0;
  *((_DWORD *)this + 8) = 1;
  return result;
}

```

## disassembly

```asm
0x1800169e0  push    rbx
0x1800169e2  sub     rsp, 20h
0x1800169e6  cmp     cs:?g_fInitialized@XProcHelpers@@3HA, 0; int XProcHelpers::g_fInitialized
0x1800169ed  mov     rbx, rcx
0x1800169f0  jz      short loc_180016A15
0x1800169f2  lea     rcx, stru_18003E3B8; lpCriticalSection
0x1800169f9  call    cs:__imp_EnterCriticalSection
0x1800169ff  cmp     cs:?g_fShuttingDown@XProcHelpers@@3HA, 0; int XProcHelpers::g_fShuttingDown
0x180016a06  lea     rcx, stru_18003E3B8; lpCriticalSection
0x180016a0d  jz      short loc_180016A20
0x180016a0f  call    cs:__imp_LeaveCriticalSection
0x180016a15  mov     eax, 80004005h
0x180016a1a  add     rsp, 20h
0x180016a1e  pop     rbx
0x180016a1f  retn
0x180016a20  inc     cs:?g_cActiveThread@XProcHelpers@@3KA; ulong XProcHelpers::g_cActiveThread
0x180016a26  call    cs:__imp_LeaveCriticalSection
0x180016a2c  xor     eax, eax
0x180016a2e  mov     dword ptr [rbx+20h], 1
0x180016a35  add     rsp, 20h
0x180016a39  pop     rbx
0x180016a3a  retn
```
