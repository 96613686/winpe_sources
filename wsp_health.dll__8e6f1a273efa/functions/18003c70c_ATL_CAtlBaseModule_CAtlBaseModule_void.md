# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x18003c70c`
- end: `0x18003c732`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `38`
- prototype: `void __fastcall(ATL::CAtlBaseModule *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18008d6b0`

## callees

- `0x18003c780`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003c719`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003c719`

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
0x18003c70c  push    rbx
0x18003c70e  sub     rsp, 20h
0x18003c712  mov     rbx, rcx
0x18003c715  add     rcx, 28h ; '('; lpCriticalSection
0x18003c719  call    cs:__imp_DeleteCriticalSection
0x18003c720  nop     dword ptr [rax+rax+00h]
0x18003c725  mov     rcx, rbx; this
0x18003c728  add     rsp, 20h
0x18003c72c  pop     rbx
0x18003c72d  jmp     ??1_ATL_BASE_MODULE70@ATL@@QEAA@XZ; ATL::_ATL_BASE_MODULE70::~_ATL_BASE_MODULE70(void)
```
