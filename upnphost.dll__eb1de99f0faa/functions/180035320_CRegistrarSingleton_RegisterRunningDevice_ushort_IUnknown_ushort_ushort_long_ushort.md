# CRegistrarSingleton::RegisterRunningDevice(ushort *,IUnknown *,ushort *,ushort *,long,ushort * *)

- ea: `0x180035320`
- end: `0x18003575d`
- name: `?RegisterRunningDevice@CRegistrarSingleton@@UEAAJPEAGPEAUIUnknown@@00JPEAPEAG@Z`
- size: `1085`
- prototype: `__int64 __usercall@<rax>(CRegistrarSingleton *__hidden this@<rcx>, unsigned __int16 *@<rdx>, struct IUnknown *@<r8>, unsigned __int16 *@<r9>, unsigned __int16 *, int, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `21`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000db4c`
- `0x180013180`
- `0x180019c98`
- `0x18001c6bc`
- `0x18001e478`
- `0x180029cb0`
- `0x18002bed0`
- `0x18002f384`
- `0x18002f684`
- `0x1800310ac`
- `0x180031134`
- `0x180035320`
- `0x180038be4`
- `0x180038ce4`
- `0x1800394b4`
- `0x180039a84`
- `0x18003a560`
- `0x18004ae14`
- `0x18004b99c`
- `0x18004d770`
- `0x180055010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18003561a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18003561a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800353f9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180035409`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800353f9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180035409`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180035487`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003568b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180035735`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180035487`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003568b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180035735`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035497`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035634`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035647`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035497`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035634`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035647`

## pseudocode

```c
__int64 __fastcall CRegistrarSingleton::RegisterRunningDevice(
        struct _RTL_CRITICAL_SECTION *this,
        unsigned __int16 **a2,
        struct IUnknown *a3,
        unsigned __int16 *a4,
        unsigned __int16 *pbstr,
        int a6,
        unsigned __int16 **a7)
{
  wchar_t *v9; // rcx
  __int64 result; // rax
  int IsAllowedCOMCallLocality; // edi
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rcx
  int v13; // eax
  unsigned int v14; // r15d
  int v15; // esi
  HANDLE LockSemaphore; // rcx
  HANDLE v17; // rcx
  struct IUnknown *v18; // r13
  int i; // r15d
  STRSAFE_PCNZWCH v20; // rcx
  LPVOID pv; // [rsp+40h] [rbp-51h] BYREF
  int v22; // [rsp+48h] [rbp-49h] BYREF
  unsigned __int16 **v23; // [rsp+50h] [rbp-41h] BYREF
  struct IUnknown *v24; // [rsp+58h] [rbp-39h] BYREF
  unsigned __int16 *v25; // [rsp+60h] [rbp-31h] BYREF
  unsigned __int16 **v26; // [rsp+68h] [rbp-29h] BYREF
  unsigned __int16 **v27; // [rsp+70h] [rbp-21h]
  struct _GUID v28; // [rsp+78h] [rbp-19h] BYREF

  v27 = a7;
  v25 = a4;
  v24 = a3;
  v23 = a2;
  v26 = a2;
  v9 = (wchar_t *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 0x40) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, WPP_0f8e6464007c3e0bdd6d585d5cfe4b6e_Traceguids);
    v9 = (wchar_t *)WPP_GLOBAL_Control;
  }
  if ( !CRegistrarSingleton::m_fRegObjDeleted )
  {
    if ( !LODWORD(this[3].SpinCount) )
    {
      result = CServiceModule::CompleteInitialization((struct IUnknown *)v9);
      if ( (int)result < 0 )
        return result;
    }
    EnterCriticalSection(this + 5);
    EnterCriticalSection(this + 4);
    if ( !LODWORD(this[3].SpinCount) )
    {
      IsAllowedCOMCallLocality = -2147467259;
LABEL_17:
      LeaveCriticalSection(this + 4);
LABEL_58:
      LeaveCriticalSection(this + 5);
      return (unsigned int)IsAllowedCOMCallLocality;
    }
    IsAllowedCOMCallLocality = HrIsAllowedCOMCallLocality(3);
    if ( IsAllowedCOMCallLocality < 0
      || (IsAllowedCOMCallLocality = HrValidateResourcePath(pbstr), IsAllowedCOMCallLocality < 0) )
    {
      v15 = 0;
      goto LABEL_45;
    }
    DebugInfo = this[3].DebugInfo;
    pv = 0;
    IsAllowedCOMCallLocality = (*(__int64 (__fastcall **)(PRTL_CRITICAL_SECTION_DEBUG, unsigned __int16 **, unsigned __int16 *, LPVOID *))(*(_QWORD *)&DebugInfo->Type + 40LL))(
                                 DebugInfo,
                                 a2,
                                 pbstr,
                                 &pv);
    if ( IsAllowedCOMCallLocality < 0 )
    {
      HrSetErrorInfo((const unsigned __int16 *)pv, &IID_IUPnPRegistrar);
      goto LABEL_17;
    }
    if ( pv )
    {
      CoTaskMemFree(pv);
      pv = 0;
    }
    v13 = CheckRegistryForLifeTime((unsigned int *)&a6);
    v14 = a6;
    if ( v13 )
    {
      if ( a6 )
      {
        v15 = 0;
        if ( a6 < 900 )
        {
          IsAllowedCOMCallLocality = -2147024809;
          goto LABEL_45;
        }
        goto LABEL_24;
      }
      v14 = 1800;
    }
    v15 = 0;
LABEL_24:
    LockSemaphore = this[2].LockSemaphore;
    v28 = 0;
    IsAllowedCOMCallLocality = (*(__int64 (__fastcall **)(HANDLE, unsigned __int16 **, unsigned __int16 *, struct _GUID *, _DWORD, _DWORD))(*(_QWORD *)LockSemaphore + 24LL))(
                                 LockSemaphore,
                                 v23,
                                 pbstr,
                                 &v28,
                                 0,
                                 0);
    if ( IsAllowedCOMCallLocality >= 0 )
    {
      v17 = this[2].LockSemaphore;
      v23 = 0;
      v22 = 0;
      IsAllowedCOMCallLocality = (*(__int64 (__fastcall **)(HANDLE, struct _GUID *, int *, unsigned __int16 ***))(*(_QWORD *)v17 + 64LL))(
                                   v17,
                                   &v28,
                                   &v22,
                                   &v23);
      if ( IsAllowedCOMCallLocality >= 0 && v23 )
      {
        v18 = v24;
        IsAllowedCOMCallLocality = CDeviceManager::HrAddRunningDevice(
                                     (CDeviceManager *)&this->LockCount,
                                     &v28,
                                     v24,
                                     v25,
                                     v22,
                                     v23);
        LODWORD(v24) = IsAllowedCOMCallLocality;
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AddUpnpTelemetry>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AddUpnpTelemetry>::GetImpl'::`2'::impl) )
        {
          LODWORD(v25) = 0;
          LODWORD(pv) = 1;
          UpnpHostTelemetry::RegisterDevice<unsigned short * &,int,int,long &>(&v26, &pv, &v25, &v24);
        }
        if ( IsAllowedCOMCallLocality >= 0 )
        {
          IsAllowedCOMCallLocality = CRegistrarSingleton::HrStoreDeviceControlHttpHeadersObject(
                                       (CRegistrarSingleton *)this,
                                       &v28,
                                       v18);
          if ( IsAllowedCOMCallLocality >= 0 )
          {
            IsAllowedCOMCallLocality = CRegistrarSingleton::HrStoreDeviceControlSsdpHeadersObject(
                                         (CRegistrarSingleton *)this,
                                         &v28,
                                         v18);
            if ( IsAllowedCOMCallLocality >= 0 )
            {
              IsAllowedCOMCallLocality = (*(__int64 (__fastcall **)(HANDLE, struct _GUID *, _QWORD))(*(_QWORD *)this[2].LockSemaphore + 32LL))(
                                           this[2].LockSemaphore,
                                           &v28,
                                           v14);
              if ( IsAllowedCOMCallLocality >= 0 )
              {
                pv = 0;
                IsAllowedCOMCallLocality = HrPhysicalDeviceIdentifierToString(&v28, (struct CUString *)&pv);
                if ( IsAllowedCOMCallLocality >= 0 )
                  IsAllowedCOMCallLocality = CUString::HrGetBSTR((CUString *)&pv, v27);
                free(pv);
              }
            }
          }
        }
        for ( i = 0; i < v22; ++i )
          CoTaskMemFree(v23[i]);
        CoTaskMemFree(v23);
      }
      if ( IsAllowedCOMCallLocality < 0
        && CRegistrarSingleton::HrUnregisterDeviceByPDI((CRegistrarSingleton *)this, &v28, 1) >= 0 )
      {
        v15 = 1;
      }
    }
