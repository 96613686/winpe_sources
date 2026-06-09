# SendFileInfoToTelemetry(ushort const *)

- ea: `0x180023dbc`
- end: `0x1800242c8`
- name: `?SendFileInfoToTelemetry@@YAXPEBG@Z`
- size: `1292`
- prototype: `void __fastcall(LPCWSTR lptstrFilename)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180014fc0`

## callees

- `0x180001958`
- `0x180001a24`
- `0x1800066d0`
- `0x180008320`
- `0x18001a6a8`
- `0x180020850`
- `0x180021590`
- `0x18002188c`
- `0x1800218e0`
- `0x180021978`
- `0x1800224ac`
- `0x180022750`
- `0x180022ec4`
- `0x180023220`
- `0x1800237e8`
- `0x180023dbc`
- `0x1800242d0`
- `0x18002463c`

## import_xrefs

- `SHLWAPI!PathFindFileNameW` at `0x180023dde`
- `SHLWAPI!PathFindFileNameW` at `0x180023dde`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall SendFileInfoToTelemetry(LPCWSTR lptstrFilename)
{
  const unsigned __int16 *FileNameW; // r14
  const unsigned __int16 *v3; // rdi
  const unsigned __int16 *FileVersion; // rsi
  __int64 v5; // rax
  const WCHAR *v6; // rax
  const unsigned __int16 *v7; // r8
  const unsigned __int16 *v8; // rcx
  const unsigned __int16 *v9; // rax
  const unsigned __int16 *v10; // rdx
  int v11; // r8d
  int v12; // r9d
  unsigned __int16 **v13; // rax
  unsigned __int16 **v14; // rax
  unsigned __int16 **v15; // rax
  unsigned __int16 **v16; // rax
  __int64 *v17; // rax
  __int16 *v18; // rdx
  int *v19; // rcx
  unsigned __int16 **v20; // rax
  unsigned __int16 **v21; // rax
  unsigned __int16 **v22; // rax
  unsigned __int16 **v23; // rax
  unsigned __int16 **v24; // rax
  unsigned __int16 **v25; // rax
  const char *v26; // r9
  unsigned __int16 *v27; // [rsp+28h] [rbp-210h]
  unsigned __int16 *v28; // [rsp+30h] [rbp-208h]
  const unsigned __int16 **v29; // [rsp+38h] [rbp-200h]
  const unsigned __int16 **v30; // [rsp+40h] [rbp-1F8h]
  unsigned __int16 ***v31; // [rsp+48h] [rbp-1F0h]
  void **v32; // [rsp+50h] [rbp-1E8h]
  __int64 *v33; // [rsp+58h] [rbp-1E0h]
  __int64 v34; // [rsp+60h] [rbp-1D8h] BYREF
  void *v35; // [rsp+68h] [rbp-1D0h] BYREF
  unsigned __int16 **v36; // [rsp+70h] [rbp-1C8h] BYREF
  const unsigned __int16 *v37; // [rsp+78h] [rbp-1C0h] BYREF
  const unsigned __int16 *v38; // [rsp+80h] [rbp-1B8h] BYREF
  unsigned __int16 **v39; // [rsp+88h] [rbp-1B0h] BYREF
  void *v40; // [rsp+90h] [rbp-1A8h] BYREF
  __int64 v41; // [rsp+98h] [rbp-1A0h] BYREF
  __int64 v42; // [rsp+A0h] [rbp-198h] BYREF
  unsigned __int16 *v43[3]; // [rsp+A8h] [rbp-190h] BYREF
  unsigned __int64 v44; // [rsp+C0h] [rbp-178h]
  _BYTE v45[32]; // [rsp+D0h] [rbp-168h] BYREF
  _QWORD v46[3]; // [rsp+F0h] [rbp-148h] BYREF
  unsigned __int64 v47; // [rsp+108h] [rbp-130h]
  unsigned __int16 *v48[3]; // [rsp+110h] [rbp-128h] BYREF
  unsigned __int64 v49; // [rsp+128h] [rbp-110h]
  unsigned __int16 *v50[3]; // [rsp+130h] [rbp-108h] BYREF
  unsigned __int64 v51; // [rsp+148h] [rbp-F0h]
  char v52[8]; // [rsp+150h] [rbp-E8h] BYREF
  unsigned __int16 *v53[3]; // [rsp+158h] [rbp-E0h] BYREF
  unsigned __int64 v54; // [rsp+170h] [rbp-C8h]
  _BYTE v55[32]; // [rsp+1C0h] [rbp-78h] BYREF
  _BYTE v56[32]; // [rsp+1E0h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+238h] [rbp+0h]

  FileNameW = PathFindFileNameW(lptstrFilename);
  try
  {
    GetAppFileInfo(&v42, lptstrFilename);
    v3 = &Class;
    if ( v42 )
      v3 = *(const unsigned __int16 **)(v42 + 48);
    std::wstring::wstring(v43, &Class);
    GetOriginalFileName(lptstrFilename, v43);
    FileVersion = GetFileVersion(lptstrFilename);
    v5 = std::wstring::wstring(v56, lptstrFilename);
    v6 = (const WCHAR *)std::operator+<unsigned short>(v55, v5, L":Zone.Identifier");
    GetMarkOfTheWebFromFile((__int64)v45, v6);
    std::wstring::_Tidy_deallocate(v55);
    std::wstring::_Tidy_deallocate(v56);
    GetAppFileCertInfo(v52, lptstrFilename);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsCoreInsteadOfMicrosoftTelemetry>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WindowsCoreInsteadOfMicrosoftTelemetry>::GetImpl'::`2'::impl) )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_FullHostUrlInSmartScreenInitializedTelemetry>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_FullHostUrlInSmartScreenInitializedTelemetry>::GetImpl'::`2'::impl) )
      {
        v7 = (const unsigned __int16 *)v53;
        if ( v54 > 7 )
          v7 = v53[0];
        v8 = (const unsigned __int16 *)v50;
        if ( v51 > 7 )
          v8 = v50[0];
        v9 = (const unsigned __int16 *)v48;
        if ( v49 > 7 )
          v9 = v48[0];
        v10 = (const unsigned __int16 *)v43;
        if ( v44 > 7 )
          v10 = v43[0];
        SendSmartScreenInitializedTelemetry(FileNameW, v10, FileVersion, v3, v9, v8, v7);
        goto LABEL_49;
      }
      if ( (unsigned int)dword_180038080 <= 5 || !(unsigned __int8)tlgKeywordOn(&dword_180038080, 0x800000000000LL) )
      {
LABEL_49:
        AUTHENTICODE_INFO::~AUTHENTICODE_INFO((AUTHENTICODE_INFO *)v52);
        MarkOfTheWeb::~MarkOfTheWeb((MarkOfTheWeb *)v45);
        std::wstring::_Tidy_deallocate(v43);
        wil::details::unique_storage<wil::details::resource_policy<_FILE_INFO *,long (*)(_FILE_INFO *),&long PicFreeFileInfo(_FILE_INFO *),wistd::integral_constant<unsigned __int64,0>,_FILE_INFO *,_FILE_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_FILE_INFO *,long (*)(_FILE_INFO *),&long PicFreeFileInfo(_FILE_INFO *),wistd::integral_constant<unsigned __int64,0>,_FILE_INFO *,_FILE_INFO *,0,std::nullptr_t>>(&v42);
        return;
      }
      v13 = v53;
      if ( v54 > 7 )
        v13 = (unsigned __int16 **)v53[0];
      v34 = (__int64)v13;
      v14 = v50;
      if ( v51 > 7 )
        v14 = (unsigned __int16 **)v50[0];
      v35 = v14;
      v15 = (unsigned __int16 **)v46;
      if ( v47 > 7 )
        v15 = (unsigned __int16 **)v46[0];
      v36 = v15;
      v37 = v3;
      v38 = FileVersion;
      v16 = v43;
      if ( v44 > 7 )
        v16 = (unsigned __int16 **)v43[0];
      v39 = v16;
      v40 = (void *)FileNameW;
      v41 = 0x80000000LL;
      v33 = &v34;
      v32 = &v35;
      v31 = &v36;
      v30 = &v37;
      v29 = &v38;
      v28 = (unsigned __int16 *)&v39;
      v27 = (unsigned __int16 *)&v40;
      v17 = &v41;
      v18 = &word_1800302D6;
      v19 = &dword_180038080;
    }
    else
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_FullHostUrlInSmartScreenInitializedTelemetry>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_FullHostUrlInSmartScreenInitializedTelemetry>::GetImpl'::`2'::impl) )
      {
        if ( (unsigned int)dword_1800380B8 <= 5 || !(unsigned __int8)tlgKeywordOn(&dword_1800380B8, 0x800000000000LL) )
          goto LABEL_49;
        v20 = v53;
        if ( v54 > 7 )
          v20 = (unsigned __int16 **)v53[0];
        v41 = (__int64)v20;
        v21 = v50;
        if ( v51 > 7 )
          v21 = (unsigned __int16 **)v50[0];
        v40 = v21;
        v22 = v48;
        if ( v49 > 7 )
          v22 = (unsigned __int16 **)v48[0];
        v18 = (__int16 *)&unk_180030248;
      }
      else
      {
        if ( (unsigned int)dword_1800380B8 <= 5 || !(unsigned __int8)tlgKeywordOn(&dword_1800380B8, 0x800000000000LL) )
          goto LABEL_49;
        v23 = v53;
        if ( v54 > 7 )
          v23 = (unsigned __int16 **)v53[0];
        v41 = (__int64)v23;
        v24 = v50;
        if ( v51 > 7 )
          v24 = (unsigned __int16 **)v50[0];
        v40 = v24;
        v22 = (unsigned __int16 **)v46;
        if ( v47 > 7 )
          v22 = (unsigned __int16 **)v46[0];
        v18 = word_1800301BA;
      }
      v39 = v22;
      v25 = v43;
      if ( v44 > 7 )
        v25 = (unsigned __int16 **)v43[0];
      v36 = v25;
      v34 = 0x80000000LL;
      v33 = &v41;
      v32 = &v40;
      v31 = &v39;
      v30 = &v38;
      v29 = &v37;
      v28 = (unsigned __int16 *)&v36;
      v27 = (unsigned __int16 *)&v35;
      v19 = &dword_1800380B8;
      v17 = &v34;
      v35 = (void *)FileNameW;
      v37 = FileVersion;
      v38 = v3;
    }
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (_DWORD)v19,
      (_DWORD)v18,
      v11,
      v12,
      (__int64)v17,
      (__int64)v27,
      (__int64)v28,
      (__int64)v29,
      (__int64)v30,
      (__int64)v31,
      (__int64)v32,
      (__int64)v33);
    goto LABEL_49;
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x357,
      (unsigned int)"shell\\shdocvw\\smartinst.cpp",
      v26);
  }
}

