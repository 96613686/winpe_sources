# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x18000bcc0`
- end: `0x18000bce0`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `32`
- prototype: `void __fastcall(ATL::CAtlBaseModule *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800336f0`

## callees

- `0x18000bd28`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000bccd`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000bccd`

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
0x18000bcc0  push    rbx
0x18000bcc2  sub     rsp, 20h
0x18000bcc6  mov     rbx, rcx
0x18000bcc9  add     rcx, 28h ; '('; lpCriticalSection
0x18000bccd  call    cs:__imp_DeleteCriticalSection
0x18000bcd3  mov     rcx, rbx; this
0x18000bcd6  add     rsp, 20h
0x18000bcda  pop     rbx
0x18000bcdb  jmp     ??1_ATL_BASE_MODULE70@ATL@@QEAA@XZ; ATL::_ATL_BASE_MODULE70::~_ATL_BASE_MODULE70(void)
```
