# CTimer<CTpSrvDataState>::Initialize(CTpSrvDataState *,void *,ulong,ulong,void *,ulong)

- ea: `0x180014040`
- end: `0x180014100`
- name: `?Initialize@?$CTimer@VCTpSrvDataState@@@@QEAAKPEAVCTpSrvDataState@@PEAXKK1K@Z`
- size: `192`
- prototype: `__int64 __fastcall(PVOID Parameter)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180011a4c`

## callees

- `0x180008d38`
- `0x180014040`

## import_xrefs

- `KERNEL32!CreateTimerQueueTimer` at `0x1800140cd`
- `KERNEL32!CreateTimerQueueTimer` at `0x1800140cd`
- `KERNEL32!GetCurrentThreadId` at `0x18001406a`
- `KERNEL32!GetCurrentThreadId` at `0x18001406a`
- `KERNEL32!SwitchToThread` at `0x180014085`
- `KERNEL32!SwitchToThread` at `0x180014085`
- `KERNEL32!GetLastError` at `0x1800140d7`
- `KERNEL32!GetLastError` at `0x1800140d7`

## pseudocode

```c
__int64 __fastcall CTimer<CTpSrvDataState>::Initialize(PVOID Parameter, __int64 a2)
{
  DWORD LastError; // ebx
  int v5; // esi
  DWORD CurrentThreadId; // ecx
  signed __int32 v7; // eax
  PVOID v9; // [rsp+40h] [rbp-18h] BYREF
  int v10; // [rsp+48h] [rbp-10h]

  LastError = 0;
  v9 = Parameter;
  v10 = 0;
  while ( 1 )
  {
    v5 = 0;
    if ( *((_DWORD *)Parameter + 2) )
      break;
LABEL_6:
    SwitchToThread();
  }
  while ( 1 )
  {
    CurrentThreadId = GetCurrentThreadId();
    v7 = _InterlockedCompareExchange((volatile signed __int32 *)Parameter, CurrentThreadId, 0);
    if ( !v7 || v7 == CurrentThreadId )
      break;
    if ( (unsigned int)++v5 >= *((_DWORD *)Parameter + 2) )
      goto LABEL_6;
  }
  _InterlockedIncrement((volatile signed __int32 *)Parameter + 1);
  v10 = 1;
  *((_QWORD *)Parameter + 2) = 0;
  *((_QWORD *)Parameter + 4) = a2;
  *((_QWORD *)Parameter + 6) = 0;
  *((_DWORD *)Parameter + 10) = 0;
  if ( !CreateTimerQueueTimer(
          (PHANDLE)Parameter + 3,
          0,
          (WAITORTIMERCALLBACK)CTimer<CTpSrvDataState>::_TimerCallback,
          Parameter,
          0xFFFFFFFE,
          0xFFFFFFFE,
          1u) )
    LastError = GetLastError();
  CAutoTypeLock<CSpinLock>::~CAutoTypeLock<CSpinLock>(&v9);
  return LastError;
}

```

## disassembly

```asm
0x180014040  mov     rax, rsp
0x180014043  mov     [rax+8], rbx
0x180014047  mov     [rax+10h], rbp
0x18001404b  mov     [rax+18h], rsi
0x18001404f  push    rdi
0x180014050  sub     rsp, 50h
0x180014054  xor     ebx, ebx
0x180014056  mov     [rax-18h], rcx
0x18001405a  mov     [rax-10h], ebx
0x18001405d  mov     rbp, rdx
0x180014060  mov     rdi, rcx
0x180014063  mov     esi, ebx
0x180014065  cmp     [rdi+8], ebx
0x180014068  jbe     short loc_180014085
0x18001406a  call    cs:__imp_GetCurrentThreadId
0x180014070  mov     ecx, eax
0x180014072  xor     eax, eax
0x180014074  lock cmpxchg [rdi], ecx
0x180014078  jz      short loc_18001408D
0x18001407a  cmp     eax, ecx
0x18001407c  jz      short loc_18001408D
0x18001407e  inc     esi
0x180014080  cmp     esi, [rdi+8]
0x180014083  jb      short loc_18001406A
0x180014085  call    cs:__imp_SwitchToThread
0x18001408b  jmp     short loc_180014063
0x18001408d  lock inc dword ptr [rdi+4]
0x180014091  mov     eax, 0FFFFFFFEh
0x180014096  mov     [rsp+58h+Flags], 1; Flags
0x18001409e  mov     [rsp+58h+Period], eax; Period
0x1800140a2  lea     rcx, [rdi+18h]; phNewTimer
0x1800140a6  mov     r9, rdi; Parameter
0x1800140a9  mov     [rsp+58h+DueTime], eax; DueTime
0x1800140ad  lea     r8, ?_TimerCallback@?$CTimer@VCTpSrvDataState@@@@SAXPEAXE@Z; Callback
0x1800140b4  mov     [rsp+58h+var_10], 1
0x1800140bc  xor     edx, edx; TimerQueue
0x1800140be  mov     [rdi+10h], rbx
0x1800140c2  mov     [rdi+20h], rbp
0x1800140c6  mov     [rdi+30h], rbx
0x1800140ca  mov     [rdi+28h], ebx
0x1800140cd  call    cs:__imp_CreateTimerQueueTimer
0x1800140d3  test    eax, eax
0x1800140d5  jnz     short loc_1800140DF
0x1800140d7  call    cs:__imp_GetLastError
0x1800140dd  mov     ebx, eax
0x1800140df  lea     rcx, [rsp+58h+var_18]
0x1800140e4  call    ??1?$CAutoTypeLock@VCSpinLock@@@@QEAA@XZ; CAutoTypeLock<CSpinLock>::~CAutoTypeLock<CSpinLock>(void)
0x1800140e9  mov     rbp, [rsp+58h+arg_8]
0x1800140ee  mov     eax, ebx
0x1800140f0  mov     rbx, [rsp+58h+arg_0]
0x1800140f5  mov     rsi, [rsp+58h+arg_10]
0x1800140fa  add     rsp, 50h
0x1800140fe  pop     rdi
0x1800140ff  retn
```
