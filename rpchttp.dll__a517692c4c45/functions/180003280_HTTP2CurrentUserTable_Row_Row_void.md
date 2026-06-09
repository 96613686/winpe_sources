# HTTP2CurrentUserTable::Row::~Row(void)

- ea: `0x180003280`
- end: `0x1800032a0`
- name: `??1Row@HTTP2CurrentUserTable@@QEAA@XZ`
- size: `32`
- prototype: `void __fastcall(HTTP2CurrentUserTable::Row *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18001e964`

## import_xrefs

- `ntdll!RtlDeleteCriticalSection` at `0x18000328d`
- `ntdll!RtlDeleteCriticalSection` at `0x18000328d`

## pseudocode

```c
void __fastcall HTTP2CurrentUserTable::Row::~Row(HTTP2CurrentUserTable::Row *this)
{
  RtlDeleteCriticalSection((PRTL_CRITICAL_SECTION)((char *)this + 48));
  QUEUE::~QUEUE(this);
}

```

## disassembly

```asm
0x180003280  push    rbx
0x180003282  sub     rsp, 20h
0x180003286  mov     rbx, rcx
0x180003289  add     rcx, 30h ; '0'; CriticalSection
0x18000328d  call    cs:__imp_RtlDeleteCriticalSection
0x180003293  mov     rcx, rbx; this
0x180003296  add     rsp, 20h
0x18000329a  pop     rbx
0x18000329b  jmp     ??1QUEUE@@QEAA@XZ; QUEUE::~QUEUE(void)
```
