# Windows::WCP::Implementation::Rtl::CBaseTracingStream::Write(_LBLOB const *)

- ea: `0x180018e60`
- end: `0x180018f81`
- name: `?Write@CBaseTracingStream@Rtl@Implementation@WCP@Windows@@UEAAXPEBU_LBLOB@@@Z`
- size: `289`
- prototype: `void __fastcall(Windows::WCP::Implementation::Rtl::CBaseTracingStream *__hidden this, const struct _LBLOB *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180018e60`
- `0x18001c010`

## pseudocode

```c
void __fastcall Windows::WCP::Implementation::Rtl::CBaseTracingStream::Write(
        Windows::WCP::Implementation::Rtl::CBaseTracingStream *this,
        const struct _LBLOB *a2)
{
  Windows::WCP::Implementation::Rtl::CBaseTracingStream *v3; // rdi
  void (__fastcall *v4)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, __int64 *); // rax
  __int64 *v5; // rdx
  unsigned __int64 v6; // rsi
  __int64 v7; // rbx
  __int64 v8; // rbp
  __int64 v9; // rbx
  __int64 v10; // rdx

  v3 = this;
  v4 = *(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, __int64 *))(*(_QWORD *)this
                                                                                                 + 200LL);
  if ( a2 )
  {
    v6 = *(_QWORD *)a2;
    v7 = *((_QWORD *)a2 + 1);
    v4(
      this,
      ___LiteralObject__2U__BaseLiteralBuffer__03U_LUTF8_STRING__D_Details_RtlStringLiterals__3E0HL__0GM__0DK__0A_____0A__00_01_02_Details_RtlStringLiterals__3U_LUTF8_STRING__B);
    (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, _QWORD))(*(_QWORD *)v3 + 376LL))(
      v3,
      *(_QWORD *)a2);
    if ( v6 != v7 )
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
      ___LiteralObject__2U__BaseLiteralBuffer__03U_LUTF8_STRING__D_Details_RtlStringLiterals__3E0CA__0GC__0DK__0A_____0A__00_01_02_Details_RtlStringLiterals__3U_LUTF8_STRING__B);
    if ( v6 <= 0x80 )
    {
      v8 = v6;
      if ( !v6 )
      {
LABEL_12:
        v5 = ___LiteralObject__2U__BaseLiteralBuffer__01U_LUTF8_STRING__D_Details_RtlStringLiterals__3E0HN__0A_____0A__00_Details_RtlStringLiterals__3U_LUTF8_STRING__B;
        this = v3;
        v4 = *(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, __int64 *))(*(_QWORD *)v3 + 200LL);
        goto LABEL_13;
      }
    }
    else
    {
      v8 = 128;
    }
    v9 = 0;
    do
    {
      v10 = *((_QWORD *)a2 + 2);
      LOBYTE(v10) = *(_BYTE *)(v9 + v10);
      (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, __int64))(*(_QWORD *)v3 + 384LL))(
        v3,
        v10);
      ++v9;
    }
    while ( v9 != v8 );
    if ( v6 > 0x80 )
      (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, __int64 *))(*(_QWORD *)v3 + 200LL))(
        v3,
        ___LiteralObject__2U__BaseLiteralBuffer__03U_LUTF8_STRING__D_Details_RtlStringLiterals__3E0CO__0CO__0CO__0A_____0A__00_01_02_Details_RtlStringLiterals__3U_LUTF8_STRING__B);
    goto LABEL_12;
  }
  v5 = ___LiteralObject__2U__BaseLiteralBuffer__06U_LUTF8_STRING__D_Details_RtlStringLiterals__3E0CI__0GO__0HF__0GM__0GM__0CJ__0A_____0A__00_01_02_03_04_05_Details_RtlStringLiterals__3U_LUTF8_STRING__B;
LABEL_13:
  v4(this, v5);
}

```

## disassembly

