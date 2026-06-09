# UtilGetSystemDirectory2(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &,ushort,bool)

- ea: `0x180008dfc`
- end: `0x180008ec1`
- name: `?UtilGetSystemDirectory2@@YAJAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@G_N@Z`
- size: `197`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180008ec8`

## callees

- `0x180003fe4`
- `0x180008dfc`
- `0x1800093bc`
- `0x1800096d0`
- `0x18000977c`
- `0x18000979c`
- `0x180016c50`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180008e93`
- `KERNEL32!GetLastError` at `0x180008e93`
- `KERNEL32!GetSystemDirectoryW` at `0x180008e28`
- `KERNEL32!GetSystemDirectoryW` at `0x180008e28`

## pseudocode

```c
__int64 __fastcall UtilGetSystemDirectory2(__int64 a1)
{
  __int64 v2; // rbx
  unsigned __int64 v3; // rax
  unsigned __int64 v4; // rdx
  DWORD LastError; // eax
  WCHAR Buffer[64]; // [rsp+20h] [rbp-98h] BYREF

  if ( GetSystemDirectoryW(Buffer, 0x40u) - 1 > 0x3F )
  {
    LastError = GetLastError();
    return ERROR_HR_FROM_WIN32(LastError);
  }
  else
  {
    v2 = -1;
    do
      ++v2;
    while ( Buffer[v2] );
    v3 = utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::capacity(
           a1,
           v2 + 1);
    if ( v4 > v3 )
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Grow();
    if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                            a1,
                            Buffer) )
      return (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::push_back(
                                a1,
                                92) == 0
           ? 0x8007000E
           : 0;
    else
      return 2147942414LL;
  }
}

```

## disassembly

```asm
0x180008dfc  mov     [rsp+arg_8], rbx
0x180008e01  push    rdi
0x180008e02  sub     rsp, 0B0h
0x180008e09  mov     rax, cs:__security_cookie
0x180008e10  xor     rax, rsp
0x180008e13  mov     [rsp+0B8h+var_18], rax
0x180008e1b  mov     rdi, rcx
0x180008e1e  mov     edx, 40h ; '@'; uSize
0x180008e23  lea     rcx, [rsp+0B8h+Buffer]; lpBuffer
0x180008e28  call    cs:__imp_GetSystemDirectoryW
0x180008e2e  dec     eax
0x180008e30  cmp     eax, 3Fh ; '?'
0x180008e33  ja      short loc_180008E93
0x180008e35  lea     rax, [rsp+0B8h+Buffer]
0x180008e3a  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180008e3e  inc     rbx
0x180008e41  cmp     word ptr [rax+rbx*2], 0
0x180008e46  jnz     short loc_180008E3E
0x180008e48  mov     rcx, rdi
0x180008e4b  lea     rdx, [rbx+1]
0x180008e4f  call    ?capacity@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEBA_KXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::capacity(void)
0x180008e54  cmp     rdx, rax
0x180008e57  jbe     short loc_180008E5E
0x180008e59  call    ?_Grow@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAA_N_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Grow(unsigned __int64)
0x180008e5e  mov     r8, rbx
0x180008e61  lea     rdx, [rsp+0B8h+Buffer]
0x180008e66  mov     rcx, rdi
0x180008e69  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x180008e6e  test    al, al
0x180008e70  jz      short loc_180008E8C
0x180008e72  mov     edx, 5Ch ; '\'
0x180008e77  mov     rcx, rdi
0x180008e7a  call    ?push_back@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::push_back(ushort)
0x180008e7f  neg     al
0x180008e81  sbb     eax, eax
0x180008e83  not     eax
0x180008e85  and     eax, 8007000Eh
0x180008e8a  jmp     short loc_180008EA0
0x180008e8c  mov     eax, 8007000Eh
0x180008e91  jmp     short loc_180008EA0
0x180008e93  call    cs:__imp_GetLastError
0x180008e99  mov     ecx, eax; unsigned int
0x180008e9b  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180008ea0  mov     rcx, [rsp+0B8h+var_18]
0x180008ea8  xor     rcx, rsp; StackCookie
0x180008eab  call    __security_check_cookie
0x180008eb0  mov     rbx, [rsp+0B8h+arg_8]
0x180008eb8  add     rsp, 0B0h
0x180008ebf  pop     rdi
0x180008ec0  retn
```
