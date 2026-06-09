# EnterprisePolicyReader::ReadPolicyWithFallbackInternal(tagEnterprisePolicy,tagEnterprisePolicyValue_V1 *)

- ea: `0x180010c1c`
- end: `0x18001144a`
- name: `?ReadPolicyWithFallbackInternal@EnterprisePolicyReader@@CAJW4tagEnterprisePolicy@@PEAUtagEnterprisePolicyValue_V1@@@Z`
- size: `2094`
- prototype: `__int64 __fastcall(unsigned int, __int64)`
- caller_count: `2`
- callee_count: `17`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180010ae0`
- `0x180010c1c`

## callees

- `0x180010c1c`
- `0x180011484`
- `0x1800116a0`
- `0x1800118d4`
- `0x180011d90`
- `0x180011e8c`
- `0x18001203c`
- `0x180012138`
- `0x180014ea8`
- `0x180016e74`
- `0x180018ac8`
- `0x18001f880`
- `0x18001f950`
- `0x180026c78`
- `0x18002fda9`
- `0x18002ffd0`
- `0x180036a10`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x180010d5c`
- `OLEAUT32!__imp_SysStringLen` at `0x180010d5c`
- `OLEAUT32!__imp_VariantInit` at `0x180010cf4`
- `OLEAUT32!__imp_VariantInit` at `0x180010dd9`
- `OLEAUT32!__imp_VariantInit` at `0x180010cf4`
- `OLEAUT32!__imp_VariantInit` at `0x180010dd9`
- `OLEAUT32!__imp_VariantClear` at `0x180010ca5`
- `OLEAUT32!__imp_VariantClear` at `0x180010d92`
- `OLEAUT32!__imp_VariantClear` at `0x180010da7`
- `OLEAUT32!__imp_VariantClear` at `0x180011418`
- `OLEAUT32!__imp_VariantClear` at `0x180010ca5`
- `OLEAUT32!__imp_VariantClear` at `0x180010d92`
- `OLEAUT32!__imp_VariantClear` at `0x180010da7`
- `OLEAUT32!__imp_VariantClear` at `0x180011418`
- `OLEAUT32!__imp_VariantCopy` at `0x180011407`
- `OLEAUT32!__imp_VariantCopy` at `0x180011407`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180010d0a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180010df1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180010d0a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180010df1`

## string_xrefs

- `0x180010f99`: `WindowsUpdateUXRoot`
- `0x18001123d`: `WindowsUpdateUXRoot`

## pseudocode

```c
__int64 __fastcall EnterprisePolicyReader::ReadPolicyWithFallbackInternal(unsigned int a1, __int64 a2)
{
  __int64 v2; // rbx
  int PolicyWithFallbackInternal; // esi
  __int64 v5; // r15
  wchar_t *v6; // rax
  int v7; // r13d
  int v8; // eax
  bool v9; // zf
  int v10; // eax
  const wchar_t *v11; // rdx
  int TestHookPolicy; // eax
  wchar_t *v13; // rax
  const wchar_t *v14; // rdx
  wchar_t *v15; // rax
  const wchar_t *v16; // rdx
  char v17; // al
  unsigned int v18; // eax
  char v19; // al
  unsigned int v20; // eax
  wchar_t *v21; // rax
  wchar_t *v22; // rdi
  wchar_t *v23; // rax
  const wchar_t *v24; // rdx
  int LusPolicy; // eax
  __int64 v26; // rdi
  wchar_t *v27; // rax
  wchar_t *v28; // rax
  char IsEnabled; // al
  unsigned int v30; // eax
  char v31; // al
  unsigned int v32; // eax
  wchar_t *v33; // rax
  int v34; // edi
  unsigned int v35; // r15d
  unsigned int v36; // r13d
  wchar_t *v37; // rax
  int v38; // ecx
  wchar_t *v39; // rax
  __int64 v40; // rcx
  unsigned int v41; // ecx
  unsigned int v42; // edx
  unsigned int v43; // eax
  int v44; // ecx
  wchar_t *v46; // [rsp+40h] [rbp-C0h]
  _OWORD v47[3]; // [rsp+48h] [rbp-B8h] BYREF
  wchar_t v48[264]; // [rsp+80h] [rbp-80h] BYREF

  v2 = (int)a1;
  PolicyWithFallbackInternal = 0;
  if ( !a2 )
    return (unsigned int)-2147467261;
  if ( a1 > 0x55 )
    return (unsigned int)-2147024809;
  v5 = 15LL * (int)a1;
  v6 = off_18004B4F0[v5 + 12];
  if ( v6 && !((unsigned int (__fastcall *)(_QWORD))v6)(a1) )
  {
    *(_DWORD *)a2 = v2;
    *(_QWORD *)(a2 + 4) = 0;
    return (unsigned int)VariantClear((VARIANTARG *)(a2 + 16));
  }
  v7 = 0;
  v8 = HIDWORD(off_18004B4F0[v5 + 11]);
  if ( v8 && v8 != (_DWORD)v2 )
  {
    memset(v47, 0, sizeof(v47));
    VariantInit((VARIANTARG *)&v47[1]);
    *(_QWORD *)((char *)v47 + 4) = 0;
    LODWORD(v47[0]) = 0;
    GetSystemTimeAsFileTime((LPFILETIME)&v47[2] + 1);
    PolicyWithFallbackInternal = EnterprisePolicyReader::ReadPolicyWithFallbackInternal(
                                   HIDWORD(off_18004B4F0[v5 + 11]),
                                   v47);
    if ( PolicyWithFallbackInternal >= 0 && DWORD1(v47[0]) == 1 )
    {
      switch ( LOWORD(v47[1]) )
      {
        case 3:
          v9 = DWORD2(v47[1]) == 0;
          break;
        case 8:
          v9 = SysStringLen(*((BSTR *)&v47[1] + 1)) == 0;
          break;
        case 0x15:
          v9 = *((_QWORD *)&v47[1] + 1) == 0;
          break;
        default:
          goto LABEL_20;
      }
      if ( !v9 )
      {
        v7 = 1;
LABEL_21:
        VariantClear((VARIANTARG *)&v47[1]);
        if ( !v7 )
          return (unsigned int)PolicyWithFallbackInternal;
        goto LABEL_22;
      }
    }
LABEL_20:
    *(_DWORD *)(a2 + 8) = DWORD2(v47[0]);
    *(_DWORD *)(a2 + 4) = 0;
    *(_DWORD *)a2 = v2;
    PolicyWithFallbackInternal = VariantClear((VARIANTARG *)(a2 + 16));
    if ( PolicyWithFallbackInternal < 0 )
      return (unsigned int)PolicyWithFallbackInternal;
    goto LABEL_21;
  }
LABEL_22:
  memset(v47, 0, sizeof(v47));
  VariantInit((VARIANTARG *)&v47[1]);
  *(_QWORD *)((char *)v47 + 4) = 0;
  LODWORD(v47[0]) = 0;
  GetSystemTimeAsFileTime((LPFILETIME)&v47[2] + 1);
  v10 = (int)off_18004B4F0[v5 + 2];
  if ( v10 == 3 )
  {
    v26 = 15 * v2;
    if ( TestHookPolicyReader::AreTestHooksEnabled() )
    {
      TestHookPolicy = EnterprisePolicyReader::ReadTestHookPolicy(
                         off_18004B4F0[15 * v2 + 1],
                         (unsigned int)off_18004B4F0[15 * v2 + 5],
                         (unsigned int)off_18004B4F0[15 * v2 + 3],
                         (unsigned int)off_18004B4F0[v26 + 4],
                         (struct tagEnterprisePolicyValue_V1 *)v47);
      goto LABEL_29;
    }
    v27 = off_18004B4F0[v26 + 7];
    if ( v27 && ((unsigned int (__fastcall *)(_QWORD))v27)((unsigned int)v2) )
    {
      PolicyWithFallbackInternal = EnterprisePolicyReader::ReadGPPolicy(
                                     off_18004B4F0[15 * v2 + 1],
                                     (const wchar_t *)(120 * v2),
                                     (unsigned int)off_18004B4F0[15 * v2 + 5],
                                     (unsigned int)off_18004B4F0[15 * v2 + 3],
                                     (unsigned int)off_18004B4F0[15 * v2 + 4],
                                     (unsigned int)off_18004B4F0[v5 + 2],
                                     (struct tagEnterprisePolicyValue_V1 *)v47);
      LODWORD(v47[0]) = v2;
    }
    if ( DWORD1(v47[0]) )
      goto LABEL_107;
    v28 = off_18004B4F0[15 * v2 + 8];
    if ( !v28 )
      goto LABEL_93;
    if ( !((unsigned int (__fastcall *)(_QWORD))v28)((unsigned int)v2) )
    {
LABEL_92:
      if ( DWORD1(v47[0]) )
        goto LABEL_107;
LABEL_93:
      v33 = off_18004B4F0[15 * v2 + 9];
      if ( !v33 )
        goto LABEL_137;
      if ( ((unsigned int (__fastcall *)(_QWORD))v33)((unsigned int)v2) )
      {
        v34 = (int)off_18004B4F0[15 * v2 + 4];
        v35 = (unsigned int)off_18004B4F0[15 * v2 + 3];
        v36 = (unsigned int)off_18004B4F0[15 * v2 + 5];
        v46 = off_18004B4F0[15 * v2];
        memset_0(v48, 0, 0x208u);
        PolicyWithFallbackInternal = PolicyRegistryHelper::GetRedirectedRegistryKeyName(
                                       (wchar_t *)L"WindowsUpdateUXRoot",
                                       L"\\Settings",
                                       v48,
                                       (wchar_t **)0x104);
        if ( PolicyWithFallbackInternal >= 0 )
          PolicyWithFallbackInternal = PolicyHelpers::ReadPolicyRegistry(v48, v46, v36, v35, v34, 4, v47);
        LODWORD(v47[0]) = v2;
      }
      if ( !DWORD1(v47[0]) )
      {
LABEL_137:
        v37 = off_18004B4F0[15 * v2 + 10];
        if ( v37 )
        {
          if ( ((unsigned int (__fastcall *)(_QWORD))v37)((unsigned int)v2) )
          {
            LusPolicy = EnterprisePolicyReader::ReadLusPolicy(
                          off_18004B4F0[15 * v2],
                          (unsigned int)off_18004B4F0[15 * v2 + 5],
                          (unsigned int)off_18004B4F0[15 * v2 + 3],
                          (unsigned int)off_18004B4F0[15 * v2 + 4],
                          (struct tagEnterprisePolicyValue_V1 *)v47);
            goto LABEL_102;
          }
        }
      }
LABEL_107:
      if ( PolicyWithFallbackInternal < 0 )
        goto LABEL_133;
      goto LABEL_108;
    }
    PolicyWithFallbackInternal = EnterprisePolicyReader::ReadCspPolicy(
                                   off_18004B4F0[15 * v2],
                                   (unsigned int)off_18004B4F0[15 * v2 + 5],
                                   (unsigned int)off_18004B4F0[15 * v2 + 3],
                                   (unsigned int)off_18004B4F0[15 * v2 + 4],
                                   (struct tagEnterprisePolicyValue_V1 *)v47);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UpdatePolicyReaderUTFixes>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UpdatePolicyReaderUTFixes>::GetImpl'::`2'::impl) )
    {
      IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_QuickMachineRecoveryEnrolled_59112206>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_QuickMachineRecoveryEnrolled_59112206>::GetImpl'::`2'::impl);
      if ( (_DWORD)v2 == 59 || (_DWORD)v2 == 60 )
        goto LABEL_81;
      v9 = IsEnabled == 0;
      v30 = v2 - 61;
      if ( !v9 )
      {
        if ( (v30 & 0xFFFFFFFC) != 0 || (_DWORD)v2 == 63 )
          goto LABEL_91;
LABEL_81:
        if ( DWORD1(v47[0]) != 1 )
          goto LABEL_91;
        goto LABEL_90;
      }
      if ( v30 <= 1 )
        goto LABEL_81;