```asm
0x180018e60  push    rbx
0x180018e62  push    rbp
0x180018e63  push    rsi
0x180018e64  push    rdi
0x180018e65  push    r14
0x180018e67  push    r15
0x180018e69  sub     rsp, 28h
0x180018e6d  mov     rax, [rcx]
0x180018e70  mov     r14, rdx
0x180018e73  mov     rdi, rcx
0x180018e76  mov     rax, [rax+0C8h]
0x180018e7d  test    rdx, rdx
0x180018e80  jnz     short loc_180018E8E
0x180018e82  lea     rdx, ??$LiteralObject@$2U?$BaseLiteralBuffer@$06U_LUTF8_STRING@@D@Details@RtlStringLiterals@@3E0CI@@0GO@@0HF@@0GM@@0GM@@0CJ@@0A@@@@$0A@$00$01$02$03$04$05@Details@RtlStringLiterals@@3U_LUTF8_STRING@@B
0x180018e89  jmp     loc_180018F70
0x180018e8e  mov     rsi, [rdx]
0x180018e91  mov     rbx, [rdx+8]
0x180018e95  lea     rdx, ??$LiteralObject@$2U?$BaseLiteralBuffer@$03U_LUTF8_STRING@@D@Details@RtlStringLiterals@@3E0HL@@0GM@@0DK@@0A@@@@$0A@$00$01$02@Details@RtlStringLiterals@@3U_LUTF8_STRING@@B
0x180018e9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018ea1  mov     rax, [rdi]
0x180018ea4  mov     rcx, rdi
0x180018ea7  mov     rdx, [r14]
0x180018eaa  mov     rax, [rax+178h]
0x180018eb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018eb6  cmp     rsi, rbx
0x180018eb9  jz      short loc_180018EEA
0x180018ebb  mov     rax, [rdi]
0x180018ebe  lea     rdx, ??$LiteralObject@$2U?$BaseLiteralBuffer@$04U_LUTF8_STRING@@D@Details@RtlStringLiterals@@3E0CA@@0GN@@0GM@@0DK@@0A@@@@$0A@$00$01$02$03@Details@RtlStringLiterals@@3U_LUTF8_STRING@@B
0x180018ec5  mov     rcx, rdi
0x180018ec8  mov     rax, [rax+0C8h]
0x180018ecf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018ed4  mov     rax, [rdi]
0x180018ed7  mov     rcx, rdi
0x180018eda  mov     rdx, [r14+8]
0x180018ede  mov     rax, [rax+178h]
0x180018ee5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018eea  mov     rax, [rdi]
0x180018eed  lea     rdx, ??$LiteralObject@$2U?$BaseLiteralBuffer@$03U_LUTF8_STRING@@D@Details@RtlStringLiterals@@3E0CA@@0GC@@0DK@@0A@@@@$0A@$00$01$02@Details@RtlStringLiterals@@3U_LUTF8_STRING@@B
0x180018ef4  mov     rcx, rdi
0x180018ef7  mov     rax, [rax+0C8h]
0x180018efe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018f03  mov     r15d, 80h
0x180018f09  cmp     rsi, r15
0x180018f0c  jbe     short loc_180018F13
0x180018f0e  mov     ebp, r15d
0x180018f11  jmp     short loc_180018F1B
0x180018f13  mov     rbp, rsi
0x180018f16  test    rsi, rsi
0x180018f19  jz      short loc_180018F5C
0x180018f1b  xor     ebx, ebx
0x180018f1d  mov     rax, [rdi]
0x180018f20  mov     rcx, rdi
0x180018f23  mov     rdx, [r14+10h]
0x180018f27  mov     rax, [rax+180h]
0x180018f2e  mov     dl, [rbx+rdx]
0x180018f31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018f36  inc     rbx
0x180018f39  cmp     rbx, rbp
0x180018f3c  jnz     short loc_180018F1D
0x180018f3e  cmp     rsi, r15
0x180018f41  jbe     short loc_180018F5C
0x180018f43  mov     rax, [rdi]
0x180018f46  lea     rdx, ??$LiteralObject@$2U?$BaseLiteralBuffer@$03U_LUTF8_STRING@@D@Details@RtlStringLiterals@@3E0CO@@0CO@@0CO@@0A@@@@$0A@$00$01$02@Details@RtlStringLiterals@@3U_LUTF8_STRING@@B
0x180018f4d  mov     rcx, rdi
0x180018f50  mov     rax, [rax+0C8h]
0x180018f57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018f5c  mov     rax, [rdi]
0x180018f5f  lea     rdx, ??$LiteralObject@$2U?$BaseLiteralBuffer@$01U_LUTF8_STRING@@D@Details@RtlStringLiterals@@3E0HN@@0A@@@@$0A@$00@Details@RtlStringLiterals@@3U_LUTF8_STRING@@B
0x180018f66  mov     rcx, rdi
0x180018f69  mov     rax, [rax+0C8h]
0x180018f70  add     rsp, 28h
0x180018f74  pop     r15
0x180018f76  pop     r14
0x180018f78  pop     rdi
0x180018f79  pop     rsi
0x180018f7a  pop     rbp
0x180018f7b  pop     rbx
0x180018f7c  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
