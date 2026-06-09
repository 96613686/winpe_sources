# META_SCRIPT_MAP_ENTRY::~META_SCRIPT_MAP_ENTRY(void)

- ea: `0x180005790`
- end: `0x1800057f1`
- name: `??1META_SCRIPT_MAP_ENTRY@@UEAA@XZ`
- size: `97`
- prototype: `void __fastcall(META_SCRIPT_MAP_ENTRY *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x1800058a0`

## import_xrefs

- `iisutil!??1MULTISZA@@QEAA@XZ` at `0x1800057d1`
- `iisutil!??1MULTISZA@@QEAA@XZ` at `0x1800057d1`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800057aa`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800057b7`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800057c4`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800057db`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800057aa`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800057b7`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800057c4`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800057db`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800057ea`

## pseudocode

```c
void __fastcall META_SCRIPT_MAP_ENTRY::~META_SCRIPT_MAP_ENTRY(META_SCRIPT_MAP_ENTRY *this)
{
  *(_QWORD *)this = &META_SCRIPT_MAP_ENTRY::`vftable';
  STRU::~STRU((META_SCRIPT_MAP_ENTRY *)((char *)this + 304));
  STRU::~STRU((META_SCRIPT_MAP_ENTRY *)((char *)this + 248));
  STRU::~STRU((META_SCRIPT_MAP_ENTRY *)((char *)this + 192));
  MULTISZA::~MULTISZA((META_SCRIPT_MAP_ENTRY *)((char *)this + 136));
  STRU::~STRU((META_SCRIPT_MAP_ENTRY *)((char *)this + 80));
  STRU::~STRU((META_SCRIPT_MAP_ENTRY *)((char *)this + 24));
}

```

## disassembly

```asm
0x180005790  push    rbx
0x180005792  sub     rsp, 20h
0x180005796  lea     rax, ??_7META_SCRIPT_MAP_ENTRY@@6B@; const META_SCRIPT_MAP_ENTRY::`vftable'
0x18000579d  mov     rbx, rcx
0x1800057a0  mov     [rcx], rax
0x1800057a3  add     rcx, 130h
0x1800057aa  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800057b0  lea     rcx, [rbx+0F8h]
0x1800057b7  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800057bd  lea     rcx, [rbx+0C0h]
0x1800057c4  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800057ca  lea     rcx, [rbx+88h]
0x1800057d1  call    cs:__imp_??1MULTISZA@@QEAA@XZ; MULTISZA::~MULTISZA(void)
0x1800057d7  lea     rcx, [rbx+50h]
0x1800057db  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800057e1  lea     rcx, [rbx+18h]
0x1800057e5  add     rsp, 20h
0x1800057e9  pop     rbx
0x1800057ea  jmp     cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
```
