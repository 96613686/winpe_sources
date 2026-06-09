# CSsdpCacheEntry::~CSsdpCacheEntry(void)

- ea: `0x180026394`
- end: `0x1800263d6`
- name: `??1CSsdpCacheEntry@@QEAA@XZ`
- size: `66`
- prototype: `void __fastcall(CSsdpCacheEntry *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180026344`

## callees

- `0x180008190`
- `0x18000ba2c`
- `0x18001fabc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800263b2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800263b2`

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
0x180026394  push    rbx
0x180026396  sub     rsp, 20h
0x18002639a  mov     rbx, rcx
0x18002639d  call    ?ClearLocationCacheEntry@CSsdpCacheEntry@@AEAAXXZ; CSsdpCacheEntry::ClearLocationCacheEntry(void)
0x1800263a2  lea     rcx, [rbx+8]; struct _SSDP_REQUEST *
0x1800263a6  call    ?FreeSsdpRequest@@YAXPEAU_SSDP_REQUEST@@@Z; FreeSsdpRequest(_SSDP_REQUEST *)
0x1800263ab  lea     rcx, [rbx+0D8h]; lpCriticalSection
0x1800263b2  call    cs:__imp_DeleteCriticalSection
0x1800263b9  nop     dword ptr [rax+rax+00h]
0x1800263be  lea     rcx, [rbx+78h]; this
0x1800263c2  lea     rax, ??_7?$CTimer@VCSsdpCacheEntry@@@@6B@; const CTimer<CSsdpCacheEntry>::`vftable'
0x1800263c9  mov     [rcx], rax
0x1800263cc  add     rsp, 20h
0x1800263d0  pop     rbx
0x1800263d1  jmp     ??1CTimerBase@@UEAA@XZ; CTimerBase::~CTimerBase(void)
```
