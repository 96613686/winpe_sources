# Windows::WCP::Implementation::Rtl::CBaseTracingStream::Write(_UNICODE_STRING const &)

- ea: `0x180016b70`
- end: `0x180016b7f`
- name: `?Write@CBaseTracingStream@Rtl@Implementation@WCP@Windows@@UEAAXAEBU_UNICODE_STRING@@@Z`
- size: `15`
- prototype: `void __fastcall(Windows::WCP::Implementation::Rtl::CBaseTracingStream *__hidden this, const struct _UNICODE_STRING *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18001c010`

## pseudocode

```c
void __fastcall Windows::WCP::Implementation::Rtl::CBaseTracingStream::Write(
        Windows::WCP::Implementation::Rtl::CBaseTracingStream *this,
        const struct _UNICODE_STRING *a2)
{
  (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, const struct _UNICODE_STRING *))(*(_QWORD *)this + 152LL))(
    this,
    a2);
}

```

## disassembly

```asm
0x180016b70  mov     rax, [rcx]
0x180016b73  mov     rax, [rax+98h]
0x180016b7a  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
