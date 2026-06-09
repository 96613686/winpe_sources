# HTTP2GenericReceiver::~HTTP2GenericReceiver(void)

- ea: `0x180002f64`
- end: `0x180002f85`
- name: `??1HTTP2GenericReceiver@@UEAA@XZ`
- size: `33`
- prototype: `void __fastcall(HTTP2GenericReceiver *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180003410`
- `0x18000a720`

## callees

- `0x18001e964`

## import_xrefs

- `ntdll!RtlDeleteCriticalSection` at `0x180002f71`
- `ntdll!RtlDeleteCriticalSection` at `0x180002f71`

## pseudocode

```c
void __fastcall HTTP2GenericReceiver::~HTTP2GenericReceiver(HTTP2GenericReceiver *this)
{
  RtlDeleteCriticalSection((PRTL_CRITICAL_SECTION)((char *)this + 112));
  QUEUE::~QUEUE((HTTP2GenericReceiver *)((char *)this + 32));
}

```

## disassembly

```asm
0x180002f64  push    rbx
0x180002f66  sub     rsp, 20h
0x180002f6a  mov     rbx, rcx
0x180002f6d  add     rcx, 70h ; 'p'; CriticalSection
0x180002f71  call    cs:__imp_RtlDeleteCriticalSection
0x180002f77  lea     rcx, [rbx+20h]; this
0x180002f7b  add     rsp, 20h
0x180002f7f  pop     rbx
0x180002f80  jmp     ??1QUEUE@@QEAA@XZ; QUEUE::~QUEUE(void)
```
