# Windows::WCP::Implementation::Rtl::CBaseTracingStream::Write(_GUID const *)

- ea: `0x180018cb0`
- end: `0x180018e56`
- name: `?Write@CBaseTracingStream@Rtl@Implementation@WCP@Windows@@UEAAXPEBU_GUID@@@Z`
- size: `422`
- prototype: `void __fastcall(Windows::WCP::Implementation::Rtl::CBaseTracingStream *__hidden this, const struct _GUID *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180018cb0`
- `0x18001c010`

## pseudocode

```c
void __fastcall Windows::WCP::Implementation::Rtl::CBaseTracingStream::Write(
        Windows::WCP::Implementation::Rtl::CBaseTracingStream *this,
        const struct _GUID *a2)
{
  Windows::WCP::Implementation::Rtl::CBaseTracingStream *v3; // rbx
  void (__fastcall *v4)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, __int64 *); // rax
  __int64 *v5; // rdx
  __int64 v6; // rdx
  __int64 v7; // rdx
  __int64 v8; // rdx
  __int64 v9; // rdx
  __int64 v10; // rdx
  __int64 v11; // rdx
  __int64 v12; // rdx
  __int64 v13; // rdx

  v3 = this;
  v4 = *(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, __int64 *))(*(_QWORD *)this
                                                                                                 + 200LL);
  if ( a2 )
  {
    v4(
      this,
      ___LiteralObject__2U__BaseLiteralBuffer__01U_LUTF8_STRING__D_Details_RtlStringLiterals__3E0HL__0A_____0A__00_Details_RtlStringLiterals__3U_LUTF8_STRING__B);
    (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, _QWORD))(*(_QWORD *)v3 + 400LL))(
      v3,
      a2->Data1);
    (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, __int64 *))(*(_QWORD *)v3 + 200LL))(
      v3,
      ___LiteralObject__2U__BaseLiteralBuffer__01U_LUTF8_STRING__D_Details_RtlStringLiterals__3E0CN__0A_____0A__00_Details_RtlStringLiterals__3U_LUTF8_STRING__B);
    (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, _QWORD))(*(_QWORD *)v3 + 392LL))(
      v3,
      a2->Data2);
    (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, __int64 *))(*(_QWORD *)v3 + 200LL))(
      v3,
      ___LiteralObject__2U__BaseLiteralBuffer__01U_LUTF8_STRING__D_Details_RtlStringLiterals__3E0CN__0A_____0A__00_Details_RtlStringLiterals__3U_LUTF8_STRING__B);
    (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, _QWORD))(*(_QWORD *)v3 + 392LL))(
      v3,
      a2->Data3);
    (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, __int64 *))(*(_QWORD *)v3 + 200LL))(
      v3,
      ___LiteralObject__2U__BaseLiteralBuffer__01U_LUTF8_STRING__D_Details_RtlStringLiterals__3E0CN__0A_____0A__00_Details_RtlStringLiterals__3U_LUTF8_STRING__B);
    LOBYTE(v6) = a2->Data4[0];
    (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, __int64))(*(_QWORD *)v3 + 384LL))(
      v3,
      v6);
    LOBYTE(v7) = a2->Data4[1];
    (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, __int64))(*(_QWORD *)v3 + 384LL))(
      v3,
      v7);
    (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, __int64 *))(*(_QWORD *)v3 + 200LL))(
      v3,
      ___LiteralObject__2U__BaseLiteralBuffer__01U_LUTF8_STRING__D_Details_RtlStringLiterals__3E0CN__0A_____0A__00_Details_RtlStringLiterals__3U_LUTF8_STRING__B);
    LOBYTE(v8) = a2->Data4[2];
    (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, __int64))(*(_QWORD *)v3 + 384LL))(
      v3,
      v8);
    LOBYTE(v9) = a2->Data4[3];
    (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, __int64))(*(_QWORD *)v3 + 384LL))(
      v3,
      v9);
    LOBYTE(v10) = a2->Data4[4];
    (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, __int64))(*(_QWORD *)v3 + 384LL))(
      v3,
      v10);
    LOBYTE(v11) = a2->Data4[5];
    (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, __int64))(*(_QWORD *)v3 + 384LL))(
      v3,
      v11);
    LOBYTE(v12) = a2->Data4[6];
    (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, __int64))(*(_QWORD *)v3 + 384LL))(
      v3,
      v12);
    LOBYTE(v13) = a2->Data4[7];
    (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, __int64))(*(_QWORD *)v3 + 384LL))(
      v3,
      v13);
    v5 = ___LiteralObject__2U__BaseLiteralBuffer__01U_LUTF8_STRING__D_Details_RtlStringLiterals__3E0HN__0A_____0A__00_Details_RtlStringLiterals__3U_LUTF8_STRING__B;
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
0x180018cb0  mov     [rsp+arg_0], rbx
0x180018cb5  push    rdi
0x180018cb6  sub     rsp, 20h
0x180018cba  mov     rax, [rcx]
0x180018cbd  mov     rdi, rdx
0x180018cc0  mov     rbx, rcx
0x180018cc3  mov     rax, [rax+0C8h]
0x180018cca  test    rdx, rdx
0x180018ccd  jnz     short loc_180018CDB
0x180018ccf  lea     rdx, ??$LiteralObject@$2U?$BaseLiteralBuffer@$06U_LUTF8_STRING@@D@Details@RtlStringLiterals@@3E0CI@@0GO@@0HF@@0GM@@0GM@@0CJ@@0A@@@@$0A@$00$01$02$03$04$05@Details@RtlStringLiterals@@3U_LUTF8_STRING@@B
0x180018cd6  jmp     loc_180018E47
0x180018cdb  lea     rdx, ??$LiteralObject@$2U?$BaseLiteralBuffer@$01U_LUTF8_STRING@@D@Details@RtlStringLiterals@@3E0HL@@0A@@@@$0A@$00@Details@RtlStringLiterals@@3U_LUTF8_STRING@@B
0x180018ce2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018ce7  mov     rax, [rbx]
0x180018cea  mov     rcx, rbx
0x180018ced  mov     edx, [rdi]
0x180018cef  mov     rax, [rax+190h]
0x180018cf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018cfb  mov     rax, [rbx]
0x180018cfe  lea     rdx, ??$LiteralObject@$2U?$BaseLiteralBuffer@$01U_LUTF8_STRING@@D@Details@RtlStringLiterals@@3E0CN@@0A@@@@$0A@$00@Details@RtlStringLiterals@@3U_LUTF8_STRING@@B
0x180018d05  mov     rcx, rbx
0x180018d08  mov     rax, [rax+0C8h]
0x180018d0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018d14  mov     rax, [rbx]
0x180018d17  mov     rcx, rbx
0x180018d1a  movzx   edx, word ptr [rdi+4]
0x180018d1e  mov     rax, [rax+188h]
0x180018d25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018d2a  mov     rax, [rbx]
0x180018d2d  lea     rdx, ??$LiteralObject@$2U?$BaseLiteralBuffer@$01U_LUTF8_STRING@@D@Details@RtlStringLiterals@@3E0CN@@0A@@@@$0A@$00@Details@RtlStringLiterals@@3U_LUTF8_STRING@@B
0x180018d34  mov     rcx, rbx
0x180018d37  mov     rax, [rax+0C8h]
0x180018d3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018d43  mov     rax, [rbx]
0x180018d46  mov     rcx, rbx
0x180018d49  movzx   edx, word ptr [rdi+6]
0x180018d4d  mov     rax, [rax+188h]
0x180018d54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018d59  mov     rax, [rbx]
0x180018d5c  lea     rdx, ??$LiteralObject@$2U?$BaseLiteralBuffer@$01U_LUTF8_STRING@@D@Details@RtlStringLiterals@@3E0CN@@0A@@@@$0A@$00@Details@RtlStringLiterals@@3U_LUTF8_STRING@@B
0x180018d63  mov     rcx, rbx
0x180018d66  mov     rax, [rax+0C8h]
0x180018d6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018d72  mov     rax, [rbx]
0x180018d75  mov     rcx, rbx
0x180018d78  mov     dl, [rdi+8]
0x180018d7b  mov     rax, [rax+180h]
0x180018d82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018d87  mov     rax, [rbx]
0x180018d8a  mov     rcx, rbx
0x180018d8d  mov     dl, [rdi+9]
0x180018d90  mov     rax, [rax+180h]
0x180018d97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018d9c  mov     rax, [rbx]
0x180018d9f  lea     rdx, ??$LiteralObject@$2U?$BaseLiteralBuffer@$01U_LUTF8_STRING@@D@Details@RtlStringLiterals@@3E0CN@@0A@@@@$0A@$00@Details@RtlStringLiterals@@3U_LUTF8_STRING@@B
0x180018da6  mov     rcx, rbx
0x180018da9  mov     rax, [rax+0C8h]
0x180018db0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018db5  mov     rax, [rbx]
0x180018db8  mov     rcx, rbx
0x180018dbb  mov     dl, [rdi+0Ah]
0x180018dbe  mov     rax, [rax+180h]
0x180018dc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018dca  mov     rax, [rbx]
0x180018dcd  mov     rcx, rbx
0x180018dd0  mov     dl, [rdi+0Bh]
0x180018dd3  mov     rax, [rax+180h]
0x180018dda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018ddf  mov     rax, [rbx]
0x180018de2  mov     rcx, rbx
0x180018de5  mov     dl, [rdi+0Ch]
0x180018de8  mov     rax, [rax+180h]
0x180018def  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018df4  mov     rax, [rbx]
0x180018df7  mov     rcx, rbx
0x180018dfa  mov     dl, [rdi+0Dh]
0x180018dfd  mov     rax, [rax+180h]
0x180018e04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018e09  mov     rax, [rbx]
0x180018e0c  mov     rcx, rbx
0x180018e0f  mov     dl, [rdi+0Eh]
0x180018e12  mov     rax, [rax+180h]
0x180018e19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018e1e  mov     rax, [rbx]
0x180018e21  mov     rcx, rbx
0x180018e24  mov     dl, [rdi+0Fh]
0x180018e27  mov     rax, [rax+180h]
0x180018e2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018e33  mov     rax, [rbx]
0x180018e36  lea     rdx, ??$LiteralObject@$2U?$BaseLiteralBuffer@$01U_LUTF8_STRING@@D@Details@RtlStringLiterals@@3E0HN@@0A@@@@$0A@$00@Details@RtlStringLiterals@@3U_LUTF8_STRING@@B
0x180018e3d  mov     rcx, rbx
0x180018e40  mov     rax, [rax+0C8h]
0x180018e47  mov     rbx, [rsp+28h+arg_0]
0x180018e4c  add     rsp, 20h
0x180018e50  pop     rdi
0x180018e51  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
