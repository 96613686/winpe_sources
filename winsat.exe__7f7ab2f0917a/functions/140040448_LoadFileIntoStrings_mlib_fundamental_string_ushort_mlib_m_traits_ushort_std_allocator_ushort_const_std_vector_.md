# LoadFileIntoStrings(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,std::vector<mlib::fundamental_string<char,mlib::m_traits<char>,std::allocator<char>>,std::allocator<mlib::fundamental_string<char,mlib::m_traits<char>,std::allocator<char>>>> &)

- ea: `0x140040448`
- end: `0x1400406e0`
- name: `?LoadFileIntoStrings@@YA_NAEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@AEAV?$vector@V?$fundamental_string@DV?$m_traits@D@mlib@@V?$allocator@D@std@@@mlib@@V?$allocator@V?$fundamental_string@DV?$m_traits@D@mlib@@V?$allocator@D@std@@@mlib@@@std@@@std@@@Z`
- size: `664`
- prototype: ``
- caller_count: `2`
- callee_count: `18`
- tags: `file_ops`

## callers

- `0x1400337c4`
- `0x1400406e8`

## callees

- `0x140001abc`
- `0x140001ac8`
- `0x140005cb8`
- `0x1400143a0`
- `0x140016480`
- `0x140016d04`
- `0x140018968`
- `0x140021e30`
- `0x140039bd4`
- `0x140039eb8`
- `0x140039f10`
- `0x14003a694`
- `0x14003cd24`
- `0x14003f8e0`
- `0x14003fa8c`
- `0x140040448`
- `0x1400407e4`
- `0x140040878`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1400404ca`
- `KERNEL32!GetLastError` at `0x140040689`
- `KERNEL32!GetLastError` at `0x1400404ca`
- `KERNEL32!GetLastError` at `0x140040689`
- `msvcrt!feof` at `0x140040677`
- `msvcrt!feof` at `0x140040677`
- `msvcrt!_wfopen` at `0x1400404b4`
- `msvcrt!_wfopen` at `0x1400404b4`
- `msvcrt!fgets` at `0x140040512`
- `msvcrt!fgets` at `0x14004065d`
- `msvcrt!fgets` at `0x140040512`
- `msvcrt!fgets` at `0x14004065d`
- `msvcrt!fclose` at `0x1400406b5`
- `msvcrt!fclose` at `0x1400406b5`

## string_xrefs

- `0x1400404d5`: `Can't open input file '%s'`
- `0x140040694`: `Error while reading from file\n%s`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall LoadFileIntoStrings(__int64 a1, _QWORD *a2)
{
  FILE *v5; // r15
  __int64 v6; // rbx
  char *v7; // r12
  char *v8; // rax
  char v9; // r14
  __int64 *v10; // rbx
  __int64 v11; // r8
  _BYTE *non_space_char; // rax
  char v13; // al
  __int64 v14; // rax
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 str; // rax
  __int64 v18; // rcx
  _QWORD *v19; // rbx
  _BYTE *i; // rsi
  bool v21; // al
  __int64 v22; // rcx
  __int64 v23; // rbx
  __int64 v24; // rdx
  _QWORD *v25; // rcx
  __int64 v26; // rdx
  __int64 v27; // rbx
  _QWORD v28[2]; // [rsp+30h] [rbp-10h] BYREF

  std::vector<mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>> const,std::allocator<mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>> const>>::_Destroy(
    a1,
    *a2,
    a2[1]);
  a2[1] = *a2;
  if ( (unsigned __int8)mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::is_blank(a1) )
  {
    Record_InternalError_w("base\\winsat\\exe\\textfileloader.cpp");
    return 0;
  }
  v5 = _wfopen(*(const wchar_t **)(*(_QWORD *)a1 + 24LL), L"rt");
  if ( !v5 )
  {
    v6 = *(_QWORD *)(*(_QWORD *)a1 + 24LL);
    GetLastError();
    Record_Win32Error_w("base\\winsat\\exe\\textfileloader.cpp", v6);
    return 0;
  }
  v7 = (char *)operator new[](0x1000u);
  mlib::fundamental_string<char,mlib::m_traits<char>,std::allocator<char>>::fundamental_string<char,mlib::m_traits<char>,std::allocator<char>>(v28);
  v8 = fgets(v7, 4096, v5);
  v9 = 1;
  while ( v8 )
  {
    mlib::fundamental_string<char,mlib::m_traits<char>,std::allocator<char>>::assign(v28, v7);
    v10 = (__int64 *)v28[0];
    v11 = *(_QWORD *)v28[0];
    if ( *(_QWORD *)v28[0] <= 1u
      || ((non_space_char = (_BYTE *)mlib::fundamental_string<char,mlib::m_traits<char>,std::allocator<char>>::first_non_space_char(v28),
           v11 = *v10,
           (unsigned __int64)non_space_char >= v10[3] + *v10 - 1)
       || *non_space_char == 47 && non_space_char[1] == 47
        ? (v13 = 1)
        : (v13 = 0),
          !v13) )
    {
      if ( v11 )
      {
        v14 = mlib::m_traits<char>::CStrlen("//", 0x10000);
        str = mlib::fundamental_string<char,mlib::m_traits<char>,std::allocator<char>>::find_str(v28, v15, v16, v14);
        if ( str != -1 )
          mlib::fundamental_string<char,mlib::m_traits<char>,std::allocator<char>>::erase(v28, str);
      }
      mlib::fundamental_string<char,mlib::m_traits<char>,std::allocator<char>>::strip_lt_ws(v28);
      v19 = (_QWORD *)v28[0];
      if ( *(_QWORD *)v28[0] )
      {
        for ( i = *(_BYTE **)(v28[0] + 24LL); (unsigned __int64)i < v19[3] + *v19; ++i )
        {
          LOBYTE(v18) = *i;
          if ( !(unsigned __int8)mlib::m_traits<char>::isSpace(v18) )
          {
            v21 = (unsigned __int64)v28 < a2[1] && *a2 <= (unsigned __int64)v28;
            v22 = a2[2];
            if ( v21 )
            {
              v23 = ((__int64)v28 - *a2) >> 3;
              if ( a2[1] == v22 )
                std::vector<mlib::fundamental_string<char,mlib::m_traits<char>,std::allocator<char>>>::_Reserve(a2);
              v24 = *a2;
              v25 = (_QWORD *)a2[1];
              *v25 = 0;
              v26 = *(_QWORD *)(v24 + 8 * v23);
            }
            else
            {
              if ( a2[1] == v22 )
                std::vector<mlib::fundamental_string<char,mlib::m_traits<char>,std::allocator<char>>>::_Reserve(a2);
              v25 = (_QWORD *)a2[1];
              *v25 = 0;
              v26 = (__int64)v19;
            }
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::attach_buf(
              v25,
              v26);
            a2[1] += 8LL;
            break;
          }
        }
      }
    }
    v8 = fgets(v7, 4096, v5);
  }
  operator delete(v7);
  if ( !feof(v5) )
  {
    v27 = *(_QWORD *)(*(_QWORD *)a1 + 24LL);
    GetLastError();
    Record_Win32Error_w("base\\winsat\\exe\\textfileloader.cpp", v27);
    v9 = 0;
  }
  fclose(v5);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v28);
  return v9;
}

