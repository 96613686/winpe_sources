# std::_Builder2<ushort const *,ushort,std::regex_traits<ushort>>::_Add_equiv(ushort const *,ushort const *)

- ea: `0x14005d470`
- end: `0x14005d7d0`
- name: `?_Add_equiv@?$_Builder2@PEBGGV?$regex_traits@G@std@@@std@@QEAAXPEBG0@Z`
- size: `864`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x14005ed70`

## callees

- `0x140005530`
- `0x1400057f0`
- `0x1400076c8`
- `0x140009858`
- `0x14000ccac`
- `0x1400200b0`
- `0x14005d470`
- `0x14005e4e0`
- `0x14005ff2c`

## import_xrefs

- `msvcp_win!?_Xregex_error@std@@YAXW4error_type@regex_constants@1@@Z` at `0x14005d7c9`
- `msvcp_win!?_Xregex_error@std@@YAXW4error_type@regex_constants@1@@Z` at `0x14005d7c9`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x14005d4e9`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x14005d607`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x14005d4e9`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x14005d607`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x14005d4fd`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x14005d511`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x14005d61b`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x14005d62f`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x14005d4fd`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x14005d511`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x14005d61b`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x14005d62f`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall std::_Builder2<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>::_Add_equiv(
        char *a1,
        _BYTE *a2,
        _BYTE *a3)
{
  unsigned int v5; // esi
  __int64 v6; // r13
  __int64 v7; // r14
  __int64 v8; // rbx
  __int64 v9; // r14
  wchar_t **v10; // rcx
  unsigned __int64 v11; // rax
  unsigned int v12; // edi
  char *v13; // r12
  _QWORD *v14; // rcx
  int v15; // esi
  __int64 v16; // r15
  __int64 v17; // rbx
  __int128 *v18; // r14
  __int64 v19; // r15
  wchar_t **v20; // rcx
  size_t v21; // rax
  const wchar_t *v22; // rdx
  const wchar_t *v23; // rcx
  bool v24; // bl
  __int64 v25; // rcx
  _OWORD *v26; // rdx
  unsigned __int64 v27; // r9
  __int16 v29[2]; // [rsp+30h] [rbp-69h] BYREF
  int v30; // [rsp+34h] [rbp-65h]
  char *v31; // [rsp+38h] [rbp-61h]
  _BYTE *v32; // [rsp+40h] [rbp-59h]
  const void *v33; // [rsp+48h] [rbp-51h]
  wchar_t *S1[2]; // [rsp+50h] [rbp-49h] BYREF
  size_t N; // [rsp+60h] [rbp-39h]
  unsigned __int64 v36; // [rsp+68h] [rbp-31h]
  wchar_t *S2[2]; // [rsp+70h] [rbp-29h] BYREF
  size_t v38; // [rsp+80h] [rbp-19h]
  unsigned __int64 v39; // [rsp+88h] [rbp-11h]
  __int128 v40; // [rsp+90h] [rbp-9h] BYREF
  size_t v41; // [rsp+A0h] [rbp+7h]
  unsigned __int64 v42; // [rsp+A8h] [rbp+Fh]

  v32 = a3;
  v33 = a2;
  v31 = a1;
  *(_OWORD *)S2 = 0;
  v38 = 0;
  v39 = 7;
  LOWORD(S2[0]) = 0;
  v5 = 1;
  v30 = 1;
  if ( a2 == a3 )
    goto LABEL_39;
  v6 = *((_QWORD *)a1 + 1);
  v7 = **((_QWORD **)a1 + 3);
  v8 = __RTtypeid(v7) + 8;
  if ( !(unsigned int)__std_type_info_compare(v8, &qword_1400F43F0)
    || !(unsigned int)__std_type_info_compare(v8, &qword_1400F4420) )
  {
    *(_OWORD *)S1 = 0;
    N = 0;
    v36 = 0;
    std::wstring::_Construct<1,unsigned short const *>((char **)S1, a2, (a3 - a2) >> 1);
    if ( v38 < N )
    {
      v9 = v7 + 16;
      do
      {
        std::wstring::resize(S2);
        v10 = S2;
        if ( v39 > 7 )
          v10 = (wchar_t **)S2[0];
        v11 = _std_regex_transform_primary_wchar_t(v10, v9);
      }
      while ( v11 != -1 && v38 < v11 );
    }
    std::wstring::resize(S2);
    std::wstring::~wstring((char **)S1);
  }
  if ( !v38 )
  {
LABEL_39:
    std::_Xregex_error(0);
    JUMPOUT(0x14005D7CFLL);
  }
  v12 = 0;
  v13 = v31;
  do
  {
    v29[0] = v12;
    v14 = (_QWORD *)*((_QWORD *)v13 + 3);
    *(_OWORD *)S1 = 0;
    N = 0;
    v36 = 7;
    LOWORD(S1[0]) = 0;
    v15 = v5 | 2;
    v30 = v15;
    v16 = *v14;
    v17 = __RTtypeid(*v14) + 8;
    if ( !(unsigned int)__std_type_info_compare(v17, &qword_1400F43F0)
      || !(unsigned int)__std_type_info_compare(v17, &qword_1400F4420) )
    {
      v40 = 0;
      v41 = 0;
      v42 = 0;
      std::wstring::_Construct<1,unsigned short const *>((char **)&v40, v29, 1u);
      v18 = &v40;
      if ( v42 > 7 )
        v18 = (__int128 *)v40;
      v31 = (char *)v18 + 2 * v41;
      if ( N < v41 )
      {
        v19 = v16 + 16;
        do
        {
          std::wstring::resize(S1);
          v20 = S1;
          if ( v36 > 7 )
            v20 = (wchar_t **)S1[0];
          v21 = _std_regex_transform_primary_wchar_t(v20, v19);
        }
        while ( v21 != -1 && N < v21 );
      }
      std::wstring::resize(S1);
      std::wstring::~wstring((char **)&v40);
    }
    v22 = (const wchar_t *)S2;
    if ( v39 > 7 )
      v22 = S2[0];
    v23 = (const wchar_t *)S1;
    if ( v36 > 7 )
      v23 = S1[0];
    if ( N == v38 )
    {
      if ( N )
        v24 = wmemcmp(v23, v22, N) == 0;
      else
        v24 = 1;
    }
    else
    {
      v24 = 0;
    }
    v5 = v15 & 0xFFFFFFFD;
    v30 = v5;
    std::wstring::~wstring((char **)S1);
    if ( v24 )
    {
      v26 = *(_OWORD **)(v6 + 40);
      if ( !v26 )
      {
        v26 = operator new(0x20u);
        *v26 = 0;
        v26[1] = 0;
        *(_QWORD *)(v6 + 40) = v26;
      }
      v27 = (unsigned __int64)v12 >> 3;
      v25 = *((unsigned __int8 *)v26 + v27);
      LODWORD(v25) = v25 | (1 << (v12 & 7));
      *((_BYTE *)v26 + v27) = v25;
    }
    ++v12;
  }
  while ( v12 < 0x100 );
  std::_Builder2<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>::_Char_to_elts(
    v25,
    v33,
    v32,
    v6 + 72);
  return std::wstring::~wstring((char **)S2);
}

```

