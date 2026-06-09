# Windows::WCP::Implementation::Rtl::CBaseTracingStream::WriteLiteralString(unsigned __int64,char const * const)

- ea: `0x180019e00`
- end: `0x180019e0f`
- name: `?WriteLiteralString@CBaseTracingStream@Rtl@Implementation@WCP@Windows@@UEAAX_KQEBD@Z`
- size: `15`
- prototype: `void __fastcall(Windows::WCP::Implementation::Rtl::CBaseTracingStream *this, __int64, const char *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18001c010`

## pseudocode

```c
void __fastcall Windows::WCP::Implementation::Rtl::CBaseTracingStream::WriteLiteralString(
        Windows::WCP::Implementation::Rtl::CBaseTracingStream *this,
        __int64 a2,
        const char *a3)
{
  (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, __int64, const char *))(*(_QWORD *)this + 280LL))(
    this,
    a2,
    a3);
}

```

## disassembly

```asm
0x180019e00  mov     rax, [rcx]
0x180019e03  mov     rax, [rax+118h]
0x180019e0a  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
