# KspImportKeyInternal(unsigned __int64,unsigned __int64,ushort const *,_BCryptBufferDesc *,unsigned __int64 *,uchar *,ulong,ulong)

- ea: `0x1800232ec`
- end: `0x180023dc7`
- name: `?KspImportKeyInternal@@YAJ_K0PEBGPEAU_BCryptBufferDesc@@PEA_KPEAEKK@Z`
- size: `2779`
- prototype: `int(unsigned __int64, unsigned __int64, const unsigned __int16 *, struct _BCryptBufferDesc *, unsigned __int64 *, unsigned __int8 *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18002ae80`

## callees

- `0x180009e82`
- `0x18000a3c8`
- `0x18000a408`
- `0x18000d2a8`
- `0x18000d9d0`
- `0x180011444`
- `0x180011fd8`
- `0x1800122b4`
- `0x180012b24`
- `0x1800135dc`
- `0x180013734`
- `0x180013aac`
- `0x18001423c`
- `0x180014858`
- `0x180016adc`
- `0x180019eb8`
- `0x1800232ec`
- `0x18002b140`
- `0x18002ec0c`
- `0x18003af5c`
- `0x18003bc98`
- `0x18003c240`

## import_xrefs

- `ncrypt!NCryptDeleteKey` at `0x180023681`
- `ncrypt!NCryptDeleteKey` at `0x180023681`
- `ncrypt!NCryptFinalizeKey` at `0x180023a84`
- `ncrypt!NCryptFinalizeKey` at `0x180023a84`
- `ncrypt!NCryptImportKey` at `0x180023823`
- `ncrypt!NCryptImportKey` at `0x180023c27`
- `ncrypt!NCryptImportKey` at `0x180023823`
- `ncrypt!NCryptImportKey` at `0x180023c27`
- `ncrypt!NCryptSetProperty` at `0x180023a32`
- `ncrypt!NCryptSetProperty` at `0x180023a32`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall KspImportKeyInternal(
        __int64 a1,
        NCRYPT_KEY_HANDLE a2,
        const unsigned __int16 *a3,
        struct _BCryptBufferDesc *a4,
        unsigned __int64 *a5,
        unsigned __int8 *a6,
        DWORD cbData,
        DWORD dwFlags)
{
  __int64 v10; // rcx
  __int64 v11; // r14
  PVOID v12; // rcx
  unsigned int Handle; // ebx
  void *v14; // rax
  _QWORD *v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // rcx
  _QWORD *v18; // rcx
  int v19; // edx
  NCryptBufferDesc *v20; // r13
  __int64 v21; // rcx
  int v22; // ebx
  unsigned int v23; // edi
  NCryptBufferDesc *v24; // rax
  NCryptBufferDesc *v25; // rdi
  struct _BCryptBuffer *v26; // rax
  unsigned __int16 *pvBuffer; // rcx
  NCryptBufferDesc *v28; // rcx
  unsigned int v30; // edi
  PBCryptBuffer pBuffers; // r8
  __int64 v32; // rcx
  int v33; // ebx
  int v34; // ebx
  __int64 v35; // rcx
  char IsEnabled; // al
  WCHAR *v37; // r10
  __int64 v38; // rcx
  _QWORD *v39; // rcx
  int v40; // edx
  unsigned int v41; // eax
  _QWORD *v42; // rcx
  int v43; // edx
  struct _BCryptBuffer *v44; // rcx
  __int64 v45; // r9
  _QWORD *v46; // rcx
  __int64 v47; // rdx
  __int64 v48; // rcx
  __int64 v49; // rcx
  __int64 v50; // rcx
  __int64 v51; // rcx
  __int64 v52; // rcx
  __int64 v53; // rcx
  __int64 PqcParamInfoByKeyHandle; // rax
  __int64 v55; // rcx
  int pbData; // [rsp+28h] [rbp-D8h]
  struct _BCryptBuffer *v57; // [rsp+40h] [rbp-C0h]
  NCryptBufferDesc *pParameterList; // [rsp+48h] [rbp-B8h] BYREF
  int v59; // [rsp+50h] [rbp-B0h]
  NCRYPT_KEY_HANDLE hKey; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v61; // [rsp+60h] [rbp-A0h] BYREF
  int v62; // [rsp+68h] [rbp-98h]
  unsigned int v63; // [rsp+6Ch] [rbp-94h]
  BYTE pbInput[4]; // [rsp+70h] [rbp-90h] BYREF
  BOOL v65; // [rsp+74h] [rbp-8Ch]
  __int64 v66; // [rsp+78h] [rbp-88h] BYREF
  PBYTE v67; // [rsp+80h] [rbp-80h]
  LPCWSTR pszBlobType; // [rsp+88h] [rbp-78h]
  NCRYPT_KEY_HANDLE hImportKey; // [rsp+90h] [rbp-70h]
  _QWORD v70[2]; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int64 *v71; // [rsp+A8h] [rbp-58h]
  unsigned __int16 v72[40]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 v73[264]; // [rsp+100h] [rbp+0h] BYREF

  pszBlobType = a3;
  hImportKey = a2;
  v71 = a5;
  v67 = a6;
  pParameterList = 0;
  LODWORD(v66) = 0;
  v59 = 0;
  v61 = 0;
  hKey = 0;
  *(_DWORD *)pbInput = 3;
  memset_0(v73, 0, 0x208u);
  memset_0(v72, 0, sizeof(v72));
  v62 = 0;
  v70[0] = &Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable';
  v70[1] = 0;
  if ( (dwFlags & 0xFFFFFBBF) != 0 )
  {
    v11 = 0;
    WppTraceIndent(v10, 2);
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        204,
        (unsigned int)&WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids,
        (_DWORD)WPP_pszIndent,
        dwFlags);
    }
    WppTraceIndent(v12, 2);
    Handle = -2146893815;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 205, &WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids, 2148073481LL);
    }
    goto LABEL_40;
  }
  v14 = MIDL_user_allocate(0x4C0u);
  v11 = (__int64)v14;
  if ( !v14 )
  {
    Handle = -2146893810;
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_40;
    }
    v16 = 206;
    goto LABEL_15;
  }
  memset_0(v14, 0, 0x4C0u);
  Handle = HtGetHandle(a1, 3, &pParameterList);
  if ( Handle )
  {
    WppTraceIndent(v17, 2);
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_40;
    }
    v19 = 207;
    goto LABEL_21;
  }
  v20 = pParameterList;
  Handle = KspEnterCriticalSection(&pParameterList[1]);
  if ( Handle )
  {
    WppTraceIndent(v21, 2);
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_40;
    }
    v19 = 208;
