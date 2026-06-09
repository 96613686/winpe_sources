# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x18003173c`
- end: `0x18003175c`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `32`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18004af50`

## callees

- `0x180031790`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180031749`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180031749`

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
0x18003173c  push    rbx
0x18003173e  sub     rsp, 20h
0x180031742  mov     rbx, rcx
0x180031745  add     rcx, 28h ; '('; lpCriticalSection
0x180031749  call    cs:__imp_DeleteCriticalSection
0x18003174f  mov     rcx, rbx; this
0x180031752  add     rsp, 20h
0x180031756  pop     rbx
0x180031757  jmp     ??1_ATL_BASE_MODULE70@ATL@@QEAA@XZ; ATL::_ATL_BASE_MODULE70::~_ATL_BASE_MODULE70(void)
```
