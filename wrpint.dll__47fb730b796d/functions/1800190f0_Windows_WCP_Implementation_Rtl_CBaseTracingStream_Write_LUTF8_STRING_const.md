# Windows::WCP::Implementation::Rtl::CBaseTracingStream::Write(_LUTF8_STRING const *)

- ea: `0x1800190f0`
- end: `0x1800191c9`
- name: `?Write@CBaseTracingStream@Rtl@Implementation@WCP@Windows@@UEAAXPEBU_LUTF8_STRING@@@Z`
- size: `217`
- prototype: `void __fastcall(Windows::WCP::Implementation::Rtl::CBaseTracingStream *__hidden this, const struct _LUTF8_STRING *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800190f0`
- `0x18001c010`

## pseudocode

```c
void __fastcall Windows::WCP::Implementation::Rtl::CBaseTracingStream::Write(
        Windows::WCP::Implementation::Rtl::CBaseTracingStream *this,
        const struct _LUTF8_STRING *a2)
{
  Windows::WCP::Implementation::Rtl::CBaseTracingStream *v3; // rbx
  void (__fastcall *v4)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, __int64 *); // rax
  __int64 *v5; // rdx

  v3 = this;
  v4 = *(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, __int64 *))(*(_QWORD *)this
                                                                                                 + 200LL);
  if ( a2 )
  {
    v4(
      this,
      ___LiteralObject__2U__BaseLiteralBuffer__03U_LUTF8_STRING__D_Details_RtlStringLiterals__3E0FL__0GM__0DK__0A_____0A__00_01_02_Details_RtlStringLiterals__3U_LUTF8_STRING__B);
    (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, _QWORD))(*(_QWORD *)v3 + 376LL))(
      v3,
      *(_QWORD *)a2);
    if ( *(_QWORD *)a2 != *((_QWORD *)a2 + 1) )
    {
      (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, __int64 *))(*(_QWORD *)v3 + 200LL))(
        v3,
        ___LiteralObject__2U__BaseLiteralBuffer__04U_LUTF8_STRING__D_Details_RtlStringLiterals__3E0CA__0GN__0GM__0DK__0A_____0A__00_01_02_03_Details_RtlStringLiterals__3U_LUTF8_STRING__B);
      (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, _QWORD))(*(_QWORD *)v3 + 376LL))(
        v3,
        *((_QWORD *)a2 + 1));
    }
    (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, __int64 *))(*(_QWORD *)v3 + 200LL))(
      v3,
      ___LiteralObject__2U__BaseLiteralBuffer__02U_LUTF8_STRING__D_Details_RtlStringLiterals__3E0FN__0CH__0A_____0A__00_01_Details_RtlStringLiterals__3U_LUTF8_STRING__B);
    (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, _QWORD, _QWORD))(*(_QWORD *)v3 + 280LL))(
      v3,
      *(_QWORD *)a2,
      *((_QWORD *)a2 + 2));
    v5 = ___LiteralObject__2U__BaseLiteralBuffer__01U_LUTF8_STRING__D_Details_RtlStringLiterals__3E0CH__0A_____0A__00_Details_RtlStringLiterals__3U_LUTF8_STRING__B;
    this = v3;
    v4 = *(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, __int64 *))(*(_QWORD *)v3 + 200LL);
  }
  else
  {
    v5 = ___LiteralObject__2U__BaseLiteralBuffer__06U_LUTF8_STRING__D_Details_RtlStringLiterals__3E0CI__0GO__0HF__0GM__0GM__0CJ__0A_____0A__00_01_02_03_04_05_Details_RtlStringLiterals__3U_LUTF8_STRING__B;
  }
  v4(this, v5);
}

```

## disassembly

```asm
0x1800190f0  mov     [rsp+arg_0], rbx
0x1800190f5  push    rdi
0x1800190f6  sub     rsp, 20h
0x1800190fa  mov     rax, [rcx]
0x1800190fd  mov     rdi, rdx
0x180019100  mov     rbx, rcx
0x180019103  mov     rax, [rax+0C8h]
0x18001910a  test    rdx, rdx
0x18001910d  jnz     short loc_18001911B
0x18001910f  lea     rdx, ??$LiteralObject@$2U?$BaseLiteralBuffer@$06U_LUTF8_STRING@@D@Details@RtlStringLiterals@@3E0CI@@0GO@@0HF@@0GM@@0GM@@0CJ@@0A@@@@$0A@$00$01$02$03$04$05@Details@RtlStringLiterals@@3U_LUTF8_STRING@@B
0x180019116  jmp     loc_1800191BA
0x18001911b  lea     rdx, ??$LiteralObject@$2U?$BaseLiteralBuffer@$03U_LUTF8_STRING@@D@Details@RtlStringLiterals@@3E0FL@@0GM@@0DK@@0A@@@@$0A@$00$01$02@Details@RtlStringLiterals@@3U_LUTF8_STRING@@B
0x180019122  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019127  mov     rax, [rbx]
0x18001912a  mov     rcx, rbx
0x18001912d  mov     rdx, [rdi]
0x180019130  mov     rax, [rax+178h]
0x180019137  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001913c  mov     rax, [rdi+8]
0x180019140  cmp     [rdi], rax
0x180019143  jz      short loc_180019174
0x180019145  mov     rax, [rbx]
0x180019148  lea     rdx, ??$LiteralObject@$2U?$BaseLiteralBuffer@$04U_LUTF8_STRING@@D@Details@RtlStringLiterals@@3E0CA@@0GN@@0GM@@0DK@@0A@@@@$0A@$00$01$02$03@Details@RtlStringLiterals@@3U_LUTF8_STRING@@B
0x18001914f  mov     rcx, rbx
0x180019152  mov     rax, [rax+0C8h]
0x180019159  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001915e  mov     rax, [rbx]
0x180019161  mov     rcx, rbx
0x180019164  mov     rdx, [rdi+8]
0x180019168  mov     rax, [rax+178h]
0x18001916f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019174  mov     rax, [rbx]
0x180019177  lea     rdx, ??$LiteralObject@$2U?$BaseLiteralBuffer@$02U_LUTF8_STRING@@D@Details@RtlStringLiterals@@3E0FN@@0CH@@0A@@@@$0A@$00$01@Details@RtlStringLiterals@@3U_LUTF8_STRING@@B
0x18001917e  mov     rcx, rbx
0x180019181  mov     rax, [rax+0C8h]
0x180019188  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001918d  mov     rax, [rbx]
0x180019190  mov     rcx, rbx
0x180019193  mov     r8, [rdi+10h]
0x180019197  mov     rdx, [rdi]
0x18001919a  mov     rax, [rax+118h]
0x1800191a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800191a6  mov     rax, [rbx]
0x1800191a9  lea     rdx, ??$LiteralObject@$2U?$BaseLiteralBuffer@$01U_LUTF8_STRING@@D@Details@RtlStringLiterals@@3E0CH@@0A@@@@$0A@$00@Details@RtlStringLiterals@@3U_LUTF8_STRING@@B
0x1800191b0  mov     rcx, rbx
0x1800191b3  mov     rax, [rax+0C8h]
0x1800191ba  mov     rbx, [rsp+28h+arg_0]
0x1800191bf  add     rsp, 20h
0x1800191c3  pop     rdi
0x1800191c4  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
