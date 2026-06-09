# CEssStateManager::ProcessEssChange(void)

- ea: `0x180073538`
- end: `0x180073b86`
- name: `?ProcessEssChange@CEssStateManager@@SAXXZ`
- size: `1614`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `40`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180073b8c`

## callees

- `0x180001314`
- `0x1800013a4`
- `0x180001434`
- `0x1800119c4`
- `0x180014110`
- `0x180014854`
- `0x180014894`
- `0x180023d88`
- `0x180026b28`
- `0x180027438`
- `0x18002de8c`
- `0x18003b80c`
- `0x18003f2dc`
- `0x180044b1c`
- `0x180046664`
- `0x180051284`
- `0x180052f44`
- `0x1800530c4`
- `0x180055878`
- `0x1800559c8`
- `0x180060254`
- `0x180068f60`
- `0x180069cc8`
- `0x18006e540`
- `0x180071188`
- `0x180071694`
- `0x180071780`
- `0x180071de8`
- `0x180072d58`
- `0x180073028`
- `0x180073060`
- `0x1800731cc`
- `0x180073538`
- `0x180073c84`
- `0x180074334`
- `0x1800743fc`
- `0x180085b00`
- `0x180086da4`
- `0x1800be068`
- `0x1800be44c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180073627`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180073627`
- `ntdll!RtlPublishWnfStateData` at `0x1800738ea`
- `ntdll!RtlPublishWnfStateData` at `0x1800738ea`
- `ext-ms-win-biometrics-winbio-core-l1-1-7!WinBioIsDeviceEnhancedSignInSecurityCapable` at `0x180073637`
- `ext-ms-win-biometrics-winbio-core-l1-1-7!WinBioIsDeviceEnhancedSignInSecurityCapable` at `0x180073637`

## string_xrefs

