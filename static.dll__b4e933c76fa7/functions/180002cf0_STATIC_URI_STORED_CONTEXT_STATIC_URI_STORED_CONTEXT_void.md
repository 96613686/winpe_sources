# STATIC_URI_STORED_CONTEXT::~STATIC_URI_STORED_CONTEXT(void)

- ea: `0x180002cf0`
- end: `0x180002d13`
- name: `??1STATIC_URI_STORED_CONTEXT@@QEAA@XZ`
- size: `35`
- prototype: `void __fastcall(STATIC_URI_STORED_CONTEXT *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180002db0`

## import_xrefs

- `iisutil!??1STRA@@QEAA@XZ` at `0x180002d0c`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002cfd`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002cfd`

## pseudocode

```c
void __fastcall STATIC_URI_STORED_CONTEXT::~STATIC_URI_STORED_CONTEXT(STATIC_URI_STORED_CONTEXT *this)
{
  STRU::~STRU((STATIC_URI_STORED_CONTEXT *)((char *)this + 96));
  STRA::~STRA((STATIC_URI_STORED_CONTEXT *)((char *)this + 8));
}

```

## disassembly

```asm
0x180002cf0  push    rbx
0x180002cf2  sub     rsp, 20h
0x180002cf6  mov     rbx, rcx
0x180002cf9  add     rcx, 60h ; '`'
0x180002cfd  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180002d03  lea     rcx, [rbx+8]
0x180002d07  add     rsp, 20h
0x180002d0b  pop     rbx
0x180002d0c  jmp     cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
```
