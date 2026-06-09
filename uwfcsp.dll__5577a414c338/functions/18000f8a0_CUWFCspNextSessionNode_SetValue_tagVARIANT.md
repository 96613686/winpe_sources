# CUWFCspNextSessionNode::SetValue(tagVARIANT)

- ea: `0x18000f8a0`
- end: `0x18000fdaa`
- name: `?SetValue@CUWFCspNextSessionNode@@UEAAJUtagVARIANT@@@Z`
- size: `1290`
- prototype: `__int64 __fastcall(CUWFCspNextSessionNode *this, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, installer_update`

## callees

- `0x180004368`
- `0x180007b90`
- `0x180007fc4`
- `0x18000b4dc`
- `0x18000b61c`
- `0x18000c1ec`
- `0x18000c5b4`
- `0x18000c8d8`
- `0x18000cbfc`
- `0x18000f8a0`
- `0x18001a210`
- `0x18001b010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18000f919`
- `OLEAUT32!__imp_VariantInit` at `0x18000f919`
- `OLEAUT32!__imp_VariantChangeType` at `0x18000f993`
- `OLEAUT32!__imp_VariantChangeType` at `0x18000f9c5`
- `OLEAUT32!__imp_VariantChangeType` at `0x18000f9f7`
- `OLEAUT32!__imp_VariantChangeType` at `0x18000fa24`
- `OLEAUT32!__imp_VariantChangeType` at `0x18000fa51`
- `OLEAUT32!__imp_VariantChangeType` at `0x18000fa7e`
- `OLEAUT32!__imp_VariantChangeType` at `0x18000fab0`
- `OLEAUT32!__imp_VariantChangeType` at `0x18000faf5`
- `OLEAUT32!__imp_VariantChangeType` at `0x18000fb75`
- `OLEAUT32!__imp_VariantChangeType` at `0x18000fbcb`
- `OLEAUT32!__imp_VariantChangeType` at `0x18000fc28`
- `OLEAUT32!__imp_VariantChangeType` at `0x18000fc7e`
- `OLEAUT32!__imp_VariantChangeType` at `0x18000fca4`
- `OLEAUT32!__imp_VariantChangeType` at `0x18000f993`
- `OLEAUT32!__imp_VariantChangeType` at `0x18000f9c5`
- `OLEAUT32!__imp_VariantChangeType` at `0x18000f9f7`
- `OLEAUT32!__imp_VariantChangeType` at `0x18000fa24`
- `OLEAUT32!__imp_VariantChangeType` at `0x18000fa51`
- `OLEAUT32!__imp_VariantChangeType` at `0x18000fa7e`
- `OLEAUT32!__imp_VariantChangeType` at `0x18000fab0`
- `OLEAUT32!__imp_VariantChangeType` at `0x18000faf5`
- `OLEAUT32!__imp_VariantChangeType` at `0x18000fb75`
- `OLEAUT32!__imp_VariantChangeType` at `0x18000fbcb`
- `OLEAUT32!__imp_VariantChangeType` at `0x18000fc28`
- `OLEAUT32!__imp_VariantChangeType` at `0x18000fc7e`
- `OLEAUT32!__imp_VariantChangeType` at `0x18000fca4`
- `uwfcfgmgmt!UwfCfgSetFilterEnabled` at `0x18000fac9`
- `uwfcfgmgmt!UwfCfgSetFilterEnabled` at `0x18000fac9`
- `uwfcfgmgmt!UwfCfgSetHormEnabled` at `0x18000fa97`
- `uwfcfgmgmt!UwfCfgSetHormEnabled` at `0x18000fa97`
- `uwfcfgmgmt!UwfCfgSetOverlayType` at `0x18000fa65`
- `uwfcfgmgmt!UwfCfgSetOverlayType` at `0x18000fa65`
- `uwfcfgmgmt!UwfCfgSetOverlayMaximumSize` at `0x18000fa0b`
- `uwfcfgmgmt!UwfCfgSetOverlayMaximumSize` at `0x18000fa0b`
- `uwfcfgmgmt!UwfCfgSetPersistDomainSecretKey` at `0x18000f9de`
- `uwfcfgmgmt!UwfCfgSetPersistDomainSecretKey` at `0x18000f9de`
- `uwfcfgmgmt!UwfCfgSetPersistTSCAL` at `0x18000f9ac`
- `uwfcfgmgmt!UwfCfgSetPersistTSCAL` at `0x18000f9ac`
- `uwfcfgmgmt!UwfCfgSetResetPersistentOverlay` at `0x18000fcb4`
- `uwfcfgmgmt!UwfCfgSetResetPersistentOverlay` at `0x18000fcb4`
- `uwfcfgmgmt!UwfCfgSetResetPersistentOverlaySavedMode` at `0x18000fc8e`
- `uwfcfgmgmt!UwfCfgSetResetPersistentOverlaySavedMode` at `0x18000fc8e`
- `uwfcfgmgmt!UwfCfgSetVolumeProtected` at `0x18000fc68`
- `uwfcfgmgmt!UwfCfgSetVolumeProtected` at `0x18000fc68`
- `uwfcfgmgmt!UwfCfgSetVolumeBindByDriveLetter` at `0x18000fc0f`
- `uwfcfgmgmt!UwfCfgSetVolumeBindByDriveLetter` at `0x18000fc0f`
- `uwfcfgmgmt!UwfCfgSetVolumeSwapfileSize` at `0x18000fbb2`
- `uwfcfgmgmt!UwfCfgSetVolumeSwapfileSize` at `0x18000fbb2`
- `uwfcfgmgmt!UwfCfgSetOverlayFlags` at `0x18000fa38`
- `uwfcfgmgmt!UwfCfgSetOverlayFlags` at `0x18000fa38`
- `ext-ms-win-uwf-servicing-apis-l1-1-0!SetServicingModeState` at `0x18000fb11`
- `ext-ms-win-uwf-servicing-apis-l1-1-0!SetServicingModeState` at `0x18000fb11`

