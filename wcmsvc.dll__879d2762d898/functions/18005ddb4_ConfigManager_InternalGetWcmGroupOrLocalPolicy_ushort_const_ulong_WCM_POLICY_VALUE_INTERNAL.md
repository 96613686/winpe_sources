# ConfigManager::InternalGetWcmGroupOrLocalPolicy(ushort const *,ulong,WCM_POLICY_VALUE_INTERNAL *)

- ea: `0x18005ddb4`
- end: `0x18005e142`
- name: `?InternalGetWcmGroupOrLocalPolicy@ConfigManager@@AEAAXPEBGKPEAUWCM_POLICY_VALUE_INTERNAL@@@Z`
- size: `910`
- prototype: `void __fastcall(ConfigManager *__hidden this, const unsigned __int16 *, unsigned int, struct WCM_POLICY_VALUE_INTERNAL *)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18006947c`
- `0x18007c93c`

## callees

- `0x180002190`
- `0x18001b970`
- `0x180027630`
- `0x1800277c0`
- `0x180033860`
- `0x18003fe94`
- `0x180052d30`
- `0x18005ddb4`
- `0x180084f50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005e0db`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005e0db`
- `api-ms-win-core-state-helpers-l1-1-0!GetRegistryValueWithFallbackW` at `0x18005df57`
- `api-ms-win-core-state-helpers-l1-1-0!GetRegistryValueWithFallbackW` at `0x18005dfd4`
- `api-ms-win-core-state-helpers-l1-1-0!GetRegistryValueWithFallbackW` at `0x18005df57`
- `api-ms-win-core-state-helpers-l1-1-0!GetRegistryValueWithFallbackW` at `0x18005dfd4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ConfigManager::InternalGetWcmGroupOrLocalPolicy(
        ConfigManager *this,
        const unsigned __int16 *a2,
        __int64 a3,
        struct WCM_POLICY_VALUE_INTERNAL *a4)
{
  ConfigManager *v5; // rcx
  unsigned int v6; // r8d
  const char *v7; // r9
  int Value; // eax
  char v9; // bl
  ConfigManager *v10; // rcx
  unsigned int v11; // r8d
  int v12; // eax
  __int64 v13; // r10
  int v14; // eax
  __int64 v15; // rcx
  int v16; // edx
  __int64 v17; // rcx
  int RegistryValueWithFallbackW; // eax
  signed int v19; // ebx
  ConfigManager *v20; // rcx
  int v21; // eax
  int v22; // ecx
  int v23; // r8d
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+50h] [rbp-48h] BYREF
  __int64 v25; // [rsp+58h] [rbp-40h] BYREF
  const unsigned __int16 *v26; // [rsp+60h] [rbp-38h] BYREF
  __int64 v27; // [rsp+68h] [rbp-30h] BYREF
  unsigned __int8 v28[8]; // [rsp+70h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  lpCriticalSection = 0;
  wil::EnterCriticalSection(&lpCriticalSection, &s_keyLock);
  ConfigManager::InternalInit(v5);
  *(_QWORD *)a4 = 0;
  if ( !s_wcmGroupPolicyKey )
    goto LABEL_15;
  *(_DWORD *)v28 = 0;
  Value = WcmCommon::Registry::Key::GetValue(
            (WcmCommon::Registry::Key *)&s_wcmGroupPolicyKey,
            L"fBlockNonDomain",
            v6,
            (unsigned __int64)v7,
            v28);
  v9 = Value;
  if ( Value >= 0
    || Value != -2147024894
    && (wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
          &s_wcmGroupPolicyKey,
          0),
        ConfigManager::InternalInit(v10),
        s_wcmGroupPolicyKey)
    && (v12 = WcmCommon::Registry::Key::GetValue(
                (WcmCommon::Registry::Key *)&s_wcmGroupPolicyKey,
                L"fBlockNonDomain",
                v11,
                (unsigned __int64)v7,
                v28),
        v9 = v12,
        v12 >= 0) )
  {
    LOBYTE(v14) = v28[0];
    *(_DWORD *)a4 = *(_DWORD *)v28;
    *((_DWORD *)a4 + 1) = 1;
    v15 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 4u
      || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
    {
      goto LABEL_43;
    }
    v16 = 29;
LABEL_14:
    v17 = *(_QWORD *)(v15 + 16);
LABEL_33:
    WPP_SF_Sd(
      v17,
      v16,
      (unsigned int)WPP_d1926522bc273c8e7056db3405527a30_Traceguids,
      (unsigned int)L"fBlockNonDomain",
      v14);
    goto LABEL_43;
  }
  v13 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u
    && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    WPP_SF_Sd(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      28,
      (unsigned int)WPP_d1926522bc273c8e7056db3405527a30_Traceguids,
      (unsigned int)L"fBlockNonDomain",
      v9);