LABEL_45:
    LeaveCriticalSection(this + 4);
    if ( v15 )
    {
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1>::GetImpl'::`2'::impl)
        || g_pVars )
      {
        BaseHttpListener::DecrementURLCount(*(BaseHttpListener **)g_pVars);
      }
      else
      {
        IsAllowedCOMCallLocality = -2147467259;
        v20 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control )
          goto LABEL_58;
        if ( (WPP_GLOBAL_Control[14] & 1) == 0 )
        {
LABEL_55:
          if ( v20 != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (v20[14] & 1) != 0 )
            WPP_SF_d(
              *((_QWORD *)v20 + 2),
              47,
              WPP_0f8e6464007c3e0bdd6d585d5cfe4b6e_Traceguids,
              (unsigned int)IsAllowedCOMCallLocality);
          goto LABEL_58;
        }
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          46,
          (unsigned int)WPP_0f8e6464007c3e0bdd6d585d5cfe4b6e_Traceguids,
          (unsigned int)"CRegistrarSingleton::RegisterRunningDevice: g_pVars is null.",
          5);
      }
    }
    if ( !IsAllowedCOMCallLocality )
      goto LABEL_58;
    v20 = WPP_GLOBAL_Control;
    goto LABEL_55;
  }
  if ( v9 != (wchar_t *)&WPP_GLOBAL_Control && (v9[14] & 0x40) != 0 )
    WPP_SF_(*((_QWORD *)v9 + 2), 45, WPP_0f8e6464007c3e0bdd6d585d5cfe4b6e_Traceguids);
  return 2147500037LL;
}

