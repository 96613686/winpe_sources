# Windows::WCP::Implementation::Rtl::CBaseTracingStream::Write(_LUNICODE_STRING const *)

- ea: `0x180018f90`
- end: `0x1800190dc`
- name: `?Write@CBaseTracingStream@Rtl@Implementation@WCP@Windows@@UEAAXPEBU_LUNICODE_STRING@@@Z`
- size: `332`
- prototype: `void __fastcall(Windows::WCP::Implementation::Rtl::CBaseTracingStream *__hidden this, const struct _LUNICODE_STRING *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180018f90`
- `0x18001c010`

## pseudocode

```c
void __fastcall Windows::WCP::Implementation::Rtl::CBaseTracingStream::Write(
        Windows::WCP::Implementation::Rtl::CBaseTracingStream *this,
        const struct _LUNICODE_STRING *a2)
{
  Windows::WCP::Implementation::Rtl::CBaseTracingStream *v3; // rbx
  void (__fastcall *v4)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, __int64 *); // rax
  __int64 *v5; // rdx
  unsigned __int64 v6; // rsi
  bool v7; // zf

  v3 = this;
  v4 = *(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, __int64 *))(*(_QWORD *)this
                                                                                                 + 200LL);
  if ( a2 )
  {
    v6 = *(_QWORD *)a2;
    if ( *((_QWORD *)a2 + 1) == *(_QWORD *)a2 )
    {
      v4(
        this,
        ___LiteralObject__2U__BaseLiteralBuffer__03U_LUTF8_STRING__D_Details_RtlStringLiterals__3E0FL__0GM__0DK__0A_____0A__00_01_02_Details_RtlStringLiterals__3U_LUTF8_STRING__B);
      (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, unsigned __int64))(*(_QWORD *)v3 + 376LL))(
        v3,
        v6 >> 1);
      v7 = (v6 & 1) == 0;
    }
    else
    {
      v4(
        this,
        ___LiteralObject__2U__BaseLiteralBuffer__03U_LUTF8_STRING__D_Details_RtlStringLiterals__3E0FL__0GM__0DK__0A_____0A__00_01_02_Details_RtlStringLiterals__3U_LUTF8_STRING__B);
      (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, _QWORD))(*(_QWORD *)v3 + 376LL))(
        v3,
        *(_QWORD *)a2 >> 1);
      if ( (*(_BYTE *)a2 & 1) != 0 )
        (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, __int64 *))(*(_QWORD *)v3 + 200LL))(
          v3,
          ___LiteralObject__2U__BaseLiteralBuffer__03U_LUTF8_STRING__D_Details_RtlStringLiterals__3E0CB__0CB__0CB__0A_____0A__00_01_02_Details_RtlStringLiterals__3U_LUTF8_STRING__B);
      (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, __int64 *))(*(_QWORD *)v3 + 200LL))(
        v3,
        ___LiteralObject__2U__BaseLiteralBuffer__04U_LUTF8_STRING__D_Details_RtlStringLiterals__3E0CA__0GN__0GM__0DK__0A_____0A__00_01_02_03_Details_RtlStringLiterals__3U_LUTF8_STRING__B);
      (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, _QWORD))(*(_QWORD *)v3 + 376LL))(
        v3,
        *((_QWORD *)a2 + 1) >> 1);
      v7 = (*((_BYTE *)a2 + 8) & 1) == 0;
    }
    if ( !v7 )
      (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, __int64 *))(*(_QWORD *)v3 + 200LL))(
        v3,
        ___LiteralObject__2U__BaseLiteralBuffer__03U_LUTF8_STRING__D_Details_RtlStringLiterals__3E0CB__0CB__0CB__0A_____0A__00_01_02_Details_RtlStringLiterals__3U_LUTF8_STRING__B);
    (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, __int64 *))(*(_QWORD *)v3 + 200LL))(
      v3,
      ___LiteralObject__2U__BaseLiteralBuffer__02U_LUTF8_STRING__D_Details_RtlStringLiterals__3E0FN__0CH__0A_____0A__00_01_Details_RtlStringLiterals__3U_LUTF8_STRING__B);
    (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, _QWORD, _QWORD))(*(_QWORD *)v3 + 288LL))(
      v3,
      *(_QWORD *)a2 >> 1,
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
0x180018f90  mov     [rsp+arg_0], rbx
0x180018f95  mov     [rsp+arg_8], rsi
0x180018f9a  push    rdi
0x180018f9b  sub     rsp, 20h
0x180018f9f  mov     rax, [rcx]
0x180018fa2  mov     rdi, rdx
0x180018fa5  mov     rbx, rcx
0x180018fa8  mov     rax, [rax+0C8h]
0x180018faf  test    rdx, rdx
0x180018fb2  jnz     short loc_180018FC0
0x180018fb4  lea     rdx, ??$LiteralObject@$2U?$BaseLiteralBuffer@$06U_LUTF8_STRING@@D@Details@RtlStringLiterals@@3E0CI@@0GO@@0HF@@0GM@@0GM@@0CJ@@0A@@@@$0A@$00$01$02$03$04$05@Details@RtlStringLiterals@@3U_LUTF8_STRING@@B
0x180018fbb  jmp     loc_1800190C8
0x180018fc0  mov     rsi, [rdx]
0x180018fc3  cmp     [rdx+8], rsi
0x180018fc7  lea     rdx, ??$LiteralObject@$2U?$BaseLiteralBuffer@$03U_LUTF8_STRING@@D@Details@RtlStringLiterals@@3E0FL@@0GM@@0DK@@0A@@@@$0A@$00$01$02@Details@RtlStringLiterals@@3U_LUTF8_STRING@@B
0x180018fce  jnz     short loc_180018FF3
0x180018fd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018fd5  mov     rax, [rbx]
0x180018fd8  mov     rdx, rsi
0x180018fdb  shr     rdx, 1
0x180018fde  mov     rcx, rbx
0x180018fe1  mov     rax, [rax+178h]
0x180018fe8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018fed  test    sil, 1
0x180018ff1  jmp     short loc_180019064
0x180018ff3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018ff8  mov     rax, [rbx]
0x180018ffb  mov     rcx, rbx
0x180018ffe  mov     rdx, [rdi]
0x180019001  shr     rdx, 1
0x180019004  mov     rax, [rax+178h]
0x18001900b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019010  test    byte ptr [rdi], 1
0x180019013  jz      short loc_18001902E
0x180019015  mov     rax, [rbx]
0x180019018  lea     rdx, ??$LiteralObject@$2U?$BaseLiteralBuffer@$03U_LUTF8_STRING@@D@Details@RtlStringLiterals@@3E0CB@@0CB@@0CB@@0A@@@@$0A@$00$01$02@Details@RtlStringLiterals@@3U_LUTF8_STRING@@B
0x18001901f  mov     rcx, rbx
0x180019022  mov     rax, [rax+0C8h]
0x180019029  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001902e  mov     rax, [rbx]
0x180019031  lea     rdx, ??$LiteralObject@$2U?$BaseLiteralBuffer@$04U_LUTF8_STRING@@D@Details@RtlStringLiterals@@3E0CA@@0GN@@0GM@@0DK@@0A@@@@$0A@$00$01$02$03@Details@RtlStringLiterals@@3U_LUTF8_STRING@@B
0x180019038  mov     rcx, rbx
0x18001903b  mov     rax, [rax+0C8h]
0x180019042  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019047  mov     rax, [rbx]
0x18001904a  mov     rcx, rbx
0x18001904d  mov     rdx, [rdi+8]
0x180019051  shr     rdx, 1
0x180019054  mov     rax, [rax+178h]
0x18001905b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019060  test    byte ptr [rdi+8], 1
0x180019064  jz      short loc_18001907F
0x180019066  mov     rax, [rbx]
0x180019069  lea     rdx, ??$LiteralObject@$2U?$BaseLiteralBuffer@$03U_LUTF8_STRING@@D@Details@RtlStringLiterals@@3E0CB@@0CB@@0CB@@0A@@@@$0A@$00$01$02@Details@RtlStringLiterals@@3U_LUTF8_STRING@@B
0x180019070  mov     rcx, rbx
0x180019073  mov     rax, [rax+0C8h]
0x18001907a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001907f  mov     rax, [rbx]
0x180019082  lea     rdx, ??$LiteralObject@$2U?$BaseLiteralBuffer@$02U_LUTF8_STRING@@D@Details@RtlStringLiterals@@3E0FN@@0CH@@0A@@@@$0A@$00$01@Details@RtlStringLiterals@@3U_LUTF8_STRING@@B
0x180019089  mov     rcx, rbx
0x18001908c  mov     rax, [rax+0C8h]
0x180019093  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019098  mov     rax, [rbx]
0x18001909b  mov     rcx, rbx
0x18001909e  mov     rdx, [rdi]
0x1800190a1  mov     r8, [rdi+10h]
0x1800190a5  shr     rdx, 1
0x1800190a8  mov     rax, [rax+120h]
0x1800190af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800190b4  mov     rax, [rbx]
0x1800190b7  lea     rdx, ??$LiteralObject@$2U?$BaseLiteralBuffer@$01U_LUTF8_STRING@@D@Details@RtlStringLiterals@@3E0CH@@0A@@@@$0A@$00@Details@RtlStringLiterals@@3U_LUTF8_STRING@@B
0x1800190be  mov     rcx, rbx
0x1800190c1  mov     rax, [rax+0C8h]
0x1800190c8  mov     rbx, [rsp+28h+arg_0]
0x1800190cd  mov     rsi, [rsp+28h+arg_8]
0x1800190d2  add     rsp, 20h
0x1800190d6  pop     rdi
0x1800190d7  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
