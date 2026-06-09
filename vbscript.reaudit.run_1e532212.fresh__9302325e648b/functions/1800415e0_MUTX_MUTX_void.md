# MUTX::~MUTX(void)

- ea: `0x1800415e0`
- end: `0x1800415f5`
- name: `??1MUTX@@QEAA@XZ`
- size: `21`
- prototype: `void __fastcall(MUTX *__hidden this)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x1800194b0`
- `0x18003cab4`
- `0x1800415b8`
- `0x1800505ac`
- `0x180064e5c`

## callees

- `0x1800415e0`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1800415ea`
- `KERNEL32!DeleteCriticalSection` at `0x1800415ea`

## pseudocode

```c
void __fastcall MUTX::~MUTX(struct _RTL_CRITICAL_SECTION *this)
{
  if ( BYTE1(this[1].DebugInfo) )
    DeleteCriticalSection(this);
}

```

## disassembly

```asm
0x1800415e0  sub     rsp, 28h
0x1800415e4  cmp     byte ptr [rcx+29h], 0
0x1800415e8  jz      short loc_1800415F0
0x1800415ea  call    cs:__imp_DeleteCriticalSection
0x1800415f0  add     rsp, 28h
0x1800415f4  retn
```
