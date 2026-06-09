# CTimer<CTpSrvKickDemote>::Shutdown(void)

- ea: `0x18000f130`
- end: `0x18000f1ec`
- name: `?Shutdown@?$CTimer@VCTpSrvKickDemote@@@@QEAAKXZ`
- size: `188`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000e454`
- `0x18000f5cc`

## callees

- `0x180008738`
- `0x180008d38`
- `0x18000f130`
- `0x1800227d4`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18000f15a`
- `KERNEL32!GetCurrentThreadId` at `0x18000f188`
- `KERNEL32!GetCurrentThreadId` at `0x18000f15a`
- `KERNEL32!GetCurrentThreadId` at `0x18000f188`
- `KERNEL32!SwitchToThread` at `0x18000f175`
- `KERNEL32!SwitchToThread` at `0x18000f175`

## string_xrefs

- `0x18000f198`: `(ULONG) _InterlockedExchangeAdd((LONG volatile*)&(m_uOwnerThread), 0) == GetCurrentThreadId()`

## pseudocode

```c
__int64 __fastcall CTimer<CTpSrvKickDemote>::Shutdown(__int64 a1)
{
  int v2; // esi
  DWORD CurrentThreadId; // ecx
  signed __int32 v4; // eax
  DWORD v5; // eax
  int v6; // r9d
  __int64 v8; // [rsp+30h] [rbp-18h] BYREF
  int v9; // [rsp+38h] [rbp-10h]

  v8 = a1;
  v9 = 0;
  while ( 1 )
  {
    v2 = 0;
    if ( *(_DWORD *)(a1 + 8) )
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
    if ( (unsigned int)++v2 >= *(_DWORD *)(a1 + 8) )
      goto LABEL_6;
  }
  _InterlockedAdd((volatile signed __int32 *)(a1 + 4), 1u);
  _InterlockedExchange((volatile __int32 *)(a1 + 40), 1);
  v9 = 0;
  v5 = GetCurrentThreadId();
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)a1, 0) != v5 )
    WdsAssert(
      "internal\\onecorebase\\private\\inc\\eco\\wds\\locks.h",
      0x99u,
      "(ULONG) _InterlockedExchangeAdd((LONG volatile*)&(m_uOwnerThread), 0) == GetCurrentThreadId()",
      v6,
      0);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 4), 0xFFFFFFFF) == 1 )
    _InterlockedExchange((volatile __int32 *)a1, 0);
  CTimer<CMulticastServer>::~CTimer<CMulticastServer>(a1);
  CAutoTypeLock<CSpinLock>::~CAutoTypeLock<CSpinLock>(&v8);
  return 0;
}

```

## disassembly

```asm
0x18000f130  mov     rax, rsp
0x18000f133  mov     [rax+8], rbx
0x18000f137  mov     [rax+10h], rbp
0x18000f13b  mov     [rax+18h], rsi
0x18000f13f  push    rdi
0x18000f140  sub     rsp, 40h
0x18000f144  xor     edi, edi
0x18000f146  mov     [rax-18h], rcx
0x18000f14a  mov     rbx, rcx
0x18000f14d  mov     [rax-10h], edi
0x18000f150  lea     ebp, [rdi+1]
0x18000f153  mov     esi, edi
0x18000f155  cmp     [rbx+8], edi
0x18000f158  jbe     short loc_18000F175
0x18000f15a  call    cs:__imp_GetCurrentThreadId
0x18000f160  mov     ecx, eax
0x18000f162  xor     eax, eax
0x18000f164  lock cmpxchg [rbx], ecx
0x18000f168  jz      short loc_18000F17D
0x18000f16a  cmp     eax, ecx
0x18000f16c  jz      short loc_18000F17D
0x18000f16e  add     esi, ebp
0x18000f170  cmp     esi, [rbx+8]
0x18000f173  jb      short loc_18000F15A
0x18000f175  call    cs:__imp_SwitchToThread
0x18000f17b  jmp     short loc_18000F153
0x18000f17d  lock add [rbx+4], ebp
0x18000f181  xchg    ebp, [rbx+28h]
0x18000f184  mov     [rsp+48h+var_10], edi
0x18000f188  call    cs:__imp_GetCurrentThreadId
0x18000f18e  mov     ecx, edi
0x18000f190  lock xadd [rbx], ecx
0x18000f194  cmp     ecx, eax
0x18000f196  jz      short loc_18000F1B4
0x18000f198  lea     r8, aUlongInterlock; "(ULONG) _InterlockedExchangeAdd((LONG v"...
0x18000f19f  mov     [rsp+48h+var_28], edi; int
0x18000f1a3  mov     edx, 99h; unsigned int
0x18000f1a8  lea     rcx, aInternalOnecor_0; "internal\\onecorebase\\private\\inc\\ec"...
0x18000f1af  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x18000f1b4  or      eax, 0FFFFFFFFh
0x18000f1b7  lock xadd [rbx+4], eax
0x18000f1bc  cmp     eax, 1
0x18000f1bf  jnz     short loc_18000F1C3
0x18000f1c1  xchg    edi, [rbx]
0x18000f1c3  mov     rcx, rbx
0x18000f1c6  call    ??1?$CTimer@VCMulticastServer@@@@QEAA@XZ; CTimer<CMulticastServer>::~CTimer<CMulticastServer>(void)
0x18000f1cb  lea     rcx, [rsp+48h+var_18]
0x18000f1d0  call    ??1?$CAutoTypeLock@VCSpinLock@@@@QEAA@XZ; CAutoTypeLock<CSpinLock>::~CAutoTypeLock<CSpinLock>(void)
0x18000f1d5  mov     rbx, [rsp+48h+arg_0]
0x18000f1da  xor     eax, eax
0x18000f1dc  mov     rbp, [rsp+48h+arg_8]
0x18000f1e1  mov     rsi, [rsp+48h+arg_10]
0x18000f1e6  add     rsp, 40h
0x18000f1ea  pop     rdi
0x18000f1eb  retn
```
