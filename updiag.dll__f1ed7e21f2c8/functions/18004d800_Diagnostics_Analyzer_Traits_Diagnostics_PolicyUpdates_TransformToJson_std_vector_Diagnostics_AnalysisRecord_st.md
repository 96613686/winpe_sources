# Diagnostics::Analyzer_Traits<Diagnostics::PolicyUpdates>::TransformToJson(std::vector<Diagnostics::AnalysisRecord,std::allocator<Diagnostics::AnalysisRecord>> const &,Diagnostics::TraitsConfig const &)

- ea: `0x18004d800`
- end: `0x18004e08d`
- name: `?TransformToJson@?$Analyzer_Traits@UPolicyUpdates@Diagnostics@@@Diagnostics@@AEBA?AV?$optional@Vvalue@json@web@@@std@@AEBV?$vector@UAnalysisRecord@Diagnostics@@V?$allocator@UAnalysisRecord@Diagnostics@@@std@@@4@AEBUTraitsConfig@2@@Z`
- size: `2189`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180040930`

## callees

- `0x180018b04`
- `0x180018eec`
- `0x180019080`
- `0x18001adcc`
- `0x18001f520`
- `0x180028b18`
- `0x180028b98`
- `0x18003870c`
- `0x18004d800`
- `0x1800566c0`
- `0x18005873c`
- `0x18005ad30`
- `0x18005e018`
- `0x18005f12c`
- `0x180072de4`
- `0x180072eb0`
- `0x180072f30`
- `0x180072fa0`
- `0x1800731f0`
- `0x180073294`
- `0x18008fe00`
- `0x180096170`

## string_xrefs

- `0x18004da21`: `Outcome`

## pseudocode

```c
// Hidden C++ exception states: #wind=22
__int64 __fastcall Diagnostics::Analyzer_Traits<Diagnostics::PolicyUpdates>::TransformToJson(
        __int64 a1,
        __int64 a2,
        __int64 *a3,
        _BYTE *a4)
{
  _BYTE *v4; // rdi
  __int64 v6; // r12
  unsigned __int64 v7; // r14
  __int64 v8; // r13
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
  _QWORD **v40; // rdi
  _QWORD *i; // rbx
  __int64 v42; // rax
  __int64 *v43; // r15
  __int64 *v44; // rax
  __int64 v45; // rdx
  wchar_t **v46; // rbx
  __int64 *v47; // rdi
  __int64 *v48; // rax
  __int64 v49; // rdx
  __int64 v50; // rsi
  bool v51; // zf
  __int64 v52; // rax
  __int64 *v53; // rax
  __int64 v54; // rdx
  __int64 v55; // r8
  __int64 v56; // rbx
  __int64 v57; // rdi
  __int64 v58; // rcx
  __int128 *p_Src; // rax
  __int64 v60; // r9
  _QWORD *v61; // rax
  unsigned __int64 v62; // rbx
  unsigned __int64 v63; // rdi
  __int64 **v64; // rax
  __int64 v65; // r9
  _QWORD *v66; // rcx
  __int64 v67; // rcx
  __int64 v68; // rbx
  __int64 v69; // rax
  __int64 v71; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v72[2]; // [rsp+38h] [rbp-C8h] BYREF
  _OWORD v73[2]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v74; // [rsp+68h] [rbp-98h]
  _QWORD v75[3]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v76; // [rsp+88h] [rbp-78h] BYREF
  __int64 v77; // [rsp+90h] [rbp-70h] BYREF
  __int64 v78; // [rsp+98h] [rbp-68h] BYREF
  __int64 v79; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v80; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v81; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v82; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v83; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v84; // [rsp+C8h] [rbp-38h]
  __int128 Src; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v86; // [rsp+E0h] [rbp-20h]
  __int128 v87; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v88; // [rsp+100h] [rbp+0h]
  _BYTE v89[32]; // [rsp+108h] [rbp+8h] BYREF
  char v90; // [rsp+128h] [rbp+28h]

  v4 = a4;
  v72[0] = a4;
  v6 = a2;
  v84 = a2;
  v74 = a2;
  v7 = 0;
  v87 = 0;
  v88 = 0;
  std::vector<web::json::value>::reserve(&v87, 0xAF8AF8AF8AF8AF8BuLL * ((a3[1] - *a3) >> 3));
  v8 = *a3;
  v74 = a3[1];
  if ( v8 != v74 )
  {
    v9 = v72[0];
    while ( 1 )
    {
      v71 = 0;
      web::json::value::object(&v71, 0);
      if ( *(_BYTE *)(v9 + 3) && *(_QWORD *)(v8 + 184) )
      {
        v10 = std::wstring::wstring((__int64)v73, v8 + 168);
        v11 = (__int64 *)web::json::value::string(&v76, v10);
        Src = 0;
        v86 = 0;
        std::wstring::_Construct<1,wchar_t const *>(&Src, L"Event", 5u);
        v12 = (__int64 *)web::json::value::operator[](&v71, &Src);
        if ( v12 != v11 )
        {
          v13 = *v12;
          *v12 = *v11;
          *v11 = v13;
        }
        std::wstring::~wstring((__int64)&Src);
        if ( v76 )
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v76 + 192LL))(v76, 1);
      }
      if ( *(_BYTE *)(v8 + 232) )
      {
        v14 = std::wstring::wstring((__int64)v73, v8 + 200);
        v15 = (__int64 *)web::json::value::string(&v77, v14);
        Src = 0;
        v86 = 0;
        std::wstring::_Construct<1,wchar_t const *>(&Src, L"Event", 5u);
        v16 = (__int64 *)web::json::value::operator[](&v71, &Src);
        if ( v16 != v15 )
        {
          v17 = *v16;
          *v16 = *v15;
          *v15 = v17;
        }
        std::wstring::~wstring((__int64)&Src);
        if ( v77 )
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v77 + 192LL))(v77, 1);
      }
      if ( *(_BYTE *)(v8 + 272) )
      {
        v18 = std::wstring::wstring((__int64)v73, v8 + 240);
        v19 = (__int64 *)web::json::value::string(&v78, v18);
        Src = 0;
        v86 = 0;
        std::wstring::_Construct<1,wchar_t const *>(&Src, L"Outcome", 7u);
        v20 = (__int64 *)web::json::value::operator[](&v71, &Src);
        if ( v20 != v19 )
        {
          v21 = *v20;
          *v20 = *v19;
          *v19 = v21;
        }
        std::wstring::~wstring((__int64)&Src);
        if ( v78 )
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v78 + 192LL))(v78, 1);
      }
      if ( *(_QWORD *)(v9 + 16) )
      {
        v22 = std::wstring::wstring((__int64)v73, v8 + 8);
        v23 = (__int64 *)web::json::value::string(&v79, v22);
        v24 = *(_WORD **)(v9 + 8);
        Src = 0;
        v86 = 0;
        v25 = -1;
        do
          ++v25;
        while ( v24[v25] );
        std::wstring::_Construct<1,wchar_t const *>(&Src, v24, v25);
        v26 = (__int64 *)web::json::value::operator[](&v71, &Src);
        if ( v26 != v23 )
        {
          v27 = *v26;
          *v26 = *v23;
          *v23 = v27;
        }
        std::wstring::~wstring((__int64)&Src);
        if ( v79 )
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v79 + 192LL))(v79, 1);
      }
      if ( *(_QWORD *)(v9 + 32) )
      {
        v28 = std::wstring::wstring((__int64)v73, v8 + 40);
        v29 = (__int64 *)web::json::value::string(&v80, v28);
        v30 = *(_WORD **)(v9 + 24);
        Src = 0;
        v86 = 0;
        v31 = -1;
        do
          ++v31;
        while ( v30[v31] );
        std::wstring::_Construct<1,wchar_t const *>(&Src, v30, v31);
        v32 = (__int64 *)web::json::value::operator[](&v71, &Src);
        if ( v32 != v29 )
        {
          v33 = *v32;
          *v32 = *v29;
          *v29 = v33;
        }
        std::wstring::~wstring((__int64)&Src);
        if ( v80 )
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v80 + 192LL))(v80, 1);
      }
      if ( *(_QWORD *)(v9 + 48) )
      {
        v34 = std::wstring::wstring((__int64)v73, v8 + 72);
        v35 = (__int64 *)web::json::value::string(&v81, v34);
        v36 = *(_WORD **)(v9 + 40);
        Src = 0;
        v86 = 0;
        v37 = -1;
        do
          ++v37;
        while ( v36[v37] );
        std::wstring::_Construct<1,wchar_t const *>(&Src, v36, v37);
        v38 = (__int64 *)web::json::value::operator[](&v71, &Src);
        if ( v38 != v35 )
        {
          v39 = *v38;
          *v38 = *v35;
          *v35 = v39;
        }
        std::wstring::~wstring((__int64)&Src);
        if ( v81 )
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v81 + 192LL))(v81, 1);
      }
      if ( *(_BYTE *)(v8 + 232) )
      {
        v40 = *(_QWORD ***)(v8 + 112);
        for ( i = *v40; i != v40; i = (_QWORD *)*i )
        {
          v42 = std::wstring::wstring((__int64)v73, (__int64)(i + 6));
          v43 = (__int64 *)web::json::value::string(&v82, v42);
          v44 = (__int64 *)web::json::value::operator[](&v71, i + 2);
          if ( v44 != v43 )
          {
            v45 = *v44;
            *v44 = *v43;
            *v43 = v45;
          }
          if ( v82 )
            (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v82 + 192LL))(v82, 1);
        }
      }
      else
      {
        v46 = &Diagnostics::PolicyUpdates::select;
        do
        {
          Src = 0;
          v86 = 0;
          std::wstring::_Construct<1,wchar_t const *>(&Src, *v46, (unsigned __int64)v46[1]);
          Diagnostics::AnalysisRecord::GetField(v8, v89, &Src);
          std::wstring::~wstring((__int64)&Src);
          if ( v90 )
          {
            std::wstring::wstring((__int64)&Src, (__int64)v89);
          }
          else
          {
            Src = 0;
            v86 = 0u;
            std::wstring::_Construct<1,wchar_t const *>(&Src, &psz, 0);
          }
          v47 = (__int64 *)web::json::value::string(&v83, &Src);
          memset(v73, 0, sizeof(v73));
          std::wstring::_Construct<1,wchar_t const *>(v73, v46[2], (unsigned __int64)v46[3]);
          v48 = (__int64 *)web::json::value::operator[](&v71, v73);
          if ( v48 != v47 )
          {
            v49 = *v48;
            *v48 = *v47;
            *v47 = v49;
          }
          std::wstring::~wstring((__int64)v73);
          if ( v83 )
            (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v83 + 192LL))(v83, 1);
          if ( v90 )
            std::wstring::~wstring((__int64)v89);
          v46 += 4;
        }
        while ( v46 != (wchar_t **)&Diagnostics::UpdateErrorsFull::config );
      }
      Diagnostics::Analyzer_Traits<Diagnostics::PolicyUpdates>::TryApplyArrayExpansion(&v71);
      Src = 0;
      *(_QWORD *)&v86 = 0;
      *((_QWORD *)&v86 + 1) = 7;
      LOWORD(Src) = 0;
      v75[0] = &Diagnostics::PolicyUpdates::fieldTransforms;
      v75[1] = 1;
      v50 = v71;
      v51 = (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v71 + 88LL))(v71) == 3;
      v52 = *(_QWORD *)v50;
      if ( v51 )
      {
        v53 = (__int64 *)(*(__int64 (__fastcall **)(__int64))(v52 + 168))(v50);
        v56 = *v53;
        v57 = v53[1];
        if ( *v53 != v57 )
        {
          do
          {
            v58 = v86;
            if ( (_QWORD)v86 )
            {
              if ( (unsigned __int64)v86 >= *((_QWORD *)&v86 + 1) )
              {
                ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__QEAAXG_Z_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXG_Z_G_Z(
                  &Src,
                  v54,
                  v55,
                  47);
              }
              else
              {
                *(_QWORD *)&v86 = v86 + 1;
                p_Src = &Src;
                if ( *((_QWORD *)&v86 + 1) > 7u )
                  p_Src = (__int128 *)Src;
                *(_DWORD *)((char *)p_Src + 2 * v58) = 47;
              }
            }
            std::wstring::append(&Src);
            ___TraverseJson_AEAV_lambda_1___1__TryApplyFieldTransforms___Analyzer_Traits_UDeviceIdentity_Diagnostics___Diagnostics__CAXAEAVvalue_json_web__V__span___CBUFieldTransform_Diagnostics___0_0_std___Z____Analyzer_Traits_UDeviceIdentity_Diagnostics___Diagnostics__CAXAEAV_lambda_1___1__TryApplyFieldTransforms_01_CAXAEAVvalue_json_web__V__span___CBUFieldTransform_Diagnostics___0_0_std___Z_0AEAV__basic_string__WU__char_traits__W_std__V__allocator__W_2__8__WH_Z(
              (__int64)v75,
              (__int64 **)(v56 + 32),
              &Src,
              v60,
              9);
            std::wstring::resize(&Src);
            v56 += 40;
          }
          while ( v56 != v57 );
          v9 = v72[0];
        }
        goto LABEL_76;
      }
      if ( (*(unsigned int (__fastcall **)(__int64))(v52 + 88))(v50) != 4 )
        break;
      v61 = (_QWORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v50 + 152LL))(v50);
      v62 = (__int64)(v61[1] - *v61) >> 3;
      v63 = 0;
      if ( v62 )
      {
        do
        {
          v64 = (__int64 **)web::json::value::operator[](&v71, v63);
          ___TraverseJson_AEAV_lambda_1___1__TryApplyFieldTransforms___Analyzer_Traits_UDeviceIdentity_Diagnostics___Diagnostics__CAXAEAVvalue_json_web__V__span___CBUFieldTransform_Diagnostics___0_0_std___Z____Analyzer_Traits_UDeviceIdentity_Diagnostics___Diagnostics__CAXAEAV_lambda_1___1__TryApplyFieldTransforms_01_CAXAEAVvalue_json_web__V__span___CBUFieldTransform_Diagnostics___0_0_std___Z_0AEAV__basic_string__WU__char_traits__W_std__V__allocator__W_2__8__WH_Z(
            (__int64)v75,
            v64,
            &Src,
            v65,
            9);
          ++v63;
        }
        while ( v63 < v62 );
        goto LABEL_75;
      }
