# CCriticalSection::Acquire(void)

- ea: `0x180004430`
- end: `0x180004441`
- name: `?Acquire@CCriticalSection@@QEAAXXZ`
- size: `17`
- prototype: `void __fastcall(CCriticalSection *__hidden this)`
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x180003e1c`
- `0x180004324`
- `0x180004be0`
- `0x180006580`
- `0x180006710`
- `0x18000ab04`
- `0x18000acc0`
- `0x18000aefc`
- `0x18000b180`
- `0x18000db00`

## callees

- `0x180004430`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004439`

## pseudocode

```c
void __fastcall CCriticalSection::Acquire(CCriticalSection *this)
{
  if ( *(int *)this >= 0 )
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
}

```

## disassembly

```asm
0x180004430  cmp     dword ptr [rcx], 0
0x180004433  jl      short locret_180004440
0x180004435  add     rcx, 8
0x180004439  jmp     cs:__imp_EnterCriticalSection
0x180004440  retn
```
