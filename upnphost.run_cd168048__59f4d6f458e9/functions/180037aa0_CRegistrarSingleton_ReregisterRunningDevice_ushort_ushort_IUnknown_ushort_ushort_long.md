# CRegistrarSingleton::ReregisterRunningDevice(ushort *,ushort *,IUnknown *,ushort *,ushort *,long)

- ea: `0x180037aa0`
- end: `0x180037f37`
- name: `?ReregisterRunningDevice@CRegistrarSingleton@@UEAAJPEAG0PEAUIUnknown@@00J@Z`
- size: `1175`
- prototype: `__int64 __usercall@<rax>(CRegistrarSingleton *__hidden this@<rcx>, unsigned __int16 *@<rdx>, unsigned __int16 *@<r8>, struct IUnknown *@<r9>, unsigned __int16 *, unsigned __int16 *, int)`
- caller_count: `0`
- callee_count: `21`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800071c0`
- `0x18001158c`
- `0x1800134e4`
- `0x1800200f4`
- `0x18002d6f4`
- `0x180030b0c`
- `0x180030cdc`
- `0x180030fd0`
- `0x1800326c8`
- `0x180032d28`
- `0x180032db4`
- `0x180037aa0`
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

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180037b7a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180037b90`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180037b7a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180037b90`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180037c11`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180037c20`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180037e56`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180037f08`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180037c11`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180037c20`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180037e56`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180037f08`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037c39`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037df1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037e0a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037c39`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037df1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037e0a`

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
      result = CServiceModule::CompleteInitialization((CServiceModule *)v10);
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
      v15 = CheckRegistryForLifeTime(&a7);
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
0x180037aa0  push    rbp
0x180037aa2  push    rbx
0x180037aa3  push    rsi
0x180037aa4  push    rdi
0x180037aa5  push    r12
0x180037aa7  push    r13
0x180037aa9  push    r14
0x180037aab  push    r15
0x180037aad  lea     rbp, [rsp-7]
0x180037ab2  sub     rsp, 98h
0x180037ab9  mov     rax, cs:__security_cookie
0x180037ac0  xor     rax, rsp
0x180037ac3  mov     [rbp+3Fh+var_48], rax
0x180037ac7  mov     rax, [rbp+3Fh+arg_20]
0x180037acb  mov     r13, r8
0x180037ace  mov     r14, [rbp+3Fh+pbstr]
0x180037ad2  mov     r12, rdx
0x180037ad5  mov     [rbp+3Fh+var_78], rax
0x180037ad9  mov     r15, rcx
0x180037adc  mov     [rbp+3Fh+var_80], r14
0x180037ae0  mov     [rbp+3Fh+var_68], r9
0x180037ae4  mov     [rbp+3Fh+var_70], r8
0x180037ae8  mov     [rbp+3Fh+var_60], r8
0x180037aec  mov     rcx, cs:WPP_GLOBAL_Control
0x180037af3  lea     rax, WPP_GLOBAL_Control
0x180037afa  cmp     rcx, rax
0x180037afd  jz      short loc_180037B28
0x180037aff  test    byte ptr [rcx+1Ch], 40h
0x180037b03  jz      short loc_180037B28
0x180037b05  mov     rcx, [rcx+10h]
0x180037b09  lea     r8, WPP_0f8e6464007c3e0bdd6d585d5cfe4b6e_Traceguids
0x180037b10  mov     edx, 44h ; 'D'
0x180037b15  call    WPP_SF_
0x180037b1a  mov     rcx, cs:WPP_GLOBAL_Control; this
0x180037b21  lea     rax, WPP_GLOBAL_Control
0x180037b28  xor     esi, esi
0x180037b2a  cmp     cs:?m_fRegObjDeleted@CRegistrarSingleton@@1HA, esi; int CRegistrarSingleton::m_fRegObjDeleted
0x180037b30  jz      short loc_180037B5A
0x180037b32  cmp     rcx, rax
0x180037b35  jz      short loc_180037B50
0x180037b37  test    byte ptr [rcx+1Ch], 40h
0x180037b3b  jz      short loc_180037B50
0x180037b3d  mov     rcx, [rcx+10h]
0x180037b41  lea     edx, [rsi+45h]
0x180037b44  lea     r8, WPP_0f8e6464007c3e0bdd6d585d5cfe4b6e_Traceguids
0x180037b4b  call    WPP_SF_
0x180037b50  mov     eax, 80004005h
0x180037b55  jmp     loc_180037F16
0x180037b5a  cmp     [r15+98h], esi
0x180037b61  jnz     short loc_180037B70
0x180037b63  call    ?CompleteInitialization@CServiceModule@@QEAAJXZ; CServiceModule::CompleteInitialization(void)
0x180037b68  test    eax, eax
0x180037b6a  js      loc_180037F16
0x180037b70  lea     rdi, [r15+0C8h]
0x180037b77  mov     rcx, rdi; lpCriticalSection
0x180037b7a  call    cs:__imp_EnterCriticalSection
0x180037b81  nop     dword ptr [rax+rax+00h]
0x180037b86  lea     rbx, [r15+0A0h]
0x180037b8d  mov     rcx, rbx; lpCriticalSection
0x180037b90  call    cs:__imp_EnterCriticalSection
0x180037b97  nop     dword ptr [rax+rax+00h]
0x180037b9c  cmp     [r15+98h], esi
0x180037ba3  jnz     short loc_180037BAD
0x180037ba5  mov     r14d, 80004005h
0x180037bab  jmp     short loc_180037C0E
0x180037bad  mov     ecx, 3
0x180037bb2  call    ?HrIsAllowedCOMCallLocality@@YAJW4CALL_LOCALITY@@@Z; HrIsAllowedCOMCallLocality(CALL_LOCALITY)
0x180037bb7  mov     esi, eax
0x180037bb9  test    eax, eax
0x180037bbb  js      loc_180037C87
0x180037bc1  mov     rcx, r14; pbstr
0x180037bc4  call    ?HrValidateResourcePath@@YAJPEAG@Z; HrValidateResourcePath(ushort *)
0x180037bc9  mov     esi, eax
0x180037bcb  test    eax, eax
0x180037bcd  js      loc_180037C87
0x180037bd3  mov     rcx, [r15+78h]
0x180037bd7  lea     r9, [rbp+3Fh+pv]
0x180037bdb  mov     [rbp+3Fh+pv], 0
0x180037be3  mov     r8, r14
0x180037be6  mov     rdx, r13
0x180037be9  mov     rax, [rcx]
0x180037bec  mov     rax, [rax+28h]
0x180037bf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037bf5  mov     rcx, [rbp+3Fh+pv]; unsigned __int16 *
0x180037bf9  mov     r14d, eax
0x180037bfc  mov     esi, eax
0x180037bfe  test    eax, eax
0x180037c00  jns     short loc_180037C34
0x180037c02  lea     rdx, IID_IUPnPReregistrar; struct _GUID *
0x180037c09  call    ?HrSetErrorInfo@@YAJPEBGAEBU_GUID@@@Z; HrSetErrorInfo(ushort const *,_GUID const &)
0x180037c0e  mov     rcx, rbx; lpCriticalSection
0x180037c11  call    cs:__imp_LeaveCriticalSection
0x180037c18  nop     dword ptr [rax+rax+00h]
0x180037c1d  mov     rcx, rdi; lpCriticalSection
0x180037c20  call    cs:__imp_LeaveCriticalSection
0x180037c27  nop     dword ptr [rax+rax+00h]
0x180037c2c  mov     eax, r14d
0x180037c2f  jmp     loc_180037F16
0x180037c34  test    rcx, rcx
0x180037c37  jz      short loc_180037C4D
0x180037c39  call    cs:__imp_CoTaskMemFree
0x180037c40  nop     dword ptr [rax+rax+00h]
0x180037c45  mov     [rbp+3Fh+pv], 0
0x180037c4d  lea     rcx, [rbp+3Fh+arg_30]; int *
0x180037c51  call    ?CheckRegistryForLifeTime@@YAHPEAJ@Z; CheckRegistryForLifeTime(long *)
0x180037c56  mov     r14d, [rbp+3Fh+arg_30]
0x180037c5a  test    eax, eax
0x180037c5c  jz      short loc_180037C7A
0x180037c5e  test    r14d, r14d
0x180037c61  jnz     short loc_180037C6B
0x180037c63  mov     r14d, 708h
0x180037c69  jmp     short loc_180037C7A
0x180037c6b  cmp     r14d, 384h
0x180037c72  mov     eax, 80070057h
0x180037c77  cmovl   esi, eax
0x180037c7a  test    r12, r12
0x180037c7d  mov     eax, 80004003h
0x180037c82  cmovz   esi, eax
0x180037c85  jmp     short loc_180037C8B
0x180037c87  mov     r14d, [rbp+3Fh+arg_30]
0x180037c8b  xor     r13d, r13d
0x180037c8e  test    esi, esi
0x180037c90  js      loc_180037E53
0x180037c96  xorps   xmm0, xmm0
0x180037c99  lea     rdx, [rbp+3Fh+var_58]; struct _GUID *
0x180037c9d  mov     rcx, r12; unsigned __int16 *
0x180037ca0  movups  xmmword ptr [rbp+3Fh+var_58.Data1], xmm0
0x180037ca4  call    ?HrStringToPhysicalDeviceIdentifier@@YAJPEBGAEAU_GUID@@@Z; HrStringToPhysicalDeviceIdentifier(ushort const *,_GUID &)
0x180037ca9  mov     esi, eax
0x180037cab  test    eax, eax
0x180037cad  js      loc_180037E45
0x180037cb3  lea     rdx, [rbp+3Fh+var_58]; struct _GUID *
0x180037cb7  lea     rcx, [r15+8]; this
0x180037cbb  call    ?FHasDevice@CDeviceManager@@QEAAHAEBU_GUID@@@Z; CDeviceManager::FHasDevice(_GUID const &)
0x180037cc0  test    eax, eax
0x180037cc2  jz      short loc_180037CCE
0x180037cc4  mov     esi, 8004A031h
0x180037cc9  jmp     loc_180037E53
0x180037cce  mov     rcx, [r15+68h]
0x180037cd2  lea     r9, [rbp+3Fh+var_58]
0x180037cd6  mov     r8, [rbp+3Fh+var_80]
0x180037cda  mov     rdx, [rbp+3Fh+var_70]
0x180037cde  mov     dword ptr [rsp+0D0h+var_A8], 1
0x180037ce6  mov     rax, [rcx]
0x180037ce9  mov     [rsp+0D0h+var_B0], r13d
0x180037cee  mov     rax, [rax+18h]
0x180037cf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037cf7  mov     esi, eax
0x180037cf9  test    eax, eax
0x180037cfb  js      loc_180037E53
0x180037d01  mov     rcx, [r15+68h]
0x180037d05  lea     r9, [rbp+3Fh+var_80]
0x180037d09  mov     [rbp+3Fh+var_80], r13
0x180037d0d  lea     r8, [rbp+3Fh+var_90]
0x180037d11  mov     [rbp+3Fh+var_90], r13d
0x180037d15  lea     rdx, [rbp+3Fh+var_58]
0x180037d19  mov     rax, [rcx]
0x180037d1c  mov     rax, [rax+40h]
0x180037d20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037d25  mov     esi, eax
0x180037d27  test    eax, eax
0x180037d29  js      loc_180037E16
0x180037d2f  mov     rax, [rbp+3Fh+var_80]
0x180037d33  test    rax, rax
0x180037d36  jz      loc_180037E16
0x180037d3c  mov     r9, [rbp+3Fh+var_78]; unsigned __int16 *
0x180037d40  lea     rdx, [rbp+3Fh+var_58]; struct _GUID *
0x180037d44  mov     r8, [rbp+3Fh+var_68]; struct IUnknown *
0x180037d48  lea     rcx, [r15+8]; this
0x180037d4c  mov     [rsp+0D0h+var_A8], rax; unsigned __int16 **
0x180037d51  mov     eax, [rbp+3Fh+var_90]
0x180037d54  mov     [rsp+0D0h+var_B0], eax; int
0x180037d58  call    ?HrAddRunningDevice@CDeviceManager@@QEAAJAEBU_GUID@@PEAUIUnknown@@PEBGJPEAPEAG@Z; CDeviceManager::HrAddRunningDevice(_GUID const &,IUnknown *,ushort const *,long,ushort * *)
0x180037d5d  mov     esi, eax
0x180037d5f  mov     dword ptr [rbp+3Fh+var_78], eax
0x180037d62  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AddUpnpTelemetry@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AddUpnpTelemetry@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AddUpnpTelemetry> `wil::Feature<__WilFeatureTraits_Feature_AddUpnpTelemetry>::GetImpl(void)'::`2'::impl
0x180037d69  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AddUpnpTelemetry@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AddUpnpTelemetry>::__private_IsEnabled(void)
0x180037d6e  test    al, al
0x180037d70  jz      short loc_180037D92
0x180037d72  mov     eax, 1
0x180037d77  lea     r9, [rbp+3Fh+var_78]
0x180037d7b  lea     r8, [rbp+3Fh+var_70]
0x180037d7f  mov     dword ptr [rbp+3Fh+var_70], eax
0x180037d82  lea     rdx, [rbp+3Fh+pv]
0x180037d86  mov     dword ptr [rbp+3Fh+pv], eax
0x180037d89  lea     rcx, [rbp+3Fh+var_60]
0x180037d8d  call    ??$RegisterDevice@AEAPEAGHHAEAJ@UpnpHostTelemetry@@SAXAEAPEAG$$QEAH1AEAJ@Z; UpnpHostTelemetry::RegisterDevice<ushort * &,int,int,long &>(ushort * &,int &&,int &&,long &)
0x180037d92  test    esi, esi
0x180037d94  js      short loc_180037DDD
0x180037d96  mov     r12, [rbp+3Fh+var_68]
0x180037d9a  lea     rdx, [rbp+3Fh+var_58]; struct _GUID *
0x180037d9e  mov     r8, r12; struct IUnknown *
0x180037da1  mov     rcx, r15; this
0x180037da4  call    ?HrStoreDeviceControlHttpHeadersObject@CRegistrarSingleton@@AEAAJAEAU_GUID@@PEAUIUnknown@@@Z; CRegistrarSingleton::HrStoreDeviceControlHttpHeadersObject(_GUID &,IUnknown *)
0x180037da9  mov     esi, eax
0x180037dab  test    eax, eax
0x180037dad  js      short loc_180037DDD
0x180037daf  mov     r8, r12; struct IUnknown *
0x180037db2  lea     rdx, [rbp+3Fh+var_58]; struct _GUID *
0x180037db6  mov     rcx, r15; this
0x180037db9  call    ?HrStoreDeviceControlSsdpHeadersObject@CRegistrarSingleton@@AEAAJAEAU_GUID@@PEAUIUnknown@@@Z; CRegistrarSingleton::HrStoreDeviceControlSsdpHeadersObject(_GUID &,IUnknown *)
0x180037dbe  mov     esi, eax
0x180037dc0  test    eax, eax
0x180037dc2  js      short loc_180037DDD
0x180037dc4  mov     rcx, [r15+68h]
0x180037dc8  lea     rdx, [rbp+3Fh+var_58]
0x180037dcc  mov     r8d, r14d
0x180037dcf  mov     rax, [rcx]
0x180037dd2  mov     rax, [rax+20h]
0x180037dd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037ddb  mov     esi, eax
0x180037ddd  xor     r14d, r14d
0x180037de0  cmp     [rbp+3Fh+var_90], r13d
0x180037de4  jle     short loc_180037E06
0x180037de6  mov     rcx, [rbp+3Fh+var_80]
0x180037dea  movsxd  rdx, r14d
0x180037ded  mov     rcx, [rcx+rdx*8]; pv
0x180037df1  call    cs:__imp_CoTaskMemFree
0x180037df8  nop     dword ptr [rax+rax+00h]
0x180037dfd  inc     r14d
0x180037e00  cmp     r14d, [rbp+3Fh+var_90]
0x180037e04  jl      short loc_180037DE6
0x180037e06  mov     rcx, [rbp+3Fh+var_80]; pv
0x180037e0a  call    cs:__imp_CoTaskMemFree
0x180037e11  nop     dword ptr [rax+rax+00h]
0x180037e16  mov     ecx, 80000000h
0x180037e1b  lea     eax, [rsi+rcx]
0x180037e1e  test    ecx, eax
0x180037e20  jnz     short loc_180037E53
0x180037e22  cmp     esi, 8004A031h
0x180037e28  jz      short loc_180037E53
0x180037e2a  xor     r8d, r8d; int
0x180037e2d  lea     rdx, [rbp+3Fh+var_58]; struct _GUID *
0x180037e31  mov     rcx, r15; this
0x180037e34  call    ?HrUnregisterDeviceByPDI@CRegistrarSingleton@@AEAAJAEAU_GUID@@H@Z; CRegistrarSingleton::HrUnregisterDeviceByPDI(_GUID &,int)
0x180037e39  test    eax, eax
0x180037e3b  js      short loc_180037E53
0x180037e3d  mov     r13d, 1
0x180037e43  jmp     short loc_180037E53
0x180037e45  cmp     esi, 800401F3h
0x180037e4b  mov     eax, 80070057h
0x180037e50  cmovz   esi, eax
0x180037e53  mov     rcx, rbx; lpCriticalSection
0x180037e56  call    cs:__imp_LeaveCriticalSection
0x180037e5d  nop     dword ptr [rax+rax+00h]
0x180037e62  test    r13d, r13d
0x180037e65  jz      short loc_180037ED0
0x180037e67  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1> `wil::Feature<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1>::GetImpl(void)'::`2'::impl
0x180037e6e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1>::__private_IsEnabled(void)
0x180037e73  mov     rcx, cs:?g_pVars@@3PEAVCGlobalVariables@@EA; CGlobalVariables * g_pVars
0x180037e7a  test    al, al
0x180037e7c  jz      short loc_180037EC8
0x180037e7e  test    rcx, rcx
0x180037e81  jnz     short loc_180037EC8
0x180037e83  mov     r14d, 80004005h
0x180037e89  mov     esi, r14d
0x180037e8c  mov     rcx, cs:WPP_GLOBAL_Control
0x180037e93  lea     rbx, WPP_GLOBAL_Control
0x180037e9a  cmp     rcx, rbx
0x180037e9d  jz      short loc_180037F05
0x180037e9f  test    byte ptr [rcx+1Ch], 1
0x180037ea3  jz      short loc_180037EE2
0x180037ea5  mov     rcx, [rcx+10h]
0x180037ea9  lea     r9, aCregistrarsing_1; "CRegistrarSingleton::ReregisterRunningD"...
0x180037eb0  mov     edx, 46h ; 'F'
0x180037eb5  mov     [rsp+0D0h+var_B0], r14d
0x180037eba  lea     r8, WPP_0f8e6464007c3e0bdd6d585d5cfe4b6e_Traceguids
0x180037ec1  call    WPP_SF_sd
0x180037ec6  jmp     short loc_180037ED7
0x180037ec8  mov     rcx, [rcx]; this
0x180037ecb  call    ?DecrementURLCount@BaseHttpListener@@QEAAJXZ; BaseHttpListener::DecrementURLCount(void)
0x180037ed0  lea     rbx, WPP_GLOBAL_Control
0x180037ed7  test    esi, esi
0x180037ed9  jz      short loc_180037F05
0x180037edb  mov     rcx, cs:WPP_GLOBAL_Control
0x180037ee2  cmp     rcx, rbx
0x180037ee5  jz      short loc_180037F05
0x180037ee7  test    byte ptr [rcx+1Ch], 1
0x180037eeb  jz      short loc_180037F05
0x180037eed  mov     rcx, [rcx+10h]
0x180037ef1  lea     r8, WPP_0f8e6464007c3e0bdd6d585d5cfe4b6e_Traceguids
0x180037ef8  mov     edx, 47h ; 'G'
0x180037efd  mov     r9d, esi
0x180037f00  call    WPP_SF_d
0x180037f05  mov     rcx, rdi; lpCriticalSection
0x180037f08  call    cs:__imp_LeaveCriticalSection
0x180037f0f  nop     dword ptr [rax+rax+00h]
0x180037f14  mov     eax, esi
0x180037f16  mov     rcx, [rbp+3Fh+var_48]
0x180037f1a  xor     rcx, rsp; StackCookie
0x180037f1d  call    __security_check_cookie
0x180037f22  add     rsp, 98h
0x180037f29  pop     r15
0x180037f2b  pop     r14
0x180037f2d  pop     r13
0x180037f2f  pop     r12
0x180037f31  pop     rdi
0x180037f32  pop     rsi
0x180037f33  pop     rbx
0x180037f34  pop     rbp
  ... truncated ...
```
