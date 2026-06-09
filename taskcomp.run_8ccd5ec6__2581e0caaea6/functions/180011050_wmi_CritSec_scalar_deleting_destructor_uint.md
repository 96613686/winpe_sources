# wmi::CritSec::`scalar deleting destructor'(uint)

- ea: `0x180011050`
- end: `0x180011077`
- name: `??_GCritSec@wmi@@QEAAPEAXI@Z`
- size: `39`
- prototype: `void *__fastcall(wmi::CritSec *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18001431c`
- `0x18001c300`

## callees

- `0x180007988`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180011059`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180011059`

## pseudocode

```c
struct _RTL_CRITICAL_SECTION *__fastcall wmi::CritSec::`scalar deleting destructor'(struct _RTL_CRITICAL_SECTION *this)
{
  DeleteCriticalSection(this);
  operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180011050  push    rbx
0x180011052  sub     rsp, 20h
0x180011056  mov     rbx, rcx
0x180011059  call    cs:__imp_DeleteCriticalSection
0x180011060  nop     dword ptr [rax+rax+00h]
0x180011065  mov     rcx, rbx; Block
0x180011068  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001106d  mov     rax, rbx
0x180011070  add     rsp, 20h
0x180011074  pop     rbx
0x180011075  retn
```
