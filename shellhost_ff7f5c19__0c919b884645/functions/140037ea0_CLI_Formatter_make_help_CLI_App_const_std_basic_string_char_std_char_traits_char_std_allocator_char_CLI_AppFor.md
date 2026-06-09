# CLI::Formatter::make_help(CLI::App const *,std::basic_string<char,std::char_traits<char>,std::allocator<char>>,CLI::AppFormatMode)

- ea: `0x140037ea0`
- end: `0x14003836b`
- name: `?make_help@Formatter@CLI@@UEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBVApp@2@V34@W4AppFormatMode@2@@Z`
- size: `1227`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1400083f0`
- `0x140008a50`
- `0x14000c50c`
- `0x14000f7e0`
- `0x14000fab8`
- `0x140010608`
- `0x140010ad0`
- `0x1400379b0`
- `0x140037ea0`
- `0x14004aa1c`
- `0x14004b384`
- `0x140067010`

## import_xrefs

- `msvcp_win!??1?$basic_iostream@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x14003832c`
- `msvcp_win!??1?$basic_iostream@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x14003832c`
- `msvcp_win!??1?$basic_streambuf@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x140038321`
- `msvcp_win!??1?$basic_streambuf@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x140038321`
- `msvcp_win!??1?$basic_ios@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x140038336`
- `msvcp_win!??1?$basic_ios@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x140038336`
- `msvcp_win!??0?$basic_iostream@DU?$char_traits@D@std@@@std@@QEAA@PEAV?$basic_streambuf@DU?$char_traits@D@std@@@1@@Z` at `0x140037f47`
- `msvcp_win!??0?$basic_iostream@DU?$char_traits@D@std@@@std@@QEAA@PEAV?$basic_streambuf@DU?$char_traits@D@std@@@1@@Z` at `0x140037f47`
- `msvcp_win!??0?$basic_ios@DU?$char_traits@D@std@@@std@@IEAA@XZ` at `0x140037f2b`
- `msvcp_win!??0?$basic_ios@DU?$char_traits@D@std@@@std@@IEAA@XZ` at `0x140037f2b`
- `msvcp_win!??0?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAA@XZ` at `0x140037f7b`
- `msvcp_win!??0?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAA@XZ` at `0x140037f7b`

## string_xrefs

- `0x140037fca`: `Subcommands`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CLI::Formatter::make_help(__int64 a1, __int64 a2, _QWORD *a3, void *a4, unsigned int a5)
{
  void *v5; // rbx
  const void **v9; // rbx
  const void *v10; // rcx
  unsigned __int64 v11; // r15
  __int64 v12; // r14
  __int64 v13; // rax
  __int64 v14; // rdx
  _QWORD *v15; // rax
  _QWORD *v16; // rdx
  unsigned __int64 v17; // rdx
  void *v18; // rcx
  __int64 v19; // rax
  _QWORD *v20; // rax
  _QWORD *v21; // rdx
  unsigned __int64 v22; // rdx
  void *v23; // rcx
  _QWORD *v24; // rax
  _QWORD *v25; // rdx
  unsigned __int64 v26; // rdx
  void *v27; // rcx
  _QWORD *groups; // rax
  _QWORD *v29; // rdx
  unsigned __int64 v30; // rdx
  void *v31; // rcx
  _QWORD *v32; // rax
  _QWORD *v33; // rdx
  unsigned __int64 v34; // rdx
  void *v35; // rcx
  _QWORD *v36; // rax
  _QWORD *v37; // rdx
  unsigned __int64 v38; // rdx
  void *v39; // rcx
  int v42; // [rsp+4Ch] [rbp-B4h]
  _QWORD v43[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 *v44; // [rsp+60h] [rbp-A0h] BYREF
  void **v45; // [rsp+68h] [rbp-98h] BYREF
  char v46[96]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v47; // [rsp+D0h] [rbp-30h]
  int v48; // [rsp+D8h] [rbp-28h]
  _BYTE v49[104]; // [rsp+E8h] [rbp-18h] BYREF
  char v50[32]; // [rsp+150h] [rbp+50h] BYREF
  void *v51; // [rsp+170h] [rbp+70h]
  void *v52[3]; // [rsp+178h] [rbp+78h] BYREF
  unsigned __int64 v53; // [rsp+190h] [rbp+90h]

  v5 = a4;
  v51 = a4;
  if ( a5 != 2 )
  {
    v43[0] = &std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::`vbtable'{for `std::istream'};
    v44 = &std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::`vbtable'{for `std::ostream'};
    std::ios::ios(v49);
    std::iostream::basic_iostream<char>(v43, &v45, 0);
    *(_QWORD *)((char *)v43 + *(int *)(v43[0] + 4LL)) = &std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::`vftable';
    *(int *)((char *)&v42 + *(int *)(v43[0] + 4LL)) = *(_DWORD *)(v43[0] + 4LL) - 152;
    std::streambuf::streambuf(&v45);
    v45 = &std::stringbuf::`vftable';
    v47 = 0;
    v48 = 0;
    if ( !a3[3] && a3[105] )
    {
      v9 = (const void **)(a3 + 106);
      v10 = a3 + 106;
      v11 = a3[109];
      if ( v11 > 0xF )
        v10 = *v9;
      v12 = a3[108];
      if ( v12 != 11 || memcmp_0(v10, "Subcommands", 0xBu) )
      {
        if ( v11 > 0xF )
          v9 = (const void **)*v9;
        v13 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(&v44, v9, v12);
        LOBYTE(v14) = 58;
        std::operator<<<std::char_traits<char>>(v13, v14);
      }
      v5 = a4;
    }
    v15 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, void **, _QWORD *))(*(_QWORD *)a1 + 64LL))(a1, v52, a3);
    if ( v15[3] <= 0xFu )
      v16 = v15;
    else
      v16 = (_QWORD *)*v15;
    std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(&v44, v16, v15[2]);
    if ( v53 > 0xF )
    {
      v17 = v53 + 1;
      if ( v53 + 1 < 0x1000 )
      {
        v18 = v52[0];
      }
      else
      {
        v18 = (void *)*((_QWORD *)v52[0] - 1);
        if ( (unsigned __int64)((char *)v52[0] - (char *)v18 - 8) > 0x1F )
          goto LABEL_65;
        v17 = v53 + 40;
      }
      operator delete(v18, v17);
    }
    v19 = std::string::string(v50, v5);
    v20 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, void **, _QWORD *, __int64))(*(_QWORD *)a1 + 72LL))(
                      a1,
                      v52,
                      a3,
                      v19);
    if ( v20[3] <= 0xFu )
      v21 = v20;
    else
      v21 = (_QWORD *)*v20;
    std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(&v44, v21, v20[2]);
    if ( v53 > 0xF )
    {
      v22 = v53 + 1;
      if ( v53 + 1 < 0x1000 )
      {
        v23 = v52[0];
      }
      else
      {
        v23 = (void *)*((_QWORD *)v52[0] - 1);
        if ( (unsigned __int64)((char *)v52[0] - (char *)v23 - 8) > 0x1F )
          goto LABEL_65;
        v22 = v53 + 40;
      }
      operator delete(v23, v22);
    }
    v24 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, void **, _QWORD *))(*(_QWORD *)a1 + 24LL))(a1, v52, a3);
    if ( v24[3] <= 0xFu )
      v25 = v24;
    else
      v25 = (_QWORD *)*v24;
    std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(&v44, v25, v24[2]);
    if ( v53 > 0xF )
    {
      v26 = v53 + 1;
      if ( v53 + 1 < 0x1000 )
      {
        v27 = v52[0];
      }
      else
      {
        v27 = (void *)*((_QWORD *)v52[0] - 1);
        if ( (unsigned __int64)((char *)v52[0] - (char *)v27 - 8) > 0x1F )
          goto LABEL_65;
        v26 = v53 + 40;
      }
      operator delete(v27, v26);
    }
    groups = (_QWORD *)CLI::Formatter::make_groups(a1, v52, a3, a5);
    if ( groups[3] <= 0xFu )
      v29 = groups;
    else
      v29 = (_QWORD *)*groups;
    std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(&v44, v29, groups[2]);
    if ( v53 > 0xF )
    {
      v30 = v53 + 1;
      if ( v53 + 1 < 0x1000 )
      {
        v31 = v52[0];
      }
      else
      {
        v31 = (void *)*((_QWORD *)v52[0] - 1);
        if ( (unsigned __int64)((char *)v52[0] - (char *)v31 - 8) > 0x1F )
          goto LABEL_65;
        v30 = v53 + 40;
      }
      operator delete(v31, v30);
    }
    v32 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, void **, _QWORD *, _QWORD))(*(_QWORD *)a1 + 32LL))(
                      a1,
                      v52,
                      a3,
                      a5);
    if ( v32[3] <= 0xFu )
      v33 = v32;
    else
      v33 = (_QWORD *)*v32;
    std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(&v44, v33, v32[2]);
    if ( v53 > 0xF )
    {
      v34 = v53 + 1;
      if ( v53 + 1 < 0x1000 )
      {
        v35 = v52[0];
      }
      else
      {
        v35 = (void *)*((_QWORD *)v52[0] - 1);
        if ( (unsigned __int64)((char *)v52[0] - (char *)v35 - 8) > 0x1F )
          goto LABEL_65;
        v34 = v53 + 40;
      }
      operator delete(v35, v34);
    }
    v36 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, void **, _QWORD *))(*(_QWORD *)a1 + 56LL))(a1, v52, a3);
    if ( v36[3] <= 0xFu )
      v37 = v36;
    else
      v37 = (_QWORD *)*v36;
    std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(&v44, v37, v36[2]);
    if ( v53 <= 0xF )
      goto LABEL_68;
    v38 = v53 + 1;
    if ( v53 + 1 < 0x1000 )
    {
      v39 = v52[0];
      goto LABEL_67;
    }
    v39 = (void *)*((_QWORD *)v52[0] - 1);
    if ( (unsigned __int64)((char *)v52[0] - (char *)v39 - 8) <= 0x1F )
    {
      v38 = v53 + 40;
LABEL_67:
      operator delete(v39, v38);
LABEL_68:
      std::stringbuf::str(&v45, a2);
      *(_QWORD *)((char *)v43 + *(int *)(v43[0] + 4LL)) = &std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::`vftable';
      *(int *)((char *)&v42 + *(int *)(v43[0] + 4LL)) = *(_DWORD *)(v43[0] + 4LL) - 152;
      v45 = &std::stringbuf::`vftable';
      std::stringbuf::_Tidy(&v45);
      std::streambuf::~streambuf<char,std::char_traits<char>>(&v45);
      std::iostream::~basic_iostream<char,std::char_traits<char>>(v46);
      std::ios::~ios<char,std::char_traits<char>>(v49);
      goto LABEL_69;
    }
