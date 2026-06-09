# ColorFiltering::ColorFilterHelper::UpdateActiveFilter(void)

- ea: `0x14001aa78`
- end: `0x14001b164`
- name: `?UpdateActiveFilter@ColorFilterHelper@ColorFiltering@@SAXXZ`
- size: `1772`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1400172b0`

## callees

- `0x140002480`
- `0x140002fa0`
- `0x14000d75c`
- `0x14000ea8c`
- `0x14000eb0c`
- `0x140019410`
- `0x140019838`
- `0x140019a74`
- `0x14001a540`
- `0x14001aa78`
- `0x14001b2ec`
- `0x14001b470`
- `0x14001b5f4`
- `0x14001b778`
- `0x14001b7ac`

## import_xrefs

- `USER32!SetDesktopColorTransform` at `0x14001b124`
- `USER32!SetDesktopColorTransform` at `0x14001b124`
- `mscms!__imp_?InternalSetAccessibilityColorMatrix@@YAJAEAY144M@Z` at `0x14001b110`
- `mscms!__imp_?InternalSetAccessibilityColorMatrix@@YAJAEAY144M@Z` at `0x14001b110`

## string_xrefs

- `0x14001aae9`: `Software\Microsoft\Windows NT\CurrentVersion\Accessibility\ATConfig\colorfiltering`

## pseudocode

```c
void ColorFiltering::ColorFilterHelper::UpdateActiveFilter(void)
{
  char v0; // si
  char v1; // bl
  char v2; // di
  __int64 v3; // rdx
  float v4; // eax
  __int128 v5; // xmm0
  __int128 v6; // xmm1
  const struct _MAGN_COLOR_TRANSFORM *v7; // rcx
  __int64 *v8; // r9
  __int64 *v9; // r8
  __int128 v10; // xmm1
  __int64 *v11; // rax
  __int64 *v12; // [rsp+28h] [rbp-D8h]
  __int64 *v13; // [rsp+30h] [rbp-D0h]
  __int64 *v14; // [rsp+38h] [rbp-C8h]
  __int64 *v15; // [rsp+40h] [rbp-C0h]
  __int64 *v16; // [rsp+48h] [rbp-B8h]
  __int64 *v17; // [rsp+50h] [rbp-B0h]
  __int64 *v18; // [rsp+58h] [rbp-A8h]
  ColorFiltering::Filters *v19; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v20; // [rsp+68h] [rbp-98h] BYREF
  __int64 v21; // [rsp+70h] [rbp-90h] BYREF
  __int64 v22; // [rsp+78h] [rbp-88h]
  __int64 v23; // [rsp+80h] [rbp-80h]
  _QWORD v24[3]; // [rsp+88h] [rbp-78h] BYREF
  __m256i v25; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v26; // [rsp+C0h] [rbp-40h]
  __m128i si128; // [rsp+D0h] [rbp-30h]
  __int128 v28; // [rsp+E0h] [rbp-20h]
  __int128 v29; // [rsp+F0h] [rbp-10h]
  int v30; // [rsp+100h] [rbp+0h]
  float v31[5][5]; // [rsp+110h] [rbp+10h] BYREF
  __int128 v32; // [rsp+180h] [rbp+80h] BYREF
  __int128 v33; // [rsp+190h] [rbp+90h]
  __int128 v34; // [rsp+1A0h] [rbp+A0h]
  __int128 v35; // [rsp+1B0h] [rbp+B0h]
  __int128 v36; // [rsp+1C0h] [rbp+C0h]
  __int128 v37; // [rsp+1D0h] [rbp+D0h]
  int v38; // [rsp+1E0h] [rbp+E0h]
  __int128 v39; // [rsp+1F0h] [rbp+F0h] BYREF
  __int128 v40; // [rsp+200h] [rbp+100h]
  __int128 v41; // [rsp+210h] [rbp+110h]
  __int128 v42; // [rsp+220h] [rbp+120h]
  __int128 v43; // [rsp+230h] [rbp+130h]
  __int128 v44; // [rsp+240h] [rbp+140h]
  int v45; // [rsp+250h] [rbp+150h]

  v20 = -1;
  v19 = (ColorFiltering::Filters *)0x6400000046LL;
  if ( ColorFiltering::ColorFilterHelper::IsActive() )
  {
    memset(v24, 0, sizeof(v24));
    v0 = 1;
    v1 = 1;
    if ( (unsigned int)ATL::CRegKey::Open(
                         (ATL::CRegKey *)v24,
                         HKEY_CURRENT_USER,
                         L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Accessibility\\ATConfig\\colorfiltering",
                         1u) )
      goto LABEL_22;
    if ( (unsigned int)ATL::CRegKey::QueryDWORDValue((ATL::CRegKey *)v24, L"FilterType", &v20) )
    {
      v21 = 0;
      v22 = 0;
      v23 = 0;
      v2 = 1;
      if ( !(unsigned int)ATL::CRegKey::Open(
                            (ATL::CRegKey *)&v21,
                            HKEY_CURRENT_USER,
                            L"Software\\Microsoft\\ColorFiltering",
                            1u)
        && !(unsigned int)ATL::CRegKey::QueryDWORDValue((ATL::CRegKey *)&v21, L"FilterType", &v20) )
      {
        v2 = 0;
        ColorFiltering::ColorFilterHelper::UpdateTransferSettingsFilterType(v20);
      }
      ATL::CRegKey::Close((ATL::CRegKey *)&v21);
    }
    else
    {
      v2 = 0;
    }
    if ( (unsigned int)ATL::CRegKey::QueryDWORDValue((ATL::CRegKey *)v24, L"Intensity", (unsigned int *)&v19 + 1) )
    {
      v21 = 0;
      v22 = 0;
      v23 = 0;
      if ( !(unsigned int)ATL::CRegKey::Open(
                            (ATL::CRegKey *)&v21,
                            HKEY_CURRENT_USER,
                            L"Software\\Microsoft\\ColorFiltering",
                            1u)
        && !(unsigned int)ATL::CRegKey::QueryDWORDValue((ATL::CRegKey *)&v21, L"Intensity", (unsigned int *)&v19 + 1) )
      {
        v0 = 0;
        ColorFiltering::ColorFilterHelper::UpdateTransferSettingsIntensity(SHIDWORD(v19));
      }
      ATL::CRegKey::Close((ATL::CRegKey *)&v21);
    }
    else
    {
      v0 = 0;
    }
    if ( (unsigned int)ATL::CRegKey::QueryDWORDValue((ATL::CRegKey *)v24, L"Gain", (unsigned int *)&v19) )
    {
      v21 = 0;
      v22 = 0;
      v23 = 0;
      if ( !(unsigned int)ATL::CRegKey::Open(
                            (ATL::CRegKey *)&v21,
                            HKEY_CURRENT_USER,
                            L"Software\\Microsoft\\ColorFiltering",
                            1u)
        && !(unsigned int)ATL::CRegKey::QueryDWORDValue((ATL::CRegKey *)&v21, L"Gain", (unsigned int *)&v19) )
      {
        v1 = 0;
        ColorFiltering::ColorFilterHelper::UpdateTransferSettingsGain((int)v19);
      }
      ATL::CRegKey::Close((ATL::CRegKey *)&v21);
    }
    else
    {
      v1 = 0;
    }
    if ( v2 )
LABEL_22:
      v20 = 0;
    if ( v0 )
      HIDWORD(v19) = 100;
    if ( v1 )
      LODWORD(v19) = 70;
    ATL::CRegKey::Close((ATL::CRegKey *)v24);
  }
  memset_0(v31, 0, sizeof(v31));
  switch ( v20 )
  {
    case 0u:
      v4 = 1.0;
      *(_OWORD *)&v31[0][0] = ColorFiltering::Filters::Greyscale;
      *(_OWORD *)&v31[0][4] = xmmword_14002F000;
      *(_OWORD *)&v31[1][3] = xmmword_14002F010;
      v5 = xmmword_14002F030;
      *(_OWORD *)&v31[2][2] = xmmword_14002F020;
      v6 = xmmword_14002F040;
      goto LABEL_43;
    case 1u:
      v4 = 1.0;
      *(_OWORD *)&v31[0][0] = ColorFiltering::Filters::InvertFilter;
      *(_OWORD *)&v31[0][4] = xmmword_14002E660;
      *(_OWORD *)&v31[1][3] = xmmword_14002E670;
      v5 = xmmword_14002E690;
      *(_OWORD *)&v31[2][2] = xmmword_14002E680;
      v6 = xmmword_14002E6A0;
      goto LABEL_43;
    case 2u:
      v4 = 1.0;
      *(_OWORD *)&v31[0][0] = ColorFiltering::Filters::GreyscaleInvert;
      *(_OWORD *)&v31[0][4] = xmmword_14002E4A0;
      *(_OWORD *)&v31[1][3] = xmmword_14002E4B0;
      v5 = xmmword_14002E4D0;
      *(_OWORD *)&v31[2][2] = xmmword_14002E4C0;
      v6 = xmmword_14002E4E0;
      goto LABEL_43;
    case 3u:
      v25.m256i_i32[1] = ColorFiltering::Filters::_ConvertToPercent((ColorFiltering::Filters *)(unsigned int)v19, v3);
      v18 = qword_14002E2B0;
      v8 = qword_14002E7A0;
      HIDWORD(v26) = v25.m256i_i32[1];
      v17 = qword_14002F0D0;
      v9 = qword_14002E6C0;
      v25.m256i_i32[0] = 1065353216;
      v16 = qword_14002F060;
      v10 = 0;
      memset(&v25.m256i_u64[1], 0, 24);
      v15 = qword_14002EF10;
      v14 = qword_14002EAB0;
      v13 = qword_14002E880;
      v12 = qword_14002EB90;
      v11 = qword_14002EEA0;
      DWORD2(v26) = 0;
      goto LABEL_38;
    case 4u:
      v25.m256i_i32[5] = ColorFiltering::Filters::_ConvertToPercent((ColorFiltering::Filters *)(unsigned int)v19, v3);
      v18 = qword_14002E9D0;
      v8 = qword_14002E570;
      *((_QWORD *)&v26 + 1) = v25.m256i_u32[5];
      v17 = qword_14002EC70;
      v9 = qword_14002E730;
      v16 = qword_14002ED50;
      v10 = 0;
      memset(&v25, 0, 20);
      v15 = qword_14002EB20;
      v14 = qword_14002E340;
      v13 = qword_14002E8F0;
      v12 = qword_14002E500;
      v11 = qword_14002EA40;
      v25.m256i_i64[3] = 1065353216;
LABEL_38:
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      v28 = 0;
      v30 = 0;
      v29 = v10;
      *(_QWORD *)&v26 = 0;
      ColorFiltering::Filters::_GetAppearance(&v39, HIDWORD(v19), v9, v8, v11, v12, v13, v14, v15, v16, v17, v18);
      v7 = (const struct _MAGN_COLOR_TRANSFORM *)&v32;
      v38 = v45;
      v32 = v39;
      v33 = v40;
      v34 = v41;
      v35 = v42;
      v36 = v43;
      v37 = v44;
      goto LABEL_39;
    case 5u:
      v25.m256i_i32[2] = ColorFiltering::Filters::_ConvertToPercent((ColorFiltering::Filters *)(unsigned int)v19, v3);
      v25.m256i_i32[7] = v25.m256i_i32[2];
      v25.m256i_i64[0] = 1065353216;
      *(__int64 *)((char *)&v25.m256i_i64[1] + 4) = 0;
      *(__int64 *)((char *)&v25.m256i_i64[2] + 4) = 0x3F80000000000000LL;
      v26 = 0;
      si128 = 0;
      v28 = 0;
      v29 = 0;
      v30 = 0;
      ColorFiltering::Filters::_GetAppearance(
        &v32,
        HIDWORD(v19),
        qword_14002E420,
        qword_14002E240,
        qword_14002EE30,
        qword_14002E5E0,
        qword_14002EDC0,
        qword_14002E960,
        qword_14002E3B0,
        qword_14002EC00,
        qword_14002E810,
        qword_14002ECE0);
      v7 = (const struct _MAGN_COLOR_TRANSFORM *)&v39;
      v45 = v38;
      v39 = v32;
      v40 = v33;
      v41 = v34;
      v42 = v35;
      v43 = v36;
      v44 = v37;
LABEL_39:
      ColorFiltering::ColorFilterHelper::GenerateAdaptationFilter(
        v7,
        (const struct _MAGN_COLOR_TRANSFORM *)&v25,
        (struct _MAGN_COLOR_TRANSFORM *)v31);
      goto LABEL_44;
  }
  v4 = *(float *)&dword_140046C90;
  *(_OWORD *)&v31[0][0] = ColorFiltering::Filters::PassthroughFilter;
  *(_OWORD *)&v31[0][4] = xmmword_140046C40;
  *(_OWORD *)&v31[1][3] = xmmword_140046C50;
  v5 = xmmword_140046C70;
  *(_OWORD *)&v31[2][2] = xmmword_140046C60;
  v6 = xmmword_140046C80;
LABEL_43:
  v31[4][4] = v4;
  *(_OWORD *)&v31[4][0] = v6;
  *(_OWORD *)&v31[3][1] = v5;
LABEL_44:
  LOBYTE(v3) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_AllowProcessingColorFiltersOnHardware>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_AllowProcessingColorFiltersOnHardware>::GetImpl'::`2'::impl,
    v3);
  if ( (int)InternalSetAccessibilityColorMatrix((float (*)[5][5])v31) < 0 )
    SetDesktopColorTransform((float *)v31);
  AccessibilitySettingsTelemetry::ColorFilterWithOptions<unsigned long &,unsigned long &,unsigned long &>(
    &v20,
    (char *)&v19 + 4,
    &v19);
}

