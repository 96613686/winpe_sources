# decoder_context::process_wpp_event(void)

- ea: `0x18005ddcc`
- end: `0x18005e449`
- name: `?process_wpp_event@decoder_context@@AEAA?AV?$optional@Uetw_event@@@std@@XZ`
- size: `1661`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `25`
- tags: `broker_com_uri`

## callers

- `0x18004bfb8`

## callees

- `0x180004510`
- `0x1800048c0`
- `0x18000491c`
- `0x180004aac`
- `0x180004b14`
- `0x1800054e4`
- `0x180005508`
- `0x18003a52c`
- `0x18003b0bc`
- `0x18003f6b8`
- `0x180040f94`
- `0x180041564`
- `0x180041e58`
- `0x180044a38`
- `0x18004760c`
- `0x180048fd8`
- `0x180049674`
- `0x18004a490`
- `0x18004b24c`
- `0x180057480`
- `0x18005872c`
- `0x180059b9c`
- `0x18005d370`
- `0x18005ddcc`
- `0x18005f6b0`

## import_xrefs

- `tdh!TdhOpenDecodingHandle` at `0x18005de49`
- `tdh!TdhOpenDecodingHandle` at `0x18005de49`
- `tdh!TdhSetDecodingParameter` at `0x18005de99`
- `tdh!TdhSetDecodingParameter` at `0x18005de99`

## string_xrefs

