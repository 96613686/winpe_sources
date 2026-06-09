# CTimer<CTpSrvQCCState>::Initialize(CTpSrvQCCState *,void *,ulong,ulong,void *,ulong)

- ea: `0x180011098`
- end: `0x180011158`
- name: `?Initialize@?$CTimer@VCTpSrvQCCState@@@@QEAAKPEAVCTpSrvQCCState@@PEAXKK1K@Z`
- size: `192`
- prototype: `__int64 __fastcall(PVOID Parameter)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800148b4`

## callees

- `0x180008d38`
- `0x180011098`

## import_xrefs

- `KERNEL32!CreateTimerQueueTimer` at `0x180011125`
- `KERNEL32!CreateTimerQueueTimer` at `0x180011125`
- `KERNEL32!GetCurrentThreadId` at `0x1800110c2`
- `KERNEL32!GetCurrentThreadId` at `0x1800110c2`
- `KERNEL32!SwitchToThread` at `0x1800110dd`
- `KERNEL32!SwitchToThread` at `0x1800110dd`
- `KERNEL32!GetLastError` at `0x18001112f`
- `KERNEL32!GetLastError` at `0x18001112f`

## pseudocode

```c
__int64 __fastcall CTimer<CTpSrvQCCState>::Initialize(PVOID Parameter, __int64 a2)
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
          (WAITORTIMERCALLBACK)CTimer<CTpSrvQCCState>::_TimerCallback,
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
0x180011098  mov     rax, rsp
0x18001109b  mov     [rax+8], rbx
0x18001109f  mov     [rax+10h], rbp
0x1800110a3  mov     [rax+18h], rsi
0x1800110a7  push    rdi
0x1800110a8  sub     rsp, 50h
0x1800110ac  xor     ebx, ebx
0x1800110ae  mov     [rax-18h], rcx
0x1800110b2  mov     [rax-10h], ebx
0x1800110b5  mov     rbp, rdx
0x1800110b8  mov     rdi, rcx
0x1800110bb  mov     esi, ebx
0x1800110bd  cmp     [rdi+8], ebx
0x1800110c0  jbe     short loc_1800110DD
0x1800110c2  call    cs:__imp_GetCurrentThreadId
0x1800110c8  mov     ecx, eax
0x1800110ca  xor     eax, eax
0x1800110cc  lock cmpxchg [rdi], ecx
0x1800110d0  jz      short loc_1800110E5
0x1800110d2  cmp     eax, ecx
0x1800110d4  jz      short loc_1800110E5
0x1800110d6  inc     esi
0x1800110d8  cmp     esi, [rdi+8]
0x1800110db  jb      short loc_1800110C2
0x1800110dd  call    cs:__imp_SwitchToThread
0x1800110e3  jmp     short loc_1800110BB
0x1800110e5  lock inc dword ptr [rdi+4]
0x1800110e9  mov     eax, 0FFFFFFFEh
0x1800110ee  mov     [rsp+58h+Flags], 1; Flags
0x1800110f6  mov     [rsp+58h+Period], eax; Period
0x1800110fa  lea     rcx, [rdi+18h]; phNewTimer
0x1800110fe  mov     r9, rdi; Parameter
0x180011101  mov     [rsp+58h+DueTime], eax; DueTime
0x180011105  lea     r8, ?_TimerCallback@?$CTimer@VCTpSrvQCCState@@@@SAXPEAXE@Z; Callback
0x18001110c  mov     [rsp+58h+var_10], 1
0x180011114  xor     edx, edx; TimerQueue
0x180011116  mov     [rdi+10h], rbx
0x18001111a  mov     [rdi+20h], rbp
0x18001111e  mov     [rdi+30h], rbx
0x180011122  mov     [rdi+28h], ebx
0x180011125  call    cs:__imp_CreateTimerQueueTimer
0x18001112b  test    eax, eax
0x18001112d  jnz     short loc_180011137
0x18001112f  call    cs:__imp_GetLastError
0x180011135  mov     ebx, eax
0x180011137  lea     rcx, [rsp+58h+var_18]
0x18001113c  call    ??1?$CAutoTypeLock@VCSpinLock@@@@QEAA@XZ; CAutoTypeLock<CSpinLock>::~CAutoTypeLock<CSpinLock>(void)
0x180011141  mov     rbp, [rsp+58h+arg_8]
0x180011146  mov     eax, ebx
0x180011148  mov     rbx, [rsp+58h+arg_0]
0x18001114d  mov     rsi, [rsp+58h+arg_10]
0x180011152  add     rsp, 50h
0x180011156  pop     rdi
0x180011157  retn
```
