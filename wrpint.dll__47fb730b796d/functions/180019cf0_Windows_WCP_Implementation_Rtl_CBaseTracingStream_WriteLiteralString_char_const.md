# Windows::WCP::Implementation::Rtl::CBaseTracingStream::WriteLiteralString(char const *)

- ea: `0x180019cf0`
- end: `0x180019d1e`
- name: `?WriteLiteralString@CBaseTracingStream@Rtl@Implementation@WCP@Windows@@UEAAXPEBD@Z`
- size: `46`
- prototype: `void __fastcall(Windows::WCP::Implementation::Rtl::CBaseTracingStream *__hidden this, const char *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180019cf0`
- `0x18001c010`

## pseudocode

```c
void __fastcall Windows::WCP::Implementation::Rtl::CBaseTracingStream::WriteLiteralString(
        Windows::WCP::Implementation::Rtl::CBaseTracingStream *this,
        const char *a2)
{
  __int64 v3; // rdx

  if ( a2 )
  {
    v3 = -1;
    do
      ++v3;
    while ( a2[v3] );
    (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *))(*(_QWORD *)this + 280LL))(this);
  }
}

```

## disassembly

```asm
0x180019cf0  sub     rsp, 28h
0x180019cf4  mov     r8, rdx
0x180019cf7  test    rdx, rdx
0x180019cfa  jz      short loc_180019D19
0x180019cfc  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180019d00  inc     rdx
0x180019d03  cmp     byte ptr [r8+rdx], 0
0x180019d08  jnz     short loc_180019D00
0x180019d0a  mov     rax, [rcx]
0x180019d0d  mov     rax, [rax+118h]
0x180019d14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019d19  add     rsp, 28h
0x180019d1d  retn
```
