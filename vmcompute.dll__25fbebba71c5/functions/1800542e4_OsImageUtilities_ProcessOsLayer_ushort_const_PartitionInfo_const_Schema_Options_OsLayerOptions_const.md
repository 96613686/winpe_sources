# OsImageUtilities::ProcessOsLayer(ushort const *,PartitionInfo const &,Schema::Options::OsLayerOptions const &)

- ea: `0x1800542e4`
- end: `0x1800548be`
- name: `?ProcessOsLayer@OsImageUtilities@@YAXPEBGAEBUPartitionInfo@@AEBUOsLayerOptions@Options@Schema@@@Z`
- size: `1498`
- prototype: `void __fastcall(PCWSTR pszPathIn, PCWSTR, const struct PartitionInfo *, const struct Schema::Options::OsLayerOptions *)`
- caller_count: `1`
- callee_count: `25`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800369c0`

## callees

- `0x180002f50`
- `0x180003c78`
- `0x180006158`
- `0x180006660`
- `0x18000d0ec`
- `0x18000d108`
- `0x18001d3b8`
- `0x180022cd4`
- `0x18002e454`
- `0x18002eb7c`
- `0x18002f94c`
- `0x180051ea0`
- `0x180052040`
- `0x180052630`
- `0x180053040`
- `0x180053208`
- `0x18005340c`
- `0x180053778`
- `0x1800539c8`
- `0x180053bec`
- `0x1800541c8`
- `0x1800542e4`
- `0x180054b38`
- `0x180054fe8`
- `0x1800552a8`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800545cd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800545cd`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800545a5`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800545a5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180054540`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180054540`

## string_xrefs

- `0x1800543f3`: `ComputeStorage_ProcessOsLayer`
- `0x180054852`: `onecore\vm\compute\dll\lib\storage\osimageutilities.cpp`
- `0x180054888`: `onecore\vm\compute\dll\lib\storage\osimageutilities.cpp`
- `0x18005489a`: `onecore\vm\compute\dll\lib\storage\osimageutilities.cpp`
- `0x1800548ac`: `onecore\vm\compute\dll\lib\storage\osimageutilities.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
void __fastcall OsImageUtilities::ProcessOsLayer(
        PCWSTR pszPathIn,
        const WCHAR *a2,
        const struct PartitionInfo *a3,
        const struct Schema::Options::OsLayerOptions *a4)
{
  __m256i *v7; // rax
  const unsigned __int16 *v8; // rdx
  OsImageUtilities::Helpers *v9; // rax
  const unsigned __int16 *v10; // rdx
  __int64 v11; // rax
  char *FileW; // rbx
  const char *v13; // r9
  LPCVOID *v14; // rdx
  const char *v15; // r9
  OsImageUtilities::Helpers *v16; // rcx
  const unsigned __int16 *v17; // rdx
  BOOL v18; // r15d
  wchar_t **v19; // rcx
  _OWORD *v20; // xmm1_8
  __int128 *v21; // r14
  __int128 *i; // rbx
  __int128 v23; // xmm1
  _QWORD *v24; // rax
  __int64 v25; // rdx
  const WCHAR *v26; // rdx
  PCWSTR *v27; // rdx
  _QWORD *v28; // rcx
  const unsigned __int16 *v29; // rdx
  const WCHAR *v30; // rcx
  const struct PartitionInfo *v31; // r8
  const WCHAR *v32; // rcx
  unsigned int v33; // eax
  unsigned int v34; // eax
  int v35; // edx
  int dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  const char *dwFlagsAndAttributes; // [rsp+28h] [rbp-D8h]
  __m256i v38; // [rsp+40h] [rbp-C0h] BYREF
  char *v39; // [rsp+60h] [rbp-A0h]
  __int128 v40; // [rsp+68h] [rbp-98h] BYREF
  __int128 v41; // [rsp+78h] [rbp-88h] BYREF
  __int64 v42; // [rsp+88h] [rbp-78h]
  __int128 v43; // [rsp+90h] [rbp-70h]
  DWORD NumberOfBytesWritten[2]; // [rsp+A0h] [rbp-60h] BYREF
  PCWSTR pszPathIna[3]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int64 v46; // [rsp+C8h] [rbp-38h]
  __int128 Src; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v48; // [rsp+E0h] [rbp-20h]
  __int128 v49; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v50; // [rsp+100h] [rbp+0h]
  _QWORD v51[4]; // [rsp+110h] [rbp+10h] BYREF
  void **v52; // [rsp+130h] [rbp+30h] BYREF
  int v53; // [rsp+138h] [rbp+38h] BYREF
  char v54; // [rsp+13Ch] [rbp+3Ch]
  int v55; // [rsp+160h] [rbp+60h] BYREF
  const char *v56; // [rsp+168h] [rbp+68h]
  __int64 v57; // [rsp+170h] [rbp+70h]
  char v58; // [rsp+178h] [rbp+78h]
  int v59; // [rsp+180h] [rbp+80h]
  _BYTE v60[152]; // [rsp+188h] [rbp+88h] BYREF
  __int128 v61; // [rsp+220h] [rbp+120h]
  int v62; // [rsp+230h] [rbp+130h]
  __int64 v63; // [rsp+238h] [rbp+138h]
  int *v64; // [rsp+240h] [rbp+140h]
  __int64 v65; // [rsp+248h] [rbp+148h]
  __int64 v66; // [rsp+250h] [rbp+150h]
  void ***v67; // [rsp+258h] [rbp+158h]
  __int64 v68; // [rsp+260h] [rbp+160h]
  int v69; // [rsp+268h] [rbp+168h]
  int *v70; // [rsp+270h] [rbp+170h]
  char v71; // [rsp+278h] [rbp+178h]
  wil::details::in1diag3 *retaddr; // [rsp+2C8h] [rbp+1C8h]

  memset_0(&v52, 0, 0x150u);
  NumberOfBytesWritten[0] = 0;
  *(_OWORD *)v38.m256i_i8 = 0;
  *(__m128i *)&v38.m256i_u64[2] = _mm_load_si128((const __m128i *)&_xmm);
  v38.m256i_i16[0] = 0;
  LODWORD(v39) = 1;
  *(_QWORD *)&Src = &v38;
  BYTE8(Src) = 0;
  v51[0] = Marshal::Details::ObjectTypeInfo<Marshal::TypeList<enum Schema::Options::OsLayerType,bool,bool,bool,bool,Marshal::ModifiedType<std::vector<Schema::Common::Resources::Layer>,Marshal::ModifierList<>>,_GUID>,Marshal::Details::JsonTypeData,Marshal::Details::JsonTypeInfo>::Value;
  v51[1] = Marshal::Details::ObjectTypeInfo<Marshal::TypeList<_GUID,std::wstring,enum Schema::Common::Resources::PathType,enum Schema::Common::Resources::CacheMode>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value;
  pszPathIna[0] = (PCWSTR)Marshal::Details::ObjectTypeInfo<Marshal::TypeList<enum Schema::Options::OsLayerType,bool,bool,bool,bool,Marshal::ModifiedType<std::vector<Schema::Common::Resources::Layer>,Marshal::ModifierList<>>,_GUID>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value;
  pszPathIna[1] = (PCWSTR)Marshal::Details::ObjectTypeInfo<Marshal::TypeList<_GUID,std::wstring,enum Schema::Common::Resources::PathType,enum Schema::Common::Resources::CacheMode>,Marshal::Details::JsonTypeData,Marshal::Details::JsonTypeInfo>::Value;
  *(_QWORD *)&v49 = Schema::Options::OsLayerOptions_ClassData;
  *((_QWORD *)&v49 + 1) = Schema::Options::OsLayerOptions_ClassData + 224LL;
  Marshal::Details::ObjectToJson(
    (unsigned int)&Src,
    (_DWORD)a3,
    (unsigned int)NumberOfBytesWritten,
    (unsigned int)&v49,
    (__int64)pszPathIna,
    (__int64)v51);
  v7 = &v38;
  if ( v38.m256i_i64[3] > 7uLL )
    v7 = (__m256i *)v38.m256i_i64[0];
  *(_QWORD *)NumberOfBytesWritten = v7;
  v53 = 0;
  v54 = 0;
  v58 = 0;
  v55 = 0;
  v56 = "ComputeStorage_ProcessOsLayer";
  v57 = 0;
  v59 = 0;
  v61 = 0;
  memset_0(v60, 0, sizeof(v60));
  v62 = 1;
  v63 = 0;
  v64 = &v53;
  v65 = 0;
  v66 = 0;
  v67 = &v52;
  v68 = 0;
  v69 = 0;
  v70 = &v55;
  v71 = 0;
  v52 = &ComputeLib::Diagnostics::TraceProvider::ComputeStorage_ProcessOsLayer::`vftable';
  ComputeLib::Diagnostics::TraceProvider::ComputeStorage_ProcessOsLayer::StartActivity<unsigned short const *>(
    (__int64)&v52,
    (__int64 *)NumberOfBytesWritten);
  std::wstring::~wstring(&v38);
  v8 = (const unsigned __int16 *)*(unsigned int *)a3;
  if ( (unsigned int)v8 > 1 )
  {
    v34 = wil::verify_hresult<long>(2147942487LL);
    LODWORD(dwFlagsAndAttributes) = v35;
    wil::details::in1diag3::Throw_HrMsg(
      retaddr,
      (void *)0x1D4,
      (unsigned int)"onecore\\vm\\compute\\dll\\lib\\storage\\osimageutilities.cpp",
      (const char *)v34,
      (int)"Invalid LayerType: %x",
      dwFlagsAndAttributes);
  }
  if ( !*((_BYTE *)a3 + 4) )
  {
    v9 = (OsImageUtilities::Helpers *)Vml::CombineFilePath(&Src, pszPathIn, L"Files");
    if ( *((_QWORD *)v9 + 3) > 7u )
      v9 = *(OsImageUtilities::Helpers **)v9;
    OsImageUtilities::Helpers::OptimizeCiCache(v9, v10);
    std::wstring::~wstring(&Src);
  }
  if ( !*(_DWORD *)a3 )
    goto LABEL_11;
  if ( *(_DWORD *)a3 != 1 )
    goto LABEL_53;
  if ( *((_BYTE *)a3 + 6) )
  {
LABEL_11:
    OsImageUtilities::Helpers::CreateBaseHives(pszPathIn, v8);
    v11 = Vml::CombineFilePath(&Src, pszPathIn, L"layout");
    if ( *(_QWORD *)(v11 + 24) > 7u )
      v11 = *(_QWORD *)v11;
    FileW = (char *)CreateFileW((LPCWSTR)v11, 0x40000000u, 0, 0, 1u, 0, 0);
    v39 = FileW;
    std::wstring::~wstring(&Src);
    if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x1EB,
        (unsigned int)"onecore\\vm\\compute\\dll\\lib\\storage\\osimageutilities.cpp",
        v13);
    NumberOfBytesWritten[0] = 0;
    v14 = &lpBuffer;
    if ( (unsigned __int64)qword_1800BDD80 > 0xF )
      v14 = (LPCVOID *)lpBuffer;
    if ( !WriteFile(FileW, v14, nNumberOfBytesToWrite, NumberOfBytesWritten, 0) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x1EE,
        (unsigned int)"onecore\\vm\\compute\\dll\\lib\\storage\\osimageutilities.cpp",
        v15);
    if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(FileW);
  }
  if ( *(_DWORD *)a3 == 1 )
  {
    Vml::CombineFilePath(pszPathIna, pszPathIn, L"Files");
    if ( !OsImageUtilities::Helpers::IsHostPreReleaseImageCapable(v16)
      && OsImageUtilities::Helpers::IsPreReleaseImage(pszPathIn, v17) )
    {
      v33 = wil::verify_hresult<long>(2151088403LL);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1F9,
        (unsigned int)"onecore\\vm\\compute\\dll\\lib\\storage\\osimageutilities.cpp",
        (const char *)v33,
        dwCreationDisposition);
    }
    v18 = !OsImageUtilities::Helpers::UseLegacyFilter(pszPathIn, v17);
    v40 = 0;
    v41 = 0;
    v42 = 0;
    v43 = 0;
    v38.m256i_i64[2] = 0;
    *(_OWORD *)v38.m256i_i8 = UTILITY_VM_LAYER_ID;
    if ( !*((_BYTE *)a3 + 7) )
    {
      if ( *((_BYTE *)a3 + 6) )
      {
        v38.m256i_i32[4] = 4;
        v19 = &off_18008AE00;
        *(_QWORD *)&v40 = 2;
      }
      else
      {
        v19 = &off_18008AD50;
        *(_QWORD *)&v40 = 11;
      }
      *((_QWORD *)&v40 + 1) = v19;
    }
    v38.m256i_i64[3] = (__int64)pszPathIn;
    v20 = (_OWORD *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
    if ( v20 )
    {
      *v20 = UTILITY_VM_LAYER_ID;
      v20[1] = *(_OWORD *)&v38.m256i_u64[2];
      *((_QWORD *)&v41 + 1) += 32LL;
    }
    else
    {
      std::vector<_WC_LAYER_DESCRIPTOR>::_Emplace_reallocate<_WC_LAYER_DESCRIPTOR>(&v41, 0, &v38);
    }
    v21 = (__int128 *)*((_QWORD *)a3 + 2);
    for ( i = (__int128 *)*((_QWORD *)a3 + 1); i != v21; i = (__int128 *)((char *)i + 56) )
    {
      *(_OWORD *)&v38.m256i_u64[1] = 0;
      v23 = *i;
      *(_OWORD *)v38.m256i_i8 = *i;
      v24 = i + 1;
      if ( *((_QWORD *)i + 5) > 7u )
        v24 = (_QWORD *)*v24;
      v38.m256i_i64[3] = (__int64)v24;
      v25 = *((_QWORD *)&v41 + 1);
      if ( *((_QWORD *)&v41 + 1) == v42 )
      {
        std::vector<_WC_LAYER_DESCRIPTOR>::_Emplace_reallocate<_WC_LAYER_DESCRIPTOR>(&v41, *((_BYTE **)&v41 + 1), &v38);
      }
      else
      {
        **((_OWORD **)&v41 + 1) = v23;
        *(_OWORD *)(v25 + 16) = *(_OWORD *)&v38.m256i_u64[2];
        *((_QWORD *)&v41 + 1) += 32LL;
      }
    }
    v43 = *((_OWORD *)a3 + 2);
    v49 = 0;
    v50 = 0;
    Vml::TemporaryPrivilege::TemporaryPrivilege((Vml::TemporaryPrivilege *)&v49, 17);
    Src = 0;
    v48 = 0;
    Vml::TemporaryPrivilege::TemporaryPrivilege((Vml::TemporaryPrivilege *)&Src, 18);
    if ( *((_QWORD *)a2 + 3) <= 7u )
      v26 = a2;
    else
      v26 = *(const WCHAR **)a2;
    Vml::CombineFilePath(v51, v26, L"\\");
    v27 = pszPathIna;
    if ( v46 > 7 )
      v27 = (PCWSTR *)pszPathIna[0];
    v28 = v51;
    if ( v51[3] > 7u )
      v28 = (_QWORD *)v51[0];
    OsImageUtilities::Helpers::InitializeAndPopulateSandbox(v28, v27, &v40, v18);
    if ( *((_QWORD *)a2 + 3) <= 7u )
      v30 = a2;
    else
      v30 = *(const WCHAR **)a2;
    OsImageUtilities::Helpers::CreateSandboxStateDirectory(v30, v29);
    if ( !*((_BYTE *)a3 + 5) )
    {
      v32 = (const WCHAR *)pszPathIna;
      if ( v46 > 7 )
        v32 = pszPathIna[0];
      OsImageUtilities::Helpers::UpdateBcdStore(v32, a2, v31);
    }
    std::wstring::~wstring(v51);
    Vml::TemporaryPrivilege::~TemporaryPrivilege((Vml::TemporaryPrivilege *)&Src);
    Vml::TemporaryPrivilege::~TemporaryPrivilege((Vml::TemporaryPrivilege *)&v49);
    std::vector<_WC_LAYER_DESCRIPTOR>::~vector<_WC_LAYER_DESCRIPTOR>(&v41);
    std::wstring::~wstring(pszPathIna);
  }
LABEL_53:
  wil::ActivityBase<ComputeLib::Diagnostics::TraceProvider,1,64,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(&v52);
  ComputeLib::Diagnostics::TraceProvider::ComputeStorage_ProcessOsLayer::~ComputeStorage_ProcessOsLayer((ComputeLib::Diagnostics::TraceProvider::ComputeStorage_ProcessOsLayer *)&v52);
}

```

## disassembly

```asm
0x1800542e4  push    rbp
0x1800542e6  push    rbx
0x1800542e7  push    rsi
0x1800542e8  push    rdi
0x1800542e9  push    r12
0x1800542eb  push    r14
0x1800542ed  push    r15
0x1800542ef  lea     rbp, [rsp-190h]
0x1800542f7  sub     rsp, 290h
0x1800542fe  mov     rax, cs:__security_cookie
0x180054305  xor     rax, rsp
0x180054308  mov     [rbp+1C0h+var_40], rax
0x18005430f  mov     rdi, r8
0x180054312  mov     rsi, rdx
0x180054315  mov     r14, rcx
0x180054318  xor     r12d, r12d
0x18005431b  mov     dword ptr [rsp+2C0h+var_260], r12d
0x180054320  xor     edx, edx; Val
0x180054322  mov     r8d, 150h; Size
0x180054328  lea     rcx, [rbp+1C0h+var_190]; void *
0x18005432c  call    memset_0
0x180054331  nop
0x180054332  mov     [rbp+1C0h+NumberOfBytesWritten], r12d
0x180054336  xorps   xmm0, xmm0
0x180054339  movups  [rsp+2C0h+var_280], xmm0
0x18005433e  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180054346  movdqu  [rsp+2C0h+var_270], xmm1
0x18005434c  mov     word ptr [rsp+2C0h+var_280], r12w
0x180054352  mov     dword ptr [rsp+2C0h+var_260], 1
0x18005435a  lea     rax, [rsp+2C0h+var_280]
0x18005435f  mov     qword ptr [rbp+1C0h+Src], rax
0x180054363  mov     byte ptr [rbp+1C0h+Src+8], r12b
0x180054367  mov     rax, cs:?OsLayerOptions_ClassData@Options@Schema@@3UClassData@Marshal@@B; Marshal::ClassData const Schema::Options::OsLayerOptions_ClassData
0x18005436e  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@W4OsLayerType@Options@Schema@@_N_N_N_NU?$ModifiedType@V?$vector@ULayer@Resources@Common@Schema@@V?$allocator@ULayer@Resources@Common@Schema@@@std@@@std@@U?$ModifierList@$$V@Marshal@@@Marshal@@U_GUID@@@Marshal@@UJsonTypeData@Details@2@UJsonTypeInfo@42@@Details@Marshal@@2V?$array@PEBUJsonTypeData@Details@Marshal@@$06@std@@A; std::array<Marshal::Details::JsonTypeData const *,7> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<Schema::Options::OsLayerType,bool,bool,bool,bool,Marshal::ModifiedType<std::vector<Schema::Common::Resources::Layer>,Marshal::ModifierList<>>,_GUID>,Marshal::Details::JsonTypeData,Marshal::Details::JsonTypeInfo>::Value
0x180054375  mov     [rbp+1C0h+var_1B0], rcx
0x180054379  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@U_GUID@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4PathType@Resources@Common@Schema@@W4CacheMode@567@@Marshal@@UBaseTypeData@Details@2@UBaseTypeInfo@42@@Details@Marshal@@2V?$array@PEBUBaseTypeData@Details@Marshal@@$03@std@@A; std::array<Marshal::Details::BaseTypeData const *,4> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<_GUID,std::wstring,Schema::Common::Resources::PathType,Schema::Common::Resources::CacheMode>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value
0x180054380  mov     [rbp+1C0h+var_1A8], rcx
0x180054384  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@W4OsLayerType@Options@Schema@@_N_N_N_NU?$ModifiedType@V?$vector@ULayer@Resources@Common@Schema@@V?$allocator@ULayer@Resources@Common@Schema@@@std@@@std@@U?$ModifierList@$$V@Marshal@@@Marshal@@U_GUID@@@Marshal@@UBaseTypeData@Details@2@UBaseTypeInfo@42@@Details@Marshal@@2V?$array@PEBUBaseTypeData@Details@Marshal@@$06@std@@A; std::array<Marshal::Details::BaseTypeData const *,7> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<Schema::Options::OsLayerType,bool,bool,bool,bool,Marshal::ModifiedType<std::vector<Schema::Common::Resources::Layer>,Marshal::ModifierList<>>,_GUID>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value
0x18005438b  mov     [rbp+1C0h+pszPathIn], rcx
0x18005438f  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@U_GUID@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4PathType@Resources@Common@Schema@@W4CacheMode@567@@Marshal@@UJsonTypeData@Details@2@UJsonTypeInfo@42@@Details@Marshal@@2V?$array@PEBUJsonTypeData@Details@Marshal@@$03@std@@A; std::array<Marshal::Details::JsonTypeData const *,4> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<_GUID,std::wstring,Schema::Common::Resources::PathType,Schema::Common::Resources::CacheMode>,Marshal::Details::JsonTypeData,Marshal::Details::JsonTypeInfo>::Value
0x180054396  mov     [rbp+1C0h+var_208], rcx
0x18005439a  mov     qword ptr [rbp+1C0h+var_1D0], rax
0x18005439e  add     rax, 0E0h
0x1800543a4  mov     qword ptr [rbp+1C0h+var_1D0+8], rax
0x1800543a8  lea     rax, [rbp+1C0h+var_1B0]
0x1800543ac  mov     qword ptr [rsp+2C0h+dwFlagsAndAttributes], rax
0x1800543b1  lea     rax, [rbp+1C0h+pszPathIn]
0x1800543b5  mov     qword ptr [rsp+2C0h+dwCreationDisposition], rax
0x1800543ba  lea     r9, [rbp+1C0h+var_1D0]
0x1800543be  lea     r8, [rbp+1C0h+NumberOfBytesWritten]
0x1800543c2  mov     rdx, rdi
0x1800543c5  lea     rcx, [rbp+1C0h+Src]
0x1800543c9  call    ?ObjectToJson@Details@Marshal@@YA_NAEAVJsonWriter@2@PEBXAEBVMarshalContext@2@V?$ArrayView@UFieldData@Marshal@@@12@V?$ArrayView@PEBUBaseTypeData@Details@Marshal@@@12@V?$ArrayView@PEBUJsonTypeData@Details@Marshal@@@12@@Z; Marshal::Details::ObjectToJson(Marshal::JsonWriter &,void const *,Marshal::MarshalContext const &,Marshal::Details::ArrayView<Marshal::FieldData>,Marshal::Details::ArrayView<Marshal::Details::BaseTypeData const *>,Marshal::Details::ArrayView<Marshal::Details::JsonTypeData const *>)
0x1800543ce  lea     rax, [rsp+2C0h+var_280]
0x1800543d3  cmp     qword ptr [rsp+2C0h+var_270+8], 7
0x1800543d9  cmova   rax, qword ptr [rsp+2C0h+var_280]
0x1800543df  mov     qword ptr [rbp+1C0h+NumberOfBytesWritten], rax
0x1800543e3  mov     [rbp+1C0h+var_188], r12d
0x1800543e7  mov     [rbp+1C0h+var_184], r12b
0x1800543eb  mov     [rbp+1C0h+var_148], r12b
0x1800543ef  mov     [rbp+1C0h+var_160], r12d
0x1800543f3  lea     rax, aComputestorage; "ComputeStorage_ProcessOsLayer"
0x1800543fa  mov     [rbp+1C0h+var_158], rax
0x1800543fe  mov     [rbp+1C0h+var_150], r12
0x180054402  mov     [rbp+1C0h+var_140], r12d
0x180054409  xorps   xmm0, xmm0
0x18005440c  movdqa  [rbp+1C0h+var_A0], xmm0
0x180054414  xor     edx, edx; Val
0x180054416  mov     r8d, 98h; Size
0x18005441c  lea     rcx, [rbp+1C0h+var_138]; void *
0x180054423  call    memset_0
0x180054428  mov     [rbp+1C0h+var_90], 1
0x180054432  xor     eax, eax
0x180054434  mov     [rbp+1C0h+var_88], rax
0x18005443b  lea     rax, [rbp+1C0h+var_188]
0x18005443f  mov     [rbp+1C0h+var_80], rax
0x180054446  mov     [rbp+1C0h+var_78], r12
0x18005444d  mov     [rbp+1C0h+var_70], r12
0x180054454  lea     rax, [rbp+1C0h+var_190]
0x180054458  mov     [rbp+1C0h+var_68], rax
0x18005445f  mov     [rbp+1C0h+var_60], r12
0x180054466  mov     [rbp+1C0h+var_58], r12d
0x18005446d  lea     rax, [rbp+1C0h+var_160]
0x180054471  mov     [rbp+1C0h+var_50], rax
0x180054478  mov     [rbp+1C0h+var_48], r12b
0x18005447f  lea     rax, ??_7ComputeStorage_ProcessOsLayer@TraceProvider@Diagnostics@ComputeLib@@6B@; const ComputeLib::Diagnostics::TraceProvider::ComputeStorage_ProcessOsLayer::`vftable'
0x180054486  mov     [rbp+1C0h+var_190], rax
0x18005448a  lea     rdx, [rbp+1C0h+NumberOfBytesWritten]
0x18005448e  lea     rcx, [rbp+1C0h+var_190]
0x180054492  call    ??$StartActivity@PEBG@ComputeStorage_ProcessOsLayer@TraceProvider@Diagnostics@ComputeLib@@QEAAX$$QEAPEBG@Z; ComputeLib::Diagnostics::TraceProvider::ComputeStorage_ProcessOsLayer::StartActivity<ushort const *>(ushort const * &&)
0x180054497  nop
0x180054498  lea     rcx, [rsp+2C0h+var_280]
0x18005449d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800544a2  mov     edx, [rdi]
0x1800544a4  cmp     edx, 1
0x1800544a7  ja      loc_180054864
0x1800544ad  cmp     [rdi+4], r12b
0x1800544b1  jnz     short loc_1800544E3
0x1800544b3  lea     r8, aFiles; "Files"
0x1800544ba  mov     rdx, r14; pszPathIn
0x1800544bd  lea     rcx, [rbp+1C0h+Src]; Src
0x1800544c1  call    ?CombineFilePath@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG0@Z; Vml::CombineFilePath(ushort const *,ushort const *)
0x1800544c6  nop
0x1800544c7  cmp     qword ptr [rax+18h], 7
0x1800544cc  jbe     short loc_1800544D1
0x1800544ce  mov     rax, [rax]
0x1800544d1  mov     rcx, rax; this
0x1800544d4  call    ?OptimizeCiCache@Helpers@OsImageUtilities@@YAXPEBG@Z; OsImageUtilities::Helpers::OptimizeCiCache(ushort const *)
0x1800544d9  nop
0x1800544da  lea     rcx, [rbp+1C0h+Src]
0x1800544de  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800544e3  cmp     [rdi], r12d
0x1800544e6  jz      short loc_1800544FB
0x1800544e8  cmp     dword ptr [rdi], 1
0x1800544eb  jnz     loc_180054809
0x1800544f1  cmp     [rdi+6], r12b
0x1800544f5  jz      loc_1800545D9
0x1800544fb  mov     rcx, r14; pszPathIn
0x1800544fe  call    ?CreateBaseHives@Helpers@OsImageUtilities@@YAXPEBG@Z; OsImageUtilities::Helpers::CreateBaseHives(ushort const *)
0x180054503  lea     r8, aLayout; "layout"
0x18005450a  mov     rdx, r14; pszPathIn
0x18005450d  lea     rcx, [rbp+1C0h+Src]; Src
0x180054511  call    ?CombineFilePath@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG0@Z; Vml::CombineFilePath(ushort const *,ushort const *)
0x180054516  cmp     qword ptr [rax+18h], 7
0x18005451b  jbe     short loc_180054520
0x18005451d  mov     rax, [rax]
0x180054520  mov     [rsp+2C0h+hTemplateFile], r12; hTemplateFile
0x180054525  mov     [rsp+2C0h+dwFlagsAndAttributes], r12d; dwFlagsAndAttributes
0x18005452a  mov     [rsp+2C0h+dwCreationDisposition], 1; dwCreationDisposition
0x180054532  xor     r9d, r9d; lpSecurityAttributes
0x180054535  xor     r8d, r8d; dwShareMode
0x180054538  mov     edx, 40000000h; dwDesiredAccess
0x18005453d  mov     rcx, rax; lpFileName
0x180054540  call    cs:__imp_CreateFileW
0x180054547  nop     dword ptr [rax+rax+00h]
0x18005454c  mov     rbx, rax
0x18005454f  mov     [rsp+2C0h+var_260], rax
0x180054554  lea     rcx, [rbp+1C0h+Src]
0x180054558  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005455d  lea     rax, [rbx-1]
0x180054561  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180054565  setnbe  al
0x180054568  mov     rcx, [rbp+1C8h]; this
0x18005456f  test    al, al
0x180054571  jnz     loc_18005489A
0x180054577  mov     [rbp+1C0h+NumberOfBytesWritten], r12d
0x18005457b  lea     rdx, lpBuffer
0x180054582  cmp     cs:qword_1800BDD80, 0Fh
0x18005458a  cmova   rdx, cs:lpBuffer; lpBuffer
0x180054592  mov     qword ptr [rsp+2C0h+dwCreationDisposition], r12; int
0x180054597  lea     r9, [rbp+1C0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18005459b  mov     r8d, cs:nNumberOfBytesToWrite; nNumberOfBytesToWrite
0x1800545a2  mov     rcx, rbx; hFile
0x1800545a5  call    cs:__imp_WriteFile
0x1800545ac  nop     dword ptr [rax+rax+00h]
0x1800545b1  mov     rcx, [rbp+1C8h]; this
0x1800545b8  test    eax, eax
0x1800545ba  jz      loc_1800548AC
0x1800545c0  lea     rax, [rbx-1]
0x1800545c4  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800545c8  ja      short loc_1800545D9
0x1800545ca  mov     rcx, rbx; hObject
0x1800545cd  call    cs:__imp_CloseHandle
0x1800545d4  nop     dword ptr [rax+rax+00h]
0x1800545d9  cmp     dword ptr [rdi], 1
0x1800545dc  jnz     loc_180054809
0x1800545e2  lea     r8, aFiles; "Files"
0x1800545e9  mov     rdx, r14; pszPathIn
0x1800545ec  lea     rcx, [rbp+1C0h+pszPathIn]; Src
0x1800545f0  call    ?CombineFilePath@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG0@Z; Vml::CombineFilePath(ushort const *,ushort const *)
0x1800545f5  nop
0x1800545f6  call    ?IsHostPreReleaseImageCapable@Helpers@OsImageUtilities@@YA_NXZ; OsImageUtilities::Helpers::IsHostPreReleaseImageCapable(void)
0x1800545fb  test    al, al
0x1800545fd  jnz     short loc_18005460F
0x1800545ff  mov     rcx, r14; pszPathIn
0x180054602  call    ?IsPreReleaseImage@Helpers@OsImageUtilities@@YA_NPEBG@Z; OsImageUtilities::Helpers::IsPreReleaseImage(ushort const *)
0x180054607  test    al, al
0x180054609  jnz     loc_18005483E
0x18005460f  mov     rcx, r14; pszPathIn
0x180054612  call    ?UseLegacyFilter@Helpers@OsImageUtilities@@YA_NPEBG@Z; OsImageUtilities::Helpers::UseLegacyFilter(ushort const *)
0x180054617  movzx   r15d, al
0x18005461b  xor     r15d, 1
0x18005461f  xorps   xmm0, xmm0
0x180054622  movups  [rsp+2C0h+var_258], xmm0
0x180054627  xorps   xmm1, xmm1
0x18005462a  movdqu  [rsp+2C0h+var_248], xmm1
0x180054630  mov     rax, r12
0x180054633  mov     [rbp+1C0h+var_238], rax
0x180054637  movups  [rbp+1C0h+var_230], xmm0
0x18005463b  mov     qword ptr [rsp+2C0h+var_270], r12
0x180054640  movups  xmm2, cs:UTILITY_VM_LAYER_ID
0x180054647  movups  [rsp+2C0h+var_280], xmm2
0x18005464c  cmp     [rdi+7], r12b
0x180054650  jnz     short loc_180054687
0x180054652  cmp     [rdi+6], r12b
0x180054656  jz      short loc_180054672
0x180054658  mov     dword ptr [rsp+2C0h+var_270], 4
0x180054660  lea     rcx, off_18008AE00; "Windows"
0x180054667  mov     qword ptr [rsp+2C0h+var_258], 2
0x180054670  jmp     short loc_180054682
0x180054672  lea     rcx, off_18008AD50; "Windows"
0x180054679  mov     qword ptr [rsp+2C0h+var_258], 0Bh
0x180054682  mov     qword ptr [rsp+2C0h+var_258+8], rcx
0x180054687  mov     qword ptr [rsp+2C0h+var_270+8], r14
0x18005468c  psrldq  xmm1, 8
0x180054691  movq    rdx, xmm1
0x180054696  cmp     rdx, rax
0x180054699  jz      short loc_1800546AE
0x18005469b  movups  xmmword ptr [rdx], xmm2
0x18005469e  movups  xmm0, [rsp+2C0h+var_270]
0x1800546a3  movups  xmmword ptr [rdx+10h], xmm0
0x1800546a7  add     qword ptr [rbp+1C0h+var_248+8], 20h ; ' '
0x1800546ac  jmp     short loc_1800546BD
0x1800546ae  lea     r8, [rsp+2C0h+var_280]
0x1800546b3  lea     rcx, [rsp+2C0h+var_248]
0x1800546b8  call    ??$_Emplace_reallocate@U_WC_LAYER_DESCRIPTOR@@@?$vector@U_WC_LAYER_DESCRIPTOR@@V?$allocator@U_WC_LAYER_DESCRIPTOR@@@std@@@std@@AEAAPEAU_WC_LAYER_DESCRIPTOR@@QEAU2@$$QEAU2@@Z; std::vector<_WC_LAYER_DESCRIPTOR>::_Emplace_reallocate<_WC_LAYER_DESCRIPTOR>(_WC_LAYER_DESCRIPTOR * const,_WC_LAYER_DESCRIPTOR &&)
0x1800546bd  mov     r14, [rdi+10h]
0x1800546c1  mov     rbx, [rdi+8]
0x1800546c5  jmp     short loc_18005471B
0x1800546c7  xorps   xmm0, xmm0
0x1800546ca  movdqu  [rsp+2C0h+var_280+8], xmm0
0x1800546d0  movups  xmm1, xmmword ptr [rbx]
0x1800546d3  movups  [rsp+2C0h+var_280], xmm1
0x1800546d8  lea     rax, [rbx+10h]
0x1800546dc  cmp     qword ptr [rbx+28h], 7
0x1800546e1  jbe     short loc_1800546E6
0x1800546e3  mov     rax, [rax]
0x1800546e6  mov     qword ptr [rsp+2C0h+var_270+8], rax
0x1800546eb  mov     rdx, qword ptr [rbp+1C0h+var_248+8]
0x1800546ef  cmp     rdx, [rbp+1C0h+var_238]
0x1800546f3  jz      short loc_180054708
0x1800546f5  movups  xmmword ptr [rdx], xmm1
0x1800546f8  movups  xmm0, [rsp+2C0h+var_270]
0x1800546fd  movups  xmmword ptr [rdx+10h], xmm0
0x180054701  add     qword ptr [rbp+1C0h+var_248+8], 20h ; ' '
0x180054706  jmp     short loc_180054717
0x180054708  lea     r8, [rsp+2C0h+var_280]
0x18005470d  lea     rcx, [rsp+2C0h+var_248]
0x180054712  call    ??$_Emplace_reallocate@U_WC_LAYER_DESCRIPTOR@@@?$vector@U_WC_LAYER_DESCRIPTOR@@V?$allocator@U_WC_LAYER_DESCRIPTOR@@@std@@@std@@AEAAPEAU_WC_LAYER_DESCRIPTOR@@QEAU2@$$QEAU2@@Z; std::vector<_WC_LAYER_DESCRIPTOR>::_Emplace_reallocate<_WC_LAYER_DESCRIPTOR>(_WC_LAYER_DESCRIPTOR * const,_WC_LAYER_DESCRIPTOR &&)
0x180054717  add     rbx, 38h ; '8'
0x18005471b  cmp     rbx, r14
0x18005471e  jnz     short loc_1800546C7
0x180054720  movups  xmm0, xmmword ptr [rdi+20h]
0x180054724  movdqu  [rbp+1C0h+var_230], xmm0
0x180054729  xorps   xmm1, xmm1
0x18005472c  xor     eax, eax
0x18005472e  movups  [rbp+1C0h+var_1D0], xmm1
0x180054732  mov     [rbp+1C0h+var_1C0], rax
0x180054736  lea     edx, [rax+11h]; int
0x180054739  lea     rcx, [rbp+1C0h+var_1D0]; this
0x18005473d  call    ??0TemporaryPrivilege@Vml@@QEAA@J@Z; Vml::TemporaryPrivilege::TemporaryPrivilege(long)
0x180054742  nop
0x180054743  xorps   xmm0, xmm0
0x180054746  xor     eax, eax
0x180054748  movups  [rbp+1C0h+Src], xmm0
0x18005474c  mov     [rbp+1C0h+var_1E0], rax
0x180054750  lea     edx, [rax+12h]; int
0x180054753  lea     rcx, [rbp+1C0h+Src]; this
0x180054757  call    ??0TemporaryPrivilege@Vml@@QEAA@J@Z; Vml::TemporaryPrivilege::TemporaryPrivilege(long)
0x18005475c  nop
0x18005475d  cmp     qword ptr [rsi+18h], 7
0x180054762  jbe     short loc_180054769
0x180054764  mov     rdx, [rsi]
0x180054767  jmp     short loc_18005476C
0x180054769  mov     rdx, rsi; pszPathIn
0x18005476c  lea     r8, asc_18008E17C; "\\"
0x180054773  lea     rcx, [rbp+1C0h+var_1B0]; Src
0x180054777  call    ?CombineFilePath@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG0@Z; Vml::CombineFilePath(ushort const *,ushort const *)
0x18005477c  nop
0x18005477d  lea     rdx, [rbp+1C0h+pszPathIn]
0x180054781  cmp     [rbp+1C0h+var_1F8], 7
0x180054786  cmova   rdx, [rbp+1C0h+pszPathIn]
0x18005478b  lea     rcx, [rbp+1C0h+var_1B0]
0x18005478f  cmp     [rbp+1C0h+var_198], 7
0x180054794  cmova   rcx, [rbp+1C0h+var_1B0]
0x180054799  mov     r9d, r15d
0x18005479c  lea     r8, [rsp+2C0h+var_258]
0x1800547a1  call    ?InitializeAndPopulateSandbox@Helpers@OsImageUtilities@@YAXPEBG0AEBUSandboxOptions@12@W4_WC_NESTING_MODE@@@Z; OsImageUtilities::Helpers::InitializeAndPopulateSandbox(ushort const *,ushort const *,OsImageUtilities::Helpers::SandboxOptions const &,_WC_NESTING_MODE)
0x1800547a6  cmp     qword ptr [rsi+18h], 7
0x1800547ab  jbe     short loc_1800547B2
0x1800547ad  mov     rcx, [rsi]
0x1800547b0  jmp     short loc_1800547B5
0x1800547b2  mov     rcx, rsi; pszPathIn
0x1800547b5  call    ?CreateSandboxStateDirectory@Helpers@OsImageUtilities@@YAXPEBG@Z; OsImageUtilities::Helpers::CreateSandboxStateDirectory(ushort const *)
0x1800547ba  cmp     [rdi+5], r12b
0x1800547be  jnz     short loc_1800547D7
0x1800547c0  lea     rcx, [rbp+1C0h+pszPathIn]
0x1800547c4  cmp     [rbp+1C0h+var_1F8], 7
0x1800547c9  cmova   rcx, [rbp+1C0h+pszPathIn]; pszPathIn
0x1800547ce  mov     rdx, rsi; unsigned __int16 *
0x1800547d1  call    ?UpdateBcdStore@Helpers@OsImageUtilities@@YAXPEBGAEBUPartitionInfo@@@Z; OsImageUtilities::Helpers::UpdateBcdStore(ushort const *,PartitionInfo const &)
0x1800547d6  nop
0x1800547d7  lea     rcx, [rbp+1C0h+var_1B0]
0x1800547db  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800547e0  nop
0x1800547e1  lea     rcx, [rbp+1C0h+Src]; this
0x1800547e5  call    ??1TemporaryPrivilege@Vml@@QEAA@XZ; Vml::TemporaryPrivilege::~TemporaryPrivilege(void)
0x1800547ea  nop
0x1800547eb  lea     rcx, [rbp+1C0h+var_1D0]; this
0x1800547ef  call    ??1TemporaryPrivilege@Vml@@QEAA@XZ; Vml::TemporaryPrivilege::~TemporaryPrivilege(void)
  ... truncated ...
```
