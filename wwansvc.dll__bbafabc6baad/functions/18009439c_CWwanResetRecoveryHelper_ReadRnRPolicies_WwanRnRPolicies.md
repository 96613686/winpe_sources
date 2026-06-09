# CWwanResetRecoveryHelper::_ReadRnRPolicies(WwanRnRPolicies &)

- ea: `0x18009439c`
- end: `0x180094ad3`
- name: `?_ReadRnRPolicies@CWwanResetRecoveryHelper@@SAXAEAUWwanRnRPolicies@@@Z`
- size: `1847`
- prototype: `void __fastcall(struct WwanRnRPolicies *)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config`

## callers

- `0x180077224`

## callees

- `0x1800085d0`
- `0x180008abc`
- `0x180010f10`
- `0x1800117a8`
- `0x180011a1c`
- `0x180012300`
- `0x180013288`
- `0x180013588`
- `0x180014154`
- `0x180014b5c`
- `0x180014f1c`
- `0x1800317b4`
- `0x180093a84`
- `0x180093b10`
- `0x180093b9c`
- `0x180093c28`
- `0x180093cb4`
- `0x18009439c`

## string_xrefs

- `0x18009448d`: `RnR Support is not configured in Registry`
- `0x1800944ae`: `Registry Lookup for RnR support failed 0x%x`
- `0x180094496`: `CWwanResetRecoveryHelper::_ReadRnRPolicies`
- `0x1800944b7`: `CWwanResetRecoveryHelper::_ReadRnRPolicies`
- `0x1800944f6`: `CWwanResetRecoveryHelper::_ReadRnRPolicies`
- `0x1800944ed`: `Registry Lookup for RnR support succeeded (RnREnabled: 0x%x) fRnREnabled %d fRnRForcedDisablement %d`
- `0x180094812`: `Registry Lookup for PLDR support failed 0x%x`
- `0x1800947f8`: `PLDR Support is not configured in Registry`
- `0x1800948fe`: `Reg sub path or value of RSSI threshold configuration (%s) not present`
- `0x18009484c`: `Registry Lookup for PLDR support succeeded (0x%x) fRnRUsePLDR %d fRnRPLDRForcedDisablement %d`
- `0x18009492c`: `RSSI threshold configuration (%s) contains invalid data %d`
- `0x180094914`: `failed to read RSSI threshold configuration (%s), error 0x%x`
- `0x1800949f9`: `Reg sub path or value of DisregardDeviceResetCapabilities configuration (%s) not present. Set it to TRUE`
- `0x180094942`: `RSSI threshold configuration %d read at (%s)`
- `0x180094a2a`: `DisregardDeviceResetCapabilities configuration (%s) contains invalid data %d`
- `0x180094a13`: `failed to read DisregardDeviceResetCapabilities configuration (%s), error 0x%x`
- `0x180094a40`: `DisregardDeviceResetCapabilities configuration %d read at (%s)`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall CWwanResetRecoveryHelper::_ReadRnRPolicies(struct WwanRnRPolicies *a1)
{
  void *v2; // rax
  StateSeparation *v3; // r14
  __int64 v4; // rbx
  __int64 v5; // rax
  __int64 v6; // rax
  __int64 v7; // rax
  const unsigned __int16 *v8; // rax
  unsigned int DWORD; // ebx
  __int64 v10; // rdx
  __int64 v11; // rbx
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  const unsigned __int16 *v15; // rax
  __int64 v16; // rbx
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  const unsigned __int16 *v20; // rax
  __int64 v21; // rbx
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rax
  const unsigned __int16 *v25; // rax
  __int64 v26; // rbx
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v29; // rax
  const unsigned __int16 *v30; // rax
  __int64 v31; // rbx
  __int64 v32; // rax
  __int64 v33; // rax
  __int64 v34; // rax
  const unsigned __int16 *v35; // rax
  unsigned int v36; // ebx
  __int64 v37; // rbx
  __int64 v38; // rax
  __int64 v39; // rax
  __int64 v40; // rax
  const unsigned __int16 *v41; // rax
  unsigned int v42; // ebx
  __int64 v43; // rbx
  __int64 v44; // rax
  __int64 v45; // rax
  __int64 v46; // rax
  const unsigned __int16 *v47; // rax
  unsigned int v48; // ebx
  __int64 v49; // rdx
  __int64 v50; // rdx
  __int64 v51; // rdx
  __int64 v52; // rdx
  const unsigned __int16 *v53; // [rsp+20h] [rbp-79h]
  unsigned int v54; // [rsp+30h] [rbp-69h] BYREF
  unsigned int v55; // [rsp+34h] [rbp-65h] BYREF
  unsigned int v56; // [rsp+38h] [rbp-61h] BYREF
  StateSeparation *v57; // [rsp+40h] [rbp-59h] BYREF
  _BYTE v58[32]; // [rsp+48h] [rbp-51h] BYREF
  _BYTE v59[32]; // [rsp+68h] [rbp-31h] BYREF
  _BYTE v60[32]; // [rsp+88h] [rbp-11h] BYREF
  _BYTE v61[32]; // [rsp+A8h] [rbp+Fh] BYREF

  v2 = operator new(0x20u);
  v3 = (StateSeparation *)StateSeparation::StateSeparation((__int64)v2);
  v57 = v3;
  v54 = 0;
  v4 = std::wstring::wstring((__int64)v61, (__int64)L"Policies");
  v5 = std::wstring::wstring((__int64)v60, (__int64)L"RnR");
  v6 = std::operator+<unsigned short>(v59, v5, L"\\");
  v7 = std::operator+<unsigned short>(v58, v6, v4);
  v8 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v7);
  DWORD = StateSeparation::GetDWORD(v3, v8, L"RnREnabled", &v54);
  std::wstring::_Tidy_deallocate(v58);
  std::wstring::_Tidy_deallocate(v59);
  std::wstring::_Tidy_deallocate(v60);
  std::wstring::_Tidy_deallocate(v61);
  if ( DWORD == 2 )
  {
    WwanLog::Info("CWwanResetRecoveryHelper::_ReadRnRPolicies", 0, L"RnR Support is not configured in Registry");
  }
  else if ( DWORD )
  {
    WwanLog::Error(
      "CWwanResetRecoveryHelper::_ReadRnRPolicies",
      0,
      L"Registry Lookup for RnR support failed 0x%x",
      DWORD);
  }
  else
  {
    if ( v54 == 1 )
    {
      *((_DWORD *)a1 + 2) = 1;
    }
    else if ( v54 == 2 )
    {
      *(_DWORD *)a1 = 1;
    }
    WwanLog::Info(
      "CWwanResetRecoveryHelper::_ReadRnRPolicies",
      0,
      L"Registry Lookup for RnR support succeeded (RnREnabled: 0x%x) fRnREnabled %d fRnRForcedDisablement %d");
  }
  LOBYTE(v10) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_RnR_MBB>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_RnR_MBB>::GetImpl'::`2'::impl,
    v10);
  *((_DWORD *)a1 + 8) = 1;
  WwanLog::Info("CWwanResetRecoveryHelper::_ReadRnRPolicies", 0, L"Enabling RnR through Coin Velocity");
  if ( !*(_DWORD *)a1 && (*((_DWORD *)a1 + 2) || *((_DWORD *)a1 + 8)) )
  {
    v11 = std::wstring::wstring((__int64)v58, (__int64)L"Policies");
    v12 = std::wstring::wstring((__int64)v59, (__int64)L"RnR");
    v13 = std::operator+<unsigned short>(v60, v12, L"\\");
    v14 = std::operator+<unsigned short>(v61, v13, v11);
    v15 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v14);
    StateSeparation::GetDWORD(v3, v15, L"PDPContextResetEnabled", (unsigned int *)a1 + 3);
    std::wstring::_Tidy_deallocate(v61);
    std::wstring::_Tidy_deallocate(v60);
    std::wstring::_Tidy_deallocate(v59);
    std::wstring::_Tidy_deallocate(v58);
    v16 = std::wstring::wstring((__int64)v58, (__int64)L"Policies");
    v17 = std::wstring::wstring((__int64)v59, (__int64)L"RnR");
    v18 = std::operator+<unsigned short>(v60, v17, L"\\");
    v19 = std::operator+<unsigned short>(v61, v18, v16);
    v20 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v19);
    StateSeparation::GetDWORD(v3, v20, L"APMTogglingEnabled", (unsigned int *)a1 + 4);
    std::wstring::_Tidy_deallocate(v61);
    std::wstring::_Tidy_deallocate(v60);
    std::wstring::_Tidy_deallocate(v59);
    std::wstring::_Tidy_deallocate(v58);
    v21 = std::wstring::wstring((__int64)v58, (__int64)L"Policies");
    v22 = std::wstring::wstring((__int64)v59, (__int64)L"RnR");
    v23 = std::operator+<unsigned short>(v60, v22, L"\\");
    v24 = std::operator+<unsigned short>(v61, v23, v21);
    v25 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v24);
    StateSeparation::GetDWORD(v3, v25, L"PnPRestartEnabled", (unsigned int *)a1 + 5);
    std::wstring::_Tidy_deallocate(v61);
    std::wstring::_Tidy_deallocate(v60);
    std::wstring::_Tidy_deallocate(v59);
    std::wstring::_Tidy_deallocate(v58);
    v26 = std::wstring::wstring((__int64)v58, (__int64)L"Policies");
    v27 = std::wstring::wstring((__int64)v59, (__int64)L"RnR");
    v28 = std::operator+<unsigned short>(v60, v27, L"\\");
    v29 = std::operator+<unsigned short>(v61, v28, v26);
    v30 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v29);
    StateSeparation::GetDWORD(v3, v30, L"FLDREnabled", (unsigned int *)a1 + 6);
    std::wstring::_Tidy_deallocate(v61);
    std::wstring::_Tidy_deallocate(v60);
    std::wstring::_Tidy_deallocate(v59);
    std::wstring::_Tidy_deallocate(v58);
    v54 = 0;
    v31 = std::wstring::wstring((__int64)v58, (__int64)L"Policies");
    v32 = std::wstring::wstring((__int64)v59, (__int64)L"RnR");
    v33 = std::operator+<unsigned short>(v60, v32, L"\\");
    v34 = std::operator+<unsigned short>(v61, v33, v31);
    v35 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v34);
    v36 = StateSeparation::GetDWORD(v3, v35, L"PLDREnabled", &v54);
    std::wstring::_Tidy_deallocate(v61);
    std::wstring::_Tidy_deallocate(v60);
    std::wstring::_Tidy_deallocate(v59);
    std::wstring::_Tidy_deallocate(v58);
    if ( v36 == 2 )
    {
      WwanLog::Info("CWwanResetRecoveryHelper::_ReadRnRPolicies", 0, L"PLDR Support is not configured in Registry");
    }
    else if ( v36 )
    {
      WwanLog::Error(
        "CWwanResetRecoveryHelper::_ReadRnRPolicies",
        0,
        L"Registry Lookup for PLDR support failed 0x%x",
        v36);
    }
    else
    {
      if ( v54 == 1 )
      {
        *((_DWORD *)a1 + 7) = 1;
      }
      else if ( v54 == 2 )
      {
        *((_DWORD *)a1 + 1) = 1;
      }
      WwanLog::Info(
        "CWwanResetRecoveryHelper::_ReadRnRPolicies",
        0,
        L"Registry Lookup for PLDR support succeeded (0x%x) fRnRUsePLDR %d fRnRPLDRForcedDisablement %d");
    }
    v55 = 0;
    v37 = std::wstring::wstring((__int64)v58, (__int64)L"Policies");
    v38 = std::wstring::wstring((__int64)v59, (__int64)L"RnR");
    v39 = std::operator+<unsigned short>(v60, v38, L"\\");
    v40 = std::operator+<unsigned short>(v61, v39, v37);
    v41 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v40);
    v42 = StateSeparation::GetDWORD(v3, v41, L"RssiThreshold", &v55);
    std::wstring::_Tidy_deallocate(v61);
    std::wstring::_Tidy_deallocate(v60);
    std::wstring::_Tidy_deallocate(v59);
    std::wstring::_Tidy_deallocate(v58);
    if ( v42 == 2 )
    {
      WwanLog::Info(
        "CWwanResetRecoveryHelper::_ReadRnRPolicies",
        0,
        L"Reg sub path or value of RSSI threshold configuration (%s) not present",
        L"RssiThreshold");
    }
    else if ( v42 )
    {
      WwanLog::Error(
        "CWwanResetRecoveryHelper::_ReadRnRPolicies",
        0,
        L"failed to read RSSI threshold configuration (%s), error 0x%x",
        L"RssiThreshold",
        v42);
    }
    else if ( v55 <= 0x1F )
    {
      v53 = L"RssiThreshold";
      WwanLog::Info("CWwanResetRecoveryHelper::_ReadRnRPolicies", 0, L"RSSI threshold configuration %d read at (%s)");
      *((_DWORD *)a1 + 14) = v55;
    }
    else
    {
      WwanLog::Error(
        "CWwanResetRecoveryHelper::_ReadRnRPolicies",
        0,
        L"RSSI threshold configuration (%s) contains invalid data %d",
        L"RssiThreshold",
        v55);
    }
    v56 = 0;
    v43 = std::wstring::wstring((__int64)v58, (__int64)L"Policies");
    v44 = std::wstring::wstring((__int64)v59, (__int64)L"RnR");
    v45 = std::operator+<unsigned short>(v60, v44, L"\\");
    v46 = std::operator+<unsigned short>(v61, v45, v43);
    v47 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v46);
    v48 = StateSeparation::GetDWORD(v3, v47, L"DisregardDeviceResetCapabilities", &v56);
    std::wstring::_Tidy_deallocate(v61);
    std::wstring::_Tidy_deallocate(v60);
    std::wstring::_Tidy_deallocate(v59);
    std::wstring::_Tidy_deallocate(v58);
    if ( v48 == 2 )
    {
      WwanLog::Info(
        "CWwanResetRecoveryHelper::_ReadRnRPolicies",
        0,
        L"Reg sub path or value of DisregardDeviceResetCapabilities configuration (%s) not present. Set it to TRUE",
        L"DisregardDeviceResetCapabilities");
      *((_DWORD *)a1 + 15) = 1;
    }
    else if ( v48 )
    {
      LODWORD(v53) = v48;
      WwanLog::Error(
        "CWwanResetRecoveryHelper::_ReadRnRPolicies",
        0,
        L"failed to read DisregardDeviceResetCapabilities configuration (%s), error 0x%x",
        L"DisregardDeviceResetCapabilities",
        v53);
    }
    else if ( v56 <= 1 )
    {
      WwanLog::Info(
        "CWwanResetRecoveryHelper::_ReadRnRPolicies",
        0,
        L"DisregardDeviceResetCapabilities configuration %d read at (%s)");
      *((_DWORD *)a1 + 15) = v56;
    }
    else
    {
      LODWORD(v53) = v56;
      WwanLog::Error(
        "CWwanResetRecoveryHelper::_ReadRnRPolicies",
        0,
        L"DisregardDeviceResetCapabilities configuration (%s) contains invalid data %d",
        L"DisregardDeviceResetCapabilities",
        v53);
    }
    LOBYTE(v49) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_RnR_PDPReset>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_RnR_PDPReset>::GetImpl'::`2'::impl,
      v49);
    *((_DWORD *)a1 + 9) = 1;
    LOBYTE(v50) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_RnR_APMToggling>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_RnR_APMToggling>::GetImpl'::`2'::impl,
      v50);
    *((_DWORD *)a1 + 10) = 1;
    LOBYTE(v51) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_RnR_PnPDisableEnable>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_RnR_PnPDisableEnable>::GetImpl'::`2'::impl,
      v51);
    *(_QWORD *)((char *)a1 + 44) = 1;
    LOBYTE(v52) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_RnR_PLDR>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_RnR_PLDR>::GetImpl'::`2'::impl,
      v52);
    *((_DWORD *)a1 + 13) = 1;
  }
  std::unique_ptr<StateSeparation>::~unique_ptr<StateSeparation>(&v57);
}

