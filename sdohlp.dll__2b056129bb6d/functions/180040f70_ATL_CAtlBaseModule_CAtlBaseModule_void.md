# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x180040f70`
- end: `0x180040f90`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `32`
- prototype: `void __fastcall(ATL::CAtlBaseModule *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800573e0`

## callees

- `0x180040fc4`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180040f7d`
- `KERNEL32!DeleteCriticalSection` at `0x180040f7d`

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
0x180040f70  push    rbx
0x180040f72  sub     rsp, 20h
0x180040f76  mov     rbx, rcx
0x180040f79  add     rcx, 28h ; '('; lpCriticalSection
0x180040f7d  call    cs:__imp_DeleteCriticalSection
0x180040f83  mov     rcx, rbx; this
0x180040f86  add     rsp, 20h
0x180040f8a  pop     rbx
0x180040f8b  jmp     ??1_ATL_BASE_MODULE70@ATL@@QEAA@XZ; ATL::_ATL_BASE_MODULE70::~_ATL_BASE_MODULE70(void)
```