## disassembly

```asm
0x14005d470  mov     [rsp-8+arg_18], rbx
0x14005d475  push    rbp
0x14005d476  push    rsi
0x14005d477  push    rdi
0x14005d478  push    r12
0x14005d47a  push    r13
0x14005d47c  push    r14
0x14005d47e  push    r15
0x14005d480  lea     rbp, [rsp-27h]
0x14005d485  sub     rsp, 0C0h
0x14005d48c  mov     rax, cs:__security_cookie
0x14005d493  xor     rax, rsp
0x14005d496  mov     [rbp+57h+var_40], rax
0x14005d49a  mov     rdi, r8
0x14005d49d  mov     [rbp+57h+var_B0], r8
0x14005d4a1  mov     r12, rdx
0x14005d4a4  mov     [rbp+57h+var_A8], rdx
0x14005d4a8  mov     [rbp+57h+var_B8], rcx
0x14005d4ac  xor     r15d, r15d
0x14005d4af  mov     [rbp+57h+var_BC], r15d
0x14005d4b3  xorps   xmm0, xmm0
0x14005d4b6  movups  xmmword ptr [rbp+57h+S2], xmm0
0x14005d4ba  mov     [rbp+57h+var_70], r15
0x14005d4be  mov     [rbp+57h+var_68], 7
0x14005d4c6  mov     word ptr [rbp+57h+S2], r15w
0x14005d4cb  lea     esi, [r15+1]
0x14005d4cf  mov     [rbp+57h+var_BC], esi
0x14005d4d2  cmp     rdx, r8
0x14005d4d5  jz      loc_14005D7C7
0x14005d4db  mov     r13, [rcx+8]
0x14005d4df  mov     rax, [rcx+18h]
0x14005d4e3  mov     r14, [rax]
0x14005d4e6  mov     rcx, r14
0x14005d4e9  call    cs:__imp___RTtypeid
0x14005d4ef  lea     rbx, [rax+8]
0x14005d4f3  lea     rdx, qword_1400F43F0
0x14005d4fa  mov     rcx, rbx
0x14005d4fd  call    cs:__imp___std_type_info_compare
0x14005d503  test    eax, eax
0x14005d505  jz      short loc_14005D51F
0x14005d507  lea     rdx, qword_1400F4420
0x14005d50e  mov     rcx, rbx
0x14005d511  call    cs:__imp___std_type_info_compare
0x14005d517  test    eax, eax
0x14005d519  jnz     loc_14005D5C4
0x14005d51f  xorps   xmm0, xmm0
0x14005d522  movups  xmmword ptr [rbp+57h+S1], xmm0
0x14005d526  mov     [rbp+57h+N], r15
0x14005d52a  mov     [rbp+57h+var_88], r15
0x14005d52e  mov     r8, rdi
0x14005d531  sub     r8, r12
0x14005d534  sar     r8, 1
0x14005d537  mov     rdx, r12
0x14005d53a  lea     rcx, [rbp+57h+S1]
0x14005d53e  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14005d543  nop
0x14005d544  lea     rdi, [rbp+57h+S1]
0x14005d548  cmp     [rbp+57h+var_88], 7
0x14005d54d  cmova   rdi, [rbp+57h+S1]
0x14005d552  mov     rbx, [rbp+57h+N]
0x14005d556  lea     r15, [rdi+rbx*2]
0x14005d55a  cmp     [rbp+57h+var_70], rbx
0x14005d55e  jnb     short loc_14005D5AE
0x14005d560  add     r14, 10h
0x14005d564  mov     rdx, rbx
0x14005d567  lea     rcx, [rbp+57h+S2]; Src
0x14005d56b  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x14005d570  lea     rax, [rbp+57h+S2]
0x14005d574  cmp     [rbp+57h+var_68], 7
0x14005d579  cmova   rax, [rbp+57h+S2]
0x14005d57e  lea     rdx, [rax+rbx*2]
0x14005d582  lea     rcx, [rbp+57h+S2]
0x14005d586  cmova   rcx, [rbp+57h+S2]; void *
0x14005d58b  mov     [rsp+0F0h+var_D0], r14; __int64
0x14005d590  mov     r9, r15
0x14005d593  mov     r8, rdi
0x14005d596  call    __std_regex_transform_primary_wchar_t
0x14005d59b  mov     rbx, rax
0x14005d59e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14005d5a2  jz      short loc_14005D5AC
0x14005d5a4  cmp     [rbp+57h+var_70], rax
0x14005d5a8  jb      short loc_14005D564
0x14005d5aa  jmp     short loc_14005D5AE
0x14005d5ac  xor     ebx, ebx
0x14005d5ae  mov     rdx, rbx
0x14005d5b1  lea     rcx, [rbp+57h+S2]; Src
0x14005d5b5  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x14005d5ba  nop
0x14005d5bb  lea     rcx, [rbp+57h+S1]
0x14005d5bf  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005d5c4  cmp     [rbp+57h+var_70], 0
0x14005d5c9  jz      loc_14005D7C7
0x14005d5cf  xor     edi, edi
0x14005d5d1  mov     r12, [rbp+57h+var_B8]
0x14005d5d5  mov     [rbp+57h+var_C0], di
0x14005d5d9  mov     rcx, [r12+18h]
0x14005d5de  xorps   xmm0, xmm0
0x14005d5e1  movups  xmmword ptr [rbp+57h+S1], xmm0
0x14005d5e5  mov     [rbp+57h+N], 0
0x14005d5ed  mov     [rbp+57h+var_88], 7
0x14005d5f5  xor     eax, eax
0x14005d5f7  mov     word ptr [rbp+57h+S1], ax
0x14005d5fb  or      esi, 2
0x14005d5fe  mov     [rbp+57h+var_BC], esi
0x14005d601  mov     r15, [rcx]
0x14005d604  mov     rcx, r15
0x14005d607  call    cs:__imp___RTtypeid
0x14005d60d  lea     rbx, [rax+8]
0x14005d611  lea     rdx, qword_1400F43F0
0x14005d618  mov     rcx, rbx
0x14005d61b  call    cs:__imp___std_type_info_compare
0x14005d621  test    eax, eax
0x14005d623  jz      short loc_14005D63D
0x14005d625  lea     rdx, qword_1400F4420
0x14005d62c  mov     rcx, rbx
0x14005d62f  call    cs:__imp___std_type_info_compare
0x14005d635  test    eax, eax
0x14005d637  jnz     loc_14005D6ED
0x14005d63d  xorps   xmm0, xmm0
0x14005d640  movups  [rbp+57h+var_60], xmm0
0x14005d644  mov     [rbp+57h+var_50], 0
0x14005d64c  mov     [rbp+57h+var_48], 0
0x14005d654  mov     r8d, 1
0x14005d65a  lea     rdx, [rbp+57h+var_C0]
0x14005d65e  lea     rcx, [rbp+57h+var_60]
0x14005d662  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14005d667  nop
0x14005d668  lea     r14, [rbp+57h+var_60]
0x14005d66c  cmp     [rbp+57h+var_48], 7
0x14005d671  cmova   r14, qword ptr [rbp+57h+var_60]
0x14005d676  mov     rbx, [rbp+57h+var_50]
0x14005d67a  lea     rax, [r14+rbx*2]
0x14005d67e  mov     [rbp+57h+var_B8], rax
0x14005d682  cmp     [rbp+57h+N], rbx
0x14005d686  jnb     short loc_14005D6D7
0x14005d688  add     r15, 10h
0x14005d68c  mov     rdx, rbx
0x14005d68f  lea     rcx, [rbp+57h+S1]; Src
0x14005d693  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x14005d698  lea     rax, [rbp+57h+S1]
0x14005d69c  cmp     [rbp+57h+var_88], 7
0x14005d6a1  cmova   rax, [rbp+57h+S1]
0x14005d6a6  lea     rdx, [rax+rbx*2]
0x14005d6aa  lea     rcx, [rbp+57h+S1]
0x14005d6ae  cmova   rcx, [rbp+57h+S1]; void *
0x14005d6b3  mov     [rsp+0F0h+var_D0], r15; __int64
0x14005d6b8  mov     r9, [rbp+57h+var_B8]
0x14005d6bc  mov     r8, r14
0x14005d6bf  call    __std_regex_transform_primary_wchar_t
0x14005d6c4  mov     rbx, rax
0x14005d6c7  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14005d6cb  jz      short loc_14005D6D5
0x14005d6cd  cmp     [rbp+57h+N], rax
0x14005d6d1  jb      short loc_14005D68C
0x14005d6d3  jmp     short loc_14005D6D7
0x14005d6d5  xor     ebx, ebx
0x14005d6d7  mov     rdx, rbx
0x14005d6da  lea     rcx, [rbp+57h+S1]; Src
0x14005d6de  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x14005d6e3  nop
0x14005d6e4  lea     rcx, [rbp+57h+var_60]
0x14005d6e8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005d6ed  lea     rdx, [rbp+57h+S2]
0x14005d6f1  cmp     [rbp+57h+var_68], 7
0x14005d6f6  cmova   rdx, [rbp+57h+S2]; S2
0x14005d6fb  mov     r8, [rbp+57h+N]; N
0x14005d6ff  lea     rcx, [rbp+57h+S1]
0x14005d703  cmp     [rbp+57h+var_88], 7
0x14005d708  cmova   rcx, [rbp+57h+S1]; S1
0x14005d70d  cmp     r8, [rbp+57h+var_70]
0x14005d711  jz      short loc_14005D717
0x14005d713  xor     bl, bl
0x14005d715  jmp     short loc_14005D72A
0x14005d717  test    r8, r8
0x14005d71a  jnz     short loc_14005D720
0x14005d71c  mov     bl, 1
0x14005d71e  jmp     short loc_14005D72A
0x14005d720  call    wmemcmp
0x14005d725  test    eax, eax
0x14005d727  setz    bl
0x14005d72a  and     esi, 0FFFFFFFDh
0x14005d72d  mov     [rbp+57h+var_BC], esi
0x14005d730  lea     rcx, [rbp+57h+S1]
0x14005d734  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005d739  test    bl, bl
0x14005d73b  jz      short loc_14005D777
0x14005d73d  mov     rdx, [r13+28h]
0x14005d741  test    rdx, rdx
0x14005d744  jnz     short loc_14005D75F
0x14005d746  lea     ecx, [rdx+20h]; Size
0x14005d749  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14005d74e  mov     rdx, rax
0x14005d751  xorps   xmm0, xmm0
0x14005d754  movups  xmmword ptr [rax], xmm0
0x14005d757  movups  xmmword ptr [rax+10h], xmm0
0x14005d75b  mov     [r13+28h], rax
0x14005d75f  mov     r9d, edi
0x14005d762  shr     r9, 3
0x14005d766  movzx   ecx, byte ptr [r9+rdx]
0x14005d76b  mov     eax, edi
0x14005d76d  and     eax, 7
0x14005d770  bts     ecx, eax
0x14005d773  mov     [r9+rdx], cl
0x14005d777  inc     edi
0x14005d779  cmp     edi, 100h
0x14005d77f  jb      loc_14005D5D5
0x14005d785  lea     r9, [r13+48h]
0x14005d789  mov     r8, [rbp+57h+var_B0]
0x14005d78d  mov     rdx, [rbp+57h+var_A8]
0x14005d791  call    ?_Char_to_elts@?$_Builder2@PEBGGV?$regex_traits@G@std@@@std@@AEAAXPEBG0PEAPEAU?$_Sequence@G@2@@Z; std::_Builder2<ushort const *,ushort,std::regex_traits<ushort>>::_Char_to_elts(ushort const *,ushort const *,std::_Sequence<ushort> * *)
0x14005d796  nop
0x14005d797  lea     rcx, [rbp+57h+S2]
0x14005d79b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005d7a0  mov     rcx, [rbp+57h+var_40]
0x14005d7a4  xor     rcx, rsp; StackCookie
0x14005d7a7  call    __security_check_cookie
0x14005d7ac  mov     rbx, [rsp+0F0h+arg_18]
0x14005d7b4  add     rsp, 0C0h
0x14005d7bb  pop     r15
0x14005d7bd  pop     r14
0x14005d7bf  pop     r13
0x14005d7c1  pop     r12
0x14005d7c3  pop     rdi
0x14005d7c4  pop     rsi
0x14005d7c5  pop     rbp
0x14005d7c6  retn
0x14005d7c7  xor     ecx, ecx
0x14005d7c9  call    cs:__imp_?_Xregex_error@std@@YAXW4error_type@regex_constants@1@@Z; std::_Xregex_error(std::regex_constants::error_type)
```
