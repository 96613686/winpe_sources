# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x18001a154`
- end: `0x18001a17a`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `38`
- prototype: `void __fastcall(ATL::CAtlBaseModule *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001f2d0`

## callees

- `0x18001a1ac`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18001a161`
- `KERNEL32!DeleteCriticalSection` at `0x18001a161`

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
0x18001a154  push    rbx
0x18001a156  sub     rsp, 20h
0x18001a15a  mov     rbx, rcx
0x18001a15d  add     rcx, 28h ; '('; lpCriticalSection
0x18001a161  call    cs:__imp_DeleteCriticalSection
0x18001a168  nop     dword ptr [rax+rax+00h]
0x18001a16d  mov     rcx, rbx; this
0x18001a170  add     rsp, 20h
0x18001a174  pop     rbx
0x18001a175  jmp     ??1_ATL_BASE_MODULE70@ATL@@QEAA@XZ; ATL::_ATL_BASE_MODULE70::~_ATL_BASE_MODULE70(void)
```
