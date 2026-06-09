# _RNvXs5_NtNtCs9MWeMO1rkJG_4core3num5errorNtB5_15TryFromIntErrorNtNtB9_3fmt5Debug3fmt.llvm.7541658972310832757

- ea: `0x14000fb30`
- end: `0x14000fb98`
- name: `_RNvXs5_NtNtCs9MWeMO1rkJG_4core3num5errorNtB5_15TryFromIntErrorNtNtB9_3fmt5Debug3fmt.llvm.7541658972310832757`
- size: `104`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140005d80`
- `0x14000fb30`
- `0x140017a10`

## string_xrefs

- `0x14000fb57`: `TryFromIntErrorgdi_rust\src\region\from_path.rs`

## pseudocode

```c
__int64 __fastcall RNvXs5_NtNtCs9MWeMO1rkJG_4core3num5errorNtB5_15TryFromIntErrorNtNtB9_3fmt5Debug3fmt_llvm_7541658972310832757(
        __int64 a1,
        int a2)
{
  __int64 result; // rax
  __int64 v3; // [rsp+0h] [rbp-38h] BYREF
  _QWORD v4[2]; // [rsp+28h] [rbp-10h] BYREF

  v4[0] = a1;
  result = RNvMsa_NtCs9MWeMO1rkJG_4core3fmtNtB5_9Formatter25debug_tuple_field1_finish(
             a2,
             (unsigned int)"TryFromIntErrorgdi_rust\\src\\region\\from_path.rs",
             15,
             (unsigned int)v4,
             (__int64)&qword_14001BA88);
  if ( _security_cookie != ((unsigned __int64)&v3 ^ v4[1]) )
    JUMPOUT(0x14000FB97LL);
  return result;
}

```

## disassembly

```asm
0x14000fb30  sub     rsp, 38h
0x14000fb34  mov     rax, rdx
0x14000fb37  mov     rdx, cs:__security_cookie
0x14000fb3e  xor     rdx, rsp
0x14000fb41  mov     [rsp+38h+var_8], rdx
0x14000fb46  mov     [rsp+38h+var_10], rcx
0x14000fb4b  lea     rcx, qword_14001BA88
0x14000fb52  mov     [rsp+38h+var_18], rcx
0x14000fb57  lea     rdx, aTryfrominterro; "TryFromIntErrorgdi_rust\\src\\region\\f"...
0x14000fb5e  lea     r9, [rsp+38h+var_10]
0x14000fb63  mov     r8d, 0Fh
0x14000fb69  mov     rcx, rax
0x14000fb6c  call    _RNvMsa_NtCs9MWeMO1rkJG_4core3fmtNtB5_9Formatter25debug_tuple_field1_finish
0x14000fb71  mov     rcx, [rsp+38h+var_8]
0x14000fb76  xor     rcx, rsp
0x14000fb79  mov     rdx, cs:__security_cookie
0x14000fb80  cmp     rdx, rcx
0x14000fb83  jnz     short loc_14000FB8A
0x14000fb85  add     rsp, 38h
0x14000fb89  retn
0x14000fb8a  mov     rcx, [rsp+38h+var_8]
0x14000fb8f  xor     rcx, rsp; StackCookie
0x14000fb92  call    __security_check_cookie
```
