# Windows::WCP::Implementation::Rtl::CBaseTracingStream::WriteHexadecimal(unsigned __int64)

- ea: `0x180019a30`
- end: `0x180019a9a`
- name: `?WriteHexadecimal@CBaseTracingStream@Rtl@Implementation@WCP@Windows@@UEAAX_K@Z`
- size: `106`
- prototype: `void __fastcall(Windows::WCP::Implementation::Rtl::CBaseTracingStream *this, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180019a30`
- `0x18001b7b0`
- `0x18001c010`

## import_xrefs

- `msvcrt!_snprintf_s` at `0x180019a61`
- `msvcrt!_snprintf_s` at `0x180019a61`

## pseudocode

```c
void __fastcall Windows::WCP::Implementation::Rtl::CBaseTracingStream::WriteHexadecimal(
        Windows::WCP::Implementation::Rtl::CBaseTracingStream *this,
        __int64 a2)
{
  unsigned __int64 v3; // rdx
  char Buffer[24]; // [rsp+30h] [rbp-28h] BYREF

  v3 = _snprintf_s(Buffer, 0x11u, 0xFFFFFFFFFFFFFFFFuLL, "%016I64x", a2);
  if ( v3 <= 0x11 )
    (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, unsigned __int64, char *))(*(_QWORD *)this + 280LL))(
      this,
      v3,
      Buffer);
}

```

## disassembly

```asm
0x180019a30  push    rbx
0x180019a32  sub     rsp, 50h
0x180019a36  mov     rax, cs:__security_cookie
0x180019a3d  xor     rax, rsp
0x180019a40  mov     [rsp+58h+var_10], rax
0x180019a45  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x180019a49  mov     [rsp+58h+var_38], rdx
0x180019a4e  mov     rbx, rcx
0x180019a51  lea     r9, a016i64x; "%016I64x"
0x180019a58  lea     rcx, [rsp+58h+Buffer]; Buffer
0x180019a5d  lea     edx, [r8+12h]; BufferCount
0x180019a61  call    cs:__imp__snprintf_s
0x180019a67  movsxd  rdx, eax
0x180019a6a  cmp     rdx, 11h
0x180019a6e  ja      short loc_180019A87
0x180019a70  mov     rax, [rbx]
0x180019a73  lea     r8, [rsp+58h+Buffer]
0x180019a78  mov     rcx, rbx
0x180019a7b  mov     rax, [rax+118h]
0x180019a82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019a87  mov     rcx, [rsp+58h+var_10]
0x180019a8c  xor     rcx, rsp; StackCookie
0x180019a8f  call    __security_check_cookie
0x180019a94  add     rsp, 50h
0x180019a98  pop     rbx
0x180019a99  retn
```
