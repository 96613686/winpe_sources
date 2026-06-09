# CTpSrvTxRate::Shutdown(void)

- ea: `0x18000d978`
- end: `0x18000da46`
- name: `?Shutdown@CTpSrvTxRate@@QEAAKXZ`
- size: `206`
- prototype: `unsigned int __fastcall(CTpSrvTxRate *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18001198c`
- `0x180011bbc`

## callees

- `0x180008738`
- `0x180008d38`
- `0x18000d978`
- `0x1800227d4`
- `0x180025850`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18000d9a3`
- `KERNEL32!GetCurrentThreadId` at `0x18000d9d1`
- `KERNEL32!GetCurrentThreadId` at `0x18000d9a3`
- `KERNEL32!GetCurrentThreadId` at `0x18000d9d1`
- `KERNEL32!SwitchToThread` at `0x18000d9be`
- `KERNEL32!SwitchToThread` at `0x18000d9be`

## string_xrefs

- `0x18000d9e1`: `(ULONG) _InterlockedExchangeAdd((LONG volatile*)&(m_uOwnerThread), 0) == GetCurrentThreadId()`

## pseudocode

```c
unsigned int __fastcall CTpSrvTxRate::Shutdown(CTpSrvTxRate *this)
{
  char *v1; // rbx
  int v2; // esi
  DWORD CurrentThreadId; // ecx
  signed __int32 v4; // eax
  DWORD v5; // eax
  int v6; // r9d
  const char *v7; // rdx
  char *v9; // [rsp+30h] [rbp-18h] BYREF
  int v10; // [rsp+38h] [rbp-10h]

  v1 = (char *)this + 32;
  v9 = (char *)this + 32;
  v10 = 0;
  while ( 1 )
  {
    v2 = 0;
    if ( *((_DWORD *)v1 + 2) )
      break;
LABEL_6:
    SwitchToThread();
  }
  while ( 1 )
  {
    CurrentThreadId = GetCurrentThreadId();
    v4 = _InterlockedCompareExchange((volatile signed __int32 *)v1, CurrentThreadId, 0);
    if ( !v4 || v4 == CurrentThreadId )
      break;
    if ( (unsigned int)++v2 >= *((_DWORD *)v1 + 2) )
      goto LABEL_6;
  }
  _InterlockedAdd((volatile signed __int32 *)v1 + 1, 1u);
  _InterlockedExchange((volatile __int32 *)v1 + 10, 1);
  v10 = 0;
  v5 = GetCurrentThreadId();
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v1, 0) != v5 )
    WdsAssert(
      "internal\\onecorebase\\private\\inc\\eco\\wds\\locks.h",
      0x99u,
      "(ULONG) _InterlockedExchangeAdd((LONG volatile*)&(m_uOwnerThread), 0) == GetCurrentThreadId()",
      v6,
      0);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v1 + 1, 0xFFFFFFFF) == 1 )
    _InterlockedExchange((volatile __int32 *)v1, 0);
  CTimer<CMulticastServer>::~CTimer<CMulticastServer>((__int64)v1);
  CAutoTypeLock<CSpinLock>::~CAutoTypeLock<CSpinLock>(&v9);
  return ElValidateWin32(0, v7, "base\\eco\\wds\\transport\\server\\mc\\tpsrvtxrate.cpp", 0x68u);
}

```

## disassembly

```asm
0x18000d978  mov     rax, rsp
0x18000d97b  mov     [rax+8], rbx
0x18000d97f  mov     [rax+10h], rbp
0x18000d983  mov     [rax+18h], rsi
0x18000d987  push    rdi
0x18000d988  sub     rsp, 40h
0x18000d98c  xor     edi, edi
0x18000d98e  lea     rbx, [rcx+20h]
0x18000d992  mov     [rax-18h], rbx
0x18000d996  mov     [rax-10h], edi
0x18000d999  lea     ebp, [rdi+1]
0x18000d99c  mov     esi, edi
0x18000d99e  cmp     [rbx+8], edi
0x18000d9a1  jbe     short loc_18000D9BE
0x18000d9a3  call    cs:__imp_GetCurrentThreadId
0x18000d9a9  mov     ecx, eax
0x18000d9ab  xor     eax, eax
0x18000d9ad  lock cmpxchg [rbx], ecx
0x18000d9b1  jz      short loc_18000D9C6
0x18000d9b3  cmp     eax, ecx
0x18000d9b5  jz      short loc_18000D9C6
0x18000d9b7  add     esi, ebp
0x18000d9b9  cmp     esi, [rbx+8]
0x18000d9bc  jb      short loc_18000D9A3
0x18000d9be  call    cs:__imp_SwitchToThread
0x18000d9c4  jmp     short loc_18000D99C
0x18000d9c6  lock add [rbx+4], ebp
0x18000d9ca  xchg    ebp, [rbx+28h]
0x18000d9cd  mov     [rsp+48h+var_10], edi
0x18000d9d1  call    cs:__imp_GetCurrentThreadId
0x18000d9d7  mov     ecx, edi
0x18000d9d9  lock xadd [rbx], ecx
0x18000d9dd  cmp     ecx, eax
0x18000d9df  jz      short loc_18000D9FD
0x18000d9e1  lea     r8, aUlongInterlock; "(ULONG) _InterlockedExchangeAdd((LONG v"...
0x18000d9e8  mov     [rsp+48h+var_28], edi; int
0x18000d9ec  mov     edx, 99h; unsigned int
0x18000d9f1  lea     rcx, aInternalOnecor_0; "internal\\onecorebase\\private\\inc\\ec"...
0x18000d9f8  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x18000d9fd  or      eax, 0FFFFFFFFh
0x18000da00  lock xadd [rbx+4], eax
0x18000da05  cmp     eax, 1
0x18000da08  jnz     short loc_18000DA0C
0x18000da0a  xchg    edi, [rbx]
0x18000da0c  mov     rcx, rbx
0x18000da0f  call    ??1?$CTimer@VCMulticastServer@@@@QEAA@XZ; CTimer<CMulticastServer>::~CTimer<CMulticastServer>(void)
0x18000da14  lea     rcx, [rsp+48h+var_18]
0x18000da19  call    ??1?$CAutoTypeLock@VCSpinLock@@@@QEAA@XZ; CAutoTypeLock<CSpinLock>::~CAutoTypeLock<CSpinLock>(void)
0x18000da1e  mov     r9d, 68h ; 'h'; unsigned int
0x18000da24  lea     r8, aBaseEcoWdsTran; "base\\eco\\wds\\transport\\server\\mc\\"...
0x18000da2b  xor     ecx, ecx; unsigned int
0x18000da2d  mov     rbx, [rsp+48h+arg_0]
0x18000da32  mov     rbp, [rsp+48h+arg_8]
0x18000da37  mov     rsi, [rsp+48h+arg_10]
0x18000da3c  add     rsp, 40h
0x18000da40  pop     rdi
0x18000da41  jmp     ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
```
