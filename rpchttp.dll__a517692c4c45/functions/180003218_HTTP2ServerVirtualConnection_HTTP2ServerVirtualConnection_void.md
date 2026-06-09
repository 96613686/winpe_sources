# HTTP2ServerVirtualConnection::~HTTP2ServerVirtualConnection(void)

- ea: `0x180003218`
- end: `0x180003248`
- name: `??1HTTP2ServerVirtualConnection@@UEAA@XZ`
- size: `48`
- prototype: `void __fastcall(HTTP2ServerVirtualConnection *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180003650`
- `0x180007be0`
- `0x18000dfe8`

## callees

- `0x180003250`

## import_xrefs

- `ntdll!RtlDeleteCriticalSection` at `0x180003228`
- `ntdll!RtlDeleteCriticalSection` at `0x180003235`
- `ntdll!RtlDeleteCriticalSection` at `0x180003228`
- `ntdll!RtlDeleteCriticalSection` at `0x180003235`

## pseudocode

```c
void __fastcall HTTP2ServerVirtualConnection::~HTTP2ServerVirtualConnection(HTTP2ServerVirtualConnection *this)
{
  RtlDeleteCriticalSection((PRTL_CRITICAL_SECTION)this + 9);
  RtlDeleteCriticalSection((PRTL_CRITICAL_SECTION)((char *)this + 312));
  HTTP2VirtualConnection::~HTTP2VirtualConnection(this);
}

```

## disassembly

```asm
0x180003218  push    rbx
0x18000321a  sub     rsp, 20h
0x18000321e  mov     rbx, rcx
0x180003221  add     rcx, 168h; CriticalSection
0x180003228  call    cs:__imp_RtlDeleteCriticalSection
0x18000322e  lea     rcx, [rbx+138h]; CriticalSection
0x180003235  call    cs:__imp_RtlDeleteCriticalSection
0x18000323b  mov     rcx, rbx; this
0x18000323e  add     rsp, 20h
0x180003242  pop     rbx
0x180003243  jmp     ??1HTTP2VirtualConnection@@UEAA@XZ; HTTP2VirtualConnection::~HTTP2VirtualConnection(void)
```
