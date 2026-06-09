# Windows::WCP::Implementation::Rtl::CBaseTracingStream::WriteHexadecimal(uint)

- ea: `0x180019950`
- end: `0x1800199b9`
- name: `?WriteHexadecimal@CBaseTracingStream@Rtl@Implementation@WCP@Windows@@UEAAXI@Z`
- size: `105`
- prototype: `void __fastcall(Windows::WCP::Implementation::Rtl::CBaseTracingStream *this, int)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180019950`
- `0x18001b7b0`
- `0x18001c010`

## import_xrefs

- `msvcrt!_snprintf_s` at `0x180019980`
- `msvcrt!_snprintf_s` at `0x180019980`

## pseudocode

```c
void __fastcall Windows::WCP::Implementation::Rtl::CBaseTracingStream::WriteHexadecimal(
        Windows::WCP::Implementation::Rtl::CBaseTracingStream *this,
        int a2)
{
  unsigned __int64 v3; // rdx
  char Buffer[16]; // [rsp+30h] [rbp-28h] BYREF

  v3 = _snprintf_s(Buffer, 9u, 0xFFFFFFFFFFFFFFFFuLL, "%08x", a2);
  if ( v3 <= 9 )
    (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, unsigned __int64, char *))(*(_QWORD *)this + 280LL))(
      this,
      v3,
      Buffer);
}

```

## disassembly

```asm
0x180019950  push    rbx
0x180019952  sub     rsp, 50h
0x180019956  mov     rax, cs:__security_cookie
0x18001995d  xor     rax, rsp
0x180019960  mov     [rsp+58h+var_18], rax
0x180019965  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x180019969  mov     [rsp+58h+var_38], edx
0x18001996d  mov     rbx, rcx
0x180019970  lea     r9, a08x; "%08x"
0x180019977  lea     rcx, [rsp+58h+Buffer]; Buffer
0x18001997c  lea     edx, [r8+0Ah]; BufferCount
0x180019980  call    cs:__imp__snprintf_s
0x180019986  movsxd  rdx, eax
0x180019989  cmp     rdx, 9
0x18001998d  ja      short loc_1800199A6
0x18001998f  mov     rax, [rbx]
0x180019992  lea     r8, [rsp+58h+Buffer]
0x180019997  mov     rcx, rbx
0x18001999a  mov     rax, [rax+118h]
0x1800199a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800199a6  mov     rcx, [rsp+58h+var_18]
0x1800199ab  xor     rcx, rsp; StackCookie
0x1800199ae  call    __security_check_cookie
0x1800199b3  add     rsp, 50h
0x1800199b7  pop     rbx
0x1800199b8  retn
```
