# CApSrvCIRState::Shutdown(void)

- ea: `0x18000c6c0`
- end: `0x18000c7bc`
- name: `?Shutdown@CApSrvCIRState@@QEAAKXZ`
- size: `252`
- prototype: `unsigned int __fastcall(CApSrvCIRState *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180017254`
- `0x18001a83c`

## callees

- `0x180008738`
- `0x180008d38`
- `0x18000c404`
- `0x18000c6c0`
- `0x1800227d4`
- `0x180025850`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18000c6f3`
- `KERNEL32!GetCurrentThreadId` at `0x18000c721`
- `KERNEL32!GetCurrentThreadId` at `0x18000c6f3`
- `KERNEL32!GetCurrentThreadId` at `0x18000c721`
- `KERNEL32!SwitchToThread` at `0x18000c70e`
- `KERNEL32!SwitchToThread` at `0x18000c70e`

## string_xrefs

- `0x18000c731`: `(ULONG) _InterlockedExchangeAdd((LONG volatile*)&(m_uOwnerThread), 0) == GetCurrentThreadId()`

## pseudocode

```c
__int64 __fastcall CApSrvCIRState::Shutdown(CApSrvCIRState *this)
{
  char *v1; // rbx
  int v3; // esi
  DWORD CurrentThreadId; // ecx
  signed __int32 v5; // eax
  DWORD v6; // eax
  int v7; // r9d
  const char *v8; // rdx
  unsigned int v9; // eax
  const char *v10; // rdx
  char *v12; // [rsp+30h] [rbp-18h] BYREF
  int v13; // [rsp+38h] [rbp-10h]

  v1 = (char *)this + 80;
  v12 = (char *)this + 80;
  v13 = 0;
  while ( 1 )
  {
    v3 = 0;
    if ( *((_DWORD *)v1 + 2) )
      break;
LABEL_6:
    SwitchToThread();
  }
  while ( 1 )
  {
    CurrentThreadId = GetCurrentThreadId();
    v5 = _InterlockedCompareExchange((volatile signed __int32 *)v1, CurrentThreadId, 0);
    if ( !v5 || v5 == CurrentThreadId )
      break;
    if ( (unsigned int)++v3 >= *((_DWORD *)v1 + 2) )
      goto LABEL_6;
  }
  _InterlockedAdd((volatile signed __int32 *)v1 + 1, 1u);
  _InterlockedExchange((volatile __int32 *)v1 + 10, 1);
  v13 = 0;
  v6 = GetCurrentThreadId();
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v1, 0) != v6 )
    WdsAssert(
      "internal\\onecorebase\\private\\inc\\eco\\wds\\locks.h",
      0x99u,
      "(ULONG) _InterlockedExchangeAdd((LONG volatile*)&(m_uOwnerThread), 0) == GetCurrentThreadId()",
      v7,
      0);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v1 + 1, 0xFFFFFFFF) == 1 )
    _InterlockedExchange((volatile __int32 *)v1, 0);
  CTimer<CMulticastServer>::~CTimer<CMulticastServer>((__int64)v1);
  CAutoTypeLock<CSpinLock>::~CAutoTypeLock<CSpinLock>(&v12);
  ElValidateWin32(0, v8, "base\\eco\\wds\\transport\\server\\mc\\apsrvcirstate.cpp", 0x68u);
  v9 = CApSrvCRR::Shutdown((CApSrvCIRState *)((char *)this + 40));
  ElValidateWin32(v9, v10, "base\\eco\\wds\\transport\\server\\mc\\apsrvcirstate.cpp", 0x69u);
  return 0;
}