LABEL_21:
    WPP_SF_sd(
      v18[2],
      v19,
      (unsigned int)&WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids,
      (_DWORD)WPP_pszIndent,
      Handle);
    goto LABEL_40;
  }
  pParameterList = 0;
  v57 = 0;
  v22 = 0;
  Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Attach(v70, &v20[1]);
  v23 = dwFlags & 0x400;
  v63 = v23;
  v65 = v23 == 0;
  if ( !a4 )
  {
LABEL_60:
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SmartCardKspPqcSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_SmartCardKspPqcSupport>::GetImpl'::`2'::impl);
    v37 = (WCHAR *)pszBlobType;
    if ( IsEnabled )
      *(_QWORD *)(v11 + 1176) = pszBlobType;
    if ( v22 )
    {
      Handle = NCryptImportKey(
                 *(_QWORD *)(*(_QWORD *)&v20->ulVersion + 224LL),
                 hImportKey,
                 v37,
                 pParameterList,
                 &hKey,
                 v67,
                 cbData,
                 dwFlags | 0x400);
      if ( Handle )
      {
        WppTraceIndent(v38, 2);
        v39 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v40 = 216;
LABEL_68:
          WPP_SF_sd(
            v39[2],
            v40,
            (unsigned int)&WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids,
            (_DWORD)WPP_pszIndent,
            Handle);
          goto LABEL_142;
        }
        goto LABEL_142;
      }
      Handle = NCryptSetProperty(hKey, L"Export Policy", pbInput, 4u, 0);
      if ( Handle )
      {
        WppTraceIndent(v48, 2);
        v39 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v40 = 217;
          goto LABEL_68;
        }
