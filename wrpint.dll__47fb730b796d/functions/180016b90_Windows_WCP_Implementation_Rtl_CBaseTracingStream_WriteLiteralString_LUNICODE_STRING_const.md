# Windows::WCP::Implementation::Rtl::CBaseTracingStream::WriteLiteralString(_LUNICODE_STRING const &)

- ea: `0x180016b90`
- end: `0x180016b9f`
- name: `?WriteLiteralString@CBaseTracingStream@Rtl@Implementation@WCP@Windows@@UEAAXAEBU_LUNICODE_STRING@@@Z`
- size: `15`
- prototype: `void __fastcall(Windows::WCP::Implementation::Rtl::CBaseTracingStream *__hidden this, const struct _LUNICODE_STRING *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18001c010`

## pseudocode

```c
void __fastcall Windows::WCP::Implementation::Rtl::CBaseTracingStream::WriteLiteralString(
        Windows::WCP::Implementation::Rtl::CBaseTracingStream *this,
        const struct _LUNICODE_STRING *a2)
{
  (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, const struct _LUNICODE_STRING *))(*(_QWORD *)this + 248LL))(
    this,
    a2);
}

```

## disassembly

```asm
0x180016b90  mov     rax, [rcx]
0x180016b93  mov     rax, [rax+0F8h]
0x180016b9a  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
