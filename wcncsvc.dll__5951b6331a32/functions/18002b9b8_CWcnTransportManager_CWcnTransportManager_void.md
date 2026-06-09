# CWcnTransportManager::~CWcnTransportManager(void)

- ea: `0x18002b9b8`
- end: `0x18002b9ee`
- name: `??1CWcnTransportManager@@QEAA@XZ`
- size: `54`
- prototype: `void __fastcall(CWcnTransportManager *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180002e04`
- `0x1800572f8`

## callees

- `0x180001cd4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002b9c8`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002b9c8`

## pseudocode

```c
void __fastcall CWcnTransportManager::~CWcnTransportManager(CWcnTransportManager *this)
{
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
  `eh vector destructor iterator'(
    (char *)this + 16,
    0x10u,
    7u,
    (void (*)(void *))CWcnTransportManager::tagTRANSPORT_DATA::~tagTRANSPORT_DATA);
}

```

## disassembly

```asm
0x18002b9b8  push    rbx
0x18002b9ba  sub     rsp, 20h
0x18002b9be  mov     rbx, rcx
0x18002b9c1  add     rcx, 98h; lpCriticalSection
0x18002b9c8  call    cs:__imp_DeleteCriticalSection
0x18002b9ce  lea     rcx, [rbx+10h]; void *
0x18002b9d2  lea     r9, ??1tagTRANSPORT_DATA@CWcnTransportManager@@QEAA@XZ; void (*)(void *)
0x18002b9d9  mov     edx, 10h; unsigned __int64
0x18002b9de  lea     r8d, [rdx-9]; unsigned __int64
0x18002b9e2  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18002b9e7  nop
0x18002b9e8  add     rsp, 20h
0x18002b9ec  pop     rbx
0x18002b9ed  retn
```
