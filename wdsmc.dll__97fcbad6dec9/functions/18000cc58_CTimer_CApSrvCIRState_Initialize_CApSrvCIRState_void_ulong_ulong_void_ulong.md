# CTimer<CApSrvCIRState>::Initialize(CApSrvCIRState *,void *,ulong,ulong,void *,ulong)

- ea: `0x18000cc58`
- end: `0x18000cd18`
- name: `?Initialize@?$CTimer@VCApSrvCIRState@@@@QEAAKPEAVCApSrvCIRState@@PEAXKK1K@Z`
- size: `192`
- prototype: `__int64 __fastcall(PVOID Parameter)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180016e70`

## callees

- `0x180008d38`
- `0x18000cc58`

## import_xrefs

- `KERNEL32!CreateTimerQueueTimer` at `0x18000cce5`
- `KERNEL32!CreateTimerQueueTimer` at `0x18000cce5`
- `KERNEL32!GetCurrentThreadId` at `0x18000cc82`
- `KERNEL32!GetCurrentThreadId` at `0x18000cc82`
- `KERNEL32!SwitchToThread` at `0x18000cc9d`
- `KERNEL32!SwitchToThread` at `0x18000cc9d`
- `KERNEL32!GetLastError` at `0x18000ccef`
- `KERNEL32!GetLastError` at `0x18000ccef`

## pseudocode

```c
__int64 __fastcall CTimer<CApSrvCIRState>::Initialize(PVOID Parameter, __int64 a2)
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
          (WAITORTIMERCALLBACK)CTimer<CApSrvCIRState>::_TimerCallback,
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
0x18000cc58  mov     rax, rsp
0x18000cc5b  mov     [rax+8], rbx
0x18000cc5f  mov     [rax+10h], rbp
0x18000cc63  mov     [rax+18h], rsi
0x18000cc67  push    rdi
0x18000cc68  sub     rsp, 50h
0x18000cc6c  xor     ebx, ebx
0x18000cc6e  mov     [rax-18h], rcx
0x18000cc72  mov     [rax-10h], ebx
0x18000cc75  mov     rbp, rdx
0x18000cc78  mov     rdi, rcx
0x18000cc7b  mov     esi, ebx
0x18000cc7d  cmp     [rdi+8], ebx
0x18000cc80  jbe     short loc_18000CC9D
0x18000cc82  call    cs:__imp_GetCurrentThreadId
0x18000cc88  mov     ecx, eax
0x18000cc8a  xor     eax, eax
0x18000cc8c  lock cmpxchg [rdi], ecx
0x18000cc90  jz      short loc_18000CCA5
0x18000cc92  cmp     eax, ecx
0x18000cc94  jz      short loc_18000CCA5
0x18000cc96  inc     esi
0x18000cc98  cmp     esi, [rdi+8]
0x18000cc9b  jb      short loc_18000CC82
0x18000cc9d  call    cs:__imp_SwitchToThread
0x18000cca3  jmp     short loc_18000CC7B
0x18000cca5  lock inc dword ptr [rdi+4]
0x18000cca9  mov     eax, 0FFFFFFFEh
0x18000ccae  mov     [rsp+58h+Flags], 1; Flags
0x18000ccb6  mov     [rsp+58h+Period], eax; Period
0x18000ccba  lea     rcx, [rdi+18h]; phNewTimer
0x18000ccbe  mov     r9, rdi; Parameter
0x18000ccc1  mov     [rsp+58h+DueTime], eax; DueTime
0x18000ccc5  lea     r8, ?_TimerCallback@?$CTimer@VCApSrvCIRState@@@@SAXPEAXE@Z; Callback
0x18000cccc  mov     [rsp+58h+var_10], 1
0x18000ccd4  xor     edx, edx; TimerQueue
0x18000ccd6  mov     [rdi+10h], rbx
0x18000ccda  mov     [rdi+20h], rbp
0x18000ccde  mov     [rdi+30h], rbx
0x18000cce2  mov     [rdi+28h], ebx
0x18000cce5  call    cs:__imp_CreateTimerQueueTimer
0x18000cceb  test    eax, eax
0x18000cced  jnz     short loc_18000CCF7
0x18000ccef  call    cs:__imp_GetLastError
0x18000ccf5  mov     ebx, eax
0x18000ccf7  lea     rcx, [rsp+58h+var_18]
0x18000ccfc  call    ??1?$CAutoTypeLock@VCSpinLock@@@@QEAA@XZ; CAutoTypeLock<CSpinLock>::~CAutoTypeLock<CSpinLock>(void)
0x18000cd01  mov     rbp, [rsp+58h+arg_8]
0x18000cd06  mov     eax, ebx
0x18000cd08  mov     rbx, [rsp+58h+arg_0]
0x18000cd0d  mov     rsi, [rsp+58h+arg_10]
0x18000cd12  add     rsp, 50h
0x18000cd16  pop     rdi
0x18000cd17  retn
```
