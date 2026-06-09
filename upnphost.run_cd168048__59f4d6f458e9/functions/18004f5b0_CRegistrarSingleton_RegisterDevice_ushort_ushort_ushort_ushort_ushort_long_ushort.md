# CRegistrarSingleton::RegisterDevice(ushort *,ushort *,ushort *,ushort *,ushort *,long,ushort * *)

- ea: `0x18004f5b0`
- end: `0x18004fa59`
- name: `?RegisterDevice@CRegistrarSingleton@@UEAAJPEAG0000JPEAPEAG@Z`
- size: `1193`
- prototype: `__int64 __usercall@<rax>(CRegistrarSingleton *__hidden this@<rcx>, unsigned __int16 *@<rdx>, unsigned __int16 *@<r8>, unsigned __int16 *@<r9>, unsigned __int16 *, unsigned __int16 *, int, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `20`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800071c0`
- `0x18000e910`
- `0x18001158c`
- `0x1800134e4`
- `0x1800200f4`
- `0x18002b050`
- `0x180030cdc`
- `0x180030fd0`
- `0x18003b0bc`
- `0x18003b1cc`
- `0x18003ba4c`
- `0x18003c018`
- `0x18003cb60`
- `0x180049b64`
- `0x18004e098`
- `0x18004ec90`
- `0x18004f368`
- `0x18004f5b0`
- `0x180050bc0`
- `0x180059010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18004f8f7`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18004f8f7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004f694`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004f6aa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004f694`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004f6aa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004f72e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004f97a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004fa2a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004f72e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004f97a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004fa2a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004f744`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004f917`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004f930`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004f744`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004f917`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004f930`

## pseudocode

