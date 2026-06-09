# Windows::WCP::Implementation::Rtl::CBaseTracingStream::WriteLiteralString(unsigned __int64,wchar_t const * const)

- ea: `0x18001a000`
- end: `0x18001a111`
- name: `?WriteLiteralString@CBaseTracingStream@Rtl@Implementation@WCP@Windows@@UEAAX_KQEB_W@Z`
- size: `273`
- prototype: `void __fastcall(Windows::WCP::Implementation::Rtl::CBaseTracingStream *__hidden this, unsigned __int64, const wchar_t *const)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18001a000`
- `0x18001b7b0`
- `0x18001c010`

## pseudocode

```c
void __fastcall Windows::WCP::Implementation::Rtl::CBaseTracingStream::WriteLiteralString(
        Windows::WCP::Implementation::Rtl::CBaseTracingStream *this,
        unsigned __int64 a2,
        const wchar_t *const a3)
{
  unsigned __int64 v6; // rbx
  unsigned __int64 i; // rsi
  wchar_t v8; // bp
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
      if ( v8 >= 0x80u )
      {
        (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, unsigned __int64, _BYTE *))(*(_QWORD *)this + 280LL))(
          this,
          v6,
          v9);
        v6 = 0;
        (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, __int64 *))(*(_QWORD *)this + 200LL))(
          this,
          ___LiteralObject__2U__BaseLiteralBuffer__02U_LUTF8_STRING__D_Details_RtlStringLiterals__3E0FM__0HF__0A_____0A__00_01_Details_RtlStringLiterals__3U_LUTF8_STRING__B);
        (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, _QWORD))(*(_QWORD *)this + 392LL))(
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
0x18001a000  test    rdx, rdx
0x18001a003  jz      locret_18001A110
0x18001a009  mov     [rsp+arg_8], rbx
0x18001a00e  push    rbp
0x18001a00f  push    rsi
0x18001a010  push    rdi
0x18001a011  push    r14
0x18001a013  push    r15
0x18001a015  sub     rsp, 50h
0x18001a019  mov     rax, cs:__security_cookie
0x18001a020  xor     rax, rsp
0x18001a023  mov     [rsp+78h+var_38], rax
0x18001a028  mov     r14, r8
0x18001a02b  mov     r15, rdx
0x18001a02e  mov     rdi, rcx
0x18001a031  test    r8, r8
0x18001a034  jz      loc_18001A0F0
0x18001a03a  xor     ebx, ebx
0x18001a03c  xor     esi, esi
0x18001a03e  movzx   ebp, word ptr [r14+rsi*2]
0x18001a043  cmp     rbx, 20h ; ' '
0x18001a047  jb      short loc_18001A067
0x18001a049  mov     rax, [rdi]
0x18001a04c  lea     r8, [rsp+78h+var_58]
0x18001a051  mov     edx, 20h ; ' '
0x18001a056  mov     rcx, rdi
0x18001a059  mov     rax, [rax+118h]
0x18001a060  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a065  xor     ebx, ebx
0x18001a067  mov     eax, 80h
0x18001a06c  cmp     bp, ax
0x18001a06f  jnb     short loc_18001A07B
0x18001a071  mov     [rsp+rbx+78h+var_58], bpl
0x18001a076  inc     rbx
0x18001a079  jmp     short loc_18001A0C5
0x18001a07b  mov     rax, [rdi]
0x18001a07e  lea     r8, [rsp+78h+var_58]
0x18001a083  mov     rdx, rbx
0x18001a086  mov     rcx, rdi
0x18001a089  mov     rax, [rax+118h]
0x18001a090  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a095  mov     rax, [rdi]
0x18001a098  lea     rdx, ??$LiteralObject@$2U?$BaseLiteralBuffer@$02U_LUTF8_STRING@@D@Details@RtlStringLiterals@@3E0FM@@0HF@@0A@@@@$0A@$00$01@Details@RtlStringLiterals@@3U_LUTF8_STRING@@B
0x18001a09f  mov     rcx, rdi
0x18001a0a2  xor     ebx, ebx
0x18001a0a4  mov     rax, [rax+0C8h]
0x18001a0ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a0b0  mov     rax, [rdi]
0x18001a0b3  movzx   edx, bp
0x18001a0b6  mov     rcx, rdi
0x18001a0b9  mov     rax, [rax+188h]
0x18001a0c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a0c5  inc     rsi
0x18001a0c8  cmp     rsi, r15
0x18001a0cb  jb      loc_18001A03E
0x18001a0d1  test    rbx, rbx
0x18001a0d4  jz      short loc_18001A0F0
0x18001a0d6  mov     rax, [rdi]
0x18001a0d9  lea     r8, [rsp+78h+var_58]
0x18001a0de  mov     rdx, rbx
0x18001a0e1  mov     rcx, rdi
0x18001a0e4  mov     rax, [rax+118h]
0x18001a0eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a0f0  mov     rcx, [rsp+78h+var_38]
0x18001a0f5  xor     rcx, rsp; StackCookie
0x18001a0f8  call    __security_check_cookie
0x18001a0fd  mov     rbx, [rsp+78h+arg_8]
0x18001a105  add     rsp, 50h
0x18001a109  pop     r15
0x18001a10b  pop     r14
0x18001a10d  pop     rdi
0x18001a10e  pop     rsi
0x18001a10f  pop     rbp
0x18001a110  retn
```