## pseudocode

```c
__int64 __fastcall CUWFCspNextSessionNode::SetValue(CUWFCspNextSessionNode *this, struct tagVARIANT *a2)
{
  HRESULT v4; // ebx
  unsigned int v5; // eax
  unsigned int v6; // eax
  unsigned int v7; // eax
  unsigned int v8; // eax
  unsigned int v9; // eax
  unsigned int v10; // eax
  unsigned int v11; // eax
  unsigned int v12; // eax
  HRESULT v13; // eax
  unsigned int v14; // eax
  unsigned int v15; // eax
  unsigned int v16; // eax
  unsigned int v17; // eax
  unsigned int v18; // eax
  LONG lVal; // esi
  bool v20; // si
  bool v21; // si
  __int64 v22; // rcx
  __int64 v23; // rdx
  RTL_SRWLOCK *v24; // r8
  int *v25; // rsi
  int v26; // r8d
  LONG v27; // edx
  VARIANTARG pvarg; // [rsp+20h] [rbp-E0h] BYREF
  const unsigned __int16 *v30; // [rsp+38h] [rbp-C8h] BYREF
  int *v31; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v32[42]; // [rsp+50h] [rbp-B0h] BYREF

  wil::ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>((__int64)v32);
  v32[0] = &UwfTraceLoggingProvider<2>::ConfigurationActivity::`vftable';
  UwfTraceLoggingProvider<2>::ConfigurationActivity::StartActivity(v32, L"UWFCSPNextSessionNodeSet");
  v30 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  if ( !a2->vt )
  {
    v4 = -2147024809;
    goto LABEL_52;
  }
  v5 = *((_DWORD *)this + 11);
  if ( v5 <= 0x27 )
  {
    if ( v5 != 39 )
    {
      v6 = v5 - 30;
      if ( !v6 )
      {
        v4 = VariantChangeType(&pvarg, a2, 0, 0xBu);
        if ( v4 < 0 )
          goto LABEL_52;
        v13 = UwfCfgSetFilterEnabled(pvarg.iVal != 0);
        goto LABEL_51;
      }
      v7 = v6 - 1;
      if ( !v7 )
      {
        v4 = VariantChangeType(&pvarg, a2, 0, 0xBu);
        if ( v4 < 0 )
          goto LABEL_52;
        v13 = UwfCfgSetHormEnabled(pvarg.iVal != 0);
        goto LABEL_51;
      }
      v8 = v7 - 1;
      if ( !v8 )
      {
        v4 = VariantChangeType(&pvarg, a2, 0, 0x13u);
        if ( v4 < 0 )
          goto LABEL_52;
        v13 = UwfCfgSetOverlayType(pvarg.cyVal.Lo);
        goto LABEL_51;
      }
      v9 = v8 - 1;
      if ( !v9 )
      {
        v4 = VariantChangeType(&pvarg, a2, 0, 0x13u);
        if ( v4 < 0 )
          goto LABEL_52;
        v13 = UwfCfgSetOverlayFlags(pvarg.cyVal.Lo);
        goto LABEL_51;
      }
      v10 = v9 - 1;
      if ( !v10 )
      {
        v4 = VariantChangeType(&pvarg, a2, 0, 0x13u);
        if ( v4 < 0 )
          goto LABEL_52;
        v13 = UwfCfgSetOverlayMaximumSize(pvarg.cyVal.Lo);
        goto LABEL_51;
      }
      v11 = v10 - 1;
      if ( !v11 )
      {
        v4 = VariantChangeType(&pvarg, a2, 0, 0xBu);
        if ( v4 < 0 )
          goto LABEL_52;
        v13 = UwfCfgSetPersistDomainSecretKey(pvarg.iVal != 0);
        goto LABEL_51;
      }
      v12 = v11 - 1;
      if ( !v12 )
      {
        v4 = VariantChangeType(&pvarg, a2, 0, 0xBu);
        if ( v4 < 0 )
          goto LABEL_52;
        v13 = UwfCfgSetPersistTSCAL(pvarg.iVal != 0);
LABEL_51:
        v4 = v13;
        goto LABEL_52;
      }
      goto LABEL_36;
    }
    if ( (unsigned __int8)IsGetServicingModeStatePresent(19) )
    {
      v4 = VariantChangeType(&pvarg, a2, 0, 0xBu);
      if ( v4 < 0 )
        goto LABEL_52;
      v13 = SetServicingModeState(pvarg.iVal != 0);
      goto LABEL_51;
    }
LABEL_27:
    v4 = -2046820335;
    goto LABEL_52;
  }
  v14 = v5 - 40;
  if ( !v14 )
  {
    v4 = VariantChangeType(&pvarg, a2, 0, 0x13u);
    if ( v4 < 0 )
      goto LABEL_52;
    v13 = UwfCfgSetResetPersistentOverlay(pvarg.cyVal.Lo);
    goto LABEL_51;
  }
  v15 = v14 - 1;
  if ( !v15 )
  {
    v4 = VariantChangeType(&pvarg, a2, 0, 0x13u);
    if ( v4 < 0 )
      goto LABEL_52;
    v13 = UwfCfgSetResetPersistentOverlaySavedMode(pvarg.cyVal.Lo);
    goto LABEL_51;
  }
  v16 = v15 - 2;
  if ( !v16 )
    goto LABEL_27;
  v17 = v16 - 1;
  if ( v17 )
  {
    v18 = v17 - 1;
    if ( v18 )
    {
      v12 = v18 - 2;
      if ( v12 )
      {
LABEL_36:
        if ( v12 != 2 )
        {
          v4 = (*((_DWORD *)this + 13) & 2) != 0 ? -2147467263 : -2046820335;
          goto LABEL_52;
        }
        goto LABEL_27;
      }
      v4 = VariantChangeType(&pvarg, a2, 0, 0x13u);
      if ( v4 >= 0 )
      {
        lVal = pvarg.lVal;
        v4 = (*(__int64 (__fastcall **)(_QWORD, __int64, const unsigned __int16 **))(**((_QWORD **)this + 3) + 88LL))(
               *((_QWORD *)this + 3),
               3,
               &v30);
        if ( v4 >= 0 )
        {
          v13 = UwfCfgSetVolumeSwapfileSize(v30, lVal);
          goto LABEL_51;
        }
      }
    }
    else
    {
      v4 = VariantChangeType(&pvarg, a2, 0, 0xBu);
      if ( v4 >= 0 )
      {
        v20 = pvarg.iVal != 0;
        v4 = (*(__int64 (__fastcall **)(_QWORD, __int64, const unsigned __int16 **))(**((_QWORD **)this + 3) + 88LL))(
               *((_QWORD *)this + 3),
               3,
               &v30);
        if ( v4 >= 0 )
        {
          v13 = UwfCfgSetVolumeBindByDriveLetter(v30, v20);
          goto LABEL_51;
        }
      }
    }
  }
  else
  {
    v4 = VariantChangeType(&pvarg, a2, 0, 0xBu);
    if ( v4 >= 0 )
    {
      v21 = pvarg.iVal != 0;
      v4 = (*(__int64 (__fastcall **)(_QWORD, __int64, const unsigned __int16 **))(**((_QWORD **)this + 3) + 88LL))(
             *((_QWORD *)this + 3),
             3,
             &v30);
      if ( v4 >= 0 )
      {
        v13 = UwfCfgSetVolumeProtected(v30, v21);
        goto LABEL_51;
      }
    }
  }
