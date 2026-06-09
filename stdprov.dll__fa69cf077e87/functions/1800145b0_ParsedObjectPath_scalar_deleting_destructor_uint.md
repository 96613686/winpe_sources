# ParsedObjectPath::`scalar deleting destructor'(uint)

- ea: `0x1800145b0`
- end: `0x1800145d0`
- name: `??_GParsedObjectPath@@QEAAPEAXI@Z`
- size: `32`
- prototype: `ParsedObjectPath *__fastcall(ParsedObjectPath *this, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000e110`
- `0x1800147e4`

## callees

- `0x1800144e8`

## import_xrefs

- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800145c1`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800145c1`

## pseudocode

```c
ParsedObjectPath *__fastcall ParsedObjectPath::`scalar deleting destructor'(ParsedObjectPath *this, unsigned int a2)
{
  ParsedObjectPath::~ParsedObjectPath(this, a2);
  CWin32DefaultArena::WbemMemFree(this);
  return this;
}

```

## disassembly

```asm
0x1800145b0  push    rbx
0x1800145b2  sub     rsp, 20h
0x1800145b6  mov     rbx, rcx
0x1800145b9  call    ??1ParsedObjectPath@@QEAA@XZ; ParsedObjectPath::~ParsedObjectPath(void)
0x1800145be  mov     rcx, rbx
0x1800145c1  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x1800145c7  mov     rax, rbx
0x1800145ca  add     rsp, 20h
0x1800145ce  pop     rbx
0x1800145cf  retn
```