LABEL_91:
      LODWORD(v47[0]) = v2;
      goto LABEL_92;
    }
    v31 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_QuickMachineRecoveryEnrolled_59112206>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_QuickMachineRecoveryEnrolled_59112206>::GetImpl'::`2'::impl);
    if ( (_DWORD)v2 != 59 && (_DWORD)v2 != 60 )
    {
      v9 = v31 == 0;
      v32 = v2 - 61;
      if ( v9 )
      {
        if ( v32 > 1 )
          goto LABEL_91;
      }
      else if ( (v32 & 0xFFFFFFFC) != 0 || (_DWORD)v2 == 63 )
      {
        goto LABEL_91;
      }
    }
LABEL_90:
    DWORD2(v47[0]) = 7;
    goto LABEL_91;
  }
  if ( v10 == 8 )
  {
    if ( TestHookPolicyReader::AreTestHooksEnabled() )
    {
      TestHookPolicy = EnterprisePolicyReader::ReadTestHookPolicy(
                         off_18004B4F0[v5 + 1],
                         v11,
                         (struct tagEnterprisePolicyValue_V1 *)v47);
LABEL_29:
      PolicyWithFallbackInternal = TestHookPolicy;
LABEL_106:
      LODWORD(v47[0]) = v2;
      goto LABEL_107;
    }
    v13 = off_18004B4F0[v5 + 7];
    if ( v13 && ((unsigned int (__fastcall *)(_QWORD))v13)((unsigned int)v2) )
    {
      PolicyWithFallbackInternal = EnterprisePolicyReader::ReadGPPolicy(
                                     off_18004B4F0[v5 + 1],
                                     v14,
                                     (unsigned int)off_18004B4F0[v5 + 5],
                                     (unsigned int)off_18004B4F0[v5 + 3],
                                     (unsigned int)off_18004B4F0[v5 + 4],
                                     (unsigned int)off_18004B4F0[v5 + 2],
                                     (struct tagEnterprisePolicyValue_V1 *)v47);
      LODWORD(v47[0]) = v2;
    }
    if ( DWORD1(v47[0]) )
      goto LABEL_107;
    v15 = off_18004B4F0[v5 + 8];
    if ( !v15 )
      goto LABEL_56;
    if ( !((unsigned int (__fastcall *)(_QWORD))v15)((unsigned int)v2) )
    {
LABEL_55:
      if ( DWORD1(v47[0]) )
        goto LABEL_107;
LABEL_56:
      v21 = off_18004B4F0[v5 + 9];
      if ( !v21 )
        goto LABEL_138;
      if ( ((unsigned int (__fastcall *)(_QWORD))v21)((unsigned int)v2) )
      {
        v22 = off_18004B4F0[v5];
        memset_0(v48, 0, 0x208u);
        PolicyWithFallbackInternal = PolicyRegistryHelper::GetRedirectedRegistryKeyName(
                                       (wchar_t *)L"WindowsUpdateUXRoot",
                                       L"\\Settings",
                                       v48,
                                       (wchar_t **)0x104);
        if ( PolicyWithFallbackInternal >= 0 )
          PolicyWithFallbackInternal = PolicyHelpers::ReadPolicyRegistry(v48, v22, &psz, 4, v47);
        LODWORD(v47[0]) = v2;
      }
      if ( !DWORD1(v47[0]) )
      {
LABEL_138:
        v23 = off_18004B4F0[15 * v2 + 10];
        if ( v23 )
        {
          if ( ((unsigned int (__fastcall *)(_QWORD))v23)((unsigned int)v2) )
          {
            LusPolicy = EnterprisePolicyReader::ReadLusPolicy(
                          off_18004B4F0[15 * v2],
                          v24,
                          (struct tagEnterprisePolicyValue_V1 *)v47);
LABEL_102:
            v38 = DWORD1(v47[0]);
            PolicyWithFallbackInternal = 0;
            if ( LusPolicy >= 0 )
              PolicyWithFallbackInternal = LusPolicy;
            else
              v38 = 0;
            DWORD1(v47[0]) = v38;
            goto LABEL_106;
          }
        }
      }
      goto LABEL_107;
    }
    PolicyWithFallbackInternal = EnterprisePolicyReader::ReadCspPolicy(
                                   off_18004B4F0[v5],
                                   v16,
                                   (struct tagEnterprisePolicyValue_V1 *)v47);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UpdatePolicyReaderUTFixes>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UpdatePolicyReaderUTFixes>::GetImpl'::`2'::impl) )
    {
      v17 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_QuickMachineRecoveryEnrolled_59112206>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_QuickMachineRecoveryEnrolled_59112206>::GetImpl'::`2'::impl);
      if ( (_DWORD)v2 == 59 || (_DWORD)v2 == 60 )
        goto LABEL_44;
      v9 = v17 == 0;
      v18 = v2 - 61;
      if ( !v9 )
      {
        if ( (v18 & 0xFFFFFFFC) != 0 || (_DWORD)v2 == 63 )
          goto LABEL_54;
LABEL_44:
        if ( DWORD1(v47[0]) != 1 )
          goto LABEL_54;
        goto LABEL_53;
      }
      if ( v18 <= 1 )
        goto LABEL_44;