LABEL_76:
      std::wstring::~wstring((__int64)&Src);
      if ( *((_QWORD *)&v87 + 1) == v88 )
      {
        std::vector<web::json::value>::_Emplace_reallocate<web::json::value>(&v87, *((__int64 **)&v87 + 1), &v71);
      }
      else
      {
        v71 = 0;
        **((_QWORD **)&v87 + 1) = v50;
        *((_QWORD *)&v87 + 1) += 8LL;
      }
      if ( v71 )
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v71 + 192LL))(v71, 1);
      v8 += 280;
      if ( v8 == v74 )
      {
        v6 = v84;
        v4 = (_BYTE *)v72[0];
        goto LABEL_83;
      }
    }
    `Diagnostics::Analyzer_Traits<Diagnostics::PolicyUpdates>::TryApplyFieldTransforms'::`2'::_lambda_1_::operator()(
      v75,
      &Src,
      &v71);
LABEL_75:
    v50 = v71;
    goto LABEL_76;
  }
LABEL_83:
  if ( v4[1] )
  {
    if ( *v4 )
      v66 = (_QWORD *)v87;
    else
      v66 = (_QWORD *)(*((_QWORD *)&v87 + 1) - 8LL);
    (**(void (__fastcall ***)(_QWORD, __int64))*v66)(*v66, v6);
    *(_BYTE *)(v6 + 8) = 1;
  }
  else
  {
    v72[0] = 0;
    web::json::value::array(v72);
    v67 = v87;
    if ( (__int64)(*((_QWORD *)&v87 + 1) - v87) >> 3 )
    {
      do
      {
        v68 = v67 + 8 * v7;
        v69 = web::json::value::operator[](v72, v7);
        web::json::value::operator=(v69, v68);
        ++v7;
        v67 = v87;
      }
      while ( v7 < (__int64)(*((_QWORD *)&v87 + 1) - v87) >> 3 );
    }
    *(_QWORD *)v6 = v72[0];
    *(_BYTE *)(v6 + 8) = 1;
  }
  std::vector<web::json::value>::_Tidy(&v87);
  return v6;
}

