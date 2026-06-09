# CAutoTypeLock<CSpinLock>::~CAutoTypeLock<CSpinLock>(void)

- ea: `0x18000277c`
- end: `0x1800027c1`
- name: `??1?$CAutoTypeLock@VCSpinLock@@@@QEAA@XZ`
- size: `69`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002948`
- `0x180006bf0`
- `0x180008f00`
- `0x18000abac`
- `0x18000ace0`

## callees

- `0x18000277c`
- `0x180006da4`

## import_xrefs

- `WdsCommonLib!?WdsAssert@@YAXPEBDK0HH@Z` at `0x1800027ae`
- `WdsCommonLib!?WdsAssert@@YAXPEBDK0HH@Z` at `0x1800027ae`

## pseudocode

```c
void __fastcall CAutoTypeLock<CSpinLock>::~CAutoTypeLock<CSpinLock>(__int64 a1)
{
  CAutoTypeLock<CSpinLock>::Unlock(a1);
  if ( *(_DWORD *)(a1 + 8) )
    WdsAssert("onecore\\internal\\base\\inc\\private\\eco\\wds\\locks.h", 0x16Bu, "m_uLockCount == 0", 1, 0);
}

```

## disassembly

```asm
0x18000277c  push    rbx
0x18000277e  sub     rsp, 30h
0x180002782  mov     rbx, rcx
0x180002785  call    ?Unlock@?$CAutoTypeLock@VCSpinLock@@@@QEAAXXZ; CAutoTypeLock<CSpinLock>::Unlock(void)
0x18000278a  cmp     dword ptr [rbx+8], 0
0x18000278e  jz      short loc_1800027BA
0x180002790  and     [rsp+38h+var_18], 0
0x180002795  lea     r8, aMUlockcount0; "m_uLockCount == 0"
0x18000279c  mov     r9d, 1
0x1800027a2  lea     rcx, aOnecoreInterna; "onecore\\internal\\base\\inc\\private\\"...
0x1800027a9  mov     edx, 16Bh
0x1800027ae  call    cs:__imp_?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x1800027b5  nop     dword ptr [rax+rax+00h]
0x1800027ba  add     rsp, 30h
0x1800027be  pop     rbx
0x1800027bf  retn
```