LABEL_54:
      LODWORD(v47[0]) = v2;
      goto LABEL_55;
    }
    v19 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_QuickMachineRecoveryEnrolled_59112206>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_QuickMachineRecoveryEnrolled_59112206>::GetImpl'::`2'::impl);
    if ( (_DWORD)v2 != 59 && (_DWORD)v2 != 60 )
    {
      v9 = v19 == 0;
      v20 = v2 - 61;
      if ( v9 )
      {
        if ( v20 > 1 )
          goto LABEL_54;
      }
      else if ( (v20 & 0xFFFFFFFC) != 0 || (_DWORD)v2 == 63 )
      {
        goto LABEL_54;
      }
    }
LABEL_53:
    DWORD2(v47[0]) = 7;
    goto LABEL_54;
  }
  if ( v10 != 21 )
  {
    PolicyWithFallbackInternal = -2147024809;
LABEL_133:
    VariantClear((VARIANTARG *)&v47[1]);
    return (unsigned int)PolicyWithFallbackInternal;
  }
  PolicyWithFallbackInternal = 0;
LABEL_108:
  v39 = off_18004B4F0[15 * v2 + 13];
  if ( v39 )
    PolicyWithFallbackInternal = ((__int64 (__fastcall *)(_OWORD *))v39)(v47);
  if ( !DWORD1(v47[0]) )
  {
    v40 = LODWORD(off_18004B4F0[15 * v2 + 14]);
    if ( (unsigned int)(v40 - 1) > 0x54 || (_DWORD)v40 == (_DWORD)v2 )
      goto LABEL_124;
    PolicyWithFallbackInternal = EnterprisePolicyReader::ReadPolicyWithFallbackInternal(v40, v47);
    if ( PolicyWithFallbackInternal >= 0 )
    {
      if ( DWORD1(v47[0]) == 1 && LOWORD(v47[1]) == 3 )
      {
        v41 = (unsigned int)off_18004B4F0[15 * v2 + 3];
        v42 = (unsigned int)off_18004B4F0[15 * v2 + 4];
        if ( v41 <= v42 )
        {
          v43 = DWORD2(v47[1]);
          if ( DWORD2(v47[1]) < v41 )
            v43 = (unsigned int)off_18004B4F0[15 * v2 + 3];
          if ( v43 > v42 )
            v43 = (unsigned int)off_18004B4F0[15 * v2 + 4];
          DWORD2(v47[1]) = v43;
        }
      }
      PolicyWithFallbackInternal = 0;
    }
    if ( !DWORD1(v47[0]) )
    {
LABEL_124:
      v44 = (int)off_18004B4F0[15 * v2 + 2];
      if ( v44 == 3 )
      {
        if ( LODWORD(off_18004B4F0[15 * v2 + 11]) )
        {
          LOWORD(v47[1]) = 3;
          DWORD2(v47[1]) = off_18004B4F0[15 * v2 + 5];
LABEL_130:
          *(_QWORD *)((char *)v47 + 4) = 3;
        }
      }
      else if ( v44 == 21 && LODWORD(off_18004B4F0[15 * v2 + 11]) )
      {
        LOWORD(v47[1]) = 21;
        *((_QWORD *)&v47[1] + 1) = LODWORD(off_18004B4F0[15 * v2 + 5]);
        goto LABEL_130;
      }
    }
  }
  if ( PolicyWithFallbackInternal < 0 )
    goto LABEL_133;
  *(_QWORD *)(a2 + 4) = *(_QWORD *)((char *)v47 + 4);
  *(_DWORD *)a2 = v2;
  PolicyWithFallbackInternal = VariantCopy((VARIANTARG *)(a2 + 16), (const VARIANTARG *)&v47[1]);
  if ( PolicyWithFallbackInternal >= 0 )
    goto LABEL_133;
  return (unsigned int)PolicyWithFallbackInternal;
}

