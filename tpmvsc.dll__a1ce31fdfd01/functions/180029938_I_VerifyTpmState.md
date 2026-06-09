# I_VerifyTpmState

- ea: `0x180029938`
- end: `0x180029cb1`
- name: `I_VerifyTpmState`
- size: `889`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800292e8`

## callees

- `0x1800011ec`
- `0x180001218`
- `0x180001ec0`
- `0x1800068dc`
- `0x18000bc48`
- `0x18000c010`
- `0x18000c0c8`
- `0x18000c198`
- `0x180015384`
- `0x18001a31c`
- `0x1800272f8`
- `0x180027458`
- `0x18002796c`
- `0x180029938`
- `0x180029e80`
- `0x180029f00`
- `0x1800348a0`

## import_xrefs

- `ncrypt!NCryptOpenKey` at `0x180029a75`
- `ncrypt!NCryptOpenKey` at `0x180029a75`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800299f4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800299f4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180029a2b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180029a2b`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180029a86`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180029a86`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall I_VerifyTpmState(__int64 a1)
{
  __int64 v2; // rdx
  __int64 v3; // rcx
  unsigned int v4; // r14d
  DWORD v5; // r15d
  const WCHAR *v6; // rbx
  SECURITY_STATUS v7; // edi
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 v10; // r9
  __int64 v11; // rax
  __int64 v12; // rcx
  unsigned int v13; // ebx
  __int64 v14; // rax
  __int64 v15; // rcx
  __int64 v16; // rax
  __int64 v17; // rdx
  __int64 v18; // rcx
  unsigned int v20; // [rsp+30h] [rbp-39h] BYREF
  BYTE Data[4]; // [rsp+34h] [rbp-35h] BYREF
  DWORD cbData[2]; // [rsp+38h] [rbp-31h] BYREF
  int v23; // [rsp+40h] [rbp-29h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-21h] BYREF
  _QWORD *v25; // [rsp+50h] [rbp-19h] BYREF
  _QWORD v26[3]; // [rsp+58h] [rbp-11h] BYREF
  char v27[24]; // [rsp+70h] [rbp+7h] BYREF

  v20 = 0;
  v23 = 0;
  strcpy(v27, "I_VerifyTpmState");
  v26[0] = v27;
  v26[1] = &v23;
  v26[2] = &v20;
  lambda_6a5662304a6850b5573c4a0437f5f904_::operator()(v26);
  v23 = 1;
  v25 = v26;
  if ( !a1 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v3, v2);
  if ( !*(_QWORD *)(a1 + 64) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v3, v2);
  v4 = 5000;
  hKey = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Policies\\Microsoft\\Windows\\SmartCard", 0, 0x20019u, &hKey) )
  {
    *(_DWORD *)Data = 0;
    cbData[0] = 4;
    if ( !RegQueryValueExW(hKey, L"MaxMsRetryValidateTPM", 0, 0, Data, cbData) )
    {
      v4 = *(_DWORD *)Data;
      if ( *(_DWORD *)Data > 0xEA60u )
        v4 = 60000;
    }
  }
  v5 = 0;
  while ( 1 )
  {
    *(_QWORD *)cbData = 0;
    v6 = *(const WCHAR **)(a1 + 64);
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(
      (NCRYPT_HANDLE *)cbData,
      0);
    v7 = NCryptOpenKey(*(_QWORD *)(a1 + 88), (NCRYPT_KEY_HANDLE *)cbData, v6, 0, 0x40u);
    if ( v7 >= 0 )
      break;
    Sleep(0x64u);
    v5 += 100;
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>((NCRYPT_HANDLE *)cbData);
    if ( v5 >= v4 )
      goto LABEL_14;
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>((NCRYPT_HANDLE *)cbData);
LABEL_14:
  if ( (unsigned int)dword_180048098 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180048098, 0x200000000000LL, v9, v10) )
  {
    cbData[0] = v5;
    *(_DWORD *)Data = v7;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (__int64)&dword_180048098,
      (__int64)&word_18003F19E,
      0,
      0,
      (__int64)Data,
      (__int64)cbData);
  }
  switch ( v7 )
  {
    case -2146893775:
      if ( (Microsoft_Windows_SmartCard_TPM_VCard_ModuleEnableBits & 2) != 0 )
      {
        v11 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
        McTemplateU0z_EventWriteTransfer(v12, EVENT_TPM_VERIFICATION_BLOCKED, v11);
      }
      WppTraceIndent(v8, 2u);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_0b864d11e5aa35941b658d08f6a7e9ca_Traceguids);
      }
      v20 = 0;
      v13 = 0;
      break;
    case -2146893807:
      if ( (Microsoft_Windows_SmartCard_TPM_VCard_ModuleEnableBits & 1) != 0 )
      {
        v14 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
        McTemplateU0z_EventWriteTransfer(v15, EVENT_TPM_VERIFICATION_OWNERSHIP_CHANGED, v14);
      }
      WppTraceIndent(v8, 2u);
      v13 = I_MapSecurityStatusToWinError(0x80090011);
      v20 = v13;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_sDs(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          32,
          (unsigned int)WPP_0b864d11e5aa35941b658d08f6a7e9ca_Traceguids,
          (_DWORD)WPP_pszIndent,
          17,
          (__int64)"TPM verification key cannot be found. TPM ownership may have been changed.");
