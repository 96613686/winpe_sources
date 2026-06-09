# CTimer<CMulticastServer>::Initialize(CMulticastServer *,void *,ulong,ulong,void *,ulong)

- ea: `0x1800089d4`
- end: `0x180008a97`
- name: `?Initialize@?$CTimer@VCMulticastServer@@@@QEAAKPEAVCMulticastServer@@PEAXKK1K@Z`
- size: `195`
- prototype: `__int64 __fastcall(PVOID Parameter)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800053a0`

## callees

- `0x1800089d4`
- `0x180008d38`

## import_xrefs

- `KERNEL32!CreateTimerQueueTimer` at `0x180008a64`
- `KERNEL32!CreateTimerQueueTimer` at `0x180008a64`
- `KERNEL32!GetCurrentThreadId` at `0x1800089fe`
- `KERNEL32!GetCurrentThreadId` at `0x1800089fe`
- `KERNEL32!SwitchToThread` at `0x180008a19`
- `KERNEL32!SwitchToThread` at `0x180008a19`
- `KERNEL32!GetLastError` at `0x180008a6e`
- `KERNEL32!GetLastError` at `0x180008a6e`

## pseudocode

```c
__int64 __fastcall CTimer<CMulticastServer>::Initialize(PVOID Parameter, __int64 a2)
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
          (WAITORTIMERCALLBACK)CTimer<CMulticastServer>::_TimerCallback,
          Parameter,
          0x7530u,
          0xFFFFFFFE,
          1u) )
    LastError = GetLastError();
  CAutoTypeLock<CSpinLock>::~CAutoTypeLock<CSpinLock>(&v9);
  return LastError;
}

```

## disassembly

```asm
0x1800089d4  mov     rax, rsp
0x1800089d7  mov     [rax+8], rbx
0x1800089db  mov     [rax+10h], rbp
0x1800089df  mov     [rax+18h], rsi
0x1800089e3  push    rdi
0x1800089e4  sub     rsp, 50h
0x1800089e8  xor     edi, edi
0x1800089ea  mov     [rax-18h], rcx
0x1800089ee  mov     [rax-10h], edi
0x1800089f1  mov     rbp, rdx
0x1800089f4  mov     rbx, rcx
0x1800089f7  mov     esi, edi
0x1800089f9  cmp     [rbx+8], edi
0x1800089fc  jbe     short loc_180008A19
0x1800089fe  call    cs:__imp_GetCurrentThreadId
0x180008a04  mov     ecx, eax
0x180008a06  xor     eax, eax
0x180008a08  lock cmpxchg [rbx], ecx
0x180008a0c  jz      short loc_180008A21
0x180008a0e  cmp     eax, ecx
0x180008a10  jz      short loc_180008A21
0x180008a12  inc     esi
0x180008a14  cmp     esi, [rbx+8]
0x180008a17  jb      short loc_1800089FE
0x180008a19  call    cs:__imp_SwitchToThread
0x180008a1f  jmp     short loc_1800089F7
0x180008a21  lock inc dword ptr [rbx+4]
0x180008a25  mov     [rsp+58h+Flags], 1; Flags
0x180008a2d  lea     rcx, [rbx+18h]; phNewTimer
0x180008a31  mov     [rsp+58h+Period], 0FFFFFFFEh; Period
0x180008a39  lea     r8, ?_TimerCallback@?$CTimer@VCMulticastServer@@@@SAXPEAXE@Z; Callback
0x180008a40  mov     r9, rbx; Parameter
0x180008a43  mov     [rsp+58h+DueTime], 7530h; DueTime
0x180008a4b  xor     edx, edx; TimerQueue
0x180008a4d  mov     [rsp+58h+var_10], 1
0x180008a55  mov     [rbx+10h], rdi
0x180008a59  mov     [rbx+20h], rbp
0x180008a5d  mov     [rbx+30h], rdi
0x180008a61  mov     [rbx+28h], edi
0x180008a64  call    cs:__imp_CreateTimerQueueTimer
0x180008a6a  test    eax, eax
0x180008a6c  jnz     short loc_180008A76
0x180008a6e  call    cs:__imp_GetLastError
0x180008a74  mov     edi, eax
0x180008a76  lea     rcx, [rsp+58h+var_18]
0x180008a7b  call    ??1?$CAutoTypeLock@VCSpinLock@@@@QEAA@XZ; CAutoTypeLock<CSpinLock>::~CAutoTypeLock<CSpinLock>(void)
0x180008a80  mov     rbx, [rsp+58h+arg_0]
0x180008a85  mov     eax, edi
0x180008a87  mov     rbp, [rsp+58h+arg_8]
0x180008a8c  mov     rsi, [rsp+58h+arg_10]
0x180008a91  add     rsp, 50h
0x180008a95  pop     rdi
0x180008a96  retn
```
