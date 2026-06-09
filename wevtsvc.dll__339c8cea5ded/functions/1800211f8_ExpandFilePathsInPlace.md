# ExpandFilePathsInPlace

- ea: `0x1800211f8`
- end: `0x1800215c4`
- name: `ExpandFilePathsInPlace`
- size: `972`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `4`
- callee_count: `13`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001d268`
- `0x1800204d8`
- `0x1800bbb2c`
- `0x1800bbf34`

## callees

- `0x180004980`
- `0x180014bd0`
- `0x180017b60`
- `0x18001c320`
- `0x1800211f8`
- `0x1800215cc`
- `0x18002afa8`
- `0x18002d204`
- `0x18002d354`
- `0x18002d6dc`
- `0x18002ede4`
- `0x18006d87c`
- `0x180092008`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800213cf`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800213cf`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800214bf`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800214bf`

## pseudocode

```c
__int64 __fastcall ExpandFilePathsInPlace(void *a1)
{
  unsigned int v2; // ebx
  LPCWCH v3; // rdi
  __int64 v4; // rdx
  const WCHAR *v5; // r9
  const WCHAR *v6; // r8
  const WCHAR *v7; // rbx
  __int64 v8; // rcx
  unsigned __int64 v9; // r14
  __int64 v10; // rbx
  unsigned __int64 v11; // r12
  __int64 first_of; // rax
  const WCHAR *v13; // rdx
  __int64 v14; // r14
  const WCHAR *v15; // rcx
  unsigned int i; // esi
  unsigned __int64 v17; // rbx
  const WCHAR *v18; // r8
  unsigned __int64 v19; // rdi
  unsigned __int64 v20; // r8
  unsigned __int64 v21; // rax
  __int64 v22; // rcx
  unsigned __int64 v23; // rdx
  LPCWCH lpString1; // [rsp+30h] [rbp-49h] BYREF
  const WCHAR *v26; // [rsp+38h] [rbp-41h]
  __int64 v27; // [rsp+40h] [rbp-39h] BYREF
  __int64 v28; // [rsp+48h] [rbp-31h]
  LPCWSTR lpSrc; // [rsp+50h] [rbp-29h] BYREF
  const WCHAR *v30; // [rsp+58h] [rbp-21h]
  __int64 v31; // [rsp+60h] [rbp-19h] BYREF
  __int64 v32; // [rsp+68h] [rbp-11h]
  LPCWSTR lpFileName[2]; // [rsp+70h] [rbp-9h] BYREF
  _QWORD v34[10]; // [rsp+80h] [rbp+7h] BYREF

  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
    &lpSrc,
    a1);
  if ( byte_1801115E4 )
  {
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(&lpString1);
    ExpandEnvStringNoThrow(lpSrc);
    v3 = lpString1;
    v4 = v31;
    v5 = lpSrc;
    v6 = v30;
    v7 = v26;
    v31 = v27;
    v8 = v28;
    v28 = v32;
    lpSrc = lpString1;
    lpString1 = v5;
    v30 = v26;
    v26 = v6;
    v32 = v8;
    v27 = v4;
    if ( lpSrc == (LPCWSTR)&v27 )
    {
      v3 = (LPCWCH)&v31;
      lpSrc = (LPCWSTR)&v31;
      v7 = (const WCHAR *)&v31 + (((char *)v7 - (char *)&lpString1 - 16) >> 1);
      v30 = v7;
    }
    if ( v5 == (const WCHAR *)&v31 )
    {
      lpString1 = (LPCWCH)&v27;
      v26 = (const WCHAR *)&v27 + (((char *)v6 - (char *)&lpSrc - 16) >> 1);
    }
    v9 = 0;
    while ( 1 )
    {
      v10 = v7 - v3;
      v11 = v9;
      first_of = utl::_StringTraits<utl::char_traits<wchar_t>>::find_first_of(
                   (_DWORD)v3,
                   v10,
                   v9,
                   (unsigned int)L";,",
                   2);
      v13 = &v3[v9];
      v14 = first_of;
      if ( first_of == -1 )
        v14 = v10;
      if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                               &lpString1,
                               v13,
                               v14 - v11) )
      {
LABEL_52:
        utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&lpString1);
        utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&lpSrc);
        return 14;
      }
      v15 = lpString1;
      if ( lpString1 != v26 )
      {
        for ( i = 0; i < 6; ++i )
        {
          v17 = (unsigned __int64)i << 6;
          if ( *(__int64 *)((char *)&qword_1801112A0[4] + v17) != *(__int64 *)((char *)&qword_1801112A0[5] + v17) )
          {
            v18 = *(const WCHAR **)((char *)qword_1801112A0 + v17);
            v19 = (*(__int64 *)((char *)&qword_1801112A0[1] + v17) - (__int64)v18) >> 1;
            if ( v26 - v15 > v19 )
            {
              if ( CompareStringOrdinal(v15, v19, v18, v19, 1) == 2 )
              {
                utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpFileName);
                v20 = v19
                    + ((*(__int64 *)((char *)&qword_1801112A0[5] + v17) - *(__int64 *)((char *)&qword_1801112A0[4] + v17)) >> 1);
                if ( (_QWORD *)lpFileName[0] == v34 )
                  v21 = 7;
                else
                  v21 = (__int64)(v34[0] - (unsigned __int64)lpFileName[0]) >> 1;
                if ( v20 > v21 )
                {
                  if ( (_QWORD *)lpFileName[0] == v34 )
                    v22 = 7;
                  else
                    v22 = (__int64)(v34[0] - (unsigned __int64)lpFileName[0]) >> 1;
                  v23 = v19
                      + ((*(__int64 *)((char *)&qword_1801112A0[5] + v17)
                        - *(__int64 *)((char *)&qword_1801112A0[4] + v17)) >> 1);
                  if ( 2 * v22 + 1 >= v20 )
                    v23 = 2 * v22 + 1;
                  if ( v23 > 0x3FFFFFFFFFFFFFF7LL )
                    v23 = 0x3FFFFFFFFFFFFFF7LL;
                  if ( v20 > v23
                    || !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_GrowTo(lpFileName) )
                  {
                    goto LABEL_46;
                  }
                }
                if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                                         lpFileName,
                                         *(__int64 *)((char *)&qword_1801112A0[4] + v17),
                                         (*(__int64 *)((char *)&qword_1801112A0[5] + v17)
                                        - *(__int64 *)((char *)&qword_1801112A0[4] + v17)) >> 1)
                  || !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(lpFileName) )
                {
LABEL_46:
                  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpFileName);
                  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&lpString1);
                  v2 = 14;
                  goto LABEL_47;
                }
                if ( GetFileAttributesW(lpFileName[0]) != -1 )
                  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::swap(
                    &lpString1,
                    lpFileName);
                if ( (_QWORD *)lpFileName[0] != v34 )
                  operator delete((void *)lpFileName[0]);
                break;
              }
              v15 = lpString1;
            }
          }
        }
      }
      if ( v11
        && !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(
                               a1,
                               59) )
      {
        break;
      }
      if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(a1) )
        goto LABEL_52;
      v7 = v30;
      v9 = v14 + 1;
      v3 = lpSrc;
      if ( v9 >= v30 - lpSrc )
      {
        utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&lpString1);
        utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&lpSrc);
        return 0;
      }
    }
    if ( lpString1 != (LPCWCH)&v27 )
      operator delete((void *)lpString1);
    if ( lpSrc != (LPCWSTR)&v31 )
      operator delete((void *)lpSrc);
    return 14;
  }
  else
  {
    v2 = 1359;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_5b779035add530f74e9405630361780f_Traceguids, 1359);
    }
