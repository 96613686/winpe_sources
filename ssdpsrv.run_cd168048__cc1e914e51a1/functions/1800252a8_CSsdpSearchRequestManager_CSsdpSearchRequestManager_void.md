# CSsdpSearchRequestManager::~CSsdpSearchRequestManager(void)

- ea: `0x1800252a8`
- end: `0x1800252ea`
- name: `??1CSsdpSearchRequestManager@@QEAA@XZ`
- size: `66`
- prototype: `void __fastcall(CSsdpSearchRequestManager *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800381a0`

## callees

- `0x18000dc84`
- `0x1800252f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800252b8`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800252b8`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800252de`

## pseudocode

```c
void __fastcall CSsdpSearchRequestManager::~CSsdpSearchRequestManager(CSsdpSearchRequestManager *this)
{
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 688));
  CSsdpSearchSocketManager::~CSsdpSearchSocketManager((CSsdpSearchRequestManager *)((char *)this + 64));
  CUList<CSsdpSearchRequest>::Clear((char *)this + 40);
  DeleteCriticalSection((LPCRITICAL_SECTION)this);
}

```

## disassembly

```asm
0x1800252a8  push    rbx
0x1800252aa  sub     rsp, 20h
0x1800252ae  mov     rbx, rcx
0x1800252b1  add     rcx, 2B0h; lpCriticalSection
0x1800252b8  call    cs:__imp_DeleteCriticalSection
0x1800252bf  nop     dword ptr [rax+rax+00h]
0x1800252c4  lea     rcx, [rbx+40h]; this
0x1800252c8  call    ??1CSsdpSearchSocketManager@@QEAA@XZ; CSsdpSearchSocketManager::~CSsdpSearchSocketManager(void)
0x1800252cd  lea     rcx, [rbx+28h]
0x1800252d1  call    ?Clear@?$CUList@VCSsdpSearchRequest@@@@QEAAXXZ; CUList<CSsdpSearchRequest>::Clear(void)
0x1800252d6  mov     rcx, rbx
0x1800252d9  add     rsp, 20h
0x1800252dd  pop     rbx
0x1800252de  jmp     cs:__imp_DeleteCriticalSection
```
