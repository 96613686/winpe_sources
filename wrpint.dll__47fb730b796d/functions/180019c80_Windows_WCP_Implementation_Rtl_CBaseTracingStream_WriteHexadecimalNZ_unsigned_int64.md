# Windows::WCP::Implementation::Rtl::CBaseTracingStream::WriteHexadecimalNZ(unsigned __int64)

- ea: `0x180019c80`
- end: `0x180019cea`
- name: `?WriteHexadecimalNZ@CBaseTracingStream@Rtl@Implementation@WCP@Windows@@UEAAX_K@Z`
- size: `106`
- prototype: `void __fastcall(Windows::WCP::Implementation::Rtl::CBaseTracingStream *this, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180019c80`
- `0x18001b7b0`
- `0x18001c010`

## import_xrefs

- `msvcrt!_snprintf_s` at `0x180019cb1`
- `msvcrt!_snprintf_s` at `0x180019cb1`

## pseudocode

```c
void __fastcall Windows::WCP::Implementation::Rtl::CBaseTracingStream::WriteHexadecimalNZ(
        Windows::WCP::Implementation::Rtl::CBaseTracingStream *this,
        __int64 a2)
{
  unsigned __int64 v3; // rdx
  char Buffer[24]; // [rsp+30h] [rbp-28h] BYREF

  v3 = _snprintf_s(Buffer, 0x11u, 0xFFFFFFFFFFFFFFFFuLL, "%I64x", a2);
  if ( v3 <= 0x11 )
    (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, unsigned __int64, char *))(*(_QWORD *)this + 280LL))(
      this,
      v3,
      Buffer);
}

```

## disassembly

```asm
0x180019c80  push    rbx
0x180019c82  sub     rsp, 50h
0x180019c86  mov     rax, cs:__security_cookie
0x180019c8d  xor     rax, rsp
0x180019c90  mov     [rsp+58h+var_10], rax
0x180019c95  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x180019c99  mov     [rsp+58h+var_38], rdx
0x180019c9e  mov     rbx, rcx
0x180019ca1  lea     r9, aI64x; "%I64x"
0x180019ca8  lea     rcx, [rsp+58h+Buffer]; Buffer
0x180019cad  lea     edx, [r8+12h]; BufferCount
0x180019cb1  call    cs:__imp__snprintf_s
0x180019cb7  movsxd  rdx, eax
0x180019cba  cmp     rdx, 11h
0x180019cbe  ja      short loc_180019CD7
0x180019cc0  mov     rax, [rbx]
0x180019cc3  lea     r8, [rsp+58h+Buffer]
0x180019cc8  mov     rcx, rbx
0x180019ccb  mov     rax, [rax+118h]
0x180019cd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019cd7  mov     rcx, [rsp+58h+var_10]
0x180019cdc  xor     rcx, rsp; StackCookie
0x180019cdf  call    __security_check_cookie
0x180019ce4  add     rsp, 50h
0x180019ce8  pop     rbx
0x180019ce9  retn
```
