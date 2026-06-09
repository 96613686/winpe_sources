# Diagnostics::Analyzer_Traits<Diagnostics::DeviceIdentity>::TransformToJson(std::vector<Diagnostics::AnalysisRecord,std::allocator<Diagnostics::AnalysisRecord>> const &,Diagnostics::TraitsConfig const &)

- ea: `0x18004ef24`
- end: `0x18004f7b9`
- name: `?TransformToJson@?$Analyzer_Traits@UDeviceIdentity@Diagnostics@@@Diagnostics@@AEBA?AV?$optional@Vvalue@json@web@@@std@@AEBV?$vector@UAnalysisRecord@Diagnostics@@V?$allocator@UAnalysisRecord@Diagnostics@@@std@@@4@AEBUTraitsConfig@2@@Z`
- size: `2197`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800411f0`

## callees

- `0x180018b04`
- `0x180018eec`
- `0x180019080`
- `0x18001adcc`
- `0x18001f520`
- `0x180028b18`
- `0x180028b98`
- `0x18003870c`
- `0x18004ef24`
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

- `0x18004f14d`: `Outcome`

## pseudocode

```c
// Hidden C++ exception states: #wind=31
__int64 __fastcall Diagnostics::Analyzer_Traits<Diagnostics::DeviceIdentity>::TransformToJson(
        __int64 a1,
        __int64 a2,
        __int64 *a3,
        _BYTE *a4)
{
  _BYTE *v4; // rdi
  __int64 v6; // r12
  unsigned __int64 v7; // r14
  int v8; // esi
  __int64 v9; // r13
  __int64 v10; // r12
  __int64 v11; // rax
  __int64 *v12; // rbx
  __int64 *v13; // rax
  __int64 v14; // rdx
  __int64 v15; // rax
  __int64 *v16; // rbx
  __int64 *v17; // rax
  __int64 v18; // rdx
  __int64 v19; // rax
  __int64 *v20; // rbx
  __int64 *v21; // rax
  __int64 v22; // rdx
  __int64 v23; // rax
  __int64 *v24; // rbx
  _WORD *v25; // rdx
  unsigned __int64 v26; // r8
  __int64 *v27; // rax
  __int64 v28; // rdx
  __int64 v29; // rax
  __int64 *v30; // rbx
  _WORD *v31; // rdx
  unsigned __int64 v32; // r8
  __int64 *v33; // rax
  __int64 v34; // rdx
  __int64 v35; // rax
  __int64 *v36; // rbx
  _WORD *v37; // rdx
  unsigned __int64 v38; // r8
  __int64 *v39; // rax
  __int64 v40; // rdx
  _QWORD **v41; // rdi
  _QWORD *i; // rbx
  __int64 v43; // rax
  __int64 *v44; // r15
  __int64 *v45; // rax
  __int64 v46; // rdx
  wchar_t **v47; // rbx
  __int64 *v48; // rdi
  __int64 *v49; // rax
  __int64 v50; // rdx
  __int64 v51; // rsi
  bool v52; // zf
  __int64 v53; // rax
  __int64 *v54; // rax
  __int64 v55; // rdx
  __int64 v56; // r8
  __int64 v57; // rbx
  __int64 v58; // rdi
  __int64 v59; // rcx
  __int128 *p_Src; // rax
  __int64 v61; // r9
  _QWORD *v62; // rax
  unsigned __int64 v63; // rbx
  unsigned __int64 v64; // rdi
  __int64 **v65; // rax
  __int64 v66; // r9
  _QWORD *v67; // rcx
  __int64 v68; // rcx
  __int64 v69; // rbx
  __int64 v70; // rax
  __int64 v72; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v73[2]; // [rsp+38h] [rbp-C8h] BYREF
  int v74; // [rsp+48h] [rbp-B8h]
  _OWORD v75[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v76; // [rsp+70h] [rbp-90h]
  _QWORD v77[2]; // [rsp+78h] [rbp-88h] BYREF
  __int64 v78; // [rsp+88h] [rbp-78h] BYREF
  __int64 v79; // [rsp+90h] [rbp-70h] BYREF
  __int64 v80; // [rsp+98h] [rbp-68h] BYREF
  __int64 v81; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v82; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v83; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v84; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v85; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v86; // [rsp+C8h] [rbp-38h]
  __int128 Src; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v88; // [rsp+E0h] [rbp-20h]
  __int128 v89; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v90; // [rsp+100h] [rbp+0h]
  _BYTE v91[32]; // [rsp+108h] [rbp+8h] BYREF
  char v92; // [rsp+128h] [rbp+28h]

  v4 = a4;
  v73[0] = a4;
  v6 = a2;
  v86 = a2;
  v76 = a2;
  v7 = 0;
  v8 = 0;
  v74 = 0;
  v89 = 0;
  v90 = 0;
  std::vector<web::json::value>::reserve(&v89, 0xAF8AF8AF8AF8AF8BuLL * ((a3[1] - *a3) >> 3));
  v9 = *a3;
  v76 = a3[1];
  if ( v9 != v76 )
  {
    v10 = v73[0];
    while ( 1 )
    {
      v72 = 0;
      web::json::value::object(&v72, 0);
      if ( *(_BYTE *)(v10 + 3) && *(_QWORD *)(v9 + 184) )
      {
        v11 = std::wstring::wstring((__int64)v75, v9 + 168);
        v12 = (__int64 *)web::json::value::string(&v78, v11);
        Src = 0;
        v88 = 0;
        std::wstring::_Construct<1,wchar_t const *>(&Src, L"Event", 5u);
        v13 = (__int64 *)web::json::value::operator[](&v72, &Src);
        if ( v13 != v12 )
        {
          v14 = *v13;
          *v13 = *v12;
          *v12 = v14;
        }
        std::wstring::~wstring((__int64)&Src);
        if ( v78 )
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v78 + 192LL))(v78, 1);
      }
      if ( *(_BYTE *)(v9 + 232) )
      {
        v15 = std::wstring::wstring((__int64)v75, v9 + 200);
        v16 = (__int64 *)web::json::value::string(&v79, v15);
        Src = 0;
        v88 = 0;
        std::wstring::_Construct<1,wchar_t const *>(&Src, L"Event", 5u);
        v17 = (__int64 *)web::json::value::operator[](&v72, &Src);
        if ( v17 != v16 )
        {
          v18 = *v17;
          *v17 = *v16;
          *v16 = v18;
        }
        std::wstring::~wstring((__int64)&Src);
        if ( v79 )
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v79 + 192LL))(v79, 1);
      }
      if ( *(_BYTE *)(v9 + 272) )
      {
        v19 = std::wstring::wstring((__int64)v75, v9 + 240);
        v20 = (__int64 *)web::json::value::string(&v80, v19);
        Src = 0;
        v88 = 0;
        std::wstring::_Construct<1,wchar_t const *>(&Src, L"Outcome", 7u);
        v21 = (__int64 *)web::json::value::operator[](&v72, &Src);
        if ( v21 != v20 )
        {
          v22 = *v21;
          *v21 = *v20;
          *v20 = v22;
        }
        std::wstring::~wstring((__int64)&Src);
        if ( v80 )
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v80 + 192LL))(v80, 1);
      }
      if ( *(_QWORD *)(v10 + 16) )
      {
        v23 = std::wstring::wstring((__int64)v75, v9 + 8);
        v24 = (__int64 *)web::json::value::string(&v81, v23);
        v25 = *(_WORD **)(v10 + 8);
        Src = 0;
        v88 = 0;
        v26 = -1;
        do
          ++v26;
        while ( v25[v26] );
        std::wstring::_Construct<1,wchar_t const *>(&Src, v25, v26);
        v27 = (__int64 *)web::json::value::operator[](&v72, &Src);
        if ( v27 != v24 )
        {
          v28 = *v27;
          *v27 = *v24;
          *v24 = v28;
        }
        std::wstring::~wstring((__int64)&Src);
        if ( v81 )
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v81 + 192LL))(v81, 1);
      }
      if ( *(_QWORD *)(v10 + 32) )
      {
        v29 = std::wstring::wstring((__int64)v75, v9 + 40);
        v30 = (__int64 *)web::json::value::string(&v82, v29);
        v31 = *(_WORD **)(v10 + 24);
        Src = 0;
        v88 = 0;
        v32 = -1;
        do
          ++v32;
        while ( v31[v32] );
        std::wstring::_Construct<1,wchar_t const *>(&Src, v31, v32);
        v33 = (__int64 *)web::json::value::operator[](&v72, &Src);
        if ( v33 != v30 )
        {
          v34 = *v33;
          *v33 = *v30;
          *v30 = v34;
        }
        std::wstring::~wstring((__int64)&Src);
        if ( v82 )
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v82 + 192LL))(v82, 1);
      }
      if ( *(_QWORD *)(v10 + 48) )
      {
        v35 = std::wstring::wstring((__int64)v75, v9 + 72);
        v36 = (__int64 *)web::json::value::string(&v83, v35);
        v37 = *(_WORD **)(v10 + 40);
        Src = 0;
        v88 = 0;
        v38 = -1;
        do
          ++v38;
        while ( v37[v38] );
        std::wstring::_Construct<1,wchar_t const *>(&Src, v37, v38);
        v39 = (__int64 *)web::json::value::operator[](&v72, &Src);
        if ( v39 != v36 )
        {
          v40 = *v39;
          *v39 = *v36;
          *v36 = v40;
        }
        std::wstring::~wstring((__int64)&Src);
        if ( v83 )
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v83 + 192LL))(v83, 1);
      }
      if ( *(_BYTE *)(v9 + 232) )
      {
        v41 = *(_QWORD ***)(v9 + 112);
        for ( i = *v41; i != v41; i = (_QWORD *)*i )
        {
          v43 = std::wstring::wstring((__int64)v75, (__int64)(i + 6));
          v44 = (__int64 *)web::json::value::string(&v84, v43);
          v45 = (__int64 *)web::json::value::operator[](&v72, i + 2);
          if ( v45 != v44 )
          {
            v46 = *v45;
            *v45 = *v44;
            *v44 = v46;
          }
          if ( v84 )
            (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v84 + 192LL))(v84, 1);
        }
      }
      else
      {
        v47 = &Diagnostics::DeviceIdentity::select;
        do
        {
          Src = 0;
          v88 = 0;
          std::wstring::_Construct<1,wchar_t const *>(&Src, *v47, (unsigned __int64)v47[1]);
          Diagnostics::AnalysisRecord::GetField(v9, v91, &Src);
          std::wstring::~wstring((__int64)&Src);
          if ( v92 )
          {
            std::wstring::wstring((__int64)&Src, (__int64)v91);
          }
          else
          {
            Src = 0;
            v88 = 0u;
            std::wstring::_Construct<1,wchar_t const *>(&Src, &psz, 0);
          }
          v8 |= 4u;
          v48 = (__int64 *)web::json::value::string(&v85, &Src);
          memset(v75, 0, sizeof(v75));
          std::wstring::_Construct<1,wchar_t const *>(v75, v47[2], (unsigned __int64)v47[3]);
          v49 = (__int64 *)web::json::value::operator[](&v72, v75);
          if ( v49 != v48 )
          {
            v50 = *v49;
            *v49 = *v48;
            *v48 = v50;
          }
          std::wstring::~wstring((__int64)v75);
          if ( v85 )
            (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v85 + 192LL))(v85, 1);
          if ( v92 )
            std::wstring::~wstring((__int64)v91);
          v47 += 4;
        }
        while ( v47 != &Diagnostics::CtacAttributes::inputs );
        v74 = v8;
      }
      Src = 0;
      *(_QWORD *)&v88 = 0;
      *((_QWORD *)&v88 + 1) = 7;
      LOWORD(Src) = 0;
      v77[0] = &Diagnostics::DeviceIdentity::fieldTransforms;
      v77[1] = 2;
      v51 = v72;
      v52 = (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v72 + 88LL))(v72) == 3;
      v53 = *(_QWORD *)v51;
      if ( v52 )
      {
        v54 = (__int64 *)(*(__int64 (__fastcall **)(__int64))(v53 + 168))(v51);
        v57 = *v54;
        v58 = v54[1];
        if ( *v54 != v58 )
        {
          do
          {
            v59 = v88;
            if ( (_QWORD)v88 )
            {
              if ( (unsigned __int64)v88 >= *((_QWORD *)&v88 + 1) )
              {
                ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__QEAAXG_Z_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXG_Z_G_Z(
                  &Src,
                  v55,
                  v56,
                  47);
              }
              else
              {
                *(_QWORD *)&v88 = v88 + 1;
                p_Src = &Src;
                if ( *((_QWORD *)&v88 + 1) > 7u )
                  p_Src = (__int128 *)Src;
                *(_DWORD *)((char *)p_Src + 2 * v59) = 47;
              }
            }
            std::wstring::append(&Src);
            ___TraverseJson_AEAV_lambda_1___1__TryApplyFieldTransforms___Analyzer_Traits_UDeviceIdentity_Diagnostics___Diagnostics__CAXAEAVvalue_json_web__V__span___CBUFieldTransform_Diagnostics___0_0_std___Z____Analyzer_Traits_UDeviceIdentity_Diagnostics___Diagnostics__CAXAEAV_lambda_1___1__TryApplyFieldTransforms_01_CAXAEAVvalue_json_web__V__span___CBUFieldTransform_Diagnostics___0_0_std___Z_0AEAV__basic_string__WU__char_traits__W_std__V__allocator__W_2__8__WH_Z(
              (__int64)v77,
              (__int64 **)(v57 + 32),
              &Src,
              v61,
              9);
            std::wstring::resize(&Src);
            v57 += 40;
          }
          while ( v57 != v58 );
          v10 = v73[0];
        }
        goto LABEL_77;
      }
      if ( (*(unsigned int (__fastcall **)(__int64))(v53 + 88))(v51) != 4 )
        break;
      v62 = (_QWORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v51 + 152LL))(v51);
      v63 = (__int64)(v62[1] - *v62) >> 3;
      v64 = 0;
      if ( v63 )
      {
        do
        {
          v65 = (__int64 **)web::json::value::operator[](&v72, v64);
          ___TraverseJson_AEAV_lambda_1___1__TryApplyFieldTransforms___Analyzer_Traits_UDeviceIdentity_Diagnostics___Diagnostics__CAXAEAVvalue_json_web__V__span___CBUFieldTransform_Diagnostics___0_0_std___Z____Analyzer_Traits_UDeviceIdentity_Diagnostics___Diagnostics__CAXAEAV_lambda_1___1__TryApplyFieldTransforms_01_CAXAEAVvalue_json_web__V__span___CBUFieldTransform_Diagnostics___0_0_std___Z_0AEAV__basic_string__WU__char_traits__W_std__V__allocator__W_2__8__WH_Z(
            (__int64)v77,
            v65,
            &Src,
            v66,
            9);
          ++v64;
        }
        while ( v64 < v63 );
        goto LABEL_76;
      }
