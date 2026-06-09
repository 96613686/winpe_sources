# Windows::WCP::Implementation::Rtl::CBaseTracingStream::WriteHexadecimalNZ(ushort)

- ea: `0x180019b20`
- end: `0x180019b8c`
- name: `?WriteHexadecimalNZ@CBaseTracingStream@Rtl@Implementation@WCP@Windows@@UEAAXG@Z`
- size: `108`
- prototype: `void __fastcall(Windows::WCP::Implementation::Rtl::CBaseTracingStream *__hidden this, unsigned __int16)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180019b20`
- `0x18001b7b0`
- `0x18001c010`

## import_xrefs

- `msvcrt!_snprintf_s` at `0x180019b53`
- `msvcrt!_snprintf_s` at `0x180019b53`

## pseudocode

```c
void __fastcall Windows::WCP::Implementation::Rtl::CBaseTracingStream::WriteHexadecimalNZ(
        Windows::WCP::Implementation::Rtl::CBaseTracingStream *this,
        unsigned __int16 a2)
{
  unsigned __int64 v3; // rdx
  char Buffer[8]; // [rsp+30h] [rbp-18h] BYREF

  v3 = _snprintf_s(Buffer, 5u, 0xFFFFFFFFFFFFFFFFuLL, "%x", a2);
  if ( v3 <= 5 )
    (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, unsigned __int64, char *))(*(_QWORD *)this + 280LL))(
      this,
      v3,
      Buffer);
}

```

## disassembly

```asm
0x180019b20  push    rbx
0x180019b22  sub     rsp, 40h
0x180019b26  mov     rax, cs:__security_cookie
0x180019b2d  xor     rax, rsp
0x180019b30  mov     [rsp+48h+var_10], rax
0x180019b35  movzx   eax, dx
0x180019b38  lea     r9, asc_180025B70; "%x"
0x180019b3f  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x180019b43  mov     [rsp+48h+var_28], eax
0x180019b47  mov     rbx, rcx
0x180019b4a  lea     rcx, [rsp+48h+Buffer]; Buffer
0x180019b4f  lea     edx, [r8+6]; BufferCount
0x180019b53  call    cs:__imp__snprintf_s
0x180019b59  movsxd  rdx, eax
0x180019b5c  cmp     rdx, 5
0x180019b60  ja      short loc_180019B79
0x180019b62  mov     rax, [rbx]
0x180019b65  lea     r8, [rsp+48h+Buffer]
0x180019b6a  mov     rcx, rbx
0x180019b6d  mov     rax, [rax+118h]
0x180019b74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019b79  mov     rcx, [rsp+48h+var_10]
0x180019b7e  xor     rcx, rsp; StackCookie
0x180019b81  call    __security_check_cookie
0x180019b86  add     rsp, 40h
0x180019b8a  pop     rbx
0x180019b8b  retn
```
