# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x18000be74`
- end: `0x18000be94`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `32`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180011460`

## callees

- `0x18000bec8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000be81`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000be81`

## pseudocode

```c
void __fastcall ATL::CAtlBaseModule::~CAtlBaseModule(struct _RTL_CRITICAL_SECTION *this)
{
  DeleteCriticalSection(this + 1);
  ATL::_ATL_BASE_MODULE70::~_ATL_BASE_MODULE70((ATL::_ATL_BASE_MODULE70 *)this);
}

```

## disassembly

```asm
0x18000be74  push    rbx
0x18000be76  sub     rsp, 20h
0x18000be7a  mov     rbx, rcx
0x18000be7d  add     rcx, 28h ; '('; lpCriticalSection
0x18000be81  call    cs:__imp_DeleteCriticalSection
0x18000be87  mov     rcx, rbx; this
0x18000be8a  add     rsp, 20h
0x18000be8e  pop     rbx
0x18000be8f  jmp     ??1_ATL_BASE_MODULE70@ATL@@QEAA@XZ; ATL::_ATL_BASE_MODULE70::~_ATL_BASE_MODULE70(void)
```
