# CUser::IsGoodbyeAllowed(void)

- ea: `0x140038ef4`
- end: `0x140039361`
- name: `?IsGoodbyeAllowed@CUser@@AEAAHXZ`
- size: `1133`
- prototype: `__int64 __fastcall(CUser *__hidden this)`
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400339b4`
- `0x140038d00`

## callees

- `0x14000b41c`
- `0x14002d330`
- `0x14002d410`
- `0x140030f30`
- `0x140038ef4`
- `0x14003b5d0`
- `0x14003cb6c`
- `0x140041c34`
- `0x140044800`
- `0x14004df08`
- `0x14004eb98`
- `0x14004effc`
- `0x140053720`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140038faa`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400390d0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140038faa`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400390d0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140038fff`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140039117`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140038fff`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140039117`

## pseudocode

```c
_BOOL8 __fastcall CUser::IsGoodbyeAllowed(CUser *this)
{
  bool v1; // bl
  char v3; // r12
  char v4; // r13
  LSTATUS v5; // ebx
  unsigned int v6; // eax
  CUser *v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // rcx
  const char *v10; // r9
  LSTATUS v11; // ebx
  unsigned int v12; // eax
  CUser *v13; // rcx
  char v15; // [rsp+30h] [rbp-89h] BYREF
  char v16; // [rsp+31h] [rbp-88h] BYREF
  bool v17; // [rsp+32h] [rbp-87h] BYREF
  BYTE Data[4]; // [rsp+34h] [rbp-85h] BYREF
  DWORD cbData; // [rsp+38h] [rbp-81h] BYREF
  DWORD Type; // [rsp+3Ch] [rbp-7Dh] BYREF
  HKEY hKey; // [rsp+40h] [rbp-79h] BYREF
  __int64 v22; // [rsp+48h] [rbp-71h] BYREF
  HKEY phkResult[2]; // [rsp+50h] [rbp-69h] BYREF
  char v24; // [rsp+60h] [rbp-59h]
  char v25[32]; // [rsp+70h] [rbp-49h] BYREF
  HKEY *v26; // [rsp+90h] [rbp-29h]
  __int64 v27; // [rsp+98h] [rbp-21h]
  __int64 *v28; // [rsp+A0h] [rbp-19h]
  __int64 v29; // [rsp+A8h] [rbp-11h]
  bool *v30; // [rsp+B0h] [rbp-9h]
  __int64 v31; // [rsp+B8h] [rbp-1h]
  char *v32; // [rsp+C0h] [rbp+7h]
  __int64 v33; // [rsp+C8h] [rbp+Fh]
  char *v34; // [rsp+D0h] [rbp+17h]
  __int64 v35; // [rsp+D8h] [rbp+1Fh]

  v1 = 0;
  v3 = 0;
  hKey = 0;
  cbData = 0;
  Type = 0;
  *(_DWORD *)Data = 0;
  if ( !(unsigned int)CUser::IsLockWorkstationDisabled(this)
    && *(_DWORD *)(*((_QWORD *)this + 9) + 148LL) != 3
    && (!(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID56916126>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID56916126>::GetImpl'::`2'::impl)
     || *(_DWORD *)(*((_QWORD *)this + 9) + 148LL) != 4) )
  {
    phkResult[1] = 0;
    phkResult[0] = (HKEY)&hKey;
    v24 = 1;
    v4 = 0;
    v5 = RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"Software\\Policies\\Microsoft\\PassportForWork\\DynamicLock",
           0,
           0x20019u,
           &phkResult[1]);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(phkResult);
    if ( !v5 )
    {
      cbData = 4;
      v6 = RegQueryValueExW(hKey, L"DynamicLock", 0, &Type, Data, &cbData);
      if ( !v6 && Type == 4 )
      {
        v3 = 1;
        v1 = *(_DWORD *)Data != 0;
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
        {
          goto LABEL_43;
        }
        v8 = 229;
LABEL_12:
        v9 = *((_QWORD *)v7 + 2);
        v10 = "Enabled";
        if ( !v1 )
          v10 = "Disabled";
        WPP_SF_s(v9, v8, WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids, v10);
        goto LABEL_43;
      }
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_DD(*((_QWORD *)WPP_GLOBAL_Control + 2), 230, WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids, v6);
      }
    }
    phkResult[1] = 0;
    phkResult[0] = (HKEY)&hKey;
    v24 = 1;
    v11 = RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"Software\\Microsoft\\Policies\\PassportForWork\\DynamicLock",
            0,
            0x20019u,
            &phkResult[1]);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(phkResult);
    if ( !v11 )
    {
      cbData = 4;
      v12 = RegQueryValueExW(hKey, L"DynamicLock", 0, &Type, Data, &cbData);
      if ( !v12 && Type == 4 )
      {
        v3 = 1;
        v1 = *(_DWORD *)Data != 0;
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
        {
          goto LABEL_43;
        }
        v8 = 231;
        goto LABEL_12;
      }
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control )
      {
LABEL_35:
        CUser::RegQueryDWORD(
          this,
          L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon",
          L"EnableGoodbye",
          *(unsigned int *)Data,
          (unsigned int *)Data);
        v1 = *(_DWORD *)Data != 0;
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
        {
          goto LABEL_43;
        }
        v8 = 234;
        goto LABEL_12;
      }
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
LABEL_31:
        if ( v13 != (CUser *)&WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 0x20) != 0 && *((_BYTE *)v13 + 25) >= 4u )
          WPP_SF_(*((_QWORD *)v13 + 2), 233, WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids);
        goto LABEL_35;
      }
      WPP_SF_DD(*((_QWORD *)WPP_GLOBAL_Control + 2), 232, WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids, v12);
    }
    v13 = WPP_GLOBAL_Control;
    goto LABEL_31;
  }
  v4 = 1;
  if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 228, WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids);
  }
