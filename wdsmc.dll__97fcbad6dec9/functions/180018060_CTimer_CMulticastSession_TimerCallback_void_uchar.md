# CTimer<CMulticastSession>::_TimerCallback(void *,uchar)

- ea: `0x180018060`
- end: `0x180018119`
- name: `?_TimerCallback@?$CTimer@VCMulticastSession@@@@SAXPEAXE@Z`
- size: `185`
- prototype: `void __stdcall(PVOID, BOOLEAN)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180008d38`
- `0x180017924`
- `0x180018060`
- `0x1800227d4`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18001807e`
- `KERNEL32!GetCurrentThreadId` at `0x1800180b9`
- `KERNEL32!GetCurrentThreadId` at `0x18001807e`
- `KERNEL32!GetCurrentThreadId` at `0x1800180b9`
- `KERNEL32!SwitchToThread` at `0x180018099`
- `KERNEL32!SwitchToThread` at `0x180018099`

## string_xrefs

- `0x1800180ce`: `(ULONG) _InterlockedExchangeAdd((LONG volatile*)&(m_uOwnerThread), 0) == GetCurrentThreadId()`

## pseudocode

```c
void __fastcall CTimer<CMulticastSession>::_TimerCallback(PVOID a1)
{
  int v2; // edi
  DWORD CurrentThreadId; // ecx
  signed __int32 v4; // eax
  BOOL v5; // edi
  DWORD v6; // eax
  int v7; // r9d
  PVOID v8; // [rsp+30h] [rbp-18h] BYREF
  int v9; // [rsp+38h] [rbp-10h]

  v9 = 0;
  v8 = a1;
  while ( 1 )
  {
    v2 = 0;
    if ( *((_DWORD *)a1 + 2) )
      break;
LABEL_6:
    SwitchToThread();
  }
  while ( 1 )
  {
    CurrentThreadId = GetCurrentThreadId();
    v4 = _InterlockedCompareExchange((volatile signed __int32 *)a1, CurrentThreadId, 0);
    if ( !v4 || v4 == CurrentThreadId )
      break;
    if ( (unsigned int)++v2 >= *((_DWORD *)a1 + 2) )
      goto LABEL_6;
  }
  _InterlockedIncrement((volatile signed __int32 *)a1 + 1);
  v5 = _InterlockedExchangeAdd((volatile signed __int32 *)a1 + 10, 0) == 0;
  v9 = 0;
  v6 = GetCurrentThreadId();
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)a1, 0) != v6 )
    WdsAssert(
      "internal\\onecorebase\\private\\inc\\eco\\wds\\locks.h",
      0x99u,
      "(ULONG) _InterlockedExchangeAdd((LONG volatile*)&(m_uOwnerThread), 0) == GetCurrentThreadId()",
      v7,
      0);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)a1 + 1, 0xFFFFFFFF) == 1 )
    _InterlockedExchange((volatile __int32 *)a1, 0);
  if ( v5 )
    CMulticastSession::OnTimer(*((CMulticastSession **)a1 + 4));
  CAutoTypeLock<CSpinLock>::~CAutoTypeLock<CSpinLock>(&v8);
}

```

## disassembly

```asm
0x180018060  mov     [rsp+arg_0], rbx
0x180018065  push    rdi
0x180018066  sub     rsp, 40h
0x18001806a  and     [rsp+48h+var_10], 0
0x18001806f  mov     rbx, rcx
0x180018072  mov     [rsp+48h+var_18], rcx
0x180018077  xor     edi, edi
0x180018079  cmp     [rbx+8], edi
0x18001807c  jbe     short loc_180018099
0x18001807e  call    cs:__imp_GetCurrentThreadId
0x180018084  mov     ecx, eax
0x180018086  xor     eax, eax
0x180018088  lock cmpxchg [rbx], ecx
0x18001808c  jz      short loc_1800180A1
0x18001808e  cmp     eax, ecx
0x180018090  jz      short loc_1800180A1
0x180018092  inc     edi
0x180018094  cmp     edi, [rbx+8]
0x180018097  jb      short loc_18001807E
0x180018099  call    cs:__imp_SwitchToThread
0x18001809f  jmp     short loc_180018077
0x1800180a1  lock inc dword ptr [rbx+4]
0x1800180a5  xor     eax, eax
0x1800180a7  lock xadd [rbx+28h], eax
0x1800180ac  xor     edi, edi
0x1800180ae  test    eax, eax
0x1800180b0  setz    dil
0x1800180b4  and     [rsp+48h+var_10], 0
0x1800180b9  call    cs:__imp_GetCurrentThreadId
0x1800180bf  xor     ecx, ecx
0x1800180c1  lock xadd [rbx], ecx
0x1800180c5  cmp     ecx, eax
0x1800180c7  jz      short loc_1800180E6
0x1800180c9  and     [rsp+48h+var_28], 0
0x1800180ce  lea     r8, aUlongInterlock; "(ULONG) _InterlockedExchangeAdd((LONG v"...
0x1800180d5  mov     edx, 99h; unsigned int
0x1800180da  lea     rcx, aInternalOnecor_0; "internal\\onecorebase\\private\\inc\\ec"...
0x1800180e1  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x1800180e6  or      eax, 0FFFFFFFFh
0x1800180e9  lock xadd [rbx+4], eax
0x1800180ee  cmp     eax, 1
0x1800180f1  jnz     short loc_1800180F7
0x1800180f3  xor     eax, eax
0x1800180f5  xchg    eax, [rbx]
0x1800180f7  test    edi, edi
0x1800180f9  jz      short loc_180018104
0x1800180fb  mov     rcx, [rbx+20h]; this
0x1800180ff  call    ?OnTimer@CMulticastSession@@QEAAXPEAV?$CTimer@VCMulticastSession@@@@@Z; CMulticastSession::OnTimer(CTimer<CMulticastSession> *)
0x180018104  lea     rcx, [rsp+48h+var_18]
0x180018109  call    ??1?$CAutoTypeLock@VCSpinLock@@@@QEAA@XZ; CAutoTypeLock<CSpinLock>::~CAutoTypeLock<CSpinLock>(void)
0x18001810e  mov     rbx, [rsp+48h+arg_0]
0x180018113  add     rsp, 40h
0x180018117  pop     rdi
0x180018118  retn
```
