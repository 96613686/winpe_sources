# Diagnostics::Analyzer_Traits<Diagnostics::ApplicableUpdates>::TransformToJson(std::vector<Diagnostics::AnalysisRecord,std::allocator<Diagnostics::AnalysisRecord>> const &,Diagnostics::TraitsConfig const &)

- ea: `0x18004e7dc`
- end: `0x18004ef1c`
- name: `?TransformToJson@?$Analyzer_Traits@UApplicableUpdates@Diagnostics@@@Diagnostics@@AEBA?AV?$optional@Vvalue@json@web@@@std@@AEBV?$vector@UAnalysisRecord@Diagnostics@@V?$allocator@UAnalysisRecord@Diagnostics@@@std@@@4@AEBUTraitsConfig@2@@Z`
- size: `1856`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180040f00`

## callees

- `0x180018b04`
- `0x180018eec`
- `0x180019080`
- `0x18001f520`
- `0x18003870c`
- `0x18004e7dc`
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

- `0x18004ea08`: `Outcome`

## pseudocode

```c
__int64 __fastcall Diagnostics::Analyzer_Traits<Diagnostics::ApplicableUpdates>::TransformToJson(
        __int64 a1,
        __int64 a2,
        __int64 *a3,
        __int64 a4)
{
  __int64 v4; // rsi
  __int64 v6; // r13
  unsigned __int64 v7; // r14
  int v8; // r12d
  __int64 v9; // r15
  __int64 v10; // r13
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
  _QWORD *v42; // rbx
  __int64 v43; // rax
  __int64 *v44; // r12
  __int64 *v45; // rax
  __int64 v46; // rdx
  wchar_t **v47; // rbx
  __int64 *v48; // rdi
  __int64 *v49; // rax
  __int64 v50; // rdx
  __int64 v51; // rax
  _QWORD *v52; // rcx
  __int64 v53; // rcx
  __int64 v54; // rbx
  __int64 v55; // rax
  __int64 v57; // [rsp+20h] [rbp-E0h] BYREF
  __int128 v58; // [rsp+28h] [rbp-D8h] BYREF
  __int128 v59; // [rsp+38h] [rbp-C8h]
  int v60; // [rsp+50h] [rbp-B0h]
  _OWORD v61[2]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v62; // [rsp+78h] [rbp-88h] BYREF
  __int64 v63; // [rsp+80h] [rbp-80h] BYREF
  __int64 v64; // [rsp+88h] [rbp-78h] BYREF
  __int64 v65; // [rsp+90h] [rbp-70h] BYREF
  __int64 v66; // [rsp+98h] [rbp-68h] BYREF
  __int64 v67; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v68; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v69; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v70; // [rsp+B8h] [rbp-48h]
  __int64 v71; // [rsp+C0h] [rbp-40h]
  __int128 v72; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v73; // [rsp+D8h] [rbp-28h]
  _BYTE v74[32]; // [rsp+E0h] [rbp-20h] BYREF
  char v75; // [rsp+100h] [rbp+0h]

  v4 = a4;
  v70 = a4;
  v6 = a2;
  v71 = a2;
  v62 = a2;
  v7 = 0;
  v8 = 0;
  v60 = 0;
  v72 = 0;
  v73 = 0;
  std::vector<web::json::value>::reserve(&v72, 0xAF8AF8AF8AF8AF8BuLL * ((a3[1] - *a3) >> 3));
  v9 = *a3;
  if ( *a3 != a3[1] )
  {
    v10 = a3[1];
    do
    {
      v57 = 0;
      web::json::value::object(&v57, 0);
      if ( *(_BYTE *)(v4 + 3) && *(_QWORD *)(v9 + 184) )
      {
        v11 = std::wstring::wstring((__int64)v61, v9 + 168);
        v12 = (__int64 *)web::json::value::string(&v63, v11);
        v58 = 0;
        v59 = 0;
        std::wstring::_Construct<1,wchar_t const *>(&v58, L"Event", 5u);
        v13 = (__int64 *)web::json::value::operator[](&v57, &v58);
        if ( v13 != v12 )
        {
          v14 = *v13;
          *v13 = *v12;
          *v12 = v14;
        }
        std::wstring::~wstring((__int64)&v58);
        if ( v63 )
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v63 + 192LL))(v63, 1);
      }
      if ( *(_BYTE *)(v9 + 232) )
      {
        v15 = std::wstring::wstring((__int64)v61, v9 + 200);
        v16 = (__int64 *)web::json::value::string(&v64, v15);
        v58 = 0;
        v59 = 0;
        std::wstring::_Construct<1,wchar_t const *>(&v58, L"Event", 5u);
        v17 = (__int64 *)web::json::value::operator[](&v57, &v58);
        if ( v17 != v16 )
        {
          v18 = *v17;
          *v17 = *v16;
          *v16 = v18;
        }
        std::wstring::~wstring((__int64)&v58);
        if ( v64 )
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v64 + 192LL))(v64, 1);
      }
      if ( *(_BYTE *)(v9 + 272) )
      {
        v19 = std::wstring::wstring((__int64)v61, v9 + 240);
        v20 = (__int64 *)web::json::value::string(&v65, v19);
        v58 = 0;
        v59 = 0;
        std::wstring::_Construct<1,wchar_t const *>(&v58, L"Outcome", 7u);
        v21 = (__int64 *)web::json::value::operator[](&v57, &v58);
        if ( v21 != v20 )
        {
          v22 = *v21;
          *v21 = *v20;
          *v20 = v22;
        }
        std::wstring::~wstring((__int64)&v58);
        if ( v65 )
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v65 + 192LL))(v65, 1);
      }
      if ( *(_QWORD *)(v4 + 16) )
      {
        v23 = std::wstring::wstring((__int64)v61, v9 + 8);
        v24 = (__int64 *)web::json::value::string(&v66, v23);
        v25 = *(_WORD **)(v4 + 8);
        v58 = 0;
        v59 = 0;
        v26 = -1;
        do
          ++v26;
        while ( v25[v26] );
        std::wstring::_Construct<1,wchar_t const *>(&v58, v25, v26);
        v27 = (__int64 *)web::json::value::operator[](&v57, &v58);
        if ( v27 != v24 )
        {
          v28 = *v27;
          *v27 = *v24;
          *v24 = v28;
        }
        std::wstring::~wstring((__int64)&v58);
        if ( v66 )
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v66 + 192LL))(v66, 1);
      }
      if ( *(_QWORD *)(v4 + 32) )
      {
        v29 = std::wstring::wstring((__int64)v61, v9 + 40);
        v30 = (__int64 *)web::json::value::string(&v67, v29);
        v31 = *(_WORD **)(v4 + 24);
        v58 = 0;
        v59 = 0;
        v32 = -1;
        do
          ++v32;
        while ( v31[v32] );
        std::wstring::_Construct<1,wchar_t const *>(&v58, v31, v32);
        v33 = (__int64 *)web::json::value::operator[](&v57, &v58);
        if ( v33 != v30 )
        {
          v34 = *v33;
          *v33 = *v30;
          *v30 = v34;
        }
        std::wstring::~wstring((__int64)&v58);
        if ( v67 )
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v67 + 192LL))(v67, 1);
      }
      if ( *(_QWORD *)(v4 + 48) )
      {
        v35 = std::wstring::wstring((__int64)v61, v9 + 72);
        v36 = (__int64 *)web::json::value::string(&v68, v35);
        v37 = *(_WORD **)(v4 + 40);
        v58 = 0;
        v59 = 0;
        v38 = -1;
        do
          ++v38;
        while ( v37[v38] );
        std::wstring::_Construct<1,wchar_t const *>(&v58, v37, v38);
        v39 = (__int64 *)web::json::value::operator[](&v57, &v58);
        if ( v39 != v36 )
        {
          v40 = *v39;
          *v39 = *v36;
          *v36 = v40;
        }
        std::wstring::~wstring((__int64)&v58);
        if ( v68 )
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v68 + 192LL))(v68, 1);
      }
      if ( *(_BYTE *)(v9 + 232) )
      {
        v41 = *(_QWORD ***)(v9 + 112);
        v42 = *v41;
        if ( *v41 != v41 )
        {
          do
          {
            v43 = std::wstring::wstring((__int64)v61, (__int64)(v42 + 6));
            v44 = (__int64 *)web::json::value::string(&v69, v43);
            v45 = (__int64 *)web::json::value::operator[](&v57, v42 + 2);
            if ( v45 != v44 )
            {
              v46 = *v45;
              *v45 = *v44;
              *v44 = v46;
            }
            if ( v69 )
              (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v69 + 192LL))(v69, 1);
            v42 = (_QWORD *)*v42;
          }
          while ( v42 != v41 );
          v4 = v70;
          v8 = v60;
        }
      }
      else
      {
        v47 = &Diagnostics::ApplicableUpdates::select;
        do
        {
          v58 = 0;
          v59 = 0;
          std::wstring::_Construct<1,wchar_t const *>(&v58, *v47, (unsigned __int64)v47[1]);
          Diagnostics::AnalysisRecord::GetField(v9, v74, &v58);
          std::wstring::~wstring((__int64)&v58);
          if ( v75 )
          {
            std::wstring::wstring((__int64)&v58, (__int64)v74);
          }
          else
          {
            v58 = 0;
            v59 = 0u;
            std::wstring::_Construct<1,wchar_t const *>(&v58, &psz, 0);
          }
          v8 |= 4u;
          v48 = (__int64 *)web::json::value::string(&v62, &v58);
          memset(v61, 0, sizeof(v61));
          std::wstring::_Construct<1,wchar_t const *>(v61, v47[2], (unsigned __int64)v47[3]);
          v49 = (__int64 *)web::json::value::operator[](&v57, v61);
          if ( v49 != v48 )
          {
            v50 = *v49;
            *v49 = *v48;
            *v48 = v50;
          }
          std::wstring::~wstring((__int64)v61);
          if ( v62 )
            (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v62 + 192LL))(v62, 1);
          if ( v75 )
            std::wstring::~wstring((__int64)v74);
          v47 += 4;
        }
        while ( v47 != (wchar_t **)&Diagnostics::DeviceIdentity::config );
        v60 = v8;
      }
      if ( *((_QWORD *)&v72 + 1) == v73 )
      {
        std::vector<web::json::value>::_Emplace_reallocate<web::json::value>(&v72, *((__int64 **)&v72 + 1), &v57);
      }
      else
      {
        v51 = v57;
        v57 = 0;
        **((_QWORD **)&v72 + 1) = v51;
        *((_QWORD *)&v72 + 1) += 8LL;
      }
      if ( v57 )
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v57 + 192LL))(v57, 1);
      v9 += 280;
    }
    while ( v9 != v10 );
    v6 = v71;
  }
  if ( *(_BYTE *)(v4 + 1) )
  {
    if ( *(_BYTE *)v4 )
      v52 = (_QWORD *)v72;
    else
      v52 = (_QWORD *)(*((_QWORD *)&v72 + 1) - 8LL);
    (**(void (__fastcall ***)(_QWORD, __int64))*v52)(*v52, v6);
    *(_BYTE *)(v6 + 8) = 1;
  }
  else
  {
    v57 = 0;
    web::json::value::array(&v57);
    v53 = v72;
    if ( (__int64)(*((_QWORD *)&v72 + 1) - v72) >> 3 )
    {
      do
      {
        v54 = v53 + 8 * v7;
        v55 = web::json::value::operator[](&v57, v7);
        web::json::value::operator=(v55, v54);
        ++v7;
        v53 = v72;
      }
      while ( v7 < (__int64)(*((_QWORD *)&v72 + 1) - v72) >> 3 );
    }
    *(_QWORD *)v6 = v57;
    *(_BYTE *)(v6 + 8) = 1;
  }
  std::vector<web::json::value>::_Tidy(&v72);
  return v6;
}

