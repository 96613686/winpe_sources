# std::basic_filebuf<char,std::char_traits<char>>::xsputn(char const *,__int64)

- ea: `0x1400446f0`
- end: `0x1400447b9`
- name: `?xsputn@?$basic_filebuf@DU?$char_traits@D@std@@@std@@MEAA_JPEBD_J@Z`
- size: `201`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140010614`
- `0x1400446f0`

## import_xrefs

- `msvcp_win!?xsputn@?$basic_streambuf@DU?$char_traits@D@std@@@std@@MEAA_JPEBD_J@Z` at `0x14004471e`
- `msvcp_win!?pptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ` at `0x14004474f`
- `msvcp_win!?pptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ` at `0x14004474f`
- `msvcp_win!?pbump@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXH@Z` at `0x14004476b`
- `msvcp_win!?pbump@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXH@Z` at `0x14004476b`
- `msvcp_win!?_Pnavail@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBA_JXZ` at `0x140044732`
- `msvcp_win!?_Pnavail@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBA_JXZ` at `0x140044732`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x140044790`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x140044790`

## pseudocode

```c
__int64 __fastcall std::filebuf::xsputn(__int64 a1, char *a2, __int64 a3)
{
  __int64 v3; // rbx
  __int64 v8; // rax
  size_t v9; // rbp
  void *v10; // rax
  __int64 v11; // r9

  v3 = a3;
  if ( *(_QWORD *)(a1 + 104) )
    return std::streambuf::xsputn();
  v8 = std::streambuf::_Pnavail();
  v9 = v8;
  if ( v3 > 0 )
  {
    if ( v8 > 0 )
    {
      if ( v3 < v8 )
        v9 = v3;
      v10 = (void *)std::streambuf::pptr(a1);
      memcpy_0(v10, a2, v9);
      v3 -= v9;
      std::streambuf::pbump(a1, (unsigned int)v9);
      if ( v3 <= 0 )
        return a3 - v3;
      a2 += v9;
    }
    v11 = *(_QWORD *)(a1 + 128);
    if ( v11 )
      v3 -= _o_fwrite(a2, 1, v3, v11);
  }
  return a3 - v3;
}

```

## disassembly

```asm
0x1400446f0  mov     [rsp+arg_10], rbx
0x1400446f5  mov     [rsp+arg_18], rsi
0x1400446fa  push    rdi
0x1400446fb  sub     rsp, 20h
0x1400446ff  cmp     qword ptr [rcx+68h], 0
0x140044704  mov     rbx, r8
0x140044707  mov     rsi, rdx
0x14004470a  mov     rdi, rcx
0x14004470d  jz      short loc_140044725
0x14004470f  mov     rbx, [rsp+28h+arg_10]
0x140044714  mov     rsi, [rsp+28h+arg_18]
0x140044719  add     rsp, 20h
0x14004471d  pop     rdi
0x14004471e  jmp     cs:__imp_?xsputn@?$basic_streambuf@DU?$char_traits@D@std@@@std@@MEAA_JPEBD_J@Z; std::streambuf::xsputn(char const *,__int64)
0x140044725  mov     [rsp+28h+arg_0], rbp
0x14004472a  mov     [rsp+28h+arg_8], r14
0x14004472f  mov     r14, rbx
0x140044732  call    cs:__imp_?_Pnavail@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBA_JXZ; std::streambuf::_Pnavail(void)
0x140044738  mov     rbp, rax
0x14004473b  test    rbx, rbx
0x14004473e  jle     short loc_140044799
0x140044740  test    rax, rax
0x140044743  jle     short loc_140044779
0x140044745  cmp     rbx, rax
0x140044748  mov     rcx, rdi
0x14004474b  cmovl   rbp, rbx
0x14004474f  call    cs:__imp_?pptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ; std::streambuf::pptr(void)
0x140044755  mov     r8, rbp; Size
0x140044758  mov     rdx, rsi; Src
0x14004475b  mov     rcx, rax; void *
0x14004475e  call    memcpy_0
0x140044763  mov     edx, ebp
0x140044765  mov     rcx, rdi
0x140044768  sub     rbx, rbp
0x14004476b  call    cs:__imp_?pbump@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXH@Z; std::streambuf::pbump(int)
0x140044771  test    rbx, rbx
0x140044774  jle     short loc_140044799
0x140044776  add     rsi, rbp
0x140044779  mov     r9, [rdi+80h]
0x140044780  test    r9, r9
0x140044783  jz      short loc_140044799
0x140044785  mov     r8, rbx
0x140044788  mov     edx, 1
0x14004478d  mov     rcx, rsi
0x140044790  call    cs:__imp__o_fwrite
0x140044796  sub     rbx, rax
0x140044799  mov     rbp, [rsp+28h+arg_0]
0x14004479e  sub     r14, rbx
0x1400447a1  mov     rbx, [rsp+28h+arg_10]
0x1400447a6  mov     rax, r14
0x1400447a9  mov     r14, [rsp+28h+arg_8]
0x1400447ae  mov     rsi, [rsp+28h+arg_18]
0x1400447b3  add     rsp, 20h
0x1400447b7  pop     rdi
0x1400447b8  retn
```
