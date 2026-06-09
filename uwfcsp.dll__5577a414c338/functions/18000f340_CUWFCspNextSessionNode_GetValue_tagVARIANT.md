# CUWFCspNextSessionNode::GetValue(tagVARIANT *)

- ea: `0x18000f340`
- end: `0x18000f868`
- name: `?GetValue@CUWFCspNextSessionNode@@UEAAJPEAUtagVARIANT@@@Z`
- size: `1320`
- prototype: `__int64 __fastcall(CUWFCspNextSessionNode *__hidden this, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `13`
- tags: `file_ops, registry_config, installer_update`

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
- `0x18000f340`
- `0x180019b20`
- `0x18001a210`
- `0x18001b010`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18000f827`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000f827`
- `OLEAUT32!__imp_SysAllocString` at `0x18000f479`
- `OLEAUT32!__imp_SysAllocString` at `0x18000f479`
- `OLEAUT32!__imp_VariantInit` at `0x18000f3d5`
- `OLEAUT32!__imp_VariantInit` at `0x18000f3d5`
- `uwfcfgmgmt!UwfCfgGetPersistTSCAL` at `0x18000f4a2`
- `uwfcfgmgmt!UwfCfgGetPersistTSCAL` at `0x18000f4a2`
- `uwfcfgmgmt!UwfCfgGetVolumeProtected` at `0x18000f722`
- `uwfcfgmgmt!UwfCfgGetVolumeProtected` at `0x18000f722`
- `uwfcfgmgmt!UwfCfgGetVolumeBindByDriveLetter` at `0x18000f6e9`
- `uwfcfgmgmt!UwfCfgGetVolumeBindByDriveLetter` at `0x18000f6e9`
- `uwfcfgmgmt!UwfCfgGetDriveLetter` at `0x18000f69d`
- `uwfcfgmgmt!UwfCfgGetDriveLetter` at `0x18000f69d`
- `uwfcfgmgmt!UwfCfgGetVolumeSwapfileSize` at `0x18000f665`
- `uwfcfgmgmt!UwfCfgGetVolumeSwapfileSize` at `0x18000f665`
- `uwfcfgmgmt!UwfCfgGetHormEnabled` at `0x18000f50d`
- `uwfcfgmgmt!UwfCfgGetHormEnabled` at `0x18000f50d`
- `uwfcfgmgmt!UwfCfgGetResetPersistentOverlay` at `0x18000f74b`
- `uwfcfgmgmt!UwfCfgGetResetPersistentOverlay` at `0x18000f74b`
- `uwfcfgmgmt!UwfCfgGetResetPersistentOverlaySavedMode` at `0x18000f739`
- `uwfcfgmgmt!UwfCfgGetResetPersistentOverlaySavedMode` at `0x18000f739`
- `uwfcfgmgmt!UwfCfgGetOverlayMaximumSize` at `0x18000f4ca`
- `uwfcfgmgmt!UwfCfgGetOverlayMaximumSize` at `0x18000f4ca`
- `uwfcfgmgmt!UwfCfgGetOverlayFlags` at `0x18000f4e1`
- `uwfcfgmgmt!UwfCfgGetOverlayFlags` at `0x18000f4e1`
- `uwfcfgmgmt!UwfCfgGetFilterEnabled` at `0x18000f521`
- `uwfcfgmgmt!UwfCfgGetFilterEnabled` at `0x18000f521`
- `uwfcfgmgmt!UwfCfgDoesFileExclusionExist` at `0x18000f619`
- `uwfcfgmgmt!UwfCfgDoesFileExclusionExist` at `0x18000f619`
- `uwfcfgmgmt!UwfCfgDoesRegExclusionExist` at `0x18000f45a`
- `uwfcfgmgmt!UwfCfgDoesRegExclusionExist` at `0x18000f45a`
- `uwfcfgmgmt!UwfCfgGetPersistDomainSecretKey` at `0x18000f4b6`
- `uwfcfgmgmt!UwfCfgGetPersistDomainSecretKey` at `0x18000f4b6`
- `uwfcfgmgmt!UwfCfgGetOverlayType` at `0x18000f4f8`
- `uwfcfgmgmt!UwfCfgGetOverlayType` at `0x18000f4f8`
- `ext-ms-win-uwf-servicing-apis-l1-1-0!GetServicingModeState` at `0x18000f565`
- `ext-ms-win-uwf-servicing-apis-l1-1-0!GetServicingModeState` at `0x18000f565`

## pseudocode

```c
__int64 __fastcall CUWFCspNextSessionNode::GetValue(CUWFCspNextSessionNode *this, struct tagVARIANT *a2)
{
  int DriveLetter; // ebx
  unsigned int v5; // eax
  unsigned int v6; // eax
  unsigned int v7; // eax
  unsigned int v8; // eax
  unsigned int v9; // eax
  unsigned int v10; // eax
  unsigned int v11; // eax
  unsigned int v12; // eax
  OLECHAR *v13; // rcx
  BSTR v14; // rax
  int VolumeBindByDriveLetter; // eax
  int ResetPersistentOverlay; // eax
  bool v17; // zf
  SHORT v18; // ax
  unsigned int v19; // eax
  unsigned int v20; // eax
  unsigned int v21; // eax
  unsigned int v22; // eax
  unsigned int v23; // eax
  unsigned int v24; // eax
  __int64 v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rcx
  __int64 v28; // rdx
  int *v29; // rsi
  int v30; // r8d
  LONG lVal; // edx
  bool v33[4]; // [rsp+20h] [rbp-E0h] BYREF
  LONG v34; // [rsp+24h] [rbp-DCh] BYREF
  const unsigned __int16 *v35; // [rsp+28h] [rbp-D8h] BYREF
  unsigned __int16 *v36; // [rsp+30h] [rbp-D0h] BYREF
  OLECHAR *psz; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 *v38; // [rsp+40h] [rbp-C0h] BYREF
  int *v39; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v40[42]; // [rsp+50h] [rbp-B0h] BYREF

  wil::ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>((__int64)v40);
  v40[0] = &UwfTraceLoggingProvider<2>::ConfigurationActivity::`vftable';
  UwfTraceLoggingProvider<2>::ConfigurationActivity::StartActivity(v40, L"UWFCSPNextSessionNodeGet");
  v35 = 0;
  psz = 0;
  v38 = 0;
  v36 = 0;
  if ( !a2 )
  {
    DriveLetter = -2147024809;
    goto LABEL_60;
  }
  VariantInit(a2);
  v5 = *((_DWORD *)this + 11);
  if ( v5 > 0x27 )
  {
    v19 = v5 - 40;
    if ( !v19 )
    {
      v34 = 0;
      ResetPersistentOverlay = UwfCfgGetResetPersistentOverlay((unsigned int *)&v34);
      goto LABEL_58;
    }
    v20 = v19 - 1;
    if ( !v20 )
    {
      v34 = 0;
      ResetPersistentOverlay = UwfCfgGetResetPersistentOverlaySavedMode(0, (unsigned int *)&v34);
      goto LABEL_58;
    }
    v21 = v20 - 3;
    if ( v21 )
    {
      v22 = v21 - 1;
      if ( v22 )
      {
        v23 = v22 - 1;
        if ( !v23 )
        {
          DriveLetter = (*(__int64 (__fastcall **)(_QWORD, __int64, const unsigned __int16 **))(**((_QWORD **)this + 3)
                                                                                              + 88LL))(
                          *((_QWORD *)this + 3),
                          3,
                          &v35);
          if ( DriveLetter < 0 )
            goto LABEL_60;
          DriveLetter = UwfCfgGetDriveLetter(0, v35, &v36);
          if ( DriveLetter < 0 )
            goto LABEL_60;
          v13 = v36;
          goto LABEL_17;
        }
        v24 = v23 - 1;
        if ( v24 )
        {
          if ( v24 == 2 )
          {
            DriveLetter = (*(__int64 (__fastcall **)(_QWORD, __int64, const unsigned __int16 **))(**((_QWORD **)this + 3)
                                                                                                + 88LL))(
                            *((_QWORD *)this + 3),
                            3,
                            &v35);
            if ( DriveLetter < 0 )
              goto LABEL_60;
            DriveLetter = (*(__int64 (__fastcall **)(_QWORD, __int64, unsigned __int16 **))(**((_QWORD **)this + 3)
                                                                                          + 88LL))(
                            *((_QWORD *)this + 3),
                            5,
                            &v38);
            if ( DriveLetter < 0 )
              goto LABEL_60;
            DriveLetter = UwfCfgDoesFileExclusionExist(0, v35, v38);
            if ( DriveLetter < 0 )
              goto LABEL_15;
            v13 = v38;
            goto LABEL_17;
          }
LABEL_42:
          DriveLetter = CCSPNodeImpl::GetValue(this, a2);
          goto LABEL_60;
        }
        DriveLetter = (*(__int64 (__fastcall **)(_QWORD, __int64, const unsigned __int16 **))(**((_QWORD **)this + 3)
                                                                                            + 88LL))(
                        *((_QWORD *)this + 3),
                        3,
                        &v35);
        if ( DriveLetter < 0 )
          goto LABEL_60;
        v34 = 0;
        ResetPersistentOverlay = UwfCfgGetVolumeSwapfileSize(0, v35, (unsigned int *)&v34);
        goto LABEL_58;
      }
      v25 = *((_QWORD *)this + 3);
      v33[0] = 0;
      DriveLetter = (*(__int64 (__fastcall **)(__int64, __int64, const unsigned __int16 **))(*(_QWORD *)v25 + 88LL))(
                      v25,
                      3,
                      &v35);
      if ( DriveLetter < 0 )
        goto LABEL_60;
      VolumeBindByDriveLetter = UwfCfgGetVolumeBindByDriveLetter(0, v35, v33);
    }
    else
    {
      v26 = *((_QWORD *)this + 3);
      v33[0] = 0;
      DriveLetter = (*(__int64 (__fastcall **)(__int64, __int64, const unsigned __int16 **))(*(_QWORD *)v26 + 88LL))(
                      v26,
                      3,
                      &v35);
      if ( DriveLetter < 0 )
        goto LABEL_60;
      VolumeBindByDriveLetter = UwfCfgGetVolumeProtected(0, v35, v33);
    }
LABEL_26:
    DriveLetter = VolumeBindByDriveLetter;
    if ( VolumeBindByDriveLetter < 0 )
      goto LABEL_60;
    v17 = !v33[0];
LABEL_28:
    a2->vt = 11;
    if ( v17 )
      v18 = 0;
    else
      v18 = -1;
    a2->iVal = v18;
    goto LABEL_60;
  }
  if ( v5 == 39 )
  {
    DriveLetter = 0;
    v34 = 0;
    if ( (unsigned __int8)IsGetServicingModeStatePresent() )
    {
      DriveLetter = GetServicingModeState(0, &v34);
      if ( DriveLetter < 0 )
        goto LABEL_60;
    }
    v17 = v34 == 0;
    goto LABEL_28;
  }
  v6 = v5 - 30;
  if ( !v6 )
  {
    v33[0] = 0;
    VolumeBindByDriveLetter = UwfCfgGetFilterEnabled(0, v33);
    goto LABEL_26;
  }
  v7 = v6 - 1;
  if ( !v7 )
  {
    v33[0] = 0;
    VolumeBindByDriveLetter = UwfCfgGetHormEnabled(v33);
    goto LABEL_26;
  }
  v8 = v7 - 1;
  if ( v8 )
  {
    v9 = v8 - 1;
    if ( v9 )
    {
      v10 = v9 - 1;
      if ( v10 )
      {
        v11 = v10 - 1;
        if ( v11 )
        {
          v12 = v11 - 1;
          if ( v12 )
          {
            if ( v12 == 2 )
            {
              DriveLetter = (*(__int64 (__fastcall **)(_QWORD, __int64, OLECHAR **))(**((_QWORD **)this + 3) + 88LL))(
                              *((_QWORD *)this + 3),
                              3,
                              &psz);
              if ( DriveLetter < 0 )
                goto LABEL_60;
              DriveLetter = UwfCfgDoesRegExclusionExist(0, psz);
              if ( DriveLetter < 0 )
              {
LABEL_15:
                DriveLetter = -2046820350;
                goto LABEL_60;
              }
              v13 = psz;
LABEL_17:
              a2->vt = 8;
              v14 = SysAllocString(v13);
              a2->llVal = (LONGLONG)v14;
              if ( !v14 )
                DriveLetter = -2147024882;
              goto LABEL_60;
            }
            goto LABEL_42;
          }
          v33[0] = 0;
          VolumeBindByDriveLetter = UwfCfgGetPersistTSCAL(1, v33);
        }
        else
        {
          v33[0] = 0;
          VolumeBindByDriveLetter = UwfCfgGetPersistDomainSecretKey(1, v33);
        }
        goto LABEL_26;
      }
      v34 = 0;
      ResetPersistentOverlay = UwfCfgGetOverlayMaximumSize(0, (unsigned int *)&v34);
    }
    else
    {
      v34 = 0;
      ResetPersistentOverlay = UwfCfgGetOverlayFlags(0, (unsigned int *)&v34);
    }
  }
  else
  {
    v34 = 0;
    ResetPersistentOverlay = UwfCfgGetOverlayType(0, (enum _UWF_CONFIG_OVERLAY_TYPE *)&v34);
  }
LABEL_58:
  DriveLetter = ResetPersistentOverlay;
  if ( ResetPersistentOverlay >= 0 )
  {
    a2->lVal = v34;
    a2->vt = 19;
  }
LABEL_60:
  v27 = *((_QWORD *)this + 3);
  v28 = *((unsigned int *)this + 10);
  v39 = 0;
  if ( (*(int (__fastcall **)(__int64, __int64, int **))(*(_QWORD *)v27 + 88LL))(v27, v28, &v39) < 0 || (v29 = v39) == 0 )
  {
    v29 = &dword_18001F7A4;
    v39 = &dword_18001F7A4;
  }
  wil::ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
    v40,
    (unsigned int)DriveLetter);
  if ( !a2 )
    UwfTraceLoggingProvider<2>::ConfigurationActivity::Stop<unsigned long,unsigned long,unsigned short const *>(
      (__int64)v40,
      -1,
      *((_DWORD *)this + 11),
      (__int64)v29);
  v30 = *((_DWORD *)this + 11);
  switch ( a2->vt )
  {
    case 3u:
      UwfTraceLoggingProvider<2>::ConfigurationActivity::Stop<long,unsigned long,unsigned short const *>(
        (__int64)v40,
        a2->lVal,
        v30,
        (__int64)v29);
      break;
    case 8u:
      UwfTraceLoggingProvider<2>::ConfigurationActivity::Stop<unsigned short *,unsigned long,unsigned short const *>(
        (__int64)v40,
        a2->plVal,
        v30,
        v29);
      break;
    case 0xBu:
      UwfTraceLoggingProvider<2>::ConfigurationActivity::Stop<short,unsigned long,unsigned short const *>(
        (__int64)v40,
        a2->iVal,
        v30,
        v29);
      break;
    default:
      lVal = -1;
      if ( a2->vt == 19 )
        lVal = a2->lVal;
      UwfTraceLoggingProvider<2>::ConfigurationActivity::Stop<unsigned long,unsigned long,unsigned short const *>(
        (__int64)v40,
        lVal,
        v30,
        (__int64)v29);
      break;
  }
  if ( v36 )
  {
    operator delete[](v36);
    v36 = 0;
  }
  UwfTraceLoggingProvider<2>::ConfigurationActivity::~ConfigurationActivity(v40);
  return (unsigned int)DriveLetter;
}

```

## disassembly

```asm
0x18000f340  mov     [rsp-8+arg_10], rbx
0x18000f345  push    rbp
0x18000f346  push    rsi
0x18000f347  push    rdi
0x18000f348  push    r12
0x18000f34a  push    r13
0x18000f34c  push    r14
0x18000f34e  push    r15
0x18000f350  lea     rbp, [rsp-0B0h]
0x18000f358  sub     rsp, 1B0h
0x18000f35f  mov     rax, cs:__security_cookie
0x18000f366  xor     rax, rsp
0x18000f369  mov     [rbp+0E0h+var_40], rax
0x18000f370  mov     r14, rcx
0x18000f373  mov     rdi, rdx
0x18000f376  lea     rcx, [rsp+1E0h+var_190]
0x18000f37b  call    ??0?$ActivityBase@V?$UwfTraceLoggingProvider@$01@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18000f380  lea     rax, ??_7ConfigurationActivity@?$UwfTraceLoggingProvider@$01@@6B@; const UwfTraceLoggingProvider<2>::ConfigurationActivity::`vftable'
0x18000f387  lea     rdx, aUwfcspnextsess_1; "UWFCSPNextSessionNodeGet"
0x18000f38e  mov     [rsp+1E0h+var_190], rax
0x18000f393  lea     rcx, [rsp+1E0h+var_190]
0x18000f398  call    ?StartActivity@ConfigurationActivity@?$UwfTraceLoggingProvider@$01@@QEAAXPEBG@Z; UwfTraceLoggingProvider<2>::ConfigurationActivity::StartActivity(ushort const *)
0x18000f39d  xor     r15d, r15d
0x18000f3a0  mov     [rsp+1E0h+var_1B8], r15
0x18000f3a5  mov     [rsp+1E0h+psz], r15
0x18000f3aa  mov     [rsp+1E0h+var_1A0], r15
0x18000f3af  mov     [rsp+1E0h+var_1B0], r15
0x18000f3b4  lea     ebx, [r15+3]
0x18000f3b8  lea     esi, [rbx+10h]
0x18000f3bb  lea     r12d, [r15+8]
0x18000f3bf  lea     r13d, [r15+0Bh]
0x18000f3c3  test    rdi, rdi
0x18000f3c6  jnz     short loc_18000F3D2
0x18000f3c8  mov     ebx, 80070057h
0x18000f3cd  jmp     loc_18000F761
0x18000f3d2  mov     rcx, rdi; pvarg
0x18000f3d5  call    cs:__imp_VariantInit
0x18000f3db  mov     eax, [r14+2Ch]
0x18000f3df  cmp     eax, 27h ; '''
0x18000f3e2  ja      loc_18000F57C
0x18000f3e8  jz      loc_18000F54D
0x18000f3ee  sub     eax, 1Eh
0x18000f3f1  jz      loc_18000F515
0x18000f3f7  sub     eax, 1
0x18000f3fa  jz      loc_18000F503
0x18000f400  sub     eax, 1
0x18000f403  jz      loc_18000F4EC
0x18000f409  sub     eax, 1
0x18000f40c  jz      loc_18000F4D5
0x18000f412  sub     eax, 1
0x18000f415  jz      loc_18000F4BE
0x18000f41b  sub     eax, 1
0x18000f41e  jz      loc_18000F4AA
0x18000f424  sub     eax, 1
0x18000f427  jz      short loc_18000F496
0x18000f429  cmp     eax, 2
0x18000f42c  jnz     loc_18000F5B6
0x18000f432  mov     rcx, [r14+18h]
0x18000f436  lea     r8, [rsp+1E0h+psz]
0x18000f43b  mov     edx, ebx
0x18000f43d  mov     rax, [rcx]
0x18000f440  mov     rax, [rax+58h]
0x18000f444  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f449  mov     ebx, eax
0x18000f44b  test    eax, eax
0x18000f44d  js      loc_18000F761
0x18000f453  mov     rdx, [rsp+1E0h+psz]
0x18000f458  xor     ecx, ecx
0x18000f45a  call    cs:__imp_?UwfCfgDoesRegExclusionExist@@YAJ_NPEBG@Z; UwfCfgDoesRegExclusionExist(bool,ushort const *)
0x18000f460  mov     ebx, eax
0x18000f462  test    eax, eax
0x18000f464  jns     short loc_18000F470
0x18000f466  mov     ebx, 86000002h
0x18000f46b  jmp     loc_18000F761
0x18000f470  mov     rcx, [rsp+1E0h+psz]; psz
0x18000f475  mov     [rdi], r12w
0x18000f479  call    cs:__imp_SysAllocString
0x18000f47f  mov     [rdi+8], rax
0x18000f483  test    rax, rax
0x18000f486  jnz     loc_18000F761
0x18000f48c  mov     ebx, 8007000Eh
0x18000f491  jmp     loc_18000F761
0x18000f496  lea     rdx, [rsp+1E0h+var_1C0]
0x18000f49b  mov     [rsp+1E0h+var_1C0], r15b
0x18000f4a0  mov     cl, 1
0x18000f4a2  call    cs:__imp_?UwfCfgGetPersistTSCAL@@YAJ_NPEA_N@Z; UwfCfgGetPersistTSCAL(bool,bool *)
0x18000f4a8  jmp     short loc_18000F527
0x18000f4aa  lea     rdx, [rsp+1E0h+var_1C0]
0x18000f4af  mov     [rsp+1E0h+var_1C0], r15b
0x18000f4b4  mov     cl, 1
0x18000f4b6  call    cs:__imp_?UwfCfgGetPersistDomainSecretKey@@YAJ_NPEA_N@Z; UwfCfgGetPersistDomainSecretKey(bool,bool *)
0x18000f4bc  jmp     short loc_18000F527
0x18000f4be  lea     rdx, [rsp+1E0h+var_1BC]
0x18000f4c3  mov     [rsp+1E0h+var_1BC], r15d
0x18000f4c8  xor     ecx, ecx
0x18000f4ca  call    cs:__imp_?UwfCfgGetOverlayMaximumSize@@YAJ_NPEAK@Z; UwfCfgGetOverlayMaximumSize(bool,ulong *)
0x18000f4d0  jmp     loc_18000F751
0x18000f4d5  lea     rdx, [rsp+1E0h+var_1BC]
0x18000f4da  mov     [rsp+1E0h+var_1BC], r15d
0x18000f4df  xor     ecx, ecx
0x18000f4e1  call    cs:__imp_?UwfCfgGetOverlayFlags@@YAJ_NPEAK@Z; UwfCfgGetOverlayFlags(bool,ulong *)
0x18000f4e7  jmp     loc_18000F751
0x18000f4ec  lea     rdx, [rsp+1E0h+var_1BC]
0x18000f4f1  mov     [rsp+1E0h+var_1BC], r15d
0x18000f4f6  xor     ecx, ecx
0x18000f4f8  call    cs:__imp_?UwfCfgGetOverlayType@@YAJ_NPEAW4_UWF_CONFIG_OVERLAY_TYPE@@@Z; UwfCfgGetOverlayType(bool,_UWF_CONFIG_OVERLAY_TYPE *)
0x18000f4fe  jmp     loc_18000F751
0x18000f503  lea     rcx, [rsp+1E0h+var_1C0]
0x18000f508  mov     [rsp+1E0h+var_1C0], r15b
0x18000f50d  call    cs:__imp_?UwfCfgGetHormEnabled@@YAJPEA_N@Z; UwfCfgGetHormEnabled(bool *)
0x18000f513  jmp     short loc_18000F527
0x18000f515  lea     rdx, [rsp+1E0h+var_1C0]
0x18000f51a  mov     [rsp+1E0h+var_1C0], r15b
0x18000f51f  xor     ecx, ecx
0x18000f521  call    cs:__imp_?UwfCfgGetFilterEnabled@@YAJ_NPEA_N@Z; UwfCfgGetFilterEnabled(bool,bool *)
0x18000f527  mov     ebx, eax
0x18000f529  test    eax, eax
0x18000f52b  js      loc_18000F761
0x18000f531  cmp     [rsp+1E0h+var_1C0], r15b
0x18000f536  mov     [rdi], r13w
0x18000f53a  jz      short loc_18000F541
0x18000f53c  or      eax, 0FFFFFFFFh
0x18000f53f  jmp     short loc_18000F544
0x18000f541  mov     eax, r15d
0x18000f544  mov     [rdi+8], ax
0x18000f548  jmp     loc_18000F761
0x18000f54d  mov     ebx, r15d
0x18000f550  mov     [rsp+1E0h+var_1BC], r15d
0x18000f555  call    IsGetServicingModeStatePresent
0x18000f55a  test    al, al
0x18000f55c  jz      short loc_18000F575
0x18000f55e  lea     rdx, [rsp+1E0h+var_1BC]
0x18000f563  xor     ecx, ecx
0x18000f565  call    cs:__imp_GetServicingModeState
0x18000f56b  mov     ebx, eax
0x18000f56d  test    eax, eax
0x18000f56f  js      loc_18000F761
0x18000f575  cmp     [rsp+1E0h+var_1BC], r15d
0x18000f57a  jmp     short loc_18000F536
0x18000f57c  sub     eax, 28h ; '('
0x18000f57f  jz      loc_18000F741
0x18000f585  sub     eax, 1
0x18000f588  jz      loc_18000F72D
0x18000f58e  sub     eax, ebx
0x18000f590  jz      loc_18000F6F4
0x18000f596  sub     eax, 1
0x18000f599  jz      loc_18000F6B7
0x18000f59f  sub     eax, 1
0x18000f5a2  jz      loc_18000F670
0x18000f5a8  sub     eax, 1
0x18000f5ab  jz      loc_18000F633
0x18000f5b1  cmp     eax, 2
0x18000f5b4  jz      short loc_18000F5C8
0x18000f5b6  mov     rdx, rdi; struct tagVARIANT *
0x18000f5b9  mov     rcx, r14; this
0x18000f5bc  call    ?GetValue@CCSPNodeImpl@@UEAAJPEAUtagVARIANT@@@Z; CCSPNodeImpl::GetValue(tagVARIANT *)
0x18000f5c1  mov     ebx, eax
0x18000f5c3  jmp     loc_18000F761
0x18000f5c8  mov     rcx, [r14+18h]
0x18000f5cc  lea     r8, [rsp+1E0h+var_1B8]
0x18000f5d1  mov     edx, ebx
0x18000f5d3  mov     rax, [rcx]
0x18000f5d6  mov     rax, [rax+58h]
0x18000f5da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f5df  mov     ebx, eax
0x18000f5e1  test    eax, eax
0x18000f5e3  js      loc_18000F761
0x18000f5e9  mov     rcx, [r14+18h]
0x18000f5ed  lea     r8, [rsp+1E0h+var_1A0]
0x18000f5f2  mov     edx, 5
0x18000f5f7  mov     rax, [rcx]
0x18000f5fa  mov     rax, [rax+58h]
0x18000f5fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f603  mov     ebx, eax
0x18000f605  test    eax, eax
0x18000f607  js      loc_18000F761
0x18000f60d  mov     r8, [rsp+1E0h+var_1A0]
0x18000f612  xor     ecx, ecx
0x18000f614  mov     rdx, [rsp+1E0h+var_1B8]
0x18000f619  call    cs:__imp_?UwfCfgDoesFileExclusionExist@@YAJ_NPEBG1@Z; UwfCfgDoesFileExclusionExist(bool,ushort const *,ushort const *)
0x18000f61f  mov     ebx, eax
0x18000f621  test    eax, eax
0x18000f623  js      loc_18000F466
0x18000f629  mov     rcx, [rsp+1E0h+var_1A0]
0x18000f62e  jmp     loc_18000F475
0x18000f633  mov     rcx, [r14+18h]
0x18000f637  lea     r8, [rsp+1E0h+var_1B8]
0x18000f63c  mov     edx, ebx
0x18000f63e  mov     rax, [rcx]
0x18000f641  mov     rax, [rax+58h]
0x18000f645  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f64a  mov     ebx, eax
0x18000f64c  test    eax, eax
0x18000f64e  js      loc_18000F761
0x18000f654  mov     rdx, [rsp+1E0h+var_1B8]
0x18000f659  lea     r8, [rsp+1E0h+var_1BC]
0x18000f65e  xor     ecx, ecx
0x18000f660  mov     [rsp+1E0h+var_1BC], r15d
0x18000f665  call    cs:__imp_?UwfCfgGetVolumeSwapfileSize@@YAJ_NPEBGPEAK@Z; UwfCfgGetVolumeSwapfileSize(bool,ushort const *,ulong *)
0x18000f66b  jmp     loc_18000F751
0x18000f670  mov     rcx, [r14+18h]
0x18000f674  lea     r8, [rsp+1E0h+var_1B8]
0x18000f679  mov     edx, ebx
0x18000f67b  mov     rax, [rcx]
0x18000f67e  mov     rax, [rax+58h]
0x18000f682  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f687  mov     ebx, eax
0x18000f689  test    eax, eax
0x18000f68b  js      loc_18000F761
0x18000f691  mov     rdx, [rsp+1E0h+var_1B8]
0x18000f696  lea     r8, [rsp+1E0h+var_1B0]
0x18000f69b  xor     ecx, ecx
0x18000f69d  call    cs:__imp_?UwfCfgGetDriveLetter@@YAJ_NPEBGPEAPEAG@Z; UwfCfgGetDriveLetter(bool,ushort const *,ushort * *)
0x18000f6a3  mov     ebx, eax
0x18000f6a5  test    eax, eax
0x18000f6a7  js      loc_18000F761
0x18000f6ad  mov     rcx, [rsp+1E0h+var_1B0]
0x18000f6b2  jmp     loc_18000F475
0x18000f6b7  mov     rcx, [r14+18h]
0x18000f6bb  lea     r8, [rsp+1E0h+var_1B8]
0x18000f6c0  mov     [rsp+1E0h+var_1C0], r15b
0x18000f6c5  mov     edx, ebx
0x18000f6c7  mov     rax, [rcx]
0x18000f6ca  mov     rax, [rax+58h]
0x18000f6ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f6d3  mov     ebx, eax
0x18000f6d5  test    eax, eax
0x18000f6d7  js      loc_18000F761
0x18000f6dd  mov     rdx, [rsp+1E0h+var_1B8]
0x18000f6e2  lea     r8, [rsp+1E0h+var_1C0]
0x18000f6e7  xor     ecx, ecx
0x18000f6e9  call    cs:__imp_?UwfCfgGetVolumeBindByDriveLetter@@YAJ_NPEBGPEA_N@Z; UwfCfgGetVolumeBindByDriveLetter(bool,ushort const *,bool *)
0x18000f6ef  jmp     loc_18000F527
0x18000f6f4  mov     rcx, [r14+18h]
0x18000f6f8  lea     r8, [rsp+1E0h+var_1B8]
0x18000f6fd  mov     [rsp+1E0h+var_1C0], r15b
0x18000f702  mov     edx, ebx
0x18000f704  mov     rax, [rcx]
0x18000f707  mov     rax, [rax+58h]
0x18000f70b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f710  mov     ebx, eax
0x18000f712  test    eax, eax
0x18000f714  js      short loc_18000F761
0x18000f716  mov     rdx, [rsp+1E0h+var_1B8]
0x18000f71b  lea     r8, [rsp+1E0h+var_1C0]
0x18000f720  xor     ecx, ecx
0x18000f722  call    cs:__imp_?UwfCfgGetVolumeProtected@@YAJ_NPEBGPEA_N@Z; UwfCfgGetVolumeProtected(bool,ushort const *,bool *)
0x18000f728  jmp     loc_18000F527
0x18000f72d  lea     rdx, [rsp+1E0h+var_1BC]
0x18000f732  mov     [rsp+1E0h+var_1BC], r15d
0x18000f737  xor     ecx, ecx
0x18000f739  call    cs:__imp_?UwfCfgGetResetPersistentOverlaySavedMode@@YAJ_NPEAK@Z; UwfCfgGetResetPersistentOverlaySavedMode(bool,ulong *)
0x18000f73f  jmp     short loc_18000F751
0x18000f741  lea     rcx, [rsp+1E0h+var_1BC]
0x18000f746  mov     [rsp+1E0h+var_1BC], r15d
0x18000f74b  call    cs:__imp_?UwfCfgGetResetPersistentOverlay@@YAJPEAK@Z; UwfCfgGetResetPersistentOverlay(ulong *)
0x18000f751  mov     ebx, eax
0x18000f753  test    eax, eax
0x18000f755  js      short loc_18000F761
0x18000f757  mov     eax, [rsp+1E0h+var_1BC]
0x18000f75b  mov     [rdi+8], eax
0x18000f75e  mov     [rdi], si
0x18000f761  mov     rcx, [r14+18h]
0x18000f765  lea     r8, [rsp+1E0h+var_198]
0x18000f76a  mov     edx, [r14+28h]
0x18000f76e  mov     [rsp+1E0h+var_198], r15
0x18000f773  mov     rax, [rcx]
0x18000f776  mov     rax, [rax+58h]
0x18000f77a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f77f  test    eax, eax
0x18000f781  js      short loc_18000F78D
0x18000f783  mov     rsi, [rsp+1E0h+var_198]
0x18000f788  test    rsi, rsi
0x18000f78b  jnz     short loc_18000F799
0x18000f78d  lea     rsi, dword_18001F7A4
0x18000f794  mov     [rsp+1E0h+var_198], rsi
0x18000f799  mov     edx, ebx
0x18000f79b  lea     rcx, [rsp+1E0h+var_190]
0x18000f7a0  call    ?SetStopResult@?$ActivityBase@V?$UwfTraceLoggingProvider@$01@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXJPEAJ@Z; wil::ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(long,long *)
0x18000f7a5  or      r12d, 0FFFFFFFFh
0x18000f7a9  test    rdi, rdi
0x18000f7ac  jnz     short loc_18000F7C2
0x18000f7ae  mov     r8d, [r14+2Ch]
0x18000f7b2  lea     rcx, [rsp+1E0h+var_190]
0x18000f7b7  mov     r9, rsi
0x18000f7ba  mov     edx, r12d
0x18000f7bd  call    ??$Stop@KKPEBG@ConfigurationActivity@?$UwfTraceLoggingProvider@$01@@QEAAXKKPEBG@Z; UwfTraceLoggingProvider<2>::ConfigurationActivity::Stop<ulong,ulong,ushort const *>(ulong,ulong,ushort const *)
0x18000f7c2  mov     r8d, [r14+2Ch]
0x18000f7c6  lea     rcx, [rsp+1E0h+var_190]
0x18000f7cb  mov     eax, 3
0x18000f7d0  mov     r9, rsi
0x18000f7d3  cmp     [rdi], ax
0x18000f7d6  jz      short loc_18000F815
0x18000f7d8  mov     eax, 8
0x18000f7dd  cmp     [rdi], ax
0x18000f7e0  jz      short loc_18000F80A
0x18000f7e2  cmp     [rdi], r13w
0x18000f7e6  jz      short loc_18000F7FF
0x18000f7e8  mov     eax, 13h
0x18000f7ed  mov     edx, r12d
  ... truncated ...
```
