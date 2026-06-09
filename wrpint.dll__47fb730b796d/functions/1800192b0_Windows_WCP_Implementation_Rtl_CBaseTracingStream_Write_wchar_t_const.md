# Windows::WCP::Implementation::Rtl::CBaseTracingStream::Write(wchar_t const *)

- ea: `0x1800192b0`
- end: `0x18001933b`
- name: `?Write@CBaseTracingStream@Rtl@Implementation@WCP@Windows@@UEAAXPEB_W@Z`
- size: `139`
- prototype: `void __fastcall(Windows::WCP::Implementation::Rtl::CBaseTracingStream *__hidden this, const wchar_t *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800192b0`
- `0x18001c010`

## pseudocode

```c
void __fastcall Windows::WCP::Implementation::Rtl::CBaseTracingStream::Write(
        Windows::WCP::Implementation::Rtl::CBaseTracingStream *this,
        const wchar_t *a2)
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
    (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, __int64, const wchar_t *))(*(_QWORD *)v3 + 288LL))(
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
0x1800192b0  mov     [rsp+arg_0], rbx
0x1800192b5  mov     [rsp+arg_8], rsi
0x1800192ba  push    rdi
0x1800192bb  sub     rsp, 20h
0x1800192bf  xor     eax, eax
0x1800192c1  mov     rsi, rdx
0x1800192c4  mov     rdi, rcx
0x1800192c7  test    rdx, rdx
0x1800192ca  jnz     short loc_1800192D8
0x1800192cc  mov     rax, [rcx]
0x1800192cf  lea     rdx, ??$LiteralObject@$2U?$BaseLiteralBuffer@$06U_LUTF8_STRING@@D@Details@RtlStringLiterals@@3E0CI@@0GO@@0HF@@0GM@@0GM@@0CJ@@0A@@@@$0A@$00$01$02$03$04$05@Details@RtlStringLiterals@@3U_LUTF8_STRING@@B
0x1800192d6  jmp     short loc_180019320
0x1800192d8  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800192dc  inc     rbx
0x1800192df  cmp     [rdx+rbx*2], ax
0x1800192e3  jnz     short loc_1800192DC
0x1800192e5  mov     rax, [rcx]
0x1800192e8  lea     rdx, ??$LiteralObject@$2U?$BaseLiteralBuffer@$01U_LUTF8_STRING@@D@Details@RtlStringLiterals@@3E0CH@@0A@@@@$0A@$00@Details@RtlStringLiterals@@3U_LUTF8_STRING@@B
0x1800192ef  mov     rax, [rax+0C8h]
0x1800192f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800192fb  mov     rax, [rdi]
0x1800192fe  mov     r8, rsi
0x180019301  mov     rdx, rbx
0x180019304  mov     rcx, rdi
0x180019307  mov     rax, [rax+120h]
0x18001930e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019313  mov     rax, [rdi]
0x180019316  lea     rdx, ??$LiteralObject@$2U?$BaseLiteralBuffer@$01U_LUTF8_STRING@@D@Details@RtlStringLiterals@@3E0CH@@0A@@@@$0A@$00@Details@RtlStringLiterals@@3U_LUTF8_STRING@@B
0x18001931d  mov     rcx, rdi
0x180019320  mov     rax, [rax+0C8h]
0x180019327  mov     rbx, [rsp+28h+arg_0]
0x18001932c  mov     rsi, [rsp+28h+arg_8]
0x180019331  add     rsp, 20h
0x180019335  pop     rdi
0x180019336  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
