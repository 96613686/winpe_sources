# Windows::WCP::Implementation::Rtl::CBaseTracingStream::Write(unsigned __int64,wchar_t const * const)

- ea: `0x1800195b0`
- end: `0x18001964c`
- name: `?Write@CBaseTracingStream@Rtl@Implementation@WCP@Windows@@UEAAX_KQEB_W@Z`
- size: `156`
- prototype: `void __fastcall(Windows::WCP::Implementation::Rtl::CBaseTracingStream *this, __int64, const wchar_t *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18001c010`

## pseudocode

```c
void __fastcall Windows::WCP::Implementation::Rtl::CBaseTracingStream::Write(
        Windows::WCP::Implementation::Rtl::CBaseTracingStream *this,
        __int64 a2,
        const wchar_t *a3)
{
  (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, __int64 *))(*(_QWORD *)this + 200LL))(
    this,
    ___LiteralObject__2U__BaseLiteralBuffer__01U_LUTF8_STRING__D_Details_RtlStringLiterals__3E0FL__0A_____0A__00_Details_RtlStringLiterals__3U_LUTF8_STRING__B);
  (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, __int64))(*(_QWORD *)this + 376LL))(
    this,
    a2);
  (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, __int64 *))(*(_QWORD *)this + 200LL))(
    this,
    ___LiteralObject__2U__BaseLiteralBuffer__02U_LUTF8_STRING__D_Details_RtlStringLiterals__3E0FN__0CH__0A_____0A__00_01_Details_RtlStringLiterals__3U_LUTF8_STRING__B);
  (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, __int64, const wchar_t *))(*(_QWORD *)this + 288LL))(
    this,
    a2,
    a3);
  (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, __int64 *))(*(_QWORD *)this + 200LL))(
    this,
    ___LiteralObject__2U__BaseLiteralBuffer__01U_LUTF8_STRING__D_Details_RtlStringLiterals__3E0CH__0A_____0A__00_Details_RtlStringLiterals__3U_LUTF8_STRING__B);
}

```

## disassembly

```asm
0x1800195b0  mov     [rsp+arg_0], rbx
0x1800195b5  mov     [rsp+arg_8], rsi
0x1800195ba  push    rdi
0x1800195bb  sub     rsp, 20h
0x1800195bf  mov     rax, [rcx]
0x1800195c2  mov     rdi, rdx
0x1800195c5  lea     rdx, ??$LiteralObject@$2U?$BaseLiteralBuffer@$01U_LUTF8_STRING@@D@Details@RtlStringLiterals@@3E0FL@@0A@@@@$0A@$00@Details@RtlStringLiterals@@3U_LUTF8_STRING@@B
0x1800195cc  mov     rbx, r8
0x1800195cf  mov     rsi, rcx
0x1800195d2  mov     rax, [rax+0C8h]
0x1800195d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800195de  mov     rax, [rsi]
0x1800195e1  mov     rdx, rdi
0x1800195e4  mov     rcx, rsi
0x1800195e7  mov     rax, [rax+178h]
0x1800195ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800195f3  mov     rax, [rsi]
0x1800195f6  lea     rdx, ??$LiteralObject@$2U?$BaseLiteralBuffer@$02U_LUTF8_STRING@@D@Details@RtlStringLiterals@@3E0FN@@0CH@@0A@@@@$0A@$00$01@Details@RtlStringLiterals@@3U_LUTF8_STRING@@B
0x1800195fd  mov     rcx, rsi
0x180019600  mov     rax, [rax+0C8h]
0x180019607  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001960c  mov     rax, [rsi]
0x18001960f  mov     r8, rbx
0x180019612  mov     rdx, rdi
0x180019615  mov     rcx, rsi
0x180019618  mov     rax, [rax+120h]
0x18001961f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019624  mov     rax, [rsi]
0x180019627  lea     rdx, ??$LiteralObject@$2U?$BaseLiteralBuffer@$01U_LUTF8_STRING@@D@Details@RtlStringLiterals@@3E0CH@@0A@@@@$0A@$00@Details@RtlStringLiterals@@3U_LUTF8_STRING@@B
0x18001962e  mov     rcx, rsi
0x180019631  mov     rax, [rax+0C8h]
0x180019638  mov     rbx, [rsp+28h+arg_0]
0x18001963d  mov     rsi, [rsp+28h+arg_8]
0x180019642  add     rsp, 20h
0x180019646  pop     rdi
0x180019647  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
