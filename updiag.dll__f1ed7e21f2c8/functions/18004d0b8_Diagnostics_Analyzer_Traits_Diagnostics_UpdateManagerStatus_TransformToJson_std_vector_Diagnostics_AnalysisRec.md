# Diagnostics::Analyzer_Traits<Diagnostics::UpdateManagerStatus>::TransformToJson(std::vector<Diagnostics::AnalysisRecord,std::allocator<Diagnostics::AnalysisRecord>> const &,Diagnostics::TraitsConfig const &)

- ea: `0x18004d0b8`
- end: `0x18004d7f8`
- name: `?TransformToJson@?$Analyzer_Traits@UUpdateManagerStatus@Diagnostics@@@Diagnostics@@AEBA?AV?$optional@Vvalue@json@web@@@std@@AEBV?$vector@UAnalysisRecord@Diagnostics@@V?$allocator@UAnalysisRecord@Diagnostics@@@std@@@4@AEBUTraitsConfig@2@@Z`
- size: `1856`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18003cbc0`

## callees

- `0x180018b04`
- `0x180018eec`
- `0x180019080`
- `0x18001f520`
- `0x18003870c`
- `0x18004d0b8`
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

- `0x18004d2e4`: `Outcome`

## pseudocode

```c
__int64 __fastcall Diagnostics::Analyzer_Traits<Diagnostics::UpdateManagerStatus>::TransformToJson(
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
        v47 = &Diagnostics::UpdateManagerStatus::select;
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
        while ( v47 != (wchar_t **)&Diagnostics::ApplicableUpdates::config );
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
0x18004d0b8  mov     [rsp-8+arg_0], rbx
0x18004d0bd  push    rbp
0x18004d0be  push    rsi
0x18004d0bf  push    rdi
0x18004d0c0  push    r12
0x18004d0c2  push    r13
0x18004d0c4  push    r14
0x18004d0c6  push    r15
0x18004d0c8  lea     rbp, [rsp-10h]
0x18004d0cd  sub     rsp, 110h
0x18004d0d4  mov     rax, cs:__security_cookie
0x18004d0db  xor     rax, rsp
0x18004d0de  mov     [rbp+40h+var_38], rax
0x18004d0e2  mov     rsi, r9
0x18004d0e5  mov     [rbp+40h+var_88], r9
0x18004d0e9  mov     rbx, r8
0x18004d0ec  mov     r13, rdx
0x18004d0ef  mov     [rbp+40h+var_80], rdx
0x18004d0f3  mov     [rsp+140h+var_C8], rdx
0x18004d0f8  xor     r14d, r14d
0x18004d0fb  mov     r12d, r14d
0x18004d0fe  mov     [rsp+140h+var_F0], r14d
0x18004d103  xorps   xmm1, xmm1
0x18004d106  movdqu  [rbp+40h+var_78], xmm1
0x18004d10b  mov     [rbp+40h+var_68], r14
0x18004d10f  mov     rdx, [r8+8]
0x18004d113  sub     rdx, [r8]
0x18004d116  sar     rdx, 3
0x18004d11a  mov     rax, 0AF8AF8AF8AF8AF8Bh
0x18004d124  imul    rdx, rax
0x18004d128  lea     rcx, [rbp+40h+var_78]
0x18004d12c  call    ?reserve@?$vector@Vvalue@json@web@@V?$allocator@Vvalue@json@web@@@std@@@std@@QEAAX_K@Z; std::vector<web::json::value>::reserve(unsigned __int64)
0x18004d131  mov     r15, [rbx]
0x18004d134  mov     rax, [rbx+8]
0x18004d138  cmp     r15, rax
0x18004d13b  jz      loc_18004D72F
0x18004d141  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18004d145  mov     r13, rax
0x18004d148  mov     [rsp+140h+var_120], r14
0x18004d14d  xor     edx, edx
0x18004d14f  lea     rcx, [rsp+140h+var_120]
0x18004d154  call    ?object@value@json@web@@SA?AV123@_N@Z; web::json::value::object(bool)
0x18004d159  nop
0x18004d15a  cmp     [rsi+3], r14b
0x18004d15e  jz      loc_18004D202
0x18004d164  cmp     [r15+0B8h], r14
0x18004d16b  jz      loc_18004D202
0x18004d171  lea     rdx, [r15+0A8h]
0x18004d178  lea     rcx, [rsp+140h+var_E8]
0x18004d17d  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18004d182  mov     rdx, rax
0x18004d185  lea     rcx, [rbp+40h+var_C0]
0x18004d189  call    ?string@value@json@web@@SA?AV123@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::string(std::wstring)
0x18004d18e  mov     rbx, rax
0x18004d191  xorps   xmm0, xmm0
0x18004d194  movups  [rsp+140h+var_118], xmm0
0x18004d199  xorps   xmm1, xmm1
0x18004d19c  movdqu  [rsp+140h+var_108], xmm1
0x18004d1a2  mov     r8d, 5
0x18004d1a8  lea     rdx, aEvent_0; "Event"
0x18004d1af  lea     rcx, [rsp+140h+var_118]
0x18004d1b4  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18004d1b9  nop
0x18004d1ba  lea     rdx, [rsp+140h+var_118]
0x18004d1bf  lea     rcx, [rsp+140h+var_120]
0x18004d1c4  call    ??Avalue@json@web@@QEAAAEAV012@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::operator[](std::wstring const &)
0x18004d1c9  cmp     rax, rbx
0x18004d1cc  jz      short loc_18004D1DA
0x18004d1ce  mov     rdx, [rax]
0x18004d1d1  mov     rcx, [rbx]
0x18004d1d4  mov     [rax], rcx
0x18004d1d7  mov     [rbx], rdx
0x18004d1da  lea     rcx, [rsp+140h+var_118]
0x18004d1df  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004d1e4  nop
0x18004d1e5  mov     rcx, [rbp+40h+var_C0]
0x18004d1e9  test    rcx, rcx
0x18004d1ec  jz      short loc_18004D202
0x18004d1ee  mov     rax, [rcx]
0x18004d1f1  mov     edx, 1
0x18004d1f6  mov     rax, [rax+0C0h]
0x18004d1fd  call    _guard_dispatch_icall
0x18004d202  cmp     [r15+0E8h], r14b
0x18004d209  jz      loc_18004D2A0
0x18004d20f  lea     rdx, [r15+0C8h]
0x18004d216  lea     rcx, [rsp+140h+var_E8]
0x18004d21b  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18004d220  mov     rdx, rax
0x18004d223  lea     rcx, [rbp+40h+var_B8]
0x18004d227  call    ?string@value@json@web@@SA?AV123@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::string(std::wstring)
0x18004d22c  mov     rbx, rax
0x18004d22f  xorps   xmm0, xmm0
0x18004d232  movups  [rsp+140h+var_118], xmm0
0x18004d237  xorps   xmm1, xmm1
0x18004d23a  movdqu  [rsp+140h+var_108], xmm1
0x18004d240  mov     r8d, 5
0x18004d246  lea     rdx, aEvent_0; "Event"
0x18004d24d  lea     rcx, [rsp+140h+var_118]
0x18004d252  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18004d257  nop
0x18004d258  lea     rdx, [rsp+140h+var_118]
0x18004d25d  lea     rcx, [rsp+140h+var_120]
0x18004d262  call    ??Avalue@json@web@@QEAAAEAV012@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::operator[](std::wstring const &)
0x18004d267  cmp     rax, rbx
0x18004d26a  jz      short loc_18004D278
0x18004d26c  mov     rdx, [rax]
0x18004d26f  mov     rcx, [rbx]
0x18004d272  mov     [rax], rcx
0x18004d275  mov     [rbx], rdx
0x18004d278  lea     rcx, [rsp+140h+var_118]
0x18004d27d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004d282  nop
0x18004d283  mov     rcx, [rbp+40h+var_B8]
0x18004d287  test    rcx, rcx
0x18004d28a  jz      short loc_18004D2A0
0x18004d28c  mov     rax, [rcx]
0x18004d28f  mov     edx, 1
0x18004d294  mov     rax, [rax+0C0h]
0x18004d29b  call    _guard_dispatch_icall
0x18004d2a0  cmp     [r15+110h], r14b
0x18004d2a7  jz      loc_18004D33E
0x18004d2ad  lea     rdx, [r15+0F0h]
0x18004d2b4  lea     rcx, [rsp+140h+var_E8]
0x18004d2b9  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18004d2be  mov     rdx, rax
0x18004d2c1  lea     rcx, [rbp+40h+var_B0]
0x18004d2c5  call    ?string@value@json@web@@SA?AV123@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::string(std::wstring)
0x18004d2ca  mov     rbx, rax
0x18004d2cd  xorps   xmm0, xmm0
0x18004d2d0  movups  [rsp+140h+var_118], xmm0
0x18004d2d5  xorps   xmm1, xmm1
0x18004d2d8  movdqu  [rsp+140h+var_108], xmm1
0x18004d2de  mov     r8d, 7
0x18004d2e4  lea     rdx, aOutcome; "Outcome"
0x18004d2eb  lea     rcx, [rsp+140h+var_118]
0x18004d2f0  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18004d2f5  nop
0x18004d2f6  lea     rdx, [rsp+140h+var_118]
0x18004d2fb  lea     rcx, [rsp+140h+var_120]
0x18004d300  call    ??Avalue@json@web@@QEAAAEAV012@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::operator[](std::wstring const &)
0x18004d305  cmp     rax, rbx
0x18004d308  jz      short loc_18004D316
0x18004d30a  mov     rdx, [rax]
0x18004d30d  mov     rcx, [rbx]
0x18004d310  mov     [rax], rcx
0x18004d313  mov     [rbx], rdx
0x18004d316  lea     rcx, [rsp+140h+var_118]
0x18004d31b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004d320  nop
0x18004d321  mov     rcx, [rbp+40h+var_B0]
0x18004d325  test    rcx, rcx
0x18004d328  jz      short loc_18004D33E
0x18004d32a  mov     rax, [rcx]
0x18004d32d  mov     edx, 1
0x18004d332  mov     rax, [rax+0C0h]
0x18004d339  call    _guard_dispatch_icall
0x18004d33e  cmp     [rsi+10h], r14
0x18004d342  jz      loc_18004D3DA
0x18004d348  lea     rdx, [r15+8]
0x18004d34c  lea     rcx, [rsp+140h+var_E8]
0x18004d351  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18004d356  mov     rdx, rax
0x18004d359  lea     rcx, [rbp+40h+var_A8]
0x18004d35d  call    ?string@value@json@web@@SA?AV123@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::string(std::wstring)
0x18004d362  mov     rbx, rax
0x18004d365  mov     rdx, [rsi+8]
0x18004d369  xorps   xmm0, xmm0
0x18004d36c  movups  [rsp+140h+var_118], xmm0
0x18004d371  xorps   xmm1, xmm1
0x18004d374  movdqu  [rsp+140h+var_108], xmm1
0x18004d37a  mov     r8, rdi
0x18004d37d  inc     r8
0x18004d380  cmp     [rdx+r8*2], r14w
0x18004d385  jnz     short loc_18004D37D
0x18004d387  lea     rcx, [rsp+140h+var_118]
0x18004d38c  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18004d391  nop
0x18004d392  lea     rdx, [rsp+140h+var_118]
0x18004d397  lea     rcx, [rsp+140h+var_120]
0x18004d39c  call    ??Avalue@json@web@@QEAAAEAV012@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::operator[](std::wstring const &)
0x18004d3a1  cmp     rax, rbx
0x18004d3a4  jz      short loc_18004D3B2
0x18004d3a6  mov     rdx, [rax]
0x18004d3a9  mov     rcx, [rbx]
0x18004d3ac  mov     [rax], rcx
0x18004d3af  mov     [rbx], rdx
0x18004d3b2  lea     rcx, [rsp+140h+var_118]
0x18004d3b7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004d3bc  nop
0x18004d3bd  mov     rcx, [rbp+40h+var_A8]
0x18004d3c1  test    rcx, rcx
0x18004d3c4  jz      short loc_18004D3DA
0x18004d3c6  mov     rax, [rcx]
0x18004d3c9  mov     edx, 1
0x18004d3ce  mov     rax, [rax+0C0h]
0x18004d3d5  call    _guard_dispatch_icall
0x18004d3da  cmp     [rsi+20h], r14
0x18004d3de  jz      loc_18004D476
0x18004d3e4  lea     rdx, [r15+28h]
0x18004d3e8  lea     rcx, [rsp+140h+var_E8]
0x18004d3ed  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18004d3f2  mov     rdx, rax
0x18004d3f5  lea     rcx, [rbp+40h+var_A0]
0x18004d3f9  call    ?string@value@json@web@@SA?AV123@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::string(std::wstring)
0x18004d3fe  mov     rbx, rax
0x18004d401  mov     rdx, [rsi+18h]
0x18004d405  xorps   xmm0, xmm0
0x18004d408  movups  [rsp+140h+var_118], xmm0
0x18004d40d  xorps   xmm1, xmm1
0x18004d410  movdqu  [rsp+140h+var_108], xmm1
0x18004d416  mov     r8, rdi
0x18004d419  inc     r8
0x18004d41c  cmp     [rdx+r8*2], r14w
0x18004d421  jnz     short loc_18004D419
0x18004d423  lea     rcx, [rsp+140h+var_118]
0x18004d428  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18004d42d  nop
0x18004d42e  lea     rdx, [rsp+140h+var_118]
0x18004d433  lea     rcx, [rsp+140h+var_120]
0x18004d438  call    ??Avalue@json@web@@QEAAAEAV012@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::operator[](std::wstring const &)
0x18004d43d  cmp     rax, rbx
0x18004d440  jz      short loc_18004D44E
0x18004d442  mov     rdx, [rax]
0x18004d445  mov     rcx, [rbx]
0x18004d448  mov     [rax], rcx
0x18004d44b  mov     [rbx], rdx
0x18004d44e  lea     rcx, [rsp+140h+var_118]
0x18004d453  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004d458  nop
0x18004d459  mov     rcx, [rbp+40h+var_A0]
0x18004d45d  test    rcx, rcx
0x18004d460  jz      short loc_18004D476
0x18004d462  mov     rax, [rcx]
0x18004d465  mov     edx, 1
0x18004d46a  mov     rax, [rax+0C0h]
0x18004d471  call    _guard_dispatch_icall
0x18004d476  cmp     [rsi+30h], r14
0x18004d47a  jz      loc_18004D512
0x18004d480  lea     rdx, [r15+48h]
0x18004d484  lea     rcx, [rsp+140h+var_E8]
0x18004d489  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18004d48e  mov     rdx, rax
0x18004d491  lea     rcx, [rbp+40h+var_98]
0x18004d495  call    ?string@value@json@web@@SA?AV123@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::string(std::wstring)
0x18004d49a  mov     rbx, rax
0x18004d49d  mov     rdx, [rsi+28h]
0x18004d4a1  xorps   xmm0, xmm0
0x18004d4a4  movups  [rsp+140h+var_118], xmm0
0x18004d4a9  xorps   xmm1, xmm1
0x18004d4ac  movdqu  [rsp+140h+var_108], xmm1
0x18004d4b2  mov     r8, rdi
0x18004d4b5  inc     r8
0x18004d4b8  cmp     [rdx+r8*2], r14w
0x18004d4bd  jnz     short loc_18004D4B5
0x18004d4bf  lea     rcx, [rsp+140h+var_118]
0x18004d4c4  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18004d4c9  nop
0x18004d4ca  lea     rdx, [rsp+140h+var_118]
0x18004d4cf  lea     rcx, [rsp+140h+var_120]
0x18004d4d4  call    ??Avalue@json@web@@QEAAAEAV012@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::operator[](std::wstring const &)
0x18004d4d9  cmp     rax, rbx
0x18004d4dc  jz      short loc_18004D4EA
0x18004d4de  mov     rdx, [rax]
0x18004d4e1  mov     rcx, [rbx]
0x18004d4e4  mov     [rax], rcx
0x18004d4e7  mov     [rbx], rdx
0x18004d4ea  lea     rcx, [rsp+140h+var_118]
0x18004d4ef  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004d4f4  nop
0x18004d4f5  mov     rcx, [rbp+40h+var_98]
0x18004d4f9  test    rcx, rcx
0x18004d4fc  jz      short loc_18004D512
0x18004d4fe  mov     rax, [rcx]
0x18004d501  mov     edx, 1
0x18004d506  mov     rax, [rax+0C0h]
0x18004d50d  call    _guard_dispatch_icall
0x18004d512  cmp     [r15+0E8h], r14b
0x18004d519  jz      loc_18004D5A0
0x18004d51f  mov     rdi, [r15+70h]
0x18004d523  mov     rbx, [rdi]
0x18004d526  cmp     rbx, rdi
0x18004d529  jz      loc_18004D6C9
0x18004d52f  lea     rdx, [rbx+30h]
0x18004d533  lea     rcx, [rsp+140h+var_E8]
0x18004d538  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18004d53d  mov     rdx, rax
0x18004d540  lea     rcx, [rbp+40h+var_90]
0x18004d544  call    ?string@value@json@web@@SA?AV123@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::string(std::wstring)
0x18004d549  mov     r12, rax
0x18004d54c  lea     rdx, [rbx+10h]
0x18004d550  lea     rcx, [rsp+140h+var_120]
0x18004d555  call    ??Avalue@json@web@@QEAAAEAV012@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::operator[](std::wstring const &)
0x18004d55a  cmp     rax, r12
0x18004d55d  jz      short loc_18004D56D
0x18004d55f  mov     rdx, [rax]
0x18004d562  mov     rcx, [r12]
0x18004d566  mov     [rax], rcx
0x18004d569  mov     [r12], rdx
0x18004d56d  mov     rcx, [rbp+40h+var_90]
0x18004d571  test    rcx, rcx
  ... truncated ...
```
