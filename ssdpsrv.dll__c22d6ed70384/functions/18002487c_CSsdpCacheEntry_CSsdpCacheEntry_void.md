# CSsdpCacheEntry::~CSsdpCacheEntry(void)

- ea: `0x18002487c`
- end: `0x1800248b8`
- name: `??1CSsdpCacheEntry@@QEAA@XZ`
- size: `60`
- prototype: `void __fastcall(CSsdpCacheEntry *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18002482c`

## callees

- `0x180006d70`
- `0x18000a358`
- `0x18001e594`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002489a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002489a`

## pseudocode

```c
void __fastcall CSsdpCacheEntry::~CSsdpCacheEntry(CSsdpCacheEntry *this)
{
  CSsdpCacheEntry::ClearLocationCacheEntry(this);
  FreeSsdpRequest((CSsdpCacheEntry *)((char *)this + 8));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 216));
  *((_QWORD *)this + 15) = &CTimer<CSsdpCacheEntry>::`vftable';
  CTimerBase::~CTimerBase((CSsdpCacheEntry *)((char *)this + 120));
}

```

## disassembly

```asm
0x18002487c  push    rbx
0x18002487e  sub     rsp, 20h
0x180024882  mov     rbx, rcx
0x180024885  call    ?ClearLocationCacheEntry@CSsdpCacheEntry@@AEAAXXZ; CSsdpCacheEntry::ClearLocationCacheEntry(void)
0x18002488a  lea     rcx, [rbx+8]; struct _SSDP_REQUEST *
0x18002488e  call    ?FreeSsdpRequest@@YAXPEAU_SSDP_REQUEST@@@Z; FreeSsdpRequest(_SSDP_REQUEST *)
0x180024893  lea     rcx, [rbx+0D8h]; lpCriticalSection
0x18002489a  call    cs:__imp_DeleteCriticalSection
0x1800248a0  lea     rcx, [rbx+78h]; this
0x1800248a4  lea     rax, ??_7?$CTimer@VCSsdpCacheEntry@@@@6B@; const CTimer<CSsdpCacheEntry>::`vftable'
0x1800248ab  mov     [rcx], rax
0x1800248ae  add     rsp, 20h
0x1800248b2  pop     rbx
0x1800248b3  jmp     ??1CTimerBase@@UEAA@XZ; CTimerBase::~CTimerBase(void)
```