- `0x18005e3e2`: `ComponentName`
- `0x18005e3fe`: `SubComponentName`
- `0x18005e3f0`: `scomp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall decoder_context::process_wpp_event(__int64 a1, __int64 a2)
{
  _QWORD *v4; // rdi
  _QWORD *i; // rbx
  _QWORD *v6; // rsi
  _QWORD *v7; // rax
  _QWORD *v8; // rax
  __int64 v9; // r8
  void **v10; // rbx
  __int64 v11; // r8
  __int64 v12; // r8
  void **v13; // r9
  unsigned __int64 v14; // rdx
  void **v15; // rdi
  __int64 v16; // rbx
  __int64 *v17; // rbx
  __int64 v18; // r8
  char v19; // al
  void **v20; // rdx
  __int64 v21; // rsi
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v24; // rdi
  __int64 **v25; // rcx
  __int64 *j; // rax
  __int64 *k; // rcx
  char v28; // cl
  __int64 v29; // rdi
  __int64 v30; // rbx
  __int64 v32; // rcx
  __int128 v33; // [rsp+28h] [rbp-D8h] BYREF
  __int128 v34; // [rsp+38h] [rbp-C8h]
  void *Src[2]; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v36; // [rsp+58h] [rbp-A8h]
  char v37; // [rsp+68h] [rbp-98h]
  _QWORD *v38; // [rsp+70h] [rbp-90h] BYREF
  __int64 v39; // [rsp+78h] [rbp-88h]
  __int128 v40; // [rsp+80h] [rbp-80h] BYREF
  _OWORD v41[2]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v42[80]; // [rsp+C0h] [rbp-40h] BYREF
  __int16 v43; // [rsp+110h] [rbp+10h]
  int v44; // [rsp+112h] [rbp+12h]
  __int16 v45; // [rsp+116h] [rbp+16h]
  void *v46[2]; // [rsp+118h] [rbp+18h] BYREF
  unsigned __int64 v47; // [rsp+128h] [rbp+28h]
  unsigned __int64 v48; // [rsp+130h] [rbp+30h]
  void *v49[2]; // [rsp+138h] [rbp+38h] BYREF
  __int64 v50; // [rsp+148h] [rbp+48h]
  unsigned __int64 v51; // [rsp+150h] [rbp+50h]
  _QWORD v52[3]; // [rsp+158h] [rbp+58h] BYREF
  _QWORD v53[14]; // [rsp+170h] [rbp+70h] BYREF
  __int64 v54; // [rsp+1E0h] [rbp+E0h] BYREF

  v38 = (_QWORD *)a2;
  if ( dword_1800BED38 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_1800BED38);
    if ( dword_1800BED38 == -1 )
    {
      v53[0] = "mod";
      v53[1] = L"GuidName";
      v53[2] = "func";
      v53[3] = L"FunctionName";
      v53[4] = "msg";
      v53[5] = L"FormattedString";
      v53[6] = "flags";
      v53[7] = L"FlagsName";
      v53[8] = "level";
      v53[9] = L"LevelName";
      v53[10] = "comp";
      v53[11] = L"ComponentName";
      v53[12] = "scomp";
      v53[13] = L"SubComponentName";
      v38 = v53;
      v39 = (__int64)&v54;
      std::map<char const *,unsigned short const *>::map<char const *,unsigned short const *>(v32, &v38);
      atexit(decoder_context::process_wpp_event_::_2_::_dynamic_atexit_destructor_for__wpp_string_props__);
      Init_thread_footer(&dword_1800BED38);
    }
  }
  v4 = (_QWORD *)(a1 + 232);
  if ( !*(_QWORD *)(a1 + 232) )
  {
    *v4 = 0;
    if ( (unsigned int)TdhOpenDecodingHandle(a1 + 232) )
    {
      *(_BYTE *)(a2 + 168) = 0;
      return a2;
    }
    decoder_context::pdb_files(a1, &v40);
    v6 = (_QWORD *)*((_QWORD *)&v40 + 1);
    for ( i = (_QWORD *)v40; i != v6; i += 4 )
    {
      if ( i[3] <= 7u )
        v7 = i;
      else
        v7 = (_QWORD *)*i;
      v38 = v7;
      v39 = 4;
      TdhSetDecodingParameter(*v4, &v38);
    }
    std::vector<std::wstring>::_Tidy(&v40);
  }
  memset_0(v42, 0, sizeof(v42));
  v43 = 0;
  v44 = 0;
  v45 = 0;
  *(_OWORD *)v46 = 0;
  v47 = 0;
  v48 = 7;
  LOWORD(v46[0]) = 0;
  *(_OWORD *)v49 = 0;
  v50 = 0;
  v51 = 7;
  LOWORD(v49[0]) = 0;
  v52[0] = 0;
  v52[1] = 0;
  v8 = operator new(0x70u);
  *v8 = v8;
  v8[1] = v8;
  v8[2] = v8;
  *((_WORD *)v8 + 12) = 257;
  v52[0] = v8;
  if ( v51 < 5 )
  {
    std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
      v49,
      5,
      v9,
      L"[wpp]");
  }
  else
  {
    v10 = v49;
    if ( v51 > 7 )
      v10 = (void **)v49[0];
    v50 = 5;
    memmove_0(v10, L"[wpp]", 0xAu);
    *((_WORD *)v10 + 5) = 0;
  }
  decoder_context::wpp_property_value(a1, &v33, L"GuidTypeName");
  if ( BYTE8(v34) )
  {
    *(_OWORD *)Src = 0;
    v36 = 0;
    v12 = -1;
    do
      ++v12;
    while ( *(_WORD *)(v33 + 2 * v12) );
    std::wstring::_Construct<1,unsigned short const *>(Src, v33);
    v37 = 1;
    if ( BYTE8(v34) )
      std::vector<char>::~vector<char>(&v33);
  }
  else
  {
    v37 = 0;
  }
  if ( v37 )
  {
    v13 = Src;
    if ( *((_QWORD *)&v36 + 1) > 7u )
      v13 = (void **)Src[0];
    v14 = -1;
    do
      ++v14;
    while ( *((_WORD *)v13 + v14) );
    if ( v14 > v48 )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
        v46,
        v14,
        v11,
        v13);
    }
    else
    {
      v15 = v46;
      if ( v48 > 7 )
        v15 = (void **)v46[0];
      v47 = v14;
      v16 = 2 * v14;
      memmove_0(v15, v13, 2 * v14);
      *(_WORD *)((char *)v15 + v16) = 0;
    }
  }
  if ( v37 )
    std::wstring::~wstring(Src);
  v17 = *(__int64 **)qword_1800BED40;
  while ( !*((_BYTE *)v17 + 25) )
  {
    decoder_context::wpp_property_value(a1, &v33, v17[5]);
    if ( BYTE8(v34) )
    {
      *(_OWORD *)Src = 0;
      v36 = 0u;
      v18 = -1;
      do
        ++v18;
      while ( *(_WORD *)(v33 + 2 * v18) );
      std::wstring::_Construct<1,unsigned short const *>(Src, v33);
      v19 = 1;
      v37 = 1;
      if ( BYTE8(v34) )
      {
        std::vector<char>::~vector<char>(&v33);
        v19 = v37;
      }
    }
    else
    {
      v19 = 0;
      v37 = 0;
    }
    if ( v19 && (_QWORD)v36 )
    {
      v20 = Src;
      if ( *((_QWORD *)&v36 + 1) > 7u )
        v20 = (void **)Src[0];
      v21 = windiag::wchar_to_string(v41, v20);
      v22 = v17[4];
      v33 = 0;
      v34 = 0;
      v23 = -1;
      do
        ++v23;
      while ( *(_BYTE *)(v22 + v23) );
      std::string::_Construct<1,char const *>(&v33, v22, v23);
      v24 = std::map<std::string,std::variant<bool,etw_integer,double,etw_pointer,std::string,etw_stack,etw_stack_user,etw_key_stack,std::vector<__int64>,std::vector<std::string>>>::operator[](
              v52,
              &v33);
      if ( *(_BYTE *)(v24 + 40) == 4 )
      {
        std::string::operator=(v24, v21);
      }
      else
      {
        std::_Variant_base<bool,etw_integer,double,etw_pointer,std::string,etw_stack,etw_stack_user,etw_key_stack,std::vector<__int64>,std::vector<std::string>>::_Reset(v24);
        *(_OWORD *)v24 = 0;
        *(_QWORD *)(v24 + 16) = 0;
        *(_QWORD *)(v24 + 24) = 0;
        *(_OWORD *)v24 = *(_OWORD *)v21;
        *(_OWORD *)(v24 + 16) = *(_OWORD *)(v21 + 16);
        *(_QWORD *)(v21 + 16) = 0;
        *(_QWORD *)(v21 + 24) = 15;
        *(_BYTE *)v21 = 0;
        *(_BYTE *)(v24 + 40) = 4;
      }
      std::string::~string(&v33);
      std::string::~string(v41);
      v19 = v37;
    }
    if ( v19 )
      std::wstring::~wstring(Src);
    v25 = (__int64 **)v17[2];
    if ( *((_BYTE *)v25 + 25) )
    {
      for ( j = (__int64 *)v17[1]; !*((_BYTE *)j + 25) && v17 == (__int64 *)j[2]; j = (__int64 *)j[1] )
        v17 = j;
      v17 = j;
    }
    else
    {
      v17 = (__int64 *)v17[2];
      for ( k = *v25; !*((_BYTE *)k + 25); k = (__int64 *)*k )
        v17 = k;
    }
  }
  decoder_context::wpp_property_value(a1, &v33, L"SystemTime");
  v28 = BYTE8(v34);
  if ( BYTE8(v34) && *((_QWORD *)&v33 + 1) - (_QWORD)v33 == 16 )
  {
    v40 = *(_OWORD *)v33;
    BYTE2(v38) = 0;
    v29 = windiag::format_systime(Src, &v40, (unsigned int)v38);
    memset(v41, 0, sizeof(v41));
    std::string::_Construct<1,char const *>(v41, "stime", 5);
    v30 = std::map<std::string,std::variant<bool,etw_integer,double,etw_pointer,std::string,etw_stack,etw_stack_user,etw_key_stack,std::vector<__int64>,std::vector<std::string>>>::operator[](
            v52,
            v41);
    if ( *(_BYTE *)(v30 + 40) == 4 )
    {
      std::string::operator=(v30, v29);
    }
    else
    {
      std::_Variant_base<bool,etw_integer,double,etw_pointer,std::string,etw_stack,etw_stack_user,etw_key_stack,std::vector<__int64>,std::vector<std::string>>::_Reset(v30);
      *(_OWORD *)v30 = 0;
      *(_QWORD *)(v30 + 16) = 0;
      *(_QWORD *)(v30 + 24) = 0;
      *(_OWORD *)v30 = *(_OWORD *)v29;
      *(_OWORD *)(v30 + 16) = *(_OWORD *)(v29 + 16);
      *(_QWORD *)(v29 + 16) = 0;
      *(_QWORD *)(v29 + 24) = 15;
      *(_BYTE *)v29 = 0;
      *(_BYTE *)(v30 + 40) = 4;
    }
    std::string::~string(v41);
    std::string::~string(Src);
    v28 = BYTE8(v34);
  }
  if ( v28 )
    std::vector<char>::~vector<char>(&v33);
  etw_event::etw_event(a2, v42);
  *(_BYTE *)(a2 + 168) = 1;
  __1___Tree_V___Tmap_traits_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__V__variant__NUetw_integer__NUetw_pointer__V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__Uetw_stack__Uetw_stack_user__Uetw_key_stack__V__vector__JV__allocator__J_std___4_V__vector_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__V__allocator_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___2__4__2_U__less_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___2_V__allocator_U__pair___CBV__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__V__variant__NUetw_integer__NUetw_pointer__V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__Uetw_stack__Uetw_stack_user__Uetw_key_stack__V__vector__JV__allocator__J_std___4_V__vector_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__V__allocator_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___2__4__2__std___2__0A__std___std__QEAA_XZ(v52);
  std::wstring::~wstring(v49);
  std::wstring::~wstring(v46);
  return a2;
}

```