LABEL_15:
    v13 = WPP_GLOBAL_Control;
  }
  if ( !s_wcmLocalPolicyKey )
    goto LABEL_29;
  *(_DWORD *)v28 = 0;
  RegistryValueWithFallbackW = GetRegistryValueWithFallbackW(
                                 s_wcmLocalPolicyKey,
                                 0,
                                 -2147483646,
                                 L"Software\\Policies\\Microsoft\\Windows\\WcmSvc\\Local",
                                 L"fBlockNonDomain",
                                 16,
                                 0,
                                 v28,
                                 4,
                                 0);
  v19 = RegistryValueWithFallbackW;
  if ( RegistryValueWithFallbackW > 0 )
    v19 = (unsigned __int16)RegistryValueWithFallbackW | 0x80070000;
  if ( v19 >= 0 )
    goto LABEL_39;
  if ( v19 != -2147024894 )
  {
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &s_wcmLocalPolicyKey,
      0);
    ConfigManager::InternalInit(v20);
    if ( s_wcmLocalPolicyKey )
    {
      v21 = GetRegistryValueWithFallbackW(
              s_wcmLocalPolicyKey,
              0,
              -2147483646,
              L"Software\\Policies\\Microsoft\\Windows\\WcmSvc\\Local",
              L"fBlockNonDomain",
              16,
              0,
              v28,
              4,
              0);
      v19 = v21;
      if ( v21 > 0 )
        v19 = (unsigned __int16)v21 | 0x80070000;
      if ( v19 >= 0 )
      {
LABEL_39:
        LOBYTE(v14) = v28[0];
        *(_DWORD *)a4 = *(_DWORD *)v28;
        *((_DWORD *)a4 + 1) = 0;
        v15 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 4u
          || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        {
          goto LABEL_43;
        }
        v16 = 31;
        goto LABEL_14;
      }
    }
  }
  v13 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    goto LABEL_43;
  if ( *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    WPP_SF_Sd(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      30,
      (unsigned int)WPP_d1926522bc273c8e7056db3405527a30_Traceguids,
      (unsigned int)L"fBlockNonDomain",
      v19);
    v13 = WPP_GLOBAL_Control;
  }
LABEL_29:
  if ( (_UNKNOWN *)v13 != &WPP_GLOBAL_Control && *(_BYTE *)(v13 + 25) >= 4u && (*(_BYTE *)(v13 + 28) & 1) != 0 )
  {
    v16 = 32;
    v14 = *(_DWORD *)a4;
    v17 = *(_QWORD *)(v13 + 16);
    goto LABEL_33;
  }
LABEL_43:
  try
  {
    if ( (unsigned int)dword_18013A120 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18013A120, 0x400000000000LL) )
    {
      v25 = 2048;
      *(_DWORD *)v28 = *(_DWORD *)a4;
      v26 = L"fBlockNonDomain";
      v27 = 1;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        v22,
        (unsigned int)byte_18011DF61,
        v23,
        (unsigned int)&v27,
        (__int64)&v26,
        (__int64)v28,
        (__int64)&v25);
    }
    if ( lpCriticalSection )
      LeaveCriticalSection(lpCriticalSection);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x396,
      (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\configmanager\\configmanager.cpp",
      v7);
  }
}

