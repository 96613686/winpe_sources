# Windows::WCP::Implementation::Rtl::CBaseTracingStream::WritePointer(void const *)

- ea: `0x18001a120`
- end: `0x18001a173`
- name: `?WritePointer@CBaseTracingStream@Rtl@Implementation@WCP@Windows@@UEAAXPEBX@Z`
- size: `83`
- prototype: `void __fastcall(Windows::WCP::Implementation::Rtl::CBaseTracingStream *this, __int64 *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18001a120`
- `0x18001c010`

## pseudocode

```c
void __fastcall Windows::WCP::Implementation::Rtl::CBaseTracingStream::WritePointer(
        Windows::WCP::Implementation::Rtl::CBaseTracingStream *this,
        __int64 *a2)
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
      ___LiteralObject__2U__BaseLiteralBuffer__03U_LUTF8_STRING__D_Details_RtlStringLiterals__3E0EA__0DA__0HI__0A_____0A__00_01_02_Details_RtlStringLiterals__3U_LUTF8_STRING__B);
    v5 = a2;
    this = v3;
    v4 = *(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, __int64 *))(*(_QWORD *)v3 + 456LL);
  }
  else
  {
    v5 = ___LiteralObject__2U__BaseLiteralBuffer__04U_LUTF8_STRING__D_Details_RtlStringLiterals__3E0EO__0FF__0EM__0EM__0A_____0A__00_01_02_03_Details_RtlStringLiterals__3U_LUTF8_STRING__B;
  }
  v4(this, v5);
}

```

## disassembly

```asm
0x18001a120  mov     [rsp+arg_0], rbx
0x18001a125  push    rdi
0x18001a126  sub     rsp, 20h
0x18001a12a  mov     rax, [rcx]
0x18001a12d  mov     rdi, rdx
0x18001a130  mov     rbx, rcx
0x18001a133  mov     rax, [rax+0C8h]
0x18001a13a  test    rdx, rdx
0x18001a13d  jnz     short loc_18001A148
0x18001a13f  lea     rdx, ??$LiteralObject@$2U?$BaseLiteralBuffer@$04U_LUTF8_STRING@@D@Details@RtlStringLiterals@@3E0EO@@0FF@@0EM@@0EM@@0A@@@@$0A@$00$01$02$03@Details@RtlStringLiterals@@3U_LUTF8_STRING@@B
0x18001a146  jmp     short loc_18001A164
0x18001a148  lea     rdx, ??$LiteralObject@$2U?$BaseLiteralBuffer@$03U_LUTF8_STRING@@D@Details@RtlStringLiterals@@3E0EA@@0DA@@0HI@@0A@@@@$0A@$00$01$02@Details@RtlStringLiterals@@3U_LUTF8_STRING@@B
0x18001a14f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a154  mov     rax, [rbx]
0x18001a157  mov     rdx, rdi
0x18001a15a  mov     rcx, rbx
0x18001a15d  mov     rax, [rax+1C8h]
0x18001a164  mov     rbx, [rsp+28h+arg_0]
0x18001a169  add     rsp, 20h
0x18001a16d  pop     rdi
0x18001a16e  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
