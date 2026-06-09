# CTimer<CTpSrvClients>::Initialize(CTpSrvClients *,void *,ulong,ulong,void *,ulong)

- ea: `0x1800106fc`
- end: `0x1800107cc`
- name: `?Initialize@?$CTimer@VCTpSrvClients@@@@QEAAKPEAVCTpSrvClients@@PEAXKK1K@Z`
- size: `208`
- prototype: `__int64 __usercall@<rax>(PVOID Parameter@<rcx>, DWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800148b4`

## callees

- `0x180008d38`
- `0x1800106fc`

## import_xrefs

- `KERNEL32!CreateTimerQueueTimer` at `0x180010793`
- `KERNEL32!CreateTimerQueueTimer` at `0x180010793`
- `KERNEL32!GetCurrentThreadId` at `0x18001072e`
- `KERNEL32!GetCurrentThreadId` at `0x18001072e`
- `KERNEL32!SwitchToThread` at `0x180010749`
- `KERNEL32!SwitchToThread` at `0x180010749`
- `KERNEL32!GetLastError` at `0x18001079d`
- `KERNEL32!GetLastError` at `0x18001079d`

## pseudocode

```c
__int64 __fastcall CTimer<CTpSrvClients>::Initialize(PVOID Parameter, __int64 a2, __int64 a3, DWORD a4, DWORD Period)
{
  DWORD LastError; // ebx
  int v9; // esi
  DWORD CurrentThreadId; // ecx
  signed __int32 v11; // eax
  PVOID v13; // [rsp+40h] [rbp-18h] BYREF
  int v14; // [rsp+48h] [rbp-10h]

  LastError = 0;
  v13 = Parameter;
  v14 = 0;
  while ( 1 )
  {
    v9 = 0;
    if ( *((_DWORD *)Parameter + 2) )
      break;
LABEL_6:
    SwitchToThread();
  }
  while ( 1 )
  {
    CurrentThreadId = GetCurrentThreadId();
    v11 = _InterlockedCompareExchange((volatile signed __int32 *)Parameter, CurrentThreadId, 0);
    if ( !v11 || v11 == CurrentThreadId )
      break;
    if ( (unsigned int)++v9 >= *((_DWORD *)Parameter + 2) )
      goto LABEL_6;
  }
  _InterlockedIncrement((volatile signed __int32 *)Parameter + 1);
  v14 = 1;
  *((_QWORD *)Parameter + 2) = 0;
  *((_QWORD *)Parameter + 4) = a2;
  *((_QWORD *)Parameter + 6) = 0;
  *((_DWORD *)Parameter + 10) = 0;
  if ( !CreateTimerQueueTimer(
          (PHANDLE)Parameter + 3,
          0,
          (WAITORTIMERCALLBACK)CTimer<CTpSrvClients>::_TimerCallback,
          Parameter,
          a4,
          Period,
          1u) )
    LastError = GetLastError();
  CAutoTypeLock<CSpinLock>::~CAutoTypeLock<CSpinLock>(&v13);
  return LastError;
}

```

## disassembly

```asm
0x1800106fc  mov     rax, rsp
0x1800106ff  mov     [rax+8], rbx
0x180010703  mov     [rax+10h], rbp
0x180010707  mov     [rax+18h], rsi
0x18001070b  mov     [rax+20h], rdi
0x18001070f  push    r14
0x180010711  sub     rsp, 50h
0x180010715  xor     ebx, ebx
0x180010717  mov     [rax-18h], rcx
0x18001071b  mov     [rax-10h], ebx
0x18001071e  mov     ebp, r9d
0x180010721  mov     r14, rdx
0x180010724  mov     rdi, rcx
0x180010727  mov     esi, ebx
0x180010729  cmp     [rdi+8], ebx
0x18001072c  jbe     short loc_180010749
0x18001072e  call    cs:__imp_GetCurrentThreadId
0x180010734  mov     ecx, eax
0x180010736  xor     eax, eax
0x180010738  lock cmpxchg [rdi], ecx
0x18001073c  jz      short loc_180010751
0x18001073e  cmp     eax, ecx
0x180010740  jz      short loc_180010751
0x180010742  inc     esi
0x180010744  cmp     esi, [rdi+8]
0x180010747  jb      short loc_18001072E
0x180010749  call    cs:__imp_SwitchToThread
0x18001074f  jmp     short loc_180010727
0x180010751  lock inc dword ptr [rdi+4]
0x180010755  mov     eax, [rsp+58h+arg_20]
0x18001075c  lea     rcx, [rdi+18h]; phNewTimer
0x180010760  mov     [rsp+58h+Flags], 1; Flags
0x180010768  lea     r8, ?_TimerCallback@?$CTimer@VCTpSrvClients@@@@SAXPEAXE@Z; Callback
0x18001076f  mov     [rsp+58h+Period], eax; Period
0x180010773  mov     r9, rdi; Parameter
0x180010776  xor     edx, edx; TimerQueue
0x180010778  mov     [rsp+58h+DueTime], ebp; DueTime
0x18001077c  mov     [rsp+58h+var_10], 1
0x180010784  mov     [rdi+10h], rbx
0x180010788  mov     [rdi+20h], r14
0x18001078c  mov     [rdi+30h], rbx
0x180010790  mov     [rdi+28h], ebx
0x180010793  call    cs:__imp_CreateTimerQueueTimer
0x180010799  test    eax, eax
0x18001079b  jnz     short loc_1800107A5
0x18001079d  call    cs:__imp_GetLastError
0x1800107a3  mov     ebx, eax
0x1800107a5  lea     rcx, [rsp+58h+var_18]
0x1800107aa  call    ??1?$CAutoTypeLock@VCSpinLock@@@@QEAA@XZ; CAutoTypeLock<CSpinLock>::~CAutoTypeLock<CSpinLock>(void)
0x1800107af  mov     rbp, [rsp+58h+arg_8]
0x1800107b4  mov     eax, ebx
0x1800107b6  mov     rbx, [rsp+58h+arg_0]
0x1800107bb  mov     rsi, [rsp+58h+arg_10]
0x1800107c0  mov     rdi, [rsp+58h+arg_18]
0x1800107c5  add     rsp, 50h
0x1800107c9  pop     r14
0x1800107cb  retn
```
