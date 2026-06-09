# CRegistrarSingleton::ReregisterDevice(ushort *,ushort *,ushort *,ushort *,ushort *,ushort *,long)

- ea: `0x18004ff50`
- end: `0x18005041b`
- name: `?ReregisterDevice@CRegistrarSingleton@@UEAAJPEAG00000J@Z`
- size: `1227`
- prototype: `__int64 __usercall@<rax>(CRegistrarSingleton *__hidden this@<rcx>, unsigned __int16 *@<rdx>, unsigned __int16 *@<r8>, unsigned __int16 *@<r9>, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, int)`
- caller_count: `0`
- callee_count: `20`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800071c0`
- `0x18001158c`
- `0x1800134e4`
- `0x1800200f4`
- `0x180030b0c`
- `0x180030cdc`
- `0x180030fd0`
- `0x1800326c8`
- `0x18003b0bc`
- `0x18003b1cc`
- `0x18003ba4c`
- `0x18003c018`
- `0x18003cb60`
- `0x180049b64`
- `0x18004e098`
- `0x18004ec90`
- `0x18004f368`
- `0x18004ff50`
- `0x180050bc0`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180050032`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180050048`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180050032`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180050048`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800500c9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800500d8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005033a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800503ec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800500c9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800500d8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005033a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800503ec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800500f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800502d5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800502ee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800500f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800502d5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800502ee`

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
      result = CServiceModule::CompleteInitialization((CServiceModule *)v11);
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
      v16 = CheckRegistryForLifeTime(&a8);
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
0x18004ff50  push    rbp
0x18004ff52  push    rbx
0x18004ff53  push    rsi
0x18004ff54  push    rdi
0x18004ff55  push    r12
0x18004ff57  push    r13
0x18004ff59  push    r14
0x18004ff5b  push    r15
0x18004ff5d  lea     rbp, [rsp-7]
0x18004ff62  sub     rsp, 0A8h
0x18004ff69  mov     rax, cs:__security_cookie
0x18004ff70  xor     rax, rsp
0x18004ff73  mov     [rbp+3Fh+var_48], rax
0x18004ff77  mov     rax, [rbp+3Fh+arg_20]
0x18004ff7b  mov     r14, r8
0x18004ff7e  mov     r13, [rbp+3Fh+pbstr]
0x18004ff82  mov     r12, rdx
0x18004ff85  mov     [rbp+3Fh+var_70], rax
0x18004ff89  mov     r15, rcx
0x18004ff8c  mov     rax, [rbp+3Fh+arg_28]
0x18004ff90  mov     [rbp+3Fh+var_78], rax
0x18004ff94  mov     [rbp+3Fh+var_68], r9
0x18004ff98  mov     [rbp+3Fh+var_90], r8
0x18004ff9c  mov     [rbp+3Fh+var_60], r8
0x18004ffa0  mov     [rbp+3Fh+var_80], r13
0x18004ffa4  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ffab  lea     rax, WPP_GLOBAL_Control
0x18004ffb2  cmp     rcx, rax
0x18004ffb5  jz      short loc_18004FFE0
0x18004ffb7  test    byte ptr [rcx+1Ch], 40h
0x18004ffbb  jz      short loc_18004FFE0
0x18004ffbd  mov     rcx, [rcx+10h]
0x18004ffc1  lea     r8, WPP_0f8e6464007c3e0bdd6d585d5cfe4b6e_Traceguids
0x18004ffc8  mov     edx, 40h ; '@'
0x18004ffcd  call    WPP_SF_
0x18004ffd2  mov     rcx, cs:WPP_GLOBAL_Control; this
0x18004ffd9  lea     rax, WPP_GLOBAL_Control
0x18004ffe0  xor     esi, esi
0x18004ffe2  cmp     cs:?m_fRegObjDeleted@CRegistrarSingleton@@1HA, esi; int CRegistrarSingleton::m_fRegObjDeleted
0x18004ffe8  jz      short loc_180050012
0x18004ffea  cmp     rcx, rax
0x18004ffed  jz      short loc_180050008
0x18004ffef  test    byte ptr [rcx+1Ch], 40h
0x18004fff3  jz      short loc_180050008
0x18004fff5  mov     rcx, [rcx+10h]
0x18004fff9  lea     edx, [rsi+41h]
0x18004fffc  lea     r8, WPP_0f8e6464007c3e0bdd6d585d5cfe4b6e_Traceguids
0x180050003  call    WPP_SF_
0x180050008  mov     eax, 80004005h
0x18005000d  jmp     loc_1800503FA
0x180050012  cmp     [r15+98h], esi
0x180050019  jnz     short loc_180050028
0x18005001b  call    ?CompleteInitialization@CServiceModule@@QEAAJXZ; CServiceModule::CompleteInitialization(void)
0x180050020  test    eax, eax
0x180050022  js      loc_1800503FA
0x180050028  lea     rdi, [r15+0C8h]
0x18005002f  mov     rcx, rdi; lpCriticalSection
0x180050032  call    cs:__imp_EnterCriticalSection
0x180050039  nop     dword ptr [rax+rax+00h]
0x18005003e  lea     rbx, [r15+0A0h]
0x180050045  mov     rcx, rbx; lpCriticalSection
0x180050048  call    cs:__imp_EnterCriticalSection
0x18005004f  nop     dword ptr [rax+rax+00h]
0x180050054  cmp     [r15+98h], esi
0x18005005b  jnz     short loc_180050065
0x18005005d  mov     r14d, 80004005h
0x180050063  jmp     short loc_1800500C6
0x180050065  mov     ecx, 3
0x18005006a  call    ?HrIsAllowedCOMCallLocality@@YAJW4CALL_LOCALITY@@@Z; HrIsAllowedCOMCallLocality(CALL_LOCALITY)
0x18005006f  mov     esi, eax
0x180050071  test    eax, eax
0x180050073  js      loc_180050145
0x180050079  mov     rcx, r13; pbstr
0x18005007c  call    ?HrValidateResourcePath@@YAJPEAG@Z; HrValidateResourcePath(ushort *)
0x180050081  mov     esi, eax
0x180050083  test    eax, eax
0x180050085  js      loc_180050145
0x18005008b  mov     rcx, [r15+78h]
0x18005008f  lea     r9, [rbp+3Fh+pv]
0x180050093  mov     [rbp+3Fh+pv], 0
0x18005009b  mov     r8, r13
0x18005009e  mov     rdx, r14
0x1800500a1  mov     rax, [rcx]
0x1800500a4  mov     rax, [rax+28h]
0x1800500a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800500ad  mov     rcx, [rbp+3Fh+pv]; unsigned __int16 *
0x1800500b1  mov     r14d, eax
0x1800500b4  mov     esi, eax
0x1800500b6  test    eax, eax
0x1800500b8  jns     short loc_1800500EC
0x1800500ba  lea     rdx, IID_IUPnPReregistrar; struct _GUID *
0x1800500c1  call    ?HrSetErrorInfo@@YAJPEBGAEBU_GUID@@@Z; HrSetErrorInfo(ushort const *,_GUID const &)
0x1800500c6  mov     rcx, rbx; lpCriticalSection
0x1800500c9  call    cs:__imp_LeaveCriticalSection
0x1800500d0  nop     dword ptr [rax+rax+00h]
0x1800500d5  mov     rcx, rdi; lpCriticalSection
0x1800500d8  call    cs:__imp_LeaveCriticalSection
0x1800500df  nop     dword ptr [rax+rax+00h]
0x1800500e4  mov     eax, r14d
0x1800500e7  jmp     loc_1800503FA
0x1800500ec  test    rcx, rcx
0x1800500ef  jz      short loc_180050105
0x1800500f1  call    cs:__imp_CoTaskMemFree
0x1800500f8  nop     dword ptr [rax+rax+00h]
0x1800500fd  mov     [rbp+3Fh+pv], 0
0x180050105  lea     rcx, [rbp+3Fh+arg_38]; int *
0x18005010c  call    ?CheckRegistryForLifeTime@@YAHPEAJ@Z; CheckRegistryForLifeTime(long *)
0x180050111  mov     r14d, [rbp+3Fh+arg_38]
0x180050118  test    eax, eax
0x18005011a  jz      short loc_180050138
0x18005011c  test    r14d, r14d
0x18005011f  jnz     short loc_180050129
0x180050121  mov     r14d, 708h
0x180050127  jmp     short loc_180050138
0x180050129  cmp     r14d, 384h
0x180050130  mov     eax, 80070057h
0x180050135  cmovl   esi, eax
0x180050138  test    r12, r12
0x18005013b  mov     eax, 80004003h
0x180050140  cmovz   esi, eax
0x180050143  jmp     short loc_18005014C
0x180050145  mov     r14d, [rbp+3Fh+arg_38]
0x18005014c  xor     r13d, r13d
0x18005014f  test    esi, esi
0x180050151  js      loc_180050337
0x180050157  call    ?HrSetAutoStart@@YAJXZ; HrSetAutoStart(void)
0x18005015c  mov     esi, eax
0x18005015e  test    eax, eax
0x180050160  js      loc_180050337
0x180050166  xorps   xmm0, xmm0
0x180050169  lea     rdx, [rbp+3Fh+var_58]; struct _GUID *
0x18005016d  mov     rcx, r12; unsigned __int16 *
0x180050170  movups  xmmword ptr [rbp+3Fh+var_58.Data1], xmm0
0x180050174  call    ?HrStringToPhysicalDeviceIdentifier@@YAJPEBGAEAU_GUID@@@Z; HrStringToPhysicalDeviceIdentifier(ushort const *,_GUID &)
0x180050179  mov     esi, eax
0x18005017b  test    eax, eax
0x18005017d  js      loc_180050329
0x180050183  lea     rdx, [rbp+3Fh+var_58]; struct _GUID *
0x180050187  lea     rcx, [r15+8]; this
0x18005018b  call    ?FHasDevice@CDeviceManager@@QEAAHAEBU_GUID@@@Z; CDeviceManager::FHasDevice(_GUID const &)
0x180050190  test    eax, eax
0x180050192  jz      short loc_18005019E
0x180050194  mov     esi, 8004A031h
0x180050199  jmp     loc_180050337
0x18005019e  mov     rcx, [r15+68h]
0x1800501a2  lea     r9, [rbp+3Fh+var_58]
0x1800501a6  mov     r8, [rbp+3Fh+var_80]
0x1800501aa  mov     edx, 1
0x1800501af  mov     [rsp+0E0h+var_B8], edx
0x1800501b3  mov     dword ptr [rsp+0E0h+var_C0], edx
0x1800501b7  mov     rax, [rcx]
0x1800501ba  mov     rdx, [rbp+3Fh+var_90]
0x1800501be  mov     rax, [rax+18h]
0x1800501c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800501c7  mov     esi, eax
0x1800501c9  test    eax, eax
0x1800501cb  js      loc_180050337
0x1800501d1  mov     rcx, [r15+68h]
0x1800501d5  lea     r9, [rbp+3Fh+var_90]
0x1800501d9  mov     [rbp+3Fh+var_90], r13
0x1800501dd  lea     r8, [rbp+3Fh+var_A0]
0x1800501e1  mov     [rbp+3Fh+var_A0], r13d
0x1800501e5  lea     rdx, [rbp+3Fh+var_58]
0x1800501e9  mov     rax, [rcx]
0x1800501ec  mov     rax, [rax+40h]
0x1800501f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800501f5  mov     esi, eax
0x1800501f7  test    eax, eax
0x1800501f9  js      loc_1800502FA
0x1800501ff  mov     rax, [rbp+3Fh+var_90]
0x180050203  test    rax, rax
0x180050206  jz      loc_1800502FA
0x18005020c  mov     r9, [rbp+3Fh+var_70]; unsigned __int16 *
0x180050210  lea     rdx, [rbp+3Fh+var_58]; struct _GUID *
0x180050214  mov     r8, [rbp+3Fh+var_68]; unsigned __int16 *
0x180050218  lea     rcx, [r15+8]; this
0x18005021c  mov     [rsp+0E0h+var_B0], rax; unsigned __int16 **
0x180050221  mov     eax, [rbp+3Fh+var_A0]
0x180050224  mov     [rsp+0E0h+var_B8], eax; int
0x180050228  mov     rax, [rbp+3Fh+var_78]
0x18005022c  mov     [rsp+0E0h+var_C0], rax; unsigned __int16 *
0x180050231  call    ?HrAddDevice@CDeviceManager@@QEAAJAEBU_GUID@@PEBG11JPEAPEAG@Z; CDeviceManager::HrAddDevice(_GUID const &,ushort const *,ushort const *,ushort const *,long,ushort * *)
0x180050236  mov     esi, eax
0x180050238  mov     [rbp+3Fh+var_88], eax
0x18005023b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AddUpnpTelemetry@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AddUpnpTelemetry@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AddUpnpTelemetry> `wil::Feature<__WilFeatureTraits_Feature_AddUpnpTelemetry>::GetImpl(void)'::`2'::impl
0x180050242  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AddUpnpTelemetry@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AddUpnpTelemetry>::__private_IsEnabled(void)
0x180050247  test    al, al
0x180050249  jz      short loc_18005026B
0x18005024b  lea     r9, [rbp+3Fh+var_88]
0x18005024f  mov     [rbp+3Fh+var_84], 1
0x180050256  lea     r8, [rbp+3Fh+var_84]
0x18005025a  mov     dword ptr [rbp+3Fh+pv], r13d
0x18005025e  lea     rdx, [rbp+3Fh+pv]
0x180050262  lea     rcx, [rbp+3Fh+var_60]
0x180050266  call    ??$RegisterDevice@AEAPEAGHHAEAJ@UpnpHostTelemetry@@SAXAEAPEAG$$QEAH1AEAJ@Z; UpnpHostTelemetry::RegisterDevice<ushort * &,int,int,long &>(ushort * &,int &&,int &&,long &)
0x18005026b  test    esi, esi
0x18005026d  js      short loc_1800502C1
0x18005026f  mov     rcx, [r15+70h]
0x180050273  mov     rdx, [rbp+3Fh+var_80]
0x180050277  mov     r9, [rbp+3Fh+var_70]
0x18005027b  mov     r8, [rbp+3Fh+var_68]
0x18005027f  mov     rax, [rcx]
0x180050282  mov     dword ptr [rsp+0E0h+var_B0], r14d
0x180050287  mov     qword ptr [rsp+0E0h+var_B8], rdx
0x18005028c  mov     rdx, [rbp+3Fh+var_78]
0x180050290  mov     rax, [rax+18h]
0x180050294  mov     [rsp+0E0h+var_C0], rdx
0x180050299  lea     rdx, [rbp+3Fh+var_58]
0x18005029d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800502a2  mov     esi, eax
0x1800502a4  test    eax, eax
0x1800502a6  js      short loc_1800502C1
0x1800502a8  mov     rcx, [r15+68h]
0x1800502ac  lea     rdx, [rbp+3Fh+var_58]
0x1800502b0  mov     r8d, r14d
0x1800502b3  mov     rax, [rcx]
0x1800502b6  mov     rax, [rax+20h]
0x1800502ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800502bf  mov     esi, eax
0x1800502c1  xor     r14d, r14d
0x1800502c4  cmp     [rbp+3Fh+var_A0], r13d
0x1800502c8  jle     short loc_1800502EA
0x1800502ca  mov     rcx, [rbp+3Fh+var_90]
0x1800502ce  movsxd  rdx, r14d
0x1800502d1  mov     rcx, [rcx+rdx*8]; pv
0x1800502d5  call    cs:__imp_CoTaskMemFree
0x1800502dc  nop     dword ptr [rax+rax+00h]
0x1800502e1  inc     r14d
0x1800502e4  cmp     r14d, [rbp+3Fh+var_A0]
0x1800502e8  jl      short loc_1800502CA
0x1800502ea  mov     rcx, [rbp+3Fh+var_90]; pv
0x1800502ee  call    cs:__imp_CoTaskMemFree
0x1800502f5  nop     dword ptr [rax+rax+00h]
0x1800502fa  mov     ecx, 80000000h
0x1800502ff  lea     eax, [rsi+rcx]
0x180050302  test    ecx, eax
0x180050304  jnz     short loc_180050337
0x180050306  cmp     esi, 8004A031h
0x18005030c  jz      short loc_180050337
0x18005030e  xor     r8d, r8d; int
0x180050311  lea     rdx, [rbp+3Fh+var_58]; struct _GUID *
0x180050315  mov     rcx, r15; this
0x180050318  call    ?HrUnregisterDeviceByPDI@CRegistrarSingleton@@AEAAJAEAU_GUID@@H@Z; CRegistrarSingleton::HrUnregisterDeviceByPDI(_GUID &,int)
0x18005031d  test    eax, eax
0x18005031f  js      short loc_180050337
0x180050321  mov     r13d, 1
0x180050327  jmp     short loc_180050337
0x180050329  cmp     esi, 800401F3h
0x18005032f  mov     eax, 80070057h
0x180050334  cmovz   esi, eax
0x180050337  mov     rcx, rbx; lpCriticalSection
0x18005033a  call    cs:__imp_LeaveCriticalSection
0x180050341  nop     dword ptr [rax+rax+00h]
0x180050346  test    r13d, r13d
0x180050349  jz      short loc_1800503B4
0x18005034b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1> `wil::Feature<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1>::GetImpl(void)'::`2'::impl
0x180050352  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1>::__private_IsEnabled(void)
0x180050357  mov     rcx, cs:?g_pVars@@3PEAVCGlobalVariables@@EA; CGlobalVariables * g_pVars
0x18005035e  test    al, al
0x180050360  jz      short loc_1800503AC
0x180050362  test    rcx, rcx
0x180050365  jnz     short loc_1800503AC
0x180050367  mov     r14d, 80004005h
0x18005036d  mov     esi, r14d
0x180050370  mov     rcx, cs:WPP_GLOBAL_Control
0x180050377  lea     rbx, WPP_GLOBAL_Control
0x18005037e  cmp     rcx, rbx
0x180050381  jz      short loc_1800503E9
0x180050383  test    byte ptr [rcx+1Ch], 1
0x180050387  jz      short loc_1800503C6
0x180050389  mov     rcx, [rcx+10h]
0x18005038d  lea     r9, aCregistrarsing; "CRegistrarSingleton::ReregisterDevice: "...
0x180050394  mov     edx, 42h ; 'B'
0x180050399  mov     dword ptr [rsp+0E0h+var_C0], r14d
0x18005039e  lea     r8, WPP_0f8e6464007c3e0bdd6d585d5cfe4b6e_Traceguids
0x1800503a5  call    WPP_SF_sd
0x1800503aa  jmp     short loc_1800503BB
0x1800503ac  mov     rcx, [rcx]; this
0x1800503af  call    ?DecrementURLCount@BaseHttpListener@@QEAAJXZ; BaseHttpListener::DecrementURLCount(void)
0x1800503b4  lea     rbx, WPP_GLOBAL_Control
0x1800503bb  test    esi, esi
0x1800503bd  jz      short loc_1800503E9
0x1800503bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800503c6  cmp     rcx, rbx
0x1800503c9  jz      short loc_1800503E9
0x1800503cb  test    byte ptr [rcx+1Ch], 1
0x1800503cf  jz      short loc_1800503E9
0x1800503d1  mov     rcx, [rcx+10h]
0x1800503d5  lea     r8, WPP_0f8e6464007c3e0bdd6d585d5cfe4b6e_Traceguids
0x1800503dc  mov     edx, 43h ; 'C'
0x1800503e1  mov     r9d, esi
0x1800503e4  call    WPP_SF_d
0x1800503e9  mov     rcx, rdi; lpCriticalSection
0x1800503ec  call    cs:__imp_LeaveCriticalSection
0x1800503f3  nop     dword ptr [rax+rax+00h]
0x1800503f8  mov     eax, esi
0x1800503fa  mov     rcx, [rbp+3Fh+var_48]
0x1800503fe  xor     rcx, rsp; StackCookie
0x180050401  call    __security_check_cookie
0x180050406  add     rsp, 0A8h
  ... truncated ...
```
