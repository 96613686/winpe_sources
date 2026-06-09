# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x1800268e4`
- end: `0x18002690a`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `38`
- prototype: `void __fastcall(ATL::CAtlBaseModule *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800299e0`

## callees

- `0x180026958`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800268f1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800268f1`

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
0x1800268e4  push    rbx
0x1800268e6  sub     rsp, 20h
0x1800268ea  mov     rbx, rcx
0x1800268ed  add     rcx, 28h ; '('; lpCriticalSection
0x1800268f1  call    cs:__imp_DeleteCriticalSection
0x1800268f8  nop     dword ptr [rax+rax+00h]
0x1800268fd  mov     rcx, rbx; this
0x180026900  add     rsp, 20h
0x180026904  pop     rbx
0x180026905  jmp     ??1_ATL_BASE_MODULE70@ATL@@QEAA@XZ; ATL::_ATL_BASE_MODULE70::~_ATL_BASE_MODULE70(void)
```
