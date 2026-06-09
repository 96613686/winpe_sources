# CCriticalSection::~CCriticalSection(void)

- ea: `0x18000363c`
- end: `0x180003651`
- name: `??1CCriticalSection@@QEAA@XZ`
- size: `21`
- prototype: `void __fastcall(CCriticalSection *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180003658`

## callees

- `0x18000363c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003646`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003646`

## pseudocode

```c
void __fastcall CCriticalSection::~CCriticalSection(struct _RTL_CRITICAL_SECTION *this)
{
  if ( LODWORD(this[1].DebugInfo) )
    DeleteCriticalSection(this);
}

```

## disassembly

```asm
0x18000363c  sub     rsp, 28h
0x180003640  cmp     dword ptr [rcx+28h], 0
0x180003644  jz      short loc_18000364C
0x180003646  call    cs:__imp_DeleteCriticalSection
0x18000364c  add     rsp, 28h
0x180003650  retn
```
