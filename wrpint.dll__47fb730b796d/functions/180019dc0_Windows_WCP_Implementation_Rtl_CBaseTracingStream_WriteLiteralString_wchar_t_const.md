# Windows::WCP::Implementation::Rtl::CBaseTracingStream::WriteLiteralString(wchar_t const *)

- ea: `0x180019dc0`
- end: `0x180019df0`
- name: `?WriteLiteralString@CBaseTracingStream@Rtl@Implementation@WCP@Windows@@UEAAXPEB_W@Z`
- size: `48`
- prototype: `void __fastcall(Windows::WCP::Implementation::Rtl::CBaseTracingStream *__hidden this, const wchar_t *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180019dc0`
- `0x18001c010`

## pseudocode

```c
void __fastcall Windows::WCP::Implementation::Rtl::CBaseTracingStream::WriteLiteralString(
        Windows::WCP::Implementation::Rtl::CBaseTracingStream *this,
        const wchar_t *a2)
{
  __int64 v3; // rdx

  if ( a2 )
  {
    v3 = -1;
    do
      ++v3;
    while ( a2[v3] );
    (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *))(*(_QWORD *)this + 288LL))(this);
  }
}

```

## disassembly

```asm
0x180019dc0  sub     rsp, 28h
0x180019dc4  xor     eax, eax
0x180019dc6  mov     r8, rdx
0x180019dc9  test    rdx, rdx
0x180019dcc  jz      short loc_180019DEB
0x180019dce  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180019dd2  inc     rdx
0x180019dd5  cmp     [r8+rdx*2], ax
0x180019dda  jnz     short loc_180019DD2
0x180019ddc  mov     rax, [rcx]
0x180019ddf  mov     rax, [rax+120h]
0x180019de6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019deb  add     rsp, 28h
0x180019def  retn
```
