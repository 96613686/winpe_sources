# I_ImportKspKey

- ea: `0x180021be0`
- end: `0x180021f7c`
- name: `I_ImportKspKey`
- size: `924`
- prototype: `__int64 __fastcall(int, int, int, int, LPCWSTR pszKeyName, int, __int64, __int64, int)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180025330`

## callees

- `0x180001ec0`
- `0x1800068dc`
- `0x18000bc48`
- `0x18000c010`
- `0x18000c198`
- `0x18001a31c`
- `0x18001cbe0`
- `0x18001d15c`
- `0x180021be0`
- `0x180023840`
- `0x1800348a0`

## import_xrefs

- `ncrypt!NCryptFinalizeKey` at `0x180021ed4`
- `ncrypt!NCryptFinalizeKey` at `0x180021ed4`
- `ncrypt!NCryptCreatePersistedKey` at `0x180021cda`
- `ncrypt!NCryptCreatePersistedKey` at `0x180021cda`
- `ncrypt!NCryptSetProperty` at `0x180021d77`
- `ncrypt!NCryptSetProperty` at `0x180021e0b`
- `ncrypt!NCryptSetProperty` at `0x180021d77`
- `ncrypt!NCryptSetProperty` at `0x180021e0b`

## string_xrefs

- `0x180021d2e`: `Unable to create asymmetric key`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall I_ImportKspKey(
        __int64 a1,
        __int64 a2,
        int a3,
        NCRYPT_KEY_HANDLE *a4,
        LPCWSTR pszKeyName,
        int a6,
        __int64 a7,
        __int64 a8,
        int a9)
{
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // rcx
  SECURITY_STATUS v14; // edi
  unsigned int v15; // ebx
  __int64 v16; // rcx
  SECURITY_STATUS v17; // ebx
  unsigned int v18; // eax
  _QWORD *v19; // r10
  int v20; // edx
  const char *v21; // rax
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rcx
  NCRYPT_KEY_HANDLE v25; // rax
  unsigned int v27; // [rsp+30h] [rbp-59h] BYREF
  NCRYPT_KEY_HANDLE phKey; // [rsp+38h] [rbp-51h] BYREF
  int v29; // [rsp+40h] [rbp-49h] BYREF
  BYTE pbInput[8]; // [rsp+48h] [rbp-41h] BYREF
  _QWORD *v31; // [rsp+50h] [rbp-39h] BYREF
  _QWORD v32[3]; // [rsp+58h] [rbp-31h] BYREF
  char v33[16]; // [rsp+70h] [rbp-19h] BYREF

  *(_DWORD *)pbInput = a3;
  v27 = 0;
  v29 = 0;
  strcpy(v33, "I_ImportKspKey");
  v32[0] = v33;
  v32[1] = &v29;
  v32[2] = &v27;
  lambda_0c1a35c1fb2b6d68c19a0515e6fe73a8_::operator()(v32);
  v29 = 1;
  v31 = v32;
  if ( !a1 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v12, v11);
  if ( !pszKeyName )
    MicrosoftTelemetryAssertTriggeredNoArgs(v12, v11);
  phKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(
    &phKey,
    0);
  v14 = NCryptCreatePersistedKey(*(_QWORD *)(a1 + 88), &phKey, L"RSA", pszKeyName, 0, a9 != 0 ? 0x80 : 0);
  if ( !v14 )
  {
    v17 = NCryptSetProperty(phKey, L"RSAFULLPRIVATEBLOB", *(PBYTE *)a7, *(_DWORD *)(a7 + 8) - *(_DWORD *)a7, 0);
    if ( v17 )
    {
      WppTraceIndent(v16, 2u);
      v18 = I_MapSecurityStatusToWinError(v17);
      v27 = v18;
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_17;
      }
      v20 = 52;
      v21 = "Unable to import key blob";
    }
    else
    {
      v17 = NCryptSetProperty(phKey, L"PCP_KEY_USAGE_POLICY", pbInput, 4u, 0);
      if ( v17 )
      {
        WppTraceIndent(v22, 2u);
        v18 = I_MapSecurityStatusToWinError(v17);
        v27 = v18;
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_17;
        }
        v20 = 53;
        v21 = "Unable to set key usage policy";
      }
      else
      {
        v27 = I_SetPasswordPropertyKspKey(phKey, (wchar_t *)L"SmartCardPin");
        if ( v27 )
        {
          WppTraceIndent(v23, 2u);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_sDs(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              54,
              (unsigned int)WPP_ea4669cd28db3200c02309d6e6ed7064_Traceguids,
              (_DWORD)WPP_pszIndent,
              v27,
              (__int64)"Unable to set key password");
          }
          goto LABEL_35;
        }
        v17 = NCryptFinalizeKey(phKey, 0x40u);
        if ( !v17 )
        {
          if ( a4 )
          {
            v25 = phKey;
            phKey = 0;
            *a4 = v25;
          }
          goto LABEL_35;
        }
        WppTraceIndent(v24, 2u);
        v18 = I_MapSecurityStatusToWinError(v17);
        v27 = v18;
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_17;
        }
        v20 = 55;
        v21 = "Unable to finalize key";
      }
    }
    WPP_SF_sDs(
      v19[2],
      v20,
      (unsigned int)WPP_ea4669cd28db3200c02309d6e6ed7064_Traceguids,
      (_DWORD)WPP_pszIndent,
      v17,
      (__int64)v21);
    v18 = v27;