LABEL_52:
  v22 = *((_QWORD *)this + 3);
  v23 = *((unsigned int *)this + 10);
  v31 = 0;
  if ( (*(int (__fastcall **)(__int64, __int64, int **))(*(_QWORD *)v22 + 88LL))(v22, v23, &v31) < 0 || (v25 = v31) == 0 )
  {
    v25 = &dword_18001F7A4;
    v31 = &dword_18001F7A4;
  }
  wil::ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
    (__int64)v32,
    v4,
    v24);
  if ( !a2 )
    UwfTraceLoggingProvider<2>::ConfigurationActivity::Stop<unsigned long,unsigned long,unsigned short const *>(
      (__int64)v32,
      -1,
      *((_DWORD *)this + 11),
      (__int64)v25);
  v26 = *((_DWORD *)this + 11);
  switch ( a2->vt )
  {
    case 3u:
      UwfTraceLoggingProvider<2>::ConfigurationActivity::Stop<long,unsigned long,unsigned short const *>(
        (__int64)v32,
        a2->lVal,
        v26,
        (__int64)v25);
      break;
    case 8u:
      UwfTraceLoggingProvider<2>::ConfigurationActivity::Stop<unsigned short *,unsigned long,unsigned short const *>(
        (__int64)v32,
        a2->plVal,
        v26,
        v25);
      break;
    case 0xBu:
      UwfTraceLoggingProvider<2>::ConfigurationActivity::Stop<short,unsigned long,unsigned short const *>(
        (__int64)v32,
        a2->iVal,
        v26,
        v25);
      break;
    default:
      v27 = -1;
      if ( a2->vt == 19 )
        v27 = a2->lVal;
      UwfTraceLoggingProvider<2>::ConfigurationActivity::Stop<unsigned long,unsigned long,unsigned short const *>(
        (__int64)v32,
        v27,
        v26,
        (__int64)v25);
      break;
  }
  UwfTraceLoggingProvider<2>::ConfigurationActivity::~ConfigurationActivity(v32);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000f8a0  mov     [rsp-8+arg_10], rbx
