# Windows::WCP::Implementation::Rtl::CBaseTracingStream::Write(_LUNICODE_STRING const &)

- ea: `0x180016b30`
- end: `0x180016b3f`
- name: `?Write@CBaseTracingStream@Rtl@Implementation@WCP@Windows@@UEAAXAEBU_LUNICODE_STRING@@@Z`
- size: `15`
- prototype: `void __fastcall(Windows::WCP::Implementation::Rtl::CBaseTracingStream *__hidden this, const struct _LUNICODE_STRING *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18001c010`

## pseudocode

```c
void __fastcall Windows::WCP::Implementation::Rtl::CBaseTracingStream::Write(
        Windows::WCP::Implementation::Rtl::CBaseTracingStream *this,
        const struct _LUNICODE_STRING *a2)
{
  (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, const struct _LUNICODE_STRING *))(*(_QWORD *)this + 144LL))(
    this,
    a2);
}

```

## disassembly

```asm
0x180016b30  mov     rax, [rcx]
0x180016b33  mov     rax, [rax+90h]
0x180016b3a  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
