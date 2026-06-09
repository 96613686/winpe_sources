# Microsoft::Diagnostics::UsageAnalyzer::InlineUpdate(Microsoft::Diagnostics::ITriggerInst const &)

- ea: `0x18007dc84`
- end: `0x18007e205`
- name: `?InlineUpdate@UsageAnalyzer@Diagnostics@Microsoft@@QEAAXAEBVITriggerInst@23@@Z`
- size: `1409`
- prototype: `void __fastcall(Microsoft::Diagnostics::UsageAnalyzer *__hidden this, const struct Microsoft::Diagnostics::ITriggerInst *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18029b5f0`

## callees

- `0x18001c5b0`
- `0x180020fbc`
- `0x180053740`
- `0x180057d34`
- `0x1800717ec`
- `0x18007dc84`
- `0x18007f0d8`
- `0x1800bc2e0`
- `0x1802c497c`
- `0x1802c4a10`
- `0x1802c6b54`
- `0x1802c8248`
- `0x1802c84c0`
- `0x180346010`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x18007e1d0`
- `msvcp_win!_Mtx_unlock` at `0x18007e1e0`
- `msvcp_win!_Mtx_unlock` at `0x18007e1d0`
- `msvcp_win!_Mtx_unlock` at `0x18007e1e0`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18007df0c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18007e17d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18007df0c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18007e17d`

## string_xrefs

