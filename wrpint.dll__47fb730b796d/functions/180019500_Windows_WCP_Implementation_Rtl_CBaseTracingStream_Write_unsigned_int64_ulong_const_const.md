# Windows::WCP::Implementation::Rtl::CBaseTracingStream::Write(unsigned __int64,ulong const * const)

- ea: `0x180019500`
- end: `0x18001959c`
- name: `?Write@CBaseTracingStream@Rtl@Implementation@WCP@Windows@@UEAAX_KQEBK@Z`
- size: `156`
- prototype: `void __fastcall(Windows::WCP::Implementation::Rtl::CBaseTracingStream *this, __int64, const unsigned int *)`
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
        const unsigned int *a3)
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
  (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, __int64, const unsigned int *))(*(_QWORD *)this + 296LL))(
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
0x180019500  mov     [rsp+arg_0], rbx
0x180019505  mov     [rsp+arg_8], rsi
0x18001950a  push    rdi
0x18001950b  sub     rsp, 20h
0x18001950f  mov     rax, [rcx]
0x180019512  mov     rdi, rdx
0x180019515  lea     rdx, ??$LiteralObject@$2U?$BaseLiteralBuffer@$01U_LUTF8_STRING@@D@Details@RtlStringLiterals@@3E0FL@@0A@@@@$0A@$00@Details@RtlStringLiterals@@3U_LUTF8_STRING@@B
0x18001951c  mov     rbx, r8
0x18001951f  mov     rsi, rcx
0x180019522  mov     rax, [rax+0C8h]
0x180019529  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001952e  mov     rax, [rsi]
0x180019531  mov     rdx, rdi
0x180019534  mov     rcx, rsi
0x180019537  mov     rax, [rax+178h]
0x18001953e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019543  mov     rax, [rsi]
0x180019546  lea     rdx, ??$LiteralObject@$2U?$BaseLiteralBuffer@$02U_LUTF8_STRING@@D@Details@RtlStringLiterals@@3E0FN@@0CH@@0A@@@@$0A@$00$01@Details@RtlStringLiterals@@3U_LUTF8_STRING@@B
0x18001954d  mov     rcx, rsi
0x180019550  mov     rax, [rax+0C8h]
0x180019557  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001955c  mov     rax, [rsi]
0x18001955f  mov     r8, rbx
0x180019562  mov     rdx, rdi
0x180019565  mov     rcx, rsi
0x180019568  mov     rax, [rax+128h]
0x18001956f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019574  mov     rax, [rsi]
0x180019577  lea     rdx, ??$LiteralObject@$2U?$BaseLiteralBuffer@$01U_LUTF8_STRING@@D@Details@RtlStringLiterals@@3E0CH@@0A@@@@$0A@$00@Details@RtlStringLiterals@@3U_LUTF8_STRING@@B
0x18001957e  mov     rcx, rsi
0x180019581  mov     rax, [rax+0C8h]
0x180019588  mov     rbx, [rsp+28h+arg_0]
0x18001958d  mov     rsi, [rsp+28h+arg_8]
0x180019592  add     rsp, 20h
0x180019596  pop     rdi
0x180019597  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
