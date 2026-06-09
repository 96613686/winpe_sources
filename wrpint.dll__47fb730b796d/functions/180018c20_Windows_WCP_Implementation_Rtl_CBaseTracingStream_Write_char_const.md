# Windows::WCP::Implementation::Rtl::CBaseTracingStream::Write(char const *)

- ea: `0x180018c20`
- end: `0x180018ca9`
- name: `?Write@CBaseTracingStream@Rtl@Implementation@WCP@Windows@@UEAAXPEBD@Z`
- size: `137`
- prototype: `void __fastcall(Windows::WCP::Implementation::Rtl::CBaseTracingStream *__hidden this, const char *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180018c20`
- `0x18001c010`

## pseudocode

```c
void __fastcall Windows::WCP::Implementation::Rtl::CBaseTracingStream::Write(
        Windows::WCP::Implementation::Rtl::CBaseTracingStream *this,
        const char *a2)
{
  Windows::WCP::Implementation::Rtl::CBaseTracingStream *v3; // rdi
  __int64 v4; // rax
  __int64 *v5; // rdx
  __int64 v6; // rbx

  v3 = this;
  if ( a2 )
  {
    v6 = -1;
    do
      ++v6;
    while ( a2[v6] );
    (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, __int64 *))(*(_QWORD *)this + 200LL))(
      this,
      ___LiteralObject__2U__BaseLiteralBuffer__01U_LUTF8_STRING__D_Details_RtlStringLiterals__3E0CH__0A_____0A__00_Details_RtlStringLiterals__3U_LUTF8_STRING__B);
    (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, __int64, const char *))(*(_QWORD *)v3 + 264LL))(
      v3,
      v6,
      a2);
    v4 = *(_QWORD *)v3;
    v5 = ___LiteralObject__2U__BaseLiteralBuffer__01U_LUTF8_STRING__D_Details_RtlStringLiterals__3E0CH__0A_____0A__00_Details_RtlStringLiterals__3U_LUTF8_STRING__B;
    this = v3;
  }
  else
  {
    v4 = *(_QWORD *)this;
    v5 = ___LiteralObject__2U__BaseLiteralBuffer__06U_LUTF8_STRING__D_Details_RtlStringLiterals__3E0CI__0GO__0HF__0GM__0GM__0CJ__0A_____0A__00_01_02_03_04_05_Details_RtlStringLiterals__3U_LUTF8_STRING__B;
  }
  (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, __int64 *))(v4 + 200))(this, v5);
}

```

## disassembly

```asm
0x180018c20  mov     [rsp+arg_0], rbx
0x180018c25  mov     [rsp+arg_8], rsi
0x180018c2a  push    rdi
0x180018c2b  sub     rsp, 20h
0x180018c2f  mov     rsi, rdx
0x180018c32  mov     rdi, rcx
0x180018c35  test    rdx, rdx
0x180018c38  jnz     short loc_180018C46
0x180018c3a  mov     rax, [rcx]
0x180018c3d  lea     rdx, ??$LiteralObject@$2U?$BaseLiteralBuffer@$06U_LUTF8_STRING@@D@Details@RtlStringLiterals@@3E0CI@@0GO@@0HF@@0GM@@0GM@@0CJ@@0A@@@@$0A@$00$01$02$03$04$05@Details@RtlStringLiterals@@3U_LUTF8_STRING@@B
0x180018c44  jmp     short loc_180018C8E
0x180018c46  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180018c4a  inc     rbx
0x180018c4d  cmp     byte ptr [rdx+rbx], 0
0x180018c51  jnz     short loc_180018C4A
0x180018c53  mov     rax, [rcx]
0x180018c56  lea     rdx, ??$LiteralObject@$2U?$BaseLiteralBuffer@$01U_LUTF8_STRING@@D@Details@RtlStringLiterals@@3E0CH@@0A@@@@$0A@$00@Details@RtlStringLiterals@@3U_LUTF8_STRING@@B
0x180018c5d  mov     rax, [rax+0C8h]
0x180018c64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018c69  mov     rax, [rdi]
0x180018c6c  mov     r8, rsi
0x180018c6f  mov     rdx, rbx
0x180018c72  mov     rcx, rdi
0x180018c75  mov     rax, [rax+108h]
0x180018c7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018c81  mov     rax, [rdi]
0x180018c84  lea     rdx, ??$LiteralObject@$2U?$BaseLiteralBuffer@$01U_LUTF8_STRING@@D@Details@RtlStringLiterals@@3E0CH@@0A@@@@$0A@$00@Details@RtlStringLiterals@@3U_LUTF8_STRING@@B
0x180018c8b  mov     rcx, rdi
0x180018c8e  mov     rax, [rax+0C8h]
0x180018c95  mov     rbx, [rsp+28h+arg_0]
0x180018c9a  mov     rsi, [rsp+28h+arg_8]
0x180018c9f  add     rsp, 20h
0x180018ca3  pop     rdi
0x180018ca4  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
