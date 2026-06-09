# CAutoTypeLock<CList<CRegUdpEndpoint,CCriticalSection>>::~CAutoTypeLock<CList<CRegUdpEndpoint,CCriticalSection>>(void)

- ea: `0x180002358`
- end: `0x1800023ba`
- name: `??1?$CAutoTypeLock@V?$CList@VCRegUdpEndpoint@@VCCriticalSection@@@@@@QEAA@XZ`
- size: `98`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `12`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180002108`
- `0x18000263c`
- `0x180002ab0`
- `0x1800033c0`
- `0x1800034b8`
- `0x180003680`
- `0x180003a18`
- `0x180003bb4`
- `0x180003e04`
- `0x180005354`
- `0x180005ec0`
- `0x180008514`

## callees

- `0x180002358`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180002377`
- `KERNEL32!LeaveCriticalSection` at `0x180002377`
- `WdsServerCommonLib!?WdsAssert@@YAXPEBDK0HH@Z` at `0x1800023a7`
- `WdsServerCommonLib!?WdsAssert@@YAXPEBDK0HH@Z` at `0x1800023a7`

## pseudocode

```c
void __fastcall CAutoTypeLock<CList<CRegUdpEndpoint,CCriticalSection>>::~CAutoTypeLock<CList<CRegUdpEndpoint,CCriticalSection>>(
        _DWORD *a1)
{
  int v1; // eax
  int v3; // eax

  v1 = a1[2];
  if ( v1 )
  {
    v3 = v1 - 1;
    a1[2] = v3;
    if ( !v3 )
      LeaveCriticalSection((LPCRITICAL_SECTION)(*(_QWORD *)a1 + 16LL));
  }
  if ( a1[2] )
    WdsAssert("onecore\\internal\\base\\inc\\private\\eco\\wds\\locks.h", 0x16Bu, "m_uLockCount == 0", 1, 0);
}

```

## disassembly

```asm
0x180002358  push    rbx
0x18000235a  sub     rsp, 30h
0x18000235e  mov     eax, [rcx+8]
0x180002361  mov     rbx, rcx
0x180002364  test    eax, eax
0x180002366  jz      short loc_180002383
0x180002368  sub     eax, 1
0x18000236b  mov     [rcx+8], eax
0x18000236e  jnz     short loc_180002383
0x180002370  mov     rcx, [rcx]
0x180002373  add     rcx, 10h; lpCriticalSection
0x180002377  call    cs:__imp_LeaveCriticalSection
0x18000237e  nop     dword ptr [rax+rax+00h]
0x180002383  cmp     dword ptr [rbx+8], 0
0x180002387  jz      short loc_1800023B3
0x180002389  and     [rsp+38h+var_18], 0
0x18000238e  lea     r8, aMUlockcount0; "m_uLockCount == 0"
0x180002395  mov     r9d, 1
0x18000239b  lea     rcx, aOnecoreInterna; "onecore\\internal\\base\\inc\\private\\"...
0x1800023a2  mov     edx, 16Bh
0x1800023a7  call    cs:__imp_?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x1800023ae  nop     dword ptr [rax+rax+00h]
0x1800023b3  add     rsp, 30h
0x1800023b7  pop     rbx
0x1800023b8  retn
```
