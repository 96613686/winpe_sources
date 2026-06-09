# Windows::WCP::Implementation::Rtl::CBaseTracingStream::Write(ushort)

- ea: `0x1800189e0`
- end: `0x180018a4c`
- name: `?Write@CBaseTracingStream@Rtl@Implementation@WCP@Windows@@UEAAXG@Z`
- size: `108`
- prototype: `void __fastcall(Windows::WCP::Implementation::Rtl::CBaseTracingStream *__hidden this, unsigned __int16)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800189e0`
- `0x18001b7b0`
- `0x18001c010`

## import_xrefs

- `msvcrt!_snprintf_s` at `0x180018a13`
- `msvcrt!_snprintf_s` at `0x180018a13`

## pseudocode

```c
void __fastcall Windows::WCP::Implementation::Rtl::CBaseTracingStream::Write(
        Windows::WCP::Implementation::Rtl::CBaseTracingStream *this,
        unsigned __int16 a2)
{
  unsigned __int64 v3; // rdx
  char Buffer[8]; // [rsp+30h] [rbp-18h] BYREF

  v3 = _snprintf_s(Buffer, 8u, 0xFFFFFFFFFFFFFFFFuLL, "%u", a2);
  if ( v3 <= 8 )
    (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, unsigned __int64, char *))(*(_QWORD *)this + 280LL))(
      this,
      v3,
      Buffer);
}

```

## disassembly

```asm
0x1800189e0  push    rbx
0x1800189e2  sub     rsp, 40h
0x1800189e6  mov     rax, cs:__security_cookie
0x1800189ed  xor     rax, rsp
0x1800189f0  mov     [rsp+48h+var_10], rax
0x1800189f5  movzx   eax, dx
0x1800189f8  lea     r9, aU; "%u"
0x1800189ff  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x180018a03  mov     [rsp+48h+var_28], eax
0x180018a07  mov     rbx, rcx
0x180018a0a  lea     rcx, [rsp+48h+Buffer]; Buffer
0x180018a0f  lea     edx, [r8+9]; BufferCount
0x180018a13  call    cs:__imp__snprintf_s
0x180018a19  movsxd  rdx, eax
0x180018a1c  cmp     rdx, 8
0x180018a20  ja      short loc_180018A39
0x180018a22  mov     rax, [rbx]
0x180018a25  lea     r8, [rsp+48h+Buffer]
0x180018a2a  mov     rcx, rbx
0x180018a2d  mov     rax, [rax+118h]
0x180018a34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018a39  mov     rcx, [rsp+48h+var_10]
0x180018a3e  xor     rcx, rsp; StackCookie
0x180018a41  call    __security_check_cookie
0x180018a46  add     rsp, 40h
0x180018a4a  pop     rbx
0x180018a4b  retn
```
