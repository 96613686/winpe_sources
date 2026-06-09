# CTimer<CTpSrvKickDemote>::_TimerCallback(void *,uchar)

- ea: `0x18000f480`
- end: `0x18000f558`
- name: `?_TimerCallback@?$CTimer@VCTpSrvKickDemote@@@@SAXPEAXE@Z`
- size: `216`
- prototype: `void __stdcall(PVOID, BOOLEAN)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180008d38`
- `0x18000ea7c`
- `0x18000ec74`
- `0x18000f480`
- `0x1800227d4`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18000f49e`
- `KERNEL32!GetCurrentThreadId` at `0x18000f4d9`
- `KERNEL32!GetCurrentThreadId` at `0x18000f49e`
- `KERNEL32!GetCurrentThreadId` at `0x18000f4d9`
- `KERNEL32!SwitchToThread` at `0x18000f4b9`
- `KERNEL32!SwitchToThread` at `0x18000f4b9`

## string_xrefs

- `0x18000f4ee`: `(ULONG) _InterlockedExchangeAdd((LONG volatile*)&(m_uOwnerThread), 0) == GetCurrentThreadId()`

## pseudocode

```c
void __fastcall CTimer<CTpSrvKickDemote>::_TimerCallback(volatile signed __int32 *a1)
{
  int v2; // edi
  DWORD CurrentThreadId; // ecx
  signed __int32 v4; // eax
  BOOL v5; // edi
  DWORD v6; // eax
  int v7; // r9d
  volatile signed __int32 *v8; // rcx
  volatile signed __int32 *v9; // [rsp+30h] [rbp-18h] BYREF
  int v10; // [rsp+38h] [rbp-10h]

  v10 = 0;
  v9 = a1;
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
  v10 = 0;
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
  {
    v8 = (volatile signed __int32 *)*((_QWORD *)a1 + 4);
    if ( a1 == v8 + 1370 )
    {
      CTpSrvKickDemote::ProcessKick((CTpSrvKickDemote *)v8);
    }
    else if ( a1 == v8 + 1384 )
    {
      CTpSrvKickDemote::ProcessDemote((CTpSrvKickDemote *)v8);
    }
  }
  CAutoTypeLock<CSpinLock>::~CAutoTypeLock<CSpinLock>(&v9);
}

```

## disassembly

```asm
0x18000f480  mov     [rsp+arg_0], rbx
0x18000f485  push    rdi
0x18000f486  sub     rsp, 40h
0x18000f48a  and     [rsp+48h+var_10], 0
0x18000f48f  mov     rbx, rcx
0x18000f492  mov     [rsp+48h+var_18], rcx
0x18000f497  xor     edi, edi
0x18000f499  cmp     [rbx+8], edi
0x18000f49c  jbe     short loc_18000F4B9
0x18000f49e  call    cs:__imp_GetCurrentThreadId
0x18000f4a4  mov     ecx, eax
0x18000f4a6  xor     eax, eax
0x18000f4a8  lock cmpxchg [rbx], ecx
0x18000f4ac  jz      short loc_18000F4C1
0x18000f4ae  cmp     eax, ecx
0x18000f4b0  jz      short loc_18000F4C1
0x18000f4b2  inc     edi
0x18000f4b4  cmp     edi, [rbx+8]
0x18000f4b7  jb      short loc_18000F49E
0x18000f4b9  call    cs:__imp_SwitchToThread
0x18000f4bf  jmp     short loc_18000F497
0x18000f4c1  lock inc dword ptr [rbx+4]
0x18000f4c5  xor     eax, eax
0x18000f4c7  lock xadd [rbx+28h], eax
0x18000f4cc  xor     edi, edi
0x18000f4ce  test    eax, eax
0x18000f4d0  setz    dil
0x18000f4d4  and     [rsp+48h+var_10], 0
0x18000f4d9  call    cs:__imp_GetCurrentThreadId
0x18000f4df  xor     ecx, ecx
0x18000f4e1  lock xadd [rbx], ecx
0x18000f4e5  cmp     ecx, eax
0x18000f4e7  jz      short loc_18000F506
0x18000f4e9  and     [rsp+48h+var_28], 0
0x18000f4ee  lea     r8, aUlongInterlock; "(ULONG) _InterlockedExchangeAdd((LONG v"...
0x18000f4f5  mov     edx, 99h; unsigned int
0x18000f4fa  lea     rcx, aInternalOnecor_0; "internal\\onecorebase\\private\\inc\\ec"...
0x18000f501  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x18000f506  or      eax, 0FFFFFFFFh
0x18000f509  lock xadd [rbx+4], eax
0x18000f50e  cmp     eax, 1
0x18000f511  jnz     short loc_18000F517
0x18000f513  xor     eax, eax
0x18000f515  xchg    eax, [rbx]
0x18000f517  test    edi, edi
0x18000f519  jz      short loc_18000F543
0x18000f51b  mov     rcx, [rbx+20h]; this
0x18000f51f  lea     rax, [rcx+1568h]
0x18000f526  cmp     rbx, rax
0x18000f529  jnz     short loc_18000F532
0x18000f52b  call    ?ProcessKick@CTpSrvKickDemote@@AEAAXXZ; CTpSrvKickDemote::ProcessKick(void)
0x18000f530  jmp     short loc_18000F543
0x18000f532  lea     rax, [rcx+15A0h]
0x18000f539  cmp     rbx, rax
0x18000f53c  jnz     short loc_18000F543
0x18000f53e  call    ?ProcessDemote@CTpSrvKickDemote@@AEAAXXZ; CTpSrvKickDemote::ProcessDemote(void)
0x18000f543  lea     rcx, [rsp+48h+var_18]
0x18000f548  call    ??1?$CAutoTypeLock@VCSpinLock@@@@QEAA@XZ; CAutoTypeLock<CSpinLock>::~CAutoTypeLock<CSpinLock>(void)
0x18000f54d  mov     rbx, [rsp+48h+arg_0]
0x18000f552  add     rsp, 40h
0x18000f556  pop     rdi
0x18000f557  retn
```
