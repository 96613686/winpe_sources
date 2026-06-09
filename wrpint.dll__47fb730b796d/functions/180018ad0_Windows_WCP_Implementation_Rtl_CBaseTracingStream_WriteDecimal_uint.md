# Windows::WCP::Implementation::Rtl::CBaseTracingStream::WriteDecimal(uint)

- ea: `0x180018ad0`
- end: `0x180018b39`
- name: `?WriteDecimal@CBaseTracingStream@Rtl@Implementation@WCP@Windows@@UEAAXI@Z`
- size: `105`
- prototype: `void __fastcall(Windows::WCP::Implementation::Rtl::CBaseTracingStream *this, int)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180018ad0`
- `0x18001b7b0`
- `0x18001c010`

## import_xrefs

- `msvcrt!_snprintf_s` at `0x180018b00`
- `msvcrt!_snprintf_s` at `0x180018b00`

## pseudocode

```c
void __fastcall Windows::WCP::Implementation::Rtl::CBaseTracingStream::WriteDecimal(
        Windows::WCP::Implementation::Rtl::CBaseTracingStream *this,
        int a2)
{
  unsigned __int64 v3; // rdx
  char Buffer[16]; // [rsp+30h] [rbp-28h] BYREF

  v3 = _snprintf_s(Buffer, 0xDu, 0xFFFFFFFFFFFFFFFFuLL, "%u", a2);
  if ( v3 <= 0xD )
    (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, unsigned __int64, char *))(*(_QWORD *)this + 280LL))(
      this,
      v3,
      Buffer);
}

```

## disassembly

```asm
0x180018ad0  push    rbx
0x180018ad2  sub     rsp, 50h
0x180018ad6  mov     rax, cs:__security_cookie
0x180018add  xor     rax, rsp
0x180018ae0  mov     [rsp+58h+var_18], rax
0x180018ae5  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x180018ae9  mov     [rsp+58h+var_38], edx
0x180018aed  mov     rbx, rcx
0x180018af0  lea     r9, aU; "%u"
0x180018af7  lea     rcx, [rsp+58h+Buffer]; Buffer
0x180018afc  lea     edx, [r8+0Eh]; BufferCount
0x180018b00  call    cs:__imp__snprintf_s
0x180018b06  movsxd  rdx, eax
0x180018b09  cmp     rdx, 0Dh
0x180018b0d  ja      short loc_180018B26
0x180018b0f  mov     rax, [rbx]
0x180018b12  lea     r8, [rsp+58h+Buffer]
0x180018b17  mov     rcx, rbx
0x180018b1a  mov     rax, [rax+118h]
0x180018b21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018b26  mov     rcx, [rsp+58h+var_18]
0x180018b2b  xor     rcx, rsp; StackCookie
0x180018b2e  call    __security_check_cookie
0x180018b33  add     rsp, 50h
0x180018b37  pop     rbx
0x180018b38  retn
```