LABEL_142:
        v44 = v57;
        if ( v57 )
          goto LABEL_75;
        goto LABEL_76;
      }
      Handle = NCryptFinalizeKey(hKey, 0);
      if ( Handle )
      {
        WppTraceIndent(v49, 2);
        v39 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v40 = 218;
          goto LABEL_68;
        }
        goto LABEL_142;
      }
      Handle = KsppPrepareKeyImport(hKey);
      if ( Handle )
      {
        WppTraceIndent(v50, 2);
        v39 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v40 = 219;
          goto LABEL_68;
        }
        goto LABEL_142;
      }
      if ( !v23 )
      {
        Handle = KsppFinalizeKey(v20, v11, dwFlags);
        if ( Handle )
        {
          WppTraceIndent(v51, 2);
          v39 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v40 = 220;
            goto LABEL_68;
          }
          goto LABEL_142;
        }
      }
      *(_DWORD *)(v11 + 1048) = v65;
    }
    else
    {
      Handle = KsppBlobToKeySpec(v37, (__int64)&v66, (__int64)&v61);
      if ( Handle )
      {
        WppTraceIndent(v52, 2);
        v39 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v40 = 221;
          goto LABEL_68;
        }
        goto LABEL_142;
      }
      Handle = NCryptImportKey(
                 *(_QWORD *)(*(_QWORD *)&v20->ulVersion + 224LL),
                 hImportKey,
                 pszBlobType,
                 a4,
                 &hKey,
                 v67,
                 cbData,
                 dwFlags);
      if ( Handle )
      {
        WppTraceIndent(v53, 2);
        v39 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v40 = 222;
          goto LABEL_68;
        }
        goto LABEL_142;
      }
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SmartCardKspPqcSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_SmartCardKspPqcSupport>::GetImpl'::`2'::impl)
        && (unsigned int)(v59 - 64) <= 1 )
      {
        PqcParamInfoByKeyHandle = GetPqcParamInfoByKeyHandle(hKey);
        if ( !PqcParamInfoByKeyHandle )
        {
          WppTraceIndent(0, 2);
          Handle = -2146893802;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              223,
              &WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids,
              2148073494LL);
          }
          goto LABEL_142;
        }
        LODWORD(v61) = *(_DWORD *)(PqcParamInfoByKeyHandle + 12);
        v59 = *(_DWORD *)(PqcParamInfoByKeyHandle + 32);
        *(_QWORD *)(v11 + 1208) = *(_QWORD *)PqcParamInfoByKeyHandle;
      }
      *(_DWORD *)(v11 + 1048) = 1;
      *(_QWORD *)(v11 + 1144) = hKey;
      *(_DWORD *)(v11 + 1056) = 0;
      *(_DWORD *)(v11 + 1040) = v59;
      *(_DWORD *)(v11 + 1044) = v61;
      hKey = 0;
    }
    *(_DWORD *)(v11 + 1064) = (HIDWORD(v20[3].pBuffers) | dwFlags) & 0x40;
    Handle = HtAddHandle(v11, 2, v71);
    if ( Handle )
    {
      WppTraceIndent(v55, 2);
      v39 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v40 = 224;
        goto LABEL_68;
      }
    }
    else
    {
      v11 = 0;
    }
    goto LABEL_142;
  }
  v24 = (NCryptBufferDesc *)MIDL_user_allocate(0x10u);
  v25 = v24;
  pParameterList = v24;
  if ( !v24 )
  {
    Handle = -2146893810;
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_40;
    }
    v16 = 209;
