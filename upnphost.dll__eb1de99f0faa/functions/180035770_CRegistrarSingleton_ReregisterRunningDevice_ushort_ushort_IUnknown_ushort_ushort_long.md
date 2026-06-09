# CRegistrarSingleton::ReregisterRunningDevice(ushort *,ushort *,IUnknown *,ushort *,ushort *,long)

- ea: `0x180035770`
- end: `0x180035bd0`
- name: `?ReregisterRunningDevice@CRegistrarSingleton@@UEAAJPEAG0PEAUIUnknown@@00J@Z`
- size: `1120`
- prototype: `__int64 __usercall@<rax>(CRegistrarSingleton *__hidden this@<rcx>, unsigned __int16 *@<rdx>, unsigned __int16 *@<r8>, struct IUnknown *@<r9>, unsigned __int16 *, unsigned __int16 *, int)`
- caller_count: `0`
- callee_count: `21`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000db4c`
- `0x180013180`
- `0x18001c6bc`
- `0x18001e478`
- `0x18002bed0`
- `0x18002f1ac`
- `0x18002f384`
- `0x18002f684`
- `0x180030bdc`
- `0x1800310ac`
- `0x180031134`
- `0x180035770`
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

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003584a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003585a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003584a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003585a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800358d5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800358de`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180035afc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180035ba8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800358d5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800358de`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180035afc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180035ba8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800358f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035aa3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035ab6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800358f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035aa3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035ab6`

## pseudocode