```

## disassembly

```asm
0x140040448  mov     [rsp-38h+arg_10], rbx
0x14004044d  push    rbp
0x14004044e  push    rsi
0x14004044f  push    rdi
0x140040450  push    r12
0x140040452  push    r13
0x140040454  push    r14
0x140040456  push    r15
0x140040458  mov     rbp, rsp
0x14004045b  sub     rsp, 40h
0x14004045f  mov     rdi, rdx
0x140040462  mov     r13, rcx
0x140040465  mov     r8, [rdx+8]
0x140040469  mov     rdx, [rdx]
0x14004046c  call    ?_Destroy@?$vector@$$CBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@V?$allocator@$$CBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@std@@@std@@IEAAXPEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@0@Z; std::vector<mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const,std::allocator<mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const>>::_Destroy(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x140040471  mov     rax, [rdi]
0x140040474  mov     [rdi+8], rax
0x140040478  mov     rcx, r13
0x14004047b  call    ?is_blank@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEBA_NXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::is_blank(void)
0x140040480  test    al, al
0x140040482  jz      short loc_1400404A5
0x140040484  xor     r9d, r9d
0x140040487  lea     r8, aTheFileNamePar; "the file name parameter is blank"
0x14004048e  lea     edx, [r9+1Fh]
0x140040492  lea     rcx, aBaseWinsatExeT; "base\\winsat\\exe\\textfileloader.cpp"
0x140040499  call    Record_InternalError_w
0x14004049e  xor     al, al
0x1400404a0  jmp     loc_1400406C8
0x1400404a5  mov     rcx, [r13+0]
0x1400404a9  lea     rdx, aRt; "rt"
0x1400404b0  mov     rcx, [rcx+18h]; FileName
0x1400404b4  call    cs:__imp__wfopen
0x1400404ba  mov     r15, rax
0x1400404bd  test    rax, rax
0x1400404c0  jnz     short loc_1400404F1
0x1400404c2  mov     rax, [r13+0]
0x1400404c6  mov     rbx, [rax+18h]
0x1400404ca  call    cs:__imp_GetLastError
0x1400404d0  mov     qword ptr [rsp+40h+var_20], rbx; char
0x1400404d5  lea     r9, aCanTOpenInputF; "Can't open input file '%s'"
0x1400404dc  mov     r8d, eax
0x1400404df  lea     edx, [r15+27h]
0x1400404e3  lea     rcx, aBaseWinsatExeT; "base\\winsat\\exe\\textfileloader.cpp"
0x1400404ea  call    Record_Win32Error_w
0x1400404ef  jmp     short loc_14004049E
0x1400404f1  mov     ebx, 1000h
0x1400404f6  mov     ecx, ebx; unsigned __int64
0x1400404f8  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1400404fd  mov     r12, rax
0x140040500  lea     rcx, [rbp+var_10]
0x140040504  call    ??0?$fundamental_string@DV?$m_traits@D@mlib@@V?$allocator@D@std@@@mlib@@QEAA@XZ; mlib::fundamental_string<char,mlib::m_traits<char>,std::allocator<char>>::fundamental_string<char,mlib::m_traits<char>,std::allocator<char>>(void)
0x140040509  nop
0x14004050a  mov     r8, r15; Stream
0x14004050d  mov     edx, ebx; MaxCount
0x14004050f  mov     rcx, r12; Buffer
0x140040512  call    cs:__imp_fgets
0x140040518  mov     r14d, 1
0x14004051e  jmp     loc_140040663
0x140040523  mov     rdx, r12
0x140040526  lea     rcx, [rbp+var_10]
0x14004052a  call    ?assign@?$fundamental_string@DV?$m_traits@D@mlib@@V?$allocator@D@std@@@mlib@@QEAAAEAV12@PEBD@Z; mlib::fundamental_string<char,mlib::m_traits<char>,std::allocator<char>>::assign(char const *)
0x14004052f  mov     rbx, [rbp+var_10]
0x140040533  mov     r8, [rbx]
0x140040536  cmp     r8, r14
0x140040539  jbe     short loc_14004056E
0x14004053b  lea     rcx, [rbp+var_10]
0x14004053f  call    ?first_non_space_char@?$fundamental_string@DV?$m_traits@D@mlib@@V?$allocator@D@std@@@mlib@@QEBAPEBDXZ; mlib::fundamental_string<char,mlib::m_traits<char>,std::allocator<char>>::first_non_space_char(void)
0x140040544  mov     r8, [rbx]
0x140040547  lea     rdx, [r8-1]
0x14004054b  add     rdx, [rbx+18h]
0x14004054f  cmp     rax, rdx
0x140040552  jnb     short loc_140040563
0x140040554  cmp     byte ptr [rax], 2Fh ; '/'
0x140040557  jnz     short loc_14004055F
0x140040559  cmp     byte ptr [rax+1], 2Fh ; '/'
0x14004055d  jz      short loc_140040563
0x14004055f  xor     al, al
0x140040561  jmp     short loc_140040566
0x140040563  mov     al, r14b
0x140040566  test    al, al
0x140040568  jnz     loc_140040652
0x14004056e  test    r8, r8
0x140040571  jz      short loc_1400405A2
0x140040573  mov     edx, 10000h
0x140040578  lea     rcx, asc_140139A10; "//"
0x14004057f  call    ?CStrlen@?$m_traits@D@mlib@@SA_KPEBD_K@Z; mlib::m_traits<char>::CStrlen(char const *,unsigned __int64)
0x140040584  mov     r9, rax
0x140040587  lea     rcx, [rbp+var_10]
0x14004058b  call    ?find_str@?$fundamental_string@DV?$m_traits@D@mlib@@V?$allocator@D@std@@@mlib@@IEBA_KPEBD_K1@Z; mlib::fundamental_string<char,mlib::m_traits<char>,std::allocator<char>>::find_str(char const *,unsigned __int64,unsigned __int64)
0x140040590  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140040594  jz      short loc_1400405A2
0x140040596  mov     rdx, rax
0x140040599  lea     rcx, [rbp+var_10]
0x14004059d  call    ?erase@?$fundamental_string@DV?$m_traits@D@mlib@@V?$allocator@D@std@@@mlib@@QEAAAEAV12@_K0@Z; mlib::fundamental_string<char,mlib::m_traits<char>,std::allocator<char>>::erase(unsigned __int64,unsigned __int64)
0x1400405a2  lea     rcx, [rbp+var_10]
0x1400405a6  call    ?strip_lt_ws@?$fundamental_string@DV?$m_traits@D@mlib@@V?$allocator@D@std@@@mlib@@QEAAAEAV12@XZ; mlib::fundamental_string<char,mlib::m_traits<char>,std::allocator<char>>::strip_lt_ws(void)
0x1400405ab  mov     rbx, [rbp+var_10]
0x1400405af  cmp     qword ptr [rbx], 0
0x1400405b3  jz      loc_140040652
0x1400405b9  mov     rsi, [rbx+18h]
0x1400405bd  mov     rax, [rbx]
0x1400405c0  add     rax, [rbx+18h]
0x1400405c4  cmp     rsi, rax
0x1400405c7  jnb     loc_140040652
0x1400405cd  mov     cl, [rsi]
0x1400405cf  call    ?isSpace@?$m_traits@D@mlib@@SA_ND@Z; mlib::m_traits<char>::isSpace(char)
0x1400405d4  test    al, al
0x1400405d6  jz      short loc_1400405DD
0x1400405d8  add     rsi, r14
0x1400405db  jmp     short loc_1400405BD
0x1400405dd  lea     rax, [rbp+var_10]
0x1400405e1  cmp     rax, [rdi+8]
0x1400405e5  jnb     short loc_1400405F5
0x1400405e7  lea     rax, [rbp+var_10]
0x1400405eb  cmp     [rdi], rax
0x1400405ee  ja      short loc_1400405F5
0x1400405f0  mov     al, r14b
0x1400405f3  jmp     short loc_1400405F7
0x1400405f5  xor     al, al
0x1400405f7  mov     rcx, [rdi+10h]
0x1400405fb  test    al, al
0x1400405fd  jz      short loc_14004062C
0x1400405ff  lea     rbx, [rbp+var_10]
0x140040603  sub     rbx, [rdi]
0x140040606  sar     rbx, 3
0x14004060a  cmp     [rdi+8], rcx
0x14004060e  jnz     short loc_140040618
0x140040610  mov     rcx, rdi
0x140040613  call    ?_Reserve@?$vector@V?$fundamental_string@DV?$m_traits@D@mlib@@V?$allocator@D@std@@@mlib@@V?$allocator@V?$fundamental_string@DV?$m_traits@D@mlib@@V?$allocator@D@std@@@mlib@@@std@@@std@@IEAAX_K@Z; std::vector<mlib::fundamental_string<char,mlib::m_traits<char>,std::allocator<char>>>::_Reserve(unsigned __int64)
0x140040618  mov     rdx, [rdi]
0x14004061b  mov     rcx, [rdi+8]
0x14004061f  mov     qword ptr [rcx], 0
0x140040626  mov     rdx, [rdx+rbx*8]
0x14004062a  jmp     short loc_140040648
0x14004062c  cmp     [rdi+8], rcx
0x140040630  jnz     short loc_14004063A
0x140040632  mov     rcx, rdi
0x140040635  call    ?_Reserve@?$vector@V?$fundamental_string@DV?$m_traits@D@mlib@@V?$allocator@D@std@@@mlib@@V?$allocator@V?$fundamental_string@DV?$m_traits@D@mlib@@V?$allocator@D@std@@@mlib@@@std@@@std@@IEAAX_K@Z; std::vector<mlib::fundamental_string<char,mlib::m_traits<char>,std::allocator<char>>>::_Reserve(unsigned __int64)
0x14004063a  mov     rcx, [rdi+8]
0x14004063e  mov     qword ptr [rcx], 0
0x140040645  mov     rdx, rbx
0x140040648  call    ?attach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXPEAV?$mstring_buf@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::attach_buf(mlib::mstring_buf<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x14004064d  add     qword ptr [rdi+8], 8
0x140040652  mov     r8, r15; Stream
0x140040655  mov     edx, 1000h; MaxCount
0x14004065a  mov     rcx, r12; Buffer
0x14004065d  call    cs:__imp_fgets
0x140040663  test    rax, rax
0x140040666  jnz     loc_140040523
0x14004066c  mov     rcx, r12; Block
0x14004066f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140040674  mov     rcx, r15; Stream
0x140040677  call    cs:__imp_feof
0x14004067d  test    eax, eax
0x14004067f  jnz     short loc_1400406B2
0x140040681  mov     rax, [r13+0]
0x140040685  mov     rbx, [rax+18h]
0x140040689  call    cs:__imp_GetLastError
0x14004068f  mov     qword ptr [rsp+40h+var_20], rbx; char
0x140040694  lea     r9, aErrorWhileRead; "Error while reading from file\n%s"
0x14004069b  mov     r8d, eax
0x14004069e  mov     edx, 4Ah ; 'J'
0x1400406a3  lea     rcx, aBaseWinsatExeT; "base\\winsat\\exe\\textfileloader.cpp"
0x1400406aa  call    Record_Win32Error_w
0x1400406af  xor     r14b, r14b
0x1400406b2  mov     rcx, r15; Stream
0x1400406b5  call    cs:__imp_fclose
0x1400406bb  nop
0x1400406bc  lea     rcx, [rbp+var_10]
0x1400406c0  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x1400406c5  mov     al, r14b
0x1400406c8  mov     rbx, [rsp+40h+arg_10]
0x1400406d0  add     rsp, 40h
0x1400406d4  pop     r15
0x1400406d6  pop     r14
0x1400406d8  pop     r13
0x1400406da  pop     r12
0x1400406dc  pop     rdi
0x1400406dd  pop     rsi
0x1400406de  pop     rbp
0x1400406df  retn
```
