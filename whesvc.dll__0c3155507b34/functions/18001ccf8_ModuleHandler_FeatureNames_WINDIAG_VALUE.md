# ModuleHandler::FeatureNames(_WINDIAG_VALUE *)

- ea: `0x18001ccf8`
- end: `0x18001cf72`
- name: `?FeatureNames@ModuleHandler@@AEAAJPEAU_WINDIAG_VALUE@@@Z`
- size: `634`
- prototype: `__int64 __fastcall(ModuleHandler *__hidden this, struct _WINDIAG_VALUE *)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x1800214d8`

## callees

- `0x1800032e0`
- `0x180004575`
- `0x180004581`
- `0x180009044`
- `0x18000fc50`
- `0x180011578`
- `0x180019b18`
- `0x18001a3b8`
- `0x18001b7a0`
- `0x18001ccf8`

## import_xrefs

- `msvcp_win!??1?$basic_ostream@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x18001cf44`
- `msvcp_win!??1?$basic_ostream@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x18001cf44`
- `msvcp_win!??0?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAA@PEAV?$basic_streambuf@DU?$char_traits@D@std@@@1@_N@Z` at `0x18001cd84`
- `msvcp_win!??0?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAA@PEAV?$basic_streambuf@DU?$char_traits@D@std@@@1@_N@Z` at `0x18001cd84`
- `msvcp_win!??0?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAA@XZ` at `0x18001cdb8`
- `msvcp_win!??0?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAA@XZ` at `0x18001cdb8`
- `msvcp_win!??1?$basic_ios@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x18001cf4e`
- `msvcp_win!??1?$basic_ios@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x18001cf4e`
- `msvcp_win!??0?$basic_ios@DU?$char_traits@D@std@@@std@@IEAA@XZ` at `0x18001cd65`
- `msvcp_win!??0?$basic_ios@DU?$char_traits@D@std@@@std@@IEAA@XZ` at `0x18001cd65`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001cecc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001cecc`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ModuleHandler::FeatureNames(ModuleHandler *this, struct _WINDIAG_VALUE *a2)
{
  char v4; // r15
  __int64 v5; // r8
  __int64 v6; // rdi
  _QWORD *i; // rbx
  _QWORD *v8; // rsi
  unsigned __int64 v9; // rbx
  const void *v10; // r9
  SIZE_T v11; // rbx
  HLOCAL v12; // rax
  void **v13; // rdx
  int v14; // [rsp+2Ch] [rbp-D4h]
  __int64 *v15; // [rsp+30h] [rbp-D0h] BYREF
  void **v16; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v17[16]; // [rsp+40h] [rbp-C0h] BYREF
  const void **v18; // [rsp+50h] [rbp-B0h]
  const void **v19; // [rsp+58h] [rbp-A8h]
  _QWORD *v20; // [rsp+70h] [rbp-90h]
  unsigned __int64 *v21; // [rsp+78h] [rbp-88h]
  int *v22; // [rsp+88h] [rbp-78h]
  unsigned __int64 v23; // [rsp+A0h] [rbp-60h]
  int v24; // [rsp+A8h] [rbp-58h]
  _BYTE v25[104]; // [rsp+B8h] [rbp-48h] BYREF
  void *Src[2]; // [rsp+120h] [rbp+20h] BYREF
  SIZE_T uBytes; // [rsp+130h] [rbp+30h]
  unsigned __int64 v28; // [rsp+138h] [rbp+38h]
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+88h]

  if ( !a2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2CF,
      (unsigned int)"pcshell\\base\\whesvc\\lib\\modulehandler.cpp",
      (const char *)0x80004003LL,
      0);
    return 2147500035LL;
  }
  v4 = 0;
  v15 = &std::ostringstream::`vbtable';
  std::ios::ios(v25);
  std::ostream::ostream(&v15, &v16, 0, 0, 1);
  *(__int64 **)((char *)&v15 + *((int *)v15 + 1)) = (__int64 *)&std::ostringstream::`vftable';
  *(int *)((char *)&v14 + *((int *)v15 + 1)) = *((_DWORD *)v15 + 1) - 136;
  std::streambuf::streambuf(&v16);
  v16 = &std::stringbuf::`vftable';
  v23 = 0;
  v24 = 4;
  v6 = qword_180034E08;
  for ( i = *(_QWORD **)qword_180034E08; i != (_QWORD *)v6; i = (_QWORD *)*i )
  {
    v8 = i + 2;
    if ( v4 )
      std::operator<<<std::char_traits<char>>(&v15);
    if ( i[5] > 0xFu )
      v8 = (_QWORD *)*v8;
    std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(&v15, v8, i[4]);
    v4 = 1;
  }
  *(_OWORD *)Src = 0;
  uBytes = 0;
  v28 = 15;
  LOBYTE(Src[0]) = 0;
  if ( (v24 & 0x22) != 2 )
  {
    v9 = *v21;
    if ( *v21 )
    {
      v10 = *v19;
      if ( v9 < v23 )
        v9 = v23;
      v11 = v9 - (_QWORD)v10;
      goto LABEL_18;
    }
  }
  if ( (v24 & 4) == 0 && *v20 )
  {
    v10 = *v18;
    v11 = *v20 + *v22 - (_QWORD)*v18;
LABEL_18:
    if ( v10 )
    {
      if ( v11 > 0xF )
      {
        std::string::_Reallocate_for<_lambda_a132b9f505f015b07a26cb4edca31da2_,char const *>(Src, v11, v5, v10);
      }
      else
      {
        uBytes = v11;
        memmove_0(Src, v10, v11);
        *((_BYTE *)Src + v11) = 0;
      }
    }
  }
  v12 = LocalAlloc(0x40u, uBytes);
  *((_QWORD *)a2 + 1) = v12;
  if ( v12 )
  {
    v13 = Src;
    if ( v28 > 0xF )
      v13 = (void **)Src[0];
    memcpy_0(v12, v13, uBytes);
    *((_DWORD *)a2 + 4) = uBytes;
    *(_DWORD *)a2 = 4;
  }
  std::string::~string((char **)Src);
  *(__int64 **)((char *)&v15 + *((int *)v15 + 1)) = (__int64 *)&std::ostringstream::`vftable';
  *(int *)((char *)&v14 + *((int *)v15 + 1)) = *((_DWORD *)v15 + 1) - 136;
  std::stringbuf::~stringbuf(&v16);
  std::ostream::~ostream<char,std::char_traits<char>>(v17);
  std::ios::~ios<char,std::char_traits<char>>(v25);
  return 0;
}

```

