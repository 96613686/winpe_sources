# CBiometricUnit::Configure(void)

- ea: `0x18001c2ac`
- end: `0x18001c999`
- name: `?Configure@CBiometricUnit@@QEAAJXZ`
- size: `1773`
- prototype: `__int64 __fastcall(CBiometricUnit *__hidden this)`
- caller_count: `2`
- callee_count: `46`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001c2ac`
- `0x18001caa8`

## callees

- `0x180001630`
- `0x180006340`
- `0x18000b760`
- `0x1800100b0`
- `0x180013b6c`
- `0x18001434c`
- `0x180014854`
- `0x180014894`
- `0x180014bcc`
- `0x180017630`
- `0x18001c238`
- `0x18001c2ac`
- `0x18001ca14`
- `0x180023d88`
- `0x180028af0`
- `0x18002ab1c`
- `0x18002b01c`
- `0x18002b7c0`
- `0x18002d3b4`
- `0x180037294`
- `0x18003f2dc`
- `0x180040044`
- `0x180044b1c`
- `0x18004c4bc`
- `0x18004c810`
- `0x1800530c4`
- `0x180055878`
- `0x1800559c8`
- `0x180059380`
- `0x1800593b4`
- `0x180068f60`
- `0x18006b0b5`
- `0x18006e4c4`
- `0x180074224`
- `0x18007889c`
- `0x180078ca8`
- `0x180078dec`
- `0x180079cac`
- `0x18007a8e4`
- `0x18007c97c`
- `0x18007d18c`
- `0x180080ff4`
- `0x1800859dc`
- `0x180086da4`
- `0x1800b5988`
- `0x1800b7818`

## import_xrefs

- `ntdll!RtlPublishWnfStateData` at `0x18001c6dd`
- `ntdll!RtlPublishWnfStateData` at `0x18001c8d4`
- `ntdll!RtlPublishWnfStateData` at `0x18001c6dd`
- `ntdll!RtlPublishWnfStateData` at `0x18001c8d4`

## string_xrefs

- `0x18001c6f8`: `onecore\ds\security\biometrics\service\server\biometricunit.cpp`
- `0x18001c875`: `onecore\ds\security\biometrics\service\server\biometricunit.cpp`
- `0x18001c8eb`: `onecore\ds\security\biometrics\service\server\biometricunit.cpp`
- `0x18001c2e5`: `CBiometricUnit::Configure`

## pseudocode

```c
__int64 __fastcall CBiometricUnit::Configure(CBiometricUnit *this)
{
  struct CSensorConfig *ActiveConfiguration; // rax
  struct CSensorConfig *v3; // r14
  const unsigned __int16 *v4; // rax
  const unsigned __int16 *v5; // r8
  const unsigned __int16 *v6; // r9
  int v7; // ecx
  int v8; // r8d
  int v9; // r9d
  char HasSecureFpRegKey; // bl
  int v11; // r8d
  int v12; // r9d
  __int64 v13; // rax
  __int64 *v14; // rax
  __int64 v15; // rcx
  __int64 v16; // rdx
  int v17; // eax
  char IsEnabled; // al
  int v19; // ecx
  int v20; // r9d
  struct _Mtx_internal_imp_t *v21; // rdi
  int v22; // eax
  __int64 v23; // rax
  __int64 v24; // rax
  int v25; // eax
  char v26; // bl
  CSensorConfigSelector *v27; // rcx
  int active; // eax
  int v29; // eax
  int v30; // r8d
  int v31; // edx
  unsigned int v32; // ebx
  int v34; // [rsp+20h] [rbp-E0h]
  int v35; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v36[4]; // [rsp+54h] [rbp-ACh] BYREF
  int v37; // [rsp+58h] [rbp-A8h] BYREF
  int v38; // [rsp+5Ch] [rbp-A4h] BYREF
  int v39; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v40; // [rsp+68h] [rbp-98h] BYREF
  std::_Ref_count_base *v41; // [rsp+70h] [rbp-90h]
  _BYTE v42[8]; // [rsp+78h] [rbp-88h] BYREF
  _QWORD *v43; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v44[5]; // [rsp+88h] [rbp-78h] BYREF
  struct _GUID v45; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v46; // [rsp+C0h] [rbp-40h]
  _BYTE v47[32]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE Src[360]; // [rsp+F0h] [rbp-10h] BYREF
  int v49; // [rsp+258h] [rbp+158h]
  char v50[32]; // [rsp+B10h] [rbp+A10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B78h] [rbp+A78h]

  v35 = 0;
  v38 = 0;
  strcpy(v50, "CBiometricUnit::Configure");
  v44[0] = v50;
  v44[1] = &v38;
  v44[2] = &v35;
  v44[3] = this;
  lambda_94f52387e22c6c608242f2f7e8241c5b_::operator()(v44);
  v38 = 1;
  v43 = v44;
  winbio::lockable_object::lock_exclusive(this, v42);
  ActiveConfiguration = CSensorConfigSelector::GetActiveConfiguration(*((CSensorConfigSelector **)this + 344));
  v3 = ActiveConfiguration;
  if ( !ActiveConfiguration || !*((_BYTE *)ActiveConfiguration + 132) )
  {
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_EssFprPeripherals>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_EssFprPeripherals>::GetImpl'::`2'::impl);
    v19 = *((_DWORD *)this + 22);
    if ( IsEnabled )
    {
      if ( (v19 == 8 || v19 == 2) && CEssStateManager::ShouldBlockNonEssSensors() )
      {
        if ( (unsigned int)dword_18010F170 > 4 )
        {
          v37 = 0;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            (unsigned int)&dword_18010F170,
            (unsigned int)word_1800EDB0A,
            0,
            v20,
            (__int64)&v37);
        }
        v35 = -2146860969;
        v21 = CDeviceStateManager::Instance();
        std::wstring::wstring(v47, (char *)this + 2672);
        memcpy_0(Src, (char *)this + 80, 0xA1Cu);
        CDeviceStateManager::CacheBlockedSensor(v21, Src);
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EssFprPeripherals>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_EssFprPeripherals>::GetImpl'::`2'::impl) )
        {
          v34 = 0;
          v22 = RtlPublishWnfStateData(WNF_WBIO_BIO_UNITS_STATE_CHANGE, 0, 0, 0) | 0x10000000;
          if ( v22 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x1EC,
              (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\biometricunit.cpp",
              (const char *)(unsigned int)v22,
              0);
        }
        goto LABEL_44;
      }
    }
    else if ( (v19 == 8 || v19 == 2) && CHardwareManager::ShouldBlockNonESSSensors() )
    {
      v35 = -2146860969;
LABEL_44:
      v17 = 0;
      goto LABEL_45;
    }
    v23 = std::enable_shared_from_this<CBiometricUnit>::shared_from_this((char *)this + 24, &v40);
    v24 = std::make_unique<CPresenceMonitorLocal,std::shared_ptr<CBiometricUnit>,0>(&v45, v23);
    std::unique_ptr<CPresenceMonitor>::operator=<CPresenceMonitorLocal,std::default_delete<CPresenceMonitorLocal>,0>(
      (char *)this + 2864,
      v24);
    std::unique_ptr<CPresenceMonitorLocal>::~unique_ptr<CPresenceMonitorLocal>(&v45);
    if ( v41 )
      std::_Ref_count_base::_Decref(v41);
    goto LABEL_44;
  }
  if ( !*((_QWORD *)this + 365) )
  {
    std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)ActiveConfiguration + 200);
    std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)v3 + 168);
    v4 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)v3 + 136);
    v45 = *(struct _GUID *)((char *)v3 + 104);
    v35 = BioIsoCreateSecureBiometricUnit(
            (struct _WINBIO_UNIT_SCHEMA *)((char *)this + 80),
            v4,
            v5,
            v6,
            &v45,
            (void **)this + 365);
    if ( v35 >= 0 )
    {
      v45 = 0;
      v46 = 0;
      v35 = CAccountManager::EnumAccountPolicies(*((_DWORD *)this + 22));
      if ( v35 >= 0 )
        v35 = BioIsoSetBiometricUnitPolicy(
                *((void **)this + 365),
                *(struct _WINBIO_ACCOUNT_POLICY **)&v45.Data1,
                0xCCCCCCCCCCCCCCCDuLL * ((__int64)(*(_QWORD *)v45.Data4 - *(_QWORD *)&v45.Data1) >> 4));
      if ( *(_QWORD *)&v45.Data1 )
        std::_Deallocate<16>(*(_QWORD *)&v45.Data1, 16 * ((v46 - *(_QWORD *)&v45.Data1) >> 4));
    }
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EssFprPeripherals>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_EssFprPeripherals>::GetImpl'::`2'::impl)
    && *((_DWORD *)this + 22) == 8
    && *((char *)this + 96) >= 0 )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EssScpV1CapabilityCheck>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_EssScpV1CapabilityCheck>::GetImpl'::`2'::impl) )
    {
      if ( (*((_DWORD *)this + 24) & 0x200) == 0 )
        v35 = -2146860969;
      if ( (unsigned int)dword_18010F170 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18010F170, 0x400000000000LL) )
      {
        v40 = 50331648;
        std::wstring::wstring(v47, (char *)this + 100);
        v36[0] = BioTrustlet::DeviceHasSecureFpRegKey(v47);
        v39 = *((_DWORD *)this + 24);
        *(_QWORD *)&v45.Data1 = (char *)this + 100;
        v37 = v35;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>>(
          v7,
          (unsigned int)byte_1800EDB9D,
          v8,
          v9,
          (__int64)&v37,
          (__int64)&v45,
          (__int64)&v39,
          (__int64)v36,
          (__int64)&v40);
        std::wstring::_Tidy_deallocate(v47);
      }
    }
    else
    {
      std::wstring::wstring(v47, (char *)this + 100);
      HasSecureFpRegKey = BioTrustlet::DeviceHasSecureFpRegKey(v47);
      std::wstring::_Tidy_deallocate(v47);
      if ( !HasSecureFpRegKey )
      {
        if ( (unsigned int)dword_18010F170 > 4 )
        {
          *(_QWORD *)&v45.Data1 = (char *)this + 100;
          v37 = 0;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
            (unsigned int)&dword_18010F170,
            (unsigned int)byte_1800EDB51,
            v11,
            v12,
            (__int64)&v37,
            (__int64)&v45);
        }
        v35 = -2146860969;
      }
    }
  }
  if ( v35 < 0 )
    goto LABEL_48;
  v13 = std::enable_shared_from_this<CBiometricUnit>::shared_from_this((char *)this + 24, &v40);
  v14 = (__int64 *)std::make_unique<CPresenceMonitorRemote,std::shared_ptr<CBiometricUnit>,0>(&v45, v13);
  v15 = *v14;
  *v14 = 0;
  v16 = *((_QWORD *)this + 358);
  *((_QWORD *)this + 358) = v15;
  if ( v16 )
    std::default_delete<CPresenceMonitor>::operator()();
  std::unique_ptr<CPresenceMonitorRemote>::~unique_ptr<CPresenceMonitorRemote>(&v45);
  if ( v41 )
    std::_Ref_count_base::_Decref(v41);
  v17 = 1;
