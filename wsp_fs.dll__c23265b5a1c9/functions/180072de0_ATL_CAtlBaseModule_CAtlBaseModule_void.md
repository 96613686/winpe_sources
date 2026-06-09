# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x180072de0`
- end: `0x180072e06`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `38`
- prototype: `void __fastcall(ATL::CAtlBaseModule *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800aa720`

## callees

- `0x180072e54`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180072ded`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180072ded`

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
0x180072de0  push    rbx
0x180072de2  sub     rsp, 20h
0x180072de6  mov     rbx, rcx
0x180072de9  add     rcx, 28h ; '('; lpCriticalSection
0x180072ded  call    cs:__imp_DeleteCriticalSection
0x180072df4  nop     dword ptr [rax+rax+00h]
0x180072df9  mov     rcx, rbx; this
0x180072dfc  add     rsp, 20h
0x180072e00  pop     rbx
0x180072e01  jmp     ??1_ATL_BASE_MODULE70@ATL@@QEAA@XZ; ATL::_ATL_BASE_MODULE70::~_ATL_BASE_MODULE70(void)
```
