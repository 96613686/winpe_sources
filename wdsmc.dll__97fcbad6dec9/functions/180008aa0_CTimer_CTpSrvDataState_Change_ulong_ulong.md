# CTimer<CTpSrvDataState>::Change(ulong,ulong)

- ea: `0x180008aa0`
- end: `0x180008b4f`
- name: `?Change@?$CTimer@VCTpSrvDataState@@@@QEAAKKK@Z`
- size: `175`
- prototype: ``
- caller_count: `18`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180005a4c`
- `0x180008c50`
- `0x18000c850`
- `0x18000c8c0`
- `0x18000cb74`
- `0x18000e968`
- `0x18000ea7c`
- `0x18000ec74`
- `0x180010b40`
- `0x180010be0`
- `0x180010dd0`
- `0x1800112f4`
- `0x180011d70`
- `0x180011f00`
- `0x180011ff0`
- `0x180012a60`
- `0x180017410`
- `0x180017924`

## callees

- `0x180008aa0`
- `0x180008d38`

## import_xrefs

- `KERNEL32!ChangeTimerQueueTimer` at `0x180008b1c`
- `KERNEL32!ChangeTimerQueueTimer` at `0x180008b1c`
- `KERNEL32!GetCurrentThreadId` at `0x180008ac9`
- `KERNEL32!GetCurrentThreadId` at `0x180008ac9`
- `KERNEL32!SwitchToThread` at `0x180008ae4`
- `KERNEL32!SwitchToThread` at `0x180008ae4`
- `KERNEL32!GetLastError` at `0x180008b26`
- `KERNEL32!GetLastError` at `0x180008b26`

## pseudocode

```c
__int64 __fastcall CTimer<CTpSrvDataState>::Change(__int64 a1, ULONG a2)
{
  DWORD LastError; // ebx
  int v5; // esi
  DWORD CurrentThreadId; // ecx
  signed __int32 v7; // eax
  __int64 v9; // [rsp+20h] [rbp-18h] BYREF
  int v10; // [rsp+28h] [rbp-10h]

  LastError = 0;
  v9 = a1;
  v10 = 0;
  while ( 1 )
  {
    v5 = 0;
    if ( *(_DWORD *)(a1 + 8) )
      break;
LABEL_6:
    SwitchToThread();
  }
  while ( 1 )
  {
    CurrentThreadId = GetCurrentThreadId();
    v7 = _InterlockedCompareExchange((volatile signed __int32 *)a1, CurrentThreadId, 0);
    if ( !v7 || v7 == CurrentThreadId )
      break;
    if ( (unsigned int)++v5 >= *(_DWORD *)(a1 + 8) )
      goto LABEL_6;
  }
  _InterlockedIncrement((volatile signed __int32 *)(a1 + 4));
  v10 = 1;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 40), 0) == 1 )
  {
    LastError = 5023;
  }
  else if ( !ChangeTimerQueueTimer(*(HANDLE *)(a1 + 16), *(HANDLE *)(a1 + 24), a2, 0xFFFFFFFE) )
  {
    LastError = GetLastError();
  }
  CAutoTypeLock<CSpinLock>::~CAutoTypeLock<CSpinLock>(&v9);
  return LastError;
}

```

## disassembly

```asm
0x180008aa0  mov     rax, rsp
0x180008aa3  mov     [rax+8], rbx
0x180008aa7  mov     [rax+10h], rbp
0x180008aab  mov     [rax+18h], rsi
0x180008aaf  push    rdi
0x180008ab0  sub     rsp, 30h
0x180008ab4  xor     ebx, ebx
0x180008ab6  mov     [rax-18h], rcx
0x180008aba  mov     [rax-10h], ebx
0x180008abd  mov     ebp, edx
0x180008abf  mov     rdi, rcx
0x180008ac2  mov     esi, ebx
0x180008ac4  cmp     [rdi+8], ebx
0x180008ac7  jbe     short loc_180008AE4
0x180008ac9  call    cs:__imp_GetCurrentThreadId
0x180008acf  mov     ecx, eax
0x180008ad1  xor     eax, eax
0x180008ad3  lock cmpxchg [rdi], ecx
0x180008ad7  jz      short loc_180008AEC
0x180008ad9  cmp     eax, ecx
0x180008adb  jz      short loc_180008AEC
0x180008add  inc     esi
0x180008adf  cmp     esi, [rdi+8]
0x180008ae2  jb      short loc_180008AC9
0x180008ae4  call    cs:__imp_SwitchToThread
0x180008aea  jmp     short loc_180008AC2
0x180008aec  lock inc dword ptr [rdi+4]
0x180008af0  mov     [rsp+38h+var_10], 1
0x180008af8  mov     eax, ebx
0x180008afa  lock xadd [rdi+28h], eax
0x180008aff  cmp     eax, 1
0x180008b02  jnz     short loc_180008B0B
0x180008b04  mov     ebx, 139Fh
0x180008b09  jmp     short loc_180008B2E
0x180008b0b  mov     rdx, [rdi+18h]; Timer
0x180008b0f  mov     r9d, 0FFFFFFFEh; Period
0x180008b15  mov     rcx, [rdi+10h]; TimerQueue
0x180008b19  mov     r8d, ebp; DueTime
0x180008b1c  call    cs:__imp_ChangeTimerQueueTimer
0x180008b22  test    eax, eax
0x180008b24  jnz     short loc_180008B2E
0x180008b26  call    cs:__imp_GetLastError
0x180008b2c  mov     ebx, eax
0x180008b2e  lea     rcx, [rsp+38h+var_18]
0x180008b33  call    ??1?$CAutoTypeLock@VCSpinLock@@@@QEAA@XZ; CAutoTypeLock<CSpinLock>::~CAutoTypeLock<CSpinLock>(void)
0x180008b38  mov     rbp, [rsp+38h+arg_8]
0x180008b3d  mov     eax, ebx
0x180008b3f  mov     rbx, [rsp+38h+arg_0]
0x180008b44  mov     rsi, [rsp+38h+arg_10]
0x180008b49  add     rsp, 30h
0x180008b4d  pop     rdi
0x180008b4e  retn
```