```

## disassembly

```asm
0x180010c1c  mov     [rsp-8+arg_10], rbx
0x180010c21  push    rbp
0x180010c22  push    rsi
0x180010c23  push    rdi
0x180010c24  push    r12
0x180010c26  push    r13
0x180010c28  push    r14
0x180010c2a  push    r15
0x180010c2c  lea     rbp, [rsp-1A0h]
0x180010c34  sub     rsp, 2A0h
0x180010c3b  mov     rax, cs:__security_cookie
0x180010c42  xor     rax, rsp
0x180010c45  mov     [rbp+1D0h+var_40], rax
0x180010c4c  xor     edi, edi
0x180010c4e  movsxd  rbx, ecx
0x180010c51  mov     r12, rdx
0x180010c54  mov     esi, edi
0x180010c56  test    rdx, rdx
0x180010c59  jnz     short loc_180010C65
0x180010c5b  mov     esi, 80004003h
0x180010c60  jmp     loc_18001141E
0x180010c65  cmp     ebx, 55h ; 'U'
0x180010c68  jbe     short loc_180010C74
0x180010c6a  mov     esi, 80070057h
0x180010c6f  jmp     loc_18001141E
0x180010c74  imul    r15, rbx, 78h ; 'x'
0x180010c78  lea     rax, off_18004B4F0; "None"
0x180010c7f  mov     r14, rbx
0x180010c82  mov     rax, [r15+rax+60h]
0x180010c87  test    rax, rax
0x180010c8a  jz      short loc_180010CB2
0x180010c8c  mov     ecx, ebx
0x180010c8e  call    _guard_dispatch_icall
0x180010c93  test    eax, eax
0x180010c95  jnz     short loc_180010CB2
0x180010c97  lea     rcx, [r12+10h]; pvarg
0x180010c9c  mov     [r12], ebx
0x180010ca0  mov     [r12+4], rdi
0x180010ca5  call    cs:__imp_VariantClear
0x180010cab  mov     esi, eax
0x180010cad  jmp     loc_18001141E
0x180010cb2  lea     rax, off_18004B4F0; "None"
0x180010cb9  mov     r13d, edi
0x180010cbc  mov     eax, [r15+rax+5Ch]
0x180010cc1  test    eax, eax
0x180010cc3  jz      loc_180010DB6
0x180010cc9  cmp     eax, ebx
0x180010ccb  jz      loc_180010DB6
0x180010cd1  xorps   xmm0, xmm0
0x180010cd4  lea     rdi, [rsp+2D0h+var_288]
0x180010cd9  xor     eax, eax
0x180010cdb  movups  [rsp+2D0h+var_288], xmm0
0x180010ce0  movups  xmmword ptr [rsp+2D0h+pvarg], xmm0
0x180010ce5  lea     ecx, [rax+30h]
0x180010ce8  movups  xmmword ptr [rsp+2D0h+pvarg+10h], xmm0
0x180010ced  rep stosb
0x180010cef  lea     rcx, [rsp+2D0h+pvarg]; pvarg
0x180010cf4  call    cs:__imp_VariantInit
0x180010cfa  xor     edi, edi
0x180010cfc  lea     rcx, [rsp+2D0h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180010d01  mov     qword ptr [rsp+2D0h+var_288+4], rdi
0x180010d06  mov     dword ptr [rsp+2D0h+var_288], edi
0x180010d0a  call    cs:__imp_GetSystemTimeAsFileTime
0x180010d10  lea     rax, off_18004B4F0; "None"
0x180010d17  mov     ecx, [r15+rax+5Ch]
0x180010d1c  lea     rdx, [rsp+2D0h+var_288]
0x180010d21  call    ?ReadPolicyWithFallbackInternal@EnterprisePolicyReader@@CAJW4tagEnterprisePolicy@@PEAUtagEnterprisePolicyValue_V1@@@Z; EnterprisePolicyReader::ReadPolicyWithFallbackInternal(tagEnterprisePolicy,tagEnterprisePolicyValue_V1 *)
0x180010d26  mov     esi, eax
0x180010d28  test    eax, eax
0x180010d2a  js      short loc_180010D7B
0x180010d2c  cmp     dword ptr [rsp+2D0h+var_288+4], 1
0x180010d31  jnz     short loc_180010D7B
0x180010d33  movzx   ecx, word ptr [rsp+2D0h+pvarg]
0x180010d38  lea     eax, [rdi+3]
0x180010d3b  cmp     cx, ax
0x180010d3e  jz      short loc_180010D66
0x180010d40  lea     eax, [rdi+8]
0x180010d43  cmp     cx, ax
0x180010d46  jz      short loc_180010D57
0x180010d48  lea     eax, [rdi+15h]
0x180010d4b  cmp     cx, ax
0x180010d4e  jnz     short loc_180010D7B
0x180010d50  cmp     qword ptr [rsp+2D0h+pvarg+8], rdi
0x180010d55  jmp     short loc_180010D6A
0x180010d57  mov     rcx, qword ptr [rsp+2D0h+pvarg+8]; pbstr
0x180010d5c  call    cs:__imp_SysStringLen
0x180010d62  test    eax, eax
0x180010d64  jmp     short loc_180010D6A
0x180010d66  cmp     dword ptr [rsp+2D0h+pvarg+8], edi
0x180010d6a  mov     ecx, edi
0x180010d6c  setnz   cl
0x180010d6f  test    ecx, ecx
0x180010d71  jz      short loc_180010D7B
0x180010d73  mov     r13d, 1
0x180010d79  jmp     short loc_180010DA2
0x180010d7b  mov     eax, dword ptr [rsp+2D0h+var_288+8]
0x180010d7f  lea     rcx, [r12+10h]; pvarg
0x180010d84  mov     [r12+8], eax
0x180010d89  mov     [r12+4], edi
0x180010d8e  mov     [r12], ebx
0x180010d92  call    cs:__imp_VariantClear
0x180010d98  mov     esi, eax
0x180010d9a  test    eax, eax
0x180010d9c  js      loc_18001141E
0x180010da2  lea     rcx, [rsp+2D0h+pvarg]; pvarg
0x180010da7  call    cs:__imp_VariantClear
0x180010dad  test    r13d, r13d
0x180010db0  jz      loc_18001141E
0x180010db6  xorps   xmm0, xmm0
0x180010db9  lea     rdi, [rsp+2D0h+var_288]
0x180010dbe  xor     eax, eax
0x180010dc0  movups  [rsp+2D0h+var_288], xmm0
0x180010dc5  movups  xmmword ptr [rsp+2D0h+pvarg], xmm0
0x180010dca  lea     ecx, [rax+30h]
0x180010dcd  movups  xmmword ptr [rsp+2D0h+pvarg+10h], xmm0
0x180010dd2  rep stosb
0x180010dd4  lea     rcx, [rsp+2D0h+pvarg]; pvarg
0x180010dd9  call    cs:__imp_VariantInit
0x180010ddf  xor     r13d, r13d
0x180010de2  lea     rcx, [rsp+2D0h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180010de7  mov     qword ptr [rsp+2D0h+var_288+4], r13
0x180010dec  mov     dword ptr [rsp+2D0h+var_288], r13d
0x180010df1  call    cs:__imp_GetSystemTimeAsFileTime
0x180010df7  lea     rdi, off_18004B4F0; "None"
0x180010dfe  mov     eax, [r15+rdi+10h]
0x180010e03  cmp     eax, 3
0x180010e06  jz      loc_18001101E
0x180010e0c  cmp     eax, 8
0x180010e0f  jz      short loc_180010E2C
0x180010e11  lea     r15d, [r13+15h]
0x180010e15  cmp     eax, r15d
0x180010e18  jz      short loc_180010E24
0x180010e1a  mov     esi, 80070057h
0x180010e1f  jmp     loc_180011413
0x180010e24  mov     esi, r13d
0x180010e27  jmp     loc_180011300
0x180010e2c  call    ?AreTestHooksEnabled@TestHookPolicyReader@@SA_NXZ; TestHookPolicyReader::AreTestHooksEnabled(void)
0x180010e31  test    al, al
0x180010e33  jz      short loc_180010E4B
0x180010e35  mov     rcx, [r15+rdi+8]; wchar_t *
0x180010e3a  lea     r8, [rsp+2D0h+var_288]; struct tagEnterprisePolicyValue_V1 *
0x180010e3f  call    ?ReadTestHookPolicy@EnterprisePolicyReader@@CAJPEB_W0PEAUtagEnterprisePolicyValue_V1@@@Z; EnterprisePolicyReader::ReadTestHookPolicy(wchar_t const *,wchar_t const *,tagEnterprisePolicyValue_V1 *)
0x180010e44  mov     esi, eax
0x180010e46  jmp     loc_1800112EE
0x180010e4b  mov     rax, [r15+rdi+38h]
0x180010e50  test    rax, rax
0x180010e53  jz      short loc_180010E96
0x180010e55  mov     ecx, ebx
0x180010e57  call    _guard_dispatch_icall
0x180010e5c  test    eax, eax
0x180010e5e  jz      short loc_180010E96
0x180010e60  mov     r9d, [r15+rdi+18h]; unsigned int
0x180010e65  lea     rax, [rsp+2D0h+var_288]
0x180010e6a  mov     r8d, [r15+rdi+28h]; unsigned int
0x180010e6f  mov     rcx, [r15+rdi+8]; wchar_t *
0x180010e74  mov     [rsp+2D0h+var_2A0], rax; struct tagEnterprisePolicyValue_V1 *
0x180010e79  mov     eax, [r15+rdi+10h]
0x180010e7e  mov     [rsp+2D0h+var_2A8], eax; unsigned int
0x180010e82  mov     eax, [r15+rdi+20h]
0x180010e87  mov     dword ptr [rsp+2D0h+var_2B0], eax; unsigned int
0x180010e8b  call    ?ReadGPPolicy@EnterprisePolicyReader@@CAJPEB_W0KKKKPEAUtagEnterprisePolicyValue_V1@@@Z; EnterprisePolicyReader::ReadGPPolicy(wchar_t const *,wchar_t const *,ulong,ulong,ulong,ulong,tagEnterprisePolicyValue_V1 *)
0x180010e90  mov     esi, eax
0x180010e92  mov     dword ptr [rsp+2D0h+var_288], ebx
0x180010e96  cmp     dword ptr [rsp+2D0h+var_288+4], r13d
0x180010e9b  jnz     loc_1800112F2
0x180010ea1  mov     rax, [r15+rdi+40h]
0x180010ea6  test    rax, rax
0x180010ea9  jz      loc_180010F5E
0x180010eaf  mov     ecx, ebx
0x180010eb1  call    _guard_dispatch_icall
0x180010eb6  test    eax, eax
0x180010eb8  jz      loc_180010F53
0x180010ebe  mov     rcx, [r15+rdi]; wchar_t *
0x180010ec2  lea     r8, [rsp+2D0h+var_288]; struct tagEnterprisePolicyValue_V1 *
0x180010ec7  call    ?ReadCspPolicy@EnterprisePolicyReader@@CAJPEB_W0PEAUtagEnterprisePolicyValue_V1@@@Z; EnterprisePolicyReader::ReadCspPolicy(wchar_t const *,wchar_t const *,tagEnterprisePolicyValue_V1 *)
0x180010ecc  mov     esi, eax
0x180010ece  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UpdatePolicyReaderUTFixes@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UpdatePolicyReaderUTFixes@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UpdatePolicyReaderUTFixes> `wil::Feature<__WilFeatureTraits_Feature_UpdatePolicyReaderUTFixes>::GetImpl(void)'::`2'::impl
0x180010ed5  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UpdatePolicyReaderUTFixes@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UpdatePolicyReaderUTFixes>::__private_IsEnabled(void)
0x180010eda  test    al, al
0x180010edc  jz      short loc_180010F17
0x180010ede  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_QuickMachineRecoveryEnrolled_59112206@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_QuickMachineRecoveryEnrolled_59112206@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_QuickMachineRecoveryEnrolled_59112206> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_QuickMachineRecoveryEnrolled_59112206>::GetImpl(void)'::`2'::impl
0x180010ee5  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_QuickMachineRecoveryEnrolled_59112206@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_QuickMachineRecoveryEnrolled_59112206>::__private_IsEnabled(void)
0x180010eea  cmp     ebx, 3Bh ; ';'
0x180010eed  jz      short loc_180010F0E
0x180010eef  cmp     ebx, 3Ch ; '<'
0x180010ef2  jz      short loc_180010F0E
0x180010ef4  test    al, al
0x180010ef6  lea     eax, [rbx-3Dh]
0x180010ef9  jz      short loc_180010F09
0x180010efb  test    eax, 0FFFFFFFCh
0x180010f00  jnz     short loc_180010F4F
0x180010f02  cmp     ebx, 3Fh ; '?'
0x180010f05  jz      short loc_180010F4F
0x180010f07  jmp     short loc_180010F0E
0x180010f09  cmp     eax, 1
0x180010f0c  ja      short loc_180010F4F
0x180010f0e  cmp     dword ptr [rsp+2D0h+var_288+4], 1
0x180010f13  jz      short loc_180010F47
0x180010f15  jmp     short loc_180010F4F
0x180010f17  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_QuickMachineRecoveryEnrolled_59112206@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_QuickMachineRecoveryEnrolled_59112206@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_QuickMachineRecoveryEnrolled_59112206> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_QuickMachineRecoveryEnrolled_59112206>::GetImpl(void)'::`2'::impl
0x180010f1e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_QuickMachineRecoveryEnrolled_59112206@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_QuickMachineRecoveryEnrolled_59112206>::__private_IsEnabled(void)
0x180010f23  cmp     ebx, 3Bh ; ';'
0x180010f26  jz      short loc_180010F47
0x180010f28  cmp     ebx, 3Ch ; '<'
0x180010f2b  jz      short loc_180010F47
0x180010f2d  test    al, al
0x180010f2f  lea     eax, [rbx-3Dh]
0x180010f32  jz      short loc_180010F42
0x180010f34  test    eax, 0FFFFFFFCh
0x180010f39  jnz     short loc_180010F4F
0x180010f3b  cmp     ebx, 3Fh ; '?'
0x180010f3e  jz      short loc_180010F4F
0x180010f40  jmp     short loc_180010F47
0x180010f42  cmp     eax, 1
0x180010f45  ja      short loc_180010F4F
0x180010f47  mov     dword ptr [rsp+2D0h+var_288+8], 7
0x180010f4f  mov     dword ptr [rsp+2D0h+var_288], ebx
0x180010f53  cmp     dword ptr [rsp+2D0h+var_288+4], r13d
0x180010f58  jnz     loc_1800112F2
0x180010f5e  mov     rax, [r15+rdi+48h]
0x180010f63  test    rax, rax
0x180010f66  jz      short loc_180010FE6
0x180010f68  mov     ecx, ebx
0x180010f6a  call    _guard_dispatch_icall
0x180010f6f  test    eax, eax
0x180010f71  jz      short loc_180010FDB
0x180010f73  mov     rdi, [r15+rdi]
0x180010f77  lea     rcx, [rbp+1D0h+var_250]; void *
0x180010f7b  xor     edx, edx; Val
0x180010f7d  mov     r8d, 208h; Size
0x180010f83  call    memset_0
0x180010f88  mov     r9d, 104h; unsigned __int64
0x180010f8e  lea     r8, [rbp+1D0h+var_250]; wchar_t *
0x180010f92  lea     rdx, aSettings; "\\Settings"
0x180010f99  lea     rcx, aWindowsupdateu; "WindowsUpdateUXRoot"
0x180010fa0  call    ?GetRedirectedRegistryKeyName@PolicyRegistryHelper@@SAJPEB_W0PEA_W_K@Z; PolicyRegistryHelper::GetRedirectedRegistryKeyName(wchar_t const *,wchar_t const *,wchar_t *,unsigned __int64)
0x180010fa5  mov     esi, eax
0x180010fa7  test    eax, eax
0x180010fa9  js      short loc_180010FD0
0x180010fab  lea     rax, [rsp+2D0h+var_288]
0x180010fb0  mov     r9d, 4
0x180010fb6  lea     r8, psz
0x180010fbd  mov     [rsp+2D0h+var_2B0], rax
0x180010fc2  mov     rdx, rdi
0x180010fc5  lea     rcx, [rbp+1D0h+var_250]
0x180010fc9  call    ?ReadPolicyRegistry@PolicyHelpers@@SAJPEB_W00W4tagPolicyStore@@PEAUtagEnterprisePolicyValue_V1@@@Z; PolicyHelpers::ReadPolicyRegistry(wchar_t const *,wchar_t const *,wchar_t const *,tagPolicyStore,tagEnterprisePolicyValue_V1 *)
0x180010fce  mov     esi, eax
0x180010fd0  mov     dword ptr [rsp+2D0h+var_288], ebx
0x180010fd4  lea     rdi, off_18004B4F0; "None"
0x180010fdb  cmp     dword ptr [rsp+2D0h+var_288+4], r13d
0x180010fe0  jnz     loc_1800112F2
0x180010fe6  imul    rax, r14, 78h ; 'x'
0x180010fea  mov     rax, [rax+rdi+50h]
0x180010fef  test    rax, rax
0x180010ff2  jz      loc_1800112F2
0x180010ff8  mov     ecx, ebx
0x180010ffa  call    _guard_dispatch_icall
0x180010fff  test    eax, eax
0x180011001  jz      loc_1800112F2
0x180011007  imul    rcx, r14, 78h ; 'x'
0x18001100b  lea     r8, [rsp+2D0h+var_288]; struct tagEnterprisePolicyValue_V1 *
0x180011010  mov     rcx, [rcx+rdi]; wchar_t *
0x180011014  call    ?ReadLusPolicy@EnterprisePolicyReader@@CAJPEB_W0PEAUtagEnterprisePolicyValue_V1@@@Z; EnterprisePolicyReader::ReadLusPolicy(wchar_t const *,wchar_t const *,tagEnterprisePolicyValue_V1 *)
0x180011019  jmp     loc_1800112DA
0x18001101e  imul    rdi, r14, 78h ; 'x'
0x180011022  call    ?AreTestHooksEnabled@TestHookPolicyReader@@SA_NXZ; TestHookPolicyReader::AreTestHooksEnabled(void)
0x180011027  test    al, al
0x180011029  jz      short loc_18001106C
0x18001102b  imul    r8, r14, 78h ; 'x'
0x18001102f  imul    rdx, r14, 78h ; 'x'
0x180011033  imul    rcx, r14, 78h ; 'x'
0x180011037  lea     rax, [rsp+2D0h+var_288]
0x18001103c  mov     [rsp+2D0h+var_2B0], rax; struct tagEnterprisePolicyValue_V1 *
0x180011041  lea     rax, off_18004B4F0; "None"
0x180011048  mov     r9d, [rdi+rax+20h]; unsigned int
0x18001104d  lea     rdi, off_18004B4F0; "None"
0x180011054  mov     r8d, [r8+rdi+18h]; unsigned int
0x180011059  mov     edx, [rdx+rdi+28h]; unsigned int
0x18001105d  mov     rcx, [rcx+rdi+8]; wchar_t *
0x180011062  call    ?ReadTestHookPolicy@EnterprisePolicyReader@@CAJPEB_WKKKPEAUtagEnterprisePolicyValue_V1@@@Z; EnterprisePolicyReader::ReadTestHookPolicy(wchar_t const *,ulong,ulong,ulong,tagEnterprisePolicyValue_V1 *)
0x180011067  jmp     loc_180010E44
0x18001106c  lea     rax, off_18004B4F0; "None"
0x180011073  mov     rax, [rdi+rax+38h]
0x180011078  test    rax, rax
0x18001107b  jz      short loc_1800110D6
0x18001107d  mov     ecx, ebx
0x18001107f  call    _guard_dispatch_icall
0x180011084  lea     rdi, off_18004B4F0; "None"
0x18001108b  test    eax, eax
0x18001108d  jz      short loc_1800110DD
0x18001108f  lea     rax, [rsp+2D0h+var_288]
0x180011094  mov     [rsp+2D0h+var_2A0], rax; struct tagEnterprisePolicyValue_V1 *
0x180011099  mov     eax, [r15+rdi+10h]
0x18001109e  mov     [rsp+2D0h+var_2A8], eax; unsigned int
0x1800110a2  imul    rdx, r14, 78h ; 'x'; wchar_t *
0x1800110a6  imul    r9, r14, 78h ; 'x'
0x1800110aa  imul    r8, r14, 78h ; 'x'
0x1800110ae  imul    rcx, r14, 78h ; 'x'
0x1800110b2  mov     eax, [rdx+rdi+20h]
0x1800110b6  mov     r9d, [r9+rdi+18h]; unsigned int
  ... truncated ...
```
