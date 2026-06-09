# Windows::WCP::Implementation::Rtl::CBaseTracingStream::Write(__int64)

- ea: `0x180019350`
- end: `0x1800193ba`
- name: `?Write@CBaseTracingStream@Rtl@Implementation@WCP@Windows@@UEAAX_J@Z`
- size: `106`
- prototype: `void __fastcall(Windows::WCP::Implementation::Rtl::CBaseTracingStream *__hidden this, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180019350`
- `0x18001b7b0`
- `0x18001c010`

## import_xrefs

- `msvcrt!_snprintf_s` at `0x180019381`
- `msvcrt!_snprintf_s` at `0x180019381`

## pseudocode

```c
void __fastcall Windows::WCP::Implementation::Rtl::CBaseTracingStream::Write(
        Windows::WCP::Implementation::Rtl::CBaseTracingStream *this,
        __int64 a2)
{
  unsigned __int64 v3; // rdx
  char Buffer[24]; // [rsp+30h] [rbp-28h] BYREF

  v3 = _snprintf_s(Buffer, 0x18u, 0xFFFFFFFFFFFFFFFFuLL, "%I64d", a2);
  if ( v3 <= 0x18 )
    (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, unsigned __int64, char *))(*(_QWORD *)this + 280LL))(
      this,
      v3,
      Buffer);
}

```

## disassembly

```asm
0x180019350  push    rbx
0x180019352  sub     rsp, 50h
0x180019356  mov     rax, cs:__security_cookie
0x18001935d  xor     rax, rsp
0x180019360  mov     [rsp+58h+var_10], rax
0x180019365  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x180019369  mov     [rsp+58h+var_38], rdx
0x18001936e  mov     rbx, rcx
0x180019371  lea     r9, aI64d; "%I64d"
0x180019378  lea     rcx, [rsp+58h+Buffer]; Buffer
0x18001937d  lea     edx, [r8+19h]; BufferCount
0x180019381  call    cs:__imp__snprintf_s
0x180019387  movsxd  rdx, eax
0x18001938a  cmp     rdx, 18h
0x18001938e  ja      short loc_1800193A7
0x180019390  mov     rax, [rbx]
0x180019393  lea     r8, [rsp+58h+Buffer]
0x180019398  mov     rcx, rbx
0x18001939b  mov     rax, [rax+118h]
0x1800193a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800193a7  mov     rcx, [rsp+58h+var_10]
0x1800193ac  xor     rcx, rsp; StackCookie
0x1800193af  call    __security_check_cookie
0x1800193b4  add     rsp, 50h
0x1800193b8  pop     rbx
0x1800193b9  retn
```
