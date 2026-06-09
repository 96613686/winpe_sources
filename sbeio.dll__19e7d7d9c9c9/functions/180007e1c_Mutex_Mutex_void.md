# Mutex::~Mutex(void)

- ea: `0x180007e1c`
- end: `0x180007e31`
- name: `??1Mutex@@QEAA@XZ`
- size: `21`
- prototype: `void __fastcall(Mutex *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180007bd8`

## callees

- `0x180007e1c`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180007e26`
- `KERNEL32!DeleteCriticalSection` at `0x180007e26`

## pseudocode

```c
void __fastcall Mutex::~Mutex(struct _RTL_CRITICAL_SECTION *this)
{
  if ( LODWORD(this[1].DebugInfo) )
    DeleteCriticalSection(this);
}

```

## disassembly

```asm
0x180007e1c  sub     rsp, 28h
0x180007e20  cmp     dword ptr [rcx+28h], 0
0x180007e24  jz      short loc_180007E2C
0x180007e26  call    cs:__imp_DeleteCriticalSection
0x180007e2c  add     rsp, 28h
0x180007e30  retn
```
