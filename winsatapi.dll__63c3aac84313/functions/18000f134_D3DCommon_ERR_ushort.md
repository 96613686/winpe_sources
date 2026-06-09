# D3DCommon::ERR(ushort,...)

- ea: `0x18000f134`
- end: `0x18000f2f9`
- name: `?ERR@D3DCommon@@YAXGZZ`
- size: `453`
- prototype: `void(D3DCommon *this, __int64, ...)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000f018`

## callees

- `0x180005370`
- `0x180005570`
- `0x18000b194`
- `0x18000e430`
- `0x18000e4dc`
- `0x18000e6ac`
- `0x18000f134`
- `0x18000f300`
- `0x18000f99c`
- `0x180029478`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000f28c`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000f295`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000f2b1`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000f2ba`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000f2e0`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000f2e9`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000f28c`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000f295`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000f2b1`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000f2ba`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000f2e0`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000f2e9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000f1d1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000f1d1`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void D3DCommon::ERR(D3DCommon *this, __int64 a2, ...)
{
  _QWORD *v2; // rax
  _QWORD *v3; // rax
  void *v4; // rax
  _QWORD *v5; // rbx
  _QWORD *v6; // rdi
  __int64 v7; // rax
  bool v8; // zf
  void *v9; // rcx
  void *v10; // rcx
  void *v11; // rbx
  void *v12; // rcx
  _QWORD *v13; // [rsp+20h] [rbp-68h] BYREF
  _QWORD *v14; // [rsp+28h] [rbp-60h] BYREF
  _QWORD v15[3]; // [rsp+30h] [rbp-58h] BYREF
  void **v16; // [rsp+48h] [rbp-40h] BYREF
  __int16 v17; // [rsp+50h] [rbp-38h]
  HMODULE ModuleHandleW; // [rsp+58h] [rbp-30h]
  __int64 v19; // [rsp+60h] [rbp-28h]
  __int64 v20; // [rsp+68h] [rbp-20h]
  __int16 v21; // [rsp+90h] [rbp+8h]
  __int64 v22; // [rsp+98h] [rbp+10h] BYREF

  v21 = (__int16)this;
  v22 = a2;
  v15[1] = -2;
  try
  {
    v2 = mlib::mstring_buf<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::operator new();
    v15[0] = v2;
    if ( v2 )
      v2 = mlib::mstring_buf<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::mstring_buf<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
             v2,
             1024);
    v13 = v2;
    v3 = mlib::mstring_buf<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::operator new();
    v15[0] = v3;
    if ( v3 )
      v3 = mlib::mstring_buf<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::mstring_buf<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
             v3,
             1024);
    v14 = v3;
    v4 = mlib::mstring_buf<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::operator new();
    v15[0] = v4;
    if ( v4 )
      v4 = (void *)mlib::mstring_buf<char,mlib::m_traits<char>,std::allocator<char>>::mstring_buf<char,mlib::m_traits<char>,std::allocator<char>>(v4);
    v15[0] = v4;
    v16 = &mlib::MUILoader::`vftable';
    v17 = v21;
    ModuleHandleW = GetModuleHandleW(0);
    v19 = 0;
    v20 = 0;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::operator=(
      (__int64)&v13,
      (__int64)&v16);
    v15[2] = 0;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::spfva(
      &v14,
      v13[3],
      &v22);
    v5 = v14;
    mlib::fundamental_string<char,mlib::m_traits<char>,std::allocator<char>>::transcode_from(v15, v14[3], *v14);
    v6 = (_QWORD *)v15[0];
    Log_Text_F("base\\winsat\\d3d\\dx9misc.cpp", 1035, *(const char **)(v15[0] + 24LL));
    if ( D3DCommon::g_phStdOut )
    {
      v7 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
             D3DCommon::g_phStdOut + 240,
             &v14);
      std::endl(v7);
    }
    v8 = v6[2]-- == 1;
    if ( v8 && v6 )
    {
      v9 = (void *)v6[3];
      if ( v9 )
        operator delete(v9);
      operator delete(v6);
    }
    v8 = v5[2]-- == 1;
    if ( v8 && v5 )
    {
      v10 = (void *)v5[3];
      if ( v10 )
        operator delete(v10);
      operator delete(v5);
    }
    v8 = v13[2]-- == 1;
    if ( v8 )
    {
      v11 = v13;
      if ( v13 )
      {
        v12 = (void *)v13[3];
        if ( v12 )
          operator delete(v12);
        operator delete(v11);
      }
    }
  }
  catch ( ... )
  {
  }
}

```

