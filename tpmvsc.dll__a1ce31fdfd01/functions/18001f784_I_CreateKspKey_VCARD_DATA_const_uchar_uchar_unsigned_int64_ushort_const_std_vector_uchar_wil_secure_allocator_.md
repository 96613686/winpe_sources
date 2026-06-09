# I_CreateKspKey(VCARD_DATA const *,uchar,uchar,unsigned __int64 *,ushort const *,std::vector<uchar,wil::secure_allocator<uchar>> const &,int)

- ea: `0x18001f784`
- end: `0x18001fc44`
- name: `?I_CreateKspKey@@YAKPEBUVCARD_DATA@@EEPEA_KPEBGAEBV?$vector@EU?$secure_allocator@E@wil@@@std@@H@Z`
- size: `1216`
- prototype: `__int64 __fastcall(__int64, unsigned __int8, char, NCRYPT_KEY_HANDLE *, LPCWSTR pszKeyName, _QWORD *, int)`
- caller_count: `5`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a81c`
- `0x180016954`
- `0x180024aac`
- `0x1800252d0`
- `0x1800253b0`

## callees

- `0x180001ec0`
- `0x1800068dc`
- `0x18000bc48`
- `0x18000c010`
- `0x18000c124`
- `0x18000c198`
- `0x18001a2f8`
- `0x18001a31c`
- `0x18001cc34`
- `0x18001d3a4`
- `0x18001f784`
- `0x180023840`
- `0x1800348a0`

## import_xrefs

- `ncrypt!NCryptFinalizeKey` at `0x18001fba5`
- `ncrypt!NCryptFinalizeKey` at `0x18001fba5`
- `ncrypt!NCryptCreatePersistedKey` at `0x18001f9a6`
- `ncrypt!NCryptCreatePersistedKey` at `0x18001f9a6`
- `ncrypt!NCryptSetProperty` at `0x18001fa5b`
- `ncrypt!NCryptSetProperty` at `0x18001facd`
- `ncrypt!NCryptSetProperty` at `0x18001fa5b`
- `ncrypt!NCryptSetProperty` at `0x18001facd`

## string_xrefs

- `0x18001f9f6`: `Unable to create KSP key`
- `0x18001f7ca`: `I_CreateKspKey`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall I_CreateKspKey(
        __int64 a1,
        unsigned __int8 a2,
        char a3,
        NCRYPT_KEY_HANDLE *a4,
        LPCWSTR pszKeyName,
        _QWORD *a6,
        int a7)
{
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // rcx
  int v16; // r9d
  unsigned int v17; // ebx
  __int64 v18; // rcx
  SECURITY_STATUS v19; // edi
  _QWORD *v20; // rcx
  int v21; // edx
  const char *v22; // rax
  int v23; // eax
  __int64 v24; // rcx
  __int64 v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rcx
  NCRYPT_KEY_HANDLE v28; // rax
  int v30; // [rsp+30h] [rbp-51h] BYREF
  NCRYPT_KEY_HANDLE phKey; // [rsp+38h] [rbp-49h] BYREF
  BYTE v32[4]; // [rsp+40h] [rbp-41h] BYREF
  int v33; // [rsp+44h] [rbp-3Dh] BYREF
  BYTE pbInput[8]; // [rsp+48h] [rbp-39h] BYREF
  _QWORD *v35; // [rsp+50h] [rbp-31h] BYREF
  _QWORD v36[3]; // [rsp+58h] [rbp-29h] BYREF
  char v37[16]; // [rsp+70h] [rbp-11h] BYREF

  v30 = 0;
  v33 = 0;
  strcpy(v37, "I_CreateKspKey");
  v36[0] = v37;
  v36[1] = &v33;
  v36[2] = &v30;
  lambda_175614b7c72d31d763eb11fada827153_::operator()(v36);
  v33 = 1;
  v35 = v36;
  if ( !a1 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v12, v11);
  if ( !pszKeyName )
    MicrosoftTelemetryAssertTriggeredNoArgs(v12, v11);
  if ( !(unsigned int)I_IsAsymAlg(a2) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v14, v13);
  *(_DWORD *)v32 = 0;
  switch ( a2 & 0xF )
  {
    case 6:
      *(_DWORD *)v32 = 1024;
LABEL_26:
      phKey = 0;
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(
        &phKey,
        0);
      v19 = NCryptCreatePersistedKey(*(_QWORD *)(a1 + 88), &phKey, L"RSA", pszKeyName, 0, a7 != 0 ? 0x80 : 0);
      if ( v19 )
      {
        WppTraceIndent(v18, 2);
        v17 = I_MapSecurityStatusToWinError(v19);
        v30 = v17;
        v20 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_59;
        }
        v21 = 33;
        v22 = "Unable to create KSP key";
      }
      else
      {
        if ( a3 == 2 )
          v23 = 1;
        else
          v23 = (a3 != 4) + 2;
        *(_DWORD *)pbInput = v23;
        v19 = NCryptSetProperty(phKey, L"PCP_KEY_USAGE_POLICY", pbInput, 4u, 0);
        if ( v19 )
        {
          WppTraceIndent(v24, 2);
          v17 = I_MapSecurityStatusToWinError(v19);
          v30 = v17;
          v20 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_59;
          }
          v21 = 34;
          v22 = "Unable to set key usage policy";
        }
        else
        {
          v19 = NCryptSetProperty(phKey, L"Length", v32, 4u, 0);
          if ( v19 )
          {
            WppTraceIndent(v25, 2);
            v17 = I_MapSecurityStatusToWinError(v19);
            v30 = v17;
            v20 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_59;
            }
            v21 = 35;
            v22 = "Unable to set key length";
          }
          else
          {
            if ( *a6 != a6[1] )
            {
              v30 = I_SetPasswordPropertyKspKey(phKey, (wchar_t *)L"SmartCardPin");
              if ( v30 )
              {
                WppTraceIndent(v26, 2);
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  WPP_SF_sDs(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    36,
                    (unsigned int)WPP_ea4669cd28db3200c02309d6e6ed7064_Traceguids,
                    (_DWORD)WPP_pszIndent,
                    v30,
                    (__int64)"Unable to set key password");
                }
                goto LABEL_58;
              }
            }
            v19 = NCryptFinalizeKey(phKey, 0x40u);
            if ( !v19 )
            {
              if ( a4 )
              {
                v28 = phKey;
                phKey = 0;
                *a4 = v28;
              }
              goto LABEL_58;
            }
            WppTraceIndent(v27, 2);
            v17 = I_MapSecurityStatusToWinError(v19);
            v30 = v17;
            v20 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_59;
            }
            v21 = 37;
            v22 = "Unable to finalize key";
          }
        }
      }
      WPP_SF_sDs(
        v20[2],
        v21,
        (unsigned int)WPP_ea4669cd28db3200c02309d6e6ed7064_Traceguids,
        (_DWORD)WPP_pszIndent,
        v19,
        (__int64)v22);
LABEL_58:
      v17 = v30;
LABEL_59:
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phKey);
      goto LABEL_60;
    case 7:
      *(_DWORD *)v32 = 2048;
      goto LABEL_26;
    case 8:
      *(_DWORD *)v32 = 3072;
      goto LABEL_26;
    case 9:
      *(_DWORD *)v32 = 4096;
      goto LABEL_26;
  }
  v15 = (a2 & 0xFu) - 12;
  if ( (a2 & 0xF) != 0xC )
  {
    v15 = (a2 & 0xFu) - 13;
    if ( (unsigned int)v15 >= 2 )
    {
      WppTraceIndent(v15, 2);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        if ( *((_BYTE *)WPP_GLOBAL_Control + 25) )
          WPP_SF_sD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            32,
            (unsigned int)WPP_ea4669cd28db3200c02309d6e6ed7064_Traceguids,
            v16,
            87);
      }
      __fastfail(0x57u);
    }
  }
  WppTraceIndent(v15, 2);
  v17 = 50;
  v30 = 50;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_sDs(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      31,
      (unsigned int)WPP_ea4669cd28db3200c02309d6e6ed7064_Traceguids,
      (_DWORD)WPP_pszIndent,
      50,
      (__int64)"ECC algorithms are not supported");
    v17 = v30;
  }
LABEL_60:
  WppTraceUnwinder__lambda_175614b7c72d31d763eb11fada827153____::_WppTraceUnwinder__lambda_175614b7c72d31d763eb11fada827153____(&v35);
  return v17;
}

```

