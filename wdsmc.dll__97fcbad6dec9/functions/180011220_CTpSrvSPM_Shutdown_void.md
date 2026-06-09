# CTpSrvSPM::Shutdown(void)

- ea: `0x180011220`
- end: `0x1800112ee`
- name: `?Shutdown@CTpSrvSPM@@QEAAKXZ`
- size: `206`
- prototype: `unsigned int __fastcall(CTpSrvSPM *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18001198c`
- `0x180011bbc`

## callees

- `0x180008738`
- `0x180008d38`
- `0x180011220`
- `0x1800227d4`
- `0x180025850`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18001124b`
- `KERNEL32!GetCurrentThreadId` at `0x180011279`
- `KERNEL32!GetCurrentThreadId` at `0x18001124b`
- `KERNEL32!GetCurrentThreadId` at `0x180011279`
- `KERNEL32!SwitchToThread` at `0x180011266`
- `KERNEL32!SwitchToThread` at `0x180011266`

## string_xrefs

- `0x180011289`: `(ULONG) _InterlockedExchangeAdd((LONG volatile*)&(m_uOwnerThread), 0) == GetCurrentThreadId()`

## pseudocode

```c
unsigned int __fastcall CTpSrvSPM::Shutdown(CTpSrvSPM *this)
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

  v1 = (char *)this + 80;
  v9 = (char *)this + 80;
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
  return ElValidateWin32(0, v7, "base\\eco\\wds\\transport\\server\\mc\\tpsrvspm.cpp", 0x54u);
}

```

## disassembly

```asm
0x180011220  mov     rax, rsp
0x180011223  mov     [rax+8], rbx
0x180011227  mov     [rax+10h], rbp
0x18001122b  mov     [rax+18h], rsi
0x18001122f  push    rdi
0x180011230  sub     rsp, 40h
0x180011234  xor     edi, edi
0x180011236  lea     rbx, [rcx+50h]
0x18001123a  mov     [rax-18h], rbx
0x18001123e  mov     [rax-10h], edi
0x180011241  lea     ebp, [rdi+1]
0x180011244  mov     esi, edi
0x180011246  cmp     [rbx+8], edi
0x180011249  jbe     short loc_180011266
0x18001124b  call    cs:__imp_GetCurrentThreadId
0x180011251  mov     ecx, eax
0x180011253  xor     eax, eax
0x180011255  lock cmpxchg [rbx], ecx
0x180011259  jz      short loc_18001126E
0x18001125b  cmp     eax, ecx
0x18001125d  jz      short loc_18001126E
0x18001125f  add     esi, ebp
0x180011261  cmp     esi, [rbx+8]
0x180011264  jb      short loc_18001124B
0x180011266  call    cs:__imp_SwitchToThread
0x18001126c  jmp     short loc_180011244
0x18001126e  lock add [rbx+4], ebp
0x180011272  xchg    ebp, [rbx+28h]
0x180011275  mov     [rsp+48h+var_10], edi
0x180011279  call    cs:__imp_GetCurrentThreadId
0x18001127f  mov     ecx, edi
0x180011281  lock xadd [rbx], ecx
0x180011285  cmp     ecx, eax
0x180011287  jz      short loc_1800112A5
0x180011289  lea     r8, aUlongInterlock; "(ULONG) _InterlockedExchangeAdd((LONG v"...
0x180011290  mov     [rsp+48h+var_28], edi; int
0x180011294  mov     edx, 99h; unsigned int
0x180011299  lea     rcx, aInternalOnecor_0; "internal\\onecorebase\\private\\inc\\ec"...
0x1800112a0  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x1800112a5  or      eax, 0FFFFFFFFh
0x1800112a8  lock xadd [rbx+4], eax
0x1800112ad  cmp     eax, 1
0x1800112b0  jnz     short loc_1800112B4
0x1800112b2  xchg    edi, [rbx]
0x1800112b4  mov     rcx, rbx
0x1800112b7  call    ??1?$CTimer@VCMulticastServer@@@@QEAA@XZ; CTimer<CMulticastServer>::~CTimer<CMulticastServer>(void)
0x1800112bc  lea     rcx, [rsp+48h+var_18]
0x1800112c1  call    ??1?$CAutoTypeLock@VCSpinLock@@@@QEAA@XZ; CAutoTypeLock<CSpinLock>::~CAutoTypeLock<CSpinLock>(void)
0x1800112c6  mov     r9d, 54h ; 'T'; unsigned int
0x1800112cc  lea     r8, aBaseEcoWdsTran_7; "base\\eco\\wds\\transport\\server\\mc\\"...
0x1800112d3  xor     ecx, ecx; unsigned int
0x1800112d5  mov     rbx, [rsp+48h+arg_0]
0x1800112da  mov     rbp, [rsp+48h+arg_8]
0x1800112df  mov     rsi, [rsp+48h+arg_10]
0x1800112e4  add     rsp, 40h
0x1800112e8  pop     rdi
0x1800112e9  jmp     ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
```
