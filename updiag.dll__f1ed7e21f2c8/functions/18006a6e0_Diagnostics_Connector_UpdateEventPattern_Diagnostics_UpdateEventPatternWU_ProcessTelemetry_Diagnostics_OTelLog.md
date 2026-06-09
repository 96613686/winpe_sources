# Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternWU>::ProcessTelemetry(Diagnostics::OTelLogRecord &,Diagnostics::OTelFile &)

- ea: `0x18006a6e0`
- end: `0x18006add9`
- name: `?ProcessTelemetry@?$Connector_UpdateEventPattern@UUpdateEventPatternWU@Diagnostics@@@Diagnostics@@UEAA_NAEAVOTelLogRecord@2@AEAVOTelFile@2@@Z`
- size: `1785`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180015360`
- `0x180018eec`
- `0x180018f68`
- `0x180019080`
- `0x18001adcc`
- `0x18001c92c`
- `0x180020dc8`
- `0x18002a6ac`
- `0x18003c324`
- `0x18006a6e0`
- `0x18006cfcc`
- `0x18006db04`
- `0x18008fe00`

## string_xrefs

- `0x18006a7f2`: `UPDATEID`

## pseudocode

```c
// Hidden C++ exception states: #wind=27
char __fastcall Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternWU>::ProcessTelemetry(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 Attribute; // rax
  __int64 v6; // rax
  __int64 v7; // rsi
  __int64 v8; // rax
  bool v9; // zf
  wchar_t **v10; // rbx
  const wchar_t *v11; // rdx
  size_t v12; // r8
  __int64 v13; // rax
  wchar_t *v14; // rbx
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rdx
  __int128 v24; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v25; // [rsp+50h] [rbp-B0h]
  __int128 v26; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v27; // [rsp+70h] [rbp-90h]
  _BYTE v28[32]; // [rsp+80h] [rbp-80h] BYREF
  char v29; // [rsp+A0h] [rbp-60h]
  _BYTE v30[48]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v31; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v32; // [rsp+E8h] [rbp-18h] BYREF
  __int128 v33; // [rsp+F8h] [rbp-8h]
  __int128 v34; // [rsp+108h] [rbp+8h] BYREF
  __int128 v35; // [rsp+118h] [rbp+18h]
  __int128 v36; // [rsp+128h] [rbp+28h] BYREF
  __int128 v37; // [rsp+138h] [rbp+38h]
  _BYTE v38[32]; // [rsp+150h] [rbp+50h] BYREF
  char v39; // [rsp+170h] [rbp+70h]
  _BYTE v40[40]; // [rsp+178h] [rbp+78h] BYREF
  wchar_t *S2[2]; // [rsp+1A0h] [rbp+A0h] BYREF
  __int128 v42; // [rsp+1B0h] [rbp+B0h]
  __int128 v43; // [rsp+1C0h] [rbp+C0h] BYREF
  __int128 v44; // [rsp+1D0h] [rbp+D0h]
  __int128 v45; // [rsp+1E0h] [rbp+E0h] BYREF
  __int64 v46[2]; // [rsp+1F0h] [rbp+F0h]

  *(_QWORD *)(a1 + 72) = a3;
  v43 = 0;
  v44 = 0;
  std::wstring::_Construct<1,wchar_t const *>(&v43, L"PROVIDERID", 0xAu);
  Attribute = Diagnostics::OTelLogRecord::GetAttribute(a2, v38, &v43);
  if ( *(_BYTE *)(Attribute + 32) )
  {
    v45 = *(_OWORD *)Attribute;
    *(_OWORD *)v46 = *(_OWORD *)(Attribute + 16);
    *(_WORD *)Attribute = 0;
    *(_QWORD *)(Attribute + 16) = 0;
    *(_QWORD *)(Attribute + 24) = 7;
  }
  else
  {
    v45 = 0;
    v46[0] = 0;
    v46[1] = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v45, &psz, 0);
  }
  if ( v39 )
    std::wstring::~wstring((__int64)v38);
  std::wstring::~wstring((__int64)&v43);
  v24 = 0;
  v25 = 0;
  std::wstring::_Construct<1,wchar_t const *>(&v24, L"UPDATEID", 8u);
  v6 = Diagnostics::OTelLogRecord::GetAttribute(a2, v40, &v24);
  if ( *(_BYTE *)(v6 + 32) )
  {
    v43 = *(_OWORD *)v6;
    v44 = *(_OWORD *)(v6 + 16);
    *(_WORD *)v6 = 0;
    *(_QWORD *)(v6 + 16) = 0;
    *(_QWORD *)(v6 + 24) = 7;
  }
  else
  {
    v43 = 0;
    v44 = 0u;
    std::wstring::_Construct<1,wchar_t const *>(&v43, &psz, 0);
  }
  if ( v40[32] )
    std::wstring::~wstring((__int64)v40);
  std::wstring::~wstring((__int64)&v24);
  v7 = v46[0];
  if ( v46[0] && (_QWORD)v44 )
  {
    v24 = 0;
    v25 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v24, L"CATEGORY", 8u);
    v8 = Diagnostics::OTelLogRecord::GetAttribute(a2, v28, &v24);
    v9 = *(_BYTE *)(v8 + 32) == 0;
    v42 = 0u;
    *(_OWORD *)S2 = 0;
    if ( v9 )
    {
      std::wstring::_Construct<1,wchar_t const *>(S2, &psz, 0);
    }
    else
    {
      *(_OWORD *)S2 = *(_OWORD *)v8;
      v42 = *(_OWORD *)(v8 + 16);
      *(_WORD *)v8 = 0;
      *(_QWORD *)(v8 + 16) = 0;
      *(_QWORD *)(v8 + 24) = 7;
    }
    if ( v29 )
      std::wstring::~wstring((__int64)v28);
    std::wstring::~wstring((__int64)&v24);
    v10 = &Diagnostics::UpdateEventPatternWU::allowedCategories;
    do
    {
      v11 = (const wchar_t *)S2;
      if ( *((_QWORD *)&v42 + 1) > 7u )
        v11 = S2[0];
      v12 = (size_t)v10[1];
      if ( v12 == (_QWORD)v42 && (!v12 || !wmemcmp(*v10, v11, v12)) )
        break;
      v10 += 2;
    }
    while ( v10 != (wchar_t **)&qword_1800B2048 );
    if ( v10 != (wchar_t **)&qword_1800B2048 )
    {
      std::wstring::~wstring((__int64)S2);
      if ( v7 == 0x7FFFFFFFFFFFFFFELL )
        std::_Xlen_string();
      std::wstring::wstring(v30, v7, L"|", 1);
      v13 = std::wstring::append(v30);
      v26 = 0;
      v27 = 0;
      v26 = *(_OWORD *)v13;
      v27 = *(_OWORD *)(v13 + 16);
      *(_WORD *)v13 = 0;
      *(_QWORD *)(v13 + 16) = 0;
      *(_QWORD *)(v13 + 24) = 7;
      std::_Hash<std::_Umap_traits<std::wstring,Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternWU>::UpdateGroup,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternWU>::UpdateGroup>>,0>>::_Try_emplace<std::wstring,>(
        (float *)(a1 + 8),
        (__int64)S2,
        &v26);
      std::wstring::~wstring((__int64)&v26);
      std::wstring::~wstring((__int64)v30);
      v14 = S2[0];
      if ( LOBYTE(S2[1]) )
      {
        std::wstring::operator=(S2[0] + 24, &v45);
        std::wstring::operator=(v14 + 40, &v43);
        v24 = 0;
        v25 = 0;
        std::wstring::_Construct<1,wchar_t const *>(&v24, L"TITLE", 5u);
        v15 = Diagnostics::OTelLogRecord::GetAttribute(a2, v28, &v24);
        v16 = std::optional<std::wstring>::value_or<wchar_t const (&)[1]>(v15, v30);
        std::wstring::operator=(v14 + 56, v16);
        std::wstring::~wstring((__int64)v30);
        if ( v29 )
          std::wstring::~wstring((__int64)v28);
        std::wstring::~wstring((__int64)&v24);
        v24 = 0;
        v25 = 0;
        std::wstring::_Construct<1,wchar_t const *>(&v24, L"CATEGORY", 8u);
        v17 = Diagnostics::OTelLogRecord::GetAttribute(a2, v28, &v24);
        v18 = std::optional<std::wstring>::value_or<wchar_t const (&)[1]>(v17, v30);
        std::wstring::operator=(v14 + 72, v18);
        std::wstring::~wstring((__int64)v30);
        if ( v29 )
          std::wstring::~wstring((__int64)v28);
        std::wstring::~wstring((__int64)&v24);
      }
      v31 = 100LL * *(_QWORD *)(a2 + 128);
      *(_OWORD *)S2 = 0;
      v42 = 0;
      std::wstring::_Construct<1,wchar_t const *>(S2, L"EVENT", 5u);
      v19 = Diagnostics::OTelLogRecord::GetAttribute(a2, v30, S2);
      std::optional<std::wstring>::value_or<wchar_t const (&)[1]>(v19, &v32);
      v26 = 0;
      v27 = 0;
      std::wstring::_Construct<1,wchar_t const *>(&v26, L"RESULT", 6u);
      v20 = Diagnostics::OTelLogRecord::GetAttribute(a2, v38, &v26);
      std::optional<std::wstring>::value_or<wchar_t const (&)[1]>(v20, &v34);
      v24 = 0;
      v25 = 0;
      std::wstring::_Construct<1,wchar_t const *>(&v24, L"REASON", 6u);
      v21 = Diagnostics::OTelLogRecord::GetAttribute(a2, v28, &v24);
      std::optional<std::wstring>::value_or<wchar_t const (&)[1]>(v21, &v36);
      v22 = *((_QWORD *)v14 + 23);
      if ( v22 == *((_QWORD *)v14 + 24) )
      {
        std::vector<Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternOther>::EventEntry,std::allocator<Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternOther>::EventEntry>>::_Emplace_reallocate<Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternOther>::EventEntry>(
          (_QWORD *)v14 + 22,
          (_QWORD *)v22,
          &v31);
      }
      else
      {
        *(_QWORD *)v22 = v31;
        *(_OWORD *)(v22 + 8) = v32;
        *(_OWORD *)(v22 + 24) = v33;
        *(_QWORD *)&v33 = 0;
        *((_QWORD *)&v33 + 1) = 7;
        LOWORD(v32) = 0;
        *(_OWORD *)(v22 + 40) = v34;
        *(_OWORD *)(v22 + 56) = v35;
        *(_QWORD *)&v35 = 0;
        *((_QWORD *)&v35 + 1) = 7;
        LOWORD(v34) = 0;
        *(_OWORD *)(v22 + 72) = v36;
        *(_OWORD *)(v22 + 88) = v37;
        *(_QWORD *)&v37 = 0;
        *((_QWORD *)&v37 + 1) = 7;
        LOWORD(v36) = 0;
        *((_QWORD *)v14 + 23) += 104LL;
      }
      std::wstring::~wstring((__int64)&v36);
      std::wstring::~wstring((__int64)&v34);
      std::wstring::~wstring((__int64)&v32);
      if ( v29 )
        std::wstring::~wstring((__int64)v28);
      std::wstring::~wstring((__int64)&v24);
      if ( v39 )
        std::wstring::~wstring((__int64)v38);
      std::wstring::~wstring((__int64)&v26);
      if ( v30[32] )
        std::wstring::~wstring((__int64)v30);
    }
    std::wstring::~wstring((__int64)S2);
  }
  std::wstring::~wstring((__int64)&v43);
  std::wstring::~wstring((__int64)&v45);
  return 1;
}