## disassembly

```asm
0x18001ccf8  push    rbp
0x18001ccfa  push    rbx
0x18001ccfb  push    rsi
0x18001ccfc  push    rdi
0x18001ccfd  push    r14
0x18001ccff  push    r15
0x18001cd01  lea     rbp, [rsp-58h]
0x18001cd06  sub     rsp, 158h
0x18001cd0d  mov     rax, cs:__security_cookie
0x18001cd14  xor     rax, rsp
0x18001cd17  mov     [rbp+80h+var_40], rax
0x18001cd1b  mov     r14, rdx
0x18001cd1e  mov     [rsp+180h+var_160], 0; int
0x18001cd26  test    rdx, rdx
0x18001cd29  jnz     short loc_18001CD52
0x18001cd2b  mov     rcx, [rbp+88h]; this
0x18001cd32  mov     ebx, 80004003h
0x18001cd37  mov     r9d, ebx; char *
0x18001cd3a  lea     r8, aPcshellBaseWhe_2; "pcshell\\base\\whesvc\\lib\\modulehandl"...
0x18001cd41  mov     edx, 2CFh; void *
0x18001cd46  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001cd4b  mov     eax, ebx
0x18001cd4d  jmp     loc_18001CF56
0x18001cd52  xor     r15b, r15b
0x18001cd55  lea     rax, ??_8?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@7B@; const std::ostringstream::`vbtable'
0x18001cd5c  mov     [rsp+180h+var_150], rax
0x18001cd61  lea     rcx, [rbp+80h+var_C8]
0x18001cd65  call    cs:__imp_??0?$basic_ios@DU?$char_traits@D@std@@@std@@IEAA@XZ; std::ios::ios(void)
0x18001cd6b  nop
0x18001cd6c  mov     [rsp+180h+var_160], 1
0x18001cd74  xor     r9d, r9d
0x18001cd77  xor     r8d, r8d
0x18001cd7a  lea     rdx, [rsp+180h+var_148]
0x18001cd7f  lea     rcx, [rsp+180h+var_150]
0x18001cd84  call    cs:__imp_??0?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAA@PEAV?$basic_streambuf@DU?$char_traits@D@std@@@1@_N@Z; std::ostream::ostream(std::streambuf *,bool)
0x18001cd8a  nop
0x18001cd8b  mov     rax, [rsp+180h+var_150]
0x18001cd90  movsxd  rcx, dword ptr [rax+4]
0x18001cd94  lea     rsi, ??_7?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@6B@; const std::ostringstream::`vftable'
0x18001cd9b  mov     [rsp+rcx+180h+var_150], rsi
0x18001cda0  mov     rax, [rsp+180h+var_150]
0x18001cda5  movsxd  rcx, dword ptr [rax+4]
0x18001cda9  lea     edx, [rcx-88h]
0x18001cdaf  mov     [rsp+rcx+180h+var_154], edx
0x18001cdb3  lea     rcx, [rsp+180h+var_148]
0x18001cdb8  call    cs:__imp_??0?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAA@XZ; std::streambuf::streambuf(void)
0x18001cdbe  lea     rax, ??_7?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@6B@; const std::stringbuf::`vftable'
0x18001cdc5  mov     [rsp+180h+var_148], rax
0x18001cdca  mov     [rbp+80h+var_E0], 0
0x18001cdd2  mov     [rbp+80h+var_D8], 4
0x18001cdd9  mov     rdi, cs:qword_180034E08
0x18001cde0  mov     rbx, [rdi]
0x18001cde3  cmp     rbx, rdi
0x18001cde6  jz      short loc_18001CE1E
0x18001cde8  lea     rsi, [rbx+10h]
0x18001cdec  test    r15b, r15b
0x18001cdef  jz      short loc_18001CDFB
0x18001cdf1  lea     rcx, [rsp+180h+var_150]
0x18001cdf6  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@D@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char)
0x18001cdfb  mov     r8, [rsi+10h]
0x18001cdff  cmp     qword ptr [rsi+18h], 0Fh
0x18001ce04  jbe     short loc_18001CE09
0x18001ce06  mov     rsi, [rsi]
0x18001ce09  mov     rdx, rsi
0x18001ce0c  lea     rcx, [rsp+180h+var_150]
0x18001ce11  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18001ce16  mov     r15b, 1
0x18001ce19  mov     rbx, [rbx]
0x18001ce1c  jmp     short loc_18001CDE3
0x18001ce1e  xorps   xmm0, xmm0
0x18001ce21  movups  xmmword ptr [rbp+80h+Src], xmm0
0x18001ce25  mov     [rbp+80h+uBytes], 0
0x18001ce2d  mov     [rbp+80h+var_48], 0Fh
0x18001ce35  mov     byte ptr [rbp+80h+Src], 0
0x18001ce39  mov     [rsp+180h+var_160], 5
0x18001ce41  mov     eax, [rbp+80h+var_D8]
0x18001ce44  and     al, 22h
0x18001ce46  cmp     al, 2
0x18001ce48  jz      short loc_18001CE6D
0x18001ce4a  mov     rax, [rsp+180h+var_108]
0x18001ce4f  mov     rbx, [rax]
0x18001ce52  test    rbx, rbx
0x18001ce55  jz      short loc_18001CE6D
0x18001ce57  mov     rax, [rsp+180h+var_128]
0x18001ce5c  mov     r9, [rax]
0x18001ce5f  cmp     rbx, [rbp+80h+var_E0]
0x18001ce63  cmovb   rbx, [rbp+80h+var_E0]
0x18001ce68  sub     rbx, r9
0x18001ce6b  jmp     short loc_18001CE95
0x18001ce6d  test    byte ptr [rbp+80h+var_D8], 4
0x18001ce71  jnz     short loc_18001CEC3
0x18001ce73  mov     rax, [rsp+180h+var_110]
0x18001ce78  mov     rcx, [rax]
0x18001ce7b  test    rcx, rcx
0x18001ce7e  jz      short loc_18001CEC3
0x18001ce80  mov     rax, [rsp+180h+var_130]
0x18001ce85  mov     r9, [rax]
0x18001ce88  mov     rax, [rbp+80h+var_F8]
0x18001ce8c  movsxd  rbx, dword ptr [rax]
0x18001ce8f  sub     rbx, r9
0x18001ce92  add     rbx, rcx
0x18001ce95  test    r9, r9
0x18001ce98  jz      short loc_18001CEC3
0x18001ce9a  lea     rcx, [rbp+80h+Src]; void *
0x18001ce9e  cmp     rbx, 0Fh
0x18001cea2  ja      short loc_18001CEBA
0x18001cea4  mov     [rbp+80h+uBytes], rbx
0x18001cea8  mov     r8, rbx; Size
0x18001ceab  mov     rdx, r9; Src
0x18001ceae  call    memmove_0
0x18001ceb3  mov     byte ptr [rbp+rbx+80h+Src], 0
0x18001ceb8  jmp     short loc_18001CEC3
0x18001ceba  mov     rdx, rbx
0x18001cebd  call    ??$_Reallocate_for@V_lambda_a132b9f505f015b07a26cb4edca31da2_@@PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_a132b9f505f015b07a26cb4edca31da2_@@PEBD@Z; std::string::_Reallocate_for<_lambda_a132b9f505f015b07a26cb4edca31da2_,char const *>(unsigned __int64,_lambda_a132b9f505f015b07a26cb4edca31da2_,char const *)
0x18001cec2  nop
0x18001cec3  mov     rdx, [rbp+80h+uBytes]; uBytes
0x18001cec7  mov     ecx, 40h ; '@'; uFlags
0x18001cecc  call    cs:__imp_LocalAlloc
0x18001ced2  mov     [r14+8], rax
0x18001ced6  test    rax, rax
0x18001ced9  jz      short loc_18001CF03
0x18001cedb  lea     rdx, [rbp+80h+Src]
0x18001cedf  cmp     [rbp+80h+var_48], 0Fh
0x18001cee4  cmova   rdx, [rbp+80h+Src]; Src
0x18001cee9  mov     r8, [rbp+80h+uBytes]; Size
0x18001ceed  mov     rcx, rax; void *
0x18001cef0  call    memcpy_0
0x18001cef5  mov     eax, dword ptr [rbp+80h+uBytes]
0x18001cef8  mov     [r14+10h], eax
0x18001cefc  mov     dword ptr [r14], 4
0x18001cf03  lea     rcx, [rbp+80h+Src]
0x18001cf07  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18001cf0c  nop
0x18001cf0d  mov     rax, [rsp+180h+var_150]
0x18001cf12  movsxd  rcx, dword ptr [rax+4]
0x18001cf16  lea     rax, ??_7?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@6B@; const std::ostringstream::`vftable'
0x18001cf1d  mov     [rsp+rcx+180h+var_150], rax
0x18001cf22  mov     rax, [rsp+180h+var_150]
0x18001cf27  movsxd  rcx, dword ptr [rax+4]
0x18001cf2b  lea     edx, [rcx-88h]
0x18001cf31  mov     [rsp+rcx+180h+var_154], edx
0x18001cf35  lea     rcx, [rsp+180h+var_148]
0x18001cf3a  call    ??1?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@UEAA@XZ; std::stringbuf::~stringbuf(void)
0x18001cf3f  lea     rcx, [rsp+180h+var_140]
0x18001cf44  call    cs:__imp_??1?$basic_ostream@DU?$char_traits@D@std@@@std@@UEAA@XZ; std::ostream::~ostream<char,std::char_traits<char>>(void)
0x18001cf4a  lea     rcx, [rbp+80h+var_C8]
0x18001cf4e  call    cs:__imp_??1?$basic_ios@DU?$char_traits@D@std@@@std@@UEAA@XZ; std::ios::~ios<char,std::char_traits<char>>(void)
0x18001cf54  xor     eax, eax
0x18001cf56  mov     rcx, [rbp+80h+var_40]
0x18001cf5a  xor     rcx, rsp; StackCookie
0x18001cf5d  call    __security_check_cookie
0x18001cf62  add     rsp, 158h
0x18001cf69  pop     r15
0x18001cf6b  pop     r14
0x18001cf6d  pop     rdi
0x18001cf6e  pop     rsi
0x18001cf6f  pop     rbx
0x18001cf70  pop     rbp
0x18001cf71  retn
```
