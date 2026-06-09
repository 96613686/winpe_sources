# CCriticalSection::~CCriticalSection(void)

- ea: `0x18000d114`
- end: `0x18000d13f`
- name: `??1CCriticalSection@@QEAA@XZ`
- size: `43`
- prototype: `void __fastcall(CCriticalSection *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000cfa0`
- `0x18000d100`

## callees

- `0x18000d114`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000d12a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000d12a`

## pseudocode

```c
void __fastcall CCriticalSection::~CCriticalSection(struct _RTL_CRITICAL_SECTION *this)
{
  if ( LODWORD(this[1].DebugInfo) == 1 )
  {
    DeleteCriticalSection(this);
    LODWORD(this[1].DebugInfo) = 0;
  }
}

```

## disassembly

```asm
0x18000d114  push    rbx
0x18000d116  sub     rsp, 20h
0x18000d11a  cmp     dword ptr [rcx+28h], 1
0x18000d11e  mov     rbx, rcx
0x18000d121  jz      short loc_18000D12A
0x18000d123  add     rsp, 20h
0x18000d127  pop     rbx
0x18000d128  retn
0x18000d12a  call    cs:__imp_DeleteCriticalSection
0x18000d131  nop     dword ptr [rax+rax+00h]
0x18000d136  mov     dword ptr [rbx+28h], 0
0x18000d13d  jmp     short loc_18000D123
```
