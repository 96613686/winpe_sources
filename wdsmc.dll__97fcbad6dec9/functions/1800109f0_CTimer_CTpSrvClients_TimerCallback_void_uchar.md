# CTimer<CTpSrvClients>::_TimerCallback(void *,uchar)

- ea: `0x1800109f0`
- end: `0x180010ac2`
- name: `?_TimerCallback@?$CTimer@VCTpSrvClients@@@@SAXPEAXE@Z`
- size: `210`
- prototype: `void __stdcall(PVOID, BOOLEAN)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180008d38`
- `0x18001038c`
- `0x18001050c`
- `0x1800109f0`
- `0x1800227d4`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180010a0e`
- `KERNEL32!GetCurrentThreadId` at `0x180010a49`
- `KERNEL32!GetCurrentThreadId` at `0x180010a0e`
- `KERNEL32!GetCurrentThreadId` at `0x180010a49`
- `KERNEL32!SwitchToThread` at `0x180010a29`
- `KERNEL32!SwitchToThread` at `0x180010a29`

## string_xrefs

- `0x180010a5e`: `(ULONG) _InterlockedExchangeAdd((LONG volatile*)&(m_uOwnerThread), 0) == GetCurrentThreadId()`

## pseudocode

```c
void __fastcall CTimer<CTpSrvClients>::_TimerCallback(volatile signed __int32 *a1)
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
    if ( a1 == v8 + 4 )
    {
      CTpSrvClients::OnQCCTimer((CTpSrvClients *)v8);
    }
    else if ( a1 == v8 + 20 )
    {
      CTpSrvClients::OnCleanupTimer((CTpSrvClients *)v8);
    }
  }
  CAutoTypeLock<CSpinLock>::~CAutoTypeLock<CSpinLock>(&v9);
}

```

## disassembly

```asm
0x1800109f0  mov     [rsp+arg_0], rbx
0x1800109f5  push    rdi
0x1800109f6  sub     rsp, 40h
0x1800109fa  and     [rsp+48h+var_10], 0
0x1800109ff  mov     rbx, rcx
0x180010a02  mov     [rsp+48h+var_18], rcx
0x180010a07  xor     edi, edi
0x180010a09  cmp     [rbx+8], edi
0x180010a0c  jbe     short loc_180010A29
0x180010a0e  call    cs:__imp_GetCurrentThreadId
0x180010a14  mov     ecx, eax
0x180010a16  xor     eax, eax
0x180010a18  lock cmpxchg [rbx], ecx
0x180010a1c  jz      short loc_180010A31
0x180010a1e  cmp     eax, ecx
0x180010a20  jz      short loc_180010A31
0x180010a22  inc     edi
0x180010a24  cmp     edi, [rbx+8]
0x180010a27  jb      short loc_180010A0E
0x180010a29  call    cs:__imp_SwitchToThread
0x180010a2f  jmp     short loc_180010A07
0x180010a31  lock inc dword ptr [rbx+4]
0x180010a35  xor     eax, eax
0x180010a37  lock xadd [rbx+28h], eax
0x180010a3c  xor     edi, edi
0x180010a3e  test    eax, eax
0x180010a40  setz    dil
0x180010a44  and     [rsp+48h+var_10], 0
0x180010a49  call    cs:__imp_GetCurrentThreadId
0x180010a4f  xor     ecx, ecx
0x180010a51  lock xadd [rbx], ecx
0x180010a55  cmp     ecx, eax
0x180010a57  jz      short loc_180010A76
0x180010a59  and     [rsp+48h+var_28], 0
0x180010a5e  lea     r8, aUlongInterlock; "(ULONG) _InterlockedExchangeAdd((LONG v"...
0x180010a65  mov     edx, 99h; unsigned int
0x180010a6a  lea     rcx, aInternalOnecor_0; "internal\\onecorebase\\private\\inc\\ec"...
0x180010a71  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x180010a76  or      eax, 0FFFFFFFFh
0x180010a79  lock xadd [rbx+4], eax
0x180010a7e  cmp     eax, 1
0x180010a81  jnz     short loc_180010A87
0x180010a83  xor     eax, eax
0x180010a85  xchg    eax, [rbx]
0x180010a87  test    edi, edi
0x180010a89  jz      short loc_180010AAD
0x180010a8b  mov     rcx, [rbx+20h]; this
0x180010a8f  lea     rax, [rcx+10h]
0x180010a93  cmp     rbx, rax
0x180010a96  jnz     short loc_180010A9F
0x180010a98  call    ?OnQCCTimer@CTpSrvClients@@AEAAXXZ; CTpSrvClients::OnQCCTimer(void)
0x180010a9d  jmp     short loc_180010AAD
0x180010a9f  lea     rax, [rcx+50h]
0x180010aa3  cmp     rbx, rax
0x180010aa6  jnz     short loc_180010AAD
0x180010aa8  call    ?OnCleanupTimer@CTpSrvClients@@AEAAXXZ; CTpSrvClients::OnCleanupTimer(void)
0x180010aad  lea     rcx, [rsp+48h+var_18]
0x180010ab2  call    ??1?$CAutoTypeLock@VCSpinLock@@@@QEAA@XZ; CAutoTypeLock<CSpinLock>::~CAutoTypeLock<CSpinLock>(void)
0x180010ab7  mov     rbx, [rsp+48h+arg_0]
0x180010abc  add     rsp, 40h
0x180010ac0  pop     rdi
0x180010ac1  retn
```
