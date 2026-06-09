# OpenFilesFromDelimitedPath

- ea: `0x180021650`
- end: `0x18002192a`
- name: `OpenFilesFromDelimitedPath`
- size: `730`
- prototype: `__int64 __fastcall(__int64, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1800204d8`

## callees

- `0x180004a3c`
- `0x180014bd0`
- `0x180017b60`
- `0x18001c320`
- `0x1800215cc`
- `0x180021650`
- `0x18002d204`
- `0x1800338c0`
- `0x1800341a4`
- `0x180034704`
- `0x180063c88`
- `0x180089988`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002185c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002185c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800218a9`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800218a9`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180021776`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180021776`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002171f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002171f`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
__int64 __fastcall OpenFilesFromDelimitedPath(__int64 a1, _QWORD *a2, _QWORD *a3)
{
  unsigned __int64 i; // rbx
  __int64 first_of; // rax
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // r13
  unsigned int j; // r14d
  __int64 v12; // r10
  unsigned int *v13; // rax
  HMODULE v14; // r15
  HMODULE v15; // r14
  __int64 v16; // rcx
  HMODULE *v17; // rax
  unsigned int *v18; // rcx
  unsigned int v19; // eax
  unsigned int v20; // ebx
  char LastError; // al
  LPCWCH lpString2[2]; // [rsp+30h] [rbp-20h] BYREF
  char v24; // [rsp+40h] [rbp-10h] BYREF
  unsigned int v25; // [rsp+A0h] [rbp+50h] BYREF
  HMODULE Library; // [rsp+A8h] [rbp+58h] BYREF

  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpString2);
  for ( i = 0; ; i = v10 + 1 )
  {
    if ( i >= a3[1] )
    {
      v20 = 0;
      if ( *a2 == a2[1] )
        v20 = 2;
      goto LABEL_42;
    }
    first_of = utl::_StringTraits<utl::char_traits<wchar_t>>::find_first_of(*a3, a3[1], i, (unsigned int)L";,", 2);
    v10 = first_of;
    if ( first_of == -1 )
    {
      v10 = v8;
    }
    else if ( i == first_of )
    {
      continue;
    }
    if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                             lpString2,
                             v9 + 2 * i,
                             v10 - i) )
      break;
    for ( j = 0; ; ++j )
    {
      v12 = *(_QWORD *)(a1 + 24);
      if ( j >= (unsigned __int64)((*(_QWORD *)(a1 + 32) - v12) >> 5) )
      {
        Library = LoadLibraryExW(lpString2[0], 0, 0x20u);
        v14 = Library;
        v15 = Library;
        if ( !Library )
        {
          LastError = GetLastError();
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
          {
            WPP_SF_Sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              65,
              (unsigned int)&WPP_5b779035add530f74e9405630361780f_Traceguids,
              lpString2[0],
              LastError);
          }
          goto LABEL_31;
        }
        v16 = *(_QWORD *)(a1 + 40);
        if ( *(_QWORD *)(a1 + 32) != v16
          || (unsigned __int8)utl::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::_Grow(a1 + 24) )
        {
          if ( (unsigned __int8)utl::allocator_traits<utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::construct<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const &>(
                                  v16,
                                  *(_QWORD *)(a1 + 32),
                                  lpString2) )
          {
            *(_QWORD *)(a1 + 32) += 32LL;
            v17 = *(HMODULE **)(a1 + 8);
            if ( v17 != *(HMODULE **)(a1 + 16) )
            {
              v15 = 0;
              *v17 = v14;
              *(_QWORD *)(a1 + 8) += 8LL;
              Library = 0;
LABEL_23:
              v18 = (unsigned int *)a2[1];
              v19 = ((__int64)(*(_QWORD *)(a1 + 8) - *(_QWORD *)a1) >> 3) - 1;
              v25 = v19;
              if ( v18 != (unsigned int *)a2[2] )
              {
                *v18 = v19;
                a2[1] += 4LL;
                goto LABEL_31;
              }
              if ( (unsigned __int8)utl::vector<int,utl::allocator<int>>::_PushBackOne2<int>(a2, &v25) )
              {
LABEL_31:
                if ( v15 )
                  FreeLibrary(v15);
                goto LABEL_33;
              }
              *(_QWORD *)(a1 + 32) -= 32LL;
              utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(*(void **)(a1 + 32));
              *(_QWORD *)(a1 + 8) -= 8LL;
              tlx::unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),0>>::~unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),0>>(*(_QWORD *)(a1 + 8));
              tlx::unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),0>>::~unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),0>>(&Library);
              v20 = 14;
LABEL_42:
              utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpString2);
              return v20;
            }
            if ( (unsigned __int8)utl::vector<tlx::unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),0>>,utl::allocator<tlx::unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),0>>>>::_PushBackOne2<tlx::unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),0>>>(
                                    a1,
                                    &Library) )
            {
              v15 = Library;
              goto LABEL_23;
            }
            *(_QWORD *)(a1 + 32) -= 32LL;
          }
          utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(*(void **)(a1 + 32));
        }
        tlx::unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),0>>::~unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),0>>(&Library);
LABEL_14:
        utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpString2);
        return 14;
      }
      if ( CompareStringOrdinal(
             *(LPCWCH *)(32LL * j + v12),
             (__int64)(*(_QWORD *)(32LL * j + v12 + 8) - *(_QWORD *)(32LL * j + v12)) >> 1,
             lpString2[0],
             lpString2[1] - lpString2[0],
             1) == 2 )
        break;
    }
    v13 = (unsigned int *)a2[1];
    v25 = j;
    if ( v13 != (unsigned int *)a2[2] )
    {
      *v13 = j;
      a2[1] += 4LL;
      continue;
    }
    if ( !(unsigned __int8)utl::vector<int,utl::allocator<int>>::_PushBackOne2<int>(a2, &v25) )
      goto LABEL_14;
LABEL_33:
    ;
  }
  if ( (char *)lpString2[0] != &v24 )
    operator delete((void *)lpString2[0]);
  return 14;
}

```

