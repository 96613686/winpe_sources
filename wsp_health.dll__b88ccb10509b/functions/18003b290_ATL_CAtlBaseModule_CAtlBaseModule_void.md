# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x18003b290`
- end: `0x18003b2b0`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `32`
- prototype: `void __fastcall(ATL::CAtlBaseModule *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18008b0f0`

## callees

- `0x18003b2f8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003b29d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003b29d`

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
0x18003b290  push    rbx
0x18003b292  sub     rsp, 20h
0x18003b296  mov     rbx, rcx
0x18003b299  add     rcx, 28h ; '('; lpCriticalSection
0x18003b29d  call    cs:__imp_DeleteCriticalSection
0x18003b2a3  mov     rcx, rbx; this
0x18003b2a6  add     rsp, 20h
0x18003b2aa  pop     rbx
0x18003b2ab  jmp     ??1_ATL_BASE_MODULE70@ATL@@QEAA@XZ; ATL::_ATL_BASE_MODULE70::~_ATL_BASE_MODULE70(void)
```