LABEL_39:
        v13 = v20;
      }
      break;
    case 0:
      goto LABEL_39;
    default:
      if ( (Microsoft_Windows_SmartCard_TPM_VCard_ModuleEnableBits & 1) != 0 )
      {
        v16 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
        McTemplateU0zq_EventWriteTransfer(v18, v17, v16, (unsigned int)v7);
      }
      WppTraceIndent(v8, 2u);
      v13 = I_MapSecurityStatusToWinError(v7);
      v20 = v13;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_sDs(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          33,
          (unsigned int)WPP_0b864d11e5aa35941b658d08f6a7e9ca_Traceguids,
          (_DWORD)WPP_pszIndent,
          v7,
          (__int64)"TPM state verification failed");
        goto LABEL_39;
      }
      break;
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  WppTraceUnwinder__lambda_6a5662304a6850b5573c4a0437f5f904____::_WppTraceUnwinder__lambda_6a5662304a6850b5573c4a0437f5f904____(&v25);
  return v13;
}

```

## disassembly

```asm
0x180029938  push    rbp
0x18002993a  push    rbx
0x18002993b  push    rsi
0x18002993c  push    rdi
0x18002993d  push    r14
0x18002993f  push    r15
0x180029941  lea     rbp, [rsp-2Fh]
0x180029946  sub     rsp, 98h
0x18002994d  mov     rax, cs:__security_cookie
0x180029954  xor     rax, rsp
0x180029957  mov     [rbp+57h+var_38], rax
0x18002995b  mov     rsi, rcx
0x18002995e  mov     [rbp+57h+var_90], 0
0x180029965  mov     [rbp+57h+var_80], 0
0x18002996c  movups  xmm0, xmmword ptr cs:aIVerifytpmstat; "I_VerifyTpmState"
0x180029973  movups  xmmword ptr [rbp+57h+var_50], xmm0
0x180029977  mov     al, byte ptr cs:aIVerifytpmstat+10h; ""
0x18002997d  mov     [rbp+57h+var_50+10h], al
0x180029980  lea     rax, [rbp+57h+var_50]
0x180029984  mov     [rbp+57h+var_68], rax
0x180029988  lea     rax, [rbp+57h+var_80]
0x18002998c  mov     [rbp+57h+var_60], rax
0x180029990  lea     rax, [rbp+57h+var_90]
0x180029994  mov     [rbp+57h+var_58], rax
0x180029998  lea     rcx, [rbp+57h+var_68]
0x18002999c  call    _lambda_6a5662304a6850b5573c4a0437f5f904___operator__
0x1800299a1  mov     [rbp+57h+var_80], 1
0x1800299a8  lea     rax, [rbp+57h+var_68]
0x1800299ac  mov     [rbp+57h+var_70], rax
0x1800299b0  test    rsi, rsi
0x1800299b3  jnz     short loc_1800299BA
0x1800299b5  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800299ba  cmp     qword ptr [rsi+40h], 0
0x1800299bf  jnz     short loc_1800299C6
0x1800299c1  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800299c6  mov     r14d, 1388h
0x1800299cc  mov     [rbp+57h+hKey], 0
0x1800299d4  lea     rax, [rbp+57h+hKey]
0x1800299d8  mov     [rsp+0C0h+phkResult], rax; phkResult
0x1800299dd  mov     r9d, 20019h; samDesired
0x1800299e3  xor     r8d, r8d; ulOptions
0x1800299e6  lea     rdx, SubKey; "Software\\Policies\\Microsoft\\Windows"...
0x1800299ed  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800299f4  call    cs:__imp_RegOpenKeyExW
0x1800299fa  test    eax, eax
0x1800299fc  jnz     short loc_180029A45
0x1800299fe  mov     dword ptr [rbp+57h+Data], eax
0x180029a01  mov     [rbp+57h+cbData], 4
0x180029a08  lea     rax, [rbp+57h+cbData]
0x180029a0c  mov     [rsp+0C0h+lpcbData], rax; lpcbData
0x180029a11  lea     rax, [rbp+57h+Data]
0x180029a15  mov     [rsp+0C0h+phkResult], rax; lpData
0x180029a1a  xor     r9d, r9d; lpType
0x180029a1d  xor     r8d, r8d; lpReserved
0x180029a20  lea     rdx, aMaxmsretryvali; "MaxMsRetryValidateTPM"
0x180029a27  mov     rcx, [rbp+57h+hKey]; hKey
0x180029a2b  call    cs:__imp_RegQueryValueExW
0x180029a31  test    eax, eax
0x180029a33  jnz     short loc_180029A45
0x180029a35  mov     r14d, dword ptr [rbp+57h+Data]
0x180029a39  mov     eax, 0EA60h
0x180029a3e  cmp     r14d, eax
0x180029a41  cmova   r14d, eax
0x180029a45  xor     r15d, r15d
0x180029a48  mov     qword ptr [rbp+57h+cbData], 0
0x180029a50  mov     rbx, [rsi+40h]
0x180029a54  xor     edx, edx
0x180029a56  lea     rcx, [rbp+57h+cbData]
0x180029a5a  call    ?reset@?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAAX_K@Z; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(unsigned __int64)
0x180029a5f  mov     dword ptr [rsp+0C0h+phkResult], 40h ; '@'; dwFlags
0x180029a67  xor     r9d, r9d; dwLegacyKeySpec
0x180029a6a  mov     r8, rbx; pszKeyName
0x180029a6d  lea     rdx, [rbp+57h+cbData]; phKey
0x180029a71  mov     rcx, [rsi+58h]; hProvider
0x180029a75  call    cs:__imp_NCryptOpenKey
0x180029a7b  mov     edi, eax
0x180029a7d  test    eax, eax
0x180029a7f  jns     short loc_180029AA0
0x180029a81  mov     ecx, 64h ; 'd'; dwMilliseconds
0x180029a86  call    cs:__imp_Sleep
0x180029a8c  add     r15d, 64h ; 'd'
0x180029a90  lea     rcx, [rbp+57h+cbData]
0x180029a94  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180029a99  cmp     r15d, r14d
0x180029a9c  jb      short loc_180029A48
0x180029a9e  jmp     short loc_180029AA9
0x180029aa0  lea     rcx, [rbp+57h+cbData]
0x180029aa4  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180029aa9  mov     eax, cs:dword_180048098
0x180029aaf  cmp     eax, 5
0x180029ab2  jbe     short loc_180029B00
0x180029ab4  mov     rdx, 200000000000h
0x180029abe  lea     rcx, dword_180048098
0x180029ac5  call    _tlgKeywordOn
0x180029aca  test    al, al
0x180029acc  jz      short loc_180029B00
0x180029ace  mov     [rbp+57h+cbData], r15d
0x180029ad2  mov     dword ptr [rbp+57h+Data], edi
0x180029ad5  lea     rax, [rbp+57h+cbData]
0x180029ad9  mov     [rsp+0C0h+lpcbData], rax
0x180029ade  lea     rax, [rbp+57h+Data]
0x180029ae2  mov     [rsp+0C0h+phkResult], rax
0x180029ae7  xor     r9d, r9d
0x180029aea  xor     r8d, r8d
0x180029aed  lea     rdx, word_18003F19E
0x180029af4  lea     rcx, dword_180048098
0x180029afb  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180029b00  cmp     edi, 80090031h
0x180029b06  jnz     short loc_180029B75
0x180029b08  test    cs:Microsoft_Windows_SmartCard_TPM_VCard_ModuleEnableBits, 2
0x180029b0f  jz      short loc_180029B29
0x180029b11  lea     rcx, [rsi+18h]
0x180029b15  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180029b1a  mov     r8, rax
0x180029b1d  lea     rdx, EVENT_TPM_VERIFICATION_BLOCKED
0x180029b24  call    McTemplateU0z_EventWriteTransfer
0x180029b29  mov     edx, 2
0x180029b2e  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180029b33  lea     rax, WPP_GLOBAL_Control
0x180029b3a  mov     rcx, cs:WPP_GLOBAL_Control
0x180029b41  cmp     rcx, rax
0x180029b44  jz      short loc_180029B67
0x180029b46  test    byte ptr [rcx+1Ch], 1
0x180029b4a  jz      short loc_180029B67
0x180029b4c  cmp     byte ptr [rcx+19h], 3
0x180029b50  jb      short loc_180029B67
0x180029b52  mov     edx, 1Fh
0x180029b57  lea     r8, WPP_0b864d11e5aa35941b658d08f6a7e9ca_Traceguids
0x180029b5e  mov     rcx, [rcx+10h]
0x180029b62  call    WPP_SF_s
0x180029b67  mov     [rbp+57h+var_90], 0
0x180029b6e  xor     ebx, ebx
0x180029b70  jmp     loc_180029C80
0x180029b75  mov     ebx, 80090011h
0x180029b7a  cmp     edi, ebx
0x180029b7c  jnz     short loc_180029BFB
0x180029b7e  test    cs:Microsoft_Windows_SmartCard_TPM_VCard_ModuleEnableBits, 1
0x180029b85  jz      short loc_180029B9F
0x180029b87  lea     rcx, [rsi+18h]
0x180029b8b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180029b90  mov     r8, rax
0x180029b93  lea     rdx, EVENT_TPM_VERIFICATION_OWNERSHIP_CHANGED
0x180029b9a  call    McTemplateU0z_EventWriteTransfer
0x180029b9f  mov     edx, 2
0x180029ba4  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180029ba9  mov     ecx, ebx; int
0x180029bab  call    ?I_MapSecurityStatusToWinError@@YAKJ@Z; I_MapSecurityStatusToWinError(long)
0x180029bb0  mov     ebx, eax
0x180029bb2  mov     [rbp+57h+var_90], eax
0x180029bb5  lea     rax, WPP_GLOBAL_Control
0x180029bbc  mov     rcx, cs:WPP_GLOBAL_Control
0x180029bc3  cmp     rcx, rax
0x180029bc6  jz      loc_180029C80
0x180029bcc  test    byte ptr [rcx+1Ch], 1
0x180029bd0  jz      loc_180029C80
0x180029bd6  cmp     byte ptr [rcx+19h], 2
0x180029bda  jb      loc_180029C80
0x180029be0  mov     edx, 20h ; ' '
0x180029be5  lea     rax, aTpmVerificatio; "TPM verification key cannot be found. T"...
0x180029bec  mov     [rsp+0C0h+lpcbData], rax
0x180029bf1  mov     dword ptr [rsp+0C0h+phkResult], 80090011h
0x180029bf9  jmp     short loc_180029C66
0x180029bfb  test    edi, edi
0x180029bfd  jz      short loc_180029C7D
0x180029bff  test    cs:Microsoft_Windows_SmartCard_TPM_VCard_ModuleEnableBits, 1
0x180029c06  jz      short loc_180029C1C
0x180029c08  lea     rcx, [rsi+18h]
0x180029c0c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180029c11  mov     r9d, edi
0x180029c14  mov     r8, rax
0x180029c17  call    McTemplateU0zq_EventWriteTransfer
0x180029c1c  mov     edx, 2
0x180029c21  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180029c26  mov     ecx, edi; int
0x180029c28  call    ?I_MapSecurityStatusToWinError@@YAKJ@Z; I_MapSecurityStatusToWinError(long)
0x180029c2d  mov     ebx, eax
0x180029c2f  mov     [rbp+57h+var_90], eax
0x180029c32  lea     rax, WPP_GLOBAL_Control
0x180029c39  mov     rcx, cs:WPP_GLOBAL_Control
0x180029c40  cmp     rcx, rax
0x180029c43  jz      short loc_180029C80
0x180029c45  test    byte ptr [rcx+1Ch], 1
0x180029c49  jz      short loc_180029C80
0x180029c4b  cmp     byte ptr [rcx+19h], 2
0x180029c4f  jb      short loc_180029C80
0x180029c51  mov     edx, 21h ; '!'
0x180029c56  lea     rax, aTpmStateVerifi; "TPM state verification failed"
0x180029c5d  mov     [rsp+0C0h+lpcbData], rax
0x180029c62  mov     dword ptr [rsp+0C0h+phkResult], edi
0x180029c66  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180029c6d  lea     r8, WPP_0b864d11e5aa35941b658d08f6a7e9ca_Traceguids
0x180029c74  mov     rcx, [rcx+10h]
0x180029c78  call    WPP_SF_sDs
0x180029c7d  mov     ebx, [rbp+57h+var_90]
0x180029c80  lea     rcx, [rbp+57h+hKey]
0x180029c84  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180029c89  nop
0x180029c8a  lea     rcx, [rbp+57h+var_70]
0x180029c8e  call    WppTraceUnwinder__lambda_6a5662304a6850b5573c4a0437f5f904_______WppTraceUnwinder__lambda_6a5662304a6850b5573c4a0437f5f904____
0x180029c93  mov     eax, ebx
0x180029c95  mov     rcx, [rbp+57h+var_38]
0x180029c99  xor     rcx, rsp; StackCookie
0x180029c9c  call    __security_check_cookie
0x180029ca1  add     rsp, 98h
0x180029ca8  pop     r15
0x180029caa  pop     r14
0x180029cac  pop     rdi
0x180029cad  pop     rsi
0x180029cae  pop     rbx
0x180029caf  pop     rbp
0x180029cb0  retn
```