- `0x1800735b2`: `onecore\ds\security\biometrics\service\server\essstatemanager.cpp`
- `0x18007378f`: `onecore\ds\security\biometrics\service\server\essstatemanager.cpp`
- `0x1800737f6`: `onecore\ds\security\biometrics\service\server\essstatemanager.cpp`
- `0x180073901`: `onecore\ds\security\biometrics\service\server\essstatemanager.cpp`
- `0x1800739c8`: `onecore\ds\security\biometrics\service\server\essstatemanager.cpp`
- `0x180073a03`: `onecore\ds\security\biometrics\service\server\essstatemanager.cpp`
- `0x180073a8b`: `onecore\ds\security\biometrics\service\server\essstatemanager.cpp`
- `0x180073ab7`: `onecore\ds\security\biometrics\service\server\essstatemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void CEssStateManager::ProcessEssChange(void)
{
  unsigned int v0; // edi
  unsigned int v1; // r12d
  __int64 v2; // rax
  __int64 v3; // rcx
  unsigned int value; // eax
  wil::details::in1diag3 *v5; // rcx
  __int64 v6; // rdx
  BOOL IsEssEnabled; // esi
  unsigned int *v8; // r9
  int EnrolledFactorsForIdentity; // eax
  int v10; // r13d
  unsigned int v11; // r14d
  signed int v12; // r15d
  __int64 v13; // rcx
  CDeviceStateManager *v14; // rcx
  int v15; // eax
  int v16; // eax
  __int64 v17; // rcx
  bool v18; // bl
  int v19; // eax
  __int64 v20; // rax
  struct _WINBIO_IDENTITY **v21; // rcx
  __int64 v22; // rdx
  struct _WINBIO_IDENTITY **v23; // rbx
  struct _WINBIO_IDENTITY **v24; // rdi
  int v25; // eax
  int v26; // eax
  __int64 v27; // rax
  CHardwareManager *v28; // rax
  int v29; // eax
  HANDLE *v30; // rax
  int v31; // eax
  int v32; // r8d
  bool *v33; // [rsp+20h] [rbp-E0h]
  int v34; // [rsp+20h] [rbp-E0h]
  int v35; // [rsp+20h] [rbp-E0h]
  bool v36[4]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v37; // [rsp+44h] [rbp-BCh] BYREF
  _BYTE v38[80]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v39; // [rsp+98h] [rbp-68h]
  _OWORD v40[2]; // [rsp+A0h] [rbp-60h] BYREF
  _DWORD v41[20]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v42[96]; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v43[424]; // [rsp+170h] [rbp+70h] BYREF
  _BYTE v44[32]; // [rsp+318h] [rbp+218h] BYREF
  BOOL v45; // [rsp+338h] [rbp+238h]
  unsigned int v46; // [rsp+33Ch] [rbp+23Ch]
  wil::details::in1diag3 *retaddr; // [rsp+3D8h] [rbp+2D8h]

  BioPolicy::Refresh((BioPolicy *)v42);
  v0 = *(_DWORD *)&v42[8 * (int)BioPolicy::Values::make_index(11) + 4];
  if ( v0 != 1 )
  {
    v40[0] = 0;
    v40[1] = _mm_load_si128((const __m128i *)&_xmm);
    v1 = 0;
    LOWORD(v40[0]) = 0;
    *(_DWORD *)&v38[16] = 0;
    if ( (int)GetWinBioRegistryLocation((__int64)v40) < 0 )
      goto LABEL_10;
    *(_QWORD *)&v38[8] = 0;
    v2 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v40);
    value = wil::reg::open_unique_key_nothrow(v3, v2, &v38[8]);
    v5 = retaddr;
    if ( value )
    {
      v6 = 287;
    }
    else
    {
      value = wil::reg::get_value_nothrow<unsigned long,0>(*(_QWORD *)&v38[8], 0, L"NonVsmStateUpgradeFlow", &v38[16]);
      v5 = retaddr;
      if ( !value )
        goto LABEL_8;
      v6 = 289;
    }
    wil::details::in1diag3::_Log_Win32(
      v5,
      (void *)v6,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\essstatemanager.cpp",
      (const char *)value,
      (unsigned int)v33);
LABEL_8:
    if ( *(_QWORD *)&v38[8] )
      RegCloseKey(*(HKEY *)&v38[8]);
LABEL_10:
    *(_DWORD *)&v38[20] = 0;
    if ( (int)WinBioIsDeviceEnhancedSignInSecurityCapable(&v38[20]) < 0 || !*(_DWORD *)&v38[20] || !*(_DWORD *)&v38[16] )
    {
      if ( (unsigned int)dword_18010F170 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18010F170, 0x400000000000LL) )
      {
        *(_DWORD *)&v38[24] = v32;
        v37 = *(_DWORD *)&v38[16];
        *(_DWORD *)v38 = v0;
        *(_DWORD *)&v38[8] = *(_DWORD *)&v38[20];
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          (__int64)&dword_18010F170,
          (__int64)&unk_1800ED1A0);
      }
      goto LABEL_57;
    }
    IsEssEnabled = CEssStateManager::IsEssEnabled();
    v36[0] = CEssStateManager::WasEssEnabled();
    *(_OWORD *)&v38[64] = 0;
    v39 = 0;
    memset_0(v41, 0, 0x4Cu);
    v41[0] = 1;
    v41[1] = 621175426;
    *(_DWORD *)v38 = 0;
    v37 = 0;
    EnrolledFactorsForIdentity = winbio::GetEnrolledFactorsForIdentity(
                                   (winbio *)v41,
                                   (struct _WINBIO_IDENTITY *)v38,
                                   &v37,
                                   v8);
    v10 = *(_DWORD *)v38;
    v11 = v37;
    if ( EnrolledFactorsForIdentity < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x14B,
        (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\essstatemanager.cpp",
        (const char *)(unsigned int)EnrolledFactorsForIdentity,
        (int)v33);
    }
    else if ( (unsigned int)dword_18010F170 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18010F170, 0x400000000000LL) )
    {
      *(_QWORD *)&v38[8] = 50331648;
      v37 = v11;
      *(_DWORD *)v38 = v10;
      v33 = v38;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        (__int64)&dword_18010F170,
        (__int64)&word_1800ED14E);
    }
    v12 = 0;
    v37 = 0;
    if ( IsEssEnabled )
    {
      CDeviceStateManager::Instance();
      v15 = CDeviceStateManager::DeleteVtl0Containers(v14, (int *)&v37);
      if ( v15 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x157,
          (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\essstatemanager.cpp",
          (const char *)(unsigned int)v15,
          (int)v33);
      *(_DWORD *)v38 = 8;
      std::vector<unsigned int>::push_back(&v38[64], v38);
      *(_DWORD *)v38 = 2;
      std::vector<unsigned int>::push_back(&v38[64], v38);
      LOBYTE(v11) = v10;
      v12 = v37;
    }
    else
    {
      v1 = 1;
      v37 = 2;
      std::vector<unsigned int>::push_back(&v38[64], &v37);
    }
    if ( (v11 & 2) != 0 )
    {
      v16 = winbio::SetBioRegKeyValue(v13, 5, 1);
      if ( v16 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x162,
          (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\essstatemanager.cpp",
          (const char *)(unsigned int)v16,
          (int)v33);
    }
    if ( (unsigned int)dword_18010F170 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18010F170, 0x800000000000LL) )
    {
      *(_QWORD *)&v38[8] = 50331648;
      v37 = v0;
      v18 = v36[0];
      *(_DWORD *)v38 = v36[0];
      *(_DWORD *)&v38[24] = IsEssEnabled;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        v17,
        (__int64)byte_1800ED0F1);
    }
    else
    {
      v18 = v36[0];
    }
    CEtwEvent::CEtwEvent((CEtwEvent *)v43);
    std::wstring::_Assign<unsigned short>(v44, L"Enabling ESS");
    v45 = IsEssEnabled;
    v46 = v0;
    CEtwEvent::Write(v43, 1115, 1);
    *(_DWORD *)&v38[32] = v0;
    v38[36] = IsEssEnabled;
    v38[37] = v18;
    *(_WORD *)&v38[38] = 0;
    v34 = 0;
    v19 = RtlPublishWnfStateData(WNF_WBIO_ESS_STATE_CHANGE, 0, &v38[32], 8) | 0x10000000;
    if ( v19 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x17B,
        (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\essstatemanager.cpp",
        (const char *)(unsigned int)v19,
        0);
    CHardwareManager::Instance();
    v20 = std::vector<unsigned int>::vector<unsigned int>(&v38[40], &v38[64]);
    CHardwareManager::DeleteAllEnrollments(v20, v1);
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_K2EnrollmentCorruption>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_K2EnrollmentCorruption>::GetImpl'::`2'::impl)
      && IsEssEnabled )
    {
      memset(&v38[40], 0, 24);
      if ( (int)winbio::GetIdentities((__int64)&v38[40]) >= 0 )
      {
        v24 = *(struct _WINBIO_IDENTITY ***)&v38[48];
        v23 = *(struct _WINBIO_IDENTITY ***)&v38[40];
        if ( *(_QWORD *)&v38[40] != *(_QWORD *)&v38[48] )
        {
          do
          {
            v36[0] = 0;
            v25 = CAccountManager::SetEnrolledFactorState(*v23, 8u, 0, 0, v36);
            if ( v25 < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x18F,
                (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\essstatemanager.cpp",
                (const char *)(unsigned int)v25,
                v35);
            v26 = CAccountManager::SetEnrolledFactorState(*v23, 2u, 0, 0, v36);
            if ( v26 < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x195,
                (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\essstatemanager.cpp",
                (const char *)(unsigned int)v26,
                v34);
            ++v23;
          }
          while ( v23 != v24 );
          v23 = *(struct _WINBIO_IDENTITY ***)&v38[40];
        }
        if ( !v23 )
          goto LABEL_47;
        v22 = *(_QWORD *)&v38[56] - (_QWORD)v23;
        v21 = v23;
        goto LABEL_46;
      }
      v21 = *(struct _WINBIO_IDENTITY ***)&v38[40];
      if ( *(_QWORD *)&v38[40] )
      {
        v22 = *(_QWORD *)&v38[56] - *(_QWORD *)&v38[40];
LABEL_46:
        std::_Deallocate<16>(v21, v22 & 0xFFFFFFFFFFFFFFF8uLL);
      }
    }
LABEL_47:
    CHardwareManager::Instance();
    v27 = std::vector<unsigned int>::vector<unsigned int>(&v38[40], &v38[64]);
    CHardwareManager::DeleteBiometricUnitsBySecurityLevel(v27, v1);
    CEssStateManager::SetEnableEssPreviousValue();
    if ( v12 > 0 )
    {
      CHardwareManager::Instance();
      CHardwareManager::InitializeSecureBioAvailability();
    }
    v28 = CHardwareManager::Instance();
    v29 = CHardwareManager::ScanForVirtualSensors(v28);
    if ( v29 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x1A1,
        (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\essstatemanager.cpp",
        (const char *)(unsigned int)v29,
        v34);
    v30 = (HANDLE *)CHardwareManager::Instance();
    v31 = CHardwareManager::ScanForPhysicalSensors(v30);
    if ( v31 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x1A2,
        (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\essstatemanager.cpp",
        (const char *)(unsigned int)v31,
        v34);
    CEtwEvent::~CEtwEvent((CEtwEvent *)v43);
    std::vector<unsigned int>::_Tidy(&v38[64]);
LABEL_57:
    std::wstring::_Tidy_deallocate(v40);
  }
}

```

## disassembly

```asm
0x180073538  push    rbp
0x18007353a  push    rbx
0x18007353b  push    rsi
0x18007353c  push    rdi
0x18007353d  push    r12
0x18007353f  push    r13
0x180073541  push    r14
0x180073543  push    r15
0x180073545  lea     rbp, [rsp-298h]
0x18007354d  sub     rsp, 398h
0x180073554  mov     rax, cs:__security_cookie
0x18007355b  xor     rax, rsp
0x18007355e  mov     [rbp+2D0h+var_50], rax
0x180073565  lea     rcx, [rbp+2D0h+var_2C0]; this
0x180073569  call    ?Refresh@BioPolicy@@QEAAJXZ; BioPolicy::Refresh(void)
0x18007356e  mov     ecx, 0Bh
0x180073573  call    ?make_index@Values@BioPolicy@@SAHW4type@12@@Z; BioPolicy::Values::make_index(BioPolicy::Values::type)
0x180073578  movsxd  rcx, eax
0x18007357b  mov     edi, [rbp+rcx*8+2D0h+var_2BC]
0x18007357f  cmp     edi, 1
0x180073582  jz      loc_180073B63
0x180073588  xorps   xmm0, xmm0
0x18007358b  movups  [rbp+2D0h+var_330], xmm0
0x18007358f  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180073597  movdqu  [rbp+2D0h+var_320], xmm1
0x18007359c  xor     r12d, r12d
0x18007359f  mov     word ptr [rbp+2D0h+var_330], r12w
0x1800735a4  mov     dword ptr [rsp+3D0h+var_388+10h], r12d
0x1800735a9  lea     rcx, [rbp+2D0h+var_330]
0x1800735ad  call    ?GetWinBioRegistryLocation@@YAJPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GetWinBioRegistryLocation(std::wstring *)
0x1800735b2  lea     r15, aOnecoreDsSecur_28; "onecore\\ds\\security\\biometrics\\serv"...
0x1800735b9  test    eax, eax
0x1800735bb  js      short loc_18007362D
0x1800735bd  mov     qword ptr [rsp+3D0h+var_388+8], r12
0x1800735c2  lea     rcx, [rbp+2D0h+var_330]
0x1800735c6  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800735cb  mov     rdx, rax
0x1800735ce  lea     r8, [rsp+3D0h+var_388+8]
0x1800735d3  call    ?open_unique_key_nothrow@reg@wil@@YAJPEAUHKEY__@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@W4key_access@12@@Z; wil::reg::open_unique_key_nothrow(HKEY__ *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,wil::reg::key_access)
0x1800735d8  mov     rcx, [rbp+2D8h]
0x1800735df  test    eax, eax
0x1800735e1  jz      short loc_1800735EA
0x1800735e3  mov     edx, 11Fh
0x1800735e8  jmp     short loc_180073612
0x1800735ea  lea     r9, [rsp+3D0h+var_388+10h]
0x1800735ef  lea     r8, aNonvsmstateupg; "NonVsmStateUpgradeFlow"
0x1800735f6  xor     edx, edx
0x1800735f8  mov     rcx, qword ptr [rsp+3D0h+var_388+8]
0x1800735fd  call    ??$get_value_nothrow@K$0A@@reg@wil@@YAJPEAUHKEY__@@PEBG1PEAK@Z; wil::reg::get_value_nothrow<ulong,0>(HKEY__ *,ushort const *,ushort const *,ulong *)
0x180073602  mov     rcx, [rbp+2D8h]; this
0x180073609  test    eax, eax
0x18007360b  jz      short loc_18007361D
0x18007360d  mov     edx, 121h; void *
0x180073612  mov     r9d, eax; char *
0x180073615  mov     r8, r15; unsigned int
0x180073618  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x18007361d  mov     rcx, qword ptr [rsp+3D0h+var_388+8]; hKey
0x180073622  test    rcx, rcx
0x180073625  jz      short loc_18007362D
0x180073627  call    cs:__imp_RegCloseKey
0x18007362d  mov     dword ptr [rsp+3D0h+var_388+14h], r12d
0x180073632  lea     rcx, [rsp+3D0h+var_388+14h]
0x180073637  call    cs:__imp_WinBioIsDeviceEnhancedSignInSecurityCapable
0x18007363d  mov     r8d, eax
0x180073640  test    eax, eax
0x180073642  js      loc_180073ADE
0x180073648  cmp     dword ptr [rsp+3D0h+var_388+14h], r12d
0x18007364d  jz      loc_180073ADE
0x180073653  cmp     dword ptr [rsp+3D0h+var_388+10h], r12d
0x180073658  jz      loc_180073ADE
0x18007365e  call    ?IsEssEnabled@CEssStateManager@@SA_NXZ; CEssStateManager::IsEssEnabled(void)
0x180073663  movzx   esi, al
0x180073666  call    ?WasEssEnabled@CEssStateManager@@SA_NXZ; CEssStateManager::WasEssEnabled(void)
0x18007366b  mov     [rsp+3D0h+var_390], al
0x18007366f  xorps   xmm0, xmm0
0x180073672  movdqu  xmmword ptr [rbp+2D0h+var_388+40h], xmm0
0x180073677  mov     [rbp+2D0h+var_338], r12
0x18007367b  xor     edx, edx; Val
0x18007367d  lea     r8d, [rdx+4Ch]; Size
0x180073681  lea     rcx, [rbp+2D0h+var_310]; void *
0x180073685  call    memset_0
0x18007368a  mov     [rbp+2D0h+var_310], 1
0x180073691  mov     [rbp+2D0h+var_30C], 25066282h
0x180073698  mov     dword ptr [rsp+3D0h+var_388], r12d
0x18007369d  mov     [rsp+3D0h+var_38C], r12d
0x1800736a2  lea     r8, [rsp+3D0h+var_38C]; unsigned int *
0x1800736a7  lea     rdx, [rsp+3D0h+var_388]; struct _WINBIO_IDENTITY *
0x1800736ac  lea     rcx, [rbp+2D0h+var_310]; this
0x1800736b0  call    ?GetEnrolledFactorsForIdentity@winbio@@YAJPEAU_WINBIO_IDENTITY@@PEAI1@Z; winbio::GetEnrolledFactorsForIdentity(_WINBIO_IDENTITY *,uint *,uint *)
0x1800736b5  lea     rbx, dword_18010F170
0x1800736bc  mov     r13d, dword ptr [rsp+3D0h+var_388]
0x1800736c1  mov     r14d, [rsp+3D0h+var_38C]
0x1800736c6  test    eax, eax
0x1800736c8  js      short loc_180073730
0x1800736ca  mov     eax, cs:dword_18010F170
0x1800736d0  cmp     eax, 5
0x1800736d3  jbe     short loc_180073747
0x1800736d5  mov     rdx, 400000000000h
0x1800736df  mov     rcx, rbx
0x1800736e2  call    _tlgKeywordOn
0x1800736e7  test    al, al
0x1800736e9  jz      short loc_180073747
0x1800736eb  mov     qword ptr [rsp+3D0h+var_388+8], 3000000h
0x1800736f4  mov     [rsp+3D0h+var_38C], r14d
0x1800736f9  mov     dword ptr [rsp+3D0h+var_388], r13d
0x1800736fe  lea     rax, [rsp+3D0h+var_388+8]
0x180073703  mov     [rsp+3D0h+var_3A0], rax
0x180073708  lea     rax, [rsp+3D0h+var_38C]
0x18007370d  mov     [rsp+3D0h+var_3A8], rax
0x180073712  lea     rax, [rsp+3D0h+var_388]
0x180073717  mov     [rsp+3D0h+var_3B0], rax
0x18007371c  xor     r8d, r8d
0x18007371f  lea     rdx, word_1800ED14E
0x180073726  mov     rcx, rbx
0x180073729  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x18007372e  jmp     short loc_180073747
0x180073730  mov     rcx, [rbp+2D8h]; this
0x180073737  mov     r9d, eax; char *
0x18007373a  mov     r8, r15; unsigned int
0x18007373d  mov     edx, 14Bh; void *
0x180073742  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180073747  mov     r15d, r12d
0x18007374a  mov     [rsp+3D0h+var_38C], r12d
0x18007374f  test    sil, sil
0x180073752  jnz     short loc_180073772
0x180073754  mov     r12d, 1
0x18007375a  mov     [rsp+3D0h+var_38C], 2
0x180073762  lea     rdx, [rsp+3D0h+var_38C]
0x180073767  lea     rcx, [rbp+2D0h+var_388+40h]
0x18007376b  call    ?push_back@?$vector@IV?$allocator@I@std@@@std@@QEAAX$$QEAI@Z; std::vector<uint>::push_back(uint &&)
0x180073770  jmp     short loc_1800737D4
0x180073772  call    ?Instance@CDeviceStateManager@@SAAEAV1@XZ; CDeviceStateManager::Instance(void)
0x180073777  lea     rdx, [rsp+3D0h+var_38C]; int *
0x18007377c  call    ?DeleteVtl0Containers@CDeviceStateManager@@QEAAJAEAH@Z; CDeviceStateManager::DeleteVtl0Containers(int &)
0x180073781  mov     rcx, [rbp+2D8h]; this
0x180073788  test    eax, eax
0x18007378a  jns     short loc_1800737A0
0x18007378c  mov     r9d, eax; char *
0x18007378f  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\biometrics\\serv"...
0x180073796  mov     edx, 157h; void *
0x18007379b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800737a0  mov     dword ptr [rsp+3D0h+var_388], 8
0x1800737a8  lea     rdx, [rsp+3D0h+var_388]
0x1800737ad  lea     rcx, [rbp+2D0h+var_388+40h]
0x1800737b1  call    ?push_back@?$vector@IV?$allocator@I@std@@@std@@QEAAX$$QEAI@Z; std::vector<uint>::push_back(uint &&)
0x1800737b6  mov     dword ptr [rsp+3D0h+var_388], 2
0x1800737be  lea     rdx, [rsp+3D0h+var_388]
0x1800737c3  lea     rcx, [rbp+2D0h+var_388+40h]
0x1800737c7  call    ?push_back@?$vector@IV?$allocator@I@std@@@std@@QEAAX$$QEAI@Z; std::vector<uint>::push_back(uint &&)
0x1800737cc  mov     r14d, r13d
0x1800737cf  mov     r15d, [rsp+3D0h+var_38C]
0x1800737d4  test    r14b, 2
0x1800737d8  jz      short loc_180073807
0x1800737da  mov     edx, 5
0x1800737df  lea     r8d, [rdx-4]
0x1800737e3  call    ?SetBioRegKeyValue@winbio@@YAJPEAU_WINBIO_IDENTITY@@W4RegKeyName@1@K@Z; winbio::SetBioRegKeyValue(_WINBIO_IDENTITY *,winbio::RegKeyName,ulong)
0x1800737e8  mov     rcx, [rbp+2D8h]; this
0x1800737ef  test    eax, eax
0x1800737f1  jns     short loc_180073807
0x1800737f3  mov     r9d, eax; char *
0x1800737f6  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\biometrics\\serv"...
0x1800737fd  mov     edx, 162h; void *
0x180073802  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180073807  mov     eax, cs:dword_18010F170
0x18007380d  cmp     eax, 5
0x180073810  jbe     short loc_180073878
0x180073812  mov     rdx, 800000000000h
0x18007381c  mov     rcx, rbx
0x18007381f  call    _tlgKeywordOn
0x180073824  test    al, al
0x180073826  jz      short loc_180073878
0x180073828  mov     qword ptr [rsp+3D0h+var_388+8], 3000000h
0x180073831  mov     [rsp+3D0h+var_38C], edi
0x180073835  movzx   ebx, [rsp+3D0h+var_390]
0x18007383a  mov     dword ptr [rsp+3D0h+var_388], ebx
0x18007383e  mov     dword ptr [rsp+3D0h+var_388+18h], esi
0x180073842  lea     rax, [rsp+3D0h+var_388+8]
0x180073847  mov     [rsp+3D0h+var_398], rax
0x18007384c  lea     rax, [rsp+3D0h+var_38C]
0x180073851  mov     [rsp+3D0h+var_3A0], rax
0x180073856  lea     rax, [rsp+3D0h+var_388]
0x18007385b  mov     [rsp+3D0h+var_3A8], rax
0x180073860  lea     rax, [rsp+3D0h+var_388+18h]
0x180073865  mov     [rsp+3D0h+var_3B0], rax
0x18007386a  lea     rdx, byte_1800ED0F1
0x180073871  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@33AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x180073876  jmp     short loc_18007387C
0x180073878  mov     bl, [rsp+3D0h+var_390]
0x18007387c  lea     rcx, [rbp+2D0h+var_260]; this
0x180073880  call    ??0CEtwEvent@@QEAA@XZ; CEtwEvent::CEtwEvent(void)
0x180073885  nop
0x180073886  mov     r8d, 0Ch
0x18007388c  lea     rdx, aEnablingEss; "Enabling ESS"
0x180073893  lea     rcx, [rbp+2D0h+var_B8]
0x18007389a  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18007389f  mov     [rbp+2D0h+var_98], esi
0x1800738a5  mov     [rbp+2D0h+var_94], edi
0x1800738ab  mov     edx, 45Bh
0x1800738b0  mov     r8d, 1
0x1800738b6  lea     rcx, [rbp+2D0h+var_260]
0x1800738ba  call    ?Write@CEtwEvent@@QEAAJKW4WBioEventLevel@@@Z; CEtwEvent::Write(ulong,WBioEventLevel)
0x1800738bf  mov     dword ptr [rsp+3D0h+var_388+20h], edi
0x1800738c3  mov     [rsp+3D0h+var_388+24h], sil
0x1800738c8  mov     [rsp+3D0h+var_388+25h], bl
0x1800738cc  xor     eax, eax
0x1800738ce  mov     word ptr [rsp+3D0h+var_388+26h], ax
0x1800738d3  mov     [rsp+3D0h+var_3B0], rax; int
0x1800738d8  lea     r9d, [rax+8]
0x1800738dc  lea     r8, [rsp+3D0h+var_388+20h]
0x1800738e1  xor     edx, edx
0x1800738e3  mov     rcx, cs:WNF_WBIO_ESS_STATE_CHANGE
0x1800738ea  call    cs:__imp_RtlPublishWnfStateData
0x1800738f0  or      eax, 10000000h
0x1800738f5  mov     rcx, [rbp+2D8h]; this
0x1800738fc  jge     short loc_180073912
0x1800738fe  mov     r9d, eax; char *
0x180073901  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\biometrics\\serv"...
0x180073908  mov     edx, 17Bh; void *
0x18007390d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180073912  call    ?Instance@CHardwareManager@@SAAEAV1@XZ; CHardwareManager::Instance(void)
0x180073917  lea     rdx, [rbp+2D0h+var_388+40h]
0x18007391b  lea     rcx, [rsp+3D0h+var_388+28h]
0x180073920  call    ??0?$vector@IV?$allocator@I@std@@@std@@QEAA@AEBV01@@Z; std::vector<uint>::vector<uint>(std::vector<uint> const &)
0x180073925  mov     edx, r12d
0x180073928  mov     rcx, rax
0x18007392b  call    ?DeleteAllEnrollments@CHardwareManager@@SAXV?$vector@IV?$allocator@I@std@@@std@@K@Z; CHardwareManager::DeleteAllEnrollments(std::vector<uint>,ulong)
0x180073930  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_K2EnrollmentCorruption@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_K2EnrollmentCorruption@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_K2EnrollmentCorruption> `wil::Feature<__WilFeatureTraits_Feature_K2EnrollmentCorruption>::GetImpl(void)'::`2'::impl
0x180073937  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_K2EnrollmentCorruption@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_K2EnrollmentCorruption>::__private_IsEnabled(void)
0x18007393c  test    al, al
0x18007393e  jnz     loc_180073A3E
0x180073944  test    sil, sil
0x180073947  jz      loc_180073A3E
0x18007394d  xorps   xmm0, xmm0
0x180073950  movdqu  xmmword ptr [rsp+3D0h+var_388+28h], xmm0
0x180073956  mov     qword ptr [rbp+2D0h+var_388+38h], 0
0x18007395e  lea     rcx, [rsp+3D0h+var_388+28h]
0x180073963  call    ?GetIdentities@winbio@@YAJPEAV?$vector@PEAU_WINBIO_IDENTITY@@V?$allocator@PEAU_WINBIO_IDENTITY@@@std@@@std@@@Z; winbio::GetIdentities(std::vector<_WINBIO_IDENTITY *> *)
0x180073968  test    eax, eax
0x18007396a  jns     short loc_180073986
0x18007396c  mov     rcx, qword ptr [rsp+3D0h+var_388+28h]
0x180073971  test    rcx, rcx
0x180073974  jz      loc_180073A3E
0x18007397a  mov     rdx, qword ptr [rbp+2D0h+var_388+38h]
0x18007397e  sub     rdx, rcx
0x180073981  jmp     loc_180073A35
0x180073986  mov     rbx, qword ptr [rsp+3D0h+var_388+28h]
0x18007398b  mov     rdi, qword ptr [rsp+3D0h+var_388+30h]
0x180073990  cmp     rbx, rdi
0x180073993  jz      loc_180073A26
0x180073999  mov     [rsp+3D0h+var_390], 0
0x18007399e  lea     rax, [rsp+3D0h+var_390]
0x1800739a3  mov     [rsp+3D0h+var_3B0], rax; int
0x1800739a8  xor     r9d, r9d; bool
0x1800739ab  xor     r8d, r8d; unsigned int
0x1800739ae  lea     edx, [r9+8]; unsigned int
0x1800739b2  mov     rcx, [rbx]; this
0x1800739b5  call    ?SetEnrolledFactorState@CAccountManager@@SAJPEAU_WINBIO_IDENTITY@@IK_NPEA_N@Z; CAccountManager::SetEnrolledFactorState(_WINBIO_IDENTITY *,uint,ulong,bool,bool *)
0x1800739ba  mov     rcx, [rbp+2D8h]; this
0x1800739c1  test    eax, eax
0x1800739c3  jns     short loc_1800739D9
0x1800739c5  mov     r9d, eax; char *
0x1800739c8  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\biometrics\\serv"...
0x1800739cf  mov     edx, 18Fh; void *
0x1800739d4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800739d9  lea     rax, [rsp+3D0h+var_390]
0x1800739de  mov     [rsp+3D0h+var_3B0], rax; int
0x1800739e3  xor     r9d, r9d; bool
0x1800739e6  xor     r8d, r8d; unsigned int
0x1800739e9  lea     edx, [r9+2]; unsigned int
0x1800739ed  mov     rcx, [rbx]; this
0x1800739f0  call    ?SetEnrolledFactorState@CAccountManager@@SAJPEAU_WINBIO_IDENTITY@@IK_NPEA_N@Z; CAccountManager::SetEnrolledFactorState(_WINBIO_IDENTITY *,uint,ulong,bool,bool *)
0x1800739f5  mov     rcx, [rbp+2D8h]; this
0x1800739fc  test    eax, eax
0x1800739fe  jns     short loc_180073A14
0x180073a00  mov     r9d, eax; char *
0x180073a03  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\biometrics\\serv"...
0x180073a0a  mov     edx, 195h; void *
0x180073a0f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180073a14  add     rbx, 8
0x180073a18  cmp     rbx, rdi
0x180073a1b  jnz     loc_180073999
0x180073a21  mov     rbx, qword ptr [rsp+3D0h+var_388+28h]
0x180073a26  test    rbx, rbx
0x180073a29  jz      short loc_180073A3E
0x180073a2b  mov     rdx, qword ptr [rbp+2D0h+var_388+38h]
0x180073a2f  sub     rdx, rbx
0x180073a32  mov     rcx, rbx
0x180073a35  and     rdx, 0FFFFFFFFFFFFFFF8h
0x180073a39  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180073a3e  call    ?Instance@CHardwareManager@@SAAEAV1@XZ; CHardwareManager::Instance(void)
0x180073a43  lea     rdx, [rbp+2D0h+var_388+40h]
0x180073a47  lea     rcx, [rsp+3D0h+var_388+28h]
0x180073a4c  call    ??0?$vector@IV?$allocator@I@std@@@std@@QEAA@AEBV01@@Z; std::vector<uint>::vector<uint>(std::vector<uint> const &)
0x180073a51  mov     edx, r12d
0x180073a54  mov     rcx, rax
0x180073a57  call    ?DeleteBiometricUnitsBySecurityLevel@CHardwareManager@@SAXV?$vector@IV?$allocator@I@std@@@std@@K@Z; CHardwareManager::DeleteBiometricUnitsBySecurityLevel(std::vector<uint>,ulong)
0x180073a5c  call    ?SetEnableEssPreviousValue@CEssStateManager@@SA?AW4EssState@BioPolicy@@XZ; CEssStateManager::SetEnableEssPreviousValue(void)
0x180073a61  test    r15d, r15d
0x180073a64  jle     short loc_180073A70
0x180073a66  call    ?Instance@CHardwareManager@@SAAEAV1@XZ; CHardwareManager::Instance(void)
  ... truncated ...
```