LABEL_47:
    utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&lpSrc);
    return v2;
  }
}

```

## disassembly

```asm
0x1800211f8  push    rbp
0x1800211fa  push    rbx
0x1800211fb  push    rsi
0x1800211fc  push    rdi
0x1800211fd  push    r12
0x1800211ff  push    r13
0x180021201  push    r14
0x180021203  push    r15
0x180021205  lea     rbp, [rsp-1Fh]
0x18002120a  sub     rsp, 98h
0x180021211  mov     rdx, rcx
0x180021214  mov     r15, rcx
0x180021217  lea     rcx, [rbp+57h+lpSrc]
0x18002121b  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@$$QEAV01@@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &&)
0x180021220  cmp     cs:byte_1801115E4, 0
0x180021227  jnz     short loc_180021279
0x180021229  mov     rcx, cs:WPP_GLOBAL_Control
0x180021230  lea     rax, WPP_GLOBAL_Control
0x180021237  mov     ebx, 54Fh
0x18002123c  cmp     rcx, rax
0x18002123f  jz      loc_18002156A
0x180021245  test    dword ptr [rcx+1Ch], 10000h
0x18002124c  jz      loc_18002156A
0x180021252  cmp     byte ptr [rcx+19h], 2
0x180021256  jb      loc_18002156A
0x18002125c  mov     rcx, [rcx+10h]
0x180021260  lea     r8, WPP_5b779035add530f74e9405630361780f_Traceguids
0x180021267  mov     edx, 0Ah
0x18002126c  mov     r9d, ebx
0x18002126f  call    WPP_SF_d
0x180021274  jmp     loc_18002156A
0x180021279  lea     rcx, [rbp+57h+lpString1]; void *
0x18002127d  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180021282  mov     rcx, [rbp+57h+lpSrc]; lpSrc
0x180021286  lea     rdx, [rbp+57h+lpString1]
0x18002128a  call    ?ExpandEnvStringNoThrow@@YAKPEB_WAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; ExpandEnvStringNoThrow(wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x18002128f  mov     rcx, [rbp+57h+var_90]
0x180021293  mov     rax, [rbp+57h+var_68]
0x180021297  mov     rdi, [rbp+57h+lpString1]
0x18002129b  mov     rdx, [rbp+57h+var_70]
0x18002129f  mov     r9, [rbp+57h+lpSrc]
0x1800212a3  mov     r8, [rbp+57h+var_78]
0x1800212a7  mov     rbx, [rbp+57h+var_98]
0x1800212ab  mov     [rbp+57h+var_70], rcx
0x1800212af  mov     rcx, [rbp+57h+var_88]
0x1800212b3  mov     [rbp+57h+var_88], rax
0x1800212b7  lea     rax, [rbp+57h+var_90]
0x1800212bb  mov     [rbp+57h+lpSrc], rdi
0x1800212bf  mov     [rbp+57h+lpString1], r9
0x1800212c3  mov     [rbp+57h+var_78], rbx
0x1800212c7  mov     [rbp+57h+var_98], r8
0x1800212cb  mov     [rbp+57h+var_68], rcx
0x1800212cf  mov     [rbp+57h+var_90], rdx
0x1800212d3  cmp     rdi, rax
0x1800212d6  jnz     short loc_1800212F7
0x1800212d8  lea     rax, [rbp+57h+lpString1]
0x1800212dc  sub     rbx, rax
0x1800212df  lea     rdi, [rbp+57h+var_70]
0x1800212e3  sub     rbx, 10h
0x1800212e7  mov     [rbp+57h+lpSrc], rdi
0x1800212eb  sar     rbx, 1
0x1800212ee  lea     rbx, [rbp+rbx*2+57h+var_70]
0x1800212f3  mov     [rbp+57h+var_78], rbx
0x1800212f7  lea     rax, [rbp+57h+var_70]
0x1800212fb  cmp     r9, rax
0x1800212fe  jnz     short loc_180021322
0x180021300  lea     rax, [rbp+57h+var_90]
0x180021304  mov     [rbp+57h+lpString1], rax
0x180021308  lea     rax, [rbp+57h+lpSrc]
0x18002130c  sub     r8, rax
0x18002130f  lea     rax, [rbp+57h+var_90]
0x180021313  sub     r8, 10h
0x180021317  sar     r8, 1
0x18002131a  lea     rax, [rax+r8*2]
0x18002131e  mov     [rbp+57h+var_98], rax
0x180021322  xor     r14d, r14d
0x180021325  lea     r13, qword_1801112A0
0x18002132c  mov     r9, cs:off_1800DE0C8; ";,"
0x180021333  sub     rbx, rdi
0x180021336  sar     rbx, 1
0x180021339  mov     r8, r14
0x18002133c  mov     rdx, rbx
0x18002133f  mov     qword ptr [rsp+0D0h+bIgnoreCase], 2
0x180021348  mov     rcx, rdi
0x18002134b  mov     r12, r14
0x18002134e  call    ?find_first_of@?$_StringTraits@U?$char_traits@_W@utl@@@utl@@SA_KPEB_W_K101@Z; utl::_StringTraits<utl::char_traits<wchar_t>>::find_first_of(wchar_t const *,unsigned __int64,unsigned __int64,wchar_t const *,unsigned __int64)
0x180021353  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180021357  lea     rdx, [rdi+r12*2]
0x18002135b  mov     r14, rax
0x18002135e  lea     rcx, [rbp+57h+lpString1]
0x180021362  cmovz   r14, rbx
0x180021366  mov     r8, r14
0x180021369  sub     r8, r12
0x18002136c  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x180021371  test    al, al
0x180021373  jz      loc_180021599
0x180021379  mov     rcx, [rbp+57h+lpString1]; lpString1
0x18002137d  cmp     rcx, [rbp+57h+var_98]
0x180021381  jz      loc_1800214ED
0x180021387  xor     esi, esi
0x180021389  cmp     esi, 6
0x18002138c  jnb     loc_1800214ED
0x180021392  mov     ebx, esi
0x180021394  shl     rbx, 6
0x180021398  mov     rax, [rbx+r13+28h]
0x18002139d  cmp     [rbx+r13+20h], rax
0x1800213a2  jz      short loc_1800213DE
0x1800213a4  mov     r8, [rbx+r13]; lpString2
0x1800213a8  mov     rdi, [rbx+r13+8]
0x1800213ad  mov     rax, [rbp+57h+var_98]
0x1800213b1  sub     rdi, r8
0x1800213b4  sub     rax, rcx
0x1800213b7  sar     rdi, 1
0x1800213ba  sar     rax, 1
0x1800213bd  cmp     rax, rdi
0x1800213c0  jbe     short loc_1800213DE
0x1800213c2  mov     r9d, edi; cchCount2
0x1800213c5  mov     [rsp+0D0h+bIgnoreCase], 1; bIgnoreCase
0x1800213cd  mov     edx, edi; cchCount1
0x1800213cf  call    cs:__imp_CompareStringOrdinal
0x1800213d5  cmp     eax, 2
0x1800213d8  jz      short loc_1800213E2
0x1800213da  mov     rcx, [rbp+57h+lpString1]
0x1800213de  inc     esi
0x1800213e0  jmp     short loc_180021389
0x1800213e2  lea     rcx, [rbp+57h+lpFileName]; void *
0x1800213e6  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800213eb  mov     r8, [rbx+r13+28h]
0x1800213f0  lea     rax, [rbp+57h+var_50]
0x1800213f4  sub     r8, [rbx+r13+20h]
0x1800213f9  mov     rdx, [rbp+57h+lpFileName]
0x1800213fd  mov     rcx, [rbp+57h+var_50]
0x180021401  sar     r8, 1
0x180021404  add     r8, rdi
0x180021407  cmp     rdx, rax
0x18002140a  jnz     short loc_180021413
0x18002140c  mov     eax, 7
0x180021411  jmp     short loc_18002141C
0x180021413  mov     rax, rcx
0x180021416  sub     rax, rdx
0x180021419  sar     rax, 1
0x18002141c  cmp     r8, rax
0x18002141f  jbe     short loc_180021474
0x180021421  lea     rax, [rbp+57h+var_50]
0x180021425  cmp     rdx, rax
0x180021428  jnz     short loc_180021431
0x18002142a  mov     ecx, 7
0x18002142f  jmp     short loc_180021437
0x180021431  sub     rcx, rdx
0x180021434  sar     rcx, 1
0x180021437  lea     rax, ds:1[rcx*2]
0x18002143f  mov     rsi, 3FFFFFFFFFFFFFF7h
0x180021449  cmp     rax, r8
0x18002144c  mov     rdx, r8
0x18002144f  cmovnb  rdx, rax
0x180021453  cmp     rdx, rsi
0x180021456  cmova   rdx, rsi
0x18002145a  cmp     r8, rdx
0x18002145d  ja      loc_180021553
0x180021463  lea     rcx, [rbp+57h+lpFileName]
0x180021467  call    ?_GrowTo@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAA_N_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_GrowTo(unsigned __int64)
0x18002146c  test    al, al
0x18002146e  jz      loc_180021553
0x180021474  mov     rdx, [rbx+r13+20h]
0x180021479  lea     rcx, [rbp+57h+lpFileName]
0x18002147d  mov     r8, [rbx+r13+28h]
0x180021482  sub     r8, rdx
0x180021485  sar     r8, 1
0x180021488  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x18002148d  test    al, al
0x18002148f  jz      loc_180021553
0x180021495  mov     rax, [rbp+57h+lpString1]
0x180021499  lea     rcx, [rbp+57h+lpFileName]
0x18002149d  mov     r8, [rbp+57h+var_98]
0x1800214a1  sub     r8, rax
0x1800214a4  sar     r8, 1
0x1800214a7  sub     r8, rdi
0x1800214aa  lea     rdx, [rax+rdi*2]
0x1800214ae  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x1800214b3  test    al, al
0x1800214b5  jz      loc_180021553
0x1800214bb  mov     rcx, [rbp+57h+lpFileName]; lpFileName
0x1800214bf  call    cs:__imp_GetFileAttributesW
0x1800214c5  cmp     eax, 0FFFFFFFFh
0x1800214c8  jz      short loc_1800214D7
0x1800214ca  lea     rdx, [rbp+57h+lpFileName]
0x1800214ce  lea     rcx, [rbp+57h+lpString1]
0x1800214d2  call    ?swap@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAAXAEAV12@@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::swap(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x1800214d7  mov     rcx, [rbp+57h+lpFileName]; void *
0x1800214db  lea     rax, [rbp+57h+var_50]
0x1800214df  cmp     rcx, rax
0x1800214e2  jz      short loc_1800214E9
0x1800214e4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800214e9  mov     rcx, [rbp+57h+lpString1]
0x1800214ed  test    r12, r12
0x1800214f0  jz      short loc_180021507
0x1800214f2  mov     edx, 3Bh ; ';'
0x1800214f7  mov     rcx, r15
0x1800214fa  call    ?push_back@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(wchar_t)
0x1800214ff  mov     rcx, [rbp+57h+lpString1]; void *
0x180021503  test    al, al
0x180021505  jz      short loc_180021577
0x180021507  mov     r8, [rbp+57h+var_98]
0x18002150b  mov     rdx, rcx
0x18002150e  sub     r8, rcx
0x180021511  mov     rcx, r15
0x180021514  sar     r8, 1
0x180021517  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x18002151c  test    al, al
0x18002151e  jz      short loc_180021599
0x180021520  mov     rbx, [rbp+57h+var_78]
0x180021524  inc     r14
0x180021527  mov     rdi, [rbp+57h+lpSrc]
0x18002152b  mov     rax, rbx
0x18002152e  sub     rax, rdi
0x180021531  sar     rax, 1
0x180021534  cmp     r14, rax
0x180021537  jb      loc_18002132C
0x18002153d  lea     rcx, [rbp+57h+lpString1]; void *
0x180021541  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180021546  lea     rcx, [rbp+57h+lpSrc]; void *
0x18002154a  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18002154f  xor     eax, eax
0x180021551  jmp     short loc_1800215B0
0x180021553  lea     rcx, [rbp+57h+lpFileName]; void *
0x180021557  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18002155c  lea     rcx, [rbp+57h+lpString1]; void *
0x180021560  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180021565  mov     ebx, 0Eh
0x18002156a  lea     rcx, [rbp+57h+lpSrc]; void *
0x18002156e  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180021573  mov     eax, ebx
0x180021575  jmp     short loc_1800215B0
0x180021577  lea     rax, [rbp+57h+var_90]
0x18002157b  cmp     rcx, rax
0x18002157e  jz      short loc_180021585
0x180021580  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180021585  mov     rcx, [rbp+57h+lpSrc]; void *
0x180021589  lea     rax, [rbp+57h+var_70]
0x18002158d  cmp     rcx, rax
0x180021590  jz      short loc_1800215AB
0x180021592  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180021597  jmp     short loc_1800215AB
0x180021599  lea     rcx, [rbp+57h+lpString1]; void *
0x18002159d  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800215a2  lea     rcx, [rbp+57h+lpSrc]; void *
0x1800215a6  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800215ab  mov     eax, 0Eh
0x1800215b0  add     rsp, 98h
0x1800215b7  pop     r15
0x1800215b9  pop     r14
0x1800215bb  pop     r13
0x1800215bd  pop     r12
0x1800215bf  pop     rdi
0x1800215c0  pop     rsi
0x1800215c1  pop     rbx
0x1800215c2  pop     rbp
0x1800215c3  retn
```