0x18000f8a5  push    rbp
0x18000f8a6  push    rsi
0x18000f8a7  push    rdi
0x18000f8a8  push    r12
0x18000f8aa  push    r13
0x18000f8ac  push    r14
0x18000f8ae  push    r15
0x18000f8b0  lea     rbp, [rsp-0B0h]
0x18000f8b8  sub     rsp, 1B0h
0x18000f8bf  mov     rax, cs:__security_cookie
0x18000f8c6  xor     rax, rsp
0x18000f8c9  mov     [rbp+0E0h+var_40], rax
0x18000f8d0  mov     r14, rcx
0x18000f8d3  mov     rdi, rdx
0x18000f8d6  lea     rcx, [rsp+1E0h+var_190]
0x18000f8db  call    ??0?$ActivityBase@V?$UwfTraceLoggingProvider@$01@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18000f8e0  lea     rax, ??_7ConfigurationActivity@?$UwfTraceLoggingProvider@$01@@6B@; const UwfTraceLoggingProvider<2>::ConfigurationActivity::`vftable'
0x18000f8e7  lea     rdx, aUwfcspnextsess_3; "UWFCSPNextSessionNodeSet"
0x18000f8ee  mov     [rsp+1E0h+var_190], rax
0x18000f8f3  lea     rcx, [rsp+1E0h+var_190]
0x18000f8f8  call    ?StartActivity@ConfigurationActivity@?$UwfTraceLoggingProvider@$01@@QEAAXPEBG@Z; UwfTraceLoggingProvider<2>::ConfigurationActivity::StartActivity(ushort const *)
0x18000f8fd  xorps   xmm0, xmm0
0x18000f900  lea     rcx, [rsp+1E0h+pvarg]; pvarg
0x18000f905  xor     eax, eax
0x18000f907  xor     r15d, r15d
0x18000f90a  mov     [rsp+1E0h+var_1A8], r15
0x18000f90f  movups  xmmword ptr [rsp+1E0h+pvarg], xmm0
0x18000f914  mov     qword ptr [rsp+1E0h+pvarg+10h], rax
0x18000f919  call    cs:__imp_VariantInit
0x18000f91f  lea     ecx, [r15+13h]
0x18000f923  lea     r13d, [r15+0Bh]
0x18000f927  lea     r12d, [r15+3]
0x18000f92b  cmp     r15w, [rdi]
0x18000f92f  jnz     short loc_18000F93B
0x18000f931  mov     ebx, 80070057h
0x18000f936  jmp     loc_18000FCBC
0x18000f93b  mov     eax, [r14+2Ch]
0x18000f93f  cmp     eax, 27h ; '''
0x18000f942  ja      loc_18000FB1C
0x18000f948  jz      loc_18000FAD4
0x18000f94e  sub     eax, 1Eh
0x18000f951  jz      loc_18000FAA2
0x18000f957  sub     eax, 1
0x18000f95a  jz      loc_18000FA70
0x18000f960  sub     eax, 1
0x18000f963  jz      loc_18000FA43
0x18000f969  sub     eax, 1
0x18000f96c  jz      loc_18000FA16
0x18000f972  sub     eax, 1
0x18000f975  jz      short loc_18000F9E9
0x18000f977  sub     eax, 1
0x18000f97a  jz      short loc_18000F9B7
0x18000f97c  sub     eax, 1
0x18000f97f  jnz     loc_18000FB46
0x18000f985  mov     r9d, r13d; vt
0x18000f988  lea     rcx, [rsp+1E0h+pvarg]; pvargDest
0x18000f98d  xor     r8d, r8d; wFlags
0x18000f990  mov     rdx, rdi; pvarSrc
0x18000f993  call    cs:__imp_VariantChangeType
0x18000f999  mov     ebx, eax
0x18000f99b  test    eax, eax
0x18000f99d  js      loc_18000FCBC
0x18000f9a3  cmp     word ptr [rsp+1E0h+pvarg+8], r15w
0x18000f9a9  setnz   cl
0x18000f9ac  call    cs:__imp_?UwfCfgSetPersistTSCAL@@YAJ_N@Z; UwfCfgSetPersistTSCAL(bool)
0x18000f9b2  jmp     loc_18000FCBA
0x18000f9b7  mov     r9d, r13d; vt
0x18000f9ba  lea     rcx, [rsp+1E0h+pvarg]; pvargDest
0x18000f9bf  xor     r8d, r8d; wFlags
0x18000f9c2  mov     rdx, rdi; pvarSrc
0x18000f9c5  call    cs:__imp_VariantChangeType
0x18000f9cb  mov     ebx, eax
0x18000f9cd  test    eax, eax
0x18000f9cf  js      loc_18000FCBC
0x18000f9d5  cmp     word ptr [rsp+1E0h+pvarg+8], r15w
0x18000f9db  setnz   cl
0x18000f9de  call    cs:__imp_?UwfCfgSetPersistDomainSecretKey@@YAJ_N@Z; UwfCfgSetPersistDomainSecretKey(bool)
0x18000f9e4  jmp     loc_18000FCBA
0x18000f9e9  mov     r9d, ecx; vt
0x18000f9ec  xor     r8d, r8d; wFlags
0x18000f9ef  lea     rcx, [rsp+1E0h+pvarg]; pvargDest
0x18000f9f4  mov     rdx, rdi; pvarSrc
0x18000f9f7  call    cs:__imp_VariantChangeType
0x18000f9fd  mov     ebx, eax
0x18000f9ff  test    eax, eax
0x18000fa01  js      loc_18000FCBC
0x18000fa07  mov     ecx, dword ptr [rsp+1E0h+pvarg+8]
0x18000fa0b  call    cs:__imp_?UwfCfgSetOverlayMaximumSize@@YAJK@Z; UwfCfgSetOverlayMaximumSize(ulong)
0x18000fa11  jmp     loc_18000FCBA
0x18000fa16  mov     r9d, ecx; vt
0x18000fa19  xor     r8d, r8d; wFlags
0x18000fa1c  lea     rcx, [rsp+1E0h+pvarg]; pvargDest
0x18000fa21  mov     rdx, rdi; pvarSrc
0x18000fa24  call    cs:__imp_VariantChangeType
0x18000fa2a  mov     ebx, eax
0x18000fa2c  test    eax, eax
0x18000fa2e  js      loc_18000FCBC
0x18000fa34  mov     ecx, dword ptr [rsp+1E0h+pvarg+8]
0x18000fa38  call    cs:__imp_?UwfCfgSetOverlayFlags@@YAJK@Z; UwfCfgSetOverlayFlags(ulong)
0x18000fa3e  jmp     loc_18000FCBA
0x18000fa43  mov     r9d, ecx; vt
0x18000fa46  xor     r8d, r8d; wFlags
0x18000fa49  lea     rcx, [rsp+1E0h+pvarg]; pvargDest
0x18000fa4e  mov     rdx, rdi; pvarSrc
0x18000fa51  call    cs:__imp_VariantChangeType
0x18000fa57  mov     ebx, eax
0x18000fa59  test    eax, eax
0x18000fa5b  js      loc_18000FCBC
0x18000fa61  mov     ecx, dword ptr [rsp+1E0h+pvarg+8]
0x18000fa65  call    cs:__imp_?UwfCfgSetOverlayType@@YAJW4_UWF_CONFIG_OVERLAY_TYPE@@@Z; UwfCfgSetOverlayType(_UWF_CONFIG_OVERLAY_TYPE)
0x18000fa6b  jmp     loc_18000FCBA
0x18000fa70  mov     r9d, r13d; vt
0x18000fa73  lea     rcx, [rsp+1E0h+pvarg]; pvargDest
0x18000fa78  xor     r8d, r8d; wFlags
0x18000fa7b  mov     rdx, rdi; pvarSrc
0x18000fa7e  call    cs:__imp_VariantChangeType
0x18000fa84  mov     ebx, eax
0x18000fa86  test    eax, eax
0x18000fa88  js      loc_18000FCBC
0x18000fa8e  cmp     word ptr [rsp+1E0h+pvarg+8], r15w
0x18000fa94  setnz   cl
0x18000fa97  call    cs:__imp_?UwfCfgSetHormEnabled@@YAJ_N@Z; UwfCfgSetHormEnabled(bool)
0x18000fa9d  jmp     loc_18000FCBA
0x18000faa2  mov     r9d, r13d; vt
0x18000faa5  lea     rcx, [rsp+1E0h+pvarg]; pvargDest
0x18000faaa  xor     r8d, r8d; wFlags
0x18000faad  mov     rdx, rdi; pvarSrc
0x18000fab0  call    cs:__imp_VariantChangeType
0x18000fab6  mov     ebx, eax
0x18000fab8  test    eax, eax
0x18000faba  js      loc_18000FCBC
0x18000fac0  cmp     word ptr [rsp+1E0h+pvarg+8], r15w
0x18000fac6  setnz   cl
0x18000fac9  call    cs:__imp_?UwfCfgSetFilterEnabled@@YAJ_N@Z; UwfCfgSetFilterEnabled(bool)
0x18000facf  jmp     loc_18000FCBA
0x18000fad4  call    IsGetServicingModeStatePresent
0x18000fad9  test    al, al
0x18000fadb  jnz     short loc_18000FAE7
0x18000fadd  mov     ebx, 86000011h
0x18000fae2  jmp     loc_18000FCBC
0x18000fae7  mov     r9d, r13d; vt
0x18000faea  lea     rcx, [rsp+1E0h+pvarg]; pvargDest
0x18000faef  xor     r8d, r8d; wFlags
0x18000faf2  mov     rdx, rdi; pvarSrc
0x18000faf5  call    cs:__imp_VariantChangeType
0x18000fafb  mov     ebx, eax
0x18000fafd  test    eax, eax
0x18000faff  js      loc_18000FCBC
0x18000fb05  cmp     word ptr [rsp+1E0h+pvarg+8], r15w
0x18000fb0b  mov     ecx, r15d
0x18000fb0e  setnz   cl
0x18000fb11  call    cs:__imp_SetServicingModeState
0x18000fb17  jmp     loc_18000FCBA
0x18000fb1c  sub     eax, 28h ; '('
0x18000fb1f  jz      loc_18000FC96
0x18000fb25  sub     eax, 1
0x18000fb28  jz      loc_18000FC70
0x18000fb2e  sub     eax, 2
0x18000fb31  jz      short loc_18000FADD
0x18000fb33  sub     eax, 1
0x18000fb36  jz      loc_18000FC1A
0x18000fb3c  sub     eax, 1
0x18000fb3f  jz      short loc_18000FBBD
0x18000fb41  sub     eax, 2
0x18000fb44  jz      short loc_18000FB67
0x18000fb46  cmp     eax, 2
0x18000fb49  jz      short loc_18000FADD
0x18000fb4b  mov     eax, [r14+34h]
0x18000fb4f  mov     ebx, 86000011h
0x18000fb54  and     al, 2
0x18000fb56  neg     al
0x18000fb58  sbb     ecx, ecx
0x18000fb5a  and     ecx, 0FA003FF0h
0x18000fb60  add     ebx, ecx
0x18000fb62  jmp     loc_18000FCBC
0x18000fb67  mov     r9d, ecx; vt
0x18000fb6a  xor     r8d, r8d; wFlags
0x18000fb6d  lea     rcx, [rsp+1E0h+pvarg]; pvargDest
0x18000fb72  mov     rdx, rdi; pvarSrc
0x18000fb75  call    cs:__imp_VariantChangeType
0x18000fb7b  mov     ebx, eax
0x18000fb7d  test    eax, eax
0x18000fb7f  js      loc_18000FCBC
0x18000fb85  mov     rcx, [r14+18h]
0x18000fb89  lea     r8, [rsp+1E0h+var_1A8]
0x18000fb8e  mov     esi, dword ptr [rsp+1E0h+pvarg+8]
0x18000fb92  mov     edx, r12d
0x18000fb95  mov     rax, [rcx]
0x18000fb98  mov     rax, [rax+58h]
0x18000fb9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fba1  mov     ebx, eax
0x18000fba3  test    eax, eax
0x18000fba5  js      loc_18000FCBC
0x18000fbab  mov     rcx, [rsp+1E0h+var_1A8]
0x18000fbb0  mov     edx, esi
0x18000fbb2  call    cs:__imp_?UwfCfgSetVolumeSwapfileSize@@YAJPEBGK@Z; UwfCfgSetVolumeSwapfileSize(ushort const *,ulong)
0x18000fbb8  jmp     loc_18000FCBA
0x18000fbbd  mov     r9d, r13d; vt
0x18000fbc0  lea     rcx, [rsp+1E0h+pvarg]; pvargDest
0x18000fbc5  xor     r8d, r8d; wFlags
0x18000fbc8  mov     rdx, rdi; pvarSrc
0x18000fbcb  call    cs:__imp_VariantChangeType
0x18000fbd1  mov     ebx, eax
0x18000fbd3  test    eax, eax
0x18000fbd5  js      loc_18000FCBC
0x18000fbdb  mov     rcx, [r14+18h]
0x18000fbdf  lea     r8, [rsp+1E0h+var_1A8]
0x18000fbe4  cmp     word ptr [rsp+1E0h+pvarg+8], r15w
0x18000fbea  mov     edx, r12d
0x18000fbed  setnz   sil
0x18000fbf1  mov     rax, [rcx]
0x18000fbf4  mov     rax, [rax+58h]
0x18000fbf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fbfd  mov     ebx, eax
0x18000fbff  test    eax, eax
0x18000fc01  js      loc_18000FCBC
0x18000fc07  mov     rcx, [rsp+1E0h+var_1A8]
0x18000fc0c  mov     dl, sil
0x18000fc0f  call    cs:__imp_?UwfCfgSetVolumeBindByDriveLetter@@YAJPEBG_N@Z; UwfCfgSetVolumeBindByDriveLetter(ushort const *,bool)
0x18000fc15  jmp     loc_18000FCBA
0x18000fc1a  mov     r9d, r13d; vt
0x18000fc1d  lea     rcx, [rsp+1E0h+pvarg]; pvargDest
0x18000fc22  xor     r8d, r8d; wFlags
0x18000fc25  mov     rdx, rdi; pvarSrc
0x18000fc28  call    cs:__imp_VariantChangeType
0x18000fc2e  mov     ebx, eax
0x18000fc30  test    eax, eax
0x18000fc32  js      loc_18000FCBC
0x18000fc38  mov     rcx, [r14+18h]
0x18000fc3c  lea     r8, [rsp+1E0h+var_1A8]
0x18000fc41  cmp     word ptr [rsp+1E0h+pvarg+8], r15w
0x18000fc47  mov     edx, r12d
0x18000fc4a  setnz   sil
0x18000fc4e  mov     rax, [rcx]
0x18000fc51  mov     rax, [rax+58h]
0x18000fc55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fc5a  mov     ebx, eax
0x18000fc5c  test    eax, eax
0x18000fc5e  js      short loc_18000FCBC
0x18000fc60  mov     rcx, [rsp+1E0h+var_1A8]
0x18000fc65  mov     dl, sil
0x18000fc68  call    cs:__imp_?UwfCfgSetVolumeProtected@@YAJPEBG_N@Z; UwfCfgSetVolumeProtected(ushort const *,bool)
0x18000fc6e  jmp     short loc_18000FCBA
0x18000fc70  mov     r9d, ecx; vt
0x18000fc73  xor     r8d, r8d; wFlags
0x18000fc76  lea     rcx, [rsp+1E0h+pvarg]; pvargDest
0x18000fc7b  mov     rdx, rdi; pvarSrc
0x18000fc7e  call    cs:__imp_VariantChangeType
0x18000fc84  mov     ebx, eax
0x18000fc86  test    eax, eax
0x18000fc88  js      short loc_18000FCBC
0x18000fc8a  mov     ecx, dword ptr [rsp+1E0h+pvarg+8]
0x18000fc8e  call    cs:__imp_?UwfCfgSetResetPersistentOverlaySavedMode@@YAJK@Z; UwfCfgSetResetPersistentOverlaySavedMode(ulong)
0x18000fc94  jmp     short loc_18000FCBA
0x18000fc96  mov     r9d, ecx; vt
0x18000fc99  xor     r8d, r8d; wFlags
0x18000fc9c  lea     rcx, [rsp+1E0h+pvarg]; pvargDest
0x18000fca1  mov     rdx, rdi; pvarSrc
0x18000fca4  call    cs:__imp_VariantChangeType
0x18000fcaa  mov     ebx, eax
0x18000fcac  test    eax, eax
0x18000fcae  js      short loc_18000FCBC
0x18000fcb0  mov     ecx, dword ptr [rsp+1E0h+pvarg+8]
0x18000fcb4  call    cs:__imp_?UwfCfgSetResetPersistentOverlay@@YAJK@Z; UwfCfgSetResetPersistentOverlay(ulong)
0x18000fcba  mov     ebx, eax
0x18000fcbc  mov     rcx, [r14+18h]
0x18000fcc0  lea     r8, [rsp+1E0h+var_1A0]
0x18000fcc5  mov     edx, [r14+28h]
0x18000fcc9  mov     [rsp+1E0h+var_1A0], r15
0x18000fcce  mov     rax, [rcx]
0x18000fcd1  mov     rax, [rax+58h]
0x18000fcd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fcda  test    eax, eax
0x18000fcdc  js      short loc_18000FCE8
0x18000fcde  mov     rsi, [rsp+1E0h+var_1A0]
0x18000fce3  test    rsi, rsi
0x18000fce6  jnz     short loc_18000FCF4
0x18000fce8  lea     rsi, dword_18001F7A4
0x18000fcef  mov     [rsp+1E0h+var_1A0], rsi
0x18000fcf4  mov     edx, ebx
0x18000fcf6  lea     rcx, [rsp+1E0h+var_190]
0x18000fcfb  call    ?SetStopResult@?$ActivityBase@V?$UwfTraceLoggingProvider@$01@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXJPEAJ@Z; wil::ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(long,long *)
0x18000fd00  or      r12d, 0FFFFFFFFh
0x18000fd04  test    rdi, rdi
0x18000fd07  jnz     short loc_18000FD1D
0x18000fd09  mov     r8d, [r14+2Ch]
0x18000fd0d  lea     rcx, [rsp+1E0h+var_190]
0x18000fd12  mov     r9, rsi
0x18000fd15  mov     edx, r12d
0x18000fd18  call    ??$Stop@KKPEBG@ConfigurationActivity@?$UwfTraceLoggingProvider@$01@@QEAAXKKPEBG@Z; UwfTraceLoggingProvider<2>::ConfigurationActivity::Stop<ulong,ulong,ushort const *>(ulong,ulong,ushort const *)
0x18000fd1d  mov     r8d, [r14+2Ch]
0x18000fd21  lea     rcx, [rsp+1E0h+var_190]
0x18000fd26  mov     eax, 3
0x18000fd2b  mov     r9, rsi
0x18000fd2e  cmp     [rdi], ax
0x18000fd31  jz      short loc_18000FD6C
0x18000fd33  cmp     word ptr [rdi], 8
0x18000fd37  jz      short loc_18000FD61
0x18000fd39  cmp     [rdi], r13w
  ... truncated ...
```
