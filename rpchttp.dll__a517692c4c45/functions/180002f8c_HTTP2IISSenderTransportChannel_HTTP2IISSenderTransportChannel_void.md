# HTTP2IISSenderTransportChannel::~HTTP2IISSenderTransportChannel(void)

- ea: `0x180002f8c`
- end: `0x180002fa1`
- name: `??1HTTP2IISSenderTransportChannel@@UEAA@XZ`
- size: `21`
- prototype: `void __fastcall(HTTP2IISSenderTransportChannel *__hidden this)`
- caller_count: `2`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180003490`
- `0x18000a7a0`

## import_xrefs

- `ntdll!RtlDeleteCriticalSection` at `0x180002f9a`

## pseudocode

```c
void __fastcall HTTP2IISSenderTransportChannel::~HTTP2IISSenderTransportChannel(HTTP2IISSenderTransportChannel *this)
{
  *(_QWORD *)this = &HTTP2IISSenderTransportChannel::`vftable';
  RtlDeleteCriticalSection((PRTL_CRITICAL_SECTION)((char *)this + 128));
}

```

## disassembly

```asm
0x180002f8c  lea     rax, ??_7HTTP2IISSenderTransportChannel@@6B@; const HTTP2IISSenderTransportChannel::`vftable'
0x180002f93  mov     [rcx], rax
0x180002f96  sub     rcx, 0FFFFFFFFFFFFFF80h
0x180002f9a  jmp     cs:__imp_RtlDeleteCriticalSection
```
