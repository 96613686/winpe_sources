# Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternOther>::ProcessTelemetry(Diagnostics::OTelLogRecord &,Diagnostics::OTelFile &)

- ea: `0x18006afe0`
- end: `0x18006b66a`
- name: `?ProcessTelemetry@?$Connector_UpdateEventPattern@UUpdateEventPatternOther@Diagnostics@@@Diagnostics@@UEAA_NAEAVOTelLogRecord@2@AEAVOTelFile@2@@Z`
- size: `1674`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180015360`
- `0x180018eec`
- `0x180018f68`
- `0x180019080`
- `0x18001adcc`
- `0x180020dc8`
- `0x18002a6ac`
- `0x18003c324`
- `0x18006afe0`
- `0x18006cfcc`
- `0x18006db04`
- `0x18008fe00`

## string_xrefs

- `0x18006b0f2`: `UPDATEID`

## pseudocode

```c
// Hidden C++ exception states: #wind=27
char __fastcall Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternOther>::ProcessTelemetry(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 Attribute; // rax
  __int64 v6; // rax
  __int64 v7; // rax
  _QWORD *v8; // rdi
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  __int128 v16; // xmm2
  __int128 v17; // xmm3
  __int64 v18; // rdx
  __int128 v20; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v21; // [rsp+50h] [rbp-B0h]
  __int128 v22; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v23; // [rsp+70h] [rbp-90h]
  __int64 v24; // [rsp+80h] [rbp-80h] BYREF
  __int128 v25; // [rsp+88h] [rbp-78h] BYREF
  __int128 v26; // [rsp+98h] [rbp-68h]
  __int128 v27; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v28; // [rsp+B8h] [rbp-48h]
  __int128 v29; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v30; // [rsp+D8h] [rbp-28h]
  _BYTE v31[32]; // [rsp+F8h] [rbp-8h] BYREF
  char v32; // [rsp+118h] [rbp+18h]
  _BYTE v33[32]; // [rsp+120h] [rbp+20h] BYREF
  _OWORD v34[2]; // [rsp+140h] [rbp+40h] BYREF
  _OWORD v35[2]; // [rsp+160h] [rbp+60h] BYREF
  _BYTE v36[40]; // [rsp+180h] [rbp+80h] BYREF
  _BYTE v37[40]; // [rsp+1A8h] [rbp+A8h] BYREF
  _BYTE v38[40]; // [rsp+1D0h] [rbp+D0h] BYREF
  _BYTE v39[40]; // [rsp+1F8h] [rbp+F8h] BYREF
  __int128 v40; // [rsp+220h] [rbp+120h] BYREF
  __int128 v41; // [rsp+230h] [rbp+130h]
  __int128 v42; // [rsp+240h] [rbp+140h] BYREF
  __int64 v43[2]; // [rsp+250h] [rbp+150h]

  *(_QWORD *)(a1 + 72) = a3;
  v40 = 0;
  v41 = 0;
  std::wstring::_Construct<1,wchar_t const *>(&v40, L"PROVIDERID", 0xAu);
  Attribute = Diagnostics::OTelLogRecord::GetAttribute(a2, v31, &v40);
  if ( *(_BYTE *)(Attribute + 32) )
  {
    v42 = *(_OWORD *)Attribute;
    *(_OWORD *)v43 = *(_OWORD *)(Attribute + 16);
    *(_WORD *)Attribute = 0;
    *(_QWORD *)(Attribute + 16) = 0;
    *(_QWORD *)(Attribute + 24) = 7;
  }
  else
  {
    v42 = 0;
    v43[0] = 0;
    v43[1] = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v42, &psz, 0);
  }
  if ( v32 )
    std::wstring::~wstring((__int64)v31);
  std::wstring::~wstring((__int64)&v40);
  v22 = 0;
  v23 = 0;
  std::wstring::_Construct<1,wchar_t const *>(&v22, L"UPDATEID", 8u);
  v6 = Diagnostics::OTelLogRecord::GetAttribute(a2, v36, &v22);
  if ( *(_BYTE *)(v6 + 32) )
  {
    v40 = *(_OWORD *)v6;
    v41 = *(_OWORD *)(v6 + 16);
    *(_WORD *)v6 = 0;
    *(_QWORD *)(v6 + 16) = 0;
    *(_QWORD *)(v6 + 24) = 7;
  }
  else
  {
    v40 = 0;
    v41 = 0u;
    std::wstring::_Construct<1,wchar_t const *>(&v40, &psz, 0);
  }
  if ( v36[32] )
    std::wstring::~wstring((__int64)v36);
  std::wstring::~wstring((__int64)&v22);
  if ( v43[0] && (_QWORD)v41 )
  {
    if ( v43[0] == 0x7FFFFFFFFFFFFFFELL )
      std::_Xlen_string();
    std::wstring::wstring(v33, v43[0], L"|", 1);
    v7 = std::wstring::append(v33);
    v20 = 0;
    v21 = 0;
    v20 = *(_OWORD *)v7;
    v21 = *(_OWORD *)(v7 + 16);
    *(_WORD *)v7 = 0;
    *(_QWORD *)(v7 + 16) = 0;
    *(_QWORD *)(v7 + 24) = 7;
    std::_Hash<std::_Umap_traits<std::wstring,Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternWU>::UpdateGroup,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternWU>::UpdateGroup>>,0>>::_Try_emplace<std::wstring,>(
      (float *)(a1 + 8),
      (__int64)&v22,
      &v20);
    std::wstring::~wstring((__int64)&v20);
    std::wstring::~wstring((__int64)v33);
    v8 = (_QWORD *)v22;
    if ( BYTE8(v22) )
    {
      std::wstring::operator=(v22 + 48, &v42);
      std::wstring::operator=(v8 + 10, &v40);
      v20 = 0;
      v21 = 0;
      std::wstring::_Construct<1,wchar_t const *>(&v20, L"TITLE", 5u);
      v9 = Diagnostics::OTelLogRecord::GetAttribute(a2, v31, &v20);
      v10 = std::optional<std::wstring>::value_or<wchar_t const (&)[1]>(v9, v33);
      std::wstring::operator=(v8 + 14, v10);
      std::wstring::~wstring((__int64)v33);
      if ( v32 )
        std::wstring::~wstring((__int64)v31);
      std::wstring::~wstring((__int64)&v20);
      v20 = 0;
      v21 = 0;
      std::wstring::_Construct<1,wchar_t const *>(&v20, L"CATEGORY", 8u);
      v11 = Diagnostics::OTelLogRecord::GetAttribute(a2, v31, &v20);
      v12 = std::optional<std::wstring>::value_or<wchar_t const (&)[1]>(v11, v33);
      std::wstring::operator=(v8 + 18, v12);
      std::wstring::~wstring((__int64)v33);
      if ( v32 )
        std::wstring::~wstring((__int64)v31);
      std::wstring::~wstring((__int64)&v20);
    }
    v24 = 100LL * *(_QWORD *)(a2 + 128);
    memset(v35, 0, sizeof(v35));
    std::wstring::_Construct<1,wchar_t const *>(v35, L"EVENT", 5u);
    v13 = Diagnostics::OTelLogRecord::GetAttribute(a2, v39, v35);
    if ( *(_BYTE *)(v13 + 32) )
    {
      v25 = *(_OWORD *)v13;
      v26 = *(_OWORD *)(v13 + 16);
      *(_WORD *)v13 = 0;
      *(_QWORD *)(v13 + 16) = 0;
      *(_QWORD *)(v13 + 24) = 7;
    }
    else
    {
      v25 = 0;
      v26 = 0u;
      std::wstring::_Construct<1,wchar_t const *>(&v25, &psz, 0);
    }
    memset(v34, 0, sizeof(v34));
    std::wstring::_Construct<1,wchar_t const *>(v34, L"RESULT", 6u);
    v14 = Diagnostics::OTelLogRecord::GetAttribute(a2, v38, v34);
    if ( *(_BYTE *)(v14 + 32) )
    {
      v27 = *(_OWORD *)v14;
      v28 = *(_OWORD *)(v14 + 16);
      *(_WORD *)v14 = 0;
      *(_QWORD *)(v14 + 16) = 0;
      *(_QWORD *)(v14 + 24) = 7;
    }
    else
    {
      v27 = 0;
      v28 = 0u;
      std::wstring::_Construct<1,wchar_t const *>(&v27, &psz, 0);
    }
    v22 = 0;
    v23 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v22, L"REASON", 6u);
    v15 = Diagnostics::OTelLogRecord::GetAttribute(a2, v37, &v22);
    if ( *(_BYTE *)(v15 + 32) )
    {
      v16 = *(_OWORD *)v15;
      v29 = *(_OWORD *)v15;
      v17 = *(_OWORD *)(v15 + 16);
      v30 = v17;
      *(_WORD *)v15 = 0;
      *(_QWORD *)(v15 + 16) = 0;
      *(_QWORD *)(v15 + 24) = 7;
    }
    else
    {
      v29 = 0;
      v30 = 0u;
      std::wstring::_Construct<1,wchar_t const *>(&v29, &psz, 0);
      v17 = v30;
      v16 = v29;
    }
    v18 = v8[23];
    if ( v18 == v8[24] )
    {
      std::vector<Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternOther>::EventEntry,std::allocator<Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternOther>::EventEntry>>::_Emplace_reallocate<Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternOther>::EventEntry>(
        v8 + 22,
        (_QWORD *)v18,
        &v24);
    }
    else
    {
      *(_QWORD *)v18 = v24;
      *(_OWORD *)(v18 + 8) = v25;
      *(_OWORD *)(v18 + 24) = v26;
      *(_QWORD *)&v26 = 0;
      *((_QWORD *)&v26 + 1) = 7;
      LOWORD(v25) = 0;
      *(_OWORD *)(v18 + 40) = v27;
      *(_OWORD *)(v18 + 56) = v28;
      *(_QWORD *)&v28 = 0;
      *((_QWORD *)&v28 + 1) = 7;
      LOWORD(v27) = 0;
      *(_OWORD *)(v18 + 72) = v16;
      *(_OWORD *)(v18 + 88) = v17;
      *(_QWORD *)&v30 = 0;
      *((_QWORD *)&v30 + 1) = 7;
      LOWORD(v29) = 0;
      v8[23] += 104LL;
    }
    std::wstring::~wstring((__int64)&v29);
    std::wstring::~wstring((__int64)&v27);
    std::wstring::~wstring((__int64)&v25);
    if ( v37[32] )
      std::wstring::~wstring((__int64)v37);
    std::wstring::~wstring((__int64)&v22);
    if ( v38[32] )
      std::wstring::~wstring((__int64)v38);
    std::wstring::~wstring((__int64)v34);
    if ( v39[32] )
      std::wstring::~wstring((__int64)v39);
    std::wstring::~wstring((__int64)v35);
  }
  std::wstring::~wstring((__int64)&v40);
  std::wstring::~wstring((__int64)&v42);
  return 1;
}