```

## disassembly

```asm
0x18004e7dc  mov     [rsp-8+arg_0], rbx
0x18004e7e1  push    rbp
0x18004e7e2  push    rsi
0x18004e7e3  push    rdi
0x18004e7e4  push    r12
0x18004e7e6  push    r13
0x18004e7e8  push    r14
0x18004e7ea  push    r15
0x18004e7ec  lea     rbp, [rsp-10h]
0x18004e7f1  sub     rsp, 110h
0x18004e7f8  mov     rax, cs:__security_cookie
0x18004e7ff  xor     rax, rsp
0x18004e802  mov     [rbp+40h+var_38], rax
0x18004e806  mov     rsi, r9
0x18004e809  mov     [rbp+40h+var_88], r9
0x18004e80d  mov     rbx, r8
0x18004e810  mov     r13, rdx
0x18004e813  mov     [rbp+40h+var_80], rdx
0x18004e817  mov     [rsp+140h+var_C8], rdx
0x18004e81c  xor     r14d, r14d
0x18004e81f  mov     r12d, r14d
0x18004e822  mov     [rsp+140h+var_F0], r14d
0x18004e827  xorps   xmm1, xmm1
0x18004e82a  movdqu  [rbp+40h+var_78], xmm1
0x18004e82f  mov     [rbp+40h+var_68], r14
0x18004e833  mov     rdx, [r8+8]
0x18004e837  sub     rdx, [r8]
0x18004e83a  sar     rdx, 3
0x18004e83e  mov     rax, 0AF8AF8AF8AF8AF8Bh
0x18004e848  imul    rdx, rax
0x18004e84c  lea     rcx, [rbp+40h+var_78]
0x18004e850  call    ?reserve@?$vector@Vvalue@json@web@@V?$allocator@Vvalue@json@web@@@std@@@std@@QEAAX_K@Z; std::vector<web::json::value>::reserve(unsigned __int64)
0x18004e855  mov     r15, [rbx]
0x18004e858  mov     rax, [rbx+8]
0x18004e85c  cmp     r15, rax
0x18004e85f  jz      loc_18004EE53
0x18004e865  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18004e869  mov     r13, rax
0x18004e86c  mov     [rsp+140h+var_120], r14
0x18004e871  xor     edx, edx
0x18004e873  lea     rcx, [rsp+140h+var_120]
0x18004e878  call    ?object@value@json@web@@SA?AV123@_N@Z; web::json::value::object(bool)
0x18004e87d  nop
0x18004e87e  cmp     [rsi+3], r14b
0x18004e882  jz      loc_18004E926
0x18004e888  cmp     [r15+0B8h], r14
0x18004e88f  jz      loc_18004E926
0x18004e895  lea     rdx, [r15+0A8h]
0x18004e89c  lea     rcx, [rsp+140h+var_E8]
0x18004e8a1  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18004e8a6  mov     rdx, rax
0x18004e8a9  lea     rcx, [rbp+40h+var_C0]
0x18004e8ad  call    ?string@value@json@web@@SA?AV123@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::string(std::wstring)
0x18004e8b2  mov     rbx, rax
0x18004e8b5  xorps   xmm0, xmm0
0x18004e8b8  movups  [rsp+140h+var_118], xmm0
0x18004e8bd  xorps   xmm1, xmm1
0x18004e8c0  movdqu  [rsp+140h+var_108], xmm1
0x18004e8c6  mov     r8d, 5
0x18004e8cc  lea     rdx, aEvent_0; "Event"
0x18004e8d3  lea     rcx, [rsp+140h+var_118]
0x18004e8d8  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18004e8dd  nop
0x18004e8de  lea     rdx, [rsp+140h+var_118]
0x18004e8e3  lea     rcx, [rsp+140h+var_120]
0x18004e8e8  call    ??Avalue@json@web@@QEAAAEAV012@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::operator[](std::wstring const &)
0x18004e8ed  cmp     rax, rbx
0x18004e8f0  jz      short loc_18004E8FE
0x18004e8f2  mov     rdx, [rax]
0x18004e8f5  mov     rcx, [rbx]
0x18004e8f8  mov     [rax], rcx
0x18004e8fb  mov     [rbx], rdx
0x18004e8fe  lea     rcx, [rsp+140h+var_118]
0x18004e903  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004e908  nop
0x18004e909  mov     rcx, [rbp+40h+var_C0]
0x18004e90d  test    rcx, rcx
0x18004e910  jz      short loc_18004E926
0x18004e912  mov     rax, [rcx]
0x18004e915  mov     edx, 1
0x18004e91a  mov     rax, [rax+0C0h]
0x18004e921  call    _guard_dispatch_icall
0x18004e926  cmp     [r15+0E8h], r14b
0x18004e92d  jz      loc_18004E9C4
0x18004e933  lea     rdx, [r15+0C8h]
0x18004e93a  lea     rcx, [rsp+140h+var_E8]
0x18004e93f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18004e944  mov     rdx, rax
0x18004e947  lea     rcx, [rbp+40h+var_B8]
0x18004e94b  call    ?string@value@json@web@@SA?AV123@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::string(std::wstring)
0x18004e950  mov     rbx, rax
0x18004e953  xorps   xmm0, xmm0
0x18004e956  movups  [rsp+140h+var_118], xmm0
0x18004e95b  xorps   xmm1, xmm1
0x18004e95e  movdqu  [rsp+140h+var_108], xmm1
0x18004e964  mov     r8d, 5
0x18004e96a  lea     rdx, aEvent_0; "Event"
0x18004e971  lea     rcx, [rsp+140h+var_118]
0x18004e976  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18004e97b  nop
0x18004e97c  lea     rdx, [rsp+140h+var_118]
0x18004e981  lea     rcx, [rsp+140h+var_120]
0x18004e986  call    ??Avalue@json@web@@QEAAAEAV012@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::operator[](std::wstring const &)
0x18004e98b  cmp     rax, rbx
0x18004e98e  jz      short loc_18004E99C
0x18004e990  mov     rdx, [rax]
0x18004e993  mov     rcx, [rbx]
0x18004e996  mov     [rax], rcx
0x18004e999  mov     [rbx], rdx
0x18004e99c  lea     rcx, [rsp+140h+var_118]
0x18004e9a1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004e9a6  nop
0x18004e9a7  mov     rcx, [rbp+40h+var_B8]
0x18004e9ab  test    rcx, rcx
0x18004e9ae  jz      short loc_18004E9C4
0x18004e9b0  mov     rax, [rcx]
0x18004e9b3  mov     edx, 1
0x18004e9b8  mov     rax, [rax+0C0h]
0x18004e9bf  call    _guard_dispatch_icall
0x18004e9c4  cmp     [r15+110h], r14b
0x18004e9cb  jz      loc_18004EA62
0x18004e9d1  lea     rdx, [r15+0F0h]
0x18004e9d8  lea     rcx, [rsp+140h+var_E8]
0x18004e9dd  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18004e9e2  mov     rdx, rax
0x18004e9e5  lea     rcx, [rbp+40h+var_B0]
0x18004e9e9  call    ?string@value@json@web@@SA?AV123@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::string(std::wstring)
0x18004e9ee  mov     rbx, rax
0x18004e9f1  xorps   xmm0, xmm0
0x18004e9f4  movups  [rsp+140h+var_118], xmm0
0x18004e9f9  xorps   xmm1, xmm1
0x18004e9fc  movdqu  [rsp+140h+var_108], xmm1
0x18004ea02  mov     r8d, 7
0x18004ea08  lea     rdx, aOutcome; "Outcome"
0x18004ea0f  lea     rcx, [rsp+140h+var_118]
0x18004ea14  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18004ea19  nop
0x18004ea1a  lea     rdx, [rsp+140h+var_118]
0x18004ea1f  lea     rcx, [rsp+140h+var_120]
0x18004ea24  call    ??Avalue@json@web@@QEAAAEAV012@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::operator[](std::wstring const &)
0x18004ea29  cmp     rax, rbx
0x18004ea2c  jz      short loc_18004EA3A
0x18004ea2e  mov     rdx, [rax]
0x18004ea31  mov     rcx, [rbx]
0x18004ea34  mov     [rax], rcx
0x18004ea37  mov     [rbx], rdx
0x18004ea3a  lea     rcx, [rsp+140h+var_118]
0x18004ea3f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004ea44  nop
0x18004ea45  mov     rcx, [rbp+40h+var_B0]
0x18004ea49  test    rcx, rcx
0x18004ea4c  jz      short loc_18004EA62
0x18004ea4e  mov     rax, [rcx]
0x18004ea51  mov     edx, 1
0x18004ea56  mov     rax, [rax+0C0h]
0x18004ea5d  call    _guard_dispatch_icall
0x18004ea62  cmp     [rsi+10h], r14
0x18004ea66  jz      loc_18004EAFE
0x18004ea6c  lea     rdx, [r15+8]
0x18004ea70  lea     rcx, [rsp+140h+var_E8]
0x18004ea75  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18004ea7a  mov     rdx, rax
0x18004ea7d  lea     rcx, [rbp+40h+var_A8]
0x18004ea81  call    ?string@value@json@web@@SA?AV123@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::string(std::wstring)
0x18004ea86  mov     rbx, rax
0x18004ea89  mov     rdx, [rsi+8]
0x18004ea8d  xorps   xmm0, xmm0
0x18004ea90  movups  [rsp+140h+var_118], xmm0
0x18004ea95  xorps   xmm1, xmm1
0x18004ea98  movdqu  [rsp+140h+var_108], xmm1
0x18004ea9e  mov     r8, rdi
0x18004eaa1  inc     r8
0x18004eaa4  cmp     [rdx+r8*2], r14w
0x18004eaa9  jnz     short loc_18004EAA1
0x18004eaab  lea     rcx, [rsp+140h+var_118]
0x18004eab0  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18004eab5  nop
0x18004eab6  lea     rdx, [rsp+140h+var_118]
0x18004eabb  lea     rcx, [rsp+140h+var_120]
0x18004eac0  call    ??Avalue@json@web@@QEAAAEAV012@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::operator[](std::wstring const &)
0x18004eac5  cmp     rax, rbx
0x18004eac8  jz      short loc_18004EAD6
0x18004eaca  mov     rdx, [rax]
0x18004eacd  mov     rcx, [rbx]
0x18004ead0  mov     [rax], rcx
0x18004ead3  mov     [rbx], rdx
0x18004ead6  lea     rcx, [rsp+140h+var_118]
0x18004eadb  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004eae0  nop
0x18004eae1  mov     rcx, [rbp+40h+var_A8]
0x18004eae5  test    rcx, rcx
0x18004eae8  jz      short loc_18004EAFE
0x18004eaea  mov     rax, [rcx]
0x18004eaed  mov     edx, 1
0x18004eaf2  mov     rax, [rax+0C0h]
0x18004eaf9  call    _guard_dispatch_icall
0x18004eafe  cmp     [rsi+20h], r14
0x18004eb02  jz      loc_18004EB9A
0x18004eb08  lea     rdx, [r15+28h]
0x18004eb0c  lea     rcx, [rsp+140h+var_E8]
0x18004eb11  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18004eb16  mov     rdx, rax
0x18004eb19  lea     rcx, [rbp+40h+var_A0]
0x18004eb1d  call    ?string@value@json@web@@SA?AV123@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::string(std::wstring)
0x18004eb22  mov     rbx, rax
0x18004eb25  mov     rdx, [rsi+18h]
0x18004eb29  xorps   xmm0, xmm0
0x18004eb2c  movups  [rsp+140h+var_118], xmm0
0x18004eb31  xorps   xmm1, xmm1
0x18004eb34  movdqu  [rsp+140h+var_108], xmm1
0x18004eb3a  mov     r8, rdi
0x18004eb3d  inc     r8
0x18004eb40  cmp     [rdx+r8*2], r14w
0x18004eb45  jnz     short loc_18004EB3D
0x18004eb47  lea     rcx, [rsp+140h+var_118]
0x18004eb4c  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18004eb51  nop
0x18004eb52  lea     rdx, [rsp+140h+var_118]
0x18004eb57  lea     rcx, [rsp+140h+var_120]
0x18004eb5c  call    ??Avalue@json@web@@QEAAAEAV012@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::operator[](std::wstring const &)
0x18004eb61  cmp     rax, rbx
0x18004eb64  jz      short loc_18004EB72
0x18004eb66  mov     rdx, [rax]
0x18004eb69  mov     rcx, [rbx]
0x18004eb6c  mov     [rax], rcx
0x18004eb6f  mov     [rbx], rdx
0x18004eb72  lea     rcx, [rsp+140h+var_118]
0x18004eb77  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004eb7c  nop
0x18004eb7d  mov     rcx, [rbp+40h+var_A0]
0x18004eb81  test    rcx, rcx
0x18004eb84  jz      short loc_18004EB9A
0x18004eb86  mov     rax, [rcx]
0x18004eb89  mov     edx, 1
0x18004eb8e  mov     rax, [rax+0C0h]
0x18004eb95  call    _guard_dispatch_icall
0x18004eb9a  cmp     [rsi+30h], r14
0x18004eb9e  jz      loc_18004EC36
0x18004eba4  lea     rdx, [r15+48h]
0x18004eba8  lea     rcx, [rsp+140h+var_E8]
0x18004ebad  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18004ebb2  mov     rdx, rax
0x18004ebb5  lea     rcx, [rbp+40h+var_98]
0x18004ebb9  call    ?string@value@json@web@@SA?AV123@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::string(std::wstring)
0x18004ebbe  mov     rbx, rax
0x18004ebc1  mov     rdx, [rsi+28h]
0x18004ebc5  xorps   xmm0, xmm0
0x18004ebc8  movups  [rsp+140h+var_118], xmm0
0x18004ebcd  xorps   xmm1, xmm1
0x18004ebd0  movdqu  [rsp+140h+var_108], xmm1
0x18004ebd6  mov     r8, rdi
0x18004ebd9  inc     r8
0x18004ebdc  cmp     [rdx+r8*2], r14w
0x18004ebe1  jnz     short loc_18004EBD9
0x18004ebe3  lea     rcx, [rsp+140h+var_118]
0x18004ebe8  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18004ebed  nop
0x18004ebee  lea     rdx, [rsp+140h+var_118]
0x18004ebf3  lea     rcx, [rsp+140h+var_120]
0x18004ebf8  call    ??Avalue@json@web@@QEAAAEAV012@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::operator[](std::wstring const &)
0x18004ebfd  cmp     rax, rbx
0x18004ec00  jz      short loc_18004EC0E
0x18004ec02  mov     rdx, [rax]
0x18004ec05  mov     rcx, [rbx]
0x18004ec08  mov     [rax], rcx
0x18004ec0b  mov     [rbx], rdx
0x18004ec0e  lea     rcx, [rsp+140h+var_118]
0x18004ec13  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004ec18  nop
0x18004ec19  mov     rcx, [rbp+40h+var_98]
0x18004ec1d  test    rcx, rcx
0x18004ec20  jz      short loc_18004EC36
0x18004ec22  mov     rax, [rcx]
0x18004ec25  mov     edx, 1
0x18004ec2a  mov     rax, [rax+0C0h]
0x18004ec31  call    _guard_dispatch_icall
0x18004ec36  cmp     [r15+0E8h], r14b
0x18004ec3d  jz      loc_18004ECC4
0x18004ec43  mov     rdi, [r15+70h]
0x18004ec47  mov     rbx, [rdi]
0x18004ec4a  cmp     rbx, rdi
0x18004ec4d  jz      loc_18004EDED
0x18004ec53  lea     rdx, [rbx+30h]
0x18004ec57  lea     rcx, [rsp+140h+var_E8]
0x18004ec5c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18004ec61  mov     rdx, rax
0x18004ec64  lea     rcx, [rbp+40h+var_90]
0x18004ec68  call    ?string@value@json@web@@SA?AV123@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::string(std::wstring)
0x18004ec6d  mov     r12, rax
0x18004ec70  lea     rdx, [rbx+10h]
0x18004ec74  lea     rcx, [rsp+140h+var_120]
0x18004ec79  call    ??Avalue@json@web@@QEAAAEAV012@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::operator[](std::wstring const &)
0x18004ec7e  cmp     rax, r12
0x18004ec81  jz      short loc_18004EC91
0x18004ec83  mov     rdx, [rax]
0x18004ec86  mov     rcx, [r12]
0x18004ec8a  mov     [rax], rcx
0x18004ec8d  mov     [r12], rdx
0x18004ec91  mov     rcx, [rbp+40h+var_90]
0x18004ec95  test    rcx, rcx
  ... truncated ...
```
