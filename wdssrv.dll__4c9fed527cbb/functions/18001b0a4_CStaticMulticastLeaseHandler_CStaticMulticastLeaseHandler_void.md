# CStaticMulticastLeaseHandler::~CStaticMulticastLeaseHandler(void)

- ea: `0x18001b0a4`
- end: `0x18001b0c6`
- name: `??1CStaticMulticastLeaseHandler@@QEAA@XZ`
- size: `34`
- prototype: `void __fastcall(CStaticMulticastLeaseHandler *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18001747c`

## callees

- `0x18001b51c`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18001b0ba`

## pseudocode

```c
void __fastcall CStaticMulticastLeaseHandler::~CStaticMulticastLeaseHandler(CStaticMulticastLeaseHandler *this)
{
  CStaticMulticastLeaseHandler::Shutdown(this);
  DeleteCriticalSection((LPCRITICAL_SECTION)this);
}

```

## disassembly

```asm
0x18001b0a4  push    rbx
0x18001b0a6  sub     rsp, 20h
0x18001b0aa  mov     rbx, rcx
0x18001b0ad  call    ?Shutdown@CStaticMulticastLeaseHandler@@QEAAKXZ; CStaticMulticastLeaseHandler::Shutdown(void)
0x18001b0b2  mov     rcx, rbx
0x18001b0b5  add     rsp, 20h
0x18001b0b9  pop     rbx
0x18001b0ba  jmp     cs:__imp_DeleteCriticalSection
```
