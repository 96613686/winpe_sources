# Windows::WCP::Implementation::Rtl::CBaseTracingStream::Write(unsigned __int64,signed char const * const)

- ea: `0x180019430`
- end: `0x18001943f`
- name: `?Write@CBaseTracingStream@Rtl@Implementation@WCP@Windows@@UEAAX_KQEBC@Z`
- size: `15`
- prototype: `void __fastcall(Windows::WCP::Implementation::Rtl::CBaseTracingStream *this, __int64, const signed __int8 *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18001c010`

## pseudocode

```c
void __fastcall Windows::WCP::Implementation::Rtl::CBaseTracingStream::Write(
        Windows::WCP::Implementation::Rtl::CBaseTracingStream *this,
        __int64 a2,
        const signed __int8 *a3)
{
  (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, __int64, const signed __int8 *))(*(_QWORD *)this + 176LL))(
    this,
    a2,
    a3);
}

```

## disassembly

```asm
0x180019430  mov     rax, [rcx]
0x180019433  mov     rax, [rax+0B0h]
0x18001943a  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