```

## disassembly

```asm
0x18006a6e0  mov     [rsp-8+arg_10], rbx
0x18006a6e5  push    rbp
0x18006a6e6  push    rsi
0x18006a6e7  push    rdi
0x18006a6e8  push    r12
0x18006a6ea  push    r13
0x18006a6ec  push    r14
0x18006a6ee  push    r15
0x18006a6f0  lea     rbp, [rsp-110h]
0x18006a6f8  sub     rsp, 210h
0x18006a6ff  mov     rax, cs:__security_cookie
0x18006a706  xor     rax, rsp
0x18006a709  mov     [rbp+140h+var_40], rax
0x18006a710  mov     rdi, rdx
0x18006a713  mov     r15, rcx
0x18006a716  xor     r12d, r12d
0x18006a719  mov     [rcx+48h], r8
0x18006a71d  xorps   xmm0, xmm0
0x18006a720  movups  [rbp+140h+var_80], xmm0
0x18006a727  xorps   xmm1, xmm1
0x18006a72a  movdqu  [rbp+140h+var_70], xmm1
0x18006a732  lea     r8d, [r12+0Ah]
0x18006a737  lea     rdx, aProviderid; "PROVIDERID"
0x18006a73e  lea     rcx, [rbp+140h+var_80]
0x18006a745  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18006a74a  nop
0x18006a74b  lea     r8, [rbp+140h+var_80]
0x18006a752  lea     rdx, [rbp+140h+var_F0]
0x18006a756  mov     rcx, rdi
0x18006a759  call    ?GetAttribute@OTelLogRecord@Diagnostics@@QEBA?AV?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@@Z; Diagnostics::OTelLogRecord::GetAttribute(std::wstring const &)
0x18006a75e  nop
0x18006a75f  lea     rbx, psz
0x18006a766  lea     r13d, [r12+7]
0x18006a76b  cmp     [rax+20h], r12b
0x18006a76f  jz      short loc_18006A794
0x18006a771  movups  xmm0, xmmword ptr [rax]
0x18006a774  movups  [rbp+140h+var_60], xmm0
0x18006a77b  movups  xmm1, xmmword ptr [rax+10h]
0x18006a77f  movups  xmmword ptr [rbp+140h+var_50], xmm1
0x18006a786  mov     [rax], r12w
0x18006a78a  mov     [rax+10h], r12
0x18006a78e  mov     [rax+18h], r13
0x18006a792  jmp     short loc_18006A7BF
0x18006a794  xorps   xmm0, xmm0
0x18006a797  movups  [rbp+140h+var_60], xmm0
0x18006a79e  mov     [rbp+140h+var_50], r12
0x18006a7a5  mov     [rbp+140h+var_50+8], r12
0x18006a7ac  xor     r8d, r8d
0x18006a7af  mov     rdx, rbx
0x18006a7b2  lea     rcx, [rbp+140h+var_60]
0x18006a7b9  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18006a7be  nop
0x18006a7bf  cmp     [rbp+140h+var_D0], r12b
0x18006a7c3  jz      short loc_18006A7CF
0x18006a7c5  lea     rcx, [rbp+140h+var_F0]
0x18006a7c9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18006a7ce  nop
0x18006a7cf  lea     rcx, [rbp+140h+var_80]
0x18006a7d6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18006a7db  xorps   xmm0, xmm0
0x18006a7de  movups  [rsp+240h+var_200], xmm0
0x18006a7e3  xorps   xmm1, xmm1
0x18006a7e6  movdqu  [rsp+240h+var_1F0], xmm1
0x18006a7ec  mov     r8d, 8
0x18006a7f2  lea     rdx, aUpdateid_0; "UPDATEID"
0x18006a7f9  lea     rcx, [rsp+240h+var_200]
0x18006a7fe  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18006a803  nop
0x18006a804  lea     r8, [rsp+240h+var_200]
0x18006a809  lea     rdx, [rbp+140h+var_C8]
0x18006a80d  mov     rcx, rdi
0x18006a810  call    ?GetAttribute@OTelLogRecord@Diagnostics@@QEBA?AV?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@@Z; Diagnostics::OTelLogRecord::GetAttribute(std::wstring const &)
0x18006a815  nop
0x18006a816  cmp     [rax+20h], r12b
0x18006a81a  jz      short loc_18006A83F
0x18006a81c  movups  xmm0, xmmword ptr [rax]
0x18006a81f  movups  [rbp+140h+var_80], xmm0
0x18006a826  movups  xmm1, xmmword ptr [rax+10h]
0x18006a82a  movups  [rbp+140h+var_70], xmm1
0x18006a831  mov     [rax], r12w
0x18006a835  mov     [rax+10h], r12
0x18006a839  mov     [rax+18h], r13
0x18006a83d  jmp     short loc_18006A86A
0x18006a83f  xorps   xmm0, xmm0
0x18006a842  movups  [rbp+140h+var_80], xmm0
0x18006a849  mov     qword ptr [rbp+140h+var_70], r12
0x18006a850  mov     qword ptr [rbp+140h+var_70+8], r12
0x18006a857  xor     r8d, r8d
0x18006a85a  mov     rdx, rbx
0x18006a85d  lea     rcx, [rbp+140h+var_80]
0x18006a864  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18006a869  nop
0x18006a86a  cmp     [rbp+140h+var_A8], r12b
0x18006a871  jz      short loc_18006A87D
0x18006a873  lea     rcx, [rbp+140h+var_C8]
0x18006a877  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18006a87c  nop
0x18006a87d  lea     rcx, [rsp+240h+var_200]
0x18006a882  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18006a887  mov     rsi, [rbp+140h+var_50]
0x18006a88e  test    rsi, rsi
0x18006a891  jz      loc_18006AD8E
0x18006a897  mov     r14, qword ptr [rbp+140h+var_70]
0x18006a89e  test    r14, r14
0x18006a8a1  jz      loc_18006AD8E
0x18006a8a7  xorps   xmm0, xmm0
0x18006a8aa  movups  [rsp+240h+var_200], xmm0
0x18006a8af  xorps   xmm1, xmm1
0x18006a8b2  movdqu  [rsp+240h+var_1F0], xmm1
0x18006a8b8  mov     r8d, 8
0x18006a8be  lea     rdx, aCategory_0; "CATEGORY"
0x18006a8c5  lea     rcx, [rsp+240h+var_200]
0x18006a8ca  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18006a8cf  nop
0x18006a8d0  lea     r8, [rsp+240h+var_200]
0x18006a8d5  lea     rdx, [rbp+140h+var_1C0]
0x18006a8d9  mov     rcx, rdi
0x18006a8dc  call    ?GetAttribute@OTelLogRecord@Diagnostics@@QEBA?AV?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@@Z; Diagnostics::OTelLogRecord::GetAttribute(std::wstring const &)
0x18006a8e1  nop
0x18006a8e2  xorps   xmm0, xmm0
0x18006a8e5  cmp     [rax+20h], r12b
0x18006a8e9  mov     qword ptr [rbp+140h+var_90], r12
0x18006a8f0  mov     qword ptr [rbp+140h+var_90+8], r12
0x18006a8f7  movups  xmmword ptr [rbp+140h+S2], xmm0
0x18006a8fe  jz      short loc_18006A923
0x18006a900  movups  xmm0, xmmword ptr [rax]
0x18006a903  movups  xmmword ptr [rbp+140h+S2], xmm0
0x18006a90a  movups  xmm1, xmmword ptr [rax+10h]
0x18006a90e  movups  [rbp+140h+var_90], xmm1
0x18006a915  mov     [rax], r12w
0x18006a919  mov     [rax+10h], r12
0x18006a91d  mov     [rax+18h], r13
0x18006a921  jmp     short loc_18006A936
0x18006a923  xor     r8d, r8d
0x18006a926  mov     rdx, rbx
0x18006a929  lea     rcx, [rbp+140h+S2]
0x18006a930  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18006a935  nop
0x18006a936  cmp     [rbp+140h+var_1A0], r12b
0x18006a93a  jz      short loc_18006A946
0x18006a93c  lea     rcx, [rbp+140h+var_1C0]
0x18006a940  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18006a945  nop
0x18006a946  lea     rcx, [rsp+240h+var_200]
0x18006a94b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18006a950  lea     rbx, ?allowedCategories@UpdateEventPatternWU@Diagnostics@@2QBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@B; std::wstring_view const near * const Diagnostics::UpdateEventPatternWU::allowedCategories
0x18006a957  lea     rax, qword_1800B2048
0x18006a95e  lea     rdx, [rbp+140h+S2]
0x18006a965  cmp     qword ptr [rbp+140h+var_90+8], r13
0x18006a96c  cmova   rdx, [rbp+140h+S2]; S2
0x18006a974  movups  xmm1, xmmword ptr [rbx]
0x18006a977  mov     r8, [rbx+8]; N
0x18006a97b  cmp     r8, qword ptr [rbp+140h+var_90]
0x18006a982  jnz     short loc_18006A99E
0x18006a984  test    r8, r8
0x18006a987  jz      short loc_18006A9A7
0x18006a989  movq    rcx, xmm1; S1
0x18006a98e  call    wmemcmp
0x18006a993  test    eax, eax
0x18006a995  lea     rax, qword_1800B2048
0x18006a99c  jz      short loc_18006A9A7
0x18006a99e  add     rbx, 10h
0x18006a9a2  cmp     rbx, rax
0x18006a9a5  jnz     short loc_18006A95E
0x18006a9a7  lea     rcx, [rbp+140h+S2]
0x18006a9ae  cmp     rbx, rax
0x18006a9b1  jz      loc_18006AD88
0x18006a9b7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18006a9bc  mov     rax, 7FFFFFFFFFFFFFFEh
0x18006a9c6  sub     rax, rsi
0x18006a9c9  cmp     rax, 1
0x18006a9cd  jb      loc_18006ADD3
0x18006a9d3  lea     r9, [rbp+140h+var_60]
0x18006a9da  cmp     [rbp+140h+var_50+8], r13
0x18006a9e1  cmova   r9, qword ptr [rbp+140h+var_60]
0x18006a9e9  mov     [rsp+240h+var_210], 1; __int64
0x18006a9f2  lea     rax, asc_1800AA2E0; "|"
0x18006a9f9  mov     [rsp+240h+Src], rax; Src
0x18006a9fe  mov     [rsp+240h+var_220], rsi; __int64
0x18006aa03  lea     rcx, [rbp+140h+var_190]; void *
0x18006aa07  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEB_W_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x18006aa0c  nop
0x18006aa0d  lea     rdx, [rbp+140h+var_80]
0x18006aa14  cmp     qword ptr [rbp+140h+var_70+8], r13
0x18006aa1b  cmova   rdx, qword ptr [rbp+140h+var_80]
0x18006aa23  mov     r8, r14
0x18006aa26  lea     rcx, [rbp+140h+var_190]; Src
0x18006aa2a  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::append(wchar_t const * const,unsigned __int64)
0x18006aa2f  xorps   xmm0, xmm0
0x18006aa32  movups  [rsp+240h+var_1E0], xmm0
0x18006aa37  xorps   xmm1, xmm1
0x18006aa3a  movdqu  [rsp+240h+var_1D0], xmm1
0x18006aa40  movups  xmm0, xmmword ptr [rax]
0x18006aa43  movups  [rsp+240h+var_1E0], xmm0
0x18006aa48  movups  xmm1, xmmword ptr [rax+10h]
0x18006aa4c  movups  [rsp+240h+var_1D0], xmm1
0x18006aa51  mov     [rax], r12w
0x18006aa55  mov     [rax+10h], r12
0x18006aa59  mov     [rax+18h], r13
0x18006aa5d  lea     r8, [rsp+240h+var_1E0]
0x18006aa62  lea     rdx, [rbp+140h+S2]
0x18006aa69  lea     rcx, [r15+8]
0x18006aa6d  call    ??$_Try_emplace@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$V@?$_Hash@V?$_Umap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UUpdateGroup@?$Connector_UpdateEventPattern@UUpdateEventPatternWU@Diagnostics@@@Diagnostics@@V?$_Uhash_compare@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UUpdateGroup@?$Connector_UpdateEventPattern@UUpdateEventPatternWU@Diagnostics@@@Diagnostics@@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UUpdateGroup@?$Connector_UpdateEventPattern@UUpdateEventPatternWU@Diagnostics@@@Diagnostics@@@std@@PEAX@std@@_N@1@$$QEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::_Hash<std::_Umap_traits<std::wstring,Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternWU>::UpdateGroup,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternWU>::UpdateGroup>>,0>>::_Try_emplace<std::wstring,>(std::wstring &&)
0x18006aa72  nop
0x18006aa73  lea     rcx, [rsp+240h+var_1E0]
0x18006aa78  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18006aa7d  nop
0x18006aa7e  lea     rcx, [rbp+140h+var_190]
0x18006aa82  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18006aa87  mov     rbx, [rbp+140h+S2]
0x18006aa8e  mov     esi, 5
0x18006aa93  cmp     byte ptr [rbp+140h+S2+8], r12b
0x18006aa9a  jz      loc_18006ABAE
0x18006aaa0  lea     rdx, [rbp+140h+var_60]
0x18006aaa7  lea     rcx, [rbx+30h]
0x18006aaab  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18006aab0  lea     rcx, [rbx+50h]
0x18006aab4  lea     rdx, [rbp+140h+var_80]
0x18006aabb  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18006aac0  xorps   xmm0, xmm0
0x18006aac3  movups  [rsp+240h+var_200], xmm0
0x18006aac8  xorps   xmm1, xmm1
0x18006aacb  movdqu  [rsp+240h+var_1F0], xmm1
0x18006aad1  mov     r8d, esi
0x18006aad4  lea     rdx, aTitle; "TITLE"
0x18006aadb  lea     rcx, [rsp+240h+var_200]
0x18006aae0  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18006aae5  nop
0x18006aae6  lea     r8, [rsp+240h+var_200]
0x18006aaeb  lea     rdx, [rbp+140h+var_1C0]
0x18006aaef  mov     rcx, rdi
0x18006aaf2  call    ?GetAttribute@OTelLogRecord@Diagnostics@@QEBA?AV?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@@Z; Diagnostics::OTelLogRecord::GetAttribute(std::wstring const &)
0x18006aaf7  nop
0x18006aaf8  lea     rdx, [rbp+140h+var_190]
0x18006aafc  mov     rcx, rax
0x18006aaff  call    ??$value_or@AEAY00$$CB_W@?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@QEHAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@AEAY00$$CB_W@Z; std::optional<std::wstring>::value_or<wchar_t const (&)[1]>(wchar_t const (&)[1])
0x18006ab04  lea     rcx, [rbx+70h]
0x18006ab08  mov     rdx, rax
0x18006ab0b  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18006ab10  lea     rcx, [rbp+140h+var_190]
0x18006ab14  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18006ab19  nop
0x18006ab1a  cmp     [rbp+140h+var_1A0], r12b
0x18006ab1e  jz      short loc_18006AB2A
0x18006ab20  lea     rcx, [rbp+140h+var_1C0]
0x18006ab24  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18006ab29  nop
0x18006ab2a  lea     rcx, [rsp+240h+var_200]
0x18006ab2f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18006ab34  xorps   xmm0, xmm0
0x18006ab37  movups  [rsp+240h+var_200], xmm0
0x18006ab3c  xorps   xmm1, xmm1
0x18006ab3f  movdqu  [rsp+240h+var_1F0], xmm1
0x18006ab45  mov     r8d, 8
0x18006ab4b  lea     rdx, aCategory_0; "CATEGORY"
0x18006ab52  lea     rcx, [rsp+240h+var_200]
0x18006ab57  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18006ab5c  nop
0x18006ab5d  lea     r8, [rsp+240h+var_200]
0x18006ab62  lea     rdx, [rbp+140h+var_1C0]
0x18006ab66  mov     rcx, rdi
0x18006ab69  call    ?GetAttribute@OTelLogRecord@Diagnostics@@QEBA?AV?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@@Z; Diagnostics::OTelLogRecord::GetAttribute(std::wstring const &)
0x18006ab6e  nop
0x18006ab6f  lea     rdx, [rbp+140h+var_190]
0x18006ab73  mov     rcx, rax
0x18006ab76  call    ??$value_or@AEAY00$$CB_W@?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@QEHAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@AEAY00$$CB_W@Z; std::optional<std::wstring>::value_or<wchar_t const (&)[1]>(wchar_t const (&)[1])
0x18006ab7b  lea     rcx, [rbx+90h]
0x18006ab82  mov     rdx, rax
0x18006ab85  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18006ab8a  lea     rcx, [rbp+140h+var_190]
0x18006ab8e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18006ab93  nop
0x18006ab94  cmp     [rbp+140h+var_1A0], r12b
0x18006ab98  jz      short loc_18006ABA4
0x18006ab9a  lea     rcx, [rbp+140h+var_1C0]
0x18006ab9e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18006aba3  nop
0x18006aba4  lea     rcx, [rsp+240h+var_200]
0x18006aba9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18006abae  imul    rax, [rdi+80h], 64h ; 'd'
0x18006abb6  mov     [rbp+140h+var_160], rax
0x18006abba  xorps   xmm0, xmm0
0x18006abbd  movups  xmmword ptr [rbp+140h+S2], xmm0
0x18006abc4  xorps   xmm1, xmm1
0x18006abc7  movdqu  [rbp+140h+var_90], xmm1
0x18006abcf  mov     r8, rsi
0x18006abd2  lea     rdx, aEvent; "EVENT"
0x18006abd9  lea     rcx, [rbp+140h+S2]
0x18006abe0  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18006abe5  nop
0x18006abe6  lea     r8, [rbp+140h+S2]
0x18006abed  lea     rdx, [rbp+140h+var_190]
0x18006abf1  mov     rcx, rdi
0x18006abf4  call    ?GetAttribute@OTelLogRecord@Diagnostics@@QEBA?AV?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@@Z; Diagnostics::OTelLogRecord::GetAttribute(std::wstring const &)
0x18006abf9  nop
0x18006abfa  lea     rdx, [rbp+140h+var_158]
0x18006abfe  mov     rcx, rax
0x18006ac01  call    ??$value_or@AEAY00$$CB_W@?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@QEHAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@AEAY00$$CB_W@Z; std::optional<std::wstring>::value_or<wchar_t const (&)[1]>(wchar_t const (&)[1])
0x18006ac06  nop
0x18006ac07  xorps   xmm0, xmm0
  ... truncated ...
```
