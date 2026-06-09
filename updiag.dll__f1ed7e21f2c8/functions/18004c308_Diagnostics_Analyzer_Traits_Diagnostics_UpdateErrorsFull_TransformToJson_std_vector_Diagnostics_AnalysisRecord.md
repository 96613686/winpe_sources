# Diagnostics::Analyzer_Traits<Diagnostics::UpdateErrorsFull>::TransformToJson(std::vector<Diagnostics::AnalysisRecord,std::allocator<Diagnostics::AnalysisRecord>> const &,Diagnostics::TraitsConfig const &)

- ea: `0x18004c308`
- end: `0x18004ca48`
- name: `?TransformToJson@?$Analyzer_Traits@UUpdateErrorsFull@Diagnostics@@@Diagnostics@@AEBA?AV?$optional@Vvalue@json@web@@@std@@AEBV?$vector@UAnalysisRecord@Diagnostics@@V?$allocator@UAnalysisRecord@Diagnostics@@@std@@@4@AEBUTraitsConfig@2@@Z`
- size: `1856`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18003c600`

## callees

- `0x180018b04`
- `0x180018eec`
- `0x180019080`
- `0x18001f520`
- `0x18003870c`
- `0x18004c308`
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

- `0x18004c534`: `Outcome`

## pseudocode

```c
// Hidden C++ exception states: #wind=30
__int64 __fastcall Diagnostics::Analyzer_Traits<Diagnostics::UpdateErrorsFull>::TransformToJson(
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
        v47 = &Diagnostics::UpdateErrorsFull::select;
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
        while ( v47 != &Diagnostics::UpdateErrorsFull::inputs );
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
0x18004c308  mov     [rsp-8+arg_0], rbx
0x18004c30d  push    rbp
0x18004c30e  push    rsi
0x18004c30f  push    rdi
0x18004c310  push    r12
0x18004c312  push    r13
0x18004c314  push    r14
0x18004c316  push    r15
0x18004c318  lea     rbp, [rsp-10h]
0x18004c31d  sub     rsp, 110h
0x18004c324  mov     rax, cs:__security_cookie
0x18004c32b  xor     rax, rsp
0x18004c32e  mov     [rbp+40h+var_38], rax
0x18004c332  mov     rsi, r9
0x18004c335  mov     [rbp+40h+var_88], r9
0x18004c339  mov     rbx, r8
0x18004c33c  mov     r13, rdx
0x18004c33f  mov     [rbp+40h+var_80], rdx
0x18004c343  mov     [rsp+140h+var_C8], rdx
0x18004c348  xor     r14d, r14d
0x18004c34b  mov     r12d, r14d
0x18004c34e  mov     [rsp+140h+var_F0], r14d
0x18004c353  xorps   xmm1, xmm1
0x18004c356  movdqu  [rbp+40h+var_78], xmm1
0x18004c35b  mov     [rbp+40h+var_68], r14
0x18004c35f  mov     rdx, [r8+8]
0x18004c363  sub     rdx, [r8]
0x18004c366  sar     rdx, 3
0x18004c36a  mov     rax, 0AF8AF8AF8AF8AF8Bh
0x18004c374  imul    rdx, rax
0x18004c378  lea     rcx, [rbp+40h+var_78]
0x18004c37c  call    ?reserve@?$vector@Vvalue@json@web@@V?$allocator@Vvalue@json@web@@@std@@@std@@QEAAX_K@Z; std::vector<web::json::value>::reserve(unsigned __int64)
0x18004c381  mov     r15, [rbx]
0x18004c384  mov     rax, [rbx+8]
0x18004c388  cmp     r15, rax
0x18004c38b  jz      loc_18004C97F
0x18004c391  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18004c395  mov     r13, rax
0x18004c398  mov     [rsp+140h+var_120], r14
0x18004c39d  xor     edx, edx
0x18004c39f  lea     rcx, [rsp+140h+var_120]
0x18004c3a4  call    ?object@value@json@web@@SA?AV123@_N@Z; web::json::value::object(bool)
0x18004c3a9  nop
0x18004c3aa  cmp     [rsi+3], r14b
0x18004c3ae  jz      loc_18004C452
0x18004c3b4  cmp     [r15+0B8h], r14
0x18004c3bb  jz      loc_18004C452
0x18004c3c1  lea     rdx, [r15+0A8h]
0x18004c3c8  lea     rcx, [rsp+140h+var_E8]
0x18004c3cd  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18004c3d2  mov     rdx, rax
0x18004c3d5  lea     rcx, [rbp+40h+var_C0]
0x18004c3d9  call    ?string@value@json@web@@SA?AV123@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::string(std::wstring)
0x18004c3de  mov     rbx, rax
0x18004c3e1  xorps   xmm0, xmm0
0x18004c3e4  movups  [rsp+140h+var_118], xmm0
0x18004c3e9  xorps   xmm1, xmm1
0x18004c3ec  movdqu  [rsp+140h+var_108], xmm1
0x18004c3f2  mov     r8d, 5
0x18004c3f8  lea     rdx, aEvent_0; "Event"
0x18004c3ff  lea     rcx, [rsp+140h+var_118]
0x18004c404  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18004c409  nop
0x18004c40a  lea     rdx, [rsp+140h+var_118]
0x18004c40f  lea     rcx, [rsp+140h+var_120]
0x18004c414  call    ??Avalue@json@web@@QEAAAEAV012@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::operator[](std::wstring const &)
0x18004c419  cmp     rax, rbx
0x18004c41c  jz      short loc_18004C42A
0x18004c41e  mov     rdx, [rax]
0x18004c421  mov     rcx, [rbx]
0x18004c424  mov     [rax], rcx
0x18004c427  mov     [rbx], rdx
0x18004c42a  lea     rcx, [rsp+140h+var_118]
0x18004c42f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004c434  nop
0x18004c435  mov     rcx, [rbp+40h+var_C0]
0x18004c439  test    rcx, rcx
0x18004c43c  jz      short loc_18004C452
0x18004c43e  mov     rax, [rcx]
0x18004c441  mov     edx, 1
0x18004c446  mov     rax, [rax+0C0h]
0x18004c44d  call    _guard_dispatch_icall
0x18004c452  cmp     [r15+0E8h], r14b
0x18004c459  jz      loc_18004C4F0
0x18004c45f  lea     rdx, [r15+0C8h]
0x18004c466  lea     rcx, [rsp+140h+var_E8]
0x18004c46b  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18004c470  mov     rdx, rax
0x18004c473  lea     rcx, [rbp+40h+var_B8]
0x18004c477  call    ?string@value@json@web@@SA?AV123@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::string(std::wstring)
0x18004c47c  mov     rbx, rax
0x18004c47f  xorps   xmm0, xmm0
0x18004c482  movups  [rsp+140h+var_118], xmm0
0x18004c487  xorps   xmm1, xmm1
0x18004c48a  movdqu  [rsp+140h+var_108], xmm1
0x18004c490  mov     r8d, 5
0x18004c496  lea     rdx, aEvent_0; "Event"
0x18004c49d  lea     rcx, [rsp+140h+var_118]
0x18004c4a2  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18004c4a7  nop
0x18004c4a8  lea     rdx, [rsp+140h+var_118]
0x18004c4ad  lea     rcx, [rsp+140h+var_120]
0x18004c4b2  call    ??Avalue@json@web@@QEAAAEAV012@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::operator[](std::wstring const &)
0x18004c4b7  cmp     rax, rbx
0x18004c4ba  jz      short loc_18004C4C8
0x18004c4bc  mov     rdx, [rax]
0x18004c4bf  mov     rcx, [rbx]
0x18004c4c2  mov     [rax], rcx
0x18004c4c5  mov     [rbx], rdx
0x18004c4c8  lea     rcx, [rsp+140h+var_118]
0x18004c4cd  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004c4d2  nop
0x18004c4d3  mov     rcx, [rbp+40h+var_B8]
0x18004c4d7  test    rcx, rcx
0x18004c4da  jz      short loc_18004C4F0
0x18004c4dc  mov     rax, [rcx]
0x18004c4df  mov     edx, 1
0x18004c4e4  mov     rax, [rax+0C0h]
0x18004c4eb  call    _guard_dispatch_icall
0x18004c4f0  cmp     [r15+110h], r14b
0x18004c4f7  jz      loc_18004C58E
0x18004c4fd  lea     rdx, [r15+0F0h]
0x18004c504  lea     rcx, [rsp+140h+var_E8]
0x18004c509  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18004c50e  mov     rdx, rax
0x18004c511  lea     rcx, [rbp+40h+var_B0]
0x18004c515  call    ?string@value@json@web@@SA?AV123@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::string(std::wstring)
0x18004c51a  mov     rbx, rax
0x18004c51d  xorps   xmm0, xmm0
0x18004c520  movups  [rsp+140h+var_118], xmm0
0x18004c525  xorps   xmm1, xmm1
0x18004c528  movdqu  [rsp+140h+var_108], xmm1
0x18004c52e  mov     r8d, 7
0x18004c534  lea     rdx, aOutcome; "Outcome"
0x18004c53b  lea     rcx, [rsp+140h+var_118]
0x18004c540  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18004c545  nop
0x18004c546  lea     rdx, [rsp+140h+var_118]
0x18004c54b  lea     rcx, [rsp+140h+var_120]
0x18004c550  call    ??Avalue@json@web@@QEAAAEAV012@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::operator[](std::wstring const &)
0x18004c555  cmp     rax, rbx
0x18004c558  jz      short loc_18004C566
0x18004c55a  mov     rdx, [rax]
0x18004c55d  mov     rcx, [rbx]
0x18004c560  mov     [rax], rcx
0x18004c563  mov     [rbx], rdx
0x18004c566  lea     rcx, [rsp+140h+var_118]
0x18004c56b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004c570  nop
0x18004c571  mov     rcx, [rbp+40h+var_B0]
0x18004c575  test    rcx, rcx
0x18004c578  jz      short loc_18004C58E
0x18004c57a  mov     rax, [rcx]
0x18004c57d  mov     edx, 1
0x18004c582  mov     rax, [rax+0C0h]
0x18004c589  call    _guard_dispatch_icall
0x18004c58e  cmp     [rsi+10h], r14
0x18004c592  jz      loc_18004C62A
0x18004c598  lea     rdx, [r15+8]
0x18004c59c  lea     rcx, [rsp+140h+var_E8]
0x18004c5a1  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18004c5a6  mov     rdx, rax
0x18004c5a9  lea     rcx, [rbp+40h+var_A8]
0x18004c5ad  call    ?string@value@json@web@@SA?AV123@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::string(std::wstring)
0x18004c5b2  mov     rbx, rax
0x18004c5b5  mov     rdx, [rsi+8]
0x18004c5b9  xorps   xmm0, xmm0
0x18004c5bc  movups  [rsp+140h+var_118], xmm0
0x18004c5c1  xorps   xmm1, xmm1
0x18004c5c4  movdqu  [rsp+140h+var_108], xmm1
0x18004c5ca  mov     r8, rdi
0x18004c5cd  inc     r8
0x18004c5d0  cmp     [rdx+r8*2], r14w
0x18004c5d5  jnz     short loc_18004C5CD
0x18004c5d7  lea     rcx, [rsp+140h+var_118]
0x18004c5dc  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18004c5e1  nop
0x18004c5e2  lea     rdx, [rsp+140h+var_118]
0x18004c5e7  lea     rcx, [rsp+140h+var_120]
0x18004c5ec  call    ??Avalue@json@web@@QEAAAEAV012@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::operator[](std::wstring const &)
0x18004c5f1  cmp     rax, rbx
0x18004c5f4  jz      short loc_18004C602
0x18004c5f6  mov     rdx, [rax]
0x18004c5f9  mov     rcx, [rbx]
0x18004c5fc  mov     [rax], rcx
0x18004c5ff  mov     [rbx], rdx
0x18004c602  lea     rcx, [rsp+140h+var_118]
0x18004c607  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004c60c  nop
0x18004c60d  mov     rcx, [rbp+40h+var_A8]
0x18004c611  test    rcx, rcx
0x18004c614  jz      short loc_18004C62A
0x18004c616  mov     rax, [rcx]
0x18004c619  mov     edx, 1
0x18004c61e  mov     rax, [rax+0C0h]
0x18004c625  call    _guard_dispatch_icall
0x18004c62a  cmp     [rsi+20h], r14
0x18004c62e  jz      loc_18004C6C6
0x18004c634  lea     rdx, [r15+28h]
0x18004c638  lea     rcx, [rsp+140h+var_E8]
0x18004c63d  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18004c642  mov     rdx, rax
0x18004c645  lea     rcx, [rbp+40h+var_A0]
0x18004c649  call    ?string@value@json@web@@SA?AV123@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::string(std::wstring)
0x18004c64e  mov     rbx, rax
0x18004c651  mov     rdx, [rsi+18h]
0x18004c655  xorps   xmm0, xmm0
0x18004c658  movups  [rsp+140h+var_118], xmm0
0x18004c65d  xorps   xmm1, xmm1
0x18004c660  movdqu  [rsp+140h+var_108], xmm1
0x18004c666  mov     r8, rdi
0x18004c669  inc     r8
0x18004c66c  cmp     [rdx+r8*2], r14w
0x18004c671  jnz     short loc_18004C669
0x18004c673  lea     rcx, [rsp+140h+var_118]
0x18004c678  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18004c67d  nop
0x18004c67e  lea     rdx, [rsp+140h+var_118]
0x18004c683  lea     rcx, [rsp+140h+var_120]
0x18004c688  call    ??Avalue@json@web@@QEAAAEAV012@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::operator[](std::wstring const &)
0x18004c68d  cmp     rax, rbx
0x18004c690  jz      short loc_18004C69E
0x18004c692  mov     rdx, [rax]
0x18004c695  mov     rcx, [rbx]
0x18004c698  mov     [rax], rcx
0x18004c69b  mov     [rbx], rdx
0x18004c69e  lea     rcx, [rsp+140h+var_118]
0x18004c6a3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004c6a8  nop
0x18004c6a9  mov     rcx, [rbp+40h+var_A0]
0x18004c6ad  test    rcx, rcx
0x18004c6b0  jz      short loc_18004C6C6
0x18004c6b2  mov     rax, [rcx]
0x18004c6b5  mov     edx, 1
0x18004c6ba  mov     rax, [rax+0C0h]
0x18004c6c1  call    _guard_dispatch_icall
0x18004c6c6  cmp     [rsi+30h], r14
0x18004c6ca  jz      loc_18004C762
0x18004c6d0  lea     rdx, [r15+48h]
0x18004c6d4  lea     rcx, [rsp+140h+var_E8]
0x18004c6d9  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18004c6de  mov     rdx, rax
0x18004c6e1  lea     rcx, [rbp+40h+var_98]
0x18004c6e5  call    ?string@value@json@web@@SA?AV123@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::string(std::wstring)
0x18004c6ea  mov     rbx, rax
0x18004c6ed  mov     rdx, [rsi+28h]
0x18004c6f1  xorps   xmm0, xmm0
0x18004c6f4  movups  [rsp+140h+var_118], xmm0
0x18004c6f9  xorps   xmm1, xmm1
0x18004c6fc  movdqu  [rsp+140h+var_108], xmm1
0x18004c702  mov     r8, rdi
0x18004c705  inc     r8
0x18004c708  cmp     [rdx+r8*2], r14w
0x18004c70d  jnz     short loc_18004C705
0x18004c70f  lea     rcx, [rsp+140h+var_118]
0x18004c714  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18004c719  nop
0x18004c71a  lea     rdx, [rsp+140h+var_118]
0x18004c71f  lea     rcx, [rsp+140h+var_120]
0x18004c724  call    ??Avalue@json@web@@QEAAAEAV012@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::operator[](std::wstring const &)
0x18004c729  cmp     rax, rbx
0x18004c72c  jz      short loc_18004C73A
0x18004c72e  mov     rdx, [rax]
0x18004c731  mov     rcx, [rbx]
0x18004c734  mov     [rax], rcx
0x18004c737  mov     [rbx], rdx
0x18004c73a  lea     rcx, [rsp+140h+var_118]
0x18004c73f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004c744  nop
0x18004c745  mov     rcx, [rbp+40h+var_98]
0x18004c749  test    rcx, rcx
0x18004c74c  jz      short loc_18004C762
0x18004c74e  mov     rax, [rcx]
0x18004c751  mov     edx, 1
0x18004c756  mov     rax, [rax+0C0h]
0x18004c75d  call    _guard_dispatch_icall
0x18004c762  cmp     [r15+0E8h], r14b
0x18004c769  jz      loc_18004C7F0
0x18004c76f  mov     rdi, [r15+70h]
0x18004c773  mov     rbx, [rdi]
0x18004c776  cmp     rbx, rdi
0x18004c779  jz      loc_18004C919
0x18004c77f  lea     rdx, [rbx+30h]
0x18004c783  lea     rcx, [rsp+140h+var_E8]
0x18004c788  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18004c78d  mov     rdx, rax
0x18004c790  lea     rcx, [rbp+40h+var_90]
0x18004c794  call    ?string@value@json@web@@SA?AV123@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::string(std::wstring)
0x18004c799  mov     r12, rax
0x18004c79c  lea     rdx, [rbx+10h]
0x18004c7a0  lea     rcx, [rsp+140h+var_120]
0x18004c7a5  call    ??Avalue@json@web@@QEAAAEAV012@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::operator[](std::wstring const &)
0x18004c7aa  cmp     rax, r12
0x18004c7ad  jz      short loc_18004C7BD
0x18004c7af  mov     rdx, [rax]
0x18004c7b2  mov     rcx, [r12]
0x18004c7b6  mov     [rax], rcx
0x18004c7b9  mov     [r12], rdx
0x18004c7bd  mov     rcx, [rbp+40h+var_90]
0x18004c7c1  test    rcx, rcx
  ... truncated ...
```
