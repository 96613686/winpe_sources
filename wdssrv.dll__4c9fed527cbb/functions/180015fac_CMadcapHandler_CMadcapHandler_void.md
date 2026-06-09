# CMadcapHandler::~CMadcapHandler(void)

- ea: `0x180015fac`
- end: `0x180015fd7`
- name: `??1CMadcapHandler@@QEAA@XZ`
- size: `43`
- prototype: `void __fastcall(CMadcapHandler *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callers

- `0x18001747c`

## callees

- `0x180008464`
- `0x1800171d0`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180015fcb`

## pseudocode

```c
void __fastcall CMadcapHandler::~CMadcapHandler(struct _RTL_CRITICAL_SECTION *this)
{
  CMadcapHandler::Shutdown(this);
  CTimer<CMadcapHandler>::Delete((__int64)&this[2].LockSemaphore);
  DeleteCriticalSection(this);
}

```

## disassembly

```asm
0x180015fac  push    rbx
0x180015fae  sub     rsp, 20h
0x180015fb2  mov     rbx, rcx
0x180015fb5  call    ?Shutdown@CMadcapHandler@@QEAAKXZ; CMadcapHandler::Shutdown(void)
0x180015fba  lea     rcx, [rbx+68h]
0x180015fbe  call    ?Delete@?$CTimer@VCMadcapHandler@@@@AEAAXXZ; CTimer<CMadcapHandler>::Delete(void)
0x180015fc3  mov     rcx, rbx
0x180015fc6  add     rsp, 20h
0x180015fca  pop     rbx
0x180015fcb  jmp     cs:__imp_DeleteCriticalSection
```
