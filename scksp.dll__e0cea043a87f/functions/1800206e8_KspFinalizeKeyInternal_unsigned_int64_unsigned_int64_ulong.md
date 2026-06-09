# KspFinalizeKeyInternal(unsigned __int64,unsigned __int64,ulong)

- ea: `0x1800206e8`
- end: `0x180020ecb`
- name: `?KspFinalizeKeyInternal@@YAJ_K0K@Z`
- size: `2019`
- prototype: `__int64 __fastcall(unsigned __int64, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18002ad50`

## callees

- `0x18000a3c8`
- `0x18000a408`
- `0x18000d2a8`
- `0x180011fd8`
- `0x1800122b4`
- `0x1800135dc`
- `0x180013aac`
- `0x180016adc`
- `0x18001b0c4`
- `0x1800206e8`
- `0x18003af5c`
- `0x18003bebc`

## import_xrefs

- `ncrypt!NCryptDeleteKey` at `0x180020e95`
- `ncrypt!NCryptDeleteKey` at `0x180020e95`
- `ncrypt!NCryptFinalizeKey` at `0x180020dcb`
- `ncrypt!NCryptFinalizeKey` at `0x180020dcb`
- `ncrypt!NCryptCreatePersistedKey` at `0x1800209ab`
- `ncrypt!NCryptCreatePersistedKey` at `0x1800209ab`
- `ncrypt!NCryptSetProperty` at `0x180020a2c`
- `ncrypt!NCryptSetProperty` at `0x180020b00`
- `ncrypt!NCryptSetProperty` at `0x180020b71`
- `ncrypt!NCryptSetProperty` at `0x180020c06`
- `ncrypt!NCryptSetProperty` at `0x180020c64`
- `ncrypt!NCryptSetProperty` at `0x180020cb6`
- `ncrypt!NCryptSetProperty` at `0x180020d2c`
- `ncrypt!NCryptSetProperty` at `0x180020d7e`
- `ncrypt!NCryptSetProperty` at `0x180020a2c`
- `ncrypt!NCryptSetProperty` at `0x180020b00`
- `ncrypt!NCryptSetProperty` at `0x180020b71`
- `ncrypt!NCryptSetProperty` at `0x180020c06`
- `ncrypt!NCryptSetProperty` at `0x180020c64`
- `ncrypt!NCryptSetProperty` at `0x180020cb6`
- `ncrypt!NCryptSetProperty` at `0x180020d2c`
- `ncrypt!NCryptSetProperty` at `0x180020d7e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall KspFinalizeKeyInternal(__int64 a1, __int64 a2, int a3)
{
  PVOID v5; // rcx
  unsigned int Handle; // esi
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // r9
  __int64 v10; // rcx
  _QWORD *v11; // rcx
  int v12; // edx
  _QWORD *v13; // r15
  __int64 v14; // rcx
  __int64 v15; // rcx
  char IsEnabled; // al
  __int64 v17; // rcx
  __int64 v18; // rdi
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // rcx
  BYTE *v23; // r8
  __int64 v24; // r9
  __int64 v25; // rcx
  __int64 v26; // rcx
  int v27; // eax
  int v28; // ecx
  DWORD v29; // r9d
  BYTE *v30; // r8
  __int64 v31; // rcx
  __int64 v32; // rcx
  __int64 v33; // rcx
  DWORD v34; // r9d
  BYTE *v35; // r8
  __int64 v36; // rcx
  __int64 v37; // rcx
  __int64 v38; // rcx
  __int64 v39; // rcx
  _QWORD *v41; // [rsp+30h] [rbp-30h] BYREF
  __int64 v42; // [rsp+38h] [rbp-28h] BYREF
  LPCWSTR pszAlgId; // [rsp+40h] [rbp-20h] BYREF
  _QWORD v44[3]; // [rsp+48h] [rbp-18h] BYREF
  NCRYPT_KEY_HANDLE phKey; // [rsp+A8h] [rbp+48h] BYREF

  v41 = 0;
  v42 = 0;
  pszAlgId = 0;
  phKey = 0;
  v44[0] = &Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable';
  v44[1] = 0;
  if ( (a3 & 0xFFFFFFBF) != 0 )
  {
    WppTraceIndent(a1, 2);
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        103,
        (unsigned int)&WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids,
        (_DWORD)WPP_pszIndent,
        a3);
    }
    WppTraceIndent(v5, 2);
    Handle = -2146893815;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_111;
    }
    v8 = 104;
    v9 = 2148073481LL;
    goto LABEL_10;
  }
  Handle = HtGetHandle(a1, 3, &v41);
  if ( Handle )
  {
    WppTraceIndent(v10, 2);
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v12 = 105;
LABEL_110:
      WPP_SF_sd(
        v11[2],
        v12,
        (unsigned int)&WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids,
        (_DWORD)WPP_pszIndent,
        Handle);
      goto LABEL_111;
    }
    goto LABEL_111;
  }
  v13 = v41;
  Handle = KspEnterCriticalSection(v41 + 2);
  if ( !Handle )
  {
    Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Attach(v44, v13 + 2);
    Handle = HtGetHandle(a2, 2, &v42);
    if ( Handle )
    {
      WppTraceIndent(v15, 2);
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v12 = 107;
        goto LABEL_110;
      }
      goto LABEL_111;
    }
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SmartCardKspPqcSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_SmartCardKspPqcSupport>::GetImpl'::`2'::impl);
    v18 = v42;
    if ( IsEnabled && (unsigned int)(*(_DWORD *)(v42 + 1040) - 64) <= 1 )
    {
      WppTraceIndent(v17, 2);
      v9 = 2148073483LL;
      Handle = -2146893813;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_111;
      }
      v8 = 108;
      goto LABEL_10;
    }
    if ( *(_WORD *)v42 )
    {
      Handle = KsppFinalizeKey(v13, v42, a3);
      if ( Handle )
      {
        WppTraceIndent(v39, 2);
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v12 = 121;
          goto LABEL_110;
        }
      }
      goto LABEL_111;
    }
    Handle = KsppTranslateKeySpecToAlgorithm(*(unsigned int *)(v42 + 1040), &pszAlgId);
    if ( Handle )
    {
      WppTraceIndent(v19, 2);
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v12 = 109;
        goto LABEL_110;
      }
      goto LABEL_111;
    }
    Handle = NCryptCreatePersistedKey(*(_QWORD *)(*v13 + 224LL), &phKey, pszAlgId, 0, 0, 0);
    if ( Handle )
    {
      WppTraceIndent(v20, 2);
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v12 = 110;
        goto LABEL_110;
      }
      goto LABEL_111;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SmartCardKspPqcSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_SmartCardKspPqcSupport>::GetImpl'::`2'::impl) )
    {
      if ( *(_DWORD *)(v18 + 1052) )
      {
        Handle = NCryptSetProperty(phKey, L"Length", (PBYTE)(v18 + 1044), 4u, 0);
        if ( Handle )
        {
          WppTraceIndent(v21, 2);
          v11 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v12 = 111;
            goto LABEL_110;
          }
          goto LABEL_111;
        }
      }
      else if ( (unsigned int)IsPqcKey(*(unsigned int *)(v18 + 1040)) )
      {
        v23 = *(BYTE **)(v18 + 1208);
        if ( !v23 )
        {
          WppTraceIndent(v22, 2);
          v9 = 2148073483LL;
          Handle = -2146893813;
          v7 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_111;
          }
          v8 = 112;
LABEL_10:
          WPP_SF_d(v7[2], v8, &WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids, v9);
          goto LABEL_111;
        }
        v24 = -1;
        do
          ++v24;
        while ( *(_WORD *)&v23[2 * v24] );
        Handle = NCryptSetProperty(phKey, L"ParameterSetName", v23, 2 * v24 + 2, 0);
        if ( Handle )
        {
          WppTraceIndent(v25, 2);
          v11 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v12 = 113;
            goto LABEL_110;
          }
          goto LABEL_111;
        }
      }
    }
    else if ( *(_DWORD *)(v18 + 1052) )
    {
      Handle = NCryptSetProperty(phKey, L"Length", (PBYTE)(v18 + 1044), 4u, 0);
      if ( Handle )
      {
        WppTraceIndent(v26, 2);
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v12 = 114;
          goto LABEL_110;
        }
        goto LABEL_111;
      }
    }
    if ( *(_QWORD *)(v18 + 1160) )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SmartCardKspPqcSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_SmartCardKspPqcSupport>::GetImpl'::`2'::impl) )
      {
        v27 = IsPqcKey(*(unsigned int *)(v18 + 1040));
        v29 = *(_DWORD *)(v18 + 1168);
        v30 = *(BYTE **)(v18 + 1160);
        if ( v27 )
        {
          Handle = NCryptSetProperty(phKey, *(LPCWSTR *)(v18 + 1176), v30, v29, 0);
          if ( Handle )
          {
            WppTraceIndent(v31, 2);
            v11 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v12 = 115;
              goto LABEL_110;
            }
            goto LABEL_111;
          }
        }
        else if ( (unsigned int)(v28 - 1) <= 1 )
        {
          Handle = NCryptSetProperty(phKey, L"CAPIPRIVATEBLOB", v30, v29, 0);
          if ( Handle )
          {
            WppTraceIndent(v33, 2);
            v11 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v12 = 116;
              goto LABEL_110;
            }
            goto LABEL_111;
          }
        }
        else
        {
          Handle = NCryptSetProperty(phKey, L"ECCPRIVATEBLOB", v30, v29, 0);
          if ( Handle )
          {
            WppTraceIndent(v32, 2);
            v11 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v12 = 117;
              goto LABEL_110;
            }
            goto LABEL_111;
          }
        }
      }
      else
      {
        v34 = *(_DWORD *)(v18 + 1168);
        v35 = *(BYTE **)(v18 + 1160);
        if ( (unsigned int)(*(_DWORD *)(v18 + 1040) - 1) <= 1 )
        {
          Handle = NCryptSetProperty(phKey, L"CAPIPRIVATEBLOB", v35, v34, 0);
          if ( Handle )
          {
            WppTraceIndent(v37, 2);
            v11 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v12 = 118;
              goto LABEL_110;
            }
            goto LABEL_111;
          }
        }
        else
        {
          Handle = NCryptSetProperty(phKey, L"ECCPRIVATEBLOB", v35, v34, 0);
          if ( Handle )
          {
            WppTraceIndent(v36, 2);
            v11 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v12 = 119;
              goto LABEL_110;
            }
            goto LABEL_111;
          }
        }
      }
    }
    Handle = NCryptFinalizeKey(phKey, 0);
    if ( !Handle )
    {
      *(_DWORD *)(v18 + 1048) = 1;
      *(_DWORD *)(v18 + 1056) = 0;
      *(_QWORD *)(v18 + 1144) = phKey;
      phKey = 0;
      goto LABEL_113;
    }
    WppTraceIndent(v38, 2);
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v12 = 120;
      goto LABEL_110;
    }
    goto LABEL_111;
  }
  WppTraceIndent(v14, 2);
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v12 = 106;
    goto LABEL_110;
  }