```

## disassembly

```asm
0x18009439c  mov     [rsp-8+arg_8], rbx
0x1800943a1  mov     [rsp-8+arg_10], rsi
0x1800943a6  push    rbp
0x1800943a7  push    rdi
0x1800943a8  push    r13
0x1800943aa  push    r14
0x1800943ac  push    r15
0x1800943ae  lea     rbp, [rsp-37h]
0x1800943b3  sub     rsp, 0D0h
0x1800943ba  mov     rax, cs:__security_cookie
0x1800943c1  xor     rax, rsp
0x1800943c4  mov     [rbp+57h+var_28], rax
0x1800943c8  mov     rdi, rcx
0x1800943cb  mov     ecx, 20h ; ' '; Size
0x1800943d0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800943d5  mov     [rbp+57h+var_B0], rax
0x1800943d9  xor     edx, edx
0x1800943db  mov     rcx, rax
0x1800943de  call    ??0StateSeparation@@QEAA@W4_REG_ROOT_PATH@@@Z; StateSeparation::StateSeparation(_REG_ROOT_PATH)
0x1800943e3  mov     r14, rax
0x1800943e6  mov     [rbp+57h+var_B0], rax
0x1800943ea  mov     [rbp+57h+var_C0], 0
0x1800943f1  lea     r13, aPolicies; "Policies"
0x1800943f8  mov     rdx, r13
0x1800943fb  lea     rcx, [rbp+57h+var_48]
0x1800943ff  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180094404  mov     rbx, rax
0x180094407  lea     rdx, aRnr; "RnR"
0x18009440e  lea     rcx, [rbp+57h+var_68]
0x180094412  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180094417  nop
0x180094418  lea     r8, SubBlock; "\\"
0x18009441f  mov     rdx, rax
0x180094422  lea     rcx, [rbp+57h+var_88]
0x180094426  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x18009442b  nop
0x18009442c  mov     r8, rbx
0x18009442f  mov     rdx, rax
0x180094432  lea     rcx, [rbp+57h+var_A8]
0x180094436  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@0@Z; std::operator+<ushort>(std::wstring &&,std::wstring &&)
0x18009443b  mov     rcx, rax
0x18009443e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180094443  lea     r9, [rbp+57h+var_C0]; unsigned int *
0x180094447  lea     r8, aRnrenabled; "RnREnabled"
0x18009444e  mov     rdx, rax; unsigned __int16 *
0x180094451  mov     rcx, r14; this
0x180094454  call    ?GetDWORD@StateSeparation@@QEAAKPEBG0PEAK@Z; StateSeparation::GetDWORD(ushort const *,ushort const *,ulong *)
0x180094459  mov     ebx, eax
0x18009445b  lea     rcx, [rbp+57h+var_A8]
0x18009445f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180094464  nop
0x180094465  lea     rcx, [rbp+57h+var_88]
0x180094469  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18009446e  nop
0x18009446f  lea     rcx, [rbp+57h+var_68]
0x180094473  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180094478  nop
0x180094479  lea     rcx, [rbp+57h+var_48]
0x18009447d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180094482  mov     r15d, 1
0x180094488  cmp     ebx, 2
0x18009448b  jnz     short loc_1800944A7
0x18009448d  lea     r8, aRnrSupportIsNo; "RnR Support is not configured in Regist"...
0x180094494  xor     edx, edx; struct _GUID *
0x180094496  lea     rsi, aCwwanresetreco_26; "CWwanResetRecoveryHelper::_ReadRnRPolic"...
0x18009449d  mov     rcx, rsi; char *
0x1800944a0  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x1800944a5  jmp     short loc_180094505
0x1800944a7  test    ebx, ebx
0x1800944a9  jz      short loc_1800944C8
0x1800944ab  mov     r9d, ebx
0x1800944ae  lea     r8, aRegistryLookup_0; "Registry Lookup for RnR support failed "...
0x1800944b5  xor     edx, edx; struct _GUID *
0x1800944b7  lea     rsi, aCwwanresetreco_26; "CWwanResetRecoveryHelper::_ReadRnRPolic"...
0x1800944be  mov     rcx, rsi; char *
0x1800944c1  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800944c6  jmp     short loc_180094505
0x1800944c8  mov     r9d, [rbp+57h+var_C0]
0x1800944cc  cmp     r9d, r15d
0x1800944cf  jnz     short loc_1800944D7
0x1800944d1  mov     [rdi+8], r15d
0x1800944d5  jmp     short loc_1800944E0
0x1800944d7  cmp     r9d, 2
0x1800944db  jnz     short loc_1800944E0
0x1800944dd  mov     [rdi], r15d
0x1800944e0  mov     eax, [rdi]
0x1800944e2  mov     [rsp+0F0h+var_C8], eax
0x1800944e6  mov     eax, [rdi+8]
0x1800944e9  mov     dword ptr [rsp+0F0h+var_D0], eax
0x1800944ed  lea     r8, aRegistryLookup; "Registry Lookup for RnR support succeed"...
0x1800944f4  xor     edx, edx; struct _GUID *
0x1800944f6  lea     rsi, aCwwanresetreco_26; "CWwanResetRecoveryHelper::_ReadRnRPolic"...
0x1800944fd  mov     rcx, rsi; char *
0x180094500  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x180094505  mov     dl, r15b
0x180094508  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_RnR_MBB@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_RnR_MBB@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RnR_MBB> `wil::Feature<__WilFeatureTraits_Feature_RnR_MBB>::GetImpl(void)'::`2'::impl
0x18009450f  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_RnR_MBB@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RnR_MBB>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180094514  mov     [rdi+20h], r15d
0x180094518  lea     r8, aEnablingRnrThr; "Enabling RnR through Coin Velocity"
0x18009451f  xor     edx, edx; struct _GUID *
0x180094521  mov     rcx, rsi; char *
0x180094524  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x180094529  cmp     dword ptr [rdi], 0
0x18009452c  jnz     loc_180094AA2
0x180094532  cmp     dword ptr [rdi+8], 0
0x180094536  jnz     short loc_180094542
0x180094538  cmp     dword ptr [rdi+20h], 0
0x18009453c  jz      loc_180094AA2
0x180094542  mov     rdx, r13
0x180094545  lea     rcx, [rbp+57h+var_A8]
0x180094549  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18009454e  mov     rbx, rax
0x180094551  lea     rdx, aRnr; "RnR"
0x180094558  lea     rcx, [rbp+57h+var_88]
0x18009455c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180094561  nop
0x180094562  lea     r8, SubBlock; "\\"
0x180094569  mov     rdx, rax
0x18009456c  lea     rcx, [rbp+57h+var_68]
0x180094570  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x180094575  nop
0x180094576  mov     r8, rbx
0x180094579  mov     rdx, rax
0x18009457c  lea     rcx, [rbp+57h+var_48]
0x180094580  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@0@Z; std::operator+<ushort>(std::wstring &&,std::wstring &&)
0x180094585  mov     rcx, rax
0x180094588  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18009458d  lea     r9, [rdi+0Ch]; unsigned int *
0x180094591  lea     r8, aPdpcontextrese; "PDPContextResetEnabled"
0x180094598  mov     rdx, rax; unsigned __int16 *
0x18009459b  mov     rcx, r14; this
0x18009459e  call    ?GetDWORD@StateSeparation@@QEAAKPEBG0PEAK@Z; StateSeparation::GetDWORD(ushort const *,ushort const *,ulong *)
0x1800945a3  lea     rcx, [rbp+57h+var_48]
0x1800945a7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800945ac  nop
0x1800945ad  lea     rcx, [rbp+57h+var_68]
0x1800945b1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800945b6  nop
0x1800945b7  lea     rcx, [rbp+57h+var_88]
0x1800945bb  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800945c0  nop
0x1800945c1  lea     rcx, [rbp+57h+var_A8]
0x1800945c5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800945ca  mov     rdx, r13
0x1800945cd  lea     rcx, [rbp+57h+var_A8]
0x1800945d1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800945d6  mov     rbx, rax
0x1800945d9  lea     rdx, aRnr; "RnR"
0x1800945e0  lea     rcx, [rbp+57h+var_88]
0x1800945e4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800945e9  nop
0x1800945ea  lea     r8, SubBlock; "\\"
0x1800945f1  mov     rdx, rax
0x1800945f4  lea     rcx, [rbp+57h+var_68]
0x1800945f8  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x1800945fd  nop
0x1800945fe  mov     r8, rbx
0x180094601  mov     rdx, rax
0x180094604  lea     rcx, [rbp+57h+var_48]
0x180094608  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@0@Z; std::operator+<ushort>(std::wstring &&,std::wstring &&)
0x18009460d  mov     rcx, rax
0x180094610  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180094615  lea     r9, [rdi+10h]; unsigned int *
0x180094619  lea     r8, aApmtogglingena; "APMTogglingEnabled"
0x180094620  mov     rdx, rax; unsigned __int16 *
0x180094623  mov     rcx, r14; this
0x180094626  call    ?GetDWORD@StateSeparation@@QEAAKPEBG0PEAK@Z; StateSeparation::GetDWORD(ushort const *,ushort const *,ulong *)
0x18009462b  lea     rcx, [rbp+57h+var_48]
0x18009462f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180094634  nop
0x180094635  lea     rcx, [rbp+57h+var_68]
0x180094639  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18009463e  nop
0x18009463f  lea     rcx, [rbp+57h+var_88]
0x180094643  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180094648  nop
0x180094649  lea     rcx, [rbp+57h+var_A8]
0x18009464d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180094652  mov     rdx, r13
0x180094655  lea     rcx, [rbp+57h+var_A8]
0x180094659  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18009465e  mov     rbx, rax
0x180094661  lea     rdx, aRnr; "RnR"
0x180094668  lea     rcx, [rbp+57h+var_88]
0x18009466c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180094671  nop
0x180094672  lea     r8, SubBlock; "\\"
0x180094679  mov     rdx, rax
0x18009467c  lea     rcx, [rbp+57h+var_68]
0x180094680  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x180094685  nop
0x180094686  mov     r8, rbx
0x180094689  mov     rdx, rax
0x18009468c  lea     rcx, [rbp+57h+var_48]
0x180094690  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@0@Z; std::operator+<ushort>(std::wstring &&,std::wstring &&)
0x180094695  mov     rcx, rax
0x180094698  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18009469d  lea     r9, [rdi+14h]; unsigned int *
0x1800946a1  lea     r8, aPnprestartenab; "PnPRestartEnabled"
0x1800946a8  mov     rdx, rax; unsigned __int16 *
0x1800946ab  mov     rcx, r14; this
0x1800946ae  call    ?GetDWORD@StateSeparation@@QEAAKPEBG0PEAK@Z; StateSeparation::GetDWORD(ushort const *,ushort const *,ulong *)
0x1800946b3  lea     rcx, [rbp+57h+var_48]
0x1800946b7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800946bc  nop
0x1800946bd  lea     rcx, [rbp+57h+var_68]
0x1800946c1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800946c6  nop
0x1800946c7  lea     rcx, [rbp+57h+var_88]
0x1800946cb  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800946d0  nop
0x1800946d1  lea     rcx, [rbp+57h+var_A8]
0x1800946d5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800946da  mov     rdx, r13
0x1800946dd  lea     rcx, [rbp+57h+var_A8]
0x1800946e1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800946e6  mov     rbx, rax
0x1800946e9  lea     rdx, aRnr; "RnR"
0x1800946f0  lea     rcx, [rbp+57h+var_88]
0x1800946f4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800946f9  nop
0x1800946fa  lea     r8, SubBlock; "\\"
0x180094701  mov     rdx, rax
0x180094704  lea     rcx, [rbp+57h+var_68]
0x180094708  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x18009470d  nop
0x18009470e  mov     r8, rbx
0x180094711  mov     rdx, rax
0x180094714  lea     rcx, [rbp+57h+var_48]
0x180094718  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@0@Z; std::operator+<ushort>(std::wstring &&,std::wstring &&)
0x18009471d  mov     rcx, rax
0x180094720  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180094725  lea     r9, [rdi+18h]; unsigned int *
0x180094729  lea     r8, aFldrenabled; "FLDREnabled"
0x180094730  mov     rdx, rax; unsigned __int16 *
0x180094733  mov     rcx, r14; this
0x180094736  call    ?GetDWORD@StateSeparation@@QEAAKPEBG0PEAK@Z; StateSeparation::GetDWORD(ushort const *,ushort const *,ulong *)
0x18009473b  lea     rcx, [rbp+57h+var_48]
0x18009473f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180094744  nop
0x180094745  lea     rcx, [rbp+57h+var_68]
0x180094749  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18009474e  nop
0x18009474f  lea     rcx, [rbp+57h+var_88]
0x180094753  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180094758  nop
0x180094759  lea     rcx, [rbp+57h+var_A8]
0x18009475d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180094762  mov     [rbp+57h+var_C0], 0
0x180094769  mov     rdx, r13
0x18009476c  lea     rcx, [rbp+57h+var_A8]
0x180094770  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180094775  mov     rbx, rax
0x180094778  lea     rdx, aRnr; "RnR"
0x18009477f  lea     rcx, [rbp+57h+var_88]
0x180094783  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180094788  nop
0x180094789  lea     r8, SubBlock; "\\"
0x180094790  mov     rdx, rax
0x180094793  lea     rcx, [rbp+57h+var_68]
0x180094797  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x18009479c  nop
0x18009479d  mov     r8, rbx
0x1800947a0  mov     rdx, rax
0x1800947a3  lea     rcx, [rbp+57h+var_48]
0x1800947a7  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@0@Z; std::operator+<ushort>(std::wstring &&,std::wstring &&)
0x1800947ac  mov     rcx, rax
0x1800947af  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800947b4  lea     r9, [rbp+57h+var_C0]; unsigned int *
0x1800947b8  lea     r8, aPldrenabled; "PLDREnabled"
0x1800947bf  mov     rdx, rax; unsigned __int16 *
0x1800947c2  mov     rcx, r14; this
0x1800947c5  call    ?GetDWORD@StateSeparation@@QEAAKPEBG0PEAK@Z; StateSeparation::GetDWORD(ushort const *,ushort const *,ulong *)
0x1800947ca  mov     ebx, eax
0x1800947cc  lea     rcx, [rbp+57h+var_48]
0x1800947d0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800947d5  nop
0x1800947d6  lea     rcx, [rbp+57h+var_68]
0x1800947da  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800947df  nop
0x1800947e0  lea     rcx, [rbp+57h+var_88]
0x1800947e4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800947e9  nop
0x1800947ea  lea     rcx, [rbp+57h+var_A8]
0x1800947ee  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800947f3  cmp     ebx, 2
0x1800947f6  jnz     short loc_18009480B
0x1800947f8  lea     r8, aPldrSupportIsN; "PLDR Support is not configured in Regis"...
0x1800947ff  xor     edx, edx; struct _GUID *
0x180094801  mov     rcx, rsi; char *
0x180094804  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x180094809  jmp     short loc_18009485D
0x18009480b  test    ebx, ebx
0x18009480d  jz      short loc_180094825
0x18009480f  mov     r9d, ebx
0x180094812  lea     r8, aRegistryLookup_2; "Registry Lookup for PLDR support failed"...
0x180094819  xor     edx, edx; struct _GUID *
0x18009481b  mov     rcx, rsi; char *
0x18009481e  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x180094823  jmp     short loc_18009485D
  ... truncated ...
```
