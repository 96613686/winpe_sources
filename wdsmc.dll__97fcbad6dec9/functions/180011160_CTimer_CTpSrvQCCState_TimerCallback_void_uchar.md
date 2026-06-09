# CTimer<CTpSrvQCCState>::_TimerCallback(void *,uchar)

- ea: `0x180011160`
- end: `0x180011219`
- name: `?_TimerCallback@?$CTimer@VCTpSrvQCCState@@@@SAXPEAXE@Z`
- size: `185`
- prototype: `void __stdcall(PVOID, BOOLEAN)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180008d38`
- `0x180010fbc`
- `0x180011160`
- `0x1800227d4`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18001117e`
- `KERNEL32!GetCurrentThreadId` at `0x1800111b9`
- `KERNEL32!GetCurrentThreadId` at `0x18001117e`
- `KERNEL32!GetCurrentThreadId` at `0x1800111b9`
- `KERNEL32!SwitchToThread` at `0x180011199`
- `KERNEL32!SwitchToThread` at `0x180011199`

## string_xrefs

- `0x1800111ce`: `(ULONG) _InterlockedExchangeAdd((LONG volatile*)&(m_uOwnerThread), 0) == GetCurrentThreadId()`

## pseudocode

```c
void __fastcall CTimer<CTpSrvQCCState>::_TimerCallback(volatile signed __int32 *a1)
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
    CTpSrvQCCState::OnTimer(*((_QWORD *)a1 + 4));
  CAutoTypeLock<CSpinLock>::~CAutoTypeLock<CSpinLock>(&v8);
}

```

## disassembly

```asm
0x180011160  mov     [rsp+arg_0], rbx
0x180011165  push    rdi
0x180011166  sub     rsp, 40h
0x18001116a  and     [rsp+48h+var_10], 0
0x18001116f  mov     rbx, rcx
0x180011172  mov     [rsp+48h+var_18], rcx
0x180011177  xor     edi, edi
0x180011179  cmp     [rbx+8], edi
0x18001117c  jbe     short loc_180011199
0x18001117e  call    cs:__imp_GetCurrentThreadId
0x180011184  mov     ecx, eax
0x180011186  xor     eax, eax
0x180011188  lock cmpxchg [rbx], ecx
0x18001118c  jz      short loc_1800111A1
0x18001118e  cmp     eax, ecx
0x180011190  jz      short loc_1800111A1
0x180011192  inc     edi
0x180011194  cmp     edi, [rbx+8]
0x180011197  jb      short loc_18001117E
0x180011199  call    cs:__imp_SwitchToThread
0x18001119f  jmp     short loc_180011177
0x1800111a1  lock inc dword ptr [rbx+4]
0x1800111a5  xor     eax, eax
0x1800111a7  lock xadd [rbx+28h], eax
0x1800111ac  xor     edi, edi
0x1800111ae  test    eax, eax
0x1800111b0  setz    dil
0x1800111b4  and     [rsp+48h+var_10], 0
0x1800111b9  call    cs:__imp_GetCurrentThreadId
0x1800111bf  xor     ecx, ecx
0x1800111c1  lock xadd [rbx], ecx
0x1800111c5  cmp     ecx, eax
0x1800111c7  jz      short loc_1800111E6
0x1800111c9  and     [rsp+48h+var_28], 0
0x1800111ce  lea     r8, aUlongInterlock; "(ULONG) _InterlockedExchangeAdd((LONG v"...
0x1800111d5  mov     edx, 99h; unsigned int
0x1800111da  lea     rcx, aInternalOnecor_0; "internal\\onecorebase\\private\\inc\\ec"...
0x1800111e1  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x1800111e6  or      eax, 0FFFFFFFFh
0x1800111e9  lock xadd [rbx+4], eax
0x1800111ee  cmp     eax, 1
0x1800111f1  jnz     short loc_1800111F7
0x1800111f3  xor     eax, eax
0x1800111f5  xchg    eax, [rbx]
0x1800111f7  test    edi, edi
0x1800111f9  jz      short loc_180011204
0x1800111fb  mov     rcx, [rbx+20h]
0x1800111ff  call    ?OnTimer@CTpSrvQCCState@@QEAAXPEAV?$CTimer@VCTpSrvQCCState@@@@@Z; CTpSrvQCCState::OnTimer(CTimer<CTpSrvQCCState> *)
0x180011204  lea     rcx, [rsp+48h+var_18]
0x180011209  call    ??1?$CAutoTypeLock@VCSpinLock@@@@QEAA@XZ; CAutoTypeLock<CSpinLock>::~CAutoTypeLock<CSpinLock>(void)
0x18001120e  mov     rbx, [rsp+48h+arg_0]
0x180011213  add     rsp, 40h
0x180011217  pop     rdi
0x180011218  retn
```
