# std::basic_filebuf<char,std::char_traits<char>>::xsgetn(char *,__int64)

- ea: `0x1400445c0`
- end: `0x1400446ea`
- name: `?xsgetn@?$basic_filebuf@DU?$char_traits@D@std@@@std@@MEAA_JPEAD_J@Z`
- size: `298`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x140010614`
- `0x1400200f0`
- `0x1400445c0`

## import_xrefs

- `msvcp_win!?xsgetn@?$basic_streambuf@DU?$char_traits@D@std@@@std@@MEAA_JPEAD_J@Z` at `0x140044608`
- `msvcp_win!?gbump@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXH@Z` at `0x140044653`
- `msvcp_win!?gbump@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXH@Z` at `0x140044653`
- `msvcp_win!?gptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ` at `0x140044631`
- `msvcp_win!?gptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ` at `0x140044631`
- `msvcp_win!?_Gnavail@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBA_JXZ` at `0x140044614`
- `msvcp_win!?_Gnavail@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBA_JXZ` at `0x140044614`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x140044695`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x1400446c5`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x140044695`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x1400446c5`

## pseudocode

```c
__int64 __fastcall std::filebuf::xsgetn(__int64 a1, char *a2, __int64 a3)
{
  unsigned __int64 v7; // rax
  size_t v8; // rdi
  const void *v9; // rax
  size_t v10; // rbx
  size_t v11; // rax

  if ( a3 <= 0 )
    return 0;
  if ( *(_QWORD *)(a1 + 104) )
    return std::streambuf::xsgetn();
  v7 = std::streambuf::_Gnavail();
  if ( v7 )
  {
    v8 = a3;
    if ( v7 < a3 )
      v8 = v7;
    v9 = (const void *)std::streambuf::gptr(a1);
    memcpy_0(a2, v9, v8);
    a2 += v8;
    v10 = a3 - v8;
    std::streambuf::gbump(a1, (unsigned int)v8);
  }
  else
  {
    v10 = a3;
  }
  if ( *(_QWORD *)(a1 + 128) )
  {
    std::filebuf::_Reset_back(a1);
    if ( v10 <= 0xFFF )
    {
LABEL_14:
      if ( v10 )
        v10 -= fread(a2, 1u, v10, *(FILE **)(a1 + 128));
    }
    else
    {
      while ( 1 )
      {
        v11 = fread(a2, 1u, 0xFFFu, *(FILE **)(a1 + 128));
        v10 -= v11;
        if ( v11 != 4095 )
          break;
        a2 += 4095;
        if ( v10 <= 0xFFF )
          goto LABEL_14;
      }
    }
  }
  return a3 - v10;
}

```

## disassembly

```asm
0x1400445c0  mov     [rsp+arg_10], rbp
0x1400445c5  mov     [rsp+arg_18], rsi
0x1400445ca  push    r14
0x1400445cc  sub     rsp, 20h
0x1400445d0  mov     rbp, r8
0x1400445d3  mov     rsi, rdx
0x1400445d6  mov     r14, rcx
0x1400445d9  test    r8, r8
0x1400445dc  jg      short loc_1400445F1
0x1400445de  xor     eax, eax
0x1400445e0  mov     rbp, [rsp+28h+arg_10]
0x1400445e5  mov     rsi, [rsp+28h+arg_18]
0x1400445ea  add     rsp, 20h
0x1400445ee  pop     r14
0x1400445f0  retn
0x1400445f1  cmp     qword ptr [rcx+68h], 0
0x1400445f6  jz      short loc_14004460F
0x1400445f8  mov     rbp, [rsp+28h+arg_10]
0x1400445fd  mov     rsi, [rsp+28h+arg_18]
0x140044602  add     rsp, 20h
0x140044606  pop     r14
0x140044608  jmp     cs:__imp_?xsgetn@?$basic_streambuf@DU?$char_traits@D@std@@@std@@MEAA_JPEAD_J@Z; std::streambuf::xsgetn(char *,__int64)
0x14004460f  mov     [rsp+28h+arg_0], rbx
0x140044614  call    cs:__imp_?_Gnavail@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBA_JXZ; std::streambuf::_Gnavail(void)
0x14004461a  test    rax, rax
0x14004461d  jz      short loc_140044660
0x14004461f  mov     [rsp+28h+arg_8], rdi
0x140044624  cmp     rax, rbp
0x140044627  mov     rdi, rbp
0x14004462a  mov     rcx, r14
0x14004462d  cmovb   rdi, rax
0x140044631  call    cs:__imp_?gptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ; std::streambuf::gptr(void)
0x140044637  mov     r8, rdi; Size
0x14004463a  mov     rcx, rsi; void *
0x14004463d  mov     rdx, rax; Src
0x140044640  call    memcpy_0
0x140044645  mov     rbx, rbp
0x140044648  add     rsi, rdi
0x14004464b  sub     rbx, rdi
0x14004464e  mov     edx, edi
0x140044650  mov     rcx, r14
0x140044653  call    cs:__imp_?gbump@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXH@Z; std::streambuf::gbump(int)
0x140044659  mov     rdi, [rsp+28h+arg_8]
0x14004465e  jmp     short loc_140044663
0x140044660  mov     rbx, rbp
0x140044663  cmp     qword ptr [r14+80h], 0
0x14004466b  jz      short loc_1400446CE
0x14004466d  mov     rcx, r14
0x140044670  call    ?_Reset_back@?$basic_filebuf@DU?$char_traits@D@std@@@std@@AEAAXXZ; std::filebuf::_Reset_back(void)
0x140044675  cmp     rbx, 0FFFh
0x14004467c  jbe     short loc_1400446AE
0x14004467e  xchg    ax, ax
0x140044680  mov     r9, [r14+80h]; Stream
0x140044687  mov     edx, 1; ElementSize
0x14004468c  mov     r8d, 0FFFh; ElementCount
0x140044692  mov     rcx, rsi; Buffer
0x140044695  call    cs:__imp_fread
0x14004469b  sub     rbx, rax
0x14004469e  cmp     rax, 0FFFh
0x1400446a4  jnz     short loc_1400446CE
0x1400446a6  add     rsi, rax
0x1400446a9  cmp     rbx, rax
0x1400446ac  ja      short loc_140044680
0x1400446ae  test    rbx, rbx
0x1400446b1  jz      short loc_1400446CE
0x1400446b3  mov     r9, [r14+80h]; Stream
0x1400446ba  mov     r8, rbx; ElementCount
0x1400446bd  mov     edx, 1; ElementSize
0x1400446c2  mov     rcx, rsi; Buffer
0x1400446c5  call    cs:__imp_fread
0x1400446cb  sub     rbx, rax
0x1400446ce  mov     rsi, [rsp+28h+arg_18]
0x1400446d3  sub     rbp, rbx
0x1400446d6  mov     rbx, [rsp+28h+arg_0]
0x1400446db  mov     rax, rbp
0x1400446de  mov     rbp, [rsp+28h+arg_10]
0x1400446e3  add     rsp, 20h
0x1400446e7  pop     r14
0x1400446e9  retn
```
