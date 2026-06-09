# Windows::WCP::Implementation::Rtl::CBaseTracingStream::WriteEnum(ulong,Windows::Rtl::_FORMATTED_STREAM_ENUM_MAP const *)

- ea: `0x180019660`
- end: `0x180019701`
- name: `?WriteEnum@CBaseTracingStream@Rtl@Implementation@WCP@Windows@@UEAAXKPEBU_FORMATTED_STREAM_ENUM_MAP@25@@Z`
- size: `161`
- prototype: `void __fastcall(Windows::WCP::Implementation::Rtl::CBaseTracingStream *__hidden this, unsigned int, const struct Windows::Rtl::_FORMATTED_STREAM_ENUM_MAP *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180019660`
- `0x18001c010`

## pseudocode

```c
void __fastcall Windows::WCP::Implementation::Rtl::CBaseTracingStream::WriteEnum(
        Windows::WCP::Implementation::Rtl::CBaseTracingStream *this,
        unsigned int a2,
        const struct Windows::Rtl::_FORMATTED_STREAM_ENUM_MAP *a3)
{
  unsigned __int64 v3; // r9
  __int64 v4; // rax
  __int64 v6; // rcx

  if ( a3 )
  {
    v3 = *((_QWORD *)a3 + 1);
    v4 = 0;
    v6 = *((_QWORD *)a3 + 2);
    if ( v3 )
    {
      while ( a2 != *(_DWORD *)(v6 + 16 * v4) )
      {
        if ( ++v4 >= v3 )
          goto LABEL_5;
      }
      (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, _QWORD))(*(_QWORD *)this + 224LL))(
        this,
        *(_QWORD *)(v6 + 16 * v4 + 8));
    }
    else
    {
LABEL_5:
      if ( v4 == v3 )
      {
        (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, __int64 *))(*(_QWORD *)this + 200LL))(
          this,
          ___LiteralObject__2U__BaseLiteralBuffer__0BE_U_LUTF8_STRING__D_Details_RtlStringLiterals__3E0CI__0HF__0GO__0GL__0GO__0GP__0HH__0GO__0CA__0GF__0GO__0HF__0GN__0GF__0HC__0GB__0GO__0HE__0CA__0A_____0A__00_01_02_03_04_05_06_07_08_09_0L__0M__0N__0O__0P__0BA__0BB__0BC__0BD__Details_RtlStringLiterals__3U_LUTF8_STRING__B);
        (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, _QWORD))(*(_QWORD *)this + 344LL))(
          this,
          a2);
        (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, __int64 *))(*(_QWORD *)this + 200LL))(
          this,
          ___LiteralObject__2U__BaseLiteralBuffer__01U_LUTF8_STRING__D_Details_RtlStringLiterals__3E0CJ__0A_____0A__00_Details_RtlStringLiterals__3U_LUTF8_STRING__B);
      }
    }
  }
}

```

## disassembly

```asm
0x180019660  test    r8, r8
0x180019663  jz      locret_1800196EF
0x180019669  mov     [rsp+arg_0], rbx
0x18001966e  push    rdi
0x18001966f  sub     rsp, 20h
0x180019673  mov     r9, [r8+8]
0x180019677  xor     eax, eax
0x180019679  mov     rbx, rcx
0x18001967c  mov     rcx, [r8+10h]
0x180019680  mov     edi, edx
0x180019682  test    r9, r9
0x180019685  jz      short loc_18001969A
0x180019687  mov     rdx, rax
0x18001968a  add     rdx, rdx
0x18001968d  cmp     edi, [rcx+rdx*8]
0x180019690  jz      short loc_1800196F0
0x180019692  inc     rax
0x180019695  cmp     rax, r9
0x180019698  jb      short loc_180019687
0x18001969a  cmp     rax, r9
0x18001969d  jnz     short loc_1800196E5
0x18001969f  mov     rax, [rbx]
0x1800196a2  lea     rdx, ??$LiteralObject@$2U?$BaseLiteralBuffer@$0BE@U_LUTF8_STRING@@D@Details@RtlStringLiterals@@3E0CI@@0HF@@0GO@@0GL@@0GO@@0GP@@0HH@@0GO@@0CA@@0GF@@0GO@@0HF@@0GN@@0GF@@0HC@@0GB@@0GO@@0HE@@0CA@@0A@@@@$0A@$00$01$02$03$04$05$06$07$08$09$0L@$0M@$0N@$0O@$0P@$0BA@$0BB@$0BC@$0BD@@Details@RtlStringLiterals@@3U_LUTF8_STRING@@B
0x1800196a9  mov     rcx, rbx
0x1800196ac  mov     rax, [rax+0C8h]
0x1800196b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800196b8  mov     rax, [rbx]
0x1800196bb  mov     edx, edi
0x1800196bd  mov     rcx, rbx
0x1800196c0  mov     rax, [rax+158h]
0x1800196c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800196cc  mov     rax, [rbx]
0x1800196cf  lea     rdx, ??$LiteralObject@$2U?$BaseLiteralBuffer@$01U_LUTF8_STRING@@D@Details@RtlStringLiterals@@3E0CJ@@0A@@@@$0A@$00@Details@RtlStringLiterals@@3U_LUTF8_STRING@@B
0x1800196d6  mov     rax, [rax+0C8h]
0x1800196dd  mov     rcx, rbx
0x1800196e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800196e5  mov     rbx, [rsp+28h+arg_0]
0x1800196ea  add     rsp, 20h
0x1800196ee  pop     rdi
0x1800196ef  retn
0x1800196f0  mov     rax, [rbx]
0x1800196f3  mov     rdx, [rcx+rdx*8+8]
0x1800196f8  mov     rax, [rax+0E0h]
0x1800196ff  jmp     short loc_1800196DD
```