```

## disassembly

```asm
0x18005ddb4  mov     r11, rsp
0x18005ddb7  mov     [r11+8], rbx
0x18005ddbb  mov     [r11+10h], rsi
0x18005ddbf  push    rdi
0x18005ddc0  push    r14
0x18005ddc2  push    r15
0x18005ddc4  sub     rsp, 80h
0x18005ddcb  mov     rax, cs:__security_cookie
0x18005ddd2  xor     rax, rsp
0x18005ddd5  mov     [rsp+98h+var_20], rax
0x18005ddda  mov     rsi, r9
0x18005dddd  xor     r15d, r15d
0x18005dde0  mov     [r11-48h], r15
0x18005dde4  lea     rdx, ?s_keyLock@@3Vcritical_section@wil@@A; wil::critical_section s_keyLock
0x18005ddeb  lea     rcx, [r11-48h]
0x18005ddef  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x18005ddf4  nop
0x18005ddf5  call    ?InternalInit@ConfigManager@@AEAAXXZ; ConfigManager::InternalInit(void)
0x18005ddfa  mov     [rsi], r15
0x18005ddfd  lea     rdi, aFblocknondomai; "fBlockNonDomain"
0x18005de04  cmp     cs:?s_wcmGroupPolicyKey@@3VKey@Registry@WcmCommon@@A, r15; WcmCommon::Registry::Key s_wcmGroupPolicyKey
0x18005de0b  jz      loc_18005DEFB
0x18005de11  mov     dword ptr [rsp+98h+var_28], r15d
0x18005de16  lea     rax, [rsp+98h+var_28]
0x18005de1b  mov     [rsp+98h+var_78], rax; unsigned __int8 *
0x18005de20  mov     rdx, rdi; unsigned __int16 *
0x18005de23  lea     r14, ?s_wcmGroupPolicyKey@@3VKey@Registry@WcmCommon@@A; WcmCommon::Registry::Key s_wcmGroupPolicyKey
0x18005de2a  mov     rcx, r14; this
0x18005de2d  call    ?GetValue@Key@Registry@WcmCommon@@QEBAJQEBGK_KPEAE@Z; WcmCommon::Registry::Key::GetValue(ushort const * const,ulong,unsigned __int64,uchar *)
0x18005de32  mov     ebx, eax
0x18005de34  test    eax, eax
0x18005de36  jns     short loc_18005DEB5
0x18005de38  cmp     eax, 80070002h
0x18005de3d  jz      short loc_18005DE72
0x18005de3f  xor     edx, edx
0x18005de41  mov     rcx, r14
0x18005de44  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18005de49  call    ?InternalInit@ConfigManager@@AEAAXXZ; ConfigManager::InternalInit(void)
0x18005de4e  cmp     cs:?s_wcmGroupPolicyKey@@3VKey@Registry@WcmCommon@@A, r15; WcmCommon::Registry::Key s_wcmGroupPolicyKey
0x18005de55  jz      short loc_18005DE72
0x18005de57  lea     rax, [rsp+98h+var_28]
0x18005de5c  mov     [rsp+98h+var_78], rax; unsigned __int8 *
0x18005de61  mov     rdx, rdi; unsigned __int16 *
0x18005de64  mov     rcx, r14; this
0x18005de67  call    ?GetValue@Key@Registry@WcmCommon@@QEBAJQEBGK_KPEAE@Z; WcmCommon::Registry::Key::GetValue(ushort const * const,ulong,unsigned __int64,uchar *)
0x18005de6c  mov     ebx, eax
0x18005de6e  test    eax, eax
0x18005de70  jns     short loc_18005DEB5
0x18005de72  lea     r14, WPP_GLOBAL_Control
0x18005de79  mov     r10, cs:WPP_GLOBAL_Control
0x18005de80  cmp     r10, r14
0x18005de83  jz      loc_18005DF09
0x18005de89  cmp     byte ptr [r10+19h], 4
0x18005de8e  jb      short loc_18005DF09
0x18005de90  test    byte ptr [r10+1Ch], 1
0x18005de95  jz      short loc_18005DF09
0x18005de97  mov     edx, 1Ch
0x18005de9c  mov     dword ptr [rsp+98h+var_78], ebx
0x18005dea0  mov     r9, rdi
0x18005dea3  lea     r8, WPP_d1926522bc273c8e7056db3405527a30_Traceguids
0x18005deaa  mov     rcx, [r10+10h]
0x18005deae  call    WPP_SF_Sd
0x18005deb3  jmp     short loc_18005DF02
0x18005deb5  mov     eax, dword ptr [rsp+98h+var_28]
0x18005deb9  mov     [rsi], eax
0x18005debb  mov     dword ptr [rsi+4], 1
0x18005dec2  lea     r14, WPP_GLOBAL_Control
0x18005dec9  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ded0  cmp     rcx, r14
0x18005ded3  jz      loc_18005E05F
0x18005ded9  cmp     byte ptr [rcx+19h], 4
0x18005dedd  jb      loc_18005E05F
0x18005dee3  test    byte ptr [rcx+1Ch], 1
0x18005dee7  jz      loc_18005E05F
0x18005deed  mov     edx, 1Dh
0x18005def2  mov     rcx, [rcx+10h]
0x18005def6  jmp     loc_18005E04C
0x18005defb  lea     r14, WPP_GLOBAL_Control
0x18005df02  mov     r10, cs:WPP_GLOBAL_Control
0x18005df09  mov     rcx, cs:?s_wcmLocalPolicyKey@@3VKey@Registry@WcmCommon@@A; WcmCommon::Registry::Key s_wcmLocalPolicyKey
0x18005df10  test    rcx, rcx
0x18005df13  jz      loc_18005E02E
0x18005df19  mov     dword ptr [rsp+98h+var_28], r15d
0x18005df1e  mov     [rsp+98h+var_50], r15
0x18005df23  mov     [rsp+98h+var_58], 4
0x18005df2b  lea     rax, [rsp+98h+var_28]
0x18005df30  mov     [rsp+98h+var_60], rax
0x18005df35  mov     [rsp+98h+var_68], r15
0x18005df3a  mov     dword ptr [rsp+98h+var_70], 10h
0x18005df42  mov     [rsp+98h+var_78], rdi
0x18005df47  lea     r9, aSoftwarePolici_0; "Software\\Policies\\Microsoft\\Windows"...
0x18005df4e  xor     edx, edx
0x18005df50  mov     r8, 0FFFFFFFF80000002h
0x18005df57  call    cs:__imp_GetRegistryValueWithFallbackW
0x18005df5d  mov     ebx, eax
0x18005df5f  test    eax, eax
0x18005df61  jle     short loc_18005DF6C
0x18005df63  movzx   ebx, ax
0x18005df66  or      ebx, 80070000h
0x18005df6c  test    ebx, ebx
0x18005df6e  jns     loc_18005E108
0x18005df74  cmp     ebx, 80070002h
0x18005df7a  jz      short loc_18005DFF1
0x18005df7c  xor     edx, edx
0x18005df7e  lea     rcx, ?s_wcmLocalPolicyKey@@3VKey@Registry@WcmCommon@@A; WcmCommon::Registry::Key s_wcmLocalPolicyKey
0x18005df85  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18005df8a  call    ?InternalInit@ConfigManager@@AEAAXXZ; ConfigManager::InternalInit(void)
0x18005df8f  mov     rcx, cs:?s_wcmLocalPolicyKey@@3VKey@Registry@WcmCommon@@A; WcmCommon::Registry::Key s_wcmLocalPolicyKey
0x18005df96  test    rcx, rcx
0x18005df99  jz      short loc_18005DFF1
0x18005df9b  mov     [rsp+98h+var_50], r15
0x18005dfa0  mov     [rsp+98h+var_58], 4
0x18005dfa8  lea     rax, [rsp+98h+var_28]
0x18005dfad  mov     [rsp+98h+var_60], rax
0x18005dfb2  mov     [rsp+98h+var_68], r15
0x18005dfb7  mov     dword ptr [rsp+98h+var_70], 10h
0x18005dfbf  mov     [rsp+98h+var_78], rdi
0x18005dfc4  lea     r9, aSoftwarePolici_0; "Software\\Policies\\Microsoft\\Windows"...
0x18005dfcb  xor     edx, edx
0x18005dfcd  mov     r8, 0FFFFFFFF80000002h
0x18005dfd4  call    cs:__imp_GetRegistryValueWithFallbackW
0x18005dfda  mov     ebx, eax
0x18005dfdc  test    eax, eax
0x18005dfde  jle     short loc_18005DFE9
0x18005dfe0  movzx   ebx, ax
0x18005dfe3  or      ebx, 80070000h
0x18005dfe9  test    ebx, ebx
0x18005dfeb  jns     loc_18005E108
0x18005dff1  mov     r10, cs:WPP_GLOBAL_Control
0x18005dff8  cmp     r10, r14
0x18005dffb  jz      short loc_18005E05F
0x18005dffd  cmp     byte ptr [r10+19h], 4
0x18005e002  jb      short loc_18005E02E
0x18005e004  test    byte ptr [r10+1Ch], 1
0x18005e009  jz      short loc_18005E02E
0x18005e00b  mov     edx, 1Eh
0x18005e010  mov     dword ptr [rsp+98h+var_78], ebx
0x18005e014  mov     r9, rdi
0x18005e017  lea     r8, WPP_d1926522bc273c8e7056db3405527a30_Traceguids
0x18005e01e  mov     rcx, [r10+10h]
0x18005e022  call    WPP_SF_Sd
0x18005e027  mov     r10, cs:WPP_GLOBAL_Control
0x18005e02e  cmp     r10, r14
0x18005e031  jz      short loc_18005E05F
0x18005e033  cmp     byte ptr [r10+19h], 4
0x18005e038  jb      short loc_18005E05F
0x18005e03a  test    byte ptr [r10+1Ch], 1
0x18005e03f  jz      short loc_18005E05F
0x18005e041  mov     edx, 20h ; ' '
0x18005e046  mov     eax, [rsi]
0x18005e048  mov     rcx, [r10+10h]
0x18005e04c  mov     dword ptr [rsp+98h+var_78], eax
0x18005e050  mov     r9, rdi
0x18005e053  lea     r8, WPP_d1926522bc273c8e7056db3405527a30_Traceguids
0x18005e05a  call    WPP_SF_Sd
0x18005e05f  mov     eax, cs:dword_18013A120
0x18005e065  cmp     eax, 5
0x18005e068  jbe     short loc_18005E0D1
0x18005e06a  mov     rdx, 400000000000h
0x18005e074  lea     rcx, dword_18013A120
0x18005e07b  call    _tlgKeywordOn
0x18005e080  test    al, al
0x18005e082  jz      short loc_18005E0D1
0x18005e084  mov     [rsp+98h+var_40], 800h
0x18005e08d  mov     eax, [rsi]
0x18005e08f  mov     dword ptr [rsp+98h+var_28], eax
0x18005e093  mov     [rsp+98h+var_38], rdi
0x18005e098  mov     [rsp+98h+var_30], 1
0x18005e0a1  lea     rax, [rsp+98h+var_40]
0x18005e0a6  mov     [rsp+98h+var_68], rax
0x18005e0ab  lea     rax, [rsp+98h+var_28]
0x18005e0b0  mov     [rsp+98h+var_70], rax
0x18005e0b5  lea     rax, [rsp+98h+var_38]
0x18005e0ba  mov     [rsp+98h+var_78], rax
0x18005e0bf  lea     r9, [rsp+98h+var_30]
0x18005e0c4  lea     rdx, byte_18011DF61
0x18005e0cb  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBX1IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteAgg@@YAJ011I2@ZPEBX@@SAJPEBU_tlgProvider_t@@PEBX1AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,uint,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,void const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x18005e0d0  nop
0x18005e0d1  mov     rcx, [rsp+98h+lpCriticalSection]; lpCriticalSection
0x18005e0d6  test    rcx, rcx
0x18005e0d9  jz      short loc_18005E0E2
0x18005e0db  call    cs:__imp_LeaveCriticalSection
0x18005e0e1  nop
0x18005e0e2  mov     rcx, [rsp+98h+var_20]
0x18005e0e7  xor     rcx, rsp; StackCookie
0x18005e0ea  call    __security_check_cookie
0x18005e0ef  lea     r11, [rsp+98h+var_18]
0x18005e0f7  mov     rbx, [r11+20h]
0x18005e0fb  mov     rsi, [r11+28h]
0x18005e0ff  mov     rsp, r11
0x18005e102  pop     r15
0x18005e104  pop     r14
0x18005e106  pop     rdi
0x18005e107  retn
0x18005e108  mov     eax, dword ptr [rsp+98h+var_28]
0x18005e10c  mov     [rsi], eax
0x18005e10e  mov     [rsi+4], r15d
0x18005e112  mov     rcx, cs:WPP_GLOBAL_Control
0x18005e119  cmp     rcx, r14
0x18005e11c  jz      loc_18005E05F
0x18005e122  cmp     byte ptr [rcx+19h], 4
0x18005e126  jb      loc_18005E05F
0x18005e12c  test    byte ptr [rcx+1Ch], 1
0x18005e130  jz      loc_18005E05F
0x18005e136  mov     edx, 1Fh
0x18005e13b  jmp     loc_18005DEF2
```
