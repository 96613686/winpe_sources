# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x1400266e4`
- end: `0x14002670a`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `38`
- prototype: `void __fastcall(ATL::CAtlBaseModule *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400282f0`

## callees

- `0x14002673c`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1400266f1`
- `KERNEL32!DeleteCriticalSection` at `0x1400266f1`

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
0x1400266e4  push    rbx
0x1400266e6  sub     rsp, 20h
0x1400266ea  mov     rbx, rcx
0x1400266ed  add     rcx, 28h ; '('; lpCriticalSection
0x1400266f1  call    cs:__imp_DeleteCriticalSection
0x1400266f8  nop     dword ptr [rax+rax+00h]
0x1400266fd  mov     rcx, rbx; this
0x140026700  add     rsp, 20h
0x140026704  pop     rbx
0x140026705  jmp     ??1_ATL_BASE_MODULE70@ATL@@QEAA@XZ; ATL::_ATL_BASE_MODULE70::~_ATL_BASE_MODULE70(void)
```
