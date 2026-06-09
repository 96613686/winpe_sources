# Windows::WCP::Implementation::Rtl::CBaseTracingStream::WriteDecimal(ulong)

- ea: `0x180018bb0`
- end: `0x180018c19`
- name: `?WriteDecimal@CBaseTracingStream@Rtl@Implementation@WCP@Windows@@UEAAXK@Z`
- size: `105`
- prototype: `void __fastcall(Windows::WCP::Implementation::Rtl::CBaseTracingStream *this, int)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180018bb0`
- `0x18001b7b0`
- `0x18001c010`

## import_xrefs

- `msvcrt!_snprintf_s` at `0x180018be0`
- `msvcrt!_snprintf_s` at `0x180018be0`

## pseudocode

```c
void __fastcall Windows::WCP::Implementation::Rtl::CBaseTracingStream::WriteDecimal(
        Windows::WCP::Implementation::Rtl::CBaseTracingStream *this,
        int a2)
{
  unsigned __int64 v3; // rdx
  char Buffer[16]; // [rsp+30h] [rbp-28h] BYREF

  v3 = _snprintf_s(Buffer, 0xDu, 0xFFFFFFFFFFFFFFFFuLL, "%lu", a2);
  if ( v3 <= 0xD )
    (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, unsigned __int64, char *))(*(_QWORD *)this + 280LL))(
      this,
      v3,
      Buffer);
}

```

## disassembly

```asm
0x180018bb0  push    rbx
0x180018bb2  sub     rsp, 50h
0x180018bb6  mov     rax, cs:__security_cookie
0x180018bbd  xor     rax, rsp
0x180018bc0  mov     [rsp+58h+var_18], rax
0x180018bc5  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x180018bc9  mov     [rsp+58h+var_38], edx
0x180018bcd  mov     rbx, rcx
0x180018bd0  lea     r9, aLu; "%lu"
0x180018bd7  lea     rcx, [rsp+58h+Buffer]; Buffer
0x180018bdc  lea     edx, [r8+0Eh]; BufferCount
0x180018be0  call    cs:__imp__snprintf_s
0x180018be6  movsxd  rdx, eax
0x180018be9  cmp     rdx, 0Dh
0x180018bed  ja      short loc_180018C06
0x180018bef  mov     rax, [rbx]
0x180018bf2  lea     r8, [rsp+58h+Buffer]
0x180018bf7  mov     rcx, rbx
0x180018bfa  mov     rax, [rax+118h]
0x180018c01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018c06  mov     rcx, [rsp+58h+var_18]
0x180018c0b  xor     rcx, rsp; StackCookie
0x180018c0e  call    __security_check_cookie
0x180018c13  add     rsp, 50h
0x180018c17  pop     rbx
0x180018c18  retn
```
