# Windows::WCP::Implementation::Rtl::CBaseTracingStream::WriteLiteralString(_UNICODE_STRING const *)

- ea: `0x180019d90`
- end: `0x180019dba`
- name: `?WriteLiteralString@CBaseTracingStream@Rtl@Implementation@WCP@Windows@@UEAAXPEBU_UNICODE_STRING@@@Z`
- size: `42`
- prototype: `void __fastcall(Windows::WCP::Implementation::Rtl::CBaseTracingStream *__hidden this, const struct _UNICODE_STRING *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180019d90`
- `0x18001c010`

## pseudocode

```c
void __fastcall Windows::WCP::Implementation::Rtl::CBaseTracingStream::WriteLiteralString(
        Windows::WCP::Implementation::Rtl::CBaseTracingStream *this,
        const struct _UNICODE_STRING *a2)
{
  if ( a2 )
    (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, unsigned __int64, PWSTR))(*(_QWORD *)this + 288LL))(
      this,
      (unsigned __int64)a2->Length >> 1,
      a2->Buffer);
}

```

## disassembly

```asm
0x180019d90  sub     rsp, 28h
0x180019d94  mov     r8, rdx
0x180019d97  test    rdx, rdx
0x180019d9a  jz      short loc_180019DB5
0x180019d9c  mov     rax, [rcx]
0x180019d9f  movzx   edx, word ptr [rdx]
0x180019da2  mov     r8, [r8+8]
0x180019da6  shr     rdx, 1
0x180019da9  mov     rax, [rax+120h]
0x180019db0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019db5  add     rsp, 28h
0x180019db9  retn
```
