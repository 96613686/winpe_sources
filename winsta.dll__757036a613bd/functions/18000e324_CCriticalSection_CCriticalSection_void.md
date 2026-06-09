# CCriticalSection::~CCriticalSection(void)

- ea: `0x18000e324`
- end: `0x18000e348`
- name: `??1CCriticalSection@@QEAA@XZ`
- size: `36`
- prototype: `void __fastcall(CCriticalSection *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000e1b8`
- `0x18000e310`

## callees

- `0x18000e324`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000e339`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000e339`

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
0x18000e324  push    rbx
0x18000e326  sub     rsp, 20h
0x18000e32a  cmp     dword ptr [rcx+28h], 1
0x18000e32e  mov     rbx, rcx
0x18000e331  jz      short loc_18000E339
0x18000e333  add     rsp, 20h
0x18000e337  pop     rbx
0x18000e338  retn
0x18000e339  call    cs:__imp_DeleteCriticalSection
0x18000e33f  mov     dword ptr [rbx+28h], 0
0x18000e346  jmp     short loc_18000E333
```
