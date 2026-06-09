# STATIC_META_STORED_CONTEXT::~STATIC_META_STORED_CONTEXT(void)

- ea: `0x180004418`
- end: `0x180004477`
- name: `??1STATIC_META_STORED_CONTEXT@@MEAA@XZ`
- size: `95`
- prototype: `void __fastcall(STATIC_META_STORED_CONTEXT *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800044c0`

## callees

- `0x18000439c`
- `0x1800043d4`

## import_xrefs

- `iisutil!??1STRA@@QEAA@XZ` at `0x180004457`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180004461`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180004457`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180004461`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180004470`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000444a`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000444a`

## pseudocode

```c
void __fastcall STATIC_META_STORED_CONTEXT::~STATIC_META_STORED_CONTEXT(STATIC_META_STORED_CONTEXT *this)
{
  *(_QWORD *)this = &STATIC_META_STORED_CONTEXT::`vftable';
  META_SCRIPT_MAP::~META_SCRIPT_MAP((STATIC_META_STORED_CONTEXT *)((char *)this + 264));
  MIME_MAP::~MIME_MAP((STATIC_META_STORED_CONTEXT *)((char *)this + 240));
  STRU::~STRU((STATIC_META_STORED_CONTEXT *)((char *)this + 184));
  STRA::~STRA((STATIC_META_STORED_CONTEXT *)((char *)this + 128));
  STRA::~STRA((STATIC_META_STORED_CONTEXT *)((char *)this + 64));
  STRA::~STRA((STATIC_META_STORED_CONTEXT *)((char *)this + 8));
}

```

## disassembly

```asm
0x180004418  push    rbx
0x18000441a  sub     rsp, 20h
0x18000441e  lea     rax, ??_7STATIC_META_STORED_CONTEXT@@6B@; const STATIC_META_STORED_CONTEXT::`vftable'
0x180004425  mov     rbx, rcx
0x180004428  mov     [rcx], rax
0x18000442b  add     rcx, 108h; this
0x180004432  call    ??1META_SCRIPT_MAP@@QEAA@XZ; META_SCRIPT_MAP::~META_SCRIPT_MAP(void)
0x180004437  lea     rcx, [rbx+0F0h]; this
0x18000443e  call    ??1MIME_MAP@@UEAA@XZ; MIME_MAP::~MIME_MAP(void)
0x180004443  lea     rcx, [rbx+0B8h]
0x18000444a  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180004450  lea     rcx, [rbx+80h]
0x180004457  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18000445d  lea     rcx, [rbx+40h]
0x180004461  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180004467  lea     rcx, [rbx+8]
0x18000446b  add     rsp, 20h
0x18000446f  pop     rbx
0x180004470  jmp     cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
```