```c
__int64 __fastcall CRegistrarSingleton::ReregisterRunningDevice(
        struct _RTL_CRITICAL_SECTION *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        struct IUnknown *a4,
        unsigned __int16 *a5,
        unsigned __int16 **pbstr,
        int a7)
{
  wchar_t *v10; // rcx
  __int64 result; // rax
  int v12; // r14d
  int IsAllowedCOMCallLocality; // esi
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rcx
  int v15; // eax
  unsigned int v16; // r14d
  int v17; // r13d
  HANDLE LockSemaphore; // rcx
  struct IUnknown *v19; // r12
  int i; // r14d
  STRSAFE_PCNZWCH v21; // rcx
  int v22; // [rsp+40h] [rbp-51h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-49h] BYREF
  unsigned __int16 **v24; // [rsp+50h] [rbp-41h] BYREF
  unsigned __int16 *v25; // [rsp+58h] [rbp-39h] BYREF
  unsigned __int16 *v26; // [rsp+60h] [rbp-31h] BYREF
  struct IUnknown *v27; // [rsp+68h] [rbp-29h]
  unsigned __int16 *v28; // [rsp+70h] [rbp-21h] BYREF
  struct _GUID v29; // [rsp+78h] [rbp-19h] BYREF

  v25 = a5;
  v24 = pbstr;
  v27 = a4;
  v26 = a3;
  v28 = a3;
  v10 = (wchar_t *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 0x40) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 68, WPP_0f8e6464007c3e0bdd6d585d5cfe4b6e_Traceguids);
    v10 = (wchar_t *)WPP_GLOBAL_Control;
  }
  if ( !CRegistrarSingleton::m_fRegObjDeleted )
  {
    if ( !LODWORD(this[3].SpinCount) )
    {
      result = CServiceModule::CompleteInitialization((struct IUnknown *)v10);
      if ( (int)result < 0 )
        return result;
    }
    EnterCriticalSection(this + 5);
    EnterCriticalSection(this + 4);
    if ( !LODWORD(this[3].SpinCount) )
    {
      v12 = -2147467259;
LABEL_17:
      LeaveCriticalSection(this + 4);
      LeaveCriticalSection(this + 5);
      return (unsigned int)v12;
    }
    IsAllowedCOMCallLocality = HrIsAllowedCOMCallLocality(3);
    if ( IsAllowedCOMCallLocality < 0
      || (IsAllowedCOMCallLocality = HrValidateResourcePath((BSTR)pbstr), IsAllowedCOMCallLocality < 0) )
    {
      v16 = a7;
    }
    else
    {
      DebugInfo = this[3].DebugInfo;
      pv = 0;
      v12 = (*(__int64 (__fastcall **)(PRTL_CRITICAL_SECTION_DEBUG, unsigned __int16 *, unsigned __int16 **, LPVOID *))(*(_QWORD *)&DebugInfo->Type + 40LL))(
              DebugInfo,
              a3,
              pbstr,
              &pv);
      IsAllowedCOMCallLocality = v12;
      if ( v12 < 0 )
      {
        HrSetErrorInfo((const unsigned __int16 *)pv, &IID_IUPnPReregistrar);
        goto LABEL_17;
      }
      if ( pv )
      {
        CoTaskMemFree(pv);
        pv = 0;
      }
      v15 = CheckRegistryForLifeTime((unsigned int *)&a7);
      v16 = a7;
      if ( v15 )
      {
        if ( a7 )
        {
          if ( a7 < 900 )
            IsAllowedCOMCallLocality = -2147024809;
        }
        else
        {
          v16 = 1800;
        }
      }
      if ( !a2 )
        IsAllowedCOMCallLocality = -2147467261;
    }
    v17 = 0;
    if ( IsAllowedCOMCallLocality >= 0 )
    {
      v29 = 0;
      IsAllowedCOMCallLocality = HrStringToPhysicalDeviceIdentifier(a2, &v29);
      if ( IsAllowedCOMCallLocality < 0 )
      {
        if ( IsAllowedCOMCallLocality == -2147221005 )
          IsAllowedCOMCallLocality = -2147024809;
      }
      else if ( (unsigned int)CDeviceManager::FHasDevice((CDeviceManager *)&this->LockCount, &v29) )
      {
        IsAllowedCOMCallLocality = -2147180495;
      }
      else
      {
        IsAllowedCOMCallLocality = (*(__int64 (__fastcall **)(HANDLE, unsigned __int16 *, unsigned __int16 **, struct _GUID *, _DWORD, int))(*(_QWORD *)this[2].LockSemaphore + 24LL))(
                                     this[2].LockSemaphore,
                                     v26,
                                     v24,
                                     &v29,
                                     0,
                                     1);
        if ( IsAllowedCOMCallLocality >= 0 )
        {
          LockSemaphore = this[2].LockSemaphore;
          v24 = 0;
          v22 = 0;
          IsAllowedCOMCallLocality = (*(__int64 (__fastcall **)(HANDLE, struct _GUID *, int *, unsigned __int16 ***))(*(_QWORD *)LockSemaphore + 64LL))(
                                       LockSemaphore,
                                       &v29,
                                       &v22,
                                       &v24);
          if ( IsAllowedCOMCallLocality >= 0 && v24 )
          {
            IsAllowedCOMCallLocality = CDeviceManager::HrAddRunningDevice(
                                         (CDeviceManager *)&this->LockCount,
                                         &v29,
                                         v27,
                                         v25,
                                         v22,
                                         v24);
            LODWORD(v25) = IsAllowedCOMCallLocality;
            if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AddUpnpTelemetry>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AddUpnpTelemetry>::GetImpl'::`2'::impl) )
            {
              LODWORD(v26) = 1;
              LODWORD(pv) = 1;
              UpnpHostTelemetry::RegisterDevice<unsigned short * &,int,int,long &>(&v28, &pv, &v26, &v25);
            }
            if ( IsAllowedCOMCallLocality >= 0 )
            {
              v19 = v27;
              IsAllowedCOMCallLocality = CRegistrarSingleton::HrStoreDeviceControlHttpHeadersObject(
                                           (CRegistrarSingleton *)this,
                                           &v29,
                                           v27);
              if ( IsAllowedCOMCallLocality >= 0 )
              {
                IsAllowedCOMCallLocality = CRegistrarSingleton::HrStoreDeviceControlSsdpHeadersObject(
                                             (CRegistrarSingleton *)this,
                                             &v29,
                                             v19);
                if ( IsAllowedCOMCallLocality >= 0 )
                  IsAllowedCOMCallLocality = (*(__int64 (__fastcall **)(HANDLE, struct _GUID *, _QWORD))(*(_QWORD *)this[2].LockSemaphore + 32LL))(
                                               this[2].LockSemaphore,
                                               &v29,
                                               v16);
              }
            }
            for ( i = 0; i < v22; ++i )
              CoTaskMemFree(v24[i]);
            CoTaskMemFree(v24);
          }
          if ( (int)(IsAllowedCOMCallLocality + 0x80000000) >= 0
            && IsAllowedCOMCallLocality != -2147180495
            && CRegistrarSingleton::HrUnregisterDeviceByPDI((CRegistrarSingleton *)this, &v29, 0) >= 0 )
          {
            v17 = 1;
          }
        }
      }
    }
    LeaveCriticalSection(this + 4);
    if ( v17 )
    {
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1>::GetImpl'::`2'::impl)
        || g_pVars )
      {
        BaseHttpListener::DecrementURLCount(*(BaseHttpListener **)g_pVars);
      }
      else
      {
        IsAllowedCOMCallLocality = -2147467259;
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control )
          goto LABEL_63;
        if ( (WPP_GLOBAL_Control[14] & 1) == 0 )
        {
LABEL_60:
          if ( v21 != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (v21[14] & 1) != 0 )
            WPP_SF_d(
              *((_QWORD *)v21 + 2),
              71,
              WPP_0f8e6464007c3e0bdd6d585d5cfe4b6e_Traceguids,
              (unsigned int)IsAllowedCOMCallLocality);
          goto LABEL_63;
        }
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          70,
          (unsigned int)WPP_0f8e6464007c3e0bdd6d585d5cfe4b6e_Traceguids,
          (unsigned int)"CRegistrarSingleton::ReregisterRunningDevice: g_pVars is null.",
          5);
      }
    }
    if ( IsAllowedCOMCallLocality )
    {
      v21 = WPP_GLOBAL_Control;
      goto LABEL_60;
    }
