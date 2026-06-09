# CredentialManager::ReadSubscriptionEntries(HKEY__ *,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &)

- ea: `0x18001b998`
- end: `0x18001bcec`
- name: `?ReadSubscriptionEntries@CredentialManager@@AEAAXPEAUHKEY__@@AEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@11@Z`
- size: `852`
- prototype: `__int64 __fastcall(__int64, HKEY, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001ab58`

## callees

- `0x18000195c`
- `0x1800032dc`
- `0x180003e6c`
- `0x1800062d4`
- `0x180006898`
- `0x180011c24`
- `0x180011d6c`
- `0x180011e68`
- `0x180011f40`
- `0x1800128c0`
- `0x18001b998`
- `0x18001fe50`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001ba85`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001ba85`

## string_xrefs

- `0x18001b9fe`: `CommonUserName`
- `0x18001ba15`: `CommonPassword`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CredentialManager::ReadSubscriptionEntries(__int64 a1, HKEY a2, __int64 a3, __int64 a4, __int64 a5)
{
  unsigned int v8; // eax
  unsigned int v9; // ebx
  HKEY v10; // rdx
  unsigned int v11; // ebx
  HKEY CurrentSubKey; // rbx
  HKEY phkResult; // [rsp+30h] [rbp-D0h] BYREF
  void **pExceptionObject; // [rsp+38h] [rbp-C8h] BYREF
  char v16; // [rsp+40h] [rbp-C0h]
  const char *v17; // [rsp+48h] [rbp-B8h]
  __int64 v18; // [rsp+50h] [rbp-B0h]
  __int64 v19; // [rsp+58h] [rbp-A8h]
  unsigned int v20; // [rsp+60h] [rbp-A0h]
  int v21; // [rsp+64h] [rbp-9Ch]
  int v22; // [rsp+68h] [rbp-98h]
  HKEY v23; // [rsp+70h] [rbp-90h] BYREF
  HKEY v24; // [rsp+78h] [rbp-88h] BYREF
  int v25; // [rsp+80h] [rbp-80h]
  _QWORD v26[4]; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD v27[4]; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD v28[4]; // [rsp+F0h] [rbp-10h] BYREF

  v28[3] = 7;
  v28[2] = 0;
  LOWORD(v28[0]) = 0;
  v27[3] = 7;
  v27[2] = 0;
  LOWORD(v27[0]) = 0;
  v26[3] = 7;
  v26[2] = 0;
  LOWORD(v26[0]) = 0;
  if ( (unsigned __int8)RegReadStringValue(a2, L"CommonUserName", v28)
    && (unsigned __int8)RegReadStringValue(a2, L"CommonPassword", v27)
    && (unsigned __int8)RegReadStringValue(a2, L"CredSourceId", v26) )
  {
    std::vector<std::wstring>::push_back(a3, v26);
    std::vector<std::wstring>::push_back(a4, v28);
    std::vector<std::wstring>::push_back(a5, v27);
  }
  phkResult = 0;
  v8 = RegOpenKeyExW(a2, L"EventSources", 0, 0x20019u, &phkResult);
  v9 = v8;
  if ( v8 != 2 )
  {
    if ( v8 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_3b54ed34bb4835de3895f7d36279b99a_Traceguids, v8);
      }
      v16 = 0;
      v17 = "admin\\wmi\\events\\forwarding\\collector\\store\\credentialmanager.cpp";
      v18 = 0;
      v19 = 0;
      v20 = v9;
      v21 = -1;
      v22 = 109;
      pExceptionObject = &wmi::GenericException::`vftable';
      throw (wmi::GenericException *)&pExceptionObject;
    }
    v10 = phkResult;
    phkResult = 0;
    RegistryKeyEnumerator::RegistryKeyEnumerator((RegistryKeyEnumerator *)&v24, v10);
    v25 = 0;
    v11 = RegistryKeyEnumerator::MoveNext((RegistryKeyEnumerator *)&v24);
    while ( !v11 )
    {
      CurrentSubKey = RegistryKeyEnumerator::GetCurrentSubKey((RegistryKeyEnumerator *)&v24, 0x20019u);
      v23 = CurrentSubKey;
      if ( (unsigned __int8)RegReadStringValue(CurrentSubKey, L"UserName", v28)
        && (unsigned __int8)RegReadStringValue(CurrentSubKey, L"TargetId", v27)
        && (unsigned __int8)RegReadStringValue(CurrentSubKey, L"CredSourceId", v26) )
      {
        std::vector<std::wstring>::push_back(a3, v26);
        std::vector<std::wstring>::push_back(a4, v28);
        std::vector<std::wstring>::push_back(a5, v27);
      }
      v11 = RegistryKeyEnumerator::MoveNext((RegistryKeyEnumerator *)&v24);
      wmi::AutoRegKey::Close(&v23);
    }
    if ( v11 != 259 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_3b54ed34bb4835de3895f7d36279b99a_Traceguids, v11);
      }
      v16 = 0;
      v17 = "admin\\wmi\\events\\forwarding\\collector\\store\\credentialmanager.cpp";
      v18 = 0;
      v19 = 0;
      v20 = v11;
      v21 = -1;
      v22 = 131;
      pExceptionObject = &wmi::GenericException::`vftable';
      throw (wmi::GenericException *)&pExceptionObject;
    }
    RegistryKeyEnumerator::~RegistryKeyEnumerator(&v24);
  }
  wmi::AutoRegKey::Close(&phkResult);
  std::wstring::_Tidy(v26, 1, 0);
  std::wstring::_Tidy(v27, 1, 0);
  return std::wstring::_Tidy(v28, 1, 0);
}

