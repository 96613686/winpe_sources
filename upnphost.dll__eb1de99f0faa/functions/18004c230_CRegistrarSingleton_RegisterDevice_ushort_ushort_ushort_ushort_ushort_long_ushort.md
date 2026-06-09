# CRegistrarSingleton::RegisterDevice(ushort *,ushort *,ushort *,ushort *,ushort *,long,ushort * *)

- ea: `0x18004c230`
- end: `0x18004c6a2`
- name: `?RegisterDevice@CRegistrarSingleton@@UEAAJPEAG0000JPEAPEAG@Z`
- size: `1138`
- prototype: `__int64 __usercall@<rax>(CRegistrarSingleton *__hidden this@<rcx>, unsigned __int16 *@<rdx>, unsigned __int16 *@<r8>, unsigned __int16 *@<r9>, unsigned __int16 *, unsigned __int16 *, int, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `20`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000db4c`
- `0x180013180`
- `0x180019c98`
- `0x18001c6bc`
- `0x18001e478`
- `0x180029cb0`
- `0x18002f384`
- `0x18002f684`
- `0x180038be4`
- `0x180038ce4`
- `0x1800394b4`
- `0x180039a84`
- `0x18003a560`
- `0x180046de8`
- `0x18004ae14`
- `0x18004b99c`
- `0x18004c024`
- `0x18004c230`
- `0x18004d770`
- `0x180055010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18004c55f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18004c55f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004c314`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004c324`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004c314`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004c324`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004c3a2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004c5d0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004c67a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004c3a2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004c5d0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004c67a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004c3b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004c579`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004c58c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004c3b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004c579`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004c58c`

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
      result = CServiceModule::CompleteInitialization((struct IUnknown *)v10);
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
    v14 = CheckRegistryForLifeTime((unsigned int *)&a7);
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
0x18004c230  push    rbp
0x18004c232  push    rbx
0x18004c233  push    rsi
0x18004c234  push    rdi
0x18004c235  push    r12
0x18004c237  push    r13
0x18004c239  push    r14
0x18004c23b  push    r15
0x18004c23d  lea     rbp, [rsp-7]
0x18004c242  sub     rsp, 0B8h
0x18004c249  mov     rax, cs:__security_cookie
0x18004c250  xor     rax, rsp
0x18004c253  mov     [rbp+3Fh+var_50], rax
0x18004c257  mov     rax, [rbp+3Fh+arg_20]
0x18004c25b  mov     r13, rdx
0x18004c25e  mov     rsi, [rbp+3Fh+pbstr]
0x18004c262  mov     r15, rcx
0x18004c265  mov     [rbp+3Fh+var_80], rax
0x18004c269  mov     rax, [rbp+3Fh+arg_38]
0x18004c270  mov     [rbp+3Fh+var_68], rax
0x18004c274  mov     [rbp+3Fh+var_78], r9
0x18004c278  mov     [rbp+3Fh+var_90], r8
0x18004c27c  mov     [rbp+3Fh+var_70], rdx
0x18004c280  mov     [rbp+3Fh+var_88], rsi
0x18004c284  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c28b  lea     rax, WPP_GLOBAL_Control
0x18004c292  cmp     rcx, rax
0x18004c295  jz      short loc_18004C2C0
0x18004c297  test    byte ptr [rcx+1Ch], 40h
0x18004c29b  jz      short loc_18004C2C0
0x18004c29d  mov     rcx, [rcx+10h]
0x18004c2a1  lea     r8, WPP_0f8e6464007c3e0bdd6d585d5cfe4b6e_Traceguids
0x18004c2a8  mov     edx, 28h ; '('
0x18004c2ad  call    WPP_SF_
0x18004c2b2  mov     rcx, cs:WPP_GLOBAL_Control; this
0x18004c2b9  lea     rax, WPP_GLOBAL_Control
0x18004c2c0  cmp     cs:?m_fRegObjDeleted@CRegistrarSingleton@@1HA, 0; int CRegistrarSingleton::m_fRegObjDeleted
0x18004c2c7  jz      short loc_18004C2F3
0x18004c2c9  cmp     rcx, rax
0x18004c2cc  jz      short loc_18004C2E9
0x18004c2ce  test    byte ptr [rcx+1Ch], 40h
0x18004c2d2  jz      short loc_18004C2E9
0x18004c2d4  mov     rcx, [rcx+10h]
0x18004c2d8  lea     r8, WPP_0f8e6464007c3e0bdd6d585d5cfe4b6e_Traceguids
0x18004c2df  mov     edx, 29h ; ')'
0x18004c2e4  call    WPP_SF_
0x18004c2e9  mov     eax, 80004005h
0x18004c2ee  jmp     loc_18004C682
0x18004c2f3  cmp     dword ptr [r15+98h], 0
0x18004c2fb  jnz     short loc_18004C30A
0x18004c2fd  call    ?CompleteInitialization@CServiceModule@@QEAAJXZ; CServiceModule::CompleteInitialization(void)
0x18004c302  test    eax, eax
0x18004c304  js      loc_18004C682
0x18004c30a  lea     rbx, [r15+0C8h]
0x18004c311  mov     rcx, rbx; lpCriticalSection
0x18004c314  call    cs:__imp_EnterCriticalSection
0x18004c31a  lea     r12, [r15+0A0h]
0x18004c321  mov     rcx, r12; lpCriticalSection
0x18004c324  call    cs:__imp_EnterCriticalSection
0x18004c32a  cmp     dword ptr [r15+98h], 0
0x18004c332  jnz     short loc_18004C33B
0x18004c334  mov     edi, 80004005h
0x18004c339  jmp     short loc_18004C39F
0x18004c33b  mov     ecx, 3
0x18004c340  call    ?HrIsAllowedCOMCallLocality@@YAJW4CALL_LOCALITY@@@Z; HrIsAllowedCOMCallLocality(CALL_LOCALITY)
0x18004c345  mov     edi, eax
0x18004c347  mov     r14d, 1
0x18004c34d  test    eax, eax
0x18004c34f  js      loc_18004C636
0x18004c355  mov     rcx, rsi; pbstr
0x18004c358  call    ?HrValidateResourcePath@@YAJPEAG@Z; HrValidateResourcePath(ushort *)
0x18004c35d  mov     edi, eax
0x18004c35f  test    eax, eax
0x18004c361  js      loc_18004C636
0x18004c367  mov     rcx, [r15+78h]
0x18004c36b  lea     r9, [rbp+3Fh+pv]
0x18004c36f  mov     [rbp+3Fh+pv], 0
0x18004c377  mov     r8, rsi
0x18004c37a  mov     rdx, r13
0x18004c37d  mov     rax, [rcx]
0x18004c380  mov     rax, [rax+28h]
0x18004c384  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c389  mov     rcx, [rbp+3Fh+pv]; unsigned __int16 *
0x18004c38d  mov     edi, eax
0x18004c38f  test    eax, eax
0x18004c391  jns     short loc_18004C3AD
0x18004c393  lea     rdx, IID_IUPnPRegistrar; struct _GUID *
0x18004c39a  call    ?HrSetErrorInfo@@YAJPEBGAEBU_GUID@@@Z; HrSetErrorInfo(ushort const *,_GUID const &)
0x18004c39f  mov     rcx, r12; lpCriticalSection
0x18004c3a2  call    cs:__imp_LeaveCriticalSection
0x18004c3a8  jmp     loc_18004C677
0x18004c3ad  test    rcx, rcx
0x18004c3b0  jz      short loc_18004C3C0
0x18004c3b2  call    cs:__imp_CoTaskMemFree
0x18004c3b8  mov     [rbp+3Fh+pv], 0
0x18004c3c0  lea     rcx, [rbp+3Fh+arg_30]; int *
0x18004c3c4  call    ?CheckRegistryForLifeTime@@YAHPEAJ@Z; CheckRegistryForLifeTime(long *)
0x18004c3c9  mov     r14d, [rbp+3Fh+arg_30]
0x18004c3cd  test    eax, eax
0x18004c3cf  jz      short loc_18004C3E0
0x18004c3d1  test    r14d, r14d
0x18004c3d4  jnz     loc_18004C5B3
0x18004c3da  mov     r14d, 708h
0x18004c3e0  xor     esi, esi
0x18004c3e2  call    ?HrSetAutoStart@@YAJXZ; HrSetAutoStart(void)
0x18004c3e7  mov     edi, eax
0x18004c3e9  test    eax, eax
0x18004c3eb  js      loc_18004C5C7
0x18004c3f1  mov     rcx, [r15+68h]
0x18004c3f5  lea     r9, [rbp+3Fh+var_60]
0x18004c3f9  mov     r8, [rbp+3Fh+var_88]
0x18004c3fd  xorps   xmm0, xmm0
0x18004c400  movups  xmmword ptr [rbp+3Fh+var_60.Data1], xmm0
0x18004c404  mov     [rsp+0F0h+var_C8], 0
0x18004c40c  mov     rdx, r13
0x18004c40f  mov     rax, [rcx]
0x18004c412  mov     dword ptr [rsp+0F0h+var_D0], 1
0x18004c41a  mov     rax, [rax+18h]
0x18004c41e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c423  mov     edi, eax
0x18004c425  test    eax, eax
0x18004c427  js      loc_18004C5C7
0x18004c42d  mov     rcx, [r15+68h]
0x18004c431  lea     r9, [rbp+3Fh+var_A0]
0x18004c435  mov     [rbp+3Fh+var_A0], 0
0x18004c43d  lea     r8, [rbp+3Fh+var_A8]
0x18004c441  mov     [rbp+3Fh+var_A8], 0
0x18004c448  lea     rdx, [rbp+3Fh+var_60]
0x18004c44c  mov     rax, [rcx]
0x18004c44f  mov     rax, [rax+40h]
0x18004c453  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c458  mov     edi, eax
0x18004c45a  test    eax, eax
0x18004c45c  js      loc_18004C592
0x18004c462  mov     rax, [rbp+3Fh+var_A0]
0x18004c466  test    rax, rax
0x18004c469  jz      loc_18004C592
0x18004c46f  mov     r13, [rbp+3Fh+var_90]
0x18004c473  lea     rcx, [r15+8]; this
0x18004c477  mov     r9, [rbp+3Fh+var_78]; unsigned __int16 *
0x18004c47b  lea     rdx, [rbp+3Fh+var_60]; struct _GUID *
0x18004c47f  mov     [rsp+0F0h+var_C0], rax; unsigned __int16 **
0x18004c484  mov     r8, r13; unsigned __int16 *
0x18004c487  mov     eax, [rbp+3Fh+var_A8]
0x18004c48a  mov     [rsp+0F0h+var_C8], eax; int
0x18004c48e  mov     rax, [rbp+3Fh+var_80]
0x18004c492  mov     [rsp+0F0h+var_D0], rax; unsigned __int16 *
0x18004c497  call    ?HrAddDevice@CDeviceManager@@QEAAJAEBU_GUID@@PEBG11JPEAPEAG@Z; CDeviceManager::HrAddDevice(_GUID const &,ushort const *,ushort const *,ushort const *,long,ushort * *)
0x18004c49c  mov     edi, eax
0x18004c49e  mov     [rbp+3Fh+var_98], eax
0x18004c4a1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AddUpnpTelemetry@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AddUpnpTelemetry@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AddUpnpTelemetry> `wil::Feature<__WilFeatureTraits_Feature_AddUpnpTelemetry>::GetImpl(void)'::`2'::impl
0x18004c4a8  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AddUpnpTelemetry@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AddUpnpTelemetry>::__private_IsEnabled(void)
0x18004c4ad  test    al, al
0x18004c4af  jz      short loc_18004C4D4
0x18004c4b1  lea     r9, [rbp+3Fh+var_98]
0x18004c4b5  mov     dword ptr [rbp+3Fh+var_90], 0
0x18004c4bc  lea     r8, [rbp+3Fh+var_90]
0x18004c4c0  mov     dword ptr [rbp+3Fh+pv], 0
0x18004c4c7  lea     rdx, [rbp+3Fh+pv]
0x18004c4cb  lea     rcx, [rbp+3Fh+var_70]
0x18004c4cf  call    ??$RegisterDevice@AEAPEAGHHAEAJ@UpnpHostTelemetry@@SAXAEAPEAG$$QEAH1AEAJ@Z; UpnpHostTelemetry::RegisterDevice<ushort * &,int,int,long &>(ushort * &,int &&,int &&,long &)
0x18004c4d4  test    edi, edi
0x18004c4d6  js      loc_18004C565
0x18004c4dc  mov     rcx, [r15+70h]
0x18004c4e0  mov     r8, r13
0x18004c4e3  mov     rdx, [rbp+3Fh+var_88]
0x18004c4e7  mov     r9, [rbp+3Fh+var_78]
0x18004c4eb  mov     dword ptr [rsp+0F0h+var_C0], r14d
0x18004c4f0  mov     rax, [rcx]
0x18004c4f3  mov     qword ptr [rsp+0F0h+var_C8], rdx
0x18004c4f8  mov     rdx, [rbp+3Fh+var_80]
0x18004c4fc  mov     [rsp+0F0h+var_D0], rdx
0x18004c501  lea     rdx, [rbp+3Fh+var_60]
0x18004c505  mov     rax, [rax+18h]
0x18004c509  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c50e  mov     edi, eax
0x18004c510  test    eax, eax
0x18004c512  js      short loc_18004C565
0x18004c514  mov     rcx, [r15+68h]
0x18004c518  lea     rdx, [rbp+3Fh+var_60]
0x18004c51c  mov     r8d, r14d
0x18004c51f  mov     rax, [rcx]
0x18004c522  mov     rax, [rax+20h]
0x18004c526  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c52b  mov     edi, eax
0x18004c52d  test    eax, eax
0x18004c52f  js      short loc_18004C565
0x18004c531  lea     rdx, [rbp+3Fh+pv]; this
0x18004c535  mov     [rbp+3Fh+pv], 0
0x18004c53d  lea     rcx, [rbp+3Fh+var_60]; struct _GUID *
0x18004c541  call    ?HrPhysicalDeviceIdentifierToString@@YAJAEBU_GUID@@AEAVCUString@@@Z; HrPhysicalDeviceIdentifierToString(_GUID const &,CUString &)
0x18004c546  mov     edi, eax
0x18004c548  test    eax, eax
0x18004c54a  js      short loc_18004C55B
0x18004c54c  mov     rdx, [rbp+3Fh+var_68]; unsigned __int16 **
0x18004c550  lea     rcx, [rbp+3Fh+pv]; this
0x18004c554  call    ?HrGetBSTR@CUString@@QEBAJPEAPEAG@Z; CUString::HrGetBSTR(ushort * *)
0x18004c559  mov     edi, eax
0x18004c55b  mov     rcx, [rbp+3Fh+pv]; Block
0x18004c55f  call    cs:__imp_free
0x18004c565  xor     r14d, r14d
0x18004c568  cmp     [rbp+3Fh+var_A8], r14d
0x18004c56c  jle     short loc_18004C588
0x18004c56e  mov     rcx, [rbp+3Fh+var_A0]
0x18004c572  movsxd  rdx, r14d
0x18004c575  mov     rcx, [rcx+rdx*8]; pv
0x18004c579  call    cs:__imp_CoTaskMemFree
0x18004c57f  inc     r14d
0x18004c582  cmp     r14d, [rbp+3Fh+var_A8]
0x18004c586  jl      short loc_18004C56E
0x18004c588  mov     rcx, [rbp+3Fh+var_A0]; pv
0x18004c58c  call    cs:__imp_CoTaskMemFree
0x18004c592  test    edi, edi
0x18004c594  jns     short loc_18004C5C7
0x18004c596  mov     r14d, 1
0x18004c59c  lea     rdx, [rbp+3Fh+var_60]; struct _GUID *
0x18004c5a0  mov     r8d, r14d; int
0x18004c5a3  mov     rcx, r15; this
0x18004c5a6  call    ?HrUnregisterDeviceByPDI@CRegistrarSingleton@@AEAAJAEAU_GUID@@H@Z; CRegistrarSingleton::HrUnregisterDeviceByPDI(_GUID &,int)
0x18004c5ab  test    eax, eax
0x18004c5ad  cmovns  esi, r14d
0x18004c5b1  jmp     short loc_18004C5CD
0x18004c5b3  xor     esi, esi
0x18004c5b5  cmp     r14d, 384h
0x18004c5bc  jge     loc_18004C3E2
0x18004c5c2  mov     edi, 80070057h
0x18004c5c7  mov     r14d, 1
0x18004c5cd  mov     rcx, r12; lpCriticalSection
0x18004c5d0  call    cs:__imp_LeaveCriticalSection
0x18004c5d6  test    esi, esi
0x18004c5d8  jz      short loc_18004C642
0x18004c5da  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1> `wil::Feature<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1>::GetImpl(void)'::`2'::impl
0x18004c5e1  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1>::__private_IsEnabled(void)
0x18004c5e6  mov     rcx, cs:?g_pVars@@3PEAVCGlobalVariables@@EA; CGlobalVariables * g_pVars
0x18004c5ed  test    al, al
0x18004c5ef  jz      short loc_18004C63A
0x18004c5f1  test    rcx, rcx
0x18004c5f4  jnz     short loc_18004C63A
0x18004c5f6  mov     edi, 80004005h
0x18004c5fb  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c602  lea     rsi, WPP_GLOBAL_Control
0x18004c609  cmp     rcx, rsi
0x18004c60c  jz      short loc_18004C677
0x18004c60e  test    [rcx+1Ch], r14b
0x18004c612  jz      short loc_18004C654
0x18004c614  mov     rcx, [rcx+10h]
0x18004c618  lea     r9, aCregistrarsing_3; "CRegistrarSingleton::RegisterDevice: g_"...
0x18004c61f  mov     edx, 2Ah ; '*'
0x18004c624  mov     dword ptr [rsp+0F0h+var_D0], edi
0x18004c628  lea     r8, WPP_0f8e6464007c3e0bdd6d585d5cfe4b6e_Traceguids
0x18004c62f  call    WPP_SF_sd
0x18004c634  jmp     short loc_18004C649
0x18004c636  xor     esi, esi
0x18004c638  jmp     short loc_18004C5CD
0x18004c63a  mov     rcx, [rcx]; this
0x18004c63d  call    ?DecrementURLCount@BaseHttpListener@@QEAAJXZ; BaseHttpListener::DecrementURLCount(void)
0x18004c642  lea     rsi, WPP_GLOBAL_Control
0x18004c649  test    edi, edi
0x18004c64b  jz      short loc_18004C677
0x18004c64d  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c654  cmp     rcx, rsi
0x18004c657  jz      short loc_18004C677
0x18004c659  test    [rcx+1Ch], r14b
0x18004c65d  jz      short loc_18004C677
0x18004c65f  mov     rcx, [rcx+10h]
0x18004c663  lea     r8, WPP_0f8e6464007c3e0bdd6d585d5cfe4b6e_Traceguids
0x18004c66a  mov     edx, 2Bh ; '+'
0x18004c66f  mov     r9d, edi
0x18004c672  call    WPP_SF_d
0x18004c677  mov     rcx, rbx; lpCriticalSection
0x18004c67a  call    cs:__imp_LeaveCriticalSection
0x18004c680  mov     eax, edi
0x18004c682  mov     rcx, [rbp+3Fh+var_50]
0x18004c686  xor     rcx, rsp; StackCookie
0x18004c689  call    __security_check_cookie
0x18004c68e  add     rsp, 0B8h
0x18004c695  pop     r15
0x18004c697  pop     r14
0x18004c699  pop     r13
0x18004c69b  pop     r12
0x18004c69d  pop     rdi
0x18004c69e  pop     rsi
0x18004c69f  pop     rbx
0x18004c6a0  pop     rbp
0x18004c6a1  retn
```
