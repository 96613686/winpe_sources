# I_LoadKspKey(VCARD_DATA const *,ushort const *,std::vector<uchar,wil::secure_allocator<uchar>> const &,unsigned __int64 *)

- ea: `0x180022e80`
- end: `0x18002306f`
- name: `?I_LoadKspKey@@YAKPEBUVCARD_DATA@@PEBGAEBV?$vector@EU?$secure_allocator@E@wil@@@std@@PEA_K@Z`
- size: `495`
- prototype: `__int64 __fastcall(__int64, const WCHAR *, _QWORD *, NCRYPT_KEY_HANDLE *)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000f6a0`
- `0x1800121dc`

## callees

- `0x180001ec0`
- `0x1800068dc`
- `0x18000bc48`
- `0x18000c010`
- `0x18000c198`
- `0x18001a31c`
- `0x18001cc50`
- `0x18001d414`
- `0x18001e9a8`
- `0x180022e80`
- `0x1800348a0`

## import_xrefs

- `ncrypt!NCryptOpenKey` at `0x180022f4f`
- `ncrypt!NCryptOpenKey` at `0x180022f4f`

## string_xrefs

- `0x180022fa1`: `Unable to open KSP key`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall I_LoadKspKey(__int64 a1, const WCHAR *a2, _QWORD *a3, NCRYPT_KEY_HANDLE *a4)
{
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // rcx
  SECURITY_STATUS v11; // edi
  unsigned int v12; // ebx
  __int64 v13; // rcx
  NCRYPT_KEY_HANDLE v14; // rax
  unsigned int v16; // [rsp+30h] [rbp-50h] BYREF
  NCRYPT_KEY_HANDLE phKey; // [rsp+38h] [rbp-48h] BYREF
  int v18; // [rsp+40h] [rbp-40h] BYREF
  _QWORD *v19; // [rsp+48h] [rbp-38h] BYREF
  _QWORD v20[3]; // [rsp+50h] [rbp-30h] BYREF
  char v21[16]; // [rsp+68h] [rbp-18h] BYREF

  v16 = 0;
  v18 = 0;
  strcpy(v21, "I_LoadKspKey");
  v20[0] = v21;
  v20[1] = &v18;
  v20[2] = &v16;
  lambda_185f1a48f2483c747532de9f1d050a6e_::operator()(v20);
  v18 = 1;
  v19 = v20;
  if ( !a1 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v9, v8);
  if ( !a2 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v9, v8);
  if ( !a4 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v9, v8);
  phKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(
    &phKey,
    0);
  v11 = NCryptOpenKey(*(_QWORD *)(a1 + 88), &phKey, a2, 0, 0x40u);
  if ( !v11 )
  {
    if ( *a3 == a3[1] )
    {
      v12 = v16;
    }
    else
    {
      v12 = I_AuthenticateKspKey(phKey);
      v16 = v12;
      if ( v12 )
      {
        WppTraceIndent(v13, 2);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_sDs(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            40,
            (unsigned int)WPP_ea4669cd28db3200c02309d6e6ed7064_Traceguids,
            (_DWORD)WPP_pszIndent,
            v16,
            (__int64)"Unable to set key password");
        }
        goto LABEL_18;
      }
    }
    v14 = phKey;
    phKey = 0;
    *a4 = v14;
    goto LABEL_21;
  }
  WppTraceIndent(v10, 2);
  v12 = I_MapSecurityStatusToWinError(v11);
  v16 = v12;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_sDs(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      39,
      (unsigned int)WPP_ea4669cd28db3200c02309d6e6ed7064_Traceguids,
      (_DWORD)WPP_pszIndent,
      v11,
      (__int64)"Unable to open KSP key");
LABEL_18:
    v12 = v16;
  }
LABEL_21:
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phKey);
  WppTraceUnwinder__lambda_185f1a48f2483c747532de9f1d050a6e____::_WppTraceUnwinder__lambda_185f1a48f2483c747532de9f1d050a6e____(&v19);
  return v12;
}