LABEL_65:
    __fastfail(5u);
  }
  (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 48LL))(a1, a2);
LABEL_69:
  std::string::_Tidy_deallocate(v5);
  return a2;
}

```

## disassembly

```asm
0x140037ea0  push    rbp
0x140037ea2  push    rbx
0x140037ea3  push    rsi
0x140037ea4  push    rdi
0x140037ea5  push    r12
0x140037ea7  push    r13
0x140037ea9  push    r14
0x140037eab  push    r15
0x140037ead  lea     rbp, [rsp-0A8h]
0x140037eb5  sub     rsp, 1A8h
0x140037ebc  mov     rax, cs:__security_cookie
0x140037ec3  xor     rax, rsp
0x140037ec6  mov     [rbp+0E0h+var_48], rax
0x140037ecd  mov     rbx, r9
0x140037ed0  mov     [rsp+1E0h+var_1A8], rbx
0x140037ed5  mov     rsi, r8
0x140037ed8  mov     r12, rdx
0x140037edb  mov     rdi, rcx
0x140037ede  mov     [rbp+0E0h+var_70], rdx
0x140037ee2  mov     [rbp+0E0h+var_70], rbx
0x140037ee6  mov     r13d, [rbp+0E0h+arg_20]
0x140037eed  xor     r14d, r14d
0x140037ef0  mov     [rsp+1E0h+var_1B0], r14d
0x140037ef5  cmp     r13d, 2
0x140037ef9  jnz     short loc_140037F0F
0x140037efb  mov     rdx, [rcx]
0x140037efe  mov     rax, [rdx+30h]
0x140037f02  mov     rdx, r12
0x140037f05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140037f0a  jmp     loc_14003833D
0x140037f0f  lea     rax, ??_8?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@7B?$basic_istream@DU?$char_traits@D@std@@@1@@; const std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::`vbtable'{for `std::istream'}
0x140037f16  mov     [rsp+1E0h+var_190], rax
0x140037f1b  lea     rax, ??_8?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@7B?$basic_ostream@DU?$char_traits@D@std@@@1@@; const std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::`vbtable'{for `std::ostream'}
0x140037f22  mov     [rsp+1E0h+var_180], rax
0x140037f27  lea     rcx, [rbp+0E0h+var_F8]
0x140037f2b  call    cs:__imp_??0?$basic_ios@DU?$char_traits@D@std@@@std@@IEAA@XZ; std::ios::ios(void)
0x140037f31  nop
0x140037f32  mov     [rsp+1E0h+var_1B0], 2
0x140037f3a  xor     r8d, r8d
0x140037f3d  lea     rdx, [rsp+1E0h+var_178]
0x140037f42  lea     rcx, [rsp+1E0h+var_190]
0x140037f47  call    cs:__imp_??0?$basic_iostream@DU?$char_traits@D@std@@@std@@QEAA@PEAV?$basic_streambuf@DU?$char_traits@D@std@@@1@@Z; std::iostream::basic_iostream<char>(std::streambuf *)
0x140037f4d  nop
0x140037f4e  mov     rax, [rsp+1E0h+var_190]
0x140037f53  movsxd  rcx, dword ptr [rax+4]
0x140037f57  lea     rax, ??_7?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@6B@; const std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::`vftable'
0x140037f5e  mov     [rsp+rcx+1E0h+var_190], rax
0x140037f63  mov     rax, [rsp+1E0h+var_190]
0x140037f68  movsxd  rcx, dword ptr [rax+4]
0x140037f6c  lea     edx, [rcx-98h]
0x140037f72  mov     [rsp+rcx+1E0h+var_194], edx
0x140037f76  lea     rcx, [rsp+1E0h+var_178]
0x140037f7b  call    cs:__imp_??0?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAA@XZ; std::streambuf::streambuf(void)
0x140037f81  lea     r15, ??_7?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@6B@; const std::stringbuf::`vftable'
0x140037f88  mov     [rsp+1E0h+var_178], r15
0x140037f8d  mov     [rbp+0E0h+var_110], r14
0x140037f91  mov     [rbp+0E0h+var_108], r14d
0x140037f95  cmp     qword ptr [rsi+18h], 0
0x140037f9a  jnz     short loc_140038009
0x140037f9c  cmp     qword ptr [rsi+348h], 0
0x140037fa4  jz      short loc_140038009
0x140037fa6  lea     rbx, [rsi+350h]
0x140037fad  mov     rcx, rbx
0x140037fb0  mov     r15, [rbx+18h]
0x140037fb4  cmp     r15, 0Fh
0x140037fb8  jbe     short loc_140037FBD
0x140037fba  mov     rcx, [rbx]; Buf1
0x140037fbd  mov     r14, [rbx+10h]
0x140037fc1  cmp     r14, 0Bh
0x140037fc5  jnz     short loc_140037FDA
0x140037fc7  mov     r8, r14; Size
0x140037fca  lea     rdx, aSubcommands_0; "Subcommands"
0x140037fd1  call    memcmp_0
0x140037fd6  test    eax, eax
0x140037fd8  jz      short loc_140037FFD
0x140037fda  cmp     r15, 0Fh
0x140037fde  jbe     short loc_140037FE3
0x140037fe0  mov     rbx, [rbx]
0x140037fe3  mov     r8, r14
0x140037fe6  mov     rdx, rbx
0x140037fe9  lea     rcx, [rsp+1E0h+var_180]
0x140037fee  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x140037ff3  mov     dl, 3Ah ; ':'
0x140037ff5  mov     rcx, rax
0x140037ff8  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@D@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char)
0x140037ffd  lea     r15, ??_7?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@6B@; const std::stringbuf::`vftable'
0x140038004  mov     rbx, [rsp+1E0h+var_1A8]
0x140038009  mov     rax, [rdi]
0x14003800c  mov     r8, rsi
0x14003800f  lea     rdx, [rbp+0E0h+var_68]
0x140038013  mov     rcx, rdi
0x140038016  mov     rax, [rax+40h]
0x14003801a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003801f  nop
0x140038020  cmp     qword ptr [rax+18h], 0Fh
0x140038025  jbe     short loc_14003802C
0x140038027  mov     rdx, [rax]
0x14003802a  jmp     short loc_14003802F
0x14003802c  mov     rdx, rax
0x14003802f  mov     r8, [rax+10h]
0x140038033  lea     rcx, [rsp+1E0h+var_180]
0x140038038  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x14003803d  nop
0x14003803e  mov     rdx, [rbp+0E0h+var_50]
0x140038045  cmp     rdx, 0Fh
0x140038049  jbe     short loc_14003807E
0x14003804b  mov     rax, [rbp+0E0h+var_68]
0x14003804f  inc     rdx; unsigned __int64
0x140038052  cmp     rdx, 1000h
0x140038059  jb      short loc_140038076
0x14003805b  mov     rcx, [rax-8]
0x14003805f  sub     rax, rcx
0x140038062  sub     rax, 8
0x140038066  cmp     rax, 1Fh
0x14003806a  ja      loc_1400382C8
0x140038070  add     rdx, 27h ; '''
0x140038074  jmp     short loc_140038079
0x140038076  mov     rcx, rax; void *
0x140038079  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14003807e  mov     rdx, rbx
0x140038081  lea     rcx, [rbp+0E0h+var_90]
0x140038085  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x14003808a  mov     rcx, [rdi]
0x14003808d  mov     r10, [rcx+48h]
0x140038091  mov     r9, rax
0x140038094  mov     r8, rsi
0x140038097  lea     rdx, [rbp+0E0h+var_68]
0x14003809b  mov     rcx, rdi
0x14003809e  mov     rax, r10
0x1400380a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400380a6  nop
0x1400380a7  cmp     qword ptr [rax+18h], 0Fh
0x1400380ac  jbe     short loc_1400380B3
0x1400380ae  mov     rdx, [rax]
0x1400380b1  jmp     short loc_1400380B6
0x1400380b3  mov     rdx, rax
0x1400380b6  mov     r8, [rax+10h]
0x1400380ba  lea     rcx, [rsp+1E0h+var_180]
0x1400380bf  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x1400380c4  nop
0x1400380c5  mov     rdx, [rbp+0E0h+var_50]
0x1400380cc  cmp     rdx, 0Fh
0x1400380d0  jbe     short loc_140038105
0x1400380d2  mov     rax, [rbp+0E0h+var_68]
0x1400380d6  inc     rdx; unsigned __int64
0x1400380d9  cmp     rdx, 1000h
0x1400380e0  jb      short loc_1400380FD
0x1400380e2  mov     rcx, [rax-8]
0x1400380e6  sub     rax, rcx
0x1400380e9  sub     rax, 8
0x1400380ed  cmp     rax, 1Fh
0x1400380f1  ja      loc_1400382C8
0x1400380f7  add     rdx, 27h ; '''
0x1400380fb  jmp     short loc_140038100
0x1400380fd  mov     rcx, rax; void *
0x140038100  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140038105  mov     rax, [rdi]
0x140038108  mov     r8, rsi
0x14003810b  lea     rdx, [rbp+0E0h+var_68]
0x14003810f  mov     rcx, rdi
0x140038112  mov     rax, [rax+18h]
0x140038116  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003811b  nop
0x14003811c  cmp     qword ptr [rax+18h], 0Fh
0x140038121  jbe     short loc_140038128
0x140038123  mov     rdx, [rax]
0x140038126  jmp     short loc_14003812B
0x140038128  mov     rdx, rax
0x14003812b  mov     r8, [rax+10h]
0x14003812f  lea     rcx, [rsp+1E0h+var_180]
0x140038134  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x140038139  nop
0x14003813a  mov     rdx, [rbp+0E0h+var_50]
0x140038141  cmp     rdx, 0Fh
0x140038145  jbe     short loc_14003817A
0x140038147  mov     rax, [rbp+0E0h+var_68]
0x14003814b  inc     rdx; unsigned __int64
0x14003814e  cmp     rdx, 1000h
0x140038155  jb      short loc_140038172
0x140038157  mov     rcx, [rax-8]
0x14003815b  sub     rax, rcx
0x14003815e  sub     rax, 8
0x140038162  cmp     rax, 1Fh
0x140038166  ja      loc_1400382C8
0x14003816c  add     rdx, 27h ; '''
0x140038170  jmp     short loc_140038175
0x140038172  mov     rcx, rax; void *
0x140038175  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14003817a  mov     r9d, r13d
0x14003817d  mov     r8, rsi
0x140038180  lea     rdx, [rbp+0E0h+var_68]
0x140038184  mov     rcx, rdi
0x140038187  call    ?make_groups@Formatter@CLI@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBVApp@2@W4AppFormatMode@2@@Z; CLI::Formatter::make_groups(CLI::App const *,CLI::AppFormatMode)
0x14003818c  nop
0x14003818d  cmp     qword ptr [rax+18h], 0Fh
0x140038192  jbe     short loc_140038199
0x140038194  mov     rdx, [rax]
0x140038197  jmp     short loc_14003819C
0x140038199  mov     rdx, rax
0x14003819c  mov     r8, [rax+10h]
0x1400381a0  lea     rcx, [rsp+1E0h+var_180]
0x1400381a5  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x1400381aa  nop
0x1400381ab  mov     rdx, [rbp+0E0h+var_50]
0x1400381b2  cmp     rdx, 0Fh
0x1400381b6  jbe     short loc_1400381EB
0x1400381b8  mov     rax, [rbp+0E0h+var_68]
0x1400381bc  inc     rdx; unsigned __int64
0x1400381bf  cmp     rdx, 1000h
0x1400381c6  jb      short loc_1400381E3
0x1400381c8  mov     rcx, [rax-8]
0x1400381cc  sub     rax, rcx
0x1400381cf  sub     rax, 8
0x1400381d3  cmp     rax, 1Fh
0x1400381d7  ja      loc_1400382C8
0x1400381dd  add     rdx, 27h ; '''
0x1400381e1  jmp     short loc_1400381E6
0x1400381e3  mov     rcx, rax; void *
0x1400381e6  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400381eb  mov     rax, [rdi]
0x1400381ee  mov     r9d, r13d
0x1400381f1  mov     r8, rsi
0x1400381f4  lea     rdx, [rbp+0E0h+var_68]
0x1400381f8  mov     rcx, rdi
0x1400381fb  mov     rax, [rax+20h]
0x1400381ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140038204  nop
0x140038205  cmp     qword ptr [rax+18h], 0Fh
0x14003820a  jbe     short loc_140038211
0x14003820c  mov     rdx, [rax]
0x14003820f  jmp     short loc_140038214
0x140038211  mov     rdx, rax
0x140038214  mov     r8, [rax+10h]
0x140038218  lea     rcx, [rsp+1E0h+var_180]
0x14003821d  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x140038222  nop
0x140038223  mov     rdx, [rbp+0E0h+var_50]
0x14003822a  cmp     rdx, 0Fh
0x14003822e  jbe     short loc_14003825F
0x140038230  mov     rax, [rbp+0E0h+var_68]
0x140038234  inc     rdx; unsigned __int64
0x140038237  cmp     rdx, 1000h
0x14003823e  jb      short loc_140038257
0x140038240  mov     rcx, [rax-8]
0x140038244  sub     rax, rcx
0x140038247  sub     rax, 8
0x14003824b  cmp     rax, 1Fh
0x14003824f  ja      short loc_1400382C8
0x140038251  add     rdx, 27h ; '''
0x140038255  jmp     short loc_14003825A
0x140038257  mov     rcx, rax; void *
0x14003825a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14003825f  mov     rax, [rdi]
0x140038262  mov     r8, rsi
0x140038265  lea     rdx, [rbp+0E0h+var_68]
0x140038269  mov     rcx, rdi
0x14003826c  mov     rax, [rax+38h]
0x140038270  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140038275  nop
0x140038276  cmp     qword ptr [rax+18h], 0Fh
0x14003827b  jbe     short loc_140038282
0x14003827d  mov     rdx, [rax]
0x140038280  jmp     short loc_140038285
0x140038282  mov     rdx, rax
0x140038285  mov     r8, [rax+10h]
0x140038289  lea     rcx, [rsp+1E0h+var_180]
0x14003828e  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x140038293  nop
0x140038294  mov     rdx, [rbp+0E0h+var_50]
0x14003829b  cmp     rdx, 0Fh
0x14003829f  jbe     short loc_1400382D7
0x1400382a1  mov     rax, [rbp+0E0h+var_68]
0x1400382a5  inc     rdx; unsigned __int64
0x1400382a8  cmp     rdx, 1000h
0x1400382af  jb      short loc_1400382CF
0x1400382b1  mov     rcx, [rax-8]
0x1400382b5  sub     rax, rcx
0x1400382b8  sub     rax, 8
0x1400382bc  cmp     rax, 1Fh
0x1400382c0  ja      short loc_1400382C8
0x1400382c2  add     rdx, 27h ; '''
0x1400382c6  jmp     short loc_1400382D2
0x1400382c8  mov     ecx, 5
0x1400382cd  int     29h; Win8: RtlFailFast(ecx)
0x1400382cf  mov     rcx, rax; void *
0x1400382d2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400382d7  mov     rdx, r12
0x1400382da  lea     rcx, [rsp+1E0h+var_178]
0x1400382df  call    ?str@?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@XZ; std::stringbuf::str(void)
0x1400382e4  nop
0x1400382e5  mov     rax, [rsp+1E0h+var_190]
0x1400382ea  movsxd  rcx, dword ptr [rax+4]
0x1400382ee  lea     rax, ??_7?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@6B@; const std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::`vftable'
0x1400382f5  mov     [rsp+rcx+1E0h+var_190], rax
0x1400382fa  mov     rax, [rsp+1E0h+var_190]
0x1400382ff  movsxd  rcx, dword ptr [rax+4]
0x140038303  lea     edx, [rcx-98h]
0x140038309  mov     [rsp+rcx+1E0h+var_194], edx
0x14003830d  mov     [rsp+1E0h+var_178], r15
0x140038312  lea     rcx, [rsp+1E0h+var_178]
  ... truncated ...
```
