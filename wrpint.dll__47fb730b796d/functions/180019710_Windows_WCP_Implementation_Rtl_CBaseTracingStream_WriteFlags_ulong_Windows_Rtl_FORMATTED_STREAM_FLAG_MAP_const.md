# Windows::WCP::Implementation::Rtl::CBaseTracingStream::WriteFlags(ulong,Windows::Rtl::_FORMATTED_STREAM_FLAG_MAP const *)

- ea: `0x180019710`
- end: `0x180019842`
- name: `?WriteFlags@CBaseTracingStream@Rtl@Implementation@WCP@Windows@@UEAAXKPEBU_FORMATTED_STREAM_FLAG_MAP@25@@Z`
- size: `306`
- prototype: `void __fastcall(Windows::WCP::Implementation::Rtl::CBaseTracingStream *__hidden this, unsigned int, const struct Windows::Rtl::_FORMATTED_STREAM_FLAG_MAP *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180019710`
- `0x18001c010`

## pseudocode

```c
void __fastcall Windows::WCP::Implementation::Rtl::CBaseTracingStream::WriteFlags(
        Windows::WCP::Implementation::Rtl::CBaseTracingStream *this,
        unsigned int a2,
        const struct Windows::Rtl::_FORMATTED_STREAM_FLAG_MAP *a3)
{
  char v3; // r13
  unsigned __int64 v6; // r15
  char v7; // bp
  __int64 v8; // r12
  unsigned __int64 v9; // rsi
  void (__fastcall *v10)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, __int64 *); // rax
  void (__fastcall *v11)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, __int64 *); // rax

  v3 = 0;
  if ( !a3 )
    goto LABEL_12;
  v6 = *(_QWORD *)a3;
  v7 = 0;
  v8 = *((_QWORD *)a3 + 1);
  v9 = 0;
  if ( !*(_QWORD *)a3 )
    goto LABEL_12;
  do
  {
    if ( (a2 & *(_DWORD *)(v8 + 16 * v9)) == *(_DWORD *)(v8 + 16 * v9) )
    {
      v10 = *(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, __int64 *))(*(_QWORD *)this + 200LL);
      if ( v7 )
      {
        v10(
          this,
          ___LiteralObject__2U__BaseLiteralBuffer__01U_LUTF8_STRING__D_Details_RtlStringLiterals__3E0HM__0A_____0A__00_Details_RtlStringLiterals__3U_LUTF8_STRING__B);
      }
      else
      {
        v10(
          this,
          ___LiteralObject__2U__BaseLiteralBuffer__01U_LUTF8_STRING__D_Details_RtlStringLiterals__3E0CI__0A_____0A__00_Details_RtlStringLiterals__3U_LUTF8_STRING__B);
        v3 = 1;
        v7 = 1;
      }
      (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, _QWORD))(*(_QWORD *)this + 224LL))(
        this,
        *(_QWORD *)(v8 + 16 * v9 + 8));
      a2 &= ~*(_DWORD *)(v8 + 16 * v9);
    }
    ++v9;
  }
  while ( v9 < v6 );
  if ( !v7 )
    goto LABEL_12;
  if ( a2 )
  {
    (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, __int64 *))(*(_QWORD *)this + 200LL))(
      this,
      ___LiteralObject__2U__BaseLiteralBuffer__01U_LUTF8_STRING__D_Details_RtlStringLiterals__3E0HM__0A_____0A__00_Details_RtlStringLiterals__3U_LUTF8_STRING__B);
LABEL_12:
    v11 = *(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, __int64 *))(*(_QWORD *)this + 200LL);
    if ( a2 )
    {
      v11(
        this,
        ___LiteralObject__2U__BaseLiteralBuffer__02U_LUTF8_STRING__D_Details_RtlStringLiterals__3E0DA__0HI__0A_____0A__00_01_Details_RtlStringLiterals__3U_LUTF8_STRING__B);
      (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, _QWORD))(*(_QWORD *)this + 400LL))(
        this,
        a2);
    }
    else
    {
      v11(
        this,
        ___LiteralObject__2U__BaseLiteralBuffer__01U_LUTF8_STRING__D_Details_RtlStringLiterals__3E0DA__0A_____0A__00_Details_RtlStringLiterals__3U_LUTF8_STRING__B);
    }
  }
  if ( v3 )
    (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, __int64 *))(*(_QWORD *)this + 200LL))(
      this,
      ___LiteralObject__2U__BaseLiteralBuffer__01U_LUTF8_STRING__D_Details_RtlStringLiterals__3E0CJ__0A_____0A__00_Details_RtlStringLiterals__3U_LUTF8_STRING__B);
}

```

## disassembly

