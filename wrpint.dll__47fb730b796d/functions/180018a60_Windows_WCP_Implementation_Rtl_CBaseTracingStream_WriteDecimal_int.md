# Windows::WCP::Implementation::Rtl::CBaseTracingStream::WriteDecimal(int)

- ea: `0x180018a60`
- end: `0x180018ac9`
- name: `?WriteDecimal@CBaseTracingStream@Rtl@Implementation@WCP@Windows@@UEAAXH@Z`
- size: `105`
- prototype: `void __fastcall(Windows::WCP::Implementation::Rtl::CBaseTracingStream *__hidden this, int)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180018a60`
- `0x18001b7b0`
- `0x18001c010`

## import_xrefs

- `msvcrt!_snprintf_s` at `0x180018a90`
- `msvcrt!_snprintf_s` at `0x180018a90`

## pseudocode

```c
void __fastcall Windows::WCP::Implementation::Rtl::CBaseTracingStream::WriteDecimal(
        Windows::WCP::Implementation::Rtl::CBaseTracingStream *this,
        int a2)
{
  unsigned __int64 v3; // rdx
  char Buffer[16]; // [rsp+30h] [rbp-28h] BYREF

  v3 = _snprintf_s(Buffer, 0xDu, 0xFFFFFFFFFFFFFFFFuLL, "%d", a2);
  if ( v3 <= 0xD )
    (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, unsigned __int64, char *))(*(_QWORD *)this + 280LL))(
      this,
      v3,
      Buffer);
}

```

## disassembly

```asm
0x180018a60  push    rbx
0x180018a62  sub     rsp, 50h
0x180018a66  mov     rax, cs:__security_cookie
0x180018a6d  xor     rax, rsp
0x180018a70  mov     [rsp+58h+var_18], rax
0x180018a75  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x180018a79  mov     [rsp+58h+var_38], edx
0x180018a7d  mov     rbx, rcx
0x180018a80  lea     r9, aD; "%d"
0x180018a87  lea     rcx, [rsp+58h+Buffer]; Buffer
0x180018a8c  lea     edx, [r8+0Eh]; BufferCount
0x180018a90  call    cs:__imp__snprintf_s
0x180018a96  movsxd  rdx, eax
0x180018a99  cmp     rdx, 0Dh
0x180018a9d  ja      short loc_180018AB6
0x180018a9f  mov     rax, [rbx]
0x180018aa2  lea     r8, [rsp+58h+Buffer]
0x180018aa7  mov     rcx, rbx
0x180018aaa  mov     rax, [rax+118h]
0x180018ab1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018ab6  mov     rcx, [rsp+58h+var_18]
0x180018abb  xor     rcx, rsp; StackCookie
0x180018abe  call    __security_check_cookie
0x180018ac3  add     rsp, 50h
0x180018ac7  pop     rbx
0x180018ac8  retn
```