LABEL_77:
      std::wstring::~wstring((__int64)&Src);
      if ( *((_QWORD *)&v89 + 1) == v90 )
      {
        std::vector<web::json::value>::_Emplace_reallocate<web::json::value>(&v89, *((__int64 **)&v89 + 1), &v72);
      }
      else
      {
        v72 = 0;
        **((_QWORD **)&v89 + 1) = v51;
        *((_QWORD *)&v89 + 1) += 8LL;
      }
      if ( v72 )
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v72 + 192LL))(v72, 1);
      v9 += 280;
      v8 = v74;
      if ( v9 == v76 )
      {
        v6 = v86;
        v4 = (_BYTE *)v73[0];
        goto LABEL_84;
      }
    }
    `Diagnostics::Analyzer_Traits<Diagnostics::PolicyUpdates>::TryApplyFieldTransforms'::`2'::_lambda_1_::operator()(
      v77,
      &Src,
      &v72);
LABEL_76:
    v51 = v72;
    goto LABEL_77;
  }
LABEL_84:
  if ( v4[1] )
  {
    if ( *v4 )
      v67 = (_QWORD *)v89;
    else
      v67 = (_QWORD *)(*((_QWORD *)&v89 + 1) - 8LL);
    (**(void (__fastcall ***)(_QWORD, __int64))*v67)(*v67, v6);
    *(_BYTE *)(v6 + 8) = 1;
  }
  else
  {
    v73[0] = 0;
    web::json::value::array(v73);
    v68 = v89;
    if ( (__int64)(*((_QWORD *)&v89 + 1) - v89) >> 3 )
    {
      do
      {
        v69 = v68 + 8 * v7;
        v70 = web::json::value::operator[](v73, v7);
        web::json::value::operator=(v70, v69);
        ++v7;
        v68 = v89;
      }
      while ( v7 < (__int64)(*((_QWORD *)&v89 + 1) - v89) >> 3 );
    }
    *(_QWORD *)v6 = v73[0];
    *(_BYTE *)(v6 + 8) = 1;
  }
  std::vector<web::json::value>::_Tidy(&v89);
  return v6;
}