LABEL_15:
    WPP_SF_s(v15[2], v16, &WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids, WPP_pszIndent);
    goto LABEL_40;
  }
  v24->ulVersion = a4->ulVersion;
  v24->cBuffers = a4->cBuffers;
  v26 = (struct _BCryptBuffer *)MIDL_user_allocate(16LL * a4->cBuffers);
  v57 = v26;
  if ( !v26 )
  {
    Handle = -2146893810;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        210,
        &WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids,
        WPP_pszIndent);
    }
    v28 = pParameterList;
    goto LABEL_39;
  }
  v25->pBuffers = v26;
  v30 = 0;
  if ( !a4->cBuffers )
  {
LABEL_59:
    v23 = v63;
    goto LABEL_60;
  }
  while ( 1 )
  {
    pBuffers = a4->pBuffers;
    if ( pBuffers[v30].BufferType != 45 )
    {
      v35 = v30 - 1;
      if ( !v22 )
        v35 = v30;
      pvBuffer = (unsigned __int16 *)(2 * v35);
      *(struct _BCryptBuffer *)((char *)pParameterList->pBuffers + 8 * (_QWORD)pvBuffer) = pBuffers[v30];
      goto LABEL_58;
    }
    if ( !pBuffers[v30].cbBuffer )
      break;
    pvBuffer = (unsigned __int16 *)pBuffers[v30].pvBuffer;
    if ( !pvBuffer )
      break;
    Handle = KsppAnalyzeContainerName(pvBuffer, v73, v72, pbData, (__int64)&v61 + 4);
    if ( Handle )
    {
      WppTraceIndent(v32, 2);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          212,
          (unsigned int)&WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids,
          (_DWORD)WPP_pszIndent,
          Handle);
      }
      goto LABEL_74;
    }
    if ( !HIDWORD(v61) )
    {
      WppTraceIndent(v32, 2);
      v45 = 2148073494LL;
      Handle = -2146893802;
      v46 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v47 = 213;
        goto LABEL_86;
      }
      goto LABEL_74;
    }
    v33 = StringCchCopyW((unsigned __int16 *)v11, 0x104u, v72);
    if ( v33 < 0 )
    {
      WppTraceIndent(pvBuffer, 2);
      v41 = HR_Remap((unsigned int)v33);
      Handle = v41;
      v42 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_74;
      }
      v43 = 214;
LABEL_73:
      WPP_SF_sd(v42[2], v43, (unsigned int)&WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids, (_DWORD)WPP_pszIndent, v41);
      goto LABEL_74;
    }
    if ( v62 )
    {
      v34 = StringCchCopyW((unsigned __int16 *)(v11 + 520), 0x104u, v73);
      if ( v34 < 0 )
      {
        WppTraceIndent(pvBuffer, 2);
        v41 = HR_Remap((unsigned int)v34);
        Handle = v41;
        v42 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_74;
        }
        v43 = 215;
        goto LABEL_73;
      }
    }
    v22 = 1;
    --pParameterList->cBuffers;
LABEL_58:
    if ( ++v30 >= a4->cBuffers )
      goto LABEL_59;
  }
  WppTraceIndent(pvBuffer, 2);
  Handle = -2146893785;
  v46 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v47 = 211;
    v45 = 2148073511LL;
LABEL_86:
    WPP_SF_d(v46[2], v47, &WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids, v45);
  }
LABEL_74:
  v44 = v57;
LABEL_75:
  CspFreeH(v44);
LABEL_76:
  v28 = pParameterList;
  if ( pParameterList )
LABEL_39:
    CspFreeH(v28);
LABEL_40:
  if ( hKey )
    NCryptDeleteKey(hKey, 0);
  if ( v11 )
    CspFreeH(v11);
  v70[0] = &Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Close(v70);
  return Handle;
}