```

## disassembly

```asm
0x18004d800  mov     [rsp-8+arg_0], rbx
0x18004d805  push    rbp
0x18004d806  push    rsi
0x18004d807  push    rdi
0x18004d808  push    r12
0x18004d80a  push    r13
0x18004d80c  push    r14
0x18004d80e  push    r15
0x18004d810  lea     rbp, [rsp-40h]
0x18004d815  sub     rsp, 140h
0x18004d81c  mov     rax, cs:__security_cookie
0x18004d823  xor     rax, rsp
0x18004d826  mov     [rbp+70h+var_40], rax
0x18004d82a  mov     rdi, r9
0x18004d82d  mov     [rsp+170h+var_138], r9
0x18004d832  mov     rbx, r8
0x18004d835  mov     r12, rdx
0x18004d838  mov     [rbp+70h+var_A8], rdx
0x18004d83c  mov     [rsp+170h+var_108], rdx
0x18004d841  xor     r14d, r14d
0x18004d844  xorps   xmm1, xmm1
0x18004d847  movdqu  [rbp+70h+var_80], xmm1
0x18004d84c  mov     [rbp+70h+var_70], r14
0x18004d850  mov     rdx, [r8+8]
0x18004d854  sub     rdx, [r8]
0x18004d857  sar     rdx, 3
0x18004d85b  mov     rax, 0AF8AF8AF8AF8AF8Bh
0x18004d865  imul    rdx, rax
0x18004d869  lea     rcx, [rbp+70h+var_80]
0x18004d86d  call    ?reserve@?$vector@Vvalue@json@web@@V?$allocator@Vvalue@json@web@@@std@@@std@@QEAAX_K@Z; std::vector<web::json::value>::reserve(unsigned __int64)
0x18004d872  mov     r13, [rbx]
0x18004d875  mov     rax, [rbx+8]
0x18004d879  mov     [rsp+170h+var_108], rax
0x18004d87e  cmp     r13, rax
0x18004d881  jz      loc_18004DFC2
0x18004d887  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18004d88b  mov     r12, [rsp+170h+var_138]
0x18004d890  mov     [rsp+170h+var_140], r14
0x18004d895  xor     edx, edx
0x18004d897  lea     rcx, [rsp+170h+var_140]
0x18004d89c  call    ?object@value@json@web@@SA?AV123@_N@Z; web::json::value::object(bool)
0x18004d8a1  nop
0x18004d8a2  cmp     [r12+3], r14b
0x18004d8a7  jz      loc_18004D946
0x18004d8ad  cmp     [r13+0B8h], r14
0x18004d8b4  jz      loc_18004D946
0x18004d8ba  lea     rdx, [r13+0A8h]
0x18004d8c1  lea     rcx, [rsp+170h+var_128]
0x18004d8c6  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18004d8cb  mov     rdx, rax
0x18004d8ce  lea     rcx, [rbp+70h+var_E8]
0x18004d8d2  call    ?string@value@json@web@@SA?AV123@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::string(std::wstring)
0x18004d8d7  mov     rbx, rax
0x18004d8da  xorps   xmm0, xmm0
0x18004d8dd  movups  [rbp+70h+Src], xmm0
0x18004d8e1  xorps   xmm1, xmm1
0x18004d8e4  movdqu  [rbp+70h+var_90], xmm1
0x18004d8e9  mov     r8d, 5
0x18004d8ef  lea     rdx, aEvent_0; "Event"
0x18004d8f6  lea     rcx, [rbp+70h+Src]
0x18004d8fa  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18004d8ff  nop
0x18004d900  lea     rdx, [rbp+70h+Src]
0x18004d904  lea     rcx, [rsp+170h+var_140]
0x18004d909  call    ??Avalue@json@web@@QEAAAEAV012@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::operator[](std::wstring const &)
0x18004d90e  cmp     rax, rbx
0x18004d911  jz      short loc_18004D91F
0x18004d913  mov     rdx, [rax]
0x18004d916  mov     rcx, [rbx]
0x18004d919  mov     [rax], rcx
0x18004d91c  mov     [rbx], rdx
0x18004d91f  lea     rcx, [rbp+70h+Src]
0x18004d923  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004d928  nop
0x18004d929  mov     rcx, [rbp+70h+var_E8]
0x18004d92d  test    rcx, rcx
0x18004d930  jz      short loc_18004D946
0x18004d932  mov     rax, [rcx]
0x18004d935  mov     edx, 1
0x18004d93a  mov     rax, [rax+0C0h]
0x18004d941  call    _guard_dispatch_icall
0x18004d946  cmp     [r13+0E8h], r14b
0x18004d94d  jz      loc_18004D9DF
0x18004d953  lea     rdx, [r13+0C8h]
0x18004d95a  lea     rcx, [rsp+170h+var_128]
0x18004d95f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18004d964  mov     rdx, rax
0x18004d967  lea     rcx, [rbp+70h+var_E0]
0x18004d96b  call    ?string@value@json@web@@SA?AV123@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::string(std::wstring)
0x18004d970  mov     rbx, rax
0x18004d973  xorps   xmm0, xmm0
0x18004d976  movups  [rbp+70h+Src], xmm0
0x18004d97a  xorps   xmm1, xmm1
0x18004d97d  movdqu  [rbp+70h+var_90], xmm1
0x18004d982  mov     r8d, 5
0x18004d988  lea     rdx, aEvent_0; "Event"
0x18004d98f  lea     rcx, [rbp+70h+Src]
0x18004d993  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18004d998  nop
0x18004d999  lea     rdx, [rbp+70h+Src]
0x18004d99d  lea     rcx, [rsp+170h+var_140]
0x18004d9a2  call    ??Avalue@json@web@@QEAAAEAV012@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::operator[](std::wstring const &)
0x18004d9a7  cmp     rax, rbx
0x18004d9aa  jz      short loc_18004D9B8
0x18004d9ac  mov     rdx, [rax]
0x18004d9af  mov     rcx, [rbx]
0x18004d9b2  mov     [rax], rcx
0x18004d9b5  mov     [rbx], rdx
0x18004d9b8  lea     rcx, [rbp+70h+Src]
0x18004d9bc  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004d9c1  nop
0x18004d9c2  mov     rcx, [rbp+70h+var_E0]
0x18004d9c6  test    rcx, rcx
0x18004d9c9  jz      short loc_18004D9DF
0x18004d9cb  mov     rax, [rcx]
0x18004d9ce  mov     edx, 1
0x18004d9d3  mov     rax, [rax+0C0h]
0x18004d9da  call    _guard_dispatch_icall
0x18004d9df  cmp     [r13+110h], r14b
0x18004d9e6  jz      loc_18004DA78
0x18004d9ec  lea     rdx, [r13+0F0h]
0x18004d9f3  lea     rcx, [rsp+170h+var_128]
0x18004d9f8  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18004d9fd  mov     rdx, rax
0x18004da00  lea     rcx, [rbp+70h+var_D8]
0x18004da04  call    ?string@value@json@web@@SA?AV123@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::string(std::wstring)
0x18004da09  mov     rbx, rax
0x18004da0c  xorps   xmm0, xmm0
0x18004da0f  movups  [rbp+70h+Src], xmm0
0x18004da13  xorps   xmm1, xmm1
0x18004da16  movdqu  [rbp+70h+var_90], xmm1
0x18004da1b  mov     r8d, 7
0x18004da21  lea     rdx, aOutcome; "Outcome"
0x18004da28  lea     rcx, [rbp+70h+Src]
0x18004da2c  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18004da31  nop
0x18004da32  lea     rdx, [rbp+70h+Src]
0x18004da36  lea     rcx, [rsp+170h+var_140]
0x18004da3b  call    ??Avalue@json@web@@QEAAAEAV012@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::operator[](std::wstring const &)
0x18004da40  cmp     rax, rbx
0x18004da43  jz      short loc_18004DA51
0x18004da45  mov     rdx, [rax]
0x18004da48  mov     rcx, [rbx]
0x18004da4b  mov     [rax], rcx
0x18004da4e  mov     [rbx], rdx
0x18004da51  lea     rcx, [rbp+70h+Src]
0x18004da55  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004da5a  nop
0x18004da5b  mov     rcx, [rbp+70h+var_D8]
0x18004da5f  test    rcx, rcx
0x18004da62  jz      short loc_18004DA78
0x18004da64  mov     rax, [rcx]
0x18004da67  mov     edx, 1
0x18004da6c  mov     rax, [rax+0C0h]
0x18004da73  call    _guard_dispatch_icall
0x18004da78  cmp     [r12+10h], r14
0x18004da7d  jz      loc_18004DB11
0x18004da83  lea     rdx, [r13+8]
0x18004da87  lea     rcx, [rsp+170h+var_128]
0x18004da8c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18004da91  mov     rdx, rax
0x18004da94  lea     rcx, [rbp+70h+var_D0]
0x18004da98  call    ?string@value@json@web@@SA?AV123@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::string(std::wstring)
0x18004da9d  mov     rbx, rax
0x18004daa0  mov     rdx, [r12+8]
0x18004daa5  xorps   xmm0, xmm0
0x18004daa8  movups  [rbp+70h+Src], xmm0
0x18004daac  xorps   xmm1, xmm1
0x18004daaf  movdqu  [rbp+70h+var_90], xmm1
0x18004dab4  mov     r8, rdi
0x18004dab7  inc     r8
0x18004daba  cmp     [rdx+r8*2], r14w
0x18004dabf  jnz     short loc_18004DAB7
0x18004dac1  lea     rcx, [rbp+70h+Src]
0x18004dac5  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18004daca  nop
0x18004dacb  lea     rdx, [rbp+70h+Src]
0x18004dacf  lea     rcx, [rsp+170h+var_140]
0x18004dad4  call    ??Avalue@json@web@@QEAAAEAV012@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::operator[](std::wstring const &)
0x18004dad9  cmp     rax, rbx
0x18004dadc  jz      short loc_18004DAEA
0x18004dade  mov     rdx, [rax]
0x18004dae1  mov     rcx, [rbx]
0x18004dae4  mov     [rax], rcx
0x18004dae7  mov     [rbx], rdx
0x18004daea  lea     rcx, [rbp+70h+Src]
0x18004daee  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004daf3  nop
0x18004daf4  mov     rcx, [rbp+70h+var_D0]
0x18004daf8  test    rcx, rcx
0x18004dafb  jz      short loc_18004DB11
0x18004dafd  mov     rax, [rcx]
0x18004db00  mov     edx, 1
0x18004db05  mov     rax, [rax+0C0h]
0x18004db0c  call    _guard_dispatch_icall
0x18004db11  cmp     [r12+20h], r14
0x18004db16  jz      loc_18004DBAA
0x18004db1c  lea     rdx, [r13+28h]
0x18004db20  lea     rcx, [rsp+170h+var_128]
0x18004db25  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18004db2a  mov     rdx, rax
0x18004db2d  lea     rcx, [rbp+70h+var_C8]
0x18004db31  call    ?string@value@json@web@@SA?AV123@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::string(std::wstring)
0x18004db36  mov     rbx, rax
0x18004db39  mov     rdx, [r12+18h]
0x18004db3e  xorps   xmm0, xmm0
0x18004db41  movups  [rbp+70h+Src], xmm0
0x18004db45  xorps   xmm1, xmm1
0x18004db48  movdqu  [rbp+70h+var_90], xmm1
0x18004db4d  mov     r8, rdi
0x18004db50  inc     r8
0x18004db53  cmp     [rdx+r8*2], r14w
0x18004db58  jnz     short loc_18004DB50
0x18004db5a  lea     rcx, [rbp+70h+Src]
0x18004db5e  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18004db63  nop
0x18004db64  lea     rdx, [rbp+70h+Src]
0x18004db68  lea     rcx, [rsp+170h+var_140]
0x18004db6d  call    ??Avalue@json@web@@QEAAAEAV012@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::operator[](std::wstring const &)
0x18004db72  cmp     rax, rbx
0x18004db75  jz      short loc_18004DB83
0x18004db77  mov     rdx, [rax]
0x18004db7a  mov     rcx, [rbx]
0x18004db7d  mov     [rax], rcx
0x18004db80  mov     [rbx], rdx
0x18004db83  lea     rcx, [rbp+70h+Src]
0x18004db87  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004db8c  nop
0x18004db8d  mov     rcx, [rbp+70h+var_C8]
0x18004db91  test    rcx, rcx
0x18004db94  jz      short loc_18004DBAA
0x18004db96  mov     rax, [rcx]
0x18004db99  mov     edx, 1
0x18004db9e  mov     rax, [rax+0C0h]
0x18004dba5  call    _guard_dispatch_icall
0x18004dbaa  cmp     [r12+30h], r14
0x18004dbaf  jz      loc_18004DC43
0x18004dbb5  lea     rdx, [r13+48h]
0x18004dbb9  lea     rcx, [rsp+170h+var_128]
0x18004dbbe  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18004dbc3  mov     rdx, rax
0x18004dbc6  lea     rcx, [rbp+70h+var_C0]
0x18004dbca  call    ?string@value@json@web@@SA?AV123@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::string(std::wstring)
0x18004dbcf  mov     rbx, rax
0x18004dbd2  mov     rdx, [r12+28h]
0x18004dbd7  xorps   xmm0, xmm0
0x18004dbda  movups  [rbp+70h+Src], xmm0
0x18004dbde  xorps   xmm1, xmm1
0x18004dbe1  movdqu  [rbp+70h+var_90], xmm1
0x18004dbe6  mov     r8, rdi
0x18004dbe9  inc     r8
0x18004dbec  cmp     [rdx+r8*2], r14w
0x18004dbf1  jnz     short loc_18004DBE9
0x18004dbf3  lea     rcx, [rbp+70h+Src]
0x18004dbf7  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18004dbfc  nop
0x18004dbfd  lea     rdx, [rbp+70h+Src]
0x18004dc01  lea     rcx, [rsp+170h+var_140]
0x18004dc06  call    ??Avalue@json@web@@QEAAAEAV012@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::operator[](std::wstring const &)
0x18004dc0b  cmp     rax, rbx
0x18004dc0e  jz      short loc_18004DC1C
0x18004dc10  mov     rdx, [rax]
0x18004dc13  mov     rcx, [rbx]
0x18004dc16  mov     [rax], rcx
0x18004dc19  mov     [rbx], rdx
0x18004dc1c  lea     rcx, [rbp+70h+Src]
0x18004dc20  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004dc25  nop
0x18004dc26  mov     rcx, [rbp+70h+var_C0]
0x18004dc2a  test    rcx, rcx
0x18004dc2d  jz      short loc_18004DC43
0x18004dc2f  mov     rax, [rcx]
0x18004dc32  mov     edx, 1
0x18004dc37  mov     rax, [rax+0C0h]
0x18004dc3e  call    _guard_dispatch_icall
0x18004dc43  cmp     [r13+0E8h], r14b
0x18004dc4a  jz      short loc_18004DCBB
0x18004dc4c  mov     rdi, [r13+70h]
0x18004dc50  mov     rbx, [rdi]
0x18004dc53  jmp     short loc_18004DCB1
0x18004dc55  lea     rdx, [rbx+30h]
0x18004dc59  lea     rcx, [rsp+170h+var_128]
0x18004dc5e  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18004dc63  mov     rdx, rax
0x18004dc66  lea     rcx, [rbp+70h+var_B8]
0x18004dc6a  call    ?string@value@json@web@@SA?AV123@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::string(std::wstring)
0x18004dc6f  mov     r15, rax
0x18004dc72  lea     rdx, [rbx+10h]
0x18004dc76  lea     rcx, [rsp+170h+var_140]
0x18004dc7b  call    ??Avalue@json@web@@QEAAAEAV012@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::operator[](std::wstring const &)
0x18004dc80  cmp     rax, r15
0x18004dc83  jz      short loc_18004DC91
0x18004dc85  mov     rdx, [rax]
0x18004dc88  mov     rcx, [r15]
0x18004dc8b  mov     [rax], rcx
0x18004dc8e  mov     [r15], rdx
0x18004dc91  mov     rcx, [rbp+70h+var_B8]
0x18004dc95  test    rcx, rcx
0x18004dc98  jz      short loc_18004DCAE
0x18004dc9a  mov     rax, [rcx]
  ... truncated ...
```
