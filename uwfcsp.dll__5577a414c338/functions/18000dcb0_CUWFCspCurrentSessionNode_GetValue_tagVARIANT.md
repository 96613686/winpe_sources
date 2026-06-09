# CUWFCspCurrentSessionNode::GetValue(tagVARIANT *)

- ea: `0x18000dcb0`
- end: `0x18000e2c0`
- name: `?GetValue@CUWFCspCurrentSessionNode@@UEAAJPEAUtagVARIANT@@@Z`
- size: `1552`
- prototype: `__int64 __fastcall(CUWFCspCurrentSessionNode *__hidden this, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `13`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

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
- `0x18000dcb0`
- `0x180019b20`
- `0x18001a210`
- `0x18001b010`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18000e27f`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000e27f`
- `OLEAUT32!__imp_SysAllocString` at `0x18000df31`
- `OLEAUT32!__imp_SysAllocString` at `0x18000e1a2`
- `OLEAUT32!__imp_SysAllocString` at `0x18000df31`
- `OLEAUT32!__imp_SysAllocString` at `0x18000e1a2`
- `OLEAUT32!__imp_VariantInit` at `0x18000dd42`
- `OLEAUT32!__imp_VariantInit` at `0x18000dd42`
- `uwfcfgmgmt!UwfCfgGetPersistTSCAL` at `0x18000de87`
- `uwfcfgmgmt!UwfCfgGetPersistTSCAL` at `0x18000de87`
- `uwfcfgmgmt!UwfCfgGetOverlayCommitState` at `0x18000e07a`
- `uwfcfgmgmt!UwfCfgGetOverlayCommitState` at `0x18000e07a`
- `uwfcfgmgmt!UwfCfgGetVolumeProtected` at `0x18000e042`
- `uwfcfgmgmt!UwfCfgGetVolumeProtected` at `0x18000e042`
- `uwfcfgmgmt!UwfCfgGetVolumeBindByDriveLetter` at `0x18000e004`
- `uwfcfgmgmt!UwfCfgGetVolumeBindByDriveLetter` at `0x18000e004`
- `uwfcfgmgmt!UwfCfgGetDriveLetter` at `0x18000dfb7`
- `uwfcfgmgmt!UwfCfgGetDriveLetter` at `0x18000dfb7`
- `uwfcfgmgmt!UwfCfgGetVolumeSwapfileSize` at `0x18000e0fa`
- `uwfcfgmgmt!UwfCfgGetVolumeSwapfileSize` at `0x18000e0fa`
- `uwfcfgmgmt!UwfCfgGetOverlayMaximumSize` at `0x18000deb2`
- `uwfcfgmgmt!UwfCfgGetOverlayMaximumSize` at `0x18000deb2`
- `uwfcfgmgmt!UwfCfgGetOverlayFlags` at `0x18000dec6`
- `uwfcfgmgmt!UwfCfgGetOverlayFlags` at `0x18000dec6`
- `uwfcfgmgmt!UwfCfgGetOverlayInformation` at `0x18000ddc8`
- `uwfcfgmgmt!UwfCfgGetOverlayInformation` at `0x18000ddc8`
- `uwfcfgmgmt!UwfCfgGetShutdownPending` at `0x18000ddfb`
- `uwfcfgmgmt!UwfCfgGetShutdownPending` at `0x18000ddfb`
- `uwfcfgmgmt!UwfCfgGetFilterEnabled` at `0x18000de0f`
- `uwfcfgmgmt!UwfCfgGetFilterEnabled` at `0x18000e059`
- `uwfcfgmgmt!UwfCfgGetFilterEnabled` at `0x18000de0f`
- `uwfcfgmgmt!UwfCfgGetFilterEnabled` at `0x18000e059`
- `uwfcfgmgmt!UwfCfgDoesFileExclusionExist` at `0x18000e188`
- `uwfcfgmgmt!UwfCfgDoesFileExclusionExist` at `0x18000e188`
- `uwfcfgmgmt!UwfCfgDoesRegExclusionExist` at `0x18000df11`
- `uwfcfgmgmt!UwfCfgDoesRegExclusionExist` at `0x18000df11`
- `uwfcfgmgmt!UwfCfgGetPersistDomainSecretKey` at `0x18000de9b`
- `uwfcfgmgmt!UwfCfgGetPersistDomainSecretKey` at `0x18000de9b`
- `uwfcfgmgmt!UwfCfgGetOverlayType` at `0x18000dedd`
- `uwfcfgmgmt!UwfCfgGetOverlayType` at `0x18000dedd`
- `uwfcfgmgmt!UwfCfgGetWarningThreshold` at `0x18000de45`
- `uwfcfgmgmt!UwfCfgGetWarningThreshold` at `0x18000de45`
- `uwfcfgmgmt!UwfCfgGetCriticalThreshold` at `0x18000dd95`
- `uwfcfgmgmt!UwfCfgGetCriticalThreshold` at `0x18000dd95`
- `ext-ms-win-uwf-servicing-apis-l1-1-0!GetServicingModeState` at `0x18000e0ad`
- `ext-ms-win-uwf-servicing-apis-l1-1-0!GetServicingModeState` at `0x18000e0ad`

## pseudocode

```c
__int64 __fastcall CUWFCspCurrentSessionNode::GetValue(CUWFCspCurrentSessionNode *this, struct tagVARIANT *a2)
{
  int CriticalThreshold; // ebx
  unsigned int v5; // eax
  unsigned int v6; // eax
  unsigned int v7; // eax
  unsigned int v8; // eax
  unsigned int v9; // eax
  LONG v10; // eax
  int ShutdownPending; // eax
  bool v12; // zf
  SHORT v13; // ax
  int WarningThreshold; // eax
  unsigned int v15; // eax
  unsigned int v16; // eax
  unsigned int v17; // eax
  unsigned int v18; // eax
  OLECHAR *v19; // rcx
  BSTR v20; // rax
  unsigned int v21; // eax
  unsigned int v22; // eax
  unsigned int v23; // eax
  unsigned int v24; // eax
  __int64 v25; // rcx
  __int64 v26; // rcx
  unsigned int v27; // eax
  unsigned int v28; // eax
  unsigned int v29; // eax
  int DoesFileExclusionExist; // esi
  OLECHAR *v31; // rcx
  BSTR v32; // rax
  __int64 v33; // rcx
  __int64 v34; // rdx
  int *v35; // rsi
  int v36; // r8d
  LONG lVal; // edx
  bool v39[4]; // [rsp+20h] [rbp-E0h] BYREF
  LONG v40; // [rsp+24h] [rbp-DCh] BYREF
  LONG v41; // [rsp+28h] [rbp-D8h] BYREF
  const unsigned __int16 *v42; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 *v43; // [rsp+38h] [rbp-C8h] BYREF
  OLECHAR *psz; // [rsp+40h] [rbp-C0h] BYREF
  OLECHAR *v45; // [rsp+48h] [rbp-B8h] BYREF
  int *v46; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v47[42]; // [rsp+60h] [rbp-A0h] BYREF

  wil::ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>((__int64)v47);
  v47[0] = &UwfTraceLoggingProvider<2>::ConfigurationActivity::`vftable';
  UwfTraceLoggingProvider<2>::ConfigurationActivity::StartActivity(v47, L"UWFCSPCurrentSessionNodeGet");
  v42 = 0;
  psz = 0;
  v45 = 0;
  v43 = 0;
  if ( !a2 )
  {
    CriticalThreshold = -2147024809;
    goto LABEL_81;
  }
  VariantInit(a2);
  v5 = *((_DWORD *)this + 11);
  if ( v5 <= 0xE )
  {
    if ( v5 != 14 )
    {
      if ( v5 <= 7 )
      {
        if ( v5 != 7 )
        {
          v6 = v5 - 2;
          if ( v6 )
          {
            v7 = v6 - 1;
            if ( v7 )
            {
              v8 = v7 - 1;
              if ( v8 )
              {
                v9 = v8 - 1;
                if ( v9 )
                {
                  if ( v9 == 1 )
                  {
                    v41 = 0;
                    CriticalThreshold = UwfCfgGetCriticalThreshold((unsigned int *)&v41);
                    if ( CriticalThreshold >= 0 )
                    {
                      a2->lVal = v41;
                      a2->vt = 19;
                    }
                    goto LABEL_81;
                  }
LABEL_73:
                  CriticalThreshold = CCSPNodeImpl::GetValue(this, a2);
                  goto LABEL_81;
                }
              }
              v40 = 0;
              v41 = 0;
              CriticalThreshold = UwfCfgGetOverlayInformation((unsigned int *)&v40, (unsigned int *)&v41);
              if ( CriticalThreshold < 0 )
                goto LABEL_81;
              v10 = v41;
              a2->vt = 19;
              if ( *((_DWORD *)this + 11) == 4 )
                v10 = v40;
LABEL_17:
              a2->lVal = v10;
              goto LABEL_81;
            }
            v39[0] = 0;
            ShutdownPending = UwfCfgGetShutdownPending(v39);
          }
          else
          {
            v39[0] = 0;
            ShutdownPending = UwfCfgGetFilterEnabled(1, v39);
          }
          goto LABEL_20;
        }
        v40 = 0;
        WarningThreshold = UwfCfgGetWarningThreshold((unsigned int *)&v40);
LABEL_27:
        CriticalThreshold = WarningThreshold;
        if ( WarningThreshold < 0 )
          goto LABEL_81;
        v10 = v40;
        a2->vt = 19;
        goto LABEL_17;
      }
      v15 = v5 - 8;
      if ( !v15 )
      {
        v40 = 0;
        WarningThreshold = UwfCfgGetOverlayType(1, (enum _UWF_CONFIG_OVERLAY_TYPE *)&v40);
        goto LABEL_27;
      }
      v16 = v15 - 1;
      if ( !v16 )
      {
        v40 = 0;
        WarningThreshold = UwfCfgGetOverlayFlags(1, (unsigned int *)&v40);
        goto LABEL_27;
      }
      v17 = v16 - 1;
      if ( !v17 )
      {
        v40 = 0;
        WarningThreshold = UwfCfgGetOverlayMaximumSize(1, (unsigned int *)&v40);
        goto LABEL_27;
      }
      v18 = v17 - 1;
      if ( v18 )
      {
        if ( v18 != 1 )
          goto LABEL_73;
        v39[0] = 0;
        ShutdownPending = UwfCfgGetPersistTSCAL(1, v39);
      }
      else
      {
        v39[0] = 0;
        ShutdownPending = UwfCfgGetPersistDomainSecretKey(1, v39);
      }
LABEL_20:
      CriticalThreshold = ShutdownPending;
      if ( ShutdownPending < 0 )
        goto LABEL_81;
      v12 = !v39[0];
      goto LABEL_22;
    }
    CriticalThreshold = (*(__int64 (__fastcall **)(_QWORD, __int64, OLECHAR **))(**((_QWORD **)this + 3) + 88LL))(
                          *((_QWORD *)this + 3),
                          3,
                          &psz);
    if ( CriticalThreshold < 0 )
      goto LABEL_81;
    CriticalThreshold = UwfCfgDoesRegExclusionExist(1, psz);
    if ( CriticalThreshold < 0 )
    {
LABEL_41:
      CriticalThreshold = -2046820350;
      goto LABEL_81;
    }
    v19 = psz;
    goto LABEL_43;
  }
  CriticalThreshold = 0;
  if ( v5 <= 0x16 )
  {
    if ( v5 == 22 )
    {
      CriticalThreshold = (*(__int64 (__fastcall **)(_QWORD, __int64, const unsigned __int16 **))(**((_QWORD **)this + 3)
                                                                                                + 88LL))(
                            *((_QWORD *)this + 3),
                            3,
                            &v42);
      if ( CriticalThreshold < 0 )
        goto LABEL_81;
      v40 = 0;
      WarningThreshold = UwfCfgGetVolumeSwapfileSize(1, v42, (unsigned int *)&v40);
      goto LABEL_27;
    }
    v21 = v5 - 15;
    if ( !v21 )
    {
      v40 = 0;
      if ( (unsigned __int8)IsGetServicingModeStatePresent() )
      {
        CriticalThreshold = GetServicingModeState(1, &v40);
        if ( CriticalThreshold < 0 )
          goto LABEL_81;
      }
      v12 = v40 == 0;
      goto LABEL_22;
    }
    v22 = v21 - 1;
    if ( !v22 )
    {
      v39[0] = 0;
      CriticalThreshold = UwfCfgGetFilterEnabled(1, v39);
      if ( CriticalThreshold < 0 )
        goto LABEL_81;
      v12 = !v39[0];
      if ( v39[0] )
      {
        CriticalThreshold = UwfCfgGetOverlayCommitState(v39);
        if ( CriticalThreshold < 0 )
          goto LABEL_81;
        v12 = !v39[0];
      }
LABEL_22:
      a2->vt = 11;
      if ( v12 )
        v13 = 0;
      else
        v13 = -1;
      a2->iVal = v13;
      goto LABEL_81;
    }
    v23 = v22 - 3;
    if ( !v23 )
    {
      v26 = *((_QWORD *)this + 3);
      v39[0] = 0;
      CriticalThreshold = (*(__int64 (__fastcall **)(__int64, __int64, const unsigned __int16 **))(*(_QWORD *)v26 + 88LL))(
                            v26,
                            3,
                            &v42);
      if ( CriticalThreshold < 0 )
        goto LABEL_81;
      ShutdownPending = UwfCfgGetVolumeProtected(1, v42, v39);
      goto LABEL_20;
    }
    v24 = v23 - 1;
    if ( !v24 )
    {
      v25 = *((_QWORD *)this + 3);
      v39[0] = 0;
      CriticalThreshold = (*(__int64 (__fastcall **)(__int64, __int64, const unsigned __int16 **))(*(_QWORD *)v25 + 88LL))(
                            v25,
                            3,
                            &v42);
      if ( CriticalThreshold < 0 )
        goto LABEL_81;
      ShutdownPending = UwfCfgGetVolumeBindByDriveLetter(1, v42, v39);
      goto LABEL_20;
    }
    if ( v24 != 1 )
      goto LABEL_73;
    CriticalThreshold = (*(__int64 (__fastcall **)(_QWORD, __int64, const unsigned __int16 **))(**((_QWORD **)this + 3)
                                                                                              + 88LL))(
                          *((_QWORD *)this + 3),
                          3,
                          &v42);
    if ( CriticalThreshold < 0 )
      goto LABEL_81;
    CriticalThreshold = UwfCfgGetDriveLetter(1, v42, &v43);
    if ( CriticalThreshold < 0 )
      goto LABEL_81;
    v19 = v43;
LABEL_43:
    a2->vt = 8;
LABEL_44:
    v20 = SysAllocString(v19);
    a2->llVal = (LONGLONG)v20;
    if ( !v20 )
      CriticalThreshold = -2147024882;
    goto LABEL_81;
  }
  v27 = v5 - 24;
  if ( v27 )
  {
    v28 = v27 - 1;
    if ( v28 )
    {
      v29 = v28 - 1;
      if ( v29 )
      {
        if ( v29 - 1 >= 2 )
          goto LABEL_73;
      }
    }
    a2->vt = 8;
    v19 = (OLECHAR *)*((_QWORD *)this + 4);
    goto LABEL_44;
  }
  CriticalThreshold = (*(__int64 (__fastcall **)(_QWORD, __int64, const unsigned __int16 **))(**((_QWORD **)this + 3)
                                                                                            + 88LL))(
                        *((_QWORD *)this + 3),
                        3,
                        &v42);
  if ( CriticalThreshold < 0 )
    goto LABEL_81;
  CriticalThreshold = (*(__int64 (__fastcall **)(_QWORD, __int64, OLECHAR **))(**((_QWORD **)this + 3) + 88LL))(
                        *((_QWORD *)this + 3),
                        5,
                        &v45);
  if ( CriticalThreshold < 0 )
    goto LABEL_81;
  DoesFileExclusionExist = UwfCfgDoesFileExclusionExist(1, v42, v45);
  if ( DoesFileExclusionExist < 0 )
    goto LABEL_41;
  v31 = v45;
  a2->vt = 8;
  v32 = SysAllocString(v31);
  a2->llVal = (LONGLONG)v32;
  if ( !v32 )
    DoesFileExclusionExist = -2147024882;
  CriticalThreshold = DoesFileExclusionExist;
LABEL_81:
  v33 = *((_QWORD *)this + 3);
  v34 = *((unsigned int *)this + 10);
  v46 = 0;
  if ( (*(int (__fastcall **)(__int64, __int64, int **))(*(_QWORD *)v33 + 88LL))(v33, v34, &v46) < 0 || (v35 = v46) == 0 )
  {
    v35 = &dword_18001F7A4;
    v46 = &dword_18001F7A4;
  }
  wil::ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
    v47,
    (unsigned int)CriticalThreshold);
  if ( !a2 )
    UwfTraceLoggingProvider<2>::ConfigurationActivity::Stop<unsigned long,unsigned long,unsigned short const *>(
      (__int64)v47,
      -1,
      *((_DWORD *)this + 11),
      (__int64)v35);
  v36 = *((_DWORD *)this + 11);
  switch ( a2->vt )
  {
    case 3u:
      UwfTraceLoggingProvider<2>::ConfigurationActivity::Stop<long,unsigned long,unsigned short const *>(
        (__int64)v47,
        a2->lVal,
        v36,
        (__int64)v35);
      break;
    case 8u:
      UwfTraceLoggingProvider<2>::ConfigurationActivity::Stop<unsigned short *,unsigned long,unsigned short const *>(
        (__int64)v47,
        a2->plVal,
        v36,
        v35);
      break;
    case 0xBu:
      UwfTraceLoggingProvider<2>::ConfigurationActivity::Stop<short,unsigned long,unsigned short const *>(
        (__int64)v47,
        a2->iVal,
        v36,
        v35);
      break;
    default:
      lVal = -1;
      if ( a2->vt == 19 )
        lVal = a2->lVal;
      UwfTraceLoggingProvider<2>::ConfigurationActivity::Stop<unsigned long,unsigned long,unsigned short const *>(
        (__int64)v47,
        lVal,
        v36,
        (__int64)v35);
      break;
  }
  if ( v43 )
  {
    operator delete[](v43);
    v43 = 0;
  }
  UwfTraceLoggingProvider<2>::ConfigurationActivity::~ConfigurationActivity(v47);
  return (unsigned int)CriticalThreshold;
}

```

## disassembly

```asm
0x18000dcb0  mov     [rsp-8+arg_10], rbx
0x18000dcb5  push    rbp
0x18000dcb6  push    rsi
0x18000dcb7  push    rdi
0x18000dcb8  push    r12
0x18000dcba  push    r13
0x18000dcbc  push    r14
0x18000dcbe  push    r15
0x18000dcc0  lea     rbp, [rsp-0C0h]
0x18000dcc8  sub     rsp, 1C0h
0x18000dccf  mov     rax, cs:__security_cookie
0x18000dcd6  xor     rax, rsp
0x18000dcd9  mov     [rbp+0F0h+var_40], rax
0x18000dce0  mov     r14, rcx
0x18000dce3  mov     rdi, rdx
0x18000dce6  lea     rcx, [rsp+1F0h+var_190]
0x18000dceb  call    ??0?$ActivityBase@V?$UwfTraceLoggingProvider@$01@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18000dcf0  lea     rax, ??_7ConfigurationActivity@?$UwfTraceLoggingProvider@$01@@6B@; const UwfTraceLoggingProvider<2>::ConfigurationActivity::`vftable'
0x18000dcf7  lea     rdx, aUwfcspcurrents; "UWFCSPCurrentSessionNodeGet"
0x18000dcfe  mov     [rsp+1F0h+var_190], rax
0x18000dd03  lea     rcx, [rsp+1F0h+var_190]
0x18000dd08  call    ?StartActivity@ConfigurationActivity@?$UwfTraceLoggingProvider@$01@@QEAAXPEBG@Z; UwfTraceLoggingProvider<2>::ConfigurationActivity::StartActivity(ushort const *)
0x18000dd0d  xor     r15d, r15d
0x18000dd10  mov     [rsp+1F0h+var_1C0], r15
0x18000dd15  mov     [rsp+1F0h+psz], r15
0x18000dd1a  mov     [rsp+1F0h+var_1A8], r15
0x18000dd1f  mov     [rsp+1F0h+var_1B8], r15
0x18000dd24  lea     esi, [r15+13h]
0x18000dd28  lea     r13d, [r15+0Bh]
0x18000dd2c  lea     r12d, [r15+3]
0x18000dd30  test    rdi, rdi
0x18000dd33  jnz     short loc_18000DD3F
0x18000dd35  mov     ebx, 80070057h
0x18000dd3a  jmp     loc_18000E1B9
0x18000dd3f  mov     rcx, rdi; pvarg
0x18000dd42  call    cs:__imp_VariantInit
0x18000dd48  mov     eax, [r14+2Ch]
0x18000dd4c  cmp     eax, 0Eh
0x18000dd4f  ja      loc_18000DF4E
0x18000dd55  jz      loc_18000DEE8
0x18000dd5b  cmp     eax, 7
0x18000dd5e  ja      loc_18000DE5E
0x18000dd64  jz      loc_18000DE3B
0x18000dd6a  sub     eax, 2
0x18000dd6d  jz      loc_18000DE03
0x18000dd73  sub     eax, 1
0x18000dd76  jz      short loc_18000DDF1
0x18000dd78  sub     eax, 1
0x18000dd7b  jz      short loc_18000DDB4
0x18000dd7d  sub     eax, 1
0x18000dd80  jz      short loc_18000DDB4
0x18000dd82  cmp     eax, 1
0x18000dd85  jnz     loc_18000E11E
0x18000dd8b  lea     rcx, [rsp+1F0h+var_1C8]
0x18000dd90  mov     [rsp+1F0h+var_1C8], r15d
0x18000dd95  call    cs:__imp_?UwfCfgGetCriticalThreshold@@YAJPEAK@Z; UwfCfgGetCriticalThreshold(ulong *)
0x18000dd9b  mov     ebx, eax
0x18000dd9d  test    eax, eax
0x18000dd9f  js      loc_18000E1B9
0x18000dda5  mov     ecx, [rsp+1F0h+var_1C8]
0x18000dda9  mov     [rdi+8], ecx
0x18000ddac  mov     [rdi], si
0x18000ddaf  jmp     loc_18000E1B9
0x18000ddb4  lea     rdx, [rsp+1F0h+var_1C8]
0x18000ddb9  mov     [rsp+1F0h+var_1CC], r15d
0x18000ddbe  lea     rcx, [rsp+1F0h+var_1CC]
0x18000ddc3  mov     [rsp+1F0h+var_1C8], r15d
0x18000ddc8  call    cs:__imp_?UwfCfgGetOverlayInformation@@YAJPEAK0@Z; UwfCfgGetOverlayInformation(ulong *,ulong *)
0x18000ddce  mov     ebx, eax
0x18000ddd0  test    eax, eax
0x18000ddd2  js      loc_18000E1B9
0x18000ddd8  mov     eax, [rsp+1F0h+var_1C8]
0x18000dddc  mov     [rdi], si
0x18000dddf  cmp     dword ptr [r14+2Ch], 4
0x18000dde4  cmovz   eax, [rsp+1F0h+var_1CC]
0x18000dde9  mov     [rdi+8], eax
0x18000ddec  jmp     loc_18000E1B9
0x18000ddf1  lea     rcx, [rsp+1F0h+var_1D0]
0x18000ddf6  mov     [rsp+1F0h+var_1D0], r15b
0x18000ddfb  call    cs:__imp_?UwfCfgGetShutdownPending@@YAJPEA_N@Z; UwfCfgGetShutdownPending(bool *)
0x18000de01  jmp     short loc_18000DE15
0x18000de03  lea     rdx, [rsp+1F0h+var_1D0]
0x18000de08  mov     [rsp+1F0h+var_1D0], r15b
0x18000de0d  mov     cl, 1
0x18000de0f  call    cs:__imp_?UwfCfgGetFilterEnabled@@YAJ_NPEA_N@Z; UwfCfgGetFilterEnabled(bool,bool *)
0x18000de15  mov     ebx, eax
0x18000de17  test    eax, eax
0x18000de19  js      loc_18000E1B9
0x18000de1f  cmp     [rsp+1F0h+var_1D0], r15b
0x18000de24  mov     [rdi], r13w
0x18000de28  jz      short loc_18000DE2F
0x18000de2a  or      eax, 0FFFFFFFFh
0x18000de2d  jmp     short loc_18000DE32
0x18000de2f  mov     eax, r15d
0x18000de32  mov     [rdi+8], ax
0x18000de36  jmp     loc_18000E1B9
0x18000de3b  lea     rcx, [rsp+1F0h+var_1CC]
0x18000de40  mov     [rsp+1F0h+var_1CC], r15d
0x18000de45  call    cs:__imp_?UwfCfgGetWarningThreshold@@YAJPEAK@Z; UwfCfgGetWarningThreshold(ulong *)
0x18000de4b  mov     ebx, eax
0x18000de4d  test    eax, eax
0x18000de4f  js      loc_18000E1B9
0x18000de55  mov     eax, [rsp+1F0h+var_1CC]
0x18000de59  mov     [rdi], si
0x18000de5c  jmp     short loc_18000DDE9
0x18000de5e  sub     eax, 8
0x18000de61  jz      short loc_18000DED1
0x18000de63  sub     eax, 1
0x18000de66  jz      short loc_18000DEBA
0x18000de68  sub     eax, 1
0x18000de6b  jz      short loc_18000DEA6
0x18000de6d  sub     eax, 1
0x18000de70  jz      short loc_18000DE8F
0x18000de72  cmp     eax, 1
0x18000de75  jnz     loc_18000E11E
0x18000de7b  lea     rdx, [rsp+1F0h+var_1D0]
0x18000de80  mov     [rsp+1F0h+var_1D0], r15b
0x18000de85  mov     cl, al
0x18000de87  call    cs:__imp_?UwfCfgGetPersistTSCAL@@YAJ_NPEA_N@Z; UwfCfgGetPersistTSCAL(bool,bool *)
0x18000de8d  jmp     short loc_18000DE15
0x18000de8f  lea     rdx, [rsp+1F0h+var_1D0]
0x18000de94  mov     [rsp+1F0h+var_1D0], r15b
0x18000de99  mov     cl, 1
0x18000de9b  call    cs:__imp_?UwfCfgGetPersistDomainSecretKey@@YAJ_NPEA_N@Z; UwfCfgGetPersistDomainSecretKey(bool,bool *)
0x18000dea1  jmp     loc_18000DE15
0x18000dea6  lea     rdx, [rsp+1F0h+var_1CC]
0x18000deab  mov     [rsp+1F0h+var_1CC], r15d
0x18000deb0  mov     cl, 1
0x18000deb2  call    cs:__imp_?UwfCfgGetOverlayMaximumSize@@YAJ_NPEAK@Z; UwfCfgGetOverlayMaximumSize(bool,ulong *)
0x18000deb8  jmp     short loc_18000DE4B
0x18000deba  lea     rdx, [rsp+1F0h+var_1CC]
0x18000debf  mov     [rsp+1F0h+var_1CC], r15d
0x18000dec4  mov     cl, 1
0x18000dec6  call    cs:__imp_?UwfCfgGetOverlayFlags@@YAJ_NPEAK@Z; UwfCfgGetOverlayFlags(bool,ulong *)
0x18000decc  jmp     loc_18000DE4B
0x18000ded1  lea     rdx, [rsp+1F0h+var_1CC]
0x18000ded6  mov     [rsp+1F0h+var_1CC], r15d
0x18000dedb  mov     cl, 1
0x18000dedd  call    cs:__imp_?UwfCfgGetOverlayType@@YAJ_NPEAW4_UWF_CONFIG_OVERLAY_TYPE@@@Z; UwfCfgGetOverlayType(bool,_UWF_CONFIG_OVERLAY_TYPE *)
0x18000dee3  jmp     loc_18000DE4B
0x18000dee8  mov     rcx, [r14+18h]
0x18000deec  lea     r8, [rsp+1F0h+psz]
0x18000def1  mov     edx, r12d
0x18000def4  mov     rax, [rcx]
0x18000def7  mov     rax, [rax+58h]
0x18000defb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000df00  mov     ebx, eax
0x18000df02  test    eax, eax
0x18000df04  js      loc_18000E1B9
0x18000df0a  mov     rdx, [rsp+1F0h+psz]
0x18000df0f  mov     cl, 1
0x18000df11  call    cs:__imp_?UwfCfgDoesRegExclusionExist@@YAJ_NPEBG@Z; UwfCfgDoesRegExclusionExist(bool,ushort const *)
0x18000df17  mov     ebx, eax
0x18000df19  test    eax, eax
0x18000df1b  jns     short loc_18000DF27
0x18000df1d  mov     ebx, 86000002h
0x18000df22  jmp     loc_18000E1B9
0x18000df27  mov     rcx, [rsp+1F0h+psz]; psz
0x18000df2c  mov     word ptr [rdi], 8
0x18000df31  call    cs:__imp_SysAllocString
0x18000df37  mov     [rdi+8], rax
0x18000df3b  test    rax, rax
0x18000df3e  jnz     loc_18000E1B9
0x18000df44  mov     ebx, 8007000Eh
0x18000df49  jmp     loc_18000E1B9
0x18000df4e  mov     ebx, r15d
0x18000df51  cmp     eax, 16h
0x18000df54  ja      loc_18000E105
0x18000df5a  jz      loc_18000E0C7
0x18000df60  sub     eax, 0Fh
0x18000df63  jz      loc_18000E095
0x18000df69  sub     eax, 1
0x18000df6c  jz      loc_18000E04D
0x18000df72  sub     eax, r12d
0x18000df75  jz      loc_18000E00F
0x18000df7b  sub     eax, 1
0x18000df7e  jz      short loc_18000DFD1
0x18000df80  cmp     eax, 1
0x18000df83  jnz     loc_18000E11E
0x18000df89  mov     rcx, [r14+18h]
0x18000df8d  lea     r8, [rsp+1F0h+var_1C0]
0x18000df92  mov     edx, r12d
0x18000df95  mov     rax, [rcx]
0x18000df98  mov     rax, [rax+58h]
0x18000df9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dfa1  mov     ebx, eax
0x18000dfa3  test    eax, eax
0x18000dfa5  js      loc_18000E1B9
0x18000dfab  mov     rdx, [rsp+1F0h+var_1C0]
0x18000dfb0  lea     r8, [rsp+1F0h+var_1B8]
0x18000dfb5  mov     cl, 1
0x18000dfb7  call    cs:__imp_?UwfCfgGetDriveLetter@@YAJ_NPEBGPEAPEAG@Z; UwfCfgGetDriveLetter(bool,ushort const *,ushort * *)
0x18000dfbd  mov     ebx, eax
0x18000dfbf  test    eax, eax
0x18000dfc1  js      loc_18000E1B9
0x18000dfc7  mov     rcx, [rsp+1F0h+var_1B8]
0x18000dfcc  jmp     loc_18000DF2C
0x18000dfd1  mov     rcx, [r14+18h]
0x18000dfd5  lea     r8, [rsp+1F0h+var_1C0]
0x18000dfda  mov     [rsp+1F0h+var_1D0], r15b
0x18000dfdf  mov     edx, r12d
0x18000dfe2  mov     rax, [rcx]
0x18000dfe5  mov     rax, [rax+58h]
0x18000dfe9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dfee  mov     ebx, eax
0x18000dff0  test    eax, eax
0x18000dff2  js      loc_18000E1B9
0x18000dff8  mov     rdx, [rsp+1F0h+var_1C0]
0x18000dffd  lea     r8, [rsp+1F0h+var_1D0]
0x18000e002  mov     cl, 1
0x18000e004  call    cs:__imp_?UwfCfgGetVolumeBindByDriveLetter@@YAJ_NPEBGPEA_N@Z; UwfCfgGetVolumeBindByDriveLetter(bool,ushort const *,bool *)
0x18000e00a  jmp     loc_18000DE15
0x18000e00f  mov     rcx, [r14+18h]
0x18000e013  lea     r8, [rsp+1F0h+var_1C0]
0x18000e018  mov     [rsp+1F0h+var_1D0], r15b
0x18000e01d  mov     edx, r12d
0x18000e020  mov     rax, [rcx]
0x18000e023  mov     rax, [rax+58h]
0x18000e027  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e02c  mov     ebx, eax
0x18000e02e  test    eax, eax
0x18000e030  js      loc_18000E1B9
0x18000e036  mov     rdx, [rsp+1F0h+var_1C0]
0x18000e03b  lea     r8, [rsp+1F0h+var_1D0]
0x18000e040  mov     cl, 1
0x18000e042  call    cs:__imp_?UwfCfgGetVolumeProtected@@YAJ_NPEBGPEA_N@Z; UwfCfgGetVolumeProtected(bool,ushort const *,bool *)
0x18000e048  jmp     loc_18000DE15
0x18000e04d  lea     rdx, [rsp+1F0h+var_1D0]
0x18000e052  mov     [rsp+1F0h+var_1D0], r15b
0x18000e057  mov     cl, 1
0x18000e059  call    cs:__imp_?UwfCfgGetFilterEnabled@@YAJ_NPEA_N@Z; UwfCfgGetFilterEnabled(bool,bool *)
0x18000e05f  mov     ebx, eax
0x18000e061  test    eax, eax
0x18000e063  js      loc_18000E1B9
0x18000e069  mov     al, [rsp+1F0h+var_1D0]
0x18000e06d  test    al, al
0x18000e06f  jz      loc_18000DE24
0x18000e075  lea     rcx, [rsp+1F0h+var_1D0]
0x18000e07a  call    cs:__imp_?UwfCfgGetOverlayCommitState@@YAJPEA_N@Z; UwfCfgGetOverlayCommitState(bool *)
0x18000e080  mov     ebx, eax
0x18000e082  test    eax, eax
0x18000e084  js      loc_18000E1B9
0x18000e08a  mov     al, [rsp+1F0h+var_1D0]
0x18000e08e  test    al, al
0x18000e090  jmp     loc_18000DE24
0x18000e095  mov     [rsp+1F0h+var_1CC], r15d
0x18000e09a  call    IsGetServicingModeStatePresent
0x18000e09f  test    al, al
0x18000e0a1  jz      short loc_18000E0BD
0x18000e0a3  lea     rdx, [rsp+1F0h+var_1CC]
0x18000e0a8  mov     ecx, 1
0x18000e0ad  call    cs:__imp_GetServicingModeState
0x18000e0b3  mov     ebx, eax
0x18000e0b5  test    eax, eax
0x18000e0b7  js      loc_18000E1B9
0x18000e0bd  cmp     [rsp+1F0h+var_1CC], r15d
0x18000e0c2  jmp     loc_18000DE24
0x18000e0c7  mov     rcx, [r14+18h]
0x18000e0cb  lea     r8, [rsp+1F0h+var_1C0]
0x18000e0d0  mov     edx, r12d
0x18000e0d3  mov     rax, [rcx]
0x18000e0d6  mov     rax, [rax+58h]
0x18000e0da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e0df  mov     ebx, eax
0x18000e0e1  test    eax, eax
0x18000e0e3  js      loc_18000E1B9
0x18000e0e9  mov     rdx, [rsp+1F0h+var_1C0]
0x18000e0ee  lea     r8, [rsp+1F0h+var_1CC]
0x18000e0f3  mov     cl, 1
0x18000e0f5  mov     [rsp+1F0h+var_1CC], r15d
0x18000e0fa  call    cs:__imp_?UwfCfgGetVolumeSwapfileSize@@YAJ_NPEBGPEAK@Z; UwfCfgGetVolumeSwapfileSize(bool,ushort const *,ulong *)
0x18000e100  jmp     loc_18000DE4B
0x18000e105  sub     eax, 18h
0x18000e108  jz      short loc_18000E13E
0x18000e10a  sub     eax, 1
0x18000e10d  jz      short loc_18000E130
0x18000e10f  sub     eax, 1
0x18000e112  jz      short loc_18000E130
0x18000e114  sub     eax, 1
0x18000e117  jz      short loc_18000E130
0x18000e119  cmp     eax, 1
0x18000e11c  jz      short loc_18000E130
0x18000e11e  mov     rdx, rdi; struct tagVARIANT *
0x18000e121  mov     rcx, r14; this
0x18000e124  call    ?GetValue@CCSPNodeImpl@@UEAAJPEAUtagVARIANT@@@Z; CCSPNodeImpl::GetValue(tagVARIANT *)
0x18000e129  mov     ebx, eax
0x18000e12b  jmp     loc_18000E1B9
0x18000e130  mov     word ptr [rdi], 8
0x18000e135  mov     rcx, [r14+20h]
0x18000e139  jmp     loc_18000DF31
0x18000e13e  mov     rcx, [r14+18h]
0x18000e142  lea     r8, [rsp+1F0h+var_1C0]
0x18000e147  mov     edx, r12d
0x18000e14a  mov     rax, [rcx]
0x18000e14d  mov     rax, [rax+58h]
0x18000e151  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e156  mov     ebx, eax
0x18000e158  test    eax, eax
0x18000e15a  js      short loc_18000E1B9
0x18000e15c  mov     rcx, [r14+18h]
  ... truncated ...
```