LABEL_111:
  if ( phKey )
    NCryptDeleteKey(phKey, 0);
LABEL_113:
  v44[0] = &Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Close(v44);
  return Handle;
}

```

## disassembly

```asm
0x1800206e8  mov     [rsp-28h+arg_0], rbx
0x1800206ed  mov     [rsp-28h+arg_8], rsi
0x1800206f2  push    rbp
0x1800206f3  push    rdi
0x1800206f4  push    r12
0x1800206f6  push    r13
0x1800206f8  push    r15
0x1800206fa  mov     rbp, rsp
0x1800206fd  sub     rsp, 60h
0x180020701  mov     r12d, r8d
0x180020704  mov     rdi, rdx
0x180020707  xor     r13d, r13d
0x18002070a  mov     [rbp+var_30], r13
0x18002070e  mov     [rbp+var_28], r13
0x180020712  mov     [rbp+pszAlgId], r13
0x180020716  mov     [rbp+phKey], r13
0x18002071a  lea     rax, ??_7?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable'
0x180020721  mov     [rbp+var_18], rax
0x180020725  mov     [rbp+var_10], r13
0x180020729  test    r8d, 0FFFFFFBFh
0x180020730  jz      loc_1800207CA
0x180020736  lea     ebx, [r13+2]
0x18002073a  mov     edx, ebx
0x18002073c  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180020741  lea     rdi, WPP_GLOBAL_Control
0x180020748  mov     rcx, cs:WPP_GLOBAL_Control
0x18002074f  cmp     rcx, rdi
0x180020752  jz      short loc_18002077E
0x180020754  test    byte ptr [rcx+1Ch], 1
0x180020758  jz      short loc_18002077E
0x18002075a  cmp     [rcx+19h], bl
0x18002075d  jb      short loc_18002077E
0x18002075f  lea     edx, [rbx+65h]
0x180020762  mov     [rsp+60h+dwLegacyKeySpec], r12d
0x180020767  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18002076e  lea     r8, WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids
0x180020775  mov     rcx, [rcx+10h]
0x180020779  call    WPP_SF_sd
0x18002077e  mov     edx, ebx
0x180020780  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180020785  mov     esi, 80090009h
0x18002078a  mov     rcx, cs:WPP_GLOBAL_Control
0x180020791  cmp     rcx, rdi
0x180020794  jz      loc_180020E8A
0x18002079a  test    byte ptr [rcx+1Ch], 1
0x18002079e  jz      loc_180020E8A
0x1800207a4  cmp     [rcx+19h], bl
0x1800207a7  jb      loc_180020E8A
0x1800207ad  mov     edx, 68h ; 'h'
0x1800207b2  mov     r9d, esi
0x1800207b5  lea     r8, WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids
0x1800207bc  mov     rcx, [rcx+10h]
0x1800207c0  call    WPP_SF_d
0x1800207c5  jmp     loc_180020E8A
0x1800207ca  lea     r8, [rbp+var_30]
0x1800207ce  mov     edx, 3
0x1800207d3  call    HtGetHandle
0x1800207d8  mov     esi, eax
0x1800207da  test    eax, eax
0x1800207dc  jz      short loc_18002081C
0x1800207de  mov     ebx, 2
0x1800207e3  mov     edx, ebx
0x1800207e5  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800207ea  lea     rdi, WPP_GLOBAL_Control
0x1800207f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800207f8  cmp     rcx, rdi
0x1800207fb  jz      loc_180020E8A
0x180020801  test    byte ptr [rcx+1Ch], 1
0x180020805  jz      loc_180020E8A
0x18002080b  cmp     [rcx+19h], bl
0x18002080e  jb      loc_180020E8A
0x180020814  lea     edx, [rbx+67h]
0x180020817  jmp     loc_180020E6F
0x18002081c  mov     r15, [rbp+var_30]
0x180020820  lea     rcx, [r15+10h]
0x180020824  call    KspEnterCriticalSection
0x180020829  mov     esi, eax
0x18002082b  test    eax, eax
0x18002082d  jz      short loc_18002086D
0x18002082f  mov     ebx, 2
0x180020834  mov     edx, ebx
0x180020836  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002083b  lea     rdi, WPP_GLOBAL_Control
0x180020842  mov     rcx, cs:WPP_GLOBAL_Control
0x180020849  cmp     rcx, rdi
0x18002084c  jz      loc_180020E8A
0x180020852  test    byte ptr [rcx+1Ch], 1
0x180020856  jz      loc_180020E8A
0x18002085c  cmp     [rcx+19h], bl
0x18002085f  jb      loc_180020E8A
0x180020865  lea     edx, [rbx+68h]
0x180020868  jmp     loc_180020E6F
0x18002086d  lea     rdx, [r15+10h]
0x180020871  lea     rcx, [rbp+var_18]
0x180020875  call    ?Attach@?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@QEAAXPEAU_RTL_CRITICAL_SECTION@@@Z; Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Attach(_RTL_CRITICAL_SECTION *)
0x18002087a  lea     r8, [rbp+var_28]
0x18002087e  mov     ebx, 2
0x180020883  mov     edx, ebx
0x180020885  mov     rcx, rdi
0x180020888  call    HtGetHandle
0x18002088d  mov     esi, eax
0x18002088f  test    eax, eax
0x180020891  jz      short loc_1800208CC
0x180020893  mov     edx, ebx
0x180020895  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002089a  lea     rdi, WPP_GLOBAL_Control
0x1800208a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800208a8  cmp     rcx, rdi
0x1800208ab  jz      loc_180020E8A
0x1800208b1  test    byte ptr [rcx+1Ch], 1
0x1800208b5  jz      loc_180020E8A
0x1800208bb  cmp     [rcx+19h], bl
0x1800208be  jb      loc_180020E8A
0x1800208c4  lea     edx, [rbx+69h]
0x1800208c7  jmp     loc_180020E6F
0x1800208cc  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_SmartCardKspPqcSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_SmartCardKspPqcSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SmartCardKspPqcSupport> `wil::Feature<__WilFeatureTraits_Feature_Servicing_SmartCardKspPqcSupport>::GetImpl(void)'::`2'::impl
0x1800208d3  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_SmartCardKspPqcSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SmartCardKspPqcSupport>::__private_IsEnabled(void)
0x1800208d8  mov     rdi, [rbp+var_28]
0x1800208dc  test    al, al
0x1800208de  jz      short loc_180020932
0x1800208e0  mov     eax, [rdi+410h]
0x1800208e6  sub     eax, 40h ; '@'
0x1800208e9  cmp     eax, 1
0x1800208ec  ja      short loc_180020932
0x1800208ee  mov     edx, ebx
0x1800208f0  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800208f5  mov     r9d, 8009000Bh
0x1800208fb  mov     esi, r9d
0x1800208fe  lea     rdi, WPP_GLOBAL_Control
0x180020905  mov     rcx, cs:WPP_GLOBAL_Control
0x18002090c  cmp     rcx, rdi
0x18002090f  jz      loc_180020E8A
0x180020915  test    byte ptr [rcx+1Ch], 1
0x180020919  jz      loc_180020E8A
0x18002091f  cmp     [rcx+19h], bl
0x180020922  jb      loc_180020E8A
0x180020928  mov     edx, 6Ch ; 'l'
0x18002092d  jmp     loc_1800207B5
0x180020932  cmp     r13w, [rdi]
0x180020936  jnz     loc_180020E31
0x18002093c  lea     rdx, [rbp+pszAlgId]
0x180020940  mov     ecx, [rdi+410h]
0x180020946  call    KsppTranslateKeySpecToAlgorithm
0x18002094b  mov     esi, eax
0x18002094d  test    eax, eax
0x18002094f  jz      short loc_18002098C
0x180020951  mov     edx, ebx
0x180020953  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180020958  lea     rdi, WPP_GLOBAL_Control
0x18002095f  mov     rcx, cs:WPP_GLOBAL_Control
0x180020966  cmp     rcx, rdi
0x180020969  jz      loc_180020E8A
0x18002096f  test    byte ptr [rcx+1Ch], 1
0x180020973  jz      loc_180020E8A
0x180020979  cmp     [rcx+19h], bl
0x18002097c  jb      loc_180020E8A
0x180020982  mov     edx, 6Dh ; 'm'
0x180020987  jmp     loc_180020E6F
0x18002098c  mov     rcx, [r15]
0x18002098f  mov     [rsp+60h+dwFlags], r13d; dwFlags
0x180020994  mov     [rsp+60h+dwLegacyKeySpec], r13d; dwLegacyKeySpec
0x180020999  xor     r9d, r9d; pszKeyName
0x18002099c  mov     r8, [rbp+pszAlgId]; pszAlgId
0x1800209a0  lea     rdx, [rbp+phKey]; phKey
0x1800209a4  mov     rcx, [rcx+0E0h]; hProvider
0x1800209ab  call    cs:__imp_NCryptCreatePersistedKey
0x1800209b1  mov     esi, eax
0x1800209b3  test    eax, eax
0x1800209b5  jz      short loc_1800209F2
0x1800209b7  mov     edx, ebx
0x1800209b9  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800209be  lea     rdi, WPP_GLOBAL_Control
0x1800209c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800209cc  cmp     rcx, rdi
0x1800209cf  jz      loc_180020E8A
0x1800209d5  test    byte ptr [rcx+1Ch], 1
0x1800209d9  jz      loc_180020E8A
0x1800209df  cmp     [rcx+19h], bl
0x1800209e2  jb      loc_180020E8A
0x1800209e8  mov     edx, 6Eh ; 'n'
0x1800209ed  jmp     loc_180020E6F
0x1800209f2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_SmartCardKspPqcSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_SmartCardKspPqcSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SmartCardKspPqcSupport> `wil::Feature<__WilFeatureTraits_Feature_Servicing_SmartCardKspPqcSupport>::GetImpl(void)'::`2'::impl
0x1800209f9  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_SmartCardKspPqcSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SmartCardKspPqcSupport>::__private_IsEnabled(void)
0x1800209fe  test    al, al
0x180020a00  jz      loc_180020B4B
0x180020a06  cmp     [rdi+41Ch], r13d
0x180020a0d  jz      short loc_180020A77
0x180020a0f  lea     r8, [rdi+414h]; pbInput
0x180020a16  mov     [rsp+60h+dwLegacyKeySpec], r13d; dwFlags
0x180020a1b  mov     r9d, 4; cbInput
0x180020a21  lea     rdx, aLength; "Length"
0x180020a28  mov     rcx, [rbp+phKey]; hObject
0x180020a2c  call    cs:__imp_NCryptSetProperty
0x180020a32  mov     esi, eax
0x180020a34  test    eax, eax
0x180020a36  jz      loc_180020BB8
0x180020a3c  mov     edx, ebx
0x180020a3e  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180020a43  lea     rdi, WPP_GLOBAL_Control
0x180020a4a  mov     rcx, cs:WPP_GLOBAL_Control
0x180020a51  cmp     rcx, rdi
0x180020a54  jz      loc_180020E8A
0x180020a5a  test    byte ptr [rcx+1Ch], 1
0x180020a5e  jz      loc_180020E8A
0x180020a64  cmp     [rcx+19h], bl
0x180020a67  jb      loc_180020E8A
0x180020a6d  mov     edx, 6Fh ; 'o'
0x180020a72  jmp     loc_180020E6F
0x180020a77  mov     ecx, [rdi+410h]
0x180020a7d  call    IsPqcKey
0x180020a82  test    eax, eax
0x180020a84  jz      loc_180020BB8
0x180020a8a  mov     r8, [rdi+4B8h]; pbInput
0x180020a91  test    r8, r8
0x180020a94  jnz     short loc_180020ADA
0x180020a96  mov     edx, ebx
0x180020a98  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180020a9d  mov     r9d, 8009000Bh
0x180020aa3  mov     esi, r9d
0x180020aa6  lea     rdi, WPP_GLOBAL_Control
0x180020aad  mov     rcx, cs:WPP_GLOBAL_Control
0x180020ab4  cmp     rcx, rdi
0x180020ab7  jz      loc_180020E8A
0x180020abd  test    byte ptr [rcx+1Ch], 1
0x180020ac1  jz      loc_180020E8A
0x180020ac7  cmp     [rcx+19h], bl
0x180020aca  jb      loc_180020E8A
0x180020ad0  mov     edx, 70h ; 'p'
0x180020ad5  jmp     loc_1800207B5
0x180020ada  or      r9, 0FFFFFFFFFFFFFFFFh
0x180020ade  inc     r9
0x180020ae1  cmp     [r8+r9*2], r13w
0x180020ae6  jnz     short loc_180020ADE
0x180020ae8  lea     r9d, ds:2[r9*2]; cbInput
0x180020af0  mov     [rsp+60h+dwLegacyKeySpec], r13d; dwFlags
0x180020af5  lea     rdx, aParametersetna; "ParameterSetName"
0x180020afc  mov     rcx, [rbp+phKey]; hObject
0x180020b00  call    cs:__imp_NCryptSetProperty
0x180020b06  mov     esi, eax
0x180020b08  test    eax, eax
0x180020b0a  jz      loc_180020BB8
0x180020b10  mov     edx, ebx
0x180020b12  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180020b17  lea     rdi, WPP_GLOBAL_Control
0x180020b1e  mov     rcx, cs:WPP_GLOBAL_Control
0x180020b25  cmp     rcx, rdi
0x180020b28  jz      loc_180020E8A
0x180020b2e  test    byte ptr [rcx+1Ch], 1
0x180020b32  jz      loc_180020E8A
0x180020b38  cmp     [rcx+19h], bl
0x180020b3b  jb      loc_180020E8A
0x180020b41  mov     edx, 71h ; 'q'
0x180020b46  jmp     loc_180020E6F
0x180020b4b  cmp     [rdi+41Ch], r13d
0x180020b52  jz      short loc_180020BB8
0x180020b54  lea     r8, [rdi+414h]; pbInput
0x180020b5b  mov     [rsp+60h+dwLegacyKeySpec], r13d; dwFlags
0x180020b60  mov     r9d, 4; cbInput
0x180020b66  lea     rdx, aLength; "Length"
0x180020b6d  mov     rcx, [rbp+phKey]; hObject
0x180020b71  call    cs:__imp_NCryptSetProperty
0x180020b77  mov     esi, eax
0x180020b79  test    eax, eax
0x180020b7b  jz      short loc_180020BB8
0x180020b7d  mov     edx, ebx
0x180020b7f  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180020b84  lea     rdi, WPP_GLOBAL_Control
0x180020b8b  mov     rcx, cs:WPP_GLOBAL_Control
0x180020b92  cmp     rcx, rdi
0x180020b95  jz      loc_180020E8A
0x180020b9b  test    byte ptr [rcx+1Ch], 1
0x180020b9f  jz      loc_180020E8A
0x180020ba5  cmp     [rcx+19h], bl
0x180020ba8  jb      loc_180020E8A
0x180020bae  mov     edx, 72h ; 'r'
0x180020bb3  jmp     loc_180020E6F
0x180020bb8  cmp     [rdi+488h], r13
0x180020bbf  jz      loc_180020DC5
0x180020bc5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_SmartCardKspPqcSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_SmartCardKspPqcSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SmartCardKspPqcSupport> `wil::Feature<__WilFeatureTraits_Feature_Servicing_SmartCardKspPqcSupport>::GetImpl(void)'::`2'::impl
0x180020bcc  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_SmartCardKspPqcSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SmartCardKspPqcSupport>::__private_IsEnabled(void)
0x180020bd1  test    al, al
0x180020bd3  jz      loc_180020D01
0x180020bd9  mov     ecx, [rdi+410h]
0x180020bdf  call    IsPqcKey
0x180020be4  mov     [rsp+60h+dwLegacyKeySpec], r13d; dwFlags
0x180020be9  mov     r9d, [rdi+490h]; cbInput
0x180020bf0  mov     r8, [rdi+488h]; pbInput
0x180020bf7  test    eax, eax
0x180020bf9  jz      short loc_180020C51
0x180020bfb  mov     rdx, [rdi+498h]; pszProperty
0x180020c02  mov     rcx, [rbp+phKey]; hObject
0x180020c06  call    cs:__imp_NCryptSetProperty
0x180020c0c  mov     esi, eax
0x180020c0e  test    eax, eax
0x180020c10  jz      loc_180020DC5
0x180020c16  mov     edx, ebx
0x180020c18  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180020c1d  lea     rdi, WPP_GLOBAL_Control
0x180020c24  mov     rcx, cs:WPP_GLOBAL_Control
0x180020c2b  cmp     rcx, rdi
  ... truncated ...
```
