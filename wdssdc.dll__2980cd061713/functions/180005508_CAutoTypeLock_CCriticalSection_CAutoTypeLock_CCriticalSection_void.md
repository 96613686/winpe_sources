# CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(void)

- ea: `0x180005508`
- end: `0x180005569`
- name: `??1?$CAutoTypeLock@VCCriticalSection@@@@QEAA@XZ`
- size: `97`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `19`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800055b0`
- `0x18000592c`
- `0x180005b10`
- `0x180005c20`
- `0x180005c80`
- `0x180005dac`
- `0x180005ef0`
- `0x180005f70`
- `0x180006210`
- `0x180006320`
- `0x180006460`
- `0x180006598`
- `0x1800068d0`
- `0x180006a60`
- `0x1800070d0`
- `0x180007214`
- `0x1800075e0`
- `0x180007710`
- `0x180007790`

## callees

- `0x180005508`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180005523`
- `KERNEL32!LeaveCriticalSection` at `0x180005523`
- `WdsCommonLib!?WdsAssert@@YAXPEBDK0HH@Z` at `0x180005556`
- `WdsCommonLib!?WdsAssert@@YAXPEBDK0HH@Z` at `0x180005556`

## pseudocode

```c
void __fastcall CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(__int64 a1)
{
  int v1; // eax
  int v3; // eax

  v1 = *(_DWORD *)(a1 + 8);
  if ( v1 )
  {
    v3 = v1 - 1;
    *(_DWORD *)(a1 + 8) = v3;
    if ( !v3 )
      LeaveCriticalSection(*(LPCRITICAL_SECTION *)a1);
  }
  if ( *(_DWORD *)(a1 + 8) )
    WdsAssert("onecore\\internal\\base\\inc\\private\\eco\\wds\\locks.h", 0x16Bu, "m_uLockCount == 0", 1, 0);
}

```

## disassembly

```asm
0x180005508  push    rbx
0x18000550a  sub     rsp, 30h
0x18000550e  mov     eax, [rcx+8]
0x180005511  mov     rbx, rcx
0x180005514  test    eax, eax
0x180005516  jz      short loc_18000552F
0x180005518  sub     eax, 1
0x18000551b  mov     [rcx+8], eax
0x18000551e  jnz     short loc_18000552F
0x180005520  mov     rcx, [rcx]; lpCriticalSection
0x180005523  call    cs:__imp_LeaveCriticalSection
0x18000552a  nop     dword ptr [rax+rax+00h]
0x18000552f  cmp     dword ptr [rbx+8], 0
0x180005533  jz      short loc_180005562
0x180005535  mov     r9d, 1
0x18000553b  mov     [rsp+38h+var_18], 0
0x180005543  lea     r8, aMUlockcount0; "m_uLockCount == 0"
0x18000554a  mov     edx, 16Bh
0x18000554f  lea     rcx, aOnecoreInterna; "onecore\\internal\\base\\inc\\private\\"...
0x180005556  call    cs:__imp_?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x18000555d  nop     dword ptr [rax+rax+00h]
0x180005562  add     rsp, 30h
0x180005566  pop     rbx
0x180005567  retn
```