- `0x18007dd28`: `onecore\base\telemetry\utc\service\analysis\usageanalyzer.cpp`
- `0x18007dde8`: `onecore\base\telemetry\utc\service\analysis\usageanalyzer.cpp`
- `0x18007de43`: `onecore\base\telemetry\utc\service\analysis\usageanalyzer.cpp`
- `0x18007de9f`: `onecore\base\telemetry\utc\service\analysis\usageanalyzer.cpp`
- `0x18007ded7`: `onecore\base\telemetry\utc\service\analysis\usageanalyzer.cpp`
- `0x18007df98`: `onecore\base\telemetry\utc\service\analysis\usageanalyzer.cpp`
- `0x18007dfcf`: `onecore\base\telemetry\utc\service\analysis\usageanalyzer.cpp`
- `0x18007e02e`: `onecore\base\telemetry\utc\service\analysis\usageanalyzer.cpp`
- `0x18007e08c`: `onecore\base\telemetry\utc\service\analysis\usageanalyzer.cpp`
- `0x18007e0e5`: `onecore\base\telemetry\utc\service\analysis\usageanalyzer.cpp`
- `0x18007e11d`: `onecore\base\telemetry\utc\service\analysis\usageanalyzer.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall Microsoft::Diagnostics::UsageAnalyzer::InlineUpdate(
        Microsoft::Diagnostics::UsageAnalyzer *this,
        const struct Microsoft::Diagnostics::ITriggerInst *a2)
{
  struct _Mtx_internal_imp_t *v4; // r13
  _QWORD *v5; // rax
  __int64 v6; // rcx
  __int64 *v7; // rax
  __int64 v8; // rdi
  __int64 v9; // rbx
  _QWORD *FullyQualifiedName; // rax
  int v11; // ecx
  char v12; // di
  __int64 v13; // rax
  __int64 v14; // rdx
  wil::details::in1diag3 *v15; // r10
  struct Microsoft::Diagnostics::UsageAnalyzer::ProcessRecord *v16; // rbx
  __int64 *v17; // rax
  __int64 v18; // rdi
  __int64 v19; // rbx
  _QWORD *v20; // rax
  wil::details::in1diag3 *v21; // r10
  __int64 v22; // rax
  __int128 v23; // xmm1
  __int64 v24; // rdx
  int v25; // ebx
  char v26; // al
  __int64 v27; // rax
  __int64 v28; // rdx
  wil::details::in1diag3 *v29; // r10
  unsigned __int64 v30; // r15
  unsigned __int64 v31; // rbx
  ULONGLONG TickCount64; // rax
  int v33[4]; // [rsp+20h] [rbp-40h] BYREF
  const wchar_t *v34; // [rsp+30h] [rbp-30h] BYREF
  __int64 v35; // [rsp+38h] [rbp-28h]
  const char *v36; // [rsp+40h] [rbp-20h] BYREF
  __int64 v37; // [rsp+48h] [rbp-18h]
  const char *v38; // [rsp+50h] [rbp-10h] BYREF
  __int64 v39; // [rsp+58h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+38h]
  unsigned __int64 v41; // [rsp+A0h] [rbp+40h] BYREF
  char *v42; // [rsp+B0h] [rbp+50h]
  char *v43; // [rsp+B8h] [rbp+58h]

  if ( *((_BYTE *)this + 576) )
  {
    v4 = (Microsoft::Diagnostics::UsageAnalyzer *)((char *)this + 592);
    v42 = (char *)this + 592;
    std::_Mutex_base::lock((Microsoft::Diagnostics::UsageAnalyzer *)((char *)this + 592));
    if ( !*(_BYTE *)((*(__int64 (__fastcall **)(const struct Microsoft::Diagnostics::ITriggerInst *))(*(_QWORD *)a2 + 120LL))(a2)
                   + 48) )
    {
      v34 = L"data";
      v35 = 4;
      v36 = (char *)a2 + 16;
      LODWORD(v37) = 0;
      JsonBuilder::find<>((char *)a2 + 16, v33, &v36, &v34);
      if ( !v33[2] )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x4F,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\usageanalyzer.cpp",
          (const char *)0x80070490LL,
          v33[0]);
      v5 = (_QWORD *)(*(__int64 (__fastcall **)(const struct Microsoft::Diagnostics::ITriggerInst *))(*(_QWORD *)a2 + 80LL))(a2);
      v6 = *v5 - *(_QWORD *)&Microsoft::Diagnostics::EventBasedMetadata::k_kernelTLProcessProviderGuid.Data1;
      if ( *v5 == *(_QWORD *)&Microsoft::Diagnostics::EventBasedMetadata::k_kernelTLProcessProviderGuid.Data1 )
        v6 = v5[1] - *(_QWORD *)Microsoft::Diagnostics::EventBasedMetadata::k_kernelTLProcessProviderGuid.Data4;
      if ( !v6 )
      {
        v7 = (__int64 *)std::wstring::operator std::wstring_view((char *)this + 64, &v38);
        v8 = *v7;
        v9 = v7[1];
        FullyQualifiedName = (_QWORD *)Microsoft::Diagnostics::ITriggerInst::GetFullyQualifiedName(a2, &v36);
        if ( (unsigned __int8)std::_Traits_equal<std::char_traits<wchar_t>>(
                                *FullyQualifiedName,
                                FullyQualifiedName[1],
                                v8,
                                v9) )
        {
          LODWORD(v34) = 0;
          v35 = 0;
          v36 = L"InstanceId";
          v37 = 10;
          JsonBuilder::find<>((char *)a2 + 16, &v38, v33, &v36);
          if ( !(_DWORD)v39 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x58,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\usageanalyzer.cpp",
              (const char *)0x80070490LL,
              v33[0]);
          v41 = 0;
          if ( (unsigned __int8)JsonImplementType<unsigned __int64>::ConvertTo(
                                  *(_QWORD *)v38 + 4LL * (unsigned int)v39,
                                  &v41)
            && (v11 = v41, v41 < 0x100000000LL) )
          {
            v12 = 0;
          }
          else
          {
            v11 = 0;
            v12 = 1;
          }
          if ( v12 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x59,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\usageanalyzer.cpp",
              (const char *)0x8007070CLL,
              v33[0]);
          LODWORD(v34) = v11;
          v41 = 0;
          v38 = L"ProcessStartKey";
          v39 = 15;
          v13 = JsonBuilder::find<>((char *)a2 + 16, &v36, v33, &v38);
          v14 = *(unsigned int *)(v13 + 8);
          if ( !(_DWORD)v14 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x5E,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\usageanalyzer.cpp",
              (const char *)0x80070490LL,
              v33[0]);
          if ( !(unsigned __int8)JsonImplementType<unsigned __int64>::ConvertTo(**(_QWORD **)v13 + 4 * v14, &v41) )
            wil::details::in1diag3::Throw_Hr(
              v15,
              (void *)0x5F,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\usageanalyzer.cpp",
              (const char *)0x8007070CLL,
              v33[0]);
          v35 = v41;
          v16 = Microsoft::Diagnostics::UsageAnalyzer::AcquireProcessRecord(this, (const struct ProcessKey *)&v34);
          if ( v16 )
            *((_QWORD *)v16 + 1) = GetTickCount64();
        }
        else
        {
          v17 = (__int64 *)std::wstring::operator std::wstring_view((char *)this + 96, &v38);
          v18 = *v17;
          v19 = v17[1];
          v20 = (_QWORD *)Microsoft::Diagnostics::ITriggerInst::GetFullyQualifiedName(a2, &v36);
          if ( (unsigned __int8)std::_Traits_equal<std::char_traits<wchar_t>>(*v20, v20[1], v18, v19) )
          {
            v41 = 0;
            v38 = L"AppStateChange";
            v39 = 14;
            JsonBuilder::find<>((char *)a2 + 16, &v36, v33, &v38);
            if ( !(_DWORD)v37 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x6C,
                (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\usageanalyzer.cpp",
                (const char *)0x80070490LL,
                v33[0]);
            if ( !(unsigned __int8)JsonImplementType<unsigned __int64>::ConvertTo(
                                     *(_QWORD *)v36 + 4LL * (unsigned int)v37,
                                     &v41) )
              wil::details::in1diag3::Throw_Hr(
                v21,
                (void *)0x6D,
                (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\usageanalyzer.cpp",
                (const char *)0x8007070CLL,
                v33[0]);
            if ( (_DWORD)v41 == 3 )
            {
              v38 = L"InstanceId";
              v39 = 10;
              v22 = JsonBuilder::find<>((char *)a2 + 16, &v36, v33, &v38);
              v23 = *(_OWORD *)v22;
              v24 = *(unsigned int *)(v22 + 8);
              if ( !(_DWORD)v24 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0x75,
                  (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\usageanalyzer.cpp",
                  (const char *)0x80070490LL,
                  v33[0]);
              v41 = 0;
              if ( (unsigned __int8)JsonImplementType<unsigned __int64>::ConvertTo(*(_QWORD *)v23 + 4 * v24, &v41)
                && (v25 = v41, v41 < 0x100000000LL) )
              {
                v26 = 0;
              }
              else
              {
                v25 = 0;
                v26 = 1;
              }
              if ( v26 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0x76,
                  (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\usageanalyzer.cpp",
                  (const char *)0x8007070CLL,
                  v33[0]);
              LODWORD(v36) = v25;
              v41 = 0;
              v38 = L"ProcessStartKey";
              v39 = 15;
              v27 = JsonBuilder::find<>((char *)a2 + 16, &v34, v33, &v38);
              v28 = *(unsigned int *)(v27 + 8);
              if ( !(_DWORD)v28 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0x7B,
                  (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\usageanalyzer.cpp",
                  (const char *)0x80070490LL,
                  v33[0]);
              if ( !(unsigned __int8)JsonImplementType<unsigned __int64>::ConvertTo(**(_QWORD **)v27 + 4 * v28, &v41) )
                wil::details::in1diag3::Throw_Hr(
                  v29,
                  (void *)0x7C,
                  (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\usageanalyzer.cpp",
                  (const char *)0x8007070CLL,
                  v33[0]);
              v30 = v41;
              v37 = v41;
              v43 = (char *)this + 736;
              std::_Mutex_base::lock((Microsoft::Diagnostics::UsageAnalyzer *)((char *)this + 736));
              std::_Hash<std::_Umap_traits<ProcessKey,Microsoft::Diagnostics::UsageAnalyzer::ProcessRecord,std::_Uhash_compare<ProcessKey,Microsoft::Diagnostics::UsageAnalyzer::ProcessKeyHash,std::equal_to<ProcessKey>>,std::allocator<std::pair<ProcessKey const,Microsoft::Diagnostics::UsageAnalyzer::ProcessRecord>>,0>>::find(
                (char *)this + 672,
                &v41,
                &v36);
              if ( v25 != -1 || v30 != -1 )
              {
                v31 = v41;
                if ( v41 != *((_QWORD *)this + 85) )
                {
                  TickCount64 = GetTickCount64();
                  Microsoft::Diagnostics::UsageAnalyzer::ProcessRecord::RecordUpdate(
                    (Microsoft::Diagnostics::UsageAnalyzer::ProcessRecord *)(v31 + 32),
                    *((_QWORD *)this + 24) & 1,
                    TickCount64);
                  *(_QWORD *)(v31 + 40) = 0;
                  if ( *((_DWORD *)this + 266) )
                  {
                    Microsoft::Diagnostics::UsageAnalyzer::AggregatePerProcessRecord((char *)this + 816, v31 + 16);
                    std::_Hash<std::_Umap_traits<ProcessKey,Microsoft::Diagnostics::UsageAnalyzer::ProcessRecord,std::_Uhash_compare<ProcessKey,Microsoft::Diagnostics::UsageAnalyzer::ProcessKeyHash,std::equal_to<ProcessKey>>,std::allocator<std::pair<ProcessKey const,Microsoft::Diagnostics::UsageAnalyzer::ProcessRecord>>,0>>::_Unchecked_erase(
                      (char *)this + 672,
                      v31);
                  }
                }
              }
              _Mtx_unlock((Microsoft::Diagnostics::UsageAnalyzer *)((char *)this + 736));
            }
          }
        }
      }
    }
    _Mtx_unlock(v4);
  }
}

```

