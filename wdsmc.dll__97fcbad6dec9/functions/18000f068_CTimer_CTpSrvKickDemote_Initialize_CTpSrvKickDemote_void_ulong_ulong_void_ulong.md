# CTimer<CTpSrvKickDemote>::Initialize(CTpSrvKickDemote *,void *,ulong,ulong,void *,ulong)

- ea: `0x18000f068`
- end: `0x18000f128`
- name: `?Initialize@?$CTimer@VCTpSrvKickDemote@@@@QEAAKPEAVCTpSrvKickDemote@@PEAXKK1K@Z`
- size: `192`
- prototype: `__int64 __fastcall(PVOID Parameter)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000e340`

## callees

- `0x180008d38`
- `0x18000f068`

## import_xrefs

- `KERNEL32!CreateTimerQueueTimer` at `0x18000f0f5`
- `KERNEL32!CreateTimerQueueTimer` at `0x18000f0f5`
- `KERNEL32!GetCurrentThreadId` at `0x18000f092`
- `KERNEL32!GetCurrentThreadId` at `0x18000f092`
- `KERNEL32!SwitchToThread` at `0x18000f0ad`
- `KERNEL32!SwitchToThread` at `0x18000f0ad`
- `KERNEL32!GetLastError` at `0x18000f0ff`
- `KERNEL32!GetLastError` at `0x18000f0ff`

## pseudocode

```c
__int64 __fastcall CTimer<CTpSrvKickDemote>::Initialize(PVOID Parameter, __int64 a2)
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
          (WAITORTIMERCALLBACK)CTimer<CTpSrvKickDemote>::_TimerCallback,
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
0x18000f068  mov     rax, rsp
0x18000f06b  mov     [rax+8], rbx
0x18000f06f  mov     [rax+10h], rbp
0x18000f073  mov     [rax+18h], rsi
0x18000f077  push    rdi
0x18000f078  sub     rsp, 50h
0x18000f07c  xor     ebx, ebx
0x18000f07e  mov     [rax-18h], rcx
0x18000f082  mov     [rax-10h], ebx
0x18000f085  mov     rbp, rdx
0x18000f088  mov     rdi, rcx
0x18000f08b  mov     esi, ebx
0x18000f08d  cmp     [rdi+8], ebx
0x18000f090  jbe     short loc_18000F0AD
0x18000f092  call    cs:__imp_GetCurrentThreadId
0x18000f098  mov     ecx, eax
0x18000f09a  xor     eax, eax
0x18000f09c  lock cmpxchg [rdi], ecx
0x18000f0a0  jz      short loc_18000F0B5
0x18000f0a2  cmp     eax, ecx
0x18000f0a4  jz      short loc_18000F0B5
0x18000f0a6  inc     esi
0x18000f0a8  cmp     esi, [rdi+8]
0x18000f0ab  jb      short loc_18000F092
0x18000f0ad  call    cs:__imp_SwitchToThread
0x18000f0b3  jmp     short loc_18000F08B
0x18000f0b5  lock inc dword ptr [rdi+4]
0x18000f0b9  mov     eax, 0FFFFFFFEh
0x18000f0be  mov     [rsp+58h+Flags], 1; Flags
0x18000f0c6  mov     [rsp+58h+Period], eax; Period
0x18000f0ca  lea     rcx, [rdi+18h]; phNewTimer
0x18000f0ce  mov     r9, rdi; Parameter
0x18000f0d1  mov     [rsp+58h+DueTime], eax; DueTime
0x18000f0d5  lea     r8, ?_TimerCallback@?$CTimer@VCTpSrvKickDemote@@@@SAXPEAXE@Z; Callback
0x18000f0dc  mov     [rsp+58h+var_10], 1
0x18000f0e4  xor     edx, edx; TimerQueue
0x18000f0e6  mov     [rdi+10h], rbx
0x18000f0ea  mov     [rdi+20h], rbp
0x18000f0ee  mov     [rdi+30h], rbx
0x18000f0f2  mov     [rdi+28h], ebx
0x18000f0f5  call    cs:__imp_CreateTimerQueueTimer
0x18000f0fb  test    eax, eax
0x18000f0fd  jnz     short loc_18000F107
0x18000f0ff  call    cs:__imp_GetLastError
0x18000f105  mov     ebx, eax
0x18000f107  lea     rcx, [rsp+58h+var_18]
0x18000f10c  call    ??1?$CAutoTypeLock@VCSpinLock@@@@QEAA@XZ; CAutoTypeLock<CSpinLock>::~CAutoTypeLock<CSpinLock>(void)
0x18000f111  mov     rbp, [rsp+58h+arg_8]
0x18000f116  mov     eax, ebx
0x18000f118  mov     rbx, [rsp+58h+arg_0]
0x18000f11d  mov     rsi, [rsp+58h+arg_10]
0x18000f122  add     rsp, 50h
0x18000f126  pop     rdi
0x18000f127  retn
```