```c
__int64 __fastcall CRegistrarSingleton::RegisterDevice(
        struct _RTL_CRITICAL_SECTION *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        unsigned __int16 *pbstr,
        int a7,
        unsigned __int16 **a8)
{
  wchar_t *v10; // rcx
  __int64 result; // rax
  int IsAllowedCOMCallLocality; // edi
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rcx
  int v14; // eax
  unsigned int v15; // r14d
  int v16; // esi
  HANDLE LockSemaphore; // rcx
  HANDLE v18; // rcx
  unsigned __int16 *v19; // r13
  int i; // r14d
  STRSAFE_PCNZWCH v21; // rcx
  LPVOID pv; // [rsp+40h] [rbp-71h] BYREF
  int v23; // [rsp+48h] [rbp-69h] BYREF
  unsigned __int16 **v24; // [rsp+50h] [rbp-61h] BYREF
  int v25; // [rsp+58h] [rbp-59h] BYREF
  unsigned __int16 *v26; // [rsp+60h] [rbp-51h] BYREF
  unsigned __int16 *v27; // [rsp+68h] [rbp-49h]
  unsigned __int16 *v28; // [rsp+70h] [rbp-41h]
  unsigned __int16 *v29; // [rsp+78h] [rbp-39h]
  unsigned __int16 *v30; // [rsp+80h] [rbp-31h] BYREF
  unsigned __int16 **v31; // [rsp+88h] [rbp-29h]
  struct _GUID v32; // [rsp+90h] [rbp-21h] BYREF

  v28 = a5;
  v31 = a8;
  v29 = a4;
  v26 = a3;
  v30 = a2;
  v27 = pbstr;
  v10 = (wchar_t *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 0x40) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_0f8e6464007c3e0bdd6d585d5cfe4b6e_Traceguids);
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
      v16 = 0;
      goto LABEL_45;
    }
    DebugInfo = this[3].DebugInfo;
    pv = 0;
    IsAllowedCOMCallLocality = (*(__int64 (__fastcall **)(PRTL_CRITICAL_SECTION_DEBUG, unsigned __int16 *, unsigned __int16 *, LPVOID *))(*(_QWORD *)&DebugInfo->Type + 40LL))(
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
    v14 = CheckRegistryForLifeTime(&a7);
    v15 = a7;
    if ( v14 )
    {
      if ( a7 )
      {
        v16 = 0;
        if ( a7 < 900 )
        {
          IsAllowedCOMCallLocality = -2147024809;
          goto LABEL_45;
        }
        goto LABEL_24;
      }
      v15 = 1800;
    }
    v16 = 0;
LABEL_24:
    IsAllowedCOMCallLocality = HrSetAutoStart();
    if ( IsAllowedCOMCallLocality >= 0 )
    {
      LockSemaphore = this[2].LockSemaphore;
      v32 = 0;
      IsAllowedCOMCallLocality = (*(__int64 (__fastcall **)(HANDLE, unsigned __int16 *, unsigned __int16 *, struct _GUID *, int, _DWORD))(*(_QWORD *)LockSemaphore + 24LL))(
                                   LockSemaphore,
                                   a2,
                                   v27,
                                   &v32,
                                   1,
                                   0);
      if ( IsAllowedCOMCallLocality >= 0 )
      {
        v18 = this[2].LockSemaphore;
        v24 = 0;
        v23 = 0;
        IsAllowedCOMCallLocality = (*(__int64 (__fastcall **)(HANDLE, struct _GUID *, int *, unsigned __int16 ***))(*(_QWORD *)v18 + 64LL))(
                                     v18,
                                     &v32,
                                     &v23,
                                     &v24);
        if ( IsAllowedCOMCallLocality >= 0 && v24 )
        {
          v19 = v26;
          IsAllowedCOMCallLocality = CDeviceManager::HrAddDevice(
                                       (CDeviceManager *)&this->LockCount,
                                       &v32,
                                       v26,
                                       v29,
                                       v28,
                                       v23,
                                       v24);
          v25 = IsAllowedCOMCallLocality;
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AddUpnpTelemetry>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AddUpnpTelemetry>::GetImpl'::`2'::impl) )
          {
            LODWORD(v26) = 0;
            LODWORD(pv) = 0;
            UpnpHostTelemetry::RegisterDevice<unsigned short * &,int,int,long &>(&v30, &pv, &v26, &v25);
          }
          if ( IsAllowedCOMCallLocality >= 0 )
          {
            IsAllowedCOMCallLocality = (*(__int64 (__fastcall **)(ULONG_PTR, struct _GUID *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned int))(*(_QWORD *)this[2].SpinCount + 24LL))(
                                         this[2].SpinCount,
                                         &v32,
                                         v19,
                                         v29,
                                         v28,
                                         v27,
                                         v15);
            if ( IsAllowedCOMCallLocality >= 0 )
            {
              IsAllowedCOMCallLocality = (*(__int64 (__fastcall **)(HANDLE, struct _GUID *, _QWORD))(*(_QWORD *)this[2].LockSemaphore + 32LL))(
                                           this[2].LockSemaphore,
                                           &v32,
                                           v15);
              if ( IsAllowedCOMCallLocality >= 0 )
              {
                pv = 0;
                IsAllowedCOMCallLocality = HrPhysicalDeviceIdentifierToString(&v32, (struct CUString *)&pv);
                if ( IsAllowedCOMCallLocality >= 0 )
                  IsAllowedCOMCallLocality = CUString::HrGetBSTR((CUString *)&pv, v31);
                free(pv);
              }
            }
          }
          for ( i = 0; i < v23; ++i )
            CoTaskMemFree(v24[i]);
          CoTaskMemFree(v24);
        }
        if ( IsAllowedCOMCallLocality < 0
          && CRegistrarSingleton::HrUnregisterDeviceByPDI((CRegistrarSingleton *)this, &v32, 1) >= 0 )
        {
          v16 = 1;
        }
      }
    }
