# CTimer<CTpSrvSPM>::_TimerCallback(void *,uchar)

- ea: `0x180011610`
- end: `0x1800116c9`
- name: `?_TimerCallback@?$CTimer@VCTpSrvSPM@@@@SAXPEAXE@Z`
- size: `185`
- prototype: `void __stdcall(PVOID, BOOLEAN)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180008d38`
- `0x180011530`
- `0x180011610`
- `0x1800227d4`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18001162e`
- `KERNEL32!GetCurrentThreadId` at `0x180011669`
- `KERNEL32!GetCurrentThreadId` at `0x18001162e`
- `KERNEL32!GetCurrentThreadId` at `0x180011669`
- `KERNEL32!SwitchToThread` at `0x180011649`
- `KERNEL32!SwitchToThread` at `0x180011649`

## string_xrefs

- `0x18001167e`: `(ULONG) _InterlockedExchangeAdd((LONG volatile*)&(m_uOwnerThread), 0) == GetCurrentThreadId()`

## pseudocode

```c
void __fastcall CTimer<CTpSrvSPM>::_TimerCallback(PVOID a1)
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
    CTpSrvSPM::OnTimer(*((CTpSrvSPM **)a1 + 4));
  CAutoTypeLock<CSpinLock>::~CAutoTypeLock<CSpinLock>(&v8);
}

```

## disassembly

```asm
0x180011610  mov     [rsp+arg_0], rbx
0x180011615  push    rdi
0x180011616  sub     rsp, 40h
0x18001161a  and     [rsp+48h+var_10], 0
0x18001161f  mov     rbx, rcx
0x180011622  mov     [rsp+48h+var_18], rcx
0x180011627  xor     edi, edi
0x180011629  cmp     [rbx+8], edi
0x18001162c  jbe     short loc_180011649
0x18001162e  call    cs:__imp_GetCurrentThreadId
0x180011634  mov     ecx, eax
0x180011636  xor     eax, eax
0x180011638  lock cmpxchg [rbx], ecx
0x18001163c  jz      short loc_180011651
0x18001163e  cmp     eax, ecx
0x180011640  jz      short loc_180011651
0x180011642  inc     edi
0x180011644  cmp     edi, [rbx+8]
0x180011647  jb      short loc_18001162E
0x180011649  call    cs:__imp_SwitchToThread
0x18001164f  jmp     short loc_180011627
0x180011651  lock inc dword ptr [rbx+4]
0x180011655  xor     eax, eax
0x180011657  lock xadd [rbx+28h], eax
0x18001165c  xor     edi, edi
0x18001165e  test    eax, eax
0x180011660  setz    dil
0x180011664  and     [rsp+48h+var_10], 0
0x180011669  call    cs:__imp_GetCurrentThreadId
0x18001166f  xor     ecx, ecx
0x180011671  lock xadd [rbx], ecx
0x180011675  cmp     ecx, eax
0x180011677  jz      short loc_180011696
0x180011679  and     [rsp+48h+var_28], 0
0x18001167e  lea     r8, aUlongInterlock; "(ULONG) _InterlockedExchangeAdd((LONG v"...
0x180011685  mov     edx, 99h; unsigned int
0x18001168a  lea     rcx, aInternalOnecor_0; "internal\\onecorebase\\private\\inc\\ec"...
0x180011691  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x180011696  or      eax, 0FFFFFFFFh
0x180011699  lock xadd [rbx+4], eax
0x18001169e  cmp     eax, 1
0x1800116a1  jnz     short loc_1800116A7
0x1800116a3  xor     eax, eax
0x1800116a5  xchg    eax, [rbx]
0x1800116a7  test    edi, edi
0x1800116a9  jz      short loc_1800116B4
0x1800116ab  mov     rcx, [rbx+20h]; this
0x1800116af  call    ?OnTimer@CTpSrvSPM@@QEAAXPEAV?$CTimer@VCTpSrvSPM@@@@@Z; CTpSrvSPM::OnTimer(CTimer<CTpSrvSPM> *)
0x1800116b4  lea     rcx, [rsp+48h+var_18]
0x1800116b9  call    ??1?$CAutoTypeLock@VCSpinLock@@@@QEAA@XZ; CAutoTypeLock<CSpinLock>::~CAutoTypeLock<CSpinLock>(void)
0x1800116be  mov     rbx, [rsp+48h+arg_0]
0x1800116c3  add     rsp, 40h
0x1800116c7  pop     rdi
0x1800116c8  retn
```
