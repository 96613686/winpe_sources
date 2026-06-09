# Windows::WCP::Implementation::Rtl::CBaseTracingStream::Write(char)

- ea: `0x180018860`
- end: `0x1800188cc`
- name: `?Write@CBaseTracingStream@Rtl@Implementation@WCP@Windows@@UEAAXD@Z`
- size: `108`
- prototype: `void __fastcall(Windows::WCP::Implementation::Rtl::CBaseTracingStream *__hidden this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180018860`
- `0x18001b7b0`
- `0x18001c010`

## import_xrefs

- `msvcrt!_snprintf_s` at `0x180018893`
- `msvcrt!_snprintf_s` at `0x180018893`

## pseudocode

```c
void __fastcall Windows::WCP::Implementation::Rtl::CBaseTracingStream::Write(
        Windows::WCP::Implementation::Rtl::CBaseTracingStream *this,
        char a2)
{
  unsigned __int64 v3; // rdx
  char Buffer[8]; // [rsp+30h] [rbp-18h] BYREF

  v3 = _snprintf_s(Buffer, 5u, 0xFFFFFFFFFFFFFFFFuLL, "%d", a2);
  if ( v3 <= 5 )
    (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, unsigned __int64, char *))(*(_QWORD *)this + 280LL))(
      this,
      v3,
      Buffer);
}

```

## disassembly

```asm
0x180018860  push    rbx
0x180018862  sub     rsp, 40h
0x180018866  mov     rax, cs:__security_cookie
0x18001886d  xor     rax, rsp
0x180018870  mov     [rsp+48h+var_10], rax
0x180018875  movsx   eax, dl
0x180018878  lea     r9, aD; "%d"
0x18001887f  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x180018883  mov     [rsp+48h+var_28], eax
0x180018887  mov     rbx, rcx
0x18001888a  lea     rcx, [rsp+48h+Buffer]; Buffer
0x18001888f  lea     edx, [r8+6]; BufferCount
0x180018893  call    cs:__imp__snprintf_s
0x180018899  movsxd  rdx, eax
0x18001889c  cmp     rdx, 5
0x1800188a0  ja      short loc_1800188B9
0x1800188a2  mov     rax, [rbx]
0x1800188a5  lea     r8, [rsp+48h+Buffer]
0x1800188aa  mov     rcx, rbx
0x1800188ad  mov     rax, [rax+118h]
0x1800188b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800188b9  mov     rcx, [rsp+48h+var_10]
0x1800188be  xor     rcx, rsp; StackCookie
0x1800188c1  call    __security_check_cookie
0x1800188c6  add     rsp, 40h
0x1800188ca  pop     rbx
0x1800188cb  retn
```
