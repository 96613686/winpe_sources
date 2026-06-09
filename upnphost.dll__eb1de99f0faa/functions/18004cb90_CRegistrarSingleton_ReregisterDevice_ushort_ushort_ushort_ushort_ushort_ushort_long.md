# CRegistrarSingleton::ReregisterDevice(ushort *,ushort *,ushort *,ushort *,ushort *,ushort *,long)

- ea: `0x18004cb90`
- end: `0x18004d024`
- name: `?ReregisterDevice@CRegistrarSingleton@@UEAAJPEAG00000J@Z`
- size: `1172`
- prototype: `__int64 __usercall@<rax>(CRegistrarSingleton *__hidden this@<rcx>, unsigned __int16 *@<rdx>, unsigned __int16 *@<r8>, unsigned __int16 *@<r9>, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, int)`
- caller_count: `0`
- callee_count: `20`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000db4c`
- `0x180013180`
- `0x18001c6bc`
- `0x18001e478`
- `0x18002f1ac`
- `0x18002f384`
- `0x18002f684`
- `0x180030bdc`
- `0x180038be4`
- `0x180038ce4`
- `0x1800394b4`
- `0x180039a84`
- `0x18003a560`
- `0x180046de8`
- `0x18004ae14`
- `0x18004b99c`
- `0x18004c024`
- `0x18004cb90`
- `0x18004d770`
- `0x180055010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004cc72`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004cc82`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004cc72`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004cc82`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004ccfd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004cd06`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004cf50`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004cffc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004ccfd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004cd06`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004cf50`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004cffc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004cd19`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004cef7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004cf0a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004cd19`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004cef7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004cf0a`

## pseudocode

```c
__int64 __fastcall CRegistrarSingleton::ReregisterDevice(
        struct _RTL_CRITICAL_SECTION *this,
        unsigned __int16 *a2,
        unsigned __int16 **a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        unsigned __int16 *a6,
        unsigned __int16 *pbstr,
        int a8)
{
  wchar_t *v11; // rcx
  __int64 result; // rax
  int v13; // r14d
  int IsAllowedCOMCallLocality; // esi
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rcx
  int v16; // eax
  unsigned int v17; // r14d
  int v18; // r13d
  HANDLE LockSemaphore; // rcx
  int i; // r14d
  STRSAFE_PCNZWCH v21; // rcx
  int v22; // [rsp+40h] [rbp-61h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-59h] BYREF
  unsigned __int16 **v24; // [rsp+50h] [rbp-51h] BYREF
  int v25; // [rsp+58h] [rbp-49h] BYREF
  int v26; // [rsp+5Ch] [rbp-45h] BYREF
  unsigned __int16 *v27; // [rsp+60h] [rbp-41h]
  unsigned __int16 *v28; // [rsp+68h] [rbp-39h]
  unsigned __int16 *v29; // [rsp+70h] [rbp-31h]
  unsigned __int16 *v30; // [rsp+78h] [rbp-29h]
  unsigned __int16 **v31; // [rsp+80h] [rbp-21h] BYREF
  struct _GUID v32; // [rsp+88h] [rbp-19h] BYREF

  v29 = a5;
  v28 = a6;
  v30 = a4;
  v24 = a3;
  v31 = a3;
  v27 = pbstr;
  v11 = (wchar_t *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 0x40) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 64, WPP_0f8e6464007c3e0bdd6d585d5cfe4b6e_Traceguids);
    v11 = (wchar_t *)WPP_GLOBAL_Control;
  }
  if ( !CRegistrarSingleton::m_fRegObjDeleted )
  {
    if ( !LODWORD(this[3].SpinCount) )
    {
      result = CServiceModule::CompleteInitialization((struct IUnknown *)v11);
      if ( (int)result < 0 )
        return result;
    }
    EnterCriticalSection(this + 5);
    EnterCriticalSection(this + 4);
    if ( !LODWORD(this[3].SpinCount) )
    {
      v13 = -2147467259;
LABEL_17:
      LeaveCriticalSection(this + 4);
      LeaveCriticalSection(this + 5);
      return (unsigned int)v13;
    }
    IsAllowedCOMCallLocality = HrIsAllowedCOMCallLocality(3);
    if ( IsAllowedCOMCallLocality < 0
      || (IsAllowedCOMCallLocality = HrValidateResourcePath(pbstr), IsAllowedCOMCallLocality < 0) )
    {
      v17 = a8;
    }
    else
    {
      DebugInfo = this[3].DebugInfo;
      pv = 0;
      v13 = (*(__int64 (__fastcall **)(PRTL_CRITICAL_SECTION_DEBUG, unsigned __int16 **, unsigned __int16 *, LPVOID *))(*(_QWORD *)&DebugInfo->Type + 40LL))(
              DebugInfo,
              a3,
              pbstr,
              &pv);
      IsAllowedCOMCallLocality = v13;
      if ( v13 < 0 )
      {
        HrSetErrorInfo((const unsigned __int16 *)pv, &IID_IUPnPReregistrar);
        goto LABEL_17;
      }
      if ( pv )
      {
        CoTaskMemFree(pv);
        pv = 0;
      }
      v16 = CheckRegistryForLifeTime((unsigned int *)&a8);
      v17 = a8;
      if ( v16 )
      {
        if ( a8 )
        {
          if ( a8 < 900 )
            IsAllowedCOMCallLocality = -2147024809;
        }
        else
        {
          v17 = 1800;
        }
      }
      if ( !a2 )
        IsAllowedCOMCallLocality = -2147467261;
    }
    v18 = 0;
    if ( IsAllowedCOMCallLocality >= 0 )
    {
      IsAllowedCOMCallLocality = HrSetAutoStart();
      if ( IsAllowedCOMCallLocality >= 0 )
      {
        v32 = 0;
        IsAllowedCOMCallLocality = HrStringToPhysicalDeviceIdentifier(a2, &v32);
        if ( IsAllowedCOMCallLocality < 0 )
        {
          if ( IsAllowedCOMCallLocality == -2147221005 )
            IsAllowedCOMCallLocality = -2147024809;
        }
        else if ( (unsigned int)CDeviceManager::FHasDevice((CDeviceManager *)&this->LockCount, &v32) )
        {
          IsAllowedCOMCallLocality = -2147180495;
        }
        else
        {
          IsAllowedCOMCallLocality = (*(__int64 (__fastcall **)(HANDLE, unsigned __int16 **, unsigned __int16 *, struct _GUID *, int, int))(*(_QWORD *)this[2].LockSemaphore + 24LL))(
                                       this[2].LockSemaphore,
                                       v24,
                                       v27,
                                       &v32,
                                       1,
                                       1);
          if ( IsAllowedCOMCallLocality >= 0 )
          {
            LockSemaphore = this[2].LockSemaphore;
            v24 = 0;
            v22 = 0;
            IsAllowedCOMCallLocality = (*(__int64 (__fastcall **)(HANDLE, struct _GUID *, int *, unsigned __int16 ***))(*(_QWORD *)LockSemaphore + 64LL))(
                                         LockSemaphore,
                                         &v32,
                                         &v22,
                                         &v24);
            if ( IsAllowedCOMCallLocality >= 0 && v24 )
            {
              IsAllowedCOMCallLocality = CDeviceManager::HrAddDevice(
                                           (CDeviceManager *)&this->LockCount,
                                           &v32,
                                           v30,
                                           v29,
                                           v28,
                                           v22,
                                           v24);
              v25 = IsAllowedCOMCallLocality;
              if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AddUpnpTelemetry>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AddUpnpTelemetry>::GetImpl'::`2'::impl) )
              {
                v26 = 1;
                LODWORD(pv) = 0;
                UpnpHostTelemetry::RegisterDevice<unsigned short * &,int,int,long &>(&v31, &pv, &v26, &v25);
              }
              if ( IsAllowedCOMCallLocality >= 0 )
              {
                IsAllowedCOMCallLocality = (*(__int64 (__fastcall **)(ULONG_PTR, struct _GUID *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned int))(*(_QWORD *)this[2].SpinCount + 24LL))(
                                             this[2].SpinCount,
                                             &v32,
                                             v30,
                                             v29,
                                             v28,
                                             v27,
                                             v17);
                if ( IsAllowedCOMCallLocality >= 0 )
                  IsAllowedCOMCallLocality = (*(__int64 (__fastcall **)(HANDLE, struct _GUID *, _QWORD))(*(_QWORD *)this[2].LockSemaphore + 32LL))(
                                               this[2].LockSemaphore,
                                               &v32,
                                               v17);
              }
              for ( i = 0; i < v22; ++i )
                CoTaskMemFree(v24[i]);
              CoTaskMemFree(v24);
            }
            if ( (int)(IsAllowedCOMCallLocality + 0x80000000) >= 0
              && IsAllowedCOMCallLocality != -2147180495
              && CRegistrarSingleton::HrUnregisterDeviceByPDI((CRegistrarSingleton *)this, &v32, 0) >= 0 )
            {
              v18 = 1;
            }
          }
        }
      }
    }
    LeaveCriticalSection(this + 4);
    if ( v18 )
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
              67,
              WPP_0f8e6464007c3e0bdd6d585d5cfe4b6e_Traceguids,
              (unsigned int)IsAllowedCOMCallLocality);
          goto LABEL_63;
        }
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          66,
          (unsigned int)WPP_0f8e6464007c3e0bdd6d585d5cfe4b6e_Traceguids,
          (unsigned int)"CRegistrarSingleton::ReregisterDevice: g_pVars is null.",
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
  if ( v11 != (wchar_t *)&WPP_GLOBAL_Control && (v11[14] & 0x40) != 0 )
    WPP_SF_(*((_QWORD *)v11 + 2), 65, WPP_0f8e6464007c3e0bdd6d585d5cfe4b6e_Traceguids);
  return 2147500037LL;
}

