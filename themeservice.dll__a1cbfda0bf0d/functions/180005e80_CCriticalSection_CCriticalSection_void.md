# CCriticalSection::~CCriticalSection(void)

- ea: `0x180005e80`
- end: `0x180005e91`
- name: `??1CCriticalSection@@QEAA@XZ`
- size: `17`
- prototype: `void __fastcall(CCriticalSection *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180005dec`
- `0x18000a96c`
- `0x18000ee4c`

## callees

- `0x180005e80`

## import_xrefs

- `ntdll!RtlDeleteCriticalSection` at `0x180005e89`

## pseudocode

```c
void __fastcall CCriticalSection::~CCriticalSection(CCriticalSection *this)
{
  if ( *(int *)this >= 0 )
    RtlDeleteCriticalSection((PRTL_CRITICAL_SECTION)((char *)this + 8));
}

```

## disassembly

```asm
0x180005e80  cmp     dword ptr [rcx], 0
0x180005e83  jl      short locret_180005E90
0x180005e85  add     rcx, 8
0x180005e89  jmp     cs:__imp_RtlDeleteCriticalSection
0x180005e90  retn
```
