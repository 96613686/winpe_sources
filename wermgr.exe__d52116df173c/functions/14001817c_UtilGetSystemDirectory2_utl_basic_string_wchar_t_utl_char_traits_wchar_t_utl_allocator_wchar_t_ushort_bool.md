# UtilGetSystemDirectory2(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,ushort,bool)

- ea: `0x14001817c`
- end: `0x140018250`
- name: `?UtilGetSystemDirectory2@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@G_N@Z`
- size: `212`
- prototype: `signed int __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14001852c`

## callees

- `0x140003200`
- `0x14000db44`
- `0x14000dc18`
- `0x14000e020`
- `0x14001817c`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1400181ad`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1400181ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001820f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001820f`

## pseudocode

```c
signed int __fastcall UtilGetSystemDirectory2(_QWORD *a1)
{
  unsigned __int64 v2; // rdi
  signed int result; // eax
  WCHAR Buffer[64]; // [rsp+20h] [rbp-98h] BYREF

  if ( GetSystemDirectoryW(Buffer, 0x40u) - 1 > 0x3F )
  {
    result = GetLastError();
    if ( result > 0 )
      result = (unsigned __int16)result | 0x80070000;
    if ( result >= 0 )
      return -2147467259;
  }
  else
  {
    v2 = -1;
    do
      ++v2;
    while ( Buffer[v2] );
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::reserve(a1, v2 + 1);
    if ( utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign((__int64)a1, Buffer, v2) )
      return utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(a1, 92) == 0
           ? 0x8007000E
           : 0;
    else
      return -2147024882;
  }
  return result;
}

```

## disassembly

```asm
0x14001817c  mov     [rsp+arg_8], rbx
0x140018181  mov     [rsp+arg_10], rsi
0x140018186  push    rdi
0x140018187  sub     rsp, 0B0h
0x14001818e  mov     rax, cs:__security_cookie
0x140018195  xor     rax, rsp
0x140018198  mov     [rsp+0B8h+var_18], rax
0x1400181a0  mov     rsi, rcx
0x1400181a3  mov     edx, 40h ; '@'; uSize
0x1400181a8  lea     rcx, [rsp+0B8h+Buffer]; lpBuffer
0x1400181ad  call    cs:__imp_GetSystemDirectoryW
0x1400181b3  dec     eax
0x1400181b5  cmp     eax, 3Fh ; '?'
0x1400181b8  ja      short loc_14001820F
0x1400181ba  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1400181be  lea     rax, [rsp+0B8h+Buffer]
0x1400181c3  xor     ebx, ebx
0x1400181c5  inc     rdi
0x1400181c8  cmp     [rax+rdi*2], bx
0x1400181cc  jnz     short loc_1400181C5
0x1400181ce  lea     rdx, [rdi+1]
0x1400181d2  mov     rcx, rsi
0x1400181d5  call    ?reserve@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::reserve(unsigned __int64)
0x1400181da  mov     r8, rdi
0x1400181dd  lea     rdx, [rsp+0B8h+Buffer]
0x1400181e2  mov     rcx, rsi
0x1400181e5  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x1400181ea  test    al, al
0x1400181ec  jz      short loc_140018208
0x1400181ee  mov     edx, 5Ch ; '\'
0x1400181f3  mov     rcx, rsi
0x1400181f6  call    ?push_back@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(wchar_t)
0x1400181fb  neg     al
0x1400181fd  sbb     eax, eax
0x1400181ff  not     eax
0x140018201  and     eax, 8007000Eh
0x140018206  jmp     short loc_14001822B
0x140018208  mov     eax, 8007000Eh
0x14001820d  jmp     short loc_14001822B
0x14001820f  call    cs:__imp_GetLastError
0x140018215  test    eax, eax
0x140018217  jle     short loc_140018221
0x140018219  movzx   eax, ax
0x14001821c  or      eax, 80070000h
0x140018221  test    eax, eax
0x140018223  mov     ecx, 80004005h
0x140018228  cmovns  eax, ecx
0x14001822b  mov     rcx, [rsp+0B8h+var_18]
0x140018233  xor     rcx, rsp; StackCookie
0x140018236  call    __security_check_cookie
0x14001823b  lea     r11, [rsp+0B8h+var_8]
0x140018243  mov     rbx, [r11+18h]
0x140018247  mov     rsi, [r11+20h]
0x14001824b  mov     rsp, r11
0x14001824e  pop     rdi
0x14001824f  retn
```
