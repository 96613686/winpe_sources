# CWdsTransportConfigurationManager::~CWdsTransportConfigurationManager(void)

- ea: `0x180009d9c`
- end: `0x180009dc3`
- name: `??1CWdsTransportConfigurationManager@@QEAA@XZ`
- size: `39`
- prototype: `void __fastcall(CWdsTransportConfigurationManager *__hidden this)`
- caller_count: `7`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009cec`
- `0x18000b23c`
- `0x18000c704`
- `0x18000ed68`
- `0x18000fe9c`
- `0x180017114`
- `0x1800196c0`

## callees

- `0x180002bc4`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180009da9`
- `KERNEL32!DeleteCriticalSection` at `0x180009da9`

## pseudocode

```c
void __fastcall CWdsTransportConfigurationManager::~CWdsTransportConfigurationManager(
        struct _RTL_CRITICAL_SECTION *this)
{
  DeleteCriticalSection(this + 2);
  ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection((ATL::CComSafeDeleteCriticalSection *)&this->OwningThread);
}

```

## disassembly

```asm
0x180009d9c  push    rbx
0x180009d9e  sub     rsp, 20h
0x180009da2  mov     rbx, rcx
0x180009da5  add     rcx, 50h ; 'P'; lpCriticalSection
0x180009da9  call    cs:__imp_DeleteCriticalSection
0x180009db0  nop     dword ptr [rax+rax+00h]
0x180009db5  lea     rcx, [rbx+10h]; this
0x180009db9  add     rsp, 20h
0x180009dbd  pop     rbx
0x180009dbe  jmp     ??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ; ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)
```
