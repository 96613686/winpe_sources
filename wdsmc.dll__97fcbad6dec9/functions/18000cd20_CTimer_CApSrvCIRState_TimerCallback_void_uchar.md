# CTimer<CApSrvCIRState>::_TimerCallback(void *,uchar)

- ea: `0x18000cd20`
- end: `0x18000cdd9`
- name: `?_TimerCallback@?$CTimer@VCApSrvCIRState@@@@SAXPEAXE@Z`
- size: `185`
- prototype: `void __stdcall(PVOID, BOOLEAN)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180008d38`
- `0x18000cb74`
- `0x18000cd20`
- `0x1800227d4`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18000cd3e`
- `KERNEL32!GetCurrentThreadId` at `0x18000cd79`
- `KERNEL32!GetCurrentThreadId` at `0x18000cd3e`
- `KERNEL32!GetCurrentThreadId` at `0x18000cd79`
- `KERNEL32!SwitchToThread` at `0x18000cd59`
- `KERNEL32!SwitchToThread` at `0x18000cd59`

## string_xrefs

- `0x18000cd8e`: `(ULONG) _InterlockedExchangeAdd((LONG volatile*)&(m_uOwnerThread), 0) == GetCurrentThreadId()`

## pseudocode

```c
void __fastcall CTimer<CApSrvCIRState>::_TimerCallback(volatile signed __int32 *a1)
{
  int v2; // edi
  DWORD CurrentThreadId; // ecx
  signed __int32 v4; // eax
  BOOL v5; // edi
  DWORD v6; // eax
  int v7; // r9d
  volatile signed __int32 *v8; // [rsp+30h] [rbp-18h] BYREF
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
    v4 = _InterlockedCompareExchange(a1, CurrentThreadId, 0);
    if ( !v4 || v4 == CurrentThreadId )
      break;
    if ( (unsigned int)++v2 >= *((_DWORD *)a1 + 2) )
      goto LABEL_6;
  }
  _InterlockedIncrement(a1 + 1);
  v5 = _InterlockedExchangeAdd(a1 + 10, 0) == 0;
  v9 = 0;
  v6 = GetCurrentThreadId();
  if ( _InterlockedExchangeAdd(a1, 0) != v6 )
    WdsAssert(
      "internal\\onecorebase\\private\\inc\\eco\\wds\\locks.h",
      0x99u,
      "(ULONG) _InterlockedExchangeAdd((LONG volatile*)&(m_uOwnerThread), 0) == GetCurrentThreadId()",
      v7,
      0);
  if ( _InterlockedExchangeAdd(a1 + 1, 0xFFFFFFFF) == 1 )
    _InterlockedExchange(a1, 0);
  if ( v5 )
    CApSrvCIRState::OnTimer(*((_QWORD *)a1 + 4));
  CAutoTypeLock<CSpinLock>::~CAutoTypeLock<CSpinLock>(&v8);
}

```

## disassembly

```asm
0x18000cd20  mov     [rsp+arg_0], rbx
0x18000cd25  push    rdi
0x18000cd26  sub     rsp, 40h
0x18000cd2a  and     [rsp+48h+var_10], 0
0x18000cd2f  mov     rbx, rcx
0x18000cd32  mov     [rsp+48h+var_18], rcx
0x18000cd37  xor     edi, edi
0x18000cd39  cmp     [rbx+8], edi
0x18000cd3c  jbe     short loc_18000CD59
0x18000cd3e  call    cs:__imp_GetCurrentThreadId
0x18000cd44  mov     ecx, eax
0x18000cd46  xor     eax, eax
0x18000cd48  lock cmpxchg [rbx], ecx
0x18000cd4c  jz      short loc_18000CD61
0x18000cd4e  cmp     eax, ecx
0x18000cd50  jz      short loc_18000CD61
0x18000cd52  inc     edi
0x18000cd54  cmp     edi, [rbx+8]
0x18000cd57  jb      short loc_18000CD3E
0x18000cd59  call    cs:__imp_SwitchToThread
0x18000cd5f  jmp     short loc_18000CD37
0x18000cd61  lock inc dword ptr [rbx+4]
0x18000cd65  xor     eax, eax
0x18000cd67  lock xadd [rbx+28h], eax
0x18000cd6c  xor     edi, edi
0x18000cd6e  test    eax, eax
0x18000cd70  setz    dil
0x18000cd74  and     [rsp+48h+var_10], 0
0x18000cd79  call    cs:__imp_GetCurrentThreadId
0x18000cd7f  xor     ecx, ecx
0x18000cd81  lock xadd [rbx], ecx
0x18000cd85  cmp     ecx, eax
0x18000cd87  jz      short loc_18000CDA6
0x18000cd89  and     [rsp+48h+var_28], 0
0x18000cd8e  lea     r8, aUlongInterlock; "(ULONG) _InterlockedExchangeAdd((LONG v"...
0x18000cd95  mov     edx, 99h; unsigned int
0x18000cd9a  lea     rcx, aInternalOnecor_0; "internal\\onecorebase\\private\\inc\\ec"...
0x18000cda1  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x18000cda6  or      eax, 0FFFFFFFFh
0x18000cda9  lock xadd [rbx+4], eax
0x18000cdae  cmp     eax, 1
0x18000cdb1  jnz     short loc_18000CDB7
0x18000cdb3  xor     eax, eax
0x18000cdb5  xchg    eax, [rbx]
0x18000cdb7  test    edi, edi
0x18000cdb9  jz      short loc_18000CDC4
0x18000cdbb  mov     rcx, [rbx+20h]
0x18000cdbf  call    ?OnTimer@CApSrvCIRState@@QEAAXPEAV?$CTimer@VCApSrvCIRState@@@@@Z; CApSrvCIRState::OnTimer(CTimer<CApSrvCIRState> *)
0x18000cdc4  lea     rcx, [rsp+48h+var_18]
0x18000cdc9  call    ??1?$CAutoTypeLock@VCSpinLock@@@@QEAA@XZ; CAutoTypeLock<CSpinLock>::~CAutoTypeLock<CSpinLock>(void)
0x18000cdce  mov     rbx, [rsp+48h+arg_0]
0x18000cdd3  add     rsp, 40h
0x18000cdd7  pop     rdi
0x18000cdd8  retn
```
