# CTimer<CTpSrvClients>::Change(ulong,ulong)

- ea: `0x1800107d4`
- end: `0x18001087b`
- name: `?Change@?$CTimer@VCTpSrvClients@@@@QEAAKKK@Z`
- size: `167`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000f688`
- `0x18001038c`

## callees

- `0x180008d38`
- `0x1800107d4`

## import_xrefs

- `KERNEL32!ChangeTimerQueueTimer` at `0x18001084d`
- `KERNEL32!ChangeTimerQueueTimer` at `0x18001084d`
- `KERNEL32!GetCurrentThreadId` at `0x1800107f7`
- `KERNEL32!GetCurrentThreadId` at `0x1800107f7`
- `KERNEL32!SwitchToThread` at `0x180010812`
- `KERNEL32!SwitchToThread` at `0x180010812`
- `KERNEL32!GetLastError` at `0x180010857`
- `KERNEL32!GetLastError` at `0x180010857`

## pseudocode

```c
__int64 __fastcall CTimer<CTpSrvClients>::Change(__int64 a1)
{
  DWORD LastError; // edi
  int v3; // esi
  DWORD CurrentThreadId; // ecx
  signed __int32 v5; // eax
  __int64 v7; // [rsp+20h] [rbp-18h] BYREF
  int v8; // [rsp+28h] [rbp-10h]

  LastError = 0;
  v7 = a1;
  v8 = 0;
  while ( 1 )
  {
    v3 = 0;
    if ( *(_DWORD *)(a1 + 8) )
      break;
LABEL_6:
    SwitchToThread();
  }
  while ( 1 )
  {
    CurrentThreadId = GetCurrentThreadId();
    v5 = _InterlockedCompareExchange((volatile signed __int32 *)a1, CurrentThreadId, 0);
    if ( !v5 || v5 == CurrentThreadId )
      break;
    if ( (unsigned int)++v3 >= *(_DWORD *)(a1 + 8) )
      goto LABEL_6;
  }
  _InterlockedIncrement((volatile signed __int32 *)(a1 + 4));
  v8 = 1;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 40), 0) == 1 )
  {
    LastError = 5023;
  }
  else if ( !ChangeTimerQueueTimer(*(HANDLE *)(a1 + 16), *(HANDLE *)(a1 + 24), 0x1F4u, 0xFFFFFFFE) )
  {
    LastError = GetLastError();
  }
  CAutoTypeLock<CSpinLock>::~CAutoTypeLock<CSpinLock>(&v7);
  return LastError;
}

```

## disassembly

```asm
0x1800107d4  mov     rax, rsp
0x1800107d7  mov     [rax+8], rbx
0x1800107db  mov     [rax+10h], rsi
0x1800107df  push    rdi
0x1800107e0  sub     rsp, 30h
0x1800107e4  xor     edi, edi
0x1800107e6  mov     [rax-18h], rcx
0x1800107ea  mov     [rax-10h], edi
0x1800107ed  mov     rbx, rcx
0x1800107f0  mov     esi, edi
0x1800107f2  cmp     [rbx+8], edi
0x1800107f5  jbe     short loc_180010812
0x1800107f7  call    cs:__imp_GetCurrentThreadId
0x1800107fd  mov     ecx, eax
0x1800107ff  xor     eax, eax
0x180010801  lock cmpxchg [rbx], ecx
0x180010805  jz      short loc_18001081A
0x180010807  cmp     eax, ecx
0x180010809  jz      short loc_18001081A
0x18001080b  inc     esi
0x18001080d  cmp     esi, [rbx+8]
0x180010810  jb      short loc_1800107F7
0x180010812  call    cs:__imp_SwitchToThread
0x180010818  jmp     short loc_1800107F0
0x18001081a  lock inc dword ptr [rbx+4]
0x18001081e  mov     [rsp+38h+var_10], 1
0x180010826  mov     eax, edi
0x180010828  lock xadd [rbx+28h], eax
0x18001082d  cmp     eax, 1
0x180010830  jnz     short loc_180010839
0x180010832  mov     edi, 139Fh
0x180010837  jmp     short loc_18001085F
0x180010839  mov     rdx, [rbx+18h]; Timer
0x18001083d  mov     r9d, 0FFFFFFFEh; Period
0x180010843  mov     rcx, [rbx+10h]; TimerQueue
0x180010847  mov     r8d, 1F4h; DueTime
0x18001084d  call    cs:__imp_ChangeTimerQueueTimer
0x180010853  test    eax, eax
0x180010855  jnz     short loc_18001085F
0x180010857  call    cs:__imp_GetLastError
0x18001085d  mov     edi, eax
0x18001085f  lea     rcx, [rsp+38h+var_18]
0x180010864  call    ??1?$CAutoTypeLock@VCSpinLock@@@@QEAA@XZ; CAutoTypeLock<CSpinLock>::~CAutoTypeLock<CSpinLock>(void)
0x180010869  mov     rbx, [rsp+38h+arg_0]
0x18001086e  mov     eax, edi
0x180010870  mov     rsi, [rsp+38h+arg_8]
0x180010875  add     rsp, 30h
0x180010879  pop     rdi
0x18001087a  retn
```
