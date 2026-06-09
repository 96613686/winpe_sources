# CListPtr<CRegUdpEndpoint,CCriticalSection>::~CListPtr<CRegUdpEndpoint,CCriticalSection>(void)

- ea: `0x180002438`
- end: `0x180002486`
- name: `??1?$CListPtr@VCRegUdpEndpoint@@VCCriticalSection@@@@QEAA@XZ`
- size: `78`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800034b8`

## callees

- `0x180002438`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18000247a`
- `WdsServerCommonLib!?WdsAssert@@YAXPEBDK0HH@Z` at `0x180002465`
- `WdsServerCommonLib!?WdsAssert@@YAXPEBDK0HH@Z` at `0x180002465`

## pseudocode

```c
void __fastcall CListPtr<CRegUdpEndpoint,CCriticalSection>::~CListPtr<CRegUdpEndpoint,CCriticalSection>(__int64 a1)
{
  if ( *(_DWORD *)(a1 + 16) )
    WdsAssert("onecore\\internal\\base\\inc\\private\\eco\\wds\\ListPtr.h", 0xF3u, "m_uNodeCount == 0", 1, 0);
  DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 24));
}

```

## disassembly

```asm
0x180002438  push    rbx
0x18000243a  sub     rsp, 30h
0x18000243e  cmp     dword ptr [rcx+10h], 0
0x180002442  mov     rbx, rcx
0x180002445  jz      short loc_180002471
0x180002447  and     [rsp+38h+var_18], 0
0x18000244c  lea     r8, aMUnodecount0; "m_uNodeCount == 0"
0x180002453  mov     r9d, 1
0x180002459  lea     rcx, aOnecoreInterna_4; "onecore\\internal\\base\\inc\\private\\"...
0x180002460  mov     edx, 0F3h
0x180002465  call    cs:__imp_?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x18000246c  nop     dword ptr [rax+rax+00h]
0x180002471  lea     rcx, [rbx+18h]
0x180002475  add     rsp, 30h
0x180002479  pop     rbx
0x18000247a  jmp     cs:__imp_DeleteCriticalSection
```
