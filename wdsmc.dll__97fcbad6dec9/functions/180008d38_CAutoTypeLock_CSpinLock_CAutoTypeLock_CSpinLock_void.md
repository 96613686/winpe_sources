# CAutoTypeLock<CSpinLock>::~CAutoTypeLock<CSpinLock>(void)

- ea: `0x180008d38`
- end: `0x180008dc3`
- name: `??1?$CAutoTypeLock@VCSpinLock@@@@QEAA@XZ`
- size: `139`
- prototype: ``
- caller_count: `29`
- callee_count: `2`
- tags: ``

## callers

- `0x180008738`
- `0x1800089d4`
- `0x180008aa0`
- `0x180008c50`
- `0x18000c6c0`
- `0x18000cc58`
- `0x18000cd20`
- `0x18000d898`
- `0x18000d978`
- `0x18000de34`
- `0x18000e1e0`
- `0x18000f068`
- `0x18000f130`
- `0x18000f480`
- `0x1800106fc`
- `0x1800107d4`
- `0x1800109f0`
- `0x180011098`
- `0x180011160`
- `0x180011220`
- `0x180011610`
- `0x180011a4c`
- `0x180011bbc`
- `0x180014040`
- `0x1800142b0`
- `0x1800150c0`
- `0x180017254`
- `0x180017f94`
- `0x180018060`

## callees

- `0x180008d38`
- `0x1800227d4`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180008d57`
- `KERNEL32!GetCurrentThreadId` at `0x180008d57`

## string_xrefs

- `0x180008d6c`: `(ULONG) _InterlockedExchangeAdd((LONG volatile*)&(m_uOwnerThread), 0) == GetCurrentThreadId()`

## pseudocode

```c
void __fastcall CAutoTypeLock<CSpinLock>::~CAutoTypeLock<CSpinLock>(__int64 a1, __int64 a2, __int64 a3, int a4)
{
  int v4; // eax
  int v6; // eax
  volatile signed __int32 *v7; // rbx
  DWORD CurrentThreadId; // eax

  v4 = *(_DWORD *)(a1 + 8);
  if ( v4 )
  {
    v6 = v4 - 1;
    *(_DWORD *)(a1 + 8) = v6;
    if ( !v6 )
    {
      v7 = *(volatile signed __int32 **)a1;
      CurrentThreadId = GetCurrentThreadId();
      if ( _InterlockedExchangeAdd(v7, 0) != CurrentThreadId )
        WdsAssert(
          "internal\\onecorebase\\private\\inc\\eco\\wds\\locks.h",
          0x99u,
          "(ULONG) _InterlockedExchangeAdd((LONG volatile*)&(m_uOwnerThread), 0) == GetCurrentThreadId()",
          a4,
          0);
      if ( _InterlockedExchangeAdd(v7 + 1, 0xFFFFFFFF) == 1 )
        _InterlockedExchange(v7, 0);
    }
  }
  if ( *(_DWORD *)(a1 + 8) )
    WdsAssert("internal\\onecorebase\\private\\inc\\eco\\wds\\locks.h", 0x16Au, "m_uLockCount == 0", a4, 0);
}

```

## disassembly

```asm
0x180008d38  mov     [rsp+arg_0], rbx
0x180008d3d  push    rdi
0x180008d3e  sub     rsp, 30h
0x180008d42  mov     eax, [rcx+8]
0x180008d45  mov     rdi, rcx
0x180008d48  test    eax, eax
0x180008d4a  jz      short loc_180008D95
0x180008d4c  sub     eax, 1
0x180008d4f  mov     [rcx+8], eax
0x180008d52  jnz     short loc_180008D95
0x180008d54  mov     rbx, [rcx]
0x180008d57  call    cs:__imp_GetCurrentThreadId
0x180008d5d  xor     ecx, ecx
0x180008d5f  lock xadd [rbx], ecx
0x180008d63  cmp     ecx, eax
0x180008d65  jz      short loc_180008D84
0x180008d67  and     [rsp+38h+var_18], 0
0x180008d6c  lea     r8, aUlongInterlock; "(ULONG) _InterlockedExchangeAdd((LONG v"...
0x180008d73  mov     edx, 99h; unsigned int
0x180008d78  lea     rcx, aInternalOnecor_0; "internal\\onecorebase\\private\\inc\\ec"...
0x180008d7f  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x180008d84  or      eax, 0FFFFFFFFh
0x180008d87  lock xadd [rbx+4], eax
0x180008d8c  cmp     eax, 1
0x180008d8f  jnz     short loc_180008D95
0x180008d91  xor     eax, eax
0x180008d93  xchg    eax, [rbx]
0x180008d95  cmp     dword ptr [rdi+8], 0
0x180008d99  jz      short loc_180008DB8
0x180008d9b  and     [rsp+38h+var_18], 0
0x180008da0  lea     r8, aMUlockcount0; "m_uLockCount == 0"
0x180008da7  mov     edx, 16Ah; unsigned int
0x180008dac  lea     rcx, aInternalOnecor_0; "internal\\onecorebase\\private\\inc\\ec"...
0x180008db3  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x180008db8  mov     rbx, [rsp+38h+arg_0]
0x180008dbd  add     rsp, 30h
0x180008dc1  pop     rdi
0x180008dc2  retn
```
