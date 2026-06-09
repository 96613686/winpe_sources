# Windows::WCP::Implementation::Rtl::CBaseTracingStream::Write(_UNICODE_STRING const *)

- ea: `0x1800191d0`
- end: `0x1800192a7`
- name: `?Write@CBaseTracingStream@Rtl@Implementation@WCP@Windows@@UEAAXPEBU_UNICODE_STRING@@@Z`
- size: `215`
- prototype: `void __fastcall(Windows::WCP::Implementation::Rtl::CBaseTracingStream *this, const struct _UNICODE_STRING *, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180007568`
- `0x180007c90`
- `0x1800191d0`
- `0x18001b7b0`
- `0x18001c010`

## pseudocode

```c
void __fastcall Windows::WCP::Implementation::Rtl::CBaseTracingStream::Write(
        Windows::WCP::Implementation::Rtl::CBaseTracingStream *this,
        const struct _UNICODE_STRING *a2,
        __int64 a3)
{
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // r8
  __int64 v7; // r9
  __int64 v8; // rax
  const char *v9; // [rsp+20h] [rbp-48h]
  const char *v10; // [rsp+28h] [rbp-40h]
  __int64 v11; // [rsp+30h] [rbp-38h]
  const char *v12; // [rsp+38h] [rbp-30h]
  __m128i v13; // [rsp+40h] [rbp-28h] BYREF
  __int64 v14; // [rsp+50h] [rbp-18h]

  if ( a2 )
  {
    v13 = 0u;
    v14 = 0;
    if ( (unsigned __int8)RtlIsUnicodeStringValid(a2) )
    {
      v8 = *(_QWORD *)(v7 + 8);
      v13 = _mm_unpacklo_epi32(_mm_unpacklo_epi16(_mm_cvtsi32_si128(*(_DWORD *)v7), (__m128i)0LL), (__m128i)0LL);
      v14 = v8;
    }
    else
    {
      v11 = 333;
      v9 = "onecore\\base\\lstring\\lunicode_string.cpp";
      v10 = "RtlInitLUnicodeStringFromUnicodeString";
      v12 = "::RtlIsUnicodeStringValid(Source)";
      RtlReportErrorOrigination(v5, v4, 3221225485LL);
    }
    (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, __m128i *, __int64, __int64, const char *, const char *, __int64, const char *))(*(_QWORD *)this + 144LL))(
      this,
      &v13,
      v6,
      v7,
      v9,
      v10,
      v11,
      v12);
  }
  else
  {
    (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, __int64 *, __int64, _QWORD))(*(_QWORD *)this + 200LL))(
      this,
      ___LiteralObject__2U__BaseLiteralBuffer__06U_LUTF8_STRING__D_Details_RtlStringLiterals__3E0CI__0GO__0HF__0GM__0GM__0CJ__0A_____0A__00_01_02_03_04_05_Details_RtlStringLiterals__3U_LUTF8_STRING__B,
      a3,
      0);
  }
}

```

## disassembly

```asm
0x1800191d0  push    rbx
0x1800191d2  sub     rsp, 60h
0x1800191d6  mov     rax, cs:__security_cookie
0x1800191dd  xor     rax, rsp
0x1800191e0  mov     [rsp+68h+var_10], rax
0x1800191e5  xor     r10d, r10d
0x1800191e8  mov     r9, rdx
0x1800191eb  mov     rbx, rcx
0x1800191ee  test    rdx, rdx
0x1800191f1  jnz     short loc_180019209
0x1800191f3  mov     rax, [rcx]
0x1800191f6  lea     rdx, ??$LiteralObject@$2U?$BaseLiteralBuffer@$06U_LUTF8_STRING@@D@Details@RtlStringLiterals@@3E0CI@@0GO@@0HF@@0GM@@0GM@@0CJ@@0A@@@@$0A@$00$01$02$03$04$05@Details@RtlStringLiterals@@3U_LUTF8_STRING@@B
0x1800191fd  mov     rax, [rax+0C8h]
0x180019204  jmp     loc_18001928F
0x180019209  mov     rcx, r9
0x18001920c  mov     qword ptr [rsp+68h+var_28], r10
0x180019211  mov     qword ptr [rsp+68h+var_28+8], r10
0x180019216  mov     [rsp+68h+var_18], r10
0x18001921b  call    RtlIsUnicodeStringValid
0x180019220  test    al, al
0x180019222  jnz     short loc_18001925E
0x180019224  lea     rax, aOnecoreBaseLst_2; "onecore\\base\\lstring\\lunicode_string"...
0x18001922b  mov     [rsp+68h+var_38], 14Dh
0x180019234  mov     [rsp+68h+var_48], rax
0x180019239  mov     r8d, 0C000000Dh
0x18001923f  lea     rax, aRtlinitlunicod_0; "RtlInitLUnicodeStringFromUnicodeString"
0x180019246  mov     [rsp+68h+var_40], rax
0x18001924b  lea     rax, aRtlisunicodest; "::RtlIsUnicodeStringValid(Source)"
0x180019252  mov     [rsp+68h+var_30], rax
0x180019257  call    RtlReportErrorOrigination
0x18001925c  jmp     short loc_18001927D
0x18001925e  movd    xmm1, dword ptr [r9]
0x180019263  xorps   xmm0, xmm0
0x180019266  mov     rax, [r9+8]
0x18001926a  punpcklwd xmm1, xmm0
0x18001926e  punpckldq xmm1, xmm0
0x180019272  movdqu  [rsp+68h+var_28], xmm1
0x180019278  mov     [rsp+68h+var_18], rax
0x18001927d  mov     rax, [rbx]
0x180019280  lea     rdx, [rsp+68h+var_28]
0x180019285  mov     rcx, rbx
0x180019288  mov     rax, [rax+90h]
0x18001928f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019294  mov     rcx, [rsp+68h+var_10]
0x180019299  xor     rcx, rsp; StackCookie
0x18001929c  call    __security_check_cookie
0x1800192a1  add     rsp, 60h
0x1800192a5  pop     rbx
0x1800192a6  retn
```