```

## disassembly

```asm
0x180035320  push    rbp
0x180035322  push    rbx
0x180035323  push    rsi
0x180035324  push    rdi
0x180035325  push    r12
0x180035327  push    r13
0x180035329  push    r14
0x18003532b  push    r15
0x18003532d  lea     rbp, [rsp-7]
0x180035332  sub     rsp, 98h
0x180035339  mov     rax, cs:__security_cookie
0x180035340  xor     rax, rsp
0x180035343  mov     [rbp+3Fh+var_48], rax
0x180035347  mov     rax, [rbp+3Fh+arg_30]
0x18003534b  mov     rsi, rdx
0x18003534e  mov     r13, [rbp+3Fh+pbstr]
0x180035352  mov     r14, rcx
0x180035355  mov     [rbp+3Fh+var_60], rax
0x180035359  mov     [rbp+3Fh+var_70], r9
0x18003535d  mov     [rbp+3Fh+var_78], r8
0x180035361  mov     [rbp+3Fh+var_80], rdx
0x180035365  mov     [rbp+3Fh+var_68], rdx
0x180035369  mov     rcx, cs:WPP_GLOBAL_Control
0x180035370  lea     rax, WPP_GLOBAL_Control
0x180035377  cmp     rcx, rax
0x18003537a  jz      short loc_1800353A5
0x18003537c  test    byte ptr [rcx+1Ch], 40h
0x180035380  jz      short loc_1800353A5
0x180035382  mov     rcx, [rcx+10h]
0x180035386  lea     r8, WPP_0f8e6464007c3e0bdd6d585d5cfe4b6e_Traceguids
0x18003538d  mov     edx, 2Ch ; ','
0x180035392  call    WPP_SF_
0x180035397  mov     rcx, cs:WPP_GLOBAL_Control; this
0x18003539e  lea     rax, WPP_GLOBAL_Control
0x1800353a5  cmp     cs:?m_fRegObjDeleted@CRegistrarSingleton@@1HA, 0; int CRegistrarSingleton::m_fRegObjDeleted
0x1800353ac  jz      short loc_1800353D8
0x1800353ae  cmp     rcx, rax
0x1800353b1  jz      short loc_1800353CE
0x1800353b3  test    byte ptr [rcx+1Ch], 40h
0x1800353b7  jz      short loc_1800353CE
0x1800353b9  mov     rcx, [rcx+10h]
0x1800353bd  lea     r8, WPP_0f8e6464007c3e0bdd6d585d5cfe4b6e_Traceguids
0x1800353c4  mov     edx, 2Dh ; '-'
0x1800353c9  call    WPP_SF_
0x1800353ce  mov     eax, 80004005h
0x1800353d3  jmp     loc_18003573D
0x1800353d8  cmp     dword ptr [r14+98h], 0
0x1800353e0  jnz     short loc_1800353EF
0x1800353e2  call    ?CompleteInitialization@CServiceModule@@QEAAJXZ; CServiceModule::CompleteInitialization(void)
0x1800353e7  test    eax, eax
0x1800353e9  js      loc_18003573D
0x1800353ef  lea     rbx, [r14+0C8h]
0x1800353f6  mov     rcx, rbx; lpCriticalSection
0x1800353f9  call    cs:__imp_EnterCriticalSection
0x1800353ff  lea     r12, [r14+0A0h]
0x180035406  mov     rcx, r12; lpCriticalSection
0x180035409  call    cs:__imp_EnterCriticalSection
0x18003540f  cmp     dword ptr [r14+98h], 0
0x180035417  jnz     short loc_180035420
0x180035419  mov     edi, 80004005h
0x18003541e  jmp     short loc_180035484
0x180035420  mov     ecx, 3
0x180035425  call    ?HrIsAllowedCOMCallLocality@@YAJW4CALL_LOCALITY@@@Z; HrIsAllowedCOMCallLocality(CALL_LOCALITY)
0x18003542a  mov     edi, eax
0x18003542c  mov     r15d, 1
0x180035432  test    eax, eax
0x180035434  js      loc_1800356F1
0x18003543a  mov     rcx, r13; pbstr
0x18003543d  call    ?HrValidateResourcePath@@YAJPEAG@Z; HrValidateResourcePath(ushort *)
0x180035442  mov     edi, eax
0x180035444  test    eax, eax
0x180035446  js      loc_1800356F1
0x18003544c  mov     rcx, [r14+78h]
0x180035450  lea     r9, [rbp+3Fh+pv]
0x180035454  mov     [rbp+3Fh+pv], 0
0x18003545c  mov     r8, r13
0x18003545f  mov     rdx, rsi
0x180035462  mov     rax, [rcx]
0x180035465  mov     rax, [rax+28h]
0x180035469  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003546e  mov     rcx, [rbp+3Fh+pv]; unsigned __int16 *
0x180035472  mov     edi, eax
0x180035474  test    eax, eax
0x180035476  jns     short loc_180035492
0x180035478  lea     rdx, IID_IUPnPRegistrar; struct _GUID *
0x18003547f  call    ?HrSetErrorInfo@@YAJPEBGAEBU_GUID@@@Z; HrSetErrorInfo(ushort const *,_GUID const &)
0x180035484  mov     rcx, r12; lpCriticalSection
0x180035487  call    cs:__imp_LeaveCriticalSection
0x18003548d  jmp     loc_180035732
0x180035492  test    rcx, rcx
0x180035495  jz      short loc_1800354A5
0x180035497  call    cs:__imp_CoTaskMemFree
0x18003549d  mov     [rbp+3Fh+pv], 0
0x1800354a5  lea     rcx, [rbp+3Fh+arg_28]; int *
0x1800354a9  call    ?CheckRegistryForLifeTime@@YAHPEAJ@Z; CheckRegistryForLifeTime(long *)
0x1800354ae  mov     r15d, [rbp+3Fh+arg_28]
0x1800354b2  test    eax, eax
0x1800354b4  jz      short loc_1800354C5
0x1800354b6  test    r15d, r15d
0x1800354b9  jnz     loc_18003566E
0x1800354bf  mov     r15d, 708h
0x1800354c5  xor     esi, esi
0x1800354c7  mov     rcx, [r14+68h]
0x1800354cb  lea     r9, [rbp+3Fh+var_58]
0x1800354cf  mov     rdx, [rbp+3Fh+var_80]
0x1800354d3  xorps   xmm0, xmm0
0x1800354d6  movups  xmmword ptr [rbp+3Fh+var_58.Data1], xmm0
0x1800354da  mov     dword ptr [rsp+0D0h+var_A8], 0
0x1800354e2  mov     r8, r13
0x1800354e5  mov     rax, [rcx]
0x1800354e8  mov     [rsp+0D0h+var_B0], 0
0x1800354f0  mov     rax, [rax+18h]
0x1800354f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800354f9  mov     edi, eax
0x1800354fb  test    eax, eax
0x1800354fd  js      loc_180035682
0x180035503  mov     rcx, [r14+68h]
0x180035507  lea     r9, [rbp+3Fh+var_80]
0x18003550b  mov     [rbp+3Fh+var_80], 0
0x180035513  lea     r8, [rbp+3Fh+var_88]
0x180035517  mov     [rbp+3Fh+var_88], 0
0x18003551e  lea     rdx, [rbp+3Fh+var_58]
0x180035522  mov     rax, [rcx]
0x180035525  mov     rax, [rax+40h]
0x180035529  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003552e  mov     edi, eax
0x180035530  test    eax, eax
0x180035532  js      loc_18003564D
0x180035538  mov     rax, [rbp+3Fh+var_80]
0x18003553c  test    rax, rax
0x18003553f  jz      loc_18003564D
0x180035545  mov     r13, [rbp+3Fh+var_78]
0x180035549  lea     rcx, [r14+8]; this
0x18003554d  mov     r9, [rbp+3Fh+var_70]; unsigned __int16 *
0x180035551  lea     rdx, [rbp+3Fh+var_58]; struct _GUID *
0x180035555  mov     [rsp+0D0h+var_A8], rax; unsigned __int16 **
0x18003555a  mov     r8, r13; struct IUnknown *
0x18003555d  mov     eax, [rbp+3Fh+var_88]
0x180035560  mov     [rsp+0D0h+var_B0], eax; int
0x180035564  call    ?HrAddRunningDevice@CDeviceManager@@QEAAJAEBU_GUID@@PEAUIUnknown@@PEBGJPEAPEAG@Z; CDeviceManager::HrAddRunningDevice(_GUID const &,IUnknown *,ushort const *,long,ushort * *)
0x180035569  mov     edi, eax
0x18003556b  mov     dword ptr [rbp+3Fh+var_78], eax
0x18003556e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AddUpnpTelemetry@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AddUpnpTelemetry@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AddUpnpTelemetry> `wil::Feature<__WilFeatureTraits_Feature_AddUpnpTelemetry>::GetImpl(void)'::`2'::impl
0x180035575  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AddUpnpTelemetry@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AddUpnpTelemetry>::__private_IsEnabled(void)
0x18003557a  test    al, al
0x18003557c  jz      short loc_1800355A1
0x18003557e  lea     r9, [rbp+3Fh+var_78]
0x180035582  mov     dword ptr [rbp+3Fh+var_70], 0
0x180035589  lea     r8, [rbp+3Fh+var_70]
0x18003558d  mov     dword ptr [rbp+3Fh+pv], 1
0x180035594  lea     rdx, [rbp+3Fh+pv]
0x180035598  lea     rcx, [rbp+3Fh+var_68]
0x18003559c  call    ??$RegisterDevice@AEAPEAGHHAEAJ@UpnpHostTelemetry@@SAXAEAPEAG$$QEAH1AEAJ@Z; UpnpHostTelemetry::RegisterDevice<ushort * &,int,int,long &>(ushort * &,int &&,int &&,long &)
0x1800355a1  test    edi, edi
0x1800355a3  js      short loc_180035620
0x1800355a5  mov     r8, r13; struct IUnknown *
0x1800355a8  lea     rdx, [rbp+3Fh+var_58]; struct _GUID *
0x1800355ac  mov     rcx, r14; this
0x1800355af  call    ?HrStoreDeviceControlHttpHeadersObject@CRegistrarSingleton@@AEAAJAEAU_GUID@@PEAUIUnknown@@@Z; CRegistrarSingleton::HrStoreDeviceControlHttpHeadersObject(_GUID &,IUnknown *)
0x1800355b4  mov     edi, eax
0x1800355b6  test    eax, eax
0x1800355b8  js      short loc_180035620
0x1800355ba  mov     r8, r13; struct IUnknown *
0x1800355bd  lea     rdx, [rbp+3Fh+var_58]; struct _GUID *
0x1800355c1  mov     rcx, r14; this
0x1800355c4  call    ?HrStoreDeviceControlSsdpHeadersObject@CRegistrarSingleton@@AEAAJAEAU_GUID@@PEAUIUnknown@@@Z; CRegistrarSingleton::HrStoreDeviceControlSsdpHeadersObject(_GUID &,IUnknown *)
0x1800355c9  mov     edi, eax
0x1800355cb  test    eax, eax
0x1800355cd  js      short loc_180035620
0x1800355cf  mov     rcx, [r14+68h]
0x1800355d3  lea     rdx, [rbp+3Fh+var_58]
0x1800355d7  mov     r8d, r15d
0x1800355da  mov     rax, [rcx]
0x1800355dd  mov     rax, [rax+20h]
0x1800355e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800355e6  mov     edi, eax
0x1800355e8  test    eax, eax
0x1800355ea  js      short loc_180035620
0x1800355ec  lea     rdx, [rbp+3Fh+pv]; this
0x1800355f0  mov     [rbp+3Fh+pv], 0
0x1800355f8  lea     rcx, [rbp+3Fh+var_58]; struct _GUID *
0x1800355fc  call    ?HrPhysicalDeviceIdentifierToString@@YAJAEBU_GUID@@AEAVCUString@@@Z; HrPhysicalDeviceIdentifierToString(_GUID const &,CUString &)
0x180035601  mov     edi, eax
0x180035603  test    eax, eax
0x180035605  js      short loc_180035616
0x180035607  mov     rdx, [rbp+3Fh+var_60]; unsigned __int16 **
0x18003560b  lea     rcx, [rbp+3Fh+pv]; this
0x18003560f  call    ?HrGetBSTR@CUString@@QEBAJPEAPEAG@Z; CUString::HrGetBSTR(ushort * *)
0x180035614  mov     edi, eax
0x180035616  mov     rcx, [rbp+3Fh+pv]; Block
0x18003561a  call    cs:__imp_free
0x180035620  xor     r15d, r15d
0x180035623  cmp     [rbp+3Fh+var_88], r15d
0x180035627  jle     short loc_180035643
0x180035629  mov     rcx, [rbp+3Fh+var_80]
0x18003562d  movsxd  rdx, r15d
0x180035630  mov     rcx, [rcx+rdx*8]; pv
0x180035634  call    cs:__imp_CoTaskMemFree
0x18003563a  inc     r15d
0x18003563d  cmp     r15d, [rbp+3Fh+var_88]
0x180035641  jl      short loc_180035629
0x180035643  mov     rcx, [rbp+3Fh+var_80]; pv
0x180035647  call    cs:__imp_CoTaskMemFree
0x18003564d  test    edi, edi
0x18003564f  jns     short loc_180035682
0x180035651  mov     r15d, 1
0x180035657  lea     rdx, [rbp+3Fh+var_58]; struct _GUID *
0x18003565b  mov     r8d, r15d; int
0x18003565e  mov     rcx, r14; this
0x180035661  call    ?HrUnregisterDeviceByPDI@CRegistrarSingleton@@AEAAJAEAU_GUID@@H@Z; CRegistrarSingleton::HrUnregisterDeviceByPDI(_GUID &,int)
0x180035666  test    eax, eax
0x180035668  cmovns  esi, r15d
0x18003566c  jmp     short loc_180035688
0x18003566e  xor     esi, esi
0x180035670  cmp     r15d, 384h
0x180035677  jge     loc_1800354C7
0x18003567d  mov     edi, 80070057h
0x180035682  mov     r15d, 1
0x180035688  mov     rcx, r12; lpCriticalSection
0x18003568b  call    cs:__imp_LeaveCriticalSection
0x180035691  test    esi, esi
0x180035693  jz      short loc_1800356FD
0x180035695  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1> `wil::Feature<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1>::GetImpl(void)'::`2'::impl
0x18003569c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1>::__private_IsEnabled(void)
0x1800356a1  mov     rcx, cs:?g_pVars@@3PEAVCGlobalVariables@@EA; CGlobalVariables * g_pVars
0x1800356a8  test    al, al
0x1800356aa  jz      short loc_1800356F5
0x1800356ac  test    rcx, rcx
0x1800356af  jnz     short loc_1800356F5
0x1800356b1  mov     edi, 80004005h
0x1800356b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800356bd  lea     rsi, WPP_GLOBAL_Control
0x1800356c4  cmp     rcx, rsi
0x1800356c7  jz      short loc_180035732
0x1800356c9  test    [rcx+1Ch], r15b
0x1800356cd  jz      short loc_18003570F
0x1800356cf  mov     rcx, [rcx+10h]
0x1800356d3  lea     r9, aCregistrarsing_0; "CRegistrarSingleton::RegisterRunningDev"...
0x1800356da  mov     edx, 2Eh ; '.'
0x1800356df  mov     [rsp+0D0h+var_B0], edi
0x1800356e3  lea     r8, WPP_0f8e6464007c3e0bdd6d585d5cfe4b6e_Traceguids
0x1800356ea  call    WPP_SF_sd
0x1800356ef  jmp     short loc_180035704
0x1800356f1  xor     esi, esi
0x1800356f3  jmp     short loc_180035688
0x1800356f5  mov     rcx, [rcx]; this
0x1800356f8  call    ?DecrementURLCount@BaseHttpListener@@QEAAJXZ; BaseHttpListener::DecrementURLCount(void)
0x1800356fd  lea     rsi, WPP_GLOBAL_Control
0x180035704  test    edi, edi
0x180035706  jz      short loc_180035732
0x180035708  mov     rcx, cs:WPP_GLOBAL_Control
0x18003570f  cmp     rcx, rsi
0x180035712  jz      short loc_180035732
0x180035714  test    [rcx+1Ch], r15b
0x180035718  jz      short loc_180035732
0x18003571a  mov     rcx, [rcx+10h]
0x18003571e  lea     r8, WPP_0f8e6464007c3e0bdd6d585d5cfe4b6e_Traceguids
0x180035725  mov     edx, 2Fh ; '/'
0x18003572a  mov     r9d, edi
0x18003572d  call    WPP_SF_d
0x180035732  mov     rcx, rbx; lpCriticalSection
0x180035735  call    cs:__imp_LeaveCriticalSection
0x18003573b  mov     eax, edi
0x18003573d  mov     rcx, [rbp+3Fh+var_48]
0x180035741  xor     rcx, rsp; StackCookie
0x180035744  call    __security_check_cookie
0x180035749  add     rsp, 98h
0x180035750  pop     r15
0x180035752  pop     r14
0x180035754  pop     r13
0x180035756  pop     r12
0x180035758  pop     rdi
0x180035759  pop     rsi
0x18003575a  pop     rbx
0x18003575b  pop     rbp
0x18003575c  retn
```
