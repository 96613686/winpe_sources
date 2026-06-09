# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x18000e2e4`
- end: `0x18000e304`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `32`
- prototype: `void __fastcall(ATL::CAtlBaseModule *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800303b0`

## callees

- `0x18000e338`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000e2f1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000e2f1`

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
0x18000e2e4  push    rbx
0x18000e2e6  sub     rsp, 20h
0x18000e2ea  mov     rbx, rcx
0x18000e2ed  add     rcx, 28h ; '('; lpCriticalSection
0x18000e2f1  call    cs:__imp_DeleteCriticalSection
0x18000e2f7  mov     rcx, rbx; this
0x18000e2fa  add     rsp, 20h
0x18000e2fe  pop     rbx
0x18000e2ff  jmp     ??1_ATL_BASE_MODULE70@ATL@@QEAA@XZ; ATL::_ATL_BASE_MODULE70::~_ATL_BASE_MODULE70(void)
```
