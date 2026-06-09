# Windows::WCP::Implementation::Rtl::CBaseTracingStream::WriteHexadecimalNZ(ulong)

- ea: `0x180019c10`
- end: `0x180019c79`
- name: `?WriteHexadecimalNZ@CBaseTracingStream@Rtl@Implementation@WCP@Windows@@UEAAXK@Z`
- size: `105`
- prototype: `void __fastcall(Windows::WCP::Implementation::Rtl::CBaseTracingStream *this, int)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180019c10`
- `0x18001b7b0`
- `0x18001c010`

## import_xrefs

- `msvcrt!_snprintf_s` at `0x180019c40`
- `msvcrt!_snprintf_s` at `0x180019c40`

## pseudocode

```c
void __fastcall Windows::WCP::Implementation::Rtl::CBaseTracingStream::WriteHexadecimalNZ(
        Windows::WCP::Implementation::Rtl::CBaseTracingStream *this,
        int a2)
{
  unsigned __int64 v3; // rdx
  char Buffer[16]; // [rsp+30h] [rbp-28h] BYREF

  v3 = _snprintf_s(Buffer, 9u, 0xFFFFFFFFFFFFFFFFuLL, "%lx", a2);
  if ( v3 <= 9 )
    (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, unsigned __int64, char *))(*(_QWORD *)this + 280LL))(
      this,
      v3,
      Buffer);
}

```

## disassembly

```asm
0x180019c10  push    rbx
0x180019c12  sub     rsp, 50h
0x180019c16  mov     rax, cs:__security_cookie
0x180019c1d  xor     rax, rsp
0x180019c20  mov     [rsp+58h+var_18], rax
0x180019c25  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x180019c29  mov     [rsp+58h+var_38], edx
0x180019c2d  mov     rbx, rcx
0x180019c30  lea     r9, aLx; "%lx"
0x180019c37  lea     rcx, [rsp+58h+Buffer]; Buffer
0x180019c3c  lea     edx, [r8+0Ah]; BufferCount
0x180019c40  call    cs:__imp__snprintf_s
0x180019c46  movsxd  rdx, eax
0x180019c49  cmp     rdx, 9
0x180019c4d  ja      short loc_180019C66
0x180019c4f  mov     rax, [rbx]
0x180019c52  lea     r8, [rsp+58h+Buffer]
0x180019c57  mov     rcx, rbx
0x180019c5a  mov     rax, [rax+118h]
0x180019c61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019c66  mov     rcx, [rsp+58h+var_18]
0x180019c6b  xor     rcx, rsp; StackCookie
0x180019c6e  call    __security_check_cookie
0x180019c73  add     rsp, 50h
0x180019c77  pop     rbx
0x180019c78  retn
```
