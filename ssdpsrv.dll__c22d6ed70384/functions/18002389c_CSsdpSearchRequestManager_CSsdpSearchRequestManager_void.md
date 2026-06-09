# CSsdpSearchRequestManager::~CSsdpSearchRequestManager(void)

- ea: `0x18002389c`
- end: `0x1800238d3`
- name: `??1CSsdpSearchRequestManager@@QEAA@XZ`
- size: `55`
- prototype: `void __fastcall(CSsdpSearchRequestManager *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180035650`

## callees

- `0x18000c158`
- `0x1800238dc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800238ac`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800238ac`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800238cc`

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
0x18002389c  push    rbx
0x18002389e  sub     rsp, 20h
0x1800238a2  mov     rbx, rcx
0x1800238a5  add     rcx, 2B0h; lpCriticalSection
0x1800238ac  call    cs:__imp_DeleteCriticalSection
0x1800238b2  lea     rcx, [rbx+40h]; this
0x1800238b6  call    ??1CSsdpSearchSocketManager@@QEAA@XZ; CSsdpSearchSocketManager::~CSsdpSearchSocketManager(void)
0x1800238bb  lea     rcx, [rbx+28h]
0x1800238bf  call    ?Clear@?$CUList@VCSsdpSearchRequest@@@@QEAAXXZ; CUList<CSsdpSearchRequest>::Clear(void)
0x1800238c4  mov     rcx, rbx
0x1800238c7  add     rsp, 20h
0x1800238cb  pop     rbx
0x1800238cc  jmp     cs:__imp_DeleteCriticalSection
```