```

## disassembly

```asm
0x18006afe0  mov     [rsp-8+arg_10], rbx
0x18006afe5  mov     [rsp-8+arg_18], rsi
0x18006afea  push    rbp
0x18006afeb  push    rdi
0x18006afec  push    r12
0x18006afee  push    r14
0x18006aff0  push    r15
0x18006aff2  lea     rbp, [rsp-170h]
0x18006affa  sub     rsp, 270h
0x18006b001  mov     rax, cs:__security_cookie
0x18006b008  xor     rax, rsp
0x18006b00b  mov     [rbp+190h+var_30], rax
0x18006b012  mov     rbx, rdx
0x18006b015  mov     rsi, rcx
0x18006b018  xor     r14d, r14d
0x18006b01b  mov     [rcx+48h], r8
0x18006b01f  xorps   xmm0, xmm0
0x18006b022  movups  [rbp+190h+var_70], xmm0
0x18006b029  xorps   xmm1, xmm1
0x18006b02c  movdqu  [rbp+190h+var_60], xmm1
0x18006b034  lea     r8d, [r14+0Ah]
0x18006b038  lea     rdx, aProviderid; "PROVIDERID"
0x18006b03f  lea     rcx, [rbp+190h+var_70]
0x18006b046  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18006b04b  nop
0x18006b04c  lea     r8, [rbp+190h+var_70]
0x18006b053  lea     rdx, [rbp+190h+var_198]
0x18006b057  mov     rcx, rbx
0x18006b05a  call    ?GetAttribute@OTelLogRecord@Diagnostics@@QEBA?AV?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@@Z; Diagnostics::OTelLogRecord::GetAttribute(std::wstring const &)
0x18006b05f  nop
0x18006b060  lea     r12, psz
0x18006b067  lea     r15d, [r14+7]
0x18006b06b  cmp     [rax+20h], r14b
0x18006b06f  jz      short loc_18006B094
0x18006b071  movups  xmm0, xmmword ptr [rax]
0x18006b074  movups  [rbp+190h+var_50], xmm0
0x18006b07b  movups  xmm1, xmmword ptr [rax+10h]
0x18006b07f  movups  xmmword ptr [rbp+190h+var_40], xmm1
0x18006b086  mov     [rax], r14w
0x18006b08a  mov     [rax+10h], r14
0x18006b08e  mov     [rax+18h], r15
0x18006b092  jmp     short loc_18006B0BF
0x18006b094  xorps   xmm0, xmm0
0x18006b097  movups  [rbp+190h+var_50], xmm0
0x18006b09e  mov     [rbp+190h+var_40], r14
0x18006b0a5  mov     [rbp+190h+var_40+8], r14
0x18006b0ac  xor     r8d, r8d
0x18006b0af  mov     rdx, r12
0x18006b0b2  lea     rcx, [rbp+190h+var_50]
0x18006b0b9  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18006b0be  nop
0x18006b0bf  cmp     [rbp+190h+var_178], r14b
0x18006b0c3  jz      short loc_18006B0CF
0x18006b0c5  lea     rcx, [rbp+190h+var_198]
0x18006b0c9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18006b0ce  nop
0x18006b0cf  lea     rcx, [rbp+190h+var_70]
0x18006b0d6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18006b0db  xorps   xmm0, xmm0
0x18006b0de  movups  [rsp+290h+var_230], xmm0
0x18006b0e3  xorps   xmm1, xmm1
0x18006b0e6  movdqu  [rsp+290h+var_220], xmm1
0x18006b0ec  mov     r8d, 8
0x18006b0f2  lea     rdx, aUpdateid_0; "UPDATEID"
0x18006b0f9  lea     rcx, [rsp+290h+var_230]
0x18006b0fe  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18006b103  nop
0x18006b104  lea     r8, [rsp+290h+var_230]
0x18006b109  lea     rdx, [rbp+190h+var_110]
0x18006b110  mov     rcx, rbx
0x18006b113  call    ?GetAttribute@OTelLogRecord@Diagnostics@@QEBA?AV?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@@Z; Diagnostics::OTelLogRecord::GetAttribute(std::wstring const &)
0x18006b118  nop
0x18006b119  cmp     [rax+20h], r14b
0x18006b11d  jz      short loc_18006B142
0x18006b11f  movups  xmm0, xmmword ptr [rax]
0x18006b122  movups  [rbp+190h+var_70], xmm0
0x18006b129  movups  xmm1, xmmword ptr [rax+10h]
0x18006b12d  movups  [rbp+190h+var_60], xmm1
0x18006b134  mov     [rax], r14w
0x18006b138  mov     [rax+10h], r14
0x18006b13c  mov     [rax+18h], r15
0x18006b140  jmp     short loc_18006B16D
0x18006b142  xorps   xmm0, xmm0
0x18006b145  movups  [rbp+190h+var_70], xmm0
0x18006b14c  mov     qword ptr [rbp+190h+var_60], r14
0x18006b153  mov     qword ptr [rbp+190h+var_60+8], r14
0x18006b15a  xor     r8d, r8d
0x18006b15d  mov     rdx, r12
0x18006b160  lea     rcx, [rbp+190h+var_70]
0x18006b167  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18006b16c  nop
0x18006b16d  cmp     [rbp+190h+var_F0], r14b
0x18006b174  jz      short loc_18006B183
0x18006b176  lea     rcx, [rbp+190h+var_110]
0x18006b17d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18006b182  nop
0x18006b183  lea     rcx, [rsp+290h+var_230]
0x18006b188  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18006b18d  mov     rcx, [rbp+190h+var_40]
0x18006b194  test    rcx, rcx
0x18006b197  jz      loc_18006B61E
0x18006b19d  mov     rdi, qword ptr [rbp+190h+var_60]
0x18006b1a4  test    rdi, rdi
0x18006b1a7  jz      loc_18006B61E
0x18006b1ad  mov     rax, 7FFFFFFFFFFFFFFEh
0x18006b1b7  sub     rax, rcx
0x18006b1ba  cmp     rax, 1
0x18006b1be  jb      loc_18006B664
0x18006b1c4  lea     r9, [rbp+190h+var_50]
0x18006b1cb  cmp     [rbp+190h+var_40+8], r15
0x18006b1d2  cmova   r9, qword ptr [rbp+190h+var_50]
0x18006b1da  mov     [rsp+290h+var_260], 1; __int64
0x18006b1e3  lea     rax, asc_1800AA2E0; "|"
0x18006b1ea  mov     [rsp+290h+Src], rax; Src
0x18006b1ef  mov     [rsp+290h+var_270], rcx; __int64
0x18006b1f4  lea     rcx, [rbp+190h+var_170]; void *
0x18006b1f8  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEB_W_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x18006b1fd  nop
0x18006b1fe  lea     rdx, [rbp+190h+var_70]
0x18006b205  cmp     qword ptr [rbp+190h+var_60+8], r15
0x18006b20c  cmova   rdx, qword ptr [rbp+190h+var_70]
0x18006b214  mov     r8, rdi
0x18006b217  lea     rcx, [rbp+190h+var_170]; Src
0x18006b21b  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::append(wchar_t const * const,unsigned __int64)
0x18006b220  xorps   xmm0, xmm0
0x18006b223  movups  [rsp+290h+var_250], xmm0
0x18006b228  xorps   xmm1, xmm1
0x18006b22b  movdqu  [rsp+290h+var_240], xmm1
0x18006b231  movups  xmm0, xmmword ptr [rax]
0x18006b234  movups  [rsp+290h+var_250], xmm0
0x18006b239  movups  xmm1, xmmword ptr [rax+10h]
0x18006b23d  movups  [rsp+290h+var_240], xmm1
0x18006b242  mov     [rax], r14w
0x18006b246  mov     [rax+10h], r14
0x18006b24a  mov     [rax+18h], r15
0x18006b24e  lea     r8, [rsp+290h+var_250]
0x18006b253  lea     rdx, [rsp+290h+var_230]
0x18006b258  lea     rcx, [rsi+8]
0x18006b25c  call    ??$_Try_emplace@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$V@?$_Hash@V?$_Umap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UUpdateGroup@?$Connector_UpdateEventPattern@UUpdateEventPatternWU@Diagnostics@@@Diagnostics@@V?$_Uhash_compare@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UUpdateGroup@?$Connector_UpdateEventPattern@UUpdateEventPatternWU@Diagnostics@@@Diagnostics@@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UUpdateGroup@?$Connector_UpdateEventPattern@UUpdateEventPatternWU@Diagnostics@@@Diagnostics@@@std@@PEAX@std@@_N@1@$$QEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::_Hash<std::_Umap_traits<std::wstring,Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternWU>::UpdateGroup,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternWU>::UpdateGroup>>,0>>::_Try_emplace<std::wstring,>(std::wstring &&)
0x18006b261  nop
0x18006b262  lea     rcx, [rsp+290h+var_250]
0x18006b267  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18006b26c  nop
0x18006b26d  lea     rcx, [rbp+190h+var_170]
0x18006b271  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18006b276  mov     rdi, qword ptr [rsp+290h+var_230]
0x18006b27b  mov     esi, 5
0x18006b280  cmp     byte ptr [rsp+290h+var_230+8], r14b
0x18006b285  jz      loc_18006B399
0x18006b28b  lea     rdx, [rbp+190h+var_50]
0x18006b292  lea     rcx, [rdi+30h]
0x18006b296  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18006b29b  lea     rcx, [rdi+50h]
0x18006b29f  lea     rdx, [rbp+190h+var_70]
0x18006b2a6  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18006b2ab  xorps   xmm0, xmm0
0x18006b2ae  movups  [rsp+290h+var_250], xmm0
0x18006b2b3  xorps   xmm1, xmm1
0x18006b2b6  movdqu  [rsp+290h+var_240], xmm1
0x18006b2bc  mov     r8d, esi
0x18006b2bf  lea     rdx, aTitle; "TITLE"
0x18006b2c6  lea     rcx, [rsp+290h+var_250]
0x18006b2cb  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18006b2d0  nop
0x18006b2d1  lea     r8, [rsp+290h+var_250]
0x18006b2d6  lea     rdx, [rbp+190h+var_198]
0x18006b2da  mov     rcx, rbx
0x18006b2dd  call    ?GetAttribute@OTelLogRecord@Diagnostics@@QEBA?AV?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@@Z; Diagnostics::OTelLogRecord::GetAttribute(std::wstring const &)
0x18006b2e2  nop
0x18006b2e3  lea     rdx, [rbp+190h+var_170]
0x18006b2e7  mov     rcx, rax
0x18006b2ea  call    ??$value_or@AEAY00$$CB_W@?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@QEHAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@AEAY00$$CB_W@Z; std::optional<std::wstring>::value_or<wchar_t const (&)[1]>(wchar_t const (&)[1])
0x18006b2ef  lea     rcx, [rdi+70h]
0x18006b2f3  mov     rdx, rax
0x18006b2f6  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18006b2fb  lea     rcx, [rbp+190h+var_170]
0x18006b2ff  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18006b304  nop
0x18006b305  cmp     [rbp+190h+var_178], r14b
0x18006b309  jz      short loc_18006B315
0x18006b30b  lea     rcx, [rbp+190h+var_198]
0x18006b30f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18006b314  nop
0x18006b315  lea     rcx, [rsp+290h+var_250]
0x18006b31a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18006b31f  xorps   xmm0, xmm0
0x18006b322  movups  [rsp+290h+var_250], xmm0
0x18006b327  xorps   xmm1, xmm1
0x18006b32a  movdqu  [rsp+290h+var_240], xmm1
0x18006b330  mov     r8d, 8
0x18006b336  lea     rdx, aCategory_0; "CATEGORY"
0x18006b33d  lea     rcx, [rsp+290h+var_250]
0x18006b342  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18006b347  nop
0x18006b348  lea     r8, [rsp+290h+var_250]
0x18006b34d  lea     rdx, [rbp+190h+var_198]
0x18006b351  mov     rcx, rbx
0x18006b354  call    ?GetAttribute@OTelLogRecord@Diagnostics@@QEBA?AV?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@@Z; Diagnostics::OTelLogRecord::GetAttribute(std::wstring const &)
0x18006b359  nop
0x18006b35a  lea     rdx, [rbp+190h+var_170]
0x18006b35e  mov     rcx, rax
0x18006b361  call    ??$value_or@AEAY00$$CB_W@?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@QEHAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@AEAY00$$CB_W@Z; std::optional<std::wstring>::value_or<wchar_t const (&)[1]>(wchar_t const (&)[1])
0x18006b366  lea     rcx, [rdi+90h]
0x18006b36d  mov     rdx, rax
0x18006b370  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18006b375  lea     rcx, [rbp+190h+var_170]
0x18006b379  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18006b37e  nop
0x18006b37f  cmp     [rbp+190h+var_178], r14b
0x18006b383  jz      short loc_18006B38F
0x18006b385  lea     rcx, [rbp+190h+var_198]
0x18006b389  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18006b38e  nop
0x18006b38f  lea     rcx, [rsp+290h+var_250]
0x18006b394  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18006b399  imul    rax, [rbx+80h], 64h ; 'd'
0x18006b3a1  mov     [rbp+190h+var_210], rax
0x18006b3a5  xorps   xmm0, xmm0
0x18006b3a8  movups  [rbp+190h+var_130], xmm0
0x18006b3ac  xorps   xmm1, xmm1
0x18006b3af  movdqu  [rbp+190h+var_120], xmm1
0x18006b3b4  mov     r8, rsi
0x18006b3b7  lea     rdx, aEvent; "EVENT"
0x18006b3be  lea     rcx, [rbp+190h+var_130]
0x18006b3c2  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18006b3c7  nop
0x18006b3c8  lea     r8, [rbp+190h+var_130]
0x18006b3cc  lea     rdx, [rbp+190h+var_98]
0x18006b3d3  mov     rcx, rbx
0x18006b3d6  call    ?GetAttribute@OTelLogRecord@Diagnostics@@QEBA?AV?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@@Z; Diagnostics::OTelLogRecord::GetAttribute(std::wstring const &)
0x18006b3db  nop
0x18006b3dc  cmp     [rax+20h], r14b
0x18006b3e0  jz      short loc_18006B3FF
0x18006b3e2  movups  xmm1, xmmword ptr [rax]
0x18006b3e5  movups  [rbp+190h+var_208], xmm1
0x18006b3e9  movups  xmm0, xmmword ptr [rax+10h]
0x18006b3ed  movups  [rbp+190h+var_1F8], xmm0
0x18006b3f1  mov     [rax], r14w
0x18006b3f5  mov     [rax+10h], r14
0x18006b3f9  mov     [rax+18h], r15
0x18006b3fd  jmp     short loc_18006B41E
0x18006b3ff  xorps   xmm0, xmm0
0x18006b402  movups  [rbp+190h+var_208], xmm0
0x18006b406  mov     qword ptr [rbp+190h+var_1F8], r14
0x18006b40a  mov     qword ptr [rbp+190h+var_1F8+8], r14
0x18006b40e  xor     r8d, r8d
0x18006b411  mov     rdx, r12
0x18006b414  lea     rcx, [rbp+190h+var_208]
0x18006b418  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18006b41d  nop
0x18006b41e  xorps   xmm0, xmm0
0x18006b421  movups  [rbp+190h+var_150], xmm0
0x18006b425  xorps   xmm1, xmm1
0x18006b428  movdqu  [rbp+190h+var_140], xmm1
0x18006b42d  mov     esi, 6
0x18006b432  mov     r8d, esi
0x18006b435  lea     rdx, aResult; "RESULT"
0x18006b43c  lea     rcx, [rbp+190h+var_150]
0x18006b440  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18006b445  nop
0x18006b446  lea     r8, [rbp+190h+var_150]
0x18006b44a  lea     rdx, [rbp+190h+var_C0]
0x18006b451  mov     rcx, rbx
0x18006b454  call    ?GetAttribute@OTelLogRecord@Diagnostics@@QEBA?AV?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@@Z; Diagnostics::OTelLogRecord::GetAttribute(std::wstring const &)
0x18006b459  nop
0x18006b45a  cmp     [rax+20h], r14b
0x18006b45e  jz      short loc_18006B47D
0x18006b460  movups  xmm1, xmmword ptr [rax]
0x18006b463  movups  [rbp+190h+var_1E8], xmm1
0x18006b467  movups  xmm0, xmmword ptr [rax+10h]
0x18006b46b  movups  [rbp+190h+var_1D8], xmm0
0x18006b46f  mov     [rax], r14w
0x18006b473  mov     [rax+10h], r14
0x18006b477  mov     [rax+18h], r15
0x18006b47b  jmp     short loc_18006B49C
0x18006b47d  xorps   xmm0, xmm0
0x18006b480  movups  [rbp+190h+var_1E8], xmm0
0x18006b484  mov     qword ptr [rbp+190h+var_1D8], r14
0x18006b488  mov     qword ptr [rbp+190h+var_1D8+8], r14
0x18006b48c  xor     r8d, r8d
0x18006b48f  mov     rdx, r12
0x18006b492  lea     rcx, [rbp+190h+var_1E8]
0x18006b496  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18006b49b  nop
0x18006b49c  xorps   xmm0, xmm0
0x18006b49f  movups  [rsp+290h+var_230], xmm0
0x18006b4a4  xorps   xmm1, xmm1
0x18006b4a7  movdqu  [rsp+290h+var_220], xmm1
0x18006b4ad  mov     r8, rsi
0x18006b4b0  lea     rdx, aReason_0; "REASON"
0x18006b4b7  lea     rcx, [rsp+290h+var_230]
0x18006b4bc  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18006b4c1  nop
0x18006b4c2  lea     r8, [rsp+290h+var_230]
0x18006b4c7  lea     rdx, [rbp+190h+var_E8]
0x18006b4ce  mov     rcx, rbx
0x18006b4d1  call    ?GetAttribute@OTelLogRecord@Diagnostics@@QEBA?AV?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@@Z; Diagnostics::OTelLogRecord::GetAttribute(std::wstring const &)
0x18006b4d6  nop
0x18006b4d7  cmp     [rax+20h], r14b
0x18006b4db  jz      short loc_18006B4FA
  ... truncated ...
```