```

## disassembly

```asm
0x1800232ec  push    rbp
0x1800232ee  push    rbx
0x1800232ef  push    rdi
0x1800232f0  push    r12
0x1800232f2  push    r13
0x1800232f4  push    r14
0x1800232f6  push    r15
0x1800232f8  lea     rbp, [rsp-220h]
0x180023300  sub     rsp, 320h
0x180023307  mov     rax, cs:__security_cookie
0x18002330e  xor     rax, rsp
0x180023311  mov     [rbp+250h+var_40], rax
0x180023318  mov     r12, r9
0x18002331b  mov     [rbp+250h+pszBlobType], r8
0x18002331f  mov     [rbp+250h+hImportKey], rdx
0x180023323  mov     rbx, rcx
0x180023326  mov     rax, [rbp+250h+arg_20]
0x18002332d  mov     [rbp+250h+var_2A8], rax
0x180023331  mov     rax, [rbp+250h+arg_28]
0x180023338  mov     [rbp+250h+var_2D0], rax
0x18002333c  xor     edi, edi
0x18002333e  mov     [rsp+350h+pParameterList], rdi
0x180023343  mov     dword ptr [rsp+350h+var_2D8], edi
0x180023347  mov     [rsp+350h+var_300], edi
0x18002334b  mov     dword ptr [rsp+350h+var_2F0], edi
0x18002334f  mov     [rsp+350h+hKey], rdi
0x180023354  lea     r13d, [rdi+3]
0x180023358  mov     dword ptr [rsp+350h+pbInput], r13d
0x18002335d  xor     edx, edx; Val
0x18002335f  mov     r8d, 208h; Size
0x180023365  lea     rcx, [rbp+250h+var_250]; void *
0x180023369  call    memset_0
0x18002336e  xor     edx, edx; Val
0x180023370  lea     r8d, [rdi+50h]; Size
0x180023374  lea     rcx, [rbp+250h+var_2A0]; void *
0x180023378  call    memset_0
0x18002337d  mov     [rsp+350h+var_2E8], edi
0x180023381  mov     dword ptr [rsp+350h+var_2F0+4], edi
0x180023385  lea     rax, ??_7?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable'
0x18002338c  mov     [rbp+250h+var_2B8], rax
0x180023390  mov     [rbp+250h+var_2B0], rdi
0x180023394  mov     r15d, [rbp+250h+arg_38]
0x18002339b  test    r15d, 0FFFFFBBFh
0x1800233a2  jz      loc_180023443
0x1800233a8  mov     r14d, edi
0x1800233ab  lea     edx, [rdi+2]
0x1800233ae  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800233b3  lea     rdi, WPP_GLOBAL_Control
0x1800233ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1800233c1  cmp     rcx, rdi
0x1800233c4  jz      short loc_1800233F3
0x1800233c6  test    byte ptr [rcx+1Ch], 1
0x1800233ca  jz      short loc_1800233F3
0x1800233cc  cmp     byte ptr [rcx+19h], 2
0x1800233d0  jb      short loc_1800233F3
0x1800233d2  mov     edx, 0CCh
0x1800233d7  mov     dword ptr [rsp+350h+phKey], r15d
0x1800233dc  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x1800233e3  lea     r8, WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids
0x1800233ea  mov     rcx, [rcx+10h]
0x1800233ee  call    WPP_SF_sd
0x1800233f3  mov     edx, 2
0x1800233f8  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800233fd  mov     ebx, 80090009h
0x180023402  mov     rcx, cs:WPP_GLOBAL_Control
0x180023409  cmp     rcx, rdi
0x18002340c  jz      loc_180023675
0x180023412  test    byte ptr [rcx+1Ch], 1
0x180023416  jz      loc_180023675
0x18002341c  cmp     byte ptr [rcx+19h], 2
0x180023420  jb      loc_180023675
0x180023426  mov     edx, 0CDh
0x18002342b  mov     r9d, ebx
0x18002342e  lea     r8, WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids
0x180023435  mov     rcx, [rcx+10h]
0x180023439  call    WPP_SF_d
0x18002343e  jmp     loc_180023675
0x180023443  mov     ecx, 4C0h; size
0x180023448  call    MIDL_user_allocate
0x18002344d  mov     r14, rax
0x180023450  test    rax, rax
0x180023453  jnz     short loc_1800234A6
0x180023455  mov     ebx, 8009000Eh
0x18002345a  lea     rdi, WPP_GLOBAL_Control
0x180023461  mov     rcx, cs:WPP_GLOBAL_Control
0x180023468  cmp     rcx, rdi
0x18002346b  jz      loc_180023675
0x180023471  test    byte ptr [rcx+1Ch], 1
0x180023475  jz      loc_180023675
0x18002347b  cmp     byte ptr [rcx+19h], 2
0x18002347f  jb      loc_180023675
0x180023485  mov     edx, 0CEh
0x18002348a  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180023491  lea     r8, WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids
0x180023498  mov     rcx, [rcx+10h]
0x18002349c  call    WPP_SF_s
0x1800234a1  jmp     loc_180023675
0x1800234a6  xor     edx, edx; Val
0x1800234a8  mov     r8d, 4C0h; Size
0x1800234ae  mov     rcx, r14; void *
0x1800234b1  call    memset_0
0x1800234b6  lea     r8, [rsp+350h+pParameterList]
0x1800234bb  mov     edx, r13d
0x1800234be  mov     rcx, rbx
0x1800234c1  call    HtGetHandle
0x1800234c6  mov     ebx, eax
0x1800234c8  test    eax, eax
0x1800234ca  jz      short loc_180023526
0x1800234cc  mov     edx, 2
0x1800234d1  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800234d6  lea     rdi, WPP_GLOBAL_Control
0x1800234dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800234e4  cmp     rcx, rdi
0x1800234e7  jz      loc_180023675
0x1800234ed  test    byte ptr [rcx+1Ch], 1
0x1800234f1  jz      loc_180023675
0x1800234f7  cmp     byte ptr [rcx+19h], 2
0x1800234fb  jb      loc_180023675
0x180023501  mov     edx, 0CFh
0x180023506  mov     dword ptr [rsp+350h+phKey], ebx
0x18002350a  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180023511  lea     r8, WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids
0x180023518  mov     rcx, [rcx+10h]
0x18002351c  call    WPP_SF_sd
0x180023521  jmp     loc_180023675
0x180023526  mov     r13, [rsp+350h+pParameterList]
0x18002352b  lea     rcx, [r13+10h]
0x18002352f  call    KspEnterCriticalSection
0x180023534  mov     ebx, eax
0x180023536  test    eax, eax
0x180023538  jz      short loc_180023576
0x18002353a  mov     edx, 2
0x18002353f  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180023544  lea     rdi, WPP_GLOBAL_Control
0x18002354b  mov     rcx, cs:WPP_GLOBAL_Control
0x180023552  cmp     rcx, rdi
0x180023555  jz      loc_180023675
0x18002355b  test    byte ptr [rcx+1Ch], 1
0x18002355f  jz      loc_180023675
0x180023565  cmp     byte ptr [rcx+19h], 2
0x180023569  jb      loc_180023675
0x18002356f  mov     edx, 0D0h
0x180023574  jmp     short loc_180023506
0x180023576  mov     [rsp+350h+pParameterList], 0
0x18002357f  mov     [rsp+350h+var_310], 0
0x180023588  xor     ebx, ebx
0x18002358a  lea     rdx, [r13+10h]
0x18002358e  lea     rcx, [rbp+250h+var_2B8]
0x180023592  call    ?Attach@?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@QEAAXPEAU_RTL_CRITICAL_SECTION@@@Z; Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Attach(_RTL_CRITICAL_SECTION *)
0x180023597  mov     edi, r15d
0x18002359a  and     edi, 400h
0x1800235a0  mov     [rsp+350h+var_2E4], edi
0x1800235a4  mov     eax, ebx
0x1800235a6  setz    al
0x1800235a9  mov     [rsp+350h+var_2DC], eax
0x1800235ad  test    r12, r12
0x1800235b0  jz      loc_1800237C1
0x1800235b6  lea     ecx, [rbx+10h]; size
0x1800235b9  call    MIDL_user_allocate
0x1800235be  mov     rdi, rax
0x1800235c1  mov     [rsp+350h+pParameterList], rax
0x1800235c6  test    rax, rax
0x1800235c9  jnz     short loc_180023601
0x1800235cb  mov     ebx, 8009000Eh
0x1800235d0  lea     rdi, WPP_GLOBAL_Control
0x1800235d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800235de  cmp     rcx, rdi
0x1800235e1  jz      loc_180023675
0x1800235e7  test    byte ptr [rcx+1Ch], 1
0x1800235eb  jz      loc_180023675
0x1800235f1  cmp     byte ptr [rcx+19h], 2
0x1800235f5  jb      short loc_180023675
0x1800235f7  mov     edx, 0D1h
0x1800235fc  jmp     loc_18002348A
0x180023601  mov     eax, [r12]
0x180023605  mov     [rdi], eax
0x180023607  mov     eax, [r12+4]
0x18002360c  mov     [rdi+4], eax
0x18002360f  mov     ecx, [r12+4]
0x180023614  shl     rcx, 4; size
0x180023618  call    MIDL_user_allocate
0x18002361d  mov     [rsp+350h+var_310], rax
0x180023622  test    rax, rax
0x180023625  jnz     loc_1800236CD
0x18002362b  mov     ebx, 8009000Eh
0x180023630  lea     rdi, WPP_GLOBAL_Control
0x180023637  mov     rcx, cs:WPP_GLOBAL_Control
0x18002363e  cmp     rcx, rdi
0x180023641  jz      short loc_18002366B
0x180023643  test    byte ptr [rcx+1Ch], 1
0x180023647  jz      short loc_18002366B
0x180023649  cmp     byte ptr [rcx+19h], 2
0x18002364d  jb      short loc_18002366B
0x18002364f  mov     edx, 0D2h
0x180023654  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18002365b  lea     r8, WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids
0x180023662  mov     rcx, [rcx+10h]
0x180023666  call    WPP_SF_s
0x18002366b  mov     rcx, [rsp+350h+pParameterList]
0x180023670  call    CspFreeH
0x180023675  mov     rcx, [rsp+350h+hKey]; hKey
0x18002367a  test    rcx, rcx
0x18002367d  jz      short loc_180023687
0x18002367f  xor     edx, edx; dwFlags
0x180023681  call    cs:__imp_NCryptDeleteKey
0x180023687  test    r14, r14
0x18002368a  jz      short loc_180023695
0x18002368c  mov     rcx, r14
0x18002368f  call    CspFreeH
0x180023694  nop
0x180023695  lea     rax, ??_7?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable'
0x18002369c  mov     [rbp+250h+var_2B8], rax
0x1800236a0  lea     rcx, [rbp+250h+var_2B8]
0x1800236a4  call    ?Close@?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Close(void)
0x1800236a9  mov     eax, ebx
0x1800236ab  mov     rcx, [rbp+250h+var_40]
0x1800236b2  xor     rcx, rsp; StackCookie
0x1800236b5  call    __security_check_cookie
0x1800236ba  add     rsp, 320h
0x1800236c1  pop     r15
0x1800236c3  pop     r14
0x1800236c5  pop     r13
0x1800236c7  pop     r12
0x1800236c9  pop     rdi
0x1800236ca  pop     rbx
0x1800236cb  pop     rbp
0x1800236cc  retn
0x1800236cd  mov     [rdi+8], rax
0x1800236d1  xor     edi, edi
0x1800236d3  cmp     [r12+4], ebx
0x1800236d8  jbe     loc_1800237BD
0x1800236de  mov     edx, edi
0x1800236e0  add     rdx, rdx
0x1800236e3  mov     r8, [r12+8]
0x1800236e8  cmp     dword ptr [r8+rdx*8+4], 2Dh ; '-'
0x1800236ee  jnz     loc_180023792
0x1800236f4  cmp     dword ptr [r8+rdx*8], 0
0x1800236f9  jz      loc_1800239CC
0x1800236ff  mov     rcx, [r8+rdx*8+8]; unsigned __int16 *
0x180023704  test    rcx, rcx
0x180023707  jz      loc_1800239CC
0x18002370d  lea     rax, [rsp+350h+var_2F0+4]
0x180023712  mov     qword ptr [rsp+350h+cbData], rax; __int64
0x180023717  lea     rax, [rbp+250h+var_2A0]
0x18002371b  mov     [rsp+350h+phKey], rax; unsigned __int16 *
0x180023720  lea     r9, [rsp+350h+var_2E8]
0x180023725  lea     rdx, [rbp+250h+var_250]; unsigned __int16 *
0x180023729  call    KsppAnalyzeContainerName
0x18002372e  mov     ebx, eax
0x180023730  test    eax, eax
0x180023732  jnz     loc_180023989
0x180023738  cmp     dword ptr [rsp+350h+var_2F0+4], eax
0x18002373c  jz      loc_180023935
0x180023742  lea     r8, [rbp+250h+var_2A0]; unsigned __int16 *
0x180023746  mov     edx, 104h; unsigned __int64
0x18002374b  mov     rcx, r14; unsigned __int16 *
0x18002374e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180023753  mov     ebx, eax
0x180023755  test    eax, eax
0x180023757  js      loc_1800238FC
0x18002375d  cmp     [rsp+350h+var_2E8], 0
0x180023762  jz      short loc_180023783
0x180023764  lea     rcx, [r14+208h]; unsigned __int16 *
0x18002376b  lea     r8, [rbp+250h+var_250]; unsigned __int16 *
0x18002376f  mov     edx, 104h; unsigned __int64
0x180023774  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180023779  mov     ebx, eax
0x18002377b  test    eax, eax
0x18002377d  js      loc_18002388D
0x180023783  mov     ebx, 1
0x180023788  mov     rax, [rsp+350h+pParameterList]
0x18002378d  dec     dword ptr [rax+4]
0x180023790  jmp     short loc_1800237B0
0x180023792  lea     ecx, [rdi-1]
0x180023795  test    ebx, ebx
0x180023797  cmovz   ecx, edi
0x18002379a  add     rcx, rcx
0x18002379d  mov     rax, [rsp+350h+pParameterList]
0x1800237a2  mov     rax, [rax+8]
0x1800237a6  movups  xmm0, xmmword ptr [r8+rdx*8]
0x1800237ab  movdqu  xmmword ptr [rax+rcx*8], xmm0
0x1800237b0  inc     edi
0x1800237b2  cmp     edi, [r12+4]
0x1800237b7  jb      loc_1800236DE
0x1800237bd  mov     edi, [rsp+350h+var_2E4]
0x1800237c1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_SmartCardKspPqcSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_SmartCardKspPqcSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SmartCardKspPqcSupport> `wil::Feature<__WilFeatureTraits_Feature_Servicing_SmartCardKspPqcSupport>::GetImpl(void)'::`2'::impl
0x1800237c8  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_SmartCardKspPqcSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SmartCardKspPqcSupport>::__private_IsEnabled(void)
0x1800237cd  mov     r10, [rbp+250h+pszBlobType]
0x1800237d1  test    al, al
0x1800237d3  jz      short loc_1800237DC
0x1800237d5  mov     [r14+498h], r10
0x1800237dc  mov     rdx, [rbp+250h+var_2D0]
0x1800237e0  test    ebx, ebx
0x1800237e2  jz      loc_180023B86
0x1800237e8  mov     eax, r15d
0x1800237eb  bts     eax, 0Ah
0x1800237ef  mov     rcx, [r13+0]
0x1800237f3  mov     [rsp+350h+dwFlags], eax; dwFlags
0x1800237f7  mov     eax, [rbp+250h+arg_30]
0x1800237fd  mov     [rsp+350h+cbData], eax; cbData
  ... truncated ...
```