LABEL_17:
    v15 = v18;
    goto LABEL_36;
  }
  WppTraceIndent(v13, 2u);
  v15 = I_MapSecurityStatusToWinError(v14);
  v27 = v15;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_sDs(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      51,
      (unsigned int)WPP_ea4669cd28db3200c02309d6e6ed7064_Traceguids,
      (_DWORD)WPP_pszIndent,
      v14,
      (__int64)"Unable to create asymmetric key");
LABEL_35:
    v15 = v27;
  }
LABEL_36:
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phKey);
  WppTraceUnwinder__lambda_0c1a35c1fb2b6d68c19a0515e6fe73a8____::_WppTraceUnwinder__lambda_0c1a35c1fb2b6d68c19a0515e6fe73a8____(&v31);
  return v15;
}

```

## disassembly

```asm
0x180021be0  push    rbp
0x180021be2  push    rbx
0x180021be3  push    rsi
0x180021be4  push    rdi
0x180021be5  push    r13
0x180021be7  push    r14
0x180021be9  push    r15
0x180021beb  lea     rbp, [rsp-7]
0x180021bf0  sub     rsp, 90h
0x180021bf7  mov     rax, cs:__security_cookie
0x180021bfe  xor     rax, rsp
0x180021c01  mov     [rbp+37h+var_40], rax
0x180021c05  mov     rsi, r9
0x180021c08  mov     r13, rcx
0x180021c0b  mov     r14, [rbp+37h+arg_30]
0x180021c0f  mov     dword ptr [rbp+37h+pbInput], r8d
0x180021c13  mov     rdi, [rbp+37h+pszKeyName]
0x180021c17  mov     r15, [rbp+37h+arg_38]
0x180021c1b  mov     [rbp+37h+var_90], 0
0x180021c22  mov     [rbp+37h+var_80], 0
0x180021c29  movsd   xmm0, qword ptr cs:aIImportkspkey; "I_ImportKspKey"
0x180021c31  movsd   qword ptr [rbp+37h+var_50], xmm0
0x180021c36  mov     eax, dword ptr cs:aIImportkspkey+8; "KspKey"
0x180021c3c  mov     dword ptr [rbp+37h+var_50+8], eax
0x180021c3f  movzx   eax, word ptr cs:aIImportkspkey+0Ch; "ey"
0x180021c46  mov     word ptr [rbp+37h+var_50+0Ch], ax
0x180021c4a  mov     al, byte ptr cs:aIImportkspkey+0Eh; ""
0x180021c50  mov     [rbp+37h+var_50+0Eh], al
0x180021c53  lea     rax, [rbp+37h+var_50]
0x180021c57  mov     [rbp+37h+var_68], rax
0x180021c5b  lea     rax, [rbp+37h+var_80]
0x180021c5f  mov     [rbp+37h+var_60], rax
0x180021c63  lea     rax, [rbp+37h+var_90]
0x180021c67  mov     [rbp+37h+var_58], rax
0x180021c6b  lea     rcx, [rbp+37h+var_68]
0x180021c6f  call    _lambda_0c1a35c1fb2b6d68c19a0515e6fe73a8___operator__
0x180021c74  mov     [rbp+37h+var_80], 1
0x180021c7b  lea     rax, [rbp+37h+var_68]
0x180021c7f  mov     [rbp+37h+var_70], rax
0x180021c83  test    r13, r13
0x180021c86  jnz     short loc_180021C8D
0x180021c88  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180021c8d  test    rdi, rdi
0x180021c90  jnz     short loc_180021C97
0x180021c92  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180021c97  xor     eax, eax
0x180021c99  sub     eax, [rbp+37h+arg_40]
0x180021c9f  neg     eax
0x180021ca1  sbb     ebx, ebx
0x180021ca3  and     ebx, 80h
0x180021ca9  mov     [rbp+37h+phKey], 0
0x180021cb1  xor     edx, edx
0x180021cb3  lea     rcx, [rbp+37h+phKey]
0x180021cb7  call    ?reset@?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAAX_K@Z; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(unsigned __int64)
0x180021cbc  mov     [rsp+0C0h+dwFlags], ebx; dwFlags
0x180021cc0  mov     [rsp+0C0h+dwLegacyKeySpec], 0; dwLegacyKeySpec
0x180021cc8  mov     r9, rdi; pszKeyName
0x180021ccb  lea     r8, pszAlgId; "RSA"
0x180021cd2  lea     rdx, [rbp+37h+phKey]; phKey
0x180021cd6  mov     rcx, [r13+58h]; hProvider
0x180021cda  call    cs:__imp_NCryptCreatePersistedKey
0x180021ce0  mov     edi, eax
0x180021ce2  test    eax, eax
0x180021ce4  jz      short loc_180021D5A
0x180021ce6  mov     edx, 2
0x180021ceb  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180021cf0  mov     ecx, edi; int
0x180021cf2  call    ?I_MapSecurityStatusToWinError@@YAKJ@Z; I_MapSecurityStatusToWinError(long)
0x180021cf7  mov     ebx, eax
0x180021cf9  mov     [rbp+37h+var_90], eax
0x180021cfc  lea     rcx, WPP_GLOBAL_Control
0x180021d03  mov     r10, cs:WPP_GLOBAL_Control
0x180021d0a  cmp     r10, rcx
0x180021d0d  jz      loc_180021F49
0x180021d13  test    byte ptr [r10+1Ch], 1
0x180021d18  jz      loc_180021F49
0x180021d1e  cmp     byte ptr [r10+19h], 2
0x180021d23  jb      loc_180021F49
0x180021d29  mov     edx, 33h ; '3'
0x180021d2e  lea     rax, aUnableToCreate_15; "Unable to create asymmetric key"
0x180021d35  mov     qword ptr [rsp+0C0h+dwFlags], rax
0x180021d3a  mov     [rsp+0C0h+dwLegacyKeySpec], edi
0x180021d3e  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180021d45  lea     r8, WPP_ea4669cd28db3200c02309d6e6ed7064_Traceguids
0x180021d4c  mov     rcx, [r10+10h]
0x180021d50  call    WPP_SF_sDs
0x180021d55  jmp     loc_180021F46
0x180021d5a  mov     r9d, [r14+8]
0x180021d5e  sub     r9d, [r14]; cbInput
0x180021d61  mov     [rsp+0C0h+dwLegacyKeySpec], 0; dwFlags
0x180021d69  mov     r8, [r14]; pbInput
0x180021d6c  lea     rdx, aRsafullprivate; "RSAFULLPRIVATEBLOB"
0x180021d73  mov     rcx, [rbp+37h+phKey]; hObject
0x180021d77  call    cs:__imp_NCryptSetProperty
0x180021d7d  mov     ebx, eax
0x180021d7f  test    eax, eax
0x180021d81  jz      short loc_180021DEE
0x180021d83  mov     edx, 2
0x180021d88  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180021d8d  mov     ecx, ebx; int
0x180021d8f  call    ?I_MapSecurityStatusToWinError@@YAKJ@Z; I_MapSecurityStatusToWinError(long)
0x180021d94  mov     [rbp+37h+var_90], eax
0x180021d97  lea     rcx, WPP_GLOBAL_Control
0x180021d9e  mov     r10, cs:WPP_GLOBAL_Control
0x180021da5  cmp     r10, rcx
0x180021da8  jz      short loc_180021DE7
0x180021daa  test    byte ptr [r10+1Ch], 1
0x180021daf  jz      short loc_180021DE7
0x180021db1  cmp     byte ptr [r10+19h], 2
0x180021db6  jb      short loc_180021DE7
0x180021db8  mov     edx, 34h ; '4'
0x180021dbd  lea     rax, aUnableToImport_3; "Unable to import key blob"
0x180021dc4  mov     qword ptr [rsp+0C0h+dwFlags], rax
0x180021dc9  mov     [rsp+0C0h+dwLegacyKeySpec], ebx
0x180021dcd  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180021dd4  lea     r8, WPP_ea4669cd28db3200c02309d6e6ed7064_Traceguids
0x180021ddb  mov     rcx, [r10+10h]
0x180021ddf  call    WPP_SF_sDs
0x180021de4  mov     eax, [rbp+37h+var_90]
0x180021de7  mov     ebx, eax
0x180021de9  jmp     loc_180021F49
0x180021dee  mov     [rsp+0C0h+dwLegacyKeySpec], 0; dwFlags
0x180021df6  mov     r9d, 4; cbInput
0x180021dfc  lea     r8, [rbp+37h+pbInput]; pbInput
0x180021e00  lea     rdx, aPcpKeyUsagePol; "PCP_KEY_USAGE_POLICY"
0x180021e07  mov     rcx, [rbp+37h+phKey]; hObject
0x180021e0b  call    cs:__imp_NCryptSetProperty
0x180021e11  mov     ebx, eax
0x180021e13  test    eax, eax
0x180021e15  jz      short loc_180021E5D
0x180021e17  mov     edx, 2
0x180021e1c  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180021e21  mov     ecx, ebx; int
0x180021e23  call    ?I_MapSecurityStatusToWinError@@YAKJ@Z; I_MapSecurityStatusToWinError(long)
0x180021e28  mov     [rbp+37h+var_90], eax
0x180021e2b  lea     rcx, WPP_GLOBAL_Control
0x180021e32  mov     r10, cs:WPP_GLOBAL_Control
0x180021e39  cmp     r10, rcx
0x180021e3c  jz      short loc_180021DE7
0x180021e3e  test    byte ptr [r10+1Ch], 1
0x180021e43  jz      short loc_180021DE7
0x180021e45  cmp     byte ptr [r10+19h], 2
0x180021e4a  jb      short loc_180021DE7
0x180021e4c  mov     edx, 35h ; '5'
0x180021e51  lea     rax, aUnableToSetKey_1; "Unable to set key usage policy"
0x180021e58  jmp     loc_180021DC4
0x180021e5d  mov     r8, r15
0x180021e60  lea     rdx, aSmartcardpin; "SmartCardPin"
0x180021e67  mov     rcx, [rbp+37h+phKey]; hObject
0x180021e6b  call    I_SetPasswordPropertyKspKey
0x180021e70  mov     [rbp+37h+var_90], eax
0x180021e73  test    eax, eax
0x180021e75  jz      short loc_180021ECB
0x180021e77  mov     edx, 2
0x180021e7c  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180021e81  lea     rcx, WPP_GLOBAL_Control
0x180021e88  mov     r10, cs:WPP_GLOBAL_Control
0x180021e8f  cmp     r10, rcx
0x180021e92  jz      loc_180021F46
0x180021e98  test    byte ptr [r10+1Ch], 1
0x180021e9d  jz      loc_180021F46
0x180021ea3  cmp     byte ptr [r10+19h], 2
0x180021ea8  jb      loc_180021F46
0x180021eae  mov     edx, 36h ; '6'
0x180021eb3  lea     rax, aUnableToSetKey_0; "Unable to set key password"
0x180021eba  mov     qword ptr [rsp+0C0h+dwFlags], rax
0x180021ebf  mov     eax, [rbp+37h+var_90]
0x180021ec2  mov     [rsp+0C0h+dwLegacyKeySpec], eax
0x180021ec6  jmp     loc_180021D3E
0x180021ecb  mov     edx, 40h ; '@'; dwFlags
0x180021ed0  mov     rcx, [rbp+37h+phKey]; hKey
0x180021ed4  call    cs:__imp_NCryptFinalizeKey
0x180021eda  mov     ebx, eax
0x180021edc  test    eax, eax
0x180021ede  jz      short loc_180021F32
0x180021ee0  mov     edx, 2
0x180021ee5  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180021eea  mov     ecx, ebx; int
0x180021eec  call    ?I_MapSecurityStatusToWinError@@YAKJ@Z; I_MapSecurityStatusToWinError(long)
0x180021ef1  mov     [rbp+37h+var_90], eax
0x180021ef4  lea     rcx, WPP_GLOBAL_Control
0x180021efb  mov     r10, cs:WPP_GLOBAL_Control
0x180021f02  cmp     r10, rcx
0x180021f05  jz      loc_180021DE7
0x180021f0b  test    byte ptr [r10+1Ch], 1
0x180021f10  jz      loc_180021DE7
0x180021f16  cmp     byte ptr [r10+19h], 2
0x180021f1b  jb      loc_180021DE7
0x180021f21  mov     edx, 37h ; '7'
0x180021f26  lea     rax, aUnableToFinali; "Unable to finalize key"
0x180021f2d  jmp     loc_180021DC4
0x180021f32  test    rsi, rsi
0x180021f35  jz      short loc_180021F46
0x180021f37  mov     rax, [rbp+37h+phKey]
0x180021f3b  mov     [rbp+37h+phKey], 0
0x180021f43  mov     [rsi], rax
0x180021f46  mov     ebx, [rbp+37h+var_90]
0x180021f49  lea     rcx, [rbp+37h+phKey]
0x180021f4d  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180021f52  nop
0x180021f53  lea     rcx, [rbp+37h+var_70]
0x180021f57  call    WppTraceUnwinder__lambda_0c1a35c1fb2b6d68c19a0515e6fe73a8_______WppTraceUnwinder__lambda_0c1a35c1fb2b6d68c19a0515e6fe73a8____
0x180021f5c  mov     eax, ebx
0x180021f5e  mov     rcx, [rbp+37h+var_40]
0x180021f62  xor     rcx, rsp; StackCookie
0x180021f65  call    __security_check_cookie
0x180021f6a  add     rsp, 90h
0x180021f71  pop     r15
0x180021f73  pop     r14
0x180021f75  pop     r13
0x180021f77  pop     rdi
0x180021f78  pop     rsi
0x180021f79  pop     rbx
0x180021f7a  pop     rbp
0x180021f7b  retn
```
