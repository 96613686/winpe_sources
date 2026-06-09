# RegionCore_fill_path_with_outline

- ea: `0x140004cf0`
- end: `0x140004d49`
- name: `RegionCore_fill_path_with_outline`
- size: `89`
- prototype: `bool __fastcall(__int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140003860`
- `0x140004cf0`
- `0x140017a10`

## pseudocode

```c
bool __fastcall RegionCore_fill_path_with_outline(__int64 a1, __int64 a2, __int64 a3)
{
  bool v3; // cl
  __int64 v5; // [rsp+0h] [rbp-38h] BYREF
  _QWORD v6[3]; // [rsp+20h] [rbp-18h] BYREF

  v6[0] = a2;
  v6[1] = a3;
  v3 = (unsigned int)RINvMNtCsdcpJtfrLhSH_7rgncore9fill_pathNtB5_10RegionCore30fill_path_with_outline_genericNtNtCs7vXzV21FY6F_8gdi_rust6region12EPATHOBJSinkEB1s_(
                       a1,
                       v6) == 0;
  if ( _security_cookie != ((unsigned __int64)&v5 ^ v6[2]) )
    JUMPOUT(0x140004D48LL);
  return v3;
}

```

## disassembly

```asm
0x140004cf0  sub     rsp, 38h
0x140004cf4  mov     rax, cs:__security_cookie
0x140004cfb  xor     rax, rsp
0x140004cfe  mov     [rsp+38h+var_8], rax
0x140004d03  mov     [rsp+38h+var_18], rdx
0x140004d08  mov     [rsp+38h+var_10], r8
0x140004d0d  lea     rdx, [rsp+38h+var_18]
0x140004d12  call    _RINvMNtCsdcpJtfrLhSH_7rgncore9fill_pathNtB5_10RegionCore30fill_path_with_outline_genericNtNtCs7vXzV21FY6F_8gdi_rust6region12EPATHOBJSinkEB1s_
0x140004d17  mov     ecx, eax
0x140004d19  xor     eax, eax
0x140004d1b  test    ecx, ecx
0x140004d1d  setz    cl
0x140004d20  mov     rdx, [rsp+38h+var_8]
0x140004d25  xor     rdx, rsp
0x140004d28  mov     r8, cs:__security_cookie
0x140004d2f  cmp     r8, rdx
0x140004d32  jnz     short loc_140004D3B
0x140004d34  mov     al, cl
0x140004d36  add     rsp, 38h
0x140004d3a  retn
0x140004d3b  mov     rcx, [rsp+38h+var_8]
0x140004d40  xor     rcx, rsp; StackCookie
0x140004d43  call    __security_check_cookie
```
