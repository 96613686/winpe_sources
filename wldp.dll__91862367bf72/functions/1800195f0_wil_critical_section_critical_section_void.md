# wil::critical_section::~critical_section(void)

- ea: `0x1800195f0`
- end: `0x180019600`
- name: `??1critical_section@wil@@QEAA@XZ`
- size: `16`
- prototype: `void __fastcall(wil::critical_section *__hidden this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x18003e390`
- `0x18003f02f`
- `0x18003f07f`
- `0x18003f1f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800195f4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800195f4`

## pseudocode

```c
void __fastcall wil::critical_section::~critical_section(struct _RTL_CRITICAL_SECTION *this)
{
  DeleteCriticalSection(this);
}

```

## disassembly

```asm
0x1800195f0  sub     rsp, 28h
0x1800195f4  call    cs:__imp_DeleteCriticalSection
0x1800195fa  nop
0x1800195fb  add     rsp, 28h
0x1800195ff  retn
```