```

## disassembly

```asm
0x14001aa78  push    rbp
0x14001aa7a  push    rbx
0x14001aa7b  push    rsi
0x14001aa7c  push    rdi
0x14001aa7d  push    r12
0x14001aa7f  push    r14
0x14001aa81  lea     rbp, [rsp-178h]
0x14001aa89  sub     rsp, 278h
0x14001aa90  mov     rax, cs:__security_cookie
0x14001aa97  xor     rax, rsp
0x14001aa9a  mov     [rbp+1A0h+var_40], rax
0x14001aaa1  mov     [rsp+2A0h+var_238], 0FFFFFFFFh
0x14001aaa9  mov     dword ptr [rsp+2A0h+var_240+4], 64h ; 'd'
0x14001aab1  mov     dword ptr [rsp+2A0h+var_240], 46h ; 'F'
0x14001aab9  call    ?IsActive@ColorFilterHelper@ColorFiltering@@SA_NXZ; ColorFiltering::ColorFilterHelper::IsActive(void)
0x14001aabe  xor     r14d, r14d
0x14001aac1  test    al, al
0x14001aac3  jz      loc_14001AC9E
0x14001aac9  mov     r12, 0FFFFFFFF80000001h
0x14001aad0  mov     [rbp+1A0h+var_218], r14
0x14001aad4  mov     sil, 1
0x14001aad7  mov     [rbp+1A0h+var_210], r14
0x14001aadb  mov     rdx, r12; hKey
0x14001aade  mov     [rbp+1A0h+var_208], r14
0x14001aae2  lea     r9d, [r14+1]; unsigned int
0x14001aae6  mov     bl, sil
0x14001aae9  lea     r8, aSoftwareMicros_12; "Software\\Microsoft\\Windows NT\\Curren"...
0x14001aaf0  lea     rcx, [rbp+1A0h+var_218]; this
0x14001aaf4  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x14001aaf9  test    eax, eax
0x14001aafb  jnz     loc_14001AC77
0x14001ab01  lea     r8, [rsp+2A0h+var_238]; unsigned int *
0x14001ab06  lea     rdx, aFiltertype_0; "FilterType"
0x14001ab0d  lea     rcx, [rbp+1A0h+var_218]; this
0x14001ab11  call    ?QueryDWORDValue@CRegKey@ATL@@QEAAJPEBGAEAK@Z; ATL::CRegKey::QueryDWORDValue(ushort const *,ulong &)
0x14001ab16  test    eax, eax
0x14001ab18  jnz     short loc_14001AB1F
0x14001ab1a  mov     dil, r14b
0x14001ab1d  jmp     short loc_14001AB7E
0x14001ab1f  mov     r9d, 1; unsigned int
0x14001ab25  mov     [rsp+2A0h+var_230], r14
0x14001ab2a  lea     r8, aSoftwareMicros_13; "Software\\Microsoft\\ColorFiltering"
0x14001ab31  mov     [rsp+2A0h+var_228], r14
0x14001ab36  mov     rdx, r12; hKey
0x14001ab39  mov     [rbp+1A0h+var_220], r14
0x14001ab3d  lea     rcx, [rsp+2A0h+var_230]; this
0x14001ab42  mov     dil, bl
0x14001ab45  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x14001ab4a  test    eax, eax
0x14001ab4c  jnz     short loc_14001AB74
0x14001ab4e  lea     r8, [rsp+2A0h+var_238]; unsigned int *
0x14001ab53  lea     rdx, aFiltertype_0; "FilterType"
0x14001ab5a  lea     rcx, [rsp+2A0h+var_230]; this
0x14001ab5f  call    ?QueryDWORDValue@CRegKey@ATL@@QEAAJPEBGAEAK@Z; ATL::CRegKey::QueryDWORDValue(ushort const *,ulong &)
0x14001ab64  test    eax, eax
0x14001ab66  jnz     short loc_14001AB74
0x14001ab68  mov     ecx, [rsp+2A0h+var_238]; unsigned int
0x14001ab6c  mov     dil, r14b
0x14001ab6f  call    ?UpdateTransferSettingsFilterType@ColorFilterHelper@ColorFiltering@@SAXK@Z; ColorFiltering::ColorFilterHelper::UpdateTransferSettingsFilterType(ulong)
0x14001ab74  lea     rcx, [rsp+2A0h+var_230]; this
0x14001ab79  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x14001ab7e  lea     r8, [rsp+2A0h+var_240+4]; unsigned int *
0x14001ab83  lea     rdx, aIntensity_0; "Intensity"
0x14001ab8a  lea     rcx, [rbp+1A0h+var_218]; this
0x14001ab8e  call    ?QueryDWORDValue@CRegKey@ATL@@QEAAJPEBGAEAK@Z; ATL::CRegKey::QueryDWORDValue(ushort const *,ulong &)
0x14001ab93  test    eax, eax
0x14001ab95  jnz     short loc_14001AB9C
0x14001ab97  mov     sil, r14b
0x14001ab9a  jmp     short loc_14001ABF8
0x14001ab9c  mov     r9d, 1; unsigned int
0x14001aba2  mov     [rsp+2A0h+var_230], r14
0x14001aba7  lea     r8, aSoftwareMicros_13; "Software\\Microsoft\\ColorFiltering"
0x14001abae  mov     [rsp+2A0h+var_228], r14
0x14001abb3  mov     rdx, r12; hKey
0x14001abb6  mov     [rbp+1A0h+var_220], r14
0x14001abba  lea     rcx, [rsp+2A0h+var_230]; this
0x14001abbf  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x14001abc4  test    eax, eax
0x14001abc6  jnz     short loc_14001ABEE
0x14001abc8  lea     r8, [rsp+2A0h+var_240+4]; unsigned int *
0x14001abcd  lea     rdx, aIntensity_0; "Intensity"
0x14001abd4  lea     rcx, [rsp+2A0h+var_230]; this
0x14001abd9  call    ?QueryDWORDValue@CRegKey@ATL@@QEAAJPEBGAEAK@Z; ATL::CRegKey::QueryDWORDValue(ushort const *,ulong &)
0x14001abde  test    eax, eax
0x14001abe0  jnz     short loc_14001ABEE
0x14001abe2  mov     ecx, dword ptr [rsp+2A0h+var_240+4]; unsigned int
0x14001abe6  mov     sil, r14b
0x14001abe9  call    ?UpdateTransferSettingsIntensity@ColorFilterHelper@ColorFiltering@@SAXK@Z; ColorFiltering::ColorFilterHelper::UpdateTransferSettingsIntensity(ulong)
0x14001abee  lea     rcx, [rsp+2A0h+var_230]; this
0x14001abf3  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x14001abf8  lea     r8, [rsp+2A0h+var_240]; unsigned int *
0x14001abfd  lea     rdx, aGain_0; "Gain"
0x14001ac04  lea     rcx, [rbp+1A0h+var_218]; this
0x14001ac08  call    ?QueryDWORDValue@CRegKey@ATL@@QEAAJPEBGAEAK@Z; ATL::CRegKey::QueryDWORDValue(ushort const *,ulong &)
0x14001ac0d  test    eax, eax
0x14001ac0f  jnz     short loc_14001AC16
0x14001ac11  mov     bl, r14b
0x14001ac14  jmp     short loc_14001AC72
0x14001ac16  mov     r9d, 1; unsigned int
0x14001ac1c  mov     [rsp+2A0h+var_230], r14
0x14001ac21  lea     r8, aSoftwareMicros_13; "Software\\Microsoft\\ColorFiltering"
0x14001ac28  mov     [rsp+2A0h+var_228], r14
0x14001ac2d  mov     rdx, r12; hKey
0x14001ac30  mov     [rbp+1A0h+var_220], r14
0x14001ac34  lea     rcx, [rsp+2A0h+var_230]; this
0x14001ac39  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x14001ac3e  test    eax, eax
0x14001ac40  jnz     short loc_14001AC68
0x14001ac42  lea     r8, [rsp+2A0h+var_240]; unsigned int *
0x14001ac47  lea     rdx, aGain_0; "Gain"
0x14001ac4e  lea     rcx, [rsp+2A0h+var_230]; this
0x14001ac53  call    ?QueryDWORDValue@CRegKey@ATL@@QEAAJPEBGAEAK@Z; ATL::CRegKey::QueryDWORDValue(ushort const *,ulong &)
0x14001ac58  test    eax, eax
0x14001ac5a  jnz     short loc_14001AC68
0x14001ac5c  mov     ecx, dword ptr [rsp+2A0h+var_240]; unsigned int
0x14001ac60  mov     bl, r14b
0x14001ac63  call    ?UpdateTransferSettingsGain@ColorFilterHelper@ColorFiltering@@SAXK@Z; ColorFiltering::ColorFilterHelper::UpdateTransferSettingsGain(ulong)
0x14001ac68  lea     rcx, [rsp+2A0h+var_230]; this
0x14001ac6d  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x14001ac72  test    dil, dil
0x14001ac75  jz      short loc_14001AC7C
0x14001ac77  mov     [rsp+2A0h+var_238], r14d
0x14001ac7c  test    sil, sil
0x14001ac7f  jz      short loc_14001AC89
0x14001ac81  mov     dword ptr [rsp+2A0h+var_240+4], 64h ; 'd'
0x14001ac89  test    bl, bl
0x14001ac8b  jz      short loc_14001AC95
0x14001ac8d  mov     dword ptr [rsp+2A0h+var_240], 46h ; 'F'
0x14001ac95  lea     rcx, [rbp+1A0h+var_218]; this
0x14001ac99  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x14001ac9e  xor     edx, edx; Val
0x14001aca0  lea     rcx, [rbp+1A0h+var_190]; void *
0x14001aca4  lea     r8d, [rdx+64h]; Size
0x14001aca8  call    memset_0
0x14001acad  mov     eax, [rsp+2A0h+var_238]
0x14001acb1  test    eax, eax
0x14001acb3  jz      loc_14001B0B3
0x14001acb9  cmp     eax, 1
0x14001acbc  jz      loc_14001B071
0x14001acc2  cmp     eax, 2
0x14001acc5  jz      loc_14001B02C
0x14001accb  cmp     eax, 3
0x14001acce  jz      loc_14001AEED
0x14001acd4  cmp     eax, 4
0x14001acd7  jz      loc_14001AE55
0x14001acdd  cmp     eax, 5
0x14001ace0  jz      short loc_14001AD27
0x14001ace2  movaps  xmm0, cs:?PassthroughFilter@Filters@ColorFiltering@@3U_MAGN_COLOR_TRANSFORM@@A; _MAGN_COLOR_TRANSFORM ColorFiltering::Filters::PassthroughFilter
0x14001ace9  movaps  xmm1, cs:xmmword_140046C40
0x14001acf0  mov     eax, cs:dword_140046C90
0x14001acf6  movaps  [rbp+1A0h+var_190], xmm0
0x14001acfa  movaps  xmm0, cs:xmmword_140046C50
0x14001ad01  movaps  [rbp+1A0h+var_180], xmm1
0x14001ad05  movaps  xmm1, cs:xmmword_140046C60
0x14001ad0c  movaps  [rbp+1A0h+var_170], xmm0
0x14001ad10  movaps  xmm0, cs:xmmword_140046C70
0x14001ad17  movaps  [rbp+1A0h+var_160], xmm1
0x14001ad1b  movaps  xmm1, cs:xmmword_140046C80
0x14001ad22  jmp     loc_14001B0F3
0x14001ad27  mov     ecx, dword ptr [rsp+2A0h+var_240]; this
0x14001ad2b  call    ?_ConvertToPercent@Filters@ColorFiltering@@YAMK@Z; ColorFiltering::Filters::_ConvertToPercent(ulong)
0x14001ad30  mov     edx, dword ptr [rsp+2A0h+var_240+4]
0x14001ad34  lea     rax, qword_14002ECE0
0x14001ad3b  mov     [rsp+2A0h+var_248], rax
0x14001ad40  lea     r9, qword_14002E240
0x14001ad47  xorps   xmm1, xmm1
0x14001ad4a  movss   dword ptr [rbp+1A0h+var_200+8], xmm0
0x14001ad4f  lea     rax, qword_14002E810
0x14001ad56  movss   dword ptr [rbp+1A0h+var_1E8+4], xmm0
0x14001ad5b  mov     [rsp+2A0h+var_250], rax
0x14001ad60  lea     r8, qword_14002E420
0x14001ad67  xorps   xmm0, xmm0
0x14001ad6a  mov     qword ptr [rbp+1A0h+var_200], 3F800000h
0x14001ad72  lea     rax, qword_14002EC00
0x14001ad79  mov     qword ptr [rbp+1A0h+var_200+0Ch], r14
0x14001ad7d  mov     [rsp+2A0h+var_258], rax
0x14001ad82  lea     rcx, [rbp+1A0h+var_120]
0x14001ad89  lea     rax, qword_14002E3B0
0x14001ad90  mov     [rbp+1A0h+var_1EC], r14d
0x14001ad94  mov     [rsp+2A0h+var_260], rax
0x14001ad99  lea     rax, qword_14002E960
0x14001ada0  mov     [rsp+2A0h+var_268], rax
0x14001ada5  lea     rax, qword_14002EDC0
0x14001adac  mov     [rsp+2A0h+var_270], rax
0x14001adb1  lea     rax, qword_14002E5E0
0x14001adb8  mov     [rsp+2A0h+var_278], rax
0x14001adbd  lea     rax, qword_14002EE30
0x14001adc4  mov     [rsp+2A0h+var_280], rax
0x14001adc9  mov     dword ptr [rbp+1A0h+var_1E8], 3F800000h
0x14001add0  movaps  [rbp+1A0h+var_1E0], xmm0
0x14001add4  movaps  [rbp+1A0h+var_1D0], xmm1
0x14001add8  movaps  [rbp+1A0h+var_1C0], xmm0
0x14001addc  movaps  [rbp+1A0h+var_1B0], xmm1
0x14001ade0  mov     [rbp+1A0h+var_1A0], r14d
0x14001ade4  call    ?_GetAppearance@Filters@ColorFiltering@@YA?AU_MAGN_COLOR_TRANSFORM@@KAEBU3@000000000@Z; ColorFiltering::Filters::_GetAppearance(ulong,_MAGN_COLOR_TRANSFORM const &,_MAGN_COLOR_TRANSFORM const &,_MAGN_COLOR_TRANSFORM const &,_MAGN_COLOR_TRANSFORM const &,_MAGN_COLOR_TRANSFORM const &,_MAGN_COLOR_TRANSFORM const &,_MAGN_COLOR_TRANSFORM const &,_MAGN_COLOR_TRANSFORM const &,_MAGN_COLOR_TRANSFORM const &,_MAGN_COLOR_TRANSFORM const &)
0x14001ade9  movups  xmm0, [rbp+1A0h+var_120]
0x14001adf0  mov     eax, [rbp+1A0h+var_C0]
0x14001adf6  lea     rcx, [rbp+1A0h+var_B0]
0x14001adfd  movups  xmm1, [rbp+1A0h+var_110]
0x14001ae04  mov     [rbp+1A0h+var_50], eax
0x14001ae0a  movaps  [rbp+1A0h+var_B0], xmm0
0x14001ae11  movups  xmm0, [rbp+1A0h+var_100]
0x14001ae18  movaps  [rbp+1A0h+var_A0], xmm1
0x14001ae1f  movups  xmm1, [rbp+1A0h+var_F0]
0x14001ae26  movaps  [rbp+1A0h+var_90], xmm0
0x14001ae2d  movups  xmm0, [rbp+1A0h+var_E0]
0x14001ae34  movaps  [rbp+1A0h+var_80], xmm1
0x14001ae3b  movups  xmm1, [rbp+1A0h+var_D0]
0x14001ae42  movaps  [rbp+1A0h+var_70], xmm0
0x14001ae49  movaps  [rbp+1A0h+var_60], xmm1
0x14001ae50  jmp     loc_14001B01A
0x14001ae55  mov     ecx, dword ptr [rsp+2A0h+var_240]; this
0x14001ae59  call    ?_ConvertToPercent@Filters@ColorFiltering@@YAMK@Z; ColorFiltering::Filters::_ConvertToPercent(ulong)
0x14001ae5e  lea     rax, qword_14002E9D0
0x14001ae65  movss   [rbp+1A0h+var_1EC], xmm0
0x14001ae6a  mov     [rsp+2A0h+var_248], rax
0x14001ae6f  lea     r9, qword_14002E570
0x14001ae76  lea     rax, qword_14002EC70
0x14001ae7d  movss   dword ptr [rbp+1A0h+var_1E0+8], xmm0
0x14001ae82  mov     [rsp+2A0h+var_250], rax
0x14001ae87  lea     r8, qword_14002E730
0x14001ae8e  lea     rax, qword_14002ED50
0x14001ae95  mov     [rbp-50h], r14d
0x14001ae99  mov     [rsp+2A0h+var_258], rax
0x14001ae9e  xorps   xmm1, xmm1
0x14001aea1  lea     rax, qword_14002EB20
0x14001aea8  movaps  [rbp+1A0h+var_200], xmm1
0x14001aeac  mov     [rsp+2A0h+var_260], rax
0x14001aeb1  lea     rax, qword_14002E340
0x14001aeb8  mov     [rsp+2A0h+var_268], rax
0x14001aebd  lea     rax, qword_14002E8F0
0x14001aec4  mov     [rsp+2A0h+var_270], rax
0x14001aec9  lea     rax, qword_14002E500
0x14001aed0  mov     [rsp+2A0h+var_278], rax
0x14001aed5  lea     rax, qword_14002EA40
0x14001aedc  mov     [rbp+1A0h+var_1E8], 3F800000h
0x14001aee4  mov     dword ptr [rbp+1A0h+var_1E0+0Ch], r14d
0x14001aee8  jmp     loc_14001AF7F
0x14001aeed  mov     ecx, dword ptr [rsp+2A0h+var_240]; this
0x14001aef1  call    ?_ConvertToPercent@Filters@ColorFiltering@@YAMK@Z; ColorFiltering::Filters::_ConvertToPercent(ulong)
0x14001aef6  lea     rax, qword_14002E2B0
0x14001aefd  movss   dword ptr [rbp+1A0h+var_200+4], xmm0
0x14001af02  mov     [rsp+2A0h+var_248], rax
0x14001af07  lea     r9, qword_14002E7A0
0x14001af0e  lea     rax, qword_14002F0D0
0x14001af15  movss   dword ptr [rbp+1A0h+var_1E0+0Ch], xmm0
0x14001af1a  mov     [rsp+2A0h+var_250], rax
0x14001af1f  lea     r8, qword_14002E6C0
0x14001af26  lea     rax, qword_14002F060
0x14001af2d  mov     dword ptr [rbp+1A0h+var_200], 3F800000h
0x14001af34  mov     [rsp+2A0h+var_258], rax
0x14001af39  xorps   xmm1, xmm1
0x14001af3c  lea     rax, qword_14002EF10
0x14001af43  mov     qword ptr [rbp+1A0h+var_200+8], r14
0x14001af47  mov     [rsp+2A0h+var_260], rax
0x14001af4c  lea     rax, qword_14002EAB0
0x14001af53  mov     [rsp+2A0h+var_268], rax
0x14001af58  lea     rax, qword_14002E880
0x14001af5f  mov     [rsp+2A0h+var_270], rax
0x14001af64  lea     rax, qword_14002EB90
0x14001af6b  mov     [rsp+2A0h+var_278], rax
0x14001af70  lea     rax, qword_14002EEA0
0x14001af77  movaps  xmmword ptr [rbp-50h], xmm1
0x14001af7b  mov     dword ptr [rbp+1A0h+var_1E0+8], r14d
0x14001af7f  movdqa  xmm0, cs:__xmm@0000000000000000000000003f800000
0x14001af87  lea     rcx, [rbp+1A0h+var_B0]
0x14001af8e  mov     edx, dword ptr [rsp+2A0h+var_240+4]
0x14001af92  movaps  [rbp+1A0h+var_1D0], xmm0
0x14001af96  xorps   xmm0, xmm0
0x14001af99  movaps  [rbp+1A0h+var_1C0], xmm0
0x14001af9d  mov     [rsp+2A0h+var_280], rax
0x14001afa2  mov     [rbp+1A0h+var_1A0], r14d
0x14001afa6  movaps  [rbp+1A0h+var_1B0], xmm1
0x14001afaa  mov     qword ptr [rbp+1A0h+var_1E0], r14
0x14001afae  call    ?_GetAppearance@Filters@ColorFiltering@@YA?AU_MAGN_COLOR_TRANSFORM@@KAEBU3@000000000@Z; ColorFiltering::Filters::_GetAppearance(ulong,_MAGN_COLOR_TRANSFORM const &,_MAGN_COLOR_TRANSFORM const &,_MAGN_COLOR_TRANSFORM const &,_MAGN_COLOR_TRANSFORM const &,_MAGN_COLOR_TRANSFORM const &,_MAGN_COLOR_TRANSFORM const &,_MAGN_COLOR_TRANSFORM const &,_MAGN_COLOR_TRANSFORM const &,_MAGN_COLOR_TRANSFORM const &,_MAGN_COLOR_TRANSFORM const &)
0x14001afb3  movups  xmm0, [rbp+1A0h+var_B0]
0x14001afba  mov     eax, [rbp+1A0h+var_50]
0x14001afc0  lea     rcx, [rbp+1A0h+var_120]; struct _MAGN_COLOR_TRANSFORM *
0x14001afc7  movups  xmm1, [rbp+1A0h+var_A0]
0x14001afce  mov     [rbp+1A0h+var_C0], eax
0x14001afd4  movaps  [rbp+1A0h+var_120], xmm0
0x14001afdb  movups  xmm0, [rbp+1A0h+var_90]
0x14001afe2  movaps  [rbp+1A0h+var_110], xmm1
0x14001afe9  movups  xmm1, [rbp+1A0h+var_80]
0x14001aff0  movaps  [rbp+1A0h+var_100], xmm0
0x14001aff7  movups  xmm0, [rbp+1A0h+var_70]
0x14001affe  movaps  [rbp+1A0h+var_F0], xmm1
0x14001b005  movups  xmm1, [rbp+1A0h+var_60]
0x14001b00c  movaps  [rbp+1A0h+var_E0], xmm0
0x14001b013  movaps  [rbp+1A0h+var_D0], xmm1
0x14001b01a  lea     rdx, [rbp+1A0h+var_200]; struct _MAGN_COLOR_TRANSFORM *
0x14001b01e  lea     r8, [rbp+1A0h+var_190]; struct _MAGN_COLOR_TRANSFORM *
0x14001b022  call    ?GenerateAdaptationFilter@ColorFilterHelper@ColorFiltering@@CAXAEBU_MAGN_COLOR_TRANSFORM@@0AEAU3@@Z; ColorFiltering::ColorFilterHelper::GenerateAdaptationFilter(_MAGN_COLOR_TRANSFORM const &,_MAGN_COLOR_TRANSFORM const &,_MAGN_COLOR_TRANSFORM &)
0x14001b027  jmp     loc_14001B0FE
0x14001b02c  movaps  xmm0, cs:?GreyscaleInvert@Filters@ColorFiltering@@3U_MAGN_COLOR_TRANSFORM@@A; _MAGN_COLOR_TRANSFORM ColorFiltering::Filters::GreyscaleInvert
0x14001b033  movaps  xmm1, cs:xmmword_14002E4A0
0x14001b03a  mov     eax, cs:dword_14002E4F0
0x14001b040  movaps  [rbp+1A0h+var_190], xmm0
0x14001b044  movaps  xmm0, cs:xmmword_14002E4B0
0x14001b04b  movaps  [rbp+1A0h+var_180], xmm1
  ... truncated ...
```
