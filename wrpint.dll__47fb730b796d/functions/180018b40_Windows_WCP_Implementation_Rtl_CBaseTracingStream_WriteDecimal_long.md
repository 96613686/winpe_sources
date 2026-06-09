# Windows::WCP::Implementation::Rtl::CBaseTracingStream::WriteDecimal(long)

- ea: `0x180018b40`
- end: `0x180018ba9`
- name: `?WriteDecimal@CBaseTracingStream@Rtl@Implementation@WCP@Windows@@UEAAXJ@Z`
- size: `105`
- prototype: `void __fastcall(Windows::WCP::Implementation::Rtl::CBaseTracingStream *__hidden this, int)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180018b40`
- `0x18001b7b0`
- `0x18001c010`

## import_xrefs

- `msvcrt!_snprintf_s` at `0x180018b70`
- `msvcrt!_snprintf_s` at `0x180018b70`

## pseudocode

```c
void __fastcall Windows::WCP::Implementation::Rtl::CBaseTracingStream::WriteDecimal(
        Windows::WCP::Implementation::Rtl::CBaseTracingStream *this,
        int a2)
{
  unsigned __int64 v3; // rdx
  char Buffer[16]; // [rsp+30h] [rbp-28h] BYREF

  v3 = _snprintf_s(Buffer, 0xDu, 0xFFFFFFFFFFFFFFFFuLL, "%ld", a2);
  if ( v3 <= 0xD )
    (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, unsigned __int64, char *))(*(_QWORD *)this + 280LL))(
      this,
      v3,
      Buffer);
}

```

## disassembly

```asm
0x180018b40  push    rbx
0x180018b42  sub     rsp, 50h
0x180018b46  mov     rax, cs:__security_cookie
0x180018b4d  xor     rax, rsp
0x180018b50  mov     [rsp+58h+var_18], rax
0x180018b55  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x180018b59  mov     [rsp+58h+var_38], edx
0x180018b5d  mov     rbx, rcx
0x180018b60  lea     r9, aLd; "%ld"
0x180018b67  lea     rcx, [rsp+58h+Buffer]; Buffer
0x180018b6c  lea     edx, [r8+0Eh]; BufferCount
0x180018b70  call    cs:__imp__snprintf_s
0x180018b76  movsxd  rdx, eax
0x180018b79  cmp     rdx, 0Dh
0x180018b7d  ja      short loc_180018B96
0x180018b7f  mov     rax, [rbx]
0x180018b82  lea     r8, [rsp+58h+Buffer]
0x180018b87  mov     rcx, rbx
0x180018b8a  mov     rax, [rax+118h]
0x180018b91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018b96  mov     rcx, [rsp+58h+var_18]
0x180018b9b  xor     rcx, rsp; StackCookie
0x180018b9e  call    __security_check_cookie
0x180018ba3  add     rsp, 50h
0x180018ba7  pop     rbx
0x180018ba8  retn
```
