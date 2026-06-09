# CTimer<CTpSrvTxRate>::_TimerCallback(void *,uchar)

- ea: `0x18000e1e0`
- end: `0x18000e299`
- name: `?_TimerCallback@?$CTimer@VCTpSrvTxRate@@@@SAXPEAXE@Z`
- size: `185`
- prototype: `void __stdcall(PVOID, BOOLEAN)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180008d38`
- `0x18000de34`
- `0x18000e1e0`
- `0x1800227d4`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18000e1fe`
- `KERNEL32!GetCurrentThreadId` at `0x18000e239`
- `KERNEL32!GetCurrentThreadId` at `0x18000e1fe`
- `KERNEL32!GetCurrentThreadId` at `0x18000e239`
- `KERNEL32!SwitchToThread` at `0x18000e219`
- `KERNEL32!SwitchToThread` at `0x18000e219`

## string_xrefs

- `0x18000e24e`: `(ULONG) _InterlockedExchangeAdd((LONG volatile*)&(m_uOwnerThread), 0) == GetCurrentThreadId()`

## pseudocode

```c
void __fastcall CTimer<CTpSrvTxRate>::_TimerCallback(PVOID a1)
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
    CTpSrvTxRate::OnTimer(*((CTpSrvTxRate **)a1 + 4));
  CAutoTypeLock<CSpinLock>::~CAutoTypeLock<CSpinLock>(&v8);
}

```

## disassembly

```asm
0x18000e1e0  mov     [rsp+arg_0], rbx
0x18000e1e5  push    rdi
0x18000e1e6  sub     rsp, 40h
0x18000e1ea  and     [rsp+48h+var_10], 0
0x18000e1ef  mov     rbx, rcx
0x18000e1f2  mov     [rsp+48h+var_18], rcx
0x18000e1f7  xor     edi, edi
0x18000e1f9  cmp     [rbx+8], edi
0x18000e1fc  jbe     short loc_18000E219
0x18000e1fe  call    cs:__imp_GetCurrentThreadId
0x18000e204  mov     ecx, eax
0x18000e206  xor     eax, eax
0x18000e208  lock cmpxchg [rbx], ecx
0x18000e20c  jz      short loc_18000E221
0x18000e20e  cmp     eax, ecx
0x18000e210  jz      short loc_18000E221
0x18000e212  inc     edi
0x18000e214  cmp     edi, [rbx+8]
0x18000e217  jb      short loc_18000E1FE
0x18000e219  call    cs:__imp_SwitchToThread
0x18000e21f  jmp     short loc_18000E1F7
0x18000e221  lock inc dword ptr [rbx+4]
0x18000e225  xor     eax, eax
0x18000e227  lock xadd [rbx+28h], eax
0x18000e22c  xor     edi, edi
0x18000e22e  test    eax, eax
0x18000e230  setz    dil
0x18000e234  and     [rsp+48h+var_10], 0
0x18000e239  call    cs:__imp_GetCurrentThreadId
0x18000e23f  xor     ecx, ecx
0x18000e241  lock xadd [rbx], ecx
0x18000e245  cmp     ecx, eax
0x18000e247  jz      short loc_18000E266
0x18000e249  and     [rsp+48h+var_28], 0
0x18000e24e  lea     r8, aUlongInterlock; "(ULONG) _InterlockedExchangeAdd((LONG v"...
0x18000e255  mov     edx, 99h; unsigned int
0x18000e25a  lea     rcx, aInternalOnecor_0; "internal\\onecorebase\\private\\inc\\ec"...
0x18000e261  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x18000e266  or      eax, 0FFFFFFFFh
0x18000e269  lock xadd [rbx+4], eax
0x18000e26e  cmp     eax, 1
0x18000e271  jnz     short loc_18000E277
0x18000e273  xor     eax, eax
0x18000e275  xchg    eax, [rbx]
0x18000e277  test    edi, edi
0x18000e279  jz      short loc_18000E284
0x18000e27b  mov     rcx, [rbx+20h]; this
0x18000e27f  call    ?OnTimer@CTpSrvTxRate@@QEAAXPEAV?$CTimer@VCTpSrvTxRate@@@@@Z; CTpSrvTxRate::OnTimer(CTimer<CTpSrvTxRate> *)
0x18000e284  lea     rcx, [rsp+48h+var_18]
0x18000e289  call    ??1?$CAutoTypeLock@VCSpinLock@@@@QEAA@XZ; CAutoTypeLock<CSpinLock>::~CAutoTypeLock<CSpinLock>(void)
0x18000e28e  mov     rbx, [rsp+48h+arg_0]
0x18000e293  add     rsp, 40h
0x18000e297  pop     rdi
0x18000e298  retn
```
