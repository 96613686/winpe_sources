# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x180006980`
- end: `0x1800069a0`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `32`
- prototype: `void __fastcall(ATL::CAtlBaseModule *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180012f40`

## callees

- `0x1800069e8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000698d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000698d`

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
0x180006980  push    rbx
0x180006982  sub     rsp, 20h
0x180006986  mov     rbx, rcx
0x180006989  add     rcx, 28h ; '('; lpCriticalSection
0x18000698d  call    cs:__imp_DeleteCriticalSection
0x180006993  mov     rcx, rbx; this
0x180006996  add     rsp, 20h
0x18000699a  pop     rbx
0x18000699b  jmp     ??1_ATL_BASE_MODULE70@ATL@@QEAA@XZ; ATL::_ATL_BASE_MODULE70::~_ATL_BASE_MODULE70(void)
```
