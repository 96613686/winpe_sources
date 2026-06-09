# UusComponent::GetComponentForSession(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::map<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::less<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const>,std::allocator<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>>> const &,std::map<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const,UusComponent,std::less<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const>,std::allocator<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const,UusComponent>>> const &)

- ea: `0x180034de8`
- end: `0x18003515a`
- name: `?GetComponentForSession@UusComponent@@SA?AV?$optional@VUusComponent@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@3@AEBV?$map@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@U?$less@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@@3@AEBV?$map@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VUusComponent@@U?$less@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VUusComponent@@@std@@@2@@3@@Z`
- size: `882`
- prototype: `__int64 __fastcall(__int64, _QWORD *, __int64 *, __int64 *)`
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180036ca8`
- `0x180036e60`

## callees

- `0x18000dc44`
- `0x18000f84c`
- `0x18001dd5c`
- `0x180028728`
- `0x180029644`
- `0x180034de8`
- `0x18003a910`
- `0x180040b90`
- `0x180042790`
- `0x1800427d0`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall UusComponent::GetComponentForSession(__int64 a1, _QWORD *a2, __int64 *a3, __int64 *a4)
{
  _QWORD *v6; // rbx
  __int128 *v8; // rcx
  __int64 v9; // r8
  char *v10; // rsi
  _QWORD *v11; // rcx
  _QWORD *v12; // r14
  signed __int64 v13; // rsi
  int v14; // r14d
  __int64 v15; // rbx
  __int64 v16; // rsi
  char v17; // al
  __int64 *v18; // rcx
  _QWORD *v19; // rsi
  char *v20; // rbx
  __int64 traits_2_unsigned_short; // rax
  unsigned __int64 v22; // rdx
  _QWORD *v23; // rax
  __int64 v24; // rbx
  __int64 v25; // rsi
  char v26; // al
  __int64 *v27; // rcx
  __int64 v29; // [rsp+20h] [rbp-A9h]
  __int128 v30; // [rsp+30h] [rbp-99h] BYREF
  __m128i si128; // [rsp+40h] [rbp-89h]
  __int128 v32; // [rsp+50h] [rbp-79h] BYREF
  __int64 v33; // [rsp+60h] [rbp-69h]
  int v34; // [rsp+68h] [rbp-61h]
  __int64 v35; // [rsp+70h] [rbp-59h]
  int v36; // [rsp+94h] [rbp-35h]
  _QWORD v37[2]; // [rsp+A0h] [rbp-29h] BYREF
  unsigned __int64 v38; // [rsp+B0h] [rbp-19h]
  unsigned __int64 v39; // [rsp+B8h] [rbp-11h]
  _BYTE v40[16]; // [rsp+C0h] [rbp-9h] BYREF
  __int64 v41; // [rsp+D0h] [rbp+7h]

  v6 = a2;
  v29 = a1;
  if ( !a2[2] )
  {
    v30 = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v30) = 0;
    v32 = 0;
    v33 = 0;
    v34 = 0;
    v35 = 0;
    std::wstring::wstring(a1, &v30);
    std::vector<enum UusCapability>::vector<enum UusCapability>(a1 + 32, &v32);
    *(_DWORD *)(a1 + 56) = v34;
    *(_QWORD *)(a1 + 64) = v35;
    *(_BYTE *)(a1 + 72) = 1;
    std::vector<enum UusCapability>::~vector<enum UusCapability>(&v32);
    v8 = &v30;
    goto LABEL_51;
  }
  std::wstring::wstring(v37, a2);
  v10 = (char *)v37;
  if ( v39 > 7 )
    v10 = (char *)v37[0];
  v11 = v6;
  if ( v6[3] > 7u )
    v11 = (_QWORD *)*v6;
  v12 = (_QWORD *)((char *)v11 + 2 * v6[2]);
  if ( v6[3] > 7u )
    v6 = (_QWORD *)*v6;
  if ( v6 != v12 )
  {
    v13 = v10 - (char *)v6;
    do
    {
      *(_WORD *)((char *)v6 + v13) = o_towlower_0(*(unsigned __int16 *)v6);
      v6 = (_QWORD *)((char *)v6 + 2);
    }
    while ( v6 != v12 );
  }
  v14 = 0;
  while ( 1 )
  {
    v15 = *a3;
    v16 = *(_QWORD *)(*a3 + 8);
    v36 = 0;
    while ( !*(_BYTE *)(v16 + 25) )
    {
      v17 = std::operator<<wchar_t>(v16 + 32, v37);
      if ( !v17 )
        v15 = v16;
      v18 = (__int64 *)(v16 + 16);
      if ( !v17 )
        v18 = (__int64 *)v16;
      v16 = *v18;
    }
    if ( *(_BYTE *)(v15 + 25) || (unsigned __int8)std::operator<<wchar_t>(v37, v15 + 32) )
      v15 = *a3;
    if ( v15 != *a3 )
      break;
    v19 = v37;
    if ( v39 > 7 )
      v19 = (_QWORD *)v37[0];
    if ( v38 )
    {
      v20 = (char *)v19 + 2 * v38;
      traits_2_unsigned_short = anonymous_namespace_::__std_find_end_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                                  v19,
                                  v20,
                                  v9,
                                  1,
                                  v29);
      if ( (char *)traits_2_unsigned_short != v20 )
      {
        v22 = (traits_2_unsigned_short - (__int64)v19) >> 1;
        if ( v22 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
        {
          if ( v38 < v22 )
            std::_String_val<std::_Simple_types<char>>::_Xran();
          v38 = (traits_2_unsigned_short - (__int64)v19) >> 1;
          v23 = v37;
          if ( v39 > 7 )
            v23 = (_QWORD *)v37[0];
          *((_WORD *)v23 + v22) = 0;
          if ( (unsigned int)++v14 <= 0xF )
            continue;
        }
      }
    }
    *(_BYTE *)(a1 + 72) = 0;
    goto LABEL_50;
  }
  std::wstring::wstring(v40, v15 + 64);
  if ( !v41 )
  {
    v30 = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v30) = 0;
    v32 = 0;
    v33 = 0;
    v34 = 0;
    v35 = 0;
    std::wstring::wstring(a1, &v30);
    std::vector<enum UusCapability>::vector<enum UusCapability>(a1 + 32, &v32);
    *(_DWORD *)(a1 + 56) = v34;
    *(_QWORD *)(a1 + 64) = v35;
    *(_BYTE *)(a1 + 72) = 1;
LABEL_36:
    std::vector<enum UusCapability>::~vector<enum UusCapability>(&v32);
    std::wstring::_Tidy_deallocate(&v30);
    goto LABEL_49;
  }
  v24 = *a4;
  v25 = *(_QWORD *)(*a4 + 8);
  v36 = 0;
  while ( !*(_BYTE *)(v25 + 25) )
  {
    v26 = std::operator<<wchar_t>(v25 + 32, v40);
    if ( !v26 )
      v24 = v25;
    v27 = (__int64 *)(v25 + 16);
    if ( !v26 )
      v27 = (__int64 *)v25;
    v25 = *v27;
  }
  if ( !*(_BYTE *)(v24 + 25) && !(unsigned __int8)std::operator<<wchar_t>(v40, v24 + 32) && v24 != *a4 )
  {
    std::wstring::wstring(&v30, v24 + 64);
    std::vector<enum UusCapability>::vector<enum UusCapability>(&v32, v24 + 96);
    v34 = *(_DWORD *)(v24 + 120);
    v35 = *(_QWORD *)(v24 + 128);
    std::wstring::wstring(a1, &v30);
    std::vector<enum UusCapability>::vector<enum UusCapability>(a1 + 32, &v32);
    *(_DWORD *)(a1 + 56) = v34;
    *(_QWORD *)(a1 + 64) = v35;
    *(_BYTE *)(a1 + 72) = 1;
    goto LABEL_36;
  }
  *(_BYTE *)(a1 + 72) = 0;
LABEL_49:
  std::wstring::_Tidy_deallocate(v40);
LABEL_50:
  v8 = (__int128 *)v37;
LABEL_51:
  std::wstring::_Tidy_deallocate(v8);
  return a1;
}

```

