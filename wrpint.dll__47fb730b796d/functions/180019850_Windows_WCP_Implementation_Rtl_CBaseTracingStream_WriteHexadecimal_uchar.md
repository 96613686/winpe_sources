# Windows::WCP::Implementation::Rtl::CBaseTracingStream::WriteHexadecimal(uchar)

- ea: `0x180019850`
- end: `0x1800198bc`
- name: `?WriteHexadecimal@CBaseTracingStream@Rtl@Implementation@WCP@Windows@@UEAAXE@Z`
- size: `108`
- prototype: `void __fastcall(Windows::WCP::Implementation::Rtl::CBaseTracingStream *__hidden this, unsigned __int8)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180019850`
- `0x18001b7b0`
- `0x18001c010`

## import_xrefs

- `msvcrt!_snprintf_s` at `0x180019883`
- `msvcrt!_snprintf_s` at `0x180019883`

## pseudocode

```c
void __fastcall Windows::WCP::Implementation::Rtl::CBaseTracingStream::WriteHexadecimal(
        Windows::WCP::Implementation::Rtl::CBaseTracingStream *this,
        unsigned __int8 a2)
{
  unsigned __int64 v3; // rdx
  char Buffer[8]; // [rsp+30h] [rbp-18h] BYREF

  v3 = _snprintf_s(Buffer, 3u, 0xFFFFFFFFFFFFFFFFuLL, "%02x", a2);
  if ( v3 <= 3 )
    (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, unsigned __int64, char *))(*(_QWORD *)this + 280LL))(
      this,
      v3,
      Buffer);
}

```

## disassembly

```asm
0x180019850  push    rbx
0x180019852  sub     rsp, 40h
0x180019856  mov     rax, cs:__security_cookie
0x18001985d  xor     rax, rsp
0x180019860  mov     [rsp+48h+var_10], rax
0x180019865  movzx   eax, dl
0x180019868  lea     r9, a02x; "%02x"
0x18001986f  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x180019873  mov     [rsp+48h+var_28], eax
0x180019877  mov     rbx, rcx
0x18001987a  lea     rcx, [rsp+48h+Buffer]; Buffer
0x18001987f  lea     edx, [r8+4]; BufferCount
0x180019883  call    cs:__imp__snprintf_s
0x180019889  movsxd  rdx, eax
0x18001988c  cmp     rdx, 3
0x180019890  ja      short loc_1800198A9
0x180019892  mov     rax, [rbx]
0x180019895  lea     r8, [rsp+48h+Buffer]
0x18001989a  mov     rcx, rbx
0x18001989d  mov     rax, [rax+118h]
0x1800198a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800198a9  mov     rcx, [rsp+48h+var_10]
0x1800198ae  xor     rcx, rsp; StackCookie
0x1800198b1  call    __security_check_cookie
0x1800198b6  add     rsp, 40h
0x1800198ba  pop     rbx
0x1800198bb  retn
```