```

## disassembly

```asm
0x18004cb90  push    rbp
0x18004cb92  push    rbx
0x18004cb93  push    rsi
0x18004cb94  push    rdi
0x18004cb95  push    r12
0x18004cb97  push    r13
0x18004cb99  push    r14
0x18004cb9b  push    r15
0x18004cb9d  lea     rbp, [rsp-7]
0x18004cba2  sub     rsp, 0A8h
0x18004cba9  mov     rax, cs:__security_cookie
0x18004cbb0  xor     rax, rsp
0x18004cbb3  mov     [rbp+3Fh+var_48], rax
0x18004cbb7  mov     rax, [rbp+3Fh+arg_20]
0x18004cbbb  mov     r14, r8
0x18004cbbe  mov     r13, [rbp+3Fh+pbstr]
0x18004cbc2  mov     r12, rdx
0x18004cbc5  mov     [rbp+3Fh+var_70], rax
0x18004cbc9  mov     r15, rcx
0x18004cbcc  mov     rax, [rbp+3Fh+arg_28]
0x18004cbd0  mov     [rbp+3Fh+var_78], rax
0x18004cbd4  mov     [rbp+3Fh+var_68], r9
0x18004cbd8  mov     [rbp+3Fh+var_90], r8
0x18004cbdc  mov     [rbp+3Fh+var_60], r8
0x18004cbe0  mov     [rbp+3Fh+var_80], r13
0x18004cbe4  mov     rcx, cs:WPP_GLOBAL_Control
0x18004cbeb  lea     rax, WPP_GLOBAL_Control
0x18004cbf2  cmp     rcx, rax
0x18004cbf5  jz      short loc_18004CC20
0x18004cbf7  test    byte ptr [rcx+1Ch], 40h
0x18004cbfb  jz      short loc_18004CC20
0x18004cbfd  mov     rcx, [rcx+10h]
0x18004cc01  lea     r8, WPP_0f8e6464007c3e0bdd6d585d5cfe4b6e_Traceguids
0x18004cc08  mov     edx, 40h ; '@'
0x18004cc0d  call    WPP_SF_
0x18004cc12  mov     rcx, cs:WPP_GLOBAL_Control; this
0x18004cc19  lea     rax, WPP_GLOBAL_Control
0x18004cc20  xor     esi, esi
0x18004cc22  cmp     cs:?m_fRegObjDeleted@CRegistrarSingleton@@1HA, esi; int CRegistrarSingleton::m_fRegObjDeleted
0x18004cc28  jz      short loc_18004CC52
0x18004cc2a  cmp     rcx, rax
0x18004cc2d  jz      short loc_18004CC48
0x18004cc2f  test    byte ptr [rcx+1Ch], 40h
0x18004cc33  jz      short loc_18004CC48
0x18004cc35  mov     rcx, [rcx+10h]
0x18004cc39  lea     edx, [rsi+41h]
0x18004cc3c  lea     r8, WPP_0f8e6464007c3e0bdd6d585d5cfe4b6e_Traceguids
0x18004cc43  call    WPP_SF_
0x18004cc48  mov     eax, 80004005h
0x18004cc4d  jmp     loc_18004D004
0x18004cc52  cmp     [r15+98h], esi
0x18004cc59  jnz     short loc_18004CC68
0x18004cc5b  call    ?CompleteInitialization@CServiceModule@@QEAAJXZ; CServiceModule::CompleteInitialization(void)
0x18004cc60  test    eax, eax
0x18004cc62  js      loc_18004D004
0x18004cc68  lea     rdi, [r15+0C8h]
0x18004cc6f  mov     rcx, rdi; lpCriticalSection
0x18004cc72  call    cs:__imp_EnterCriticalSection
0x18004cc78  lea     rbx, [r15+0A0h]
0x18004cc7f  mov     rcx, rbx; lpCriticalSection
0x18004cc82  call    cs:__imp_EnterCriticalSection
0x18004cc88  cmp     [r15+98h], esi
0x18004cc8f  jnz     short loc_18004CC99
0x18004cc91  mov     r14d, 80004005h
0x18004cc97  jmp     short loc_18004CCFA
0x18004cc99  mov     ecx, 3
0x18004cc9e  call    ?HrIsAllowedCOMCallLocality@@YAJW4CALL_LOCALITY@@@Z; HrIsAllowedCOMCallLocality(CALL_LOCALITY)
0x18004cca3  mov     esi, eax
0x18004cca5  test    eax, eax
0x18004cca7  js      loc_18004CD67
0x18004ccad  mov     rcx, r13; pbstr
0x18004ccb0  call    ?HrValidateResourcePath@@YAJPEAG@Z; HrValidateResourcePath(ushort *)
0x18004ccb5  mov     esi, eax
0x18004ccb7  test    eax, eax
0x18004ccb9  js      loc_18004CD67
0x18004ccbf  mov     rcx, [r15+78h]
0x18004ccc3  lea     r9, [rbp+3Fh+pv]
0x18004ccc7  mov     [rbp+3Fh+pv], 0
0x18004cccf  mov     r8, r13
0x18004ccd2  mov     rdx, r14
0x18004ccd5  mov     rax, [rcx]
0x18004ccd8  mov     rax, [rax+28h]
0x18004ccdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cce1  mov     rcx, [rbp+3Fh+pv]; unsigned __int16 *
0x18004cce5  mov     r14d, eax
0x18004cce8  mov     esi, eax
0x18004ccea  test    eax, eax
0x18004ccec  jns     short loc_18004CD14
0x18004ccee  lea     rdx, IID_IUPnPReregistrar; struct _GUID *
0x18004ccf5  call    ?HrSetErrorInfo@@YAJPEBGAEBU_GUID@@@Z; HrSetErrorInfo(ushort const *,_GUID const &)
0x18004ccfa  mov     rcx, rbx; lpCriticalSection
0x18004ccfd  call    cs:__imp_LeaveCriticalSection
0x18004cd03  mov     rcx, rdi; lpCriticalSection
0x18004cd06  call    cs:__imp_LeaveCriticalSection
0x18004cd0c  mov     eax, r14d
0x18004cd0f  jmp     loc_18004D004
0x18004cd14  test    rcx, rcx
0x18004cd17  jz      short loc_18004CD27
0x18004cd19  call    cs:__imp_CoTaskMemFree
0x18004cd1f  mov     [rbp+3Fh+pv], 0
0x18004cd27  lea     rcx, [rbp+3Fh+arg_38]; int *
0x18004cd2e  call    ?CheckRegistryForLifeTime@@YAHPEAJ@Z; CheckRegistryForLifeTime(long *)
0x18004cd33  mov     r14d, [rbp+3Fh+arg_38]
0x18004cd3a  test    eax, eax
0x18004cd3c  jz      short loc_18004CD5A
0x18004cd3e  test    r14d, r14d
0x18004cd41  jnz     short loc_18004CD4B
0x18004cd43  mov     r14d, 708h
0x18004cd49  jmp     short loc_18004CD5A
0x18004cd4b  cmp     r14d, 384h
0x18004cd52  mov     eax, 80070057h
0x18004cd57  cmovl   esi, eax
0x18004cd5a  test    r12, r12
0x18004cd5d  mov     eax, 80004003h
0x18004cd62  cmovz   esi, eax
0x18004cd65  jmp     short loc_18004CD6E
0x18004cd67  mov     r14d, [rbp+3Fh+arg_38]
0x18004cd6e  xor     r13d, r13d
0x18004cd71  test    esi, esi
0x18004cd73  js      loc_18004CF4D
0x18004cd79  call    ?HrSetAutoStart@@YAJXZ; HrSetAutoStart(void)
0x18004cd7e  mov     esi, eax
0x18004cd80  test    eax, eax
0x18004cd82  js      loc_18004CF4D
0x18004cd88  xorps   xmm0, xmm0
0x18004cd8b  lea     rdx, [rbp+3Fh+var_58]; struct _GUID *
0x18004cd8f  mov     rcx, r12; unsigned __int16 *
0x18004cd92  movups  xmmword ptr [rbp+3Fh+var_58.Data1], xmm0
0x18004cd96  call    ?HrStringToPhysicalDeviceIdentifier@@YAJPEBGAEAU_GUID@@@Z; HrStringToPhysicalDeviceIdentifier(ushort const *,_GUID &)
0x18004cd9b  mov     esi, eax
0x18004cd9d  test    eax, eax
0x18004cd9f  js      loc_18004CF3F
0x18004cda5  lea     rdx, [rbp+3Fh+var_58]; struct _GUID *
0x18004cda9  lea     rcx, [r15+8]; this
0x18004cdad  call    ?FHasDevice@CDeviceManager@@QEAAHAEBU_GUID@@@Z; CDeviceManager::FHasDevice(_GUID const &)
0x18004cdb2  test    eax, eax
0x18004cdb4  jz      short loc_18004CDC0
0x18004cdb6  mov     esi, 8004A031h
0x18004cdbb  jmp     loc_18004CF4D
0x18004cdc0  mov     rcx, [r15+68h]
0x18004cdc4  lea     r9, [rbp+3Fh+var_58]
0x18004cdc8  mov     r8, [rbp+3Fh+var_80]
0x18004cdcc  mov     edx, 1
0x18004cdd1  mov     [rsp+0E0h+var_B8], edx
0x18004cdd5  mov     dword ptr [rsp+0E0h+var_C0], edx
0x18004cdd9  mov     rax, [rcx]
0x18004cddc  mov     rdx, [rbp+3Fh+var_90]
0x18004cde0  mov     rax, [rax+18h]
0x18004cde4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cde9  mov     esi, eax
0x18004cdeb  test    eax, eax
0x18004cded  js      loc_18004CF4D
0x18004cdf3  mov     rcx, [r15+68h]
0x18004cdf7  lea     r9, [rbp+3Fh+var_90]
0x18004cdfb  mov     [rbp+3Fh+var_90], r13
0x18004cdff  lea     r8, [rbp+3Fh+var_A0]
0x18004ce03  mov     [rbp+3Fh+var_A0], r13d
0x18004ce07  lea     rdx, [rbp+3Fh+var_58]
0x18004ce0b  mov     rax, [rcx]
0x18004ce0e  mov     rax, [rax+40h]
0x18004ce12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ce17  mov     esi, eax
0x18004ce19  test    eax, eax
0x18004ce1b  js      loc_18004CF10
0x18004ce21  mov     rax, [rbp+3Fh+var_90]
0x18004ce25  test    rax, rax
0x18004ce28  jz      loc_18004CF10
0x18004ce2e  mov     r9, [rbp+3Fh+var_70]; unsigned __int16 *
0x18004ce32  lea     rdx, [rbp+3Fh+var_58]; struct _GUID *
0x18004ce36  mov     r8, [rbp+3Fh+var_68]; unsigned __int16 *
0x18004ce3a  lea     rcx, [r15+8]; this
0x18004ce3e  mov     [rsp+0E0h+var_B0], rax; unsigned __int16 **
0x18004ce43  mov     eax, [rbp+3Fh+var_A0]
0x18004ce46  mov     [rsp+0E0h+var_B8], eax; int
0x18004ce4a  mov     rax, [rbp+3Fh+var_78]
0x18004ce4e  mov     [rsp+0E0h+var_C0], rax; unsigned __int16 *
0x18004ce53  call    ?HrAddDevice@CDeviceManager@@QEAAJAEBU_GUID@@PEBG11JPEAPEAG@Z; CDeviceManager::HrAddDevice(_GUID const &,ushort const *,ushort const *,ushort const *,long,ushort * *)
0x18004ce58  mov     esi, eax
0x18004ce5a  mov     [rbp+3Fh+var_88], eax
0x18004ce5d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AddUpnpTelemetry@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AddUpnpTelemetry@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AddUpnpTelemetry> `wil::Feature<__WilFeatureTraits_Feature_AddUpnpTelemetry>::GetImpl(void)'::`2'::impl
0x18004ce64  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AddUpnpTelemetry@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AddUpnpTelemetry>::__private_IsEnabled(void)
0x18004ce69  test    al, al
0x18004ce6b  jz      short loc_18004CE8D
0x18004ce6d  lea     r9, [rbp+3Fh+var_88]
0x18004ce71  mov     [rbp+3Fh+var_84], 1
0x18004ce78  lea     r8, [rbp+3Fh+var_84]
0x18004ce7c  mov     dword ptr [rbp+3Fh+pv], r13d
0x18004ce80  lea     rdx, [rbp+3Fh+pv]
0x18004ce84  lea     rcx, [rbp+3Fh+var_60]
0x18004ce88  call    ??$RegisterDevice@AEAPEAGHHAEAJ@UpnpHostTelemetry@@SAXAEAPEAG$$QEAH1AEAJ@Z; UpnpHostTelemetry::RegisterDevice<ushort * &,int,int,long &>(ushort * &,int &&,int &&,long &)
0x18004ce8d  test    esi, esi
0x18004ce8f  js      short loc_18004CEE3
0x18004ce91  mov     rcx, [r15+70h]
0x18004ce95  mov     rdx, [rbp+3Fh+var_80]
0x18004ce99  mov     r9, [rbp+3Fh+var_70]
0x18004ce9d  mov     r8, [rbp+3Fh+var_68]
0x18004cea1  mov     rax, [rcx]
0x18004cea4  mov     dword ptr [rsp+0E0h+var_B0], r14d
0x18004cea9  mov     qword ptr [rsp+0E0h+var_B8], rdx
0x18004ceae  mov     rdx, [rbp+3Fh+var_78]
0x18004ceb2  mov     rax, [rax+18h]
0x18004ceb6  mov     [rsp+0E0h+var_C0], rdx
0x18004cebb  lea     rdx, [rbp+3Fh+var_58]
0x18004cebf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cec4  mov     esi, eax
0x18004cec6  test    eax, eax
0x18004cec8  js      short loc_18004CEE3
0x18004ceca  mov     rcx, [r15+68h]
0x18004cece  lea     rdx, [rbp+3Fh+var_58]
0x18004ced2  mov     r8d, r14d
0x18004ced5  mov     rax, [rcx]
0x18004ced8  mov     rax, [rax+20h]
0x18004cedc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cee1  mov     esi, eax
0x18004cee3  xor     r14d, r14d
0x18004cee6  cmp     [rbp+3Fh+var_A0], r13d
0x18004ceea  jle     short loc_18004CF06
0x18004ceec  mov     rcx, [rbp+3Fh+var_90]
0x18004cef0  movsxd  rdx, r14d
0x18004cef3  mov     rcx, [rcx+rdx*8]; pv
0x18004cef7  call    cs:__imp_CoTaskMemFree
0x18004cefd  inc     r14d
0x18004cf00  cmp     r14d, [rbp+3Fh+var_A0]
0x18004cf04  jl      short loc_18004CEEC
0x18004cf06  mov     rcx, [rbp+3Fh+var_90]; pv
0x18004cf0a  call    cs:__imp_CoTaskMemFree
0x18004cf10  mov     ecx, 80000000h
0x18004cf15  lea     eax, [rsi+rcx]
0x18004cf18  test    ecx, eax
0x18004cf1a  jnz     short loc_18004CF4D
0x18004cf1c  cmp     esi, 8004A031h
0x18004cf22  jz      short loc_18004CF4D
0x18004cf24  xor     r8d, r8d; int
0x18004cf27  lea     rdx, [rbp+3Fh+var_58]; struct _GUID *
0x18004cf2b  mov     rcx, r15; this
0x18004cf2e  call    ?HrUnregisterDeviceByPDI@CRegistrarSingleton@@AEAAJAEAU_GUID@@H@Z; CRegistrarSingleton::HrUnregisterDeviceByPDI(_GUID &,int)
0x18004cf33  test    eax, eax
0x18004cf35  js      short loc_18004CF4D
0x18004cf37  mov     r13d, 1
0x18004cf3d  jmp     short loc_18004CF4D
0x18004cf3f  cmp     esi, 800401F3h
0x18004cf45  mov     eax, 80070057h
0x18004cf4a  cmovz   esi, eax
0x18004cf4d  mov     rcx, rbx; lpCriticalSection
0x18004cf50  call    cs:__imp_LeaveCriticalSection
0x18004cf56  test    r13d, r13d
0x18004cf59  jz      short loc_18004CFC4
0x18004cf5b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1> `wil::Feature<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1>::GetImpl(void)'::`2'::impl
0x18004cf62  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1>::__private_IsEnabled(void)
0x18004cf67  mov     rcx, cs:?g_pVars@@3PEAVCGlobalVariables@@EA; CGlobalVariables * g_pVars
0x18004cf6e  test    al, al
0x18004cf70  jz      short loc_18004CFBC
0x18004cf72  test    rcx, rcx
0x18004cf75  jnz     short loc_18004CFBC
0x18004cf77  mov     r14d, 80004005h
0x18004cf7d  mov     esi, r14d
0x18004cf80  mov     rcx, cs:WPP_GLOBAL_Control
0x18004cf87  lea     rbx, WPP_GLOBAL_Control
0x18004cf8e  cmp     rcx, rbx
0x18004cf91  jz      short loc_18004CFF9
0x18004cf93  test    byte ptr [rcx+1Ch], 1
0x18004cf97  jz      short loc_18004CFD6
0x18004cf99  mov     rcx, [rcx+10h]
0x18004cf9d  lea     r9, aCregistrarsing; "CRegistrarSingleton::ReregisterDevice: "...
0x18004cfa4  mov     edx, 42h ; 'B'
0x18004cfa9  mov     dword ptr [rsp+0E0h+var_C0], r14d
0x18004cfae  lea     r8, WPP_0f8e6464007c3e0bdd6d585d5cfe4b6e_Traceguids
0x18004cfb5  call    WPP_SF_sd
0x18004cfba  jmp     short loc_18004CFCB
0x18004cfbc  mov     rcx, [rcx]; this
0x18004cfbf  call    ?DecrementURLCount@BaseHttpListener@@QEAAJXZ; BaseHttpListener::DecrementURLCount(void)
0x18004cfc4  lea     rbx, WPP_GLOBAL_Control
0x18004cfcb  test    esi, esi
0x18004cfcd  jz      short loc_18004CFF9
0x18004cfcf  mov     rcx, cs:WPP_GLOBAL_Control
0x18004cfd6  cmp     rcx, rbx
0x18004cfd9  jz      short loc_18004CFF9
0x18004cfdb  test    byte ptr [rcx+1Ch], 1
0x18004cfdf  jz      short loc_18004CFF9
0x18004cfe1  mov     rcx, [rcx+10h]
0x18004cfe5  lea     r8, WPP_0f8e6464007c3e0bdd6d585d5cfe4b6e_Traceguids
0x18004cfec  mov     edx, 43h ; 'C'
0x18004cff1  mov     r9d, esi
0x18004cff4  call    WPP_SF_d
0x18004cff9  mov     rcx, rdi; lpCriticalSection
0x18004cffc  call    cs:__imp_LeaveCriticalSection
0x18004d002  mov     eax, esi
0x18004d004  mov     rcx, [rbp+3Fh+var_48]
0x18004d008  xor     rcx, rsp; StackCookie
0x18004d00b  call    __security_check_cookie
0x18004d010  add     rsp, 0A8h
0x18004d017  pop     r15
0x18004d019  pop     r14
0x18004d01b  pop     r13
0x18004d01d  pop     r12
0x18004d01f  pop     rdi
0x18004d020  pop     rsi
0x18004d021  pop     rbx
0x18004d022  pop     rbp
0x18004d023  retn
  ... truncated ...
```