## disassembly

```asm
0x18005ddcc  mov     [rsp-8+arg_10], rbx
0x18005ddd1  push    rbp
0x18005ddd2  push    rsi
0x18005ddd3  push    rdi
0x18005ddd4  push    r12
0x18005ddd6  push    r13
0x18005ddd8  push    r14
0x18005ddda  push    r15
0x18005dddc  lea     rbp, [rsp-0F0h]
0x18005dde4  sub     rsp, 1F0h
0x18005ddeb  mov     rax, cs:__security_cookie
0x18005ddf2  xor     rax, rsp
0x18005ddf5  mov     [rbp+120h+var_40], rax
0x18005ddfc  mov     r14, rdx
0x18005ddff  mov     r15, rcx
0x18005de02  mov     [rsp+220h+var_1B0], rdx
0x18005de07  xor     r12d, r12d
0x18005de0a  mov     ecx, cs:_tls_index
0x18005de10  mov     rax, gs:58h
0x18005de19  mov     edx, 4
0x18005de1e  mov     rax, [rax+rcx*8]
0x18005de22  mov     eax, [rdx+rax]
0x18005de25  cmp     cs:dword_1800BED38, eax
0x18005de2b  jg      loc_18005E335
0x18005de31  lea     rdi, [r15+0E8h]
0x18005de38  mov     r13d, 7
0x18005de3e  cmp     [rdi], r12
0x18005de41  jnz     short loc_18005DEB1
0x18005de43  mov     [rdi], r12
0x18005de46  mov     rcx, rdi
0x18005de49  call    cs:__imp_TdhOpenDecodingHandle
0x18005de4f  test    eax, eax
0x18005de51  jz      short loc_18005DE5F
0x18005de53  mov     [r14+0A8h], r12b
0x18005de5a  jmp     loc_18005E308
0x18005de5f  lea     rdx, [rbp+120h+var_1A0]
0x18005de63  mov     rcx, r15
0x18005de66  call    ?pdb_files@decoder_context@@AEBA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@XZ; decoder_context::pdb_files(void)
0x18005de6b  mov     rbx, qword ptr [rbp+120h+var_1A0]
0x18005de6f  mov     rsi, qword ptr [rbp+120h+var_1A0+8]
0x18005de73  jmp     short loc_18005DEA3
0x18005de75  cmp     [rbx+18h], r13
0x18005de79  jbe     short loc_18005DE80
0x18005de7b  mov     rax, [rbx]
0x18005de7e  jmp     short loc_18005DE83
0x18005de80  mov     rax, rbx
0x18005de83  mov     [rsp+220h+var_1B0], rax
0x18005de88  mov     [rsp+220h+var_1A8], 4
0x18005de91  lea     rdx, [rsp+220h+var_1B0]
0x18005de96  mov     rcx, [rdi]
0x18005de99  call    cs:__imp_TdhSetDecodingParameter
0x18005de9f  add     rbx, 20h ; ' '
0x18005dea3  cmp     rbx, rsi
0x18005dea6  jnz     short loc_18005DE75
0x18005dea8  lea     rcx, [rbp+120h+var_1A0]
0x18005deac  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18005deb1  xor     edx, edx; Val
0x18005deb3  lea     r8d, [rdx+50h]; Size
0x18005deb7  lea     rcx, [rbp+120h+var_160]; void *
0x18005debb  call    memset_0
0x18005dec0  mov     [rbp+120h+var_110], r12w
0x18005dec5  xor     eax, eax
0x18005dec7  mov     [rbp+120h+var_10E], eax
0x18005deca  mov     [rbp+120h+var_10A], ax
0x18005dece  xorps   xmm0, xmm0
0x18005ded1  movups  xmmword ptr [rbp+120h+var_108], xmm0
0x18005ded5  mov     [rbp+120h+var_F8], r12
0x18005ded9  mov     [rbp+120h+var_F0], r13
0x18005dedd  mov     word ptr [rbp+120h+var_108], r12w
0x18005dee2  movups  xmmword ptr [rbp+120h+var_E8], xmm0
0x18005dee6  mov     [rbp+120h+var_D8], r12
0x18005deea  mov     [rbp+120h+var_D0], r13
0x18005deee  mov     word ptr [rbp+120h+var_E8], r12w
0x18005def3  mov     [rbp+120h+var_C8], r12
0x18005def7  mov     [rbp+120h+var_C0], r12
0x18005defb  lea     ecx, [rax+70h]; Size
0x18005defe  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005df03  mov     [rax], rax
0x18005df06  mov     [rax+8], rax
0x18005df0a  mov     [rax+10h], rax
0x18005df0e  mov     word ptr [rax+18h], 101h
0x18005df14  mov     [rbp+120h+var_C8], rax
0x18005df18  mov     esi, 5
0x18005df1d  cmp     [rbp+120h+var_D0], rsi
0x18005df21  jb      short loc_18005DF4E
0x18005df23  lea     rbx, [rbp+120h+var_E8]
0x18005df27  cmp     [rbp+120h+var_D0], r13
0x18005df2b  cmova   rbx, [rbp+120h+var_E8]
0x18005df30  mov     [rbp+120h+var_D8], rsi
0x18005df34  lea     r8d, [rsi+5]; Size
0x18005df38  lea     rdx, aWpp; "[wpp]"
0x18005df3f  mov     rcx, rbx; void *
0x18005df42  call    memmove_0
0x18005df47  mov     [rbx+0Ah], r12w
0x18005df4c  jmp     short loc_18005DF61
0x18005df4e  lea     r9, aWpp; "[wpp]"
0x18005df55  mov     rdx, rsi
0x18005df58  lea     rcx, [rbp+120h+var_E8]
0x18005df5c  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18005df61  lea     r8, aGuidtypename; "GuidTypeName"
0x18005df68  lea     rdx, [rsp+220h+var_1F8]
0x18005df6d  mov     rcx, r15
0x18005df70  call    ?wpp_property_value@decoder_context@@AEAA?AV?$optional@V?$vector@EV?$allocator@E@std@@@std@@@std@@PEBG@Z; decoder_context::wpp_property_value(ushort const *)
0x18005df75  nop
0x18005df76  cmp     byte ptr [rsp+220h+var_1E0], r12b
0x18005df7b  jz      short loc_18005DFC3
0x18005df7d  mov     rdx, qword ptr [rsp+220h+var_1F8]
0x18005df82  xorps   xmm0, xmm0
0x18005df85  movups  xmmword ptr [rsp+220h+Src], xmm0
0x18005df8a  xorps   xmm1, xmm1
0x18005df8d  movdqu  [rsp+220h+var_1C8], xmm1
0x18005df93  or      r8, 0FFFFFFFFFFFFFFFFh
0x18005df97  inc     r8
0x18005df9a  cmp     [rdx+r8*2], r12w
0x18005df9f  jnz     short loc_18005DF97
0x18005dfa1  lea     rcx, [rsp+220h+Src]
0x18005dfa6  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18005dfab  mov     [rsp+220h+var_1B8], 1
0x18005dfb0  cmp     byte ptr [rsp+220h+var_1E0], r12b
0x18005dfb5  jz      short loc_18005DFC8
0x18005dfb7  lea     rcx, [rsp+220h+var_1F8]
0x18005dfbc  call    ??1?$vector@DV?$allocator@D@std@@@std@@QEAA@XZ; std::vector<char>::~vector<char>(void)
0x18005dfc1  jmp     short loc_18005DFC8
0x18005dfc3  mov     [rsp+220h+var_1B8], r12b
0x18005dfc8  cmp     [rsp+220h+var_1B8], r12b
0x18005dfcd  jz      short loc_18005E027
0x18005dfcf  lea     r9, [rsp+220h+Src]
0x18005dfd4  cmp     qword ptr [rsp+220h+var_1C8+8], r13
0x18005dfd9  cmova   r9, [rsp+220h+Src]
0x18005dfdf  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18005dfe3  inc     rdx
0x18005dfe6  cmp     [r9+rdx*2], r12w
0x18005dfeb  jnz     short loc_18005DFE3
0x18005dfed  cmp     rdx, [rbp+120h+var_F0]
0x18005dff1  ja      short loc_18005E01D
0x18005dff3  lea     rdi, [rbp+120h+var_108]
0x18005dff7  cmp     [rbp+120h+var_F0], r13
0x18005dffb  cmova   rdi, [rbp+120h+var_108]
0x18005e000  mov     [rbp+120h+var_F8], rdx
0x18005e004  lea     rbx, [rdx+rdx]
0x18005e008  mov     r8, rbx; Size
0x18005e00b  mov     rdx, r9; Src
0x18005e00e  mov     rcx, rdi; void *
0x18005e011  call    memmove_0
0x18005e016  mov     [rdi+rbx], r12w
0x18005e01b  jmp     short loc_18005E027
0x18005e01d  lea     rcx, [rbp+120h+var_108]
0x18005e021  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18005e026  nop
0x18005e027  cmp     [rsp+220h+var_1B8], r12b
0x18005e02c  jz      short loc_18005E038
0x18005e02e  lea     rcx, [rsp+220h+Src]
0x18005e033  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005e038  mov     rbx, cs:qword_1800BED40
0x18005e03f  mov     rbx, [rbx]
0x18005e042  lea     rdx, [rsp+220h+var_1F8]
0x18005e047  mov     rcx, r15
0x18005e04a  cmp     [rbx+19h], r12b
0x18005e04e  jnz     loc_18005E1E1
0x18005e054  mov     r8, [rbx+28h]
0x18005e058  call    ?wpp_property_value@decoder_context@@AEAA?AV?$optional@V?$vector@EV?$allocator@E@std@@@std@@@std@@PEBG@Z; decoder_context::wpp_property_value(ushort const *)
0x18005e05d  nop
0x18005e05e  cmp     byte ptr [rsp+220h+var_1E0], r12b
0x18005e063  jz      short loc_18005E0B1
0x18005e065  mov     rdx, qword ptr [rsp+220h+var_1F8]
0x18005e06a  xorps   xmm0, xmm0
0x18005e06d  movups  xmmword ptr [rsp+220h+Src], xmm0
0x18005e072  mov     qword ptr [rsp+220h+var_1C8], r12
0x18005e077  mov     qword ptr [rsp+220h+var_1C8+8], r12
0x18005e07c  or      r8, 0FFFFFFFFFFFFFFFFh
0x18005e080  inc     r8
0x18005e083  cmp     [rdx+r8*2], r12w
0x18005e088  jnz     short loc_18005E080
0x18005e08a  lea     rcx, [rsp+220h+Src]
0x18005e08f  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18005e094  mov     al, 1
0x18005e096  mov     [rsp+220h+var_1B8], al
0x18005e09a  cmp     byte ptr [rsp+220h+var_1E0], r12b
0x18005e09f  jz      short loc_18005E0B8
0x18005e0a1  lea     rcx, [rsp+220h+var_1F8]
0x18005e0a6  call    ??1?$vector@DV?$allocator@D@std@@@std@@QEAA@XZ; std::vector<char>::~vector<char>(void)
0x18005e0ab  mov     al, [rsp+220h+var_1B8]
0x18005e0af  jmp     short loc_18005E0B8
0x18005e0b1  mov     al, r12b
0x18005e0b4  mov     [rsp+220h+var_1B8], al
0x18005e0b8  test    al, al
0x18005e0ba  jz      loc_18005E184
0x18005e0c0  cmp     qword ptr [rsp+220h+var_1C8], r12
0x18005e0c5  jz      loc_18005E184
0x18005e0cb  lea     rdx, [rsp+220h+Src]
0x18005e0d0  cmp     qword ptr [rsp+220h+var_1C8+8], r13
0x18005e0d5  cmova   rdx, [rsp+220h+Src]
0x18005e0db  lea     rcx, [rbp+120h+var_188]
0x18005e0df  call    ?wchar_to_string@windiag@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBG@Z; windiag::wchar_to_string(ushort const *)
0x18005e0e4  mov     rsi, rax
0x18005e0e7  mov     rdx, [rbx+20h]
0x18005e0eb  xorps   xmm0, xmm0
0x18005e0ee  movups  [rsp+220h+var_1F8], xmm0
0x18005e0f3  xorps   xmm1, xmm1
0x18005e0f6  movdqu  xmmword ptr [rsp+38h], xmm1
0x18005e0fc  or      r8, 0FFFFFFFFFFFFFFFFh
0x18005e100  inc     r8
0x18005e103  cmp     [rdx+r8], r12b
0x18005e107  jnz     short loc_18005E100
0x18005e109  lea     rcx, [rsp+220h+var_1F8]
0x18005e10e  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18005e113  nop
0x18005e114  lea     rdx, [rsp+220h+var_1F8]
0x18005e119  lea     rcx, [rbp+120h+var_C8]
0x18005e11d  call    ??A?$map@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$variant@_NUetw_integer@@NUetw_pointer@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Uetw_stack@@Uetw_stack_user@@Uetw_key_stack@@V?$vector@_JV?$allocator@_J@std@@@4@V?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@4@@2@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$variant@_NUetw_integer@@NUetw_pointer@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Uetw_stack@@Uetw_stack_user@@Uetw_key_stack@@V?$vector@_JV?$allocator@_J@std@@@4@V?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@4@@2@@std@@@2@@std@@QEAAAEAV?$variant@_NUetw_integer@@NUetw_pointer@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Uetw_stack@@Uetw_stack_user@@Uetw_key_stack@@V?$vector@_JV?$allocator@_J@std@@@4@V?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@4@@1@$$QEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::map<std::string,std::variant<bool,etw_integer,double,etw_pointer,std::string,etw_stack,etw_stack_user,etw_key_stack,std::vector<__int64>,std::vector<std::string>>>::operator[](std::string &&)
0x18005e122  mov     rdi, rax
0x18005e125  mov     rcx, rax
0x18005e128  cmp     byte ptr [rax+28h], 4
0x18005e12c  jnz     short loc_18005E138
0x18005e12e  mov     rdx, rsi
0x18005e131  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x18005e136  jmp     short loc_18005E16C
0x18005e138  call    ?_Reset@?$_Variant_base@_NUetw_integer@@NUetw_pointer@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Uetw_stack@@Uetw_stack_user@@Uetw_key_stack@@V?$vector@_JV?$allocator@_J@std@@@4@V?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@4@@std@@QEAAXXZ; std::_Variant_base<bool,etw_integer,double,etw_pointer,std::string,etw_stack,etw_stack_user,etw_key_stack,std::vector<__int64>,std::vector<std::string>>::_Reset(void)
0x18005e13d  xorps   xmm0, xmm0
0x18005e140  movups  xmmword ptr [rdi], xmm0
0x18005e143  mov     [rdi+10h], r12
0x18005e147  mov     [rdi+18h], r12
0x18005e14b  movups  xmm0, xmmword ptr [rsi]
0x18005e14e  movups  xmmword ptr [rdi], xmm0
0x18005e151  movups  xmm1, xmmword ptr [rsi+10h]
0x18005e155  movups  xmmword ptr [rdi+10h], xmm1
0x18005e159  mov     [rsi+10h], r12
0x18005e15d  mov     qword ptr [rsi+18h], 0Fh
0x18005e165  mov     [rsi], r12b
0x18005e168  mov     byte ptr [rdi+28h], 4
0x18005e16c  lea     rcx, [rsp+220h+var_1F8]
0x18005e171  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18005e176  nop
0x18005e177  lea     rcx, [rbp+120h+var_188]
0x18005e17b  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18005e180  mov     al, [rsp+220h+var_1B8]
0x18005e184  test    al, al
0x18005e186  jz      short loc_18005E192
0x18005e188  lea     rcx, [rsp+220h+Src]
0x18005e18d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005e192  mov     rcx, [rbx+10h]
0x18005e196  cmp     [rcx+19h], r12b
0x18005e19a  jz      short loc_18005E1BD
0x18005e19c  mov     rax, [rbx+8]
0x18005e1a0  jmp     short loc_18005E1AF
0x18005e1a2  cmp     rbx, [rax+10h]
0x18005e1a6  jnz     short loc_18005E1B5
0x18005e1a8  mov     rbx, rax
0x18005e1ab  mov     rax, [rax+8]
0x18005e1af  cmp     [rax+19h], r12b
0x18005e1b3  jz      short loc_18005E1A2
0x18005e1b5  mov     rbx, rax
0x18005e1b8  jmp     loc_18005E042
0x18005e1bd  mov     rbx, rcx
0x18005e1c0  mov     rcx, [rcx]
0x18005e1c3  cmp     [rcx+19h], r12b
0x18005e1c7  jnz     loc_18005E042
0x18005e1cd  mov     rbx, rcx
0x18005e1d0  mov     rax, [rcx]
0x18005e1d3  mov     rcx, rax
0x18005e1d6  cmp     [rax+19h], r12b
0x18005e1da  jz      short loc_18005E1CD
0x18005e1dc  jmp     loc_18005E042
0x18005e1e1  lea     r8, aSystemtime; "SystemTime"
0x18005e1e8  call    ?wpp_property_value@decoder_context@@AEAA?AV?$optional@V?$vector@EV?$allocator@E@std@@@std@@@std@@PEBG@Z; decoder_context::wpp_property_value(ushort const *)
0x18005e1ed  nop
0x18005e1ee  mov     rcx, [rsp+220h+var_1E0]
0x18005e1f3  test    cl, cl
0x18005e1f5  jz      loc_18005E2CB
0x18005e1fb  mov     rdx, qword ptr [rsp+220h+var_1F8]
0x18005e200  mov     rax, qword ptr [rsp+220h+var_1F8+8]
0x18005e205  sub     rax, rdx
0x18005e208  cmp     rax, 10h
0x18005e20c  jnz     loc_18005E2CB
0x18005e212  movups  xmm0, xmmword ptr [rdx]
0x18005e215  movdqu  [rbp+120h+var_1A0], xmm0
0x18005e21a  mov     byte ptr [rsp+220h+var_1B0+2], r12b
0x18005e21f  mov     r8d, dword ptr [rsp+220h+var_1B0]
0x18005e224  lea     rdx, [rbp+120h+var_1A0]
0x18005e228  lea     rcx, [rsp+220h+Src]
0x18005e22d  call    ?format_systime@windiag@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBU_SYSTEMTIME@@V?$optional@G@3@@Z; windiag::format_systime(_SYSTEMTIME const &,std::optional<ushort>)
0x18005e232  mov     rdi, rax
0x18005e235  xorps   xmm0, xmm0
0x18005e238  movups  [rbp+120h+var_188], xmm0
0x18005e23c  xorps   xmm1, xmm1
0x18005e23f  movdqu  [rbp+120h+var_178], xmm1
0x18005e244  mov     r8d, 5
0x18005e24a  lea     rdx, aStime; "stime"
0x18005e251  lea     rcx, [rbp+120h+var_188]
0x18005e255  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18005e25a  nop
0x18005e25b  lea     rdx, [rbp+120h+var_188]
0x18005e25f  lea     rcx, [rbp+120h+var_C8]
0x18005e263  call    ??A?$map@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$variant@_NUetw_integer@@NUetw_pointer@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Uetw_stack@@Uetw_stack_user@@Uetw_key_stack@@V?$vector@_JV?$allocator@_J@std@@@4@V?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@4@@2@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$variant@_NUetw_integer@@NUetw_pointer@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Uetw_stack@@Uetw_stack_user@@Uetw_key_stack@@V?$vector@_JV?$allocator@_J@std@@@4@V?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@4@@2@@std@@@2@@std@@QEAAAEAV?$variant@_NUetw_integer@@NUetw_pointer@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Uetw_stack@@Uetw_stack_user@@Uetw_key_stack@@V?$vector@_JV?$allocator@_J@std@@@4@V?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@4@@1@$$QEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::map<std::string,std::variant<bool,etw_integer,double,etw_pointer,std::string,etw_stack,etw_stack_user,etw_key_stack,std::vector<__int64>,std::vector<std::string>>>::operator[](std::string &&)
0x18005e268  mov     rbx, rax
0x18005e26b  mov     rcx, rax
0x18005e26e  cmp     byte ptr [rax+28h], 4
0x18005e272  jnz     short loc_18005E27E
0x18005e274  mov     rdx, rdi
0x18005e277  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
  ... truncated ...
```
