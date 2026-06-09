# Windows::WCP::Implementation::Rtl::CBaseTracingStream::WriteHexadecimal(ushort)

- ea: `0x1800198d0`
- end: `0x18001993c`
- name: `?WriteHexadecimal@CBaseTracingStream@Rtl@Implementation@WCP@Windows@@UEAAXG@Z`
- size: `108`
- prototype: `void __fastcall(Windows::WCP::Implementation::Rtl::CBaseTracingStream *__hidden this, unsigned __int16)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800198d0`
- `0x18001b7b0`
- `0x18001c010`

## import_xrefs

- `msvcrt!_snprintf_s` at `0x180019903`
- `msvcrt!_snprintf_s` at `0x180019903`

## pseudocode

```c
void __fastcall Windows::WCP::Implementation::Rtl::CBaseTracingStream::WriteHexadecimal(
        Windows::WCP::Implementation::Rtl::CBaseTracingStream *this,
        unsigned __int16 a2)
{
  unsigned __int64 v3; // rdx
  char Buffer[8]; // [rsp+30h] [rbp-18h] BYREF

  v3 = _snprintf_s(Buffer, 5u, 0xFFFFFFFFFFFFFFFFuLL, "%04x", a2);
  if ( v3 <= 5 )
    (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, unsigned __int64, char *))(*(_QWORD *)this + 280LL))(
      this,
      v3,
      Buffer);
}

```

## disassembly

```asm
0x1800198d0  push    rbx
0x1800198d2  sub     rsp, 40h
0x1800198d6  mov     rax, cs:__security_cookie
0x1800198dd  xor     rax, rsp
0x1800198e0  mov     [rsp+48h+var_10], rax
0x1800198e5  movzx   eax, dx
0x1800198e8  lea     r9, a04x; "%04x"
0x1800198ef  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x1800198f3  mov     [rsp+48h+var_28], eax
0x1800198f7  mov     rbx, rcx
0x1800198fa  lea     rcx, [rsp+48h+Buffer]; Buffer
0x1800198ff  lea     edx, [r8+6]; BufferCount
0x180019903  call    cs:__imp__snprintf_s
0x180019909  movsxd  rdx, eax
0x18001990c  cmp     rdx, 5
0x180019910  ja      short loc_180019929
0x180019912  mov     rax, [rbx]
0x180019915  lea     r8, [rsp+48h+Buffer]
0x18001991a  mov     rcx, rbx
0x18001991d  mov     rax, [rax+118h]
0x180019924  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019929  mov     rcx, [rsp+48h+var_10]
0x18001992e  xor     rcx, rsp; StackCookie
0x180019931  call    __security_check_cookie
0x180019936  add     rsp, 40h
0x18001993a  pop     rbx
0x18001993b  retn
```
