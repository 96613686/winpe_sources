# Windows::WCP::Implementation::Rtl::CBaseTracingStream::WriteLiteralString(_LUNICODE_STRING const *)

- ea: `0x180019d30`
- end: `0x180019d5a`
- name: `?WriteLiteralString@CBaseTracingStream@Rtl@Implementation@WCP@Windows@@UEAAXPEBU_LUNICODE_STRING@@@Z`
- size: `42`
- prototype: `void __fastcall(Windows::WCP::Implementation::Rtl::CBaseTracingStream *__hidden this, const struct _LUNICODE_STRING *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180019d30`
- `0x18001c010`

## pseudocode

```c
void __fastcall Windows::WCP::Implementation::Rtl::CBaseTracingStream::WriteLiteralString(
        Windows::WCP::Implementation::Rtl::CBaseTracingStream *this,
        const struct _LUNICODE_STRING *a2)
{
  if ( a2 )
    (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, _QWORD, _QWORD))(*(_QWORD *)this + 288LL))(
      this,
      *(_QWORD *)a2 >> 1,
      *((_QWORD *)a2 + 2));
}

```

## disassembly

```asm
0x180019d30  sub     rsp, 28h
0x180019d34  mov     r8, rdx
0x180019d37  test    rdx, rdx
0x180019d3a  jz      short loc_180019D55
0x180019d3c  mov     rax, [rcx]
0x180019d3f  mov     rdx, [rdx]
0x180019d42  mov     r8, [r8+10h]
0x180019d46  shr     rdx, 1
0x180019d49  mov     rax, [rax+120h]
0x180019d50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019d55  add     rsp, 28h
0x180019d59  retn
```
