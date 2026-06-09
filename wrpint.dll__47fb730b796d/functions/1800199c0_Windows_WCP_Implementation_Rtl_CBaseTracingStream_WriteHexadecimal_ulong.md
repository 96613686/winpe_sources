# Windows::WCP::Implementation::Rtl::CBaseTracingStream::WriteHexadecimal(ulong)

- ea: `0x1800199c0`
- end: `0x180019a29`
- name: `?WriteHexadecimal@CBaseTracingStream@Rtl@Implementation@WCP@Windows@@UEAAXK@Z`
- size: `105`
- prototype: `void __fastcall(Windows::WCP::Implementation::Rtl::CBaseTracingStream *this, int)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800199c0`
- `0x18001b7b0`
- `0x18001c010`

## import_xrefs

- `msvcrt!_snprintf_s` at `0x1800199f0`
- `msvcrt!_snprintf_s` at `0x1800199f0`

## pseudocode

```c
void __fastcall Windows::WCP::Implementation::Rtl::CBaseTracingStream::WriteHexadecimal(
        Windows::WCP::Implementation::Rtl::CBaseTracingStream *this,
        int a2)
{
  unsigned __int64 v3; // rdx
  char Buffer[16]; // [rsp+30h] [rbp-28h] BYREF

  v3 = _snprintf_s(Buffer, 9u, 0xFFFFFFFFFFFFFFFFuLL, "%08lx", a2);
  if ( v3 <= 9 )
    (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, unsigned __int64, char *))(*(_QWORD *)this + 280LL))(
      this,
      v3,
      Buffer);
}

```

## disassembly

```asm
0x1800199c0  push    rbx
0x1800199c2  sub     rsp, 50h
0x1800199c6  mov     rax, cs:__security_cookie
0x1800199cd  xor     rax, rsp
0x1800199d0  mov     [rsp+58h+var_18], rax
0x1800199d5  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x1800199d9  mov     [rsp+58h+var_38], edx
0x1800199dd  mov     rbx, rcx
0x1800199e0  lea     r9, a08lx; "%08lx"
0x1800199e7  lea     rcx, [rsp+58h+Buffer]; Buffer
0x1800199ec  lea     edx, [r8+0Ah]; BufferCount
0x1800199f0  call    cs:__imp__snprintf_s
0x1800199f6  movsxd  rdx, eax
0x1800199f9  cmp     rdx, 9
0x1800199fd  ja      short loc_180019A16
0x1800199ff  mov     rax, [rbx]
0x180019a02  lea     r8, [rsp+58h+Buffer]
0x180019a07  mov     rcx, rbx
0x180019a0a  mov     rax, [rax+118h]
0x180019a11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019a16  mov     rcx, [rsp+58h+var_18]
0x180019a1b  xor     rcx, rsp; StackCookie
0x180019a1e  call    __security_check_cookie
0x180019a23  add     rsp, 50h
0x180019a27  pop     rbx
0x180019a28  retn
```