```

## disassembly

```asm
0x180023dbc  push    rbx
0x180023dbe  push    rsi
0x180023dbf  push    rdi
0x180023dc0  push    r14
0x180023dc2  sub     rsp, 218h
0x180023dc9  mov     rax, cs:__security_cookie
0x180023dd0  xor     rax, rsp
0x180023dd3  mov     [rsp+238h+var_38], rax
0x180023ddb  mov     rbx, rcx
0x180023dde  call    cs:__imp_PathFindFileNameW
0x180023de4  mov     r14, rax
0x180023de7  mov     rdx, rbx
0x180023dea  lea     rcx, [rsp+238h+var_198]
0x180023df2  call    ?GetAppFileInfo@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_FILE_INFO@@P6AJPEAU1@@Z$1?PicFreeFileInfo@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEBG@Z; GetAppFileInfo(ushort const *)
0x180023df7  nop
0x180023df8  mov     rcx, [rsp+238h+var_198]
0x180023e00  test    rcx, rcx
0x180023e03  lea     rdi, Class
0x180023e0a  jz      short loc_180023E10
0x180023e0c  mov     rdi, [rcx+30h]
0x180023e10  lea     rdx, Class
0x180023e17  lea     rcx, [rsp+238h+var_190]
0x180023e1f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180023e24  nop
0x180023e25  lea     rdx, [rsp+238h+var_190]
0x180023e2d  mov     rcx, rbx
0x180023e30  call    ?GetOriginalFileName@@YA_NPEBGPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GetOriginalFileName(ushort const *,std::wstring *)
0x180023e35  mov     rcx, rbx; lptstrFilename
0x180023e38  call    ?GetFileVersion@@YAPEBGPEBG@Z; GetFileVersion(ushort const *)
0x180023e3d  mov     rsi, rax
0x180023e40  mov     rdx, rbx
0x180023e43  lea     rcx, [rsp+238h+var_58]
0x180023e4b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180023e50  nop
0x180023e51  lea     r8, aZoneIdentifier; ":Zone.Identifier"
0x180023e58  mov     rdx, rax
0x180023e5b  lea     rcx, [rsp+238h+var_78]
0x180023e63  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x180023e68  nop
0x180023e69  mov     rdx, rax
0x180023e6c  lea     rcx, [rsp+238h+var_168]
0x180023e74  call    ?GetMarkOfTheWebFromFile@@YA?AUMarkOfTheWeb@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GetMarkOfTheWebFromFile(std::wstring const &)
0x180023e79  nop
0x180023e7a  lea     rcx, [rsp+238h+var_78]
0x180023e82  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180023e87  nop
0x180023e88  lea     rcx, [rsp+238h+var_58]
0x180023e90  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180023e95  mov     rdx, rbx
0x180023e98  lea     rcx, [rsp+238h+var_E8]
0x180023ea0  call    ?GetAppFileCertInfo@@YA?AUAUTHENTICODE_INFO@@PEBG@Z; GetAppFileCertInfo(ushort const *)
0x180023ea5  nop
0x180023ea6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WindowsCoreInsteadOfMicrosoftTelemetry@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsCoreInsteadOfMicrosoftTelemetry@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsCoreInsteadOfMicrosoftTelemetry> `wil::Feature<__WilFeatureTraits_Feature_WindowsCoreInsteadOfMicrosoftTelemetry>::GetImpl(void)'::`2'::impl
0x180023ead  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsCoreInsteadOfMicrosoftTelemetry@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsCoreInsteadOfMicrosoftTelemetry>::__private_IsEnabled(void)
0x180023eb2  test    al, al
0x180023eb4  jz      loc_180024090
0x180023eba  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_FullHostUrlInSmartScreenInitializedTelemetry@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_FullHostUrlInSmartScreenInitializedTelemetry@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FullHostUrlInSmartScreenInitializedTelemetry> `wil::Feature<__WilFeatureTraits_Feature_FullHostUrlInSmartScreenInitializedTelemetry>::GetImpl(void)'::`2'::impl
0x180023ec1  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_FullHostUrlInSmartScreenInitializedTelemetry@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FullHostUrlInSmartScreenInitializedTelemetry>::__private_IsEnabled(void)
0x180023ec6  test    al, al
0x180023ec8  jz      loc_180023F58
0x180023ece  lea     r8, [rsp+238h+var_E0]
0x180023ed6  cmp     [rsp+238h+var_C8], 7
0x180023edf  cmova   r8, [rsp+238h+var_E0]
0x180023ee8  lea     rcx, [rsp+238h+var_108]
0x180023ef0  cmp     [rsp+238h+var_F0], 7
0x180023ef9  cmova   rcx, [rsp+238h+var_108]
0x180023f02  lea     rax, [rsp+238h+var_128]
0x180023f0a  cmp     [rsp+238h+var_110], 7
0x180023f13  cmova   rax, [rsp+238h+var_128]
0x180023f1c  lea     rdx, [rsp+238h+var_190]
0x180023f24  cmp     [rsp+238h+var_178], 7
0x180023f2d  cmova   rdx, [rsp+238h+var_190]; unsigned __int16 *
0x180023f36  mov     [rsp+238h+var_208], r8; unsigned __int16 *
0x180023f3b  mov     [rsp+238h+var_210], rcx; unsigned __int16 *
0x180023f40  mov     [rsp+238h+var_218], rax; unsigned __int16 *
0x180023f45  mov     r9, rdi; unsigned __int16 *
0x180023f48  mov     r8, rsi; unsigned __int16 *
0x180023f4b  mov     rcx, r14; unsigned __int16 *
0x180023f4e  call    ?SendSmartScreenInitializedTelemetry@@YAXPEBG000000@Z; SendSmartScreenInitializedTelemetry(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x180023f53  jmp     loc_180024273
0x180023f58  mov     eax, cs:dword_180038080
0x180023f5e  cmp     eax, 5
0x180023f61  jbe     loc_180024273
0x180023f67  mov     rdx, 800000000000h
0x180023f71  lea     rcx, dword_180038080
0x180023f78  call    _tlgKeywordOn
0x180023f7d  test    al, al
0x180023f7f  jz      loc_180024273
0x180023f85  lea     rax, [rsp+238h+var_E0]
0x180023f8d  cmp     [rsp+238h+var_C8], 7
0x180023f96  cmova   rax, [rsp+238h+var_E0]
0x180023f9f  mov     [rsp+238h+var_1D8], rax
0x180023fa4  lea     rax, [rsp+238h+var_108]
0x180023fac  cmp     [rsp+238h+var_F0], 7
0x180023fb5  cmova   rax, [rsp+238h+var_108]
0x180023fbe  mov     [rsp+238h+var_1D0], rax
0x180023fc3  lea     rax, [rsp+238h+var_148]
0x180023fcb  cmp     [rsp+238h+var_130], 7
0x180023fd4  cmova   rax, [rsp+238h+var_148]
0x180023fdd  mov     [rsp+238h+var_1C8], rax
0x180023fe2  mov     [rsp+238h+var_1C0], rdi
0x180023fe7  mov     [rsp+238h+var_1B8], rsi
0x180023fef  lea     rax, [rsp+238h+var_190]
0x180023ff7  cmp     [rsp+238h+var_178], 7
0x180024000  cmova   rax, [rsp+238h+var_190]
0x180024009  mov     [rsp+238h+var_1B0], rax
0x180024011  mov     [rsp+238h+var_1A8], r14
0x180024019  mov     eax, 80000000h
0x18002401e  mov     [rsp+238h+var_1A0], rax
0x180024026  lea     rax, [rsp+238h+var_1D8]
0x18002402b  mov     [rsp+238h+var_1E0], rax
0x180024030  lea     rax, [rsp+238h+var_1D0]
0x180024035  mov     [rsp+238h+var_1E8], rax
0x18002403a  lea     rax, [rsp+238h+var_1C8]
0x18002403f  mov     [rsp+238h+var_1F0], rax
0x180024044  lea     rax, [rsp+238h+var_1C0]
0x180024049  mov     [rsp+238h+var_1F8], rax
0x18002404e  lea     rax, [rsp+238h+var_1B8]
0x180024056  mov     [rsp+238h+var_200], rax
0x18002405b  lea     rax, [rsp+238h+var_1B0]
0x180024063  mov     [rsp+238h+var_208], rax
0x180024068  lea     rax, [rsp+238h+var_1A8]
0x180024070  mov     [rsp+238h+var_210], rax
0x180024075  lea     rax, [rsp+238h+var_1A0]
0x18002407d  lea     rdx, word_1800302D6
0x180024084  lea     rcx, dword_180038080
0x18002408b  jmp     loc_180024268
0x180024090  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_FullHostUrlInSmartScreenInitializedTelemetry@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_FullHostUrlInSmartScreenInitializedTelemetry@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FullHostUrlInSmartScreenInitializedTelemetry> `wil::Feature<__WilFeatureTraits_Feature_FullHostUrlInSmartScreenInitializedTelemetry>::GetImpl(void)'::`2'::impl
0x180024097  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_FullHostUrlInSmartScreenInitializedTelemetry@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FullHostUrlInSmartScreenInitializedTelemetry>::__private_IsEnabled(void)
0x18002409c  test    al, al
0x18002409e  mov     eax, cs:dword_1800380B8
0x1800240a4  jz      loc_18002413B
0x1800240aa  cmp     eax, 5
0x1800240ad  jbe     loc_180024273
0x1800240b3  mov     rdx, 800000000000h
0x1800240bd  lea     rcx, dword_1800380B8
0x1800240c4  call    _tlgKeywordOn
0x1800240c9  test    al, al
0x1800240cb  jz      loc_180024273
0x1800240d1  lea     rax, [rsp+238h+var_E0]
0x1800240d9  cmp     [rsp+238h+var_C8], 7
0x1800240e2  cmova   rax, [rsp+238h+var_E0]
0x1800240eb  mov     [rsp+238h+var_1A0], rax
0x1800240f3  lea     rax, [rsp+238h+var_108]
0x1800240fb  cmp     [rsp+238h+var_F0], 7
0x180024104  cmova   rax, [rsp+238h+var_108]
0x18002410d  mov     [rsp+238h+var_1A8], rax
0x180024115  lea     rax, [rsp+238h+var_128]
0x18002411d  cmp     [rsp+238h+var_110], 7
0x180024126  cmova   rax, [rsp+238h+var_128]
0x18002412f  lea     rdx, unk_180030248
0x180024136  jmp     loc_1800241C7
0x18002413b  cmp     eax, 5
0x18002413e  jbe     loc_180024273
0x180024144  mov     rdx, 800000000000h
0x18002414e  lea     rcx, dword_1800380B8
0x180024155  call    _tlgKeywordOn
0x18002415a  test    al, al
0x18002415c  jz      loc_180024273
0x180024162  lea     rax, [rsp+238h+var_E0]
0x18002416a  cmp     [rsp+238h+var_C8], 7
0x180024173  cmova   rax, [rsp+238h+var_E0]
0x18002417c  mov     [rsp+238h+var_1A0], rax
0x180024184  lea     rax, [rsp+238h+var_108]
0x18002418c  cmp     [rsp+238h+var_F0], 7
0x180024195  cmova   rax, [rsp+238h+var_108]
0x18002419e  mov     [rsp+238h+var_1A8], rax
0x1800241a6  lea     rax, [rsp+238h+var_148]
0x1800241ae  cmp     [rsp+238h+var_130], 7
0x1800241b7  cmova   rax, [rsp+238h+var_148]
0x1800241c0  lea     rdx, word_1800301BA
0x1800241c7  mov     [rsp+238h+var_1B0], rax
0x1800241cf  lea     rax, [rsp+238h+var_190]
0x1800241d7  cmp     [rsp+238h+var_178], 7
0x1800241e0  cmova   rax, [rsp+238h+var_190]
0x1800241e9  mov     [rsp+238h+var_1C8], rax
0x1800241ee  mov     eax, 80000000h
0x1800241f3  mov     [rsp+238h+var_1D8], rax
0x1800241f8  lea     rax, [rsp+238h+var_1A0]
0x180024200  mov     [rsp+238h+var_1E0], rax
0x180024205  lea     rax, [rsp+238h+var_1A8]
0x18002420d  mov     [rsp+238h+var_1E8], rax
0x180024212  lea     rax, [rsp+238h+var_1B0]
0x18002421a  mov     [rsp+238h+var_1F0], rax
0x18002421f  lea     rax, [rsp+238h+var_1B8]
0x180024227  mov     [rsp+238h+var_1F8], rax
0x18002422c  lea     rax, [rsp+238h+var_1C0]
0x180024231  mov     [rsp+238h+var_200], rax
0x180024236  lea     rax, [rsp+238h+var_1C8]
0x18002423b  mov     [rsp+238h+var_208], rax
0x180024240  lea     rax, [rsp+238h+var_1D0]
0x180024245  mov     [rsp+238h+var_210], rax
0x18002424a  lea     rcx, dword_1800380B8
0x180024251  lea     rax, [rsp+238h+var_1D8]
0x180024256  mov     [rsp+238h+var_1D0], r14
0x18002425b  mov     [rsp+238h+var_1C0], rsi
0x180024260  mov     [rsp+238h+var_1B8], rdi
0x180024268  mov     [rsp+238h+var_218], rax
0x18002426d  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U2@U2@U2@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@444444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x180024272  nop
0x180024273  lea     rcx, [rsp+238h+var_E8]; this
0x18002427b  call    ??1AUTHENTICODE_INFO@@QEAA@XZ; AUTHENTICODE_INFO::~AUTHENTICODE_INFO(void)
0x180024280  nop
0x180024281  lea     rcx, [rsp+238h+var_168]; this
0x180024289  call    ??1MarkOfTheWeb@@QEAA@XZ; MarkOfTheWeb::~MarkOfTheWeb(void)
0x18002428e  nop
0x18002428f  lea     rcx, [rsp+238h+var_190]
0x180024297  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002429c  nop
0x18002429d  lea     rcx, [rsp+238h+var_198]
0x1800242a5  call    ??1?$unique_storage@U?$resource_policy@PEAU_FILE_INFO@@P6AJPEAU1@@Z$1?PicFreeFileInfo@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_FILE_INFO *,long (*)(_FILE_INFO *),&PicFreeFileInfo(_FILE_INFO *),wistd::integral_constant<unsigned __int64,0>,_FILE_INFO *,_FILE_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_FILE_INFO *,long (*)(_FILE_INFO *),&PicFreeFileInfo(_FILE_INFO *),wistd::integral_constant<unsigned __int64,0>,_FILE_INFO *,_FILE_INFO *,0,std::nullptr_t>>(void)
0x1800242aa  nop
0x1800242ab  mov     rcx, [rsp+238h+var_38]
0x1800242b3  xor     rcx, rsp; StackCookie
0x1800242b6  call    __security_check_cookie
0x1800242bb  add     rsp, 218h
0x1800242c2  pop     r14
0x1800242c4  pop     rdi
0x1800242c5  pop     rsi
0x1800242c6  pop     rbx
0x1800242c7  retn
```