```asm
0x180019710  push    rbx
0x180019712  push    rbp
0x180019713  push    rsi
0x180019714  push    rdi
0x180019715  push    r12
0x180019717  push    r13
0x180019719  push    r14
0x18001971b  push    r15
0x18001971d  sub     rsp, 28h
0x180019721  xor     r13b, r13b
0x180019724  mov     edi, edx
0x180019726  mov     rbx, rcx
0x180019729  test    r8, r8
0x18001972c  jz      loc_1800197D4
0x180019732  mov     r15, [r8]
0x180019735  xor     bpl, bpl
0x180019738  mov     r12, [r8+8]
0x18001973c  xor     esi, esi
0x18001973e  test    r15, r15
0x180019741  jz      loc_1800197D4
0x180019747  mov     r14, rsi
0x18001974a  add     r14, r14
0x18001974d  mov     eax, [r12+r14*8]
0x180019751  and     eax, edi
0x180019753  cmp     eax, [r12+r14*8]
0x180019757  jnz     short loc_1800197AA
0x180019759  mov     rax, [rbx]
0x18001975c  mov     rcx, rbx
0x18001975f  mov     rax, [rax+0C8h]
0x180019766  test    bpl, bpl
0x180019769  jnz     short loc_18001977F
0x18001976b  lea     rdx, ??$LiteralObject@$2U?$BaseLiteralBuffer@$01U_LUTF8_STRING@@D@Details@RtlStringLiterals@@3E0CI@@0A@@@@$0A@$00@Details@RtlStringLiterals@@3U_LUTF8_STRING@@B
0x180019772  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019777  mov     r13b, 1
0x18001977a  mov     bpl, r13b
0x18001977d  jmp     short loc_18001978B
0x18001977f  lea     rdx, ??$LiteralObject@$2U?$BaseLiteralBuffer@$01U_LUTF8_STRING@@D@Details@RtlStringLiterals@@3E0HM@@0A@@@@$0A@$00@Details@RtlStringLiterals@@3U_LUTF8_STRING@@B
0x180019786  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001978b  mov     rax, [rbx]
0x18001978e  mov     rcx, rbx
0x180019791  mov     rdx, [r12+r14*8+8]
0x180019796  mov     rax, [rax+0E0h]
0x18001979d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800197a2  mov     eax, [r12+r14*8]
0x1800197a6  not     eax
0x1800197a8  and     edi, eax
0x1800197aa  inc     rsi
0x1800197ad  cmp     rsi, r15
0x1800197b0  jb      short loc_180019747
0x1800197b2  test    bpl, bpl
0x1800197b5  jz      short loc_1800197D4
0x1800197b7  test    edi, edi
0x1800197b9  jz      short loc_180019813
0x1800197bb  mov     rax, [rbx]
0x1800197be  lea     rdx, ??$LiteralObject@$2U?$BaseLiteralBuffer@$01U_LUTF8_STRING@@D@Details@RtlStringLiterals@@3E0HM@@0A@@@@$0A@$00@Details@RtlStringLiterals@@3U_LUTF8_STRING@@B
0x1800197c5  mov     rcx, rbx
0x1800197c8  mov     rax, [rax+0C8h]
0x1800197cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800197d4  mov     rax, [rbx]
0x1800197d7  mov     rcx, rbx
0x1800197da  mov     rax, [rax+0C8h]
0x1800197e1  test    edi, edi
0x1800197e3  jnz     short loc_1800197F3
0x1800197e5  lea     rdx, ??$LiteralObject@$2U?$BaseLiteralBuffer@$01U_LUTF8_STRING@@D@Details@RtlStringLiterals@@3E0DA@@0A@@@@$0A@$00@Details@RtlStringLiterals@@3U_LUTF8_STRING@@B
0x1800197ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800197f1  jmp     short loc_180019813
0x1800197f3  lea     rdx, ??$LiteralObject@$2U?$BaseLiteralBuffer@$02U_LUTF8_STRING@@D@Details@RtlStringLiterals@@3E0DA@@0HI@@0A@@@@$0A@$00$01@Details@RtlStringLiterals@@3U_LUTF8_STRING@@B
0x1800197fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800197ff  mov     rax, [rbx]
0x180019802  mov     edx, edi
0x180019804  mov     rcx, rbx
0x180019807  mov     rax, [rax+190h]
0x18001980e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019813  test    r13b, r13b
0x180019816  jz      short loc_180019831
0x180019818  mov     rax, [rbx]
0x18001981b  lea     rdx, ??$LiteralObject@$2U?$BaseLiteralBuffer@$01U_LUTF8_STRING@@D@Details@RtlStringLiterals@@3E0CJ@@0A@@@@$0A@$00@Details@RtlStringLiterals@@3U_LUTF8_STRING@@B
0x180019822  mov     rcx, rbx
0x180019825  mov     rax, [rax+0C8h]
0x18001982c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019831  add     rsp, 28h
0x180019835  pop     r15
0x180019837  pop     r14
0x180019839  pop     r13
0x18001983b  pop     r12
0x18001983d  pop     rdi
0x18001983e  pop     rsi
0x18001983f  pop     rbp
0x180019840  pop     rbx
0x180019841  retn
```