```

## disassembly

```asm
0x18004ef24  mov     [rsp-8+arg_0], rbx
0x18004ef29  push    rbp
0x18004ef2a  push    rsi
0x18004ef2b  push    rdi
0x18004ef2c  push    r12
0x18004ef2e  push    r13
0x18004ef30  push    r14
0x18004ef32  push    r15
0x18004ef34  lea     rbp, [rsp-40h]
0x18004ef39  sub     rsp, 140h
0x18004ef40  mov     rax, cs:__security_cookie
0x18004ef47  xor     rax, rsp
0x18004ef4a  mov     [rbp+70h+var_40], rax
0x18004ef4e  mov     rdi, r9
0x18004ef51  mov     [rsp+170h+var_138], r9
0x18004ef56  mov     rbx, r8
0x18004ef59  mov     r12, rdx
0x18004ef5c  mov     [rbp+70h+var_A8], rdx
0x18004ef60  mov     [rsp+170h+var_100], rdx
0x18004ef65  xor     r14d, r14d
0x18004ef68  mov     esi, r14d
0x18004ef6b  mov     [rsp+170h+var_128], r14d
0x18004ef70  xorps   xmm1, xmm1
0x18004ef73  movdqu  [rbp+70h+var_80], xmm1
0x18004ef78  mov     [rbp+70h+var_70], r14
0x18004ef7c  mov     rdx, [r8+8]
0x18004ef80  sub     rdx, [r8]
0x18004ef83  sar     rdx, 3
0x18004ef87  mov     rax, 0AF8AF8AF8AF8AF8Bh
0x18004ef91  imul    rdx, rax
0x18004ef95  lea     rcx, [rbp+70h+var_80]
0x18004ef99  call    ?reserve@?$vector@Vvalue@json@web@@V?$allocator@Vvalue@json@web@@@std@@@std@@QEAAX_K@Z; std::vector<web::json::value>::reserve(unsigned __int64)
0x18004ef9e  mov     r13, [rbx]
0x18004efa1  mov     rax, [rbx+8]
0x18004efa5  mov     [rsp+170h+var_100], rax
0x18004efaa  cmp     r13, rax
0x18004efad  jz      loc_18004F6EE
0x18004efb3  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18004efb7  mov     r12, [rsp+170h+var_138]
0x18004efbc  mov     [rsp+170h+var_140], r14
0x18004efc1  xor     edx, edx
0x18004efc3  lea     rcx, [rsp+170h+var_140]
0x18004efc8  call    ?object@value@json@web@@SA?AV123@_N@Z; web::json::value::object(bool)
0x18004efcd  nop
0x18004efce  cmp     [r12+3], r14b
0x18004efd3  jz      loc_18004F072
0x18004efd9  cmp     [r13+0B8h], r14
0x18004efe0  jz      loc_18004F072
0x18004efe6  lea     rdx, [r13+0A8h]
0x18004efed  lea     rcx, [rsp+170h+var_120]
0x18004eff2  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18004eff7  mov     rdx, rax
0x18004effa  lea     rcx, [rbp+70h+var_E8]
0x18004effe  call    ?string@value@json@web@@SA?AV123@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::string(std::wstring)
0x18004f003  mov     rbx, rax
0x18004f006  xorps   xmm0, xmm0
0x18004f009  movups  [rbp+70h+Src], xmm0
0x18004f00d  xorps   xmm1, xmm1
0x18004f010  movdqu  [rbp+70h+var_90], xmm1
0x18004f015  mov     r8d, 5
0x18004f01b  lea     rdx, aEvent_0; "Event"
0x18004f022  lea     rcx, [rbp+70h+Src]
0x18004f026  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18004f02b  nop
0x18004f02c  lea     rdx, [rbp+70h+Src]
0x18004f030  lea     rcx, [rsp+170h+var_140]
0x18004f035  call    ??Avalue@json@web@@QEAAAEAV012@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::operator[](std::wstring const &)
0x18004f03a  cmp     rax, rbx
0x18004f03d  jz      short loc_18004F04B
0x18004f03f  mov     rdx, [rax]
0x18004f042  mov     rcx, [rbx]
0x18004f045  mov     [rax], rcx
0x18004f048  mov     [rbx], rdx
0x18004f04b  lea     rcx, [rbp+70h+Src]
0x18004f04f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004f054  nop
0x18004f055  mov     rcx, [rbp+70h+var_E8]
0x18004f059  test    rcx, rcx
0x18004f05c  jz      short loc_18004F072
0x18004f05e  mov     rax, [rcx]
0x18004f061  mov     edx, 1
0x18004f066  mov     rax, [rax+0C0h]
0x18004f06d  call    _guard_dispatch_icall
0x18004f072  cmp     [r13+0E8h], r14b
0x18004f079  jz      loc_18004F10B
0x18004f07f  lea     rdx, [r13+0C8h]
0x18004f086  lea     rcx, [rsp+170h+var_120]
0x18004f08b  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18004f090  mov     rdx, rax
0x18004f093  lea     rcx, [rbp+70h+var_E0]
0x18004f097  call    ?string@value@json@web@@SA?AV123@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::string(std::wstring)
0x18004f09c  mov     rbx, rax
0x18004f09f  xorps   xmm0, xmm0
0x18004f0a2  movups  [rbp+70h+Src], xmm0
0x18004f0a6  xorps   xmm1, xmm1
0x18004f0a9  movdqu  [rbp+70h+var_90], xmm1
0x18004f0ae  mov     r8d, 5
0x18004f0b4  lea     rdx, aEvent_0; "Event"
0x18004f0bb  lea     rcx, [rbp+70h+Src]
0x18004f0bf  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18004f0c4  nop
0x18004f0c5  lea     rdx, [rbp+70h+Src]
0x18004f0c9  lea     rcx, [rsp+170h+var_140]
0x18004f0ce  call    ??Avalue@json@web@@QEAAAEAV012@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::operator[](std::wstring const &)
0x18004f0d3  cmp     rax, rbx
0x18004f0d6  jz      short loc_18004F0E4
0x18004f0d8  mov     rdx, [rax]
0x18004f0db  mov     rcx, [rbx]
0x18004f0de  mov     [rax], rcx
0x18004f0e1  mov     [rbx], rdx
0x18004f0e4  lea     rcx, [rbp+70h+Src]
0x18004f0e8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004f0ed  nop
0x18004f0ee  mov     rcx, [rbp+70h+var_E0]
0x18004f0f2  test    rcx, rcx
0x18004f0f5  jz      short loc_18004F10B
0x18004f0f7  mov     rax, [rcx]
0x18004f0fa  mov     edx, 1
0x18004f0ff  mov     rax, [rax+0C0h]
0x18004f106  call    _guard_dispatch_icall
0x18004f10b  cmp     [r13+110h], r14b
0x18004f112  jz      loc_18004F1A4
0x18004f118  lea     rdx, [r13+0F0h]
0x18004f11f  lea     rcx, [rsp+170h+var_120]
0x18004f124  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18004f129  mov     rdx, rax
0x18004f12c  lea     rcx, [rbp+70h+var_D8]
0x18004f130  call    ?string@value@json@web@@SA?AV123@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::string(std::wstring)
0x18004f135  mov     rbx, rax
0x18004f138  xorps   xmm0, xmm0
0x18004f13b  movups  [rbp+70h+Src], xmm0
0x18004f13f  xorps   xmm1, xmm1
0x18004f142  movdqu  [rbp+70h+var_90], xmm1
0x18004f147  mov     r8d, 7
0x18004f14d  lea     rdx, aOutcome; "Outcome"
0x18004f154  lea     rcx, [rbp+70h+Src]
0x18004f158  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18004f15d  nop
0x18004f15e  lea     rdx, [rbp+70h+Src]
0x18004f162  lea     rcx, [rsp+170h+var_140]
0x18004f167  call    ??Avalue@json@web@@QEAAAEAV012@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::operator[](std::wstring const &)
0x18004f16c  cmp     rax, rbx
0x18004f16f  jz      short loc_18004F17D
0x18004f171  mov     rdx, [rax]
0x18004f174  mov     rcx, [rbx]
0x18004f177  mov     [rax], rcx
0x18004f17a  mov     [rbx], rdx
0x18004f17d  lea     rcx, [rbp+70h+Src]
0x18004f181  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004f186  nop
0x18004f187  mov     rcx, [rbp+70h+var_D8]
0x18004f18b  test    rcx, rcx
0x18004f18e  jz      short loc_18004F1A4
0x18004f190  mov     rax, [rcx]
0x18004f193  mov     edx, 1
0x18004f198  mov     rax, [rax+0C0h]
0x18004f19f  call    _guard_dispatch_icall
0x18004f1a4  cmp     [r12+10h], r14
0x18004f1a9  jz      loc_18004F23D
0x18004f1af  lea     rdx, [r13+8]
0x18004f1b3  lea     rcx, [rsp+170h+var_120]
0x18004f1b8  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18004f1bd  mov     rdx, rax
0x18004f1c0  lea     rcx, [rbp+70h+var_D0]
0x18004f1c4  call    ?string@value@json@web@@SA?AV123@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::string(std::wstring)
0x18004f1c9  mov     rbx, rax
0x18004f1cc  mov     rdx, [r12+8]
0x18004f1d1  xorps   xmm0, xmm0
0x18004f1d4  movups  [rbp+70h+Src], xmm0
0x18004f1d8  xorps   xmm1, xmm1
0x18004f1db  movdqu  [rbp+70h+var_90], xmm1
0x18004f1e0  mov     r8, rdi
0x18004f1e3  inc     r8
0x18004f1e6  cmp     [rdx+r8*2], r14w
0x18004f1eb  jnz     short loc_18004F1E3
0x18004f1ed  lea     rcx, [rbp+70h+Src]
0x18004f1f1  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18004f1f6  nop
0x18004f1f7  lea     rdx, [rbp+70h+Src]
0x18004f1fb  lea     rcx, [rsp+170h+var_140]
0x18004f200  call    ??Avalue@json@web@@QEAAAEAV012@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::operator[](std::wstring const &)
0x18004f205  cmp     rax, rbx
0x18004f208  jz      short loc_18004F216
0x18004f20a  mov     rdx, [rax]
0x18004f20d  mov     rcx, [rbx]
0x18004f210  mov     [rax], rcx
0x18004f213  mov     [rbx], rdx
0x18004f216  lea     rcx, [rbp+70h+Src]
0x18004f21a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004f21f  nop
0x18004f220  mov     rcx, [rbp+70h+var_D0]
0x18004f224  test    rcx, rcx
0x18004f227  jz      short loc_18004F23D
0x18004f229  mov     rax, [rcx]
0x18004f22c  mov     edx, 1
0x18004f231  mov     rax, [rax+0C0h]
0x18004f238  call    _guard_dispatch_icall
0x18004f23d  cmp     [r12+20h], r14
0x18004f242  jz      loc_18004F2D6
0x18004f248  lea     rdx, [r13+28h]
0x18004f24c  lea     rcx, [rsp+170h+var_120]
0x18004f251  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18004f256  mov     rdx, rax
0x18004f259  lea     rcx, [rbp+70h+var_C8]
0x18004f25d  call    ?string@value@json@web@@SA?AV123@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::string(std::wstring)
0x18004f262  mov     rbx, rax
0x18004f265  mov     rdx, [r12+18h]
0x18004f26a  xorps   xmm0, xmm0
0x18004f26d  movups  [rbp+70h+Src], xmm0
0x18004f271  xorps   xmm1, xmm1
0x18004f274  movdqu  [rbp+70h+var_90], xmm1
0x18004f279  mov     r8, rdi
0x18004f27c  inc     r8
0x18004f27f  cmp     [rdx+r8*2], r14w
0x18004f284  jnz     short loc_18004F27C
0x18004f286  lea     rcx, [rbp+70h+Src]
0x18004f28a  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18004f28f  nop
0x18004f290  lea     rdx, [rbp+70h+Src]
0x18004f294  lea     rcx, [rsp+170h+var_140]
0x18004f299  call    ??Avalue@json@web@@QEAAAEAV012@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::operator[](std::wstring const &)
0x18004f29e  cmp     rax, rbx
0x18004f2a1  jz      short loc_18004F2AF
0x18004f2a3  mov     rdx, [rax]
0x18004f2a6  mov     rcx, [rbx]
0x18004f2a9  mov     [rax], rcx
0x18004f2ac  mov     [rbx], rdx
0x18004f2af  lea     rcx, [rbp+70h+Src]
0x18004f2b3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004f2b8  nop
0x18004f2b9  mov     rcx, [rbp+70h+var_C8]
0x18004f2bd  test    rcx, rcx
0x18004f2c0  jz      short loc_18004F2D6
0x18004f2c2  mov     rax, [rcx]
0x18004f2c5  mov     edx, 1
0x18004f2ca  mov     rax, [rax+0C0h]
0x18004f2d1  call    _guard_dispatch_icall
0x18004f2d6  cmp     [r12+30h], r14
0x18004f2db  jz      loc_18004F36F
0x18004f2e1  lea     rdx, [r13+48h]
0x18004f2e5  lea     rcx, [rsp+170h+var_120]
0x18004f2ea  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18004f2ef  mov     rdx, rax
0x18004f2f2  lea     rcx, [rbp+70h+var_C0]
0x18004f2f6  call    ?string@value@json@web@@SA?AV123@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::string(std::wstring)
0x18004f2fb  mov     rbx, rax
0x18004f2fe  mov     rdx, [r12+28h]
0x18004f303  xorps   xmm0, xmm0
0x18004f306  movups  [rbp+70h+Src], xmm0
0x18004f30a  xorps   xmm1, xmm1
0x18004f30d  movdqu  [rbp+70h+var_90], xmm1
0x18004f312  mov     r8, rdi
0x18004f315  inc     r8
0x18004f318  cmp     [rdx+r8*2], r14w
0x18004f31d  jnz     short loc_18004F315
0x18004f31f  lea     rcx, [rbp+70h+Src]
0x18004f323  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18004f328  nop
0x18004f329  lea     rdx, [rbp+70h+Src]
0x18004f32d  lea     rcx, [rsp+170h+var_140]
0x18004f332  call    ??Avalue@json@web@@QEAAAEAV012@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::operator[](std::wstring const &)
0x18004f337  cmp     rax, rbx
0x18004f33a  jz      short loc_18004F348
0x18004f33c  mov     rdx, [rax]
0x18004f33f  mov     rcx, [rbx]
0x18004f342  mov     [rax], rcx
0x18004f345  mov     [rbx], rdx
0x18004f348  lea     rcx, [rbp+70h+Src]
0x18004f34c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004f351  nop
0x18004f352  mov     rcx, [rbp+70h+var_C0]
0x18004f356  test    rcx, rcx
0x18004f359  jz      short loc_18004F36F
0x18004f35b  mov     rax, [rcx]
0x18004f35e  mov     edx, 1
0x18004f363  mov     rax, [rax+0C0h]
0x18004f36a  call    _guard_dispatch_icall
0x18004f36f  cmp     [r13+0E8h], r14b
0x18004f376  jz      short loc_18004F3E7
0x18004f378  mov     rdi, [r13+70h]
0x18004f37c  mov     rbx, [rdi]
0x18004f37f  jmp     short loc_18004F3DD
0x18004f381  lea     rdx, [rbx+30h]
0x18004f385  lea     rcx, [rsp+170h+var_120]
0x18004f38a  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18004f38f  mov     rdx, rax
0x18004f392  lea     rcx, [rbp+70h+var_B8]
0x18004f396  call    ?string@value@json@web@@SA?AV123@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::string(std::wstring)
0x18004f39b  mov     r15, rax
0x18004f39e  lea     rdx, [rbx+10h]
0x18004f3a2  lea     rcx, [rsp+170h+var_140]
0x18004f3a7  call    ??Avalue@json@web@@QEAAAEAV012@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::operator[](std::wstring const &)
0x18004f3ac  cmp     rax, r15
0x18004f3af  jz      short loc_18004F3BD
0x18004f3b1  mov     rdx, [rax]
0x18004f3b4  mov     rcx, [r15]
0x18004f3b7  mov     [rax], rcx
0x18004f3ba  mov     [r15], rdx
0x18004f3bd  mov     rcx, [rbp+70h+var_B8]
0x18004f3c1  test    rcx, rcx
  ... truncated ...
```