```

## disassembly

```asm
0x18000c6c0  mov     rax, rsp
0x18000c6c3  mov     [rax+8], rbx
0x18000c6c7  mov     [rax+10h], rbp
0x18000c6cb  mov     [rax+18h], rsi
0x18000c6cf  mov     [rax+20h], rdi
0x18000c6d3  push    r14
0x18000c6d5  sub     rsp, 40h
0x18000c6d9  xor     edi, edi
0x18000c6db  lea     rbx, [rcx+50h]
0x18000c6df  mov     r14, rcx
0x18000c6e2  mov     [rax-18h], rbx
0x18000c6e6  mov     [rax-10h], edi
0x18000c6e9  lea     ebp, [rdi+1]
0x18000c6ec  mov     esi, edi
0x18000c6ee  cmp     [rbx+8], edi
0x18000c6f1  jbe     short loc_18000C70E
0x18000c6f3  call    cs:__imp_GetCurrentThreadId
0x18000c6f9  mov     ecx, eax
0x18000c6fb  xor     eax, eax
0x18000c6fd  lock cmpxchg [rbx], ecx
0x18000c701  jz      short loc_18000C716
0x18000c703  cmp     eax, ecx
0x18000c705  jz      short loc_18000C716
0x18000c707  add     esi, ebp
0x18000c709  cmp     esi, [rbx+8]
0x18000c70c  jb      short loc_18000C6F3
0x18000c70e  call    cs:__imp_SwitchToThread
0x18000c714  jmp     short loc_18000C6EC
0x18000c716  lock add [rbx+4], ebp
0x18000c71a  xchg    ebp, [rbx+28h]
0x18000c71d  mov     [rsp+48h+var_10], edi
0x18000c721  call    cs:__imp_GetCurrentThreadId
0x18000c727  mov     ecx, edi
0x18000c729  lock xadd [rbx], ecx
0x18000c72d  cmp     ecx, eax
0x18000c72f  jz      short loc_18000C74D
0x18000c731  lea     r8, aUlongInterlock; "(ULONG) _InterlockedExchangeAdd((LONG v"...
0x18000c738  mov     [rsp+48h+var_28], edi; int
0x18000c73c  mov     edx, 99h; unsigned int
0x18000c741  lea     rcx, aInternalOnecor_0; "internal\\onecorebase\\private\\inc\\ec"...
0x18000c748  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x18000c74d  or      eax, 0FFFFFFFFh
0x18000c750  lock xadd [rbx+4], eax
0x18000c755  cmp     eax, 1
0x18000c758  jnz     short loc_18000C75C
0x18000c75a  xchg    edi, [rbx]
0x18000c75c  mov     rcx, rbx
0x18000c75f  call    ??1?$CTimer@VCMulticastServer@@@@QEAA@XZ; CTimer<CMulticastServer>::~CTimer<CMulticastServer>(void)
0x18000c764  lea     rcx, [rsp+48h+var_18]
0x18000c769  call    ??1?$CAutoTypeLock@VCSpinLock@@@@QEAA@XZ; CAutoTypeLock<CSpinLock>::~CAutoTypeLock<CSpinLock>(void)
0x18000c76e  mov     r9d, 68h ; 'h'; unsigned int
0x18000c774  lea     r8, aBaseEcoWdsTran_15; "base\\eco\\wds\\transport\\server\\mc\\"...
0x18000c77b  xor     ecx, ecx; unsigned int
0x18000c77d  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000c782  lea     rcx, [r14+28h]; this
0x18000c786  call    ?Shutdown@CApSrvCRR@@QEAAKXZ; CApSrvCRR::Shutdown(void)
0x18000c78b  mov     ecx, eax; unsigned int
0x18000c78d  lea     r8, aBaseEcoWdsTran_15; "base\\eco\\wds\\transport\\server\\mc\\"...
0x18000c794  mov     r9d, 69h ; 'i'; unsigned int
0x18000c79a  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000c79f  mov     rbx, [rsp+48h+arg_0]
0x18000c7a4  xor     eax, eax
0x18000c7a6  mov     rbp, [rsp+48h+arg_8]
0x18000c7ab  mov     rsi, [rsp+48h+arg_10]
0x18000c7b0  mov     rdi, [rsp+48h+arg_18]
0x18000c7b5  add     rsp, 40h
0x18000c7b9  pop     r14
0x18000c7bb  retn
```