## disassembly

```asm
0x18007dc84  mov     [rsp-38h+arg_8], rbx
0x18007dc89  push    rbp
0x18007dc8a  push    rsi
0x18007dc8b  push    rdi
0x18007dc8c  push    r12
0x18007dc8e  push    r13
0x18007dc90  push    r14
0x18007dc92  push    r15
0x18007dc94  mov     rbp, rsp
0x18007dc97  sub     rsp, 60h
0x18007dc9b  mov     r14, rdx
0x18007dc9e  mov     rsi, rcx
0x18007dca1  mov     al, [rcx+240h]
0x18007dca7  nop
0x18007dca8  xor     r12d, r12d
0x18007dcab  test    al, al
0x18007dcad  jz      loc_18007E1EC
0x18007dcb3  lea     r13, [rcx+250h]
0x18007dcba  mov     [rbp+arg_10], r13
0x18007dcbe  mov     rcx, r13; this
0x18007dcc1  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x18007dcc6  nop
0x18007dcc7  mov     rax, [r14]
0x18007dcca  mov     rcx, r14
0x18007dccd  mov     rax, [rax+78h]
0x18007dcd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007dcd6  cmp     [rax+30h], r12b
0x18007dcda  jnz     loc_18007E1DD
0x18007dce0  lea     r15, [r14+10h]
0x18007dce4  lea     rax, aData_0; "data"
0x18007dceb  mov     [rbp+var_30], rax
0x18007dcef  mov     [rbp+var_28], 4
0x18007dcf7  mov     [rbp+var_20], r15
0x18007dcfb  mov     dword ptr [rbp+var_18], r12d
0x18007dcff  lea     r9, [rbp+var_30]
0x18007dd03  lea     r8, [rbp+var_20]
0x18007dd07  lea     rdx, [rbp+var_40]
0x18007dd0b  mov     rcx, r15
0x18007dd0e  call    ??$find@$$V@JsonBuilder@@QEBA?AVJsonConstIterator@@AEBV1@AEBV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; JsonBuilder::find<>(JsonConstIterator const &,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const &)
0x18007dd13  cmp     [rbp+var_38], r12d
0x18007dd17  setz    al
0x18007dd1a  mov     rcx, [rbp+38h]; this
0x18007dd1e  test    al, al
0x18007dd20  jz      short loc_18007DD3A
0x18007dd22  mov     r9d, 80070490h; char *
0x18007dd28  lea     r8, aOnecoreBaseTel_153; "onecore\\base\\telemetry\\utc\\service"...
0x18007dd2f  lea     edx, [r12+4Fh]; void *
0x18007dd34  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007dd3a  mov     rax, [r14]
0x18007dd3d  mov     rcx, r14
0x18007dd40  mov     rax, [rax+50h]
0x18007dd44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007dd49  mov     rcx, [rax]
0x18007dd4c  sub     rcx, qword ptr cs:?k_kernelTLProcessProviderGuid@EventBasedMetadata@Diagnostics@Microsoft@@1U_GUID@@B.Data1; _GUID const Microsoft::Diagnostics::EventBasedMetadata::k_kernelTLProcessProviderGuid ...
0x18007dd53  jnz     short loc_18007DD60
0x18007dd55  mov     rcx, [rax+8]
0x18007dd59  sub     rcx, qword ptr cs:?k_kernelTLProcessProviderGuid@EventBasedMetadata@Diagnostics@Microsoft@@1U_GUID@@B.Data4; _GUID const Microsoft::Diagnostics::EventBasedMetadata::k_kernelTLProcessProviderGuid ...
0x18007dd60  test    rcx, rcx
0x18007dd63  jnz     loc_18007E1DD
0x18007dd69  lea     rcx, [rsi+40h]
0x18007dd6d  lea     rdx, [rbp+var_10]
0x18007dd71  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18007dd76  mov     rdi, [rax]
0x18007dd79  mov     rbx, [rax+8]
0x18007dd7d  lea     rdx, [rbp+var_20]
0x18007dd81  mov     rcx, r14
0x18007dd84  call    ?GetFullyQualifiedName@ITriggerInst@Diagnostics@Microsoft@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; Microsoft::Diagnostics::ITriggerInst::GetFullyQualifiedName(void)
0x18007dd89  mov     r9, rbx
0x18007dd8c  mov     r8, rdi
0x18007dd8f  mov     rdx, [rax+8]
0x18007dd93  mov     rcx, [rax]
0x18007dd96  call    ??$_Traits_equal@U?$char_traits@_W@std@@@std@@YA_NQEB_W_K01@Z; std::_Traits_equal<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x18007dd9b  lea     rdx, [rbp+var_10]
0x18007dd9f  test    al, al
0x18007dda1  jz      loc_18007DF21
0x18007dda7  mov     dword ptr [rbp+var_30], r12d
0x18007ddab  mov     [rbp+var_28], r12
0x18007ddaf  lea     rax, aInstanceid_0; "InstanceId"
0x18007ddb6  mov     [rbp+var_20], rax
0x18007ddba  mov     [rbp+var_18], 0Ah
0x18007ddc2  lea     r9, [rbp+var_20]
0x18007ddc6  lea     r8, [rbp+var_40]
0x18007ddca  mov     rcx, r15
0x18007ddcd  call    ??$find@$$V@JsonBuilder@@QEBA?AVJsonConstIterator@@AEBV1@AEBV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; JsonBuilder::find<>(JsonConstIterator const &,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const &)
0x18007ddd2  mov     edx, dword ptr [rbp+var_8]
0x18007ddd5  test    edx, edx
0x18007ddd7  setz    al
0x18007ddda  mov     rcx, [rbp+38h]; this
0x18007ddde  test    al, al
0x18007dde0  jz      short loc_18007DDFA
0x18007dde2  mov     r9d, 80070490h; char *
0x18007dde8  lea     r8, aOnecoreBaseTel_153; "onecore\\base\\telemetry\\utc\\service"...
0x18007ddef  mov     edx, 58h ; 'X'; void *
0x18007ddf4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007ddfa  mov     [rbp+arg_0], r12
0x18007ddfe  mov     rax, [rbp+var_10]
0x18007de02  mov     rcx, [rax]
0x18007de05  lea     rcx, [rcx+rdx*4]
0x18007de09  lea     rdx, [rbp+arg_0]
0x18007de0d  call    ?ConvertTo@?$JsonImplementType@_K@@SA_NAEBVJsonValue@@AEA_K@Z; JsonImplementType<unsigned __int64>::ConvertTo(JsonValue const &,unsigned __int64 &)
0x18007de12  test    al, al
0x18007de14  jz      short loc_18007DE2E
0x18007de16  mov     rax, 100000000h
0x18007de20  mov     rcx, [rbp+arg_0]
0x18007de24  cmp     rcx, rax
0x18007de27  jnb     short loc_18007DE2E
0x18007de29  mov     dil, r12b
0x18007de2c  jmp     short loc_18007DE34
0x18007de2e  mov     ecx, r12d
0x18007de31  mov     dil, 1
0x18007de34  mov     rax, [rbp+38h]
0x18007de38  test    dil, dil
0x18007de3b  jz      short loc_18007DE58
0x18007de3d  mov     r9d, 8007070Ch; char *
0x18007de43  lea     r8, aOnecoreBaseTel_153; "onecore\\base\\telemetry\\utc\\service"...
0x18007de4a  mov     edx, 59h ; 'Y'; void *
0x18007de4f  mov     rcx, rax; this
0x18007de52  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007de58  mov     dword ptr [rbp+var_30], ecx
0x18007de5b  mov     [rbp+arg_0], r12
0x18007de5f  lea     rax, aProcessstartke; "ProcessStartKey"
0x18007de66  mov     [rbp+var_10], rax
0x18007de6a  mov     [rbp+var_8], 0Fh
0x18007de72  lea     r9, [rbp+var_10]
0x18007de76  lea     r8, [rbp+var_40]
0x18007de7a  lea     rdx, [rbp+var_20]
0x18007de7e  mov     rcx, r15
0x18007de81  call    ??$find@$$V@JsonBuilder@@QEBA?AVJsonConstIterator@@AEBV1@AEBV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; JsonBuilder::find<>(JsonConstIterator const &,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const &)
0x18007de86  movups  xmm1, xmmword ptr [rax]
0x18007de89  mov     edx, [rax+8]
0x18007de8c  test    edx, edx
0x18007de8e  setz    al
0x18007de91  mov     rcx, [rbp+38h]; this
0x18007de95  test    al, al
0x18007de97  jz      short loc_18007DEB1
0x18007de99  mov     r9d, 80070490h; char *
0x18007de9f  lea     r8, aOnecoreBaseTel_153; "onecore\\base\\telemetry\\utc\\service"...
0x18007dea6  mov     edx, 5Eh ; '^'; void *
0x18007deab  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007deb1  mov     r10, [rbp+38h]
0x18007deb5  mov     r8, rdx
0x18007deb8  movq    rax, xmm1
0x18007debd  mov     rdx, [rax]
0x18007dec0  lea     rcx, [rdx+r8*4]
0x18007dec4  lea     rdx, [rbp+arg_0]
0x18007dec8  call    ?ConvertTo@?$JsonImplementType@_K@@SA_NAEBVJsonValue@@AEA_K@Z; JsonImplementType<unsigned __int64>::ConvertTo(JsonValue const &,unsigned __int64 &)
0x18007decd  test    al, al
0x18007decf  jnz     short loc_18007DEEC
0x18007ded1  mov     r9d, 8007070Ch; char *
0x18007ded7  lea     r8, aOnecoreBaseTel_153; "onecore\\base\\telemetry\\utc\\service"...
0x18007dede  mov     edx, 5Fh ; '_'; void *
0x18007dee3  mov     rcx, r10; this
0x18007dee6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007deec  mov     rax, [rbp+arg_0]
0x18007def0  mov     [rbp+var_28], rax
0x18007def4  lea     rdx, [rbp+var_30]; struct ProcessKey *
0x18007def8  mov     rcx, rsi; this
0x18007defb  call    ?AcquireProcessRecord@UsageAnalyzer@Diagnostics@Microsoft@@AEAAPEAUProcessRecord@123@AEBUProcessKey@@@Z; Microsoft::Diagnostics::UsageAnalyzer::AcquireProcessRecord(ProcessKey const &)
0x18007df00  mov     rbx, rax
0x18007df03  test    rax, rax
0x18007df06  jz      loc_18007E1DD
0x18007df0c  call    cs:__imp_GetTickCount64
0x18007df13  nop     dword ptr [rax+rax+00h]
0x18007df18  mov     [rbx+8], rax
0x18007df1c  jmp     loc_18007E1DD
0x18007df21  lea     rcx, [rsi+60h]
0x18007df25  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18007df2a  mov     rdi, [rax]
0x18007df2d  mov     rbx, [rax+8]
0x18007df31  lea     rdx, [rbp+var_20]
0x18007df35  mov     rcx, r14
0x18007df38  call    ?GetFullyQualifiedName@ITriggerInst@Diagnostics@Microsoft@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; Microsoft::Diagnostics::ITriggerInst::GetFullyQualifiedName(void)
0x18007df3d  mov     r9, rbx
0x18007df40  mov     r8, rdi
0x18007df43  mov     rdx, [rax+8]
0x18007df47  mov     rcx, [rax]
0x18007df4a  call    ??$_Traits_equal@U?$char_traits@_W@std@@@std@@YA_NQEB_W_K01@Z; std::_Traits_equal<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x18007df4f  test    al, al
0x18007df51  jz      loc_18007E1DD
0x18007df57  mov     [rbp+arg_0], r12
0x18007df5b  lea     rax, aAppstatechange; "AppStateChange"
0x18007df62  mov     [rbp+var_10], rax
0x18007df66  mov     [rbp+var_8], 0Eh
0x18007df6e  lea     r9, [rbp+var_10]
0x18007df72  lea     r8, [rbp+var_40]
0x18007df76  lea     rdx, [rbp+var_20]
0x18007df7a  mov     rcx, r15
0x18007df7d  call    ??$find@$$V@JsonBuilder@@QEBA?AVJsonConstIterator@@AEBV1@AEBV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; JsonBuilder::find<>(JsonConstIterator const &,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const &)
0x18007df82  mov     edx, dword ptr [rbp+var_18]
0x18007df85  test    edx, edx
0x18007df87  setz    al
0x18007df8a  mov     rcx, [rbp+38h]; this
0x18007df8e  test    al, al
0x18007df90  jz      short loc_18007DFAA
0x18007df92  mov     r9d, 80070490h; char *
0x18007df98  lea     r8, aOnecoreBaseTel_153; "onecore\\base\\telemetry\\utc\\service"...
0x18007df9f  mov     edx, 6Ch ; 'l'; void *
0x18007dfa4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007dfaa  mov     r10, [rbp+38h]
0x18007dfae  mov     r8, rdx
0x18007dfb1  mov     rax, [rbp+var_20]
0x18007dfb5  mov     rdx, [rax]
0x18007dfb8  lea     rcx, [rdx+r8*4]
0x18007dfbc  lea     rdx, [rbp+arg_0]
0x18007dfc0  call    ?ConvertTo@?$JsonImplementType@_K@@SA_NAEBVJsonValue@@AEA_K@Z; JsonImplementType<unsigned __int64>::ConvertTo(JsonValue const &,unsigned __int64 &)
0x18007dfc5  test    al, al
0x18007dfc7  jnz     short loc_18007DFE4
0x18007dfc9  mov     r9d, 8007070Ch; char *
0x18007dfcf  lea     r8, aOnecoreBaseTel_153; "onecore\\base\\telemetry\\utc\\service"...
0x18007dfd6  mov     edx, 6Dh ; 'm'; void *
0x18007dfdb  mov     rcx, r10; this
0x18007dfde  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007dfe4  cmp     dword ptr [rbp+arg_0], 3
0x18007dfe8  jnz     loc_18007E1DD
0x18007dfee  lea     rax, aInstanceid_0; "InstanceId"
0x18007dff5  mov     [rbp+var_10], rax
0x18007dff9  mov     [rbp+var_8], 0Ah
0x18007e001  lea     r9, [rbp+var_10]
0x18007e005  lea     r8, [rbp+var_40]
0x18007e009  lea     rdx, [rbp+var_20]
0x18007e00d  mov     rcx, r15
0x18007e010  call    ??$find@$$V@JsonBuilder@@QEBA?AVJsonConstIterator@@AEBV1@AEBV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; JsonBuilder::find<>(JsonConstIterator const &,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const &)
0x18007e015  movups  xmm1, xmmword ptr [rax]
0x18007e018  mov     edx, [rax+8]
0x18007e01b  test    edx, edx
0x18007e01d  setz    al
0x18007e020  mov     rcx, [rbp+38h]; this
0x18007e024  test    al, al
0x18007e026  jz      short loc_18007E040
0x18007e028  mov     r9d, 80070490h; char *
0x18007e02e  lea     r8, aOnecoreBaseTel_153; "onecore\\base\\telemetry\\utc\\service"...
0x18007e035  mov     edx, 75h ; 'u'; void *
0x18007e03a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007e040  mov     [rbp+arg_0], r12
0x18007e044  movq    rax, xmm1
0x18007e049  mov     rcx, [rax]
0x18007e04c  lea     rcx, [rcx+rdx*4]
0x18007e050  lea     rdx, [rbp+arg_0]
0x18007e054  call    ?ConvertTo@?$JsonImplementType@_K@@SA_NAEBVJsonValue@@AEA_K@Z; JsonImplementType<unsigned __int64>::ConvertTo(JsonValue const &,unsigned __int64 &)
0x18007e059  mov     dil, 1
0x18007e05c  test    al, al
0x18007e05e  jz      short loc_18007E078
0x18007e060  mov     rax, 100000000h
0x18007e06a  mov     rbx, [rbp+arg_0]
0x18007e06e  cmp     rbx, rax
0x18007e071  jnb     short loc_18007E078
0x18007e073  mov     al, r12b
0x18007e076  jmp     short loc_18007E07E
0x18007e078  mov     ebx, r12d
0x18007e07b  mov     al, dil
0x18007e07e  mov     rcx, [rbp+38h]; this
0x18007e082  test    al, al
0x18007e084  jz      short loc_18007E09E
0x18007e086  mov     r9d, 8007070Ch; char *
0x18007e08c  lea     r8, aOnecoreBaseTel_153; "onecore\\base\\telemetry\\utc\\service"...
0x18007e093  mov     edx, 76h ; 'v'; void *
0x18007e098  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007e09e  mov     dword ptr [rbp+var_20], ebx
0x18007e0a1  mov     [rbp+arg_0], r12
0x18007e0a5  lea     rax, aProcessstartke; "ProcessStartKey"
0x18007e0ac  mov     [rbp+var_10], rax
0x18007e0b0  mov     [rbp+var_8], 0Fh
0x18007e0b8  lea     r9, [rbp+var_10]
0x18007e0bc  lea     r8, [rbp+var_40]
0x18007e0c0  lea     rdx, [rbp+var_30]
0x18007e0c4  mov     rcx, r15
0x18007e0c7  call    ??$find@$$V@JsonBuilder@@QEBA?AVJsonConstIterator@@AEBV1@AEBV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; JsonBuilder::find<>(JsonConstIterator const &,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const &)
0x18007e0cc  movups  xmm1, xmmword ptr [rax]
0x18007e0cf  mov     edx, [rax+8]
0x18007e0d2  test    edx, edx
0x18007e0d4  setz    al
0x18007e0d7  mov     rcx, [rbp+38h]; this
0x18007e0db  test    al, al
0x18007e0dd  jz      short loc_18007E0F7
0x18007e0df  mov     r9d, 80070490h; char *
0x18007e0e5  lea     r8, aOnecoreBaseTel_153; "onecore\\base\\telemetry\\utc\\service"...
0x18007e0ec  mov     edx, 7Bh ; '{'; void *
0x18007e0f1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007e0f7  mov     r10, [rbp+38h]
0x18007e0fb  mov     r8, rdx
0x18007e0fe  movq    rax, xmm1
0x18007e103  mov     rdx, [rax]
0x18007e106  lea     rcx, [rdx+r8*4]
0x18007e10a  lea     rdx, [rbp+arg_0]
0x18007e10e  call    ?ConvertTo@?$JsonImplementType@_K@@SA_NAEBVJsonValue@@AEA_K@Z; JsonImplementType<unsigned __int64>::ConvertTo(JsonValue const &,unsigned __int64 &)
0x18007e113  test    al, al
0x18007e115  jnz     short loc_18007E132
0x18007e117  mov     r9d, 8007070Ch; char *
0x18007e11d  lea     r8, aOnecoreBaseTel_153; "onecore\\base\\telemetry\\utc\\service"...
0x18007e124  mov     edx, 7Ch ; '|'; void *
0x18007e129  mov     rcx, r10; this
0x18007e12c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007e132  mov     r15, [rbp+arg_0]
0x18007e136  mov     [rbp+var_18], r15
0x18007e13a  lea     r14, [rsi+2E0h]
0x18007e141  mov     [rbp+arg_18], r14
0x18007e145  mov     rcx, r14; this
0x18007e148  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x18007e14d  nop
0x18007e14e  lea     r12, [rsi+2A0h]
  ... truncated ...
```