LABEL_43:
  if ( qword_1400D2DA8 )
  {
    *(_OWORD *)phkResult = 0;
    WLGetTSActivityId(phkResult);
    if ( (unsigned int)dword_1400CF778 > 4 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_1400CF778, 0x400000000000LL) )
      {
        v34 = &v15;
        v15 = v3;
        v32 = &v16;
        v16 = v4;
        v30 = &v17;
        v17 = v1;
        v28 = &v22;
        v22 = 0x1000000;
        v26 = phkResult;
        v35 = 1;
        v33 = 1;
        v31 = 1;
        v29 = 8;
        v27 = 16;
        tlgWriteTransfer_EtwEventWriteTransfer(
          (unsigned int)&dword_1400CF778,
          (unsigned int)byte_1400BD03B,
          (_DWORD)qword_1400D2DA8 + 8,
          (unsigned int)phkResult,
          7,
          (__int64)v25);
      }
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return v1;
}

```

## disassembly

```asm
0x140038ef4  mov     [rsp-8+arg_8], rbx
0x140038ef9  mov     [rsp-8+arg_10], rsi
0x140038efe  push    rbp
0x140038eff  push    r12
0x140038f01  push    r13
0x140038f03  push    r14
0x140038f05  push    r15
0x140038f07  lea     rbp, [rsp-37h]
0x140038f0c  sub     rsp, 0F0h
0x140038f13  mov     rax, cs:__security_cookie
0x140038f1a  xor     rax, rsp
0x140038f1d  mov     [rbp+57h+var_30], rax
0x140038f21  xor     ebx, ebx
0x140038f23  mov     r15, rcx
0x140038f26  mov     r12b, bl
0x140038f29  mov     [rbp+57h+hKey], rbx
0x140038f2d  mov     [rsp+110h+cbData], ebx
0x140038f31  mov     [rbp+57h+Type], ebx
0x140038f34  mov     dword ptr [rsp+110h+Data], ebx
0x140038f38  call    ?IsLockWorkstationDisabled@CUser@@QEAAHXZ; CUser::IsLockWorkstationDisabled(void)
0x140038f3d  test    eax, eax
0x140038f3f  jnz     loc_14003920C
0x140038f45  mov     rax, [r15+48h]
0x140038f49  cmp     dword ptr [rax+94h], 3
0x140038f50  jz      loc_14003920C
0x140038f56  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID56916126@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID56916126@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID56916126> `wil::Feature<__WilFeatureTraits_Feature_ID56916126>::GetImpl(void)'::`2'::impl
0x140038f5d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ID56916126@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID56916126>::__private_IsEnabled(void)
0x140038f62  test    al, al
0x140038f64  jz      short loc_140038F77
0x140038f66  mov     rax, [r15+48h]
0x140038f6a  cmp     dword ptr [rax+94h], 4
0x140038f71  jz      loc_14003920C
0x140038f77  lea     rax, [rbp+57h+hKey]
0x140038f7b  mov     [rbp+57h+var_C0+8], rbx
0x140038f7f  mov     [rbp+57h+var_C0], rax
0x140038f83  lea     rdx, aSoftwarePolici_2; "Software\\Policies\\Microsoft\\Passport"...
0x140038f8a  lea     rax, [rbp+57h+var_C0+8]
0x140038f8e  mov     [rbp+57h+var_B0], 1
0x140038f92  mov     r9d, 20019h; samDesired
0x140038f98  mov     [rsp+110h+phkResult], rax; phkResult
0x140038f9d  xor     r8d, r8d; ulOptions
0x140038fa0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140038fa7  mov     r13b, bl
0x140038faa  call    cs:__imp_RegOpenKeyExW
0x140038fb0  lea     rcx, [rbp+57h+var_C0]
0x140038fb4  mov     ebx, eax
0x140038fb6  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x140038fbb  lea     r14, WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids
0x140038fc2  lea     rsi, WPP_GLOBAL_Control
0x140038fc9  test    ebx, ebx
0x140038fcb  jnz     loc_14003909C
0x140038fd1  mov     rcx, [rbp+57h+hKey]; hKey
0x140038fd5  lea     rax, [rsp+110h+cbData]
0x140038fda  mov     [rsp+110h+lpcbData], rax; lpcbData
0x140038fdf  lea     r9, [rbp+57h+Type]; lpType
0x140038fe3  lea     rax, [rsp+110h+Data]
0x140038fe8  mov     [rsp+110h+cbData], 4
0x140038ff0  xor     r8d, r8d; lpReserved
0x140038ff3  mov     [rsp+110h+phkResult], rax; lpData
0x140038ff8  lea     rdx, aDynamiclock; "DynamicLock"
0x140038fff  call    cs:__imp_RegQueryValueExW
0x140039005  mov     r8d, [rbp+57h+Type]
0x140039009  test    eax, eax
0x14003900b  jnz     short loc_14003906B
0x14003900d  cmp     r8d, 4
0x140039011  jnz     short loc_14003906B
0x140039013  cmp     dword ptr [rsp+110h+Data], eax
0x140039017  mov     r12b, 1
0x14003901a  setnz   bl
0x14003901d  mov     rcx, cs:WPP_GLOBAL_Control
0x140039024  cmp     rcx, rsi
0x140039027  jz      loc_140039243
0x14003902d  test    byte ptr [rcx+1Ch], 20h
0x140039031  jz      loc_140039243
0x140039037  cmp     [rcx+19h], r8b
0x14003903b  jb      loc_140039243
0x140039041  mov     edx, 0E5h
0x140039046  mov     rcx, [rcx+10h]
0x14003904a  lea     rax, aDisabled; "Disabled"
0x140039051  test    bl, bl
0x140039053  lea     r9, aEnabled_0; "Enabled"
0x14003905a  mov     r8, r14
0x14003905d  cmovz   r9, rax
0x140039061  call    WPP_SF_s
0x140039066  jmp     loc_140039243
0x14003906b  mov     rcx, cs:WPP_GLOBAL_Control
0x140039072  cmp     rcx, rsi
0x140039075  jz      short loc_14003909C
0x140039077  test    byte ptr [rcx+1Ch], 20h
0x14003907b  jz      short loc_14003909C
0x14003907d  cmp     byte ptr [rcx+19h], 2
0x140039081  jb      short loc_14003909C
0x140039083  mov     rcx, [rcx+10h]
0x140039087  mov     edx, 0E6h
0x14003908c  mov     dword ptr [rsp+110h+phkResult], r8d
0x140039091  mov     r9d, eax
0x140039094  mov     r8, r14
0x140039097  call    WPP_SF_DD
0x14003909c  lea     rax, [rbp+57h+hKey]
0x1400390a0  mov     [rbp+57h+var_C0+8], 0
0x1400390a8  mov     [rbp+57h+var_C0], rax
0x1400390ac  lea     rdx, aSoftwareMicros_38; "Software\\Microsoft\\Policies\\Passport"...
0x1400390b3  lea     rax, [rbp+57h+var_C0+8]
0x1400390b7  mov     [rbp+57h+var_B0], 1
0x1400390bb  mov     r9d, 20019h; samDesired
0x1400390c1  mov     [rsp+110h+phkResult], rax; phkResult
0x1400390c6  xor     r8d, r8d; ulOptions
0x1400390c9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400390d0  call    cs:__imp_RegOpenKeyExW
0x1400390d6  lea     rcx, [rbp+57h+var_C0]
0x1400390da  mov     ebx, eax
0x1400390dc  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x1400390e1  test    ebx, ebx
0x1400390e3  jnz     loc_140039194
0x1400390e9  mov     rcx, [rbp+57h+hKey]; hKey
0x1400390ed  lea     rax, [rsp+110h+cbData]
0x1400390f2  mov     [rsp+110h+lpcbData], rax; lpcbData
0x1400390f7  lea     r9, [rbp+57h+Type]; lpType
0x1400390fb  lea     rax, [rsp+110h+Data]
0x140039100  mov     [rsp+110h+cbData], 4
0x140039108  xor     r8d, r8d; lpReserved
0x14003910b  mov     [rsp+110h+phkResult], rax; lpData
0x140039110  lea     rdx, aDynamiclock; "DynamicLock"
0x140039117  call    cs:__imp_RegQueryValueExW
0x14003911d  mov     r8d, [rbp+57h+Type]
0x140039121  test    eax, eax
0x140039123  jnz     short loc_140039163
0x140039125  cmp     r8d, 4
0x140039129  jnz     short loc_140039163
0x14003912b  cmp     dword ptr [rsp+110h+Data], eax
0x14003912f  mov     r12b, 1
0x140039132  setnz   bl
0x140039135  mov     rcx, cs:WPP_GLOBAL_Control
0x14003913c  cmp     rcx, rsi
0x14003913f  jz      loc_140039243
0x140039145  test    byte ptr [rcx+1Ch], 20h
0x140039149  jz      loc_140039243
0x14003914f  cmp     [rcx+19h], r8b
0x140039153  jb      loc_140039243
0x140039159  mov     edx, 0E7h
0x14003915e  jmp     loc_140039046
0x140039163  mov     rcx, cs:WPP_GLOBAL_Control
0x14003916a  cmp     rcx, rsi
0x14003916d  jz      short loc_1400391BD
0x14003916f  test    byte ptr [rcx+1Ch], 20h
0x140039173  jz      short loc_14003919B
0x140039175  cmp     byte ptr [rcx+19h], 2
0x140039179  jb      short loc_14003919B
0x14003917b  mov     rcx, [rcx+10h]
0x14003917f  mov     edx, 0E8h
0x140039184  mov     dword ptr [rsp+110h+phkResult], r8d
0x140039189  mov     r9d, eax
0x14003918c  mov     r8, r14
0x14003918f  call    WPP_SF_DD
0x140039194  mov     rcx, cs:WPP_GLOBAL_Control
0x14003919b  cmp     rcx, rsi
0x14003919e  jz      short loc_1400391BD
0x1400391a0  test    byte ptr [rcx+1Ch], 20h
0x1400391a4  jz      short loc_1400391BD
0x1400391a6  cmp     byte ptr [rcx+19h], 4
0x1400391aa  jb      short loc_1400391BD
0x1400391ac  mov     rcx, [rcx+10h]
0x1400391b0  mov     edx, 0E9h
0x1400391b5  mov     r8, r14
0x1400391b8  call    WPP_SF_
0x1400391bd  mov     r9d, dword ptr [rsp+110h+Data]; unsigned int
0x1400391c2  lea     rax, [rsp+110h+Data]
0x1400391c7  lea     r8, aEnablegoodbye; "EnableGoodbye"
0x1400391ce  mov     [rsp+110h+phkResult], rax; unsigned int *
0x1400391d3  lea     rdx, aSoftwareMicros_48; "Software\\Microsoft\\Windows NT\\Curren"...
0x1400391da  mov     rcx, r15; this
0x1400391dd  call    ?RegQueryDWORD@CUser@@QEAAKPEBG0KPEAK@Z; CUser::RegQueryDWORD(ushort const *,ushort const *,ulong,ulong *)
0x1400391e2  cmp     dword ptr [rsp+110h+Data], 0
0x1400391e7  setnz   bl
0x1400391ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1400391f1  cmp     rcx, rsi
0x1400391f4  jz      short loc_140039243
0x1400391f6  test    byte ptr [rcx+1Ch], 20h
0x1400391fa  jz      short loc_140039243
0x1400391fc  cmp     byte ptr [rcx+19h], 4
0x140039200  jb      short loc_140039243
0x140039202  mov     edx, 0EAh
0x140039207  jmp     loc_140039046
0x14003920c  mov     r13b, 1
0x14003920f  mov     rcx, cs:WPP_GLOBAL_Control
0x140039216  lea     rsi, WPP_GLOBAL_Control
0x14003921d  cmp     rcx, rsi
0x140039220  jz      short loc_140039243
0x140039222  test    byte ptr [rcx+1Ch], 20h
0x140039226  jz      short loc_140039243
0x140039228  cmp     byte ptr [rcx+19h], 4
0x14003922c  jb      short loc_140039243
0x14003922e  mov     rcx, [rcx+10h]
0x140039232  lea     r8, WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids
0x140039239  mov     edx, 0E4h
0x14003923e  call    WPP_SF_
0x140039243  xor     r14d, r14d
0x140039246  cmp     cs:qword_1400D2DA8, r14
0x14003924d  jz      loc_14003932C
0x140039253  xorps   xmm0, xmm0
0x140039256  lea     rcx, [rbp+57h+var_C0]
0x14003925a  movups  xmmword ptr [rbp+57h+var_C0], xmm0
0x14003925e  call    WLGetTSActivityId
0x140039263  mov     eax, cs:dword_1400CF778
0x140039269  cmp     eax, 4
0x14003926c  jbe     loc_14003932C
0x140039272  mov     rdx, 400000000000h
0x14003927c  lea     rcx, dword_1400CF778
0x140039283  call    _tlgKeywordOn
0x140039288  test    al, al
0x14003928a  jz      loc_14003932C
0x140039290  mov     r8, cs:qword_1400D2DA8
0x140039297  lea     rax, [rsp+110h+var_E0]
0x14003929c  mov     [rbp+57h+var_40], rax
0x1400392a0  lea     r9, [rbp+57h+var_C0]
0x1400392a4  lea     rax, [rsp+110h+var_DF]
0x1400392a9  mov     [rsp+110h+var_E0], r12b
0x1400392ae  mov     [rbp+57h+var_50], rax
0x1400392b2  lea     rdx, byte_1400BD03B
0x1400392b9  lea     rax, [rsp+110h+var_DE]
0x1400392be  mov     [rsp+110h+var_DF], r13b
0x1400392c3  mov     [rbp+57h+var_60], rax
0x1400392c7  lea     rcx, dword_1400CF778
0x1400392ce  lea     rax, [rbp+57h+var_C8]
0x1400392d2  mov     [rsp+110h+var_DE], bl
0x1400392d6  mov     [rbp+57h+var_70], rax
0x1400392da  add     r8, 8
0x1400392de  lea     rax, [rbp+57h+var_C0]
0x1400392e2  mov     [rbp+57h+var_C8], 1000000h
0x1400392ea  mov     [rbp+57h+var_80], rax
0x1400392ee  lea     rax, [rbp+57h+var_A0]
0x1400392f2  mov     [rsp+110h+lpcbData], rax
0x1400392f7  mov     dword ptr [rsp+110h+phkResult], 7
0x1400392ff  mov     [rbp+57h+var_38], 1
0x140039307  mov     [rbp+57h+var_48], 1
0x14003930f  mov     [rbp+57h+var_58], 1
0x140039317  mov     [rbp+57h+var_68], 8
0x14003931f  mov     [rbp+57h+var_78], 10h
0x140039327  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x14003932c  lea     rcx, [rbp+57h+hKey]
0x140039330  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x140039335  movzx   eax, bl
0x140039338  mov     rcx, [rbp+57h+var_30]
0x14003933c  xor     rcx, rsp; StackCookie
0x14003933f  call    __security_check_cookie
0x140039344  lea     r11, [rsp+110h+var_20]
0x14003934c  mov     rbx, [r11+38h]
0x140039350  mov     rsi, [r11+40h]
0x140039354  mov     rsp, r11
0x140039357  pop     r15
0x140039359  pop     r14
0x14003935b  pop     r13
0x14003935d  pop     r12
0x14003935f  pop     rbp
0x140039360  retn
```
