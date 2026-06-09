# CCriticalSection::Release(void)

- ea: `0x1800045a0`
- end: `0x1800045b1`
- name: `?Release@CCriticalSection@@QEAAXXZ`
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

- `0x1800045a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800045a9`

## pseudocode

```c
void __fastcall CCriticalSection::Release(CCriticalSection *this)
{
  if ( *(int *)this >= 0 )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
}

```

## disassembly

```asm
0x1800045a0  cmp     dword ptr [rcx], 0
0x1800045a3  jl      short locret_1800045B0
0x1800045a5  add     rcx, 8
0x1800045a9  jmp     cs:__imp_LeaveCriticalSection
0x1800045b0  retn
```
