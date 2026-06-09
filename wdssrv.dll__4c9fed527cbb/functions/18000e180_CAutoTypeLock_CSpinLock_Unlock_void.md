# CAutoTypeLock<CSpinLock>::Unlock(void)

- ea: `0x18000e180`
- end: `0x18000e1f6`
- name: `?Unlock@?$CAutoTypeLock@VCSpinLock@@@@QEAAXXZ`
- size: `118`
- prototype: ``
- caller_count: `10`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180008158`
- `0x180008464`
- `0x180009cdc`
- `0x18000d380`
- `0x18000eb30`
- `0x1800102c4`
- `0x180010790`
- `0x18001687c`
- `0x1800171d0`
- `0x180017320`

## callees

- `0x18000e180`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18000e19e`
- `KERNEL32!GetCurrentThreadId` at `0x18000e19e`
- `WdsServerCommonLib!?WdsAssert@@YAXPEBDK0HH@Z` at `0x18000e1cf`
- `WdsServerCommonLib!?WdsAssert@@YAXPEBDK0HH@Z` at `0x18000e1cf`

## string_xrefs

- `0x18000e1bc`: `(ULONG) _InterlockedExchangeAdd((LONG volatile*)&(m_uOwnerThread), 0) == GetCurrentThreadId()`

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
0x18000e180  mov     [rsp+arg_0], rbx
0x18000e185  push    rdi
0x18000e186  sub     rsp, 30h
0x18000e18a  mov     eax, [rcx+8]
0x18000e18d  xor     edi, edi
0x18000e18f  test    eax, eax
0x18000e191  jz      short loc_18000E1EA
0x18000e193  sub     eax, 1
0x18000e196  mov     [rcx+8], eax
0x18000e199  jnz     short loc_18000E1EA
0x18000e19b  mov     rbx, [rcx]
0x18000e19e  call    cs:__imp_GetCurrentThreadId
0x18000e1a5  nop     dword ptr [rax+rax+00h]
0x18000e1aa  mov     ecx, edi
0x18000e1ac  lock xadd [rbx], ecx
0x18000e1b0  cmp     ecx, eax
0x18000e1b2  jz      short loc_18000E1DB
0x18000e1b4  lea     r9d, [rdi+1]
0x18000e1b8  mov     [rsp+38h+var_18], edi
0x18000e1bc  lea     r8, aUlongInterlock; "(ULONG) _InterlockedExchangeAdd((LONG v"...
0x18000e1c3  mov     edx, 9Ah
0x18000e1c8  lea     rcx, aOnecoreInterna; "onecore\\internal\\base\\inc\\private\\"...
0x18000e1cf  call    cs:__imp_?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x18000e1d6  nop     dword ptr [rax+rax+00h]
0x18000e1db  or      eax, 0FFFFFFFFh
0x18000e1de  lock xadd [rbx+4], eax
0x18000e1e3  cmp     eax, 1
0x18000e1e6  jnz     short loc_18000E1EA
0x18000e1e8  xchg    edi, [rbx]
0x18000e1ea  mov     rbx, [rsp+38h+arg_0]
0x18000e1ef  add     rsp, 30h
0x18000e1f3  pop     rdi
0x18000e1f4  retn
```
