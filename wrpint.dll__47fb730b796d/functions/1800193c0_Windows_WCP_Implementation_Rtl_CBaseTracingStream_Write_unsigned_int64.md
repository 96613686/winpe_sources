# Windows::WCP::Implementation::Rtl::CBaseTracingStream::Write(unsigned __int64)

- ea: `0x1800193c0`
- end: `0x18001942a`
- name: `?Write@CBaseTracingStream@Rtl@Implementation@WCP@Windows@@UEAAX_K@Z`
- size: `106`
- prototype: `void __fastcall(Windows::WCP::Implementation::Rtl::CBaseTracingStream *this, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800193c0`
- `0x18001b7b0`
- `0x18001c010`

## import_xrefs

- `msvcrt!_snprintf_s` at `0x1800193f1`
- `msvcrt!_snprintf_s` at `0x1800193f1`

## pseudocode

```c
void __fastcall Windows::WCP::Implementation::Rtl::CBaseTracingStream::Write(
        Windows::WCP::Implementation::Rtl::CBaseTracingStream *this,
        __int64 a2)
{
  unsigned __int64 v3; // rdx
  char Buffer[24]; // [rsp+30h] [rbp-28h] BYREF

  v3 = _snprintf_s(Buffer, 0x18u, 0xFFFFFFFFFFFFFFFFuLL, "%I64u", a2);
  if ( v3 <= 0x18 )
    (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, unsigned __int64, char *))(*(_QWORD *)this + 280LL))(
      this,
      v3,
      Buffer);
}

```

## disassembly

```asm
0x1800193c0  push    rbx
0x1800193c2  sub     rsp, 50h
0x1800193c6  mov     rax, cs:__security_cookie
0x1800193cd  xor     rax, rsp
0x1800193d0  mov     [rsp+58h+var_10], rax
0x1800193d5  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x1800193d9  mov     [rsp+58h+var_38], rdx
0x1800193de  mov     rbx, rcx
0x1800193e1  lea     r9, aI64u; "%I64u"
0x1800193e8  lea     rcx, [rsp+58h+Buffer]; Buffer
0x1800193ed  lea     edx, [r8+19h]; BufferCount
0x1800193f1  call    cs:__imp__snprintf_s
0x1800193f7  movsxd  rdx, eax
0x1800193fa  cmp     rdx, 18h
0x1800193fe  ja      short loc_180019417
0x180019400  mov     rax, [rbx]
0x180019403  lea     r8, [rsp+58h+Buffer]
0x180019408  mov     rcx, rbx
0x18001940b  mov     rax, [rax+118h]
0x180019412  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019417  mov     rcx, [rsp+58h+var_10]
0x18001941c  xor     rcx, rsp; StackCookie
0x18001941f  call    __security_check_cookie
0x180019424  add     rsp, 50h
0x180019428  pop     rbx
0x180019429  retn
```
