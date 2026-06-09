# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x180033994`
- end: `0x1800339b4`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `32`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180036c60`

## callees

- `0x1800339fc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800339a1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800339a1`

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
0x180033994  push    rbx
0x180033996  sub     rsp, 20h
0x18003399a  mov     rbx, rcx
0x18003399d  add     rcx, 28h ; '('; lpCriticalSection
0x1800339a1  call    cs:__imp_DeleteCriticalSection
0x1800339a7  mov     rcx, rbx; this
0x1800339aa  add     rsp, 20h
0x1800339ae  pop     rbx
0x1800339af  jmp     ??1_ATL_BASE_MODULE70@ATL@@QEAA@XZ; ATL::_ATL_BASE_MODULE70::~_ATL_BASE_MODULE70(void)
```