```

## disassembly

```asm
0x18001b998  mov     [rsp-8+arg_0], rbx
0x18001b99d  push    rbp
0x18001b99e  push    rsi
0x18001b99f  push    rdi
0x18001b9a0  push    r14
0x18001b9a2  push    r15
0x18001b9a4  lea     rbp, [rsp-20h]
0x18001b9a9  sub     rsp, 120h
0x18001b9b0  mov     rax, cs:__security_cookie
0x18001b9b7  xor     rax, rsp
0x18001b9ba  mov     [rbp+40h+var_30], rax
0x18001b9be  mov     rsi, r9
0x18001b9c1  mov     rdi, r8
0x18001b9c4  mov     rbx, rdx
0x18001b9c7  mov     r14, [rbp+40h+arg_20]
0x18001b9cb  mov     ecx, 7
0x18001b9d0  mov     [rbp+40h+var_38], rcx
0x18001b9d4  xor     r15d, r15d
0x18001b9d7  mov     [rbp+40h+var_40], r15
0x18001b9db  mov     [rbp+40h+var_50], r15w
0x18001b9e0  mov     [rbp+40h+var_58], rcx
0x18001b9e4  mov     [rbp+40h+var_60], r15
0x18001b9e8  mov     [rbp+40h+var_70], r15w
0x18001b9ed  mov     [rbp+40h+var_78], rcx
0x18001b9f1  mov     [rbp+40h+var_80], r15
0x18001b9f5  mov     [rbp+40h+var_90], r15w
0x18001b9fa  lea     r8, [rbp+40h+var_50]
0x18001b9fe  lea     rdx, aCommonusername; "CommonUserName"
0x18001ba05  mov     rcx, rbx
0x18001ba08  call    ?RegReadStringValue@@YA_NPEAUHKEY__@@PEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; RegReadStringValue(HKEY__ *,ushort const *,std::wstring &)
0x18001ba0d  test    al, al
0x18001ba0f  jz      short loc_18001BA63
0x18001ba11  lea     r8, [rbp+40h+var_70]
0x18001ba15  lea     rdx, aCommonpassword; "CommonPassword"
0x18001ba1c  mov     rcx, rbx
0x18001ba1f  call    ?RegReadStringValue@@YA_NPEAUHKEY__@@PEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; RegReadStringValue(HKEY__ *,ushort const *,std::wstring &)
0x18001ba24  test    al, al
0x18001ba26  jz      short loc_18001BA63
0x18001ba28  lea     r8, [rbp+40h+var_90]
0x18001ba2c  lea     rdx, aCredsourceid; "CredSourceId"
0x18001ba33  mov     rcx, rbx
0x18001ba36  call    ?RegReadStringValue@@YA_NPEAUHKEY__@@PEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; RegReadStringValue(HKEY__ *,ushort const *,std::wstring &)
0x18001ba3b  test    al, al
0x18001ba3d  jz      short loc_18001BA63
0x18001ba3f  lea     rdx, [rbp+40h+var_90]
0x18001ba43  mov     rcx, rdi
0x18001ba46  call    ?push_back@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::vector<std::wstring>::push_back(std::wstring const &)
0x18001ba4b  lea     rdx, [rbp+40h+var_50]
0x18001ba4f  mov     rcx, rsi
0x18001ba52  call    ?push_back@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::vector<std::wstring>::push_back(std::wstring const &)
0x18001ba57  lea     rdx, [rbp+40h+var_70]
0x18001ba5b  mov     rcx, r14
0x18001ba5e  call    ?push_back@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::vector<std::wstring>::push_back(std::wstring const &)
0x18001ba63  mov     [rsp+140h+var_110], r15
0x18001ba68  lea     rax, [rsp+140h+var_110]
0x18001ba6d  mov     [rsp+140h+phkResult], rax; phkResult
0x18001ba72  mov     r9d, 20019h; samDesired
0x18001ba78  xor     r8d, r8d; ulOptions
0x18001ba7b  lea     rdx, aEventsources; "EventSources"
0x18001ba82  mov     rcx, rbx; hKey
0x18001ba85  call    cs:__imp_RegOpenKeyExW
0x18001ba8b  mov     ebx, eax
0x18001ba8d  cmp     eax, 2
0x18001ba90  jz      loc_18001BC92
0x18001ba96  test    eax, eax
0x18001ba98  jz      loc_18001BB22
0x18001ba9e  lea     rax, WPP_GLOBAL_Control
0x18001baa5  mov     rcx, cs:WPP_GLOBAL_Control
0x18001baac  cmp     rcx, rax
0x18001baaf  jz      short loc_18001BAD5
0x18001bab1  test    byte ptr [rcx+1Ch], 40h
0x18001bab5  jz      short loc_18001BAD5
0x18001bab7  cmp     byte ptr [rcx+19h], 2
0x18001babb  jb      short loc_18001BAD5
0x18001babd  mov     edx, 0Dh
0x18001bac2  mov     r9d, ebx
0x18001bac5  lea     r8, WPP_3b54ed34bb4835de3895f7d36279b99a_Traceguids
0x18001bacc  mov     rcx, [rcx+10h]
0x18001bad0  call    WPP_SF_D
0x18001bad5  mov     [rsp+140h+var_100], r15b
0x18001bada  lea     rax, aAdminWmiEvents_9; "admin\\wmi\\events\\forwarding\\collect"...
0x18001bae1  mov     [rsp+140h+var_F8], rax
0x18001bae6  mov     [rsp+140h+var_F0], r15
0x18001baeb  mov     [rsp+140h+var_E8], r15
0x18001baf0  mov     [rsp+140h+var_E0], ebx
0x18001baf4  mov     [rsp+140h+var_DC], 0FFFFFFFFh
0x18001bafc  mov     [rsp+140h+var_D8], 6Dh ; 'm'
0x18001bb04  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18001bb0b  mov     [rsp+140h+pExceptionObject], rax
0x18001bb10  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18001bb17  lea     rcx, [rsp+140h+pExceptionObject]; pExceptionObject
0x18001bb1c  call    _CxxThrowException_0
0x18001bb22  mov     rdx, [rsp+140h+var_110]; HKEY
0x18001bb27  mov     [rsp+140h+var_110], r15
0x18001bb2c  lea     rcx, [rsp+140h+var_C8]; this
0x18001bb31  call    ??0RegistryKeyEnumerator@@QEAA@PEAUHKEY__@@@Z; RegistryKeyEnumerator::RegistryKeyEnumerator(HKEY__ *)
0x18001bb36  nop
0x18001bb37  mov     [rbp+40h+var_C0], r15d
0x18001bb3b  lea     rcx, [rsp+140h+var_C8]; this
0x18001bb40  call    ?MoveNext@RegistryKeyEnumerator@@QEAAKXZ; RegistryKeyEnumerator::MoveNext(void)
0x18001bb45  mov     ebx, eax
0x18001bb47  test    eax, eax
0x18001bb49  jnz     loc_18001BBED
0x18001bb4f  mov     edx, 20019h; unsigned int
0x18001bb54  lea     rcx, [rsp+140h+var_C8]; this
0x18001bb59  call    ?GetCurrentSubKey@RegistryKeyEnumerator@@QEBAPEAUHKEY__@@K@Z; RegistryKeyEnumerator::GetCurrentSubKey(ulong)
0x18001bb5e  mov     rbx, rax
0x18001bb61  mov     [rsp+140h+var_D0], rax
0x18001bb66  lea     r8, [rbp+40h+var_50]
0x18001bb6a  lea     rdx, aUsername; "UserName"
0x18001bb71  mov     rcx, rax
0x18001bb74  call    ?RegReadStringValue@@YA_NPEAUHKEY__@@PEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; RegReadStringValue(HKEY__ *,ushort const *,std::wstring &)
0x18001bb79  test    al, al
0x18001bb7b  jz      short loc_18001BBCF
0x18001bb7d  lea     r8, [rbp+40h+var_70]
0x18001bb81  lea     rdx, aTargetid; "TargetId"
0x18001bb88  mov     rcx, rbx
0x18001bb8b  call    ?RegReadStringValue@@YA_NPEAUHKEY__@@PEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; RegReadStringValue(HKEY__ *,ushort const *,std::wstring &)
0x18001bb90  test    al, al
0x18001bb92  jz      short loc_18001BBCF
0x18001bb94  lea     r8, [rbp+40h+var_90]
0x18001bb98  lea     rdx, aCredsourceid; "CredSourceId"
0x18001bb9f  mov     rcx, rbx
0x18001bba2  call    ?RegReadStringValue@@YA_NPEAUHKEY__@@PEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; RegReadStringValue(HKEY__ *,ushort const *,std::wstring &)
0x18001bba7  test    al, al
0x18001bba9  jz      short loc_18001BBCF
0x18001bbab  lea     rdx, [rbp+40h+var_90]
0x18001bbaf  mov     rcx, rdi
0x18001bbb2  call    ?push_back@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::vector<std::wstring>::push_back(std::wstring const &)
0x18001bbb7  lea     rdx, [rbp+40h+var_50]
0x18001bbbb  mov     rcx, rsi
0x18001bbbe  call    ?push_back@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::vector<std::wstring>::push_back(std::wstring const &)
0x18001bbc3  lea     rdx, [rbp+40h+var_70]
0x18001bbc7  mov     rcx, r14
0x18001bbca  call    ?push_back@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::vector<std::wstring>::push_back(std::wstring const &)
0x18001bbcf  lea     rcx, [rsp+140h+var_C8]; this
0x18001bbd4  call    ?MoveNext@RegistryKeyEnumerator@@QEAAKXZ; RegistryKeyEnumerator::MoveNext(void)
0x18001bbd9  mov     ebx, eax
0x18001bbdb  lea     rcx, [rsp+140h+var_D0]; this
0x18001bbe0  call    ?Close@AutoRegKey@wmi@@QEAAXXZ; wmi::AutoRegKey::Close(void)
0x18001bbe5  test    ebx, ebx
0x18001bbe7  jz      loc_18001BB4F
0x18001bbed  cmp     ebx, 103h
0x18001bbf3  jz      loc_18001BC87
0x18001bbf9  mov     eax, 507h
0x18001bbfe  test    ebx, ebx
0x18001bc00  cmovz   ebx, eax
0x18001bc03  lea     rax, WPP_GLOBAL_Control
0x18001bc0a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bc11  cmp     rcx, rax
0x18001bc14  jz      short loc_18001BC3A
0x18001bc16  test    byte ptr [rcx+1Ch], 40h
0x18001bc1a  jz      short loc_18001BC3A
0x18001bc1c  cmp     byte ptr [rcx+19h], 2
0x18001bc20  jb      short loc_18001BC3A
0x18001bc22  mov     edx, 0Eh
0x18001bc27  mov     r9d, ebx
0x18001bc2a  lea     r8, WPP_3b54ed34bb4835de3895f7d36279b99a_Traceguids
0x18001bc31  mov     rcx, [rcx+10h]
0x18001bc35  call    WPP_SF_D
0x18001bc3a  mov     [rsp+140h+var_100], r15b
0x18001bc3f  lea     rax, aAdminWmiEvents_9; "admin\\wmi\\events\\forwarding\\collect"...
0x18001bc46  mov     [rsp+140h+var_F8], rax
0x18001bc4b  mov     [rsp+140h+var_F0], r15
0x18001bc50  mov     [rsp+140h+var_E8], r15
0x18001bc55  mov     [rsp+140h+var_E0], ebx
0x18001bc59  mov     [rsp+140h+var_DC], 0FFFFFFFFh
0x18001bc61  mov     [rsp+140h+var_D8], 83h
0x18001bc69  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18001bc70  mov     [rsp+140h+pExceptionObject], rax
0x18001bc75  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18001bc7c  lea     rcx, [rsp+140h+pExceptionObject]; pExceptionObject
0x18001bc81  call    _CxxThrowException_0
0x18001bc87  lea     rcx, [rsp+140h+var_C8]; this
0x18001bc8c  call    ??1RegistryKeyEnumerator@@QEAA@XZ; RegistryKeyEnumerator::~RegistryKeyEnumerator(void)
0x18001bc91  nop
0x18001bc92  lea     rcx, [rsp+140h+var_110]; this
0x18001bc97  call    ?Close@AutoRegKey@wmi@@QEAAXXZ; wmi::AutoRegKey::Close(void)
0x18001bc9c  nop
0x18001bc9d  xor     r8d, r8d
0x18001bca0  mov     dl, 1
0x18001bca2  lea     rcx, [rbp+40h+var_90]
0x18001bca6  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18001bcab  nop
0x18001bcac  xor     r8d, r8d
0x18001bcaf  mov     dl, 1
0x18001bcb1  lea     rcx, [rbp+40h+var_70]
0x18001bcb5  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18001bcba  nop
0x18001bcbb  xor     r8d, r8d
0x18001bcbe  mov     dl, 1
0x18001bcc0  lea     rcx, [rbp+40h+var_50]
0x18001bcc4  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18001bcc9  mov     rcx, [rbp+40h+var_30]
0x18001bccd  xor     rcx, rsp; StackCookie
0x18001bcd0  call    __security_check_cookie
0x18001bcd5  mov     rbx, [rsp+140h+arg_0]
0x18001bcdd  add     rsp, 120h
0x18001bce4  pop     r15
0x18001bce6  pop     r14
0x18001bce8  pop     rdi
0x18001bce9  pop     rsi
0x18001bcea  pop     rbp
0x18001bceb  retn
```
