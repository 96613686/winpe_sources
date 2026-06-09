# CAutoTypeLock<CSpinLock>::Unlock(void)

- ea: `0x180006da4`
- end: `0x180006e1a`
- name: `?Unlock@?$CAutoTypeLock@VCSpinLock@@@@QEAAXXZ`
- size: `118`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000277c`
- `0x180002948`
- `0x180006bf0`
- `0x18000ace0`

## callees

- `0x180006da4`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180006dc2`
- `KERNEL32!GetCurrentThreadId` at `0x180006dc2`
- `WdsCommonLib!?WdsAssert@@YAXPEBDK0HH@Z` at `0x180006df3`
- `WdsCommonLib!?WdsAssert@@YAXPEBDK0HH@Z` at `0x180006df3`

## string_xrefs

- `0x180006de0`: `(ULONG) _InterlockedExchangeAdd((LONG volatile*)&(m_uOwnerThread), 0) == GetCurrentThreadId()`

## pseudocode

```c
__int64 __fastcall CAutoTypeLock<CSpinLock>::Unlock(__int64 a1)
{
  __int64 result; // rax
  volatile signed __int32 *v2; // rbx
  DWORD CurrentThreadId; // eax

  result = *(unsigned int *)(a1 + 8);
  if ( (_DWORD)result )
  {
    result = (unsigned int)(result - 1);
    *(_DWORD *)(a1 + 8) = result;
    if ( !(_DWORD)result )
    {
      v2 = *(volatile signed __int32 **)a1;
      CurrentThreadId = GetCurrentThreadId();
      if ( _InterlockedExchangeAdd(v2, 0) != CurrentThreadId )
        WdsAssert(
          "onecore\\internal\\base\\inc\\private\\eco\\wds\\locks.h",
          0x9Au,
          "(ULONG) _InterlockedExchangeAdd((LONG volatile*)&(m_uOwnerThread), 0) == GetCurrentThreadId()",
          1,
          0);
      result = (unsigned int)_InterlockedExchangeAdd(v2 + 1, 0xFFFFFFFF);
      if ( (_DWORD)result == 1 )
        _InterlockedExchange(v2, 0);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180006da4  mov     [rsp+arg_0], rbx
0x180006da9  push    rdi
0x180006daa  sub     rsp, 30h
0x180006dae  mov     eax, [rcx+8]
0x180006db1  xor     edi, edi
0x180006db3  test    eax, eax
0x180006db5  jz      short loc_180006E0E
0x180006db7  sub     eax, 1
0x180006dba  mov     [rcx+8], eax
0x180006dbd  jnz     short loc_180006E0E
0x180006dbf  mov     rbx, [rcx]
0x180006dc2  call    cs:__imp_GetCurrentThreadId
0x180006dc9  nop     dword ptr [rax+rax+00h]
0x180006dce  mov     ecx, edi
0x180006dd0  lock xadd [rbx], ecx
0x180006dd4  cmp     ecx, eax
0x180006dd6  jz      short loc_180006DFF
0x180006dd8  lea     r9d, [rdi+1]
0x180006ddc  mov     [rsp+38h+var_18], edi
0x180006de0  lea     r8, aUlongInterlock; "(ULONG) _InterlockedExchangeAdd((LONG v"...
0x180006de7  mov     edx, 9Ah
0x180006dec  lea     rcx, aOnecoreInterna; "onecore\\internal\\base\\inc\\private\\"...
0x180006df3  call    cs:__imp_?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x180006dfa  nop     dword ptr [rax+rax+00h]
0x180006dff  or      eax, 0FFFFFFFFh
0x180006e02  lock xadd [rbx+4], eax
0x180006e07  cmp     eax, 1
0x180006e0a  jnz     short loc_180006E0E
0x180006e0c  xchg    edi, [rbx]
0x180006e0e  mov     rbx, [rsp+38h+arg_0]
0x180006e13  add     rsp, 30h
0x180006e17  pop     rdi
0x180006e18  retn
```