## disassembly

```asm
0x18001f784  mov     [rsp-8+arg_8], rbx
0x18001f789  push    rbp
0x18001f78a  push    rsi
0x18001f78b  push    rdi
0x18001f78c  push    r12
0x18001f78e  push    r13
0x18001f790  push    r14
0x18001f792  push    r15
0x18001f794  lea     rbp, [rsp-0Fh]
0x18001f799  sub     rsp, 90h
0x18001f7a0  mov     rax, cs:__security_cookie
0x18001f7a7  xor     rax, rsp
0x18001f7aa  mov     [rbp+3Fh+var_40], rax
0x18001f7ae  mov     r14, r9
0x18001f7b1  mov     r15b, r8b
0x18001f7b4  movzx   ebx, dl
0x18001f7b7  mov     r13, rcx
0x18001f7ba  mov     rsi, [rbp+3Fh+arg_28]
0x18001f7be  mov     r12, [rbp+3Fh+pszKeyName]
0x18001f7c2  xor     edi, edi
0x18001f7c4  mov     [rbp+3Fh+var_90], edi
0x18001f7c7  mov     [rbp+3Fh+var_7C], edi
0x18001f7ca  movsd   xmm0, qword ptr cs:aICreatekspkey; "I_CreateKspKey"
0x18001f7d2  movsd   qword ptr [rbp+3Fh+var_50], xmm0
0x18001f7d7  mov     eax, dword ptr cs:aICreatekspkey+8; "KspKey"
0x18001f7dd  mov     dword ptr [rbp+3Fh+var_50+8], eax
0x18001f7e0  movzx   eax, word ptr cs:aICreatekspkey+0Ch; "ey"
0x18001f7e7  mov     word ptr [rbp+3Fh+var_50+0Ch], ax
0x18001f7eb  mov     al, byte ptr cs:aICreatekspkey+0Eh; ""
0x18001f7f1  mov     [rbp+3Fh+var_50+0Eh], al
0x18001f7f4  lea     rax, [rbp+3Fh+var_50]
0x18001f7f8  mov     [rbp+3Fh+var_68], rax
0x18001f7fc  lea     rax, [rbp+3Fh+var_7C]
0x18001f800  mov     [rbp+3Fh+var_60], rax
0x18001f804  lea     rax, [rbp+3Fh+var_90]
0x18001f808  mov     [rbp+3Fh+var_58], rax
0x18001f80c  lea     rcx, [rbp+3Fh+var_68]
0x18001f810  call    _lambda_175614b7c72d31d763eb11fada827153___operator__
0x18001f815  mov     [rbp+3Fh+var_7C], 1
0x18001f81c  lea     rax, [rbp+3Fh+var_68]
0x18001f820  mov     [rbp+3Fh+var_70], rax
0x18001f824  test    r13, r13
0x18001f827  jnz     short loc_18001F82E
0x18001f829  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001f82e  test    r12, r12
0x18001f831  jnz     short loc_18001F838
0x18001f833  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001f838  mov     cl, bl; unsigned __int8
0x18001f83a  call    ?I_IsAsymAlg@@YAHE@Z; I_IsAsymAlg(uchar)
0x18001f83f  test    eax, eax
0x18001f841  jnz     short loc_18001F848
0x18001f843  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001f848  mov     dword ptr [rbp+3Fh+var_80], edi
0x18001f84b  mov     ecx, ebx
0x18001f84d  and     ecx, 0Fh
0x18001f850  mov     eax, 2
0x18001f855  lea     rbx, WPP_GLOBAL_Control
0x18001f85c  sub     ecx, 6
0x18001f85f  jz      loc_18001F95E
0x18001f865  sub     ecx, 1
0x18001f868  jz      loc_18001F955
0x18001f86e  sub     ecx, 1
0x18001f871  jz      loc_18001F94C
0x18001f877  sub     ecx, 1
0x18001f87a  jz      loc_18001F943
0x18001f880  sub     ecx, 3
0x18001f883  jz      short loc_18001F8D7
0x18001f885  sub     ecx, 1
0x18001f888  jz      short loc_18001F8D7
0x18001f88a  cmp     ecx, 1
0x18001f88d  jz      short loc_18001F8D7
0x18001f88f  mov     edx, eax
0x18001f891  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001f896  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f89d  cmp     rcx, rbx
0x18001f8a0  jz      short loc_18001F8CB
0x18001f8a2  test    byte ptr [rcx+1Ch], 1
0x18001f8a6  jz      short loc_18001F8CB
0x18001f8a8  cmp     byte ptr [rcx+19h], 1
0x18001f8ac  jb      short loc_18001F8CB
0x18001f8ae  mov     edx, 20h ; ' '
0x18001f8b3  mov     [rsp+0C0h+dwLegacyKeySpec], 57h ; 'W'
0x18001f8bb  lea     r8, WPP_ea4669cd28db3200c02309d6e6ed7064_Traceguids
0x18001f8c2  mov     rcx, [rcx+10h]
0x18001f8c6  call    WPP_SF_sD
0x18001f8cb  mov     ecx, 57h ; 'W'
0x18001f8d0  int     29h; Win8: RtlFailFast(ecx)
0x18001f8d2  jmp     loc_18001F96C
0x18001f8d7  mov     edx, eax
0x18001f8d9  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001f8de  mov     ebx, 32h ; '2'
0x18001f8e3  mov     [rbp+3Fh+var_90], ebx
0x18001f8e6  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f8ed  lea     rax, WPP_GLOBAL_Control
0x18001f8f4  cmp     rcx, rax
0x18001f8f7  jz      loc_18001FC12
0x18001f8fd  test    byte ptr [rcx+1Ch], 1
0x18001f901  jz      loc_18001FC12
0x18001f907  cmp     byte ptr [rcx+19h], 2
0x18001f90b  jb      loc_18001FC12
0x18001f911  lea     edx, [rbx-13h]
0x18001f914  lea     rax, aEccAlgorithmsA; "ECC algorithms are not supported"
0x18001f91b  mov     qword ptr [rsp+0C0h+dwFlags], rax
0x18001f920  mov     [rsp+0C0h+dwLegacyKeySpec], ebx
0x18001f924  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18001f92b  lea     r8, WPP_ea4669cd28db3200c02309d6e6ed7064_Traceguids
0x18001f932  mov     rcx, [rcx+10h]
0x18001f936  call    WPP_SF_sDs
0x18001f93b  mov     ebx, [rbp+3Fh+var_90]
0x18001f93e  jmp     loc_18001FC12
0x18001f943  mov     dword ptr [rbp+3Fh+var_80], 1000h
0x18001f94a  jmp     short loc_18001F965
0x18001f94c  mov     dword ptr [rbp+3Fh+var_80], 0C00h
0x18001f953  jmp     short loc_18001F965
0x18001f955  mov     dword ptr [rbp+3Fh+var_80], 800h
0x18001f95c  jmp     short loc_18001F965
0x18001f95e  mov     dword ptr [rbp+3Fh+var_80], 400h
0x18001f965  lea     rdi, pszAlgId; "RSA"
0x18001f96c  xor     eax, eax
0x18001f96e  sub     eax, [rbp+3Fh+arg_30]
0x18001f971  neg     eax
0x18001f973  sbb     ebx, ebx
0x18001f975  and     ebx, 80h
0x18001f97b  mov     [rbp+3Fh+phKey], 0
0x18001f983  xor     edx, edx
0x18001f985  lea     rcx, [rbp+3Fh+phKey]
0x18001f989  call    ?reset@?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAAX_K@Z; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(unsigned __int64)
0x18001f98e  mov     [rsp+0C0h+dwFlags], ebx; dwFlags
0x18001f992  xor     ebx, ebx
0x18001f994  mov     [rsp+0C0h+dwLegacyKeySpec], ebx; dwLegacyKeySpec
0x18001f998  mov     r9, r12; pszKeyName
0x18001f99b  mov     r8, rdi; pszAlgId
0x18001f99e  lea     rdx, [rbp+3Fh+phKey]; phKey
0x18001f9a2  mov     rcx, [r13+58h]; hProvider
0x18001f9a6  call    cs:__imp_NCryptCreatePersistedKey
0x18001f9ac  mov     edi, eax
0x18001f9ae  test    eax, eax
0x18001f9b0  jz      short loc_18001FA22
0x18001f9b2  lea     edx, [rbx+2]
0x18001f9b5  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001f9ba  mov     ecx, edi; int
0x18001f9bc  call    ?I_MapSecurityStatusToWinError@@YAKJ@Z; I_MapSecurityStatusToWinError(long)
0x18001f9c1  mov     ebx, eax
0x18001f9c3  mov     [rbp+3Fh+var_90], eax
0x18001f9c6  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f9cd  lea     rax, WPP_GLOBAL_Control
0x18001f9d4  cmp     rcx, rax
0x18001f9d7  jz      loc_18001FC08
0x18001f9dd  test    byte ptr [rcx+1Ch], 1
0x18001f9e1  jz      loc_18001FC08
0x18001f9e7  cmp     byte ptr [rcx+19h], 2
0x18001f9eb  jb      loc_18001FC08
0x18001f9f1  mov     edx, 21h ; '!'
0x18001f9f6  lea     rax, aUnableToCreate_11; "Unable to create KSP key"
0x18001f9fd  mov     qword ptr [rsp+0C0h+dwFlags], rax
0x18001fa02  mov     [rsp+0C0h+dwLegacyKeySpec], edi
0x18001fa06  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18001fa0d  lea     r8, WPP_ea4669cd28db3200c02309d6e6ed7064_Traceguids
0x18001fa14  mov     rcx, [rcx+10h]
0x18001fa18  call    WPP_SF_sDs
0x18001fa1d  jmp     loc_18001FC05
0x18001fa22  mov     r13d, 4
0x18001fa28  lea     r12d, [r13-2]
0x18001fa2c  cmp     r15b, r12b
0x18001fa2f  jnz     short loc_18001FA37
0x18001fa31  lea     eax, [r13-3]
0x18001fa35  jmp     short loc_18001FA42
0x18001fa37  mov     eax, ebx
0x18001fa39  cmp     r15b, r13b
0x18001fa3c  setnz   al
0x18001fa3f  add     eax, r12d
0x18001fa42  mov     dword ptr [rbp+3Fh+pbInput], eax
0x18001fa45  mov     [rsp+0C0h+dwLegacyKeySpec], ebx; dwFlags
0x18001fa49  mov     r9d, r13d; cbInput
0x18001fa4c  lea     r8, [rbp+3Fh+pbInput]; pbInput
0x18001fa50  lea     rdx, aPcpKeyUsagePol; "PCP_KEY_USAGE_POLICY"
0x18001fa57  mov     rcx, [rbp+3Fh+phKey]; hObject
0x18001fa5b  call    cs:__imp_NCryptSetProperty
0x18001fa61  mov     edi, eax
0x18001fa63  test    eax, eax
0x18001fa65  jz      short loc_18001FAB7
0x18001fa67  mov     edx, r12d
0x18001fa6a  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001fa6f  mov     ecx, edi; int
0x18001fa71  call    ?I_MapSecurityStatusToWinError@@YAKJ@Z; I_MapSecurityStatusToWinError(long)
0x18001fa76  mov     ebx, eax
0x18001fa78  mov     [rbp+3Fh+var_90], eax
0x18001fa7b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fa82  lea     rax, WPP_GLOBAL_Control
0x18001fa89  cmp     rcx, rax
0x18001fa8c  jz      loc_18001FC08
0x18001fa92  test    byte ptr [rcx+1Ch], 1
0x18001fa96  jz      loc_18001FC08
0x18001fa9c  cmp     [rcx+19h], r12b
0x18001faa0  jb      loc_18001FC08
0x18001faa6  mov     edx, 22h ; '"'
0x18001faab  lea     rax, aUnableToSetKey_1; "Unable to set key usage policy"
0x18001fab2  jmp     loc_18001F9FD
0x18001fab7  mov     [rsp+0C0h+dwLegacyKeySpec], ebx; dwFlags
0x18001fabb  mov     r9d, r13d; cbInput
0x18001fabe  lea     r8, [rbp+3Fh+var_80]; pbInput
0x18001fac2  lea     rdx, aLength; "Length"
0x18001fac9  mov     rcx, [rbp+3Fh+phKey]; hObject
0x18001facd  call    cs:__imp_NCryptSetProperty
0x18001fad3  mov     edi, eax
0x18001fad5  test    eax, eax
0x18001fad7  jz      short loc_18001FB29
0x18001fad9  mov     edx, r12d
0x18001fadc  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001fae1  mov     ecx, edi; int
0x18001fae3  call    ?I_MapSecurityStatusToWinError@@YAKJ@Z; I_MapSecurityStatusToWinError(long)
0x18001fae8  mov     ebx, eax
0x18001faea  mov     [rbp+3Fh+var_90], eax
0x18001faed  mov     rcx, cs:WPP_GLOBAL_Control
0x18001faf4  lea     rax, WPP_GLOBAL_Control
0x18001fafb  cmp     rcx, rax
0x18001fafe  jz      loc_18001FC08
0x18001fb04  test    byte ptr [rcx+1Ch], 1
0x18001fb08  jz      loc_18001FC08
0x18001fb0e  cmp     [rcx+19h], r12b
0x18001fb12  jb      loc_18001FC08
0x18001fb18  mov     edx, 23h ; '#'
0x18001fb1d  lea     rax, aUnableToSetKey_2; "Unable to set key length"
0x18001fb24  jmp     loc_18001F9FD
0x18001fb29  mov     rax, [rsi+8]
0x18001fb2d  cmp     [rsi], rax
0x18001fb30  jz      short loc_18001FB9C
0x18001fb32  mov     r8, rsi
0x18001fb35  lea     rdx, aSmartcardpin; "SmartCardPin"
0x18001fb3c  mov     rcx, [rbp+3Fh+phKey]; hObject
0x18001fb40  call    I_SetPasswordPropertyKspKey
0x18001fb45  mov     [rbp+3Fh+var_90], eax
0x18001fb48  test    eax, eax
0x18001fb4a  jz      short loc_18001FB9C
0x18001fb4c  mov     edx, r12d
0x18001fb4f  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001fb54  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fb5b  lea     rax, WPP_GLOBAL_Control
0x18001fb62  cmp     rcx, rax
0x18001fb65  jz      loc_18001FC05
0x18001fb6b  test    byte ptr [rcx+1Ch], 1
0x18001fb6f  jz      loc_18001FC05
0x18001fb75  cmp     [rcx+19h], r12b
0x18001fb79  jb      loc_18001FC05
0x18001fb7f  mov     edx, 24h ; '$'
0x18001fb84  lea     rax, aUnableToSetKey_0; "Unable to set key password"
0x18001fb8b  mov     qword ptr [rsp+0C0h+dwFlags], rax
0x18001fb90  mov     eax, [rbp+3Fh+var_90]
0x18001fb93  mov     [rsp+0C0h+dwLegacyKeySpec], eax
0x18001fb97  jmp     loc_18001FA06
0x18001fb9c  mov     edx, 40h ; '@'; dwFlags
0x18001fba1  mov     rcx, [rbp+3Fh+phKey]; hKey
0x18001fba5  call    cs:__imp_NCryptFinalizeKey
0x18001fbab  mov     edi, eax
0x18001fbad  test    eax, eax
0x18001fbaf  jz      short loc_18001FBF5
0x18001fbb1  mov     edx, r12d
0x18001fbb4  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001fbb9  mov     ecx, edi; int
0x18001fbbb  call    ?I_MapSecurityStatusToWinError@@YAKJ@Z; I_MapSecurityStatusToWinError(long)
0x18001fbc0  mov     ebx, eax
0x18001fbc2  mov     [rbp+3Fh+var_90], eax
0x18001fbc5  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fbcc  lea     rax, WPP_GLOBAL_Control
0x18001fbd3  cmp     rcx, rax
0x18001fbd6  jz      short loc_18001FC08
0x18001fbd8  test    byte ptr [rcx+1Ch], 1
0x18001fbdc  jz      short loc_18001FC08
0x18001fbde  cmp     [rcx+19h], r12b
0x18001fbe2  jb      short loc_18001FC08
0x18001fbe4  mov     edx, 25h ; '%'
0x18001fbe9  lea     rax, aUnableToFinali; "Unable to finalize key"
0x18001fbf0  jmp     loc_18001F9FD
0x18001fbf5  test    r14, r14
0x18001fbf8  jz      short loc_18001FC05
0x18001fbfa  mov     rax, [rbp+3Fh+phKey]
0x18001fbfe  mov     [rbp+3Fh+phKey], rbx
0x18001fc02  mov     [r14], rax
0x18001fc05  mov     ebx, [rbp+3Fh+var_90]
0x18001fc08  lea     rcx, [rbp+3Fh+phKey]
0x18001fc0c  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18001fc11  nop
0x18001fc12  lea     rcx, [rbp+3Fh+var_70]
0x18001fc16  call    WppTraceUnwinder__lambda_175614b7c72d31d763eb11fada827153_______WppTraceUnwinder__lambda_175614b7c72d31d763eb11fada827153____
0x18001fc1b  mov     eax, ebx
0x18001fc1d  mov     rcx, [rbp+3Fh+var_40]
0x18001fc21  xor     rcx, rsp; StackCookie
0x18001fc24  call    __security_check_cookie
0x18001fc29  mov     rbx, [rsp+0C0h+arg_8]
0x18001fc31  add     rsp, 90h
0x18001fc38  pop     r15
0x18001fc3a  pop     r14
0x18001fc3c  pop     r13
0x18001fc3e  pop     r12
0x18001fc40  pop     rdi
0x18001fc41  pop     rsi
0x18001fc42  pop     rbp
0x18001fc43  retn
```
