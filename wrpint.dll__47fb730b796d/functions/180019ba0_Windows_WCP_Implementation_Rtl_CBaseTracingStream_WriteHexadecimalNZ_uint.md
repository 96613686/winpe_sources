# Windows::WCP::Implementation::Rtl::CBaseTracingStream::WriteHexadecimalNZ(uint)

- ea: `0x180019ba0`
- end: `0x180019c09`
- name: `?WriteHexadecimalNZ@CBaseTracingStream@Rtl@Implementation@WCP@Windows@@UEAAXI@Z`
- size: `105`
- prototype: `void __fastcall(Windows::WCP::Implementation::Rtl::CBaseTracingStream *this, int)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180019ba0`
- `0x18001b7b0`
- `0x18001c010`

## import_xrefs

- `msvcrt!_snprintf_s` at `0x180019bd0`
- `msvcrt!_snprintf_s` at `0x180019bd0`

## pseudocode

```c
void __fastcall Windows::WCP::Implementation::Rtl::CBaseTracingStream::WriteHexadecimalNZ(
        Windows::WCP::Implementation::Rtl::CBaseTracingStream *this,
        int a2)
{
  unsigned __int64 v3; // rdx
  char Buffer[16]; // [rsp+30h] [rbp-28h] BYREF

  v3 = _snprintf_s(Buffer, 9u, 0xFFFFFFFFFFFFFFFFuLL, "%x", a2);
  if ( v3 <= 9 )
    (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, unsigned __int64, char *))(*(_QWORD *)this + 280LL))(
      this,
      v3,
      Buffer);
}

```

## disassembly

```asm
0x180019ba0  push    rbx
0x180019ba2  sub     rsp, 50h
0x180019ba6  mov     rax, cs:__security_cookie
0x180019bad  xor     rax, rsp
0x180019bb0  mov     [rsp+58h+var_18], rax
0x180019bb5  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x180019bb9  mov     [rsp+58h+var_38], edx
0x180019bbd  mov     rbx, rcx
0x180019bc0  lea     r9, asc_180025B70; "%x"
0x180019bc7  lea     rcx, [rsp+58h+Buffer]; Buffer
0x180019bcc  lea     edx, [r8+0Ah]; BufferCount
0x180019bd0  call    cs:__imp__snprintf_s
0x180019bd6  movsxd  rdx, eax
0x180019bd9  cmp     rdx, 9
0x180019bdd  ja      short loc_180019BF6
0x180019bdf  mov     rax, [rbx]
0x180019be2  lea     r8, [rsp+58h+Buffer]
0x180019be7  mov     rcx, rbx
0x180019bea  mov     rax, [rax+118h]
0x180019bf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019bf6  mov     rcx, [rsp+58h+var_18]
0x180019bfb  xor     rcx, rsp; StackCookie
0x180019bfe  call    __security_check_cookie
0x180019c03  add     rsp, 50h
0x180019c07  pop     rbx
0x180019c08  retn
```
