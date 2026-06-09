# CTimer<CTpSrvDataState>::_TimerCallback(void *,uchar)

- ea: `0x1800142b0`
- end: `0x180014369`
- name: `?_TimerCallback@?$CTimer@VCTpSrvDataState@@@@SAXPEAXE@Z`
- size: `185`
- prototype: `void __stdcall(PVOID, BOOLEAN)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180008d38`
- `0x180012a60`
- `0x1800142b0`
- `0x1800227d4`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800142ce`
- `KERNEL32!GetCurrentThreadId` at `0x180014309`
- `KERNEL32!GetCurrentThreadId` at `0x1800142ce`
- `KERNEL32!GetCurrentThreadId` at `0x180014309`
- `KERNEL32!SwitchToThread` at `0x1800142e9`
- `KERNEL32!SwitchToThread` at `0x1800142e9`

## string_xrefs

- `0x18001431e`: `(ULONG) _InterlockedExchangeAdd((LONG volatile*)&(m_uOwnerThread), 0) == GetCurrentThreadId()`

## pseudocode

```c
void __fastcall CTimer<CTpSrvDataState>::_TimerCallback(PVOID a1)
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
    CTpSrvDataState::CleanupFlowWindow(*((CTpSrvDataState **)a1 + 4));
  CAutoTypeLock<CSpinLock>::~CAutoTypeLock<CSpinLock>(&v8);
}

```

## disassembly

```asm
0x1800142b0  mov     [rsp+arg_0], rbx
0x1800142b5  push    rdi
0x1800142b6  sub     rsp, 40h
0x1800142ba  and     [rsp+48h+var_10], 0
0x1800142bf  mov     rbx, rcx
0x1800142c2  mov     [rsp+48h+var_18], rcx
0x1800142c7  xor     edi, edi
0x1800142c9  cmp     [rbx+8], edi
0x1800142cc  jbe     short loc_1800142E9
0x1800142ce  call    cs:__imp_GetCurrentThreadId
0x1800142d4  mov     ecx, eax
0x1800142d6  xor     eax, eax
0x1800142d8  lock cmpxchg [rbx], ecx
0x1800142dc  jz      short loc_1800142F1
0x1800142de  cmp     eax, ecx
0x1800142e0  jz      short loc_1800142F1
0x1800142e2  inc     edi
0x1800142e4  cmp     edi, [rbx+8]
0x1800142e7  jb      short loc_1800142CE
0x1800142e9  call    cs:__imp_SwitchToThread
0x1800142ef  jmp     short loc_1800142C7
0x1800142f1  lock inc dword ptr [rbx+4]
0x1800142f5  xor     eax, eax
0x1800142f7  lock xadd [rbx+28h], eax
0x1800142fc  xor     edi, edi
0x1800142fe  test    eax, eax
0x180014300  setz    dil
0x180014304  and     [rsp+48h+var_10], 0
0x180014309  call    cs:__imp_GetCurrentThreadId
0x18001430f  xor     ecx, ecx
0x180014311  lock xadd [rbx], ecx
0x180014315  cmp     ecx, eax
0x180014317  jz      short loc_180014336
0x180014319  and     [rsp+48h+var_28], 0
0x18001431e  lea     r8, aUlongInterlock; "(ULONG) _InterlockedExchangeAdd((LONG v"...
0x180014325  mov     edx, 99h; unsigned int
0x18001432a  lea     rcx, aInternalOnecor_0; "internal\\onecorebase\\private\\inc\\ec"...
0x180014331  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x180014336  or      eax, 0FFFFFFFFh
0x180014339  lock xadd [rbx+4], eax
0x18001433e  cmp     eax, 1
0x180014341  jnz     short loc_180014347
0x180014343  xor     eax, eax
0x180014345  xchg    eax, [rbx]
0x180014347  test    edi, edi
0x180014349  jz      short loc_180014354
0x18001434b  mov     rcx, [rbx+20h]; this
0x18001434f  call    ?CleanupFlowWindow@CTpSrvDataState@@AEAAXXZ; CTpSrvDataState::CleanupFlowWindow(void)
0x180014354  lea     rcx, [rsp+48h+var_18]
0x180014359  call    ??1?$CAutoTypeLock@VCSpinLock@@@@QEAA@XZ; CAutoTypeLock<CSpinLock>::~CAutoTypeLock<CSpinLock>(void)
0x18001435e  mov     rbx, [rsp+48h+arg_0]
0x180014363  add     rsp, 40h
0x180014367  pop     rdi
0x180014368  retn
```
