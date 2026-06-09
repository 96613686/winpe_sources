# Windows::WCP::Implementation::Rtl::CBaseTracingStream::WriteHexadecimalNZ(uchar)

- ea: `0x180019aa0`
- end: `0x180019b0c`
- name: `?WriteHexadecimalNZ@CBaseTracingStream@Rtl@Implementation@WCP@Windows@@UEAAXE@Z`
- size: `108`
- prototype: `void __fastcall(Windows::WCP::Implementation::Rtl::CBaseTracingStream *__hidden this, unsigned __int8)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180019aa0`
- `0x18001b7b0`
- `0x18001c010`

## import_xrefs

- `msvcrt!_snprintf_s` at `0x180019ad3`
- `msvcrt!_snprintf_s` at `0x180019ad3`

## pseudocode

```c
void __fastcall Windows::WCP::Implementation::Rtl::CBaseTracingStream::WriteHexadecimalNZ(
        Windows::WCP::Implementation::Rtl::CBaseTracingStream *this,
        unsigned __int8 a2)
{
  unsigned __int64 v3; // rdx
  char Buffer[8]; // [rsp+30h] [rbp-18h] BYREF

  v3 = _snprintf_s(Buffer, 3u, 0xFFFFFFFFFFFFFFFFuLL, "%x", a2);
  if ( v3 <= 3 )
    (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, unsigned __int64, char *))(*(_QWORD *)this + 280LL))(
      this,
      v3,
      Buffer);
}

```

## disassembly

```asm
0x180019aa0  push    rbx
0x180019aa2  sub     rsp, 40h
0x180019aa6  mov     rax, cs:__security_cookie
0x180019aad  xor     rax, rsp
0x180019ab0  mov     [rsp+48h+var_10], rax
0x180019ab5  movzx   eax, dl
0x180019ab8  lea     r9, asc_180025B70; "%x"
0x180019abf  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x180019ac3  mov     [rsp+48h+var_28], eax
0x180019ac7  mov     rbx, rcx
0x180019aca  lea     rcx, [rsp+48h+Buffer]; Buffer
0x180019acf  lea     edx, [r8+4]; BufferCount
0x180019ad3  call    cs:__imp__snprintf_s
0x180019ad9  movsxd  rdx, eax
0x180019adc  cmp     rdx, 3
0x180019ae0  ja      short loc_180019AF9
0x180019ae2  mov     rax, [rbx]
0x180019ae5  lea     r8, [rsp+48h+Buffer]
0x180019aea  mov     rcx, rbx
0x180019aed  mov     rax, [rax+118h]
0x180019af4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019af9  mov     rcx, [rsp+48h+var_10]
0x180019afe  xor     rcx, rsp; StackCookie
0x180019b01  call    __security_check_cookie
0x180019b06  add     rsp, 40h
0x180019b0a  pop     rbx
0x180019b0b  retn
```
