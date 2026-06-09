# Windows::WCP::Implementation::Rtl::CBaseTracingStream::Write(unsigned __int64,uchar const * const)

- ea: `0x180019450`
- end: `0x1800194ec`
- name: `?Write@CBaseTracingStream@Rtl@Implementation@WCP@Windows@@UEAAX_KQEBE@Z`
- size: `156`
- prototype: `void __fastcall(Windows::WCP::Implementation::Rtl::CBaseTracingStream *this, __int64, const unsigned __int8 *)`
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
        const unsigned __int8 *a3)
{
  (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, __int64 *))(*(_QWORD *)this + 200LL))(
    this,
    ___LiteralObject__2U__BaseLiteralBuffer__01U_LUTF8_STRING__D_Details_RtlStringLiterals__3E0FL__0A_____0A__00_Details_RtlStringLiterals__3U_LUTF8_STRING__B);
  (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, __int64))(*(_QWORD *)this + 376LL))(
    this,
    a2);
  (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, __int64 *))(*(_QWORD *)this + 200LL))(
    this,
    ___LiteralObject__2U__BaseLiteralBuffer__01U_LUTF8_STRING__D_Details_RtlStringLiterals__3E0CH__0A_____0A__00_Details_RtlStringLiterals__3U_LUTF8_STRING__B);
  (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, __int64, const unsigned __int8 *))(*(_QWORD *)this + 280LL))(
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
0x180019450  mov     [rsp+arg_0], rbx
0x180019455  mov     [rsp+arg_8], rsi
0x18001945a  push    rdi
0x18001945b  sub     rsp, 20h
0x18001945f  mov     rax, [rcx]
0x180019462  mov     rdi, rdx
0x180019465  lea     rdx, ??$LiteralObject@$2U?$BaseLiteralBuffer@$01U_LUTF8_STRING@@D@Details@RtlStringLiterals@@3E0FL@@0A@@@@$0A@$00@Details@RtlStringLiterals@@3U_LUTF8_STRING@@B
0x18001946c  mov     rbx, r8
0x18001946f  mov     rsi, rcx
0x180019472  mov     rax, [rax+0C8h]
0x180019479  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001947e  mov     rax, [rsi]
0x180019481  mov     rdx, rdi
0x180019484  mov     rcx, rsi
0x180019487  mov     rax, [rax+178h]
0x18001948e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019493  mov     rax, [rsi]
0x180019496  lea     rdx, ??$LiteralObject@$2U?$BaseLiteralBuffer@$01U_LUTF8_STRING@@D@Details@RtlStringLiterals@@3E0CH@@0A@@@@$0A@$00@Details@RtlStringLiterals@@3U_LUTF8_STRING@@B
0x18001949d  mov     rcx, rsi
0x1800194a0  mov     rax, [rax+0C8h]
0x1800194a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800194ac  mov     rax, [rsi]
0x1800194af  mov     r8, rbx
0x1800194b2  mov     rdx, rdi
0x1800194b5  mov     rcx, rsi
0x1800194b8  mov     rax, [rax+118h]
0x1800194bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800194c4  mov     rax, [rsi]
0x1800194c7  lea     rdx, ??$LiteralObject@$2U?$BaseLiteralBuffer@$01U_LUTF8_STRING@@D@Details@RtlStringLiterals@@3E0CH@@0A@@@@$0A@$00@Details@RtlStringLiterals@@3U_LUTF8_STRING@@B
0x1800194ce  mov     rcx, rsi
0x1800194d1  mov     rax, [rax+0C8h]
0x1800194d8  mov     rbx, [rsp+28h+arg_0]
0x1800194dd  mov     rsi, [rsp+28h+arg_8]
0x1800194e2  add     rsp, 20h
0x1800194e6  pop     rdi
0x1800194e7  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