LABEL_45:
  *((_DWORD *)this + 745) = v17;
  if ( v35 < 0 )
  {
LABEL_48:
    CEtwEvent::CEtwEvent((CEtwEvent *)Src);
    CEtwEvent::CaptureSensorInfo((CEtwEvent *)Src, this);
    CEtwEvent::CaptureConfigurationInfo((CEtwEvent *)Src, v3);
    v49 = v35;
    CEtwEvent::Write(Src, 1109, 1);
    CEtwEvent::~CEtwEvent((CEtwEvent *)Src);
    v25 = v35;
    goto LABEL_49;
  }
  v25 = CPipeline::Configure(*((CPipeline **)this + 338), v3);
  v35 = v25;
  if ( v25 >= 0 )
  {
    *((_BYTE *)this + 2712) = 1;
    v25 = CPipeline::Open(*((CPipeline **)this + 338), v3);
    v35 = v25;
  }
LABEL_49:
  if ( !*((_DWORD *)this + 22) && v25 == -2147467263 )
  {
    v25 = 0;
    v35 = 0;
  }
  if ( v25 >= 0 )
    goto LABEL_58;
  v26 = 0;
  v27 = (CSensorConfigSelector *)*((_QWORD *)this + 344);
  if ( *((_QWORD *)v27 + 11) != 0xFFFFFFFFLL )
  {
    active = CSensorConfigSelector::SwitchActiveConfigurationToFallback(v27);
    if ( active >= 0 )
    {
      Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockExclusive *)v42);
      CBiometricUnit::Deconfigure(this);
      v25 = CBiometricUnit::Configure(this);
      v35 = v25;
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x229,
        (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\biometricunit.cpp",
        (const char *)(unsigned int)active,
        v34);
      v25 = v35;
    }
  }
  if ( v25 >= 0 )
  {
LABEL_58:
    v26 = 1;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EssFprPeripherals>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_EssFprPeripherals>::GetImpl'::`2'::impl) )
    {
      v29 = RtlPublishWnfStateData(WNF_WBIO_BIO_UNITS_STATE_CHANGE, 0, 0, 0) | 0x10000000;
      if ( v29 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x236,
          (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\biometricunit.cpp",
          (const char *)(unsigned int)v29,
          0);
    }
  }
  std::wstring::wstring(&v45, (char *)this + 1636);
  std::wstring::wstring(v47, (char *)this + 1124);
  LOBYTE(v30) = v26;
  LOBYTE(v31) = 1;
  CBioTraceLogging::OnBiometricUnitStateChanged(
    v35,
    v31,
    v30,
    *((_DWORD *)this + 22),
    *((_DWORD *)this + 745),
    (__int64)v47,
    (__int64)&v45);
  std::wstring::_Tidy_deallocate(v47);
  std::wstring::_Tidy_deallocate(&v45);
  v32 = v35;
  Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockExclusive *)v42);
  WppTraceUnwinder__lambda_94f52387e22c6c608242f2f7e8241c5b____::_WppTraceUnwinder__lambda_94f52387e22c6c608242f2f7e8241c5b____(&v43);
  return v32;
}