LABEL_45:
    LeaveCriticalSection(this + 4);
    if ( v16 )
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
          goto LABEL_58;
        if ( (WPP_GLOBAL_Control[14] & 1) == 0 )
        {
LABEL_55:
          if ( v21 != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (v21[14] & 1) != 0 )
            WPP_SF_d(
              *((_QWORD *)v21 + 2),
              43,
              WPP_0f8e6464007c3e0bdd6d585d5cfe4b6e_Traceguids,
              (unsigned int)IsAllowedCOMCallLocality);
          goto LABEL_58;
        }
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          42,
          (unsigned int)WPP_0f8e6464007c3e0bdd6d585d5cfe4b6e_Traceguids,
          (unsigned int)"CRegistrarSingleton::RegisterDevice: g_pVars is null.",
          5);
      }
    }
    if ( !IsAllowedCOMCallLocality )
      goto LABEL_58;
    v21 = WPP_GLOBAL_Control;
    goto LABEL_55;
  }
  if ( v10 != (wchar_t *)&WPP_GLOBAL_Control && (v10[14] & 0x40) != 0 )
    WPP_SF_(*((_QWORD *)v10 + 2), 41, WPP_0f8e6464007c3e0bdd6d585d5cfe4b6e_Traceguids);
  return 2147500037LL;
}

