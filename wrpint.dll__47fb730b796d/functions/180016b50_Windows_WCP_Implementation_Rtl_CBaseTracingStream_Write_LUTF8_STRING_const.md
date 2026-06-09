# Windows::WCP::Implementation::Rtl::CBaseTracingStream::Write(_LUTF8_STRING const &)

- ea: `0x180016b50`
- end: `0x180016b5f`
- name: `?Write@CBaseTracingStream@Rtl@Implementation@WCP@Windows@@UEAAXAEBU_LUTF8_STRING@@@Z`
- size: `15`
- prototype: `void __fastcall(Windows::WCP::Implementation::Rtl::CBaseTracingStream *__hidden this, const struct _LUTF8_STRING *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18001c010`

## pseudocode

```c
void __fastcall Windows::WCP::Implementation::Rtl::CBaseTracingStream::Write(
        Windows::WCP::Implementation::Rtl::CBaseTracingStream *this,
        const struct _LUTF8_STRING *a2)
{
  (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, const struct _LUTF8_STRING *))(*(_QWORD *)this + 136LL))(
    this,
    a2);
}

```

## disassembly

```asm
0x180016b50  mov     rax, [rcx]
0x180016b53  mov     rax, [rax+88h]
0x180016b5a  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
