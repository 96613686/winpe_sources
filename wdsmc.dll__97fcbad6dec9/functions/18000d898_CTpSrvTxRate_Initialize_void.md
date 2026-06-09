# CTpSrvTxRate::Initialize(void)

- ea: `0x18000d898`
- end: `0x18000d970`
- name: `?Initialize@CTpSrvTxRate@@QEAAKXZ`
- size: `216`
- prototype: `unsigned int __fastcall(CTpSrvTxRate *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180011a4c`

## callees

- `0x180008d38`
- `0x18000d898`
- `0x180025850`

## import_xrefs

- `KERNEL32!CreateTimerQueueTimer` at `0x18000d929`
- `KERNEL32!CreateTimerQueueTimer` at `0x18000d929`
- `KERNEL32!GetCurrentThreadId` at `0x18000d8c3`
- `KERNEL32!GetCurrentThreadId` at `0x18000d8c3`
- `KERNEL32!SwitchToThread` at `0x18000d8de`
- `KERNEL32!SwitchToThread` at `0x18000d8de`
- `KERNEL32!GetLastError` at `0x18000d933`
- `KERNEL32!GetLastError` at `0x18000d933`

## pseudocode

```c
__int64 __fastcall CTpSrvTxRate::Initialize(CTpSrvTxRate *this)
{
  char *v1; // rdi
  DWORD LastError; // ebx
  int v4; // esi
  DWORD CurrentThreadId; // ecx
  signed __int32 v6; // eax
  const char *v7; // rdx
  char *v9; // [rsp+40h] [rbp-18h] BYREF
  int v10; // [rsp+48h] [rbp-10h]

  v1 = (char *)this + 32;
  LastError = 0;
  v9 = (char *)this + 32;
  v10 = 0;
  while ( 1 )
  {
    v4 = 0;
    if ( *((_DWORD *)v1 + 2) )
      break;
LABEL_6:
    SwitchToThread();
  }
  while ( 1 )
  {
    CurrentThreadId = GetCurrentThreadId();
    v6 = _InterlockedCompareExchange((volatile signed __int32 *)v1, CurrentThreadId, 0);
    if ( !v6 || v6 == CurrentThreadId )
      break;
    if ( (unsigned int)++v4 >= *((_DWORD *)v1 + 2) )
      goto LABEL_6;
  }
  _InterlockedIncrement((volatile signed __int32 *)v1 + 1);
  v10 = 1;
  *((_QWORD *)v1 + 2) = 0;
  *((_QWORD *)v1 + 4) = this;
  *((_QWORD *)v1 + 6) = 0;
  *((_DWORD *)v1 + 10) = 0;
  if ( !CreateTimerQueueTimer(
          (PHANDLE)v1 + 3,
          0,
          (WAITORTIMERCALLBACK)CTimer<CTpSrvTxRate>::_TimerCallback,
          v1,
          0x64u,
          0xFFFFFFFE,
          1u) )
    LastError = GetLastError();
  CAutoTypeLock<CSpinLock>::~CAutoTypeLock<CSpinLock>(&v9);
  ElValidateWin32(LastError, v7, "base\\eco\\wds\\transport\\server\\mc\\tpsrvtxrate.cpp", 0x47u);
  return LastError;
}

```

## disassembly

```asm
0x18000d898  mov     rax, rsp
0x18000d89b  mov     [rax+8], rbx
0x18000d89f  mov     [rax+10h], rbp
0x18000d8a3  mov     [rax+18h], rsi
0x18000d8a7  push    rdi
0x18000d8a8  sub     rsp, 50h
0x18000d8ac  lea     rdi, [rcx+20h]
0x18000d8b0  xor     ebx, ebx
0x18000d8b2  mov     [rax-18h], rdi
0x18000d8b6  mov     rbp, rcx
0x18000d8b9  mov     [rax-10h], ebx
0x18000d8bc  mov     esi, ebx
0x18000d8be  cmp     [rdi+8], ebx
0x18000d8c1  jbe     short loc_18000D8DE
0x18000d8c3  call    cs:__imp_GetCurrentThreadId
0x18000d8c9  mov     ecx, eax
0x18000d8cb  xor     eax, eax
0x18000d8cd  lock cmpxchg [rdi], ecx
0x18000d8d1  jz      short loc_18000D8E6
0x18000d8d3  cmp     eax, ecx
0x18000d8d5  jz      short loc_18000D8E6
0x18000d8d7  inc     esi
0x18000d8d9  cmp     esi, [rdi+8]
0x18000d8dc  jb      short loc_18000D8C3
0x18000d8de  call    cs:__imp_SwitchToThread
0x18000d8e4  jmp     short loc_18000D8BC
0x18000d8e6  lock inc dword ptr [rdi+4]
0x18000d8ea  mov     [rsp+58h+Flags], 1; Flags
0x18000d8f2  lea     rcx, [rdi+18h]; phNewTimer
0x18000d8f6  mov     [rsp+58h+Period], 0FFFFFFFEh; Period
0x18000d8fe  lea     r8, ?_TimerCallback@?$CTimer@VCTpSrvTxRate@@@@SAXPEAXE@Z; Callback
0x18000d905  mov     r9, rdi; Parameter
0x18000d908  mov     [rsp+58h+DueTime], 64h ; 'd'; DueTime
0x18000d910  xor     edx, edx; TimerQueue
0x18000d912  mov     [rsp+58h+var_10], 1
0x18000d91a  mov     [rdi+10h], rbx
0x18000d91e  mov     [rdi+20h], rbp
0x18000d922  mov     [rdi+30h], rbx
0x18000d926  mov     [rdi+28h], ebx
0x18000d929  call    cs:__imp_CreateTimerQueueTimer
0x18000d92f  test    eax, eax
0x18000d931  jnz     short loc_18000D93B
0x18000d933  call    cs:__imp_GetLastError
0x18000d939  mov     ebx, eax
0x18000d93b  lea     rcx, [rsp+58h+var_18]
0x18000d940  call    ??1?$CAutoTypeLock@VCSpinLock@@@@QEAA@XZ; CAutoTypeLock<CSpinLock>::~CAutoTypeLock<CSpinLock>(void)
0x18000d945  mov     r9d, 47h ; 'G'; unsigned int
0x18000d94b  lea     r8, aBaseEcoWdsTran; "base\\eco\\wds\\transport\\server\\mc\\"...
0x18000d952  mov     ecx, ebx; unsigned int
0x18000d954  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000d959  mov     rbp, [rsp+58h+arg_8]
0x18000d95e  mov     eax, ebx
0x18000d960  mov     rbx, [rsp+58h+arg_0]
0x18000d965  mov     rsi, [rsp+58h+arg_10]
0x18000d96a  add     rsp, 50h
0x18000d96e  pop     rdi
0x18000d96f  retn
```
