# Windows::WCP::Implementation::Rtl::CBaseTracingStream::WriteLiteralString(_LUTF8_STRING const *)

- ea: `0x180019d60`
- end: `0x180019d84`
- name: `?WriteLiteralString@CBaseTracingStream@Rtl@Implementation@WCP@Windows@@UEAAXPEBU_LUTF8_STRING@@@Z`
- size: `36`
- prototype: `void __fastcall(Windows::WCP::Implementation::Rtl::CBaseTracingStream *__hidden this, const struct _LUTF8_STRING *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180019d60`
- `0x18001c010`

## pseudocode

```c
void __fastcall Windows::WCP::Implementation::Rtl::CBaseTracingStream::WriteLiteralString(
        Windows::WCP::Implementation::Rtl::CBaseTracingStream *this,
        const struct _LUTF8_STRING *a2)
{
  if ( a2 )
    (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, _QWORD, _QWORD))(*(_QWORD *)this + 280LL))(
      this,
      *(_QWORD *)a2,
      *((_QWORD *)a2 + 2));
}

```

## disassembly

```asm
0x180019d60  sub     rsp, 28h
0x180019d64  test    rdx, rdx
0x180019d67  jz      short loc_180019D7F
0x180019d69  mov     rax, [rcx]
0x180019d6c  mov     r8, [rdx+10h]
0x180019d70  mov     rdx, [rdx]
0x180019d73  mov     rax, [rax+118h]
0x180019d7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019d7f  add     rsp, 28h
0x180019d83  retn
```