```

## disassembly

```asm
0x18004f5b0  push    rbp
0x18004f5b2  push    rbx
0x18004f5b3  push    rsi
0x18004f5b4  push    rdi
0x18004f5b5  push    r12
0x18004f5b7  push    r13
0x18004f5b9  push    r14
0x18004f5bb  push    r15
0x18004f5bd  lea     rbp, [rsp-7]
0x18004f5c2  sub     rsp, 0B8h
0x18004f5c9  mov     rax, cs:__security_cookie
0x18004f5d0  xor     rax, rsp
0x18004f5d3  mov     [rbp+3Fh+var_50], rax
0x18004f5d7  mov     rax, [rbp+3Fh+arg_20]
0x18004f5db  mov     r13, rdx
0x18004f5de  mov     rsi, [rbp+3Fh+pbstr]
0x18004f5e2  mov     r15, rcx
0x18004f5e5  mov     [rbp+3Fh+var_80], rax
0x18004f5e9  mov     rax, [rbp+3Fh+arg_38]
0x18004f5f0  mov     [rbp+3Fh+var_68], rax
0x18004f5f4  mov     [rbp+3Fh+var_78], r9
0x18004f5f8  mov     [rbp+3Fh+var_90], r8
0x18004f5fc  mov     [rbp+3Fh+var_70], rdx
0x18004f600  mov     [rbp+3Fh+var_88], rsi
0x18004f604  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f60b  lea     rax, WPP_GLOBAL_Control
0x18004f612  cmp     rcx, rax
0x18004f615  jz      short loc_18004F640
0x18004f617  test    byte ptr [rcx+1Ch], 40h
0x18004f61b  jz      short loc_18004F640
0x18004f61d  mov     rcx, [rcx+10h]
0x18004f621  lea     r8, WPP_0f8e6464007c3e0bdd6d585d5cfe4b6e_Traceguids
0x18004f628  mov     edx, 28h ; '('
0x18004f62d  call    WPP_SF_
0x18004f632  mov     rcx, cs:WPP_GLOBAL_Control; this
0x18004f639  lea     rax, WPP_GLOBAL_Control
0x18004f640  cmp     cs:?m_fRegObjDeleted@CRegistrarSingleton@@1HA, 0; int CRegistrarSingleton::m_fRegObjDeleted
0x18004f647  jz      short loc_18004F673
0x18004f649  cmp     rcx, rax
0x18004f64c  jz      short loc_18004F669
0x18004f64e  test    byte ptr [rcx+1Ch], 40h
0x18004f652  jz      short loc_18004F669
0x18004f654  mov     rcx, [rcx+10h]
0x18004f658  lea     r8, WPP_0f8e6464007c3e0bdd6d585d5cfe4b6e_Traceguids
0x18004f65f  mov     edx, 29h ; ')'
0x18004f664  call    WPP_SF_
0x18004f669  mov     eax, 80004005h
0x18004f66e  jmp     loc_18004FA38
0x18004f673  cmp     dword ptr [r15+98h], 0
0x18004f67b  jnz     short loc_18004F68A
0x18004f67d  call    ?CompleteInitialization@CServiceModule@@QEAAJXZ; CServiceModule::CompleteInitialization(void)
0x18004f682  test    eax, eax
0x18004f684  js      loc_18004FA38
0x18004f68a  lea     rbx, [r15+0C8h]
0x18004f691  mov     rcx, rbx; lpCriticalSection
0x18004f694  call    cs:__imp_EnterCriticalSection
0x18004f69b  nop     dword ptr [rax+rax+00h]
0x18004f6a0  lea     r12, [r15+0A0h]
0x18004f6a7  mov     rcx, r12; lpCriticalSection
0x18004f6aa  call    cs:__imp_EnterCriticalSection
0x18004f6b1  nop     dword ptr [rax+rax+00h]
0x18004f6b6  cmp     dword ptr [r15+98h], 0
0x18004f6be  jnz     short loc_18004F6C7
0x18004f6c0  mov     edi, 80004005h
0x18004f6c5  jmp     short loc_18004F72B
0x18004f6c7  mov     ecx, 3
0x18004f6cc  call    ?HrIsAllowedCOMCallLocality@@YAJW4CALL_LOCALITY@@@Z; HrIsAllowedCOMCallLocality(CALL_LOCALITY)
0x18004f6d1  mov     edi, eax
0x18004f6d3  mov     r14d, 1
0x18004f6d9  test    eax, eax
0x18004f6db  js      loc_18004F9E6
0x18004f6e1  mov     rcx, rsi; pbstr
0x18004f6e4  call    ?HrValidateResourcePath@@YAJPEAG@Z; HrValidateResourcePath(ushort *)
0x18004f6e9  mov     edi, eax
0x18004f6eb  test    eax, eax
0x18004f6ed  js      loc_18004F9E6
0x18004f6f3  mov     rcx, [r15+78h]
0x18004f6f7  lea     r9, [rbp+3Fh+pv]
0x18004f6fb  mov     [rbp+3Fh+pv], 0
0x18004f703  mov     r8, rsi
0x18004f706  mov     rdx, r13
0x18004f709  mov     rax, [rcx]
0x18004f70c  mov     rax, [rax+28h]
0x18004f710  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f715  mov     rcx, [rbp+3Fh+pv]; unsigned __int16 *
0x18004f719  mov     edi, eax
0x18004f71b  test    eax, eax
0x18004f71d  jns     short loc_18004F73F
0x18004f71f  lea     rdx, IID_IUPnPRegistrar; struct _GUID *
0x18004f726  call    ?HrSetErrorInfo@@YAJPEBGAEBU_GUID@@@Z; HrSetErrorInfo(ushort const *,_GUID const &)
0x18004f72b  mov     rcx, r12; lpCriticalSection
0x18004f72e  call    cs:__imp_LeaveCriticalSection
0x18004f735  nop     dword ptr [rax+rax+00h]
0x18004f73a  jmp     loc_18004FA27
0x18004f73f  test    rcx, rcx
0x18004f742  jz      short loc_18004F758
0x18004f744  call    cs:__imp_CoTaskMemFree
0x18004f74b  nop     dword ptr [rax+rax+00h]
0x18004f750  mov     [rbp+3Fh+pv], 0
0x18004f758  lea     rcx, [rbp+3Fh+arg_30]; int *
0x18004f75c  call    ?CheckRegistryForLifeTime@@YAHPEAJ@Z; CheckRegistryForLifeTime(long *)
0x18004f761  mov     r14d, [rbp+3Fh+arg_30]
0x18004f765  test    eax, eax
0x18004f767  jz      short loc_18004F778
0x18004f769  test    r14d, r14d
0x18004f76c  jnz     loc_18004F95D
0x18004f772  mov     r14d, 708h
0x18004f778  xor     esi, esi
0x18004f77a  call    ?HrSetAutoStart@@YAJXZ; HrSetAutoStart(void)
0x18004f77f  mov     edi, eax
0x18004f781  test    eax, eax
0x18004f783  js      loc_18004F971
0x18004f789  mov     rcx, [r15+68h]
0x18004f78d  lea     r9, [rbp+3Fh+var_60]
0x18004f791  mov     r8, [rbp+3Fh+var_88]
0x18004f795  xorps   xmm0, xmm0
0x18004f798  movups  xmmword ptr [rbp+3Fh+var_60.Data1], xmm0
0x18004f79c  mov     [rsp+0F0h+var_C8], 0
0x18004f7a4  mov     rdx, r13
0x18004f7a7  mov     rax, [rcx]
0x18004f7aa  mov     dword ptr [rsp+0F0h+var_D0], 1
0x18004f7b2  mov     rax, [rax+18h]
0x18004f7b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f7bb  mov     edi, eax
0x18004f7bd  test    eax, eax
0x18004f7bf  js      loc_18004F971
0x18004f7c5  mov     rcx, [r15+68h]
0x18004f7c9  lea     r9, [rbp+3Fh+var_A0]
0x18004f7cd  mov     [rbp+3Fh+var_A0], 0
0x18004f7d5  lea     r8, [rbp+3Fh+var_A8]
0x18004f7d9  mov     [rbp+3Fh+var_A8], 0
0x18004f7e0  lea     rdx, [rbp+3Fh+var_60]
0x18004f7e4  mov     rax, [rcx]
0x18004f7e7  mov     rax, [rax+40h]
0x18004f7eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f7f0  mov     edi, eax
0x18004f7f2  test    eax, eax
0x18004f7f4  js      loc_18004F93C
0x18004f7fa  mov     rax, [rbp+3Fh+var_A0]
0x18004f7fe  test    rax, rax
0x18004f801  jz      loc_18004F93C
0x18004f807  mov     r13, [rbp+3Fh+var_90]
0x18004f80b  lea     rcx, [r15+8]; this
0x18004f80f  mov     r9, [rbp+3Fh+var_78]; unsigned __int16 *
0x18004f813  lea     rdx, [rbp+3Fh+var_60]; struct _GUID *
0x18004f817  mov     [rsp+0F0h+var_C0], rax; unsigned __int16 **
0x18004f81c  mov     r8, r13; unsigned __int16 *
0x18004f81f  mov     eax, [rbp+3Fh+var_A8]
0x18004f822  mov     [rsp+0F0h+var_C8], eax; int
0x18004f826  mov     rax, [rbp+3Fh+var_80]
0x18004f82a  mov     [rsp+0F0h+var_D0], rax; unsigned __int16 *
0x18004f82f  call    ?HrAddDevice@CDeviceManager@@QEAAJAEBU_GUID@@PEBG11JPEAPEAG@Z; CDeviceManager::HrAddDevice(_GUID const &,ushort const *,ushort const *,ushort const *,long,ushort * *)
0x18004f834  mov     edi, eax
0x18004f836  mov     [rbp+3Fh+var_98], eax
0x18004f839  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AddUpnpTelemetry@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AddUpnpTelemetry@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AddUpnpTelemetry> `wil::Feature<__WilFeatureTraits_Feature_AddUpnpTelemetry>::GetImpl(void)'::`2'::impl
0x18004f840  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AddUpnpTelemetry@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AddUpnpTelemetry>::__private_IsEnabled(void)
0x18004f845  test    al, al
0x18004f847  jz      short loc_18004F86C
0x18004f849  lea     r9, [rbp+3Fh+var_98]
0x18004f84d  mov     dword ptr [rbp+3Fh+var_90], 0
0x18004f854  lea     r8, [rbp+3Fh+var_90]
0x18004f858  mov     dword ptr [rbp+3Fh+pv], 0
0x18004f85f  lea     rdx, [rbp+3Fh+pv]
0x18004f863  lea     rcx, [rbp+3Fh+var_70]
0x18004f867  call    ??$RegisterDevice@AEAPEAGHHAEAJ@UpnpHostTelemetry@@SAXAEAPEAG$$QEAH1AEAJ@Z; UpnpHostTelemetry::RegisterDevice<ushort * &,int,int,long &>(ushort * &,int &&,int &&,long &)
0x18004f86c  test    edi, edi
0x18004f86e  js      loc_18004F903
0x18004f874  mov     rcx, [r15+70h]
0x18004f878  mov     r8, r13
0x18004f87b  mov     rdx, [rbp+3Fh+var_88]
0x18004f87f  mov     r9, [rbp+3Fh+var_78]
0x18004f883  mov     dword ptr [rsp+0F0h+var_C0], r14d
0x18004f888  mov     rax, [rcx]
0x18004f88b  mov     qword ptr [rsp+0F0h+var_C8], rdx
0x18004f890  mov     rdx, [rbp+3Fh+var_80]
0x18004f894  mov     [rsp+0F0h+var_D0], rdx
0x18004f899  lea     rdx, [rbp+3Fh+var_60]
0x18004f89d  mov     rax, [rax+18h]
0x18004f8a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f8a6  mov     edi, eax
0x18004f8a8  test    eax, eax
0x18004f8aa  js      short loc_18004F903
0x18004f8ac  mov     rcx, [r15+68h]
0x18004f8b0  lea     rdx, [rbp+3Fh+var_60]
0x18004f8b4  mov     r8d, r14d
0x18004f8b7  mov     rax, [rcx]
0x18004f8ba  mov     rax, [rax+20h]
0x18004f8be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f8c3  mov     edi, eax
0x18004f8c5  test    eax, eax
0x18004f8c7  js      short loc_18004F903
0x18004f8c9  lea     rdx, [rbp+3Fh+pv]; this
0x18004f8cd  mov     [rbp+3Fh+pv], 0
0x18004f8d5  lea     rcx, [rbp+3Fh+var_60]; struct _GUID *
0x18004f8d9  call    ?HrPhysicalDeviceIdentifierToString@@YAJAEBU_GUID@@AEAVCUString@@@Z; HrPhysicalDeviceIdentifierToString(_GUID const &,CUString &)
0x18004f8de  mov     edi, eax
0x18004f8e0  test    eax, eax
0x18004f8e2  js      short loc_18004F8F3
0x18004f8e4  mov     rdx, [rbp+3Fh+var_68]; unsigned __int16 **
0x18004f8e8  lea     rcx, [rbp+3Fh+pv]; this
0x18004f8ec  call    ?HrGetBSTR@CUString@@QEBAJPEAPEAG@Z; CUString::HrGetBSTR(ushort * *)
0x18004f8f1  mov     edi, eax
0x18004f8f3  mov     rcx, [rbp+3Fh+pv]; Block
0x18004f8f7  call    cs:__imp_free
0x18004f8fe  nop     dword ptr [rax+rax+00h]
0x18004f903  xor     r14d, r14d
0x18004f906  cmp     [rbp+3Fh+var_A8], r14d
0x18004f90a  jle     short loc_18004F92C
0x18004f90c  mov     rcx, [rbp+3Fh+var_A0]
0x18004f910  movsxd  rdx, r14d
0x18004f913  mov     rcx, [rcx+rdx*8]; pv
0x18004f917  call    cs:__imp_CoTaskMemFree
0x18004f91e  nop     dword ptr [rax+rax+00h]
0x18004f923  inc     r14d
0x18004f926  cmp     r14d, [rbp+3Fh+var_A8]
0x18004f92a  jl      short loc_18004F90C
0x18004f92c  mov     rcx, [rbp+3Fh+var_A0]; pv
0x18004f930  call    cs:__imp_CoTaskMemFree
0x18004f937  nop     dword ptr [rax+rax+00h]
0x18004f93c  test    edi, edi
0x18004f93e  jns     short loc_18004F971
0x18004f940  mov     r14d, 1
0x18004f946  lea     rdx, [rbp+3Fh+var_60]; struct _GUID *
0x18004f94a  mov     r8d, r14d; int
0x18004f94d  mov     rcx, r15; this
0x18004f950  call    ?HrUnregisterDeviceByPDI@CRegistrarSingleton@@AEAAJAEAU_GUID@@H@Z; CRegistrarSingleton::HrUnregisterDeviceByPDI(_GUID &,int)
0x18004f955  test    eax, eax
0x18004f957  cmovns  esi, r14d
0x18004f95b  jmp     short loc_18004F977
0x18004f95d  xor     esi, esi
0x18004f95f  cmp     r14d, 384h
0x18004f966  jge     loc_18004F77A
0x18004f96c  mov     edi, 80070057h
0x18004f971  mov     r14d, 1
0x18004f977  mov     rcx, r12; lpCriticalSection
0x18004f97a  call    cs:__imp_LeaveCriticalSection
0x18004f981  nop     dword ptr [rax+rax+00h]
0x18004f986  test    esi, esi
0x18004f988  jz      short loc_18004F9F2
0x18004f98a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1> `wil::Feature<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1>::GetImpl(void)'::`2'::impl
0x18004f991  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1>::__private_IsEnabled(void)
0x18004f996  mov     rcx, cs:?g_pVars@@3PEAVCGlobalVariables@@EA; CGlobalVariables * g_pVars
0x18004f99d  test    al, al
0x18004f99f  jz      short loc_18004F9EA
0x18004f9a1  test    rcx, rcx
0x18004f9a4  jnz     short loc_18004F9EA
0x18004f9a6  mov     edi, 80004005h
0x18004f9ab  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f9b2  lea     rsi, WPP_GLOBAL_Control
0x18004f9b9  cmp     rcx, rsi
0x18004f9bc  jz      short loc_18004FA27
0x18004f9be  test    [rcx+1Ch], r14b
0x18004f9c2  jz      short loc_18004FA04
0x18004f9c4  mov     rcx, [rcx+10h]
0x18004f9c8  lea     r9, aCregistrarsing_3; "CRegistrarSingleton::RegisterDevice: g_"...
0x18004f9cf  mov     edx, 2Ah ; '*'
0x18004f9d4  mov     dword ptr [rsp+0F0h+var_D0], edi
0x18004f9d8  lea     r8, WPP_0f8e6464007c3e0bdd6d585d5cfe4b6e_Traceguids
0x18004f9df  call    WPP_SF_sd
0x18004f9e4  jmp     short loc_18004F9F9
0x18004f9e6  xor     esi, esi
0x18004f9e8  jmp     short loc_18004F977
0x18004f9ea  mov     rcx, [rcx]; this
0x18004f9ed  call    ?DecrementURLCount@BaseHttpListener@@QEAAJXZ; BaseHttpListener::DecrementURLCount(void)
0x18004f9f2  lea     rsi, WPP_GLOBAL_Control
0x18004f9f9  test    edi, edi
0x18004f9fb  jz      short loc_18004FA27
0x18004f9fd  mov     rcx, cs:WPP_GLOBAL_Control
0x18004fa04  cmp     rcx, rsi
0x18004fa07  jz      short loc_18004FA27
0x18004fa09  test    [rcx+1Ch], r14b
0x18004fa0d  jz      short loc_18004FA27
0x18004fa0f  mov     rcx, [rcx+10h]
0x18004fa13  lea     r8, WPP_0f8e6464007c3e0bdd6d585d5cfe4b6e_Traceguids
0x18004fa1a  mov     edx, 2Bh ; '+'
0x18004fa1f  mov     r9d, edi
0x18004fa22  call    WPP_SF_d
0x18004fa27  mov     rcx, rbx; lpCriticalSection
0x18004fa2a  call    cs:__imp_LeaveCriticalSection
0x18004fa31  nop     dword ptr [rax+rax+00h]
0x18004fa36  mov     eax, edi
0x18004fa38  mov     rcx, [rbp+3Fh+var_50]
0x18004fa3c  xor     rcx, rsp; StackCookie
0x18004fa3f  call    __security_check_cookie
0x18004fa44  add     rsp, 0B8h
0x18004fa4b  pop     r15
0x18004fa4d  pop     r14
0x18004fa4f  pop     r13
0x18004fa51  pop     r12
0x18004fa53  pop     rdi
0x18004fa54  pop     rsi
0x18004fa55  pop     rbx
0x18004fa56  pop     rbp
0x18004fa57  retn
```
