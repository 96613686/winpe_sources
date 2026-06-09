# Windows::WCP::Implementation::Rtl::CBaseTracingStream::Write(uchar)

- ea: `0x1800188e0`
- end: `0x18001894c`
- name: `?Write@CBaseTracingStream@Rtl@Implementation@WCP@Windows@@UEAAXE@Z`
- size: `108`
- prototype: `void __fastcall(Windows::WCP::Implementation::Rtl::CBaseTracingStream *__hidden this, unsigned __int8)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800188e0`
- `0x18001b7b0`
- `0x18001c010`

## import_xrefs

- `msvcrt!_snprintf_s` at `0x180018913`
- `msvcrt!_snprintf_s` at `0x180018913`

## pseudocode

```c
void __fastcall Windows::WCP::Implementation::Rtl::CBaseTracingStream::Write(
        Windows::WCP::Implementation::Rtl::CBaseTracingStream *this,
        unsigned __int8 a2)
{
  unsigned __int64 v3; // rdx
  char Buffer[8]; // [rsp+30h] [rbp-18h] BYREF

  v3 = _snprintf_s(Buffer, 5u, 0xFFFFFFFFFFFFFFFFuLL, "%u", a2);
  if ( v3 <= 5 )
    (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, unsigned __int64, char *))(*(_QWORD *)this + 280LL))(
      this,
      v3,
      Buffer);
}

```

## disassembly

```asm
0x1800188e0  push    rbx
0x1800188e2  sub     rsp, 40h
0x1800188e6  mov     rax, cs:__security_cookie
0x1800188ed  xor     rax, rsp
0x1800188f0  mov     [rsp+48h+var_10], rax
0x1800188f5  movzx   eax, dl
0x1800188f8  lea     r9, aU; "%u"
0x1800188ff  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x180018903  mov     [rsp+48h+var_28], eax
0x180018907  mov     rbx, rcx
0x18001890a  lea     rcx, [rsp+48h+Buffer]; Buffer
0x18001890f  lea     edx, [r8+6]; BufferCount
0x180018913  call    cs:__imp__snprintf_s
0x180018919  movsxd  rdx, eax
0x18001891c  cmp     rdx, 5
0x180018920  ja      short loc_180018939
0x180018922  mov     rax, [rbx]
0x180018925  lea     r8, [rsp+48h+Buffer]
0x18001892a  mov     rcx, rbx
0x18001892d  mov     rax, [rax+118h]
0x180018934  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018939  mov     rcx, [rsp+48h+var_10]
0x18001893e  xor     rcx, rsp; StackCookie
0x180018941  call    __security_check_cookie
0x180018946  add     rsp, 40h
0x18001894a  pop     rbx
0x18001894b  retn
```