## disassembly

```asm
0x18000f134  mov     rax, rsp
0x18000f137  mov     [rax+8], cx
0x18000f13b  mov     [rax+10h], rdx
0x18000f13f  mov     [rax+18h], r8
0x18000f143  mov     [rax+20h], r9
0x18000f147  push    rbx
0x18000f148  push    rdi
0x18000f149  sub     rsp, 78h
0x18000f14d  mov     qword ptr [rax-50h], 0FFFFFFFFFFFFFFFEh
0x18000f155  call    ??2?$mstring_buf@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@CAPEAX_K@Z; mlib::mstring_buf<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::operator new(unsigned __int64)
0x18000f15a  mov     [rsp+88h+var_58], rax
0x18000f15f  test    rax, rax
0x18000f162  jz      short loc_18000F172
0x18000f164  mov     edx, 400h
0x18000f169  mov     rcx, rax
0x18000f16c  call    ??0?$mstring_buf@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@AEAA@_KAEBV?$allocator@G@std@@@Z; mlib::mstring_buf<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::mstring_buf<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(unsigned __int64,std::allocator<ushort> const &)
0x18000f171  nop
0x18000f172  mov     [rsp+88h+var_68], rax
0x18000f177  call    ??2?$mstring_buf@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@CAPEAX_K@Z; mlib::mstring_buf<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::operator new(unsigned __int64)
0x18000f17c  mov     [rsp+88h+var_58], rax
0x18000f181  test    rax, rax
0x18000f184  jz      short loc_18000F194
0x18000f186  mov     edx, 400h
0x18000f18b  mov     rcx, rax
0x18000f18e  call    ??0?$mstring_buf@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@AEAA@_KAEBV?$allocator@G@std@@@Z; mlib::mstring_buf<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::mstring_buf<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(unsigned __int64,std::allocator<ushort> const &)
0x18000f193  nop
0x18000f194  mov     [rsp+88h+var_60], rax
0x18000f199  call    ??2?$mstring_buf@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@CAPEAX_K@Z; mlib::mstring_buf<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::operator new(unsigned __int64)
0x18000f19e  mov     [rsp+88h+var_58], rax
0x18000f1a3  test    rax, rax
0x18000f1a6  jz      short loc_18000F1B1
0x18000f1a8  mov     rcx, rax
0x18000f1ab  call    ??0?$mstring_buf@DV?$m_traits@D@mlib@@V?$allocator@D@std@@@mlib@@AEAA@_KAEBV?$allocator@D@std@@@Z; mlib::mstring_buf<char,mlib::m_traits<char>,std::allocator<char>>::mstring_buf<char,mlib::m_traits<char>,std::allocator<char>>(unsigned __int64,std::allocator<char> const &)
0x18000f1b0  nop
0x18000f1b1  mov     [rsp+88h+var_58], rax
0x18000f1b6  lea     rax, ??_7MUILoader@mlib@@6B@; const mlib::MUILoader::`vftable'
0x18000f1bd  mov     [rsp+88h+var_40], rax
0x18000f1c2  movzx   eax, [rsp+88h+arg_0]
0x18000f1ca  mov     [rsp+88h+var_38], ax
0x18000f1cf  xor     ecx, ecx; lpModuleName
0x18000f1d1  call    cs:__imp_GetModuleHandleW
0x18000f1d7  mov     [rsp+88h+var_30], rax
0x18000f1dc  mov     [rsp+88h+var_28], 0
0x18000f1e5  mov     [rsp+88h+var_20], 0
0x18000f1ee  lea     rdx, [rsp+88h+var_40]
0x18000f1f3  lea     rcx, [rsp+88h+var_68]
0x18000f1f8  call    ??4?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAAEAV01@AEBVMSInitializer@1@@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::operator=(mlib::MSInitializer const &)
0x18000f1fd  mov     [rsp+88h+var_48], 0
0x18000f206  lea     r8, [rsp+88h+arg_8]
0x18000f20e  mov     rdx, [rsp+88h+var_68]
0x18000f213  mov     rdx, [rdx+18h]
0x18000f217  lea     rcx, [rsp+88h+var_60]
0x18000f21c  call    ?spfva@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAXPEBGPEAD@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::spfva(ushort const *,char *)
0x18000f221  mov     rbx, [rsp+88h+var_60]
0x18000f226  mov     r8, [rbx]
0x18000f229  mov     rdx, [rbx+18h]
0x18000f22d  lea     rcx, [rsp+88h+var_58]
0x18000f232  call    ?transcode_from@?$fundamental_string@DV?$m_traits@D@mlib@@V?$allocator@D@std@@@mlib@@QEAAKPEBG_K@Z; mlib::fundamental_string<char,mlib::m_traits<char>,std::allocator<char>>::transcode_from(ushort const *,unsigned __int64)
0x18000f237  mov     rdi, [rsp+88h+var_58]
0x18000f23c  mov     r8, [rdi+18h]
0x18000f240  mov     edx, 40Bh
0x18000f245  lea     rcx, aBaseWinsatD3dD; "base\\winsat\\d3d\\dx9misc.cpp"
0x18000f24c  call    Log_Text_F
0x18000f251  mov     rcx, cs:?g_phStdOut@D3DCommon@@3PEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@EA; mlib::handle_ostreamT<ushort,std::char_traits<ushort>> * D3DCommon::g_phStdOut
0x18000f258  test    rcx, rcx
0x18000f25b  jz      short loc_18000F277
0x18000f25d  add     rcx, 0F0h
0x18000f264  lea     rdx, [rsp+88h+var_60]
0x18000f269  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x18000f26e  mov     rcx, rax
0x18000f271  call    ?endl@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@1@AEAV21@@Z; std::endl(std::basic_ostream<ushort> &)
0x18000f276  nop
0x18000f277  sub     qword ptr [rdi+10h], 1
0x18000f27c  jnz     short loc_18000F29C
0x18000f27e  test    rdi, rdi
0x18000f281  jz      short loc_18000F29C
0x18000f283  mov     rcx, [rdi+18h]
0x18000f287  test    rcx, rcx
0x18000f28a  jz      short loc_18000F292
0x18000f28c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000f292  mov     rcx, rdi
0x18000f295  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000f29b  nop
0x18000f29c  sub     qword ptr [rbx+10h], 1
0x18000f2a1  jnz     short loc_18000F2C1
0x18000f2a3  test    rbx, rbx
0x18000f2a6  jz      short loc_18000F2C1
0x18000f2a8  mov     rcx, [rbx+18h]
0x18000f2ac  test    rcx, rcx
0x18000f2af  jz      short loc_18000F2B7
0x18000f2b1  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000f2b7  mov     rcx, rbx
0x18000f2ba  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000f2c0  nop
0x18000f2c1  mov     rax, [rsp+88h+var_68]
0x18000f2c6  sub     qword ptr [rax+10h], 1
0x18000f2cb  jnz     short loc_18000F2F0
0x18000f2cd  mov     rbx, [rsp+88h+var_68]
0x18000f2d2  test    rbx, rbx
0x18000f2d5  jz      short loc_18000F2F0
0x18000f2d7  mov     rcx, [rbx+18h]
0x18000f2db  test    rcx, rcx
0x18000f2de  jz      short loc_18000F2E6
0x18000f2e0  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000f2e6  mov     rcx, rbx
0x18000f2e9  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000f2ef  nop
0x18000f2f0  jmp     short $+2
0x18000f2f2  add     rsp, 78h
0x18000f2f6  pop     rdi
0x18000f2f7  pop     rbx
0x18000f2f8  retn
```