## disassembly

```asm
0x180034de8  mov     [rsp-8+arg_10], rbx
0x180034ded  mov     [rsp-8+arg_0], rcx
0x180034df2  push    rbp
0x180034df3  push    rsi
0x180034df4  push    rdi
0x180034df5  push    r12
0x180034df7  push    r13
0x180034df9  push    r14
0x180034dfb  push    r15
0x180034dfd  lea     rbp, [rsp-27h]
0x180034e02  sub     rsp, 0F0h
0x180034e09  mov     rax, cs:__security_cookie
0x180034e10  xor     rax, rsp
0x180034e13  mov     [rbp+57h+var_40], rax
0x180034e17  mov     r12, r9
0x180034e1a  mov     r15, r8
0x180034e1d  mov     rbx, rdx
0x180034e20  mov     rdi, rcx
0x180034e23  mov     [rsp+120h+var_100], rcx
0x180034e28  xor     r13d, r13d
0x180034e2b  cmp     [rdx+10h], r13
0x180034e2f  jnz     short loc_180034EA0
0x180034e31  xorps   xmm0, xmm0
0x180034e34  movups  [rsp+120h+var_F0], xmm0
0x180034e39  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180034e41  movdqa  [rsp+120h+var_E0], xmm1
0x180034e47  mov     word ptr [rsp+120h+var_F0], r13w
0x180034e4d  movdqa  [rbp+57h+var_D0], xmm0
0x180034e52  mov     [rbp+57h+var_C0], r13
0x180034e56  mov     [rbp+57h+var_B8], r13d
0x180034e5a  mov     [rbp+57h+var_B0], r13
0x180034e5e  mov     [rsp+120h+var_100], rcx
0x180034e63  lea     rdx, [rsp+120h+var_F0]
0x180034e68  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180034e6d  nop
0x180034e6e  lea     rcx, [rdi+20h]
0x180034e72  lea     rdx, [rbp+57h+var_D0]
0x180034e76  call    ??0?$vector@W4UusCapability@@V?$allocator@W4UusCapability@@@std@@@std@@QEAA@AEBV01@@Z; std::vector<UusCapability>::vector<UusCapability>(std::vector<UusCapability> const &)
0x180034e7b  mov     ecx, [rbp+57h+var_B8]
0x180034e7e  mov     [rdi+38h], ecx
0x180034e81  mov     rcx, [rbp+57h+var_B0]
0x180034e85  mov     [rdi+40h], rcx
0x180034e89  mov     byte ptr [rdi+48h], 1
0x180034e8d  lea     rcx, [rbp+57h+var_D0]
0x180034e91  call    ??1?$vector@W4UusCapability@@V?$allocator@W4UusCapability@@@std@@@std@@QEAA@XZ; std::vector<UusCapability>::~vector<UusCapability>(void)
0x180034e96  lea     rcx, [rsp+120h+var_F0]
0x180034e9b  jmp     loc_180035125
0x180034ea0  lea     rcx, [rbp+57h+var_80]
0x180034ea4  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180034ea9  nop
0x180034eaa  lea     rsi, [rbp+57h+var_80]
0x180034eae  cmp     [rbp+57h+var_68], 7
0x180034eb3  cmova   rsi, [rbp+57h+var_80]
0x180034eb8  mov     rcx, rbx
0x180034ebb  cmp     qword ptr [rbx+18h], 7
0x180034ec0  jbe     short loc_180034EC5
0x180034ec2  mov     rcx, [rbx]
0x180034ec5  mov     rax, [rbx+10h]
0x180034ec9  lea     r14, [rcx+rax*2]
0x180034ecd  jbe     short loc_180034ED2
0x180034ecf  mov     rbx, [rbx]
0x180034ed2  cmp     rbx, r14
0x180034ed5  jz      short loc_180034EEF
0x180034ed7  sub     rsi, rbx
0x180034eda  movzx   ecx, word ptr [rbx]
0x180034edd  call    _o_towlower_0
0x180034ee2  mov     [rbx+rsi], ax
0x180034ee6  add     rbx, 2
0x180034eea  cmp     rbx, r14
0x180034eed  jnz     short loc_180034EDA
0x180034eef  mov     r14d, r13d
0x180034ef2  mov     rbx, [r15]
0x180034ef5  mov     rsi, [rbx+8]
0x180034ef9  xor     eax, eax
0x180034efb  mov     [rbp+57h+var_8C], eax
0x180034efe  jmp     short loc_180034F1E
0x180034f00  lea     rcx, [rsi+20h]
0x180034f04  lea     rdx, [rbp+57h+var_80]
0x180034f08  call    ??$?M_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@0@Z; std::operator<<wchar_t>(std::wstring const &,std::wstring const &)
0x180034f0d  test    al, al
0x180034f0f  cmovz   rbx, rsi
0x180034f13  lea     rcx, [rsi+10h]
0x180034f17  cmovz   rcx, rsi
0x180034f1b  mov     rsi, [rcx]
0x180034f1e  cmp     [rsi+19h], r13b
0x180034f22  jz      short loc_180034F00
0x180034f24  cmp     [rbx+19h], r13b
0x180034f28  jnz     short loc_180034F3B
0x180034f2a  lea     rdx, [rbx+20h]
0x180034f2e  lea     rcx, [rbp+57h+var_80]
0x180034f32  call    ??$?M_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@0@Z; std::operator<<wchar_t>(std::wstring const &,std::wstring const &)
0x180034f37  test    al, al
0x180034f39  jz      short loc_180034F3E
0x180034f3b  mov     rbx, [r15]
0x180034f3e  cmp     rbx, [r15]
0x180034f41  jnz     loc_180034FD4
0x180034f47  lea     rsi, [rbp+57h+var_80]
0x180034f4b  cmp     [rbp+57h+var_68], 7
0x180034f50  cmova   rsi, [rbp+57h+var_80]
0x180034f55  mov     rcx, [rbp+57h+var_70]
0x180034f59  cmp     rcx, 1
0x180034f5d  jb      short loc_180034FCB
0x180034f5f  dec     rcx
0x180034f62  or      rax, 0FFFFFFFFFFFFFFFFh
0x180034f66  cmp     rcx, rax
0x180034f69  cmovb   rax, rcx
0x180034f6d  inc     rax
0x180034f70  lea     rbx, [rsi+rax*2]
0x180034f74  mov     r9d, 1
0x180034f7a  mov     rdx, rbx
0x180034f7d  mov     rcx, rsi
0x180034f80  call    _anonymous_namespace_____std_find_end_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x180034f85  mov     rdx, rax
0x180034f88  cmp     rax, rbx
0x180034f8b  jz      short loc_180034FCB
0x180034f8d  sub     rdx, rsi
0x180034f90  sar     rdx, 1
0x180034f93  lea     rcx, [rdx-1]
0x180034f97  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180034f9b  ja      short loc_180034FCB
0x180034f9d  cmp     [rbp+57h+var_70], rdx
0x180034fa1  jb      loc_180035154
0x180034fa7  mov     [rbp+57h+var_70], rdx
0x180034fab  lea     rax, [rbp+57h+var_80]
0x180034faf  cmp     [rbp+57h+var_68], 7
0x180034fb4  cmova   rax, [rbp+57h+var_80]
0x180034fb9  mov     [rax+rdx*2], r13w
0x180034fbe  inc     r14d
0x180034fc1  cmp     r14d, 0Fh
0x180034fc5  jbe     loc_180034EF2
0x180034fcb  mov     [rdi+48h], r13b
0x180034fcf  jmp     loc_180035121
0x180034fd4  lea     rdx, [rbx+40h]
0x180034fd8  lea     rcx, [rbp+57h+var_60]
0x180034fdc  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180034fe1  nop
0x180034fe2  cmp     [rbp+57h+var_50], r13
0x180034fe6  jnz     short loc_18003505F
0x180034fe8  xorps   xmm0, xmm0
0x180034feb  movups  [rsp+120h+var_F0], xmm0
0x180034ff0  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180034ff8  movdqa  [rsp+120h+var_E0], xmm1
0x180034ffe  mov     word ptr [rsp+120h+var_F0], r13w
0x180035004  movdqa  [rbp+57h+var_D0], xmm0
0x180035009  mov     [rbp+57h+var_C0], r13
0x18003500d  mov     [rbp+57h+var_B8], r13d
0x180035011  mov     [rbp+57h+var_B0], r13
0x180035015  mov     [rsp+120h+var_100], rdi
0x18003501a  lea     rdx, [rsp+120h+var_F0]
0x18003501f  mov     rcx, rdi
0x180035022  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180035027  nop
0x180035028  lea     rcx, [rdi+20h]
0x18003502c  lea     rdx, [rbp+57h+var_D0]
0x180035030  call    ??0?$vector@W4UusCapability@@V?$allocator@W4UusCapability@@@std@@@std@@QEAA@AEBV01@@Z; std::vector<UusCapability>::vector<UusCapability>(std::vector<UusCapability> const &)
0x180035035  mov     eax, [rbp+57h+var_B8]
0x180035038  mov     [rdi+38h], eax
0x18003503b  mov     rax, [rbp+57h+var_B0]
0x18003503f  mov     [rdi+40h], rax
0x180035043  mov     byte ptr [rdi+48h], 1
0x180035047  lea     rcx, [rbp+57h+var_D0]
0x18003504b  call    ??1?$vector@W4UusCapability@@V?$allocator@W4UusCapability@@@std@@@std@@QEAA@XZ; std::vector<UusCapability>::~vector<UusCapability>(void)
0x180035050  lea     rcx, [rsp+120h+var_F0]
0x180035055  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003505a  jmp     loc_180035117
0x18003505f  mov     rbx, [r12]
0x180035063  mov     rsi, [rbx+8]
0x180035067  xor     eax, eax
0x180035069  mov     [rbp+57h+var_8C], eax
0x18003506c  jmp     short loc_18003508C
0x18003506e  lea     rcx, [rsi+20h]
0x180035072  lea     rdx, [rbp+57h+var_60]
0x180035076  call    ??$?M_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@0@Z; std::operator<<wchar_t>(std::wstring const &,std::wstring const &)
0x18003507b  test    al, al
0x18003507d  cmovz   rbx, rsi
0x180035081  lea     rcx, [rsi+10h]
0x180035085  cmovz   rcx, rsi
0x180035089  mov     rsi, [rcx]
0x18003508c  cmp     [rsi+19h], r13b
0x180035090  jz      short loc_18003506E
0x180035092  cmp     [rbx+19h], r13b
0x180035096  jnz     short loc_180035113
0x180035098  lea     rdx, [rbx+20h]
0x18003509c  lea     rcx, [rbp+57h+var_60]
0x1800350a0  call    ??$?M_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@0@Z; std::operator<<wchar_t>(std::wstring const &,std::wstring const &)
0x1800350a5  test    al, al
0x1800350a7  jnz     short loc_180035113
0x1800350a9  cmp     rbx, [r12]
0x1800350ad  jz      short loc_180035113
0x1800350af  lea     rdx, [rbx+40h]
0x1800350b3  lea     rcx, [rsp+120h+var_F0]
0x1800350b8  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800350bd  nop
0x1800350be  lea     rdx, [rbx+60h]
0x1800350c2  lea     rcx, [rbp+57h+var_D0]
0x1800350c6  call    ??0?$vector@W4UusCapability@@V?$allocator@W4UusCapability@@@std@@@std@@QEAA@AEBV01@@Z; std::vector<UusCapability>::vector<UusCapability>(std::vector<UusCapability> const &)
0x1800350cb  mov     eax, [rbx+78h]
0x1800350ce  mov     [rbp+57h+var_B8], eax
0x1800350d1  mov     rax, [rbx+80h]
0x1800350d8  mov     [rbp+57h+var_B0], rax
0x1800350dc  mov     [rsp+120h+var_100], rdi
0x1800350e1  lea     rdx, [rsp+120h+var_F0]
0x1800350e6  mov     rcx, rdi
0x1800350e9  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800350ee  nop
0x1800350ef  lea     rcx, [rdi+20h]
0x1800350f3  lea     rdx, [rbp+57h+var_D0]
0x1800350f7  call    ??0?$vector@W4UusCapability@@V?$allocator@W4UusCapability@@@std@@@std@@QEAA@AEBV01@@Z; std::vector<UusCapability>::vector<UusCapability>(std::vector<UusCapability> const &)
0x1800350fc  mov     eax, [rbp+57h+var_B8]
0x1800350ff  mov     [rdi+38h], eax
0x180035102  mov     rax, [rbp+57h+var_B0]
0x180035106  mov     [rdi+40h], rax
0x18003510a  mov     byte ptr [rdi+48h], 1
0x18003510e  jmp     loc_180035047
0x180035113  mov     [rdi+48h], r13b
0x180035117  lea     rcx, [rbp+57h+var_60]
0x18003511b  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180035120  nop
0x180035121  lea     rcx, [rbp+57h+var_80]
0x180035125  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003512a  mov     rax, rdi
0x18003512d  mov     rcx, [rbp+57h+var_40]
0x180035131  xor     rcx, rsp; StackCookie
0x180035134  call    __security_check_cookie
0x180035139  mov     rbx, [rsp+120h+arg_10]
0x180035141  add     rsp, 0F0h
0x180035148  pop     r15
0x18003514a  pop     r14
0x18003514c  pop     r13
0x18003514e  pop     r12
0x180035150  pop     rdi
0x180035151  pop     rsi
0x180035152  pop     rbp
0x180035153  retn
0x180035154  call    ?_Xran@?$_String_val@U?$_Simple_types@D@std@@@std@@SAXXZ; std::_String_val<std::_Simple_types<char>>::_Xran(void)
```