```

## disassembly

```asm
0x18001c2ac  push    rbp
0x18001c2ae  push    rbx
0x18001c2af  push    rsi
0x18001c2b0  push    rdi
0x18001c2b1  push    r14
0x18001c2b3  push    r15
0x18001c2b5  lea     rbp, [rsp-0A48h]
0x18001c2bd  sub     rsp, 0B48h
0x18001c2c4  mov     rax, cs:__security_cookie
0x18001c2cb  xor     rax, rsp
0x18001c2ce  mov     [rbp+0A70h+var_40], rax
0x18001c2d5  mov     rsi, rcx
0x18001c2d8  xor     r15d, r15d
0x18001c2db  mov     [rsp+0B70h+var_B20], r15d
0x18001c2e0  mov     [rsp+0B70h+var_B14], r15d
0x18001c2e5  movups  xmm0, xmmword ptr cs:aCbiometricunit_21; "CBiometricUnit::Configure"
0x18001c2ec  movups  xmmword ptr [rbp+0A70h+var_60], xmm0
0x18001c2f3  movups  xmm1, xmmword ptr cs:aCbiometricunit_21+0Ah; "Unit::Configure"
0x18001c2fa  movups  xmmword ptr [rbp+0A70h+var_60+0Ah], xmm1
0x18001c301  lea     rax, [rbp+0A70h+var_60]
0x18001c308  mov     [rbp+0A70h+var_AE8], rax
0x18001c30c  lea     rax, [rsp+0B70h+var_B14]
0x18001c311  mov     [rbp+0A70h+var_AE0], rax
0x18001c315  lea     rax, [rsp+0B70h+var_B20]
0x18001c31a  mov     [rbp+0A70h+var_AD8], rax
0x18001c31e  mov     [rbp+0A70h+var_AD0], rcx
0x18001c322  lea     rcx, [rbp+0A70h+var_AE8]
0x18001c326  call    _lambda_94f52387e22c6c608242f2f7e8241c5b___operator__
0x18001c32b  mov     [rsp+0B70h+var_B14], 1
0x18001c333  lea     rax, [rbp+0A70h+var_AE8]
0x18001c337  mov     [rbp+0A70h+var_AF0], rax
0x18001c33b  lea     rdx, [rsp+0B70h+var_AF8]
0x18001c340  mov     rcx, rsi
0x18001c343  call    ?lock_exclusive@lockable_object@winbio@@QEBA?AVSyncLockExclusive@Details@Wrappers@WRL@Microsoft@@XZ; winbio::lockable_object::lock_exclusive(void)
0x18001c348  nop
0x18001c349  mov     rcx, [rsi+0AC0h]; this
0x18001c350  call    ?GetActiveConfiguration@CSensorConfigSelector@@QEAAPEAVCSensorConfig@@XZ; CSensorConfigSelector::GetActiveConfiguration(void)
0x18001c355  mov     r14, rax
0x18001c358  test    rax, rax
0x18001c35b  jz      loc_18001C60E
0x18001c361  cmp     [rax+84h], r15b
0x18001c368  jz      loc_18001C60E
0x18001c36e  lea     rbx, [rsi+0B68h]
0x18001c375  cmp     [rbx], r15
0x18001c378  jnz     loc_18001C442
0x18001c37e  lea     rcx, [rax+0C8h]
0x18001c385  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001c38a  mov     r9, rax
0x18001c38d  lea     rcx, [r14+0A8h]
0x18001c394  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001c399  mov     r8, rax
0x18001c39c  lea     rcx, [r14+88h]
0x18001c3a3  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001c3a8  movups  xmm0, xmmword ptr [r14+68h]
0x18001c3ad  movdqu  xmmword ptr [rbp+0A70h+var_AC0.Data1], xmm0
0x18001c3b2  lea     rcx, [rsi+50h]; struct _WINBIO_UNIT_SCHEMA *
0x18001c3b6  mov     [rsp+0B70h+var_B48], rbx; void **
0x18001c3bb  lea     rdx, [rbp+0A70h+var_AC0]
0x18001c3bf  mov     [rsp+0B70h+var_B50], rdx; struct _GUID *
0x18001c3c4  mov     rdx, rax; unsigned __int16 *
0x18001c3c7  call    ?BioIsoCreateSecureBiometricUnit@@YAJPEAU_WINBIO_UNIT_SCHEMA@@PEBG11U_GUID@@PEAPEAX@Z; BioIsoCreateSecureBiometricUnit(_WINBIO_UNIT_SCHEMA *,ushort const *,ushort const *,ushort const *,_GUID,void * *)
0x18001c3cc  mov     [rsp+0B70h+var_B20], eax
0x18001c3d0  test    eax, eax
0x18001c3d2  js      short loc_18001C442
0x18001c3d4  xorps   xmm0, xmm0
0x18001c3d7  movdqu  xmmword ptr [rbp+0A70h+var_AC0.Data1], xmm0
0x18001c3dc  mov     [rbp+0A70h+var_AB0], r15
0x18001c3e0  lea     rdx, [rbp+0A70h+var_AC0]
0x18001c3e4  mov     ecx, [rsi+58h]; unsigned int
0x18001c3e7  call    ?EnumAccountPolicies@CAccountManager@@SAJIAEAV?$vector@U_WINBIO_ACCOUNT_POLICY@@V?$allocator@U_WINBIO_ACCOUNT_POLICY@@@std@@@std@@@Z; CAccountManager::EnumAccountPolicies(uint,std::vector<_WINBIO_ACCOUNT_POLICY> &)
0x18001c3ec  mov     [rsp+0B70h+var_B20], eax
0x18001c3f0  mov     rdi, 0CCCCCCCCCCCCCCCDh
0x18001c3fa  test    eax, eax
0x18001c3fc  js      short loc_18001C41D
0x18001c3fe  mov     rdx, qword ptr [rbp+0A70h+var_AC0.Data1]; struct _WINBIO_ACCOUNT_POLICY *
0x18001c402  mov     r8, qword ptr [rbp+0A70h+var_AC0.Data4]
0x18001c406  sub     r8, rdx
0x18001c409  sar     r8, 4
0x18001c40d  imul    r8, rdi; unsigned __int64
0x18001c411  mov     rcx, [rbx]; void *
0x18001c414  call    ?BioIsoSetBiometricUnitPolicy@@YAJPEAXPEAU_WINBIO_ACCOUNT_POLICY@@_K@Z; BioIsoSetBiometricUnitPolicy(void *,_WINBIO_ACCOUNT_POLICY *,unsigned __int64)
0x18001c419  mov     [rsp+0B70h+var_B20], eax
0x18001c41d  mov     rcx, qword ptr [rbp+0A70h+var_AC0.Data1]
0x18001c421  test    rcx, rcx
0x18001c424  jz      short loc_18001C442
0x18001c426  mov     rax, [rbp+0A70h+var_AB0]
0x18001c42a  sub     rax, rcx
0x18001c42d  sar     rax, 4
0x18001c431  imul    rax, rdi
0x18001c435  lea     rdx, [rax+rax*4]
0x18001c439  shl     rdx, 4
0x18001c43d  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001c442  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EssFprPeripherals@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EssFprPeripherals@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EssFprPeripherals> `wil::Feature<__WilFeatureTraits_Feature_EssFprPeripherals>::GetImpl(void)'::`2'::impl
0x18001c449  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EssFprPeripherals@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EssFprPeripherals>::__private_IsEnabled(void)
0x18001c44e  test    al, al
0x18001c450  jz      loc_18001C5A7
0x18001c456  cmp     dword ptr [rsi+58h], 8
0x18001c45a  jnz     loc_18001C5A7
0x18001c460  test    byte ptr [rsi+60h], 80h
0x18001c464  jnz     loc_18001C5A7
0x18001c46a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EssScpV1CapabilityCheck@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EssScpV1CapabilityCheck@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EssScpV1CapabilityCheck> `wil::Feature<__WilFeatureTraits_Feature_EssScpV1CapabilityCheck>::GetImpl(void)'::`2'::impl
0x18001c471  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EssScpV1CapabilityCheck@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EssScpV1CapabilityCheck>::__private_IsEnabled(void)
0x18001c476  test    al, al
0x18001c478  jz      loc_18001C53D
0x18001c47e  test    dword ptr [rsi+60h], 200h
0x18001c485  jnz     short loc_18001C48F
0x18001c487  mov     [rsp+0B70h+var_B20], 80098057h
0x18001c48f  mov     eax, cs:dword_18010F170
0x18001c495  cmp     eax, 5
0x18001c498  jbe     loc_18001C5A7
0x18001c49e  mov     rdx, 400000000000h
0x18001c4a8  lea     rcx, dword_18010F170
0x18001c4af  call    _tlgKeywordOn
0x18001c4b4  test    al, al
0x18001c4b6  jz      loc_18001C5A7
0x18001c4bc  mov     [rsp+0B70h+var_B08], 3000000h
0x18001c4c5  lea     rbx, [rsi+64h]
0x18001c4c9  mov     rdx, rbx
0x18001c4cc  lea     rcx, [rbp+0A70h+var_AA0]
0x18001c4d0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001c4d5  lea     rcx, [rbp+0A70h+var_AA0]
0x18001c4d9  call    ?DeviceHasSecureFpRegKey@BioTrustlet@@SA?B_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; BioTrustlet::DeviceHasSecureFpRegKey(std::wstring const &)
0x18001c4de  mov     [rsp+0B70h+var_B1C], al
0x18001c4e2  mov     eax, [rsi+60h]
0x18001c4e5  mov     [rsp+0B70h+var_B10], eax
0x18001c4e9  mov     qword ptr [rbp+0A70h+var_AC0.Data1], rbx
0x18001c4ed  mov     eax, [rsp+0B70h+var_B20]
0x18001c4f1  mov     [rsp+0B70h+var_B18], eax
0x18001c4f5  lea     rax, [rsp+0B70h+var_B08]
0x18001c4fa  mov     [rsp+0B70h+var_B30], rax
0x18001c4ff  lea     rax, [rsp+0B70h+var_B1C]
0x18001c504  mov     [rsp+0B70h+var_B38], rax
0x18001c509  lea     rax, [rsp+0B70h+var_B10]
0x18001c50e  mov     [rsp+0B70h+var_B40], rax
0x18001c513  lea     rax, [rbp+0A70h+var_AC0]
0x18001c517  mov     [rsp+0B70h+var_B48], rax
0x18001c51c  lea     rax, [rsp+0B70h+var_B18]
0x18001c521  mov     [rsp+0B70h+var_B50], rax
0x18001c526  lea     rdx, byte_1800EDB9D
0x18001c52d  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U1@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@3AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<8> const &)
0x18001c532  lea     rcx, [rbp+0A70h+var_AA0]
0x18001c536  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001c53b  jmp     short loc_18001C5A7
0x18001c53d  lea     rdi, [rsi+64h]
0x18001c541  mov     rdx, rdi
0x18001c544  lea     rcx, [rbp+0A70h+var_AA0]
0x18001c548  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001c54d  lea     rcx, [rbp+0A70h+var_AA0]
0x18001c551  call    ?DeviceHasSecureFpRegKey@BioTrustlet@@SA?B_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; BioTrustlet::DeviceHasSecureFpRegKey(std::wstring const &)
0x18001c556  mov     bl, al
0x18001c558  lea     rcx, [rbp+0A70h+var_AA0]
0x18001c55c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001c561  test    bl, bl
0x18001c563  jnz     short loc_18001C5A7
0x18001c565  mov     eax, cs:dword_18010F170
0x18001c56b  cmp     eax, 4
0x18001c56e  jbe     short loc_18001C59F
0x18001c570  mov     qword ptr [rbp+0A70h+var_AC0.Data1], rdi
0x18001c574  mov     [rsp+0B70h+var_B18], r15d
0x18001c579  lea     rax, [rbp+0A70h+var_AC0]
0x18001c57d  mov     [rsp+0B70h+var_B48], rax
0x18001c582  lea     rax, [rsp+0B70h+var_B18]
0x18001c587  mov     [rsp+0B70h+var_B50], rax; int
0x18001c58c  lea     rdx, byte_1800EDB51
0x18001c593  lea     rcx, dword_18010F170
0x18001c59a  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x18001c59f  mov     [rsp+0B70h+var_B20], 80098057h
0x18001c5a7  cmp     [rsp+0B70h+var_B20], r15d
0x18001c5ac  jl      loc_18001C7E7
0x18001c5b2  lea     rcx, [rsi+18h]
0x18001c5b6  lea     rdx, [rsp+0B70h+var_B08]
0x18001c5bb  call    ?shared_from_this@?$enable_shared_from_this@VCBiometricUnit@@@std@@QEAA?AV?$shared_ptr@VCBiometricUnit@@@2@XZ; std::enable_shared_from_this<CBiometricUnit>::shared_from_this(void)
0x18001c5c0  nop
0x18001c5c1  mov     rdx, rax
0x18001c5c4  lea     rcx, [rbp+0A70h+var_AC0]
0x18001c5c8  call    ??$make_unique@VCPresenceMonitorRemote@@V?$shared_ptr@VCBiometricUnit@@@std@@$0A@@std@@YA?AV?$unique_ptr@VCPresenceMonitorRemote@@U?$default_delete@VCPresenceMonitorRemote@@@std@@@0@$$QEAV?$shared_ptr@VCBiometricUnit@@@0@@Z; std::make_unique<CPresenceMonitorRemote,std::shared_ptr<CBiometricUnit>,0>(std::shared_ptr<CBiometricUnit> &&)
0x18001c5cd  mov     rcx, [rax]
0x18001c5d0  mov     [rax], r15
0x18001c5d3  mov     rdx, [rsi+0B30h]
0x18001c5da  mov     [rsi+0B30h], rcx
0x18001c5e1  test    rdx, rdx
0x18001c5e4  jz      short loc_18001C5EB
0x18001c5e6  call    ??R?$default_delete@VCPresenceMonitor@@@std@@QEBAXPEAVCPresenceMonitor@@@Z; std::default_delete<CPresenceMonitor>::operator()(CPresenceMonitor *)
0x18001c5eb  lea     rcx, [rbp+0A70h+var_AC0]
0x18001c5ef  call    ??1?$unique_ptr@VCPresenceMonitorRemote@@U?$default_delete@VCPresenceMonitorRemote@@@std@@@std@@QEAA@XZ; std::unique_ptr<CPresenceMonitorRemote>::~unique_ptr<CPresenceMonitorRemote>(void)
0x18001c5f4  nop
0x18001c5f5  mov     rcx, [rsp+0B70h+var_B00]; this
0x18001c5fa  test    rcx, rcx
0x18001c5fd  jz      short loc_18001C604
0x18001c5ff  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001c604  mov     eax, 1
0x18001c609  jmp     loc_18001C7A7
0x18001c60e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EssFprPeripherals@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EssFprPeripherals@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EssFprPeripherals> `wil::Feature<__WilFeatureTraits_Feature_EssFprPeripherals>::GetImpl(void)'::`2'::impl
0x18001c615  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EssFprPeripherals@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EssFprPeripherals>::__private_IsEnabled(void)
0x18001c61a  mov     ecx, [rsi+58h]
0x18001c61d  test    al, al
0x18001c61f  jz      loc_18001C744
0x18001c625  cmp     ecx, 8
0x18001c628  jz      short loc_18001C633
0x18001c62a  cmp     ecx, 2
0x18001c62d  jnz     loc_18001C70E
0x18001c633  call    ?ShouldBlockNonEssSensors@CEssStateManager@@SA_NXZ; CEssStateManager::ShouldBlockNonEssSensors(void)
0x18001c638  test    al, al
0x18001c63a  jz      loc_18001C70E
0x18001c640  mov     eax, cs:dword_18010F170
0x18001c646  cmp     eax, 4
0x18001c649  jbe     short loc_18001C670
0x18001c64b  mov     [rsp+0B70h+var_B18], r15d
0x18001c650  lea     rax, [rsp+0B70h+var_B18]
0x18001c655  mov     [rsp+0B70h+var_B50], rax
0x18001c65a  xor     r8d, r8d
0x18001c65d  lea     rdx, word_1800EDB0A
0x18001c664  lea     rcx, dword_18010F170
0x18001c66b  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18001c670  mov     [rsp+0B70h+var_B20], 80098057h
0x18001c678  call    ?Instance@CDeviceStateManager@@SAAEAV1@XZ; CDeviceStateManager::Instance(void)
0x18001c67d  mov     rdi, rax
0x18001c680  lea     rdx, [rsi+0A70h]
0x18001c687  lea     rcx, [rbp+0A70h+var_AA0]
0x18001c68b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001c690  mov     rbx, rax
0x18001c693  lea     rcx, [rbp+0A70h+Src]; void *
0x18001c697  lea     rdx, [rsi+50h]; Src
0x18001c69b  mov     r8d, 0A1Ch; Size
0x18001c6a1  call    memcpy_0
0x18001c6a6  mov     r8, rbx
0x18001c6a9  lea     rdx, [rbp+0A70h+Src]; Src
0x18001c6ad  mov     rcx, rdi; _Mtx_t
0x18001c6b0  call    ?CacheBlockedSensor@CDeviceStateManager@@QEAAXU_WINBIO_UNIT_SCHEMA@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CDeviceStateManager::CacheBlockedSensor(_WINBIO_UNIT_SCHEMA,std::wstring)
0x18001c6b5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EssFprPeripherals@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EssFprPeripherals@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EssFprPeripherals> `wil::Feature<__WilFeatureTraits_Feature_EssFprPeripherals>::GetImpl(void)'::`2'::impl
0x18001c6bc  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EssFprPeripherals@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EssFprPeripherals>::__private_IsEnabled(void)
0x18001c6c1  test    al, al
0x18001c6c3  jz      loc_18001C7A4
0x18001c6c9  mov     [rsp+0B70h+var_B50], r15; int
0x18001c6ce  xor     r9d, r9d
0x18001c6d1  xor     r8d, r8d
0x18001c6d4  xor     edx, edx
0x18001c6d6  mov     rcx, cs:WNF_WBIO_BIO_UNITS_STATE_CHANGE
0x18001c6dd  call    cs:__imp_RtlPublishWnfStateData
0x18001c6e3  or      eax, 10000000h
0x18001c6e8  mov     rcx, [rbp+0A78h]; this
0x18001c6ef  jge     loc_18001C7A4
0x18001c6f5  mov     r9d, eax; char *
0x18001c6f8  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\biometrics\\serv"...
0x18001c6ff  mov     edx, 1ECh; void *
0x18001c704  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001c709  jmp     loc_18001C7A4
0x18001c70e  lea     rcx, [rsi+18h]
0x18001c712  lea     rdx, [rsp+0B70h+var_B08]
0x18001c717  call    ?shared_from_this@?$enable_shared_from_this@VCBiometricUnit@@@std@@QEAA?AV?$shared_ptr@VCBiometricUnit@@@2@XZ; std::enable_shared_from_this<CBiometricUnit>::shared_from_this(void)
0x18001c71c  nop
0x18001c71d  mov     rdx, rax
0x18001c720  lea     rcx, [rbp+0A70h+var_AC0]
0x18001c724  call    ??$make_unique@VCPresenceMonitorLocal@@V?$shared_ptr@VCBiometricUnit@@@std@@$0A@@std@@YA?AV?$unique_ptr@VCPresenceMonitorLocal@@U?$default_delete@VCPresenceMonitorLocal@@@std@@@0@$$QEAV?$shared_ptr@VCBiometricUnit@@@0@@Z; std::make_unique<CPresenceMonitorLocal,std::shared_ptr<CBiometricUnit>,0>(std::shared_ptr<CBiometricUnit> &&)
0x18001c729  lea     rcx, [rsi+0B30h]
0x18001c730  mov     rdx, rax
0x18001c733  call    ??$?4VCPresenceMonitorLocal@@U?$default_delete@VCPresenceMonitorLocal@@@std@@$0A@@?$unique_ptr@VCPresenceMonitor@@U?$default_delete@VCPresenceMonitor@@@std@@@std@@QEAAAEAV01@$$QEAV?$unique_ptr@VCPresenceMonitorLocal@@U?$default_delete@VCPresenceMonitorLocal@@@std@@@1@@Z; std::unique_ptr<CPresenceMonitor>::operator=<CPresenceMonitorLocal,std::default_delete<CPresenceMonitorLocal>,0>(std::unique_ptr<CPresenceMonitorLocal> &&)
0x18001c738  lea     rcx, [rbp+0A70h+var_AC0]
0x18001c73c  call    ??1?$unique_ptr@VCPresenceMonitorLocal@@U?$default_delete@VCPresenceMonitorLocal@@@std@@@std@@QEAA@XZ; std::unique_ptr<CPresenceMonitorLocal>::~unique_ptr<CPresenceMonitorLocal>(void)
0x18001c741  nop
0x18001c742  jmp     short loc_18001C795
0x18001c744  cmp     ecx, 8
0x18001c747  jz      short loc_18001C74E
0x18001c749  cmp     ecx, 2
0x18001c74c  jnz     short loc_18001C761
0x18001c74e  call    ?ShouldBlockNonESSSensors@CHardwareManager@@SA_NXZ; CHardwareManager::ShouldBlockNonESSSensors(void)
0x18001c753  test    al, al
0x18001c755  jz      short loc_18001C761
0x18001c757  mov     [rsp+0B70h+var_B20], 80098057h
0x18001c75f  jmp     short loc_18001C7A4
0x18001c761  lea     rcx, [rsi+18h]
0x18001c765  lea     rdx, [rsp+0B70h+var_B08]
0x18001c76a  call    ?shared_from_this@?$enable_shared_from_this@VCBiometricUnit@@@std@@QEAA?AV?$shared_ptr@VCBiometricUnit@@@2@XZ; std::enable_shared_from_this<CBiometricUnit>::shared_from_this(void)
0x18001c76f  nop
0x18001c770  mov     rdx, rax
0x18001c773  lea     rcx, [rbp+0A70h+var_AC0]
0x18001c777  call    ??$make_unique@VCPresenceMonitorLocal@@V?$shared_ptr@VCBiometricUnit@@@std@@$0A@@std@@YA?AV?$unique_ptr@VCPresenceMonitorLocal@@U?$default_delete@VCPresenceMonitorLocal@@@std@@@0@$$QEAV?$shared_ptr@VCBiometricUnit@@@0@@Z; std::make_unique<CPresenceMonitorLocal,std::shared_ptr<CBiometricUnit>,0>(std::shared_ptr<CBiometricUnit> &&)
0x18001c77c  lea     rcx, [rsi+0B30h]
0x18001c783  mov     rdx, rax
0x18001c786  call    ??$?4VCPresenceMonitorLocal@@U?$default_delete@VCPresenceMonitorLocal@@@std@@$0A@@?$unique_ptr@VCPresenceMonitor@@U?$default_delete@VCPresenceMonitor@@@std@@@std@@QEAAAEAV01@$$QEAV?$unique_ptr@VCPresenceMonitorLocal@@U?$default_delete@VCPresenceMonitorLocal@@@std@@@1@@Z; std::unique_ptr<CPresenceMonitor>::operator=<CPresenceMonitorLocal,std::default_delete<CPresenceMonitorLocal>,0>(std::unique_ptr<CPresenceMonitorLocal> &&)
0x18001c78b  lea     rcx, [rbp+0A70h+var_AC0]
0x18001c78f  call    ??1?$unique_ptr@VCPresenceMonitorLocal@@U?$default_delete@VCPresenceMonitorLocal@@@std@@@std@@QEAA@XZ; std::unique_ptr<CPresenceMonitorLocal>::~unique_ptr<CPresenceMonitorLocal>(void)
0x18001c794  nop
0x18001c795  mov     rcx, [rsp+0B70h+var_B00]; this
0x18001c79a  test    rcx, rcx
0x18001c79d  jz      short loc_18001C7A4
0x18001c79f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001c7a4  mov     eax, r15d
0x18001c7a7  mov     [rsi+0BA4h], eax
0x18001c7ad  cmp     [rsp+0B70h+var_B20], r15d
0x18001c7b2  jl      short loc_18001C7E7
0x18001c7b4  mov     rdx, r14; struct CSensorConfig *
0x18001c7b7  mov     rcx, [rsi+0A90h]; this
0x18001c7be  call    ?Configure@CPipeline@@QEAAJPEAVCSensorConfig@@@Z; CPipeline::Configure(CSensorConfig *)
0x18001c7c3  mov     [rsp+0B70h+var_B20], eax
0x18001c7c7  test    eax, eax
0x18001c7c9  js      short loc_18001C835
0x18001c7cb  mov     byte ptr [rsi+0A98h], 1
0x18001c7d2  mov     rdx, r14; struct CSensorConfig *
0x18001c7d5  mov     rcx, [rsi+0A90h]; this
  ... truncated ...
```
