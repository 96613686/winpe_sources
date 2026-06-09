# CRegistrarSingleton::RegisterRunningDevice(ushort *,IUnknown *,ushort *,ushort *,long,ushort * *)

- ea: `0x180037620`
- end: `0x180037a98`
- name: `?RegisterRunningDevice@CRegistrarSingleton@@UEAAJPEAGPEAUIUnknown@@00JPEAPEAG@Z`
- size: `1144`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this, unsigned __int16 **, struct IUnknown *, unsigned __int16 *, unsigned __int16 *pbstr, int, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `21`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800071c0`
- `0x18000e910`
- `0x18001158c`
- `0x1800134e4`
- `0x1800200f4`
- `0x18002b050`
- `0x18002d6f4`
- `0x180030cdc`
- `0x180030fd0`
- `0x180032d28`
- `0x180032db4`
- `0x180037620`
- `0x18003b0bc`
- `0x18003b1cc`
- `0x18003ba4c`
- `0x18003c018`
- `0x18003cb60`
- `0x18004e098`
- `0x18004ec90`
- `0x180050bc0`
- `0x180059010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180037936`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180037936`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800376f9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003770f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800376f9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003770f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180037793`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800379b9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180037a69`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180037793`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800379b9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180037a69`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800377a9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037956`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003796f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800377a9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037956`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003796f`

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
      result = CServiceModule::CompleteInitialization((CServiceModule *)v9);
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
    v13 = CheckRegistryForLifeTime(&a6);
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
0x180037620  push    rbp
0x180037622  push    rbx
0x180037623  push    rsi
0x180037624  push    rdi
0x180037625  push    r12
0x180037627  push    r13
0x180037629  push    r14
0x18003762b  push    r15
0x18003762d  lea     rbp, [rsp-7]
0x180037632  sub     rsp, 98h
0x180037639  mov     rax, cs:__security_cookie
0x180037640  xor     rax, rsp
0x180037643  mov     [rbp+3Fh+var_48], rax
0x180037647  mov     rax, [rbp+3Fh+arg_30]
0x18003764b  mov     rsi, rdx
0x18003764e  mov     r13, [rbp+3Fh+pbstr]
0x180037652  mov     r14, rcx
0x180037655  mov     [rbp+3Fh+var_60], rax
0x180037659  mov     [rbp+3Fh+var_70], r9
0x18003765d  mov     [rbp+3Fh+var_78], r8
0x180037661  mov     [rbp+3Fh+var_80], rdx
0x180037665  mov     [rbp+3Fh+var_68], rdx
0x180037669  mov     rcx, cs:WPP_GLOBAL_Control
0x180037670  lea     rax, WPP_GLOBAL_Control
0x180037677  cmp     rcx, rax
0x18003767a  jz      short loc_1800376A5
0x18003767c  test    byte ptr [rcx+1Ch], 40h
0x180037680  jz      short loc_1800376A5
0x180037682  mov     rcx, [rcx+10h]
0x180037686  lea     r8, WPP_0f8e6464007c3e0bdd6d585d5cfe4b6e_Traceguids
0x18003768d  mov     edx, 2Ch ; ','
0x180037692  call    WPP_SF_
0x180037697  mov     rcx, cs:WPP_GLOBAL_Control; this
0x18003769e  lea     rax, WPP_GLOBAL_Control
0x1800376a5  cmp     cs:?m_fRegObjDeleted@CRegistrarSingleton@@1HA, 0; int CRegistrarSingleton::m_fRegObjDeleted
0x1800376ac  jz      short loc_1800376D8
0x1800376ae  cmp     rcx, rax
0x1800376b1  jz      short loc_1800376CE
0x1800376b3  test    byte ptr [rcx+1Ch], 40h
0x1800376b7  jz      short loc_1800376CE
0x1800376b9  mov     rcx, [rcx+10h]
0x1800376bd  lea     r8, WPP_0f8e6464007c3e0bdd6d585d5cfe4b6e_Traceguids
0x1800376c4  mov     edx, 2Dh ; '-'
0x1800376c9  call    WPP_SF_
0x1800376ce  mov     eax, 80004005h
0x1800376d3  jmp     loc_180037A77
0x1800376d8  cmp     dword ptr [r14+98h], 0
0x1800376e0  jnz     short loc_1800376EF
0x1800376e2  call    ?CompleteInitialization@CServiceModule@@QEAAJXZ; CServiceModule::CompleteInitialization(void)
0x1800376e7  test    eax, eax
0x1800376e9  js      loc_180037A77
0x1800376ef  lea     rbx, [r14+0C8h]
0x1800376f6  mov     rcx, rbx; lpCriticalSection
0x1800376f9  call    cs:__imp_EnterCriticalSection
0x180037700  nop     dword ptr [rax+rax+00h]
0x180037705  lea     r12, [r14+0A0h]
0x18003770c  mov     rcx, r12; lpCriticalSection
0x18003770f  call    cs:__imp_EnterCriticalSection
0x180037716  nop     dword ptr [rax+rax+00h]
0x18003771b  cmp     dword ptr [r14+98h], 0
0x180037723  jnz     short loc_18003772C
0x180037725  mov     edi, 80004005h
0x18003772a  jmp     short loc_180037790
0x18003772c  mov     ecx, 3
0x180037731  call    ?HrIsAllowedCOMCallLocality@@YAJW4CALL_LOCALITY@@@Z; HrIsAllowedCOMCallLocality(CALL_LOCALITY)
0x180037736  mov     edi, eax
0x180037738  mov     r15d, 1
0x18003773e  test    eax, eax
0x180037740  js      loc_180037A25
0x180037746  mov     rcx, r13; pbstr
0x180037749  call    ?HrValidateResourcePath@@YAJPEAG@Z; HrValidateResourcePath(ushort *)
0x18003774e  mov     edi, eax
0x180037750  test    eax, eax
0x180037752  js      loc_180037A25
0x180037758  mov     rcx, [r14+78h]
0x18003775c  lea     r9, [rbp+3Fh+pv]
0x180037760  mov     [rbp+3Fh+pv], 0
0x180037768  mov     r8, r13
0x18003776b  mov     rdx, rsi
0x18003776e  mov     rax, [rcx]
0x180037771  mov     rax, [rax+28h]
0x180037775  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003777a  mov     rcx, [rbp+3Fh+pv]; unsigned __int16 *
0x18003777e  mov     edi, eax
0x180037780  test    eax, eax
0x180037782  jns     short loc_1800377A4
0x180037784  lea     rdx, IID_IUPnPRegistrar; struct _GUID *
0x18003778b  call    ?HrSetErrorInfo@@YAJPEBGAEBU_GUID@@@Z; HrSetErrorInfo(ushort const *,_GUID const &)
0x180037790  mov     rcx, r12; lpCriticalSection
0x180037793  call    cs:__imp_LeaveCriticalSection
0x18003779a  nop     dword ptr [rax+rax+00h]
0x18003779f  jmp     loc_180037A66
0x1800377a4  test    rcx, rcx
0x1800377a7  jz      short loc_1800377BD
0x1800377a9  call    cs:__imp_CoTaskMemFree
0x1800377b0  nop     dword ptr [rax+rax+00h]
0x1800377b5  mov     [rbp+3Fh+pv], 0
0x1800377bd  lea     rcx, [rbp+3Fh+arg_28]; int *
0x1800377c1  call    ?CheckRegistryForLifeTime@@YAHPEAJ@Z; CheckRegistryForLifeTime(long *)
0x1800377c6  mov     r15d, [rbp+3Fh+arg_28]
0x1800377ca  test    eax, eax
0x1800377cc  jz      short loc_1800377DD
0x1800377ce  test    r15d, r15d
0x1800377d1  jnz     loc_18003799C
0x1800377d7  mov     r15d, 708h
0x1800377dd  xor     esi, esi
0x1800377df  mov     rcx, [r14+68h]
0x1800377e3  lea     r9, [rbp+3Fh+var_58]
0x1800377e7  mov     rdx, [rbp+3Fh+var_80]
0x1800377eb  xorps   xmm0, xmm0
0x1800377ee  movups  xmmword ptr [rbp+3Fh+var_58.Data1], xmm0
0x1800377f2  mov     dword ptr [rsp+0D0h+var_A8], 0
0x1800377fa  mov     r8, r13
0x1800377fd  mov     rax, [rcx]
0x180037800  mov     [rsp+0D0h+var_B0], 0
0x180037808  mov     rax, [rax+18h]
0x18003780c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037811  mov     edi, eax
0x180037813  test    eax, eax
0x180037815  js      loc_1800379B0
0x18003781b  mov     rcx, [r14+68h]
0x18003781f  lea     r9, [rbp+3Fh+var_80]
0x180037823  mov     [rbp+3Fh+var_80], 0
0x18003782b  lea     r8, [rbp+3Fh+var_88]
0x18003782f  mov     [rbp+3Fh+var_88], 0
0x180037836  lea     rdx, [rbp+3Fh+var_58]
0x18003783a  mov     rax, [rcx]
0x18003783d  mov     rax, [rax+40h]
0x180037841  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037846  mov     edi, eax
0x180037848  test    eax, eax
0x18003784a  js      loc_18003797B
0x180037850  mov     rax, [rbp+3Fh+var_80]
0x180037854  test    rax, rax
0x180037857  jz      loc_18003797B
0x18003785d  mov     r13, [rbp+3Fh+var_78]
0x180037861  lea     rcx, [r14+8]; this
0x180037865  mov     r9, [rbp+3Fh+var_70]; unsigned __int16 *
0x180037869  lea     rdx, [rbp+3Fh+var_58]; struct _GUID *
0x18003786d  mov     [rsp+0D0h+var_A8], rax; unsigned __int16 **
0x180037872  mov     r8, r13; struct IUnknown *
0x180037875  mov     eax, [rbp+3Fh+var_88]
0x180037878  mov     [rsp+0D0h+var_B0], eax; int
0x18003787c  call    ?HrAddRunningDevice@CDeviceManager@@QEAAJAEBU_GUID@@PEAUIUnknown@@PEBGJPEAPEAG@Z; CDeviceManager::HrAddRunningDevice(_GUID const &,IUnknown *,ushort const *,long,ushort * *)
0x180037881  mov     edi, eax
0x180037883  mov     dword ptr [rbp+3Fh+var_78], eax
0x180037886  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AddUpnpTelemetry@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AddUpnpTelemetry@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AddUpnpTelemetry> `wil::Feature<__WilFeatureTraits_Feature_AddUpnpTelemetry>::GetImpl(void)'::`2'::impl
0x18003788d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AddUpnpTelemetry@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AddUpnpTelemetry>::__private_IsEnabled(void)
0x180037892  test    al, al
0x180037894  jz      short loc_1800378B9
0x180037896  lea     r9, [rbp+3Fh+var_78]
0x18003789a  mov     dword ptr [rbp+3Fh+var_70], 0
0x1800378a1  lea     r8, [rbp+3Fh+var_70]
0x1800378a5  mov     dword ptr [rbp+3Fh+pv], 1
0x1800378ac  lea     rdx, [rbp+3Fh+pv]
0x1800378b0  lea     rcx, [rbp+3Fh+var_68]
0x1800378b4  call    ??$RegisterDevice@AEAPEAGHHAEAJ@UpnpHostTelemetry@@SAXAEAPEAG$$QEAH1AEAJ@Z; UpnpHostTelemetry::RegisterDevice<ushort * &,int,int,long &>(ushort * &,int &&,int &&,long &)
0x1800378b9  test    edi, edi
0x1800378bb  js      loc_180037942
0x1800378c1  mov     r8, r13; struct IUnknown *
0x1800378c4  lea     rdx, [rbp+3Fh+var_58]; struct _GUID *
0x1800378c8  mov     rcx, r14; this
0x1800378cb  call    ?HrStoreDeviceControlHttpHeadersObject@CRegistrarSingleton@@AEAAJAEAU_GUID@@PEAUIUnknown@@@Z; CRegistrarSingleton::HrStoreDeviceControlHttpHeadersObject(_GUID &,IUnknown *)
0x1800378d0  mov     edi, eax
0x1800378d2  test    eax, eax
0x1800378d4  js      short loc_180037942
0x1800378d6  mov     r8, r13; struct IUnknown *
0x1800378d9  lea     rdx, [rbp+3Fh+var_58]; struct _GUID *
0x1800378dd  mov     rcx, r14; this
0x1800378e0  call    ?HrStoreDeviceControlSsdpHeadersObject@CRegistrarSingleton@@AEAAJAEAU_GUID@@PEAUIUnknown@@@Z; CRegistrarSingleton::HrStoreDeviceControlSsdpHeadersObject(_GUID &,IUnknown *)
0x1800378e5  mov     edi, eax
0x1800378e7  test    eax, eax
0x1800378e9  js      short loc_180037942
0x1800378eb  mov     rcx, [r14+68h]
0x1800378ef  lea     rdx, [rbp+3Fh+var_58]
0x1800378f3  mov     r8d, r15d
0x1800378f6  mov     rax, [rcx]
0x1800378f9  mov     rax, [rax+20h]
0x1800378fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037902  mov     edi, eax
0x180037904  test    eax, eax
0x180037906  js      short loc_180037942
0x180037908  lea     rdx, [rbp+3Fh+pv]; this
0x18003790c  mov     [rbp+3Fh+pv], 0
0x180037914  lea     rcx, [rbp+3Fh+var_58]; struct _GUID *
0x180037918  call    ?HrPhysicalDeviceIdentifierToString@@YAJAEBU_GUID@@AEAVCUString@@@Z; HrPhysicalDeviceIdentifierToString(_GUID const &,CUString &)
0x18003791d  mov     edi, eax
0x18003791f  test    eax, eax
0x180037921  js      short loc_180037932
0x180037923  mov     rdx, [rbp+3Fh+var_60]; unsigned __int16 **
0x180037927  lea     rcx, [rbp+3Fh+pv]; this
0x18003792b  call    ?HrGetBSTR@CUString@@QEBAJPEAPEAG@Z; CUString::HrGetBSTR(ushort * *)
0x180037930  mov     edi, eax
0x180037932  mov     rcx, [rbp+3Fh+pv]; Block
0x180037936  call    cs:__imp_free
0x18003793d  nop     dword ptr [rax+rax+00h]
0x180037942  xor     r15d, r15d
0x180037945  cmp     [rbp+3Fh+var_88], r15d
0x180037949  jle     short loc_18003796B
0x18003794b  mov     rcx, [rbp+3Fh+var_80]
0x18003794f  movsxd  rdx, r15d
0x180037952  mov     rcx, [rcx+rdx*8]; pv
0x180037956  call    cs:__imp_CoTaskMemFree
0x18003795d  nop     dword ptr [rax+rax+00h]
0x180037962  inc     r15d
0x180037965  cmp     r15d, [rbp+3Fh+var_88]
0x180037969  jl      short loc_18003794B
0x18003796b  mov     rcx, [rbp+3Fh+var_80]; pv
0x18003796f  call    cs:__imp_CoTaskMemFree
0x180037976  nop     dword ptr [rax+rax+00h]
0x18003797b  test    edi, edi
0x18003797d  jns     short loc_1800379B0
0x18003797f  mov     r15d, 1
0x180037985  lea     rdx, [rbp+3Fh+var_58]; struct _GUID *
0x180037989  mov     r8d, r15d; int
0x18003798c  mov     rcx, r14; this
0x18003798f  call    ?HrUnregisterDeviceByPDI@CRegistrarSingleton@@AEAAJAEAU_GUID@@H@Z; CRegistrarSingleton::HrUnregisterDeviceByPDI(_GUID &,int)
0x180037994  test    eax, eax
0x180037996  cmovns  esi, r15d
0x18003799a  jmp     short loc_1800379B6
0x18003799c  xor     esi, esi
0x18003799e  cmp     r15d, 384h
0x1800379a5  jge     loc_1800377DF
0x1800379ab  mov     edi, 80070057h
0x1800379b0  mov     r15d, 1
0x1800379b6  mov     rcx, r12; lpCriticalSection
0x1800379b9  call    cs:__imp_LeaveCriticalSection
0x1800379c0  nop     dword ptr [rax+rax+00h]
0x1800379c5  test    esi, esi
0x1800379c7  jz      short loc_180037A31
0x1800379c9  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1> `wil::Feature<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1>::GetImpl(void)'::`2'::impl
0x1800379d0  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1>::__private_IsEnabled(void)
0x1800379d5  mov     rcx, cs:?g_pVars@@3PEAVCGlobalVariables@@EA; CGlobalVariables * g_pVars
0x1800379dc  test    al, al
0x1800379de  jz      short loc_180037A29
0x1800379e0  test    rcx, rcx
0x1800379e3  jnz     short loc_180037A29
0x1800379e5  mov     edi, 80004005h
0x1800379ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800379f1  lea     rsi, WPP_GLOBAL_Control
0x1800379f8  cmp     rcx, rsi
0x1800379fb  jz      short loc_180037A66
0x1800379fd  test    [rcx+1Ch], r15b
0x180037a01  jz      short loc_180037A43
0x180037a03  mov     rcx, [rcx+10h]
0x180037a07  lea     r9, aCregistrarsing_0; "CRegistrarSingleton::RegisterRunningDev"...
0x180037a0e  mov     edx, 2Eh ; '.'
0x180037a13  mov     [rsp+0D0h+var_B0], edi
0x180037a17  lea     r8, WPP_0f8e6464007c3e0bdd6d585d5cfe4b6e_Traceguids
0x180037a1e  call    WPP_SF_sd
0x180037a23  jmp     short loc_180037A38
0x180037a25  xor     esi, esi
0x180037a27  jmp     short loc_1800379B6
0x180037a29  mov     rcx, [rcx]; this
0x180037a2c  call    ?DecrementURLCount@BaseHttpListener@@QEAAJXZ; BaseHttpListener::DecrementURLCount(void)
0x180037a31  lea     rsi, WPP_GLOBAL_Control
0x180037a38  test    edi, edi
0x180037a3a  jz      short loc_180037A66
0x180037a3c  mov     rcx, cs:WPP_GLOBAL_Control
0x180037a43  cmp     rcx, rsi
0x180037a46  jz      short loc_180037A66
0x180037a48  test    [rcx+1Ch], r15b
0x180037a4c  jz      short loc_180037A66
0x180037a4e  mov     rcx, [rcx+10h]
0x180037a52  lea     r8, WPP_0f8e6464007c3e0bdd6d585d5cfe4b6e_Traceguids
0x180037a59  mov     edx, 2Fh ; '/'
0x180037a5e  mov     r9d, edi
0x180037a61  call    WPP_SF_d
0x180037a66  mov     rcx, rbx; lpCriticalSection
0x180037a69  call    cs:__imp_LeaveCriticalSection
0x180037a70  nop     dword ptr [rax+rax+00h]
0x180037a75  mov     eax, edi
0x180037a77  mov     rcx, [rbp+3Fh+var_48]
0x180037a7b  xor     rcx, rsp; StackCookie
0x180037a7e  call    __security_check_cookie
0x180037a83  add     rsp, 98h
0x180037a8a  pop     r15
0x180037a8c  pop     r14
0x180037a8e  pop     r13
0x180037a90  pop     r12
0x180037a92  pop     rdi
0x180037a93  pop     rsi
0x180037a94  pop     rbx
0x180037a95  pop     rbp
0x180037a96  retn
```
