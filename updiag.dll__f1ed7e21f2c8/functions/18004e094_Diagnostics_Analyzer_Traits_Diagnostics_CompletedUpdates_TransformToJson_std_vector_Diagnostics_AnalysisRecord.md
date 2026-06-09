# Diagnostics::Analyzer_Traits<Diagnostics::CompletedUpdates>::TransformToJson(std::vector<Diagnostics::AnalysisRecord,std::allocator<Diagnostics::AnalysisRecord>> const &,Diagnostics::TraitsConfig const &)

- ea: `0x18004e094`
- end: `0x18004e7d4`
- name: `?TransformToJson@?$Analyzer_Traits@UCompletedUpdates@Diagnostics@@@Diagnostics@@AEBA?AV?$optional@Vvalue@json@web@@@std@@AEBV?$vector@UAnalysisRecord@Diagnostics@@V?$allocator@UAnalysisRecord@Diagnostics@@@std@@@4@AEBUTraitsConfig@2@@Z`
- size: `1856`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180040c30`

## callees

- `0x180018b04`
- `0x180018eec`
- `0x180019080`
- `0x18001f520`
- `0x18003870c`
- `0x18004e094`
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

- `0x18004e2c0`: `Outcome`

## pseudocode

```c
__int64 __fastcall Diagnostics::Analyzer_Traits<Diagnostics::CompletedUpdates>::TransformToJson(
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
        v47 = &Diagnostics::CompletedUpdates::select;
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
        while ( v47 != (wchar_t **)&Diagnostics::CompletedUpdates::config );
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
0x18004e094  mov     [rsp-8+arg_0], rbx
0x18004e099  push    rbp
0x18004e09a  push    rsi
0x18004e09b  push    rdi
0x18004e09c  push    r12
0x18004e09e  push    r13
0x18004e0a0  push    r14
0x18004e0a2  push    r15
0x18004e0a4  lea     rbp, [rsp-10h]
0x18004e0a9  sub     rsp, 110h
0x18004e0b0  mov     rax, cs:__security_cookie
0x18004e0b7  xor     rax, rsp
0x18004e0ba  mov     [rbp+40h+var_38], rax
0x18004e0be  mov     rsi, r9
0x18004e0c1  mov     [rbp+40h+var_88], r9
0x18004e0c5  mov     rbx, r8
0x18004e0c8  mov     r13, rdx
0x18004e0cb  mov     [rbp+40h+var_80], rdx
0x18004e0cf  mov     [rsp+140h+var_C8], rdx
0x18004e0d4  xor     r14d, r14d
0x18004e0d7  mov     r12d, r14d
0x18004e0da  mov     [rsp+140h+var_F0], r14d
0x18004e0df  xorps   xmm1, xmm1
0x18004e0e2  movdqu  [rbp+40h+var_78], xmm1
0x18004e0e7  mov     [rbp+40h+var_68], r14
0x18004e0eb  mov     rdx, [r8+8]
0x18004e0ef  sub     rdx, [r8]
0x18004e0f2  sar     rdx, 3
0x18004e0f6  mov     rax, 0AF8AF8AF8AF8AF8Bh
0x18004e100  imul    rdx, rax
0x18004e104  lea     rcx, [rbp+40h+var_78]
0x18004e108  call    ?reserve@?$vector@Vvalue@json@web@@V?$allocator@Vvalue@json@web@@@std@@@std@@QEAAX_K@Z; std::vector<web::json::value>::reserve(unsigned __int64)
0x18004e10d  mov     r15, [rbx]
0x18004e110  mov     rax, [rbx+8]
0x18004e114  cmp     r15, rax
0x18004e117  jz      loc_18004E70B
0x18004e11d  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18004e121  mov     r13, rax
0x18004e124  mov     [rsp+140h+var_120], r14
0x18004e129  xor     edx, edx
0x18004e12b  lea     rcx, [rsp+140h+var_120]
0x18004e130  call    ?object@value@json@web@@SA?AV123@_N@Z; web::json::value::object(bool)
0x18004e135  nop
0x18004e136  cmp     [rsi+3], r14b
0x18004e13a  jz      loc_18004E1DE
0x18004e140  cmp     [r15+0B8h], r14
0x18004e147  jz      loc_18004E1DE
0x18004e14d  lea     rdx, [r15+0A8h]
0x18004e154  lea     rcx, [rsp+140h+var_E8]
0x18004e159  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18004e15e  mov     rdx, rax
0x18004e161  lea     rcx, [rbp+40h+var_C0]
0x18004e165  call    ?string@value@json@web@@SA?AV123@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::string(std::wstring)
0x18004e16a  mov     rbx, rax
0x18004e16d  xorps   xmm0, xmm0
0x18004e170  movups  [rsp+140h+var_118], xmm0
0x18004e175  xorps   xmm1, xmm1
0x18004e178  movdqu  [rsp+140h+var_108], xmm1
0x18004e17e  mov     r8d, 5
0x18004e184  lea     rdx, aEvent_0; "Event"
0x18004e18b  lea     rcx, [rsp+140h+var_118]
0x18004e190  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18004e195  nop
0x18004e196  lea     rdx, [rsp+140h+var_118]
0x18004e19b  lea     rcx, [rsp+140h+var_120]
0x18004e1a0  call    ??Avalue@json@web@@QEAAAEAV012@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::operator[](std::wstring const &)
0x18004e1a5  cmp     rax, rbx
0x18004e1a8  jz      short loc_18004E1B6
0x18004e1aa  mov     rdx, [rax]
0x18004e1ad  mov     rcx, [rbx]
0x18004e1b0  mov     [rax], rcx
0x18004e1b3  mov     [rbx], rdx
0x18004e1b6  lea     rcx, [rsp+140h+var_118]
0x18004e1bb  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004e1c0  nop
0x18004e1c1  mov     rcx, [rbp+40h+var_C0]
0x18004e1c5  test    rcx, rcx
0x18004e1c8  jz      short loc_18004E1DE
0x18004e1ca  mov     rax, [rcx]
0x18004e1cd  mov     edx, 1
0x18004e1d2  mov     rax, [rax+0C0h]
0x18004e1d9  call    _guard_dispatch_icall
0x18004e1de  cmp     [r15+0E8h], r14b
0x18004e1e5  jz      loc_18004E27C
0x18004e1eb  lea     rdx, [r15+0C8h]
0x18004e1f2  lea     rcx, [rsp+140h+var_E8]
0x18004e1f7  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18004e1fc  mov     rdx, rax
0x18004e1ff  lea     rcx, [rbp+40h+var_B8]
0x18004e203  call    ?string@value@json@web@@SA?AV123@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::string(std::wstring)
0x18004e208  mov     rbx, rax
0x18004e20b  xorps   xmm0, xmm0
0x18004e20e  movups  [rsp+140h+var_118], xmm0
0x18004e213  xorps   xmm1, xmm1
0x18004e216  movdqu  [rsp+140h+var_108], xmm1
0x18004e21c  mov     r8d, 5
0x18004e222  lea     rdx, aEvent_0; "Event"
0x18004e229  lea     rcx, [rsp+140h+var_118]
0x18004e22e  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18004e233  nop
0x18004e234  lea     rdx, [rsp+140h+var_118]
0x18004e239  lea     rcx, [rsp+140h+var_120]
0x18004e23e  call    ??Avalue@json@web@@QEAAAEAV012@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::operator[](std::wstring const &)
0x18004e243  cmp     rax, rbx
0x18004e246  jz      short loc_18004E254
0x18004e248  mov     rdx, [rax]
0x18004e24b  mov     rcx, [rbx]
0x18004e24e  mov     [rax], rcx
0x18004e251  mov     [rbx], rdx
0x18004e254  lea     rcx, [rsp+140h+var_118]
0x18004e259  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004e25e  nop
0x18004e25f  mov     rcx, [rbp+40h+var_B8]
0x18004e263  test    rcx, rcx
0x18004e266  jz      short loc_18004E27C
0x18004e268  mov     rax, [rcx]
0x18004e26b  mov     edx, 1
0x18004e270  mov     rax, [rax+0C0h]
0x18004e277  call    _guard_dispatch_icall
0x18004e27c  cmp     [r15+110h], r14b
0x18004e283  jz      loc_18004E31A
0x18004e289  lea     rdx, [r15+0F0h]
0x18004e290  lea     rcx, [rsp+140h+var_E8]
0x18004e295  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18004e29a  mov     rdx, rax
0x18004e29d  lea     rcx, [rbp+40h+var_B0]
0x18004e2a1  call    ?string@value@json@web@@SA?AV123@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::string(std::wstring)
0x18004e2a6  mov     rbx, rax
0x18004e2a9  xorps   xmm0, xmm0
0x18004e2ac  movups  [rsp+140h+var_118], xmm0
0x18004e2b1  xorps   xmm1, xmm1
0x18004e2b4  movdqu  [rsp+140h+var_108], xmm1
0x18004e2ba  mov     r8d, 7
0x18004e2c0  lea     rdx, aOutcome; "Outcome"
0x18004e2c7  lea     rcx, [rsp+140h+var_118]
0x18004e2cc  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18004e2d1  nop
0x18004e2d2  lea     rdx, [rsp+140h+var_118]
0x18004e2d7  lea     rcx, [rsp+140h+var_120]
0x18004e2dc  call    ??Avalue@json@web@@QEAAAEAV012@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::operator[](std::wstring const &)
0x18004e2e1  cmp     rax, rbx
0x18004e2e4  jz      short loc_18004E2F2
0x18004e2e6  mov     rdx, [rax]
0x18004e2e9  mov     rcx, [rbx]
0x18004e2ec  mov     [rax], rcx
0x18004e2ef  mov     [rbx], rdx
0x18004e2f2  lea     rcx, [rsp+140h+var_118]
0x18004e2f7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004e2fc  nop
0x18004e2fd  mov     rcx, [rbp+40h+var_B0]
0x18004e301  test    rcx, rcx
0x18004e304  jz      short loc_18004E31A
0x18004e306  mov     rax, [rcx]
0x18004e309  mov     edx, 1
0x18004e30e  mov     rax, [rax+0C0h]
0x18004e315  call    _guard_dispatch_icall
0x18004e31a  cmp     [rsi+10h], r14
0x18004e31e  jz      loc_18004E3B6
0x18004e324  lea     rdx, [r15+8]
0x18004e328  lea     rcx, [rsp+140h+var_E8]
0x18004e32d  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18004e332  mov     rdx, rax
0x18004e335  lea     rcx, [rbp+40h+var_A8]
0x18004e339  call    ?string@value@json@web@@SA?AV123@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::string(std::wstring)
0x18004e33e  mov     rbx, rax
0x18004e341  mov     rdx, [rsi+8]
0x18004e345  xorps   xmm0, xmm0
0x18004e348  movups  [rsp+140h+var_118], xmm0
0x18004e34d  xorps   xmm1, xmm1
0x18004e350  movdqu  [rsp+140h+var_108], xmm1
0x18004e356  mov     r8, rdi
0x18004e359  inc     r8
0x18004e35c  cmp     [rdx+r8*2], r14w
0x18004e361  jnz     short loc_18004E359
0x18004e363  lea     rcx, [rsp+140h+var_118]
0x18004e368  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18004e36d  nop
0x18004e36e  lea     rdx, [rsp+140h+var_118]
0x18004e373  lea     rcx, [rsp+140h+var_120]
0x18004e378  call    ??Avalue@json@web@@QEAAAEAV012@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::operator[](std::wstring const &)
0x18004e37d  cmp     rax, rbx
0x18004e380  jz      short loc_18004E38E
0x18004e382  mov     rdx, [rax]
0x18004e385  mov     rcx, [rbx]
0x18004e388  mov     [rax], rcx
0x18004e38b  mov     [rbx], rdx
0x18004e38e  lea     rcx, [rsp+140h+var_118]
0x18004e393  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004e398  nop
0x18004e399  mov     rcx, [rbp+40h+var_A8]
0x18004e39d  test    rcx, rcx
0x18004e3a0  jz      short loc_18004E3B6
0x18004e3a2  mov     rax, [rcx]
0x18004e3a5  mov     edx, 1
0x18004e3aa  mov     rax, [rax+0C0h]
0x18004e3b1  call    _guard_dispatch_icall
0x18004e3b6  cmp     [rsi+20h], r14
0x18004e3ba  jz      loc_18004E452
0x18004e3c0  lea     rdx, [r15+28h]
0x18004e3c4  lea     rcx, [rsp+140h+var_E8]
0x18004e3c9  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18004e3ce  mov     rdx, rax
0x18004e3d1  lea     rcx, [rbp+40h+var_A0]
0x18004e3d5  call    ?string@value@json@web@@SA?AV123@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::string(std::wstring)
0x18004e3da  mov     rbx, rax
0x18004e3dd  mov     rdx, [rsi+18h]
0x18004e3e1  xorps   xmm0, xmm0
0x18004e3e4  movups  [rsp+140h+var_118], xmm0
0x18004e3e9  xorps   xmm1, xmm1
0x18004e3ec  movdqu  [rsp+140h+var_108], xmm1
0x18004e3f2  mov     r8, rdi
0x18004e3f5  inc     r8
0x18004e3f8  cmp     [rdx+r8*2], r14w
0x18004e3fd  jnz     short loc_18004E3F5
0x18004e3ff  lea     rcx, [rsp+140h+var_118]
0x18004e404  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18004e409  nop
0x18004e40a  lea     rdx, [rsp+140h+var_118]
0x18004e40f  lea     rcx, [rsp+140h+var_120]
0x18004e414  call    ??Avalue@json@web@@QEAAAEAV012@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::operator[](std::wstring const &)
0x18004e419  cmp     rax, rbx
0x18004e41c  jz      short loc_18004E42A
0x18004e41e  mov     rdx, [rax]
0x18004e421  mov     rcx, [rbx]
0x18004e424  mov     [rax], rcx
0x18004e427  mov     [rbx], rdx
0x18004e42a  lea     rcx, [rsp+140h+var_118]
0x18004e42f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004e434  nop
0x18004e435  mov     rcx, [rbp+40h+var_A0]
0x18004e439  test    rcx, rcx
0x18004e43c  jz      short loc_18004E452
0x18004e43e  mov     rax, [rcx]
0x18004e441  mov     edx, 1
0x18004e446  mov     rax, [rax+0C0h]
0x18004e44d  call    _guard_dispatch_icall
0x18004e452  cmp     [rsi+30h], r14
0x18004e456  jz      loc_18004E4EE
0x18004e45c  lea     rdx, [r15+48h]
0x18004e460  lea     rcx, [rsp+140h+var_E8]
0x18004e465  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18004e46a  mov     rdx, rax
0x18004e46d  lea     rcx, [rbp+40h+var_98]
0x18004e471  call    ?string@value@json@web@@SA?AV123@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::string(std::wstring)
0x18004e476  mov     rbx, rax
0x18004e479  mov     rdx, [rsi+28h]
0x18004e47d  xorps   xmm0, xmm0
0x18004e480  movups  [rsp+140h+var_118], xmm0
0x18004e485  xorps   xmm1, xmm1
0x18004e488  movdqu  [rsp+140h+var_108], xmm1
0x18004e48e  mov     r8, rdi
0x18004e491  inc     r8
0x18004e494  cmp     [rdx+r8*2], r14w
0x18004e499  jnz     short loc_18004E491
0x18004e49b  lea     rcx, [rsp+140h+var_118]
0x18004e4a0  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18004e4a5  nop
0x18004e4a6  lea     rdx, [rsp+140h+var_118]
0x18004e4ab  lea     rcx, [rsp+140h+var_120]
0x18004e4b0  call    ??Avalue@json@web@@QEAAAEAV012@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::operator[](std::wstring const &)
0x18004e4b5  cmp     rax, rbx
0x18004e4b8  jz      short loc_18004E4C6
0x18004e4ba  mov     rdx, [rax]
0x18004e4bd  mov     rcx, [rbx]
0x18004e4c0  mov     [rax], rcx
0x18004e4c3  mov     [rbx], rdx
0x18004e4c6  lea     rcx, [rsp+140h+var_118]
0x18004e4cb  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004e4d0  nop
0x18004e4d1  mov     rcx, [rbp+40h+var_98]
0x18004e4d5  test    rcx, rcx
0x18004e4d8  jz      short loc_18004E4EE
0x18004e4da  mov     rax, [rcx]
0x18004e4dd  mov     edx, 1
0x18004e4e2  mov     rax, [rax+0C0h]
0x18004e4e9  call    _guard_dispatch_icall
0x18004e4ee  cmp     [r15+0E8h], r14b
0x18004e4f5  jz      loc_18004E57C
0x18004e4fb  mov     rdi, [r15+70h]
0x18004e4ff  mov     rbx, [rdi]
0x18004e502  cmp     rbx, rdi
0x18004e505  jz      loc_18004E6A5
0x18004e50b  lea     rdx, [rbx+30h]
0x18004e50f  lea     rcx, [rsp+140h+var_E8]
0x18004e514  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18004e519  mov     rdx, rax
0x18004e51c  lea     rcx, [rbp+40h+var_90]
0x18004e520  call    ?string@value@json@web@@SA?AV123@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::string(std::wstring)
0x18004e525  mov     r12, rax
0x18004e528  lea     rdx, [rbx+10h]
0x18004e52c  lea     rcx, [rsp+140h+var_120]
0x18004e531  call    ??Avalue@json@web@@QEAAAEAV012@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::operator[](std::wstring const &)
0x18004e536  cmp     rax, r12
0x18004e539  jz      short loc_18004E549
0x18004e53b  mov     rdx, [rax]
0x18004e53e  mov     rcx, [r12]
0x18004e542  mov     [rax], rcx
0x18004e545  mov     [r12], rdx
0x18004e549  mov     rcx, [rbp+40h+var_90]
0x18004e54d  test    rcx, rcx
  ... truncated ...
```
