# TraceSession::~TraceSession(void)

- ea: `0x18000fd64`
- end: `0x18000fd88`
- name: `??1TraceSession@@QEAA@XZ`
- size: `36`
- prototype: `void __fastcall(TraceSession *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x1800114e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000fd71`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000fd71`

## pseudocode

```c
void __fastcall TraceSession::~TraceSession(TraceSession *this)
{
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  *((_QWORD *)this + 1) = &IRegistryFunctions::`vftable';
}

```

## disassembly

```asm
0x18000fd64  push    rbx
0x18000fd66  sub     rsp, 20h
0x18000fd6a  mov     rbx, rcx
0x18000fd6d  add     rcx, 18h; lpCriticalSection
0x18000fd71  call    cs:__imp_DeleteCriticalSection
0x18000fd77  lea     rax, ??_7IRegistryFunctions@@6B@; const IRegistryFunctions::`vftable'
0x18000fd7e  mov     [rbx+8], rax
0x18000fd82  add     rsp, 20h
0x18000fd86  pop     rbx
0x18000fd87  retn
```