## disassembly

```asm
0x180021650  mov     [rsp-38h+arg_0], rbx
0x180021655  push    rbp
0x180021656  push    rsi
0x180021657  push    rdi
0x180021658  push    r12
0x18002165a  push    r13
0x18002165c  push    r14
0x18002165e  push    r15
0x180021660  mov     rbp, rsp
0x180021663  sub     rsp, 50h
0x180021667  mov     rsi, rcx
0x18002166a  mov     r12, r8
0x18002166d  lea     rcx, [rbp+lpString2]; void *
0x180021671  mov     rdi, rdx
0x180021674  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180021679  mov     r14, cs:off_1800DE0C8; ";,"
0x180021680  xor     ebx, ebx
0x180021682  lea     r15d, [rbx+2]
0x180021686  cmp     rbx, [r12+8]
0x18002168b  jnb     loc_1800218FA
0x180021691  mov     rcx, [r12]
0x180021695  mov     r9, r14
0x180021698  mov     rdx, [r12+8]
0x18002169d  mov     r8, rbx
0x1800216a0  mov     qword ptr [rsp+50h+bIgnoreCase], r15
0x1800216a5  call    ?find_first_of@?$_StringTraits@U?$char_traits@_W@utl@@@utl@@SA_KPEB_W_K101@Z; utl::_StringTraits<utl::char_traits<wchar_t>>::find_first_of(wchar_t const *,unsigned __int64,unsigned __int64,wchar_t const *,unsigned __int64)
0x1800216aa  mov     r13, rax
0x1800216ad  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800216b1  jnz     short loc_1800216B8
0x1800216b3  mov     r13, rdx
0x1800216b6  jmp     short loc_1800216C1
0x1800216b8  cmp     rbx, rax
0x1800216bb  jz      loc_1800218BC
0x1800216c1  lea     rdx, [rcx+rbx*2]
0x1800216c5  mov     r8, r13
0x1800216c8  sub     r8, rbx
0x1800216cb  lea     rcx, [rbp+lpString2]
0x1800216cf  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x1800216d4  test    al, al
0x1800216d6  jz      loc_1800218E1
0x1800216dc  xor     r14d, r14d
0x1800216df  mov     r10, [rsi+18h]
0x1800216e3  mov     rax, [rsi+20h]
0x1800216e7  sub     rax, r10
0x1800216ea  mov     edx, r14d
0x1800216ed  sar     rax, 5
0x1800216f1  cmp     rdx, rax
0x1800216f4  jnb     short loc_18002176C
0x1800216f6  mov     r8, [rbp+lpString2]; lpString2
0x1800216fa  mov     r9, [rbp+var_18]
0x1800216fe  shl     rdx, 5
0x180021702  sub     r9, r8
0x180021705  sar     r9, 1; cchCount2
0x180021708  mov     [rsp+50h+bIgnoreCase], 1; bIgnoreCase
0x180021710  mov     rcx, [rdx+r10]; lpString1
0x180021714  mov     rdx, [rdx+r10+8]
0x180021719  sub     rdx, rcx
0x18002171c  sar     rdx, 1; cchCount1
0x18002171f  call    cs:__imp_CompareStringOrdinal
0x180021725  cmp     eax, r15d
0x180021728  jz      short loc_18002172F
0x18002172a  inc     r14d
0x18002172d  jmp     short loc_1800216DF
0x18002172f  mov     rax, [rdi+8]
0x180021733  mov     [rbp+arg_10], r14d
0x180021737  cmp     rax, [rdi+10h]
0x18002173b  jz      short loc_18002174A
0x18002173d  mov     [rax], r14d
0x180021740  add     qword ptr [rdi+8], 4
0x180021745  jmp     loc_1800218B5
0x18002174a  lea     rdx, [rbp+arg_10]
0x18002174e  mov     rcx, rdi
0x180021751  call    ??$_PushBackOne2@H@?$vector@HV?$allocator@H@utl@@@utl@@AEAA_N$$QEAH@Z; utl::vector<int,utl::allocator<int>>::_PushBackOne2<int>(int &&)
0x180021756  test    al, al
0x180021758  jnz     loc_1800218B5
0x18002175e  lea     rcx, [rbp+lpString2]; void *
0x180021762  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180021767  jmp     loc_1800218F3
0x18002176c  mov     rcx, [rbp+lpString2]; lpLibFileName
0x180021770  xor     edx, edx; hFile
0x180021772  lea     r8d, [rdx+20h]; dwFlags
0x180021776  call    cs:__imp_LoadLibraryExW
0x18002177c  mov     [rbp+arg_18], rax
0x180021780  mov     r15, rax
0x180021783  mov     r14, rax
0x180021786  test    rax, rax
0x180021789  jz      loc_18002185C
0x18002178f  mov     rcx, [rsi+28h]
0x180021793  cmp     [rsi+20h], rcx
0x180021797  jnz     short loc_1800217AA
0x180021799  lea     rcx, [rsi+18h]
0x18002179d  call    ?_Grow@?$vector@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@2@@utl@@AEAA_NXZ; utl::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::_Grow(void)
0x1800217a2  test    al, al
0x1800217a4  jz      loc_1800218D3
0x1800217aa  mov     rdx, [rsi+20h]
0x1800217ae  lea     r8, [rbp+lpString2]
0x1800217b2  call    ??$construct@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEBV12@@?$allocator_traits@V?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@utl@@@utl@@SA_NAEAV?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@1@PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@1@AEBV31@@Z; utl::allocator_traits<utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::construct<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const &>(utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>> &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const &)
0x1800217b7  test    al, al
0x1800217b9  jz      loc_1800218CA
0x1800217bf  add     qword ptr [rsi+20h], 20h ; ' '
0x1800217c4  mov     rax, [rsi+8]
0x1800217c8  cmp     rax, [rsi+10h]
0x1800217cc  jz      short loc_1800217DF
0x1800217ce  xor     r14d, r14d
0x1800217d1  mov     [rax], r15
0x1800217d4  add     qword ptr [rsi+8], 8
0x1800217d9  mov     [rbp+arg_18], r14
0x1800217dd  jmp     short loc_1800217F7
0x1800217df  lea     rdx, [rbp+arg_18]
0x1800217e3  mov     rcx, rsi
0x1800217e6  call    ??$_PushBackOne2@V?$unique_any@U?$handle_traits@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@Z$0A@@tlx@@@tlx@@@?$vector@V?$unique_any@U?$handle_traits@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@Z$0A@@tlx@@@tlx@@V?$allocator@V?$unique_any@U?$handle_traits@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@Z$0A@@tlx@@@tlx@@@utl@@@utl@@AEAA_N$$QEAV?$unique_any@U?$handle_traits@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@Z$0A@@tlx@@@tlx@@@Z; utl::vector<tlx::unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),0>>,utl::allocator<tlx::unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),0>>>>::_PushBackOne2<tlx::unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),0>>>(tlx::unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),0>> &&)
0x1800217eb  test    al, al
0x1800217ed  jz      loc_1800218C5
0x1800217f3  mov     r14, [rbp+arg_18]
0x1800217f7  mov     rax, [rsi+8]
0x1800217fb  sub     rax, [rsi]
0x1800217fe  mov     rcx, [rdi+8]
0x180021802  sar     rax, 3
0x180021806  dec     eax
0x180021808  mov     [rbp+arg_10], eax
0x18002180b  cmp     rcx, [rdi+10h]
0x18002180f  jz      short loc_18002181D
0x180021811  mov     [rcx], eax
0x180021813  add     qword ptr [rdi+8], 4
0x180021818  jmp     loc_1800218A1
0x18002181d  lea     rdx, [rbp+arg_10]
0x180021821  mov     rcx, rdi
0x180021824  call    ??$_PushBackOne2@H@?$vector@HV?$allocator@H@utl@@@utl@@AEAA_N$$QEAH@Z; utl::vector<int,utl::allocator<int>>::_PushBackOne2<int>(int &&)
0x180021829  test    al, al
0x18002182b  jnz     short loc_1800218A1
0x18002182d  add     qword ptr [rsi+20h], 0FFFFFFFFFFFFFFE0h
0x180021832  mov     rcx, [rsi+20h]; void *
0x180021836  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18002183b  add     qword ptr [rsi+8], 0FFFFFFFFFFFFFFF8h
0x180021840  mov     rcx, [rsi+8]
0x180021844  call    ??1?$unique_any@U?$handle_traits@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),0>>::~unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),0>>(void)
0x180021849  lea     rcx, [rbp+arg_18]
0x18002184d  call    ??1?$unique_any@U?$handle_traits@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),0>>::~unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),0>>(void)
0x180021852  mov     ebx, 0Eh
0x180021857  jmp     loc_180021907
0x18002185c  call    cs:__imp_GetLastError
0x180021862  mov     rcx, cs:WPP_GLOBAL_Control
0x180021869  lea     rdx, WPP_GLOBAL_Control
0x180021870  cmp     rcx, rdx
0x180021873  jz      short loc_1800218A1
0x180021875  test    dword ptr [rcx+1Ch], 10000h
0x18002187c  jz      short loc_1800218A1
0x18002187e  cmp     byte ptr [rcx+19h], 3
0x180021882  jb      short loc_1800218A1
0x180021884  mov     r9, [rbp+lpString2]
0x180021888  lea     r8, WPP_5b779035add530f74e9405630361780f_Traceguids
0x18002188f  mov     rcx, [rcx+10h]
0x180021893  mov     edx, 41h ; 'A'
0x180021898  mov     [rsp+50h+bIgnoreCase], eax
0x18002189c  call    WPP_SF_Sd
0x1800218a1  test    r14, r14
0x1800218a4  jz      short loc_1800218AF
0x1800218a6  mov     rcx, r14; hLibModule
0x1800218a9  call    cs:__imp_FreeLibrary
0x1800218af  mov     r15d, 2
0x1800218b5  mov     r14, cs:off_1800DE0C8; ";,"
0x1800218bc  lea     rbx, [r13+1]
0x1800218c0  jmp     loc_180021686
0x1800218c5  add     qword ptr [rsi+20h], 0FFFFFFFFFFFFFFE0h
0x1800218ca  mov     rcx, [rsi+20h]; void *
0x1800218ce  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800218d3  lea     rcx, [rbp+arg_18]
0x1800218d7  call    ??1?$unique_any@U?$handle_traits@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),0>>::~unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),0>>(void)
0x1800218dc  jmp     loc_18002175E
0x1800218e1  mov     rcx, [rbp+lpString2]; void *
0x1800218e5  lea     rax, [rbp+var_10]
0x1800218e9  cmp     rcx, rax
0x1800218ec  jz      short loc_1800218F3
0x1800218ee  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800218f3  mov     eax, 0Eh
0x1800218f8  jmp     short loc_180021912
0x1800218fa  mov     rcx, [rdi+8]
0x1800218fe  xor     ebx, ebx
0x180021900  cmp     [rdi], rcx
0x180021903  cmovz   ebx, r15d
0x180021907  lea     rcx, [rbp+lpString2]; void *
0x18002190b  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180021910  mov     eax, ebx
0x180021912  mov     rbx, [rsp+50h+arg_0]
0x18002191a  add     rsp, 50h
0x18002191e  pop     r15
0x180021920  pop     r14
0x180021922  pop     r13
0x180021924  pop     r12
0x180021926  pop     rdi
0x180021927  pop     rsi
0x180021928  pop     rbp
0x180021929  retn
```