LABEL_63:
    LeaveCriticalSection(this + 5);
    return (unsigned int)IsAllowedCOMCallLocality;
  }
  if ( v10 != (wchar_t *)&WPP_GLOBAL_Control && (v10[14] & 0x40) != 0 )
    WPP_SF_(*((_QWORD *)v10 + 2), 69, WPP_0f8e6464007c3e0bdd6d585d5cfe4b6e_Traceguids);
  return 2147500037LL;
}

```

## disassembly

```asm
0x180035770  push    rbp
0x180035772  push    rbx
0x180035773  push    rsi
0x180035774  push    rdi
0x180035775  push    r12
0x180035777  push    r13
0x180035779  push    r14
0x18003577b  push    r15
0x18003577d  lea     rbp, [rsp-7]
0x180035782  sub     rsp, 98h
0x180035789  mov     rax, cs:__security_cookie
0x180035790  xor     rax, rsp
0x180035793  mov     [rbp+3Fh+var_48], rax
0x180035797  mov     rax, [rbp+3Fh+arg_20]
0x18003579b  mov     r13, r8
0x18003579e  mov     r14, [rbp+3Fh+pbstr]
0x1800357a2  mov     r12, rdx
0x1800357a5  mov     [rbp+3Fh+var_78], rax
0x1800357a9  mov     r15, rcx
0x1800357ac  mov     [rbp+3Fh+var_80], r14
0x1800357b0  mov     [rbp+3Fh+var_68], r9
0x1800357b4  mov     [rbp+3Fh+var_70], r8
0x1800357b8  mov     [rbp+3Fh+var_60], r8
0x1800357bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800357c3  lea     rax, WPP_GLOBAL_Control
0x1800357ca  cmp     rcx, rax
0x1800357cd  jz      short loc_1800357F8
0x1800357cf  test    byte ptr [rcx+1Ch], 40h
0x1800357d3  jz      short loc_1800357F8
0x1800357d5  mov     rcx, [rcx+10h]
0x1800357d9  lea     r8, WPP_0f8e6464007c3e0bdd6d585d5cfe4b6e_Traceguids
0x1800357e0  mov     edx, 44h ; 'D'
0x1800357e5  call    WPP_SF_
0x1800357ea  mov     rcx, cs:WPP_GLOBAL_Control; this
0x1800357f1  lea     rax, WPP_GLOBAL_Control
0x1800357f8  xor     esi, esi
0x1800357fa  cmp     cs:?m_fRegObjDeleted@CRegistrarSingleton@@1HA, esi; int CRegistrarSingleton::m_fRegObjDeleted
0x180035800  jz      short loc_18003582A
0x180035802  cmp     rcx, rax
0x180035805  jz      short loc_180035820
0x180035807  test    byte ptr [rcx+1Ch], 40h
0x18003580b  jz      short loc_180035820
0x18003580d  mov     rcx, [rcx+10h]
0x180035811  lea     edx, [rsi+45h]
0x180035814  lea     r8, WPP_0f8e6464007c3e0bdd6d585d5cfe4b6e_Traceguids
0x18003581b  call    WPP_SF_
0x180035820  mov     eax, 80004005h
0x180035825  jmp     loc_180035BB0
0x18003582a  cmp     [r15+98h], esi
0x180035831  jnz     short loc_180035840
0x180035833  call    ?CompleteInitialization@CServiceModule@@QEAAJXZ; CServiceModule::CompleteInitialization(void)
0x180035838  test    eax, eax
0x18003583a  js      loc_180035BB0
0x180035840  lea     rdi, [r15+0C8h]
0x180035847  mov     rcx, rdi; lpCriticalSection
0x18003584a  call    cs:__imp_EnterCriticalSection
0x180035850  lea     rbx, [r15+0A0h]
0x180035857  mov     rcx, rbx; lpCriticalSection
0x18003585a  call    cs:__imp_EnterCriticalSection
0x180035860  cmp     [r15+98h], esi
0x180035867  jnz     short loc_180035871
0x180035869  mov     r14d, 80004005h
0x18003586f  jmp     short loc_1800358D2
0x180035871  mov     ecx, 3
0x180035876  call    ?HrIsAllowedCOMCallLocality@@YAJW4CALL_LOCALITY@@@Z; HrIsAllowedCOMCallLocality(CALL_LOCALITY)
0x18003587b  mov     esi, eax
0x18003587d  test    eax, eax
0x18003587f  js      loc_180035939
0x180035885  mov     rcx, r14; pbstr
0x180035888  call    ?HrValidateResourcePath@@YAJPEAG@Z; HrValidateResourcePath(ushort *)
0x18003588d  mov     esi, eax
0x18003588f  test    eax, eax
0x180035891  js      loc_180035939
0x180035897  mov     rcx, [r15+78h]
0x18003589b  lea     r9, [rbp+3Fh+pv]
0x18003589f  mov     [rbp+3Fh+pv], 0
0x1800358a7  mov     r8, r14
0x1800358aa  mov     rdx, r13
0x1800358ad  mov     rax, [rcx]
0x1800358b0  mov     rax, [rax+28h]
0x1800358b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800358b9  mov     rcx, [rbp+3Fh+pv]; unsigned __int16 *
0x1800358bd  mov     r14d, eax
0x1800358c0  mov     esi, eax
0x1800358c2  test    eax, eax
0x1800358c4  jns     short loc_1800358EC
0x1800358c6  lea     rdx, IID_IUPnPReregistrar; struct _GUID *
0x1800358cd  call    ?HrSetErrorInfo@@YAJPEBGAEBU_GUID@@@Z; HrSetErrorInfo(ushort const *,_GUID const &)
0x1800358d2  mov     rcx, rbx; lpCriticalSection
0x1800358d5  call    cs:__imp_LeaveCriticalSection
0x1800358db  mov     rcx, rdi; lpCriticalSection
0x1800358de  call    cs:__imp_LeaveCriticalSection
0x1800358e4  mov     eax, r14d
0x1800358e7  jmp     loc_180035BB0
0x1800358ec  test    rcx, rcx
0x1800358ef  jz      short loc_1800358FF
0x1800358f1  call    cs:__imp_CoTaskMemFree
0x1800358f7  mov     [rbp+3Fh+pv], 0
0x1800358ff  lea     rcx, [rbp+3Fh+arg_30]; int *
0x180035903  call    ?CheckRegistryForLifeTime@@YAHPEAJ@Z; CheckRegistryForLifeTime(long *)
0x180035908  mov     r14d, [rbp+3Fh+arg_30]
0x18003590c  test    eax, eax
0x18003590e  jz      short loc_18003592C
0x180035910  test    r14d, r14d
0x180035913  jnz     short loc_18003591D
0x180035915  mov     r14d, 708h
0x18003591b  jmp     short loc_18003592C
0x18003591d  cmp     r14d, 384h
0x180035924  mov     eax, 80070057h
0x180035929  cmovl   esi, eax
0x18003592c  test    r12, r12
0x18003592f  mov     eax, 80004003h
0x180035934  cmovz   esi, eax
0x180035937  jmp     short loc_18003593D
0x180035939  mov     r14d, [rbp+3Fh+arg_30]
0x18003593d  xor     r13d, r13d
0x180035940  test    esi, esi
0x180035942  js      loc_180035AF9
0x180035948  xorps   xmm0, xmm0
0x18003594b  lea     rdx, [rbp+3Fh+var_58]; struct _GUID *
0x18003594f  mov     rcx, r12; unsigned __int16 *
0x180035952  movups  xmmword ptr [rbp+3Fh+var_58.Data1], xmm0
0x180035956  call    ?HrStringToPhysicalDeviceIdentifier@@YAJPEBGAEAU_GUID@@@Z; HrStringToPhysicalDeviceIdentifier(ushort const *,_GUID &)
0x18003595b  mov     esi, eax
0x18003595d  test    eax, eax
0x18003595f  js      loc_180035AEB
0x180035965  lea     rdx, [rbp+3Fh+var_58]; struct _GUID *
0x180035969  lea     rcx, [r15+8]; this
0x18003596d  call    ?FHasDevice@CDeviceManager@@QEAAHAEBU_GUID@@@Z; CDeviceManager::FHasDevice(_GUID const &)
0x180035972  test    eax, eax
0x180035974  jz      short loc_180035980
0x180035976  mov     esi, 8004A031h
0x18003597b  jmp     loc_180035AF9
0x180035980  mov     rcx, [r15+68h]
0x180035984  lea     r9, [rbp+3Fh+var_58]
0x180035988  mov     r8, [rbp+3Fh+var_80]
0x18003598c  mov     rdx, [rbp+3Fh+var_70]
0x180035990  mov     dword ptr [rsp+0D0h+var_A8], 1
0x180035998  mov     rax, [rcx]
0x18003599b  mov     [rsp+0D0h+var_B0], r13d
0x1800359a0  mov     rax, [rax+18h]
0x1800359a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800359a9  mov     esi, eax
0x1800359ab  test    eax, eax
0x1800359ad  js      loc_180035AF9
0x1800359b3  mov     rcx, [r15+68h]
0x1800359b7  lea     r9, [rbp+3Fh+var_80]
0x1800359bb  mov     [rbp+3Fh+var_80], r13
0x1800359bf  lea     r8, [rbp+3Fh+var_90]
0x1800359c3  mov     [rbp+3Fh+var_90], r13d
0x1800359c7  lea     rdx, [rbp+3Fh+var_58]
0x1800359cb  mov     rax, [rcx]
0x1800359ce  mov     rax, [rax+40h]
0x1800359d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800359d7  mov     esi, eax
0x1800359d9  test    eax, eax
0x1800359db  js      loc_180035ABC
0x1800359e1  mov     rax, [rbp+3Fh+var_80]
0x1800359e5  test    rax, rax
0x1800359e8  jz      loc_180035ABC
0x1800359ee  mov     r9, [rbp+3Fh+var_78]; unsigned __int16 *
0x1800359f2  lea     rdx, [rbp+3Fh+var_58]; struct _GUID *
0x1800359f6  mov     r8, [rbp+3Fh+var_68]; struct IUnknown *
0x1800359fa  lea     rcx, [r15+8]; this
0x1800359fe  mov     [rsp+0D0h+var_A8], rax; unsigned __int16 **
0x180035a03  mov     eax, [rbp+3Fh+var_90]
0x180035a06  mov     [rsp+0D0h+var_B0], eax; int
0x180035a0a  call    ?HrAddRunningDevice@CDeviceManager@@QEAAJAEBU_GUID@@PEAUIUnknown@@PEBGJPEAPEAG@Z; CDeviceManager::HrAddRunningDevice(_GUID const &,IUnknown *,ushort const *,long,ushort * *)
0x180035a0f  mov     esi, eax
0x180035a11  mov     dword ptr [rbp+3Fh+var_78], eax
0x180035a14  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AddUpnpTelemetry@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AddUpnpTelemetry@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AddUpnpTelemetry> `wil::Feature<__WilFeatureTraits_Feature_AddUpnpTelemetry>::GetImpl(void)'::`2'::impl
0x180035a1b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AddUpnpTelemetry@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AddUpnpTelemetry>::__private_IsEnabled(void)
0x180035a20  test    al, al
0x180035a22  jz      short loc_180035A44
0x180035a24  mov     eax, 1
0x180035a29  lea     r9, [rbp+3Fh+var_78]
0x180035a2d  lea     r8, [rbp+3Fh+var_70]
0x180035a31  mov     dword ptr [rbp+3Fh+var_70], eax
0x180035a34  lea     rdx, [rbp+3Fh+pv]
0x180035a38  mov     dword ptr [rbp+3Fh+pv], eax
0x180035a3b  lea     rcx, [rbp+3Fh+var_60]
0x180035a3f  call    ??$RegisterDevice@AEAPEAGHHAEAJ@UpnpHostTelemetry@@SAXAEAPEAG$$QEAH1AEAJ@Z; UpnpHostTelemetry::RegisterDevice<ushort * &,int,int,long &>(ushort * &,int &&,int &&,long &)
0x180035a44  test    esi, esi
0x180035a46  js      short loc_180035A8F
0x180035a48  mov     r12, [rbp+3Fh+var_68]
0x180035a4c  lea     rdx, [rbp+3Fh+var_58]; struct _GUID *
0x180035a50  mov     r8, r12; struct IUnknown *
0x180035a53  mov     rcx, r15; this
0x180035a56  call    ?HrStoreDeviceControlHttpHeadersObject@CRegistrarSingleton@@AEAAJAEAU_GUID@@PEAUIUnknown@@@Z; CRegistrarSingleton::HrStoreDeviceControlHttpHeadersObject(_GUID &,IUnknown *)
0x180035a5b  mov     esi, eax
0x180035a5d  test    eax, eax
0x180035a5f  js      short loc_180035A8F
0x180035a61  mov     r8, r12; struct IUnknown *
0x180035a64  lea     rdx, [rbp+3Fh+var_58]; struct _GUID *
0x180035a68  mov     rcx, r15; this
0x180035a6b  call    ?HrStoreDeviceControlSsdpHeadersObject@CRegistrarSingleton@@AEAAJAEAU_GUID@@PEAUIUnknown@@@Z; CRegistrarSingleton::HrStoreDeviceControlSsdpHeadersObject(_GUID &,IUnknown *)
0x180035a70  mov     esi, eax
0x180035a72  test    eax, eax
0x180035a74  js      short loc_180035A8F
0x180035a76  mov     rcx, [r15+68h]
0x180035a7a  lea     rdx, [rbp+3Fh+var_58]
0x180035a7e  mov     r8d, r14d
0x180035a81  mov     rax, [rcx]
0x180035a84  mov     rax, [rax+20h]
0x180035a88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035a8d  mov     esi, eax
0x180035a8f  xor     r14d, r14d
0x180035a92  cmp     [rbp+3Fh+var_90], r13d
0x180035a96  jle     short loc_180035AB2
0x180035a98  mov     rcx, [rbp+3Fh+var_80]
0x180035a9c  movsxd  rdx, r14d
0x180035a9f  mov     rcx, [rcx+rdx*8]; pv
0x180035aa3  call    cs:__imp_CoTaskMemFree
0x180035aa9  inc     r14d
0x180035aac  cmp     r14d, [rbp+3Fh+var_90]
0x180035ab0  jl      short loc_180035A98
0x180035ab2  mov     rcx, [rbp+3Fh+var_80]; pv
0x180035ab6  call    cs:__imp_CoTaskMemFree
0x180035abc  mov     ecx, 80000000h
0x180035ac1  lea     eax, [rsi+rcx]
0x180035ac4  test    ecx, eax
0x180035ac6  jnz     short loc_180035AF9
0x180035ac8  cmp     esi, 8004A031h
0x180035ace  jz      short loc_180035AF9
0x180035ad0  xor     r8d, r8d; int
0x180035ad3  lea     rdx, [rbp+3Fh+var_58]; struct _GUID *
0x180035ad7  mov     rcx, r15; this
0x180035ada  call    ?HrUnregisterDeviceByPDI@CRegistrarSingleton@@AEAAJAEAU_GUID@@H@Z; CRegistrarSingleton::HrUnregisterDeviceByPDI(_GUID &,int)
0x180035adf  test    eax, eax
0x180035ae1  js      short loc_180035AF9
0x180035ae3  mov     r13d, 1
0x180035ae9  jmp     short loc_180035AF9
0x180035aeb  cmp     esi, 800401F3h
0x180035af1  mov     eax, 80070057h
0x180035af6  cmovz   esi, eax
0x180035af9  mov     rcx, rbx; lpCriticalSection
0x180035afc  call    cs:__imp_LeaveCriticalSection
0x180035b02  test    r13d, r13d
0x180035b05  jz      short loc_180035B70
0x180035b07  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1> `wil::Feature<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1>::GetImpl(void)'::`2'::impl
0x180035b0e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1>::__private_IsEnabled(void)
0x180035b13  mov     rcx, cs:?g_pVars@@3PEAVCGlobalVariables@@EA; CGlobalVariables * g_pVars
0x180035b1a  test    al, al
0x180035b1c  jz      short loc_180035B68
0x180035b1e  test    rcx, rcx
0x180035b21  jnz     short loc_180035B68
0x180035b23  mov     r14d, 80004005h
0x180035b29  mov     esi, r14d
0x180035b2c  mov     rcx, cs:WPP_GLOBAL_Control
0x180035b33  lea     rbx, WPP_GLOBAL_Control
0x180035b3a  cmp     rcx, rbx
0x180035b3d  jz      short loc_180035BA5
0x180035b3f  test    byte ptr [rcx+1Ch], 1
0x180035b43  jz      short loc_180035B82
0x180035b45  mov     rcx, [rcx+10h]
0x180035b49  lea     r9, aCregistrarsing_1; "CRegistrarSingleton::ReregisterRunningD"...
0x180035b50  mov     edx, 46h ; 'F'
0x180035b55  mov     [rsp+0D0h+var_B0], r14d
0x180035b5a  lea     r8, WPP_0f8e6464007c3e0bdd6d585d5cfe4b6e_Traceguids
0x180035b61  call    WPP_SF_sd
0x180035b66  jmp     short loc_180035B77
0x180035b68  mov     rcx, [rcx]; this
0x180035b6b  call    ?DecrementURLCount@BaseHttpListener@@QEAAJXZ; BaseHttpListener::DecrementURLCount(void)
0x180035b70  lea     rbx, WPP_GLOBAL_Control
0x180035b77  test    esi, esi
0x180035b79  jz      short loc_180035BA5
0x180035b7b  mov     rcx, cs:WPP_GLOBAL_Control
0x180035b82  cmp     rcx, rbx
0x180035b85  jz      short loc_180035BA5
0x180035b87  test    byte ptr [rcx+1Ch], 1
0x180035b8b  jz      short loc_180035BA5
0x180035b8d  mov     rcx, [rcx+10h]
0x180035b91  lea     r8, WPP_0f8e6464007c3e0bdd6d585d5cfe4b6e_Traceguids
0x180035b98  mov     edx, 47h ; 'G'
0x180035b9d  mov     r9d, esi
0x180035ba0  call    WPP_SF_d
0x180035ba5  mov     rcx, rdi; lpCriticalSection
0x180035ba8  call    cs:__imp_LeaveCriticalSection
0x180035bae  mov     eax, esi
0x180035bb0  mov     rcx, [rbp+3Fh+var_48]
0x180035bb4  xor     rcx, rsp; StackCookie
0x180035bb7  call    __security_check_cookie
0x180035bbc  add     rsp, 98h
0x180035bc3  pop     r15
0x180035bc5  pop     r14
0x180035bc7  pop     r13
0x180035bc9  pop     r12
0x180035bcb  pop     rdi
0x180035bcc  pop     rsi
0x180035bcd  pop     rbx
0x180035bce  pop     rbp
0x180035bcf  retn
```
