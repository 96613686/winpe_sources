# Diagnostics::Analyzer_Traits<Diagnostics::ReportingEvents>::TransformToJson(std::vector<Diagnostics::AnalysisRecord,std::allocator<Diagnostics::AnalysisRecord>> const &,Diagnostics::TraitsConfig const &)

- ea: `0x18004ca50`
- end: `0x18004d0af`
- name: `?TransformToJson@?$Analyzer_Traits@UReportingEvents@Diagnostics@@@Diagnostics@@AEBA?AV?$optional@Vvalue@json@web@@@std@@AEBV?$vector@UAnalysisRecord@Diagnostics@@V?$allocator@UAnalysisRecord@Diagnostics@@@std@@@4@AEBUTraitsConfig@2@@Z`
- size: `1631`
- prototype: ``
- caller_count: `4`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003c8e0`
- `0x1800400d0`
- `0x1800403b0`
- `0x180040690`

## callees

- `0x180018b04`
- `0x180018eec`
- `0x180019080`
- `0x18001f520`
- `0x18004ca50`
- `0x18005873c`
- `0x18005e018`
- `0x180072de4`
- `0x180072eb0`
- `0x180072f30`
- `0x180072fa0`
- `0x1800731f0`
- `0x180073294`
- `0x18008fe00`
- `0x180096170`

## string_xrefs

- `0x18004cc6d`: `Outcome`

## pseudocode

```c
// Hidden C++ exception states: #wind=30
__int64 __fastcall Diagnostics::Analyzer_Traits<Diagnostics::ReportingEvents>::TransformToJson(
        __int64 a1,
        __int64 a2,
        __int64 *a3,
        __int64 a4)
{
  __int64 v4; // rsi
  unsigned __int64 v7; // r14
  __int64 v8; // r15
  __int64 v9; // r12
  __int64 v10; // rax
  __int64 *v11; // rbx
  __int64 *v12; // rax
  __int64 v13; // rdx
  __int64 v14; // rax
  __int64 *v15; // rbx
  __int64 *v16; // rax
  __int64 v17; // rdx
  __int64 v18; // rax
  __int64 *v19; // rbx
  __int64 *v20; // rax
  __int64 v21; // rdx
  __int64 v22; // rax
  __int64 *v23; // rbx
  _WORD *v24; // rdx
  unsigned __int64 v25; // r8
  __int64 *v26; // rax
  __int64 v27; // rdx
  __int64 v28; // rax
  __int64 *v29; // rbx
  _WORD *v30; // rdx
  unsigned __int64 v31; // r8
  __int64 *v32; // rax
  __int64 v33; // rdx
  __int64 v34; // rax
  __int64 *v35; // rbx
  _WORD *v36; // rdx
  unsigned __int64 v37; // r8
  __int64 *v38; // rax
  __int64 v39; // rdx
  _QWORD **v40; // rbx
  _QWORD *v41; // rdi
  __int64 v42; // rax
  __int64 *v43; // r12
  __int64 *v44; // rax
  __int64 v45; // rdx
  __int64 v46; // rax
  __int64 *v47; // r12
  __int64 *v48; // rax
  __int64 v49; // rdx
  __int64 v50; // rax
  _QWORD *v51; // rcx
  __int64 v52; // rcx
  __int64 v53; // rbx
  __int64 v54; // rax
  __int64 v56[2]; // [rsp+20h] [rbp-A9h] BYREF
  __int128 v57; // [rsp+30h] [rbp-99h] BYREF
  __int128 v58; // [rsp+40h] [rbp-89h]
  _BYTE v59[32]; // [rsp+50h] [rbp-79h] BYREF
  __int64 v60; // [rsp+70h] [rbp-59h]
  __int64 v61; // [rsp+78h] [rbp-51h]
  __int64 v62; // [rsp+80h] [rbp-49h] BYREF
  __int64 v63; // [rsp+90h] [rbp-39h] BYREF
  __int64 v64; // [rsp+98h] [rbp-31h] BYREF
  __int64 v65; // [rsp+A0h] [rbp-29h] BYREF
  __int64 v66; // [rsp+A8h] [rbp-21h] BYREF
  __int64 v67; // [rsp+B0h] [rbp-19h] BYREF
  __int64 v68; // [rsp+B8h] [rbp-11h] BYREF
  __int64 v69; // [rsp+C0h] [rbp-9h] BYREF
  __int128 v70; // [rsp+C8h] [rbp-1h] BYREF
  __int64 v71; // [rsp+D8h] [rbp+Fh]

  v4 = a4;
  v60 = a4;
  v62 = a2;
  v7 = 0;
  v70 = 0;
  v71 = 0;
  std::vector<web::json::value>::reserve(&v70, 0xAF8AF8AF8AF8AF8BuLL * ((a3[1] - *a3) >> 3));
  v8 = *a3;
  v9 = a3[1];
  v61 = v9;
  while ( v8 != v9 )
  {
    v56[0] = 0;
    web::json::value::object(v56, 0);
    if ( *(_BYTE *)(v4 + 3) && *(_QWORD *)(v8 + 184) )
    {
      v10 = std::wstring::wstring((__int64)v59, v8 + 168);
      v11 = (__int64 *)web::json::value::string(&v63, v10);
      v57 = 0;
      v58 = 0;
      std::wstring::_Construct<1,wchar_t const *>(&v57, L"Event", 5u);
      v12 = (__int64 *)web::json::value::operator[](v56, &v57);
      if ( v12 != v11 )
      {
        v13 = *v12;
        *v12 = *v11;
        *v11 = v13;
      }
      std::wstring::~wstring((__int64)&v57);
      if ( v63 )
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v63 + 192LL))(v63, 1);
    }
    if ( *(_BYTE *)(v8 + 232) )
    {
      v14 = std::wstring::wstring((__int64)v59, v8 + 200);
      v15 = (__int64 *)web::json::value::string(&v64, v14);
      v57 = 0;
      v58 = 0;
      std::wstring::_Construct<1,wchar_t const *>(&v57, L"Event", 5u);
      v16 = (__int64 *)web::json::value::operator[](v56, &v57);
      if ( v16 != v15 )
      {
        v17 = *v16;
        *v16 = *v15;
        *v15 = v17;
      }
      std::wstring::~wstring((__int64)&v57);
      if ( v64 )
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v64 + 192LL))(v64, 1);
    }
    if ( *(_BYTE *)(v8 + 272) )
    {
      v18 = std::wstring::wstring((__int64)v59, v8 + 240);
      v19 = (__int64 *)web::json::value::string(&v65, v18);
      v57 = 0;
      v58 = 0;
      std::wstring::_Construct<1,wchar_t const *>(&v57, L"Outcome", 7u);
      v20 = (__int64 *)web::json::value::operator[](v56, &v57);
      if ( v20 != v19 )
      {
        v21 = *v20;
        *v20 = *v19;
        *v19 = v21;
      }
      std::wstring::~wstring((__int64)&v57);
      if ( v65 )
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v65 + 192LL))(v65, 1);
    }
    if ( *(_QWORD *)(v4 + 16) )
    {
      v22 = std::wstring::wstring((__int64)v59, v8 + 8);
      v23 = (__int64 *)web::json::value::string(&v66, v22);
      v24 = *(_WORD **)(v4 + 8);
      v57 = 0;
      v58 = 0;
      v25 = -1;
      do
        ++v25;
      while ( v24[v25] );
      std::wstring::_Construct<1,wchar_t const *>(&v57, v24, v25);
      v26 = (__int64 *)web::json::value::operator[](v56, &v57);
      if ( v26 != v23 )
      {
        v27 = *v26;
        *v26 = *v23;
        *v23 = v27;
      }
      std::wstring::~wstring((__int64)&v57);
      if ( v66 )
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v66 + 192LL))(v66, 1);
    }
    if ( *(_QWORD *)(v4 + 32) )
    {
      v28 = std::wstring::wstring((__int64)v59, v8 + 40);
      v29 = (__int64 *)web::json::value::string(&v67, v28);
      v30 = *(_WORD **)(v4 + 24);
      v57 = 0;
      v58 = 0;
      v31 = -1;
      do
        ++v31;
      while ( v30[v31] );
      std::wstring::_Construct<1,wchar_t const *>(&v57, v30, v31);
      v32 = (__int64 *)web::json::value::operator[](v56, &v57);
      if ( v32 != v29 )
      {
        v33 = *v32;
        *v32 = *v29;
        *v29 = v33;
      }
      std::wstring::~wstring((__int64)&v57);
      if ( v67 )
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v67 + 192LL))(v67, 1);
    }
    if ( *(_QWORD *)(v4 + 48) )
    {
      v34 = std::wstring::wstring((__int64)v59, v8 + 72);
      v35 = (__int64 *)web::json::value::string(&v68, v34);
      v36 = *(_WORD **)(v4 + 40);
      v57 = 0;
      v58 = 0;
      v37 = -1;
      do
        ++v37;
      while ( v36[v37] );
      std::wstring::_Construct<1,wchar_t const *>(&v57, v36, v37);
      v38 = (__int64 *)web::json::value::operator[](v56, &v57);
      if ( v38 != v35 )
      {
        v39 = *v38;
        *v38 = *v35;
        *v35 = v39;
      }
      std::wstring::~wstring((__int64)&v57);
      if ( v68 )
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v68 + 192LL))(v68, 1);
    }
    v40 = *(_QWORD ***)(v8 + 112);
    v41 = *v40;
    if ( *(_BYTE *)(v8 + 232) )
    {
      if ( v41 != v40 )
      {
        do
        {
          v42 = std::wstring::wstring((__int64)v59, (__int64)(v41 + 6));
          v43 = (__int64 *)web::json::value::string(&v69, v42);
          v44 = (__int64 *)web::json::value::operator[](v56, v41 + 2);
          if ( v44 != v43 )
          {
            v45 = *v44;
            *v44 = *v43;
            *v43 = v45;
          }
          if ( v69 )
            (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v69 + 192LL))(v69, 1);
          v41 = (_QWORD *)*v41;
        }
        while ( v41 != v40 );
LABEL_53:
        v9 = v61;
        v4 = v60;
      }
    }
    else if ( v41 != v40 )
    {
      do
      {
        v46 = std::wstring::wstring((__int64)v59, (__int64)(v41 + 6));
        v47 = (__int64 *)web::json::value::string(&v62, v46);
        v48 = (__int64 *)web::json::value::operator[](v56, v41 + 2);
        if ( v48 != v47 )
        {
          v49 = *v48;
          *v48 = *v47;
          *v47 = v49;
        }
        if ( v62 )
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v62 + 192LL))(v62, 1);
        v41 = (_QWORD *)*v41;
      }
      while ( v41 != v40 );
      goto LABEL_53;
    }
    if ( *((_QWORD *)&v70 + 1) == v71 )
    {
      std::vector<web::json::value>::_Emplace_reallocate<web::json::value>(&v70, *((__int64 **)&v70 + 1), v56);
    }
    else
    {
      v50 = v56[0];
      v56[0] = 0;
      **((_QWORD **)&v70 + 1) = v50;
      *((_QWORD *)&v70 + 1) += 8LL;
    }
    if ( v56[0] )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v56[0] + 192LL))(v56[0], 1);
    v8 += 280;
  }
  if ( *(_BYTE *)(v4 + 1) )
  {
    if ( *(_BYTE *)v4 )
      v51 = (_QWORD *)v70;
    else
      v51 = (_QWORD *)(*((_QWORD *)&v70 + 1) - 8LL);
    (**(void (__fastcall ***)(_QWORD, __int64))*v51)(*v51, a2);
    *(_BYTE *)(a2 + 8) = 1;
  }
  else
  {
    v56[0] = 0;
    web::json::value::array(v56);
    v52 = v70;
    if ( (__int64)(*((_QWORD *)&v70 + 1) - v70) >> 3 )
    {
      do
      {
        v53 = v52 + 8 * v7;
        v54 = web::json::value::operator[](v56, v7);
        web::json::value::operator=(v54, v53);
        ++v7;
        v52 = v70;
      }
      while ( v7 < (__int64)(*((_QWORD *)&v70 + 1) - v70) >> 3 );
    }
    *(_QWORD *)a2 = v56[0];
    *(_BYTE *)(a2 + 8) = 1;
  }
  std::vector<web::json::value>::_Tidy(&v70);
  return a2;
}

