# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x180026658`
- end: `0x180026678`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `32`
- prototype: `void __fastcall(ATL::CAtlBaseModule *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18002f230`

## callees

- `0x1800266ac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180026665`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180026665`

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
0x180026658  push    rbx
0x18002665a  sub     rsp, 20h
0x18002665e  mov     rbx, rcx
0x180026661  add     rcx, 28h ; '('; lpCriticalSection
0x180026665  call    cs:__imp_DeleteCriticalSection
0x18002666b  mov     rcx, rbx; this
0x18002666e  add     rsp, 20h
0x180026672  pop     rbx
0x180026673  jmp     ??1_ATL_BASE_MODULE70@ATL@@QEAA@XZ; ATL::_ATL_BASE_MODULE70::~_ATL_BASE_MODULE70(void)
```