```

## disassembly

```asm
0x180022e80  push    rbp
0x180022e82  push    rbx
0x180022e83  push    rsi
0x180022e84  push    rdi
0x180022e85  push    r14
0x180022e87  mov     rbp, rsp
0x180022e8a  sub     rsp, 80h
0x180022e91  mov     rax, cs:__security_cookie
0x180022e98  xor     rax, rsp
0x180022e9b  mov     [rbp+var_8], rax
0x180022e9f  mov     rsi, r9
0x180022ea2  mov     rbx, r8
0x180022ea5  mov     rdi, rdx
0x180022ea8  mov     r14, rcx
0x180022eab  mov     [rbp+var_50], 0
0x180022eb2  mov     [rbp+var_40], 0
0x180022eb9  movsd   xmm0, qword ptr cs:aILoadkspkey; "I_LoadKspKey"
0x180022ec1  movsd   qword ptr [rbp+var_18], xmm0
0x180022ec6  mov     eax, dword ptr cs:aILoadkspkey+8; "pKey"
0x180022ecc  mov     dword ptr [rbp+var_18+8], eax
0x180022ecf  mov     al, byte ptr cs:aILoadkspkey+0Ch; ""
0x180022ed5  mov     [rbp+var_18+0Ch], al
0x180022ed8  lea     rax, [rbp+var_18]
0x180022edc  mov     [rbp+var_30], rax
0x180022ee0  lea     rax, [rbp+var_40]
0x180022ee4  mov     [rbp+var_28], rax
0x180022ee8  lea     rax, [rbp+var_50]
0x180022eec  mov     [rbp+var_20], rax
0x180022ef0  lea     rcx, [rbp+var_30]
0x180022ef4  call    _lambda_185f1a48f2483c747532de9f1d050a6e___operator__
0x180022ef9  mov     [rbp+var_40], 1
0x180022f00  lea     rax, [rbp+var_30]
0x180022f04  mov     [rbp+var_38], rax
0x180022f08  test    r14, r14
0x180022f0b  jnz     short loc_180022F12
0x180022f0d  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180022f12  test    rdi, rdi
0x180022f15  jnz     short loc_180022F1C
0x180022f17  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180022f1c  test    rsi, rsi
0x180022f1f  jnz     short loc_180022F26
0x180022f21  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180022f26  mov     [rbp+phKey], 0
0x180022f2e  xor     edx, edx
0x180022f30  lea     rcx, [rbp+phKey]
0x180022f34  call    ?reset@?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAAX_K@Z; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(unsigned __int64)
0x180022f39  mov     [rsp+80h+dwFlags], 40h ; '@'; dwFlags
0x180022f41  xor     r9d, r9d; dwLegacyKeySpec
0x180022f44  mov     r8, rdi; pszKeyName
0x180022f47  lea     rdx, [rbp+phKey]; phKey
0x180022f4b  mov     rcx, [r14+58h]; hProvider
0x180022f4f  call    cs:__imp_NCryptOpenKey
0x180022f55  mov     edi, eax
0x180022f57  test    eax, eax
0x180022f59  jz      short loc_180022FB3
0x180022f5b  mov     edx, 2
0x180022f60  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180022f65  mov     ecx, edi; int
0x180022f67  call    ?I_MapSecurityStatusToWinError@@YAKJ@Z; I_MapSecurityStatusToWinError(long)
0x180022f6c  mov     ebx, eax
0x180022f6e  mov     [rbp+var_50], eax
0x180022f71  lea     rdx, WPP_GLOBAL_Control
0x180022f78  mov     rcx, cs:WPP_GLOBAL_Control
0x180022f7f  cmp     rcx, rdx
0x180022f82  jz      loc_180023040
0x180022f88  test    byte ptr [rcx+1Ch], 1
0x180022f8c  jz      loc_180023040
0x180022f92  cmp     byte ptr [rcx+19h], 2
0x180022f96  jb      loc_180023040
0x180022f9c  mov     edx, 27h ; '''
0x180022fa1  lea     rax, aUnableToOpenKs; "Unable to open KSP key"
0x180022fa8  mov     [rsp+80h+var_58], rax
0x180022fad  mov     [rsp+80h+dwFlags], edi
0x180022fb1  jmp     short loc_180023012
0x180022fb3  mov     rax, [rbx+8]
0x180022fb7  cmp     [rbx], rax
0x180022fba  jz      short loc_18002302E
0x180022fbc  mov     rdx, rbx
0x180022fbf  mov     rcx, [rbp+phKey]; hObject
0x180022fc3  call    ?I_AuthenticateKspKey@@YAK_KAEBV?$vector@EU?$secure_allocator@E@wil@@@std@@@Z; I_AuthenticateKspKey(unsigned __int64,std::vector<uchar,wil::secure_allocator<uchar>> const &)
0x180022fc8  mov     ebx, eax
0x180022fca  mov     [rbp+var_50], eax
0x180022fcd  test    eax, eax
0x180022fcf  jz      short loc_180023031
0x180022fd1  mov     edx, 2
0x180022fd6  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180022fdb  lea     rdx, WPP_GLOBAL_Control
0x180022fe2  mov     rcx, cs:WPP_GLOBAL_Control
0x180022fe9  cmp     rcx, rdx
0x180022fec  jz      short loc_180023029
0x180022fee  test    byte ptr [rcx+1Ch], 1
0x180022ff2  jz      short loc_180023029
0x180022ff4  cmp     byte ptr [rcx+19h], 2
0x180022ff8  jb      short loc_180023029
0x180022ffa  mov     edx, 28h ; '('
0x180022fff  lea     rax, aUnableToSetKey_0; "Unable to set key password"
0x180023006  mov     [rsp+80h+var_58], rax
0x18002300b  mov     eax, [rbp+var_50]
0x18002300e  mov     [rsp+80h+dwFlags], eax
0x180023012  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180023019  lea     r8, WPP_ea4669cd28db3200c02309d6e6ed7064_Traceguids
0x180023020  mov     rcx, [rcx+10h]
0x180023024  call    WPP_SF_sDs
0x180023029  mov     ebx, [rbp+var_50]
0x18002302c  jmp     short loc_180023040
0x18002302e  mov     ebx, [rbp+var_50]
0x180023031  mov     rax, [rbp+phKey]
0x180023035  mov     [rbp+phKey], 0
0x18002303d  mov     [rsi], rax
0x180023040  lea     rcx, [rbp+phKey]
0x180023044  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180023049  nop
0x18002304a  lea     rcx, [rbp+var_38]
0x18002304e  call    WppTraceUnwinder__lambda_185f1a48f2483c747532de9f1d050a6e_______WppTraceUnwinder__lambda_185f1a48f2483c747532de9f1d050a6e____
0x180023053  mov     eax, ebx
0x180023055  mov     rcx, [rbp+var_8]
0x180023059  xor     rcx, rsp; StackCookie
0x18002305c  call    __security_check_cookie
0x180023061  add     rsp, 80h
0x180023068  pop     r14
0x18002306a  pop     rdi
0x18002306b  pop     rsi
0x18002306c  pop     rbx
0x18002306d  pop     rbp
0x18002306e  retn
```