```

## disassembly

```asm
0x18004ca50  mov     [rsp-8+arg_0], rbx
0x18004ca55  push    rbp
0x18004ca56  push    rsi
0x18004ca57  push    rdi
0x18004ca58  push    r12
0x18004ca5a  push    r13
0x18004ca5c  push    r14
0x18004ca5e  push    r15
0x18004ca60  lea     rbp, [rsp-27h]
0x18004ca65  sub     rsp, 0F0h
0x18004ca6c  mov     rax, cs:__security_cookie
0x18004ca73  xor     rax, rsp
0x18004ca76  mov     [rbp+57h+var_40], rax
0x18004ca7a  mov     rsi, r9
0x18004ca7d  mov     [rbp+57h+var_B0], r9
0x18004ca81  mov     rbx, r8
0x18004ca84  mov     r13, rdx
0x18004ca87  mov     [rbp+57h+var_A0], rdx
0x18004ca8b  xor     r14d, r14d
0x18004ca8e  xorps   xmm1, xmm1
0x18004ca91  movdqu  [rbp+57h+var_58], xmm1
0x18004ca96  mov     [rbp+57h+var_48], r14
0x18004ca9a  mov     rdx, [r8+8]
0x18004ca9e  sub     rdx, [r8]
0x18004caa1  sar     rdx, 3
0x18004caa5  mov     rax, 0AF8AF8AF8AF8AF8Bh
0x18004caaf  imul    rdx, rax
0x18004cab3  lea     rcx, [rbp+57h+var_58]
0x18004cab7  call    ?reserve@?$vector@Vvalue@json@web@@V?$allocator@Vvalue@json@web@@@std@@@std@@QEAAX_K@Z; std::vector<web::json::value>::reserve(unsigned __int64)
0x18004cabc  mov     r15, [rbx]
0x18004cabf  mov     r12, [rbx+8]
0x18004cac3  mov     [rbp+57h+var_A8], r12
0x18004cac7  cmp     r15, r12
0x18004caca  jz      loc_18004CFE6
0x18004cad0  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18004cad4  mov     [rsp+120h+var_100], r14
0x18004cad9  xor     edx, edx
0x18004cadb  lea     rcx, [rsp+120h+var_100]
0x18004cae0  call    ?object@value@json@web@@SA?AV123@_N@Z; web::json::value::object(bool)
0x18004cae5  nop
0x18004cae6  cmp     [rsi+3], r14b
0x18004caea  jz      loc_18004CB8D
0x18004caf0  cmp     [r15+0B8h], r14
0x18004caf7  jz      loc_18004CB8D
0x18004cafd  lea     rdx, [r15+0A8h]
0x18004cb04  lea     rcx, [rbp+57h+var_D0]
0x18004cb08  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18004cb0d  mov     rdx, rax
0x18004cb10  lea     rcx, [rbp+57h+var_90]
0x18004cb14  call    ?string@value@json@web@@SA?AV123@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::string(std::wstring)
0x18004cb19  mov     rbx, rax
0x18004cb1c  xorps   xmm0, xmm0
0x18004cb1f  movups  [rsp+120h+var_F0], xmm0
0x18004cb24  xorps   xmm1, xmm1
0x18004cb27  movdqu  [rsp+120h+var_E0], xmm1
0x18004cb2d  mov     r8d, 5
0x18004cb33  lea     rdx, aEvent_0; "Event"
0x18004cb3a  lea     rcx, [rsp+120h+var_F0]
0x18004cb3f  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18004cb44  nop
0x18004cb45  lea     rdx, [rsp+120h+var_F0]
0x18004cb4a  lea     rcx, [rsp+120h+var_100]
0x18004cb4f  call    ??Avalue@json@web@@QEAAAEAV012@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::operator[](std::wstring const &)
0x18004cb54  cmp     rax, rbx
0x18004cb57  jz      short loc_18004CB65
0x18004cb59  mov     rdx, [rax]
0x18004cb5c  mov     rcx, [rbx]
0x18004cb5f  mov     [rax], rcx
0x18004cb62  mov     [rbx], rdx
0x18004cb65  lea     rcx, [rsp+120h+var_F0]
0x18004cb6a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004cb6f  nop
0x18004cb70  mov     rcx, [rbp+57h+var_90]
0x18004cb74  test    rcx, rcx
0x18004cb77  jz      short loc_18004CB8D
0x18004cb79  mov     rax, [rcx]
0x18004cb7c  mov     edx, 1
0x18004cb81  mov     rax, [rax+0C0h]
0x18004cb88  call    _guard_dispatch_icall
0x18004cb8d  cmp     [r15+0E8h], r14b
0x18004cb94  jz      loc_18004CC2A
0x18004cb9a  lea     rdx, [r15+0C8h]
0x18004cba1  lea     rcx, [rbp+57h+var_D0]
0x18004cba5  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18004cbaa  mov     rdx, rax
0x18004cbad  lea     rcx, [rbp+57h+var_88]
0x18004cbb1  call    ?string@value@json@web@@SA?AV123@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::string(std::wstring)
0x18004cbb6  mov     rbx, rax
0x18004cbb9  xorps   xmm0, xmm0
0x18004cbbc  movups  [rsp+120h+var_F0], xmm0
0x18004cbc1  xorps   xmm1, xmm1
0x18004cbc4  movdqu  [rsp+120h+var_E0], xmm1
0x18004cbca  mov     r8d, 5
0x18004cbd0  lea     rdx, aEvent_0; "Event"
0x18004cbd7  lea     rcx, [rsp+120h+var_F0]
0x18004cbdc  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18004cbe1  nop
0x18004cbe2  lea     rdx, [rsp+120h+var_F0]
0x18004cbe7  lea     rcx, [rsp+120h+var_100]
0x18004cbec  call    ??Avalue@json@web@@QEAAAEAV012@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::operator[](std::wstring const &)
0x18004cbf1  cmp     rax, rbx
0x18004cbf4  jz      short loc_18004CC02
0x18004cbf6  mov     rdx, [rax]
0x18004cbf9  mov     rcx, [rbx]
0x18004cbfc  mov     [rax], rcx
0x18004cbff  mov     [rbx], rdx
0x18004cc02  lea     rcx, [rsp+120h+var_F0]
0x18004cc07  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004cc0c  nop
0x18004cc0d  mov     rcx, [rbp+57h+var_88]
0x18004cc11  test    rcx, rcx
0x18004cc14  jz      short loc_18004CC2A
0x18004cc16  mov     rax, [rcx]
0x18004cc19  mov     edx, 1
0x18004cc1e  mov     rax, [rax+0C0h]
0x18004cc25  call    _guard_dispatch_icall
0x18004cc2a  cmp     [r15+110h], r14b
0x18004cc31  jz      loc_18004CCC7
0x18004cc37  lea     rdx, [r15+0F0h]
0x18004cc3e  lea     rcx, [rbp+57h+var_D0]
0x18004cc42  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18004cc47  mov     rdx, rax
0x18004cc4a  lea     rcx, [rbp+57h+var_80]
0x18004cc4e  call    ?string@value@json@web@@SA?AV123@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::string(std::wstring)
0x18004cc53  mov     rbx, rax
0x18004cc56  xorps   xmm0, xmm0
0x18004cc59  movups  [rsp+120h+var_F0], xmm0
0x18004cc5e  xorps   xmm1, xmm1
0x18004cc61  movdqu  [rsp+120h+var_E0], xmm1
0x18004cc67  mov     r8d, 7
0x18004cc6d  lea     rdx, aOutcome; "Outcome"
0x18004cc74  lea     rcx, [rsp+120h+var_F0]
0x18004cc79  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18004cc7e  nop
0x18004cc7f  lea     rdx, [rsp+120h+var_F0]
0x18004cc84  lea     rcx, [rsp+120h+var_100]
0x18004cc89  call    ??Avalue@json@web@@QEAAAEAV012@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::operator[](std::wstring const &)
0x18004cc8e  cmp     rax, rbx
0x18004cc91  jz      short loc_18004CC9F
0x18004cc93  mov     rdx, [rax]
0x18004cc96  mov     rcx, [rbx]
0x18004cc99  mov     [rax], rcx
0x18004cc9c  mov     [rbx], rdx
0x18004cc9f  lea     rcx, [rsp+120h+var_F0]
0x18004cca4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004cca9  nop
0x18004ccaa  mov     rcx, [rbp+57h+var_80]
0x18004ccae  test    rcx, rcx
0x18004ccb1  jz      short loc_18004CCC7
0x18004ccb3  mov     rax, [rcx]
0x18004ccb6  mov     edx, 1
0x18004ccbb  mov     rax, [rax+0C0h]
0x18004ccc2  call    _guard_dispatch_icall
0x18004ccc7  cmp     [rsi+10h], r14
0x18004cccb  jz      loc_18004CD62
0x18004ccd1  lea     rdx, [r15+8]
0x18004ccd5  lea     rcx, [rbp+57h+var_D0]
0x18004ccd9  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18004ccde  mov     rdx, rax
0x18004cce1  lea     rcx, [rbp+57h+var_78]
0x18004cce5  call    ?string@value@json@web@@SA?AV123@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::string(std::wstring)
0x18004ccea  mov     rbx, rax
0x18004cced  mov     rdx, [rsi+8]
0x18004ccf1  xorps   xmm0, xmm0
0x18004ccf4  movups  [rsp+120h+var_F0], xmm0
0x18004ccf9  xorps   xmm1, xmm1
0x18004ccfc  movdqu  [rsp+120h+var_E0], xmm1
0x18004cd02  mov     r8, rdi
0x18004cd05  inc     r8
0x18004cd08  cmp     [rdx+r8*2], r14w
0x18004cd0d  jnz     short loc_18004CD05
0x18004cd0f  lea     rcx, [rsp+120h+var_F0]
0x18004cd14  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18004cd19  nop
0x18004cd1a  lea     rdx, [rsp+120h+var_F0]
0x18004cd1f  lea     rcx, [rsp+120h+var_100]
0x18004cd24  call    ??Avalue@json@web@@QEAAAEAV012@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::operator[](std::wstring const &)
0x18004cd29  cmp     rax, rbx
0x18004cd2c  jz      short loc_18004CD3A
0x18004cd2e  mov     rdx, [rax]
0x18004cd31  mov     rcx, [rbx]
0x18004cd34  mov     [rax], rcx
0x18004cd37  mov     [rbx], rdx
0x18004cd3a  lea     rcx, [rsp+120h+var_F0]
0x18004cd3f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004cd44  nop
0x18004cd45  mov     rcx, [rbp+57h+var_78]
0x18004cd49  test    rcx, rcx
0x18004cd4c  jz      short loc_18004CD62
0x18004cd4e  mov     rax, [rcx]
0x18004cd51  mov     edx, 1
0x18004cd56  mov     rax, [rax+0C0h]
0x18004cd5d  call    _guard_dispatch_icall
0x18004cd62  cmp     [rsi+20h], r14
0x18004cd66  jz      loc_18004CDFD
0x18004cd6c  lea     rdx, [r15+28h]
0x18004cd70  lea     rcx, [rbp+57h+var_D0]
0x18004cd74  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18004cd79  mov     rdx, rax
0x18004cd7c  lea     rcx, [rbp+57h+var_70]
0x18004cd80  call    ?string@value@json@web@@SA?AV123@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::string(std::wstring)
0x18004cd85  mov     rbx, rax
0x18004cd88  mov     rdx, [rsi+18h]
0x18004cd8c  xorps   xmm0, xmm0
0x18004cd8f  movups  [rsp+120h+var_F0], xmm0
0x18004cd94  xorps   xmm1, xmm1
0x18004cd97  movdqu  [rsp+120h+var_E0], xmm1
0x18004cd9d  mov     r8, rdi
0x18004cda0  inc     r8
0x18004cda3  cmp     [rdx+r8*2], r14w
0x18004cda8  jnz     short loc_18004CDA0
0x18004cdaa  lea     rcx, [rsp+120h+var_F0]
0x18004cdaf  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18004cdb4  nop
0x18004cdb5  lea     rdx, [rsp+120h+var_F0]
0x18004cdba  lea     rcx, [rsp+120h+var_100]
0x18004cdbf  call    ??Avalue@json@web@@QEAAAEAV012@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::operator[](std::wstring const &)
0x18004cdc4  cmp     rax, rbx
0x18004cdc7  jz      short loc_18004CDD5
0x18004cdc9  mov     rdx, [rax]
0x18004cdcc  mov     rcx, [rbx]
0x18004cdcf  mov     [rax], rcx
0x18004cdd2  mov     [rbx], rdx
0x18004cdd5  lea     rcx, [rsp+120h+var_F0]
0x18004cdda  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004cddf  nop
0x18004cde0  mov     rcx, [rbp+57h+var_70]
0x18004cde4  test    rcx, rcx
0x18004cde7  jz      short loc_18004CDFD
0x18004cde9  mov     rax, [rcx]
0x18004cdec  mov     edx, 1
0x18004cdf1  mov     rax, [rax+0C0h]
0x18004cdf8  call    _guard_dispatch_icall
0x18004cdfd  cmp     [rsi+30h], r14
0x18004ce01  jz      loc_18004CE98
0x18004ce07  lea     rdx, [r15+48h]
0x18004ce0b  lea     rcx, [rbp+57h+var_D0]
0x18004ce0f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18004ce14  mov     rdx, rax
0x18004ce17  lea     rcx, [rbp+57h+var_68]
0x18004ce1b  call    ?string@value@json@web@@SA?AV123@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::string(std::wstring)
0x18004ce20  mov     rbx, rax
0x18004ce23  mov     rdx, [rsi+28h]
0x18004ce27  xorps   xmm0, xmm0
0x18004ce2a  movups  [rsp+120h+var_F0], xmm0
0x18004ce2f  xorps   xmm1, xmm1
0x18004ce32  movdqu  [rsp+120h+var_E0], xmm1
0x18004ce38  mov     r8, rdi
0x18004ce3b  inc     r8
0x18004ce3e  cmp     [rdx+r8*2], r14w
0x18004ce43  jnz     short loc_18004CE3B
0x18004ce45  lea     rcx, [rsp+120h+var_F0]
0x18004ce4a  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18004ce4f  nop
0x18004ce50  lea     rdx, [rsp+120h+var_F0]
0x18004ce55  lea     rcx, [rsp+120h+var_100]
0x18004ce5a  call    ??Avalue@json@web@@QEAAAEAV012@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::operator[](std::wstring const &)
0x18004ce5f  cmp     rax, rbx
0x18004ce62  jz      short loc_18004CE70
0x18004ce64  mov     rdx, [rax]
0x18004ce67  mov     rcx, [rbx]
0x18004ce6a  mov     [rax], rcx
0x18004ce6d  mov     [rbx], rdx
0x18004ce70  lea     rcx, [rsp+120h+var_F0]
0x18004ce75  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004ce7a  nop
0x18004ce7b  mov     rcx, [rbp+57h+var_68]
0x18004ce7f  test    rcx, rcx
0x18004ce82  jz      short loc_18004CE98
0x18004ce84  mov     rax, [rcx]
0x18004ce87  mov     edx, 1
0x18004ce8c  mov     rax, [rax+0C0h]
0x18004ce93  call    _guard_dispatch_icall
0x18004ce98  mov     rbx, [r15+70h]
0x18004ce9c  mov     rdi, [rbx]
0x18004ce9f  cmp     [r15+0E8h], r14b
0x18004cea6  jz      short loc_18004CF15
0x18004cea8  cmp     rdi, rbx
0x18004ceab  jz      loc_18004CF84
0x18004ceb1  lea     rdx, [rdi+30h]
0x18004ceb5  lea     rcx, [rbp+57h+var_D0]
0x18004ceb9  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18004cebe  mov     rdx, rax
0x18004cec1  lea     rcx, [rbp+57h+var_60]
0x18004cec5  call    ?string@value@json@web@@SA?AV123@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::string(std::wstring)
0x18004ceca  mov     r12, rax
0x18004cecd  lea     rdx, [rdi+10h]
0x18004ced1  lea     rcx, [rsp+120h+var_100]
0x18004ced6  call    ??Avalue@json@web@@QEAAAEAV012@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::operator[](std::wstring const &)
0x18004cedb  cmp     rax, r12
0x18004cede  jz      short loc_18004CEEE
0x18004cee0  mov     rdx, [rax]
0x18004cee3  mov     rcx, [r12]
0x18004cee7  mov     [rax], rcx
0x18004ceea  mov     [r12], rdx
0x18004ceee  mov     rcx, [rbp+57h+var_60]
0x18004cef2  test    rcx, rcx
0x18004cef5  jz      short loc_18004CF0B
0x18004cef7  mov     rax, [rcx]
0x18004cefa  mov     edx, 1
  ... truncated ...
```
