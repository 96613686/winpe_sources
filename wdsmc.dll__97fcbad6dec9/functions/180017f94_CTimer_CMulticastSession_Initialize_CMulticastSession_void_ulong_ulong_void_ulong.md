# CTimer<CMulticastSession>::Initialize(CMulticastSession *,void *,ulong,ulong,void *,ulong)

- ea: `0x180017f94`
- end: `0x180018057`
- name: `?Initialize@?$CTimer@VCMulticastSession@@@@QEAAKPEAVCMulticastSession@@PEAXKK1K@Z`
- size: `195`
- prototype: `__int64 __fastcall(PVOID Parameter)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180016e70`

## callees

- `0x180008d38`
- `0x180017f94`

## import_xrefs

- `KERNEL32!CreateTimerQueueTimer` at `0x180018024`
- `KERNEL32!CreateTimerQueueTimer` at `0x180018024`
- `KERNEL32!GetCurrentThreadId` at `0x180017fbe`
- `KERNEL32!GetCurrentThreadId` at `0x180017fbe`
- `KERNEL32!SwitchToThread` at `0x180017fd9`
- `KERNEL32!SwitchToThread` at `0x180017fd9`
- `KERNEL32!GetLastError` at `0x18001802e`
- `KERNEL32!GetLastError` at `0x18001802e`

## pseudocode

```c
__int64 __fastcall CTimer<CMulticastSession>::Initialize(PVOID Parameter, __int64 a2)
{
  DWORD LastError; // edi
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
          (WAITORTIMERCALLBACK)CTimer<CMulticastSession>::_TimerCallback,
          Parameter,
          0xEA60u,
          0xFFFFFFFE,
          1u) )
    LastError = GetLastError();
  CAutoTypeLock<CSpinLock>::~CAutoTypeLock<CSpinLock>(&v9);
  return LastError;
}

```

## disassembly

```asm
0x180017f94  mov     rax, rsp
0x180017f97  mov     [rax+8], rbx
0x180017f9b  mov     [rax+10h], rbp
0x180017f9f  mov     [rax+18h], rsi
0x180017fa3  push    rdi
0x180017fa4  sub     rsp, 50h
0x180017fa8  xor     edi, edi
0x180017faa  mov     [rax-18h], rcx
0x180017fae  mov     [rax-10h], edi
0x180017fb1  mov     rbp, rdx
0x180017fb4  mov     rbx, rcx
0x180017fb7  mov     esi, edi
0x180017fb9  cmp     [rbx+8], edi
0x180017fbc  jbe     short loc_180017FD9
0x180017fbe  call    cs:__imp_GetCurrentThreadId
0x180017fc4  mov     ecx, eax
0x180017fc6  xor     eax, eax
0x180017fc8  lock cmpxchg [rbx], ecx
0x180017fcc  jz      short loc_180017FE1
0x180017fce  cmp     eax, ecx
0x180017fd0  jz      short loc_180017FE1
0x180017fd2  inc     esi
0x180017fd4  cmp     esi, [rbx+8]
0x180017fd7  jb      short loc_180017FBE
0x180017fd9  call    cs:__imp_SwitchToThread
0x180017fdf  jmp     short loc_180017FB7
0x180017fe1  lock inc dword ptr [rbx+4]
0x180017fe5  mov     [rsp+58h+Flags], 1; Flags
0x180017fed  lea     rcx, [rbx+18h]; phNewTimer
0x180017ff1  mov     [rsp+58h+Period], 0FFFFFFFEh; Period
0x180017ff9  lea     r8, ?_TimerCallback@?$CTimer@VCMulticastSession@@@@SAXPEAXE@Z; Callback
0x180018000  mov     r9, rbx; Parameter
0x180018003  mov     [rsp+58h+DueTime], 0EA60h; DueTime
0x18001800b  xor     edx, edx; TimerQueue
0x18001800d  mov     [rsp+58h+var_10], 1
0x180018015  mov     [rbx+10h], rdi
0x180018019  mov     [rbx+20h], rbp
0x18001801d  mov     [rbx+30h], rdi
0x180018021  mov     [rbx+28h], edi
0x180018024  call    cs:__imp_CreateTimerQueueTimer
0x18001802a  test    eax, eax
0x18001802c  jnz     short loc_180018036
0x18001802e  call    cs:__imp_GetLastError
0x180018034  mov     edi, eax
0x180018036  lea     rcx, [rsp+58h+var_18]
0x18001803b  call    ??1?$CAutoTypeLock@VCSpinLock@@@@QEAA@XZ; CAutoTypeLock<CSpinLock>::~CAutoTypeLock<CSpinLock>(void)
0x180018040  mov     rbx, [rsp+58h+arg_0]
0x180018045  mov     eax, edi
0x180018047  mov     rbp, [rsp+58h+arg_8]
0x18001804c  mov     rsi, [rsp+58h+arg_10]
0x180018051  add     rsp, 50h
0x180018055  pop     rdi
0x180018056  retn
```
