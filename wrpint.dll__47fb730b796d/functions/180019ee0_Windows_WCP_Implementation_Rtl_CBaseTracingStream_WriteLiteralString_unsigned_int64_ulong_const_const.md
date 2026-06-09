# Windows::WCP::Implementation::Rtl::CBaseTracingStream::WriteLiteralString(unsigned __int64,ulong const * const)

- ea: `0x180019ee0`
- end: `0x180019fed`
- name: `?WriteLiteralString@CBaseTracingStream@Rtl@Implementation@WCP@Windows@@UEAAX_KQEBK@Z`
- size: `269`
- prototype: `void __fastcall(Windows::WCP::Implementation::Rtl::CBaseTracingStream *__hidden this, unsigned __int64, const unsigned int *const)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180019ee0`
- `0x18001b7b0`
- `0x18001c010`

## pseudocode

```c
void __fastcall Windows::WCP::Implementation::Rtl::CBaseTracingStream::WriteLiteralString(
        Windows::WCP::Implementation::Rtl::CBaseTracingStream *this,
        unsigned __int64 a2,
        const unsigned int *const a3)
{
  unsigned __int64 v6; // rbx
  unsigned __int64 i; // rsi
  unsigned int v8; // ebp
  _BYTE v9[32]; // [rsp+20h] [rbp-58h] BYREF

  if ( a2 && a3 )
  {
    v6 = 0;
    for ( i = 0; i < a2; ++i )
    {
      v8 = a3[i];
      if ( v6 >= 0x20 )
      {
        (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, __int64, _BYTE *))(*(_QWORD *)this + 280LL))(
          this,
          32,
          v9);
        v6 = 0;
      }
      if ( v8 >= 0x80 )
      {
        (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, unsigned __int64, _BYTE *))(*(_QWORD *)this + 280LL))(
          this,
          v6,
          v9);
        v6 = 0;
        (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, __int64 *))(*(_QWORD *)this + 200LL))(
          this,
          ___LiteralObject__2U__BaseLiteralBuffer__02U_LUTF8_STRING__D_Details_RtlStringLiterals__3E0FM__0HF__0A_____0A__00_01_Details_RtlStringLiterals__3U_LUTF8_STRING__B);
        (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, _QWORD))(*(_QWORD *)this + 400LL))(
          this,
          v8);
      }
      else
      {
        v9[v6++] = v8;
      }
    }
    if ( v6 )
      (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, unsigned __int64, _BYTE *))(*(_QWORD *)this + 280LL))(
        this,
        v6,
        v9);
  }
}

```

## disassembly

```asm
0x180019ee0  test    rdx, rdx
0x180019ee3  jz      locret_180019FEC
0x180019ee9  mov     [rsp+arg_8], rbx
0x180019eee  push    rbp
0x180019eef  push    rsi
0x180019ef0  push    rdi
0x180019ef1  push    r14
0x180019ef3  push    r15
0x180019ef5  sub     rsp, 50h
0x180019ef9  mov     rax, cs:__security_cookie
0x180019f00  xor     rax, rsp
0x180019f03  mov     [rsp+78h+var_38], rax
0x180019f08  mov     r14, r8
0x180019f0b  mov     r15, rdx
0x180019f0e  mov     rdi, rcx
0x180019f11  test    r8, r8
0x180019f14  jz      loc_180019FCC
0x180019f1a  xor     ebx, ebx
0x180019f1c  xor     esi, esi
0x180019f1e  mov     ebp, [r14+rsi*4]
0x180019f22  cmp     rbx, 20h ; ' '
0x180019f26  jb      short loc_180019F46
0x180019f28  mov     rax, [rdi]
0x180019f2b  lea     r8, [rsp+78h+var_58]
0x180019f30  mov     edx, 20h ; ' '
0x180019f35  mov     rcx, rdi
0x180019f38  mov     rax, [rax+118h]
0x180019f3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019f44  xor     ebx, ebx
0x180019f46  cmp     ebp, 80h
0x180019f4c  jnb     short loc_180019F58
0x180019f4e  mov     [rsp+rbx+78h+var_58], bpl
0x180019f53  inc     rbx
0x180019f56  jmp     short loc_180019FA1
0x180019f58  mov     rax, [rdi]
0x180019f5b  lea     r8, [rsp+78h+var_58]
0x180019f60  mov     rdx, rbx
0x180019f63  mov     rcx, rdi
0x180019f66  mov     rax, [rax+118h]
0x180019f6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019f72  mov     rax, [rdi]
0x180019f75  lea     rdx, ??$LiteralObject@$2U?$BaseLiteralBuffer@$02U_LUTF8_STRING@@D@Details@RtlStringLiterals@@3E0FM@@0HF@@0A@@@@$0A@$00$01@Details@RtlStringLiterals@@3U_LUTF8_STRING@@B
0x180019f7c  mov     rcx, rdi
0x180019f7f  xor     ebx, ebx
0x180019f81  mov     rax, [rax+0C8h]
0x180019f88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019f8d  mov     rax, [rdi]
0x180019f90  mov     edx, ebp
0x180019f92  mov     rcx, rdi
0x180019f95  mov     rax, [rax+190h]
0x180019f9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019fa1  inc     rsi
0x180019fa4  cmp     rsi, r15
0x180019fa7  jb      loc_180019F1E
0x180019fad  test    rbx, rbx
0x180019fb0  jz      short loc_180019FCC
0x180019fb2  mov     rax, [rdi]
0x180019fb5  lea     r8, [rsp+78h+var_58]
0x180019fba  mov     rdx, rbx
0x180019fbd  mov     rcx, rdi
0x180019fc0  mov     rax, [rax+118h]
0x180019fc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019fcc  mov     rcx, [rsp+78h+var_38]
0x180019fd1  xor     rcx, rsp; StackCookie
0x180019fd4  call    __security_check_cookie
0x180019fd9  mov     rbx, [rsp+78h+arg_8]
0x180019fe1  add     rsp, 50h
0x180019fe5  pop     r15
0x180019fe7  pop     r14
0x180019fe9  pop     rdi
0x180019fea  pop     rsi
0x180019feb  pop     rbp
0x180019fec  retn
```
